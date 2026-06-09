# SrvAdminCleanupEx

- ea: `0x140021d88`
- end: `0x140021fba`
- name: `SrvAdminCleanupEx`
- size: `562`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14000fc18`
- `0x140021d70`

## callees

- `0x1400141ec`
- `0x140021594`
- `0x140021d88`
- `0x14002395c`
- `0x140024ab8`
- `0x14002993c`
- `0x140029b40`
- `0x14004ba54`
- `0x14004c120`
- `0x14004cc20`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140021f9b`
- `ntoskrnl!IoDeleteDevice` at `0x140021f9b`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021efd`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f10`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f23`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f36`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f49`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f5c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021efd`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f10`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f23`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f36`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f49`
- `ntoskrnl!ExDeleteResourceLite` at `0x140021f5c`
- `ntoskrnl!PoDeletePowerRequest` at `0x140021e14`
- `ntoskrnl!PoDeletePowerRequest` at `0x140021e33`
- `ntoskrnl!PoDeletePowerRequest` at `0x140021e14`
- `ntoskrnl!PoDeletePowerRequest` at `0x140021e33`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140021e52`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140021e71`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140021e52`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x140021e71`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140021f7d`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140021f7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021dab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021dc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021dab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021dc8`
- `ntoskrnl!EtwUnregister` at `0x140021eaf`
- `ntoskrnl!EtwUnregister` at `0x140021eaf`
- `ext-ms-win-kmpdc-l1-1-0!Pdcv2ActivationClientUnregister` at `0x140021e90`
- `ext-ms-win-kmpdc-l1-1-0!Pdcv2ActivationClientUnregister` at `0x140021e90`

## pseudocode

```c
__int64 SrvAdminCleanupEx()
{
  SrvAdminAliasCleanup();
  SrvAdminDeleteFsctlPropertyList();
  if ( SrvAdminNullSessionShares )
    ExFreePoolWithTag(SrvAdminNullSessionShares, 0x52736652u);
  if ( SrvAdminNullSessionPipes )
    ExFreePoolWithTag(SrvAdminNullSessionPipes, 0x52736652u);
  SrvAdminFreePipeList();
  SrvAdminCleanupNameLists();
  SrvAdminLocalNodeUninitialize();
  _m_prefetchw(&dword_140036DE0);
  if ( (_InterlockedOr(&dword_140036DE0, 1u) & 0x20) != 0 )
    RfsTimerCancel();
  if ( SrvPowerOpenFileRequest )
  {
    PoDeletePowerRequest(SrvPowerOpenFileRequest);
    SrvPowerOpenFileRequest = 0;
  }
  if ( SrvPowerNonIdleRequest )
  {
    PoDeletePowerRequest(SrvPowerNonIdleRequest);
    SrvPowerNonIdleRequest = 0;
  }
  if ( SrvPowerLowPowerEpochHandle )
  {
    PoUnregisterPowerSettingCallback(SrvPowerLowPowerEpochHandle);
    SrvPowerLowPowerEpochHandle = 0;
  }
  if ( SrvPowerAcDcPowerSourceHandle )
  {
    PoUnregisterPowerSettingCallback(SrvPowerAcDcPowerSourceHandle);
    SrvPowerAcDcPowerSourceHandle = 0;
  }
  if ( SrvPowerNetworkActivator )
  {
    Pdcv2ActivationClientUnregister();
    SrvPowerNetworkActivator = 0;
  }
  if ( KSumRegHandle )
  {
    EtwUnregister(KSumRegHandle);
    KSumRegHandle = 0;
  }
  if ( SrvAdminInstanceStarted )
    SrvAdminCleanupInstances();
  if ( hProviderTable )
  {
    RfsTableCleanup((PVOID)hProviderTable);
    hProviderTable = 0;
  }
  if ( LockInitialized )
  {
    ExDeleteResourceLite(&ProviderLock);
    ExDeleteResourceLite(&AliasLock);
    ExDeleteResourceLite(&AnonymousLock);
    ExDeleteResourceLite(&SrvAdminNameLock);
    ExDeleteResourceLite(&SrvAdminInstanceListLock);
    ExDeleteResourceLite(&SrvAdminInstanceStartStopLock);
    LockInitialized = 0;
  }
  if ( SrvAdminPagedListInitialized )
  {
    ExDeletePagedLookasideList(&SrvAdminPagedList256);
    SrvAdminPagedListInitialized = 0;
  }
  if ( SrvAdminDeviceObject )
  {
    IoDeleteDevice(SrvAdminDeviceObject);
    SrvAdminDeviceObject = 0;
  }
  return TraceLoggingUnregister_EtwUnregister();
}

```

