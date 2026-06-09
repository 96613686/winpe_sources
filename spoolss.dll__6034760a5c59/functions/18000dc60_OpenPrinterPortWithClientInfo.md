# OpenPrinterPortWithClientInfo

- ea: `0x18000dc60`
- end: `0x18000dcb5`
- name: `OpenPrinterPortWithClientInfo`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dc60`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dca8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dca8`

## string_xrefs

- `0x18000dca1`: `OpenPrinterPortWithClientInfo`

## pseudocode

```c
__int64 __fastcall OpenPrinterPortWithClientInfo(__int64 a1, __int64 a2)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(__int64, __int64))g_pSpoolSvForwards + 32))(a1, a2);
  SetLastError(0x32u);
  OutputDebugStringA("OpenPrinterPortWithClientInfo");
  return 0;
}

```

## disassembly

```asm
0x18000dc60  sub     rsp, 48h
0x18000dc64  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000dc6b  jnz     short loc_18000DC96
0x18000dc6d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000dc74  mov     r10d, [rsp+48h+arg_28]
0x18000dc79  mov     [rsp+48h+var_20], r10d
0x18000dc7e  mov     r10, [rsp+48h+arg_20]
0x18000dc83  mov     rax, [rax+100h]
0x18000dc8a  mov     [rsp+48h+var_28], r10
0x18000dc8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc94  jmp     short loc_18000DCB0
0x18000dc96  mov     ecx, 32h ; '2'; dwErrCode
0x18000dc9b  call    cs:__imp_SetLastError
0x18000dca1  lea     rcx, aOpenprinterpor_2; "OpenPrinterPortWithClientInfo"
0x18000dca8  call    cs:__imp_OutputDebugStringA
0x18000dcae  xor     eax, eax
0x18000dcb0  add     rsp, 48h
0x18000dcb4  retn
```
