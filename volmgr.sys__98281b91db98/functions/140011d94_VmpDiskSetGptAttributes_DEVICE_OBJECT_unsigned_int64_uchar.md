# VmpDiskSetGptAttributes(_DEVICE_OBJECT *,unsigned __int64,uchar)

- ea: `0x140011d94`
- end: `0x140011df8`
- name: `?VmpDiskSetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@_KE@Z`
- size: `100`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, unsigned __int64, unsigned __int8)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e888`
- `0x140010898`
- `0x140013ba0`
- `0x140013e00`

## callees

- `0x140002db0`
- `0x140005050`

## pseudocode

```c
NTSTATUS __fastcall VmpDiskSetGptAttributes(struct _DEVICE_OBJECT *a1, __int64 a2)
{
  int v3; // [rsp+30h] [rbp-28h] BYREF
  char v4; // [rsp+34h] [rbp-24h]
  __int16 v5; // [rsp+35h] [rbp-23h]
  char v6; // [rsp+37h] [rbp-21h]
  __int64 v7; // [rsp+38h] [rbp-20h]
  __int64 v8; // [rsp+40h] [rbp-18h]

  v5 = 0;
  v6 = 0;
  v3 = 24;
  v4 = 1;
  v7 = a2;
  v8 = -1;
  return VmpSendDeviceControl(a1, 0x7C0ECu, &v3, 0x18u, 0, 0);
}

```

## disassembly

```asm
0x140011d94  mov     r11, rsp
0x140011d97  sub     rsp, 58h
0x140011d9b  mov     rax, cs:__security_cookie
0x140011da2  xor     rax, rsp
0x140011da5  mov     [rsp+58h+var_10], rax
0x140011daa  xor     r8d, r8d
0x140011dad  mov     [r11-23h], r8w
0x140011db2  mov     [r11-21h], r8b
0x140011db6  mov     [r11-30h], r8d
0x140011dba  lea     r9d, [r8+18h]; InputBufferLength
0x140011dbe  mov     [r11-38h], r8
0x140011dc2  mov     [r11-28h], r9d
0x140011dc6  lea     r8, [r11-28h]; InputBuffer
0x140011dca  mov     [rsp+58h+var_24], 1
0x140011dcf  mov     [r11-20h], rdx
0x140011dd3  mov     edx, 7C0ECh; IoControlCode
0x140011dd8  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFFh
0x140011de0  call    VmpSendDeviceControl
0x140011de5  mov     rcx, [rsp+58h+var_10]
0x140011dea  xor     rcx, rsp; StackCookie
0x140011ded  call    __security_check_cookie
0x140011df2  add     rsp, 58h
0x140011df6  retn
```
