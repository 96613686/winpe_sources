# kfapi::CKFFacade::RebuildKnownFolderCacheIfNeeded(void)

- ea: `0x180032fc0`
- end: `0x180033883`
- name: `?RebuildKnownFolderCacheIfNeeded@CKFFacade@kfapi@@AEAAJXZ`
- size: `2243`
- prototype: `__int64 __fastcall(kfapi::CKFFacade *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800329e0`

## callees

- `0x180031900`
- `0x180031a78`
- `0x180031aa4`
- `0x180031fa8`
- `0x180032664`
- `0x1800326dc`
- `0x180032e64`
- `0x180032eb8`
- `0x180032f1c`
- `0x180032fc0`
- `0x180033890`
- `0x180033a40`
- `0x180033bb8`
- `0x180033c60`
- `0x180034a40`
- `0x180036df0`
- `0x180038f50`
- `0x180063050`
- `0x180078030`
- `0x180297864`
- `0x18038f984`
- `0x1803b243c`
- `0x1804efdfc`
- `0x1804efe40`
- `0x1804f23ac`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033012`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003353c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003373e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180033012`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003353c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003373e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180032fea`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800330ac`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800330ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800331c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003343f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033477`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800334a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800334fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800336c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800336dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033795`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800337c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033819`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003385f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800331c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003343f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033477`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800334a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800334fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800336c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800336dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033795`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800337c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033819`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003385f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003308a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003308a`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
__int64 __fastcall kfapi::CKFFacade::RebuildKnownFolderCacheIfNeeded(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // r15
  unsigned int v2; // r13d
  RTL_SRWLOCK *v3; // r14
  char *Ptr; // rbx
  char *k; // rax
  __int64 v7; // rax
  const WCHAR *v8; // r12
  __int64 v9; // r13
  const WCHAR *StringRawBuffer; // rax
  _BYTE *v11; // rax
  char *j; // rax
  RTL_SRWLOCK *v13; // r15
  unsigned __int16 *v14; // rsi
  unsigned __int16 *v15; // rax
  char v16; // si
  unsigned __int16 *v17; // rax
  std::_Ref_count_base *v18; // r12
  int FolderDefinition; // eax
  winrt::impl *v20; // rdi
  PWSTR *v21; // rax
  _QWORD *v22; // rsi
  int v23; // eax
  unsigned int v24; // ebx
  RTL_SRWLOCK *v25; // r13
  __int64 v26; // rax
  char *v27; // rsi
  __int128 v28; // xmm0
  volatile signed __int32 *v29; // rax
  unsigned int v30; // r8d
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rdx
  struct winrt::impl::hstring_header *v33; // rdx
  int FolderIds; // eax
  const QITAB *i; // rdi
  const KNOWNFOLDERID *piid; // rsi
  PWSTR *v37; // rax
  unsigned __int16 **v38; // rax
  kfapi::CKFFacade *v39; // rcx
  int v40; // eax
  char *v41; // rdx
  KNOWNFOLDERID v42; // xmm0
  std::_Ref_count_base *v43; // rbx
  struct winrt::impl::hstring_header *v44; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v47; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v48; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v49; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  winrt::impl *v51; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 length[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v53; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v54[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v55; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v56[16]; // [rsp+90h] [rbp-70h] BYREF
  RTL_SRWLOCK *v57; // [rsp+A0h] [rbp-60h]
  RTL_SRWLOCK *v58; // [rsp+A8h] [rbp-58h]
  _BYTE v59[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v60; // [rsp+C0h] [rbp-40h]
  _QWORD v61[14]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v1 = this;
  v58 = this;
  v2 = 0;
  v3 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  v61[2] = v3;
  if ( LOBYTE(v1[6].Ptr) || v1[8].Ptr )
  {
LABEL_3:
    if ( v3 )
      ReleaseSRWLockExclusive(v3);
    return 0;
  }
  wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v56);
  v53 = 0;
  FolderIds = kfapi::CKFFacade::GetFolderIds(v1, v56, &v53);
  v24 = FolderIds;
  if ( FolderIds < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\kffacade.cpp",
      (const char *)(unsigned int)FolderIds,
      bIgnoreCase);
LABEL_106:
    wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v56);
    if ( v3 )
      ReleaseSRWLockExclusive(v3);
    return v24;
  }
  for ( i = (const QITAB *)off_180683DE0; i != &`CItem::QueryInterface'::`2'::qit; i = (const QITAB *)((char *)i + 8) )
  {
    piid = i->piid;
    v47 = 0;
    v37 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v47);
    if ( SHGetKnownFolderPath(piid, 0x4000u, 0, v37) < 0 )
      goto LABEL_99;
    v48 = 0;
    v38 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v48);
    v40 = kfapi::CKFFacade::AddNamespaceMapPathPrefix(v39, v47, v38);
    v24 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\kffacade.cpp",
        (const char *)(unsigned int)v40,
        bIgnoreCase);
      if ( v48 )
        CoTaskMemFree(v48);
      if ( v47 )
        CoTaskMemFree(v47);
      goto LABEL_106;
    }
    v41 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v57 = (RTL_SRWLOCK *)v41;
    if ( v41 )
    {
      v42 = *piid;
      *(_QWORD *)v41 = v47;
      v47 = 0;
      *(KNOWNFOLDERID *)(v41 + 8) = v42;
    }
    std::shared_ptr<kfapi::KnownFolderCacheItem>::shared_ptr<kfapi::KnownFolderCacheItem>(v54);
    if ( !v54[0] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\kffacade.cpp",
        (const char *)0x8007000ELL,
        bIgnoreCase);
      if ( v54[1] )
        std::_Ref_count_base::_Decref(v54[1]);
      if ( v48 )
        CoTaskMemFree(v48);
      if ( v47 )
        CoTaskMemFree(v47);
      wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v56);
      if ( v3 )
        goto LABEL_83;
      return 2147942414LL;
    }
    v57 = (RTL_SRWLOCK *)&v55;
    v55 = 0;
    v43 = v54[1];
    if ( v54[1] )
      _InterlockedIncrement((volatile signed __int32 *)v54[1] + 2);
    v55 = *(_OWORD *)v54;
    winrt::hstring::hstring((winrt::hstring *)&v51, v48);
    pv = winrt::impl::duplicate_hstring(v51, v44);
    WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<kfapi::KnownFolderCacheItem>,nt_path_segment_tokenizer<unsigned short>>::Insert(
      &v1[4],
      pv,
      &v55);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&pv);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
    if ( v43 )
      std::_Ref_count_base::_Decref(v43);
    if ( v48 )
      CoTaskMemFree(v48);
