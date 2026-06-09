# WPP_RECORDER_SF_sl

- ea: `0x14000293c`
- end: `0x140002a0c`
- name: `WPP_RECORDER_SF_sl`
- size: `208`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400024e8`
- `0x1400026a0`

## callees

- `0x14000293c`
- `0x140003130`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400029ee`
- `WppRecorder!WppAutoLogTrace` at `0x1400029ee`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sl(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, int a5, __int64 a6, ...)
{
  int v9; // [rsp+20h] [rbp-38h]
  va_list va; // [rsp+90h] [rbp+38h] BYREF

  va_start(va, a6);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, const char *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids,
      a4,
      " ",
      2,
      va,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, 0, 1, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids, v9, " ", 2, va);
}

```

## disassembly

```asm
0x14000293c  mov     r11, rsp
0x14000293f  mov     [r11+8], rbx
0x140002943  mov     [r11+10h], rdi
0x140002947  push    r14
0x140002949  sub     rsp, 50h
0x14000294d  mov     rdi, rcx
0x140002950  movzx   ebx, r9w
0x140002954  mov     rcx, cs:WPP_GLOBAL_Control
0x14000295b  lea     r14, asc_140005150; " "
0x140002962  mov     eax, [rcx+2Ch]
0x140002965  test    al, 1
0x140002967  jz      short loc_1400029AC
0x140002969  mov     rax, cs:pfnWppTraceMessage
0x140002970  lea     rdx, [r11+38h]
0x140002974  mov     rcx, [rcx+18h]
0x140002978  lea     r8, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x14000297f  mov     qword ptr [r11-18h], 0
0x140002987  mov     r9d, ebx
0x14000298a  mov     qword ptr [r11-20h], 4
0x140002992  mov     [r11-28h], rdx
0x140002996  mov     edx, 2Bh ; '+'
0x14000299b  mov     qword ptr [r11-30h], 2
0x1400029a3  mov     [r11-38h], r14
0x1400029a7  call    _guard_dispatch_icall
0x1400029ac  mov     [rsp+58h+var_10], 0
0x1400029b5  lea     rax, [rsp+58h+arg_30]
0x1400029bd  mov     [rsp+58h+var_18], 4
0x1400029c6  lea     r9, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x1400029cd  mov     [rsp+58h+var_20], rax
0x1400029d2  xor     edx, edx
0x1400029d4  mov     [rsp+58h+var_28], 2
0x1400029dd  mov     rcx, rdi
0x1400029e0  mov     [rsp+58h+var_30], r14
0x1400029e5  mov     [rsp+58h+var_38], bx
0x1400029ea  lea     r8d, [rdx+1]
0x1400029ee  call    cs:__imp_WppAutoLogTrace
0x1400029f5  nop     dword ptr [rax+rax+00h]
0x1400029fa  mov     rbx, [rsp+58h+arg_0]
0x1400029ff  mov     rdi, [rsp+58h+arg_8]
0x140002a04  add     rsp, 50h
0x140002a08  pop     r14
0x140002a0a  retn
```
