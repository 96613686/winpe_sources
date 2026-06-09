# McTemplateK0pq_EtwWriteTransfer

- ea: `0x140001f94`
- end: `0x140001ff4`
- name: `McTemplateK0pq_EtwWriteTransfer`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x140003a80`
- `0x140007b70`
- `0x14000ed20`
- `0x1400165c0`
- `0x140018090`
- `0x1400286e0`
- `0x14002e514`
- `0x14003f5b4`
- `0x140077238`
- `0x140078bd0`
- `0x140079940`
- `0x14007a4e0`
- `0x14007ab24`
- `0x14007afe0`
- `0x14007f118`
- `0x140080590`
- `0x140081660`
- `0x140084d2c`

## callees

- `0x1400019f8`
- `0x140045530`

## pseudocode

```c
NTSTATUS McTemplateK0pq_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const GUID *a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-48h] BYREF
  va_list v5; // [rsp+40h] [rbp-38h]
  __int64 v6; // [rsp+48h] [rbp-30h]
  va_list v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]
  __int64 v9; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  va_list va1; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v9 = va_arg(va1, _QWORD);
  v6 = 8;
  va_copy(v5, va);
  v8 = 4;
  va_copy(v7, va1);
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 3u, &v4);
}

```

## disassembly

```asm
0x140001f94  mov     r11, rsp
0x140001f97  mov     [r11+20h], r9
0x140001f9b  sub     rsp, 78h
0x140001f9f  mov     rax, cs:__security_cookie
0x140001fa6  xor     rax, rsp
0x140001fa9  mov     [rsp+78h+var_18], rax
0x140001fae  lea     rax, [r11+20h]
0x140001fb2  mov     qword ptr [r11-30h], 8
0x140001fba  mov     [r11-38h], rax
0x140001fbe  mov     r9d, 3
0x140001fc4  lea     rax, [r11+28h]
0x140001fc8  mov     qword ptr [r11-20h], 4
0x140001fd0  mov     [r11-28h], rax
0x140001fd4  lea     rax, [r11-48h]
0x140001fd8  mov     [r11-58h], rax
0x140001fdc  call    McGenEventWrite_EtwWriteTransfer
0x140001fe1  mov     rcx, [rsp+78h+var_18]
0x140001fe6  xor     rcx, rsp; StackCookie
0x140001fe9  call    __security_check_cookie
0x140001fee  add     rsp, 78h
0x140001ff2  retn
```
