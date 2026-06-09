# ApplicationTheme::ThemeColorsChangedEvent::AddHandler(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x180007590`
- end: `0x180007dd2`
- name: `?AddHandler@ThemeColorsChangedEvent@ApplicationTheme@@UEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `2114`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007590`
- `0x180007de0`
- `0x180007e00`
- `0x180007e60`
- `0x180007ed8`
- `0x1800083a4`
- `0x180008954`
- `0x1800089e0`
- `0x180008ad0`
- `0x180008b50`
- `0x1800161c0`
- `0x180029660`
- `0x180036c2c`
- `0x180037140`
- `0x18003729c`
- `0x1800419a0`
- `0x180045dec`
- `0x18004b0b4`
- `0x180054130`
- `0x180054500`
- `0x180059b4c`
- `0x180059b70`
- `0x18006f7f8`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007a36`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180007a36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007845`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007aac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007cd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007845`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007aac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007cd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007d1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800075d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007636`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007817`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800075d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007636`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007817`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d65`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007c61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180007c61`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180007b9b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180007b9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007cbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007c3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007cbd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007987`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007987`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180007b7a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180007b7a`

## string_xrefs

- `0x180007bce`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180007c93`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180007ce6`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`
- `0x180007d44`: `onecore\internal\sdk\inc\wil\opensource\wil\registry.h`

## pseudocode

```c
__int64 __fastcall ApplicationTheme::ThemeColorsChangedEvent::AddHandler(
        RTL_SRWLOCK *a1,
        struct IUnknown *a2,
        struct IUnknown **a3)
{
  RTL_SRWLOCK *v4; // r14
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  RTL_SRWLOCK *v7; // r15
  RTL_SRWLOCK *v8; // r13
  unsigned __int64 v9; // rsi
  HKEY v10; // rax
  HKEY v11; // r12
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  unsigned __int64 *v15; // rax
  unsigned __int64 v16; // rdi
  Microsoft::WRL::AgileRef *v17; // rax
  Microsoft::WRL::AgileRef *v18; // rbx
  unsigned __int64 v19; // rax
  void *v20; // rax
  volatile int *v21; // rdx
  __int64 v22; // rcx
  _QWORD *Ptr; // rax
  _QWORD *v24; // rdi
  __int64 *v25; // r14
  RTL_SRWLOCK *v26; // r13
  __int64 *v27; // rsi
  __int64 v28; // rbx
  __int64 v29; // r15
  __int64 v30; // rcx
  struct IUnknown *v31; // rdx
  void *v32; // r8
  __int64 v33; // rdx
  wil::details::registry_watcher_state **v34; // rsi
  wil::details::registry_watcher_state **v35; // rbx
  wil::details::registry_watcher_state **registry_watcher_nothrow; // rax
  wil::details::registry_watcher_state **v37; // rdi
  wil::details::registry_watcher_state *v38; // rsi
  wil::details::registry_watcher_state **v39; // rbx
  unsigned int v40; // ebx
  wil::details::registry_watcher_state *v41; // r12
  LSTATUS v42; // eax
  bool v43; // sf
  _QWORD *v44; // rax
  _QWORD *v45; // rdi
  wil::details *v46; // rcx
  HANDLE Event; // rbx
  wil::details::registry_watcher_state **v49; // rax
  wil::details::registry_watcher_state **v50; // rdi
  wil::details::registry_watcher_state *v51; // rsi
  int LastErrorFailHr; // eax
  unsigned int v53; // eax
  PTP_WAIT ThreadpoolWait; // rax
  const char *v55; // r9
  struct _TP_WAIT *v56; // r13
  struct _TP_WAIT *v57; // r14
  unsigned int v58; // edx
  void *v59; // rdx
  unsigned int v60; // edx
  unsigned int v61; // edx
  DWORD LastError; // ebx
  DWORD dwOptions; // [rsp+28h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  void *v66; // [rsp+60h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v67; // [rsp+68h] [rbp-A0h]
  _QWORD *v68; // [rsp+70h] [rbp-98h] BYREF
  RTL_SRWLOCK *v69; // [rsp+78h] [rbp-90h]
  __int64 v70; // [rsp+80h] [rbp-88h] BYREF
  Microsoft::WRL::AgileRef *v71; // [rsp+88h] [rbp-80h]
  RTL_SRWLOCK *v72; // [rsp+90h] [rbp-78h]
  struct IUnknown *v73; // [rsp+98h] [rbp-70h]
  struct IUnknown **v74; // [rsp+A0h] [rbp-68h]
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-60h]
  __int64 (__fastcall **v76)(); // [rsp+B8h] [rbp-50h] BYREF
  RTL_SRWLOCK *v77; // [rsp+C0h] [rbp-48h]
  __int64 (__fastcall ***v78)(); // [rsp+120h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+170h] [rbp+68h]

  v4 = a1;
  v67 = a1;
  v74 = a3;
  v73 = a2;
  SRWLock = a1 + 11;
  AcquireSRWLockExclusive(a1 + 11);
  if ( !a2 )
  {
    v40 = -2147024809;
    goto LABEL_56;
  }
  QueryInterface = a2->lpVtbl[1].QueryInterface;
  v7 = v4 + 8;
  v8 = v4 + 10;
  v69 = v4 + 8;
  v66 = QueryInterface;
  *a3 = 0;
  v70 = 0;
  v72 = v4 + 10;
  AcquireSRWLockExclusive(v4 + 10);
  if ( v4[8].Ptr )
    v9 = ((__int64)(*((_QWORD *)v4[8].Ptr + 3) - *((_QWORD *)v4[8].Ptr + 2)) >> 3) + 1;
  else
    v9 = 1;
  v10 = (HKEY)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  hKey = v10;
  v11 = v10;
  if ( v10 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(v10);
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *(_QWORD *)v11 = &Microsoft::WRL::Details::EventTargetArray::`vftable';
    v12 = 8 * v9;
    *((_QWORD *)v11 + 4) = 0;
    hKey = 0;
    if ( !is_mul_ok(v9, 8u) )
      v12 = -1;
    v13 = __CFADD__(v12, 8);
    v14 = v12 + 8;
    if ( v13 )
      v14 = -1;
    v15 = (unsigned __int64 *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
    if ( v15 )
    {
      *v15 = v9;
      v16 = v9;
      v17 = (Microsoft::WRL::AgileRef *)(v15 + 1);
      v71 = v17;
      v18 = v17;
      if ( v9 )
      {
        do
        {
          Microsoft::WRL::AgileRef::AgileRef(v18);
          v18 = (Microsoft::WRL::AgileRef *)((char *)v18 + 8);
          --v16;
        }
        while ( v16 );
        v17 = v71;
      }
    }
    else
    {
      v17 = 0;
    }
    *((_QWORD *)v11 + 2) = v17;
    v19 = 8 * v9;
    if ( !is_mul_ok(v9, 8u) )
      v19 = -1;
    v20 = operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
    v22 = *((_QWORD *)v11 + 2);
    *((_QWORD *)v11 + 4) = v20;
    if ( v22 )
    {
      if ( v20 )
      {
        *((_QWORD *)v11 + 3) = v22;
        Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v11 + 3), v21);
        hKey = v11;
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v11);
        Ptr = v7->Ptr;
        if ( v7->Ptr )
        {
          v24 = (_QWORD *)Ptr[2];
          v25 = (__int64 *)Ptr[4];
          if ( v24 != (_QWORD *)Ptr[3] )
          {
            v26 = v7;
            do
            {
              v27 = (__int64 *)*((_QWORD *)v11 + 3);
              v28 = *v24;
              v29 = *v25;
              if ( *v27 != *v24 )
              {
                if ( v28 )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28 + 8LL))(*v24);
                v30 = *v27;
                *v27 = v28;
                if ( v30 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
              }
              ++v25;
              ++v24;
              *(_QWORD *)(*((_QWORD *)v11 + 4) + 8 * ((__int64)(*((_QWORD *)v11 + 3) - *((_QWORD *)v11 + 2)) >> 3)) = v29;
              *((_QWORD *)v11 + 3) += 8LL;
            }
            while ( v24 != *((_QWORD **)v26->Ptr + 3) );
            v8 = v72;
            v7 = v69;
          }
          v4 = v67;
        }
        v31 = v73;
        v32 = v66;
        *v74 = v73;
        Microsoft::WRL::Details::EventTargetArray::AddTail((Microsoft::WRL::Details::EventTargetArray *)v11, v31, v32);
        AcquireSRWLockExclusive(v7 + 1);
        Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v70, v7);
        Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(v7, &hKey);
        if ( v7 != (RTL_SRWLOCK *)-8LL )
          ReleaseSRWLockExclusive(v7 + 1);
        if ( hKey )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(hKey);
        if ( v8 )
          ReleaseSRWLockExclusive(v8);
        if ( v70 )
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v70);
        v34 = (wil::details::registry_watcher_state **)&v4[12];
        if ( v4[12].Ptr )
          goto LABEL_37;
        v77 = v4;
        v76 = off_1800EEAB0;
        v68 = 0;
        v78 = &v76;
        hKey = 0;
        v41 = 0;
        v42 = RegCreateKeyExW(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
                0,
                0,
                0,
                0x10u,
                0,
                &hKey,
                0);
        v43 = v42 < 0;
        if ( v42 > 0 )
          v43 = 1;
        if ( v43 )
        {
          if ( !hKey )
            goto LABEL_74;
          goto LABEL_73;
        }
        v44 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
        v45 = v44;
        if ( !v44 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCBB,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
            (const char *)0x8007000ELL,
            dwOptions);
          goto LABEL_72;
        }
        if ( v78 )
        {
          v44[14] = v44 + 1;
          ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v78)[2])(v78);
          ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v78)[3])(v78);
          v78 = 0;
        }
        else
        {
          v44[14] = 0;
        }
        v45[15] = hKey;
        hKey = 0;
        v45[16] = 0;
        v45[17] = 0;
        *((_BYTE *)v45 + 144) = 0;
        *((_DWORD *)v45 + 37) = 1;
        v45[19] = 0;
        Event = CreateEventExW(0, 0, 0, 0x1F0003u);
        if ( Event )
        {
          GetLastError();
          _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
            v45 + 16,
            Event);
        }
        else
        {
          LastErrorFailHr = wil::details::GetLastErrorFailHr(v46);
          if ( LastErrorFailHr < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCBC,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
              (const char *)(unsigned int)LastErrorFailHr,
              dwOptions);
            wil::details::registry_watcher_state::`scalar deleting destructor'(
              (wil::details::registry_watcher_state *)v45,
              v61);
            goto LABEL_72;
          }
        }
        v53 = RegNotifyChangeKeyValue((HKEY)v45[15], *((unsigned __int8 *)v45 + 144), 0x10000005u, (HANDLE)v45[16], 1);
        if ( v53 )
        {
          wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xCC2,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
            (const char *)v53,
            dwOptionsa);
          wil::details::registry_watcher_state::`scalar deleting destructor'(
            (wil::details::registry_watcher_state *)v45,
            v60);
        }
        else
        {
          ThreadpoolWait = CreateThreadpoolWait(
                             wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::callback,
                             v45,
                             0);
          v56 = (struct _TP_WAIT *)v45[17];
          v57 = ThreadpoolWait;
          if ( v56 )
          {
            LastError = GetLastError();
            wil::details::DestroyThreadPoolWait<0>::Destroy(v56);
            SetLastError(LastError);
          }
          v45[17] = v57;
          if ( v57 )
          {
            v59 = (void *)v45[16];
            v68 = v45;
            v41 = (wil::details::registry_watcher_state *)v45;
            SetThreadpoolWait(v57, v59, 0);
          }
          else
          {
            wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xCC5,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\registry.h",
              v55);
            wil::details::registry_watcher_state::`scalar deleting destructor'(
              (wil::details::registry_watcher_state *)v45,
              v58);
          }
          v4 = v67;
        }
