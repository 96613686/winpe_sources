# McTemplateU0dpq_EventWriteTransfer

- ea: `0x18000bb64`
- end: `0x18000bbd8`
- name: `McTemplateU0dpq_EventWriteTransfer`
- size: `116`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d330`
- `0x18000d630`
- `0x18000dde0`

## callees

- `0x1800061d0`
- `0x180006620`

## pseudocode

```c
ULONG McTemplateU0dpq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-50h] BYREF
  int *v5; // [rsp+40h] [rbp-40h]
  __int64 v6; // [rsp+48h] [rbp-38h]
  va_list v7; // [rsp+50h] [rbp-30h]
  __int64 v8; // [rsp+58h] [rbp-28h]
  va_list v9; // [rsp+60h] [rbp-20h]
  __int64 v10; // [rsp+68h] [rbp-18h]
  int v11; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v12; // [rsp+A8h] [rbp+28h] BYREF
  va_list va; // [rsp+A8h] [rbp+28h]
  va_list va1; // [rsp+B0h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v12 = va_arg(va1, _QWORD);
  v11 = a3;
  v8 = 8;
  v6 = 4;
  v5 = &v11;
  va_copy(v7, va);
  va_copy(v9, va1);
  v10 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 4u, &v4);
}

```

## disassembly

```asm
0x18000bb64  mov     [rsp-8+arg_18], r9
0x18000bb69  mov     [rsp-8+arg_10], r8d
0x18000bb6e  push    rbp
0x18000bb6f  mov     rbp, rsp
0x18000bb72  sub     rsp, 80h
0x18000bb79  mov     rax, cs:__security_cookie
0x18000bb80  xor     rax, rsp
0x18000bb83  mov     [rbp+var_10], rax
0x18000bb87  mov     r9d, 4
0x18000bb8d  mov     [rbp+var_28], 8
0x18000bb95  lea     rax, [rbp+arg_10]
0x18000bb99  mov     [rbp+var_38], r9
0x18000bb9d  mov     [rbp+var_40], rax
0x18000bba1  lea     rax, [rbp+arg_18]
0x18000bba5  mov     [rbp+var_30], rax
0x18000bba9  lea     rax, [rbp+arg_20]
0x18000bbad  mov     [rbp+var_20], rax
0x18000bbb1  lea     rax, [rbp+var_50]
0x18000bbb5  mov     [rsp+80h+var_60], rax
0x18000bbba  mov     [rbp+var_18], r9
0x18000bbbe  call    McGenEventWrite_EventWriteTransfer
0x18000bbc3  mov     rcx, [rbp+var_10]
0x18000bbc7  xor     rcx, rsp; StackCookie
0x18000bbca  call    __security_check_cookie
0x18000bbcf  add     rsp, 80h
0x18000bbd6  pop     rbp
0x18000bbd7  retn
```
