# CGlobalClusteredStoreManager::EnumStoresOnPath(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180020b08`
- end: `0x180020d42`
- name: `?EnumStoresOnPath@CGlobalClusteredStoreManager@@SAXPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `570`
- prototype: `__int64 __fastcall(LPCWSTR lpszSubKey)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18000fb7c`

## callees

- `0x18000266c`
- `0x180010b24`
- `0x18001e338`
- `0x18001e69c`
- `0x18001eb94`
- `0x18001fad8`
- `0x180020b08`
- `0x18006febc`
- `0x1800700b8`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `CLUSAPI!ClusterRegCloseKey` at `0x180020ca9`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020cdd`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020cec`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020ca9`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020cdd`
- `CLUSAPI!ClusterRegCloseKey` at `0x180020cec`
- `CLUSAPI!CloseCluster` at `0x180020cfd`
- `CLUSAPI!CloseCluster` at `0x180020cfd`

## string_xrefs

- `0x180020b3e`: `base\fs\fsrm\service\globalstore\globalstoremanagercluster.cpp`
- `0x180020b4a`: `CGlobalClusteredStoreManager::EnumStoresOnPath`

## pseudocode

```c

```
