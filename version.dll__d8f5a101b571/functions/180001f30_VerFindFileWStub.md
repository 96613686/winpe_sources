# VerFindFileWStub

- ea: `0x180001f30`
- end: `0x180001f6c`
- name: `VerFindFileWStub`
- size: `60`
- prototype: `DWORD __stdcall(DWORD uFlags, LPCWSTR szFileName, LPCWSTR szWinDir, LPCWSTR szAppDir, LPWSTR szCurDir, PUINT puCurDirLen, LPWSTR szDestDir, PUINT puDestDirLen)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerFindFileW` at `0x180001f61`
- `api-ms-win-core-version-l1-1-0!VerFindFileW` at `0x180001f61`

## pseudocode

```c
DWORD __stdcall VerFindFileWStub(
        DWORD uFlags,
        LPCWSTR szFileName,
        LPCWSTR szWinDir,
        LPCWSTR szAppDir,
        LPWSTR szCurDir,
        PUINT puCurDirLen,
        LPWSTR szDestDir,
        PUINT puDestDirLen)
{
  return VerFindFileW(uFlags, szFileName, szWinDir, szAppDir, szCurDir, puCurDirLen, szDestDir, puDestDirLen);
}

```

## disassembly

```asm
0x180001f30  mov     r11, rsp
0x180001f33  sub     rsp, 48h
0x180001f37  mov     rax, [rsp+48h+puDestDirLen]
0x180001f3f  mov     [r11-10h], rax
0x180001f43  mov     rax, [rsp+48h+szDestDir]
0x180001f4b  mov     [r11-18h], rax
0x180001f4f  mov     rax, [rsp+48h+puCurDirLen]
0x180001f54  mov     [r11-20h], rax
0x180001f58  mov     rax, [rsp+48h+szCurDir]
0x180001f5d  mov     [r11-28h], rax
0x180001f61  call    cs:__imp_VerFindFileW
0x180001f67  add     rsp, 48h
0x180001f6b  retn
```
