# UpdatePrinterRegAllEx

- ea: `0x1800025a0`
- end: `0x180002602`
- name: `UpdatePrinterRegAllEx`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800025a0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025df`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800025f6`

## string_xrefs

- `0x1800025eb`: `UpdatePrinterRegAllEx`

## pseudocode

```c
void __fastcall UpdatePrinterRegAllEx(__int64 a1, __int64 a2)
{
  if ( g_bSandbox )
  {
    SetLastError(0x32u);
    OutputDebugStringA("UpdatePrinterRegAllEx");
  }
  else
  {
    (*((void (__fastcall **)(__int64, __int64))g_pSpoolSvForwards + 133))(a1, a2);
  }
}

```

## disassembly

```asm
0x1800025a0  sub     rsp, 48h
0x1800025a4  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x1800025ab  jnz     short loc_1800025DA
0x1800025ad  mov     r10, [rsp+48h+arg_28]
0x1800025b2  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x1800025b9  mov     [rsp+48h+var_20], r10
0x1800025be  mov     r10d, [rsp+48h+arg_20]
0x1800025c3  mov     [rsp+48h+var_28], r10d
0x1800025c8  mov     rax, [rax+428h]
0x1800025cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d4  add     rsp, 48h
0x1800025d8  retn
0x1800025da  mov     ecx, 32h ; '2'; dwErrCode
0x1800025df  call    cs:__imp_SetLastError
0x1800025e6  nop     dword ptr [rax+rax+00h]
0x1800025eb  lea     rcx, aUpdateprinterr_4; "UpdatePrinterRegAllEx"
0x1800025f2  add     rsp, 48h
0x1800025f6  jmp     cs:__imp_OutputDebugStringA
```
