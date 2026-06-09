# CheckDirectoryOwnershipInternal(ushort const *,ulong,void *)

- ea: `0x180018b50`
- end: `0x180018feb`
- name: `?CheckDirectoryOwnershipInternal@@YAJPEBGKPEAX@Z`
- size: `1179`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, char, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014490`

## callees

- `0x1800053f0`
- `0x1800056a0`
- `0x1800078a0`
- `0x1800082d0`
- `0x18000cfe4`
- `0x18000d9b0`
- `0x180017a94`
- `0x180018b50`
- `0x18001992c`
- `0x180019c00`
- `0x180019c58`
- `0x180019f0c`
- `0x18001a144`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018bd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018c9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018db6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180018bcb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180018c92`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180018bcb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180018c92`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180018d09`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180018d09`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180018e84`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180018eb8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180018e84`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180018eb8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180018f81`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180018f81`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018dac`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180018dac`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018efb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180018efb`

## string_xrefs

- `0x180018bef`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180018c61`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180018cb5`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180018d2c`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180018dcf`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x180018e3a`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

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
      (void *)0xE60,
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
        (void *)0xE7D,
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
        (void *)0xE8E,
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
        (void *)0xEAB,
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
        (void *)0xEB9,
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
    (void *)0xE70,
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
0x180018b50  mov     [rsp-8+arg_8], rbx
0x180018b55  mov     [rsp-8+arg_18], rsi
0x180018b5a  push    rbp
0x180018b5b  push    rdi
0x180018b5c  push    r12
0x180018b5e  push    r14
0x180018b60  push    r15
0x180018b62  lea     rbp, [rsp-37h]
0x180018b67  sub     rsp, 0B0h
0x180018b6e  mov     rax, cs:__security_cookie
0x180018b75  xor     rax, rsp
0x180018b78  mov     [rbp+57h+var_30], rax
0x180018b7c  xor     r12d, r12d
0x180018b7f  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180018b85  mov     [rbp+57h+nLengthNeeded], r12d
0x180018b89  mov     r14, r8
0x180018b8c  mov     [rbp+57h+bOwnerDefaulted], r12d
0x180018b90  mov     esi, edx
0x180018b92  mov     [rbp+57h+pSid1], r12
0x180018b96  mov     rdi, rcx
0x180018b99  mov     [rbp+57h+lpMem], r12
0x180018b9d  mov     [rbp+57h+pOwner], r12
0x180018ba1  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x180018ba5  test    rcx, rcx
0x180018ba8  jz      loc_180018F73
0x180018bae  test    r8, r8
0x180018bb1  jz      loc_180018F73
0x180018bb7  lea     rax, [rbp+57h+nLengthNeeded]
0x180018bbb  xor     r9d, r9d; nLength
0x180018bbe  xor     r8d, r8d; pSecurityDescriptor
0x180018bc1  mov     [rsp+0D0h+lpnLengthNeeded], rax; int
0x180018bc6  lea     edx, [r12+1]; RequestedInformation
0x180018bcb  call    cs:__imp_GetFileSecurityW
0x180018bd1  call    cs:__imp_GetLastError
0x180018bd7  mov     ebx, eax
0x180018bd9  cmp     eax, 7Ah ; 'z'
0x180018bdc  jz      short loc_180018C38
0x180018bde  test    eax, eax
0x180018be0  jle     short loc_180018BEB
0x180018be2  movzx   ebx, ax
0x180018be5  or      ebx, 80070000h
0x180018beb  mov     rcx, [rbp+5Fh]; this
0x180018bef  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180018bf6  mov     r9d, ebx; char *
0x180018bf9  mov     edx, 0E60h; void *
0x180018bfe  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180018c03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018c0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018c0f  test    al, al
0x180018c11  jz      loc_180018F78
0x180018c17  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x180018c1e  jz      loc_180018F78
0x180018c24  mov     r8, rdi
0x180018c27  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_FILE_SECURITY_FAILED
0x180018c2e  call    McTemplateU0z_EventWriteTransfer
0x180018c33  jmp     loc_180018F78
0x180018c38  mov     ecx, [rbp+57h+nLengthNeeded]; dwBytes
0x180018c3b  call    ?ProfAlloc@@YAPEAX_K@Z; ProfAlloc(unsigned __int64)
0x180018c40  mov     r15, rax
0x180018c43  test    rax, rax
0x180018c46  jnz     short loc_180018C7A
0x180018c48  call    cs:__imp_GetLastError
0x180018c4e  mov     ebx, eax
0x180018c50  test    eax, eax
0x180018c52  jle     short loc_180018C5D
0x180018c54  movzx   ebx, ax
0x180018c57  or      ebx, 80070000h
0x180018c5d  mov     rcx, [rbp+5Fh]; this
0x180018c61  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180018c68  mov     r9d, ebx; char *
0x180018c6b  mov     edx, 0E70h; void *
0x180018c70  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180018c75  jmp     loc_180018F78
0x180018c7a  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180018c7e  lea     rax, [rbp+57h+nLengthNeeded]
0x180018c82  mov     r8, r15; pSecurityDescriptor
0x180018c85  mov     [rsp+0D0h+lpnLengthNeeded], rax; int
0x180018c8a  mov     edx, 1; RequestedInformation
0x180018c8f  mov     rcx, rdi; lpFileName
0x180018c92  call    cs:__imp_GetFileSecurityW
0x180018c98  test    eax, eax
0x180018c9a  jnz     short loc_180018CFE
0x180018c9c  call    cs:__imp_GetLastError
0x180018ca2  mov     ebx, eax
0x180018ca4  test    eax, eax
0x180018ca6  jle     short loc_180018CB1
0x180018ca8  movzx   ebx, ax
0x180018cab  or      ebx, 80070000h
0x180018cb1  mov     rcx, [rbp+5Fh]; this
0x180018cb5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180018cbc  mov     r9d, ebx; char *
0x180018cbf  mov     edx, 0E7Dh; void *
0x180018cc4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180018cc9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018cd0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018cd5  test    al, al
0x180018cd7  jz      loc_180018F69
0x180018cdd  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x180018ce4  jz      loc_180018F69
0x180018cea  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_FILE_SECURITY_FAILED
0x180018cf1  mov     r8, rdi
0x180018cf4  call    McTemplateU0z_EventWriteTransfer
0x180018cf9  jmp     loc_180018F69
0x180018cfe  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180018d02  mov     rcx, r15; pSecurityDescriptor
0x180018d05  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180018d09  call    cs:__imp_GetSecurityDescriptorOwner
0x180018d0f  test    eax, eax
0x180018d11  jnz     short loc_180018D6A
0x180018d13  call    cs:__imp_GetLastError
0x180018d19  mov     ebx, eax
0x180018d1b  test    eax, eax
0x180018d1d  jle     short loc_180018D28
0x180018d1f  movzx   ebx, ax
0x180018d22  or      ebx, 80070000h
0x180018d28  mov     rcx, [rbp+5Fh]; this
0x180018d2c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180018d33  mov     r9d, ebx; char *
0x180018d36  mov     edx, 0E8Eh; void *
0x180018d3b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180018d40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018d47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018d4c  test    al, al
0x180018d4e  jz      loc_180018F69
0x180018d54  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x180018d5b  jz      loc_180018F69
0x180018d61  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_SD_FAILED
0x180018d68  jmp     short loc_180018CF1
0x180018d6a  and     esi, 1
0x180018d6d  jz      loc_180018E24
0x180018d73  lea     rax, [rbp+57h+pSid1]
0x180018d77  mov     r9d, 220h; nSubAuthority1
0x180018d7d  mov     [rsp+0D0h+pSid], rax; pSid
0x180018d82  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180018d86  mov     [rsp+0D0h+nSubAuthority7], r12d; nSubAuthority7
0x180018d8b  mov     r8d, 20h ; ' '; nSubAuthority0
0x180018d91  mov     [rsp+0D0h+nSubAuthority6], r12d; nSubAuthority6
0x180018d96  mov     dl, 2; nSubAuthorityCount
0x180018d98  mov     [rsp+0D0h+nSubAuthority5], r12d; nSubAuthority5
0x180018d9d  mov     [rsp+0D0h+nSubAuthority4], r12d; nSubAuthority4
0x180018da2  mov     [rsp+0D0h+nSubAuthority3], r12d; nSubAuthority3
0x180018da7  mov     dword ptr [rsp+0D0h+lpnLengthNeeded], r12d; int
0x180018dac  call    cs:__imp_AllocateAndInitializeSid
0x180018db2  test    eax, eax
0x180018db4  jnz     short loc_180018E24
0x180018db6  call    cs:__imp_GetLastError
0x180018dbc  mov     ebx, eax
0x180018dbe  test    eax, eax
0x180018dc0  jle     short loc_180018DCB
0x180018dc2  movzx   ebx, ax
0x180018dc5  or      ebx, 80070000h
0x180018dcb  mov     rcx, [rbp+5Fh]; this
0x180018dcf  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180018dd6  mov     r9d, ebx; char *
0x180018dd9  mov     edx, 0EABh; void *
0x180018dde  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180018de3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018dea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018def  test    al, al
0x180018df1  jz      loc_180018F69
0x180018df7  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x180018dfe  jz      loc_180018F69
0x180018e04  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_ALLOC_SID_FAILED
0x180018e0b  lea     rax, [rbp+57h+StringSid]
0x180018e0f  mov     r9d, 1
0x180018e15  mov     [rsp+0D0h+lpnLengthNeeded], rax
0x180018e1a  call    McGenEventWrite_EventWriteTransfer
0x180018e1f  jmp     loc_180018F69
0x180018e24  lea     rdx, [rbp+57h+lpMem]; void **
0x180018e28  mov     rcx, r14; TokenHandle
0x180018e2b  call    ?GetUserSid@@YAJPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180018e30  mov     ebx, eax
0x180018e32  test    eax, eax
0x180018e34  jns     short loc_180018E78
0x180018e36  mov     rcx, [rbp+5Fh]; this
0x180018e3a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180018e41  mov     r9d, eax; char *
0x180018e44  mov     edx, 0EB9h; void *
0x180018e49  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018e4e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018e55  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018e5a  test    al, al
0x180018e5c  jz      loc_180018F69
0x180018e62  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x180018e69  jz      loc_180018F69
0x180018e6f  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_USER_SID_FAILED
0x180018e76  jmp     short loc_180018E0B
0x180018e78  test    esi, esi
0x180018e7a  jz      short loc_180018EB0
0x180018e7c  mov     rdx, [rbp+57h+pOwner]; pSid2
0x180018e80  mov     rcx, [rbp+57h+pSid1]; pSid1
0x180018e84  call    cs:__imp_EqualSid
0x180018e8a  test    eax, eax
0x180018e8c  jz      short loc_180018EB0
0x180018e8e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018e95  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018e9a  test    al, al
0x180018e9c  jz      short loc_180018EEA
0x180018e9e  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x180018ea5  jz      short loc_180018EEA
0x180018ea7  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_ADMIN_GROUP
0x180018eae  jmp     short loc_180018EE2
0x180018eb0  mov     rdx, [rbp+57h+pOwner]; pSid2
0x180018eb4  mov     rcx, [rbp+57h+lpMem]; pSid1
0x180018eb8  call    cs:__imp_EqualSid
0x180018ebe  test    eax, eax
0x180018ec0  jz      short loc_180018EEF
0x180018ec2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018ec9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018ece  test    al, al
0x180018ed0  jz      short loc_180018EEA
0x180018ed2  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x180018ed9  jz      short loc_180018EEA
0x180018edb  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_USER
0x180018ee2  mov     r8, rdi
0x180018ee5  call    McTemplateU0z_EventWriteTransfer
0x180018eea  mov     ebx, r12d
0x180018eed  jmp     short loc_180018F69
0x180018eef  mov     rcx, [rbp+57h+pOwner]; Sid
0x180018ef3  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180018ef7  mov     [rbp+57h+StringSid], r12
0x180018efb  call    cs:__imp_ConvertSidToStringSidW
0x180018f01  test    eax, eax
0x180018f03  jz      short loc_180018F3C
0x180018f05  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018f0c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018f11  test    al, al
0x180018f13  jz      short loc_180018F31
0x180018f15  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x180018f1c  jz      short loc_180018F31
0x180018f1e  mov     r9, [rbp+57h+StringSid]
0x180018f22  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_WRONG_USER
0x180018f29  mov     r8, rdi
0x180018f2c  call    McTemplateU0zz_EventWriteTransfer
0x180018f31  mov     rcx, [rbp+57h+StringSid]
0x180018f35  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180018f3a  jmp     short loc_180018F64
0x180018f3c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018f43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018f48  test    al, al
0x180018f4a  jz      short loc_180018F64
0x180018f4c  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x180018f53  jz      short loc_180018F64
0x180018f55  mov     r8, rdi
0x180018f58  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_UNKNOWN_USER
0x180018f5f  call    McTemplateU0z_EventWriteTransfer
0x180018f64  mov     ebx, 8007051Bh
0x180018f69  mov     rcx, r15
0x180018f6c  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180018f71  jmp     short loc_180018F78
0x180018f73  mov     ebx, 80070057h
0x180018f78  mov     rcx, [rbp+57h+pSid1]; pSid
0x180018f7c  test    rcx, rcx
0x180018f7f  jz      short loc_180018F87
0x180018f81  call    cs:__imp_FreeSid
0x180018f87  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180018f8b  test    rcx, rcx
0x180018f8e  jz      short loc_180018F95
0x180018f90  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180018f95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x180018f9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x180018fa1  test    al, al
0x180018fa3  jz      short loc_180018FC1
0x180018fa5  test    ebx, ebx
0x180018fa7  jz      short loc_180018FC1
0x180018fa9  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 20h
0x180018fb0  jz      short loc_180018FC1
0x180018fb2  mov     r8d, ebx
0x180018fb5  lea     rdx, EVENT_CHECK_DIR_OWNERSHIP_FAILED
0x180018fbc  call    McTemplateU0d_EventWriteTransfer
0x180018fc1  mov     eax, ebx
0x180018fc3  mov     rcx, [rbp+57h+var_30]
0x180018fc7  xor     rcx, rsp; StackCookie
0x180018fca  call    __security_check_cookie
0x180018fcf  lea     r11, [rsp+0D0h+var_20]
0x180018fd7  mov     rbx, [r11+38h]
0x180018fdb  mov     rsi, [r11+48h]
0x180018fdf  mov     rsp, r11
0x180018fe2  pop     r15
0x180018fe4  pop     r14
0x180018fe6  pop     r12
0x180018fe8  pop     rdi
0x180018fe9  pop     rbp
0x180018fea  retn
```
