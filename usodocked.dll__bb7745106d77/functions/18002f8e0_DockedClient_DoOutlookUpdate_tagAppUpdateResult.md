# DockedClient::DoOutlookUpdate(tagAppUpdateResult *)

- ea: `0x18002f8e0`
- end: `0x180030193`
- name: `?DoOutlookUpdate@DockedClient@@UEAAJPEAUtagAppUpdateResult@@@Z`
- size: `2227`
- prototype: `__int64 __fastcall(DockedClient *__hidden this, struct tagAppUpdateResult *)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x1800183f4`
- `0x18001ba70`
- `0x18001ee04`
- `0x180026a98`
- `0x180028394`
- `0x18002a048`
- `0x18002a0c0`
- `0x18002f8e0`
- `0x180031f7c`
- `0x1800328f0`
- `0x180032dd0`
- `0x180033b78`
- `0x180035764`
- `0x180035ebc`
- `0x180037224`
- `0x18003738c`
- `0x18003a228`
- `0x18003aa30`
- `0x18003bf74`
- `0x1800446a0`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18002fbbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18002fbbe`

## string_xrefs

- `0x18002f931`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x18002fa3f`: `OutlookUpdateTimeoutMins`
- `0x18002fcb4`: `https://go.microsoft.com/fwlink/?linkid=2195164`
- `0x18002fbed`: `https://go.microsoft.com/fwlink/?linkid=2195278`
- `0x18002fbff`: `https://go.microsoft.com/fwlink/?linkid=2195438`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall DockedClient::DoOutlookUpdate(DockedClient *this, struct tagAppUpdateResult *a2)
{
  int v3; // r15d
  int v4; // edi
  __int64 result; // rax
  __int64 v6; // rdx
  DockedClient *v7; // rcx
  _DWORD *v8; // rax
  __int64 v9; // rcx
  bool v10; // zf
  char v11; // bl
  char v12; // r12
  __int64 v13; // rdx
  const wchar_t *v14; // rax
  const char *v15; // r9
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rbx
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  int v20; // r15d
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  __int64 v22; // rax
  int v23; // r13d
  __int64 *v24; // rcx
  __int64 v25; // rdx
  char v26; // r15
  volatile signed __int32 *v27; // rbx
  volatile signed __int32 *v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rbx
  int v31; // ebx
  int v32; // eax
  int v33; // [rsp+20h] [rbp-1C8h]
  char v34; // [rsp+30h] [rbp-1B8h]
  char v35; // [rsp+31h] [rbp-1B7h]
  int v36; // [rsp+38h] [rbp-1B0h] BYREF
  unsigned __int16 v37; // [rsp+3Ch] [rbp-1ACh]
  __int16 v38; // [rsp+3Eh] [rbp-1AAh]
  unsigned int v39; // [rsp+40h] [rbp-1A8h] BYREF
  unsigned int v40; // [rsp+44h] [rbp-1A4h]
  __int64 v41; // [rsp+48h] [rbp-1A0h]
  int v42; // [rsp+50h] [rbp-198h]
  __int64 v43; // [rsp+58h] [rbp-190h] BYREF
  int v44; // [rsp+60h] [rbp-188h]
  __int16 v45; // [rsp+64h] [rbp-184h]
  __int64 v46; // [rsp+68h] [rbp-180h] BYREF
  void *v47; // [rsp+70h] [rbp-178h] BYREF
  __int64 v48; // [rsp+78h] [rbp-170h] BYREF
  char v49; // [rsp+80h] [rbp-168h]
  __int16 v50; // [rsp+86h] [rbp-162h]
  int v51; // [rsp+90h] [rbp-158h]
  int v52; // [rsp+94h] [rbp-154h]
  _QWORD v53[2]; // [rsp+A0h] [rbp-148h] BYREF
  _QWORD v54[2]; // [rsp+B0h] [rbp-138h] BYREF
  _QWORD v55[2]; // [rsp+C0h] [rbp-128h] BYREF
  __int128 v56; // [rsp+D0h] [rbp-118h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-108h]
  __int64 v58; // [rsp+E8h] [rbp-100h]
  _SYSTEM_INFO SystemInfo; // [rsp+F0h] [rbp-F8h] BYREF
  _BYTE v60[96]; // [rsp+120h] [rbp-C8h] BYREF
  volatile signed __int32 *v61; // [rsp+180h] [rbp-68h]
  _BYTE v62[40]; // [rsp+188h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v3 = (int)this;
  v54[1] = a2;
  v4 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)0x80004003LL,
      v33);
    return 2147500035LL;
  }
  LODWORD(v53[0]) = -1;
  v51 = -1;
  v52 = 0;
  v39 = 0;
  v40 = 0;
  v34 = 0;
  try
  {
    ((void (*)(void))wil::details::FeatureImpl<__WilFeatureTraits_Feature_OutlookInstall>::ReportUsage)();
    v41 = 0;
    v43 = 0;
    if ( Windows::Configuration::IsCTA((Windows::Configuration *)v54) || DockedClient::IsAutoInstallBlockedForSku(v7) )
    {
      v23 = 0;
      v29 = 0;
      v41 = 0;
      v36 = 1;
      v26 = 0;
      v12 = 0;
      v42 = 0;
      v43 = 0;
      v44 = 1;
      v45 = 0;
LABEL_62:
      if ( v12 || (v35 = 0, !v26) )
        v35 = 1;
      v52 = v23;
      v30 = v29;
      v55[0] = v29;
      if ( v29 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
        v29 = v41;
      }
      if ( v29 )
      {
        v39 = *(_DWORD *)winrt::impl::consume_Windows_Management_Deployment_IDeploymentResult<winrt::Windows::Management::Deployment::IDeploymentResult>::ExtendedErrorCode(
                           v55,
                           &v39);
        v40 = v39;
        v30 = v55[0];
      }
      if ( v30 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v55);
      if ( v41 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v43);
      v31 = v53[0];
      if ( v35 )
      {
        v32 = 1;
      }
      else
      {
        v6 = v39;
        v32 = 0;
      }
      *(_DWORD *)a2 = v32;
      LOBYTE(v6) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_OutlookInstall>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_OutlookInstall>::GetImpl'::`2'::impl,
        v6,
        0);
      *((_DWORD *)a2 + 1) = 1;
      *((_DWORD *)a2 + 2) = v31;
      *((_DWORD *)a2 + 3) = v12 != 0;
      *((_DWORD *)a2 + 4) = v26 != 0;
      *((_DWORD *)a2 + 5) = v36;
      *((_DWORD *)a2 + 6) = v23;
      *((_DWORD *)a2 + 7) = v39;
      LOBYTE(v4) = v34 != 0;
      *((_DWORD *)a2 + 8) = v4;
      return 0;
    }
    v8 = operator new(0x18u);
    v8[2] = 1;
    v8[3] = 1;
    *(_QWORD *)v8 = &std::_Ref_count_obj2<Windows::Network>::`vftable';
    *((_QWORD *)v8 + 2) = &Windows::Registry::`vftable';
    v47 = v8 + 4;
    v48 = (__int64)v8;
    v56 = 0;
    Windows::Settings::Settings(v60, &v47, 0);
    v36 = 15;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v56, L"OutlookUpdateTimeoutMins", 24);
    v54[0] = 60LL * (int)Windows::Settings::GetSettingOrDefault(v60, &v56, &v36);
    std::wstring::_Tidy_deallocate(&v56);
    winrt::Windows::Management::Deployment::PackageManager::PackageManager((winrt::Windows::Management::Deployment::PackageManager *)v55);
    v9 = v55[0];
    v46 = v55[0];
    if ( v55[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v55[0] + 8LL))(v55[0]);
    *(_QWORD *)&v56 = L"Microsoft.OutlookForWindows_8wekyb3d8bbwe";
    *((_QWORD *)&v56 + 1) = 41;
    DockedClient::GetProvisionedPackageVersion(v9, &v36, &v46, &v56);
    if ( (_WORD)v36 )
    {
      if ( (_WORD)v36 != 1 )
        goto LABEL_53;
      v10 = HIWORD(v36) == 0;
    }
    else
    {
      if ( __PAIR32__(HIWORD(v36), 0) != v37 )
        goto LABEL_53;
      v10 = v38 == 0;
    }
    if ( v10 )
    {
      v56 = 0;
      v57 = 0;
      v58 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v56, L"Microsoft.OutlookForWindows_8wekyb3d8bbwe", 41);
      v11 = IsPackageFamilyDeprovisioned(&v56);
      std::wstring::_Tidy_deallocate(&v56);
      if ( v11 )
      {
        DWORD1(v56) = 0;
        v36 = 8;
        HIWORD(v57) = 0;
        v44 = 8;
        v45 = 0;
        v12 = 0;
LABEL_54:
        v43 = 0;
        v42 = 0;
        v26 = 0;
        v41 = 0;
        v23 = 0;
LABEL_55:
        if ( v55[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v55);
        std::wstring::_Tidy_deallocate(v62);
        v28 = v61;
        if ( v61 )
        {
          if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
            if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
          }
        }
        v29 = v41;
        goto LABEL_62;
      }
      memset(&SystemInfo, 0, sizeof(SystemInfo));
      GetSystemInfo(&SystemInfo);
      if ( SystemInfo.wProcessorArchitecture == 9 )
      {
        v36 = 6;
      }
      else
      {
        v36 = 6;
        if ( SystemInfo.wProcessorArchitecture != 6 )
        {
          if ( SystemInfo.wProcessorArchitecture )
          {
            if ( SystemInfo.wProcessorArchitecture != 12 )
            {
              *(_DWORD *)a2 = 1;
              LOBYTE(v13) = 1;
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(
                `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl'::`2'::impl,
                v13,
                0);
              *((_DWORD *)a2 + 1) = 1;
              *((_DWORD *)a2 + 2) = -1;
              *(_QWORD *)((char *)a2 + 12) = 0;
              *(_QWORD *)((char *)a2 + 20) = 4;
              *(_QWORD *)((char *)a2 + 28) = 0;
              if ( v55[0] )
                winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v55);
              std::wstring::_Tidy_deallocate(v62);
              v16 = v61;
              if ( v61 )
              {
                if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
                  if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
                }
              }
              return 0;
            }
            v14 = L"https://go.microsoft.com/fwlink/?linkid=2195438";
          }
          else
          {
            v14 = L"https://go.microsoft.com/fwlink/?linkid=2195278";
          }
          goto LABEL_31;
        }
      }
      v14 = L"https://go.microsoft.com/fwlink/?linkid=2195164";
