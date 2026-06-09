# McTemplateU0q_EventWriteTransfer

- ea: `0x180007c88`
- end: `0x180007cd7`
- name: `McTemplateU0q_EventWriteTransfer`
- size: `79`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800067c0`
- `0x180006950`
- `0x180006fa0`
- `0x180009e60`
- `0x18000ab30`
- `0x18000c618`
- `0x180010938`

## callees

- `0x18000247c`
- `0x1800180f0`

## pseudocode

```c
ULONG __fastcall McTemplateU0q_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  int *v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v6 = 4;
  v5 = &v7;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x180007c88  mov     r11, rsp
0x180007c8b  mov     [r11+18h], r8d
0x180007c8f  sub     rsp, 68h
0x180007c93  mov     rax, cs:__security_cookie
0x180007c9a  xor     rax, rsp
0x180007c9d  mov     [rsp+68h+var_18], rax
0x180007ca2  lea     rax, [r11+18h]
0x180007ca6  mov     qword ptr [r11-20h], 4
0x180007cae  mov     [r11-28h], rax
0x180007cb2  mov     r9d, 2
0x180007cb8  lea     rax, [r11-38h]
0x180007cbc  mov     [r11-48h], rax
0x180007cc0  call    McGenEventWrite_EventWriteTransfer
0x180007cc5  mov     rcx, [rsp+68h+var_18]
0x180007cca  xor     rcx, rsp; StackCookie
0x180007ccd  call    __security_check_cookie
0x180007cd2  add     rsp, 68h
0x180007cd6  retn
```
