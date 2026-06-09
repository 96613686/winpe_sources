# DriverEntry

- ea: `0x14008f314`
- end: `0x14008fd55`
- name: `DriverEntry`
- size: `2625`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `67`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14008e420`

## callees

- `0x1400026c0`
- `0x140003d20`
- `0x1400051bc`
- `0x140006334`
- `0x14000c3ec`
- `0x14000c428`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140077660`
- `0x140079464`
- `0x140079540`
- `0x140079778`
- `0x14007a060`
- `0x14007b5a0`
- `0x14007bca4`
- `0x14007c130`
- `0x14007c1b0`
- `0x14007c244`
- `0x14007d008`
- `0x14007d264`
- `0x14007f8a8`
- `0x14007fa84`
- `0x140080828`
- `0x1400820ec`
- `0x140082130`
- `0x140083b94`
- `0x1400842d8`
- `0x140084638`
- `0x14008475c`
- `0x140084924`
- `0x140084b5c`
- `0x1400854f8`
- `0x140085588`
- `0x140088a2c`
- `0x140088b40`
- `0x14008a86c`
- `0x14008aa0c`
- `0x14008acd8`
- `0x14008b200`
- `0x14008b270`
- `0x14008e000`
- `0x14008e4b0`
- `0x14008e860`
- `0x14008efe8`
- `0x14008f290`
- `0x14008f314`
- `0x1400905ec`
- `0x1400907b8`
- `0x14009176c`

## import_xrefs

