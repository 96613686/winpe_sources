# __security_check_cookie

- ea: `0x180001dc0`
- end: `0x180001dde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `57`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001270`
- `0x180001694`
- `0x180002eec`
- `0x180002fe8`
- `0x180003638`
- `0x180003824`
- `0x180003bd4`
- `0x180003f2c`
- `0x180004200`
- `0x180004834`
- `0x180004a70`
- `0x18000552c`
- `0x1800056a8`
- `0x180005b80`
- `0x180005de4`
- `0x180005eb4`
- `0x180005f4c`
- `0x180006174`
- `0x1800069e4`
- `0x180006aa0`
- `0x180006c10`
- `0x180006cb0`
- `0x180006f80`
- `0x18000710c`
- `0x1800071b0`
- `0x18000725c`
- `0x180007344`
- `0x1800075f0`
- `0x180007680`
- `0x180007720`
- `0x1800079cc`
- `0x180007a80`
- `0x180007b58`
- `0x180007d90`
- `0x180007e60`
- `0x180007f04`
- `0x1800082a0`
- `0x180008328`
- `0x1800083cc`
- `0x1800086b0`
- `0x18000885c`
- `0x180008a48`
- `0x180008bd8`
- `0x180009270`
- `0x1800093ec`
- `0x18000955c`
- `0x180009778`
- `0x180009810`
- `0x180009eb8`

## callees

- `0x180001dc0`
- `0x180002680`

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
0x180001dc0  cmp     rcx, cs:__security_cookie
0x180001dc7  jnz     short ReportFailure
0x180001dc9  rol     rcx, 10h
0x180001dcd  test    cx, 0FFFFh
0x180001dd2  jnz     short RestoreRcx
0x180001dd4  retn
0x180001dd5  ror     rcx, 10h; StackCookie
0x180001dd9  jmp     __report_gsfailure
```
