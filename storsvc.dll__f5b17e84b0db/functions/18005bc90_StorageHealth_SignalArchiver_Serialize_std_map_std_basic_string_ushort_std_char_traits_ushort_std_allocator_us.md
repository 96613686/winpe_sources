# StorageHealth::SignalArchiver::Serialize(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,StorageHealth::_SignalArchiveData,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,StorageHealth::_SignalArchiveData>>> const &,unsigned __int64)

- ea: `0x18005bc90`
- end: `0x18005c6bd`
- name: `?Serialize@SignalArchiver@StorageHealth@@QEAAJAEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SignalArchiveData@StorageHealth@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SignalArchiveData@StorageHealth@@@std@@@2@@std@@_K@Z`
- size: `2605`
- prototype: ``
- caller_count: `1`
- callee_count: `35`
- tags: ``

## callers

- `0x180054558`

## callees

- `0x180001148`
- `0x180004498`
- `0x18000d030`
- `0x180019318`
- `0x180019dd4`
- `0x18001c130`
- `0x18001c208`
- `0x18001ee68`
- `0x18001f634`
- `0x18003d054`
- `0x18003d0a8`
- `0x18003d254`
- `0x1800416b4`
- `0x18004196c`
- `0x180043b14`
- `0x18004b074`
- `0x18004b7c0`
- `0x18004ebe0`
- `0x180050b50`
- `0x180050d1c`
- `0x180050db0`
- `0x18005126c`
- `0x180051740`
- `0x1800524d8`
- `0x18005290c`
- `0x180053174`
- `0x180053534`
- `0x180053908`
- `0x18005a3e4`
- `0x18005a9b8`
- `0x18005af1c`
- `0x18005b2e4`
- `0x18005bc90`
- `0x18005c984`
- `0x18005ca90`

## import_xrefs

- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18005c56d`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18005c56d`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18005c57a`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18005c5d5`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18005c57a`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18005c5d5`
- `msvcp_win!?exceptions@ios_base@std@@QEAAXH@Z` at `0x18005c4c2`
- `msvcp_win!?exceptions@ios_base@std@@QEAAXH@Z` at `0x18005c4c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c482`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005c46b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005c46b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18005c1f9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18005c1f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall StorageHealth::SignalArchiver::Serialize(__int64 a1, __int64 **a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // r13
  __int64 **v4; // rbx
  unsigned __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rbx
  _DWORD *v15; // r10
  _DWORD *v16; // r8
  __int64 i; // rax
  unsigned __int64 v18; // r12
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  _QWORD *v22; // rax
  unsigned __int64 v23; // r14
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // r15
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  unsigned __int64 v33; // r13
  __int64 v34; // rax
  __int64 **v35; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  signed int LastError; // eax
  signed int v39; // ebx
  const WCHAR *v40; // rcx
  signed int v41; // eax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  bool v45; // zf
  __int64 v46; // rcx
  __int64 v47; // rax
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  struct _FILETIME FileTime; // [rsp+40h] [rbp-2C8h] BYREF
  __int128 v53; // [rsp+48h] [rbp-2C0h] BYREF
  __int128 v54; // [rsp+58h] [rbp-2B0h] BYREF
  _DWORD *v55; // [rsp+68h] [rbp-2A0h]
  unsigned __int64 v56; // [rsp+70h] [rbp-298h]
  __int64 v57; // [rsp+78h] [rbp-290h] BYREF
  unsigned __int64 v58; // [rsp+80h] [rbp-288h] BYREF
  __int64 **v59; // [rsp+88h] [rbp-280h]
  __int128 *v60; // [rsp+90h] [rbp-278h] BYREF
  __int128 *v61; // [rsp+98h] [rbp-270h]
  __int128 *v62; // [rsp+A0h] [rbp-268h] BYREF
  __int128 *v63; // [rsp+A8h] [rbp-260h]
  __int128 *v64; // [rsp+B0h] [rbp-258h] BYREF
  __int128 *v65; // [rsp+B8h] [rbp-250h]
  char v66[16]; // [rsp+C0h] [rbp-248h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-238h] BYREF
  _BYTE v68[128]; // [rsp+D8h] [rbp-230h] BYREF
  __int64 v69; // [rsp+158h] [rbp-1B0h]
  __int128 v70; // [rsp+1E0h] [rbp-128h] BYREF
  __int128 v71; // [rsp+1F0h] [rbp-118h] BYREF
  _BYTE v72[32]; // [rsp+200h] [rbp-108h] BYREF
  _BYTE v73[32]; // [rsp+220h] [rbp-E8h] BYREF
  _BYTE v74[16]; // [rsp+240h] [rbp-C8h] BYREF
  _BYTE v75[6]; // [rsp+26Ah] [rbp-9Eh] BYREF
  _QWORD v76[2]; // [rsp+270h] [rbp-98h] BYREF
  _BYTE v77[48]; // [rsp+29Ah] [rbp-6Eh] BYREF
  _BYTE v78[6]; // [rsp+2CAh] [rbp-3Eh] BYREF

  v3 = a3;
  v56 = a3;
  v4 = a2;
  v59 = a2;
  v58 = a3;
  v5 = 0;
  std::operator+<unsigned short>(v72, qword_1800C6540, L"\n");
  std::wstring::wstring(v73, &word_180092AF0);
  std::basic_ofstream<unsigned short>::basic_ofstream<unsigned short>(&v67);
  v6 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v77, v4[1]);
  std::wstring::wstring(v74, v6, v77);
  v7 = std::operator+<unsigned short>(&v70, v74, L"\n");
  v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
  std::wstring::_Append<unsigned short>(v72, v8);
  std::wstring::_Tidy_deallocate(&v70);
  std::wstring::_Tidy_deallocate(v74);
  v9 = (__int64 *)**v4;
  while ( v9 != *v4 )
  {
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9 + 4);
    std::wstring::_Append<unsigned short>(v72, v10);
    std::wstring::_Append<unsigned short>(v72, L"\n");
    v70 = 0;
    v60 = &v70;
    v61 = &v70;
    *(_QWORD *)&v70 = std::_Tree_node<std::pair<int const,unsigned __int64>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<int const,unsigned __int64>,void *>>>();
    std::_Tree<std::_Tmap_traits<int,_SYSTEMTIME,std::less<int>,std::allocator<std::pair<int const,_SYSTEMTIME>>,0>>::_Copy<0>(
      &v70,
      v9 + 8);
    v61 = 0;
    std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,_SYSTEMTIME>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,_SYSTEMTIME>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,_SYSTEMTIME>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,_SYSTEMTIME>>>>(&v60);
    v71 = 0;
    v62 = &v71;
    v63 = &v71;
    *(_QWORD *)&v71 = std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>>();
    std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>>::_Copy<0>(
      &v71,
      v9 + 10);
    v63 = 0;
    std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>>(&v62);
    v11 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v75, *((_QWORD *)&v71 + 1));
    std::wstring::wstring(v76, v11, v75);
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v76);
    std::wstring::_Append<unsigned short>(v72, v12);
    std::wstring::_Tidy_deallocate(v76);
    std::wstring::_Append<unsigned short>(v72, L"\n");
    v54 = 0;
    v55 = 0;
    v53 = 0;
    v64 = &v53;
    v65 = &v53;
    *(_QWORD *)&v53 = std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>>();
    std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>>::_Copy<0>(
      &v53,
      &v71);
    v65 = 0;
    std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>>(&v64);
    v14 = *(_QWORD *)v53;
    v15 = (_DWORD *)*((_QWORD *)&v54 + 1);
    while ( v14 != (_QWORD)v53 )
    {
      v16 = (_DWORD *)(v14 + 32);
      if ( v15 == v55 )
      {
        std::vector<int>::_Emplace_reallocate<int const &>(&v54, v15, v16);
        v15 = (_DWORD *)*((_QWORD *)&v54 + 1);
      }
      else
      {
        *v15 = *v16;
        v15 = (_DWORD *)(*((_QWORD *)&v54 + 1) + 4LL);
        *((_QWORD *)&v54 + 1) += 4LL;
      }
      if ( *(_BYTE *)(*(_QWORD *)(v14 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v14 + 8); !*(_BYTE *)(i + 25) && v14 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v14 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>::_Min();
      }
      v14 = i;
    }
    LOBYTE(v13) = 0;
    std::_Sort_unchecked<int *,std::less<void>>(v54, v15, (__int64)((__int64)v15 - v54) >> 2, v13);
    v18 = 0;
    v19 = v54;
    if ( (__int64)(*((_QWORD *)&v54 + 1) - v54) >> 2 )
    {
      while ( 1 )
      {
        v20 = std::to_wstring(v74, *(unsigned int *)(v19 + 4 * v18));
        v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
        std::wstring::_Append<unsigned short>(v72, v21);
        std::wstring::_Tidy_deallocate(v74);
        std::wstring::_Append<unsigned short>(v72, L"\n");
        v22 = (_QWORD *)std::map<int,std::vector<StorageHealth::_SignalValues>>::_Try_emplace<int const &,>(
                          &v53,
                          v66,
                          v54 + 4 * v18);
        std::vector<StorageHealth::_SignalValues>::vector<StorageHealth::_SignalValues>(v76, *v22 + 40LL);
        v23 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v76[1] - v76[0]) >> 4);
        if ( v23 )
          v24 = (__int64)(*(_QWORD *)(v76[0] + 32LL) - *(_QWORD *)(v76[0] + 24LL)) >> 5;
        else
          v24 = 0;
        v25 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v78, v24);
        std::wstring::wstring(v74, v25, v78);
        v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
        std::wstring::_Append<unsigned short>(v72, v26);
        std::wstring::_Tidy_deallocate(v74);
        std::wstring::_Append<unsigned short>(v72, L"\n");
        if ( v3 < v23 )
          v23 = v3;
        v27 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(v78, v23);
        std::wstring::wstring(v74, v27, v78);
        v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
        std::wstring::_Append<unsigned short>(v72, v28);
        std::wstring::_Tidy_deallocate(v74);
        std::wstring::_Append<unsigned short>(v72, L"\n");
        v29 = 0;
        if ( v23 )
          break;
