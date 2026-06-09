# McTemplateK0_EtwWriteTransfer

- ea: `0x14001215c`
- end: `0x140012191`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011c40`

## callees

- `0x1400120f4`
- `0x140017000`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, a4, &v5);
}

```

## disassembly

```asm
0x14001215c  sub     rsp, 58h
0x140012160  mov     rax, cs:__security_cookie
0x140012167  xor     rax, rsp
0x14001216a  mov     [rsp+58h+var_18], rax
0x14001216f  lea     rax, [rsp+58h+var_28]
0x140012174  mov     [rsp+58h+var_38], rax; PEVENT_DATA_DESCRIPTOR
0x140012179  call    McGenEventWrite_EtwWriteTransfer
0x14001217e  mov     rcx, [rsp+58h+var_18]
0x140012183  xor     rcx, rsp; StackCookie
0x140012186  call    __security_check_cookie
0x14001218b  add     rsp, 58h
0x14001218f  retn
```
