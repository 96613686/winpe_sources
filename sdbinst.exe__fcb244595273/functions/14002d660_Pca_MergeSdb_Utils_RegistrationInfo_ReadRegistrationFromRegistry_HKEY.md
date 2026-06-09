# Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry(HKEY__ *)

- ea: `0x14002d660`
- end: `0x14002dcdd`
- name: `?ReadRegistrationFromRegistry@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAKPEAUHKEY__@@@Z`
- size: `1661`
- prototype: `__int64 __fastcall(Pca::MergeSdb::Utils::RegistrationInfo *this, HKEY hkey)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140023638`
- `0x1400238c0`
- `0x14002a7a0`

## callees

- `0x14001008c`
- `0x140020f9c`
- `0x140021ee4`
- `0x140022210`
- `0x14002955c`
- `0x14002c15c`
- `0x14002d1dc`
- `0x14002d220`
- `0x14002d278`
- `0x14002d61c`
- `0x14002d660`
- `0x14002df00`
- `0x14002e134`
- `0x14002e420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002dae3`
- `KERNEL32!GetLastError` at `0x14002dbc2`
- `KERNEL32!GetLastError` at `0x14002dae3`
- `KERNEL32!GetLastError` at `0x14002dbc2`
- `KERNEL32!GetProcessHeap` at `0x14002daeb`
- `KERNEL32!GetProcessHeap` at `0x14002db88`
- `KERNEL32!GetProcessHeap` at `0x14002dbca`
- `KERNEL32!GetProcessHeap` at `0x14002dc28`
- `KERNEL32!GetProcessHeap` at `0x14002dc79`
- `KERNEL32!GetProcessHeap` at `0x14002dc94`
- `KERNEL32!GetProcessHeap` at `0x14002daeb`
- `KERNEL32!GetProcessHeap` at `0x14002db88`
- `KERNEL32!GetProcessHeap` at `0x14002dbca`
- `KERNEL32!GetProcessHeap` at `0x14002dc28`
- `KERNEL32!GetProcessHeap` at `0x14002dc79`
- `KERNEL32!GetProcessHeap` at `0x14002dc94`
- `KERNEL32!SetLastError` at `0x14002db01`
- `KERNEL32!SetLastError` at `0x14002dbe0`
- `KERNEL32!SetLastError` at `0x14002db01`
- `KERNEL32!SetLastError` at `0x14002dbe0`
- `KERNEL32!HeapFree` at `0x14002daf9`
- `KERNEL32!HeapFree` at `0x14002db96`
- `KERNEL32!HeapFree` at `0x14002dbd8`
- `KERNEL32!HeapFree` at `0x14002dc36`
- `KERNEL32!HeapFree` at `0x14002dc87`
- `KERNEL32!HeapFree` at `0x14002dca2`
- `KERNEL32!HeapFree` at `0x14002daf9`
- `KERNEL32!HeapFree` at `0x14002db96`
- `KERNEL32!HeapFree` at `0x14002dbd8`
- `KERNEL32!HeapFree` at `0x14002dc36`
- `KERNEL32!HeapFree` at `0x14002dc87`
- `KERNEL32!HeapFree` at `0x14002dca2`
- `ntdll!RtlDoesFileExists_U` at `0x14002dacc`
- `ntdll!RtlDoesFileExists_U` at `0x14002dacc`

## string_xrefs

