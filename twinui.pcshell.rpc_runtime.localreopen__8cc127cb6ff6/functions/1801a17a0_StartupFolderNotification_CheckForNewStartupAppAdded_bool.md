# StartupFolderNotification::CheckForNewStartupAppAdded(bool)

- ea: `0x1801a17a0`
- end: `0x1801a1e34`
- name: `?CheckForNewStartupAppAdded@StartupFolderNotification@@UEAAX_N@Z`
- size: `1684`
- prototype: `void __fastcall(StartupFolderNotification *__hidden this, bool)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, installer_update`

## callees

- `0x180043f00`
- `0x18005db20`
- `0x18005f410`
- `0x18005f480`
- `0x18005f540`
- `0x18005fa88`
- `0x18005fd20`
- `0x18006634c`
- `0x18007f488`
- `0x1801a17a0`
- `0x1801a1e3c`
- `0x1801a1e9c`
- `0x18028ba78`
- `0x18029b3b4`
- `0x1802a3790`
- `0x1802c4dec`
- `0x1802c8a40`
- `0x180356360`
- `0x18039a22c`
- `0x1803bc514`
- `0x1803bc538`
- `0x1805a512c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801a1a10`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801a1a10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a19d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a1ad3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a19d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801a1ad3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a1a7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a1d8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a1a7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a1d8d`
- `msvcp_win!_Query_perf_frequency` at `0x1801a1bfc`
- `msvcp_win!_Query_perf_frequency` at `0x1801a1bfc`
- `msvcp_win!_Query_perf_counter` at `0x1801a1c05`
- `msvcp_win!_Query_perf_counter` at `0x1801a1c05`

## string_xrefs

- `0x1801a182b`: `directory_iterator::directory_iterator`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall StartupFolderNotification::CheckForNewStartupAppAdded(StartupFolderNotification *this, char a2)
{
  std::_Ref_count_base *v4; // rax
  std::_Ref_count_base *v5; // rcx
  unsigned int v6; // eax
  std::_Ref_count_base *v7; // rdi
  __int64 v8; // rax
  std::_Ref_count_base *v9; // rsi
  __int64 v10; // rax
  const unsigned __int16 *v11; // r8
  std::filesystem **v12; // r14
  std::filesystem *v13; // rcx
  const unsigned __int16 *filename; // rax
  __int64 v15; // r10
  LPCWSTR *v16; // rcx
  const unsigned __int16 *v17; // r8
  std::filesystem *v18; // rcx
  const unsigned __int16 *v19; // rax
  __int64 v20; // r10
  const WCHAR *v21; // rdx
  LSTATUS Value; // ebx
  __int64 v23; // rax
  unsigned int v24; // eax
  const WCHAR *v25; // rdx
  unsigned int v26; // eax
  const WCHAR *v27; // rdx
  _QWORD *v28; // rax
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 perf_frequency; // rbx
  __int64 perf_counter; // rax
  __int64 v33; // rax
  _QWORD *v34; // rdx
  __int64 v35; // rax
  int updated; // eax
  const WCHAR *v37; // rdx
  unsigned int v38; // eax
  unsigned int v39; // eax
  __int64 v40; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  unsigned int lpDataa; // [rsp+20h] [rbp-E0h]
  int lpDatab; // [rsp+20h] [rbp-E0h]
  unsigned int lpDatac; // [rsp+20h] [rbp-E0h]
  BYTE v45[8]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v47[2]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v48; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v49; // [rsp+58h] [rbp-A8h]
  __int128 v50; // [rsp+60h] [rbp-A0h]
  _BYTE v51[192]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+130h] [rbp+30h] BYREF
  __int128 v53; // [rsp+138h] [rbp+38h] BYREF
  __int64 v54; // [rsp+148h] [rbp+48h]
  __int64 v55; // [rsp+150h] [rbp+50h]
  _BYTE v56[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v57[32]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v58[32]; // [rsp+198h] [rbp+98h] BYREF
  int v59; // [rsp+1B8h] [rbp+B8h]
  int v60; // [rsp+1BCh] [rbp+BCh]
  __int64 v61; // [rsp+1C0h] [rbp+C0h]
  __int128 v62; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v63; // [rsp+1D8h] [rbp+D8h]
  __int64 v64; // [rsp+1E0h] [rbp+E0h]
  LPCWSTR lpValueName[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v66; // [rsp+200h] [rbp+100h]
  LPCWSTR Src[2]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v68; // [rsp+220h] [rbp+120h]
  _OWORD v69[2]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v70[32]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v4 = (StartupFolderNotification *)((char *)this + 64);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(std::_Ref_count_base **)v4;
  v47[0] = v4;
  v47[1] = v5;
  std::wstring::wstring(lpValueName, v47);
  *(_OWORD *)v47 = 0;
  v6 = std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(v47, lpValueName);
  if ( v6 )
    std::filesystem::_Throw_fs_error("directory_iterator::directory_iterator", v6, lpValueName);
  std::wstring::_Tidy_deallocate(lpValueName);
  v7 = v47[1];
  if ( v47[1] )
  {
    v8 = (__int64)v47[1] + 8;
    _InterlockedIncrement((volatile signed __int32 *)v47[1] + 2);
  }
  else
  {
    v8 = 8;
  }
  v9 = v47[0];
  v48 = v47[0];
  v49 = v7;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)v8);
  v50 = 0;
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  while ( v9 )
  {
    *(_OWORD *)Src = 0;
    v68 = 0;
    v10 = std::_WChar_traits<unsigned short>::length(L"StartupTNoti");
    std::wstring::_Construct<1,unsigned short const *>(Src, L"StartupTNoti", v10);
    v12 = (std::filesystem **)((char *)v9 + 32);
    if ( *((_QWORD *)v9 + 7) <= 7u )
      v13 = (std::_Ref_count_base *)((char *)v9 + 32);
    else
      v13 = *v12;
    filename = std::filesystem::_Find_filename(v13, (const unsigned __int16 *const)v13 + *((_QWORD *)v9 + 6), v11);
    *(_OWORD *)lpValueName = 0;
    v66 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(lpValueName, filename, (v15 - (__int64)filename) >> 1);
    v16 = lpValueName;
    if ( *((_QWORD *)&v66 + 1) > 7u )
      v16 = (LPCWSTR *)lpValueName[0];
    std::_WChar_traits<unsigned short>::length(v16);
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Tidy_deallocate(lpValueName);
    if ( *((_QWORD *)v9 + 7) <= 7u )
      v18 = (std::_Ref_count_base *)((char *)v9 + 32);
    else
      v18 = *v12;
    v19 = std::filesystem::_Find_filename(v18, (const unsigned __int16 *const)v18 + *((_QWORD *)v9 + 6), v17);
    *(_OWORD *)lpValueName = 0;
    v66 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(lpValueName, v19, (v20 - (__int64)v19) >> 1);
    v21 = (const WCHAR *)lpValueName;
    if ( *((_QWORD *)&v66 + 1) > 7u )
      v21 = lpValueName[0];
    Value = RegQueryValueExW(*((HKEY *)this + 1), v21, 0, 0, 0, 0);
    std::wstring::_Tidy_deallocate(lpValueName);
    if ( !Value )
    {
      v23 = std::filesystem::path::filename((char *)v9 + 32, v69);
      if ( *(_QWORD *)(v23 + 24) > 7u )
        v23 = *(_QWORD *)v23;
      v24 = RegDeleteValueW(*((HKEY *)this + 1), (LPCWSTR)v23);
      if ( v24 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x148,
          (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
          (const char *)v24,
          lpData);
      std::wstring::_Tidy_deallocate(v69);
      *(_DWORD *)Data = *((_DWORD *)this + 14);
      v25 = (const WCHAR *)Src;
      if ( *((_QWORD *)&v68 + 1) > 7u )
        v25 = Src[0];
      v26 = RegSetValueExW(*((HKEY *)this + 1), v25, 0, 4u, Data, 4u);
      if ( v26 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x14B,
          (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
          (const char *)v26,
          lpDataa);
    }
    v27 = (const WCHAR *)Src;
    if ( *((_QWORD *)&v68 + 1) > 7u )
      v27 = Src[0];
    if ( RegQueryValueExW(*((HKEY *)this + 1), v27, 0, 0, 0, 0) == 2
      && StartupFolderNotification::IsValidStartupAppFile(v9) )
    {
      if ( a2 )
      {
        v28 = (_QWORD *)std::filesystem::path::filename((char *)v9 + 32, v70);
        memset(v69, 0, sizeof(v69));
        v29 = v28[2];
        if ( v28[3] > 7u )
          v28 = (_QWORD *)*v28;
        std::wstring::_Construct<2,unsigned short const *>(v69, v28, v29);
        std::wstring::_Tidy_deallocate(v70);
        *(_OWORD *)lpValueName = 0;
        v66 = 0;
        if ( *((_QWORD *)v9 + 7) > 7u )
          v12 = (std::filesystem **)*v12;
        std::wstring::_Construct<2,unsigned short const *>(lpValueName, v12, *((_QWORD *)v9 + 6));
        v52 = *((_QWORD *)this + 12);
        v53 = 0;
        v54 = 0;
        v55 = 0;
        v30 = std::_WChar_traits<unsigned short>::length(&pvData);
        std::wstring::_Construct<1,unsigned short const *>(&v53, &pvData, v30);
        std::wstring::wstring(v56, v69);
        std::wstring::wstring(v57, Src);
        std::wstring::wstring(v58, lpValueName);
        v59 = *((_DWORD *)this + 14);
        v60 = 0;
        perf_frequency = _Query_perf_frequency();
        perf_counter = _Query_perf_counter();
        if ( perf_frequency == 10000000 )
        {
          v33 = 100 * perf_counter;
          goto LABEL_46;
        }
        if ( perf_frequency == 24000000 )
        {
          v61 = 1000000000 * (perf_counter / 24000000) + 1000000000 * (perf_counter % 24000000) / 24000000;
        }
        else
        {
          v33 = 1000000000 * (perf_counter / perf_frequency)
              + 1000000000 * (perf_counter % perf_frequency) / perf_frequency;
LABEL_46:
          v61 = v33;
        }
        v34 = (_QWORD *)((char *)this + 24);
        v62 = 0;
        v63 = 0;
        v64 = 0;
        if ( *((_QWORD *)this + 6) > 7u )
          v34 = (_QWORD *)*v34;
        std::wstring::_Construct<2,unsigned short const *>(&v62, v34, *((_QWORD *)this + 5));
        v35 = STARTUPAPPINFO::STARTUPAPPINFO(v51, &v52);
        updated = StartupAppMonitor::UpdateNotificationMap(v35);
        if ( updated < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x159,
            (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
            (const char *)(unsigned int)updated,
            lpDatab);
        std::wstring::_Tidy_deallocate(&v62);
        std::wstring::_Tidy_deallocate(v58);
        std::wstring::_Tidy_deallocate(v57);
        std::wstring::_Tidy_deallocate(v56);
        std::wstring::_Tidy_deallocate(&v53);
        std::wstring::_Tidy_deallocate(lpValueName);
        std::wstring::_Tidy_deallocate(v69);
        goto LABEL_54;
      }
      *(_DWORD *)v45 = *((_DWORD *)this + 14);
      v37 = (const WCHAR *)Src;
      if ( *((_QWORD *)&v68 + 1) > 7u )
        v37 = Src[0];
      v38 = RegSetValueExW(*((HKEY *)this + 1), v37, 0, 4u, v45, 4u);
      if ( v38 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x161,
          (unsigned int)"pcshell\\twinui\\startupappmonitor\\lib\\startupnotification.cpp",
          (const char *)v38,
          lpDatac);
    }
LABEL_54:
    std::wstring::_Tidy_deallocate(Src);
    v39 = std::filesystem::_Dir_enum_impl::_Advance_and_reset_if_no_more_files(&v48);
    if ( v39 )
      std::filesystem::_Throw_fs_error(v40, v39);
    v9 = v48;
  }
  if ( v49 )
    std::_Ref_count_base::_Decref(v49);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
}

```

