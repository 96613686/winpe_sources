# SecurityManager::Initialize(int)

- ea: `0x1400ce6d0`
- end: `0x1400cf1d5`
- name: `?Initialize@SecurityManager@@UEAAJH@Z`
- size: `2821`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x14002db90`
- `0x1400364a0`
- `0x14003c680`
- `0x14003d828`
- `0x14004b838`
- `0x140053de8`
- `0x140053f10`
- `0x1400545bc`
- `0x140064f4c`
- `0x140069004`
- `0x1400691b4`
- `0x14006d540`
- `0x1400927e8`
- `0x1400ce6d0`
- `0x1400cf1dc`
- `0x14011b920`
- `0x14011ea40`
- `0x14027a8bc`
- `0x1402a0624`
- `0x1402a07a4`
- `0x1402cb010`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1400cedbc`
- `ntdll!RtlCompareMemory` at `0x1400cedbc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400ce74b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400ce74b`

## string_xrefs

- `0x1400ce971`: `/configuration/security/settings/vbs_opt_out`
- `0x1400cea38`: `/configuration/security/settings/ksd_enabled`
- `0x1400cef79`: `/configuration/security/policy/encrypted_policy`
- `0x1400cf0bb`: `/configuration/security/keys/key_protector`
- `0x1400cf122`: `/configuration/security/keys/key_protector`
- `0x1400cee2c`: `/configuration/security/policy/security_policy`
- `0x1400cee89`: `/configuration/security/policy/security_policy`
- `0x1400ceb90`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x1400cebf8`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x1400ceaca`: `/configuration/security/settings/shielding_requested`
- `0x1400cec66`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x1400ced5a`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x1400cea84`: `/configuration/security/settings/data_protection_requested`
- `0x1400cea8b`: `/configuration/security/settings/encrypt_state_migration`
- `0x1400cea09`: `/configuration/security/settings/tpm_enabled`
- `0x1400ce725`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ce791`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ce7dc`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ce836`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ce8af`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ce93a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ceb53`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400cec19`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ced1a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ced7b`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400ceeaa`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400cf143`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
int __fastcall SecurityManager::Initialize(SecurityManager *this, int a2, __int64 a3, const char *a4)
{
  NTSTATUS v6; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rax
  _DWORD *v14; // r14
  int v15; // eax
  int v16; // ebx
  int v17; // eax
  int v18; // ebx
  _DWORD *v19; // rbx
  int v20; // eax
  int v21; // eax
  bool v22; // cf
  _DWORD *v23; // rsi
  int v24; // eax
  _DWORD *v25; // rbx
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  int v28; // eax
  _DWORD *v29; // rbx
  int v30; // eax
  int v31; // ebx
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  int v35; // ebx
  int v36; // eax
  int v37; // eax
  int v38; // ebx
  int v39; // eax
  int v40; // ebx
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  int v44; // ebx
  _QWORD *v45; // rax
  _QWORD *v46; // rdi
  int v47; // eax
  _QWORD *v48; // rax
  _QWORD *v49; // rdi
  _QWORD *v50; // rax
  _QWORD *v51; // rax
  int v52; // eax
  __int64 v53; // rax
  int v54; // eax
  int v55; // ebx
  int v56; // [rsp+20h] [rbp-F8h]
  char *v57[2]; // [rsp+30h] [rbp-E8h] BYREF
  char *v58[2]; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v59; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v60; // [rsp+58h] [rbp-C0h] BYREF
  _BYTE v61[32]; // [rsp+60h] [rbp-B8h] BYREF
  unsigned int v62; // [rsp+80h] [rbp-98h] BYREF
  int v63; // [rsp+84h] [rbp-94h] BYREF
  __int128 v64; // [rsp+88h] [rbp-90h] BYREF
  _BYTE Source2[32]; // [rsp+98h] [rbp-80h] BYREF
  unsigned __int8 Source1[32]; // [rsp+B8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  memset(Source1, 0, sizeof(Source1));
  memset(Source2, 0, sizeof(Source2));
  if ( !*((_QWORD *)this + 2) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      a4);
  v6 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 46, L"SHA256", 0, 0);
  if ( v6 < 0 )
    return v6 | 0x10000000;
  *(_OWORD *)v57 = 0;
  VmRepositoryAutoLock::VmRepositoryAutoLock(v57, *((_QWORD *)this + 1), 0);
  v8 = (int)v57[1];
  if ( SLODWORD(v57[1]) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)LODWORD(v57[1]),
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v8;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 296LL))(
         *((_QWORD *)this + 1),
         (char *)this + 32);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v9,
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v10;
  }
  v64 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 1) + 304LL))(*((_QWORD *)this + 1), &v64);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v11,
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v12;
  }
  v13 = Vml::GuidToString(v61, &v64);
  std::wstring::operator=((char *)this + 64, v13);
  std::wstring::_Tidy_deallocate(v61);
  v14 = (_DWORD *)((char *)this + 376);
  v15 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 288LL))(
          *((_QWORD *)this + 1),
          (char *)this + 376);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v15,
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v16;
  }
  if ( *v14 > 0x800u )
  {
    if ( *v14 == 65024 || *v14 == 65280 )
      *((_DWORD *)this + 6) = 65280;
    else
      *((_DWORD *)this + 6) = 257;
  }
  else
  {
    *((_DWORD *)this + 6) = 256;
  }
  v63 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 320LL))(*((_QWORD *)this + 1), &v63);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D1,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)(unsigned int)v17,
      v56);
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return v18;
  }
  *((_DWORD *)this + 28) = a2;
  v19 = (_DWORD *)((char *)this + 128);
  v20 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          L"/configuration/security/settings/vbs_opt_out",
          (char *)this + 128);
  if ( !(unsigned int)RepositoryKeyFound(v20) )
    *v19 = 0;
  if ( *v19 )
    goto LABEL_36;
  v21 = *((_DWORD *)this + 34);
  switch ( v21 )
  {
    case 0:
      goto LABEL_36;
    case 2:
      if ( !*((_DWORD *)this + 28) )
        goto LABEL_34;
      v22 = *v14 < 0xB01u;
      break;
    case 3:
      if ( !*((_DWORD *)this + 28) )
        goto LABEL_34;
      v22 = *v14 < 0xC02u;
      break;
    case 1:
      goto LABEL_36;
    default:
      goto LABEL_34;
  }
  if ( v22 )
  {
LABEL_34:
    *v19 = 1;
    if ( (unsigned int)VmlIsDebugTraceEnabled(49184) )
      VmlDebugTrace(
        49184,
        L"VM isolation type %x does not support VTL1 - implicitly disabled",
        *((unsigned int *)this + 34));
  }
LABEL_36:
  v23 = (_DWORD *)((char *)this + 120);
  v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          L"/configuration/security/settings/tpm_enabled",
          (char *)this + 120);
  if ( !(unsigned int)RepositoryKeyFound(v24) )
    *v23 = 0;
  v25 = (_DWORD *)((char *)this + 124);
  v26 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          L"/configuration/security/settings/ksd_enabled",
          (char *)this + 124);
  if ( !(unsigned int)RepositoryKeyFound(v26) )
    *v25 = 0;
  if ( !*v23 && !*v25 || *((_DWORD *)this + 34) )
    goto LABEL_111;
  v27 = L"/configuration/security/settings/encrypt_state_migration";
  if ( *v14 < 0x701u )
    v27 = L"/configuration/security/settings/data_protection_requested";
  v28 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          v27,
          (char *)this + 116);
  if ( !(unsigned int)RepositoryKeyFound(v28) )
    *((_DWORD *)this + 29) = 0;
  v29 = (_DWORD *)((char *)this + 108);
  v30 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *))(**((_QWORD **)this + 1) + 128LL))(
          *((_QWORD *)this + 1),
          L"/configuration/security/settings/shielding_requested",
          (char *)this + 108);
  if ( !(unsigned int)RepositoryKeyFound(v30) )
    *v29 = 0;
  if ( *v23 )
  {
    v62 = 0;
    if ( v63 != 1 )
    {
LABEL_51:
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
      return -2147024846;
    }
    if ( *v29 )
      *((_DWORD *)this + 29) = 1;
    *(_OWORD *)v58 = 0;
    VmRepositoryAutoLock::VmRepositoryAutoLock(v58, *((_QWORD *)this + 2), 0);
    v31 = (int)v58[1];
    if ( SLODWORD(v58[1]) < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)LODWORD(v58[1]),
        v56);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
      return v31;
    }
    v32 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/vtpm/vtpm_engine_nvram",
            &v62);
    if ( (unsigned int)RepositoryKeyFound(v32) )
    {
      if ( v62 )
      {
        v33 = std::vector<enum gsl::byte>::vector<enum gsl::byte>(v61, v62);
        std::vector<unsigned char>::operator=((char *)this + 296, v33);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v61);
        v34 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 2)
                                                                                          + 88LL))(
                *((_QWORD *)this + 2),
                L"/configuration/security/vtpm/vtpm_engine_nvram",
                *((_QWORD *)this + 37),
                v62);
        v35 = v34;
        if ( v34 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x24D,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v34,
            v56);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
          return v35;
        }
      }
    }
    if ( *((_DWORD *)this + 94) >= 0x802u )
    {
      v36 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
              *((_QWORD *)this + 2),
              L"/configuration/security/vtpm/vtpm_engine_nvram_hash",
              &v62);
      if ( (unsigned int)RepositoryKeyFound(v36) )
      {
        if ( v62 )
        {
          if ( v62 != 32 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Engine NV state hash size not expected (0x%x).", v62);
LABEL_66:
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
            return -2147024883;
          }
          v37 = SecurityManager::Sha256HashData(
                  (SecurityManager *)((char *)this - 24),
                  *((unsigned __int8 **)this + 37),
                  *((_DWORD *)this + 76) - *((_DWORD *)this + 74),
                  Source1);
          v38 = v37;
          if ( v37 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x262,
              (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
              (const char *)(unsigned int)v37,
              v56);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
            return v38;
          }
          v39 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _BYTE *, __int64))(**((_QWORD **)this + 2)
                                                                                              + 88LL))(
                  *((_QWORD *)this + 2),
                  L"/configuration/security/vtpm/vtpm_engine_nvram_hash",
                  Source2,
                  32);
          v40 = v39;
          if ( v39 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x265,
              (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
              (const char *)(unsigned int)v39,
              v56);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
            VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
            return v40;
          }
          if ( RtlCompareMemory(Source1, Source2, 0x20u) != 32 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16739) )
              VmlDebugTrace(16739, L"Engine NV state corrupted.");
            goto LABEL_66;
          }
        }
      }
    }
    if ( !*((_DWORD *)this + 28) )
    {
      v62 = 0;
      v41 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
              *((_QWORD *)this + 2),
              L"/configuration/security/policy/security_policy",
              &v62);
      if ( (unsigned int)RepositoryKeyFound(v41) )
      {
        v42 = std::vector<enum gsl::byte>::vector<enum gsl::byte>(v61, v62);
        std::vector<unsigned char>::operator=((char *)this + 248, v42);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v61);
        v43 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 2)
                                                                                          + 88LL))(
                *((_QWORD *)this + 2),
                L"/configuration/security/policy/security_policy",
                *((_QWORD *)this + 31),
                (unsigned int)(*((_DWORD *)this + 64) - *((_DWORD *)this + 62)));
        v44 = v43;
        if ( v43 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x284,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v43,
            v56);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
          return v44;
        }
        if ( (unsigned __int8)VmSecurityPolicy::IsPolicySetShielded((char *)this + 248) != (*((_DWORD *)this + 27) != 0) )
        {
          v45 = (_QWORD *)((char *)this + 64);
          if ( *((_QWORD *)this + 11) > 7u )
            v45 = (_QWORD *)*v45;
          v59 = (__int64)v45;
          v46 = (_QWORD *)((char *)this + 32);
          if ( v46[3] > 7u )
            v46 = (_QWORD *)*v46;
          v60 = (__int64)v46;
          VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
            (struct _EVENT_DESCRIPTOR *)&VMWP_SECURITYMGR_SETTINGS_DISALLOWED_BY_POLICY_ERROR,
            5u,
            (__int64)&v60,
            (__int64)&v59);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
          return -2147019873;
        }
      }
      else
      {
        if ( !*((_DWORD *)this + 27) )
        {
          v47 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2)
                                                                                            + 80LL))(
                  *((_QWORD *)this + 2),
                  L"/configuration/security/policy/encrypted_policy",
                  &v62);
          if ( (unsigned int)RepositoryKeyFound(v47) )
          {
            if ( SecurityManager::UsingLocalHostGuardianService((SecurityManager *)((char *)this - 24)) )
            {
              v48 = (_QWORD *)((char *)this + 64);
              if ( *((_QWORD *)this + 11) > 7u )
                v48 = (_QWORD *)*v48;
              v60 = (__int64)v48;
              v49 = (_QWORD *)((char *)this + 32);
              if ( v49[3] > 7u )
                v49 = (_QWORD *)*v49;
              v59 = (__int64)v49;
              VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
                (struct _EVENT_DESCRIPTOR *)&VMWP_SECURITYMGR_LEGACY_POLICY_FOUND_ERROR,
                5u,
                (__int64)&v59,
                (__int64)&v60);
              VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
              VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
              return -2147019873;
            }
          }
        }
        *((_DWORD *)this + 27) = 1;
      }
    }
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
  }
  if ( *((_DWORD *)this + 31) )
  {
    if ( v63 || *((_DWORD *)this + 94) < 0x800u )
      goto LABEL_51;
    v50 = (_QWORD *)((char *)this + 64);
    if ( *((_QWORD *)this + 11) > 7u )
      v50 = (_QWORD *)*v50;
    v60 = (__int64)v50;
    v51 = (_QWORD *)((char *)this + 32);
    if ( *((_QWORD *)this + 7) > 7u )
      v51 = (_QWORD *)*v51;
    v59 = (__int64)v51;
    VmEventWriteAndReport<unsigned short const *,unsigned short const *>(
      (struct _EVENT_DESCRIPTOR *)&VMWP_VM_KSD_DEPRECATED_WARNING,
      1u,
      (__int64)&v59,
      (__int64)&v60);
  }
  if ( *((_DWORD *)this + 28) )
  {
LABEL_111:
    VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
    return 0;
  }
  v62 = 0;
  v52 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
          *((_QWORD *)this + 2),
          L"/configuration/security/keys/key_protector",
          &v62);
  if ( (unsigned int)RepositoryKeyFound(v52) && v62 )
  {
    v53 = std::vector<enum gsl::byte>::vector<enum gsl::byte>(v61, v62);
    std::vector<unsigned char>::operator=((char *)this + 200, v53);
    std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v61);
    v54 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 88LL))(
            *((_QWORD *)this + 2),
            L"/configuration/security/keys/key_protector",
            *((_QWORD *)this + 25),
            (unsigned int)(*((_DWORD *)this + 52) - *((_DWORD *)this + 50)));
    v55 = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CD,
        (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
        (const char *)(unsigned int)v54,
        v56);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
      return v55;
    }
    VmSecurityPolicy::ValidateOctetString((char *)this + 200);
    goto LABEL_111;
  }
  if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
    VmlDebugTrace(16416, L"Empty ingress key protector.");
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v57);
  return -2147024894;
}

```

