# McTemplateK0qbr0br0qbr3br3q_EtwWriteTransfer

- ea: `0x14001af88`
- end: `0x14001b047`
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
- `0x14001f320`

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
0x14001af88  mov     [rsp-8+arg_18], r9d
0x14001af8d  push    rbp
0x14001af8e  lea     rbp, [rsp-27h]
0x14001af93  sub     rsp, 0C0h
0x14001af9a  mov     rax, cs:__security_cookie
0x14001afa1  xor     rax, rsp
0x14001afa4  mov     [rbp+27h+var_10], rax
0x14001afa8  mov     r8d, [rbp+27h+arg_30]
0x14001afac  lea     rax, [rbp+27h+arg_18]
0x14001afb0  mov     [rbp+27h+var_80], rax
0x14001afb4  xor     r10d, r10d
0x14001afb7  mov     rax, [rbp+27h+arg_20]
0x14001afbb  mov     [rbp+27h+var_70], rax
0x14001afbf  mov     rax, [rbp+27h+arg_28]
0x14001afc3  mov     [rbp+27h+var_60], rax
0x14001afc7  lea     rax, [rbp+27h+arg_30]
0x14001afcb  mov     [rbp+27h+var_50], rax
0x14001afcf  mov     rax, [rbp+27h+arg_38]
0x14001afd3  mov     [rbp+27h+var_40], rax
0x14001afd7  mov     rax, [rbp+27h+arg_40]
0x14001afdb  mov     [rbp+27h+var_30], rax
0x14001afdf  lea     rax, [rbp+27h+arg_48]
0x14001afe3  mov     [rbp+27h+var_20], rax
0x14001afe7  lea     rax, [rbp+27h+var_90]
0x14001afeb  mov     [rbp+27h+var_68], r9d
0x14001afef  mov     [rbp+27h+var_58], r9d
0x14001aff3  lea     r9d, [r10+8]
0x14001aff7  mov     [rsp+0C0h+var_A0], rax
0x14001affc  mov     [rbp+27h+var_78], 4
0x14001b004  mov     [rbp+27h+var_64], r10d
0x14001b008  mov     [rbp+27h+var_54], r10d
0x14001b00c  mov     [rbp+27h+var_48], 4
0x14001b014  mov     [rbp+27h+var_38], r8d
0x14001b018  mov     [rbp+27h+var_34], r10d
0x14001b01c  mov     [rbp+27h+var_28], r8d
0x14001b020  mov     [rbp+27h+var_24], r10d
0x14001b024  mov     [rbp+27h+var_18], 4
0x14001b02c  call    McGenEventWrite_EtwWriteTransfer
0x14001b031  mov     rcx, [rbp+27h+var_10]
0x14001b035  xor     rcx, rsp; StackCookie
0x14001b038  call    __security_check_cookie
0x14001b03d  add     rsp, 0C0h
0x14001b044  pop     rbp
0x14001b045  retn
```
