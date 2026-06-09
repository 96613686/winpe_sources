# CacheAddName

- ea: `0x180001ca0`
- end: `0x180001cf5`
- name: `CacheAddName`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ca0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ccf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001ccf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ce2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001ce2`

## string_xrefs

- `0x180001cdb`: `CacheAddName`

## pseudocode

```c
__int64 CacheAddName()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 171))();
  SetLastError(0x32u);
  OutputDebugStringA("CacheAddName");
  return 2147942450LL;
}

```

## disassembly

```asm
0x180001ca0  sub     rsp, 28h
0x180001ca4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180001cab  jnz     short loc_180001CCA
0x180001cad  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180001cb4  mov     rax, [rax+558h]
0x180001cbb  add     rsp, 28h
0x180001cbf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001cc4  add     rsp, 28h
0x180001cc8  retn
0x180001cca  mov     ecx, 32h ; '2'; dwErrCode
0x180001ccf  call    cs:__imp_SetLastError
0x180001cd6  nop     dword ptr [rax+rax+00h]
0x180001cdb  lea     rcx, aCacheaddname_0; "CacheAddName"
0x180001ce2  call    cs:__imp_OutputDebugStringA
0x180001ce9  nop     dword ptr [rax+rax+00h]
0x180001cee  mov     eax, 80070032h
0x180001cf3  jmp     short loc_180001CC4
```
