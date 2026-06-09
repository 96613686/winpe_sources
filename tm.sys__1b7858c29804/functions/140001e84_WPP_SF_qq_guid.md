# WPP_SF_qq_guid_

- ea: `0x140001e84`
- end: `0x140001ee3`
- name: `WPP_SF_qq_guid_`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400108c0`
- `0x140016110`
- `0x1400161c0`

## callees

- `0x1400025c0`

## pseudocode

```c
__int64 WPP_SF_qq_guid_(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  __int64 v8; // [rsp+98h] [rbp+30h]
  va_list va2; // [rsp+A0h] [rbp+38h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  v8 = va_arg(va2, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           8,
           v8,
           16,
           0);
}

```

## disassembly

```asm
0x140001e84  mov     r11, rsp
0x140001e87  mov     [r11+20h], r9
0x140001e8b  sub     rsp, 68h
0x140001e8f  mov     r9, [rsp+68h+arg_28]
0x140001e97  mov     r10d, 8
0x140001e9d  mov     rax, cs:pfnWppTraceMessage
0x140001ea4  mov     qword ptr [r11-18h], 0
0x140001eac  mov     qword ptr [r11-20h], 10h
0x140001eb4  mov     [r11-28h], r9
0x140001eb8  lea     r9, [r11+28h]
0x140001ebc  mov     [r11-30h], r10
0x140001ec0  mov     [r11-38h], r9
0x140001ec4  lea     r9, [r11+20h]
0x140001ec8  mov     [r11-40h], r10
0x140001ecc  mov     [r11-48h], r9
0x140001ed0  movzx   r9d, dx
0x140001ed4  lea     edx, [r10+23h]
0x140001ed8  call    _guard_dispatch_icall
0x140001edd  add     rsp, 68h
0x140001ee1  retn
```
