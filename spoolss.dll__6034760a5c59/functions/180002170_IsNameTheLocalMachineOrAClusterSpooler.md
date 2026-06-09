# IsNameTheLocalMachineOrAClusterSpooler

- ea: `0x180002170`
- end: `0x1800021b5`
- name: `IsNameTheLocalMachineOrAClusterSpooler`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180002170`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000219e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000219e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800021ab`

## string_xrefs

- `0x1800021a4`: `IsNameTheLocalMachineOrAClusterSpooler`

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
0x180002170  sub     rsp, 28h
0x180002174  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000217b  jnz     short loc_180002199
0x18000217d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002184  mov     rax, [rax+618h]
0x18000218b  add     rsp, 28h
0x18000218f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002194  add     rsp, 28h
0x180002198  retn
0x180002199  mov     ecx, 32h ; '2'; dwErrCode
0x18000219e  call    cs:__imp_SetLastError
0x1800021a4  lea     rcx, aIsnamethelocal_0; "IsNameTheLocalMachineOrAClusterSpooler"
0x1800021ab  call    cs:__imp_OutputDebugStringA
0x1800021b1  xor     eax, eax
0x1800021b3  jmp     short loc_180002194
```
