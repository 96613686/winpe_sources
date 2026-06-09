# IppIsCompartmentAccessibleByThread

- ea: `0x140066310`
- end: `0x140066542`
- name: `IppIsCompartmentAccessibleByThread`
- size: `562`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140065430`
- `0x14007f330`
- `0x1400a15b0`
- `0x1400e1cb0`
- `0x1401077b0`
- `0x140140050`
- `0x140184ad8`
- `0x140189b00`
- `0x14018a454`
- `0x14018fb40`
- `0x140190310`
- `0x14019e070`
- `0x1401a1a10`

## callees

- `0x140066310`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400663ac`
- `ntoskrnl!KfRaiseIrql` at `0x1400663ac`
- `ntoskrnl!KeLowerIrql` at `0x140066460`
- `ntoskrnl!KeLowerIrql` at `0x140066525`
- `ntoskrnl!KeLowerIrql` at `0x140066460`
- `ntoskrnl!KeLowerIrql` at `0x140066525`
- `ntoskrnl!IoQueueWorkItem` at `0x14006650c`
- `ntoskrnl!IoQueueWorkItem` at `0x14006650c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400663ee`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400663ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140066403`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140066403`
- `ntoskrnl!KeTestSpinLock` at `0x1400663d2`
- `ntoskrnl!KeTestSpinLock` at `0x1400663d2`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400664c6`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400664c6`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140066378`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140066378`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140066395`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140066395`

## pseudocode

```c
__int64 __fastcall IppIsCompartmentAccessibleByThread(unsigned int *a1, __int64 a2, unsigned __int8 a3)
{
  __int64 v5; // rbx
  int ThreadObjectCompartmentId; // esi
  __int64 v7; // rdi
  KIRQL v8; // r15
  _QWORD **v9; // rdx
  _QWORD *i; // rax
  _QWORD *v11; // rbx
  signed __int64 v12; // rax
  bool v13; // cc
  signed __int64 v14; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v17[3]; // [rsp+48h] [rbp-60h] BYREF

  memset(v17, 0, sizeof(v17));
  if ( !a2 )
  {
    v5 = *((_QWORD *)a1 + 5);
    NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), v17, (char *)v17 + 4);
    ThreadObjectCompartmentId = HIDWORD(v17[0]);
    if ( !HIDWORD(v17[0]) )
      ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
    v7 = v5 + 19880;
    v8 = KfRaiseIrql(2u);
    memset(&LockHandle, 0, sizeof(LockHandle));
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 19888));
    if ( !KeTestSpinLock((PKSPIN_LOCK)(v5 + 19880)) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v5 + 19888));
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v5 + 19880), &LockHandle);
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 19888));
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    }
    v9 = (_QWORD **)(*(_QWORD *)(v5 + 19872)
                   + 16LL * (ThreadObjectCompartmentId & (unsigned int)(*(_DWORD *)(v5 + 19868) - 1)));
    for ( i = *v9; ; i = (_QWORD *)*i )
    {
      if ( i == v9 )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v7 + 8));
        KeLowerIrql(v8);
        return NetioIsCompartmentAccessibleByThread(*a1, a1 + 1, a3);
      }
      v11 = i - 6;
      if ( *((_DWORD *)i - 12) == ThreadObjectCompartmentId )
        break;
    }
    if ( _InterlockedIncrement64(v11 + 4) <= 1 )
      __fastfail(0xEu);
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 8));
    KeLowerIrql(v8);
    if ( v11 )
    {
      *(_OWORD *)&v17[1] = *(_OWORD *)((char *)v11 + 4);
      v12 = _InterlockedExchangeAdd64(v11 + 4, 0xFFFFFFFFFFFFFFFFuLL);
      v13 = v12 <= 1;
      v14 = v12 - 1;
      if ( v13 )
      {
        if ( v14 )
          __fastfail(0xEu);
        IoQueueWorkItem((PIO_WORKITEM)v11[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v11);
      }
    }
  }
  return NetioIsCompartmentAccessibleByThread(*a1, a1 + 1, a3);
}

```

## disassembly

