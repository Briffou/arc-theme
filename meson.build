project(
  'arc-theme',
  version : '20211018',
  meson_version: '>= 0.50.0',
  license : 'GPL3'
)

variant_name = {
  'light' : (get_option('transparency') ? 'Arc-Qogir' : 'Arc-Qogir-solid'),
  'darker' : (get_option('transparency') ? 'Arc-Qogir-Darker' : 'Arc-Qogir-Darker-solid'),
  'dark' : (get_option('transparency') ? 'Arc-Qogir-Dark' : 'Arc-Qogir-Dark-solid'),
  'lighter' : (get_option('transparency') ? 'Arc-Qogir-Lighter' : 'Arc-Qogir-Lighter-solid'),
}

prefix = get_option('prefix')
datadir = get_option('datadir')

install_dir = {
  'light' : datadir / 'themes' / variant_name.get('light'),
  'darker' : datadir / 'themes' / variant_name.get('darker'),
  'dark' : datadir / 'themes' / variant_name.get('dark'),
  'lighter' : datadir / 'themes' / variant_name.get('lighter'),
}

# sassc dependency
foreach theme : ['cinnamon', 'gnome-shell', 'gtk3', 'gtk4']
  if theme in get_option('themes')
    sassc = find_program('sassc')
    break
  endif
endforeach

# inkscape dependency
foreach theme : ['gtk2', 'gtk3', 'gtk4', 'xfwm']
  if theme in get_option('themes')
    inkscape = find_program('inkscape')
    inkscape_ver = run_command(inkscape, '--version').stdout().split()[1]
    break
  endif
endforeach

subdir('common')
