# IppInspectInjectReceiveEx

- ea: `0x14004bb20`
- end: `0x14004c085`
- name: `IppInspectInjectReceiveEx`
- size: `1381`
- prototype: `void __fastcall(int, int, int, unsigned int, __int64, char, int, unsigned __int8, char)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14016dd08`
- `0x140195250`
- `0x140199f80`
- `0x140266488`

## callees

- `0x14003eac0`
- `0x14004bb20`
- `0x14004c0b0`
- `0x14004d040`
- `0x140073660`
- `0x140154d30`
- `0x14018d8cc`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14004bbcd`
- `ntoskrnl!KfRaiseIrql` at `0x14004bc9f`
- `ntoskrnl!KfRaiseIrql` at `0x14004bd67`
- `ntoskrnl!KfRaiseIrql` at `0x14004bbcd`
- `ntoskrnl!KfRaiseIrql` at `0x14004bc9f`
- `ntoskrnl!KfRaiseIrql` at `0x14004bd67`
- `ntoskrnl!KeLowerIrql` at `0x14004bc81`
- `ntoskrnl!KeLowerIrql` at `0x14004bd49`
- `ntoskrnl!KeLowerIrql` at `0x14004be49`
- `ntoskrnl!KeLowerIrql` at `0x14004befa`
- `ntoskrnl!KeLowerIrql` at `0x14004bf90`
- `ntoskrnl!KeLowerIrql` at `0x14004c023`
- `ntoskrnl!KeLowerIrql` at `0x14004bc81`
- `ntoskrnl!KeLowerIrql` at `0x14004bd49`
- `ntoskrnl!KeLowerIrql` at `0x14004be49`
- `ntoskrnl!KeLowerIrql` at `0x14004befa`
- `ntoskrnl!KeLowerIrql` at `0x14004bf90`
- `ntoskrnl!KeLowerIrql` at `0x14004c023`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004bfeb`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004bfeb`
- `ntoskrnl!IoQueueWorkItem` at `0x14004bee4`
- `ntoskrnl!IoQueueWorkItem` at `0x14004bf77`
- `ntoskrnl!IoQueueWorkItem` at `0x14004bee4`
- `ntoskrnl!IoQueueWorkItem` at `0x14004bf77`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004be72`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004be72`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004bc0f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004bce0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004bda9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004bc0f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004bce0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14004bda9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004bc24`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004bcf5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004bdbe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004bc24`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004bcf5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004bdbe`
- `ntoskrnl!KeTestSpinLock` at `0x14004bbf3`
- `ntoskrnl!KeTestSpinLock` at `0x14004bcc4`
- `ntoskrnl!KeTestSpinLock` at `0x14004bd8d`
- `ntoskrnl!KeTestSpinLock` at `0x14004bbf3`
- `ntoskrnl!KeTestSpinLock` at `0x14004bcc4`
- `ntoskrnl!KeTestSpinLock` at `0x14004bd8d`
- `NETIO!NetioDereferenceNetBufferList` at `0x14004c074`
- `NETIO!NetioDereferenceNetBufferList` at `0x14004c074`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14004bbb6`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14004bbb6`

## pseudocode

