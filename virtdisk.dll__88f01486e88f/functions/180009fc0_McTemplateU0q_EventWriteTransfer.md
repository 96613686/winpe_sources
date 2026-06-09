# McTemplateU0q_EventWriteTransfer

- ea: `0x180009fc0`
- end: `0x18000a010`
- name: `McTemplateU0q_EventWriteTransfer`
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
0x180009fc0  mov     r11, rsp
0x180009fc3  mov     [r11+18h], r8d
0x180009fc7  sub     rsp, 68h
0x180009fcb  mov     rax, cs:__security_cookie
0x180009fd2  xor     rax, rsp
0x180009fd5  mov     [rsp+68h+var_18], rax
0x180009fda  lea     rax, [r11+18h]
0x180009fde  mov     qword ptr [r11-20h], 4
0x180009fe6  mov     [r11-28h], rax
0x180009fea  mov     r9d, 2
0x180009ff0  lea     rax, [r11-38h]
0x180009ff4  mov     [r11-48h], rax
0x180009ff8  call    McGenEventWrite_EventWriteTransfer
0x180009ffd  mov     rcx, [rsp+68h+var_18]
0x18000a002  xor     rcx, rsp; StackCookie
0x18000a005  call    __security_check_cookie
0x18000a00a  add     rsp, 68h
0x18000a00e  retn
```
