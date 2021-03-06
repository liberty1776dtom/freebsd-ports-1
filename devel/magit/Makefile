# Created by: Jun Kuriyama <kuriyama@FreeBSD.org>
# $FreeBSD$

PORTNAME=	magit
PORTVERSION=	2.90.0
DISTVERSIONPREFIX=	v
CATEGORIES=	devel elisp
MASTER_SITES=	https://github.com/${PORTNAME}/${PORTNAME}/releases/download/${DISTVERSIONFULL}/
PKGNAMESUFFIX=	${EMACS_PKGNAMESUFFIX}

MAINTAINER=	yasu@utahime.org
COMMENT=	Interface to Git for Emacs

LICENSE=	GPLv3+
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	dash.el${EMACS_PKGNAMESUFFIX}>=2.14.1:devel/dash.el@${EMACS_FLAVOR} \
		ghub${EMACS_PKGNAMESUFFIX}>=3.0.0:devel/ghub@${EMACS_FLAVOR} \
		magit-popup${EMACS_PKGNAMESUFFIX}>=2.12.4:devel/magit-popup@${EMACS_FLAVOR} \
		with-editor${EMACS_PKGNAMESUFFIX}>=2.8.0:editors/with-editor@${EMACS_FLAVOR}
RUN_DEPENDS=	dash.el${EMACS_PKGNAMESUFFIX}>=2.14.1:devel/dash.el@${EMACS_FLAVOR} \
		ghub${EMACS_PKGNAMESUFFIX}>=3.0.0:devel/ghub@${EMACS_FLAVOR} \
		magit-popup${EMACS_PKGNAMESUFFIX}>=2.12.4:devel/magit-popup@${EMACS_FLAVOR} \
		with-editor${EMACS_PKGNAMESUFFIX}>=2.8.0:editors/with-editor@${EMACS_FLAVOR}

USES=		emacs gmake makeinfo

INFO=		magit
PORTDOCS=	AUTHORS.md
NO_ARCH=	yes

ELISPDIR=	${EMACS_VERSION_SITE_LISPDIR}/${PORTNAME}
MAKE_ENV+=	INSTALL_INFO=install-info \
		LOAD_PATH="-L ${WRKSRC}/lisp -L ${PREFIX}/${EMACS_SITE_LISPDIR} -L ${PREFIX}/${EMACS_VERSION_SITE_LISPDIR} -L ${PREFIX}/${EMACS_VERSION_SITE_LISPDIR}/ghub" \
		VERSION=${PORTVERSION} \
		lispdir=${PREFIX}/${ELISPDIR} \
		infodir=${PREFIX}/${INFO_PATH} \
		docdir=${DOCSDIR}
PLIST_SUB+=	ELISPDIR=${ELISPDIR}

OPTIONS_DEFINE=			DOCS GIT_SUBVERSION
GIT_SUBVERSION_DESC=		Use devel/git-subversion as backend
GIT_SUBVERSION_BUILD_DEPENDS=	git-subversion>0:devel/git-subversion
GIT_SUBVERSION_BUILD_DEPENDS_OFF=	git>0:devel/git
GIT_SUBVERSION_RUN_DEPENDS=	git-subversion>0:devel/git-subversion
GIT_SUBVERSION_RUN_DEPENDS_OFF=	git>0:devel/git

.include <bsd.port.mk>
