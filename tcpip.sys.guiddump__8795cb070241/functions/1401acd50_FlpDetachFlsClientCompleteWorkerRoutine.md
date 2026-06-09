# FlpDetachFlsClientCompleteWorkerRoutine

- ea: `0x1401acd50`
- end: `0x1401acecd`
- name: `FlpDetachFlsClientCompleteWorkerRoutine`
- size: `381`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140159c54`
- `0x1401acd50`
- `0x1401ad8c0`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401ace49`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401ace49`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401acdd2`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401acdd2`
- `ntoskrnl!IoFreeWorkItem` at `0x1401ace61`
- `ntoskrnl!IoFreeWorkItem` at `0x1401ace61`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401acdc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ace39`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401acdc2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ace39`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401acd66`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401acdf6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401acd66`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401acdf6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401acdb6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ace2d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401acdb6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ace2d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401acd7e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ace07`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401acd7e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ace07`
- `NETIO!NmrProviderDetachClientComplete` at `0x1401acea9`
- `NETIO!NmrProviderDetachClientComplete` at `0x1401acea9`
- `NDIS!NdisFreeNetBufferListPool` at `0x1401ace79`
- `NDIS!NdisFreeNetBufferListPool` at `0x1401ace79`
- `NDIS!NdisFreeGenericObject` at `0x1401ace91`
- `NDIS!NdisFreeGenericObject` at `0x1401ace91`

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
0x1401acd50  mov     [rsp+arg_0], rbx
0x1401acd55  mov     [rsp+arg_8], rsi
0x1401acd5a  push    rdi
0x1401acd5b  sub     rsp, 20h
0x1401acd5f  mov     rdi, [rdx+38h]
0x1401acd63  mov     rbx, rdx
0x1401acd66  call    cs:__imp_KeEnterCriticalRegion
0x1401acd6d  nop     dword ptr [rax+rax+00h]
0x1401acd72  lea     rsi, [rdi+2F0h]
0x1401acd79  xor     edx, edx
0x1401acd7b  mov     rcx, rsi
0x1401acd7e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401acd85  nop     dword ptr [rax+rax+00h]
0x1401acd8a  dec     dword ptr [rdi+308h]
0x1401acd90  mov     rcx, [rbx]
0x1401acd93  cmp     [rcx+8], rbx
0x1401acd97  jnz     loc_1401ACEC6
0x1401acd9d  mov     rax, [rbx+8]
0x1401acda1  cmp     [rax], rbx
0x1401acda4  jnz     loc_1401ACEC6
0x1401acdaa  mov     [rax], rcx
0x1401acdad  xor     edx, edx
0x1401acdaf  mov     [rcx+8], rax
0x1401acdb3  mov     rcx, rsi
0x1401acdb6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401acdbd  nop     dword ptr [rax+rax+00h]
0x1401acdc2  call    cs:__imp_KeLeaveCriticalRegion
0x1401acdc9  nop     dword ptr [rax+rax+00h]
0x1401acdce  mov     rcx, [rbx+40h]; RunRef
0x1401acdd2  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401acdd9  nop     dword ptr [rax+rax+00h]
0x1401acdde  mov     eax, cs:Feature_TCPIP_FLS_CrossInterface__private_featureState
0x1401acde4  test    al, 10h
0x1401acde6  jz      short loc_1401ACDED
0x1401acde8  and     eax, 1
0x1401acdeb  jmp     short loc_1401ACDF2
0x1401acded  call    Feature_TCPIP_FLS_CrossInterface__private_IsEnabledDeviceUsageNoInline
0x1401acdf2  test    eax, eax
0x1401acdf4  jz      short loc_1401ACE45
0x1401acdf6  call    cs:__imp_KeEnterCriticalRegion
0x1401acdfd  nop     dword ptr [rax+rax+00h]
0x1401ace02  xor     edx, edx
0x1401ace04  mov     rcx, rsi
0x1401ace07  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401ace0e  nop     dword ptr [rax+rax+00h]
0x1401ace13  cmp     dword ptr [rdi+308h], 0
0x1401ace1a  jnz     short loc_1401ACE28
0x1401ace1c  lea     rcx, [rdi+298h]
0x1401ace23  call    FlpUninitializeDatapathContexts
0x1401ace28  xor     edx, edx
0x1401ace2a  mov     rcx, rsi
0x1401ace2d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ace34  nop     dword ptr [rax+rax+00h]
0x1401ace39  call    cs:__imp_KeLeaveCriticalRegion
0x1401ace40  nop     dword ptr [rax+rax+00h]
0x1401ace45  mov     rcx, [rbx+40h]; RunRefCacheAware
0x1401ace49  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401ace50  nop     dword ptr [rax+rax+00h]
0x1401ace55  mov     rcx, [rbx+70h]; IoWorkItem
0x1401ace59  mov     qword ptr [rbx+40h], 0
0x1401ace61  call    cs:__imp_IoFreeWorkItem
0x1401ace68  nop     dword ptr [rax+rax+00h]
0x1401ace6d  mov     rcx, [rbx+60h]; PoolHandle
0x1401ace71  mov     qword ptr [rbx+70h], 0
0x1401ace79  call    cs:__imp_NdisFreeNetBufferListPool
0x1401ace80  nop     dword ptr [rax+rax+00h]
0x1401ace85  mov     rcx, [rbx+58h]; NdisObject
0x1401ace89  mov     qword ptr [rbx+60h], 0
0x1401ace91  call    cs:__imp_NdisFreeGenericObject
0x1401ace98  nop     dword ptr [rax+rax+00h]
0x1401ace9d  mov     rcx, [rbx+68h]; NmrBindingHandle
0x1401acea1  mov     qword ptr [rbx+58h], 0
0x1401acea9  call    cs:__imp_NmrProviderDetachClientComplete
0x1401aceb0  nop     dword ptr [rax+rax+00h]
0x1401aceb5  mov     rbx, [rsp+28h+arg_0]
0x1401aceba  mov     rsi, [rsp+28h+arg_8]
0x1401acebf  add     rsp, 20h
0x1401acec3  pop     rdi
0x1401acec4  retn
0x1401acec6  mov     ecx, 3
0x1401acecb  int     29h; Win8: RtlFailFast(ecx)
```
