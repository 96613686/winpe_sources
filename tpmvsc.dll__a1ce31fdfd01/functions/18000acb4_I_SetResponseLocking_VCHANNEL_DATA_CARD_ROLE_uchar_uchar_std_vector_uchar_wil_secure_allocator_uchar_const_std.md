# I_SetResponseLocking(VCHANNEL_DATA *,_CARD_ROLE,uchar,uchar,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)

- ea: `0x18000acb4`
- end: `0x18000b855`
- name: `?I_SetResponseLocking@@YAKPEAUVCHANNEL_DATA@@W4_CARD_ROLE@@EEAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV34@@Z`
- size: `2977`
- prototype: `__int64 __fastcall(struct VCHANNEL_DATA *, unsigned int, unsigned __int8, char, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f338`

## callees

- `0x180001ec0`
- `0x180002a90`
- `0x180006128`
- `0x1800064bc`
- `0x1800064e4`
- `0x18000653c`
- `0x180006644`
- `0x1800068bc`
- `0x1800069b8`
- `0x1800069e4`
- `0x180007064`
- `0x1800079b8`
- `0x1800079e4`
- `0x18000a028`
- `0x18000acb4`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c198`
- `0x18000f6a0`
- `0x18000fafc`
- `0x18000fcb0`
- `0x1800116a0`
- `0x1800190ac`
- `0x180019cb4`
- `0x18001e9a8`
- `0x18002356c`
- `0x180024f14`
- `0x180028494`
- `0x18002b378`
- `0x1800348a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b3c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000af05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b3c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae0a`

## string_xrefs

- `0x18000b2c8`: `Unable to cache auth key`
- `0x18000b38b`: `Unable to update challenge`
- `0x18000b573`: `Response is not complete`

## pseudocode

```c
__int64 __fastcall I_SetResponseLocking(
        struct VCHANNEL_DATA *a1,
        unsigned int a2,
        unsigned __int8 a3,
        char a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  RTL_SRWLOCK *v10; // rdi
  __int64 v11; // rcx
  unsigned int v12; // ebx
  _QWORD *v13; // rcx
  int v14; // edx
  const char *v15; // rax
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  int v18; // edx
  const char *v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  int v22; // edx
  const char *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // edx
  int v27; // r8d
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rcx
  struct VCHANNEL_DATA *v34; // rcx
  __int64 v35; // rcx
  _QWORD *v36; // rcx
  int v37; // edx
  const char *v38; // rax
  unsigned __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  unsigned int Handle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v44; // [rsp+38h] [rbp-C8h] BYREF
  char v45; // [rsp+40h] [rbp-C0h] BYREF
  struct VCHANNEL_DATA *v46; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+58h] [rbp-A8h] BYREF
  char *p_hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-98h]
  NCRYPT_KEY_HANDLE hKey; // [rsp+78h] [rbp-88h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+88h] [rbp-78h]
  _QWORD *v54; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v55[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v57; // [rsp+C0h] [rbp-40h]
  _QWORD v58[3]; // [rsp+D0h] [rbp-30h] BYREF
  struct VCHANNEL_DATA **v59; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v60; // [rsp+F0h] [rbp-10h]
  _QWORD v61[3]; // [rsp+F8h] [rbp-8h] BYREF
  RTL_SRWLOCK *v62; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v63[3]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v64[5]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v65[3]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v66[3]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v67[3]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v68[80]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v69; // [rsp+1F0h] [rbp+F0h]
  char v70[24]; // [rsp+200h] [rbp+100h] BYREF

  v46 = a1;
  v44 = a3;
  Handle = 0;
  v48 = 0;
  strcpy(v70, "I_SetResponseLocking");
  v67[0] = v70;
  v67[1] = &v48;
  v67[2] = &Handle;
  lambda_042e0e6ab9f569e61690dbe75fd8663e_::operator()(v67);
  v48 = 1;
  v54 = v67;
  if ( !v46 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a6 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( a2 != 3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( (unsigned __int8)(v44 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( (unsigned __int8)((a4 & 0xF) - 2) > 3u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( *(_QWORD *)a5 == *(_QWORD *)(a5 + 8) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  v59 = &v46;
  v60 = 258;
  if ( a2 == *((_DWORD *)v46 + 17) && v44 == *((_BYTE *)v46 + 72) )
  {
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v66);
    v10 = (RTL_SRWLOCK *)(*(_QWORD *)v46 + 56LL);
    AcquireSRWLockExclusive(v10);
    v62 = v10;
    memset_0(v68, 0, 0x54u);
    I_KeyMapGetRecord(*(const struct VCARD_DATA **)v46, v44, (struct KEY_MAP_RECORD *)v68);
    if ( !I_KeyMapIsActive((const struct KEY_MAP_RECORD *)v68) )
    {
      WppTraceIndent(v11, 2);
      v12 = -2146435024;
      Handle = -2146435024;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 27;
        v15 = "Key does not exist";
LABEL_25:
        WPP_SF_sDs(
          v13[2],
          v14,
          (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
          (_DWORD)WPP_pszIndent,
          v12,
          (__int64)v15);
        v12 = Handle;
        goto LABEL_26;
      }
      goto LABEL_26;
    }
    if ( v69 != 3 )
    {
      WppTraceIndent(v11, 2);
      v12 = -2146435068;
      Handle = -2146435068;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 28;
        v15 = "Key requested cannot be used for authentication";
        goto LABEL_25;
      }
LABEL_26:
      if ( v10 )
        ReleaseSRWLockExclusive(v10);
      goto LABEL_119;
    }
    v45 = 0;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v52);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v55);
    v64[0] = &v46;
    v64[1] = &v44;
    v64[2] = &v45;
    v64[3] = &v52;
    v64[4] = v55;
    Handle = lambda_6fa97c5487e65a36447b328a389b0745_::operator()(v64);
    if ( Handle )
    {
      WppTraceIndent(v16, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle,
          (__int64)"Getting symmetric auth key blob failed");
      }
      goto LABEL_33;
    }
    if ( v45 != a4 )
    {
      WppTraceIndent(v16, 2);
      v12 = -2146435068;
      Handle = -2146435068;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v18 = 31;
      v19 = "Algorithm requested for authentication is not supported by the key";
      goto LABEL_40;
    }
    if ( *(_QWORD *)(a5 + 8) - *(_QWORD *)a5 < (unsigned __int64)(v53 - v52) )
    {
      WppTraceIndent(v53 - v52, 2);
      v12 = -2146434965;
      Handle = -2146434965;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_34;
      }
      v18 = 32;
      v19 = "Response is too short";
LABEL_40:
      WPP_SF_sDs(
        v17[2],
        v18,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        v12,
        (__int64)v19);
LABEL_33:
      v12 = Handle;
LABEL_34:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v55);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v52);
      goto LABEL_26;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v61);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
      v61,
      *(char **)a5,
      v53 - v52);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v58);
    hKey = 0;
    Handle = I_KeyMapGetHandle(v46, v44, &hKey);
    if ( Handle )
    {
      WppTraceIndent(v20, 2);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_52;
      }
      v22 = 33;
      v23 = "Unable to load protection key";
