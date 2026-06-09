# NvmeAdapterStop

- ea: `0x1400ff204`
- end: `0x1400ff6ea`
- name: `NvmeAdapterStop`
- size: `1254`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1401391b8`
- `0x1401a8144`
- `0x1401a8f14`

## callees

- `0x140076c38`
- `0x140076f84`
- `0x140077470`
- `0x14009d768`
- `0x1400f4674`
- `0x1400f8094`
- `0x1400fa1d0`
- `0x1400fc9a0`
- `0x1400ff204`
- `0x1400ff6f0`
- `0x140100b40`
- `0x1401164c4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ff449`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ff48c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ff4dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ff449`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ff48c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ff4dd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ff4f3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ff4f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ff61b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ff65c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ff69b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ff61b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ff65c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ff69b`
- `ntoskrnl!KeCancelTimer` at `0x1400ff278`
- `ntoskrnl!KeCancelTimer` at `0x1400ff357`
- `ntoskrnl!KeCancelTimer` at `0x1400ff546`
- `ntoskrnl!KeCancelTimer` at `0x1400ff278`
- `ntoskrnl!KeCancelTimer` at `0x1400ff357`
- `ntoskrnl!KeCancelTimer` at `0x1400ff546`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400ff638`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400ff678`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400ff638`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400ff678`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ff627`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ff668`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ff6a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ff627`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ff668`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400ff6a7`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400ff293`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400ff372`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400ff561`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400ff293`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400ff372`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400ff561`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400ff45b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400ff4a1`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400ff45b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400ff4a1`

## pseudocode

