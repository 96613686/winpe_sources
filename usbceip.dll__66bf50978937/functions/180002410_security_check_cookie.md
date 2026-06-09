# __security_check_cookie

- ea: `0x180002410`
- end: `0x18000242e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010b0`
- `0x18000121c`
- `0x1800012c4`
- `0x180001700`
- `0x1800017ac`
- `0x180001990`
- `0x1800019f0`
- `0x180001ac0`
- `0x180001c1c`
- `0x180001cb0`
- `0x180001dc4`
- `0x180003414`
- `0x180003600`
- `0x180004388`
- `0x180005258`
- `0x1800053e4`
- `0x180005e94`
- `0x180006c28`
- `0x1800072b4`
- `0x1800074fc`
- `0x1800075e4`
- `0x180007754`
- `0x180008290`
- `0x180008730`
- `0x180009260`
- `0x18000a4c8`
- `0x18000a838`
- `0x18000ab84`
- `0x18000af94`
- `0x18000b5c8`
- `0x18000b78c`
- `0x18000be14`
- `0x18000e360`
- `0x18000e640`
- `0x18000e928`
- `0x18000ec18`
- `0x18000edec`
- `0x18000f600`
- `0x18000f74c`
- `0x18000f9ec`
- `0x18000fbf8`
- `0x18000fd50`

## callees

- `0x180002410`
- `0x180002a10`

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
0x180002410  cmp     rcx, cs:__security_cookie
0x180002417  jnz     short ReportFailure
0x180002419  rol     rcx, 10h
0x18000241d  test    cx, 0FFFFh
0x180002422  jnz     short RestoreRcx
0x180002424  retn
0x180002425  ror     rcx, 10h; StackCookie
0x180002429  jmp     __report_gsfailure
```
