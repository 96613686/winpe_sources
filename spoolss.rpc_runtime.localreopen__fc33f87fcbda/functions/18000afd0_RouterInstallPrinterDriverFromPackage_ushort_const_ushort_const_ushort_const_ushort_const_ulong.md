# RouterInstallPrinterDriverFromPackage(ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000afd0`
- end: `0x18000b02b`
- name: `?RouterInstallPrinterDriverFromPackage@@YAJPEBG000K@Z`
- size: `91`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000afd0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b001`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b001`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000b014`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000b014`

## string_xrefs

- `0x18000b00d`: `RouterInstallPrinterDriverFromPackage`

## pseudocode

```c
__int64 __fastcall RouterInstallPrinterDriverFromPackage(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int))g_pSpoolSvForwards
            + 186))(
             a1,
             a2,
             a3,
             a4,
             a5);
  SetLastError(0x32u);
  OutputDebugStringA("RouterInstallPrinterDriverFromPackage");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000afd0  sub     rsp, 38h
0x18000afd4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000afdb  jnz     short loc_18000AFFC
0x18000afdd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000afe4  mov     r10d, [rsp+38h+arg_20]
0x18000afe9  mov     [rsp+38h+var_18], r10d
0x18000afee  mov     rax, [rax+5D0h]
0x18000aff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000affa  jmp     short loc_18000B025
0x18000affc  mov     ecx, 32h ; '2'; dwErrCode
0x18000b001  call    cs:__imp_SetLastError
0x18000b008  nop     dword ptr [rax+rax+00h]
0x18000b00d  lea     rcx, aRouterinstallp_1; "RouterInstallPrinterDriverFromPackage"
0x18000b014  call    cs:__imp_OutputDebugStringA
0x18000b01b  nop     dword ptr [rax+rax+00h]
0x18000b020  mov     eax, 80070032h
0x18000b025  add     rsp, 38h
0x18000b029  retn
```
