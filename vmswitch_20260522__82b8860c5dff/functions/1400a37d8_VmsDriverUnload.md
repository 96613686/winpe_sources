# VmsDriverUnload

- ea: `0x1400a37d8`
- end: `0x1400a3b2b`
- name: `VmsDriverUnload`
- size: `851`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400a2918`
- `0x1400a41e8`
- `0x1400f6bb0`

## callees

- `0x140046e5c`
- `0x14007a97c`
- `0x140087228`
- `0x1400883bc`
- `0x14008846c`
- `0x140089ed8`
- `0x14008d760`
- `0x14008d8e8`
- `0x14008db88`
- `0x14008e5f0`
- `0x14008e6d4`
- `0x140096b98`
- `0x1400a37d8`
- `0x1400a8e3c`
- `0x1400a8ee4`
- `0x140105aac`
- `0x14018546c`
- `0x1401854f4`
- `0x14018a7e4`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400a3984`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400a3984`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a38ce`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a3920`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a38ce`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a3920`
- `ntoskrnl!ExFreePool` at `0x1400a38ab`
- `ntoskrnl!ExFreePool` at `0x1400a38ab`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400a38fd`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400a38fd`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400a3ae8`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400a3ae8`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400a3b07`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400a3b07`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400a37f1`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400a37f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a3a5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a3a5b`
- `NDIS!NdisDeregisterProtocolDriver` at `0x1400a39a8`
- `NDIS!NdisDeregisterProtocolDriver` at `0x1400a39c7`
- `NDIS!NdisDeregisterProtocolDriver` at `0x1400a39a8`
- `NDIS!NdisDeregisterProtocolDriver` at `0x1400a39c7`
- `NDIS!NdisFDeregisterFilterDriver` at `0x1400a39e6`
- `NDIS!NdisFDeregisterFilterDriver` at `0x1400a39e6`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x1400a3a05`
- `NDIS!NdisMDeregisterMiniportDriver` at `0x1400a3a05`
- `NDIS!NdisFreeRWLock` at `0x1400a3a29`
- `NDIS!NdisFreeRWLock` at `0x1400a3a29`
- `NETIO!NmrDeregisterClient` at `0x1400a394b`
- `NETIO!NmrDeregisterClient` at `0x1400a394b`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400a3965`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400a3965`
- `NETIO!MdpDestroyPool` at `0x1400a3875`
- `NETIO!MdpDestroyPool` at `0x1400a3875`

## pseudocode

