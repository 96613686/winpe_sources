# DeletePrinterDataW

- ea: `0x18000da10`
- end: `0x18000da63`
- name: `DeletePrinterDataW`
- size: `83`
- prototype: `DWORD __stdcall(HANDLE hPrinter, LPWSTR pValueName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000da10`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000da39`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000da4c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000da4c`

## string_xrefs

- `0x18000da45`: `DeletePrinterDataW`

## pseudocode

```c
DWORD __stdcall DeletePrinterDataW(HANDLE hPrinter, LPWSTR pValueName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, LPWSTR))g_pSpoolSvForwards + 44))(hPrinter, pValueName);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterDataW");
  return 50;
}

```

## disassembly

```asm
0x18000da10  sub     rsp, 28h
0x18000da14  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000da1b  jnz     short loc_18000DA34
0x18000da1d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000da24  mov     rax, [rax+160h]
0x18000da2b  add     rsp, 28h
0x18000da2f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000da34  mov     ecx, 32h ; '2'; dwErrCode
0x18000da39  call    cs:__imp_SetLastError
0x18000da40  nop     dword ptr [rax+rax+00h]
0x18000da45  lea     rcx, aDeleteprinterd_4; "DeletePrinterDataW"
0x18000da4c  call    cs:__imp_OutputDebugStringA
0x18000da53  nop     dword ptr [rax+rax+00h]
0x18000da58  mov     eax, 32h ; '2'
0x18000da5d  add     rsp, 28h
0x18000da61  retn
```
