# CacheIsNameCluster

- ea: `0x18000c9b0`
- end: `0x18000c9f6`
- name: `CacheIsNameCluster`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c9b0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9d9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c9e6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c9e6`

## string_xrefs

- `0x18000c9df`: `CacheIsNameCluster`

## pseudocode

```c
__int64 CacheIsNameCluster()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 180))();
  SetLastError(0x32u);
  OutputDebugStringA("CacheIsNameCluster");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000c9b0  sub     rsp, 28h
0x18000c9b4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000c9bb  jnz     short loc_18000C9D4
0x18000c9bd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000c9c4  mov     rax, [rax+5A0h]
0x18000c9cb  add     rsp, 28h
0x18000c9cf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9d4  mov     ecx, 32h ; '2'; dwErrCode
0x18000c9d9  call    cs:__imp_SetLastError
0x18000c9df  lea     rcx, aCacheisnameclu_0; "CacheIsNameCluster"
0x18000c9e6  call    cs:__imp_OutputDebugStringA
0x18000c9ec  mov     eax, 80070032h
0x18000c9f1  add     rsp, 28h
0x18000c9f5  retn
```
