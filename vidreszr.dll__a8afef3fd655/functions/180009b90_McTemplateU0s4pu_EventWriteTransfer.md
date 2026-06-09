# McTemplateU0s4pu_EventWriteTransfer

- ea: `0x180009b90`
- end: `0x180009c01`
- name: `McTemplateU0s4pu_EventWriteTransfer`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ac0`

## callees

- `0x180001dc0`
- `0x180009b30`

## pseudocode

```c
ULONG McTemplateU0s4pu_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-58h] BYREF
  __int64 v5; // [rsp+40h] [rbp-48h]
  __int64 v6; // [rsp+48h] [rbp-40h]
  va_list v7; // [rsp+50h] [rbp-38h]
  __int64 v8; // [rsp+58h] [rbp-30h]
  va_list v9; // [rsp+60h] [rbp-28h]
  __int64 v10; // [rsp+68h] [rbp-20h]
  __int64 v11; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  va_list va1; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, _QWORD);
  v5 = a3;
  va_copy(v7, va);
  v6 = 4;
  va_copy(v9, va1);
  v8 = 8;
  v10 = 1;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 4u, &v4);
}

```

## disassembly

```asm
0x180009b90  mov     r11, rsp
0x180009b93  mov     [r11+20h], r9
0x180009b97  sub     rsp, 88h
0x180009b9e  mov     rax, cs:__security_cookie
0x180009ba5  xor     rax, rsp
0x180009ba8  mov     [rsp+88h+var_18], rax
0x180009bad  lea     rax, [r11+20h]
0x180009bb1  mov     [r11-48h], r8
0x180009bb5  mov     [r11-38h], rax
0x180009bb9  mov     r9d, 4
0x180009bbf  lea     rax, [r11+28h]
0x180009bc3  mov     qword ptr [r11-40h], 4
0x180009bcb  mov     [r11-28h], rax
0x180009bcf  lea     rax, [r11-58h]
0x180009bd3  mov     [r11-68h], rax
0x180009bd7  mov     qword ptr [r11-30h], 8
0x180009bdf  mov     qword ptr [r11-20h], 1
0x180009be7  call    McGenEventWrite_EventWriteTransfer
0x180009bec  mov     rcx, [rsp+88h+var_18]
0x180009bf1  xor     rcx, rsp; StackCookie
0x180009bf4  call    __security_check_cookie
0x180009bf9  add     rsp, 88h
0x180009c00  retn
```
