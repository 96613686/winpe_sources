# DisplayExitWindowsWarnings

- ea: `0x1800670e0`
- end: `0x180067365`
- name: `DisplayExitWindowsWarnings`
- size: `645`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180077970`

## callees

- `0x180026f90`
- `0x1800670e0`
- `0x180068f04`
- `0x180096e00`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x180067139`
- `ntdll!RtlGetActiveConsoleId` at `0x180067139`
- `ntdll!NtQueryValueKey` at `0x1800672c2`
- `ntdll!NtQueryValueKey` at `0x1800672c2`
- `ntdll!NtClose` at `0x1800672d3`
- `ntdll!NtClose` at `0x1800672d3`
- `ntdll!NtOpenKey` at `0x180067280`
- `ntdll!NtOpenKey` at `0x180067280`
- `ntdll!RtlInitUnicodeString` at `0x180067243`
- `ntdll!RtlInitUnicodeString` at `0x180067296`
- `ntdll!RtlInitUnicodeString` at `0x180067243`
- `ntdll!RtlInitUnicodeString` at `0x180067296`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18006711d`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18006711d`
- `KERNELBASE!LoadStringBaseExW` at `0x1800672f5`
- `KERNELBASE!LoadStringBaseExW` at `0x180067317`
- `KERNELBASE!LoadStringBaseExW` at `0x1800672f5`
- `KERNELBASE!LoadStringBaseExW` at `0x180067317`
- `WINSTA!WinStationGetLoggedOnCount` at `0x18006715c`
- `WINSTA!WinStationGetLoggedOnCount` at `0x18006715c`

## string_xrefs

