# __security_check_cookie

- ea: `0x180027510`
- end: `0x18002752e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e7c`
- `0x180004830`
- `0x180004bc4`
- `0x18000525c`
- `0x180006cb4`
- `0x180006d64`
- `0x180007330`
- `0x1800076a4`
- `0x180007c60`
- `0x180008380`
- `0x18000859c`
- `0x180008d8c`
- `0x180008e78`
- `0x1800096f8`
- `0x180009f2c`
- `0x18000a288`
- `0x18000a6b8`
- `0x18000a8f0`
- `0x18000af7c`
- `0x18000b484`
- `0x18000b860`
- `0x18000c1a0`
- `0x18000c850`
- `0x18000d1c0`
- `0x1800104fc`
- `0x180010e44`
- `0x180011264`
- `0x180011868`
- `0x180011914`
- `0x180012704`
- `0x1800128dc`
- `0x180012e78`
- `0x180013b28`
- `0x180013fb4`
- `0x1800142c8`
- `0x18001524c`
- `0x180017598`
- `0x180017888`
- `0x180017e48`
- `0x180018760`
- `0x18001a4a8`
- `0x18001a85c`
- `0x18001a940`
- `0x18001aa9c`
- `0x18001ae10`
- `0x18001bd30`
- `0x18001c830`
- `0x18001cb20`
- `0x18001d920`
- `0x18001dc70`

## callees

- `0x1800016c0`
- `0x180027510`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180027510  cmp     rcx, cs:__security_cookie
0x180027517  jnz     short ReportFailure
0x180027519  rol     rcx, 10h
0x18002751d  test    cx, 0FFFFh
0x180027522  jnz     short RestoreRcx
0x180027524  retn
0x180027525  ror     rcx, 10h
0x180027529  jmp     __report_gsfailure
```
