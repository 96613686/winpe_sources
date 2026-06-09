# __security_check_cookie

- ea: `0x140045530`
- end: `0x14004554e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `160`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010ac`
- `0x140001a54`
- `0x140001a98`
- `0x140001b14`
- `0x140001f04`
- `0x140001f94`
- `0x140001ffc`
- `0x140002078`
- `0x140002108`
- `0x140002384`
- `0x140002728`
- `0x14000329c`
- `0x140003394`
- `0x140005abc`
- `0x1400065b0`
- `0x140006644`
- `0x1400066d4`
- `0x1400073f4`
- `0x1400078c8`
- `0x140007e10`
- `0x1400083b4`
- `0x1400098f0`
- `0x14000c2bc`
- `0x14000c84c`
- `0x14000ca70`
- `0x14000cbb4`
- `0x14000d900`
- `0x14000da60`
- `0x14000dcb8`
- `0x14000e110`
- `0x14000e910`
- `0x14000ed20`
- `0x14000f304`
- `0x14000f37c`
- `0x14000fe78`
- `0x14000ff58`
- `0x140010ac0`
- `0x140014710`
- `0x1400148bc`
- `0x140014a68`
- `0x1400153c0`
- `0x140015610`
- `0x1400165c0`
- `0x140018090`
- `0x140018498`
- `0x140018a1c`
- `0x14001a308`
- `0x14001b548`
- `0x14001ba08`
- `0x14001bdc8`

## callees

- `0x1400014e0`
- `0x140045530`

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
0x140045530  cmp     rcx, cs:__security_cookie
0x140045537  jnz     short ReportFailure
0x140045539  rol     rcx, 10h
0x14004553d  test    cx, 0FFFFh
0x140045542  jnz     short RestoreRcx
0x140045544  retn
0x140045545  ror     rcx, 10h; StackCookie
0x140045549  jmp     __report_gsfailure
```
