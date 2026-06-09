# ServerXMLUpdateHandler::WritePrincipal(Schema const &,bool,ushort const *,ushort const *,_TASK_LOGON_TYPE,bool,bool)

- ea: `0x180034210`
- end: `0x180034594`
- name: `?WritePrincipal@ServerXMLUpdateHandler@@AEAAXAEBUSchema@@_NPEBG2W4_TASK_LOGON_TYPE@@11@Z`
- size: `900`
- prototype: `void __usercall(ServerXMLUpdateHandler *__hidden this@<rcx>, const struct Schema *@<rdx>, bool@<r8b>, const unsigned __int16 *@<r9>, const unsigned __int16 *, enum _TASK_LOGON_TYPE, bool, bool)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180049bd0`
- `0x18007e21c`

## callees

- `0x180012180`
- `0x180016680`
- `0x180016df0`
- `0x18001a260`
- `0x180034210`
- `0x1800346c0`
- `0x1800346e0`
- `0x180034728`
- `0x1800347e0`
- `0x18004e4fc`
- `0x18005236c`
- `0x180054330`
- `0x180054700`
- `0x18007dfcc`
- `0x18007e5b0`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800343b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800343b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003448d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003448d`

## pseudocode

```c

```
