# FlpSetVirtualInterfaceHelper

- ea: `0x1401a87e8`
- end: `0x1401a8a17`
- name: `FlpSetVirtualInterfaceHelper`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a8140`

## callees

- `0x1400c7da4`
- `0x1401a4f04`
- `0x1401a500c`
- `0x1401a5c5c`
- `0x1401a729c`
- `0x1401a7d88`
- `0x1401a87e8`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401a892f`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401a892f`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401a89d8`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401a89d8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a8837`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a8837`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a88a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a88a9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a889d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a889d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a8822`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a8822`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a88fb`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a88fb`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a894e`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a894e`
- `NDIS!NdisReleaseRWLock` at `0x1401a897a`
- `NDIS!NdisReleaseRWLock` at `0x1401a897a`

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
0x1401a87e8  mov     [rsp-28h+arg_0], rsi
0x1401a87ed  mov     [rsp-28h+arg_10], rdi
0x1401a87f2  push    rbp
0x1401a87f3  push    r12
0x1401a87f5  push    r13
0x1401a87f7  push    r14
0x1401a87f9  push    r15
0x1401a87fb  mov     rbp, rsp
0x1401a87fe  sub     rsp, 50h
0x1401a8802  xor     eax, eax
0x1401a8804  xor     edi, edi
0x1401a8806  mov     r14, r9
0x1401a8809  mov     r13, r8
0x1401a880c  mov     r12, rdx
0x1401a880f  mov     r15, rcx
0x1401a8812  mov     word ptr [rbp+LockState.OldIrql], ax
0x1401a8816  mov     [rbp+LockState.Flags], al
0x1401a8819  cmp     [rdx+18h], eax
0x1401a881c  jz      loc_1401A88E3
0x1401a8822  call    cs:__imp_KeEnterCriticalRegion
0x1401a8829  nop     dword ptr [rax+rax+00h]
0x1401a882e  mov     dl, 1; Wait
0x1401a8830  lea     rcx, Resource; Resource
0x1401a8837  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a883e  nop     dword ptr [rax+rax+00h]
0x1401a8843  mov     rcx, [r12]
0x1401a8847  mov     edx, [r12+18h]
0x1401a884c  call    FlIfpFindVirtualInterfaceUnderLock
0x1401a8851  mov     rsi, rax
0x1401a8854  mov     eax, cs:Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_featureState
0x1401a885a  test    al, 10h
0x1401a885c  jz      short loc_1401A8863
0x1401a885e  and     eax, 1
0x1401a8861  jmp     short loc_1401A8868
0x1401a8863  call    Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_IsEnabledDeviceUsageNoInline
0x1401a8868  test    eax, eax
0x1401a886a  jz      short loc_1401A887A
0x1401a886c  test    rsi, rsi
0x1401a886f  jnz     short loc_1401A887F
0x1401a8871  mov     dword ptr [r14], 7
0x1401a8878  jmp     short loc_1401A8891
0x1401a887a  test    rsi, rsi
0x1401a887d  jz      short loc_1401A8891
0x1401a887f  mov     r9, r14
0x1401a8882  mov     rdx, rsi
0x1401a8885  mov     rcx, r15
0x1401a8888  call    FlIfIsVirtualInterfaceAccessibleByThread
0x1401a888d  test    al, al
0x1401a888f  jnz     short loc_1401A8896
0x1401a8891  mov     edi, 0C0000225h
0x1401a8896  lea     rcx, Resource; Resource
0x1401a889d  call    cs:__imp_ExReleaseResourceLite
0x1401a88a4  nop     dword ptr [rax+rax+00h]
0x1401a88a9  call    cs:__imp_KeLeaveCriticalRegion
0x1401a88b0  nop     dword ptr [rax+rax+00h]
0x1401a88b5  test    edi, edi
0x1401a88b7  js      loc_1401A89FA
0x1401a88bd  mov     edx, [r12+18h]
0x1401a88c2  mov     rcx, r15
0x1401a88c5  call    FlpFindClientInterfaceByIsolationId
0x1401a88ca  mov     rsi, rax
0x1401a88cd  test    rax, rax
0x1401a88d0  jnz     short loc_1401A8926
0x1401a88d2  mov     edi, 0C0000225h
0x1401a88d7  mov     dword ptr [r14], 9
0x1401a88de  jmp     loc_1401A89FA
0x1401a88e3  mov     r9b, 1
0x1401a88e6  mov     [rsp+50h+var_30], rax
0x1401a88eb  lea     rdx, [rcx+3B8h]
0x1401a88f2  mov     r8b, r9b
0x1401a88f5  mov     ecx, [rcx+4A0h]
0x1401a88fb  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401a8902  nop     dword ptr [rax+rax+00h]
0x1401a8907  test    al, al
0x1401a8909  jnz     short loc_1401A891C
0x1401a890b  mov     edi, 0C0000225h
0x1401a8910  mov     dword ptr [r14], 4
0x1401a8917  jmp     loc_1401A89FA
0x1401a891c  mov     rcx, r15
0x1401a891f  call    FlpFindDefaultClientInterface
0x1401a8924  jmp     short loc_1401A88CA
0x1401a8926  mov     rcx, [rsi+38h]; RunRefCacheAware
0x1401a892a  mov     edx, 1; Count
0x1401a892f  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401a8936  nop     dword ptr [rax+rax+00h]
0x1401a893b  test    al, al
0x1401a893d  jz      loc_1401A89E6
0x1401a8943  mov     rcx, [r15+28h]; Lock
0x1401a8947  lea     rdx, [rbp+LockState]; LockState
0x1401a894b  xor     r8d, r8d; Flags
0x1401a894e  call    cs:__imp_NdisAcquireRWLockWrite
0x1401a8955  nop     dword ptr [rax+rax+00h]
0x1401a895a  mov     cl, [r13+0]
0x1401a895e  cmp     cl, 0FFh
0x1401a8961  jz      short loc_1401A8972
0x1401a8963  mov     al, [rsi+40h]
0x1401a8966  add     cl, cl
0x1401a8968  xor     cl, al
0x1401a896a  and     cl, 2
0x1401a896d  xor     cl, al
0x1401a896f  mov     [rsi+40h], cl
0x1401a8972  mov     rcx, [r15+28h]; Lock
0x1401a8976  lea     rdx, [rbp+LockState]; LockState
0x1401a897a  call    cs:__imp_NdisReleaseRWLock
0x1401a8981  nop     dword ptr [rax+rax+00h]
0x1401a8986  mov     rax, [rsi+88h]
0x1401a898d  xor     cl, cl
0x1401a898f  mov     [rbp+var_20], rax
0x1401a8993  or      cl, 10h
0x1401a8996  xor     eax, eax
0x1401a8998  mov     [rbp+var_18], cl
0x1401a899b  mov     [rbp+var_14], eax
0x1401a899e  mov     [rbp-17h], eax
0x1401a89a1  mov     word ptr [rbp+var_14+1], ax
0x1401a89a5  mov     byte ptr [rbp+var_14+3], al
0x1401a89a8  lea     rax, [r15+4D8h]
0x1401a89af  mov     [rbp+var_10], rax
0x1401a89b3  mov     rax, [r15+20h]
0x1401a89b7  mov     rcx, [rax+0D8h]
0x1401a89be  mov     rax, [rcx+8]
0x1401a89c2  lea     rcx, [rbp+var_20]
0x1401a89c6  mov     rax, [rax+18h]
0x1401a89ca  call    _guard_dispatch_icall
0x1401a89cf  mov     rcx, [rsi+38h]; RunRef
0x1401a89d3  mov     edx, 1; Count
0x1401a89d8  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401a89df  nop     dword ptr [rax+rax+00h]
0x1401a89e4  jmp     short loc_1401A89F2
0x1401a89e6  mov     edi, 0C0000225h
0x1401a89eb  mov     dword ptr [r14], 14h
0x1401a89f2  mov     rcx, rsi
0x1401a89f5  call    FlpDereferenceClientInterface
0x1401a89fa  lea     r11, [rsp+50h+var_s0]
0x1401a89ff  mov     eax, edi
0x1401a8a01  mov     rsi, [r11+30h]
0x1401a8a05  mov     rdi, [r11+40h]
0x1401a8a09  mov     rsp, r11
0x1401a8a0c  pop     r15
0x1401a8a0e  pop     r14
0x1401a8a10  pop     r13
0x1401a8a12  pop     r12
0x1401a8a14  pop     rbp
0x1401a8a15  retn
```
