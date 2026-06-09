# DeletePrinterDataExW

- ea: `0x18000d9b0`
- end: `0x18000da03`
- name: `DeletePrinterDataExW`
- size: `83`
- prototype: `DWORD __stdcall(HANDLE hPrinter, LPCWSTR pKeyName, LPCWSTR pValueName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d9b0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d9ec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d9ec`

## string_xrefs

- `0x18000d9e5`: `DeletePrinterDataExW`

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
0x18000d9b0  sub     rsp, 28h
0x18000d9b4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d9bb  jnz     short loc_18000D9D4
0x18000d9bd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d9c4  mov     rax, [rax+168h]
0x18000d9cb  add     rsp, 28h
0x18000d9cf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9d4  mov     ecx, 32h ; '2'; dwErrCode
0x18000d9d9  call    cs:__imp_SetLastError
0x18000d9e0  nop     dword ptr [rax+rax+00h]
0x18000d9e5  lea     rcx, aDeleteprinterd_3; "DeletePrinterDataExW"
0x18000d9ec  call    cs:__imp_OutputDebugStringA
0x18000d9f3  nop     dword ptr [rax+rax+00h]
0x18000d9f8  mov     eax, 32h ; '2'
0x18000d9fd  add     rsp, 28h
0x18000da01  retn
```
