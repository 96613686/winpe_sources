# WPP_RECORDER_SF_qDD

- ea: `0x14000bc4c`
- end: `0x14000bd41`
- name: `WPP_RECORDER_SF_qDD`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c500`
- `0x14000da50`

## callees

- `0x14000bc4c`
- `0x140010700`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000bd24`
- `WppRecorder!WppAutoLogTrace` at `0x14000bd24`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qDD(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-48h]
  __int64 v9; // [rsp+98h] [rbp+30h] BYREF
  va_list va; // [rsp+98h] [rbp+30h]
  __int64 v11; // [rsp+A0h] [rbp+38h] BYREF
  va_list va1; // [rsp+A0h] [rbp+38h]
  va_list va2; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(_DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_0eec754a616436344c523d073d150c9e_Traceguids,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 4, 3, WPP_0eec754a616436344c523d073d150c9e_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x14000bc4c  mov     r11, rsp
0x14000bc4f  mov     [r11+8], rbx
0x14000bc53  mov     [r11+10h], rsi
0x14000bc57  push    rdi
0x14000bc58  sub     rsp, 60h
0x14000bc5c  mov     rdi, rcx
0x14000bc5f  movzx   ebx, r9w
0x14000bc63  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc6a  mov     esi, 4
0x14000bc6f  mov     eax, [rcx+2Ch]
0x14000bc72  test    sil, al
0x14000bc75  jz      short loc_14000BCCA
0x14000bc77  cmp     [rcx+29h], sil
0x14000bc7b  jb      short loc_14000BCCA
0x14000bc7d  mov     rax, cs:pfnWppTraceMessage
0x14000bc84  lea     rdx, [r11+40h]
0x14000bc88  mov     rcx, [rcx+18h]
0x14000bc8c  lea     r8, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000bc93  mov     qword ptr [r11-18h], 0
0x14000bc9b  mov     r9d, ebx
0x14000bc9e  mov     [r11-20h], rsi
0x14000bca2  mov     [r11-28h], rdx
0x14000bca6  lea     rdx, [r11+38h]
0x14000bcaa  mov     [r11-30h], rsi
0x14000bcae  mov     [r11-38h], rdx
0x14000bcb2  lea     rdx, [r11+30h]
0x14000bcb6  mov     qword ptr [r11-40h], 8
0x14000bcbe  mov     [r11-48h], rdx
0x14000bcc2  lea     edx, [rsi+27h]
0x14000bcc5  call    _guard_dispatch_icall
0x14000bcca  mov     [rsp+68h+var_10], 0
0x14000bcd3  lea     rax, [rsp+68h+arg_38]
0x14000bcdb  mov     [rsp+68h+var_18], rsi
0x14000bce0  lea     r9, WPP_0eec754a616436344c523d073d150c9e_Traceguids
0x14000bce7  mov     [rsp+68h+var_20], rax
0x14000bcec  mov     r8d, 3
0x14000bcf2  mov     [rsp+68h+var_28], rsi
0x14000bcf7  lea     rax, [rsp+68h+arg_30]
0x14000bcff  mov     [rsp+68h+var_30], rax
0x14000bd04  mov     edx, esi
0x14000bd06  lea     rax, [rsp+68h+arg_28]
0x14000bd0e  mov     [rsp+68h+var_38], 8
0x14000bd17  mov     [rsp+68h+var_40], rax
0x14000bd1c  mov     rcx, rdi
0x14000bd1f  mov     [rsp+68h+var_48], bx
0x14000bd24  call    cs:__imp_WppAutoLogTrace
0x14000bd2b  nop     dword ptr [rax+rax+00h]
0x14000bd30  mov     rbx, [rsp+68h+arg_0]
0x14000bd35  mov     rsi, [rsp+68h+arg_8]
0x14000bd3a  add     rsp, 60h
0x14000bd3e  pop     rdi
0x14000bd3f  retn
```
