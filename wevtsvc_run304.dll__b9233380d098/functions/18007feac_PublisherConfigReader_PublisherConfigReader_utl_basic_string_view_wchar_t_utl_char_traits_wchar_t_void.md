# PublisherConfigReader::PublisherConfigReader(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,void *)

- ea: `0x18007feac`
- end: `0x180080d49`
- name: `??0PublisherConfigReader@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEAX@Z`
- size: `3741`
- prototype: `__int64 __fastcall(PublisherConfigReader *this)`
- caller_count: `3`
- callee_count: `44`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034f3c`
- `0x18003a2e4`
- `0x18008e3b8`

## callees

- `0x180003de0`
- `0x180006600`
- `0x180006650`
- `0x180006770`
- `0x180008870`
- `0x1800092c4`
- `0x18001722c`
- `0x180017b60`
- `0x180017b98`
- `0x18002afa8`
- `0x18002c6f4`
- `0x18002d204`
- `0x18002d6dc`
- `0x18002d934`
- `0x18003a2c8`
- `0x18003bb7c`
- `0x18003be9c`
- `0x18003d1dc`
- `0x18003d3fc`
- `0x18003ee98`
- `0x180052af0`
- `0x180054848`
- `0x18005667c`
- `0x180056714`
- `0x18005af7c`
- `0x18006bb08`
- `0x18006e604`
- `0x18006e7c0`
- `0x1800755c4`
- `0x180075f00`
- `0x180077984`
- `0x18007feac`
- `0x180083e64`
- `0x180083f2c`
- `0x18008d8a8`
- `0x180090d74`
- `0x180092008`
- `0x180092c6c`
- `0x180092d78`
- `0x18009aee0`
- `0x18009e770`
- `0x1800c0fd4`
- `0x1800c1170`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007ff7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007ff7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800804bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800804bc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800801ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800801ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
PublisherConfigReader *__fastcall PublisherConfigReader::PublisherConfigReader(
        PublisherConfigReader *this,
        __int128 *a2)
{
  struct _GUID *v3; // r13
  char *v4; // r12
  _QWORD *v5; // rdi
  _WORD *v6; // rcx
  const wchar_t **v7; // rbx
  const char *v8; // r8
  __int64 v9; // rcx
  __int64 v10; // r8
  const char *v11; // r8
  _QWORD *RegCacheProviderNodebyGuid; // rbx
  HKEY *v13; // rax
  unsigned int v14; // ebx
  _QWORD *RegCacheLegacyProviderNode; // rbx
  __int64 v16; // r8
  __int64 v17; // rcx
  const char *v18; // r8
  const char *v19; // r8
  unsigned int i; // eax
  HKEY v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // r9
  const WCHAR *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // ebx
  __int64 CurrentPublisherKey; // rax
  __int64 v29; // r8
  const char *v30; // r8
  _QWORD *v31; // rbx
  unsigned int EventlogServiceRegPath; // ebx
  void *v33; // rbx
  HKEY *v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // ebx
  const WCHAR *v37; // rbx
  unsigned int LegacyChannelRegPath; // eax
  unsigned int v39; // ebx
  const char *v40; // r8
  void *v41; // rbx
  HKEY *v42; // rax
  __int64 v43; // rcx
  const char *v44; // r8
  const char *v45; // r8
  __int64 *v46; // rbx
  _QWORD *v47; // rbx
  _WORD *v48; // rcx
  const char *v49; // r8
  const char *v50; // r8
  __int64 v51; // rcx
  _QWORD *v52; // rbx
  __int64 v53; // rax
  const char *v54; // r8
  HKEY *v55; // rax
  unsigned int v56; // ebx
  _QWORD *v57; // rbx
  _QWORD v59[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v60; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+58h] [rbp-A8h]
  LPCWCH lpString2; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v64; // [rsp+68h] [rbp-98h]
  _WORD v65[12]; // [rsp+70h] [rbp-90h] BYREF
  HKEY v66; // [rsp+88h] [rbp-78h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+90h] [rbp-70h] BYREF
  LPCWCH v68; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-38h]
  wchar_t *v70[2]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD v71[8]; // [rsp+E0h] [rbp-20h] BYREF
  PublisherConfigReader *v72; // [rsp+F0h] [rbp-10h]
  HKEY v73[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v74[16]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v75; // [rsp+120h] [rbp+20h]
  int v76; // [rsp+130h] [rbp+30h]
  int v77; // [rsp+134h] [rbp+34h]
  _BYTE v78[16]; // [rsp+340h] [rbp+240h] BYREF
  HKEY v79; // [rsp+350h] [rbp+250h]
  __int64 v80; // [rsp+358h] [rbp+258h]
  int v81; // [rsp+360h] [rbp+260h]
  int v82; // [rsp+364h] [rbp+264h]

  v59[0] = a2;
  v72 = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = -1;
  v3 = (struct _GUID *)((char *)this + 16);
  *((GUID *)this + 1) = GUID_NULL;
  v4 = (char *)this + 32;
  *((_QWORD *)this + 4) = 0;
  v5 = (_QWORD *)((char *)this + 40);
  v6 = (_WORD *)((char *)this + 56);
  *v5 = v6;
  v5[1] = v6;
  *v6 = 0;
  v7 = (const wchar_t **)((char *)this + 72);
  *((_QWORD *)this + 9) = (char *)this + 88;
  *((_QWORD *)this + 10) = (char *)this + 88;
  *((_WORD *)this + 44) = 0;
  *((_QWORD *)this + 13) = (char *)this + 120;
  *((_QWORD *)this + 14) = (char *)this + 120;
  *((_WORD *)this + 60) = 0;
  *((_BYTE *)this + 136) = 1;
  v60 = *a2;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 72) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)&lpString2, 0xEu, v8, 211);
    throw (EvtException *)&lpString2;
  }
  hKey = (HKEY)&PublisherConfigReader::s_pubNameCachesMutex;
  AcquireSRWLockShared(&PublisherConfigReader::s_pubNameCachesMutex);
  LOBYTE(v62) = 1;
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::less<void>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::find<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
    v9,
    v73,
    (char *)this + 72);
  if ( (__int64 *)v73[0] != &PublisherConfigReader::s_pubNameNotFoundCache )
  {
    EvtException::EvtException((EvtException *)&lpString2, 2u);
    throw (EvtException *)&lpString2;
  }
  utl::shared_lock<utl::shared_mutex>::~shared_lock<utl::shared_mutex>(&hKey);
  if ( GetRegCacheProviderGuidForName(*v7, v3) )
  {
    *((_BYTE *)this + 136) = 0;
    LOBYTE(v10) = 1;
    if ( (int)tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v5, v3, v10) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&lpString2, 0xEu, v11, 232);
      throw (EvtException *)&lpString2;
    }
    RegCacheProviderNodebyGuid = (_QWORD *)GetRegCacheProviderNodebyGuid(v59, v3);
    wmi::AutoRef<PublisherMetadata>::Release(v4);
    *(_QWORD *)v4 = *RegCacheProviderNodebyGuid;
    *RegCacheProviderNodebyGuid = 0;
    wmi::AutoRef<PublisherMetadata>::Release(v59);
    if ( !*(_QWORD *)v4 )
    {
      v13 = (HKEY *)OpenPublishersKeyOrThrow(v59);
      v14 = PublisherConfigReader::LoadFromRegistryHelper(this, *v13);
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v59);
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, v14);
        }
        EvtException::EvtException((EvtException *)&lpString2, v14);
        throw (EvtException *)&lpString2;
      }
    }
    return this;
  }
  RegCacheLegacyProviderNode = (_QWORD *)GetRegCacheLegacyProviderNode(v73, *v7);
  wmi::AutoRef<PublisherMetadata>::Release(v4);
  *(_QWORD *)v4 = *RegCacheLegacyProviderNode;
  *RegCacheLegacyProviderNode = 0;
  wmi::AutoRef<PublisherMetadata>::Release(v73);
  v17 = *(_QWORD *)v4;
  if ( *(_QWORD *)v4 )
  {
    *((_BYTE *)this + 136) = *(_BYTE *)(v17 + 156) != 0;
    *v3 = *(struct _GUID *)(v17 + 136);
    LOBYTE(v16) = 1;
    if ( (int)tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v5, v3, v16) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&lpString2, 0xEu, v18, 257);
      throw (EvtException *)&lpString2;
    }
    if ( (*(_DWORD *)(*(_QWORD *)v4 + 192LL) & 0x800) != 0
      && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             (char *)this + 104,
                             *(_QWORD *)(*(_QWORD *)v4 + 88LL)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)&lpString2, 0xEu, v19, 264);
      throw (EvtException *)&lpString2;
    }
    return this;
  }
  PublisherConfigEnumerator::PublisherConfigEnumerator((PublisherConfigEnumerator *)v78, *((void **)this + 1));
  lpString2 = v65;
  v64 = v65;
  v65[0] = 0;
  v81 = v82;
  for ( i = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v78);
        ;
        i = RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v78) )
  {
    if ( i == 259 )
    {
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString2);
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v78);
      v73[0] = 0;
      v70[0] = v71;
      v70[1] = v71;
      v71[0] = 0;
      EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(0, v73, v70);
      if ( EventlogServiceRegPath )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids,
            EventlogServiceRegPath);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, EventlogServiceRegPath);
        throw (EvtException *)pExceptionObject;
      }
      v66 = 0;
      v33 = (void *)*((_QWORD *)this + 1);
      v34 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v66);
      v35 = OpenRegKey(v73[0], v70[0], 0x20019u, v34, v33);
      v36 = v35;
      if ( v35 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, v35);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, v36);
        throw (EvtException *)pExceptionObject;
      }
      RegistryKeyEnumerator::RegistryKeyEnumerator((RegistryKeyEnumerator *)v74, v66, *((void **)this + 1));
      v76 = v77;
      while ( 1 )
      {
        do
        {
          if ( RegistryKeyEnumerator::MoveNext((RegistryKeyEnumerator *)v74) == 259 )
          {
            v73[0] = (HKEY)&PublisherConfigReader::s_pubNameCachesMutex;
            AcquireSRWLockExclusive(&PublisherConfigReader::s_pubNameCachesMutex);
            utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::less<void>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::emplace<utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> &,0>(
              v43,
              &v60,
              v59[0]);
            if ( !(_QWORD)v60 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
              }
              EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v44, 459);
              throw (EvtException *)pExceptionObject;
            }
            utl::lock_guard<utl::shared_mutex>::~lock_guard<utl::shared_mutex>(v73);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF__utlwsv_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                43,
                &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids,
                v59[0]);
            }
            EvtException::EvtException((EvtException *)pExceptionObject, 2u);
            throw (EvtException *)pExceptionObject;
          }
          v37 = (const WCHAR *)v75;
          v60 = v75;
        }
        while ( (unsigned __int8)ShouldSkipLegacyChannelKey(&v60) );
        lpString2 = v65;
        v64 = v65;
        v65[0] = 0;
        v68 = v37;
        v69 = *((_QWORD *)&v75 + 1);
        LegacyChannelRegPath = RegistryPaths::GetLegacyChannelRegPath(0, &v68, v73, &lpString2);
        v39 = LegacyChannelRegPath;
        if ( LegacyChannelRegPath )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids,
              LegacyChannelRegPath);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, v39);
          throw (EvtException *)pExceptionObject;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                 &lpString2,
                                 92)
          || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&lpString2) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v40, 348);
          throw (EvtException *)pExceptionObject;
        }
        hKey = 0;
        v41 = (void *)*((_QWORD *)this + 1);
        v42 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
        if ( !OpenRegKey(v73[0], lpString2, 0x20019u, v42, v41) )
          break;
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString2);
      }
      v60 = v75;
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 104) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v45, 358);
        throw (EvtException *)pExceptionObject;
      }
      v46 = (__int64 *)((char *)this + 40);
      if ( (unsigned int)RegReadStringValueNoThrow(hKey) )
      {
        *((_BYTE *)this + 136) = 1;
        tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::operator=(
          this,
          &hKey);
        v47 = (_QWORD *)AddRegCacheLegacyProviderNode(
                          v59,
                          *((_QWORD *)this + 9),
                          *((_QWORD *)this + 13),
                          *(_QWORD *)this);
        wmi::AutoRef<PublisherMetadata>::Release(v4);
        *(_QWORD *)v4 = *v47;
        *v47 = 0;
      }
      else
      {
        if ( tlx::string_to_guid<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
               v3,
               (char *)this + 40) )
        {
          if ( *(_WORD *)(*((_QWORD *)this + 6) - 2LL) != 125
            && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                   (char *)this + 40,
                                   125) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v49, 395);
            throw (EvtException *)pExceptionObject;
          }
          if ( *(_WORD *)*v46 != 123
            && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::insert((char *)this + 40) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
            }
            EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v50, 403);
            throw (EvtException *)pExceptionObject;
          }
          v51 = -1;
          do
            ++v51;
          while ( *(_WORD *)(*((_QWORD *)this + 9) + 2 * v51) );
          *(_QWORD *)&v60 = *((_QWORD *)this + 9);
          *((_QWORD *)&v60 + 1) = v51;
          AddRegCacheProviderGuidForName(&v60, v3);
          v52 = (_QWORD *)GetRegCacheProviderNodebyGuid(v73, v3);
          wmi::AutoRef<PublisherMetadata>::Release(v4);
          *(_QWORD *)v4 = *v52;
          *v52 = 0;
          wmi::AutoRef<PublisherMetadata>::Release(v73);
          v53 = *(_QWORD *)v4;
          if ( *(_QWORD *)v4 )
          {
            *((_BYTE *)this + 136) = 0;
            v60 = *(_OWORD *)(v53 + 24);
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign((char *)this + 72) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
              }
              EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v54, 419);
              throw (EvtException *)pExceptionObject;
            }
            goto LABEL_67;
          }
          v55 = (HKEY *)OpenPublishersKeyOrThrow(v73);
          v56 = PublisherConfigReader::LoadFromRegistryHelper(this, *v55);
          tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v73);
          if ( !v56 )
          {
            *((_BYTE *)this + 136) = 0;
            v60 = *(_OWORD *)v59[0];
            AddRegCacheProviderGuidForName(&v60, v3);
LABEL_67:
            tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString2);
            tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v74);
            tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v66);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v70);
            return this;
          }
          *((_BYTE *)this + 136) = 1;
          tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::operator=(
            this,
            &hKey);
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              (unsigned int)&WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids,
              *((_QWORD *)this + 9),
              *v46);
          }
          *((_BYTE *)this + 136) = 1;
          tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::operator=(
            this,
            &hKey);
          v48 = (_WORD *)*v46;
          *((_QWORD *)this + 6) = *((_QWORD *)this + 5);
          *v48 = 0;
        }
        v57 = (_QWORD *)AddRegCacheLegacyProviderNode(
                          v59,
                          *((_QWORD *)this + 9),
                          *((_QWORD *)this + 13),
                          *(_QWORD *)this);
        wmi::AutoRef<PublisherMetadata>::Release(v4);
        *(_QWORD *)v4 = *v57;
        *v57 = 0;
      }
      wmi::AutoRef<PublisherMetadata>::Release(v59);
      goto LABEL_67;
    }
    *(_OWORD *)v73 = 0;
    v21 = v79;
    hKey = v79;
    v22 = v80;
    v62 = v80;
    if ( !v80 )
      goto LABEL_26;
    if ( tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(v73, &hKey) )
      break;
    v21 = v79;
LABEL_26:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      *(_QWORD *)&v60 = v21;
      *((_QWORD *)&v60 + 1) = v22;
      WPP_SF__utlwsv_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, &v60);
    }
LABEL_30:
    ;
  }
  if ( !(unsigned __int8)PublisherConfigEnumerator::GetCurrentPublisherName(v78, &lpString2) )
    goto LABEL_30;
  if ( lpString2 == v64 )
    goto LABEL_30;
  v23 = -1;
  do
    ++v23;
  while ( lpString2[v23] );
  v68 = lpString2;
  v69 = v23;
  AddRegCacheProviderGuidForName(&v68, v73);
  v24 = v64 - lpString2;
  v25 = (const WCHAR *)*((_QWORD *)this + 9);
  v26 = (__int64)(*((_QWORD *)this + 10) - (_QWORD)v25) >> 1;
  if ( v26 != v24 || CompareStringOrdinal(v25, v26, lpString2, v24, 1) != 2 )
    goto LABEL_30;
  v60 = *(_OWORD *)v59[0];
  v27 = ScanForInvalidChars(&v60, 15004);
  if ( v27 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, v27);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v27);
    throw (EvtException *)pExceptionObject;
  }
  *((_BYTE *)this + 136) = 0;
  CurrentPublisherKey = PublisherConfigEnumerator::GetCurrentPublisherKey(v78, v59);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::operator=(
    this,
    CurrentPublisherKey);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v59);
  *v3 = *(struct _GUID *)v73;
  LOBYTE(v29) = 1;
  if ( (int)tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)this + 40, v3, v29) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids, 14);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v30, 310);
    throw (EvtException *)pExceptionObject;
  }
  v31 = (_QWORD *)AddRegCacheProviderNode(v59, v3, *(_QWORD *)this);
  wmi::AutoRef<PublisherMetadata>::Release(v4);
  *(_QWORD *)v4 = *v31;
  *v31 = 0;
  wmi::AutoRef<PublisherMetadata>::Release(v59);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString2);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(v78);
  return this;
}

```

