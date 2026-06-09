# IppFindInterfaceForThread

- ea: `0x140051730`
- end: `0x140051a82`
- name: `IppFindInterfaceForThread`
- size: `850`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14005151c`
- `0x140051c00`
- `0x14007ac50`
- `0x14007c640`
- `0x14009a3c0`
- `0x14010bdb4`
- `0x14011edf0`
- `0x140142f30`
- `0x1401433f0`
- `0x140184ea0`
- `0x140185100`
- `0x140185240`
- `0x140189f60`
- `0x1401903a0`
- `0x140190630`
- `0x14019fcd0`
- `0x14019fe30`
- `0x1401a3690`
- `0x1401a37d0`

## callees

- `0x140051730`
- `0x140073660`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140051764`
- `ntoskrnl!KfRaiseIrql` at `0x1400518d2`
- `ntoskrnl!KfRaiseIrql` at `0x140051764`
- `ntoskrnl!KfRaiseIrql` at `0x1400518d2`
- `ntoskrnl!KeLowerIrql` at `0x1400517f2`
- `ntoskrnl!KeLowerIrql` at `0x140051825`
- `ntoskrnl!KeLowerIrql` at `0x14005198d`
- `ntoskrnl!KeLowerIrql` at `0x140051a59`
- `ntoskrnl!KeLowerIrql` at `0x1400517f2`
- `ntoskrnl!KeLowerIrql` at `0x140051825`
- `ntoskrnl!KeLowerIrql` at `0x14005198d`
- `ntoskrnl!KeLowerIrql` at `0x140051a59`
- `ntoskrnl!IoQueueWorkItem` at `0x140051a3f`
- `ntoskrnl!IoQueueWorkItem` at `0x140051a3f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400517a5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140051916`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400517a5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140051916`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400517ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005192c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400517ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005192c`
- `ntoskrnl!KeTestSpinLock` at `0x140051789`
- `ntoskrnl!KeTestSpinLock` at `0x1400518f9`
- `ntoskrnl!KeTestSpinLock` at `0x140051789`
- `ntoskrnl!KeTestSpinLock` at `0x1400518f9`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400519df`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400519df`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14005189e`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14005189e`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400518bb`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400518bb`

## pseudocode

