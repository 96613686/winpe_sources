# WPP_RECORDER_SF_sDlLDd

- ea: `0x140006814`
- end: `0x140006963`
- name: `WPP_RECORDER_SF_sDlLDd`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140032d30`

## callees

- `0x140006814`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006948`
- `WppRecorder!WppAutoLogTrace` at `0x140006948`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDlLDd(__int64 a1, unsigned __int8 a2, _DWORD a3, unsigned __int16 a4, int a5, __int64 a6, ...)
{
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-98h]
  __int64 v11; // [rsp+90h] [rbp-28h]
  __int64 v12; // [rsp+98h] [rbp-20h]
  __int64 v13; // [rsp+A0h] [rbp-18h]
  __int64 v14; // [rsp+F0h] [rbp+38h] BYREF
  va_list va; // [rsp+F0h] [rbp+38h]
  __int64 v16; // [rsp+F8h] [rbp+40h] BYREF
  va_list va1; // [rsp+F8h] [rbp+40h]
  __int64 v18; // [rsp+100h] [rbp+48h] BYREF
  va_list va2; // [rsp+100h] [rbp+48h]
  __int64 v20; // [rsp+108h] [rbp+50h] BYREF
  va_list va3; // [rsp+108h] [rbp+50h]
  va_list va4; // [rsp+110h] [rbp+58h] BYREF

  va_start(va4, a6);
  va_start(va3, a6);
  va_start(va2, a6);
  va_start(va1, a6);
  va_start(va, a6);
  v14 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v16 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v18 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v20 = va_arg(va4, _QWORD);
  v8 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, const char *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
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
      (__int64 *)va3,
      4,
      va4,
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
           (__int64 *)va3,
           4,
           va4,
           4,
           0,
           v11,
           v12,
           v13);
}

```

## disassembly

```asm
0x140006814  mov     r11, rsp
0x140006817  push    rbx
0x140006818  push    rbp
0x140006819  push    rsi
0x14000681a  push    rdi
0x14000681b  push    r15
0x14000681d  sub     rsp, 90h
0x140006824  mov     rsi, rcx
0x140006827  movzx   edi, r9w
0x14000682b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006832  lea     r15, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\wcifs\\wcifs.c"
0x140006839  movzx   ebx, dl
0x14000683c  mov     ebp, 4
0x140006841  mov     eax, [rcx+2Ch]
0x140006844  test    al, 8
0x140006846  jz      short loc_1400068BD
0x140006848  cmp     [rcx+29h], bl
0x14000684b  jb      short loc_1400068BD
0x14000684d  mov     rax, cs:pfnWppTraceMessage
0x140006854  lea     rdx, [r11+58h]
0x140006858  mov     rcx, [rcx+18h]
0x14000685c  lea     r8, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x140006863  mov     qword ptr [r11-38h], 0
0x14000686b  mov     r9d, edi
0x14000686e  mov     [r11-40h], rbp
0x140006872  mov     [r11-48h], rdx
0x140006876  lea     rdx, [r11+50h]
0x14000687a  mov     [r11-50h], rbp
0x14000687e  mov     [r11-58h], rdx
0x140006882  lea     rdx, [r11+48h]
0x140006886  mov     [r11-60h], rbp
0x14000688a  mov     [r11-68h], rdx
0x14000688e  lea     rdx, [r11+40h]
0x140006892  mov     [r11-70h], rbp
0x140006896  mov     [r11-78h], rdx
0x14000689a  lea     rdx, [r11+38h]
0x14000689e  mov     [r11-80h], rbp
0x1400068a2  mov     [rsp+0B8h+var_88], rdx
0x1400068a7  lea     edx, [rbp+27h]
0x1400068aa  mov     [rsp+0B8h+var_90], 22h ; '"'
0x1400068b3  mov     [rsp+0B8h+var_98], r15
0x1400068b8  call    _guard_dispatch_icall
0x1400068bd  mov     [rsp+0B8h+var_30], 0
0x1400068c9  lea     rax, [rsp+0B8h+arg_50]
0x1400068d1  mov     [rsp+0B8h+var_38], rbp
0x1400068d9  lea     r9, WPP_8cd792e1b32a3ec2c787b7fc12e314ec_Traceguids
0x1400068e0  mov     [rsp+0B8h+var_40], rax
0x1400068e5  mov     r8d, ebp
0x1400068e8  mov     [rsp+0B8h+var_48], rbp
0x1400068ed  lea     rax, [rsp+0B8h+arg_48]
0x1400068f5  mov     [rsp+0B8h+var_50], rax
0x1400068fa  mov     edx, ebx
0x1400068fc  mov     [rsp+0B8h+var_58], rbp
0x140006901  lea     rax, [rsp+0B8h+arg_40]
0x140006909  mov     [rsp+0B8h+var_60], rax
0x14000690e  mov     rcx, rsi
0x140006911  mov     [rsp+0B8h+var_68], rbp
0x140006916  lea     rax, [rsp+0B8h+arg_38]
0x14000691e  mov     [rsp+0B8h+var_70], rax
0x140006923  lea     rax, [rsp+0B8h+arg_30]
0x14000692b  mov     [rsp+0B8h+var_78], rbp
0x140006930  mov     [rsp+0B8h+var_80], rax
0x140006935  mov     [rsp+0B8h+var_88], 22h ; '"'
0x14000693e  mov     [rsp+0B8h+var_90], r15
0x140006943  mov     word ptr [rsp+0B8h+var_98], di
0x140006948  call    cs:__imp_WppAutoLogTrace
0x14000694f  nop     dword ptr [rax+rax+00h]
0x140006954  add     rsp, 90h
0x14000695b  pop     r15
0x14000695d  pop     rdi
0x14000695e  pop     rsi
0x14000695f  pop     rbp
0x140006960  pop     rbx
0x140006961  retn
```
