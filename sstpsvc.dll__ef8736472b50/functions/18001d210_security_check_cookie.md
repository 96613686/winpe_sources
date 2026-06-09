# __security_check_cookie

- ea: `0x18001d210`
- end: `0x18001d22e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `91`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800012b0`
- `0x180001b40`
- `0x180001fe0`
- `0x180002320`
- `0x180002aac`
- `0x180003010`
- `0x180003620`
- `0x180003bc0`
- `0x180004950`
- `0x180004bdc`
- `0x180004d10`
- `0x180004fb0`
- `0x180005110`
- `0x18000530c`
- `0x1800056e0`
- `0x1800059f0`
- `0x180005e30`
- `0x180006960`
- `0x180006c60`
- `0x180007110`
- `0x1800071cc`
- `0x1800079d4`
- `0x180007ae4`
- `0x1800080dc`
- `0x18000823c`
- `0x180008b90`
- `0x180009c3c`
- `0x18000a300`
- `0x18000a59c`
- `0x18000a710`
- `0x18000aa44`
- `0x18000abe0`
- `0x18000accc`
- `0x18000adb8`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000bd24`
- `0x18000c4c4`
- `0x18000c768`
- `0x18000ca68`
- `0x18000d2ec`
- `0x18000d444`
- `0x18000d730`
- `0x18000d978`
- `0x18000da7c`
- `0x18000dd70`
- `0x18000df08`
- `0x18000ebd0`
- `0x18000f6e0`
- `0x18000fa00`

## callees

- `0x1800095e0`
- `0x18001d210`

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
0x18001d210  cmp     rcx, cs:__security_cookie
0x18001d217  jnz     short ReportFailure
0x18001d219  rol     rcx, 10h
0x18001d21d  test    cx, 0FFFFh
0x18001d222  jnz     short RestoreRcx
0x18001d224  retn
0x18001d225  ror     rcx, 10h
0x18001d229  jmp     __report_gsfailure
```
