# McTemplateK0qbr0qbr2qqtq_EtwWriteTransfer

- ea: `0x140019884`
- end: `0x140019952`
- name: `McTemplateK0qbr0qbr2qqtq_EtwWriteTransfer`
- size: `206`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004648`
- `0x140008df0`
- `0x14000b220`
- `0x140019d5c`

## callees

- `0x1400095bc`
- `0x14001ede0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qbr0qbr2qqtq_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        char a8,
        char a9,
        char a10,
        char a11)
{
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-81h] BYREF
  int *v13; // [rsp+40h] [rbp-71h]
  __int64 v14; // [rsp+48h] [rbp-69h]
  __int64 v15; // [rsp+50h] [rbp-61h]
  int v16; // [rsp+58h] [rbp-59h]
  int v17; // [rsp+5Ch] [rbp-55h]
  int *v18; // [rsp+60h] [rbp-51h]
  __int64 v19; // [rsp+68h] [rbp-49h]
  __int64 v20; // [rsp+70h] [rbp-41h]
  int v21; // [rsp+78h] [rbp-39h]
  int v22; // [rsp+7Ch] [rbp-35h]
  char *v23; // [rsp+80h] [rbp-31h]
  __int64 v24; // [rsp+88h] [rbp-29h]
  char *v25; // [rsp+90h] [rbp-21h]
  __int64 v26; // [rsp+98h] [rbp-19h]
  char *v27; // [rsp+A0h] [rbp-11h]
  __int64 v28; // [rsp+A8h] [rbp-9h]
  char *v29; // [rsp+B0h] [rbp-1h]
  __int64 v30; // [rsp+B8h] [rbp+7h]
  int v31; // [rsp+F8h] [rbp+47h] BYREF

  v31 = a4;
  v16 = a4;
  v14 = 4;
  v13 = &v31;
  v15 = a5;
  v17 = 0;
  v18 = &a6;
  v20 = a7;
  v21 = a6;
  v23 = &a8;
  v25 = &a9;
  v27 = &a10;
  v29 = &a11;
  v19 = 4;
  v22 = 0;
  v24 = 4;
  v26 = 4;
  v28 = 4;
  v30 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, 0, 9u, &v12);
}

```

## disassembly

```asm
0x140019884  mov     [rsp-8+arg_18], r9d
0x140019889  push    rbp
0x14001988a  lea     rbp, [rsp-1Fh]
0x14001988f  sub     rsp, 0D0h
0x140019896  mov     rax, cs:__security_cookie
0x14001989d  xor     rax, rsp
0x1400198a0  mov     [rbp+1Fh+var_10], rax
0x1400198a4  xor     r8d, r8d
0x1400198a7  mov     [rbp+1Fh+var_78], r9d
0x1400198ab  lea     rax, [rbp+1Fh+arg_18]
0x1400198af  mov     [rbp+1Fh+var_88], 4
0x1400198b7  mov     [rbp+1Fh+var_90], rax
0x1400198bb  mov     rax, [rbp+1Fh+arg_20]
0x1400198bf  mov     [rbp+1Fh+var_80], rax
0x1400198c3  lea     r9d, [r8+9]
0x1400198c7  lea     rax, [rbp+1Fh+arg_28]
0x1400198cb  mov     [rbp+1Fh+var_74], r8d
0x1400198cf  mov     [rbp+1Fh+var_70], rax
0x1400198d3  mov     rax, [rbp+1Fh+arg_30]
0x1400198d7  mov     [rbp+1Fh+var_60], rax
0x1400198db  mov     eax, [rbp+1Fh+arg_28]
0x1400198de  mov     [rbp+1Fh+var_58], eax
0x1400198e1  lea     rax, [rbp+1Fh+arg_38]
0x1400198e5  mov     [rbp+1Fh+var_50], rax
0x1400198e9  lea     rax, [rbp+1Fh+arg_40]
0x1400198ed  mov     [rbp+1Fh+var_40], rax
0x1400198f1  lea     rax, [rbp+1Fh+arg_48]
0x1400198f5  mov     [rbp+1Fh+var_30], rax
0x1400198f9  lea     rax, [rbp+1Fh+arg_50]
0x1400198fd  mov     [rbp+1Fh+var_20], rax
0x140019901  lea     rax, [rsp+0D0h+var_A0]
0x140019906  mov     [rsp+0D0h+var_B0], rax
0x14001990b  mov     [rbp+1Fh+var_68], 4
0x140019913  mov     [rbp+1Fh+var_54], r8d
0x140019917  mov     [rbp+1Fh+var_48], 4
0x14001991f  mov     [rbp+1Fh+var_38], 4
0x140019927  mov     [rbp+1Fh+var_28], 4
0x14001992f  mov     [rbp+1Fh+var_18], 4
0x140019937  call    McGenEventWrite_EtwWriteTransfer
0x14001993c  mov     rcx, [rbp+1Fh+var_10]
0x140019940  xor     rcx, rsp; StackCookie
0x140019943  call    __security_check_cookie
0x140019948  add     rsp, 0D0h
0x14001994f  pop     rbp
0x140019950  retn
```
