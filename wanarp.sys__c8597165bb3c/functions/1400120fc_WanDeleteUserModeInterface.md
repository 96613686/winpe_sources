# WanDeleteUserModeInterface

- ea: `0x1400120fc`
- end: `0x14001245a`
- name: `WanDeleteUserModeInterface`
- size: `862`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400172d0`

## callees

- `0x1400024d0`
- `0x140002b6c`
- `0x140003090`
- `0x140004124`
- `0x14000e280`
- `0x1400120fc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001214b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001214b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001230c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001230c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123c4`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400121f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012202`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012215`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001226a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012282`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012295`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012347`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001237c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001238f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400123e3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400123f2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012405`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400121f3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012202`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012215`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001226a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012282`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012295`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012347`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001237c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001238f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400123e3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400123f2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012405`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012161`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001218b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400121bb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012161`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001218b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400121bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001222b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400122ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400123a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001241b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001222b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400122ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400123a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001241b`
- `NDIS!NdisIfDeregisterInterface` at `0x1400122d7`
- `NDIS!NdisIfDeregisterInterface` at `0x1400122d7`

## pseudocode

```c
__int64 __fastcall WanDeleteUserModeInterface(__int64 a1, unsigned int a2, __int64 a3, unsigned __int8 a4)
{
  unsigned int v4; // r14d
  _DWORD *v6; // r15
  KIRQL v7; // r12
  __int64 DialInAdapterGivenInterfaceIndex; // rax
  __int64 v9; // rbx
  KSPIN_LOCK *v10; // rsi
  __int64 v11; // rdi
  char v12; // al
  NET_IFINDEX v13; // r15d
  unsigned int v14; // ebx
  KSPIN_LOCK *v15; // rcx
  _QWORD *v16; // rbx
  __int64 v17; // rcx
  _QWORD *v18; // rax

  v4 = a4;
  _InterlockedIncrement(&dword_140009770);
  *(_QWORD *)(a1 + 56) = 0;
  if ( a2 < 4 )
  {
    _InterlockedIncrement(&dword_140009774);
    return 3221225507LL;
  }
  v6 = *(_DWORD **)(a1 + 24);
  WanpAcquireResource(&g_wrBindMutex);
  v7 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
  KeAcquireSpinLockAtDpcLevel(&SpinLock);
  DialInAdapterGivenInterfaceIndex = WanpFindDialInAdapterGivenInterfaceIndex((unsigned int)*v6, v4);
  v9 = DialInAdapterGivenInterfaceIndex;
  if ( DialInAdapterGivenInterfaceIndex )
  {
    v10 = (KSPIN_LOCK *)(DialInAdapterGivenInterfaceIndex + 120);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(DialInAdapterGivenInterfaceIndex + 120));
    v11 = *(_QWORD *)((-(__int64)((_BYTE)v4 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + v9 + 176);
    if ( v11 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v11 + 56));
      if ( *(_DWORD *)(v11 + 32) == *v6 )
      {
        v12 = *(_BYTE *)(v9 + 148);
        if ( v12 == 3 || v12 == 6 )
        {
          v13 = *(_DWORD *)(v9 + 360);
          if ( v13 != -1 )
          {
            v15 = (KSPIN_LOCK *)(v11 + 56);
            if ( *(_DWORD *)(v9 + 184) == 1 )
            {
              *(_DWORD *)(v9 + 360) = -1;
              *(_BYTE *)(v9 + 148) = 0;
              KeReleaseSpinLockFromDpcLevel(v15);
              --*(_DWORD *)(v9 + 184);
              KeReleaseSpinLockFromDpcLevel(v10);
              KeReleaseSpinLockFromDpcLevel(&SpinLock);
              KeReleaseSpinLock(&g_rwlAdapterLock, v7);
              if ( (_BYTE)v4 )
                *(_QWORD *)(v9 + 168) = 0;
              else
                *(_QWORD *)(v9 + 176) = 0;
              NdisIfDeregisterInterface(v13);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 128), 0xFFFFFFFF) == 1 )
                WanpDeleteAdapter((PVOID)v9);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 64), 0xFFFFFFFF) == 1 )
                ExFreePoolWithTag((PVOID)v11, 0);
              v16 = (_QWORD *)(v9 + 32);
              v17 = *v16;
              if ( *(_QWORD **)(*v16 + 8LL) != v16 || (v18 = (_QWORD *)v16[1], (_QWORD *)*v18 != v16) )
                __fastfail(3u);
              --g_ulNumDialInAdapters;
              *v18 = v17;
              *(_QWORD *)(v17 + 8) = v18;
            }
            else
            {
              KeReleaseSpinLockFromDpcLevel(v15);
              --*(_DWORD *)(v9 + 184);
              if ( (_BYTE)v4 )
                *(_QWORD *)(v9 + 168) = 0;
              else
                *(_QWORD *)(v9 + 176) = 0;
              KeReleaseSpinLockFromDpcLevel(v10);
              KeReleaseSpinLockFromDpcLevel(&SpinLock);
              KeReleaseSpinLock(&g_rwlAdapterLock, v7);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 64), 0xFFFFFFFF) == 1 )
                ExFreePoolWithTag((PVOID)v11, 0);
            }
            v14 = 0;
            WanpReleaseResource(&g_wrBindMutex);
            return v14;
          }
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v11 + 56));
        KeReleaseSpinLockFromDpcLevel(v10);
        KeReleaseSpinLockFromDpcLevel(&SpinLock);
        KeReleaseSpinLock(&g_rwlAdapterLock, v7);
        WanpReleaseResource(&g_wrBindMutex);
        v14 = -1073741436;
        goto LABEL_31;
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v11 + 56));
    }
    KeReleaseSpinLockFromDpcLevel(v10);
  }
  KeReleaseSpinLockFromDpcLevel(&SpinLock);
  KeReleaseSpinLock(&g_rwlAdapterLock, v7);
  v14 = WanRemoveRouterInterface((unsigned int)*v6);
  WanpReleaseResource(&g_wrBindMutex);
  if ( v14 )
LABEL_31:
    _InterlockedIncrement(&dword_140009774);
  return v14;
}

```

