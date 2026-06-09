# WPP_RECORDER_SF_sDlLD

- ea: `0x140002ab4`
- end: `0x140002bdd`
- name: `WPP_RECORDER_SF_sDlLD`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140032d30`

## callees

- `0x140002ab4`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002bc2`
- `WppRecorder!WppAutoLogTrace` at `0x140002bc2`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDlLD(__int64 a1, unsigned __int8 a2, __int64 a3, unsigned __int16 a4, int a5, int a6, ...)
{
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-88h]
  __int64 v11; // [rsp+80h] [rbp-28h]
  __int64 v12; // [rsp+88h] [rbp-20h]
  __int64 v13; // [rsp+90h] [rbp-18h]
  __int64 v14; // [rsp+98h] [rbp-10h]
  __int64 v15; // [rsp+A0h] [rbp-8h]
  __int64 v16; // [rsp+E0h] [rbp+38h] BYREF
  va_list va; // [rsp+E0h] [rbp+38h]
  __int64 v18; // [rsp+E8h] [rbp+40h] BYREF
  va_list va1; // [rsp+E8h] [rbp+40h]
  __int64 v20; // [rsp+F0h] [rbp+48h] BYREF
  va_list va2; // [rsp+F0h] [rbp+48h]
  va_list va3; // [rsp+F8h] [rbp+50h] BYREF

  va_start(va3, a6);
  va_start(va2, a6);
  va_start(va1, a6);
  va_start(va, a6);
  v16 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v18 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v20 = va_arg(va3, _QWORD);
  v8 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, const char *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
      a4,
      "onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
      34,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      (__int64 *)va2,
      4,
      va3,
      4,
      0);
  LOWORD(v10) = a4;
  return WppAutoLogTrace(
           a1,
           v8,
           4,
           WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids,
           v10,
           "onecore\\base\\fs\\wci\\wcifs\\wcifs.c",
           34,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           4,
           va3,
           4,
           0,
           v11,
           v12,
           v13,
           v14,
           v15);
}

```

## disassembly

```asm
0x140002ab4  mov     r11, rsp
0x140002ab7  push    rbx
0x140002ab8  push    rbp
0x140002ab9  push    rsi
0x140002aba  push    rdi
0x140002abb  push    r15
0x140002abd  sub     rsp, 80h
0x140002ac4  mov     rsi, rcx
0x140002ac7  movzx   edi, r9w
0x140002acb  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ad2  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140002ad9  movzx   ebx, dl
0x140002adc  mov     ebp, 4
0x140002ae1  mov     eax, [rcx+2Ch]
0x140002ae4  test    al, 8
0x140002ae6  jz      short loc_140002B4F
0x140002ae8  cmp     [rcx+29h], bl
0x140002aeb  jb      short loc_140002B4F
0x140002aed  mov     rax, cs:pfnWppTraceMessage
0x140002af4  lea     rdx, [r11+50h]
0x140002af8  mov     rcx, [rcx+18h]
0x140002afc  lea     r8, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140002b03  mov     qword ptr [r11-38h], 0
0x140002b0b  mov     r9d, edi
0x140002b0e  mov     [r11-40h], rbp
0x140002b12  mov     [r11-48h], rdx
0x140002b16  lea     rdx, [r11+48h]
0x140002b1a  mov     [r11-50h], rbp
0x140002b1e  mov     [r11-58h], rdx
0x140002b22  lea     rdx, [r11+40h]
0x140002b26  mov     [r11-60h], rbp
0x140002b2a  mov     [r11-68h], rdx
0x140002b2e  lea     rdx, [r11+38h]
0x140002b32  mov     [r11-70h], rbp
0x140002b36  mov     [r11-78h], rdx
0x140002b3a  lea     edx, [rbp+27h]
0x140002b3d  mov     qword ptr [r11-80h], 22h ; '"'
0x140002b45  mov     [rsp+0A8h+var_88], r15
0x140002b4a  call    _guard_dispatch_icall
0x140002b4f  mov     [rsp+0A8h+var_30], 0
0x140002b58  lea     rax, [rsp+0A8h+arg_48]
0x140002b60  mov     [rsp+0A8h+var_38], rbp
0x140002b65  lea     r9, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140002b6c  mov     [rsp+0A8h+var_40], rax
0x140002b71  mov     r8d, ebp
0x140002b74  mov     [rsp+0A8h+var_48], rbp
0x140002b79  lea     rax, [rsp+0A8h+arg_40]
0x140002b81  mov     [rsp+0A8h+var_50], rax
0x140002b86  mov     edx, ebx
0x140002b88  mov     [rsp+0A8h+var_58], rbp
0x140002b8d  lea     rax, [rsp+0A8h+arg_38]
0x140002b95  mov     [rsp+0A8h+var_60], rax
0x140002b9a  mov     rcx, rsi
0x140002b9d  mov     [rsp+0A8h+var_68], rbp
0x140002ba2  lea     rax, [rsp+0A8h+arg_30]
0x140002baa  mov     [rsp+0A8h+var_70], rax
0x140002baf  mov     [rsp+0A8h+var_78], 22h ; '"'
0x140002bb8  mov     [rsp+0A8h+var_80], r15
0x140002bbd  mov     word ptr [rsp+0A8h+var_88], di
0x140002bc2  call    cs:__imp_WppAutoLogTrace
0x140002bc9  nop     dword ptr [rax+rax+00h]
0x140002bce  add     rsp, 80h
0x140002bd5  pop     r15
0x140002bd7  pop     rdi
0x140002bd8  pop     rsi
0x140002bd9  pop     rbp
0x140002bda  pop     rbx
0x140002bdb  retn
```