LABEL_51:
      WPP_SF_sDs(
        v21[2],
        v22,
        (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
        (_DWORD)WPP_pszIndent,
        Handle,
        (__int64)v23);
LABEL_52:
      v12 = Handle;
LABEL_53:
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v58);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v61);
      goto LABEL_34;
    }
    Handle = I_AuthenticateKspKey(hKey);
    if ( Handle )
    {
      WppTraceIndent(v24, 2);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_52;
      }
      v22 = 34;
      v23 = "Unable to authenticate the protection key";
      goto LABEL_51;
    }
    p_hKey = (char *)&hKey;
    LOWORD(v50) = 258;
    Handle = I_KeyMapUnpackSymAuthKeyBlob(hKey);
    if ( Handle )
    {
      WppTraceIndent(v25, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle,
          (__int64)"Unable to unpack sym auth key blob");
      }
      v12 = Handle;
      wil::details::ScopeExitFnGuard__lambda_8562040d0fb1123f4cc46b9c1bc3a741___::operator()(&p_hKey);
      goto LABEL_53;
    }
    wil::details::ScopeExitFnGuard__lambda_8562040d0fb1123f4cc46b9c1bc3a741___::operator()(&p_hKey);
    v28 = *((_QWORD *)v46 + 19);
    if ( v28 != *((_QWORD *)v46 + 20) )
      *((_QWORD *)v46 + 20) = v28;
    v29 = *((_QWORD *)v46 + 16);
    if ( v29 != *((_QWORD *)v46 + 17) )
      *((_QWORD *)v46 + 17) = v29;
    if ( v58[0] != v58[1] )
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v64);
      Handle = I_ProtectMemory(v58, v64);
      if ( Handle )
      {
        WppTraceIndent(v30, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
            (_DWORD)WPP_pszIndent,
            Handle,
            (__int64)"Unable to cache auth key");
        }
        v12 = Handle;
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v64);
        goto LABEL_53;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=((_QWORD *)v46 + 19, (__int64)v64);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v64);
    }
    *((_DWORD *)v46 + 16) = a2;
    LOBYTE(v27) = a4;
    LOBYTE(v26) = v44;
    Handle = I_UpdateSymAuthKey((_DWORD)v46, v26, v27, (unsigned int)v66, (__int64)v61);
    if ( Handle )
    {
      WppTraceIndent(v31, 2);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_52;
      }
      v22 = 37;
      v23 = "Unable to update challenge";
      goto LABEL_51;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v58);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v61);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v55);
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v52);
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    hObject = 0;
    LOBYTE(v32) = a4;
    Handle = I_LoadSymKeyFromBuffer(*(_QWORD *)v46, v32, v66, &hObject);
    if ( Handle )
    {
      WppTraceIndent(v33, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sDs(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle,
          (__int64)"Unable to load admin key");
      }
      v12 = Handle;
      goto LABEL_118;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v56);
    v34 = v46;
    if ( *((_QWORD *)v46 + 10) == *((_QWORD *)v46 + 11) )
    {
      if ( *a6 != a6[1] )
        a6[1] = *a6;
    }
    else
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&p_hKey);
      Handle = I_DecryptSym(hObject);
      if ( Handle )
      {
        WppTraceIndent(v35, 2);
        v12 = -2146434965;
        Handle = -2146434965;
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_116;
        }
        v37 = 39;
        v38 = "Cannot decrypt response";
        goto LABEL_96;
      }
      v39 = *((_QWORD *)v46 + 11) + *((_QWORD *)v46 + 14) - *((_QWORD *)v46 + 13) - *((_QWORD *)v46 + 10);
      if ( v50 - (__int64)p_hKey <= v39 )
      {
        WppTraceIndent(v39, 2);
        v12 = -2146434965;
        Handle = -2146434965;
        v36 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_116;
        }
        v37 = 40;
        v38 = "Response is not complete";
