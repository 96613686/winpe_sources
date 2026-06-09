# McTemplateK0ppq_EtwWriteTransfer

- ea: `0x140018990`
- end: `0x140018a0b`
- name: `McTemplateK0ppq_EtwWriteTransfer`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001977c`
- `0x1400199e8`

## callees

- `0x1400052a8`
- `0x140040a30`

## pseudocode

```c
NTSTATUS McTemplateK0ppq_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-50h] BYREF
  va_list v5; // [rsp+40h] [rbp-40h]
  __int64 v6; // [rsp+48h] [rbp-38h]
  va_list v7; // [rsp+50h] [rbp-30h]
  __int64 v8; // [rsp+58h] [rbp-28h]
  va_list v9; // [rsp+60h] [rbp-20h]
  __int64 v10; // [rsp+68h] [rbp-18h]
  __int64 v11; // [rsp+A8h] [rbp+28h] BYREF
  va_list va; // [rsp+A8h] [rbp+28h]
  __int64 v13; // [rsp+B0h] [rbp+30h] BYREF
  va_list va1; // [rsp+B0h] [rbp+30h]
  va_list va2; // [rsp+B8h] [rbp+38h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v13 = va_arg(va2, _QWORD);
  v6 = 8;
  va_copy(v5, va);
  v8 = 8;
  va_copy(v7, va1);
  v10 = 4;
  va_copy(v9, va2);
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)USBVideo_FilterIrp_Completed, a3, 4u, &v4);
}

```

## disassembly

```asm
0x140018990  mov     [rsp-8+arg_18], r9
0x140018995  push    rbp
0x140018996  mov     rbp, rsp
0x140018999  sub     rsp, 80h
0x1400189a0  mov     rax, cs:__security_cookie
0x1400189a7  xor     rax, rsp
0x1400189aa  mov     [rbp+var_10], rax
0x1400189ae  lea     rax, [rbp+arg_18]
0x1400189b2  mov     [rbp+var_38], 8
0x1400189ba  mov     [rbp+var_40], rax
0x1400189be  lea     rdx, USBVideo_FilterIrp_Completed
0x1400189c5  lea     rax, [rbp+arg_20]
0x1400189c9  mov     [rbp+var_28], 8
0x1400189d1  mov     [rbp+var_30], rax
0x1400189d5  mov     r9d, 4
0x1400189db  lea     rax, [rbp+arg_28]
0x1400189df  mov     [rbp+var_18], r9
0x1400189e3  mov     [rbp+var_20], rax
0x1400189e7  lea     rax, [rbp+var_50]
0x1400189eb  mov     [rsp+80h+var_60], rax
0x1400189f0  call    McGenEventWrite_EtwWriteTransfer
0x1400189f5  mov     rcx, [rbp+var_10]
0x1400189f9  xor     rcx, rsp; StackCookie
0x1400189fc  call    __security_check_cookie
0x140018a01  add     rsp, 80h
0x140018a08  pop     rbp
0x140018a09  retn
```
