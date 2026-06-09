# __security_check_cookie

- ea: `0x180010070`
- end: `0x18001008e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `84`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012a0`
- `0x180001580`
- `0x180001980`
- `0x180001d24`
- `0x180002288`
- `0x180002420`
- `0x180002530`
- `0x1800027d4`
- `0x180002bc0`
- `0x1800037b0`
- `0x180003a00`
- `0x180003cb0`
- `0x180004380`
- `0x180004420`
- `0x180004830`
- `0x180004c48`
- `0x180005480`
- `0x180005cb4`
- `0x1800061d0`
- `0x18000681c`
- `0x180007254`
- `0x180007440`
- `0x180007790`
- `0x180007ee8`
- `0x180008044`
- `0x180008510`
- `0x180008978`
- `0x180008be0`
- `0x180008dd0`
- `0x180008e68`
- `0x180008fe8`
- `0x18000909c`
- `0x180009198`
- `0x180009684`
- `0x180009b50`
- `0x180009f14`
- `0x18000a030`
- `0x18000a990`
- `0x18000b020`
- `0x18000b7b0`
- `0x18000c34c`
- `0x18000c658`
- `0x18000c9f4`
- `0x18000cb4c`
- `0x18000d080`
- `0x18000d2f4`
- `0x18000d9f0`
- `0x18000e0c0`
- `0x18000e750`

## callees

- `0x180010070`
- `0x1800100a0`

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
0x180010070  cmp     rcx, cs:__security_cookie
0x180010077  jnz     short ReportFailure
0x180010079  rol     rcx, 10h
0x18001007d  test    cx, 0FFFFh
0x180010082  jnz     short RestoreRcx
0x180010084  retn
0x180010085  ror     rcx, 10h; StackCookie
0x180010089  jmp     __report_gsfailure
```
