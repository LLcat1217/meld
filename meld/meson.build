
# TODO: Replace our existing conf.py hacks with configure_file().
# See e.g., gnome-music for an example of this

folders = {
    '.': [
        '__init__.py',
        'accelerators.py',
        'actiongutter.py',
        'build_helpers.py',
        'chunkmap.py',
        'const.py',
        'diffgrid.py',
        'dirdiff.py',
        'filediff.py',
        'filters.py',
        'gutterrendererchunk.py',
        'iohelpers.py',
        'linkmap.py',
        'meldapp.py',
        'meldbuffer.py',
        'melddoc.py',
        'meldwindow.py',
        'menuhelpers.py',
        'misc.py',
        'newdifftab.py',
        'patchdialog.py',
        'preferences.py',
        'recent.py',
        'settings.py',
        'sourceview.py',
        'style.py',
        'task.py',
        'tree.py',
        'treehelpers.py',
        'undo.py',
        'vcview.py',
        'windowstate.py',
    ],
    'matchers': [
        'matchers/__init__.py',
        'matchers/diffutil.py',
        'matchers/helpers.py',
        'matchers/merge.py',
        'matchers/myers.py',
    ],
    'ui': [
      'ui/__init__.py',
      'ui/bufferselectors.py',
      'ui/cellrenderers.py',
      'ui/emblemcellrenderer.py',
      'ui/findbar.py',
      'ui/gladesupport.py',
      'ui/gtkcompat.py',
      'ui/historyentry.py',
      'ui/listwidget.py',
      'ui/msgarea.py',
      'ui/notebook.py',
      'ui/notebooklabel.py',
      'ui/recentselector.py',
      'ui/statusbar.py',
      'ui/util.py',
      'ui/vcdialogs.py',
    ],
    'vc': [
      'vc/COPYING',
      'vc/README',
      'vc/__init__.py',
      'vc/_null.py',
      'vc/_vc.py',
      'vc/bzr.py',
      'vc/cvs.py',
      'vc/darcs.py',
      'vc/git.py',
      'vc/mercurial.py',
      'vc/svn.py',
    ],
}

foreach folder_name, sources : folders
  pkgdir = join_paths(meson.project_name(), folder_name)
  python3.install_sources(sources, pure: true, subdir: pkgdir)
endforeach

# Install the executable file
app_config = configuration_data()
app_config.set('profile', profile)
app_config.set('application_id', application_id)
app_config.set('resource_base_id', resource_base_id)
app_config.set('localedir', localedir)
app_config.set('pkgdatadir', pkgdatadir)
app_config.set('configured', 'True')

configure_file(
    input: 'conf.py.in',
    output: 'conf.py',
    configuration: app_config,
    install_dir: python3.get_install_dir(pure: true, subdir: meson.project_name()),
)

subdir('resources')
