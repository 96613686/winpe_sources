# McTemplateU0dq_EventWriteTransfer

- ea: `0x180006160`
- end: `0x1800061c3`
- name: `McTemplateU0dq_EventWriteTransfer`
- size: `99`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x180001080`
- `0x1800016a0`
- `0x180001ea0`
- `0x180002390`
- `0x180002530`
- `0x1800033c0`
- `0x18000e6e0`
- `0x18000e9c0`
- `0x18000eca0`
- `0x18000ef50`
- `0x18000f210`

## callees

- `0x1800061d0`
- `0x180006620`

## pseudocode

```c
ULONG __fastcall McTemplateU0dq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 3u, &v5);
}

```

## disassembly

```asm
0x180006160  mov     r11, rsp
0x180006163  mov     [r11+20h], r9d
0x180006167  mov     [r11+18h], r8d
0x18000616b  sub     rsp, 78h
0x18000616f  mov     rax, cs:__security_cookie
0x180006176  xor     rax, rsp
0x180006179  mov     [rsp+78h+var_18], rax
0x18000617e  lea     rax, [r11+18h]
0x180006182  mov     qword ptr [r11-30h], 4
0x18000618a  mov     [r11-38h], rax
0x18000618e  mov     r9d, 3
0x180006194  lea     rax, [r11+20h]
0x180006198  mov     qword ptr [r11-20h], 4
0x1800061a0  mov     [r11-28h], rax
0x1800061a4  lea     rax, [r11-48h]
0x1800061a8  mov     [r11-58h], rax
0x1800061ac  call    McGenEventWrite_EventWriteTransfer
0x1800061b1  mov     rcx, [rsp+78h+var_18]
0x1800061b6  xor     rcx, rsp; StackCookie
0x1800061b9  call    __security_check_cookie
0x1800061be  add     rsp, 78h
0x1800061c2  retn
```
