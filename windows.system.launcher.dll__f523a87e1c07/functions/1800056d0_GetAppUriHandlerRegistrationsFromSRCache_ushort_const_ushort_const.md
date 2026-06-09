# GetAppUriHandlerRegistrationsFromSRCache(ushort const *,ushort const *)

- ea: `0x1800056d0`
- end: `0x180005e39`
- name: `?GetAppUriHandlerRegistrationsFromSRCache@@YA?AV?$vector@USRCacheAppUriHandlerRegistration@@V?$allocator@USRCacheAppUriHandlerRegistration@@@std@@@std@@PEBG0@Z`
- size: `1897`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c520`

## callees

- `0x180004714`
- `0x1800047dc`
- `0x1800049e8`
- `0x180004bdc`
- `0x180004d34`
- `0x180004ed0`
- `0x1800056d0`
- `0x180005e40`
- `0x180009a7c`
- `0x18000b0fc`
- `0x18000b1fc`
- `0x18000b284`
- `0x18000f194`
- `0x180010c04`
- `0x180034540`
- `0x180040358`
- `0x180065294`
- `0x180071c08`
- `0x180075ebc`
- `0x180078874`
- `0x1800d0c58`
- `0x1800d63c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000590c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000590c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000572a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000572a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000574e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180005e00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000574e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180005e00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005dcc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005dea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005dcc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180005dea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005a66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d58`

## string_xrefs

- `0x180005ae0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DynamicAppUriHandler.hpp`
- `0x1800057f6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppUriHandler.hpp`
- `0x180005786`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x1800057ba`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18000581a`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x18000587c`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180005b07`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180005b2a`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180005bf8`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180005e27`: `onecoreuap\shell\windows.system.launcher\lib\appurivalidationhelpers.cpp`
- `0x180005762`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall GetAppUriHandlerRegistrationsFromSRCache(
        _QWORD *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  int v10; // ebx
  int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  unsigned __int64 v14; // rdx
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rax
  const WCHAR *v17; // r8
  int v18; // ebx
  int v19; // ebx
  int v20; // eax
  int v21; // eax
  int v22; // edi
  int v23; // eax
  int v24; // edi
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  int v27; // eax
  __int64 v28; // rdx
  int v29; // ebx
  int v30; // ebx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  char *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v38; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v40; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v41; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+70h] [rbp-90h] BYREF
  int v44; // [rsp+80h] [rbp-80h]
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  int v46; // [rsp+90h] [rbp-70h]
  __int64 v47; // [rsp+98h] [rbp-68h]
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  int v50; // [rsp+B0h] [rbp-50h]
  __int64 v51; // [rsp+B8h] [rbp-48h]
  __int128 v52; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v53; // [rsp+D0h] [rbp-30h]
  __int64 v54; // [rsp+E0h] [rbp-20h]
  __int128 v55; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v56; // [rsp+100h] [rbp+0h]
  __int128 v57; // [rsp+108h] [rbp+8h]
  __int64 v58; // [rsp+118h] [rbp+18h]
  __int64 v59; // [rsp+120h] [rbp+20h]
  __int64 v60; // [rsp+128h] [rbp+28h]
  __int128 v61; // [rsp+130h] [rbp+30h]
  int v62; // [rsp+140h] [rbp+40h]
  __int64 v63; // [rsp+148h] [rbp+48h]
  __int64 v64; // [rsp+150h] [rbp+50h]
  LPCWCH lpString1[2]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v66; // [rsp+170h] [rbp+70h]
  __int128 v67; // [rsp+180h] [rbp+80h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]
  char v69; // [rsp+1E8h] [rbp+E8h] BYREF

  v37 = 0;
  v42 = (unsigned __int64)&v37;
  LOBYTE(v43) = 1;
  v6 = SRCacheManager_Open(0, (char *)&v42 + 8);
  if ( (_BYTE)v43 )
  {
    v7 = *(_QWORD *)v42;
    *(_QWORD *)v42 = *((_QWORD *)&v42 + 1);
    if ( v7 )
      SRCacheManager_Close(v7);
  }
  if ( v6 >= 0 )
    v6 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v6,
      (int)bIgnoreCase);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28B,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v6,
      (int)bIgnoreCase);
  v48 = 0;
  v8 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
         (struct StateRepository::Cache::Manager_NoThrow *)&v37,
         0,
         &v48);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28E,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v8,
      (int)bIgnoreCase);
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v9 = StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Open(
         (StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow *)&v49,
         (struct StateRepository::Cache::Manager_NoThrow *)&v37);
  v10 = v9;
  if ( v9 >= 0 )
    v10 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-AppUriHandler.hpp",
      (const char *)(unsigned int)v9,
      (int)bIgnoreCase);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x292,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v10,
      (int)bIgnoreCase);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>(a1);
  v11 = 1;
  v69 = 0;
  *(_OWORD *)lpString1 = 0;
  v66 = 0;
  v67 = 0;
  v13 = StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Get(&v49, v12, lpString1, &v69);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x298,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v13,
      (int)bIgnoreCase);
  while ( v69 )
  {
    v15 = lpString1[1];
    if ( lpString1[1] && *lpString1[1] && a2 && *a2 )
    {
      if ( *lpString1[1] != 42 )
      {
        v17 = a2;
        goto LABEL_31;
      }
      v15 = lpString1[1] + 1;
      v14 = -1;
      do
        ++v14;
      while ( v15[v14] );
      v16 = -1;
      do
        ++v16;
      while ( a2[v16] );
      if ( v14 <= v16 )
      {
        v17 = &a2[v16 - v14];
LABEL_31:
        if ( CompareStringOrdinal(v15, -1, v17, -1, 1) == 2
          && StateRepository::Cache::Entity::AppUriHandler_NoThrow::IsPathMatch(
               (StateRepository::Cache::Entity::AppUriHandler_NoThrow *)lpString1,
               a3) )
        {
          v55 = 0;
          v56 = 0;
          v57 = 0;
          v58 = 0;
          v59 = 0;
          v60 = 0;
          v61 = 0;
          v62 = 0;
          v63 = 0;
          v64 = 0;
          if ( GetAppUriHandlerPackage(
                 (struct StateRepository::Cache::Manager_NoThrow *)&v37,
                 v48,
                 (struct StateRepository::Cache::Entity::AppUriHandler_NoThrow *)lpString1,
                 (struct StateRepository::Cache::Entity::Package_NoThrow *)&v55) )
          {
            v42 = 0;
            v43 = 0;
            v44 = 0;
            wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &pv,
              lpString1[1]);
            v18 = v11 | 2;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v42,
              &pv);
            if ( pv )
              CoTaskMemFree(pv);
            if ( (_QWORD)v66 )
            {
              wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v40,
                v66);
              v18 |= 8u;
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                (char *)&v42 + 8,
                &v40);
              if ( v40 )
                CoTaskMemFree(v40);
            }
            wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v41,
              v67);
            v19 = v18 | 0x20;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v43,
              &v41);
            if ( v41 )
              CoTaskMemFree(v41);
            wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v38,
              *((_QWORD *)&v55 + 1));
            v11 = v19 | 0x80;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              (char *)&v43 + 8,
              &v38);
            if ( v38 )
              CoTaskMemFree(v38);
            v44 = HIDWORD(v57);
            std::vector<SRCacheAppUriHandlerRegistration>::emplace_back<SRCacheAppUriHandlerRegistration>(
              a1,
              (__int64)&v42);
            SRCacheAppUriHandlerRegistration::~SRCacheAppUriHandlerRegistration((SRCacheAppUriHandlerRegistration *)&v42);
          }
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v55);
        }
      }
    }
    ++v50;
    v20 = StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Get(&v49, v14, lpString1, &v69);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2AB,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v20,
        (int)bIgnoreCase);
  }
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v21 = StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow *)&v45,
          (struct StateRepository::Cache::Manager_NoThrow *)&v37);
  v22 = v21;
  if ( v21 >= 0 )
    v22 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
      (const char *)(unsigned int)v21,
      (int)bIgnoreCase);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B0,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v22,
      (int)bIgnoreCase);
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v69 = 0;
  if ( v45 )
  {
    v38 = 0;
    v23 = StateRepository::Cache::Context_NoThrow::EnumerateData(
            (StateRepository::Cache::Context_NoThrow *)&v45,
            v46,
            (__int64 *)&v38);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DD,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
        (const char *)(unsigned int)v23,
        (int)bIgnoreCase);
      v25 = (unsigned int)v24;
      v26 = 501;
