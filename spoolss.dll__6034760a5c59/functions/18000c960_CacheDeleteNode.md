# CacheDeleteNode

- ea: `0x18000c960`
- end: `0x18000c9a6`
- name: `CacheDeleteNode`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c960`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c989`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c989`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c996`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c996`

## string_xrefs

- `0x18000c98f`: `CacheDeleteNode`

## pseudocode

```c
__int64 CacheDeleteNode()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 172))();
  SetLastError(0x32u);
  OutputDebugStringA("CacheDeleteNode");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000c960  sub     rsp, 28h
0x18000c964  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000c96b  jnz     short loc_18000C984
0x18000c96d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000c974  mov     rax, [rax+560h]
0x18000c97b  add     rsp, 28h
0x18000c97f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000c984  mov     ecx, 32h ; '2'; dwErrCode
0x18000c989  call    cs:__imp_SetLastError
0x18000c98f  lea     rcx, aCachedeletenod_0; "CacheDeleteNode"
0x18000c996  call    cs:__imp_OutputDebugStringA
0x18000c99c  mov     eax, 80070032h
0x18000c9a1  add     rsp, 28h
0x18000c9a5  retn
```
