# CreateReplicationConfigKeyTable(void)

- ea: `0x1404fe3d8`
- end: `0x1404fe721`
- name: `?CreateReplicationConfigKeyTable@@YAXXZ`
- size: `841`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1403b142c`

## string_xrefs

- `0x1404fe5a6`: `/configuration/global_settings/replication/extended_settings`
- `0x1404fe598`: `/configuration/global_settings/replication/settings`
- `0x1404fe712`: `/configuration/global_settings/replication/extended_settings/included_disks/disk%.3d`
- `0x1404fe6f6`: `/configuration/global_settings/replication/extended_settings/included_disks/count`
- `0x1404fe4f0`: `/configuration/global_settings/replication/settings/recovery_snapshot_range`
- `0x1404fe6a2`: `/configuration/global_settings/replication/extended_tracker/pending_delta_transfer/size`
- `0x1404fe6da`: `/configuration/global_settings/replication/extended_tracker/pending_delta_transfer/disk%.3d/log_file_path`
- `0x1404fe4d4`: `/configuration/global_settings/replication/settings/primary_server_node`
- `0x1404fe608`: `/configuration/global_settings/replication/tracker/resynchronize/size`
- `0x1404fe480`: `/configuration/global_settings/replication/settings/root_certificate_thumbprint`
- `0x1404fe3d8`: `/configuration/global_settings/replication/settings/recovery_server`
- `0x1404fe464`: `/configuration/global_settings/replication/settings/certificate_thumbprint`
- `0x1404fe448`: `/configuration/global_settings/replication/settings/authentication_type`
- `0x1404fe3f4`: `/configuration/global_settings/replication/settings/recovery_server_port`
- `0x1404fe544`: `/configuration/global_settings/replication/settings/autoresync_window_end`
- `0x1404fe57c`: `/configuration/global_settings/replication/settings/replication_interval`
- `0x1404fe560`: `/configuration/global_settings/replication/settings/hostonly_kvp_replication_enabled`
- `0x1404fe528`: `/configuration/global_settings/replication/settings/autoresync_window_start`
- `0x1404fe42c`: `/configuration/global_settings/replication/settings/bypass_proxy`
- `0x1404fe50c`: `/configuration/global_settings/replication/settings/autoresync_enabled`
- `0x1404fe49c`: `/configuration/global_settings/replication/settings/compression_enabled`
- `0x1404fe694`: `/configuration/global_settings/replication/tracker/pending_delta_transfer/size`
- `0x1404fe410`: `/configuration/global_settings/replication/settings/recovery_server_node`
- `0x1404fe4b8`: `/configuration/global_settings/replication/settings/primary_server`
- `0x1404fe6cc`: `/configuration/global_settings/replication/tracker/pending_delta_transfer/disk%.3d/log_file_path`
- `0x1404fe704`: `/configuration/global_settings/replication/settings/included_disks/disk%.3d`
- `0x1404fe6e8`: `/configuration/global_settings/replication/settings/included_disks/count`
- `0x1404fe66a`: `/configuration/global_settings/replication/extended_tracker/resynchronize_start_tickcount`
- `0x1404fe5b4`: `/configuration/global_settings/replication/settings/additional_settings`
- `0x1404fe58a`: `/configuration/global_settings/replication/extended_settings/replication_interval`
- `0x1404fe552`: `/configuration/global_settings/replication/extended_settings/autoresync_window_end`
- `0x1404fe5de`: `/configuration/global_settings/replication/extended_tracker/resynchronize`
- `0x1404fe5c2`: `/configuration/global_settings/replication/extended_settings/additional_settings`
- `0x1404fe6b0`: `/configuration/global_settings/replication/tracker/pending_delta_transfer/disk%.3d/wmi_instance_id`
- `0x1404fe4c6`: `/configuration/global_settings/replication/extended_settings/primary_server`
- `0x1404fe624`: `/configuration/global_settings/replication/tracker/resynchronize/disk%.3d/wmi_instance_id`
- `0x1404fe43a`: `/configuration/global_settings/replication/extended_settings/bypass_proxy`
- `0x1404fe616`: `/configuration/global_settings/replication/extended_tracker/resynchronize/size`
- `0x1404fe686`: `/configuration/global_settings/replication/extended_settings/endpointprovider/clsid`
- `0x1404fe678`: `/configuration/global_settings/replication/settings/endpointprovider/clsid`
- `0x1404fe536`: `/configuration/global_settings/replication/extended_settings/autoresync_window_start`
- `0x1404fe4fe`: `/configuration/global_settings/replication/extended_settings/recovery_snapshot_range`
- `0x1404fe402`: `/configuration/global_settings/replication/extended_settings/recovery_server_port`
- `0x1404fe632`: `/configuration/global_settings/replication/extended_tracker/resynchronize/disk%.3d/wmi_instance_id`
- `0x1404fe5fa`: `/configuration/global_settings/replication/extended_tracker/resynchronize/transfer_id`
- `0x1404fe456`: `/configuration/global_settings/replication/extended_settings/authentication_type`
- `0x1404fe64e`: `/configuration/global_settings/replication/extended_tracker/resynchronize/disk%.3d/blocks_done`
- `0x1404fe48e`: `/configuration/global_settings/replication/extended_settings/root_certificate_thumbprint`
- `0x1404fe4e2`: `/configuration/global_settings/replication/extended_settings/primary_server_node`
- `0x1404fe3e6`: `/configuration/global_settings/replication/extended_settings/recovery_server`
- `0x1404fe5d0`: `/configuration/global_settings/replication/tracker/resynchronize`
- `0x1404fe65c`: `/configuration/global_settings/replication/tracker/resynchronize_start_tickcount`
- `0x1404fe4aa`: `/configuration/global_settings/replication/extended_settings/compression_enabled`
- `0x1404fe640`: `/configuration/global_settings/replication/tracker/resynchronize/disk%.3d/blocks_done`
- `0x1404fe5ec`: `/configuration/global_settings/replication/tracker/resynchronize/transfer_id`
- `0x1404fe6be`: `/configuration/global_settings/replication/extended_tracker/pending_delta_transfer/disk%.3d/wmi_instance_id`
- `0x1404fe51a`: `/configuration/global_settings/replication/extended_settings/autoresync_enabled`
- `0x1404fe472`: `/configuration/global_settings/replication/extended_settings/certificate_thumbprint`
- `0x1404fe56e`: `/configuration/global_settings/replication/extended_settings/hostonly_kvp_replication_enabled`
- `0x1404fe41e`: `/configuration/global_settings/replication/extended_settings/recovery_server_node`

## pseudocode

```c
void CreateReplicationConfigKeyTable(void)
{
  g_ReplicationConfigKeyTable = (const unsigned __int16 *(near *)[2])L"/configuration/global_settings/replication/settings"
                                                                      "/recovery_server";
  qword_140D2D058 = (__int64)L"/configuration/global_settings/replication/extended_settings/recovery_server";
  qword_140D2D060 = (__int64)L"/configuration/global_settings/replication/settings/recovery_server_port";
  qword_140D2D068 = (__int64)L"/configuration/global_settings/replication/extended_settings/recovery_server_port";
  qword_140D2D070 = (__int64)L"/configuration/global_settings/replication/settings/recovery_server_node";
  qword_140D2D078 = (__int64)L"/configuration/global_settings/replication/extended_settings/recovery_server_node";
  qword_140D2D080 = (__int64)L"/configuration/global_settings/replication/settings/bypass_proxy";
  qword_140D2D088 = (__int64)L"/configuration/global_settings/replication/extended_settings/bypass_proxy";
  qword_140D2D090 = (__int64)L"/configuration/global_settings/replication/settings/authentication_type";
  qword_140D2D098 = (__int64)L"/configuration/global_settings/replication/extended_settings/authentication_type";
  qword_140D2D0A0 = (__int64)L"/configuration/global_settings/replication/settings/certificate_thumbprint";
  qword_140D2D0A8 = (__int64)L"/configuration/global_settings/replication/extended_settings/certificate_thumbprint";
  qword_140D2D0B0 = (__int64)L"/configuration/global_settings/replication/settings/root_certificate_thumbprint";
  qword_140D2D0B8 = (__int64)L"/configuration/global_settings/replication/extended_settings/root_certificate_thumbprint";
  qword_140D2D0C0 = (__int64)L"/configuration/global_settings/replication/settings/compression_enabled";
  qword_140D2D0C8 = (__int64)L"/configuration/global_settings/replication/extended_settings/compression_enabled";
  qword_140D2D0D0 = (__int64)L"/configuration/global_settings/replication/settings/primary_server";
  qword_140D2D0D8 = (__int64)L"/configuration/global_settings/replication/extended_settings/primary_server";
  qword_140D2D0E0 = (__int64)L"/configuration/global_settings/replication/settings/primary_server_node";
  qword_140D2D0E8 = (__int64)L"/configuration/global_settings/replication/extended_settings/primary_server_node";
  qword_140D2D0F0 = (__int64)L"/configuration/global_settings/replication/settings/recovery_snapshot_range";
  qword_140D2D0F8 = (__int64)L"/configuration/global_settings/replication/extended_settings/recovery_snapshot_range";
  qword_140D2D100 = (__int64)L"/configuration/global_settings/replication/settings/autoresync_enabled";
  qword_140D2D108 = (__int64)L"/configuration/global_settings/replication/extended_settings/autoresync_enabled";
  qword_140D2D110 = (__int64)L"/configuration/global_settings/replication/settings/autoresync_window_start";
  qword_140D2D118 = (__int64)L"/configuration/global_settings/replication/extended_settings/autoresync_window_start";
  qword_140D2D120 = (__int64)L"/configuration/global_settings/replication/settings/autoresync_window_end";
  qword_140D2D128 = (__int64)L"/configuration/global_settings/replication/extended_settings/autoresync_window_end";
  qword_140D2D130 = (__int64)L"/configuration/global_settings/replication/settings/hostonly_kvp_replication_enabled";
  qword_140D2D138 = (__int64)L"/configuration/global_settings/replication/extended_settings/hostonly_kvp_replication_enabled";
  qword_140D2D140 = (__int64)L"/configuration/global_settings/replication/settings/replication_interval";
  qword_140D2D148 = (__int64)L"/configuration/global_settings/replication/extended_settings/replication_interval";
  qword_140D2D150 = (__int64)L"/configuration/global_settings/replication/settings";
  qword_140D2D158 = (__int64)L"/configuration/global_settings/replication/extended_settings";
  qword_140D2D160 = (__int64)L"/configuration/global_settings/replication/settings/additional_settings";
  qword_140D2D168 = (__int64)L"/configuration/global_settings/replication/extended_settings/additional_settings";
  qword_140D2D170 = (__int64)L"/configuration/global_settings/replication/tracker/resynchronize";
  qword_140D2D178 = (__int64)L"/configuration/global_settings/replication/extended_tracker/resynchronize";
  qword_140D2D180 = (__int64)L"/configuration/global_settings/replication/tracker/resynchronize/transfer_id";
  qword_140D2D188 = (__int64)L"/configuration/global_settings/replication/extended_tracker/resynchronize/transfer_id";
  qword_140D2D190 = (__int64)L"/configuration/global_settings/replication/tracker/resynchronize/size";
  qword_140D2D198 = (__int64)L"/configuration/global_settings/replication/extended_tracker/resynchronize/size";
  qword_140D2D1A0 = (__int64)L"/configuration/global_settings/replication/tracker/resynchronize/disk%.3d/wmi_instance_id";
  qword_140D2D1A8 = (__int64)L"/configuration/global_settings/replication/extended_tracker/resynchronize/disk%.3d/wmi_instance_id";
  qword_140D2D1B0 = (__int64)L"/configuration/global_settings/replication/tracker/resynchronize/disk%.3d/blocks_done";
  qword_140D2D1B8 = (__int64)L"/configuration/global_settings/replication/extended_tracker/resynchronize/disk%.3d/blocks_done";
  qword_140D2D1C0 = (__int64)L"/configuration/global_settings/replication/tracker/resynchronize_start_tickcount";
  qword_140D2D1C8 = (__int64)L"/configuration/global_settings/replication/extended_tracker/resynchronize_start_tickcount";
  qword_140D2D1D0 = (__int64)L"/configuration/global_settings/replication/settings/endpointprovider/clsid";
  qword_140D2D1D8 = (__int64)L"/configuration/global_settings/replication/extended_settings/endpointprovider/clsid";
  qword_140D2D1E0 = (__int64)L"/configuration/global_settings/replication/tracker/pending_delta_transfer/size";
  qword_140D2D1E8 = (__int64)L"/configuration/global_settings/replication/extended_tracker/pending_delta_transfer/size";
  qword_140D2D1F0 = (__int64)L"/configuration/global_settings/replication/tracker/pending_delta_transfer/disk%.3d/wmi_instance_id";
  qword_140D2D1F8 = (__int64)L"/configuration/global_settings/replication/extended_tracker/pending_delta_transfer/disk%.3d"
                              "/wmi_instance_id";
  qword_140D2D200 = (__int64)L"/configuration/global_settings/replication/tracker/pending_delta_transfer/disk%.3d/log_file_path";
  qword_140D2D208 = (__int64)L"/configuration/global_settings/replication/extended_tracker/pending_delta_transfer/disk%.3d/log_file_path";
  qword_140D2D210 = (__int64)L"/configuration/global_settings/replication/settings/included_disks/count";
  qword_140D2D218 = (__int64)L"/configuration/global_settings/replication/extended_settings/included_disks/count";
  qword_140D2D220 = (__int64)L"/configuration/global_settings/replication/settings/included_disks/disk%.3d";
  qword_140D2D228 = (__int64)L"/configuration/global_settings/replication/extended_settings/included_disks/disk%.3d";
}

