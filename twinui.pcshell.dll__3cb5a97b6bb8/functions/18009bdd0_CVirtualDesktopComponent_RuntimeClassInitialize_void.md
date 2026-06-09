# CVirtualDesktopComponent::RuntimeClassInitialize(void)

- ea: `0x18009bdd0`
- end: `0x18009d3af`
- name: `?RuntimeClassInitialize@CVirtualDesktopComponent@@QEAAJXZ`
- size: `5599`
- prototype: `__int64 __fastcall(CVirtualDesktopComponent *__hidden this)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802c79c0`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x1800255d0`
- `0x180033a90`
- `0x180098c08`
- `0x18009ac04`
- `0x18009ad04`
- `0x18009ae74`
- `0x18009af58`
- `0x18009b0cc`
- `0x18009b350`
- `0x18009b380`
- `0x18009b408`
- `0x18009b52c`
- `0x18009b5e0`
- `0x18009b690`
- `0x18009b788`
- `0x18009b868`
- `0x18009b948`
- `0x18009b9bc`
- `0x18009ba70`
- `0x18009bb28`
- `0x18009bc40`
- `0x18009bdd0`
- `0x18009d3b8`
- `0x18018ea9c`
- `0x1801fa198`
- `0x18029b61c`
- `0x1802a9734`
- `0x18066ad24`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18009be31`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18009be31`

## string_xrefs

- `0x18009c83d`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009c8f8`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009c935`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009ca08`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cadb`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cb94`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cbba`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cbe2`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cc1c`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009ccb0`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cdac`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009ce86`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cebb`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cef0`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cf25`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cf5d`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cf95`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009cfcd`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d005`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d041`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d087`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d0c3`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d0ff`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d13b`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d18b`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d1db`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d217`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d256`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d295`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d2d4`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d313`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d352`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`
- `0x18009d390`: `pcshell\twinui\virtualdesktops\lib\virtualdesktopcomponent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CVirtualDesktopComponent::RuntimeClassInitialize(void **this)
{
  void **v2; // r15
  const struct _GUID *v3; // rcx
  CCriticalFailureHandler *v4; // rcx
  int Instance; // ebx
  unsigned int UniqueContext; // r12d
  void **v7; // rax
  const struct _GUID *v8; // r8
  CCriticalFailureHandler *v9; // rcx
  const struct _GUID *v10; // rdx
  CCriticalFailureHandler *v11; // rcx
  const struct _GUID *v12; // r8
  CCriticalFailureHandler *v13; // rcx
  struct IVirtualDesktopRegistryHelpers **v14; // r13
  const struct _GUID *v15; // rcx
  CCriticalFailureHandler *v16; // rcx
  CVirtualDesktopComponent *v17; // rcx
  CCriticalFailureHandler *v18; // rcx
  int IsThreadRTL; // eax
  const struct _GUID *v20; // r9
  CCriticalFailureHandler *v21; // rcx
  const struct _GUID *v22; // rcx
  CCriticalFailureHandler *v23; // rcx
  const struct _GUID *v24; // r9
  CCriticalFailureHandler *v25; // rcx
  struct IVirtualDesktopManagerPrivate **v26; // r14
  int v27; // eax
  CCriticalFailureHandler *v28; // rcx
  CCriticalFailureHandler *v29; // rcx
  CCriticalFailureHandler *v30; // rcx
  const struct _GUID *v31; // rdx
  CCriticalFailureHandler *v32; // rcx
  void *v33; // rcx
  CCriticalFailureHandler *v34; // rcx
  const struct _GUID *v35; // r8
  void *v36; // rcx
  CCriticalFailureHandler *v37; // rcx
  struct IVirtualDesktopNotification *v38; // rbx
  __int64 (__fastcall *v39)(struct IVirtualDesktopNotification *, GUID *, void **); // rdi
  CCriticalFailureHandler *v40; // rcx
  CCriticalFailureHandler *v41; // rcx
  const struct _GUID *v42; // rdx
  CCriticalFailureHandler *v43; // rcx
  struct IVirtualDesktopPinnedAppsPrivate **v44; // r12
  struct IUnknown *v45; // r9
  CCriticalFailureHandler *v46; // rcx
  CCriticalFailureHandler *v47; // rcx
  CCriticalFailureHandler *v48; // rcx
  CCriticalFailureHandler *v49; // rcx
  __int64 v50; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  struct IVirtualDesktopDefaultForegroundHandler *v54; // rcx
  struct IVirtualDesktopCollection *v55; // rcx
  struct IVirtualDesktopPersistence *v56; // rcx
  struct IVirtualDesktopFactory *v57; // rcx
  struct IVirtualDesktopVisibilityPolicy *v58; // rcx
  struct IVirtualDesktopNotification *v59; // rcx
  struct IVirtualDesktopDefaultForegroundHandler *v60; // rcx
  struct IVirtualDesktopCollection *v61; // rcx
  struct IVirtualDesktopPersistence *v62; // rcx
  struct IVirtualDesktopFactory *v63; // rcx
  struct IVirtualDesktopVisibilityPolicy *v64; // rcx
  struct IVirtualDesktopNotification *v65; // rcx
  struct IVirtualDesktopCollection *v66; // rcx
  struct IVirtualDesktopPersistence *v67; // rcx
  struct IVirtualDesktopFactory *v68; // rcx
  struct IVirtualDesktopVisibilityPolicy *v69; // rcx
  struct IVirtualDesktopNotification *v70; // rcx
  struct IVirtualDesktopDefaultForegroundHandler *v71; // rcx
  struct IVirtualDesktopCollection *v72; // rcx
  struct IVirtualDesktopPersistence *v73; // rcx
  struct IVirtualDesktopFactory *v74; // rcx
  struct IVirtualDesktopVisibilityPolicy *v75; // rcx
  struct IVirtualDesktopNotification *v76; // rcx
  struct IVirtualDesktopDefaultForegroundHandler *v77; // rcx
  struct IVirtualDesktopCollection *v78; // rcx
  struct IVirtualDesktopPersistence *v79; // rcx
  struct IVirtualDesktopFactory *v80; // rcx
  struct IVirtualDesktopVisibilityPolicy *v81; // rcx
  struct IVirtualDesktopNotification *v82; // rcx
  unsigned int v83; // r12d
  unsigned int v84; // r13d
  unsigned __int64 *v85; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v86; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v87; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v88; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v89; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v90; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v91; // [rsp+28h] [rbp-D8h]
  unsigned __int64 *v92; // [rsp+28h] [rbp-D8h]
  struct IVirtualDesktopCollection *v93; // [rsp+40h] [rbp-C0h] BYREF
  struct IVirtualDesktopPersistence *v94; // [rsp+48h] [rbp-B8h] BYREF
  struct IVirtualDesktopFactory *v95; // [rsp+50h] [rbp-B0h] BYREF
  struct IVirtualDesktopDefaultForegroundHandler *v96; // [rsp+58h] [rbp-A8h] BYREF
  struct IVirtualDesktopNotification *v97; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v98; // [rsp+68h] [rbp-98h] BYREF
  struct IVirtualDesktopNotification *v99; // [rsp+78h] [rbp-88h] BYREF
  struct IVirtualDesktopVisibilityPolicy *v100; // [rsp+80h] [rbp-80h] BYREF
  struct IVirtualDesktopCollection *v101; // [rsp+88h] [rbp-78h] BYREF
  __int128 v102; // [rsp+90h] [rbp-70h] BYREF
  struct IVirtualDesktopManagerPrivate *v103; // [rsp+A0h] [rbp-60h]
  __int64 v104; // [rsp+A8h] [rbp-58h]
  __int128 v105; // [rsp+B0h] [rbp-50h]
  void *v106; // [rsp+C0h] [rbp-40h]
  __int64 v107; // [rsp+C8h] [rbp-38h]
  __int128 v108; // [rsp+D0h] [rbp-30h]
  struct IVirtualDesktopNotification *v109; // [rsp+E0h] [rbp-20h]
  __int64 v110; // [rsp+E8h] [rbp-18h]
  GUID v111; // [rsp+F0h] [rbp-10h]
  void *v112; // [rsp+100h] [rbp+0h]
  __int64 v113; // [rsp+108h] [rbp+8h]
  __int128 v114; // [rsp+110h] [rbp+10h]
  void *v115; // [rsp+120h] [rbp+20h]
  __int64 v116; // [rsp+128h] [rbp+28h]
  __int128 v117; // [rsp+130h] [rbp+30h]
  void *v118; // [rsp+140h] [rbp+40h]
  __int64 v119; // [rsp+148h] [rbp+48h]
  GUID v120; // [rsp+150h] [rbp+50h]
  void *v121; // [rsp+160h] [rbp+60h]
  __int64 v122; // [rsp+168h] [rbp+68h]
  __int128 v123; // [rsp+170h] [rbp+70h]
  struct IVirtualDesktopPinnedAppsPrivate *v124; // [rsp+180h] [rbp+80h]
  __int64 v125; // [rsp+188h] [rbp+88h]
  __int128 v126; // [rsp+190h] [rbp+90h]
  void *v127; // [rsp+1A0h] [rbp+A0h]
  __int64 v128; // [rsp+1A8h] [rbp+A8h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]
  CCriticalFailureHandler *v130; // [rsp+200h] [rbp+100h] BYREF
  unsigned int v131; // [rsp+208h] [rbp+108h] BYREF
  void *v132; // [rsp+210h] [rbp+110h] BYREF
  struct IVirtualDesktopVisibilityPolicy *v133; // [rsp+218h] [rbp+118h] BYREF

  v2 = this + 18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 18);
  Instance = CVirtualDesktopLock_CreateInstance(v3, v2);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v4, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v4,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x41u,
        v85,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v85);
      return (unsigned int)Instance;
    }
  }
  UniqueContext = SHTaskPoolGetUniqueContext();
  v97 = 0;
  v7 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(&v97);
  Instance = CVirtualDesktopNotifications_CreateInstance(UniqueContext, (struct IVirtualDesktopLock *)*v2, v8, v7);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v9, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v9,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x47u,
        v85,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v85);
      goto LABEL_84;
    }
  }
  v133 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v133);
  Instance = CVirtualDesktopVisibilityPolicy_CreateInstance(v97, v10, (void **)&v133);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v11, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v11,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x4Bu,
        v85,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v85);
      goto LABEL_83;
    }
  }
  v95 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
  Instance = CVirtualDesktopFactory_CreateInstance(v133, (struct IVirtualDesktopLock *)*v2, v12, (void **)&v95);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v13, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v13,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x4Fu,
        v85,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      v53 = 79;
      goto LABEL_90;
    }
  }
  v14 = (struct IVirtualDesktopRegistryHelpers **)(this + 30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 30);
  Instance = VirtualDesktopRegistryHelpers_CreateInstance(v15, this + 30);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v16, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v16,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x52u,
        v85,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      v53 = 82;
