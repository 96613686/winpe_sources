# __security_check_cookie

- ea: `0x180005730`
- end: `0x18000574e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a40`
- `0x1800025c0`
- `0x180003930`
- `0x180004060`
- `0x180004270`
- `0x180004ed0`
- `0x18000648c`
- `0x180006aac`
- `0x1800076cc`
- `0x1800083d0`
- `0x1800085a8`
- `0x1800088c0`
- `0x180008be0`
- `0x1800095e4`
- `0x1800096a0`
- `0x18000981c`
- `0x180009890`
- `0x180009934`
- `0x180009f68`
- `0x180009fc0`
- `0x18000a3f8`
- `0x18000ac64`
- `0x18000ada0`
- `0x18000b620`
- `0x18000b780`
- `0x18000b8b0`
- `0x18000b9a8`

## callees

- `0x180005730`
- `0x180005760`

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
0x180005730  cmp     rcx, cs:__security_cookie
0x180005737  jnz     short ReportFailure
0x180005739  rol     rcx, 10h
0x18000573d  test    cx, 0FFFFh
0x180005742  jnz     short RestoreRcx
0x180005744  retn
0x180005745  ror     rcx, 10h; StackCookie
0x180005749  jmp     __report_gsfailure
```
