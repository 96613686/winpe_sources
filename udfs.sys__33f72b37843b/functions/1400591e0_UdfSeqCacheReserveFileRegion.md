# UdfSeqCacheReserveFileRegion

- ea: `0x1400591e0`
- end: `0x14005953a`
- name: `UdfSeqCacheReserveFileRegion`
- size: `858`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1400010f0`
- `0x140004514`
- `0x140007b90`
- `0x14000b2b0`
- `0x1400121e0`
- `0x140041110`
- `0x14004d45c`
- `0x140051d74`

## callees

- `0x14000ed4c`
- `0x14001c080`
- `0x1400591e0`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x1400593b3`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x1400593b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400592a4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400592a4`
- `ntoskrnl!ExRaiseStatus` at `0x140059378`
- `ntoskrnl!ExRaiseStatus` at `0x140059505`
- `ntoskrnl!ExRaiseStatus` at `0x140059378`
- `ntoskrnl!ExRaiseStatus` at `0x140059505`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400594de`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b113`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400594de`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005b113`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005935f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005935f`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400592d9`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400592d9`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14005949b`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x14005949b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140059414`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140059414`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140059478`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400594ca`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140059478`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400594ca`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x1400592f1`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x1400592f1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140059267`
- `ntoskrnl!ExAcquireFastMutex` at `0x140059267`
- `ntoskrnl!ExReleaseFastMutex` at `0x140059336`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005b0e8`
- `ntoskrnl!ExReleaseFastMutex` at `0x140059336`
- `ntoskrnl!ExReleaseFastMutex` at `0x14005b0e8`

## pseudocode

```c
__int64 __fastcall UdfSeqCacheReserveFileRegion(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        char a6,
        char a7)
{
  __int64 v9; // rbx
  __int64 v11; // r14
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v13; // rcx
  struct _ERESOURCE *PoolWithTag; // rax
  struct _ERESOURCE *v15; // rdi
  __int64 v16; // rax
  LARGE_MCB *v17; // rdi
  BOOLEAN v18; // al
  unsigned int v19; // edi
  unsigned int v20; // eax
  __int64 v21; // r10
  unsigned int v22; // r9d
  struct _FAST_MUTEX *v23; // rcx
  __int64 Lbn; // [rsp+50h] [rbp-38h] BYREF
  PLARGE_MCB Mcb; // [rsp+58h] [rbp-30h]
  __int64 SectorCountFromLbn; // [rsp+90h] [rbp+8h] BYREF
  __int64 v28; // [rsp+98h] [rbp+10h]

  v28 = a2;
  v9 = a2;
  v11 = *(_QWORD *)(a1 + 16);
  Lbn = 0;
  SectorCountFromLbn = 0;
  if ( (*(_DWORD *)(a2 + 212) & 0x8000000) != 0 )
  {
    v9 = *(_QWORD *)(v11 + 320);
    v28 = v9;
  }
  if ( (*(_DWORD *)(v9 + 212) & 0x4000000) == 0 )
  {
    CurrentThread = KeGetCurrentThread();
    v13 = *(_QWORD *)(v9 + 136);
    if ( CurrentThread != *(struct _KTHREAD **)(v13 + 64) )
    {
      ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(v13 + 80) + 216LL));
      *(_QWORD *)(*(_QWORD *)(v9 + 136) + 64LL) = CurrentThread;
    }
    ++*(_DWORD *)(*(_QWORD *)(v9 + 136) + 72LL);
    if ( (*(_DWORD *)(v9 + 212) & 0x4000000) == 0 )
    {
      PoolWithTag = (struct _ERESOURCE *)ExAllocatePoolWithTag((POOL_TYPE)1552, 0x68u, 0x52666455u);
      v15 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
        memset(PoolWithTag, 0, sizeof(struct _ERESOURCE));
      *(_QWORD *)(v9 + 336) = v15;
      ExInitializeResourceLite(v15);
      FsRtlInitializeLargeMcb((PLARGE_MCB)(v9 + 344), PagedPool);
      *(_DWORD *)(v9 + 212) |= 0x4000000u;
    }
    --*(_DWORD *)(*(_QWORD *)(v9 + 136) + 72LL);
    v16 = *(_QWORD *)(v9 + 136);
    if ( !*(_DWORD *)(v16 + 72) )
    {
      *(_QWORD *)(v16 + 64) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(*(_QWORD *)(v9 + 136) + 80LL) + 216LL));
    }
  }
  v17 = (LARGE_MCB *)(v9 + 344);
  Mcb = (PLARGE_MCB)(v9 + 344);
  if ( !ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v9 + 336), (*(_DWORD *)(a1 + 28) & 4) != 0) )
  {
    *(_DWORD *)(a1 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  while ( 1 )
  {
    v18 = FsRtlLookupLargeMcbEntry(v17, a3, &Lbn, &SectorCountFromLbn, 0, 0, 0);
    if ( v18 )
    {
      v19 = SectorCountFromLbn;
      if ( a4 < (unsigned int)SectorCountFromLbn )
        v19 = a4;
    }
    else
    {
      v19 = a4;
    }
    if ( !v18 || Lbn == -1 )
      break;
LABEL_33:
    a4 -= v19;
    a3 += v19;
    if ( !a4 )
      goto LABEL_36;
    v17 = Mcb;
  }
  if ( a5 )
  {
    v20 = *a5;
    if ( *a5 )
    {
      if ( v19 > v20 )
        v19 = *a5;
      *a5 = v20 - v19;
      goto LABEL_32;
    }
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v11 + 1584));
  *(_QWORD *)(v11 + 1640) = KeGetCurrentThread();
  v21 = 0;
  if ( a7 )
    v22 = UdfAvailableFreeBlocks(v11, 0);
  else
    v22 = *(_DWORD *)(v11 + 668) - *(_DWORD *)(v11 + 672);
  v23 = (struct _FAST_MUTEX *)(v11 + 1584);
  if ( v22 >= v19 )
  {
    *(_DWORD *)(v11 + 672) += v19;
    *(_QWORD *)(v11 + 1640) = v21;
    ExReleaseFastMutexUnsafe(v23);
LABEL_32:
    *(_DWORD *)(v9 + 328) += v19;
    FsRtlAddLargeMcbEntry(Mcb, a3, 1, v19);
    goto LABEL_33;
  }
  *(_QWORD *)(v11 + 1640) = v21;
  ExReleaseFastMutexUnsafe(v23);
LABEL_36:
  ExReleaseResourceLite(*(PERESOURCE *)(v9 + 336));
  if ( a4 && !a6 )
  {
    *(_DWORD *)(a1 + 24) = -1073741697;
    ExRaiseStatus(-1073741697);
  }
  return a4 != 0 ? 0xC000007F : 0;
}

```

