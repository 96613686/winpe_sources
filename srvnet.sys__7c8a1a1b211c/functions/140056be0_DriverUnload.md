# DriverUnload

- ea: `0x140056be0`
- end: `0x140056e35`
- name: `DriverUnload`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14005b3c8`

## callees

- `0x140007ec0`
- `0x140013a0c`
- `0x140013a84`
- `0x140014c04`
- `0x140015470`
- `0x140015790`
- `0x14001acb4`
- `0x140021d70`
- `0x14002970c`
- `0x1400414e8`
- `0x140041b8c`
- `0x140041c44`
- `0x1400439cc`
- `0x140044550`
- `0x140045db0`
- `0x140047a64`
- `0x140047e98`
- `0x140049a68`
- `0x14004ad58`
- `0x140056be0`
- `0x140056f58`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140056dfe`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140056dfe`
- `ntoskrnl!IoDeleteDevice` at `0x140056d99`
- `ntoskrnl!IoDeleteDevice` at `0x140056d99`
- `ntoskrnl!ExDeleteResourceLite` at `0x140056ca7`
- `ntoskrnl!ExDeleteResourceLite` at `0x140056ccc`
- `ntoskrnl!ExDeleteResourceLite` at `0x140056ca7`
- `ntoskrnl!ExDeleteResourceLite` at `0x140056ccc`
- `ntoskrnl!ZwClose` at `0x140056cf9`
- `ntoskrnl!ZwClose` at `0x140056cf9`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140056ddb`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140056ddb`

## pseudocode

```c
__int64 DriverUnload()
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_4c791a4f213531f920775678ddb20f34_Traceguids);
  }
  SrvNetIsLoadedAsDriver = 0;
  if ( (byte_140036679 & 0x20) != 0 )
    SmbCompressionCleanup();
  if ( (SrvNetInitProgress & 0x10) != 0 )
  {
    SrvNetTdiDetachPnpCallbacks();
    SrvNetCleanupDeviceExtensionPreScavengerTermination();
  }
  if ( (byte_140036679 & 0x10) != 0 )
    SrvNetTerminateScavenger();
  if ( (byte_140036679 & 8) != 0 )
    SrvNetCleanupStatisticsQueues();
  if ( (byte_140036679 & 4) != 0 )
    SrvNetDeleteBufferLookasides();
  if ( (byte_140036679 & 2) != 0 )
    RfsRpcBindingCleanup();
  if ( (byte_140036679 & 1) != 0 )
  {
    while ( SrvGrovelerStatus && (int)SrvGrovelerDisconnect() >= 0 )
      ;
    ExDeleteResourceLite(&SrvGrovelerResource);
    while ( SrvXsStatus && (int)SrvXsDisconnect() >= 0 )
      ;
    ExDeleteResourceLite(&SrvXsResource);
  }
  if ( (SrvNetInitProgress & 0x40) != 0 && !_InterlockedCompareExchange(&SmbdInitingOrDeiniting, 2, 0) )
  {
    if ( SmbdHandle )
    {
      ZwClose(SmbdHandle);
      SmbdHandle = 0;
      SmbdFastDispatch = 0;
    }
    _InterlockedExchange(&SmbdInitingOrDeiniting, 0);
  }
  if ( (SrvNetInitProgress & 0x10) != 0 )
    SrvNetDeregisterPnpCallbacks();
  if ( (SrvNetInitProgress & 0x20) != 0 )
  {
    SrvNetWskProviderTerminate();
    if ( (SrvNetInitProgress & 0x20) != 0 && Src != qword_1400370B0 && Src )
    {
      SrvNetWskNotifyCleanupProviderContext(Src);
      Src = qword_1400370B0;
    }
  }
  if ( (SrvNetInitProgress & 0x10) != 0 )
    SrvNetCleanupDeviceExtensionPostScavengerTermination();
  if ( SrvNetInitProgress < 0 )
    SrvNetQUICProviderTerminate();
  if ( (SrvNetInitProgress & 8) != 0 )
    IoDeleteDevice((PDEVICE_OBJECT)SrvNetDeviceObject);
  if ( (SrvNetInitProgress & 4) != 0 )
    SmbCryptoDeinitialize();
  if ( (SrvNetInitProgress & 2) != 0 )
    SrvAdminCleanup();
  if ( (SrvNetInitProgress & 1) != 0 )
    SrvLibCleanup();
  if ( WPP_MAIN_CB.Dpc.DpcData )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DpcData = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  WPP_MAIN_CB.ActiveThreadCount = 0;
  WppCleanupKm();
  return McGenEventUnregister_EtwUnregister();
}

