# GetPrinterDriverDirectoryW

- ea: `0x18000e5a0`
- end: `0x18000e624`
- name: `GetPrinterDriverDirectoryW`
- size: `132`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, DWORD Level, LPBYTE pDriverDirectory, DWORD cbBuf, LPDWORD pcbNeeded)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e5a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e60f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e60f`

## pseudocode

```c
BOOL __stdcall GetPrinterDriverDirectoryW(
        LPWSTR pName,
        LPWSTR pEnvironment,
        DWORD Level,
        LPBYTE pDriverDirectory,
        DWORD cbBuf,
        LPDWORD pcbNeeded)
{
  BOOL v6; // ebx
  __int64 (__fastcall *v8)(LPWSTR, LPWSTR, DWORD, LPBYTE, DWORD, LPDWORD); // rax

  v6 = 0;
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPWSTR, DWORD, LPBYTE, DWORD, LPDWORD))g_pSpoolSvForwards + 13))(
             pName,
             pEnvironment,
             Level,
             pDriverDirectory,
             cbBuf,
             pcbNeeded);
  v8 = (__int64 (__fastcall *)(LPWSTR, LPWSTR, DWORD, LPBYTE, DWORD, LPDWORD))*((_QWORD *)g_pWinSpoolForwards + 25);
  if ( v8 )
    return v8(pName, pEnvironment, Level, pDriverDirectory, cbBuf, pcbNeeded);
  SetLastError(0x7Fu);
  return v6;
}

```

## disassembly

```asm
0x18000e5a0  push    rbx
0x18000e5a2  sub     rsp, 40h
0x18000e5a6  xor     ebx, ebx
0x18000e5a8  mov     r11, rcx
0x18000e5ab  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000e5b1  jnz     short loc_18000E5D9
0x18000e5b3  mov     r10, [rsp+48h+pcbNeeded]
0x18000e5b8  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e5bf  mov     [rsp+48h+var_20], r10
0x18000e5c4  mov     r10d, [rsp+48h+cbBuf]
0x18000e5c9  mov     [rsp+48h+var_28], r10d
0x18000e5ce  mov     rax, [rax+68h]
0x18000e5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5d7  jmp     short loc_18000E61D
0x18000e5d9  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000e5e0  mov     rax, [rax+0C8h]
0x18000e5e7  test    rax, rax
0x18000e5ea  jz      short loc_18000E60A
0x18000e5ec  mov     rcx, [rsp+48h+pcbNeeded]
0x18000e5f1  mov     [rsp+48h+var_20], rcx
0x18000e5f6  mov     ecx, [rsp+48h+cbBuf]
0x18000e5fa  mov     [rsp+48h+var_28], ecx
0x18000e5fe  mov     rcx, r11
0x18000e601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e606  mov     ebx, eax
0x18000e608  jmp     short loc_18000E61B
0x18000e60a  mov     ecx, 7Fh; dwErrCode
0x18000e60f  call    cs:__imp_SetLastError
0x18000e616  nop     dword ptr [rax+rax+00h]
0x18000e61b  mov     eax, ebx
0x18000e61d  add     rsp, 40h
0x18000e621  pop     rbx
0x18000e622  retn
```
