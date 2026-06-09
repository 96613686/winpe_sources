# McTemplateK0qbr0qbr2qqq_EtwWriteTransfer

- ea: `0x14000e3e8`
- end: `0x14000e4a9`
- name: `McTemplateK0qbr0qbr2qqq_EtwWriteTransfer`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011778`

## callees

- `0x1400095bc`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qbr0qbr2qqq_EtwWriteTransfer(
        REGHANDLE *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        char a8,
        char a9,
        char a10)
{
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-69h] BYREF
  int *v12; // [rsp+40h] [rbp-59h]
  __int64 v13; // [rsp+48h] [rbp-51h]
  __int64 v14; // [rsp+50h] [rbp-49h]
  int v15; // [rsp+58h] [rbp-41h]
  int v16; // [rsp+5Ch] [rbp-3Dh]
  int *v17; // [rsp+60h] [rbp-39h]
  __int64 v18; // [rsp+68h] [rbp-31h]
  __int64 v19; // [rsp+70h] [rbp-29h]
  int v20; // [rsp+78h] [rbp-21h]
  int v21; // [rsp+7Ch] [rbp-1Dh]
  char *v22; // [rsp+80h] [rbp-19h]
  __int64 v23; // [rsp+88h] [rbp-11h]
  char *v24; // [rsp+90h] [rbp-9h]
  __int64 v25; // [rsp+98h] [rbp-1h]
  char *v26; // [rsp+A0h] [rbp+7h]
  __int64 v27; // [rsp+A8h] [rbp+Fh]
  int v28; // [rsp+E8h] [rbp+4Fh] BYREF

  v28 = a4;
  v15 = a4;
  v16 = 0;
  v12 = &v28;
  v14 = a5;
  v21 = 0;
  v17 = &a6;
  v19 = a7;
  v20 = a6;
  v22 = &a8;
  v24 = &a9;
  v26 = &a10;
  v13 = 4;
  v18 = 4;
  v23 = 4;
  v25 = 4;
  v27 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WINNAT_STATIC_BINDING_EVENT, a3, 8u, &v11);
}

```

## disassembly

```asm
0x14000e3e8  mov     [rsp-8+arg_18], r9d
0x14000e3ed  push    rbp
0x14000e3ee  lea     rbp, [rsp-27h]
0x14000e3f3  sub     rsp, 0C0h
0x14000e3fa  mov     rax, cs:__security_cookie
0x14000e401  xor     rax, rsp
0x14000e404  mov     [rbp+27h+var_10], rax
0x14000e408  xor     edx, edx
0x14000e40a  mov     [rbp+27h+var_68], r9d
0x14000e40e  lea     rax, [rbp+27h+arg_18]
0x14000e412  mov     [rbp+27h+var_64], edx
0x14000e415  mov     [rbp+27h+var_80], rax
0x14000e419  mov     rax, [rbp+27h+arg_20]
0x14000e41d  mov     [rbp+27h+var_70], rax
0x14000e421  lea     r9d, [rdx+8]
0x14000e425  lea     rax, [rbp+27h+arg_28]
0x14000e429  mov     [rbp+27h+var_44], edx
0x14000e42c  mov     [rbp+27h+var_60], rax
0x14000e430  lea     rdx, WINNAT_STATIC_BINDING_EVENT
0x14000e437  mov     rax, [rbp+27h+arg_30]
0x14000e43b  mov     [rbp+27h+var_50], rax
0x14000e43f  mov     eax, [rbp+27h+arg_28]
0x14000e442  mov     [rbp+27h+var_48], eax
0x14000e445  lea     rax, [rbp+27h+arg_38]
0x14000e449  mov     [rbp+27h+var_40], rax
0x14000e44d  lea     rax, [rbp+27h+arg_40]
0x14000e451  mov     [rbp+27h+var_30], rax
0x14000e455  lea     rax, [rbp+27h+arg_48]
0x14000e459  mov     [rbp+27h+var_20], rax
0x14000e45d  lea     rax, [rbp+27h+var_90]
0x14000e461  mov     [rsp+0C0h+var_A0], rax
0x14000e466  mov     [rbp+27h+var_78], 4
0x14000e46e  mov     [rbp+27h+var_58], 4
0x14000e476  mov     [rbp+27h+var_38], 4
0x14000e47e  mov     [rbp+27h+var_28], 4
0x14000e486  mov     [rbp+27h+var_18], 4
0x14000e48e  call    McGenEventWrite_EtwWriteTransfer
0x14000e493  mov     rcx, [rbp+27h+var_10]
0x14000e497  xor     rcx, rsp; StackCookie
0x14000e49a  call    __security_check_cookie
0x14000e49f  add     rsp, 0C0h
0x14000e4a6  pop     rbp
0x14000e4a7  retn
```