LABEL_56:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DynamicAppUriHandler.hpp",
        (const char *)v25,
        (int)bIgnoreCase);
      goto LABEL_61;
    }
    if ( v38 )
    {
      bIgnoreCase = &v69;
      v27 = StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::Get(v47, v38, 0, &v52);
      v24 = v27;
      if ( v27 < 0 )
      {
        v25 = (unsigned int)v27;
        v26 = 506;
        goto LABEL_56;
      }
    }
  }
  v24 = 0;
LABEL_61:
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B4,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
      (const char *)(unsigned int)v24,
      (int)bIgnoreCase);
  while ( v69 )
  {
    if ( StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::IsMatch(
           (StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)&v52,
           a2,
           a3) )
    {
      v55 = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      if ( GetDynamicAppUriHandlerPackage(
             (struct StateRepository::Cache::Manager_NoThrow *)&v37,
             v48,
             (struct StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)&v52,
             (struct StateRepository::Cache::Entity::Package_NoThrow *)&v55) )
      {
        v42 = 0;
        v43 = 0;
        v44 = 0;
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v38,
          v53);
        v29 = v11 | 0x200;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v42,
          &v38);
        if ( v38 )
          CoTaskMemFree(v38);
        if ( *((_QWORD *)&v53 + 1) )
        {
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v41,
            *((_QWORD *)&v53 + 1));
          v29 |= 0x800u;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            (char *)&v42 + 8,
            &v41);
          if ( v41 )
            CoTaskMemFree(v41);
        }
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v40,
          v54);
        v30 = v29 | 0x2000;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v43,
          &v40);
        if ( v40 )
          CoTaskMemFree(v40);
        wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          *((_QWORD *)&v55 + 1));
        v11 = v30 | 0x8000;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          (char *)&v43 + 8,
          &pv);
        if ( pv )
          CoTaskMemFree(pv);
        v44 = HIDWORD(v57);
        std::vector<SRCacheAppUriHandlerRegistration>::emplace_back<SRCacheAppUriHandlerRegistration>(a1, (__int64)&v42);
        SRCacheAppUriHandlerRegistration::~SRCacheAppUriHandlerRegistration((SRCacheAppUriHandlerRegistration *)&v42);
      }
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v55);
    }
    ++v46;
    v31 = StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Get(&v45, v28, &v52, &v69);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2C7,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\appurivalidationhelpers.cpp",
        (const char *)(unsigned int)v31,
        (int)bIgnoreCase);
  }
  StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow::~DynamicAppUriHandler_NoThrow((StateRepository::Cache::Entity::DynamicAppUriHandler_NoThrow *)&v52);
  v32 = v45;
  v45 = 0;
  if ( v32 )
    SRCacheContext_Close(v32);
  StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow((StateRepository::Cache::Entity::AppUriHandler_NoThrow *)lpString1);
  v33 = v49;
  v49 = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  v34 = v37;
  v37 = 0;
  if ( v34 )
    SRCacheManager_Close(v34);
  return a1;
}

