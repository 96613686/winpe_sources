# WPP_RECORDER_SF_sq

- ea: `0x1400019a8`
- end: `0x140001a7a`
- name: `WPP_RECORDER_SF_sq`
- size: `210`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140001020`
- `0x140001c34`
- `0x1400024e8`
- `0x1400026a0`
- `0x140002a7c`
- `0x140002c9c`
- `0x14000a0f0`

## callees

- `0x1400019a8`
- `0x140003130`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001a5c`
- `WppRecorder!WppAutoLogTrace` at `0x140001a5c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sq(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, __int64 a6, ...)
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
      8,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, 0, 1, a5, v9, " ", 2, va);
}

```

## disassembly

```asm
0x1400019a8  mov     r11, rsp
0x1400019ab  mov     [r11+8], rbx
0x1400019af  mov     [r11+10h], rdi
0x1400019b3  push    r14
0x1400019b5  sub     rsp, 50h
0x1400019b9  mov     rdi, rcx
0x1400019bc  movzx   ebx, r9w
0x1400019c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019c7  lea     r14, asc_140005150; " "
0x1400019ce  mov     eax, [rcx+2Ch]
0x1400019d1  test    al, 1
0x1400019d3  jz      short loc_140001A19
0x1400019d5  mov     rax, cs:pfnWppTraceMessage
0x1400019dc  lea     rdx, [r11+38h]
0x1400019e0  mov     r8, [rsp+58h+arg_20]
0x1400019e8  mov     r9d, ebx
0x1400019eb  mov     rcx, [rcx+18h]
0x1400019ef  mov     qword ptr [r11-18h], 0
0x1400019f7  mov     qword ptr [r11-20h], 8
0x1400019ff  mov     [r11-28h], rdx
0x140001a03  mov     edx, 2Bh ; '+'
0x140001a08  mov     qword ptr [r11-30h], 2
0x140001a10  mov     [r11-38h], r14
0x140001a14  call    _guard_dispatch_icall
0x140001a19  mov     r9, [rsp+58h+arg_20]
0x140001a21  lea     rax, [rsp+58h+arg_30]
0x140001a29  mov     [rsp+58h+var_10], 0
0x140001a32  xor     edx, edx
0x140001a34  mov     [rsp+58h+var_18], 8
0x140001a3d  mov     rcx, rdi
0x140001a40  mov     [rsp+58h+var_20], rax
0x140001a45  mov     [rsp+58h+var_28], 2
0x140001a4e  lea     r8d, [rdx+1]
0x140001a52  mov     [rsp+58h+var_30], r14
0x140001a57  mov     [rsp+58h+var_38], bx
0x140001a5c  call    cs:__imp_WppAutoLogTrace
0x140001a63  nop     dword ptr [rax+rax+00h]
0x140001a68  mov     rbx, [rsp+58h+arg_0]
0x140001a6d  mov     rdi, [rsp+58h+arg_8]
0x140001a72  add     rsp, 50h
0x140001a76  pop     r14
0x140001a78  retn
```
