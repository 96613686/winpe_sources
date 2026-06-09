# OpenPrinterW

- ea: `0x1800020c0`
- end: `0x180002124`
- name: `OpenPrinterW`
- size: `100`
- prototype: `BOOL __stdcall(LPWSTR pPrinterName, LPHANDLE phPrinter, LPPRINTER_DEFAULTSW pDefault)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800126a0`

## callees

- `0x1800020c0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000210f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000210f`

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
0x1800020c0  sub     rsp, 28h
0x1800020c4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800020cb  jnz     short loc_1800020EA
0x1800020cd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800020d4  mov     rax, [rax+0D8h]
0x1800020db  add     rsp, 28h
0x1800020df  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e4  add     rsp, 28h
0x1800020e8  retn
0x1800020ea  mov     rax, cs:?g_pWinSpoolForwards@@3PEAU_ForwardedWinSpoolFunctions@@EA; _ForwardedWinSpoolFunctions * g_pWinSpoolForwards
0x1800020f1  mov     [rsp+28h+var_8], rbx
0x1800020f6  mov     rax, [rax+18h]
0x1800020fa  test    rax, rax
0x1800020fd  jz      short loc_180002108
0x1800020ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002104  mov     ebx, eax
0x180002106  jmp     short loc_18000211B
0x180002108  xor     ebx, ebx
0x18000210a  mov     ecx, 7Fh; dwErrCode
0x18000210f  call    cs:__imp_SetLastError
0x180002116  nop     dword ptr [rax+rax+00h]
0x18000211b  mov     eax, ebx
0x18000211d  mov     rbx, [rsp+28h+var_8]
0x180002122  jmp     short loc_1800020E4
```