LABEL_96:
        WPP_SF_sDs(
          v36[2],
          v37,
          (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
          (_DWORD)WPP_pszIndent,
          107,
          (__int64)v38);
        v12 = Handle;
LABEL_116:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&p_hKey);
LABEL_117:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v56);
LABEL_118:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hObject);
LABEL_119:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v66);
        goto LABEL_127;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v63);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
        v63,
        p_hKey,
        *((_QWORD *)v46 + 14) - *((_QWORD *)v46 + 13));
      v40 = v63[0];
      if ( v63[1] - v63[0] != *((_QWORD *)v46 + 14) - *((_QWORD *)v46 + 13)
        || !(unsigned __int8)std::equal<unsigned char const *,unsigned char const *,std::equal_to<void>>() )
      {
        WppTraceIndent(v40, 2);
        v12 = -2146434965;
        Handle = -2146434965;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
            (_DWORD)WPP_pszIndent,
            107,
            (__int64)"R2 in response does not match");
          v12 = Handle;
        }
        goto LABEL_115;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v65);
      Handle = I_GenerateRandomData(
                 *(_QWORD *)v46,
                 (unsigned int)(v50
                              + *((_DWORD *)v46 + 20)
                              + *((_DWORD *)v46 + 26)
                              - *((_DWORD *)v46 + 28)
                              - *((_DWORD *)v46 + 22)
                              - (_DWORD)p_hKey),
                 v65);
      if ( Handle )
      {
        WppTraceIndent(v41, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sDs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
            (_DWORD)WPP_pszIndent,
            Handle,
            (__int64)"Unable to generate Z2");
        }
        v12 = Handle;
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v65);
LABEL_115:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v63);
        goto LABEL_116;
      }
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(&v56, (__int64)v46 + 80);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::insert<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,0>(
        &v56,
        &v62,
        v57,
        *((_QWORD *)v46 + 13),
        *((_QWORD *)v46 + 14));
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::insert<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<unsigned char>>>,0>(
        &v56,
        &v62,
        v57,
        v65[0],
        v65[1]);
      Handle = I_EncryptSym(hObject);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v65);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v63);
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&p_hKey);
      v34 = v46;
    }
    I_InvalidateChallenge(v34, a2);
    HIBYTE(v60) = 0;
    v12 = Handle;
    goto LABEL_117;
  }
  WppTraceIndent(v9, 2);
  v12 = -2146434965;
  Handle = -2146434965;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids,
      (_DWORD)WPP_pszIndent,
      107,
      (__int64)"Response does not match challenge parameter");
    v12 = Handle;
  }