```c
void __fastcall IppInspectInjectReceiveEx(
        int a1,
        int a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        char a6,
        int a7,
        unsigned __int8 a8,
        char a9)
{
  __int64 v9; // r14
  __int64 *v10; // rdi
  int ThreadObjectCompartmentId; // esi
  __int64 v14; // rbp
  __int64 v15; // rcx
  unsigned int v16; // ebx
  _BYTE *v17; // rax
  KIRQL v18; // r12
  _QWORD **v19; // rdx
  _QWORD *i; // rax
  _QWORD *v21; // rbp
  KIRQL v22; // si
  _QWORD *v23; // rax
  _QWORD *v24; // rbx
  KIRQL v25; // r15
  _QWORD *v26; // rdi
  __int64 SubInterfaceOnInterfaceByIndexUnderLock; // rdi
  signed __int64 v28; // rax
  bool v29; // cc
  signed __int64 v30; // rax
  signed __int64 v31; // rsi
  signed __int64 v32; // rsi
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-68h] BYREF

  v9 = a5;
  v10 = (__int64 *)&Ipv4Global;
  if ( a1 )
    v10 = &Ipv6Global;
  ThreadObjectCompartmentId = a2;
  if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 1) != 0 )
    McTemplateK0pqqqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)IP_INJECT_NBL_RECEIVE,
      (unsigned int)MICROSOFT_TCPIP_PROVIDER,
      a5,
      *((_WORD *)v10 + 14),
      a2,
      a3,
      0);
  v14 = *(_QWORD *)(a5 + 8);
  v15 = *(_QWORD *)(v14 + 8);
  v16 = *(_DWORD *)(v15 + 40) - *(_DWORD *)(v14 + 16);
  if ( v16 < *((unsigned __int16 *)v10 + 20)
    || ((*(_BYTE *)(v15 + 10) & 5) == 0
      ? (v17 = MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000000u))
      : (v17 = *(_BYTE **)(v15 + 24)),
        v10 == (__int64 *)&Ipv4Global && v16 < (unsigned __int8)(4 * (v17[*(unsigned int *)(v14 + 16)] & 0xF))) )
  {
    *(_DWORD *)(a5 + 140) = -1073741285;
    goto LABEL_46;
  }
  if ( !ThreadObjectCompartmentId )
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v18 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)v10 + 4972);
  if ( !KeTestSpinLock((PKSPIN_LOCK)v10 + 2485) )
  {
    _InterlockedDecrement((volatile signed __int32 *)v10 + 4972);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v10 + 2485, &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)v10 + 4972);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v19 = (_QWORD **)(v10[2484] + 16LL * (ThreadObjectCompartmentId & (unsigned int)(*((_DWORD *)v10 + 4967) - 1)));
  for ( i = *v19; ; i = (_QWORD *)*i )
  {
    if ( i == v19 )
    {
      _InterlockedDecrement((volatile signed __int32 *)v10 + 4972);
      KeLowerIrql(v18);
LABEL_54:
      *(_DWORD *)(a5 + 140) = -1073741275;
      goto LABEL_46;
    }
    v21 = i - 6;
    if ( *((_DWORD *)i - 12) == ThreadObjectCompartmentId )
      break;
  }
  if ( _InterlockedIncrement64(v21 + 4) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)v10 + 4972);
  KeLowerIrql(v18);
  if ( !v21 )
    goto LABEL_54;
  v22 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)v21 + 40);
  if ( !KeTestSpinLock(v21 + 19) )
  {
    _InterlockedDecrement((volatile signed __int32 *)v21 + 40);
    KeAcquireInStackQueuedSpinLockAtDpcLevel(v21 + 19, &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)v21 + 40);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v23 = (_QWORD *)v21[21];
  while ( 2 )
  {
    if ( v23 == v21 + 21 )
    {
      _InterlockedDecrement((volatile signed __int32 *)v21 + 40);
      KeLowerIrql(v22);
      goto LABEL_50;
    }
    v24 = v23 - 22;
    if ( *((_DWORD *)v23 - 42) != a3 )
    {
      v23 = (_QWORD *)*v23;
      continue;
    }
    break;
  }
  if ( _InterlockedIncrement64(v24 + 19) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)v21 + 40);
  KeLowerIrql(v22);
  if ( !v24 )
  {
LABEL_50:
    *(_DWORD *)(a5 + 140) = -1073741811;
    goto LABEL_43;
  }
  v25 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)v24 + 76);
  if ( !KeTestSpinLock(v24 + 37) )
  {
    _InterlockedDecrement((volatile signed __int32 *)v24 + 76);
    KeAcquireInStackQueuedSpinLockAtDpcLevel(v24 + 37, &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)v24 + 76);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  if ( a4 )
  {
    SubInterfaceOnInterfaceByIndexUnderLock = IppFindSubInterfaceOnInterfaceByIndexUnderLock(v24, a4);
  }
  else
  {
    v26 = (_QWORD *)v24[44];
    if ( v26 == v24 + 44 || (SubInterfaceOnInterfaceByIndexUnderLock = (__int64)(v26 - 9)) == 0 )
    {
      SubInterfaceOnInterfaceByIndexUnderLock = 0;
    }
    else if ( _InterlockedIncrement64((volatile signed __int64 *)(SubInterfaceOnInterfaceByIndexUnderLock + 64)) <= 1 )
    {
      __fastfail(0xEu);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)v24 + 76);
  if ( SubInterfaceOnInterfaceByIndexUnderLock )
  {
    *(_DWORD *)(a5 + 136) |= 0x1000000u;
    if ( !a6 || (int)IppBatchRecvPacket(a5, SubInterfaceOnInterfaceByIndexUnderLock, 0, a8, a9) < 0 )
      IppReceivePackets(SubInterfaceOnInterfaceByIndexUnderLock, (_QWORD *)a5, 1, 0);
    v9 = 0;
    KeLowerIrql(v25);
    v28 = _InterlockedExchangeAdd64(
            (volatile signed __int64 *)(SubInterfaceOnInterfaceByIndexUnderLock + 64),
            0xFFFFFFFFFFFFFFFFuLL);
    v29 = v28 <= 1;
    v30 = v28 - 1;
    if ( v29 )
    {
      if ( v30 )
        __fastfail(0xEu);
      if ( KeGetCurrentIrql() )
        IoQueueWorkItem(
          *(PIO_WORKITEM *)(SubInterfaceOnInterfaceByIndexUnderLock + 56),
          IppCleanupSubInterfaceWorkerRoutine,
          DelayedWorkQueue,
          (PVOID)SubInterfaceOnInterfaceByIndexUnderLock);
      else
        IppCleanupSubInterfaceWorkerRoutine(IppDeviceObject, (PVOID)SubInterfaceOnInterfaceByIndexUnderLock);
    }
  }
  else
  {
    KeLowerIrql(v25);
    *(_DWORD *)(a5 + 140) = -1073741252;
  }
  IppDereferenceInterface(v24);
LABEL_43:
  v31 = _InterlockedExchangeAdd64(v21 + 4, 0xFFFFFFFFFFFFFFFFuLL);
  v29 = v31 <= 1;
  v32 = v31 - 1;
  if ( v29 )
  {
    if ( v32 )
      __fastfail(0xEu);
    IoQueueWorkItem((PIO_WORKITEM)v21[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v21);
  }
LABEL_46:
  if ( v9 )
    NetioDereferenceNetBufferList(v9, 0);
}

```

