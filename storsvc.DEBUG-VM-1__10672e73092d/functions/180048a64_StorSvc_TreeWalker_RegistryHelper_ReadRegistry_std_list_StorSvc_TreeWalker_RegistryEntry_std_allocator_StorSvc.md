# StorSvc::TreeWalker::RegistryHelper::ReadRegistry(std::list<StorSvc::TreeWalker::RegistryEntry,std::allocator<StorSvc::TreeWalker::RegistryEntry>> &,StorSvc::TreeWalker::MediaClass,bool,bool)

- ea: `0x180048a64`
- end: `0x180048f42`
- name: `?ReadRegistry@RegistryHelper@TreeWalker@StorSvc@@CAJAEAV?$list@URegistryEntry@TreeWalker@StorSvc@@V?$allocator@URegistryEntry@TreeWalker@StorSvc@@@std@@@std@@W4MediaClass@23@_N2@Z`
- size: `1246`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180049a08`

## callees

- `0x18000d030`
- `0x180018fb8`
- `0x180019cd4`
- `0x180019dd4`
- `0x18001c130`
- `0x18001c208`
- `0x18001f634`
- `0x18002e740`
- `0x18002ebb4`
- `0x18003c1c0`
- `0x18003d054`
- `0x18003d0a8`
- `0x18003fe10`
- `0x18004196c`
- `0x1800419c0`
- `0x180041a14`
- `0x180041fc8`
- `0x18004269c`
- `0x180042844`
- `0x180042d58`
- `0x18004379c`
- `0x180043850`
- `0x180043d30`
- `0x180045b18`
- `0x180048708`
- `0x180048a64`
- `0x18004a924`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180048b28`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180048b28`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180048acd`
- `api-ms-win-core-file-l1-1-0!GetLogicalDrives` at `0x180048acd`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall StorSvc::TreeWalker::RegistryHelper::ReadRegistry(_QWORD *a1, unsigned int a2)
{
  __int64 v4; // rax
  const WCHAR *v5; // rax
  BOOL VolumeNameForVolumeMountPointW; // edi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  char v11; // al
  __int64 v12; // rcx
  _QWORD *v13; // rax
  _WORD *v14; // rax
  DWORD i; // ebx
  __int64 *m; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  _QWORD **v22; // rcx
  _QWORD *k; // rdx
  _QWORD *v24; // rdi
  _QWORD *v25; // rsi
  _QWORD *v26; // rdi
  _QWORD **v27; // rcx
  _QWORD *j; // rdx
  _QWORD *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rax
  unsigned int v34; // r14d
  unsigned int v35; // r8d
  const char *v36; // r9
  __int64 result; // rax
  _QWORD v38[2]; // [rsp+30h] [rbp-408h] BYREF
  _QWORD v39[2]; // [rsp+40h] [rbp-3F8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-3E8h]
  _BYTE v41[16]; // [rsp+58h] [rbp-3E0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-3D0h]
  _BYTE v43[16]; // [rsp+70h] [rbp-3C8h] BYREF
  _BYTE v44[16]; // [rsp+80h] [rbp-3B8h] BYREF
  __int64 v45; // [rsp+90h] [rbp-3A8h]
  _BYTE v46[32]; // [rsp+A8h] [rbp-390h] BYREF
  _BYTE v47[32]; // [rsp+C8h] [rbp-370h] BYREF
  _BYTE v48[32]; // [rsp+E8h] [rbp-350h] BYREF
  _BYTE v49[32]; // [rsp+108h] [rbp-330h] BYREF
  _BYTE v50[32]; // [rsp+128h] [rbp-310h] BYREF
  _BYTE v51[32]; // [rsp+148h] [rbp-2F0h] BYREF
  _BYTE v52[32]; // [rsp+168h] [rbp-2D0h] BYREF
  _BYTE v53[32]; // [rsp+188h] [rbp-2B0h] BYREF
  _BYTE v54[32]; // [rsp+1A8h] [rbp-290h] BYREF
  _BYTE v55[40]; // [rsp+1C8h] [rbp-270h] BYREF
  WCHAR szVolumeName[264]; // [rsp+1F0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+0h]

  try
  {
    v34 = -2147467259;
    std::wstring::wstring(v46, L"A:");
    v38[0] = 0;
    v38[1] = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(v38);
    for ( i = GetLogicalDrives(); i; i >>= 1 )
    {
      if ( (i & 1) != 0 )
      {
        v4 = std::operator+<unsigned short>(v49, v46, L"\\");
        v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
        VolumeNameForVolumeMountPointW = GetVolumeNameForVolumeMountPointW(v5, szVolumeName, 0x104u);
        std::wstring::_Tidy_deallocate(v49);
        if ( VolumeNameForVolumeMountPointW )
        {
          v7 = std::wstring::wstring(v50, szVolumeName);
          std::wstring::substr(v7, v44, 10);
          std::wstring::_Tidy_deallocate(v50);
          --v45;
          v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
          *(_WORD *)(v8 + 2 * v9) = 0;
          std::_Tree<std::_Tmap_traits<std::wstring,StorageHealth::_SignalArchiveData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,StorageHealth::_SignalArchiveData>>,0>>::_Find_lower_bound<std::wstring>(
            v38,
            v41,
            v44);
          v11 = std::_Tree<std::_Tmap_traits<std::wstring,VolumeInfo *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeInfo *>>,0>>::_Lower_bound_duplicate<std::wstring>(
                  v10,
                  v42,
                  v44);
          v12 = v38[0];
          if ( v11 )
            v12 = v42;
          v40 = v38[0];
          if ( v12 == v38[0] )
          {
            v13 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(v38, v43, v44);
            std::wstring::operator=(*v13 + 64LL, v46);
          }
          std::wstring::_Tidy_deallocate(v44);
        }
      }
      v14 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
      ++*v14;
    }
    m = *(__int64 **)v38[0];
    while ( !*((_BYTE *)m + 25) )
    {
      std::list<StorSvc::TreeWalker::RegistryEntry>::list<StorSvc::TreeWalker::RegistryEntry>(v39);
      std::wstring::wstring(v48, m + 4);
      v17 = StorSvc::TreeWalker::RegistryHelper::MediaString(v55, a2);
      v18 = std::operator+<unsigned short>(
              v54,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\StorageSense\\SuggestedFolders\\",
              v17);
      v19 = std::operator+<unsigned short>(v53, v18, L"\\");
      v20 = std::operator+<unsigned short>(v52, v19, L"Rejections");
      v21 = std::operator+<unsigned short>(v51, v20, L"\\");
      std::operator+<unsigned short>(v47, v21, v48);
      std::wstring::_Tidy_deallocate(v51);
      std::wstring::_Tidy_deallocate(v52);
      std::wstring::_Tidy_deallocate(v53);
      std::wstring::_Tidy_deallocate(v54);
      std::wstring::_Tidy_deallocate(v55);
      if ( (int)StorSvc::TreeWalker::RegistryHelper::ReadRegistry(v39, (__int64)v47) >= 0 )
      {
        v25 = (_QWORD *)v39[0];
        v26 = *(_QWORD **)v39[0];
        v40 = v39[0];
        while ( v26 != v25 )
        {
          StorSvc::TreeWalker::RegistryEntry::RegistryEntry(
            (StorSvc::TreeWalker::RegistryEntry *)v44,
            (const struct StorSvc::TreeWalker::RegistryEntry *)(v26 + 2));
          v32 = std::operator+<unsigned short>(v49, v31, m + 8);
          v33 = std::operator+<unsigned short>(v50, v32, v26 + 2);
          std::wstring::operator=(v44, v33);
          std::wstring::_Tidy_deallocate(v50);
          std::wstring::_Tidy_deallocate(v49);
          std::list<StorSvc::TreeWalker::RegistryEntry>::_Emplace<StorSvc::TreeWalker::RegistryEntry const &>(
            a1,
            *a1,
            v44);
          v34 = 0;
          SYNC_ROOT_INFO::~SYNC_ROOT_INFO((SYNC_ROOT_INFO *)v44);
          v26 = (_QWORD *)*v26;
        }
        std::wstring::_Tidy_deallocate(v47);
        std::wstring::_Tidy_deallocate(v48);
        v27 = (_QWORD **)v39[0];
        **(_QWORD **)(v39[0] + 8LL) = 0;
        for ( j = *v27; j; j = v29 )
        {
          v29 = (_QWORD *)*j;
          std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>::_Freenode<std::allocator<std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>>>(
            v27,
            j);
        }
      }
      else
      {
        std::wstring::_Tidy_deallocate(v47);
        std::wstring::_Tidy_deallocate(v48);
        v22 = (_QWORD **)v39[0];
        **(_QWORD **)(v39[0] + 8LL) = 0;
        for ( k = *v22; k; k = v24 )
        {
          v24 = (_QWORD *)*k;
          std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>::_Freenode<std::allocator<std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>>>(
            v22,
            k);
        }
      }
      std::_Deallocate<16>(v39[0], 56);
      if ( *(_BYTE *)(m[2] + 25) )
      {
        while ( 1 )
        {
          v30 = m[1];
          if ( *(_BYTE *)(v30 + 25) || m != *(__int64 **)(v30 + 16) )
            break;
          m = (__int64 *)m[1];
        }
        m = (__int64 *)m[1];
      }
      else
      {
        for ( m = (__int64 *)m[2]; !*(_BYTE *)(*m + 25); m = (__int64 *)*m )
          ;
      }
    }
    std::map<std::wstring,std::wstring>::~map<std::wstring,std::wstring>(v38);
    std::wstring::_Tidy_deallocate(v46);
    result = v34;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x195, v35, v36);
  }
  return result;
}

