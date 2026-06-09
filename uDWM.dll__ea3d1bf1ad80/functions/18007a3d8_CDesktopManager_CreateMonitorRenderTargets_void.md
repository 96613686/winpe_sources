# CDesktopManager::CreateMonitorRenderTargets(void)

- ea: `0x18007a3d8`
- end: `0x18007b18e`
- name: `?CreateMonitorRenderTargets@CDesktopManager@@AEAAJXZ`
- size: `3510`
- prototype: `__int64 __fastcall(CDesktopManager *__hidden this)`
- caller_count: `2`
- callee_count: `41`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800757e0`
- `0x180077154`

## callees

- `0x1800028d4`
- `0x1800028f4`
- `0x180004714`
- `0x180009e5c`
- `0x18000e960`
- `0x18000e98c`
- `0x18001f43c`
- `0x18003a338`
- `0x18003cf94`
- `0x1800430f4`
- `0x180044ec0`
- `0x1800514f0`
- `0x1800517fc`
- `0x18005467c`
- `0x18005da70`
- `0x18005f000`
- `0x18005f888`
- `0x18005fbe0`
- `0x18006ad98`
- `0x18006b628`
- `0x18006c36c`
- `0x18006e9a0`
- `0x18006eb90`
- `0x180070548`
- `0x180071304`
- `0x180077be4`
- `0x18007a3cc`
- `0x18007a3d8`
- `0x18007b288`
- `0x18007ee5c`
- `0x180087d58`
- `0x18008c760`
- `0x180095130`
- `0x180096008`
- `0x1800ab1dc`
- `0x1800adbf8`
- `0x1800afdac`
- `0x1800b119c`
- `0x1800b7948`
- `0x1800dc988`
- `0x1800ea010`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18007a525`
- `USER32!SystemParametersInfoW` at `0x18007a525`
- `USER32!GetDesktopID` at `0x18007a4b8`
- `USER32!GetDesktopID` at `0x18007a4b8`
- `win32u!NtDCompositionCreateSynchronizationObject` at `0x18007aefd`
- `win32u!NtDCompositionCreateSynchronizationObject` at `0x18007aefd`
- `win32u!NtDCompositionCommitSynchronizationObject` at `0x18007b055`
- `win32u!NtDCompositionCommitSynchronizationObject` at `0x18007b055`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CDesktopManager::CreateMonitorRenderTargets(CDWMDXGIEnumeration **this)
{
  int v2; // eax
  unsigned int v3; // ebx
  int AllDisplaysNoRef; // eax
  CDWMDisplaySet *v5; // r15
  CDWMDXGIEnumeration *v6; // rax
  unsigned int HasChanged; // ebx
  int v8; // eax
  CDisplayAnimatedVisual *v9; // rbx
  int v10; // eax
  int v11; // eax
  unsigned int v12; // r12d
  __int64 v13; // rcx
  __int64 v14; // rdi
  char v15; // dl
  __int64 v16; // rax
  __int64 v17; // r13
  struct IDCompositionRenderTargetPartner *v18; // rsi
  CDWMDisplay *v19; // rcx
  int v20; // eax
  __int64 (__fastcall **v21)(struct IDCompositionRenderTargetPartner *, GUID *, __int64); // rbx
  __int64 v22; // rax
  int v23; // eax
  __int64 (__fastcall *v24)(__int64, _QWORD, CDWMDisplaySet **); // r10
  int v25; // eax
  int v26; // eax
  int v27; // r13d
  unsigned int v28; // r13d
  __int64 v29; // rcx
  __int64 v30; // rsi
  CCompositor *v31; // rcx
  int v32; // eax
  CDDisplayManager *v33; // rbx
  int SourceHandleForTarget; // eax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, void *, _QWORD, _QWORD); // rbx
  int v37; // eax
  int v38; // eax
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, _QWORD, _QWORD, _QWORD); // rbx
  int v41; // eax
  int v42; // eax
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v44)(_QWORD, GUID *, __int64); // rbx
  __int64 v45; // rax
  int v46; // eax
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, _QWORD, struct IDCompositionRenderTargetPartner **); // rbx
  int v49; // eax
  int v50; // eax
  struct IDCompositionRenderTargetPartner *v51; // rdi
  __int64 (__fastcall *v52)(struct IDCompositionRenderTargetPartner *, GUID *, __int64); // rbx
  __int64 v53; // rax
  int v54; // eax
  __int64 (__fastcall *v55)(CDWMDisplaySet *, _QWORD, float *); // r10
  int v56; // eax
  __int64 (__fastcall *v57)(struct IDCompositionRenderTargetPartner *, _QWORD, __int128 *); // r10
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // ebx
  int v62; // r9d
  int v63; // eax
  int v64; // eax
  int *v66; // [rsp+20h] [rbp-E0h]
  unsigned int v67; // [rsp+20h] [rbp-E0h]
  struct IDCompositionRenderTargetPartner *v68; // [rsp+60h] [rbp-A0h] BYREF
  char v69; // [rsp+68h] [rbp-98h]
  unsigned int v70; // [rsp+6Ch] [rbp-94h] BYREF
  BOOL IsWarpAdapterLuid; // [rsp+70h] [rbp-90h]
  int v72; // [rsp+74h] [rbp-8Ch]
  void *v73; // [rsp+78h] [rbp-88h] BYREF
  int pvParam; // [rsp+80h] [rbp-80h] BYREF
  int v75; // [rsp+84h] [rbp-7Ch] BYREF
  int v76; // [rsp+88h] [rbp-78h] BYREF
  __int128 v77; // [rsp+90h] [rbp-70h] BYREF
  __int64 v78; // [rsp+A0h] [rbp-60h]
  __int64 v79; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v80; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v81; // [rsp+C0h] [rbp-40h]
  unsigned int v82; // [rsp+C8h] [rbp-38h]
  CDWMDisplaySet *v83; // [rsp+D0h] [rbp-30h] BYREF
  float v84; // [rsp+D8h] [rbp-28h]
  float v85; // [rsp+DCh] [rbp-24h]
  void *v86; // [rsp+E0h] [rbp-20h] BYREF
  float v87; // [rsp+E8h] [rbp-18h]
  float v88; // [rsp+ECh] [rbp-14h]
  int v89[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v90; // [rsp+F8h] [rbp-8h]
  int v91; // [rsp+FCh] [rbp-4h]
  __int128 v92; // [rsp+100h] [rbp+0h] BYREF
  __int64 v93; // [rsp+110h] [rbp+10h]
  unsigned int v94; // [rsp+118h] [rbp+18h]
  int v95; // [rsp+120h] [rbp+20h]
  int v96; // [rsp+124h] [rbp+24h]
  int v97; // [rsp+128h] [rbp+28h]
  int v98; // [rsp+12Ch] [rbp+2Ch]
  int v99; // [rsp+130h] [rbp+30h]
  int v100; // [rsp+134h] [rbp+34h]
  int v101; // [rsp+138h] [rbp+38h]
  int v102; // [rsp+13Ch] [rbp+3Ch]
  float v103[4]; // [rsp+140h] [rbp+40h] BYREF
  _DWORD v104[4]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v83 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v76 = 0;
  v75 = 0;
  v73 = 0;
  v2 = CDesktopManager::EnumerateMonitors((CDesktopManager *)this, &v83);
  v3 = v2;
  if ( v2 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x451u, 0);
    goto LABEL_121;
  }
  AllDisplaysNoRef = CDWMDisplaySet::GetAllDisplaysNoRef(this[18], &v80);
  v3 = AllDisplaysNoRef;
  if ( AllDisplaysNoRef < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, AllDisplaysNoRef, 0x453u, 0);