LABEL_90:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v53,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v85);
      goto LABEL_82;
    }
  }
  v94 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
  Instance = CVirtualDesktopComponent::CreatePersistence(v17, *v14, &v94);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v18, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v18,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x56u,
        v85,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v85);
      goto LABEL_81;
    }
  }
  v93 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
  IsThreadRTL = Mirror_IsThreadRTL();
  Instance = CVirtualDesktopCollection_CreateInstance(v95, v94, IsThreadRTL != 0, v20, (void **)&v93);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v21, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v21,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x5Au,
        v86,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v86);
      v66 = v93;
      if ( v93 )
      {
        v93 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopCollection *))(*(_QWORD *)v66 + 16LL))(v66);
      }
      v67 = v94;
      if ( v94 )
      {
        v94 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopPersistence *))(*(_QWORD *)v67 + 16LL))(v67);
      }
      v68 = v95;
      if ( v95 )
      {
        v95 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopFactory *))(*(_QWORD *)v68 + 16LL))(v68);
      }
      v69 = v133;
      if ( v133 )
      {
        v133 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopVisibilityPolicy *))(*(_QWORD *)v69 + 16LL))(v69);
      }
      v70 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopNotification *))(*(_QWORD *)v70 + 16LL))(v70);
      }
      return (unsigned int)Instance;
    }
  }
  v96 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
  Instance = CVirtualDesktopDefaultForegroundHandler_CreateInstance(v22, (void **)&v96);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v23, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v23,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x5Eu,
        v86,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      v50 = 94;
      goto LABEL_80;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 19);
  Instance = CVirtualDesktopForegroundPolicy_CreateInstance(v93, v133, v96, v24, this + 19);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v25, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v25,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x64u,
        v86,
        v88);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      v50 = 100;
      goto LABEL_80;
    }
  }
  v26 = (struct IVirtualDesktopManagerPrivate **)(this + 20);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 20);
  v132 = *v2;
  *(_QWORD *)&v98.Data1 = v94;
  *(_QWORD *)v98.Data4 = this[19];
  v99 = v97;
  v100 = v133;
  v101 = v93;
  this[20] = 0;
  v130 = 0;
  Microsoft::WRL::ComPtr<CVirtualDesktopManager>::InternalRelease(&v130);
  v27 = Microsoft::WRL::Details::MakeAndInitialize<CVirtualDesktopManager,CVirtualDesktopManager,IVirtualDesktopCollection * &,IVirtualDesktopVisibilityPolicy * &,IVirtualDesktopNotification * &,IVirtualDesktopForegroundPolicy * &,IVirtualDesktopPersistence * &,std::nullptr_t,IVirtualDesktopLock * &>(
          (unsigned int)&v130,
          (unsigned int)&v101,
          (unsigned int)&v100,
          (unsigned int)&v99,
          (__int64)v98.Data4,
          (__int64)&v98);
  Instance = v27;
  if ( v27 < 0 )
  {
    v52 = 1690;
  }
  else
  {
    v27 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IVirtualDesktopManagerPrivate,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,ISuspendableVirtualDesktopManager,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>(
            v130,
            &GUID_95bb3d6c_9eba_40cc_af4d_1a3255717d9d,
            this + 20);
    Instance = v27;
    if ( v27 >= 0 )
      goto LABEL_30;
    v52 = 1691;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v52,
    (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopmanager.cpp",
    (const char *)(unsigned int)v27,
    (int)v86);
LABEL_30:
  v28 = v130;
  if ( v130 )
  {
    v130 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IVirtualDesktopManagerPrivate,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,ISuspendableVirtualDesktopManager,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::Release();
  }
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v28, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v28,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x6Eu,
        v86,
        v89);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      v50 = 110;
      goto LABEL_80;
    }
  }
  LOBYTE(v130) = 0;
  v131 = 0;
  Instance = wil::wnf_query_nothrow<enum _TABLETMODESTATE>(v28, &v130, &v131);
  LODWORD(v132) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v29, (int *)&v132);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v132;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v29,
        (int *)&v132,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x72u,
        v86,
        v89);
      Instance = (int)v132;
    }
    if ( Instance < 0 )
    {
      v50 = 114;
      goto LABEL_80;
    }
  }
  if ( !(_BYTE)v130 )
    v131 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 26);
  v86 = (unsigned __int64 *)*v2;
  Instance = VirtualDesktopTabletModePolicy_CreateInstance(v131, v93, *v26, v133);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v30, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v30,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x7Fu,
        v86,
        v89);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      v50 = 127;
      goto LABEL_80;
    }
  }
  v86 = (unsigned __int64 *)this[26];
  Instance = (*(__int64 (__fastcall **)(struct IVirtualDesktopPersistence *, _QWORD, struct IVirtualDesktopManagerPrivate *, struct IVirtualDesktopCollection *))(*(_QWORD *)v94 + 40LL))(
               v94,
               v131,
               *v26,
               v93);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v32, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v32,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x83u,
        v86,
        v89);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      v50 = 131;
      goto LABEL_80;
    }
  }
  v33 = this[21];
  this[21] = 0;
  if ( v33 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
  Instance = VirtualDesktopAnimationSyncNotifications_CreateInstance(UniqueContext, v31, this + 21);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v34, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v34,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x87u,
        v86,
        v89);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v86);
      v54 = v96;
      if ( v96 )
      {
        v96 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopDefaultForegroundHandler *))(*(_QWORD *)v54 + 16LL))(v54);
      }
      v55 = v93;
      if ( v93 )
      {
        v93 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopCollection *))(*(_QWORD *)v55 + 16LL))(v55);
      }
      v56 = v94;
      if ( v94 )
      {
        v94 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopPersistence *))(*(_QWORD *)v56 + 16LL))(v56);
      }
      v57 = v95;
      if ( v95 )
      {
        v95 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopFactory *))(*(_QWORD *)v57 + 16LL))(v57);
      }
      v58 = v133;
      if ( v133 )
      {
        v133 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopVisibilityPolicy *))(*(_QWORD *)v58 + 16LL))(v58);
      }
      v59 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopNotification *))(*(_QWORD *)v59 + 16LL))(v59);
      }
      return (unsigned int)Instance;
    }
  }
  v36 = this[23];
  this[23] = 0;
  if ( v36 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
  Instance = CVirtualDesktopHotkeyHandler_CreateInstance(*v26, (struct IVirtualDesktopLock *)*v2, v35, this + 23);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v37, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    v83 = 140;
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v37,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x8Cu,
        v86,
        v89);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
      goto LABEL_79;
  }
  v38 = v97;
  v39 = **(__int64 (__fastcall ***)(struct IVirtualDesktopNotification *, GUID *, void **))v97;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 31);
  Instance = v39(v38, &GUID_81ae09de_340b_4b9f_9cba_61bb8e6a8a68, this + 31);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v40, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v40,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x8Eu,
        v86,
        v89);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v86);
      v71 = v96;
      if ( v96 )
      {
        v96 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopDefaultForegroundHandler *))(*(_QWORD *)v71 + 16LL))(v71);
      }
      v72 = v93;
      if ( v93 )
      {
        v93 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopCollection *))(*(_QWORD *)v72 + 16LL))(v72);
      }
      v73 = v94;
      if ( v94 )
      {
        v94 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopPersistence *))(*(_QWORD *)v73 + 16LL))(v73);
      }
      v74 = v95;
      if ( v95 )
      {
        v95 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopFactory *))(*(_QWORD *)v74 + 16LL))(v74);
      }
      v75 = v133;
      if ( v133 )
      {
        v133 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopVisibilityPolicy *))(*(_QWORD *)v75 + 16LL))(v75);
      }
      v76 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(struct IVirtualDesktopNotification *))(*(_QWORD *)v76 + 16LL))(v76);
      }
      return (unsigned int)Instance;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 29);
  v86 = (unsigned __int64 *)*v2;
  Instance = VirtualDesktopAcessibility_CreateInstance(v131, this[31], v93, *v26);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v41, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    v83 = 151;
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v41,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x97u,
        v86,
        v89);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
      goto LABEL_79;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 28);
  Instance = VirtualDesktopGestureHandler_CreateInstance(*v26, v42, this + 28);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v43, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    v83 = 153;
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v43,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0x99u,
        v86,
        v89);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
