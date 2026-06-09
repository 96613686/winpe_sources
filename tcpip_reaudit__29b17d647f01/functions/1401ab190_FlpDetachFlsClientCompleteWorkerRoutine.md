# FlpDetachFlsClientCompleteWorkerRoutine

- ea: `0x1401ab190`
- end: `0x1401ab30d`
- name: `FlpDetachFlsClientCompleteWorkerRoutine`
- size: `381`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140157ec0`
- `0x1401ab190`
- `0x1401abd00`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401ab289`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401ab289`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401ab212`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401ab212`
- `ntoskrnl!IoFreeWorkItem` at `0x1401ab2a1`
- `ntoskrnl!IoFreeWorkItem` at `0x1401ab2a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ab202`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ab279`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ab202`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ab279`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ab1a6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ab236`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ab1a6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ab236`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ab1f6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ab26d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ab1f6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ab26d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ab1be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ab247`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ab1be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ab247`
- `NETIO!NmrProviderDetachClientComplete` at `0x1401ab2e9`
- `NETIO!NmrProviderDetachClientComplete` at `0x1401ab2e9`
- `NDIS!NdisFreeNetBufferListPool` at `0x1401ab2b9`
- `NDIS!NdisFreeNetBufferListPool` at `0x1401ab2b9`
- `NDIS!NdisFreeGenericObject` at `0x1401ab2d1`
- `NDIS!NdisFreeGenericObject` at `0x1401ab2d1`

## pseudocode

```c
void __fastcall FlpDetachFlsClientCompleteWorkerRoutine(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  __int64 v2; // rdi
  _QWORD *v4; // rcx
  PVOID *v5; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  struct _IO_WORKITEM *v7; // rcx
  void *v8; // rcx
  struct _NDIS_GENERIC_OBJECT *v9; // rcx
  void *v10; // rcx

  v2 = *((_QWORD *)Context + 7);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v2 + 752, 0);
  --*(_DWORD *)(v2 + 776);
  v4 = *(_QWORD **)Context;
  if ( *(PVOID *)(*(_QWORD *)Context + 8LL) != Context || (v5 = (PVOID *)*((_QWORD *)Context + 1), *v5 != Context) )
    __fastfail(3u);
  *v5 = v4;
  v4[1] = v5;
  ExReleasePushLockExclusiveEx(v2 + 752, 0);
  KeLeaveCriticalRegion();
  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 8));
  if ( (Feature_TCPIP_FLS_CrossInterface__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_FLS_CrossInterface__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_FLS_CrossInterface__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v2 + 752, 0);
    if ( !*(_DWORD *)(v2 + 776) )
      FlpUninitializeDatapathContexts(v2 + 664);
    ExReleasePushLockExclusiveEx(v2 + 752, 0);
    KeLeaveCriticalRegion();
  }
  ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 8));
  v7 = (struct _IO_WORKITEM *)*((_QWORD *)Context + 14);
  *((_QWORD *)Context + 8) = 0;
  IoFreeWorkItem(v7);
  v8 = (void *)*((_QWORD *)Context + 12);
  *((_QWORD *)Context + 14) = 0;
  NdisFreeNetBufferListPool(v8);
  v9 = (struct _NDIS_GENERIC_OBJECT *)*((_QWORD *)Context + 11);
  *((_QWORD *)Context + 12) = 0;
  NdisFreeGenericObject(v9);
  v10 = (void *)*((_QWORD *)Context + 13);
  *((_QWORD *)Context + 11) = 0;
  NmrProviderDetachClientComplete(v10);
}

```

## disassembly

