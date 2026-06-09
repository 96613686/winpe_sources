# McTemplateK0qbr0br0qbr3br3q_EtwWriteTransfer

- ea: `0x14001aaa8`
- end: `0x14001ab67`
- name: `McTemplateK0qbr0br0qbr3br3q_EtwWriteTransfer`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140009b04`
- `0x14000ae68`

## callees

- `0x1400095bc`
- `0x14001ede0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qbr0br0qbr3br3q_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        char a10)
{
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-69h] BYREF
  int *v12; // [rsp+40h] [rbp-59h]
  __int64 v13; // [rsp+48h] [rbp-51h]
  __int64 v14; // [rsp+50h] [rbp-49h]
  int v15; // [rsp+58h] [rbp-41h]
  int v16; // [rsp+5Ch] [rbp-3Dh]
  __int64 v17; // [rsp+60h] [rbp-39h]
  int v18; // [rsp+68h] [rbp-31h]
  int v19; // [rsp+6Ch] [rbp-2Dh]
  unsigned int *v20; // [rsp+70h] [rbp-29h]
  __int64 v21; // [rsp+78h] [rbp-21h]
  __int64 v22; // [rsp+80h] [rbp-19h]
  unsigned int v23; // [rsp+88h] [rbp-11h]
  int v24; // [rsp+8Ch] [rbp-Dh]
  __int64 v25; // [rsp+90h] [rbp-9h]
  unsigned int v26; // [rsp+98h] [rbp-1h]
  int v27; // [rsp+9Ch] [rbp+3h]
  char *v28; // [rsp+A0h] [rbp+7h]
  __int64 v29; // [rsp+A8h] [rbp+Fh]
  int v30; // [rsp+E8h] [rbp+4Fh] BYREF

  v30 = a4;
  v12 = &v30;
  v14 = a5;
  v17 = a6;
  v20 = &a7;
  v22 = a8;
  v25 = a9;
  v28 = &a10;
  v15 = a4;
  v18 = a4;
  v13 = 4;
  v16 = 0;
  v19 = 0;
  v21 = 4;
  v23 = a7;
  v24 = 0;
  v26 = a7;
  v27 = 0;
  v29 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a7, 8u, &v11);
}

```

## disassembly

```asm
0x14001aaa8  mov     [rsp-8+arg_18], r9d
0x14001aaad  push    rbp
0x14001aaae  lea     rbp, [rsp-27h]
0x14001aab3  sub     rsp, 0C0h
0x14001aaba  mov     rax, cs:__security_cookie
0x14001aac1  xor     rax, rsp
0x14001aac4  mov     [rbp+27h+var_10], rax
0x14001aac8  mov     r8d, [rbp+27h+arg_30]
0x14001aacc  lea     rax, [rbp+27h+arg_18]
0x14001aad0  mov     [rbp+27h+var_80], rax
0x14001aad4  xor     r10d, r10d
0x14001aad7  mov     rax, [rbp+27h+arg_20]
0x14001aadb  mov     [rbp+27h+var_70], rax
0x14001aadf  mov     rax, [rbp+27h+arg_28]
0x14001aae3  mov     [rbp+27h+var_60], rax
0x14001aae7  lea     rax, [rbp+27h+arg_30]
0x14001aaeb  mov     [rbp+27h+var_50], rax
0x14001aaef  mov     rax, [rbp+27h+arg_38]
0x14001aaf3  mov     [rbp+27h+var_40], rax
0x14001aaf7  mov     rax, [rbp+27h+arg_40]
0x14001aafb  mov     [rbp+27h+var_30], rax
0x14001aaff  lea     rax, [rbp+27h+arg_48]
0x14001ab03  mov     [rbp+27h+var_20], rax
0x14001ab07  lea     rax, [rbp+27h+var_90]
0x14001ab0b  mov     [rbp+27h+var_68], r9d
0x14001ab0f  mov     [rbp+27h+var_58], r9d
0x14001ab13  lea     r9d, [r10+8]
0x14001ab17  mov     [rsp+0C0h+var_A0], rax
0x14001ab1c  mov     [rbp+27h+var_78], 4
0x14001ab24  mov     [rbp+27h+var_64], r10d
0x14001ab28  mov     [rbp+27h+var_54], r10d
0x14001ab2c  mov     [rbp+27h+var_48], 4
0x14001ab34  mov     [rbp+27h+var_38], r8d
0x14001ab38  mov     [rbp+27h+var_34], r10d
0x14001ab3c  mov     [rbp+27h+var_28], r8d
0x14001ab40  mov     [rbp+27h+var_24], r10d
0x14001ab44  mov     [rbp+27h+var_18], 4
0x14001ab4c  call    McGenEventWrite_EtwWriteTransfer
0x14001ab51  mov     rcx, [rbp+27h+var_10]
0x14001ab55  xor     rcx, rsp; StackCookie
0x14001ab58  call    __security_check_cookie
0x14001ab5d  add     rsp, 0C0h
0x14001ab64  pop     rbp
0x14001ab65  retn
```
