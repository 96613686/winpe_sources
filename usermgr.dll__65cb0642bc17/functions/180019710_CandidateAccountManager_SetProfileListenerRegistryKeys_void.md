# CandidateAccountManager::SetProfileListenerRegistryKeys(void)

- ea: `0x180019710`
- end: `0x1800198b3`
- name: `?SetProfileListenerRegistryKeys@CandidateAccountManager@@AEAAJXZ`
- size: `419`
- prototype: `__int64 __fastcall(CandidateAccountManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b4180`

## callees

- `0x180019710`
- `0x1800198bc`
- `0x18003d38c`
- `0x18004a9cc`
- `0x18004e75c`
- `0x180054818`
- `0x1800d6da4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800197bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800197fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019834`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001986e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800197bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800197fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019834`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001986e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019785`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019785`

## string_xrefs

- `0x1800197e5`: `CLSID`
- `0x180019882`: `onecore\ds\security\umstartup\candidateaccountmanager\candidateaccountmanager.cpp`

## pseudocode

```c
__int64 __fastcall CandidateAccountManager::SetProfileListenerRegistryKeys(CandidateAccountManager *this)
{
  __int64 v1; // rdx
  CredProvPolicy *v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = (HKEY)this;
  if ( CredProvPolicy::IsPrimaryUserForEduEnvironment(this) || CredProvPolicy::IsSharedUserForEduEnvironment(v2) )
  {
    LOBYTE(v1) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserInitSynchronization>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_UserInitSynchronization>::GetImpl'::`2'::impl,
      v1);
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v3 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileNotification\\CandidateAccountManager",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &hKey,
           0);
    if ( v3 )
    {
      v4 = 70;
LABEL_13:
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\ds\\security\\umstartup\\candidateaccountmanager\\candidateaccountmanager.cpp",
             (const char *)v3,
             dwOptions);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v5;
    }
    v3 = RegSetValueExW(hKey, 0, 0, 1u, L"Candidate Account Manager", 0x34u);
    if ( v3 )
    {
      v4 = 75;
      goto LABEL_13;
    }
    v3 = RegSetValueExW(hKey, L"CLSID", 0, 1u, L"{ae7e0cd9-0faa-459c-ba09-d141c4b3d06e}", 0x4Eu);
    if ( v3 )
    {
      v4 = 79;
      goto LABEL_13;
    }
    v3 = RegSetValueExW(hKey, L"Events", 0, 4u, &byte_180117A88, 4u);
    if ( v3 )
    {
      v4 = 82;
      goto LABEL_13;
    }
    v3 = RegSetValueExW(hKey, L"Flags", 0, 4u, &byte_180117A8C, 4u);
    if ( v3 )
    {
      v4 = 85;
      goto LABEL_13;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180019710  mov     [rsp+hKey], rcx
0x180019715  push    rbx
0x180019716  sub     rsp, 50h
0x18001971a  call    ?IsPrimaryUserForEduEnvironment@CredProvPolicy@@YA_NXZ; CredProvPolicy::IsPrimaryUserForEduEnvironment(void)
0x18001971f  xor     ebx, ebx
0x180019721  test    al, al
0x180019723  jnz     short loc_180019732
0x180019725  call    ?IsSharedUserForEduEnvironment@CredProvPolicy@@YA_NXZ; CredProvPolicy::IsSharedUserForEduEnvironment(void)
0x18001972a  test    al, al
0x18001972c  jz      loc_1800198AB
0x180019732  mov     dl, 1
0x180019734  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UserInitSynchronization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UserInitSynchronization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserInitSynchronization> `wil::Feature<__WilFeatureTraits_Feature_UserInitSynchronization>::GetImpl(void)'::`2'::impl
0x18001973b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UserInitSynchronization@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserInitSynchronization>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180019740  xor     edx, edx
0x180019742  mov     [rsp+58h+hKey], rbx
0x180019747  lea     rcx, [rsp+58h+hKey]
0x18001974c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180019751  mov     [rsp+58h+lpdwDisposition], rbx; lpdwDisposition
0x180019756  lea     rax, [rsp+58h+hKey]
0x18001975b  mov     [rsp+58h+phkResult], rax; phkResult
0x180019760  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180019767  mov     [rsp+58h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18001976c  xor     r9d, r9d; lpClass
0x18001976f  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180019777  xor     r8d, r8d; Reserved
0x18001977a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019781  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x180019785  call    cs:__imp_RegCreateKeyExW
0x18001978b  test    eax, eax
0x18001978d  jz      short loc_180019799
0x18001978f  mov     edx, 46h ; 'F'
0x180019794  jmp     loc_18001987D
0x180019799  mov     rcx, [rsp+58h+hKey]; hKey
0x18001979e  lea     rax, Data; "Candidate Account Manager"
0x1800197a5  mov     [rsp+58h+samDesired], 34h ; '4'; cbData
0x1800197ad  mov     r9d, 1; dwType
0x1800197b3  xor     r8d, r8d; Reserved
0x1800197b6  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800197bb  xor     edx, edx; lpValueName
0x1800197bd  call    cs:__imp_RegSetValueExW
0x1800197c3  test    eax, eax
0x1800197c5  jz      short loc_1800197D1
0x1800197c7  mov     edx, 4Bh ; 'K'
0x1800197cc  jmp     loc_18001987D
0x1800197d1  mov     rcx, [rsp+58h+hKey]; hKey
0x1800197d6  lea     rax, aAe7e0cd90faa45; "{ae7e0cd9-0faa-459c-ba09-d141c4b3d06e}"
0x1800197dd  mov     [rsp+58h+samDesired], 4Eh ; 'N'; cbData
0x1800197e5  lea     rdx, ValueName; "CLSID"
0x1800197ec  mov     r9d, 1; dwType
0x1800197f2  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800197f7  xor     r8d, r8d; Reserved
0x1800197fa  call    cs:__imp_RegSetValueExW
0x180019800  test    eax, eax
0x180019802  jz      short loc_18001980B
0x180019804  mov     edx, 4Fh ; 'O'
0x180019809  jmp     short loc_18001987D
0x18001980b  mov     rcx, [rsp+58h+hKey]; hKey
0x180019810  lea     rax, byte_180117A88
0x180019817  mov     [rsp+58h+samDesired], 4; cbData
0x18001981f  lea     rdx, aEvents; "Events"
0x180019826  mov     r9d, 4; dwType
0x18001982c  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180019831  xor     r8d, r8d; Reserved
0x180019834  call    cs:__imp_RegSetValueExW
0x18001983a  test    eax, eax
0x18001983c  jz      short loc_180019845
0x18001983e  mov     edx, 52h ; 'R'
0x180019843  jmp     short loc_18001987D
0x180019845  mov     rcx, [rsp+58h+hKey]; hKey
0x18001984a  lea     rax, byte_180117A8C
0x180019851  mov     [rsp+58h+samDesired], 4; cbData
0x180019859  lea     rdx, aFlags; "Flags"
0x180019860  mov     r9d, 4; dwType
0x180019866  mov     qword ptr [rsp+58h+dwOptions], rax; unsigned int
0x18001986b  xor     r8d, r8d; Reserved
0x18001986e  call    cs:__imp_RegSetValueExW
0x180019874  test    eax, eax
0x180019876  jz      short loc_1800198A1
0x180019878  mov     edx, 55h ; 'U'; void *
0x18001987d  mov     rcx, [rsp+58h]; this
0x180019882  lea     r8, aOnecoreDsSecur_90; "onecore\\ds\\security\\umstartup\\candi"...
0x180019889  mov     r9d, eax; char *
0x18001988c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180019891  lea     rcx, [rsp+58h+hKey]
0x180019896  mov     ebx, eax
0x180019898  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001989d  mov     eax, ebx
0x18001989f  jmp     short loc_1800198AD
0x1800198a1  lea     rcx, [rsp+58h+hKey]
0x1800198a6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800198ab  xor     eax, eax
0x1800198ad  add     rsp, 50h
0x1800198b1  pop     rbx
0x1800198b2  retn
```
