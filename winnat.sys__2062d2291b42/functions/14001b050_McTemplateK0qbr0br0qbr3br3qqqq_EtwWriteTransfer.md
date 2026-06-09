# McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer

- ea: `0x14001b050`
- end: `0x14001b149`
- name: `McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer`
- size: `249`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ed0`
- `0x1400052d0`
- `0x140009b04`
- `0x14000a9d0`
- `0x14000ae68`

## callees

- `0x1400095bc`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9,
        char a10,
        char a11,
        char a12,
        char a13)
{
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-B1h] BYREF
  int *v15; // [rsp+40h] [rbp-A1h]
  __int64 v16; // [rsp+48h] [rbp-99h]
  __int64 v17; // [rsp+50h] [rbp-91h]
  int v18; // [rsp+58h] [rbp-89h]
  int v19; // [rsp+5Ch] [rbp-85h]
  __int64 v20; // [rsp+60h] [rbp-81h]
  int v21; // [rsp+68h] [rbp-79h]
  int v22; // [rsp+6Ch] [rbp-75h]
  int *v23; // [rsp+70h] [rbp-71h]
  __int64 v24; // [rsp+78h] [rbp-69h]
  __int64 v25; // [rsp+80h] [rbp-61h]
  int v26; // [rsp+88h] [rbp-59h]
  int v27; // [rsp+8Ch] [rbp-55h]
  __int64 v28; // [rsp+90h] [rbp-51h]
  int v29; // [rsp+98h] [rbp-49h]
  int v30; // [rsp+9Ch] [rbp-45h]
  char *v31; // [rsp+A0h] [rbp-41h]
  __int64 v32; // [rsp+A8h] [rbp-39h]
  char *v33; // [rsp+B0h] [rbp-31h]
  __int64 v34; // [rsp+B8h] [rbp-29h]
  char *v35; // [rsp+C0h] [rbp-21h]
  __int64 v36; // [rsp+C8h] [rbp-19h]
  char *v37; // [rsp+D0h] [rbp-11h]
  __int64 v38; // [rsp+D8h] [rbp-9h]
  int v39; // [rsp+118h] [rbp+37h] BYREF

  v39 = a4;
  v18 = a4;
  v21 = a4;
  v15 = &v39;
  v17 = a5;
  v20 = a6;
  v23 = &a7;
  v25 = a8;
  v28 = a9;
  v31 = &a10;
  v33 = &a11;
  v35 = &a12;
  v37 = &a13;
  v26 = a7;
  v29 = a7;
  v16 = 4;
  v19 = 0;
  v22 = 0;
  v24 = 4;
  v27 = 0;
  v30 = 0;
  v32 = 4;
  v34 = 4;
  v36 = 4;
  v38 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, (__int64)a1, 0xBu, &v14);
}

```

## disassembly

```asm
0x14001b050  mov     [rsp-8+arg_18], r9d
0x14001b055  push    rbp
0x14001b056  lea     rbp, [rsp-0Fh]
0x14001b05b  sub     rsp, 0F0h
0x14001b062  mov     rax, cs:__security_cookie
0x14001b069  xor     rax, rsp
0x14001b06c  mov     [rbp+0Fh+var_10], rax
0x14001b070  xor     r10d, r10d
0x14001b073  mov     [rsp+0F0h+var_98], r9d
0x14001b078  mov     r8, rcx
0x14001b07b  mov     [rbp+0Fh+var_88], r9d
0x14001b07f  mov     ecx, [rbp+0Fh+arg_30]
0x14001b082  lea     rax, [rbp+0Fh+arg_18]
0x14001b086  mov     [rsp+0F0h+var_B0], rax
0x14001b08b  mov     rax, [rbp+0Fh+arg_20]
0x14001b08f  lea     r9d, [r10+0Bh]
0x14001b093  mov     [rsp+0F0h+var_A0], rax
0x14001b098  mov     rax, [rbp+0Fh+arg_28]
0x14001b09c  mov     [rsp+0F0h+var_90], rax
0x14001b0a1  lea     rax, [rbp+0Fh+arg_30]
0x14001b0a5  mov     [rbp+0Fh+var_80], rax
0x14001b0a9  mov     rax, [rbp+0Fh+arg_38]
0x14001b0ad  mov     [rbp+0Fh+var_70], rax
0x14001b0b1  mov     rax, [rbp+0Fh+arg_40]
0x14001b0b5  mov     [rbp+0Fh+var_60], rax
0x14001b0b9  lea     rax, [rbp+0Fh+arg_48]
0x14001b0bd  mov     [rbp+0Fh+var_50], rax
0x14001b0c1  lea     rax, [rbp+0Fh+arg_50]
0x14001b0c5  mov     [rbp+0Fh+var_40], rax
0x14001b0c9  lea     rax, [rbp+0Fh+arg_58]
0x14001b0cd  mov     [rbp+0Fh+var_30], rax
0x14001b0d1  lea     rax, [rbp+0Fh+arg_60]
0x14001b0d5  mov     [rbp+0Fh+var_20], rax
0x14001b0d9  lea     rax, [rsp+0F0h+var_C0]
0x14001b0de  mov     [rbp+0Fh+var_68], ecx
0x14001b0e1  mov     [rbp+0Fh+var_58], ecx
0x14001b0e4  mov     rcx, r8
0x14001b0e7  mov     [rsp+0F0h+var_D0], rax
0x14001b0ec  mov     [rsp+0F0h+var_A8], 4
0x14001b0f5  mov     [rsp+0F0h+var_94], r10d
0x14001b0fa  mov     [rbp+0Fh+var_84], r10d
0x14001b0fe  mov     [rbp+0Fh+var_78], 4
0x14001b106  mov     [rbp+0Fh+var_64], r10d
0x14001b10a  mov     [rbp+0Fh+var_54], r10d
0x14001b10e  mov     [rbp+0Fh+var_48], 4
0x14001b116  mov     [rbp+0Fh+var_38], 4
0x14001b11e  mov     [rbp+0Fh+var_28], 4
0x14001b126  mov     [rbp+0Fh+var_18], 4
0x14001b12e  call    McGenEventWrite_EtwWriteTransfer
0x14001b133  mov     rcx, [rbp+0Fh+var_10]
0x14001b137  xor     rcx, rsp; StackCookie
0x14001b13a  call    __security_check_cookie
0x14001b13f  add     rsp, 0F0h
0x14001b146  pop     rbp
0x14001b147  retn
```