```c
__int64 __fastcall VmsDriverUnload(__int64 a1)
{
  int v2; // eax
  int v3; // edx
  int v4; // ebx
  int v5; // edx
  __int64 result; // rax
  __int64 v7; // [rsp+68h] [rbp+10h] BYREF

  v7 = 0;
  v2 = KeQueryInterruptTimePrecise(&v7);
  v3 = dword_1401F68A0;
  v4 = v2;
  if ( dword_1401F68A0 )
    VmsTraceLogDriverOperationBegin("VmsDriverUnload", (unsigned int)dword_1401F68A0, "Started Unloading");
  LOBYTE(v3) = 4;
  WPP_RECORDER_SF_(VmsIfrLog, v3, 18, 16, (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids);
  VmsVmNicDestroyControlDevice();
  VmsProxyUnregister();
  VmsOmDeInitialize();
  if ( byte_1401FA258 )
  {
    qword_140224C88 = 0;
    if ( BYTE8(xmmword_140224C90) && (_QWORD)xmmword_140224C90 )
    {
      MdpDestroyPool();
      *(_QWORD *)&xmmword_140224C90 = 0;
    }
    LOBYTE(g_SegLibContext) = 0;
    byte_1401FA258 = 0;
  }
  if ( byte_1401FA259 )
  {
    if ( P )
    {
      ExFreePool(P);
      P = 0;
    }
    if ( byte_1401F96F0 )
    {
      ExDeleteNPagedLookasideList(&stru_1401F9700);
      byte_1401F96F0 = 0;
    }
    byte_1401FA259 = 0;
  }
  VmsVmDeinitialize();
  if ( byte_1401F96A0 == 1 )
  {
    ExDeleteLookasideListEx(&g_NvLibContext);
    byte_1401F96A0 = 0;
  }
  if ( byte_1401FA25A )
  {
    ExDeleteNPagedLookasideList(&g_ProtocolNicMemberNbls);
    byte_1401FA25A = 0;
  }
  VmsQsDeinitialize();
  *((_QWORD *)&xmmword_1401FB3E0 + 1) = 0;
  if ( PktMon )
  {
    if ( NmrDeregisterClient(PktMon) == 259 )
      NmrWaitForClientDeregisterComplete(PktMon);
    PktMon = 0;
  }
  if ( RunRef )
  {
    ExFreeCacheAwareRundownProtection(RunRef);
    RunRef = 0;
  }
  VmsCdNicProxyUnregister();
  if ( VmsProtocolHandle )
  {
    NdisDeregisterProtocolDriver(VmsProtocolHandle);
    VmsProtocolHandle = 0;
  }
  if ( VmsVswitchProtocolHandle )
  {
    NdisDeregisterProtocolDriver(VmsVswitchProtocolHandle);
    VmsVswitchProtocolHandle = 0;
  }
  if ( VmsVswitchFilterHandle )
  {
    NdisFDeregisterFilterDriver(VmsVswitchFilterHandle);
    VmsVswitchFilterHandle = 0;
  }
  if ( VmsVswitchMiniportHandle )
  {
    NdisMDeregisterMiniportDriver(VmsVswitchMiniportHandle);
    VmsVswitchMiniportHandle = 0;
  }
  ExecMonitorDeinitialize();
  if ( VmsOmObjectListLock )
  {
    NdisFreeRWLock(VmsOmObjectListLock);
    VmsOmObjectListLock = 0;
  }
  if ( KeyHandle )
  {
    VmsCsKeyClose();
    if ( qword_1401FA150 )
    {
      ExFreePoolWithTag(qword_1401FA150, 0);
      qword_1401FA150 = 0;
    }
  }
  VmsScIPsecOffloadStateUninit();
  VmsScQosDeinit();
  VmsDriverObject = 0;
  VmsCdUninitializeVswitchGeneration();
  VmsCdpAuditUninitialize();
  if ( dword_1401F68A0 )
    VmsTraceLogDriverOperationEnd((unsigned int)"VmsDriverUnload", v5, (unsigned int)"Stopped and Unloaded", v4, 0);
  LOBYTE(v5) = 4;
  WPP_RECORDER_SF_(VmsIfrLog, v5, 18, 17, (__int64)WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids);
  UninitializeTelemetryAssertsKM();
  VmsEtwStopTrace();
  result = VmsTrcLogDeinitialize(a1);
  if ( g_wil_details_featureChangeNotification )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return result;
}

```

## disassembly

