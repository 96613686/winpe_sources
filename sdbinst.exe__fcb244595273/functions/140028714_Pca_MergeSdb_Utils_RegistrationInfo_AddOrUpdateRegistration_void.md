# Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration(void)

- ea: `0x140028714`
- end: `0x1400293c4`
- name: `?AddOrUpdateRegistration@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKXZ`
- size: `3248`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils::RegistrationInfo *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140027c80`

## callees

- `0x14000fb80`
- `0x14001008c`
- `0x140028298`
- `0x140028714`
- `0x14002a1ac`
- `0x14002acfc`
- `0x14002ce68`
- `0x14002d220`
- `0x14002d278`
- `0x14002d61c`
- `0x14002e24c`
- `0x14002e3ee`
- `0x14002e420`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140028a78`
- `ADVAPI32!RegSetValueExW` at `0x140028ad4`
- `ADVAPI32!RegSetValueExW` at `0x140028b36`
- `ADVAPI32!RegSetValueExW` at `0x140028b92`
- `ADVAPI32!RegSetValueExW` at `0x140028c78`
- `ADVAPI32!RegSetValueExW` at `0x140028d20`
- `ADVAPI32!RegSetValueExW` at `0x140028d7c`
- `ADVAPI32!RegSetValueExW` at `0x140028e70`
- `ADVAPI32!RegSetValueExW` at `0x140028a78`
- `ADVAPI32!RegSetValueExW` at `0x140028ad4`
- `ADVAPI32!RegSetValueExW` at `0x140028b36`
- `ADVAPI32!RegSetValueExW` at `0x140028b92`
- `ADVAPI32!RegSetValueExW` at `0x140028c78`
- `ADVAPI32!RegSetValueExW` at `0x140028d20`
- `ADVAPI32!RegSetValueExW` at `0x140028d7c`
- `ADVAPI32!RegSetValueExW` at `0x140028e70`
- `ADVAPI32!RegCreateKeyExW` at `0x140028857`
- `ADVAPI32!RegCreateKeyExW` at `0x1400289c2`
- `ADVAPI32!RegCreateKeyExW` at `0x140028857`
- `ADVAPI32!RegCreateKeyExW` at `0x1400289c2`
- `ADVAPI32!RegCloseKey` at `0x140028890`
- `ADVAPI32!RegCloseKey` at `0x14002892f`
- `ADVAPI32!RegCloseKey` at `0x1400289f9`
- `ADVAPI32!RegCloseKey` at `0x140028ec7`
- `ADVAPI32!RegCloseKey` at `0x140028f39`
- `ADVAPI32!RegCloseKey` at `0x140028fe5`
- `ADVAPI32!RegCloseKey` at `0x1400290e5`
- `ADVAPI32!RegCloseKey` at `0x1400291ec`
- `ADVAPI32!RegCloseKey` at `0x14002920d`
- `ADVAPI32!RegCloseKey` at `0x14002921e`
- `ADVAPI32!RegCloseKey` at `0x14002927b`
- `ADVAPI32!RegCloseKey` at `0x1400292a5`
- `ADVAPI32!RegCloseKey` at `0x140029313`
- `ADVAPI32!RegCloseKey` at `0x140029324`
- `ADVAPI32!RegCloseKey` at `0x140028890`
- `ADVAPI32!RegCloseKey` at `0x14002892f`
- `ADVAPI32!RegCloseKey` at `0x1400289f9`
- `ADVAPI32!RegCloseKey` at `0x140028ec7`
- `ADVAPI32!RegCloseKey` at `0x140028f39`
- `ADVAPI32!RegCloseKey` at `0x140028fe5`
- `ADVAPI32!RegCloseKey` at `0x1400290e5`
- `ADVAPI32!RegCloseKey` at `0x1400291ec`
- `ADVAPI32!RegCloseKey` at `0x14002920d`
- `ADVAPI32!RegCloseKey` at `0x14002921e`
- `ADVAPI32!RegCloseKey` at `0x14002927b`
- `ADVAPI32!RegCloseKey` at `0x1400292a5`
- `ADVAPI32!RegCloseKey` at `0x140029313`
- `ADVAPI32!RegCloseKey` at `0x140029324`
- `ADVAPI32!RegDeleteKeyW` at `0x140028ee5`
- `ADVAPI32!RegDeleteKeyW` at `0x140029103`
- `ADVAPI32!RegDeleteKeyW` at `0x1400292c3`
- `ADVAPI32!RegDeleteKeyW` at `0x140028ee5`
- `ADVAPI32!RegDeleteKeyW` at `0x140029103`
- `ADVAPI32!RegDeleteKeyW` at `0x1400292c3`
- `ADVAPI32!RegOpenKeyW` at `0x140028f8f`
- `ADVAPI32!RegOpenKeyW` at `0x140028f8f`
- `ADVAPI32!RegEnumKeyW` at `0x140028f59`
- `ADVAPI32!RegEnumKeyW` at `0x140028f59`
- `KERNEL32!GetLastError` at `0x140028ebc`
- `KERNEL32!GetLastError` at `0x1400290da`
- `KERNEL32!GetLastError` at `0x140029181`
- `KERNEL32!GetLastError` at `0x14002929a`
- `KERNEL32!GetLastError` at `0x140028ebc`
- `KERNEL32!GetLastError` at `0x1400290da`
- `KERNEL32!GetLastError` at `0x140029181`
- `KERNEL32!GetLastError` at `0x14002929a`
- `KERNEL32!DeleteFileW` at `0x140029174`
- `KERNEL32!DeleteFileW` at `0x140029174`
- `KERNEL32!GetProcessHeap` at `0x14002893b`
- `KERNEL32!GetProcessHeap` at `0x1400290b7`
- `KERNEL32!GetProcessHeap` at `0x1400291b3`
- `KERNEL32!GetProcessHeap` at `0x1400291cd`
- `KERNEL32!GetProcessHeap` at `0x14002922a`
- `KERNEL32!GetProcessHeap` at `0x140029330`
- `KERNEL32!GetProcessHeap` at `0x140029384`
- `KERNEL32!GetProcessHeap` at `0x14002893b`
- `KERNEL32!GetProcessHeap` at `0x1400290b7`
- `KERNEL32!GetProcessHeap` at `0x1400291b3`
- `KERNEL32!GetProcessHeap` at `0x1400291cd`
- `KERNEL32!GetProcessHeap` at `0x14002922a`
- `KERNEL32!GetProcessHeap` at `0x140029330`
- `KERNEL32!GetProcessHeap` at `0x140029384`
- `KERNEL32!SetLastError` at `0x140028ecf`
- `KERNEL32!SetLastError` at `0x1400290ed`
- `KERNEL32!SetLastError` at `0x1400292ad`
- `KERNEL32!SetLastError` at `0x140028ecf`
- `KERNEL32!SetLastError` at `0x1400290ed`
- `KERNEL32!SetLastError` at `0x1400292ad`
- `KERNEL32!HeapFree` at `0x140028949`
- `KERNEL32!HeapFree` at `0x1400290c5`
- `KERNEL32!HeapFree` at `0x1400291c1`
- `KERNEL32!HeapFree` at `0x1400291db`
- `KERNEL32!HeapFree` at `0x140029238`
- `KERNEL32!HeapFree` at `0x14002933e`
- `KERNEL32!HeapFree` at `0x140029392`
- `KERNEL32!HeapFree` at `0x140028949`
- `KERNEL32!HeapFree` at `0x1400290c5`
- `KERNEL32!HeapFree` at `0x1400291c1`
- `KERNEL32!HeapFree` at `0x1400291db`
- `KERNEL32!HeapFree` at `0x140029238`
- `KERNEL32!HeapFree` at `0x14002933e`
- `KERNEL32!HeapFree` at `0x140029392`
- `msvcrt!_wcsicmp` at `0x140028f72`
- `msvcrt!_wcsicmp` at `0x140028f72`
- `msvcrt!_wcsnicmp` at `0x140029167`
- `msvcrt!_wcsnicmp` at `0x140029167`
- `ntdll!RtlNtStatusToDosError` at `0x1400288fc`
- `ntdll!RtlNtStatusToDosError` at `0x1400288fc`

