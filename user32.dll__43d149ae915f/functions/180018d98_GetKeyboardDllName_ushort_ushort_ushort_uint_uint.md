# GetKeyboardDllName(ushort *,ushort *,ushort,uint *,uint *)

- ea: `0x180018d98`
- end: `0x1800192ed`
- name: `?GetKeyboardDllName@@YAPEAGPEAG0GPEAI1@Z`
- size: `1365`
- prototype: `unsigned __int16 *(unsigned __int16 *, unsigned __int16 *, unsigned __int16, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001867c`
- `0x1800193b4`
- `0x1800731c0`

## callees

- `0x180018d98`
- `0x18001a8e0`
- `0x18004c348`
- `0x18004ed44`
- `0x180093a74`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `ntdll!wcstoul` at `0x180018e48`
- `ntdll!wcstoul` at `0x180018edf`
- `ntdll!wcstoul` at `0x180018f1b`
- `ntdll!wcstoul` at `0x180018e48`
- `ntdll!wcstoul` at `0x180018edf`
- `ntdll!wcstoul` at `0x180018f1b`
- `ntdll!wcstol` at `0x1800190fc`
- `ntdll!wcstol` at `0x1800190fc`
- `ntdll!RtlGetActiveConsoleId` at `0x18001921e`
- `ntdll!RtlGetActiveConsoleId` at `0x18001921e`
- `ntdll!NtQueryValueKey` at `0x180018fe0`
- `ntdll!NtQueryValueKey` at `0x18001903d`
- `ntdll!NtQueryValueKey` at `0x1800190d8`
- `ntdll!NtQueryValueKey` at `0x1800191aa`
- `ntdll!NtQueryValueKey` at `0x180018fe0`
- `ntdll!NtQueryValueKey` at `0x18001903d`
- `ntdll!NtQueryValueKey` at `0x1800190d8`
- `ntdll!NtQueryValueKey` at `0x1800191aa`
- `ntdll!NtClose` at `0x18001911c`
- `ntdll!NtClose` at `0x1800191cc`
- `ntdll!NtClose` at `0x18001911c`
- `ntdll!NtClose` at `0x1800191cc`
- `ntdll!NtOpenKey` at `0x180018f9a`
- `ntdll!NtOpenKey` at `0x18001916e`
- `ntdll!NtOpenKey` at `0x180018f9a`
- `ntdll!NtOpenKey` at `0x18001916e`
- `ntdll!RtlInitUnicodeString` at `0x180018f5d`
- `ntdll!RtlInitUnicodeString` at `0x180018fb4`
- `ntdll!RtlInitUnicodeString` at `0x180019013`
- `ntdll!RtlInitUnicodeString` at `0x1800190ae`
- `ntdll!RtlInitUnicodeString` at `0x18001912e`
- `ntdll!RtlInitUnicodeString` at `0x180019180`
- `ntdll!RtlInitUnicodeString` at `0x180018f5d`
- `ntdll!RtlInitUnicodeString` at `0x180018fb4`
- `ntdll!RtlInitUnicodeString` at `0x180019013`
- `ntdll!RtlInitUnicodeString` at `0x1800190ae`
- `ntdll!RtlInitUnicodeString` at `0x18001912e`
- `ntdll!RtlInitUnicodeString` at `0x180019180`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180018ef2`
- `api-ms-win-core-privateprofile-l1-1-0!WritePrivateProfileStringW` at `0x180018ef2`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180018e84`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180018ec2`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180018e84`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringW` at `0x180018ec2`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180019205`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180019205`

## string_xrefs

- `0x180019273`: `kbdus.dll`
- `0x1800192a5`: `kbdus.dll`
- `0x180018f27`: `\Registry\Machine\System\CurrentControlSet\Control\Keyboard Layouts\`
- `0x18001924d`: `kbdjpn.dll`
- `0x180019262`: `kbdkor.dll`
- `0x180019127`: `\Registry\Machine\System\CurrentControlSet\Control\Keyboard Layout`

## pseudocode

```c
unsigned __int16 *__fastcall GetKeyboardDllName(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 a3,
        unsigned int *a4,
        unsigned int *a5)
{
  unsigned __int16 *v7; // rdi
  unsigned __int16 *result; // rax
  unsigned int v10; // r15d
  unsigned int v11; // esi
  unsigned int v12; // r11d
  NTSTATUS v13; // eax
  int v14; // ecx
  NTSTATUS v15; // eax
  int v16; // ecx
  NTSTATUS v17; // eax
  int v18; // ebx
  int v19; // r15d
  ULONG SessionId; // ebx
  ULONG v21; // ebx
  __int16 v22; // r14
  int v23; // eax
  const unsigned __int16 *v24; // r8
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+88h] [rbp-78h] BYREF
  int v31; // [rsp+98h] [rbp-68h]
  wchar_t v32[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-50h]
  __int128 v34; // [rsp+C0h] [rbp-40h]
  _BYTE KeyValueInformation[12]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v36[510]; // [rsp+DCh] [rbp-24h] BYREF
  __int16 v37; // [rsp+2DAh] [rbp+1DAh]
  WCHAR String[8]; // [rsp+2E0h] [rbp+1E0h] BYREF
  WCHAR ReturnedString[16]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR SourceString[160]; // [rsp+310h] [rbp+210h] BYREF

  v29 = a1;
  v7 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(KeyValueInformation, 0, 0x210u);
  result = 0;
  v31 = 0;
  *(_OWORD *)v32 = 0;
  v33 = 0;
  v34 = 0;
  v30 = 0;
  if ( a2 )
  {
    v10 = 0;
    if ( !a3 )
      a3 = wcstoul(a2, 0, 16);
    if ( (*(_BYTE *)a4 & 2) != 0 )
    {
      GetPrivateProfileStringW(L"Substitutes", a2, a2, ReturnedString, 9u, L"keyboardlayout.ini");
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomKeyboardProfiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CustomKeyboardProfiles>::GetImpl'::`2'::impl)
        && GetPrivateProfileStringW(L"Custom", a2, 0, String, 5u, L"keyboardlayout.ini") )
      {
        String[4] = 0;
        v10 = wcstoul(String, 0, 16);
      }
      WritePrivateProfileStringW(0, 0, 0, 0);
      ReturnedString[8] = 0;
      StringCchCopyW(a2, 9u, ReturnedString);
    }
    v11 = wcstoul(a2, 0, 16);
    StringCchCopyW(SourceString, 0x9Au, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Keyboard Layouts\\");
    StringCchCatW(SourceString, v12, a2);
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 )
    {
      RtlInitUnicodeString(
        &DestinationString,
        L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Keyboard Layout");
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, a2);
        v17 = NtQueryValueKey(
                KeyHandle,
                &DestinationString,
                KeyValuePartialInformation,
                KeyValueInformation,
                0x210u,
                &ResultLength);
        v18 = 0;
        if ( v17 != -2147483643 )
          v18 = v17;
        if ( v18 >= 0 )
          v37 = 0;
        NtClose(KeyHandle);
        v7 = (unsigned __int16 *)v36;
        if ( v18 < 0 )
          v7 = 0;
      }
    }
    else
    {
      RtlInitUnicodeString(&DestinationString, L"Layout File");
      v13 = NtQueryValueKey(
              KeyHandle,
              &DestinationString,
              KeyValuePartialInformation,
              KeyValueInformation,
              0x210u,
              &ResultLength);
      v14 = 0;
      if ( v13 != -2147483643 )
        v14 = v13;
      if ( v14 >= 0 )
        v37 = 0;
      v7 = (unsigned __int16 *)v36;
      if ( v14 < 0 )
        v7 = 0;
      RtlInitUnicodeString(&DestinationString, L"Attributes");
      if ( NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, &v30, 0x14u, &ResultLength) >= 0 )
        *a4 |= HIDWORD(v30) & 0xFF0000;
      if ( (HIWORD(v11) & 0xF000) == 0xE000 )
      {
        v11 >>= 16;
      }
      else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomKeyboardProfiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CustomKeyboardProfiles>::GetImpl'::`2'::impl)
             && v10 )
      {
        v11 = v10 & 0xFFF | 0xC000;
      }
      else if ( HIWORD(v11) )
      {
        RtlInitUnicodeString(&DestinationString, L"Layout ID");
        v15 = NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v32, 0x30u, &ResultLength);
        v16 = 0;
        if ( v15 != -2147483643 )
          v16 = v15;
        if ( v16 < 0 )
        {
          v11 = 65534;
        }
        else
        {
          WORD5(v34) = 0;
          v11 = wcstol(&v32[6], 0, 16) & 0xFFF | 0xF000;
        }
      }
      NtClose(KeyHandle);
    }
    v19 = a3;
    *a5 = a3 | ((unsigned __int16)v11 << 16);
    if ( !v7 )
    {
      SessionId = NtCurrentPeb()->SessionId;
      if ( SessionId == (unsigned int)WTSGetServiceSessionId()
        || (v21 = NtCurrentPeb()->SessionId, v21 == (unsigned int)RtlGetActiveConsoleId())
        || (HIWORD(v11) & 0xF000) != 0xE000 )
      {
        if ( (*a4 & 0x80000000) == 0
          && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_60490815>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KeyboardSettings_60490815>::GetImpl'::`2'::impl) )
        {
          return v7;
        }
        *a5 = 67699721;
        v7 = L"kbdus.dll";
      }
      else
      {
        v22 = a3 & 0x3FF;
        if ( v22 == 17 )
        {
          v7 = L"kbdjpn.dll";
          v23 = 68224017;
        }
        else if ( v22 == 18 )
        {
          v7 = L"kbdkor.dll";
          v23 = 68289554;
        }
        else
        {
          v7 = L"kbdus.dll";
          v23 = v19 | (v19 << 16);
        }
        *a5 = v23;
      }
    }
    v24 = v7;
    v7 = v29;
    StringCchCopyW(v29, 0x104u, v24);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180018d98  mov     [rsp-8+arg_10], rbx