LABEL_29:
        std::vector<StorageHealth::_SignalValues>::_Tidy(v76);
        ++v18;
        v19 = v54;
        if ( v18 >= (__int64)(*((_QWORD *)&v54 + 1) - v54) >> 2 )
          goto LABEL_30;
      }
      while ( 1 )
      {
        v30 = 48 * v29;
        if ( *(_QWORD *)(48 * v29 + v76[0] + 24) == *(_QWORD *)(48 * v29 + v76[0] + 32) )
        {
          v39 = -2147467259;
          std::vector<StorageHealth::_SignalValues>::_Tidy(v76);
          std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>>(
            &v53,
            &v53);
          std::vector<unsigned int>::_Tidy(&v54);
          StorageHealth::_SignalArchiveData::~_SignalArchiveData((StorageHealth::_SignalArchiveData *)&v70);
          v3 = v56;
          goto LABEL_59;
        }
        FileTime = 0;
        if ( !SystemTimeToFileTime((const SYSTEMTIME *)(v30 + v76[0] + 4LL), &FileTime) )
          break;
        v31 = std::_UIntegral_to_buff<unsigned short,unsigned __int64>(
                v78,
                FileTime.dwLowDateTime + ((unsigned __int64)FileTime.dwHighDateTime << 32));
        std::wstring::wstring(v74, v31, v78);
        v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
        std::wstring::_Append<unsigned short>(v72, v32);
        std::wstring::_Tidy_deallocate(v74);
        v33 = (__int64)(*(_QWORD *)(v30 + v76[0] + 32) - *(_QWORD *)(v30 + v76[0] + 24)) >> 5;
        v57 = 0;
        if ( v33 )
        {
          do
          {
            std::wstring::_Append<unsigned short>(v72, L"\t");
            v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(32 * v5 + *(_QWORD *)(v76[0] + v30 + 24));
            std::wstring::_Append<unsigned short>(v72, v34);
            ++v5;
          }
          while ( v5 < v33 );
          v5 = 0;
        }
        std::wstring::_Append<unsigned short>(v72, L"\n");
        if ( ++v29 >= v23 )
        {
          v3 = v56;
          goto LABEL_29;
        }
      }
      LastError = GetLastError();
      v39 = LastError;
      if ( LastError > 0 )
        v39 = (unsigned __int16)LastError | 0x80070000;
      std::vector<StorageHealth::_SignalValues>::_Tidy(v76);
      std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>>(
        &v53,
        &v53);
      std::vector<unsigned int>::_Tidy(&v54);
      StorageHealth::_SignalArchiveData::~_SignalArchiveData((StorageHealth::_SignalArchiveData *)&v70);
      v3 = v56;
      goto LABEL_48;
    }
