# CmInitSystem1

- ea: `0x140c8ce24`
- end: `0x140c8d7fa`
- name: `CmInitSystem1`
- size: `2518`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `57`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140c52ae4`

## callees

- `0x1403f14a0`
- `0x140403380`
- `0x14040a7b0`
- `0x1404c2df0`
- `0x140541bf0`
- `0x14069c6e8`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd780`
- `0x1406f7380`
- `0x14072b02c`
- `0x140741834`
- `0x1407fb9a4`
- `0x1407fef5c`
- `0x140800e08`
- `0x140801044`
- `0x14080124c`
- `0x1408014a0`
- `0x140801e94`
- `0x140802500`
- `0x140802770`
- `0x140803948`
- `0x140803b68`
- `0x140803c00`
- `0x140803f08`
- `0x140861a20`
- `0x140894180`
- `0x1408976d0`
- `0x1408994e0`
- `0x1408999b8`
- `0x140899f00`
- `0x140899f90`
- `0x14089a090`
- `0x140aa178c`
- `0x140aebee4`
- `0x140bb19f0`
- `0x140bfa910`
- `0x140bfa950`
- `0x140bfaa30`
- `0x140c8ce24`
- `0x140c8dd08`
- `0x140c8e22c`
- `0x140c8e2e8`
- `0x140c8eb64`
- `0x140c8ec34`
- `0x140c8f090`
- `0x140c8f88c`
- `0x140c8fd58`
- `0x140c8fe74`
- `0x140c8ff74`

## import_xrefs

- `ext-ms-win-ntos-kcminitcfg-l1-1-0!CmSetInitMachineConfig` at `0x140c8d6e2`
- `ext-ms-win-ntos-kcminitcfg-l1-1-0!CmSetInitMachineConfig` at `0x140c8d6e2`

## pseudocode

