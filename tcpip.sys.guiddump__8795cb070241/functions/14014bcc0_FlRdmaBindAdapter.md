# FlRdmaBindAdapter

- ea: `0x14014bcc0`
- end: `0x14014bf4c`
- name: `FlRdmaBindAdapter`
- size: `652`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140103de4`
- `0x1401213d4`
- `0x14012ec90`
- `0x14014abc0`
- `0x14014bcc0`
- `0x1401aff4c`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014be5c`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14014be5c`
- `ntoskrnl!IoQueueWorkItem` at `0x14014bf17`
- `ntoskrnl!IoQueueWorkItem` at `0x14014bf17`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014be03`
- `ntoskrnl!KeWaitForSingleObject` at `0x14014be03`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014beaa`
- `NETIO!NetioRegisterTriageDumpDataCallback` at `0x14014beaa`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014be31`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014bec1`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014be31`
- `NDIS!NdisAcquireRWLockWrite` at `0x14014bec1`
- `NDIS!NdisReleaseRWLock` at `0x14014be4c`
- `NDIS!NdisReleaseRWLock` at `0x14014bee6`
- `NDIS!NdisReleaseRWLock` at `0x14014be4c`
- `NDIS!NdisReleaseRWLock` at `0x14014bee6`
- `NDIS!NdisOpenAdapterEx` at `0x14014bdd4`
- `NDIS!NdisOpenAdapterEx` at `0x14014bdd4`

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
0x14014bcc0  push    rbp
0x14014bcc2  push    rbx
0x14014bcc3  push    rsi
0x14014bcc4  push    rdi
0x14014bcc5  push    r14
0x14014bcc7  push    r15
0x14014bcc9  mov     rbp, rsp
0x14014bccc  sub     rsp, 78h
0x14014bcd0  xorps   xmm0, xmm0
0x14014bcd3  xor     eax, eax
0x14014bcd5  mov     rbx, r8
0x14014bcd8  mov     r14, rdx
0x14014bcdb  mov     rsi, rcx
0x14014bcde  mov     qword ptr [rbp+OpenParameters.FrameTypeArraySize], rax
0x14014bce2  movups  xmmword ptr [rbp+OpenParameters.Header.Type], xmm0
0x14014bce6  movups  xmmword ptr [rbp+OpenParameters.MediumArray], xmm0
0x14014bcea  movups  xmmword ptr [rbp+OpenParameters.SelectedMediumIndex], xmm0
0x14014bcee  cmp     [r8+120h], rax
0x14014bcf5  jnz     short loc_14014BD01
0x14014bcf7  mov     eax, 10001h
0x14014bcfc  jmp     loc_14014BF3E
0x14014bd01  call    FlpCreateInterface
0x14014bd06  mov     rdi, rax
0x14014bd09  test    rax, rax
0x14014bd0c  jnz     short loc_14014BD18
0x14014bd0e  mov     eax, 0C000009Ah
0x14014bd13  jmp     loc_14014BF3E
0x14014bd18  or      dword ptr [rax+0C8h], 1
0x14014bd1f  lea     r15, [rdi+138h]
0x14014bd26  mov     eax, [rax+0C8h]
0x14014bd2c  movzx   ecx, byte ptr [rbx+118h]
0x14014bd33  add     ecx, ecx
0x14014bd35  xor     ecx, eax
0x14014bd37  and     ecx, 2
0x14014bd3a  xor     ecx, eax
0x14014bd3c  or      dword ptr [rdi+0C4h], 3
0x14014bd43  mov     [rdi+0C8h], ecx
0x14014bd49  mov     rax, [rbx+18h]
0x14014bd4d  mov     [rdi+508h], rax
0x14014bd54  mov     rax, [rbx+0A8h]
0x14014bd5b  mov     [rdi+490h], rax
0x14014bd62  mov     eax, [rbx+0B0h]
0x14014bd68  mov     [rdi+498h], eax
0x14014bd6e  lea     rax, [rdi+428h]
0x14014bd75  mov     [rax+8], rax
0x14014bd79  mov     [rax], rax
0x14014bd7c  mov     rax, [rbx+10h]
0x14014bd80  mov     [rbp+OpenParameters.AdapterName], rax
0x14014bd84  lea     rax, [rsi+1E4h]
0x14014bd8b  mov     [rbp+OpenParameters.MediumArray], rax
0x14014bd8f  mov     eax, [rsi+1E0h]
0x14014bd95  mov     [rbp+OpenParameters.MediumArraySize], eax
0x14014bd98  lea     rax, [rsi+1FCh]
0x14014bd9f  mov     [rbp+OpenParameters.FrameTypeArray], rax
0x14014bda3  mov     eax, [rsi+1F8h]
0x14014bda9  mov     [rbp+OpenParameters.FrameTypeArraySize], eax
0x14014bdac  mov     dword ptr [rbp+OpenParameters.Header.Type], 380187h
0x14014bdb3  mov     [rbp+OpenParameters.SelectedMediumIndex], r15
0x14014bdb7  mov     rcx, [rsi+170h]; NdisProtocolHandle
0x14014bdbe  lea     rax, [rdi+500h]
0x14014bdc5  mov     r9, r14; BindContext
0x14014bdc8  mov     [rsp+78h+NdisBindingHandle], rax; NdisBindingHandle
0x14014bdcd  lea     r8, [rbp+OpenParameters]; OpenParameters
0x14014bdd1  mov     rdx, rdi; ProtocolBindingContext
0x14014bdd4  call    cs:__imp_NdisOpenAdapterEx
0x14014bddb  nop     dword ptr [rax+rax+00h]
0x14014bde0  mov     ebx, eax
0x14014bde2  cmp     eax, 103h
0x14014bde7  jnz     short loc_14014BE15
0x14014bde9  xor     r9d, r9d; Alertable
0x14014bdec  mov     [rsp+78h+NdisBindingHandle], 0; Timeout
0x14014bdf5  lea     rcx, [rdi+0A8h]; Object
0x14014bdfc  xor     r8d, r8d; WaitMode
0x14014bdff  lea     edx, [r9+6]; WaitReason
0x14014be03  call    cs:__imp_KeWaitForSingleObject
0x14014be0a  nop     dword ptr [rax+rax+00h]
0x14014be0f  mov     ebx, [rdi+0C0h]
0x14014be15  test    ebx, ebx
0x14014be17  js      loc_14014BF27
0x14014be1d  mov     rcx, [rdi+28h]; Lock
0x14014be21  lea     rdx, [rbp+LockState]; LockState
0x14014be25  xor     eax, eax
0x14014be27  xor     r8d, r8d; Flags
0x14014be2a  mov     word ptr [rbp+LockState.OldIrql], ax
0x14014be2e  mov     [rbp+LockState.Flags], al
0x14014be31  call    cs:__imp_NdisAcquireRWLockWrite
0x14014be38  nop     dword ptr [rax+rax+00h]
0x14014be3d  mov     rcx, [rdi+28h]; Lock
0x14014be41  lea     rdx, [rbp+LockState]; LockState
0x14014be45  and     dword ptr [rdi+0C4h], 0FFFFFFFEh
0x14014be4c  call    cs:__imp_NdisReleaseRWLock
0x14014be53  nop     dword ptr [rax+rax+00h]
0x14014be58  mov     rcx, [rdi+50h]; RunRefCacheAware
0x14014be5c  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14014be63  nop     dword ptr [rax+rax+00h]
0x14014be68  mov     eax, [r15]
0x14014be6b  mov     rdx, rdi
0x14014be6e  mov     ecx, [rsi+rax*4+1E4h]
0x14014be75  mov     [r15], ecx
0x14014be78  mov     rcx, [rdi+20h]
0x14014be7c  add     rcx, 1B8h
0x14014be83  call    FlpInsertInterface
0x14014be88  lea     rax, aFlif; "FLIf"
0x14014be8f  mov     r9, rdi
0x14014be92  lea     rcx, [rdi+440h]
0x14014be99  mov     [rsp+78h+NdisBindingHandle], rax
0x14014be9e  lea     r8, FlpPopulateInterfaceTriageDumpData
0x14014bea5  mov     edx, 1
0x14014beaa  call    cs:__imp_NetioRegisterTriageDumpDataCallback
0x14014beb1  nop     dword ptr [rax+rax+00h]
0x14014beb6  mov     rcx, [rdi+28h]; Lock
0x14014beba  lea     rdx, [rbp+LockState]; LockState
0x14014bebe  xor     r8d, r8d; Flags
0x14014bec1  call    cs:__imp_NdisAcquireRWLockWrite
0x14014bec8  nop     dword ptr [rax+rax+00h]
0x14014becd  xor     r8d, r8d
0x14014bed0  mov     rcx, rdi
0x14014bed3  lea     edx, [r8+1]
0x14014bed7  call    FlRdmapNsiInitNotification
0x14014bedc  mov     rcx, [rdi+28h]; Lock
0x14014bee0  lea     rdx, [rbp+LockState]; LockState
0x14014bee4  mov     bl, al
0x14014bee6  call    cs:__imp_NdisReleaseRWLock
0x14014beed  nop     dword ptr [rax+rax+00h]
0x14014bef2  xor     r8d, r8d
0x14014bef5  xor     edx, edx
0x14014bef7  mov     rcx, rdi
0x14014befa  call    FlRdmapLogInterfaceEvent
0x14014beff  test    bl, bl
0x14014bf01  jz      short loc_14014BF23
0x14014bf03  mov     rcx, [rdi+60h]; IoWorkItem
0x14014bf07  lea     rdx, FlRdmapNSINotificationWorkerRoutine; WorkerRoutine
0x14014bf0e  mov     r9, rdi; Context
0x14014bf11  mov     r8d, 1; QueueType
0x14014bf17  call    cs:__imp_IoQueueWorkItem
0x14014bf1e  nop     dword ptr [rax+rax+00h]
0x14014bf23  xor     ebx, ebx
0x14014bf25  jmp     short loc_14014BF3C
0x14014bf27  mov     r8d, ebx
0x14014bf2a  xor     edx, edx
0x14014bf2c  mov     rcx, rdi
0x14014bf2f  call    FlRdmapLogInterfaceEvent
0x14014bf34  mov     rcx, rdi
0x14014bf37  call    FlpDereferenceInterface
0x14014bf3c  mov     eax, ebx
0x14014bf3e  add     rsp, 78h
0x14014bf42  pop     r15
0x14014bf44  pop     r14
0x14014bf46  pop     rdi
0x14014bf47  pop     rsi
0x14014bf48  pop     rbx
0x14014bf49  pop     rbp
0x14014bf4a  retn
```
