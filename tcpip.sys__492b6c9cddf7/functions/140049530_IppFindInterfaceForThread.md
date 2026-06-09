# IppFindInterfaceForThread

- ea: `0x140049530`
- end: `0x140049882`
- name: `IppFindInterfaceForThread`
- size: `850`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140047900`
- `0x140048c14`
- `0x140048cf0`
- `0x14004931c`
- `0x140049a00`
- `0x14004b7e0`
- `0x1400e1cb0`
- `0x14013dc90`
- `0x14013e150`
- `0x140183280`
- `0x1401834e0`
- `0x140183620`
- `0x1401882f0`
- `0x14018e5c0`
- `0x14018e850`
- `0x14019df10`
- `0x14019e070`
- `0x1401a18d0`
- `0x1401a1a10`

## callees

- `0x140030da0`
- `0x140049530`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140049564`
- `ntoskrnl!KfRaiseIrql` at `0x1400496d2`
- `ntoskrnl!KfRaiseIrql` at `0x140049564`
- `ntoskrnl!KfRaiseIrql` at `0x1400496d2`
- `ntoskrnl!KeLowerIrql` at `0x1400495f2`
- `ntoskrnl!KeLowerIrql` at `0x140049625`
- `ntoskrnl!KeLowerIrql` at `0x14004978d`
- `ntoskrnl!KeLowerIrql` at `0x140049859`
- `ntoskrnl!KeLowerIrql` at `0x1400495f2`
- `ntoskrnl!KeLowerIrql` at `0x140049625`
- `ntoskrnl!KeLowerIrql` at `0x14004978d`
- `ntoskrnl!KeLowerIrql` at `0x140049859`
- `ntoskrnl!IoQueueWorkItem` at `0x14004983f`
- `ntoskrnl!IoQueueWorkItem` at `0x14004983f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400495a5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140049716`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400495a5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140049716`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400495ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004972c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400495ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004972c`
- `ntoskrnl!KeTestSpinLock` at `0x140049589`
- `ntoskrnl!KeTestSpinLock` at `0x1400496f9`
- `ntoskrnl!KeTestSpinLock` at `0x140049589`
- `ntoskrnl!KeTestSpinLock` at `0x1400496f9`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400497df`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400497df`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14004969e`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14004969e`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400496bb`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400496bb`

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
0x140049530  push    rbx
0x140049532  push    rbp
0x140049533  push    rsi
0x140049534  push    rdi
0x140049535  push    r13
0x140049537  sub     rsp, 80h
0x14004953e  mov     rax, cs:__security_cookie
0x140049545  xor     rax, rsp
0x140049548  mov     [rsp+0A8h+var_40], rax
0x14004954d  mov     rbx, rcx
0x140049550  mov     [rsp+0A8h+var_78], r8b
0x140049555  lea     rsi, [rcx+4DB8h]
0x14004955c  mov     rdi, r9
0x14004955f  mov     cl, 2; NewIrql
0x140049561  mov     r13, rdx
0x140049564  call    cs:__imp_KfRaiseIrql
0x14004956b  nop     dword ptr [rax+rax+00h]
0x140049570  movzx   ebp, al
0x140049573  xorps   xmm0, xmm0
0x140049576  xor     eax, eax
0x140049578  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14004957d  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x140049582  lock inc dword ptr [rsi+8]
0x140049586  mov     rcx, rsi; SpinLock
0x140049589  call    cs:__imp_KeTestSpinLock
0x140049590  nop     dword ptr [rax+rax+00h]
0x140049595  test    al, al
0x140049597  jnz     short loc_1400495C6
0x140049599  lock dec dword ptr [rsi+8]
0x14004959d  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x1400495a2  mov     rcx, rsi; SpinLock
0x1400495a5  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400495ac  nop     dword ptr [rax+rax+00h]
0x1400495b1  lock inc dword ptr [rsi+8]
0x1400495b5  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x1400495ba  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400495c1  nop     dword ptr [rax+rax+00h]
0x1400495c6  lea     r8, [rbx+4DC8h]
0x1400495cd  mov     rax, [r8]
0x1400495d0  cmp     rax, r8
0x1400495d3  jz      short loc_1400495EA
0x1400495d5  mov     rdx, [rdi]
0x1400495d8  lea     rbx, [rax-0A0h]
0x1400495df  cmp     rdx, [rbx+10h]
0x1400495e3  jz      short loc_140049602
0x1400495e5  mov     rax, [rax]
0x1400495e8  jmp     short loc_1400495D0
0x1400495ea  lock dec dword ptr [rsi+8]
0x1400495ee  movzx   ecx, bpl; NewIrql
0x1400495f2  call    cs:__imp_KeLowerIrql
0x1400495f9  nop     dword ptr [rax+rax+00h]
0x1400495fe  xor     eax, eax
0x140049600  jmp     short loc_140049639
0x140049602  mov     eax, 1
0x140049607  lock xadd [rbx+98h], rax
0x140049610  inc     rax
0x140049613  cmp     rax, 1
0x140049617  jle     loc_14004986A
0x14004961d  lock dec dword ptr [rsi+8]
0x140049621  movzx   ecx, bpl; NewIrql
0x140049625  call    cs:__imp_KeLowerIrql
0x14004962c  nop     dword ptr [rax+rax+00h]
0x140049631  test    rbx, rbx
0x140049634  jnz     short loc_140049655
0x140049636  mov     rax, rbx
0x140049639  mov     rcx, [rsp+0A8h+var_40]
0x14004963e  xor     rcx, rsp; StackCookie
0x140049641  call    __security_check_cookie
0x140049646  add     rsp, 80h
0x14004964d  pop     r13
0x14004964f  pop     rdi
0x140049650  pop     rsi
0x140049651  pop     rbp
0x140049652  pop     rbx
0x140049653  retn
0x140049655  mov     rsi, [rbx]
0x140049658  xor     eax, eax
0x14004965a  mov     [rsp+0A8h+arg_18], r12
0x140049662  xorps   xmm0, xmm0
0x140049665  mov     [rsp+0A8h+var_30], r14
0x14004966a  mov     [rsp+0A8h+var_38], r15
0x14004966f  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140049674  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x140049679  test    r13, r13
0x14004967c  jnz     loc_1400497C8
0x140049682  mov     rcx, gs:188h
0x14004968b  lea     r8, [rsp+0A8h+LockHandle.LockQueue.Next+4]
0x140049690  mov     rdi, [rsi+28h]
0x140049694  lea     rdx, [rsp+0A8h+LockHandle]
0x140049699  lea     r13, [rsp+0A8h+LockHandle]
0x14004969e  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x1400496a5  nop     dword ptr [rax+rax+00h]
0x1400496aa  mov     ebp, dword ptr [rsp+0A8h+LockHandle.LockQueue.Next+4]
0x1400496ae  test    ebp, ebp
0x1400496b0  jnz     short loc_1400496C9
0x1400496b2  mov     rcx, gs:188h
0x1400496bb  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400496c2  nop     dword ptr [rax+rax+00h]
0x1400496c7  mov     ebp, eax
0x1400496c9  mov     cl, 2; NewIrql
0x1400496cb  lea     r14, [rdi+4DA8h]
0x1400496d2  call    cs:__imp_KfRaiseIrql
0x1400496d9  nop     dword ptr [rax+rax+00h]
0x1400496de  movzx   r15d, al
0x1400496e2  xorps   xmm0, xmm0
0x1400496e5  xor     eax, eax
0x1400496e7  mov     qword ptr [rsp+0A8h+var_70.OldIrql], rax
0x1400496ec  movups  xmmword ptr [rsp+0A8h+var_70.LockQueue.Next], xmm0
0x1400496f1  lock inc dword ptr [r14+8]
0x1400496f6  mov     rcx, r14; SpinLock
0x1400496f9  call    cs:__imp_KeTestSpinLock
0x140049700  nop     dword ptr [rax+rax+00h]
0x140049705  test    al, al
0x140049707  jnz     short loc_140049738
0x140049709  lock dec dword ptr [r14+8]
0x14004970e  lea     rdx, [rsp+0A8h+var_70]; LockHandle
0x140049713  mov     rcx, r14; SpinLock
0x140049716  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14004971d  nop     dword ptr [rax+rax+00h]
0x140049722  lock inc dword ptr [r14+8]
0x140049727  lea     rcx, [rsp+0A8h+var_70]; LockHandle
0x14004972c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140049733  nop     dword ptr [rax+rax+00h]
0x140049738  mov     edx, [rdi+4D9Ch]
0x14004973e  mov     r12, rbx
0x140049741  dec     edx
0x140049743  mov     eax, ebp
0x140049745  and     rdx, rax
0x140049748  shl     rdx, 4
0x14004974c  add     rdx, [rdi+4DA0h]
0x140049753  mov     rax, [rdx]
0x140049756  cmp     rax, rdx
0x140049759  jz      loc_140049850
0x14004975f  cmp     [rax-30h], ebp
0x140049762  lea     rdi, [rax-30h]
0x140049766  jnz     loc_140049820
0x14004976c  mov     eax, 1
0x140049771  lock xadd [rdi+20h], rax
0x140049777  inc     rax
0x14004977a  cmp     rax, 1
0x14004977e  jle     loc_140049876
0x140049784  lock dec dword ptr [r14+8]
0x140049789  movzx   ecx, r15b; NewIrql
0x14004978d  call    cs:__imp_KeLowerIrql
0x140049794  nop     dword ptr [rax+rax+00h]
0x140049799  test    rdi, rdi
0x14004979c  jz      short loc_1400497CB
0x14004979e  movups  xmm0, xmmword ptr [rdi+4]
0x1400497a2  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400497a9  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Lock], xmm0
0x1400497ae  lock xadd [rdi+20h], rax
0x1400497b4  sub     rax, 1
0x1400497b8  jg      short loc_1400497CB
0x1400497ba  test    rax, rax
0x1400497bd  jz      short loc_140049828
0x1400497bf  mov     ecx, 0Eh
0x1400497c4  int     29h; Win8: RtlFailFast(ecx)
0x1400497c6  jmp     short loc_1400497CB
0x1400497c8  mov     r12, rbx
0x1400497cb  movzx   r8d, [rsp+0A8h+var_78]
0x1400497d1  lea     rdx, [rsi+4]
0x1400497d5  mov     ecx, [rsi]
0x1400497d7  mov     r9b, 1
0x1400497da  mov     [rsp+0A8h+var_88], r13
0x1400497df  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1400497e6  nop     dword ptr [rax+rax+00h]
0x1400497eb  mov     r15, [rsp+0A8h+var_38]
0x1400497f0  mov     r14, [rsp+0A8h+var_30]
0x1400497f5  test    al, al
0x1400497f7  jz      short loc_140049809
0x1400497f9  mov     r12, [rsp+0A8h+arg_18]
0x140049801  mov     rax, rbx
0x140049804  jmp     loc_140049639
0x140049809  mov     rcx, r12; Context
0x14004980c  call    IppDereferenceInterface
0x140049811  mov     r12, [rsp+0A8h+arg_18]
0x140049819  xor     eax, eax
0x14004981b  jmp     loc_140049639
0x140049820  mov     rax, [rax]
0x140049823  jmp     loc_140049756
0x140049828  mov     rcx, [rdi+80h]; IoWorkItem
0x14004982f  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x140049836  mov     r9, rdi; Context
0x140049839  mov     r8d, 1; QueueType
0x14004983f  call    cs:__imp_IoQueueWorkItem
0x140049846  nop     dword ptr [rax+rax+00h]
0x14004984b  jmp     loc_1400497CB
0x140049850  lock dec dword ptr [r14+8]
0x140049855  movzx   ecx, r15b; NewIrql
0x140049859  call    cs:__imp_KeLowerIrql
0x140049860  nop     dword ptr [rax+rax+00h]
0x140049865  jmp     loc_1400497CB
0x14004986a  mov     ecx, 0Eh
0x14004986f  int     29h; Win8: RtlFailFast(ecx)
0x140049871  jmp     loc_14004961D
0x140049876  mov     ecx, 0Eh
0x14004987b  int     29h; Win8: RtlFailFast(ecx)
0x14004987d  jmp     loc_140049784
```
