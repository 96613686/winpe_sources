# OpenPrinter2W

- ea: `0x18000dc10`
- end: `0x18000dc51`
- name: `OpenPrinter2W`
- size: `65`
- prototype: `BOOL __stdcall(LPCWSTR pPrinterName, LPHANDLE phPrinter, PPRINTER_DEFAULTSW pDefault, PPRINTER_OPTIONSW pOptions)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dc10`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc37`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dc44`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dc44`

## string_xrefs

- `0x18000dc3d`: `OpenPrinter2W`

## pseudocode

```c
BOOL __stdcall OpenPrinter2W(
        LPCWSTR pPrinterName,
        LPHANDLE phPrinter,
        PPRINTER_DEFAULTSW pDefault,
        PPRINTER_OPTIONSW pOptions)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPCWSTR, LPHANDLE, PPRINTER_DEFAULTSW, PPRINTER_OPTIONSW))g_pSpoolSvForwards + 29))(
             pPrinterName,
             phPrinter,
             pDefault,
             pOptions);
  SetLastError(0x32u);
  OutputDebugStringA("OpenPrinter2W");
  return 0;
}

```

## disassembly

```asm
0x18000dc10  sub     rsp, 38h
0x18000dc14  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000dc1b  jnz     short loc_18000DC32
0x18000dc1d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000dc24  mov     rax, [rax+0E8h]
0x18000dc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc30  jmp     short loc_18000DC4C
0x18000dc32  mov     ecx, 32h ; '2'; dwErrCode
0x18000dc37  call    cs:__imp_SetLastError
0x18000dc3d  lea     rcx, aOpenprinter2w_0; "OpenPrinter2W"
0x18000dc44  call    cs:__imp_OutputDebugStringA
0x18000dc4a  xor     eax, eax
0x18000dc4c  add     rsp, 38h
0x18000dc50  retn
```
