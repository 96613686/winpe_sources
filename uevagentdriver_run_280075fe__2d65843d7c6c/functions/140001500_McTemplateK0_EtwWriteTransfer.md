# McTemplateK0_EtwWriteTransfer

- ea: `0x140001500`
- end: `0x14000153b`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b5c0`
- `0x14000c614`

## callees

- `0x140001030`
- `0x140001a30`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 1u, &v4);
}

```

## disassembly

```asm
0x140001500  sub     rsp, 58h
0x140001504  mov     rax, cs:__security_cookie
0x14000150b  xor     rax, rsp
0x14000150e  mov     [rsp+58h+var_18], rax
0x140001513  lea     rax, [rsp+58h+var_28]
0x140001518  mov     r9d, 1
0x14000151e  mov     [rsp+58h+var_38], rax
0x140001523  call    McGenEventWrite_EtwWriteTransfer
0x140001528  mov     rcx, [rsp+58h+var_18]
0x14000152d  xor     rcx, rsp; StackCookie
0x140001530  call    __security_check_cookie
0x140001535  add     rsp, 58h
0x140001539  retn
```
