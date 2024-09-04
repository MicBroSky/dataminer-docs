---
uid: Configuring_dashboard_security
---

# Configuring security for a dashboard

> [!NOTE]
> Prior to DataMiner 10.3.0 [CU19]/10.4.0 [CU7]/10.4.10<!--RN 40501-->, these security settings can be found in the *Settings* pane of the dashboard. See [Changing dashboard settings](xref:Changing_dashboard_settings).

User permissions can be customized for both dashboard folders and individual dashboards, allowing you to restrict access and prevent unauthorized modifications.

> [!IMPORTANT]
> Restricting access to dashboards does not imply any restrictions on the underlying data. For this, the access rights on the corresponding data sources should be configured.

To configure which users can access and/or edit a folder or dashboard:

1. Right-click the folder or dashboard in the list pane and select *Settings*.

1. Under *Access*, determine which users and groups are allowed to view and/or edit the folder or dashboard. You can configure access for specific users, groups, or everyone.

   - *Everyone*: Specify the access level for all users who have the [General > DataMiner web apps](xref:DataMiner_user_permissions#general--dataminer-web-apps) user permission.

   - *Add user/group*: Enter the names of specific users and/or groups that should be allowed to view or edit the folder/dashboard. Then, assign them an appropriate access level.

   The available access levels are:

   - *No access*: Users cannot view or edit the dashboard folder or dashboard. The folder/dashboard will be hidden from the [Dashboards app sidebar](xref:Overview_of_the_Dashboards_app_UI#the-dashboards-app-sidebar) and will be inaccessible even with a direct link. This option is only available in the dropdown menu next to *Everyone*.

     > [!NOTE]
     > If you select *No access* for *Everyone*, you must assign at least one user or group as an editor to keep the folder/dashboard functional.

   - *Viewer*: Users can view the folder or dashboard. They can interact with dashboard components, but they cannot make any modifications. They are also unable to add new dashboards to the folder or change folder/dashboard settings.

   - *Editor*: Users can view and edit the dashboard. They can modify the folder or dashboard, including adding and removing dashboards, renaming them, and editing settings. However, the folder itself cannot be altered; i.e. it cannot be renamed or moved.

   > [!NOTE]
   >
   > - See [Special combinations of privileges](#special-combinations-of-privileges).
   > - If a user has been given an access level both as an individual and as part of a group, the level with the most privileges is the one that counts.
   > - If *Everyone* is set to *No access* and you do not manually add your user account as an editor, you will lose the ability to make further changes to the folder or dashboard.
   > - Granting a user *Viewer* rights to a folder allows them to view all subfolders and dashboards within. However, granting a user *Editor* rights to a folder does not automatically grant them edit rights to subfolders and dashboards within.
   > - The built-in Administrator account always has full access to all dashboards.

1. Click *Apply* in the lower right corner.

   ![Dashboard settings](~/user-guide/images/Dashboard_Settings.png)<br>*Dashboard settings in DataMiner 10.4.10*

## Special combinations of privileges

Certain combinations of privileges may lead to specific behaviors in terms of what users can or cannot do. Below are some common scenarios:

- *Viewer* rights to parent folder and *Editor* rights to child folder: Users can create new dashboards or folders within the child folder.

- *Viewer* rights to parent folder and *Editor* rights to dashboards within: Users can edit specific dashboards within the parent folder.

- *Viewer* rights to parent folder and *No access* rights to dashboards within: Users cannot see the restricted dashboards within the parent folder.

- *Editor* rights to parent folder and *Viewer* rights to dashboards within: Users can view the dashboards without making changes. They also cannot rename, move, or delete the dashboards. However, they can create and edit new dashboards within the parent folder.

- *Editor* rights to parent folder and *Viewer* rights to a child folder: Users cannot create new dashboards or subfolders in the child folder. They can delete, move, or rename the child folder and all dashboards directly within the parent folder.