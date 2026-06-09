# SecurityManager::Initialize(int)

- ea: `0x1400de650`
- end: `0x1400df155`
- name: `?Initialize@SecurityManager@@UEAAJH@Z`
- size: `2821`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this, int)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140030120`
- `0x140031ca8`
- `0x140034f18`
- `0x14003ae10`
- `0x140042260`
- `0x1400544a8`
- `0x1400545d0`
- `0x140054a90`
- `0x14005e6a4`
- `0x14005e804`
- `0x140081798`
- `0x14009fa0c`
- `0x1400b42d0`
- `0x1400de650`
- `0x1400df15c`
- `0x14012ea5c`
- `0x140132960`
- `0x1402748ac`
- `0x140297ae4`
- `0x140297c64`
- `0x1402c2010`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1400ded3c`
- `ntdll!RtlCompareMemory` at `0x1400ded3c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400de6cb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400de6cb`

## string_xrefs

- `0x1400de8f1`: `/configuration/security/settings/vbs_opt_out`
- `0x1400de9b8`: `/configuration/security/settings/ksd_enabled`
- `0x1400deef9`: `/configuration/security/policy/encrypted_policy`
- `0x1400df03b`: `/configuration/security/keys/key_protector`
- `0x1400df0a2`: `/configuration/security/keys/key_protector`
- `0x1400dedac`: `/configuration/security/policy/security_policy`
- `0x1400dee09`: `/configuration/security/policy/security_policy`
- `0x1400deb10`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x1400deb78`: `/configuration/security/vtpm/vtpm_engine_nvram`
- `0x1400dea4a`: `/configuration/security/settings/shielding_requested`
- `0x1400debe6`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x1400decda`: `/configuration/security/vtpm/vtpm_engine_nvram_hash`
- `0x1400dea04`: `/configuration/security/settings/data_protection_requested`
- `0x1400dea0b`: `/configuration/security/settings/encrypt_state_migration`
- `0x1400de989`: `/configuration/security/settings/tpm_enabled`
- `0x1400de6a5`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de711`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de75c`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de7b6`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de82f`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400de8ba`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400dead3`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400deb99`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400dec9a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400decfb`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400dee2a`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1400df0c3`: `onecore\vm\worker\security\securitymanager.cpp`

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
0x1400de650  mov     r11, rsp
0x1400de653  push    rbx
0x1400de654  push    rsi
0x1400de655  push    rdi
0x1400de656  push    r12
0x1400de658  push    r14
0x1400de65a  push    r15
0x1400de65c  sub     rsp, 0E8h
0x1400de663  mov     rax, cs:__security_cookie
0x1400de66a  xor     rax, rsp
0x1400de66d  mov     [rsp+118h+var_40], rax
0x1400de675  mov     esi, edx
0x1400de677  mov     rdi, rcx
0x1400de67a  xorps   xmm0, xmm0
0x1400de67d  movups  xmmword ptr [r11-60h], xmm0
0x1400de682  movups  xmmword ptr [r11-50h], xmm0
0x1400de687  xorps   xmm1, xmm1
0x1400de68a  movups  xmmword ptr [r11-80h], xmm1
0x1400de68f  movups  xmmword ptr [r11-70h], xmm1
0x1400de694  mov     rcx, [rsp+118h]; this
0x1400de69c  xor     r12d, r12d
0x1400de69f  cmp     [rdi+10h], r12
0x1400de6a3  jnz     short loc_1400DE6B7
0x1400de6a5  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de6ac  mov     edx, 1B6h; void *
0x1400de6b1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400de6b7  lea     rcx, [rdi+170h]; phAlgorithm
0x1400de6be  xor     r9d, r9d; dwFlags
0x1400de6c1  xor     r8d, r8d; pszImplementation
0x1400de6c4  lea     rdx, pszAlgId; "SHA256"
0x1400de6cb  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400de6d2  nop     dword ptr [rax+rax+00h]
0x1400de6d7  test    eax, eax
0x1400de6d9  jns     short loc_1400DE6E4
0x1400de6db  bts     eax, 1Ch
0x1400de6df  jmp     loc_1400DF133
0x1400de6e4  xorps   xmm0, xmm0
0x1400de6e7  movups  xmmword ptr [rsp+118h+var_E8], xmm0
0x1400de6ec  xor     r8d, r8d
0x1400de6ef  mov     rdx, [rdi+8]
0x1400de6f3  lea     rcx, [rsp+118h+var_E8]
0x1400de6f8  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400de6fd  nop
0x1400de6fe  mov     ebx, dword ptr [rsp+118h+var_E8+8]
0x1400de702  test    ebx, ebx
0x1400de704  jns     short loc_1400DE734
0x1400de706  mov     rcx, [rsp+118h]; this
0x1400de70e  mov     r9d, ebx; char *
0x1400de711  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de718  mov     edx, 1C5h; void *
0x1400de71d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de722  nop
0x1400de723  lea     rcx, [rsp+118h+var_E8]; this
0x1400de728  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de72d  mov     eax, ebx
0x1400de72f  jmp     loc_1400DF133
0x1400de734  mov     rcx, [rdi+8]
0x1400de738  mov     rax, [rcx]
0x1400de73b  lea     rdx, [rdi+20h]
0x1400de73f  mov     rax, [rax+128h]
0x1400de746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de74b  mov     ebx, eax
0x1400de74d  test    eax, eax
0x1400de74f  jns     short loc_1400DE77F
0x1400de751  mov     rcx, [rsp+118h]; this
0x1400de759  mov     r9d, eax; char *
0x1400de75c  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de763  mov     edx, 1C7h; void *
0x1400de768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de76d  nop
0x1400de76e  lea     rcx, [rsp+118h+var_E8]; this
0x1400de773  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de778  mov     eax, ebx
0x1400de77a  jmp     loc_1400DF133
0x1400de77f  xorps   xmm0, xmm0
0x1400de782  movups  [rsp+118h+var_90], xmm0
0x1400de78a  mov     rcx, [rdi+8]
0x1400de78e  mov     rax, [rcx]
0x1400de791  lea     rdx, [rsp+118h+var_90]
0x1400de799  mov     rax, [rax+130h]
0x1400de7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de7a5  mov     ebx, eax
0x1400de7a7  test    eax, eax
0x1400de7a9  jns     short loc_1400DE7D9
0x1400de7ab  mov     rcx, [rsp+118h]; this
0x1400de7b3  mov     r9d, eax; char *
0x1400de7b6  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de7bd  mov     edx, 1CAh; void *
0x1400de7c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de7c7  nop
0x1400de7c8  lea     rcx, [rsp+118h+var_E8]; this
0x1400de7cd  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de7d2  mov     eax, ebx
0x1400de7d4  jmp     loc_1400DF133
0x1400de7d9  lea     rdx, [rsp+118h+var_90]
0x1400de7e1  lea     rcx, [rsp+118h+var_B8]
0x1400de7e6  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400de7eb  lea     rcx, [rdi+40h]
0x1400de7ef  mov     rdx, rax
0x1400de7f2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400de7f7  lea     rcx, [rsp+118h+var_B8]
0x1400de7fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400de801  mov     rcx, [rdi+8]
0x1400de805  lea     r14, [rdi+178h]
0x1400de80c  mov     rax, [rcx]
0x1400de80f  mov     rdx, r14
0x1400de812  mov     rax, [rax+120h]
0x1400de819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de81e  mov     ebx, eax
0x1400de820  test    eax, eax
0x1400de822  jns     short loc_1400DE852
0x1400de824  mov     rcx, [rsp+118h]; this
0x1400de82c  mov     r9d, eax; char *
0x1400de82f  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de836  mov     edx, 1CDh; void *
0x1400de83b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de840  nop
0x1400de841  lea     rcx, [rsp+118h+var_E8]; this
0x1400de846  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de84b  mov     eax, ebx
0x1400de84d  jmp     loc_1400DF133
0x1400de852  cmp     dword ptr [r14], 800h
0x1400de859  ja      short loc_1400DE864
0x1400de85b  mov     dword ptr [rdi+18h], 100h
0x1400de862  jmp     short loc_1400DE886
0x1400de864  cmp     dword ptr [r14], 0FE00h
0x1400de86b  jz      short loc_1400DE87F
0x1400de86d  cmp     dword ptr [r14], 0FF00h
0x1400de874  jz      short loc_1400DE87F
0x1400de876  mov     dword ptr [rdi+18h], 101h
0x1400de87d  jmp     short loc_1400DE886
0x1400de87f  mov     dword ptr [rdi+18h], 0FF00h
0x1400de886  mov     [rsp+118h+var_94], r12d
0x1400de88e  mov     rcx, [rdi+8]
0x1400de892  mov     rax, [rcx]
0x1400de895  lea     rdx, [rsp+118h+var_94]
0x1400de89d  mov     rax, [rax+140h]
0x1400de8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de8a9  mov     ebx, eax
0x1400de8ab  test    eax, eax
0x1400de8ad  jns     short loc_1400DE8DD
0x1400de8af  mov     rcx, [rsp+118h]; this
0x1400de8b7  mov     r9d, eax; char *
0x1400de8ba  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400de8c1  mov     edx, 1D1h; void *
0x1400de8c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400de8cb  nop
0x1400de8cc  lea     rcx, [rsp+118h+var_E8]; this
0x1400de8d1  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de8d6  mov     eax, ebx
0x1400de8d8  jmp     loc_1400DF133
0x1400de8dd  mov     [rdi+70h], esi
0x1400de8e0  mov     rcx, [rdi+8]
0x1400de8e4  lea     rbx, [rdi+80h]
0x1400de8eb  mov     rax, [rcx]
0x1400de8ee  mov     r8, rbx
0x1400de8f1  lea     rdx, ?SECURITY_SETTING_VBS_OPT_OUT@@3QBGB; "/configuration/security/settings/vbs_op"...
0x1400de8f8  mov     rax, [rax+80h]
0x1400de8ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de904  mov     ecx, eax; int
0x1400de906  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400de90b  test    eax, eax
0x1400de90d  jnz     short loc_1400DE912
0x1400de90f  mov     [rbx], r12d
0x1400de912  cmp     [rbx], r12d
0x1400de915  jnz     short loc_1400DE97B
0x1400de917  mov     eax, [rdi+88h]
0x1400de91d  test    eax, eax
0x1400de91f  jz      short loc_1400DE97B
0x1400de921  cmp     eax, 2
0x1400de924  jnz     short loc_1400DE935
0x1400de926  cmp     [rdi+70h], r12d
0x1400de92a  jz      short loc_1400DE950
0x1400de92c  cmp     dword ptr [r14], 0B01h
0x1400de933  jmp     short loc_1400DE947
0x1400de935  cmp     eax, 3
0x1400de938  jnz     short loc_1400DE94B
0x1400de93a  cmp     [rdi+70h], r12d
0x1400de93e  jz      short loc_1400DE950
0x1400de940  cmp     dword ptr [r14], 0C02h
0x1400de947  jnb     short loc_1400DE97B
0x1400de949  jmp     short loc_1400DE950
0x1400de94b  cmp     eax, 1
0x1400de94e  jz      short loc_1400DE97B
0x1400de950  mov     dword ptr [rbx], 1
0x1400de956  mov     ebx, 0C020h
0x1400de95b  mov     ecx, ebx
0x1400de95d  call    VmlIsDebugTraceEnabled
0x1400de962  test    eax, eax
0x1400de964  jz      short loc_1400DE97B
0x1400de966  mov     r8d, [rdi+88h]
0x1400de96d  lea     rdx, aVmIsolationTyp; "VM isolation type %x does not support V"...
0x1400de974  mov     ecx, ebx
0x1400de976  call    VmlDebugTrace
0x1400de97b  mov     rcx, [rdi+8]
0x1400de97f  lea     rsi, [rdi+78h]
0x1400de983  mov     rax, [rcx]
0x1400de986  mov     r8, rsi
0x1400de989  lea     rdx, ?SECURITY_SETTING_TPM_ENABLED@@3QBGB; "/configuration/security/settings/tpm_en"...
0x1400de990  mov     rax, [rax+80h]
0x1400de997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de99c  mov     ecx, eax; int
0x1400de99e  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400de9a3  test    eax, eax
0x1400de9a5  jnz     short loc_1400DE9AA
0x1400de9a7  mov     [rsi], r12d
0x1400de9aa  mov     rcx, [rdi+8]
0x1400de9ae  lea     rbx, [rdi+7Ch]
0x1400de9b2  mov     rax, [rcx]
0x1400de9b5  mov     r8, rbx
0x1400de9b8  lea     rdx, ?SECURITY_SETTING_KSD_ENABLED@@3QBGB; "/configuration/security/settings/ksd_en"...
0x1400de9bf  mov     rax, [rax+80h]
0x1400de9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400de9cb  mov     ecx, eax; int
0x1400de9cd  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400de9d2  test    eax, eax
0x1400de9d4  jnz     short loc_1400DE9D9
0x1400de9d6  mov     [rbx], r12d
0x1400de9d9  cmp     [rsi], r12d
0x1400de9dc  jnz     short loc_1400DE9E3
0x1400de9de  cmp     [rbx], r12d
0x1400de9e1  jz      short loc_1400DE9EC
0x1400de9e3  cmp     [rdi+88h], r12d
0x1400de9ea  jz      short loc_1400DE9FD
0x1400de9ec  lea     rcx, [rsp+118h+var_E8]; this
0x1400de9f1  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400de9f6  xor     eax, eax
0x1400de9f8  jmp     loc_1400DF133
0x1400de9fd  mov     rcx, [rdi+8]
0x1400dea01  mov     rax, [rcx]
0x1400dea04  lea     r8, ?LEGACY_SECURITY_SETTING_ENCRYPT_STATE_MIGRATION@@3QBGB; "/configuration/security/settings/data_p"...
0x1400dea0b  lea     rdx, ?SECURITY_SETTING_ENCRYPT_STATE_MIGRATION@@3QBGB; "/configuration/security/settings/encryp"...
0x1400dea12  cmp     dword ptr [r14], 701h
0x1400dea19  cmovb   rdx, r8
0x1400dea1d  lea     r8, [rdi+74h]
0x1400dea21  mov     rax, [rax+80h]
0x1400dea28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400dea2d  mov     ecx, eax; int
0x1400dea2f  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400dea34  test    eax, eax
0x1400dea36  jnz     short loc_1400DEA3C
0x1400dea38  mov     [rdi+74h], r12d
0x1400dea3c  mov     rcx, [rdi+8]
0x1400dea40  lea     rbx, [rdi+6Ch]
0x1400dea44  mov     rax, [rcx]
0x1400dea47  mov     r8, rbx
0x1400dea4a  lea     rdx, ?SECURITY_SETTING_SHIELDING_REQUESTED@@3QBGB; "/configuration/security/settings/shield"...
0x1400dea51  mov     rax, [rax+80h]
0x1400dea58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400dea5d  mov     ecx, eax; int
0x1400dea5f  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400dea64  test    eax, eax
0x1400dea66  jnz     short loc_1400DEA6B
0x1400dea68  mov     [rbx], r12d
0x1400dea6b  cmp     [rsi], r12d
0x1400dea6e  jz      loc_1400DEF9D
0x1400dea74  mov     [rsp+118h+var_98], r12d
0x1400dea7c  cmp     [rsp+118h+var_94], 1
0x1400dea84  jz      short loc_1400DEA9A
0x1400dea86  lea     rcx, [rsp+118h+var_E8]; this
0x1400dea8b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400dea90  mov     eax, 80070032h
0x1400dea95  jmp     loc_1400DF133
0x1400dea9a  cmp     [rbx], r12d
0x1400dea9d  jz      short loc_1400DEAA6
0x1400dea9f  mov     dword ptr [rdi+74h], 1
0x1400deaa6  xorps   xmm0, xmm0
0x1400deaa9  movups  xmmword ptr [rsp+118h+var_D8], xmm0
0x1400deaae  xor     r8d, r8d
0x1400deab1  mov     rdx, [rdi+10h]
0x1400deab5  lea     rcx, [rsp+118h+var_D8]
0x1400deaba  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1400deabf  nop
0x1400deac0  mov     ebx, dword ptr [rsp+118h+var_D8+8]
0x1400deac4  test    ebx, ebx
0x1400deac6  jns     short loc_1400DEB01
0x1400deac8  mov     rcx, [rsp+118h]; this
0x1400dead0  mov     r9d, ebx; char *
0x1400dead3  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1400deada  mov     edx, 241h; void *
0x1400deadf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400deae4  nop
0x1400deae5  lea     rcx, [rsp+118h+var_D8]; this
0x1400deaea  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400deaef  nop
0x1400deaf0  lea     rcx, [rsp+118h+var_E8]; this
0x1400deaf5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1400deafa  mov     eax, ebx
0x1400deafc  jmp     loc_1400DF133
0x1400deb01  mov     rcx, [rdi+10h]
0x1400deb05  mov     rax, [rcx]
0x1400deb08  lea     r8, [rsp+118h+var_98]
0x1400deb10  lea     rdx, ?SECURITY_VTPM_ENGINE_NVRAM@@3QBGB; "/configuration/security/vtpm/vtpm_engin"...
0x1400deb17  mov     rax, [rax+50h]
0x1400deb1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400deb20  mov     ecx, eax; int
0x1400deb22  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x1400deb27  test    eax, eax
0x1400deb29  jz      loc_1400DEBC7
0x1400deb2f  mov     eax, [rsp+118h+var_98]
  ... truncated ...
```
