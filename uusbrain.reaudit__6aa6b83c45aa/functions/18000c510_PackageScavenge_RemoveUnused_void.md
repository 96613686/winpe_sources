# PackageScavenge::RemoveUnused(void)

- ea: `0x18000c510`
- end: `0x18000cdf6`
- name: `?RemoveUnused@PackageScavenge@@SAXXZ`
- size: `2278`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, installer_update`

## callers

- `0x18000d640`

## callees

- `0x1800089f4`
- `0x180008fc4`
- `0x180009e64`
- `0x18000a4c8`
- `0x18000a748`
- `0x18000ae24`
- `0x18000af34`
- `0x18000bc8c`
- `0x18000c510`
- `0x18000cf18`
- `0x18000e7ac`
- `0x18000ecdc`
- `0x18000f39c`
- `0x18000f5a0`
- `0x18000f61c`
- `0x18001044c`
- `0x18001052c`
- `0x180017dd4`
- `0x1800234e4`
- `0x1800240ac`
- `0x180025058`
- `0x1800252e0`
- `0x180026370`
- `0x180028728`
- `0x180028ec4`
- `0x180029644`
- `0x1800427d0`
- `0x180042bfc`
- `0x180047a30`
- `0x180047ab0`
- `0x180047e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb45`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000cb3b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18000cb3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall PackageScavenge::RemoveUnused()
{
  __int64 v0; // rdi
  _QWORD *v1; // rax
  __m128i si128; // xmm6
  __int64 v3; // rax
  __int64 v4; // rax
  int v5; // r14d
  const char *v6; // r9
  unsigned __int64 v7; // r12
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  unsigned __int64 v10; // r15
  __int64 *v11; // rbx
  int v12; // r14d
  void **v13; // r12
  __int64 v14; // r8
  void **v15; // r13
  __int64 v16; // r15
  void **v17; // rax
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  const WCHAR *v20; // rdx
  const WCHAR *v21; // rcx
  DWORD LastError; // eax
  __int64 v23; // rcx
  const struct std::filesystem::path *v24; // rdx
  __int64 **v25; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  unsigned __int64 v28; // rdi
  const wchar_t *v29; // rbx
  const wchar_t *v30; // rcx
  __int64 v31; // kr20_8
  const char *v32; // rsi
  const wchar_t *v33; // rdi
  const wchar_t *v34; // rcx
  int v35; // [rsp+40h] [rbp-3D8h]
  int v36; // [rsp+40h] [rbp-3D8h]
  __int64 *v37; // [rsp+48h] [rbp-3D0h] BYREF
  _OWORD *v38; // [rsp+50h] [rbp-3C8h]
  unsigned __int64 v39; // [rsp+58h] [rbp-3C0h] BYREF
  unsigned __int64 v40; // [rsp+60h] [rbp-3B8h]
  void *Src[2]; // [rsp+68h] [rbp-3B0h] BYREF
  __int64 v42; // [rsp+78h] [rbp-3A0h]
  unsigned __int64 v43; // [rsp+80h] [rbp-398h]
  _OWORD v44[3]; // [rsp+88h] [rbp-390h] BYREF
  _OWORD *v45; // [rsp+C0h] [rbp-358h]
  const std::exception *v46; // [rsp+C8h] [rbp-350h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+D0h] [rbp-348h] BYREF
  __m128i v48; // [rsp+E0h] [rbp-338h]
  unsigned __int64 v49[2]; // [rsp+F0h] [rbp-328h] BYREF
  int v50; // [rsp+100h] [rbp-318h] BYREF
  LPCWSTR lpExistingFileName[8]; // [rsp+110h] [rbp-308h] BYREF
  unsigned __int64 v52[2]; // [rsp+150h] [rbp-2C8h] BYREF
  __int128 v53; // [rsp+160h] [rbp-2B8h] BYREF
  __m128i v54; // [rsp+170h] [rbp-2A8h]
  __int128 v55; // [rsp+180h] [rbp-298h] BYREF
  __m128i v56; // [rsp+190h] [rbp-288h]
  _QWORD v57[4]; // [rsp+1A0h] [rbp-278h] BYREF
  void **v58; // [rsp+1C0h] [rbp-258h] BYREF
  _BYTE v59[32]; // [rsp+1C8h] [rbp-250h] BYREF
  __int64 v60; // [rsp+1E8h] [rbp-230h]
  _QWORD v61[2]; // [rsp+1F0h] [rbp-228h] BYREF
  void (__fastcall **v62)(_QWORD, _QWORD); // [rsp+200h] [rbp-218h] BYREF
  char v63; // [rsp+210h] [rbp-208h]
  _QWORD v64[6]; // [rsp+220h] [rbp-1F8h] BYREF
  _BYTE v65[8]; // [rsp+250h] [rbp-1C8h] BYREF
  __int64 *v66; // [rsp+258h] [rbp-1C0h]
  char v67; // [rsp+278h] [rbp-1A0h]
  __int64 v68; // [rsp+280h] [rbp-198h] BYREF
  _BYTE v69[88]; // [rsp+288h] [rbp-190h] BYREF
  _QWORD v70[32]; // [rsp+2E0h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+0h]

  PackageScavenge::RemovePackagesMarkedForDeletion((__int64 **)v52);
  *(_OWORD *)v49 = 0;
  v1 = operator new(0x80u);
  *v1 = v1;
  v1[1] = v1;
  v1[2] = v1;
  *((_WORD *)v1 + 12) = 257;
  v49[0] = (unsigned __int64)v1;
  *(_QWORD *)&v44[0] = &std::_Func_impl_no_alloc<_lambda_8d831eddfe3752f93790a35eaa4aecc3_,void,std::filesystem::path const &,char const *>::`vftable';
  *((_QWORD *)&v44[0] + 1) = v52;
  v45 = v44;
  UusPackage::GetLatestPackage(v64, v49, v44);
  if ( v67 )
  {
    v55 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v56 = si128;
    LOWORD(v55) = 0;
    v53 = 0;
    v54 = si128;
    LOWORD(v53) = 0;
    memset(lpExistingFileName, 0, sizeof(lpExistingFileName));
    try
    {
      UusPackage::GetUpdateInfo(v64, lpExistingFileName);
      v3 = std::wstring::wstring(v44, UusPackageUpdateInfo::_keyUpdateId);
      UusPackageUpdateInfo::GetStringOrEmpty(lpExistingFileName, lpNewFileName, v3);
      std::wstring::_Tidy_deallocate(&v55);
      v55 = *(_OWORD *)lpNewFileName;
      v56 = v48;
      v48 = si128;
      LOWORD(lpNewFileName[0]) = 0;
      std::wstring::_Tidy_deallocate(lpNewFileName);
      v4 = std::wstring::wstring(v44, UusPackageUpdateInfo::_keyFlightId);
      UusPackageUpdateInfo::GetStringOrEmpty(lpExistingFileName, lpNewFileName, v4);
      v5 = 192;
      std::wstring::_Tidy_deallocate(&v53);
      v53 = *(_OWORD *)lpNewFileName;
      v54 = v48;
      v48 = si128;
      LOWORD(lpNewFileName[0]) = 0;
      std::wstring::_Tidy_deallocate(lpNewFileName);
      v50 = *(_DWORD *)UusPackageUpdateInfo::GetDurationSinceInstalledTime<std::chrono::duration<int,std::ratio<60,1>>>(
                         lpExistingFileName,
                         &v39);
      lpExistingFileName[0] = (LPCWSTR)&UusPackageUpdateInfo::`vftable';
      if ( lpExistingFileName[7] )
        (*(void (__fastcall **)(LPCWSTR, __int64))(*(_QWORD *)lpExistingFileName[7] + 192LL))(lpExistingFileName[7], 1);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&lpExistingFileName[5]);
      std::wstring::_Tidy_deallocate(&lpExistingFileName[1]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x40,
        (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\PackageScavenge.hpp",
        v6);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v5 = 192;
    }
    v7 = v49[1];
    v40 = v49[1];
    memset(v70, 0, 0xF8u);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v70);
    v37 = v66;
    std::_Tree<std::_Tmap_traits<unsigned __int64,UusPackage,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,UusPackage>>,0>>::erase(
      v49,
      &v37);
    UusState::GetRootFolder(v57);
    v38 = v44;
    v45 = 0;
    v8 = operator new(0x40u);
    *v8 = &std::_Func_impl_no_alloc<_lambda_2efa2d74120b9f4caa20bb41099c3060_,void,std::wstring const &>::`vftable';
    v8[1] = v64;
    v8[2] = v57;
    v8[3] = &v55;
    v8[4] = &v53;
    v8[5] = &v50;
    v8[6] = v70;
    v8[7] = v49;
    v45 = v8;
    v9 = v57;
    if ( v57[3] > 7u )
      v9 = (_QWORD *)v57[0];
    _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::EnumerateTokens(v9, v44);
    v10 = 0;
    v39 = 0;
    v11 = *(__int64 **)v49[0];
    while ( 1 )
    {
      v37 = v11;
      if ( *((_BYTE *)v11 + 25) )
        break;
      v68 = v11[4];
      UusPackage::UusPackage((UusPackage *)v69, (const struct UusPackage *)(v11 + 5));
      UusPackage::UusPackage((UusPackage *)&v58, (const struct UusPackage *)v69);
      try
      {
        std::wstring::wstring(lpNewFileName, v59);
        UusVersion::GetString(v61, Src);
        v12 = v5 | 3;
        v38 = (_OWORD *)qword_180063B00;
        v13 = &PackageScavenge::_deletionPreffix;
        if ( (unsigned __int64)qword_180063B08 > 7 )
          v13 = (void **)PackageScavenge::_deletionPreffix;
        v14 = v42;
        if ( qword_180063B00 > v43 - v42 )
        {
          v17 = (void **)std::wstring::_Reallocate_grow_by<_lambda_967c2ed818824c5314a20ec3af46b793_,unsigned __int64,wchar_t const *,unsigned __int64>(
                           Src,
                           v13,
                           qword_180063B00);
        }
        else
        {
          v42 += qword_180063B00;
          v15 = Src;
          if ( v43 > 7 )
            v15 = (void **)Src[0];
          if ( (void **)((char *)v13 + 2 * qword_180063B00) <= v15 || v13 > (void **)((char *)v15 + 2 * v14) )
          {
            v16 = qword_180063B00;
          }
          else if ( v15 > v13 )
          {
            v16 = ((char *)v15 - (char *)v13) >> 1;
          }
          else
          {
            v16 = 0;
          }
          memmove((char *)v15 + 2 * qword_180063B00, v15, 2 * v14 + 2);
          v0 = 2 * v16;
          memmove(v15, v13, 2 * v16);
          memmove((char *)v15 + 2 * v16, (char *)v13 + 2 * ((_QWORD)v38 + v16), 2 * ((_QWORD)v38 - v16));
          v17 = Src;
          v10 = v39;
        }
        v44[0] = *(_OWORD *)v17;
        v18 = v44[0];
        v19 = *((_OWORD *)v17 + 1);
        v17[2] = 0;
        v17[3] = (void *)7;
        *(_WORD *)v17 = 0;
        *(_OWORD *)lpExistingFileName = v18;
        *(_OWORD *)&lpExistingFileName[2] = v19;
        v44[1] = si128;
        LOWORD(v44[0]) = 0;
        std::filesystem::path::remove_filename((std::filesystem::path *)lpNewFileName);
        std::filesystem::path::operator/=(lpNewFileName, lpExistingFileName);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(v44);
        std::wstring::_Tidy_deallocate(Src);
        std::wstring::wstring(lpExistingFileName, v59);
        v5 = v12 | 0xC;
        v35 = v5;
        v20 = (const WCHAR *)lpNewFileName;
        if ( v48.m128i_i64[1] > 7uLL )
          v20 = lpNewFileName[0];
        v21 = (const WCHAR *)lpExistingFileName;
        if ( lpExistingFileName[3] > (LPCWSTR)7 )
          v21 = lpExistingFileName[0];
        if ( !MoveFileExW(v21, v20, 3u) )
        {
          LastError = GetLastError();
          if ( LastError )
            std::filesystem::_Throw_fs_error(v23, LastError, lpExistingFileName, lpNewFileName);
        }
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::filesystem::remove_all((std::filesystem *)lpNewFileName, v24);
        v39 = ++v10;
        std::wstring::_Tidy_deallocate(lpNewFileName);
      }
      catch ( const std::exception *v46 )
      {
        v31 = v0;
        v32 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v46 + 8LL))(v46);
        std::wstring::wstring(lpNewFileName, v59);
        v33 = (const wchar_t *)lpNewFileName;
        if ( v48.m128i_i64[1] > 7uLL )
          v33 = lpNewFileName[0];
        UusVersion::GetString(v61, lpExistingFileName);
        v36 = v35 | 0x300;
        v34 = (const wchar_t *)lpExistingFileName;
        if ( lpExistingFileName[3] > (LPCWSTR)7 )
          v34 = lpExistingFileName[0];
        uus::UndockedUpdateTelemetry::UusFailedToRemoveUnusedPackage(v34, v33, v32);
        std::wstring::_Tidy_deallocate(lpExistingFileName);
        std::wstring::_Tidy_deallocate(lpNewFileName);
        v0 = v31;
        v11 = v37;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v5 = v36;
        v10 = v39;
      }
      v7 = v40;
      v58 = &UusPackage::`vftable';
      if ( v63 )
        (*v62)(&v62, 0);
      v61[0] = &UusVersion::`vftable';
      if ( v60 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 192LL))(v60, 1);
      std::wstring::_Tidy_deallocate(v59);
      std::pair<unsigned __int64 const,UusPackage>::~pair<unsigned __int64 const,UusPackage>(&v68);
      v25 = (__int64 **)v11[2];
      if ( *((_BYTE *)v25 + 25) )
      {
        for ( i = (__int64 *)v11[1]; !*((_BYTE *)i + 25) && v11 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v11 = i;
        v11 = i;
      }
      else
      {
        v11 = (__int64 *)v11[2];
        for ( j = *v25; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v11 = j;
      }
    }
    v28 = v49[1];
    std::wstringbuf::str(&v70[3], lpNewFileName);
    v29 = (const wchar_t *)lpNewFileName;
    if ( v48.m128i_i64[1] > 7uLL )
      v29 = lpNewFileName[0];
    UusVersion::GetString(v65, lpExistingFileName);
    v30 = (const wchar_t *)lpExistingFileName;
    if ( lpExistingFileName[3] > (LPCWSTR)7 )
      v30 = lpExistingFileName[0];
    uus::UndockedUpdateTelemetry::UusScavengeReport(v30, v29, v7, v28, v10, v52[0], v52[1]);
    std::wstring::_Tidy_deallocate(lpExistingFileName);
    std::wstring::_Tidy_deallocate(lpNewFileName);
    std::wstring::_Tidy_deallocate(v57);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(&v70[19]);
    v70[19] = &std::wios::`vftable';
    std::ios_base::~ios_base((std::ios_base *)&v70[19]);
    std::wstring::_Tidy_deallocate(&v53);
    std::wstring::_Tidy_deallocate(&v55);
    if ( v67 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))v64[0])(v64, 0);
  }
  std::_Tree<std::_Tmap_traits<unsigned __int64,UusPackage,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,UusPackage>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,UusPackage,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,UusPackage>>,0>>(v49);
}

```

## disassembly

```asm
0x18000c510  mov     rax, rsp
0x18000c513  mov     [rax+8], rbx
0x18000c517  mov     [rax+10h], rsi
0x18000c51b  mov     [rax+18h], rdi
0x18000c51f  mov     [rax+20h], r12
0x18000c523  push    r13
0x18000c525  push    r14
0x18000c527  push    r15
0x18000c529  sub     rsp, 400h
0x18000c530  movaps  xmmword ptr [rax-28h], xmm6
0x18000c534  mov     rax, cs:__security_cookie
0x18000c53b  xor     rax, rsp
0x18000c53e  mov     [rsp+418h+var_38], rax
0x18000c546  xor     esi, esi
0x18000c548  mov     [rsp+418h+var_3D8], esi
0x18000c54c  lea     rcx, [rsp+418h+var_2C8]
0x18000c554  call    ?RemovePackagesMarkedForDeletion@PackageScavenge@@CA?AU?$pair@_K_K@std@@XZ; PackageScavenge::RemovePackagesMarkedForDeletion(void)
0x18000c559  xorps   xmm1, xmm1
0x18000c55c  movdqu  xmmword ptr [rsp+418h+var_328], xmm1
0x18000c565  mov     ecx, 80h; Size
0x18000c56a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c56f  mov     [rax], rax
0x18000c572  mov     [rax+8], rax
0x18000c576  mov     [rax+10h], rax
0x18000c57a  mov     word ptr [rax+18h], 101h
0x18000c580  mov     [rsp+418h+var_328], rax
0x18000c588  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_8d831eddfe3752f93790a35eaa4aecc3_@@XAEBVpath@filesystem@std@@PEBD@std@@6B@; const std::_Func_impl_no_alloc<_lambda_8d831eddfe3752f93790a35eaa4aecc3_,void,std::filesystem::path const &,char const *>::`vftable'
0x18000c58f  mov     qword ptr [rsp+418h+var_390], rax
0x18000c597  lea     rax, [rsp+418h+var_2C8]
0x18000c59f  mov     qword ptr [rsp+418h+var_390+8], rax
0x18000c5a7  lea     rax, [rsp+418h+var_390]
0x18000c5af  mov     [rsp+418h+var_358], rax
0x18000c5b7  lea     r8, [rsp+418h+var_390]
0x18000c5bf  lea     rdx, [rsp+418h+var_328]
0x18000c5c7  lea     rcx, [rsp+418h+var_1F8]
0x18000c5cf  call    ?GetLatestPackage@UusPackage@@SA?AV?$optional@VUusPackage@@@std@@PEAV?$map@_KVUusPackage@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KVUusPackage@@@std@@@3@@3@V?$function@$$A6AXAEBVpath@filesystem@std@@PEBD@Z@3@@Z; UusPackage::GetLatestPackage(std::map<unsigned __int64,UusPackage> *,std::function<void (std::filesystem::path const &,char const *)>)
0x18000c5d4  nop
0x18000c5d5  cmp     [rsp+418h+var_1A0], sil
0x18000c5dd  jnz     short loc_18000C5E4
0x18000c5df  jmp     loc_18000CD99
0x18000c5e4  xorps   xmm0, xmm0
0x18000c5e7  movups  [rsp+418h+var_298], xmm0
0x18000c5ef  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000c5f7  movdqu  [rsp+418h+var_288], xmm6
0x18000c600  mov     word ptr [rsp+418h+var_298], si
0x18000c608  movups  [rsp+418h+var_2B8], xmm0
0x18000c610  movdqu  [rsp+418h+var_2A8], xmm6
0x18000c619  mov     word ptr [rsp+418h+var_2B8], si
0x18000c621  xor     edx, edx; Val
0x18000c623  lea     r8d, [rdx+40h]; Size
0x18000c627  lea     rcx, [rsp+418h+lpExistingFileName]; void *
0x18000c62f  call    memset
0x18000c634  lea     rdx, [rsp+418h+lpExistingFileName]
0x18000c63c  lea     rcx, [rsp+418h+var_1F8]
0x18000c644  call    ?GetUpdateInfo@UusPackage@@QEBA?AVUusPackageUpdateInfo@@XZ; UusPackage::GetUpdateInfo(void)
0x18000c649  nop
0x18000c64a  lea     rdx, ?_keyUpdateId@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyUpdateId
0x18000c651  lea     rcx, [rsp+418h+var_390]
0x18000c659  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c65e  mov     r8, rax
0x18000c661  lea     rdx, [rsp+418h+lpNewFileName]
0x18000c669  lea     rcx, [rsp+418h+lpExistingFileName]
0x18000c671  call    ?GetStringOrEmpty@UusPackageUpdateInfo@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V23@@Z; UusPackageUpdateInfo::GetStringOrEmpty(std::wstring)
0x18000c676  mov     [rsp+418h+var_3D8], 40h ; '@'
0x18000c67e  lea     rcx, [rsp+418h+var_298]
0x18000c686  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c68b  movups  xmm0, xmmword ptr [rsp+418h+lpNewFileName]
0x18000c693  movups  [rsp+418h+var_298], xmm0
0x18000c69b  movups  xmm1, [rsp+418h+var_338]
0x18000c6a3  movups  [rsp+418h+var_288], xmm1
0x18000c6ab  movdqu  [rsp+418h+var_338], xmm6
0x18000c6b4  mov     word ptr [rsp+418h+lpNewFileName], si
0x18000c6bc  lea     rcx, [rsp+418h+lpNewFileName]
0x18000c6c4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c6c9  lea     rdx, ?_keyFlightId@UusPackageUpdateInfo@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const UusPackageUpdateInfo::_keyFlightId
0x18000c6d0  lea     rcx, [rsp+418h+var_390]
0x18000c6d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c6dd  mov     r8, rax
0x18000c6e0  lea     rdx, [rsp+418h+lpNewFileName]
0x18000c6e8  lea     rcx, [rsp+418h+lpExistingFileName]
0x18000c6f0  call    ?GetStringOrEmpty@UusPackageUpdateInfo@@AEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V23@@Z; UusPackageUpdateInfo::GetStringOrEmpty(std::wstring)
0x18000c6f5  mov     r14d, 0C0h
0x18000c6fb  mov     [rsp+418h+var_3D8], r14d
0x18000c700  lea     rcx, [rsp+418h+var_2B8]
0x18000c708  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c70d  movups  xmm0, xmmword ptr [rsp+418h+lpNewFileName]
0x18000c715  movups  [rsp+418h+var_2B8], xmm0
0x18000c71d  movups  xmm1, [rsp+418h+var_338]
0x18000c725  movups  [rsp+418h+var_2A8], xmm1
0x18000c72d  movdqu  [rsp+418h+var_338], xmm6
0x18000c736  mov     word ptr [rsp+418h+lpNewFileName], si
0x18000c73e  lea     rcx, [rsp+418h+lpNewFileName]
0x18000c746  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c74b  lea     rdx, [rsp+418h+var_3C0]
0x18000c750  lea     rcx, [rsp+418h+lpExistingFileName]
0x18000c758  call    ??$GetDurationSinceInstalledTime@V?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@@UusPackageUpdateInfo@@QEBA?AV?$duration@HU?$ratio@$0DM@$00@std@@@chrono@std@@XZ; UusPackageUpdateInfo::GetDurationSinceInstalledTime<std::chrono::duration<int,std::ratio<60,1>>>(void)
0x18000c75d  mov     eax, [rax]
0x18000c75f  mov     [rsp+418h+var_318], eax
0x18000c766  lea     rax, ??_7UusPackageUpdateInfo@@6B@; const UusPackageUpdateInfo::`vftable'
0x18000c76d  mov     [rsp+418h+lpExistingFileName], rax
0x18000c775  mov     rcx, [rsp+418h+var_2D0]
0x18000c77d  test    rcx, rcx
0x18000c780  jz      short loc_18000C796
0x18000c782  mov     rax, [rcx]
0x18000c785  mov     edx, 1
0x18000c78a  mov     rax, [rax+0C0h]
0x18000c791  call    _guard_dispatch_icall
0x18000c796  lea     rcx, [rsp+418h+var_2E0]
0x18000c79e  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000c7a3  lea     rcx, [rsp+418h+lpExistingFileName+8]
0x18000c7ab  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000c7b0  nop
0x18000c7b1  jmp     short loc_18000C7C2
0x18000c7b3  xor     esi, esi
0x18000c7b5  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18000c7bd  mov     r14d, [rsp+418h+var_3D8]
0x18000c7c2  mov     r12, [rsp+418h+var_328+8]
0x18000c7ca  mov     [rsp+418h+var_3B8], r12
0x18000c7cf  xor     edx, edx; Val
0x18000c7d1  mov     r8d, 0F8h; Size
0x18000c7d7  lea     rcx, [rsp+418h+var_138]; void *
0x18000c7df  call    memset
0x18000c7e4  lea     rcx, [rsp+418h+var_138]
0x18000c7ec  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x18000c7f1  nop
0x18000c7f2  mov     rax, [rsp+418h+var_1C0]
0x18000c7fa  mov     [rsp+418h+var_3D0], rax
0x18000c7ff  lea     rdx, [rsp+418h+var_3D0]
0x18000c804  lea     rcx, [rsp+418h+var_328]
0x18000c80c  call    ?erase@?$_Tree@V?$_Tmap_traits@_KVUusPackage@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KVUusPackage@@@std@@@3@$0A@@std@@@std@@QEAA_KAEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,UusPackage,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,UusPackage>>,0>>::erase(unsigned __int64 const &)
0x18000c811  lea     rcx, [rsp+418h+var_278]
0x18000c819  call    ?GetRootFolder@UusState@@SA?AVpath@filesystem@std@@XZ; UusState::GetRootFolder(void)
0x18000c81e  nop
0x18000c81f  lea     rax, [rsp+418h+var_390]
0x18000c827  mov     [rsp+418h+var_3C8], rax
0x18000c82c  mov     [rsp+418h+var_358], rsi
0x18000c834  mov     ecx, 40h ; '@'; Size
0x18000c839  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c83e  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_2efa2d74120b9f4caa20bb41099c3060_@@XAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_2efa2d74120b9f4caa20bb41099c3060_,void,std::wstring const &>::`vftable'
0x18000c845  mov     [rax], rcx
0x18000c848  lea     rcx, [rsp+418h+var_1F8]
0x18000c850  mov     [rax+8], rcx
0x18000c854  lea     rcx, [rsp+418h+var_278]
0x18000c85c  mov     [rax+10h], rcx
0x18000c860  lea     rcx, [rsp+418h+var_298]
0x18000c868  mov     [rax+18h], rcx
0x18000c86c  lea     rcx, [rsp+418h+var_2B8]
0x18000c874  mov     [rax+20h], rcx
0x18000c878  lea     rcx, [rsp+418h+var_318]
0x18000c880  mov     [rax+28h], rcx
0x18000c884  lea     rcx, [rsp+418h+var_138]
0x18000c88c  mov     [rax+30h], rcx
0x18000c890  lea     rcx, [rsp+418h+var_328]
0x18000c898  mov     [rax+38h], rcx
0x18000c89c  mov     [rsp+418h+var_358], rax
0x18000c8a4  lea     rcx, [rsp+418h+var_278]
0x18000c8ac  cmp     [rsp+418h+var_260], 7
0x18000c8b5  cmova   rcx, [rsp+418h+var_278]
0x18000c8be  lea     rdx, [rsp+418h+var_390]
0x18000c8c6  call    ?EnumerateTokens@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@SAXPEB_WV?$function@$$A6AXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@std@@@Z; _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::EnumerateTokens(wchar_t const *,std::function<void (std::wstring const &)>)
0x18000c8cb  mov     r15, rsi
0x18000c8ce  mov     [rsp+418h+var_3C0], rsi
0x18000c8d3  mov     rbx, [rsp+418h+var_328]
0x18000c8db  mov     rbx, [rbx]
0x18000c8de  mov     [rsp+418h+var_3D0], rbx
0x18000c8e3  cmp     [rbx+19h], sil
0x18000c8e7  jnz     loc_18000CC70
0x18000c8ed  mov     rax, [rbx+20h]
0x18000c8f1  mov     [rsp+418h+var_198], rax
0x18000c8f9  lea     rdx, [rbx+28h]; struct UusPackage *
0x18000c8fd  lea     rcx, [rsp+418h+var_190]; this
0x18000c905  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x18000c90a  nop
0x18000c90b  lea     rdx, [rsp+418h+var_190]; struct UusPackage *
0x18000c913  lea     rcx, [rsp+418h+var_258]; this
0x18000c91b  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x18000c920  nop
0x18000c921  lea     rdx, [rsp+418h+var_250]
0x18000c929  lea     rcx, [rsp+418h+lpNewFileName]
0x18000c931  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000c936  or      r14d, 1
0x18000c93a  mov     [rsp+418h+var_3D8], r14d
0x18000c93f  lea     rdx, [rsp+418h+Src]
0x18000c944  lea     rcx, [rsp+418h+var_228]
0x18000c94c  call    ?GetString@UusVersion@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; UusVersion::GetString(void)
0x18000c951  or      r14d, 2
0x18000c955  mov     [rsp+418h+var_3D8], r14d
0x18000c95a  mov     rcx, cs:qword_180063B00
0x18000c961  mov     [rsp+418h+var_3C8], rcx
0x18000c966  lea     r12, ?_deletionPreffix@PackageScavenge@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const PackageScavenge::_deletionPreffix
0x18000c96d  cmp     cs:qword_180063B08, 7
0x18000c975  cmova   r12, cs:?_deletionPreffix@PackageScavenge@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const PackageScavenge::_deletionPreffix
0x18000c97d  mov     r8, [rsp+418h+var_3A0]
0x18000c982  mov     rax, [rsp+418h+var_398]
0x18000c98a  sub     rax, r8
0x18000c98d  cmp     rcx, rax
0x18000c990  ja      loc_18000CA3B
0x18000c996  lea     rax, [r8+rcx]
0x18000c99a  mov     [rsp+418h+var_3A0], rax
0x18000c99f  lea     r13, [rsp+418h+Src]
0x18000c9a4  cmp     [rsp+418h+var_398], 7
0x18000c9ad  cmova   r13, [rsp+418h+Src]
0x18000c9b3  lea     rax, [r12+rcx*2]
0x18000c9b7  cmp     rax, r13
0x18000c9ba  jbe     short loc_18000C9E1
0x18000c9bc  lea     rax, ds:0[r8*2]
0x18000c9c4  add     rax, r13
0x18000c9c7  cmp     r12, rax
0x18000c9ca  ja      short loc_18000C9E1
0x18000c9cc  cmp     r13, r12
0x18000c9cf  ja      short loc_18000C9D6
0x18000c9d1  mov     r15, rsi
0x18000c9d4  jmp     short loc_18000C9E4
0x18000c9d6  mov     r15, r13
0x18000c9d9  sub     r15, r12
0x18000c9dc  sar     r15, 1
0x18000c9df  jmp     short loc_18000C9E4
0x18000c9e1  mov     r15, rcx
0x18000c9e4  lea     r8, ds:2[r8*2]; Size
0x18000c9ec  lea     rcx, ds:0[rcx*2]
0x18000c9f4  add     rcx, r13; void *
0x18000c9f7  mov     rdx, r13; Src
0x18000c9fa  call    memmove
0x18000c9ff  lea     rdi, [r15+r15]
0x18000ca03  mov     r8, rdi; Size
0x18000ca06  mov     rdx, r12; Src
0x18000ca09  mov     rcx, r13; void *
0x18000ca0c  call    memmove
0x18000ca11  mov     rax, [rsp+418h+var_3C8]
0x18000ca16  mov     r8, rax
0x18000ca19  sub     r8, r15
0x18000ca1c  add     r8, r8; Size
0x18000ca1f  add     rax, r15
0x18000ca22  lea     rdx, [r12+rax*2]; Src
0x18000ca26  lea     rcx, [rdi+r13]; void *
0x18000ca2a  call    memmove
0x18000ca2f  lea     rax, [rsp+418h+Src]
0x18000ca34  mov     r15, [rsp+418h+var_3C0]
0x18000ca39  jmp     short loc_18000CA52
0x18000ca3b  mov     [rsp+418h+var_3F0], rcx; __int64
0x18000ca40  mov     [rsp+418h+var_3F8], r12; void *
0x18000ca45  mov     rdx, rcx
0x18000ca48  lea     rcx, [rsp+418h+Src]; Src
0x18000ca4d  call    ??$_Reallocate_grow_by@V_lambda_967c2ed818824c5314a20ec3af46b793_@@_KPEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_967c2ed818824c5314a20ec3af46b793_@@_KPEB_W2@Z; std::wstring::_Reallocate_grow_by<_lambda_967c2ed818824c5314a20ec3af46b793_,unsigned __int64,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_967c2ed818824c5314a20ec3af46b793_,unsigned __int64,wchar_t const *,unsigned __int64)
0x18000ca52  movups  xmm1, xmmword ptr [rax]
0x18000ca55  movups  [rsp+418h+var_390], xmm1
0x18000ca5d  movups  xmm0, xmmword ptr [rax+10h]
0x18000ca61  mov     [rax+10h], rsi
0x18000ca65  mov     qword ptr [rax+18h], 7
0x18000ca6d  mov     [rax], si
0x18000ca70  or      r14d, 4
0x18000ca74  mov     [rsp+418h+var_3D8], r14d
0x18000ca79  movups  xmmword ptr [rsp+418h+lpExistingFileName], xmm1
0x18000ca81  movups  [rsp+418h+var_2F8], xmm0
0x18000ca89  movdqu  [rsp+418h+var_380], xmm6
0x18000ca92  mov     word ptr [rsp+418h+var_390], si
0x18000ca9a  lea     rcx, [rsp+418h+lpNewFileName]; this
0x18000caa2  call    ?remove_filename@path@filesystem@std@@QEAAAEAV123@XZ; std::filesystem::path::remove_filename(void)
0x18000caa7  lea     rdx, [rsp+418h+lpExistingFileName]; void *
0x18000caaf  lea     rcx, [rsp+418h+lpNewFileName]; Src
0x18000cab7  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18000cabc  nop
0x18000cabd  lea     rcx, [rsp+418h+lpExistingFileName]
0x18000cac5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000caca  nop
0x18000cacb  lea     rcx, [rsp+418h+var_390]
0x18000cad3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cad8  nop
0x18000cad9  lea     rcx, [rsp+418h+Src]
0x18000cade  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cae3  lea     rdx, [rsp+418h+var_250]
0x18000caeb  lea     rcx, [rsp+418h+lpExistingFileName]
0x18000caf3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000caf8  or      r14d, 8
0x18000cafc  mov     [rsp+418h+var_3D8], r14d
0x18000cb01  lea     rdx, [rsp+418h+lpNewFileName]
0x18000cb09  cmp     qword ptr [rsp+418h+var_338+8], 7
0x18000cb12  cmova   rdx, [rsp+418h+lpNewFileName]; lpNewFileName
0x18000cb1b  lea     rcx, [rsp+418h+lpExistingFileName]
0x18000cb23  cmp     qword ptr [rsp+418h+var_2F8+8], 7
0x18000cb2c  cmova   rcx, [rsp+418h+lpExistingFileName]; lpExistingFileName
0x18000cb35  mov     r8d, 3; dwFlags
0x18000cb3b  call    cs:__imp_MoveFileExW
0x18000cb41  test    eax, eax
0x18000cb43  jnz     short loc_18000CB53
0x18000cb45  call    cs:__imp_GetLastError
0x18000cb4b  test    eax, eax
0x18000cb4d  jnz     loc_18000CDDD
0x18000cb53  lea     rcx, [rsp+418h+lpExistingFileName]
0x18000cb5b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cb60  lea     rcx, [rsp+418h+lpNewFileName]; this
0x18000cb68  call    ?remove_all@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::remove_all(std::filesystem::path const &)
0x18000cb6d  inc     r15
0x18000cb70  mov     [rsp+418h+var_3C0], r15
0x18000cb75  lea     rcx, [rsp+418h+lpNewFileName]
0x18000cb7d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000cb82  nop
0x18000cb83  jmp     short loc_18000CB9E
0x18000cb85  xor     esi, esi
0x18000cb87  mov     rbx, [rsp+418h+var_3D0]
  ... truncated ...
```
