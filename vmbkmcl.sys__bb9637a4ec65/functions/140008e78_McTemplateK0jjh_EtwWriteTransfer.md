# McTemplateK0jjh_EtwWriteTransfer

- ea: `0x140008e78`
- end: `0x140008eea`
- name: `McTemplateK0jjh_EtwWriteTransfer`
- size: `114`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x1400026f0`

## callees

- `0x140008e18`
- `0x140011e90`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0jjh_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-58h] BYREF
  __int64 v8; // [rsp+40h] [rbp-48h]
  __int64 v9; // [rsp+48h] [rbp-40h]
  __int64 v10; // [rsp+50h] [rbp-38h]
  __int64 v11; // [rsp+58h] [rbp-30h]
  __int64 *v12; // [rsp+60h] [rbp-28h]
  __int64 v13; // [rsp+68h] [rbp-20h]

  v10 = a5;
  v12 = &a6;
  v8 = a4;
  v9 = 16;
  v11 = 16;
  v13 = 2;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 4u, &v7);
}

```

## disassembly

```asm
0x140008e78  mov     r11, rsp
0x140008e7b  sub     rsp, 88h
0x140008e82  mov     rax, cs:__security_cookie
0x140008e89  xor     rax, rsp
0x140008e8c  mov     [rsp+88h+var_18], rax
0x140008e91  mov     rax, [rsp+88h+arg_20]
0x140008e99  mov     [r11-38h], rax
0x140008e9d  lea     rax, [r11+30h]
0x140008ea1  mov     [r11-28h], rax
0x140008ea5  lea     rax, [r11-58h]
0x140008ea9  mov     [r11-48h], r9
0x140008ead  mov     r9d, 4
0x140008eb3  mov     [r11-68h], rax
0x140008eb7  mov     qword ptr [r11-40h], 10h
0x140008ebf  mov     qword ptr [r11-30h], 10h
0x140008ec7  mov     qword ptr [r11-20h], 2
0x140008ecf  call    McGenEventWrite_EtwWriteTransfer
0x140008ed4  mov     rcx, [rsp+88h+var_18]
0x140008ed9  xor     rcx, rsp; StackCookie
0x140008edc  call    __security_check_cookie
0x140008ee1  add     rsp, 88h
0x140008ee8  retn
```
