# McTemplateK0pqq_EtwWriteTransfer

- ea: `0x14000f304`
- end: `0x14000f374`
- name: `McTemplateK0pqq_EtwWriteTransfer`
- size: `112`
- prototype: ``
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ca70`
- `0x14000d120`
- `0x14000d580`
- `0x14000e110`
- `0x14001444c`
- `0x140014710`
- `0x1400148bc`
- `0x140014a68`
- `0x1400153c0`
- `0x140015610`
- `0x1400165c0`
- `0x1400286e0`
- `0x14007ab24`
- `0x14007b5a8`
- `0x14007b784`
- `0x14007b9c0`
- `0x14007bc60`
- `0x14007be94`
- `0x14007c208`
- `0x14007c64c`
- `0x14007ca5c`
- `0x14007cf54`
- `0x14007d144`
- `0x14007d6cc`
- `0x14008c9fc`

## callees

- `0x1400019f8`
- `0x140045530`

## pseudocode

```c
NTSTATUS McTemplateK0pqq_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const GUID *a3, ...)
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
  v8 = 4;
  va_copy(v5, va);
  va_copy(v7, va1);
  va_copy(v9, va2);
  v10 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 4u, &v4);
}

```

## disassembly

```asm
0x14000f304  mov     [rsp-8+arg_18], r9
0x14000f309  push    rbp
0x14000f30a  mov     rbp, rsp
0x14000f30d  sub     rsp, 80h
0x14000f314  mov     rax, cs:__security_cookie
0x14000f31b  xor     rax, rsp
0x14000f31e  mov     [rbp+var_10], rax
0x14000f322  mov     r9d, 4
0x14000f328  mov     [rbp+var_38], 8
0x14000f330  lea     rax, [rbp+arg_18]
0x14000f334  mov     [rbp+var_28], r9
0x14000f338  mov     [rbp+var_40], rax
0x14000f33c  lea     rax, [rbp+arg_20]
0x14000f340  mov     [rbp+var_30], rax
0x14000f344  lea     rax, [rbp+arg_28]
0x14000f348  mov     [rbp+var_20], rax
0x14000f34c  lea     rax, [rbp+var_50]
0x14000f350  mov     [rsp+80h+var_60], rax
0x14000f355  mov     [rbp+var_18], r9
0x14000f359  call    McGenEventWrite_EtwWriteTransfer
0x14000f35e  mov     rcx, [rbp+var_10]
0x14000f362  xor     rcx, rsp; StackCookie
0x14000f365  call    __security_check_cookie
0x14000f36a  add     rsp, 80h
0x14000f371  pop     rbp
0x14000f372  retn
```
