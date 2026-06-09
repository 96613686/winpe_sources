# IppDetachIpsClientCompleteWorkerRoutine

- ea: `0x14018efa0`
- end: `0x14018f16f`
- name: `IppDetachIpsClientCompleteWorkerRoutine`
- size: `463`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1400f99d0`
- `0x140126284`
- `0x14012d708`
- `0x14018efa0`
- `0x14018f618`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018f0e7`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018f0e7`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14018f0d7`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14018f0d7`
- `ntoskrnl!IoFreeWorkItem` at `0x14018f0ff`
- `ntoskrnl!IoFreeWorkItem` at `0x14018f0ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018f0c7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018f0c7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018eff5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018eff5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018f0bb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018f0bb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018f00d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018f00d`
- `NETIO!NmrProviderDetachClientComplete` at `0x14018f147`
- `NETIO!NmrProviderDetachClientComplete` at `0x14018f147`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018f117`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018f117`
- `NDIS!NdisFreeGenericObject` at `0x14018f12f`
- `NDIS!NdisFreeGenericObject` at `0x14018f12f`

## pseudocode

```c
void __fastcall IppDetachIpsClientCompleteWorkerRoutine(PDEVICE_OBJECT DeviceObject, char *Context)
{
  __int64 v2; // rdi
  _QWORD *v4; // rcx
  PVOID *v5; // rax
  __int64 v6; // rcx
  struct _IO_WORKITEM *v8; // rcx
  void *v9; // rcx
  struct _NDIS_GENERIC_OBJECT *v10; // rcx
  void *v11; // rcx

  v2 = *((_QWORD *)Context + 2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
  {
    WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids, Context + 28);
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v2 + 19632, 0);
  --*(_DWORD *)(v2 + 19656);
  v4 = *(_QWORD **)Context;
  if ( *(char **)(*(_QWORD *)Context + 8LL) != Context || (v5 = (PVOID *)*((_QWORD *)Context + 1), *v5 != Context) )
    __fastfail(3u);
  *v5 = v4;
  v4[1] = v5;
  IppUpdateIpsServiceChainsForClient(Context, 0);
  if ( *(_QWORD *)(v2 + 19640) == v2 + 19640 )
  {
    if ( (int *)v2 == &Ipv4Global )
    {
      v6 = 4;
LABEL_12:
      TcpipUpdateUroDisabledMask(v6, 0);
      goto LABEL_13;
    }
    if ( (__int64 *)v2 == &Ipv6Global )
    {
      v6 = 5;
      goto LABEL_12;
    }
  }
LABEL_13:
  if ( !Context[63] && (*(_DWORD *)(v2 + 19660))-- == 1 )
  {
    IppIpsNotifyNlClientsOnAllInterfaces(Context);
    if ( (int *)v2 == &Ipv4Global )
    {
      _interlockedbittestandreset(&TcpipGlobalRscDisabledMask, 4u);
    }
    else if ( (__int64 *)v2 == &Ipv6Global )
    {
      _interlockedbittestandreset(&TcpipGlobalRscDisabledMask, 5u);
    }
  }
  ExReleasePushLockExclusiveEx(v2 + 19632, 0);
  KeLeaveCriticalRegion();
  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 9));
  ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)Context + 9));
  v8 = (struct _IO_WORKITEM *)*((_QWORD *)Context + 15);
  *((_QWORD *)Context + 9) = 0;
  IoFreeWorkItem(v8);
  v9 = (void *)*((_QWORD *)Context + 13);
  *((_QWORD *)Context + 15) = 0;
  NdisFreeNetBufferListPool(v9);
  v10 = (struct _NDIS_GENERIC_OBJECT *)*((_QWORD *)Context + 12);
  *((_QWORD *)Context + 13) = 0;
  NdisFreeGenericObject(v10);
  v11 = (void *)*((_QWORD *)Context + 14);
  *((_QWORD *)Context + 12) = 0;
  NmrProviderDetachClientComplete(v11);
}

