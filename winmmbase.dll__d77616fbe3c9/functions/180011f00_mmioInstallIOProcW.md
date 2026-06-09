# mmioInstallIOProcW

- ea: `0x180011f00`
- end: `0x180011f16`
- name: `mmioInstallIOProcW`
- size: `22`
- prototype: `LPMMIOPROC __stdcall(FOURCC fccIOProc, LPMMIOPROC pIOProc, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180011c1c`
- `0x180011f00`

## pseudocode

```c
LPMMIOPROC __stdcall mmioInstallIOProcW(FOURCC fccIOProc, LPMMIOPROC pIOProc, DWORD dwFlags)
{
  if ( (dwFlags & 0xEFF8FFFF) != 0 )
    return 0;
  else
    return (LPMMIOPROC)mmioInternalInstallIOProc(fccIOProc, (__int64)pIOProc, dwFlags | 0x1000000);
}

```

## disassembly

```asm
0x180011f00  test    r8d, 0EFF8FFFFh
0x180011f07  jz      short loc_180011F0C
0x180011f09  xor     eax, eax
0x180011f0b  retn
0x180011f0c  bts     r8d, 18h
0x180011f11  jmp     mmioInternalInstallIOProc
```
