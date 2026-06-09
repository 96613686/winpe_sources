# MergeSdbp_RemoveUnusedSdbRegistrationFiles(void)

- ea: `0x1400238c0`
- end: `0x1400242a5`
- name: `?MergeSdbp_RemoveUnusedSdbRegistrationFiles@@YAKXZ`
- size: `2533`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140024958`

## callees

- `0x1400018b0`
- `0x14001008c`
- `0x140020cb8`
- `0x140020d40`
- `0x140020f9c`
- `0x140021c68`
- `0x140021db4`
- `0x140021ee4`
- `0x140021f6c`
- `0x140022210`
- `0x1400238c0`
- `0x140024510`
- `0x14002d660`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140023978`
- `ADVAPI32!RegOpenKeyExW` at `0x140023a8f`
- `ADVAPI32!RegOpenKeyExW` at `0x140023978`
- `ADVAPI32!RegOpenKeyExW` at `0x140023a8f`
- `ADVAPI32!RegEnumKeyExW` at `0x140023a61`
- `ADVAPI32!RegEnumKeyExW` at `0x140023a61`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400239fc`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400239fc`
- `ADVAPI32!RegCloseKey` at `0x140023997`
- `ADVAPI32!RegCloseKey` at `0x140023bf5`
- `ADVAPI32!RegCloseKey` at `0x140023c79`
- `ADVAPI32!RegCloseKey` at `0x140023d8f`
- `ADVAPI32!RegCloseKey` at `0x140023da0`
- `ADVAPI32!RegCloseKey` at `0x140023df6`
- `ADVAPI32!RegCloseKey` at `0x140023e21`
- `ADVAPI32!RegCloseKey` at `0x140023e9f`
- `ADVAPI32!RegCloseKey` at `0x140024209`
- `ADVAPI32!RegCloseKey` at `0x140023997`
- `ADVAPI32!RegCloseKey` at `0x140023bf5`
- `ADVAPI32!RegCloseKey` at `0x140023c79`
- `ADVAPI32!RegCloseKey` at `0x140023d8f`
- `ADVAPI32!RegCloseKey` at `0x140023da0`
- `ADVAPI32!RegCloseKey` at `0x140023df6`
- `ADVAPI32!RegCloseKey` at `0x140023e21`
- `ADVAPI32!RegCloseKey` at `0x140023e9f`
- `ADVAPI32!RegCloseKey` at `0x140024209`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140023c25`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140023c25`
- `ADVAPI32!RegDeleteKeyW` at `0x140023c3f`
- `ADVAPI32!RegDeleteKeyW` at `0x140023c3f`
- `KERNEL32!GetLastError` at `0x140023ba9`
- `KERNEL32!GetLastError` at `0x140023fa4`
- `KERNEL32!GetLastError` at `0x140024000`
- `KERNEL32!GetLastError` at `0x1400240ed`
- `KERNEL32!GetLastError` at `0x140023ba9`
- `KERNEL32!GetLastError` at `0x140023fa4`
- `KERNEL32!GetLastError` at `0x140024000`
- `KERNEL32!GetLastError` at `0x1400240ed`
- `KERNEL32!DeleteFileW` at `0x140023f9a`
- `KERNEL32!DeleteFileW` at `0x140023f9a`
- `KERNEL32!GetProcessHeap` at `0x1400239a3`
- `KERNEL32!GetProcessHeap` at `0x140023bb1`
- `KERNEL32!GetProcessHeap` at `0x140023c5a`
- `KERNEL32!GetProcessHeap` at `0x140023c85`
- `KERNEL32!GetProcessHeap` at `0x140023d5a`
- `KERNEL32!GetProcessHeap` at `0x140023dac`
- `KERNEL32!GetProcessHeap` at `0x140023e02`
- `KERNEL32!GetProcessHeap` at `0x140023e2d`
- `KERNEL32!GetProcessHeap` at `0x140023e80`
- `KERNEL32!GetProcessHeap` at `0x140023eab`
- `KERNEL32!GetProcessHeap` at `0x140023ef7`
- `KERNEL32!GetProcessHeap` at `0x140023f1b`
- `KERNEL32!GetProcessHeap` at `0x140023fd7`
- `KERNEL32!GetProcessHeap` at `0x140024007`
- `KERNEL32!GetProcessHeap` at `0x140024035`
- `KERNEL32!GetProcessHeap` at `0x140024098`
- `KERNEL32!GetProcessHeap` at `0x1400240ad`
- `KERNEL32!GetProcessHeap` at `0x1400240d1`
- `KERNEL32!GetProcessHeap` at `0x140024147`
- `KERNEL32!GetProcessHeap` at `0x14002419f`
- `KERNEL32!GetProcessHeap` at `0x14002424b`
- `KERNEL32!GetProcessHeap` at `0x1400239a3`
- `KERNEL32!GetProcessHeap` at `0x140023bb1`
- `KERNEL32!GetProcessHeap` at `0x140023c5a`
- `KERNEL32!GetProcessHeap` at `0x140023c85`
- `KERNEL32!GetProcessHeap` at `0x140023d5a`
- `KERNEL32!GetProcessHeap` at `0x140023dac`
- `KERNEL32!GetProcessHeap` at `0x140023e02`
- `KERNEL32!GetProcessHeap` at `0x140023e2d`
- `KERNEL32!GetProcessHeap` at `0x140023e80`
- `KERNEL32!GetProcessHeap` at `0x140023eab`
- `KERNEL32!GetProcessHeap` at `0x140023ef7`
- `KERNEL32!GetProcessHeap` at `0x140023f1b`
- `KERNEL32!GetProcessHeap` at `0x140023fd7`
- `KERNEL32!GetProcessHeap` at `0x140024007`
- `KERNEL32!GetProcessHeap` at `0x140024035`
- `KERNEL32!GetProcessHeap` at `0x140024098`
- `KERNEL32!GetProcessHeap` at `0x1400240ad`
- `KERNEL32!GetProcessHeap` at `0x1400240d1`
- `KERNEL32!GetProcessHeap` at `0x140024147`
- `KERNEL32!GetProcessHeap` at `0x14002419f`
- `KERNEL32!GetProcessHeap` at `0x14002424b`
- `KERNEL32!FindFirstFileExW` at `0x140023d10`
- `KERNEL32!FindFirstFileExW` at `0x140023d10`
- `KERNEL32!FindClose` at `0x140023d4e`
- `KERNEL32!FindClose` at `0x140023f0f`
- `KERNEL32!FindClose` at `0x140024029`
- `KERNEL32!FindClose` at `0x1400240c5`
- `KERNEL32!FindClose` at `0x14002413b`
- `KERNEL32!FindClose` at `0x140023d4e`
- `KERNEL32!FindClose` at `0x140023f0f`
- `KERNEL32!FindClose` at `0x140024029`
- `KERNEL32!FindClose` at `0x1400240c5`
- `KERNEL32!FindClose` at `0x14002413b`
- `KERNEL32!FindNextFileW` at `0x140023ff2`
- `KERNEL32!FindNextFileW` at `0x140023ff2`
- `KERNEL32!SetLastError` at `0x140023bc7`
- `KERNEL32!SetLastError` at `0x140023bc7`
- `KERNEL32!HeapFree` at `0x1400239b1`
- `KERNEL32!HeapFree` at `0x140023bbf`
- `KERNEL32!HeapFree` at `0x140023c68`
- `KERNEL32!HeapFree` at `0x140023c93`
- `KERNEL32!HeapFree` at `0x140023d68`
- `KERNEL32!HeapFree` at `0x140023dba`
- `KERNEL32!HeapFree` at `0x140023e10`
- `KERNEL32!HeapFree` at `0x140023e3b`
- `KERNEL32!HeapFree` at `0x140023e8e`
- `KERNEL32!HeapFree` at `0x140023eb9`
- `KERNEL32!HeapFree` at `0x140023f05`
- `KERNEL32!HeapFree` at `0x140023f29`
- `KERNEL32!HeapFree` at `0x140023fe5`
- `KERNEL32!HeapFree` at `0x140024015`
- `KERNEL32!HeapFree` at `0x140024043`
- `KERNEL32!HeapFree` at `0x1400240a6`
- `KERNEL32!HeapFree` at `0x1400240bb`
- `KERNEL32!HeapFree` at `0x1400240df`
- `KERNEL32!HeapFree` at `0x140024155`
- `KERNEL32!HeapFree` at `0x1400241ad`
- `KERNEL32!HeapFree` at `0x140024259`
- `KERNEL32!HeapFree` at `0x1400239b1`
- `KERNEL32!HeapFree` at `0x140023bbf`
- `KERNEL32!HeapFree` at `0x140023c68`
- `KERNEL32!HeapFree` at `0x140023c93`
- `KERNEL32!HeapFree` at `0x140023d68`
- `KERNEL32!HeapFree` at `0x140023dba`
- `KERNEL32!HeapFree` at `0x140023e10`
- `KERNEL32!HeapFree` at `0x140023e3b`
- `KERNEL32!HeapFree` at `0x140023e8e`
- `KERNEL32!HeapFree` at `0x140023eb9`
- `KERNEL32!HeapFree` at `0x140023f05`
- `KERNEL32!HeapFree` at `0x140023f29`
- `KERNEL32!HeapFree` at `0x140023fe5`
- `KERNEL32!HeapFree` at `0x140024015`
- `KERNEL32!HeapFree` at `0x140024043`
- `KERNEL32!HeapFree` at `0x1400240a6`
- `KERNEL32!HeapFree` at `0x1400240bb`
- `KERNEL32!HeapFree` at `0x1400240df`
- `KERNEL32!HeapFree` at `0x140024155`
- `KERNEL32!HeapFree` at `0x1400241ad`
- `KERNEL32!HeapFree` at `0x140024259`
- `msvcrt!wcsrchr` at `0x140023ecf`
- `msvcrt!wcsrchr` at `0x140023ecf`
- `msvcrt!_wcsicmp` at `0x140023f56`
- `msvcrt!_wcsicmp` at `0x140023f56`

