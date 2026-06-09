# CacheDeleteNode

- ea: `0x18000d440`
- end: `0x18000d493`
- name: `CacheDeleteNode`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d440`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d469`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d469`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d47c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d47c`

## string_xrefs

- `0x18000d475`: `CacheDeleteNode`

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
0x18000d440  sub     rsp, 28h
0x18000d444  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d44b  jnz     short loc_18000D464
0x18000d44d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d454  mov     rax, [rax+560h]
0x18000d45b  add     rsp, 28h
0x18000d45f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d464  mov     ecx, 32h ; '2'; dwErrCode
0x18000d469  call    cs:__imp_SetLastError
0x18000d470  nop     dword ptr [rax+rax+00h]
0x18000d475  lea     rcx, aCachedeletenod_0; "CacheDeleteNode"
0x18000d47c  call    cs:__imp_OutputDebugStringA
0x18000d483  nop     dword ptr [rax+rax+00h]
0x18000d488  mov     eax, 80070032h
0x18000d48d  add     rsp, 28h
0x18000d491  retn
```
