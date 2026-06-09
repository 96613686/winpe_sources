# ReplyOpenPrinter

- ea: `0x18000df70`
- end: `0x18000dfbb`
- name: `ReplyOpenPrinter`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000df70`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dfa1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dfa1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dfae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000dfae`

## string_xrefs

- `0x18000dfa7`: `ReplyOpenPrinter`

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
0x18000df70  sub     rsp, 38h
0x18000df74  cmp     cs:?g_bSandbox@@3_NA, 0; bool g_bSandbox
0x18000df7b  jnz     short loc_18000DF9C
0x18000df7d  mov     rax, cs:?g_pSpoolSvForwards@@3PEAU_ForwardedSpoolSvFunctions@@EA; _ForwardedSpoolSvFunctions * g_pSpoolSvForwards
0x18000df84  mov     r10, [rsp+38h+arg_20]
0x18000df89  mov     [rsp+38h+var_18], r10
0x18000df8e  mov     rax, [rax+298h]
0x18000df95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df9a  jmp     short loc_18000DFB6
0x18000df9c  mov     ecx, 32h ; '2'; dwErrCode
0x18000dfa1  call    cs:__imp_SetLastError
0x18000dfa7  lea     rcx, aReplyopenprint_0; "ReplyOpenPrinter"
0x18000dfae  call    cs:__imp_OutputDebugStringA
0x18000dfb4  xor     eax, eax
0x18000dfb6  add     rsp, 38h
0x18000dfba  retn
```
