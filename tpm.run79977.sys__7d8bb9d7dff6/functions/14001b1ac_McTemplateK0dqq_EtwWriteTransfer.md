# McTemplateK0dqq_EtwWriteTransfer

- ea: `0x14001b1ac`
- end: `0x14001b218`
- name: `McTemplateK0dqq_EtwWriteTransfer`
- size: `108`
- prototype: ``
- caller_count: `33`
- callee_count: `2`
- tags: ``

## callers

- `0x140001620`
- `0x140001880`
- `0x140001a30`
- `0x1400028a0`
- `0x140002a90`
- `0x140002d80`
- `0x140003208`
- `0x140005370`
- `0x14000660c`
- `0x140008aac`
- `0x140008bfc`
- `0x14000d130`
- `0x14000f5a0`
- `0x14000f910`
- `0x140010040`
- `0x140010540`
- `0x1400116fc`
- `0x1400120d0`
- `0x14001240c`
- `0x140013210`
- `0x1400157a0`
- `0x1400171d0`
- `0x1400179c4`
- `0x1400183d0`
- `0x14001a5b8`
- `0x14001b464`
- `0x1400228ac`
- `0x140022934`
- `0x1400229f4`
- `0x140022adc`
- `0x140025de0`
- `0x1400287f0`
- `0x1400289a0`

## callees

- `0x140014ac4`
- `0x140039740`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0dqq_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  int *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  char *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  char *v12; // [rsp+60h] [rbp-20h]
  __int64 v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+A8h] [rbp+28h] BYREF

  v14 = a4;
  v8 = &v14;
  v10 = &a5;
  v12 = &a6;
  v9 = 4;
  v11 = 4;
  v13 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 4u, &v7);
}

```

## disassembly

```asm
0x14001b1ac  mov     [rsp-8+arg_18], r9d
0x14001b1b1  push    rbp
0x14001b1b2  mov     rbp, rsp
0x14001b1b5  sub     rsp, 80h
0x14001b1bc  mov     rax, cs:__security_cookie
0x14001b1c3  xor     rax, rsp
0x14001b1c6  mov     [rbp+var_10], rax
0x14001b1ca  mov     r9d, 4
0x14001b1d0  lea     rax, [rbp+arg_18]
0x14001b1d4  mov     [rbp+var_40], rax
0x14001b1d8  lea     rax, [rbp+arg_20]
0x14001b1dc  mov     [rbp+var_30], rax
0x14001b1e0  lea     rax, [rbp+arg_28]
0x14001b1e4  mov     [rbp+var_20], rax
0x14001b1e8  lea     rax, [rbp+var_50]
0x14001b1ec  mov     [rsp+80h+var_60], rax
0x14001b1f1  mov     [rbp+var_38], r9
0x14001b1f5  mov     [rbp+var_28], r9
0x14001b1f9  mov     [rbp+var_18], r9
0x14001b1fd  call    McGenEventWrite_EtwWriteTransfer
0x14001b202  mov     rcx, [rbp+var_10]
0x14001b206  xor     rcx, rsp; StackCookie
0x14001b209  call    __security_check_cookie
0x14001b20e  add     rsp, 80h
0x14001b215  pop     rbp
0x14001b216  retn
```
