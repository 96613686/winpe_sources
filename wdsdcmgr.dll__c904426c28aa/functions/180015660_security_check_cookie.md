# __security_check_cookie

- ea: `0x180015660`
- end: `0x18001567e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e14`
- `0x1800026ac`
- `0x18000294c`
- `0x1800036dc`
- `0x1800040ac`
- `0x1800042f4`
- `0x1800070a4`
- `0x1800071e4`
- `0x180007ba4`
- `0x180007f90`
- `0x180009164`
- `0x1800092a8`
- `0x18000c2d0`
- `0x18000c4e0`
- `0x18000c774`
- `0x18000d540`
- `0x18000d7bc`
- `0x18000d954`
- `0x18000f470`
- `0x18000fe40`
- `0x1800102e0`
- `0x180010a00`
- `0x180010da0`
- `0x180011df0`
- `0x180012090`
- `0x180012f34`
- `0x180014010`
- `0x180014404`
- `0x1800144e4`
- `0x18001465c`
- `0x180015c0c`

## callees

- `0x180015660`
- `0x1800157f0`

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
0x180015660  cmp     rcx, cs:__security_cookie
0x180015667  jnz     short ReportFailure
0x180015669  rol     rcx, 10h
0x18001566d  test    cx, 0FFFFh
0x180015672  jnz     short RestoreRcx
0x180015674  retn
0x180015675  ror     rcx, 10h
0x180015679  jmp     __report_gsfailure
```
