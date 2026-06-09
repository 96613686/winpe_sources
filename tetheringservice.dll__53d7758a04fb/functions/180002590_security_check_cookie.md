# __security_check_cookie

- ea: `0x180002590`
- end: `0x1800025ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `100`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010a8`
- `0x180001174`
- `0x180001428`
- `0x180001720`
- `0x18000185c`
- `0x180003fb0`
- `0x180004244`
- `0x180005188`
- `0x18000555c`
- `0x180005958`
- `0x1800064a4`
- `0x180006820`
- `0x1800075e4`
- `0x1800076f0`
- `0x180008108`
- `0x18000993c`
- `0x18000a440`
- `0x18000a568`
- `0x18000a838`
- `0x18000ab48`
- `0x18000c5fc`
- `0x18000d134`
- `0x18000d9dc`
- `0x18000dea0`
- `0x18000dfd8`
- `0x18000e528`
- `0x18000ee3c`
- `0x1800102b0`
- `0x1800107fc`
- `0x1800110d4`
- `0x180012818`
- `0x180012a90`
- `0x1800130c8`
- `0x1800132c8`
- `0x180013604`
- `0x180013ca0`
- `0x180014280`
- `0x180014c8c`
- `0x180015430`
- `0x180015cdc`
- `0x1800162dc`
- `0x18001670c`
- `0x180016da0`
- `0x18001877c`
- `0x18001935c`
- `0x180019b4c`
- `0x18001a3ec`
- `0x18001a800`
- `0x18001ad34`
- `0x18001afb4`

## callees

- `0x180002590`
- `0x180002bf0`

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
0x180002590  cmp     rcx, cs:__security_cookie
0x180002597  jnz     short ReportFailure
0x180002599  rol     rcx, 10h
0x18000259d  test    cx, 0FFFFh
0x1800025a2  jnz     short RestoreRcx
0x1800025a4  retn
0x1800025a5  ror     rcx, 10h; StackCookie
0x1800025a9  jmp     __report_gsfailure
```
