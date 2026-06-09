# __security_check_cookie

- ea: `0x1800032e0`
- end: `0x1800032fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001560`
- `0x180001cb0`
- `0x180001f30`
- `0x180004500`
- `0x180004984`
- `0x180004c30`
- `0x180005414`
- `0x180006700`
- `0x180006ae0`
- `0x180006fdc`
- `0x180007864`
- `0x180007c38`
- `0x1800085a0`
- `0x180008bd8`
- `0x1800096a4`
- `0x18000a370`
- `0x18000a478`
- `0x18000a5e8`
- `0x18000b1d8`
- `0x18000b380`
- `0x18000b5c4`
- `0x18000b750`
- `0x18000c5c4`
- `0x18000d430`
- `0x18000d53c`
- `0x18000dedc`
- `0x18000ef2c`
- `0x18000f16c`
- `0x18000f484`
- `0x18000f76c`
- `0x180010550`
- `0x180014bf4`
- `0x1800153dc`
- `0x180016840`
- `0x180018c10`
- `0x180019c88`
- `0x180019fd8`
- `0x18001b290`
- `0x18001c6b4`
- `0x18001cbbc`
- `0x18001ccf8`
- `0x180020364`
- `0x1800208f8`
- `0x180020ba4`
- `0x180020dc4`
- `0x1800221ec`
- `0x1800227bc`
- `0x1800238cc`

## callees

- `0x1800032e0`
- `0x180003910`

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
0x1800032e0  cmp     rcx, cs:__security_cookie
0x1800032e7  jnz     short ReportFailure
0x1800032e9  rol     rcx, 10h
0x1800032ed  test    cx, 0FFFFh
0x1800032f2  jnz     short RestoreRcx
0x1800032f4  retn
0x1800032f5  ror     rcx, 10h; StackCookie
0x1800032f9  jmp     __report_gsfailure
```
