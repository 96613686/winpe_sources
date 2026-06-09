# CGlobalClusteredStoreManager::DeleteStore(ushort const *,ushort const *)

- ea: `0x1800209ac`
- end: `0x180020aff`
- name: `?DeleteStore@CGlobalClusteredStoreManager@@SAXPEBG0@Z`
- size: `339`
- prototype: `void __fastcall(LPCWSTR lpszSubKey, LPCWSTR)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000f98c`

## callees

- `0x18001e0d0`
- `0x18001e69c`
- `0x18001eb94`
- `0x1800209ac`
- `0x18006febc`
- `0x1800700b8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `CLUSAPI!ClusterRegCloseKey` at `0x180020a9d`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020aac`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020a9d`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020aac`
- `CLUSAPI!CloseCluster` at `0x180020abd`
- `CLUSAPI!CloseCluster` at `0x180020abd`

## string_xrefs

- `0x1800209e0`: `base\fs\fsrm\service\globalstore\globalstoremanagercluster.cpp`
- `0x1800209ec`: `CGlobalClusteredStoreManager::DeleteStore`

## pseudocode

```c

```
