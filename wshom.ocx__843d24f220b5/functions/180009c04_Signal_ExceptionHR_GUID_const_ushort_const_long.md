# Signal_ExceptionHR(_GUID const &,ushort const *,long,...)

- ea: `0x180009c04`
- end: `0x180009c38`
- name: `?Signal_ExceptionHR@@YAJAEBU_GUID@@PEBGJZZ`
- size: `52`
- prototype: `__int64(const struct _GUID *, const unsigned __int16 *, int, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b90`
- `0x180008570`
- `0x180008600`
- `0x18000d070`

## callees

- `0x180005358`

## pseudocode

```c
__int64 Signal_ExceptionHR(const struct _GUID *a1, const unsigned __int16 *a2, signed int a3, ...)
{
  va_list v4; // [rsp+30h] [rbp-18h] BYREF
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  va_copy(v4, va);
  return Signal_Exception((__int64)a1, (__int64)a2, a3, 0, &v4);
}

```

## disassembly

```asm
0x180009c04  mov     r11, rsp
0x180009c07  mov     [r11+18h], r8d
0x180009c0b  mov     [r11+20h], r9
0x180009c0f  sub     rsp, 48h
0x180009c13  lea     rax, [r11+20h]
0x180009c17  mov     qword ptr [r11-18h], 0
0x180009c1f  mov     [r11-18h], rax
0x180009c23  xor     r9d, r9d
0x180009c26  lea     rax, [r11-18h]
0x180009c2a  mov     [r11-28h], rax
0x180009c2e  call    Signal_Exception
0x180009c33  add     rsp, 48h
0x180009c37  retn
```
