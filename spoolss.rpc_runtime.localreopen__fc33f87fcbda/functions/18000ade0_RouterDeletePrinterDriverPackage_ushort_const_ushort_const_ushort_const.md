# RouterDeletePrinterDriverPackage(ushort const *,ushort const *,ushort const *)

- ea: `0x18000ade0`
- end: `0x18000ae33`
- name: `?RouterDeletePrinterDriverPackage@@YAJPEBG00@Z`
- size: `83`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ade0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae09`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ae1c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ae1c`

## string_xrefs

- `0x18000ae15`: `RouterDeletePrinterDriverPackage`

## pseudocode

```c
__int64 __fastcall RouterDeletePrinterDriverPackage(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *))g_pSpoolSvForwards
            + 191))(
             a1,
             a2,
             a3);
  SetLastError(0x32u);
  OutputDebugStringA("RouterDeletePrinterDriverPackage");
  return 2147942450LL;
}

```

## disassembly

```asm
0x18000ade0  sub     rsp, 28h
0x18000ade4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000adeb  jnz     short loc_18000AE04
0x18000aded  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000adf4  mov     rax, [rax+5F8h]
0x18000adfb  add     rsp, 28h
0x18000adff  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae04  mov     ecx, 32h ; '2'; dwErrCode
0x18000ae09  call    cs:__imp_SetLastError
0x18000ae10  nop     dword ptr [rax+rax+00h]
0x18000ae15  lea     rcx, aRouterdeletepr_0; "RouterDeletePrinterDriverPackage"
0x18000ae1c  call    cs:__imp_OutputDebugStringA
0x18000ae23  nop     dword ptr [rax+rax+00h]
0x18000ae28  mov     eax, 80070032h
0x18000ae2d  add     rsp, 28h
0x18000ae31  retn
```
