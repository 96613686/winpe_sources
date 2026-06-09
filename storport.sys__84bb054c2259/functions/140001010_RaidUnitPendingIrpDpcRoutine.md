# RaidUnitPendingIrpDpcRoutine

- ea: `0x140001010`
- end: `0x140001295`
- name: `RaidUnitPendingIrpDpcRoutine`
- size: `645`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001010`
- `0x1400016cc`
- `0x140005c50`
- `0x140021bf0`
- `0x140068798`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x1400011fa`
- `ntoskrnl!PoFxIdleComponent` at `0x1400011fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001082`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001082`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010e3`
- `ntoskrnl!KeSetEvent` at `0x140001284`
- `ntoskrnl!KeSetEvent` at `0x140001284`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000120d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14000120d`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400010b2`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400010b2`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400010f6`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x1400010f6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001063`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001063`

## pseudocode

```c
void __fastcall RaidUnitPendingIrpDpcRoutine(
        struct _KDPC *Dpc,
        _QWORD *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  KIRQL v6; // al
  __int64 v7; // rdx
  int v8; // ecx
  ULONG MaximumProcessorCount; // eax
  int v10; // r8d
  ULONG v11; // r10d
  __int64 i; // r9
  __int64 v13; // rdx
  ULONG j; // r8d
  __int64 v15; // rcx
  bool v16; // dl
  char v17; // di
  ULONG k; // r8d
  __int64 v19; // rdx
  __int64 v20; // rsi
  unsigned __int8 v21; // di
  unsigned __int64 v22; // r8
  signed __int32 v23; // eax
  signed __int32 v24; // ett

  v4 = DeferredContext[8];
  if ( _bittest((const signed __int32 *)(*(_QWORD *)(v4 + 32) + 80LL), 8u)
    && !(unsigned __int8)RaUnitCheckForwardIoOutstanding(DeferredContext[8], DeferredContext) )
  {
    RaidStartNextIoPacket(v4, 0, 1);
  }
  v5 = *(_QWORD *)(v4 + 32);
  if ( (*(_DWORD *)(v5 + 80) & 1) != 0 )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 24));
    v7 = *(_QWORD *)(v4 + 32);
    v8 = *(_DWORD *)(v7 + 80);
    if ( (v8 & 0x100) == 0 )
    {
      *(_DWORD *)(v7 + 80) = v8 & 0xFFFFFDFF;
      KeReleaseSpinLock((PKSPIN_LOCK)(*(_QWORD *)(v4 + 32) + 24LL), v6);
      return;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 24), v6);
    goto LABEL_7;
  }
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  v10 = 0;
  v11 = 0;
  for ( i = MaximumProcessorCount;
        v11 < MaximumProcessorCount;
        v10 += _InterlockedExchange((volatile __int32 *)((v13 << 6) + *(_QWORD *)(v4 + 40) + 4), 0) / 2 )
  {
    v13 = v11++;
  }
  if ( 4 * v10 + _InterlockedExchangeAdd(*(volatile signed __int32 **)(v4 + 32), 4 * v10) )
  {
LABEL_7:
    KeSetCoalescableTimer(
      (PKTIMER)(*(_QWORD *)(v4 + 32) + 88LL),
      (LARGE_INTEGER)-2000000LL,
      0,
      0x32u,
      (PKDPC)(*(_QWORD *)(v4 + 32) + 152LL));
    return;
  }
  for ( j = 0; j < MaximumProcessorCount; ++j )
  {
    if ( _InterlockedCompareExchange(
           (volatile signed __int32 *)(((unsigned __int64)j << 6) + *(_QWORD *)(v4 + 40) + 4),
           1,
           0) )
    {
      while ( j )
        _InterlockedExchange((volatile __int32 *)(((unsigned __int64)--j << 6) + *(_QWORD *)(v4 + 40) + 4), 0);
      goto LABEL_7;
    }
  }
  v15 = *(_QWORD *)(v4 + 32);
  v16 = (*(_DWORD *)(v15 + 80) & 2) != 0;
  v17 = (*(_DWORD *)(v15 + 80) >> 1) & 2;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)v15, 1, 0) )
  {
    for ( k = 0; k < MaximumProcessorCount; ++k )
    {
      v19 = k;
      _InterlockedExchange((volatile __int32 *)((v19 << 6) + *(_QWORD *)(v4 + 40) + 4), 0);
    }
    goto LABEL_7;
  }
  v20 = *(_QWORD *)(v4 + 24);
  v21 = v16 | v17;
  if ( (v21 & 1) != 0 && (unsigned __int8)RaidUnitCheckAndAcquirePoFx(v4) )
  {
    PoFxIdleComponent(**(_QWORD **)(v4 + 1872), 0, 0);
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v4 + 1864));
  }
  if ( v21 >= 2u && *(_QWORD *)(v20 + 5024) )
    RaidAdapterPoFxIdleComponent(v20, 0, 0, i);
  v22 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
  v23 = *(_DWORD *)(v22 + *(_QWORD *)(v4 + 40));
  while ( (v23 & 1) == 0 )
  {
    v24 = v23;
    v23 = _InterlockedCompareExchange((volatile signed __int32 *)(v22 + *(_QWORD *)(v4 + 40)), v23 - 2, v23);
    if ( v24 == v23 )
      return;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 1032), 0xFFFFFFFF) == 1 )
    KeSetEvent((PRKEVENT)(v4 + 520), 0, 0);
}

```

