# GetPrinterDriverDirectoryW

- ea: `0x18000d890`
- end: `0x18000d90d`
- name: `GetPrinterDriverDirectoryW`
- size: `125`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, DWORD Level, LPBYTE pDriverDirectory, DWORD cbBuf, LPDWORD pcbNeeded)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d890`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d8ff`

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
0x18000d890  push    rbx
0x18000d892  sub     rsp, 40h
0x18000d896  xor     ebx, ebx
0x18000d898  mov     r11, rcx
0x18000d89b  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000d8a1  jnz     short loc_18000D8C9
0x18000d8a3  mov     r10, [rsp+48h+pcbNeeded]
0x18000d8a8  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d8af  mov     [rsp+48h+var_20], r10
0x18000d8b4  mov     r10d, [rsp+48h+cbBuf]
0x18000d8b9  mov     [rsp+48h+var_28], r10d
0x18000d8be  mov     rax, [rax+68h]
0x18000d8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c7  jmp     short loc_18000D907
0x18000d8c9  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000d8d0  mov     rax, [rax+0C8h]
0x18000d8d7  test    rax, rax
0x18000d8da  jz      short loc_18000D8FA
0x18000d8dc  mov     rcx, [rsp+48h+pcbNeeded]
0x18000d8e1  mov     [rsp+48h+var_20], rcx
0x18000d8e6  mov     ecx, [rsp+48h+cbBuf]
0x18000d8ea  mov     [rsp+48h+var_28], ecx
0x18000d8ee  mov     rcx, r11
0x18000d8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8f6  mov     ebx, eax
0x18000d8f8  jmp     short loc_18000D905
0x18000d8fa  mov     ecx, 7Fh; dwErrCode
0x18000d8ff  call    cs:__imp_SetLastError
0x18000d905  mov     eax, ebx
0x18000d907  add     rsp, 40h
0x18000d90b  pop     rbx
0x18000d90c  retn
```
