# __security_check_cookie

- ea: `0x18001f980`
- end: `0x18001f99e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `91`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027d8`
- `0x180002cb0`
- `0x180002dd0`
- `0x180003730`
- `0x180003a20`
- `0x180004280`
- `0x180004300`
- `0x180004920`
- `0x180004b50`
- `0x1800052d0`
- `0x180005530`
- `0x180007a34`
- `0x1800080a4`
- `0x180008230`
- `0x1800084c0`
- `0x180008710`
- `0x180009118`
- `0x1800094a8`
- `0x180009e20`
- `0x18000a820`
- `0x18000aa60`
- `0x18000ac20`
- `0x18000aef0`
- `0x18000b440`
- `0x18000c560`
- `0x18000cf90`
- `0x18000d9d0`
- `0x180011850`
- `0x180012100`
- `0x180012620`
- `0x180012800`
- `0x180012d80`
- `0x180012ed0`
- `0x180013020`
- `0x180013140`
- `0x180013260`
- `0x180013390`
- `0x1800134c0`
- `0x1800136d0`
- `0x1800137e0`
- `0x180013930`
- `0x180013b00`
- `0x180014200`
- `0x180014580`
- `0x180014970`
- `0x180014bfc`
- `0x180014dd8`
- `0x1800151ec`
- `0x1800155fc`
- `0x1800158cc`

## callees

- `0x180001520`
- `0x18001f980`

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
0x18001f980  cmp     rcx, cs:__security_cookie
0x18001f987  jnz     short ReportFailure
0x18001f989  rol     rcx, 10h
0x18001f98d  test    cx, 0FFFFh
0x18001f992  jnz     short RestoreRcx
0x18001f994  retn
0x18001f995  ror     rcx, 10h
0x18001f999  jmp     __report_gsfailure
```
