include $(top_srcdir)/config/utility.am
include $(top_srcdir)/config/java.am
include $(top_srcdir)/common.am

EXTRA_DIST = \
	$(sipxhotprovisioning_SRC) \
	$(sipxhotprovisioning_RESOURCES) 

# tests do not compile
noinst_DATA = \
	javac-sipxhotprovisioning
#javac-test   tests do not compile     

jardir = @SIPX_JAVADIR@/sipXconfig/plugins
sipxhotprovisioning_JAR = sipXhotprovisioning.jar
jar_DATA = $(sipxhotprovisioning_JAR)
sipxhotprovisioning_RESOURCES = \
	$(shell cd $(srcdir); find plugin -type f) \
	sipxplugin.beans.xml

$(sipxhotprovisioning_JAR) : javac-sipxhotprovisioning $(sipxhotprovisioning_RESOURCES)
	jar -cf $@ \
	$(call JarInclude,$(JAVAROOT),.) \
	$(call JarInclude,$(srcdir),$(sipxhotprovisioning_RESOURCES))

sipxhotprovisioning_DEPS = \
	$(call JavaDep,@SIPX_JAVADIR@/sipXcommons @SIPX_JAVADIR@/sipXconfig,$(sipxhotprovisioning_PKGS))

sipxhotprovisioning_SRC = \
	$(shell cd $(srcdir); find src -name '*.java')

