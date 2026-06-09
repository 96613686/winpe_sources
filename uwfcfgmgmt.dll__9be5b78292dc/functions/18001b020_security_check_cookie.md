# __security_check_cookie

- ea: `0x18001b020`
- end: `0x18001b03e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `65`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800028f0`
- `0x180002a2c`
- `0x1800030c4`
- `0x180003360`
- `0x1800036bc`
- `0x180003a88`
- `0x180003fd4`
- `0x18000434c`
- `0x18000555c`
- `0x180006c80`
- `0x180007420`
- `0x180007e38`
- `0x180008300`
- `0x1800085b0`
- `0x180008c30`
- `0x1800092a8`
- `0x180009758`
- `0x180009a50`
- `0x180009f38`
- `0x18000a3ac`
- `0x18000a824`
- `0x18000a8c8`
- `0x18000b6b0`
- `0x18000bc90`
- `0x18000d18c`
- `0x18000d690`
- `0x18000d884`
- `0x18000dc40`
- `0x18000def0`
- `0x18000e660`
- `0x18000e96c`
- `0x18000ee48`
- `0x18000f8d4`
- `0x18000fbdc`
- `0x18000fd10`
- `0x180010228`
- `0x1800104ac`
- `0x180010738`
- `0x180010a5c`
- `0x180010d10`
- `0x180010fc0`
- `0x180011130`
- `0x180011490`
- `0x180011738`
- `0x180011870`
- `0x180011e40`
- `0x1800122f0`
- `0x180012430`
- `0x1800129d0`
- `0x180012b00`

## callees

- `0x1800022c0`
- `0x18001b020`

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
0x18001b020  cmp     rcx, cs:__security_cookie
0x18001b027  jnz     short ReportFailure
0x18001b029  rol     rcx, 10h
0x18001b02d  test    cx, 0FFFFh
0x18001b032  jnz     short RestoreRcx
0x18001b034  retn
0x18001b035  ror     rcx, 10h
0x18001b039  jmp     __report_gsfailure
```
