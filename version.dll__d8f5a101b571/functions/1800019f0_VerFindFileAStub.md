# VerFindFileAStub

- ea: `0x1800019f0`
- end: `0x180001a2c`
- name: `VerFindFileAStub`
- size: `60`
- prototype: `DWORD __stdcall(DWORD uFlags, LPCSTR szFileName, LPCSTR szWinDir, LPCSTR szAppDir, LPSTR szCurDir, PUINT puCurDirLen, LPSTR szDestDir, PUINT puDestDirLen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-versionansi-l1-1-0!VerFindFileA` at `0x180001a21`
- `api-ms-win-core-versionansi-l1-1-0!VerFindFileA` at `0x180001a21`

## pseudocode

```c
DWORD __stdcall VerFindFileAStub(
        DWORD uFlags,
        LPCSTR szFileName,
        LPCSTR szWinDir,
        LPCSTR szAppDir,
        LPSTR szCurDir,
        PUINT puCurDirLen,
        LPSTR szDestDir,
        PUINT puDestDirLen)
{
  return VerFindFileA(uFlags, szFileName, szWinDir, szAppDir, szCurDir, puCurDirLen, szDestDir, puDestDirLen);
}

```

## disassembly

```asm
0x1800019f0  mov     r11, rsp
0x1800019f3  sub     rsp, 48h
0x1800019f7  mov     rax, [rsp+48h+puDestDirLen]
0x1800019ff  mov     [r11-10h], rax
0x180001a03  mov     rax, [rsp+48h+szDestDir]
0x180001a0b  mov     [r11-18h], rax
0x180001a0f  mov     rax, [rsp+48h+puCurDirLen]
0x180001a14  mov     [r11-20h], rax
0x180001a18  mov     rax, [rsp+48h+szCurDir]
0x180001a1d  mov     [r11-28h], rax
0x180001a21  call    cs:__imp_VerFindFileA
0x180001a27  add     rsp, 48h
0x180001a2b  retn
```
