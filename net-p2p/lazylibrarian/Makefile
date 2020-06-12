# $FreeBSD$

PORTNAME= 	LazyLibrarian	
PORTVERSION=	1.7.2
PORTREVISION=	0
CATEGORIES=	net-p2p
#MASTER_SITES=	https://gitlab.com/LazyLibrarian/LazyLibrarian/-/archive/${PORTVERSION}/
#DISTNAME=	${PORTNAME}-${PORTVERSION}

MAINTAINER=	ballew@sublinear.net
COMMENT=	ebook and Audiobook Manager for Usenet and BitTorrent users

LICENSE=	GPLv3

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}sqlite3>0:databases/py-sqlite3@${PY_FLAVOR} \
				${PYTHON_PKGNAMEPREFIX}urllib3>0:net/py-urllib3 \
		wget>0:ftp/wget
		
USES=			python:3.7 shebangfix

USE_GITLAB=		YES
GL_ACCOUNT=		${PORTNAME}
GL_COMMIT=		6512f5a89598f4b214f697bd89eb6bec9c7b1b47

NO_ARCH=        YES
NO_BUILD=       YES

SHEBANG_FILES=	*.py lib/*.py lib/*/*.py lib/requests/packages/chardet/chardetect.py cherrypy/cherryd *.sh  

USERS=	lazylibrarian
GROUPS=	lazylibrarian



do-install:
	${INSTALL} -d -m 755 ${STAGEDIR}/${DATADIR}
	${INSTALL_SCRIPT} ${WRKSRC}/${PORTNAME}.py ${STAGEDIR}${PREFIX}/bin
	@${MKDIR} ${STAGEDIR}${DATADIR}
.for i in cherrypy demo_preprocessor.py epubandmobi.py example_custom_notification.py example_custom_notification.sh example_ebook_convert.py gsconvert.py lib lib3 mako
	${INSTALL_DATA} ${WRKSRC}/${i} ${STAGEDIR}${PREFIX}
.endfor

# post-install:
# 	@${FIND} -s ${STAGEDIR}${DATADIR} -not -type d | ${SORT} | \
# 		${SED} -e 's#^${STAGEDIR}${PREFIX}/##' >> ${TMPPLIST}

.include <bsd.port.mk>