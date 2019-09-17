---
name: Import Export API
route: /Import-Export-API
menu: Documentation
submenu: Import/Export
---

import  themen  from 'theme/styles/styled-colors';
import  * as theme  from 'react-syntax-highlighter/dist/esm/styles/hljs';
import SyntaxHighlighter from 'react-syntax-highlighter';

# Export & Import REST APIs

### What's New
The release of 0.8.3 includes the following improvements to Export and Import APIs:
   * Export: Support for [Incremental Export](Incremental-Export).
   * Export & Import: Support for [replicated attributes](ReplicatedToFromAttributes) to entities made possible by [SoftReference](SoftReference) entity attribute option.
   * Export option: [skipLineage](skipLineage).
   * New entity transforms framework.
   * New [AtlasServer](AtlasServer) entity type.
   * Export: [Automatic creation of HDFS path](Export-HDFS-API) requested entities.
   * New [ExportImportAudits](ExportImportAudits) for Export & Import operations.

### Background
The Import-Export APIs for Atlas facilitate transfer of data to and from a cluster that has Atlas provisioned.

The APIs when integrated with backup and/or disaster recovery process will ensure participation of Atlas.

### Introduction
There are 2 broad categories viz. Export & Import. The details of the APIs are discussed below.

The APIs are available only to _admin_ user.

Only a single import or export operation can be performed at a given time. The operations have a potential for generating large amount. They can also put pressure on resources. This restriction tries to alleviate this problem.

For Import-Export APIs relating to HDFS path, can be found [here](Import-Export-HDFS-Path).

For additional information please refer to the following:
   * [ATLAS-1503](https://issues.apache.org/jira/browse/ATLAS-1503) Original Import-Export API requirements.
   * [ATLAS-1618](https://issues.apache.org/jira/browse/ATLAS-1618) Export API Scope Specification.

### Errors
If an import or export operation is initiated while another is in progress, the consumer will receive this error:

<SyntaxHighlighter wrapLines={true} language="shell" style={theme.dark}>
{`"ATLAS5005E": "Another import or export is in progress. Please try again."`}
</SyntaxHighlighter>

Unhandled errors will be returned as Internal error code 500.

### REST API Reference
   * [Export](Export-API)
   * [Export HDFS](Export-HDFS-API)
   * [Import](Import-API)
   * [Import Options](Import-API-Options)