## disassembly

```asm
0x140001010  mov     [rsp+arg_0], rbx
0x140001015  mov     [rsp+arg_10], rbp
0x14000101a  push    rsi
0x14000101b  push    rdi
0x14000101c  push    r14
0x14000101e  sub     rsp, 30h
0x140001022  mov     rbx, [rdx+40h]
0x140001026  mov     ebp, 1
0x14000102b  mov     rax, [rbx+20h]
0x14000102f  bt      dword ptr [rax+50h], 8
0x140001034  jnb     short loc_14000104F
0x140001036  mov     rcx, rbx
0x140001039  call    RaUnitCheckForwardIoOutstanding
0x14000103e  test    al, al
0x140001040  jnz     short loc_14000104F
0x140001042  mov     r8d, ebp
0x140001045  xor     edx, edx
0x140001047  mov     rcx, rbx
0x14000104a  call    RaidStartNextIoPacket
0x14000104f  mov     rcx, [rbx+20h]
0x140001053  mov     eax, [rcx+50h]
0x140001056  test    bpl, al
0x140001059  jz      loc_1400010F1
0x14000105f  add     rcx, 18h; SpinLock
0x140001063  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000106a  nop     dword ptr [rax+rax+00h]
0x14000106f  mov     rdx, [rbx+20h]
0x140001073  mov     ecx, [rdx+50h]
0x140001076  bt      ecx, 8
0x14000107a  jnb     short loc_1400010D2
0x14000107c  lea     rcx, [rdx+18h]; SpinLock
0x140001080  mov     dl, al; NewIrql
0x140001082  call    cs:__imp_KeReleaseSpinLock
0x140001089  nop     dword ptr [rax+rax+00h]
0x14000108e  mov     rcx, [rbx+20h]
0x140001092  mov     r9d, 32h ; '2'; TolerableDelay
0x140001098  xor     r8d, r8d; Period
0x14000109b  mov     rdx, 0FFFFFFFFFFE17B80h; DueTime
0x1400010a2  lea     rax, [rcx+98h]
0x1400010a9  add     rcx, 58h ; 'X'; Timer
0x1400010ad  mov     [rsp+48h+Dpc], rax; Dpc
0x1400010b2  call    cs:__imp_KeSetCoalescableTimer
0x1400010b9  nop     dword ptr [rax+rax+00h]
0x1400010be  mov     rbx, [rsp+48h+arg_0]
0x1400010c3  mov     rbp, [rsp+48h+arg_10]
0x1400010c8  add     rsp, 30h
0x1400010cc  pop     r14
0x1400010ce  pop     rdi
0x1400010cf  pop     rsi
0x1400010d0  retn
0x1400010d2  btr     ecx, 9
0x1400010d6  mov     [rdx+50h], ecx
0x1400010d9  mov     dl, al; NewIrql
0x1400010db  mov     rcx, [rbx+20h]
0x1400010df  add     rcx, 18h; SpinLock
0x1400010e3  call    cs:__imp_KeReleaseSpinLock
0x1400010ea  nop     dword ptr [rax+rax+00h]
0x1400010ef  jmp     short loc_1400010BE
0x1400010f1  mov     ecx, 0FFFFh; GroupNumber
0x1400010f6  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x1400010fd  nop     dword ptr [rax+rax+00h]
0x140001102  xor     r8d, r8d
0x140001105  xor     r10d, r10d
0x140001108  mov     r9d, eax
0x14000110b  lea     r14d, [r8+2]
0x14000110f  test    eax, eax
0x140001111  jz      short loc_140001133
0x140001113  mov     rcx, [rbx+28h]
0x140001117  xor     eax, eax
0x140001119  mov     edx, r10d
0x14000111c  add     r10d, ebp
0x14000111f  shl     rdx, 6
0x140001123  xchg    eax, [rdx+rcx+4]
0x140001127  cdq
0x140001128  idiv    r14d
0x14000112b  add     r8d, eax
0x14000112e  cmp     r10d, r9d
0x140001131  jb      short loc_140001113
0x140001133  mov     rax, [rbx+20h]
0x140001137  lea     edx, ds:0[r8*4]
0x14000113f  mov     ecx, edx
0x140001141  lock xadd [rax], ecx
0x140001145  lea     eax, [rdx+rcx]
0x140001148  test    eax, eax
0x14000114a  jnz     loc_14000108E
0x140001150  xor     r8d, r8d
0x140001153  xor     eax, eax
0x140001155  cmp     r8d, r9d
0x140001158  jnb     short loc_140001190
0x14000115a  mov     rcx, [rbx+28h]
0x14000115e  mov     edx, r8d
0x140001161  shl     rdx, 6
0x140001165  lock cmpxchg [rdx+rcx+4], ebp
0x14000116b  jnz     short loc_140001186
0x14000116d  add     r8d, ebp
0x140001170  jmp     short loc_140001153
0x140001172  mov     rcx, [rbx+28h]
0x140001176  dec     r8d
0x140001179  mov     edx, r8d
0x14000117c  shl     rdx, 6
0x140001180  xor     eax, eax
0x140001182  xchg    eax, [rdx+rcx+4]
0x140001186  test    r8d, r8d
0x140001189  jnz     short loc_140001172
0x14000118b  jmp     loc_14000108E
0x140001190  mov     rcx, [rbx+20h]
0x140001194  mov     edi, [rcx+50h]
0x140001197  mov     edx, edi
0x140001199  shr     edx, 1
0x14000119b  and     dl, bpl
0x14000119e  shr     edi, 1
0x1400011a0  and     dil, r14b
0x1400011a3  lock cmpxchg [rcx], ebp
0x1400011a7  jz      short loc_1400011D3
0x1400011a9  xor     r8d, r8d
0x1400011ac  test    r9d, r9d
0x1400011af  jz      loc_14000108E
0x1400011b5  mov     rcx, [rbx+28h]
0x1400011b9  xor     eax, eax
0x1400011bb  mov     edx, r8d
0x1400011be  add     r8d, ebp
0x1400011c1  shl     rdx, 6
0x1400011c5  xchg    eax, [rdx+rcx+4]
0x1400011c9  cmp     r8d, r9d
0x1400011cc  jb      short loc_1400011B5
0x1400011ce  jmp     loc_14000108E
0x1400011d3  mov     rsi, [rbx+18h]
0x1400011d7  or      dil, dl
0x1400011da  test    bpl, dil
0x1400011dd  jz      short loc_140001219
0x1400011df  mov     rcx, rbx
0x1400011e2  call    RaidUnitCheckAndAcquirePoFx
0x1400011e7  test    al, al
0x1400011e9  jz      short loc_140001219
0x1400011eb  mov     rcx, [rbx+750h]
0x1400011f2  xor     r8d, r8d
0x1400011f5  xor     edx, edx
0x1400011f7  mov     rcx, [rcx]
0x1400011fa  call    cs:__imp_PoFxIdleComponent
0x140001201  nop     dword ptr [rax+rax+00h]
0x140001206  mov     rcx, [rbx+748h]; RunRefCacheAware
0x14000120d  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140001214  nop     dword ptr [rax+rax+00h]
0x140001219  cmp     dil, r14b
0x14000121c  jb      short loc_140001235
0x14000121e  cmp     qword ptr [rsi+13A0h], 0
0x140001226  jz      short loc_140001235
0x140001228  xor     r8d, r8d
0x14000122b  xor     edx, edx
0x14000122d  mov     rcx, rsi
0x140001230  call    RaidAdapterPoFxIdleComponent
0x140001235  mov     eax, gs:1A4h
0x14000123d  mov     r8d, eax
0x140001240  mov     rax, [rbx+28h]
0x140001244  shl     r8, 6
0x140001248  mov     eax, [r8+rax]
0x14000124c  test    bpl, al
0x14000124f  jnz     short loc_140001265
0x140001251  mov     rcx, [rbx+28h]
0x140001255  lea     edx, [rax-2]
0x140001258  lock cmpxchg [r8+rcx], edx
0x14000125e  jnz     short loc_14000124C
0x140001260  jmp     loc_1400010BE
0x140001265  or      eax, 0FFFFFFFFh
0x140001268  lock xadd [rbx+408h], eax
0x140001270  cmp     eax, ebp
0x140001272  jnz     loc_1400010BE
0x140001278  lea     rcx, [rbx+208h]; Event
0x14000127f  xor     r8d, r8d; Wait
0x140001282  xor     edx, edx; Increment
0x140001284  call    cs:__imp_KeSetEvent
0x14000128b  nop     dword ptr [rax+rax+00h]
0x140001290  jmp     loc_1400010BE
```
