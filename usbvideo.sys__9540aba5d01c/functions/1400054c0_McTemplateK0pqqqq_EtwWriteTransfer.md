# McTemplateK0pqqqq_EtwWriteTransfer

- ea: `0x1400054c0`
- end: `0x140005561`
- name: `McTemplateK0pqqqq_EtwWriteTransfer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001fdf0`

## callees

- `0x1400052a8`
- `0x140040a30`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0pqqqq_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        char a7,
        char a8)
{
  __int64 v9; // [rsp+30h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v11; // [rsp+50h] [rbp-29h]
  __int64 v12; // [rsp+58h] [rbp-21h]
  char *v13; // [rsp+60h] [rbp-19h]
  __int64 v14; // [rsp+68h] [rbp-11h]
  char *v15; // [rsp+70h] [rbp-9h]
  __int64 v16; // [rsp+78h] [rbp-1h]
  char *v17; // [rsp+80h] [rbp+7h]
  __int64 v18; // [rsp+88h] [rbp+Fh]
  char *v19; // [rsp+90h] [rbp+17h]
  __int64 v20; // [rsp+98h] [rbp+1Fh]

  v12 = 8;
  v9 = 0;
  v11 = &v9;
  v13 = &a5;
  v15 = &a6;
  v14 = 4;
  v17 = &a7;
  v16 = 4;
  v19 = &a8;
  v18 = 4;
  v20 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)USBVideo_PowerIrpCompletion_Start, a3, 6u, &v10);
}

```

## disassembly

```asm
0x1400054c0  push    rbp
0x1400054c2  lea     rbp, [rsp-37h]
0x1400054c7  sub     rsp, 0B0h
0x1400054ce  mov     rax, cs:__security_cookie
0x1400054d5  xor     rax, rsp
0x1400054d8  mov     [rbp+37h+var_10], rax
0x1400054dc  xor     edx, edx
0x1400054de  mov     [rbp+37h+var_58], 8
0x1400054e6  lea     rax, [rbp+37h+var_80]
0x1400054ea  mov     [rbp+37h+var_80], rdx
0x1400054ee  mov     [rbp+37h+var_60], rax
0x1400054f2  lea     rax, [rbp+37h+arg_20]
0x1400054f6  mov     [rbp+37h+var_50], rax
0x1400054fa  lea     rax, [rbp+37h+arg_28]
0x1400054fe  mov     [rbp+37h+var_40], rax
0x140005502  lea     r9d, [rdx+6]
0x140005506  lea     rax, [rbp+37h+arg_30]
0x14000550a  mov     [rbp+37h+var_48], 4
0x140005512  mov     [rbp+37h+var_30], rax
0x140005516  lea     rdx, USBVideo_PowerIrpCompletion_Start
0x14000551d  lea     rax, [rbp+37h+arg_38]
0x140005521  mov     [rbp+37h+var_38], 4
0x140005529  mov     [rbp+37h+var_20], rax
0x14000552d  lea     rax, [rbp+37h+var_70]
0x140005531  mov     [rsp+0B0h+var_90], rax
0x140005536  mov     [rbp+37h+var_28], 4
0x14000553e  mov     [rbp+37h+var_18], 4
0x140005546  call    McGenEventWrite_EtwWriteTransfer
0x14000554b  mov     rcx, [rbp+37h+var_10]
0x14000554f  xor     rcx, rsp; StackCookie
0x140005552  call    __security_check_cookie
0x140005557  add     rsp, 0B0h
0x14000555e  pop     rbp
0x14000555f  retn
```
