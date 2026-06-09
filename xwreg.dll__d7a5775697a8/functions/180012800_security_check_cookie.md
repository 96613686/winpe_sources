# __security_check_cookie

- ea: `0x180012800`
- end: `0x18001281e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000275c`
- `0x1800028ac`
- `0x1800033ac`
- `0x180004d18`
- `0x180005168`
- `0x18000527c`
- `0x1800053f0`
- `0x1800055a0`
- `0x180005e5c`
- `0x1800060fc`
- `0x180006374`
- `0x180007860`
- `0x180007b28`
- `0x1800085ac`
- `0x180008b4c`
- `0x1800095c0`
- `0x1800099b4`
- `0x18000a168`
- `0x18000a768`
- `0x18000af74`
- `0x18000b114`
- `0x18000b4b8`
- `0x18000bac8`
- `0x18000c240`
- `0x18000c428`
- `0x18000c5c8`
- `0x18000ca6c`
- `0x18000d070`
- `0x18000d858`
- `0x18000daac`
- `0x18000ded4`
- `0x18000e140`
- `0x18000e40c`
- `0x18000e61c`
- `0x18000e8bc`
- `0x18000ebc0`
- `0x18000ee04`
- `0x18000f010`
- `0x18000f238`
- `0x18000f484`
- `0x18000f7c4`
- `0x18000fa80`
- `0x1800102e0`
- `0x180010400`
- `0x180010a54`
- `0x180010dcc`
- `0x180010ff4`
- `0x1800123e0`

## callees

- `0x180002090`
- `0x180012800`

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
0x180012800  cmp     rcx, cs:__security_cookie
0x180012807  jnz     short ReportFailure
0x180012809  rol     rcx, 10h
0x18001280d  test    cx, 0FFFFh
0x180012812  jnz     short RestoreRcx
0x180012814  retn
0x180012815  ror     rcx, 10h
0x180012819  jmp     __report_gsfailure
```
