# RouterGetPrinterDriverPackagePath(ushort const *,ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)

- ea: `0x18000a6b0`
- end: `0x18000a71b`
- name: `?RouterGetPrinterDriverPackagePath@@YAJPEBG000PEAGKPEAK@Z`
- size: `107`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a6b0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a6fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000a70b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000a70b`

## string_xrefs

- `0x18000a704`: `RouterGetPrinterDriverPackagePath`

## pseudocode

```c
__int64 __fastcall RouterGetPrinterDriverPackagePath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int *a7)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *))g_pSpoolSvForwards
            + 190))(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7);
  SetLastError(0x32u);
  OutputDebugStringA("RouterGetPrinterDriverPackagePath");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000a6b0  sub     rsp, 48h
0x18000a6b4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000a6bb  mov     r11, r9
0x18000a6be  jnz     short loc_18000A6F9
0x18000a6c0  mov     r10, [rsp+48h+arg_30]
0x18000a6c8  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000a6cf  mov     r9, [rsp+48h+arg_20]
0x18000a6d4  mov     [rsp+48h+var_18], r10
0x18000a6d9  mov     r10d, [rsp+48h+arg_28]
0x18000a6de  mov     rax, [rax+5F0h]
0x18000a6e5  mov     [rsp+48h+var_20], r10d
0x18000a6ea  mov     [rsp+48h+var_28], r9
0x18000a6ef  mov     r9, r11
0x18000a6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6f7  jmp     short loc_18000A716
0x18000a6f9  mov     ecx, 32h ; '2'; dwErrCode
0x18000a6fe  call    cs:__imp_SetLastError
0x18000a704  lea     rcx, aRoutergetprint_1; "RouterGetPrinterDriverPackagePath"
0x18000a70b  call    cs:__imp_OutputDebugStringA
0x18000a711  mov     eax, 80070032h
0x18000a716  add     rsp, 48h
0x18000a71a  retn
```
