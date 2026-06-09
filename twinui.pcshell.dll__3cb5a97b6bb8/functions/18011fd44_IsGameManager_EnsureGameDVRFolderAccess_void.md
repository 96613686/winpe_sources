# IsGameManager::EnsureGameDVRFolderAccess(void)

- ea: `0x18011fd44`
- end: `0x18011ffbc`
- name: `?EnsureGameDVRFolderAccess@IsGameManager@@AEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(IsGameManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18011ecd8`

## callees

- `0x1800237c8`
- `0x18008b6a0`
- `0x18011fd44`
- `0x1801206d0`
- `0x180120f8c`
- `0x1802c56a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fde3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fe59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011feb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fde3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fe59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011feb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011fdaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011fef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ffac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011fdaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011fef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18011ffac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011fe3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011ff1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011fe3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011ff1e`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18011fe4b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18011fe4b`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18011ff82`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18011ff9e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18011ff82`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18011ff9e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011feab`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18011feab`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18011fdd9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18011fdd9`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18011ff49`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18011ff49`

## string_xrefs

- `0x18011fd8d`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18011fe00`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18011fed7`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`
- `0x18011ff57`: `pcshell\twinui\broadcastdvrcomponent\lib\isgamemanager.cpp`

## pseudocode

```c
__int64 __fastcall IsGameManager::EnsureGameDVRFolderAccess(IsGameManager *this, __int64 a2)
{
  int KnownFolderSubFolder; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  HSTRING v6; // rbx
  const WCHAR *StringRawBuffer; // rax
  signed int v8; // eax
  signed int v9; // edi
  __int64 v10; // rdx
  signed int v11; // eax
  struct _ACL *v12; // rdi
  WCHAR *v13; // rax
  DWORD v14; // eax
  int psidGroup; // [rsp+20h] [rbp-40h]
  unsigned int psidGroupa; // [rsp+20h] [rbp-40h]
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+40h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HSTRING string; // [rsp+80h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+88h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp+30h] BYREF
  PACL pDacl; // [rsp+98h] [rbp+38h] BYREF

  string = (HSTRING)this;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GameMRU>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_GameMRU>::GetImpl'::`2'::impl,
    a2);
  string = 0;
  KnownFolderSubFolder = GetKnownFolderSubFolder(
                           &FOLDERID_LocalAppData,
                           L"Microsoft\\GameDVR",
                           0,
                           (struct Windows::Internal::String *)&string);
  v3 = KnownFolderSubFolder;
  if ( KnownFolderSubFolder < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x264,
      (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
      (const char *)(unsigned int)KnownFolderSubFolder,
      psidGroup);
LABEL_3:
    if ( string )
      WindowsDeleteString(string);
    return v3;
  }
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;CIOI;0x111FFFFF;;;CO)(A;CIOI;0x111FFFFF;;;SY)(A;CIOI;0x111FFFFF;;;BA)(A;CIOI;GRGXGW;;;S-1-15-3-1024-44950"
           "0426-4112254358-3456904286-1727260714-2501084857-171973213-3131658879-2198086578)(A;CIOI;GRGXGW;;;S-1-5-32-44"
           "9500426-4112254358-3456904286-1727260714-2501084857-171973213-3131658879-2198086578)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( (v3 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26B,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)v3,
        psidGroup);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
    goto LABEL_3;
  }
  v6 = string;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.bInheritHandle = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( !CreateDirectoryW(StringRawBuffer, &SecurityAttributes) )
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 != 80 && v8 != 183 )
    {
      if ( v8 > 0 )
        v9 = (unsigned __int16)v8 | 0x80070000;
      if ( v9 >= 0 )
        goto LABEL_25;
      v10 = 654;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
        (const char *)(unsigned int)v9,
        psidGroup);
LABEL_25:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
LABEL_26:
      if ( v6 )
        WindowsDeleteString(v6);
      return (unsigned int)v9;
    }
    pDacl = 0;
    bDaclPresent = 0;
    LODWORD(string) = 0;
    if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, (LPBOOL)&string) )
    {
      v11 = GetLastError();
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 >= 0 )
        goto LABEL_25;
      v10 = 636;
      goto LABEL_24;
    }
    v12 = pDacl;
    if ( !pDacl )
    {
      v9 = -2147024891;
      v10 = 643;
      goto LABEL_24;
    }
    v13 = (WCHAR *)WindowsGetStringRawBuffer(v6, 0);
    v14 = SetNamedSecurityInfoW(v13, SE_FILE_OBJECT, 4u, 0, 0, v12, 0);
    if ( v14 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x28A,
             (unsigned int)"pcshell\\twinui\\broadcastdvrcomponent\\lib\\isgamemanager.cpp",
             (const char *)v14,
             psidGroupa);
      if ( SecurityDescriptor )
      {
        ObjectDescriptor = SecurityDescriptor;
        DestroyPrivateObjectSecurity(&ObjectDescriptor);
      }
      goto LABEL_26;
    }
  }
  if ( SecurityDescriptor )
  {
    string = (HSTRING)SecurityDescriptor;
    DestroyPrivateObjectSecurity((PSECURITY_DESCRIPTOR *)&string);
  }
  if ( v6 )
    WindowsDeleteString(v6);
  return 0;
}

