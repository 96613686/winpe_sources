# OpenPrinterExW(ushort *,void * *,_PRINTER_DEFAULTSW *,_SPLCLIENT_CONTAINER *)

- ea: `0x180009680`
- end: `0x1800096c1`
- name: `?OpenPrinterExW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAU_SPLCLIENT_CONTAINER@@@Z`
- size: `65`
- prototype: `__int64 __fastcall(unsigned __int16 *, void **, struct _PRINTER_DEFAULTSW *, struct _SPLCLIENT_CONTAINER *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009680`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800096a7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800096b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800096b4`

## string_xrefs

- `0x1800096ad`: `OpenPrinterExW`

## pseudocode

```c
__int64 __fastcall OpenPrinterExW(
        unsigned __int16 *a1,
        void **a2,
        struct _PRINTER_DEFAULTSW *a3,
        struct _SPLCLIENT_CONTAINER *a4)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(unsigned __int16 *, void **, struct _PRINTER_DEFAULTSW *, struct _SPLCLIENT_CONTAINER *))g_pSpoolSvForwards
            + 28))(
             a1,
             a2,
             a3,
             a4);
  SetLastError(0x32u);
  OutputDebugStringA("OpenPrinterExW");
  return 0;
}

```

## disassembly

```asm
0x180009680  sub     rsp, 38h
0x180009684  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000968b  jnz     short loc_1800096A2
0x18000968d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180009694  mov     rax, [rax+0E0h]
0x18000969b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a0  jmp     short loc_1800096BC
0x1800096a2  mov     ecx, 32h ; '2'; dwErrCode
0x1800096a7  call    cs:__imp_SetLastError
0x1800096ad  lea     rcx, aOpenprinterexw_0; "OpenPrinterExW"
0x1800096b4  call    cs:__imp_OutputDebugStringA
0x1800096ba  xor     eax, eax
0x1800096bc  add     rsp, 38h
0x1800096c0  retn
```
