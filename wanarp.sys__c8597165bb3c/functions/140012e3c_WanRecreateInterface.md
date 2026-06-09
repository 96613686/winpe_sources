# WanRecreateInterface

- ea: `0x140012e3c`
- end: `0x140013243`
- name: `WanRecreateInterface`
- size: `1031`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400172d0`

## callees

- `0x1400024d0`
- `0x140002b6c`
- `0x1400050f0`
- `0x14000d3e4`
- `0x14000e280`
- `0x14000e310`
- `0x14000e530`
- `0x14000f728`
- `0x140012e3c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012ea2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013101`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001317f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012ea2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013101`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001317f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131e2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012edd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012f1f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012f93`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012fbe`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013036`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012edd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012f1f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012f93`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140012fbe`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140013036`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012eca`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012f03`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013017`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013112`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012eca`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140012f03`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013017`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140013112`
- `ntoskrnl!KeLowerIrql` at `0x140012f66`
- `ntoskrnl!KeLowerIrql` at `0x140012ff3`
- `ntoskrnl!KeLowerIrql` at `0x140012f66`
- `ntoskrnl!KeLowerIrql` at `0x140012ff3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012f55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012fe2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013077`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013199`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013207`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012f55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012fe2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013077`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013199`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013207`

## pseudocode

```c
__int64 __fastcall WanRecreateInterface(__int64 a1, unsigned int a2, __int64 a3, char a4)
{
  int v6; // ebx
  _DWORD *v7; // r12
  __int64 v8; // rbp
  char v9; // si
  KIRQL v10; // r15
  __int64 i; // rbx
  signed __int32 v12; // eax
  __int64 v13; // rsi
  __int64 v14; // r14
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rdx
  KIRQL v18; // bl
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r9
  KIRQL v22; // al
  KSPIN_LOCK *v23; // rcx
  __int128 v25; // [rsp+28h] [rbp-60h] BYREF
  __int128 v26; // [rsp+38h] [rbp-50h] BYREF
  __int64 v27; // [rsp+90h] [rbp+8h]

  *(_QWORD *)(a1 + 56) = 0;
  v25 = 0;
  v26 = 0;
  if ( a2 < 8 )
  {
    v6 = -1073741789;
LABEL_41:
    *(_DWORD *)(a1 + 48) = v6;
    return (unsigned int)v6;
  }
  v7 = *(_DWORD **)(a1 + 24);
  v8 = 0;
  v9 = 0;
  WanpAcquireResource(&g_wrBindMutex);
  v10 = KeAcquireSpinLockRaiseToDpc(&g_rwlAdapterLock);
  if ( _InterlockedIncrement(&dword_140009CB0) == 1 )
    KeAcquireSpinLockAtDpcLevel(&SpinLock);
  KeReleaseSpinLockFromDpcLevel(&g_rwlAdapterLock);
  for ( i = g_leMappedAdapterList; (__int64 *)i != &g_leMappedAdapterList; i = *(_QWORD *)i )
  {
    v8 = i;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(i + 120));
    if ( *(_DWORD *)(i + 360) == *v7 )
    {
      v9 = 1;
      break;
    }
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(i + 120));
  }
  v12 = _InterlockedDecrement(&dword_140009CB0);
  if ( !v9 )
  {
    if ( v12 )
      KeLowerIrql(v10);
    else
      KeReleaseSpinLock(&SpinLock, v10);
    WanpReleaseResource(&g_wrBindMutex);
    v6 = -1073741275;
    goto LABEL_41;
  }
  if ( !v12 )
    KeReleaseSpinLockFromDpcLevel(&SpinLock);
  v13 = *(_QWORD *)((-(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + v8 + 176);
  if ( v13 )
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v13 + 56));
    v14 = *(_QWORD *)(v13 + 40);
    v27 = *(_QWORD *)(v13 + 88);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v13 + 56));
    if ( *(_DWORD *)(v14 + 100) != 1 || *(_DWORD *)(v14 + 124) != 2 && *(_BYTE *)(v8 + 148) != 6 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 120), v10);
      WanpReleaseResource(&g_wrBindMutex);
      v6 = -1073741811;
      goto LABEL_41;
    }
    v15 = *(_QWORD *)(v14 + 128);
    *(_DWORD *)(v14 + 124) = 5;
    KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 120), v10);
    v16 = qword_1400090D8;
    *(_QWORD *)&v25 = WanIpDummyInterfaceDeleteComplete;
    *((_QWORD *)&v25 + 1) = v15;
    if ( !a4 )
      v16 = qword_140009328;
    (*(void (__fastcall **)(__int128 *))(*(_QWORD *)(v16 + 8) + 40LL))(&v25);
    v17 = qword_1400090D8;
    *((_QWORD *)&v26 + 1) = v27;
    if ( !a4 )
      v17 = qword_140009328;
    *(_QWORD *)&v26 = WanIpDummyInterfaceDeleteComplete;
    (*(void (__fastcall **)(__int128 *))(*(_QWORD *)(v17 + 8) + 16LL))(&v26);
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 120));
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v13 + 56));
    LOBYTE(v19) = v18;
    LOBYTE(v20) = a4;
    *(_DWORD *)(v13 + 164) = v7[1];
    --*(_DWORD *)(v8 + 184);
    *(_QWORD *)(v13 + 88) = 0;
    *(_QWORD *)(v14 + 128) = 0;
    v6 = WanpAddAdapterToIp(v8, v13, v20, v19);
    if ( v6 >= 0 )
    {
      LOBYTE(v21) = a4;
      v6 = WanpIpAddSubInterface(v8, v13, v14, v21);
      if ( v6 < 0 )
        WanpDeleteInterfaceFromIp((PVOID)v13);
    }
    v22 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(v14 + 80));
    v23 = *(KSPIN_LOCK **)(v14 + 80);
    *(_DWORD *)(v14 + 124) = 2;
    KeReleaseSpinLock(v23, v22);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 96), 0xFFFFFFFF) == 1 )
      WanpDeleteConnEntry((PVOID)v14);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 128), 0xFFFFFFFF) == 1 )
      WanpDeleteAdapter((PVOID)v8);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 64), 0xFFFFFFFF) == 1 )
      ExFreePoolWithTag((PVOID)v13, 0);
    WanpReleaseResource(&g_wrBindMutex);
    if ( v6 < 0 )
      goto LABEL_41;
  }
  else
  {
    v6 = 0;
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v8 + 120));
    if ( _InterlockedExchangeAdd(&dword_140009CB0, 0xFFFFFFFF) == 1 )
      KeReleaseSpinLock(&SpinLock, v10);
    else
      KeLowerIrql(v10);
    WanpReleaseResource(&g_wrBindMutex);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140012e3c  mov     rax, rsp