- `0x14002d6ae`: `FilePath`
- `0x14002d6d8`: `FilePath`
- `0x14002d8c1`: `CompilerVersion`
- `0x14002d8d8`: `CompilerVersion`
- `0x14002d6c4`: `Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry`
- `0x14002db30`: `Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry`
- `0x14002db73`: `Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry`
- `0x14002dc07`: `Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry`
- `0x14002dc62`: `Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry`
- `0x14002d6bd`: `Failed to read registry value '%S' (%d)`
- `0x14002db23`: `KeyPathFromHKey failed to get the key path (%d)`
- `0x14002db66`: `KeyPathFromHKey returned an invalid registry key path (too short).`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry(
        Pca::MergeSdb::Utils::RegistrationInfo *this,
        HKEY hkey)
{
  int v4; // esi
  int RegValue; // eax
  unsigned int v6; // eax
  int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  BOOLEAN DoesFileExists_U; // al
  unsigned int v20; // eax
  unsigned int v21; // edi
  void *v22; // rbx
  unsigned __int64 v23; // rax
  HANDLE v24; // rax
  void *v25; // r15
  void *v26; // r14
  DWORD LastError; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v29; // rax
  unsigned int v30; // eax
  HANDLE v31; // rax
  HANDLE v32; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-89h] BYREF
  void *v35; // [rsp+38h] [rbp-81h] BYREF
  PCWSTR FileName; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v37[8]; // [rsp+48h] [rbp-71h] BYREF
  char v38; // [rsp+50h] [rbp-69h]
  struct _GUID v39; // [rsp+54h] [rbp-65h] BYREF
  struct _GUID v40; // [rsp+64h] [rbp-55h] BYREF
  unsigned int v41; // [rsp+74h] [rbp-45h] BYREF
  unsigned int v42; // [rsp+78h] [rbp-41h] BYREF
  _BYTE v43[8]; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v44[3]; // [rsp+90h] [rbp-29h] BYREF
  unsigned int v45; // [rsp+9Ch] [rbp-1Dh] BYREF
  LPVOID v46; // [rsp+B0h] [rbp-9h]

  Pca::MergeSdb::Utils::RegistrationInfo::Reset(this);
  Pca::MergeSdb::Utils::SdbFileData::SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)&FileName);
  lpMem = 0;
  v4 = 0;
  RegValue = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"FilePath");
  if ( RegValue )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1619,
      "Failed to read registry value '%S' (%d)",
      L"FilePath",
      RegValue);
    v4 = 1;
  }
  v6 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"FileTime", (struct Pca::MergeSdb::Utils::TimeValue *)v37);
  if ( v6 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1620,
      "Failed to read registry value '%S' (%d)",
      L"FileTime",
      v6);
    ++v4;
  }
  v7 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"FriendlyName");
  if ( v7 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1621,
      "Failed to read registry value '%S' (%d)",
      L"FriendlyName",
      v7);
    ++v4;
  }
  v8 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"DatabaseId", &v39);
  if ( v8 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1622,
      "Failed to read registry value '%S' (%d)",
      L"DatabaseId",
      v8);
    ++v4;
  }
  v9 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"TargetDatabaseChecksum", &v41);
  if ( v9 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1623,
      "Failed to read registry value '%S' (%d)",
      L"TargetDatabaseChecksum",
      v9);
    ++v4;
  }
  v10 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"TargetDatabaseId", &v40);
  if ( v10 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1624,
      "Failed to read registry value '%S' (%d)",
      L"TargetDatabaseId",
      v10);
    ++v4;
  }
  v11 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"RuntimePlatform", &v42);
  if ( v11 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1625,
      "Failed to read registry value '%S' (%d)",
      L"RuntimePlatform",
      v11);
    ++v4;
  }
  v12 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"SdbTime", (struct Pca::MergeSdb::Utils::TimeValue *)v43);
  if ( v12 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1626,
      "Failed to read registry value '%S' (%d)",
      L"SdbTime",
      v12);
    ++v4;
  }
  v13 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"CompilerVersion");
  if ( v13 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1627,
      "Failed to read registry value '%S' (%d)",
      L"CompilerVersion",
      v13);
    ++v4;
  }
  v14 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"CrcChecksum", v44);
  if ( v14 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1628,
      "Failed to read registry value '%S' (%d)",
      L"CrcChecksum",
      v14);
    ++v4;
  }
  v15 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"MergeTarget");
  if ( v15 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1629,
      "Failed to read registry value '%S' (%d)",
      L"MergeTarget",
      v15);
    ++v4;
  }
  v16 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"RegisteredName");
  if ( v16 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1630,
      "Failed to read registry value '%S' (%d)",
      L"RegisteredName",
      v16);
    ++v4;
  }
  v17 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"InputTestOnly", &v45);
  if ( v17 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1631,
      "Failed to read registry value '%S' (%d)",
      L"InputTestOnly",
      v17);
    ++v4;
  }
  v18 = Pca::MergeSdb::Utils::RegUtil::ReadRegValue(hkey, L"MergeInputType");
  if ( v18 )
  {
    AslLogCallPrintf(
      3,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1633,
      "Failed to read registry value '%S' (%d)",
      L"MergeInputType",
      v18);
    ++v4;
  }
  if ( !FileName || (DoesFileExists_U = RtlDoesFileExists_U(FileName), v38 = 1, !DoesFileExists_U) )
    v38 = 0;
  lpMem = 0;
  v20 = Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey(&lpMem, hkey);
  v21 = v20;
  if ( v20 )
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1662,
      "KeyPathFromHKey failed to get the key path (%d)",
      v20);
    v22 = lpMem;
    goto LABEL_48;
  }
  v22 = lpMem;
  v23 = -1;
  do
    ++v23;
  while ( *((_WORD *)lpMem + v23) );
  if ( v23 > 0x12 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v35,
      (char *)lpMem + 36,
      -1);
    v25 = v35;
    v26 = v46;
    if ( v46 )
    {
      LastError = GetLastError();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
      SetLastError(LastError);
    }
    v46 = v25;
    Pca::MergeSdb::Utils::SdbFileData::Swap(this, (struct Pca::MergeSdb::Utils::SdbFileData *)&FileName);
    if ( v4 )
    {
      AslLogCallPrintf(
        1,
        "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
        1681,
        "Registration missing one or more values");
      *((_DWORD *)this + 36) = 5;
      if ( v22 )
      {
        v29 = GetProcessHeap();
        HeapFree(v29, 0, v22);
      }
      v21 = 299;
    }
    else
    {
      v30 = Pca::MergeSdb::Utils::RegistrationInfo::CheckRegisteredState(this);
      v21 = v30;
      if ( v30 )
      {
        AslLogCallPrintf(
          1,
          "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
          1690,
          "Failed to check the registered state (%d)",
          v30);
LABEL_48:
        if ( v22 )
        {
          v31 = GetProcessHeap();
          HeapFree(v31, 0, v22);
        }
        goto LABEL_53;
      }
      if ( v22 )
      {
        v32 = GetProcessHeap();
        HeapFree(v32, 0, v22);
      }
      v21 = 0;
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      "Pca::MergeSdb::Utils::RegistrationInfo::ReadRegistrationFromRegistry",
      1669,
      "KeyPathFromHKey returned an invalid registry key path (too short).");
    if ( v22 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v22);
    }
    v21 = 161;
  }
