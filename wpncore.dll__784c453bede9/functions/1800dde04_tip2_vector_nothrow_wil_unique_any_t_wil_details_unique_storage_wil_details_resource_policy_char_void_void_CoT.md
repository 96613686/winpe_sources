# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(unsigned __int64)

- ea: `0x1800dde04`
- end: `0x1800dde9e`
- name: `?reserve@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N_K@Z`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800da94c`

## callees

- `0x18001bf30`
- `0x1800dde04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dde30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800dde30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dde22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dde77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dde22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800dde77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dde85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800dde85`

## pseudocode

```c

```
