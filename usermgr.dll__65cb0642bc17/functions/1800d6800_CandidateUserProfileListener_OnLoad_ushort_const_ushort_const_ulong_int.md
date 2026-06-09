# CandidateUserProfileListener::OnLoad(ushort const *,ushort const *,ulong,int)

- ea: `0x1800d6800`
- end: `0x1800d6b77`
- name: `?OnLoad@CandidateUserProfileListener@@UEAAJPEBG0KH@Z`
- size: `887`
- prototype: `int(CandidateUserProfileListener *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800088e8`
- `0x1800198bc`
- `0x18003d38c`
- `0x18003d588`
- `0x18004a9cc`
- `0x18004e75c`
- `0x180054818`
- `0x180061e1c`
- `0x18006e09c`
- `0x1800749bc`
- `0x1800d64dc`
- `0x1800d67a8`
- `0x1800d6800`
- `0x1800d6b80`
- `0x1800d6da4`
- `0x1800d6e30`
- `0x1800d6e88`
- `0x1800d6ee0`
- `0x1800d6f38`
- `0x1800d6f90`
- `0x1800d7078`
- `0x1800de450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d6993`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d6aa9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d6993`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d6aa9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d69e0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800d69e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d693b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d6a5e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d693b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d6a5e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d6886`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d6886`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x1800d68bb`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x1800d68bb`

## string_xrefs

- `0x1800d692d`: `Software\Microsoft\Windows\CurrentVersion\Authentication\LogonUI\Security`
- `0x1800d6849`: `onecore\ds\security\umstartup\candidateaccountmanager\candidateuserprofilelistener.cpp`
- `0x1800d6897`: `onecore\ds\security\umstartup\candidateaccountmanager\candidateuserprofilelistener.cpp`
- `0x1800d68d1`: `onecore\ds\security\umstartup\candidateaccountmanager\candidateuserprofilelistener.cpp`
- `0x1800d694a`: `onecore\ds\security\umstartup\candidateaccountmanager\candidateuserprofilelistener.cpp`
- `0x1800d69fe`: `onecore\ds\security\umstartup\candidateaccountmanager\candidateuserprofilelistener.cpp`
- `0x1800d6a6d`: `onecore\ds\security\umstartup\candidateaccountmanager\candidateuserprofilelistener.cpp`
- `0x1800d6aeb`: `onecore\ds\security\umstartup\candidateaccountmanager\candidateuserprofilelistener.cpp`

## pseudocode

```c
__int64 __fastcall CandidateUserProfileListener::OnLoad(
        CandidateUserProfileListener *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rdx
  CredProvPolicy *v5; // rcx
  const char *v6; // r9
  const char *v7; // r9
  unsigned int LastError; // ebx
  int IsCandidateUser; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbData[3]; // [rsp+74h] [rbp-8Ch] BYREF
  BYTE pvData[528]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  if ( !CredProvPolicy::IsPrimaryUserForEduEnvironment(this) && !CredProvPolicy::IsSharedUserForEduEnvironment(v5) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanager\\candidateuserprofilelistener.cpp",
      v6);
  LOBYTE(v4) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserInitSynchronization>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_UserInitSynchronization>::GetImpl'::`2'::impl,
    v4);
  CandidateUserProfileListenerTraceProvider::ProfileLoaded();
  if ( (unsigned __int8)IsCamIsCandidateUserPresent() )
  {
    Sid = 0;
    if ( !ConvertStringSidToSidW(a2, &Sid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x36,
                    (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanager\\candidateuserprofilelistener.cpp",
                    v7);
LABEL_29:
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
      return LastError;
    }
    v23 = 0;
    IsCandidateUser = CamIsCandidateUser(Sid, &v23);
    LastError = IsCandidateUser;
    if ( IsCandidateUser < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanager\\candidateuserprofilelistener.cpp",
        (const char *)(unsigned int)IsCandidateUser,
        dwOptions);
      goto LABEL_29;
    }
    if ( v23 )
    {
      CandidateUserProfileListenerTraceProvider::SetSuppressSystemDialogsRegistryKey();
      hKey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKey,
        0);
      v10 = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Security",
              0,
              0,
              0,
              2u,
              0,
              &hKey,
              0);
      if ( v10 )
      {
        v11 = 68;
LABEL_12:
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)v11,
                      (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanager\\candidateuserprofilelistener.cpp",
                      (const char *)v10,
                      dwOptionsa);
