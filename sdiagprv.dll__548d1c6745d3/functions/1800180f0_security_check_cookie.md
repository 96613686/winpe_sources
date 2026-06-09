# __security_check_cookie

- ea: `0x1800180f0`
- end: `0x18001810e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180003d30`
- `0x180003dc8`
- `0x180003e60`
- `0x180003f00`
- `0x1800052f4`
- `0x1800053c0`
- `0x180005468`
- `0x1800067c0`
- `0x180006950`
- `0x180006cd0`
- `0x180006fa0`
- `0x1800078d8`
- `0x180007c88`
- `0x180007ce0`
- `0x180007d60`
- `0x180008f00`
- `0x180009604`
- `0x18000ab30`
- `0x18000ad80`
- `0x18000b1f8`
- `0x18000b268`
- `0x18000b324`
- `0x18000b3f8`
- `0x18000b4f8`
- `0x18000b5fc`
- `0x18000d030`
- `0x18000d100`
- `0x180010938`
- `0x180011984`
- `0x180011aa8`
- `0x1800124a8`
- `0x180015ae8`
- `0x180018030`

## callees

- `0x180001830`
- `0x1800180f0`

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
0x1800180f0  cmp     rcx, cs:__security_cookie
0x1800180f7  jnz     short ReportFailure
0x1800180f9  rol     rcx, 10h
0x1800180fd  test    cx, 0FFFFh
0x180018102  jnz     short RestoreRcx
0x180018104  retn
0x180018105  ror     rcx, 10h
0x180018109  jmp     __report_gsfailure
```
