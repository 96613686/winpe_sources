# RouterInstallPrinterDriverFromPackage(ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000a730`
- end: `0x18000a77e`
- name: `?RouterInstallPrinterDriverFromPackage@@YAJPEBG000K@Z`
- size: `78`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000a730`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a761`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a761`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000a76e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000a76e`

## string_xrefs

- `0x18000a767`: `RouterInstallPrinterDriverFromPackage`

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
0x18000a730  sub     rsp, 38h
0x18000a734  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000a73b  jnz     short loc_18000A75C
0x18000a73d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000a744  mov     r10d, [rsp+38h+arg_20]
0x18000a749  mov     [rsp+38h+var_18], r10d
0x18000a74e  mov     rax, [rax+5D0h]
0x18000a755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a75a  jmp     short loc_18000A779
0x18000a75c  mov     ecx, 32h ; '2'; dwErrCode
0x18000a761  call    cs:__imp_SetLastError
0x18000a767  lea     rcx, aRouterinstallp_1; "RouterInstallPrinterDriverFromPackage"
0x18000a76e  call    cs:__imp_OutputDebugStringA
0x18000a774  mov     eax, 80070032h
0x18000a779  add     rsp, 38h
0x18000a77d  retn
```
