# McTemplateU0dq_EventWriteTransfer

- ea: `0x180006770`
- end: `0x1800067da`
- name: `McTemplateU0dq_EventWriteTransfer`
- size: `106`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002270`

## callees

- `0x180004084`
- `0x18000fa00`

## pseudocode

```c
ULONG __fastcall McTemplateU0dq_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)"\x1B", a3, 3u, &v5);
}

```

## disassembly

```asm
0x180006770  mov     r11, rsp
0x180006773  mov     [r11+20h], r9d
0x180006777  mov     [r11+18h], r8d
0x18000677b  sub     rsp, 78h
0x18000677f  mov     rax, cs:__security_cookie
0x180006786  xor     rax, rsp
0x180006789  mov     [rsp+78h+var_18], rax
0x18000678e  lea     rax, [r11+18h]
0x180006792  mov     qword ptr [r11-30h], 4
0x18000679a  mov     [r11-38h], rax
0x18000679e  lea     rdx, ShellTraceId_ThemeService_GetClientSessionData_Stop; "\x1B"
0x1800067a5  lea     rax, [r11+20h]
0x1800067a9  mov     qword ptr [r11-20h], 4
0x1800067b1  mov     [r11-28h], rax
0x1800067b5  mov     r9d, 3
0x1800067bb  lea     rax, [r11-48h]
0x1800067bf  mov     [r11-58h], rax
0x1800067c3  call    McGenEventWrite_EventWriteTransfer
0x1800067c8  mov     rcx, [rsp+78h+var_18]
0x1800067cd  xor     rcx, rsp; StackCookie
0x1800067d0  call    __security_check_cookie
0x1800067d5  add     rsp, 78h
0x1800067d9  retn
```
