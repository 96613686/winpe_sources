# McTemplateK0qq_EtwWriteTransfer

- ea: `0x140014d00`
- end: `0x140014d60`
- name: `McTemplateK0qq_EtwWriteTransfer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c618`

## callees

- `0x1400095bc`
- `0x14001ede0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qq_EtwWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  int *v7; // [rsp+40h] [rbp-38h]
  __int64 v8; // [rsp+48h] [rbp-30h]
  __int64 *v9; // [rsp+50h] [rbp-28h]
  __int64 v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v8 = 4;
  v7 = &v11;
  v10 = 4;
  v9 = &a5;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 3u, &v6);
}

```

## disassembly

```asm
0x140014d00  mov     r11, rsp
0x140014d03  mov     [r11+20h], r9d
0x140014d07  sub     rsp, 78h
0x140014d0b  mov     rax, cs:__security_cookie
0x140014d12  xor     rax, rsp
0x140014d15  mov     [rsp+78h+var_18], rax
0x140014d1a  lea     rax, [r11+20h]
0x140014d1e  mov     qword ptr [r11-30h], 4
0x140014d26  mov     [r11-38h], rax
0x140014d2a  mov     r9d, 3
0x140014d30  lea     rax, [r11+28h]
0x140014d34  mov     qword ptr [r11-20h], 4
0x140014d3c  mov     [r11-28h], rax
0x140014d40  lea     rax, [r11-48h]
0x140014d44  mov     [r11-58h], rax
0x140014d48  call    McGenEventWrite_EtwWriteTransfer
0x140014d4d  mov     rcx, [rsp+78h+var_18]
0x140014d52  xor     rcx, rsp; StackCookie
0x140014d55  call    __security_check_cookie
0x140014d5a  add     rsp, 78h
0x140014d5e  retn
```
