# SplGetUserSidStringFromToken

- ea: `0x1800034a0`
- end: `0x1800034e4`
- name: `SplGetUserSidStringFromToken`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x1800034a0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034c7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800034d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800034d4`

## string_xrefs

- `0x1800034cd`: `SplGetUserSidStringFromToken`

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
0x1800034a0  sub     rsp, 38h
0x1800034a4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800034ab  jnz     short loc_1800034C2
0x1800034ad  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800034b4  mov     rax, [rax+500h]
0x1800034bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034c0  jmp     short loc_1800034DF
0x1800034c2  mov     ecx, 32h ; '2'; dwErrCode
0x1800034c7  call    cs:__imp_SetLastError
0x1800034cd  lea     rcx, aSplgetusersids_0; "SplGetUserSidStringFromToken"
0x1800034d4  call    cs:__imp_OutputDebugStringA
0x1800034da  mov     eax, 32h ; '2'
0x1800034df  add     rsp, 38h
0x1800034e3  retn
```
