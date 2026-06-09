# McTemplateK0jjqqh_EtwWriteTransfer

- ea: `0x140008ef0`
- end: `0x140008f89`
- name: `McTemplateK0jjqqh_EtwWriteTransfer`
- size: `153`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x1400022c0`

## callees

- `0x140008e18`
- `0x140011e90`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jjqqh_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        char a7,
        char a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-39h] BYREF
  __int64 v10; // [rsp+40h] [rbp-29h]
  __int64 v11; // [rsp+48h] [rbp-21h]
  __int64 v12; // [rsp+50h] [rbp-19h]
  __int64 v13; // [rsp+58h] [rbp-11h]
  char *v14; // [rsp+60h] [rbp-9h]
  __int64 v15; // [rsp+68h] [rbp-1h]
  char *v16; // [rsp+70h] [rbp+7h]
  __int64 v17; // [rsp+78h] [rbp+Fh]
  char *v18; // [rsp+80h] [rbp+17h]
  __int64 v19; // [rsp+88h] [rbp+1Fh]

  v12 = a5;
  v14 = &a6;
  v16 = &a7;
  v18 = &a8;
  v10 = a4;
  v11 = 16;
  v13 = 16;
  v15 = 4;
  v17 = 4;
  v19 = 2;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)VMBUS_FINISH_FETCHING, a3, 6u, &v9);
}

```

## disassembly

```asm
0x140008ef0  push    rbp
0x140008ef2  lea     rbp, [rsp-37h]
0x140008ef7  sub     rsp, 0A0h
0x140008efe  mov     rax, cs:__security_cookie
0x140008f05  xor     rax, rsp
0x140008f08  mov     [rbp+37h+var_10], rax
0x140008f0c  mov     rax, [rbp+37h+arg_20]
0x140008f10  lea     rdx, VMBUS_FINISH_FETCHING
0x140008f17  mov     [rbp+37h+var_50], rax
0x140008f1b  lea     rax, [rbp+37h+arg_28]
0x140008f1f  mov     [rbp+37h+var_40], rax
0x140008f23  lea     rax, [rbp+37h+arg_30]
0x140008f27  mov     [rbp+37h+var_30], rax
0x140008f2b  lea     rax, [rbp+37h+arg_38]
0x140008f2f  mov     [rbp+37h+var_20], rax
0x140008f33  lea     rax, [rbp+37h+var_70]
0x140008f37  mov     [rbp+37h+var_60], r9
0x140008f3b  mov     r9d, 6
0x140008f41  mov     [rsp+0A0h+var_80], rax
0x140008f46  mov     [rbp+37h+var_58], 10h
0x140008f4e  mov     [rbp+37h+var_48], 10h
0x140008f56  mov     [rbp+37h+var_38], 4
0x140008f5e  mov     [rbp+37h+var_28], 4
0x140008f66  mov     [rbp+37h+var_18], 2
0x140008f6e  call    McGenEventWrite_EtwWriteTransfer
0x140008f73  mov     rcx, [rbp+37h+var_10]
0x140008f77  xor     rcx, rsp; StackCookie
0x140008f7a  call    __security_check_cookie
0x140008f7f  add     rsp, 0A0h
0x140008f86  pop     rbp
0x140008f87  retn
```
