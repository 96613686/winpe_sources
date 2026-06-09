# FlRdmaBindAdapter

- ea: `0x140149eb0`
- end: `0x14014a13c`
- name: `FlRdmaBindAdapter`
- size: `652`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400c54b0`
- `0x140116b54`
- `0x140124e20`
- `0x140148940`
- `0x140149eb0`
- `0x1401ae24c`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014a04c`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014a04c`
- `ntoskrnl!IoQueueWorkItem` at `0x14014a107`
- `ntoskrnl!IoQueueWorkItem` at `0x14014a107`
- `ntoskrnl!KeWaitForSingleObject` at `0x140149ff3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140149ff3`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014a09a`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014a09a`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014a021`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014a0b1`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014a021`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014a0b1`
- `NDIS!NdisReleaseRWLock` at `0x14014a03c`
- `NDIS!NdisReleaseRWLock` at `0x14014a0d6`
- `NDIS!NdisReleaseRWLock` at `0x14014a03c`
- `NDIS!NdisReleaseRWLock` at `0x14014a0d6`
- `NDIS!NdisOpenAdapterEx` at `0x140149fc4`
- `NDIS!NdisOpenAdapterEx` at `0x140149fc4`

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
0x140149eb0  push    rbp
0x140149eb2  push    rbx
0x140149eb3  push    rsi
0x140149eb4  push    rdi
0x140149eb5  push    r14
0x140149eb7  push    r15
0x140149eb9  mov     rbp, rsp
0x140149ebc  sub     rsp, 78h
0x140149ec0  xorps   xmm0, xmm0
0x140149ec3  xor     eax, eax
0x140149ec5  mov     rbx, r8
0x140149ec8  mov     r14, rdx
0x140149ecb  mov     rsi, rcx
0x140149ece  mov     qword ptr [rbp+OpenParameters.FrameTypeArraySize], rax
0x140149ed2  movups  xmmword ptr [rbp+OpenParameters.Header.Type], xmm0
0x140149ed6  movups  xmmword ptr [rbp+OpenParameters.MediumArray], xmm0
0x140149eda  movups  xmmword ptr [rbp+OpenParameters.SelectedMediumIndex], xmm0
0x140149ede  cmp     [r8+120h], rax
0x140149ee5  jnz     short loc_140149EF1
0x140149ee7  mov     eax, 10001h
0x140149eec  jmp     loc_14014A12E
0x140149ef1  call    FlpCreateInterface
0x140149ef6  mov     rdi, rax
0x140149ef9  test    rax, rax
0x140149efc  jnz     short loc_140149F08
0x140149efe  mov     eax, 0C000009Ah
0x140149f03  jmp     loc_14014A12E
0x140149f08  or      dword ptr [rax+0C8h], 1
0x140149f0f  lea     r15, [rdi+138h]
0x140149f16  mov     eax, [rax+0C8h]
0x140149f1c  movzx   ecx, byte ptr [rbx+118h]
0x140149f23  add     ecx, ecx
0x140149f25  xor     ecx, eax
0x140149f27  and     ecx, 2
0x140149f2a  xor     ecx, eax
0x140149f2c  or      dword ptr [rdi+0C4h], 3
0x140149f33  mov     [rdi+0C8h], ecx
0x140149f39  mov     rax, [rbx+18h]
0x140149f3d  mov     [rdi+508h], rax
0x140149f44  mov     rax, [rbx+0A8h]
0x140149f4b  mov     [rdi+490h], rax
0x140149f52  mov     eax, [rbx+0B0h]
0x140149f58  mov     [rdi+498h], eax
0x140149f5e  lea     rax, [rdi+428h]
0x140149f65  mov     [rax+8], rax
0x140149f69  mov     [rax], rax
0x140149f6c  mov     rax, [rbx+10h]
0x140149f70  mov     [rbp+OpenParameters.AdapterName], rax
0x140149f74  lea     rax, [rsi+1E4h]
0x140149f7b  mov     [rbp+OpenParameters.MediumArray], rax
0x140149f7f  mov     eax, [rsi+1E0h]
0x140149f85  mov     [rbp+OpenParameters.MediumArraySize], eax
0x140149f88  lea     rax, [rsi+1FCh]
0x140149f8f  mov     [rbp+OpenParameters.FrameTypeArray], rax
0x140149f93  mov     eax, [rsi+1F8h]
0x140149f99  mov     [rbp+OpenParameters.FrameTypeArraySize], eax
0x140149f9c  mov     dword ptr [rbp+OpenParameters.Header.Type], 380187h
0x140149fa3  mov     [rbp+OpenParameters.SelectedMediumIndex], r15
0x140149fa7  mov     rcx, [rsi+170h]; NdisProtocolHandle
0x140149fae  lea     rax, [rdi+500h]
0x140149fb5  mov     r9, r14; BindContext
0x140149fb8  mov     [rsp+78h+NdisBindingHandle], rax; NdisBindingHandle
0x140149fbd  lea     r8, [rbp+OpenParameters]; OpenParameters
0x140149fc1  mov     rdx, rdi; ProtocolBindingContext
0x140149fc4  call    cs:__imp_NdisOpenAdapterEx
0x140149fcb  nop     dword ptr [rax+rax+00h]
0x140149fd0  mov     ebx, eax
0x140149fd2  cmp     eax, 103h
0x140149fd7  jnz     short loc_14014A005
0x140149fd9  xor     r9d, r9d; Alertable
0x140149fdc  mov     [rsp+78h+NdisBindingHandle], 0; Timeout
0x140149fe5  lea     rcx, [rdi+0A8h]; Object
0x140149fec  xor     r8d, r8d; WaitMode
0x140149fef  lea     edx, [r9+6]; WaitReason
0x140149ff3  call    cs:__imp_KeWaitForSingleObject
0x140149ffa  nop     dword ptr [rax+rax+00h]
0x140149fff  mov     ebx, [rdi+0C0h]
0x14014a005  test    ebx, ebx
0x14014a007  js      loc_14014A117
0x14014a00d  mov     rcx, [rdi+28h]; Lock
0x14014a011  lea     rdx, [rbp+LockState]; LockState
0x14014a015  xor     eax, eax
0x14014a017  xor     r8d, r8d; Flags
0x14014a01a  mov     word ptr [rbp+LockState.OldIrql], ax
0x14014a01e  mov     [rbp+LockState.Flags], al
0x14014a021  call    cs:__imp_NdisAcquireRWLockWrite
0x14014a028  nop     dword ptr [rax+rax+00h]
0x14014a02d  mov     rcx, [rdi+28h]; Lock
0x14014a031  lea     rdx, [rbp+LockState]; LockState
0x14014a035  and     dword ptr [rdi+0C4h], 0FFFFFFFEh
0x14014a03c  call    cs:__imp_NdisReleaseRWLock
0x14014a043  nop     dword ptr [rax+rax+00h]
0x14014a048  mov     rcx, [rdi+50h]; RunRefCacheAware
0x14014a04c  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14014a053  nop     dword ptr [rax+rax+00h]
0x14014a058  mov     eax, [r15]
0x14014a05b  mov     rdx, rdi
0x14014a05e  mov     ecx, [rsi+rax*4+1E4h]
0x14014a065  mov     [r15], ecx
0x14014a068  mov     rcx, [rdi+20h]
0x14014a06c  add     rcx, 1B8h
0x14014a073  call    FlpInsertInterface
0x14014a078  lea     rax, aFlif; "FLIf"
0x14014a07f  mov     r9, rdi
0x14014a082  lea     rcx, [rdi+440h]
0x14014a089  mov     [rsp+78h+NdisBindingHandle], rax
0x14014a08e  lea     r8, FlpPopulateInterfaceTriageDumpData
0x14014a095  mov     edx, 1
0x14014a09a  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x14014a0a1  nop     dword ptr [rax+rax+00h]
0x14014a0a6  mov     rcx, [rdi+28h]; Lock
0x14014a0aa  lea     rdx, [rbp+LockState]; LockState
0x14014a0ae  xor     r8d, r8d; Flags
0x14014a0b1  call    cs:__imp_NdisAcquireRWLockWrite
0x14014a0b8  nop     dword ptr [rax+rax+00h]
0x14014a0bd  xor     r8d, r8d
0x14014a0c0  mov     rcx, rdi
0x14014a0c3  lea     edx, [r8+1]
0x14014a0c7  call    FlRdmapNsiInitNotification
0x14014a0cc  mov     rcx, [rdi+28h]; Lock
0x14014a0d0  lea     rdx, [rbp+LockState]; LockState
0x14014a0d4  mov     bl, al
0x14014a0d6  call    cs:__imp_NdisReleaseRWLock
0x14014a0dd  nop     dword ptr [rax+rax+00h]
0x14014a0e2  xor     r8d, r8d
0x14014a0e5  xor     edx, edx
0x14014a0e7  mov     rcx, rdi
0x14014a0ea  call    FlRdmapLogInterfaceEvent
0x14014a0ef  test    bl, bl
0x14014a0f1  jz      short loc_14014A113
0x14014a0f3  mov     rcx, [rdi+60h]; IoWorkItem
0x14014a0f7  lea     rdx, FlRdmapNSINotificationWorkerRoutine; WorkerRoutine
0x14014a0fe  mov     r9, rdi; Context
0x14014a101  mov     r8d, 1; QueueType
0x14014a107  call    cs:__imp_IoQueueWorkItem
0x14014a10e  nop     dword ptr [rax+rax+00h]
0x14014a113  xor     ebx, ebx
0x14014a115  jmp     short loc_14014A12C
0x14014a117  mov     r8d, ebx
0x14014a11a  xor     edx, edx
0x14014a11c  mov     rcx, rdi
0x14014a11f  call    FlRdmapLogInterfaceEvent
0x14014a124  mov     rcx, rdi
0x14014a127  call    FlpDereferenceInterface
0x14014a12c  mov     eax, ebx
0x14014a12e  add     rsp, 78h
0x14014a132  pop     r15
0x14014a134  pop     r14
0x14014a136  pop     rdi
0x14014a137  pop     rsi
0x14014a138  pop     rbx
0x14014a139  pop     rbp
0x14014a13a  retn
```
