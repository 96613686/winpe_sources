# McTemplateK0xqqb16b16qb16q_EtwWriteTransfer

- ea: `0x140016f08`
- end: `0x140016fd3`
- name: `McTemplateK0xqqb16b16qb16q_EtwWriteTransfer`
- size: `203`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400164a8`
- `0x140016760`
- `0x140016af0`
- `0x14003476c`

## callees

- `0x1400095bc`
- `0x14001f320`

## pseudocode

```c
NTSTATUS McTemplateK0xqqb16b16qb16q_EtwWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-81h] BYREF
  va_list v5; // [rsp+40h] [rbp-71h]
  __int64 v6; // [rsp+48h] [rbp-69h]
  va_list v7; // [rsp+50h] [rbp-61h]
  __int64 v8; // [rsp+58h] [rbp-59h]
  va_list v9; // [rsp+60h] [rbp-51h]
  __int64 v10; // [rsp+68h] [rbp-49h]
  __int64 v11; // [rsp+70h] [rbp-41h]
  __int64 v12; // [rsp+78h] [rbp-39h]
  __int64 v13; // [rsp+80h] [rbp-31h]
  __int64 v14; // [rsp+88h] [rbp-29h]
  va_list v15; // [rsp+90h] [rbp-21h]
  __int64 v16; // [rsp+98h] [rbp-19h]
  __int64 v17; // [rsp+A0h] [rbp-11h]
  __int64 v18; // [rsp+A8h] [rbp-9h]
  va_list v19; // [rsp+B0h] [rbp-1h]
  __int64 v20; // [rsp+B8h] [rbp+7h]
  __int64 v21; // [rsp+F8h] [rbp+47h] BYREF
  va_list va; // [rsp+F8h] [rbp+47h]
  __int64 v23; // [rsp+100h] [rbp+4Fh] BYREF
  va_list va1; // [rsp+100h] [rbp+4Fh]
  __int64 v25; // [rsp+108h] [rbp+57h] BYREF
  va_list va2; // [rsp+108h] [rbp+57h]
  __int64 v27; // [rsp+110h] [rbp+5Fh]
  __int64 v28; // [rsp+118h] [rbp+67h]
  __int64 v29; // [rsp+120h] [rbp+6Fh] BYREF
  va_list va3; // [rsp+120h] [rbp+6Fh]
  __int64 v31; // [rsp+128h] [rbp+77h]
  va_list va4; // [rsp+130h] [rbp+7Fh] BYREF

  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v21 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v23 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v25 = va_arg(va3, _QWORD);
  v27 = va_arg(va3, _QWORD);
  v28 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v29 = va_arg(va4, _QWORD);
  v31 = va_arg(va4, _QWORD);
  v6 = 8;
  va_copy(v5, va);
  v8 = 4;
  va_copy(v7, va1);
  va_copy(v9, va2);
  v11 = v27;
  v13 = v28;
  va_copy(v15, va3);
  v17 = v31;
  va_copy(v19, va4);
  v10 = 4;
  v12 = 16;
  v14 = 16;
  v16 = 4;
  v18 = 16;
  v20 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 9u, &v4);
}

```

## disassembly

```asm
0x140016f08  mov     [rsp-8+arg_18], r9
0x140016f0d  push    rbp
0x140016f0e  lea     rbp, [rsp-1Fh]
0x140016f13  sub     rsp, 0D0h
0x140016f1a  mov     rax, cs:__security_cookie
0x140016f21  xor     rax, rsp
0x140016f24  mov     [rbp+1Fh+var_10], rax
0x140016f28  lea     rax, [rbp+1Fh+arg_18]
0x140016f2c  mov     [rbp+1Fh+var_88], 8
0x140016f34  mov     [rbp+1Fh+var_90], rax
0x140016f38  mov     r9d, 9
0x140016f3e  lea     rax, [rbp+1Fh+arg_20]
0x140016f42  mov     [rbp+1Fh+var_78], 4
0x140016f4a  mov     [rbp+1Fh+var_80], rax
0x140016f4e  lea     rax, [rbp+1Fh+arg_28]
0x140016f52  mov     [rbp+1Fh+var_70], rax
0x140016f56  mov     rax, [rbp+1Fh+arg_30]
0x140016f5a  mov     [rbp+1Fh+var_60], rax
0x140016f5e  mov     rax, [rbp+1Fh+arg_38]
0x140016f62  mov     [rbp+1Fh+var_50], rax
0x140016f66  lea     rax, [rbp+1Fh+arg_40]
0x140016f6a  mov     [rbp+1Fh+var_40], rax
0x140016f6e  mov     rax, [rbp+1Fh+arg_48]
0x140016f72  mov     [rbp+1Fh+var_30], rax
0x140016f76  lea     rax, [rbp+1Fh+arg_50]
0x140016f7a  mov     [rbp+1Fh+var_20], rax
0x140016f7e  lea     rax, [rsp+0D0h+var_A0]
0x140016f83  mov     [rsp+0D0h+var_B0], rax
0x140016f88  mov     [rbp+1Fh+var_68], 4
0x140016f90  mov     [rbp+1Fh+var_58], 10h
0x140016f98  mov     [rbp+1Fh+var_48], 10h
0x140016fa0  mov     [rbp+1Fh+var_38], 4
0x140016fa8  mov     [rbp+1Fh+var_28], 10h
0x140016fb0  mov     [rbp+1Fh+var_18], 4
0x140016fb8  call    McGenEventWrite_EtwWriteTransfer
0x140016fbd  mov     rcx, [rbp+1Fh+var_10]
0x140016fc1  xor     rcx, rsp; StackCookie
0x140016fc4  call    __security_check_cookie
0x140016fc9  add     rsp, 0D0h
0x140016fd0  pop     rbp
0x140016fd1  retn
```