```c
__int64 __fastcall NvmeAdapterStop(__int64 a1, int a2)
{
  __int64 v2; // rax
  int v3; // esi
  __int64 v6; // rbx
  int v7; // ecx
  int v8; // eax
  unsigned int v9; // r14d
  char v10; // r13
  _QWORD *v11; // r15
  _QWORD *v12; // rbx
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // rcx
  _QWORD *v17; // r15
  _QWORD *v18; // rbx
  struct _ERESOURCE *v19; // r13
  struct _ERESOURCE *Flink; // r12
  __int64 v21; // r9
  __int64 *v22; // rbx
  __int64 *v23; // rdx
  __int64 *v24; // r13
  __int64 v25; // rax
  __int64 *v26; // rcx
  __int64 **v27; // rax
  __int64 *v29; // [rsp+80h] [rbp+18h]
  struct _ERESOURCE *v30; // [rsp+88h] [rbp+20h]

  v2 = *(_QWORD *)(a1 + 408);
  v3 = 0;
  if ( !v2 || !*(_QWORD *)(a1 + 416) )
    return (unsigned int)v3;
  if ( (*(_DWORD *)(v2 + 184) & 0x40000000) != 0 )
  {
    v6 = *(_QWORD *)(a1 + 1152);
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 1312) + 40LL) + 192LL) )
    {
      KeCancelTimer((PKTIMER)(*(_QWORD *)(*(_QWORD *)(v6 + 1312) + 40LL) + 128LL));
      KeRemoveQueueDpc((PRKDPC)(*(_QWORD *)(*(_QWORD *)(v6 + 1312) + 40LL) + 64LL));
      _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v6 + 1312) + 40LL) + 192LL), 0, 1);
    }
    if ( a2 != 2 )
      NvmeControllerTerminateCommandTimeoutDetectThread(*(_QWORD *)(a1 + 1152));
    v7 = *(_DWORD *)(a1 + 84);
    if ( (unsigned int)(v7 - 5) <= 1 )
    {
      v8 = NvmeControllerRemove(*(_QWORD *)(a1 + 1152));
    }
    else
    {
      if ( v7 != 8 )
        goto LABEL_53;
      v8 = NvmeControllerStop(*(_QWORD *)(a1 + 1152));
    }
    v3 = v8;
    if ( v8 >= 0 )
      goto LABEL_53;
    return (unsigned int)v3;
  }
  if ( (*(_DWORD *)(a1 + 424) & 0x40) == 0 )
  {
    v15 = *(_QWORD *)(a1 + 616);
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)(v15 + 24), 1u);
    v16 = *(_QWORD *)(a1 + 616);
    v17 = *(_QWORD **)v16;
    while ( v17 != (_QWORD *)v16 )
    {
      v18 = v17 - 3;
      v3 = NvmeAdapterHostGatewayAcquireRundown(v17 - 3);
      if ( v3 >= 0 )
      {
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite((PERESOURCE)(v18 + 48), 1u);
        v19 = (struct _ERESOURCE *)(v18 + 45);
        Flink = (struct _ERESOURCE *)v18[45];
        v30 = (struct _ERESOURCE *)(v18 + 45);
        if ( Flink != (struct _ERESOURCE *)(v18 + 45) )
        {
          do
          {
            v3 = NvmeAdapterSubsystemPortAcquireRundown(&Flink[-1].SpinLock);
            if ( v3 >= 0 )
            {
              KeEnterCriticalRegion();
              ExAcquireResourceExclusiveLite(Flink + 6, 1u);
              v22 = *(__int64 **)&Flink[5].MiscFlags;
              if ( v22 != (__int64 *)&Flink[5].MiscFlags )
              {
                do
                {
                  v23 = (__int64 *)*v22;
                  v24 = v22 - 8;
                  v29 = (__int64 *)*v22;
                  if ( *(_DWORD *)(*(_QWORD *)(v22[156] + 40) + 192LL) )
                  {
                    KeCancelTimer((PKTIMER)(*(_QWORD *)(v24[164] + 40) + 128LL));
                    KeRemoveQueueDpc((PRKDPC)(*(_QWORD *)(v24[164] + 40) + 64LL));
                    _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v24[164] + 40) + 192LL), 0, 1);
                    v23 = v29;
                  }
                  v25 = v24[17];
                  *((_DWORD *)v24 + 142) = 3;
                  if ( (v25 & 1) == 0 )
                  {
                    v24[17] = v25 | 8;
                    v26 = (__int64 *)*v22;
                    if ( *(__int64 **)(*v22 + 8) != v22 || (v27 = (__int64 **)v22[1], *v27 != v22) )
                      __fastfail(3u);
                    *v27 = v26;
                    v26[1] = (__int64)v27;
                    --LODWORD(Flink[5].SpinLock);
                  }
                  v22 = v23;
                  LOBYTE(v21) = (v24[17] & 1) == 0;
                  NvmeAdapterDisconnectFabricsControllerInternal(
                    a1,
                    v24,
                    (char *)&Flink->OwnerEntry.OwnerThread + 4,
                    v21);
                }
                while ( v22 != (__int64 *)&Flink[5].MiscFlags );
                v19 = v30;
              }
              ExReleaseResourceLite(Flink + 6);
              KeLeaveCriticalRegion();
              ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)Flink->SharedWaiters);
            }
            Flink = (struct _ERESOURCE *)Flink->SystemResourcesList.Flink;
          }
          while ( Flink != v19 );
          v18 = v17 - 3;
        }
        ExReleaseResourceLite((PERESOURCE)(v18 + 48));
        KeLeaveCriticalRegion();
        ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v18[7]);
      }
      v17 = (_QWORD *)*v17;
      v16 = *(_QWORD *)(a1 + 616);
    }
    ExReleaseResourceLite((PERESOURCE)(v16 + 24));
    KeLeaveCriticalRegion();
    goto LABEL_53;
  }
  v9 = 0;
  NvmeAdapterAcquireStorMQControllerListLockShared();
  v10 = 0;
  v11 = *(_QWORD **)(a1 + 1200);
  while ( v11 != (_QWORD *)(a1 + 1200) )
  {
    v12 = v11 - 14;
    if ( *(_DWORD *)(*(_QWORD *)(v11[150] + 40LL) + 192LL) )
    {
      KeCancelTimer((PKTIMER)(*(_QWORD *)(v12[164] + 40LL) + 128LL));
      KeRemoveQueueDpc((PRKDPC)(*(_QWORD *)(v12[164] + 40LL) + 64LL));
      _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v12[164] + 40LL) + 192LL), 0, 1);
    }
    NvmeControllerTerminateCommandTimeoutDetectThread(v11 - 14);
    v13 = *(_DWORD *)(a1 + 84);
    if ( (unsigned int)(v13 - 5) <= 1 )
    {
      NvmeControllerSetStorMQProperty(v11 - 14, 2147483657LL, 4);
      v3 = NvmeControllerRemove((int)v11 - 112);
      if ( v3 >= 0 )
        goto LABEL_27;
      *((_DWORD *)v12 + 304) = 48;
    }
    else if ( v13 == 8 )
    {
      v3 = NvmeControllerStop((int)v11 - 112);
      if ( v3 >= 0 )
        goto LABEL_27;
      *((_DWORD *)v12 + 304) = 47;
    }
    else if ( v3 >= 0 )
    {
      goto LABEL_27;
    }
    v10 = 1;
LABEL_27:
    v11 = (_QWORD *)*v11;
    v14 = v3;
    if ( v3 >= 0 )
      v14 = v9;
    v9 = v14;
  }
  NvmeAdapterReleaseStorMQControllerListLockShared(a1);
  if ( v10 )
    return v9;
LABEL_53:
  if ( (unsigned __int8)NvmeIsAdapterControlSupported(a1 + 176, 1) )
    return (unsigned int)NvmeAdapterStopAdapter(a1);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400ff204  push    rbx
0x1400ff206  push    rsi
0x1400ff207  push    rdi
0x1400ff208  push    r12
0x1400ff20a  push    r13
0x1400ff20c  push    r14
0x1400ff20e  push    r15
0x1400ff210  sub     rsp, 30h
0x1400ff214  mov     rax, [rcx+198h]
0x1400ff21b  xor     esi, esi
0x1400ff21d  mov     [rsp+68h+arg_0], esi
0x1400ff221  mov     r14d, edx
0x1400ff224  mov     rdi, rcx
0x1400ff227  test    rax, rax
0x1400ff22a  jz      loc_1400FF6D2
0x1400ff230  cmp     [rcx+1A0h], rsi
0x1400ff237  jz      loc_1400FF6D2
0x1400ff23d  test    dword ptr [rax+0B8h], 40000000h
0x1400ff247  jz      loc_1400FF306
0x1400ff24d  mov     rbx, [rcx+480h]
0x1400ff254  mov     rax, [rbx+520h]
0x1400ff25b  mov     rcx, [rax+28h]
0x1400ff25f  mov     eax, [rcx+0C0h]
0x1400ff265  test    eax, eax
0x1400ff267  jz      short loc_1400FF2B7
0x1400ff269  mov     rax, [rbx+520h]
0x1400ff270  mov     rcx, [rax+28h]
0x1400ff274  sub     rcx, 0FFFFFFFFFFFFFF80h; PKTIMER
0x1400ff278  call    cs:__imp_KeCancelTimer
0x1400ff27f  nop     dword ptr [rax+rax+00h]
0x1400ff284  mov     rax, [rbx+520h]
0x1400ff28b  mov     rcx, [rax+28h]
0x1400ff28f  add     rcx, 40h ; '@'; Dpc
0x1400ff293  call    cs:__imp_KeRemoveQueueDpc
0x1400ff29a  nop     dword ptr [rax+rax+00h]
0x1400ff29f  mov     rax, [rbx+520h]
0x1400ff2a6  xor     ecx, ecx
0x1400ff2a8  mov     rdx, [rax+28h]
0x1400ff2ac  lea     eax, [rsi+1]
0x1400ff2af  lock cmpxchg [rdx+0C0h], ecx
0x1400ff2b7  cmp     r14d, 2
0x1400ff2bb  jz      short loc_1400FF2C9
0x1400ff2bd  mov     rcx, [rdi+480h]
0x1400ff2c4  call    NvmeControllerTerminateCommandTimeoutDetectThread
0x1400ff2c9  mov     ecx, [rdi+54h]
0x1400ff2cc  lea     eax, [rcx-5]
0x1400ff2cf  cmp     eax, 1
0x1400ff2d2  jbe     short loc_1400FF2EB
0x1400ff2d4  cmp     ecx, 8
0x1400ff2d7  jnz     loc_1400FF6B3
0x1400ff2dd  mov     rcx, [rdi+480h]; int
0x1400ff2e4  call    NvmeControllerStop
0x1400ff2e9  jmp     short loc_1400FF2F7
0x1400ff2eb  mov     rcx, [rdi+480h]; int
0x1400ff2f2  call    NvmeControllerRemove
0x1400ff2f7  mov     esi, eax
0x1400ff2f9  test    eax, eax
0x1400ff2fb  js      loc_1400FF6D2
0x1400ff301  jmp     loc_1400FF6B3
0x1400ff306  mov     eax, [rcx+1A8h]
0x1400ff30c  test    al, 40h
0x1400ff30e  jz      loc_1400FF442
0x1400ff314  xor     r14d, r14d
0x1400ff317  call    NvmeAdapterAcquireStorMQControllerListLockShared
0x1400ff31c  lea     r12, [rdi+4B0h]
0x1400ff323  xor     r13b, r13b
0x1400ff326  mov     r15, [r12]
0x1400ff32a  jmp     loc_1400FF420
0x1400ff32f  lea     rbx, [r15-70h]
0x1400ff333  mov     rax, [rbx+520h]
0x1400ff33a  mov     rcx, [rax+28h]
0x1400ff33e  mov     eax, [rcx+0C0h]
0x1400ff344  test    eax, eax
0x1400ff346  jz      short loc_1400FF396
0x1400ff348  mov     rax, [rbx+520h]
0x1400ff34f  mov     rcx, [rax+28h]
0x1400ff353  sub     rcx, 0FFFFFFFFFFFFFF80h; PKTIMER
0x1400ff357  call    cs:__imp_KeCancelTimer
0x1400ff35e  nop     dword ptr [rax+rax+00h]
0x1400ff363  mov     rax, [rbx+520h]
0x1400ff36a  mov     rcx, [rax+28h]
0x1400ff36e  add     rcx, 40h ; '@'; Dpc
0x1400ff372  call    cs:__imp_KeRemoveQueueDpc
0x1400ff379  nop     dword ptr [rax+rax+00h]
0x1400ff37e  mov     rax, [rbx+520h]
0x1400ff385  xor     ecx, ecx
0x1400ff387  mov     rdx, [rax+28h]
0x1400ff38b  lea     eax, [rcx+1]
0x1400ff38e  lock cmpxchg [rdx+0C0h], ecx
0x1400ff396  mov     rcx, rbx
0x1400ff399  call    NvmeControllerTerminateCommandTimeoutDetectThread
0x1400ff39e  mov     ecx, [rdi+54h]
0x1400ff3a1  lea     eax, [rcx-5]
0x1400ff3a4  cmp     eax, 1
0x1400ff3a7  jbe     short loc_1400FF3CE
0x1400ff3a9  cmp     ecx, 8
0x1400ff3ac  jnz     short loc_1400FF3C8
0x1400ff3ae  mov     rcx, rbx; int
0x1400ff3b1  call    NvmeControllerStop
0x1400ff3b6  mov     esi, eax
0x1400ff3b8  test    eax, eax
0x1400ff3ba  jns     short loc_1400FF412
0x1400ff3bc  mov     dword ptr [rbx+4C0h], 2Fh ; '/'
0x1400ff3c6  jmp     short loc_1400FF40F
0x1400ff3c8  test    esi, esi
0x1400ff3ca  jns     short loc_1400FF412
0x1400ff3cc  jmp     short loc_1400FF40F
0x1400ff3ce  mov     r9d, 1
0x1400ff3d4  mov     [rsp+68h+arg_0], 2
0x1400ff3dc  lea     rax, [rsp+68h+arg_0]
0x1400ff3e1  mov     edx, 80000009h
0x1400ff3e6  mov     rcx, rbx
0x1400ff3e9  mov     [rsp+68h+var_48], rax
0x1400ff3ee  lea     r8d, [r9+3]
0x1400ff3f2  call    NvmeControllerSetStorMQProperty
0x1400ff3f7  mov     rcx, rbx; int
0x1400ff3fa  call    NvmeControllerRemove
0x1400ff3ff  mov     esi, eax
0x1400ff401  test    eax, eax
0x1400ff403  jns     short loc_1400FF412
0x1400ff405  mov     dword ptr [rbx+4C0h], 30h ; '0'
0x1400ff40f  mov     r13b, 1
0x1400ff412  mov     r15, [r15]
0x1400ff415  test    esi, esi
0x1400ff417  mov     eax, esi
0x1400ff419  cmovns  eax, r14d
0x1400ff41d  mov     r14d, eax
0x1400ff420  cmp     r15, r12
0x1400ff423  jnz     loc_1400FF32F
0x1400ff429  mov     rcx, rdi
0x1400ff42c  call    NvmeAdapterReleaseStorMQControllerListLockShared
0x1400ff431  test    r13b, r13b
0x1400ff434  jz      loc_1400FF6B3
0x1400ff43a  mov     esi, r14d
0x1400ff43d  jmp     loc_1400FF6D2
0x1400ff442  mov     rbx, [rcx+268h]
0x1400ff449  call    cs:__imp_KeEnterCriticalRegion
0x1400ff450  nop     dword ptr [rax+rax+00h]
0x1400ff455  mov     dl, 1; Wait
0x1400ff457  lea     rcx, [rbx+18h]; Resource
0x1400ff45b  call    cs:__imp_ExAcquireResourceSharedLite
0x1400ff462  nop     dword ptr [rax+rax+00h]
0x1400ff467  mov     rcx, [rdi+268h]
0x1400ff46e  mov     r15, [rcx]
0x1400ff471  jmp     loc_1400FF68E
0x1400ff476  lea     rbx, [r15-18h]
0x1400ff47a  mov     rcx, rbx
0x1400ff47d  call    NvmeAdapterHostGatewayAcquireRundown
0x1400ff482  mov     esi, eax
0x1400ff484  test    eax, eax
0x1400ff486  js      loc_1400FF684
0x1400ff48c  call    cs:__imp_KeEnterCriticalRegion
0x1400ff493  nop     dword ptr [rax+rax+00h]
0x1400ff498  lea     rcx, [rbx+180h]; Resource
0x1400ff49f  mov     dl, 1; Wait
0x1400ff4a1  call    cs:__imp_ExAcquireResourceSharedLite
0x1400ff4a8  nop     dword ptr [rax+rax+00h]
0x1400ff4ad  lea     r13, [rbx+168h]
0x1400ff4b4  mov     r12, [r13+0]
0x1400ff4b8  mov     [rsp+68h+arg_18], r13
0x1400ff4c0  cmp     r12, r13
0x1400ff4c3  jz      loc_1400FF655
0x1400ff4c9  lea     rcx, [r12-8]
0x1400ff4ce  call    NvmeAdapterSubsystemPortAcquireRundown
0x1400ff4d3  mov     esi, eax
0x1400ff4d5  test    eax, eax
0x1400ff4d7  js      loc_1400FF644
0x1400ff4dd  call    cs:__imp_KeEnterCriticalRegion
0x1400ff4e4  nop     dword ptr [rax+rax+00h]
0x1400ff4e9  lea     rcx, [r12+270h]; Resource
0x1400ff4f1  mov     dl, 1; Wait
0x1400ff4f3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400ff4fa  nop     dword ptr [rax+rax+00h]
0x1400ff4ff  lea     rax, [r12+258h]
0x1400ff507  mov     rbx, [rax]
0x1400ff50a  cmp     rbx, rax
0x1400ff50d  jz      loc_1400FF613
0x1400ff513  mov     rdx, [rbx]
0x1400ff516  lea     r13, [rbx-40h]
0x1400ff51a  mov     rax, [r13+520h]
0x1400ff521  mov     [rsp+68h+arg_10], rdx
0x1400ff529  mov     rcx, [rax+28h]
0x1400ff52d  mov     eax, [rcx+0C0h]
0x1400ff533  test    eax, eax
0x1400ff535  jz      short loc_1400FF58D
0x1400ff537  mov     rax, [r13+520h]
0x1400ff53e  mov     rcx, [rax+28h]
0x1400ff542  sub     rcx, 0FFFFFFFFFFFFFF80h; PKTIMER
0x1400ff546  call    cs:__imp_KeCancelTimer
0x1400ff54d  nop     dword ptr [rax+rax+00h]
0x1400ff552  mov     rax, [r13+520h]
0x1400ff559  mov     rcx, [rax+28h]
0x1400ff55d  add     rcx, 40h ; '@'; Dpc
0x1400ff561  call    cs:__imp_KeRemoveQueueDpc
0x1400ff568  nop     dword ptr [rax+rax+00h]
0x1400ff56d  mov     rax, [r13+520h]
0x1400ff574  xor     ecx, ecx
0x1400ff576  mov     rdx, [rax+28h]
0x1400ff57a  lea     eax, [rcx+1]
0x1400ff57d  lock cmpxchg [rdx+0C0h], ecx
0x1400ff585  mov     rdx, [rsp+68h+arg_10]
0x1400ff58d  mov     rax, [r13+88h]
0x1400ff594  mov     r8d, 3
0x1400ff59a  mov     [r13+238h], r8d
0x1400ff5a1  test    al, 1
0x1400ff5a3  jnz     short loc_1400FF5D9
0x1400ff5a5  or      rax, 8
0x1400ff5a9  mov     [r13+88h], rax
0x1400ff5b0  mov     rcx, [rbx]
0x1400ff5b3  cmp     [rcx+8], rbx
0x1400ff5b7  jnz     loc_1400FF6E5
0x1400ff5bd  mov     rax, [rbx+8]
0x1400ff5c1  cmp     [rax], rbx
0x1400ff5c4  jnz     loc_1400FF6E5
0x1400ff5ca  mov     [rax], rcx
0x1400ff5cd  mov     [rcx+8], rax
0x1400ff5d1  dec     dword ptr [r12+268h]
0x1400ff5d9  mov     r9b, [r13+88h]
0x1400ff5e0  lea     r8, [r12+34h]
0x1400ff5e5  not     r9b
0x1400ff5e8  mov     rbx, rdx
0x1400ff5eb  and     r9b, 1
0x1400ff5ef  mov     rdx, r13
0x1400ff5f2  mov     rcx, rdi
0x1400ff5f5  call    NvmeAdapterDisconnectFabricsControllerInternal
0x1400ff5fa  lea     rax, [r12+258h]
0x1400ff602  cmp     rbx, rax
0x1400ff605  jnz     loc_1400FF513
0x1400ff60b  mov     r13, [rsp+68h+arg_18]
0x1400ff613  lea     rcx, [r12+270h]; Resource
0x1400ff61b  call    cs:__imp_ExReleaseResourceLite
0x1400ff622  nop     dword ptr [rax+rax+00h]
0x1400ff627  call    cs:__imp_KeLeaveCriticalRegion
0x1400ff62e  nop     dword ptr [rax+rax+00h]
0x1400ff633  mov     rcx, [r12+20h]; RunRefCacheAware
0x1400ff638  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400ff63f  nop     dword ptr [rax+rax+00h]
0x1400ff644  mov     r12, [r12]
0x1400ff648  cmp     r12, r13
0x1400ff64b  jnz     loc_1400FF4C9
0x1400ff651  lea     rbx, [r15-18h]
0x1400ff655  lea     rcx, [rbx+180h]; Resource
0x1400ff65c  call    cs:__imp_ExReleaseResourceLite
0x1400ff663  nop     dword ptr [rax+rax+00h]
0x1400ff668  call    cs:__imp_KeLeaveCriticalRegion
0x1400ff66f  nop     dword ptr [rax+rax+00h]
0x1400ff674  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400ff678  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400ff67f  nop     dword ptr [rax+rax+00h]
0x1400ff684  mov     r15, [r15]
0x1400ff687  mov     rcx, [rdi+268h]
0x1400ff68e  cmp     r15, rcx
0x1400ff691  jnz     loc_1400FF476
0x1400ff697  add     rcx, 18h; Resource
0x1400ff69b  call    cs:__imp_ExReleaseResourceLite
0x1400ff6a2  nop     dword ptr [rax+rax+00h]
0x1400ff6a7  call    cs:__imp_KeLeaveCriticalRegion
0x1400ff6ae  nop     dword ptr [rax+rax+00h]
0x1400ff6b3  lea     rcx, [rdi+0B0h]
0x1400ff6ba  mov     edx, 1
0x1400ff6bf  call    NvmeIsAdapterControlSupported
0x1400ff6c4  test    al, al
0x1400ff6c6  jz      short loc_1400FF6D2
0x1400ff6c8  mov     rcx, rdi
0x1400ff6cb  call    NvmeAdapterStopAdapter
0x1400ff6d0  mov     esi, eax
0x1400ff6d2  mov     eax, esi
0x1400ff6d4  add     rsp, 30h
0x1400ff6d8  pop     r15
0x1400ff6da  pop     r14
0x1400ff6dc  pop     r13
0x1400ff6de  pop     r12
0x1400ff6e0  pop     rdi
0x1400ff6e1  pop     rsi
0x1400ff6e2  pop     rbx
0x1400ff6e3  retn
0x1400ff6e5  mov     rcx, r8
0x1400ff6e8  int     29h; Win8: RtlFailFast(ecx)
```