```

## disassembly

```asm
0x1404fe3d8  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RECOVERY_SERVER@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe3df  mov     cs:?g_ReplicationConfigKeyTable@@3PAY01PEBGA, rax; ushort const * (near * g_ReplicationConfigKeyTable)[2]
0x1404fe3e6  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RECOVERY_SERVER@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe3ed  mov     cs:qword_140D2D058, rax
0x1404fe3f4  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RECOVERY_SERVER_PORT@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe3fb  mov     cs:qword_140D2D060, rax
0x1404fe402  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RECOVERY_SERVER_PORT@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe409  mov     cs:qword_140D2D068, rax
0x1404fe410  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RECOVERY_SERVER_NODE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe417  mov     cs:qword_140D2D070, rax
0x1404fe41e  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RECOVERY_SERVER_NODE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe425  mov     cs:qword_140D2D078, rax
0x1404fe42c  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_BYPASS_PROXY@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe433  mov     cs:qword_140D2D080, rax
0x1404fe43a  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_BYPASS_PROXY@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe441  mov     cs:qword_140D2D088, rax
0x1404fe448  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_AUTHENTICATION_TYPE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe44f  mov     cs:qword_140D2D090, rax
0x1404fe456  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_AUTHENTICATION_TYPE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe45d  mov     cs:qword_140D2D098, rax
0x1404fe464  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_CERTIFICATE_THUMBPRINT@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe46b  mov     cs:qword_140D2D0A0, rax
0x1404fe472  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_CERTIFICATE_THUMBPRINT@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe479  mov     cs:qword_140D2D0A8, rax
0x1404fe480  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_ROOT_CERTIFICATE_THUMBPRINT@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe487  mov     cs:qword_140D2D0B0, rax
0x1404fe48e  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_ROOT_CERTIFICATE_THUMBPRINT@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe495  mov     cs:qword_140D2D0B8, rax
0x1404fe49c  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_COMPRESSION_ENABLED@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe4a3  mov     cs:qword_140D2D0C0, rax
0x1404fe4aa  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_COMPRESSION_ENABLED@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe4b1  mov     cs:qword_140D2D0C8, rax
0x1404fe4b8  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_PRIMARY_SERVER@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe4bf  mov     cs:qword_140D2D0D0, rax
0x1404fe4c6  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_PRIMARY_SERVER@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe4cd  mov     cs:qword_140D2D0D8, rax
0x1404fe4d4  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_PRIMARY_SERVER_NODE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe4db  mov     cs:qword_140D2D0E0, rax
0x1404fe4e2  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_PRIMARY_SERVER_NODE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe4e9  mov     cs:qword_140D2D0E8, rax
0x1404fe4f0  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RECOVERY_SNAPSHOT_RANGE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe4f7  mov     cs:qword_140D2D0F0, rax
0x1404fe4fe  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RECOVERY_SNAPSHOT_RANGE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe505  mov     cs:qword_140D2D0F8, rax
0x1404fe50c  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_AUTORESYNC_ENABLED@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe513  mov     cs:qword_140D2D100, rax
0x1404fe51a  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_AUTORESYNC_ENABLED@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe521  mov     cs:qword_140D2D108, rax
0x1404fe528  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_AUTORESYNC_WINDOW_START@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe52f  mov     cs:qword_140D2D110, rax
0x1404fe536  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_AUTORESYNC_WINDOW_START@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe53d  mov     cs:qword_140D2D118, rax
0x1404fe544  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_AUTORESYNC_WINDOW_END@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe54b  mov     cs:qword_140D2D120, rax
0x1404fe552  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_AUTORESYNC_WINDOW_END@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe559  mov     cs:qword_140D2D128, rax
0x1404fe560  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_KVP_REPLICATION_ENABLED@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe567  mov     cs:qword_140D2D130, rax
0x1404fe56e  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_KVP_REPLICATION_ENABLED@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe575  mov     cs:qword_140D2D138, rax
0x1404fe57c  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_REPLICATION_INTERVAL@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe583  mov     cs:qword_140D2D140, rax
0x1404fe58a  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_REPLICATION_INTERVAL@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe591  mov     cs:qword_140D2D148, rax
0x1404fe598  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_XPATH@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe59f  mov     cs:qword_140D2D150, rax
0x1404fe5a6  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_XPATH@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe5ad  mov     cs:qword_140D2D158, rax
0x1404fe5b4  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_ADDITIONAL_SETTINGS@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe5bb  mov     cs:qword_140D2D160, rax
0x1404fe5c2  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_ADDITIONAL_SETTINGS@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe5c9  mov     cs:qword_140D2D168, rax
0x1404fe5d0  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RESYNC_NODE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe5d7  mov     cs:qword_140D2D170, rax
0x1404fe5de  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RESYNC_NODE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe5e5  mov     cs:qword_140D2D178, rax
0x1404fe5ec  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RESYNC_TRANSFER_ID@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe5f3  mov     cs:qword_140D2D180, rax
0x1404fe5fa  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RESYNC_TRANSFER_ID@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe601  mov     cs:qword_140D2D188, rax
0x1404fe608  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RESYNC_DISKS_SIZE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe60f  mov     cs:qword_140D2D190, rax
0x1404fe616  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RESYNC_DISKS_SIZE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe61d  mov     cs:qword_140D2D198, rax
0x1404fe624  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RESYNC_DISKS_NODE_WMI_INSTANCE_ID_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe62b  mov     cs:qword_140D2D1A0, rax
0x1404fe632  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RESYNC_DISKS_NODE_WMI_INSTANCE_ID_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe639  mov     cs:qword_140D2D1A8, rax
0x1404fe640  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RESYNC_DISKS_NODE_BLOCKS_DONE_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe647  mov     cs:qword_140D2D1B0, rax
0x1404fe64e  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RESYNC_DISKS_NODE_BLOCKS_DONE_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe655  mov     cs:qword_140D2D1B8, rax
0x1404fe65c  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_RESYNC_START_TICKCOUNT64@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe663  mov     cs:qword_140D2D1C0, rax
0x1404fe66a  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_RESYNC_START_TICKCOUNT64@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe671  mov     cs:qword_140D2D1C8, rax
0x1404fe678  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_ENDPOINT_PROVIDER_CLSID@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe67f  mov     cs:qword_140D2D1D0, rax
0x1404fe686  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_ENDPOINT_PROVIDER_CLSID@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe68d  mov     cs:qword_140D2D1D8, rax
0x1404fe694  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_TRACKER_DELTA_TRANSFER_SIZE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe69b  mov     cs:qword_140D2D1E0, rax
0x1404fe6a2  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_TRACKER_DELTA_TRANSFER_SIZE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe6a9  mov     cs:qword_140D2D1E8, rax
0x1404fe6b0  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_TRACKER_DELTA_TRANSFER_NODE_WMI_INSTANCE_ID_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe6b7  mov     cs:qword_140D2D1F0, rax
0x1404fe6be  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_TRACKER_DELTA_TRANSFER_NODE_WMI_INSTANCE_ID_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe6c5  mov     cs:qword_140D2D1F8, rax
0x1404fe6cc  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_TRACKER_DELTA_TRANSFER_NODE_LOG_FILE_PATH_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe6d3  mov     cs:qword_140D2D200, rax
0x1404fe6da  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_TRACKER_DELTA_TRANSFER_NODE_LOG_FILE_PATH_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe6e1  mov     cs:qword_140D2D208, rax
0x1404fe6e8  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_INCLUDED_DISKS_COUNT@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe6ef  mov     cs:qword_140D2D210, rax
0x1404fe6f6  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_INCLUDED_DISKS_COUNT@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe6fd  mov     cs:qword_140D2D218, rax
0x1404fe704  lea     rax, ?VIRTUAL_MACHINE_FAILOVER_REPLICATION_INCLUDED_DISKS_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe70b  mov     cs:qword_140D2D220, rax
0x1404fe712  lea     rax, ?VIRTUAL_MACHINE_EXTENDED_REPLICATION_INCLUDED_DISKS_TEMPLATE@@3QBGB; "/configuration/global_settings/replicat"...
0x1404fe719  mov     cs:qword_140D2D228, rax
0x1404fe720  retn
```
