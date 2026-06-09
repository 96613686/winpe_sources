# __security_check_cookie

- ea: `0x1800014e0`
- end: `0x1800014fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `253`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002040`
- `0x1800022c0`
- `0x180002870`
- `0x180003818`
- `0x1800054b4`
- `0x180005d1c`
- `0x180005df8`
- `0x180006044`
- `0x1800061e0`
- `0x180006360`
- `0x180006ac0`
- `0x180006bcc`
- `0x180006cf8`
- `0x180006e04`
- `0x180006f30`
- `0x18000703c`
- `0x180007168`
- `0x180007274`
- `0x180008120`
- `0x1800081c4`
- `0x18000827c`
- `0x180008324`
- `0x180008540`
- `0x1800087cc`
- `0x180008ad4`
- `0x180008b90`
- `0x18000916c`
- `0x18000950c`
- `0x180009714`
- `0x180009994`
- `0x180009aec`
- `0x180009bd8`
- `0x180009d9c`
- `0x180009f4c`
- `0x18000a0f4`
- `0x18000a2c4`
- `0x18000a4b0`
- `0x18000a664`
- `0x18000a804`
- `0x18000aa00`
- `0x18000ab90`
- `0x18000ad2c`
- `0x18000aecc`
- `0x18000b030`
- `0x18000b2dc`
- `0x18000b494`
- `0x18000b5f8`
- `0x18000bab8`
- `0x18000bf54`
- `0x18000c13c`

## callees

- `0x1800014e0`
- `0x180001510`

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
0x1800014e0  cmp     rcx, cs:__security_cookie
0x1800014e7  jnz     short ReportFailure
0x1800014e9  rol     rcx, 10h
0x1800014ed  test    cx, 0FFFFh
0x1800014f2  jnz     short RestoreRcx
0x1800014f4  retn
0x1800014f5  ror     rcx, 10h; StackCookie
0x1800014f9  jmp     __report_gsfailure
```
