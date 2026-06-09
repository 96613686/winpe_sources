# CGlobalClusteredStoreManager::GetStoreData(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180020d48`
- end: `0x180020f7c`
- name: `?GetStoreData@CGlobalClusteredStoreManager@@SAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(LPCWSTR lpszSubKey, LPCWSTR, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18000fd74`

## callees

- `0x180001350`
- `0x180010b24`
- `0x180010bc4`
- `0x18001e69c`
- `0x18001eb94`
- `0x18001f254`
- `0x180020d48`
- `0x18006febc`
- `0x1800700b8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `CLUSAPI!ClusterRegCloseKey` at `0x180020f0d`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020f1c`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020f2b`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020f0d`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020f1c`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020f2b`
- `CLUSAPI!CloseCluster` at `0x180020f3c`
- `CLUSAPI!CloseCluster` at `0x180020f3c`

## string_xrefs

- `0x180020e3a`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x180020d7d`: `base\fs\fsrm\service\globalstore\globalstoremanagercluster.cpp`

## pseudocode

```c

```