LABEL_72:
        if ( !hKey )
        {
LABEL_74:
          if ( v34 != (wil::details::registry_watcher_state **)&v68 )
          {
            if ( *v34 )
              wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*v34);
            *v34 = v41;
            v68 = 0;
          }
          wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v68);
          if ( v78 )
            ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v78)[3])(v78);
LABEL_37:
          v35 = (wil::details::registry_watcher_state **)&v4[14];
          if ( !v4[14].Ptr )
          {
            v77 = v4;
            v76 = off_1800EEAB0;
            v78 = &v76;
            registry_watcher_nothrow = (wil::details::registry_watcher_state **)wil::make_registry_watcher_nothrow(
                                                                                  &v66,
                                                                                  v33,
                                                                                  L"Control Panel\\Colors");
            v37 = registry_watcher_nothrow;
            if ( v35 != registry_watcher_nothrow )
            {
              v38 = *registry_watcher_nothrow;
              if ( *v35 )
                wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*v35);
              *v35 = v38;
              *v37 = 0;
            }
            wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v66);
            if ( v78 )
              ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v78)[3])(v78);
          }
          v39 = (wil::details::registry_watcher_state **)&v4[13];
          if ( v4[13].Ptr )
          {
            v40 = 0;
          }
          else
          {
            v77 = v4;
            v76 = off_1800EEAF0;
            v78 = &v76;
            v49 = (wil::details::registry_watcher_state **)wil::make_registry_watcher_nothrow(
                                                             &v66,
                                                             v33,
                                                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Accent");
            v50 = v49;
            if ( v39 != v49 )
            {
              v51 = *v49;
              if ( *v39 )
                wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(*v39);
              *v39 = v51;
              *v50 = 0;
            }
            wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v66);
            v40 = 0;
            if ( v78 )
              ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v78)[3])(v78);
          }
          goto LABEL_56;
        }
