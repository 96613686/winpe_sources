# __security_check_cookie

- ea: `0x180001ec0`
- end: `0x180001ede`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `219`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010b0`
- `0x1800010f8`
- `0x18000115c`
- `0x180001218`
- `0x180001284`
- `0x1800013dc`
- `0x1800016d0`
- `0x180002fac`
- `0x180003248`
- `0x1800038c8`
- `0x180003a90`
- `0x180003e24`
- `0x1800041d8`
- `0x180005878`
- `0x180005dc0`
- `0x180007a78`
- `0x180007bcc`
- `0x1800081c0`
- `0x180008324`
- `0x1800085b8`
- `0x180008c3c`
- `0x180008d28`
- `0x180009154`
- `0x1800093c8`
- `0x180009834`
- `0x180009d24`
- `0x180009ea4`
- `0x18000a028`
- `0x18000a110`
- `0x18000a1b8`
- `0x18000a46c`
- `0x18000a81c`
- `0x18000acb4`
- `0x18000b85c`
- `0x18000c404`
- `0x18000c61c`
- `0x18000f53c`
- `0x18000f6a0`
- `0x18000fafc`
- `0x18000fbe8`
- `0x18000fcb0`
- `0x18000fd68`
- `0x18000ff18`
- `0x18001001c`
- `0x180010298`
- `0x1800105b4`
- `0x1800108e8`
- `0x180010a08`
- `0x180010b0c`
- `0x180010cdc`

## callees

- `0x180001ec0`
- `0x1800023a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180001ec0  cmp     rcx, cs:__security_cookie
0x180001ec7  jnz     short ReportFailure
0x180001ec9  rol     rcx, 10h
0x180001ecd  test    cx, 0FFFFh
0x180001ed2  jnz     short RestoreRcx
0x180001ed4  retn
0x180001ed5  ror     rcx, 10h; StackCookie
0x180001ed9  jmp     __report_gsfailure
```
