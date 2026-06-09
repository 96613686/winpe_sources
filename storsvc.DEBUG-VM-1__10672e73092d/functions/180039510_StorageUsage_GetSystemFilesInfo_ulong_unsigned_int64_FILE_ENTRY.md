# StorageUsage::GetSystemFilesInfo(ulong *,unsigned __int64 *,_FILE_ENTRY * *)

- ea: `0x180039510`
- end: `0x180039ab5`
- name: `?GetSystemFilesInfo@StorageUsage@@QEAAJPEAKPEA_KPEAPEAU_FILE_ENTRY@@@Z`
- size: `1445`
- prototype: `__int64 __fastcall(StorageUsage *__hidden this, unsigned int *, unsigned __int64 *, struct _FILE_ENTRY **)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180037740`

## callees

- `0x18000d030`
- `0x180012714`
- `0x180018fb8`
- `0x180019bc4`
- `0x180019d4c`
- `0x18001a508`
- `0x18001c130`
- `0x18001c208`
- `0x18001f678`
- `0x180037b40`
- `0x180037c08`
- `0x180037d68`
- `0x180037f8c`
- `0x1800384a8`
- `0x18003934c`
- `0x180039510`
- `0x180039bb8`
- `0x180039ec8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039906`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039906`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003957e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003957e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003961b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003961b`

## string_xrefs

