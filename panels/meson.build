subdir('common')

panels = [
  'applications',
  'background',
  'color',
  'datetime',
  'default-apps',
  'display',
  'info-overview',
  'keyboard',
  'mouse',
  'multitasking',
  'notifications',
  'online-accounts',
  'power',
  'printers',
  'privacy',
  'region',
  'removable-media',
  'search',
  'sharing',
  'sound',
  'universal-access',
  'user-accounts',
 'wwan',
]

if host_is_linux
  panels += ['network']
endif

if host_is_linux_not_s390
  panels += [
    'bluetooth',
    'wacom'
  ]
endif

# override the above to just compile printers
panels = [
  'printers',
]

panels_list = []
panels_libs = []
foreach cappletname: panels
  cflags = [
    '-DG_LOG_DOMAIN="cc-@0@-panel"'.format(cappletname),
    '-DPANEL_ID="@0@"'.format(cappletname)
  ]

  subdir(cappletname)
endforeach
