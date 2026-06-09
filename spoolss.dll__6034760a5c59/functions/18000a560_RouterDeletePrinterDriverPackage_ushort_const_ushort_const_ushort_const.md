# RouterDeletePrinterDriverPackage(ushort const *,ushort const *,ushort const *)

- ea: `0x18000a560`
- end: `0x18000a5a6`
- name: `?RouterDeletePrinterDriverPackage@@YAJPEBG00@Z`
- size: `70`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a560`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a589`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a589`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000a596`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000a596`

## string_xrefs

- `0x18000a58f`: `RouterDeletePrinterDriverPackage`

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
0x18000a560  sub     rsp, 28h
0x18000a564  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000a56b  jnz     short loc_18000A584
0x18000a56d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000a574  mov     rax, [rax+5F8h]
0x18000a57b  add     rsp, 28h
0x18000a57f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000a584  mov     ecx, 32h ; '2'; dwErrCode
0x18000a589  call    cs:__imp_SetLastError
0x18000a58f  lea     rcx, aRouterdeletepr_0; "RouterDeletePrinterDriverPackage"
0x18000a596  call    cs:__imp_OutputDebugStringA
0x18000a59c  mov     eax, 80070032h
0x18000a5a1  add     rsp, 28h
0x18000a5a5  retn
```
