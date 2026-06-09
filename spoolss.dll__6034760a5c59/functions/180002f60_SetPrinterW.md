# SetPrinterW

- ea: `0x180002f60`
- end: `0x180002f9e`
- name: `SetPrinterW`
- size: `62`
- prototype: `BOOL __stdcall(HANDLE hPrinter, DWORD Level, LPBYTE pPrinter, DWORD Command)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002f60`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f84`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002f91`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002f91`

## pseudocode

```c
BOOL __stdcall SetPrinterW(HANDLE hPrinter, DWORD Level, LPBYTE pPrinter, DWORD Command)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(HANDLE, DWORD, LPBYTE, DWORD))g_pSpoolSvForwards + 9))(
             hPrinter,
             Level,
             pPrinter,
             Command);
  SetLastError(0x32u);
  OutputDebugStringA("SetPrinterW");
  return 0;
}

```

## disassembly

```asm
0x180002f60  sub     rsp, 38h
0x180002f64  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180002f6b  jnz     short loc_180002F7F
0x180002f6d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002f74  mov     rax, [rax+48h]
0x180002f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7d  jmp     short loc_180002F99
0x180002f7f  mov     ecx, 32h ; '2'; dwErrCode
0x180002f84  call    cs:__imp_SetLastError
0x180002f8a  lea     rcx, aSetprinterw_0; "SetPrinterW"
0x180002f91  call    cs:__imp_OutputDebugStringA
0x180002f97  xor     eax, eax
0x180002f99  add     rsp, 38h
0x180002f9d  retn
```
