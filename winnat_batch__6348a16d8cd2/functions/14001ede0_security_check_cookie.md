# __security_check_cookie

- ea: `0x14001ede0`
- end: `0x14001edfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `91`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400011e0`
- `0x1400020e0`
- `0x140003830`
- `0x140004094`
- `0x140004648`
- `0x140004ed0`
- `0x1400052d0`
- `0x140006f04`
- `0x140007610`
- `0x140007bb0`
- `0x140008df0`
- `0x1400091e0`
- `0x1400093f0`
- `0x14000975c`
- `0x140009b04`
- `0x14000a9d0`
- `0x14000ae68`
- `0x14000b220`
- `0x14000bdf0`
- `0x14000c328`
- `0x14000cad4`
- `0x14000d730`
- `0x14000d7f8`
- `0x14000e1dc`
- `0x14000e3c0`
- `0x14000e488`
- `0x14000e510`
- `0x14000e680`
- `0x14000e768`
- `0x14000e980`
- `0x14000eb50`
- `0x14000ee40`
- `0x14000f428`
- `0x14000fc88`
- `0x140010ac4`
- `0x1400113c0`
- `0x140011cfc`
- `0x140012478`
- `0x140012674`
- `0x1400127b4`
- `0x140012b9c`
- `0x140013b40`
- `0x140013c08`
- `0x140013d70`
- `0x140013ef0`
- `0x140013fbc`
- `0x14001407c`
- `0x140014220`
- `0x14001448c`
- `0x140014d00`

## callees

- `0x14000d7e0`
- `0x14001ede0`

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
0x14001ede0  cmp     rcx, cs:__security_cookie
0x14001ede7  jnz     short ReportFailure
0x14001ede9  rol     rcx, 10h
0x14001eded  test    cx, 0FFFFh
0x14001edf2  jnz     short RestoreRcx
0x14001edf4  retn
0x14001edf5  ror     rcx, 10h; StackCookie
0x14001edf9  jmp     __report_gsfailure
```