```

## disassembly

```asm
0x140056be0  mov     [rsp+arg_0], rbp
0x140056be5  push    rdi
0x140056be6  sub     rsp, 20h
0x140056bea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140056bf1  lea     rax, WPP_GLOBAL_Control
0x140056bf8  mov     ebp, 2
0x140056bfd  cmp     rcx, rax
0x140056c00  jz      short loc_140056C22
0x140056c02  mov     eax, [rcx+2Ch]
0x140056c05  test    al, 8
0x140056c07  jz      short loc_140056C22
0x140056c09  cmp     [rcx+29h], bpl
0x140056c0d  jb      short loc_140056C22
0x140056c0f  mov     rcx, [rcx+18h]
0x140056c13  lea     edx, [rbp+19h]
0x140056c16  lea     r8, WPP_4c791a4f213531f920775678ddb20f34_Traceguids
0x140056c1d  call    WPP_SF_
0x140056c22  mov     dil, 20h ; ' '
0x140056c25  mov     cs:SrvNetIsLoadedAsDriver, 0
0x140056c2c  test    cs:byte_140036679, dil
0x140056c33  jz      short loc_140056C3A
0x140056c35  call    SmbCompressionCleanup
0x140056c3a  test    cs:SrvNetInitProgress, 10h
0x140056c41  jz      short loc_140056C4D
0x140056c43  call    SrvNetTdiDetachPnpCallbacks
0x140056c48  call    SrvNetCleanupDeviceExtensionPreScavengerTermination
0x140056c4d  test    cs:byte_140036679, 10h
0x140056c54  jz      short loc_140056C5B
0x140056c56  call    SrvNetTerminateScavenger
0x140056c5b  test    cs:byte_140036679, 8
0x140056c62  jz      short loc_140056C69
0x140056c64  call    SrvNetCleanupStatisticsQueues
0x140056c69  test    cs:byte_140036679, 4
0x140056c70  jz      short loc_140056C77
0x140056c72  call    SrvNetDeleteBufferLookasides
0x140056c77  test    cs:byte_140036679, bpl
0x140056c7e  jz      short loc_140056C85
0x140056c80  call    RfsRpcBindingCleanup
0x140056c85  test    cs:byte_140036679, 1
0x140056c8c  jz      short loc_140056CD8
0x140056c8e  cmp     cs:SrvGrovelerStatus, 0
0x140056c95  jz      short loc_140056CA0
0x140056c97  call    SrvGrovelerDisconnect
0x140056c9c  test    eax, eax
0x140056c9e  jns     short loc_140056C8E
0x140056ca0  lea     rcx, SrvGrovelerResource; Resource
0x140056ca7  call    cs:__imp_ExDeleteResourceLite
0x140056cae  nop     dword ptr [rax+rax+00h]
0x140056cb3  cmp     cs:SrvXsStatus, 0
0x140056cba  jz      short loc_140056CC5
0x140056cbc  call    SrvXsDisconnect
0x140056cc1  test    eax, eax
0x140056cc3  jns     short loc_140056CB3
0x140056cc5  lea     rcx, SrvXsResource; Resource
0x140056ccc  call    cs:__imp_ExDeleteResourceLite
0x140056cd3  nop     dword ptr [rax+rax+00h]
0x140056cd8  test    cs:SrvNetInitProgress, 40h
0x140056cdf  jz      short loc_140056D23
0x140056ce1  xor     eax, eax
0x140056ce3  lock cmpxchg cs:SmbdInitingOrDeiniting, ebp
0x140056ceb  jnz     short loc_140056D23
0x140056ced  mov     rcx, cs:SmbdHandle; Handle
0x140056cf4  test    rcx, rcx
0x140056cf7  jz      short loc_140056D1B
0x140056cf9  call    cs:__imp_ZwClose
0x140056d00  nop     dword ptr [rax+rax+00h]
0x140056d05  mov     cs:SmbdHandle, 0
0x140056d10  mov     cs:SmbdFastDispatch, 0
0x140056d1b  xor     eax, eax
0x140056d1d  xchg    eax, cs:SmbdInitingOrDeiniting
0x140056d23  test    cs:SrvNetInitProgress, 10h
0x140056d2a  jz      short loc_140056D31
0x140056d2c  call    SrvNetDeregisterPnpCallbacks
0x140056d31  test    cs:SrvNetInitProgress, dil
0x140056d38  jz      short loc_140056D6C
0x140056d3a  call    SrvNetWskProviderTerminate
0x140056d3f  test    cs:SrvNetInitProgress, dil
0x140056d46  jz      short loc_140056D6C
0x140056d48  mov     rcx, cs:Src
0x140056d4f  lea     rdi, qword_1400370B0
0x140056d56  cmp     rcx, rdi
0x140056d59  jz      short loc_140056D6C
0x140056d5b  test    rcx, rcx
0x140056d5e  jz      short loc_140056D6C
0x140056d60  call    SrvNetWskNotifyCleanupProviderContext
0x140056d65  mov     cs:Src, rdi
0x140056d6c  test    cs:SrvNetInitProgress, 10h
0x140056d73  jz      short loc_140056D7A
0x140056d75  call    SrvNetCleanupDeviceExtensionPostScavengerTermination
0x140056d7a  mov     al, cs:SrvNetInitProgress
0x140056d80  test    al, al
0x140056d82  jns     short loc_140056D89
0x140056d84  call    SrvNetQUICProviderTerminate
0x140056d89  test    cs:SrvNetInitProgress, 8
0x140056d90  jz      short loc_140056DA5
0x140056d92  mov     rcx, cs:SrvNetDeviceObject; DeviceObject
0x140056d99  call    cs:__imp_IoDeleteDevice
0x140056da0  nop     dword ptr [rax+rax+00h]
0x140056da5  test    cs:SrvNetInitProgress, 4
0x140056dac  jz      short loc_140056DB3
0x140056dae  call    SmbCryptoDeinitialize
0x140056db3  test    cs:SrvNetInitProgress, bpl
0x140056dba  jz      short loc_140056DC1
0x140056dbc  call    SrvAdminCleanup
0x140056dc1  test    cs:SrvNetInitProgress, 1
0x140056dc8  jz      short loc_140056DCF
0x140056dca  call    SrvLibCleanup
0x140056dcf  mov     rcx, cs:WPP_MAIN_CB.Dpc.DpcData
0x140056dd6  test    rcx, rcx
0x140056dd9  jz      short loc_140056DF2
0x140056ddb  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140056de2  nop     dword ptr [rax+rax+00h]
0x140056de7  mov     cs:WPP_MAIN_CB.Dpc.DpcData, 0
0x140056df2  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140056df9  test    rcx, rcx
0x140056dfc  jz      short loc_140056E15
0x140056dfe  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140056e05  nop     dword ptr [rax+rax+00h]
0x140056e0a  mov     cs:g_wil_details_featureUsageProvider, 0
0x140056e15  mov     cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x140056e1f  call    WppCleanupKm
0x140056e24  call    McGenEventUnregister_EtwUnregister
0x140056e29  mov     rbp, [rsp+28h+arg_0]
0x140056e2e  add     rsp, 20h
0x140056e32  pop     rdi
0x140056e33  retn
```
