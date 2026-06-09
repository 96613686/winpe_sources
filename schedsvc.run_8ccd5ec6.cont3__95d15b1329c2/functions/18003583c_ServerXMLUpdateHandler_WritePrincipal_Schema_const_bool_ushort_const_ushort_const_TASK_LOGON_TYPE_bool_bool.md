# ServerXMLUpdateHandler::WritePrincipal(Schema const &,bool,ushort const *,ushort const *,_TASK_LOGON_TYPE,bool,bool)

- ea: `0x18003583c`
- end: `0x180035bcd`
- name: `?WritePrincipal@ServerXMLUpdateHandler@@AEAAXAEBUSchema@@_NPEBG2W4_TASK_LOGON_TYPE@@11@Z`
- size: `913`
- prototype: `void __usercall(ServerXMLUpdateHandler *__hidden this@<rcx>, const struct Schema *@<rdx>, bool@<r8b>, const unsigned __int16 *@<r9>, const unsigned __int16 *, enum _TASK_LOGON_TYPE, bool, bool)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18004be50`
- `0x18008255c`

## callees

- `0x180006850`
- `0x18000cc40`
- `0x18002fa10`
- `0x180030930`
- `0x18003583c`
- `0x180035cf8`
- `0x180035d20`
- `0x180035d70`
- `0x180035e30`
- `0x180050908`
- `0x1800549cc`
- `0x180056c00`
- `0x180056fe0`
- `0x18008230c`
- `0x180082910`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800359df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800359df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035abf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035abf`

## pseudocode

```c

```
