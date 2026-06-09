# WPP_RECORDER_SF_dDdd

- ea: `0x1400062f4`
- end: `0x1400063ff`
- name: `WPP_RECORDER_SF_dDdd`
- size: `267`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400065e0`
- `0x1400093e0`
- `0x1400099d0`

## callees

- `0x1400062f4`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400063e0`
- `WppRecorder!WppAutoLogTrace` at `0x1400063e0`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dDdd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, __int64 a5, ...)
{
  int v8; // [rsp+20h] [rbp-58h]
  __int64 v9; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v11; // [rsp+B0h] [rbp+38h] BYREF
  va_list va1; // [rsp+B0h] [rbp+38h]
  __int64 v13; // [rsp+B8h] [rbp+40h] BYREF
  va_list va2; // [rsp+B8h] [rbp+40h]
  va_list va3; // [rsp+C0h] [rbp+48h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v13 = va_arg(va3, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(_DEVICE_OBJECT *, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      va3,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 4, 4, a5, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x1400062f4  mov     r11, rsp
0x1400062f7  mov     [r11+8], rbx
0x1400062fb  mov     [r11+10h], rsi
0x1400062ff  push    rdi
0x140006300  sub     rsp, 70h
0x140006304  mov     rdi, rcx
0x140006307  movzx   ebx, r9w
0x14000630b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006312  mov     esi, 4
0x140006317  mov     eax, [rcx+2Ch]
0x14000631a  test    al, 8
0x14000631c  jz      short loc_14000637A
0x14000631e  cmp     [rcx+29h], sil
0x140006322  jb      short loc_14000637A
0x140006324  mov     rax, cs:pfnWppTraceMessage
0x14000632b  lea     rdx, [r11+48h]
0x14000632f  mov     r8, [rsp+78h+arg_20]
0x140006337  mov     r9d, ebx
0x14000633a  mov     rcx, [rcx+18h]
0x14000633e  mov     qword ptr [r11-18h], 0
0x140006346  mov     [r11-20h], rsi
0x14000634a  mov     [r11-28h], rdx
0x14000634e  lea     rdx, [r11+40h]
0x140006352  mov     [r11-30h], rsi
0x140006356  mov     [r11-38h], rdx
0x14000635a  lea     rdx, [r11+38h]
0x14000635e  mov     [r11-40h], rsi
0x140006362  mov     [r11-48h], rdx
0x140006366  lea     rdx, [r11+30h]
0x14000636a  mov     [r11-50h], rsi
0x14000636e  mov     [r11-58h], rdx
0x140006372  lea     edx, [rsi+27h]
0x140006375  call    _guard_dispatch_icall
0x14000637a  mov     r9, [rsp+78h+arg_20]
0x140006382  lea     rax, [rsp+78h+arg_40]
0x14000638a  mov     [rsp+78h+var_10], 0
0x140006393  mov     r8d, esi
0x140006396  mov     [rsp+78h+var_18], rsi
0x14000639b  mov     edx, esi
0x14000639d  mov     [rsp+78h+var_20], rax
0x1400063a2  mov     rcx, rdi
0x1400063a5  mov     [rsp+78h+var_28], rsi
0x1400063aa  lea     rax, [rsp+78h+arg_38]
0x1400063b2  mov     [rsp+78h+var_30], rax
0x1400063b7  lea     rax, [rsp+78h+arg_30]
0x1400063bf  mov     [rsp+78h+var_38], rsi
0x1400063c4  mov     [rsp+78h+var_40], rax
0x1400063c9  lea     rax, [rsp+78h+arg_28]
0x1400063d1  mov     [rsp+78h+var_48], rsi
0x1400063d6  mov     [rsp+78h+var_50], rax
0x1400063db  mov     [rsp+78h+var_58], bx
0x1400063e0  call    cs:__imp_WppAutoLogTrace
0x1400063e7  nop     dword ptr [rax+rax+00h]
0x1400063ec  lea     r11, [rsp+78h+var_8]
0x1400063f1  mov     rbx, [r11+10h]
0x1400063f5  mov     rsi, [r11+18h]
0x1400063f9  mov     rsp, r11
0x1400063fc  pop     rdi
0x1400063fd  retn
```
