# McTemplateK0p_EtwWriteTransfer

- ea: `0x1400083b4`
- end: `0x140008404`
- name: `McTemplateK0p_EtwWriteTransfer`
- size: `80`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `37`
- callee_count: `2`
- tags: ``

## callers

- `0x1400078c8`
- `0x140008740`
- `0x140009500`
- `0x14000a310`
- `0x14000ce50`
- `0x140014f80`
- `0x1400165c0`
- `0x140024970`
- `0x140024af0`
- `0x140024c70`
- `0x140024db0`
- `0x140024f20`
- `0x140025070`
- `0x140025160`
- `0x140025300`
- `0x140025460`
- `0x140025590`
- `0x14002bc18`
- `0x14002c0b8`
- `0x14002c2dc`
- `0x14002c90c`
- `0x14002cbe0`
- `0x14002cda0`
- `0x14002cf60`
- `0x14002d28c`
- `0x14002fa84`
- `0x1400304a8`
- `0x140030540`
- `0x1400305e8`
- `0x140033234`
- `0x14003f5b4`
- `0x140079940`
- `0x14007a4e0`
- `0x14007a780`
- `0x140080590`
- `0x140081660`
- `0x140081bb0`

## callees

- `0x1400019f8`
- `0x140045530`

## pseudocode

```c
NTSTATUS McTemplateK0p_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const GUID *a3, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  va_list v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  v6 = 8;
  va_copy(v5, va);
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x1400083b4  mov     r11, rsp
0x1400083b7  mov     [r11+20h], r9
0x1400083bb  sub     rsp, 68h
0x1400083bf  mov     rax, cs:__security_cookie
0x1400083c6  xor     rax, rsp
0x1400083c9  mov     [rsp+68h+var_18], rax
0x1400083ce  lea     rax, [r11+20h]
0x1400083d2  mov     qword ptr [r11-20h], 8
0x1400083da  mov     [r11-28h], rax
0x1400083de  mov     r9d, 2
0x1400083e4  lea     rax, [r11-38h]
0x1400083e8  mov     [r11-48h], rax
0x1400083ec  call    McGenEventWrite_EtwWriteTransfer
0x1400083f1  mov     rcx, [rsp+68h+var_18]
0x1400083f6  xor     rcx, rsp; StackCookie
0x1400083f9  call    __security_check_cookie
0x1400083fe  add     rsp, 68h
0x140008402  retn
```