## string_xrefs

- `0x140029032`: `ManifestedMergeFodSdbs`
- `0x140029045`: `ManifestedMergeStubSdbs`
- `0x14002935c`: `Failed to format the reg key path for sdb merge target key (%d)`
- `0x140028bcc`: `FilePath`
- `0x140028be7`: `FilePath`
- `0x140029075`: `FilePath`
- `0x140028a0a`: `CompilerVersion`
- `0x140028a25`: `CompilerVersion`
- `0x1400287ba`: `Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration`
- `0x1400287df`: `Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration`
- `0x140028874`: `Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration`
- `0x14002889c`: `Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration`
- `0x140029369`: `Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration`
- `0x140028867`: `Failed to open/create sdb merge file key (%d)`
- `0x1400289d2`: `Failed to open/create sdb merge file key (%d)`
- `0x1400287ad`: `Failed to move merge sdb to merge store directory (%d)`
- `0x140028975`: `Failed to write database id to default value of merge target key (%d)`
- `0x140028ef3`: `RegDeleteKeyW failed to delete key (%d)`
- `0x1400292d1`: `RegDeleteKeyW failed to delete key (%d)`
- `0x140028a31`: `Failed to write registry value %S: (%d)`
- `0x140028a94`: `Failed to write registry value %S: (%d)`
- `0x140028af0`: `Failed to write registry value %S: (%d)`
- `0x140028b52`: `Failed to write registry value %S: (%d)`
- `0x140028bae`: `Failed to write registry value %S: (%d)`
- `0x140028bf3`: `Failed to write registry value %S: (%d)`
- `0x140028c38`: `Failed to write registry value %S: (%d)`
- `0x140028c94`: `Failed to write registry value %S: (%d)`
- `0x140028cd9`: `Failed to write registry value %S: (%d)`
- `0x140028d3c`: `Failed to write registry value %S: (%d)`
- `0x140028d98`: `Failed to write registry value %S: (%d)`
- `0x140028ddd`: `Failed to write registry value %S: (%d)`
- `0x140028e29`: `Failed to write registry value %S: (%d)`
- `0x140028e8c`: `Failed to write registry value %S: (%d)`
- `0x140029254`: `Failed to open old sdb merge file key (%d)`
- `0x140028f12`: `Failed to delete file (%d)`
- `0x1400292f0`: `Failed to delete file (%d)`
- `0x14002908d`: `Failed to get old sdb merge file path (%d)`
- `0x140029144`: `Failed to get the sdb merge dir path (%d)`
- `0x140029110`: `Failed to delete old sdb merge file key (%d)`
- `0x140029190`: `Failed to delete file from the merge sdb directory (%d)`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration(
        Pca::MergeSdb::Utils::RegistrationInfo *this)
{
  __int64 *v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // ebx
  int v8; // eax
  unsigned int v9; // edi
  WCHAR *v10; // rbx
  LSTATUS v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  NTSTATUS v14; // edi
  ULONG v15; // eax
  ULONG v16; // esi
  HANDLE v17; // rax
  unsigned int v18; // eax
  LSTATUS v19; // eax
  ULONG v20; // edi
  unsigned int v21; // eax
  unsigned int v22; // esi
  LSTATUS v23; // eax
  LSTATUS v24; // esi
  LSTATUS v25; // eax
  LSTATUS v26; // esi
  LSTATUS v27; // eax
  LSTATUS v28; // esi
  LSTATUS v29; // eax
  LSTATUS v30; // esi
  unsigned int v31; // eax
  unsigned int v32; // esi
  unsigned int v33; // eax
  unsigned int v34; // esi
  LSTATUS v35; // eax
  LSTATUS v36; // esi
  unsigned int v37; // eax
  unsigned int v38; // esi
  LSTATUS v39; // eax
  LSTATUS v40; // esi
  LSTATUS v41; // eax
  LSTATUS v42; // esi
  unsigned int v43; // eax
  unsigned int v44; // esi
  unsigned int v45; // eax
  unsigned int v46; // esi
  LSTATUS v47; // eax
  HKEY v48; // r15
  DWORD LastError; // edi
  LSTATUS v50; // eax
  DWORD i; // edi
  unsigned int MergeSdbDirectoryPath; // r15d
  LSTATUS RegValue; // eax
  const char *v54; // r9
  __int64 v55; // r8
  const wchar_t *v56; // rdi
  LSTATUS v57; // eax
  const char *v58; // r9
  __int64 v59; // r8
  void *v60; // rdi
  HANDLE v61; // rax
  HKEY v62; // rsi
  DWORD v63; // edi
  WCHAR *v64; // rdi
  wchar_t *v65; // rsi
  const char *v66; // r9
  __int64 v67; // r8
  size_t v68; // r8
  HANDLE v69; // rax
  HANDLE v70; // rax
  HANDLE v71; // rax
  HKEY v72; // rsi
  DWORD v73; // edi
  LSTATUS v74; // eax
  HANDLE v75; // rax
  HANDLE ProcessHeap; // rax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String1[2]; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+80h] [rbp-80h]
  LPCWSTR lpSubKey; // [rsp+88h] [rbp-78h] BYREF
  __int64 v85; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v86; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v87[40]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Name[264]; // [rsp+100h] [rbp+0h] BYREF

  if ( !*(_QWORD *)this || !*((_QWORD *)this + 13) || !*((_BYTE *)this + 16) || !*((_QWORD *)this + 19) )
    return 5023;
  v2 = (__int64 *)&off_140031270;
  do
  {
    if ( v2[1] == *(_QWORD *)((char *)this + 20) && v2[2] == *(_QWORD *)((char *)this + 28) )
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
        1215,
        "Cannot register a main SDB to merge.");
      return 1358;
    }
    v2 += 3;
  }
  while ( v2 != &qword_1400312B8 );
  v3 = Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder(this);
  v6 = v3;
  if ( v3 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1221,
      "Failed to move merge sdb to merge store directory (%d)",
      v3);
    return v6;
  }
  lpSubKey = 0;
  v8 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [71],unsigned short [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         &lpSubKey,
         v4,
         v5,
         (char *)this + 96);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( (v8 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v8;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1230,
      "Failed to format the reg key path for sdb merge target key (%d)",
      v9);
    v10 = (WCHAR *)lpSubKey;
    goto LABEL_142;
  }
  dwDisposition = 0;
  hKey = 0;
  v10 = (WCHAR *)lpSubKey;
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  v9 = v11;
  if ( v11 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1245,
      "Failed to open/create sdb merge file key (%d)",
      v11);