LABEL_79:
      v50 = v83;
LABEL_80:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        (const char *)(unsigned int)Instance,
        (int)v86);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
LABEL_81:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
LABEL_82:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
LABEL_83:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v133);
      goto LABEL_84;
    }
  }
  v44 = (struct IVirtualDesktopPinnedAppsPrivate **)(this + 27);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 27);
  Instance = VirtualDesktopPinnedAppsHandler_CreateInstance(
               *v26,
               *v14,
               v133,
               v45,
               (struct IVirtualDesktopLock *)*v2,
               (const struct _GUID *)v89,
               this + 27);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v46, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    v84 = 161;
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v46,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0xA1u,
        v86,
        v90);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
      goto LABEL_92;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 24);
  Instance = VirtualDesktopWindowMoveManager_CreateInstance(*v26, v93, v133, *v44, (const struct _GUID *)v86, this + 24);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v47, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance < 0 )
  {
    v84 = 168;
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v47,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0xA8u,
        v86,
        v91);
      Instance = (int)v130;
    }
    if ( Instance < 0 )
    {
LABEL_92:
      v50 = v84;
      goto LABEL_80;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 25);
  Instance = VirtualDesktopsApi_CreateInstance(
               *v26,
               v93,
               v133,
               (struct IVirtualDesktopWindowMoveManager *)this[24],
               (struct IVirtualDesktopLock *)*v2,
               (const struct _GUID *)v91,
               this + 25);
  LODWORD(v130) = Instance;
  if ( !CRVPrivate::cfhImmersiveShellStartup )
  {
    CCriticalFailureHandler::GetFakeFailure(v48, (int *)&v130);
    CRVPrivate::cfhImmersiveShellStartup = 1;
    Instance = (int)v130;
  }
  if ( Instance >= 0 )
    goto LABEL_74;
  if ( Instance != -2147024882 && Instance != -2144862209 )
  {
    CCriticalFailureHandler::HandleFailure(
      v48,
      (int *)&v130,
      L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
      0xB0u,
      v87,
      v92);
    Instance = (int)v130;
  }
  if ( Instance >= 0 )
  {
LABEL_74:
    v102 = *(_OWORD *)&SID_VirtualDesktopManager.Revision;
    v103 = *v26;
    v104 = 0;
    v105 = *(_OWORD *)&SID_VirtualDesktopHotkeyHandler.Revision;
    v106 = this[23];
    v107 = 0;
    v108 = *(_OWORD *)&SID_VirtualDesktopNotificationService.Revision;
    v109 = v97;
    v110 = 0;
    v111 = IID_IVirtualDesktopManager;
    v112 = this[25];
    v113 = 0;
    v114 = *(_OWORD *)&SID_VirtualDesktopAnimationSyncNotificationService.Revision;
    v115 = this[21];
    v116 = 0;
    v117 = *(_OWORD *)&SID_VirtualDesktopTabletModePolicyService.Revision;
    v118 = this[26];
    v119 = 0;
    v120 = IID_IVirtualDesktopAccessibility;
    v121 = this[29];
    v122 = 0;
    v123 = *(_OWORD *)&SID_VirtualDesktopPinnedApps.Revision;
    v124 = *v44;
    v125 = 0;
    v126 = *(_OWORD *)&SID_VirtualDesktopGestureHandler.Revision;
    v127 = this[28];
    v128 = 0;
    Instance = CImmersiveShellComponent::RegisterServiceInformation(
                 (CImmersiveShellComponent *)(this + 5),
                 (const struct CImmersiveShellComponent::ISC_SERVICE *)&v102,
                 9u);
    LODWORD(v130) = Instance;
    if ( !CRVPrivate::cfhImmersiveShellStartup )
    {
      CCriticalFailureHandler::GetFakeFailure(v49, (int *)&v130);
      CRVPrivate::cfhImmersiveShellStartup = 1;
      Instance = (int)v130;
    }
    if ( Instance >= 0 )
      goto LABEL_77;
    if ( Instance != -2147024882 && Instance != -2144862209 )
    {
      CCriticalFailureHandler::HandleFailure(
        v49,
        (int *)&v130,
        L"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
        0xBEu,
        v87,
        v92);
      Instance = (int)v130;
    }
    if ( Instance >= 0 )
    {
LABEL_77:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v96);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v93);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v94);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v95);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v133);
      Instance = 0;
