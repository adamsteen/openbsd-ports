# $OpenBSD: Makefile,v 1.14 2020/11/03 16:12:32 rsadowski Exp $

COMMENT =	KDE image viewer
DISTNAME =	gwenview-${VERSION}
CATEGORIES =	graphics x11

SHARED_LIBS +=  gwenviewlib               55.0 # 4.97

WANTLIB += ${COMPILER_LIBCXX} KF5Activities KF5Auth KF5AuthCore
WANTLIB += KF5Baloo KF5Bookmarks KF5Codecs KF5Completion KF5ConfigCore
WANTLIB += KF5ConfigGui KF5ConfigWidgets KF5CoreAddons KF5FileMetaData
WANTLIB += KF5I18n KF5IconThemes KF5ItemModels KF5ItemViews KF5JobWidgets
WANTLIB += KF5KDcraw KF5KIOCore KF5KIOFileWidgets KF5KIOGui KF5KIOWidgets
WANTLIB += KF5Kipi KF5Notifications KF5Parts KF5Purpose KF5PurposeWidgets
WANTLIB += KF5Service KF5Solid KF5SonnetUi KF5TextWidgets KF5WidgetsAddons
WANTLIB += KF5WindowSystem KF5XmlGui Qt5Concurrent Qt5Core Qt5DBus
WANTLIB += Qt5Gui Qt5Network Qt5OpenGL Qt5PrintSupport Qt5Svg
WANTLIB += Qt5Widgets Qt5X11Extras Qt5Xml X11 c cfitsio exiv2
WANTLIB += jpeg lcms2 m phonon4qt5 png tiff z

MODKDE5_DESKTOP_FILE = yes
MODKDE5_ICON_CACHE = yes
MODKDE5_TRANSLATIONS = yes
MODKF5_I18N_CONFLICT = yes
MODKF5_L10N_CONFLICT = yes
MODKDE5_DOCS = yes

RUN_DEPENDS =	devel/kf5/kfilemetadata \
		devel/kf5/baloo,-icons \
		x11/kde-applications/ffmpegthumbs \
		x11/kde-applications/kio-extras

LIB_DEPENDS =	devel/kf5/baloo,-main \
		devel/kf5/kactivities \
		devel/kf5/kauth \
		devel/kf5/kbookmarks \
		devel/kf5/kcodecs \
		devel/kf5/kcompletion \
		devel/kf5/kconfig \
		devel/kf5/kconfigwidgets \
		devel/kf5/kcoreaddons \
		devel/kf5/kfilemetadata \
		devel/kf5/ki18n \
		devel/kf5/kiconthemes \
		devel/kf5/kio \
		devel/kf5/kitemmodels \
		devel/kf5/kitemviews \
		devel/kf5/kjobwidgets \
		devel/kf5/knotifications \
		devel/kf5/kparts \
		devel/kf5/kservice\
		devel/kf5/purpose \
		devel/kf5/solid \
		devel/kf5/sonnet \
		graphics/exiv2 \
		graphics/jpeg \
		graphics/lcms2 \
		graphics/png \
		math/cfitsio \
		x11/kde-applications/libkdcraw \
		x11/kde-applications/libkipi \
		x11/qt5/qtsvg \
		x11/qt5/qtx11extras \
		multimedia/phonon

TEST_IS_INTERACTIVE =	X11

.include <bsd.port.mk>
