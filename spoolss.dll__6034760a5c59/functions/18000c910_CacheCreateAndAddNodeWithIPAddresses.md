# CacheCreateAndAddNodeWithIPAddresses

- ea: `0x18000c910`
- end: `0x18000c954`
- name: `CacheCreateAndAddNodeWithIPAddresses`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c910`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c937`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c937`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c944`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c944`

## string_xrefs

- `0x18000c93d`: `CacheCreateAndAddNodeWithIPAddresses`

## pseudocode

```c
__int64 CacheCreateAndAddNodeWithIPAddresses()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 175))();
  SetLastError(0x32u);
  OutputDebugStringA("CacheCreateAndAddNodeWithIPAddresses");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000c910  sub     rsp, 38h
0x18000c914  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000c91b  jnz     short loc_18000C932
0x18000c91d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000c924  mov     rax, [rax+578h]
0x18000c92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c930  jmp     short loc_18000C94F
0x18000c932  mov     ecx, 32h ; '2'; dwErrCode
0x18000c937  call    cs:__imp_SetLastError
0x18000c93d  lea     rcx, aCachecreateand_2; "CacheCreateAndAddNodeWithIPAddresses"
0x18000c944  call    cs:__imp_OutputDebugStringA
0x18000c94a  mov     eax, 80070032h
0x18000c94f  add     rsp, 38h
0x18000c953  retn
```
