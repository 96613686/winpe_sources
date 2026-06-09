# UpdatePrinterRegAll

- ea: `0x180010060`
- end: `0x1800100ae`
- name: `UpdatePrinterRegAll`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180010060`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001008b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001008b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800100a2`

## string_xrefs

- `0x180010097`: `UpdatePrinterRegAll`

## pseudocode

```c
void UpdatePrinterRegAll()
{
  if ( g_bSandbox )
  {
    SetLastError(0x32u);
    OutputDebugStringA("UpdatePrinterRegAll");
  }
  else
  {
    (*((void (**)(void))g_pSpoolSvForwards + 132))();
  }
}

```

## disassembly

```asm
0x180010060  sub     rsp, 38h
0x180010064  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18001006b  jnz     short loc_180010086
0x18001006d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180010074  mov     rax, [rax+420h]
0x18001007b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010080  add     rsp, 38h
0x180010084  retn
0x180010086  mov     ecx, 32h ; '2'; dwErrCode
0x18001008b  call    cs:__imp_SetLastError
0x180010092  nop     dword ptr [rax+rax+00h]
0x180010097  lea     rcx, aUpdateprinterr_2; "UpdatePrinterRegAll"
0x18001009e  add     rsp, 38h
0x1800100a2  jmp     cs:__imp_OutputDebugStringA
```
