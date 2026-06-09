# __security_check_cookie

- ea: `0x14000f7e0`
- end: `0x14000f7fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `267`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012e0`
- `0x1400013b4`
- `0x140001478`
- `0x14000172c`
- `0x140001a24`
- `0x140001c48`
- `0x140001c90`
- `0x140001d20`
- `0x140001dcc`
- `0x140001e80`
- `0x140002350`
- `0x140002820`
- `0x140002f80`
- `0x140003000`
- `0x1400030e0`
- `0x1400031b0`
- `0x140003290`
- `0x140003360`
- `0x140003450`
- `0x140003640`
- `0x140003710`
- `0x1400038e0`
- `0x140004140`
- `0x1400049a0`
- `0x140005a40`
- `0x140005da0`
- `0x140006100`
- `0x140006460`
- `0x140006820`
- `0x140006ab0`
- `0x140007fe0`
- `0x1400080f8`
- `0x14000845c`
- `0x1400086a0`
- `0x140008a90`
- `0x140008f10`
- `0x140009080`
- `0x140009610`
- `0x140009994`
- `0x140009bfc`
- `0x14000ad00`
- `0x14000bd68`
- `0x14000bf18`
- `0x14000c384`
- `0x14000c9d4`
- `0x14000ccf8`
- `0x14000cfe0`
- `0x14000d448`
- `0x14000d770`

## callees

- `0x14000f7e0`
- `0x140010420`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x14000f7e0  cmp     rcx, cs:__security_cookie
0x14000f7e7  jnz     short loc_14000F7F9
0x14000f7e9  rol     rcx, 10h
0x14000f7ed  test    cx, 0FFFFh
0x14000f7f2  jnz     short loc_14000F7F5
0x14000f7f4  retn
0x14000f7f5  ror     rcx, 10h; StackCookie
0x14000f7f9  jmp     __report_gsfailure
```
