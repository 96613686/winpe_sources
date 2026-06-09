# WanpRemoveAllAdaptersFromIp

- ea: `0x140002510`
- end: `0x140002895`
- name: `WanpRemoveAllAdaptersFromIp`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400028b0`

## callees

- `0x140002510`
- `0x140004124`
- `0x14000e280`
- `0x14000e310`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002574`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400026bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000275a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002795`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400027d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002574`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400026bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000275a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002795`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400027d8`
- `ntoskrnl!KeInitializeEvent` at `0x14000254d`
- `ntoskrnl!KeInitializeEvent` at `0x14000254d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002667`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002679`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000268c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400026f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002837`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002667`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002679`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000268c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400026f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002837`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000258a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400025d4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400026d3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400027ee`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000258a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400025d4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400026d3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400027ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400026a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002709`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000277d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400027c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000284d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400026a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002709`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000277d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400027c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000284d`

## pseudocode

```c
__int64 __fastcall WanpRemoveAllAdaptersFromIp(char a1)
{
  KIRQL v2; // bl
  __int64 v3; // rdi
  __int64 v4; // r14
  __int64 v5; // rbp
  __int64 *v6; // r12
  __int64 *v7; // rax
  __int64 **v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rdx
  __int64 result; // rax
  __int64 v12; // rcx
  __int64 *v13; // rdi
  KIRQL v14; // al
  __int64 v15; // rcx
  char *v16; // rbx
  KIRQL v17; // bl
  _QWORD *v18; // rcx
  KSPIN_LOCK v19; // rax
  __int64 **v20; // rcx
  _QWORD v21[2]; // [rsp+20h] [rbp-88h] BYREF
  __int128 v22; // [rsp+30h] [rbp-78h]
  _KEVENT Event; // [rsp+40h] [rbp-68h] BYREF

  v22 = 0;
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v21[1] = v21;
  v21[0] = v21;
  v2 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
  KeAcquireSpinLockAtDpcLevel(&SpinLock);
  v3 = g_leMappedAdapterList;
  if ( (__int64 *)g_leMappedAdapterList != &g_leMappedAdapterList )
  {
    v4 = 168;
    if ( !a1 )
      v4 = 176;
    while ( 1 )
    {
      v5 = *(_QWORD *)(v4 + v3);
      v6 = *(__int64 **)v3;
      if ( v5 )
      {
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 120));
        if ( *(_DWORD *)(v5 + 108) == 2 )
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 120));
          KeReleaseSpinLockFromDpcLevel(&SpinLock);
          KeReleaseSpinLock(&g_rwlAdapterLock, v2);
          WanRemoveRouterInterface(*(unsigned int *)(v5 + 32));
          v2 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
          KeAcquireSpinLockAtDpcLevel(&SpinLock);
        }
        else
        {
          if ( *(_DWORD *)(v3 + 184) == 1 )
          {
            v7 = *(__int64 **)v3;
            if ( *(_QWORD *)(*(_QWORD *)v3 + 8LL) != v3 || (v8 = *(__int64 ***)(v3 + 8), *v8 != (__int64 *)v3) )
LABEL_30:
              __fastfail(3u);
            --g_ulNumMappedAdapters;
            *v8 = v7;
            v7[1] = (__int64)v8;
            *(_QWORD *)(v3 + 8) = v3;
            *(_QWORD *)v3 = v3;
            *(_BYTE *)(v3 + 148) = 1;
          }
          v9 = (_QWORD *)(v3 + 16);
          *(_QWORD *)(v3 + 24) = v3 + 16;
          *(_QWORD *)(v3 + 16) = v3 + 16;
          v10 = v21[0];
          if ( *(_QWORD **)(v21[0] + 8LL) != v21 )
            goto LABEL_30;
          *v9 = v21[0];
          *(_QWORD *)(v3 + 24) = v21;
          *(_QWORD *)(v10 + 8) = v9;
          v21[0] = v3 + 16;
          _InterlockedIncrement((volatile signed __int32 *)(v3 + 128));
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 120));
        }
      }
      if ( v6 == &g_leMappedAdapterList )
        break;
      v3 = (__int64)v6;
    }
  }
