# SmpLoadDataFromRegistry

- ea: `0x14000c638`
- end: `0x14000d410`
- name: `SmpLoadDataFromRegistry`
- size: `3544`
- prototype: `__int64 __fastcall(HANDLE EventHandle)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400146ac`

## callees

- `0x1400010ec`
- `0x140003450`
- `0x140004e30`
- `0x140009930`
- `0x14000a140`
- `0x14000b514`
- `0x14000c638`
- `0x14000d418`
- `0x14000d450`
- `0x14000d494`
- `0x14000d4c0`
- `0x14000e6c0`
- `0x14000e904`
- `0x14000ea00`
- `0x14000eb40`
- `0x140013a40`
- `0x1400143b0`
- `0x140014c70`
- `0x140014e2c`
- `0x140015660`
- `0x140015ae8`
- `0x140016018`
- `0x140016190`
- `0x1400165fc`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000c826`
- `ntdll!RtlInitUnicodeString` at `0x14000c85b`
- `ntdll!RtlInitUnicodeString` at `0x14000c826`
- `ntdll!RtlInitUnicodeString` at `0x14000c85b`
- `ntdll!NtClose` at `0x14000c8f9`
- `ntdll!NtClose` at `0x14000d153`
- `ntdll!NtClose` at `0x14000d15d`
- `ntdll!NtClose` at `0x14000d3b1`
- `ntdll!NtClose` at `0x14000c8f9`
- `ntdll!NtClose` at `0x14000d153`
- `ntdll!NtClose` at `0x14000d15d`
- `ntdll!NtClose` at `0x14000d3b1`
- `ntdll!NtQuerySystemInformation` at `0x14000cdbe`
- `ntdll!NtQuerySystemInformation` at `0x14000cdbe`
- `ntdll!RtlGetNtSystemRoot` at `0x14000c82c`
- `ntdll!RtlGetNtSystemRoot` at `0x14000c82c`
- `ntdll!NtOpenKey` at `0x14000c8ea`
- `ntdll!NtOpenKey` at `0x14000c93e`
- `ntdll!NtOpenKey` at `0x14000c8ea`
- `ntdll!NtOpenKey` at `0x14000c93e`
- `ntdll!NtOpenKey` at `0x14000c94a`
- `ntdll!RtlAllocateHeap` at `0x14000c9e2`
- `ntdll!RtlAllocateHeap` at `0x14000c9e2`
- `ntdll!RtlAllocateHeap` at `0x14000c9f0`
- `ntdll!RtlFreeHeap` at `0x14000d3a1`
- `ntdll!RtlFreeHeap` at `0x14000d3ce`
- `ntdll!RtlFreeHeap` at `0x14000d3a1`
- `ntdll!RtlFreeHeap` at `0x14000d3ce`
- `ntdll!NtSetValueKey` at `0x14000cae1`
- `ntdll!NtSetValueKey` at `0x14000cae1`
- `ntdll!NtSetValueKey` at `0x14000caed`
- `ntdll!RtlPrefixUnicodeString` at `0x14000ce36`
- `ntdll!RtlPrefixUnicodeString` at `0x14000ce36`
- `ntdll!NtDeleteValueKey` at `0x14000c971`
- `ntdll!NtDeleteValueKey` at `0x14000c971`
- `ntdll!NtInitializeRegistry` at `0x14000d0b5`
- `ntdll!NtInitializeRegistry` at `0x14000d0b5`
- `ntdll!RtlCreateEnvironment` at `0x14000c86e`
- `ntdll!RtlCreateEnvironment` at `0x14000c86e`
- `ntdll!RtlCreateEnvironment` at `0x14000c87a`
- `ntdll!NtQuerySystemInformationEx` at `0x14000c9a4`
- `ntdll!NtQuerySystemInformationEx` at `0x14000ca3f`
- `ntdll!NtQuerySystemInformationEx` at `0x14000c9a4`
- `ntdll!NtQuerySystemInformationEx` at `0x14000c9b3`
- `ntdll!NtQuerySystemInformationEx` at `0x14000ca3f`
- `ntdll!NtQuerySystemInformationEx` at `0x14000ca4b`
- `ntdll!RtlSetCurrentEnvironment` at `0x14000cb34`
- `ntdll!RtlSetCurrentEnvironment` at `0x14000cc85`
- `ntdll!RtlSetCurrentEnvironment` at `0x14000d3e5`
- `ntdll!RtlSetCurrentEnvironment` at `0x14000cb34`
- `ntdll!RtlSetCurrentEnvironment` at `0x14000cc85`
- `ntdll!RtlSetCurrentEnvironment` at `0x14000d3e5`
- `ntdll!RtlQueryRegistryValuesEx` at `0x14000cb54`
- `ntdll!RtlQueryRegistryValuesEx` at `0x14000d1dc`
- `ntdll!RtlQueryRegistryValuesEx` at `0x14000cb54`
- `ntdll!RtlQueryRegistryValuesEx` at `0x14000cb60`
- `ntdll!RtlQueryRegistryValuesEx` at `0x14000d1dc`
- `ntdll!NtCreateDirectoryObject` at `0x14000ccf3`
- `ntdll!NtCreateDirectoryObject` at `0x14000ccf3`
- `ntdll!NtCreateDirectoryObject` at `0x14000ccff`
- `ntdll!RtlEqualUnicodeString` at `0x14000ce12`
- `ntdll!RtlEqualUnicodeString` at `0x14000cebc`
- `ntdll!RtlEqualUnicodeString` at `0x14000ce12`
- `ntdll!RtlEqualUnicodeString` at `0x14000cebc`
- `ntdll!NtSerializeBoot` at `0x14000ced3`
- `ntdll!NtSetEvent` at `0x14000d093`
- `ntdll!NtSetEvent` at `0x14000d093`
- `ntdll!RtlQueryPerformanceFrequency` at `0x14000d0d8`
- `ntdll!RtlQueryPerformanceFrequency` at `0x14000d0d8`
- `ntdll!RtlQueryPerformanceCounter` at `0x14000d0eb`
- `ntdll!RtlQueryPerformanceCounter` at `0x14000d16e`
- `ntdll!RtlQueryPerformanceCounter` at `0x14000d0eb`
- `ntdll!RtlQueryPerformanceCounter` at `0x14000d16e`
- `ntdll!NtResumeThread` at `0x14000d124`
- `ntdll!NtResumeThread` at `0x14000d124`
- `ntdll!NtWaitForSingleObject` at `0x14000d133`
- `ntdll!NtWaitForSingleObject` at `0x14000d133`
- `ntdll!NtTerminateProcess` at `0x14000d149`
- `ntdll!NtTerminateProcess` at `0x14000d149`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000d1ba`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14000d1ba`
- `ntdll!TpAllocWork` at `0x14000d22c`
- `ntdll!TpAllocWork` at `0x14000d22c`
- `ntdll!TpAllocWork` at `0x14000d238`
- `ntdll!TpPostWork` at `0x14000d258`
- `ntdll!TpPostWork` at `0x14000d258`
- `ntdll!TpWaitForWork` at `0x14000d26d`
- `ntdll!TpWaitForWork` at `0x14000d26d`
- `ntdll!TpReleaseWork` at `0x14000d278`
- `ntdll!TpReleaseWork` at `0x14000d278`

## string_xrefs

- `0x14000c6a0`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`
- `0x14000c6cc`: `\Registry\Machine\System\CurrentControlSet\Control\Session Manager\Environment`
- `0x14000c8a0`: `SmpLoadDataFromRegistry`
- `0x14000cb0d`: `SmpLoadDataFromRegistry`
- `0x14000cef9`: `SmpLoadDataFromRegistry`
- `0x14000cf58`: `SmpLoadDataFromRegistry`
- `0x14000d1e9`: `SmpLoadDataFromRegistry`
- `0x14000d1d5`: `\REGISTRY\MACHINE\OSDATA\Session Manager`

