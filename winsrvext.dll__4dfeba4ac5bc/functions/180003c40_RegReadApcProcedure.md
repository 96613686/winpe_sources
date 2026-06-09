# RegReadApcProcedure

- ea: `0x180003c40`
- end: `0x180003f21`
- name: `RegReadApcProcedure`
- size: `737`
- prototype: `void __stdcall(PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, ULONG Reserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800042f0`

## callees

- `0x1800025f8`
- `0x180002684`
- `0x180003c40`
- `0x1800138f0`

## import_xrefs

- `ntdll!NtNotifyChangeKey` at `0x180003ef1`
- `ntdll!NtNotifyChangeKey` at `0x180003ef1`
- `ntdll!NtSetSystemInformation` at `0x180003cff`
- `ntdll!NtSetSystemInformation` at `0x180003cff`
- `ntdll!NtQueryValueKey` at `0x180003cc2`
- `ntdll!NtQueryValueKey` at `0x180003d4e`
- `ntdll!NtQueryValueKey` at `0x180003e1f`
- `ntdll!NtQueryValueKey` at `0x180003cc2`
- `ntdll!NtQueryValueKey` at `0x180003d4e`
- `ntdll!NtQueryValueKey` at `0x180003e1f`
- `ntdll!RtlInitUnicodeString` at `0x180003c8d`
- `ntdll!RtlInitUnicodeString` at `0x180003d1f`
- `ntdll!RtlInitUnicodeString` at `0x180003df0`
- `ntdll!RtlInitUnicodeString` at `0x180003c8d`
- `ntdll!RtlInitUnicodeString` at `0x180003d1f`
- `ntdll!RtlInitUnicodeString` at `0x180003df0`
- `win32u!NtUserSetInformationThread` at `0x180003d99`
- `win32u!NtUserSetInformationThread` at `0x180003db6`
- `win32u!NtUserSetInformationThread` at `0x180003dd0`
- `win32u!NtUserSetInformationThread` at `0x180003e63`
- `win32u!NtUserSetInformationThread` at `0x180003e82`
- `win32u!NtUserSetInformationThread` at `0x180003e9f`
- `win32u!NtUserSetInformationThread` at `0x180003d99`
- `win32u!NtUserSetInformationThread` at `0x180003db6`
- `win32u!NtUserSetInformationThread` at `0x180003dd0`
- `win32u!NtUserSetInformationThread` at `0x180003e63`
- `win32u!NtUserSetInformationThread` at `0x180003e82`
- `win32u!NtUserSetInformationThread` at `0x180003e9f`

## pseudocode

