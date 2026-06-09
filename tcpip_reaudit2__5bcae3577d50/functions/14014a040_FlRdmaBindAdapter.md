# FlRdmaBindAdapter

- ea: `0x14014a040`
- end: `0x14014a2cc`
- name: `FlRdmaBindAdapter`
- size: `652`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400c5290`
- `0x140116c94`
- `0x140124f60`
- `0x140148ad0`
- `0x14014a040`
- `0x1401ae38c`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014a1dc`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014a1dc`
- `ntoskrnl!IoQueueWorkItem` at `0x14014a297`
- `ntoskrnl!IoQueueWorkItem` at `0x14014a297`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014a183`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014a183`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014a22a`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014a22a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014a1b1`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014a241`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014a1b1`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014a241`
- `NDIS!NdisReleaseRWLock` at `0x14014a1cc`
- `NDIS!NdisReleaseRWLock` at `0x14014a266`
- `NDIS!NdisReleaseRWLock` at `0x14014a1cc`
- `NDIS!NdisReleaseRWLock` at `0x14014a266`
- `NDIS!NdisOpenAdapterEx` at `0x14014a154`
- `NDIS!NdisOpenAdapterEx` at `0x14014a154`

## pseudocode

```c
__int64 __fastcall FlRdmaBindAdapter(ULONG_PTR a1, void *a2, __int64 a3)
{
  struct _EX_RUNDOWN_REF *Interface; // rax
  struct _EX_RUNDOWN_REF *v8; // rdi
  struct _EX_RUNDOWN_REF *v9; // r15
  int v10; // ecx
  NDIS_STATUS Count; // ebx
  struct _NDIS_RW_LOCK_EX *v12; // rcx
  struct _NDIS_RW_LOCK_EX *v13; // rcx
  char inited; // bl
  struct _NDIS_OPEN_PARAMETERS OpenParameters; // [rsp+30h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+B0h] [rbp+38h] BYREF

  memset(&OpenParameters, 0, sizeof(OpenParameters));
  if ( !*(_QWORD *)(a3 + 288) )
    return 65537;
  Interface = FlpCreateInterface(a1);
  v8 = Interface;
  if ( !Interface )
    return 3221225626LL;
  LODWORD(Interface[25].Count) |= 1u;
  v9 = Interface + 39;
  v10 = LODWORD(Interface[25].Count)
      ^ ((unsigned __int8)LODWORD(Interface[25].Count)
       ^ (unsigned __int8)(2 * *(_BYTE *)(a3 + 280)))
      & 2;
  HIDWORD(Interface[24].Ptr) |= 3u;
  LODWORD(Interface[25].Count) = v10;
  Interface[161].Count = *(ULONG_PTR *)(a3 + 24);
  Interface[146].Count = *(ULONG_PTR *)(a3 + 168);
  LODWORD(Interface[147].Count) = *(_DWORD *)(a3 + 176);
  Interface[134].Count = (ULONG_PTR)&Interface[133];
  Interface[133].Count = (ULONG_PTR)&Interface[133];
  OpenParameters.AdapterName = *(PNDIS_STRING *)(a3 + 16);
  OpenParameters.MediumArray = (PNDIS_MEDIUM)(a1 + 484);
  OpenParameters.MediumArraySize = *(_DWORD *)(a1 + 480);
  OpenParameters.FrameTypeArray = (PNET_FRAME_TYPE)(a1 + 508);
  OpenParameters.FrameTypeArraySize = *(_DWORD *)(a1 + 504);
  OpenParameters.Header = (NDIS_OBJECT_HEADER)3670407;
  OpenParameters.SelectedMediumIndex = (PUINT)&Interface[39];
  Count = NdisOpenAdapterEx(*(NDIS_HANDLE *)(a1 + 368), Interface, &OpenParameters, a2, (PNDIS_HANDLE)&Interface[160]);
  if ( Count == 259 )
  {
    KeWaitForSingleObject(&v8[21], UserRequest, 0, 0, 0);
    Count = v8[24].Count;
  }
  if ( Count < 0 )
  {
    FlRdmapLogInterfaceEvent(v8, 0, (unsigned int)Count);
    FlpDereferenceInterface(v8);
  }
  else
  {
    v12 = (struct _NDIS_RW_LOCK_EX *)v8[5].Count;
    *(_WORD *)&LockState.OldIrql = 0;
    LockState.Flags = 0;
    NdisAcquireRWLockWrite(v12, &LockState, 0);
    v13 = (struct _NDIS_RW_LOCK_EX *)v8[5].Count;
    HIDWORD(v8[24].Ptr) &= ~1u;
    NdisReleaseRWLock(v13, &LockState);
    ExReInitializeRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v8[10].Count);
    LODWORD(v9->Count) = *(_DWORD *)(a1 + 4LL * LODWORD(v9->Count) + 484);
    FlpInsertInterface(v8[4].Count + 440, v8);
    NetioRegisterTriageDumpDataCallback(&v8[136], 1, FlpPopulateInterfaceTriageDumpData, v8, "FLIf");
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v8[5].Count, &LockState, 0);
    inited = FlRdmapNsiInitNotification(v8, 1);
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v8[5].Count, &LockState);
    FlRdmapLogInterfaceEvent(v8, 0, 0);
    if ( inited )
      IoQueueWorkItem((PIO_WORKITEM)v8[12].Count, FlRdmapNSINotificationWorkerRoutine, DelayedWorkQueue, v8);
    return 0;
  }
  return (unsigned int)Count;
}

```

