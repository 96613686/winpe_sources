# __security_check_cookie

- ea: `0x18001d370`
- end: `0x18001d38e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x180003318`
- `0x1800035b4`
- `0x18000383c`
- `0x180003be0`
- `0x1800041f4`
- `0x18000456c`
- `0x180005710`
- `0x180005b00`
- `0x180006604`
- `0x1800069b8`
- `0x1800070b0`
- `0x18000729c`
- `0x180007780`
- `0x18000907c`
- `0x180009148`
- `0x180009600`
- `0x180009b58`
- `0x18000a0e4`
- `0x18000a440`
- `0x18000b144`
- `0x18000b6b4`
- `0x18000c7d8`
- `0x18000ca38`
- `0x18000cbfc`
- `0x18001890c`
- `0x180019c14`
- `0x18001a148`
- `0x18001a6b0`
- `0x18001b1b0`
- `0x18001b430`
- `0x18001bcbc`
- `0x18001cd64`
- `0x18001cfa4`
- `0x18001d2a0`

## callees

- `0x180002280`
- `0x18001d370`

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
0x18001d370  cmp     rcx, cs:__security_cookie
0x18001d377  jnz     short ReportFailure
0x18001d379  rol     rcx, 10h
0x18001d37d  test    cx, 0FFFFh
0x18001d382  jnz     short RestoreRcx
0x18001d384  retn
0x18001d385  ror     rcx, 10h
0x18001d389  jmp     __report_gsfailure
```