LABEL_121:
    v5 = v83;
    goto LABEL_122;
  }
  LOBYTE(v72) = 0;
  v69 = 0;
  LOBYTE(IsWarpAdapterLuid) = 0;
  v5 = v83;
  if ( v83 )
  {
    v92 = 0;
    v93 = 0;
    v94 = 0;
    if ( CDWMDisplaySet::IsEquivalentRotated(this[18], v83) )
    {
      CDWMDisplaySet::CalculateRotationAngles(v5, this[18], &v76, &v75);
      v69 = 1;
    }
    v83 = 0;
    GetDesktopID(1, &v83);
    if ( !CDesktopManager::IsLogonDesktop((unsigned __int64)v83) )
    {
      if ( (unsigned __int8)IsOpenThemeDataPresent() )
      {
        v6 = this[22];
        if ( v6 )
        {
          if ( *((_BYTE *)v6 + 120) )
          {
            if ( *((_BYTE *)CDesktopManager::s_pDesktopManagerInstance + 23) )
            {
              if ( !CDesktopManager::s_forceDisableModeChangeAnimation )
              {
                pvParam = 0;
                if ( SystemParametersInfoW(0xAAu, 0, &pvParam, 0) )
                {
                  if ( !pvParam )
                  {
                    v77 = 0;
                    v78 = 0;
                    HasChanged = CDisplayModeChangeHelper::HasChanged(v5, this[18]);
                    if ( HasChanged )
                    {
                      v68 = 0;
                      wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(&v68);
                      v8 = CDisplayModeChangeHelper::CreateDisplayAnimatedVisual(HasChanged, &v68);
                      v3 = v8;
                      if ( v8 < 0 )
                      {
                        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x48Bu, 0);
LABEL_19:
                        wil::com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>::~com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>(&v68);
                        if ( (_QWORD)v77 )
                        {
                          std::_Deallocate<16>(v77, (v78 - v77) & 0xFFFFFFFFFFFFFFF8uLL);
                          v77 = 0;
                          v78 = 0;
                        }
                        goto LABEL_21;
                      }
                      v9 = v68;
                      CWindowList::StopAndSetDisplayAnimatedVisual(this[53], v68);
                      if ( v9 )
                      {
                        CDisplayAnimatedVisual::SetChangeContextInfo(v9, v5, &v77);
                        v10 = CDisplayAnimatedVisual::Start(v9);
                        v3 = v10;
                        if ( v10 < 0 )
                        {
                          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0x492u, 0);
                          goto LABEL_19;
                        }
                      }
                      wil::com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>::~com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>(&v68);
                    }
                    if ( (_QWORD)v77 )
                    {
                      std::_Deallocate<16>(v77, (v78 - v77) & 0xFFFFFFFFFFFFFFF8uLL);
                      v77 = 0;
                      v78 = 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v11 = CDWMDisplaySet::GetAllDisplaysNoRef(v5, &v92);
    v3 = v11;
    if ( v11 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v11, 0x498u, 0);
LABEL_21:
      CBitmapSourceArray::~CBitmapSourceArray((CBitmapSourceArray *)&v92);
      goto LABEL_122;
    }
    v12 = 0;
    if ( v82 )
    {
      v13 = v80;
      do
      {
        v14 = *(_QWORD *)(v13 + 8LL * v12);
        v15 = 0;
        v16 = 0;
        v70 = 0;
        if ( v94 )
        {
          while ( !v15 )
          {
            v17 = *(_QWORD *)(v92 + 8 * v16);
            v18 = *(struct IDCompositionRenderTargetPartner **)(v17 + 8);
            if ( v18
              && *(_DWORD *)(v14 + 188) == *(_DWORD *)(v17 + 188)
              && *(_DWORD *)(v14 + 236) == *(_DWORD *)(v17 + 236)
              && *(_DWORD *)(v14 + 252) == *(_DWORD *)(v17 + 252)
              && *(_BYTE *)(v14 + 291) == *(_BYTE *)(v17 + 291)
              && !CDWMDisplay::IsTsDisplay((CDWMDisplay *)v14) )
            {
              CDWMDisplay::SetDcompTarget(v19, v18);
              CDWMDisplay::SetDcompTarget((CDWMDisplay *)v17, 0);
              if ( *(_BYTE *)(v14 + 292) )
              {
                v20 = (*(__int64 (__fastcall **)(struct IDCompositionRenderTargetPartner *))(*(_QWORD *)v18 + 40LL))(v18);
                v3 = v20;
                if ( v20 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v20, 0x4B5u, 0);
LABEL_61:
                  CBitmapSourceArray::~CBitmapSourceArray((CBitmapSourceArray *)&v92);
                  goto LABEL_117;
                }
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopDWMCursor>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopDWMCursor>::GetImpl'::`2'::impl) )
              {
                v21 = *(__int64 (__fastcall ***)(struct IDCompositionRenderTargetPartner *, GUID *, __int64))v18;
                v79 = 0;
                v22 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>>(&v79);
                v23 = (*v21)(v18, &GUID_fd1a8dfc_09ad_422c_abf4_bad2e71c68ad, v22);
                if ( v23 < 0 )
                  wil::details::in1diag3::_FailFast_Hr(
                    retaddr,
                    (void *)0x4BB,
                    (unsigned int)"clientcore\\windows\\dwm\\udwm\\desktopmanager.cpp",
                    (const char *)(unsigned int)v23,
                    (int)v66);
                v24 = *(__int64 (__fastcall **)(__int64, _QWORD, CDWMDisplaySet **))(*(_QWORD *)v79 + 56LL);
                v95 = *(_DWORD *)(v14 + 40);
                v96 = *(_DWORD *)(v14 + 44);
                v97 = *(_DWORD *)(v14 + 48);
                v98 = *(_DWORD *)(v14 + 52);
                *(float *)&v83 = (float)*(int *)(v14 + 56);
                *((float *)&v83 + 1) = (float)*(int *)(v14 + 60);
                v84 = (float)*(int *)(v14 + 64);
                v85 = (float)*(int *)(v14 + 68);
                LODWORD(v66) = *(_DWORD *)(v14 + 260);
                v25 = v24(v79, *(_QWORD *)(*(_QWORD *)(v14 + 88) + 16LL), &v83);
                v3 = v25;
                if ( v25 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v25, 0x4C1u, 0);
                  Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>::InternalRelease(&v79);
                  goto LABEL_61;
                }
                Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>::InternalRelease(&v79);
              }
              else
              {
                v89[0] = *(_DWORD *)(v14 + 40);
                v89[1] = *(_DWORD *)(v14 + 44);
                v90 = *(_DWORD *)(v14 + 48);
                v91 = *(_DWORD *)(v14 + 52);
                *(float *)&v86 = (float)*(int *)(v14 + 56);
                *((float *)&v86 + 1) = (float)*(int *)(v14 + 60);
                v87 = (float)*(int *)(v14 + 64);
                v88 = (float)*(int *)(v14 + 68);
                v66 = v89;
                v26 = (*(__int64 (__fastcall **)(struct IDCompositionRenderTargetPartner *, _QWORD, void **))(*(_QWORD *)v18 + 32LL))(
                        v18,
                        *(_QWORD *)(*(_QWORD *)(v14 + 88) + 16LL),
                        &v86);
                v3 = v26;
                if ( v26 < 0 )
                {
                  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x4C9u, 0);
                  goto LABEL_61;
                }
              }
              if ( CDWMDisplay::RefreshRateChanged((CDWMDisplay *)v14, (const struct CDWMDisplay *)v17) )
                (*(void (__fastcall **)(struct IDCompositionRenderTargetPartner *))(*(_QWORD *)v18 + 48LL))(v18);
              v27 = (unsigned __int8)v72;
              if ( *(int *)(v14 + 200) < 2200 )
                v27 = 1;
              v72 = v27;
              if ( !IsWarpAdapterLuid )
                IsWarpAdapterLuid = CDWMDXGIEnumeration::IsWarpAdapterLuid(this[17], *(struct _LUID *)(v14 + 168));
              v15 = 1;
            }
            v16 = v70 + 1;
            v70 = v16;
            if ( (unsigned int)v16 >= v94 )
              break;
          }
          v13 = v80;
        }
        ++v12;
      }
      while ( v12 < v82 );
    }
    CBitmapSourceArray::~CBitmapSourceArray((CBitmapSourceArray *)&v92);
    CDWMDisplaySet::Release(v5);
    v5 = 0;
  }
  v28 = 0;
  if ( !v82 )
  {
LABEL_91:
    *((_BYTE *)this + 28) = IsWarpAdapterLuid;
    if ( v69 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v73,
        0);
      v61 = NtDCompositionCreateSynchronizationObject(&v73);
      if ( v61 < 0 )
      {
        v67 = 1374;
LABEL_94:
        v3 = v61 | 0x10000000;
        v62 = v3;
LABEL_116:
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v62, v67, 0);
        goto LABEL_117;
      }
      v63 = (*(__int64 (__fastcall **)(_QWORD, void *))(**((_QWORD **)this[6] + 4) + 552LL))(
              *((_QWORD *)this[6] + 4),
              v73);
      v3 = v63;
      if ( v63 < 0 )
      {
        v67 = 1377;
      }
      else
      {
        v63 = CWindowList::SetCommitHandle(this[53], v73);
        v3 = v63;
        if ( v63 < 0 )
        {
          v67 = 1378;
        }
        else
        {
          v63 = CWindowList::HandleScreenRotation(this[53], v76, v75);
          v3 = v63;
          if ( v63 >= 0 )
          {
            v64 = NtDCompositionCommitSynchronizationObject(v73);
            if ( v64 >= 0 )
              goto LABEL_117;
            v61 = v64;
            v67 = 1382;
            goto LABEL_94;
          }
          v67 = 1379;
        }
      }
    }
    else
    {
      v63 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this[6] + 4) + 24LL))(*((_QWORD *)this[6] + 4));
      v3 = v63;
      if ( v63 >= 0 )
        goto LABEL_117;
      v67 = 1386;
    }
    v62 = v63;
    goto LABEL_116;
  }
  v29 = v80;
  while ( 1 )
  {
    v30 = *(_QWORD *)(v29 + 8LL * v28);
    if ( *(_QWORD *)(v30 + 8) )
      goto LABEL_90;
    v68 = 0;
    if ( CDWMDXGIEnumeration::IsWarpAdapterLuid(this[17], *(struct _LUID *)(v30 + 168)) )
      LOBYTE(IsWarpAdapterLuid) = 1;
    if ( CDWMDisplay::IsTsDisplay((CDWMDisplay *)v30) || CCompositor::IsRemoteTreeEnabled(v31) )
      break;
    if ( CDWMDisplay::IsDDisplayCompatible((CDWMDisplay *)v30) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HandleEnsureDDisplayManagerFail>::GetImpl'::`2'::impl) )
      {
        v32 = CDesktopManager::EnsureDDisplayManager((CDesktopManager *)this);
        v3 = v32;
        if ( v32 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v32, 0x504u, 0);
          goto LABEL_71;
        }
      }
      else
      {
        CDesktopManager::EnsureDDisplayManager((CDesktopManager *)this);
      }
      v86 = 0;
      v70 = 0;
      v33 = this[159];
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v86,
        0);
      SourceHandleForTarget = CDDisplayManager::MakeSourceHandleForTarget(
                                v33,
                                (const struct CDWMDisplay *)v30,
                                &v86,
                                &v70);
      v3 = SourceHandleForTarget;
      if ( SourceHandleForTarget < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, SourceHandleForTarget, 0x511u, 0);
        goto LABEL_97;
      }
      v35 = *((_QWORD *)this[6] + 4);
      v36 = *(__int64 (__fastcall **)(__int64, void *, _QWORD, _QWORD))(*(_QWORD *)v35 + 528LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
      v95 = *(_DWORD *)(v30 + 32);
      v96 = *(_DWORD *)(v30 + 36);
      LODWORD(v66) = *(_DWORD *)(v30 + 188);
      v37 = v36(v35, v86, v70, *(_QWORD *)(v30 + 168));
      v38 = FailFastIfAccessDenied(v37);
      v3 = v38;
      if ( v38 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v38, 0x51Cu, 0);
LABEL_97:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v86);
        goto LABEL_71;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v86);
    }
    else
    {
      v39 = *((_QWORD *)this[6] + 4);
      v40 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v39 + 520LL);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
      LODWORD(v66) = *(_DWORD *)(v30 + 252);
      v41 = v40(v39, *(_QWORD *)(v30 + 168), *(unsigned int *)(v30 + 188), *(unsigned int *)(v30 + 236));
      v42 = FailFastIfAccessDenied(v41);
      v3 = v42;
      if ( v42 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v42, 0x528u, 0);
        goto LABEL_71;
      }
    }
