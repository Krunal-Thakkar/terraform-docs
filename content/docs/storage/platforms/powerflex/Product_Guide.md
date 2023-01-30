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
*   [Storage Pool Resource](#storage-pool-resource)
    *   [Synopsis](#synopsis-2)
    *   [List Of Parameters](#list-of-parameters-2)
    *   [Examples](#examples-2)
    *   [Notes](#notes-2)
*   [Snapshot Resource](#snapshot-resource)
    *   [Synopsis](#synopsis-3)
    *   [List Of Parameters](#list-of-parameters-3)
    *   [Examples](#examples-3)
    *   [Notes](#notes-3)    
*   [SDS Resource](#sds-resource)
    *   [Synopsis](#synopsis-4)
    *   [List Of Parameters](#list-of-parameters-4)
    *   [Examples](#examples-4)
    *   [Notes](#notes-4) 
*   [SDC Datasource](#sdc-datasource)
    *   [Synopsis](#synopsis-5)
    *   [List Of Parameters](#list-of-parameters-5)
    *   [Examples](#examples-5)
    *   [Notes](#notes-5)    
*   [Protection Domain Datasource](#protection-domain-datasource)
    *   [Synopsis](#synopsis-6)
    *   [List Of Parameters](#list-of-parameters-6)
    *   [Examples](#examples-6)
    *   [Notes](#notes-6)
*   [SDS Datasource](#sds-datasource)
    *   [Synopsis](#synopsis-7)
    *   [List Of Parameters](#list-of-parameters-7)
    *   [Examples](#examples-7)
    *   [Notes](#notes-7)
*   [Storage Pool Datasource](#storage-pool-datasource)
    *   [Synopsis](#synopsis-8)
    *   [List Of Parameters](#list-of-parameters-8)
    *   [Examples](#examples-8)
    *   [Notes](#notes-8) 
*   [Snapshot Policy Datasource](#snapshot-policy-datasource)
    *   [Synopsis](#synopsis-9)
    *   [List Of Parameters](#list-of-parameters-9)
    *   [Examples](#examples-9)
    *   [Notes](#notes-9) 
*   [Volume Datasource](#volume-datasource)
    *   [Synopsis](#synopsis-10)
    *   [List Of Parameters](#list-of-parameters-10)
    *   [Examples](#examples-10)
    *   [Notes](#notes-10) 
                                

--------------

## Volume Resource

Manage volumes on Dell Technologies PowerFlex

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
        <td>Optional And Computed&nbsp;</td>
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

Manage SDCs on Dell Technologies PowerFlex
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

Managing Dell Technologies PowerFlex storage pool

### Synopsis
Dell Technologies PowerFlex storage pool module includes creating a new storage pool, and modifying the attributes of a storage pool.

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
        <td>Optional And Computed&nbsp;</td>
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

Manage SDS on Dell Technologies PowerFlex

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
        <td>Optional&nbsp;</td>
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
        <td>name</td>
        <td>Name of SDS.</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>ip_list</td>
        <td>IP list of SDS.</td>
        <td>Required</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;ip</td>
        <td>IP address to be assigned to the SDS.&nbsp;</td>
        <td>Required</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;role</td>
        <td>Role to be assigned to the IP address.</td>
        <td>Required&nbsp;</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><ul>
        <li>all</li>
        <li>sdcOnly</li>
        <li>sdsOnly</li>
        </ul></td>
    </tr>
        <tr>
        <td>drl_mode</td>
        <td>DRL mode of SDS.
        </td>
        <td>Optional & Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>rmcache_frozen</td>
        <td>RMcache frozen state of SDS.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>fault_set_id</td>
        <td>Fault set id of SDS.
        </td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>rmcache_memory_allocation_state</td>
        <td>Rmcache memory allocation state of SDS.
        </td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>port</td>
        <td>Port of SDS.
        </td>
        <td>Optinal And Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>membership_state</td>
        <td>Membership state of SDS.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>rmcache_enabled</td>
        <td>Rmcache enabled state of SDS.</td>
        <td>Optional And Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>performance_profile</td>
        <td>Performance Profile of SDS.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>rfcache_enabled</td>
        <td>Rfcache enabled state of SDS.</td>
        <td>Optional And Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;is_on_vmware</td>
        <td>Is on vmware state of SDS.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>mdm_connection_state</td>
        <td>Mdm connection state of SDS.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>rmcache_size_in_mb</td>
        <td>Rmcache size in MB of SDS.</td>
        <td>Optional And Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>num_of_io_buffers</td>
        <td>Number of io buffers of SDS.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sds_state</td>
        <td>State of SDS.</td>
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
        resource "powerflex_sds" "sds" {
	      name = "Tf_SDS_01"
	      ip_list = [
		    {
			ip = "10.247.100.232"
			role = "all"
		    },
		    {
			ip = "10.10.10.1"
			role = "sdcOnly"
		    }
	      ]
	      performance_profile = "Compact"
	      rmcache_enabled = true
	      rmcache_size_in_mb = 156
	      rfcache_enabled = true
	      drl_mode = "NonVolatile"
	      protection_domain_id = "4eeb304600000000"
}
    </code>
</pre>

### Notes

<ul>
        <li>Either protection_domain_id or protection_domain_name is required in order to create / modify SDS.</li>
 </ul>

 ## SDC Datasource

Manage SDCs on Dell Technologies PowerFlex
### Synopsis
Managing SDCs on PowerFlex storage system includes getting details of SDC using id or name of SDC

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
        <td>Optional And Computed</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>name</td>
        <td>SDC name.</td>
        <td>Optional And Computed&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sdcs</td>
        <td>result SDCs.&nbsp;</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;id</td>
        <td>SDC ID.&nbsp;</td>
        <td>Computed</td>
        <td>String&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>name</td>
        <td>SDC name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td></td>
    </tr>
    <tr>
        <td>sdc_guid</td>
        <td>SDC GUID.</td>
        <td>Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>on_vmware</td>
        <td>Presence on VMware.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>sdc_approved</td>
        <td>Indicates whether an SDC has approved access to the system.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>system_id</td>
        <td>SDC System ID.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sdc_ip</td>
        <td>SDC IP.</td>
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
    # Get SDC details by id
        data "powerflex_sdc" "selected" {
		id = "c423b09800000003"
	    }

    # Get SDC details by name
        data "powerflex_sdc" "selected" {
		name = "sdc-1"
	    }

    #Get all SDC's
        data "powerflex_sdc" "selected" {
	    }

}
    </code>
</pre>

### Notes
<ul>
<li>id and name are mutually exclusive.</li>
<li>id cannot be empty.</li>
</ul>



## Protection Domain Datasource

Manage protection domain on Dell Technologies PowerFlex
### Synopsis
Managing protection domain on PowerFlex storage system includes getting details of protection domain using id or name of protection domain

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
        <td>Unique identifier of the protection domain instance.</td>
        <td>Optional</td>
        <td>String</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>name</td>
        <td>Unique name of the protection domain instance.</td>
        <td>Optional&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domains</td>
        <td>List of protection domains fetched.&nbsp;</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;id</td>
        <td>Unique identifier of the protection domain instance.&nbsp;</td>
        <td>Computed</td>
        <td>String&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;name</td>
        <td>Unique name of the protection domain instance.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;state</td>
        <td>State of a PD, which can be Active, ActivePending, Inactive or InactivePending.</td>
        <td>Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;system_id</td>
        <td>System ID of the PD.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>&emsp;&emsp;rf_cache_accp_id</td>
        <td>Rf Cache  Acceleration Pool ID.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;rf_cache_enabled</td>
        <td>Whether SDS Rf Cache is enabled or not.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;rf_cache_opertional_mode</td>
        <td>Operational Mode of the SDS RF Cache.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;rf_cache_page_size_kb</td>
        <td>Page size of the SDS RF Cache in KB.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;rf_cache_max_io_size_kb</td>
        <td>Maximum io of the SDS RF Cache in KB.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;fgl_default_num_concurrent_writes</td>
        <td>Fine Granularity default number of concurrent writes.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;fgl_metadata_cache_enabled</td>
        <td>Whether Fine Granularity Metadata Cache is enabled or not.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;fgl_default_metadata_cache_size</td>
        <td>Fine Granularity Metadata Cache size.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;protected_maintenance_mode_network_throttling_enabled</td>
        <td>Whether network throttling is enabled for protected maintenance mode.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;protected_maintenance_mode_network_throttling_in_kbps</td>
        <td>Maximum allowed io for protected maintenance mode in KBps.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebuild_network_throttling_enabled</td>
        <td>Whether network throttling is enabled for rebuilding.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebuild_network_throttling_in_kbps</td>
        <td>Maximum allowed io for rebuilding in KBps.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_network_throttling_enabled</td>
        <td>Whether network throttling is enabled for rebalancing.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_network_throttling_in_kbps</td>
        <td>PMaximum allowed io for rebalancing in KBps.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;vtree_migration_network_throttling_enabled</td>
        <td>Whether network throttling is enabled for vtree migration.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;overall_io_network_throttling_enabled</td>
        <td>Whether network throttling is enabled for overall io.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;overall_io_network_throttling_in_kbps</td>
        <td>Maximum allowed io for protected maintenance mode in KBps. Must be greater than any other network throttling parameter.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;sdr_sds_connectivity</td>
        <td>SDR-SDS Connectivity information.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;client_server_conn_status</td>
        <td>Connectivity Status.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;disconnected_client_id</td>
        <td>ID of the disconnected client.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;disconnected_client_name</td>
        <td>Name of the disconnected client.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;disconnected_server_id</td>
        <td>ID of the disconnected server.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;disconnected_server_name</td>
        <td>Name of the disconnected server.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;disconnected_server_ip</td>
        <td>IP address of the disconnected server.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;sds_decoupled_counter</td>
        <td>SDS Decoupled Counter windows.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sds_configuration_failure_counter</td>
        <td>SDS Configuration Failure Counter windows.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;mdm_sds_network_disconnections_counter</td>
        <td>MDM-SDS Network Disconnection Counter windows.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sds_sds_network_disconnections_counter</td>
        <td>SDS-SDS Network Disconnection Counter windows.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sds_receive_buffer_allocation_failures_counter</td>
        <td>SDS receive Buffer Allocation Failure Counter windows.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
<tr>
        <td>&emsp;&emsp;replication_capacity_max_ratio</td>
        <td>Maximum Replication Capacity Ratio.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;links</td>
        <td>Underlying REST API links.</td>
        <td>Computed</td>
        <td>List</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;rel</td>
        <td>Specifies the relationship with the SDC.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;href</td>
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
    # Get protection domain details by id
        data "powerflex_protection_domain" "pd1" {						
		id = "4eeb304600000000"
	}

    # Get protection domain details by name
        data "powerflex_protection_domain" "pd2" {			
		name = "domain1"
	}

    #Get all protection domains
       data "powerflex_protection_domain" "pd3" {						
	}
}
    </code>
</pre>

### Notes
<ul>
<li>id and name are mutually exclusive.</li>
</ul>



## SDS Datasource

Manage SDS on Dell Technologies PowerFlex
### Synopsis
Managing SDS on PowerFlex storage system includes getting details of SDS using id or name of SDS

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
        <td>protection_domain_id</td>
        <td>Protection Domain ID.</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_name</td>
        <td>Protection Domain Name.</td>
        <td>Optional&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sds_ids</td>
        <td>List of SDS IDs.&nbsp;</td>
        <td>Optional</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sds_names</td>
        <td>List of SDS names.&nbsp;</td>
        <td>Optional</td>
        <td>list&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sds_details</td>
        <td>List of SDS.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;id</td>
        <td>SDS ID.</td>
        <td>Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;name</td>
        <td>SDS name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>&emsp;&emsp;ip_list</td>
        <td>List of IPs associated with SDS.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;ip</td>
        <td>SDS IP.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;role</td>
        <td>SDS IP role.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;port</td>
        <td>SDS port.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;sds_state</td>
        <td>SDS state.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;membership_state</td>
        <td>Membership state.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;mdm_connection_state</td>
        <td>MDM connection state.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;drl_mode</td>
        <td>DRL mode.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rmcache_enabled</td>
        <td>Whether RM cache is enabled or not.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rmcache_size</td>
        <td>Indicates the size of Read RAM Cache on the specified SDS in KB.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rmcache_frozen</td>
        <td>Indicates whether the Read RAM Cache is currently temporarily not in use.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;on_vmware</td>
        <td>Presence on VMware.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;faultset_id</td>
        <td>Fault set ID.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;num_io_buffers</td>
        <td>Number of IO buffers.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rmcache_memory_allocation_state</td>
        <td>Indicates the state of the memory allocation process (in progress/done).</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;performance_profile</td>
        <td>Performance profile.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;software_version_info</td>
        <td>Software version information.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;configured_drl_mode</td>
        <td>Configured DRL mode.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rfcache_enabled</td>
        <td>Whether RF cache is enabled or not.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;maintenance_state</td>
        <td>Maintenance state.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;maintenance_type</td>
        <td>Maintenance type.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rfcache_error_low_resources</td>
        <td>RF cache error for low resources.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rfcache_error_api_version_mismatch</td>
        <td>RF cache error for API version mismatch.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rfcache_error_inconsistent_cache_configuration</td>
        <td>RF cache error for inconsistent cache configuration.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rfcache_error_inconsistent_source_configuration</td>
        <td>RF cache error for inconsistent source configuration.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rfcache_error_invalid_driver_path</td>
        <td>RF cache error for invalid driver path.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rfcache_error_device_does_not_exist</td>
        <td>RF cache error for device does not exist.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;authentication_error</td>
        <td>Authentication error.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;fgl_num_concurrent_writes</td>
        <td>FGL concurrent writes.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;fgl_metadata_cache_state</td>
        <td>FGL metadata cache state.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;fgl_metadata_cache_size</td>
        <td>FGL metadata cache size.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;num_restarts</td>
        <td>Number of restarts.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;last_upgrade_time</td>
        <td>Last time SDS was upgraded.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;sds_decoupled</td>
        <td>SDS decoupled windows.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <td>&emsp;&emsp;sds_configuration_failure</td>
        <td>SDS configuration failure windows.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;sds_receive_buffer_allocation_failures</td>
        <td>SDS receive buffer allocation failure windows.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;short_window</td>
        <td>Short Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;medium_window</td>
        <td>Medium Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;long_window</td>
        <td>Long Window Parameters.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;threshold</td>
        <td>Threshold</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;window_size_in_sec</td>
        <td>Window Size in seconds.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_count</td>
        <td>Last oscillation count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;last_oscillation_time</td>
        <td>Last oscillation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;max_failures_count</td>
        <td>Maximum failures count.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>    
<tr>
        <td>&emsp;&emsp;certificate_info</td>
        <td>Certificate Information.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;subject</td>
        <td>Certificate subject.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;valid_from</td>
        <td>The start date of the certificate validity.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;valid_to</td>
        <td>The end date of the certificate validity.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;thumbprint</td>
        <td>Certificate thumbprint..</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;valid_from_asn1_format</td>
        <td>The start date of the Asn1 format.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;valid_to_asn1_format</td>
        <td>The end date of the Asn1 format.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;raid_controllers</td>
        <td>RAID controllers information.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;serial_number</td>
        <td>Serial number.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;&emsp;&emsp;model_name</td>
        <td>Model name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;vendor_name</td>
        <td>Vendor name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;firmware_version</td>
        <td>Firmware version.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;driver_version</td>
        <td>Driver version.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;driver_name</td>
        <td>Driver name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;&emsp;&emsp;pci_address</td>
        <td>PCI address.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;&emsp;&emsp;status</td>
        <td>RAID status.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;&emsp;&emsp;battery_status</td>
        <td>Battery status.</td>
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
        <td>Specifies the relationship with the SDS.</td>
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
    # Get sds details by sds names and protection domain id
        data "powerflex_sds" "example1" {
            protection_domain_id = "4eeb304600000000"
            sds_names = ["SDS_Test_Tf"]
        }

    # Get sds details by sds ids and protection domain id
        data "powerflex_sds" "example2" {
            protection_domain_id = "4eeb304600000000"
            sds_ids = ["6ae199c500000007"]
        }

    # Get sds details by sds names and protection domain name
        data "powerflex_sds" "example3" {
            protection_domain_name = "domain1"
            sds_names = ["SDS_Test_Tf"]
        }

    # Get sds details by sds id and protection domain name
        data "powerflex_sds" "example4" {
            protection_domain_name = "domain1"
            sds_ids = ["6ae199c500000007"]
        }

    # Get all sds under a protection domain id
        data "powerflex_sds" "example5" {
            protection_domain_id = "4eeb304600000000"
        }
    </code>
</pre>

### Notes
<ul>
<li>protection_domain_id and protection_domain_name are mutually exclusive.</li>
<li>sds_ids and sds_names are mutually exclusive.</li>
<li>Either protection_domain_id or protection_domain_name must mentioned to fetch the details of an sds.</li>

</ul>


## Storage Pool Datasource

Manage Storage Pool on Dell Technologies PowerFlex
### Synopsis
Managing storage pool on PowerFlex storage system includes getting details of storage pool using id or name of storage pool

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
        <td>protection_domain_id</td>
        <td>Protection Domain ID.</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_name</td>
        <td>Protection Domain Name.</td>
        <td>Optional&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pool_ids</td>
        <td>List of storage pool IDs.&nbsp;</td>
        <td>Optional</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pool_names</td>
        <td>List of storage pool names.&nbsp;</td>
        <td>Optional</td>
        <td>list&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pools</td>
        <td>List of storage pools.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;id</td>
        <td>Storage pool ID.</td>
        <td>Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;name</td>
        <td>Storage pool name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>&emsp;&emsp;rebalance_io_priority_policy</td>
        <td>Rebalance IO Priority Policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;rebuild_io_priority_policy</td>
        <td>Rebuild IO Priority Policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;rebuild_io_priority_bw_limit_per_device_in_kbps</td>
        <td>Rebuild Bandwidth Limit per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;rebuild_io_priority_num_of_concurrent_ios_per_device</td>
        <td>Number of Concurrent Rebuild IOPS per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_num_of_concurrent_ios_per_device</td>
        <td>Number of Concurrent Rebalance IOPS per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_bw_limit_per_device_kbps</td>
        <td>Rebalance Bandwidth Limit per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebuild_io_priority_app_iops_per_device_threshold</td>
        <td>Rebuild Application IOPS per Device Threshold.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_app_iops_per_device_threshold</td>
        <td>Rebalance Application IOPS per Device Threshold.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebuild_io_priority_app_bw_per_device_threshold_kbps</td>
        <td>Rebuild Application Bandwidth per Device Threshold.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_app_bw_per_device_threshold_kbps</td>
        <td>Rebalance Application Bandwidth per Device Threshold.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebuild_io_priority_quiet_period_msec</td>
        <td>Rebuild Quiet Period.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_quiet_period_msec</td>
        <td>Rebalance Quiet Period.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;zero_padding_enabled</td>
        <td>Zero Padding Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;use_rm_cache</td>
        <td>Use RAM Read Cache.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;spare_percentage</td>
        <td>Spare Percentage.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rm_cache_write_handling_mode</td>
        <td>RAM Read Cache Write Handling Mode.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rebuild_enabled</td>
        <td>Rebuild Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rebalance_enabled</td>
        <td>Rebalance Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;num_of_parallel_rebuild_rebalance_jobs_per_device</td>
        <td>Number of Parallel Rebuild/Rebalance Jobs per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;background_scanner_bw_limit_kbps</td>
        <td>Background Scanner Bandwidth Limit.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;protected_maintenance_mode_io_priority_num_of_concurrent_ios_per_device</td>
        <td>Number of Concurrent Protected Maintenance Mode IOPS per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;data_layout</td>
        <td>Data Layout.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;vtree_migration_io_priority_bw_limit_per_device_kbps</td>
        <td>VTree Migration Bandwidth Limit per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;vtree_migration_io_priority_policy</td>
        <td>VTree Migration IO Priority Policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;address_space_usage</td>
        <td>Address space usage.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;external_acceleration_type</td>
        <td>External acceleration type.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;persistent_checksum_state</td>
        <td>Persistent Checksum State.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;use_rf_cache</td>
        <td>Use Read Flash Cache.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;checksum_enabled</td>
        <td>Checksum Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;compression_method</td>
        <td>Compression method.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;fragmentation_enabled</td>
        <td>Fragmentation Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;capacity_usage_state</td>
        <td>Capacity usage state (normal/high/critical/full).</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;capacity_usage_type</td>
        <td>Usage state reason.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;address_space_usage_type</td>
        <td>Address space usage reason.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;bg_scanner_compare_error_action</td>
        <td>Scanner compare-error action.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;bg_scanner_read_error_action</td>
        <td>Scanner read-error action.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;replication_capacity_max_ratio</td>
        <td>Replication allowed capacity.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;persistent_checksum_enabled</td>
        <td>Persistent checksum enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;persistent_checksum_builder_limit_kb</td>
        <td>Persistent checksum builder limit.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;persistent_checksum_validate_on_read</td>
        <td>Persistent checksum validation on read.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;vtree_migration_io_priority_num_of_concurrent_ios_per_device</td>
        <td>Number of concurrent VTree migration IOPS per device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;protected_maintenance_mode_io_priority_policy</td>
        <td>Protected maintenance mode IO priority policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;background_scanner_mode</td>
        <td>Scanner mode.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;media_type</td>
        <td>Media type.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;volumes</td>
        <td>List of volumes associated with storage pool.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;id</td>
        <td>Volume ID.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;name</td>
        <td>Volume Name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;sds</td>
        <td>List of SDS associated with storage pool.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;&emsp;&emsp;id</td>
        <td>SDS ID.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;name</td>
        <td>SDS Name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <td>links</td>
        <td>Underlying REST API links.</td>
        <td>Computed</td>
        <td>List</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;rel</td>
        <td>Specifies the relationship with the storage pool.</td>
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
    # Get storage pool details by storage pool names and protection domain id
        data "powerflex_storagepool" "example1" {
            protection_domain_id = "4eeb304600000000"
            storage_pool_names = ["pool2", "pool1"]
        }

    # Get storage pool details by storage pool ids and protection domain id
        data "powerflex_storagepool" "example2" {
            protection_domain_id = "4eeb304600000000"
            storage_pool_ids = ["7630a24600000000", "7630a24800000002"]
        }

    # Get storage pool details by storage pool names and protection domain name
        data "powerflex_storagepool" "example3" {
            protection_domain_name = "domain1"
            storage_pool_names = ["pool2", "pool1"]
        }

    # Get storage pool details by storage pool id and protection domain name
        data "powerflex_storagepool" "example4" {
            protection_domain_name = "domain1"
            storage_pool_ids = ["7630a24600000000", "7630a24800000002"]
        }

    # Get all storage pools under a protection domain id
        data "powerflex_storagepool" "example5" {
            protection_domain_name = "domain1"
        }
    </code>
</pre>

### Notes
<ul>
<li>protection_domain_id and protection_domain_name are mutually exclusive.</li>
<li>storage_pool_ids and storage_pool_names are mutually exclusive.</li>
<li>Either protection_domain_id or protection_domain_name must be mentioned to fetch the details of an sds.</li>

</ul>


## Storage Pool Datasource

Manage Storage Pool on Dell Technologies PowerFlex
### Synopsis
Managing storage pool on PowerFlex storage system includes getting details of storage pool using id or name of storage pool

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
        <td>protection_domain_id</td>
        <td>Protection Domain ID.</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>protection_domain_name</td>
        <td>Protection Domain Name.</td>
        <td>Optional&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pool_ids</td>
        <td>List of storage pool IDs.&nbsp;</td>
        <td>Optional</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pool_names</td>
        <td>List of storage pool names.&nbsp;</td>
        <td>Optional</td>
        <td>list&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pools</td>
        <td>List of storage pools.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;id</td>
        <td>Storage pool ID.</td>
        <td>Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;name</td>
        <td>Storage pool name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>&emsp;&emsp;rebalance_io_priority_policy</td>
        <td>Rebalance IO Priority Policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;rebuild_io_priority_policy</td>
        <td>Rebuild IO Priority Policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;rebuild_io_priority_bw_limit_per_device_in_kbps</td>
        <td>Rebuild Bandwidth Limit per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;rebuild_io_priority_num_of_concurrent_ios_per_device</td>
        <td>Number of Concurrent Rebuild IOPS per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_num_of_concurrent_ios_per_device</td>
        <td>Number of Concurrent Rebalance IOPS per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_bw_limit_per_device_kbps</td>
        <td>Rebalance Bandwidth Limit per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebuild_io_priority_app_iops_per_device_threshold</td>
        <td>Rebuild Application IOPS per Device Threshold.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_app_iops_per_device_threshold</td>
        <td>Rebalance Application IOPS per Device Threshold.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebuild_io_priority_app_bw_per_device_threshold_kbps</td>
        <td>Rebuild Application Bandwidth per Device Threshold.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_app_bw_per_device_threshold_kbps</td>
        <td>Rebalance Application Bandwidth per Device Threshold.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebuild_io_priority_quiet_period_msec</td>
        <td>Rebuild Quiet Period.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rebalance_io_priority_quiet_period_msec</td>
        <td>Rebalance Quiet Period.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;zero_padding_enabled</td>
        <td>Zero Padding Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;use_rm_cache</td>
        <td>Use RAM Read Cache.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;spare_percentage</td>
        <td>Spare Percentage.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;rm_cache_write_handling_mode</td>
        <td>RAM Read Cache Write Handling Mode.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rebuild_enabled</td>
        <td>Rebuild Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;rebalance_enabled</td>
        <td>Rebalance Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;num_of_parallel_rebuild_rebalance_jobs_per_device</td>
        <td>Number of Parallel Rebuild/Rebalance Jobs per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;background_scanner_bw_limit_kbps</td>
        <td>Background Scanner Bandwidth Limit.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;protected_maintenance_mode_io_priority_num_of_concurrent_ios_per_device</td>
        <td>Number of Concurrent Protected Maintenance Mode IOPS per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;data_layout</td>
        <td>Data Layout.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;vtree_migration_io_priority_bw_limit_per_device_kbps</td>
        <td>VTree Migration Bandwidth Limit per Device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;vtree_migration_io_priority_policy</td>
        <td>VTree Migration IO Priority Policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;address_space_usage</td>
        <td>Address space usage.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;external_acceleration_type</td>
        <td>External acceleration type.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;persistent_checksum_state</td>
        <td>Persistent Checksum State.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;use_rf_cache</td>
        <td>Use Read Flash Cache.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;checksum_enabled</td>
        <td>Checksum Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;compression_method</td>
        <td>Compression method.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;fragmentation_enabled</td>
        <td>Fragmentation Enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;capacity_usage_state</td>
        <td>Capacity usage state (normal/high/critical/full).</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;capacity_usage_type</td>
        <td>Usage state reason.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;address_space_usage_type</td>
        <td>Address space usage reason.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;bg_scanner_compare_error_action</td>
        <td>Scanner compare-error action.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;bg_scanner_read_error_action</td>
        <td>Scanner read-error action.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;replication_capacity_max_ratio</td>
        <td>Replication allowed capacity.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;persistent_checksum_enabled</td>
        <td>Persistent checksum enabled.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;persistent_checksum_builder_limit_kb</td>
        <td>Persistent checksum builder limit.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;persistent_checksum_validate_on_read</td>
        <td>Persistent checksum validation on read.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;vtree_migration_io_priority_num_of_concurrent_ios_per_device</td>
        <td>Number of concurrent VTree migration IOPS per device.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;protected_maintenance_mode_io_priority_policy</td>
        <td>Protected maintenance mode IO priority policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;background_scanner_mode</td>
        <td>Scanner mode.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;media_type</td>
        <td>Media type.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;volumes</td>
        <td>List of volumes associated with storage pool.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;id</td>
        <td>Volume ID.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;name</td>
        <td>Volume Name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
     <tr>
        <td>&emsp;&emsp;sds</td>
        <td>List of SDS associated with storage pool.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;&emsp;&emsp;id</td>
        <td>SDS ID.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;name</td>
        <td>SDS Name.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <td>links</td>
        <td>Underlying REST API links.</td>
        <td>Computed</td>
        <td>List</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;rel</td>
        <td>Specifies the relationship with the storage pool.</td>
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
    # Get storage pool details by storage pool names and protection domain id
        data "powerflex_storagepool" "example1" {
            protection_domain_id = "4eeb304600000000"
            storage_pool_names = ["pool2", "pool1"]
        }

    # Get storage pool details by storage pool ids and protection domain id
        data "powerflex_storagepool" "example2" {
            protection_domain_id = "4eeb304600000000"
            storage_pool_ids = ["7630a24600000000", "7630a24800000002"]
        }

    # Get storage pool details by storage pool names and protection domain name
        data "powerflex_storagepool" "example3" {
            protection_domain_name = "domain1"
            storage_pool_names = ["pool2", "pool1"]
        }

    # Get storage pool details by storage pool id and protection domain name
        data "powerflex_storagepool" "example4" {
            protection_domain_name = "domain1"
            storage_pool_ids = ["7630a24600000000", "7630a24800000002"]
        }

    # Get all storage pools under a protection domain id
        data "powerflex_storagepool" "example5" {
            protection_domain_name = "domain1"
        }
    </code>
</pre>

### Notes
<ul>
<li>protection_domain_id and protection_domain_name are mutually exclusive.</li>
<li>storage_pool_ids and storage_pool_names are mutually exclusive.</li>
<li>Either protection_domain_id or protection_domain_name must be mentioned to fetch the details of an sds.</li>

</ul>


## Snapshot Policy Datasource

Manage Snapshot Policy on Dell Technologies PowerFlex
### Synopsis
Managing snapshot policy on PowerFlex storage system includes getting details of snapshot policy using id or name of snapshot policy

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
        <td>ID of the snapshot policy instance.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>name</td>
        <td>Name of the snapshot policy.</td>
        <td>Optional&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>snapshotpolicies</td>
        <td>List of snapshot policies.&nbsp;</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;id</td>
        <td>ID of the snapshot policy instance.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;name</td>
        <td>Name of the snapshot policy.</td>
        <td>Optional&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;snapshot_policy_state</td>
        <td>Specifies the current state of the snapshot policy.</td>
        <td>Computed&nbsp;</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;auto_snapshot_creation_cadence_in_min</td>
        <td>Auto snapshot creation cadence in min.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>&emsp;&emsp;max_vtree_auto_snapshots</td>
        <td>Max vtree auto snapshots.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;num_of_source_volumes</td>
        <td>Number of source Volumes.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;num_of_expired_but_locked_snapshots</td>
        <td>Number of expired but locked snapshots.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;num_of_creation_failures</td>
        <td>Number of creation failures.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;num_of_retained_snapshots_per_level</td>
        <td>Number of retained snapshots per level.</td>
        <td>Computed</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;snapshot_access_mode</td>
        <td>Snapshot Access Mode.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;secure_snapshots</td>
        <td>Secure snapshots.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;time_of_last_auto_snapshot</td>
        <td>Time of last auto snapshot.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;next_auto_snapshot_creation_time</td>
        <td>Next auto snapshot creation time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;time_of_last_auto_snapshot_creation_failure</td>
        <td>Time of last auto snapshot creation failure.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;last_auto_snapshot_creation_failure_reason</td>
        <td>Last auto snapshot creation failure reason.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;last_auto_snapshot_failure_in_first_level</td>
        <td>Last auto snapshot failure in first level.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;num_of_auto_snapshots</td>
        <td>Number of auto snapshots.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;num_of_locked_snapshots</td>
        <td>Number of locked snapshots.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;system_id</td>
        <td>System Identifier.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>     
        <td>links</td>
        <td>Underlying REST API links.</td>
        <td>Computed</td>
        <td>List</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;rel</td>
        <td>Specifies the relationship with the snapshot policy.</td>
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
    # Get snapshot policy details by snapshot policy  id
        data "powerflex_snapshotpolicy" "sp1" {						
            id = "15ad99b900000001"
        }

    # Get snapshot policy details by snapshot policy name
        data "powerflex_snapshotpolicy" "sp2" {						
            name = "sample_snap_policy_1"
        }

    # Get all the snapshot policies
        data "powerflex_snapshotpolicy" "sp3" {						
        }
    </code>
</pre>

### Notes
<ul>
<li>id and name are mutually exclusive.</li>
<li>id and name cannot be empty</li>
</ul>


## Volume Datasource

Manage Volume on Dell Technologies PowerFlex
### Synopsis
Managing volume on PowerFlex storage system includes getting details of volume using id or name of volume

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
        <td>ID of the volume instance.</td>
        <td>Optional And Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>name</td>
        <td>Name of the volume.</td>
        <td>Optional&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pool_id</td>
        <td>ID of the storage pool instance.&nbsp;</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storage_pool_name</td>
        <td>Name of the storage pool.</td>
        <td>Optional </td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;volumes</td>
        <td>List of volumes.</td>
        <td>Computed&nbsp;</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;id</td>
        <td>ID of the volume instance.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;name</td>
        <td>Name of the volume.</td>
        <td>Computed&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>&emsp;&emsp;creation_time</td>
        <td>Specifies the time of creation.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;size_in_kb</td>
        <td>Size of the volume in KB.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>&emsp;&emsp;ancestor_volume_id</td>
        <td>The volume id to which the snapshot is linked to.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;vtree_id</td>
        <td>Unique identifier of the VTree</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>
        <td>&emsp;&emsp;consistency_group_id</td>
        <td>The unique id for the consistency group.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;volume_type</td>
        <td>Specifies the type of that volume.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;use_rm_cache</td>
        <td>Enable rm cache.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;storage_pool_id</td>
        <td>Specifies the unique identifier of the storage pool.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;data_layout</td>
        <td>Specifies the layout for the data.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;not_genuine_snapshot</td>
        <td>Specifies if not genuine snapshot.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;access_mode_limit</td>
        <td>Specifies the access mode limit.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;secure_snapshot_exp_time</td>
        <td>Specifies the secure snapshot expiry time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;managed_by</td>
        <td>Specifies by whom it's managed by.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;locked_auto_snapshot</td>
        <td>Specifies if it's a locked auto snapshot.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
        <tr>
        <td>&emsp;&emsp;locked_auto_snapshot_marked_for_removal</td>
        <td>Specifies if it's a locked auto snapshot marked for removal.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>  
    <tr>
        <td>&emsp;&emsp;compression_method</td>
        <td>Specifies the compression method.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;time_stamp_is_accurate</td>
        <td>Specifies if the time stamp is accurate.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;original_expiry_time</td>
        <td>Specifies the original expiry time.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;volume_replication_state</td>
        <td>Specifies the volume replication state.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;replication_journal_volume</td>
        <td>Specifies the replication journal volume.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;replication_time_stamp</td>
        <td>Specifies the replication time stamp.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>    
    </tr>  
    <tr>  
        <td>&emsp;&emsp;mapped_sdc_info</td>
        <td>Specifies the list of sdc's mapped to a volume.</td>
        <td>Computed</td>
        <td>List</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>  
        <td>&emsp;&emsp;&emsp;&emsp;sdc_id</td>
        <td>Unique identifier for sdc.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>  
        <td>&emsp;&emsp;&emsp;&emsp;sdc_ip</td>
        <td>Ip of the sdc.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>  
        <td>&emsp;&emsp;&emsp;&emsp;limit_iops</td>
        <td>Specifies the IOPS limits.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>  
        <td>&emsp;&emsp;&emsp;&emsp;limit_bw_in_mbps</td>
        <td>Specifies the bandwidth limits in Mbps.</td>
        <td>Computed</td>
        <td>int64</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>  
        <td>&emsp;&emsp;&emsp;&emsp;sdc_name</td>
        <td>Specifies the name of the sdc.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>  
        <td>&emsp;&emsp;&emsp;&emsp;access_mode</td>
        <td>Specifies the access mode.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>  
        <td>&emsp;&emsp;&emsp;&emsp;is_direct_buffer_mapping</td>
        <td>Specifies if it is direct buffer mapping.</td>
        <td>Computed</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
        <tr>  
        <td>&emsp;&emsp;links</td>
        <td>Underlying REST API links.</td>
        <td>Computed</td>
        <td>List</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;rel</td>
        <td>Specifies the relationship with the snapshot policy.</td>
        <td>Computed</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr> 
    <tr>
        <td>&emsp;&emsp;&emsp;&emsp;href</td>
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
    # Get volume details by volume id
        data "powerflex_volume" "all" {						
            id = "457752ff000000c7"
        }

    # Get volume details by volume name
        data "powerflex_volume" "all" {						
            name = "cicd-dbc5a5909d"
        }

    # Get all the volumes
        data "powerflex_volume" "all" {						
        }

    # Get all the volumes under a storage pool using storage pool id
        data "powerflex_volume" "all" {						
            storage_pool_id = "7630a24600000000"
        }

    # Get all the volumes under a storage pool using storage pool name
        data "powerflex_volume" "all" {						
            storage_pool_name = "pool1"
        }               
    </code>
</pre>

### Notes
<ul>
<li>id , name , storage_pool_id, storage_pool_nameare mutually exclusive and cannot be empty.</li>
</ul>