LABEL_28:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_29;
      }
      *(_DWORD *)Data = 1;
      v10 = RegSetValueExW(hKey, L"SuppressSystemDialogs", 0, 4u, Data, 4u);
      if ( v10 )
      {
        v11 = 76;
        goto LABEL_12;
      }
      pcbData[0] = 520;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\WinLogon",
             L"ShellAppRuntime",
             2u,
             0,
             pvData,
             pcbData) )
      {
        CandidateUserProfileListenerTraceProvider::ShellAppRuntimeUnavailable();
        LastError = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanager\\candidateuserprofilelistener.cpp",
          (const char *)0x8000FFFFLL,
          dwOptionsb);
        goto LABEL_28;
      }
      phkResult = 0;
      CandidateUserProfileListenerTraceProvider::SetAlternateShellRegistryKey();
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkResult,
        0);
      v12 = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\WinLogon",
              0,
              0,
              0,
              0xF003Fu,
              0,
              &phkResult,
              0);
      if ( v12 )
      {
        v13 = 105;
LABEL_19:
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)v13,
                      (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanager\\candidateuserprofilelistener.cpp",
                      (const char *)v12,
                      dwOptionsc);
LABEL_27:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        goto LABEL_28;
      }
      v12 = RegSetValueExW(phkResult, L"Shell", 0, 1u, pvData, 0x208u);
      if ( v12 )
      {
        v13 = 113;
        goto LABEL_19;
      }
      v14 = AppReadinessPolicyInfoAPI::SetUserPolicy(0);
      LastError = v14;
      if ( v14 < 0 )
      {
        v15 = 119;
LABEL_26:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanager\\candidateuserprofilelistener.cpp",
          (const char *)(unsigned int)v14,
          dwOptionsc);
        goto LABEL_27;
      }
      CandidateUserProfileListenerTraceProvider::SetShouldBlockLogonForCriticalAppsOnlyRegistryKey();
      v14 = AppReadinessPolicyInfoAPI::SetUserPolicy(1);
      LastError = v14;
      if ( v14 < 0 )
      {
        v15 = 122;
        goto LABEL_26;
      }
      CandidateUserProfileListenerTraceProvider::SetShouldRemainOnDemandForNonLogonBlockingRegistryKey();
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    else
    {
      CandidateUserProfileListenerTraceProvider::NotCandidateUser();
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
  }
  else
  {
    CandidateUserProfileListenerTraceProvider::CandidateAccountManagerNotPresent();
  }
  return 0;
}

