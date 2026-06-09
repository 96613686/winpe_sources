# DeletePrinterKeyW

- ea: `0x18000cf90`
- end: `0x18000cfd6`
- name: `DeletePrinterKeyW`
- size: `70`
- prototype: `DWORD __stdcall(HANDLE hPrinter, LPCWSTR pKeyName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cf90`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cfb9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cfc6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cfc6`

## string_xrefs

- `0x18000cfbf`: `DeletePrinterKeyW`

## pseudocode

```c
DWORD __stdcall DeletePrinterKeyW(HANDLE hPrinter, LPCWSTR pKeyName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, LPCWSTR))g_pSpoolSvForwards + 46))(hPrinter, pKeyName);
  SetLastError(0x32u);
  OutputDebugStringA("DeletePrinterKeyW");
  return 50;
}

```

## disassembly

```asm
0x18000cf90  sub     rsp, 28h
0x18000cf94  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cf9b  jnz     short loc_18000CFB4
0x18000cf9d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cfa4  mov     rax, [rax+170h]
0x18000cfab  add     rsp, 28h
0x18000cfaf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfb4  mov     ecx, 32h ; '2'; dwErrCode
0x18000cfb9  call    cs:__imp_SetLastError
0x18000cfbf  lea     rcx, aDeleteprinterk_0; "DeletePrinterKeyW"
0x18000cfc6  call    cs:__imp_OutputDebugStringA
0x18000cfcc  mov     eax, 32h ; '2'
0x18000cfd1  add     rsp, 28h
0x18000cfd5  retn
```
