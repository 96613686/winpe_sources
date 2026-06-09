# SrvAdminInitialize

- ea: `0x14000fc18`
- end: `0x14001038c`
- name: `SrvAdminInitialize`
- size: `1908`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14005b3c8`

## callees

- `0x14000f780`
- `0x14000fc18`
- `0x14001389c`
- `0x140015790`
- `0x140021660`
- `0x140021d88`
- `0x140024b40`
- `0x140025184`
- `0x140029a24`
- `0x14002a3e0`
- `0x14002a840`
- `0x14004c180`
- `0x14004c210`
- `0x14004c2d4`
- `0x14004cbc8`
- `0x14004dbdc`
- `0x14004ede4`
- `0x140056010`
- `0x140057170`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000fd03`
- `ntoskrnl!IoDeleteDevice` at `0x14000fd03`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fc8b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000fc8b`
- `ntoskrnl!VerSetConditionMask` at `0x14000fd7a`
- `ntoskrnl!VerSetConditionMask` at `0x14000fd7a`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14000fd8f`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x14000fd8f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14000ff9e`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14000ff9e`
- `ntoskrnl!PoCreatePowerRequest` at `0x14001002f`
- `ntoskrnl!PoCreatePowerRequest` at `0x1400100f6`
- `ntoskrnl!PoCreatePowerRequest` at `0x14001002f`
- `ntoskrnl!PoCreatePowerRequest` at `0x1400100f6`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14001015c`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x1400101c2`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14001015c`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x1400101c2`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14000fe4b`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14000fe4b`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fe7a`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fe8d`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fea0`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000feb3`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fec6`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fed9`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fe7a`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fe8d`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fea0`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000feb3`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fec6`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000fed9`
- `ntoskrnl!EtwRegister` at `0x14000fdc3`
- `ntoskrnl!EtwRegister` at `0x14000fdc3`
- `ntoskrnl!IoCreateDevice` at `0x14000fcc0`
- `ntoskrnl!IoCreateDevice` at `0x14000fcc0`
- `ext-ms-win-kmpdc-l1-1-0!Pdcv2ActivationClientRegister` at `0x14001022d`
- `ext-ms-win-kmpdc-l1-1-0!Pdcv2ActivationClientRegister` at `0x14001022d`

## string_xrefs

- `0x14000ffae`: `srvsvc.dll`
- `0x140010089`: `srvsvc.dll`

## pseudocode