```

## disassembly

```asm
0x1800d6800  mov     [rsp-8+arg_0], rbx
0x1800d6805  mov     [rsp-8+arg_10], rdi
0x1800d680a  push    rbp
0x1800d680b  lea     rbp, [rsp-1A0h]
0x1800d6813  sub     rsp, 2A0h
0x1800d681a  mov     rax, cs:__security_cookie
0x1800d6821  xor     rax, rsp
0x1800d6824  mov     [rbp+1A0h+var_10], rax
0x1800d682b  mov     rbx, rdx
0x1800d682e  call    ?IsPrimaryUserForEduEnvironment@CredProvPolicy@@YA_NXZ; CredProvPolicy::IsPrimaryUserForEduEnvironment(void)
0x1800d6833  xor     edi, edi
0x1800d6835  test    al, al
0x1800d6837  jnz     short loc_1800D6859
0x1800d6839  call    ?IsSharedUserForEduEnvironment@CredProvPolicy@@YA_NXZ; CredProvPolicy::IsSharedUserForEduEnvironment(void)
0x1800d683e  test    al, al
0x1800d6840  jnz     short loc_1800D6859
0x1800d6842  mov     rcx, [rbp+1A8h]; this
0x1800d6849  lea     r8, aOnecoreDsSecur_76; "onecore\\ds\\security\\umstartup\\candi"...
0x1800d6850  lea     edx, [rdi+2Dh]; void *
0x1800d6853  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d6859  mov     dl, 1
0x1800d685b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UserInitSynchronization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UserInitSynchronization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserInitSynchronization> `wil::Feature<__WilFeatureTraits_Feature_UserInitSynchronization>::GetImpl(void)'::`2'::impl
0x1800d6862  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UserInitSynchronization@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserInitSynchronization>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800d6867  call    ?ProfileLoaded@CandidateUserProfileListenerTraceProvider@@SAXXZ; CandidateUserProfileListenerTraceProvider::ProfileLoaded(void)
0x1800d686c  call    IsCamIsCandidateUserPresent
0x1800d6871  test    al, al
0x1800d6873  jz      loc_1800D6B4C
0x1800d6879  mov     [rsp+2A0h+Sid], rdi
0x1800d687e  lea     rdx, [rsp+2A0h+Sid]; Sid
0x1800d6883  mov     rcx, rbx; StringSid
0x1800d6886  call    cs:__imp_ConvertStringSidToSidW
0x1800d688c  test    eax, eax
0x1800d688e  jnz     short loc_1800D68AD
0x1800d6890  mov     rcx, [rbp+1A8h]; this
0x1800d6897  lea     r8, aOnecoreDsSecur_76; "onecore\\ds\\security\\umstartup\\candi"...
0x1800d689e  lea     edx, [rax+36h]; void *
0x1800d68a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d68a6  mov     ebx, eax
0x1800d68a8  jmp     loc_1800D6B12
0x1800d68ad  mov     [rsp+2A0h+var_240], edi
0x1800d68b1  lea     rdx, [rsp+2A0h+var_240]
0x1800d68b6  mov     rcx, [rsp+2A0h+Sid]
0x1800d68bb  call    cs:__imp_CamIsCandidateUser
0x1800d68c1  mov     ebx, eax
0x1800d68c3  test    eax, eax
0x1800d68c5  jns     short loc_1800D68E7
0x1800d68c7  mov     rcx, [rbp+1A8h]; this
0x1800d68ce  mov     r9d, eax; char *
0x1800d68d1  lea     r8, aOnecoreDsSecur_76; "onecore\\ds\\security\\umstartup\\candi"...
0x1800d68d8  mov     edx, 3Bh ; ';'; void *
0x1800d68dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d68e2  jmp     loc_1800D6B12
0x1800d68e7  cmp     [rsp+2A0h+var_240], edi
0x1800d68eb  jz      loc_1800D6B3B
0x1800d68f1  call    ?SetSuppressSystemDialogsRegistryKey@CandidateUserProfileListenerTraceProvider@@SAXXZ; CandidateUserProfileListenerTraceProvider::SetSuppressSystemDialogsRegistryKey(void)
0x1800d68f6  mov     [rsp+2A0h+hKey], rdi
0x1800d68fb  xor     edx, edx
0x1800d68fd  lea     rcx, [rsp+2A0h+hKey]
0x1800d6902  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d6907  mov     [rsp+2A0h+lpdwDisposition], rdi; lpdwDisposition
0x1800d690c  lea     rax, [rsp+2A0h+hKey]
0x1800d6911  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800d6916  mov     [rsp+2A0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800d691b  mov     [rsp+2A0h+samDesired], 2; samDesired
0x1800d6923  mov     [rsp+2A0h+dwOptions], edi; unsigned int
0x1800d6927  xor     r9d, r9d; lpClass
0x1800d692a  xor     r8d, r8d; Reserved
0x1800d692d  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d6934  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800d693b  call    cs:__imp_RegCreateKeyExW
0x1800d6941  test    eax, eax
0x1800d6943  jz      short loc_1800D6967
0x1800d6945  mov     edx, 44h ; 'D'; void *
0x1800d694a  lea     r8, aOnecoreDsSecur_76; "onecore\\ds\\security\\umstartup\\candi"...
0x1800d6951  mov     r9d, eax; char *
0x1800d6954  mov     rcx, [rbp+1A8h]; this
0x1800d695b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d6960  mov     ebx, eax
0x1800d6962  jmp     loc_1800D6B08
0x1800d6967  mov     dword ptr [rsp+2A0h+Data], 1
0x1800d696f  mov     r9d, 4; dwType
0x1800d6975  mov     [rsp+2A0h+samDesired], r9d; cbData
0x1800d697a  lea     rax, [rsp+2A0h+Data]
0x1800d697f  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x1800d6984  xor     r8d, r8d; Reserved
0x1800d6987  lea     rdx, aSuppresssystem; "SuppressSystemDialogs"
0x1800d698e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800d6993  call    cs:__imp_RegSetValueExW
0x1800d6999  test    eax, eax
0x1800d699b  jz      short loc_1800D69A4
0x1800d699d  mov     edx, 4Ch ; 'L'
0x1800d69a2  jmp     short loc_1800D694A
0x1800d69a4  mov     ebx, 208h
0x1800d69a9  mov     [rsp+2A0h+pcbData], ebx
0x1800d69ad  lea     rax, [rsp+2A0h+pcbData]
0x1800d69b2  mov     [rsp+2A0h+lpSecurityAttributes], rax; pcbData
0x1800d69b7  lea     rax, [rbp+1A0h+pvData]
0x1800d69bb  mov     qword ptr [rsp+2A0h+samDesired], rax; pvData
0x1800d69c0  mov     qword ptr [rsp+2A0h+dwOptions], rdi; int
0x1800d69c5  mov     r9d, 2; dwFlags
0x1800d69cb  lea     r8, aShellappruntim; "ShellAppRuntime"
0x1800d69d2  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800d69d9  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800d69e0  call    cs:__imp_RegGetValueW
0x1800d69e6  test    eax, eax
0x1800d69e8  jz      short loc_1800D6A14
0x1800d69ea  call    ?ShellAppRuntimeUnavailable@CandidateUserProfileListenerTraceProvider@@SAXXZ; CandidateUserProfileListenerTraceProvider::ShellAppRuntimeUnavailable(void)
0x1800d69ef  mov     rcx, [rbp+1A8h]; this
0x1800d69f6  mov     ebx, 8000FFFFh
0x1800d69fb  mov     r9d, ebx; char *
0x1800d69fe  lea     r8, aOnecoreDsSecur_76; "onecore\\ds\\security\\umstartup\\candi"...
0x1800d6a05  mov     edx, 5Eh ; '^'; void *
0x1800d6a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d6a0f  jmp     loc_1800D6B08
0x1800d6a14  mov     [rsp+2A0h+var_248], rdi
0x1800d6a19  call    ?SetAlternateShellRegistryKey@CandidateUserProfileListenerTraceProvider@@SAXXZ; CandidateUserProfileListenerTraceProvider::SetAlternateShellRegistryKey(void)
0x1800d6a1e  xor     edx, edx
0x1800d6a20  lea     rcx, [rsp+2A0h+var_248]
0x1800d6a25  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800d6a2a  mov     [rsp+2A0h+lpdwDisposition], rdi; lpdwDisposition
0x1800d6a2f  lea     rax, [rsp+2A0h+var_248]
0x1800d6a34  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800d6a39  mov     [rsp+2A0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800d6a3e  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x1800d6a46  mov     [rsp+2A0h+dwOptions], edi; unsigned int
0x1800d6a4a  xor     r9d, r9d; lpClass
0x1800d6a4d  xor     r8d, r8d; Reserved
0x1800d6a50  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800d6a57  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800d6a5e  call    cs:__imp_RegCreateKeyExW
0x1800d6a64  test    eax, eax
0x1800d6a66  jz      short loc_1800D6A87
0x1800d6a68  mov     edx, 69h ; 'i'; void *
0x1800d6a6d  lea     r8, aOnecoreDsSecur_76; "onecore\\ds\\security\\umstartup\\candi"...
0x1800d6a74  mov     r9d, eax; char *
0x1800d6a77  mov     rcx, [rbp+1A8h]; this
0x1800d6a7e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d6a83  mov     ebx, eax
0x1800d6a85  jmp     short loc_1800D6AFE
0x1800d6a87  mov     [rsp+2A0h+samDesired], ebx; cbData
0x1800d6a8b  lea     rax, [rbp+1A0h+pvData]
0x1800d6a8f  mov     qword ptr [rsp+2A0h+dwOptions], rax; int
0x1800d6a94  mov     r9d, 1; dwType
0x1800d6a9a  xor     r8d, r8d; Reserved
0x1800d6a9d  lea     rdx, aShell; "Shell"
0x1800d6aa4  mov     rcx, [rsp+2A0h+var_248]; hKey
0x1800d6aa9  call    cs:__imp_RegSetValueExW
0x1800d6aaf  test    eax, eax
0x1800d6ab1  jz      short loc_1800D6ABA
0x1800d6ab3  mov     edx, 71h ; 'q'
0x1800d6ab8  jmp     short loc_1800D6A6D
0x1800d6aba  xor     ecx, ecx
0x1800d6abc  call    ?SetUserPolicy@AppReadinessPolicyInfoAPI@@YAJW4AppReadinessUserPolicy@1@W4PolicyState@1@@Z; AppReadinessPolicyInfoAPI::SetUserPolicy(AppReadinessPolicyInfoAPI::AppReadinessUserPolicy,AppReadinessPolicyInfoAPI::PolicyState)
0x1800d6ac1  mov     ebx, eax
0x1800d6ac3  test    eax, eax
0x1800d6ac5  jns     short loc_1800D6ACE
0x1800d6ac7  mov     edx, 77h ; 'w'
0x1800d6acc  jmp     short loc_1800D6AE8
0x1800d6ace  call    ?SetShouldBlockLogonForCriticalAppsOnlyRegistryKey@CandidateUserProfileListenerTraceProvider@@SAXXZ; CandidateUserProfileListenerTraceProvider::SetShouldBlockLogonForCriticalAppsOnlyRegistryKey(void)
0x1800d6ad3  mov     ecx, 1
0x1800d6ad8  call    ?SetUserPolicy@AppReadinessPolicyInfoAPI@@YAJW4AppReadinessUserPolicy@1@W4PolicyState@1@@Z; AppReadinessPolicyInfoAPI::SetUserPolicy(AppReadinessPolicyInfoAPI::AppReadinessUserPolicy,AppReadinessPolicyInfoAPI::PolicyState)
0x1800d6add  mov     ebx, eax
0x1800d6adf  test    eax, eax
0x1800d6ae1  jns     short loc_1800D6B20
0x1800d6ae3  mov     edx, 7Ah ; 'z'; void *
0x1800d6ae8  mov     r9d, eax; char *
0x1800d6aeb  lea     r8, aOnecoreDsSecur_76; "onecore\\ds\\security\\umstartup\\candi"...
0x1800d6af2  mov     rcx, [rbp+1A8h]; this
0x1800d6af9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d6afe  lea     rcx, [rsp+2A0h+var_248]
0x1800d6b03  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d6b08  lea     rcx, [rsp+2A0h+hKey]
0x1800d6b0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d6b12  lea     rcx, [rsp+2A0h+Sid]
0x1800d6b17  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d6b1c  mov     eax, ebx
0x1800d6b1e  jmp     short loc_1800D6B53
0x1800d6b20  call    ?SetShouldRemainOnDemandForNonLogonBlockingRegistryKey@CandidateUserProfileListenerTraceProvider@@SAXXZ; CandidateUserProfileListenerTraceProvider::SetShouldRemainOnDemandForNonLogonBlockingRegistryKey(void)
0x1800d6b25  lea     rcx, [rsp+2A0h+var_248]
0x1800d6b2a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d6b2f  lea     rcx, [rsp+2A0h+hKey]
0x1800d6b34  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d6b39  jmp     short loc_1800D6B40
0x1800d6b3b  call    ?NotCandidateUser@CandidateUserProfileListenerTraceProvider@@SAXXZ; CandidateUserProfileListenerTraceProvider::NotCandidateUser(void)
0x1800d6b40  lea     rcx, [rsp+2A0h+Sid]
0x1800d6b45  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d6b4a  jmp     short loc_1800D6B51
0x1800d6b4c  call    ?CandidateAccountManagerNotPresent@CandidateUserProfileListenerTraceProvider@@SAXXZ; CandidateUserProfileListenerTraceProvider::CandidateAccountManagerNotPresent(void)
0x1800d6b51  xor     eax, eax
0x1800d6b53  mov     rcx, [rbp+1A0h+var_10]
0x1800d6b5a  xor     rcx, rsp; StackCookie
0x1800d6b5d  call    __security_check_cookie
0x1800d6b62  lea     r11, [rsp+2A0h+var_s0]
0x1800d6b6a  mov     rbx, [r11+10h]
0x1800d6b6e  mov     rdi, [r11+20h]
0x1800d6b72  mov     rsp, r11
0x1800d6b75  pop     rbp
0x1800d6b76  retn
```
