# WPP_RECORDER_SF_sdd

- ea: `0x140002858`
- end: `0x140002935`
- name: `WPP_RECORDER_SF_sdd`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400024e8`
- `0x1400026a0`

## callees

- `0x140002858`
- `0x140003130`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000291e`
- `WppRecorder!WppAutoLogTrace` at `0x14000291e`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sdd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, int a6, ...)
{
  int v9; // [rsp+20h] [rbp-68h]
  __int64 v10; // [rsp+C0h] [rbp+38h] BYREF
  va_list va; // [rsp+C0h] [rbp+38h]
  va_list va1; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v10 = va_arg(va1, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, const char *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids,
      a4,
      " ",
      2,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, 0, 1, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids, v9, " ", 2, (__int64 *)va);
}

```

## disassembly

```asm
0x140002858  mov     r11, rsp
0x14000285b  push    rbx
0x14000285c  push    rsi
0x14000285d  push    rdi
0x14000285e  push    r14
0x140002860  sub     rsp, 68h
0x140002864  mov     rdi, rcx
0x140002867  movzx   ebx, r9w
0x14000286b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002872  lea     r14, asc_140005150; " "
0x140002879  mov     esi, 4
0x14000287e  mov     eax, [rcx+2Ch]
0x140002881  test    al, 1
0x140002883  jz      short loc_1400028CE
0x140002885  mov     rax, cs:pfnWppTraceMessage
0x14000288c  lea     rdx, [r11+40h]
0x140002890  mov     rcx, [rcx+18h]
0x140002894  lea     r8, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x14000289b  mov     qword ptr [r11-38h], 0
0x1400028a3  mov     r9d, ebx
0x1400028a6  mov     [r11-40h], rsi
0x1400028aa  mov     [r11-48h], rdx
0x1400028ae  lea     rdx, [r11+38h]
0x1400028b2  mov     [r11-50h], rsi
0x1400028b6  mov     [r11-58h], rdx
0x1400028ba  lea     edx, [rsi+27h]
0x1400028bd  mov     qword ptr [r11-60h], 2
0x1400028c5  mov     [r11-68h], r14
0x1400028c9  call    _guard_dispatch_icall
0x1400028ce  mov     [rsp+88h+var_30], 0
0x1400028d7  lea     rax, [rsp+88h+arg_38]
0x1400028df  mov     [rsp+88h+var_38], rsi
0x1400028e4  lea     r9, WPP_d8869bceb4743096b6344322fa7eafaf_Traceguids
0x1400028eb  mov     [rsp+88h+var_40], rax
0x1400028f0  xor     edx, edx
0x1400028f2  mov     [rsp+88h+var_48], rsi
0x1400028f7  lea     rax, [rsp+88h+arg_30]
0x1400028ff  mov     [rsp+88h+var_50], rax
0x140002904  mov     rcx, rdi
0x140002907  mov     [rsp+88h+var_58], 2
0x140002910  mov     [rsp+88h+var_60], r14
0x140002915  lea     r8d, [rdx+1]
0x140002919  mov     [rsp+88h+var_68], bx
0x14000291e  call    cs:__imp_WppAutoLogTrace
0x140002925  nop     dword ptr [rax+rax+00h]
0x14000292a  add     rsp, 68h
0x14000292e  pop     r14
0x140002930  pop     rdi
0x140002931  pop     rsi
0x140002932  pop     rbx
0x140002933  retn
```