```

## disassembly

```asm
0x1800056d0  mov     [rsp-8+arg_8], rbx
0x1800056d5  mov     [rsp-8+arg_0], rcx
0x1800056da  push    rbp
0x1800056db  push    rsi
0x1800056dc  push    rdi
0x1800056dd  push    r12
0x1800056df  push    r13
0x1800056e1  push    r14
0x1800056e3  push    r15
0x1800056e5  lea     rbp, [rsp-90h]
0x1800056ed  sub     rsp, 190h
0x1800056f4  mov     r15, r8
0x1800056f7  mov     rsi, rdx
0x1800056fa  mov     r14, rcx
0x1800056fd  xor     r12d, r12d
0x180005700  mov     [rsp+1C0h+var_190], r12d
0x180005705  mov     [rsp+1C0h+var_188], r12
0x18000570a  lea     rax, [rsp+1C0h+var_188]
0x18000570f  mov     qword ptr [rsp+1C0h+var_160], rax
0x180005714  mov     qword ptr [rsp+1C0h+var_160+8], r12
0x180005719  lea     r13d, [r12+1]
0x18000571e  mov     byte ptr [rsp+1C0h+var_150], r13b
0x180005723  lea     rdx, [rsp+1C0h+var_160+8]
0x180005728  xor     ecx, ecx
0x18000572a  call    cs:__imp_SRCacheManager_Open
0x180005730  mov     ebx, eax
0x180005732  cmp     byte ptr [rsp+1C0h+var_150], r12b
0x180005737  jz      short loc_180005754
0x180005739  mov     rdx, qword ptr [rsp+1C0h+var_160]
0x18000573e  mov     rcx, [rdx]
0x180005741  mov     rax, qword ptr [rsp+1C0h+var_160+8]
0x180005746  mov     [rdx], rax
0x180005749  test    rcx, rcx
0x18000574c  jz      short loc_180005754
0x18000574e  call    cs:__imp_SRCacheManager_Close
0x180005754  test    ebx, ebx
0x180005756  jns     short loc_180005775
0x180005758  mov     rcx, [rbp+0C8h]; this
0x18000575f  mov     r9d, ebx; char *
0x180005762  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005769  mov     edx, 0A5h; void *
0x18000576e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005773  jmp     short loc_180005778
0x180005775  mov     ebx, r12d
0x180005778  mov     rcx, [rbp+0C8h]; this
0x18000577f  test    ebx, ebx
0x180005781  jns     short loc_180005798
0x180005783  mov     r9d, ebx; char *
0x180005786  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x18000578d  mov     edx, 28Bh; void *
0x180005792  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005798  mov     [rbp+0C0h+var_120], r12
0x18000579c  lea     r8, [rbp+0C0h+var_120]; __int64 *
0x1800057a0  xor     edx, edx; void *
0x1800057a2  lea     rcx, [rsp+1C0h+var_188]; struct StateRepository::Cache::Manager_NoThrow *
0x1800057a7  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x1800057ac  mov     rcx, [rbp+0C8h]; this
0x1800057b3  test    eax, eax
0x1800057b5  jns     short loc_1800057CC
0x1800057b7  mov     r9d, eax; char *
0x1800057ba  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x1800057c1  mov     edx, 28Eh; void *
0x1800057c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800057cc  mov     [rbp+0C0h+var_118], r12
0x1800057d0  mov     [rbp+0C0h+var_110], r12d
0x1800057d4  mov     [rbp+0C0h+var_108], r12
0x1800057d8  lea     rdx, [rsp+1C0h+var_188]; struct StateRepository::Cache::Manager_NoThrow *
0x1800057dd  lea     rcx, [rbp+0C0h+var_118]; this
0x1800057e1  call    ?Open@AppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x1800057e6  mov     ebx, eax
0x1800057e8  test    eax, eax
0x1800057ea  jns     short loc_180005809
0x1800057ec  mov     rcx, [rbp+0C8h]; this
0x1800057f3  mov     r9d, eax; char *
0x1800057f6  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800057fd  mov     edx, 3BDh; void *
0x180005802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005807  jmp     short loc_18000580C
0x180005809  mov     ebx, r12d
0x18000580c  mov     rcx, [rbp+0C8h]; this
0x180005813  test    ebx, ebx
0x180005815  jns     short loc_18000582C
0x180005817  mov     r9d, ebx; char *
0x18000581a  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180005821  mov     edx, 292h; void *
0x180005826  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000582c  mov     rcx, r14
0x18000582f  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$pair@$$CBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@$$CBV12@@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>>>>>>(std::allocator<std::pair<std::wstring const,std::pair<std::vector<std::wstring> const,std::vector<std::wstring> const>>> const &)
0x180005834  mov     ebx, r13d
0x180005837  mov     [rsp+1C0h+var_190], ebx
0x18000583b  mov     [rbp+0C0h+arg_18], r12b
0x180005842  xorps   xmm0, xmm0
0x180005845  movdqu  xmmword ptr [rbp+0C0h+lpString1], xmm0
0x18000584a  xorps   xmm1, xmm1
0x18000584d  movdqu  [rbp+0C0h+var_50], xmm1
0x180005852  movdqu  [rbp+0C0h+var_40], xmm0
0x18000585a  lea     r9, [rbp+0C0h+arg_18]
0x180005861  lea     r8, [rbp+0C0h+lpString1]
0x180005865  lea     rcx, [rbp+0C0h+var_118]
0x180005869  call    ?Get@AppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Get(StateRepository::Cache::Entity::AppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppUriHandler_NoThrow &,bool &)
0x18000586e  mov     rcx, [rbp+0C8h]; this
0x180005875  test    eax, eax
0x180005877  jns     short loc_18000588E
0x180005879  mov     r9d, eax; char *
0x18000587c  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180005883  mov     edx, 298h; void *
0x180005888  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000588e  cmp     [rbp+0C0h+arg_18], r12b
0x180005895  jz      loc_180005AC4
0x18000589b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000589f  mov     rcx, [rbp+0C0h+lpString1+8]; lpString1
0x1800058a3  test    rcx, rcx
0x1800058a6  jz      loc_180005A94
0x1800058ac  cmp     [rcx], r12w
0x1800058b0  jz      loc_180005A94
0x1800058b6  test    rsi, rsi
0x1800058b9  jz      loc_180005A94
0x1800058bf  cmp     [rsi], r12w
0x1800058c3  jz      loc_180005A94
0x1800058c9  cmp     word ptr [rcx], 2Ah ; '*'
0x1800058cd  jnz     short loc_1800058FF
0x1800058cf  add     rcx, 2
0x1800058d3  mov     rdx, rdi
0x1800058d6  inc     rdx
0x1800058d9  cmp     [rcx+rdx*2], r12w
0x1800058de  jnz     short loc_1800058D6
0x1800058e0  mov     rax, rdi
0x1800058e3  inc     rax
0x1800058e6  cmp     [rsi+rax*2], r12w
0x1800058eb  jnz     short loc_1800058E3
0x1800058ed  cmp     rdx, rax
0x1800058f0  ja      loc_180005A94
0x1800058f6  sub     rax, rdx
0x1800058f9  lea     r8, [rsi+rax*2]
0x1800058fd  jmp     short loc_180005902
0x1800058ff  mov     r8, rsi; lpString2
0x180005902  mov     [rsp+1C0h+bIgnoreCase], r13d; int
0x180005907  mov     r9d, edi; cchCount2
0x18000590a  mov     edx, edi; cchCount1
0x18000590c  call    cs:__imp_CompareStringOrdinal
0x180005912  cmp     eax, 2
0x180005915  jnz     loc_180005A94
0x18000591b  mov     rdx, r15; unsigned __int16 *
0x18000591e  lea     rcx, [rbp+0C0h+lpString1]; this
0x180005922  call    ?IsPathMatch@AppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEBA_NPEBG@Z; StateRepository::Cache::Entity::AppUriHandler_NoThrow::IsPathMatch(ushort const *)
0x180005927  test    al, al
0x180005929  jz      loc_180005A94
0x18000592f  xorps   xmm0, xmm0
0x180005932  movdqa  [rbp+0C0h+var_D0], xmm0
0x180005937  mov     [rbp+0C0h+var_C0], r12
0x18000593b  xorps   xmm1, xmm1
0x18000593e  movups  [rbp+0C0h+var_B8], xmm1
0x180005942  mov     [rbp+0C0h+var_A8], r12
0x180005946  mov     [rbp+0C0h+var_A0], r12
0x18000594a  mov     [rbp+0C0h+var_98], r12
0x18000594e  movdqa  [rbp+0C0h+var_90], xmm0
0x180005953  mov     [rbp+0C0h+var_80], r12d
0x180005957  mov     [rbp+0C0h+var_78], r12
0x18000595b  mov     [rbp+0C0h+var_70], r12
0x18000595f  lea     r9, [rbp+0C0h+var_D0]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x180005963  lea     r8, [rbp+0C0h+lpString1]; struct StateRepository::Cache::Entity::AppUriHandler_NoThrow *
0x180005967  mov     rdx, [rbp+0C0h+var_120]; __int64
0x18000596b  lea     rcx, [rsp+1C0h+var_188]; struct StateRepository::Cache::Manager_NoThrow *
0x180005970  call    ?GetAppUriHandlerPackage@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JAEAVAppUriHandler_NoThrow@Entity@23@AEAVPackage_NoThrow@523@@Z; GetAppUriHandlerPackage(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::AppUriHandler_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &)
0x180005975  test    al, al
0x180005977  jz      loc_180005A8B
0x18000597d  xorps   xmm0, xmm0
0x180005980  movdqu  [rsp+1C0h+var_160], xmm0
0x180005986  xorps   xmm1, xmm1
0x180005989  movdqu  [rsp+1C0h+var_150], xmm1
0x18000598f  mov     [rbp+0C0h+var_140], r12d
0x180005993  mov     rdx, [rbp+0C0h+lpString1+8]
0x180005997  lea     rcx, [rsp+1C0h+pv]
0x18000599c  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800059a1  or      ebx, 2
0x1800059a4  mov     [rsp+1C0h+var_190], ebx
0x1800059a8  lea     rdx, [rsp+1C0h+pv]
0x1800059ad  lea     rcx, [rsp+1C0h+var_160]
0x1800059b2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800059b7  mov     rcx, [rsp+1C0h+pv]; pv
0x1800059bc  test    rcx, rcx
0x1800059bf  jz      short loc_1800059C7
0x1800059c1  call    cs:__imp_CoTaskMemFree
0x1800059c7  mov     rdx, qword ptr [rbp+0C0h+var_50]
0x1800059cb  test    rdx, rdx
0x1800059ce  jz      short loc_180005A00
0x1800059d0  lea     rcx, [rsp+1C0h+var_170]
0x1800059d5  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800059da  or      ebx, 8
0x1800059dd  mov     [rsp+1C0h+var_190], ebx
0x1800059e1  lea     rdx, [rsp+1C0h+var_170]
0x1800059e6  lea     rcx, [rsp+1C0h+var_160+8]
0x1800059eb  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800059f0  mov     rcx, [rsp+1C0h+var_170]; pv
0x1800059f5  test    rcx, rcx
0x1800059f8  jz      short loc_180005A00
0x1800059fa  call    cs:__imp_CoTaskMemFree
0x180005a00  mov     rdx, qword ptr [rbp+0C0h+var_40]
0x180005a07  lea     rcx, [rsp+1C0h+var_168]
0x180005a0c  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180005a11  or      ebx, 20h
0x180005a14  mov     [rsp+1C0h+var_190], ebx
0x180005a18  lea     rdx, [rsp+1C0h+var_168]
0x180005a1d  lea     rcx, [rsp+1C0h+var_150]
0x180005a22  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180005a27  mov     rcx, [rsp+1C0h+var_168]; pv
0x180005a2c  test    rcx, rcx
0x180005a2f  jz      short loc_180005A37
0x180005a31  call    cs:__imp_CoTaskMemFree
0x180005a37  mov     rdx, qword ptr [rbp+0C0h+var_D0+8]
0x180005a3b  lea     rcx, [rsp+1C0h+var_180]
0x180005a40  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180005a45  bts     ebx, 7
0x180005a49  mov     [rsp+1C0h+var_190], ebx
0x180005a4d  lea     rdx, [rsp+1C0h+var_180]
0x180005a52  lea     rcx, [rsp+1C0h+var_150+8]
0x180005a57  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180005a5c  mov     rcx, [rsp+1C0h+var_180]; pv
0x180005a61  test    rcx, rcx
0x180005a64  jz      short loc_180005A6C
0x180005a66  call    cs:__imp_CoTaskMemFree
0x180005a6c  mov     eax, dword ptr [rbp+0C0h+var_B8+0Ch]
0x180005a6f  mov     [rbp+0C0h+var_140], eax
0x180005a72  lea     rdx, [rsp+1C0h+var_160]
0x180005a77  mov     rcx, r14
0x180005a7a  call    ??$emplace_back@USRCacheAppUriHandlerRegistration@@@?$vector@USRCacheAppUriHandlerRegistration@@V?$allocator@USRCacheAppUriHandlerRegistration@@@std@@@std@@QEAAAEAUSRCacheAppUriHandlerRegistration@@$$QEAU2@@Z; std::vector<SRCacheAppUriHandlerRegistration>::emplace_back<SRCacheAppUriHandlerRegistration>(SRCacheAppUriHandlerRegistration &&)
0x180005a7f  nop
0x180005a80  lea     rcx, [rsp+1C0h+var_160]; this
0x180005a85  call    ??1SRCacheAppUriHandlerRegistration@@QEAA@XZ; SRCacheAppUriHandlerRegistration::~SRCacheAppUriHandlerRegistration(void)
0x180005a8a  nop
0x180005a8b  lea     rcx, [rbp+0C0h+var_D0]; this
0x180005a8f  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180005a94  add     [rbp+0C0h+var_110], r13d
0x180005a98  lea     r9, [rbp+0C0h+arg_18]
0x180005a9f  lea     r8, [rbp+0C0h+lpString1]
0x180005aa3  lea     rcx, [rbp+0C0h+var_118]
0x180005aa7  call    ?Get@AppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Get(StateRepository::Cache::Entity::AppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppUriHandler_NoThrow &,bool &)
0x180005aac  mov     rcx, [rbp+0C8h]; this
0x180005ab3  test    eax, eax
0x180005ab5  js      short loc_180005B04
0x180005ab7  cmp     [rbp+0C0h+arg_18], r12b
0x180005abe  jnz     loc_18000589F
0x180005ac4  mov     [rbp+0C0h+var_138], r12
0x180005ac8  mov     [rbp+0C0h+var_130], r12d
0x180005acc  mov     [rbp+0C0h+var_128], r12
0x180005ad0  lea     rdx, [rsp+1C0h+var_188]; struct StateRepository::Cache::Manager_NoThrow *
0x180005ad5  lea     rcx, [rbp+0C0h+var_138]; this
0x180005ad9  call    ?Open@DynamicAppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::DynamicAppUriHandlerIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180005ade  mov     edi, eax
0x180005ae0  lea     r13, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005ae7  test    eax, eax
0x180005ae9  jns     short loc_180005B19
0x180005aeb  mov     rcx, [rbp+0C8h]; this
0x180005af2  mov     r9d, eax; char *
0x180005af5  mov     r8, r13; unsigned int
0x180005af8  mov     edx, 3A3h; void *
0x180005afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b02  jmp     short loc_180005B1C
0x180005b04  mov     r9d, eax; char *
0x180005b07  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180005b0e  mov     edx, 2ABh; void *
0x180005b13  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005b19  mov     edi, r12d
0x180005b1c  mov     rcx, [rbp+0C8h]; this
0x180005b23  test    edi, edi
0x180005b25  jns     short loc_180005B3C
0x180005b27  mov     r9d, edi; char *
0x180005b2a  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\windows.system.launc"...
0x180005b31  mov     edx, 2B0h; void *
0x180005b36  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005b3c  xorps   xmm0, xmm0
0x180005b3f  movdqu  [rbp+0C0h+var_100], xmm0
0x180005b44  xorps   xmm1, xmm1
0x180005b47  movdqu  [rbp+0C0h+var_F0], xmm1
0x180005b4c  mov     [rbp+0C0h+var_E0], r12
0x180005b50  mov     [rbp+0C0h+arg_18], r12b
0x180005b57  cmp     [rbp+0C0h+var_138], r12
0x180005b5b  jz      loc_180005BE3
0x180005b61  mov     [rsp+1C0h+var_180], r12
0x180005b66  lea     r8, [rsp+1C0h+var_180]; __int64 *
0x180005b6b  mov     edx, [rbp+0C0h+var_130]; int
0x180005b6e  lea     rcx, [rbp+0C0h+var_138]; this
0x180005b72  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x180005b77  mov     edi, eax
0x180005b79  test    eax, eax
0x180005b7b  jns     short loc_180005BAD
0x180005b7d  mov     rcx, [rbp+0C8h]; this
0x180005b84  mov     r9d, eax; char *
0x180005b87  mov     r8, r13; unsigned int
0x180005b8a  mov     edx, 1DDh; void *
0x180005b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b94  mov     r9d, edi; char *
0x180005b97  mov     edx, 1F5h; void *
0x180005b9c  mov     r8, r13; unsigned int
0x180005b9f  mov     rcx, [rbp+0C8h]; this
0x180005ba6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005bab  jmp     short loc_180005BE6
0x180005bad  mov     rdx, [rsp+1C0h+var_180]
0x180005bb2  test    rdx, rdx
0x180005bb5  jz      short loc_180005BE3
  ... truncated ...
```