## disassembly

```asm
0x1801a17a0  push    rbp
0x1801a17a2  push    rbx
0x1801a17a3  push    rsi
0x1801a17a4  push    rdi
0x1801a17a5  push    r12
0x1801a17a7  push    r13
0x1801a17a9  push    r14
0x1801a17ab  push    r15
0x1801a17ad  lea     rbp, [rsp-188h]
0x1801a17b5  sub     rsp, 288h
0x1801a17bc  mov     rax, cs:__security_cookie
0x1801a17c3  xor     rax, rsp
0x1801a17c6  mov     [rbp+1C0h+var_50], rax
0x1801a17cd  mov     r12b, dl
0x1801a17d0  mov     r15, rcx
0x1801a17d3  xor     r13d, r13d
0x1801a17d6  lea     rax, [rcx+40h]
0x1801a17da  mov     rcx, [rax+10h]
0x1801a17de  cmp     qword ptr [rax+18h], 7
0x1801a17e3  jbe     short loc_1801A17E8
0x1801a17e5  mov     rax, [rax]
0x1801a17e8  mov     [rsp+2C0h+var_280], rax
0x1801a17ed  mov     [rsp+2C0h+var_280+8], rcx
0x1801a17f2  lea     rdx, [rsp+2C0h+var_280]
0x1801a17f7  lea     rcx, [rbp+1C0h+lpValueName]
0x1801a17fe  call    ??$?0V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::basic_string_view<ushort> const &,std::allocator<ushort> const &)
0x1801a1803  nop
0x1801a1804  xorps   xmm0, xmm0
0x1801a1807  movdqu  xmmword ptr [rsp+2C0h+var_280], xmm0
0x1801a180d  lea     rdx, [rbp+1C0h+lpValueName]
0x1801a1814  lea     rcx, [rsp+2C0h+var_280]
0x1801a1819  call    ??$_Initialize_dir_enum@U_Dir_enum_impl@filesystem@std@@@_Dir_enum_impl@filesystem@std@@SA?AW4__std_win_error@@AEAV?$shared_ptr@U_Dir_enum_impl@filesystem@std@@@2@AEBVpath@12@W4directory_options@12@@Z; std::filesystem::_Dir_enum_impl::_Initialize_dir_enum<std::filesystem::_Dir_enum_impl>(std::shared_ptr<std::filesystem::_Dir_enum_impl> &,std::filesystem::path const &,std::filesystem::directory_options)
0x1801a181e  test    eax, eax
0x1801a1820  jz      short loc_1801A1838
0x1801a1822  lea     r8, [rbp+1C0h+lpValueName]
0x1801a1829  mov     edx, eax
0x1801a182b  lea     rcx, aDirectoryItera_0; "directory_iterator::directory_iterator"
0x1801a1832  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDW4__std_win_error@@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,__std_win_error,std::filesystem::path const &)
0x1801a1838  lea     rcx, [rbp+1C0h+lpValueName]
0x1801a183f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a1844  mov     rdi, [rsp+2C0h+var_280+8]
0x1801a1849  test    rdi, rdi
0x1801a184c  jz      short loc_1801A1857
0x1801a184e  lea     rax, [rdi+8]
0x1801a1852  lock inc dword ptr [rax]
0x1801a1855  jmp     short loc_1801A185C
0x1801a1857  mov     eax, 8
0x1801a185c  mov     rsi, [rsp+2C0h+var_280]
0x1801a1861  mov     [rsp+2C0h+var_270], rsi
0x1801a1866  mov     [rsp+2C0h+var_268], rdi
0x1801a186b  test    rdi, rdi
0x1801a186e  jz      short loc_1801A1873
0x1801a1870  lock inc dword ptr [rax]
0x1801a1873  xorps   xmm1, xmm1
0x1801a1876  movdqu  [rsp+2C0h+var_260], xmm1
0x1801a187c  test    rdi, rdi
0x1801a187f  jz      short loc_1801A188A
0x1801a1881  mov     rcx, rdi; this
0x1801a1884  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801a1889  nop
0x1801a188a  test    rsi, rsi
0x1801a188d  jz      loc_1801A1DF4
0x1801a1893  xorps   xmm0, xmm0
0x1801a1896  movups  xmmword ptr [rbp+1C0h+Src], xmm0
0x1801a189d  xorps   xmm1, xmm1
0x1801a18a0  movdqu  [rbp+1C0h+var_A0], xmm1
0x1801a18a8  lea     rcx, aStartuptnoti; "StartupTNoti"
0x1801a18af  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1801a18b4  mov     r8, rax
0x1801a18b7  lea     rdx, aStartuptnoti; "StartupTNoti"
0x1801a18be  lea     rcx, [rbp+1C0h+Src]
0x1801a18c5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801a18ca  nop
0x1801a18cb  lea     r14, [rsi+20h]
0x1801a18cf  cmp     qword ptr [rsi+38h], 7
0x1801a18d4  jbe     short loc_1801A18DB
0x1801a18d6  mov     rcx, [r14]
0x1801a18d9  jmp     short loc_1801A18DE
0x1801a18db  mov     rcx, r14; this
0x1801a18de  mov     rax, [rsi+30h]
0x1801a18e2  lea     r10, [rcx+rax*2]
0x1801a18e6  mov     rdx, r10; unsigned __int16 *
0x1801a18e9  call    ?_Find_filename@filesystem@std@@YAPEBGQEBGPEBG@Z; std::filesystem::_Find_filename(ushort const * const,ushort const *)
0x1801a18ee  xorps   xmm0, xmm0
0x1801a18f1  movups  xmmword ptr [rbp+1C0h+lpValueName], xmm0
0x1801a18f8  mov     qword ptr [rbp+1C0h+var_C0], r13
0x1801a18ff  mov     qword ptr [rbp+1C0h+var_C0+8], r13
0x1801a1906  sub     r10, rax
0x1801a1909  sar     r10, 1
0x1801a190c  mov     r8, r10
0x1801a190f  mov     rdx, rax
0x1801a1912  lea     rcx, [rbp+1C0h+lpValueName]
0x1801a1919  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801a191e  nop
0x1801a191f  lea     rcx, [rbp+1C0h+lpValueName]
0x1801a1926  cmp     qword ptr [rbp+1C0h+var_C0+8], 7
0x1801a192e  cmova   rcx, [rbp+1C0h+lpValueName]
0x1801a1936  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1801a193b  mov     r8, rax
0x1801a193e  mov     rdx, rcx
0x1801a1941  lea     rcx, [rbp+1C0h+Src]; Src
0x1801a1948  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1801a194d  nop
0x1801a194e  lea     rcx, [rbp+1C0h+lpValueName]
0x1801a1955  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a195a  cmp     qword ptr [rsi+38h], 7
0x1801a195f  jbe     short loc_1801A1966
0x1801a1961  mov     rcx, [r14]
0x1801a1964  jmp     short loc_1801A1969
0x1801a1966  mov     rcx, r14; this
0x1801a1969  mov     rax, [rsi+30h]
0x1801a196d  lea     r10, [rcx+rax*2]
0x1801a1971  mov     rdx, r10; unsigned __int16 *
0x1801a1974  call    ?_Find_filename@filesystem@std@@YAPEBGQEBGPEBG@Z; std::filesystem::_Find_filename(ushort const * const,ushort const *)
0x1801a1979  xorps   xmm0, xmm0
0x1801a197c  movups  xmmword ptr [rbp+1C0h+lpValueName], xmm0
0x1801a1983  mov     qword ptr [rbp+1C0h+var_C0], r13
0x1801a198a  mov     qword ptr [rbp+1C0h+var_C0+8], r13
0x1801a1991  sub     r10, rax
0x1801a1994  sar     r10, 1
0x1801a1997  mov     r8, r10
0x1801a199a  mov     rdx, rax
0x1801a199d  lea     rcx, [rbp+1C0h+lpValueName]
0x1801a19a4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801a19a9  lea     rdx, [rbp+1C0h+lpValueName]
0x1801a19b0  cmp     qword ptr [rbp+1C0h+var_C0+8], 7
0x1801a19b8  cmova   rdx, [rbp+1C0h+lpValueName]; lpValueName
0x1801a19c0  mov     [rsp+2C0h+lpcbData], r13; lpcbData
0x1801a19c5  mov     [rsp+2C0h+lpData], r13; unsigned int
0x1801a19ca  xor     r9d, r9d; lpType
0x1801a19cd  xor     r8d, r8d; lpReserved
0x1801a19d0  mov     rcx, [r15+8]; hKey
0x1801a19d4  call    cs:__imp_RegQueryValueExW
0x1801a19da  mov     ebx, eax
0x1801a19dc  lea     rcx, [rbp+1C0h+lpValueName]
0x1801a19e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a19e8  test    ebx, ebx
0x1801a19ea  jnz     loc_1801A1AA3
0x1801a19f0  lea     rdx, [rbp+1C0h+var_90]
0x1801a19f7  mov     rcx, r14
0x1801a19fa  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x1801a19ff  cmp     qword ptr [rax+18h], 7
0x1801a1a04  jbe     short loc_1801A1A09
0x1801a1a06  mov     rax, [rax]
0x1801a1a09  mov     rdx, rax; lpValueName
0x1801a1a0c  mov     rcx, [r15+8]; hKey
0x1801a1a10  call    cs:__imp_RegDeleteValueW
0x1801a1a16  mov     rcx, [rbp+1C8h]; this
0x1801a1a1d  test    eax, eax
0x1801a1a1f  jz      short loc_1801A1A35
0x1801a1a21  mov     r9d, eax; char *
0x1801a1a24  lea     r8, aPcshellTwinuiS_11; "pcshell\\twinui\\startupappmonitor\\lib"...
0x1801a1a2b  mov     edx, 148h; void *
0x1801a1a30  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1801a1a35  lea     rcx, [rbp+1C0h+var_90]
0x1801a1a3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a1a41  mov     eax, [r15+38h]
0x1801a1a45  mov     dword ptr [rsp+2C0h+Data], eax
0x1801a1a49  lea     rdx, [rbp+1C0h+Src]
0x1801a1a50  cmp     qword ptr [rbp+1C0h+var_A0+8], 7
0x1801a1a58  cmova   rdx, [rbp+1C0h+Src]; lpValueName
0x1801a1a60  mov     ebx, 4
0x1801a1a65  mov     dword ptr [rsp+2C0h+lpcbData], ebx; cbData
0x1801a1a69  lea     rax, [rsp+2C0h+Data]
0x1801a1a6e  mov     [rsp+2C0h+lpData], rax; unsigned int
0x1801a1a73  mov     r9d, ebx; dwType
0x1801a1a76  xor     r8d, r8d; Reserved
0x1801a1a79  mov     rcx, [r15+8]; hKey
0x1801a1a7d  call    cs:__imp_RegSetValueExW
0x1801a1a83  mov     rcx, [rbp+1C8h]; this
0x1801a1a8a  test    eax, eax
0x1801a1a8c  jz      short loc_1801A1AA8
0x1801a1a8e  mov     r9d, eax; char *
0x1801a1a91  lea     r8, aPcshellTwinuiS_11; "pcshell\\twinui\\startupappmonitor\\lib"...
0x1801a1a98  mov     edx, 14Bh; void *
0x1801a1a9d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1801a1aa3  mov     ebx, 4
0x1801a1aa8  lea     rdx, [rbp+1C0h+Src]
0x1801a1aaf  cmp     qword ptr [rbp+1C0h+var_A0+8], 7
0x1801a1ab7  cmova   rdx, [rbp+1C0h+Src]; lpValueName
0x1801a1abf  mov     [rsp+2C0h+lpcbData], r13; lpcbData
0x1801a1ac4  mov     [rsp+2C0h+lpData], r13; int
0x1801a1ac9  xor     r9d, r9d; lpType
0x1801a1acc  xor     r8d, r8d; lpReserved
0x1801a1acf  mov     rcx, [r15+8]; hKey
0x1801a1ad3  call    cs:__imp_RegQueryValueExW
0x1801a1ad9  cmp     eax, 2
0x1801a1adc  jnz     loc_1801A1D9E
0x1801a1ae2  mov     rcx, rsi; struct std::filesystem::directory_entry *
0x1801a1ae5  call    ?IsValidStartupAppFile@StartupFolderNotification@@CA_NAEBVdirectory_entry@filesystem@std@@@Z; StartupFolderNotification::IsValidStartupAppFile(std::filesystem::directory_entry const &)
0x1801a1aea  test    al, al
0x1801a1aec  jz      loc_1801A1D9E
0x1801a1af2  test    r12b, r12b
0x1801a1af5  jz      loc_1801A1D56
0x1801a1afb  lea     rdx, [rbp+1C0h+var_70]
0x1801a1b02  mov     rcx, r14
0x1801a1b05  call    ?filename@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::filename(void)
0x1801a1b0a  nop
0x1801a1b0b  xorps   xmm0, xmm0
0x1801a1b0e  movups  [rbp+1C0h+var_90], xmm0
0x1801a1b15  xorps   xmm1, xmm1
0x1801a1b18  movdqu  [rbp+1C0h+var_80], xmm1
0x1801a1b20  mov     r8, [rax+10h]
0x1801a1b24  cmp     qword ptr [rax+18h], 7
0x1801a1b29  jbe     short loc_1801A1B2E
0x1801a1b2b  mov     rax, [rax]
0x1801a1b2e  mov     rdx, rax
0x1801a1b31  lea     rcx, [rbp+1C0h+var_90]
0x1801a1b38  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1801a1b3d  nop
0x1801a1b3e  lea     rcx, [rbp+1C0h+var_70]
0x1801a1b45  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801a1b4a  xorps   xmm0, xmm0
0x1801a1b4d  movups  xmmword ptr [rbp+1C0h+lpValueName], xmm0
0x1801a1b54  xorps   xmm1, xmm1
0x1801a1b57  movdqu  [rbp+1C0h+var_C0], xmm1
0x1801a1b5f  cmp     qword ptr [rsi+38h], 7
0x1801a1b64  jbe     short loc_1801A1B69
0x1801a1b66  mov     r14, [r14]
0x1801a1b69  mov     r8, [rsi+30h]
0x1801a1b6d  mov     rdx, r14
0x1801a1b70  lea     rcx, [rbp+1C0h+lpValueName]
0x1801a1b77  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1801a1b7c  nop
0x1801a1b7d  mov     rax, [r15+60h]
0x1801a1b81  mov     [rbp+1C0h+var_190], rax
0x1801a1b85  xorps   xmm0, xmm0
0x1801a1b88  movups  [rbp+1C0h+var_188], xmm0
0x1801a1b8c  mov     [rbp+1C0h+var_178], r13
0x1801a1b90  mov     [rbp+1C0h+var_170], r13
0x1801a1b94  lea     rcx, pvData
0x1801a1b9b  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1801a1ba0  mov     r8, rax
0x1801a1ba3  lea     rdx, pvData
0x1801a1baa  lea     rcx, [rbp+1C0h+var_188]
0x1801a1bae  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801a1bb3  nop
0x1801a1bb4  lea     rdx, [rbp+1C0h+var_90]
0x1801a1bbb  lea     rcx, [rbp+1C0h+var_168]
0x1801a1bbf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1801a1bc4  nop
0x1801a1bc5  lea     rdx, [rbp+1C0h+Src]
0x1801a1bcc  lea     rcx, [rbp+1C0h+var_148]
0x1801a1bd0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1801a1bd5  nop
0x1801a1bd6  lea     rdx, [rbp+1C0h+lpValueName]
0x1801a1bdd  lea     rcx, [rbp+1C0h+var_128]
0x1801a1be4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1801a1be9  nop
0x1801a1bea  mov     eax, [r15+38h]
0x1801a1bee  mov     [rbp+1C0h+var_108], eax
0x1801a1bf4  xor     eax, eax
0x1801a1bf6  mov     [rbp+1C0h+var_104], eax
0x1801a1bfc  call    cs:__imp__Query_perf_frequency
0x1801a1c02  mov     rbx, rax
0x1801a1c05  call    cs:__imp__Query_perf_counter
0x1801a1c0b  mov     rcx, rax
0x1801a1c0e  cmp     rbx, 989680h
0x1801a1c15  jnz     short loc_1801A1C20
0x1801a1c17  imul    rax, rcx, 64h ; 'd'
0x1801a1c1b  jmp     loc_1801A1CA4
0x1801a1c20  cmp     rbx, 16E3600h
0x1801a1c27  jnz     short loc_1801A1C86
0x1801a1c29  mov     r9, 0B2F4FC0794908CF3h
0x1801a1c33  mov     rax, r9
0x1801a1c36  imul    rcx
0x1801a1c39  lea     r8, [rcx+rdx]
0x1801a1c3d  sar     r8, 18h
0x1801a1c41  mov     rax, r8
0x1801a1c44  shr     rax, 3Fh
0x1801a1c48  add     r8, rax
0x1801a1c4b  imul    rax, r8, 16E3600h
0x1801a1c52  sub     rcx, rax
0x1801a1c55  imul    rcx, 3B9ACA00h
0x1801a1c5c  mov     rax, r9
0x1801a1c5f  imul    rcx
0x1801a1c62  add     rdx, rcx
0x1801a1c65  sar     rdx, 18h
0x1801a1c69  mov     rax, rdx
0x1801a1c6c  shr     rax, 3Fh
0x1801a1c70  add     rdx, rax
0x1801a1c73  imul    rax, r8, 3B9ACA00h
0x1801a1c7a  add     rdx, rax
0x1801a1c7d  mov     [rbp+1C0h+var_100], rdx
0x1801a1c84  jmp     short loc_1801A1CAB
0x1801a1c86  cqo
0x1801a1c88  idiv    rbx
0x1801a1c8b  mov     rcx, rax
0x1801a1c8e  imul    rax, rdx, 3B9ACA00h
0x1801a1c95  cqo
0x1801a1c97  idiv    rbx
0x1801a1c9a  imul    rcx, 3B9ACA00h
0x1801a1ca1  add     rax, rcx
0x1801a1ca4  mov     [rbp+1C0h+var_100], rax
0x1801a1cab  lea     rdx, [r15+18h]
0x1801a1caf  xorps   xmm0, xmm0
0x1801a1cb2  movups  [rbp+1C0h+var_F8], xmm0
0x1801a1cb9  mov     [rbp+1C0h+var_E8], r13
0x1801a1cc0  mov     [rbp+1C0h+var_E0], r13
0x1801a1cc7  cmp     qword ptr [r15+30h], 7
  ... truncated ...
```
