# Percona XtraDB Cluster 5.7.14-26.17

!!! note

    This release is dedicated to the memory of Federico Goncalvez,  our colleague with Percona’s Uruguayan team until his tragic death on September 6, 2016.

    Fede, you are missed.

Percona is glad to announce the release of
Percona XtraDB Cluster 5.7.14-26.17 on September 29, 2016.
Binaries are available from the
[downloads area](https://www.percona.com/downloads/Percona-XtraDB-Cluster-57/LATEST)
or from our [software repositories](../install/index.md#install).

Percona XtraDB Cluster 5.7.14-26.17 is the first GA release in the 5.7 series,
based on the following:

* [Percona Server 5.7.14-8](https://www.percona.com/doc/percona-server/5.7/release-notes/Percona-Server-5.7.14-8.html)

* [Galera Replicator 3.17](https://github.com/percona/galera/tree/rel-3.17)

For information about the changes
and new features introduced in Percona Server 5.7,
see [Changed in Percona Server 5.7](https://www.percona.com/doc/percona-server/5.7/changed_in_57.html).

## New Features

This is a list of the most important features introduced in Percona XtraDB Cluster 5.7 compared to version 5.6

* [PXC Strict Mode](../features/pxc-strict-mode.md#pxc-strict-mode) saves your workload from experimental and unsupported features.

* Support for monitoring Galera Library instruments
and other wsrep instruments as part of Performance Schema.

* Support for encrypted tablespaces in Multi-Master Topology,
which enables Percona XtraDB Cluster to wire encrypted tablespace to new booting node.

* Compatibility with ProxySQL, including a quick configuration script.

* Support for monitoring Percona XtraDB Cluster nodes using
[Percona Monitoring and Management](https://www.percona.com/software/database-tools/percona-monitoring-and-management)

* More stable and robust operation with MySQL and Percona Server version 5.7.14,
as well as Galera 3.17 compatibility. Includes all upstream bug fixes, improved logging and more.

* Simplified packaging for Percona XtraDB Cluster to a single package
that installs everything it needs, including the Galera library.

* Support for latest XtraBackup with enhanced security checks.

## Bug Fixes

* Fixed crash when a local transaction (such as `EXPLAIN` or `SHOW`)
is interrupted by a replicated transaction with higher priopiry
(like `ALTER` that changes table structure and can thus affect the result of the local transaction).

* Fixed DONOR node getting stuck in `Joined` state after successful SST.

* Fixed error message when altering non-existent table with `pxc-strict-mode` enabled.

* Fixed path to directory in `percona-xtradb-cluster-shared.conf`.

* Fixed setting of `seqno` in `grastate.dat` to `-1` on clean shutdown.

* Fixed failure of asynchronous TOI actions (like `DROP`) for non-primary nodes.

* Fixed replacing of `my.cnf` during upgrade from 5.6 to 5.7.

## Security Fixes

* CVE-2016-6662

* CVE-2016-6663

* CVE-2016-6664

For more information, see [https://www.percona.com/blog/2016/09/12/database-affected-cve-2016-6662/](https://www.percona.com/blog/2016/09/12/database-affected-cve-2016-6662/)

## Other Improvements

Added support of [`defaults-group-suffix`](https://dev.mysql.com/doc/refman/5.7/en/option-file-options.html#option_general_defaults-group-suffix) for SST scripts.
