# __security_check_cookie

- ea: `0x180022190`
- end: `0x1800221ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `72`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001090`
- `0x1800012d0`
- `0x180001440`
- `0x1800014e0`
- `0x180001580`
- `0x180001600`
- `0x1800016b0`
- `0x180001730`
- `0x1800017c0`
- `0x180001850`
- `0x1800018f0`
- `0x1800019a0`
- `0x180001a60`
- `0x180001ae0`
- `0x180001b70`
- `0x180001cd0`
- `0x180001d90`
- `0x180001e50`
- `0x180001ef0`
- `0x180002130`
- `0x180002780`
- `0x180003670`
- `0x180003ca4`
- `0x180004290`
- `0x1800049c0`
- `0x180006548`
- `0x18000765c`
- `0x180008180`
- `0x18000996c`
- `0x18000a170`
- `0x18000a3e8`
- `0x18000a820`
- `0x18000ab30`
- `0x18000b1f0`
- `0x18000b610`
- `0x18000bbe0`
- `0x18000f1a0`
- `0x180010380`
- `0x1800104e0`
- `0x180012094`
- `0x1800122c4`
- `0x180013a68`
- `0x180014a78`
- `0x1800159dc`
- `0x180015d84`
- `0x18001628c`
- `0x180016824`
- `0x180016b70`
- `0x180016eb0`
- `0x1800172d0`

## callees

- `0x180018770`
- `0x180022190`

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
0x180022190  cmp     rcx, cs:__security_cookie
0x180022197  jnz     short loc_1800221A9
0x180022199  rol     rcx, 10h
0x18002219d  test    cx, 0FFFFh
0x1800221a2  jnz     short loc_1800221A5
0x1800221a4  retn
0x1800221a5  ror     rcx, 10h
0x1800221a9  jmp     __report_gsfailure
```
