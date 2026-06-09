# WPP_RECORDER_SF_sDq

- ea: `0x140002e78`
- end: `0x140002f70`
- name: `WPP_RECORDER_SF_sDq`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002a7c`

## callees

- `0x140002e78`
- `0x140003130`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002f52`
- `WppRecorder!WppAutoLogTrace` at `0x140002f52`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sDq(__int64 a1, _DWORD a2, _DWORD a3, _DWORD a4, int a5, __int64 a6, ...)
{
  int v8; // [rsp+20h] [rbp-48h]
  __int64 v9; // [rsp+A0h] [rbp+38h] BYREF
  va_list va; // [rsp+A0h] [rbp+38h]
  va_list va1; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v9 = va_arg(va1, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, const char *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids,
      34,
      " ",
      2,
      (__int64 *)va,
      4,
      va1,
      8,
      0);
  LOWORD(v8) = 34;
  return WppAutoLogTrace(a1, 0, 1, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids, v8, " ", 2, (__int64 *)va);
}

```

## disassembly

```asm
0x140002e78  mov     r11, rsp
0x140002e7b  mov     [r11+8], rbx
0x140002e7f  mov     [r11+10h], r14
0x140002e83  push    r15
0x140002e85  sub     rsp, 60h
0x140002e89  mov     rbx, rcx
0x140002e8c  lea     r15, asc_140005150; " "
0x140002e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e9a  mov     r14d, 22h ; '"'
0x140002ea0  mov     eax, [rcx+2Ch]
0x140002ea3  test    al, 1
0x140002ea5  jz      short loc_140002EF9
0x140002ea7  mov     rax, cs:pfnWppTraceMessage
0x140002eae  lea     rdx, [r11+40h]
0x140002eb2  mov     rcx, [rcx+18h]
0x140002eb6  lea     r8, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x140002ebd  mov     qword ptr [r11-18h], 0
0x140002ec5  mov     r9d, r14d
0x140002ec8  mov     qword ptr [r11-20h], 8
0x140002ed0  mov     [r11-28h], rdx
0x140002ed4  lea     rdx, [r11+38h]
0x140002ed8  mov     qword ptr [r11-30h], 4
0x140002ee0  mov     [r11-38h], rdx
0x140002ee4  lea     edx, [r14+9]
0x140002ee8  mov     qword ptr [r11-40h], 2
0x140002ef0  mov     [r11-48h], r15
0x140002ef4  call    _guard_dispatch_icall
0x140002ef9  mov     [rsp+68h+var_10], 0
0x140002f02  lea     rax, [rsp+68h+arg_38]
0x140002f0a  mov     [rsp+68h+var_18], 8
0x140002f13  lea     r9, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x140002f1a  mov     [rsp+68h+var_20], rax
0x140002f1f  xor     edx, edx
0x140002f21  mov     [rsp+68h+var_28], 4
0x140002f2a  lea     rax, [rsp+68h+arg_30]
0x140002f32  mov     [rsp+68h+var_30], rax
0x140002f37  mov     rcx, rbx
0x140002f3a  mov     [rsp+68h+var_38], 2
0x140002f43  mov     [rsp+68h+var_40], r15
0x140002f48  lea     r8d, [rdx+1]
0x140002f4c  mov     [rsp+68h+var_48], r14w
0x140002f52  call    cs:__imp_WppAutoLogTrace
0x140002f59  nop     dword ptr [rax+rax+00h]
0x140002f5e  mov     rbx, [rsp+68h+arg_0]
0x140002f63  mov     r14, [rsp+68h+arg_8]
0x140002f68  add     rsp, 60h
0x140002f6c  pop     r15
0x140002f6e  retn
```
