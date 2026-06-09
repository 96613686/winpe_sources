# WPP_RECORDER_SF_sDqDld

- ea: `0x140005050`
- end: `0x1400051a7`
- name: `WPP_RECORDER_SF_sDqDld`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025220`

## callees

- `0x140005050`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000518d`
- `WppRecorder!WppAutoLogTrace` at `0x14000518d`

## string_xrefs

- `0x14000506d`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDqDld(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, int a6, ...)
{
  int v9; // [rsp+20h] [rbp-98h]
  __int64 v10; // [rsp+90h] [rbp-28h]
  __int64 v11; // [rsp+98h] [rbp-20h]
  __int64 v12; // [rsp+A0h] [rbp-18h]
  __int64 v13; // [rsp+F0h] [rbp+38h] BYREF
  va_list va; // [rsp+F0h] [rbp+38h]
  __int64 v15; // [rsp+F8h] [rbp+40h] BYREF
  va_list va1; // [rsp+F8h] [rbp+40h]
  __int64 v17; // [rsp+100h] [rbp+48h] BYREF
  va_list va2; // [rsp+100h] [rbp+48h]
  __int64 v19; // [rsp+108h] [rbp+50h] BYREF
  va_list va3; // [rsp+108h] [rbp+50h]
  va_list va4; // [rsp+110h] [rbp+58h] BYREF

  va_start(va4, a6);
  va_start(va3, a6);
  va_start(va2, a6);
  va_start(va1, a6);
  va_start(va, a6);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v17 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v19 = va_arg(va4, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, const char *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_852a4bc871f63f63d337338550f67970_Traceguids,
      a4,
      "onecore\\base\\fs\\wci\\wcifs\\create.c",
      35,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      8,
      (__int64 *)va2,
      4,
      (__int64 *)va3,
      4,
      va4,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(
           a1,
           2,
           5,
           WPP_852a4bc871f63f63d337338550f67970_Traceguids,
           v9,
           "onecore\\base\\fs\\wci\\wcifs\\create.c",
           35,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           8,
           (__int64 *)va2,
           4,
           (__int64 *)va3,
           4,
           va4,
           4,
           0,
           v10,
           v11,
           v12);
}

```

## disassembly

```asm
0x140005050  mov     r11, rsp
0x140005053  push    rbx
0x140005054  push    rsi
0x140005055  push    rdi
0x140005056  push    r15
0x140005058  sub     rsp, 98h
0x14000505f  mov     rdi, rcx
0x140005062  movzx   ebx, r9w
0x140005066  mov     rcx, cs:WPP_GLOBAL_Control
0x14000506d  lea     r15, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140005074  mov     esi, 4
0x140005079  mov     eax, [rcx+2Ch]
0x14000507c  test    al, 10h
0x14000507e  jz      short loc_1400050FA
0x140005080  cmp     byte ptr [rcx+29h], 2
0x140005084  jb      short loc_1400050FA
0x140005086  mov     rax, cs:pfnWppTraceMessage
0x14000508d  lea     rdx, [r11+58h]
0x140005091  mov     rcx, [rcx+18h]
0x140005095  lea     r8, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x14000509c  mov     qword ptr [r11-38h], 0
0x1400050a4  mov     r9d, ebx
0x1400050a7  mov     [r11-40h], rsi
0x1400050ab  mov     [r11-48h], rdx
0x1400050af  lea     rdx, [r11+50h]
0x1400050b3  mov     [r11-50h], rsi
0x1400050b7  mov     [r11-58h], rdx
0x1400050bb  lea     rdx, [r11+48h]
0x1400050bf  mov     [r11-60h], rsi
0x1400050c3  mov     [r11-68h], rdx
0x1400050c7  lea     rdx, [r11+40h]
0x1400050cb  mov     qword ptr [r11-70h], 8
0x1400050d3  mov     [r11-78h], rdx
0x1400050d7  lea     rdx, [r11+38h]
0x1400050db  mov     [r11-80h], rsi
0x1400050df  mov     [rsp+0B8h+var_88], rdx
0x1400050e4  lea     edx, [rsi+27h]
0x1400050e7  mov     [rsp+0B8h+var_90], 23h ; '#'
0x1400050f0  mov     [rsp+0B8h+var_98], r15
0x1400050f5  call    _guard_dispatch_icall
0x1400050fa  mov     [rsp+0B8h+var_30], 0
0x140005106  lea     rax, [rsp+0B8h+arg_50]
0x14000510e  mov     [rsp+0B8h+var_38], rsi
0x140005116  lea     r9, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x14000511d  mov     [rsp+0B8h+var_40], rax
0x140005122  mov     edx, 2
0x140005127  mov     [rsp+0B8h+var_48], rsi
0x14000512c  lea     rax, [rsp+0B8h+arg_48]
0x140005134  mov     [rsp+0B8h+var_50], rax
0x140005139  mov     rcx, rdi
0x14000513c  mov     [rsp+0B8h+var_58], rsi
0x140005141  lea     rax, [rsp+0B8h+arg_40]
0x140005149  mov     [rsp+0B8h+var_60], rax
0x14000514e  lea     r8d, [rdx+3]
0x140005152  mov     [rsp+0B8h+var_68], 8
0x14000515b  lea     rax, [rsp+0B8h+arg_38]
0x140005163  mov     [rsp+0B8h+var_70], rax
0x140005168  lea     rax, [rsp+0B8h+arg_30]
0x140005170  mov     [rsp+0B8h+var_78], rsi
0x140005175  mov     [rsp+0B8h+var_80], rax
0x14000517a  mov     [rsp+0B8h+var_88], 23h ; '#'
0x140005183  mov     [rsp+0B8h+var_90], r15
0x140005188  mov     word ptr [rsp+0B8h+var_98], bx
0x14000518d  call    cs:__imp_WppAutoLogTrace
0x140005194  nop     dword ptr [rax+rax+00h]
0x140005199  add     rsp, 98h
0x1400051a0  pop     r15
0x1400051a2  pop     rdi
0x1400051a3  pop     rsi
0x1400051a4  pop     rbx
0x1400051a5  retn
```
