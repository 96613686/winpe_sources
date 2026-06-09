# CacheIsNameInNodeList

- ea: `0x180002060`
- end: `0x1800020b5`
- name: `CacheIsNameInNodeList`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002060`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000208f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000208f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020a2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800020a2`

## string_xrefs

- `0x18000209b`: `CacheIsNameInNodeList`

## pseudocode

```c
__int64 CacheIsNameInNodeList()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 173))();
  SetLastError(0x32u);
  OutputDebugStringA("CacheIsNameInNodeList");
  return 2147942450LL;
}

```

## disassembly

```asm
0x180002060  sub     rsp, 28h
0x180002064  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000206b  jnz     short loc_18000208A
0x18000206d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002074  mov     rax, [rax+568h]
0x18000207b  add     rsp, 28h
0x18000207f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002084  add     rsp, 28h
0x180002088  retn
0x18000208a  mov     ecx, 32h ; '2'; dwErrCode
0x18000208f  call    cs:__imp_SetLastError
0x180002096  nop     dword ptr [rax+rax+00h]
0x18000209b  lea     rcx, aCacheisnameinn_0; "CacheIsNameInNodeList"
0x1800020a2  call    cs:__imp_OutputDebugStringA
0x1800020a9  nop     dword ptr [rax+rax+00h]
0x1800020ae  mov     eax, 80070032h
0x1800020b3  jmp     short loc_180002084
```