```c
__int64 __fastcall SrvAdminInitialize(PDRIVER_OBJECT DriverObject)
{
  int LocalMajorSequence; // ebx
  ULONGLONG v4; // rax
  int v5; // ecx
  int v6; // r8d
  NTSTATUS v7; // eax
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  int refreshed; // eax
  __int64 v11; // rsi
  __int64 v12; // rcx
  const wchar_t *v13; // rax
  __int16 v14; // cx
  const wchar_t *v15; // rax
  __int16 v16; // si
  int v17; // eax
  _COUNTED_REASON_CONTEXT Context; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v19[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  _OSVERSIONINFOEXW VersionInfo; // [rsp+A0h] [rbp-60h] BYREF

  v19[0] = 4;
  v19[1] = 4;
  v21 = 0;
  DestinationString = 0;
  memset(&Context, 0, sizeof(Context));
  v20 = 0;
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  RtlInitUnicodeString(&DestinationString, L"\\Device\\SrvAdmin");
  LocalMajorSequence = IoCreateDevice(DriverObject, 0, &DestinationString, 0x22u, 0x100u, 0, &SrvAdminDeviceObject);
  if ( LocalMajorSequence < 0 )
    goto LABEL_4;
  LocalMajorSequence = SrvLibApplyDeviceAcl(
                         (__int64)SrvAdminDeviceObject,
                         0x1F01FFu,
                         0x100003u,
                         0x1F01FFu,
                         0x100003u,
                         0);
  if ( LocalMajorSequence < 0 )
  {
    IoDeleteDevice(SrvAdminDeviceObject);
    SrvAdminDeviceObject = 0;
LABEL_4:
    SrvAdminCleanupEx();
    return (unsigned int)LocalMajorSequence;
  }
  SrvAdminInitMaxUsers();
  memset(&VersionInfo, 0, sizeof(VersionInfo));
  VersionInfo.dwOSVersionInfoSize = 284;
  VersionInfo.wProductType = 2;
  v4 = VerSetConditionMask(0, 0x80u, 3u);
  if ( RtlVerifyVersionInfo(&VersionInfo, 0x80u, v4) >= 0 )
  {
    v7 = EtwRegister(&SumProvider, 0, 0, &KSumRegHandle);
    if ( v7 < 0 )
    {
      v5 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids,
          (unsigned int)v7);
      }
    }
  }
  hProviderTable = (PEX_SPIN_LOCK)RfsTableCreate(v5, (unsigned int)v19, v6, 22, 0);
  if ( !hProviderTable )
  {
    LocalMajorSequence = -1073741670;
    goto LABEL_4;
  }
  RtlInitializeGenericTableAvl(
    &AliasTableAvl,
    SrvAdminAliasTableCompare,
    SrvAdminShareTableAllocate,
    SrvAdminShareTableFree,
    0);
  DefaultAlias = 0;
  qword_140036C18 = (__int64)&SrvAdminInstanceList;
  SrvAdminInstanceList = (__int64)&SrvAdminInstanceList;
  ExInitializeResourceLite(&ProviderLock);
  ExInitializeResourceLite(&AliasLock);
  ExInitializeResourceLite(&AnonymousLock);
  ExInitializeResourceLite(&SrvAdminNameLock);
  ExInitializeResourceLite(&SrvAdminInstanceListLock);
  ExInitializeResourceLite(&SrvAdminInstanceStartStopLock);
  LockInitialized = 1;
  LocalMajorSequence = SrvAdminInitializeFsctlPropertyList();
  if ( LocalMajorSequence < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_4;
    }
    v9 = 11;
    goto LABEL_19;
  }
  refreshed = SrvAdminRefreshFsctlPropertyList();
  if ( refreshed < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids,
      (unsigned int)refreshed);
  }
  SrvAdminRefreshAnonymousLists();
  SrvAdminRefreshAllowedServerNameList();
  ExInitializePagedLookasideList(&SrvAdminPagedList256, 0, 0, 0, 0x100u, 0x64614153u, 0x80u);
  Context.Flags = 2;
  SrvAdminPagedListInitialized = 1;
  v11 = 0x7FFF;
  Context.Version = 0;
  Context.ResourceFileName = 0;
  v12 = 0x7FFF;
  v13 = L"srvsvc.dll";
  while ( *v13 )
  {
    ++v13;
    if ( !--v12 )
      goto LABEL_30;
  }
  v14 = 2 * v12;
  Context.ResourceFileName.Buffer = L"srvsvc.dll";
  Context.ResourceFileName.Length = -2 - v14;
  Context.ResourceFileName.MaximumLength = -v14;
LABEL_30:
  Context.StringCount = 0;
  Context.ResourceReasonId = 106;
  Context.ReasonStrings = 0;
  LocalMajorSequence = PoCreatePowerRequest(&SrvPowerOpenFileRequest, SrvAdminDeviceObject, &Context);
  if ( LocalMajorSequence < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_4;
    }
    v9 = 13;
    goto LABEL_19;
  }
  Context.Version = 0;
  Context.Flags = 2;
  Context.ResourceFileName = 0;
  v15 = L"srvsvc.dll";
  while ( *v15 )
  {
    ++v15;
    if ( !--v11 )
      goto LABEL_40;
  }
  v16 = 2 * v11;
  Context.ResourceFileName.Buffer = L"srvsvc.dll";
  Context.ResourceFileName.Length = -2 - v16;
  Context.ResourceFileName.MaximumLength = -v16;
LABEL_40:
  Context.StringCount = 0;
  Context.ResourceReasonId = 107;
  Context.ReasonStrings = 0;
  SrvPowerNonIdleCount = 0;
  SrvPowerOpenFileCount = 0;
  LocalMajorSequence = PoCreatePowerRequest(&SrvPowerNonIdleRequest, SrvAdminDeviceObject, &Context);
  if ( LocalMajorSequence < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_4;
    }
    v9 = 14;
    goto LABEL_19;
  }
  LocalMajorSequence = PoRegisterPowerSettingCallback(
                         SrvAdminDeviceObject,
                         &GUID_LOW_POWER_EPOCH,
                         SrvPowerLowPowerEpochCallback,
                         0,
                         &SrvPowerLowPowerEpochHandle);
  if ( LocalMajorSequence < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_4;
    }
    v9 = 15;
    goto LABEL_19;
  }
  LocalMajorSequence = PoRegisterPowerSettingCallback(
                         SrvAdminDeviceObject,
                         &GUID_ACDC_POWER_SOURCE,
                         SrvPowerAcDcPowerSourceCallback,
                         0,
                         &SrvPowerAcDcPowerSourceHandle);
  if ( LocalMajorSequence < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_4;
    }
    v9 = 16;
    goto LABEL_19;
  }
  LODWORD(v20) = 1;
  *((_QWORD *)&v20 + 1) = SrvPowerActivationCallback;
  v21 = 0;
  v17 = Pdcv2ActivationClientRegister(101, &v20, &SrvPowerNetworkActivator);
  SrvPowerNetworkActivatorStatus = v17;
  if ( v17 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids, (unsigned int)v17);
  }
  LocalMajorSequence = SrvAdminLocalNodeInitialize();
  if ( LocalMajorSequence < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_4;
    }
    v9 = 18;
    goto LABEL_19;
  }
  LocalMajorSequence = LoadLocalMajorSequence();
  if ( LocalMajorSequence < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_4;
    }
    v9 = 19;
    goto LABEL_19;
  }
  LocalMajorSequence = SrvAdminStartInstance();
  if ( LocalMajorSequence < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_4;
    }
    v9 = 20;
LABEL_19:
    WPP_SF_d(v8->AttachedDevice, v9, WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids, (unsigned int)LocalMajorSequence);
    goto LABEL_4;
  }
  SrvNetAdminDeviceObject = (__int64)SrvAdminDeviceObject;
  SrvAdminInstanceStarted = 1;
  RfsTimerInitialize();
  RfsTimerSet();
  LocalMajorSequence = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids);
  }
  return (unsigned int)LocalMajorSequence;
}

```

