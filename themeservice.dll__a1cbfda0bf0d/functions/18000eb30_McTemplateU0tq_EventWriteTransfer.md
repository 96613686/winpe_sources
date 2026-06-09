# McTemplateU0tq_EventWriteTransfer

- ea: `0x18000eb30`
- end: `0x18000eb9a`
- name: `McTemplateU0tq_EventWriteTransfer`
- size: `106`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004d80`

## callees

- `0x180004084`
- `0x18000fa00`

## pseudocode

```c
ULONG __fastcall McTemplateU0tq_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-48h] BYREF
  int *v6; // [rsp+40h] [rbp-38h]
  __int64 v7; // [rsp+48h] [rbp-30h]
  int *v8; // [rsp+50h] [rbp-28h]
  __int64 v9; // [rsp+58h] [rbp-20h]
  int v10; // [rsp+90h] [rbp+18h] BYREF
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v10 = a3;
  v7 = 4;
  v6 = &v10;
  v9 = 4;
  v8 = &v11;
  return McGenEventWrite_EventWriteTransfer(
           a1,
           (const EVENT_DESCRIPTOR *)ShellTraceId_ThemeService_SignalRequestPending_Stop,
           a3,
           3u,
           &v5);
}

```

## disassembly

```asm
0x18000eb30  mov     r11, rsp
0x18000eb33  mov     [r11+20h], r9d
0x18000eb37  mov     [r11+18h], r8d
0x18000eb3b  sub     rsp, 78h
0x18000eb3f  mov     rax, cs:__security_cookie
0x18000eb46  xor     rax, rsp
0x18000eb49  mov     [rsp+78h+var_18], rax
0x18000eb4e  lea     rax, [r11+18h]
0x18000eb52  mov     qword ptr [r11-30h], 4
0x18000eb5a  mov     [r11-38h], rax
0x18000eb5e  lea     rdx, ShellTraceId_ThemeService_SignalRequestPending_Stop
0x18000eb65  lea     rax, [r11+20h]
0x18000eb69  mov     qword ptr [r11-20h], 4
0x18000eb71  mov     [r11-28h], rax
0x18000eb75  mov     r9d, 3
0x18000eb7b  lea     rax, [r11-48h]
0x18000eb7f  mov     [r11-58h], rax
0x18000eb83  call    McGenEventWrite_EventWriteTransfer
0x18000eb88  mov     rcx, [rsp+78h+var_18]
0x18000eb8d  xor     rcx, rsp; StackCookie
0x18000eb90  call    __security_check_cookie
0x18000eb95  add     rsp, 78h
0x18000eb99  retn
```
