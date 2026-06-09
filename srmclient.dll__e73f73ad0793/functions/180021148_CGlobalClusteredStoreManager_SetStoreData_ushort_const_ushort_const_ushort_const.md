# CGlobalClusteredStoreManager::SetStoreData(ushort const *,ushort const *,ushort const *)

- ea: `0x180021148`
- end: `0x180021364`
- name: `?SetStoreData@CGlobalClusteredStoreManager@@SAXPEBG00@Z`
- size: `540`
- prototype: `void __fastcall(LPCWSTR lpszSubKey, LPCWSTR, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800106e0`

## callees

- `0x180010bc4`
- `0x18001e69c`
- `0x18001eb94`
- `0x180020150`
- `0x1800202b8`
- `0x180021148`
- `0x18006febc`
- `0x1800700b8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `CLUSAPI!ClusterRegCloseKey` at `0x1800212f5`
- `CLUSAPI!ClusterRegCloseKey` at `0x180021304`
- `CLUSAPI!ClusterRegCloseKey` at `0x180021313`
- `CLUSAPI!ClusterRegCloseKey` at `0x1800212f5`
- `CLUSAPI!ClusterRegCloseKey` at `0x180021304`
- `CLUSAPI!ClusterRegCloseKey` at `0x180021313`
- `CLUSAPI!CloseCluster` at `0x180021324`
- `CLUSAPI!CloseCluster` at `0x180021324`

## string_xrefs

- `0x18002123a`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18002117d`: `base\fs\fsrm\service\globalstore\globalstoremanagercluster.cpp`

## pseudocode

```c

```
