# OpenPrinterPortWithClientInfo

- ea: `0x18000e9d0`
- end: `0x18000ea32`
- name: `OpenPrinterPortWithClientInfo`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e9d0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ea1e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ea1e`

## string_xrefs

- `0x18000ea17`: `OpenPrinterPortWithClientInfo`

## pseudocode

```c
__int64 __fastcall OpenPrinterPortWithClientInfo(__int64 a1, __int64 a2)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(__int64, __int64))g_pSpoolSvForwards + 32))(a1, a2);
  SetLastError(0x32u);
  OutputDebugStringA("OpenPrinterPortWithClientInfo");
  return 0;
}

```

## disassembly

```asm
0x18000e9d0  sub     rsp, 48h
0x18000e9d4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000e9db  jnz     short loc_18000EA06
0x18000e9dd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e9e4  mov     r10d, [rsp+48h+arg_28]
0x18000e9e9  mov     [rsp+48h+var_20], r10d
0x18000e9ee  mov     r10, [rsp+48h+arg_20]
0x18000e9f3  mov     rax, [rax+100h]
0x18000e9fa  mov     [rsp+48h+var_28], r10
0x18000e9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea04  jmp     short loc_18000EA2C
0x18000ea06  mov     ecx, 32h ; '2'; dwErrCode
0x18000ea0b  call    cs:__imp_SetLastError
0x18000ea12  nop     dword ptr [rax+rax+00h]
0x18000ea17  lea     rcx, aOpenprinterpor_2; "OpenPrinterPortWithClientInfo"
0x18000ea1e  call    cs:__imp_OutputDebugStringA
0x18000ea25  nop     dword ptr [rax+rax+00h]
0x18000ea2a  xor     eax, eax
0x18000ea2c  add     rsp, 48h
0x18000ea30  retn
```
