# WanpLinkDownIndicationWorkItemImpl

- ea: `0x14000f9c8`
- end: `0x14000fdbb`
- name: `WanpLinkDownIndicationWorkItemImpl`
- size: `1011`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000f834`
- `0x14000f9b0`

## callees

- `0x1400024d0`
- `0x140002b6c`
- `0x14000e280`
- `0x14000f728`
- `0x14000f9c8`
- `0x1400110bc`
- `0x140013c90`
- `0x140014964`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f9f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fa40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000f9f1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fa40`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000fbdf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000fbdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fabf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fabf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fc61`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fc74`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fc90`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fca3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fcf3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fc61`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fc74`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fc90`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fca3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000fcf3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fa52`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fb64`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fb77`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fb8a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fa52`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fb64`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fb77`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000fb8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fa24`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fb35`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fd06`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fa24`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fb35`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fd06`
- `NDIS!NdisSetEvent` at `0x14000fd99`
- `NDIS!NdisSetEvent` at `0x14000fd99`

## pseudocode

```c
void __fastcall WanpLinkDownIndicationWorkItemImpl(PVOID Entry, char a2)
{
  _DWORD *v3; // rsi
  char v4; // r13
  KIRQL v5; // al
  KIRQL v6; // r12
  __int64 v7; // r15
  __int64 v8; // rsi
  int *v9; // r14
  unsigned int v10; // ebp
  int i; // eax
  char v12; // r15
  __int64 v13; // rbp
  __int64 *v14; // r14
  _DWORD *v15; // rax
  __int64 *v16; // rax
  __int64 **v17; // rdx
  __int64 v19; // [rsp+70h] [rbp+18h]

  v3 = 0;
  v4 = a2;
  v5 = KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)Entry + 10));
  v6 = v5;
  v7 = *((_QWORD *)Entry + 30);
  v19 = v7;
  if ( *((_DWORD *)Entry + 25) == 2 )
  {
    v8 = *((_QWORD *)Entry + 2);
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 64));
    KeReleaseSpinLock(*((PKSPIN_LOCK *)Entry + 10), v5);
    WanpAcquireResource(WfpMutex);
    KeAcquireSpinLockRaiseToDpc(*((PKSPIN_LOCK *)Entry + 10));
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v8 + 56));
    v9 = *(int **)(v8 + 152);
    v10 = *(_DWORD *)(v8 + 160);
    if ( (int)WanpRouterLinkDownHandler(Entry) >= 0 )
    {
      if ( v9 )
      {
        WanpAddSubnetFilters(v9, v10, v8);
        for ( i = *v9; i; --i )
          _InterlockedIncrement((volatile signed __int32 *)(v8 + 64));
      }
    }
    WanpReleaseResource(WfpMutex);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 64), 0xFFFFFFFF) == 1 )
      ExFreePoolWithTag((PVOID)v8, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
      WanpDeleteConnEntry(Entry);
    if ( !_InterlockedDecrement((volatile signed __int32 *)Entry + 24) )
      WanpDeleteConnEntry(Entry);
  }
  else
  {
    v12 = *((_BYTE *)Entry + 4);
    v13 = *((_QWORD *)Entry + 1);
    v14 = *(__int64 **)((-(__int64)(v12 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + v13 + 176);
    if ( *((_DWORD *)v14 + 27) )
    {
      *((_BYTE *)v14 + 48) = 4;
      if ( *(_DWORD *)(v13 + 184) == 1 )
        *(_WORD *)(v13 + 148) = 516;
      KeAcquireSpinLockAtDpcLevel(&g_rwlIfLock);
      KeAcquireSpinLockAtDpcLevel(&qword_140009C48);
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v14 + 7);
      *((_DWORD *)v14 + 36) = 2;
      *((_DWORD *)v14 + 35) = 2;
      *(_QWORD *)(v13 + 200) = MEMORY[0xFFFFF78000000014] / 100000LL;
      v15 = ExAllocateFromNPagedLookasideList(&g_llNotificationBlocks);
      v3 = v15;
      if ( *((_DWORD *)v14 + 27) == 1 )
      {
        if ( v15 )
        {
          v15[12] = 4;
          v15[14] = *(_DWORD *)(v13 + 360);
          v15[13] = -1;
          *((_BYTE *)v15 + 60) = v12;
          if ( v12 )
          {
            v15[16] = *((_DWORD *)Entry + 6);
            v15[17] = *((_DWORD *)Entry + 7);
            v15[18] = *((_DWORD *)Entry + 8);
          }
          else
          {
            *((_QWORD *)v15 + 8) = *((_QWORD *)Entry + 6);
          }
        }
        v16 = (__int64 *)*v14;
        if ( *(__int64 **)(*v14 + 8) != v14 || (v17 = (__int64 **)v14[1], *v17 != v14) )
          __fastfail(3u);
        *v17 = v16;
        v16[1] = (__int64)v17;
        _InterlockedAdd(&g_ulNumDialOutInterfaces, 0xFFFFFFFF);
        KeReleaseSpinLockFromDpcLevel(&qword_140009C48);
        KeReleaseSpinLockFromDpcLevel(&g_rwlIfLock);
      }
      else
      {
        KeReleaseSpinLockFromDpcLevel(&qword_140009C48);
        KeReleaseSpinLockFromDpcLevel(&g_rwlIfLock);
        if ( v3 )
        {
          v3[12] = 2;
          v3[14] = *(_DWORD *)(v13 + 360);
          v3[13] = *((_DWORD *)v14 + 8);
          *((_BYTE *)v3 + 60) = v12;
          if ( v12 )
          {
            v3[16] = *((_DWORD *)Entry + 6);
            v3[17] = *((_DWORD *)Entry + 7);
            v3[18] = *((_DWORD *)Entry + 8);
          }
          else
          {
            *((_QWORD *)v3 + 8) = *((_QWORD *)Entry + 6);
          }
        }
      }
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v14 + 7);
      KeReleaseSpinLock(*((PKSPIN_LOCK *)Entry + 10), v6);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 128), 0xFFFFFFFF) == 1 )
        WanpDeleteAdapter((PVOID)v13);
      v4 = a2;
    }
    else
    {
      KeReleaseSpinLock(*((PKSPIN_LOCK *)Entry + 10), v5);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
      WanpDeleteConnEntry(Entry);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
      WanpDeleteConnEntry(Entry);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
      WanpDeleteConnEntry(Entry);
    if ( !_InterlockedDecrement((volatile signed __int32 *)Entry + 24) )
      WanpDeleteConnEntry(Entry);
    if ( v3 )
      WanpCompleteIrp((char *)v3);
    v7 = v19;
  }
  if ( v4 )
  {
    if ( v7 )
      NdisSetEvent((PNDIS_EVENT)(v7 + 16));
  }
}

```