LABEL_81:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopDWMCursor>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopDWMCursor>::GetImpl'::`2'::impl) )
    {
      v83 = 0;
      v51 = v68;
      v52 = **(__int64 (__fastcall ***)(struct IDCompositionRenderTargetPartner *, GUID *, __int64))v68;
      v53 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>>(&v83);
      v54 = v52(v51, &GUID_fd1a8dfc_09ad_422c_abf4_bad2e71c68ad, v53);
      if ( v54 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x538,
          (unsigned int)"clientcore\\windows\\dwm\\udwm\\desktopmanager.cpp",
          (const char *)(unsigned int)v54,
          (int)v66);
      v55 = *(__int64 (__fastcall **)(CDWMDisplaySet *, _QWORD, float *))(*(_QWORD *)v83 + 56LL);
      v99 = *(_DWORD *)(v30 + 40);
      v100 = *(_DWORD *)(v30 + 44);
      v101 = *(_DWORD *)(v30 + 48);
      v102 = *(_DWORD *)(v30 + 52);
      v103[0] = (float)*(int *)(v30 + 56);
      v103[1] = (float)*(int *)(v30 + 60);
      v103[2] = (float)*(int *)(v30 + 64);
      v103[3] = (float)*(int *)(v30 + 68);
      LODWORD(v66) = *(_DWORD *)(v30 + 260);
      v56 = v55(v83, *(_QWORD *)(*(_QWORD *)(v30 + 88) + 16LL), v103);
      v3 = v56;
      if ( v56 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v56, 0x53Fu, 0);
        Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>::InternalRelease(&v83);
        goto LABEL_71;
      }
      Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>::InternalRelease(&v83);
    }
    else
    {
      v57 = *(__int64 (__fastcall **)(struct IDCompositionRenderTargetPartner *, _QWORD, __int128 *))(*(_QWORD *)v68 + 32LL);
      v104[0] = *(_DWORD *)(v30 + 40);
      v104[1] = *(_DWORD *)(v30 + 44);
      v104[2] = *(_DWORD *)(v30 + 48);
      v104[3] = *(_DWORD *)(v30 + 52);
      *(float *)&v92 = (float)*(int *)(v30 + 56);
      *((float *)&v92 + 1) = (float)*(int *)(v30 + 60);
      *((float *)&v92 + 2) = (float)*(int *)(v30 + 64);
      *((float *)&v92 + 3) = (float)*(int *)(v30 + 68);
      v66 = v104;
      v58 = v57(v68, *(_QWORD *)(*(_QWORD *)(v30 + 88) + 16LL), &v92);
      v3 = v58;
      if ( v58 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v58, 0x548u, 0);
        goto LABEL_71;
      }
    }
    v59 = (*(__int64 (__fastcall **)(struct IDCompositionRenderTargetPartner *, CDWMDXGIEnumeration *))(*(_QWORD *)v68 + 24LL))(
            v68,
            this[10]);
    v3 = v59;
    if ( v59 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v59, 0x54Bu, 0);
      goto LABEL_71;
    }
    if ( *(_BYTE *)(v30 + 292) )
    {
      v60 = (*(__int64 (__fastcall **)(struct IDCompositionRenderTargetPartner *))(*(_QWORD *)v68 + 40LL))(v68);
      v3 = v60;
      if ( v60 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v60, 0x54Fu, 0);
        goto LABEL_71;
      }
    }
    CDWMDisplay::SetDcompTarget((CDWMDisplay *)v30, v68);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
    v29 = v80;
