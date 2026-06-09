# CheckDirectoryOwnershipInternal(ushort const *,ulong,void *)

- ea: `0x18001a508`
- end: `0x18001a9f8`
- name: `?CheckDirectoryOwnershipInternal@@YAJPEBGKPEAX@Z`
- size: `1264`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180015640`

## callees

- `0x180005b30`
- `0x180005e10`
- `0x1800079f0`
- `0x180008940`
- `0x18000dc50`
- `0x18000e640`
- `0x180019404`
- `0x18001a508`
- `0x18001b3b4`
- `0x18001b6a4`
- `0x18001b704`
- `0x18001b9c4`
- `0x18001bc04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a58f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a60c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a58f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a60c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a7a1`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001a583`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001a65c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001a583`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001a65c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001a6df`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001a6df`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a875`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a8af`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a875`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001a8af`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001a987`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001a987`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001a791`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001a791`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a8fb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001a8fb`

## string_xrefs

- `0x18001a5b3`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001a62b`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001a68b`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001a70e`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001a7c0`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18001a82b`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall CheckDirectoryOwnershipInternal(LPCWSTR lpFileName, char a2, void *a3)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  void *v9; // r15
  signed int v10; // eax
  signed int v11; // eax
  __int64 v12; // rcx
  __int64 *v13; // rdx
  signed int v14; // eax
  int v15; // esi
  signed int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 *v19; // rdx
  int UserSid; // eax
  __int64 v21; // rcx
  __int64 *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int lpnLengthNeeded; // [rsp+20h] [rbp-59h]
  int lpnLengthNeededa; // [rsp+20h] [rbp-59h]
  DWORD nLengthNeeded; // [rsp+60h] [rbp-19h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-11h] BYREF
  BOOL bOwnerDefaulted; // [rsp+70h] [rbp-9h] BYREF
  PSID pSid1; // [rsp+78h] [rbp-1h] BYREF
  PSID lpMem; // [rsp+80h] [rbp+7h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+Fh] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  nLengthNeeded = 0;
  bOwnerDefaulted = 0;
  pSid1 = 0;
  lpMem = 0;
  pOwner = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !lpFileName || !a3 )
  {
    v7 = -2147024809;
    goto LABEL_60;
  }
  GetFileSecurityW(lpFileName, 1u, 0, 0, &nLengthNeeded);
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xE64,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
      (const char *)v7,
      lpnLengthNeeded);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v8, EVENT_CHECK_DIR_OWNERSHIP_FILE_SECURITY_FAILED, lpFileName);
    }
    goto LABEL_60;
  }
  v9 = ProfAlloc(nLengthNeeded);
  if ( v9 )
  {
    if ( !GetFileSecurityW(lpFileName, 1u, v9, nLengthNeeded, &nLengthNeeded) )
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xE81,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)v7,
        lpnLengthNeededa);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) == 0 )
      {
        goto LABEL_58;
      }
      v13 = EVENT_CHECK_DIR_OWNERSHIP_FILE_SECURITY_FAILED;
      goto LABEL_19;
    }
    if ( !GetSecurityDescriptorOwner(v9, &pOwner, &bOwnerDefaulted) )
    {
      v14 = GetLastError();
      v7 = v14;
      if ( v14 > 0 )
        v7 = (unsigned __int16)v14 | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xE92,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)v7,
        lpnLengthNeededa);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) == 0 )
      {
        goto LABEL_58;
      }
      v13 = EVENT_CHECK_DIR_OWNERSHIP_SD_FAILED;
LABEL_19:
      McTemplateU0z_EventWriteTransfer(v12, v13, lpFileName);
LABEL_58:
      Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v9);
      goto LABEL_60;
    }
    v15 = a2 & 1;
    if ( v15 && !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid1) )
    {
      v16 = GetLastError();
      v7 = v16;
      if ( v16 > 0 )
        v7 = (unsigned __int16)v16 | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xEAF,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)v7,
        lpnLengthNeededa);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) == 0 )
      {
        goto LABEL_58;
      }
      v19 = EVENT_CHECK_DIR_OWNERSHIP_ALLOC_SID_FAILED;
LABEL_33:
      McGenEventWrite_EventWriteTransfer(v17, v19, v18, 1);
      goto LABEL_58;
    }
    UserSid = GetUserSid(a3, &lpMem);
    v7 = UserSid;
    if ( UserSid < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xEBD,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)(unsigned int)UserSid,
        lpnLengthNeededa);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) == 0 )
      {
        goto LABEL_58;
      }
      v19 = EVENT_CHECK_DIR_OWNERSHIP_USER_SID_FAILED;
      goto LABEL_33;
    }
    if ( v15 && EqualSid(pSid1, pOwner) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) == 0 )
      {
        goto LABEL_48;
      }
      v22 = EVENT_CHECK_DIR_OWNERSHIP_ADMIN_GROUP;
    }
    else
    {
      if ( !EqualSid(lpMem, pOwner) )
      {
        StringSid = 0;
        if ( ConvertSidToStringSidW(pOwner, &StringSid) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
            && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
          {
            McTemplateU0zz_EventWriteTransfer(v23, EVENT_CHECK_DIR_OWNERSHIP_WRONG_USER, lpFileName, StringSid);
          }
          Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(StringSid);
        }
        else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
               && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(v24, EVENT_CHECK_DIR_OWNERSHIP_UNKNOWN_USER, lpFileName);
        }
        v7 = -2147023589;
        goto LABEL_58;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
        || (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) == 0 )
      {
        goto LABEL_48;
      }
      v22 = EVENT_CHECK_DIR_OWNERSHIP_USER;
    }
    McTemplateU0z_EventWriteTransfer(v21, v22, lpFileName);
LABEL_48:
    v7 = 0;
    goto LABEL_58;
  }
  v10 = GetLastError();
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0xE74,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
    (const char *)v7,
    lpnLengthNeeded);
LABEL_60:
  if ( pSid1 )
    FreeSid(pSid1);
  if ( lpMem )
    ResultFromHeapFree(lpMem);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
    && v7
    && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 0x20) != 0 )
  {
    McTemplateU0d_EventWriteTransfer(v25, EVENT_CHECK_DIR_OWNERSHIP_FAILED, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x18001a508  mov     [rsp-8+arg_8], rbx
0x18001a50d  mov     [rsp-8+arg_18], rsi
0x18001a512  push    rbp
0x18001a513  push    rdi
0x18001a514  push    r12
0x18001a516  push    r14
0x18001a518  push    r15
0x18001a51a  lea     rbp, [rsp-37h]
0x18001a51f  sub     rsp, 0B0h
0x18001a526  mov     rax, cs:__security_cookie
0x18001a52d  xor     rax, rsp
0x18001a530  mov     [rbp+57h+var_30], rax
0x18001a534  xor     r12d, r12d
0x18001a537  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18001a53d  mov     [rbp+57h+nLengthNeeded], r12d
0x18001a541  mov     r14, r8
0x18001a544  mov     [rbp+57h+bOwnerDefaulted], r12d
0x18001a548  mov     esi, edx
0x18001a54a  mov     [rbp+57h+pSid1], r12
0x18001a54e  mov     rdi, rcx
0x18001a551  mov     [rbp+57h+lpMem], r12
0x18001a555  mov     [rbp+57h+pOwner], r12
0x18001a559  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x18001a55d  test    rcx, rcx
0x18001a560  jz      loc_18001A979
0x18001a566  test    r8, r8
0x18001a569  jz      loc_18001A979
0x18001a56f  lea     rax, [rbp+57h+nLengthNeeded]
0x18001a573  xor     r9d, r9d; nLength
0x18001a576  xor     r8d, r8d; pSecurityDescriptor
0x18001a579  mov     [rsp+0D0h+lpnLengthNeeded], rax; int
0x18001a57e  lea     edx, [r12+1]; RequestedInformation
0x18001a583  call    cs:__imp_GetFileSecurityW
0x18001a58a  nop     dword ptr [rax+rax+00h]
0x18001a58f  call    cs:__imp_GetLastError
0x18001a596  nop     dword ptr [rax+rax+00h]
0x18001a59b  mov     ebx, eax
0x18001a59d  cmp     eax, 7Ah ; 'z'
0x18001a5a0  jz      short loc_18001A5FC
0x18001a5a2  test    eax, eax
0x18001a5a4  jle     short loc_18001A5AF
0x18001a5a6  movzx   ebx, ax
0x18001a5a9  or      ebx, 80070000h
0x18001a5af  mov     rcx, [rbp+5Fh]; this
0x18001a5b3  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001a5ba  mov     r9d, ebx; char *
0x18001a5bd  mov     edx, 0E64h; void *
0x18001a5c2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001a5c7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a5ce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a5d3  test    al, al
0x18001a5d5  jz      loc_18001A97E
0x18001a5db  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18001a5e2  jz      loc_18001A97E
0x18001a5e8  mov     r8, rdi
0x18001a5eb  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_FILE_SECURITY_FAILED
0x18001a5f2  call    McTemplateU0z_EventWriteTransfer
0x18001a5f7  jmp     loc_18001A97E
0x18001a5fc  mov     ecx, [rbp+57h+nLengthNeeded]; dwBytes
0x18001a5ff  call    ?ProfAlloc@@YAPEAX_K@Z; ProfAlloc(unsigned __int64)
0x18001a604  mov     r15, rax
0x18001a607  test    rax, rax
0x18001a60a  jnz     short loc_18001A644
0x18001a60c  call    cs:__imp_GetLastError
0x18001a613  nop     dword ptr [rax+rax+00h]
0x18001a618  mov     ebx, eax
0x18001a61a  test    eax, eax
0x18001a61c  jle     short loc_18001A627
0x18001a61e  movzx   ebx, ax
0x18001a621  or      ebx, 80070000h
0x18001a627  mov     rcx, [rbp+5Fh]; this
0x18001a62b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001a632  mov     r9d, ebx; char *
0x18001a635  mov     edx, 0E74h; void *
0x18001a63a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001a63f  jmp     loc_18001A97E
0x18001a644  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x18001a648  lea     rax, [rbp+57h+nLengthNeeded]
0x18001a64c  mov     r8, r15; pSecurityDescriptor
0x18001a64f  mov     [rsp+0D0h+lpnLengthNeeded], rax; int
0x18001a654  mov     edx, 1; RequestedInformation
0x18001a659  mov     rcx, rdi; lpFileName
0x18001a65c  call    cs:__imp_GetFileSecurityW
0x18001a663  nop     dword ptr [rax+rax+00h]
0x18001a668  test    eax, eax
0x18001a66a  jnz     short loc_18001A6D4
0x18001a66c  call    cs:__imp_GetLastError
0x18001a673  nop     dword ptr [rax+rax+00h]
0x18001a678  mov     ebx, eax
0x18001a67a  test    eax, eax
0x18001a67c  jle     short loc_18001A687
0x18001a67e  movzx   ebx, ax
0x18001a681  or      ebx, 80070000h
0x18001a687  mov     rcx, [rbp+5Fh]; this
0x18001a68b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001a692  mov     r9d, ebx; char *
0x18001a695  mov     edx, 0E81h; void *
0x18001a69a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001a69f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a6a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a6ab  test    al, al
0x18001a6ad  jz      loc_18001A96F
0x18001a6b3  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18001a6ba  jz      loc_18001A96F
0x18001a6c0  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_FILE_SECURITY_FAILED
0x18001a6c7  mov     r8, rdi
0x18001a6ca  call    McTemplateU0z_EventWriteTransfer
0x18001a6cf  jmp     loc_18001A96F
0x18001a6d4  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18001a6d8  mov     rcx, r15; pSecurityDescriptor
0x18001a6db  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18001a6df  call    cs:__imp_GetSecurityDescriptorOwner
0x18001a6e6  nop     dword ptr [rax+rax+00h]
0x18001a6eb  test    eax, eax
0x18001a6ed  jnz     short loc_18001A74F
0x18001a6ef  call    cs:__imp_GetLastError
0x18001a6f6  nop     dword ptr [rax+rax+00h]
0x18001a6fb  mov     ebx, eax
0x18001a6fd  test    eax, eax
0x18001a6ff  jle     short loc_18001A70A
0x18001a701  movzx   ebx, ax
0x18001a704  or      ebx, 80070000h
0x18001a70a  mov     rcx, [rbp+5Fh]; this
0x18001a70e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001a715  mov     r9d, ebx; char *
0x18001a718  mov     edx, 0E92h; void *
0x18001a71d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001a722  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a729  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a72e  test    al, al
0x18001a730  jz      loc_18001A96F
0x18001a736  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18001a73d  jz      loc_18001A96F
0x18001a743  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_SD_FAILED
0x18001a74a  jmp     loc_18001A6C7
0x18001a74f  and     esi, 1
0x18001a752  jz      loc_18001A815
0x18001a758  lea     rax, [rbp+57h+pSid1]
0x18001a75c  mov     r9d, 220h; nSubAuthority1
0x18001a762  mov     [rsp+0D0h+pSid], rax; pSid
0x18001a767  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001a76b  mov     [rsp+0D0h+nSubAuthority7], r12d; nSubAuthority7
0x18001a770  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001a776  mov     [rsp+0D0h+nSubAuthority6], r12d; nSubAuthority6
0x18001a77b  mov     dl, 2; nSubAuthorityCount
0x18001a77d  mov     [rsp+0D0h+nSubAuthority5], r12d; nSubAuthority5
0x18001a782  mov     [rsp+0D0h+nSubAuthority4], r12d; nSubAuthority4
0x18001a787  mov     [rsp+0D0h+nSubAuthority3], r12d; nSubAuthority3
0x18001a78c  mov     dword ptr [rsp+0D0h+lpnLengthNeeded], r12d; int
0x18001a791  call    cs:__imp_AllocateAndInitializeSid
0x18001a798  nop     dword ptr [rax+rax+00h]
0x18001a79d  test    eax, eax
0x18001a79f  jnz     short loc_18001A815
0x18001a7a1  call    cs:__imp_GetLastError
0x18001a7a8  nop     dword ptr [rax+rax+00h]
0x18001a7ad  mov     ebx, eax
0x18001a7af  test    eax, eax
0x18001a7b1  jle     short loc_18001A7BC
0x18001a7b3  movzx   ebx, ax
0x18001a7b6  or      ebx, 80070000h
0x18001a7bc  mov     rcx, [rbp+5Fh]; this
0x18001a7c0  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001a7c7  mov     r9d, ebx; char *
0x18001a7ca  mov     edx, 0EAFh; void *
0x18001a7cf  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001a7d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a7db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a7e0  test    al, al
0x18001a7e2  jz      loc_18001A96F
0x18001a7e8  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18001a7ef  jz      loc_18001A96F
0x18001a7f5  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_ALLOC_SID_FAILED
0x18001a7fc  lea     rax, [rbp+57h+StringSid]
0x18001a800  mov     r9d, 1
0x18001a806  mov     [rsp+0D0h+lpnLengthNeeded], rax
0x18001a80b  call    McGenEventWrite_EventWriteTransfer
0x18001a810  jmp     loc_18001A96F
0x18001a815  lea     rdx, [rbp+57h+lpMem]; void **
0x18001a819  mov     rcx, r14; TokenHandle
0x18001a81c  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x18001a821  mov     ebx, eax
0x18001a823  test    eax, eax
0x18001a825  jns     short loc_18001A869
0x18001a827  mov     rcx, [rbp+5Fh]; this
0x18001a82b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x18001a832  mov     r9d, eax; char *
0x18001a835  mov     edx, 0EBDh; void *
0x18001a83a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a83f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a846  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a84b  test    al, al
0x18001a84d  jz      loc_18001A96F
0x18001a853  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18001a85a  jz      loc_18001A96F
0x18001a860  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_USER_SID_FAILED
0x18001a867  jmp     short loc_18001A7FC
0x18001a869  test    esi, esi
0x18001a86b  jz      short loc_18001A8A7
0x18001a86d  mov     rdx, [rbp+57h+pOwner]; pSid2
0x18001a871  mov     rcx, [rbp+57h+pSid1]; pSid1
0x18001a875  call    cs:__imp_EqualSid
0x18001a87c  nop     dword ptr [rax+rax+00h]
0x18001a881  test    eax, eax
0x18001a883  jz      short loc_18001A8A7
0x18001a885  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a88c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a891  test    al, al
0x18001a893  jz      short loc_18001A8E7
0x18001a895  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18001a89c  jz      short loc_18001A8E7
0x18001a89e  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_ADMIN_GROUP
0x18001a8a5  jmp     short loc_18001A8DF
0x18001a8a7  mov     rdx, [rbp+57h+pOwner]; pSid2
0x18001a8ab  mov     rcx, [rbp+57h+lpMem]; pSid1
0x18001a8af  call    cs:__imp_EqualSid
0x18001a8b6  nop     dword ptr [rax+rax+00h]
0x18001a8bb  test    eax, eax
0x18001a8bd  jz      short loc_18001A8EF
0x18001a8bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a8c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a8cb  test    al, al
0x18001a8cd  jz      short loc_18001A8E7
0x18001a8cf  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18001a8d6  jz      short loc_18001A8E7
0x18001a8d8  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_USER
0x18001a8df  mov     r8, rdi
0x18001a8e2  call    McTemplateU0z_EventWriteTransfer
0x18001a8e7  mov     ebx, r12d
0x18001a8ea  jmp     loc_18001A96F
0x18001a8ef  mov     rcx, [rbp+57h+pOwner]; Sid
0x18001a8f3  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18001a8f7  mov     [rbp+57h+StringSid], r12
0x18001a8fb  call    cs:__imp_ConvertSidToStringSidW
0x18001a902  nop     dword ptr [rax+rax+00h]
0x18001a907  test    eax, eax
0x18001a909  jz      short loc_18001A942
0x18001a90b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a912  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a917  test    al, al
0x18001a919  jz      short loc_18001A937
0x18001a91b  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18001a922  jz      short loc_18001A937
0x18001a924  mov     r9, [rbp+57h+StringSid]
0x18001a928  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_WRONG_USER
0x18001a92f  mov     r8, rdi
0x18001a932  call    McTemplateU0zz_EventWriteTransfer
0x18001a937  mov     rcx, [rbp+57h+StringSid]
0x18001a93b  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001a940  jmp     short loc_18001A96A
0x18001a942  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a949  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a94e  test    al, al
0x18001a950  jz      short loc_18001A96A
0x18001a952  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18001a959  jz      short loc_18001A96A
0x18001a95b  mov     r8, rdi
0x18001a95e  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_UNKNOWN_USER
0x18001a965  call    McTemplateU0z_EventWriteTransfer
0x18001a96a  mov     ebx, 8007051Bh
0x18001a96f  mov     rcx, r15
0x18001a972  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18001a977  jmp     short loc_18001A97E
0x18001a979  mov     ebx, 80070057h
0x18001a97e  mov     rcx, [rbp+57h+pSid1]; pSid
0x18001a982  test    rcx, rcx
0x18001a985  jz      short loc_18001A993
0x18001a987  call    cs:__imp_FreeSid
0x18001a98e  nop     dword ptr [rax+rax+00h]
0x18001a993  mov     rcx, [rbp+57h+lpMem]; lpMem
0x18001a997  test    rcx, rcx
0x18001a99a  jz      short loc_18001A9A1
0x18001a99c  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18001a9a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001a9a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001a9ad  test    al, al
0x18001a9af  jz      short loc_18001A9CD
0x18001a9b1  test    ebx, ebx
0x18001a9b3  jz      short loc_18001A9CD
0x18001a9b5  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x18001a9bc  jz      short loc_18001A9CD
0x18001a9be  mov     r8d, ebx
0x18001a9c1  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_FAILED
0x18001a9c8  call    McTemplateU0d_EventWriteTransfer
0x18001a9cd  mov     eax, ebx
0x18001a9cf  mov     rcx, [rbp+57h+var_30]
0x18001a9d3  xor     rcx, rsp; StackCookie
0x18001a9d6  call    __security_check_cookie
0x18001a9db  lea     r11, [rsp+0D0h+var_20]
0x18001a9e3  mov     rbx, [r11+38h]
0x18001a9e7  mov     rsi, [r11+48h]
0x18001a9eb  mov     rsp, r11
0x18001a9ee  pop     r15
0x18001a9f0  pop     r14
0x18001a9f2  pop     r12
0x18001a9f4  pop     rdi
0x18001a9f5  pop     rbp
0x18001a9f6  retn
```