```c
void __fastcall RegReadApcProcedure(PVOID ApcContext, PIO_STATUS_BLOCK IoStatusBlock, __int64 Reserved)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int SystemInformation; // [rsp+50h] [rbp-19h] BYREF
  ULONG ResultLength; // [rsp+54h] [rbp-15h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-11h] BYREF
  __int128 v10; // [rsp+68h] [rbp-1h] BYREF
  __int64 v11; // [rsp+78h] [rbp+Fh]
  _BYTE KeyValueInformation[12]; // [rsp+80h] [rbp+17h] BYREF
  int v13; // [rsp+8Ch] [rbp+23h]

  ResultLength = 0;
  SystemInformation = 0;
  DestinationString = 0;
  EtwLogNotificationStart(255, IoStatusBlock, Reserved);
  RtlInitUnicodeString(&DestinationString, L"Win32PrioritySeparation");
  if ( NtQueryValueKey(
         hKeyPriority,
         &DestinationString,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x14u,
         &ResultLength) < 0 )
  {
    SystemInformation = 2;
    v4 = 2;
  }
  else
  {
    v4 = v13;
    SystemInformation = v13;
  }
  if ( !IoStatusBlock || v4 != dword_18001D180 )
  {
    NtSetSystemInformation(SystemPrioritySeperation, &SystemInformation, 4u);
    dword_18001D180 = SystemInformation;
  }
  RtlInitUnicodeString(&DestinationString, L"ConvertibleSlateMode");
  if ( NtQueryValueKey(
         hKeyPriority,
         &DestinationString,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x14u,
         &ResultLength) < 0 )
  {
    SystemInformation = 0;
    v5 = 0;
  }
  else
  {
    v5 = v13;
    SystemInformation = v13;
  }
  if ( v5 != dword_18001D84C )
  {
    v11 = 0;
    v10 = 0;
    if ( (int)NtUserSetInformationThread(-2, 7, &v10) >= 0 )
    {
      NtUserSetInformationThread(-2, 15, &SystemInformation);
      NtUserSetInformationThread(-2, 9, &v10);
    }
    dword_18001D84C = SystemInformation;
  }
  RtlInitUnicodeString(&DestinationString, L"SystemDockMode");
  if ( NtQueryValueKey(
         hKeyPriority,
         &DestinationString,
         KeyValuePartialInformation,
         KeyValueInformation,
         0x14u,
         &ResultLength) < 0 )
  {
    SystemInformation = 0;
    v6 = 0;
  }
  else
  {
    v6 = v13;
    SystemInformation = v13;
  }
  if ( v6 != dword_18001D848 )
  {
    v11 = 0;
    v10 = 0;
    if ( (int)NtUserSetInformationThread(-2, 7, &v10) >= 0 )
    {
      NtUserSetInformationThread(-2, 16, &SystemInformation);
      NtUserSetInformationThread(-2, 9, &v10);
    }
    dword_18001D848 = SystemInformation;
  }
  NtNotifyChangeKey(hKeyPriority, 0, RegReadApcProcedure, 0, &IoStatusRegChange, 4u, 0, &RegChangeBuffer, 4u, 1u);
  EtwLogNotificationStop(255);
}

```

## disassembly

