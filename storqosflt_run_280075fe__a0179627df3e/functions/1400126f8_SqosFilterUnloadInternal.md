# SqosFilterUnloadInternal

- ea: `0x1400126f8`
- end: `0x140012845`
- name: `SqosFilterUnloadInternal`
- size: `333`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400126b0`
- `0x1400161ec`

## callees

- `0x140008a54`
- `0x140011e50`
- `0x1400126f8`
- `0x140013408`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140012818`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140012818`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400127f5`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400127f5`
- `ntoskrnl!PcwUnregister` at `0x14001274a`
- `ntoskrnl!PcwUnregister` at `0x140012766`
- `ntoskrnl!PcwUnregister` at `0x14001274a`
- `ntoskrnl!PcwUnregister` at `0x140012766`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400127dd`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400127dd`
- `FLTMGR!FltCloseCommunicationPort` at `0x14001270a`
- `FLTMGR!FltCloseCommunicationPort` at `0x14001270a`
- `FLTMGR!FltUnregisterFilter` at `0x140012722`
- `FLTMGR!FltUnregisterFilter` at `0x140012722`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001278f`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14001278f`

## pseudocode

```c
__int64 SqosFilterUnloadInternal()
{
  __int64 v0; // rcx
  __int64 v1; // rax

  if ( ServerPort )
    FltCloseCommunicationPort(ServerPort);
  if ( Filter )
    FltUnregisterFilter((PFLT_FILTER)Filter);
  SqospRundownJobDispatcher(&Object);
  if ( HIBYTE(word_14000D2A8) )
    PcwUnregister(SqosPcFlowCounterSet);
  if ( (_BYTE)word_14000D2A8 )
    PcwUnregister(SqosPcDeviceCounterSet);
  if ( SecurityDescriptor )
    SqospFree(SecurityDescriptor);
  if ( FltWorkItem )
    FltFreeGenericWorkItem(FltWorkItem);
  while ( 1 )
  {
    v0 = qword_14000D168;
    if ( (__int64 *)qword_14000D168 == &qword_14000D168 )
      break;
    if ( *(__int64 **)(qword_14000D168 + 8) != &qword_14000D168
      || (v1 = *(_QWORD *)qword_14000D168, *(_QWORD *)(*(_QWORD *)qword_14000D168 + 8LL) != qword_14000D168) )
    {
      __fastfail(3u);
    }
    qword_14000D168 = *(_QWORD *)qword_14000D168;
    *(_QWORD *)(v1 + 8) = &qword_14000D168;
    SqospFree(v0);
  }
  ExDeleteLookasideListEx(&Lookaside);
  if ( WPP_MAIN_CB.DeviceQueue.1 )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.DeviceQueue.1 = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  WPP_MAIN_CB.Dpc.TargetInfoAsUlong = 0;
  return WppCleanupKm();
}

```

## disassembly

```asm
0x1400126f8  push    rdi
0x1400126fa  sub     rsp, 20h
0x1400126fe  mov     rcx, cs:ServerPort; ServerPort
0x140012705  test    rcx, rcx
0x140012708  jz      short loc_140012716
0x14001270a  call    cs:__imp_FltCloseCommunicationPort
0x140012711  nop     dword ptr [rax+rax+00h]
0x140012716  mov     rcx, cs:Filter; Filter
0x14001271d  test    rcx, rcx
0x140012720  jz      short loc_14001272E
0x140012722  call    cs:__imp_FltUnregisterFilter
0x140012729  nop     dword ptr [rax+rax+00h]
0x14001272e  lea     rcx, Object
0x140012735  call    SqospRundownJobDispatcher
0x14001273a  cmp     byte ptr cs:word_14000D2A8+1, 0
0x140012741  jz      short loc_140012756
0x140012743  mov     rcx, cs:SqosPcFlowCounterSet; Registration
0x14001274a  call    cs:__imp_PcwUnregister
0x140012751  nop     dword ptr [rax+rax+00h]
0x140012756  cmp     byte ptr cs:word_14000D2A8, 0
0x14001275d  jz      short loc_140012772
0x14001275f  mov     rcx, cs:SqosPcDeviceCounterSet; Registration
0x140012766  call    cs:__imp_PcwUnregister
0x14001276d  nop     dword ptr [rax+rax+00h]
0x140012772  mov     rcx, cs:SecurityDescriptor
0x140012779  test    rcx, rcx
0x14001277c  jz      short loc_140012783
0x14001277e  call    SqospFree
0x140012783  mov     rcx, cs:FltWorkItem; FltWorkItem
0x14001278a  test    rcx, rcx
0x14001278d  jz      short loc_14001279B
0x14001278f  call    cs:__imp_FltFreeGenericWorkItem
0x140012796  nop     dword ptr [rax+rax+00h]
0x14001279b  lea     rdi, qword_14000D168
0x1400127a2  mov     rcx, cs:qword_14000D168
0x1400127a9  cmp     rcx, rdi
0x1400127ac  jz      short loc_1400127D6
0x1400127ae  cmp     [rcx+8], rdi
0x1400127b2  jnz     short loc_1400127CF
0x1400127b4  mov     rax, [rcx]
0x1400127b7  cmp     [rax+8], rcx
0x1400127bb  jnz     short loc_1400127CF
0x1400127bd  mov     cs:qword_14000D168, rax
0x1400127c4  mov     [rax+8], rdi
0x1400127c8  call    SqospFree
0x1400127cd  jmp     short loc_1400127A2
0x1400127cf  mov     ecx, 3
0x1400127d4  int     29h; Win8: RtlFailFast(ecx)
0x1400127d6  lea     rcx, Lookaside; Lookaside
0x1400127dd  call    cs:__imp_ExDeleteLookasideListEx
0x1400127e4  nop     dword ptr [rax+rax+00h]
0x1400127e9  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h
0x1400127f0  test    rcx, rcx
0x1400127f3  jz      short loc_14001280C
0x1400127f5  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400127fc  nop     dword ptr [rax+rax+00h]
0x140012801  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 0
0x14001280c  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140012813  test    rcx, rcx
0x140012816  jz      short loc_14001282F
0x140012818  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14001281f  nop     dword ptr [rax+rax+00h]
0x140012824  mov     cs:g_wil_details_featureUsageProvider, 0
0x14001282f  mov     dword ptr cs:WPP_MAIN_CB.Dpc, 0
0x140012839  call    WppCleanupKm
0x14001283e  add     rsp, 20h
0x140012842  pop     rdi
0x140012843  retn
```
