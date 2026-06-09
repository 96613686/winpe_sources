# Windows::CoreOS::Reboot::WaitForMigration(void)

- ea: `0x180057b90`
- end: `0x180057e57`
- name: `?WaitForMigration@Reboot@CoreOS@Windows@@EEAAXXZ`
- size: `711`
- prototype: `void __fastcall(Windows::CoreOS::Reboot *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006a08`
- `0x180007660`
- `0x180013ccc`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800209fc`
- `0x18002765c`
- `0x18003b360`
- `0x18004610c`
- `0x18005765c`
- `0x180057b90`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180057dce`
- `msvcp_win!_Mtx_unlock` at `0x180057dce`
- `msvcp_win!_Mtx_lock` at `0x180057cd5`
- `msvcp_win!_Mtx_lock` at `0x180057cd5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180057ce4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180057d00`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180057ce4`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180057d00`

## string_xrefs

- `0x180057da2`: `Migration completed.`
- `0x180057e45`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\coreos.cpp`

## pseudocode

```c

```