```c
volatile signed __int64 *__fastcall IppFindInterfaceForThread(__int64 a1, __int64 a2, unsigned __int8 a3, _QWORD *a4)
{
  __int64 v5; // rsi
  KIRQL v8; // bp
  _QWORD *v9; // r8
  _QWORD *i; // rax
  volatile signed __int64 *v11; // rbx
  unsigned int *v13; // rsi
  __int64 v14; // rdi
  int Next_high; // ebp
  __int64 v16; // r14
  KIRQL v17; // r15
  volatile signed __int64 *v18; // r12
  _QWORD **v19; // rdx
  _QWORD *j; // rax
  _QWORD *v21; // rdi
  signed __int64 v22; // rax
  bool v23; // cc
  signed __int64 v24; // rax
  struct _KLOCK_QUEUE_HANDLE v26; // [rsp+38h] [rbp-70h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-58h] BYREF

  v5 = a1 + 19896;
  v8 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
  if ( !KeTestSpinLock((PKSPIN_LOCK)v5) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 8));
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v5, &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v9 = (_QWORD *)(a1 + 19912);
  for ( i = *(_QWORD **)(a1 + 19912); ; i = (_QWORD *)*i )
  {
    if ( i == v9 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v5 + 8));
      KeLowerIrql(v8);
      return 0;
    }
    v11 = i - 20;
    if ( *a4 == *(i - 18) )
      break;
  }
  if ( _InterlockedIncrement64(v11 + 19) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)(v5 + 8));
  KeLowerIrql(v8);
  if ( !v11 )
    return 0;
  v13 = (unsigned int *)*v11;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( a2 )
  {
    v18 = v11;
  }
  else
  {
    v14 = *((_QWORD *)v13 + 5);
    NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), &LockHandle, (char *)&LockHandle.LockQueue.Next + 4);
    Next_high = HIDWORD(LockHandle.LockQueue.Next);
    if ( !HIDWORD(LockHandle.LockQueue.Next) )
      Next_high = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
    v16 = v14 + 19880;
    v17 = KfRaiseIrql(2u);
    memset(&v26, 0, sizeof(v26));
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 19888));
    if ( !KeTestSpinLock((PKSPIN_LOCK)(v14 + 19880)) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v14 + 19888));
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v14 + 19880), &v26);
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 19888));
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&v26);
    }
    v18 = v11;
    v19 = (_QWORD **)(*(_QWORD *)(v14 + 19872) + 16LL * (Next_high & (unsigned int)(*(_DWORD *)(v14 + 19868) - 1)));
    for ( j = *v19; ; j = (_QWORD *)*j )
    {
      if ( j == v19 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v16 + 8));
        KeLowerIrql(v17);
        goto LABEL_25;
      }
      v21 = j - 6;
      if ( *((_DWORD *)j - 12) == Next_high )
        break;
    }
    if ( _InterlockedIncrement64(v21 + 4) <= 1 )
      __fastfail(0xEu);
    _InterlockedDecrement((volatile signed __int32 *)(v16 + 8));
    KeLowerIrql(v17);
    if ( v21 )
    {
      *(_OWORD *)&LockHandle.LockQueue.Lock = *(_OWORD *)((char *)v21 + 4);
      v22 = _InterlockedExchangeAdd64(v21 + 4, 0xFFFFFFFFFFFFFFFFuLL);
      v23 = v22 <= 1;
      v24 = v22 - 1;
      if ( v23 )
      {
        if ( v24 )
          __fastfail(0xEu);
        IoQueueWorkItem((PIO_WORKITEM)v21[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v21);
      }
    }
  }
LABEL_25:
  if ( (unsigned __int8)NetioIsCompartmentAccessibleByThread(*v13, v13 + 1, a3) )
    return v11;
  IppDereferenceInterface((PVOID)v18);
  return 0;
}

```

## disassembly