LABEL_99:
    if ( v47 )
      CoTaskMemFree(v47);
  }
  while ( 1 )
  {
    v49 = v2;
    if ( v2 >= v53 )
    {
      wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v56);
      goto LABEL_3;
    }
    v51 = 0;
    v18 = (std::_Ref_count_base *)wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](
                                    v56,
                                    v2);
    v54[0] = v18;
    FolderDefinition = kfapi::CKFFacade::GetFolderDefinition(v1, v18, &v51);
    v20 = v51;
    if ( FolderDefinition < 0 || *((_DWORD *)v51 + 4) != 1 )
      break;
    (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v51 + 16LL))(v51);
LABEL_42:
    ++v2;
  }
  v47 = 0;
  v21 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v47);
  if ( SHGetKnownFolderPath((const KNOWNFOLDERID *const)v18, 0x4000u, 0, v21) < 0 )
    goto LABEL_66;
  pv = 0;
  v22 = (_QWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  *(_QWORD *)length = 0;
  v23 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          length,
          L"\\%s",
          v47);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\kffacade.cpp",
      (const char *)(unsigned int)v23,
      bIgnoreCase);
    if ( *(_QWORD *)length )
      CoTaskMemFree(*(LPVOID *)length);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\kffacade.cpp",
      (const char *)v24,
      bIgnoreCasea);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v47 )
      CoTaskMemFree(v47);
    wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v51);
    goto LABEL_106;
  }
  *v22 = *(_QWORD *)length;
  v25 = v1 + 4;
  v57 = v1 + 4;
  v26 = -1;
  do
    ++v26;
  while ( *((_WORD *)pv + v26) );
  v13 = v1 + 4;
  Ptr = (char *)v25[3].Ptr;
  v61[0] = pv;
  v61[1] = v26;
  split_string<unsigned short,std::basic_string_view<unsigned short> (*)(std::basic_string_view<unsigned short>)>(
    &v48,
    v61);
  if ( !v48 )
    goto LABEL_22;
  (*(void (__fastcall **)(unsigned __int16 *))v48)(v48);
  v14 = v48;
  if ( !v48[4] )
  {
    std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::promise_type::_Rethrow_if_exception(v48 - 16);
LABEL_22:
    v14 = 0;
  }
  while ( v14 )
  {
    *(_QWORD *)&v55 = v14 - 16;
    v7 = *((_QWORD *)v14 - 4);
    v8 = *(const WCHAR **)v7;
    v9 = *(_QWORD *)(v7 + 8);
    Ptr = *(char **)v13[3].Ptr;
    while ( Ptr != v13[3].Ptr )
    {
      length[0] = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)Ptr + 4), length);
      if ( CompareStringOrdinal(v8, v9, StringRawBuffer, length[0], 1) == 2 )
        goto LABEL_17;
      v11 = (_BYTE *)*((_QWORD *)Ptr + 2);
      if ( v11[25] )
      {
        for ( j = (char *)*((_QWORD *)Ptr + 1); !j[25]; j = (char *)*((_QWORD *)j + 1) )
        {
          if ( Ptr != *((char **)j + 2) )
            break;
          Ptr = j;
        }
        Ptr = j;
      }
      else
      {
        Ptr = (char *)*((_QWORD *)Ptr + 2);
        for ( k = *(char **)v11; !k[25]; k = *(char **)k )
          Ptr = k;
      }
    }
    Ptr = (char *)v13[3].Ptr;
