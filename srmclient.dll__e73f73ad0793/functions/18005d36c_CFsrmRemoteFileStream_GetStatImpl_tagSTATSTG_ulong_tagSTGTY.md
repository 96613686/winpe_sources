# CFsrmRemoteFileStream::GetStatImpl(tagSTATSTG *,ulong,tagSTGTY)

- ea: `0x18005d36c`
- end: `0x18005d6f4`
- name: `?GetStatImpl@CFsrmRemoteFileStream@@AEAAJPEAUtagSTATSTG@@KW4tagSTGTY@@@Z`
- size: `904`
- prototype: `int(CFsrmRemoteFileStream *__hidden this, struct tagSTATSTG *, unsigned int, enum tagSTGTY)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18005fbe0`

## callees

- `0x180002520`
- `0x180006a1c`
- `0x1800095f4`
- `0x18005d36c`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18005d4a6`
- `KERNEL32!WaitForSingleObject` at `0x18005d4a6`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18005d4e3`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18005d51b`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18005d4e3`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18005d51b`

## string_xrefs

- `0x18005d39b`: `base\fs\fsrm\service\stream\streamlib.cpp`

## pseudocode

```c

```
