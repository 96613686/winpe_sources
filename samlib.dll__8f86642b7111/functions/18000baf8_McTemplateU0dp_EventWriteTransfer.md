# McTemplateU0dp_EventWriteTransfer

- ea: `0x18000baf8`
- end: `0x18000bb5b`
- name: `McTemplateU0dp_EventWriteTransfer`
- size: `99`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a80`
- `0x180002e90`
- `0x180004dd0`
- `0x18000fed0`
- `0x180010170`

## callees

- `0x1800061d0`
- `0x180006620`

## pseudocode

```c
ULONG McTemplateU0dp_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-48h] BYREF
  int *v5; // [rsp+40h] [rbp-38h]
  __int64 v6; // [rsp+48h] [rbp-30h]
  va_list v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]
  int v9; // [rsp+90h] [rbp+18h] BYREF
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  v9 = a3;
  v6 = 4;
  v5 = &v9;
  v8 = 8;
  va_copy(v7, va);
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 3u, &v4);
}

```

## disassembly

```asm
0x18000baf8  mov     r11, rsp
0x18000bafb  mov     [r11+20h], r9
0x18000baff  mov     [r11+18h], r8d
0x18000bb03  sub     rsp, 78h
0x18000bb07  mov     rax, cs:__security_cookie
0x18000bb0e  xor     rax, rsp
0x18000bb11  mov     [rsp+78h+var_18], rax
0x18000bb16  lea     rax, [r11+18h]
0x18000bb1a  mov     qword ptr [r11-30h], 4
0x18000bb22  mov     [r11-38h], rax
0x18000bb26  mov     r9d, 3
0x18000bb2c  lea     rax, [r11+20h]
0x18000bb30  mov     qword ptr [r11-20h], 8
0x18000bb38  mov     [r11-28h], rax
0x18000bb3c  lea     rax, [r11-48h]
0x18000bb40  mov     [r11-58h], rax
0x18000bb44  call    McGenEventWrite_EventWriteTransfer
0x18000bb49  mov     rcx, [rsp+78h+var_18]
0x18000bb4e  xor     rcx, rsp; StackCookie
0x18000bb51  call    __security_check_cookie
0x18000bb56  add     rsp, 78h
0x18000bb5a  retn
```
