usage: cvs-aws.py [-h]
                 
    (--oracleBackup | --oracleRevert | --snapCreate | --snapDelete | --snapKeepByCount 
    | --snapKeepByDays | --snapList | --snapRevert | --volCreate | --volDelete | --volList)
                  [--project PROJECT] [--preview] [--Force] [--volPattern]
                  [--snapPattern] [--volume VOLUME] [--region REGION]
                  [--name NAME] [--gigabytes GIGABYTES]
                  [--bandwidth BANDWIDTH] [--cidr CIDR] [--label LABEL]
                  [--count COUNT] [--configFile CONFIGFILE]
                  [--oracleSid ORACLESID]

    cvs-aws.py is used to issue commands to your NetApp Cloud Volumes Service on
    your behalf.

    optional arguments:
    -h, --help            show this help message and exit
    --oracleBackup        Automate Oracle backups using hotbackup mode and storage 
                          snapshots which this program manages for you
    --oracleRevert        Automate Oracle revovery using storage snapshots which 
                          this program manages for you
    --snapCreate
    --snapDelete
    --snapKeepByCount     Keep only the newest N snapshots, delete the rest for
                          given volumes
    --snapKeepByDays      Keep only the snapshots for X days, delete the rest
                          for given volumes
    --snapList
    --snapRevert
    --volCreate
    --volDelete
    --volList
    
    
    --project PROJECT, -p PROJECT
                        Enter the project name to interact with, otherwise the
                        default project is selected
    --preview           If specfied, a try befor your buy simulation is run
                        rather than the actual command. Supports all delete
                        and create and Oracle commands.
    --Force             If specfied, enables substrings to work *Delete and
                        Revert operations. Supports all *Delete operations as
                        well as snapRevert.
    --volPattern, -P    Search for volumes using name as substring. Supports
                        snapList and volList nativley, snapDelete and
                        volDelete as well as snapRevert with --Force.
    --snapPattern, -S   Search for snapshots using name as substring. Supports
                        snap*.
    --volume VOLUME, -v VOLUME
                        Enter a volume to control 
    --region REGION, -r REGION
                        Specify the region when performing creation
                        operations, specify only if different than that listed
                        already in the aws_cvs_config.json file. Supports
                        snapCreate and volCreate
    --snapshot SNAPSHOT, -s SNAPSHOT 
                        Specify the snapshot to control. Supports snap* and
    --gigabytes GIGABYTES, -g GIGABYTES
                        Volume gigabytes in Gigabytes, value accepted between
                        100 and 100,000. Supports volCreate
    --bandwidth BANDWIDTH, -b BANDWIDTH
                        Volume bandwidth requirements in Megabytes per second.
                        If unknown enter 0 and maximum bandwidth is assigned.
                        Supports volCreate
    --cidr CIDR, -c CIDR  
                        IP Range used for export rules, the format needs to be
                        similar to 0.0.0.0/0, supports volCreate
    --label LABEL, -l LABEL
                        Volume label. Supports volCreate
    --count COUNT, -C COUNT
                        Specify the number of volumes to create, or the number
                        of snapshots to keep. Supports volCreate, snapKeepBy*
    --configFile CONFIGFILE, -f CONFIGFILE
                        Enter the json config file to extract volume lists
                        from, used with oracleBackup
    --oracleSid ORACLESID, -s ORACLESID
                        Enter the Oracle SID to backup
