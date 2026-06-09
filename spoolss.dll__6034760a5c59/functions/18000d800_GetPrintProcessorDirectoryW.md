# GetPrintProcessorDirectoryW

- ea: `0x18000d800`
- end: `0x18000d87b`
- name: `GetPrintProcessorDirectoryW`
- size: `123`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, DWORD Level, LPBYTE pPrintProcessorInfo, DWORD cbBuf, LPDWORD pcbNeeded)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d800`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d86d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d86d`

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
0x18000d800  push    rbx
0x18000d802  sub     rsp, 40h
0x18000d806  xor     ebx, ebx
0x18000d808  mov     r11, rcx
0x18000d80b  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000d811  jnz     short loc_18000D837
0x18000d813  mov     r10, [rsp+48h+pcbNeeded]
0x18000d818  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d81f  mov     [rsp+48h+var_20], r10
0x18000d824  mov     r10d, [rsp+48h+cbBuf]
0x18000d829  mov     [rsp+48h+var_28], r10d
0x18000d82e  mov     rax, [rax+0C0h]
0x18000d835  jmp     short loc_18000D85F
0x18000d837  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000d83e  mov     rax, [rax+0D0h]
0x18000d845  test    rax, rax
0x18000d848  jz      short loc_18000D868
0x18000d84a  mov     rcx, [rsp+48h+pcbNeeded]
0x18000d84f  mov     [rsp+48h+var_20], rcx
0x18000d854  mov     ecx, [rsp+48h+cbBuf]
0x18000d858  mov     [rsp+48h+var_28], ecx
0x18000d85c  mov     rcx, r11
0x18000d85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d864  mov     ebx, eax
0x18000d866  jmp     short loc_18000D873
0x18000d868  mov     ecx, 7Fh; dwErrCode
0x18000d86d  call    cs:__imp_SetLastError
0x18000d873  mov     eax, ebx
0x18000d875  add     rsp, 40h
0x18000d879  pop     rbx
0x18000d87a  retn
```