LABEL_53:
  Pca::MergeSdb::Utils::SdbFileData::~SdbFileData((Pca::MergeSdb::Utils::SdbFileData *)&FileName);
  return v21;
}

```

## disassembly

```asm
0x14002d660  mov     [rsp-8+arg_10], rbx
0x14002d665  push    rbp
0x14002d666  push    rsi
0x14002d667  push    rdi
0x14002d668  push    r12
0x14002d66a  push    r13
0x14002d66c  push    r14
0x14002d66e  push    r15
0x14002d670  lea     rbp, [rsp-27h]
0x14002d675  sub     rsp, 0E0h
0x14002d67c  mov     rax, cs:__security_cookie
0x14002d683  xor     rax, rsp
0x14002d686  mov     [rbp+57h+var_40], rax
0x14002d68a  mov     r14, rdx
0x14002d68d  mov     r13, rcx
0x14002d690  call    ?Reset@RegistrationInfo@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::RegistrationInfo::Reset(void)
0x14002d695  lea     rcx, [rbp+57h+FileName]; this
0x14002d699  call    ??0SdbFileData@Utils@MergeSdb@Pca@@QEAA@XZ; Pca::MergeSdb::Utils::SdbFileData::SdbFileData(void)
0x14002d69e  nop
0x14002d69f  xor     r12d, r12d
0x14002d6a2  mov     [rsp+110h+lpMem], r12
0x14002d6a7  mov     esi, r12d
0x14002d6aa  lea     r8, [rbp+57h+FileName]
0x14002d6ae  lea     rdx, ?REG_VALUE_NAME_FILE_PATH@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FilePath"
0x14002d6b5  mov     rcx, r14; hkey
0x14002d6b8  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d6bd  lea     rbx, aFailedToReadRe_0; "Failed to read registry value '%S' (%d)"
0x14002d6c4  lea     rdi, aPcaMergesdbUti_23; "Pca::MergeSdb::Utils::RegistrationInfo:"...
0x14002d6cb  lea     r15d, [r12+1]
0x14002d6d0  test    eax, eax
0x14002d6d2  jz      short loc_14002D6FD
0x14002d6d4  mov     [rsp+110h+var_E8], eax
0x14002d6d8  lea     rax, ?REG_VALUE_NAME_FILE_PATH@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FilePath"
0x14002d6df  mov     [rsp+110h+var_F0], rax
0x14002d6e4  mov     r9, rbx
0x14002d6e7  mov     r8d, 653h
0x14002d6ed  mov     rdx, rdi
0x14002d6f0  lea     ecx, [r12+3]
0x14002d6f5  call    AslLogCallPrintf
0x14002d6fa  mov     esi, r15d
0x14002d6fd  lea     r8, [rbp+57h+var_C8]; struct Pca::MergeSdb::Utils::TimeValue *
0x14002d701  lea     rdx, ?REG_VALUE_NAME_FILE_TIME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FileTime"
0x14002d708  mov     rcx, r14; HKEY
0x14002d70b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAVTimeValue@234@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,Pca::MergeSdb::Utils::TimeValue &)
0x14002d710  test    eax, eax
0x14002d712  jz      short loc_14002D73D
0x14002d714  mov     [rsp+110h+var_E8], eax
0x14002d718  lea     rax, ?REG_VALUE_NAME_FILE_TIME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FileTime"
0x14002d71f  mov     [rsp+110h+var_F0], rax
0x14002d724  mov     r9, rbx
0x14002d727  mov     r8d, 654h
0x14002d72d  mov     rdx, rdi
0x14002d730  mov     ecx, 3
0x14002d735  call    AslLogCallPrintf
0x14002d73a  add     esi, r15d
0x14002d73d  lea     r8, [rbp+57h+var_58]
0x14002d741  lea     rdx, ?REG_VALUE_NAME_FRIENDLY_NAME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FriendlyName"
0x14002d748  mov     rcx, r14; hkey
0x14002d74b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d750  test    eax, eax
0x14002d752  jz      short loc_14002D77D
0x14002d754  mov     [rsp+110h+var_E8], eax
0x14002d758  lea     rax, ?REG_VALUE_NAME_FRIENDLY_NAME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "FriendlyName"
0x14002d75f  mov     [rsp+110h+var_F0], rax
0x14002d764  mov     r9, rbx
0x14002d767  mov     r8d, 655h
0x14002d76d  mov     rdx, rdi
0x14002d770  mov     ecx, 3
0x14002d775  call    AslLogCallPrintf
0x14002d77a  add     esi, r15d
0x14002d77d  lea     r8, [rbp+57h+var_BC]; struct _GUID *
0x14002d781  lea     rdx, ?REG_VALUE_NAME_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "DatabaseId"
0x14002d788  mov     rcx, r14; HKEY
0x14002d78b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAU_GUID@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,_GUID &)
0x14002d790  test    eax, eax
0x14002d792  jz      short loc_14002D7BD
0x14002d794  mov     [rsp+110h+var_E8], eax
0x14002d798  lea     rax, ?REG_VALUE_NAME_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "DatabaseId"
0x14002d79f  mov     [rsp+110h+var_F0], rax
0x14002d7a4  mov     r9, rbx
0x14002d7a7  mov     r8d, 656h
0x14002d7ad  mov     rdx, rdi
0x14002d7b0  mov     ecx, 3
0x14002d7b5  call    AslLogCallPrintf
0x14002d7ba  add     esi, r15d
0x14002d7bd  lea     r8, [rbp+57h+var_9C]; unsigned int *
0x14002d7c1  lea     rdx, ?REG_VALUE_NAME_TARGET_DATABASE_CHECKSUM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "TargetDatabaseChecksum"
0x14002d7c8  mov     rcx, r14; HKEY
0x14002d7cb  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAK@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,ulong &)
0x14002d7d0  test    eax, eax
0x14002d7d2  jz      short loc_14002D7FD
0x14002d7d4  mov     [rsp+110h+var_E8], eax
0x14002d7d8  lea     rax, ?REG_VALUE_NAME_TARGET_DATABASE_CHECKSUM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "TargetDatabaseChecksum"
0x14002d7df  mov     [rsp+110h+var_F0], rax
0x14002d7e4  mov     r9, rbx
0x14002d7e7  mov     r8d, 657h
0x14002d7ed  mov     rdx, rdi
0x14002d7f0  mov     ecx, 3
0x14002d7f5  call    AslLogCallPrintf
0x14002d7fa  add     esi, r15d
0x14002d7fd  lea     r8, [rbp+57h+var_AC]; struct _GUID *
0x14002d801  lea     rdx, ?REG_VALUE_NAME_TARGET_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "TargetDatabaseId"
0x14002d808  mov     rcx, r14; HKEY
0x14002d80b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAU_GUID@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,_GUID &)
0x14002d810  test    eax, eax
0x14002d812  jz      short loc_14002D83D
0x14002d814  mov     [rsp+110h+var_E8], eax
0x14002d818  lea     rax, ?REG_VALUE_NAME_TARGET_DATABASE_ID@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "TargetDatabaseId"
0x14002d81f  mov     [rsp+110h+var_F0], rax
0x14002d824  mov     r9, rbx
0x14002d827  mov     r8d, 658h
0x14002d82d  mov     rdx, rdi
0x14002d830  mov     ecx, 3
0x14002d835  call    AslLogCallPrintf
0x14002d83a  add     esi, r15d
0x14002d83d  lea     r8, [rbp+57h+var_98]; unsigned int *
0x14002d841  lea     rdx, ?REG_VALUE_NAME_RUNTIME_PLATFORM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "RuntimePlatform"
0x14002d848  mov     rcx, r14; HKEY
0x14002d84b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAK@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,ulong &)
0x14002d850  test    eax, eax
0x14002d852  jz      short loc_14002D87D
0x14002d854  mov     [rsp+110h+var_E8], eax
0x14002d858  lea     rax, ?REG_VALUE_NAME_RUNTIME_PLATFORM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "RuntimePlatform"
0x14002d85f  mov     [rsp+110h+var_F0], rax
0x14002d864  mov     r9, rbx
0x14002d867  mov     r8d, 659h
0x14002d86d  mov     rdx, rdi
0x14002d870  mov     ecx, 3
0x14002d875  call    AslLogCallPrintf
0x14002d87a  add     esi, r15d
0x14002d87d  lea     r8, [rbp+57h+var_90]; struct Pca::MergeSdb::Utils::TimeValue *
0x14002d881  lea     rdx, ?REG_VALUE_NAME_SDB_TIME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "SdbTime"
0x14002d888  mov     rcx, r14; HKEY
0x14002d88b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAVTimeValue@234@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,Pca::MergeSdb::Utils::TimeValue &)
0x14002d890  test    eax, eax
0x14002d892  jz      short loc_14002D8BD
0x14002d894  mov     [rsp+110h+var_E8], eax
0x14002d898  lea     rax, ?REG_VALUE_NAME_SDB_TIME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "SdbTime"
0x14002d89f  mov     [rsp+110h+var_F0], rax
0x14002d8a4  mov     r9, rbx
0x14002d8a7  mov     r8d, 65Ah
0x14002d8ad  mov     rdx, rdi
0x14002d8b0  mov     ecx, 3
0x14002d8b5  call    AslLogCallPrintf
0x14002d8ba  add     esi, r15d
0x14002d8bd  lea     r8, [rbp+57h+var_88]
0x14002d8c1  lea     rdx, ?REG_VALUE_NAME_COMPILER_VERSION@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "CompilerVersion"
0x14002d8c8  mov     rcx, r14; hkey
0x14002d8cb  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d8d0  test    eax, eax
0x14002d8d2  jz      short loc_14002D8FD
0x14002d8d4  mov     [rsp+110h+var_E8], eax
0x14002d8d8  lea     rax, ?REG_VALUE_NAME_COMPILER_VERSION@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "CompilerVersion"
0x14002d8df  mov     [rsp+110h+var_F0], rax
0x14002d8e4  mov     r9, rbx
0x14002d8e7  mov     r8d, 65Bh
0x14002d8ed  mov     rdx, rdi
0x14002d8f0  mov     ecx, 3
0x14002d8f5  call    AslLogCallPrintf
0x14002d8fa  add     esi, r15d
0x14002d8fd  lea     r8, [rbp+57h+var_80]; unsigned int *
0x14002d901  lea     rdx, ?REG_VALUE_NAME_CRC_CHECKSUM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "CrcChecksum"
0x14002d908  mov     rcx, r14; HKEY
0x14002d90b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAK@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,ulong &)
0x14002d910  test    eax, eax
0x14002d912  jz      short loc_14002D93D
0x14002d914  mov     [rsp+110h+var_E8], eax
0x14002d918  lea     rax, ?REG_VALUE_NAME_CRC_CHECKSUM@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "CrcChecksum"
0x14002d91f  mov     [rsp+110h+var_F0], rax
0x14002d924  mov     r9, rbx
0x14002d927  mov     r8d, 65Ch
0x14002d92d  mov     rdx, rdi
0x14002d930  mov     ecx, 3
0x14002d935  call    AslLogCallPrintf
0x14002d93a  add     esi, r15d
0x14002d93d  lea     r8, [rbp+57h+var_70]
0x14002d941  lea     rdx, ?REG_VALUE_NAME_SDB_MERGETARGET@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "MergeTarget"
0x14002d948  mov     rcx, r14; hkey
0x14002d94b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d950  test    eax, eax
0x14002d952  jz      short loc_14002D97D
0x14002d954  mov     [rsp+110h+var_E8], eax
0x14002d958  lea     rax, ?REG_VALUE_NAME_SDB_MERGETARGET@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "MergeTarget"
0x14002d95f  mov     [rsp+110h+var_F0], rax
0x14002d964  mov     r9, rbx
0x14002d967  mov     r8d, 65Dh
0x14002d96d  mov     rdx, rdi
0x14002d970  mov     ecx, 3
0x14002d975  call    AslLogCallPrintf
0x14002d97a  add     esi, r15d
0x14002d97d  lea     r8, [rbp+57h+var_68]
0x14002d981  lea     rdx, ?REG_VALUE_NAME_REGISTERED_NAME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "RegisteredName"
0x14002d988  mov     rcx, r14; hkey
0x14002d98b  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002d990  test    eax, eax
0x14002d992  jz      short loc_14002D9BD
0x14002d994  mov     [rsp+110h+var_E8], eax
0x14002d998  lea     rax, ?REG_VALUE_NAME_REGISTERED_NAME@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "RegisteredName"
0x14002d99f  mov     [rsp+110h+var_F0], rax
0x14002d9a4  mov     r9, rbx
0x14002d9a7  mov     r8d, 65Eh
0x14002d9ad  mov     rdx, rdi
0x14002d9b0  mov     ecx, 3
0x14002d9b5  call    AslLogCallPrintf
0x14002d9ba  add     esi, r15d
0x14002d9bd  lea     r8, [rbp+57h+var_74]; unsigned int *
0x14002d9c1  lea     rdx, ?REG_VALUE_NAME_INPUT_TEST_ONLY@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "InputTestOnly"
0x14002d9c8  mov     rcx, r14; HKEY
0x14002d9cb  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAK@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,ulong &)
0x14002d9d0  test    eax, eax
0x14002d9d2  jz      short loc_14002D9FD
0x14002d9d4  mov     [rsp+110h+var_E8], eax
0x14002d9d8  lea     rax, ?REG_VALUE_NAME_INPUT_TEST_ONLY@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "InputTestOnly"
0x14002d9df  mov     [rsp+110h+var_F0], rax
0x14002d9e4  mov     r9, rbx
0x14002d9e7  mov     r8d, 65Fh
0x14002d9ed  mov     rdx, rdi
0x14002d9f0  mov     ecx, 3
0x14002d9f5  call    AslLogCallPrintf
0x14002d9fa  add     esi, r15d
0x14002d9fd  lea     r8, [rsp+110h+lpMem]
0x14002da02  lea     rdx, ?REG_VALUE_NAME_MERGE_INPUT_TYPE@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "MergeInputType"
0x14002da09  mov     rcx, r14; hkey
0x14002da0c  call    ?ReadRegValue@RegUtil@Utils@MergeSdb@Pca@@SAKPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Pca::MergeSdb::Utils::RegUtil::ReadRegValue(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x14002da11  test    eax, eax
0x14002da13  jz      short loc_14002DA3E
0x14002da15  mov     [rsp+110h+var_E8], eax
0x14002da19  lea     rax, ?REG_VALUE_NAME_MERGE_INPUT_TYPE@RegistrationInfo@Utils@MergeSdb@Pca@@0QBGB; "MergeInputType"
0x14002da20  mov     [rsp+110h+var_F0], rax
0x14002da25  mov     r9, rbx
0x14002da28  mov     r8d, 661h
0x14002da2e  mov     rdx, rdi
0x14002da31  mov     ecx, 3
0x14002da36  call    AslLogCallPrintf
0x14002da3b  add     esi, r15d
0x14002da3e  mov     rbx, [rsp+110h+lpMem]
0x14002da43  test    rbx, rbx
0x14002da46  jz      short loc_14002DA93
0x14002da48  mov     ecx, r12d
0x14002da4b  lea     r11, qword_1400311F0
0x14002da52  mov     eax, ecx
0x14002da54  lea     r10, [rax+rax*2]
0x14002da58  mov     rax, rbx
0x14002da5b  mov     r9, [r11+r10*8+8]
0x14002da60  sub     r9, rbx
0x14002da63  movzx   r8d, word ptr [rax]
0x14002da67  movzx   edx, word ptr [rax+r9]
0x14002da6c  sub     r8d, edx
0x14002da6f  jnz     short loc_14002DA79
0x14002da71  add     rax, 2
0x14002da75  test    edx, edx
0x14002da77  jnz     short loc_14002DA63
0x14002da79  test    r8d, r8d
0x14002da7c  jz      short loc_14002DA88
0x14002da7e  add     ecx, r15d
0x14002da81  cmp     ecx, 5
0x14002da84  jb      short loc_14002DA52
0x14002da86  jmp     short loc_14002DA93
0x14002da88  lea     rax, [r11+r10*8]
0x14002da8c  mov     [r13+98h], rax
0x14002da93  cmp     [r13+98h], r12
0x14002da9a  jnz     short loc_14002DAC3
0x14002da9c  test    rbx, rbx
0x14002da9f  jz      short loc_14002DAC3
0x14002daa1  mov     [rsp+110h+var_F0], rbx
0x14002daa6  lea     r9, aInputTypeSWasN; "Input type '%S' was not valid"
0x14002daad  mov     r8d, 66Eh
0x14002dab3  mov     rdx, rdi
0x14002dab6  mov     ecx, 3
0x14002dabb  call    AslLogCallPrintf
0x14002dac0  add     esi, r15d
0x14002dac3  mov     rcx, [rbp+57h+FileName]; FileName
0x14002dac7  test    rcx, rcx
0x14002daca  jz      short loc_14002DADA
0x14002dacc  call    cs:__imp_RtlDoesFileExists_U
0x14002dad2  test    al, al
0x14002dad4  mov     [rbp+57h+var_C0], r15b
0x14002dad8  jnz     short loc_14002DADE
0x14002dada  mov     [rbp+57h+var_C0], r12b
0x14002dade  test    rbx, rbx
0x14002dae1  jz      short loc_14002DB07
0x14002dae3  call    cs:__imp_GetLastError
0x14002dae9  mov     edi, eax
0x14002daeb  call    cs:__imp_GetProcessHeap
0x14002daf1  mov     rcx, rax; hHeap
0x14002daf4  mov     r8, rbx; lpMem
0x14002daf7  xor     edx, edx; dwFlags
0x14002daf9  call    cs:__imp_HeapFree
0x14002daff  mov     ecx, edi; dwErrCode
0x14002db01  call    cs:__imp_SetLastError
0x14002db07  mov     [rsp+110h+lpMem], r12
0x14002db0c  mov     rdx, r14
0x14002db0f  lea     rcx, [rsp+110h+lpMem]
0x14002db14  call    ?KeyPathFromHKey@RegUtil@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@@Z; Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,HKEY__ *)
0x14002db19  mov     edi, eax
0x14002db1b  test    eax, eax
0x14002db1d  jz      short loc_14002DB4A
0x14002db1f  mov     dword ptr [rsp+110h+var_F0], eax
0x14002db23  lea     r9, aKeypathfromhke_0; "KeyPathFromHKey failed to get the key p"...
0x14002db2a  mov     r8d, 67Eh
  ... truncated ...
```