## disassembly

```asm
0x140021d88  push    rbx
0x140021d8a  sub     rsp, 20h
0x140021d8e  call    SrvAdminAliasCleanup
0x140021d93  call    SrvAdminDeleteFsctlPropertyList
0x140021d98  mov     rcx, cs:SrvAdminNullSessionShares; P
0x140021d9f  xor     ebx, ebx
0x140021da1  test    rcx, rcx
0x140021da4  jz      short loc_140021DB7
0x140021da6  mov     edx, 52736652h; Tag
0x140021dab  call    cs:__imp_ExFreePoolWithTag
0x140021db2  nop     dword ptr [rax+rax+00h]
0x140021db7  mov     rcx, cs:SrvAdminNullSessionPipes; P
0x140021dbe  test    rcx, rcx
0x140021dc1  jz      short loc_140021DD4
0x140021dc3  mov     edx, 52736652h; Tag
0x140021dc8  call    cs:__imp_ExFreePoolWithTag
0x140021dcf  nop     dword ptr [rax+rax+00h]
0x140021dd4  call    SrvAdminFreePipeList
0x140021dd9  call    SrvAdminCleanupNameLists
0x140021dde  call    SrvAdminLocalNodeUninitialize
0x140021de3  prefetchw byte ptr cs:dword_140036DE0
0x140021dea  mov     eax, cs:dword_140036DE0
0x140021df0  mov     ecx, eax
0x140021df2  or      ecx, 1
0x140021df5  lock cmpxchg cs:dword_140036DE0, ecx
0x140021dfd  jnz     short loc_140021DF0
0x140021dff  test    al, 20h
0x140021e01  jz      short loc_140021E08
0x140021e03  call    RfsTimerCancel
0x140021e08  mov     rcx, cs:SrvPowerOpenFileRequest; PowerRequest
0x140021e0f  test    rcx, rcx
0x140021e12  jz      short loc_140021E27
0x140021e14  call    cs:__imp_PoDeletePowerRequest
0x140021e1b  nop     dword ptr [rax+rax+00h]
0x140021e20  mov     cs:SrvPowerOpenFileRequest, rbx
0x140021e27  mov     rcx, cs:SrvPowerNonIdleRequest; PowerRequest
0x140021e2e  test    rcx, rcx
0x140021e31  jz      short loc_140021E46
0x140021e33  call    cs:__imp_PoDeletePowerRequest
0x140021e3a  nop     dword ptr [rax+rax+00h]
0x140021e3f  mov     cs:SrvPowerNonIdleRequest, rbx
0x140021e46  mov     rcx, cs:SrvPowerLowPowerEpochHandle; Handle
0x140021e4d  test    rcx, rcx
0x140021e50  jz      short loc_140021E65
0x140021e52  call    cs:__imp_PoUnregisterPowerSettingCallback
0x140021e59  nop     dword ptr [rax+rax+00h]
0x140021e5e  mov     cs:SrvPowerLowPowerEpochHandle, rbx
0x140021e65  mov     rcx, cs:SrvPowerAcDcPowerSourceHandle; Handle
0x140021e6c  test    rcx, rcx
0x140021e6f  jz      short loc_140021E84
0x140021e71  call    cs:__imp_PoUnregisterPowerSettingCallback
0x140021e78  nop     dword ptr [rax+rax+00h]
0x140021e7d  mov     cs:SrvPowerAcDcPowerSourceHandle, rbx
0x140021e84  mov     rcx, cs:SrvPowerNetworkActivator
0x140021e8b  test    rcx, rcx
0x140021e8e  jz      short loc_140021EA3
0x140021e90  call    cs:__imp_Pdcv2ActivationClientUnregister
0x140021e97  nop     dword ptr [rax+rax+00h]
0x140021e9c  mov     cs:SrvPowerNetworkActivator, rbx
0x140021ea3  mov     rcx, cs:KSumRegHandle; RegHandle
0x140021eaa  test    rcx, rcx
0x140021ead  jz      short loc_140021EC2
0x140021eaf  call    cs:__imp_EtwUnregister
0x140021eb6  nop     dword ptr [rax+rax+00h]
0x140021ebb  mov     cs:KSumRegHandle, rbx
0x140021ec2  cmp     cs:SrvAdminInstanceStarted, bl
0x140021ec8  jz      short loc_140021ECF
0x140021eca  call    SrvAdminCleanupInstances
0x140021ecf  mov     rcx, cs:hProviderTable; P
0x140021ed6  test    rcx, rcx
0x140021ed9  jz      short loc_140021EEE
0x140021edb  lea     rdx, SrvAdminFree
0x140021ee2  call    RfsTableCleanup
0x140021ee7  mov     cs:hProviderTable, rbx
0x140021eee  cmp     cs:LockInitialized, bl
0x140021ef4  jz      short loc_140021F6E
0x140021ef6  lea     rcx, ProviderLock; Resource
0x140021efd  call    cs:__imp_ExDeleteResourceLite
0x140021f04  nop     dword ptr [rax+rax+00h]
0x140021f09  lea     rcx, AliasLock; Resource
0x140021f10  call    cs:__imp_ExDeleteResourceLite
0x140021f17  nop     dword ptr [rax+rax+00h]
0x140021f1c  lea     rcx, AnonymousLock; Resource
0x140021f23  call    cs:__imp_ExDeleteResourceLite
0x140021f2a  nop     dword ptr [rax+rax+00h]
0x140021f2f  lea     rcx, SrvAdminNameLock; Resource
0x140021f36  call    cs:__imp_ExDeleteResourceLite
0x140021f3d  nop     dword ptr [rax+rax+00h]
0x140021f42  lea     rcx, SrvAdminInstanceListLock; Resource
0x140021f49  call    cs:__imp_ExDeleteResourceLite
0x140021f50  nop     dword ptr [rax+rax+00h]
0x140021f55  lea     rcx, SrvAdminInstanceStartStopLock; Resource
0x140021f5c  call    cs:__imp_ExDeleteResourceLite
0x140021f63  nop     dword ptr [rax+rax+00h]
0x140021f68  mov     cs:LockInitialized, bl
0x140021f6e  cmp     cs:SrvAdminPagedListInitialized, bl
0x140021f74  jz      short loc_140021F8F
0x140021f76  lea     rcx, SrvAdminPagedList256; Lookaside
0x140021f7d  call    cs:__imp_ExDeletePagedLookasideList
0x140021f84  nop     dword ptr [rax+rax+00h]
0x140021f89  mov     cs:SrvAdminPagedListInitialized, bl
0x140021f8f  mov     rcx, cs:SrvAdminDeviceObject; DeviceObject
0x140021f96  test    rcx, rcx
0x140021f99  jz      short loc_140021FAE
0x140021f9b  call    cs:__imp_IoDeleteDevice
0x140021fa2  nop     dword ptr [rax+rax+00h]
0x140021fa7  mov     cs:SrvAdminDeviceObject, rbx
0x140021fae  call    TraceLoggingUnregister_EtwUnregister
0x140021fb3  add     rsp, 20h
0x140021fb7  pop     rbx
0x140021fb8  retn
```
