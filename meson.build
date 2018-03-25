project(
  'ksmtuned', 'c',
  version: '0.1.0',
  license: 'GPL2+',
)

conf_data = configuration_data()
conf_data.set('LIBEXECDIR',
              join_paths(get_option('prefix'), get_option('libexecdir')))
conf_data.set('SBINDIR',
              join_paths(get_option('prefix'), get_option('sbindir')))
conf_data.set('SYSCONFDIR',
              join_paths(get_option('prefix'), get_option('sysconfdir')))

executable(
    'ksmctl',
    sources: 'src/ksmctl.c',
    install_dir: conf_data.get('LIBEXECDIR'),
    install: true,
)

install_data(
    'data/sysconfig/ksm',
    install_dir: join_paths(conf_data.get('SYSCONFDIR'), 'sysconfig'),
)

install_data(
    'data/ksmtuned.conf',
    install_dir: conf_data.get('SYSCONFDIR'),
)

configure_file(
    input: 'src/ksmtuned.sh.in',
    output: 'ksmtuned',
    configuration: conf_data,
    install_dir: conf_data.get('SBINDIR'),
)

configure_file(
    input: 'data/ksmtuned.service.in',
    output: 'ksmtuned.service',
    configuration: conf_data,
    install_dir: '/usr/lib/systemd/system/',
)

configure_file(
    input: 'data/ksm.service.in',
    output: 'ksm.service',
    configuration: conf_data,
    install_dir: '/usr/lib/systemd/system/',
)