- `0x180039a6b`: `onecore\drivers\storage\storsvc\service\storageusageclient.cpp`
- `0x18003972a`: `Failed GetFilePath`
- `0x1800397f8`: `Failed GetFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StorageUsage::GetSystemFilesInfo(
        StorageUsage *this,
        unsigned int *a2,
        unsigned __int64 *a3,
        struct _FILE_ENTRY **a4)
{
  int StorageDebugInfo; // r15d
  unsigned int v7; // ebx
  unsigned int v8; // esi
  char *v9; // rdi
  __int64 v10; // rcx
  const char *v11; // r9
  unsigned int v12; // r13d
  __int64 *v13; // rdi
  HLOCAL v14; // r12
  void *v15; // r14
  int v16; // ebx
  __int64 v17; // rsi
  __int64 v18; // r10
  __int64 v19; // rax
  __int64 v20; // rcx
  const wchar_t *v21; // r8
  __int64 *v22; // rbx
  char *v23; // rdi
  int v24; // esi
  __int64 v25; // r14
  HLOCAL v26; // r15
  void *v27; // r12
  __int64 v28; // rcx
  const wchar_t *v29; // r8
  __int64 **v30; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 **v33; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  struct _FILE_ENTRY *v36; // r8
  unsigned int v37; // r10d
  __int64 v38; // r9
  __int64 v39; // rdx
  unsigned int LastError; // ebx
  int FilePath; // [rsp+40h] [rbp-C0h]
  unsigned int v42[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h]
  char *FileW; // [rsp+68h] [rbp-98h] BYREF
  __int128 v46; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v47; // [rsp+80h] [rbp-80h] BYREF
  void *v48; // [rsp+88h] [rbp-78h]
  _OWORD v49[2]; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL hMem[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v51; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v52[2]; // [rsp+D0h] [rbp-30h]
  unsigned __int64 *v53; // [rsp+F0h] [rbp-10h]
  unsigned int *v54; // [rsp+F8h] [rbp-8h]
  struct _FILE_ENTRY **v55; // [rsp+100h] [rbp+0h]
  __int64 v56; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v57[28]; // [rsp+110h] [rbp+10h] BYREF
  int v58; // [rsp+12Ch] [rbp+2Ch]
  _BYTE v59[32]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v55 = a4;
  v53 = a3;
  v54 = a2;
  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  v42[0] = 0;
  hMem[0] = 0;
  StorageDebugInfo = StorageUsage::GetStorageDebugInfo(this, v42, (struct _MAP_DBG_ENTRY **)hMem);
  FilePath = StorageDebugInfo;
  if ( StorageDebugInfo >= 0 )
  {
    v46 = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,__int64,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,__int64>>,0>>::_Alloc_sentinel_and_proxy(&v46);
    v7 = 0;
    v8 = v42[0];
    if ( v42[0] )
    {
      v9 = (char *)hMem[0];
      do
      {
        v10 = 28LL * v7;
        if ( *(_DWORD *)&v9[v10 + 16] == 1 )
        {
          v56 = *(_QWORD *)&v9[v10];
          *(_OWORD *)v57 = *(_OWORD *)&v9[v10];
          *(_OWORD *)&v57[12] = *(_OWORD *)&v9[v10 + 12];
          std::_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>::_Emplace<std::pair<__int64,_MAP_DBG_ENTRY>>(
            &v46,
            hMem,
            &v56);
        }
        ++v7;
      }
      while ( v7 < v8 );
    }
    FileW = (char *)CreateFileW((LPCWSTR)(*((_QWORD *)this + 3) + 328LL), 0x100u, 3u, 0, 3u, 0x2000080u, 0);
    if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x305,
                    (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storageusageclient.cpp",
                    v11);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
      std::_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>::~_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>(&v46);
      return LastError;
    }
    else
    {
      std::vector<unsigned __int64>::vector<unsigned __int64>(&v43);
      v12 = 0;
      std::wstring::wstring(v59);
      v13 = *(__int64 **)v46;
      *(_QWORD *)v42 = *(_QWORD *)v46;
      while ( !*((_BYTE *)v13 + 25) )
      {
        v56 = v13[4];
        v14 = (HLOCAL)v13[5];
        hMem[0] = v14;
        *(_QWORD *)v57 = v14;
        v15 = (void *)v13[6];
        *(_QWORD *)&v57[8] = v15;
        v16 = *((_DWORD *)v13 + 14);
        *(_DWORD *)&v57[16] = v16;
        v17 = *(__int64 *)((char *)v13 + 60);
        *(_QWORD *)&v57[20] = v17;
        v58 = *((_DWORD *)v13 + 17);
        if ( v17 )
        {
          std::_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>::_Find_lower_bound<__int64>(
            &v46,
            &v47,
            &v57[8]);
          v19 = *(_QWORD *)&v49[0];
          if ( *(_BYTE *)(*(_QWORD *)&v49[0] + 25LL) || (__int64)v15 < *(_QWORD *)(*(_QWORD *)&v49[0] + 32LL) )
            v19 = v46;
          if ( v19 == (_QWORD)v46 )
          {
            *v53 += v17;
            ++v12;
            memset(v49, 0, 28);
            v51 = 0;
            v52[0] = v49[0];
            *(_OWORD *)((char *)v52 + 12) = 0;
            FilePath = GetFilePath(v18, v14, v59);
            v47 = v14;
            v48 = v15;
            LODWORD(v49[0]) = v16;
            *(_QWORD *)((char *)v49 + 4) = v17;
            if ( FilePath < 0 )
              v21 = L"Failed GetFilePath";
            else
              v21 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
            StorageUsage::PopulateFileEntry(v20, &v47, v21, 1, &v51);
            if ( *((_QWORD *)&v43 + 1) == v44 )
              std::vector<_FILE_ENTRY>::_Emplace_reallocate<_FILE_ENTRY const &>(&v43, *((_QWORD *)&v43 + 1), &v51);
            else
              std::vector<_FILE_ENTRY>::_Emplace_back_with_unused_capacity<_FILE_ENTRY const &>(&v43, &v51);
            v22 = *(__int64 **)v46;
            v23 = FileW;
            while ( !*((_BYTE *)v22 + 25) )
            {
              v24 = *((_DWORD *)v22 + 14);
              v25 = *(__int64 *)((char *)v22 + 60);
              if ( v25 )
              {
                v26 = (HLOCAL)v22[6];
                if ( v26 == v14 )
                {
                  v27 = (void *)v22[5];
                  ++v12;
                  memset(v49, 0, 28);
                  v51 = 0;
                  v52[0] = v49[0];
                  *(_OWORD *)((char *)v52 + 12) = 0;
                  FilePath = GetFilePath(v23, v27, v59);
                  v47 = v27;
                  v48 = v26;
                  LODWORD(v49[0]) = v24;
                  *(_QWORD *)((char *)v49 + 4) = v25;
                  if ( FilePath < 0 )
                    v29 = L"Failed GetFilePath";
                  else
                    v29 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
                  StorageUsage::PopulateFileEntry(v28, &v47, v29, 2, &v51);
                  if ( *((_QWORD *)&v43 + 1) == v44 )
                    std::vector<_FILE_ENTRY>::_Emplace_reallocate<_FILE_ENTRY const &>(
                      &v43,
                      *((_QWORD *)&v43 + 1),
                      &v51);
                  else
                    std::vector<_FILE_ENTRY>::_Emplace_back_with_unused_capacity<_FILE_ENTRY const &>(&v43, &v51);
                  v14 = hMem[0];
                }
              }
              v30 = (__int64 **)v22[2];
              if ( *((_BYTE *)v30 + 25) )
              {
                for ( i = (__int64 *)v22[1]; !*((_BYTE *)i + 25) && v22 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                  v22 = i;
                v22 = i;
              }
              else
              {
                v22 = (__int64 *)v22[2];
                for ( j = *v30; !*((_BYTE *)j + 25); j = (__int64 *)*j )
                  v22 = j;
              }
            }
            v13 = *(__int64 **)v42;
          }
        }
        v33 = (__int64 **)v13[2];
        if ( *((_BYTE *)v33 + 25) )
        {
          for ( k = (__int64 *)v13[1]; !*((_BYTE *)k + 25) && v13 == (__int64 *)k[2]; k = (__int64 *)k[1] )
            v13 = k;
          v13 = k;
          *(_QWORD *)v42 = k;
        }
        else
        {
          v13 = (__int64 *)v13[2];
          *(_QWORD *)v42 = v33;
          for ( m = *v33; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          {
            v13 = m;
            *(_QWORD *)v42 = m;
          }
        }
      }
      v36 = (struct _FILE_ENTRY *)LocalAlloc(0x40u, 44LL * v12);
      if ( v36 )
      {
        v37 = 0;
        if ( v12 )
        {
          v38 = 0;
          do
          {
            v39 = 44 * v38;
            *(_DWORD *)((char *)v36 + v39) = *(_DWORD *)(44 * v38 + v43);
            *(_QWORD *)((char *)v36 + v39 + 4) = *(_QWORD *)(44 * v38 + v43 + 4);
            *(_QWORD *)((char *)v36 + v39 + 12) = *(_QWORD *)(44 * v38 + v43 + 12);
            *(_QWORD *)((char *)v36 + v39 + 20) = *(_QWORD *)(44 * v38 + v43 + 20);
            *(_DWORD *)((char *)v36 + v39 + 28) = *(_DWORD *)(44 * v38 + v43 + 28);
            *(_QWORD *)((char *)v36 + v39 + 32) = *(_QWORD *)(44 * v38 + v43 + 32);
            *(_DWORD *)((char *)v36 + v39 + 40) = *(_DWORD *)(44 * v38 + v43 + 40);
            ++v37;
            ++v38;
          }
          while ( v37 < v12 );
        }
        *v54 = v12;
        *v55 = v36;
        std::wstring::_Tidy_deallocate(v59);
        if ( (_QWORD)v43 )
        {
          std::_Deallocate<16>(v43, 4 * ((v44 - (__int64)v43) >> 2));
          v43 = 0;
          v44 = 0;
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
        std::_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>::~_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>(&v46);
        return (unsigned int)FilePath;
      }
      else
      {
        std::wstring::_Tidy_deallocate(v59);
        if ( (_QWORD)v43 )
        {
          std::_Deallocate<16>(v43, 4 * ((v44 - (__int64)v43) >> 2));
          v43 = 0;
          v44 = 0;
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
        std::_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>::~_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>(&v46);
        return 2147942414LL;
      }
    }
  }
  else
  {
    LocalFree(hMem[0]);
    return (unsigned int)StorageDebugInfo;
  }
}

```

