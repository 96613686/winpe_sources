# FlpSetVirtualInterfaceHelper

- ea: `0x1401aa4e8`
- end: `0x1401aa717`
- name: `FlpSetVirtualInterfaceHelper`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a9e40`

## callees

- `0x1400fb124`
- `0x1401a6c04`
- `0x1401a6d0c`
- `0x1401a795c`
- `0x1401a8f9c`
- `0x1401a9a88`
- `0x1401aa4e8`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401aa62f`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401aa62f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401aa537`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401aa537`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa5a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401aa5a9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401aa59d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401aa59d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401aa522`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401aa522`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401aa6d8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401aa6d8`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401aa5fb`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401aa5fb`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401aa64e`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401aa64e`
- `NDIS!NdisReleaseRWLock` at `0x1401aa67a`
- `NDIS!NdisReleaseRWLock` at `0x1401aa67a`

## pseudocode

```c
__int64 __fastcall FlpSetVirtualInterfaceHelper(__int64 a1, __int64 a2, _BYTE *a3, _DWORD *a4)
{
  unsigned int v4; // edi
  _BYTE *v6; // r13
  __int64 VirtualInterfaceUnderLock; // rsi
  __int64 v10; // r8
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 DefaultClientInterface; // rax
  __int64 v13; // rsi
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  char v16; // [rsp+38h] [rbp-18h]
  int v17; // [rsp+39h] [rbp-17h]
  __int16 v18; // [rsp+3Dh] [rbp-13h]
  char v19; // [rsp+3Fh] [rbp-11h]
  __int64 v20; // [rsp+40h] [rbp-10h]
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+38h] BYREF

  v4 = 0;
  v6 = a3;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  if ( !*(_DWORD *)(a2 + 24) )
  {
    LOBYTE(a3) = 1;
    if ( !(unsigned __int8)NetioIsCompartmentAccessibleByThread(*(unsigned int *)(a1 + 1184), a1 + 952, a3) )
    {
      v4 = -1073741275;
      *a4 = 4;
      return v4;
    }
    DefaultClientInterface = FlpFindDefaultClientInterface(a1);
    goto LABEL_13;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(&Resource, 1u);
  VirtualInterfaceUnderLock = FlIfpFindVirtualInterfaceUnderLock(*(_QWORD *)a2, *(unsigned int *)(a2 + 24));
  if ( (Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( !VirtualInterfaceUnderLock )
    {
      *a4 = 7;
LABEL_10:
      v4 = -1073741275;
      goto LABEL_11;
    }
  }
  else if ( !VirtualInterfaceUnderLock )
  {
    goto LABEL_10;
  }
  if ( !(unsigned __int8)FlIfIsVirtualInterfaceAccessibleByThread(a1, VirtualInterfaceUnderLock, v10, a4) )
    goto LABEL_10;
LABEL_11:
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
  if ( (v4 & 0x80000000) != 0 )
    return v4;
  DefaultClientInterface = FlpFindClientInterfaceByIsolationId(a1, *(unsigned int *)(a2 + 24));
LABEL_13:
  v13 = DefaultClientInterface;
  if ( DefaultClientInterface )
  {
    if ( ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(DefaultClientInterface + 56), 1u) )
    {
      NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 40), &LockState, 0);
      if ( *v6 != 0xFF )
        *(_BYTE *)(v13 + 64) ^= (*(_BYTE *)(v13 + 64) ^ (2 * *v6)) & 2;
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 40), &LockState);
      v15 = *(_QWORD *)(v13 + 136);
      v16 = 16;
      v17 = 0;
      v18 = 0;
      v19 = 0;
      v20 = a1 + 1240;
      (*(void (__fastcall **)(__int64 *))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 216LL) + 8LL) + 24LL))(&v15);
      ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v13 + 56), 1u);
    }
    else
    {
      v4 = -1073741275;
      *a4 = 20;
    }
    FlpDereferenceClientInterface(v13);
  }
  else
  {
    v4 = -1073741275;
    *a4 = 9;
  }
  return v4;
}

