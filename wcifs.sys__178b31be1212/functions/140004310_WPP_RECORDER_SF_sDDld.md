# WPP_RECORDER_SF_sDDld

- ea: `0x140004310`
- end: `0x140004442`
- name: `WPP_RECORDER_SF_sDDld`
- size: `306`
- prototype: `__int64(__int64, __int64, __int64, __int64, int, int, int, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025270`

## callees

- `0x140004310`
- `0x140007d40`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004428`
- `WppRecorder!WppAutoLogTrace` at `0x140004428`

## string_xrefs

- `0x140004331`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDDld(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, int a7, ...)
{
  int v9; // [rsp+20h] [rbp-98h]
  _DWORD v10[14]; // [rsp+80h] [rbp-38h] BYREF
  __int64 v11; // [rsp+F8h] [rbp+40h] BYREF
  va_list va; // [rsp+F8h] [rbp+40h]
  __int64 v13; // [rsp+100h] [rbp+48h] BYREF
  va_list va1; // [rsp+100h] [rbp+48h]
  va_list va2; // [rsp+108h] [rbp+50h] BYREF

  va_start(va2, a7);
  va_start(va1, a7);
  va_start(va, a7);
  v11 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v13 = va_arg(va2, _QWORD);
  v10[0] = 2900;
  if ( (HIDWORD(wil_details_featureDescriptors_a->Timer) & 0x10) != 0
    && BYTE1(wil_details_featureDescriptors_a->Timer) >= 2u )
  {
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, const char *, __int64, _DWORD *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      wil_details_featureDescriptors_a->AttachedDevice,
      43,
      WPP_852a4bc871f63f63d337338550f67970_Traceguids,
      64,
      "onecore\\base\\fs\\wci\\wcifs\\create.c",
      35,
      v10,
      4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  }
  LOWORD(v9) = 64;
  return WppAutoLogTrace(
           a1,
           2,
           5,
           WPP_852a4bc871f63f63d337338550f67970_Traceguids,
           v9,
           "onecore\\base\\fs\\wci\\wcifs\\create.c",
           35,
           v10,
           4,
           (__int64 *)va);
}

```

## disassembly

```asm
0x140004310  mov     r11, rsp
0x140004313  push    rbx
0x140004314  push    rbp
0x140004315  push    rdi
0x140004316  push    r14
0x140004318  sub     rsp, 98h
0x14000431f  mov     rbx, rcx
0x140004322  mov     dword ptr [r11-38h], 0B54h
0x14000432a  mov     rcx, cs:wil_details_featureDescriptors_a
0x140004331  lea     r14, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140004338  mov     ebp, 40h ; '@'
0x14000433d  mov     eax, [rcx+2Ch]
0x140004340  lea     edi, [rbp-3Ch]
0x140004343  test    al, 10h
0x140004345  jz      short loc_1400043B1
0x140004347  cmp     byte ptr [rcx+29h], 2
0x14000434b  jb      short loc_1400043B1
0x14000434d  mov     rax, cs:pfnWppTraceMessage
0x140004354  lea     rdx, [r11+50h]
0x140004358  mov     rcx, [rcx+18h]
0x14000435c  lea     r8, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140004363  mov     qword ptr [r11-48h], 0
0x14000436b  mov     r9d, ebp
0x14000436e  mov     [r11-50h], rdi
0x140004372  mov     [r11-58h], rdx
0x140004376  lea     rdx, [r11+48h]
0x14000437a  mov     [r11-60h], rdi
0x14000437e  mov     [r11-68h], rdx
0x140004382  lea     rdx, [r11+40h]
0x140004386  mov     [r11-70h], rdi
0x14000438a  mov     [r11-78h], rdx
0x14000438e  lea     rdx, [r11-38h]
0x140004392  mov     [r11-80h], rdi
0x140004396  mov     [rsp+0B8h+var_88], rdx
0x14000439b  lea     edx, [rbp-15h]
0x14000439e  mov     [rsp+0B8h+var_90], 23h ; '#'
0x1400043a7  mov     [rsp+0B8h+var_98], r14
0x1400043ac  call    _guard_dispatch_icall
0x1400043b1  mov     [rsp+0B8h+var_40], 0
0x1400043ba  lea     rax, [rsp+0B8h+arg_48]
0x1400043c2  mov     [rsp+0B8h+var_48], rdi
0x1400043c7  lea     r9, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x1400043ce  mov     [rsp+0B8h+var_50], rax
0x1400043d3  mov     edx, 2
0x1400043d8  mov     [rsp+0B8h+var_58], rdi
0x1400043dd  lea     rax, [rsp+0B8h+arg_40]
0x1400043e5  mov     [rsp+0B8h+var_60], rax
0x1400043ea  mov     rcx, rbx
0x1400043ed  mov     [rsp+0B8h+var_68], rdi
0x1400043f2  lea     rax, [rsp+0B8h+arg_38]
0x1400043fa  mov     [rsp+0B8h+var_70], rax
0x1400043ff  lea     r8d, [rdx+3]
0x140004403  mov     [rsp+0B8h+var_78], rdi
0x140004408  lea     rax, [rsp+0B8h+var_38]
0x140004410  mov     [rsp+0B8h+var_80], rax
0x140004415  mov     [rsp+0B8h+var_88], 23h ; '#'
0x14000441e  mov     [rsp+0B8h+var_90], r14
0x140004423  mov     word ptr [rsp+0B8h+var_98], bp
0x140004428  call    cs:__imp_WppAutoLogTrace
0x14000442f  nop     dword ptr [rax+rax+00h]
0x140004434  add     rsp, 98h
0x14000443b  pop     r14
0x14000443d  pop     rdi
0x14000443e  pop     rbp
0x14000443f  pop     rbx
0x140004440  retn
```
