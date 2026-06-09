# IppFindInterfaceForThread

- ea: `0x1400497d0`
- end: `0x140049b22`
- name: `IppFindInterfaceForThread`
- size: `850`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140047ba0`
- `0x140048eb4`
- `0x140048f90`
- `0x1400495bc`
- `0x140049ca0`
- `0x14004ba80`
- `0x1400e1a90`
- `0x14013de20`
- `0x14013e2e0`
- `0x1401833c0`
- `0x140183620`
- `0x140183760`
- `0x140188430`
- `0x14018e700`
- `0x14018e990`
- `0x14019e050`
- `0x14019e1b0`
- `0x1401a1a10`
- `0x1401a1b50`

## callees

- `0x140031040`
- `0x1400497d0`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140049804`
- `ntoskrnl!KfRaiseIrql` at `0x140049972`
- `ntoskrnl!KfRaiseIrql` at `0x140049804`
- `ntoskrnl!KfRaiseIrql` at `0x140049972`
- `ntoskrnl!KeLowerIrql` at `0x140049892`
- `ntoskrnl!KeLowerIrql` at `0x1400498c5`
- `ntoskrnl!KeLowerIrql` at `0x140049a2d`
- `ntoskrnl!KeLowerIrql` at `0x140049af9`
- `ntoskrnl!KeLowerIrql` at `0x140049892`
- `ntoskrnl!KeLowerIrql` at `0x1400498c5`
- `ntoskrnl!KeLowerIrql` at `0x140049a2d`
- `ntoskrnl!KeLowerIrql` at `0x140049af9`
- `ntoskrnl!IoQueueWorkItem` at `0x140049adf`
- `ntoskrnl!IoQueueWorkItem` at `0x140049adf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140049845`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400499b6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140049845`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400499b6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004985a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400499cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14004985a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400499cc`
- `ntoskrnl!KeTestSpinLock` at `0x140049829`
- `ntoskrnl!KeTestSpinLock` at `0x140049999`
- `ntoskrnl!KeTestSpinLock` at `0x140049829`
- `ntoskrnl!KeTestSpinLock` at `0x140049999`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140049a7f`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x140049a7f`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14004993e`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x14004993e`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14004995b`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x14004995b`

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
0x1400497d0  push    rbx
0x1400497d2  push    rbp
0x1400497d3  push    rsi
0x1400497d4  push    rdi
0x1400497d5  push    r13
0x1400497d7  sub     rsp, 80h
0x1400497de  mov     rax, cs:__security_cookie
0x1400497e5  xor     rax, rsp
0x1400497e8  mov     [rsp+0A8h+var_40], rax
0x1400497ed  mov     rbx, rcx
0x1400497f0  mov     [rsp+0A8h+var_78], r8b
0x1400497f5  lea     rsi, [rcx+4DB8h]
0x1400497fc  mov     rdi, r9
0x1400497ff  mov     cl, 2; NewIrql
0x140049801  mov     r13, rdx
0x140049804  call    cs:__imp_KfRaiseIrql
0x14004980b  nop     dword ptr [rax+rax+00h]
0x140049810  movzx   ebp, al
0x140049813  xorps   xmm0, xmm0
0x140049816  xor     eax, eax
0x140049818  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14004981d  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x140049822  lock inc dword ptr [rsi+8]
0x140049826  mov     rcx, rsi; SpinLock
0x140049829  call    cs:__imp_KeTestSpinLock
0x140049830  nop     dword ptr [rax+rax+00h]
0x140049835  test    al, al
0x140049837  jnz     short loc_140049866
0x140049839  lock dec dword ptr [rsi+8]
0x14004983d  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x140049842  mov     rcx, rsi; SpinLock
0x140049845  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14004984c  nop     dword ptr [rax+rax+00h]
0x140049851  lock inc dword ptr [rsi+8]
0x140049855  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x14004985a  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140049861  nop     dword ptr [rax+rax+00h]
0x140049866  lea     r8, [rbx+4DC8h]
0x14004986d  mov     rax, [r8]
0x140049870  cmp     rax, r8
0x140049873  jz      short loc_14004988A
0x140049875  mov     rdx, [rdi]
0x140049878  lea     rbx, [rax-0A0h]
0x14004987f  cmp     rdx, [rbx+10h]
0x140049883  jz      short loc_1400498A2
0x140049885  mov     rax, [rax]
0x140049888  jmp     short loc_140049870
0x14004988a  lock dec dword ptr [rsi+8]
0x14004988e  movzx   ecx, bpl; NewIrql
0x140049892  call    cs:__imp_KeLowerIrql
0x140049899  nop     dword ptr [rax+rax+00h]
0x14004989e  xor     eax, eax
0x1400498a0  jmp     short loc_1400498D9
0x1400498a2  mov     eax, 1
0x1400498a7  lock xadd [rbx+98h], rax
0x1400498b0  inc     rax
0x1400498b3  cmp     rax, 1
0x1400498b7  jle     loc_140049B0A
0x1400498bd  lock dec dword ptr [rsi+8]
0x1400498c1  movzx   ecx, bpl; NewIrql
0x1400498c5  call    cs:__imp_KeLowerIrql
0x1400498cc  nop     dword ptr [rax+rax+00h]
0x1400498d1  test    rbx, rbx
0x1400498d4  jnz     short loc_1400498F5
0x1400498d6  mov     rax, rbx
0x1400498d9  mov     rcx, [rsp+0A8h+var_40]
0x1400498de  xor     rcx, rsp; StackCookie
0x1400498e1  call    __security_check_cookie
0x1400498e6  add     rsp, 80h
0x1400498ed  pop     r13
0x1400498ef  pop     rdi
0x1400498f0  pop     rsi
0x1400498f1  pop     rbp
0x1400498f2  pop     rbx
0x1400498f3  retn
0x1400498f5  mov     rsi, [rbx]
0x1400498f8  xor     eax, eax
0x1400498fa  mov     [rsp+0A8h+arg_18], r12
0x140049902  xorps   xmm0, xmm0
0x140049905  mov     [rsp+0A8h+var_30], r14
0x14004990a  mov     [rsp+0A8h+var_38], r15
0x14004990f  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140049914  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x140049919  test    r13, r13
0x14004991c  jnz     loc_140049A68
0x140049922  mov     rcx, gs:188h
0x14004992b  lea     r8, [rsp+0A8h+LockHandle.LockQueue.Next+4]
0x140049930  mov     rdi, [rsi+28h]
0x140049934  lea     rdx, [rsp+0A8h+LockHandle]
0x140049939  lea     r13, [rsp+0A8h+LockHandle]
0x14004993e  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x140049945  nop     dword ptr [rax+rax+00h]
0x14004994a  mov     ebp, dword ptr [rsp+0A8h+LockHandle.LockQueue.Next+4]
0x14004994e  test    ebp, ebp
0x140049950  jnz     short loc_140049969
0x140049952  mov     rcx, gs:188h
0x14004995b  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x140049962  nop     dword ptr [rax+rax+00h]
0x140049967  mov     ebp, eax
0x140049969  mov     cl, 2; NewIrql
0x14004996b  lea     r14, [rdi+4DA8h]
0x140049972  call    cs:__imp_KfRaiseIrql
0x140049979  nop     dword ptr [rax+rax+00h]
0x14004997e  movzx   r15d, al
0x140049982  xorps   xmm0, xmm0
0x140049985  xor     eax, eax
0x140049987  mov     qword ptr [rsp+0A8h+var_70.OldIrql], rax
0x14004998c  movups  xmmword ptr [rsp+0A8h+var_70.LockQueue.Next], xmm0
0x140049991  lock inc dword ptr [r14+8]
0x140049996  mov     rcx, r14; SpinLock
0x140049999  call    cs:__imp_KeTestSpinLock
0x1400499a0  nop     dword ptr [rax+rax+00h]
0x1400499a5  test    al, al
0x1400499a7  jnz     short loc_1400499D8
0x1400499a9  lock dec dword ptr [r14+8]
0x1400499ae  lea     rdx, [rsp+0A8h+var_70]; LockHandle
0x1400499b3  mov     rcx, r14; SpinLock
0x1400499b6  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400499bd  nop     dword ptr [rax+rax+00h]
0x1400499c2  lock inc dword ptr [r14+8]
0x1400499c7  lea     rcx, [rsp+0A8h+var_70]; LockHandle
0x1400499cc  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400499d3  nop     dword ptr [rax+rax+00h]
0x1400499d8  mov     edx, [rdi+4D9Ch]
0x1400499de  mov     r12, rbx
0x1400499e1  dec     edx
0x1400499e3  mov     eax, ebp
0x1400499e5  and     rdx, rax
0x1400499e8  shl     rdx, 4
0x1400499ec  add     rdx, [rdi+4DA0h]
0x1400499f3  mov     rax, [rdx]
0x1400499f6  cmp     rax, rdx
0x1400499f9  jz      loc_140049AF0
0x1400499ff  cmp     [rax-30h], ebp
0x140049a02  lea     rdi, [rax-30h]
0x140049a06  jnz     loc_140049AC0
0x140049a0c  mov     eax, 1
0x140049a11  lock xadd [rdi+20h], rax
0x140049a17  inc     rax
0x140049a1a  cmp     rax, 1
0x140049a1e  jle     loc_140049B16
0x140049a24  lock dec dword ptr [r14+8]
0x140049a29  movzx   ecx, r15b; NewIrql
0x140049a2d  call    cs:__imp_KeLowerIrql
0x140049a34  nop     dword ptr [rax+rax+00h]
0x140049a39  test    rdi, rdi
0x140049a3c  jz      short loc_140049A6B
0x140049a3e  movups  xmm0, xmmword ptr [rdi+4]
0x140049a42  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140049a49  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Lock], xmm0
0x140049a4e  lock xadd [rdi+20h], rax
0x140049a54  sub     rax, 1
0x140049a58  jg      short loc_140049A6B
0x140049a5a  test    rax, rax
0x140049a5d  jz      short loc_140049AC8
0x140049a5f  mov     ecx, 0Eh
0x140049a64  int     29h; Win8: RtlFailFast(ecx)
0x140049a66  jmp     short loc_140049A6B
0x140049a68  mov     r12, rbx
0x140049a6b  movzx   r8d, [rsp+0A8h+var_78]
0x140049a71  lea     rdx, [rsi+4]
0x140049a75  mov     ecx, [rsi]
0x140049a77  mov     r9b, 1
0x140049a7a  mov     [rsp+0A8h+var_88], r13
0x140049a7f  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x140049a86  nop     dword ptr [rax+rax+00h]
0x140049a8b  mov     r15, [rsp+0A8h+var_38]
0x140049a90  mov     r14, [rsp+0A8h+var_30]
0x140049a95  test    al, al
0x140049a97  jz      short loc_140049AA9
0x140049a99  mov     r12, [rsp+0A8h+arg_18]
0x140049aa1  mov     rax, rbx
0x140049aa4  jmp     loc_1400498D9
0x140049aa9  mov     rcx, r12; Context
0x140049aac  call    IppDereferenceInterface
0x140049ab1  mov     r12, [rsp+0A8h+arg_18]
0x140049ab9  xor     eax, eax
0x140049abb  jmp     loc_1400498D9
0x140049ac0  mov     rax, [rax]
0x140049ac3  jmp     loc_1400499F6
0x140049ac8  mov     rcx, [rdi+80h]; IoWorkItem
0x140049acf  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x140049ad6  mov     r9, rdi; Context
0x140049ad9  mov     r8d, 1; QueueType
0x140049adf  call    cs:__imp_IoQueueWorkItem
0x140049ae6  nop     dword ptr [rax+rax+00h]
0x140049aeb  jmp     loc_140049A6B
0x140049af0  lock dec dword ptr [r14+8]
0x140049af5  movzx   ecx, r15b; NewIrql
0x140049af9  call    cs:__imp_KeLowerIrql
0x140049b00  nop     dword ptr [rax+rax+00h]
0x140049b05  jmp     loc_140049A6B
0x140049b0a  mov     ecx, 0Eh
0x140049b0f  int     29h; Win8: RtlFailFast(ecx)
0x140049b11  jmp     loc_1400498BD
0x140049b16  mov     ecx, 0Eh
0x140049b1b  int     29h; Win8: RtlFailFast(ecx)
0x140049b1d  jmp     loc_140049A24
```