LABEL_30:
    std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>>(
      &v53,
      &v53);
    std::vector<unsigned int>::_Tidy(&v54);
    StorageHealth::_SignalArchiveData::~_SignalArchiveData((StorageHealth::_SignalArchiveData *)&v70);
    v35 = (__int64 **)v9[2];
    if ( *((_BYTE *)v35 + 25) )
    {
      for ( j = (__int64 *)v9[1]; !*((_BYTE *)j + 25) && v9 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v9 = j;
      v9 = j;
    }
    else
    {
      v9 = (__int64 *)v9[2];
      for ( k = *v35; !*((_BYTE *)k + 25); k = (__int64 *)*k )
        v9 = k;
    }
    v4 = v59;
  }
  v40 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_1800C6520);
  if ( !CreateDirectoryW(v40, 0) && GetLastError() != 183 )
  {
    v41 = GetLastError();
    v39 = v41;
    if ( v41 > 0 )
      v39 = (unsigned __int16)v41 | 0x80070000;
LABEL_48:
    if ( v39 >= 0 )
      goto LABEL_62;
LABEL_59:
    if ( (unsigned int)dword_1800BF100 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF100, 0x400000000000LL) )
    {
      FileTime.dwLowDateTime = v39;
      v58 = v3;
      v57 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v48,
        (unsigned int)byte_1800A87E3,
        v49,
        v50,
        (__int64)&v57,
        (__int64)&v58,
        (__int64)&FileTime);
    }
    goto LABEL_62;
  }
  v39 = 0;
  std::ios_base::exceptions((std::ios_base *)&v68[*(int *)(v67 + 4) - 8], 4);
  try
  {
    v42 = std::operator+<unsigned short>(&v70, qword_1800C6520, L"\\");
    v43 = std::operator+<unsigned short>(v74, v42, qword_1800C6500);
    std::wstring::operator=(v73, v43);
    std::wstring::_Tidy_deallocate(v74);
    std::wstring::_Tidy_deallocate(&v70);
    v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
    v45 = std::basic_filebuf<unsigned short>::open(v68, v44, 2) == 0;
    v46 = *(int *)(v67 + 4);
    if ( v45 )
      std::basic_ios<unsigned short>::setstate(&v68[v46 - 8], 2, 0);
    else
      std::basic_ios<unsigned short>::clear(&v68[v46 - 8], 0, 0);
  }
  catch ( std::ios_base::failure )
  {
    FileTime.dwLowDateTime = -2147467259;
    v39 = -2147467259;
    v3 = v58;
    goto LABEL_59;
  }
  if ( !v69 )
  {
    v39 = -2147024786;
    goto LABEL_59;
  }
  v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
  std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v67, v47);
  if ( !std::basic_filebuf<unsigned short>::close(v68) )
    std::basic_ios<unsigned short>::setstate(&v68[*(int *)(v67 + 4) - 8], 2, 0);
LABEL_62:
  std::basic_ofstream<unsigned short>::`vbase destructor'(&v67);
  std::wstring::_Tidy_deallocate(v73);
  std::wstring::_Tidy_deallocate(v72);
  return (unsigned int)v39;
}

```

## disassembly

