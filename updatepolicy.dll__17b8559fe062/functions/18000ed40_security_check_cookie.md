# __security_check_cookie

- ea: `0x18000ed40`
- end: `0x18000ed5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `55`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001098`
- `0x180001418`
- `0x1800015ac`
- `0x1800017f8`
- `0x180001aa0`
- `0x180002358`
- `0x18000297c`
- `0x180002a14`
- `0x180002bd8`
- `0x180002db0`
- `0x180003128`
- `0x180003984`
- `0x180004348`
- `0x1800049c4`
- `0x180004ea4`
- `0x180005320`
- `0x180005744`
- `0x180005b8c`
- `0x180005d80`
- `0x180005e40`
- `0x180006008`
- `0x180006560`
- `0x1800068b4`
- `0x180006b80`
- `0x180006bec`
- `0x180007ec4`
- `0x1800086a0`
- `0x180008d40`
- `0x180008e70`
- `0x180008fe4`
- `0x180009a28`
- `0x180009e48`
- `0x18000a180`
- `0x18000c690`
- `0x18000c808`
- `0x18000c9d8`
- `0x18000cc24`
- `0x18000cdd4`
- `0x18000d338`
- `0x18000d538`
- `0x18000d6f8`
- `0x18000d910`
- `0x18000db64`
- `0x18000dbe0`
- `0x18000de80`
- `0x18000e3ac`
- `0x18000e488`
- `0x180010468`
- `0x180010574`

## callees

- `0x18000ed40`
- `0x18000f590`

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
0x18000ed40  cmp     rcx, cs:__security_cookie
0x18000ed47  jnz     short ReportFailure
0x18000ed49  rol     rcx, 10h
0x18000ed4d  test    cx, 0FFFFh
0x18000ed52  jnz     short RestoreRcx
0x18000ed54  retn
0x18000ed55  ror     rcx, 10h
0x18000ed59  jmp     __report_gsfailure
```
