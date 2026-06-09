# WPP_RECORDER_SF_ddd

- ea: `0x140001a4c`
- end: `0x140001b43`
- name: `WPP_RECORDER_SF_ddd`
- size: `247`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e04`
- `0x140005838`
- `0x140009634`
- `0x14000e19c`

## callees

- `0x140001a4c`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001b24`
- `WppRecorder!WppAutoLogTrace` at `0x140001b24`

## pseudocode

```c
__int64 WPP_RECORDER_SF_ddd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, __int64 a5, ...)
{
  int v8; // [rsp+20h] [rbp-58h]
  int v9[4]; // [rsp+60h] [rbp-18h] BYREF
  __int64 v10; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v10 = va_arg(va1, _QWORD);
  v9[0] = -1073741811;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(_DEVICE_OBJECT *, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, int *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      v9,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 2, 3, a5, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x140001a4c  mov     r11, rsp
0x140001a4f  mov     [r11+8], rbx
0x140001a53  mov     [r11+10h], rsi
0x140001a57  push    rdi
0x140001a58  sub     rsp, 70h
0x140001a5c  mov     rdi, rcx
0x140001a5f  mov     [rsp+78h+var_18], 0C000000Dh
0x140001a67  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a6e  mov     esi, 4
0x140001a73  movzx   ebx, r9w
0x140001a77  mov     eax, [rcx+2Ch]
0x140001a7a  test    sil, al
0x140001a7d  jz      short loc_140001ACF
0x140001a7f  cmp     byte ptr [rcx+29h], 2
0x140001a83  jb      short loc_140001ACF
0x140001a85  mov     rax, cs:pfnWppTraceMessage
0x140001a8c  lea     rdx, [r11-18h]
0x140001a90  mov     r8, [rsp+78h+arg_20]
0x140001a98  mov     r9d, ebx
0x140001a9b  mov     rcx, [rcx+18h]
0x140001a9f  mov     qword ptr [r11-28h], 0
0x140001aa7  mov     [r11-30h], rsi
0x140001aab  mov     [r11-38h], rdx
0x140001aaf  lea     rdx, [r11+38h]
0x140001ab3  mov     [r11-40h], rsi
0x140001ab7  mov     [r11-48h], rdx
0x140001abb  lea     rdx, [r11+30h]
0x140001abf  mov     [r11-50h], rsi
0x140001ac3  mov     [r11-58h], rdx
0x140001ac7  lea     edx, [rsi+27h]
0x140001aca  call    _guard_dispatch_icall
0x140001acf  mov     r9, [rsp+78h+arg_20]
0x140001ad7  lea     rax, [rsp+78h+var_18]
0x140001adc  mov     [rsp+78h+var_20], 0
0x140001ae5  mov     edx, 2
0x140001aea  mov     [rsp+78h+var_28], rsi
0x140001aef  mov     rcx, rdi
0x140001af2  mov     [rsp+78h+var_30], rax
0x140001af7  lea     rax, [rsp+78h+arg_30]
0x140001aff  mov     [rsp+78h+var_38], rsi
0x140001b04  mov     [rsp+78h+var_40], rax
0x140001b09  lea     r8d, [rdx+1]
0x140001b0d  lea     rax, [rsp+78h+arg_28]
0x140001b15  mov     [rsp+78h+var_48], rsi
0x140001b1a  mov     [rsp+78h+var_50], rax
0x140001b1f  mov     [rsp+78h+var_58], bx
0x140001b24  call    cs:__imp_WppAutoLogTrace
0x140001b2b  nop     dword ptr [rax+rax+00h]
0x140001b30  lea     r11, [rsp+78h+var_8]
0x140001b35  mov     rbx, [r11+10h]
0x140001b39  mov     rsi, [r11+18h]
0x140001b3d  mov     rsp, r11
0x140001b40  pop     rdi
0x140001b41  retn
```