## string_xrefs

- `0x140024225`: `Failed to format the reg key path for sdb merge target key (%d)`
- `0x140023d78`: `Failed to open sdb merge file key (%d)`
- `0x140023ddb`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x140023e69`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x140023ee7`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x140023fc5`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x14002407c`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x14002411f`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x140024182`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x1400241c9`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x1400241f0`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x140024232`: `MergeSdbp_RemoveUnusedSdbRegistrationFiles`
- `0x140023dce`: `Failed to open sdb merge source key (%d)`
- `0x140023e57`: `Failed to delete invalid source sdb value (%d)`
- `0x140024175`: `Failed to create and expand apppatch\MergeSdbFiles path merge pattern (%d)`
- `0x140023e48`: `Failed to delete invalid source sdb key (%d)`
- `0x140023eda`: `Search returned unexpected directory.`
- `0x140023fb8`: `DeleteFileW failed to delete sdb file (%d)`
- `0x14002406f`: `Failed to build full path for sdb to delete (%d)`
- `0x140023936`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`

## pseudocode

```c
__int64 __fastcall MergeSdbp_RemoveUnusedSdbRegistrationFiles(__int64 a1)
{
  __int64 v1; // rcx
  wchar_t *v2; // r15
  DWORD v3; // r13d
  __int64 v4; // r12
  __int64 *v5; // r14
  __int64 v6; // r8
  int v7; // eax
  unsigned int v8; // edi
  WCHAR *v9; // rbx
  LSTATUS v10; // eax
  HANDLE ProcessHeap; // rax
  WCHAR *v12; // rdi
  LSTATUS v13; // eax
  LSTATUS v14; // esi
  LSTATUS v15; // eax
  __int64 *v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // rax
  LPWSTR v19; // r15
  DWORD LastError; // esi
  HANDLE v21; // rax
  __int64 **v22; // rsi
  LSTATUS v23; // r15d
  HANDLE v24; // rax
  HANDLE v25; // rax
  int v26; // eax
  WCHAR *v27; // rbx
  WCHAR *FirstFile; // rdi
  wchar_t *v29; // rsi
  HANDLE v30; // rax
  const char *v31; // r9
  __int64 v32; // r8
  HANDLE v33; // rax
  HANDLE v34; // rax
  HANDLE v35; // rax
  const char *v36; // r9
  __int64 v37; // r8
  HANDLE v38; // rax
  HANDLE v39; // rax
  wchar_t *v40; // rax
  __int64 v41; // r8
  HANDLE v42; // rax
  HANDLE v43; // rax
  __int64 ***v44; // r13
  __int64 **i; // r14
  int v46; // eax
  unsigned int v47; // r15d
  LPWSTR v48; // r14
  DWORD v49; // eax
  HANDLE v50; // rax
  HANDLE v51; // rax
  HANDLE v52; // rax
  LPWSTR v54; // r14
  HANDLE v55; // rax
  HANDLE v56; // rax
  HANDLE v57; // rax
  DWORD v58; // esi
  HANDLE v59; // rax
  WCHAR *v60; // rbx
  HANDLE v61; // rax
  HANDLE v62; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR lpName; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *Str; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-78h] BYREF
  HKEY hkey; // [rsp+90h] [rbp-70h] BYREF
  __int64 v72; // [rsp+98h] [rbp-68h] BYREF
  __int64 v73; // [rsp+A0h] [rbp-60h]
  WCHAR *v74; // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v75; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v76; // [rsp+B8h] [rbp-48h]
  _BYTE v77[20]; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v78; // [rsp+D4h] [rbp-2Ch]
  int v79; // [rsp+150h] [rbp+50h]
  __int64 v80; // [rsp+158h] [rbp+58h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+160h] [rbp+60h] BYREF

  v73 = 0;
  v72 = std::_List_alloc<0,std::_List_base_types<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::_Buynode0(
          a1,
          0,
          0);
  v2 = (wchar_t *)&off_1400311A0;
  Str = (wchar_t *)&off_1400311A0;
  v3 = 0;
  do
  {
    v4 = 0;
    v76 = 0;
    v5 = (__int64 *)std::_List_alloc<0,std::_List_base_types<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::_Buynode0(
                      v1,
                      0,
                      0);
    v75 = v5;
    lpSubKey = 0;
    v7 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [71],unsigned short [2],unsigned short const *>(
           &lpSubKey,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
           v6,
           v2);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (v7 & 0x1FFF0000) == 0x70000 )
        v8 = (unsigned __int16)v7;
      AslLogCallPrintf(
        1,
        "MergeSdbp_RemoveUnusedSdbRegistrationFiles",
        391,
        "Failed to format the reg key path for sdb merge target key (%d)",
        v8);
      v9 = (WCHAR *)lpSubKey;
      goto LABEL_125;
    }
    hKey = 0;
    v9 = (WCHAR *)lpSubKey;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Bu, &hKey);
    v8 = v10;
    if ( v10 )
    {
      if ( v10 == 2 )
      {
        if ( hKey )
          RegCloseKey(hKey);
        if ( v9 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v9);
        }
        goto LABEL_42;
      }
      v31 = "Failed to open sdb merge file key (%d)";
      v32 = 405;
      goto LABEL_119;
    }
    cbMaxSubKeyLen = 0;
    v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v8 = v10;
    if ( v10 )
    {
      v31 = "RegQueryInfoKeyW failed for merge target key (%d)";
      v32 = 423;
LABEL_119:
      LODWORD(phkResult) = v10;
      AslLogCallPrintf(1, "MergeSdbp_RemoveUnusedSdbRegistrationFiles", v32, v31, phkResult);
      if ( hKey )
        RegCloseKey(hKey);
LABEL_125:
      if ( v9 )
      {
        v62 = GetProcessHeap();
        HeapFree(v62, 0, v9);
      }
      goto LABEL_127;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpName,
      0,
      ++cbMaxSubKeyLen);
    v12 = lpName;
    if ( !lpName )
    {
LABEL_52:
      if ( hKey )
        RegCloseKey(hKey);
      if ( v9 )
      {
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v9);
      }
      v8 = 14;
      goto LABEL_127;
    }
    while ( 1 )
    {
      cchName = cbMaxSubKeyLen;
      v13 = RegEnumKeyExW(hKey, v3, v12, &cchName, 0, 0, 0, 0);
      v14 = v13;
      if ( v13 )
        break;
      hkey = 0;
      v15 = RegOpenKeyExW(hKey, v12, 0, 0x20019u, &hkey);
      v14 = v15;
      if ( v15 )
      {
        AslLogCallPrintf(
          1,
          "MergeSdbp_RemoveUnusedSdbRegistrationFiles",
          456,
          "Failed to open sdb merge source key (%d)",
          v15);
        if ( hkey )
          RegCloseKey(hkey);
        goto LABEL_59;
      }
      memset_0(v77, 0, 0x90u);
      Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v77);
      v79 = 0;
      v80 = 0;
      if ( (unsigned int)Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry(
                           (Pca::MergeSdb::Utils::RegistrationInfo *)v77,
                           hkey) )
      {
LABEL_21:
        v18 = std::_List_buy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Buynode<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v16,
                v5,
                v5[1],
                &lpName);
        if ( v4 == 0xAAAAAAAAAAAAAA9LL )
          goto LABEL_129;
        v76 = ++v4;
        v5[1] = v18;
      }
      else
      {
        v16 = (__int64 *)&off_1400311A0;
        do
        {
          if ( v16[1] == v78.m128i_i64[0] && v16[2] == _mm_srli_si128(v78, 8).m128i_u64[0] )
            goto LABEL_21;
          v16 += 3;
        }
        while ( v16 != &qword_1400311E8 );
        v17 = v72;
        v18 = std::_List_buy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Buynode<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v16,
                v72,
                *(_QWORD *)(v72 + 8),
                &lpName);
        if ( v73 == 0xAAAAAAAAAAAAAA9LL )
LABEL_129:
          std::_Xlength_error("list<T> too long");
        ++v73;
        *(_QWORD *)(v17 + 8) = v18;
      }
      **(_QWORD **)(v18 + 8) = v18;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v74,
        0,
        cbMaxSubKeyLen);
      v12 = v74;
      v19 = lpName;
      if ( lpName )
      {
        LastError = GetLastError();
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v19);
        SetLastError(LastError);
      }
      lpName = v12;
      v74 = 0;
      Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)v77);
      if ( !v12 )
      {
        if ( hkey )
          RegCloseKey(hkey);
        goto LABEL_52;
      }
      if ( hkey )
        RegCloseKey(hkey);
      ++v3;
    }
    if ( v13 != 259 )
    {
      AslLogCallPrintf(1, "MergeSdbp_RemoveUnusedSdbRegistrationFiles", 491, "Failed to enum reg key (%d)", v13);
LABEL_59:
      if ( v12 )
      {
        v34 = GetProcessHeap();
        HeapFree(v34, 0, v12);
      }
      if ( hKey )
        RegCloseKey(hKey);
      if ( v9 )
      {
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v9);
      }
      v8 = v14;
      goto LABEL_127;
    }
    v22 = (__int64 **)*v5;
    v3 = 0;
    while ( v22 != (__int64 **)v5 )
    {
      v23 = RegDeleteKeyValueW(hKey, 0, (LPCWSTR)v22[2]);
      if ( v23 )
      {
        v36 = "Failed to delete invalid source sdb value (%d)";
        v37 = 503;
LABEL_68:
        LODWORD(phkResulta) = v23;
        AslLogCallPrintf(1, "MergeSdbp_RemoveUnusedSdbRegistrationFiles", v37, v36, phkResulta);
        if ( v12 )
        {
          v38 = GetProcessHeap();
          HeapFree(v38, 0, v12);
        }
        if ( hKey )
          RegCloseKey(hKey);
        if ( v9 )
        {
          v39 = GetProcessHeap();
          HeapFree(v39, 0, v9);
        }
        v8 = v23;
LABEL_127:
        std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v75);
LABEL_128:
        std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v72);
        return v8;
      }
      v23 = RegDeleteKeyW(hKey, (LPCWSTR)v22[2]);
      if ( v23 )
      {
        v36 = "Failed to delete invalid source sdb key (%d)";
        v37 = 509;
        goto LABEL_68;
      }
      v22 = (__int64 **)*v22;
    }
    if ( v12 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v12);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v9 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v9);
    }
    v2 = Str;
LABEL_42:
    std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v75);
    v2 += 12;
    Str = v2;
  }
  while ( v2 != (wchar_t *)&qword_1400311E8 );
  lpSubKey = 0;
  v26 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
          L"%SYSTEMROOT%\\AppPatch\\MergeSdbFiles\\????????????????.*.sdb",
          &lpSubKey);
  v8 = v26;
  if ( v26 < 0 )
  {
    if ( (v26 & 0x1FFF0000) == 0x70000 )
      v8 = (unsigned __int16)v26;
    AslLogCallPrintf(
      1,
      "MergeSdbp_RemoveUnusedSdbRegistrationFiles",
      524,
      "Failed to create and expand apppatch\\MergeSdbFiles path merge pattern (%d)",
      v8);
    v60 = (WCHAR *)lpSubKey;
    if ( lpSubKey )
    {
      v61 = GetProcessHeap();
      HeapFree(v61, 0, v60);
    }
    goto LABEL_128;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v27 = (WCHAR *)lpSubKey;
  FirstFile = (WCHAR *)FindFirstFileExW(lpSubKey, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  v74 = FirstFile;
  if ( (unsigned __int64)FirstFile - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v58 = GetLastError();
    if ( !v58 )
      v58 = 1;
    if ( ((v58 - 2) & 0xFFFFFFEF) != 0 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdbp_RemoveUnusedSdbRegistrationFiles",
        543,
        "FindFirstFileExW failed to search AppPatch\\MergeSdbFiles for registered sdb files (%d)",
        v58);
      if ( (unsigned __int64)FirstFile - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        FindClose(FirstFile);
      if ( v27 )
      {
        v59 = GetProcessHeap();
        HeapFree(v59, 0, v27);
      }
      v8 = v58;
      goto LABEL_128;
    }
  }
  else
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &Str,
      v27,
      -1);
    v29 = Str;
    if ( !Str )
    {
      FindClose(FirstFile);
      if ( v27 )
      {
        v30 = GetProcessHeap();
        HeapFree(v30, 0, v27);
      }
      v8 = 14;
      goto LABEL_128;
    }
    v40 = wcsrchr(Str, 0x5Cu);
    if ( !v40 )
    {
      AslLogCallPrintf(1, "MergeSdbp_RemoveUnusedSdbRegistrationFiles", 557, "Search returned unexpected directory.");
      v42 = GetProcessHeap();
      HeapFree(v42, 0, v29);
      FindClose(FirstFile);
      if ( v27 )
      {
        v43 = GetProcessHeap();
        HeapFree(v43, 0, v27);
      }
      v8 = 1359;
      goto LABEL_128;
    }
    v40[1] = 0;
    v44 = (__int64 ***)v72;
    while ( 2 )
    {
      for ( i = *v44; i != (__int64 **)v44; i = (__int64 **)*i )
      {
        if ( !_wcsicmp((const wchar_t *)i[2], FindFileData.cFileName) )
          goto LABEL_91;
      }
      lpName = 0;
      v46 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [2],unsigned short [260]>(
              &lpName,
              &Str,
              v41,
              FindFileData.cFileName);
      v47 = v46;
      if ( v46 < 0 )
      {
        if ( (v46 & 0x1FFF0000) == 0x70000 )
          v47 = (unsigned __int16)v46;
        AslLogCallPrintf(
          1,
          "MergeSdbp_RemoveUnusedSdbRegistrationFiles",
          581,
          "Failed to build full path for sdb to delete (%d)",
          v47);
        v54 = lpName;
        if ( lpName )
        {
          v55 = GetProcessHeap();
          HeapFree(v55, 0, v54);
        }
        v56 = GetProcessHeap();
        HeapFree(v56, 0, v29);
        FindClose(FirstFile);
        if ( v27 )
        {
          v57 = GetProcessHeap();
          HeapFree(v57, 0, v27);
        }
        v8 = v47;
        goto LABEL_128;
      }
      v48 = lpName;
      if ( !DeleteFileW(lpName) )
      {
        v49 = GetLastError();
        if ( !v49 )
          v49 = 1;
        AslLogCallPrintf(
          1,
          "MergeSdbp_RemoveUnusedSdbRegistrationFiles",
          587,
          "DeleteFileW failed to delete sdb file (%d)",
          v49);
      }
      if ( v48 )
      {
        v50 = GetProcessHeap();
        HeapFree(v50, 0, v48);
      }
LABEL_91:
      if ( FindNextFileW(FirstFile, &FindFileData) )
        continue;
      break;
    }
    GetLastError();
    v51 = GetProcessHeap();
    HeapFree(v51, 0, v29);
  }
  if ( (unsigned __int64)FirstFile - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFile);
  if ( v27 )
  {
    v52 = GetProcessHeap();
    HeapFree(v52, 0, v27);
  }
  std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v72);
  return 0;
}

```

