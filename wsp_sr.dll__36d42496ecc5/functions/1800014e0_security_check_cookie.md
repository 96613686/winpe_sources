# __security_check_cookie

- ea: `0x1800014e0`
- end: `0x1800014fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `253`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002010`
- `0x180002290`
- `0x180002840`
- `0x1800038dc`
- `0x180005488`
- `0x180005cdc`
- `0x180005db8`
- `0x180006004`
- `0x1800061a0`
- `0x180006320`
- `0x180006a08`
- `0x180006b10`
- `0x180006c3c`
- `0x180006d44`
- `0x180006e70`
- `0x180006f78`
- `0x1800070a4`
- `0x1800071ac`
- `0x180007fe4`
- `0x180008088`
- `0x180008140`
- `0x1800081e8`
- `0x1800083f4`
- `0x180008668`
- `0x180008948`
- `0x180008a04`
- `0x180008fb0`
- `0x18000934c`
- `0x180009554`
- `0x180009844`
- `0x18000999c`
- `0x180009a88`
- `0x180009c48`
- `0x180009df4`
- `0x180009f9c`
- `0x18000a16c`
- `0x18000a354`
- `0x18000a508`
- `0x18000a6a8`
- `0x18000a89c`
- `0x18000aa28`
- `0x18000abc4`
- `0x18000ad64`
- `0x18000aec8`
- `0x18000b174`
- `0x18000b328`
- `0x18000b48c`
- `0x18000b98c`
- `0x18000bec0`
- `0x18000c0a8`

## callees

- `0x1800014e0`
- `0x180001510`

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
0x1800014e0  cmp     rcx, cs:__security_cookie
0x1800014e7  jnz     short ReportFailure
0x1800014e9  rol     rcx, 10h
0x1800014ed  test    cx, 0FFFFh
0x1800014f2  jnz     short RestoreRcx
0x1800014f4  retn
0x1800014f5  ror     rcx, 10h; StackCookie
0x1800014f9  jmp     __report_gsfailure
```