LABEL_17:
    if ( Ptr == v13[3].Ptr )
    {
      v17 = v48;
      if ( v48 )
      {
        *((_QWORD *)v48 + 1) |= 1uLL;
        (*(void (__fastcall **)(unsigned __int16 *))v17)(v48);
      }
      goto LABEL_31;
    }
    v13 = (RTL_SRWLOCK *)(Ptr + 40);
    (*(void (__fastcall **)(unsigned __int16 *))v14)(v14);
    if ( !v14[4] )
    {
      v14 = 0;
      std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::promise_type::_Rethrow_if_exception(v55);
    }
  }
  v15 = v48;
  if ( v48 )
  {
    *((_QWORD *)v48 + 1) |= 1uLL;
    (*(void (__fastcall **)(unsigned __int16 *))v15)(v48);
  }
  if ( v13[3].Ptr == Ptr )
  {
LABEL_31:
    v16 = 0;
    goto LABEL_32;
  }
  v16 = 0;
  v60 = 0;
  if ( !Ptr[56] )
    goto LABEL_33;
  std::shared_ptr<GraphRecentItemsManager::InstanceManager::PendingOperation>::shared_ptr<GraphRecentItemsManager::InstanceManager::PendingOperation>(
    v59,
    Ptr + 40);
  v16 = 1;
LABEL_32:
  v60 = v16;
