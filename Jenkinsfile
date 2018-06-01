node{

    stage('CheckOut')

        checkout([$class: 'GitSCM', additionalCredentials: [], excludedCommitMessages: '', excludedRegions: '', excludedRevprop: '', excludedUsers: '', filterChangelog: false, ignoreDirPropChanges: false, includedRegions: '', locations: [], workspaceUpdater: [$class: 'UpdateUpdater']])

    stage('BuildBar')

        bat '"C:\\Program Files (x86)\\IBM\\IntegrationToolkit90\\mqsicreatebar.exe" -data "D:\\SYSCO\\ToolkitWorkAreaIIB\\keerthana\\BARfiles" -b "D:\\SYSCO\\ToolkitWorkAreaIIB\\keerthana\\BARfiles\\SYSCO_TEST-%BUILD_NUMBER%.bar" -p VendorShipFrom -m VendorShipFrom.msgflow' 

    stage('DeployBar'){

        bat '''CALL "C:\\Program Files\\IBM\\MQSI\\9.0.0.2\\bin\\mqsiprofile.cmd"

        "C:\\Program Files\\IBM\\MQSI\\9.0.0.2\\bin\\mqsideployscript.bat" -n "C:\\Users\\pbis1150\\Documents\\DEV2.broker" -e EGP3 -a "D:\\SYSCO\\ToolkitWorkAreaIIB\\pbis1150\\BARfiles\\SYSCO_TEST-%BUILD_NUMBER%.bar" -w 300'''}
        }
