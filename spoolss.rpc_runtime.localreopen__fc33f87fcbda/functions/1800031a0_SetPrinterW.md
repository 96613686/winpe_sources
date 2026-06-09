# SetPrinterW

- ea: `0x1800031a0`
- end: `0x1800031eb`
- name: `SetPrinterW`
- size: `75`
- prototype: `BOOL __stdcall(HANDLE hPrinter, DWORD Level, LPBYTE pPrinter, DWORD Command)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800031a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800031d7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800031d7`

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
0x1800031a0  sub     rsp, 38h
0x1800031a4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800031ab  jnz     short loc_1800031BF
0x1800031ad  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800031b4  mov     rax, [rax+48h]
0x1800031b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031bd  jmp     short loc_1800031E5
0x1800031bf  mov     ecx, 32h ; '2'; dwErrCode
0x1800031c4  call    cs:__imp_SetLastError
0x1800031cb  nop     dword ptr [rax+rax+00h]
0x1800031d0  lea     rcx, aSetprinterw_0; "SetPrinterW"
0x1800031d7  call    cs:__imp_OutputDebugStringA
0x1800031de  nop     dword ptr [rax+rax+00h]
0x1800031e3  xor     eax, eax
0x1800031e5  add     rsp, 38h
0x1800031e9  retn
```