LABEL_33:
  if ( v16 )
  {
    std::shared_ptr<kfapi::KnownFolderCacheItem>::`scalar deleting destructor'(v59);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v47 )
      CoTaskMemFree(v47);
    if ( v20 )
      (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v20 + 16LL))(v20);
    v2 = v49;
LABEL_41:
    v1 = v58;
    goto LABEL_42;
  }
  v27 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&v55 = v27;
  if ( v27 )
  {
    v28 = *(_OWORD *)v54[0];
    *(_QWORD *)v27 = v47;
    v47 = 0;
    *(_OWORD *)(v27 + 8) = v28;
  }
  else
  {
    v27 = 0;
  }
  v29 = (volatile signed __int32 *)operator new(0x18u);
  v31 = v29;
  if ( v29 )
  {
    *((_DWORD *)v29 + 2) = 1;
    *((_DWORD *)v29 + 3) = 1;
    *(_QWORD *)v29 = &std::_Ref_count<kfapi::KnownFolderCacheItem>::`vftable';
    *((_QWORD *)v29 + 2) = v27;
  }
  else
  {
    v31 = 0;
  }
  v61[3] = v27;
  v61[4] = v31;
  if ( v27 )
  {
    v54[0] = (std::_Ref_count_base *)length;
    *(_OWORD *)length = 0;
    if ( v31 )
      _InterlockedIncrement(v31 + 2);
    *(_QWORD *)length = v27;
    *(_QWORD *)&length[2] = v31;
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)pv + v32) );
    *(_QWORD *)&v55 = winrt::impl::create_hstring_on_heap((winrt::impl *)pv, (winrt::impl *)v32, v30);
    v54[0] = winrt::impl::duplicate_hstring((winrt::impl *)v55, v33);
    WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<kfapi::KnownFolderCacheItem>,nt_path_segment_tokenizer<unsigned short>>::Insert(
      v57,
      v54[0],
      length);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v54);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v55);
    if ( v31 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v31);
    if ( pv )
      CoTaskMemFree(pv);
    v2 = v49;
LABEL_66:
    if ( v47 )
      CoTaskMemFree(v47);
    if ( v20 )
      (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_41;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9D,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\kfapi\\kffacade.cpp",
    (const char *)0x8007000ELL,
    bIgnoreCase);
  if ( v31 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v31);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v47 )
    CoTaskMemFree(v47);
  if ( v20 )
    (*(void (__fastcall **)(winrt::impl *))(*(_QWORD *)v20 + 16LL))(v20);
  wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(v56);
  if ( !v3 )
    return 2147942414LL;
LABEL_83:
  ReleaseSRWLockExclusive(v3);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180032fc0  push    rbp