## disassembly

```asm
0x1400238c0  push    rbp
0x1400238c2  push    rbx
0x1400238c3  push    rsi
0x1400238c4  push    rdi
0x1400238c5  push    r12
0x1400238c7  push    r13
0x1400238c9  push    r14
0x1400238cb  push    r15
0x1400238cd  lea     rbp, [rsp-2C8h]
0x1400238d5  sub     rsp, 3C8h
0x1400238dc  mov     rax, cs:__security_cookie
0x1400238e3  xor     rax, rsp
0x1400238e6  mov     [rbp+300h+var_50], rax
0x1400238ed  mov     [rbp+300h+var_360], 0
0x1400238f5  xor     r8d, r8d
0x1400238f8  xor     edx, edx
0x1400238fa  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::_Buynode0(std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *)
0x1400238ff  mov     [rbp+300h+var_368], rax
0x140023903  lea     r15, off_1400311A0; "sysmain.sdb"
0x14002390a  mov     [rbp+300h+Str], r15
0x14002390e  mov     esi, 1
0x140023913  xor     r13d, r13d
0x140023916  mov     r12, r13
0x140023919  mov     [rbp+300h+var_348], r13
0x14002391d  xor     r8d, r8d
0x140023920  xor     edx, edx
0x140023922  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::_Buynode0(std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *)
0x140023927  mov     r14, rax
0x14002392a  mov     [rbp+300h+var_350], rax
0x14002392e  mov     [rsp+400h+lpSubKey], r13
0x140023933  mov     r9, r15
0x140023936  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14002393d  lea     rcx, [rsp+400h+lpSubKey]
0x140023942  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0EH@G$$BY01GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0EH@$$CBGAEAY01$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [71],ushort [2],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[71],ushort const (&)[2],ushort const * const &)
0x140023947  mov     edi, eax
0x140023949  test    eax, eax
0x14002394b  js      loc_140024212
0x140023951  mov     [rsp+400h+hKey], r13
0x140023956  lea     rax, [rsp+400h+hKey]
0x14002395b  mov     [rsp+400h+phkResult], rax; phkResult
0x140023960  mov     r9d, 2001Bh; samDesired
0x140023966  xor     r8d, r8d; ulOptions
0x140023969  mov     rbx, [rsp+400h+lpSubKey]
0x14002396e  mov     rdx, rbx; lpSubKey
0x140023971  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140023978  call    cs:__imp_RegOpenKeyExW
0x14002397e  mov     edi, eax
0x140023980  test    eax, eax
0x140023982  jz      short loc_1400239BD
0x140023984  cmp     eax, 2
0x140023987  jnz     loc_140023D78
0x14002398d  mov     rcx, [rsp+400h+hKey]; hKey
0x140023992  test    rcx, rcx
0x140023995  jz      short loc_14002399E
0x140023997  call    cs:__imp_RegCloseKey
0x14002399d  nop
0x14002399e  test    rbx, rbx
0x1400239a1  jz      short loc_1400239B8
0x1400239a3  call    cs:__imp_GetProcessHeap
0x1400239a9  mov     rcx, rax; hHeap
0x1400239ac  mov     r8, rbx; lpMem
0x1400239af  xor     edx, edx; dwFlags
0x1400239b1  call    cs:__imp_HeapFree
0x1400239b7  nop
0x1400239b8  jmp     loc_140023CA3
0x1400239bd  mov     [rsp+400h+cbMaxSubKeyLen], r13d
0x1400239c2  mov     [rsp+400h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1400239c7  mov     [rsp+400h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1400239cc  mov     [rsp+400h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1400239d1  mov     [rsp+400h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1400239d6  mov     [rsp+400h+lpcValues], r13; lpcValues
0x1400239db  mov     [rsp+400h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1400239e0  lea     rax, [rsp+400h+cbMaxSubKeyLen]
0x1400239e5  mov     [rsp+400h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1400239ea  mov     [rsp+400h+phkResult], r13; lpcSubKeys
0x1400239ef  xor     r9d, r9d; lpReserved
0x1400239f2  xor     r8d, r8d; lpcchClass
0x1400239f5  xor     edx, edx; lpClass
0x1400239f7  mov     rcx, [rsp+400h+hKey]; hKey
0x1400239fc  call    cs:__imp_RegQueryInfoKeyW
0x140023a02  mov     edi, eax
0x140023a04  test    eax, eax
0x140023a06  jnz     loc_1400241DF
0x140023a0c  mov     eax, [rsp+400h+cbMaxSubKeyLen]
0x140023a10  add     eax, esi
0x140023a12  mov     [rsp+400h+cbMaxSubKeyLen], eax
0x140023a16  mov     r8d, eax
0x140023a19  xor     edx, edx
0x140023a1b  lea     rcx, [rsp+400h+lpName]
0x140023a20  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140023a25  nop
0x140023a26  mov     rdi, [rsp+400h+lpName]
0x140023a2b  test    rdi, rdi
0x140023a2e  jz      loc_140023D96
0x140023a34  xor     r15d, r15d
0x140023a37  mov     eax, [rsp+400h+cbMaxSubKeyLen]
0x140023a3b  mov     [rbp+300h+cchName], eax
0x140023a3e  mov     [rsp+400h+lpcValues], r15; lpftLastWriteTime
0x140023a43  mov     [rsp+400h+lpcbMaxClassLen], r15; lpcchClass
0x140023a48  mov     [rsp+400h+lpcbMaxSubKeyLen], r15; lpClass
0x140023a4d  mov     [rsp+400h+phkResult], r15; lpReserved
0x140023a52  lea     r9, [rbp+300h+cchName]; lpcchName
0x140023a56  mov     r8, rdi; lpName
0x140023a59  mov     edx, r13d; dwIndex
0x140023a5c  mov     rcx, [rsp+400h+hKey]; hKey
0x140023a61  call    cs:__imp_RegEnumKeyExW
0x140023a67  mov     esi, eax
0x140023a69  test    eax, eax
0x140023a6b  jnz     loc_140023C03
0x140023a71  mov     [rbp+300h+hkey], r15
0x140023a75  lea     rax, [rbp+300h+hkey]
0x140023a79  mov     [rsp+400h+phkResult], rax; phkResult
0x140023a7e  mov     r9d, 20019h; samDesired
0x140023a84  xor     r8d, r8d; ulOptions
0x140023a87  mov     rdx, rdi; lpSubKey
0x140023a8a  mov     rcx, [rsp+400h+hKey]; hKey
0x140023a8f  call    cs:__imp_RegOpenKeyExW
0x140023a95  mov     esi, eax
0x140023a97  test    eax, eax
0x140023a99  jnz     loc_140023DCA
0x140023a9f  xor     edx, edx; Val
0x140023aa1  mov     r8d, 90h; Size
0x140023aa7  lea     rcx, [rbp+300h+var_340]; void *
0x140023aab  call    memset_0
0x140023ab0  lea     rcx, [rbp+300h+var_340]; this
0x140023ab4  call    ??0SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::SdbFileData(void)
0x140023ab9  mov     [rbp+300h+var_2B0], r15d
0x140023abd  mov     [rbp+300h+var_2A8], r15
0x140023ac1  mov     rdx, [rbp+300h+hkey]; hkey
0x140023ac5  lea     rcx, [rbp+300h+var_340]; this
0x140023ac9  call    ?ReadRegistrationFromRegistry@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKPEAUHKEY__@@@Z; Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry(HKEY__ *)
0x140023ace  test    eax, eax
0x140023ad0  jnz     short loc_140023B4D
0x140023ad2  lea     rcx, off_1400311A0; "sysmain.sdb"
0x140023ad9  movups  xmm1, [rbp+300h+var_32C]
0x140023add  movq    rax, xmm1
0x140023ae2  cmp     [rcx+8], rax
0x140023ae6  jnz     short loc_140023AFC
0x140023ae8  movdqa  xmm0, xmm1
0x140023aec  psrldq  xmm0, 8
0x140023af1  movq    rax, xmm0
0x140023af6  cmp     [rcx+10h], rax
0x140023afa  jz      short loc_140023B4D
0x140023afc  add     rcx, 18h
0x140023b00  lea     rax, qword_1400311E8
0x140023b07  cmp     rcx, rax
0x140023b0a  jnz     short loc_140023ADD
0x140023b0c  lea     r9, [rsp+400h+lpName]
0x140023b11  mov     rdi, [rbp+300h+var_368]
0x140023b15  mov     r8, [rdi+8]
0x140023b19  mov     rdx, rdi
0x140023b1c  call    ??$_Buynode@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$_List_buy@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@1@PEAU21@0$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; std::_List_buy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Buynode<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x140023b21  mov     rcx, 0AAAAAAAAAAAAAA9h
0x140023b2b  mov     rdx, [rbp+300h+var_360]
0x140023b2f  sub     rcx, rdx
0x140023b32  mov     esi, 1
0x140023b37  cmp     rcx, rsi
0x140023b3a  jb      loc_140024298
0x140023b40  add     rdx, rsi
0x140023b43  mov     [rbp+300h+var_360], rdx
0x140023b47  mov     [rdi+8], rax
0x140023b4b  jmp     short loc_140023B84
0x140023b4d  lea     r9, [rsp+400h+lpName]
0x140023b52  mov     r8, [r14+8]
0x140023b56  mov     rdx, r14
0x140023b59  call    ??$_Buynode@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$_List_buy@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@1@PEAU21@0$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; std::_List_buy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Buynode<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x140023b5e  mov     rcx, 0AAAAAAAAAAAAAA9h
0x140023b68  sub     rcx, r12
0x140023b6b  mov     esi, 1
0x140023b70  cmp     rcx, rsi
0x140023b73  jb      loc_140024298
0x140023b79  add     r12, rsi
0x140023b7c  mov     [rbp+300h+var_348], r12
0x140023b80  mov     [r14+8], rax
0x140023b84  mov     rcx, [rax+8]
0x140023b88  mov     [rcx], rax
0x140023b8b  mov     r8d, [rsp+400h+cbMaxSubKeyLen]
0x140023b90  xor     edx, edx
0x140023b92  lea     rcx, [rbp+300h+var_358]
0x140023b96  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140023b9b  mov     rdi, [rbp+300h+var_358]
0x140023b9f  mov     r15, [rsp+400h+lpName]
0x140023ba4  test    r15, r15
0x140023ba7  jz      short loc_140023BCD
0x140023ba9  call    cs:__imp_GetLastError
0x140023baf  mov     esi, eax
0x140023bb1  call    cs:__imp_GetProcessHeap
0x140023bb7  mov     rcx, rax; hHeap
0x140023bba  mov     r8, r15; lpMem
0x140023bbd  xor     edx, edx; dwFlags
0x140023bbf  call    cs:__imp_HeapFree
0x140023bc5  mov     ecx, esi; dwErrCode
0x140023bc7  call    cs:__imp_SetLastError
0x140023bcd  mov     [rsp+400h+lpName], rdi
0x140023bd2  xor     r15d, r15d
0x140023bd5  mov     [rbp+300h+var_358], r15
0x140023bd9  lea     rcx, [rbp+300h+var_340]; this
0x140023bdd  call    ??1SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::~SdbFileData(void)
0x140023be2  nop
0x140023be3  mov     rcx, [rbp+300h+hkey]; hKey
0x140023be7  test    rdi, rdi
0x140023bea  jz      loc_140023D8A
0x140023bf0  test    rcx, rcx
0x140023bf3  jz      short loc_140023BFB
0x140023bf5  call    cs:__imp_RegCloseKey
0x140023bfb  inc     r13d
0x140023bfe  jmp     loc_140023A37
0x140023c03  cmp     esi, 103h
0x140023c09  jnz     loc_1400241B8
0x140023c0f  mov     rsi, [r14]
0x140023c12  xor     r13d, r13d
0x140023c15  cmp     rsi, r14
0x140023c18  jz      short loc_140023C55
0x140023c1a  mov     r8, [rsi+10h]; lpValueName
0x140023c1e  xor     edx, edx; lpSubKey
0x140023c20  mov     rcx, [rsp+400h+hKey]; hKey
0x140023c25  call    cs:__imp_RegDeleteKeyValueW
0x140023c2b  mov     r15d, eax
0x140023c2e  test    eax, eax
0x140023c30  jnz     loc_140023E57
0x140023c36  mov     rdx, [rsi+10h]; lpSubKey
0x140023c3a  mov     rcx, [rsp+400h+hKey]; hKey
0x140023c3f  call    cs:__imp_RegDeleteKeyW
0x140023c45  mov     r15d, eax
0x140023c48  test    eax, eax
0x140023c4a  jnz     loc_140023E48
0x140023c50  mov     rsi, [rsi]
0x140023c53  jmp     short loc_140023C15
0x140023c55  test    rdi, rdi
0x140023c58  jz      short loc_140023C6F
0x140023c5a  call    cs:__imp_GetProcessHeap
0x140023c60  mov     rcx, rax; hHeap
0x140023c63  mov     r8, rdi; lpMem
0x140023c66  xor     edx, edx; dwFlags
0x140023c68  call    cs:__imp_HeapFree
0x140023c6e  nop
0x140023c6f  mov     rcx, [rsp+400h+hKey]; hKey
0x140023c74  test    rcx, rcx
0x140023c77  jz      short loc_140023C80
0x140023c79  call    cs:__imp_RegCloseKey
0x140023c7f  nop
0x140023c80  test    rbx, rbx
0x140023c83  jz      short loc_140023C9A
0x140023c85  call    cs:__imp_GetProcessHeap
0x140023c8b  mov     rcx, rax; hHeap
0x140023c8e  mov     r8, rbx; lpMem
0x140023c91  xor     edx, edx; dwFlags
0x140023c93  call    cs:__imp_HeapFree
0x140023c99  nop
0x140023c9a  mov     r15, [rbp+300h+Str]
0x140023c9e  mov     esi, 1
0x140023ca3  lea     rcx, [rbp+300h+var_350]
0x140023ca7  call    ??1?$list@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x140023cac  add     r15, 18h
0x140023cb0  mov     [rbp+300h+Str], r15
0x140023cb4  lea     rax, qword_1400311E8
0x140023cbb  cmp     r15, rax
0x140023cbe  jnz     loc_140023916
0x140023cc4  mov     [rsp+400h+lpSubKey], r13
0x140023cc9  lea     rdx, [rsp+400h+lpSubKey]
0x140023cce  lea     rcx, aSystemrootAppp; "%SYSTEMROOT%\\AppPatch\\MergeSdbFiles\\"...
0x140023cd5  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x140023cda  mov     edi, eax
0x140023cdc  test    eax, eax
0x140023cde  js      loc_140024162
0x140023ce4  xor     edx, edx; Val
0x140023ce6  mov     r8d, 250h; Size
0x140023cec  lea     rcx, [rbp+300h+FindFileData]; void *
0x140023cf0  call    memset_0
0x140023cf5  mov     dword ptr [rsp+400h+lpcbMaxSubKeyLen], r13d; dwAdditionalFlags
0x140023cfa  mov     [rsp+400h+phkResult], r13; lpSearchFilter
0x140023cff  xor     r9d, r9d; fSearchOp
0x140023d02  lea     r8, [rbp+300h+FindFileData]; lpFindFileData
0x140023d06  mov     edx, esi; fInfoLevelId
0x140023d08  mov     rbx, [rsp+400h+lpSubKey]
0x140023d0d  mov     rcx, rbx; lpFileName
0x140023d10  call    cs:__imp_FindFirstFileExW
0x140023d16  mov     rdi, rax
0x140023d19  mov     [rbp+300h+var_358], rax
0x140023d1d  dec     rax
0x140023d20  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140023d24  ja      loc_1400240ED
0x140023d2a  or      r8, 0FFFFFFFFFFFFFFFFh
0x140023d2e  mov     rdx, rbx
0x140023d31  lea     rcx, [rbp+300h+Str]
0x140023d35  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140023d3a  mov     rsi, [rbp+300h+Str]
0x140023d3e  mov     [rbp+300h+Str], rsi
0x140023d42  test    rsi, rsi
0x140023d45  jnz     loc_140023EC7
0x140023d4b  mov     rcx, rdi; hFindFile
0x140023d4e  call    cs:__imp_FindClose
0x140023d54  nop
0x140023d55  test    rbx, rbx
0x140023d58  jz      short loc_140023D6E
0x140023d5a  call    cs:__imp_GetProcessHeap
0x140023d60  mov     rcx, rax; hHeap
0x140023d63  mov     r8, rbx; lpMem
0x140023d66  xor     edx, edx; dwFlags
0x140023d68  call    cs:__imp_HeapFree
  ... truncated ...
```
