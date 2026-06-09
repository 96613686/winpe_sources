# CacheCreateAndAddNode

- ea: `0x18000c8c0`
- end: `0x18000c906`
- name: `CacheCreateAndAddNode`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c8c0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c8e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c8f6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c8f6`

## string_xrefs

- `0x18000c8ef`: `CacheCreateAndAddNode`

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
0x18000c8c0  sub     rsp, 28h
0x18000c8c4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000c8cb  jnz     short loc_18000C8E4
0x18000c8cd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000c8d4  mov     rax, [rax+570h]
0x18000c8db  add     rsp, 28h
0x18000c8df  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8e4  mov     ecx, 32h ; '2'; dwErrCode
0x18000c8e9  call    cs:__imp_SetLastError
0x18000c8ef  lea     rcx, aCachecreateand_1; "CacheCreateAndAddNode"
0x18000c8f6  call    cs:__imp_OutputDebugStringA
0x18000c8fc  mov     eax, 80070032h
0x18000c901  add     rsp, 28h
0x18000c905  retn
```
