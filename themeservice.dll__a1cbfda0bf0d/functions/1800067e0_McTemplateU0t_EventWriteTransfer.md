# McTemplateU0t_EventWriteTransfer

- ea: `0x1800067e0`
- end: `0x18000682f`
- name: `McTemplateU0t_EventWriteTransfer`
- size: `79`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003790`
- `0x180003e1c`
- `0x180004d80`
- `0x180006600`

## callees

- `0x180004084`
- `0x18000fa00`

## pseudocode

```c
ULONG __fastcall McTemplateU0t_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
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
0x1800067e0  mov     r11, rsp
0x1800067e3  mov     [r11+18h], r8d
0x1800067e7  sub     rsp, 68h
0x1800067eb  mov     rax, cs:__security_cookie
0x1800067f2  xor     rax, rsp
0x1800067f5  mov     [rsp+68h+var_18], rax
0x1800067fa  lea     rax, [r11+18h]
0x1800067fe  mov     qword ptr [r11-20h], 4
0x180006806  mov     [r11-28h], rax
0x18000680a  mov     r9d, 2
0x180006810  lea     rax, [r11-38h]
0x180006814  mov     [r11-48h], rax
0x180006818  call    McGenEventWrite_EventWriteTransfer
0x18000681d  mov     rcx, [rsp+68h+var_18]
0x180006822  xor     rcx, rsp; StackCookie
0x180006825  call    __security_check_cookie
0x18000682a  add     rsp, 68h
0x18000682e  retn
```
