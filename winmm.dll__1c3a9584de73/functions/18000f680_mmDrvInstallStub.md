# mmDrvInstallStub

- ea: `0x18000f680`
- end: `0x18000f687`
- name: `mmDrvInstallStub`
- size: `7`
- prototype: `UINT __stdcall(HDRVR hDriver, LPCWSTR wszDrvEntry, DRIVERMSGPROC drvMessage, UINT wFlags)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmDrvInstall` at `0x18000f680`

## pseudocode

```c
// attributes: thunk
UINT __stdcall mmDrvInstallStub(HDRVR hDriver, LPCWSTR wszDrvEntry, DRIVERMSGPROC drvMessage, UINT wFlags)
{
  return mmDrvInstall(hDriver, wszDrvEntry, drvMessage, wFlags);
}

```

## disassembly

```asm
0x18000f680  jmp     cs:__imp_mmDrvInstall
```
