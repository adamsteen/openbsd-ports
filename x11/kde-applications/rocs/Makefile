# $OpenBSD: Makefile,v 1.10 2021/01/23 18:10:29 rsadowski Exp $

COMMENT =	graph theory IDE for KDE
DISTNAME =	rocs-${VERSION}
CATEGORIES =	games education

HOMEPAGE =	https://www.kde.org/applications/education/rocs/

SHARED_LIBS +=  rocsgraphtheory        2.0 # 0.0

WANTLIB += ${COMPILER_LIBCXX} Grantlee_Templates KF5Archive KF5Auth
WANTLIB += KF5AuthCore KF5Codecs KF5Completion KF5ConfigCore KF5ConfigGui
WANTLIB += KF5ConfigWidgets KF5CoreAddons KF5Crash KF5I18n KF5ItemViews
WANTLIB += KF5JobWidgets KF5KIOCore KF5KIOGui KF5KIOWidgets KF5Parts
WANTLIB += KF5Service KF5SonnetUi KF5TextEditor KF5TextWidgets
WANTLIB += KF5WidgetsAddons KF5WindowSystem KF5XmlGui Qt5Concurrent
WANTLIB += Qt5Core Qt5DBus Qt5Gui Qt5Network Qt5Qml Qt5QmlModels
WANTLIB += Qt5Quick Qt5QuickWidgets Qt5Script Qt5ScriptTools Qt5Widgets
WANTLIB += Qt5Xml Qt5XmlPatterns c m

MODKDE5_DESKTOP_FILE = yes
MODKDE5_ICON_CACHE = yes
MODKDE5_TRANSLATIONS = yes
MODKF5_I18N_CONFLICT = yes
MODKF5_L10N_CONFLICT = yes
MODKDE5_DOCS = yes

BUILD_DEPENDS =	devel/boost \
		x11/qt5/qtquickcontrols \
		x11/qt5/qtsvg
RUN_DEPENDS =	x11/qt5/qtquickcontrols \
		x11/qt5/qtsvg

LIB_DEPENDS =	devel/kf5/karchive \
		devel/kf5/kauth \
		devel/kf5/kcodecs \
		devel/kf5/kcompletion \
		devel/kf5/kconfig \
		devel/kf5/kconfigwidgets \
		devel/kf5/kcoreaddons \
		devel/kf5/kcrash \
		devel/kf5/ki18n \
		devel/kf5/kio \
		devel/kf5/kitemviews \
		devel/kf5/kjobwidgets \
		devel/kf5/kparts \
		devel/kf5/kservice \
		devel/kf5/ktexteditor \
		devel/kf5/ktextwidgets \
		devel/kf5/kwidgetsaddons \
		devel/kf5/kxmlgui \
		devel/kf5/sonnet \
		x11/grantlee-qt5 \
		x11/qt5/qtdeclarative \
		x11/qt5/qtscript \
		x11/qt5/qtxmlpatterns

SUBST_VARS =	LIBrocsgraphtheory_VERSION

pre-configure:
	${SUBST_CMD} ${WRKSRC}/libgraphtheory/CMakeLists.txt

.include <bsd.port.mk>
