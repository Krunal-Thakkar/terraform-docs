---
title: "Product Guide"
linkTitle: "Product Guide"
no_list: true
description: Documentation for PowerStore
weight: 5
---

# Terraform Modules for Dell PowerStore
--------------
# Contents
*   [Provider](#provider)
    *   [Synopsis](#synopsis)
    *   [List Of Parameters](#list-of-parameters)
    *   [Examples](#examples)
    *   [Notes](#notes)
*   [Volume Resource](#volume-resource)
    *   [Synopsis](#synopsis-1)
    *   [List Of Parameters](#list-of-parameters-1)
    *   [Examples](#examples-1)
    *   [Notes](#notes-1)
*   [SnapshotRule Resource](#snapshotrule-resource)
    *   [Synopsis](#synopsis-2)
    *   [List Of Parameters](#list-of-parameters-2)
    *   [Examples](#examples-2)
    *   [Notes](#notes-2)
*   [ProtectionPolicy Resource](#protectionpolicy-resource)
    *   [Synopsis](#synopsis-3)
    *   [List Of Parameters](#list-of-parameters-3)
    *   [Examples](#examples-3)
    *   [Notes](#notes-3)
*   [StorageContainer Resource](#storagecontainer-resource)
    *   [Synopsis](#synopsis-4)
    *   [List Of Parameters](#list-of-parameters-4)
    *   [Examples](#examples-4)
    *   [Notes](#notes-4)
*   [Volume DataSource](#volume-datasource)
    *   [Synopsis](#synopsis-5)
    *   [List Of Parameters](#list-of-parameters-5)
    *   [Examples](#examples-5)
    *   [Notes](#notes-5)


--------------

## Provider
Configure the provider on Dell Technologies PowerStore

### Synopsis
To create any resource / datasource , we need to provide authentication details to connect to the PowerStore 

### List Of Parameters
<table>
    <thead>
    <tr>
        <th>
            <div>Parameter Name</div>
        </th>
        <th>
            <div>Description</div>
        </th>
        <th>
            <div>Required/Optional/Computed</div>
        </th>
        <th>
            <div>Type</div>
        </th>
        <th>
            <div>Default Value</div>
        </th>
        <th>
            <div>Choices</div>
        </th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>endpoint</td>
        <td>The endpoint to which it needs to be connected.</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>username</td>
        <td>The username required for authentication.</td>
        <td>Required&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>password</td>
        <td>The password required for the authentication.&nbsp;</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>insecure</td>
        <td>Specifies if the user wants to do SSL verification.&nbsp;</td>
        <td>Optional</td>
        <td>bool&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
   </tbody>
</table>

### Examples
<pre>
    <code>
        provider "powerstore" {
            username = "username"
            password = "password"
            endpoint = "10.10.10.1"
            insecure = true
        }
    </code>
</pre>


### Notes
<ul>
<li>Provider details mandatorily needs to be provided to autnenticate and connect to the PowerStore Storage system before creating any resource / datasource</li>
</ul>

--------------

## Volume Resource

Manage Volume on Dell Technologies PowerStore

### Synopsis

Managing volumes on PowerStore storage system includes creating new volume, modifying attributes of the volume, importing existing volume and deleting the volume.

### List Of Parameters
<table>
    <thead>
    <tr>
        <th>
            <div>Parameter Name</div>
        </th>
        <th>
            <div>Description</div>
        </th>
        <th>
            <div>Required/Optional/Computed</div>
        </th>
        <th>
            <div>Type</div>
        </th>
        <th>
            <div>Default Value</div>
        </th>
        <th>
            <div>Choices</div>
        </th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>
            id
        </td>
        <td>
            Unique identifier of the volume instance
        </td>
        <td>Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            name
        </td>
        <td>
            Name of the volume
        </td>
        <td>Required</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            size
        </td>
        <td>Size of the volume to be created.</td>
        <td>Required</td>
        <td>Float64</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>capacity_unit</td>
        <td>The Capacity Unit corresponding to the size.</td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>GB</td>
        <td><ul>
        <li>MB</li>
        <li>GB</li>
        <li>TB (256 TB max)</li></ul></td>
    </tr>
    <tr>
        <td>
            host_id
        </td>
        <td>
        Unique identifier of the host to be attached to the volume.
        </td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            host_name
        </td>
        <td>
        Unique name of the host to be attached to the volume.
        </td>
        <td>Optional</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            host_group_id
        </td>
        <td>
            Unique identifier of the host group to be attached to the volume.
        </td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            host_group_name
        </td>
        <td>
            Unique name of the host group to be attached to the volume.
        </td>
        <td>Optional</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            logical_unit_number
        </td>
        <td>
            logical unit number when creating an attached volume.
        </td>
        <td>Optional and Computed</td>
        <td>Int64</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            volume_group_id
        </td>
        <td>
            Volume group to add the volume to.
        </td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            volume_group_name
        </td>
        <td>
            The volume group name of the volume.
        </td>
        <td>Optional</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            min_size
        </td>
        <td>
            minimum size for the volume, in bytes.
        </td>
        <td>Optional</td>
        <td>Int64</td>
        <td>1 MB</td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            sector_size
        </td>
        <td>
            sector size, in bytes. Only 512-byte and 4096-byte sectors are supported.
        </td>
        <td>Optional and Computed</td>
        <td>Int64</td>
        <td>512</td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            description
        </td>
        <td>
            Description of the volume
        </td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            appliance_id
        </td>
        <td>
            Unique identifier of the appliance on which the volume is provisioned
        </td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            appliance_name
        </td>
        <td>
            Unique name of the appliance on which the volume is provisioned
        </td>
        <td>Optional</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            protection_policy_id
        </td>
        <td>
            Unique identifier of the protection policy assigned to the volume. Only applicable to primary and clone
            volumes.
        </td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            protection_policy_name
        </td>
        <td>
            Unique name of the protection policy assigned to the volume. Only applicable to primary and clone
            volumes.
        </td>
        <td>Optional</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            performance_policy_id
        </td>
        <td>
            Unique identifier of the performance policy assigned to the volume.
        </td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>default_medium</td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            creation_timestamp
        </td>
        <td>
            Time when the volume was created.
        </td>
        <td>Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            is_replication_destination
        </td>
        <td>
            Indicates whether this volume is a replication destination.
        </td>
        <td>Computed</td>
        <td>Bool</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            node_affinity
        </td>
        <td>The node_affinity of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            System_Select_At_Attach, System_Selected_Node_A, System_Selected_Node_B, Preferred_Node_A, Preferred_Node_B
        </td>
    </tr>
    <tr>
        <td>
            type
        </td>
        <td>
            Type of volume
        </td>
        <td>Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            Primary, Clone, Snapshot
        </td>
    </tr>
    <tr>
        <td>
            wwn
        </td>
        <td>
            <p>World wide name of the volume.</p>
        </td>
        <td>Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            state
        </td>
        <td>
            <p>Volume life cycle states</p>
        </td>
        <td>Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>Ready, Initializing, Offline, Destroying</td>
    </tr>
    <tr>
        <td>
            logical_used
        </td>
        <td>
            Current amount of data (in bytes) host has written to a volume without dedupe, compression or sharing.
        </td>
        <td>Computed</td>
        <td>Int64</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            app_type
        </td>
        <td>
            This attribute indicates the intended use of this volume.
        </td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            Relational_Databases_Other, Relational_Databases_Oracle, Relational_Databases_SQL_Server,
            Relational_Databases_PostgreSQL, Relational_Databases_MySQL, Relational_Databases_IBM_DB2,
            Big_Data_Analytics_Other, Big_Data_Analytics_MongoDB, Big_Data_Analytics_Cassandra,
            Big_Data_Analytics_SAP_HANA, Big_Data_Analytics_Spark, Big_Data_Analytics_Splunk,
            Big_Data_Analytics_ElasticSearch, Business_Applications_Other, Business_Applications_ERP_SAP,
            Business_Applications_CRM, Business_Applications_Exchange, Business_Applications_Sharepoint,
            Healthcare_Other, Healthcare_Epic, Healthcare_MEDITECH, Healthcare_Allscripts, Healthcare_Cerner,
            Virtualization_Other, Virtualization_Virtual_Servers_VSI, Virtualization_Containers_Kubernetes,
            Virtualization_Virtual_Desktops_VDI, Other
        </td>
    </tr>
    <tr>
        <td>
            app_type_other
        </td>
        <td>
            This field can only be set if app_type is set to Relational_Databases_Other, Big_Data_Analytics_Other,
            Business_Applications_Other, Healthcare_Other, Virtualization_Other or Other. If the app_type attribute is
            set to anything other than one of these values, the attribute will be cleared.
        </td>
        <td>Optional</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            nsid
        </td>
        <td>
            NVMe Namespace unique identifier in the NVME subsystem. Used for volumes attached to NVMEoF hosts.
        </td>
        <td>Computed</td>
        <td>Int64</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    <tr>
        <td>
            nguid
        </td>
        <td>
            NVMe Namespace globally unique identifier. Used for volumes attached to NVMEoF hosts.
        </td>
        <td>Computed</td>
        <td>String</td>
        <td>
            <br>
        </td>
        <td>
            <br>
        </td>
    </tr>
    </tbody>
</table>

### Examples
```
- With required attributes only

    resource "powerstore_volume" "test" {
        name = "test_vol"
        size =  3
        capacity_unit= "GB"
    }

- With Host ID:

    resource "powerstore_volume" "test1" {
        name = "test_vol1"
        size =  3
        capacity_unit= "GB"
        description = "Creating volume"
        host_id="022c3fbc-4e92-48b6-928b-18565c803d0e"
        appliance_id="A1"
        volume_group_id="069b594c-6f68-4485-ab56-1c10b6230d71"
        min_size=1048576
        sector_size=512
        protection_policy_id="ea88-9c6e-a549-4281-b346-762451758e43"
        performance_policy_id="default_medium"
        app_type="Relational_Databases_Other"
        app_type_other="db1"
    }

- With HostGroupID:

    resource "powerstore_volume" "test2" {
        name = "test_vol2"
        size =  3
        capacity_unit= "GB"
        description = "Creating volume"
        host_group_id="80c4c618-cf91-4b67-9df3-b2c0f0d6564c"
        appliance_id="A1"
        volume_group_id="069b594c-6f68-4485-ab56-1c10b6230d71"
        min_size=1048576
        sector_size=512
        protection_policy_id="ea889c6e-a549-4281-b346-762451758e43"
        performance_policy_id="default_medium"
        app_type="Relational_Databases_Other"
        app_type_other="db1"
    }
```

### Notes

1. Only one either host_id or host_grop_id can be present at a time. logical_unit_number is used only when either of the host_id or host_group_id are present.
2. migration_session_id, metro_replication_session_id, is_host_access_available, protection_data instance, appliance, protection_policy, migration_session, mapped_volumes, volume_groups, datastores are not taken since they are all nested instances and will be covered with data source. 
location_history, type_l10n, state_l10n, node_affinity_l10n, app_type_l10n are not taken because they are not required as of now will be added later if customer requirement comes.
3. volume_group_ID, minimum_size, sector_size are present only in volume_create, so the values of these fields are updated through plan.

--------------

## SnapshotRule Resource

Manage Snapshot Rule on Dell Technologies PowerStore

### Synopsis

Managing snapshot rule on PowerStore storage system includes creating new snapshot rule, modifying attributes of the snapshot rule, importing existing snapshot rule and deleting the snapshot rule.

### List Of Parameters
<table>
    <thead>
    <tr>
        <th>
            <div>Parameter Name</div>
        </th>
        <th>
            <div>Description</div>
        </th>
        <th>
            <div>Required/Optional/Computed</div>
        </th>
        <th>
            <div>Type</div>
        </th>
        <th>
            <div>Default Value</div>
        </th>
        <th>
            <div>Choices</div>
        </th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>
            id
        </td>
        <td>Unique identifier of the snapshot rule.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            name
        </td>
        <td>Snapshot rule name.</td>
        <td>Required</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            interval
        </td>
        <td>Interval between snapshots taken by a snapshot rule.</td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td><br></td>
        <td>Five_Minutes, Fifteen_Minutes, Thirty_Minutes, One_Hour, Two_Hours, Three_Hours,
            Four_Hours, Six_Hours, Eight_Hours, Twelve_Hours, One_Day
        </td>
    </tr>
    <tr>
        <td>
            time_of_day
        </td>
        <td><p>Time of the day to take a daily snapshot</p>
            <p>Either the interval parameter or the time_of_day parameter will be set, but not both.</p></td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td><br></td>
        <td>format "hh:mm" using a 24 hour clock</td>
    </tr>
    <tr>
        <td>
            timezone
        </td>
        <td><p>timezone identifier for applying the time zone to the time_of_day for a snapshot
            rule, including any DST effects if applicable</p>
            <p>Applies only when a time_of_day is specified in the snapshot rule.</p></td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>UTC</td>
        <td>Etc__GMT_plus_12, US__Samoa, Etc__GMT_plus_11, America__Atka, US__Hawaii, Etc__GMT_plus_10,
            Pacific__Marquesas, US__Alaska, Pacific__Gambier, Etc__GMT_plus_9, PST8PDT, Pacific__Pitcairn, US__Pacific,
            Etc__GMT_plus_8, Mexico__BajaSur, America__Boise, America__Phoenix, MST7MDT, Etc__GMT_plus_7, CST6CDT,
            America__Chicago, Canada__Saskatchewan, America__Bahia_Banderas, Etc__GMT_plus_6, Chile__EasterIsland,
            America__Bogota, America__New_York, EST5EDT, America__Havana, Etc__GMT_plus_5, America__Caracas,
            America__Cuiaba, America__Santo_Domingo, Canada__Atlantic, America__Asuncion, Etc__GMT_plus_4,
            Canada__Newfoundland, Chile__Continental, Brazil__East, America__Godthab, America__Miquelon,
            America__Buenos_Aires, Etc__GMT_plus_3, America__Noronha, Etc__GMT_plus_2, America__Scoresbysund,
            Atlantic__Cape_Verde, Etc__GMT_plus_1, UTC, Europe__London, Africa__Casablanca, Atlantic__Reykjavik,
            Antarctica__Troll, Europe__Paris, Europe__Sarajevo, Europe__Belgrade, Europe__Rome, Africa__Tunis,
            Etc__GMT_minus_1, Asia__Gaza, Europe__Bucharest, Europe__Helsinki, Asia__Beirut, Africa__Harare,
            Asia__Damascus, Asia__Amman, Europe__Tiraspol, Asia__Jerusalem, Etc__GMT_minus_2, Asia__Baghdad,
            Africa__Asmera, Etc__GMT_minus_3, Asia__Tehran, Asia__Baku, Etc__GMT_minus_4, Asia__Kabul, Asia__Karachi,
            Etc__GMT_minus_5, Asia__Kolkata, Asia__Katmandu, Asia__Almaty, Etc__GMT_minus_6, Asia__Rangoon, Asia__Hovd,
            Asia__Bangkok, Etc__GMT_minus_7, Asia__Hong_Kong, Asia__Brunei, Asia__Singapore, Etc__GMT_minus_8,
            Asia__Pyongyang, Australia__Eucla, Asia__Seoul, Etc__GMT_minus_9, Australia__Darwin, Australia__Adelaide,
            Australia__Sydney, Australia__Brisbane, Asia__Magadan, Etc__GMT_minus_10, Australia__Lord_Howe,
            Etc__GMT_minus_11, Asia__Kamchatka, Pacific__Fiji, Antarctica__South_Pole, Etc__GMT_minus_12,
            Pacific__Chatham, Pacific__Tongatapu, Pacific__Apia, Etc__GMT_minus_13, Pacific__Kiritimati,
            Etc__GMT_minus_14
        </td>
    </tr>
    <tr>
        <td>
            days_of_week
        </td>
        <td><p>Days of the week when the snapshot rule should be applied.</p>
            <p>Days are determined based on the UTC time zone, unless the time_of_day and time_zone properties are
                set.</p></td>
        <td>Optional and Computed</td>
        <td>List of String</td>
        <td><br></td>
        <td>Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday</td>
    </tr>
    <tr>
        <td>
            desired_retention
        </td>
        <td><p>Desired snapshot retention period in hours. The system will retain snapshots for
            this time period.</p>
            <ul>
                <li>minimum: 0</li>
                <li>maximum: 8760</li>
            </ul>
        </td>
        <td>Required</td>
        <td>Int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            is_replica
        </td>
        <td><p>Indicates whether this is a replica of a snapshot rule on a remote system</p>
            <p>i.e. the source of a replication session replicating a storage resource to the local system</p></td>
        <td>Computed</td>
        <td>Bool</td>
        <td>false</td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            nas_access_type
        </td>
        <td><p>NAS filesystem snapshot access method.</p>
            <p>setting is ignored for volume, virtual_volume, and volume_group snapshots</p></td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td><br></td>
        <td>Snapshot, Protocol</td>
    </tr>
    <tr>
        <td>is_read_only</td>
        <td>Indicates whether this snapshot rule can be modified.
        </td>
        <td>Optional and Computed</td>
        <td>Bool</td>
        <td>false</td>
        <td><br></td>
    </tr>
    <tr>
        <td>managed_by</td>
        <td>entity that owns and manages this instance
        </td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>managed_by_id</td>
        <td><p>Unique identifier of the managing entity based on the value of the managed_by property, as show below:
        </p>
            <ul>
                <li>User - Empty</li>
                <li>Metro - Unique identifier of the remote system where the policy was assigned</li>
                <li>Replication - Unique identifier of the source remote system.</li>
                <li>VMware_vSphere - Unique identifier of the owning VMware vSphere/vCenter.</li>
            </ul>
        </td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>delete_snaps</td>
        <td>Specify whether all snapshots previously created by this snapshot rule should also be deleted when this rule
            is removed.
        </td>
        <td>Optional</td>
        <td>Bool</td>
        <td>false</td>
        <td><br></td>
    </tr>
    </tbody>
</table>

### Examples
```
- With required attributes only (using time_of_day):

    resource "powerstore_snapshotrule" "test" {
        name = "test_snapshotrule" 
        time_of_day = "21:00"
        desired_retention = 56
    }

- With required attributes only (using interval):

    resource "powerstore_snapshotrule" "test" {
        name = "test_snapshotrule" 
        interval = "Four_Hours"
        desired_retention = 56
    }

- With optional attributes:

    resource "powerstore_snapshotrule" "test" {
        name = "test_snapshotrule" 
        interval = "Four_Hours"
        days_of_week = ["Monday", "Wednesday"]
        desired_retention = 56
        nas_access_type = "Snapshot"
        is_read_only = false
        delete_snaps = true
    }
```

### Notes

1. We are allowing empty string as valid value for timezone and nas_access_type
2. Currently due to bug on powerstore (reported) , cannot set is_read_only parameter as true , handling via a workaround  TFM-154 - Powerstore : Remove "is_read_only" and nasaccesstype discrepancy in snapshot_rule template in request and response DEFINED
3. Due to mismatch in server implementation and documentation of API, default value is different for nas_access_type, currently handling via a workaround
4. We are not handling the case where resource is destroyed from outside the terraform, currently will result in error
5. Server sometime returns time_of_day value as hh:mm:00 , while client cannot send , so dropping this suffix (:00) in terraform state
6. interval_l10n , timezone_l10n , days_of_week_l10n , nas_access_type_l10n , managed_by_l10n are not taken because they are not required as of now will be added later if customer requirement comes.
7. Policies will be covered with data source.

--------------

## ProtectionPolicy Resource

Manage Protection Policy on Dell Technologies PowerStore

### Synopsis

Managing protection policy on PowerStore storage system includes creating new protection policy, modifying attributes of the protection policy, importing existing protection policy and deleting the protection policy.

### List Of Parameters
<table>
    <thead>
    <tr>
        <th>
            <div>Parameter Name</div>
        </th>
        <th>
            <div>Description</div>
        </th>
        <th>
            <div>Required/Optional/Computed</div>
        </th>
        <th>
            <div>Type</div>
        </th>
        <th>
            <div>Default Value</div>
        </th>
        <th>
            <div>Choices</div>
        </th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>
            id
        </td>
        <td>Unique identifier of the policy.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            name
        </td>
        <td><p>Policy name. This should be unique across all protection policies in the cluster.</p></td>
        <td>Required</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            description
        </td>
        <td><p>Policy description.</p></td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            type
        </td>
        <td>The type of the protection policy.
        <p>Supported policy types.</p>
        <p>Protection - A protection policy, consisting of snapshot and replication rules.</p>
        <p>Performance - A performance policy, consisting of performance rules.</p></td>
        <td>Computed</td>
        <td>String</td>
        <td></td>
        <td></td>
    </tr>
    <tr>
        <td>
            is_read_only
        </td>
        <td>Indicates whether this policy can be modified.</td>
        <td>Computed</td>
        <td>Bool</td>
        <td>false</td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            snapshot_rule_ids
        </td>
        <td>List of the snapshot rule IDs that are associated with this policy.</td>
        <td>Optional and Computed</td>
        <td>Set of string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            snapshot_rule_names
        </td>
        <td>List of the snapshot rule names that are associated with this policy.</td>
        <td>Optional and Computed</td>
        <td>Set of string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            replication_rule_ids
        </td>
        <td>List of the replication rule IDs that are associated with this policy.</td>
        <td>Optional and Computed</td>
        <td>Set of string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            replication_rule_names
        </td>
        <td>List of the replication rule names that are associated with this policy.</td>
        <td>Optional and Computed</td>
        <td>Set of string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    </tbody>
</table>

### Examples
```
- With required attributes only (associating replication rule using Name):

    resource "powerstore_protectionpolicy" "test" 
    {
        name = "protectionpolicy_acc_new"
        replication_rule_names = ["Emalee-SRA-7416-Rep"]
    }

- Associating replication rule and snapshot rule using ID:

    resource "powerstore_protectionpolicy" "test"
    {
        name = "protectionpolicy_acc_new"
        replication_rule_ids = ["5d45b173-9a85-473e-8ab8-e107f8b8085e"]
        snapshot_rule_ids = ["4be81573-c0e6-4956-a32f-a0e396a9b86d"]
    }

- Associating replication rule and snapshot rule using Name:

    resource "powerstore_protectionpolicy" "test" 
    {
        name = "protectionpolicy_acc_new"
        replication_rule_names = ["Emalee-SRA-7416-Rep"]
        snapshot_rule_names = ["test_snapshotrule_1"]
    }

- With optional attributes:

    resource "powerstore_protectionpolicy" "test" 
    {
        name = "protectionpolicy_acc_new"
        description = "Test CreateProtectionPolicy"
        snapshot_rule_names = ["test_snapshotrule_1"]
        replication_rule_ids = ["5d45b173-9a85-473e-8ab8-e107f8b8085e"]
    }

```

### Notes

1. Either of replication_rule_ids, replication_rule_names, snapshot_rule_ids or snapshot_rule_names is required.
2. replication_rule_ids and replication_rule_names are mutually exclusive attributes and both cannot be specified in one resource block.
2. snapshot_rule_ids and snapshot_rule_names are mutually exclusive attributes and both cannot be specified in one resource block.
4. virtual_volumes, virtual_machines, volumes, volume_groups, nas_servers, file_systems, performance_rules, snapshot_rules, replication_rules are not taken since they are all nested instances and will be covered with data source. 
5. managed_by, managed_by_id, is_replica, type_l10n, managed_by_l10n are not taken because they are not required as of now will be added later if customer requirement comes.

--------------

## StorageContainer Resource

Manage Storage Container on Dell Technologies PowerStore

### Synopsis

Managing storage container on PowerStore storage system includes creating new storage container, modifying attributes of the storage container, importing existing storage container and deleting the storage container.

### List Of Parameters
<table>
    <thead>
    <tr>
        <th>
            <div>Parameter Name</div>
        </th>
        <th>
            <div>Description</div>
        </th>
        <th>
            <div>Required/Optional/Computed</div>
        </th>
        <th>
            <div>Type</div>
        </th>
        <th>
            <div>Default Value</div>
        </th>
        <th>
            <div>Choices</div>
        </th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>
            id
        </td>
        <td>The unique identifier of the storage container.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            name
        </td>
        <td><p>Name for the storage container.</p>
            <p>This should be unique across all storage containers in the cluster.</p>
            <p>Name can be from 1 to 64 UTF-8 characters, and not more than 127 bytes.</p></td>
        <td>Required</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            quota
        </td>
        <td><p>The total number of bytes that can be provisioned/reserved against this storage
            container.</p>
            <p>A value of 0 means there is no limit. It is possible to set the quota to a value that overprovisions the
                amount of space available in the system.</p></td>
        <td>Optional and Computed</td>
        <td>Int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            storage_protocol
        </td>
        <td>The type of Storage Container.</td>
        <td>Optional and Computed</td>
        <td>String</td>
        <td>SCSI</td>
        <td>SCSI, NVMe</td>
    </tr>
    <tr>
        <td>
            high_water_mark
        </td>
        <td><p>This is the percentage of the quota that can be consumed before an alert is
            raised.</p>
            <p>Values between 50-100 (inclusive) are allowed</p></td>
        <td>Optional and Computed</td>
        <td>Int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    </tbody>
</table>

### Examples
```
- With required attributes only:

    resource "powerstore_storagecontainer" "test" {
        name = "scterraform_acc"
        quota = 10737418240
    }

- With optional attributes:

    resource "powerstore_storagecontainer" "test" {
        name = "scterraform_acc"
        quota = 10737418240
        storage_protocol = "SCSI"
        high_water_mark = 70
    }

```

### Notes

1. virtual_volumes , replication_groups , datastores , destinations , vsphere_host_ids will be covered with data source.
2. storage_protocol_l10n is not taken because it is not required as of now will be added later if customer requirement comes.
3. Currently server implementation is not accepting PATCH request, if request has some parameters whose value is same as already set on server , a workaround is implemented to deal with this.  TFM-195 - Resolve high water mark discrepancy for update ACCEPTED
4. high_water_mark is present only in instance of create storage container as per swagger ui, so it cannot be modified
5. mount , datastore_name are not taken as doc is not upto the mark with the server implementation

--------------

## Volume DataSource

Manage Volume DataSource on Dell Technologies PowerStore

### Synopsis

Managing volume datasource on PowerStore storage system includes fetching details of volume using volume name or volume id.

### List Of Parameters
<table>
    <thead>
    <tr>
        <th>
            <div>Parameter Name</div>
        </th>
        <th>
            <div>Description</div>
        </th>
        <th>
            <div>Required/Optional/Computed</div>
        </th>
        <th>
            <div>Type</div>
        </th>
        <th>
            <div>Default Value</div>
        </th>
        <th>
            <div>Choices</div>
        </th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>
            id
        </td>
        <td>Unique identifier of the volume instance.</td>
        <td>Optional And Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            name
        </td>
        <td>Name of the volume.</td>
        <td>Optional</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            size
        </td>
        <td>The size of the volume.</td>
        <td>Computed</td>
        <td>Float64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            capacity_unit
        </td>
        <td>The Capacity Unit corresponding to the size.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            host_id
        </td>
        <td>The host id of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            host_group_id
        </td>
        <td>The host group id of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            logical_unit_number
        </td>
        <td>The current amount of data written to the volume</td>
        <td>Computed</td>
        <td>Int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            volume_group_id
        </td>
        <td>The volume group id of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            description
        </td>
        <td>The description of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            appliance_id
        </td>
        <td>Unique identifier of the appliance on which the volume is provisioned.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            protection_policy_id
        </td>
        <td>The protection policy assigned to the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            performance_policy_id
        </td>
        <td>The performance policy assigned to the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            creation_timestamp
        </td>
        <td>The creation timestamp of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            is_replication_destination
        </td>
        <td>Indicates whether this volume is a replication destination.</td>
        <td>Computed</td>
        <td>Bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            node_affinity
        </td>
        <td>The node affinity of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            type
        </td>
        <td>The type of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            app_type
        </td>
        <td>The app type of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            app_type_other
        </td>
        <td>The app type other of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            wwn
        </td>
        <td>The wwn of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            state
        </td>
        <td>The state of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            nguid
        </td>
        <td>The nguid of the volume.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            nsid
        </td>
        <td>The nsid of the volume.</td>
        <td>Computed</td>
        <td>Int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            logical_used
        </td>
        <td>Current amount of data used by the volume.</td>
        <td>Computed</td>
        <td>Int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            migration_session_id
        </td>
        <td>Unique identifier of the migration session assigned to the volume</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            metro_replication_session_id
        </td>
        <td>Unique identifier of the replication session assigned to the volume</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            is_host_access_available
        </td>
        <td>Indicates whether the volume is available to host</td>
        <td>Computed</td>
        <td>Bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            type_l10n
        </td>
        <td>Localized message string corresponding to type</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            state_l10n
        </td>
        <td>Localized message string corresponding to state</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            node_affinity_l10n
        </td>
        <td>Localized message string corresponding to node affinity</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            app_type_l10n
        </td>
        <td>Localized message string corresponding to app type</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            protection_data
        </td>
        <td>Specifies the ProtectionData associated with a volume.</td>
        <td>Computed</td>
        <td>Object</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            location_history
        </td>
        <td>Specifies the LocationHistory for a volume.</td>
        <td>Computed</td>
        <td>Object</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            appliance
        </td>
        <td>Specifies the Appliance associated for a volume.</td>
        <td>Computed</td>
        <td>Object</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            migration_session
        </td>
        <td>Specifies the MigrationSession associated for a volume.</td>
        <td>Computed</td>
        <td>Object</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            mapped_volumes
        </td>
        <td>Specifies the MappedVolumes associated with a volume.</td>
        <td>Computed</td>
        <td>Object</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            datastores
        </td>
        <td>Specifies the Datastores for a volume.</td>
        <td>Computed</td>
        <td>Object</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            volume_groups
        </td>
        <td>Specifies the VolumeGroup for a volume.</td>
        <td>Computed</td>
        <td>Object</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>
            protection_policy
        </td>
        <td>Specifies the protection policy associated for a volume.</td>
        <td>Computed</td>
        <td>Object</td>
        <td><br></td>
        <td><br></td>
    </tr>
    </tbody>
</table>

### Examples
```
- Get volume details using volume name:

    data "powerstore_volume" "test1" 
    {
        name = "tf_vol"
    }

- Get volume details using volume ID:

    data "powerstore_volume" "test1" 
    {
	id = "a0b0c773-1c50-425a-89dc-aef9162ec787"
    }

```

### Notes

1. Either of volume id or volume name must be present to fetch details of specific volume.
2. Details of all the volumes would be fetched if no parameter is specified i.e empty block.