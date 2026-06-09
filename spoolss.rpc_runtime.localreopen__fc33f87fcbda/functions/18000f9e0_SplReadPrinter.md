# SplReadPrinter

- ea: `0x18000f9e0`
- end: `0x18000fa30`
- name: `SplReadPrinter`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f9e0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fa09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fa09`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000fa1c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000fa1c`

## string_xrefs

- `0x18000fa15`: `SplReadPrinter`

## pseudocode

```c
__int64 SplReadPrinter()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 51))();
  SetLastError(0x32u);
  OutputDebugStringA("SplReadPrinter");
  return 0;
}

```

## disassembly

```asm
0x18000f9e0  sub     rsp, 28h
0x18000f9e4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000f9eb  jnz     short loc_18000FA04
0x18000f9ed  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000f9f4  mov     rax, [rax+198h]
0x18000f9fb  add     rsp, 28h
0x18000f9ff  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa04  mov     ecx, 32h ; '2'; dwErrCode
0x18000fa09  call    cs:__imp_SetLastError
0x18000fa10  nop     dword ptr [rax+rax+00h]
0x18000fa15  lea     rcx, aSplreadprinter_0; "SplReadPrinter"
0x18000fa1c  call    cs:__imp_OutputDebugStringA
0x18000fa23  nop     dword ptr [rax+rax+00h]
0x18000fa28  xor     eax, eax
0x18000fa2a  add     rsp, 28h
0x18000fa2e  retn
```