```asm
0x1401ab190  mov     [rsp+arg_0], rbx
0x1401ab195  mov     [rsp+arg_8], rsi
0x1401ab19a  push    rdi
0x1401ab19b  sub     rsp, 20h
0x1401ab19f  mov     rdi, [rdx+38h]
0x1401ab1a3  mov     rbx, rdx
0x1401ab1a6  call    cs:__imp_KeEnterCriticalRegion
0x1401ab1ad  nop     dword ptr [rax+rax+00h]
0x1401ab1b2  lea     rsi, [rdi+2F0h]
0x1401ab1b9  xor     edx, edx
0x1401ab1bb  mov     rcx, rsi
0x1401ab1be  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401ab1c5  nop     dword ptr [rax+rax+00h]
0x1401ab1ca  dec     dword ptr [rdi+308h]
0x1401ab1d0  mov     rcx, [rbx]
0x1401ab1d3  cmp     [rcx+8], rbx
0x1401ab1d7  jnz     loc_1401AB306
0x1401ab1dd  mov     rax, [rbx+8]
0x1401ab1e1  cmp     [rax], rbx
0x1401ab1e4  jnz     loc_1401AB306
0x1401ab1ea  mov     [rax], rcx
0x1401ab1ed  xor     edx, edx
0x1401ab1ef  mov     [rcx+8], rax
0x1401ab1f3  mov     rcx, rsi
0x1401ab1f6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ab1fd  nop     dword ptr [rax+rax+00h]
0x1401ab202  call    cs:__imp_KeLeaveCriticalRegion
0x1401ab209  nop     dword ptr [rax+rax+00h]
0x1401ab20e  mov     rcx, [rbx+40h]; RunRef
0x1401ab212  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401ab219  nop     dword ptr [rax+rax+00h]
0x1401ab21e  mov     eax, cs:Feature_TCPIP_FLS_CrossInterface__private_featureState
0x1401ab224  test    al, 10h
0x1401ab226  jz      short loc_1401AB22D
0x1401ab228  and     eax, 1
0x1401ab22b  jmp     short loc_1401AB232
0x1401ab22d  call    Feature_TCPIP_FLS_CrossInterface__private_IsEnabledDeviceUsageNoInline
0x1401ab232  test    eax, eax
0x1401ab234  jz      short loc_1401AB285
0x1401ab236  call    cs:__imp_KeEnterCriticalRegion
0x1401ab23d  nop     dword ptr [rax+rax+00h]
0x1401ab242  xor     edx, edx
0x1401ab244  mov     rcx, rsi
0x1401ab247  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401ab24e  nop     dword ptr [rax+rax+00h]
0x1401ab253  cmp     dword ptr [rdi+308h], 0
0x1401ab25a  jnz     short loc_1401AB268
0x1401ab25c  lea     rcx, [rdi+298h]
0x1401ab263  call    FlpUninitializeDatapathContexts
0x1401ab268  xor     edx, edx
0x1401ab26a  mov     rcx, rsi
0x1401ab26d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ab274  nop     dword ptr [rax+rax+00h]
0x1401ab279  call    cs:__imp_KeLeaveCriticalRegion
0x1401ab280  nop     dword ptr [rax+rax+00h]
0x1401ab285  mov     rcx, [rbx+40h]; RunRefCacheAware
0x1401ab289  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401ab290  nop     dword ptr [rax+rax+00h]
0x1401ab295  mov     rcx, [rbx+70h]; IoWorkItem
0x1401ab299  mov     qword ptr [rbx+40h], 0
0x1401ab2a1  call    cs:__imp_IoFreeWorkItem
0x1401ab2a8  nop     dword ptr [rax+rax+00h]
0x1401ab2ad  mov     rcx, [rbx+60h]; PoolHandle
0x1401ab2b1  mov     qword ptr [rbx+70h], 0
0x1401ab2b9  call    cs:__imp_NdisFreeNetBufferListPool
0x1401ab2c0  nop     dword ptr [rax+rax+00h]
0x1401ab2c5  mov     rcx, [rbx+58h]; NdisObject
0x1401ab2c9  mov     qword ptr [rbx+60h], 0
0x1401ab2d1  call    cs:__imp_NdisFreeGenericObject
0x1401ab2d8  nop     dword ptr [rax+rax+00h]
0x1401ab2dd  mov     rcx, [rbx+68h]; NmrBindingHandle
0x1401ab2e1  mov     qword ptr [rbx+58h], 0
0x1401ab2e9  call    cs:__imp_NmrProviderDetachClientComplete
0x1401ab2f0  nop     dword ptr [rax+rax+00h]
0x1401ab2f5  mov     rbx, [rsp+28h+arg_0]
0x1401ab2fa  mov     rsi, [rsp+28h+arg_8]
0x1401ab2ff  add     rsp, 20h
0x1401ab303  pop     rdi
0x1401ab304  retn
0x1401ab306  mov     ecx, 3
0x1401ab30b  int     29h; Win8: RtlFailFast(ecx)
```