LABEL_15:
    if ( hKey )
      RegCloseKey(hKey);
LABEL_142:
    if ( v10 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v10);
    }
    return v9;
  }
  if ( (dwDisposition & 1) != 0 )
  {
    String1[0] = 0;
    String1[1] = 0;
    v12 = *(_QWORD *)((char *)this + 36);
    if ( !v12 )
      v12 = *(_QWORD *)((char *)this + 44);
    v13 = 36;
    if ( !v12 )
      v13 = 20;
    v86 = *(struct _GUID *)((char *)this + v13);
    v14 = AslGuidToString(v87, 39, &v86);
    v15 = RtlNtStatusToDosError(v14);
    v16 = v15;
    if ( v14 < 0 )
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
        1261,
        "AslGuidToString failed to format GUID as string (%d)",
        v15);
LABEL_25:
      if ( hKey )
        RegCloseKey(hKey);
      if ( v10 )
      {
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v10);
      }
      return v16;
    }
    v18 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(hKey, &Format, v87);
    if ( v18 )
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
        1269,
        "Failed to write database id to default value of merge target key (%d)",
        v18);
  }
  phkResult = 0;
  v19 = RegCreateKeyExW(hKey, *((LPCWSTR *)this + 13), 0, 0, 0, 0x2001Fu, 0, &phkResult, 0);
  v9 = v19;
  if ( v19 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1284,
      "Failed to open/create sdb merge file key (%d)",
      v19);
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_15;
  }
  v20 = 0;
  v21 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(
          phkResult,
          L"CompilerVersion",
          *((const unsigned __int16 **)this + 9));
  v22 = v21;
  if ( v21 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1301,
      "Failed to write registry value %S: (%d)",
      L"CompilerVersion",
      v21);
    v20 = v22;
  }
  *(_DWORD *)Data = *((_DWORD *)this + 20);
  v23 = RegSetValueExW(phkResult, L"CrcChecksum", 0, 4u, Data, 4u);
  v24 = v23;
  if ( v23 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1302,
      "Failed to write registry value %S: (%d)",
      L"CrcChecksum",
      v23);
    v20 = v24;
  }
  v25 = RegSetValueExW(phkResult, L"DatabaseId", 0, 3u, (const BYTE *)this + 20, 0x10u);
  v26 = v25;
  if ( v25 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1303,
      "Failed to write registry value %S: (%d)",
      L"DatabaseId",
      v25);
    v20 = v26;
  }
  *(_DWORD *)Data = *((_DWORD *)this + 13);
  v27 = RegSetValueExW(phkResult, L"TargetDatabaseChecksum", 0, 4u, Data, 4u);
  v28 = v27;
  if ( v27 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1304,
      "Failed to write registry value %S: (%d)",
      L"TargetDatabaseChecksum",
      v27);
    v20 = v28;
  }
  v29 = RegSetValueExW(phkResult, L"TargetDatabaseId", 0, 3u, (const BYTE *)this + 36, 0x10u);
  v30 = v29;
  if ( v29 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1305,
      "Failed to write registry value %S: (%d)",
      L"TargetDatabaseId",
      v29);
    v20 = v30;
  }
  v31 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(phkResult, L"FilePath", *(const unsigned __int16 **)this);
  v32 = v31;
  if ( v31 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1306,
      "Failed to write registry value %S: (%d)",
      L"FilePath",
      v31);
    v20 = v32;
  }
  v33 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(phkResult, L"MergeTarget", *((const unsigned __int16 **)this + 12));
  v34 = v33;
  if ( v33 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1307,
      "Failed to write registry value %S: (%d)",
      L"MergeTarget",
      v33);
    v20 = v34;
  }
  v35 = RegSetValueExW(phkResult, L"FileTime", 0, 0xBu, (const BYTE *)this + 8, 8u);
  v36 = v35;
  if ( v35 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1308,
      "Failed to write registry value %S: (%d)",
      L"FileTime",
      v35);
    v20 = v36;
  }
  v37 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(
          phkResult,
          L"FriendlyName",
          *((const unsigned __int16 **)this + 15));
  v38 = v37;
  if ( v37 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1309,
      "Failed to write registry value %S: (%d)",
      L"FriendlyName",
      v37);
    v20 = v38;
  }
  *(_DWORD *)Data = *((_DWORD *)this + 14);
  v39 = RegSetValueExW(phkResult, L"RuntimePlatform", 0, 4u, Data, 4u);
  v40 = v39;
  if ( v39 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1310,
      "Failed to write registry value %S: (%d)",
      L"RuntimePlatform",
      v39);
    v20 = v40;
  }
  v41 = RegSetValueExW(phkResult, L"SdbTime", 0, 0xBu, (const BYTE *)this + 64, 8u);
  v42 = v41;
  if ( v41 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1311,
      "Failed to write registry value %S: (%d)",
      L"SdbTime",
      v41);
    v20 = v42;
  }
  v43 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(
          phkResult,
          L"RegisteredName",
          *((const unsigned __int16 **)this + 13));
  v44 = v43;
  if ( v43 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1312,
      "Failed to write registry value %S: (%d)",
      L"RegisteredName",
      v43);
    v20 = v44;
  }
  v45 = Pca::MergeSdb::Utils::RegUtil::WriteRegValue(
          phkResult,
          L"MergeInputType",
          *(const unsigned __int16 **)(*((_QWORD *)this + 19) + 8LL));
  v46 = v45;
  if ( v45 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1313,
      "Failed to write registry value %S: (%d)",
      L"MergeInputType",
      v45);
    v20 = v46;
  }
  *(_DWORD *)Data = *((_DWORD *)this + 23);
  v47 = RegSetValueExW(phkResult, L"InputTestOnly", 0, 4u, Data, 4u);
  v16 = v47;
  if ( v47 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      1314,
      "Failed to write registry value %S: (%d)",
      L"InputTestOnly",
      v47);