```asm
0x140051730  push    rbx
0x140051732  push    rbp
0x140051733  push    rsi
0x140051734  push    rdi
0x140051735  push    r13
0x140051737  sub     rsp, 80h
0x14005173e  mov     rax, cs:__security_cookie
0x140051745  xor     rax, rsp
0x140051748  mov     [rsp+0A8h+var_40], rax
0x14005174d  mov     rbx, rcx
0x140051750  mov     [rsp+0A8h+var_78], r8b
0x140051755  lea     rsi, [rcx+4DB8h]
0x14005175c  mov     rdi, r9
0x14005175f  mov     cl, 2; NewIrql
0x140051761  mov     r13, rdx
0x140051764  call    cs:__imp_KfRaiseIrql
0x14005176b  nop     dword ptr [rax+rax+00h]
0x140051770  movzx   ebp, al
0x140051773  xorps   xmm0, xmm0
0x140051776  xor     eax, eax
0x140051778  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14005177d  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x140051782  lock inc dword ptr [rsi+8]
0x140051786  mov     rcx, rsi; SpinLock
0x140051789  call    cs:__imp_KeTestSpinLock
0x140051790  nop     dword ptr [rax+rax+00h]
0x140051795  test    al, al
0x140051797  jnz     short loc_1400517C6
0x140051799  lock dec dword ptr [rsi+8]
0x14005179d  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x1400517a2  mov     rcx, rsi; SpinLock
0x1400517a5  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400517ac  nop     dword ptr [rax+rax+00h]
0x1400517b1  lock inc dword ptr [rsi+8]
0x1400517b5  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x1400517ba  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400517c1  nop     dword ptr [rax+rax+00h]
0x1400517c6  lea     r8, [rbx+4DC8h]
0x1400517cd  mov     rax, [r8]
0x1400517d0  cmp     rax, r8
0x1400517d3  jz      short loc_1400517EA
0x1400517d5  mov     rdx, [rdi]
0x1400517d8  lea     rbx, [rax-0A0h]
0x1400517df  cmp     rdx, [rbx+10h]
0x1400517e3  jz      short loc_140051802
0x1400517e5  mov     rax, [rax]
0x1400517e8  jmp     short loc_1400517D0
0x1400517ea  lock dec dword ptr [rsi+8]
0x1400517ee  movzx   ecx, bpl; NewIrql
0x1400517f2  call    cs:__imp_KeLowerIrql
0x1400517f9  nop     dword ptr [rax+rax+00h]
0x1400517fe  xor     eax, eax
0x140051800  jmp     short loc_140051839
0x140051802  mov     eax, 1
0x140051807  lock xadd [rbx+98h], rax
0x140051810  inc     rax
0x140051813  cmp     rax, 1
0x140051817  jle     loc_140051A6A
0x14005181d  lock dec dword ptr [rsi+8]
0x140051821  movzx   ecx, bpl; NewIrql
0x140051825  call    cs:__imp_KeLowerIrql
0x14005182c  nop     dword ptr [rax+rax+00h]
0x140051831  test    rbx, rbx
0x140051834  jnz     short loc_140051855
0x140051836  mov     rax, rbx
0x140051839  mov     rcx, [rsp+0A8h+var_40]
0x14005183e  xor     rcx, rsp; StackCookie
0x140051841  call    __security_check_cookie
0x140051846  add     rsp, 80h
0x14005184d  pop     r13
0x14005184f  pop     rdi
0x140051850  pop     rsi
0x140051851  pop     rbp
0x140051852  pop     rbx
0x140051853  retn
0x140051855  mov     rsi, [rbx]
0x140051858  xor     eax, eax
0x14005185a  mov     [rsp+0A8h+arg_18], r12
0x140051862  xorps   xmm0, xmm0
0x140051865  mov     [rsp+0A8h+var_30], r14
0x14005186a  mov     [rsp+0A8h+var_38], r15
0x14005186f  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140051874  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x140051879  test    r13, r13
0x14005187c  jnz     loc_1400519C8
0x140051882  mov     rcx, gs:188h
0x14005188b  lea     r8, [rsp+0A8h+LockHandle.LockQueue.Next+4]
0x140051890  mov     rdi, [rsi+28h]
0x140051894  lea     rdx, [rsp+0A8h+LockHandle]
0x140051899  lea     r13, [rsp+0A8h+LockHandle]
0x14005189e  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x1400518a5  nop     dword ptr [rax+rax+00h]
0x1400518aa  mov     ebp, dword ptr [rsp+0A8h+LockHandle.LockQueue.Next+4]
0x1400518ae  test    ebp, ebp
0x1400518b0  jnz     short loc_1400518C9
0x1400518b2  mov     rcx, gs:188h
0x1400518bb  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400518c2  nop     dword ptr [rax+rax+00h]
0x1400518c7  mov     ebp, eax
0x1400518c9  mov     cl, 2; NewIrql
0x1400518cb  lea     r14, [rdi+4DA8h]
0x1400518d2  call    cs:__imp_KfRaiseIrql
0x1400518d9  nop     dword ptr [rax+rax+00h]
0x1400518de  movzx   r15d, al
0x1400518e2  xorps   xmm0, xmm0
0x1400518e5  xor     eax, eax
0x1400518e7  mov     qword ptr [rsp+0A8h+var_70.OldIrql], rax
0x1400518ec  movups  xmmword ptr [rsp+0A8h+var_70.LockQueue.Next], xmm0
0x1400518f1  lock inc dword ptr [r14+8]
0x1400518f6  mov     rcx, r14; SpinLock
0x1400518f9  call    cs:__imp_KeTestSpinLock
0x140051900  nop     dword ptr [rax+rax+00h]
0x140051905  test    al, al
0x140051907  jnz     short loc_140051938
0x140051909  lock dec dword ptr [r14+8]
0x14005190e  lea     rdx, [rsp+0A8h+var_70]; LockHandle
0x140051913  mov     rcx, r14; SpinLock
0x140051916  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14005191d  nop     dword ptr [rax+rax+00h]
0x140051922  lock inc dword ptr [r14+8]
0x140051927  lea     rcx, [rsp+0A8h+var_70]; LockHandle
0x14005192c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140051933  nop     dword ptr [rax+rax+00h]
0x140051938  mov     edx, [rdi+4D9Ch]
0x14005193e  mov     r12, rbx
0x140051941  dec     edx
0x140051943  mov     eax, ebp
0x140051945  and     rdx, rax
0x140051948  shl     rdx, 4
0x14005194c  add     rdx, [rdi+4DA0h]
0x140051953  mov     rax, [rdx]
0x140051956  cmp     rax, rdx
0x140051959  jz      loc_140051A50
0x14005195f  cmp     [rax-30h], ebp
0x140051962  lea     rdi, [rax-30h]
0x140051966  jnz     loc_140051A20
0x14005196c  mov     eax, 1
0x140051971  lock xadd [rdi+20h], rax
0x140051977  inc     rax
0x14005197a  cmp     rax, 1
0x14005197e  jle     loc_140051A76
0x140051984  lock dec dword ptr [r14+8]
0x140051989  movzx   ecx, r15b; NewIrql
0x14005198d  call    cs:__imp_KeLowerIrql
0x140051994  nop     dword ptr [rax+rax+00h]
0x140051999  test    rdi, rdi
0x14005199c  jz      short loc_1400519CB
0x14005199e  movups  xmm0, xmmword ptr [rdi+4]
0x1400519a2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400519a9  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Lock], xmm0
0x1400519ae  lock xadd [rdi+20h], rax
0x1400519b4  sub     rax, 1
0x1400519b8  jg      short loc_1400519CB
0x1400519ba  test    rax, rax
0x1400519bd  jz      short loc_140051A28
0x1400519bf  mov     ecx, 0Eh
0x1400519c4  int     29h; Win8: RtlFailFast(ecx)
0x1400519c6  jmp     short loc_1400519CB
0x1400519c8  mov     r12, rbx
0x1400519cb  movzx   r8d, [rsp+0A8h+var_78]
0x1400519d1  lea     rdx, [rsi+4]
0x1400519d5  mov     ecx, [rsi]
0x1400519d7  mov     r9b, 1
0x1400519da  mov     [rsp+0A8h+var_88], r13
0x1400519df  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1400519e6  nop     dword ptr [rax+rax+00h]
0x1400519eb  mov     r15, [rsp+0A8h+var_38]
0x1400519f0  mov     r14, [rsp+0A8h+var_30]
0x1400519f5  test    al, al
0x1400519f7  jz      short loc_140051A09
0x1400519f9  mov     r12, [rsp+0A8h+arg_18]
0x140051a01  mov     rax, rbx
0x140051a04  jmp     loc_140051839
0x140051a09  mov     rcx, r12; Context
0x140051a0c  call    IppDereferenceInterface
0x140051a11  mov     r12, [rsp+0A8h+arg_18]
0x140051a19  xor     eax, eax
0x140051a1b  jmp     loc_140051839
0x140051a20  mov     rax, [rax]
0x140051a23  jmp     loc_140051956
0x140051a28  mov     rcx, [rdi+80h]; IoWorkItem
0x140051a2f  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x140051a36  mov     r9, rdi; Context
0x140051a39  mov     r8d, 1; QueueType
0x140051a3f  call    cs:__imp_IoQueueWorkItem
0x140051a46  nop     dword ptr [rax+rax+00h]
0x140051a4b  jmp     loc_1400519CB
0x140051a50  lock dec dword ptr [r14+8]
0x140051a55  movzx   ecx, r15b; NewIrql
0x140051a59  call    cs:__imp_KeLowerIrql
0x140051a60  nop     dword ptr [rax+rax+00h]
0x140051a65  jmp     loc_1400519CB
0x140051a6a  mov     ecx, 0Eh
0x140051a6f  int     29h; Win8: RtlFailFast(ecx)
0x140051a71  jmp     loc_14005181D
0x140051a76  mov     ecx, 0Eh
0x140051a7b  int     29h; Win8: RtlFailFast(ecx)
0x140051a7d  jmp     loc_140051984
```