```asm
0x18005bc90  mov     [rsp+arg_0], rbx
0x18005bc95  mov     [rsp+arg_18], rsi
0x18005bc9a  push    rdi
0x18005bc9b  push    r12
0x18005bc9d  push    r13
0x18005bc9f  push    r14
0x18005bca1  push    r15
0x18005bca3  sub     rsp, 2E0h
0x18005bcaa  mov     rax, cs:__security_cookie
0x18005bcb1  xor     rax, rsp
0x18005bcb4  mov     [rsp+308h+var_38], rax
0x18005bcbc  mov     r13, r8
0x18005bcbf  mov     [rsp+308h+var_298], r8
0x18005bcc4  mov     rbx, rdx
0x18005bcc7  mov     [rsp+308h+var_280], rdx
0x18005bccf  mov     [rsp+308h+var_288], r8
0x18005bcd7  xor     esi, esi
0x18005bcd9  lea     r14, asc_180092918; "\n"
0x18005bce0  mov     r8, r14
0x18005bce3  lea     rdx, qword_1800C6540
0x18005bcea  lea     rcx, [rsp+308h+var_108]
0x18005bcf2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18005bcf7  nop
0x18005bcf8  lea     rdx, word_180092AF0
0x18005bcff  lea     rcx, [rsp+308h+var_E8]
0x18005bd07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005bd0c  nop
0x18005bd0d  lea     rcx, [rsp+308h+var_238]
0x18005bd15  call    ??0?$basic_ofstream@GU?$char_traits@G@std@@@std@@QEAA@XZ; std::basic_ofstream<ushort>::basic_ofstream<ushort>(void)
0x18005bd1a  nop
0x18005bd1b  mov     rdx, [rbx+8]
0x18005bd1f  lea     rcx, [rsp+308h+var_6E]
0x18005bd27  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x18005bd2c  lea     r8, [rsp+308h+var_6E]
0x18005bd34  mov     rdx, rax
0x18005bd37  lea     rcx, [rsp+308h+var_C8]
0x18005bd3f  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18005bd44  nop
0x18005bd45  mov     r8, r14
0x18005bd48  lea     rdx, [rsp+308h+var_C8]
0x18005bd50  lea     rcx, [rsp+308h+var_128]
0x18005bd58  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18005bd5d  mov     r8, [rax+10h]
0x18005bd61  mov     rcx, rax
0x18005bd64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005bd69  mov     rdx, rax
0x18005bd6c  lea     rcx, [rsp+308h+var_108]
0x18005bd74  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005bd79  nop
0x18005bd7a  lea     rcx, [rsp+308h+var_128]
0x18005bd82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bd87  nop
0x18005bd88  lea     rcx, [rsp+308h+var_C8]
0x18005bd90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bd95  mov     rdi, [rbx]
0x18005bd98  mov     rdi, [rdi]
0x18005bd9b  lea     r15d, [rsi+1]
0x18005bd9f  cmp     rdi, [rbx]
0x18005bda2  jz      loc_18005C45A
0x18005bda8  lea     rcx, [rdi+20h]
0x18005bdac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005bdb1  mov     r8, [rdi+30h]
0x18005bdb5  mov     rdx, rax
0x18005bdb8  lea     rcx, [rsp+308h+var_108]
0x18005bdc0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005bdc5  mov     r8, r15
0x18005bdc8  mov     rdx, r14
0x18005bdcb  lea     rcx, [rsp+308h+var_108]
0x18005bdd3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005bdd8  xorps   xmm0, xmm0
0x18005bddb  movdqu  [rsp+308h+var_128], xmm0
0x18005bde4  lea     rax, [rsp+308h+var_128]
0x18005bdec  mov     [rsp+308h+var_278], rax
0x18005bdf4  lea     rax, [rsp+308h+var_128]
0x18005bdfc  mov     [rsp+308h+var_270], rax
0x18005be04  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBH_K@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBH_K@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBH_K@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<int const,unsigned __int64>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<int const,unsigned __int64>,void *>>>(std::allocator<std::_Tree_node<std::pair<int const,unsigned __int64>,void *>> &)
0x18005be09  mov     qword ptr [rsp+308h+var_128], rax
0x18005be11  lea     rdx, [rdi+40h]
0x18005be15  lea     rcx, [rsp+308h+var_128]
0x18005be1d  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@HU_SYSTEMTIME@@U?$less@H@std@@V?$allocator@U?$pair@$$CBHU_SYSTEMTIME@@@std@@@3@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<int,_SYSTEMTIME,std::less<int>,std::allocator<std::pair<int const,_SYSTEMTIME>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<int,_SYSTEMTIME,std::less<int>,std::allocator<std::pair<int const,_SYSTEMTIME>>,0>> const &)
0x18005be22  mov     [rsp+308h+var_270], rsi
0x18005be2a  lea     rcx, [rsp+308h+var_278]
0x18005be32  call    ??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBHU_SYSTEMTIME@@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBHU_SYSTEMTIME@@@std@@@std@@@2@@std@@QEAA@XZ; std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,_SYSTEMTIME>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,_SYSTEMTIME>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,_SYSTEMTIME>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,_SYSTEMTIME>>>>(void)
0x18005be37  nop
0x18005be38  xorps   xmm0, xmm0
0x18005be3b  movdqu  [rsp+308h+var_118], xmm0
0x18005be44  lea     rax, [rsp+308h+var_118]
0x18005be4c  mov     [rsp+308h+var_268], rax
0x18005be54  lea     rax, [rsp+308h+var_118]
0x18005be5c  mov     [rsp+308h+var_260], rax
0x18005be64  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>>(std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>> &)
0x18005be69  mov     qword ptr [rsp+308h+var_118], rax
0x18005be71  lea     rdx, [rdi+50h]
0x18005be75  lea     rcx, [rsp+308h+var_118]
0x18005be7d  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@HV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>> const &)
0x18005be82  mov     [rsp+308h+var_260], rsi
0x18005be8a  lea     rcx, [rsp+308h+var_268]
0x18005be92  call    ??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>>(void)
0x18005be97  nop
0x18005be98  mov     rdx, qword ptr [rsp+308h+var_118+8]
0x18005bea0  lea     rcx, [rsp+308h+var_9E]
0x18005bea8  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x18005bead  lea     r8, [rsp+308h+var_9E]
0x18005beb5  mov     rdx, rax
0x18005beb8  lea     rcx, [rsp+308h+var_98]
0x18005bec0  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18005bec5  nop
0x18005bec6  lea     rcx, [rsp+308h+var_98]
0x18005bece  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005bed3  mov     rdx, rax
0x18005bed6  mov     r8, [rsp+308h+var_88]
0x18005bede  lea     rcx, [rsp+308h+var_108]
0x18005bee6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005beeb  nop
0x18005beec  lea     rcx, [rsp+308h+var_98]
0x18005bef4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bef9  mov     r8, r15
0x18005befc  mov     rdx, r14
0x18005beff  lea     rcx, [rsp+308h+var_108]
0x18005bf07  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005bf0c  xorps   xmm0, xmm0
0x18005bf0f  movdqu  [rsp+308h+var_2B0], xmm0
0x18005bf15  mov     [rsp+308h+var_2A0], rsi
0x18005bf1a  movdqu  [rsp+308h+var_2C0], xmm0
0x18005bf20  lea     rax, [rsp+308h+var_2C0]
0x18005bf25  mov     [rsp+308h+var_258], rax
0x18005bf2d  lea     rax, [rsp+308h+var_2C0]
0x18005bf32  mov     [rsp+308h+var_250], rax
0x18005bf3a  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>>(std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>> &)
0x18005bf3f  mov     qword ptr [rsp+308h+var_2C0], rax
0x18005bf44  lea     rdx, [rsp+308h+var_118]
0x18005bf4c  lea     rcx, [rsp+308h+var_2C0]
0x18005bf51  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@HV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<int,std::vector<StorageHealth::_SignalValues>,std::less<int>,std::allocator<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>,0>> const &)
0x18005bf56  mov     [rsp+308h+var_250], rsi
0x18005bf5e  lea     rcx, [rsp+308h+var_258]
0x18005bf66  call    ??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<int const,std::vector<StorageHealth::_SignalValues>>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<int const,std::vector<StorageHealth::_SignalValues>>>>>(void)
0x18005bf6b  nop
0x18005bf6c  mov     rbx, qword ptr [rsp+308h+var_2C0]
0x18005bf71  mov     rbx, [rbx]
0x18005bf74  mov     r10, qword ptr [rsp+308h+var_2B0+8]
0x18005bf79  cmp     rbx, qword ptr [rsp+308h+var_2C0]
0x18005bf7e  jz      short loc_18005BFE2
0x18005bf80  lea     r8, [rbx+20h]
0x18005bf84  cmp     r10, [rsp+308h+var_2A0]
0x18005bf89  jz      short loc_18005BFA1
0x18005bf8b  mov     eax, [r8]
0x18005bf8e  mov     [r10], eax
0x18005bf91  mov     r10, qword ptr [rsp+308h+var_2B0+8]
0x18005bf96  add     r10, 4
0x18005bf9a  mov     qword ptr [rsp+308h+var_2B0+8], r10
0x18005bf9f  jmp     short loc_18005BFB3
0x18005bfa1  mov     rdx, r10
0x18005bfa4  lea     rcx, [rsp+308h+var_2B0]
0x18005bfa9  call    ??$_Emplace_reallocate@AEBH@?$vector@HV?$allocator@H@std@@@std@@AEAAPEAHQEAHAEBH@Z; std::vector<int>::_Emplace_reallocate<int const &>(int * const,int const &)
0x18005bfae  mov     r10, qword ptr [rsp+308h+var_2B0+8]
0x18005bfb3  mov     rcx, [rbx+10h]
0x18005bfb7  cmp     [rcx+19h], sil
0x18005bfbb  jz      short loc_18005BFDB
0x18005bfbd  mov     rax, [rbx+8]
0x18005bfc1  jmp     short loc_18005BFD0
0x18005bfc3  cmp     rbx, [rax+10h]
0x18005bfc7  jnz     short loc_18005BFD6
0x18005bfc9  mov     rbx, rax
0x18005bfcc  mov     rax, [rax+8]
0x18005bfd0  cmp     [rax+19h], sil
0x18005bfd4  jz      short loc_18005BFC3
0x18005bfd6  mov     rbx, rax
0x18005bfd9  jmp     short loc_18005BF79
0x18005bfdb  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@NV?$allocator@N@std@@@2@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<double>>>>::_Min(std::_Tree_node<std::pair<std::wstring const,std::vector<double>>,void *> *)
0x18005bfe0  jmp     short loc_18005BFD6
0x18005bfe2  mov     rcx, qword ptr [rsp+308h+var_2B0]
0x18005bfe7  mov     r8, r10
0x18005bfea  sub     r8, rcx
0x18005bfed  sar     r8, 2
0x18005bff1  mov     r9b, sil
0x18005bff4  mov     rdx, r10
0x18005bff7  call    ??$_Sort_unchecked@PEAHU?$less@X@std@@@std@@YAXPEAH0_JU?$less@X@0@@Z; std::_Sort_unchecked<int *,std::less<void>>(int *,int *,__int64,std::less<void>)
0x18005bffc  mov     r12, rsi
0x18005bfff  mov     rax, qword ptr [rsp+308h+var_2B0+8]
0x18005c004  mov     rcx, qword ptr [rsp+308h+var_2B0]
0x18005c009  sub     rax, rcx
0x18005c00c  sar     rax, 2
0x18005c010  test    rax, rax
0x18005c013  jz      loc_18005C348
0x18005c019  mov     edx, [rcx+r12*4]
0x18005c01d  lea     rcx, [rsp+308h+var_C8]
0x18005c025  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x18005c02a  mov     r8, [rax+10h]
0x18005c02e  mov     rcx, rax
0x18005c031  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c036  mov     rdx, rax
0x18005c039  lea     rcx, [rsp+308h+var_108]
0x18005c041  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005c046  nop
0x18005c047  lea     rcx, [rsp+308h+var_C8]
0x18005c04f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c054  mov     r8, r15
0x18005c057  mov     rdx, r14
0x18005c05a  lea     rcx, [rsp+308h+var_108]
0x18005c062  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005c067  mov     rax, qword ptr [rsp+308h+var_2B0]
0x18005c06c  lea     r8, [rax+r12*4]
0x18005c070  lea     rdx, [rsp+308h+var_248]
0x18005c078  lea     rcx, [rsp+308h+var_2C0]
0x18005c07d  call    ??$_Try_emplace@AEBH$$V@?$map@HV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBHV?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@@std@@PEAX@std@@_N@1@AEBH@Z; std::map<int,std::vector<StorageHealth::_SignalValues>>::_Try_emplace<int const &,>(int const &)
0x18005c082  mov     rdx, [rax]
0x18005c085  add     rdx, 28h ; '('
0x18005c089  lea     rcx, [rsp+308h+var_98]
0x18005c091  call    ??0?$vector@U_SignalValues@StorageHealth@@V?$allocator@U_SignalValues@StorageHealth@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<StorageHealth::_SignalValues>::vector<StorageHealth::_SignalValues>(std::vector<StorageHealth::_SignalValues> const &)
0x18005c096  nop
0x18005c097  mov     r14, [rsp+308h+var_90]
0x18005c09f  mov     rax, [rsp+308h+var_98]
0x18005c0a7  sub     r14, rax
0x18005c0aa  sar     r14, 4
0x18005c0ae  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18005c0b8  imul    r14, rcx
0x18005c0bc  test    r14, r14
0x18005c0bf  jnz     short loc_18005C0C6
0x18005c0c1  mov     rdx, rsi
0x18005c0c4  jmp     short loc_18005C0D2
0x18005c0c6  mov     rdx, [rax+20h]
0x18005c0ca  sub     rdx, [rax+18h]
0x18005c0ce  sar     rdx, 5
0x18005c0d2  lea     rcx, [rsp+308h+var_3E]
0x18005c0da  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x18005c0df  lea     r8, [rsp+308h+var_3E]
0x18005c0e7  mov     rdx, rax
0x18005c0ea  lea     rcx, [rsp+308h+var_C8]
0x18005c0f2  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18005c0f7  nop
0x18005c0f8  lea     rcx, [rsp+308h+var_C8]
0x18005c100  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c105  mov     rdx, rax
0x18005c108  mov     r8, [rsp+308h+var_B8]
0x18005c110  lea     rcx, [rsp+308h+var_108]
0x18005c118  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005c11d  nop
0x18005c11e  lea     rcx, [rsp+308h+var_C8]
0x18005c126  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c12b  mov     r8, r15
0x18005c12e  lea     rdx, asc_180092918; "\n"
0x18005c135  lea     rcx, [rsp+308h+var_108]
0x18005c13d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005c142  cmp     r13, r14
0x18005c145  cmovb   r14, r13
0x18005c149  mov     rdx, r14
0x18005c14c  lea     rcx, [rsp+308h+var_3E]
0x18005c154  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x18005c159  lea     r8, [rsp+308h+var_3E]
0x18005c161  mov     rdx, rax
0x18005c164  lea     rcx, [rsp+308h+var_C8]
0x18005c16c  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18005c171  nop
0x18005c172  lea     rcx, [rsp+308h+var_C8]
0x18005c17a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c17f  mov     rdx, rax
0x18005c182  mov     r8, [rsp+308h+var_B8]
0x18005c18a  lea     rcx, [rsp+308h+var_108]
0x18005c192  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005c197  nop
0x18005c198  lea     rcx, [rsp+308h+var_C8]
0x18005c1a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005c1a5  mov     r8, r15
0x18005c1a8  lea     rdx, asc_180092918; "\n"
0x18005c1af  lea     rcx, [rsp+308h+var_108]
0x18005c1b7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005c1bc  mov     r15, rsi
0x18005c1bf  test    r14, r14
0x18005c1c2  jz      loc_18005C311
0x18005c1c8  lea     rbx, [r15+r15*2]
0x18005c1cc  shl     rbx, 4
0x18005c1d0  mov     rcx, [rsp+308h+var_98]
0x18005c1d8  mov     rax, [rbx+rcx+20h]
0x18005c1dd  cmp     [rbx+rcx+18h], rax
0x18005c1e2  jz      loc_18005C415
0x18005c1e8  mov     qword ptr [rsp+308h+FileTime.dwLowDateTime], rsi
0x18005c1ed  add     rcx, 4
0x18005c1f1  add     rcx, rbx; lpSystemTime
0x18005c1f4  lea     rdx, [rsp+308h+FileTime]; lpFileTime
0x18005c1f9  call    cs:__imp_SystemTimeToFileTime
0x18005c1ff  test    eax, eax
0x18005c201  jz      loc_18005C3C0
0x18005c207  mov     edx, [rsp+308h+FileTime.dwHighDateTime]
0x18005c20b  shl     rdx, 20h
0x18005c20f  mov     eax, [rsp+308h+FileTime.dwLowDateTime]
0x18005c213  add     rdx, rax
0x18005c216  lea     rcx, [rsp+308h+var_3E]
0x18005c21e  call    ??$_UIntegral_to_buff@G_K@std@@YAPEAGPEAG_K@Z; std::_UIntegral_to_buff<ushort,unsigned __int64>(ushort *,unsigned __int64)
0x18005c223  lea     r8, [rsp+308h+var_3E]
0x18005c22b  mov     rdx, rax
0x18005c22e  lea     rcx, [rsp+308h+var_C8]
0x18005c236  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18005c23b  nop
0x18005c23c  lea     rcx, [rsp+308h+var_C8]
0x18005c244  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005c249  mov     rdx, rax
0x18005c24c  mov     r8, [rsp+308h+var_B8]
0x18005c254  lea     rcx, [rsp+308h+var_108]
0x18005c25c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005c261  nop
  ... truncated ...
```