```

## disassembly

```asm
0x180048a64  mov     [rsp+arg_10], rbx
0x180048a69  mov     [rsp+arg_18], rsi
0x180048a6e  push    rdi
0x180048a6f  push    r12
0x180048a71  push    r13
0x180048a73  push    r14
0x180048a75  push    r15
0x180048a77  sub     rsp, 410h
0x180048a7e  mov     rax, cs:__security_cookie
0x180048a85  xor     rax, rsp
0x180048a88  mov     [rsp+438h+var_38], rax
0x180048a90  mov     r12d, edx
0x180048a93  mov     r15, rcx
0x180048a96  mov     r14d, 80004005h
0x180048a9c  mov     [rsp+438h+var_40C], r14d
0x180048aa1  lea     rdx, aA_0; "A:"
0x180048aa8  lea     rcx, [rsp+438h+var_390]
0x180048ab0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180048ab5  nop
0x180048ab6  xor     esi, esi
0x180048ab8  mov     [rsp+438h+var_408], rsi
0x180048abd  mov     [rsp+438h+var_400], rsi
0x180048ac2  lea     rcx, [rsp+438h+var_408]
0x180048ac7  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180048acc  nop
0x180048acd  call    cs:__imp_GetLogicalDrives
0x180048ad3  mov     ebx, eax
0x180048ad5  mov     [rsp+438h+var_410], eax
0x180048ad9  lea     r13d, [rsi+1]
0x180048add  test    ebx, ebx
0x180048adf  jz      loc_180048C43
0x180048ae5  mov     eax, ebx
0x180048ae7  and     eax, r13d
0x180048aea  test    al, al
0x180048aec  jz      loc_180048C27
0x180048af2  lea     r8, asc_180092790; "\\"
0x180048af9  lea     rdx, [rsp+438h+var_390]
0x180048b01  lea     rcx, [rsp+438h+var_330]
0x180048b09  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180048b0e  nop
0x180048b0f  mov     rcx, rax
0x180048b12  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048b17  mov     r8d, 104h; cchBufferLength
0x180048b1d  lea     rdx, [rsp+438h+szVolumeName]; lpszVolumeName
0x180048b25  mov     rcx, rax; lpszVolumeMountPoint
0x180048b28  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180048b2e  mov     edi, eax
0x180048b30  lea     rcx, [rsp+438h+var_330]
0x180048b38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048b3d  test    edi, edi
0x180048b3f  jz      loc_180048C27
0x180048b45  lea     rdx, [rsp+438h+szVolumeName]
0x180048b4d  lea     rcx, [rsp+438h+var_310]
0x180048b55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180048b5a  nop
0x180048b5b  or      r9, 0FFFFFFFFFFFFFFFFh
0x180048b5f  lea     r8d, [r9+0Bh]
0x180048b63  lea     rdx, [rsp+438h+var_3B8]
0x180048b6b  mov     rcx, rax
0x180048b6e  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180048b73  nop
0x180048b74  lea     rcx, [rsp+438h+var_310]
0x180048b7c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048b81  mov     r8, [rsp+438h+var_3A8]
0x180048b89  dec     r8
0x180048b8c  mov     [rsp+438h+var_3A8], r8
0x180048b94  lea     rcx, [rsp+438h+var_3B8]
0x180048b9c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048ba1  mov     [rax+r8*2], si
0x180048ba6  lea     r8, [rsp+438h+var_3B8]
0x180048bae  lea     rdx, [rsp+438h+var_3E0]
0x180048bb3  lea     rcx, [rsp+438h+var_408]
0x180048bb8  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SignalArchiveData@StorageHealth@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SignalArchiveData@StorageHealth@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_SignalArchiveData@StorageHealth@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,StorageHealth::_SignalArchiveData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,StorageHealth::_SignalArchiveData>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180048bbd  lea     r8, [rsp+438h+var_3B8]
0x180048bc5  mov     rdx, [rsp+438h+var_3D0]
0x180048bca  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVVolumeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVVolumeInfo@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVVolumeInfo@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,VolumeInfo *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeInfo *>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,VolumeInfo *>,void *> * const,std::wstring const &)
0x180048bcf  mov     rdx, [rsp+438h+var_408]
0x180048bd4  mov     rcx, rdx
0x180048bd7  test    al, al
0x180048bd9  cmovnz  rcx, [rsp+438h+var_3D0]
0x180048bdf  mov     [rsp+438h+var_418], rcx
0x180048be4  mov     [rsp+438h+var_3E8], rdx
0x180048be9  cmp     rcx, rdx
0x180048bec  jnz     short loc_180048C1A
0x180048bee  lea     r8, [rsp+438h+var_3B8]
0x180048bf6  lea     rdx, [rsp+438h+var_3C8]
0x180048bfb  lea     rcx, [rsp+438h+var_408]
0x180048c00  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180048c05  mov     rcx, [rax]
0x180048c08  add     rcx, 40h ; '@'
0x180048c0c  lea     rdx, [rsp+438h+var_390]
0x180048c14  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180048c19  nop
0x180048c1a  lea     rcx, [rsp+438h+var_3B8]
0x180048c22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048c27  lea     rcx, [rsp+438h+var_390]
0x180048c2f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180048c34  add     [rax], r13w
0x180048c38  shr     ebx, 1
0x180048c3a  mov     [rsp+438h+var_410], ebx
0x180048c3e  jmp     loc_180048ADD
0x180048c43  mov     rbx, [rsp+438h+var_408]
0x180048c48  mov     rbx, [rbx]
0x180048c4b  mov     [rsp+438h+var_418], rbx
0x180048c50  cmp     [rbx+19h], sil
0x180048c54  jnz     loc_180048EF3
0x180048c5a  lea     rcx, [rsp+438h+var_3F8]
0x180048c5f  call    ??0?$list@URegistryEntry@TreeWalker@StorSvc@@V?$allocator@URegistryEntry@TreeWalker@StorSvc@@@std@@@std@@QEAA@XZ; std::list<StorSvc::TreeWalker::RegistryEntry>::list<StorSvc::TreeWalker::RegistryEntry>(void)
0x180048c64  nop
0x180048c65  lea     rdx, [rbx+20h]
0x180048c69  lea     rcx, [rsp+438h+var_350]
0x180048c71  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180048c76  nop
0x180048c77  mov     edx, r12d
0x180048c7a  lea     rcx, [rsp+438h+var_270]
0x180048c82  call    ?MediaString@RegistryHelper@TreeWalker@StorSvc@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4MediaClass@23@@Z; StorSvc::TreeWalker::RegistryHelper::MediaString(StorSvc::TreeWalker::MediaClass)
0x180048c87  nop
0x180048c88  mov     r8, rax
0x180048c8b  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180048c92  lea     rcx, [rsp+438h+var_290]
0x180048c9a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180048c9f  nop
0x180048ca0  lea     r8, asc_180092790; "\\"
0x180048ca7  mov     rdx, rax
0x180048caa  lea     rcx, [rsp+438h+var_2B0]
0x180048cb2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180048cb7  nop
0x180048cb8  lea     r8, aRejections; "Rejections"
0x180048cbf  mov     rdx, rax
0x180048cc2  lea     rcx, [rsp+438h+var_2D0]
0x180048cca  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180048ccf  nop
0x180048cd0  lea     r8, asc_180092790; "\\"
0x180048cd7  mov     rdx, rax
0x180048cda  lea     rcx, [rsp+438h+var_2F0]
0x180048ce2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180048ce7  nop
0x180048ce8  lea     r8, [rsp+438h+var_350]
0x180048cf0  mov     rdx, rax
0x180048cf3  lea     rcx, [rsp+438h+var_370]
0x180048cfb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180048d00  nop
0x180048d01  lea     rcx, [rsp+438h+var_2F0]
0x180048d09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048d0e  nop
0x180048d0f  lea     rcx, [rsp+438h+var_2D0]
0x180048d17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048d1c  nop
0x180048d1d  lea     rcx, [rsp+438h+var_2B0]
0x180048d25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048d2a  nop
0x180048d2b  lea     rcx, [rsp+438h+var_290]
0x180048d33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048d38  nop
0x180048d39  lea     rcx, [rsp+438h+var_270]
0x180048d41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048d46  lea     rdx, [rsp+438h+var_370]
0x180048d4e  lea     rcx, [rsp+438h+var_3F8]
0x180048d53  call    ?ReadRegistry@RegistryHelper@TreeWalker@StorSvc@@CAJAEAV?$list@URegistryEntry@TreeWalker@StorSvc@@V?$allocator@URegistryEntry@TreeWalker@StorSvc@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@_N@Z; StorSvc::TreeWalker::RegistryHelper::ReadRegistry(std::list<StorSvc::TreeWalker::RegistryEntry> &,std::wstring const &,bool)
0x180048d58  test    eax, eax
0x180048d5a  jns     short loc_180048DAA
0x180048d5c  lea     rcx, [rsp+438h+var_370]
0x180048d64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048d69  nop
0x180048d6a  lea     rcx, [rsp+438h+var_350]
0x180048d72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048d77  nop
0x180048d78  mov     rcx, [rsp+438h+var_3F8]
0x180048d7d  mov     rax, [rcx+8]
0x180048d81  mov     [rax], rsi
0x180048d84  mov     rdx, [rcx]
0x180048d87  test    rdx, rdx
0x180048d8a  jz      short loc_180048D99
0x180048d8c  mov     rdi, [rdx]
0x180048d8f  call    ??$_Freenode@V?$allocator@U?$_List_node@URegistryEntry@TreeWalker@StorSvc@@PEAX@std@@@std@@@?$_List_node@URegistryEntry@TreeWalker@StorSvc@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@URegistryEntry@TreeWalker@StorSvc@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>::_Freenode<std::allocator<std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>>>(std::allocator<std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>> &,std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *> *)
0x180048d94  mov     rdx, rdi
0x180048d97  jmp     short loc_180048D87
0x180048d99  mov     edx, 38h ; '8'
0x180048d9e  mov     rcx, [rsp+438h+var_3F8]
0x180048da3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180048da8  jmp     short loc_180048E13
0x180048daa  mov     rsi, [rsp+438h+var_3F8]
0x180048daf  mov     rdi, [rsi]
0x180048db2  mov     [rsp+438h+var_418], rdi
0x180048db7  mov     [rsp+438h+var_3E8], rsi
0x180048dbc  cmp     rdi, rsi
0x180048dbf  jnz     loc_180048E59
0x180048dc5  lea     rcx, [rsp+438h+var_370]
0x180048dcd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048dd2  nop
0x180048dd3  lea     rcx, [rsp+438h+var_350]
0x180048ddb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048de0  nop
0x180048de1  mov     rcx, [rsp+438h+var_3F8]
0x180048de6  mov     rax, [rcx+8]
0x180048dea  xor     esi, esi
0x180048dec  mov     [rax], rsi
0x180048def  mov     rdx, [rcx]
0x180048df2  test    rdx, rdx
0x180048df5  jz      short loc_180048E04
0x180048df7  mov     rdi, [rdx]
0x180048dfa  call    ??$_Freenode@V?$allocator@U?$_List_node@URegistryEntry@TreeWalker@StorSvc@@PEAX@std@@@std@@@?$_List_node@URegistryEntry@TreeWalker@StorSvc@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@URegistryEntry@TreeWalker@StorSvc@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>::_Freenode<std::allocator<std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>>>(std::allocator<std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *>> &,std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *> *)
0x180048dff  mov     rdx, rdi
0x180048e02  jmp     short loc_180048DF2
0x180048e04  mov     edx, 38h ; '8'
0x180048e09  mov     rcx, [rsp+438h+var_3F8]
0x180048e0e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180048e13  mov     rax, [rbx+10h]
0x180048e17  cmp     [rax+19h], sil
0x180048e1b  jz      short loc_180048E44
0x180048e1d  mov     rax, [rbx+8]
0x180048e21  cmp     [rax+19h], sil
0x180048e25  jnz     short loc_180048E37
0x180048e27  cmp     rbx, [rax+10h]
0x180048e2b  jnz     short loc_180048E37
0x180048e2d  mov     rbx, rax
0x180048e30  mov     [rsp+438h+var_418], rax
0x180048e35  jmp     short loc_180048E1D
0x180048e37  mov     rbx, rax
0x180048e3a  mov     [rsp+438h+var_418], rax
0x180048e3f  jmp     loc_180048C50
0x180048e44  mov     rbx, rax
0x180048e47  mov     rax, [rbx]
0x180048e4a  cmp     [rax+19h], sil
0x180048e4e  jnz     loc_180048C4B
0x180048e54  mov     rbx, rax
0x180048e57  jmp     short loc_180048E47
0x180048e59  lea     rdx, [rdi+10h]; struct StorSvc::TreeWalker::RegistryEntry *
0x180048e5d  lea     rcx, [rsp+438h+var_3B8]; this
0x180048e65  call    ??0RegistryEntry@TreeWalker@StorSvc@@QEAA@AEBU012@@Z; StorSvc::TreeWalker::RegistryEntry::RegistryEntry(StorSvc::TreeWalker::RegistryEntry const &)
0x180048e6a  nop
0x180048e6b  lea     r8, [rbx+40h]
0x180048e6f  lea     rcx, [rsp+438h+var_330]
0x180048e77  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180048e7c  nop
0x180048e7d  lea     r8, [rdi+10h]
0x180048e81  mov     rdx, rax
0x180048e84  lea     rcx, [rsp+438h+var_310]
0x180048e8c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180048e91  nop
0x180048e92  mov     rdx, rax
0x180048e95  lea     rcx, [rsp+438h+var_3B8]
0x180048e9d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180048ea2  nop
0x180048ea3  lea     rcx, [rsp+438h+var_310]
0x180048eab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048eb0  nop
0x180048eb1  lea     rcx, [rsp+438h+var_330]
0x180048eb9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048ebe  lea     r8, [rsp+438h+var_3B8]
0x180048ec6  mov     rdx, [r15]
0x180048ec9  mov     rcx, r15
0x180048ecc  call    ??$_Emplace@AEBURegistryEntry@TreeWalker@StorSvc@@@?$list@URegistryEntry@TreeWalker@StorSvc@@V?$allocator@URegistryEntry@TreeWalker@StorSvc@@@std@@@std@@QEAAPEAU?$_List_node@URegistryEntry@TreeWalker@StorSvc@@PEAX@1@QEAU21@AEBURegistryEntry@TreeWalker@StorSvc@@@Z; std::list<StorSvc::TreeWalker::RegistryEntry>::_Emplace<StorSvc::TreeWalker::RegistryEntry const &>(std::_List_node<StorSvc::TreeWalker::RegistryEntry,void *> * const,StorSvc::TreeWalker::RegistryEntry const &)
0x180048ed1  xor     r14d, r14d
0x180048ed4  mov     [rsp+438h+var_40C], r14d
0x180048ed9  lea     rcx, [rsp+438h+var_3B8]; this
0x180048ee1  call    ??1SYNC_ROOT_INFO@@QEAA@XZ; SYNC_ROOT_INFO::~SYNC_ROOT_INFO(void)
0x180048ee6  mov     rdi, [rdi]
0x180048ee9  mov     [rsp+438h+var_418], rdi
0x180048eee  jmp     loc_180048DBC
0x180048ef3  lea     rcx, [rsp+438h+var_408]
0x180048ef8  call    ??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::~map<std::wstring,std::wstring>(void)
0x180048efd  nop
0x180048efe  lea     rcx, [rsp+438h+var_390]
0x180048f06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048f0b  mov     eax, r14d
0x180048f0e  jmp     short loc_180048F14
0x180048f10  mov     eax, dword ptr [rsp+438h+var_418]
0x180048f14  mov     rcx, [rsp+438h+var_38]
0x180048f1c  xor     rcx, rsp; StackCookie
0x180048f1f  call    __security_check_cookie
0x180048f24  lea     r11, [rsp+438h+var_28]
0x180048f2c  mov     rbx, [r11+40h]
0x180048f30  mov     rsi, [r11+48h]
0x180048f34  mov     rsp, r11
0x180048f37  pop     r15
0x180048f39  pop     r14
0x180048f3b  pop     r13
0x180048f3d  pop     r12
0x180048f3f  pop     rdi
0x180048f40  retn
```