LABEL_90:
    if ( ++v28 >= v82 )
      goto LABEL_91;
  }
  *(_QWORD *)v89 = 0;
  v43 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this[6] + 4);
  v44 = **v43;
  v45 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::UI::Composition::IExpCompositionProjectedShadow>>(v89);
  v46 = v44(v43, &GUID_7bd36c9a_56ee_4fdd_ac4e_76bbd16ec8e4, v45);
  v3 = v46;
  if ( v46 >= 0 )
  {
    v47 = *(_QWORD *)v89;
    v48 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IDCompositionRenderTargetPartner **))(**(_QWORD **)v89
                                                                                                + 112LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
    v49 = v48(v47, *(_QWORD *)(v30 + 168), &v68);
    v50 = FailFastIfAccessDenied(v49);
    v3 = v50;
    if ( v50 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v50, 0x532u, 0);
      goto LABEL_104;
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v89);
    goto LABEL_81;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v46, 0x52Eu, 0);
LABEL_104:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v89);
LABEL_71:
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
LABEL_117:
  if ( (_BYTE)v72 )
    CCompositor::ForceRender(*((CCompositor **)CDesktopManager::s_pDesktopManagerInstance + 6));
LABEL_122:
  if ( v5 )
    CDWMDisplaySet::Release(v5);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v73);
  CBitmapSourceArray::~CBitmapSourceArray((CBitmapSourceArray *)&v80);
  return v3;
}

