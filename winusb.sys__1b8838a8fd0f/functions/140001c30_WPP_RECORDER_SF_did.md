# WPP_RECORDER_SF_did

- ea: `0x140001c30`
- end: `0x140001d1d`
- name: `WPP_RECORDER_SF_did`
- size: `237`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400034cc`
- `0x1400043cc`
- `0x140004908`
- `0x1400055fc`
- `0x140005838`
- `0x14000ca60`
- `0x14000e19c`
- `0x14000eff0`

## callees

- `0x140001c30`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001d07`
- `WppRecorder!WppAutoLogTrace` at `0x140001d07`

## pseudocode

```c
__int64 WPP_RECORDER_SF_did(__int64 a1, unsigned __int8 a2, __int64 a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-68h]
  __int64 v10; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v12; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v10 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v12 = va_arg(va2, _QWORD);
  v7 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(_DEVICE_OBJECT *, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, v7, 3, a5, v9, (__int64 *)va);
}

```

## disassembly

```asm
0x140001c30  mov     r11, rsp
0x140001c33  push    rbx
0x140001c34  push    rbp
0x140001c35  push    rsi
0x140001c36  push    rdi
0x140001c37  sub     rsp, 68h
0x140001c3b  mov     rsi, rcx
0x140001c3e  movzx   edi, r9w
0x140001c42  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c49  mov     ebp, 4
0x140001c4e  movzx   ebx, dl
0x140001c51  mov     eax, [rcx+2Ch]
0x140001c54  test    bpl, al
0x140001c57  jz      short loc_140001CAC
0x140001c59  cmp     [rcx+29h], bl
0x140001c5c  jb      short loc_140001CAC
0x140001c5e  mov     rax, cs:pfnWppTraceMessage
0x140001c65  lea     rdx, [r11+40h]
0x140001c69  mov     r8, [rsp+88h+arg_20]
0x140001c71  mov     r9d, edi
0x140001c74  mov     rcx, [rcx+18h]
0x140001c78  mov     qword ptr [r11-38h], 0
0x140001c80  mov     [r11-40h], rbp
0x140001c84  mov     [r11-48h], rdx
0x140001c88  lea     rdx, [r11+38h]
0x140001c8c  mov     qword ptr [r11-50h], 8
0x140001c94  mov     [r11-58h], rdx
0x140001c98  lea     rdx, [r11+30h]
0x140001c9c  mov     [r11-60h], rbp
0x140001ca0  mov     [r11-68h], rdx
0x140001ca4  lea     edx, [rbp+27h]
0x140001ca7  call    _guard_dispatch_icall
0x140001cac  mov     r9, [rsp+88h+arg_20]
0x140001cb4  lea     rax, [rsp+88h+arg_38]
0x140001cbc  mov     [rsp+88h+var_30], 0
0x140001cc5  mov     r8d, 3
0x140001ccb  mov     [rsp+88h+var_38], rbp
0x140001cd0  mov     edx, ebx
0x140001cd2  mov     [rsp+88h+var_40], rax
0x140001cd7  mov     rcx, rsi
0x140001cda  mov     [rsp+88h+var_48], 8
0x140001ce3  lea     rax, [rsp+88h+arg_30]
0x140001ceb  mov     [rsp+88h+var_50], rax
0x140001cf0  lea     rax, [rsp+88h+arg_28]
0x140001cf8  mov     [rsp+88h+var_58], rbp
0x140001cfd  mov     [rsp+88h+var_60], rax
0x140001d02  mov     [rsp+88h+var_68], di
0x140001d07  call    cs:__imp_WppAutoLogTrace
0x140001d0e  nop     dword ptr [rax+rax+00h]
0x140001d13  add     rsp, 68h
0x140001d17  pop     rdi
0x140001d18  pop     rsi
0x140001d19  pop     rbp
0x140001d1a  pop     rbx
0x140001d1b  retn
```
