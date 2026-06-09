# CacheIsNameCluster

- ea: `0x18000d4a0`
- end: `0x18000d4f3`
- name: `CacheIsNameCluster`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d4a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d4c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d4c9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d4dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d4dc`

## string_xrefs

- `0x18000d4d5`: `CacheIsNameCluster`

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
0x18000d4a0  sub     rsp, 28h
0x18000d4a4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d4ab  jnz     short loc_18000D4C4
0x18000d4ad  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d4b4  mov     rax, [rax+5A0h]
0x18000d4bb  add     rsp, 28h
0x18000d4bf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4c4  mov     ecx, 32h ; '2'; dwErrCode
0x18000d4c9  call    cs:__imp_SetLastError
0x18000d4d0  nop     dword ptr [rax+rax+00h]
0x18000d4d5  lea     rcx, aCacheisnameclu_0; "CacheIsNameCluster"
0x18000d4dc  call    cs:__imp_OutputDebugStringA
0x18000d4e3  nop     dword ptr [rax+rax+00h]
0x18000d4e8  mov     eax, 80070032h
0x18000d4ed  add     rsp, 28h
0x18000d4f1  retn
```
