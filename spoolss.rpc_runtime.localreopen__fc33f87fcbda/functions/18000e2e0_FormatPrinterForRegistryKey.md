# FormatPrinterForRegistryKey

- ea: `0x18000e2e0`
- end: `0x18000e330`
- name: `FormatPrinterForRegistryKey`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000e2e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e309`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e309`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e31c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e31c`

## string_xrefs

- `0x18000e315`: `FormatPrinterForRegistryKey`

## pseudocode

```c
__int64 FormatPrinterForRegistryKey()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 122))();
  SetLastError(0x32u);
  OutputDebugStringA("FormatPrinterForRegistryKey");
  return 0;
}

```

## disassembly

```asm
0x18000e2e0  sub     rsp, 28h
0x18000e2e4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000e2eb  jnz     short loc_18000E304
0x18000e2ed  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e2f4  mov     rax, [rax+3D0h]
0x18000e2fb  add     rsp, 28h
0x18000e2ff  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000e304  mov     ecx, 32h ; '2'; dwErrCode
0x18000e309  call    cs:__imp_SetLastError
0x18000e310  nop     dword ptr [rax+rax+00h]
0x18000e315  lea     rcx, aFormatprinterf_0; "FormatPrinterForRegistryKey"
0x18000e31c  call    cs:__imp_OutputDebugStringA
0x18000e323  nop     dword ptr [rax+rax+00h]
0x18000e328  xor     eax, eax
0x18000e32a  add     rsp, 28h
0x18000e32e  retn
```