## disassembly

```asm
0x14000fc18  mov     [rsp-8+arg_8], rbx
0x14000fc1d  mov     [rsp-8+arg_10], rsi
0x14000fc22  push    rbp
0x14000fc23  push    rdi
0x14000fc24  push    r12
0x14000fc26  push    r13
0x14000fc28  push    r14
0x14000fc2a  lea     rbp, [rsp-0D0h]
0x14000fc32  sub     rsp, 1D0h
0x14000fc39  mov     rax, cs:__security_cookie
0x14000fc40  xor     rax, rsp
0x14000fc43  mov     [rbp+0F0h+var_30], rax
0x14000fc4a  xorps   xmm0, xmm0
0x14000fc4d  mov     eax, 4
0x14000fc52  mov     [rsp+1F0h+var_188], eax
0x14000fc56  mov     rbx, rcx
0x14000fc59  mov     [rsp+1F0h+var_184], eax
0x14000fc5d  xor     eax, eax
0x14000fc5f  mov     qword ptr [rsp+1F0h+Context.8+18h], rax
0x14000fc64  mov     [rbp+0F0h+var_170], rax
0x14000fc68  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x14000fc6c  movups  xmmword ptr [rsp+1F0h+Context.Version], xmm0
0x14000fc71  movups  xmmword ptr [rsp+1F0h+Context.8+8], xmm0
0x14000fc76  movups  [rsp+1F0h+var_180], xmm0
0x14000fc7b  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14000fc80  lea     rdx, aDeviceSrvadmin_5; "\\Device\\SrvAdmin"
0x14000fc87  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x14000fc8b  call    cs:__imp_RtlInitUnicodeString
0x14000fc92  nop     dword ptr [rax+rax+00h]
0x14000fc97  xor     r14d, r14d
0x14000fc9a  lea     rax, SrvAdminDeviceObject
0x14000fca1  mov     [rsp+1F0h+DeviceObject], rax; DeviceObject
0x14000fca6  lea     r8, [rbp+0F0h+DestinationString]; DeviceName
0x14000fcaa  mov     [rsp+1F0h+Exclusive], r14b; Exclusive
0x14000fcaf  xor     edx, edx; DeviceExtensionSize
0x14000fcb1  mov     rcx, rbx; DriverObject
0x14000fcb4  mov     [rsp+1F0h+DeviceCharacteristics], 100h; DeviceCharacteristics
0x14000fcbc  lea     r9d, [r14+22h]; DeviceType
0x14000fcc0  call    cs:__imp_IoCreateDevice
0x14000fcc7  nop     dword ptr [rax+rax+00h]
0x14000fccc  mov     ebx, eax
0x14000fcce  test    eax, eax
0x14000fcd0  js      short loc_14000FD16
0x14000fcd2  mov     rcx, cs:SrvAdminDeviceObject; int
0x14000fcd9  mov     edx, 1F01FFh; int
0x14000fcde  mov     r8d, 100003h; int
0x14000fce4  mov     dword ptr [rsp+1F0h+Exclusive], r14d; ACCESS_MASK
0x14000fce9  mov     r9d, edx; int
0x14000fcec  mov     [rsp+1F0h+DeviceCharacteristics], r8d; ACCESS_MASK
0x14000fcf1  call    SrvLibApplyDeviceAcl
0x14000fcf6  mov     ebx, eax
0x14000fcf8  test    eax, eax
0x14000fcfa  jns     short loc_14000FD49
0x14000fcfc  mov     rcx, cs:SrvAdminDeviceObject; DeviceObject
0x14000fd03  call    cs:__imp_IoDeleteDevice
0x14000fd0a  nop     dword ptr [rax+rax+00h]
0x14000fd0f  mov     cs:SrvAdminDeviceObject, r14
0x14000fd16  call    SrvAdminCleanupEx
0x14000fd1b  mov     eax, ebx
0x14000fd1d  mov     rcx, [rbp+0F0h+var_30]
0x14000fd24  xor     rcx, rsp; StackCookie
0x14000fd27  call    __security_check_cookie
0x14000fd2c  lea     r11, [rsp+1F0h+var_20]
0x14000fd34  mov     rbx, [r11+38h]
0x14000fd38  mov     rsi, [r11+40h]
0x14000fd3c  mov     rsp, r11
0x14000fd3f  pop     r14
0x14000fd41  pop     r13
0x14000fd43  pop     r12
0x14000fd45  pop     rdi
0x14000fd46  pop     rbp
0x14000fd47  retn
0x14000fd49  call    SrvAdminInitMaxUsers
0x14000fd4e  mov     ebx, 11Ch
0x14000fd53  lea     rcx, [rbp+0F0h+VersionInfo]; void *
0x14000fd57  mov     r8d, ebx; Size
0x14000fd5a  xor     edx, edx; Val
0x14000fd5c  call    memset
0x14000fd61  mov     esi, 2
0x14000fd66  mov     [rbp+0F0h+VersionInfo.dwOSVersionInfoSize], ebx
0x14000fd69  mov     r8b, 3; Condition
0x14000fd6c  mov     [rbp+0F0h+VersionInfo.wProductType], sil
0x14000fd73  xor     ecx, ecx; ConditionMask
0x14000fd75  lea     ebx, [rsi+7Eh]
0x14000fd78  mov     edx, ebx; TypeMask
0x14000fd7a  call    cs:__imp_VerSetConditionMask
0x14000fd81  nop     dword ptr [rax+rax+00h]
0x14000fd86  mov     edx, ebx; TypeMask
0x14000fd88  lea     rcx, [rbp+0F0h+VersionInfo]; VersionInfo
0x14000fd8c  mov     r8, rax; ConditionMask
0x14000fd8f  call    cs:__imp_RtlVerifyVersionInfo
0x14000fd96  nop     dword ptr [rax+rax+00h]
0x14000fd9b  lea     rdi, WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids
0x14000fda2  mov     r12b, 20h ; ' '
0x14000fda5  lea     r13, WPP_GLOBAL_Control
0x14000fdac  test    eax, eax
0x14000fdae  js      short loc_14000FDFF
0x14000fdb0  lea     r9, KSumRegHandle; RegHandle
0x14000fdb7  xor     r8d, r8d; CallbackContext
0x14000fdba  xor     edx, edx; EnableCallback
0x14000fdbc  lea     rcx, SumProvider; ProviderId
0x14000fdc3  call    cs:__imp_EtwRegister
0x14000fdca  nop     dword ptr [rax+rax+00h]
0x14000fdcf  test    eax, eax
0x14000fdd1  jns     short loc_14000FDFF
0x14000fdd3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000fdda  cmp     rcx, r13
0x14000fddd  jz      short loc_14000FDFF
0x14000fddf  mov     edx, [rcx+2Ch]
0x14000fde2  test    r12b, dl
0x14000fde5  jz      short loc_14000FDFF
0x14000fde7  cmp     byte ptr [rcx+29h], 1
0x14000fdeb  jb      short loc_14000FDFF
0x14000fded  mov     rcx, [rcx+18h]
0x14000fdf1  lea     edx, [rsi+8]
0x14000fdf4  mov     r9d, eax
0x14000fdf7  mov     r8, rdi
0x14000fdfa  call    WPP_SF_d
0x14000fdff  mov     r9d, 16h
0x14000fe05  mov     qword ptr [rsp+1F0h+DeviceCharacteristics], r14
0x14000fe0a  lea     rdx, [rsp+1F0h+var_188]
0x14000fe0f  call    RfsTableCreate
0x14000fe14  mov     cs:hProviderTable, rax
0x14000fe1b  test    rax, rax
0x14000fe1e  jnz     short loc_14000FE2A
0x14000fe20  mov     ebx, 0C000009Ah
0x14000fe25  jmp     loc_14000FD16
0x14000fe2a  lea     r9, SrvAdminShareTableFree; FreeRoutine
0x14000fe31  mov     qword ptr [rsp+1F0h+DeviceCharacteristics], r14; TableContext
0x14000fe36  lea     r8, SrvAdminShareTableAllocate; AllocateRoutine
0x14000fe3d  lea     rdx, SrvAdminAliasTableCompare; CompareRoutine
0x14000fe44  lea     rcx, AliasTableAvl; Table
0x14000fe4b  call    cs:__imp_RtlInitializeGenericTableAvl
0x14000fe52  nop     dword ptr [rax+rax+00h]
0x14000fe57  lea     rax, SrvAdminInstanceList
0x14000fe5e  mov     cs:DefaultAlias, r14
0x14000fe65  lea     rcx, ProviderLock; Resource
0x14000fe6c  mov     cs:qword_140036C18, rax
0x14000fe73  mov     cs:SrvAdminInstanceList, rax
0x14000fe7a  call    cs:__imp_ExInitializeResourceLite
0x14000fe81  nop     dword ptr [rax+rax+00h]
0x14000fe86  lea     rcx, AliasLock; Resource
0x14000fe8d  call    cs:__imp_ExInitializeResourceLite
0x14000fe94  nop     dword ptr [rax+rax+00h]
0x14000fe99  lea     rcx, AnonymousLock; Resource
0x14000fea0  call    cs:__imp_ExInitializeResourceLite
0x14000fea7  nop     dword ptr [rax+rax+00h]
0x14000feac  lea     rcx, SrvAdminNameLock; Resource
0x14000feb3  call    cs:__imp_ExInitializeResourceLite
0x14000feba  nop     dword ptr [rax+rax+00h]
0x14000febf  lea     rcx, SrvAdminInstanceListLock; Resource
0x14000fec6  call    cs:__imp_ExInitializeResourceLite
0x14000fecd  nop     dword ptr [rax+rax+00h]
0x14000fed2  lea     rcx, SrvAdminInstanceStartStopLock; Resource
0x14000fed9  call    cs:__imp_ExInitializeResourceLite
0x14000fee0  nop     dword ptr [rax+rax+00h]
0x14000fee5  mov     cs:LockInitialized, 1
0x14000feec  call    SrvAdminInitializeFsctlPropertyList
0x14000fef1  mov     ebx, eax
0x14000fef3  test    eax, eax
0x14000fef5  jns     short loc_14000FF36
0x14000fef7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000fefe  cmp     rcx, r13
0x14000ff01  jz      loc_14000FD16
0x14000ff07  mov     eax, [rcx+2Ch]
0x14000ff0a  test    r12b, al
0x14000ff0d  jz      loc_14000FD16
0x14000ff13  cmp     byte ptr [rcx+29h], 1
0x14000ff17  jb      loc_14000FD16
0x14000ff1d  mov     edx, 0Bh
0x14000ff22  mov     r8, rdi
0x14000ff25  mov     rcx, [rcx+18h]
0x14000ff29  mov     r9d, ebx
0x14000ff2c  call    WPP_SF_d
0x14000ff31  jmp     loc_14000FD16
0x14000ff36  call    SrvAdminRefreshFsctlPropertyList
0x14000ff3b  test    eax, eax
0x14000ff3d  jns     short loc_14000FF6D
0x14000ff3f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ff46  cmp     rcx, r13
0x14000ff49  jz      short loc_14000FF6D
0x14000ff4b  mov     edx, [rcx+2Ch]
0x14000ff4e  test    r12b, dl
0x14000ff51  jz      short loc_14000FF6D
0x14000ff53  cmp     byte ptr [rcx+29h], 1
0x14000ff57  jb      short loc_14000FF6D
0x14000ff59  mov     rcx, [rcx+18h]
0x14000ff5d  mov     edx, 0Ch
0x14000ff62  mov     r9d, eax
0x14000ff65  mov     r8, rdi
0x14000ff68  call    WPP_SF_d
0x14000ff6d  call    SrvAdminRefreshAnonymousLists
0x14000ff72  call    SrvAdminRefreshAllowedServerNameList
0x14000ff77  mov     word ptr [rsp+1F0h+DeviceObject], 80h; Depth
0x14000ff7e  lea     rcx, SrvAdminPagedList256; Lookaside
0x14000ff85  mov     dword ptr [rsp+1F0h+Exclusive], 64614153h; Tag
0x14000ff8d  xor     r9d, r9d; Flags
0x14000ff90  xor     r8d, r8d; Free
0x14000ff93  mov     qword ptr [rsp+1F0h+DeviceCharacteristics], 100h; Size
0x14000ff9c  xor     edx, edx; Allocate
0x14000ff9e  call    cs:__imp_ExInitializePagedLookasideList
0x14000ffa5  nop     dword ptr [rax+rax+00h]
0x14000ffaa  mov     [rsp+1F0h+Context.Flags], esi
0x14000ffae  lea     r8, aSrvsvcDll; "srvsvc.dll"
0x14000ffb5  xorps   xmm0, xmm0
0x14000ffb8  mov     cs:SrvAdminPagedListInitialized, 1
0x14000ffbf  mov     esi, 7FFFh
0x14000ffc4  mov     [rsp+1F0h+Context.Version], r14d
0x14000ffc9  movups  xmmword ptr [rsp+1F0h+Context.8], xmm0
0x14000ffce  mov     ecx, esi
0x14000ffd0  mov     rax, r8
0x14000ffd3  mov     edx, 2
0x14000ffd8  mov     edi, 0FFFEh
0x14000ffdd  cmp     [rax], r14w
0x14000ffe1  jz      short loc_14000FFEE
0x14000ffe3  add     rax, rdx
0x14000ffe6  sub     rcx, 1
0x14000ffea  jnz     short loc_14000FFD8
0x14000ffec  jmp     short loc_140010008
0x14000ffee  add     cx, cx
0x14000fff1  mov     qword ptr [rsp+1F0h+Context.8+8], r8
0x14000fff6  mov     eax, edi
0x14000fff8  sub     ax, cx
0x14000fffb  mov     word ptr [rsp+1F0h+Context.8], ax
0x140010000  add     ax, dx
0x140010003  mov     word ptr [rsp+1F0h+Context.8+2], ax
0x140010008  mov     rdx, cs:SrvAdminDeviceObject; DeviceObject
0x14001000f  lea     r8, [rsp+1F0h+Context]; Context
0x140010014  mov     eax, 6Ah ; 'j'
0x140010019  mov     dword ptr [rsp+1F0h+Context.8+14h], r14d
0x14001001e  lea     rcx, SrvPowerOpenFileRequest; PowerRequest
0x140010025  mov     word ptr [rsp+1F0h+Context.8+10h], ax
0x14001002a  mov     qword ptr [rsp+1F0h+Context.8+18h], r14
0x14001002f  call    cs:__imp_PoCreatePowerRequest
0x140010036  nop     dword ptr [rax+rax+00h]
0x14001003b  mov     ebx, eax
0x14001003d  test    eax, eax
0x14001003f  jns     short loc_140010078
0x140010041  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140010048  cmp     rcx, r13
0x14001004b  jz      loc_14000FD16
0x140010051  mov     eax, [rcx+2Ch]
0x140010054  test    r12b, al
0x140010057  jz      loc_14000FD16
0x14001005d  cmp     byte ptr [rcx+29h], 1
0x140010061  jb      loc_14000FD16
0x140010067  mov     edx, 0Dh
0x14001006c  lea     r8, WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids
0x140010073  jmp     loc_14000FF25
0x140010078  mov     ecx, 2
0x14001007d  mov     [rsp+1F0h+Context.Version], r14d
0x140010082  xorps   xmm0, xmm0
0x140010085  mov     [rsp+1F0h+Context.Flags], ecx
0x140010089  lea     rdx, aSrvsvcDll; "srvsvc.dll"
0x140010090  movups  xmmword ptr [rsp+1F0h+Context.8], xmm0
0x140010095  mov     rax, rdx
0x140010098  cmp     [rax], r14w
0x14001009c  jz      short loc_1400100A9
0x14001009e  add     rax, rcx
0x1400100a1  sub     rsi, 1
0x1400100a5  jnz     short loc_140010098
0x1400100a7  jmp     short loc_1400100C1
0x1400100a9  add     si, si
0x1400100ac  mov     qword ptr [rsp+1F0h+Context.8+8], rdx
0x1400100b1  sub     di, si
0x1400100b4  mov     word ptr [rsp+1F0h+Context.8], di
0x1400100b9  add     di, cx
0x1400100bc  mov     word ptr [rsp+1F0h+Context.8+2], di
0x1400100c1  mov     rdx, cs:SrvAdminDeviceObject; DeviceObject
0x1400100c8  lea     r8, [rsp+1F0h+Context]; Context
0x1400100cd  mov     eax, 6Bh ; 'k'
0x1400100d2  mov     dword ptr [rsp+1F0h+Context.8+14h], r14d
0x1400100d7  lea     rcx, SrvPowerNonIdleRequest; PowerRequest
0x1400100de  mov     word ptr [rsp+1F0h+Context.8+10h], ax
0x1400100e3  mov     qword ptr [rsp+1F0h+Context.8+18h], r14
0x1400100e8  mov     cs:SrvPowerNonIdleCount, r14d
0x1400100ef  mov     cs:SrvPowerOpenFileCount, r14d
0x1400100f6  call    cs:__imp_PoCreatePowerRequest
0x1400100fd  nop     dword ptr [rax+rax+00h]
0x140010102  mov     ebx, eax
0x140010104  test    eax, eax
0x140010106  jns     short loc_140010138
0x140010108  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001010f  cmp     rcx, r13
0x140010112  jz      loc_14000FD16
0x140010118  mov     eax, [rcx+2Ch]
0x14001011b  test    r12b, al
0x14001011e  jz      loc_14000FD16
0x140010124  cmp     byte ptr [rcx+29h], 1
0x140010128  jb      loc_14000FD16
0x14001012e  mov     edx, 0Eh
0x140010133  jmp     loc_14001006C
0x140010138  mov     rcx, cs:SrvAdminDeviceObject; DeviceObject
0x14001013f  lea     rax, SrvPowerLowPowerEpochHandle
0x140010146  xor     r9d, r9d; Context
0x140010149  mov     qword ptr [rsp+1F0h+DeviceCharacteristics], rax; Handle
0x14001014e  lea     r8, SrvPowerLowPowerEpochCallback; Callback
0x140010155  lea     rdx, GUID_LOW_POWER_EPOCH; SettingGuid
0x14001015c  call    cs:__imp_PoRegisterPowerSettingCallback
0x140010163  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
