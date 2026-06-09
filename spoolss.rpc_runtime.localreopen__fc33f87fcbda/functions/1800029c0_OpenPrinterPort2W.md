# OpenPrinterPort2W

- ea: `0x1800029c0`
- end: `0x180002a0e`
- name: `OpenPrinterPort2W`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800029c0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800029e7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029fa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029fa`

## string_xrefs

- `0x1800029f3`: `OpenPrinterPort2W`

## pseudocode

```c
__int64 OpenPrinterPort2W()
{
  if ( !g_bSandbox )
    return (*((__int64 (**)(void))g_pSpoolSvForwards + 31))();
  SetLastError(0x32u);
  OutputDebugStringA("OpenPrinterPort2W");
  return 0;
}

```

## disassembly

```asm
0x1800029c0  sub     rsp, 38h
0x1800029c4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800029cb  jnz     short loc_1800029E2
0x1800029cd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800029d4  mov     rax, [rax+0F8h]
0x1800029db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029e0  jmp     short loc_180002A08
0x1800029e2  mov     ecx, 32h ; '2'; dwErrCode
0x1800029e7  call    cs:__imp_SetLastError
0x1800029ee  nop     dword ptr [rax+rax+00h]
0x1800029f3  lea     rcx, aOpenprinterpor_1; "OpenPrinterPort2W"
0x1800029fa  call    cs:__imp_OutputDebugStringA
0x180002a01  nop     dword ptr [rax+rax+00h]
0x180002a06  xor     eax, eax
0x180002a08  add     rsp, 38h
0x180002a0c  retn
```
