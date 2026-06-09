# OpenPrinterExW(ushort *,void * *,_PRINTER_DEFAULTSW *,_SPLCLIENT_CONTAINER *)

- ea: `0x180009dd0`
- end: `0x180009e1e`
- name: `?OpenPrinterExW@@YAHPEAGPEAPEAXPEAU_PRINTER_DEFAULTSW@@PEAU_SPLCLIENT_CONTAINER@@@Z`
- size: `78`
- prototype: `__int64 __fastcall(unsigned __int16 *, void **, struct _PRINTER_DEFAULTSW *, struct _SPLCLIENT_CONTAINER *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009dd0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009df7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009df7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009e0a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180009e0a`

## string_xrefs

- `0x180009e03`: `OpenPrinterExW`

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
0x180009dd0  sub     rsp, 38h
0x180009dd4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x180009ddb  jnz     short loc_180009DF2
0x180009ddd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180009de4  mov     rax, [rax+0E0h]
0x180009deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df0  jmp     short loc_180009E18
0x180009df2  mov     ecx, 32h ; '2'; dwErrCode
0x180009df7  call    cs:__imp_SetLastError
0x180009dfe  nop     dword ptr [rax+rax+00h]
0x180009e03  lea     rcx, aOpenprinterexw_0; "OpenPrinterExW"
0x180009e0a  call    cs:__imp_OutputDebugStringA
0x180009e11  nop     dword ptr [rax+rax+00h]
0x180009e16  xor     eax, eax
0x180009e18  add     rsp, 38h
0x180009e1c  retn
```
