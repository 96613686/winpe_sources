# WritePrinter

- ea: `0x180003210`
- end: `0x180003261`
- name: `WritePrinter`
- size: `81`
- prototype: `BOOL __stdcall(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pcWritten)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003210`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003253`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003253`

## pseudocode

```c
BOOL __stdcall WritePrinter(HANDLE hPrinter, LPVOID pBuf, DWORD cbBuf, LPDWORD pcWritten)
{
  BOOL v4; // ebx
  __int64 (__fastcall *v6)(HANDLE, LPVOID, DWORD, LPDWORD); // rax

  v4 = 0;
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, LPVOID, DWORD, LPDWORD))g_pSpoolSvForwards + 35))(
             hPrinter,
             pBuf,
             cbBuf,
             pcWritten);
  v6 = (__int64 (__fastcall *)(HANDLE, LPVOID, DWORD, LPDWORD))*((_QWORD *)g_pWinSpoolForwards + 6);
  if ( v6 )
    return v6(hPrinter, pBuf, cbBuf, pcWritten);
  SetLastError(0x7Fu);
  return v4;
}

```

## disassembly

```asm
0x180003210  push    rbx
0x180003212  sub     rsp, 30h
0x180003216  xor     ebx, ebx
0x180003218  cmp     cs:?g_bSandbox@@3_NA, bl; bool g_bSandbox
0x18000321e  jnz     short loc_180003235
0x180003220  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180003227  mov     rax, [rax+118h]
0x18000322e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003233  jmp     short loc_18000325B
0x180003235  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x18000323c  mov     rax, [rax+30h]
0x180003240  test    rax, rax
0x180003243  jz      short loc_18000324E
0x180003245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000324a  mov     ebx, eax
0x18000324c  jmp     short loc_180003259
0x18000324e  mov     ecx, 7Fh; dwErrCode
0x180003253  call    cs:__imp_SetLastError
0x180003259  mov     eax, ebx
0x18000325b  add     rsp, 30h
0x18000325f  pop     rbx
0x180003260  retn
```
