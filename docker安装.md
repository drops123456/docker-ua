#ϵͳ[debian 6.0.6 wheely 64bit]��װdocker 1.2.0
##1.��װdocker
  echo deb http://get.docker.io/ubuntu docker main | sudo tee /etc/apt/sources.list.d/docker.list
  sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 36A1D7869245C8950F966E92D8576A8BA88D21E9
  sudo apt-get update
  sudo apt-get install -y lxc-docker

##2.�½��������������
###1.��������������Ǵ�docker hub���ѵ�
  �������£�
  docker search [���������]
  ������debianϵͳ���������
    docker search debian|less
  
###2.����һ��debian�����
    �����ص���kelseyhightower/debian�����
    docker pull kelseyhightower/debian
 
   ��������´���
   http:///var/run/docker.sock/v1.14/images/json: dial unix /var/run/docker.sock: no such file or directory
  ��ʾdocker����û��������������
  /etc/init.d/docker start
  ����docker����
  
  ��ʱ���Կ���������ѷ�ķ�����������kelseyhightower/debian����
  �����ַ����(�п��������ص�ʱ�򣬷����������仯)��
    ������server-54-230-149-71.sin2.r.cloudfront+.net:https
    IP:54.230.149.71:443
  ע��:����֮���ͨ��Ϊjson��ʽ�����������ӣ��ֶ�����һĿ��Ȼ
	    {
    "id": "34e94e67e63a0f079d9336b3c2a52e814d138e5b3f1f614a0cfe273814ed7c0a",
    "parent": "511136ea3c5a64f264b78b5433614aec563103b4d4702f3ba7d4d2698e22c158",
    "created": "2014-06-05T01:36:59.950625442Z",
    "container": "fe4991904c2df0cfe2dfd116a456f19d0d54d058ee982e184c11a7f9ce11f686",
    "container_config": {
        "Hostname": "fe4991904c2d",
        "Domainname": "",
        "User": "",
        "Memory": 0,
        "MemorySwap": 0,
        "CpuShares": 0,
        "AttachStdin": false,
        "AttachStdout": false,
        "AttachStderr": false,
        "PortSpecs": null,
        "ExposedPorts": null,
        "Tty": false,
        "OpenStdin": false,
        "StdinOnce": false,
        "Env": [
            "HOME=/",
            "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
        ],
        "Cmd": [
            "/bin/sh",
            "-c",
            "#(nop) MAINTAINER The CentOS Project \u003ccloud-ops@centos.org\u003e - ami_creator"
        ],
        "Image": "511136ea3c5a64f264b78b5433614aec563103b4d4702f3ba7d4d2698e22c158",
        "Volumes": null,
        "WorkingDir": "",
        "Entrypoint": null,
        "NetworkDisabled": false,
        "OnBuild": [
            
        ]
    },
    "docker_version": "0.10.0",
    "author": "The CentOS Project \u003ccloud-ops@centos.org\u003e - ami_creator",
    "config": {
        "Hostname": "fe4991904c2d",
        "Domainname": "",
        "User": "",
        "Memory": 0,
        "MemorySwap": 0,
        "CpuShares": 0,
        "AttachStdin": false,
        "AttachStdout": false,
        "AttachStderr": false,
        "PortSpecs": null,
        "ExposedPorts": null,
        "Tty": false,
        "OpenStdin": false,
        "StdinOnce": false,
        "Env": [
            "HOME=/",
            "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
        ],
        "Cmd": null,
        "Image": "511136ea3c5a64f264b78b5433614aec563103b4d4702f3ba7d4d2698e22c158",
        "Volumes": null,
        "WorkingDir": "",
        "Entrypoint": null,
        "NetworkDisabled": false,
        "OnBuild": [
            
        ]
    },
    "architecture": "amd64",
    "os": "linux",
    "Size": 0
  }
     ������һЩ�ֶεĽ��ͣ�
      1. id ��ʾ���ص�ID�ͱ����·����Ĭ��Ϊ/var/docker/graph/${id}
      2.parent ��ʾ����ͨ�ŵ�id�ż������·����Ĭ��Ϊ/var/docker/graph/#{parent},���������뿴
     {
    "id": "511136ea3c5a64f264b78b5433614aec563103b4d4702f3ba7d4d2698e22c158",
    "comment": "Imported from -",
    "created": "2013-06-13T14:03:50.821769-07:00",
    "container_config": {
        "Hostname": "",
        "User": "",
        "Memory": 0,
        "MemorySwap": 0,
        "CpuShares": 0,
        "AttachStdin": false,
        "AttachStdout": false,
        "AttachStderr": false,
        "PortSpecs": null,
        "Tty": false,
        "OpenStdin": false,
        "StdinOnce": false,
        "Env": null,
        "Cmd": null,
        "Dns": null,
        "Image": "",
        "Volumes": null,
        "VolumesFrom": ""
    },
    "docker_version": "0.4.0",
    "architecture": "x86_64"
   }
  
        1.comment   ��ʾ�����ע��
        2.created   ��ʾ����Ĵ�������
        3.container_config   ��ʾ������������Ϣ�������������ֶΣ�
                  1.Hostname  �������ƣ�������ID�ţ�65λ��ID�ŵ����ɹ��򣬾�����Ҫ��Դ���룩
                  2.User     �û�����
                  3.Memory   ������������ڴ��С
                  4.MemorySwap   ����������Ľ�������С
                  5.CpuShares   cpu��������֪��˼��
                  6.AttachStdin   ׷�ӵ����벿�֣��Ƿ����ض��������벿��?��
                  7.AttachStdout  ׷�ӵ�������֣��Ƿ����ض������������?��
                  8.AttachStderr  ׷�ӵĴ�����Ϣ���Ƿ����ض����˴�����Ϣ?��
                  9.PortSepcs   �ر�˿ڣ�����
                  10.OpenStdin   �Ƿ���˱�׼����
                  11.StdinOnce   �Ƿ��������루����
                  12.Env     ������Ϣ
                  13.Cmd     shell����������
                  14.Dns     DNS����
                  15.Image    ������Ϣ
                  16.Volumes     ���؄����Ķ�
                  17.VolumesFrom   ���Ķ����؄�
          4.docker_version docker�汾��
          5.architecture   �ܹ���Ϣ
      3.container  ������ID
      4.author   ���������
      5.config   �����������Ϣ
      6.os       ϵͳ��������Ϣ
      7.size     ����Ĵ�С 
      
      ���صİ���������/var/docker/aufs����
      ������3���ļ���
          1.diff   �Ƚϵ������ļ�
          2.layers   ��������Ϣ���ļ����Կ�����ι�ϵ
          3.mnt     ���ص�ϵͳ�����涼����ID���������ļ��У��е��ڲ�Ϊ�����ϵͳ�ṹ      
     
