# CacheCreateAndAddNodeWithIPAddresses

- ea: `0x18000d3e0`
- end: `0x18000d431`
- name: `CacheCreateAndAddNodeWithIPAddresses`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d3e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d407`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d407`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d41a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d41a`

## string_xrefs

- `0x18000d413`: `CacheCreateAndAddNodeWithIPAddresses`

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
0x18000d3e0  sub     rsp, 38h
0x18000d3e4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d3eb  jnz     short loc_18000D402
0x18000d3ed  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d3f4  mov     rax, [rax+578h]
0x18000d3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d400  jmp     short loc_18000D42B
0x18000d402  mov     ecx, 32h ; '2'; dwErrCode
0x18000d407  call    cs:__imp_SetLastError
0x18000d40e  nop     dword ptr [rax+rax+00h]
0x18000d413  lea     rcx, aCachecreateand_2; "CacheCreateAndAddNodeWithIPAddresses"
0x18000d41a  call    cs:__imp_OutputDebugStringA
0x18000d421  nop     dword ptr [rax+rax+00h]
0x18000d426  mov     eax, 80070032h
0x18000d42b  add     rsp, 38h
0x18000d42f  retn
```
