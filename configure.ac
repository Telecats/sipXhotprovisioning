AC_PREREQ(2.57)
AC_INIT(sipXhotprovisioning, 4.6.0, sipx-dev@list.sipfoundry.org)
AC_CONFIG_AUX_DIR(config)
m4_include([config/general.m4])
m4_include([config/sipXlib.m4])

#common macros
SFAC_INIT_FLAGS

# cpp macros
AM_DISABLE_STATIC
AC_PROG_LIBTOOL
AC_PROG_CXX
AC_PROG_CC
AX_COMPILER_VENDOR
SFAC_INIT_FLAGS
SFAC_LIB_PORT
SFAC_LIB_COMMSERVER
#additional to get the proxy project imported
#CHECK_XARGS_REPLACE
#AM_CONDITIONAL(IS_RPMBUILD, test x$enable_rpmbuild = xyes)


# java macros
m4_include([config/java.m4])
m4_include([config/java2.m4])
AM_INIT_AUTOMAKE(foreign tar-ustar)
SFAC_AUTOMAKE_VERSION([1.6])
AC_PATH_PROG([BASH],[bash])
AC_PROG_JAVA_CC([javac])
AC_PROG_JAVA([java])
PROG_JAVA_DEP
AC_SUBST(SIPX_IS_SRC, [true])
if test "${enable_rpmbuild}" == "yes" ; then
  SIPX_IS_SRC=false
fi

AC_CONFIG_FILES([
    Makefile
    config-plugin/Makefile
])

AC_OUTPUT
