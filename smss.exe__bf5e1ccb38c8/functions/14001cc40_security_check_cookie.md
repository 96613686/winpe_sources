# __security_check_cookie

- ea: `0x14001cc40`
- end: `0x14001cc5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `92`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010ec`
- `0x140001260`
- `0x140001880`
- `0x140001f60`
- `0x1400027a0`
- `0x140003114`
- `0x140003450`
- `0x1400036d0`
- `0x1400041d0`
- `0x140004610`
- `0x140004ec0`
- `0x1400050a0`
- `0x1400053e0`
- `0x140005f64`
- `0x140006680`
- `0x1400072e0`
- `0x140007420`
- `0x140007700`
- `0x1400078c0`
- `0x140007cb0`
- `0x140008d10`
- `0x140008d90`
- `0x140008e60`
- `0x140009100`
- `0x1400094c0`
- `0x140009930`
- `0x14000a140`
- `0x14000b110`
- `0x14000b514`
- `0x14000b930`
- `0x14000c638`
- `0x14000d4c0`
- `0x14000d608`
- `0x14000da48`
- `0x14000e080`
- `0x14000e2e8`
- `0x14000e4e0`
- `0x14000e7a0`
- `0x14000e858`
- `0x14000e904`
- `0x14000f280`
- `0x14000f3ec`
- `0x14000f4d8`
- `0x14000fed0`
- `0x1400101ec`
- `0x140010344`
- `0x1400108cc`
- `0x140010bb8`
- `0x140010c5c`
- `0x140010dc8`

## callees

- `0x14000ed30`
- `0x14001cc40`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x14001cc40  cmp     rcx, cs:__security_cookie
0x14001cc47  jnz     short loc_14001CC59
0x14001cc49  rol     rcx, 10h
0x14001cc4d  test    cx, 0FFFFh
0x14001cc52  jnz     short loc_14001CC55
0x14001cc54  retn
0x14001cc55  ror     rcx, 10h
0x14001cc59  jmp     __report_gsfailure
```
