# SplReadPrinter

- ea: `0x18000ea60`
- end: `0x18000eaa3`
- name: `SplReadPrinter`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ea60`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea89`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ea96`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ea96`

## string_xrefs

- `0x18000ea8f`: `SplReadPrinter`

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
0x18000ea60  sub     rsp, 28h
0x18000ea64  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000ea6b  jnz     short loc_18000EA84
0x18000ea6d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000ea74  mov     rax, [rax+198h]
0x18000ea7b  add     rsp, 28h
0x18000ea7f  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea84  mov     ecx, 32h ; '2'; dwErrCode
0x18000ea89  call    cs:__imp_SetLastError
0x18000ea8f  lea     rcx, aSplreadprinter_0; "SplReadPrinter"
0x18000ea96  call    cs:__imp_OutputDebugStringA
0x18000ea9c  xor     eax, eax
0x18000ea9e  add     rsp, 28h
0x18000eaa2  retn
```