```c
char __fastcall CmInitSystem1(ULONG_PTR BugCheckParameter3)
{
  __int64 i; // rax
  __int64 j; // rsi
  __int64 v4; // rbx
  int ObjectTypes; // eax
  int v6; // eax
  int v7; // eax
  int Hive; // eax
  int v9; // eax
  int inited; // eax
  void *v11; // rbx
  NTSTATUS v12; // eax
  ULONG_PTR v13; // rsi
  NTSTATUS v14; // eax
  ULONG_PTR v15; // rsi
  int v16; // eax
  ULONG_PTR v17; // rsi
  NTSTATUS v18; // eax
  ULONG_PTR v19; // rsi
  int v20; // eax
  int ControlSet; // eax
  __int64 k; // rcx
  __int64 v23; // rax
  int v24; // eax
  int v25; // r9d
  ULONG_PTR v26; // rsi
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int ExtendedControlSets; // eax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  int v35; // eax
  HANDLE KeyHandle; // [rsp+70h] [rbp-90h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  int v39[2]; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v41; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v42; // [rsp+D0h] [rbp-30h]
  struct _KAPC_STATE ApcState; // [rsp+D8h] [rbp-28h] BYREF
  ULONG_PTR BugCheckParameter4[54]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v45[116]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v42 = 0;
  KeyHandle = 0;
  *(_QWORD *)v39 = 0;
  v41 = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(v45, 0, sizeof(v45));
  DestinationString = 0;
  memset_0(BugCheckParameter4, 0, sizeof(BugCheckParameter4));
  memset(&ApcState, 0, sizeof(ApcState));
  CmpInitializeThreadInfo(&v41);
  CmpInitializeParseContext(v45);
  CmIoFileObjectType = (__int64)&IoFileObjectType;
  if ( InitIsWinPEMode )
  {
    BYTE6(NlsMbOemCodePageTag) = InitIsWinPEMode;
    BYTE4(NlsMbOemCodePageTag) = 1;
    CmpForceSynchronousMachineHiveLoad = 1;
  }
  if ( CmpVolatileBoot )
    BYTE4(NlsMbOemCodePageTag) = 1;
  if ( BYTE4(NlsMbOemCodePageTag) )
  {
    for ( i = 0; i != 7; ++i )
    {
      if ( CmpMachineHiveList[23 * i] )
        LODWORD(qword_140E0CFE0[23 * i]) |= 0x8000u;
    }
  }
  CmpInitializeRegistryNames();
  CmpInitGlobalQuotaAllowed();
  CmpHiveListHeadLock = 0;
  qword_140EDF748 = (__int64)&CmpAppHiveLoadList;
  CmpAppHiveLoadList = (__int64)&CmpAppHiveLoadList;
  qword_140FDBB50 = (__int64)&CmpHiveListHead;
  CmpHiveListHead = (__int64)&CmpHiveListHead;
  CmpLoadHiveLock = 0;
  CmpShutdownRundown.Count = 0;
  CmpHiveLoadUnloadRundown.Count = 0;
  CmpActiveHiveRundownEvent = 0;
  CmpActiveAppHiveUnloadEvent = 0;
  CmpAppHiveLoadListLock = 0;
  CmpRegistryLock = ExAllocateCacheAwarePushLock(1);
  CmpPostLock.Event.Header.WaitListHead.Blink = &CmpPostLock.Event.Header.WaitListHead;
  CmpPostLock.Event.Header.WaitListHead.Flink = &CmpPostLock.Event.Header.WaitListHead;
  qword_140FDA5B0 = (__int64)&CmpAsyncKernelPostList;
  CmpAsyncKernelPostList = (__int64)&CmpAsyncKernelPostList;
  CmpPostLock.Count = 1;
  CmpPostLock.Owner = 0;
  CmpPostLock.Contention = 0;
  LOWORD(CmpPostLock.Event.Header.Lock) = 1;
  CmpPostLock.Event.Header.Size = 6;
  CmpPostLock.Event.Header.SignalState = 0;
  CmpInitializeNameCache();
  ExInitializeLookasideListExInternal(&CmpKcbLookaside.L.ListHead, 0, 312, 1651199299, 0, 0);
  CmpInitSIDToHiveMapping();
  CmpAdminSystemFileSecurityDescriptor = (PSECURITY_DESCRIPTOR)CmpAdminSystemSecurityDescriptor();
  CmpInitializeTrustedInstallerSid();
  CmpInitializeDelayedCloseTable();
  CmpInitCallbacks();
  CmpInitializeMachineHiveLoadedCallbacks();
  CmpInitializeFreezeThaw();
  HvInitializeHashLibrary();
  CmpValidateGlobalFlushControlFlags();
  CmpInitializeGlobalKeyLockTracker();
  CmpInitializeTransactions();
  CmpVolumeManagerInitialize();
  for ( j = 0; j != 8; ++j )
  {
    v4 = 3 * j;
    RtlInitUnicodeString(&DestinationString, (&CmpBootLoadControl)[3 * j]);
    dword_140E0D58C[2 * v4] = CmpHashUnicodeComponent(&DestinationString);
  }
  ObjectTypes = CmpCreateObjectTypes();
  if ( ObjectTypes < 0 )
    KeBugCheckEx(0x67u, 1u, 1u, ObjectTypes, 0);
  v6 = CmpInitializeLightWeightTransactionType();
  if ( v6 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x18u, v6, 0);
  v7 = CmpInitializeRegistryProcess();
  if ( v7 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x19u, v7, 0);
  CmpAttachToRegistryProcess(&ApcState);
  CmpLockRegistryExclusive();
  CmpInitializePreloadedHives(BugCheckParameter3, 0);
  Hive = CmpCreateHive((unsigned int)&CmpMasterHive, 0, 1, 0, 0, 0, 0, 0x20000, 0, 0, 0, 0, (__int64)BugCheckParameter4);
  if ( Hive < 0 )
    KeBugCheckEx(0x67u, 1u, 2u, Hive, (ULONG_PTR)BugCheckParameter4);
  v9 = CmpInitializeKcbCache(CmpMasterHive, 128);
  if ( v9 < 0 )
    KeBugCheckEx(0x67u, 1u, 3u, v9, 0);
  if ( (int)CmpCreateRegistryRoot() < 0 )
    KeBugCheckEx(0x67u, 1u, 4u, 0, 0);
  inited = CmpInitSiloSupport(0);
  if ( inited < 0 )
    KeBugCheckEx(0x67u, 1u, 0x1Au, inited, 0);
  v11 = (void *)CmpHiveRootSecurityDescriptor();
  ObjectAttributes.ObjectName = &CmRegistryMachineName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v11;
  ObjectAttributes.SecurityQualityOfService = 0;
  v12 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, (PUNICODE_STRING)&nullclass, 0, 0);
  v13 = v12;
  if ( v12 < 0 )
  {
    ExFreePoolWithTag(v11, 0);
    KeBugCheckEx(0x67u, 1u, 5u, v13, 0);
  }
  ZwClose(KeyHandle);
  ObjectAttributes.ObjectName = &CmRegistryUserName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v11;
  ObjectAttributes.SecurityQualityOfService = 0;
  v14 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, (PUNICODE_STRING)&nullclass, 0, 0);
  v15 = v14;
  if ( v14 < 0 )
  {
    ExFreePoolWithTag(v11, 0);
    KeBugCheckEx(0x67u, 1u, 6u, v15, 0);
  }
  ZwClose(KeyHandle);
  ObjectAttributes.ObjectName = &CmRegistryAppName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v11;
  ObjectAttributes.SecurityQualityOfService = 0;
  v45[0] = 65;
  v16 = ObOpenObjectByName(
          (unsigned int)&ObjectAttributes,
          (_DWORD)CmKeyObjectType,
          0,
          0,
          131103,
          (__int64)v45,
          (__int64)&KeyHandle);
  v17 = v16;
  if ( v16 < 0 )
  {
    ExFreePoolWithTag(v11, 0);
    CmpCleanupParseContext(v45, 0);
    KeBugCheckEx(0x67u, 1u, 7u, v17, 0);
  }
  CmpCleanupParseContext(v45, 0);
  ZwClose(KeyHandle);
  ObjectAttributes.ObjectName = &CmRegistryContainersName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityDescriptor = v11;
  ObjectAttributes.SecurityQualityOfService = 0;
  v18 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, (PUNICODE_STRING)&nullclass, 0, 0);
  v19 = v18;
  if ( v18 < 0 )
  {
    ExFreePoolWithTag(v11, 0);
    KeBugCheckEx(0x67u, 1u, 8u, v19, 0);
  }
  ZwClose(KeyHandle);
  CmpNoMasterCreates = 1;
  CmpInitializeLoadOptions(BugCheckParameter3);
  v20 = CmpInitializePreloadedHives(BugCheckParameter3, 1);
  if ( v20 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x14u, v20, 0);
  ControlSet = CmpCreateControlSet(L"SYSTEM", 0);
  if ( ControlSet < 0 )
    KeBugCheckEx(0x67u, 1u, 0xDu, ControlSet, 0);
  if ( CmpLKGEnabled )
    *(_DWORD *)(MmWriteableSharedUserData + 752) |= 0x10u;
  if ( CmStateSeparationEnabled )
  {
    if ( CmStateSeparationAllHivesVolatile )
    {
      for ( k = 0; k != 7; ++k )
      {
        v23 = 23 * k;
        LODWORD(qword_140E0CFE0[v23]) |= 0x8000u;
      }
    }
    else
    {
      byte_140E0D0B4 = 0;
      if ( !CmStateSeparationDevMode )
      {
        dword_140E0D150 |= 0x8000u;
        dword_140E0D208 |= 0x8000u;
      }
      byte_140E0D394 = 0;
      byte_140E0D44B = 1;
    }
  }
  memset_0(BugCheckParameter4, 0, sizeof(BugCheckParameter4));
  v24 = CmpCreateHive((unsigned int)v39, 0, 1, 0, 0, 0, 0, 0x20000, 0, 0, 0, 0, (__int64)BugCheckParameter4);
  v26 = v24;
  if ( v24 < 0 )
  {
    ExFreePoolWithTag(v11, 0);
    KeBugCheckEx(0x67u, 1u, 0x10u, v26, (ULONG_PTR)BugCheckParameter4);
  }
  LOBYTE(v25) = 1;
  v27 = CmpLinkHiveToMaster(
          (int)&CmRegistryMachineHardwareName,
          0,
          v39[0],
          v25,
          dword_140E0CFE8,
          0,
          0,
          (__int64)v11,
          0,
          0,
          1,
          (__int64)BugCheckParameter4);
  if ( v27 )
    KeBugCheckEx(0x67u, 1u, 0x11u, v27, 0);
  CmpAddToHiveFileList(*(_QWORD *)v39);
  ExFreePoolWithTag(v11, 0);
  qword_140E0CFD8 = *(_QWORD *)v39;
  v28 = CmpInitializeHardwareConfiguration(BugCheckParameter3);
  if ( v28 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x12u, v28, 0);
  v29 = CmpInitializeDriverStores(BugCheckParameter3);
  if ( v29 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x13u, v29, 0);
  ExtendedControlSets = CmpCreateExtendedControlSets(BugCheckParameter3);
  if ( ExtendedControlSets < 0 )
    KeBugCheckEx(0x67u, 1u, 0x1Bu, ExtendedControlSets, 0);
  CmpCreateHardwareProfiles(BugCheckParameter3);
  CmSetInitMachineConfig(BugCheckParameter3);
  CmpUnlockRegistry();
  CmpMarkCurrentProfileDirty();
  v31 = CmpInitializeMachineDependentConfiguration(BugCheckParameter3);
  if ( v31 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x15u, v31, 0);
  v32 = CmpSetSystemValues(BugCheckParameter3);
  if ( v32 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x16u, v32, 0);
  CmpMigrateOOBELanguageToInstallationLanguage();
  ExFreePoolWithTag(CmpLoadOptions.Buffer, 0);
  v33 = *(_QWORD *)(BugCheckParameter3 + 240);
  if ( *(_DWORD *)v33 >= 0x68u )
  {
    if ( *(_QWORD *)(v33 + 96) )
    {
      v34 = CmpSetNetworkValue();
      if ( v34 < 0 )
        KeBugCheckEx(0x67u, 1u, 0x17u, v34, 0);
    }
  }
  v35 = CmFcInitSystem2();
  if ( v35 < 0 )
    KeBugCheckEx(0x67u, 1u, 0x1Au, v35, 0);
  CmpDetachFromRegistryProcess(&ApcState);
  KeGetCurrentThread()[1].UserAffinity = (_KAFFINITY_EX *)v41;
  return 1;
}

```

