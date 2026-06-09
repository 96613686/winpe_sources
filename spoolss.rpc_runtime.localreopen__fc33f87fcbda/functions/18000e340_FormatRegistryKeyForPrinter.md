# FormatRegistryKeyForPrinter

- ea: `0x18000e340`
- end: `0x18000e390`
- name: `FormatRegistryKeyForPrinter`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000e340`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e369`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e37c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000e37c`

## string_xrefs

- `0x18000e375`: `FormatRegistryKeyForPrinter`

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
0x18000e340  sub     rsp, 28h
0x18000e344  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000e34b  jnz     short loc_18000E364
0x18000e34d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000e354  mov     rax, [rax+3D8h]
0x18000e35b  add     rsp, 28h
0x18000e35f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000e364  mov     ecx, 32h ; '2'; dwErrCode
0x18000e369  call    cs:__imp_SetLastError
0x18000e370  nop     dword ptr [rax+rax+00h]
0x18000e375  lea     rcx, aFormatregistry_0; "FormatRegistryKeyForPrinter"
0x18000e37c  call    cs:__imp_OutputDebugStringA
0x18000e383  nop     dword ptr [rax+rax+00h]
0x18000e388  xor     eax, eax
0x18000e38a  add     rsp, 28h
0x18000e38e  retn
```
