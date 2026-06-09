# __security_check_cookie

- ea: `0x18001fe50`
- end: `0x18001fe6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `75`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002f14`
- `0x180003f08`
- `0x180004434`
- `0x180004b80`
- `0x1800052cc`
- `0x180005ad0`
- `0x18000840c`
- `0x1800084e0`
- `0x1800085a0`
- `0x180008828`
- `0x180009170`
- `0x180009a10`
- `0x18000a938`
- `0x18000ada0`
- `0x18000b260`
- `0x18000b300`
- `0x18000bae0`
- `0x18000c2d8`
- `0x18000c724`
- `0x18000d03c`
- `0x18000d15c`
- `0x18000d480`
- `0x18000d830`
- `0x18000d940`
- `0x18000da2c`
- `0x18000dc4c`
- `0x18000e2f8`
- `0x18000e81c`
- `0x18000ec24`
- `0x18000ef44`
- `0x18000f110`
- `0x18000f1f8`
- `0x18000f3d0`
- `0x18000f5f0`
- `0x18000f670`
- `0x18000f7b0`
- `0x18000fb2c`
- `0x18000fc00`
- `0x18000fc80`
- `0x18000fd88`
- `0x180010320`
- `0x1800103b8`
- `0x1800120f8`
- `0x1800121fc`
- `0x18001259c`
- `0x180012f20`
- `0x18001351c`
- `0x180014310`
- `0x1800145cc`
- `0x18001483c`

## callees

- `0x180001bc0`
- `0x18001fe50`

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
0x18001fe50  cmp     rcx, cs:__security_cookie
0x18001fe57  jnz     short ReportFailure
0x18001fe59  rol     rcx, 10h
0x18001fe5d  test    cx, 0FFFFh
0x18001fe62  jnz     short RestoreRcx
0x18001fe64  retn
0x18001fe65  ror     rcx, 10h
0x18001fe69  jmp     __report_gsfailure
```
