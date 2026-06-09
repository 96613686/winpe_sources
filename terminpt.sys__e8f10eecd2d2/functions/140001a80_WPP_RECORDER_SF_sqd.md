# WPP_RECORDER_SF_sqd

- ea: `0x140001a80`
- end: `0x140001b78`
- name: `WPP_RECORDER_SF_sqd`
- size: `248`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010c0`
- `0x1400015dc`
- `0x140001ce0`
- `0x140002a7c`
- `0x1400092f0`
- `0x1400098b4`
- `0x1400099f0`
- `0x140009b60`
- `0x140009d48`
- `0x140009e60`
- `0x140009fb0`
- `0x14000a1a0`
- `0x14000a250`
- `0x14000a300`
- `0x14000b2d0`

## callees

- `0x140001a80`
- `0x140003130`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001b5a`
- `WppRecorder!WppAutoLogTrace` at `0x140001b5a`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sqd(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, __int64 a6, ...)
{
  int v9; // [rsp+20h] [rbp-48h]
  __int64 v10; // [rsp+A0h] [rbp+38h] BYREF
  va_list va; // [rsp+A0h] [rbp+38h]
  va_list va1; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v10 = va_arg(va1, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, const char *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      " ",
      2,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, 0, 1, a5, v9, " ", 2, (__int64 *)va);
}

```

## disassembly

```asm
0x140001a80  mov     r11, rsp
0x140001a83  mov     [r11+8], rbx
0x140001a87  mov     [r11+10h], rdi
0x140001a8b  push    r15
0x140001a8d  sub     rsp, 60h
0x140001a91  mov     rdi, rcx
0x140001a94  movzx   ebx, r9w
0x140001a98  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a9f  lea     r15, asc_140005150; " "
0x140001aa6  mov     eax, [rcx+2Ch]
0x140001aa9  test    al, 1
0x140001aab  jz      short loc_140001B01
0x140001aad  mov     rax, cs:pfnWppTraceMessage
0x140001ab4  lea     rdx, [r11+40h]
0x140001ab8  mov     r8, [rsp+68h+arg_20]
0x140001ac0  mov     r9d, ebx
0x140001ac3  mov     rcx, [rcx+18h]
0x140001ac7  mov     qword ptr [r11-18h], 0
0x140001acf  mov     qword ptr [r11-20h], 4
0x140001ad7  mov     [r11-28h], rdx
0x140001adb  lea     rdx, [r11+38h]
0x140001adf  mov     qword ptr [r11-30h], 8
0x140001ae7  mov     [r11-38h], rdx
0x140001aeb  mov     edx, 2Bh ; '+'
0x140001af0  mov     qword ptr [r11-40h], 2
0x140001af8  mov     [r11-48h], r15
0x140001afc  call    _guard_dispatch_icall
0x140001b01  mov     r9, [rsp+68h+arg_20]
0x140001b09  lea     rax, [rsp+68h+arg_38]
0x140001b11  mov     [rsp+68h+var_10], 0
0x140001b1a  xor     edx, edx
0x140001b1c  mov     [rsp+68h+var_18], 4
0x140001b25  mov     rcx, rdi
0x140001b28  mov     [rsp+68h+var_20], rax
0x140001b2d  lea     rax, [rsp+68h+arg_30]
0x140001b35  mov     [rsp+68h+var_28], 8
0x140001b3e  mov     [rsp+68h+var_30], rax
0x140001b43  lea     r8d, [rdx+1]
0x140001b47  mov     [rsp+68h+var_38], 2
0x140001b50  mov     [rsp+68h+var_40], r15
0x140001b55  mov     [rsp+68h+var_48], bx
0x140001b5a  call    cs:__imp_WppAutoLogTrace
0x140001b61  nop     dword ptr [rax+rax+00h]
0x140001b66  mov     rbx, [rsp+68h+arg_0]
0x140001b6b  mov     rdi, [rsp+68h+arg_8]
0x140001b70  add     rsp, 60h
0x140001b74  pop     r15
0x140001b76  retn
```
