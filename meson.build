project('cronopete',['c','vala'])

NO_APPINDICATOR = (get_option('NO_APPINDICATOR') != '')

add_global_arguments('-DGETTEXT_PACKAGE="cronopete"',language: 'c')

if ( not NO_APPINDICATOR )
appindicator3_0_1_dep = dependency('appindicator3-0.1')
endif
atk_dep = dependency('atk')
cairo_dep = dependency('cairo')
gdk_3_0_dep = dependency('gdk-3.0')
gdk_pixbuf_2_0_dep = dependency('gdk-pixbuf-2.0')
gee_0_8_dep = dependency('gee-0.8')
gio_2_0_dep = dependency('gio-2.0')
glib_2_0_dep = dependency('glib-2.0')
gobject_2_0_dep = dependency('gobject-2.0')
gsl_dep = dependency('gsl')
gtk_3_0_dep = dependency('gtk+-3.0')
pango_dep = dependency('pango')
pangocairo_dep = dependency('pangocairo')
udisks2_dep = dependency('udisks2')
x11_dep = dependency('x11')

subdir('po')
cfg_dbus_data = configuration_data()
cfg_dbus_data.set ('DBUS_PREFIX',get_option('prefix'))
meson.add_install_script(join_paths(meson.current_source_dir(),'meson_scripts','install_data.sh'),join_paths(get_option('prefix'),get_option('datadir'),'cronopete'),join_paths(meson.current_source_dir(),'data/local','','*'))

meson.add_install_script(join_paths(meson.current_source_dir(),'meson_scripts','install_data.sh'),join_paths(get_option('prefix'),get_option('datadir'),'doc'),join_paths(meson.current_source_dir(),'doc','','*'))

installfile_1 = files('data/cronopete_preferences.sh')
install_data(installfile_1, install_dir: get_option('bindir'))
installfile_2 = files('data/cronopete_restore.sh')
install_data(installfile_2, install_dir: get_option('bindir'))
install_data('data/cronopete_preferences.desktop',install_dir:join_paths(get_option('prefix'),get_option('datadir'),'applications'))
install_data('data/cronopete_restore.desktop',install_dir:join_paths(get_option('prefix'),get_option('datadir'),'applications'))
if (get_option('prefix').startswith('/home/'))
	message('[33mAutostart file data/cronopete.desktop will not be installed. You must create your own .desktop file and put it at ~/.config/autostart[39m')
else
	install_data('data/cronopete.desktop',install_dir: '/etc/xdg/autostart')