- `0x180067219`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Windows`

## pseudocode

```c
__int64 __fastcall DisplayExitWindowsWarnings(unsigned int a1)
{
  unsigned int v2; // edi
  ULONG SessionId; // ebx
  ULONG v4; // ebx
  bool v5; // zf
  int v6; // ebx
  int v7; // eax
  int v8; // edx
  unsigned int v9; // ebx
  int v10; // edx
  int v11; // esi
  ULONG Length; // [rsp+20h] [rbp-E0h]
  ULONG Lengtha; // [rsp+20h] [rbp-E0h]
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-CCh] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  __int128 KeyValueInformation; // [rsp+88h] [rbp-78h] BYREF
  int v22; // [rsp+98h] [rbp-68h]
  _BYTE v23[528]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[528]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v2 = 1;
  SessionId = NtCurrentPeb()->SessionId;
  if ( SessionId == (unsigned int)WTSGetServiceSessionId()
    || (v4 = NtCurrentPeb()->SessionId, v5 = v4 == (unsigned int)RtlGetActiveConsoleId(), v6 = 1, v5) )
  {
    v6 = 0;
  }
  v15 = 0;
  v16 = 0;
  WinStationGetLoggedOnCount(&v15, &v16);
  if ( (a1 & 0x4809) != 0 )
  {
    v7 = NeedsDisplayWarning(v15, v16, a1);
    if ( v6 )
    {
      if ( v7 )
      {
        if ( v15 <= 1 )
          v9 = 751;
        else
          v9 = v8 != 0 ? 752 : 712;
      }
      else
      {
        v9 = 711;
      }
    }
    else
    {
      if ( !v7 )
        return v2;
      if ( v15 <= 1 )
        v9 = 753;
      else
        v9 = v8 != 0 ? 754 : 713;
    }
  }
  else
  {
    if ( (a1 & 0x1002) == 0 || !(unsigned int)NeedsDisplayWarning(v15, v16, a1) )
      return v2;
    if ( v15 <= 1 )
      v9 = 755;
    else
      v9 = v10 != 0 ? 756 : 714;
  }
  KeyHandle = 0;
  ResultLength = 0;
  v22 = 0;
  DestinationString = 0;
  v11 = -1;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyValueInformation = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ShutdownWarningDialogTimeout");
    if ( NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformation,
           &KeyValueInformation,
           0x14u,
           &ResultLength) >= 0 )
      v11 = HIDWORD(KeyValueInformation);
    NtClose(KeyHandle);
  }
  LOWORD(Length) = 0;
  LoadStringBaseExW(hmodUser, 710, v23, 260, Length);
  LOWORD(Lengtha) = 0;
  LoadStringBaseExW(hmodUser, v9, v24, 260, Lengtha);
  if ( (unsigned int)MessageBoxTimeoutW(0, (unsigned int)v24, (unsigned int)v23, 2166836, 0, v11) == 7 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x1800670e0  push    rbp
0x1800670e2  push    rbx
0x1800670e3  push    rsi
0x1800670e4  push    rdi
0x1800670e5  push    r15
0x1800670e7  lea     rbp, [rsp-3D0h]
0x1800670ef  sub     rsp, 4D0h
0x1800670f6  mov     rax, cs:__security_cookie
0x1800670fd  xor     rax, rsp
0x180067100  mov     [rbp+3F0h+var_30], rax
0x180067107  mov     rax, gs:60h
0x180067110  mov     esi, ecx
0x180067112  mov     edi, 1
0x180067117  mov     ebx, [rax+2C0h]
0x18006711d  call    cs:__imp_WTSGetServiceSessionId
0x180067123  xor     r15d, r15d
0x180067126  cmp     ebx, eax
0x180067128  jz      short loc_180067145
0x18006712a  mov     rax, gs:60h
0x180067133  mov     ebx, [rax+2C0h]
0x180067139  call    cs:__imp_RtlGetActiveConsoleId
0x18006713f  cmp     ebx, eax
0x180067141  mov     ebx, edi
0x180067143  jnz     short loc_180067148
0x180067145  mov     ebx, r15d
0x180067148  lea     rdx, [rsp+4F0h+var_4BC]
0x18006714d  mov     [rsp+4F0h+var_4C0], r15d
0x180067152  lea     rcx, [rsp+4F0h+var_4C0]
0x180067157  mov     [rsp+4F0h+var_4BC], r15d
0x18006715c  call    cs:__imp_WinStationGetLoggedOnCount
0x180067162  test    esi, 4809h
0x180067168  jz      short loc_1800671C9
0x18006716a  mov     ecx, [rsp+4F0h+var_4C0]; unsigned int
0x18006716e  mov     r8d, esi; unsigned int
0x180067171  mov     edx, [rsp+4F0h+var_4BC]; unsigned int
0x180067175  call    ?NeedsDisplayWarning@@YAHIII@Z; NeedsDisplayWarning(uint,uint,uint)
0x18006717a  test    ebx, ebx
0x18006717c  jz      short loc_1800671A5
0x18006717e  test    eax, eax
0x180067180  jz      short loc_18006719E
0x180067182  cmp     [rsp+4F0h+var_4C0], edi
0x180067186  jbe     short loc_180067197
0x180067188  neg     edx
0x18006718a  sbb     ebx, ebx
0x18006718c  and     ebx, 28h
0x18006718f  add     ebx, 2C8h
0x180067195  jmp     short loc_180067207
0x180067197  mov     ebx, 2EFh
0x18006719c  jmp     short loc_180067207
0x18006719e  mov     ebx, 2C7h
0x1800671a3  jmp     short loc_180067207
0x1800671a5  test    eax, eax
0x1800671a7  jz      loc_180067346
0x1800671ad  cmp     [rsp+4F0h+var_4C0], edi
0x1800671b1  jbe     short loc_1800671C2
0x1800671b3  neg     edx
0x1800671b5  sbb     ebx, ebx
0x1800671b7  and     ebx, 29h
0x1800671ba  add     ebx, 2C9h
0x1800671c0  jmp     short loc_180067207
0x1800671c2  mov     ebx, 2F1h
0x1800671c7  jmp     short loc_180067207
0x1800671c9  test    esi, 1002h
0x1800671cf  jz      loc_180067346
0x1800671d5  mov     ecx, [rsp+4F0h+var_4C0]; unsigned int
0x1800671d9  mov     r8d, esi; unsigned int
0x1800671dc  mov     edx, [rsp+4F0h+var_4BC]; unsigned int
0x1800671e0  call    ?NeedsDisplayWarning@@YAHIII@Z; NeedsDisplayWarning(uint,uint,uint)
0x1800671e5  test    eax, eax
0x1800671e7  jz      loc_180067346
0x1800671ed  cmp     [rsp+4F0h+var_4C0], edi
0x1800671f1  jbe     short loc_180067202
0x1800671f3  neg     edx
0x1800671f5  sbb     ebx, ebx
0x1800671f7  and     ebx, 2Ah
0x1800671fa  add     ebx, 2CAh
0x180067200  jmp     short loc_180067207
0x180067202  mov     ebx, 2F3h
0x180067207  xorps   xmm1, xmm1
0x18006720a  mov     [rsp+4F0h+KeyHandle], r15
0x18006720f  xorps   xmm0, xmm0
0x180067212  mov     [rsp+4F0h+var_4B8], r15d
0x180067217  xor     eax, eax
0x180067219  lea     rdx, ?szWindowsKey@@3QBGB; "\\Registry\\Machine\\Software\\Microsof"...
0x180067220  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x180067225  mov     [rbp+3F0h+var_458], eax
0x180067228  movups  xmmword ptr [rsp+4F0h+DestinationString.Length], xmm0
0x18006722d  or      esi, 0FFFFFFFFh
0x180067230  movups  xmmword ptr [rsp+4F0h+ObjectAttributes.Length], xmm1
0x180067235  movups  xmmword ptr [rsp+4F0h+ObjectAttributes.ObjectName], xmm1
0x18006723a  movups  xmmword ptr [rsp+4F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18006723f  movups  [rbp+3F0h+KeyValueInformation], xmm0
0x180067243  call    cs:__imp_RtlInitUnicodeString
0x180067249  lea     rax, [rsp+4F0h+DestinationString]
0x18006724e  mov     [rsp+4F0h+ObjectAttributes.Length], 30h ; '0'
0x180067256  xorps   xmm0, xmm0
0x180067259  mov     [rsp+4F0h+ObjectAttributes.ObjectName], rax
0x18006725e  lea     r8, [rsp+4F0h+ObjectAttributes]; ObjectAttributes
0x180067263  mov     [rsp+4F0h+ObjectAttributes.RootDirectory], r15
0x180067268  mov     edx, 20019h; DesiredAccess
0x18006726d  mov     [rsp+4F0h+ObjectAttributes.Attributes], 40h ; '@'
0x180067275  lea     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x18006727a  movdqu  xmmword ptr [rsp+4F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180067280  call    cs:__imp_NtOpenKey
0x180067286  test    eax, eax
0x180067288  js      short loc_1800672D9
0x18006728a  lea     rdx, aShutdownwarnin; "ShutdownWarningDialogTimeout"
0x180067291  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x180067296  call    cs:__imp_RtlInitUnicodeString
0x18006729c  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x1800672a1  lea     rax, [rsp+4F0h+var_4B8]
0x1800672a6  mov     [rsp+4F0h+ResultLength], rax; ResultLength
0x1800672ab  lea     r9, [rbp+3F0h+KeyValueInformation]; KeyValueInformation
0x1800672af  mov     r8d, 2; KeyValueInformationClass
0x1800672b5  mov     [rsp+4F0h+Length], 14h; Length
0x1800672bd  lea     rdx, [rsp+4F0h+DestinationString]; ValueName
0x1800672c2  call    cs:__imp_NtQueryValueKey
0x1800672c8  mov     rcx, [rsp+4F0h+KeyHandle]; Handle
0x1800672cd  test    eax, eax
0x1800672cf  cmovns  esi, dword ptr [rbp+3F0h+KeyValueInformation+0Ch]
0x1800672d3  call    cs:__imp_NtClose
0x1800672d9  mov     rcx, cs:hmodUser
0x1800672e0  lea     r8, [rbp+3F0h+var_450]
0x1800672e4  mov     r9d, 104h
0x1800672ea  mov     word ptr [rsp+4F0h+Length], r15w
0x1800672f0  mov     edx, 2C6h
0x1800672f5  call    cs:__imp_LoadStringBaseExW
0x1800672fb  mov     rcx, cs:hmodUser
0x180067302  lea     r8, [rbp+3F0h+var_240]
0x180067309  mov     r9d, 104h
0x18006730f  mov     word ptr [rsp+4F0h+Length], r15w
0x180067315  mov     edx, ebx
0x180067317  call    cs:__imp_LoadStringBaseExW
0x18006731d  mov     r9d, 211034h
0x180067323  mov     dword ptr [rsp+4F0h+ResultLength], esi
0x180067327  lea     r8, [rbp+3F0h+var_450]
0x18006732b  mov     word ptr [rsp+4F0h+Length], r15w
0x180067331  lea     rdx, [rbp+3F0h+var_240]
0x180067338  xor     ecx, ecx
0x18006733a  call    MessageBoxTimeoutW
0x18006733f  cmp     eax, 7
0x180067342  cmovz   edi, r15d
0x180067346  mov     eax, edi
0x180067348  mov     rcx, [rbp+3F0h+var_30]
0x18006734f  xor     rcx, rsp; StackCookie
0x180067352  call    __security_check_cookie
0x180067357  add     rsp, 4D0h
0x18006735e  pop     r15
0x180067360  pop     rdi
0x180067361  pop     rsi
0x180067362  pop     rbx
0x180067363  pop     rbp
0x180067364  retn
```
