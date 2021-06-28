bash_completion_dir = get_option('bash_completion_dir')

if bash_completion_dir == ''
  bash_completion = dependency(
    'bash-completion',
    version : '>=2.0',
    required : false,
  )

  if bash_completion.found()
    bash_completion_dir = bash_completion.get_pkgconfig_variable('completionsdir')
  endif
endif

if bash_completion_dir == ''
  bash_completion_dir = get_option('datadir') / 'bash-completion' / 'completions'
endif

install_data('bwrap', install_dir : bash_completion_dir)