LABEL_73:
        RegCloseKey(hKey);
        goto LABEL_74;
      }
      Microsoft::WRL::ComPtr<IUnknown>::`vector deleting destructor'();
    }
    operator delete(*((void **)v11 + 4), (const struct std::nothrow_t *)v21);
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 4) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v11);
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (IPopupEventHandler::*)(IPopupWindow *)>::DelegateInvokeHelper<IPopupEventHandler,_lambda_3f7781bf84e6b498cf9989aa99f207ed_,-1,IPopupWindow *>>(&hKey);
  if ( v4 != (RTL_SRWLOCK *)-80LL )
    ReleaseSRWLockExclusive(v4 + 10);
  v40 = -2147024882;
LABEL_56:
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return v40;
}

```

## disassembly

```asm
0x180007590  mov     r11, rsp
0x180007593  push    rbp
0x180007594  push    rbx
0x180007595  lea     rbp, [r11-68h]
0x180007599  sub     rsp, 158h
0x1800075a0  mov     rax, cs:__security_cookie
0x1800075a7  xor     rax, rsp
0x1800075aa  mov     [rbp+60h+var_40], rax
0x1800075ae  mov     [r11-18h], rdi
0x1800075b2  lea     rax, [rcx+58h]
0x1800075b6  mov     [r11-30h], r14
0x1800075ba  mov     rdi, r8
0x1800075bd  mov     r14, rcx
0x1800075c0  mov     [rsp+160h+var_100], rcx
0x1800075c5  mov     rcx, rax; SRWLock
0x1800075c8  mov     [rbp+60h+var_C8], r8
0x1800075cc  mov     rbx, rdx
0x1800075cf  mov     [rbp+60h+var_D0], rdx
0x1800075d3  mov     [rbp+60h+SRWLock], rax
0x1800075d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800075de  nop     dword ptr [rax+rax+00h]
0x1800075e3  test    rbx, rbx
0x1800075e6  jz      loc_180007D2E
0x1800075ec  mov     rax, [rbx]
0x1800075ef  xor     ebx, ebx
0x1800075f1  mov     [rsp+160h+arg_18], rsi
0x1800075f9  mov     [rsp+160h+var_18], r12
0x180007601  mov     [rsp+160h+var_20], r13
0x180007609  mov     rax, [rax+18h]
0x18000760d  mov     [rsp+160h+var_30], r15
0x180007615  lea     r15, [r14+40h]
0x180007619  lea     r13, [r15+10h]
0x18000761d  mov     [rsp+160h+var_F0], r15
0x180007622  mov     rcx, r13; SRWLock
0x180007625  mov     [rsp+160h+var_108], rax
0x18000762a  mov     [rdi], rbx
0x18000762d  mov     [rsp+160h+var_E8], rbx
0x180007632  mov     [rbp+60h+var_D8], r13
0x180007636  call    cs:__imp_AcquireSRWLockExclusive
0x18000763d  nop     dword ptr [rax+rax+00h]
0x180007642  mov     rax, [r15]
0x180007645  test    rax, rax
0x180007648  jnz     loc_180007919
0x18000764e  mov     esi, 1
0x180007653  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000765a  mov     ecx, 28h ; '('; unsigned __int64
0x18000765f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007664  mov     [rsp+160h+hKey], rax
0x180007669  mov     r12, rax
0x18000766c  test    rax, rax
0x18000766f  jz      loc_180007D07
0x180007675  mov     rcx, rax
0x180007678  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(void)
0x18000767d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007684  mov     [r12+10h], rbx
0x180007689  lea     rax, ??_7EventTargetArray@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::EventTargetArray::`vftable'
0x180007690  mov     [r12+18h], rbx
0x180007695  mov     [r12], rax
0x180007699  mov     eax, 8
0x18000769e  mul     rsi
0x1800076a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800076a8  mov     [r12+20h], rbx
0x1800076ad  mov     [rsp+160h+hKey], rbx
0x1800076b2  cmovb   rax, rcx
0x1800076b6  add     rax, 8
0x1800076ba  cmovb   rax, rcx
0x1800076be  mov     rcx, rax; unsigned __int64
0x1800076c1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800076c6  test    rax, rax
0x1800076c9  jz      loc_180007D38
0x1800076cf  mov     [rax], rsi
0x1800076d2  mov     rdi, rsi
0x1800076d5  add     rax, 8
0x1800076d9  mov     [rbp+60h+var_E0], rax
0x1800076dd  mov     rbx, rax
0x1800076e0  test    rsi, rsi
0x1800076e3  jz      short loc_1800076FB
0x1800076e5  mov     rcx, rbx; this
0x1800076e8  call    ??0AgileRef@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::AgileRef::AgileRef(void)
0x1800076ed  add     rbx, 8
0x1800076f1  sub     rdi, 1
0x1800076f5  jnz     short loc_1800076E5
0x1800076f7  mov     rax, [rbp+60h+var_E0]
0x1800076fb  xor     ebx, ebx
0x1800076fd  mov     [r12+10h], rax
0x180007702  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007709  mov     eax, 8
0x18000770e  mul     rsi
0x180007711  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007718  cmovb   rax, rcx
0x18000771c  mov     rcx, rax; unsigned __int64
0x18000771f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007724  mov     rcx, [r12+10h]
0x180007729  mov     [r12+20h], rax
0x18000772e  test    rcx, rcx
0x180007731  jz      loc_180007DB1
0x180007737  test    rax, rax
0x18000773a  jz      loc_180007DAC
0x180007740  mov     [r12+18h], rcx
0x180007745  lea     rcx, [r12+0Ch]; this
0x18000774a  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000774f  mov     rcx, r12
0x180007752  mov     [rsp+160h+hKey], r12
0x180007757  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000775c  mov     rax, [r15]
0x18000775f  test    rax, rax
0x180007762  jz      loc_1800077F8
0x180007768  mov     rdi, [rax+10h]
0x18000776c  mov     r14, [rax+20h]
0x180007770  cmp     rdi, [rax+18h]
0x180007774  jz      short loc_1800077F3
0x180007776  mov     r13, r15
0x180007779  nop     dword ptr [rax+00000000h]
0x180007780  mov     rsi, [r12+18h]
0x180007785  mov     rbx, [rdi]
0x180007788  mov     r15, [r14]
0x18000778b  cmp     [rsi], rbx
0x18000778e  jz      short loc_1800077BB
0x180007790  test    rbx, rbx
0x180007793  jz      short loc_1800077A4
0x180007795  mov     rax, [rbx]
0x180007798  mov     rcx, rbx
0x18000779b  mov     rax, [rax+8]
0x18000779f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077a4  mov     rcx, [rsi]
0x1800077a7  mov     [rsi], rbx
0x1800077aa  test    rcx, rcx
0x1800077ad  jz      short loc_1800077BB
0x1800077af  mov     rax, [rcx]
0x1800077b2  mov     rax, [rax+10h]
0x1800077b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077bb  mov     rcx, [r12+18h]
0x1800077c0  add     r14, 8
0x1800077c4  sub     rcx, [r12+10h]
0x1800077c9  add     rdi, 8
0x1800077cd  mov     rax, [r12+20h]
0x1800077d2  sar     rcx, 3
0x1800077d6  mov     [rax+rcx*8], r15
0x1800077da  add     qword ptr [r12+18h], 8
0x1800077e0  mov     rax, [r13+0]
0x1800077e4  cmp     rdi, [rax+18h]
0x1800077e8  jnz     short loc_180007780
0x1800077ea  mov     r13, [rbp+60h+var_D8]
0x1800077ee  mov     r15, [rsp+160h+var_F0]
0x1800077f3  mov     r14, [rsp+160h+var_100]
0x1800077f8  mov     rax, [rbp+60h+var_C8]
0x1800077fc  mov     rcx, r12; this
0x1800077ff  mov     rdx, [rbp+60h+var_D0]; struct IUnknown *
0x180007803  mov     r8, [rsp+160h+var_108]; void *
0x180007808  mov     [rax], rdx
0x18000780b  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x180007810  lea     rbx, [r15+8]
0x180007814  mov     rcx, rbx; SRWLock
0x180007817  call    cs:__imp_AcquireSRWLockExclusive
0x18000781e  nop     dword ptr [rax+rax+00h]
0x180007823  mov     rdx, r15
0x180007826  lea     rcx, [rsp+160h+var_E8]
0x18000782b  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180007830  lea     rdx, [rsp+160h+hKey]
0x180007835  mov     rcx, r15
0x180007838  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x18000783d  test    rbx, rbx
0x180007840  jz      short loc_180007851
0x180007842  mov     rcx, rbx; SRWLock
0x180007845  call    cs:__imp_ReleaseSRWLockExclusive
0x18000784c  nop     dword ptr [rax+rax+00h]
0x180007851  mov     rcx, [rsp+160h+hKey]
0x180007856  test    rcx, rcx
0x180007859  jz      short loc_180007860
0x18000785b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180007860  test    r13, r13
0x180007863  jnz     loc_180007CCE
0x180007869  mov     rcx, [rsp+160h+var_E8]
0x18000786e  test    rcx, rcx
0x180007871  jz      short loc_180007878
0x180007873  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180007878  cmp     qword ptr [r14+60h], 0
0x18000787d  lea     rsi, [r14+60h]
0x180007881  jz      loc_18000792D
0x180007887  cmp     qword ptr [r14+70h], 0
0x18000788c  lea     rbx, [r14+70h]
0x180007890  jnz     short loc_180007903
0x180007892  lea     rax, off_1800EEAB0
0x180007899  mov     [rbp+60h+var_A8], r14
0x18000789d  mov     [rbp+60h+var_B0], rax
0x1800078a1  lea     r8, aControlPanelCo; "Control Panel\\Colors"
0x1800078a8  lea     rax, [rbp+60h+var_B0]
0x1800078ac  mov     [rbp+60h+var_48], rax
0x1800078b0  lea     rcx, [rsp+160h+var_108]
0x1800078b5  lea     rax, [rbp+60h+var_B8]
0x1800078b9  mov     qword ptr [rsp+160h+dwOptions], rax
0x1800078be  call    ?make_registry_watcher_nothrow@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::make_registry_watcher_nothrow(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800078c3  mov     rdi, rax
0x1800078c6  cmp     rbx, rax
0x1800078c9  jz      short loc_1800078E4
0x1800078cb  mov     rcx, [rbx]; this
0x1800078ce  mov     rsi, [rax]
0x1800078d1  test    rcx, rcx
0x1800078d4  jnz     loc_180007D98
0x1800078da  mov     [rbx], rsi
0x1800078dd  mov     qword ptr [rdi], 0
0x1800078e4  lea     rcx, [rsp+160h+var_108]
0x1800078e9  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x1800078ee  mov     rcx, [rbp+60h+var_48]
0x1800078f2  test    rcx, rcx
0x1800078f5  jz      short loc_180007903
0x1800078f7  mov     rax, [rcx]
0x1800078fa  mov     rax, [rax+18h]
0x1800078fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007903  cmp     qword ptr [r14+68h], 0
0x180007908  lea     rbx, [r14+68h]
0x18000790c  jz      loc_180007AD1
0x180007912  xor     ebx, ebx
0x180007914  jmp     loc_180007A73
0x180007919  mov     rsi, [rax+18h]
0x18000791d  sub     rsi, [rax+10h]
0x180007921  sar     rsi, 3
0x180007925  inc     rsi
0x180007928  jmp     loc_180007653
0x18000792d  xor     ebx, ebx
0x18000792f  mov     [rbp+60h+var_A8], r14
0x180007933  mov     [rsp+40h], rbx; lpdwDisposition
0x180007938  lea     rax, off_1800EEAB0
0x18000793f  mov     [rbp+60h+var_B0], rax
0x180007943  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000794a  lea     rax, [rbp+60h+var_B0]
0x18000794e  mov     [rsp+160h+var_F8], rbx
0x180007953  mov     [rbp+60h+var_48], rax
0x180007957  xor     r9d, r9d; lpClass
0x18000795a  lea     rax, [rsp+160h+hKey]
0x18000795f  mov     [rsp+160h+hKey], rbx
0x180007964  mov     [rsp+160h+phkResult], rax; phkResult
0x180007969  xor     r8d, r8d; Reserved
0x18000796c  mov     [rsp+160h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180007971  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180007978  mov     [rsp+160h+samDesired], 10h; samDesired
0x180007980  mov     r12d, ebx
0x180007983  mov     [rsp+160h+dwOptions], ebx; int
0x180007987  call    cs:__imp_RegCreateKeyExW
0x18000798e  nop     dword ptr [rax+rax+00h]
0x180007993  test    eax, eax
0x180007995  jg      loc_180007C80
0x18000799b  js      loc_180007CAF
0x1800079a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800079a8  mov     ecx, 0A0h; unsigned __int64
0x1800079ad  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800079b2  mov     rdi, rax
0x1800079b5  test    rax, rax
0x1800079b8  jz      loc_180007C8F
0x1800079be  cmp     [rbp+60h+var_48], rbx
0x1800079c2  jz      loc_180007C77
0x1800079c8  lea     rdx, [rax+8]
0x1800079cc  mov     [rax+70h], rdx
0x1800079d0  mov     rcx, [rbp+60h+var_48]
0x1800079d4  mov     rax, [rcx]
0x1800079d7  mov     rax, [rax+10h]
0x1800079db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e0  mov     rcx, [rbp+60h+var_48]
0x1800079e4  mov     rax, [rcx]
0x1800079e7  mov     rax, [rax+18h]
0x1800079eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f0  mov     [rbp+60h+var_48], rbx
0x1800079f4  mov     rax, [rsp+160h+hKey]
0x1800079f9  mov     r9d, 1F0003h; dwDesiredAccess
0x1800079ff  mov     [rdi+78h], rax
0x180007a03  xor     r8d, r8d; dwFlags
0x180007a06  mov     [rsp+160h+hKey], rbx
0x180007a0b  xor     eax, eax
0x180007a0d  mov     [rdi+80h], rbx
0x180007a14  xor     edx, edx; lpName
0x180007a16  mov     [rdi+88h], rbx
0x180007a1d  xor     ecx, ecx; lpEventAttributes
0x180007a1f  mov     [rdi+90h], bl
0x180007a25  mov     dword ptr [rdi+94h], 1
0x180007a2f  mov     [rdi+98h], rax
0x180007a36  call    cs:__imp_CreateEventExW
0x180007a3d  nop     dword ptr [rax+rax+00h]
0x180007a42  mov     rbx, rax
0x180007a45  test    rax, rax
0x180007a48  jz      loc_180007B4D
0x180007a4e  call    cs:__imp_GetLastError
0x180007a55  nop     dword ptr [rax+rax+00h]
0x180007a5a  mov     rdx, rbx
0x180007a5d  lea     rcx, [rdi+80h]
0x180007a64  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007a69  jmp     loc_180007B5A
0x180007a6e  mov     ebx, 8007000Eh
0x180007a73  mov     r13, [rsp+160h+var_20]
0x180007a7b  mov     r12, [rsp+160h+var_18]
0x180007a83  mov     rsi, [rsp+160h+arg_18]
0x180007a8b  mov     r15, [rsp+160h+var_30]
0x180007a93  mov     rcx, [rbp+60h+SRWLock]; SRWLock
0x180007a97  mov     r14, [rsp+160h+var_28]
0x180007a9f  mov     rdi, [rsp+150h]
0x180007aa7  test    rcx, rcx
0x180007aaa  jz      short loc_180007AB8
0x180007aac  call    cs:__imp_ReleaseSRWLockExclusive
0x180007ab3  nop     dword ptr [rax+rax+00h]
0x180007ab8  mov     eax, ebx
0x180007aba  mov     rcx, [rbp+60h+var_40]
  ... truncated ...
```