## disassembly

```asm
0x14014a040  push    rbp
0x14014a042  push    rbx
0x14014a043  push    rsi
0x14014a044  push    rdi
0x14014a045  push    r14
0x14014a047  push    r15
0x14014a049  mov     rbp, rsp
0x14014a04c  sub     rsp, 78h
0x14014a050  xorps   xmm0, xmm0
0x14014a053  xor     eax, eax
0x14014a055  mov     rbx, r8
0x14014a058  mov     r14, rdx
0x14014a05b  mov     rsi, rcx
0x14014a05e  mov     qword ptr [rbp+OpenParameters.FrameTypeArraySize], rax
0x14014a062  movups  xmmword ptr [rbp+OpenParameters.Header.Type], xmm0
0x14014a066  movups  xmmword ptr [rbp+OpenParameters.MediumArray], xmm0
0x14014a06a  movups  xmmword ptr [rbp+OpenParameters.SelectedMediumIndex], xmm0
0x14014a06e  cmp     [r8+120h], rax
0x14014a075  jnz     short loc_14014A081
0x14014a077  mov     eax, 10001h
0x14014a07c  jmp     loc_14014A2BE
0x14014a081  call    FlpCreateInterface
0x14014a086  mov     rdi, rax
0x14014a089  test    rax, rax
0x14014a08c  jnz     short loc_14014A098
0x14014a08e  mov     eax, 0C000009Ah
0x14014a093  jmp     loc_14014A2BE
0x14014a098  or      dword ptr [rax+0C8h], 1
0x14014a09f  lea     r15, [rdi+138h]
0x14014a0a6  mov     eax, [rax+0C8h]
0x14014a0ac  movzx   ecx, byte ptr [rbx+118h]
0x14014a0b3  add     ecx, ecx
0x14014a0b5  xor     ecx, eax
0x14014a0b7  and     ecx, 2
0x14014a0ba  xor     ecx, eax
0x14014a0bc  or      dword ptr [rdi+0C4h], 3
0x14014a0c3  mov     [rdi+0C8h], ecx
0x14014a0c9  mov     rax, [rbx+18h]
0x14014a0cd  mov     [rdi+508h], rax
0x14014a0d4  mov     rax, [rbx+0A8h]
0x14014a0db  mov     [rdi+490h], rax
0x14014a0e2  mov     eax, [rbx+0B0h]
0x14014a0e8  mov     [rdi+498h], eax
0x14014a0ee  lea     rax, [rdi+428h]
0x14014a0f5  mov     [rax+8], rax
0x14014a0f9  mov     [rax], rax
0x14014a0fc  mov     rax, [rbx+10h]
0x14014a100  mov     [rbp+OpenParameters.AdapterName], rax
0x14014a104  lea     rax, [rsi+1E4h]
0x14014a10b  mov     [rbp+OpenParameters.MediumArray], rax
0x14014a10f  mov     eax, [rsi+1E0h]
0x14014a115  mov     [rbp+OpenParameters.MediumArraySize], eax
0x14014a118  lea     rax, [rsi+1FCh]
0x14014a11f  mov     [rbp+OpenParameters.FrameTypeArray], rax
0x14014a123  mov     eax, [rsi+1F8h]
0x14014a129  mov     [rbp+OpenParameters.FrameTypeArraySize], eax
0x14014a12c  mov     dword ptr [rbp+OpenParameters.Header.Type], 380187h
0x14014a133  mov     [rbp+OpenParameters.SelectedMediumIndex], r15
0x14014a137  mov     rcx, [rsi+170h]; NdisProtocolHandle
0x14014a13e  lea     rax, [rdi+500h]
0x14014a145  mov     r9, r14; BindContext
0x14014a148  mov     [rsp+78h+NdisBindingHandle], rax; NdisBindingHandle
0x14014a14d  lea     r8, [rbp+OpenParameters]; OpenParameters
0x14014a151  mov     rdx, rdi; ProtocolBindingContext
0x14014a154  call    cs:__imp_NdisOpenAdapterEx
0x14014a15b  nop     dword ptr [rax+rax+00h]
0x14014a160  mov     ebx, eax
0x14014a162  cmp     eax, 103h
0x14014a167  jnz     short loc_14014A195
0x14014a169  xor     r9d, r9d; Alertable
0x14014a16c  mov     [rsp+78h+NdisBindingHandle], 0; Timeout
0x14014a175  lea     rcx, [rdi+0A8h]; Object
0x14014a17c  xor     r8d, r8d; WaitMode
0x14014a17f  lea     edx, [r9+6]; WaitReason
0x14014a183  call    cs:__imp_KeWaitForSingleObject
0x14014a18a  nop     dword ptr [rax+rax+00h]
0x14014a18f  mov     ebx, [rdi+0C0h]
0x14014a195  test    ebx, ebx
0x14014a197  js      loc_14014A2A7
0x14014a19d  mov     rcx, [rdi+28h]; Lock
0x14014a1a1  lea     rdx, [rbp+LockState]; LockState
0x14014a1a5  xor     eax, eax
0x14014a1a7  xor     r8d, r8d; Flags
0x14014a1aa  mov     word ptr [rbp+LockState.OldIrql], ax
0x14014a1ae  mov     [rbp+LockState.Flags], al
0x14014a1b1  call    cs:__imp_NdisAcquireRWLockWrite
0x14014a1b8  nop     dword ptr [rax+rax+00h]
0x14014a1bd  mov     rcx, [rdi+28h]; Lock
0x14014a1c1  lea     rdx, [rbp+LockState]; LockState
0x14014a1c5  and     dword ptr [rdi+0C4h], 0FFFFFFFEh
0x14014a1cc  call    cs:__imp_NdisReleaseRWLock
0x14014a1d3  nop     dword ptr [rax+rax+00h]
0x14014a1d8  mov     rcx, [rdi+50h]; RunRefCacheAware
0x14014a1dc  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14014a1e3  nop     dword ptr [rax+rax+00h]
0x14014a1e8  mov     eax, [r15]
0x14014a1eb  mov     rdx, rdi
0x14014a1ee  mov     ecx, [rsi+rax*4+1E4h]
0x14014a1f5  mov     [r15], ecx
0x14014a1f8  mov     rcx, [rdi+20h]
0x14014a1fc  add     rcx, 1B8h
0x14014a203  call    FlpInsertInterface
0x14014a208  lea     rax, aFlif; "FLIf"
0x14014a20f  mov     r9, rdi
0x14014a212  lea     rcx, [rdi+440h]
0x14014a219  mov     [rsp+78h+NdisBindingHandle], rax
0x14014a21e  lea     r8, FlpPopulateInterfaceTriageDumpData
0x14014a225  mov     edx, 1
0x14014a22a  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x14014a231  nop     dword ptr [rax+rax+00h]
0x14014a236  mov     rcx, [rdi+28h]; Lock
0x14014a23a  lea     rdx, [rbp+LockState]; LockState
0x14014a23e  xor     r8d, r8d; Flags
0x14014a241  call    cs:__imp_NdisAcquireRWLockWrite
0x14014a248  nop     dword ptr [rax+rax+00h]
0x14014a24d  xor     r8d, r8d
0x14014a250  mov     rcx, rdi
0x14014a253  lea     edx, [r8+1]
0x14014a257  call    FlRdmapNsiInitNotification
0x14014a25c  mov     rcx, [rdi+28h]; Lock
0x14014a260  lea     rdx, [rbp+LockState]; LockState
0x14014a264  mov     bl, al
0x14014a266  call    cs:__imp_NdisReleaseRWLock
0x14014a26d  nop     dword ptr [rax+rax+00h]
0x14014a272  xor     r8d, r8d
0x14014a275  xor     edx, edx
0x14014a277  mov     rcx, rdi
0x14014a27a  call    FlRdmapLogInterfaceEvent
0x14014a27f  test    bl, bl
0x14014a281  jz      short loc_14014A2A3
0x14014a283  mov     rcx, [rdi+60h]; IoWorkItem
0x14014a287  lea     rdx, FlRdmapNSINotificationWorkerRoutine; WorkerRoutine
0x14014a28e  mov     r9, rdi; Context
0x14014a291  mov     r8d, 1; QueueType
0x14014a297  call    cs:__imp_IoQueueWorkItem
0x14014a29e  nop     dword ptr [rax+rax+00h]
0x14014a2a3  xor     ebx, ebx
0x14014a2a5  jmp     short loc_14014A2BC
0x14014a2a7  mov     r8d, ebx
0x14014a2aa  xor     edx, edx
0x14014a2ac  mov     rcx, rdi
0x14014a2af  call    FlRdmapLogInterfaceEvent
0x14014a2b4  mov     rcx, rdi
0x14014a2b7  call    FlpDereferenceInterface
0x14014a2bc  mov     eax, ebx
0x14014a2be  add     rsp, 78h
0x14014a2c2  pop     r15
0x14014a2c4  pop     r14
0x14014a2c6  pop     rdi
0x14014a2c7  pop     rsi
0x14014a2c8  pop     rbx
0x14014a2c9  pop     rbp
0x14014a2ca  retn
```
