# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(unsigned __int64)

- ea: `0x14001156c`
- end: `0x140011623`
- name: `?reserve@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N_K@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000b4a0`

## callees

- `0x14000cfc0`
- `0x14001156c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140011603`
- `KERNEL32!HeapFree` at `0x140011603`
- `KERNEL32!HeapAlloc` at `0x1400115a2`
- `KERNEL32!HeapAlloc` at `0x1400115a2`
- `KERNEL32!GetProcessHeap` at `0x14001158e`
- `KERNEL32!GetProcessHeap` at `0x1400115ef`
- `KERNEL32!GetProcessHeap` at `0x14001158e`
- `KERNEL32!GetProcessHeap` at `0x1400115ef`

## pseudocode

```c

```