## disassembly

```asm
0x14000f9c8  mov     [rsp+arg_18], rbx
0x14000f9cd  mov     [rsp+arg_8], dl
0x14000f9d1  push    rbp
0x14000f9d2  push    rsi
0x14000f9d3  push    rdi
0x14000f9d4  push    r12
0x14000f9d6  push    r13
0x14000f9d8  push    r14
0x14000f9da  push    r15
0x14000f9dc  sub     rsp, 20h
0x14000f9e0  mov     rdi, rcx
0x14000f9e3  xor     esi, esi
0x14000f9e5  mov     rcx, [rcx+50h]; SpinLock
0x14000f9e9  mov     r13b, dl
0x14000f9ec  mov     [rsp+58h+Entry], rsi
0x14000f9f1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000f9f8  nop     dword ptr [rax+rax+00h]
0x14000f9fd  cmp     dword ptr [rdi+64h], 2
0x14000fa01  mov     r12b, al
0x14000fa04  mov     r15, [rdi+0F0h]
0x14000fa0b  mov     [rsp+58h+arg_10], r15
0x14000fa10  jnz     loc_14000FB09
0x14000fa16  mov     rsi, [rdi+10h]
0x14000fa1a  lock inc dword ptr [rsi+40h]
0x14000fa1e  mov     rcx, [rdi+50h]; SpinLock
0x14000fa22  mov     dl, al; NewIrql
0x14000fa24  call    cs:__imp_KeReleaseSpinLock
0x14000fa2b  nop     dword ptr [rax+rax+00h]
0x14000fa30  lea     rcx, WfpMutex
0x14000fa37  call    WanpAcquireResource
0x14000fa3c  mov     rcx, [rdi+50h]; SpinLock
0x14000fa40  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fa47  nop     dword ptr [rax+rax+00h]
0x14000fa4c  lea     rcx, [rsi+38h]; SpinLock
0x14000fa50  mov     bl, al
0x14000fa52  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000fa59  nop     dword ptr [rax+rax+00h]
0x14000fa5e  mov     r14, [rsi+98h]
0x14000fa65  lea     r8, [rsp+58h+Entry]
0x14000fa6a  mov     ebp, [rsi+0A0h]
0x14000fa70  mov     dl, bl
0x14000fa72  mov     rcx, rdi; Entry
0x14000fa75  call    WanpRouterLinkDownHandler
0x14000fa7a  test    eax, eax
0x14000fa7c  js      short loc_14000FAA0
0x14000fa7e  test    r14, r14
0x14000fa81  jz      short loc_14000FAA0
0x14000fa83  mov     r8, rsi
0x14000fa86  mov     edx, ebp
0x14000fa88  mov     rcx, r14
0x14000fa8b  call    WanpAddSubnetFilters
0x14000fa90  mov     eax, [r14]
0x14000fa93  test    eax, eax
0x14000fa95  jz      short loc_14000FAA0
0x14000fa97  lock inc dword ptr [rsi+40h]
0x14000fa9b  add     eax, 0FFFFFFFFh
0x14000fa9e  jnz     short loc_14000FA97
0x14000faa0  lea     rcx, WfpMutex
0x14000faa7  call    WanpReleaseResource
0x14000faac  or      ebx, 0FFFFFFFFh
0x14000faaf  mov     eax, ebx
0x14000fab1  lock xadd [rsi+40h], eax
0x14000fab6  add     eax, ebx
0x14000fab8  jnz     short loc_14000FACB
0x14000faba  xor     edx, edx; Tag
0x14000fabc  mov     rcx, rsi; P
0x14000fabf  call    cs:__imp_ExFreePoolWithTag
0x14000fac6  nop     dword ptr [rax+rax+00h]
0x14000facb  mov     eax, ebx
0x14000facd  lock xadd [rdi+60h], eax
0x14000fad2  add     eax, ebx
0x14000fad4  jnz     short loc_14000FADE
0x14000fad6  mov     rcx, rdi; Entry
0x14000fad9  call    WanpDeleteConnEntry
0x14000fade  mov     eax, ebx
0x14000fae0  lock xadd [rdi+60h], eax
0x14000fae5  add     eax, ebx
0x14000fae7  jnz     short loc_14000FAF1
0x14000fae9  mov     rcx, rdi; Entry
0x14000faec  call    WanpDeleteConnEntry
0x14000faf1  mov     rcx, [rsp+58h+Entry]; Entry
0x14000faf6  test    rcx, rcx
0x14000faf9  jz      loc_14000FD8B
0x14000faff  call    WanpCompleteIrp
0x14000fb04  jmp     loc_14000FD8B
0x14000fb09  mov     r15b, [rdi+4]
0x14000fb0d  mov     rbp, [rdi+8]
0x14000fb11  mov     al, r15b
0x14000fb14  neg     al
0x14000fb16  sbb     rcx, rcx
0x14000fb19  or      ebx, 0FFFFFFFFh
0x14000fb1c  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14000fb20  mov     r14, [rcx+rbp+0B0h]
0x14000fb28  cmp     [r14+6Ch], esi
0x14000fb2c  jnz     short loc_14000FB46
0x14000fb2e  mov     rcx, [rdi+50h]; SpinLock
0x14000fb32  mov     dl, r12b; NewIrql
0x14000fb35  call    cs:__imp_KeReleaseSpinLock
0x14000fb3c  nop     dword ptr [rax+rax+00h]
0x14000fb41  jmp     loc_14000FD2D
0x14000fb46  mov     byte ptr [r14+30h], 4
0x14000fb4b  cmp     dword ptr [rbp+0B8h], 1
0x14000fb52  jnz     short loc_14000FB5D
0x14000fb54  mov     word ptr [rbp+94h], 204h
0x14000fb5d  lea     rcx, g_rwlIfLock; SpinLock
0x14000fb64  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000fb6b  nop     dword ptr [rax+rax+00h]
0x14000fb70  lea     rcx, qword_140009C48; SpinLock
0x14000fb77  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000fb7e  nop     dword ptr [rax+rax+00h]
0x14000fb83  lea     r13, [r14+38h]
0x14000fb87  mov     rcx, r13; SpinLock
0x14000fb8a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000fb91  nop     dword ptr [rax+rax+00h]
0x14000fb96  mov     eax, 2
0x14000fb9b  mov     rcx, 0FFFFF78000000014h
0x14000fba5  mov     [r14+90h], eax
0x14000fbac  mov     [r14+8Ch], eax
0x14000fbb3  mov     rax, 29F16B11C6D1E109h
0x14000fbbd  mov     rcx, [rcx]
0x14000fbc0  imul    rcx
0x14000fbc3  lea     rcx, g_llNotificationBlocks; Lookaside
0x14000fbca  sar     rdx, 0Eh
0x14000fbce  mov     rax, rdx
0x14000fbd1  shr     rax, 3Fh
0x14000fbd5  add     rdx, rax
0x14000fbd8  mov     [rbp+0C8h], rdx
0x14000fbdf  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000fbe6  nop     dword ptr [rax+rax+00h]
0x14000fbeb  cmp     dword ptr [r14+6Ch], 1
0x14000fbf0  mov     rsi, rax
0x14000fbf3  jnz     loc_14000FC89
0x14000fbf9  test    rax, rax
0x14000fbfc  jz      short loc_14000FC3A
0x14000fbfe  mov     dword ptr [rax+30h], 4
0x14000fc05  mov     eax, [rbp+168h]
0x14000fc0b  mov     [rsi+38h], eax
0x14000fc0e  mov     dword ptr [rsi+34h], 0FFFFFFFFh
0x14000fc15  mov     [rsi+3Ch], r15b
0x14000fc19  test    r15b, r15b
0x14000fc1c  jz      short loc_14000FC32
0x14000fc1e  mov     eax, [rdi+18h]
0x14000fc21  mov     [rsi+40h], eax
0x14000fc24  mov     eax, [rdi+1Ch]
0x14000fc27  mov     [rsi+44h], eax
0x14000fc2a  mov     eax, [rdi+20h]
0x14000fc2d  mov     [rsi+48h], eax
0x14000fc30  jmp     short loc_14000FC3A
0x14000fc32  mov     rax, [rdi+30h]
0x14000fc36  mov     [rsi+40h], rax
0x14000fc3a  mov     rax, [r14]
0x14000fc3d  cmp     [rax+8], r14
0x14000fc41  jnz     short loc_14000FC82
0x14000fc43  mov     rdx, [r14+8]
0x14000fc47  cmp     [rdx], r14
0x14000fc4a  jnz     short loc_14000FC82
0x14000fc4c  mov     [rdx], rax
0x14000fc4f  mov     [rax+8], rdx
0x14000fc53  lock add cs:g_ulNumDialOutInterfaces, ebx
0x14000fc5a  lea     rcx, qword_140009C48; SpinLock
0x14000fc61  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000fc68  nop     dword ptr [rax+rax+00h]
0x14000fc6d  lea     rcx, g_rwlIfLock; SpinLock
0x14000fc74  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000fc7b  nop     dword ptr [rax+rax+00h]
0x14000fc80  jmp     short loc_14000FCF0
0x14000fc82  mov     ecx, 3
0x14000fc87  int     29h; Win8: RtlFailFast(ecx)
0x14000fc89  lea     rcx, qword_140009C48; SpinLock
0x14000fc90  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000fc97  nop     dword ptr [rax+rax+00h]
0x14000fc9c  lea     rcx, g_rwlIfLock; SpinLock
0x14000fca3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000fcaa  nop     dword ptr [rax+rax+00h]
0x14000fcaf  test    rsi, rsi
0x14000fcb2  jz      short loc_14000FCF0
0x14000fcb4  mov     dword ptr [rsi+30h], 2
0x14000fcbb  mov     eax, [rbp+168h]
0x14000fcc1  mov     [rsi+38h], eax
0x14000fcc4  mov     eax, [r14+20h]
0x14000fcc8  mov     [rsi+34h], eax
0x14000fccb  mov     [rsi+3Ch], r15b
0x14000fccf  test    r15b, r15b
0x14000fcd2  jz      short loc_14000FCE8
0x14000fcd4  mov     eax, [rdi+18h]
0x14000fcd7  mov     [rsi+40h], eax
0x14000fcda  mov     eax, [rdi+1Ch]
0x14000fcdd  mov     [rsi+44h], eax
0x14000fce0  mov     eax, [rdi+20h]
0x14000fce3  mov     [rsi+48h], eax
0x14000fce6  jmp     short loc_14000FCF0
0x14000fce8  mov     rax, [rdi+30h]
0x14000fcec  mov     [rsi+40h], rax
0x14000fcf0  mov     rcx, r13; SpinLock
0x14000fcf3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000fcfa  nop     dword ptr [rax+rax+00h]
0x14000fcff  mov     rcx, [rdi+50h]; SpinLock
0x14000fd03  mov     dl, r12b; NewIrql
0x14000fd06  call    cs:__imp_KeReleaseSpinLock
0x14000fd0d  nop     dword ptr [rax+rax+00h]
0x14000fd12  mov     eax, ebx
0x14000fd14  lock xadd [rbp+80h], eax
0x14000fd1c  add     eax, ebx
0x14000fd1e  jnz     short loc_14000FD28
0x14000fd20  mov     rcx, rbp; P
0x14000fd23  call    WanpDeleteAdapter
0x14000fd28  mov     r13b, [rsp+58h+arg_8]
0x14000fd2d  mov     eax, ebx
0x14000fd2f  lock xadd [rdi+60h], eax
0x14000fd34  add     eax, ebx
0x14000fd36  jnz     short loc_14000FD40
0x14000fd38  mov     rcx, rdi; Entry
0x14000fd3b  call    WanpDeleteConnEntry
0x14000fd40  mov     eax, ebx
0x14000fd42  lock xadd [rdi+60h], eax
0x14000fd47  add     eax, ebx
0x14000fd49  jnz     short loc_14000FD53
0x14000fd4b  mov     rcx, rdi; Entry
0x14000fd4e  call    WanpDeleteConnEntry
0x14000fd53  mov     eax, ebx
0x14000fd55  lock xadd [rdi+60h], eax
0x14000fd5a  add     eax, ebx
0x14000fd5c  jnz     short loc_14000FD66
0x14000fd5e  mov     rcx, rdi; Entry
0x14000fd61  call    WanpDeleteConnEntry
0x14000fd66  mov     eax, ebx
0x14000fd68  lock xadd [rdi+60h], eax
0x14000fd6d  add     eax, ebx
0x14000fd6f  jnz     short loc_14000FD79
0x14000fd71  mov     rcx, rdi; Entry
0x14000fd74  call    WanpDeleteConnEntry
0x14000fd79  test    rsi, rsi
0x14000fd7c  jz      short loc_14000FD86
0x14000fd7e  mov     rcx, rsi; Entry
0x14000fd81  call    WanpCompleteIrp
0x14000fd86  mov     r15, [rsp+58h+arg_10]
0x14000fd8b  test    r13b, r13b
0x14000fd8e  jz      short loc_14000FDA5
0x14000fd90  test    r15, r15
0x14000fd93  jz      short loc_14000FDA5
0x14000fd95  lea     rcx, [r15+10h]; Event
0x14000fd99  call    cs:__imp_NdisSetEvent
0x14000fda0  nop     dword ptr [rax+rax+00h]
0x14000fda5  mov     rbx, [rsp+58h+arg_18]
0x14000fdaa  add     rsp, 20h
0x14000fdae  pop     r15
0x14000fdb0  pop     r14
0x14000fdb2  pop     r13
0x14000fdb4  pop     r12
0x14000fdb6  pop     rdi
0x14000fdb7  pop     rsi
0x14000fdb8  pop     rbp
0x14000fdb9  retn
```