## disassembly

```asm
0x18007feac  mov     [rsp-8+arg_10], rbx
0x18007feb1  push    rbp
0x18007feb2  push    rsi
0x18007feb3  push    rdi
0x18007feb4  push    r12
0x18007feb6  push    r13
0x18007feb8  push    r14
0x18007feba  push    r15
0x18007febc  lea     rbp, [rsp-480h]
0x18007fec4  sub     rsp, 580h
0x18007fecb  mov     rax, cs:__security_cookie
0x18007fed2  xor     rax, rsp
0x18007fed5  mov     [rbp+4B0h+var_40], rax
0x18007fedc  mov     [rsp+5B0h+var_580], rdx
0x18007fee1  mov     r15, rcx
0x18007fee4  mov     [rbp+4B0h+var_4C0], rcx
0x18007fee8  xor     r14d, r14d
0x18007feeb  mov     [rcx], r14
0x18007feee  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x18007fef6  lea     r13, [rcx+10h]
0x18007fefa  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18007ff01  movdqu  xmmword ptr [r13+0], xmm0
0x18007ff07  lea     r12, [rcx+20h]
0x18007ff0b  mov     [r12], r14
0x18007ff0f  lea     rdi, [rcx+28h]
0x18007ff13  lea     rcx, [rdi+10h]
0x18007ff17  mov     [rdi], rcx
0x18007ff1a  mov     [rdi+8], rcx
0x18007ff1e  mov     [rcx], r14w
0x18007ff22  lea     rbx, [r15+48h]
0x18007ff26  lea     rcx, [rbx+10h]
0x18007ff2a  mov     [rbx], rcx
0x18007ff2d  mov     [rbx+8], rcx
0x18007ff31  mov     [rcx], r14w
0x18007ff35  lea     rcx, [r15+78h]
0x18007ff39  mov     [r15+68h], rcx
0x18007ff3d  mov     [r15+70h], rcx
0x18007ff41  mov     [rcx], r14w
0x18007ff45  mov     byte ptr [r15+88h], 1
0x18007ff4d  movaps  xmm0, xmmword ptr [rdx]
0x18007ff50  movdqa  [rsp+5B0h+var_570], xmm0
0x18007ff56  lea     rdx, [rsp+5B0h+var_570]
0x18007ff5b  mov     rcx, rbx
0x18007ff5e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@2@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18007ff63  test    al, al
0x18007ff65  jz      loc_1800809E0
0x18007ff6b  lea     rax, ?s_pubNameCachesMutex@PublisherConfigReader@@0Vshared_mutex@utl@@A; utl::shared_mutex PublisherConfigReader::s_pubNameCachesMutex
0x18007ff72  mov     [rsp+5B0h+hKey], rax
0x18007ff77  mov     rcx, rax; SRWLock
0x18007ff7a  call    cs:__imp_AcquireSRWLockShared
0x18007ff80  mov     byte ptr [rsp+5B0h+var_558], 1
0x18007ff85  mov     r8, rbx
0x18007ff88  lea     rdx, [rbp+4B0h+var_4B0]
0x18007ff8c  call    ??$find@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@U?$less@X@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@QEAA?AV?$_TreeConstIt@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@@Z; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::less<void>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::find<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x18007ff91  lea     rax, ?s_pubNameNotFoundCache@PublisherConfigReader@@0V?$set@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@U?$less@X@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@A; utl::set<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::less<void>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> PublisherConfigReader::s_pubNameNotFoundCache
0x18007ff98  cmp     [rbp+4B0h+var_4B0], rax
0x18007ff9c  jnz     loc_180080A41
0x18007ffa2  lea     rcx, [rsp+5B0h+hKey]
0x18007ffa7  call    ??1?$shared_lock@Vshared_mutex@utl@@@utl@@QEAA@XZ; utl::shared_lock<utl::shared_mutex>::~shared_lock<utl::shared_mutex>(void)
0x18007ffac  mov     rdx, r13; struct _GUID *
0x18007ffaf  mov     rcx, [rbx]; wchar_t *
0x18007ffb2  call    ?GetRegCacheProviderGuidForName@@YA_NPEB_WPEAU_GUID@@@Z; GetRegCacheProviderGuidForName(wchar_t const *,_GUID *)
0x18007ffb7  test    al, al
0x18007ffb9  jz      loc_180080040
0x18007ffbf  mov     [r15+88h], r14b
0x18007ffc6  mov     r8b, 1
0x18007ffc9  mov     rdx, r13
0x18007ffcc  mov     rcx, rdi
0x18007ffcf  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x18007ffd4  test    eax, eax
0x18007ffd6  js      loc_180080A62
0x18007ffdc  mov     rdx, r13
0x18007ffdf  lea     rcx, [rsp+5B0h+var_580]
0x18007ffe4  call    ?GetRegCacheProviderNodebyGuid@@YA?AV?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@PEBU_GUID@@@Z; GetRegCacheProviderNodebyGuid(_GUID const *)
0x18007ffe9  mov     rbx, rax
0x18007ffec  mov     rcx, r12
0x18007ffef  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18007fff4  mov     rcx, [rbx]
0x18007fff7  mov     [r12], rcx
0x18007fffb  mov     [rbx], r14
0x18007fffe  lea     rcx, [rsp+5B0h+var_580]
0x180080003  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x180080008  cmp     [r12], r14
0x18008000c  jnz     loc_180080774
0x180080012  lea     rcx, [rsp+5B0h+var_580]
0x180080017  call    OpenPublishersKeyOrThrow
0x18008001c  mov     rdx, [rax]; HKEY
0x18008001f  mov     rcx, r15; this
0x180080022  call    ?LoadFromRegistryHelper@PublisherConfigReader@@AEAAKPEAUHKEY__@@@Z; PublisherConfigReader::LoadFromRegistryHelper(HKEY__ *)
0x180080027  mov     ebx, eax
0x180080029  lea     rcx, [rsp+5B0h+var_580]
0x18008002e  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180080033  test    ebx, ebx
0x180080035  jnz     loc_1800807E9
0x18008003b  jmp     loc_180080774
0x180080040  mov     rdx, [rbx]
0x180080043  lea     rcx, [rbp+4B0h+var_4B0]
0x180080047  call    ?GetRegCacheLegacyProviderNode@@YA?AV?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@PEB_W@Z; GetRegCacheLegacyProviderNode(wchar_t const *)
0x18008004c  mov     rbx, rax
0x18008004f  mov     rcx, r12
0x180080052  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x180080057  mov     rcx, [rbx]
0x18008005a  mov     [r12], rcx
0x18008005e  mov     [rbx], r14
0x180080061  lea     rcx, [rbp+4B0h+var_4B0]
0x180080065  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18008006a  mov     rcx, [r12]
0x18008006e  test    rcx, rcx
0x180080071  jz      short loc_1800800D9
0x180080073  cmp     [rcx+9Ch], r14b
0x18008007a  setnz   al
0x18008007d  mov     [r15+88h], al
0x180080084  movups  xmm0, xmmword ptr [rcx+88h]
0x18008008b  movdqu  xmmword ptr [r13+0], xmm0
0x180080091  mov     r8b, 1
0x180080094  mov     rdx, r13
0x180080097  mov     rcx, rdi
0x18008009a  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x18008009f  test    eax, eax
0x1800800a1  js      loc_180080AC3
0x1800800a7  mov     rdx, [r12]
0x1800800ab  test    dword ptr [rdx+0C0h], 800h
0x1800800b5  jz      loc_180080774
0x1800800bb  mov     r8, [rdx+60h]
0x1800800bf  mov     rdx, [rdx+58h]
0x1800800c3  lea     rcx, [r15+68h]
0x1800800c7  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800800cc  test    al, al
0x1800800ce  jz      loc_180080841
0x1800800d4  jmp     loc_180080774
0x1800800d9  mov     rdx, [r15+8]; void *
0x1800800dd  lea     rcx, [rbp+4B0h+var_270]; this
0x1800800e4  call    ??0PublisherConfigEnumerator@@QEAA@PEAX@Z; PublisherConfigEnumerator::PublisherConfigEnumerator(void *)
0x1800800e9  nop
0x1800800ea  lea     rax, [rsp+5B0h+var_540]
0x1800800ef  mov     [rsp+5B0h+lpString2], rax
0x1800800f4  lea     rax, [rsp+5B0h+var_540]
0x1800800f9  mov     [rsp+5B0h+var_548], rax
0x1800800fe  mov     [rsp+5B0h+var_540], r14w
0x180080104  mov     eax, [rbp+4B0h+var_24C]
0x18008010a  mov     [rbp+4B0h+var_250], eax
0x180080110  lea     rcx, [rbp+4B0h+var_270]; this
0x180080117  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18008011c  lea     rsi, WPP_GLOBAL_Control
0x180080123  mov     dil, 4
0x180080126  lea     r14, WPP_a3d89ccdb48c31366d4d0487d7161d1c_Traceguids
0x18008012d  jmp     loc_18008030E
0x180080132  xorps   xmm0, xmm0
0x180080135  movups  xmmword ptr [rbp+4B0h+var_4B0], xmm0
0x180080139  mov     rax, [rbp+4B0h+var_260]
0x180080140  mov     [rsp+5B0h+hKey], rax
0x180080145  mov     rbx, [rbp+4B0h+var_258]
0x18008014c  mov     [rsp+5B0h+var_558], rbx
0x180080151  test    rbx, rbx
0x180080154  jz      loc_1800802CA
0x18008015a  lea     rdx, [rsp+5B0h+hKey]
0x18008015f  lea     rcx, [rbp+4B0h+var_4B0]
0x180080163  call    ??$string_to_guid@V?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@0@@Z; tlx::string_to_guid<tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>>(_GUID *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180080168  test    rax, rax
0x18008016b  jz      loc_1800802C3
0x180080171  lea     rdx, [rsp+5B0h+lpString2]
0x180080176  lea     rcx, [rbp+4B0h+var_270]
0x18008017d  call    ?GetCurrentPublisherName@PublisherConfigEnumerator@@QEAA_NAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PublisherConfigEnumerator::GetCurrentPublisherName(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180080182  xor     edx, edx
0x180080184  test    al, al
0x180080186  jz      loc_180080302
0x18008018c  mov     rcx, [rsp+5B0h+lpString2]
0x180080191  cmp     rcx, [rsp+5B0h+var_548]
0x180080196  jz      loc_180080302
0x18008019c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800801a0  inc     rax
0x1800801a3  cmp     [rcx+rax*2], dx
0x1800801a7  jnz     short loc_1800801A0
0x1800801a9  mov     [rbp+4B0h+var_4F0], rcx
0x1800801ad  mov     [rbp+4B0h+var_4E8], rax
0x1800801b1  lea     rdx, [rbp+4B0h+var_4B0]
0x1800801b5  lea     rcx, [rbp+4B0h+var_4F0]
0x1800801b9  call    ?AddRegCacheProviderGuidForName@@YAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEBU_GUID@@@Z; AddRegCacheProviderGuidForName(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,_GUID const &)
0x1800801be  mov     r9, [rsp+5B0h+var_548]
0x1800801c3  mov     r8, [rsp+5B0h+lpString2]; lpString2
0x1800801c8  sub     r9, r8
0x1800801cb  sar     r9, 1; cchCount2
0x1800801ce  mov     rcx, [r15+48h]; lpString1
0x1800801d2  mov     rdx, [r15+50h]
0x1800801d6  sub     rdx, rcx
0x1800801d9  sar     rdx, 1; cchCount1
0x1800801dc  cmp     rdx, r9
0x1800801df  jnz     loc_180080302
0x1800801e5  mov     [rsp+5B0h+bIgnoreCase], 1; bIgnoreCase
0x1800801ed  call    cs:__imp_CompareStringOrdinal
0x1800801f3  cmp     eax, 2
0x1800801f6  jnz     loc_180080302
0x1800801fc  mov     rbx, [rsp+5B0h+var_580]
0x180080201  movaps  xmm0, xmmword ptr [rbx]
0x180080204  movdqa  [rsp+5B0h+var_570], xmm0
0x18008020a  mov     edx, 3A9Ch
0x18008020f  lea     rcx, [rsp+5B0h+var_570]
0x180080214  call    ScanForInvalidChars
0x180080219  mov     ebx, eax
0x18008021b  xor     eax, eax
0x18008021d  test    ebx, ebx
0x18008021f  jnz     loc_180080B24
0x180080225  mov     [r15+88h], al
0x18008022c  lea     rdx, [rsp+5B0h+var_580]
0x180080231  lea     rcx, [rbp+4B0h+var_270]
0x180080238  call    ?GetCurrentPublisherKey@PublisherConfigEnumerator@@QEAA?AV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@K@Z; PublisherConfigEnumerator::GetCurrentPublisherKey(ulong)
0x18008023d  mov     rdx, rax
0x180080240  mov     rcx, r15
0x180080243  call    ??4?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::operator=(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &&)
0x180080248  lea     rcx, [rsp+5B0h+var_580]
0x18008024d  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180080252  movups  xmm0, xmmword ptr [rbp+4B0h+var_4B0]
0x180080256  movdqu  xmmword ptr [r13+0], xmm0
0x18008025c  mov     r8b, 1
0x18008025f  mov     rdx, r13
0x180080262  lea     rcx, [r15+28h]
0x180080266  call    ??$assign_guid@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEBU_GUID@@_N@Z; tlx::assign_guid<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,_GUID const &,bool)
0x18008026b  test    eax, eax
0x18008026d  js      loc_180080B6C
0x180080273  mov     r8, [r15]
0x180080276  mov     rdx, r13
0x180080279  lea     rcx, [rsp+5B0h+var_580]
0x18008027e  call    ?AddRegCacheProviderNode@@YA?AV?$AutoRef@UREG_CACHE_PROVIDERNODE@@@wmi@@PEBU_GUID@@PEAUHKEY__@@@Z; AddRegCacheProviderNode(_GUID const *,HKEY__ *)
0x180080283  mov     rbx, rax
0x180080286  mov     rcx, r12
0x180080289  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x18008028e  mov     rcx, [rbx]
0x180080291  mov     [r12], rcx
0x180080295  mov     qword ptr [rbx], 0
0x18008029c  lea     rcx, [rsp+5B0h+var_580]
0x1800802a1  call    ?Release@?$AutoRef@VPublisherMetadata@@@wmi@@QEAAXXZ; wmi::AutoRef<PublisherMetadata>::Release(void)
0x1800802a6  nop
0x1800802a7  lea     rcx, [rsp+5B0h+lpString2]; void *
0x1800802ac  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800802b1  nop
0x1800802b2  lea     rcx, [rbp+4B0h+var_270]
0x1800802b9  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800802be  jmp     loc_180080774
0x1800802c3  mov     rax, [rbp+4B0h+var_260]
0x1800802ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800802d1  cmp     rcx, rsi
0x1800802d4  jz      short loc_180080302
0x1800802d6  test    [rcx+1Ch], dil
0x1800802da  jz      short loc_180080302
0x1800802dc  cmp     byte ptr [rcx+19h], 3
0x1800802e0  jb      short loc_180080302
0x1800802e2  mov     qword ptr [rsp+5B0h+var_570], rax
0x1800802e7  mov     qword ptr [rsp+5B0h+var_570+8], rbx
0x1800802ec  mov     edx, 1Eh
0x1800802f1  lea     r9, [rsp+5B0h+var_570]
0x1800802f6  mov     r8, r14
0x1800802f9  mov     rcx, [rcx+10h]
0x1800802fd  call    WPP_SF__utlwsv_
0x180080302  lea     rcx, [rbp+4B0h+var_270]; this
0x180080309  call    ?MoveNext@RegistryKeyEnumerator@@QEAAKXZ; RegistryKeyEnumerator::MoveNext(void)
0x18008030e  cmp     eax, 103h
0x180080313  jnz     loc_180080132
0x180080319  lea     rcx, [rsp+5B0h+lpString2]; void *
0x18008031e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180080323  nop
0x180080324  lea     rcx, [rbp+4B0h+var_270]
0x18008032b  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180080330  xor     ecx, ecx
0x180080332  mov     [rbp+4B0h+var_4B0], rcx
0x180080336  lea     rax, [rbp+4B0h+var_4D0]
0x18008033a  mov     [rbp+4B0h+var_4E0], rax
0x18008033e  lea     rax, [rbp+4B0h+var_4D0]
0x180080342  mov     [rbp+4B0h+var_4D8], rax
0x180080346  mov     [rbp+4B0h+var_4D0], cx
0x18008034a  lea     r8, [rbp+4B0h+var_4E0]
0x18008034e  lea     rdx, [rbp+4B0h+var_4B0]
0x180080352  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180080357  mov     ebx, eax
0x180080359  xor     eax, eax
0x18008035b  test    ebx, ebx
0x18008035d  jnz     loc_1800808A2
0x180080363  mov     [rbp+4B0h+var_528], rax
0x180080367  mov     rbx, [r15+8]
0x18008036b  lea     rcx, [rbp+4B0h+var_528]
0x18008036f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180080374  mov     qword ptr [rsp+5B0h+bIgnoreCase], rbx; void *
0x180080379  mov     r9, rax; HKEY *
0x18008037c  mov     r8d, 20019h; unsigned int
0x180080382  mov     rdx, [rbp+4B0h+var_4E0]; wchar_t *
0x180080386  mov     rcx, [rbp+4B0h+var_4B0]; HKEY
0x18008038a  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x18008038f  mov     ebx, eax
0x180080391  test    eax, eax
0x180080393  jnz     loc_180080BBD
0x180080399  mov     r8, [r15+8]; void *
0x18008039d  mov     rdx, [rbp+4B0h+var_528]; HKEY
0x1800803a1  lea     rcx, [rbp+4B0h+var_4A0]; this
0x1800803a5  call    ??0RegistryKeyEnumerator@@QEAA@PEAUHKEY__@@PEAX@Z; RegistryKeyEnumerator::RegistryKeyEnumerator(HKEY__ *,void *)
0x1800803aa  nop
0x1800803ab  mov     eax, [rbp+4B0h+var_47C]
0x1800803ae  mov     [rbp+4B0h+var_480], eax
0x1800803b1  jmp     loc_18008049D
0x1800803b6  mov     rbx, qword ptr [rbp+4B0h+var_490]
0x1800803ba  mov     qword ptr [rsp+5B0h+var_570], rbx
0x1800803bf  mov     rax, qword ptr [rbp+4B0h+var_490+8]
  ... truncated ...
```
