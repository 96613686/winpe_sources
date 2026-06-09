# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x1400248cc`
- end: `0x140024951`
- name: `?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z`
- size: `133`
- prototype: `void __fastcall(void **, void **)`
- caller_count: `10`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140020df0`
- `0x140024958`
- `0x140029c80`
- `0x14002acfc`
- `0x14002b138`
- `0x14002c36c`
- `0x14002c970`
- `0x14002ce68`
- `0x14002d278`
- `0x14002e134`

## callees

- `0x1400248cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140024906`
- `KERNEL32!GetLastError` at `0x140024906`
- `KERNEL32!GetProcessHeap` at `0x14002490e`
- `KERNEL32!GetProcessHeap` at `0x140024934`
- `KERNEL32!GetProcessHeap` at `0x14002490e`
- `KERNEL32!GetProcessHeap` at `0x140024934`
- `KERNEL32!SetLastError` at `0x140024924`
- `KERNEL32!SetLastError` at `0x140024924`
- `KERNEL32!HeapFree` at `0x14002491c`
- `KERNEL32!HeapFree` at `0x140024942`
- `KERNEL32!HeapFree` at `0x14002491c`
- `KERNEL32!HeapFree` at `0x140024942`

## pseudocode

```c

```
