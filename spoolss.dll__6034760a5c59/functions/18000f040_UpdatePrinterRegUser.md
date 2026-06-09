# UpdatePrinterRegUser

- ea: `0x18000f040`
- end: `0x18000f08e`
- name: `UpdatePrinterRegUser`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000f040`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f071`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f071`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000f07e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000f07e`

## string_xrefs

- `0x18000f077`: `UpdatePrinterRegUser`

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
0x18000f040  sub     rsp, 38h
0x18000f044  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000f04b  jnz     short loc_18000F06C
0x18000f04d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000f054  mov     r10d, [rsp+38h+arg_20]
0x18000f059  mov     [rsp+38h+var_18], r10d
0x18000f05e  mov     rax, [rax+418h]
0x18000f065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06a  jmp     short loc_18000F089
0x18000f06c  mov     ecx, 32h ; '2'; dwErrCode
0x18000f071  call    cs:__imp_SetLastError
0x18000f077  lea     rcx, aUpdateprinterr_3; "UpdatePrinterRegUser"
0x18000f07e  call    cs:__imp_OutputDebugStringA
0x18000f084  mov     eax, 32h ; '2'
0x18000f089  add     rsp, 38h
0x18000f08d  retn
```
