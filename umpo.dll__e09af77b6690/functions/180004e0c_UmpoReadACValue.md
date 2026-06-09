# UmpoReadACValue

- ea: `0x180004e0c`
- end: `0x180004e52`
- name: `UmpoReadACValue`
- size: `70`
- prototype: `__int64 __fastcall(UUID *, UUID *, UUID *, _QWORD *, __int64, DWORD *, __int64, DWORD *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012a0`
- `0x180003070`
- `0x180003cb0`
- `0x180004420`
- `0x180004e60`
- `0x18000681c`
- `0x180008640`
- `0x18000cb4c`
- `0x1800165a8`

## callees

- `0x1800059c0`

## pseudocode

```c
__int64 __fastcall UmpoReadACValue(
        UUID *a1,
        UUID *a2,
        UUID *a3,
        _QWORD *a4,
        __int64 a5,
        DWORD *a6,
        __int64 a7,
        DWORD *a8)
{
  return UmpoInternalReadxCValue(a1, a2, a3, a4, a5, 1, a6, a7, a8);
}

```

## disassembly

```asm
0x180004e0c  mov     r11, rsp
0x180004e0f  sub     rsp, 58h
0x180004e13  mov     rax, [rsp+58h+arg_38]
0x180004e1b  mov     [r11-18h], rax
0x180004e1f  mov     rax, [rsp+58h+arg_30]
0x180004e27  mov     [r11-20h], rax
0x180004e2b  mov     rax, [rsp+58h+arg_28]
0x180004e33  mov     [r11-28h], rax
0x180004e37  mov     rax, [rsp+58h+arg_20]
0x180004e3f  mov     [rsp+58h+var_30], 1
0x180004e44  mov     [r11-38h], rax
0x180004e48  call    UmpoInternalReadxCValue
0x180004e4d  add     rsp, 58h
0x180004e51  retn
```
