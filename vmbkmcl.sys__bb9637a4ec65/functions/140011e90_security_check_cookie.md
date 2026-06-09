# __security_check_cookie

- ea: `0x140011e90`
- end: `0x140011eae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006ff4`
- `0x140007068`
- `0x140008e78`
- `0x140008ef0`
- `0x140008f90`
- `0x14000a3dc`
- `0x14000b3d8`
- `0x14000e4e0`
- `0x140010490`
- `0x140010d50`
- `0x1400115cc`
- `0x140011d5c`
- `0x14001c008`
- `0x14001c34c`
- `0x14001c758`
- `0x14001cdd4`
- `0x14001df80`
- `0x14001e208`
- `0x14001e370`
- `0x140020378`

## callees

- `0x140006e40`
- `0x140011e90`

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
0x140011e90  cmp     rcx, cs:__security_cookie
0x140011e97  jnz     short ReportFailure
0x140011e99  rol     rcx, 10h
0x140011e9d  test    cx, 0FFFFh
0x140011ea2  jnz     short RestoreRcx
0x140011ea4  retn
0x140011ea5  ror     rcx, 10h; StackCookie
0x140011ea9  jmp     __report_gsfailure
```
