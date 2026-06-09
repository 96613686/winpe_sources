# McTemplateK0d_EtwWriteTransfer

- ea: `0x14000672c`
- end: `0x140006783`
- name: `McTemplateK0d_EtwWriteTransfer`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400351b4`

## callees

- `0x140003f40`
- `0x140007c60`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0d_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF
  int *v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+48h] [rbp-20h]
  int v8; // [rsp+88h] [rbp+20h] BYREF

  v8 = a4;
  v7 = 4;
  v6 = &v8;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)WcifsDriverEntryFailure, a3, 2u, &v5);
}

```

## disassembly

```asm
0x14000672c  mov     r11, rsp
0x14000672f  mov     [r11+20h], r9d
0x140006733  sub     rsp, 68h
0x140006737  mov     rax, cs:__security_cookie
0x14000673e  xor     rax, rsp
0x140006741  mov     [rsp+68h+var_18], rax
0x140006746  lea     rax, [r11+20h]
0x14000674a  mov     qword ptr [r11-20h], 4
0x140006752  mov     [r11-28h], rax
0x140006756  lea     rdx, WcifsDriverEntryFailure
0x14000675d  lea     rax, [r11-38h]
0x140006761  mov     r9d, 2
0x140006767  mov     [r11-48h], rax
0x14000676b  call    McGenEventWrite_EtwWriteTransfer
0x140006770  mov     rcx, [rsp+68h+var_18]
0x140006775  xor     rcx, rsp; StackCookie
0x140006778  call    __security_check_cookie
0x14000677d  add     rsp, 68h
0x140006781  retn
```
