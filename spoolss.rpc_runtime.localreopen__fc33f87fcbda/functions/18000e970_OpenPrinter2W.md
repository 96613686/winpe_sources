# OpenPrinter2W

- ea: `0x18000e970`
- end: `0x18000e9be`
- name: `OpenPrinter2W`
- size: `78`
- prototype: `BOOL __stdcall(LPCWSTR pPrinterName, LPHANDLE phPrinter, PPRINTER_DEFAULTSW pDefault, PPRINTER_OPTIONSW pOptions)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e970`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e997`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e9aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e9aa`

## string_xrefs

- `0x18000e9a3`: `OpenPrinter2W`

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
0x18000e970  sub     rsp, 38h
0x18000e974  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000e97b  jnz     short loc_18000E992
0x18000e97d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e984  mov     rax, [rax+0E8h]
0x18000e98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e990  jmp     short loc_18000E9B8
0x18000e992  mov     ecx, 32h ; '2'; dwErrCode
0x18000e997  call    cs:__imp_SetLastError
0x18000e99e  nop     dword ptr [rax+rax+00h]
0x18000e9a3  lea     rcx, aOpenprinter2w_0; "OpenPrinter2W"
0x18000e9aa  call    cs:__imp_OutputDebugStringA
0x18000e9b1  nop     dword ptr [rax+rax+00h]
0x18000e9b6  xor     eax, eax
0x18000e9b8  add     rsp, 38h
0x18000e9bc  retn
```