LABEL_15:
  KeReleaseSpinLockFromDpcLevel(&SpinLock);
  KeReleaseSpinLock(&g_rwlAdapterLock, v2);
  while ( 1 )
  {
    result = v21[0];
    if ( (_QWORD *)v21[0] == v21 )
      return result;
    if ( *(_QWORD **)(v21[0] + 8LL) != v21 )
      goto LABEL_30;
    v12 = *(_QWORD *)v21[0];
    if ( *(_QWORD *)(*(_QWORD *)v21[0] + 8LL) != v21[0] )
      goto LABEL_30;
    v21[0] = *(_QWORD *)v21[0];
    v13 = (__int64 *)(result - 16);
    *(_QWORD *)(v12 + 8) = v21;
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(result - 16 + 120));
    v15 = 21;
    if ( !a1 )
      v15 = 22;
    v16 = (char *)v13[v15];
    KeReleaseSpinLock((PKSPIN_LOCK)v13 + 15, v14);
    WanpDeleteInterfaceFromIp(v16);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v13 + 15);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 32, 0xFFFFFFFF) == 1 )
      WanpDeleteAdapter(v13);
    KeReleaseSpinLock((PKSPIN_LOCK)v13 + 15, v17);
    v2 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
    KeAcquireSpinLockAtDpcLevel(&SpinLock);
    v18 = v13 + 21;
    if ( a1 )
      v18 = v13 + 22;
    if ( *v18 )
      goto LABEL_15;
    v19 = *v13;
    if ( *(__int64 **)(*v13 + 8) != v13 )
      goto LABEL_30;
    v20 = (__int64 **)v13[1];
    if ( *v20 != v13 )
      goto LABEL_30;
    *v20 = (__int64 *)v19;
    *(_QWORD *)(v19 + 8) = v20;
    KeReleaseSpinLockFromDpcLevel(&SpinLock);
    KeReleaseSpinLock(&g_rwlAdapterLock, v2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 32, 0xFFFFFFFF) == 1 )
      WanpDeleteAdapter(v13);
  }
}