```

## disassembly

```asm
0x1401aa4e8  mov     [rsp-28h+arg_0], rsi
0x1401aa4ed  mov     [rsp-28h+arg_10], rdi
0x1401aa4f2  push    rbp
0x1401aa4f3  push    r12
0x1401aa4f5  push    r13
0x1401aa4f7  push    r14
0x1401aa4f9  push    r15
0x1401aa4fb  mov     rbp, rsp
0x1401aa4fe  sub     rsp, 50h
0x1401aa502  xor     eax, eax
0x1401aa504  xor     edi, edi
0x1401aa506  mov     r14, r9
0x1401aa509  mov     r13, r8
0x1401aa50c  mov     r12, rdx
0x1401aa50f  mov     r15, rcx
0x1401aa512  mov     word ptr [rbp+LockState.OldIrql], ax
0x1401aa516  mov     [rbp+LockState.Flags], al
0x1401aa519  cmp     [rdx+18h], eax
0x1401aa51c  jz      loc_1401AA5E3
0x1401aa522  call    cs:__imp_KeEnterCriticalRegion
0x1401aa529  nop     dword ptr [rax+rax+00h]
0x1401aa52e  mov     dl, 1; Wait
0x1401aa530  lea     rcx, Resource; Resource
0x1401aa537  call    cs:__imp_ExAcquireResourceSharedLite
0x1401aa53e  nop     dword ptr [rax+rax+00h]
0x1401aa543  mov     rcx, [r12]
0x1401aa547  mov     edx, [r12+18h]
0x1401aa54c  call    FlIfpFindVirtualInterfaceUnderLock
0x1401aa551  mov     rsi, rax
0x1401aa554  mov     eax, cs:Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_featureState
0x1401aa55a  test    al, 10h
0x1401aa55c  jz      short loc_1401AA563
0x1401aa55e  and     eax, 1
0x1401aa561  jmp     short loc_1401AA568
0x1401aa563  call    Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_IsEnabledDeviceUsageNoInline
0x1401aa568  test    eax, eax
0x1401aa56a  jz      short loc_1401AA57A
0x1401aa56c  test    rsi, rsi
0x1401aa56f  jnz     short loc_1401AA57F
0x1401aa571  mov     dword ptr [r14], 7
0x1401aa578  jmp     short loc_1401AA591
0x1401aa57a  test    rsi, rsi
0x1401aa57d  jz      short loc_1401AA591
0x1401aa57f  mov     r9, r14
0x1401aa582  mov     rdx, rsi
0x1401aa585  mov     rcx, r15
0x1401aa588  call    FlIfIsVirtualInterfaceAccessibleByThread
0x1401aa58d  test    al, al
0x1401aa58f  jnz     short loc_1401AA596
0x1401aa591  mov     edi, 0C0000225h
0x1401aa596  lea     rcx, Resource; Resource
0x1401aa59d  call    cs:__imp_ExReleaseResourceLite
0x1401aa5a4  nop     dword ptr [rax+rax+00h]
0x1401aa5a9  call    cs:__imp_KeLeaveCriticalRegion
0x1401aa5b0  nop     dword ptr [rax+rax+00h]
0x1401aa5b5  test    edi, edi
0x1401aa5b7  js      loc_1401AA6FA
0x1401aa5bd  mov     edx, [r12+18h]
0x1401aa5c2  mov     rcx, r15
0x1401aa5c5  call    FlpFindClientInterfaceByIsolationId
0x1401aa5ca  mov     rsi, rax
0x1401aa5cd  test    rax, rax
0x1401aa5d0  jnz     short loc_1401AA626
0x1401aa5d2  mov     edi, 0C0000225h
0x1401aa5d7  mov     dword ptr [r14], 9
0x1401aa5de  jmp     loc_1401AA6FA
0x1401aa5e3  mov     r9b, 1
0x1401aa5e6  mov     [rsp+50h+var_30], rax
0x1401aa5eb  lea     rdx, [rcx+3B8h]
0x1401aa5f2  mov     r8b, r9b
0x1401aa5f5  mov     ecx, [rcx+4A0h]
0x1401aa5fb  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401aa602  nop     dword ptr [rax+rax+00h]
0x1401aa607  test    al, al
0x1401aa609  jnz     short loc_1401AA61C
0x1401aa60b  mov     edi, 0C0000225h
0x1401aa610  mov     dword ptr [r14], 4
0x1401aa617  jmp     loc_1401AA6FA
0x1401aa61c  mov     rcx, r15
0x1401aa61f  call    FlpFindDefaultClientInterface
0x1401aa624  jmp     short loc_1401AA5CA
0x1401aa626  mov     rcx, [rsi+38h]; RunRefCacheAware
0x1401aa62a  mov     edx, 1; Count
0x1401aa62f  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401aa636  nop     dword ptr [rax+rax+00h]
0x1401aa63b  test    al, al
0x1401aa63d  jz      loc_1401AA6E6
0x1401aa643  mov     rcx, [r15+28h]; Lock
0x1401aa647  lea     rdx, [rbp+LockState]; LockState
0x1401aa64b  xor     r8d, r8d; Flags
0x1401aa64e  call    cs:__imp_NdisAcquireRWLockWrite
0x1401aa655  nop     dword ptr [rax+rax+00h]
0x1401aa65a  mov     cl, [r13+0]
0x1401aa65e  cmp     cl, 0FFh
0x1401aa661  jz      short loc_1401AA672
0x1401aa663  mov     al, [rsi+40h]
0x1401aa666  add     cl, cl
0x1401aa668  xor     cl, al
0x1401aa66a  and     cl, 2
0x1401aa66d  xor     cl, al
0x1401aa66f  mov     [rsi+40h], cl
0x1401aa672  mov     rcx, [r15+28h]; Lock
0x1401aa676  lea     rdx, [rbp+LockState]; LockState
0x1401aa67a  call    cs:__imp_NdisReleaseRWLock
0x1401aa681  nop     dword ptr [rax+rax+00h]
0x1401aa686  mov     rax, [rsi+88h]
0x1401aa68d  xor     cl, cl
0x1401aa68f  mov     [rbp+var_20], rax
0x1401aa693  or      cl, 10h
0x1401aa696  xor     eax, eax
0x1401aa698  mov     [rbp+var_18], cl
0x1401aa69b  mov     [rbp+var_14], eax
0x1401aa69e  mov     [rbp-17h], eax
0x1401aa6a1  mov     word ptr [rbp+var_14+1], ax
0x1401aa6a5  mov     byte ptr [rbp+var_14+3], al
0x1401aa6a8  lea     rax, [r15+4D8h]
0x1401aa6af  mov     [rbp+var_10], rax
0x1401aa6b3  mov     rax, [r15+20h]
0x1401aa6b7  mov     rcx, [rax+0D8h]
0x1401aa6be  mov     rax, [rcx+8]
0x1401aa6c2  lea     rcx, [rbp+var_20]
0x1401aa6c6  mov     rax, [rax+18h]
0x1401aa6ca  call    _guard_dispatch_icall
0x1401aa6cf  mov     rcx, [rsi+38h]; RunRef
0x1401aa6d3  mov     edx, 1; Count
0x1401aa6d8  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401aa6df  nop     dword ptr [rax+rax+00h]
0x1401aa6e4  jmp     short loc_1401AA6F2
0x1401aa6e6  mov     edi, 0C0000225h
0x1401aa6eb  mov     dword ptr [r14], 14h
0x1401aa6f2  mov     rcx, rsi
0x1401aa6f5  call    FlpDereferenceClientInterface
0x1401aa6fa  lea     r11, [rsp+50h+var_s0]
0x1401aa6ff  mov     eax, edi
0x1401aa701  mov     rsi, [r11+30h]
0x1401aa705  mov     rdi, [r11+40h]
0x1401aa709  mov     rsp, r11
0x1401aa70c  pop     r15
0x1401aa70e  pop     r14
0x1401aa710  pop     r13
0x1401aa712  pop     r12
0x1401aa714  pop     rbp
0x1401aa715  retn
```