## disassembly

```asm
0x14004bb20  push    rbx
0x14004bb22  push    rbp
0x14004bb23  push    rsi
0x14004bb24  push    rdi
0x14004bb25  push    r12
0x14004bb27  push    r13
0x14004bb29  push    r14
0x14004bb2b  push    r15
0x14004bb2d  sub     rsp, 68h
0x14004bb31  mov     r14, [rsp+0A8h+arg_20]
0x14004bb39  lea     r12, Ipv4Global
0x14004bb40  test    ecx, ecx
0x14004bb42  lea     rax, Ipv6Global
0x14004bb49  mov     rdi, r12
0x14004bb4c  mov     r13d, r9d
0x14004bb4f  cmovnz  rdi, rax
0x14004bb53  mov     r15d, r8d
0x14004bb56  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 1
0x14004bb5d  mov     esi, edx
0x14004bb5f  jnz     loc_14004BF25
0x14004bb65  mov     rbp, [r14+8]
0x14004bb69  movzx   eax, word ptr [rdi+28h]
0x14004bb6d  mov     rcx, [rbp+8]; MemoryDescriptorList
0x14004bb71  mov     ebx, [rcx+28h]
0x14004bb74  sub     ebx, [rbp+10h]
0x14004bb77  cmp     ebx, eax
0x14004bb79  jb      loc_14004BFFC
0x14004bb7f  test    byte ptr [rcx+0Ah], 5
0x14004bb83  jz      loc_14004BFD0
0x14004bb89  mov     rax, [rcx+18h]
0x14004bb8d  cmp     rdi, r12
0x14004bb90  jnz     short loc_14004BBA9
0x14004bb92  mov     ecx, [rbp+10h]
0x14004bb95  movzx   eax, byte ptr [rcx+rax]
0x14004bb99  and     al, 0Fh
0x14004bb9b  shl     al, 2
0x14004bb9e  movzx   eax, al
0x14004bba1  cmp     ebx, eax
0x14004bba3  jb      loc_14004BFFC
0x14004bba9  test    esi, esi
0x14004bbab  jnz     short loc_14004BBC4
0x14004bbad  mov     rcx, gs:188h
0x14004bbb6  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14004bbbd  nop     dword ptr [rax+rax+00h]
0x14004bbc2  mov     esi, eax
0x14004bbc4  mov     cl, 2; NewIrql
0x14004bbc6  lea     rbx, [rdi+4DA8h]
0x14004bbcd  call    cs:__imp_KfRaiseIrql
0x14004bbd4  nop     dword ptr [rax+rax+00h]
0x14004bbd9  movzx   r12d, al
0x14004bbdd  xorps   xmm0, xmm0
0x14004bbe0  xor     eax, eax
0x14004bbe2  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14004bbe7  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14004bbec  lock inc dword ptr [rbx+8]
0x14004bbf0  mov     rcx, rbx; SpinLock
0x14004bbf3  call    cs:__imp_KeTestSpinLock
0x14004bbfa  nop     dword ptr [rax+rax+00h]
0x14004bbff  test    al, al
0x14004bc01  jnz     short loc_14004BC30
0x14004bc03  lock dec dword ptr [rbx+8]
0x14004bc07  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14004bc0c  mov     rcx, rbx; SpinLock
0x14004bc0f  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14004bc16  nop     dword ptr [rax+rax+00h]
0x14004bc1b  lock inc dword ptr [rbx+8]
0x14004bc1f  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14004bc24  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14004bc2b  nop     dword ptr [rax+rax+00h]
0x14004bc30  mov     edx, [rdi+4D9Ch]
0x14004bc36  dec     edx
0x14004bc38  mov     eax, esi
0x14004bc3a  and     rdx, rax
0x14004bc3d  shl     rdx, 4
0x14004bc41  add     rdx, [rdi+4DA0h]
0x14004bc48  mov     rax, [rdx]
0x14004bc4b  cmp     rax, rdx
0x14004bc4e  jz      loc_14004BF88
0x14004bc54  cmp     [rax-30h], esi
0x14004bc57  lea     rbp, [rax-30h]
0x14004bc5b  jnz     loc_14004BF1D
0x14004bc61  mov     eax, 1
0x14004bc66  lock xadd [rbp+20h], rax
0x14004bc6c  inc     rax
0x14004bc6f  cmp     rax, 1
0x14004bc73  jle     loc_14004BFAC
0x14004bc79  lock dec dword ptr [rbx+8]
0x14004bc7d  movzx   ecx, r12b; NewIrql
0x14004bc81  call    cs:__imp_KeLowerIrql
0x14004bc88  nop     dword ptr [rax+rax+00h]
0x14004bc8d  test    rbp, rbp
0x14004bc90  jz      loc_14004BF9C
0x14004bc96  mov     cl, 2; NewIrql
0x14004bc98  lea     rdi, [rbp+98h]
0x14004bc9f  call    cs:__imp_KfRaiseIrql
0x14004bca6  nop     dword ptr [rax+rax+00h]
0x14004bcab  movzx   esi, al
0x14004bcae  xorps   xmm0, xmm0
0x14004bcb1  xor     eax, eax
0x14004bcb3  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14004bcb8  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14004bcbd  lock inc dword ptr [rdi+8]
0x14004bcc1  mov     rcx, rdi; SpinLock
0x14004bcc4  call    cs:__imp_KeTestSpinLock
0x14004bccb  nop     dword ptr [rax+rax+00h]
0x14004bcd0  test    al, al
0x14004bcd2  jnz     short loc_14004BD01
0x14004bcd4  lock dec dword ptr [rdi+8]
0x14004bcd8  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14004bcdd  mov     rcx, rdi; SpinLock
0x14004bce0  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14004bce7  nop     dword ptr [rax+rax+00h]
0x14004bcec  lock inc dword ptr [rdi+8]
0x14004bcf0  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14004bcf5  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14004bcfc  nop     dword ptr [rax+rax+00h]
0x14004bd01  lea     rcx, [rbp+0A8h]
0x14004bd08  mov     rax, [rcx]
0x14004bd0b  cmp     rax, rcx
0x14004bd0e  jz      loc_14004BEF2
0x14004bd14  lea     rbx, [rax-0B0h]
0x14004bd1b  cmp     [rbx+8], r15d
0x14004bd1f  jz      short loc_14004BD26
0x14004bd21  mov     rax, [rax]
0x14004bd24  jmp     short loc_14004BD0B
0x14004bd26  mov     eax, 1
0x14004bd2b  lock xadd [rbx+98h], rax
0x14004bd34  inc     rax
0x14004bd37  cmp     rax, 1
0x14004bd3b  jle     loc_14004BFB8
0x14004bd41  lock dec dword ptr [rdi+8]
0x14004bd45  movzx   ecx, sil; NewIrql
0x14004bd49  call    cs:__imp_KeLowerIrql
0x14004bd50  nop     dword ptr [rax+rax+00h]
0x14004bd55  test    rbx, rbx
0x14004bd58  jz      loc_14004BF06
0x14004bd5e  mov     cl, 2; NewIrql
0x14004bd60  lea     rsi, [rbx+128h]
0x14004bd67  call    cs:__imp_KfRaiseIrql
0x14004bd6e  nop     dword ptr [rax+rax+00h]
0x14004bd73  movzx   r15d, al
0x14004bd77  xorps   xmm0, xmm0
0x14004bd7a  xor     eax, eax
0x14004bd7c  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14004bd81  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x14004bd86  lock inc dword ptr [rsi+8]
0x14004bd8a  mov     rcx, rsi; SpinLock
0x14004bd8d  call    cs:__imp_KeTestSpinLock
0x14004bd94  nop     dword ptr [rax+rax+00h]
0x14004bd99  test    al, al
0x14004bd9b  jnz     short loc_14004BDCA
0x14004bd9d  lock dec dword ptr [rsi+8]
0x14004bda1  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x14004bda6  mov     rcx, rsi; SpinLock
0x14004bda9  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14004bdb0  nop     dword ptr [rax+rax+00h]
0x14004bdb5  lock inc dword ptr [rsi+8]
0x14004bdb9  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14004bdbe  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14004bdc5  nop     dword ptr [rax+rax+00h]
0x14004bdca  test    r13d, r13d
0x14004bdcd  jnz     loc_14004C00C
0x14004bdd3  lea     rax, [rbx+160h]
0x14004bdda  mov     rdi, [rax]
0x14004bddd  cmp     rdi, rax
0x14004bde0  jnz     short loc_14004BDE6
0x14004bde2  xor     edi, edi
0x14004bde4  jmp     short loc_14004BE04
0x14004bde6  add     rdi, 0FFFFFFFFFFFFFFB8h
0x14004bdea  jz      short loc_14004BDE2
0x14004bdec  mov     eax, 1
0x14004bdf1  lock xadd [rdi+40h], rax
0x14004bdf7  inc     rax
0x14004bdfa  cmp     rax, 1
0x14004bdfe  jle     loc_14004BFC4
0x14004be04  lock dec dword ptr [rsi+8]
0x14004be08  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x14004be0f  test    rdi, rdi
0x14004be12  jz      loc_14004C01F
0x14004be18  or      dword ptr [r14+88h], 1000000h
0x14004be23  cmp     [rsp+0A8h+arg_28], 0
0x14004be2b  jnz     loc_14004C03F
0x14004be31  xor     r9d, r9d
0x14004be34  mov     r8b, 1
0x14004be37  mov     rdx, r14
0x14004be3a  mov     rcx, rdi
0x14004be3d  call    IppReceivePackets
0x14004be42  xor     r14d, r14d
0x14004be45  movzx   ecx, r15b; NewIrql
0x14004be49  call    cs:__imp_KeLowerIrql
0x14004be50  nop     dword ptr [rax+rax+00h]
0x14004be55  mov     rax, rsi
0x14004be58  lock xadd [rdi+40h], rax
0x14004be5e  sub     rax, 1
0x14004be62  jg      short loc_14004BE91
0x14004be64  test    rax, rax
0x14004be67  jz      short loc_14004BE72
0x14004be69  mov     ecx, 0Eh
0x14004be6e  int     29h; Win8: RtlFailFast(ecx)
0x14004be70  jmp     short loc_14004BE91
0x14004be72  call    cs:__imp_KeGetCurrentIrql
0x14004be79  nop     dword ptr [rax+rax+00h]
0x14004be7e  test    al, al
0x14004be80  jnz     short loc_14004BED0
0x14004be82  mov     rcx, cs:IppDeviceObject; DeviceObject
0x14004be89  mov     rdx, rdi; Context
0x14004be8c  call    IppCleanupSubInterfaceWorkerRoutine
0x14004be91  mov     rcx, rbx; Context
0x14004be94  call    IppDereferenceInterface
0x14004be99  lock xadd [rbp+20h], rsi
0x14004be9f  sub     rsi, 1
0x14004bea3  jg      short loc_14004BEB5
0x14004bea5  test    rsi, rsi
0x14004bea8  jz      loc_14004BF60
0x14004beae  mov     ecx, 0Eh
0x14004beb3  int     29h; Win8: RtlFailFast(ecx)
0x14004beb5  test    r14, r14
0x14004beb8  jnz     loc_14004C06F
0x14004bebe  add     rsp, 68h
0x14004bec2  pop     r15
0x14004bec4  pop     r14
0x14004bec6  pop     r13
0x14004bec8  pop     r12
0x14004beca  pop     rdi
0x14004becb  pop     rsi
0x14004becc  pop     rbp
0x14004becd  pop     rbx
0x14004bece  retn
0x14004bed0  mov     rcx, [rdi+38h]; IoWorkItem
0x14004bed4  lea     rdx, IppCleanupSubInterfaceWorkerRoutine; WorkerRoutine
0x14004bedb  mov     r9, rdi; Context
0x14004bede  mov     r8d, 1; QueueType
0x14004bee4  call    cs:__imp_IoQueueWorkItem
0x14004beeb  nop     dword ptr [rax+rax+00h]
0x14004bef0  jmp     short loc_14004BE91
0x14004bef2  lock dec dword ptr [rdi+8]
0x14004bef6  movzx   ecx, sil; NewIrql
0x14004befa  call    cs:__imp_KeLowerIrql
0x14004bf01  nop     dword ptr [rax+rax+00h]
0x14004bf06  mov     dword ptr [r14+8Ch], 0C000000Dh
0x14004bf11  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x14004bf18  jmp     loc_14004BE99
0x14004bf1d  mov     rax, [rax]
0x14004bf20  jmp     loc_14004BC4B
0x14004bf25  movzx   eax, word ptr [rdi+1Ch]
0x14004bf29  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x14004bf30  mov     [rsp+0A8h+var_70], 0
0x14004bf38  lea     rdx, IP_INJECT_NBL_RECEIVE
0x14004bf3f  mov     [rsp+0A8h+var_78], r15d
0x14004bf44  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14004bf4b  mov     [rsp+0A8h+Priority], esi
0x14004bf4f  mov     r9, r14
0x14004bf52  mov     [rsp+0A8h+BugCheckOnFailure], eax
0x14004bf56  call    McTemplateK0pqqqq_EtwWriteTransfer
0x14004bf5b  jmp     loc_14004BB65
0x14004bf60  mov     rcx, [rbp+80h]; IoWorkItem
0x14004bf67  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x14004bf6e  mov     r9, rbp; Context
0x14004bf71  mov     r8d, 1; QueueType
0x14004bf77  call    cs:__imp_IoQueueWorkItem
0x14004bf7e  nop     dword ptr [rax+rax+00h]
0x14004bf83  jmp     loc_14004BEB5
0x14004bf88  lock dec dword ptr [rbx+8]
0x14004bf8c  movzx   ecx, r12b; NewIrql
0x14004bf90  call    cs:__imp_KeLowerIrql
0x14004bf97  nop     dword ptr [rax+rax+00h]
0x14004bf9c  mov     dword ptr [r14+8Ch], 0C0000225h
0x14004bfa7  jmp     loc_14004BEB5
0x14004bfac  mov     ecx, 0Eh
0x14004bfb1  int     29h; Win8: RtlFailFast(ecx)
0x14004bfb3  jmp     loc_14004BC79
0x14004bfb8  mov     ecx, 0Eh
0x14004bfbd  int     29h; Win8: RtlFailFast(ecx)
0x14004bfbf  jmp     loc_14004BD41
0x14004bfc4  mov     ecx, 0Eh
0x14004bfc9  int     29h; Win8: RtlFailFast(ecx)
0x14004bfcb  jmp     loc_14004BE04
0x14004bfd0  mov     [rsp+0A8h+Priority], 40000000h; Priority
0x14004bfd8  xor     r9d, r9d; RequestedAddress
0x14004bfdb  xor     edx, edx; AccessMode
0x14004bfdd  mov     [rsp+0A8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14004bfe5  mov     r8d, 1; CacheType
0x14004bfeb  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004bff2  nop     dword ptr [rax+rax+00h]
0x14004bff7  jmp     loc_14004BB8D
0x14004bffc  mov     dword ptr [r14+8Ch], 0C000021Bh
0x14004c007  jmp     loc_14004BEB5
0x14004c00c  mov     edx, r13d
0x14004c00f  mov     rcx, rbx
0x14004c012  call    IppFindSubInterfaceOnInterfaceByIndexUnderLock
0x14004c017  mov     rdi, rax
0x14004c01a  jmp     loc_14004BE04
0x14004c01f  movzx   ecx, r15b; NewIrql
0x14004c023  call    cs:__imp_KeLowerIrql
0x14004c02a  nop     dword ptr [rax+rax+00h]
0x14004c02f  mov     dword ptr [r14+8Ch], 0C000023Ch
0x14004c03a  jmp     loc_14004BE91
0x14004c03f  movzx   eax, [rsp+0A8h+arg_40]
0x14004c047  xor     r8d, r8d
0x14004c04a  movzx   r9d, [rsp+0A8h+arg_38]
  ... truncated ...
```
