.. _configuring_lifecycle_manager:

Lifecycle Manager
#################

Source code on Github_.

.. _Github: https://github.com/ros-planning/navigation2/tree/master/nav2_lifecycle_manager

The Lifecycle Manager module implements the method for handling the lifecycle transition states for the stack in a deterministic way.
It will take in a set of ordered nodes to transition one-by-one into the configurating and activate states to run the stack.
It will then bring down the stack into the finalized state in the opposite order. 

Parameters
**********

:node_names:

  ============== =======
  Type           Default
  -------------- -------
  vector<string>  N/A   
  ============== =======

  Description
    Ordered list of node names to bringup through lifecycle transition.

:autostart:

  ==== =======
  Type Default                                                   
  ---- -------
  bool false            
  ==== =======

  Description
    Whether to transition nodes to active state on startup.

Example
*******
.. code-block:: yaml

    lifecycle_manager:
      ros__parameters:
        autostart: true
        node_names: ['controller_server', 'planner_server', 'recoveries_server', 'bt_navigator', 'waypoint_follower']