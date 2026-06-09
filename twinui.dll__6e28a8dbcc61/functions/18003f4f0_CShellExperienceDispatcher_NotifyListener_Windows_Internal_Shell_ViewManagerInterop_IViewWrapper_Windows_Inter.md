# CShellExperienceDispatcher::_NotifyListener(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,Windows::Internal::Shell::Experience::ShellExperienceViewState,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18003f4f0`
- end: `0x18003fb81`
- name: `?_NotifyListener@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@W4ShellExperienceViewState@Experience@456@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@6@@Z`
- size: `1681`
- prototype: `int __high(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *, enum Windows::Internal::Shell::Experience::ShellExperienceViewState, HSTRING, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `7`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003eeb0`
- `0x180041040`
- `0x18006150c`
- `0x180061640`
- `0x180061e78`
- `0x1800622c0`
- `0x1800bcb98`

## callees

- `0x180008acc`
- `0x18000ae24`
- `0x18000b838`
- `0x18003c5e4`
- `0x18003c898`
- `0x18003f4f0`
- `0x18003fb88`
- `0x18003fb9c`
- `0x18003fc60`
- `0x180040f14`
- `0x1800e9c10`
- `0x18013d354`
- `0x18014b74c`
- `0x18014b7cc`
- `0x18014c154`
- `0x18014c290`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003f674`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003f674`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003f55d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003f55d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f5c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f65e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f703`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f526`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f5c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f65e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f703`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fb45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f712`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f9d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f979`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f9d5`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003f894`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003f894`

## string_xrefs