## disassembly

```asm
0x1400591e0  mov     rax, rsp
0x1400591e3  mov     [rax+18h], rbx
0x1400591e7  mov     [rax+20h], rsi
0x1400591eb  mov     [rax+10h], rdx
0x1400591ef  push    rdi
0x1400591f0  push    r12
0x1400591f2  push    r13
0x1400591f4  push    r14
0x1400591f6  push    r15
0x1400591f8  sub     rsp, 60h
0x1400591fc  mov     esi, r9d
0x1400591ff  mov     r12d, r8d
0x140059202  mov     rbx, rdx
0x140059205  mov     r13, rcx
0x140059208  mov     r14, [rcx+10h]
0x14005920c  mov     qword ptr [rax-38h], 0
0x140059214  mov     qword ptr [rax+8], 0
0x14005921c  test    dword ptr [rdx+0D4h], 8000000h
0x140059226  jz      short loc_140059233
0x140059228  mov     rbx, [r14+140h]
0x14005922f  mov     [rax+10h], rbx
0x140059233  mov     r15, rbx
0x140059236  test    dword ptr [rbx+0D4h], 4000000h
0x140059240  jnz     loc_140059342
0x140059246  mov     rdi, gs:188h
0x14005924f  mov     rcx, [rbx+88h]
0x140059256  cmp     rdi, [rcx+40h]
0x14005925a  jz      short loc_14005927E
0x14005925c  mov     rcx, [rcx+50h]
0x140059260  add     rcx, 0D8h; FastMutex
0x140059267  call    cs:__imp_ExAcquireFastMutex
0x14005926e  nop     dword ptr [rax+rax+00h]
0x140059273  mov     rax, [rbx+88h]
0x14005927a  mov     [rax+40h], rdi
0x14005927e  mov     rax, [rbx+88h]
0x140059285  inc     dword ptr [rax+48h]
0x140059288  test    dword ptr [rbx+0D4h], 4000000h
0x140059292  jnz     short loc_140059305
0x140059294  mov     edx, 68h ; 'h'; NumberOfBytes
0x140059299  mov     ecx, 610h; PoolType
0x14005929e  mov     r8d, 52666455h; Tag
0x1400592a4  call    cs:__imp_ExAllocatePoolWithTag
0x1400592ab  nop     dword ptr [rax+rax+00h]
0x1400592b0  mov     rdi, rax
0x1400592b3  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400592ba  jnz     short loc_1400592CF
0x1400592bc  test    rax, rax
0x1400592bf  jz      short loc_1400592CF
0x1400592c1  xor     edx, edx; Val
0x1400592c3  lea     r8d, [rdx+68h]; Size
0x1400592c7  mov     rcx, rax; void *
0x1400592ca  call    memset
0x1400592cf  mov     [rbx+150h], rdi
0x1400592d6  mov     rcx, rdi; Resource
0x1400592d9  call    cs:__imp_ExInitializeResourceLite
0x1400592e0  nop     dword ptr [rax+rax+00h]
0x1400592e5  lea     rcx, [rbx+158h]; Mcb
0x1400592ec  mov     edx, 1; PoolType
0x1400592f1  call    cs:__imp_FsRtlInitializeLargeMcb
0x1400592f8  nop     dword ptr [rax+rax+00h]
0x1400592fd  bts     dword ptr [rbx+0D4h], 1Ah
0x140059305  mov     rax, [rbx+88h]
0x14005930c  dec     dword ptr [rax+48h]
0x14005930f  mov     rax, [rbx+88h]
0x140059316  cmp     dword ptr [rax+48h], 0
0x14005931a  jnz     short loc_140059342
0x14005931c  mov     qword ptr [rax+40h], 0
0x140059324  mov     rax, [rbx+88h]
0x14005932b  mov     rcx, [rax+50h]
0x14005932f  add     rcx, 0D8h; FastMutex
0x140059336  call    cs:__imp_ExReleaseFastMutex
0x14005933d  nop     dword ptr [rax+rax+00h]
0x140059342  lea     rdi, [r15+158h]
0x140059349  mov     [rsp+88h+Mcb], rdi
0x14005934e  mov     edx, [r13+1Ch]
0x140059352  shr     edx, 2
0x140059355  and     dl, 1; Wait
0x140059358  mov     rcx, [rbx+150h]; Resource
0x14005935f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140059366  nop     dword ptr [rax+rax+00h]
0x14005936b  test    al, al
0x14005936d  jnz     short loc_140059385
0x14005936f  mov     ecx, 0C00000D8h; Status
0x140059374  mov     [r13+18h], ecx
0x140059378  call    cs:__imp_ExRaiseStatus
0x140059385  mov     edx, r12d; Vbn
0x140059388  mov     [rsp+88h+Index], 0; Index
0x140059391  mov     [rsp+88h+SectorCountFromStartingLbn], 0; SectorCountFromStartingLbn
0x14005939a  mov     [rsp+88h+StartingLbn], 0; StartingLbn
0x1400593a3  lea     r9, [rsp+88h+SectorCountFromLbn]; SectorCountFromLbn
0x1400593ab  lea     r8, [rsp+88h+Lbn]; Lbn
0x1400593b0  mov     rcx, rdi; Mcb
0x1400593b3  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x1400593ba  nop     dword ptr [rax+rax+00h]
0x1400593bf  test    al, al
0x1400593c1  jz      short loc_1400593D2
0x1400593c3  mov     rdi, [rsp+88h+SectorCountFromLbn]
0x1400593cb  cmp     esi, edi
0x1400593cd  cmovb   edi, esi
0x1400593d0  jmp     short loc_1400593D4
0x1400593d2  mov     edi, esi
0x1400593d4  mov     [rsp+88h+var_48], edi
0x1400593d8  test    al, al
0x1400593da  jz      short loc_1400593E8
0x1400593dc  cmp     [rsp+88h+Lbn], 0FFFFFFFFFFFFFFFFh
0x1400593e2  jnz     loc_1400594A7
0x1400593e8  mov     rcx, [rsp+88h+arg_20]
0x1400593f0  test    rcx, rcx
0x1400593f3  jz      short loc_14005940A
0x1400593f5  mov     eax, [rcx]
0x1400593f7  test    eax, eax
0x1400593f9  jz      short loc_14005940A
0x1400593fb  cmp     edi, eax
0x1400593fd  cmova   edi, eax
0x140059400  mov     [rsp+88h+var_48], edi
0x140059404  sub     eax, edi
0x140059406  mov     [rcx], eax
0x140059408  jmp     short loc_140059484
0x14005940a  lea     r15, [r14+630h]
0x140059411  mov     rcx, r15; FastMutex
0x140059414  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14005941b  nop     dword ptr [rax+rax+00h]
0x140059420  mov     rax, gs:188h
0x140059429  mov     [r14+668h], rax
0x140059430  xor     r10d, r10d
0x140059433  cmp     [rsp+88h+arg_30], r10b
0x14005943b  jz      short loc_14005944C
0x14005943d  xor     edx, edx
0x14005943f  mov     rcx, r14
0x140059442  call    UdfAvailableFreeBlocks
0x140059447  mov     r9d, eax
0x14005944a  jmp     short loc_14005945D
0x14005944c  mov     eax, [r14+2A0h]
0x140059453  mov     r9d, [r14+29Ch]
0x14005945a  sub     r9d, eax
0x14005945d  cmp     r9d, edi
0x140059460  setnb   al
0x140059463  mov     rcx, r15; FastMutex
0x140059466  test    al, al
0x140059468  jz      short loc_1400594C3
0x14005946a  add     [r14+2A0h], edi
0x140059471  mov     [r14+668h], r10
0x140059478  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005947f  nop     dword ptr [rax+rax+00h]
0x140059484  add     [rbx+148h], edi
0x14005948a  mov     r9d, edi; SectorCount
0x14005948d  mov     r8d, 1; Lbn
0x140059493  mov     edx, r12d; Vbn
0x140059496  mov     rcx, [rsp+88h+Mcb]; Mcb
0x14005949b  call    cs:__imp_FsRtlAddLargeMcbEntry
0x1400594a2  nop     dword ptr [rax+rax+00h]
0x1400594a7  sub     esi, edi
0x1400594a9  mov     [rsp+88h+var_44], esi
0x1400594ad  add     r12d, edi
0x1400594b0  mov     [rsp+88h+var_40], r12d
0x1400594b5  test    esi, esi
0x1400594b7  jz      short loc_1400594D7
0x1400594b9  mov     rdi, [rsp+88h+Mcb]
0x1400594be  jmp     loc_140059385
0x1400594c3  mov     [r14+668h], r10
0x1400594ca  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400594d1  nop     dword ptr [rax+rax+00h]
0x1400594d6  nop
0x1400594d7  mov     rcx, [rbx+150h]; Resource
0x1400594de  call    cs:__imp_ExReleaseResourceLite
0x1400594e5  nop     dword ptr [rax+rax+00h]
0x1400594ea  test    esi, esi
0x1400594ec  jz      short loc_140059512
0x1400594ee  cmp     [rsp+88h+arg_28], 0
0x1400594f6  jnz     short loc_140059512
0x1400594f8  mov     dword ptr [r13+18h], 0C000007Fh
0x140059500  mov     ecx, 0C000007Fh; Status
0x140059505  call    cs:__imp_ExRaiseStatus
0x140059512  xor     eax, eax
0x140059514  sub     eax, esi
0x140059516  neg     eax
0x140059518  sbb     eax, eax
0x14005951a  and     eax, 0C000007Fh
0x14005951f  lea     r11, [rsp+88h+var_28]
0x140059524  mov     rbx, [r11+40h]
0x140059528  mov     rsi, [r11+48h]
0x14005952c  mov     rsp, r11
0x14005952f  pop     r15
0x140059531  pop     r14
0x140059533  pop     r13
0x140059535  pop     r12
0x140059537  pop     rdi
0x140059538  retn
0x14005b0a2  push    rbp
0x14005b0a4  sub     rsp, 40h
0x14005b0a8  mov     rbp, rdx
0x14005b0ab  mov     rdx, [rbp+98h]
0x14005b0b2  mov     rax, [rdx+88h]
0x14005b0b9  mov     ecx, [rax+48h]
0x14005b0bc  dec     ecx
0x14005b0be  mov     [rax+48h], ecx
0x14005b0c1  mov     rax, [rdx+88h]
0x14005b0c8  cmp     dword ptr [rax+48h], 0
0x14005b0cc  jnz     short loc_14005B0F5
0x14005b0ce  mov     qword ptr [rax+40h], 0
0x14005b0d6  mov     rax, [rdx+88h]
0x14005b0dd  mov     rcx, [rax+50h]
0x14005b0e1  add     rcx, 0D8h; FastMutex
0x14005b0e8  call    cs:__imp_ExReleaseFastMutex
0x14005b0ef  nop     dword ptr [rax+rax+00h]
0x14005b0f4  nop
0x14005b0f5  add     rsp, 40h
0x14005b0f9  pop     rbp
0x14005b0fa  retn
0x14005b0fc  push    rbp
0x14005b0fe  sub     rsp, 40h
0x14005b102  mov     rbp, rdx
0x14005b105  mov     rcx, [rbp+98h]
0x14005b10c  mov     rcx, [rcx+150h]; Resource
0x14005b113  call    cs:__imp_ExReleaseResourceLite
0x14005b11a  nop     dword ptr [rax+rax+00h]
0x14005b11f  nop
0x14005b120  add     rsp, 40h
0x14005b124  pop     rbp
0x14005b125  retn
```
