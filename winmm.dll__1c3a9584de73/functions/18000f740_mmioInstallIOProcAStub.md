# mmioInstallIOProcAStub

- ea: `0x18000f740`
- end: `0x18000f747`
- name: `mmioInstallIOProcAStub`
- size: `7`
- prototype: `LPMMIOPROC __stdcall(FOURCC fccIOProc, LPMMIOPROC pIOProc, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!mmioInstallIOProcA` at `0x18000f740`

## pseudocode

```c
// attributes: thunk
LPMMIOPROC __stdcall mmioInstallIOProcAStub(FOURCC fccIOProc, LPMMIOPROC pIOProc, DWORD dwFlags)
{
  return mmioInstallIOProcA(fccIOProc, pIOProc, dwFlags);
}

```

## disassembly

```asm
0x18000f740  jmp     cs:__imp_mmioInstallIOProcA
```