## disassembly

```asm
0x180039510  push    rbp
0x180039512  push    rbx
0x180039513  push    rsi
0x180039514  push    rdi
0x180039515  push    r12
0x180039517  push    r13
0x180039519  push    r14
0x18003951b  push    r15
0x18003951d  lea     rbp, [rsp-68h]
0x180039522  sub     rsp, 168h
0x180039529  mov     rax, cs:__security_cookie
0x180039530  xor     rax, rsp
0x180039533  mov     [rbp+0A0h+var_50], rax
0x180039537  mov     [rbp+0A0h+var_A0], r9
0x18003953b  mov     [rbp+0A0h+var_B0], r8
0x18003953f  mov     [rbp+0A0h+var_A8], rdx
0x180039543  mov     r14, rcx
0x180039546  xor     ebx, ebx
0x180039548  test    rdx, rdx
0x18003954b  jnz     short loc_180039557
0x18003954d  mov     eax, 80070057h
0x180039552  jmp     loc_180039A95
0x180039557  mov     [rdx], ebx
0x180039559  mov     [rsp+1A0h+var_158], ebx
0x18003955d  mov     [rbp+0A0h+hMem], rbx
0x180039561  lea     r8, [rbp+0A0h+hMem]; struct _MAP_DBG_ENTRY **
0x180039565  lea     rdx, [rsp+1A0h+var_158]; unsigned int *
0x18003956a  call    ?GetStorageDebugInfo@StorageUsage@@QEAAJPEAKPEAPEAU_MAP_DBG_ENTRY@@@Z; StorageUsage::GetStorageDebugInfo(ulong *,_MAP_DBG_ENTRY * *)
0x18003956f  mov     r15d, eax
0x180039572  mov     [rsp+1A0h+var_160], eax
0x180039576  test    eax, eax
0x180039578  jns     short loc_18003958C
0x18003957a  mov     rcx, [rbp+0A0h+hMem]; hMem
0x18003957e  call    cs:__imp_LocalFree
0x180039584  mov     eax, r15d
0x180039587  jmp     loc_180039A95
0x18003958c  xorps   xmm0, xmm0
0x18003958f  movdqu  [rsp+1A0h+var_130], xmm0
0x180039595  lea     rcx, [rsp+1A0h+var_130]
0x18003959a  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_JUStringComparatorIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_J@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,__int64,StringComparatorIgnoreCase,std::allocator<std::pair<std::wstring const,__int64>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18003959f  nop
0x1800395a0  xor     r15d, r15d
0x1800395a3  mov     ebx, r15d
0x1800395a6  mov     esi, [rsp+1A0h+var_158]
0x1800395aa  test    esi, esi
0x1800395ac  jz      short loc_1800395F0
0x1800395ae  mov     rdi, [rbp+0A0h+hMem]
0x1800395b2  mov     eax, ebx
0x1800395b4  imul    rcx, rax, 1Ch
0x1800395b8  cmp     dword ptr [rcx+rdi+10h], 1
0x1800395bd  jnz     short loc_1800395EA
0x1800395bf  mov     rax, [rcx+rdi]
0x1800395c3  mov     [rbp+0A0h+var_98], rax
0x1800395c7  movups  xmm0, xmmword ptr [rcx+rdi]
0x1800395cb  movups  [rbp+0A0h+var_90], xmm0
0x1800395cf  movups  xmm1, xmmword ptr [rcx+rdi+0Ch]
0x1800395d4  movups  [rbp+0A0h+var_90+0Ch], xmm1
0x1800395d8  lea     r8, [rbp+0A0h+var_98]
0x1800395dc  lea     rdx, [rbp+0A0h+hMem]
0x1800395e0  lea     rcx, [rsp+1A0h+var_130]
0x1800395e5  call    ??$_Emplace@U?$pair@_JU_MAP_DBG_ENTRY@@@std@@@?$_Tree@V?$_Tmap_traits@_JU_MAP_DBG_ENTRY@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JU_MAP_DBG_ENTRY@@@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JU_MAP_DBG_ENTRY@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@_JU_MAP_DBG_ENTRY@@@1@@Z; std::_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>::_Emplace<std::pair<__int64,_MAP_DBG_ENTRY>>(std::pair<__int64,_MAP_DBG_ENTRY> &&)
0x1800395ea  inc     ebx
0x1800395ec  cmp     ebx, esi
0x1800395ee  jb      short loc_1800395B2
0x1800395f0  mov     rcx, [r14+18h]
0x1800395f4  add     rcx, 148h; lpFileName
0x1800395fb  mov     [rsp+1A0h+hTemplateFile], r15; hTemplateFile
0x180039600  mov     [rsp+1A0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180039608  mov     r8d, 3; dwShareMode
0x18003960e  mov     [rsp+1A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180039613  xor     r9d, r9d; lpSecurityAttributes
0x180039616  mov     edx, 100h; dwDesiredAccess
0x18003961b  call    cs:__imp_CreateFileW
0x180039621  mov     r10, rax
0x180039624  mov     [rsp+1A0h+var_138], rax
0x180039629  lea     rcx, [rax-1]
0x18003962d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180039631  ja      loc_180039A64
0x180039637  lea     rcx, [rsp+1A0h+var_150]
0x18003963c  call    ??0?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::vector<unsigned __int64>(void)
0x180039641  nop
0x180039642  mov     r13d, r15d
0x180039645  lea     rcx, [rbp+0A0h+var_70]
0x180039649  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003964e  nop
0x18003964f  mov     rdi, qword ptr [rsp+1A0h+var_130]
0x180039654  mov     rdi, [rdi]
0x180039657  mov     qword ptr [rsp+1A0h+var_158], rdi
0x18003965c  cmp     [rdi+19h], r15b
0x180039660  jnz     loc_1800398FA
0x180039666  mov     rax, [rdi+20h]
0x18003966a  mov     [rbp+0A0h+var_98], rax
0x18003966e  mov     r12, [rdi+28h]
0x180039672  mov     [rbp+0A0h+hMem], r12
0x180039676  mov     qword ptr [rbp+0A0h+var_90], r12
0x18003967a  mov     r14, [rdi+30h]
0x18003967e  mov     qword ptr [rbp+0A0h+var_90+8], r14
0x180039682  mov     ebx, [rdi+38h]
0x180039685  mov     [rbp+0A0h+var_80], ebx
0x180039688  mov     rsi, [rdi+3Ch]
0x18003968c  mov     [rbp+0A0h+var_7C], rsi
0x180039690  mov     eax, [rdi+44h]
0x180039693  mov     [rbp+0A0h+var_74], eax
0x180039696  test    rsi, rsi
0x180039699  jz      loc_18003989C
0x18003969f  lea     r8, [rbp+0A0h+var_90+8]
0x1800396a3  lea     rdx, [rbp+0A0h+var_120]
0x1800396a7  lea     rcx, [rsp+1A0h+var_130]
0x1800396ac  call    ??$_Find_lower_bound@_J@?$_Tree@V?$_Tmap_traits@_JU_MAP_DBG_ENTRY@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JU_MAP_DBG_ENTRY@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_JU_MAP_DBG_ENTRY@@@std@@PEAX@std@@@1@AEB_J@Z; std::_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>::_Find_lower_bound<__int64>(__int64 const &)
0x1800396b1  mov     rax, qword ptr [rbp+0A0h+var_110]
0x1800396b5  cmp     [rax+19h], r15b
0x1800396b9  jnz     short loc_1800396C1
0x1800396bb  cmp     r14, [rax+20h]
0x1800396bf  jge     short loc_1800396C6
0x1800396c1  mov     rax, qword ptr [rsp+1A0h+var_130]
0x1800396c6  cmp     rax, qword ptr [rsp+1A0h+var_130]
0x1800396cb  jnz     loc_18003989C
0x1800396d1  mov     rax, [rbp+0A0h+var_B0]
0x1800396d5  add     [rax], rsi
0x1800396d8  inc     r13d
0x1800396db  xorps   xmm1, xmm1
0x1800396de  movups  xmmword ptr [rbp+0A0h+var_110], xmm1
0x1800396e2  movups  xmmword ptr [rbp+0A0h+var_110+0Ch], xmm1
0x1800396e6  movups  [rbp+0A0h+var_E0], xmm1
0x1800396ea  movups  xmm0, xmmword ptr [rbp+0A0h+var_110]
0x1800396ee  movups  xmmword ptr [rbp+0A0h+var_D0], xmm0
0x1800396f2  movups  xmmword ptr [rbp+0A0h+var_D0+0Ch], xmm1
0x1800396f6  lea     r8, [rbp+0A0h+var_70]
0x1800396fa  mov     rdx, r12
0x1800396fd  mov     rcx, r10
0x180039700  call    ?GetFilePath@@YAJPEAX_JAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetFilePath(void *,__int64,std::wstring &)
0x180039705  mov     [rsp+1A0h+var_160], eax
0x180039709  mov     [rbp+0A0h+var_120], r12
0x18003970d  mov     [rbp+0A0h+var_118], r14
0x180039711  mov     dword ptr [rbp+0A0h+var_110], ebx
0x180039714  mov     qword ptr [rbp+0A0h+var_110+4], rsi
0x180039718  test    eax, eax
0x18003971a  js      short loc_18003972A
0x18003971c  lea     rcx, [rbp+0A0h+var_70]
0x180039720  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039725  mov     r8, rax
0x180039728  jmp     short loc_180039731
0x18003972a  lea     r8, aFailedGetfilep; "Failed GetFilePath"
0x180039731  lea     rax, [rbp+0A0h+var_E0]
0x180039735  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax
0x18003973a  mov     r9d, 1
0x180039740  lea     rdx, [rbp+0A0h+var_120]
0x180039744  call    ?PopulateFileEntry@StorageUsage@@AEAAXU_MAP_DBG_ENTRY@@PEBGIPEAU_FILE_ENTRY@@@Z; StorageUsage::PopulateFileEntry(_MAP_DBG_ENTRY,ushort const *,uint,_FILE_ENTRY *)
0x180039749  mov     rdx, qword ptr [rsp+1A0h+var_150+8]
0x18003974e  lea     rcx, [rsp+1A0h+var_150]
0x180039753  cmp     rdx, [rsp+1A0h+var_140]
0x180039758  jz      short loc_180039765
0x18003975a  lea     rdx, [rbp+0A0h+var_E0]
0x18003975e  call    ??$_Emplace_back_with_unused_capacity@AEBU_FILE_ENTRY@@@?$vector@U_FILE_ENTRY@@V?$allocator@U_FILE_ENTRY@@@std@@@std@@AEAAAEAU_FILE_ENTRY@@AEBU2@@Z; std::vector<_FILE_ENTRY>::_Emplace_back_with_unused_capacity<_FILE_ENTRY const &>(_FILE_ENTRY const &)
0x180039763  jmp     short loc_18003976E
0x180039765  lea     r8, [rbp+0A0h+var_E0]
0x180039769  call    ??$_Emplace_reallocate@AEBU_FILE_ENTRY@@@?$vector@U_FILE_ENTRY@@V?$allocator@U_FILE_ENTRY@@@std@@@std@@AEAAPEAU_FILE_ENTRY@@QEAU2@AEBU2@@Z; std::vector<_FILE_ENTRY>::_Emplace_reallocate<_FILE_ENTRY const &>(_FILE_ENTRY * const,_FILE_ENTRY const &)
0x18003976e  mov     rbx, qword ptr [rsp+1A0h+var_130]
0x180039773  mov     rbx, [rbx]
0x180039776  mov     rdi, [rsp+1A0h+var_138]
0x18003977b  cmp     [rbx+19h], r15b
0x18003977f  jnz     loc_180039892
0x180039785  mov     esi, [rbx+38h]
0x180039788  mov     r14, [rbx+3Ch]
0x18003978c  test    r14, r14
0x18003978f  jz      loc_180039843
0x180039795  mov     r15, [rbx+30h]
0x180039799  cmp     r15, r12
0x18003979c  jnz     loc_180039840
0x1800397a2  mov     r12, [rbx+28h]
0x1800397a6  inc     r13d
0x1800397a9  xorps   xmm1, xmm1
0x1800397ac  movups  xmmword ptr [rbp+0A0h+var_110], xmm1
0x1800397b0  movups  xmmword ptr [rbp+0A0h+var_110+0Ch], xmm1
0x1800397b4  movups  [rbp+0A0h+var_E0], xmm1
0x1800397b8  movups  xmm0, xmmword ptr [rbp+0A0h+var_110]
0x1800397bc  movups  xmmword ptr [rbp+0A0h+var_D0], xmm0
0x1800397c0  movups  xmmword ptr [rbp+0A0h+var_D0+0Ch], xmm1
0x1800397c4  lea     r8, [rbp+0A0h+var_70]
0x1800397c8  mov     rdx, r12
0x1800397cb  mov     rcx, rdi
0x1800397ce  call    ?GetFilePath@@YAJPEAX_JAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetFilePath(void *,__int64,std::wstring &)
0x1800397d3  mov     [rsp+1A0h+var_160], eax
0x1800397d7  mov     [rbp+0A0h+var_120], r12
0x1800397db  mov     [rbp+0A0h+var_118], r15
0x1800397df  mov     dword ptr [rbp+0A0h+var_110], esi
0x1800397e2  mov     qword ptr [rbp+0A0h+var_110+4], r14
0x1800397e6  test    eax, eax
0x1800397e8  js      short loc_1800397F8
0x1800397ea  lea     rcx, [rbp+0A0h+var_70]
0x1800397ee  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800397f3  mov     r8, rax
0x1800397f6  jmp     short loc_1800397FF
0x1800397f8  lea     r8, aFailedGetfilep; "Failed GetFilePath"
0x1800397ff  lea     rax, [rbp+0A0h+var_E0]
0x180039803  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax
0x180039808  mov     r9d, 2
0x18003980e  lea     rdx, [rbp+0A0h+var_120]
0x180039812  call    ?PopulateFileEntry@StorageUsage@@AEAAXU_MAP_DBG_ENTRY@@PEBGIPEAU_FILE_ENTRY@@@Z; StorageUsage::PopulateFileEntry(_MAP_DBG_ENTRY,ushort const *,uint,_FILE_ENTRY *)
0x180039817  mov     rdx, qword ptr [rsp+1A0h+var_150+8]
0x18003981c  lea     rcx, [rsp+1A0h+var_150]
0x180039821  cmp     rdx, [rsp+1A0h+var_140]
0x180039826  jz      short loc_180039833
0x180039828  lea     rdx, [rbp+0A0h+var_E0]
0x18003982c  call    ??$_Emplace_back_with_unused_capacity@AEBU_FILE_ENTRY@@@?$vector@U_FILE_ENTRY@@V?$allocator@U_FILE_ENTRY@@@std@@@std@@AEAAAEAU_FILE_ENTRY@@AEBU2@@Z; std::vector<_FILE_ENTRY>::_Emplace_back_with_unused_capacity<_FILE_ENTRY const &>(_FILE_ENTRY const &)
0x180039831  jmp     short loc_18003983C
0x180039833  lea     r8, [rbp+0A0h+var_E0]
0x180039837  call    ??$_Emplace_reallocate@AEBU_FILE_ENTRY@@@?$vector@U_FILE_ENTRY@@V?$allocator@U_FILE_ENTRY@@@std@@@std@@AEAAPEAU_FILE_ENTRY@@QEAU2@AEBU2@@Z; std::vector<_FILE_ENTRY>::_Emplace_reallocate<_FILE_ENTRY const &>(_FILE_ENTRY * const,_FILE_ENTRY const &)
0x18003983c  mov     r12, [rbp+0A0h+hMem]
0x180039840  xor     r15d, r15d
0x180039843  mov     rcx, [rbx+10h]
0x180039847  cmp     [rcx+19h], r15b
0x18003984b  jz      short loc_18003986E
0x18003984d  mov     rax, [rbx+8]
0x180039851  jmp     short loc_180039860
0x180039853  cmp     rbx, [rax+10h]
0x180039857  jnz     short loc_180039866
0x180039859  mov     rbx, rax
0x18003985c  mov     rax, [rax+8]
0x180039860  cmp     [rax+19h], r15b
0x180039864  jz      short loc_180039853
0x180039866  mov     rbx, rax
0x180039869  jmp     loc_18003977B
0x18003986e  mov     rbx, rcx
0x180039871  mov     rcx, [rcx]
0x180039874  cmp     [rcx+19h], r15b
0x180039878  jnz     loc_18003977B
0x18003987e  mov     rbx, rcx
0x180039881  mov     rax, [rcx]
0x180039884  mov     rcx, rax
0x180039887  cmp     [rax+19h], r15b
0x18003988b  jz      short loc_18003987E
0x18003988d  jmp     loc_18003977B
0x180039892  mov     rdi, qword ptr [rsp+1A0h+var_158]
0x180039897  mov     r10, [rsp+1A0h+var_138]
0x18003989c  mov     rcx, [rdi+10h]
0x1800398a0  cmp     [rcx+19h], r15b
0x1800398a4  jz      short loc_1800398CC
0x1800398a6  mov     rax, [rdi+8]
0x1800398aa  jmp     short loc_1800398B9
0x1800398ac  cmp     rdi, [rax+10h]
0x1800398b0  jnz     short loc_1800398BF
0x1800398b2  mov     rdi, rax
0x1800398b5  mov     rax, [rax+8]
0x1800398b9  cmp     [rax+19h], r15b
0x1800398bd  jz      short loc_1800398AC
0x1800398bf  mov     rdi, rax
0x1800398c2  mov     qword ptr [rsp+1A0h+var_158], rax
0x1800398c7  jmp     loc_18003965C
0x1800398cc  mov     rdi, rcx
0x1800398cf  mov     qword ptr [rsp+1A0h+var_158], rcx
0x1800398d4  mov     rcx, [rcx]
0x1800398d7  cmp     [rcx+19h], r15b
0x1800398db  jnz     loc_18003965C
0x1800398e1  mov     rdi, rcx
0x1800398e4  mov     qword ptr [rsp+1A0h+var_158], rcx
0x1800398e9  mov     rax, [rcx]
0x1800398ec  mov     rcx, rax
0x1800398ef  cmp     [rax+19h], r15b
0x1800398f3  jz      short loc_1800398E1
0x1800398f5  jmp     loc_18003965C
0x1800398fa  mov     eax, r13d
0x1800398fd  imul    rdx, rax, 2Ch ; ','; uBytes
0x180039901  mov     ecx, 40h ; '@'; uFlags
0x180039906  call    cs:__imp_LocalAlloc
0x18003990c  mov     r8, rax
0x18003990f  test    rax, rax
0x180039912  jnz     short loc_180039978
0x180039914  lea     rcx, [rbp+0A0h+var_70]
0x180039918  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003991d  nop
0x18003991e  mov     rcx, qword ptr [rsp+1A0h+var_150]
0x180039923  test    rcx, rcx
0x180039926  jz      short loc_180039959
0x180039928  mov     rax, [rsp+1A0h+var_140]
0x18003992d  sub     rax, rcx
0x180039930  sar     rax, 2
0x180039934  mov     rdx, 2E8BA2E8BA2E8BA3h
0x18003993e  imul    rax, rdx
0x180039942  imul    rdx, rax, 2Ch ; ','
0x180039946  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003994b  xorps   xmm0, xmm0
0x18003994e  movdqu  [rsp+1A0h+var_150], xmm0
0x180039954  mov     [rsp+1A0h+var_140], r15
0x180039959  lea     rcx, [rsp+1A0h+var_138]
0x18003995e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180039963  nop
0x180039964  lea     rcx, [rsp+1A0h+var_130]
0x180039969  call    ??1?$_Tree@V?$_Tmap_traits@_JU_MAP_DBG_ENTRY@@U?$less@_J@std@@V?$allocator@U?$pair@$$CB_JU_MAP_DBG_ENTRY@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>::~_Tree<std::_Tmap_traits<__int64,_MAP_DBG_ENTRY,std::less<__int64>,std::allocator<std::pair<__int64 const,_MAP_DBG_ENTRY>>,0>>(void)
0x18003996e  mov     eax, 8007000Eh
0x180039973  jmp     loc_180039A95
0x180039978  mov     r10d, r15d
0x18003997b  test    r13d, r13d
0x18003997e  jz      short loc_1800399F6
0x180039980  mov     r9, r15
0x180039983  imul    rdx, r9, 2Ch ; ','
0x180039987  mov     rax, qword ptr [rsp+1A0h+var_150]
0x18003998c  mov     ecx, [rdx+rax]
0x18003998f  mov     [r8+rdx], ecx
0x180039993  mov     rax, qword ptr [rsp+1A0h+var_150]
  ... truncated ...
```
