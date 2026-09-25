# vSphere Data Collector

> [!NOTE]
> This is a fork of [Combodo/itop-data-collector-vsphere](https://github.com/Combodo/itop-data-collector-vsphere),
> maintained by [Super-Visions](https://github.com/Super-Visions).
> See [CHANGELOG.md](CHANGELOG.md) for what has changed relative to upstream.

This stand-alone PHP application connects to a vSphere server and collects information about an entire
datacenter — extracting a set of CIs and synchronizing them with [iTop](https://itophub.io)'s CMDB using the
data synchronization mechanism built into iTop.

For more information about the original module, have a look at the upstream
[extension documentation](https://www.itophub.io/wiki/page?id=extensions%3Avsphere-data-collector).
Additional features introduced in this fork are described further in this document.

## Features

- Improved compatibility with the absence of Datacenter Management, Advanced Storage Management and
Network Management Extended modules.

## Installation

Create an empty configuration file at `conf/params.local.xml` and adapt the settings to connect to your iTop
instance and vSphere environment. To get the default configuration, run the following command:

```
php exec.php --dump_config_only
```

You can find information about the several configuration items in the files `conf/params.distrib.xml` and
`collectors/params.distrib.xml`.

## Usage

The first time the collector is run, the following command is recommended:

```
php exec.php --configure_only
```

This will create the Synchronization Data Sources if they don't already exist.

To collect the data without synchronizing with iTop, run:

```
php exec.php --collect_only
```

This will store the collected data in CSV files in the `data/` subdirectory of the collector — this is useful for
checking the data before it is passed over to iTop. Mapped values can be checked and mapping tables updated —
however, note that collection should be run again after such changes.

Finally, to perform iTop synchronization with the data collected:

```
php exec.php --synchro_only
```

Data collection and synchronization (and data source update/creation if necessary) can be performed in a single
step if desired:

```
php exec.php
```

While this is simpler, it affords less control over the synchronization process.

More information on running collectors may be found on the
[itop-data-collector-base](https://www.itophub.io/wiki/page?id=extensions%3Aitop-data-collector-base) page.