```asm
0x1400a37d8  push    rbx
0x1400a37da  push    rsi
0x1400a37db  push    rdi
0x1400a37dc  push    r14
0x1400a37de  sub     rsp, 38h
0x1400a37e2  mov     rdi, rcx
0x1400a37e5  xor     esi, esi
0x1400a37e7  lea     rcx, [rsp+58h+arg_8]
0x1400a37ec  mov     [rsp+58h+arg_8], rsi
0x1400a37f1  call    cs:__imp_KeQueryInterruptTimePrecise
0x1400a37f8  nop     dword ptr [rax+rax+00h]
0x1400a37fd  mov     edx, cs:dword_1401F68A0
0x1400a3803  mov     rbx, rax
0x1400a3806  test    edx, edx
0x1400a3808  jz      short loc_1400A381D
0x1400a380a  lea     r8, aStartedUnloadi; "Started Unloading"
0x1400a3811  lea     rcx, aVmsdriverunloa; "VmsDriverUnload"
0x1400a3818  call    VmsTraceLogDriverOperationBegin
0x1400a381d  mov     rcx, cs:VmsIfrLog
0x1400a3824  lea     r14, WPP_532b7f924599360cfd1afe862c02bbdc_Traceguids
0x1400a382b  mov     r9d, 10h
0x1400a3831  mov     [rsp+58h+var_38], r14
0x1400a3836  mov     dl, 4
0x1400a3838  lea     r8d, [r9+2]
0x1400a383c  call    WPP_RECORDER_SF_
0x1400a3841  call    VmsVmNicDestroyControlDevice
0x1400a3846  call    VmsProxyUnregister
0x1400a384b  call    VmsOmDeInitialize
0x1400a3850  cmp     cs:byte_1401FA258, sil
0x1400a3857  jz      short loc_1400A3896
0x1400a3859  cmp     byte ptr cs:xmmword_140224C90+8, sil
0x1400a3860  mov     cs:qword_140224C88, rsi
0x1400a3867  jz      short loc_1400A3888
0x1400a3869  mov     rcx, qword ptr cs:xmmword_140224C90
0x1400a3870  test    rcx, rcx
0x1400a3873  jz      short loc_1400A3888
0x1400a3875  call    cs:__imp_MdpDestroyPool
0x1400a387c  nop     dword ptr [rax+rax+00h]
0x1400a3881  mov     qword ptr cs:xmmword_140224C90, rsi
0x1400a3888  mov     byte ptr cs:g_SegLibContext, sil
0x1400a388f  mov     cs:byte_1401FA258, sil
0x1400a3896  cmp     cs:byte_1401FA259, sil
0x1400a389d  jz      short loc_1400A38E8
0x1400a389f  mov     rcx, cs:P; P
0x1400a38a6  test    rcx, rcx
0x1400a38a9  jz      short loc_1400A38BE
0x1400a38ab  call    cs:__imp_ExFreePool
0x1400a38b2  nop     dword ptr [rax+rax+00h]
0x1400a38b7  mov     cs:P, rsi
0x1400a38be  cmp     cs:byte_1401F96F0, sil
0x1400a38c5  jz      short loc_1400A38E1
0x1400a38c7  lea     rcx, stru_1401F9700; Lookaside
0x1400a38ce  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a38d5  nop     dword ptr [rax+rax+00h]
0x1400a38da  mov     cs:byte_1401F96F0, sil
0x1400a38e1  mov     cs:byte_1401FA259, sil
0x1400a38e8  call    VmsVmDeinitialize
0x1400a38ed  cmp     cs:byte_1401F96A0, 1
0x1400a38f4  jnz     short loc_1400A3910
0x1400a38f6  lea     rcx, g_NvLibContext; Lookaside
0x1400a38fd  call    cs:__imp_ExDeleteLookasideListEx
0x1400a3904  nop     dword ptr [rax+rax+00h]
0x1400a3909  mov     cs:byte_1401F96A0, sil
0x1400a3910  cmp     cs:byte_1401FA25A, sil
0x1400a3917  jz      short loc_1400A3933
0x1400a3919  lea     rcx, g_ProtocolNicMemberNbls; Lookaside
0x1400a3920  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a3927  nop     dword ptr [rax+rax+00h]
0x1400a392c  mov     cs:byte_1401FA25A, sil
0x1400a3933  call    VmsQsDeinitialize
0x1400a3938  mov     rcx, cs:PktMon; NmrClientHandle
0x1400a393f  mov     qword ptr cs:xmmword_1401FB3E0+8, rsi
0x1400a3946  test    rcx, rcx
0x1400a3949  jz      short loc_1400A3978
0x1400a394b  call    cs:__imp_NmrDeregisterClient
0x1400a3952  nop     dword ptr [rax+rax+00h]
0x1400a3957  cmp     eax, 103h
0x1400a395c  jnz     short loc_1400A3971
0x1400a395e  mov     rcx, cs:PktMon; NmrClientHandle
0x1400a3965  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400a396c  nop     dword ptr [rax+rax+00h]
0x1400a3971  mov     cs:PktMon, rsi
0x1400a3978  mov     rcx, cs:RunRef; RunRefCacheAware
0x1400a397f  test    rcx, rcx
0x1400a3982  jz      short loc_1400A3997
0x1400a3984  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400a398b  nop     dword ptr [rax+rax+00h]
0x1400a3990  mov     cs:RunRef, rsi
0x1400a3997  call    VmsCdNicProxyUnregister
0x1400a399c  mov     rcx, cs:VmsProtocolHandle; NdisProtocolHandle
0x1400a39a3  test    rcx, rcx
0x1400a39a6  jz      short loc_1400A39BB
0x1400a39a8  call    cs:__imp_NdisDeregisterProtocolDriver
0x1400a39af  nop     dword ptr [rax+rax+00h]
0x1400a39b4  mov     cs:VmsProtocolHandle, rsi
0x1400a39bb  mov     rcx, cs:VmsVswitchProtocolHandle; NdisProtocolHandle
0x1400a39c2  test    rcx, rcx
0x1400a39c5  jz      short loc_1400A39DA
0x1400a39c7  call    cs:__imp_NdisDeregisterProtocolDriver
0x1400a39ce  nop     dword ptr [rax+rax+00h]
0x1400a39d3  mov     cs:VmsVswitchProtocolHandle, rsi
0x1400a39da  mov     rcx, cs:VmsVswitchFilterHandle; NdisFilterDriverHandle
0x1400a39e1  test    rcx, rcx
0x1400a39e4  jz      short loc_1400A39F9
0x1400a39e6  call    cs:__imp_NdisFDeregisterFilterDriver
0x1400a39ed  nop     dword ptr [rax+rax+00h]
0x1400a39f2  mov     cs:VmsVswitchFilterHandle, rsi
0x1400a39f9  mov     rcx, cs:VmsVswitchMiniportHandle; NdisMiniportDriverHandle
0x1400a3a00  test    rcx, rcx
0x1400a3a03  jz      short loc_1400A3A18
0x1400a3a05  call    cs:__imp_NdisMDeregisterMiniportDriver
0x1400a3a0c  nop     dword ptr [rax+rax+00h]
0x1400a3a11  mov     cs:VmsVswitchMiniportHandle, rsi
0x1400a3a18  call    ExecMonitorDeinitialize
0x1400a3a1d  mov     rcx, cs:VmsOmObjectListLock; Lock
0x1400a3a24  test    rcx, rcx
0x1400a3a27  jz      short loc_1400A3A3C
0x1400a3a29  call    cs:__imp_NdisFreeRWLock
0x1400a3a30  nop     dword ptr [rax+rax+00h]
0x1400a3a35  mov     cs:VmsOmObjectListLock, rsi
0x1400a3a3c  mov     rcx, cs:KeyHandle
0x1400a3a43  test    rcx, rcx
0x1400a3a46  jz      short loc_1400A3A6E
0x1400a3a48  call    VmsCsKeyClose
0x1400a3a4d  mov     rcx, cs:qword_1401FA150; P
0x1400a3a54  test    rcx, rcx
0x1400a3a57  jz      short loc_1400A3A6E
0x1400a3a59  xor     edx, edx; Tag
0x1400a3a5b  call    cs:__imp_ExFreePoolWithTag
0x1400a3a62  nop     dword ptr [rax+rax+00h]
0x1400a3a67  mov     cs:qword_1401FA150, rsi
0x1400a3a6e  call    VmsScIPsecOffloadStateUninit
0x1400a3a73  call    VmsScQosDeinit
0x1400a3a78  mov     cs:VmsDriverObject, rsi
0x1400a3a7f  call    VmsCdUninitializeVswitchGeneration
0x1400a3a84  call    VmsCdpAuditUninitialize
0x1400a3a89  mov     eax, cs:dword_1401F68A0
0x1400a3a8f  test    eax, eax
0x1400a3a91  jz      short loc_1400A3AAD
0x1400a3a93  mov     r9, rbx
0x1400a3a96  mov     dword ptr [rsp+58h+var_38], esi
0x1400a3a9a  lea     r8, aStoppedAndUnlo; "Stopped and Unloaded"
0x1400a3aa1  lea     rcx, aVmsdriverunloa; "VmsDriverUnload"
0x1400a3aa8  call    VmsTraceLogDriverOperationEnd
0x1400a3aad  mov     rcx, cs:VmsIfrLog
0x1400a3ab4  mov     r9d, 11h
0x1400a3aba  mov     dl, 4
0x1400a3abc  mov     [rsp+58h+var_38], r14
0x1400a3ac1  lea     r8d, [r9+1]
0x1400a3ac5  call    WPP_RECORDER_SF_
0x1400a3aca  call    UninitializeTelemetryAssertsKM
0x1400a3acf  call    VmsEtwStopTrace
0x1400a3ad4  mov     rcx, rdi
0x1400a3ad7  call    VmsTrcLogDeinitialize
0x1400a3adc  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400a3ae3  test    rcx, rcx
0x1400a3ae6  jz      short loc_1400A3AFB
0x1400a3ae8  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400a3aef  nop     dword ptr [rax+rax+00h]
0x1400a3af4  mov     cs:g_wil_details_featureChangeNotification, rsi
0x1400a3afb  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400a3b02  test    rcx, rcx
0x1400a3b05  jz      short loc_1400A3B1A
0x1400a3b07  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400a3b0e  nop     dword ptr [rax+rax+00h]
0x1400a3b13  mov     cs:g_wil_details_featureUsageProvider, rsi
0x1400a3b1a  mov     cs:g_wil_details_isFeatureStagingInitialized, esi
0x1400a3b20  add     rsp, 38h
0x1400a3b24  pop     r14
0x1400a3b26  pop     rdi
0x1400a3b27  pop     rsi
0x1400a3b28  pop     rbx
0x1400a3b29  retn
```
