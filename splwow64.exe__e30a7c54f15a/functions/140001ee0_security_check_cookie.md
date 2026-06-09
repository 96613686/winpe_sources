# __security_check_cookie

- ea: `0x140001ee0`
- end: `0x140001efe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x1400016dc`
- `0x1400030bc`
- `0x140003358`
- `0x1400036fc`
- `0x140003ad0`
- `0x140004374`
- `0x1400046ec`
- `0x14000557c`
- `0x140005fa4`
- `0x140006f98`
- `0x1400073ac`
- `0x14000805c`
- `0x1400085d8`
- `0x1400086e0`
- `0x140009214`
- `0x14000a5b8`
- `0x14000a6c4`
- `0x14000b058`
- `0x14000c42c`
- `0x14000c718`
- `0x14000cfd0`
- `0x14000f1e4`
- `0x14000f9cc`
- `0x14000fae0`
- `0x140011bb0`
- `0x140012a9c`
- `0x140012e84`
- `0x140014a90`
- `0x140014c34`
- `0x140015464`

## callees

- `0x140001ee0`
- `0x140002470`

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
0x140001ee0  cmp     rcx, cs:__security_cookie
0x140001ee7  jnz     short loc_140001EF9
0x140001ee9  rol     rcx, 10h
0x140001eed  test    cx, 0FFFFh
0x140001ef2  jnz     short loc_140001EF5
0x140001ef4  retn
0x140001ef5  ror     rcx, 10h; StackCookie
0x140001ef9  jmp     __report_gsfailure
```
