# MergeSdb_RemoveUnusedSdbFiles

- ea: `0x140027400`
- end: `0x140027c79`
- name: `MergeSdb_RemoveUnusedSdbFiles`
- size: `2169`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140024958`

## callees

- `0x1400018b0`
- `0x14001008c`
- `0x140020cb8`
- `0x140020d40`
- `0x140020f9c`
- `0x140021934`
- `0x140021db4`
- `0x140021f6c`
- `0x140022014`
- `0x140024510`
- `0x1400245b8`
- `0x140027400`
- `0x14002ae60`
- `0x14002c10c`
- `0x14002e3e2`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140027458`
- `ADVAPI32!RegOpenKeyExW` at `0x140027576`
- `ADVAPI32!RegOpenKeyExW` at `0x140027458`
- `ADVAPI32!RegOpenKeyExW` at `0x140027576`
- `ADVAPI32!RegCloseKey` at `0x14002748e`
- `ADVAPI32!RegCloseKey` at `0x1400275b0`
- `ADVAPI32!RegCloseKey` at `0x1400277cb`
- `ADVAPI32!RegCloseKey` at `0x14002780d`
- `ADVAPI32!RegCloseKey` at `0x140027a77`
- `ADVAPI32!RegCloseKey` at `0x140027ab9`
- `ADVAPI32!RegCloseKey` at `0x140027ae5`
- `ADVAPI32!RegCloseKey` at `0x140027b27`
- `ADVAPI32!RegCloseKey` at `0x140027b88`
- `ADVAPI32!RegCloseKey` at `0x140027bca`
- `ADVAPI32!RegCloseKey` at `0x140027c41`
- `ADVAPI32!RegCloseKey` at `0x14002748e`
- `ADVAPI32!RegCloseKey` at `0x1400275b0`
- `ADVAPI32!RegCloseKey` at `0x1400277cb`
- `ADVAPI32!RegCloseKey` at `0x14002780d`
- `ADVAPI32!RegCloseKey` at `0x140027a77`
- `ADVAPI32!RegCloseKey` at `0x140027ab9`
- `ADVAPI32!RegCloseKey` at `0x140027ae5`
- `ADVAPI32!RegCloseKey` at `0x140027b27`
- `ADVAPI32!RegCloseKey` at `0x140027b88`
- `ADVAPI32!RegCloseKey` at `0x140027bca`
- `ADVAPI32!RegCloseKey` at `0x140027c41`
- `KERNEL32!GetLastError` at `0x140027945`
- `KERNEL32!GetLastError` at `0x14002799f`
- `KERNEL32!GetLastError` at `0x1400279bb`
- `KERNEL32!GetLastError` at `0x140027945`
- `KERNEL32!GetLastError` at `0x14002799f`
- `KERNEL32!GetLastError` at `0x1400279bb`
- `KERNEL32!DeleteFileW` at `0x14002793b`
- `KERNEL32!DeleteFileW` at `0x14002793b`
- `KERNEL32!GetProcessHeap` at `0x14002766a`
- `KERNEL32!GetProcessHeap` at `0x140027724`
- `KERNEL32!GetProcessHeap` at `0x140027738`
- `KERNEL32!GetProcessHeap` at `0x14002778f`
- `KERNEL32!GetProcessHeap` at `0x1400277a3`
- `KERNEL32!GetProcessHeap` at `0x1400277db`
- `KERNEL32!GetProcessHeap` at `0x1400278a7`
- `KERNEL32!GetProcessHeap` at `0x140027976`
- `KERNEL32!GetProcessHeap` at `0x1400279a5`
- `KERNEL32!GetProcessHeap` at `0x140027a30`
- `KERNEL32!GetProcessHeap` at `0x140027a44`
- `KERNEL32!GetProcessHeap` at `0x140027a87`
- `KERNEL32!GetProcessHeap` at `0x140027af5`
- `KERNEL32!GetProcessHeap` at `0x140027b98`
- `KERNEL32!GetProcessHeap` at `0x140027c0f`
- `KERNEL32!GetProcessHeap` at `0x14002766a`
- `KERNEL32!GetProcessHeap` at `0x140027724`
- `KERNEL32!GetProcessHeap` at `0x140027738`
- `KERNEL32!GetProcessHeap` at `0x14002778f`
- `KERNEL32!GetProcessHeap` at `0x1400277a3`
- `KERNEL32!GetProcessHeap` at `0x1400277db`
- `KERNEL32!GetProcessHeap` at `0x1400278a7`
- `KERNEL32!GetProcessHeap` at `0x140027976`
- `KERNEL32!GetProcessHeap` at `0x1400279a5`
- `KERNEL32!GetProcessHeap` at `0x140027a30`
- `KERNEL32!GetProcessHeap` at `0x140027a44`
- `KERNEL32!GetProcessHeap` at `0x140027a87`
- `KERNEL32!GetProcessHeap` at `0x140027af5`
- `KERNEL32!GetProcessHeap` at `0x140027b98`
- `KERNEL32!GetProcessHeap` at `0x140027c0f`
- `KERNEL32!FindFirstFileExW` at `0x14002784e`
- `KERNEL32!FindFirstFileExW` at `0x14002784e`
- `KERNEL32!FindClose` at `0x1400278bf`
- `KERNEL32!FindClose` at `0x1400279e4`
- `KERNEL32!FindClose` at `0x140027a5c`
- `KERNEL32!FindClose` at `0x140027aca`
- `KERNEL32!FindClose` at `0x140027b68`
- `KERNEL32!FindClose` at `0x1400278bf`
- `KERNEL32!FindClose` at `0x1400279e4`
- `KERNEL32!FindClose` at `0x140027a5c`
- `KERNEL32!FindClose` at `0x140027aca`
- `KERNEL32!FindClose` at `0x140027b68`
- `KERNEL32!FindNextFileW` at `0x140027991`
- `KERNEL32!FindNextFileW` at `0x140027991`
- `KERNEL32!HeapFree` at `0x140027678`
- `KERNEL32!HeapFree` at `0x140027732`
- `KERNEL32!HeapFree` at `0x140027746`
- `KERNEL32!HeapFree` at `0x14002779d`
- `KERNEL32!HeapFree` at `0x1400277b1`
- `KERNEL32!HeapFree` at `0x1400277e9`
- `KERNEL32!HeapFree` at `0x1400278b5`
- `KERNEL32!HeapFree` at `0x140027984`
- `KERNEL32!HeapFree` at `0x1400279b3`
- `KERNEL32!HeapFree` at `0x140027a3e`
- `KERNEL32!HeapFree` at `0x140027a52`
- `KERNEL32!HeapFree` at `0x140027a95`
- `KERNEL32!HeapFree` at `0x140027b03`
- `KERNEL32!HeapFree` at `0x140027ba6`
- `KERNEL32!HeapFree` at `0x140027c1d`
- `KERNEL32!HeapFree` at `0x140027678`
- `KERNEL32!HeapFree` at `0x140027732`
- `KERNEL32!HeapFree` at `0x140027746`
- `KERNEL32!HeapFree` at `0x14002779d`
- `KERNEL32!HeapFree` at `0x1400277b1`
- `KERNEL32!HeapFree` at `0x1400277e9`
- `KERNEL32!HeapFree` at `0x1400278b5`
- `KERNEL32!HeapFree` at `0x140027984`
- `KERNEL32!HeapFree` at `0x1400279b3`
- `KERNEL32!HeapFree` at `0x140027a3e`
- `KERNEL32!HeapFree` at `0x140027a52`
- `KERNEL32!HeapFree` at `0x140027a95`
- `KERNEL32!HeapFree` at `0x140027b03`
- `KERNEL32!HeapFree` at `0x140027ba6`
- `KERNEL32!HeapFree` at `0x140027c1d`
- `msvcrt!wcsrchr` at `0x14002765f`
- `msvcrt!wcsrchr` at `0x140027899`
- `msvcrt!wcsrchr` at `0x14002765f`
- `msvcrt!wcsrchr` at `0x140027899`
- `msvcrt!_wcsicmp` at `0x140027902`
- `msvcrt!_wcsicmp` at `0x140027902`

