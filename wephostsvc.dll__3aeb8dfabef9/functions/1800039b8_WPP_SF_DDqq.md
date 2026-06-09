# WPP_SF_DDqq

- ea: `0x1800039b8`
- end: `0x180003a1f`
- name: `WPP_SF_DDqq`
- size: `103`
- prototype: `ULONG(TRACEHANDLE, __int64, __int64, int, ...)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800035f0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180003a14`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180003a14`

## pseudocode

```c
ULONG WPP_SF_DDqq(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+98h] [rbp+20h] BYREF
  __int64 v6; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va1; // [rsp+A8h] [rbp+30h]
  va_list va2; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  v5 = a4;
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_3a1233b099da3452b07b65d2eb146164_Traceguids,
           0xCu,
           &v5,
           4,
           va,
           4,
           va1,
           8,
           va2,
           8,
           0);
}

```

## disassembly

```asm
0x1800039b8  mov     r11, rsp
0x1800039bb  mov     [r11+20h], r9d
0x1800039bf  sub     rsp, 78h
0x1800039c3  mov     qword ptr [r11-18h], 0
0x1800039cb  lea     rax, [r11+38h]
0x1800039cf  mov     r9d, 0Ch; MessageNumber
0x1800039d5  lea     r8, WPP_3a1233b099da3452b07b65d2eb146164_Traceguids; MessageGuid
0x1800039dc  lea     edx, [r9-4]
0x1800039e0  mov     [r11-20h], rdx
0x1800039e4  mov     [r11-28h], rax
0x1800039e8  lea     rax, [r11+30h]
0x1800039ec  mov     [r11-30h], rdx
0x1800039f0  lea     edx, [r9-8]
0x1800039f4  mov     [r11-38h], rax
0x1800039f8  lea     rax, [r11+28h]
0x1800039fc  mov     [r11-40h], rdx
0x180003a00  mov     [r11-48h], rax
0x180003a04  lea     rax, [r11+20h]
0x180003a08  mov     [r11-50h], rdx
0x180003a0c  lea     edx, [r9+1Fh]; MessageFlags
0x180003a10  mov     [r11-58h], rax
0x180003a14  call    cs:__imp_TraceMessage
0x180003a1a  add     rsp, 78h
0x180003a1e  retn
```
