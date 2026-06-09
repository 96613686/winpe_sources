# WPP_SF_qDD

- ea: `0x180014ae0`
- end: `0x180014b3c`
- name: `WPP_SF_qDD`
- size: `92`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e90`
- `0x180003a00`
- `0x18000c850`
- `0x18000d930`
- `0x18000fed0`
- `0x180010170`
- `0x180011ec0`
- `0x180012c30`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014b31`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014b31`

## pseudocode

```c
ULONG WPP_SF_qDD(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  va_list va2; // [rsp+98h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  return TraceMessage(a1, 0x2Bu, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a2, va, 8, va1, 4, va2, 4, 0);
}

```

## disassembly

```asm
0x180014ae0  mov     r11, rsp
0x180014ae3  mov     [r11+20h], r9
0x180014ae7  sub     rsp, 68h
0x180014aeb  mov     qword ptr [r11-18h], 0
0x180014af3  lea     rax, [r11+30h]
0x180014af7  mov     r8d, 4
0x180014afd  movzx   r9d, dx; MessageNumber
0x180014b01  mov     [r11-20h], r8
0x180014b05  mov     edx, 2Bh ; '+'; MessageFlags
0x180014b0a  mov     [r11-28h], rax
0x180014b0e  lea     rax, [r11+28h]
0x180014b12  mov     [r11-30h], r8
0x180014b16  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids; MessageGuid
0x180014b1d  mov     [r11-38h], rax
0x180014b21  lea     rax, [r11+20h]
0x180014b25  mov     qword ptr [r11-40h], 8
0x180014b2d  mov     [r11-48h], rax
0x180014b31  call    cs:__imp_TraceMessage
0x180014b37  add     rsp, 68h
0x180014b3b  retn
```
