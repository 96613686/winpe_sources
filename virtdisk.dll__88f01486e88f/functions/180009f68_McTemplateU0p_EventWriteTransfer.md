# McTemplateU0p_EventWriteTransfer

- ea: `0x180009f68`
- end: `0x180009fb8`
- name: `McTemplateU0p_EventWriteTransfer`
- size: `80`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800025c0`
- `0x180009b90`

## callees

- `0x180005730`
- `0x1800097bc`

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
0x180009f68  mov     r11, rsp
0x180009f6b  mov     [r11+18h], r8
0x180009f6f  sub     rsp, 68h
0x180009f73  mov     rax, cs:__security_cookie
0x180009f7a  xor     rax, rsp
0x180009f7d  mov     [rsp+68h+var_18], rax
0x180009f82  lea     rax, [r11+18h]
0x180009f86  mov     qword ptr [r11-20h], 8
0x180009f8e  mov     [r11-28h], rax
0x180009f92  mov     r9d, 2
0x180009f98  lea     rax, [r11-38h]
0x180009f9c  mov     [r11-48h], rax
0x180009fa0  call    McGenEventWrite_EventWriteTransfer
0x180009fa5  mov     rcx, [rsp+68h+var_18]
0x180009faa  xor     rcx, rsp; StackCookie
0x180009fad  call    __security_check_cookie
0x180009fb2  add     rsp, 68h
0x180009fb6  retn
```
