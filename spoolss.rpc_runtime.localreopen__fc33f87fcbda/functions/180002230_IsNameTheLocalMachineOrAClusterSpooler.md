# IsNameTheLocalMachineOrAClusterSpooler

- ea: `0x180002230`
- end: `0x180002282`
- name: `IsNameTheLocalMachineOrAClusterSpooler`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180002230`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000225f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000225f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002272`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002272`

## string_xrefs

- `0x18000226b`: `IsNameTheLocalMachineOrAClusterSpooler`

## pseudocode

```c
__int64 IsNameTheLocalMachineOrAClusterSpooler()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 195))();
  SetLastError(0x32u);
  OutputDebugStringA("IsNameTheLocalMachineOrAClusterSpooler");
  return 0;
}

```

## disassembly

```asm
0x180002230  sub     rsp, 28h
0x180002234  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000223b  jnz     short loc_18000225A
0x18000223d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002244  mov     rax, [rax+618h]
0x18000224b  add     rsp, 28h
0x18000224f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002254  add     rsp, 28h
0x180002258  retn
0x18000225a  mov     ecx, 32h ; '2'; dwErrCode
0x18000225f  call    cs:__imp_SetLastError
0x180002266  nop     dword ptr [rax+rax+00h]
0x18000226b  lea     rcx, aIsnamethelocal_0; "IsNameTheLocalMachineOrAClusterSpooler"
0x180002272  call    cs:__imp_OutputDebugStringA
0x180002279  nop     dword ptr [rax+rax+00h]
0x18000227e  xor     eax, eax
0x180002280  jmp     short loc_180002254
```
