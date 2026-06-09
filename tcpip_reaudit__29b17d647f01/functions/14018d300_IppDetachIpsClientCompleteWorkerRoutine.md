# IppDetachIpsClientCompleteWorkerRoutine

- ea: `0x14018d300`
- end: `0x14018d4cf`
- name: `IppDetachIpsClientCompleteWorkerRoutine`
- size: `463`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14003fcc4`
- `0x14011c704`
- `0x140123598`
- `0x14018d300`
- `0x14018d978`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018d447`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018d447`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14018d437`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14018d437`
- `ntoskrnl!IoFreeWorkItem` at `0x14018d45f`
- `ntoskrnl!IoFreeWorkItem` at `0x14018d45f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018d427`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018d427`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018d355`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018d355`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018d41b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018d41b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018d36d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018d36d`
- `NETIO!NmrProviderDetachClientComplete` at `0x14018d4a7`
- `NETIO!NmrProviderDetachClientComplete` at `0x14018d4a7`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018d477`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018d477`
- `NDIS!NdisFreeGenericObject` at `0x14018d48f`
- `NDIS!NdisFreeGenericObject` at `0x14018d48f`

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
    WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids, Context + 28);
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
0x14018d300  mov     [rsp+arg_0], rbx
0x14018d305  mov     [rsp+arg_10], rsi
0x14018d30a  push    rdi
0x14018d30b  push    r14
0x14018d30d  push    r15
0x14018d30f  sub     rsp, 20h
0x14018d313  mov     rdi, [rdx+10h]
0x14018d317  mov     rbx, rdx
0x14018d31a  mov     rcx, cs:WPP_GLOBAL_Control
0x14018d321  lea     rax, WPP_GLOBAL_Control
0x14018d328  cmp     rcx, rax
0x14018d32b  jz      short loc_14018D355
0x14018d32d  cmp     byte ptr [rcx+29h], 4
0x14018d331  jb      short loc_14018D355
0x14018d333  test    dword ptr [rcx+2Ch], 800000h
0x14018d33a  jz      short loc_14018D355
0x14018d33c  mov     rcx, [rcx+18h]
0x14018d340  lea     r9, [rdx+1Ch]
0x14018d344  mov     edx, 0Fh
0x14018d349  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x14018d350  call    WPP_SF_S
0x14018d355  call    cs:__imp_KeEnterCriticalRegion
0x14018d35c  nop     dword ptr [rax+rax+00h]
0x14018d361  lea     rsi, [rdi+4CB0h]
0x14018d368  xor     edx, edx
0x14018d36a  mov     rcx, rsi
0x14018d36d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14018d374  nop     dword ptr [rax+rax+00h]
0x14018d379  dec     dword ptr [rdi+4CC8h]
0x14018d37f  mov     rcx, [rbx]
0x14018d382  cmp     [rcx+8], rbx
0x14018d386  jnz     loc_14018D4C8
0x14018d38c  mov     rax, [rbx+8]
0x14018d390  cmp     [rax], rbx
0x14018d393  jnz     loc_14018D4C8
0x14018d399  mov     [rax], rcx
0x14018d39c  xor     edx, edx
0x14018d39e  mov     [rcx+8], rax
0x14018d3a2  mov     rcx, rbx
0x14018d3a5  call    IppUpdateIpsServiceChainsForClient
0x14018d3aa  lea     rax, [rdi+4CB8h]
0x14018d3b1  lea     r14, Ipv6Global
0x14018d3b8  lea     r15, Ipv4Global
0x14018d3bf  cmp     [rax], rax
0x14018d3c2  jnz     short loc_14018D3E1
0x14018d3c4  cmp     rdi, r15
0x14018d3c7  jnz     short loc_14018D3D0
0x14018d3c9  mov     ecx, 4
0x14018d3ce  jmp     short loc_14018D3DA
0x14018d3d0  cmp     rdi, r14
0x14018d3d3  jnz     short loc_14018D3E1
0x14018d3d5  mov     ecx, 5
0x14018d3da  xor     edx, edx
0x14018d3dc  call    TcpipUpdateUroDisabledMask
0x14018d3e1  cmp     byte ptr [rbx+3Fh], 0
0x14018d3e5  jnz     short loc_14018D416
0x14018d3e7  sub     dword ptr [rdi+4CCCh], 1
0x14018d3ee  jnz     short loc_14018D416
0x14018d3f0  mov     rcx, rbx
0x14018d3f3  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018d3f8  cmp     rdi, r15
0x14018d3fb  jnz     short loc_14018D408
0x14018d3fd  lock btr cs:TcpipGlobalRscDisabledMask, 4
0x14018d406  jmp     short loc_14018D416
0x14018d408  cmp     rdi, r14
0x14018d40b  jnz     short loc_14018D416
0x14018d40d  lock btr cs:TcpipGlobalRscDisabledMask, 5
0x14018d416  xor     edx, edx
0x14018d418  mov     rcx, rsi
0x14018d41b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14018d422  nop     dword ptr [rax+rax+00h]
0x14018d427  call    cs:__imp_KeLeaveCriticalRegion
0x14018d42e  nop     dword ptr [rax+rax+00h]
0x14018d433  mov     rcx, [rbx+48h]; RunRef
0x14018d437  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14018d43e  nop     dword ptr [rax+rax+00h]
0x14018d443  mov     rcx, [rbx+48h]; RunRefCacheAware
0x14018d447  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14018d44e  nop     dword ptr [rax+rax+00h]
0x14018d453  mov     rcx, [rbx+78h]; IoWorkItem
0x14018d457  mov     qword ptr [rbx+48h], 0
0x14018d45f  call    cs:__imp_IoFreeWorkItem
0x14018d466  nop     dword ptr [rax+rax+00h]
0x14018d46b  mov     rcx, [rbx+68h]; PoolHandle
0x14018d46f  mov     qword ptr [rbx+78h], 0
0x14018d477  call    cs:__imp_NdisFreeNetBufferListPool
0x14018d47e  nop     dword ptr [rax+rax+00h]
0x14018d483  mov     rcx, [rbx+60h]; NdisObject
0x14018d487  mov     qword ptr [rbx+68h], 0
0x14018d48f  call    cs:__imp_NdisFreeGenericObject
0x14018d496  nop     dword ptr [rax+rax+00h]
0x14018d49b  mov     rcx, [rbx+70h]; NmrBindingHandle
0x14018d49f  mov     qword ptr [rbx+60h], 0
0x14018d4a7  call    cs:__imp_NmrProviderDetachClientComplete
0x14018d4ae  nop     dword ptr [rax+rax+00h]
0x14018d4b3  mov     rbx, [rsp+38h+arg_0]
0x14018d4b8  mov     rsi, [rsp+38h+arg_10]
0x14018d4bd  add     rsp, 20h
0x14018d4c1  pop     r15
0x14018d4c3  pop     r14
0x14018d4c5  pop     rdi
0x14018d4c6  retn
0x14018d4c8  mov     ecx, 3
0x14018d4cd  int     29h; Win8: RtlFailFast(ecx)
```
