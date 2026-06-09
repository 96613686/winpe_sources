# McTemplateK0qbr0br0qbr3br3qqqqqt_EtwWriteTransfer

- ea: `0x14001ba60`
- end: `0x14001bb88`
- name: `McTemplateK0qbr0br0qbr3br3qqqqqt_EtwWriteTransfer`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c7e0`
- `0x14001e124`

## callees

- `0x1400095bc`
- `0x14001ede0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qbr0br0qbr3br3qqqqqt_EtwWriteTransfer(
        REGHANDLE *a1,
        __int64 a2,
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
        char a13,
        char a14,
        char a15)
{
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-D0h] BYREF
  int *v17; // [rsp+40h] [rbp-C0h]
  __int64 v18; // [rsp+48h] [rbp-B8h]
  __int64 v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+58h] [rbp-A8h]
  int v21; // [rsp+5Ch] [rbp-A4h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+6Ch] [rbp-94h]
  int *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+8Ch] [rbp-74h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  int v31; // [rsp+98h] [rbp-68h]
  int v32; // [rsp+9Ch] [rbp-64h]
  char *v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  char *v35; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  char *v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  char *v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  char *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  char *v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+138h] [rbp+38h] BYREF

  v45 = a4;
  v20 = a4;
  v23 = a4;
  v17 = &v45;
  v19 = a5;
  v22 = a6;
  v25 = &a7;
  v27 = a8;
  v30 = a9;
  v33 = &a10;
  v35 = &a11;
  v37 = &a12;
  v39 = &a13;
  v41 = &a14;
  v43 = &a15;
  v21 = 0;
  v24 = 0;
  v28 = a7;
  v29 = 0;
  v31 = a7;
  v32 = 0;
  v18 = 4;
  v26 = 4;
  v34 = 4;
  v36 = 4;
  v38 = 4;
  v40 = 4;
  v42 = 4;
  v44 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WINNAT_TRANSLATION, (__int64)a1, 0xDu, &v16);
}

```

## disassembly

```asm
0x14001ba60  mov     [rsp-8+arg_18], r9d
0x14001ba65  push    rbp
0x14001ba66  lea     rbp, [rsp-10h]
0x14001ba6b  sub     rsp, 110h
0x14001ba72  mov     rax, cs:__security_cookie
0x14001ba79  xor     rax, rsp
0x14001ba7c  mov     [rbp+10h+var_10], rax
0x14001ba80  xor     edx, edx
0x14001ba82  mov     [rsp+110h+var_B8], r9d
0x14001ba87  lea     rax, [rbp+10h+arg_18]
0x14001ba8b  mov     [rsp+110h+var_A8], r9d
0x14001ba90  mov     [rsp+110h+var_D0], rax
0x14001ba95  mov     r8, rcx
0x14001ba98  mov     ecx, [rbp+10h+arg_30]
0x14001ba9b  mov     rax, [rbp+10h+arg_20]
0x14001ba9f  lea     r9d, [rdx+0Dh]
0x14001baa3  mov     [rsp+110h+var_C0], rax
0x14001baa8  mov     rax, [rbp+10h+arg_28]
0x14001baac  mov     [rsp+110h+var_B0], rax
0x14001bab1  lea     rax, [rbp+10h+arg_30]
0x14001bab5  mov     [rsp+110h+var_A0], rax
0x14001baba  mov     rax, [rbp+10h+arg_38]
0x14001babe  mov     [rbp+10h+var_90], rax
0x14001bac2  mov     rax, [rbp+10h+arg_40]
0x14001bac6  mov     [rbp+10h+var_80], rax
0x14001baca  lea     rax, [rbp+10h+arg_48]
0x14001bace  mov     [rbp+10h+var_70], rax
0x14001bad2  lea     rax, [rbp+10h+arg_50]
0x14001bad6  mov     [rbp+10h+var_60], rax
0x14001bada  lea     rax, [rbp+10h+arg_58]
0x14001bade  mov     [rbp+10h+var_50], rax
0x14001bae2  lea     rax, [rbp+10h+arg_60]
0x14001bae9  mov     [rbp+10h+var_40], rax
0x14001baed  lea     rax, [rbp+10h+arg_68]
0x14001baf4  mov     [rbp+10h+var_30], rax
0x14001baf8  lea     rax, [rbp+10h+arg_70]
0x14001baff  mov     [rbp+10h+var_20], rax
0x14001bb03  lea     rax, [rsp+110h+var_E0]
0x14001bb08  mov     [rsp+110h+var_B4], edx
0x14001bb0c  mov     [rsp+110h+var_A4], edx
0x14001bb10  mov     [rbp+10h+var_88], ecx
0x14001bb13  mov     [rbp+10h+var_84], edx
0x14001bb16  mov     [rbp+10h+var_78], ecx
0x14001bb19  mov     rcx, r8
0x14001bb1c  mov     [rbp+10h+var_74], edx
0x14001bb1f  lea     rdx, WINNAT_TRANSLATION
0x14001bb26  mov     [rsp+110h+var_F0], rax
0x14001bb2b  mov     [rsp+110h+var_C8], 4
0x14001bb34  mov     [rsp+110h+var_98], 4
0x14001bb3d  mov     [rbp+10h+var_68], 4
0x14001bb45  mov     [rbp+10h+var_58], 4
0x14001bb4d  mov     [rbp+10h+var_48], 4
0x14001bb55  mov     [rbp+10h+var_38], 4
0x14001bb5d  mov     [rbp+10h+var_28], 4
0x14001bb65  mov     [rbp+10h+var_18], 4
0x14001bb6d  call    McGenEventWrite_EtwWriteTransfer
0x14001bb72  mov     rcx, [rbp+10h+var_10]
0x14001bb76  xor     rcx, rsp; StackCookie
0x14001bb79  call    __security_check_cookie
0x14001bb7e  add     rsp, 110h
0x14001bb85  pop     rbp
0x14001bb86  retn
```
