# AllocateDeviceIFRLog

- ea: `0x14002a82c`
- end: `0x14002a9aa`
- name: `AllocateDeviceIFRLog`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002a2e0`

## callees

- `0x14000b4bc`
- `0x140014d10`
- `0x14002a82c`

## import_xrefs

- `ntoskrnl!IoGetDeviceProperty` at `0x14002a8cf`
- `ntoskrnl!IoGetDeviceProperty` at `0x14002a8cf`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14002a8fe`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14002a8fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a8e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a8e7`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14002a92d`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14002a92d`

## pseudocode

```c
__int64 __fastcall AllocateDeviceIFRLog(_QWORD *a1)
{
  struct _DEVICE_OBJECT *v2; // rcx
  __int64 result; // rax
  int v4; // edx
  __int64 v5; // rcx
  ULONG ResultLength; // [rsp+40h] [rbp-29h] BYREF
  struct _STRING v7; // [rsp+48h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-11h] BYREF
  __int64 v9; // [rsp+68h] [rbp-1h] BYREF
  __int64 v10; // [rsp+70h] [rbp+7h]
  __int128 v11; // [rsp+78h] [rbp+Fh]
  __int128 v12; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v13; // [rsp+98h] [rbp+2Fh]
  WCHAR PropertyBuffer[8]; // [rsp+A0h] [rbp+37h] BYREF

  v13 = 0;
  v11 = 0;
  ResultLength = 0;
  v2 = (struct _DEVICE_OBJECT *)a1[3];
  *(_QWORD *)&v11 = 0;
  BYTE8(v11) = 0;
  *(_QWORD *)&v7.Length = 0x100000;
  v9 = 56;
  v12 = 0;
  LOBYTE(v12) = 0;
  v7.Buffer = (char *)&v12;
  DestinationString = 0;
  v10 = 0xC800000400LL;
  HIDWORD(v11) = 16;
  v13 = 0x200000002LL;
  if ( IoGetDeviceProperty(v2, DevicePropertyClassName, 0x10u, PropertyBuffer, &ResultLength) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, PropertyBuffer);
    RtlUnicodeStringToAnsiString(&v7, &DestinationString, 0);
  }
  v10 = 0x33300001000LL;
  result = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v9, a1 + 171);
  if ( (int)result < 0 )
  {
    v5 = g_RecorderLog;
    a1[171] = g_RecorderLog;
    if ( v5 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v4) = 2;
        return WPP_RECORDER_SF_qD(
                 v5,
                 v4,
                 8,
                 21,
                 (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids,
                 a1[4],
                 result);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002a82c  mov     [rsp-8+arg_8], rbx
0x14002a831  mov     [rsp-8+arg_10], rdi
0x14002a836  push    rbp
0x14002a837  lea     rbp, [rsp-57h]
0x14002a83c  sub     rsp, 0C0h
0x14002a843  mov     rax, cs:__security_cookie
0x14002a84a  xor     rax, rsp
0x14002a84d  mov     [rbp+57h+var_10], rax
0x14002a851  xor     eax, eax
0x14002a853  lea     r9, [rbp+57h+PropertyBuffer]; PropertyBuffer
0x14002a857  xorps   xmm0, xmm0
0x14002a85a  mov     [rbp+57h+var_28], rax
0x14002a85e  movups  [rbp+57h+var_48], xmm0
0x14002a862  mov     [rbp+57h+var_80], eax
0x14002a865  mov     rdi, rcx
0x14002a868  mov     rcx, [rcx+18h]; DeviceObject
0x14002a86c  lea     r8d, [rax+10h]; BufferLength
0x14002a870  movups  [rbp+57h+var_58], xmm0
0x14002a874  mov     qword ptr [rbp+57h+var_48], rax
0x14002a878  lea     edx, [r8-0Bh]; DeviceProperty
0x14002a87c  mov     byte ptr [rbp+57h+var_48+8], al
0x14002a87f  xorps   xmm1, xmm1
0x14002a882  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x14002a886  mov     qword ptr [rbp+57h+var_58], 38h ; '8'
0x14002a88e  movups  [rbp+57h+var_38], xmm0
0x14002a892  mov     byte ptr [rbp+57h+var_38], al
0x14002a895  lea     rax, [rbp+57h+var_38]
0x14002a899  mov     [rbp+57h+var_78.Buffer], rax
0x14002a89d  lea     rax, [rbp+57h+var_80]
0x14002a8a1  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x14002a8a6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14002a8aa  mov     dword ptr [rbp+57h+var_58+8], 400h
0x14002a8b1  mov     dword ptr [rbp+57h+var_58+0Ch], 0C8h
0x14002a8b8  mov     dword ptr [rbp+57h+var_48+0Ch], r8d
0x14002a8bc  mov     dword ptr [rbp+57h+var_28], 2
0x14002a8c3  mov     dword ptr [rbp+57h+var_28+4], 2
0x14002a8ca  mov     [rbp+57h+var_78.MaximumLength], r8w
0x14002a8cf  call    cs:__imp_IoGetDeviceProperty
0x14002a8d6  nop     dword ptr [rax+rax+00h]
0x14002a8db  test    eax, eax
0x14002a8dd  js      short loc_14002A90A
0x14002a8df  lea     rdx, [rbp+57h+PropertyBuffer]; SourceString
0x14002a8e3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002a8e7  call    cs:__imp_RtlInitUnicodeString
0x14002a8ee  nop     dword ptr [rax+rax+00h]
0x14002a8f3  xor     r8d, r8d; AllocateDestinationString
0x14002a8f6  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14002a8fa  lea     rcx, [rbp+57h+var_78]; DestinationString
0x14002a8fe  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14002a905  nop     dword ptr [rax+rax+00h]
0x14002a90a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a911  lea     rbx, [rdi+558h]
0x14002a918  mov     r8, rbx
0x14002a91b  mov     dword ptr [rbp+57h+var_58+8], 1000h
0x14002a922  lea     rdx, [rbp+57h+var_58]
0x14002a926  mov     dword ptr [rbp+57h+var_58+0Ch], 333h
0x14002a92d  call    cs:__imp_imp_WppRecorderLogCreate
0x14002a934  nop     dword ptr [rax+rax+00h]
0x14002a939  test    eax, eax
0x14002a93b  js      short loc_14002A95F
0x14002a93d  mov     rcx, [rbp+57h+var_10]
0x14002a941  xor     rcx, rsp; StackCookie
0x14002a944  call    __security_check_cookie
0x14002a949  lea     r11, [rsp+0C0h+var_s0]
0x14002a951  mov     rbx, [r11+18h]
0x14002a955  mov     rdi, [r11+20h]
0x14002a959  mov     rsp, r11
0x14002a95c  pop     rbp
0x14002a95d  retn
0x14002a95f  mov     rcx, cs:g_RecorderLog
0x14002a966  mov     [rbx], rcx
0x14002a969  test    rcx, rcx
0x14002a96c  jz      short loc_14002A93D
0x14002a96e  lea     r8, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002a975  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x14002a97c  jz      short loc_14002A93D
0x14002a97e  mov     [rsp+0C0h+var_90], eax
0x14002a982  mov     r9d, 15h
0x14002a988  mov     rax, [rdi+20h]
0x14002a98c  mov     dl, 2
0x14002a98e  mov     [rsp+0C0h+var_98], rax
0x14002a993  lea     rax, WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids
0x14002a99a  mov     [rsp+0C0h+ResultLength], rax
0x14002a99f  lea     r8d, [r9-0Dh]
0x14002a9a3  call    WPP_RECORDER_SF_qD
0x14002a9a8  jmp     short loc_14002A93D
```