LABEL_84:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
      return (unsigned int)Instance;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
      (const char *)(unsigned int)Instance,
      (int)v87);
    v77 = v96;
    if ( v96 )
    {
      v96 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopDefaultForegroundHandler *))(*(_QWORD *)v77 + 16LL))(v77);
    }
    v78 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopCollection *))(*(_QWORD *)v78 + 16LL))(v78);
    }
    v79 = v94;
    if ( v94 )
    {
      v94 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopPersistence *))(*(_QWORD *)v79 + 16LL))(v79);
    }
    v80 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopFactory *))(*(_QWORD *)v80 + 16LL))(v80);
    }
    v81 = v133;
    if ( v133 )
    {
      v133 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopVisibilityPolicy *))(*(_QWORD *)v81 + 16LL))(v81);
    }
    v82 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopNotification *))(*(_QWORD *)v82 + 16LL))(v82);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"pcshell\\twinui\\virtualdesktops\\lib\\virtualdesktopcomponent.cpp",
      (const char *)(unsigned int)Instance,
      (int)v87);
    v60 = v96;
    if ( v96 )
    {
      v96 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopDefaultForegroundHandler *))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v61 = v93;
    if ( v93 )
    {
      v93 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopCollection *))(*(_QWORD *)v61 + 16LL))(v61);
    }
    v62 = v94;
    if ( v94 )
    {
      v94 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopPersistence *))(*(_QWORD *)v62 + 16LL))(v62);
    }
    v63 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopFactory *))(*(_QWORD *)v63 + 16LL))(v63);
    }
    v64 = v133;
    if ( v133 )
    {
      v133 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopVisibilityPolicy *))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v65 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(struct IVirtualDesktopNotification *))(*(_QWORD *)v65 + 16LL))(v65);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18009bdd0  push    rbp
