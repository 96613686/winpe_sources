# CErcLuaDownloadAndInstall::static_DownloadAndInstallThread(void *)

- ea: `0x180006c30`
- end: `0x180006c35`
- name: `?static_DownloadAndInstallThread@CErcLuaDownloadAndInstall@@CAKPEAX@Z`
- size: `5`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800031bc`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CErcLuaDownloadAndInstall::static_DownloadAndInstallThread(CErcLuaDownloadAndInstall *Parameter)
{
  return CErcLuaDownloadAndInstall::DownloadAndInstallThread(Parameter);
}

```

## disassembly

```asm
0x180006c30  jmp     ?DownloadAndInstallThread@CErcLuaDownloadAndInstall@@AEAAKXZ; CErcLuaDownloadAndInstall::DownloadAndInstallThread(void)
```
