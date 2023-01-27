---
title: "Product Guide"
linkTitle: "Product Guide"
no_list: true
description: Documentation for PowerFlex
weight: 20
---


# Terraform Modules for Dell PowerFlex
<!-- © 2021 Dell Inc. or its subsidiaries. All rights reserved. Dell, and other trademarks are trademarks of Dell Inc. or its subsidiaries. Other trademarks may be trademarks of their respective owners. -->

--------------
# Contents
*   [Volume Resource](#volume-resource)
    *   [Synopsis](#synopsis)
    *   [List Of Parameters](#list-of-parameters)
    *   [Examples](#examples)
    *   [Notes](#notes)
*   [SDC Resource](#sdc-resource)
    *   [Synopsis](#synopsis-1)
    *   [List Of Parameters](#list-of-parameters-1)
    *   [Examples](#examples-1)
    *   [Notes](#notes-1)
*   [SDC Datasource Resource](#sdc-datasource-resource)
    *   [Synopsis](#synopsis-2)
    *   [List Of Parameters](#list-of-parameters-2)
    *   [Examples](#examples-2)
    *   [Notes](#notes-2)
*   [Storage Pool Resource](#storage-pool-resource)
    *   [Synopsis](#synopsis-3)
    *   [List Of Parameters](#list-of-parameters-3)
    *   [Examples](#examples-3)
    *   [Notes](#notes-3)
*   [Snapshot Resource](#snapshot-resource)
    *   [Synopsis](#synopsis-4)
    *   [List Of Parameters](#list-of-parameters-4)
    *   [Examples](#examples-4)
    *   [Notes](#notes-4)    
*   [SDS Resource](#sds-resource)
    *   [Synopsis](#synopsis-5)
    *   [List Of Parameters](#list-of-parameters-5)
    *   [Examples](#examples-5)
    *   [Notes](#notes-5) 

--------------

## Volume Resource

Manage volumes on Dell EMC PowerFlex

### Synopsis
Managing volumes on PowerFlex storage system includes creating new volume, mapping/unmapping volume to/from SDC, modifying attributes of volume and deleting volume.

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
        <td>name</td>
        <td>The Name of the Volume.</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pool_id</td>
        <td>Storage Pool id.</td>
        <td>Optioanl And Computed&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pool_name</td>
        <td>Storage Pool Name.&nbsp;</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_id</td>
        <td>Protection Domain ID.&nbsp;</td>
        <td>Optional And Computed</td>
        <td>String&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_name</td>
        <td>Protection Domain Name.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>size</td>
        <td>Size of the Volume.&nbsp;</td>
        <td>Required</td>
        <td>int64&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>capacity_unit</td>
        <td>The unit of the volume size.</td>
        <td>Optional And Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td>GB</td>
        <td><ul>
        <li>GB</li>
        <li>TB</li>
        </ul></td>
    </tr>
    <tr>
        <td>volume_type</td>
        <td>Type of volume provisioning.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ThinProvisioned</td>
        <td><ul>
        <li>ThickProvisioned</li>
        <li>ThinProvisioned</li>
        </ul></td>
    </tr>
    <tr>
        <td>use_rm_cache</td>
        <td>Whether to use RM Cache or not.
        </td>
        <td>Optional And Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>compression_method</td>
        <td>Type of the compression method.
        </td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><ul>
        <li>None</li>
        <li>Normal</li>
        </ul></td>
    </tr>
    <tr>
        <td>id</td>
        <td>The ID of the volume.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>size_in_kb</td>
        <td>Size in KB.
        </td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>access_mode</td>
        <td>The Access mode of Volume.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ReadOnly</td>
        <td><ul>
        <li>ReadOnly</li>
        <li>ReadWrite</li>
        </ul></td>
    </tr>
    <tr>
        <td>remove_mode</td>
        <td>remove mode of Volume.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ONLY_ME</td>
        <td><ul>
        <li>ONLY_ME</li>
        <li>INCLUDING_DESCENDANTS</li>
        </ul></td>
    </tr>
    <tr>
        <td>sdc_list</td>
        <td>mapped sdc info.</td>
        <td>Optional And Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sdc_id</td>
        <td>The ID of the SDC.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sdc_name</td>
        <td>The Name of the SDC.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;limit_iops</td>
        <td>Limit of volume IOPS.</td>
        <td>Optional And Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;limit_bw_in_mbps</td>
        <td>Limit of volume network bandwidth.</td>
        <td>Optional And Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;access_mode</td>
        <td>Define the access mode for all mappings of the volume.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ReadOnly</td>
        <td><ul>
        <li>ReadOnly</li>
        <li>ReadWrite</li>
        <li>NoAccess</li>
        </ul></td>
    </tr>
    </tbody>
</table>

### Examples
<pre>
    <code>
        resource "powerflex_volume" "avengers-volume-create"{
        name = "avengers-volume-create"
        protection_domain_name = "domain1"
        storage_pool_name = "pool1" 
        size = 8
        use_rm_cache = true 
        volume_type = "ThickProvisioned" 
        access_mode = "ReadWrite"
        sdc_list = [
        {
                sdc_name = "LGLW6092"
                limit_iops = 119
                limit_bw_in_mbps = 19
                access_mode = "ReadOnly"
                },
            ]   
        }
    </code>
</pre>


### Notes
<ul>
<li> Volume name is unique across the PowerFlex array.</li>
<li> Either name or the id of the storage pool is required for creating / modifying a volume.</li>
<li> Either name or the id of the protection domain is required for creating / modifying a volume.</li>
<li> Size of the volume should be a multiple of 8.</li>
<li> specify 0 for unlimited iops..</li>
<li> To set no limit over bandwidth, 0 is to be passed.</li>
<li> Specify either sdc_name or sdc_id.</li>
</ul>

## SDC Resource

Manage SDCs on Dell EMC PowerFlex
### Synopsis
Managing SDCs on PowerFlex storage system includes importing details of SDC and renaming SDC

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
        <td>id</td>
        <td>SDC ID.</td>
        <td>Required</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>last_updated</td>
        <td>Last updated timestamp.</td>
        <td>Computed&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>name</td>
        <td>SDC Name.&nbsp;</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sdc_guid</td>
        <td>SDC GUID.&nbsp;</td>
        <td>Computed</td>
        <td>String&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>on_vmware</td>
        <td>Presence on VMware.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td></td>
    </tr>
    <tr>
        <td>sdc_approved</td>
        <td>Indicates whether an SDC has approved access to the system.</td>
        <td>Computed&nbsp;</td>
        <td>bool&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>system_id</td>
        <td>ID of the System.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>sdc_ip</td>
        <td>IP of the SDC.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>mdm_connection_state</td>
        <td>MDM connection state.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>links</td>
        <td>Underlying REST API links.</td>
        <td>Computed</td>
        <td>List</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;rel</td>
        <td>Specifies the relationship with the SDC.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;href</td>
        <td>Specifies the exact path to fetch the details.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    </tbody>
</table>

### Examples
<pre>
    <code>
        resource "powerflex_sdc" "sdc" {
            id = "c423b09800000003"
            name = "powerflex_sdc26"
        }
    </code>
</pre>



## Storage Pool Resource

Managing Dell EMC PowerFlex storage pool

### Synopsis
Dell EMC PowerFlex storage pool module includes creating a new storage pool, and modifying the attributes of a storage pool.

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
        <td>id</td>
        <td>ID of the Storage pool.</td>
        <td>Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_id</td>
        <td>ID of the Protection domain.</td>
        <td>Optional&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_name</td>
        <td>Name of the Protection domain.&nbsp;</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>name</td>
        <td>Name of the Storage pool.&nbsp;</td>
        <td>Required</td>
        <td>String&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>media_type</td>
        <td>Type of devices in the storage pool.</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><ul>
        <li>HDD</li>
        <li>SSD</li>
        <li>Transitional</li>
        </ul></td>
    </tr>
    <tr>
        <td>use_rmcache</td>
        <td>Enable/Disable RMcache on a specific storage pool.</td>
        <td>Optional And Computed&nbsp;</td>
        <td>bool&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>use_rfcache</td>
        <td>Enable/Disable RFcache on a specific storage pool.</td>
        <td>Optional And Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>   
    </tbody>
</table>

### Examples
<pre>
    <code>
        resource "powerflex_storagepool" "storagepool" {
            name = "storagepool3"
            protection_domain_id = "4eeb304600000000"
            media_type = "HDD"
            use_rmcache = true
            use_rfcache = false
}
    </code>
</pre>

### Notes

<ul>
        <li>Either protection_domain_id or protection_domain_name is required in order to create / modify storage pool.</li>
        <li>Transitional media type is supported only during modification.</li>
 </ul>


## Snapshot Resource

Details about snapshot resource

### Synopsis
Managing snapshots on PowerFlex storage system includes creating snapshot for a volume,modifying attributes of snapshot and deleting snapshot.

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
        <td>name</td>
        <td>The name of the snapshot.</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>volume_id</td>
        <td>The volume id for which snapshot is created.</td>
        <td>Optioanl And Computed&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>volume_name</td>
        <td>The volume name for which snapshot is created.&nbsp;</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>access_mode</td>
        <td>The Access mode of snapshot.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ReadOnly</td>
        <td><ul>
        <li>ReadOnly</li>
        <li>ReadWrite</li>
        </ul></td>
    </tr>
        <tr>
        <td>id</td>
        <td>The ID of the snapshot.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>size</td>
        <td>Size of the snapshot.&nbsp;</td>
        <td>Optional And Computed</td>
        <td>int64&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>capacity_unit</td>
        <td>The unit of the snapshot size.</td>
        <td>Optional And Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td>GB</td>
        <td><ul>
        <li>GB</li>
        <li>TB</li>
        </ul></td>
    </tr>
        <tr>
        <td>size_in_kb</td>
        <td>Size in KB.
        </td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>lock_auto_snapshot</td>
        <td>lock auto snapshot.</td>
        <td>Optional And Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>desired_retention</td>
        <td>desired retention of snapshot.
        </td>
        <td>Optional</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>retention_unit</td>
        <td>retention unit of snapshot.
        </td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>hours</td>
        <td><ul>
        <li>hours</li>
        <li>days</li>
        </ul></td>
    </tr>
    <tr>
        <td>retention_in_min</td>
        <td>retention of snapshot in min.
        </td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>remove_mode</td>
        <td>remove mode of snapshot.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ONLY_ME</td>
        <td><ul>
        <li>ONLY_ME</li>
        <li>INCLUDING_DESCENDANTS</li>
        </ul></td>
    </tr>
    <tr>
        <td>sdc_list</td>
        <td>mapped sdc info.</td>
        <td>Optional And Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sdc_id</td>
        <td>The ID of the SDC.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sdc_name</td>
        <td>The Name of the SDC.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;limit_iops</td>
        <td>Limit of volume IOPS.</td>
        <td>Optional And Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;limit_bw_in_mbps</td>
        <td>Limit of volume network bandwidth.</td>
        <td>Optional And Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;access_mode</td>
        <td>Define the access mode for all mappings of the volume.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ReadOnly</td>
        <td><ul>
        <li>ReadOnly</li>
        <li>ReadWrite</li>
        <li>NoAccess</li>
        </ul></td>
    </tr>
    </tbody>
</table>

### Examples
<pre>
    <code>
        resource "powerflex_snapshot" "snapshots-create-access-mode-sdc-map" {
            name = "snapshots-create-epsilon"
            volume_id = "4577c84000000120"
            access_mode = "ReadWrite"
            size = 16
            capacity_unit = "GB"
            remove_mode = "INCLUDING_DESCENDANTS"
            sdc_list = [
                {	
                    sdc_id = "c423b09900000004"
                    limit_iops = 150
                    limit_bw_in_mbps = 20
                    access_mode = "ReadWrite"
                },
            ]
        }
    </code>
</pre>

### Examples
<pre>
    <code>
        resource "powerflex_snapshot" "snapshots-create-access-mode-sdc-map" {
            name = "snapshots-create-epsilon"
            volume_id = "4577c84000000120"
            access_mode = "ReadWrite"
            size = 16
            capacity_unit = "GB"
            remove_mode = "INCLUDING_DESCENDANTS"
            sdc_list = [
                {	
                    sdc_id = "c423b09900000004"
                    limit_iops = 150
                    limit_bw_in_mbps = 20
                    access_mode = "ReadWrite"
                },
            ]
        }
    </code>
</pre>

### Notes

<ul>
        <li>Either volume_id or volume_name is required in order to create / modify snapshot.</li>
        <li> Size of the volume should be a multiple of 8.</li>
        <li> specify 0 for unlimited iops..</li>
        <li> To set no limit over bandwidth, 0 is to be passed.</li>
        <li> Specify either sdc_name or sdc_id.</li>
 </ul>


 ## SDS Resource

Manage SDS on Dell EMC PowerFlex

### Synopsis
Managing SDS on PowerFlex storage system includes creating new SDS, adding/removing IP and role to/from SDS, modifying attributes of SDS, and deleting SDS.

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
        <td>id</td>
        <td>The id of the SDS.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_id</td>
        <td>Protection domain id.</td>
        <td>Optioanl&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_name</td>
        <td>Protection domain name.&nbsp;</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>access_mode</td>
        <td>The Access mode of snapshot.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ReadOnly</td>
        <td><ul>
        <li>ReadOnly</li>
        <li>ReadWrite</li>
        </ul></td>
    </tr>
        <tr>
        <td>id</td>
        <td>The ID of the snapshot.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>size</td>
        <td>Size of the snapshot.&nbsp;</td>
        <td>Optional And Computed</td>
        <td>int64&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>capacity_unit</td>
        <td>The unit of the snapshot size.</td>
        <td>Optional And Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td>GB</td>
        <td><ul>
        <li>GB</li>
        <li>TB</li>
        </ul></td>
    </tr>
        <tr>
        <td>size_in_kb</td>
        <td>Size in KB.
        </td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>lock_auto_snapshot</td>
        <td>lock auto snapshot.</td>
        <td>Optional And Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>desired_retention</td>
        <td>desired retention of snapshot.
        </td>
        <td>Optional</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>retention_unit</td>
        <td>retention unit of snapshot.
        </td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>hours</td>
        <td><ul>
        <li>hours</li>
        <li>days</li>
        </ul></td>
    </tr>
    <tr>
        <td>retention_in_min</td>
        <td>retention of snapshot in min.
        </td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>remove_mode</td>
        <td>remove mode of snapshot.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ONLY_ME</td>
        <td><ul>
        <li>ONLY_ME</li>
        <li>INCLUDING_DESCENDANTS</li>
        </ul></td>
    </tr>
    <tr>
        <td>sdc_list</td>
        <td>mapped sdc info.</td>
        <td>Optional And Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sdc_id</td>
        <td>The ID of the SDC.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sdc_name</td>
        <td>The Name of the SDC.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;limit_iops</td>
        <td>Limit of volume IOPS.</td>
        <td>Optional And Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;limit_bw_in_mbps</td>
        <td>Limit of volume network bandwidth.</td>
        <td>Optional And Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;access_mode</td>
        <td>Define the access mode for all mappings of the volume.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td>ReadOnly</td>
        <td><ul>
        <li>ReadOnly</li>
        <li>ReadWrite</li>
        <li>NoAccess</li>
        </ul></td>
    </tr>
    </tbody>
</table>

### Examples
<pre>
    <code>
        resource "powerflex_snapshot" "snapshots-create-access-mode-sdc-map" {
            name = "snapshots-create-epsilon"
            volume_id = "4577c84000000120"
            access_mode = "ReadWrite"
            size = 16
            capacity_unit = "GB"
            remove_mode = "INCLUDING_DESCENDANTS"
            sdc_list = [
                {	
                    sdc_id = "c423b09900000004"
                    limit_iops = 150
                    limit_bw_in_mbps = 20
                    access_mode = "ReadWrite"
                },
            ]
        }
    </code>
</pre>

### Examples
<pre>
    <code>
        resource "powerflex_snapshot" "snapshots-create-access-mode-sdc-map" {
            name = "snapshots-create-epsilon"
            volume_id = "4577c84000000120"
            access_mode = "ReadWrite"
            size = 16
            capacity_unit = "GB"
            remove_mode = "INCLUDING_DESCENDANTS"
            sdc_list = [
                {	
                    sdc_id = "c423b09900000004"
                    limit_iops = 150
                    limit_bw_in_mbps = 20
                    access_mode = "ReadWrite"
                },
            ]
        }
    </code>
</pre>

### Notes

<ul>
        <li>Either volume_id or volume_name is required in order to create / modify snapshot.</li>
        <li> Size of the volume should be a multiple of 8.</li>
        <li> specify 0 for unlimited iops..</li>
        <li> To set no limit over bandwidth, 0 is to be passed.</li>
        <li> Specify either sdc_name or sdc_id.</li>
 </ul>