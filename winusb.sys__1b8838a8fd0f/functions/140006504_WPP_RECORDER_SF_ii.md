# WPP_RECORDER_SF_ii

- ea: `0x140006504`
- end: `0x1400065d3`
- name: `WPP_RECORDER_SF_ii`
- size: `207`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140007b3c`
- `0x140007fdc`
- `0x140008388`

## callees

- `0x140006504`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400065b6`
- `WppRecorder!WppAutoLogTrace` at `0x1400065b6`

## pseudocode

```c
__int64 WPP_RECORDER_SF_ii(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-38h]
  __int64 v9; // [rsp+88h] [rbp+30h] BYREF
  va_list va; // [rsp+88h] [rbp+30h]
  va_list va1; // [rsp+90h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(_DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids,
      a4,
      (__int64 *)va,
      8,
      va1,
      8,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 2, 3, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x140006504  mov     r11, rsp
0x140006507  mov     [r11+8], rbx
0x14000650b  mov     [r11+10h], rsi
0x14000650f  push    rdi
0x140006510  sub     rsp, 50h
0x140006514  mov     rdi, rcx
0x140006517  movzx   ebx, r9w
0x14000651b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006522  mov     esi, 8
0x140006527  mov     eax, [rcx+2Ch]
0x14000652a  test    al, 4
0x14000652c  jz      short loc_140006571
0x14000652e  cmp     byte ptr [rcx+29h], 2
0x140006532  jb      short loc_140006571
0x140006534  mov     rax, cs:pfnWppTraceMessage
0x14000653b  lea     rdx, [r11+38h]
0x14000653f  mov     rcx, [rcx+18h]
0x140006543  lea     r8, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x14000654a  mov     qword ptr [r11-18h], 0
0x140006552  mov     r9d, ebx
0x140006555  mov     [r11-20h], rsi
0x140006559  mov     [r11-28h], rdx
0x14000655d  lea     rdx, [r11+30h]
0x140006561  mov     [r11-30h], rsi
0x140006565  mov     [r11-38h], rdx
0x140006569  lea     edx, [rsi+23h]
0x14000656c  call    _guard_dispatch_icall
0x140006571  mov     [rsp+58h+var_10], 0
0x14000657a  lea     rax, [rsp+58h+arg_30]
0x140006582  mov     [rsp+58h+var_18], rsi
0x140006587  lea     r9, WPP_a773a5ed6750358f3f4fbf06697d601c_Traceguids
0x14000658e  mov     [rsp+58h+var_20], rax
0x140006593  mov     edx, 2
0x140006598  lea     rax, [rsp+58h+arg_28]
0x1400065a0  mov     [rsp+58h+var_28], rsi
0x1400065a5  mov     [rsp+58h+var_30], rax
0x1400065aa  mov     rcx, rdi
0x1400065ad  mov     [rsp+58h+var_38], bx
0x1400065b2  lea     r8d, [rdx+1]
0x1400065b6  call    cs:__imp_WppAutoLogTrace
0x1400065bd  nop     dword ptr [rax+rax+00h]
0x1400065c2  mov     rbx, [rsp+58h+arg_0]
0x1400065c7  mov     rsi, [rsp+58h+arg_8]
0x1400065cc  add     rsp, 50h
0x1400065d0  pop     rdi
0x1400065d1  retn
```