- `ntoskrnl!InitSafeBootMode` at `0x14008f356`
- `ntoskrnl!PsSetCreateThreadNotifyRoutine` at `0x14008fadb`
- `ntoskrnl!PsSetCreateThreadNotifyRoutine` at `0x14008fadb`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14008f653`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14008f653`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14008f3f3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14008f3f3`
- `ntoskrnl!RtlGetVersion` at `0x14008f3cc`
- `ntoskrnl!RtlGetVersion` at `0x14008f3cc`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14008fc54`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14008fc74`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x140094b64`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x140094b85`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14008fc54`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x14008fc74`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x140094b64`
- `ntoskrnl!PsRemoveCreateThreadNotifyRoutine` at `0x140094b85`
- `ntoskrnl!PsSetLoadImageNotifyRoutine` at `0x14008fa98`
- `ntoskrnl!PsSetLoadImageNotifyRoutine` at `0x14008fa98`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x14008fc87`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x140094b99`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x14008fc87`
- `ntoskrnl!PsRemoveLoadImageNotifyRoutine` at `0x140094b99`
- `ntoskrnl!KeInitializeEvent` at `0x14008f9ab`
- `ntoskrnl!KeInitializeEvent` at `0x14008f9ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fd38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094c50`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fd38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094c50`
- `FLTMGR!FltStartFiltering` at `0x14008fb8d`
- `FLTMGR!FltStartFiltering` at `0x14008fb8d`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  char v4; // r12
  DWORD dwMajorVersion; // ebx
  DWORD dwMinorVersion; // esi
  PVOID SystemRoutineAddress; // rax
  _WORD *PoolWithTag; // rax
  int RegistryParameters; // ebx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // eax
  __int64 (__fastcall *v14)(_QWORD, void (__stdcall *)(HANDLE, HANDLE, BOOLEAN)); // rax
  __int64 v15; // rcx
  ULONG Flags; // [rsp+20h] [rbp-1A8h]
  struct _UNICODE_STRING SystemRoutineName; // [rsp+58h] [rbp-170h] BYREF
  _BYTE v18[8]; // [rsp+68h] [rbp-160h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-158h] BYREF

  v4 = 0;
  if ( InitSafeBootMode )
    return -1073740961;
  v18[0] = 0;
  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  SystemRoutineName.Buffer = L"NtQuerySystemInformation";
  memset(&VersionInformation, 0, sizeof(VersionInformation));
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( RtlGetVersion(&VersionInformation) >= 0 )
  {
    dwMajorVersion = VersionInformation.dwMajorVersion;
    dwMinorVersion = VersionInformation.dwMinorVersion;
  }
  else
  {
    dwMajorVersion = 5;
    dwMinorVersion = 0;
  }
  SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress
    && ((int (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))SystemRoutineAddress)(227, v18, 1, 0) >= 0
    && v18[0] )
  {
    ExPoolZeroingNativelySupported = 1;
  }
  if ( dwMajorVersion > 6 || dwMajorVersion == 6 && dwMinorVersion >= 2 )
  {
    ExDefaultNonPagedPoolType = 512;
    ExDefaultMdlProtection = 0x40000000;
  }
  ObTotalReferences = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_MpFilter;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b960013237753183ac7a6d55d666ce86_Traceguids, DriverObject);
  McGenEventRegister_EtwRegister();
  PoolWithTag = (_WORD *)MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 4480, 1684426829);
  MpData = (ULONG_PTR)PoolWithTag;
  if ( !PoolWithTag )
  {
    RegistryParameters = -1073741670;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 12;
    Flags = -1073741670;
    goto LABEL_121;
  }
  *PoolWithTag = -9728;
  *(_WORD *)(MpData + 2) = 4480;
  v12 = MpInitializeGlobals(DriverObject, RegistryPath);
  RegistryParameters = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 13;
    Flags = v12;
    goto LABEL_120;
  }
  MpTraceLogInitialize();
  RegistryParameters = MpLoadRegistryParameters();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 14;
    goto LABEL_119;
  }
  MpSetDefaultConfigs();
  MpSetBufferLimits();
  MpInitializeBoostManager();
  RegistryParameters = MpFsHardeningInitialize();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 15;
    goto LABEL_119;
  }
  RegistryParameters = ExInitializeLookasideListEx(
                         (PLOOKASIDE_LIST_EX)&gs_CopyCacheLookaside,
                         0,
                         0,
                         PagedPool,
                         0,
                         56LL * (unsigned int)dword_1400269EC,
                         0x7043504Du,
                         0);
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 16;
    goto LABEL_119;
  }
  RegistryParameters = MpInitializeDocOpenRules();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 17;
    goto LABEL_119;
  }
  RegistryParameters = MpInitializeProcessTable();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 18;
    goto LABEL_119;
  }
  RegistryParameters = MpInitializeThreadTable();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 19;
    goto LABEL_119;
  }
  RegistryParameters = MpInitBootSectorCache();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 20;
    goto LABEL_119;
  }
  RegistryParameters = MpInitializeProcessExclusions();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 21;
    goto LABEL_119;
  }
  v13 = MpPowerStatusInitialize((PVOID *)(MpData + 2456));
  if ( v13 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
      KeGetCurrentThread(),
      v13);
  }
  RegistryParameters = MpTxfInitialize();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 23;
    goto LABEL_119;
  }
  RegistryParameters = MpAsyncInitialize();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 24;
    goto LABEL_119;
  }
  RegistryParameters = MpAsyncScanInitialize();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 25;
    goto LABEL_119;
  }
  RegistryParameters = MpRegInitialize();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 26;
    goto LABEL_119;
  }
  RegistryParameters = MpFgInitialize();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 27;
    goto LABEL_119;
  }
  memset(&dword_140026AE0, 0, 0x80u);
  dword_140026B38 = 0;
  qword_140026B40 = 0;
  dword_140026B3C = 0;
  qword_140026B50 = (__int64)&qword_140026B48;
  qword_140026B48 = (__int64)&qword_140026B48;
  FastMutex.Count = 1;
  FastMutex.Owner = 0;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  RegistryParameters = MpDlpInitialize();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 28;
    goto LABEL_119;
  }
  _mm_lfence();
  RegistryParameters = MpInitializeFltMgr(DriverObject);
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 29;
    goto LABEL_119;
  }
  RegistryParameters = MpCreateCommPorts();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 30;
    goto LABEL_119;
  }
  RegistryParameters = MpSetProcessNotifyRoutine();
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 31;
    goto LABEL_119;
  }
  RegistryParameters = PsSetLoadImageNotifyRoutine(MpLoadImageNotifyRoutine);
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 32;
    goto LABEL_119;
  }
  RegistryParameters = PsSetCreateThreadNotifyRoutine(MpCreateThreadNotifyRoutine);
  if ( RegistryParameters < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_122;
    v11 = 33;
    goto LABEL_119;
  }
  v14 = *(__int64 (__fastcall **)(_QWORD, void (__stdcall *)(HANDLE, HANDLE, BOOLEAN)))(MpData + 40);
  if ( v14 )
  {
    RegistryParameters = v14(0, MpCreateThreadNotifyRoutineEx);
    if ( RegistryParameters < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_122;
      v11 = 34;
      goto LABEL_119;
    }
  }
  MpSetImageVerificationCallback();
  MpSeqDetectCtxInitialize(v15, *(_QWORD *)(MpData + 16));
  v4 = 1;
  RegistryParameters = FltStartFiltering(*(PFLT_FILTER *)(MpData + 16));
  if ( RegistryParameters >= 0 )
  {
    MpUpdateRunningProcesses();
    RegistryParameters = MpObInitialize();
    if ( RegistryParameters >= 0 )
    {
      RegistryParameters = MpRegisterRegCallback();
      if ( RegistryParameters >= 0
        || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      {
        goto LABEL_122;
      }
      v11 = 36;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_122;
      v11 = 35;
    }
LABEL_119:
    Flags = RegistryParameters;
LABEL_120:
    _mm_lfence();
LABEL_121:
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
      KeGetCurrentThread(),
      Flags);
  }
