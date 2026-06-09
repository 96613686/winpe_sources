# mmioInstallIOProcWStub

- ea: `0x18000f750`
- end: `0x18000f757`
- name: `mmioInstallIOProcWStub`
- size: `7`
- prototype: `LPMMIOPROC __stdcall(FOURCC fccIOProc, LPMMIOPROC pIOProc, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioInstallIOProcW` at `0x18000f750`

## pseudocode

```c
// attributes: thunk
LPMMIOPROC __stdcall mmioInstallIOProcWStub(FOURCC fccIOProc, LPMMIOPROC pIOProc, DWORD dwFlags)
{
  return mmioInstallIOProcW(fccIOProc, pIOProc, dwFlags);
}

```

## disassembly

```asm
0x18000f750  jmp     cs:__imp_mmioInstallIOProcW
```
