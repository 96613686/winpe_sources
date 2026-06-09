# WPP_RECORDER_SF_sDd

- ea: `0x1400018c0`
- end: `0x14000199f`
- name: `WPP_RECORDER_SF_sDd`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400092f0`
- `0x14000a300`

## callees

- `0x1400018c0`
- `0x140003130`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001988`
- `WppRecorder!WppAutoLogTrace` at `0x140001988`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDd(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, __int64 a6, ...)
{
  int v9; // [rsp+20h] [rbp-68h]
  __int64 v10; // [rsp+C0h] [rbp+38h] BYREF
  va_list va; // [rsp+C0h] [rbp+38h]
  va_list va1; // [rsp+C8h] [rbp+40h] BYREF

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
      4,
      va1,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, 0, 1, a5, v9, " ", 2, (__int64 *)va);
}

```

## disassembly

```asm
0x1400018c0  mov     r11, rsp
0x1400018c3  push    rbx
0x1400018c4  push    rsi
0x1400018c5  push    rdi
0x1400018c6  push    r14
0x1400018c8  sub     rsp, 68h
0x1400018cc  mov     rdi, rcx
0x1400018cf  movzx   ebx, r9w
0x1400018d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018da  lea     r14, asc_140005150; " "
0x1400018e1  mov     esi, 4
0x1400018e6  mov     eax, [rcx+2Ch]
0x1400018e9  test    al, 1
0x1400018eb  jz      short loc_140001937
0x1400018ed  mov     rax, cs:pfnWppTraceMessage
0x1400018f4  lea     rdx, [r11+40h]
0x1400018f8  mov     r8, [rsp+88h+arg_20]
0x140001900  mov     r9d, ebx
0x140001903  mov     rcx, [rcx+18h]
0x140001907  mov     qword ptr [r11-38h], 0
0x14000190f  mov     [r11-40h], rsi
0x140001913  mov     [r11-48h], rdx
0x140001917  lea     rdx, [r11+38h]
0x14000191b  mov     [r11-50h], rsi
0x14000191f  mov     [r11-58h], rdx
0x140001923  lea     edx, [rsi+27h]
0x140001926  mov     qword ptr [r11-60h], 2
0x14000192e  mov     [r11-68h], r14
0x140001932  call    _guard_dispatch_icall
0x140001937  mov     r9, [rsp+88h+arg_20]
0x14000193f  lea     rax, [rsp+88h+arg_38]
0x140001947  mov     [rsp+88h+var_30], 0
0x140001950  xor     edx, edx
0x140001952  mov     [rsp+88h+var_38], rsi
0x140001957  mov     rcx, rdi
0x14000195a  mov     [rsp+88h+var_40], rax
0x14000195f  lea     rax, [rsp+88h+arg_30]
0x140001967  mov     [rsp+88h+var_48], rsi
0x14000196c  mov     [rsp+88h+var_50], rax
0x140001971  lea     r8d, [rdx+1]
0x140001975  mov     [rsp+88h+var_58], 2
0x14000197e  mov     [rsp+88h+var_60], r14
0x140001983  mov     [rsp+88h+var_68], bx
0x140001988  call    cs:__imp_WppAutoLogTrace
0x14000198f  nop     dword ptr [rax+rax+00h]
0x140001994  add     rsp, 68h
0x140001998  pop     r14
0x14000199a  pop     rdi
0x14000199b  pop     rsi
0x14000199c  pop     rbx
0x14000199d  retn
```