0x18009bdd2  push    rbx
0x18009bdd3  push    rsi
0x18009bdd4  push    rdi
0x18009bdd5  push    r12
0x18009bdd7  push    r13
0x18009bdd9  push    r14
0x18009bddb  push    r15
0x18009bddd  lea     rbp, [rsp-0B8h]
0x18009bde5  sub     rsp, 1B8h
0x18009bdec  mov     rsi, rcx
0x18009bdef  lea     r15, [rcx+90h]
0x18009bdf6  mov     rcx, r15
0x18009bdf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009bdfe  mov     rdx, r15; void **
0x18009be01  call    ?CVirtualDesktopLock_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CVirtualDesktopLock_CreateInstance(_GUID const &,void * *)
0x18009be06  mov     ebx, eax
0x18009be08  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009be0e  xor     r14d, r14d
0x18009be11  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009be18  jz      loc_18009C5BC
0x18009be1e  mov     edi, 8027FFFFh
0x18009be23  mov     r13d, 8007000Eh
0x18009be29  test    ebx, ebx
0x18009be2b  js      loc_18009CE6C
0x18009be31  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18009be37  mov     r12d, eax
0x18009be3a  mov     [rsp+1F0h+var_190], r14
0x18009be3f  lea     rcx, [rsp+1F0h+var_190]
0x18009be44  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIHolographicViewTransitionNotificationService@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIHolographicViewTransitionNotificationService@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IHolographicViewTransitionNotificationService>>)
0x18009be49  mov     r9, rax; void **
0x18009be4c  mov     rdx, [r15]; struct IVirtualDesktopLock *
0x18009be4f  mov     ecx, r12d; unsigned int
0x18009be52  call    ?CVirtualDesktopNotifications_CreateInstance@@YAJKPEAUIVirtualDesktopLock@@AEBU_GUID@@PEAPEAX@Z; CVirtualDesktopNotifications_CreateInstance(ulong,IVirtualDesktopLock *,_GUID const &,void * *)
0x18009be57  mov     ebx, eax
0x18009be59  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009be5f  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009be66  jz      loc_18009C5DA
0x18009be6c  test    ebx, ebx
0x18009be6e  js      loc_18009CEA4
0x18009be74  mov     [rbp+0F0h+arg_18], r14
0x18009be7b  lea     rcx, [rbp+0F0h+arg_18]
0x18009be82  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009be87  lea     r8, [rbp+0F0h+arg_18]; void **
0x18009be8e  mov     rcx, [rsp+1F0h+var_190]; struct IVirtualDesktopNotification *
0x18009be93  call    ?CVirtualDesktopVisibilityPolicy_CreateInstance@@YAJPEAUIVirtualDesktopNotification@@AEBU_GUID@@PEAPEAX@Z; CVirtualDesktopVisibilityPolicy_CreateInstance(IVirtualDesktopNotification *,_GUID const &,void * *)
0x18009be98  mov     ebx, eax
0x18009be9a  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009bea0  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009bea7  jz      loc_18009C5F8
0x18009bead  test    ebx, ebx
0x18009beaf  js      loc_18009CED9
0x18009beb5  mov     [rsp+1F0h+var_1A0], r14
0x18009beba  lea     rcx, [rsp+1F0h+var_1A0]
0x18009bebf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009bec4  lea     r9, [rsp+1F0h+var_1A0]; void **
0x18009bec9  mov     rdx, [r15]; struct IVirtualDesktopLock *
0x18009becc  mov     rcx, [rbp+0F0h+arg_18]; struct IVirtualDesktopVisibilityPolicy *
0x18009bed3  call    ?CVirtualDesktopFactory_CreateInstance@@YAJPEAUIVirtualDesktopVisibilityPolicy@@PEAUIVirtualDesktopLock@@AEBU_GUID@@PEAPEAX@Z; CVirtualDesktopFactory_CreateInstance(IVirtualDesktopVisibilityPolicy *,IVirtualDesktopLock *,_GUID const &,void * *)
0x18009bed8  mov     ebx, eax
0x18009beda  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009bee0  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009bee7  jz      loc_18009C616
0x18009beed  test    ebx, ebx
0x18009beef  js      loc_18009CF0E
0x18009bef5  lea     r13, [rsi+0F0h]
0x18009befc  mov     rcx, r13
0x18009beff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009bf04  mov     rdx, r13; void **
0x18009bf07  call    ?VirtualDesktopRegistryHelpers_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; VirtualDesktopRegistryHelpers_CreateInstance(_GUID const &,void * *)
0x18009bf0c  mov     ebx, eax
0x18009bf0e  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009bf14  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009bf1b  jz      loc_18009C634
0x18009bf21  test    ebx, ebx
0x18009bf23  js      loc_18009CF43
0x18009bf29  mov     [rsp+1F0h+var_1A8], r14
0x18009bf2e  lea     rcx, [rsp+1F0h+var_1A8]
0x18009bf33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009bf38  lea     r8, [rsp+1F0h+var_1A8]; struct IVirtualDesktopPersistence **
0x18009bf3d  mov     rdx, [r13+0]; struct IVirtualDesktopRegistryHelpers *
0x18009bf41  call    ?CreatePersistence@CVirtualDesktopComponent@@AEAAJPEAUIVirtualDesktopRegistryHelpers@@PEAPEAUIVirtualDesktopPersistence@@@Z; CVirtualDesktopComponent::CreatePersistence(IVirtualDesktopRegistryHelpers *,IVirtualDesktopPersistence * *)
0x18009bf46  mov     ebx, eax
0x18009bf48  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009bf4e  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009bf55  jz      loc_18009C652
0x18009bf5b  test    ebx, ebx
0x18009bf5d  js      loc_18009CF7B
0x18009bf63  mov     [rsp+1F0h+var_1B0], r14
0x18009bf68  lea     rcx, [rsp+1F0h+var_1B0]
0x18009bf6d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009bf72  call    Mirror_IsThreadRTL
0x18009bf77  test    eax, eax
0x18009bf79  setnz   r8b; bool
0x18009bf7d  lea     rax, [rsp+1F0h+var_1B0]
0x18009bf82  mov     [rsp+1F0h+var_1D0], rax; unsigned __int64 *
0x18009bf87  mov     rdx, [rsp+1F0h+var_1A8]; struct IVirtualDesktopPersistence *
0x18009bf8c  mov     rcx, [rsp+1F0h+var_1A0]; struct IVirtualDesktopFactory *
0x18009bf91  call    ?CVirtualDesktopCollection_CreateInstance@@YAJPEAUIVirtualDesktopFactory@@PEAUIVirtualDesktopPersistence@@_NAEBU_GUID@@PEAPEAX@Z; CVirtualDesktopCollection_CreateInstance(IVirtualDesktopFactory *,IVirtualDesktopPersistence *,bool,_GUID const &,void * *)
0x18009bf96  mov     ebx, eax
0x18009bf98  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009bf9e  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009bfa5  jz      loc_18009C670
0x18009bfab  test    ebx, ebx
0x18009bfad  js      loc_18009CFB3
0x18009bfb3  mov     [rsp+1F0h+var_198], r14
0x18009bfb8  lea     rcx, [rsp+1F0h+var_198]
0x18009bfbd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009bfc2  lea     rdx, [rsp+1F0h+var_198]; void **
0x18009bfc7  call    ?CVirtualDesktopDefaultForegroundHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CVirtualDesktopDefaultForegroundHandler_CreateInstance(_GUID const &,void * *)
0x18009bfcc  mov     ebx, eax
0x18009bfce  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009bfd4  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009bfdb  jz      loc_18009C68E
0x18009bfe1  test    ebx, ebx
0x18009bfe3  js      loc_18009CFEB
0x18009bfe9  lea     rdi, [rsi+98h]
0x18009bff0  mov     rcx, rdi
0x18009bff3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009bff8  mov     [rsp+1F0h+var_1D0], rdi; unsigned __int64 *
0x18009bffd  mov     r8, [rsp+1F0h+var_198]; struct IVirtualDesktopDefaultForegroundHandler *
0x18009c002  mov     rdx, [rbp+0F0h+arg_18]; struct IVirtualDesktopVisibilityPolicy *
0x18009c009  mov     rcx, [rsp+1F0h+var_1B0]; struct IVirtualDesktopCollection *
0x18009c00e  call    ?CVirtualDesktopForegroundPolicy_CreateInstance@@YAJPEAUIVirtualDesktopCollection@@PEAUIVirtualDesktopVisibilityPolicy@@PEAUIVirtualDesktopDefaultForegroundHandler@@AEBU_GUID@@PEAPEAX@Z; CVirtualDesktopForegroundPolicy_CreateInstance(IVirtualDesktopCollection *,IVirtualDesktopVisibilityPolicy *,IVirtualDesktopDefaultForegroundHandler *,_GUID const &,void * *)
0x18009c013  mov     ebx, eax
0x18009c015  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009c01b  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, r14b; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c022  jz      loc_18009C6AC
0x18009c028  test    ebx, ebx
0x18009c02a  js      loc_18009D023
0x18009c030  lea     r14, [rsi+0A0h]
0x18009c037  mov     rcx, r14
0x18009c03a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009c03f  mov     rax, [r15]
0x18009c042  mov     [rbp+0F0h+arg_10], rax
0x18009c049  mov     rax, [rsp+1F0h+var_1A8]
0x18009c04e  mov     qword ptr [rsp+1F0h+var_188.Data1], rax
0x18009c053  mov     rax, [rdi]
0x18009c056  mov     qword ptr [rsp+1F0h+var_188.Data4], rax
0x18009c05b  mov     rax, [rsp+1F0h+var_190]
0x18009c060  mov     [rsp+1F0h+var_178], rax
0x18009c065  mov     rax, [rbp+0F0h+arg_18]
0x18009c06c  mov     [rbp+0F0h+var_170], rax
0x18009c070  mov     rax, [rsp+1F0h+var_1B0]
0x18009c075  mov     [rbp+0F0h+var_168], rax
0x18009c079  xor     edi, edi
0x18009c07b  mov     [r14], rdi
0x18009c07e  mov     [rbp+0F0h+arg_0], rdi
0x18009c085  lea     rcx, [rbp+0F0h+arg_0]
0x18009c08c  call    ?InternalRelease@?$ComPtr@VCVirtualDesktopManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CVirtualDesktopManager>::InternalRelease(void)
0x18009c091  lea     rax, [rbp+0F0h+arg_10]
0x18009c098  mov     [rsp+1F0h+var_1B8], rax
0x18009c09d  lea     rax, [rsp+1F0h+var_188]
0x18009c0a2  mov     [rsp+1F0h+var_1C8], rax; unsigned __int64 *
0x18009c0a7  lea     rax, [rsp+1F0h+var_188.Data4]
0x18009c0ac  mov     [rsp+1F0h+var_1D0], rax; unsigned __int64 *
0x18009c0b1  lea     r9, [rsp+1F0h+var_178]
0x18009c0b6  lea     r8, [rbp+0F0h+var_170]
0x18009c0ba  lea     rdx, [rbp+0F0h+var_168]
0x18009c0be  lea     rcx, [rbp+0F0h+arg_0]
0x18009c0c5  call    ??$MakeAndInitialize@VCVirtualDesktopManager@@V1@AEAPEAUIVirtualDesktopCollection@@AEAPEAUIVirtualDesktopVisibilityPolicy@@AEAPEAUIVirtualDesktopNotification@@AEAPEAUIVirtualDesktopForegroundPolicy@@AEAPEAUIVirtualDesktopPersistence@@$$TAEAPEAUIVirtualDesktopLock@@@Details@WRL@Microsoft@@YAJPEAPEAVCVirtualDesktopManager@@AEAPEAUIVirtualDesktopCollection@@AEAPEAUIVirtualDesktopVisibilityPolicy@@AEAPEAUIVirtualDesktopNotification@@AEAPEAUIVirtualDesktopForegroundPolicy@@AEAPEAUIVirtualDesktopPersistence@@$$QEA$$TAEAPEAUIVirtualDesktopLock@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CVirtualDesktopManager,CVirtualDesktopManager,IVirtualDesktopCollection * &,IVirtualDesktopVisibilityPolicy * &,IVirtualDesktopNotification * &,IVirtualDesktopForegroundPolicy * &,IVirtualDesktopPersistence * &,std::nullptr_t,IVirtualDesktopLock * &>(CVirtualDesktopManager * *,IVirtualDesktopCollection * &,IVirtualDesktopVisibilityPolicy * &,IVirtualDesktopNotification * &,IVirtualDesktopForegroundPolicy * &,IVirtualDesktopPersistence * &,$$TAEAPEAUIVirtualDesktopLock &&)
0x18009c0ca  mov     ebx, eax
0x18009c0cc  test    eax, eax
0x18009c0ce  js      loc_18009C8AD
0x18009c0d4  mov     r8, r14
0x18009c0d7  lea     rdx, _GUID_95bb3d6c_9eba_40cc_af4d_1a3255717d9d
0x18009c0de  mov     rcx, [rbp+0F0h+arg_0]
0x18009c0e5  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UIVirtualDesktopManagerPrivate@@UIVirtualDesktopManagerInternal@@UIVirtualDesktopManagerInternal2@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UIVirtualDesktopManagerInternal@@UIVirtualDesktopManagerInternal2@@UISuspendableVirtualDesktopManager@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UIVirtualDesktopManagerPrivate@@UIVirtualDesktopManagerInternal@@UIVirtualDesktopManagerInternal2@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UIVirtualDesktopManagerInternal@@UIVirtualDesktopManagerInternal2@@UISuspendableVirtualDesktopManager@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IVirtualDesktopManagerPrivate,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,ISuspendableVirtualDesktopManager,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IVirtualDesktopManagerPrivate,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,ISuspendableVirtualDesktopManager,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x18009c0ea  mov     ebx, eax
0x18009c0ec  test    eax, eax
0x18009c0ee  js      loc_18009D05F
0x18009c0f4  mov     rcx, [rbp+0F0h+arg_0]
0x18009c0fb  test    rcx, rcx
0x18009c0fe  jz      short loc_18009C10C
0x18009c100  mov     [rbp+0F0h+arg_0], rdi
0x18009c107  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UIVirtualDesktopManagerPrivate@@UIVirtualDesktopManagerInternal@@UIVirtualDesktopManagerInternal2@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@UIVirtualDesktopManagerInternal@@UIVirtualDesktopManagerInternal2@@UISuspendableVirtualDesktopManager@@UIImmersiveWindowMessageNotification@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<IVirtualDesktopManagerPrivate,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IVirtualDesktopManagerInternal,IVirtualDesktopManagerInternal2,ISuspendableVirtualDesktopManager,IImmersiveWindowMessageNotification,Microsoft::WRL::FtmBase>::Release(void)
0x18009c10c  mov     dword ptr [rbp+0F0h+arg_0], ebx
0x18009c112  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, dil; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c119  jz      loc_18009C6CA
0x18009c11f  test    ebx, ebx
0x18009c121  js      loc_18009D069
0x18009c127  mov     byte ptr [rbp+0F0h+arg_0], dil
0x18009c12e  mov     [rbp+0F0h+arg_8], edi
0x18009c134  lea     r8, [rbp+0F0h+arg_8]
0x18009c13b  lea     rdx, [rbp+0F0h+arg_0]
0x18009c142  call    ??$wnf_query_nothrow@W4_TABLETMODESTATE@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAW4_TABLETMODESTATE@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<_TABLETMODESTATE>(_WNF_STATE_NAME const &,bool *,_TABLETMODESTATE *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18009c147  mov     ebx, eax
0x18009c149  mov     dword ptr [rbp+0F0h+arg_10], eax
0x18009c14f  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, dil; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c156  jz      loc_18009C6E8
0x18009c15c  test    ebx, ebx
0x18009c15e  js      loc_18009D0A5
0x18009c164  cmp     byte ptr [rbp+0F0h+arg_0], dil
0x18009c16b  jnz     short loc_18009C173
0x18009c16d  mov     [rbp+0F0h+arg_8], edi
0x18009c173  lea     rdi, [rsi+0D0h]
0x18009c17a  mov     rcx, rdi
0x18009c17d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009c182  mov     [rsp+1F0h+var_1C0], rdi
0x18009c187  mov     rax, [r15]
0x18009c18a  mov     [rsp+1F0h+var_1D0], rax; unsigned __int64 *
0x18009c18f  mov     r9, [rbp+0F0h+arg_18]
0x18009c196  mov     r8, [r14]
0x18009c199  mov     rdx, [rsp+1F0h+var_1B0]
0x18009c19e  mov     ecx, [rbp+0F0h+arg_8]
0x18009c1a4  call    ?VirtualDesktopTabletModePolicy_CreateInstance@@YAJW4_TABLETMODESTATE@@PEAUIVirtualDesktopCollection@@PEAUIVirtualDesktopManagerPrivate@@PEAUIVirtualDesktopVisibilityPolicy@@PEAUIVirtualDesktopLock@@AEBU_GUID@@PEAPEAX@Z; VirtualDesktopTabletModePolicy_CreateInstance(_TABLETMODESTATE,IVirtualDesktopCollection *,IVirtualDesktopManagerPrivate *,IVirtualDesktopVisibilityPolicy *,IVirtualDesktopLock *,_GUID const &,void * *)
0x18009c1a9  mov     ebx, eax
0x18009c1ab  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009c1b1  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, 0; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c1b8  jz      loc_18009C706
0x18009c1be  test    ebx, ebx
0x18009c1c0  js      loc_18009D0E1
0x18009c1c6  mov     rcx, [rsp+1F0h+var_1A8]
0x18009c1cb  mov     rax, [rcx]
0x18009c1ce  mov     r8, [rdi]
0x18009c1d1  mov     [rsp+1F0h+var_1D0], r8; unsigned __int64 *
0x18009c1d6  mov     r9, [rsp+1F0h+var_1B0]
0x18009c1db  mov     r8, [r14]
0x18009c1de  mov     edx, [rbp+0F0h+arg_8]
0x18009c1e4  mov     rax, [rax+28h]
0x18009c1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c1ed  mov     ebx, eax
0x18009c1ef  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009c1f5  xor     edi, edi
0x18009c1f7  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, dil; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c1fe  jz      loc_18009C724
0x18009c204  test    ebx, ebx
0x18009c206  js      loc_18009D11D
0x18009c20c  lea     rbx, [rsi+0A8h]
0x18009c213  mov     rcx, [rbx]
0x18009c216  mov     [rbx], rdi
0x18009c219  test    rcx, rcx
0x18009c21c  jnz     loc_18009D159
0x18009c222  mov     r8, rbx; void **
0x18009c225  mov     ecx, r12d; unsigned int
0x18009c228  call    ?VirtualDesktopAnimationSyncNotifications_CreateInstance@@YAJKAEBU_GUID@@PEAPEAX@Z; VirtualDesktopAnimationSyncNotifications_CreateInstance(ulong,_GUID const &,void * *)
0x18009c22d  mov     ebx, eax
0x18009c22f  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009c235  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, dil; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c23c  jz      loc_18009C742
0x18009c242  test    ebx, ebx
0x18009c244  js      loc_18009D16A
0x18009c24a  lea     rbx, [rsi+0B8h]
0x18009c251  mov     rcx, [rbx]
0x18009c254  mov     [rbx], rdi
0x18009c257  test    rcx, rcx
0x18009c25a  jnz     loc_18009D1A9
0x18009c260  mov     r9, rbx; void **
0x18009c263  mov     rdx, [r15]; struct IVirtualDesktopLock *
0x18009c266  mov     rcx, [r14]; struct IVirtualDesktopManagerPrivate *
0x18009c269  call    ?CVirtualDesktopHotkeyHandler_CreateInstance@@YAJPEAUIVirtualDesktopManagerPrivate@@PEAUIVirtualDesktopLock@@AEBU_GUID@@PEAPEAX@Z; CVirtualDesktopHotkeyHandler_CreateInstance(IVirtualDesktopManagerPrivate *,IVirtualDesktopLock *,_GUID const &,void * *)
0x18009c26e  mov     ebx, eax
0x18009c270  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009c276  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, dil; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c27d  jz      loc_18009C760
0x18009c283  test    ebx, ebx
0x18009c285  js      loc_18009D1BA
0x18009c28b  lea     r12, [rsi+0F8h]
0x18009c292  mov     rbx, [rsp+1F0h+var_190]
0x18009c297  mov     rax, [rbx]
0x18009c29a  mov     rdi, [rax]
0x18009c29d  mov     rcx, r12
0x18009c2a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009c2a5  mov     r8, r12
0x18009c2a8  lea     rdx, _GUID_81ae09de_340b_4b9f_9cba_61bb8e6a8a68
0x18009c2af  mov     rcx, rbx
0x18009c2b2  mov     rax, rdi
0x18009c2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c2ba  mov     ebx, eax
0x18009c2bc  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009c2c2  xor     edi, edi
0x18009c2c4  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, dil; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c2cb  jz      loc_18009C77E
0x18009c2d1  test    ebx, ebx
0x18009c2d3  js      loc_18009D1F9
0x18009c2d9  lea     rbx, [rsi+0E8h]
0x18009c2e0  mov     rcx, rbx
0x18009c2e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009c2e8  mov     [rsp+1F0h+var_1C0], rbx
0x18009c2ed  mov     rax, [r15]
0x18009c2f0  mov     [rsp+1F0h+var_1D0], rax; unsigned __int64 *
0x18009c2f5  mov     r9, [r14]
0x18009c2f8  mov     r8, [rsp+1F0h+var_1B0]
0x18009c2fd  mov     rdx, [r12]
0x18009c301  mov     ecx, [rbp+0F0h+arg_8]
0x18009c307  call    ?VirtualDesktopAcessibility_CreateInstance@@YAJW4_TABLETMODESTATE@@PEAUIVirtualDesktopNotificationServicePrivate@@PEAUIVirtualDesktopCollection@@PEAUIVirtualDesktopManagerPrivate@@PEAUIVirtualDesktopLock@@AEBU_GUID@@PEAPEAX@Z; VirtualDesktopAcessibility_CreateInstance(_TABLETMODESTATE,IVirtualDesktopNotificationServicePrivate *,IVirtualDesktopCollection *,IVirtualDesktopManagerPrivate *,IVirtualDesktopLock *,_GUID const &,void * *)
0x18009c30c  mov     ebx, eax
0x18009c30e  mov     dword ptr [rbp+0F0h+arg_0], eax
0x18009c314  cmp     cs:?cfhImmersiveShellStartup@CRVPrivate@@3VCCriticalFailureHandler@@A, dil; CCriticalFailureHandler CRVPrivate::cfhImmersiveShellStartup
0x18009c31b  jz      loc_18009C79C
0x18009c321  test    ebx, ebx
0x18009c323  js      loc_18009D235
0x18009c329  lea     rbx, [rsi+0E0h]
0x18009c330  mov     rcx, rbx
0x18009c333  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009c338  mov     r8, rbx; void **
0x18009c33b  mov     rcx, [r14]; struct IVirtualDesktopManagerInternal *
0x18009c33e  call    ?VirtualDesktopGestureHandler_CreateInstance@@YAJPEAUIVirtualDesktopManagerInternal@@AEBU_GUID@@PEAPEAX@Z; VirtualDesktopGestureHandler_CreateInstance(IVirtualDesktopManagerInternal *,_GUID const &,void * *)
0x18009c343  mov     ebx, eax
0x18009c345  mov     dword ptr [rbp+0F0h+arg_0], eax
  ... truncated ...
```
