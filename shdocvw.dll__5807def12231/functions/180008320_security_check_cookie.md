# __security_check_cookie

- ea: `0x180008320`
- end: `0x18000833e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `120`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001478`
- `0x18000163c`
- `0x180001a24`
- `0x1800020e0`
- `0x1800027a0`
- `0x180002e30`
- `0x1800030e0`
- `0x180003810`
- `0x180004060`
- `0x180004190`
- `0x1800043e0`
- `0x180004a48`
- `0x180004d30`
- `0x180005b0c`
- `0x1800060a8`
- `0x180006c3c`
- `0x180006de0`
- `0x180008a50`
- `0x180009ce4`
- `0x180009de0`
- `0x18000a368`
- `0x18000a500`
- `0x18000a8d4`
- `0x18000ab90`
- `0x18000c15c`
- `0x18000c680`
- `0x18000cca4`
- `0x18000ce90`
- `0x18000f81c`
- `0x180010c18`
- `0x180010f64`
- `0x180011148`
- `0x180011974`
- `0x1800120d4`
- `0x180012b74`
- `0x180012f6c`
- `0x180013004`
- `0x180013488`
- `0x18001360c`
- `0x180014554`
- `0x180014fc0`
- `0x180015bc4`
- `0x180015cbc`
- `0x180016f60`
- `0x180017170`
- `0x180017264`
- `0x180017c98`
- `0x180017d88`

## callees

- `0x180008320`
- `0x180008750`

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
0x180008320  cmp     rcx, cs:__security_cookie
0x180008327  jnz     short ReportFailure
0x180008329  rol     rcx, 10h
0x18000832d  test    cx, 0FFFFh
0x180008332  jnz     short RestoreRcx
0x180008334  retn
0x180008335  ror     rcx, 10h; StackCookie
0x180008339  jmp     __report_gsfailure
```
