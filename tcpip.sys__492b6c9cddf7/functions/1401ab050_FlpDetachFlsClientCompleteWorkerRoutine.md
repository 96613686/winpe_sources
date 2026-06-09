# FlpDetachFlsClientCompleteWorkerRoutine

- ea: `0x1401ab050`
- end: `0x1401ab1cd`
- name: `FlpDetachFlsClientCompleteWorkerRoutine`
- size: `381`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140157d80`
- `0x1401ab050`
- `0x1401abbc0`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401ab149`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401ab149`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401ab0d2`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401ab0d2`
- `ntoskrnl!IoFreeWorkItem` at `0x1401ab161`
- `ntoskrnl!IoFreeWorkItem` at `0x1401ab161`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ab0c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ab139`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ab0c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ab139`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ab066`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ab0f6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ab066`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ab0f6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ab0b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ab12d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ab0b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ab12d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ab07e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ab107`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ab07e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1401ab107`
- `NETIO!NmrProviderDetachClientComplete` at `0x1401ab1a9`
- `NETIO!NmrProviderDetachClientComplete` at `0x1401ab1a9`
- `NDIS!NdisFreeNetBufferListPool` at `0x1401ab179`
- `NDIS!NdisFreeNetBufferListPool` at `0x1401ab179`
- `NDIS!NdisFreeGenericObject` at `0x1401ab191`
- `NDIS!NdisFreeGenericObject` at `0x1401ab191`

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
0x1401ab050  mov     [rsp+arg_0], rbx
0x1401ab055  mov     [rsp+arg_8], rsi
0x1401ab05a  push    rdi
0x1401ab05b  sub     rsp, 20h
0x1401ab05f  mov     rdi, [rdx+38h]
0x1401ab063  mov     rbx, rdx
0x1401ab066  call    cs:__imp_KeEnterCriticalRegion
0x1401ab06d  nop     dword ptr [rax+rax+00h]
0x1401ab072  lea     rsi, [rdi+2F0h]
0x1401ab079  xor     edx, edx
0x1401ab07b  mov     rcx, rsi
0x1401ab07e  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401ab085  nop     dword ptr [rax+rax+00h]
0x1401ab08a  dec     dword ptr [rdi+308h]
0x1401ab090  mov     rcx, [rbx]
0x1401ab093  cmp     [rcx+8], rbx
0x1401ab097  jnz     loc_1401AB1C6
0x1401ab09d  mov     rax, [rbx+8]
0x1401ab0a1  cmp     [rax], rbx
0x1401ab0a4  jnz     loc_1401AB1C6
0x1401ab0aa  mov     [rax], rcx
0x1401ab0ad  xor     edx, edx
0x1401ab0af  mov     [rcx+8], rax
0x1401ab0b3  mov     rcx, rsi
0x1401ab0b6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ab0bd  nop     dword ptr [rax+rax+00h]
0x1401ab0c2  call    cs:__imp_KeLeaveCriticalRegion
0x1401ab0c9  nop     dword ptr [rax+rax+00h]
0x1401ab0ce  mov     rcx, [rbx+40h]; RunRef
0x1401ab0d2  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401ab0d9  nop     dword ptr [rax+rax+00h]
0x1401ab0de  mov     eax, cs:Feature_TCPIP_FLS_CrossInterface__private_featureState
0x1401ab0e4  test    al, 10h
0x1401ab0e6  jz      short loc_1401AB0ED
0x1401ab0e8  and     eax, 1
0x1401ab0eb  jmp     short loc_1401AB0F2
0x1401ab0ed  call    Feature_TCPIP_FLS_CrossInterface__private_IsEnabledDeviceUsageNoInline
0x1401ab0f2  test    eax, eax
0x1401ab0f4  jz      short loc_1401AB145
0x1401ab0f6  call    cs:__imp_KeEnterCriticalRegion
0x1401ab0fd  nop     dword ptr [rax+rax+00h]
0x1401ab102  xor     edx, edx
0x1401ab104  mov     rcx, rsi
0x1401ab107  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1401ab10e  nop     dword ptr [rax+rax+00h]
0x1401ab113  cmp     dword ptr [rdi+308h], 0
0x1401ab11a  jnz     short loc_1401AB128
0x1401ab11c  lea     rcx, [rdi+298h]
0x1401ab123  call    FlpUninitializeDatapathContexts
0x1401ab128  xor     edx, edx
0x1401ab12a  mov     rcx, rsi
0x1401ab12d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1401ab134  nop     dword ptr [rax+rax+00h]
0x1401ab139  call    cs:__imp_KeLeaveCriticalRegion
0x1401ab140  nop     dword ptr [rax+rax+00h]
0x1401ab145  mov     rcx, [rbx+40h]; RunRefCacheAware
0x1401ab149  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401ab150  nop     dword ptr [rax+rax+00h]
0x1401ab155  mov     rcx, [rbx+70h]; IoWorkItem
0x1401ab159  mov     qword ptr [rbx+40h], 0
0x1401ab161  call    cs:__imp_IoFreeWorkItem
0x1401ab168  nop     dword ptr [rax+rax+00h]
0x1401ab16d  mov     rcx, [rbx+60h]; PoolHandle
0x1401ab171  mov     qword ptr [rbx+70h], 0
0x1401ab179  call    cs:__imp_NdisFreeNetBufferListPool
0x1401ab180  nop     dword ptr [rax+rax+00h]
0x1401ab185  mov     rcx, [rbx+58h]; NdisObject
0x1401ab189  mov     qword ptr [rbx+60h], 0
0x1401ab191  call    cs:__imp_NdisFreeGenericObject
0x1401ab198  nop     dword ptr [rax+rax+00h]
0x1401ab19d  mov     rcx, [rbx+68h]; NmrBindingHandle
0x1401ab1a1  mov     qword ptr [rbx+58h], 0
0x1401ab1a9  call    cs:__imp_NmrProviderDetachClientComplete
0x1401ab1b0  nop     dword ptr [rax+rax+00h]
0x1401ab1b5  mov     rbx, [rsp+28h+arg_0]
0x1401ab1ba  mov     rsi, [rsp+28h+arg_8]
0x1401ab1bf  add     rsp, 20h
0x1401ab1c3  pop     rdi
0x1401ab1c4  retn
0x1401ab1c6  mov     ecx, 3
0x1401ab1cb  int     29h; Win8: RtlFailFast(ecx)
```