LABEL_64:
    v48 = phkResult;
    if ( phkResult )
    {
      LastError = GetLastError();
      RegCloseKey(v48);
      SetLastError(LastError);
    }
    phkResult = 0;
    v50 = RegDeleteKeyW(hKey, *((LPCWSTR *)this + 13));
    if ( v50 )
    {
      dwOptions[0] = v50;
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
        1326,
        "RegDeleteKeyW failed to delete key (%d)",
        *(_QWORD *)dwOptions);
    }
    else if ( Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder(this) )
    {
      dwOptions[0] = 0;
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
        1331,
        "Failed to delete file (%d)",
        *(_QWORD *)dwOptions);
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_25;
  }
  v16 = v20;
  if ( v20 )
    goto LABEL_64;
  for ( i = 0; ; ++i )
  {
    MergeSdbDirectoryPath = RegEnumKeyW(hKey, i, Name, 0x104u);
    if ( MergeSdbDirectoryPath )
      goto LABEL_125;
    if ( _wcsicmp(Name, *((const wchar_t **)this + 13)) )
      break;
LABEL_81:
    ;
  }
  *(_QWORD *)Data = 0;
  RegValue = RegOpenKeyW(hKey, Name, (PHKEY)Data);
  MergeSdbDirectoryPath = RegValue;
  if ( RegValue )
  {
    v54 = "Failed to open old sdb merge file key (%d)";
    v55 = 1350;
    goto LABEL_122;
  }
  v86 = 0;
  RegValue = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(*(HKEY *)Data, L"DatabaseId", &v86);
  MergeSdbDirectoryPath = RegValue;
  if ( RegValue )
  {
    v54 = "Failed to get old sdb merge database ID (%d)";
    v55 = 1356;
LABEL_122:
    dwOptions[0] = RegValue;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      v55,
      v54,
      *(_QWORD *)dwOptions);