```

## disassembly

```asm
0x14018efa0  mov     [rsp+arg_0], rbx
0x14018efa5  mov     [rsp+arg_10], rsi
0x14018efaa  push    rdi
0x14018efab  push    r14
0x14018efad  push    r15
0x14018efaf  sub     rsp, 20h
0x14018efb3  mov     rdi, [rdx+10h]
0x14018efb7  mov     rbx, rdx
0x14018efba  mov     rcx, cs:WPP_GLOBAL_Control
0x14018efc1  lea     rax, WPP_GLOBAL_Control
0x14018efc8  cmp     rcx, rax
0x14018efcb  jz      short loc_14018EFF5
0x14018efcd  cmp     byte ptr [rcx+29h], 4
0x14018efd1  jb      short loc_14018EFF5
0x14018efd3  test    dword ptr [rcx+2Ch], 800000h
0x14018efda  jz      short loc_14018EFF5
0x14018efdc  mov     rcx, [rcx+18h]
0x14018efe0  lea     r9, [rdx+1Ch]
0x14018efe4  mov     edx, 0Fh
0x14018efe9  lea     r8, WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids
0x14018eff0  call    WPP_SF_S
0x14018eff5  call    cs:__imp_KeEnterCriticalRegion
0x14018effc  nop     dword ptr [rax+rax+00h]
0x14018f001  lea     rsi, [rdi+4CB0h]
0x14018f008  xor     edx, edx
0x14018f00a  mov     rcx, rsi
0x14018f00d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14018f014  nop     dword ptr [rax+rax+00h]
0x14018f019  dec     dword ptr [rdi+4CC8h]
0x14018f01f  mov     rcx, [rbx]
0x14018f022  cmp     [rcx+8], rbx
0x14018f026  jnz     loc_14018F168
0x14018f02c  mov     rax, [rbx+8]
0x14018f030  cmp     [rax], rbx
0x14018f033  jnz     loc_14018F168
0x14018f039  mov     [rax], rcx
0x14018f03c  xor     edx, edx
0x14018f03e  mov     [rcx+8], rax
0x14018f042  mov     rcx, rbx
0x14018f045  call    IppUpdateIpsServiceChainsForClient
0x14018f04a  lea     rax, [rdi+4CB8h]
0x14018f051  lea     r14, Ipv6Global
0x14018f058  lea     r15, Ipv4Global
0x14018f05f  cmp     [rax], rax
0x14018f062  jnz     short loc_14018F081
0x14018f064  cmp     rdi, r15
0x14018f067  jnz     short loc_14018F070
0x14018f069  mov     ecx, 4
0x14018f06e  jmp     short loc_14018F07A
0x14018f070  cmp     rdi, r14
0x14018f073  jnz     short loc_14018F081
0x14018f075  mov     ecx, 5
0x14018f07a  xor     edx, edx
0x14018f07c  call    TcpipUpdateUroDisabledMask
0x14018f081  cmp     byte ptr [rbx+3Fh], 0
0x14018f085  jnz     short loc_14018F0B6
0x14018f087  sub     dword ptr [rdi+4CCCh], 1
0x14018f08e  jnz     short loc_14018F0B6
0x14018f090  mov     rcx, rbx
0x14018f093  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018f098  cmp     rdi, r15
0x14018f09b  jnz     short loc_14018F0A8
0x14018f09d  lock btr cs:TcpipGlobalRscDisabledMask, 4
0x14018f0a6  jmp     short loc_14018F0B6
0x14018f0a8  cmp     rdi, r14
0x14018f0ab  jnz     short loc_14018F0B6
0x14018f0ad  lock btr cs:TcpipGlobalRscDisabledMask, 5
0x14018f0b6  xor     edx, edx
0x14018f0b8  mov     rcx, rsi
0x14018f0bb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14018f0c2  nop     dword ptr [rax+rax+00h]
0x14018f0c7  call    cs:__imp_KeLeaveCriticalRegion
0x14018f0ce  nop     dword ptr [rax+rax+00h]
0x14018f0d3  mov     rcx, [rbx+48h]; RunRef
0x14018f0d7  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14018f0de  nop     dword ptr [rax+rax+00h]
0x14018f0e3  mov     rcx, [rbx+48h]; RunRefCacheAware
0x14018f0e7  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14018f0ee  nop     dword ptr [rax+rax+00h]
0x14018f0f3  mov     rcx, [rbx+78h]; IoWorkItem
0x14018f0f7  mov     qword ptr [rbx+48h], 0
0x14018f0ff  call    cs:__imp_IoFreeWorkItem
0x14018f106  nop     dword ptr [rax+rax+00h]
0x14018f10b  mov     rcx, [rbx+68h]; PoolHandle
0x14018f10f  mov     qword ptr [rbx+78h], 0
0x14018f117  call    cs:__imp_NdisFreeNetBufferListPool
0x14018f11e  nop     dword ptr [rax+rax+00h]
0x14018f123  mov     rcx, [rbx+60h]; NdisObject
0x14018f127  mov     qword ptr [rbx+68h], 0
0x14018f12f  call    cs:__imp_NdisFreeGenericObject
0x14018f136  nop     dword ptr [rax+rax+00h]
0x14018f13b  mov     rcx, [rbx+70h]; NmrBindingHandle
0x14018f13f  mov     qword ptr [rbx+60h], 0
0x14018f147  call    cs:__imp_NmrProviderDetachClientComplete
0x14018f14e  nop     dword ptr [rax+rax+00h]
0x14018f153  mov     rbx, [rsp+38h+arg_0]
0x14018f158  mov     rsi, [rsp+38h+arg_10]
0x14018f15d  add     rsp, 20h
0x14018f161  pop     r15
0x14018f163  pop     r14
0x14018f165  pop     rdi
0x14018f166  retn
0x14018f168  mov     ecx, 3
0x14018f16d  int     29h; Win8: RtlFailFast(ecx)
```
