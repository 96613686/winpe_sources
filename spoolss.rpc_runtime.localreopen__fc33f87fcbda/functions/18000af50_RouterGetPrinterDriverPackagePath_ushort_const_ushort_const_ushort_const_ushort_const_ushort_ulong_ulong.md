# RouterGetPrinterDriverPackagePath(ushort const *,ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)

- ea: `0x18000af50`
- end: `0x18000afc8`
- name: `?RouterGetPrinterDriverPackagePath@@YAJPEBG000PEAGKPEAK@Z`
- size: `120`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000af50`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af9e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000afb1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000afb1`

## string_xrefs

- `0x18000afaa`: `RouterGetPrinterDriverPackagePath`

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
0x18000af50  sub     rsp, 48h
0x18000af54  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000af5b  mov     r11, r9
0x18000af5e  jnz     short loc_18000AF99
0x18000af60  mov     r10, [rsp+48h+arg_30]
0x18000af68  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000af6f  mov     r9, [rsp+48h+arg_20]
0x18000af74  mov     [rsp+48h+var_18], r10
0x18000af79  mov     r10d, [rsp+48h+arg_28]
0x18000af7e  mov     rax, [rax+5F0h]
0x18000af85  mov     [rsp+48h+var_20], r10d
0x18000af8a  mov     [rsp+48h+var_28], r9
0x18000af8f  mov     r9, r11
0x18000af92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af97  jmp     short loc_18000AFC2
0x18000af99  mov     ecx, 32h ; '2'; dwErrCode
0x18000af9e  call    cs:__imp_SetLastError
0x18000afa5  nop     dword ptr [rax+rax+00h]
0x18000afaa  lea     rcx, aRoutergetprint_1; "RouterGetPrinterDriverPackagePath"
0x18000afb1  call    cs:__imp_OutputDebugStringA
0x18000afb8  nop     dword ptr [rax+rax+00h]
0x18000afbd  mov     eax, 80070032h
0x18000afc2  add     rsp, 48h
0x18000afc6  retn
```