## disassembly

```asm
0x140c8ce24  push    rbp
0x140c8ce26  push    rbx
0x140c8ce27  push    rsi
0x140c8ce28  push    rdi
0x140c8ce29  push    r12
0x140c8ce2b  push    r13
0x140c8ce2d  push    r14
0x140c8ce2f  push    r15
0x140c8ce31  lea     rbp, [rsp-3A8h]
0x140c8ce39  sub     rsp, 4A8h
0x140c8ce40  mov     rax, cs:__security_cookie
0x140c8ce47  xor     rax, rsp
0x140c8ce4a  mov     [rbp+3E0h+var_50], rax
0x140c8ce51  xorps   xmm0, xmm0
0x140c8ce54  mov     rdi, rcx
0x140c8ce57  xor     eax, eax
0x140c8ce59  lea     rcx, [rbp+3E0h+var_220]; void *
0x140c8ce60  xor     r14d, r14d
0x140c8ce63  mov     [rbp+3E0h+var_410], rax
0x140c8ce67  movups  xmmword ptr [rbp+3E0h+ObjectAttributes.ObjectName], xmm0
0x140c8ce6b  xor     edx, edx; Val
0x140c8ce6d  mov     [rsp+4E0h+KeyHandle], r14
0x140c8ce72  mov     r8d, 1D0h; Size
0x140c8ce78  mov     qword ptr [rbp+3E0h+var_438], r14
0x140c8ce7c  movups  xmmword ptr [rbp+3E0h+ObjectAttributes+1Ch], xmm0
0x140c8ce80  movups  [rbp+3E0h+var_420], xmm0
0x140c8ce84  movups  xmmword ptr [rsp+4E0h+ObjectAttributes.Length], xmm0
0x140c8ce89  call    memset_0
0x140c8ce8e  xorps   xmm0, xmm0
0x140c8ce91  lea     rcx, [rbp+3E0h+var_3D0]; void *
0x140c8ce95  xor     edx, edx; Val
0x140c8ce97  mov     r8d, 1B0h; Size
0x140c8ce9d  movups  xmmword ptr [rbp+3E0h+DestinationString.Length], xmm0
0x140c8cea1  call    memset_0
0x140c8cea6  xorps   xmm0, xmm0
0x140c8cea9  lea     rcx, [rbp+3E0h+var_420]
0x140c8cead  movups  xmmword ptr [rbp+3E0h+ApcState.ApcListHead.Flink], xmm0
0x140c8ceb1  movups  xmmword ptr [rbp+3E0h+ApcState.ApcListHead.Flink+10h], xmm0
0x140c8ceb5  movups  xmmword ptr [rbp+3E0h+ApcState.Process], xmm0
0x140c8ceb9  call    CmpInitializeThreadInfo
0x140c8cebe  lea     rcx, [rbp+3E0h+var_220]
0x140c8cec5  call    CmpInitializeParseContext
0x140c8ceca  lea     rax, IoFileObjectType
0x140c8ced1  mov     cs:CmIoFileObjectType, rax
0x140c8ced8  lea     r15d, [r14+1]
0x140c8cedc  mov     al, cs:InitIsWinPEMode
0x140c8cee2  test    al, al
0x140c8cee4  jz      short loc_140C8CEFA
0x140c8cee6  mov     byte ptr cs:NlsMbOemCodePageTag+6, al
0x140c8ceec  mov     byte ptr cs:NlsMbOemCodePageTag+4, r15b
0x140c8cef3  mov     cs:CmpForceSynchronousMachineHiveLoad, r15b
0x140c8cefa  cmp     cs:CmpVolatileBoot, r14d
0x140c8cf01  jz      short loc_140C8CF0A
0x140c8cf03  mov     byte ptr cs:NlsMbOemCodePageTag+4, r15b
0x140c8cf0a  cmp     byte ptr cs:NlsMbOemCodePageTag+4, r14b
0x140c8cf11  lea     r12, cs:140000000h
0x140c8cf18  mov     r13d, 8000h
0x140c8cf1e  jz      short loc_140C8CF45
0x140c8cf20  mov     rax, r14
0x140c8cf23  imul    rcx, rax, 0B8h
0x140c8cf2a  cmp     [rcx+r12+0E0CFC0h], r14
0x140c8cf32  jz      short loc_140C8CF3C
0x140c8cf34  or      [rcx+r12+0E0CFE0h], r13d
0x140c8cf3c  add     rax, r15
0x140c8cf3f  cmp     rax, 7
0x140c8cf43  jnz     short loc_140C8CF23
0x140c8cf45  call    CmpInitializeRegistryNames
0x140c8cf4a  call    CmpInitGlobalQuotaAllowed
0x140c8cf4f  lea     rax, CmpAppHiveLoadList
0x140c8cf56  mov     cs:CmpHiveListHeadLock, r14
0x140c8cf5d  lea     r8, CmpHiveListHead
0x140c8cf64  mov     cs:qword_140EDF748, rax
0x140c8cf6b  mov     ecx, r15d
0x140c8cf6e  mov     cs:CmpAppHiveLoadList, rax
0x140c8cf75  mov     cs:qword_140FDBB50, r8
0x140c8cf7c  mov     cs:CmpHiveListHead, r8
0x140c8cf83  mov     cs:CmpLoadHiveLock, r14
0x140c8cf8a  mov     qword ptr cs:CmpShutdownRundown.___u0, r14
0x140c8cf91  mov     qword ptr cs:CmpHiveLoadUnloadRundown.___u0, r14
0x140c8cf98  mov     cs:CmpActiveHiveRundownEvent, r14
0x140c8cf9f  mov     cs:CmpActiveAppHiveUnloadEvent, r14
0x140c8cfa6  mov     cs:CmpAppHiveLoadListLock, r14
0x140c8cfad  call    ExAllocateCacheAwarePushLock
0x140c8cfb2  mov     cs:CmpRegistryLock, rax
0x140c8cfb9  lea     rax, CmpPostLock.Event.Header.WaitListHead
0x140c8cfc0  mov     cs:CmpPostLock.Event.Header.WaitListHead.Blink, rax
0x140c8cfc7  mov     cs:CmpPostLock.Event.Header.WaitListHead.Flink, rax
0x140c8cfce  lea     rax, CmpAsyncKernelPostList
0x140c8cfd5  mov     cs:qword_140FDA5B0, rax
0x140c8cfdc  mov     cs:CmpAsyncKernelPostList, rax
0x140c8cfe3  mov     cs:CmpPostLock.Count, r15d
0x140c8cfea  mov     cs:CmpPostLock.Owner, r14
0x140c8cff1  mov     cs:CmpPostLock.Contention, r14d
0x140c8cff8  mov     word ptr cs:CmpPostLock.Event.Header, r15w
0x140c8d000  mov     byte ptr cs:CmpPostLock.Event.Header+2, 6
0x140c8d007  mov     cs:CmpPostLock.Event.Header.SignalState, r14d
0x140c8d00e  call    CmpInitializeNameCache
0x140c8d013  mov     dword ptr [rsp+4E0h+var_4A0], r14d; int
0x140c8d018  lea     r8, CmSiFreeMemory
0x140c8d01f  mov     [rsp+4E0h+var_4A8], r14w; __int16
0x140c8d025  lea     rdx, CmpAllocatePoolLookaside
0x140c8d02c  mov     dword ptr [rsp+4E0h+Disposition], 626B4D43h; int
0x140c8d034  lea     rcx, CmpKcbLookaside; SListHead
0x140c8d03b  mov     qword ptr [rsp+4E0h+CreateOptions], 138h; __int64
0x140c8d044  mov     r9d, r15d
0x140c8d047  mov     dword ptr [rsp+4E0h+BugCheckParameter4], r14d; int
0x140c8d04c  call    ExInitializeLookasideListExInternal
0x140c8d051  call    CmpInitSIDToHiveMapping
0x140c8d056  call    CmpAdminSystemSecurityDescriptor
0x140c8d05b  mov     cs:CmpAdminSystemFileSecurityDescriptor, rax
0x140c8d062  call    CmpInitializeTrustedInstallerSid
0x140c8d067  call    CmpInitializeDelayedCloseTable
0x140c8d06c  call    CmpInitCallbacks
0x140c8d071  call    CmpInitializeMachineHiveLoadedCallbacks
0x140c8d076  call    CmpInitializeFreezeThaw
0x140c8d07b  call    HvInitializeHashLibrary
0x140c8d080  call    CmpValidateGlobalFlushControlFlags
0x140c8d085  call    CmpInitializeGlobalKeyLockTracker
0x140c8d08a  call    CmpInitializeTransactions
0x140c8d08f  call    CmpVolumeManagerInitialize
0x140c8d094  mov     rsi, r14
0x140c8d097  lea     rbx, [rsi+rsi*2]
0x140c8d09b  mov     rdx, rva CmpBootLoadControl[r12+rbx*8]; SourceString
0x140c8d0a3  lea     rcx, [rbp+3E0h+DestinationString]; DestinationString
0x140c8d0a7  call    RtlInitUnicodeString
0x140c8d0ac  lea     rcx, [rbp+3E0h+DestinationString]
0x140c8d0b0  call    CmpHashUnicodeComponent
0x140c8d0b5  add     rsi, r15
0x140c8d0b8  mov     rva dword_140E0D58C[r12+rbx*8], eax
0x140c8d0c0  cmp     rsi, 8
0x140c8d0c4  jnz     short loc_140C8D097
0x140c8d0c6  call    CmpCreateObjectTypes
0x140c8d0cb  test    eax, eax
0x140c8d0cd  jns     short loc_140C8D0E6
0x140c8d0cf  movsxd  r9, eax; BugCheckParameter3
0x140c8d0d2  lea     ecx, [rsi+5Fh]; BugCheckCode
0x140c8d0d5  mov     r8, r15; BugCheckParameter2
0x140c8d0d8  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8d0dd  mov     rdx, r15; BugCheckParameter1
0x140c8d0e0  call    KeBugCheckEx
0x140c8d0e6  call    CmpInitializeLightWeightTransactionType
0x140c8d0eb  test    eax, eax
0x140c8d0ed  jns     short loc_140C8D10A
0x140c8d0ef  mov     r8d, 18h; BugCheckParameter2
0x140c8d0f5  movsxd  r9, eax; BugCheckParameter3
0x140c8d0f8  mov     rdx, r15; BugCheckParameter1
0x140c8d0fb  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8d100  lea     ecx, [r8+4Fh]; BugCheckCode
0x140c8d104  call    KeBugCheckEx
0x140c8d10a  call    CmpInitializeRegistryProcess
0x140c8d10f  test    eax, eax
0x140c8d111  jns     short loc_140C8D12E
0x140c8d113  mov     r8d, 19h; BugCheckParameter2
0x140c8d119  movsxd  r9, eax; BugCheckParameter3
0x140c8d11c  mov     rdx, r15; BugCheckParameter1
0x140c8d11f  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8d124  lea     ecx, [r8+4Eh]; BugCheckCode
0x140c8d128  call    KeBugCheckEx
0x140c8d12e  lea     rcx, [rbp+3E0h+ApcState]; ApcState
0x140c8d132  call    CmpAttachToRegistryProcess
0x140c8d137  call    CmpLockRegistryExclusive
0x140c8d13c  xor     edx, edx
0x140c8d13e  mov     rcx, rdi
0x140c8d141  call    CmpInitializePreloadedHives
0x140c8d146  lea     rax, [rbp+3E0h+var_3D0]
0x140c8d14a  xor     r9d, r9d
0x140c8d14d  mov     [rsp+4E0h+var_480], rax
0x140c8d152  lea     rcx, CmpMasterHive
0x140c8d159  mov     [rsp+4E0h+var_488], r14
0x140c8d15e  mov     r8d, r15d
0x140c8d161  mov     qword ptr [rsp+4E0h+var_490], r14
0x140c8d166  xor     edx, edx
0x140c8d168  mov     [rsp+4E0h+var_498], r14
0x140c8d16d  mov     [rsp+4E0h+var_4A0], r14
0x140c8d172  mov     dword ptr [rsp+4E0h+var_4A8], 20000h
0x140c8d17a  mov     [rsp+4E0h+Disposition], r14
0x140c8d17f  mov     qword ptr [rsp+4E0h+CreateOptions], r14
0x140c8d184  mov     [rsp+4E0h+BugCheckParameter4], r14
0x140c8d189  call    CmpCreateHive
0x140c8d18e  test    eax, eax
0x140c8d190  jns     short loc_140C8D1B1
0x140c8d192  mov     r8d, 2; BugCheckParameter2
0x140c8d198  movsxd  r9, eax; BugCheckParameter3
0x140c8d19b  lea     rax, [rbp+3E0h+var_3D0]
0x140c8d19f  mov     rdx, r15; BugCheckParameter1
0x140c8d1a2  mov     [rsp+4E0h+BugCheckParameter4], rax; BugCheckParameter4
0x140c8d1a7  lea     ecx, [r8+65h]; BugCheckCode
0x140c8d1ab  call    KeBugCheckEx
0x140c8d1b1  mov     rcx, cs:CmpMasterHive
0x140c8d1b8  mov     edx, 80h
0x140c8d1bd  call    CmpInitializeKcbCache
0x140c8d1c2  test    eax, eax
0x140c8d1c4  jns     short loc_140C8D1E1
0x140c8d1c6  mov     r8d, 3; BugCheckParameter2
0x140c8d1cc  movsxd  r9, eax; BugCheckParameter3
0x140c8d1cf  mov     rdx, r15; BugCheckParameter1
0x140c8d1d2  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8d1d7  lea     ecx, [r8+64h]; BugCheckCode
0x140c8d1db  call    KeBugCheckEx
0x140c8d1e1  call    CmpCreateRegistryRoot
0x140c8d1e6  test    eax, eax
0x140c8d1e8  jns     short loc_140C8D203
0x140c8d1ea  xor     r9d, r9d; BugCheckParameter3
0x140c8d1ed  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8d1f2  mov     rdx, r15; BugCheckParameter1
0x140c8d1f5  lea     r8d, [r9+4]; BugCheckParameter2
0x140c8d1f9  lea     ecx, [r9+67h]; BugCheckCode
0x140c8d1fd  call    KeBugCheckEx
0x140c8d203  xor     ecx, ecx
0x140c8d205  call    CmpInitSiloSupport
0x140c8d20a  test    eax, eax
0x140c8d20c  jns     short loc_140C8D229
0x140c8d20e  mov     r8d, 1Ah; BugCheckParameter2
0x140c8d214  movsxd  r9, eax; BugCheckParameter3
0x140c8d217  mov     rdx, r15; BugCheckParameter1
0x140c8d21a  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8d21f  lea     ecx, [r8+4Dh]; BugCheckCode
0x140c8d223  call    KeBugCheckEx
0x140c8d229  call    CmpHiveRootSecurityDescriptor
0x140c8d22e  mov     rbx, rax
0x140c8d231  mov     [rsp+4E0h+Disposition], r14; Disposition
0x140c8d236  lea     rax, CmRegistryMachineName
0x140c8d23d  mov     [rsp+4E0h+CreateOptions], r14d; CreateOptions
0x140c8d242  mov     [rbp+3E0h+ObjectAttributes.ObjectName], rax
0x140c8d246  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x140c8d24b  lea     rax, nullclass
0x140c8d252  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x140c8d25a  xor     r9d, r9d; TitleIndex
0x140c8d25d  mov     [rsp+4E0h+BugCheckParameter4], rax; Class
0x140c8d262  mov     edx, 2001Fh; DesiredAccess
0x140c8d267  mov     [rbp+3E0h+ObjectAttributes.RootDirectory], r14
0x140c8d26b  lea     rcx, [rsp+4E0h+KeyHandle]; KeyHandle
0x140c8d270  mov     [rbp+3E0h+ObjectAttributes.Attributes], 240h
0x140c8d277  mov     [rbp+3E0h+ObjectAttributes.SecurityDescriptor], rbx
0x140c8d27b  mov     [rbp+3E0h+ObjectAttributes.SecurityQualityOfService], r14
0x140c8d27f  call    ZwCreateKey
0x140c8d284  movsxd  rsi, eax
0x140c8d287  test    eax, eax
0x140c8d289  jns     short loc_140C8D2B0
0x140c8d28b  xor     edx, edx; Tag
0x140c8d28d  mov     rcx, rbx; P
0x140c8d290  call    ExFreePoolWithTag
0x140c8d295  mov     r8d, 5; BugCheckParameter2
0x140c8d29b  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8d2a0  mov     r9, rsi; BugCheckParameter3
0x140c8d2a3  mov     rdx, r15; BugCheckParameter1
0x140c8d2a6  lea     ecx, [r8+62h]; BugCheckCode
0x140c8d2aa  call    KeBugCheckEx
0x140c8d2b0  mov     rcx, [rsp+4E0h+KeyHandle]; Handle
0x140c8d2b5  call    ZwClose
0x140c8d2ba  lea     rax, CmRegistryUserName
0x140c8d2c1  mov     [rsp+4E0h+Disposition], r14; Disposition
0x140c8d2c6  mov     [rbp+3E0h+ObjectAttributes.ObjectName], rax
0x140c8d2ca  lea     r8, [rsp+4E0h+ObjectAttributes]; ObjectAttributes
0x140c8d2cf  lea     rax, nullclass
0x140c8d2d6  mov     [rsp+4E0h+CreateOptions], r14d; CreateOptions
0x140c8d2db  xor     r9d, r9d; TitleIndex
0x140c8d2de  mov     [rsp+4E0h+BugCheckParameter4], rax; Class
0x140c8d2e3  mov     edx, 2001Fh; DesiredAccess
0x140c8d2e8  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x140c8d2f0  lea     rcx, [rsp+4E0h+KeyHandle]; KeyHandle
0x140c8d2f5  mov     [rbp+3E0h+ObjectAttributes.RootDirectory], r14
0x140c8d2f9  mov     [rbp+3E0h+ObjectAttributes.Attributes], 240h
0x140c8d300  mov     [rbp+3E0h+ObjectAttributes.SecurityDescriptor], rbx
0x140c8d304  mov     [rbp+3E0h+ObjectAttributes.SecurityQualityOfService], r14
0x140c8d308  call    ZwCreateKey
0x140c8d30d  movsxd  rsi, eax
0x140c8d310  test    eax, eax
0x140c8d312  jns     short loc_140C8D339
0x140c8d314  xor     edx, edx; Tag
0x140c8d316  mov     rcx, rbx; P
0x140c8d319  call    ExFreePoolWithTag
0x140c8d31e  mov     r8d, 6; BugCheckParameter2
0x140c8d324  mov     [rsp+4E0h+BugCheckParameter4], r14; BugCheckParameter4
0x140c8d329  mov     r9, rsi; BugCheckParameter3
0x140c8d32c  mov     rdx, r15; BugCheckParameter1
0x140c8d32f  lea     ecx, [r8+61h]; BugCheckCode
0x140c8d333  call    KeBugCheckEx
0x140c8d339  mov     rcx, [rsp+4E0h+KeyHandle]; Handle
0x140c8d33e  call    ZwClose
0x140c8d343  mov     rdx, cs:CmKeyObjectType
0x140c8d34a  lea     rax, CmRegistryAppName
0x140c8d351  mov     [rbp+3E0h+ObjectAttributes.ObjectName], rax
0x140c8d355  lea     rcx, [rsp+4E0h+ObjectAttributes]
0x140c8d35a  lea     rax, [rsp+4E0h+KeyHandle]
0x140c8d35f  mov     [rsp+4E0h+ObjectAttributes.Length], 30h ; '0'
0x140c8d367  mov     [rsp+4E0h+Disposition], rax
0x140c8d36c  xor     r9d, r9d
0x140c8d36f  lea     rax, [rbp+3E0h+var_220]
0x140c8d376  mov     [rbp+3E0h+ObjectAttributes.RootDirectory], r14
0x140c8d37a  mov     qword ptr [rsp+4E0h+CreateOptions], rax
0x140c8d37f  xor     r8d, r8d
0x140c8d382  mov     dword ptr [rsp+4E0h+BugCheckParameter4], 2001Fh
0x140c8d38a  mov     [rbp+3E0h+ObjectAttributes.Attributes], 240h
0x140c8d391  mov     [rbp+3E0h+ObjectAttributes.SecurityDescriptor], rbx
0x140c8d395  mov     [rbp+3E0h+ObjectAttributes.SecurityQualityOfService], r14
0x140c8d399  mov     [rbp+3E0h+var_220], 41h ; 'A'
0x140c8d3a3  call    ObOpenObjectByName
0x140c8d3a8  xor     edx, edx; Tag
0x140c8d3aa  movsxd  rsi, eax
  ... truncated ...
```
