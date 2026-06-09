# __security_check_cookie

- ea: `0x1800015d0`
- end: `0x1800015ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `248`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002350`
- `0x180003530`
- `0x180003a68`
- `0x180003e90`
- `0x180004800`
- `0x180004a80`
- `0x180004d90`
- `0x180005200`
- `0x180005350`
- `0x180005540`
- `0x1800057f0`
- `0x180005c80`
- `0x180005d80`
- `0x180005fd0`
- `0x1800062f0`
- `0x180006420`
- `0x180006630`
- `0x1800067d0`
- `0x1800069c0`
- `0x180006c90`
- `0x180006e80`
- `0x180006ff8`
- `0x180007150`
- `0x180007310`
- `0x1800075e0`
- `0x180007a20`
- `0x180007b70`
- `0x180007ca0`
- `0x1800089d0`
- `0x180008b00`
- `0x180008bb0`
- `0x180008d60`
- `0x180008e60`
- `0x180008f70`
- `0x180009070`
- `0x180009180`
- `0x1800094c0`
- `0x180009770`
- `0x180009854`
- `0x180009960`
- `0x180009b10`
- `0x180009fb0`
- `0x18000a3f0`
- `0x18000aab4`
- `0x18000ac64`
- `0x18000b670`
- `0x18000bbc0`
- `0x18000c5d0`
- `0x18000ca20`
- `0x18000cb20`

## callees

- `0x1800015d0`
- `0x1800019a0`

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
0x1800015d0  cmp     rcx, cs:__security_cookie
0x1800015d7  jnz     short ReportFailure
0x1800015d9  rol     rcx, 10h
0x1800015dd  test    cx, 0FFFFh
0x1800015e2  jnz     short RestoreRcx
0x1800015e4  retn
0x1800015e5  ror     rcx, 10h; StackCookie
0x1800015e9  jmp     __report_gsfailure
```