0x140012e3f  mov     [rax+10h], rbx
0x140012e43  mov     [rax+20h], r9b
0x140012e47  push    rbp
0x140012e48  push    rsi
0x140012e49  push    rdi
0x140012e4a  push    r12
0x140012e4c  push    r13
0x140012e4e  push    r14
0x140012e50  push    r15
0x140012e52  sub     rsp, 50h
0x140012e56  mov     qword ptr [rcx+38h], 0
0x140012e5e  xorps   xmm0, xmm0
0x140012e61  xorps   xmm1, xmm1
0x140012e64  mov     r14b, r9b
0x140012e67  mov     r13, rcx
0x140012e6a  movups  xmmword ptr [rax-60h], xmm0
0x140012e6e  movups  xmmword ptr [rax-50h], xmm1
0x140012e72  cmp     edx, 8
0x140012e75  jnb     short loc_140012E81
0x140012e77  mov     ebx, 0C0000023h
0x140012e7c  jmp     loc_140013224
0x140012e81  mov     r12, [rcx+18h]
0x140012e85  xor     ebp, ebp
0x140012e87  lea     rcx, g_wrBindMutex
0x140012e8e  mov     [rsp+88h+var_68], r12
0x140012e93  xor     sil, sil
0x140012e96  call    WanpAcquireResource
0x140012e9b  lea     rcx, g_rwlAdapterLock; SpinLock
0x140012ea2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012ea9  nop     dword ptr [rax+rax+00h]
0x140012eae  mov     r15b, al
0x140012eb1  lea     eax, [rbp+1]
0x140012eb4  lock xadd cs:dword_140009CB0, eax
0x140012ebc  inc     eax
0x140012ebe  cmp     eax, 1
0x140012ec1  jnz     short loc_140012ED6
0x140012ec3  lea     rcx, SpinLock; SpinLock
0x140012eca  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140012ed1  nop     dword ptr [rax+rax+00h]
0x140012ed6  lea     rcx, g_rwlAdapterLock; SpinLock
0x140012edd  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012ee4  nop     dword ptr [rax+rax+00h]
0x140012ee9  mov     rbx, cs:g_leMappedAdapterList
0x140012ef0  lea     rax, g_leMappedAdapterList
0x140012ef7  cmp     rbx, rax
0x140012efa  jz      short loc_140012F33
0x140012efc  lea     rcx, [rbx+78h]; SpinLock
0x140012f00  mov     rbp, rbx
0x140012f03  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140012f0a  nop     dword ptr [rax+rax+00h]
0x140012f0f  mov     eax, [r12]
0x140012f13  cmp     [rbx+168h], eax
0x140012f19  jz      short loc_140012F30
0x140012f1b  lea     rcx, [rbx+78h]; SpinLock
0x140012f1f  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012f26  nop     dword ptr [rax+rax+00h]
0x140012f2b  mov     rbx, [rbx]
0x140012f2e  jmp     short loc_140012EF0
0x140012f30  mov     sil, 1
0x140012f33  or      edi, 0FFFFFFFFh
0x140012f36  mov     eax, edi
0x140012f38  lock xadd cs:dword_140009CB0, eax
0x140012f40  add     eax, edi
0x140012f42  test    sil, sil
0x140012f45  jnz     short loc_140012F88
0x140012f47  test    eax, eax
0x140012f49  jnz     short loc_140012F63
0x140012f4b  mov     dl, r15b; NewIrql
0x140012f4e  lea     rcx, SpinLock; SpinLock
0x140012f55  call    cs:__imp_KeReleaseSpinLock
0x140012f5c  nop     dword ptr [rax+rax+00h]
0x140012f61  jmp     short loc_140012F72
0x140012f63  mov     cl, r15b; NewIrql
0x140012f66  call    cs:__imp_KeLowerIrql
0x140012f6d  nop     dword ptr [rax+rax+00h]
0x140012f72  lea     rcx, g_wrBindMutex
0x140012f79  call    WanpReleaseResource
0x140012f7e  mov     ebx, 0C0000225h
0x140012f83  jmp     loc_140013224
0x140012f88  test    eax, eax
0x140012f8a  jnz     short loc_140012F9F
0x140012f8c  lea     rcx, SpinLock; SpinLock
0x140012f93  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012f9a  nop     dword ptr [rax+rax+00h]
0x140012f9f  mov     al, r14b
0x140012fa2  neg     al
0x140012fa4  sbb     rcx, rcx
0x140012fa7  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140012fab  mov     rsi, [rcx+rbp+0B0h]
0x140012fb3  test    rsi, rsi
0x140012fb6  jnz     short loc_140013010
0x140012fb8  xor     ebx, ebx
0x140012fba  lea     rcx, [rbp+78h]; SpinLock
0x140012fbe  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140012fc5  nop     dword ptr [rax+rax+00h]
0x140012fca  mov     eax, edi
0x140012fcc  lock xadd cs:dword_140009CB0, eax
0x140012fd4  add     eax, edi
0x140012fd6  jnz     short loc_140012FF0
0x140012fd8  mov     dl, r15b; NewIrql
0x140012fdb  lea     rcx, SpinLock; SpinLock
0x140012fe2  call    cs:__imp_KeReleaseSpinLock
0x140012fe9  nop     dword ptr [rax+rax+00h]
0x140012fee  jmp     short loc_140012FFF
0x140012ff0  mov     cl, r15b; NewIrql
0x140012ff3  call    cs:__imp_KeLowerIrql
0x140012ffa  nop     dword ptr [rax+rax+00h]
0x140012fff  lea     rcx, g_wrBindMutex
0x140013006  call    WanpReleaseResource
0x14001300b  jmp     loc_140013228
0x140013010  lea     r12, [rsi+38h]
0x140013014  mov     rcx, r12; SpinLock
0x140013017  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001301e  nop     dword ptr [rax+rax+00h]
0x140013023  mov     rax, [rsi+58h]
0x140013027  mov     rcx, r12; SpinLock
0x14001302a  mov     r14, [rsi+28h]
0x14001302e  mov     [rsp+88h+arg_0], rax
0x140013036  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001303d  nop     dword ptr [rax+rax+00h]
0x140013042  cmp     dword ptr [r14+64h], 1
0x140013047  jnz     loc_140013200
0x14001304d  cmp     dword ptr [r14+7Ch], 2
0x140013052  jz      short loc_140013061
0x140013054  cmp     byte ptr [rbp+94h], 6
0x14001305b  jnz     loc_140013200
0x140013061  mov     rbx, [r14+80h]
0x140013068  lea     rcx, [rbp+78h]; SpinLock
0x14001306c  mov     dl, r15b; NewIrql
0x14001306f  mov     dword ptr [r14+7Ch], 5
0x140013077  call    cs:__imp_KeReleaseSpinLock
0x14001307e  nop     dword ptr [rax+rax+00h]
0x140013083  mov     rcx, cs:qword_1400090D8
0x14001308a  lea     rax, WanIpDummyInterfaceDeleteComplete
0x140013091  mov     r15b, [rsp+88h+arg_18]
0x140013099  mov     [rsp+88h+var_60], rax
0x14001309e  test    r15b, r15b
0x1400130a1  mov     [rsp+88h+var_58], rbx
0x1400130a6  cmovz   rcx, cs:qword_140009328
0x1400130ae  mov     rax, [rcx+8]
0x1400130b2  lea     rcx, [rsp+88h+var_60]
0x1400130b7  mov     rax, [rax+28h]
0x1400130bb  call    _guard_dispatch_icall
0x1400130c0  mov     rdx, cs:qword_1400090D8
0x1400130c7  lea     rcx, [rsp+88h+var_50]
0x1400130cc  mov     rax, [rsp+88h+arg_0]
0x1400130d4  test    r15b, r15b
0x1400130d7  mov     [rsp+88h+var_48], rax
0x1400130dc  lea     rax, WanIpDummyInterfaceDeleteComplete
0x1400130e3  cmovz   rdx, cs:qword_140009328
0x1400130eb  mov     [rsp+88h+var_50], rax
0x1400130f0  mov     rax, [rdx+8]
0x1400130f4  mov     rax, [rax+10h]
0x1400130f8  call    _guard_dispatch_icall
0x1400130fd  lea     rcx, [rbp+78h]; SpinLock
0x140013101  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013108  nop     dword ptr [rax+rax+00h]
0x14001310d  mov     rcx, r12; SpinLock
0x140013110  mov     bl, al
0x140013112  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140013119  nop     dword ptr [rax+rax+00h]
0x14001311e  mov     rcx, [rsp+88h+var_68]
0x140013123  mov     r9b, bl
0x140013126  mov     r8b, r15b
0x140013129  mov     rdx, rsi
0x14001312c  mov     eax, [rcx+4]
0x14001312f  mov     rcx, rbp
0x140013132  mov     [rsi+0A4h], eax
0x140013138  dec     dword ptr [rbp+0B8h]
0x14001313e  mov     qword ptr [rsi+58h], 0
0x140013146  mov     qword ptr [r14+80h], 0
0x140013151  call    WanpAddAdapterToIp
0x140013156  mov     ebx, eax
0x140013158  test    eax, eax
0x14001315a  js      short loc_14001317B
0x14001315c  mov     r9b, r15b
0x14001315f  mov     r8, r14
0x140013162  mov     rdx, rsi
0x140013165  mov     rcx, rbp
0x140013168  call    WanpIpAddSubInterface
0x14001316d  mov     ebx, eax
0x14001316f  test    eax, eax
0x140013171  jns     short loc_14001317B
0x140013173  mov     rcx, rsi; P
0x140013176  call    WanpDeleteInterfaceFromIp
0x14001317b  mov     rcx, [r14+50h]; SpinLock
0x14001317f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013186  nop     dword ptr [rax+rax+00h]
0x14001318b  mov     rcx, [r14+50h]; SpinLock
0x14001318f  mov     dl, al; NewIrql
0x140013191  mov     dword ptr [r14+7Ch], 2
0x140013199  call    cs:__imp_KeReleaseSpinLock
0x1400131a0  nop     dword ptr [rax+rax+00h]
0x1400131a5  or      edi, 0FFFFFFFFh
0x1400131a8  mov     eax, edi
0x1400131aa  lock xadd [r14+60h], eax
0x1400131b0  add     eax, edi
0x1400131b2  jnz     short loc_1400131BC
0x1400131b4  mov     rcx, r14; Entry
0x1400131b7  call    WanpDeleteConnEntry
0x1400131bc  mov     eax, edi
0x1400131be  lock xadd [rbp+80h], eax
0x1400131c6  add     eax, edi
0x1400131c8  jnz     short loc_1400131D2
0x1400131ca  mov     rcx, rbp; P
0x1400131cd  call    WanpDeleteAdapter
0x1400131d2  mov     eax, edi
0x1400131d4  lock xadd [rsi+40h], eax
0x1400131d9  add     eax, edi
0x1400131db  jnz     short loc_1400131EE
0x1400131dd  xor     edx, edx; Tag
0x1400131df  mov     rcx, rsi; P
0x1400131e2  call    cs:__imp_ExFreePoolWithTag
0x1400131e9  nop     dword ptr [rax+rax+00h]
0x1400131ee  lea     rcx, g_wrBindMutex
0x1400131f5  call    WanpReleaseResource
0x1400131fa  test    ebx, ebx
0x1400131fc  jns     short loc_140013228
0x1400131fe  jmp     short loc_140013224
0x140013200  lea     rcx, [rbp+78h]; SpinLock
0x140013204  mov     dl, r15b; NewIrql
0x140013207  call    cs:__imp_KeReleaseSpinLock
0x14001320e  nop     dword ptr [rax+rax+00h]
0x140013213  lea     rcx, g_wrBindMutex
0x14001321a  call    WanpReleaseResource
0x14001321f  mov     ebx, 0C000000Dh
0x140013224  mov     [r13+30h], ebx
0x140013228  mov     eax, ebx
0x14001322a  mov     rbx, [rsp+88h+arg_8]
0x140013232  add     rsp, 50h
0x140013236  pop     r15
0x140013238  pop     r14
0x14001323a  pop     r13
0x14001323c  pop     r12
0x14001323e  pop     rdi
0x14001323f  pop     rsi
0x140013240  pop     rbp
0x140013241  retn
```
