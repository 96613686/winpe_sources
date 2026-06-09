# McTemplateK0qttttqt_EtwWriteTransfer

- ea: `0x140014480`
- end: `0x140014541`
- name: `McTemplateK0qttttqt_EtwWriteTransfer`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140033018`

## callees

- `0x1400095bc`
- `0x14001f320`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qttttqt_EtwWriteTransfer(
        REGHANDLE *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10)
{
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-69h] BYREF
  int *v12; // [rsp+40h] [rbp-59h]
  __int64 v13; // [rsp+48h] [rbp-51h]
  char *v14; // [rsp+50h] [rbp-49h]
  __int64 v15; // [rsp+58h] [rbp-41h]
  char *v16; // [rsp+60h] [rbp-39h]
  __int64 v17; // [rsp+68h] [rbp-31h]
  char *v18; // [rsp+70h] [rbp-29h]
  __int64 v19; // [rsp+78h] [rbp-21h]
  char *v20; // [rsp+80h] [rbp-19h]
  __int64 v21; // [rsp+88h] [rbp-11h]
  char *v22; // [rsp+90h] [rbp-9h]
  __int64 v23; // [rsp+98h] [rbp-1h]
  char *v24; // [rsp+A0h] [rbp+7h]
  __int64 v25; // [rsp+A8h] [rbp+Fh]
  int v26; // [rsp+E8h] [rbp+4Fh] BYREF

  v26 = a4;
  v13 = 4;
  v12 = &v26;
  v15 = 4;
  v14 = &a5;
  v17 = 4;
  v16 = &a6;
  v18 = &a7;
  v20 = &a8;
  v22 = &a9;
  v24 = &a10;
  v19 = 4;
  v21 = 4;
  v23 = 4;
  v25 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WINNAT_DRIVER_STATE_RUNDOWN, a3, 8u, &v11);
}

```

## disassembly

```asm
0x140014480  mov     [rsp-8+arg_18], r9d
0x140014485  push    rbp
0x140014486  lea     rbp, [rsp-27h]
0x14001448b  sub     rsp, 0C0h
0x140014492  mov     rax, cs:__security_cookie
0x140014499  xor     rax, rsp
0x14001449c  mov     [rbp+27h+var_10], rax
0x1400144a0  lea     rax, [rbp+27h+arg_18]
0x1400144a4  mov     [rbp+27h+var_78], 4
0x1400144ac  mov     [rbp+27h+var_80], rax
0x1400144b0  lea     rdx, WINNAT_DRIVER_STATE_RUNDOWN
0x1400144b7  lea     rax, [rbp+27h+arg_20]
0x1400144bb  mov     [rbp+27h+var_68], 4
0x1400144c3  mov     [rbp+27h+var_70], rax
0x1400144c7  mov     r9d, 8
0x1400144cd  lea     rax, [rbp+27h+arg_28]
0x1400144d1  mov     [rbp+27h+var_58], 4
0x1400144d9  mov     [rbp+27h+var_60], rax
0x1400144dd  lea     rax, [rbp+27h+arg_30]
0x1400144e1  mov     [rbp+27h+var_50], rax
0x1400144e5  lea     rax, [rbp+27h+arg_38]
0x1400144e9  mov     [rbp+27h+var_40], rax
0x1400144ed  lea     rax, [rbp+27h+arg_40]
0x1400144f1  mov     [rbp+27h+var_30], rax
0x1400144f5  lea     rax, [rbp+27h+arg_48]
0x1400144f9  mov     [rbp+27h+var_20], rax
0x1400144fd  lea     rax, [rbp+27h+var_90]
0x140014501  mov     [rsp+0C0h+var_A0], rax
0x140014506  mov     [rbp+27h+var_48], 4
0x14001450e  mov     [rbp+27h+var_38], 4
0x140014516  mov     [rbp+27h+var_28], 4
0x14001451e  mov     [rbp+27h+var_18], 4
0x140014526  call    McGenEventWrite_EtwWriteTransfer
0x14001452b  mov     rcx, [rbp+27h+var_10]
0x14001452f  xor     rcx, rsp; StackCookie
0x140014532  call    __security_check_cookie
0x140014537  add     rsp, 0C0h
0x14001453e  pop     rbp
0x14001453f  retn
```