0x180032fc2  push    rbx
0x180032fc3  push    rsi
0x180032fc4  push    rdi
0x180032fc5  push    r12
0x180032fc7  push    r13
0x180032fc9  push    r14
0x180032fcb  push    r15
0x180032fcd  lea     rbp, [rsp-8]
0x180032fd2  sub     rsp, 108h
0x180032fd9  mov     r15, rcx
0x180032fdc  mov     [rbp+40h+var_98], rcx
0x180032fe0  xor     r13d, r13d
0x180032fe3  lea     r14, [rcx+18h]
0x180032fe7  mov     rcx, r14; SRWLock
0x180032fea  call    cs:__imp_AcquireSRWLockExclusive
0x180032ff1  nop     dword ptr [rax+rax+00h]
0x180032ff6  mov     [rbp+40h+var_60], r14
0x180032ffa  cmp     [r15+30h], r13b
0x180032ffe  jnz     short loc_18003300A
0x180033000  cmp     [r15+40h], r13
0x180033004  jz      loc_180033560
0x18003300a  test    r14, r14
0x18003300d  jz      short loc_18003301E
0x18003300f  mov     rcx, r14; SRWLock
0x180033012  call    cs:__imp_ReleaseSRWLockExclusive
0x180033019  nop     dword ptr [rax+rax+00h]
0x18003301e  xor     eax, eax
0x180033020  add     rsp, 108h
0x180033027  pop     r15
0x180033029  pop     r14
0x18003302b  pop     r13
0x18003302d  pop     r12
0x18003302f  pop     rdi
0x180033030  pop     rsi
0x180033031  pop     rbx
0x180033032  pop     rbp
0x180033033  retn
0x180033035  mov     rbx, rax
0x180033038  mov     rax, [rax]
0x18003303b  cmp     byte ptr [rax+19h], 0
0x18003303f  jnz     short loc_180033070
0x180033041  mov     rbx, rax
0x180033044  mov     rcx, [rax]
0x180033047  mov     rax, rcx
0x18003304a  cmp     byte ptr [rcx+19h], 0
0x18003304e  jz      short loc_180033041
0x180033050  jmp     short loc_180033070
0x180033052  lea     rax, [rsi-20h]
0x180033056  mov     qword ptr [rbp+40h+var_C0], rax
0x18003305a  mov     rax, [rax]
0x18003305d  mov     r12, [rax]
0x180033060  mov     r13, [rax+8]
0x180033064  mov     rbx, [r15+18h]
0x180033068  mov     rbx, [rbx]
0x18003306b  nop     dword ptr [rax+rax+00h]
0x180033070  mov     rax, [r15+18h]
0x180033074  cmp     rbx, rax
0x180033077  jz      short loc_1800330E0
0x180033079  mov     [rsp+140h+length], 0
0x180033081  lea     rdx, [rsp+140h+length]; length
0x180033086  mov     rcx, [rbx+20h]; string
0x18003308a  call    cs:__imp_WindowsGetStringRawBuffer
0x180033091  nop     dword ptr [rax+rax+00h]
0x180033096  mov     [rsp+140h+bIgnoreCase], 1; bIgnoreCase
0x18003309e  mov     r9d, [rsp+140h+length]; cchCount2
0x1800330a3  mov     r8, rax; lpString2
0x1800330a6  mov     edx, r13d; cchCount1
0x1800330a9  mov     rcx, r12; lpString1
0x1800330ac  call    cs:__imp_CompareStringOrdinal
0x1800330b3  nop     dword ptr [rax+rax+00h]
0x1800330b8  cmp     eax, 2
0x1800330bb  jz      short loc_1800330E3
0x1800330bd  mov     rax, [rbx+10h]
0x1800330c1  cmp     byte ptr [rax+19h], 0
0x1800330c5  jz      loc_180033035
0x1800330cb  mov     rax, [rbx+8]
0x1800330cf  cmp     byte ptr [rax+19h], 0
0x1800330d3  jnz     short loc_1800330DB
0x1800330d5  cmp     rbx, [rax+10h]
0x1800330d9  jz      short loc_180033110
0x1800330db  mov     rbx, rax
0x1800330de  jmp     short loc_180033070
0x1800330e0  mov     rbx, rax
0x1800330e3  cmp     rbx, [r15+18h]
0x1800330e7  jz      loc_18003317A
0x1800330ed  lea     r15, [rbx+28h]
0x1800330f1  mov     rcx, rsi
0x1800330f4  mov     rax, [rsi]
0x1800330f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330fc  cmp     word ptr [rsi+8], 0
0x180033101  jnz     short loc_180033130
0x180033103  xor     esi, esi
0x180033105  mov     rcx, qword ptr [rbp+40h+var_C0]
0x180033109  call    ?_Rethrow_if_exception@promise_type@?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAAXXZ; std::experimental::generator<std::basic_string_view<ushort>,std::allocator<char>>::promise_type::_Rethrow_if_exception(void)
0x18003310e  jmp     short loc_180033130
0x180033110  mov     rbx, rax
0x180033113  mov     rax, [rax+8]
0x180033117  cmp     byte ptr [rax+19h], 0
0x18003311b  jz      short loc_1800330D5
0x18003311d  jmp     short loc_1800330DB
0x18003311f  lea     rcx, [rsi-20h]
0x180033123  call    ?_Rethrow_if_exception@promise_type@?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAAXXZ; std::experimental::generator<std::basic_string_view<ushort>,std::allocator<char>>::promise_type::_Rethrow_if_exception(void)
0x180033128  xor     esi, esi
0x18003312a  nop     word ptr [rax+rax+00h]
0x180033130  test    rsi, rsi
0x180033133  jnz     loc_180033052
0x180033139  mov     rax, [rsp+140h+var_108]
0x18003313e  test    rax, rax
0x180033141  jz      short loc_180033155
0x180033143  or      qword ptr [rax+8], 1
0x180033148  mov     rcx, [rsp+140h+var_108]
0x18003314d  mov     rax, [rax]
0x180033150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033155  cmp     [r15+18h], rbx
0x180033159  jz      short loc_180033196
0x18003315b  xor     sil, sil
0x18003315e  mov     [rbp+40h+var_80], sil
0x180033162  cmp     [rbx+38h], sil
0x180033166  jz      short loc_18003319D
0x180033168  lea     rdx, [rbx+28h]
0x18003316c  lea     rcx, [rbp+40h+var_90]
0x180033170  call    ??0?$shared_ptr@VPendingOperation@InstanceManager@GraphRecentItemsManager@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GraphRecentItemsManager::InstanceManager::PendingOperation>::shared_ptr<GraphRecentItemsManager::InstanceManager::PendingOperation>(std::shared_ptr<GraphRecentItemsManager::InstanceManager::PendingOperation> const &)
0x180033175  mov     sil, 1
0x180033178  jmp     short loc_180033199
0x18003317a  mov     rax, [rsp+140h+var_108]
0x18003317f  test    rax, rax
0x180033182  jz      short loc_180033196
0x180033184  or      qword ptr [rax+8], 1
0x180033189  mov     rcx, [rsp+140h+var_108]
0x18003318e  mov     rax, [rax]
0x180033191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033196  xor     sil, sil
0x180033199  mov     [rbp+40h+var_80], sil
0x18003319d  test    sil, sil
0x1800331a0  jz      loc_180033326
0x1800331a6  lea     rcx, [rbp+40h+var_90]
0x1800331aa  call    ??_G?$shared_ptr@VKnownFolderCacheItem@kfapi@@@std@@QEAAPEAXI@Z; std::shared_ptr<kfapi::KnownFolderCacheItem>::`scalar deleting destructor'(uint)
0x1800331af  test    sil, sil
0x1800331b2  jz      loc_180033326
0x1800331b8  mov     rcx, [rsp+140h+pv]; pv
0x1800331bd  test    rcx, rcx
0x1800331c0  jz      short loc_1800331CF
0x1800331c2  call    cs:__imp_CoTaskMemFree
0x1800331c9  nop     dword ptr [rax+rax+00h]
0x1800331ce  nop
0x1800331cf  mov     rcx, [rsp+140h+var_110]; pv
0x1800331d4  test    rcx, rcx
0x1800331d7  jnz     loc_180033477
0x1800331dd  test    rdi, rdi
0x1800331e0  jz      short loc_1800331F1
0x1800331e2  mov     rax, [rdi]
0x1800331e5  mov     rcx, rdi
0x1800331e8  mov     rax, [rax+10h]
0x1800331ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331f1  mov     r13d, [rsp+140h+var_100]
0x1800331f6  mov     r15, [rbp+40h+var_98]
0x1800331fa  inc     r13d
0x1800331fd  mov     [rsp+140h+var_100], r13d
0x180033202  cmp     r13d, [rsp+140h+var_D8]
0x180033207  jnb     loc_1800334BC
0x18003320d  xor     ebx, ebx
0x18003320f  mov     [rsp+140h+var_F0], rbx
0x180033214  mov     edx, r13d
0x180033217  lea     rcx, [rbp+40h+var_B0]
0x18003321b  call    ??A?$unique_any_array_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAAEAU_GUID@@_K@Z; wil::unique_any_array_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::operator[](unsigned __int64)
0x180033220  mov     r12, rax
0x180033223  mov     [rsp+140h+var_D0], rax
0x180033228  lea     r8, [rsp+140h+var_F0]
0x18003322d  mov     rdx, rax
0x180033230  mov     rcx, r15
0x180033233  call    ?GetFolderDefinition@CKFFacade@kfapi@@QEAAJAEBU_GUID@@PEAPEAV?$CTRefObj@VCKnownFolderDefinition@kfapi@@VCTRefBase_NoModuleLifetimePolicy@@@@@Z; kfapi::CKFFacade::GetFolderDefinition(_GUID const &,CTRefObj<kfapi::CKnownFolderDefinition,CTRefBase_NoModuleLifetimePolicy> * *)
0x180033238  mov     rdi, [rsp+140h+var_F0]
0x18003323d  test    eax, eax
0x18003323f  jns     loc_180033488
0x180033245  mov     [rsp+140h+var_110], rbx
0x18003324a  lea     rcx, [rsp+140h+var_110]
0x18003324f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180033254  mov     r9, rax; ppszPath
0x180033257  xor     r8d, r8d; hToken
0x18003325a  mov     edx, 4000h; dwFlags
0x18003325f  mov     rcx, r12; rfid
0x180033262  call    SHGetKnownFolderPath
0x180033267  test    eax, eax
0x180033269  js      loc_180033450
0x18003326f  mov     [rsp+140h+pv], 0
0x180033278  lea     rcx, [rsp+140h+pv]
0x18003327d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180033282  mov     rsi, rax
0x180033285  mov     qword ptr [rsp+140h+length], 0
0x18003328e  mov     r8, [rsp+140h+var_110]
0x180033293  lea     rdx, aS_10; "\\%s"
0x18003329a  lea     rcx, [rsp+140h+length]
0x18003329f  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x1800332a4  mov     ebx, eax
0x1800332a6  test    eax, eax
0x1800332a8  js      loc_1800337F7
0x1800332ae  mov     rcx, qword ptr [rsp+140h+length]
0x1800332b3  mov     [rsi], rcx
0x1800332b6  lea     r13, [r15+20h]
0x1800332ba  mov     [rbp+40h+var_A0], r13
0x1800332be  mov     rcx, [rsp+140h+pv]
0x1800332c3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800332ca  nop     word ptr [rax+rax+00h]
0x1800332d0  inc     rax
0x1800332d3  cmp     word ptr [rcx+rax*2], 0
0x1800332d8  jnz     short loc_1800332D0
0x1800332da  mov     r15, r13
0x1800332dd  mov     rbx, [r13+18h]
0x1800332e1  mov     [rbp+40h+var_70], rcx
0x1800332e5  mov     [rbp+40h+var_68], rax
0x1800332e9  lea     rdx, [rbp+40h+var_70]
0x1800332ed  lea     rcx, [rsp+140h+var_108]
0x1800332f2  call    ??$split_string@GP6A?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@Z@@YA?AU?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@P6A?AV32@0@Z_N@Z; split_string<ushort,std::basic_string_view<ushort> (*)(std::basic_string_view<ushort>)>(std::basic_string_view<ushort>,std::basic_string_view<ushort> (*)(std::basic_string_view<ushort>),bool)
0x1800332f7  nop
0x1800332f8  mov     rax, [rsp+140h+var_108]
0x1800332fd  test    rax, rax
0x180033300  jz      loc_180033128
0x180033306  mov     rcx, rax
0x180033309  mov     rax, [rax]
0x18003330c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033311  mov     rsi, [rsp+140h+var_108]
0x180033316  cmp     word ptr [rsi+8], 0
0x18003331b  jnz     loc_180033130
0x180033321  jmp     loc_18003311F
0x180033326  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003332d  mov     ecx, 18h; unsigned __int64
0x180033332  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033337  mov     rsi, rax
0x18003333a  mov     qword ptr [rbp+40h+var_C0], rax
0x18003333e  test    rax, rax
0x180033341  jz      loc_18003387B
0x180033347  mov     rax, [rsp+140h+var_D0]
0x18003334c  movups  xmm0, xmmword ptr [rax]
0x18003334f  mov     rcx, [rsp+140h+var_110]
0x180033354  mov     [rsi], rcx
0x180033357  mov     [rsp+140h+var_110], 0
0x180033360  movups  xmmword ptr [rsi+8], xmm0
0x180033364  mov     ecx, 18h; unsigned __int64
0x180033369  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003336e  mov     rbx, rax
0x180033371  test    rax, rax
0x180033374  jz      loc_1800334B5
0x18003337a  mov     dword ptr [rax+8], 1
0x180033381  mov     dword ptr [rax+0Ch], 1
0x180033388  lea     rax, ??_7?$_Ref_count@VKnownFolderCacheItem@kfapi@@@std@@6B@; const std::_Ref_count<kfapi::KnownFolderCacheItem>::`vftable'
0x18003338f  mov     [rbx], rax
0x180033392  mov     [rbx+10h], rsi
0x180033396  mov     [rbp+40h+var_58], rsi
0x18003339a  mov     [rbp+40h+var_50], rbx
0x18003339e  test    rsi, rsi
0x1800333a1  jz      loc_1800334CA
0x1800333a7  lea     rax, [rsp+140h+length]
0x1800333ac  mov     [rsp+140h+var_D0], rax
0x1800333b1  xorps   xmm0, xmm0
0x1800333b4  movdqu  xmmword ptr [rsp+140h+length], xmm0
0x1800333ba  test    rbx, rbx
0x1800333bd  jz      short loc_1800333C3
0x1800333bf  lock inc dword ptr [rbx+8]
0x1800333c3  mov     qword ptr [rsp+140h+length], rsi
0x1800333c8  mov     qword ptr [rsp+140h+length+8], rbx
0x1800333cd  mov     rcx, [rsp+140h+pv]; this
0x1800333d2  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800333d9  nop     dword ptr [rax+00000000h]
0x1800333e0  inc     rdx; winrt::impl *
0x1800333e3  cmp     word ptr [rcx+rdx*2], 0
0x1800333e8  jnz     short loc_1800333E0
0x1800333ea  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEBGI@Z; winrt::impl::create_hstring_on_heap(ushort const *,uint)
0x1800333ef  mov     qword ptr [rbp+40h+var_C0], rax
0x1800333f3  mov     rcx, rax; this
0x1800333f6  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x1800333fb  mov     [rsp+140h+var_D0], rax
0x180033400  lea     r8, [rsp+140h+length]
0x180033405  mov     rdx, rax
0x180033408  mov     rcx, [rbp+40h+var_A0]
0x18003340c  call    ?Insert@?$NamespaceMap@V?$shared_ptr@VKnownFolderCacheItem@kfapi@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@QEAAXPEAUHSTRING__@@V?$shared_ptr@VKnownFolderCacheItem@kfapi@@@std@@@Z; WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<kfapi::KnownFolderCacheItem>,nt_path_segment_tokenizer<ushort>>::Insert(HSTRING__ *,std::shared_ptr<kfapi::KnownFolderCacheItem>)
0x180033411  nop
0x180033412  lea     rcx, [rsp+140h+var_D0]
0x180033417  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003341c  nop
0x18003341d  lea     rcx, [rbp+40h+var_C0]
0x180033421  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180033426  nop
0x180033427  test    rbx, rbx
0x18003342a  jz      short loc_180033435
0x18003342c  mov     rcx, rbx; this
0x18003342f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180033434  nop
0x180033435  mov     rcx, [rsp+140h+pv]; pv
0x18003343a  test    rcx, rcx
0x18003343d  jz      short loc_18003344B
0x18003343f  call    cs:__imp_CoTaskMemFree
0x180033446  nop     dword ptr [rax+rax+00h]
0x18003344b  mov     r13d, [rsp+140h+var_100]
0x180033450  mov     rcx, [rsp+140h+var_110]; pv
0x180033455  test    rcx, rcx
0x180033458  jnz     short loc_1800334A7
0x18003345a  test    rdi, rdi
0x18003345d  jz      loc_1800331F6
0x180033463  mov     rax, [rdi]
  ... truncated ...
```
