# IppDetachIpsClientCompleteWorkerRoutine

- ea: `0x14018d1c0`
- end: `0x14018d38f`
- name: `IppDetachIpsClientCompleteWorkerRoutine`
- size: `463`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14003fa24`
- `0x14011c5c4`
- `0x140123458`
- `0x14018d1c0`
- `0x14018d838`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018d307`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018d307`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14018d2f7`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14018d2f7`
- `ntoskrnl!IoFreeWorkItem` at `0x14018d31f`
- `ntoskrnl!IoFreeWorkItem` at `0x14018d31f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018d2e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018d2e7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018d215`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018d215`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018d2db`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018d2db`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018d22d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018d22d`
- `NETIO!NmrProviderDetachClientComplete` at `0x14018d367`
- `NETIO!NmrProviderDetachClientComplete` at `0x14018d367`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018d337`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018d337`
- `NDIS!NdisFreeGenericObject` at `0x14018d34f`
- `NDIS!NdisFreeGenericObject` at `0x14018d34f`

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
0x14018d1c0  mov     [rsp+arg_0], rbx
0x14018d1c5  mov     [rsp+arg_10], rsi
0x14018d1ca  push    rdi
0x14018d1cb  push    r14
0x14018d1cd  push    r15
0x14018d1cf  sub     rsp, 20h
0x14018d1d3  mov     rdi, [rdx+10h]
0x14018d1d7  mov     rbx, rdx
0x14018d1da  mov     rcx, cs:WPP_GLOBAL_Control
0x14018d1e1  lea     rax, WPP_GLOBAL_Control
0x14018d1e8  cmp     rcx, rax
0x14018d1eb  jz      short loc_14018D215
0x14018d1ed  cmp     byte ptr [rcx+29h], 4
0x14018d1f1  jb      short loc_14018D215
0x14018d1f3  test    dword ptr [rcx+2Ch], 800000h
0x14018d1fa  jz      short loc_14018D215
0x14018d1fc  mov     rcx, [rcx+18h]
0x14018d200  lea     r9, [rdx+1Ch]
0x14018d204  mov     edx, 0Fh
0x14018d209  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x14018d210  call    WPP_SF_S
0x14018d215  call    cs:__imp_KeEnterCriticalRegion
0x14018d21c  nop     dword ptr [rax+rax+00h]
0x14018d221  lea     rsi, [rdi+4CB0h]
0x14018d228  xor     edx, edx
0x14018d22a  mov     rcx, rsi
0x14018d22d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14018d234  nop     dword ptr [rax+rax+00h]
0x14018d239  dec     dword ptr [rdi+4CC8h]
0x14018d23f  mov     rcx, [rbx]
0x14018d242  cmp     [rcx+8], rbx
0x14018d246  jnz     loc_14018D388
0x14018d24c  mov     rax, [rbx+8]
0x14018d250  cmp     [rax], rbx
0x14018d253  jnz     loc_14018D388
0x14018d259  mov     [rax], rcx
0x14018d25c  xor     edx, edx
0x14018d25e  mov     [rcx+8], rax
0x14018d262  mov     rcx, rbx
0x14018d265  call    IppUpdateIpsServiceChainsForClient
0x14018d26a  lea     rax, [rdi+4CB8h]
0x14018d271  lea     r14, Ipv6Global
0x14018d278  lea     r15, Ipv4Global
0x14018d27f  cmp     [rax], rax
0x14018d282  jnz     short loc_14018D2A1
0x14018d284  cmp     rdi, r15
0x14018d287  jnz     short loc_14018D290
0x14018d289  mov     ecx, 4
0x14018d28e  jmp     short loc_14018D29A
0x14018d290  cmp     rdi, r14
0x14018d293  jnz     short loc_14018D2A1
0x14018d295  mov     ecx, 5
0x14018d29a  xor     edx, edx
0x14018d29c  call    TcpipUpdateUroDisabledMask
0x14018d2a1  cmp     byte ptr [rbx+3Fh], 0
0x14018d2a5  jnz     short loc_14018D2D6
0x14018d2a7  sub     dword ptr [rdi+4CCCh], 1
0x14018d2ae  jnz     short loc_14018D2D6
0x14018d2b0  mov     rcx, rbx
0x14018d2b3  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018d2b8  cmp     rdi, r15
0x14018d2bb  jnz     short loc_14018D2C8
0x14018d2bd  lock btr cs:TcpipGlobalRscDisabledMask, 4
0x14018d2c6  jmp     short loc_14018D2D6
0x14018d2c8  cmp     rdi, r14
0x14018d2cb  jnz     short loc_14018D2D6
0x14018d2cd  lock btr cs:TcpipGlobalRscDisabledMask, 5
0x14018d2d6  xor     edx, edx
0x14018d2d8  mov     rcx, rsi
0x14018d2db  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14018d2e2  nop     dword ptr [rax+rax+00h]
0x14018d2e7  call    cs:__imp_KeLeaveCriticalRegion
0x14018d2ee  nop     dword ptr [rax+rax+00h]
0x14018d2f3  mov     rcx, [rbx+48h]; RunRef
0x14018d2f7  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14018d2fe  nop     dword ptr [rax+rax+00h]
0x14018d303  mov     rcx, [rbx+48h]; RunRefCacheAware
0x14018d307  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14018d30e  nop     dword ptr [rax+rax+00h]
0x14018d313  mov     rcx, [rbx+78h]; IoWorkItem
0x14018d317  mov     qword ptr [rbx+48h], 0
0x14018d31f  call    cs:__imp_IoFreeWorkItem
0x14018d326  nop     dword ptr [rax+rax+00h]
0x14018d32b  mov     rcx, [rbx+68h]; PoolHandle
0x14018d32f  mov     qword ptr [rbx+78h], 0
0x14018d337  call    cs:__imp_NdisFreeNetBufferListPool
0x14018d33e  nop     dword ptr [rax+rax+00h]
0x14018d343  mov     rcx, [rbx+60h]; NdisObject
0x14018d347  mov     qword ptr [rbx+68h], 0
0x14018d34f  call    cs:__imp_NdisFreeGenericObject
0x14018d356  nop     dword ptr [rax+rax+00h]
0x14018d35b  mov     rcx, [rbx+70h]; NmrBindingHandle
0x14018d35f  mov     qword ptr [rbx+60h], 0
0x14018d367  call    cs:__imp_NmrProviderDetachClientComplete
0x14018d36e  nop     dword ptr [rax+rax+00h]
0x14018d373  mov     rbx, [rsp+38h+arg_0]
0x14018d378  mov     rsi, [rsp+38h+arg_10]
0x14018d37d  add     rsp, 20h
0x14018d381  pop     r15
0x14018d383  pop     r14
0x14018d385  pop     rdi
0x14018d386  retn
0x14018d388  mov     ecx, 3
0x14018d38d  int     29h; Win8: RtlFailFast(ecx)
```