endif
dbus_cfg_com_rastersoft_cronopete_service_base = configure_file(input: 'data/com.rastersoft.cronopete.service.base',output: 'com.rastersoft.cronopete.service', configuration: cfg_dbus_data)
install_data(dbus_cfg_com_rastersoft_cronopete_service_base,install_dir: join_paths(get_option('prefix'),get_option('datadir'),'dbus-1','services'))
eos_plug_cfg_cronopete_plug = configure_file(input: 'data/cronopete.plug',output: 'cronopete.plug', configuration: cfg_dbus_data)
install_data(eos_plug_cfg_cronopete_plug,install_dir: join_paths(get_option('prefix'),'lib','plugs','cronopete'))
install_data('data/org.rastersoft.cronopete.gschema.xml', install_dir: join_paths(get_option('prefix'),get_option('datadir'), 'glib-2.0', 'schemas'))
meson.add_install_script('meson_scripts/install_schemas.py')
	install_data('data/interface/about.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/chooser.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/config_exported.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/folder_selector.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/format_error.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/format_force.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/formatting.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/main.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/nodisk.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/options.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/restore_error.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/restore_ok.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/restoring.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
	install_data('data/interface/welcome.ui', install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
install_data('data/icons/anacronopete_128x128.png',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/128x128/apps'))
install_data('data/icons/anacronopete_16x16.png',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/16x16/apps'))
install_data('data/icons/anacronopete_22x22.png',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/22x22/apps'))
install_data('data/icons/anacronopete_24x24.png',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/24x24/apps'))
install_data('data/icons/anacronopete_32x32.png',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/32x32/apps'))
install_data('data/icons/anacronopete_48x48.png',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/48x48/apps'))
install_data('data/icons/anacronopete_64x64.png',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/64x64/apps'))
install_data('data/icons/cronopete-arrow-1-green-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-1-green.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-1-orange-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-1-orange.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-1-red-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-1-red.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-1-white-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-1-white.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-1-yellow-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-1-yellow.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-2-green-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-2-green.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-2-orange-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-2-orange.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-2-red-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-2-red.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-2-white-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-2-white.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-2-yellow-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-2-yellow.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-3-green-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-3-green.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-3-orange-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-3-orange.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-3-red-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-3-red.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-3-white-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-3-white.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-3-yellow-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-3-yellow.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-4-green-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-4-green.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-4-orange-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-4-orange.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-4-red-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-4-red.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-4-white-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-4-white.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete-arrow-4-yellow-symbolic.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/status'))
install_data('data/icons/cronopete-arrow-4-yellow.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete_preferences.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/icons/cronopete_restore.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'icons','hicolor/scalable/apps'))
install_data('data/pixmaps/anacronopete.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
install_data('data/pixmaps/anacronopete_tiny.svg',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
install_data('data/pixmaps/arrows.png',install_dir: join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
cfg_cronopete = configuration_data()
cfg_cronopete.set('DATADIR', join_paths(get_option('prefix'),get_option('datadir')))
cfg_cronopete.set('PKGDATADIR', join_paths(get_option('prefix'),get_option('datadir'),'cronopete'))
cfg_cronopete.set('GETTEXT_PACKAGE', 'cronopete')
cfg_cronopete.set('RELEASE_NAME', 'cronopete')
cfg_cronopete.set('PREFIX', get_option('prefix'))
cfg_cronopete.set('VERSION', '3.26.0')
cfg_cronopete.set('TESTSRCDIR', meson.current_source_dir())

cfgfile_3 = configure_file(input: 'src/Config.vala.base',output: 'Config_3.vala',configuration: cfg_cronopete)

cronopete_deps = []
if ( not NO_APPINDICATOR )
cronopete_deps += [appindicator3_0_1_dep]
endif
cronopete_deps += [atk_dep]
cronopete_deps += [cairo_dep]
cronopete_deps += [gdk_3_0_dep]
cronopete_deps += [gdk_pixbuf_2_0_dep]
cronopete_deps += [gee_0_8_dep]
cronopete_deps += [gio_2_0_dep]
cronopete_deps += [glib_2_0_dep]
cronopete_deps += [gobject_2_0_dep]
cronopete_deps += [gsl_dep]
cronopete_deps += [gtk_3_0_dep]
cronopete_deps += [pango_dep]
cronopete_deps += [pangocairo_dep]
cronopete_deps += [udisks2_dep]
cronopete_deps += [x11_dep]
cronopete_sources = [cfgfile_3]
cronopete_sources += ['src/backup.vala']
cronopete_sources += ['src/choose.vala']
cronopete_sources += ['src/cronopete.vala']
cronopete_sources += ['src/error_window.vala']
cronopete_sources += ['src/fixedlabel.vala']
cronopete_sources += ['src/icons_widget.vala']
cronopete_sources += ['src/ipc.vala']
cronopete_sources += ['src/menu.vala']
cronopete_sources += ['src/options.vala']
cronopete_sources += ['src/restore.vala']
cronopete_sources += ['src/usbhd_backend.vala']
cronopete_vala_args = ['--pkg','posix']
cronopete_vala_args += ['--target-glib', '2.32']
cronopete_c_args = []
if NO_APPINDICATOR
  cronopete_vala_args += ['-D', 'NO_APPINDICATOR']
  cronopete_c_args += ['-DNO_APPINDICATOR']
endif

executable('cronopete',cronopete_sources,dependencies: cronopete_deps,vala_args: cronopete_vala_args,c_args: cronopete_c_args,install: true)

