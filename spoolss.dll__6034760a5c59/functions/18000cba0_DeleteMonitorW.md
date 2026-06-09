# DeleteMonitorW

- ea: `0x18000cba0`
- end: `0x18000cbe3`
- name: `DeleteMonitorW`
- size: `67`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pMonitorName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000cba0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cbc9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbd6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbd6`

## string_xrefs

- `0x18000cbcf`: `DeleteMonitorW`

## pseudocode

```c
BOOL __stdcall DeleteMonitorW(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pMonitorName)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(LPWSTR, LPWSTR, LPWSTR))g_pSpoolSvForwards + 105))(
             pName,
             pEnvironment,
             pMonitorName);
  SetLastError(0x32u);
  OutputDebugStringA("DeleteMonitorW");
  return 0;
}

```

## disassembly

```asm
0x18000cba0  sub     rsp, 28h
0x18000cba4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000cbab  jnz     short loc_18000CBC4
0x18000cbad  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000cbb4  mov     rax, [rax+348h]
0x18000cbbb  add     rsp, 28h
0x18000cbbf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbc4  mov     ecx, 32h ; '2'; dwErrCode
0x18000cbc9  call    cs:__imp_SetLastError
0x18000cbcf  lea     rcx, aDeletemonitorw_0; "DeleteMonitorW"
0x18000cbd6  call    cs:__imp_OutputDebugStringA
0x18000cbdc  xor     eax, eax
0x18000cbde  add     rsp, 28h
0x18000cbe2  retn
```
