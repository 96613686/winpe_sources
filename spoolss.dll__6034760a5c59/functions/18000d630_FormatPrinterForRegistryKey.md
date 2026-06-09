# FormatPrinterForRegistryKey

- ea: `0x18000d630`
- end: `0x18000d673`
- name: `FormatPrinterForRegistryKey`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000d630`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d659`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d659`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d666`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d666`

## string_xrefs

- `0x18000d65f`: `FormatPrinterForRegistryKey`

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
0x18000d630  sub     rsp, 28h
0x18000d634  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d63b  jnz     short loc_18000D654
0x18000d63d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d644  mov     rax, [rax+3D0h]
0x18000d64b  add     rsp, 28h
0x18000d64f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d654  mov     ecx, 32h ; '2'; dwErrCode
0x18000d659  call    cs:__imp_SetLastError
0x18000d65f  lea     rcx, aFormatprinterf_0; "FormatPrinterForRegistryKey"
0x18000d666  call    cs:__imp_OutputDebugStringA
0x18000d66c  xor     eax, eax
0x18000d66e  add     rsp, 28h
0x18000d672  retn
```
