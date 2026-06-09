# McTemplateK0_EtwWriteTransfer

- ea: `0x140004edc`
- end: `0x140004f11`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003acc`
- `0x140004a18`

## callees

- `0x140004e78`
- `0x14000a9f0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, __int64 a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-28h] BYREF

  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, a4, &v5);
}

```

## disassembly

```asm
0x140004edc  sub     rsp, 58h
0x140004ee0  mov     rax, cs:__security_cookie
0x140004ee7  xor     rax, rsp
0x140004eea  mov     [rsp+58h+var_18], rax
0x140004eef  lea     rax, [rsp+58h+var_28]
0x140004ef4  mov     [rsp+58h+var_38], rax; PEVENT_DATA_DESCRIPTOR
0x140004ef9  call    McGenEventWrite_EtwWriteTransfer
0x140004efe  mov     rcx, [rsp+58h+var_18]
0x140004f03  xor     rcx, rsp; StackCookie
0x140004f06  call    __security_check_cookie
0x140004f0b  add     rsp, 58h
0x140004f0f  retn
```
