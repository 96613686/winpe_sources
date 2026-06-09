# CClusterSupport::GetOwnerNode(wchar_t const *,wchar_t * *)

- ea: `0x1802331fc`
- end: `0x1802333c0`
- name: `?GetOwnerNode@CClusterSupport@@AEBAJPEB_WPEAPEA_W@Z`
- size: `452`
- prototype: `int(CClusterSupport *__hidden this, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180233044`

## callees

- `0x18000def4`
- `0x1800d9a70`
- `0x180113ae8`
- `0x180113b9c`
- `0x1802331fc`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802332d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802332d2`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180233254`
- `api-ms-win-core-apiquery-l2-1-0!IsApiSetImplemented` at `0x180233254`
- `CLUSAPI!GetClusterResourceState` at `0x1802332c7`
- `CLUSAPI!GetClusterResourceState` at `0x180233330`
- `CLUSAPI!GetClusterResourceState` at `0x1802332c7`
- `CLUSAPI!GetClusterResourceState` at `0x180233330`
- `CLUSAPI!OpenClusterResource` at `0x18023328d`
- `CLUSAPI!OpenClusterResource` at `0x18023328d`
- `CLUSAPI!OpenCluster` at `0x18023326f`
- `CLUSAPI!OpenCluster` at `0x18023326f`
- `CLUSAPI!CloseCluster` at `0x18023338b`
- `CLUSAPI!CloseCluster` at `0x18023338b`
- `CLUSAPI!CloseClusterResource` at `0x180233368`
- `CLUSAPI!CloseClusterResource` at `0x180233368`

## string_xrefs

- `0x18023334a`: `C:\__w\1\s\src\Client\Engine\Agent\ClusterSupport.cpp`
- `0x180233377`: `C:\__w\1\s\src\Client\Engine\Agent\ClusterSupport.cpp`

## pseudocode

```c

```