LABEL_122:
  if ( RegistryParameters < 0 )
  {
    if ( MpData )
    {
      _mm_lfence();
      MpTraceLogDriverEntryFailure((unsigned int)RegistryParameters);
      MpRemoveImageVerificationCallback();
      MpUnregisterRegCallback();
      MpObShutdown();
      PsRemoveCreateThreadNotifyRoutine(MpCreateThreadNotifyRoutine);
      if ( *(_QWORD *)(MpData + 40) )
        PsRemoveCreateThreadNotifyRoutine(MpCreateThreadNotifyRoutineEx);
      PsRemoveLoadImageNotifyRoutine(MpLoadImageNotifyRoutine);
      MpRemoveProcessNotifyRoutine();
      MpFreeCommPorts();
      MpFgAuditShutdown();
      MpTearDownFltMgr();
      if ( (v4 & 1) != 0 )
        MpSeqDetectCtxShutdown();
      MpDlpShutdown();
      MpHashLibRelease();
      MpCleanupDriverInfo();
      MpFgCleanup();
      MpRegShutdown();
      MpAsyncScanShutdown();
      MpAsyncShutdown();
      MpTxfCleanup();
      MpPowerStatusUninitialize(*(PVOID *)(MpData + 2456));
      *(_QWORD *)(MpData + 2456) = 0;
      MpShutdownProcessExclusions();
      MpDeleteBootSectorCache();
      MpShutdownThreadTable();
      MpShutdownProcessTable();
      MpCleanupDocOpenRules();
      MpShutdownBoostManager();
      MpFsHardeningRelease();
      MpCopyCacheCleanup();
      MpFreeGlobals();
      MpTraceLogRelease();
      ExFreePoolWithTag((PVOID)MpData, 0x6466504Du);
    }
    McGenEventUnregister_EtwUnregister();
    WppCleanupKm();
  }
  return RegistryParameters;
}

