# $OpenBSD: Makefile,v 1.7 2021/01/16 03:50:32 jsg Exp $

COMMENT =	reverse-engineered ports of Build games

DISTNAME =	nblood-1.01.20210115

GH_ACCOUNT =	nukeykt
GH_PROJECT =	NBlood
GH_COMMIT =	6ae5ab57d788328dd61a12dab9c9600c982adec1
CATEGORIES =	games x11

VC_BRANCH =	master
# git rev-list --count hash
VC_REV =	12112
# git rev-parse --short=9 hash
VC_HASH =	edc76dee4

MAINTAINER =	Jonathan Gray <jsg@openbsd.org>

# GPLv2, BUILD license and shareware data
PERMIT_PACKAGE =    "BUILD engine license is not compatible with GPLv2."
PERMIT_DISTFILES =  "BUILD engine license is not compatible with GPLv2."

BUILD_DEPENDS = archivers/unzip \
		graphics/gdk-pixbuf2

WANTLIB += c m ogg pthread vorbis vorbisfile vpx lz4 xmp
WANTLIB += SDL2 FLAC execinfo ${COMPILER_LIBCXX}

LIB_DEPENDS =	archivers/lz4 \
		audio/libxmp \
		audio/libvorbis \
		audio/flac \
		devel/sdl2 \
		devel/libexecinfo \
		multimedia/libvpx

# dlopen()'d; shows as Extra in check-lib-depends but it is used
LIB_DEPENDS +=	x11/gtk+2
WANTLIB +=	gtk-x11-2.0

COMPILER =	base-clang ports-gcc

# make sure we can see compilation output, respect CC/CXX, don't strip!
MAKE_FLAGS +=	PRETTY_OUTPUT=0 \
		CC="${CC}" \
		CXX="${CXX}" \
		STRIP=true \
		PACKAGE_REPOSITORY=1 \
		NOASM=1
MAKE_FILE =	GNUmakefile
USE_GMAKE =	Yes
NO_TEST =	Yes

# Fix "undefined reference to `__atomic_load_8'"
.if ${MACHINE_ARCH:Mhppa}
WANTLIB +=	atomic
MAKE_FLAGS +=	LDFLAGS="${LDFLAGS} -latomic"
.endif

.include <bsd.port.arch.mk>

.if !${PROPERTIES:Mlld}
MAKE_FLAGS +=	LTO=0
.endif

post-extract:
	# check for data files in correct location
	@sed -i "s,/usr/share/games/eduke32,${TRUEPREFIX}/share/rednukem," \
		${WRKSRC}/source/rr/src/common.cpp
	@sed -i "s,/usr/share/games/nblood,${TRUEPREFIX}/share/nblood," \
		${WRKSRC}/source/blood/src/common.cpp
	rm ${WRKSRC}/source/build/include/lz4.h ${WRKSRC}/source/build/src/lz4.c

post-patch:
	echo "VC_BRANCH := ${VC_BRANCH}" > ${WRKSRC}/EDUKE32_REVISION.mak
	echo "VC_REV := ${VC_REV}" >> ${WRKSRC}/EDUKE32_REVISION.mak
	echo "VC_HASH := ${VC_HASH}" >> ${WRKSRC}/EDUKE32_REVISION.mak

do-install:
	${INSTALL_PROGRAM} ${WRKBUILD}/nblood ${PREFIX}/bin
	${INSTALL_PROGRAM} ${WRKBUILD}/rednukem ${PREFIX}/bin
	${INSTALL_PROGRAM} ${WRKBUILD}/pcexhumed ${PREFIX}/bin
	${INSTALL_DATA_DIR} ${PREFIX}/share/nblood
	${INSTALL_DATA_DIR} ${PREFIX}/share/rednukem
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/nblood
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/nblood
	${INSTALL_DATA} ${WRKDIST}/{AUTHORS,README}.md \
		${PREFIX}/share/doc/nblood/
	# eduke32/mapster32 licenses
	${INSTALL_DATA} ${WRKDIST}/package/common/gpl-2.0.txt \
		 ${PREFIX}/share/doc/nblood/
	${INSTALL_DATA} ${WRKDIST}/package/common/buildlic.txt \
		${PREFIX}/share/doc/nblood/
	# sample game mapping/modding data files
	${INSTALL_DATA} ${WRKDIST}/package/sdk/samples/* \
		${PREFIX}/share/examples/nblood/

.include <bsd.port.mk>
