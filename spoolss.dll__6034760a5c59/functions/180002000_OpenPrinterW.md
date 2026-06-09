# OpenPrinterW

- ea: `0x180002000`
- end: `0x18000205d`
- name: `OpenPrinterW`
- size: `93`
- prototype: `BOOL __stdcall(LPWSTR pPrinterName, LPHANDLE phPrinter, LPPRINTER_DEFAULTSW pDefault)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011050`

## callees

- `0x180002000`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000204e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000204e`

## pseudocode

```c
BOOL __stdcall OpenPrinterW(LPWSTR pPrinterName, LPHANDLE phPrinter, LPPRINTER_DEFAULTSW pDefault)
{
  __int64 (__fastcall *v4)(LPWSTR, LPHANDLE, LPPRINTER_DEFAULTSW); // rax
  BOOL v5; // ebx

  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPHANDLE, LPPRINTER_DEFAULTSW))g_pSpoolSvForwards + 27))(
             pPrinterName,
             phPrinter,
             pDefault);
  v4 = (__int64 (__fastcall *)(LPWSTR, LPHANDLE, LPPRINTER_DEFAULTSW))*((_QWORD *)g_pWinSpoolForwards + 3);
  if ( v4 )
    return v4(pPrinterName, phPrinter, pDefault);
  v5 = 0;
  SetLastError(0x7Fu);
  return v5;
}

```

## disassembly

```asm
0x180002000  sub     rsp, 28h
0x180002004  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000200b  jnz     short loc_180002029
0x18000200d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002014  mov     rax, [rax+0D8h]
0x18000201b  add     rsp, 28h
0x18000201f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002024  add     rsp, 28h
0x180002028  retn
0x180002029  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x180002030  mov     [rsp+28h+var_8], rbx
0x180002035  mov     rax, [rax+18h]
0x180002039  test    rax, rax
0x18000203c  jz      short loc_180002047
0x18000203e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002043  mov     ebx, eax
0x180002045  jmp     short loc_180002054
0x180002047  xor     ebx, ebx
0x180002049  mov     ecx, 7Fh; dwErrCode
0x18000204e  call    cs:__imp_SetLastError
0x180002054  mov     eax, ebx
0x180002056  mov     rbx, [rsp+28h+var_8]
0x18000205b  jmp     short loc_180002024
```