0x180018d9d  push    rbp
0x180018d9e  push    rsi
0x180018d9f  push    rdi
0x180018da0  push    r12
0x180018da2  push    r13
0x180018da4  push    r14
0x180018da6  push    r15
0x180018da8  lea     rbp, [rsp-360h]
0x180018db0  sub     rsp, 460h
0x180018db7  mov     rax, cs:__security_cookie
0x180018dbe  xor     rax, rsp
0x180018dc1  mov     [rbp+390h+var_40], rax
0x180018dc8  mov     r12, [rbp+390h+arg_20]
0x180018dcf  xorps   xmm1, xmm1
0x180018dd2  movzx   r14d, r8w
0x180018dd6  mov     [rbp+390h+var_410], rcx
0x180018dda  mov     rbx, rdx
0x180018ddd  lea     rcx, [rbp+390h+KeyValueInformation]; void *
0x180018de1  xorps   xmm0, xmm0
0x180018de4  xor     edi, edi
0x180018de6  xor     edx, edx; Val
0x180018de8  mov     [rsp+490h+KeyHandle], rdi
0x180018ded  mov     r8d, 210h; Size
0x180018df3  mov     [rsp+490h+ResultLength], edi
0x180018df7  movups  xmmword ptr [rsp+490h+DestinationString.Length], xmm0
0x180018dfc  mov     r13, r9
0x180018dff  movups  xmmword ptr [rsp+490h+ObjectAttributes.Length], xmm1
0x180018e04  movups  xmmword ptr [rsp+490h+ObjectAttributes.ObjectName], xmm1
0x180018e09  movups  xmmword ptr [rsp+490h+ObjectAttributes.SecurityDescriptor], xmm1
0x180018e0e  call    memset_0
0x180018e13  xorps   xmm0, xmm0
0x180018e16  xor     eax, eax
0x180018e18  mov     [rbp+390h+var_3F8], eax
0x180018e1b  movups  xmmword ptr [rbp+390h+var_3F0], xmm0
0x180018e1f  movups  [rbp+390h+var_3E0], xmm0
0x180018e23  movups  [rbp+390h+var_3D0], xmm0
0x180018e27  movups  [rbp+390h+var_408], xmm0
0x180018e2b  test    rbx, rbx
0x180018e2e  jz      loc_1800192C3
0x180018e34  lea     esi, [rdi+10h]
0x180018e37  mov     r15d, edi
0x180018e3a  test    r14w, r14w
0x180018e3e  jnz     short loc_180018E51
0x180018e40  mov     r8d, esi; Radix
0x180018e43  xor     edx, edx; EndPtr
0x180018e45  mov     rcx, rbx; String
0x180018e48  call    cs:__imp_wcstoul
0x180018e4e  mov     r14d, eax
0x180018e51  test    byte ptr [r13+0], 2
0x180018e56  jz      loc_180018F13
0x180018e5c  lea     rax, FileName; "keyboardlayout.ini"
0x180018e63  mov     r8, rbx; lpDefault
0x180018e66  mov     [rsp+490h+lpFileName], rax; lpFileName
0x180018e6b  lea     r9, [rbp+390h+ReturnedString]; lpReturnedString
0x180018e72  mov     rdx, rbx; lpKeyName
0x180018e75  mov     [rsp+490h+nSize], 9; nSize
0x180018e7d  lea     rcx, AppName; "Substitutes"
0x180018e84  call    cs:__imp_GetPrivateProfileStringW
0x180018e8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CustomKeyboardProfiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CustomKeyboardProfiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomKeyboardProfiles> `wil::Feature<__WilFeatureTraits_Feature_CustomKeyboardProfiles>::GetImpl(void)'::`2'::impl
0x180018e91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomKeyboardProfiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomKeyboardProfiles>::__private_IsEnabled(void)
0x180018e96  test    al, al
0x180018e98  jz      short loc_180018EE8
0x180018e9a  lea     rax, FileName; "keyboardlayout.ini"
0x180018ea1  xor     r8d, r8d; lpDefault
0x180018ea4  mov     [rsp+490h+lpFileName], rax; lpFileName
0x180018ea9  lea     r9, [rbp+390h+String]; lpReturnedString
0x180018eb0  mov     rdx, rbx; lpKeyName
0x180018eb3  mov     [rsp+490h+nSize], 5; nSize
0x180018ebb  lea     rcx, aCustom; "Custom"
0x180018ec2  call    cs:__imp_GetPrivateProfileStringW
0x180018ec8  test    eax, eax
0x180018eca  jz      short loc_180018EE8
0x180018ecc  mov     r8d, esi; Radix
0x180018ecf  mov     [rbp+390h+var_1A8], di
0x180018ed6  xor     edx, edx; EndPtr
0x180018ed8  lea     rcx, [rbp+390h+String]; String
0x180018edf  call    cs:__imp_wcstoul
0x180018ee5  mov     r15d, eax
0x180018ee8  xor     r9d, r9d; lpFileName
0x180018eeb  xor     r8d, r8d; lpString
0x180018eee  xor     edx, edx; lpKeyName
0x180018ef0  xor     ecx, ecx; lpAppName
0x180018ef2  call    cs:__imp_WritePrivateProfileStringW
0x180018ef8  lea     r8, [rbp+390h+ReturnedString]; unsigned __int16 *
0x180018eff  mov     [rbp+390h+var_190], di
0x180018f06  mov     edx, 9; unsigned __int64
0x180018f0b  mov     rcx, rbx; unsigned __int16 *
0x180018f0e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018f13  mov     r8d, esi; Radix
0x180018f16  xor     edx, edx; EndPtr
0x180018f18  mov     rcx, rbx; String
0x180018f1b  call    cs:__imp_wcstoul
0x180018f21  mov     r11d, 9Ah
0x180018f27  lea     r8, aRegistryMachin_4; "\\Registry\\Machine\\System\\CurrentCon"...
0x180018f2e  mov     edx, r11d; unsigned __int64
0x180018f31  lea     rcx, [rbp+390h+SourceString]; unsigned __int16 *
0x180018f38  mov     esi, eax
0x180018f3a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018f3f  mov     r8, rbx; unsigned __int16 *
0x180018f42  lea     rcx, [rbp+390h+SourceString]; unsigned __int16 *
0x180018f49  mov     edx, r11d; unsigned __int64
0x180018f4c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018f51  lea     rdx, [rbp+390h+SourceString]; SourceString
0x180018f58  lea     rcx, [rsp+490h+DestinationString]; DestinationString
0x180018f5d  call    cs:__imp_RtlInitUnicodeString
0x180018f63  lea     rax, [rsp+490h+DestinationString]
0x180018f68  mov     [rsp+490h+ObjectAttributes.Length], 30h ; '0'
0x180018f70  xorps   xmm0, xmm0
0x180018f73  mov     [rsp+490h+ObjectAttributes.ObjectName], rax
0x180018f78  lea     r8, [rsp+490h+ObjectAttributes]; ObjectAttributes
0x180018f7d  mov     [rsp+490h+ObjectAttributes.RootDirectory], rdi
0x180018f82  mov     edx, 20019h; DesiredAccess
0x180018f87  mov     [rsp+490h+ObjectAttributes.Attributes], 40h ; '@'
0x180018f8f  lea     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180018f94  movdqu  xmmword ptr [rsp+490h+ObjectAttributes.SecurityDescriptor], xmm0
0x180018f9a  call    cs:__imp_NtOpenKey
0x180018fa0  lea     rcx, [rsp+490h+DestinationString]; DestinationString
0x180018fa5  test    eax, eax
0x180018fa7  js      loc_180019127
0x180018fad  lea     rdx, aLayoutFile; "Layout File"
0x180018fb4  call    cs:__imp_RtlInitUnicodeString
0x180018fba  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180018fbf  lea     rax, [rsp+490h+ResultLength]
0x180018fc4  mov     [rsp+490h+lpFileName], rax; ResultLength
0x180018fc9  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x180018fcd  mov     r8d, 2; KeyValueInformationClass
0x180018fd3  mov     [rsp+490h+nSize], 210h; Length
0x180018fdb  lea     rdx, [rsp+490h+DestinationString]; ValueName
0x180018fe0  call    cs:__imp_NtQueryValueKey
0x180018fe6  cmp     eax, 80000005h
0x180018feb  mov     ecx, edi
0x180018fed  cmovnz  ecx, eax
0x180018ff0  test    ecx, ecx
0x180018ff2  js      short loc_180018FFB
0x180018ff4  mov     [rbp+390h+var_1B6], di
0x180018ffb  xor     ebx, ebx
0x180018ffd  lea     rdi, [rbp+390h+var_3B4]
0x180019001  test    ecx, ecx
0x180019003  lea     rdx, aAttributes; "Attributes"
0x18001900a  lea     rcx, [rsp+490h+DestinationString]; DestinationString
0x18001900f  cmovs   rdi, rbx
0x180019013  call    cs:__imp_RtlInitUnicodeString
0x180019019  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18001901e  lea     rax, [rsp+490h+ResultLength]
0x180019023  mov     [rsp+490h+lpFileName], rax; ResultLength
0x180019028  lea     r9, [rbp+390h+var_408]; KeyValueInformation
0x18001902c  lea     r8d, [rbx+2]; KeyValueInformationClass
0x180019030  mov     [rsp+490h+nSize], 14h; Length
0x180019038  lea     rdx, [rsp+490h+DestinationString]; ValueName
0x18001903d  call    cs:__imp_NtQueryValueKey
0x180019043  test    eax, eax
0x180019045  js      short loc_180019053
0x180019047  mov     eax, dword ptr [rbp+390h+var_408+0Ch]
0x18001904a  and     eax, 0FF0000h
0x18001904f  or      [r13+0], eax
0x180019053  mov     ecx, 0F000h
0x180019058  mov     ebx, esi
0x18001905a  shr     ebx, 10h
0x18001905d  movzx   eax, bx
0x180019060  and     ax, cx
0x180019063  mov     ecx, 0E000h
0x180019068  cmp     ax, cx
0x18001906b  jnz     short loc_180019074
0x18001906d  mov     esi, ebx
0x18001906f  jmp     loc_180019117
0x180019074  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CustomKeyboardProfiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CustomKeyboardProfiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomKeyboardProfiles> `wil::Feature<__WilFeatureTraits_Feature_CustomKeyboardProfiles>::GetImpl(void)'::`2'::impl
0x18001907b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CustomKeyboardProfiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CustomKeyboardProfiles>::__private_IsEnabled(void)
0x180019080  test    al, al
0x180019082  jz      short loc_18001909A
0x180019084  test    r15d, r15d
0x180019087  jz      short loc_18001909A
0x180019089  mov     esi, r15d
0x18001908c  and     esi, 0FFFh
0x180019092  or      esi, 0C000h
0x180019098  jmp     short loc_180019117
0x18001909a  xor     r15d, r15d
0x18001909d  test    bx, bx
0x1800190a0  jz      short loc_180019117
0x1800190a2  lea     rdx, aLayoutId; "Layout ID"
0x1800190a9  lea     rcx, [rsp+490h+DestinationString]; DestinationString
0x1800190ae  call    cs:__imp_RtlInitUnicodeString
0x1800190b4  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x1800190b9  lea     rax, [rsp+490h+ResultLength]
0x1800190be  mov     [rsp+490h+lpFileName], rax; ResultLength
0x1800190c3  lea     r9, [rbp+390h+var_3F0]; KeyValueInformation
0x1800190c7  lea     r8d, [r15+2]; KeyValueInformationClass
0x1800190cb  mov     [rsp+490h+nSize], 30h ; '0'; Length
0x1800190d3  lea     rdx, [rsp+490h+DestinationString]; ValueName
0x1800190d8  call    cs:__imp_NtQueryValueKey
0x1800190de  cmp     eax, 80000005h
0x1800190e3  mov     ecx, r15d
0x1800190e6  cmovnz  ecx, eax
0x1800190e9  test    ecx, ecx
0x1800190eb  js      short loc_180019112
0x1800190ed  xor     edx, edx; EndPtr
0x1800190ef  mov     word ptr [rbp+390h+var_3D0+0Ah], r15w
0x1800190f4  lea     r8d, [r15+10h]; Radix
0x1800190f8  lea     rcx, [rbp+390h+var_3F0+0Ch]; String
0x1800190fc  call    cs:__imp_wcstol
0x180019102  mov     esi, eax
0x180019104  and     esi, 0FFFh
0x18001910a  or      esi, 0F000h
0x180019110  jmp     short loc_180019117
0x180019112  mov     esi, 0FFFEh
0x180019117  mov     rcx, [rsp+490h+KeyHandle]; Handle
0x18001911c  call    cs:__imp_NtClose
0x180019122  jmp     loc_1800191DC
0x180019127  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x18001912e  call    cs:__imp_RtlInitUnicodeString
0x180019134  lea     rax, [rsp+490h+DestinationString]
0x180019139  mov     [rsp+490h+ObjectAttributes.Length], 30h ; '0'
0x180019141  xorps   xmm0, xmm0
0x180019144  mov     [rsp+490h+ObjectAttributes.ObjectName], rax
0x180019149  xor     r15d, r15d
0x18001914c  mov     [rsp+490h+ObjectAttributes.Attributes], 40h ; '@'
0x180019154  lea     r8, [rsp+490h+ObjectAttributes]; ObjectAttributes
0x180019159  mov     [rsp+490h+ObjectAttributes.RootDirectory], r15
0x18001915e  mov     edx, 20019h; DesiredAccess
0x180019163  lea     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x180019168  movdqu  xmmword ptr [rsp+490h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001916e  call    cs:__imp_NtOpenKey
0x180019174  test    eax, eax
0x180019176  js      short loc_1800191DC
0x180019178  mov     rdx, rbx; SourceString
0x18001917b  lea     rcx, [rsp+490h+DestinationString]; DestinationString
0x180019180  call    cs:__imp_RtlInitUnicodeString
0x180019186  mov     rcx, [rsp+490h+KeyHandle]; KeyHandle
0x18001918b  lea     rax, [rsp+490h+ResultLength]
0x180019190  mov     [rsp+490h+lpFileName], rax; ResultLength
0x180019195  lea     r9, [rbp+390h+KeyValueInformation]; KeyValueInformation
0x180019199  lea     r8d, [r15+2]; KeyValueInformationClass
0x18001919d  mov     [rsp+490h+nSize], 210h; Length
0x1800191a5  lea     rdx, [rsp+490h+DestinationString]; ValueName
0x1800191aa  call    cs:__imp_NtQueryValueKey
0x1800191b0  cmp     eax, 80000005h
0x1800191b5  mov     ebx, r15d
0x1800191b8  cmovnz  ebx, eax
0x1800191bb  test    ebx, ebx
0x1800191bd  js      short loc_1800191C7
0x1800191bf  mov     [rbp+390h+var_1B6], r15w
0x1800191c7  mov     rcx, [rsp+490h+KeyHandle]; Handle
0x1800191cc  call    cs:__imp_NtClose
0x1800191d2  test    ebx, ebx
0x1800191d4  lea     rdi, [rbp+390h+var_3B4]
0x1800191d8  cmovs   rdi, r15
0x1800191dc  movzx   eax, si
0x1800191df  shl     eax, 10h
0x1800191e2  movzx   r15d, r14w
0x1800191e6  or      eax, r15d
0x1800191e9  mov     [r12], eax
0x1800191ed  test    rdi, rdi
0x1800191f0  jnz     loc_1800192AC
0x1800191f6  mov     rax, gs:60h
0x1800191ff  mov     ebx, [rax+2C0h]
0x180019205  call    cs:__imp_WTSGetServiceSessionId
0x18001920b  cmp     ebx, eax
0x18001920d  jz      short loc_180019286
0x18001920f  mov     rax, gs:60h
0x180019218  mov     ebx, [rax+2C0h]
0x18001921e  call    cs:__imp_RtlGetActiveConsoleId
0x180019224  cmp     ebx, eax
0x180019226  jz      short loc_180019286
0x180019228  shr     esi, 10h
0x18001922b  mov     eax, 0F000h
0x180019230  and     si, ax
0x180019233  mov     eax, 0E000h
0x180019238  cmp     si, ax
0x18001923b  jnz     short loc_180019286
0x18001923d  mov     eax, 3FFh
0x180019242  and     r14w, ax
0x180019246  cmp     r14w, 11h
0x18001924b  jnz     short loc_18001925B
0x18001924d  lea     rdi, aKbdjpnDll; "kbdjpn.dll"
0x180019254  mov     eax, 4110411h
0x180019259  jmp     short loc_180019280
0x18001925b  cmp     r14w, 12h
0x180019260  jnz     short loc_180019270
0x180019262  lea     rdi, aKbdkorDll; "kbdkor.dll"
0x180019269  mov     eax, 4120412h
0x18001926e  jmp     short loc_180019280
0x180019270  mov     eax, r15d
0x180019273  lea     rdi, aKbdusDll; "kbdus.dll"
0x18001927a  shl     eax, 10h
0x18001927d  or      eax, r15d
0x180019280  mov     [r12], eax
0x180019284  jmp     short loc_1800192AC
0x180019286  cmp     dword ptr [r13+0], 0
0x18001928b  jl      short loc_18001929D
0x18001928d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KeyboardSettings_60490815@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KeyboardSettings_60490815@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_60490815> `wil::Feature<__WilFeatureTraits_Feature_KeyboardSettings_60490815>::GetImpl(void)'::`2'::impl
0x180019294  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KeyboardSettings_60490815@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeyboardSettings_60490815>::__private_IsEnabled(void)
0x180019299  test    al, al
0x18001929b  jnz     short loc_1800192C0
0x18001929d  mov     dword ptr [r12], 4090409h
0x1800192a5  lea     rdi, aKbdusDll; "kbdus.dll"
0x1800192ac  mov     r8, rdi; unsigned __int16 *
0x1800192af  mov     edx, 104h; unsigned __int64
0x1800192b4  mov     rdi, [rbp+390h+var_410]
0x1800192b8  mov     rcx, rdi; unsigned __int16 *
0x1800192bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
  ... truncated ...
```
