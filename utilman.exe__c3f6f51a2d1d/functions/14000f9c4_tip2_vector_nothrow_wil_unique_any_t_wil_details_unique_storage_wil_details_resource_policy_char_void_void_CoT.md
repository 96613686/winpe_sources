# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::clear(void)

- ea: `0x14000f9c4`
- end: `0x14000fa45`
- name: `?clear@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAAXXZ`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000b4a0`
- `0x14000d2b0`

## callees

- `0x14000cfc0`
- `0x14000f9c4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000fa12`
- `KERNEL32!HeapFree` at `0x14000fa12`
- `KERNEL32!GetProcessHeap` at `0x14000f9fe`
- `KERNEL32!GetProcessHeap` at `0x14000f9fe`

## pseudocode

```c

```
