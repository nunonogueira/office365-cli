# spo site list

Lists modern sites of the given type

## Usage

```sh
spo site list [options]
```

## Options

Option|Description
------|-----------
`--help`|output usage information
`--type [type]`|type of modern sites to list. Allowed values `TeamSite|CommunicationSite`, default `TeamSite`
`-f, --filter [filter]`|filter to apply when retrieving sites
`-o, --output <output>`|Output type. `json|text`. Default `text`
`--verbose`|Runs command with verbose logging
`--debug`|Runs command with debug logging

!!! important
    Before using this command, connect to a SharePoint Online tenant admin site, using the [spo connect](../connect.md) command.

## Remarks

To list modern sites, you have to first connect to a tenant admin site using the [spo connect](../connect.md) command, eg. `spo connect https://contoso-admin.sharepoint.com`. If you are connected to a different site and will try to list the available sites, you will get an error.

Using the `-f, --filter` option you can specify which sites you want to retrieve. For example, to get sites with _project_ in their URL, use `Url -like 'project'` as the filter.

## Examples

List all modern team sites in the currently connected tenant

```sh
spo site list
```

List all modern team sites in the currently connected tenant

```sh
spo site list --type TeamSite
```

List all modern communication sites in the currently connected tenant

```sh
spo site list --type CommunicationSite
```

List all modern team sites that contain _project_ in the URL

```sh
spo site list --type TeamSite --filter "Url -like 'project'"
```