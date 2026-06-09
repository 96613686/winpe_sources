# __security_check_cookie

- ea: `0x18002a590`
- end: `0x18002a5ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `85`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000131c`
- `0x180001614`
- `0x180001968`
- `0x1800019d8`
- `0x180001a68`
- `0x180006d30`
- `0x1800075a0`
- `0x180007fb0`
- `0x180008230`
- `0x18000f298`
- `0x18000faf0`
- `0x18000fd44`
- `0x18000fe8c`
- `0x18000ffc4`
- `0x18001009c`
- `0x1800110d0`
- `0x1800119f8`
- `0x1800120bc`
- `0x1800121e4`
- `0x1800134b4`
- `0x18001357c`
- `0x180013b44`
- `0x18001400c`
- `0x180014cd4`
- `0x1800153d0`
- `0x1800156e8`
- `0x180016438`
- `0x180016770`
- `0x180016f54`
- `0x180017694`
- `0x180017f30`
- `0x1800190a4`
- `0x180019a88`
- `0x180019f9c`
- `0x18001b538`
- `0x18001be6c`
- `0x18001c044`
- `0x18001cfc0`
- `0x18001d5f8`
- `0x18001ead8`
- `0x18001ec20`
- `0x18001ecf8`
- `0x18001edf0`
- `0x18001ef44`
- `0x18001f620`
- `0x18001f950`
- `0x18001fcb0`
- `0x1800200d0`
- `0x18002089c`

## callees

- `0x18001e4f0`
- `0x18002a590`

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
0x18002a590  cmp     rcx, cs:__security_cookie
0x18002a597  jnz     short ReportFailure
0x18002a599  rol     rcx, 10h
0x18002a59d  test    cx, 0FFFFh
0x18002a5a2  jnz     short RestoreRcx
0x18002a5a4  retn
0x18002a5a5  ror     rcx, 10h
0x18002a5a9  jmp     __report_gsfailure
```
