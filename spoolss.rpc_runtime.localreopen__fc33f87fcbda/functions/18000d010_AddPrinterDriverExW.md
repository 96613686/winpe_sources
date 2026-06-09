# AddPrinterDriverExW

- ea: `0x18000d010`
- end: `0x18000d05e`
- name: `AddPrinterDriverExW`
- size: `78`
- prototype: `BOOL __stdcall(LPWSTR pName, DWORD Level, PBYTE lpbDriverInfo, DWORD dwFileCopyFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d010`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d037`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d037`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d04a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d04a`

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
0x18000d010  sub     rsp, 38h
0x18000d014  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d01b  jnz     short loc_18000D032
0x18000d01d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d024  mov     rax, [rax+90h]
0x18000d02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d030  jmp     short loc_18000D058
0x18000d032  mov     ecx, 32h ; '2'; dwErrCode
0x18000d037  call    cs:__imp_SetLastError
0x18000d03e  nop     dword ptr [rax+rax+00h]
0x18000d043  lea     rcx, aAddprinterdriv_1; "AddPrinterDriverExW"
0x18000d04a  call    cs:__imp_OutputDebugStringA
0x18000d051  nop     dword ptr [rax+rax+00h]
0x18000d056  xor     eax, eax
0x18000d058  add     rsp, 38h
0x18000d05c  retn
```
