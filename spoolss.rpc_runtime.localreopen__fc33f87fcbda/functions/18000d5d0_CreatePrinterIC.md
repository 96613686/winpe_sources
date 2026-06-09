# CreatePrinterIC

- ea: `0x18000d5d0`
- end: `0x18000d620`
- name: `CreatePrinterIC`
- size: `80`
- prototype: `HANDLE __stdcall(HANDLE hPrinter, LPDEVMODEW pDevMode)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d5d0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5f9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d60c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d60c`

## string_xrefs

- `0x18000d605`: `CreatePrinterIC`

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
0x18000d5d0  sub     rsp, 28h
0x18000d5d4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d5db  jnz     short loc_18000D5F4
0x18000d5dd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d5e4  mov     rax, [rax+318h]
0x18000d5eb  add     rsp, 28h
0x18000d5ef  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f4  mov     ecx, 32h ; '2'; dwErrCode
0x18000d5f9  call    cs:__imp_SetLastError
0x18000d600  nop     dword ptr [rax+rax+00h]
0x18000d605  lea     rcx, aCreateprinteri_0; "CreatePrinterIC"
0x18000d60c  call    cs:__imp_OutputDebugStringA
0x18000d613  nop     dword ptr [rax+rax+00h]
0x18000d618  xor     eax, eax
0x18000d61a  add     rsp, 28h
0x18000d61e  retn
```
