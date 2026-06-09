# ReplyOpenPrinter

- ea: `0x18000ed60`
- end: `0x18000edb8`
- name: `ReplyOpenPrinter`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ed60`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ed91`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000eda4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000eda4`

## string_xrefs

- `0x18000ed9d`: `ReplyOpenPrinter`

## pseudocode

```c
__int64 __fastcall ReplyOpenPrinter(__int64 a1)
{
  if ( !g_bSandbox )
    return (*((__int64 (__fastcall **)(__int64))g_pSpoolSvForwards + 83))(a1);
  SetLastError(0x32u);
  OutputDebugStringA("ReplyOpenPrinter");
  return 0;
}

```

## disassembly

```asm
0x18000ed60  sub     rsp, 38h
0x18000ed64  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000ed6b  jnz     short loc_18000ED8C
0x18000ed6d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000ed74  mov     r10, [rsp+38h+arg_20]
0x18000ed79  mov     [rsp+38h+var_18], r10
0x18000ed7e  mov     rax, [rax+298h]
0x18000ed85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed8a  jmp     short loc_18000EDB2
0x18000ed8c  mov     ecx, 32h ; '2'; dwErrCode
0x18000ed91  call    cs:__imp_SetLastError
0x18000ed98  nop     dword ptr [rax+rax+00h]
0x18000ed9d  lea     rcx, aReplyopenprint_0; "ReplyOpenPrinter"
0x18000eda4  call    cs:__imp_OutputDebugStringA
0x18000edab  nop     dword ptr [rax+rax+00h]
0x18000edb0  xor     eax, eax
0x18000edb2  add     rsp, 38h
0x18000edb6  retn
```
