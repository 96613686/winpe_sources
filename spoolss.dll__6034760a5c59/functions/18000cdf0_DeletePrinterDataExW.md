# DeletePrinterDataExW

- ea: `0x18000cdf0`
- end: `0x18000ce36`
- name: `DeletePrinterDataExW`
- size: `70`
- prototype: `DWORD __stdcall(HANDLE hPrinter, LPCWSTR pKeyName, LPCWSTR pValueName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cdf0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ce19`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce26`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce26`

## string_xrefs

- `0x18000ce1f`: `DeletePrinterDataExW`

## pseudocode

```c
DWORD __stdcall DeletePrinterDataExW(HANDLE hPrinter, LPCWSTR pKeyName, LPCWSTR pValueName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, LPCWSTR, LPCWSTR))g_pSpoolSvForwards + 45))(
             hPrinter,
             pKeyName,
             pValueName);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterDataExW");
  return 50;
}

```

## disassembly

```asm
0x18000cdf0  sub     rsp, 28h
0x18000cdf4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cdfb  jnz     short loc_18000CE14
0x18000cdfd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000ce04  mov     rax, [rax+168h]
0x18000ce0b  add     rsp, 28h
0x18000ce0f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce14  mov     ecx, 32h ; '2'; dwErrCode
0x18000ce19  call    cs:__imp_SetLastError
0x18000ce1f  lea     rcx, aDeleteprinterd_3; "DeletePrinterDataExW"
0x18000ce26  call    cs:__imp_OutputDebugStringA
0x18000ce2c  mov     eax, 32h ; '2'
0x18000ce31  add     rsp, 28h
0x18000ce35  retn
```
