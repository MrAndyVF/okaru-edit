# okaru-edit: text editor de OKARU. Se compila contra el núcleo instalado (paquete okaru-core).
project('okaru-edit', 'cpp',
  version: files('VERSION'),
  meson_version: '>=1.1',
  default_options: ['cpp_std=c++23', 'cpp_extensions=false', 'warning_level=0', 'b_ndebug=if-release'],
)

# El núcleo y sus bibliotecas son privados (/usr/lib/okaru): se enlazan con su ruta en el binario.
_okaru_libdir = get_option('prefix') / get_option('libdir') / 'okaru'
_deps = [dependency('okaru-core')]
_inc = include_directories('src')
_args = ['-Wall', '-Wextra', '-Wno-missing-field-initializers', '-Wpedantic', '-Wconversion', '-Wshadow']

_shared = files('src/apps/editor/formats.cpp', 'src/apps/editor/syntax.cpp', 'src/apps/editor/text_buffer.cpp')

executable('okaru-edit',
  sources: files('src/apps/editor/editor_view.cpp', 'src/apps/editor/editor_window.cpp', 'src/apps/editor/main.cpp') + _shared,
  include_directories: _inc,
  dependencies: _deps,
  cpp_args: _args,
  install_rpath: _okaru_libdir,
  install: true,
)

# Sus textos, que el núcleo busca en /usr/share/okaru/apps/editor/translations.
install_subdir('apps/editor/translations', install_dir: get_option('datadir') / 'okaru' / 'apps' / 'editor')
install_data('assets/dev.okaru.Editor.desktop', install_dir: get_option('datadir') / 'applications')

if get_option('tests').allowed()
  test('okaru_editor', executable('okaru_editor_test',
    sources: files('tests/okaru_editor_test.cpp') + _shared,
    include_directories: _inc,
    dependencies: _deps,
    build_rpath: _okaru_libdir,
    override_options: ['b_ndebug=false'],
  ))
endif