```

## disassembly

```asm
0x18011fd44  mov     [rsp-18h+string], rcx
0x18011fd49  push    rbp
0x18011fd4a  push    rbx
0x18011fd4b  push    rdi
0x18011fd4c  mov     rbp, rsp
0x18011fd4f  sub     rsp, 60h
0x18011fd53  mov     dl, 1
0x18011fd55  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GameMRU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GameMRU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GameMRU> `wil::Feature<__WilFeatureTraits_Feature_GameMRU>::GetImpl(void)'::`2'::impl
0x18011fd5c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GameMRU@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GameMRU>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18011fd61  lea     r9, [rbp+string]; struct Windows::Internal::String *
0x18011fd65  mov     [rbp+string], 0
0x18011fd6d  xor     r8d, r8d; unsigned __int16 *
0x18011fd70  lea     rdx, aMicrosoftGamed_0; "Microsoft\\GameDVR"
0x18011fd77  lea     rcx, FOLDERID_LocalAppData; struct _GUID *
0x18011fd7e  call    ?GetKnownFolderSubFolder@@YAJAEBU_GUID@@PEBG1PEAVString@Internal@Windows@@@Z; GetKnownFolderSubFolder(_GUID const &,ushort const *,ushort const *,Windows::Internal::String *)
0x18011fd83  mov     ebx, eax
0x18011fd85  test    eax, eax
0x18011fd87  jns     short loc_18011FDB7
0x18011fd89  mov     rcx, [rbp+18h]; this
0x18011fd8d  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18011fd94  mov     r9d, eax; char *
0x18011fd97  mov     edx, 264h; void *
0x18011fd9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011fda1  mov     rcx, [rbp+string]; string
0x18011fda5  test    rcx, rcx
0x18011fda8  jz      short loc_18011FDB0
0x18011fdaa  call    cs:__imp_WindowsDeleteString
0x18011fdb0  mov     eax, ebx
0x18011fdb2  jmp     loc_18011FFB4
0x18011fdb7  xor     eax, eax
0x18011fdb9  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18011fdbd  xorps   xmm0, xmm0
0x18011fdc0  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x18011fdc4  xor     r9d, r9d; SecurityDescriptorSize
0x18011fdc7  mov     [rbp+SecurityDescriptor], rax
0x18011fdcb  lea     rcx, StringSecurityDescriptor; "D:(A;CIOI;0x111FFFFF;;;CO)(A;CIOI;0x111"...
0x18011fdd2  lea     edx, [rax+1]; StringSDRevision
0x18011fdd5  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x18011fdd9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18011fddf  test    eax, eax
0x18011fde1  jnz     short loc_18011FE1F
0x18011fde3  call    cs:__imp_GetLastError
0x18011fde9  mov     ebx, eax
0x18011fdeb  test    eax, eax
0x18011fded  jle     short loc_18011FDF8
0x18011fdef  movzx   ebx, ax
0x18011fdf2  or      ebx, 80070000h
0x18011fdf8  test    ebx, ebx
0x18011fdfa  jns     short loc_18011FE14
0x18011fdfc  mov     rcx, [rbp+18h]; this
0x18011fe00  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18011fe07  mov     r9d, ebx; char *
0x18011fe0a  mov     edx, 26Bh; void *
0x18011fe0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011fe14  lea     rcx, [rbp+SecurityDescriptor]
0x18011fe18  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18011fe1d  jmp     short loc_18011FDA1
0x18011fe1f  mov     rax, [rbp+SecurityDescriptor]
0x18011fe23  xor     edx, edx; length
0x18011fe25  mov     rbx, [rbp+string]
0x18011fe29  mov     rcx, rbx; string
0x18011fe2c  mov     [rbp+SecurityAttributes.nLength], 18h
0x18011fe33  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18011fe37  mov     [rbp+SecurityAttributes.bInheritHandle], 0
0x18011fe3e  call    cs:__imp_WindowsGetStringRawBuffer
0x18011fe44  mov     rcx, rax; lpPathName
0x18011fe47  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x18011fe4b  call    cs:__imp_CreateDirectoryW
0x18011fe51  test    eax, eax
0x18011fe53  jnz     loc_18011FF8D
0x18011fe59  call    cs:__imp_GetLastError
0x18011fe5f  mov     edi, eax
0x18011fe61  cmp     eax, 50h ; 'P'
0x18011fe64  jz      short loc_18011FE85
0x18011fe66  cmp     eax, 0B7h
0x18011fe6b  jz      short loc_18011FE85
0x18011fe6d  test    eax, eax
0x18011fe6f  jle     short loc_18011FE7A
0x18011fe71  movzx   edi, ax
0x18011fe74  or      edi, 80070000h
0x18011fe7a  test    edi, edi
0x18011fe7c  jns     short loc_18011FEE6
0x18011fe7e  mov     edx, 28Eh
0x18011fe83  jmp     short loc_18011FED3
0x18011fe85  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18011fe89  lea     r9, [rbp+string]; lpbDaclDefaulted
0x18011fe8d  lea     r8, [rbp+pDacl]; pDacl
0x18011fe91  mov     [rbp+pDacl], 0
0x18011fe99  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18011fe9d  mov     [rbp+bDaclPresent], 0
0x18011fea4  mov     dword ptr [rbp+string], 0
0x18011feab  call    cs:__imp_GetSecurityDescriptorDacl
0x18011feb1  test    eax, eax
0x18011feb3  jnz     short loc_18011FF04
0x18011feb5  call    cs:__imp_GetLastError
0x18011febb  mov     edi, eax
0x18011febd  test    eax, eax
0x18011febf  jle     short loc_18011FECA
0x18011fec1  movzx   edi, ax
0x18011fec4  or      edi, 80070000h
0x18011feca  test    edi, edi
0x18011fecc  jns     short loc_18011FEE6
0x18011fece  mov     edx, 27Ch; void *
0x18011fed3  mov     rcx, [rbp+18h]; this
0x18011fed7  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18011fede  mov     r9d, edi; char *
0x18011fee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011fee6  lea     rcx, [rbp+SecurityDescriptor]
0x18011feea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18011feef  test    rbx, rbx
0x18011fef2  jz      short loc_18011FEFD
0x18011fef4  mov     rcx, rbx; string
0x18011fef7  call    cs:__imp_WindowsDeleteString
0x18011fefd  mov     eax, edi
0x18011feff  jmp     loc_18011FFB4
0x18011ff04  mov     rdi, [rbp+pDacl]
0x18011ff08  test    rdi, rdi
0x18011ff0b  jnz     short loc_18011FF19
0x18011ff0d  mov     edi, 80070005h
0x18011ff12  mov     edx, 283h
0x18011ff17  jmp     short loc_18011FED3
0x18011ff19  xor     edx, edx; length
0x18011ff1b  mov     rcx, rbx; string
0x18011ff1e  call    cs:__imp_WindowsGetStringRawBuffer
0x18011ff24  xor     r9d, r9d; psidOwner
0x18011ff27  mov     [rsp+60h+pSacl], 0; pSacl
0x18011ff30  mov     [rsp+60h+var_38], rdi; pDacl
0x18011ff35  mov     rcx, rax; pObjectName
0x18011ff38  mov     [rsp+60h+psidGroup], 0; unsigned int
0x18011ff41  lea     edx, [r9+1]; ObjectType
0x18011ff45  lea     r8d, [r9+4]; SecurityInfo
0x18011ff49  call    cs:__imp_SetNamedSecurityInfoW
0x18011ff4f  test    eax, eax
0x18011ff51  jz      short loc_18011FF8D
0x18011ff53  mov     rcx, [rbp+18h]; this
0x18011ff57  lea     r8, aPcshellTwinuiB; "pcshell\\twinui\\broadcastdvrcomponent"...
0x18011ff5e  mov     r9d, eax; char *
0x18011ff61  mov     edx, 28Ah; void *
0x18011ff66  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011ff6b  mov     rcx, [rbp+SecurityDescriptor]
0x18011ff6f  mov     edi, eax
0x18011ff71  test    rcx, rcx
0x18011ff74  jz      loc_18011FEEF
0x18011ff7a  mov     [rbp+ObjectDescriptor], rcx
0x18011ff7e  lea     rcx, [rbp+ObjectDescriptor]; ObjectDescriptor
0x18011ff82  call    cs:__imp_DestroyPrivateObjectSecurity
0x18011ff88  jmp     loc_18011FEEF
0x18011ff8d  mov     rax, [rbp+SecurityDescriptor]
0x18011ff91  test    rax, rax
0x18011ff94  jz      short loc_18011FFA4
0x18011ff96  lea     rcx, [rbp+string]; ObjectDescriptor
0x18011ff9a  mov     [rbp+string], rax
0x18011ff9e  call    cs:__imp_DestroyPrivateObjectSecurity
0x18011ffa4  test    rbx, rbx
0x18011ffa7  jz      short loc_18011FFB2
0x18011ffa9  mov     rcx, rbx; string
0x18011ffac  call    cs:__imp_WindowsDeleteString
0x18011ffb2  xor     eax, eax
0x18011ffb4  add     rsp, 60h
0x18011ffb8  pop     rdi
0x18011ffb9  pop     rbx
0x18011ffba  pop     rbp
0x18011ffbb  retn
```
