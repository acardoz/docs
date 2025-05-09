>[!NOTE]
> On an instance in a cluster configuration, former primary nodes were able to access the newly promoted nodes after failover. This was fixed in patch release
>
> {% data reusables.enterprise_clustering.failover-blocks-ips %}
>
> Additionally, the `ghe-cluster-block-ips`, `ghe-cluster-block-ip`, `ghe-cluster-unblock-ips`, and `ghe-cluster-unblock-ip` commands were also introduced in these patch releases. With these commands, you can manually control which IPs can access your newly promoted cluster, and avoid the potentially lengthy configuration run associated with running the whole `ghe-cluster-failover` command.
