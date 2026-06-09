# Signal_Exception(_GUID const &,ushort const *,uint,...)

- ea: `0x180005d20`
- end: `0x180005d57`
- name: `?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ`
- size: `55`
- prototype: `__int64(const struct _GUID *, const unsigned __int16 *, unsigned int, ...)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800013f0`
- `0x1800023e0`
- `0x1800038c0`
- `0x180003af0`
- `0x180005980`
- `0x180007690`
- `0x180008930`
- `0x18000b840`
- `0x18000b8a0`
- `0x18000cc80`
- `0x18000d070`
- `0x18000db60`
- `0x18000dcc0`

## callees

- `0x180005358`

## pseudocode

```c
__int64 Signal_Exception(const struct _GUID *a1, const unsigned __int16 *a2, unsigned int a3, ...)
{
  va_list v4; // [rsp+30h] [rbp-18h] BYREF
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  va_copy(v4, va);
  return Signal_Exception((__int64)a1, (__int64)a2, 0, a3, &v4);
}

```

## disassembly

```asm
0x180005d20  mov     r11, rsp
0x180005d23  mov     [r11+18h], r8d
0x180005d27  mov     [r11+20h], r9
0x180005d2b  sub     rsp, 48h
0x180005d2f  lea     rax, [r11+20h]
0x180005d33  mov     qword ptr [r11-18h], 0
0x180005d3b  mov     [r11-18h], rax
0x180005d3f  mov     r9d, r8d
0x180005d42  lea     rax, [r11-18h]
0x180005d46  xor     r8d, r8d
0x180005d49  mov     [r11-28h], rax
0x180005d4d  call    Signal_Exception
0x180005d52  add     rsp, 48h
0x180005d56  retn
```
