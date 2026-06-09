# WPP_RECORDER_SF_sD

- ea: `0x1400017e8`
- end: `0x1400018ba`
- name: `WPP_RECORDER_SF_sD`
- size: `210`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010c0`
- `0x1400015dc`
- `0x140001ce0`
- `0x140009010`
- `0x1400092f0`
- `0x140009b60`
- `0x14000acac`
- `0x14000af20`
- `0x14000c078`
- `0x14000c1b8`

## callees

- `0x1400017e8`
- `0x140003130`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000189c`
- `WppRecorder!WppAutoLogTrace` at `0x14000189c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sD(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, __int64 a6, ...)
{
  int v9; // [rsp+20h] [rbp-38h]
  va_list va; // [rsp+90h] [rbp+38h] BYREF

  va_start(va, a6);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64, _QWORD, const char *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      " ",
      2,
      va,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, 0, 1, a5, v9, " ", 2, va);
}

```

## disassembly

```asm
0x1400017e8  mov     r11, rsp
0x1400017eb  mov     [r11+8], rbx
0x1400017ef  mov     [r11+10h], rdi
0x1400017f3  push    r14
0x1400017f5  sub     rsp, 50h
0x1400017f9  mov     rdi, rcx
0x1400017fc  movzx   ebx, r9w
0x140001800  mov     rcx, cs:WPP_GLOBAL_Control
0x140001807  lea     r14, asc_140005150; " "
0x14000180e  mov     eax, [rcx+2Ch]
0x140001811  test    al, 1
0x140001813  jz      short loc_140001859
0x140001815  mov     rax, cs:pfnWppTraceMessage
0x14000181c  lea     rdx, [r11+38h]
0x140001820  mov     r8, [rsp+58h+arg_20]
0x140001828  mov     r9d, ebx
0x14000182b  mov     rcx, [rcx+18h]
0x14000182f  mov     qword ptr [r11-18h], 0
0x140001837  mov     qword ptr [r11-20h], 4
0x14000183f  mov     [r11-28h], rdx
0x140001843  mov     edx, 2Bh ; '+'
0x140001848  mov     qword ptr [r11-30h], 2
0x140001850  mov     [r11-38h], r14
0x140001854  call    _guard_dispatch_icall
0x140001859  mov     r9, [rsp+58h+arg_20]
0x140001861  lea     rax, [rsp+58h+arg_30]
0x140001869  mov     [rsp+58h+var_10], 0
0x140001872  xor     edx, edx
0x140001874  mov     [rsp+58h+var_18], 4
0x14000187d  mov     rcx, rdi
0x140001880  mov     [rsp+58h+var_20], rax
0x140001885  mov     [rsp+58h+var_28], 2
0x14000188e  lea     r8d, [rdx+1]
0x140001892  mov     [rsp+58h+var_30], r14
0x140001897  mov     [rsp+58h+var_38], bx
0x14000189c  call    cs:__imp_WppAutoLogTrace
0x1400018a3  nop     dword ptr [rax+rax+00h]
0x1400018a8  mov     rbx, [rsp+58h+arg_0]
0x1400018ad  mov     rdi, [rsp+58h+arg_8]
0x1400018b2  add     rsp, 50h
0x1400018b6  pop     r14
0x1400018b8  retn
```
