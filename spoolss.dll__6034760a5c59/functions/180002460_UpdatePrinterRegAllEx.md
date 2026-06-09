# UpdatePrinterRegAllEx

- ea: `0x180002460`
- end: `0x1800024b6`
- name: `UpdatePrinterRegAllEx`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180002460`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000249e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000249e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800024af`

## string_xrefs

- `0x1800024a4`: `UpdatePrinterRegAllEx`

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
0x180002460  sub     rsp, 48h
0x180002464  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000246b  jnz     short loc_180002499
0x18000246d  mov     r10, [rsp+48h+arg_28]
0x180002472  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x180002479  mov     [rsp+48h+var_20], r10
0x18000247e  mov     r10d, [rsp+48h+arg_20]
0x180002483  mov     [rsp+48h+var_28], r10d
0x180002488  mov     rax, [rax+428h]
0x18000248f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002494  add     rsp, 48h
0x180002498  retn
0x180002499  mov     ecx, 32h ; '2'; dwErrCode
0x18000249e  call    cs:__imp_SetLastError
0x1800024a4  lea     rcx, aUpdateprinterr_4; "UpdatePrinterRegAllEx"
0x1800024ab  add     rsp, 48h
0x1800024af  jmp     cs:__imp_OutputDebugStringA
```
