# OpenPrinterPort2W

- ea: `0x180002830`
- end: `0x180002871`
- name: `OpenPrinterPort2W`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002830`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002857`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002857`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002864`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002864`

## string_xrefs

- `0x18000285d`: `OpenPrinterPort2W`

## pseudocode

```c
__int64 OpenPrinterPort2W()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 31))();
  SetLastError(0x32u);
  OutputDebugStringA("OpenPrinterPort2W");
  return 0;
}

```

## disassembly

```asm
0x180002830  sub     rsp, 38h
0x180002834  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000283b  jnz     short loc_180002852
0x18000283d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002844  mov     rax, [rax+0F8h]
0x18000284b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002850  jmp     short loc_18000286C
0x180002852  mov     ecx, 32h ; '2'; dwErrCode
0x180002857  call    cs:__imp_SetLastError
0x18000285d  lea     rcx, aOpenprinterpor_1; "OpenPrinterPort2W"
0x180002864  call    cs:__imp_OutputDebugStringA
0x18000286a  xor     eax, eax
0x18000286c  add     rsp, 38h
0x180002870  retn
```
