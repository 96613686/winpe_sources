# McTemplateU0p_EventWriteTransfer

- ea: `0x180029e28`
- end: `0x180029e77`
- name: `McTemplateU0p_EventWriteTransfer`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800292e8`
- `0x18002c4c0`
- `0x18002e54c`
- `0x18002e918`
- `0x1800302e0`

## callees

- `0x180001ec0`
- `0x180029dd0`

## pseudocode

```c
ULONG __fastcall McTemplateU0p_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  __int64 v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v6 = 8;
  v5 = &v7;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x180029e28  mov     r11, rsp
0x180029e2b  mov     [r11+18h], r8
0x180029e2f  sub     rsp, 68h
0x180029e33  mov     rax, cs:__security_cookie
0x180029e3a  xor     rax, rsp
0x180029e3d  mov     [rsp+68h+var_18], rax
0x180029e42  lea     rax, [r11+18h]
0x180029e46  mov     qword ptr [r11-20h], 8
0x180029e4e  mov     [r11-28h], rax
0x180029e52  mov     r9d, 2
0x180029e58  lea     rax, [r11-38h]
0x180029e5c  mov     [r11-48h], rax
0x180029e60  call    McGenEventWrite_EventWriteTransfer
0x180029e65  mov     rcx, [rsp+68h+var_18]
0x180029e6a  xor     rcx, rsp; StackCookie
0x180029e6d  call    __security_check_cookie
0x180029e72  add     rsp, 68h
0x180029e76  retn
```
