# FormatRegistryKeyForPrinter

- ea: `0x18000d680`
- end: `0x18000d6c3`
- name: `FormatRegistryKeyForPrinter`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000d680`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d6b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d6b6`

## string_xrefs

- `0x18000d6af`: `FormatRegistryKeyForPrinter`

## pseudocode

```c
__int64 FormatRegistryKeyForPrinter()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 123))();
  SetLastError(0x32u);
  OutputDebugStringA("FormatRegistryKeyForPrinter");
  return 0;
}

```

## disassembly

```asm
0x18000d680  sub     rsp, 28h
0x18000d684  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000d68b  jnz     short loc_18000D6A4
0x18000d68d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000d694  mov     rax, [rax+3D8h]
0x18000d69b  add     rsp, 28h
0x18000d69f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6a4  mov     ecx, 32h ; '2'; dwErrCode
0x18000d6a9  call    cs:__imp_SetLastError
0x18000d6af  lea     rcx, aFormatregistry_0; "FormatRegistryKeyForPrinter"
0x18000d6b6  call    cs:__imp_OutputDebugStringA
0x18000d6bc  xor     eax, eax
0x18000d6be  add     rsp, 28h
0x18000d6c2  retn
```