```

## disassembly

```asm
0x14008f314  mov     [rsp+arg_10], rbx
0x14008f319  mov     [rsp+arg_18], rsi
0x14008f31e  push    rdi
0x14008f31f  push    r12
0x14008f321  push    r13
0x14008f323  push    r14
0x14008f325  push    r15
0x14008f327  sub     rsp, 1A0h
0x14008f32e  mov     rax, cs:__security_cookie
0x14008f335  xor     rax, rsp
0x14008f338  mov     [rsp+1C8h+var_38], rax
0x14008f340  mov     r15, rdx
0x14008f343  mov     r14, rcx
0x14008f346  xor     r13d, r13d
0x14008f349  mov     [rsp+1C8h+var_188], r13d
0x14008f34e  mov     r12d, r13d
0x14008f351  mov     [rsp+1C8h+var_184], r13d
0x14008f356  mov     rax, cs:__imp_InitSafeBootMode
0x14008f35d  cmp     [rax], r13d
0x14008f360  jbe     short loc_14008F395
0x14008f362  mov     eax, 0C000035Fh
0x14008f367  mov     rcx, [rsp+1C8h+var_38]
0x14008f36f  xor     rcx, rsp; StackCookie
0x14008f372  call    __security_check_cookie
0x14008f377  lea     r11, [rsp+1C8h+var_28]
0x14008f37f  mov     rbx, [r11+40h]
0x14008f383  mov     rsi, [r11+48h]
0x14008f387  mov     rsp, r11
0x14008f38a  pop     r15
0x14008f38c  pop     r14
0x14008f38e  pop     r13
0x14008f390  pop     r12
0x14008f392  pop     rdi
0x14008f393  retn
0x14008f395  mov     [rsp+1C8h+var_160], r13b
0x14008f39a  mov     qword ptr [rsp+1C8h+SystemRoutineName.Length], 320030h
0x14008f3a3  lea     rax, aNtquerysystemi; "NtQuerySystemInformation"
0x14008f3aa  mov     [rsp+1C8h+SystemRoutineName.Buffer], rax
0x14008f3af  mov     ebx, 114h
0x14008f3b4  mov     r8d, ebx; Size
0x14008f3b7  xor     edx, edx; Val
0x14008f3b9  lea     rcx, [rsp+1C8h+VersionInformation]; void *
0x14008f3be  call    memset
0x14008f3c3  mov     [rsp+1C8h+VersionInformation.dwOSVersionInfoSize], ebx
0x14008f3c7  lea     rcx, [rsp+1C8h+VersionInformation]; lpVersionInformation
0x14008f3cc  call    cs:__imp_RtlGetVersion
0x14008f3d3  nop     dword ptr [rax+rax+00h]
0x14008f3d8  test    eax, eax
0x14008f3da  jns     short loc_14008F3E6
0x14008f3dc  mov     ebx, 5
0x14008f3e1  mov     esi, r13d
0x14008f3e4  jmp     short loc_14008F3EE
0x14008f3e6  mov     ebx, [rsp+1C8h+VersionInformation.dwMajorVersion]
0x14008f3ea  mov     esi, [rsp+1C8h+VersionInformation.dwMinorVersion]
0x14008f3ee  lea     rcx, [rsp+1C8h+SystemRoutineName]; SystemRoutineName
0x14008f3f3  call    cs:__imp_MmGetSystemRoutineAddress
0x14008f3fa  nop     dword ptr [rax+rax+00h]
0x14008f3ff  mov     edi, 1
0x14008f404  test    rax, rax
0x14008f407  jz      short loc_14008F431
0x14008f409  xor     r9d, r9d
0x14008f40c  mov     r8d, edi
0x14008f40f  lea     rdx, [rsp+1C8h+var_160]
0x14008f414  mov     ecx, 0E3h
0x14008f419  call    cs:__guard_dispatch_icall_fptr
0x14008f41f  test    eax, eax
0x14008f421  js      short loc_14008F431
0x14008f423  cmp     [rsp+1C8h+var_160], r13b
0x14008f428  jz      short loc_14008F431
0x14008f42a  mov     cs:ExPoolZeroingNativelySupported, dil
0x14008f431  cmp     ebx, 6
0x14008f434  ja      short loc_14008F43D
0x14008f436  jnz     short loc_14008F451
0x14008f438  cmp     esi, 2
0x14008f43b  jb      short loc_14008F451
0x14008f43d  mov     cs:ExDefaultNonPagedPoolType, 200h
0x14008f447  mov     cs:ExDefaultMdlProtection, 40000000h
0x14008f451  mov     cs:ObTotalReferences, r13
0x14008f458  mov     qword ptr cs:WPP_MAIN_CB.Type, r13
0x14008f45f  lea     rax, WPP_ThisDir_CTLGUID_MpFilter
0x14008f466  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14008f46d  mov     cs:WPP_MAIN_CB.NextDevice, r13
0x14008f474  mov     cs:WPP_MAIN_CB.CurrentIrp, r13
0x14008f47b  mov     cs:WPP_MAIN_CB.Timer, 1
0x14008f486  call    WppLoadTracingSupport
0x14008f48b  mov     cs:WPP_MAIN_CB.CurrentIrp, r13
0x14008f492  call    WppInitKm
0x14008f497  lea     rax, WPP_GLOBAL_Control
0x14008f49e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f4a5  cmp     rcx, rax
0x14008f4a8  jz      short loc_14008F4CF
0x14008f4aa  mov     eax, [rcx+2Ch]
0x14008f4ad  test    dil, al
0x14008f4b0  jz      short loc_14008F4CF
0x14008f4b2  mov     edx, 0Ah
0x14008f4b7  mov     r9, r14
0x14008f4ba  lea     rsi, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x14008f4c1  mov     r8, rsi
0x14008f4c4  mov     rcx, [rcx+18h]
0x14008f4c8  call    WPP_SF_q
0x14008f4cd  jmp     short loc_14008F4D6
0x14008f4cf  lea     rsi, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x14008f4d6  call    McGenEventRegister_EtwRegister
0x14008f4db  mov     ebx, 1180h
0x14008f4e0  mov     r8d, 6466504Dh
0x14008f4e6  mov     edx, ebx
0x14008f4e8  mov     ecx, cs:ExDefaultNonPagedPoolType
0x14008f4ee  call    MpAllocatePoolWithTag
0x14008f4f3  mov     cs:MpData, rax
0x14008f4fa  test    rax, rax
0x14008f4fd  jnz     short loc_14008F53D
0x14008f4ff  mov     ebx, 0C000009Ah
0x14008f504  mov     [rsp+1C8h+var_188], ebx
0x14008f508  mov     rax, cs:WPP_GLOBAL_Control
0x14008f50f  lea     rdx, WPP_GLOBAL_Control
0x14008f516  cmp     rax, rdx
0x14008f519  jz      loc_14008FC1E
0x14008f51f  mov     eax, [rax+2Ch]
0x14008f522  test    dil, al
0x14008f525  jz      loc_14008FC1E
0x14008f52b  mov     edx, 0Ch
0x14008f530  mov     [rsp+1C8h+Flags], 0C000009Ah
0x14008f538  jmp     loc_14008FC01
0x14008f53d  mov     ecx, 0DA00h
0x14008f542  mov     [rax], cx
0x14008f545  mov     rax, cs:MpData
0x14008f54c  mov     [rax+2], bx
0x14008f550  mov     rdx, r15
0x14008f553  mov     rcx, r14
0x14008f556  call    MpInitializeGlobals
0x14008f55b  mov     ebx, eax
0x14008f55d  mov     [rsp+1C8h+var_188], eax
0x14008f561  test    eax, eax
0x14008f563  jns     short loc_14008F596
0x14008f565  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f56c  lea     rdx, WPP_GLOBAL_Control
0x14008f573  cmp     rcx, rdx
0x14008f576  jz      loc_14008FC1E
0x14008f57c  mov     ecx, [rcx+2Ch]
0x14008f57f  test    dil, cl
0x14008f582  jz      loc_14008FC1E
0x14008f588  mov     edx, 0Dh
0x14008f58d  mov     [rsp+1C8h+Flags], eax
0x14008f591  jmp     loc_14008FBFE
0x14008f596  call    MpTraceLogInitialize
0x14008f59b  call    MpLoadRegistryParameters
0x14008f5a0  mov     ebx, eax
0x14008f5a2  mov     [rsp+1C8h+var_188], eax
0x14008f5a6  test    eax, eax
0x14008f5a8  jns     short loc_14008F5D7
0x14008f5aa  mov     rax, cs:WPP_GLOBAL_Control
0x14008f5b1  lea     rdx, WPP_GLOBAL_Control
0x14008f5b8  cmp     rax, rdx
0x14008f5bb  jz      loc_14008FC1E
0x14008f5c1  mov     eax, [rax+2Ch]
0x14008f5c4  test    dil, al
0x14008f5c7  jz      loc_14008FC1E
0x14008f5cd  mov     edx, 0Eh
0x14008f5d2  jmp     loc_14008FBFA
0x14008f5d7  call    MpSetDefaultConfigs
0x14008f5dc  call    MpSetBufferLimits
0x14008f5e1  call    MpInitializeBoostManager
0x14008f5e6  call    MpFsHardeningInitialize
0x14008f5eb  mov     ebx, eax
0x14008f5ed  mov     [rsp+1C8h+var_188], eax
0x14008f5f1  test    eax, eax
0x14008f5f3  jns     short loc_14008F622
0x14008f5f5  mov     rax, cs:WPP_GLOBAL_Control
0x14008f5fc  lea     rdx, WPP_GLOBAL_Control
0x14008f603  cmp     rax, rdx
0x14008f606  jz      loc_14008FC1E
0x14008f60c  mov     eax, [rax+2Ch]
0x14008f60f  test    dil, al
0x14008f612  jz      loc_14008FC1E
0x14008f618  mov     edx, 0Fh
0x14008f61d  jmp     loc_14008FBFA
0x14008f622  mov     eax, cs:dword_1400269EC
0x14008f628  imul    rax, 38h ; '8'
0x14008f62c  mov     [rsp+1C8h+Depth], r13w; Depth
0x14008f632  mov     [rsp+1C8h+Tag], 7043504Dh; Tag
0x14008f63a  mov     [rsp+1C8h+Size], rax; Size
0x14008f63f  mov     [rsp+1C8h+Flags], r13d; Flags
0x14008f644  mov     r9d, edi; PoolType
0x14008f647  xor     r8d, r8d; Free
0x14008f64a  xor     edx, edx; Allocate
0x14008f64c  lea     rcx, gs_CopyCacheLookaside; Lookaside
0x14008f653  call    cs:__imp_ExInitializeLookasideListEx
0x14008f65a  nop     dword ptr [rax+rax+00h]
0x14008f65f  mov     ebx, eax
0x14008f661  mov     [rsp+1C8h+var_188], eax
0x14008f665  test    eax, eax
0x14008f667  jns     short loc_14008F696
0x14008f669  mov     rax, cs:WPP_GLOBAL_Control
0x14008f670  lea     rdx, WPP_GLOBAL_Control
0x14008f677  cmp     rax, rdx
0x14008f67a  jz      loc_14008FC1E
0x14008f680  mov     eax, [rax+2Ch]
0x14008f683  test    dil, al
0x14008f686  jz      loc_14008FC1E
0x14008f68c  mov     edx, 10h
0x14008f691  jmp     loc_14008FBFA
0x14008f696  call    MpInitializeDocOpenRules
0x14008f69b  mov     ebx, eax
0x14008f69d  mov     [rsp+1C8h+var_188], eax
0x14008f6a1  test    eax, eax
0x14008f6a3  jns     short loc_14008F6D2
0x14008f6a5  mov     rax, cs:WPP_GLOBAL_Control
0x14008f6ac  lea     rdx, WPP_GLOBAL_Control
0x14008f6b3  cmp     rax, rdx
0x14008f6b6  jz      loc_14008FC1E
0x14008f6bc  mov     eax, [rax+2Ch]
0x14008f6bf  test    dil, al
0x14008f6c2  jz      loc_14008FC1E
0x14008f6c8  mov     edx, 11h
0x14008f6cd  jmp     loc_14008FBFA
0x14008f6d2  call    MpInitializeProcessTable
0x14008f6d7  mov     ebx, eax
0x14008f6d9  mov     [rsp+1C8h+var_188], eax
0x14008f6dd  test    eax, eax
0x14008f6df  jns     short loc_14008F70E
0x14008f6e1  mov     rax, cs:WPP_GLOBAL_Control
0x14008f6e8  lea     rdx, WPP_GLOBAL_Control
0x14008f6ef  cmp     rax, rdx
0x14008f6f2  jz      loc_14008FC1E
0x14008f6f8  mov     eax, [rax+2Ch]
0x14008f6fb  test    dil, al
0x14008f6fe  jz      loc_14008FC1E
0x14008f704  mov     edx, 12h
0x14008f709  jmp     loc_14008FBFA
0x14008f70e  call    MpInitializeThreadTable
0x14008f713  mov     ebx, eax
0x14008f715  mov     [rsp+1C8h+var_188], eax
0x14008f719  test    eax, eax
0x14008f71b  jns     short loc_14008F74A
0x14008f71d  mov     rax, cs:WPP_GLOBAL_Control
0x14008f724  lea     rdx, WPP_GLOBAL_Control
0x14008f72b  cmp     rax, rdx
0x14008f72e  jz      loc_14008FC1E
0x14008f734  mov     eax, [rax+2Ch]
0x14008f737  test    dil, al
0x14008f73a  jz      loc_14008FC1E
0x14008f740  mov     edx, 13h
0x14008f745  jmp     loc_14008FBFA
0x14008f74a  call    MpInitBootSectorCache
0x14008f74f  mov     ebx, eax
0x14008f751  mov     [rsp+1C8h+var_188], eax
0x14008f755  test    eax, eax
0x14008f757  jns     short loc_14008F786
0x14008f759  mov     rax, cs:WPP_GLOBAL_Control
0x14008f760  lea     rdx, WPP_GLOBAL_Control
0x14008f767  cmp     rax, rdx
0x14008f76a  jz      loc_14008FC1E
0x14008f770  mov     eax, [rax+2Ch]
0x14008f773  test    dil, al
0x14008f776  jz      loc_14008FC1E
0x14008f77c  mov     edx, 14h
0x14008f781  jmp     loc_14008FBFA
0x14008f786  call    MpInitializeProcessExclusions
0x14008f78b  mov     ebx, eax
0x14008f78d  mov     [rsp+1C8h+var_188], eax
0x14008f791  test    eax, eax
0x14008f793  jns     short loc_14008F7C2
0x14008f795  mov     rax, cs:WPP_GLOBAL_Control
0x14008f79c  lea     rdx, WPP_GLOBAL_Control
0x14008f7a3  cmp     rax, rdx
0x14008f7a6  jz      loc_14008FC1E
0x14008f7ac  mov     eax, [rax+2Ch]
0x14008f7af  test    dil, al
0x14008f7b2  jz      loc_14008FC1E
0x14008f7b8  mov     edx, 15h
0x14008f7bd  jmp     loc_14008FBFA
0x14008f7c2  mov     rcx, cs:MpData
0x14008f7c9  add     rcx, 998h; Handle
0x14008f7d0  call    MpPowerStatusInitialize
0x14008f7d5  mov     [rsp+1C8h+var_188], eax
0x14008f7d9  test    eax, eax
0x14008f7db  jns     short loc_14008F822
0x14008f7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f7e4  lea     r15, WPP_GLOBAL_Control
0x14008f7eb  cmp     rcx, r15
0x14008f7ee  jz      short loc_14008F829
0x14008f7f0  mov     ecx, [rcx+2Ch]
0x14008f7f3  test    dil, cl
0x14008f7f6  jz      short loc_14008F829
0x14008f7f8  lfence
0x14008f7fb  mov     r9, gs:188h
0x14008f804  mov     edx, 16h
0x14008f809  mov     [rsp+1C8h+Flags], eax
0x14008f80d  mov     r8, rsi
0x14008f810  mov     rcx, cs:WPP_GLOBAL_Control
0x14008f817  mov     rcx, [rcx+18h]
0x14008f81b  call    WPP_SF_qD
0x14008f820  jmp     short loc_14008F829
0x14008f822  lea     r15, WPP_GLOBAL_Control
0x14008f829  call    MpTxfInitialize
0x14008f82e  mov     ebx, eax
0x14008f830  mov     [rsp+1C8h+var_188], eax
0x14008f834  test    eax, eax
0x14008f836  jns     short loc_14008F85E
0x14008f838  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