## disassembly

```asm
0x1400ce6d0  mov     r11, rsp
0x1400ce6d3  push    rbx
0x1400ce6d4  push    rsi
0x1400ce6d5  push    rdi
0x1400ce6d6  push    r12
0x1400ce6d8  push    r14
0x1400ce6da  push    r15
0x1400ce6dc  sub     rsp, 0E8h
0x1400ce6e3  mov     rax, cs:__security_cookie
0x1400ce6ea  xor     rax, rsp
0x1400ce6ed  mov     [rsp+118h+var_40], rax
0x1400ce6f5  mov     esi, edx
0x1400ce6f7  mov     rdi, rcx
0x1400ce6fa  xorps   xmm0, xmm0
0x1400ce6fd  movups  xmmword ptr [r11-60h], xmm0
0x1400ce702  movups  xmmword ptr [r11-50h], xmm0
0x1400ce707  xorps   xmm1, xmm1
0x1400ce70a  movups  xmmword ptr [r11-80h], xmm1
0x1400ce70f  movups  xmmword ptr [r11-70h], xmm1
0x1400ce714  mov     rcx, [rsp+118h]; this
0x1400ce71c  xor     r12d, r12d
0x1400ce71f  cmp     [rdi+10h], r12
0x1400ce723  jnz     short loc_1400CE737
0x1400ce725  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1400ce72c  mov     edx, 1B6h; void *
0x1400ce731  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400ce737  lea     rcx, [rdi+170h]; phAlgorithm
0x1400ce73e  xor     r9d, r9d; dwFlags
0x1400ce741  xor     r8d, r8d; pszImplementation
0x1400ce744  lea     rdx, pszAlgId; "SHA256"
0x1400ce74b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400ce752  nop     dword ptr [rax+rax+00h]
0x1400ce757  test    eax, eax
0x1400ce759  jns     short loc_1400CE764
0x1400ce75b  bts     eax, 1Ch
0x1400ce75f  jmp     loc_1400CF1B3
0x1400ce764  xorps   xmm0, xmm0
0x1400ce767  movups  xmmword ptr [rsp+118h+var_E8], xmm0
0x1400ce76c  xor     r8d, r8d
0x1400ce76f  mov     rdx, [rdi+8]
0x1400ce773  lea     rcx, [rsp+118h+var_E8]
0x1400ce778  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400ce77d  nop
0x1400ce77e  mov     ebx, dword ptr [rsp+118h+var_E8+8]
0x1400ce782  test    ebx, ebx
0x1400ce784  jns     short loc_1400CE7B4
0x1400ce786  mov     rcx, [rsp+118h]; this
0x1400ce78e  mov     r9d, ebx; char *
0x1400ce791  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1400ce798  mov     edx, 1C5h; void *
0x1400ce79d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400ce7a2  nop
0x1400ce7a3  lea     rcx, [rsp+118h+var_E8]; this
0x1400ce7a8  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400ce7ad  mov     eax, ebx
0x1400ce7af  jmp     loc_1400CF1B3
0x1400ce7b4  mov     rcx, [rdi+8]
0x1400ce7b8  mov     rax, [rcx]
0x1400ce7bb  lea     rdx, [rdi+20h]
0x1400ce7bf  mov     rax, [rax+128h]
0x1400ce7c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ce7cb  mov     ebx, eax
0x1400ce7cd  test    eax, eax
0x1400ce7cf  jns     short loc_1400CE7FF
0x1400ce7d1  mov     rcx, [rsp+118h]; this
0x1400ce7d9  mov     r9d, eax; char *
0x1400ce7dc  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1400ce7e3  mov     edx, 1C7h; void *
0x1400ce7e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400ce7ed  nop
0x1400ce7ee  lea     rcx, [rsp+118h+var_E8]; this
0x1400ce7f3  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400ce7f8  mov     eax, ebx
0x1400ce7fa  jmp     loc_1400CF1B3
0x1400ce7ff  xorps   xmm0, xmm0
0x1400ce802  movups  [rsp+118h+var_90], xmm0
0x1400ce80a  mov     rcx, [rdi+8]
0x1400ce80e  mov     rax, [rcx]
0x1400ce811  lea     rdx, [rsp+118h+var_90]
0x1400ce819  mov     rax, [rax+130h]
0x1400ce820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ce825  mov     ebx, eax
0x1400ce827  test    eax, eax
0x1400ce829  jns     short loc_1400CE859
0x1400ce82b  mov     rcx, [rsp+118h]; this
0x1400ce833  mov     r9d, eax; char *
0x1400ce836  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1400ce83d  mov     edx, 1CAh; void *
0x1400ce842  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400ce847  nop
0x1400ce848  lea     rcx, [rsp+118h+var_E8]; this
0x1400ce84d  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400ce852  mov     eax, ebx
0x1400ce854  jmp     loc_1400CF1B3
0x1400ce859  lea     rdx, [rsp+118h+var_90]
0x1400ce861  lea     rcx, [rsp+118h+var_B8]
0x1400ce866  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ce86b  lea     rcx, [rdi+40h]
0x1400ce86f  mov     rdx, rax
0x1400ce872  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400ce877  lea     rcx, [rsp+118h+var_B8]
0x1400ce87c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400ce881  mov     rcx, [rdi+8]
0x1400ce885  lea     r14, [rdi+178h]
0x1400ce88c  mov     rax, [rcx]
0x1400ce88f  mov     rdx, r14
0x1400ce892  mov     rax, [rax+120h]
0x1400ce899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ce89e  mov     ebx, eax
0x1400ce8a0  test    eax, eax
0x1400ce8a2  jns     short loc_1400CE8D2
0x1400ce8a4  mov     rcx, [rsp+118h]; this
0x1400ce8ac  mov     r9d, eax; char *
0x1400ce8af  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1400ce8b6  mov     edx, 1CDh; void *
0x1400ce8bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400ce8c0  nop
0x1400ce8c1  lea     rcx, [rsp+118h+var_E8]; this
0x1400ce8c6  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400ce8cb  mov     eax, ebx
0x1400ce8cd  jmp     loc_1400CF1B3
0x1400ce8d2  cmp     dword ptr [r14], 800h
0x1400ce8d9  ja      short loc_1400CE8E4
0x1400ce8db  mov     dword ptr [rdi+18h], 100h
0x1400ce8e2  jmp     short loc_1400CE906
0x1400ce8e4  cmp     dword ptr [r14], 0FE00h
0x1400ce8eb  jz      short loc_1400CE8FF
0x1400ce8ed  cmp     dword ptr [r14], 0FF00h
0x1400ce8f4  jz      short loc_1400CE8FF
0x1400ce8f6  mov     dword ptr [rdi+18h], 101h
0x1400ce8fd  jmp     short loc_1400CE906
0x1400ce8ff  mov     dword ptr [rdi+18h], 0FF00h
0x1400ce906  mov     [rsp+118h+var_94], r12d
0x1400ce90e  mov     rcx, [rdi+8]
0x1400ce912  mov     rax, [rcx]
0x1400ce915  lea     rdx, [rsp+118h+var_94]
0x1400ce91d  mov     rax, [rax+140h]
0x1400ce924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ce929  mov     ebx, eax
0x1400ce92b  test    eax, eax
0x1400ce92d  jns     short loc_1400CE95D
0x1400ce92f  mov     rcx, [rsp+118h]; this
0x1400ce937  mov     r9d, eax; char *
0x1400ce93a  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1400ce941  mov     edx, 1D1h; void *
0x1400ce946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400ce94b  nop
0x1400ce94c  lea     rcx, [rsp+118h+var_E8]; this
0x1400ce951  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400ce956  mov     eax, ebx
0x1400ce958  jmp     loc_1400CF1B3
0x1400ce95d  mov     [rdi+70h], esi
0x1400ce960  mov     rcx, [rdi+8]
0x1400ce964  lea     rbx, [rdi+80h]
0x1400ce96b  mov     rax, [rcx]
0x1400ce96e  mov     r8, rbx
0x1400ce971  lea     rdx, ?SECURITY_SETTING_VBS_OPT_OUT@@3QBGB; "/configuration/security/settings/vbs_op"...
0x1400ce978  mov     rax, [rax+80h]
0x1400ce97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ce984  mov     ecx, eax; int
0x1400ce986  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400ce98b  test    eax, eax
0x1400ce98d  jnz     short loc_1400CE992
0x1400ce98f  mov     [rbx], r12d
0x1400ce992  cmp     [rbx], r12d
0x1400ce995  jnz     short loc_1400CE9FB
0x1400ce997  mov     eax, [rdi+88h]
0x1400ce99d  test    eax, eax
0x1400ce99f  jz      short loc_1400CE9FB
0x1400ce9a1  cmp     eax, 2
0x1400ce9a4  jnz     short loc_1400CE9B5
0x1400ce9a6  cmp     [rdi+70h], r12d
0x1400ce9aa  jz      short loc_1400CE9D0
0x1400ce9ac  cmp     dword ptr [r14], 0B01h
0x1400ce9b3  jmp     short loc_1400CE9C7
0x1400ce9b5  cmp     eax, 3
0x1400ce9b8  jnz     short loc_1400CE9CB
0x1400ce9ba  cmp     [rdi+70h], r12d
0x1400ce9be  jz      short loc_1400CE9D0
0x1400ce9c0  cmp     dword ptr [r14], 0C02h
0x1400ce9c7  jnb     short loc_1400CE9FB
0x1400ce9c9  jmp     short loc_1400CE9D0
0x1400ce9cb  cmp     eax, 1
0x1400ce9ce  jz      short loc_1400CE9FB
0x1400ce9d0  mov     dword ptr [rbx], 1
0x1400ce9d6  mov     ebx, 0C020h
0x1400ce9db  mov     ecx, ebx
0x1400ce9dd  call    VmlIsDebugTraceEnabled
0x1400ce9e2  test    eax, eax
0x1400ce9e4  jz      short loc_1400CE9FB
0x1400ce9e6  mov     r8d, [rdi+88h]
0x1400ce9ed  lea     rdx, aVmIsolationTyp; "VM isolation type %x does not support V"...
0x1400ce9f4  mov     ecx, ebx
0x1400ce9f6  call    VmlDebugTrace
0x1400ce9fb  mov     rcx, [rdi+8]
0x1400ce9ff  lea     rsi, [rdi+78h]
0x1400cea03  mov     rax, [rcx]
0x1400cea06  mov     r8, rsi
0x1400cea09  lea     rdx, ?SECURITY_SETTING_TPM_ENABLED@@3QBGB; "/configuration/security/settings/tpm_en"...
0x1400cea10  mov     rax, [rax+80h]
0x1400cea17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cea1c  mov     ecx, eax; int
0x1400cea1e  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400cea23  test    eax, eax
0x1400cea25  jnz     short loc_1400CEA2A
0x1400cea27  mov     [rsi], r12d
0x1400cea2a  mov     rcx, [rdi+8]
0x1400cea2e  lea     rbx, [rdi+7Ch]
0x1400cea32  mov     rax, [rcx]
0x1400cea35  mov     r8, rbx
0x1400cea38  lea     rdx, ?SECURITY_SETTING_KSD_ENABLED@@3QBGB; "/configuration/security/settings/ksd_en"...
0x1400cea3f  mov     rax, [rax+80h]
0x1400cea46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400cea4b  mov     ecx, eax; int
0x1400cea4d  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400cea52  test    eax, eax
0x1400cea54  jnz     short loc_1400CEA59
0x1400cea56  mov     [rbx], r12d
0x1400cea59  cmp     [rsi], r12d
0x1400cea5c  jnz     short loc_1400CEA63
0x1400cea5e  cmp     [rbx], r12d
0x1400cea61  jz      short loc_1400CEA6C
0x1400cea63  cmp     [rdi+88h], r12d
0x1400cea6a  jz      short loc_1400CEA7D
0x1400cea6c  lea     rcx, [rsp+118h+var_E8]; this
0x1400cea71  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400cea76  xor     eax, eax
0x1400cea78  jmp     loc_1400CF1B3
0x1400cea7d  mov     rcx, [rdi+8]
0x1400cea81  mov     rax, [rcx]
0x1400cea84  lea     r8, ?LEGACY_SECURITY_SETTING_ENCRYPT_STATE_MIGRATION@@3QBGB; "/configuration/security/settings/data_p"...
0x1400cea8b  lea     rdx, ?SECURITY_SETTING_ENCRYPT_STATE_MIGRATION@@3QBGB; "/configuration/security/settings/encryp"...
0x1400cea92  cmp     dword ptr [r14], 701h
0x1400cea99  cmovb   rdx, r8
0x1400cea9d  lea     r8, [rdi+74h]
0x1400ceaa1  mov     rax, [rax+80h]
0x1400ceaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ceaad  mov     ecx, eax; int
0x1400ceaaf  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400ceab4  test    eax, eax
0x1400ceab6  jnz     short loc_1400CEABC
0x1400ceab8  mov     [rdi+74h], r12d
0x1400ceabc  mov     rcx, [rdi+8]
0x1400ceac0  lea     rbx, [rdi+6Ch]
0x1400ceac4  mov     rax, [rcx]
0x1400ceac7  mov     r8, rbx
0x1400ceaca  lea     rdx, ?SECURITY_SETTING_SHIELDING_REQUESTED@@3QBGB; "/configuration/security/settings/shield"...
0x1400cead1  mov     rax, [rax+80h]
0x1400cead8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ceadd  mov     ecx, eax; int
0x1400ceadf  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400ceae4  test    eax, eax
0x1400ceae6  jnz     short loc_1400CEAEB
0x1400ceae8  mov     [rbx], r12d
0x1400ceaeb  cmp     [rsi], r12d
0x1400ceaee  jz      loc_1400CF01D
0x1400ceaf4  mov     [rsp+118h+var_98], r12d
0x1400ceafc  cmp     [rsp+118h+var_94], 1
0x1400ceb04  jz      short loc_1400CEB1A
0x1400ceb06  lea     rcx, [rsp+118h+var_E8]; this
0x1400ceb0b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400ceb10  mov     eax, 80070032h
0x1400ceb15  jmp     loc_1400CF1B3
0x1400ceb1a  cmp     [rbx], r12d
0x1400ceb1d  jz      short loc_1400CEB26
0x1400ceb1f  mov     dword ptr [rdi+74h], 1
0x1400ceb26  xorps   xmm0, xmm0
0x1400ceb29  movups  xmmword ptr [rsp+118h+var_D8], xmm0
0x1400ceb2e  xor     r8d, r8d
0x1400ceb31  mov     rdx, [rdi+10h]
0x1400ceb35  lea     rcx, [rsp+118h+var_D8]
0x1400ceb3a  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400ceb3f  nop
0x1400ceb40  mov     ebx, dword ptr [rsp+118h+var_D8+8]
0x1400ceb44  test    ebx, ebx
0x1400ceb46  jns     short loc_1400CEB81
0x1400ceb48  mov     rcx, [rsp+118h]; this
0x1400ceb50  mov     r9d, ebx; char *
0x1400ceb53  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1400ceb5a  mov     edx, 241h; void *
0x1400ceb5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400ceb64  nop
0x1400ceb65  lea     rcx, [rsp+118h+var_D8]; this
0x1400ceb6a  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400ceb6f  nop
0x1400ceb70  lea     rcx, [rsp+118h+var_E8]; this
0x1400ceb75  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400ceb7a  mov     eax, ebx
0x1400ceb7c  jmp     loc_1400CF1B3
0x1400ceb81  mov     rcx, [rdi+10h]
0x1400ceb85  mov     rax, [rcx]
0x1400ceb88  lea     r8, [rsp+118h+var_98]
0x1400ceb90  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x1400ceb97  mov     rax, [rax+50h]
0x1400ceb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ceba0  mov     ecx, eax; int
0x1400ceba2  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400ceba7  test    eax, eax
0x1400ceba9  jz      loc_1400CEC47
0x1400cebaf  mov     eax, [rsp+118h+var_98]
  ... truncated ...
```
