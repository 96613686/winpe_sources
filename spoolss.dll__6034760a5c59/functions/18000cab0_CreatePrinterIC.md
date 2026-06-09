# CreatePrinterIC

- ea: `0x18000cab0`
- end: `0x18000caf3`
- name: `CreatePrinterIC`
- size: `67`
- prototype: `HANDLE __stdcall(HANDLE hPrinter, LPDEVMODEW pDevMode)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cab0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cad9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cad9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cae6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cae6`

## string_xrefs

- `0x18000cadf`: `CreatePrinterIC`

## pseudocode

```c
HANDLE __stdcall CreatePrinterIC(HANDLE hPrinter, LPDEVMODEW pDevMode)
{
  if ( !g_bSandbox )
    return (HANDLE)(*((__int64 (__fastcall **)(HANDLE, LPDEVMODEW))g_pSpoolSvForwards + 99))(hPrinter, pDevMode);
  SetLastError(0x32u);
  OutputDebugStringA("CreatePrinterIC");
  return 0;
}

```

## disassembly

```asm
0x18000cab0  sub     rsp, 28h
0x18000cab4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cabb  jnz     short loc_18000CAD4
0x18000cabd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cac4  mov     rax, [rax+318h]
0x18000cacb  add     rsp, 28h
0x18000cacf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cad4  mov     ecx, 32h ; '2'; dwErrCode
0x18000cad9  call    cs:__imp_SetLastError
0x18000cadf  lea     rcx, aCreateprinteri_0; "CreatePrinterIC"
0x18000cae6  call    cs:__imp_OutputDebugStringA
0x18000caec  xor     eax, eax
0x18000caee  add     rsp, 28h
0x18000caf2  retn
```