## string_xrefs

- `0x140027568`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x140027955`: `DeleteFileW failed to delete sdb file (%d)`
- `0x140027a0a`: `Failed to build full path for sdb to delete (%d)`
- `0x140027475`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x1400274d5`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x140027593`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x1400275f4`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x140027776`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x140027962`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x140027a17`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x140027b48`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x140027bf4`: `MergeSdb_RemoveUnusedSdbFiles`
- `0x140027468`: `RegOpenKeyExW failed to open SdbUpdates key (%d)`
- `0x140027be7`: `Failed to create and expand apppatch path merge pattern (%d)`
- `0x1400274c8`: `Failed to get SdbUpdates redirect values (%d)`
- `0x1400275e7`: `Failed to get ManifestedMergeStubSdbs stub values (%d)`
- `0x140027586`: `RegOpenKeyExW failed to open ManifestedMergeStubSdbs key (%d)`
- `0x140027769`: `Failed to concat stub dir search path (%d)`
- `0x14002744a`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`

## pseudocode

```c
__int64 MergeSdb_RemoveUnusedSdbFiles()
{
  LSTATUS v0; // eax
  __int64 v1; // rcx
  unsigned int v2; // ebx
  unsigned int RegValuesForKey; // eax
  __int64 v5; // rcx
  __int64 *v6; // r15
  int v7; // eax
  __int64 v8; // rcx
  DWORD v9; // edi
  __int64 v10; // rax
  __int64 v11; // r13
  LSTATUS v12; // eax
  __int64 v13; // rcx
  DWORD v14; // eax
  __int64 *v15; // r14
  __int64 *i; // rdi
  __int64 v17; // rax
  __int64 v18; // rdx
  wchar_t *v19; // rbx
  wchar_t *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // esi
  __int64 v26; // rax
  void *v27; // rsi
  HANDLE v28; // rax
  HANDLE v29; // rax
  void *v30; // rdi
  HANDLE v31; // rax
  HANDLE v32; // rax
  void *v33; // rbx
  HANDLE v34; // rax
  __int64 **j; // r14
  char *FirstFile; // rbx
  wchar_t *v37; // rsi
  wchar_t *v38; // rcx
  __int64 v39; // r8
  HANDLE v40; // rax
  _QWORD *v41; // rax
  _QWORD *v42; // rdi
  int v43; // eax
  unsigned int v44; // r13d
  void *v45; // rdi
  DWORD LastError; // eax
  HANDLE v47; // rax
  HANDLE v48; // rax
  void *v49; // rdi
  HANDLE v50; // rax
  HANDLE v51; // rax
  void *v52; // rbx
  HANDLE v53; // rax
  void *v54; // rbx
  HANDLE v55; // rax
  void *v56; // rbx
  HANDLE v57; // rax
  void *v58; // rbx
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v61; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v64[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v65; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+68h] [rbp-98h]
  wchar_t *Str; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v68[3]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v69[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v70[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v71[2]; // [rsp+B0h] [rbp-50h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
         0,
         0x20019u,
         &hKey);
  v2 = v0;
  if ( v0 )
  {
    AslLogCallPrintf(1, "MergeSdb_RemoveUnusedSdbFiles", 636, "RegOpenKeyExW failed to open SdbUpdates key (%d)", v0);
LABEL_3:
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
  v64[1] = 0;
  v64[0] = std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegValue>>::_Buynode0(v1, 0, 0);
  RegValuesForKey = Pca::MergeSdb::Utils::RegUtil::GetRegValuesForKey(v64, hKey);
  v2 = RegValuesForKey;
  if ( RegValuesForKey )
  {
    AslLogCallPrintf(
      1,
      "MergeSdb_RemoveUnusedSdbFiles",
      642,
      "Failed to get SdbUpdates redirect values (%d)",
      RegValuesForKey);
    std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v64);
    goto LABEL_3;
  }
  v66 = 0;
  v6 = (__int64 *)std::_List_alloc<0,std::_List_base_types<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::_Buynode0(
                    v5,
                    0,
                    0);
  v65 = v6;
  v61 = 0;
  v7 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         L"%SYSTEMROOT%\\AppPatch\\????????????????.*.sdb",
         &v61);
  v9 = v7;
  if ( v7 < 0 )
  {
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v7;
    AslLogCallPrintf(
      1,
      "MergeSdb_RemoveUnusedSdbFiles",
      655,
      "Failed to create and expand apppatch path merge pattern (%d)",
      v9);
    goto LABEL_100;
  }
  v10 = std::_List_buy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Buynode<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          v8,
          v6,
          v6[1],
          &v61);
  v11 = 1;
  v66 = 1;
  v6[1] = v10;
  **(_QWORD **)(v10 + 8) = v10;
  phkResult = 0;
  v12 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
          0,
          0x20019u,
          &phkResult);
  v9 = v12;
  if ( v12 )
  {
    AslLogCallPrintf(
      1,
      "MergeSdb_RemoveUnusedSdbFiles",
      671,
      "RegOpenKeyExW failed to open ManifestedMergeStubSdbs key (%d)",
      v12);
LABEL_11:
    if ( phkResult )
      RegCloseKey(phkResult);
LABEL_100:
    v58 = v61;
    if ( v61 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v58);
    }
    std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v65);
    std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v64);
    if ( hKey )
      RegCloseKey(hKey);
    return v9;
  }
  v68[1] = 0;
  v68[0] = std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegValue>>::_Buynode0(v13, 0, 0);
  v14 = Pca::MergeSdb::Utils::RegUtil::GetRegValuesForKey(v68, phkResult);
  v9 = v14;
  if ( v14 )
  {
    AslLogCallPrintf(
      1,
      "MergeSdb_RemoveUnusedSdbFiles",
      677,
      "Failed to get ManifestedMergeStubSdbs stub values (%d)",
      v14);
LABEL_15:
    std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v68);
    goto LABEL_11;
  }
  v15 = (__int64 *)v68[0];
  for ( i = *(__int64 **)v68[0]; i != v15; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i + 6) <= 3u || (v17 = i[2], v18 = v17 + 12, !v17) )
      v18 = 0;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &Str,
      v18,
      -1);
    v19 = Str;
    Str = 0;
    if ( !v19 )
    {
LABEL_81:
      std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v68);
      if ( phkResult )
        RegCloseKey(phkResult);
      v54 = v61;
      if ( v61 )
      {
        v55 = GetProcessHeap();
        HeapFree(v55, 0, v54);
      }
      std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v65);
      std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v64);
      if ( hKey )
        RegCloseKey(hKey);
      return 14;
    }
    v20 = wcsrchr(v19, 0x5Cu);
    if ( v20 )
    {
      v20[1] = 0;
      lpMem = 0;
      v21 = -1;
      v22 = -1;
      do
        ++v22;
      while ( aSdb_0[v22] );
      do
        ++v21;
      while ( v19[v21] );
      v69[0] = L"????????????????.*.sdb";
      v69[1] = v22;
      v70[0] = v19;
      v70[1] = v21;
      v71[0] = 0;
      v71[1] = 0;
      v23 = wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
              &lpMem,
              v71,
              v70,
              v69);
      v25 = v23;
      if ( v23 < 0 )
      {
        if ( (v23 & 0x1FFF0000) == 0x70000 )
          v25 = (unsigned __int16)v23;
        AslLogCallPrintf(1, "MergeSdb_RemoveUnusedSdbFiles", 700, "Failed to concat stub dir search path (%d)", v25);
        v30 = lpMem;
        if ( lpMem )
        {
          v31 = GetProcessHeap();
          HeapFree(v31, 0, v30);
        }
        v32 = GetProcessHeap();
        HeapFree(v32, 0, v19);
        std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v68);
        if ( phkResult )
          RegCloseKey(phkResult);
        v33 = v61;
        if ( v61 )
        {
          v34 = GetProcessHeap();
          HeapFree(v34, 0, v33);
        }
        std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v65);
        std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v64);
        if ( hKey )
          RegCloseKey(hKey);
        return v25;
      }
      v26 = std::_List_buy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Buynode<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              v24,
              v6,
              v6[1],
              &lpMem);
      if ( 0xAAAAAAAAAAAAAA9LL == v11 )
        std::_Xlength_error("list<T> too long");
      v66 = ++v11;
      v6[1] = v26;
      **(_QWORD **)(v26 + 8) = v26;
      v27 = lpMem;
      if ( lpMem )
      {
        v28 = GetProcessHeap();
        HeapFree(v28, 0, v27);
      }
    }
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v19);
  }
  for ( j = (__int64 **)*v6; j != (__int64 **)v6; j = (__int64 **)*j )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFile = (char *)FindFirstFileExW((LPCWSTR)j[2], FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
    if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &Str,
        j[2],
        -1);
      v37 = Str;
      v69[0] = Str;
      Str = 0;
      if ( !v69[0] )
      {
        FindClose(FirstFile);
        goto LABEL_81;
      }
      v38 = wcsrchr(v37, 0x5Cu);
      if ( !v38 )
      {
        v40 = GetProcessHeap();
        HeapFree(v40, 0, v37);
        FindClose(FirstFile);
        continue;
      }
      v38[1] = 0;
      while ( 2 )
      {
        v41 = (_QWORD *)v64[0];
        v42 = *(_QWORD **)v64[0];
        while ( 1 )
        {
          lpMem = 0;
          if ( v42 == v41 )
            break;
          if ( Pca::MergeSdb::Utils::RegValue::GetValueValue(
                 (Pca::MergeSdb::Utils::RegValue *)(v42 + 2),
                 (const unsigned __int16 **)&lpMem)
            && !_wcsicmp(FindFileData.cFileName, (const wchar_t *)lpMem) )
          {
            goto LABEL_61;
          }
          v42 = (_QWORD *)*v42;
          v41 = (_QWORD *)v64[0];
        }
        v43 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [2],unsigned short [260]>(
                &lpMem,
                v69,
                v39,
                FindFileData.cFileName);
        v44 = v43;
        if ( v43 < 0 )
        {
          if ( (v43 & 0x1FFF0000) == 0x70000 )
            v44 = (unsigned __int16)v43;
          AslLogCallPrintf(
            1,
            "MergeSdb_RemoveUnusedSdbFiles",
            759,
            "Failed to build full path for sdb to delete (%d)",
            v44);
          v49 = lpMem;
          if ( lpMem )
          {
            v50 = GetProcessHeap();
            HeapFree(v50, 0, v49);
          }
          v51 = GetProcessHeap();
          HeapFree(v51, 0, v37);
          FindClose(FirstFile);
          std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v68);
          if ( phkResult )
            RegCloseKey(phkResult);
          v52 = v61;
          if ( v61 )
          {
            v53 = GetProcessHeap();
            HeapFree(v53, 0, v52);
          }
          std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v65);
          std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v64);
          if ( hKey )
            RegCloseKey(hKey);
          return v44;
        }
        v45 = lpMem;
        if ( !DeleteFileW((LPCWSTR)lpMem) )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 1;
          AslLogCallPrintf(
            1,
            "MergeSdb_RemoveUnusedSdbFiles",
            765,
            "DeleteFileW failed to delete sdb file (%d)",
            LastError);
        }
        if ( v45 )
        {
          v47 = GetProcessHeap();
          HeapFree(v47, 0, v45);
        }
LABEL_61:
        if ( FindNextFileW(FirstFile, &FindFileData) )
          continue;
        break;
      }
      GetLastError();
      v48 = GetProcessHeap();
      HeapFree(v48, 0, v37);
LABEL_67:
      FindClose(FirstFile);
      continue;
    }
    v9 = GetLastError();
    if ( !v9 )
      v9 = 1;
    if ( ((v9 - 2) & 0xFFFFFFEF) != 0 )
    {
      AslLogCallPrintf(
        1,
        "MergeSdb_RemoveUnusedSdbFiles",
        723,
        "FindFirstFileExW failed to search AppPatch for registered sdb files (%d)",
        v9);
      if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        FindClose(FirstFile);
      goto LABEL_15;
    }
    if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_67;
  }
  std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v68);
  if ( phkResult )
    RegCloseKey(phkResult);
  v56 = v61;
  if ( v61 )
  {
    v57 = GetProcessHeap();
    HeapFree(v57, 0, v56);
  }
  std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v65);
  std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(v64);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x140027400  push    rbp
0x140027402  push    rbx
0x140027403  push    rsi
0x140027404  push    rdi
0x140027405  push    r12
0x140027407  push    r13
0x140027409  push    r14
0x14002740b  push    r15
0x14002740d  lea     rbp, [rsp-228h]
0x140027415  sub     rsp, 328h
0x14002741c  mov     rax, cs:__security_cookie
0x140027423  xor     rax, rsp
0x140027426  mov     [rbp+260h+var_50], rax
0x14002742d  xor     esi, esi
0x14002742f  mov     [rsp+360h+hKey], rsi
0x140027434  lea     rax, [rsp+360h+hKey]
0x140027439  mov     [rsp+360h+phkResult], rax; phkResult
0x14002743e  mov     r14d, 20019h
0x140027444  mov     r9d, r14d; samDesired
0x140027447  xor     r8d, r8d; ulOptions
0x14002744a  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140027451  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140027458  call    cs:__imp_RegOpenKeyExW
0x14002745e  mov     ebx, eax
0x140027460  test    eax, eax
0x140027462  jz      short loc_14002749B
0x140027464  mov     dword ptr [rsp+360h+phkResult], eax
0x140027468  lea     r9, aRegopenkeyexwF_0; "RegOpenKeyExW failed to open SdbUpdates"...
0x14002746f  mov     r8d, 27Ch
0x140027475  lea     rdx, aMergesdbRemove; "MergeSdb_RemoveUnusedSdbFiles"
0x14002747c  lea     ecx, [rsi+1]
0x14002747f  call    AslLogCallPrintf
0x140027484  mov     rcx, [rsp+360h+hKey]; hKey
0x140027489  test    rcx, rcx
0x14002748c  jz      short loc_140027494
0x14002748e  call    cs:__imp_RegCloseKey
0x140027494  mov     eax, ebx
0x140027496  jmp     loc_140027C49
0x14002749b  mov     [rsp+360h+var_308], rsi
0x1400274a0  xor     r8d, r8d
0x1400274a3  xor     edx, edx
0x1400274a5  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@@std@@QEAAPEAU?$_List_node@VRegValue@Utils@MergeSdb@Pca@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegValue>>::_Buynode0(std::_List_node<Pca::MergeSdb::Utils::RegValue,void *> *,std::_List_node<Pca::MergeSdb::Utils::RegValue,void *> *)
0x1400274aa  mov     [rsp+360h+var_310], rax
0x1400274af  mov     rdx, [rsp+360h+hKey]
0x1400274b4  lea     rcx, [rsp+360h+var_310]
0x1400274b9  call    ?GetRegValuesForKey@RegUtil@Utils@MergeSdb@Pca@@SAKAEAV?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@PEAUHKEY__@@@Z; Pca::MergeSdb::Utils::RegUtil::GetRegValuesForKey(std::list<Pca::MergeSdb::Utils::RegValue> &,HKEY__ *)
0x1400274be  mov     ebx, eax
0x1400274c0  test    eax, eax
0x1400274c2  jz      short loc_1400274F2
0x1400274c4  mov     dword ptr [rsp+360h+phkResult], eax
0x1400274c8  lea     r9, aFailedToGetSdb; "Failed to get SdbUpdates redirect value"...
0x1400274cf  mov     r8d, 282h
0x1400274d5  lea     rdx, aMergesdbRemove; "MergeSdb_RemoveUnusedSdbFiles"
0x1400274dc  mov     ecx, 1
0x1400274e1  call    AslLogCallPrintf
0x1400274e6  lea     rcx, [rsp+360h+var_310]
0x1400274eb  call    ??1?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@QEAA@XZ; std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(void)
0x1400274f0  jmp     short loc_140027484
0x1400274f2  mov     [rsp+360h+var_2F8], rsi
0x1400274f7  xor     r8d, r8d
0x1400274fa  xor     edx, edx
0x1400274fc  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::_Buynode0(std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *)
0x140027501  mov     r15, rax
0x140027504  mov     [rsp+360h+var_300], rax
0x140027509  mov     [rsp+360h+var_328], rsi
0x14002750e  lea     rdx, [rsp+360h+var_328]
0x140027513  lea     rcx, aSystemrootAppp_2; "%SYSTEMROOT%\\AppPatch\\???????????????"...
0x14002751a  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002751f  mov     edi, eax
0x140027521  test    eax, eax
0x140027523  js      loc_140027BD4
0x140027529  lea     r9, [rsp+360h+var_328]
0x14002752e  mov     r8, [r15+8]
0x140027532  mov     rdx, r15
0x140027535  call    ??$_Buynode@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$_List_buy@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@1@PEAU21@0$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; std::_List_buy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Buynode<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x14002753a  mov     r12d, 1
0x140027540  mov     r13d, r12d
0x140027543  mov     [rsp+360h+var_2F8], r12
0x140027548  mov     [r15+8], rax
0x14002754c  mov     rdx, [rax+8]
0x140027550  mov     [rdx], rax
0x140027553  mov     [rsp+360h+var_318], rsi
0x140027558  lea     rax, [rsp+360h+var_318]
0x14002755d  mov     [rsp+360h+phkResult], rax; phkResult
0x140027562  mov     r9d, r14d; samDesired
0x140027565  xor     r8d, r8d; ulOptions
0x140027568  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x14002756f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140027576  call    cs:__imp_RegOpenKeyExW
0x14002757c  mov     edi, eax
0x14002757e  test    eax, eax
0x140027580  jz      short loc_1400275BB
0x140027582  mov     dword ptr [rsp+360h+phkResult], eax
0x140027586  lea     r9, aRegopenkeyexwF; "RegOpenKeyExW failed to open Manifested"...
0x14002758d  mov     r8d, 29Fh
0x140027593  lea     rdx, aMergesdbRemove; "MergeSdb_RemoveUnusedSdbFiles"
0x14002759a  mov     ecx, r12d
0x14002759d  call    AslLogCallPrintf
0x1400275a2  mov     rcx, [rsp+360h+var_318]; hKey
0x1400275a7  test    rcx, rcx
0x1400275aa  jz      loc_140027C05
0x1400275b0  call    cs:__imp_RegCloseKey
0x1400275b6  jmp     loc_140027C05
0x1400275bb  mov     [rbp+260h+var_2E0], rsi
0x1400275bf  xor     r8d, r8d
0x1400275c2  xor     edx, edx
0x1400275c4  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@@std@@QEAAPEAU?$_List_node@VRegValue@Utils@MergeSdb@Pca@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Pca::MergeSdb::Utils::RegValue>>::_Buynode0(std::_List_node<Pca::MergeSdb::Utils::RegValue,void *> *,std::_List_node<Pca::MergeSdb::Utils::RegValue,void *> *)
0x1400275c9  mov     [rsp+360h+var_2E8], rax
0x1400275ce  mov     rdx, [rsp+360h+var_318]
0x1400275d3  lea     rcx, [rsp+360h+var_2E8]
0x1400275d8  call    ?GetRegValuesForKey@RegUtil@Utils@MergeSdb@Pca@@SAKAEAV?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@PEAUHKEY__@@@Z; Pca::MergeSdb::Utils::RegUtil::GetRegValuesForKey(std::list<Pca::MergeSdb::Utils::RegValue> &,HKEY__ *)
0x1400275dd  mov     edi, eax
0x1400275df  test    eax, eax
0x1400275e1  jz      short loc_14002760F
0x1400275e3  mov     dword ptr [rsp+360h+phkResult], eax
0x1400275e7  lea     r9, aFailedToGetMan_0; "Failed to get ManifestedMergeStubSdbs s"...
0x1400275ee  mov     r8d, 2A5h
0x1400275f4  lea     rdx, aMergesdbRemove; "MergeSdb_RemoveUnusedSdbFiles"
0x1400275fb  mov     ecx, r12d
0x1400275fe  call    AslLogCallPrintf
0x140027603  lea     rcx, [rsp+360h+var_2E8]
0x140027608  call    ??1?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@QEAA@XZ; std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(void)
0x14002760d  jmp     short loc_1400275A2
0x14002760f  mov     r14, [rsp+360h+var_2E8]
0x140027614  mov     rdi, [r14]
0x140027617  cmp     rdi, r14
0x14002761a  jz      loc_14002781A
0x140027620  cmp     dword ptr [rdi+18h], 3
0x140027624  jbe     short loc_140027633
0x140027626  mov     rax, [rdi+10h]
0x14002762a  test    rax, rax
0x14002762d  lea     rdx, [rax+0Ch]
0x140027631  jnz     short loc_140027636
0x140027633  mov     rdx, rsi
0x140027636  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002763a  lea     rcx, [rsp+360h+Str]
0x14002763f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140027644  mov     rbx, [rsp+360h+Str]
0x140027649  mov     [rsp+360h+Str], rsi
0x14002764e  test    rbx, rbx
0x140027651  jz      loc_140027AD1
0x140027657  mov     edx, 5Ch ; '\'; Ch
0x14002765c  mov     rcx, rbx; Str
0x14002765f  call    cs:__imp_wcsrchr
0x140027665  test    rax, rax
0x140027668  jnz     short loc_140027683
0x14002766a  call    cs:__imp_GetProcessHeap
0x140027670  mov     rcx, rax; hHeap
0x140027673  mov     r8, rbx; lpMem
0x140027676  xor     edx, edx; dwFlags
0x140027678  call    cs:__imp_HeapFree
0x14002767e  jmp     loc_14002774E
0x140027683  mov     [rax+2], si
0x140027687  mov     [rsp+360h+lpMem], rsi
0x14002768c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140027690  mov     rcx, rax
0x140027693  lea     rdx, aSdb_0; "????????????????.*.sdb"
0x14002769a  inc     rcx
0x14002769d  cmp     [rdx+rcx*2], si
0x1400276a1  jnz     short loc_14002769A
0x1400276a3  inc     rax
0x1400276a6  cmp     [rbx+rax*2], si
0x1400276aa  jnz     short loc_1400276A3
0x1400276ac  mov     [rbp+260h+var_2D0], rdx
0x1400276b0  mov     [rbp+260h+var_2C8], rcx
0x1400276b4  mov     [rbp+260h+var_2C0], rbx
0x1400276b8  mov     [rbp+260h+var_2B8], rax
0x1400276bc  mov     [rbp+260h+var_2B0], rsi
0x1400276c0  mov     [rbp+260h+var_2A8], rsi
0x1400276c4  lea     r9, [rbp+260h+var_2D0]
0x1400276c8  lea     r8, [rbp+260h+var_2C0]
0x1400276cc  lea     rdx, [rbp+260h+var_2B0]
0x1400276d0  lea     rcx, [rsp+360h+lpMem]
0x1400276d5  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@11@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x1400276da  mov     esi, eax
0x1400276dc  test    eax, eax
0x1400276de  js      short loc_140027756
0x1400276e0  lea     r9, [rsp+360h+lpMem]
0x1400276e5  mov     r8, [r15+8]
0x1400276e9  mov     rdx, r15
0x1400276ec  call    ??$_Buynode@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$_List_buy@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@1@PEAU21@0$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; std::_List_buy<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Buynode<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,void *> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1400276f1  mov     rcx, 0AAAAAAAAAAAAAA9h
0x1400276fb  sub     rcx, r13
0x1400276fe  cmp     rcx, r12
0x140027701  jb      loc_140027C6C
0x140027707  add     r13, r12
0x14002770a  mov     [rsp+360h+var_2F8], r13
0x14002770f  mov     [r15+8], rax
0x140027713  mov     rcx, [rax+8]
0x140027717  mov     [rcx], rax
0x14002771a  mov     rsi, [rsp+360h+lpMem]
0x14002771f  test    rsi, rsi
0x140027722  jz      short loc_140027738
0x140027724  call    cs:__imp_GetProcessHeap
0x14002772a  mov     rcx, rax; hHeap
0x14002772d  mov     r8, rsi; lpMem
0x140027730  xor     edx, edx; dwFlags
0x140027732  call    cs:__imp_HeapFree
0x140027738  call    cs:__imp_GetProcessHeap
0x14002773e  mov     rcx, rax; hHeap
0x140027741  mov     r8, rbx; lpMem
0x140027744  xor     edx, edx; dwFlags
0x140027746  call    cs:__imp_HeapFree
0x14002774c  xor     esi, esi
0x14002774e  mov     rdi, [rdi]
0x140027751  jmp     loc_140027617
0x140027756  and     eax, 1FFF0000h
0x14002775b  cmp     eax, 70000h
0x140027760  jnz     short loc_140027765
0x140027762  movzx   esi, si
0x140027765  mov     dword ptr [rsp+360h+phkResult], esi
0x140027769  lea     r9, aFailedToConcat_2; "Failed to concat stub dir search path ("...
0x140027770  mov     r8d, 2BCh
0x140027776  lea     rdx, aMergesdbRemove; "MergeSdb_RemoveUnusedSdbFiles"
0x14002777d  mov     ecx, r12d
0x140027780  call    AslLogCallPrintf
0x140027785  mov     rdi, [rsp+360h+lpMem]
0x14002778a  test    rdi, rdi
0x14002778d  jz      short loc_1400277A3
0x14002778f  call    cs:__imp_GetProcessHeap
0x140027795  mov     rcx, rax; hHeap
0x140027798  mov     r8, rdi; lpMem
0x14002779b  xor     edx, edx; dwFlags
0x14002779d  call    cs:__imp_HeapFree
0x1400277a3  call    cs:__imp_GetProcessHeap
0x1400277a9  mov     rcx, rax; hHeap
0x1400277ac  mov     r8, rbx; lpMem
0x1400277af  xor     edx, edx; dwFlags
0x1400277b1  call    cs:__imp_HeapFree
0x1400277b7  lea     rcx, [rsp+360h+var_2E8]
0x1400277bc  call    ??1?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@QEAA@XZ; std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(void)
0x1400277c1  mov     rcx, [rsp+360h+var_318]; hKey
0x1400277c6  test    rcx, rcx
0x1400277c9  jz      short loc_1400277D1
0x1400277cb  call    cs:__imp_RegCloseKey
0x1400277d1  mov     rbx, [rsp+360h+var_328]
0x1400277d6  test    rbx, rbx
0x1400277d9  jz      short loc_1400277EF
0x1400277db  call    cs:__imp_GetProcessHeap
0x1400277e1  mov     rcx, rax; hHeap
0x1400277e4  mov     r8, rbx; lpMem
0x1400277e7  xor     edx, edx; dwFlags
0x1400277e9  call    cs:__imp_HeapFree
0x1400277ef  lea     rcx, [rsp+360h+var_300]
0x1400277f4  call    ??1?$list@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~list<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1400277f9  lea     rcx, [rsp+360h+var_310]
0x1400277fe  call    ??1?$list@VRegValue@Utils@MergeSdb@Pca@@V?$allocator@VRegValue@Utils@MergeSdb@Pca@@@std@@@std@@QEAA@XZ; std::list<Pca::MergeSdb::Utils::RegValue>::~list<Pca::MergeSdb::Utils::RegValue>(void)
0x140027803  mov     rcx, [rsp+360h+hKey]; hKey
0x140027808  test    rcx, rcx
0x14002780b  jz      short loc_140027813
0x14002780d  call    cs:__imp_RegCloseKey
0x140027813  mov     eax, esi
0x140027815  jmp     loc_140027C49
0x14002781a  mov     r14, [r15]
0x14002781d  cmp     r14, r15
0x140027820  jz      loc_140027B74
0x140027826  xor     edx, edx; Val
0x140027828  mov     r8d, 250h; Size
0x14002782e  lea     rcx, [rbp+260h+FindFileData]; void *
0x140027832  call    memset_0
0x140027837  mov     [rsp+360h+dwAdditionalFlags], esi; dwAdditionalFlags
0x14002783b  mov     [rsp+360h+phkResult], rsi; lpSearchFilter
0x140027840  xor     r9d, r9d; fSearchOp
0x140027843  lea     r8, [rbp+260h+FindFileData]; lpFindFileData
0x140027847  mov     edx, r12d; fInfoLevelId
0x14002784a  mov     rcx, [r14+10h]; lpFileName
0x14002784e  call    cs:__imp_FindFirstFileExW
0x140027854  mov     rbx, rax
0x140027857  dec     rax
0x14002785a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002785e  ja      loc_1400279BB
0x140027864  or      r8, 0FFFFFFFFFFFFFFFFh
0x140027868  mov     rdx, [r14+10h]
0x14002786c  lea     rcx, [rsp+360h+Str]
0x140027871  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140027876  mov     rsi, [rsp+360h+Str]
0x14002787b  mov     [rbp+260h+var_2D0], rsi
0x14002787f  mov     [rsp+360h+Str], 0
0x140027888  test    rsi, rsi
0x14002788b  jz      loc_140027AC7
0x140027891  mov     edx, 5Ch ; '\'; Ch
0x140027896  mov     rcx, rsi; Str
0x140027899  call    cs:__imp_wcsrchr
0x14002789f  mov     rcx, rax
0x1400278a2  test    rax, rax
0x1400278a5  jnz     short loc_1400278CB
0x1400278a7  call    cs:__imp_GetProcessHeap
0x1400278ad  mov     rcx, rax; hHeap
0x1400278b0  mov     r8, rsi; lpMem
0x1400278b3  xor     edx, edx; dwFlags
0x1400278b5  call    cs:__imp_HeapFree
0x1400278bb  nop
0x1400278bc  mov     rcx, rbx; hFindFile
0x1400278bf  call    cs:__imp_FindClose
0x1400278c5  nop
0x1400278c6  jmp     loc_1400279EB
0x1400278cb  xor     eax, eax
0x1400278cd  mov     [rcx+2], ax
0x1400278d1  mov     rax, [rsp+360h+var_310]
0x1400278d6  mov     rdi, [rax]
  ... truncated ...
```
