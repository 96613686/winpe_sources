# DeleteMonitorW

- ea: `0x18000d6f0`
- end: `0x18000d740`
- name: `DeleteMonitorW`
- size: `80`
- prototype: `BOOL __stdcall(LPWSTR pName, LPWSTR pEnvironment, LPWSTR pMonitorName)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d6f0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d719`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d719`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d72c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d72c`

## string_xrefs

- `0x18000d725`: `DeleteMonitorW`

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
0x18000d6f0  sub     rsp, 28h
0x18000d6f4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d6fb  jnz     short loc_18000D714
0x18000d6fd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d704  mov     rax, [rax+348h]
0x18000d70b  add     rsp, 28h
0x18000d70f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d714  mov     ecx, 32h ; '2'; dwErrCode
0x18000d719  call    cs:__imp_SetLastError
0x18000d720  nop     dword ptr [rax+rax+00h]
0x18000d725  lea     rcx, aDeletemonitorw_0; "DeleteMonitorW"
0x18000d72c  call    cs:__imp_OutputDebugStringA
0x18000d733  nop     dword ptr [rax+rax+00h]
0x18000d738  xor     eax, eax
0x18000d73a  add     rsp, 28h
0x18000d73e  retn
```
