# DeletePrinterDataW

- ea: `0x18000ce40`
- end: `0x18000ce86`
- name: `DeletePrinterDataW`
- size: `70`
- prototype: `DWORD __stdcall(HANDLE hPrinter, LPWSTR pValueName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ce40`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce76`

## string_xrefs

- `0x18000ce6f`: `DeletePrinterDataW`

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
0x18000ce40  sub     rsp, 28h
0x18000ce44  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000ce4b  jnz     short loc_18000CE64
0x18000ce4d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000ce54  mov     rax, [rax+160h]
0x18000ce5b  add     rsp, 28h
0x18000ce5f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce64  mov     ecx, 32h ; '2'; dwErrCode
0x18000ce69  call    cs:__imp_SetLastError
0x18000ce6f  lea     rcx, aDeleteprinterd_4; "DeletePrinterDataW"
0x18000ce76  call    cs:__imp_OutputDebugStringA
0x18000ce7c  mov     eax, 32h ; '2'
0x18000ce81  add     rsp, 28h
0x18000ce85  retn
```