LABEL_123:
    if ( *(_QWORD *)Data )
      RegCloseKey(*(HKEY *)Data);
    goto LABEL_125;
  }
  if ( *(_QWORD *)&v86.Data1 != *(_QWORD *)((char *)this + 20) || *(_QWORD *)v86.Data4 != *(_QWORD *)((char *)this + 28) )
  {
    if ( *(_QWORD *)Data )
      RegCloseKey(*(HKEY *)Data);
    goto LABEL_81;
  }
  v85 = 0;
  RegValue = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(
               *(HKEY *)Data,
               L"SdbTime",
               (struct Pca::MergeSdb::Utils::TimeValue *)&v85);
  MergeSdbDirectoryPath = RegValue;
  if ( RegValue )
  {
    v54 = "Failed to get old sdb merge database ID (%d)";
    v55 = 1363;
    goto LABEL_122;
  }
  v56 = *(const wchar_t **)(*((_QWORD *)this + 19) + 8LL);
  if ( wcscmp_0(v56, L"ManifestedMergeFodSdbs")
    && wcscmp_0(v56, L"ManifestedMergeStubSdbs")
    && v85 > *((_QWORD *)this + 8) )
  {
    MergeSdbDirectoryPath = 183;
    goto LABEL_123;
  }
  lpMem = 0;
  v57 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(*(HKEY *)Data, L"FilePath");
  MergeSdbDirectoryPath = v57;
  if ( v57 )
  {
    v58 = "Failed to get old sdb merge file path (%d)";
    v59 = 1381;
    goto LABEL_90;
  }
  v62 = *(HKEY *)Data;
  if ( *(_QWORD *)Data )
  {
    v63 = GetLastError();
    RegCloseKey(v62);
    SetLastError(v63);
  }
  *(_QWORD *)Data = 0;
  v57 = RegDeleteKeyW(hKey, Name);
  MergeSdbDirectoryPath = v57;
  if ( v57 )
  {
    v58 = "Failed to delete old sdb merge file key (%d)";
    v59 = 1388;
LABEL_90:
    dwOptions[0] = v57;
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
      v59,
      v58,
      *(_QWORD *)dwOptions);
    v60 = lpMem;
    if ( lpMem )
    {
      v61 = GetProcessHeap();
      HeapFree(v61, 0, v60);
    }
    goto LABEL_123;
  }
  String1[0] = 0;
  MergeSdbDirectoryPath = Pca::MergeSdb::Utils::RegistrationInfo::GetMergeSdbDirectoryPath((void **)String1);
  v64 = (WCHAR *)lpMem;
  v65 = String1[0];
  if ( MergeSdbDirectoryPath )
  {
    v66 = "Failed to get the sdb merge dir path (%d)";
    v67 = 1395;
    goto LABEL_105;
  }
  v68 = -1;
  do
    ++v68;
  while ( String1[0][v68] );
  if ( !_wcsnicmp(String1[0], (const wchar_t *)lpMem, v68) )
  {
    MergeSdbDirectoryPath = 0;
    if ( !DeleteFileW(v64) )
    {
      MergeSdbDirectoryPath = GetLastError();
      if ( !MergeSdbDirectoryPath )
        MergeSdbDirectoryPath = 1;
      v66 = "Failed to delete file from the merge sdb directory (%d)";
      v67 = 1403;
LABEL_105:
      dwOptions[0] = MergeSdbDirectoryPath;
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
        v67,
        v66,
        *(_QWORD *)dwOptions);
    }
  }
  if ( v65 )
  {
    v69 = GetProcessHeap();
    HeapFree(v69, 0, v65);
  }
  if ( v64 )
  {
    v70 = GetProcessHeap();
    HeapFree(v70, 0, v64);
  }
  if ( *(_QWORD *)Data )
    RegCloseKey(*(HKEY *)Data);
  if ( !MergeSdbDirectoryPath )
    goto LABEL_113;
LABEL_125:
  if ( MergeSdbDirectoryPath != 259 )
  {
    v72 = phkResult;
    if ( phkResult )
    {
      v73 = GetLastError();
      RegCloseKey(v72);
      SetLastError(v73);
    }
    phkResult = 0;
    v74 = RegDeleteKeyW(hKey, *((LPCWSTR *)this + 13));
    if ( v74 )
    {
      dwOptions[0] = v74;
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
        1418,
        "RegDeleteKeyW failed to delete key (%d)",
        *(_QWORD *)dwOptions);
    }
    else if ( Pca::MergeSdb::Utils::RegistrationInfo::DeleteFromMergeSdbFolder(this) )
    {
      dwOptions[0] = 0;
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::AddOrUpdateRegistration",
        1423,
        "Failed to delete file (%d)",
        *(_QWORD *)dwOptions);
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v10 )
    {
      v75 = GetProcessHeap();
      HeapFree(v75, 0, v10);
    }
    return MergeSdbDirectoryPath;
  }
