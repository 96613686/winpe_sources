# AddPrintProcessorW

- ea: `0x18000cef0`
- end: `0x18000cf3e`
- name: `AddPrintProcessorW`
- size: `78`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPathName, LPWSTR pPrintProcessorName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cef0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cf17`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cf2a`

## pseudocode

```c
BOOL __stdcall AddPrintProcessorW(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPathName, LPWSTR pPrintProcessorName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPWSTR, LPWSTR, LPWSTR))g_pSpoolSvForwards + 22))(
             pName,
             pEnvironment,
             pPathName,
             pPrintProcessorName);
  SetLastError(0x32u);
  OutputDebugStringA("AddPrintProcessorW");
  return 0;
}

```

## disassembly

```asm
0x18000cef0  sub     rsp, 38h
0x18000cef4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cefb  jnz     short loc_18000CF12
0x18000cefd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cf04  mov     rax, [rax+0B0h]
0x18000cf0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf10  jmp     short loc_18000CF38
0x18000cf12  mov     ecx, 32h ; '2'; dwErrCode
0x18000cf17  call    cs:__imp_SetLastError
0x18000cf1e  nop     dword ptr [rax+rax+00h]
0x18000cf23  lea     rcx, aAddprintproces_0; "AddPrintProcessorW"
0x18000cf2a  call    cs:__imp_OutputDebugStringA
0x18000cf31  nop     dword ptr [rax+rax+00h]
0x18000cf36  xor     eax, eax
0x18000cf38  add     rsp, 38h
0x18000cf3c  retn
```
