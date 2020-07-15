# AppDynamics Windows Agent Installer AIO Standalone

## What you should do

Modify This File
 .\configs.ini

Modify these files if you need to change anything additional outside of configs.ini (you should modify if you have custom configs for Java or Machine Agent as this will overwrite anything in output dir)
 AppDynamics\dotnet-config.xml (this is your winston dotnet agent config)
 AppDynamics\javaagent\conf\controller-info.xml
 AppDynamics\machineagent\monitors\analytics-agent\conf\analytics-agent.properties
 AppDynamics\machineagent\conf\controller-info.xml

## Execution

Right-click Installer.bat 'Run as Administrator'

NOTE - Machine Agent will be copied to C:\Program Files\AppDynamics\machineagent where all other installations are defaulted.
NOTE - Java Agent will be copied to C:\Program Files\AppDynamics\javaagent where all other installations are defaulted

Validate 3 Services are installed

- AppDynamics Agent Coordinator
- AppDynamics Machine Agent
- AppDynamics NetVis Agent

Restart applications

Validate traffic is reporting to Controller and agents are healthy (server / network / analytics)

Make sure you enable netvis within the UI!
 Enable Socket Instrumentation
 In the Controller, click the gear icon in the top right and choose AppDynamics Agents > App Server Agents.
 Select the agent in the table and click Configure. The App Server Agent Configuration page appears.
 Select the application, tier, and node in the tree-view (left).
 Select Use Custom Configuration and then click + (the "plus-sign" button). The Create Agent Property dialog box appears.
 In the Create Agent Property dialog box, specify:
  Name = socket-enabled
  Description = Network Visibility
  Type = Boolean
  Value = true
