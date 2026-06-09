# McTemplateK0_EtwWriteTransfer

- ea: `0x140003274`
- end: `0x1400032af`
- name: `McTemplateK0_EtwWriteTransfer`
- size: `59`
- prototype: `NTSTATUS __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140022270`
- `0x1400351b4`

## callees

- `0x140003f40`
- `0x140007c60`

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
0x140003274  sub     rsp, 58h
0x140003278  mov     rax, cs:__security_cookie
0x14000327f  xor     rax, rsp
0x140003282  mov     [rsp+58h+var_18], rax
0x140003287  lea     rax, [rsp+58h+var_28]
0x14000328c  mov     r9d, 1
0x140003292  mov     [rsp+58h+var_38], rax
0x140003297  call    McGenEventWrite_EtwWriteTransfer
0x14000329c  mov     rcx, [rsp+58h+var_18]
0x1400032a1  xor     rcx, rsp; StackCookie
0x1400032a4  call    __security_check_cookie
0x1400032a9  add     rsp, 58h
0x1400032ad  retn
```