```

## disassembly

```asm
0x140002510  push    rbx
0x140002512  push    rbp
0x140002513  push    rsi
0x140002514  push    rdi
0x140002515  push    r12
0x140002517  push    r13
0x140002519  push    r14
0x14000251b  push    r15
0x14000251d  sub     rsp, 68h
0x140002521  xorps   xmm1, xmm1
0x140002524  movzx   esi, cl
0x140002527  xorps   xmm0, xmm0
0x14000252a  lea     rcx, [rsp+0A8h+Event]; Event
0x14000252f  xor     eax, eax
0x140002531  xor     r8d, r8d; State
0x140002534  mov     edx, 1; Type
0x140002539  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14000253e  movups  [rsp+0A8h+var_88], xmm0
0x140002543  movups  [rsp+0A8h+var_78], xmm1
0x140002548  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm1
0x14000254d  call    cs:__imp_KeInitializeEvent
0x140002554  nop     dword ptr [rax+rax+00h]
0x140002559  lea     rax, [rsp+0A8h+var_88]
0x14000255e  mov     qword ptr [rsp+0A8h+var_88+8], rax
0x140002563  lea     rcx, g_rwlAdapterLock; SpinLock
0x14000256a  lea     rax, [rsp+0A8h+var_88]
0x14000256f  mov     qword ptr [rsp+0A8h+var_88], rax
0x140002574  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000257b  nop     dword ptr [rax+rax+00h]
0x140002580  lea     rcx, SpinLock; SpinLock
0x140002587  movzx   ebx, al
0x14000258a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002591  nop     dword ptr [rax+rax+00h]
0x140002596  mov     rdi, cs:g_leMappedAdapterList
0x14000259d  lea     r13, g_leMappedAdapterList
0x1400025a4  mov     r15d, 0B0h
0x1400025aa  cmp     rdi, r13
0x1400025ad  jz      loc_1400026EC
0x1400025b3  test    sil, sil
0x1400025b6  mov     r14d, 0A8h
0x1400025bc  cmovz   r14d, r15d
0x1400025c0  mov     rbp, [r14+rdi]
0x1400025c4  mov     r12, [rdi]
0x1400025c7  test    rbp, rbp
0x1400025ca  jz      loc_1400026DF
0x1400025d0  lea     rcx, [rdi+78h]; SpinLock
0x1400025d4  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400025db  nop     dword ptr [rax+rax+00h]
0x1400025e0  cmp     dword ptr [rbp+6Ch], 2
0x1400025e4  jz      loc_140002675
0x1400025ea  cmp     dword ptr [rdi+0B8h], 1
0x1400025f1  jnz     short loc_140002628
0x1400025f3  mov     rax, [rdi]
0x1400025f6  cmp     [rax+8], rdi
0x1400025fa  jnz     loc_14000287C
0x140002600  mov     rcx, [rdi+8]
0x140002604  cmp     [rcx], rdi
0x140002607  jnz     loc_14000287C
0x14000260d  dec     cs:g_ulNumMappedAdapters
0x140002613  mov     [rcx], rax
0x140002616  mov     [rax+8], rcx
0x14000261a  mov     [rdi+8], rdi
0x14000261e  mov     [rdi], rdi
0x140002621  mov     byte ptr [rdi+94h], 1
0x140002628  lea     rax, [rdi+10h]
0x14000262c  mov     [rdi+18h], rax
0x140002630  lea     rcx, [rsp+0A8h+var_88]
0x140002635  mov     [rax], rax
0x140002638  mov     rdx, qword ptr [rsp+0A8h+var_88]
0x14000263d  cmp     [rdx+8], rcx
0x140002641  jnz     loc_14000287C
0x140002647  mov     [rax], rdx
0x14000264a  lea     rcx, [rsp+0A8h+var_88]
0x14000264f  mov     [rax+8], rcx
0x140002653  mov     [rdx+8], rax
0x140002657  mov     qword ptr [rsp+0A8h+var_88], rax
0x14000265c  lock inc dword ptr [rdi+80h]
0x140002663  lea     rcx, [rdi+78h]; SpinLock
0x140002667  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000266e  nop     dword ptr [rax+rax+00h]
0x140002673  jmp     short loc_1400026DF
0x140002675  lea     rcx, [rdi+78h]; SpinLock
0x140002679  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002680  nop     dword ptr [rax+rax+00h]
0x140002685  lea     rcx, SpinLock; SpinLock
0x14000268c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002693  nop     dword ptr [rax+rax+00h]
0x140002698  movzx   edx, bl; NewIrql
0x14000269b  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400026a2  call    cs:__imp_KeReleaseSpinLock
0x1400026a9  nop     dword ptr [rax+rax+00h]
0x1400026ae  mov     ecx, [rbp+20h]
0x1400026b1  call    WanRemoveRouterInterface
0x1400026b6  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400026bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400026c4  nop     dword ptr [rax+rax+00h]
0x1400026c9  lea     rcx, SpinLock; SpinLock
0x1400026d0  movzx   ebx, al
0x1400026d3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400026da  nop     dword ptr [rax+rax+00h]
0x1400026df  cmp     r12, r13
0x1400026e2  jz      short loc_1400026EC
0x1400026e4  mov     rdi, r12
0x1400026e7  jmp     loc_1400025C0
0x1400026ec  lea     rcx, SpinLock; SpinLock
0x1400026f3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400026fa  nop     dword ptr [rax+rax+00h]
0x1400026ff  movzx   edx, bl; NewIrql
0x140002702  lea     rcx, g_rwlAdapterLock; SpinLock
0x140002709  call    cs:__imp_KeReleaseSpinLock
0x140002710  nop     dword ptr [rax+rax+00h]
0x140002715  mov     rax, qword ptr [rsp+0A8h+var_88]
0x14000271a  lea     rcx, [rsp+0A8h+var_88]
0x14000271f  cmp     rax, rcx
0x140002722  jz      loc_140002883
0x140002728  lea     rcx, [rsp+0A8h+var_88]
0x14000272d  cmp     [rax+8], rcx
0x140002731  jnz     loc_14000287C
0x140002737  mov     rcx, [rax]
0x14000273a  cmp     [rcx+8], rax
0x14000273e  jnz     loc_14000287C
0x140002744  mov     qword ptr [rsp+0A8h+var_88], rcx
0x140002749  lea     rdx, [rsp+0A8h+var_88]
0x14000274e  lea     rdi, [rax-10h]
0x140002752  mov     [rcx+8], rdx
0x140002756  lea     rcx, [rdi+78h]; SpinLock
0x14000275a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002761  nop     dword ptr [rax+rax+00h]
0x140002766  test    sil, sil
0x140002769  mov     ecx, 0A8h
0x14000276e  movzx   edx, al; NewIrql
0x140002771  cmovz   rcx, r15
0x140002775  mov     rbx, [rcx+rdi]
0x140002779  lea     rcx, [rdi+78h]; SpinLock
0x14000277d  call    cs:__imp_KeReleaseSpinLock
0x140002784  nop     dword ptr [rax+rax+00h]
0x140002789  mov     rcx, rbx; P
0x14000278c  call    WanpDeleteInterfaceFromIp
0x140002791  lea     rcx, [rdi+78h]; SpinLock
0x140002795  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000279c  nop     dword ptr [rax+rax+00h]
0x1400027a1  movzx   ebx, al
0x1400027a4  mov     edx, 0FFFFFFFFh
0x1400027a9  lock xadd [rdi+80h], edx
0x1400027b1  cmp     edx, 1
0x1400027b4  jnz     short loc_1400027BE
0x1400027b6  mov     rcx, rdi; P
0x1400027b9  call    WanpDeleteAdapter
0x1400027be  movzx   edx, bl; NewIrql
0x1400027c1  lea     rcx, [rdi+78h]; SpinLock
0x1400027c5  call    cs:__imp_KeReleaseSpinLock
0x1400027cc  nop     dword ptr [rax+rax+00h]
0x1400027d1  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400027d8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400027df  nop     dword ptr [rax+rax+00h]
0x1400027e4  lea     rcx, SpinLock; SpinLock
0x1400027eb  movzx   ebx, al
0x1400027ee  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400027f5  nop     dword ptr [rax+rax+00h]
0x1400027fa  lea     rcx, [rdi+0A8h]
0x140002801  test    sil, sil
0x140002804  jz      short loc_14000280D
0x140002806  lea     rcx, [rdi+0B0h]
0x14000280d  cmp     qword ptr [rcx], 0
0x140002811  jnz     loc_1400026EC
0x140002817  mov     rax, [rdi]
0x14000281a  cmp     [rax+8], rdi
0x14000281e  jnz     short loc_14000287C
0x140002820  mov     rcx, [rdi+8]
0x140002824  cmp     [rcx], rdi
0x140002827  jnz     short loc_14000287C
0x140002829  mov     [rcx], rax
0x14000282c  mov     [rax+8], rcx
0x140002830  lea     rcx, SpinLock; SpinLock
0x140002837  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000283e  nop     dword ptr [rax+rax+00h]
0x140002843  movzx   edx, bl; NewIrql
0x140002846  lea     rcx, g_rwlAdapterLock; SpinLock
0x14000284d  call    cs:__imp_KeReleaseSpinLock
0x140002854  nop     dword ptr [rax+rax+00h]
0x140002859  mov     eax, 0FFFFFFFFh
0x14000285e  lock xadd [rdi+80h], eax
0x140002866  cmp     eax, 1
0x140002869  jnz     loc_140002715
0x14000286f  mov     rcx, rdi; P
0x140002872  call    WanpDeleteAdapter
0x140002877  jmp     loc_140002715
0x14000287c  mov     ecx, 3
0x140002881  int     29h; Win8: RtlFailFast(ecx)
0x140002883  add     rsp, 68h
0x140002887  pop     r15
0x140002889  pop     r14
0x14000288b  pop     r13
0x14000288d  pop     r12
0x14000288f  pop     rdi
0x140002890  pop     rsi
0x140002891  pop     rbp
0x140002892  pop     rbx
0x140002893  retn
```