```asm
0x180003c40  push    rbp
0x180003c42  push    rbx
0x180003c43  push    rsi
0x180003c44  push    r14
0x180003c46  lea     rbp, [rsp-3Fh]
0x180003c4b  sub     rsp, 0A8h
0x180003c52  mov     rax, cs:__security_cookie
0x180003c59  xor     rax, rsp
0x180003c5c  mov     [rbp+57h+var_28], rax
0x180003c60  xorps   xmm0, xmm0
0x180003c63  mov     [rbp+57h+var_6C], 0
0x180003c6a  mov     ecx, 0FFh
0x180003c6f  mov     [rbp+57h+SystemInformation], 0
0x180003c76  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180003c7a  mov     rbx, rdx
0x180003c7d  call    EtwLogNotificationStart
0x180003c82  lea     rdx, SourceString; "Win32PrioritySeparation"
0x180003c89  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180003c8d  call    cs:__imp_RtlInitUnicodeString
0x180003c94  nop     dword ptr [rax+rax+00h]
0x180003c99  mov     rcx, cs:hKeyPriority; KeyHandle
0x180003ca0  lea     rax, [rbp+57h+var_6C]
0x180003ca4  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180003ca9  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180003cad  mov     r14d, 2
0x180003cb3  mov     [rsp+0C0h+Length], 14h; Length
0x180003cbb  mov     r8d, r14d; KeyValueInformationClass
0x180003cbe  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180003cc2  call    cs:__imp_NtQueryValueKey
0x180003cc9  nop     dword ptr [rax+rax+00h]
0x180003cce  test    eax, eax
0x180003cd0  js      short loc_180003CDA
0x180003cd2  mov     eax, [rbp+57h+var_34]
0x180003cd5  mov     [rbp+57h+SystemInformation], eax
0x180003cd8  jmp     short loc_180003CE1
0x180003cda  mov     [rbp+57h+SystemInformation], r14d
0x180003cde  mov     eax, r14d
0x180003ce1  mov     esi, 4
0x180003ce6  test    rbx, rbx
0x180003ce9  jz      short loc_180003CF3
0x180003ceb  cmp     eax, cs:dword_18001D180
0x180003cf1  jz      short loc_180003D14
0x180003cf3  mov     r8d, esi; SystemInformationLength
0x180003cf6  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x180003cfa  mov     ecx, 27h ; '''; SystemInformationClass
0x180003cff  call    cs:__imp_NtSetSystemInformation
0x180003d06  nop     dword ptr [rax+rax+00h]
0x180003d0b  mov     eax, [rbp+57h+SystemInformation]
0x180003d0e  mov     cs:dword_18001D180, eax
0x180003d14  lea     rdx, aConvertiblesla; "ConvertibleSlateMode"
0x180003d1b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180003d1f  call    cs:__imp_RtlInitUnicodeString
0x180003d26  nop     dword ptr [rax+rax+00h]
0x180003d2b  mov     rcx, cs:hKeyPriority; KeyHandle
0x180003d32  lea     rax, [rbp+57h+var_6C]
0x180003d36  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180003d3b  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180003d3f  mov     r8d, r14d; KeyValueInformationClass
0x180003d42  mov     [rsp+0C0h+Length], 14h; Length
0x180003d4a  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180003d4e  call    cs:__imp_NtQueryValueKey
0x180003d55  nop     dword ptr [rax+rax+00h]
0x180003d5a  test    eax, eax
0x180003d5c  js      short loc_180003D66
0x180003d5e  mov     eax, [rbp+57h+var_34]
0x180003d61  mov     [rbp+57h+SystemInformation], eax
0x180003d64  jmp     short loc_180003D6F
0x180003d66  mov     [rbp+57h+SystemInformation], 0
0x180003d6d  xor     eax, eax
0x180003d6f  cmp     eax, cs:dword_18001D84C
0x180003d75  mov     rbx, 0FFFFFFFFFFFFFFFEh
0x180003d7c  jz      short loc_180003DE5
0x180003d7e  xorps   xmm0, xmm0
0x180003d81  lea     r9d, [rbx+1Ah]
0x180003d85  xor     eax, eax
0x180003d87  lea     r8, [rbp+57h+var_58]
0x180003d8b  lea     edx, [rbx+9]
0x180003d8e  mov     [rbp+57h+var_48], rax
0x180003d92  mov     rcx, rbx
0x180003d95  movups  [rbp+57h+var_58], xmm0
0x180003d99  call    cs:__imp_NtUserSetInformationThread
0x180003da0  nop     dword ptr [rax+rax+00h]
0x180003da5  test    eax, eax
0x180003da7  js      short loc_180003DDC
0x180003da9  mov     r9d, esi
0x180003dac  lea     r8, [rbp+57h+SystemInformation]
0x180003db0  lea     edx, [rbx+11h]
0x180003db3  mov     rcx, rbx
0x180003db6  call    cs:__imp_NtUserSetInformationThread
0x180003dbd  nop     dword ptr [rax+rax+00h]
0x180003dc2  lea     r9d, [rbx+1Ah]
0x180003dc6  mov     rcx, rbx
0x180003dc9  lea     r8, [rbp+57h+var_58]
0x180003dcd  lea     edx, [rbx+0Bh]
0x180003dd0  call    cs:__imp_NtUserSetInformationThread
0x180003dd7  nop     dword ptr [rax+rax+00h]
0x180003ddc  mov     eax, [rbp+57h+SystemInformation]
0x180003ddf  mov     cs:dword_18001D84C, eax
0x180003de5  lea     rdx, aSystemdockmode; "SystemDockMode"
0x180003dec  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180003df0  call    cs:__imp_RtlInitUnicodeString
0x180003df7  nop     dword ptr [rax+rax+00h]
0x180003dfc  mov     rcx, cs:hKeyPriority; KeyHandle
0x180003e03  lea     rax, [rbp+57h+var_6C]
0x180003e07  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x180003e0c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x180003e10  mov     r8d, r14d; KeyValueInformationClass
0x180003e13  mov     [rsp+0C0h+Length], 14h; Length
0x180003e1b  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180003e1f  call    cs:__imp_NtQueryValueKey
0x180003e26  nop     dword ptr [rax+rax+00h]
0x180003e2b  test    eax, eax
0x180003e2d  js      short loc_180003E37
0x180003e2f  mov     eax, [rbp+57h+var_34]
0x180003e32  mov     [rbp+57h+SystemInformation], eax
0x180003e35  jmp     short loc_180003E40
0x180003e37  mov     [rbp+57h+SystemInformation], 0
0x180003e3e  xor     eax, eax
0x180003e40  cmp     eax, cs:dword_18001D848
0x180003e46  jz      short loc_180003EB4
0x180003e48  xor     eax, eax
0x180003e4a  lea     r8, [rbp+57h+var_58]
0x180003e4e  xorps   xmm0, xmm0
0x180003e51  mov     [rbp+57h+var_48], rax
0x180003e55  mov     rcx, rbx
0x180003e58  movups  [rbp+57h+var_58], xmm0
0x180003e5c  lea     r9d, [rax+18h]
0x180003e60  lea     edx, [rax+7]
0x180003e63  call    cs:__imp_NtUserSetInformationThread
0x180003e6a  nop     dword ptr [rax+rax+00h]
0x180003e6f  test    eax, eax
0x180003e71  js      short loc_180003EAB
0x180003e73  mov     r9d, esi
0x180003e76  lea     r8, [rbp+57h+SystemInformation]
0x180003e7a  mov     edx, 10h
0x180003e7f  mov     rcx, rbx
0x180003e82  call    cs:__imp_NtUserSetInformationThread
0x180003e89  nop     dword ptr [rax+rax+00h]
0x180003e8e  mov     r9d, 18h
0x180003e94  lea     r8, [rbp+57h+var_58]
0x180003e98  mov     rcx, rbx
0x180003e9b  lea     edx, [r9-0Fh]
0x180003e9f  call    cs:__imp_NtUserSetInformationThread
0x180003ea6  nop     dword ptr [rax+rax+00h]
0x180003eab  mov     eax, [rbp+57h+SystemInformation]
0x180003eae  mov     cs:dword_18001D848, eax
0x180003eb4  mov     rcx, cs:hKeyPriority; KeyHandle
0x180003ebb  lea     rax, RegChangeBuffer
0x180003ec2  mov     [rsp+0C0h+WatchSubtree], 1; WatchSubtree
0x180003ec7  lea     r8, RegReadApcProcedure; ApcRoutine
0x180003ece  mov     [rsp+0C0h+var_80], esi; Length
0x180003ed2  xor     r9d, r9d; ApcContext
0x180003ed5  mov     [rsp+0C0h+ChangeBuffer], rax; ChangeBuffer
0x180003eda  xor     edx, edx; Event
0x180003edc  mov     [rsp+0C0h+Asynchroneous], 0; Asynchroneous
0x180003ee1  lea     rax, IoStatusRegChange
0x180003ee8  mov     dword ptr [rsp+0C0h+ResultLength], esi; CompletionFilter
0x180003eec  mov     qword ptr [rsp+0C0h+Length], rax; IoStatusBlock
0x180003ef1  call    cs:__imp_NtNotifyChangeKey
0x180003ef8  nop     dword ptr [rax+rax+00h]
0x180003efd  mov     ecx, 0FFh
0x180003f02  call    EtwLogNotificationStop
0x180003f07  mov     rcx, [rbp+57h+var_28]
0x180003f0b  xor     rcx, rsp; StackCookie
0x180003f0e  call    __security_check_cookie
0x180003f13  add     rsp, 0A8h
0x180003f1a  pop     r14
0x180003f1c  pop     rsi
0x180003f1d  pop     rbx
0x180003f1e  pop     rbp
0x180003f1f  retn
```
