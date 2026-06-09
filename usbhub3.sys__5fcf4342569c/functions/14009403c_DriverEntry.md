# DriverEntry

- ea: `0x14009403c`
- end: `0x1400946cf`
- name: `DriverEntry`
- size: `1683`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140041c64`

## callees

- `0x14000198c`
- `0x140002430`
- `0x1400024b8`
- `0x1400025a4`
- `0x14003447c`
- `0x14004206c`
- `0x140045530`
- `0x140045570`
- `0x140077f40`
- `0x140077ff4`
- `0x1400780bc`
- `0x14008726c`
- `0x140087744`
- `0x140091a0c`
- `0x140092b8c`
- `0x14009403c`
- `0x1400946d8`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400940d8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140094484`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400944b4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400944e4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400940d8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140094484`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400944b4`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400944e4`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14009424f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14009424f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14009426e`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14009426e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094473`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400944a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400944d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140094473`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400944a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400944d3`
- `ntoskrnl!EtwSetInformation` at `0x140094443`
- `ntoskrnl!EtwSetInformation` at `0x140094443`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14009430a`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14009430a`
- `WppRecorder!imp_WppRecorderGetTriageInfo` at `0x14009453d`
- `WppRecorder!imp_WppRecorderGetTriageInfo` at `0x14009453d`
- `WppRecorder!imp_WppRecorderConfigure` at `0x14009419b`
- `WppRecorder!imp_WppRecorderConfigure` at `0x14009419b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x1400943d5`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x1400943d5`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  PVOID SystemRoutineAddress; // rax
  NTSTATUS v5; // edi
  __int64 v6; // rax
  __int64 v7; // rbx
  _QWORD *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // edx
  int v13; // eax
  int v14; // edx
  char *v15; // rsi
  int AcpiVersion; // eax
  int v17; // edx
  _BYTE v19[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+80h] [rbp-80h]
  __int128 v25; // [rsp+90h] [rbp-70h]
  __int64 *v26; // [rsp+A0h] [rbp-60h]
  _BYTE v27[28]; // [rsp+A8h] [rbp-58h] BYREF
  int v28; // [rsp+C4h] [rbp-3Ch]
  __int128 v29; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v30; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v31; // [rsp+E8h] [rbp-18h]
  char pszDest[16]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v33; // [rsp+108h] [rbp+8h]

  g_Usbhub3DriverObject = (__int64)DriverObject;
  memset(v27, 0, sizeof(v27));
  LODWORD(v26) = 0;
  v20 = 0;
  v33 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  DestinationString = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  *(_OWORD *)pszDest = 0;
  wil_InitializeFeatureStaging();
  v19[0] = 0;
  SystemRoutineName.Buffer = L"NtQuerySystemInformation";
  *(_QWORD *)&SystemRoutineName.Length = 3276848;
  SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
  if ( SystemRoutineAddress
    && ((int (__fastcall *)(__int64, _BYTE *, __int64, _QWORD))SystemRoutineAddress)(227, v19, 1, 0) >= 0
    && v19[0] )
  {
    ExPoolZeroingNativelySupported = 1;
  }
  ExDefaultNonPagedPoolType = 512;
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_USBHUB3;
  ExDefaultMdlProtection = 0x40000000;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  LODWORD(v29) = 16;
  *((_QWORD *)&v29 + 1) = 0x200000002LL;
  BYTE4(v29) = 0;
  imp_WppRecorderConfigure(WPP_GLOBAL_Control, &v29);
  *(_QWORD *)v27 = 32;
  *(_QWORD *)&v27[8] = HUBFDO_EvtDeviceAdd;
  v26 = off_14006B2C0;
  *((_QWORD *)&v23 + 1) = DriverCleanup;
  *(_QWORD *)&v27[16] = 0;
  *(_DWORD *)&v27[24] = 0;
  v28 = 1999849557;
  *(_QWORD *)&v23 = 56;
  *(_QWORD *)&v24 = 0;
  v25 = 0;
  *((_QWORD *)&v24 + 1) = 0x100000001LL;
  v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _DRIVER_OBJECT *, PUNICODE_STRING, __int128 *, _BYTE *, unsigned __int64 *))(WdfFunctions_01015 + 928))(
         WdfDriverGlobals,
         DriverObject,
         RegistryPath,
         &v23,
         v27,
         &v20);
  if ( v5 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, unsigned __int64, __int64 *))(WdfFunctions_01015 + 1616))(
           WdfDriverGlobals,
           v20,
           off_14006B2C0);
    *(_QWORD *)&v30 = 56;
    HIDWORD(v31) = 16;
    pszDest[0] = 0;
    v7 = v6;
    *(_QWORD *)&v31 = 0;
    BYTE8(v31) = 0;
    v33 = 0x200000002LL;
    *((_QWORD *)&v30 + 1) = 0x20000000400LL;
    RtlStringCchPrintfA(pszDest, 0x10u, "hub driver");
    v8 = (_QWORD *)(v7 + 64);
    v5 = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v30, v7 + 64);
    if ( v5 >= 0 )
    {
      v26 = 0;
      *(_QWORD *)&v24 = 0;
      *((_QWORD *)&v24 + 1) = 0x100000001LL;
      v25 = v20;
      v23 = 0;
      LODWORD(v23) = 56;
      v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64))(WdfFunctions_01015 + 2496))(
             WdfDriverGlobals,
             &v23,
             v7 + 32);
      if ( v5 >= 0 )
      {
        *(_QWORD *)(v7 + 24) = v7 + 16;
        *(_QWORD *)(v7 + 16) = v7 + 16;
        v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int128 *, __int64))(WdfFunctions_01015 + 2496))(
               WdfDriverGlobals,
               &v23,
               v7 + 56);
        if ( v5 >= 0 )
        {
          *(_QWORD *)(v7 + 48) = v7 + 40;
          *(_QWORD *)(v7 + 40) = v7 + 40;
          McGenEventRegister_EtwRegister(v10, v9, &MS_USBHUB3_ETW_PROVIDER_Context, &MS_USBHUB3_ETW_PROVIDER_Context);
          v11 = SleepstudyHelper_Initialize(v7 + 96, DriverObject);
          if ( v11 < 0 )
          {
            *(_BYTE *)(v7 + 92) = 0;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v12) = 4;
              WPP_RECORDER_SF_d(*v8, v12, 2, 10, (__int64)WPP_fcb91a355b2c39f481323e62bc6862ee_Traceguids, v11);
            }
          }
          else
          {
            *(_BYTE *)(v7 + 92) = 1;
          }
          InitializeTelemetryAssertsKMByDriverObject(DriverObject);
          EtwSetInformation(
            MS_USBHUB3_ETW_PROVIDER_Context,
            EventProviderSetTraits,
            &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
            (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
          HUBREG_QueryGlobalHubValues(v7);
          HUBREG_QueryGlobalUsb20HardwareLpmSettings(v7);
          HUBREG_QueryGlobalUsbLtmSettings(v7);
          RtlInitUnicodeString(&DestinationString, L"KseQueryDeviceFlags");
          g_KseQueryDeviceFlags = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
          RtlInitUnicodeString(&DestinationString, L"IoGetActivityIdIrp");
          g_IoGetActivityIdIrp = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
          RtlInitUnicodeString(&DestinationString, L"IoSetActivityIdIrp");
          g_IoSetActivityIdIrp = (__int64)MmGetSystemRoutineAddress(&DestinationString);
          *(_QWORD *)&SystemRoutineName.Length = 0;
          if ( g_KseQueryDeviceFlags )
          {
            g_KseQueryDeviceFlags(L"USBHUB:GLOBAL_FLAGS", L"USBHUB", &SystemRoutineName);
            if ( (SystemRoutineName.Length & 1) != 0 )
              _InterlockedOr((volatile signed __int32 *)(v7 + 4), 0x20000u);
          }
          imp_WppRecorderGetTriageInfo(WPP_GLOBAL_Control, &g_Usbhub3_WppTriage_Info);
          qword_14006E710 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 3448))(WdfDriverGlobals);
          dword_14006E6E0 = g_Usbhub3_WppTriage_Info;
          dword_14006E6E4 = dword_14006ED68;
          dword_14006E6E8 = dword_14006ED6C;
          dword_14006E6EC = dword_14006ED64;
          dword_14006E6F0 = dword_14006ED70;
          v13 = TlgRegisterAggregateProvider();
          if ( v13 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 2;
            WPP_RECORDER_SF_d(*v8, v14, 2, 11, (__int64)WPP_fcb91a355b2c39f481323e62bc6862ee_Traceguids, v13);
          }
          v15 = (char *)(v7 + 104);
          AcpiVersion = HUBUTIL_GetAcpiVersion(v7 + 104);
          v5 = AcpiVersion;
          if ( AcpiVersion >= 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v17) = 4;
              WPP_RECORDER_SF_dD(
                *v8,
                v17,
                2,
                13,
                (__int64)WPP_fcb91a355b2c39f481323e62bc6862ee_Traceguids,
                *(_BYTE *)(v7 + 105),
                *v15);
            }
          }
          else
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v17) = 2;
              WPP_RECORDER_SF_d(*v8, v17, 2, 12, (__int64)WPP_fcb91a355b2c39f481323e62bc6862ee_Traceguids, AcpiVersion);
            }
            v5 = 0;
            *(_WORD *)v15 = 0;
          }
          if ( v7 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_d(
              *(_QWORD *)(v7 + 64),
              v17,
              2,
              14,
              (__int64)WPP_fcb91a355b2c39f481323e62bc6862ee_Traceguids,
              *(_DWORD *)(v7 + 4));
          }
        }
      }
    }
  }
  else
  {
    WppCleanupKm(DriverObject);
    if ( *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount )
    {
      RtlUnregisterFeatureConfigurationChangeNotification();
      *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = 0;
    }
    if ( g_wil_details_featureUsageProvider )
    {
      RtlUnregisterFeatureUsageProvider();
      g_wil_details_featureUsageProvider = 0;
    }
    g_wil_details_isFeatureStagingInitialized = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x14009403c  mov     [rsp-8+arg_10], rbx
0x140094041  push    rbp
0x140094042  push    rsi
0x140094043  push    rdi
0x140094044  push    r12
0x140094046  push    r13
0x140094048  push    r14
0x14009404a  push    r15
0x14009404c  lea     rbp, [rsp-20h]
0x140094051  sub     rsp, 120h
0x140094058  mov     rax, cs:__security_cookie
0x14009405f  xor     rax, rsp
0x140094062  mov     [rbp+50h+var_40], rax
0x140094066  xorps   xmm0, xmm0
0x140094069  mov     cs:g_Usbhub3DriverObject, rcx
0x140094070  xor     eax, eax
0x140094072  xorps   xmm1, xmm1
0x140094075  movups  [rbp+50h+var_A8], xmm0
0x140094079  xor     r15d, r15d
0x14009407c  mov     dword ptr [rbp+50h+var_B0], eax
0x14009407f  movups  [rbp+50h+var_A8+0Ch], xmm0
0x140094083  mov     rbx, rdx
0x140094086  mov     [rsp+150h+var_108], r15
0x14009408b  mov     rsi, rcx
0x14009408e  mov     [rbp+50h+var_48], rax
0x140094092  movups  [rsp+150h+var_E0], xmm0
0x140094097  movups  [rbp+50h+var_D0], xmm0
0x14009409b  movups  [rbp+50h+var_C0], xmm0
0x14009409f  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x1400940a4  movups  [rbp+50h+var_88], xmm1
0x1400940a8  movups  [rbp+50h+var_78], xmm0
0x1400940ac  movups  [rbp+50h+var_68], xmm0
0x1400940b0  movups  xmmword ptr [rbp+50h+pszDest], xmm0
0x1400940b4  call    wil_InitializeFeatureStaging
0x1400940b9  lea     rax, aNtquerysystemi
0x1400940c0  mov     [rsp+150h+var_110], r15b
0x1400940c5  lea     rcx, [rsp+150h+SystemRoutineName]; SystemRoutineName
0x1400940ca  mov     [rsp+150h+SystemRoutineName.Buffer], rax
0x1400940cf  mov     qword ptr [rsp+150h+SystemRoutineName.Length], 320030h
0x1400940d8  call    cs:__imp_MmGetSystemRoutineAddress
0x1400940df  nop     dword ptr [rax+rax+00h]
0x1400940e4  lea     r13d, [r15+1]
0x1400940e8  test    rax, rax
0x1400940eb  jz      short loc_140094114
0x1400940ed  xor     r9d, r9d
0x1400940f0  lea     rdx, [rsp+150h+var_110]
0x1400940f5  mov     r8d, r13d
0x1400940f8  mov     ecx, 0E3h
0x1400940fd  call    _guard_dispatch_icall
0x140094102  test    eax, eax
0x140094104  js      short loc_140094114
0x140094106  cmp     [rsp+150h+var_110], r15b
0x14009410b  jz      short loc_140094114
0x14009410d  mov     cs:ExPoolZeroingNativelySupported, r13b
0x140094114  lea     rax, WPP_ThisDir_CTLGUID_USBHUB3
0x14009411b  mov     cs:ExDefaultNonPagedPoolType, 200h
0x140094125  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14009412c  mov     cs:ExDefaultMdlProtection, 40000000h
0x140094136  mov     qword ptr cs:WPP_MAIN_CB.Type, r15
0x14009413d  mov     cs:WPP_MAIN_CB.NextDevice, r15
0x140094144  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x14009414b  mov     cs:WPP_MAIN_CB.Timer, r13
0x140094152  mov     cs:WPP_MAIN_CB.DeviceExtension, r15
0x140094159  mov     cs:WPP_MAIN_CB.DeviceType, r15d
0x140094160  call    WppLoadTracingSupport
0x140094165  mov     rdx, rbx; __annotation("TMC:", "6E6CC2C5-8110-490e-9905-9F2ED700E455", "USBHUB3", "General", "Driver", "Hub", "Port", "Device", "HwcPlatform", "PUBLIC_TMF:")
0x140094168  mov     cs:WPP_MAIN_CB.CurrentIrp, r15
0x14009416f  mov     rcx, rsi
0x140094172  call    WppInitKm
0x140094177  mov     rcx, cs:WPP_GLOBAL_Control
0x14009417e  lea     rdx, [rbp+50h+var_88]
0x140094182  mov     r12d, 2
0x140094188  mov     dword ptr [rbp+50h+var_88], 10h
0x14009418f  mov     dword ptr [rbp+50h+var_88+8], r12d
0x140094193  mov     dword ptr [rbp+50h+var_88+0Ch], r12d
0x140094197  mov     byte ptr [rbp+50h+var_88+4], r15b
0x14009419b  call    cs:__imp_imp_WppRecorderConfigure
0x1400941a2  nop     dword ptr [rax+rax+00h]
0x1400941a7  lea     rax, HUBFDO_EvtDeviceAdd
0x1400941ae  mov     qword ptr [rbp+50h+var_A8], 20h ; ' '
0x1400941b6  mov     qword ptr [rbp+50h+var_A8+8], rax
0x1400941ba  lea     rcx, [rsp+150h+var_108]
0x1400941bf  mov     rax, cs:off_14006B2C0
0x1400941c6  lea     r9, [rsp+150h+var_E0]
0x1400941cb  mov     [rbp+50h+var_B0], rax
0x1400941cf  xorps   xmm0, xmm0
0x1400941d2  mov     [rsp+150h+var_128], rcx
0x1400941d7  lea     rax, DriverCleanup
0x1400941de  mov     qword ptr [rsp+150h+var_E0+8], rax
0x1400941e3  lea     rcx, [rbp+50h+var_A8]
0x1400941e7  mov     rax, cs:WdfFunctions_01015
0x1400941ee  mov     r8, rbx
0x1400941f1  mov     [rbp+50h+var_98], r15
0x1400941f5  mov     rdx, rsi
0x1400941f8  mov     [rbp+50h+var_90], r15d
0x1400941fc  mov     [rbp+50h+var_8C], 77334855h
0x140094203  mov     qword ptr [rsp+150h+var_E0], 38h ; '8'
0x14009420c  mov     qword ptr [rbp+50h+var_D0], r15
0x140094210  movdqu  [rbp+50h+var_C0], xmm0
0x140094215  mov     dword ptr [rbp+50h+var_D0+8], r13d
0x140094219  mov     dword ptr [rbp+50h+var_D0+0Ch], r13d
0x14009421d  mov     rax, [rax+3A0h]
0x140094224  mov     [rsp+150h+var_130], rcx
0x140094229  mov     rcx, cs:WdfDriverGlobals
0x140094230  call    _guard_dispatch_icall
0x140094235  mov     edi, eax
0x140094237  test    eax, eax
0x140094239  jns     short loc_14009428D
0x14009423b  mov     rcx, rsi
0x14009423e  call    WppCleanupKm
0x140094243  mov     rcx, qword ptr cs:WPP_MAIN_CB.ActiveThreadCount
0x14009424a  test    rcx, rcx
0x14009424d  jz      short loc_140094262
0x14009424f  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140094256  nop     dword ptr [rax+rax+00h]
0x14009425b  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, r15
0x140094262  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140094269  test    rcx, rcx
0x14009426c  jz      short loc_140094281
0x14009426e  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140094275  nop     dword ptr [rax+rax+00h]
0x14009427a  mov     cs:g_wil_details_featureUsageProvider, r15
0x140094281  mov     cs:g_wil_details_isFeatureStagingInitialized, r15d
0x140094288  jmp     loc_140094662
0x14009428d  mov     rax, cs:WdfFunctions_01015
0x140094294  mov     r8, cs:off_14006B2C0
0x14009429b  mov     rdx, [rsp+150h+var_108]
0x1400942a0  mov     rcx, cs:WdfDriverGlobals
0x1400942a7  mov     rax, [rax+650h]
0x1400942ae  call    _guard_dispatch_icall
0x1400942b3  mov     edx, 10h; cchDest
0x1400942b8  mov     qword ptr [rbp+50h+var_78], 38h ; '8'
0x1400942c0  lea     r8, aHubDriver
0x1400942c7  mov     dword ptr [rbp+50h+var_68+0Ch], edx
0x1400942ca  lea     rcx, [rbp+50h+pszDest]; pszDest
0x1400942ce  mov     [rbp+50h+pszDest], r15b
0x1400942d2  mov     rbx, rax
0x1400942d5  mov     qword ptr [rbp+50h+var_68], r15
0x1400942d9  mov     byte ptr [rbp+50h+var_68+8], r15b
0x1400942dd  mov     dword ptr [rbp+50h+var_48], r12d
0x1400942e1  mov     dword ptr [rbp+50h+var_48+4], r12d
0x1400942e5  mov     dword ptr [rbp+50h+var_78+8], 400h
0x1400942ec  mov     dword ptr [rbp+50h+var_78+0Ch], 200h
0x1400942f3  call    RtlStringCchPrintfA
0x1400942f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400942ff  lea     r14, [rbx+40h]
0x140094303  mov     r8, r14
0x140094306  lea     rdx, [rbp+50h+var_78]
0x14009430a  call    cs:__imp_imp_WppRecorderLogCreate
0x140094311  nop     dword ptr [rax+rax+00h]
0x140094316  mov     edi, eax
0x140094318  test    eax, eax
0x14009431a  js      loc_140094662
0x140094320  mov     rcx, cs:WdfDriverGlobals
0x140094327  lea     r8, [rbx+20h]
0x14009432b  xor     eax, eax
0x14009432d  lea     rdx, [rsp+150h+var_E0]
0x140094332  mov     [rbp+50h+var_B0], rax
0x140094336  xorps   xmm0, xmm0
0x140094339  mov     rax, [rsp+150h+var_108]
0x14009433e  movups  [rbp+50h+var_D0], xmm0
0x140094342  mov     dword ptr [rbp+50h+var_D0+8], r13d
0x140094346  movups  [rbp+50h+var_C0], xmm0
0x14009434a  mov     qword ptr [rbp+50h+var_C0], rax
0x14009434e  mov     rax, cs:WdfFunctions_01015
0x140094355  movups  [rsp+150h+var_E0], xmm0
0x14009435a  mov     dword ptr [rsp+150h+var_E0], 38h ; '8'
0x140094362  mov     dword ptr [rbp+50h+var_D0+0Ch], r13d
0x140094366  mov     rax, [rax+9C0h]
0x14009436d  call    _guard_dispatch_icall
0x140094372  mov     edi, eax
0x140094374  test    eax, eax
0x140094376  js      loc_140094662
0x14009437c  lea     rax, [rbx+10h]
0x140094380  mov     [rax+8], rax
0x140094384  lea     r8, [rbx+38h]
0x140094388  mov     [rax], rax
0x14009438b  lea     rdx, [rsp+150h+var_E0]
0x140094390  mov     rax, cs:WdfFunctions_01015
0x140094397  mov     rcx, cs:WdfDriverGlobals
0x14009439e  mov     rax, [rax+9C0h]
0x1400943a5  call    _guard_dispatch_icall
0x1400943aa  mov     edi, eax
0x1400943ac  test    eax, eax
0x1400943ae  js      loc_140094662
0x1400943b4  lea     rax, [rbx+28h]
0x1400943b8  lea     r8, MS_USBHUB3_ETW_PROVIDER_Context
0x1400943bf  mov     [rax+8], rax
0x1400943c3  mov     r9, r8
0x1400943c6  mov     [rax], rax
0x1400943c9  call    McGenEventRegister_EtwRegister
0x1400943ce  lea     rcx, [rbx+60h]
0x1400943d2  mov     rdx, rsi
0x1400943d5  call    cs:__imp_SleepstudyHelper_Initialize
0x1400943dc  nop     dword ptr [rax+rax+00h]
0x1400943e1  lea     rcx, WPP_fcb91a355b2c39f481323e62bc6862ee_Traceguids
0x1400943e8  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400943ef  test    eax, eax
0x1400943f1  js      short loc_1400943F9
0x1400943f3  mov     [rbx+5Ch], r13b
0x1400943f7  jmp     short loc_140094422
0x1400943f9  mov     [rbx+5Ch], r15b
0x1400943fd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140094404  jz      short loc_140094422
0x140094406  mov     dword ptr [rsp+150h+var_128], eax
0x14009440a  mov     r9d, 0Ah
0x140094410  mov     [rsp+150h+var_130], rcx
0x140094415  mov     r8d, r12d
0x140094418  mov     rcx, [r14]
0x14009441b  mov     dl, 4
0x14009441d  call    WPP_RECORDER_SF_d
0x140094422  mov     rcx, rsi
0x140094425  call    InitializeTelemetryAssertsKMByDriverObject
0x14009442a  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; InformationLength
0x140094432  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; EventInformation
0x140094439  mov     rcx, cs:MS_USBHUB3_ETW_PROVIDER_Context; RegHandle
0x140094440  mov     edx, r12d; InformationClass
0x140094443  call    cs:__imp_EtwSetInformation
0x14009444a  nop     dword ptr [rax+rax+00h]
0x14009444f  mov     rcx, rbx
0x140094452  call    HUBREG_QueryGlobalHubValues
0x140094457  mov     rcx, rbx
0x14009445a  call    HUBREG_QueryGlobalUsb20HardwareLpmSettings
0x14009445f  mov     rcx, rbx
0x140094462  call    HUBREG_QueryGlobalUsbLtmSettings
0x140094467  lea     rdx, aKsequerydevice
0x14009446e  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x140094473  call    cs:__imp_RtlInitUnicodeString
0x14009447a  nop     dword ptr [rax+rax+00h]
0x14009447f  lea     rcx, [rsp+150h+DestinationString]; SystemRoutineName
0x140094484  call    cs:__imp_MmGetSystemRoutineAddress
0x14009448b  nop     dword ptr [rax+rax+00h]
0x140094490  lea     rdx, aIogetactivityi
0x140094497  mov     cs:g_KseQueryDeviceFlags, rax
0x14009449e  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1400944a3  call    cs:__imp_RtlInitUnicodeString
0x1400944aa  nop     dword ptr [rax+rax+00h]
0x1400944af  lea     rcx, [rsp+150h+DestinationString]; SystemRoutineName
0x1400944b4  call    cs:__imp_MmGetSystemRoutineAddress
0x1400944bb  nop     dword ptr [rax+rax+00h]
0x1400944c0  lea     rdx, aIosetactivityi
0x1400944c7  mov     cs:g_IoGetActivityIdIrp, rax
0x1400944ce  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1400944d3  call    cs:__imp_RtlInitUnicodeString
0x1400944da  nop     dword ptr [rax+rax+00h]
0x1400944df  lea     rcx, [rsp+150h+DestinationString]; SystemRoutineName
0x1400944e4  call    cs:__imp_MmGetSystemRoutineAddress
0x1400944eb  nop     dword ptr [rax+rax+00h]
0x1400944f0  mov     cs:g_IoSetActivityIdIrp, rax
0x1400944f7  mov     rax, cs:g_KseQueryDeviceFlags
0x1400944fe  mov     qword ptr [rsp+150h+SystemRoutineName.Length], r15
0x140094503  test    rax, rax
0x140094506  jz      short loc_14009452F
0x140094508  lea     r8, [rsp+150h+SystemRoutineName]
0x14009450d  lea     rdx, aUsbhub
0x140094514  lea     rcx, aUsbhubGlobalFl
0x14009451b  call    _guard_dispatch_icall
0x140094520  test    byte ptr [rsp+150h+SystemRoutineName.Length], r13b
0x140094525  jz      short loc_14009452F
0x140094527  lock or dword ptr [rbx+4], 20000h
0x14009452f  mov     rcx, cs:WPP_GLOBAL_Control
0x140094536  lea     rdx, g_Usbhub3_WppTriage_Info
0x14009453d  call    cs:__imp_imp_WppRecorderGetTriageInfo
0x140094544  nop     dword ptr [rax+rax+00h]
0x140094549  mov     rax, cs:WdfFunctions_01015
0x140094550  mov     rcx, cs:WdfDriverGlobals
0x140094557  mov     rax, [rax+0D78h]
0x14009455e  call    _guard_dispatch_icall
0x140094563  mov     cs:qword_14006E710, rax
0x14009456a  mov     eax, cs:g_Usbhub3_WppTriage_Info
0x140094570  mov     cs:dword_14006E6E0, eax
0x140094576  mov     eax, cs:dword_14006ED68
0x14009457c  mov     cs:dword_14006E6E4, eax
0x140094582  mov     eax, cs:dword_14006ED6C
0x140094588  mov     cs:dword_14006E6E8, eax
0x14009458e  mov     eax, cs:dword_14006ED64
0x140094594  mov     cs:dword_14006E6EC, eax
0x14009459a  mov     eax, cs:dword_14006ED70
0x1400945a0  mov     cs:dword_14006E6F0, eax
0x1400945a6  call    TlgRegisterAggregateProvider
0x1400945ab  test    eax, eax
0x1400945ad  jns     short loc_1400945DC
0x1400945af  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400945b6  jz      short loc_1400945DC
0x1400945b8  mov     rcx, [r14]
0x1400945bb  mov     r9d, 0Bh
0x1400945c1  mov     dword ptr [rsp+150h+var_128], eax
0x1400945c5  mov     r8d, r12d
0x1400945c8  lea     rax, WPP_fcb91a355b2c39f481323e62bc6862ee_Traceguids
0x1400945cf  mov     dl, r12b
0x1400945d2  mov     [rsp+150h+var_130], rax
0x1400945d7  call    WPP_RECORDER_SF_d
0x1400945dc  lea     rsi, [rbx+68h]
0x1400945e0  mov     rcx, rsi
0x1400945e3  call    HUBUTIL_GetAcpiVersion
0x1400945e8  mov     edi, eax
0x1400945ea  test    eax, eax
0x1400945ec  jns     loc_14009468C
0x1400945f2  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400945f9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
  ... truncated ...
```
