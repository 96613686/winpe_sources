# McTemplateK0dqqq_EtwWriteTransfer

- ea: `0x140014a34`
- end: `0x140014abe`
- name: `McTemplateK0dqqq_EtwWriteTransfer`
- size: `138`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ae4`
- `0x1400116fc`
- `0x140016afc`
- `0x140018a30`
- `0x14001ae60`

## callees

- `0x140014ac4`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0dqqq_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        char a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-21h] BYREF
  int *v9; // [rsp+40h] [rbp-11h]
  __int64 v10; // [rsp+48h] [rbp-9h]
  char *v11; // [rsp+50h] [rbp-1h]
  __int64 v12; // [rsp+58h] [rbp+7h]
  char *v13; // [rsp+60h] [rbp+Fh]
  __int64 v14; // [rsp+68h] [rbp+17h]
  char *v15; // [rsp+70h] [rbp+1Fh]
  __int64 v16; // [rsp+78h] [rbp+27h]
  int v17; // [rsp+B8h] [rbp+67h] BYREF

  v17 = a4;
  v10 = 4;
  v9 = &v17;
  v12 = 4;
  v11 = &a5;
  v13 = &a6;
  v15 = &a7;
  v14 = 4;
  v16 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 5u, &v8);
}

```

## disassembly

```asm
0x140014a34  mov     [rsp-8+arg_18], r9d
0x140014a39  push    rbp
0x140014a3a  lea     rbp, [rsp-3Fh]
0x140014a3f  sub     rsp, 90h
0x140014a46  mov     rax, cs:__security_cookie
0x140014a4d  xor     rax, rsp
0x140014a50  mov     [rbp+3Fh+var_10], rax
0x140014a54  lea     rax, [rbp+3Fh+arg_18]
0x140014a58  mov     [rbp+3Fh+var_48], 4
0x140014a60  mov     [rbp+3Fh+var_50], rax
0x140014a64  mov     r9d, 5
0x140014a6a  lea     rax, [rbp+3Fh+arg_20]
0x140014a6e  mov     [rbp+3Fh+var_38], 4
0x140014a76  mov     [rbp+3Fh+var_40], rax
0x140014a7a  lea     rax, [rbp+3Fh+arg_28]
0x140014a7e  mov     [rbp+3Fh+var_30], rax
0x140014a82  lea     rax, [rbp+3Fh+arg_30]
0x140014a86  mov     [rbp+3Fh+var_20], rax
0x140014a8a  lea     rax, [rbp+3Fh+var_60]
0x140014a8e  mov     [rsp+90h+var_70], rax
0x140014a93  mov     [rbp+3Fh+var_28], 4
0x140014a9b  mov     [rbp+3Fh+var_18], 4
0x140014aa3  call    McGenEventWrite_EtwWriteTransfer
0x140014aa8  mov     rcx, [rbp+3Fh+var_10]
0x140014aac  xor     rcx, rsp; StackCookie
0x140014aaf  call    __security_check_cookie
0x140014ab4  add     rsp, 90h
0x140014abb  pop     rbp
0x140014abc  retn
```