## pseudocode

```c
__int64 __fastcall SmpLoadDataFromRegistry(HANDLE EventHandle)
{
  _WORD *v2; // r14
  char v3; // r15
  __int64 NtSystemRoot; // rax
  int Environment; // ebx
  __int64 (*v6)(void); // rax
  __int64 v7; // rdx
  _WORD *Heap; // rax
  __int64 v9; // r9
  unsigned __int16 i; // dx
  __int64 v11; // rax
  __int64 v12; // rax
  void *v13; // rax
  __int64 v14; // rdx
  PWSTR Buffer; // r8
  char v16; // al
  int v17; // eax
  __int64 v18; // r12
  int v19; // esi
  int PlatformBinary; // eax
  __int64 *v21; // rax
  __int64 v22; // rbx
  const UNICODE_STRING *v23; // rdi
  unsigned __int16 v24; // ax
  unsigned int v25; // edx
  __int16 v26; // ax
  int v27; // eax
  int v28; // eax
  int v29; // r8d
  __int64 *v30; // rbx
  __int64 *v31; // rdi
  int v32; // r8d
  __int64 *v33; // rdi
  __int64 *v34; // rbx
  int v35; // r8d
  __int64 *v36; // rdi
  __int64 *v37; // rbx
  __int64 v38; // rdi
  int v39; // r8d
  unsigned int v40; // ebx
  __int64 v41; // rcx
  unsigned int v42; // ebx
  int RegistryValues; // eax
  int DynamicEnvironmentVariables; // eax
  int v45; // r8d
  __int64 *v46; // rdi
  __int64 *v47; // rbx
  int v48; // r8d
  __int64 *v49; // rdi
  __int64 *v50; // rbx
  _BYTE v52[4]; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD Size[3]; // [rsp+34h] [rbp-CCh] BYREF
  int v54; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ReturnLength[4]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v56; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR OldEnvironment; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v63; // [rsp+C8h] [rbp-38h] BYREF
  const wchar_t *v64; // [rsp+D0h] [rbp-30h]
  _QWORD v65[2]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v66[3]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v67[4]; // [rsp+100h] [rbp+0h] BYREF
  int v68; // [rsp+104h] [rbp+4h]
  HANDLE Object; // [rsp+108h] [rbp+8h]
  HANDLE ThreadHandle; // [rsp+110h] [rbp+10h]
  char v71; // [rsp+156h] [rbp+56h]
  _DWORD SystemInformation[3]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v73; // [rsp+17Ch] [rbp+7Ch]
  wchar_t pszDest[256]; // [rsp+190h] [rbp+90h] BYREF

  v68 = 0;
  v56 = 0;
  v61 = 0;
  v60 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  memset_0(v67, 0, 0x64u);
  v65[0] = 7602290;
  v65[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT";
  v63 = 1310738;
  v64 = L"\\Sessions";
  v66[0] = 10354844;
  v66[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Session Manager\\Environment";
  v2 = 0;
  *(_QWORD *)&ValueName.Length = 2752552;
  ValueName.Buffer = L"NUMBER_OF_PROCESSORS";
  v3 = 0;
  memset(Size, 0, sizeof(Size));
  qword_140030A58 = (__int64)&SmpBootExecuteList;
  SmpBootExecuteList = (__int64)&SmpBootExecuteList;
  qword_140030A88 = (__int64)&SmpBootExecuteNoPnpSyncList;
  SmpBootExecuteNoPnpSyncList = (__int64)&SmpBootExecuteNoPnpSyncList;
  qword_140030A78 = (__int64)&SmpPlatformExecuteList;
  SmpPlatformExecuteList = (__int64)&SmpPlatformExecuteList;
  qword_140030AA8 = (__int64)&SmpSetupExecuteList;
  SmpSetupExecuteList = (__int64)&SmpSetupExecuteList;
  qword_140030A98 = (__int64)&SmpSetupExecuteNoPnpSyncList;
  SmpSetupExecuteNoPnpSyncList = (__int64)&SmpSetupExecuteNoPnpSyncList;
  qword_140030BC8 = (__int64)&SmpPagingFileList;
  SmpPagingFileList = (__int64)&SmpPagingFileList;
  qword_140030AC8 = (__int64)&SmpDosDevicesList;
  SmpDosDevicesList = (__int64)&SmpDosDevicesList;
  qword_140030AB8 = (__int64)&SmpFileRenameList;
  SmpFileRenameList = (__int64)&SmpFileRenameList;
  qword_140030AE8 = (__int64)&SmpKnownDllsList;
  SmpKnownDllsList = (__int64)&SmpKnownDllsList;
  qword_140030AD8 = (__int64)&SmpExcludeKnownDllsList;
  SmpExcludeKnownDllsList = (__int64)&SmpExcludeKnownDllsList;
  qword_140030B08 = (__int64)&SmpSubSystemsRequired;
  SmpSubSystemsRequired = (__int64)&SmpSubSystemsRequired;
  qword_140030AF8 = (__int64)&SmpSubSystemsToDefer;
  SmpSubSystemsToDefer = (__int64)&SmpSubSystemsToDefer;
  qword_140030BB8 = (__int64)&SmpExistingPageFilesList;
  SmpExistingPageFilesList = (__int64)&SmpExistingPageFilesList;
  v54 = 0;
  SmpClearTempFiles = 0;
  OldEnvironment = 0;
  v52[0] = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  NtSystemRoot = RtlGetNtSystemRoot();
  RtlStringCbPrintfW(&SmpTempDirNameBuffer, 0x20Au, L"\\??\\%s", NtSystemRoot);
  RtlInitUnicodeString(&SmpTempFilesDir, &SmpTempDirNameBuffer);
  Environment = RtlCreateEnvironment(1u, &SmpDefaultEnvironment);
  if ( Environment < 0 )
  {
    v6 = (__int64 (*)(void))RtlCreateEnvironment;
    v7 = 2320;
    SmpInitProgressByLine = 2318;
LABEL_3:
    SmpInitReturnStatus = Environment;
    SmpInitLastCall = (__int64)v6;
LABEL_4:
    SmpLogFailure("SmpLoadDataFromRegistry", v7, (unsigned int)Environment);
    goto LABEL_130;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v65;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey((PHANDLE)&Size[1], 0xF003Fu, &ObjectAttributes) >= 0 )
  {
    NtClose(*(HANDLE *)&Size[1]);
    *(_QWORD *)&Size[1] = 0;
    SmpMiniNTBoot = 1;
  }
  SmpReadSafeBootOption();
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v66;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Environment = NtOpenKey((PHANDLE)&Size[1], 0xF003Fu, &ObjectAttributes);
  if ( Environment < 0 )
  {
    v6 = (__int64 (*)(void))NtOpenKey;
    v7 = 2368;
    SmpInitProgressByLine = 2366;
    goto LABEL_3;
  }
  NtDeleteValueKey(*(HANDLE *)&Size[1], (PUNICODE_STRING)&SmpSafeBootEnvironmentValue);
  Size[0] = 0;
  v54 = 4;
  Environment = NtQuerySystemInformationEx(107, &v54, 4, 0, 0, Size);
  if ( Environment != -1073741820 )
  {
    v6 = (__int64 (*)(void))NtQuerySystemInformationEx;
    v7 = 2402;
    SmpInitProgressByLine = 2400;
    goto LABEL_3;
  }
  Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, Size[0]);
  v2 = Heap;
  if ( !Heap )
  {
    Environment = -1073741670;
    SmpInitProgressByLine = 2411;
    v7 = 2413;
    SmpInitReturnStatus = -1073741670;
    SmpInitLastCall = (__int64)RtlAllocateHeap;
    goto LABEL_4;
  }
  Environment = NtQuerySystemInformationEx(107, &v54, 4, Heap, Size[0], Size);
  if ( Environment < 0 )
  {
    v6 = (__int64 (*)(void))NtQuerySystemInformationEx;
    v7 = 2429;
    SmpInitProgressByLine = 2427;
    goto LABEL_3;
  }
  v9 = 0;
  for ( i = 0; i < v2[5]; v9 = HIBYTE(v2[24 * v11 + 16]) + (unsigned int)v9 )
    v11 = i++;
  RtlStringCbPrintfW(pszDest, 0x200u, L"%u", v9);
  v12 = -1;
  do
    ++v12;
  while ( pszDest[v12] );
  Environment = NtSetValueKey(*(HANDLE *)&Size[1], &ValueName, 0, 1u, pszDest, 2 * v12 + 2);
  if ( Environment < 0 )
  {
    v13 = NtSetValueKey;
    v14 = 2460;
    Buffer = ValueName.Buffer;
    SmpInitProgressByLine = 2458;
LABEL_21:
    SmpInitReturnStatus = Environment;
    SmpInitLastCall = (__int64)v13;
    SmpLogFailureString("SmpLoadDataFromRegistry", v14, Buffer, (unsigned int)Environment);
    goto LABEL_130;
  }
  RtlSetCurrentEnvironment(SmpDefaultEnvironment, &OldEnvironment);
  Environment = RtlQueryRegistryValuesEx(2, L"Session Manager", &SmpRegistryConfigurationTable);
  if ( Environment < 0 )
  {
    v6 = (__int64 (*)(void))RtlQueryRegistryValuesEx;
    v7 = 2484;
    SmpInitProgressByLine = 2482;
    goto LABEL_3;
  }
  Environment = SmpFinalizePathStrings();
  if ( Environment < 0 )
  {
    SmpInitProgressByLine = 2493;
    v6 = SmpFinalizePathStrings;
    v7 = 2495;
    goto LABEL_3;
  }
  SmpEventWrite(&SmssEvt_InitializeKnownDlls_Start);
  Environment = SmpOpenKnownDllsHandles(
                  &SmpKnownDllsObjectDirectoryName,
                  &SmpKnownDllsPathSuffix,
                  1,
                  &SmpKnownDllsObjectDirectory,
                  &SmpKnownDllsFileDirectory);
  if ( Environment < 0 )
  {
    SmpInitProgressByLine = 2514;
    v6 = (__int64 (*)(void))SmpOpenKnownDllsHandles;
    v7 = 2516;
    goto LABEL_3;
  }
  v16 = SmpLoadKnownDllsFlags;
  if ( SmpSoftBoot && (SmpLoadKnownDllsFlags & 2) != 0 )
  {
    v16 = SmpLoadKnownDllsFlags | 1;
    SmpLoadKnownDllsFlags |= 1u;
  }
  if ( (v16 & 1) != 0 )
  {
    Environment = SmpInitializeKnownDlls(1);
    if ( Environment < 0 )
    {
LABEL_36:
      SmpInitProgressByLine = 2545;
      v6 = (__int64 (*)(void))SmpInitializeKnownDlls;
      v7 = 2547;
      goto LABEL_3;
    }
    v17 = SmpInitializeKnownDllsAsync();
  }
  else
  {
    v17 = SmpInitializeKnownDlls(0);
  }
  Environment = v17;
  if ( v17 < 0 )
    goto LABEL_36;
  Environment = SmpInitializeSessionManagement();
  if ( Environment < 0 )
  {
    SmpInitProgressByLine = 2555;
    v6 = SmpInitializeSessionManagement;
    v7 = 2557;
    goto LABEL_3;
  }
  RtlSetCurrentEnvironment(OldEnvironment, &SmpDefaultEnvironment);
  OldEnvironment = 0;
  Environment = SmpInitializeDosDevices();
  if ( Environment < 0 )
  {
    SmpInitProgressByLine = 2574;
    v6 = SmpInitializeDosDevices;
    v7 = 2576;
    goto LABEL_3;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v63;
  ObjectAttributes.SecurityDescriptor = SmpPrimarySecurityDescriptor;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 208;
  ObjectAttributes.SecurityQualityOfService = 0;
  Environment = NtCreateDirectoryObject(&SmpSessionsObjectDirectory, 0xF000Fu, &ObjectAttributes);
  if ( Environment < 0 )
  {
    v13 = NtCreateDirectoryObject;
    v14 = 2604;
    Buffer = (PWSTR)v64;
    SmpInitProgressByLine = 2602;
    goto LABEL_21;
  }
  Environment = SmpCreateProtectedPrefixes();
  if ( Environment < 0 )
  {
    SmpInitProgressByLine = 2617;
    v6 = SmpCreateProtectedPrefixes;
    v7 = 2619;
    goto LABEL_3;
  }
  v18 = 0;
  *(_QWORD *)ReturnLength = 0;
  if ( SmpHostSmss )
  {
    if ( SmpMiniNTBoot || SmpSafeBootOption != -1 || SmpDisableWpbtExecution )
    {
      SystemInformation[0] = 1094930505;
      ReturnLength[0] = 0;
      v73 = 0;
      v19 = -1073741823;
      SystemInformation[1] = 1;
      SystemInformation[2] = 1414546007;
      if ( NtQuerySystemInformation(SystemFirmwareTableInformation, SystemInformation, 0x14u, ReturnLength) == -1073741789 )
        SmpSendPlatformBinaryStatus(2, 0, 0, 0);
    }
    else
    {
      PlatformBinary = SmpGetPlatformBinary(&DestinationString);
      v18 = *(_QWORD *)ReturnLength;
      v19 = PlatformBinary;
    }
  }
  else
  {
    v19 = -1073741823;
  }
  v21 = (__int64 *)SmpSetupExecuteList;
  v22 = SmpSetupExecuteList;
  if ( (__int64 *)SmpBootExecuteList != &SmpBootExecuteList )
  {
    if ( *(__int64 **)SmpBootExecuteList != &SmpBootExecuteList )
      goto LABEL_65;
    v23 = (const UNICODE_STRING *)(SmpBootExecuteList + 16);
    if ( !RtlEqualUnicodeString(&SmpAutoChkDefaultCommand, (PCUNICODE_STRING)(SmpBootExecuteList + 16), 1u)
      && (!SmpSoftBoot || !RtlPrefixUnicodeString(&SmpAutoChkKeyword, v23, 1u)) )
    {
      goto LABEL_65;
    }
    v21 = (__int64 *)SmpSetupExecuteList;
  }
  if ( v21 != &SmpSetupExecuteList
    && (*(__int64 **)v22 != &SmpSetupExecuteList
     || !SmpSoftBoot
     || (v24 = *(_WORD *)(v22 + 16), *(_OWORD *)ReturnLength = 0, v24 < 0x24u)
     || (LOWORD(ReturnLength[0]) = 36,
         v25 = (unsigned __int16)(v24 - 36),
         v26 = *(_WORD *)(v22 + 18) - v25,
         *(_QWORD *)&ReturnLength[2] = *(_QWORD *)(v22 + 24) + 2 * ((unsigned __int64)v25 >> 1),
         HIWORD(ReturnLength[0]) = v26,
         !RtlEqualUnicodeString(&SmpStateMigrationKeyword, (PCUNICODE_STRING)ReturnLength, 1u)))
    || v19 >= 0 )
  {
LABEL_65:
    v27 = SmpNtSerializeBoot();
    if ( v27 < 0 )
    {
      SmpInitProgressByLine = 2711;
      SmpInitReturnStatus = v27;
      SmpInitLastCall = NtSerializeBoot;
      SmpLogFailure("SmpLoadDataFromRegistry", 2713, (unsigned int)v27);
    }
  }
  SmpEventWrite(&SmssEvt_RunSecureKernelTrustlets_Start);
  if ( SmpHostSmss )
  {
    v28 = SmpRunSecureKernelTrustlets(v52);
    v3 = v52[0];
    if ( v28 < 0 )
    {
      if ( v52[0] )
      {
        SmpInitProgressByLine = 2728;
        SmpInitReturnStatus = v28;
        SmpInitLastCall = (__int64)SmpRunSecureKernelTrustlets;
        SmpLogFailure("SmpLoadDataFromRegistry", 2730, (unsigned int)v28);
      }
    }
  }
  SmpEventWrite(&SmssEvt_RunSecureKernelTrustlets_Stop);
  if ( !v3 && (__int64 *)SmpPlatformExecuteList != &SmpPlatformExecuteList )
  {
    SmpEventWrite(&SmssEvt_PlatformExecuteList_Start);
    v30 = (__int64 *)SmpPlatformExecuteList;
    do
    {
      v31 = v30;
      if ( SmpHostSmss )
        SmpExecuteCommand((_DWORD)v30 + 16, 0, v29, 0, 0);
      v30 = (__int64 *)*v30;
      SmpFreeSavedRegistryEntry(v31);
    }
    while ( v30 != &SmpPlatformExecuteList );
    SmpEventWrite(&SmssEvt_PlatformExecuteList_Stop);
  }
  if ( (__int64 *)SmpBootExecuteList != &SmpBootExecuteList )
  {
    SmpEventWrite(&SmssEvt_BootExecuteList_Start);
    v33 = (__int64 *)SmpBootExecuteList;
    do
    {
      v34 = v33;
      SmpExecuteCommand((_DWORD)v33 + 16, 0, v32, 0, 0);
      v33 = (__int64 *)*v33;
      SmpFreeSavedRegistryEntry(v34);
    }
    while ( v33 != &SmpBootExecuteList );
    SmpEventWrite(&SmssEvt_BootExecuteList_Stop);
  }
  if ( (__int64 *)SmpBootExecuteNoPnpSyncList != &SmpBootExecuteNoPnpSyncList )
  {
    SmpEventWrite(&SmssEvt_BootExecuteNoPnpSyncList_Start);
    v36 = (__int64 *)SmpBootExecuteNoPnpSyncList;
    do
    {
      v37 = v36;
      SmpExecuteCommand((_DWORD)v36 + 16, 0, v35, 0, 0);
      v36 = (__int64 *)*v36;
      SmpFreeSavedRegistryEntry(v37);
    }
    while ( v36 != &SmpBootExecuteNoPnpSyncList );
    SmpEventWrite(&SmssEvt_BootExecuteNoPnpSyncList_Stop);
  }
  if ( EventHandle )
    NtSetEvent(EventHandle, 0);
  SmpEventWrite(&SmssEvt_InitializeRegistry_Start);
  if ( SmpSoftBootSystemHiveReady )
    SmpReplaceSystemHiveOnSoftReboot();
  NtInitializeRegistry(0);
  SmpEventWrite(&SmssEvt_InitializeRegistry_Stop);
  if ( v19 >= 0 )
  {
    v38 = 0;
    if ( !(unsigned int)RtlQueryPerformanceFrequency(&v56) )
      v56 = 0;
    if ( !(unsigned int)RtlQueryPerformanceCounter(&v61) )
      v56 = 0;
    if ( (int)SmpExecuteCommand((unsigned int)&DestinationString, 0, v39, 32, (__int64)v67) < 0 )
    {
      v40 = 1;
    }
    else
    {
      if ( v71 >= 0 )
      {
        v40 = 3;
        NtTerminateProcess(Object, -1073740760);
      }
      else
      {
        v40 = 0;
        NtResumeThread(ThreadHandle, 0);
        NtWaitForSingleObject(Object, 0, 0);
      }
      NtClose(Object);
      NtClose(ThreadHandle);
    }
    if ( (unsigned int)RtlQueryPerformanceCounter(&v60) )
    {
      v41 = v56;
    }
    else
    {
      v41 = 0;
      v56 = 0;
    }
    if ( v41 > 0 )
      v38 = 1000 * (v60 - v61) / v41;
    SmpSendPlatformBinaryStatus(v40, v18, v38, &DestinationString);
  }
  v42 = 0;
  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    RegistryValues = RtlQueryRegistryValuesEx(
                       0,
                       L"\\REGISTRY\\MACHINE\\OSDATA\\Session Manager",
                       &SmpRegistryConfigurationTable2);
    if ( RegistryValues >= 0 )
      v42 = 1;
    else
      SmpLogFailure("SmpLoadDataFromRegistry", 2930, (unsigned int)RegistryValues);
  }
  if ( !SmpMiniNTBoot )
    SmpProcessFileRenames(v42);
  *(_QWORD *)ReturnLength = 0;
  Environment = TpAllocWork(ReturnLength, SmpAsyncMemoryConfiguration, 0, &SmpCallbackEnviron);
  if ( Environment < 0 )
  {
    v6 = (__int64 (*)(void))TpAllocWork;
    v7 = 2967;
    SmpInitProgressByLine = 2965;
    goto LABEL_3;
  }
  TpPostWork(*(_QWORD *)ReturnLength);
  if ( SmpWaitForPagingFiles )
    TpWaitForWork(*(_QWORD *)ReturnLength, 0);
  TpReleaseWork(*(_QWORD *)ReturnLength);
  DynamicEnvironmentVariables = SmpCreateDynamicEnvironmentVariables(*(HANDLE *)&Size[1]);
  Environment = DynamicEnvironmentVariables;
  if ( DynamicEnvironmentVariables >= 0 )
  {
    if ( (__int64 *)SmpSetupExecuteList != &SmpSetupExecuteList )
    {
      SmpEventWrite(&SmssEvt_SetupExecuteList_Start);
      v46 = (__int64 *)SmpSetupExecuteList;
      do
      {
        v47 = v46;
        SmpExecuteCommand((_DWORD)v46 + 16, 0, v45, 0, 0);
        v46 = (__int64 *)*v46;
        SmpFreeSavedRegistryEntry(v47);
      }
      while ( v46 != &SmpSetupExecuteList );
      SmpEventWrite(&SmssEvt_SetupExecuteList_Stop);
    }
    if ( (__int64 *)SmpSetupExecuteNoPnpSyncList != &SmpSetupExecuteNoPnpSyncList )
    {
      SmpEventWrite(&SmssEvt_SetupExecuteNoPnpSyncList_Start);
      v49 = (__int64 *)SmpSetupExecuteNoPnpSyncList;
      do
      {
        v50 = v49;
        SmpExecuteCommand((_DWORD)v49 + 16, 0, v48, 0, 0);
        v49 = (__int64 *)*v49;
        SmpFreeSavedRegistryEntry(v50);
      }
      while ( v49 != &SmpSetupExecuteNoPnpSyncList );
      SmpEventWrite(&SmssEvt_SetupExecuteNoPnpSyncList_Stop);
    }
    Environment = SmpConfigureSharedSessionData();
    if ( Environment < 0 )
    {
      SmpInitProgressByLine = 3044;
      v6 = SmpConfigureSharedSessionData;
      v7 = 3046;
      goto LABEL_3;
    }
    SmpTranslateSystemPartitionInformation();
    Environment = 0;
  }
  else
  {
    SmpInitProgressByLine = 2988;
    SmpInitReturnStatus = DynamicEnvironmentVariables;
    SmpInitLastCall = (__int64)SmpCreateDynamicEnvironmentVariables;
  }
LABEL_130:
  if ( DestinationString.Buffer )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, DestinationString.Buffer);
  if ( *(_QWORD *)&Size[1] )
    NtClose(*(HANDLE *)&Size[1]);
  if ( v2 )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v2);
  if ( OldEnvironment )
    RtlSetCurrentEnvironment(OldEnvironment, &SmpDefaultEnvironment);
  return (unsigned int)Environment;
}

```