LABEL_31:
      v34 = 1;
      v47 = (void *)v14;
      v48 = 47;
      v46 = v55[0];
      if ( v55[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v55[0] + 8LL))(v55[0]);
      v53[0] = L"Microsoft.OutlookForWindows_8wekyb3d8bbwe";
      v53[1] = 41;
      DockedClient::InstallAppForAllUsers(v3, (unsigned int)&v56, (unsigned int)&v46, (unsigned int)&v47, (__int64)v53);
      v53[0] = &v56;
      v47 = operator new(0x120u);
      v17 = std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_d4c478d726bd5691ef5b15af026db0d1_____(
              v47,
              v53);
      v18 = v17;
      v47 = (void *)v17;
      LOBYTE(v48) = 0;
      v49 = 0;
      if ( !v17 )
        std::_Throw_future_error2(4);
      v47 = (void *)v17;
      LOBYTE(v48) = 1;
      _InterlockedAdd((volatile signed __int32 *)(v17 + 8), 1u);
      if ( !_InterlockedDecrement((volatile signed __int32 *)(v17 + 8)) )
      {
        v19 = *(void (__fastcall ****)(_QWORD, __int64))(v17 + 200);
        if ( v19 )
          (**v19)(v19, v17);
        else
          (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
      }
      if ( *(_BYTE *)(v18 + 184) )
        std::_Throw_future_error2(4);
      v20 = std::_Associated_state<int>::_Wait_for<__int64,std::ratio<1,1>>(v18, v54);
      LODWORD(v53[0]) = v20;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 + 8), 0xFFFFFFFF) == 1 )
      {
        v21 = *(void (__fastcall ****)(_QWORD, __int64))(v18 + 200);
        if ( v21 )
          (**v21)(v21, v18);
        else
          (**(void (__fastcall ***)(__int64, __int64))v18)(v18, 1);
      }
      v51 = v20;
      if ( v20 )
      {
        v23 = 0;
        HIDWORD(v47) = 0;
        v41 = 0;
        v26 = 1;
        v12 = 0;
        v50 = 0;
        v42 = 0;
        v43 = 0;
        v44 = 6;
        v45 = 1;
      }
      else
      {
        v22 = Concurrency::task<DockedClient::AppInstallResult>::get(&v56, &v47);
        v23 = *(_DWORD *)v22;
        v42 = *(_DWORD *)v22;
        v24 = (__int64 *)(v22 + 8);
        if ( &v43 != (__int64 *)(v22 + 8) )
        {
          v41 = *v24;
          v25 = v41;
          *v24 = 0;
          v43 = v25;
        }
        v36 = *(_DWORD *)(v22 + 16);
        v44 = v36;
        v26 = *(_BYTE *)(v22 + 20);
        LOBYTE(v45) = v26;
        v12 = *(_BYTE *)(v22 + 21);
        HIBYTE(v45) = v12;
        if ( v48 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
      }
      v27 = (volatile signed __int32 *)*((_QWORD *)&v56 + 1);
      if ( *((_QWORD *)&v56 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v56 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      goto LABEL_55;
    }
LABEL_53:
    DWORD1(v56) = 0;
    v36 = 0;
    v12 = 1;
    HIWORD(v57) = 0;
    v44 = 0;
    v45 = 256;
    goto LABEL_54;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x363,
                           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\d"
                                         "ll\\dockedclient.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18002f8e0  mov     [rsp+arg_10], rbx
0x18002f8e5  mov     [rsp+arg_18], rsi
0x18002f8ea  push    rdi
0x18002f8eb  push    r12
0x18002f8ed  push    r13
0x18002f8ef  push    r14
0x18002f8f1  push    r15
0x18002f8f3  sub     rsp, 1C0h
0x18002f8fa  mov     rax, cs:__security_cookie
0x18002f901  xor     rax, rsp
0x18002f904  mov     [rsp+1E8h+var_38], rax
0x18002f90c  mov     rsi, rdx
0x18002f90f  mov     r15, rcx
0x18002f912  mov     [rsp+1E8h+var_130], rdx
0x18002f91a  xor     edi, edi
0x18002f91c  test    rdx, rdx
0x18002f91f  jnz     short loc_18002F949
0x18002f921  mov     rcx, [rsp+1E8h]; this
0x18002f929  mov     ebx, 80004003h
0x18002f92e  mov     r9d, ebx; char *
0x18002f931  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002f938  mov     edx, 2DBh; void *
0x18002f93d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f942  mov     eax, ebx
0x18002f944  jmp     loc_180030151
0x18002f949  or      r12d, 0FFFFFFFFh
0x18002f94d  mov     eax, r12d
0x18002f950  mov     dword ptr [rsp+1E8h+var_148], eax
0x18002f957  mov     [rsp+1E8h+var_158], eax
0x18002f95e  mov     [rsp+1E8h+var_154], edi
0x18002f965  mov     eax, edi
0x18002f967  mov     [rsp+1E8h+var_1A8], eax
0x18002f96b  mov     [rsp+1E8h+var_1A4], eax
0x18002f96f  mov     al, dil
0x18002f972  mov     [rsp+1E8h+var_1B8], al
0x18002f976  mov     [rsp+1E8h+var_1B6], al
0x18002f97a  mov     r8b, 3
0x18002f97d  lea     r14d, [r12+2]
0x18002f982  mov     dl, r14b
0x18002f985  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OutlookInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OutlookInstall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OutlookInstall> `wil::Feature<__WilFeatureTraits_Feature_OutlookInstall>::GetImpl(void)'::`2'::impl
0x18002f98c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OutlookInstall@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OutlookInstall>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002f991  nop
0x18002f992  mov     rdx, rdi
0x18002f995  mov     [rsp+1E8h+var_1A0], rdx
0x18002f99a  mov     [rsp+1E8h+var_190], rdx
0x18002f99f  lea     rcx, [rsp+1E8h+var_138]; this
0x18002f9a7  call    ?IsCTA@Configuration@Windows@@UEAA_NXZ; Windows::Configuration::IsCTA(void)
0x18002f9ac  test    al, al
0x18002f9ae  jnz     loc_180030071
0x18002f9b4  call    ?IsAutoInstallBlockedForSku@DockedClient@@AEAA_NXZ; DockedClient::IsAutoInstallBlockedForSku(void)
0x18002f9b9  test    al, al
0x18002f9bb  jnz     loc_180030071
0x18002f9c1  lea     ebx, [r12+19h]
0x18002f9c6  mov     ecx, ebx; Size
0x18002f9c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f9cd  mov     [rax+8], r14d
0x18002f9d1  mov     [rax+0Ch], r14d
0x18002f9d5  lea     rcx, ??_7?$_Ref_count_obj2@VNetwork@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Network>::`vftable'
0x18002f9dc  mov     [rax], rcx
0x18002f9df  lea     rcx, [rax+10h]
0x18002f9e3  lea     rdx, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x18002f9ea  mov     [rcx], rdx
0x18002f9ed  mov     qword ptr [rsp+1E8h+var_178], rcx
0x18002f9f2  mov     qword ptr [rsp+1E8h+var_178+8], rax
0x18002f9f7  xorps   xmm0, xmm0
0x18002f9fa  movdqu  [rsp+1E8h+var_118], xmm0
0x18002fa03  xor     r8d, r8d
0x18002fa06  lea     rdx, [rsp+1E8h+var_178]
0x18002fa0b  lea     rcx, [rsp+1E8h+var_C8]
0x18002fa13  call    ??0Settings@Windows@@QEAA@V?$shared_ptr@VRegistry@SystemInterface@@@std@@_N@Z; Windows::Settings::Settings(std::shared_ptr<SystemInterface::Registry>,bool)
0x18002fa18  nop
0x18002fa19  mov     [rsp+1E8h+var_1B0], 0Fh
0x18002fa21  xorps   xmm0, xmm0
0x18002fa24  movups  [rsp+1E8h+var_118], xmm0
0x18002fa2c  mov     [rsp+1E8h+var_108], rdi
0x18002fa34  mov     [rsp+1E8h+var_100], rdi
0x18002fa3c  mov     r8d, ebx
0x18002fa3f  lea     rdx, aOutlookupdatet; "OutlookUpdateTimeoutMins"
0x18002fa46  lea     rcx, [rsp+1E8h+var_118]
0x18002fa4e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002fa53  nop
0x18002fa54  lea     r8, [rsp+1E8h+var_1B0]
0x18002fa59  lea     rdx, [rsp+1E8h+var_118]
0x18002fa61  lea     rcx, [rsp+1E8h+var_C8]
0x18002fa69  call    ?GetSettingOrDefault@Settings@Windows@@UEAAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBI@Z; Windows::Settings::GetSettingOrDefault(std::wstring const &,uint const &)
0x18002fa6e  cdqe
0x18002fa70  imul    rcx, rax, 3Ch ; '<'
0x18002fa74  mov     [rsp+1E8h+var_138], rcx
0x18002fa7c  lea     rcx, [rsp+1E8h+var_118]
0x18002fa84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fa89  lea     rcx, [rsp+1E8h+var_128]; this
0x18002fa91  call    ??0PackageManager@Deployment@Management@Windows@winrt@@QEAA@XZ; winrt::Windows::Management::Deployment::PackageManager::PackageManager(void)
0x18002fa96  nop
0x18002fa97  mov     rcx, [rsp+1E8h+var_128]
0x18002fa9f  mov     [rsp+1E8h+var_180], rcx
0x18002faa4  test    rcx, rcx
0x18002faa7  jz      short loc_18002FAB5
0x18002faa9  mov     rax, [rcx]
0x18002faac  mov     rax, [rax+8]
0x18002fab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fab5  lea     r13, aMicrosoftOutlo; "Microsoft.OutlookForWindows_8wekyb3d8bb"...
0x18002fabc  mov     qword ptr [rsp+1E8h+var_118], r13
0x18002fac4  mov     ebx, 29h ; ')'
0x18002fac9  mov     qword ptr [rsp+1E8h+var_118+8], rbx
0x18002fad1  lea     r9, [rsp+1E8h+var_118]
0x18002fad9  lea     r8, [rsp+1E8h+var_180]
0x18002fade  lea     rdx, [rsp+1E8h+var_1B0]
0x18002fae3  call    ?GetProvisionedPackageVersion@DockedClient@@AEAA?AUPackageVersion@ApplicationModel@Windows@winrt@@UPackageManager@Deployment@Management@45@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; DockedClient::GetProvisionedPackageVersion(winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<ushort>)
0x18002fae8  cmp     word ptr [rsp+1E8h+var_1B0], di
0x18002faed  jnz     short loc_18002FB0C
0x18002faef  cmp     word ptr [rsp+1E8h+var_1B0+2], di
0x18002faf4  jnz     loc_18002FF23
0x18002fafa  cmp     [rsp+1E8h+var_1AC], di
0x18002faff  jnz     loc_18002FF23
0x18002fb05  cmp     [rsp+1E8h+var_1AA], di
0x18002fb0a  jmp     short loc_18002FB1D
0x18002fb0c  cmp     word ptr [rsp+1E8h+var_1B0], r14w
0x18002fb12  jnz     loc_18002FF23
0x18002fb18  cmp     word ptr [rsp+1E8h+var_1B0+2], di
0x18002fb1d  jnz     loc_18002FF23
0x18002fb23  xorps   xmm0, xmm0
0x18002fb26  movups  [rsp+1E8h+var_118], xmm0
0x18002fb2e  mov     [rsp+1E8h+var_108], rdi
0x18002fb36  mov     [rsp+1E8h+var_100], rdi
0x18002fb3e  mov     r8, rbx
0x18002fb41  mov     rdx, r13
0x18002fb44  lea     rcx, [rsp+1E8h+var_118]
0x18002fb4c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002fb51  nop
0x18002fb52  lea     rcx, [rsp+1E8h+var_118]
0x18002fb5a  call    ?IsPackageFamilyDeprovisioned@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsPackageFamilyDeprovisioned(std::wstring const &)
0x18002fb5f  mov     bl, al
0x18002fb61  lea     rcx, [rsp+1E8h+var_118]
0x18002fb69  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fb6e  test    bl, bl
0x18002fb70  jz      short loc_18002FB9B
0x18002fb72  xor     eax, eax
0x18002fb74  mov     dword ptr [rsp+1E8h+var_118+4], eax
0x18002fb7b  lea     ecx, [rax+8]
0x18002fb7e  mov     [rsp+1E8h+var_1B0], ecx
0x18002fb82  mov     word ptr [rsp+1E8h+var_108+6], ax
0x18002fb8a  mov     [rsp+1E8h+var_188], ecx
0x18002fb8e  mov     [rsp+1E8h+var_184], di
0x18002fb93  mov     r12b, dil
0x18002fb96  jmp     loc_18002FF4A
0x18002fb9b  xorps   xmm0, xmm0
0x18002fb9e  movups  xmmword ptr [rsp+1E8h+SystemInfo], xmm0
0x18002fba6  movups  xmmword ptr [rsp+1E8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002fbae  movups  xmmword ptr [rsp+1E8h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002fbb6  lea     rcx, [rsp+1E8h+SystemInfo]; lpSystemInfo
0x18002fbbe  call    cs:__imp_GetSystemInfo
0x18002fbc4  movzx   eax, word ptr [rsp+1E8h+SystemInfo]
0x18002fbcc  cmp     ax, 9
0x18002fbd0  jz      loc_18002FCAC
0x18002fbd6  mov     ecx, 6
0x18002fbdb  mov     [rsp+1E8h+var_1B0], ecx
0x18002fbdf  cmp     ax, cx
0x18002fbe2  jz      loc_18002FCB4
0x18002fbe8  test    ax, ax
0x18002fbeb  jnz     short loc_18002FBF9
0x18002fbed  lea     rax, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?linkid"...
0x18002fbf4  jmp     loc_18002FCBB
0x18002fbf9  cmp     ax, 0Ch
0x18002fbfd  jnz     short loc_18002FC0B
0x18002fbff  lea     rax, aHttpsGoMicroso_3; "https://go.microsoft.com/fwlink/?linkid"...
0x18002fc06  jmp     loc_18002FCBB
0x18002fc0b  mov     [rsi], r14d
0x18002fc0e  xor     r8d, r8d
0x18002fc11  mov     dl, r14b
0x18002fc14  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TFLHydrate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TFLHydrate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate> `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl(void)'::`2'::impl
0x18002fc1b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_TFLHydrate@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002fc20  mov     [rsi+4], r14d
0x18002fc24  mov     dword ptr [rsi+8], 0FFFFFFFFh
0x18002fc2b  mov     [rsi+0Ch], rdi
0x18002fc2f  mov     qword ptr [rsi+14h], 4
0x18002fc37  mov     [rsi+1Ch], rdi
0x18002fc3b  cmp     [rsp+1E8h+var_128], rdi
0x18002fc43  jz      short loc_18002FC53
0x18002fc45  lea     rcx, [rsp+1E8h+var_128]
0x18002fc4d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002fc52  nop
0x18002fc53  lea     rcx, [rsp+1E8h+var_60]
0x18002fc5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002fc60  mov     rbx, [rsp+1E8h+var_68]
0x18002fc68  test    rbx, rbx
0x18002fc6b  jz      short loc_18002FCA5
0x18002fc6d  mov     eax, r12d
0x18002fc70  lock xadd [rbx+8], eax
0x18002fc75  add     eax, r12d
0x18002fc78  jnz     short loc_18002FCA5
0x18002fc7a  mov     rax, [rbx]
0x18002fc7d  mov     rcx, rbx
0x18002fc80  mov     rax, [rax]
0x18002fc83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc88  mov     eax, r12d
0x18002fc8b  lock xadd [rbx+0Ch], eax
0x18002fc90  add     eax, r12d
0x18002fc93  jnz     short loc_18002FCA5
0x18002fc95  mov     rax, [rbx]
0x18002fc98  mov     rcx, rbx
0x18002fc9b  mov     rax, [rax+8]
0x18002fc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fca4  nop
0x18002fca5  xor     eax, eax
0x18002fca7  jmp     loc_180030151
0x18002fcac  mov     [rsp+1E8h+var_1B0], 6
0x18002fcb4  lea     rax, aHttpsGoMicroso_0; "https://go.microsoft.com/fwlink/?linkid"...
0x18002fcbb  mov     cl, r14b
0x18002fcbe  mov     [rsp+1E8h+var_1B8], cl
0x18002fcc2  mov     [rsp+1E8h+var_1B6], cl
0x18002fcc6  mov     qword ptr [rsp+1E8h+var_178], rax
0x18002fccb  mov     qword ptr [rsp+1E8h+var_178+8], 2Fh ; '/'
0x18002fcd4  mov     rcx, [rsp+1E8h+var_128]
0x18002fcdc  mov     [rsp+1E8h+var_180], rcx
0x18002fce1  test    rcx, rcx
0x18002fce4  jz      short loc_18002FCF2
0x18002fce6  mov     rax, [rcx]
0x18002fce9  mov     rax, [rax+8]
0x18002fced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcf2  mov     [rsp+1E8h+var_148], r13
0x18002fcfa  mov     [rsp+1E8h+var_140], 29h ; ')'
0x18002fd06  movups  xmm0, [rsp+1E8h+var_178]
0x18002fd0b  movdqu  [rsp+1E8h+var_178], xmm0
0x18002fd11  lea     rax, [rsp+1E8h+var_148]
0x18002fd19  mov     qword ptr [rsp+1E8h+var_1C8], rax
0x18002fd1e  lea     r9, [rsp+1E8h+var_178]
0x18002fd23  lea     r8, [rsp+1E8h+var_180]
0x18002fd28  lea     rdx, [rsp+1E8h+var_118]
0x18002fd30  mov     rcx, r15
0x18002fd33  call    ?InstallAppForAllUsers@DockedClient@@AEAA?AV?$task@UAppInstallResult@DockedClient@@@Concurrency@@UPackageManager@Deployment@Management@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@1@Z; DockedClient::InstallAppForAllUsers(winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x18002fd38  nop
0x18002fd39  lea     rax, [rsp+1E8h+var_118]
0x18002fd41  mov     [rsp+1E8h+var_148], rax
0x18002fd49  mov     ecx, 120h; Size
0x18002fd4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fd53  mov     qword ptr [rsp+1E8h+var_178], rax
0x18002fd58  lea     rdx, [rsp+1E8h+var_148]
0x18002fd60  mov     rcx, rax
0x18002fd63  call    std___Task_async_state_void____Task_async_state_void__std___Fake_no_copy_callable_adapter__lambda_d4c478d726bd5691ef5b15af026db0d1_____
0x18002fd68  mov     rbx, rax
0x18002fd6b  mov     qword ptr [rsp+1E8h+var_178], rax
0x18002fd70  mov     byte ptr [rsp+1E8h+var_178+8], dil
0x18002fd75  mov     [rsp+1E8h+var_168], dil
0x18002fd7d  test    rax, rax
0x18002fd80  jz      loc_18003017E
0x18002fd86  mov     qword ptr [rsp+1E8h+var_178], rbx
0x18002fd8b  mov     byte ptr [rsp+1E8h+var_178+8], r14b
0x18002fd90  lock add [rax+8], r14d
0x18002fd95  mov     eax, r12d
0x18002fd98  lock xadd [rbx+8], eax
0x18002fd9d  add     eax, r12d
0x18002fda0  jnz     short loc_18002FDD0
0x18002fda2  mov     rcx, [rbx+0C8h]
0x18002fda9  test    rcx, rcx
0x18002fdac  jz      short loc_18002FDBE
0x18002fdae  mov     rax, [rcx]
0x18002fdb1  mov     rdx, rbx
0x18002fdb4  mov     rax, [rax]
0x18002fdb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdbc  jmp     short loc_18002FDD0
0x18002fdbe  mov     rax, [rbx]
0x18002fdc1  mov     edx, r14d
0x18002fdc4  mov     rcx, rbx
0x18002fdc7  mov     rax, [rax]
0x18002fdca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdcf  nop
0x18002fdd0  cmp     [rbx+0B8h], dil
0x18002fdd7  jnz     loc_180030187
0x18002fddd  lea     rdx, [rsp+1E8h+var_138]
0x18002fde5  mov     rcx, rbx
0x18002fde8  call    ??$_Wait_for@_JU?$ratio@$00$00@std@@@?$_Associated_state@H@std@@QEAA?AW4future_status@1@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@1@@Z; std::_Associated_state<int>::_Wait_for<__int64,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,1>> const &)
0x18002fded  mov     r15d, eax
0x18002fdf0  mov     dword ptr [rsp+1E8h+var_148], eax
0x18002fdf7  mov     ecx, r12d
0x18002fdfa  lock xadd [rbx+8], ecx
0x18002fdff  add     ecx, r12d
0x18002fe02  jnz     short loc_18002FE31
0x18002fe04  mov     rcx, [rbx+0C8h]
0x18002fe0b  test    rcx, rcx
0x18002fe0e  jz      short loc_18002FE20
0x18002fe10  mov     rax, [rcx]
0x18002fe13  mov     rdx, rbx
0x18002fe16  mov     rax, [rax]
0x18002fe19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe1e  jmp     short loc_18002FE31
0x18002fe20  mov     rax, [rbx]
0x18002fe23  mov     edx, r14d
0x18002fe26  mov     rcx, rbx
0x18002fe29  mov     rax, [rax]
0x18002fe2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe31  mov     [rsp+1E8h+var_158], r15d
0x18002fe39  test    r15d, r15d
0x18002fe3c  jnz     short loc_18002FEA6
0x18002fe3e  lea     rdx, [rsp+1E8h+var_178]
0x18002fe43  lea     rcx, [rsp+1E8h+var_118]
0x18002fe4b  call    ?get@?$task@UAppInstallResult@DockedClient@@@Concurrency@@QEBA?AUAppInstallResult@DockedClient@@XZ; Concurrency::task<DockedClient::AppInstallResult>::get(void)
0x18002fe50  mov     r13d, [rax]
0x18002fe53  mov     [rsp+1E8h+var_198], r13d
0x18002fe58  lea     rcx, [rax+8]
0x18002fe5c  lea     rdx, [rsp+1E8h+var_190]
  ... truncated ...
```