```asm
0x140066310  mov     r11, rsp
0x140066313  push    rbp
0x140066314  push    r12
0x140066316  push    r14
0x140066318  sub     rsp, 90h
0x14006631f  mov     rax, cs:__security_cookie
0x140066326  xor     rax, rsp
0x140066329  mov     [rsp+0A8h+var_48], rax
0x14006632e  xor     eax, eax
0x140066330  xorps   xmm0, xmm0
0x140066333  movzx   r12d, r8b
0x140066337  mov     rbp, rdx
0x14006633a  mov     r14, rcx
0x14006633d  movups  xmmword ptr [rsp+0A8h+var_60], xmm0
0x140066342  mov     [r11-50h], rax
0x140066346  test    rdx, rdx
0x140066349  jnz     loc_1400664B3
0x14006634f  mov     [r11-20h], rbx
0x140066353  lea     r8, [r11-5Ch]
0x140066357  mov     rbx, [rcx+28h]
0x14006635b  lea     rdx, [r11-60h]
0x14006635f  mov     rcx, gs:188h
0x140066368  lea     rbp, [r11-60h]
0x14006636c  mov     [r11-28h], rsi
0x140066370  mov     [r11-30h], rdi
0x140066374  mov     [r11-38h], r15
0x140066378  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x14006637f  nop     dword ptr [rax+rax+00h]
0x140066384  mov     esi, dword ptr [rsp+0A8h+var_60+4]
0x140066388  test    esi, esi
0x14006638a  jnz     short loc_1400663A3
0x14006638c  mov     rcx, gs:188h
0x140066395  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14006639c  nop     dword ptr [rax+rax+00h]
0x1400663a1  mov     esi, eax
0x1400663a3  mov     cl, 2; NewIrql
0x1400663a5  lea     rdi, [rbx+4DA8h]
0x1400663ac  call    cs:__imp_KfRaiseIrql
0x1400663b3  nop     dword ptr [rax+rax+00h]
0x1400663b8  movzx   r15d, al
0x1400663bc  xorps   xmm0, xmm0
0x1400663bf  xor     eax, eax
0x1400663c1  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x1400663c6  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x1400663cb  lock inc dword ptr [rdi+8]
0x1400663cf  mov     rcx, rdi; SpinLock
0x1400663d2  call    cs:__imp_KeTestSpinLock
0x1400663d9  nop     dword ptr [rax+rax+00h]
0x1400663de  test    al, al
0x1400663e0  jnz     short loc_14006640F
0x1400663e2  lock dec dword ptr [rdi+8]
0x1400663e6  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x1400663eb  mov     rcx, rdi; SpinLock
0x1400663ee  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400663f5  nop     dword ptr [rax+rax+00h]
0x1400663fa  lock inc dword ptr [rdi+8]
0x1400663fe  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140066403  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14006640a  nop     dword ptr [rax+rax+00h]
0x14006640f  mov     edx, [rbx+4D9Ch]
0x140066415  dec     edx
0x140066417  mov     eax, esi
0x140066419  and     rdx, rax
0x14006641c  shl     rdx, 4
0x140066420  add     rdx, [rbx+4DA0h]
0x140066427  mov     rax, [rdx]
0x14006642a  cmp     rax, rdx
0x14006642d  jz      loc_14006651D
0x140066433  cmp     [rax-30h], esi
0x140066436  lea     rbx, [rax-30h]
0x14006643a  jnz     loc_1400664ED
0x140066440  mov     eax, 1
0x140066445  lock xadd [rbx+20h], rax
0x14006644b  inc     rax
0x14006644e  cmp     rax, 1
0x140066452  jle     loc_140066536
0x140066458  lock dec dword ptr [rdi+8]
0x14006645c  movzx   ecx, r15b; NewIrql
0x140066460  call    cs:__imp_KeLowerIrql
0x140066467  nop     dword ptr [rax+rax+00h]
0x14006646c  test    rbx, rbx
0x14006646f  jz      short loc_140066499
0x140066471  movups  xmm0, xmmword ptr [rbx+4]
0x140066475  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14006647c  movups  xmmword ptr [rsp+0A8h+var_60+8], xmm0
0x140066481  lock xadd [rbx+20h], rax
0x140066487  sub     rax, 1
0x14006648b  jg      short loc_140066499
0x14006648d  test    rax, rax
0x140066490  jz      short loc_1400664F5
0x140066492  mov     ecx, 0Eh
0x140066497  int     29h; Win8: RtlFailFast(ecx)
0x140066499  mov     rdi, [rsp+0A8h+var_30]
0x14006649e  mov     rsi, [rsp+0A8h+var_28]
0x1400664a6  mov     rbx, [rsp+0A8h+var_20]
0x1400664ae  mov     r15, [rsp+0A8h+var_38]
0x1400664b3  mov     ecx, [r14]
0x1400664b6  lea     rdx, [r14+4]
0x1400664ba  mov     r9b, 1
0x1400664bd  mov     [rsp+0A8h+var_88], rbp
0x1400664c2  movzx   r8d, r12b
0x1400664c6  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1400664cd  nop     dword ptr [rax+rax+00h]
0x1400664d2  mov     rcx, [rsp+0A8h+var_48]
0x1400664d7  xor     rcx, rsp; StackCookie
0x1400664da  call    __security_check_cookie
0x1400664df  add     rsp, 90h
0x1400664e6  pop     r14
0x1400664e8  pop     r12
0x1400664ea  pop     rbp
0x1400664eb  retn
0x1400664ed  mov     rax, [rax]
0x1400664f0  jmp     loc_14006642A
0x1400664f5  mov     rcx, [rbx+80h]; IoWorkItem
0x1400664fc  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x140066503  mov     r9, rbx; Context
0x140066506  mov     r8d, 1; QueueType
0x14006650c  call    cs:__imp_IoQueueWorkItem
0x140066513  nop     dword ptr [rax+rax+00h]
0x140066518  jmp     loc_140066499
0x14006651d  lock dec dword ptr [rdi+8]
0x140066521  movzx   ecx, r15b; NewIrql
0x140066525  call    cs:__imp_KeLowerIrql
0x14006652c  nop     dword ptr [rax+rax+00h]
0x140066531  jmp     loc_140066499
0x140066536  mov     ecx, 0Eh
0x14006653b  int     29h; Win8: RtlFailFast(ecx)
0x14006653d  jmp     loc_140066458
```