- `0x18003f9be`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003fa4d`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003fa93`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003fab0`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003fad2`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003faf6`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18003fb2f`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CShellExperienceDispatcher::_NotifyListener(__int64 a1, __int64 a2, int a3, HSTRING a4, __int64 a5)
{
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rbx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // r8
  _QWORD *v17; // rax
  __int64 v18; // rdi
  HRESULT v19; // eax
  HRESULT v20; // edi
  _QWORD *v21; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rax
  __int64 v24; // r8
  _QWORD *v25; // rax
  __int64 v26; // rdi
  CShellExperienceViewStateChangedEventArgs *v27; // rax
  CShellExperienceViewStateChangedEventArgs *v28; // rdi
  __int64 v29; // rcx
  HSTRING *v30; // rsi
  HRESULT v31; // eax
  unsigned int v32; // esi
  __int64 v33; // rsi
  __int64 v34; // rcx
  __int64 v35; // rdi
  char *v36; // r15
  __int64 v37; // r14
  unsigned int v38; // r12d
  _QWORD *v39; // rax
  _QWORD *v40; // rsi
  char *v41; // rcx
  int v43; // eax
  int v44; // eax
  char *v45; // rcx
  int v46; // [rsp+20h] [rbp-61h]
  char *v47; // [rsp+30h] [rbp-51h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-49h] BYREF
  __int64 v49; // [rsp+40h] [rbp-41h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-39h] BYREF
  HSTRING string; // [rsp+50h] [rbp-31h] BYREF
  __int64 v52; // [rsp+58h] [rbp-29h] BYREF
  char *v53; // [rsp+60h] [rbp-21h] BYREF
  __int64 v54; // [rsp+68h] [rbp-19h] BYREF
  __int64 v55; // [rsp+70h] [rbp-11h] BYREF
  _QWORD v56[10]; // [rsp+80h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]
  __int64 v58; // [rsp+E8h] [rbp+67h] BYREF

  string = 0;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(a2, &string);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24E,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v10,
      v46);
    goto LABEL_48;
  }
  v12 = 0;
  v49 = 0;
  AcquireSRWLockShared((PSRWLOCK)(a1 + 304));
  v52 = a1 + 304;
  v13 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                    a1 + 240,
                    &StringRawBuffer);
  v15 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                    v14,
                    &v47,
                    *v13);
  std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView>(
    &v58,
    *v15,
    v16,
    a2);
  v17 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                    a1 + 240,
                    &StringRawBuffer);
  v18 = v58;
  if ( v58 == *v17 )
  {
    v11 = -2147319765;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)0x8002802BLL,
      v46);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v52);
    goto LABEL_65;
  }
  if ( *(_QWORD *)(v58 + 8) )
  {
    newString = 0;
    WindowsDeleteString(0);
    newString = 0;
    v19 = WindowsDuplicateString(*(HSTRING *)(v18 + 8), &newString);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x265,
        (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shelle"
                      "xperiencedispatcher.cpp",
        (const char *)(unsigned int)v19,
        v46);
      WindowsDeleteString(newString);
      newString = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v52);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      v11 = v20;
      goto LABEL_48;
    }
    v21 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                      a1 + 216,
                      &StringRawBuffer);
    v23 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                      v22,
                      &v47,
                      *v21);
    v56[0] = &string;
    v56[1] = &newString;
    std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ShellExperienceListener_______lambda_753e7ef3057604c3fc660ce988ace198___(
      &v58,
      *v23,
      v24,
      v56);
    v25 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                      a1 + 216,
                      &StringRawBuffer);
    if ( v58 == *v25 )
    {
      LODWORD(v58) = 0;
      v43 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v58);
      if ( v43 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x276,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)(unsigned int)v43,
          v46);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      LODWORD(v47) = a3;
      ShellExperienceDispatcherTelemetry::NotificationDroppedBecauseNoListenerFound<unsigned int,unsigned int &,unsigned short const *>(
        &v47,
        &v58,
        &StringRawBuffer);
    }
    else
    {
      v26 = *(_QWORD *)(v58 + 16);
      if ( v26 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 8LL))(*(_QWORD *)(v58 + 16));
        v12 = v26;
        v49 = v26;
      }
    }
    WindowsDeleteString(newString);
    newString = 0;
    if ( a1 != -304 )
      ReleaseSRWLockShared((PSRWLOCK)(a1 + 304));
    if ( !v12 )
      goto LABEL_47;
    v47 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v47 = 0;
    v27 = (CShellExperienceViewStateChangedEventArgs *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v27 )
    {
      v28 = CShellExperienceViewStateChangedEventArgs::CShellExperienceViewStateChangedEventArgs(v27);
      v58 = 0;
      if ( *((_QWORD *)v28 + 9) != a2 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
        v29 = *((_QWORD *)v28 + 9);
        *((_QWORD *)v28 + 9) = a2;
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      *((_DWORD *)v28 + 24) = a3;
      v30 = (HSTRING *)((char *)v28 + 88);
      if ( a4 && a4 == *v30
        || (WindowsDeleteString(*v30),
            *v30 = 0,
            v31 = WindowsDuplicateString(a4, (HSTRING *)v28 + 11),
            v32 = v31,
            v31 >= 0) )
      {
        v33 = a5;
        if ( *((_QWORD *)v28 + 10) != a5 )
        {
          if ( a5 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
          v34 = *((_QWORD *)v28 + 10);
          *((_QWORD *)v28 + 10) = v33;
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        v47 = (char *)v28 + 48;
        (*(void (__fastcall **)(__int64))(*((_QWORD *)v28 + 6) + 8LL))((__int64)v28 + 48);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs>::Release(v28);
        v35 = (a1 + 160) & -(__int64)(a1 != 0);
        v58 = v35;
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))((a1 + 160) & -(__int64)(a1 != 0));
        v36 = v47;
        v53 = v47;
        if ( v47 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v47 + 8LL))(v47);
        v54 = v12;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
        v37 = (a1 + 160) & -(__int64)(a1 != 0);
        v55 = v37;
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))((a1 + 160) & -(__int64)(a1 != 0));
        v38 = *(_DWORD *)(a1 + 312);
        v39 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
        v40 = v39;
        if ( v39 )
        {
          Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v39);
          v40[2] = 0;
          if ( v40 + 2 != &v53 )
          {
            v40[2] = v36;
            v53 = 0;
          }
          v40[3] = 0;
          if ( v40 + 3 != &v54 )
          {
            v40[3] = v12;
            v54 = 0;
          }
          v40[4] = 0;
          if ( v40 + 4 != &v55 )
          {
            v40[4] = v35;
            v37 = 0;
            v55 = 0;
          }
          *v40 = off_1803A8640;
        }
        else
        {
          v40 = 0;
        }
        v11 = SHTaskPoolQueueTask(3, 2, v38);
        if ( v40 )
          (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
        if ( v37 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        if ( v53 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v53 + 16LL))(v53);
        if ( v11 >= 0 )
        {
          if ( v35 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))((a1 + 160) & -(__int64)(a1 != 0));
          v41 = v47;
          if ( v47 )
          {
            v47 = 0;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))(v41);
          }
