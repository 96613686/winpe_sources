# AddPrinterDriverExW

- ea: `0x18000c5b0`
- end: `0x18000c5f1`
- name: `AddPrinterDriverExW`
- size: `65`
- prototype: `BOOL __stdcall(LPWSTR pName, DWORD Level, PBYTE lpbDriverInfo, DWORD dwFileCopyFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c5b0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c5d7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c5e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c5e4`

## pseudocode

```c
BOOL __stdcall AddPrinterDriverExW(LPWSTR pName, DWORD Level, PBYTE lpbDriverInfo, DWORD dwFileCopyFlags)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, DWORD, PBYTE, DWORD))g_pSpoolSvForwards + 18))(
             pName,
             Level,
             lpbDriverInfo,
             dwFileCopyFlags);
  SetLastError(0x32u);
  OutputDebugStringA("AddPrinterDriverExW");
  return 0;
}

```

## disassembly

```asm
0x18000c5b0  sub     rsp, 38h
0x18000c5b4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000c5bb  jnz     short loc_18000C5D2
0x18000c5bd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000c5c4  mov     rax, [rax+90h]
0x18000c5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5d0  jmp     short loc_18000C5EC
0x18000c5d2  mov     ecx, 32h ; '2'; dwErrCode
0x18000c5d7  call    cs:__imp_SetLastError
0x18000c5dd  lea     rcx, aAddprinterdriv_1; "AddPrinterDriverExW"
0x18000c5e4  call    cs:__imp_OutputDebugStringA
0x18000c5ea  xor     eax, eax
0x18000c5ec  add     rsp, 38h
0x18000c5f0  retn
```
