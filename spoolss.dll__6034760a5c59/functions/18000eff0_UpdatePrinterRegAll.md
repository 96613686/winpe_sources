# UpdatePrinterRegAll

- ea: `0x18000eff0`
- end: `0x18000f032`
- name: `UpdatePrinterRegAll`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000eff0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f01a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f01a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000f02b`

## string_xrefs

- `0x18000f020`: `UpdatePrinterRegAll`

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
0x18000eff0  sub     rsp, 38h
0x18000eff4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000effb  jnz     short loc_18000F015
0x18000effd  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000f004  mov     rax, [rax+420h]
0x18000f00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f010  add     rsp, 38h
0x18000f014  retn
0x18000f015  mov     ecx, 32h ; '2'; dwErrCode
0x18000f01a  call    cs:__imp_SetLastError
0x18000f020  lea     rcx, aUpdateprinterr_2; "UpdatePrinterRegAll"
0x18000f027  add     rsp, 38h
0x18000f02b  jmp     cs:__imp_OutputDebugStringA
```