LABEL_47:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
          v11 = 0;
          goto LABEL_48;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x28A,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)(unsigned int)v11,
          (int)v40);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
LABEL_65:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
        goto LABEL_48;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\ShellExperienceViewStateChangedEventArgs.h",
        (const char *)(unsigned int)v31,
        v46);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs>::Release(v28);
      Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(&v58);
    }
    else
    {
      v32 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27F,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)v32,
      v46);
    v45 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v45 + 16LL))(v45);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v11 = v32;
  }
  else
  {
    LODWORD(v58) = 0;
    v44 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 48LL))(a2, &v58);
    if ( v44 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x25F,
        (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shelle"
                      "xperiencedispatcher.cpp",
        (const char *)(unsigned int)v44,
        v46);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    LODWORD(v47) = a3;
    ShellExperienceDispatcherTelemetry::NotificationDroppedDueToNoExperienceSet<unsigned int,unsigned int &,unsigned short const *>(
      &v47,
      &v58,
      &StringRawBuffer);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v52);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    v11 = 0;
  }
LABEL_48:
  WindowsDeleteString(string);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003f4f0  push    rbp
0x18003f4f2  push    rbx
0x18003f4f3  push    rsi
0x18003f4f4  push    rdi
0x18003f4f5  push    r12
0x18003f4f7  push    r13
0x18003f4f9  push    r14
0x18003f4fb  push    r15
0x18003f4fd  lea     rbp, [rsp-17h]
0x18003f502  sub     rsp, 98h
0x18003f509  mov     r14, r9
0x18003f50c  mov     r12d, r8d
0x18003f50f  mov     rsi, rdx
0x18003f512  mov     r13, rcx
0x18003f515  mov     [rbp+4Fh+string], 0
0x18003f51d  mov     rax, [rdx]
0x18003f520  mov     rbx, [rax+38h]
0x18003f524  xor     ecx, ecx; string
0x18003f526  call    cs:__imp_WindowsDeleteString
0x18003f52c  mov     [rbp+4Fh+string], 0
0x18003f534  lea     rdx, [rbp+4Fh+string]
0x18003f538  mov     rcx, rsi
0x18003f53b  mov     rax, rbx
0x18003f53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f543  mov     ebx, eax
0x18003f545  test    eax, eax
0x18003f547  js      loc_18003FAA9
0x18003f54d  xor     ebx, ebx
0x18003f54f  mov     [rbp+4Fh+var_90], rbx
0x18003f553  lea     r15, [r13+130h]
0x18003f55a  mov     rcx, r15; SRWLock
0x18003f55d  call    cs:__imp_AcquireSRWLockShared
0x18003f563  mov     [rbp+4Fh+var_78], r15
0x18003f567  lea     rdi, [r13+0F0h]
0x18003f56e  lea     rdx, [rbp+4Fh+var_88]
0x18003f572  mov     rcx, rdi
0x18003f575  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18003f57a  mov     r8, [rax]
0x18003f57d  lea     rdx, [rbp+4Fh+var_A0]
0x18003f581  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x18003f586  mov     r9, rsi
0x18003f589  mov     rdx, [rax]
0x18003f58c  lea     rcx, [rbp+4Fh+arg_8]
0x18003f590  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@std@@VShellExperienceViewFindByView@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@0@V10@V10@VShellExperienceViewFindByView@@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView)
0x18003f595  lea     rdx, [rbp+4Fh+var_88]
0x18003f599  mov     rcx, rdi
0x18003f59c  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18003f5a1  mov     rdi, [rbp+4Fh+arg_8]
0x18003f5a5  cmp     rdi, [rax]
0x18003f5a8  jz      loc_18003FAC6
0x18003f5ae  xor     eax, eax
0x18003f5b0  cmp     [rdi+8], rax
0x18003f5b4  jz      loc_18003F99D
0x18003f5ba  mov     [rbp+4Fh+newString], rax
0x18003f5be  xor     ecx, ecx; string
0x18003f5c0  call    cs:__imp_WindowsDeleteString
0x18003f5c6  mov     [rbp+4Fh+newString], rbx
0x18003f5ca  lea     rdx, [rbp+4Fh+newString]; newString
0x18003f5ce  mov     rcx, [rdi+8]; string
0x18003f5d2  call    cs:__imp_WindowsDuplicateString
0x18003f5d8  mov     edi, eax
0x18003f5da  test    eax, eax
0x18003f5dc  js      loc_18003FB28
0x18003f5e2  lea     rdi, [r13+0D8h]
0x18003f5e9  lea     rdx, [rbp+4Fh+var_88]
0x18003f5ed  mov     rcx, rdi
0x18003f5f0  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18003f5f5  mov     r8, [rax]
0x18003f5f8  lea     rdx, [rbp+4Fh+var_A0]
0x18003f5fc  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x18003f601  lea     rcx, [rbp+4Fh+string]
0x18003f605  mov     [rbp+4Fh+var_50], rcx
0x18003f609  lea     rcx, [rbp+4Fh+newString]
0x18003f60d  mov     [rbp+4Fh+var_48], rcx
0x18003f611  lea     r9, [rbp+4Fh+var_50]
0x18003f615  mov     rdx, [rax]
0x18003f618  lea     rcx, [rbp+4Fh+arg_8]
0x18003f61c  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ShellExperienceListener_______lambda_753e7ef3057604c3fc660ce988ace198___
0x18003f621  lea     rdx, [rbp+4Fh+var_88]
0x18003f625  mov     rcx, rdi
0x18003f628  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18003f62d  mov     rcx, [rbp+4Fh+arg_8]
0x18003f631  cmp     rcx, [rax]
0x18003f634  jz      loc_18003F94D
0x18003f63a  mov     rdi, [rcx+10h]
0x18003f63e  test    rdi, rdi
0x18003f641  jz      short loc_18003F65A
0x18003f643  mov     rax, [rdi]
0x18003f646  mov     rcx, rdi
0x18003f649  mov     rax, [rax+8]
0x18003f64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f652  nop
0x18003f653  mov     rbx, rdi
0x18003f656  mov     [rbp+4Fh+var_90], rbx
0x18003f65a  mov     rcx, [rbp+4Fh+newString]; string
0x18003f65e  call    cs:__imp_WindowsDeleteString
0x18003f664  mov     [rbp+4Fh+newString], 0
0x18003f66c  test    r15, r15
0x18003f66f  jz      short loc_18003F67A
0x18003f671  mov     rcx, r15; SRWLock
0x18003f674  call    cs:__imp_ReleaseSRWLockShared
0x18003f67a  xor     r15d, r15d
0x18003f67d  test    rbx, rbx
0x18003f680  jz      loc_18003F921
0x18003f686  mov     [rbp+4Fh+var_A0], r15
0x18003f68a  lea     rcx, [rbp+4Fh+var_A0]
0x18003f68e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f693  mov     [rbp+4Fh+var_A0], r15
0x18003f697  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f69e  lea     ecx, [r15+68h]; unsigned __int64
0x18003f6a2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f6a7  test    rax, rax
0x18003f6aa  jz      loc_18003FA89
0x18003f6b0  mov     rcx, rax; this
0x18003f6b3  call    ??0CShellExperienceViewStateChangedEventArgs@@QEAA@XZ; CShellExperienceViewStateChangedEventArgs::CShellExperienceViewStateChangedEventArgs(void)
0x18003f6b8  mov     rdi, rax
0x18003f6bb  mov     [rbp+4Fh+arg_8], r15
0x18003f6bf  cmp     [rax+48h], rsi
0x18003f6c3  jz      short loc_18003F6EF
0x18003f6c5  mov     rcx, [rsi]
0x18003f6c8  mov     rax, [rcx+8]
0x18003f6cc  mov     rcx, rsi
0x18003f6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6d4  nop
0x18003f6d5  mov     rcx, [rdi+48h]
0x18003f6d9  mov     [rdi+48h], rsi
0x18003f6dd  test    rcx, rcx
0x18003f6e0  jz      short loc_18003F6EF
0x18003f6e2  mov     rax, [rcx]
0x18003f6e5  mov     rax, [rax+10h]
0x18003f6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f6ee  nop
0x18003f6ef  mov     [rdi+60h], r12d
0x18003f6f3  lea     rsi, [rdi+58h]
0x18003f6f7  test    r14, r14
0x18003f6fa  jnz     loc_18003FA0F
0x18003f700  mov     rcx, [rsi]; string
0x18003f703  call    cs:__imp_WindowsDeleteString
0x18003f709  mov     [rsi], r15
0x18003f70c  mov     rdx, rsi; newString
0x18003f70f  mov     rcx, r14; string
0x18003f712  call    cs:__imp_WindowsDuplicateString
0x18003f718  mov     esi, eax
0x18003f71a  test    eax, eax
0x18003f71c  js      loc_18003FA1D
0x18003f722  mov     rsi, [rbp+4Fh+arg_20]
0x18003f726  cmp     [rdi+50h], rsi
0x18003f72a  jz      short loc_18003F75B
0x18003f72c  test    rsi, rsi
0x18003f72f  jz      short loc_18003F741
0x18003f731  mov     rax, [rsi]
0x18003f734  mov     rcx, rsi
0x18003f737  mov     rax, [rax+8]
0x18003f73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f740  nop
0x18003f741  mov     rcx, [rdi+50h]
0x18003f745  mov     [rdi+50h], rsi
0x18003f749  test    rcx, rcx
0x18003f74c  jz      short loc_18003F75B
0x18003f74e  mov     rax, [rcx]
0x18003f751  mov     rax, [rax+10h]
0x18003f755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f75a  nop
0x18003f75b  lea     rcx, [rdi+30h]
0x18003f75f  mov     [rbp+4Fh+var_A0], rcx
0x18003f763  mov     rax, [rcx]
0x18003f766  mov     rax, [rax+8]
0x18003f76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f76f  nop
0x18003f770  mov     rcx, rdi
0x18003f773  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIShellExperienceViewStateChangedEventArgs@Experience@Shell@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase,Windows::Internal::Shell::Experience::IShellExperienceViewStateChangedEventArgs>::Release(void)
0x18003f778  nop
0x18003f779  mov     rax, r13
0x18003f77c  lea     rcx, [r13+0A0h]
0x18003f783  neg     rax
0x18003f786  sbb     rdi, rdi
0x18003f789  and     rdi, rcx
0x18003f78c  mov     [rbp+4Fh+arg_8], rdi
0x18003f790  jz      short loc_18003F7A2
0x18003f792  mov     rax, [rdi]
0x18003f795  mov     rcx, rdi
0x18003f798  mov     rax, [rax+8]
0x18003f79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7a1  nop
0x18003f7a2  mov     r15, [rbp+4Fh+var_A0]
0x18003f7a6  mov     [rbp+4Fh+var_70], r15
0x18003f7aa  test    r15, r15
0x18003f7ad  jz      short loc_18003F7BF
0x18003f7af  mov     rax, [r15]
0x18003f7b2  mov     rcx, r15
0x18003f7b5  mov     rax, [rax+8]
0x18003f7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7be  nop
0x18003f7bf  mov     [rbp+4Fh+var_68], rbx
0x18003f7c3  test    rbx, rbx
0x18003f7c6  jz      short loc_18003F7D8
0x18003f7c8  mov     rax, [rbx]
0x18003f7cb  mov     rcx, rbx
0x18003f7ce  mov     rax, [rax+8]
0x18003f7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7d7  nop
0x18003f7d8  mov     r14, rdi
0x18003f7db  mov     [rbp+4Fh+var_60], rdi
0x18003f7df  test    rdi, rdi
0x18003f7e2  jz      short loc_18003F7F4
0x18003f7e4  mov     rax, [rdi]
0x18003f7e7  mov     rcx, rdi
0x18003f7ea  mov     rax, [rax+8]
0x18003f7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f7f3  nop
0x18003f7f4  mov     r12d, [r13+138h]
0x18003f7fb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f802  mov     ecx, 28h ; '('; unsigned __int64
0x18003f807  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f80c  mov     rsi, rax
0x18003f80f  test    rax, rax
0x18003f812  jz      loc_18003FB75
0x18003f818  mov     rcx, rax
0x18003f81b  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x18003f820  lea     rax, [rsi+10h]
0x18003f824  mov     qword ptr [rax], 0
0x18003f82b  lea     rcx, [rbp+4Fh+var_70]
0x18003f82f  cmp     rax, rcx
0x18003f832  jz      loc_18003FB6D
0x18003f838  mov     [rax], r15
0x18003f83b  xor     r15d, r15d
0x18003f83e  mov     [rbp+4Fh+var_70], r15
0x18003f842  lea     rcx, [rax+8]
0x18003f846  mov     [rcx], r15
0x18003f849  lea     rdx, [rbp+4Fh+var_68]
0x18003f84d  cmp     rcx, rdx
0x18003f850  jz      short loc_18003F859
0x18003f852  mov     [rcx], rbx
0x18003f855  mov     [rbp+4Fh+var_68], r15
0x18003f859  add     rax, 10h
0x18003f85d  mov     [rax], r15
0x18003f860  lea     rcx, [rbp+4Fh+var_60]
0x18003f864  cmp     rax, rcx
0x18003f867  jz      short loc_18003F873
0x18003f869  mov     [rax], rdi
0x18003f86c  mov     r14, r15
0x18003f86f  mov     [rbp+4Fh+var_60], r15
0x18003f873  lea     rax, off_1803A8640
0x18003f87a  mov     [rsi], rax
0x18003f87d  mov     [rsp+0D0h+var_A8], r15
0x18003f882  mov     qword ptr [rsp+0D0h+var_B0], rsi; int
0x18003f887  xor     r9d, r9d
0x18003f88a  mov     r8d, r12d
0x18003f88d  lea     edx, [r9+2]
0x18003f891  lea     ecx, [rdx+1]
0x18003f894  call    cs:__imp_SHTaskPoolQueueTask
0x18003f89a  mov     ebx, eax
0x18003f89c  test    rsi, rsi
0x18003f89f  jz      short loc_18003F8B1
0x18003f8a1  mov     rdx, [rsi]
0x18003f8a4  mov     rcx, rsi
0x18003f8a7  mov     rax, [rdx+10h]
0x18003f8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8b0  nop
0x18003f8b1  test    r14, r14
0x18003f8b4  jz      short loc_18003F8CA
0x18003f8b6  mov     [rbp+4Fh+var_60], r15
0x18003f8ba  mov     rax, [r14]
0x18003f8bd  mov     rcx, r14
0x18003f8c0  mov     rax, [rax+10h]
0x18003f8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8c9  nop
0x18003f8ca  lea     rcx, [rbp+4Fh+var_68]
0x18003f8ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f8d3  nop
0x18003f8d4  mov     rcx, [rbp+4Fh+var_70]
0x18003f8d8  test    rcx, rcx
0x18003f8db  jz      short loc_18003F8EA
0x18003f8dd  mov     rax, [rcx]
0x18003f8e0  mov     rax, [rax+10h]
0x18003f8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8e9  nop
0x18003f8ea  test    ebx, ebx
0x18003f8ec  js      loc_18003FAEF
0x18003f8f2  test    rdi, rdi
0x18003f8f5  jz      short loc_18003F907
0x18003f8f7  mov     rax, [rdi]
0x18003f8fa  mov     rcx, rdi
0x18003f8fd  mov     rax, [rax+10h]
0x18003f901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f906  nop
0x18003f907  mov     rcx, [rbp+4Fh+var_A0]
0x18003f90b  test    rcx, rcx
0x18003f90e  jz      short loc_18003F921
0x18003f910  mov     [rbp+4Fh+var_A0], r15
0x18003f914  mov     rax, [rcx]
0x18003f917  mov     rax, [rax+10h]
0x18003f91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f920  nop
0x18003f921  lea     rcx, [rbp+4Fh+var_90]
0x18003f925  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003f92a  mov     ebx, r15d
0x18003f92d  mov     rcx, [rbp+4Fh+string]; string
0x18003f931  call    cs:__imp_WindowsDeleteString
0x18003f937  mov     eax, ebx
  ... truncated ...
```
