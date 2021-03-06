LeApp tool
==========


check-target
^^^^^^^^^^^^

    **usage:**
        leapp-tool check-target [-h] [--user USER] [-s] target

    positional arguments:
        +-------------+---------------------------+
        | target      | Target container host     | 
        +-------------+---------------------------+

    optional arguments:
        ======================  ================================================
        -h, --help              show this help message and exit
        --user USER, -u USER    Connect as this user
        -s, --status            Check for services status on target machine
        ======================  ================================================


migrate-machine
^^^^^^^^^^^^^^^

    **usage:** 
        leapp-tool migrate-machine [-h] [-t TARGET]
                                   [--tcp-port [FORWARDED_PORTS [FORWARDED_PORTS ...]]]
                                   [--source-user USER]
                                   [--target-user USER]
                                   [--disable-start]
                                   machine
    
    positional arguments:
        +-------------+---------------------------+
        | machine     | source machine to migrate |
        +-------------+---------------------------+
    
    optional arguments:
        ==================================================== =======================================================
        -h, --help                                           show this help message and exit
        -t TARGET, --target TARGET                           target VM name
        --tcp-port [FWD_TCP_PORTS [FWD_TCP_PORTS ...]]       (Re)define target tcp ports to forward to
                                                             macrocontainer - [target_port:source_port]
        --no-tcp-port [EXD_TCP_PORTS [EXD_TCP_PORTS ...]]    define tcp ports which will be excluded from the
                                                             mapped ports [[target_port]:source_port>]
        --exclude-path [EXCLUDED_PATHS [EXCLUDED_PATHS ...]] define paths which will be excluded from the source
        -p, --print-port-map                                 List suggested port mapping on target host
        --ignore-default-port-map                            Default port mapping detected by leapp toll will be
                                                             ignored
        --use-rsync [USE_RSYNC]                              use rsync as backend for filesystem migration,
                                                             otherwise virt-tar-out
        --container-name CONTAINER_NAME, -n CONTAINER_NAME   Name of new container created on target host
        --force-create                                       force creation of new target container, even if one
                                                             already exists
        --source-user SOURCE_USER                            Connect as this user to the source
        --target-user TARGET_USER                            Connect as this user to the target
        --disable-start                                      Do not start container after migration
        ==================================================== =======================================================


destroy-containers
^^^^^^^^^^^^^^^^^^
    **usage:**
        leapp-tool destroy-container [-h] [-t TARGET] [--user USER] container
    
    
    positional arguments:
        +-------------+---------------------------+
        | container   | container name            |
        +-------------+---------------------------+

    
    optional arguments:
        ==========================  =============================== 
        -h, --help                  Show this help message and exit
        -t TARGET, --target TARGET  Target container host 
        --user USER, -u USER        Connect as this user
        ==========================  =============================== 


port-inspect
^^^^^^^^^^^^
    **usage:** 
        leapp-tool port-inspect [-h] [--range RANGE] [--shallow] ip
    
    positional arguments:
        +-------------+----------------------------+
        | ip          | virtual machine ip address |
        +-------------+----------------------------+
    
    optional arguments:
        -h, --help      Show this help message and exit
        --range RANGE   port range, example of proper
                        form:"-100,200-1024,T:3000-4000,U:60000-"
        --shallow       Skip detailed informations about used ports, this is quick
                        SYN scan

