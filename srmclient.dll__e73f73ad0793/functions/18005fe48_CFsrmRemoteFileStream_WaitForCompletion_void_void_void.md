# CFsrmRemoteFileStream::WaitForCompletion(void *,void *,void *)

- ea: `0x18005fe48`
- end: `0x180060020`
- name: `?WaitForCompletion@CFsrmRemoteFileStream@@CAXPEAX00@Z`
- size: `472`
- prototype: `static void(void *, void *, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005f0e0`
- `0x1800600b0`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18005fe48`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18005fef4`
- `KERNEL32!WaitForSingleObject` at `0x18005ffb3`
- `KERNEL32!WaitForSingleObject` at `0x18005fef4`
- `KERNEL32!WaitForSingleObject` at `0x18005ffb3`
- `KERNEL32!WaitForMultipleObjects` at `0x18005ff5d`
- `KERNEL32!WaitForMultipleObjects` at `0x18005ff5d`

## string_xrefs

- `0x18005fe83`: `base\fs\fsrm\service\inc\streamlib.h`
- `0x18005fe8f`: `CFsrmRemoteFileStream::WaitForCompletion`

## pseudocode

```c

```
