# SplGetUserSidStringFromToken

- ea: `0x1800036f0`
- end: `0x180003741`
- name: `SplGetUserSidStringFromToken`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800036f0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003717`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003717`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000372a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000372a`

## string_xrefs

- `0x180003723`: `SplGetUserSidStringFromToken`

## pseudocode

```c
__int64 SplGetUserSidStringFromToken()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 160))();
  SetLastError(0x32u);
  OutputDebugStringA("SplGetUserSidStringFromToken");
  return 50;
}

```

## disassembly

```asm
0x1800036f0  sub     rsp, 38h
0x1800036f4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800036fb  jnz     short loc_180003712
0x1800036fd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180003704  mov     rax, [rax+500h]
0x18000370b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003710  jmp     short loc_18000373B
0x180003712  mov     ecx, 32h ; '2'; dwErrCode
0x180003717  call    cs:__imp_SetLastError
0x18000371e  nop     dword ptr [rax+rax+00h]
0x180003723  lea     rcx, aSplgetusersids_0; "SplGetUserSidStringFromToken"
0x18000372a  call    cs:__imp_OutputDebugStringA
0x180003731  nop     dword ptr [rax+rax+00h]
0x180003736  mov     eax, 32h ; '2'
0x18000373b  add     rsp, 38h
0x18000373f  retn
```
