---
title: "PowerFlex"
linkTitle: "PowerFlex"
no_list: true
description: Documentation for PowerFlex
weight: 20
---


# Terraform Modules for Dell PowerFlex
<!-- © 2021 Dell Inc. or its subsidiaries. All rights reserved. Dell, and other trademarks are trademarks of Dell Inc. or its subsidiaries. Other trademarks may be trademarks of their respective owners. -->

--------------
# Contents
*   [Volume Resource](#volume-resource)
    *   [List Of Parameters](#list-of-parameters)
    *   [Examples](#examples)
    *   [Notes](#notes)
*   [SDC Resource](#sdc-resource)
    *   [List Of Parameters](#list-of-parameters-1)
    *   [Examples](#examples-1)
    *   [Notes](#notes-1)
*   [SDC Datasource Resource](#sdc-datasource-resource)
    *   [List Of Parameters](#list-of-parameters-2)
    *   [Examples](#examples-2)
    *   [Notes](#notes-2)
*   [Storage Pool Resource](#storage-pool-resource)
    *   [List Of Parameters](#list-of-parameters-3)
    *   [Examples](#examples-3)
    *   [Notes](#notes-3)


--------------

## Volume Resource

Details about volume resource

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
        <td>Volume ID</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>name</td>
        <td>Volume Name</td>
        <td>Required&nbsp;</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>volumeType</td>
        <td>Volume Type&nbsp;</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>storagePoolId</td>
        <td>Storage Pool ID&nbsp;</td>
        <td>Required</td>
        <td>String&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>compressionMethod</td>
        <td>Compression Method</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>dataLayout</td>
        <td>Data Layout&nbsp;</td>
        <td>Optional</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sizeInKb</td>
        <td>Size of volume in kb</td>
        <td>Required&nbsp;</td>
        <td>string&nbsp;</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>mappedSdcInfo</td>
        <td>Sdc mapped to volume</td>
        <td>Optional</td>
        <td>list</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>sizeInGB</td>
        <td>New volume size in GB. Basic allocation granularity is 8 GB.
        </td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>volumeClass</td>
        <td>Enter the matching volume class to execute this command if volume is managed externally.
        </td>
        <td>Optional</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>newName</td>
        <td>New name to assign to the Volume</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>removeMode</td>
        <td>Specify the removal mode: ONLY_ME - only the specified volume, INCLUDING_DESCENDANTS - the specified volume
            and its descendants, DESCENDANTS_ONLY - only the descendants of the specified volume, but not the volume
            itself, or WHOLE_VTREE - the entire V-Tree of the specified volume.
        </td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>hostId</td>
        <td>NVMe Host ID or SDC ID</td>
        <td>Required</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>UseRmCache</td>
        <td>Enable rm cache</td>
        <td>Optional</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>mappingToAllSdcsEnabled</td>
        <td>mapping to all sdcs enabled</td>
        <td>Optional</td>
        <td>bool</td>
        <td><br></td>
        <td><br></td>
    </tr>
    <tr>
        <td>vtreeId</td>
        <td>Id of V-Tree for snapshot group</td>
        <td>Optional</td>
        <td>string</td>
        <td><br></td>
        <td><br></td>
    </tr>
    </tbody>
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
</table>

### Examples

### Notes
