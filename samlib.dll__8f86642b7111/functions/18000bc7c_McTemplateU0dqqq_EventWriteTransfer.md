# McTemplateU0dqqq_EventWriteTransfer

- ea: `0x18000bc7c`
- end: `0x18000bd10`
- name: `McTemplateU0dqqq_EventWriteTransfer`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010410`

## callees

- `0x1800061d0`
- `0x180006620`

## pseudocode

```c
ULONG __fastcall McTemplateU0dqqq_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, char a5, char a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-19h] BYREF
  int *v8; // [rsp+48h] [rbp-9h]
  __int64 v9; // [rsp+50h] [rbp-1h]
  int *v10; // [rsp+58h] [rbp+7h]
  __int64 v11; // [rsp+60h] [rbp+Fh]
  char *v12; // [rsp+68h] [rbp+17h]
  __int64 v13; // [rsp+70h] [rbp+1Fh]
  char *v14; // [rsp+78h] [rbp+27h]
  __int64 v15; // [rsp+80h] [rbp+2Fh]
  int v16; // [rsp+B8h] [rbp+67h] BYREF
  int v17; // [rsp+C0h] [rbp+6Fh] BYREF

  v17 = a4;
  v16 = a3;
  v9 = 4;
  v8 = &v16;
  v11 = 4;
  v10 = &v17;
  v13 = 4;
  v12 = &a5;
  v14 = &a6;
  v15 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)SamQueryDisplayInformationExit, a3, 5u, &v7);
}

```

## disassembly

```asm
0x18000bc7c  mov     r11, rsp
0x18000bc7f  mov     [r11+20h], r9d
0x18000bc83  mov     [r11+18h], r8d
0x18000bc87  push    rbp
0x18000bc88  lea     rbp, [r11-4Fh]
0x18000bc8c  sub     rsp, 90h
0x18000bc93  mov     rax, cs:__security_cookie
0x18000bc9a  xor     rax, rsp
0x18000bc9d  mov     [rbp+47h+var_10], rax
0x18000bca1  lea     rax, [rbp+47h+arg_10]
0x18000bca5  mov     [rbp+47h+var_48], 4
0x18000bcad  mov     [rbp+47h+var_50], rax
0x18000bcb1  lea     rdx, SamQueryDisplayInformationExit
0x18000bcb8  lea     rax, [rbp+47h+arg_18]
0x18000bcbc  mov     [rbp+47h+var_38], 4
0x18000bcc4  mov     [rbp+47h+var_40], rax
0x18000bcc8  mov     r9d, 5
0x18000bcce  lea     rax, [rbp+47h+arg_20]
0x18000bcd2  mov     [rbp+47h+var_28], 4
0x18000bcda  mov     [rbp+47h+var_30], rax
0x18000bcde  lea     rax, [rbp+47h+arg_28]
0x18000bce2  mov     [rbp+47h+var_20], rax
0x18000bce6  lea     rax, [rbp+47h+var_60]
0x18000bcea  mov     [r11-78h], rax
0x18000bcee  mov     [rbp+47h+var_18], 4
0x18000bcf6  call    McGenEventWrite_EventWriteTransfer
0x18000bcfb  mov     rcx, [rbp+47h+var_10]
0x18000bcff  xor     rcx, rsp; StackCookie
0x18000bd02  call    __security_check_cookie
0x18000bd07  add     rsp, 90h
0x18000bd0e  pop     rbp
0x18000bd0f  retn
```