## disassembly

```asm
0x1400120fc  push    rbx
0x1400120fe  push    rbp
0x1400120ff  push    rsi
0x140012100  push    rdi
0x140012101  push    r12
0x140012103  push    r14
0x140012105  push    r15
0x140012107  sub     rsp, 20h
0x14001210b  movzx   r14d, r9b
0x14001210f  lock inc cs:dword_140009770
0x140012116  mov     qword ptr [rcx+38h], 0
0x14001211e  cmp     edx, 4
0x140012121  jnb     short loc_140012134
0x140012123  lock inc cs:dword_140009774
0x14001212a  mov     eax, 0C0000023h
0x14001212f  jmp     loc_14001244A
0x140012134  mov     r15, [rcx+18h]
0x140012138  lea     rcx, g_wrBindMutex
0x14001213f  call    WanpAcquireResource
0x140012144  lea     rcx, g_rwlAdapterLock; SpinLock
0x14001214b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012152  nop     dword ptr [rax+rax+00h]
0x140012157  lea     rcx, SpinLock; SpinLock
0x14001215e  mov     r12b, al
0x140012161  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140012168  nop     dword ptr [rax+rax+00h]
0x14001216d  mov     ecx, [r15]
0x140012170  mov     edx, r14d
0x140012173  call    WanpFindDialInAdapterGivenInterfaceIndex
0x140012178  mov     rbx, rax
0x14001217b  test    rax, rax
0x14001217e  jz      loc_1400123FE
0x140012184  lea     rsi, [rax+78h]
0x140012188  mov     rcx, rsi; SpinLock
0x14001218b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140012192  nop     dword ptr [rax+rax+00h]
0x140012197  mov     cl, r14b
0x14001219a  neg     cl
0x14001219c  sbb     rdx, rdx
0x14001219f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400121a3  mov     rdi, [rdx+rbx+0B0h]
0x1400121ab  test    rdi, rdi
0x1400121ae  jz      loc_1400123EF
0x1400121b4  lea     rbp, [rdi+38h]
0x1400121b8  mov     rcx, rbp; SpinLock
0x1400121bb  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400121c2  nop     dword ptr [rax+rax+00h]
0x1400121c7  mov     eax, [r15]
0x1400121ca  cmp     [rdi+20h], eax
0x1400121cd  jnz     loc_1400123E0
0x1400121d3  mov     al, [rbx+94h]
0x1400121d9  cmp     al, 3
0x1400121db  jz      short loc_1400121E1
0x1400121dd  cmp     al, 6
0x1400121df  jnz     short loc_1400121F0
0x1400121e1  mov     r15d, [rbx+168h]
0x1400121e8  or      eax, 0FFFFFFFFh
0x1400121eb  cmp     r15d, eax
0x1400121ee  jnz     short loc_14001224D
0x1400121f0  mov     rcx, rbp; SpinLock
0x1400121f3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400121fa  nop     dword ptr [rax+rax+00h]
0x1400121ff  mov     rcx, rsi; SpinLock
0x140012202  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012209  nop     dword ptr [rax+rax+00h]
0x14001220e  lea     rcx, SpinLock; SpinLock
0x140012215  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001221c  nop     dword ptr [rax+rax+00h]
0x140012221  mov     dl, r12b; NewIrql
0x140012224  lea     rcx, g_rwlAdapterLock; SpinLock
0x14001222b  call    cs:__imp_KeReleaseSpinLock
0x140012232  nop     dword ptr [rax+rax+00h]
0x140012237  lea     rcx, g_wrBindMutex
0x14001223e  call    WanpReleaseResource
0x140012243  mov     ebx, 0C0000184h
0x140012248  jmp     loc_140012441
0x14001224d  cmp     dword ptr [rbx+0B8h], 1
0x140012254  mov     rcx, rbp; SpinLock
0x140012257  jnz     loc_140012347
0x14001225d  mov     [rbx+168h], eax
0x140012263  mov     byte ptr [rbx+94h], 0
0x14001226a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012271  nop     dword ptr [rax+rax+00h]
0x140012276  or      ebp, 0FFFFFFFFh
0x140012279  mov     rcx, rsi; SpinLock
0x14001227c  add     [rbx+0B8h], ebp
0x140012282  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012289  nop     dword ptr [rax+rax+00h]
0x14001228e  lea     rcx, SpinLock; SpinLock
0x140012295  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001229c  nop     dword ptr [rax+rax+00h]
0x1400122a1  mov     dl, r12b; NewIrql
0x1400122a4  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400122ab  call    cs:__imp_KeReleaseSpinLock
0x1400122b2  nop     dword ptr [rax+rax+00h]
0x1400122b7  test    r14b, r14b
0x1400122ba  jz      short loc_1400122C9
0x1400122bc  mov     qword ptr [rbx+0A8h], 0
0x1400122c7  jmp     short loc_1400122D4
0x1400122c9  mov     qword ptr [rbx+0B0h], 0
0x1400122d4  mov     ecx, r15d; ifIndex
0x1400122d7  call    cs:__imp_NdisIfDeregisterInterface
0x1400122de  nop     dword ptr [rax+rax+00h]
0x1400122e3  or      esi, 0FFFFFFFFh
0x1400122e6  mov     eax, esi
0x1400122e8  lock xadd [rbx+80h], eax
0x1400122f0  add     eax, esi
0x1400122f2  jnz     short loc_1400122FC
0x1400122f4  mov     rcx, rbx; P
0x1400122f7  call    WanpDeleteAdapter
0x1400122fc  mov     eax, esi
0x1400122fe  lock xadd [rdi+40h], eax
0x140012303  add     eax, esi
0x140012305  jnz     short loc_140012318
0x140012307  xor     edx, edx; Tag
0x140012309  mov     rcx, rdi; P
0x14001230c  call    cs:__imp_ExFreePoolWithTag
0x140012313  nop     dword ptr [rax+rax+00h]
0x140012318  add     rbx, 20h ; ' '
0x14001231c  mov     rcx, [rbx]
0x14001231f  cmp     [rcx+8], rbx
0x140012323  jnz     short loc_140012340
0x140012325  mov     rax, [rbx+8]
0x140012329  cmp     [rax], rbx
0x14001232c  jnz     short loc_140012340
0x14001232e  add     cs:g_ulNumDialInAdapters, ebp
0x140012334  mov     [rax], rcx
0x140012337  mov     [rcx+8], rax
0x14001233b  jmp     loc_1400123D0
0x140012340  mov     ecx, 3
0x140012345  int     29h; Win8: RtlFailFast(ecx)
0x140012347  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001234e  nop     dword ptr [rax+rax+00h]
0x140012353  or      ebp, 0FFFFFFFFh
0x140012356  add     [rbx+0B8h], ebp
0x14001235c  test    r14b, r14b
0x14001235f  jz      short loc_14001236E
0x140012361  mov     qword ptr [rbx+0A8h], 0
0x14001236c  jmp     short loc_140012379
0x14001236e  mov     qword ptr [rbx+0B0h], 0
0x140012379  mov     rcx, rsi; SpinLock
0x14001237c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012383  nop     dword ptr [rax+rax+00h]
0x140012388  lea     rcx, SpinLock; SpinLock
0x14001238f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012396  nop     dword ptr [rax+rax+00h]
0x14001239b  mov     dl, r12b; NewIrql
0x14001239e  lea     rcx, g_rwlAdapterLock; SpinLock
0x1400123a5  call    cs:__imp_KeReleaseSpinLock
0x1400123ac  nop     dword ptr [rax+rax+00h]
0x1400123b1  or      esi, 0FFFFFFFFh
0x1400123b4  mov     eax, esi
0x1400123b6  lock xadd [rdi+40h], eax
0x1400123bb  add     eax, esi
0x1400123bd  jnz     short loc_1400123D0
0x1400123bf  xor     edx, edx; Tag
0x1400123c1  mov     rcx, rdi; P
0x1400123c4  call    cs:__imp_ExFreePoolWithTag
0x1400123cb  nop     dword ptr [rax+rax+00h]
0x1400123d0  xor     ebx, ebx
0x1400123d2  lea     rcx, g_wrBindMutex
0x1400123d9  call    WanpReleaseResource
0x1400123de  jmp     short loc_140012448
0x1400123e0  mov     rcx, rbp; SpinLock
0x1400123e3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400123ea  nop     dword ptr [rax+rax+00h]
0x1400123ef  mov     rcx, rsi; SpinLock
0x1400123f2  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400123f9  nop     dword ptr [rax+rax+00h]
0x1400123fe  lea     rcx, SpinLock; SpinLock
0x140012405  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001240c  nop     dword ptr [rax+rax+00h]
0x140012411  mov     dl, r12b; NewIrql
0x140012414  lea     rcx, g_rwlAdapterLock; SpinLock
0x14001241b  call    cs:__imp_KeReleaseSpinLock
0x140012422  nop     dword ptr [rax+rax+00h]
0x140012427  mov     ecx, [r15]
0x14001242a  call    WanRemoveRouterInterface
0x14001242f  lea     rcx, g_wrBindMutex
0x140012436  mov     ebx, eax
0x140012438  call    WanpReleaseResource
0x14001243d  test    ebx, ebx
0x14001243f  jz      short loc_140012448
0x140012441  lock inc cs:dword_140009774
0x140012448  mov     eax, ebx
0x14001244a  add     rsp, 20h
0x14001244e  pop     r15
0x140012450  pop     r14
0x140012452  pop     r12
0x140012454  pop     rdi
0x140012455  pop     rsi
0x140012456  pop     rbp
0x140012457  pop     rbx
0x140012458  retn
```