###3.���д������
    docker run -i -t kelseyhightower/debian:7.2 /bin/bash
    1.�����������ļ��е�����
        1.����/var/lib/docker/contains�£�
        2.һ��65λ�ַ����������ļ���
        �磺
        /var/lib/docker/contains/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d
        ע�⣺���ļ��е�ǰ13λ�ַ���Ϊ����Ĭ������
    2.�����������ļ�
    �����������ļ�������6�У��ֱ����£�
    1.������Ϣ
      config.json
      	�������£�
       {
        "ID": "633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d",
        "Created": "2014-09-06T10:53:26.583568469Z",
        "Path": "/bin/bash",
        "Args": [
         ],
        "Config": {
            "Hostname": "633710bf0be6",
            "Domainname": "",
            "User": "",
            "Memory": 0,
            "MemorySwap": 0,
            "CpuShares": 0,
            "Cpuset": "",
            "AttachStdin": true,
            "AttachStdout": true,
            "AttachStderr": true,
            "PortSpecs": null,
            "ExposedPorts": null,
            "Tty": true,
            "OpenStdin": true,
            "StdinOnce": true,
            "Env": [
              "HOME=/",
              "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
              "/bin/bash"
            ],
            "Image": "debian",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "NetworkDisabled": false,
            "OnBuild": null
        },
        "State": {
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "Pid": 4931,
            "ExitCode": 0,
            "StartedAt": "2014-09-06T10:53:28.854613233Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "25daec02219d2d852f7526137213a9b199926b4b24e732eab5b8bc6c49bd470e",
        "NetworkSettings": {
              "IPAddress": "172.17.0.2",
              "IPPrefixLen": 16,
              "Gateway": "172.17.42.1",
              "Bridge": "docker0",
              "PortMapping": null,
              "Ports": {
            
              }
        },
        "ResolvConfPath": "/var/lib/docker/containers/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d/hostname",
        "HostsPath": "/var/lib/docker/containers/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d/hosts",
        "Name": "/trusting_sinoussi",
        "Driver": "aufs",
        "ExecDriver": "native-0.2",
        "MountLabel": "",
        "ProcessLabel": "",
        "RestartCount": 0,
        "Volumes": {
        
        },
        "VolumesRW": {
        
        }
      }
    2.����������Ϣ
      1.hostconfig.json
        �������£�
        {
          "Binds": null,
          "ContainerIDFile": "",
          "LxcConf": [
            
          ],
          "Privileged": false,
          "PortBindings
          ": {
        
          },
          "Links": null,
          "PublishAllPorts": false,
          "Dns": null,
          "DnsSearch": null,
          "VolumesFrom": null,
          "Devices": [
        
           ],
          "NetworkMode": "bridge",
          "CapAdd": null,
          "CapDrop": null,
          "RestartPolicy": {
          "Name": "",
          "MaximumRetryCount": 0
           }
        }
      2.hostname
      �������£�
          633710bf0be6
      3.hosts
      �������£�
          172.17.0.2      633710bf0be6
          ff02::2 ip6-allrouters
          127.0.0.1       localhost
          ::1     localhost ip6-localhost ip6-loopback
          fe00::0 ip6-localnet
          ff00::0 ip6-mcastprefix
          ff02::1 ip6-allnodes

    3.��������������Ϣ
    resolv.conf
    �������£�
    # Generated by NetworkManager
    nameserver 211.161.45.222
    nameserver 220.113.47.34
    nameserver 192.168.1.1
    4.��־�ļ�
      1.�ļ�������
      ��־���ļ�ͬ����ֻ�Ǻ�������.log�������Ǹ���־�ļ���
      �磺
      633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d.log
      2.����
      ��ʵʱ��¼������������е��������
    5.���������������ʵ�ʴ��Ŀ¼
    ��/var/lib/docker/aufs/mnt/[ID]��
    �磺
    /var/lib/docker/aufs/mnt/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d
    6.�����¼
    ������/var/lib/docker/repositories-aufs
    �������£�
    {
    "Repositories": {
        "debian": {
            "6": "dee60b58b12881dd4ecb95c2704055f77bd8861fdef87732b029cac309d86475",
            "6.0": "dee60b58b12881dd4ecb95c2704055f77bd8861fdef87732b029cac309d86475",
            "6.0.10": "dee60b58b12881dd4ecb95c2704055f77bd8861fdef87732b029cac309d86475",
            "6.0.8": "d56191e18d6bd9f879bb52035e4e480a5442f940373ffded1b1b4df1623ac7b1",
            "6.0.9": "fee2ea4e24af3db10150730f7ad2223ae6dafd44fc00a9560f88fb9d036d273d",
            "7": "25daec02219d2d852f7526137213a9b199926b4b24e732eab5b8bc6c49bd470e",
            "7.3": "b5fe16f2ccba379b704f3dbfd5f09f7a4a7dd0e503b993efd2aa31596a4b3852",
            "7.4": "e565fbbc60335302852ee04152902c76b1a1d31d366c4070233e826cacb07cee",
            "7.5": "06af7ad6cff103d1695a9547a2294ba20ffc142770e8a830f12faf8a915eda9c",
            "7.6": "25daec02219d2d852f7526137213a9b199926b4b24e732eab5b8bc6c49bd470e",
            "experimental": "0e8bd0d713fe10cecee9389ed4654118f5252ecc5b09de40dc369ebfc282b080",
            "jessie": "f099861723c3ade7eb707fd3ce7fdce611c431a7d681051f7a085f90d8717b48",
            "latest": "25daec02219d2d852f7526137213a9b199926b4b24e732eab5b8bc6c49bd470e",
            "oldstable": "feeaaf97e7186f3d86c43787e113a280450b616d8b0f487c31417a1fd6d22370",
            "rc-buggy": "feef35a208d0d4cef3102f3e5456c39cebbdc65af0f1c94cd157476c76371999",
            "sid": "77e97a48ce6a3a01771b887c693517b6a2051dcda7d268ba645456567b7807d3",
            "squeeze": "dee60b58b12881dd4ecb95c2704055f77bd8861fdef87732b029cac309d86475",
            "stable": "5ba763dd8173da504b0a04ca038260c9baa727e4d4037008d5fcc0f176047a85",
            "testing": "b25b1bdd556e065447fcbf982cb83a8351e61196208d3aca17eb7649c2e76fa6",
            "unstable": "bc0d40402b6876a0c8ed34d9a30c113497c888af9b8d3bae67dc742030ab0ed7",
            "wheezy": "25daec02219d2d852f7526137213a9b199926b4b24e732eab5b8bc6c49bd470e"
        },
        "kelseyhightower/debian": {
            "7.2": "55bc02965e19a886a82d09d37dc1eb625ea580c9c2a8a514eb1b44085247d3f1"
        },
        "learn/vim": {
            "latest": "c9cb13da0ab652884e49cdafe5152b9eb4d730ae0e5d530054fa764060161fd1"
        }
    }
  }
  ��ʾ�����ݻ�����docker images��ʾ�Ĳ�࣬�����Ǵ�����������������ſ�
  REPOSITORY               TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
  learn/vim                latest              c9cb13da0ab6        42 seconds ago      118.7 MB
  debian                   6                   dee60b58b128        42 hours ago        78.48 MB
  debian                   6.0.10              dee60b58b128        42 hours ago        78.48 MB
  debian                   6.0                 dee60b58b128        42 hours ago        78.48 MB
  debian                   squeeze             dee60b58b128        42 hours ago        78.48 MB
  debian                   rc-buggy            feef35a208d0        42 hours ago        114.9 MB
  debian                   sid                 77e97a48ce6a        42 hours ago        114.9 MB
  debian                   jessie              f099861723c3        42 hours ago        114 MB
  debian                   stable              5ba763dd8173        42 hours ago        85.18 MB
  debian                   latest              25daec02219d        42 hours ago        85.18 MB
  debian                   wheezy              25daec02219d        42 hours ago        85.18 MB
  debian                   7                   25daec02219d        42 hours ago        85.18 MB
  debian                   7.6                 25daec02219d        42 hours ago        85.18 MB
  debian                   testing             b25b1bdd556e        42 hours ago        114 MB
  debian                   experimental        0e8bd0d713fe        42 hours ago        114.9 MB
  debian                   oldstable           feeaaf97e718        42 hours ago        78.48 MB
  debian                   unstable            bc0d40402b68        42 hours ago        114.9 MB
  debian                   6.0.9               fee2ea4e24af        6 weeks ago         78.48 MB
  debian                   7.5                 06af7ad6cff1        8 weeks ago         85.18 MB
  debian                   7.4                 e565fbbc6033        4 months ago        115 MB
  debian                   6.0.8               d56191e18d6b        7 months ago        113.1 MB
  debian                   7.3                 b5fe16f2ccba        7 months ago        117.7 MB
  kelseyhightower/debian   7.2                 55bc02965e19        8 months ago        218.6 MB
    7.��������Ŀ¼
      1.��������Ŀ¼��/var/lib/docker/execdriver/native/[ID]��,���Ŀ¼��������任����Ҳ�仯
      2.�ļ�������
        1.container.json
        �������£�
        {
         "mount_config": {
            "mounts": [
                {
                  "type": "bind",
                  "source": "/var/lib/docker/containers/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d/resolv.conf",
                  "destination": "/etc/resolv.conf",
                  "writable": true,
                  "private": true
                },
                {
                  "type": "bind",
                  "source": "/var/lib/docker/containers/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d/hostname",
                  "destination": "/etc/hostname",
                  "writable": true,
                  "private": true
                },
                {
                  "type": "bind",
                  "source": "/var/lib/docker/containers/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d/hosts",
                  "destination": "/etc/hosts",
                  "writable": true,
                  "private": true
                }
            ],
            "device_nodes": [
                {
                  "type": 99,
                  "path": "/dev/fuse",
                  "major_number": 10,
                  "minor_number": 229,
                  "cgroup_permissions": "rwm"
                },
                {
                  "type": 99,
                  "path": "/dev/null",
                  "major_number": 1,
                  "minor_number": 3,
                  "cgroup_permissions": "rwm",
                  "file_mode": 438
                },
                {
                  "type": 99,
                  "path": "/dev/zero",
                  "major_number": 1,
                  "minor_number": 5,
                  "cgroup_permissions": "rwm",
                  "file_mode": 438
                },
                {
                  "type": 99,
                  "path": "/dev/full",
                  "major_number": 1,
                  "minor_number": 7,
                  "cgroup_permissions": "rwm",
                  "file_mode": 438
                },
                {
                  "type": 99,
                  "path": "/dev/tty",
                  "major_number": 5,
                  "cgroup_permissions": "rwm",
                  "file_mode": 438
                },
                {
                  "type": 99,
                  "path": "/dev/urandom",
                  "major_number": 1,
                  "minor_number": 9,
                  "cgroup_permissions": "rwm",
                  "file_mode": 438
                },
                {
                  "type": 99,
                  "path": "/dev/random",
                  "major_number": 1,
                  "minor_number": 8,
                  "cgroup_permissions": "rwm",
                  "file_mode": 438
                }
            ]
        },
        "hostname": "633710bf0be6",
        "environment": [
           "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
            "HOSTNAME=633710bf0be6",
            "TERM=xterm",
            "HOME=/"
        ],
        "tty": true,
        "namespaces": {
            "NEWIPC": true,
            "NEWNET": true,
            "NEWNS": true,
            "NEWPID": true,
            "NEWUTS": true
        },
        "capabilities": [
            "CHOWN",
            "DAC_OVERRIDE",
            "FSETID",
            "FOWNER",
            "MKNOD",
            "NET_RAW",
            "SETGID",
            "SETUID",
            "SETFCAP",
            "SETPCAP",
            "NET_BIND_SERVICE",
            "SYS_CHROOT",
            "KILL",
            "AUDIT_WRITE"
          ],
        "networks": [
           {
              "type": "loopback",
              "address": "127.0.0.1/0",
              "gateway": "localhost",
              "mtu": 1500
            },
            {
                "type": "veth",
                "bridge": "docker0",
                "veth_prefix": "veth",
                "address": "172.17.0.2/16",
                "gateway": "172.17.42.1",
                "mtu": 1500
            }
        ],
        "cgroups": {
            "name": "633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d",
            "parent": "docker",
            "allowed_devices": [
            {
                "type": 99,
                "major_number": -1,
                "minor_number": -1,
                "cgroup_permissions": "m"
            },
            {
                "type": 98,
                "major_number": -1,
                "minor_number": -1,
                "cgroup_permissions": "m"
            },
            {
                "type": 99,
                "path": "/dev/console",
                "major_number": 5,
                "minor_number": 1,
                "cgroup_permissions": "rwm"
            },
            {
                "type": 99,
                "path": "/dev/tty0",
                "major_number": 4,
                "cgroup_permissions": "rwm"
            },
            {
                "type": 99,
                "path": "/dev/tty1",
                "major_number": 4,
                "minor_number": 1,
                "cgroup_permissions": "rwm"
            },
            {
                "type": 99,
                "major_number": 136,
                "minor_number": -1,
                "cgroup_permissions": "rwm"
            },
            {
                "type": 99,
                "major_number": 5,
                "minor_number": 2,
                "cgroup_permissions": "rwm"
            },
            {
                "type": 99,
                "major_number": 10,
                "minor_number": 200,
                "cgroup_permissions": "rwm"
            },
            {
                "type": 99,
                "path": "/dev/null",
                "major_number": 1,
                "minor_number": 3,
                "cgroup_permissions": "rwm",
                "file_mode": 438
            },
            {
                "type": 99,
                "path": "/dev/zero",
                "major_number": 1,
                "minor_number": 5,
                "cgroup_permissions": "rwm",
                "file_mode": 438
            },
            {
                "type": 99,
                "path": "/dev/full",
                "major_number": 1,
                "minor_number": 7,
                "cgroup_permissions": "rwm",
                "file_mode": 438
            },
            {
                "type": 99,
                "path": "/dev/tty",
                "major_number": 5,
                "cgroup_permissions": "rwm",
                "file_mode": 438
            },
            {
                "type": 99,
                "path": "/dev/urandom",
                "major_number": 1,
                "minor_number": 9,
                "cgroup_permissions": "rwm",
                "file_mode": 438
            },
            {
                "type": 99,
                "path": "/dev/random",
                "major_number": 1,
                "minor_number": 8,
                "cgroup_permissions": "rwm",
                "file_mode": 438
            }
         ]
      },
      "restrict_sys": true
    }
    
      2.state.json
      �������£�
      {
        "init_pid": 4931,
        "init_start_time": "862719",
        "network_state": {
          "veth_host": "veth3528",
          "veth_child": "vethc823"
        },
        "cgroup_paths": {
            "blkio": "/sys/fs/cgroup/blkio/docker/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d",
            "cpu": "/sys/fs/cgroup/cpu/docker/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d",
            "cpuacct": "/sys/fs/cgroup/cpuacct/docker/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d",
            "cpuset": "/sys/fs/cgroup/cpuset/docker/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d",
            "devices": "/sys/fs/cgroup/devices/docker/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d",
            "freezer": "/sys/fs/cgroup/freezer/docker/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d",
            "perf_event": "/sys/fs/cgroup/perf_event/docker/633710bf0be63b61affe60c8c8de374dc956e73400e0aca23efe3b870583950d"
       }
      }

  
##3.��������а�װVIM
  ���ַ�����
  1.���뵽����������������Ӱ�װһ��
  2.��docker��װ
  �������£�
    docker  run [ID] apt-get install -y vim
    
##4.�ύ���ĵ�������
   ʹ���������£�
   docker commit [ID] [ע����Ϣ]
   �磺
   docker commit 633710bf0be63 'install/vim' 
   
