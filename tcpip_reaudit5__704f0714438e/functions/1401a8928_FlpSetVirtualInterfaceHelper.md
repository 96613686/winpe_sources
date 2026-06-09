# FlpSetVirtualInterfaceHelper

- ea: `0x1401a8928`
- end: `0x1401a8b57`
- name: `FlpSetVirtualInterfaceHelper`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a8280`

## callees

- `0x1400c7b84`
- `0x1401a5044`
- `0x1401a514c`
- `0x1401a5d9c`
- `0x1401a73dc`
- `0x1401a7ec8`
- `0x1401a8928`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401a8b18`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x1401a8b18`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401a8a6f`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x1401a8a6f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a8977`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a8977`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a89e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a89e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a89dd`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a89dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a8962`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a8962`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a8a3b`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1401a8a3b`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a8a8e`
- `NDIS!NdisAcquireRWLockWrite` at `0x1401a8a8e`
- `NDIS!NdisReleaseRWLock` at `0x1401a8aba`
- `NDIS!NdisReleaseRWLock` at `0x1401a8aba`

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
0x1401a8928  mov     [rsp-28h+arg_0], rsi
0x1401a892d  mov     [rsp-28h+arg_10], rdi
0x1401a8932  push    rbp
0x1401a8933  push    r12
0x1401a8935  push    r13
0x1401a8937  push    r14
0x1401a8939  push    r15
0x1401a893b  mov     rbp, rsp
0x1401a893e  sub     rsp, 50h
0x1401a8942  xor     eax, eax
0x1401a8944  xor     edi, edi
0x1401a8946  mov     r14, r9
0x1401a8949  mov     r13, r8
0x1401a894c  mov     r12, rdx
0x1401a894f  mov     r15, rcx
0x1401a8952  mov     word ptr [rbp+LockState.OldIrql], ax
0x1401a8956  mov     [rbp+LockState.Flags], al
0x1401a8959  cmp     [rdx+18h], eax
0x1401a895c  jz      loc_1401A8A23
0x1401a8962  call    cs:__imp_KeEnterCriticalRegion
0x1401a8969  nop     dword ptr [rax+rax+00h]
0x1401a896e  mov     dl, 1; Wait
0x1401a8970  lea     rcx, Resource; Resource
0x1401a8977  call    cs:__imp_ExAcquireResourceSharedLite
0x1401a897e  nop     dword ptr [rax+rax+00h]
0x1401a8983  mov     rcx, [r12]
0x1401a8987  mov     edx, [r12+18h]
0x1401a898c  call    FlIfpFindVirtualInterfaceUnderLock
0x1401a8991  mov     rsi, rax
0x1401a8994  mov     eax, cs:Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_featureState
0x1401a899a  test    al, 10h
0x1401a899c  jz      short loc_1401A89A3
0x1401a899e  and     eax, 1
0x1401a89a1  jmp     short loc_1401A89A8
0x1401a89a3  call    Feature_TCPIP_Wave5_FlVirtSetFailureReasonFix__private_IsEnabledDeviceUsageNoInline
0x1401a89a8  test    eax, eax
0x1401a89aa  jz      short loc_1401A89BA
0x1401a89ac  test    rsi, rsi
0x1401a89af  jnz     short loc_1401A89BF
0x1401a89b1  mov     dword ptr [r14], 7
0x1401a89b8  jmp     short loc_1401A89D1
0x1401a89ba  test    rsi, rsi
0x1401a89bd  jz      short loc_1401A89D1
0x1401a89bf  mov     r9, r14
0x1401a89c2  mov     rdx, rsi
0x1401a89c5  mov     rcx, r15
0x1401a89c8  call    FlIfIsVirtualInterfaceAccessibleByThread
0x1401a89cd  test    al, al
0x1401a89cf  jnz     short loc_1401A89D6
0x1401a89d1  mov     edi, 0C0000225h
0x1401a89d6  lea     rcx, Resource; Resource
0x1401a89dd  call    cs:__imp_ExReleaseResourceLite
0x1401a89e4  nop     dword ptr [rax+rax+00h]
0x1401a89e9  call    cs:__imp_KeLeaveCriticalRegion
0x1401a89f0  nop     dword ptr [rax+rax+00h]
0x1401a89f5  test    edi, edi
0x1401a89f7  js      loc_1401A8B3A
0x1401a89fd  mov     edx, [r12+18h]
0x1401a8a02  mov     rcx, r15
0x1401a8a05  call    FlpFindClientInterfaceByIsolationId
0x1401a8a0a  mov     rsi, rax
0x1401a8a0d  test    rax, rax
0x1401a8a10  jnz     short loc_1401A8A66
0x1401a8a12  mov     edi, 0C0000225h
0x1401a8a17  mov     dword ptr [r14], 9
0x1401a8a1e  jmp     loc_1401A8B3A
0x1401a8a23  mov     r9b, 1
0x1401a8a26  mov     [rsp+50h+var_30], rax
0x1401a8a2b  lea     rdx, [rcx+3B8h]
0x1401a8a32  mov     r8b, r9b
0x1401a8a35  mov     ecx, [rcx+4A0h]
0x1401a8a3b  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1401a8a42  nop     dword ptr [rax+rax+00h]
0x1401a8a47  test    al, al
0x1401a8a49  jnz     short loc_1401A8A5C
0x1401a8a4b  mov     edi, 0C0000225h
0x1401a8a50  mov     dword ptr [r14], 4
0x1401a8a57  jmp     loc_1401A8B3A
0x1401a8a5c  mov     rcx, r15
0x1401a8a5f  call    FlpFindDefaultClientInterface
0x1401a8a64  jmp     short loc_1401A8A0A
0x1401a8a66  mov     rcx, [rsi+38h]; RunRefCacheAware
0x1401a8a6a  mov     edx, 1; Count
0x1401a8a6f  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x1401a8a76  nop     dword ptr [rax+rax+00h]
0x1401a8a7b  test    al, al
0x1401a8a7d  jz      loc_1401A8B26
0x1401a8a83  mov     rcx, [r15+28h]; Lock
0x1401a8a87  lea     rdx, [rbp+LockState]; LockState
0x1401a8a8b  xor     r8d, r8d; Flags
0x1401a8a8e  call    cs:__imp_NdisAcquireRWLockWrite
0x1401a8a95  nop     dword ptr [rax+rax+00h]
0x1401a8a9a  mov     cl, [r13+0]
0x1401a8a9e  cmp     cl, 0FFh
0x1401a8aa1  jz      short loc_1401A8AB2
0x1401a8aa3  mov     al, [rsi+40h]
0x1401a8aa6  add     cl, cl
0x1401a8aa8  xor     cl, al
0x1401a8aaa  and     cl, 2
0x1401a8aad  xor     cl, al
0x1401a8aaf  mov     [rsi+40h], cl
0x1401a8ab2  mov     rcx, [r15+28h]; Lock
0x1401a8ab6  lea     rdx, [rbp+LockState]; LockState
0x1401a8aba  call    cs:__imp_NdisReleaseRWLock
0x1401a8ac1  nop     dword ptr [rax+rax+00h]
0x1401a8ac6  mov     rax, [rsi+88h]
0x1401a8acd  xor     cl, cl
0x1401a8acf  mov     [rbp+var_20], rax
0x1401a8ad3  or      cl, 10h
0x1401a8ad6  xor     eax, eax
0x1401a8ad8  mov     [rbp+var_18], cl
0x1401a8adb  mov     [rbp+var_14], eax
0x1401a8ade  mov     [rbp-17h], eax
0x1401a8ae1  mov     word ptr [rbp+var_14+1], ax
0x1401a8ae5  mov     byte ptr [rbp+var_14+3], al
0x1401a8ae8  lea     rax, [r15+4D8h]
0x1401a8aef  mov     [rbp+var_10], rax
0x1401a8af3  mov     rax, [r15+20h]
0x1401a8af7  mov     rcx, [rax+0D8h]
0x1401a8afe  mov     rax, [rcx+8]
0x1401a8b02  lea     rcx, [rbp+var_20]
0x1401a8b06  mov     rax, [rax+18h]
0x1401a8b0a  call    _guard_dispatch_icall
0x1401a8b0f  mov     rcx, [rsi+38h]; RunRef
0x1401a8b13  mov     edx, 1; Count
0x1401a8b18  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x1401a8b1f  nop     dword ptr [rax+rax+00h]
0x1401a8b24  jmp     short loc_1401A8B32
0x1401a8b26  mov     edi, 0C0000225h
0x1401a8b2b  mov     dword ptr [r14], 14h
0x1401a8b32  mov     rcx, rsi
0x1401a8b35  call    FlpDereferenceClientInterface
0x1401a8b3a  lea     r11, [rsp+50h+var_s0]
0x1401a8b3f  mov     eax, edi
0x1401a8b41  mov     rsi, [r11+30h]
0x1401a8b45  mov     rdi, [r11+40h]
0x1401a8b49  mov     rsp, r11
0x1401a8b4c  pop     r15
0x1401a8b4e  pop     r14
0x1401a8b50  pop     r13
0x1401a8b52  pop     r12
0x1401a8b54  pop     rbp
0x1401a8b55  retn
```
