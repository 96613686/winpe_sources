# CacheCreateAndAddNode

- ea: `0x18000d380`
- end: `0x18000d3d3`
- name: `CacheCreateAndAddNode`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d380`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d3bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d3bc`

## string_xrefs

- `0x18000d3b5`: `CacheCreateAndAddNode`

## pseudocode

```c
__int64 CacheCreateAndAddNode()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 174))();
  SetLastError(0x32u);
  OutputDebugStringA("CacheCreateAndAddNode");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000d380  sub     rsp, 28h
0x18000d384  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d38b  jnz     short loc_18000D3A4
0x18000d38d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d394  mov     rax, [rax+570h]
0x18000d39b  add     rsp, 28h
0x18000d39f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a4  mov     ecx, 32h ; '2'; dwErrCode
0x18000d3a9  call    cs:__imp_SetLastError
0x18000d3b0  nop     dword ptr [rax+rax+00h]
0x18000d3b5  lea     rcx, aCachecreateand_1; "CacheCreateAndAddNode"
0x18000d3bc  call    cs:__imp_OutputDebugStringA
0x18000d3c3  nop     dword ptr [rax+rax+00h]
0x18000d3c8  mov     eax, 80070032h
0x18000d3cd  add     rsp, 28h
0x18000d3d1  retn
```
