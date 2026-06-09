# UpdatePrinterRegUser

- ea: `0x1800100c0`
- end: `0x18001011b`
- name: `UpdatePrinterRegUser`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800100c0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800100f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180010104`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180010104`

## string_xrefs

- `0x1800100fd`: `UpdatePrinterRegUser`

## pseudocode

```c
__int64 __fastcall UpdatePrinterRegUser(__int64 a1)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(__int64))g_pSpoolSvForwards + 131))(a1);
  SetLastError(0x32u);
  OutputDebugStringA("UpdatePrinterRegUser");
  return 50;
}

```

## disassembly

```asm
0x1800100c0  sub     rsp, 38h
0x1800100c4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800100cb  jnz     short loc_1800100EC
0x1800100cd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800100d4  mov     r10d, [rsp+38h+arg_20]
0x1800100d9  mov     [rsp+38h+var_18], r10d
0x1800100de  mov     rax, [rax+418h]
0x1800100e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100ea  jmp     short loc_180010115
0x1800100ec  mov     ecx, 32h ; '2'; dwErrCode
0x1800100f1  call    cs:__imp_SetLastError
0x1800100f8  nop     dword ptr [rax+rax+00h]
0x1800100fd  lea     rcx, aUpdateprinterr_3; "UpdatePrinterRegUser"
0x180010104  call    cs:__imp_OutputDebugStringA
0x18001010b  nop     dword ptr [rax+rax+00h]
0x180010110  mov     eax, 32h ; '2'
0x180010115  add     rsp, 38h
0x180010119  retn
```