## disassembly

```asm
0x14000c638  push    rbp
0x14000c63a  push    rbx
0x14000c63b  push    rsi
0x14000c63c  push    rdi
0x14000c63d  push    r12
0x14000c63f  push    r13
0x14000c641  push    r14
0x14000c643  push    r15
0x14000c645  lea     rbp, [rsp-2A8h]
0x14000c64d  sub     rsp, 3A8h
0x14000c654  mov     rax, cs:__security_cookie
0x14000c65b  xor     rax, rsp
0x14000c65e  mov     [rbp+2E0h+var_50], rax
0x14000c665  xorps   xmm0, xmm0
0x14000c668  xor     eax, eax
0x14000c66a  xor     esi, esi
0x14000c66c  mov     [rbp+2E0h+var_2DC], eax
0x14000c66f  mov     r13, rcx
0x14000c672  mov     [rsp+3E0h+var_388], rsi
0x14000c677  movups  xmmword ptr [rsp+3E0h+ObjectAttributes.ObjectName], xmm0
0x14000c67c  lea     r8d, [rax+64h]; Size
0x14000c680  mov     [rbp+2E0h+var_330], rsi
0x14000c684  xor     edx, edx; Val
0x14000c686  mov     [rbp+2E0h+var_338], rsi
0x14000c68a  lea     rcx, [rbp+2E0h+var_2E0]; void *
0x14000c68e  movups  xmmword ptr [rsp+3E0h+ObjectAttributes.Length], xmm0
0x14000c693  movups  xmmword ptr [rbp+2E0h+ObjectAttributes+1Ch], xmm0
0x14000c697  movups  xmmword ptr [rbp+2E0h+DestinationString.Length], xmm0
0x14000c69b  call    memset_0
0x14000c6a0  lea     rax, aRegistryMachin_103; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000c6a7  mov     [rbp+2E0h+var_308], 740072h
0x14000c6af  mov     [rbp+2E0h+var_300], rax
0x14000c6b3  lea     rcx, [rbp+2E0h+DestinationString]; DestinationString
0x14000c6b7  lea     rax, aSessions; "\\Sessions"
0x14000c6be  mov     [rbp+2E0h+var_318], 140012h
0x14000c6c6  mov     [rbp+2E0h+var_310], rax
0x14000c6ca  xor     edx, edx; SourceString
0x14000c6cc  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000c6d3  mov     [rbp+2E0h+var_2F8], 9E009Ch
0x14000c6db  mov     [rbp+2E0h+var_2F0], rax
0x14000c6df  mov     r14d, esi
0x14000c6e2  lea     rax, aNumberOfProces; "NUMBER_OF_PROCESSORS"
0x14000c6e9  mov     qword ptr [rbp+2E0h+ValueName.Length], 2A0028h
0x14000c6f1  mov     [rbp+2E0h+ValueName.Buffer], rax
0x14000c6f5  mov     r15b, sil
0x14000c6f8  lea     rax, SmpBootExecuteList
0x14000c6ff  mov     dword ptr [rsp+3E0h+Size], esi
0x14000c703  mov     cs:qword_140030A58, rax
0x14000c70a  mov     cs:SmpBootExecuteList, rax
0x14000c711  lea     rax, SmpBootExecuteNoPnpSyncList
0x14000c718  mov     cs:qword_140030A88, rax
0x14000c71f  mov     cs:SmpBootExecuteNoPnpSyncList, rax
0x14000c726  lea     rax, SmpPlatformExecuteList
0x14000c72d  mov     cs:qword_140030A78, rax
0x14000c734  mov     cs:SmpPlatformExecuteList, rax
0x14000c73b  lea     rax, SmpSetupExecuteList
0x14000c742  mov     cs:qword_140030AA8, rax
0x14000c749  mov     cs:SmpSetupExecuteList, rax
0x14000c750  lea     rax, SmpSetupExecuteNoPnpSyncList
0x14000c757  mov     cs:qword_140030A98, rax
0x14000c75e  mov     cs:SmpSetupExecuteNoPnpSyncList, rax
0x14000c765  lea     rax, SmpPagingFileList
0x14000c76c  mov     cs:qword_140030BC8, rax
0x14000c773  mov     cs:SmpPagingFileList, rax
0x14000c77a  lea     rax, SmpDosDevicesList
0x14000c781  mov     cs:qword_140030AC8, rax
0x14000c788  mov     cs:SmpDosDevicesList, rax
0x14000c78f  lea     rax, SmpFileRenameList
0x14000c796  mov     cs:qword_140030AB8, rax
0x14000c79d  mov     cs:SmpFileRenameList, rax
0x14000c7a4  lea     rax, SmpKnownDllsList
0x14000c7ab  mov     cs:qword_140030AE8, rax
0x14000c7b2  mov     cs:SmpKnownDllsList, rax
0x14000c7b9  lea     rax, SmpExcludeKnownDllsList
0x14000c7c0  mov     cs:qword_140030AD8, rax
0x14000c7c7  mov     cs:SmpExcludeKnownDllsList, rax
0x14000c7ce  lea     rax, SmpSubSystemsRequired
0x14000c7d5  mov     cs:qword_140030B08, rax
0x14000c7dc  mov     cs:SmpSubSystemsRequired, rax
0x14000c7e3  lea     rax, SmpSubSystemsToDefer
0x14000c7ea  mov     cs:qword_140030AF8, rax
0x14000c7f1  mov     cs:SmpSubSystemsToDefer, rax
0x14000c7f8  lea     rax, SmpExistingPageFilesList
0x14000c7ff  mov     cs:qword_140030BB8, rax
0x14000c806  mov     cs:SmpExistingPageFilesList, rax
0x14000c80d  mov     [rsp+3E0h+var_3A0], esi
0x14000c811  mov     cs:SmpClearTempFiles, esi
0x14000c817  mov     qword ptr [rsp+3E0h+Size+4], rsi
0x14000c81c  mov     [rsp+3E0h+OldEnvironment], rsi
0x14000c821  mov     [rsp+3E0h+var_3B0], sil
0x14000c826  call    cs:__imp_RtlInitUnicodeString
0x14000c82c  call    cs:__imp_RtlGetNtSystemRoot
0x14000c832  mov     r9, rax
0x14000c835  lea     r8, aS; "\\??\\%s"
0x14000c83c  mov     edx, 20Ah; cbDest
0x14000c841  lea     rcx, SmpTempDirNameBuffer; pszDest
0x14000c848  call    RtlStringCbPrintfW
0x14000c84d  lea     rdx, SmpTempDirNameBuffer; SourceString
0x14000c854  lea     rcx, SmpTempFilesDir; DestinationString
0x14000c85b  call    cs:__imp_RtlInitUnicodeString
0x14000c861  lea     edi, [rsi+1]
0x14000c864  mov     cl, dil; Inherit
0x14000c867  lea     rdx, SmpDefaultEnvironment; Environment
0x14000c86e  call    cs:__imp_RtlCreateEnvironment
0x14000c874  mov     ebx, eax
0x14000c876  test    eax, eax
0x14000c878  jns     short loc_14000C8B1
0x14000c87a  mov     rax, cs:__imp_RtlCreateEnvironment
0x14000c881  mov     edx, 910h
0x14000c886  mov     cs:SmpInitProgressByLine, 90Eh
0x14000c890  mov     cs:SmpInitReturnStatus, ebx
0x14000c896  mov     cs:SmpInitLastCall, rax
0x14000c89d  mov     r8d, ebx
0x14000c8a0  lea     rcx, aSmploaddatafro; "SmpLoadDataFromRegistry"
0x14000c8a7  call    SmpLogFailure
0x14000c8ac  jmp     loc_14000D388
0x14000c8b1  lea     rax, [rbp+2E0h+var_308]
0x14000c8b5  mov     [rsp+3E0h+ObjectAttributes.Length], 30h ; '0'
0x14000c8bd  xorps   xmm0, xmm0
0x14000c8c0  mov     [rsp+3E0h+ObjectAttributes.RootDirectory], rsi
0x14000c8c5  mov     r12d, 0F003Fh
0x14000c8cb  mov     [rsp+3E0h+ObjectAttributes.ObjectName], rax
0x14000c8d0  mov     ebx, 40h ; '@'
0x14000c8d5  lea     r8, [rsp+3E0h+ObjectAttributes]; ObjectAttributes
0x14000c8da  mov     edx, r12d; DesiredAccess
0x14000c8dd  mov     [rbp+2E0h+ObjectAttributes.Attributes], ebx
0x14000c8e0  lea     rcx, [rsp+3E0h+Size+4]; KeyHandle
0x14000c8e5  movdqu  xmmword ptr [rbp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000c8ea  call    cs:__imp_NtOpenKey
0x14000c8f0  test    eax, eax
0x14000c8f2  js      short loc_14000C90B
0x14000c8f4  mov     rcx, qword ptr [rsp+3E0h+Size+4]; Handle
0x14000c8f9  call    cs:__imp_NtClose
0x14000c8ff  mov     qword ptr [rsp+3E0h+Size+4], rsi
0x14000c904  mov     cs:SmpMiniNTBoot, dil
0x14000c90b  call    SmpReadSafeBootOption
0x14000c910  lea     rax, [rbp+2E0h+var_2F8]
0x14000c914  mov     [rsp+3E0h+ObjectAttributes.Length], 30h ; '0'
0x14000c91c  xorps   xmm0, xmm0
0x14000c91f  mov     [rsp+3E0h+ObjectAttributes.ObjectName], rax
0x14000c924  lea     r8, [rsp+3E0h+ObjectAttributes]; ObjectAttributes
0x14000c929  mov     [rsp+3E0h+ObjectAttributes.RootDirectory], rsi
0x14000c92e  mov     edx, r12d; DesiredAccess
0x14000c931  mov     [rbp+2E0h+ObjectAttributes.Attributes], ebx
0x14000c934  lea     rcx, [rsp+3E0h+Size+4]; KeyHandle
0x14000c939  movdqu  xmmword ptr [rbp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000c93e  call    cs:__imp_NtOpenKey
0x14000c944  mov     ebx, eax
0x14000c946  test    eax, eax
0x14000c948  jns     short loc_14000C965
0x14000c94a  mov     rax, cs:__imp_NtOpenKey
0x14000c951  mov     edx, 940h
0x14000c956  mov     cs:SmpInitProgressByLine, 93Eh
0x14000c960  jmp     loc_14000C890
0x14000c965  mov     rcx, qword ptr [rsp+3E0h+Size+4]; KeyHandle
0x14000c96a  lea     rdx, SmpSafeBootEnvironmentValue; ValueName
0x14000c971  call    cs:__imp_NtDeleteValueKey
0x14000c977  mov     r12d, 4
0x14000c97d  mov     dword ptr [rsp+3E0h+Size], esi
0x14000c981  lea     rax, [rsp+3E0h+Size]
0x14000c986  mov     [rsp+3E0h+var_3A0], r12d
0x14000c98b  mov     qword ptr [rsp+3E0h+DataSize], rax
0x14000c990  lea     rdx, [rsp+3E0h+var_3A0]
0x14000c995  xor     r9d, r9d
0x14000c998  mov     dword ptr [rsp+3E0h+Data], esi
0x14000c99c  lea     ecx, [r12+67h]
0x14000c9a1  mov     r8d, r12d
0x14000c9a4  call    cs:__imp_NtQuerySystemInformationEx
0x14000c9aa  mov     ebx, eax
0x14000c9ac  cmp     eax, 0C0000004h
0x14000c9b1  jz      short loc_14000C9CE
0x14000c9b3  mov     rax, cs:__imp_NtQuerySystemInformationEx
0x14000c9ba  mov     edx, 962h
0x14000c9bf  mov     cs:SmpInitProgressByLine, 960h
0x14000c9c9  jmp     loc_14000C890
0x14000c9ce  mov     rcx, gs:60h
0x14000c9d7  xor     edx, edx; Flags
0x14000c9d9  mov     r8d, dword ptr [rsp+3E0h+Size]; Size
0x14000c9de  mov     rcx, [rcx+30h]; HeapHandle
0x14000c9e2  call    cs:__imp_RtlAllocateHeap
0x14000c9e8  mov     r14, rax
0x14000c9eb  test    rax, rax
0x14000c9ee  jnz     short loc_14000CA1D
0x14000c9f0  mov     rcx, cs:__imp_RtlAllocateHeap
0x14000c9f7  mov     ebx, 0C000009Ah
0x14000c9fc  mov     cs:SmpInitProgressByLine, 96Bh
0x14000ca06  mov     edx, 96Dh
0x14000ca0b  mov     cs:SmpInitReturnStatus, ebx
0x14000ca11  mov     cs:SmpInitLastCall, rcx
0x14000ca18  jmp     loc_14000C89D
0x14000ca1d  lea     rax, [rsp+3E0h+Size]
0x14000ca22  mov     r9, r14
0x14000ca25  mov     qword ptr [rsp+3E0h+DataSize], rax
0x14000ca2a  lea     rdx, [rsp+3E0h+var_3A0]
0x14000ca2f  mov     eax, dword ptr [rsp+3E0h+Size]
0x14000ca33  mov     r8d, r12d
0x14000ca36  mov     ecx, 6Bh ; 'k'
0x14000ca3b  mov     dword ptr [rsp+3E0h+Data], eax
0x14000ca3f  call    cs:__imp_NtQuerySystemInformationEx
0x14000ca45  mov     ebx, eax
0x14000ca47  test    eax, eax
0x14000ca49  jns     short loc_14000CA66
0x14000ca4b  mov     rax, cs:__imp_NtQuerySystemInformationEx
0x14000ca52  mov     edx, 97Dh
0x14000ca57  mov     cs:SmpInitProgressByLine, 97Bh
0x14000ca61  jmp     loc_14000C890
0x14000ca66  mov     r9d, esi
0x14000ca69  mov     edx, esi
0x14000ca6b  cmp     si, [r14+0Ah]
0x14000ca70  jnb     short loc_14000CA8F
0x14000ca72  movzx   eax, dx
0x14000ca75  add     dx, di
0x14000ca78  lea     rcx, [rax+rax*2]
0x14000ca7c  add     rcx, rcx
0x14000ca7f  movzx   eax, byte ptr [r14+rcx*8+21h]
0x14000ca85  add     r9d, eax
0x14000ca88  cmp     dx, [r14+0Ah]
0x14000ca8d  jb      short loc_14000CA72
0x14000ca8f  lea     r8, aU; "%u"
0x14000ca96  mov     edx, 200h; cbDest
0x14000ca9b  lea     rcx, [rbp+2E0h+pszDest]; pszDest
0x14000caa2  call    RtlStringCbPrintfW
0x14000caa7  lea     rcx, [rbp+2E0h+pszDest]
0x14000caae  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000cab2  inc     rax
0x14000cab5  cmp     [rcx+rax*2], si
0x14000cab9  jnz     short loc_14000CAB2
0x14000cabb  mov     rcx, qword ptr [rsp+3E0h+Size+4]; KeyHandle
0x14000cac0  lea     eax, ds:2[rax*2]
0x14000cac7  mov     [rsp+3E0h+DataSize], eax; DataSize
0x14000cacb  lea     rdx, [rbp+2E0h+ValueName]; ValueName
0x14000cacf  lea     rax, [rbp+2E0h+pszDest]
0x14000cad6  mov     r9d, edi; Type
0x14000cad9  xor     r8d, r8d; TitleIndex
0x14000cadc  mov     [rsp+3E0h+Data], rax; Data
0x14000cae1  call    cs:__imp_NtSetValueKey
0x14000cae7  mov     ebx, eax
0x14000cae9  test    eax, eax
0x14000caeb  jns     short loc_14000CB28
0x14000caed  mov     rax, cs:__imp_NtSetValueKey
0x14000caf4  mov     edx, 99Ch
0x14000caf9  mov     r8, [rbp+2E0h+ValueName.Buffer]
0x14000cafd  mov     cs:SmpInitProgressByLine, 99Ah
0x14000cb07  mov     cs:SmpInitReturnStatus, ebx
0x14000cb0d  lea     rcx, aSmploaddatafro; "SmpLoadDataFromRegistry"
0x14000cb14  mov     r9d, ebx
0x14000cb17  mov     cs:SmpInitLastCall, rax
0x14000cb1e  call    SmpLogFailureString
0x14000cb23  jmp     loc_14000D388
0x14000cb28  mov     rcx, cs:SmpDefaultEnvironment; NewEnvironment
0x14000cb2f  lea     rdx, [rsp+3E0h+OldEnvironment]; OldEnvironment
0x14000cb34  call    cs:__imp_RtlSetCurrentEnvironment
0x14000cb3a  xor     r9d, r9d
0x14000cb3d  mov     [rsp+3E0h+Data], rsi
0x14000cb42  lea     r8, SmpRegistryConfigurationTable
0x14000cb49  lea     rdx, Path; "Session Manager"
0x14000cb50  lea     ecx, [r9+2]
0x14000cb54  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000cb5a  mov     ebx, eax
0x14000cb5c  test    eax, eax
0x14000cb5e  jns     short loc_14000CB7B
0x14000cb60  mov     rax, cs:__imp_RtlQueryRegistryValuesEx
0x14000cb67  mov     edx, 9B4h
0x14000cb6c  mov     cs:SmpInitProgressByLine, 9B2h
0x14000cb76  jmp     loc_14000C890
0x14000cb7b  call    SmpFinalizePathStrings
0x14000cb80  mov     ebx, eax
0x14000cb82  test    eax, eax
0x14000cb84  jns     short loc_14000CBA1
0x14000cb86  mov     cs:SmpInitProgressByLine, 9BDh
0x14000cb90  lea     rax, SmpFinalizePathStrings
0x14000cb97  mov     edx, 9BFh
0x14000cb9c  jmp     loc_14000C890
0x14000cba1  lea     rcx, SmssEvt_InitializeKnownDlls_Start; EventDescriptor
0x14000cba8  call    SmpEventWrite
0x14000cbad  lea     rax, SmpKnownDllsFileDirectory
0x14000cbb4  mov     r8d, edi
0x14000cbb7  lea     r9, SmpKnownDllsObjectDirectory
0x14000cbbe  mov     [rsp+3E0h+Data], rax
0x14000cbc3  lea     rdx, SmpKnownDllsPathSuffix
0x14000cbca  lea     rcx, SmpKnownDllsObjectDirectoryName
0x14000cbd1  call    SmpOpenKnownDllsHandles
0x14000cbd6  mov     ebx, eax
0x14000cbd8  test    eax, eax
0x14000cbda  jns     short loc_14000CBF7
0x14000cbdc  mov     cs:SmpInitProgressByLine, 9D2h
0x14000cbe6  lea     rax, SmpOpenKnownDllsHandles
0x14000cbed  mov     edx, 9D4h
0x14000cbf2  jmp     loc_14000C890
0x14000cbf7  cmp     cs:SmpSoftBoot, sil
0x14000cbfe  mov     eax, cs:SmpLoadKnownDllsFlags
0x14000cc04  jz      short loc_14000CC12
0x14000cc06  test    al, 2
0x14000cc08  jz      short loc_14000CC12
0x14000cc0a  or      eax, edi
0x14000cc0c  mov     cs:SmpLoadKnownDllsFlags, eax
0x14000cc12  test    dil, al
0x14000cc15  jz      short loc_14000CC2B
0x14000cc17  mov     ecx, edi
0x14000cc19  call    SmpInitializeKnownDlls
  ... truncated ...
```
