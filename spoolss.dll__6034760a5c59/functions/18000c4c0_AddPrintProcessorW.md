# AddPrintProcessorW

- ea: `0x18000c4c0`
- end: `0x18000c501`
- name: `AddPrintProcessorW`
- size: `65`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pPathName, LPWSTR pPrintProcessorName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c4c0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c4e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c4e7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c4f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c4f4`

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
0x18000c4c0  sub     rsp, 38h
0x18000c4c4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000c4cb  jnz     short loc_18000C4E2
0x18000c4cd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000c4d4  mov     rax, [rax+0B0h]
0x18000c4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4e0  jmp     short loc_18000C4FC
0x18000c4e2  mov     ecx, 32h ; '2'; dwErrCode
0x18000c4e7  call    cs:__imp_SetLastError
0x18000c4ed  lea     rcx, aAddprintproces_0; "AddPrintProcessorW"
0x18000c4f4  call    cs:__imp_OutputDebugStringA
0x18000c4fa  xor     eax, eax
0x18000c4fc  add     rsp, 38h
0x18000c500  retn
```
