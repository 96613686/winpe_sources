# McTemplateU0dpqq_EventWriteTransfer

- ea: `0x18000bbe0`
- end: `0x18000bc74`
- name: `McTemplateU0dpqq_EventWriteTransfer`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d930`

## callees

- `0x1800061d0`
- `0x180006620`

## pseudocode

```c
ULONG McTemplateU0dpqq_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+38h] [rbp-19h] BYREF
  int *v5; // [rsp+48h] [rbp-9h]
  __int64 v6; // [rsp+50h] [rbp-1h]
  va_list v7; // [rsp+58h] [rbp+7h]
  __int64 v8; // [rsp+60h] [rbp+Fh]
  va_list v9; // [rsp+68h] [rbp+17h]
  __int64 v10; // [rsp+70h] [rbp+1Fh]
  va_list v11; // [rsp+78h] [rbp+27h]
  __int64 v12; // [rsp+80h] [rbp+2Fh]
  int v13; // [rsp+B8h] [rbp+67h] BYREF
  __int64 v14; // [rsp+C0h] [rbp+6Fh] BYREF
  va_list va; // [rsp+C0h] [rbp+6Fh]
  __int64 v16; // [rsp+C8h] [rbp+77h] BYREF
  va_list va1; // [rsp+C8h] [rbp+77h]
  va_list va2; // [rsp+D0h] [rbp+7Fh] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v14 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v16 = va_arg(va2, _QWORD);
  v13 = a3;
  v6 = 4;
  v5 = &v13;
  v8 = 8;
  va_copy(v7, va);
  v10 = 4;
  va_copy(v9, va1);
  va_copy(v11, va2);
  v12 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)SamCreateUser2InDomainExit, a3, 5u, &v4);
}

```

## disassembly

```asm
0x18000bbe0  mov     r11, rsp
0x18000bbe3  mov     [r11+20h], r9
0x18000bbe7  mov     [r11+18h], r8d
0x18000bbeb  push    rbp
0x18000bbec  lea     rbp, [r11-4Fh]
0x18000bbf0  sub     rsp, 90h
0x18000bbf7  mov     rax, cs:__security_cookie
0x18000bbfe  xor     rax, rsp
0x18000bc01  mov     [rbp+47h+var_10], rax
0x18000bc05  lea     rax, [rbp+47h+arg_10]
0x18000bc09  mov     [rbp+47h+var_48], 4
0x18000bc11  mov     [rbp+47h+var_50], rax
0x18000bc15  lea     rdx, SamCreateUser2InDomainExit
0x18000bc1c  lea     rax, [rbp+47h+arg_18]
0x18000bc20  mov     [rbp+47h+var_38], 8
0x18000bc28  mov     [rbp+47h+var_40], rax
0x18000bc2c  mov     r9d, 5
0x18000bc32  lea     rax, [rbp+47h+arg_20]
0x18000bc36  mov     [rbp+47h+var_28], 4
0x18000bc3e  mov     [rbp+47h+var_30], rax
0x18000bc42  lea     rax, [rbp+47h+arg_28]
0x18000bc46  mov     [rbp+47h+var_20], rax
0x18000bc4a  lea     rax, [rbp+47h+var_60]
0x18000bc4e  mov     [r11-78h], rax
0x18000bc52  mov     [rbp+47h+var_18], 4
0x18000bc5a  call    McGenEventWrite_EventWriteTransfer
0x18000bc5f  mov     rcx, [rbp+47h+var_10]
0x18000bc63  xor     rcx, rsp; StackCookie
0x18000bc66  call    __security_check_cookie
0x18000bc6b  add     rsp, 90h
0x18000bc72  pop     rbp
0x18000bc73  retn
```