LABEL_127:
  wil::details::ScopeExitFnGuard__lambda_e4819bc7d4d7c528f40e1c7e2380f75e___::operator()(&v59);
  WppTraceUnwinder__lambda_042e0e6ab9f569e61690dbe75fd8663e____::_WppTraceUnwinder__lambda_042e0e6ab9f569e61690dbe75fd8663e____(&v54);
  return v12;
}

```

## disassembly

```asm
0x18000acb4  push    rbp
0x18000acb6  push    rbx
0x18000acb7  push    rsi
0x18000acb8  push    rdi
0x18000acb9  push    r12
0x18000acbb  push    r14
0x18000acbd  push    r15
0x18000acbf  lea     rbp, [rsp-120h]
0x18000acc7  sub     rsp, 220h
0x18000acce  mov     rax, cs:__security_cookie
0x18000acd5  xor     rax, rsp
0x18000acd8  mov     [rbp+150h+var_38], rax
0x18000acdf  mov     r14b, r9b
0x18000ace2  mov     r15d, edx
0x18000ace5  mov     rbx, [rbp+150h+arg_20]
0x18000acec  mov     [rsp+250h+var_208], rcx
0x18000acf1  mov     [rsp+250h+var_218], r8b
0x18000acf6  mov     rsi, [rbp+150h+arg_28]
0x18000acfd  mov     [rsp+250h+var_220], 0
0x18000ad05  mov     [rsp+250h+var_1F8], 0
0x18000ad0d  movups  xmm0, xmmword ptr cs:aISetresponselo; "I_SetResponseLocking"
0x18000ad14  movups  xmmword ptr [rbp+150h+var_50], xmm0
0x18000ad1b  movsd   xmm1, qword ptr cs:aISetresponselo+0Dh; "Locking"
0x18000ad23  movsd   qword ptr [rbp+150h+var_50+0Dh], xmm1
0x18000ad2b  lea     rax, [rbp+150h+var_50]
0x18000ad32  mov     [rbp+150h+var_C8], rax
0x18000ad39  lea     rax, [rsp+250h+var_1F8]
0x18000ad3e  mov     [rbp+150h+var_C0], rax
0x18000ad45  lea     rax, [rsp+250h+var_220]
0x18000ad4a  mov     [rbp+150h+var_B8], rax
0x18000ad51  lea     rcx, [rbp+150h+var_C8]
0x18000ad58  call    _lambda_042e0e6ab9f569e61690dbe75fd8663e___operator__
0x18000ad5d  mov     [rsp+250h+var_1F8], 1
0x18000ad65  lea     rax, [rbp+150h+var_C8]
0x18000ad6c  mov     [rbp+150h+var_1B8], rax
0x18000ad70  cmp     [rsp+250h+var_208], 0
0x18000ad76  jnz     short loc_18000AD7D
0x18000ad78  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ad7d  test    rsi, rsi
0x18000ad80  jnz     short loc_18000AD87
0x18000ad82  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ad87  cmp     r15d, 3
0x18000ad8b  jz      short loc_18000AD92
0x18000ad8d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ad92  mov     al, [rsp+250h+var_218]
0x18000ad96  sub     al, 80h
0x18000ad98  cmp     al, 20h ; ' '
0x18000ad9a  jbe     short loc_18000ADA1
0x18000ad9c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ada1  mov     al, r14b
0x18000ada4  and     al, 0Fh
0x18000ada6  mov     r12d, 2
0x18000adac  sub     al, r12b
0x18000adaf  cmp     al, 3
0x18000adb1  jbe     short loc_18000ADB8
0x18000adb3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000adb8  mov     rax, [rbx+8]
0x18000adbc  cmp     [rbx], rax
0x18000adbf  jnz     short loc_18000ADC6
0x18000adc1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000adc6  lea     rax, [rsp+250h+var_208]
0x18000adcb  mov     [rbp+150h+var_168], rax
0x18000adcf  mov     [rbp+150h+var_160], 102h
0x18000add5  mov     rax, [rsp+250h+var_208]
0x18000adda  cmp     r15d, [rax+44h]
0x18000adde  jnz     loc_18000B7BF
0x18000ade4  mov     al, [rax+48h]
0x18000ade7  cmp     [rsp+250h+var_218], al
0x18000adeb  jnz     loc_18000B7BF
0x18000adf1  lea     rcx, [rbp+150h+var_E0]
0x18000adf5  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18000adfa  nop
0x18000adfb  mov     rax, [rsp+250h+var_208]
0x18000ae00  mov     rdi, [rax]
0x18000ae03  add     rdi, 38h ; '8'
0x18000ae07  mov     rcx, rdi; SRWLock
0x18000ae0a  call    cs:__imp_AcquireSRWLockExclusive
0x18000ae10  mov     [rbp+150h+var_140], rdi
0x18000ae14  xor     edx, edx; Val
0x18000ae16  lea     r8d, [rdx+54h]; Size
0x18000ae1a  lea     rcx, [rbp+150h+var_B0]; void *
0x18000ae21  call    memset_0
0x18000ae26  lea     r8, [rbp+150h+var_B0]; struct KEY_MAP_RECORD *
0x18000ae2d  mov     dl, [rsp+250h+var_218]; unsigned __int8
0x18000ae31  mov     rcx, [rsp+250h+var_208]
0x18000ae36  mov     rcx, [rcx]; struct VCARD_DATA *
0x18000ae39  call    ?I_KeyMapGetRecord@@YAXPEBUVCARD_DATA@@EPEAUKEY_MAP_RECORD@@@Z; I_KeyMapGetRecord(VCARD_DATA const *,uchar,KEY_MAP_RECORD *)
0x18000ae3e  lea     rcx, [rbp+150h+var_B0]; struct KEY_MAP_RECORD *
0x18000ae45  call    ?I_KeyMapIsActive@@YAHPEBUKEY_MAP_RECORD@@@Z; I_KeyMapIsActive(KEY_MAP_RECORD const *)
0x18000ae4a  test    eax, eax
0x18000ae4c  jnz     short loc_18000AE90
0x18000ae4e  mov     edx, r12d
0x18000ae51  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000ae56  mov     ebx, 80100030h
0x18000ae5b  mov     [rsp+250h+var_220], ebx
0x18000ae5f  lea     rax, WPP_GLOBAL_Control
0x18000ae66  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae6d  cmp     rcx, rax
0x18000ae70  jz      loc_18000AEF9
0x18000ae76  test    byte ptr [rcx+1Ch], 1
0x18000ae7a  jz      short loc_18000AEF9
0x18000ae7c  cmp     [rcx+19h], r12b
0x18000ae80  jb      short loc_18000AEF9
0x18000ae82  mov     edx, 1Bh
0x18000ae87  lea     rax, aKeyDoesNotExis; "Key does not exist"
0x18000ae8e  jmp     short loc_18000AED5
0x18000ae90  cmp     [rbp+150h+var_60], 3
0x18000ae97  jz      short loc_18000AF10
0x18000ae99  mov     edx, r12d
0x18000ae9c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000aea1  mov     ebx, 80100004h
0x18000aea6  mov     [rsp+250h+var_220], ebx
0x18000aeaa  lea     rax, WPP_GLOBAL_Control
0x18000aeb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeb8  cmp     rcx, rax
0x18000aebb  jz      short loc_18000AEF9
0x18000aebd  test    byte ptr [rcx+1Ch], 1
0x18000aec1  jz      short loc_18000AEF9
0x18000aec3  cmp     [rcx+19h], r12b
0x18000aec7  jb      short loc_18000AEF9
0x18000aec9  mov     edx, 1Ch
0x18000aece  lea     rax, aKeyRequestedCa; "Key requested cannot be used for authen"...
0x18000aed5  mov     [rsp+250h+var_228], rax
0x18000aeda  mov     dword ptr [rsp+250h+var_230], ebx
0x18000aede  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000aee5  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000aeec  mov     rcx, [rcx+10h]
0x18000aef0  call    WPP_SF_sDs
0x18000aef5  mov     ebx, [rsp+250h+var_220]
0x18000aef9  test    rdi, rdi
0x18000aefc  jz      loc_18000B795
0x18000af02  mov     rcx, rdi; SRWLock
0x18000af05  call    cs:__imp_ReleaseSRWLockExclusive
0x18000af0b  jmp     loc_18000B795
0x18000af10  mov     [rsp+250h+var_210], 0
0x18000af15  lea     rcx, [rbp+150h+var_1D0]
0x18000af19  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18000af1e  nop
0x18000af1f  lea     rcx, [rbp+150h+var_1B0]
0x18000af23  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18000af28  nop
0x18000af29  lea     rax, [rsp+250h+var_208]
0x18000af2e  mov     [rbp+150h+var_120], rax
0x18000af32  lea     rax, [rsp+250h+var_218]
0x18000af37  mov     [rbp+150h+var_118], rax
0x18000af3b  lea     rax, [rsp+250h+var_210]
0x18000af40  mov     [rbp+150h+var_110], rax
0x18000af44  lea     rax, [rbp+150h+var_1D0]
0x18000af48  mov     [rbp+150h+var_108], rax
0x18000af4c  lea     rax, [rbp+150h+var_1B0]
0x18000af50  mov     [rbp+150h+var_100], rax
0x18000af54  lea     rcx, [rbp+150h+var_120]
0x18000af58  call    _lambda_6fa97c5487e65a36447b328a389b0745___operator__
0x18000af5d  mov     [rsp+250h+var_220], eax
0x18000af61  test    eax, eax
0x18000af63  jz      short loc_18000AFD8
0x18000af65  mov     edx, r12d
0x18000af68  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000af6d  lea     rax, WPP_GLOBAL_Control
0x18000af74  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af7b  cmp     rcx, rax
0x18000af7e  jz      short loc_18000AFBC
0x18000af80  test    byte ptr [rcx+1Ch], 1
0x18000af84  jz      short loc_18000AFBC
0x18000af86  cmp     [rcx+19h], r12b
0x18000af8a  jb      short loc_18000AFBC
0x18000af8c  mov     edx, 1Eh
0x18000af91  lea     rax, aGettingSymmetr_0; "Getting symmetric auth key blob failed"
0x18000af98  mov     [rsp+250h+var_228], rax
0x18000af9d  mov     eax, [rsp+250h+var_220]
0x18000afa1  mov     dword ptr [rsp+250h+var_230], eax
0x18000afa5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000afac  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000afb3  mov     rcx, [rcx+10h]
0x18000afb7  call    WPP_SF_sDs
0x18000afbc  mov     ebx, [rsp+250h+var_220]
0x18000afc0  lea     rcx, [rbp+150h+var_1B0]
0x18000afc4  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18000afc9  nop
0x18000afca  lea     rcx, [rbp+150h+var_1D0]
0x18000afce  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18000afd3  jmp     loc_18000AEF9
0x18000afd8  cmp     [rsp+250h+var_210], r14b
0x18000afdd  jz      short loc_18000B029
0x18000afdf  mov     edx, r12d
0x18000afe2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000afe7  mov     ebx, 80100004h
0x18000afec  mov     [rsp+250h+var_220], ebx
0x18000aff0  lea     rax, WPP_GLOBAL_Control
0x18000aff7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000affe  cmp     rcx, rax
0x18000b001  jz      short loc_18000AFC0
0x18000b003  test    byte ptr [rcx+1Ch], 1
0x18000b007  jz      short loc_18000AFC0
0x18000b009  cmp     [rcx+19h], r12b
0x18000b00d  jb      short loc_18000AFC0
0x18000b00f  mov     edx, 1Fh
0x18000b014  lea     rax, aAlgorithmReque_0; "Algorithm requested for authentication "...
0x18000b01b  mov     [rsp+250h+var_228], rax
0x18000b020  mov     dword ptr [rsp+250h+var_230], ebx
0x18000b024  jmp     loc_18000AFA5
0x18000b029  mov     rcx, [rbp+150h+var_1C8]
0x18000b02d  sub     rcx, [rbp+150h+var_1D0]
0x18000b031  mov     rax, [rbx+8]
0x18000b035  sub     rax, [rbx]
0x18000b038  cmp     rax, rcx
0x18000b03b  jnb     short loc_18000B087
0x18000b03d  mov     edx, r12d
0x18000b040  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b045  mov     ebx, 8010006Bh
0x18000b04a  mov     [rsp+250h+var_220], ebx
0x18000b04e  lea     rax, WPP_GLOBAL_Control
0x18000b055  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b05c  cmp     rcx, rax
0x18000b05f  jz      loc_18000AFC0
0x18000b065  test    byte ptr [rcx+1Ch], 1
0x18000b069  jz      loc_18000AFC0
0x18000b06f  cmp     [rcx+19h], r12b
0x18000b073  jb      loc_18000AFC0
0x18000b079  mov     edx, 20h ; ' '
0x18000b07e  lea     rax, aResponseIsTooS; "Response is too short"
0x18000b085  jmp     short loc_18000B01B
0x18000b087  lea     rcx, [rbp+150h+var_158]
0x18000b08b  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18000b090  nop
0x18000b091  mov     r8, [rbp+150h+var_1C8]
0x18000b095  sub     r8, [rbp+150h+var_1D0]
0x18000b099  mov     rdx, [rbx]
0x18000b09c  lea     rcx, [rbp+150h+var_158]
0x18000b0a0  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x18000b0a5  lea     rcx, [rbp+150h+var_180]
0x18000b0a9  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18000b0ae  nop
0x18000b0af  mov     [rsp+250h+hKey], 0
0x18000b0b8  lea     r8, [rsp+250h+hKey]; unsigned __int64 *
0x18000b0bd  mov     dl, [rsp+250h+var_218]; unsigned __int8
0x18000b0c1  mov     rcx, [rsp+250h+var_208]; struct VCHANNEL_DATA *
0x18000b0c6  call    ?I_KeyMapGetHandle@@YAKPEAUVCHANNEL_DATA@@EPEA_K@Z; I_KeyMapGetHandle(VCHANNEL_DATA *,uchar,unsigned __int64 *)
0x18000b0cb  mov     [rsp+250h+var_220], eax
0x18000b0cf  test    eax, eax
0x18000b0d1  jz      short loc_18000B146
0x18000b0d3  mov     edx, r12d
0x18000b0d6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b0db  lea     rax, WPP_GLOBAL_Control
0x18000b0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0e9  cmp     rcx, rax
0x18000b0ec  jz      short loc_18000B12A
0x18000b0ee  test    byte ptr [rcx+1Ch], 1
0x18000b0f2  jz      short loc_18000B12A
0x18000b0f4  cmp     [rcx+19h], r12b
0x18000b0f8  jb      short loc_18000B12A
0x18000b0fa  mov     edx, 21h ; '!'
0x18000b0ff  lea     rax, aUnableToLoadPr; "Unable to load protection key"
0x18000b106  mov     [rsp+250h+var_228], rax
0x18000b10b  mov     eax, [rsp+250h+var_220]
0x18000b10f  mov     dword ptr [rsp+250h+var_230], eax
0x18000b113  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000b11a  lea     r8, WPP_d28439aa9f743fcde759327bfe03a8da_Traceguids
0x18000b121  mov     rcx, [rcx+10h]
0x18000b125  call    WPP_SF_sDs
0x18000b12a  mov     ebx, [rsp+250h+var_220]
0x18000b12e  lea     rcx, [rbp+150h+var_180]
0x18000b132  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18000b137  nop
0x18000b138  lea     rcx, [rbp+150h+var_158]
0x18000b13c  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18000b141  jmp     loc_18000AFC0
0x18000b146  lea     rdx, [rbp+150h+var_158]
0x18000b14a  mov     rcx, [rsp+250h+hKey]; hObject
0x18000b14f  call    ?I_AuthenticateKspKey@@YAK_KAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_AuthenticateKspKey(unsigned __int64,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18000b154  mov     [rsp+250h+var_220], eax
0x18000b158  test    eax, eax
0x18000b15a  jz      short loc_18000B194
0x18000b15c  mov     edx, r12d
0x18000b15f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b164  lea     rax, WPP_GLOBAL_Control
0x18000b16b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b172  cmp     rcx, rax
0x18000b175  jz      short loc_18000B12A
0x18000b177  test    byte ptr [rcx+1Ch], 1
0x18000b17b  jz      short loc_18000B12A
0x18000b17d  cmp     [rcx+19h], r12b
0x18000b181  jb      short loc_18000B12A
0x18000b183  mov     edx, 22h ; '"'
0x18000b188  lea     rax, aUnableToAuthen_0; "Unable to authenticate the protection k"...
0x18000b18f  jmp     loc_18000B106
0x18000b194  lea     rax, [rsp+250h+hKey]
0x18000b199  mov     [rsp+250h+var_1F0], rax
0x18000b19e  mov     word ptr [rsp+250h+var_1E8], 102h
0x18000b1a5  lea     r9, [rbp+150h+var_180]
0x18000b1a9  lea     r8, [rbp+150h+var_E0]
0x18000b1ad  lea     rdx, [rbp+150h+var_1B0]
0x18000b1b1  mov     rcx, [rsp+250h+hKey]; hKey
0x18000b1b6  call    ?I_KeyMapUnpackSymAuthKeyBlob@@YAK_KAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@2@Z; I_KeyMapUnpackSymAuthKeyBlob(unsigned __int64,std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x18000b1bb  mov     [rsp+250h+var_220], eax
0x18000b1bf  test    eax, eax
0x18000b1c1  jz      short loc_18000B22D
0x18000b1c3  mov     edx, r12d
0x18000b1c6  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000b1cb  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
