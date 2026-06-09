# GetPrintProcessorDirectoryW

- ea: `0x18000e510`
- end: `0x18000e592`
- name: `GetPrintProcessorDirectoryW`
- size: `130`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, DWORD Level, LPBYTE pPrintProcessorInfo, DWORD cbBuf, LPDWORD pcbNeeded)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e510`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e57d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e57d`

## pseudocode

```c
BOOL __stdcall GetPrintProcessorDirectoryW(
        LPWSTR pName,
        LPWSTR pEnvironment,
        DWORD Level,
        LPBYTE pPrintProcessorInfo,
        DWORD cbBuf,
        LPDWORD pcbNeeded)
{
  BOOL v6; // ebx
  __int64 (__fastcall *v8)(LPWSTR, LPWSTR, DWORD, LPBYTE, DWORD, LPDWORD); // rax

  v6 = 0;
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPWSTR, DWORD, LPBYTE, DWORD, LPDWORD))g_pSpoolSvForwards + 24))(
             pName,
             pEnvironment,
             Level,
             pPrintProcessorInfo,
             cbBuf,
             pcbNeeded);
  v8 = (__int64 (__fastcall *)(LPWSTR, LPWSTR, DWORD, LPBYTE, DWORD, LPDWORD))*((_QWORD *)g_pWinSpoolForwards + 26);
  if ( !v8 )
  {
    SetLastError(0x7Fu);
    return v6;
  }
  return v8(pName, pEnvironment, Level, pPrintProcessorInfo, cbBuf, pcbNeeded);
}

```

## disassembly

```asm
0x18000e510  push    rbx
0x18000e512  sub     rsp, 40h
0x18000e516  xor     ebx, ebx
0x18000e518  mov     r11, rcx
0x18000e51b  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000e521  jnz     short loc_18000E547
0x18000e523  mov     r10, [rsp+48h+pcbNeeded]
0x18000e528  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e52f  mov     [rsp+48h+var_20], r10
0x18000e534  mov     r10d, [rsp+48h+cbBuf]
0x18000e539  mov     [rsp+48h+var_28], r10d
0x18000e53e  mov     rax, [rax+0C0h]
0x18000e545  jmp     short loc_18000E56F
0x18000e547  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000e54e  mov     rax, [rax+0D0h]
0x18000e555  test    rax, rax
0x18000e558  jz      short loc_18000E578
0x18000e55a  mov     rcx, [rsp+48h+pcbNeeded]
0x18000e55f  mov     [rsp+48h+var_20], rcx
0x18000e564  mov     ecx, [rsp+48h+cbBuf]
0x18000e568  mov     [rsp+48h+var_28], ecx
0x18000e56c  mov     rcx, r11
0x18000e56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e574  mov     ebx, eax
0x18000e576  jmp     short loc_18000E589
0x18000e578  mov     ecx, 7Fh; dwErrCode
0x18000e57d  call    cs:__imp_SetLastError
0x18000e584  nop     dword ptr [rax+rax+00h]
0x18000e589  mov     eax, ebx
0x18000e58b  add     rsp, 40h
0x18000e58f  pop     rbx
0x18000e590  retn
```
