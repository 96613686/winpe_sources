# McTemplateK0dqddddddddhUR10_EtwWriteTransfer

- ea: `0x14001b5b4`
- end: `0x14001b6ee`
- name: `McTemplateK0dqddddddddhUR10_EtwWriteTransfer`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400157a0`

## callees

- `0x140014ac4`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0dqddddddddhUR10_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13,
        unsigned __int16 a14,
        __int64 a15)
{
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+40h] [rbp-C0h] BYREF
  int *v19; // [rsp+50h] [rbp-B0h]
  __int64 v20; // [rsp+58h] [rbp-A8h]
  int *v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+68h] [rbp-98h]
  char *v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  char *v25; // [rsp+80h] [rbp-80h]
  __int64 v26; // [rsp+88h] [rbp-78h]
  char *v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  char *v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  char *v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  char *v33; // [rsp+C0h] [rbp-40h]
  __int64 v34; // [rsp+C8h] [rbp-38h]
  char *v35; // [rsp+D0h] [rbp-30h]
  __int64 v36; // [rsp+D8h] [rbp-28h]
  char *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v39; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  __int64 v41; // [rsp+100h] [rbp+0h]
  int v42; // [rsp+108h] [rbp+8h]
  int v43; // [rsp+10Ch] [rbp+Ch]

  v17 = 405;
  v43 = 0;
  v19 = &v16;
  v21 = &v17;
  v23 = &a6;
  v16 = 30;
  v25 = &a7;
  v20 = 4;
  v27 = &a8;
  v29 = &a9;
  v31 = &a10;
  v33 = &a11;
  v35 = &a12;
  v37 = &a13;
  v39 = &a14;
  v41 = a15;
  v42 = a14;
  v22 = 4;
  v24 = 4;
  v26 = 4;
  v28 = 4;
  v30 = 4;
  v32 = 4;
  v34 = 4;
  v36 = 4;
  v38 = 4;
  v40 = 2;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)TPM_FAILURE_INFORMATION, a3, 0xDu, &v18);
}

```

## disassembly

```asm
0x14001b5b4  push    rbp
0x14001b5b6  lea     rbp, [rsp-20h]
0x14001b5bb  sub     rsp, 120h
0x14001b5c2  mov     rax, cs:__security_cookie
0x14001b5c9  xor     rax, rsp
0x14001b5cc  mov     [rbp+20h+var_10], rax
0x14001b5d0  xor     edx, edx
0x14001b5d2  mov     [rsp+120h+var_E8], 195h
0x14001b5da  lea     rax, [rsp+120h+var_F0]
0x14001b5df  mov     [rbp+20h+var_14], edx
0x14001b5e2  mov     [rsp+120h+var_D0], rax
0x14001b5e7  lea     rax, [rsp+120h+var_E8]
0x14001b5ec  mov     [rsp+120h+var_C0], rax
0x14001b5f1  lea     rax, [rbp+20h+arg_28]
0x14001b5f5  mov     [rsp+120h+var_B0], rax
0x14001b5fa  lea     r9d, [rdx+0Dh]
0x14001b5fe  lea     rax, [rbp+20h+arg_30]
0x14001b602  mov     [rsp+120h+var_F0], 1Eh
0x14001b60a  mov     [rbp+20h+var_A0], rax
0x14001b60e  lea     rdx, TPM_FAILURE_INFORMATION
0x14001b615  lea     rax, [rbp+20h+arg_38]
0x14001b619  mov     [rsp+120h+var_C8], 4
0x14001b622  mov     [rbp+20h+var_90], rax
0x14001b626  lea     rax, [rbp+20h+arg_40]
0x14001b62a  mov     [rbp+20h+var_80], rax
0x14001b62e  lea     rax, [rbp+20h+arg_48]
0x14001b632  mov     [rbp+20h+var_70], rax
0x14001b636  lea     rax, [rbp+20h+arg_50]
0x14001b63d  mov     [rbp+20h+var_60], rax
0x14001b641  lea     rax, [rbp+20h+arg_58]
0x14001b648  mov     [rbp+20h+var_50], rax
0x14001b64c  lea     rax, [rbp+20h+arg_60]
0x14001b653  mov     [rbp+20h+var_40], rax
0x14001b657  lea     rax, [rbp+20h+arg_68]
0x14001b65e  mov     [rbp+20h+var_30], rax
0x14001b662  mov     rax, [rbp+20h+arg_70]
0x14001b669  mov     [rbp+20h+var_20], rax
0x14001b66d  movzx   eax, [rbp+20h+arg_68]
0x14001b674  mov     [rbp+20h+var_18], eax
0x14001b677  lea     rax, [rsp+120h+var_E0]
0x14001b67c  mov     [rsp+120h+var_100], rax
0x14001b681  mov     [rsp+120h+var_B8], 4
0x14001b68a  mov     [rsp+120h+var_A8], 4
0x14001b693  mov     [rbp+20h+var_98], 4
0x14001b69b  mov     [rbp+20h+var_88], 4
0x14001b6a3  mov     [rbp+20h+var_78], 4
0x14001b6ab  mov     [rbp+20h+var_68], 4
0x14001b6b3  mov     [rbp+20h+var_58], 4
0x14001b6bb  mov     [rbp+20h+var_48], 4
0x14001b6c3  mov     [rbp+20h+var_38], 4
0x14001b6cb  mov     [rbp+20h+var_28], 2
0x14001b6d3  call    McGenEventWrite_EtwWriteTransfer
0x14001b6d8  mov     rcx, [rbp+20h+var_10]
0x14001b6dc  xor     rcx, rsp; StackCookie
0x14001b6df  call    __security_check_cookie
0x14001b6e4  add     rsp, 120h
0x14001b6eb  pop     rbp
0x14001b6ec  retn
```