LABEL_113:
  *((_DWORD *)this + 36) |= 5u;
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 )
  {
    v71 = GetProcessHeap();
    HeapFree(v71, 0, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x140028714  push    rbp
0x140028716  push    rbx
0x140028717  push    rsi
0x140028718  push    rdi
0x140028719  push    r12
0x14002871b  push    r13
0x14002871d  push    r14
0x14002871f  push    r15
0x140028721  lea     rbp, [rsp-228h]
0x140028729  sub     rsp, 328h
0x140028730  mov     rax, cs:__security_cookie
0x140028737  xor     rax, rsp
0x14002873a  mov     [rbp+260h+var_50], rax
0x140028741  mov     r13, rcx
0x140028744  xor     esi, esi
0x140028746  cmp     [rcx], rsi
0x140028749  jz      loc_14002939C
0x14002874f  cmp     [rcx+68h], rsi
0x140028753  jz      loc_14002939C
0x140028759  cmp     [rcx+10h], sil
0x14002875d  jz      loc_14002939C
0x140028763  cmp     [rcx+98h], rsi
0x14002876a  jz      loc_14002939C
0x140028770  lea     rcx, off_140031270; "sysmain.sdb"
0x140028777  mov     rax, [rcx+8]
0x14002877b  cmp     rax, [r13+14h]
0x14002877f  jnz     short loc_14002878B
0x140028781  mov     rax, [rcx+10h]
0x140028785  cmp     rax, [r13+1Ch]
0x140028789  jz      short loc_1400287D2
0x14002878b  add     rcx, 18h
0x14002878f  lea     rax, qword_1400312B8
0x140028796  cmp     rcx, rax
0x140028799  jnz     short loc_140028777
0x14002879b  mov     rcx, r13; this
0x14002879e  call    ?MoveToMergeSdbFolder@RegistrationInfo@Utils@MergeSdb@Pca@@AEAAKXZ; Pca::MergeSdb::Utils::RegistrationInfo::MoveToMergeSdbFolder(void)
0x1400287a3  mov     ebx, eax
0x1400287a5  test    eax, eax
0x1400287a7  jz      short loc_1400287FA
0x1400287a9  mov     [rsp+360h+dwOptions], eax
0x1400287ad  lea     r9, aFailedToMoveMe; "Failed to move merge sdb to merge store"...
0x1400287b4  mov     r8d, 4C5h
0x1400287ba  lea     rdx, aPcaMergesdbUti_12; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x1400287c1  mov     ecx, 1
0x1400287c6  call    AslLogCallPrintf
0x1400287cb  mov     eax, ebx
0x1400287cd  jmp     loc_1400293A1
0x1400287d2  lea     r9, aCannotRegister_0; "Cannot register a main SDB to merge."
0x1400287d9  mov     r8d, 4BFh
0x1400287df  lea     rdx, aPcaMergesdbUti_12; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x1400287e6  mov     ecx, 1
0x1400287eb  call    AslLogCallPrintf
0x1400287f0  mov     eax, 54Eh
0x1400287f5  jmp     loc_1400293A1
0x1400287fa  mov     [rbp+260h+lpSubKey], rsi
0x1400287fe  lea     r9, [r13+60h]
0x140028802  lea     rcx, [rbp+260h+lpSubKey]
0x140028806  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$$BY0EH@G$$BY01GV12@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEAY0EH@$$CBGAEAY01$$CBGAEBV10@@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [71],ushort [2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const (&)[71],ushort const (&)[2],wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x14002880b  mov     edi, eax
0x14002880d  test    eax, eax
0x14002880f  js      loc_140029349
0x140028815  mov     [rsp+360h+dwDisposition], esi
0x140028819  mov     [rsp+360h+hKey], rsi
0x14002881e  lea     rax, [rsp+360h+dwDisposition]
0x140028823  mov     [rsp+360h+lpdwDisposition], rax; lpdwDisposition
0x140028828  lea     rax, [rsp+360h+hKey]
0x14002882d  mov     [rsp+360h+phkResult], rax; phkResult
0x140028832  mov     [rsp+360h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140028837  mov     [rsp+360h+samDesired], 2001Fh; samDesired
0x14002883f  mov     [rsp+360h+dwOptions], esi; dwOptions
0x140028843  xor     r9d, r9d; lpClass
0x140028846  xor     r8d, r8d; Reserved
0x140028849  mov     rbx, [rbp+260h+lpSubKey]
0x14002884d  mov     rdx, rbx; lpSubKey
0x140028850  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140028857  call    cs:__imp_RegCreateKeyExW
0x14002885d  mov     edi, eax
0x14002885f  test    eax, eax
0x140028861  jz      short loc_14002889C
0x140028863  mov     [rsp+360h+dwOptions], eax
0x140028867  lea     r9, aFailedToOpenCr; "Failed to open/create sdb merge file ke"...
0x14002886e  mov     r8d, 4DDh
0x140028874  lea     rdx, aPcaMergesdbUti_12; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002887b  mov     ecx, 1
0x140028880  call    AslLogCallPrintf
0x140028885  nop
0x140028886  mov     rcx, [rsp+360h+hKey]; hKey
0x14002888b  test    rcx, rcx
0x14002888e  jz      short loc_140028897
0x140028890  call    cs:__imp_RegCloseKey
0x140028896  nop
0x140028897  jmp     loc_14002937F
0x14002889c  lea     r12, aPcaMergesdbUti_12; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x1400288a3  mov     r14d, 1
0x1400288a9  test    byte ptr [rsp+360h+dwDisposition], r14b
0x1400288ae  jz      loc_14002898E
0x1400288b4  mov     [rsp+360h+String1], rsi
0x1400288b9  mov     [rsp+360h+var_2F0], rsi
0x1400288be  mov     rcx, [r13+24h]
0x1400288c2  sub     rcx, rsi
0x1400288c5  jnz     short loc_1400288CE
0x1400288c7  mov     rcx, [r13+2Ch]
0x1400288cb  sub     rcx, rsi
0x1400288ce  mov     eax, 24h ; '$'
0x1400288d3  lea     edx, [rax-10h]
0x1400288d6  test    rcx, rcx
0x1400288d9  cmovz   eax, edx
0x1400288dc  movups  xmm0, xmmword ptr [rax+r13]
0x1400288e1  movdqu  xmmword ptr [rbp+260h+var_2C8.Data1], xmm0
0x1400288e6  lea     r8, [rbp+260h+var_2C8]
0x1400288ea  mov     edx, 27h ; '''
0x1400288ef  lea     rcx, [rbp+260h+var_2B0]
0x1400288f3  call    AslGuidToString
0x1400288f8  mov     edi, eax
0x1400288fa  mov     ecx, eax; Status
0x1400288fc  call    cs:__imp_RtlNtStatusToDosError
0x140028902  mov     esi, eax
0x140028904  test    edi, edi
0x140028906  jns     short loc_140028956
0x140028908  mov     [rsp+360h+dwOptions], eax
0x14002890c  lea     r9, aAslguidtostrin_0; "AslGuidToString failed to format GUID a"...
0x140028913  mov     r8d, 4EDh
0x140028919  mov     rdx, r12
0x14002891c  mov     ecx, r14d
0x14002891f  call    AslLogCallPrintf
0x140028924  nop
0x140028925  mov     rcx, [rsp+360h+hKey]; hKey
0x14002892a  test    rcx, rcx
0x14002892d  jz      short loc_140028936
0x14002892f  call    cs:__imp_RegCloseKey
0x140028935  nop
0x140028936  test    rbx, rbx
0x140028939  jz      short loc_14002894F
0x14002893b  call    cs:__imp_GetProcessHeap
0x140028941  mov     rcx, rax; hHeap
0x140028944  mov     r8, rbx; lpMem
0x140028947  xor     edx, edx; dwFlags
0x140028949  call    cs:__imp_HeapFree
0x14002894f  mov     eax, esi
0x140028951  jmp     loc_1400293A1
0x140028956  lea     r8, [rbp+260h+var_2B0]; unsigned __int16 *
0x14002895a  lea     rdx, Format; unsigned __int16 *
0x140028961  mov     rcx, [rsp+360h+hKey]; HKEY
0x140028966  call    ?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBG1@Z; Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ushort const *)
0x14002896b  xor     esi, esi
0x14002896d  test    eax, eax
0x14002896f  jz      short loc_14002898E
0x140028971  mov     [rsp+360h+dwOptions], eax
0x140028975  lea     r9, aFailedToWriteD_1; "Failed to write database id to default "...
0x14002897c  mov     r8d, 4F5h
0x140028982  mov     rdx, r12
0x140028985  mov     ecx, r14d
0x140028988  call    AslLogCallPrintf
0x14002898d  nop
0x14002898e  mov     [rsp+360h+var_310], rsi
0x140028993  mov     [rsp+360h+lpdwDisposition], rsi; lpdwDisposition
0x140028998  lea     rax, [rsp+360h+var_310]
0x14002899d  mov     [rsp+360h+phkResult], rax; phkResult
0x1400289a2  mov     [rsp+360h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1400289a7  mov     [rsp+360h+samDesired], 2001Fh; samDesired
0x1400289af  mov     [rsp+360h+dwOptions], esi; dwOptions
0x1400289b3  xor     r9d, r9d; lpClass
0x1400289b6  xor     r8d, r8d; Reserved
0x1400289b9  mov     rdx, [r13+68h]; lpSubKey
0x1400289bd  mov     rcx, [rsp+360h+hKey]; hKey
0x1400289c2  call    cs:__imp_RegCreateKeyExW
0x1400289c8  mov     edi, eax
0x1400289ca  test    eax, eax
0x1400289cc  jz      short loc_140028A04
0x1400289ce  mov     [rsp+360h+dwOptions], eax
0x1400289d2  lea     r9, aFailedToOpenCr; "Failed to open/create sdb merge file ke"...
0x1400289d9  mov     r8d, 504h
0x1400289df  mov     rdx, r12
0x1400289e2  mov     ecx, r14d
0x1400289e5  call    AslLogCallPrintf
0x1400289ea  nop
0x1400289eb  mov     rcx, [rsp+360h+var_310]; hKey
0x1400289f0  test    rcx, rcx
0x1400289f3  jz      loc_140028886
0x1400289f9  call    cs:__imp_RegCloseKey
0x1400289ff  jmp     loc_140028886
0x140028a04  mov     edi, esi
0x140028a06  mov     r8, [r13+48h]; unsigned __int16 *
0x140028a0a  lea     rdx, ?REG_VALUE_NAME_COMPILER_VERSION@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "CompilerVersion"
0x140028a11  mov     rcx, [rsp+360h+var_310]; HKEY
0x140028a16  call    ?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBG1@Z; Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ushort const *)
0x140028a1b  mov     esi, eax
0x140028a1d  test    eax, eax
0x140028a1f  jz      short loc_140028A4B
0x140028a21  mov     [rsp+360h+samDesired], eax
0x140028a25  lea     rax, ?REG_VALUE_NAME_COMPILER_VERSION@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "CompilerVersion"
0x140028a2c  mov     qword ptr [rsp+360h+dwOptions], rax
0x140028a31  lea     r9, aFailedToWriteR; "Failed to write registry value %S: (%d)"
0x140028a38  mov     r8d, 515h
0x140028a3e  mov     rdx, r12
0x140028a41  mov     ecx, r14d
0x140028a44  call    AslLogCallPrintf
0x140028a49  mov     edi, esi
0x140028a4b  mov     eax, [r13+50h]
0x140028a4f  mov     dword ptr [rsp+360h+Data], eax
0x140028a53  mov     ecx, 4
0x140028a58  mov     [rsp+360h+samDesired], ecx; cbData
0x140028a5c  lea     rax, [rsp+360h+Data]
0x140028a61  mov     qword ptr [rsp+360h+dwOptions], rax; lpData
0x140028a66  mov     r9d, ecx; dwType
0x140028a69  xor     r8d, r8d; Reserved
0x140028a6c  lea     rdx, ?REG_VALUE_NAME_CRC_CHECKSUM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "CrcChecksum"
0x140028a73  mov     rcx, [rsp+360h+var_310]; hKey
0x140028a78  call    cs:__imp_RegSetValueExW
0x140028a7e  mov     esi, eax
0x140028a80  test    eax, eax
0x140028a82  jz      short loc_140028AAE
0x140028a84  mov     [rsp+360h+samDesired], eax
0x140028a88  lea     rax, ?REG_VALUE_NAME_CRC_CHECKSUM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "CrcChecksum"
0x140028a8f  mov     qword ptr [rsp+360h+dwOptions], rax
0x140028a94  lea     r9, aFailedToWriteR; "Failed to write registry value %S: (%d)"
0x140028a9b  mov     r8d, 516h
0x140028aa1  mov     rdx, r12
0x140028aa4  mov     ecx, r14d
0x140028aa7  call    AslLogCallPrintf
0x140028aac  mov     edi, esi
0x140028aae  mov     [rsp+360h+samDesired], 10h; cbData
0x140028ab6  lea     rax, [r13+14h]
0x140028aba  mov     qword ptr [rsp+360h+dwOptions], rax; lpData
0x140028abf  mov     r9d, 3; dwType
0x140028ac5  xor     r8d, r8d; Reserved
0x140028ac8  lea     rdx, ?REG_VALUE_NAME_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "DatabaseId"
0x140028acf  mov     rcx, [rsp+360h+var_310]; hKey
0x140028ad4  call    cs:__imp_RegSetValueExW
0x140028ada  mov     esi, eax
0x140028adc  test    eax, eax
0x140028ade  jz      short loc_140028B0A
0x140028ae0  mov     [rsp+360h+samDesired], eax
0x140028ae4  lea     rax, ?REG_VALUE_NAME_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "DatabaseId"
0x140028aeb  mov     qword ptr [rsp+360h+dwOptions], rax
0x140028af0  lea     r9, aFailedToWriteR; "Failed to write registry value %S: (%d)"
0x140028af7  mov     r8d, 517h
0x140028afd  mov     rdx, r12
0x140028b00  mov     ecx, r14d
0x140028b03  call    AslLogCallPrintf
0x140028b08  mov     edi, esi
0x140028b0a  mov     eax, [r13+34h]
0x140028b0e  mov     dword ptr [rsp+360h+Data], eax
0x140028b12  mov     r9d, 4; dwType
0x140028b18  mov     [rsp+360h+samDesired], r9d; cbData
0x140028b1d  lea     rax, [rsp+360h+Data]
0x140028b22  mov     qword ptr [rsp+360h+dwOptions], rax; lpData
0x140028b27  xor     r8d, r8d; Reserved
0x140028b2a  lea     rdx, ?REG_VALUE_NAME_TARGET_DATABASE_CHECKSUM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "TargetDatabaseChecksum"
0x140028b31  mov     rcx, [rsp+360h+var_310]; hKey
0x140028b36  call    cs:__imp_RegSetValueExW
0x140028b3c  mov     esi, eax
0x140028b3e  test    eax, eax
0x140028b40  jz      short loc_140028B6C
0x140028b42  mov     [rsp+360h+samDesired], eax
0x140028b46  lea     rax, ?REG_VALUE_NAME_TARGET_DATABASE_CHECKSUM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "TargetDatabaseChecksum"
0x140028b4d  mov     qword ptr [rsp+360h+dwOptions], rax
0x140028b52  lea     r9, aFailedToWriteR; "Failed to write registry value %S: (%d)"
0x140028b59  mov     r8d, 518h
0x140028b5f  mov     rdx, r12
0x140028b62  mov     ecx, r14d
0x140028b65  call    AslLogCallPrintf
0x140028b6a  mov     edi, esi
0x140028b6c  lea     rax, [r13+24h]
0x140028b70  mov     [rsp+360h+samDesired], 10h; cbData
0x140028b78  mov     qword ptr [rsp+360h+dwOptions], rax; lpData
0x140028b7d  mov     r9d, 3; dwType
0x140028b83  xor     r8d, r8d; Reserved
0x140028b86  lea     rdx, ?REG_VALUE_NAME_TARGET_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "TargetDatabaseId"
0x140028b8d  mov     rcx, [rsp+360h+var_310]; hKey
0x140028b92  call    cs:__imp_RegSetValueExW
0x140028b98  mov     esi, eax
0x140028b9a  test    eax, eax
0x140028b9c  jz      short loc_140028BC8
0x140028b9e  mov     [rsp+360h+samDesired], eax
0x140028ba2  lea     rax, ?REG_VALUE_NAME_TARGET_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "TargetDatabaseId"
0x140028ba9  mov     qword ptr [rsp+360h+dwOptions], rax
0x140028bae  lea     r9, aFailedToWriteR; "Failed to write registry value %S: (%d)"
0x140028bb5  mov     r8d, 519h
0x140028bbb  mov     rdx, r12
0x140028bbe  mov     ecx, r14d
0x140028bc1  call    AslLogCallPrintf
0x140028bc6  mov     edi, esi
0x140028bc8  mov     r8, [r13+0]; unsigned __int16 *
0x140028bcc  lea     rdx, ?REG_VALUE_NAME_FILE_PATH@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FilePath"
0x140028bd3  mov     rcx, [rsp+360h+var_310]; HKEY
0x140028bd8  call    ?WriteRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBG1@Z; Pca::MergeSdb::Utils::RegUtil::WriteRegValue(HKEY__ *,ushort const *,ushort const *)
0x140028bdd  mov     esi, eax
0x140028bdf  test    eax, eax
0x140028be1  jz      short loc_140028C0D
0x140028be3  mov     [rsp+360h+samDesired], eax
0x140028be7  lea     rax, ?REG_VALUE_NAME_FILE_PATH@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FilePath"
0x140028bee  mov     qword ptr [rsp+360h+dwOptions], rax
0x140028bf3  lea     r9, aFailedToWriteR; "Failed to write registry value %S: (%d)"
0x140028bfa  mov     r8d, 51Ah
0x140028c00  mov     rdx, r12
0x140028c03  mov     ecx, r14d
0x140028c06  call    AslLogCallPrintf
0x140028c0b  mov     edi, esi
0x140028c0d  mov     r8, [r13+60h]; unsigned __int16 *
  ... truncated ...
```