```

## disassembly

```asm
0x18007a3d8  push    rbp
0x18007a3da  push    rbx
0x18007a3db  push    rsi
0x18007a3dc  push    rdi
0x18007a3dd  push    r12
0x18007a3df  push    r13
0x18007a3e1  push    r14
0x18007a3e3  push    r15
0x18007a3e5  lea     rbp, [rsp-78h]
0x18007a3ea  sub     rsp, 178h
0x18007a3f1  mov     rax, cs:__security_cookie
0x18007a3f8  xor     rax, rsp
0x18007a3fb  mov     [rbp+0B0h+var_50], rax
0x18007a3ff  mov     r14, rcx
0x18007a402  xor     edi, edi
0x18007a404  mov     [rbp+0B0h+var_E0], rdi
0x18007a408  xorps   xmm0, xmm0
0x18007a40b  movdqu  [rbp+0B0h+var_100], xmm0
0x18007a410  mov     [rbp+0B0h+var_F0], rdi
0x18007a414  mov     [rbp+0B0h+var_E8], edi
0x18007a417  mov     [rbp+0B0h+var_128], edi
0x18007a41a  mov     [rbp+0B0h+var_12C], edi
0x18007a41d  mov     [rsp+1B0h+var_138], rdi
0x18007a422  lea     rdx, [rbp+0B0h+var_E0]; struct CDWMDisplaySet **
0x18007a426  call    ?EnumerateMonitors@CDesktopManager@@AEAAJPEAPEAVCDWMDisplaySet@@@Z; CDesktopManager::EnumerateMonitors(CDWMDisplaySet * *)
0x18007a42b  mov     ebx, eax
0x18007a42d  test    eax, eax
0x18007a42f  js      loc_18007B0FF
0x18007a435  lea     rdx, [rbp+0B0h+var_100]
0x18007a439  mov     rcx, [r14+90h]
0x18007a440  call    ?GetAllDisplaysNoRef@CDWMDisplaySet@@QEBAJPEAV?$DynArray@PEAVCDWMDisplay@@$0A@@@@Z; CDWMDisplaySet::GetAllDisplaysNoRef(DynArray<CDWMDisplay *,0> *)
0x18007a445  mov     ebx, eax
0x18007a447  test    eax, eax
0x18007a449  js      loc_18007B0F0
0x18007a44f  mov     byte ptr [rsp+1B0h+var_13C], dil
0x18007a454  mov     [rsp+1B0h+var_148], dil
0x18007a459  mov     byte ptr [rsp+1B0h+var_140], dil
0x18007a45e  lea     r12d, [rdi+1]
0x18007a462  mov     r15, [rbp+0B0h+var_E0]
0x18007a466  test    r15, r15
0x18007a469  jz      loc_18007A984
0x18007a46f  xorps   xmm0, xmm0
0x18007a472  movdqu  [rbp+0B0h+var_B0], xmm0
0x18007a477  mov     [rbp+0B0h+var_A0], rdi
0x18007a47b  mov     [rbp+0B0h+var_98], edi
0x18007a47e  mov     rdx, r15; struct CDWMDisplaySet *
0x18007a481  mov     rcx, [r14+90h]; this
0x18007a488  call    ?IsEquivalentRotated@CDWMDisplaySet@@QEBA_NPEBV1@@Z; CDWMDisplaySet::IsEquivalentRotated(CDWMDisplaySet const *)
0x18007a48d  test    al, al
0x18007a48f  jz      short loc_18007A4AD
0x18007a491  lea     r9, [rbp+0B0h+var_12C]; int *
0x18007a495  lea     r8, [rbp+0B0h+var_128]; int *
0x18007a499  mov     rdx, [r14+90h]; struct CDWMDisplaySet *
0x18007a4a0  mov     rcx, r15; struct CDWMDisplaySet *
0x18007a4a3  call    ?CalculateRotationAngles@CDWMDisplaySet@@SAJPEBV1@0PEAH1@Z; CDWMDisplaySet::CalculateRotationAngles(CDWMDisplaySet const *,CDWMDisplaySet const *,int *,int *)
0x18007a4a8  mov     [rsp+1B0h+var_148], r12b
0x18007a4ad  mov     [rbp+0B0h+var_E0], rdi
0x18007a4b1  lea     rdx, [rbp+0B0h+var_E0]
0x18007a4b5  mov     ecx, r12d
0x18007a4b8  call    cs:__imp_GetDesktopID
0x18007a4be  mov     rcx, [rbp+0B0h+var_E0]; unsigned __int64
0x18007a4c2  call    ?IsLogonDesktop@CDesktopManager@@SA_N_K@Z; CDesktopManager::IsLogonDesktop(unsigned __int64)
0x18007a4c7  test    al, al
0x18007a4c9  jnz     loc_18007A64C
0x18007a4cf  call    IsOpenThemeDataPresent
0x18007a4d4  test    al, al
0x18007a4d6  jz      loc_18007A64C
0x18007a4dc  mov     rax, [r14+0B0h]
0x18007a4e3  test    rax, rax
0x18007a4e6  jz      loc_18007A64C
0x18007a4ec  cmp     [rax+78h], dil
0x18007a4f0  jz      loc_18007A64C
0x18007a4f6  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18007a4fd  cmp     [rax+17h], dil
0x18007a501  jz      loc_18007A64C
0x18007a507  cmp     cs:?s_forceDisableModeChangeAnimation@CDesktopManager@@0_NA, dil; bool CDesktopManager::s_forceDisableModeChangeAnimation
0x18007a50e  jnz     loc_18007A64C
0x18007a514  mov     [rbp+0B0h+pvParam], edi
0x18007a517  xor     r9d, r9d; fWinIni
0x18007a51a  lea     r8, [rbp+0B0h+pvParam]; pvParam
0x18007a51e  xor     edx, edx; uiParam
0x18007a520  mov     ecx, 0AAh; uiAction
0x18007a525  call    cs:__imp_SystemParametersInfoW
0x18007a52b  test    eax, eax
0x18007a52d  jz      loc_18007A64C
0x18007a533  cmp     [rbp+0B0h+pvParam], edi
0x18007a536  jnz     loc_18007A64C
0x18007a53c  xorps   xmm0, xmm0
0x18007a53f  movdqu  [rbp+0B0h+var_120], xmm0
0x18007a544  mov     [rbp+0B0h+var_110], rdi
0x18007a548  lea     r8, [rbp+0B0h+var_120]
0x18007a54c  mov     rdx, [r14+90h]; CDWMDisplaySet *
0x18007a553  mov     rcx, r15; this
0x18007a556  call    ?HasChanged@CDisplayModeChangeHelper@@SA?AW4DisplayModeChangeResult@@PEAVCDWMDisplaySet@@0AEAV?$vector@PEBVCDWMDisplay@@V?$allocator@PEBVCDWMDisplay@@@std@@@std@@@Z; CDisplayModeChangeHelper::HasChanged(CDWMDisplaySet *,CDWMDisplaySet *,std::vector<CDWMDisplay const *> &)
0x18007a55b  mov     ebx, eax
0x18007a55d  test    eax, eax
0x18007a55f  jz      loc_18007A627
0x18007a565  mov     [rsp+1B0h+var_150], rdi
0x18007a56a  lea     rcx, [rsp+1B0h+var_150]
0x18007a56f  call    ?reset@?$com_ptr_t@VCImage@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(void)
0x18007a574  lea     rdx, [rsp+1B0h+var_150]
0x18007a579  mov     ecx, ebx
0x18007a57b  call    ?CreateDisplayAnimatedVisual@CDisplayModeChangeHelper@@SAJW4DisplayModeChangeResult@@PEAPEAVCDisplayAnimatedVisual@@@Z; CDisplayModeChangeHelper::CreateDisplayAnimatedVisual(DisplayModeChangeResult,CDisplayAnimatedVisual * *)
0x18007a580  mov     ebx, eax
0x18007a582  test    eax, eax
0x18007a584  js      loc_18007A837
0x18007a58a  mov     rbx, [rsp+1B0h+var_150]
0x18007a58f  mov     rdx, rbx; struct CDisplayAnimatedVisual *
0x18007a592  mov     rcx, [r14+1A8h]; this
0x18007a599  call    ?StopAndSetDisplayAnimatedVisual@CWindowList@@QEAAJPEAVCDisplayAnimatedVisual@@@Z; CWindowList::StopAndSetDisplayAnimatedVisual(CDisplayAnimatedVisual *)
0x18007a59e  test    rbx, rbx
0x18007a5a1  jz      short loc_18007A61C
0x18007a5a3  lea     r8, [rbp+0B0h+var_120]
0x18007a5a7  mov     rdx, r15
0x18007a5aa  mov     rcx, rbx
0x18007a5ad  call    ?SetChangeContextInfo@CDisplayAnimatedVisual@@QEAAXPEAVCDWMDisplaySet@@AEAV?$vector@PEBVCDWMDisplay@@V?$allocator@PEBVCDWMDisplay@@@std@@@std@@@Z; CDisplayAnimatedVisual::SetChangeContextInfo(CDWMDisplaySet *,std::vector<CDWMDisplay const *> &)
0x18007a5b2  mov     rcx, rbx; this
0x18007a5b5  call    ?Start@CDisplayAnimatedVisual@@QEAAJXZ; CDisplayAnimatedVisual::Start(void)
0x18007a5ba  mov     ebx, eax
0x18007a5bc  test    eax, eax
0x18007a5be  jns     short loc_18007A61C
0x18007a5c0  mov     [rsp+1B0h+var_188], rdi; void *
0x18007a5c5  mov     [rsp+1B0h+var_190], 492h; unsigned int
0x18007a5cd  mov     r9d, eax; int
0x18007a5d0  xor     r8d, r8d; unsigned int
0x18007a5d3  xor     edx, edx; int *
0x18007a5d5  lea     ecx, [rdx+14h]; unsigned int
0x18007a5d8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18007a5dd  nop
0x18007a5de  lea     rcx, [rsp+1B0h+var_150]
0x18007a5e3  call    ??1?$com_ptr_t@VCDisplaySecondaryOnlyToExtendAnimatedVisual@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>::~com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>(void)
0x18007a5e8  nop
0x18007a5e9  mov     rcx, qword ptr [rbp+0B0h+var_120]
0x18007a5ed  test    rcx, rcx
0x18007a5f0  jz      short loc_18007A60E
0x18007a5f2  mov     rdx, [rbp+0B0h+var_110]
0x18007a5f6  sub     rdx, rcx
0x18007a5f9  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18007a5fd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007a602  xorps   xmm0, xmm0
0x18007a605  movdqu  [rbp+0B0h+var_120], xmm0
0x18007a60a  mov     [rbp+0B0h+var_110], rdi
0x18007a60e  lea     rcx, [rbp+0B0h+var_B0]; this
0x18007a612  call    ??1CBitmapSourceArray@@QEAA@XZ; CBitmapSourceArray::~CBitmapSourceArray(void)
0x18007a617  jmp     loc_18007B120
0x18007a61c  lea     rcx, [rsp+1B0h+var_150]
0x18007a621  call    ??1?$com_ptr_t@VCDisplaySecondaryOnlyToExtendAnimatedVisual@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>::~com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>(void)
0x18007a626  nop
0x18007a627  mov     rcx, qword ptr [rbp+0B0h+var_120]
0x18007a62b  test    rcx, rcx
0x18007a62e  jz      short loc_18007A64C
0x18007a630  mov     rdx, [rbp+0B0h+var_110]
0x18007a634  sub     rdx, rcx
0x18007a637  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18007a63b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18007a640  xorps   xmm0, xmm0
0x18007a643  movdqu  [rbp+0B0h+var_120], xmm0
0x18007a648  mov     [rbp+0B0h+var_110], rdi
0x18007a64c  lea     rdx, [rbp+0B0h+var_B0]
0x18007a650  mov     rcx, r15
0x18007a653  call    ?GetAllDisplaysNoRef@CDWMDisplaySet@@QEBAJPEAV?$DynArray@PEAVCDWMDisplay@@$0A@@@@Z; CDWMDisplaySet::GetAllDisplaysNoRef(DynArray<CDWMDisplay *,0> *)
0x18007a658  mov     ebx, eax
0x18007a65a  test    eax, eax
0x18007a65c  js      loc_18007AA3F
0x18007a662  mov     r12d, edi
0x18007a665  cmp     [rbp+0B0h+var_E8], edi
0x18007a668  jbe     loc_18007A96A
0x18007a66e  mov     rcx, qword ptr [rbp+0B0h+var_100]
0x18007a672  mov     eax, r12d
0x18007a675  mov     rdi, [rcx+rax*8]
0x18007a679  xor     dl, dl
0x18007a67b  xor     eax, eax
0x18007a67d  mov     [rsp+1B0h+var_144], eax
0x18007a681  cmp     [rbp+0B0h+var_98], eax
0x18007a684  jbe     loc_18007A95B
0x18007a68a  test    dl, dl
0x18007a68c  jnz     loc_18007A957
0x18007a692  mov     rcx, qword ptr [rbp+0B0h+var_B0]
0x18007a696  mov     r13, [rcx+rax*8]
0x18007a69a  mov     rsi, [r13+8]
0x18007a69e  test    rsi, rsi
0x18007a6a1  jz      loc_18007A944
0x18007a6a7  mov     eax, [r13+0BCh]
0x18007a6ae  cmp     [rdi+0BCh], eax
0x18007a6b4  jnz     loc_18007A944
0x18007a6ba  mov     eax, [r13+0ECh]
0x18007a6c1  cmp     [rdi+0ECh], eax
0x18007a6c7  jnz     loc_18007A944
0x18007a6cd  mov     eax, [r13+0FCh]
0x18007a6d4  cmp     [rdi+0FCh], eax
0x18007a6da  jnz     loc_18007A944
0x18007a6e0  mov     al, [r13+123h]
0x18007a6e7  cmp     [rdi+123h], al
0x18007a6ed  jnz     loc_18007A944
0x18007a6f3  mov     rcx, rdi; this
0x18007a6f6  call    ?IsTsDisplay@CDWMDisplay@@QEBA_NXZ; CDWMDisplay::IsTsDisplay(void)
0x18007a6fb  test    al, al
0x18007a6fd  jnz     loc_18007A944
0x18007a703  mov     rdx, rsi; struct IDCompositionRenderTargetPartner *
0x18007a706  call    ?SetDcompTarget@CDWMDisplay@@QEAAXPEAUIDCompositionRenderTargetPartner@@@Z; CDWMDisplay::SetDcompTarget(IDCompositionRenderTargetPartner *)
0x18007a70b  xor     edx, edx; struct IDCompositionRenderTargetPartner *
0x18007a70d  mov     rcx, r13; this
0x18007a710  call    ?SetDcompTarget@CDWMDisplay@@QEAAXPEAUIDCompositionRenderTargetPartner@@@Z; CDWMDisplay::SetDcompTarget(IDCompositionRenderTargetPartner *)
0x18007a715  cmp     byte ptr [rdi+124h], 0
0x18007a71c  jz      short loc_18007A73F
0x18007a71e  mov     rax, [rsi]
0x18007a721  movss   xmm1, dword ptr [rdi+100h]
0x18007a729  mov     rcx, rsi
0x18007a72c  mov     rax, [rax+28h]
0x18007a730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a735  mov     ebx, eax
0x18007a737  test    eax, eax
0x18007a739  js      loc_18007A9D5
0x18007a73f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopDWMCursor@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopDWMCursor@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopDWMCursor> `wil::Feature<__WilFeatureTraits_Feature_DesktopDWMCursor>::GetImpl(void)'::`2'::impl
0x18007a746  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopDWMCursor@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopDWMCursor>::__private_IsEnabled(void)
0x18007a74b  test    al, al
0x18007a74d  jz      loc_18007A849
0x18007a753  mov     rbx, [rsi]
0x18007a756  mov     [rbp+0B0h+var_108], 0
0x18007a75e  lea     rcx, [rbp+0B0h+var_108]
0x18007a762  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIDCompositionRenderTargetPartner2@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIDCompositionRenderTargetPartner2@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>>)
0x18007a767  mov     r8, rax
0x18007a76a  lea     rdx, _GUID_fd1a8dfc_09ad_422c_abf4_bad2e71c68ad
0x18007a771  mov     rcx, rsi
0x18007a774  mov     rax, [rbx]
0x18007a777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a77c  mov     rcx, [rbp+0B8h]; this
0x18007a783  test    eax, eax
0x18007a785  js      loc_18007B179
0x18007a78b  mov     rcx, [rbp+0B0h+var_108]
0x18007a78f  mov     rax, [rcx]
0x18007a792  mov     r10, [rax+38h]
0x18007a796  mov     eax, [rdi+28h]
0x18007a799  mov     [rbp+0B0h+var_90], eax
0x18007a79c  mov     eax, [rdi+2Ch]
0x18007a79f  mov     [rbp+0B0h+var_8C], eax
0x18007a7a2  mov     eax, [rdi+30h]
0x18007a7a5  mov     [rbp+0B0h+var_88], eax
0x18007a7a8  mov     eax, [rdi+34h]
0x18007a7ab  mov     [rbp+0B0h+var_84], eax
0x18007a7ae  movd    xmm0, dword ptr [rdi+38h]
0x18007a7b3  cvtdq2ps xmm0, xmm0
0x18007a7b6  movss   dword ptr [rbp+0B0h+var_E0], xmm0
0x18007a7bb  movd    xmm1, dword ptr [rdi+3Ch]
0x18007a7c0  cvtdq2ps xmm1, xmm1
0x18007a7c3  movss   dword ptr [rbp+0B0h+var_E0+4], xmm1
0x18007a7c8  movd    xmm0, dword ptr [rdi+40h]
0x18007a7cd  cvtdq2ps xmm0, xmm0
0x18007a7d0  movss   [rbp+0B0h+var_D8], xmm0
0x18007a7d5  movd    xmm1, dword ptr [rdi+44h]
0x18007a7da  cvtdq2ps xmm1, xmm1
0x18007a7dd  movss   [rbp+0B0h+var_D4], xmm1
0x18007a7e2  mov     r9, [rdi+58h]
0x18007a7e6  mov     edx, [rdi+0F8h]
0x18007a7ec  mov     [rsp+1B0h+var_180], edx
0x18007a7f0  lea     rax, [rbp+0B0h+var_90]
0x18007a7f4  mov     [rsp+1B0h+var_188], rax
0x18007a7f9  movss   xmm0, dword ptr [rdi+104h]
0x18007a801  movss   [rsp+1B0h+var_190], xmm0
0x18007a807  movss   xmm3, cs:__real@3f800000
0x18007a80f  lea     r8, [rbp+0B0h+var_E0]
0x18007a813  mov     rdx, [r9+10h]
0x18007a817  mov     rax, r10
0x18007a81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a81f  mov     ebx, eax
0x18007a821  test    eax, eax
0x18007a823  js      loc_18007AA03
0x18007a829  lea     rcx, [rbp+0B0h+var_108]
0x18007a82d  call    ?InternalRelease@?$ComPtr@UIDCompositionRenderTargetPartner2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionRenderTargetPartner2>::InternalRelease(void)
0x18007a832  jmp     loc_18007A8D5
0x18007a837  mov     [rsp+1B0h+var_188], rdi
0x18007a83c  mov     [rsp+1B0h+var_190], 48Bh
0x18007a844  jmp     loc_18007A5CD
0x18007a849  mov     eax, [rdi+28h]
0x18007a84c  mov     [rbp+0B0h+var_C0], eax
0x18007a84f  mov     eax, [rdi+2Ch]
0x18007a852  mov     [rbp+0B0h+var_C0+4], eax
0x18007a855  mov     eax, [rdi+30h]
0x18007a858  mov     [rbp+0B0h+var_B8], eax
0x18007a85b  mov     eax, [rdi+34h]
0x18007a85e  mov     [rbp+0B0h+var_B4], eax
0x18007a861  movd    xmm0, dword ptr [rdi+38h]
0x18007a866  cvtdq2ps xmm0, xmm0
0x18007a869  movss   dword ptr [rbp+0B0h+var_D0], xmm0
0x18007a86e  movd    xmm1, dword ptr [rdi+3Ch]
0x18007a873  cvtdq2ps xmm1, xmm1
0x18007a876  movss   dword ptr [rbp+0B0h+var_D0+4], xmm1
0x18007a87b  movd    xmm0, dword ptr [rdi+40h]
0x18007a880  cvtdq2ps xmm0, xmm0
0x18007a883  movss   [rbp+0B0h+var_C8], xmm0
0x18007a888  movd    xmm1, dword ptr [rdi+44h]
0x18007a88d  cvtdq2ps xmm1, xmm1
0x18007a890  movss   [rbp+0B0h+var_C4], xmm1
0x18007a895  mov     rax, [rsi]
0x18007a898  mov     rdx, [rdi+58h]
0x18007a89c  mov     ecx, [rdi+0F8h]
0x18007a8a2  mov     dword ptr [rsp+1B0h+var_188], ecx
0x18007a8a6  lea     rcx, [rbp+0B0h+var_C0]
0x18007a8aa  mov     qword ptr [rsp+1B0h+var_190], rcx; int
0x18007a8af  movss   xmm3, cs:__real@3f800000
  ... truncated ...
```
