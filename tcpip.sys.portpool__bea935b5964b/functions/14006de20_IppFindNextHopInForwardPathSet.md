# IppFindNextHopInForwardPathSet

- ea: `0x14006de20`
- end: `0x14006e1f2`
- name: `IppFindNextHopInForwardPathSet`
- size: `978`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004a420`
- `0x14006d990`
- `0x14011c810`

## callees

- `0x14006bdc8`
- `0x14006de20`
- `0x14006e200`
- `0x14009f8e0`
- `0x1401162c0`
- `0x14011f72c`
- `0x1401c1aa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14006dec9`
- `ntoskrnl!KfRaiseIrql` at `0x14006dec9`
- `ntoskrnl!KeLowerIrql` at `0x14006e05f`
- `ntoskrnl!KeLowerIrql` at `0x14006e05f`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14006e1b0`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14006e1b0`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14006e0a7`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14006e0a7`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006df64`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14006df64`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006df29`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006e0f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006df29`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006e0f3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14006df3e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14006e165`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14006df3e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14006e165`
- `ntoskrnl!KeTestSpinLock` at `0x14006df0d`
- `ntoskrnl!KeTestSpinLock` at `0x14006df0d`
- `NETIO!RtlCompute37Hash` at `0x14006de90`
- `NETIO!RtlCompute37Hash` at `0x14006deb5`
- `NETIO!RtlCompute37Hash` at `0x14006de90`
- `NETIO!RtlCompute37Hash` at `0x14006deb5`

## pseudocode

```c
__int64 __fastcall IppFindNextHopInForwardPathSet(
        __int64 a1,
        const void *a2,
        const void *a3,
        int a4,
        unsigned int a5,
        unsigned __int8 a6,
        int a7)
{
  __int64 v7; // rsi
  __int64 v9; // rax
  __int64 NextHopFromForwardPathUnderLock; // r15
  unsigned int v13; // edi
  unsigned int v14; // edi
  KIRQL v15; // al
  unsigned int LockArray_high; // r13d
  volatile signed __int32 *v17; // rbp
  struct _RTL_DYNAMIC_HASH_TABLE *v18; // rbp
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v20; // rdi
  size_t v21; // rbp
  const void *Signature; // rcx
  bool v23; // zf
  int Flink_high; // eax
  unsigned int v25; // ecx
  char v26; // al
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v27; // rcx
  int j; // edx
  struct _LIST_ENTRY *Blink; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY *v31; // rcx
  char v32; // al
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+30h] [rbp-88h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-70h] BYREF
  struct _KLOCK_QUEUE_HANDLE v35; // [rsp+60h] [rbp-58h] BYREF
  KIRQL v36; // [rsp+C0h] [rbp+8h]

  v7 = a1 + 1280;
  v9 = *(_QWORD *)(a1 + 40);
  memset(&Context, 0, sizeof(Context));
  memset(&v35, 0, sizeof(v35));
  NextHopFromForwardPathUnderLock = 0;
  v13 = RtlCompute37Hash((unsigned int)g_37HashSeed, a3, *(unsigned __int16 *)(*(_QWORD *)(v9 + 16) + 6LL));
  if ( a2 )
    v13 = RtlCompute37Hash(v13, a2, *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 6LL));
  v14 = v13 | 0x80000000;
  v15 = KfRaiseIrql(2u);
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v36 = v15;
  v17 = (volatile signed __int32 *)(v7 + (((LockArray_high & *(_DWORD *)(v7 + 8)) + 1LL) << 6));
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement(v17);
  if ( !KeTestSpinLock((PKSPIN_LOCK)v7) )
  {
    _InterlockedDecrement(v17);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v7, &LockHandle);
    _InterlockedIncrement(v17);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v18 = (struct _RTL_DYNAMIC_HASH_TABLE *)(v7 + 344);
  *(_OWORD *)&Context.ChainHead = 0;
  for ( i = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v7 + 344), v14, &Context);
        ;
        i = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v7 + 344), &Context) )
  {
    v20 = i;
    if ( !i )
    {
      v20 = 0;
      goto LABEL_21;
    }
    v21 = *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 6LL);
    if ( !memcmp(i[2].Linkage.Blink, a3, v21) )
    {
      Signature = (const void *)v20[2].Signature;
      if ( Signature )
      {
        if ( !a2 )
          goto LABEL_25;
        v23 = memcmp(Signature, a2, v21) == 0;
      }
      else
      {
        v23 = a2 == 0;
      }
      if ( v23 && a7 == LODWORD(v20[3].Linkage.Flink) && ((LODWORD(v20[2].Linkage.Flink) ^ a4) & 0xFFFFFFF) == 0 )
        break;
    }
LABEL_25:
    v18 = (struct _RTL_DYNAMIC_HASH_TABLE *)(v7 + 344);
  }
  if ( a5 == -1 )
    goto LABEL_19;
  Flink_high = HIDWORD(v20[3].Linkage.Flink);
  if ( a6 )
  {
    v26 = (Flink_high & a5) != 0;
LABEL_18:
    if ( v26 )
      goto LABEL_19;
    goto LABEL_25;
  }
  v25 = Flink_high & 0xFFFFFFFE;
  if ( (a5 & 0xFFFFFFFE) == 0 )
  {
    if ( v25 )
      goto LABEL_25;
    v26 = (a5 ^ ~(_BYTE)Flink_high) & 1;
    goto LABEL_18;
  }
  if ( (a5 & 0xFFFFFFFE) != v25 )
    goto LABEL_25;
LABEL_19:
  v27 = v20;
  if ( *(_DWORD *)(a1 + 20) == LODWORD(v20[4].Linkage.Flink) )
  {
    v20 = 0;
    v18 = (struct _RTL_DYNAMIC_HASH_TABLE *)(v7 + 344);
    NextHopFromForwardPathUnderLock = IppGetNextHopFromForwardPathUnderLock(v27);
  }
  else
  {
    IppReferenceForwardPath(v20);
    v18 = (struct _RTL_DYNAMIC_HASH_TABLE *)(v7 + 344);
  }
LABEL_21:
  _InterlockedDecrement((volatile signed __int32 *)((((LockArray_high & *(_DWORD *)(v7 + 8)) + 1LL) << 6) + v7));
  KeLowerIrql(v36);
  if ( v20 )
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)v7, &v35);
    for ( j = 0; j <= *(_DWORD *)(v7 + 8); ++j )
    {
      while ( *(_DWORD *)(((__int64)j << 6) + v7 + 64) )
        ;
    }
    if ( *(_DWORD *)(a1 + 20) == LODWORD(v20[4].Linkage.Flink)
      || (unsigned __int8)IppRefreshForwardPathUnderLock(a1, v20, a5, a6) )
    {
      NextHopFromForwardPathUnderLock = IppGetNextHopFromForwardPathUnderLock(v20);
    }
    else
    {
      v32 = v20[4].Signature;
      if ( (v32 & 1) != 0 )
      {
        LOBYTE(v20[4].Signature) = v32 & 0xFE;
        Blink = v20[1].Linkage.Blink;
        if ( (struct _LIST_ENTRY **)Blink->Blink != &v20[1].Linkage.Blink
          || (v31 = (PRTL_DYNAMIC_HASH_TABLE_ENTRY *)v20[1].Signature,
              *v31 != (PRTL_DYNAMIC_HASH_TABLE_ENTRY)&v20[1].Linkage.Blink) )
        {
          __fastfail(3u);
        }
        *v31 = (PRTL_DYNAMIC_HASH_TABLE_ENTRY)Blink;
        Blink->Blink = (struct _LIST_ENTRY *)v31;
        RtlRemoveEntryHashTable(v18, v20, 0);
        RtlRestructureHashTable(v18, 128);
        IppDereferenceForwardPath(v20);
      }
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&v35);
    IppDereferenceForwardPath(v20);
  }
  return NextHopFromForwardPathUnderLock;
}

```

## disassembly

```asm
0x14006de20  mov     [rsp+arg_18], rbx
0x14006de25  mov     [rsp+Buf2], r8
0x14006de2a  push    rbp
0x14006de2b  push    rsi
0x14006de2c  push    rdi
0x14006de2d  push    r12
0x14006de2f  push    r13
0x14006de31  push    r14
0x14006de33  push    r15
0x14006de35  sub     rsp, 80h
0x14006de3c  xor     eax, eax
0x14006de3e  mov     [rsp+0B8h+Entry], 0
0x14006de4a  mov     [rsp+0B8h+Context.Signature], rax
0x14006de4f  lea     rsi, [rcx+500h]
0x14006de56  mov     qword ptr [rsp+0B8h+var_58.OldIrql], rax
0x14006de5b  mov     r14, rcx
0x14006de5e  mov     rax, [rcx+28h]
0x14006de62  xorps   xmm0, xmm0
0x14006de65  movups  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x14006de6a  mov     ebx, r9d
0x14006de6d  mov     r9, r8
0x14006de70  xorps   xmm1, xmm1
0x14006de73  mov     r12, rdx
0x14006de76  movups  xmmword ptr [rsp+0B8h+var_58.LockQueue.Next], xmm1
0x14006de7b  mov     rcx, [rax+10h]
0x14006de7f  mov     rdx, r9
0x14006de82  xor     r15d, r15d
0x14006de85  movzx   r8d, word ptr [rcx+6]
0x14006de8a  mov     ecx, cs:g_37HashSeed
0x14006de90  call    cs:__imp_RtlCompute37Hash
0x14006de97  nop     dword ptr [rax+rax+00h]
0x14006de9c  mov     edi, eax
0x14006de9e  test    r12, r12
0x14006dea1  jz      short loc_14006DEC3
0x14006dea3  mov     rax, [r14+28h]
0x14006dea7  mov     rdx, r12
0x14006deaa  mov     rcx, [rax+10h]
0x14006deae  movzx   r8d, word ptr [rcx+6]
0x14006deb3  mov     ecx, edi
0x14006deb5  call    cs:__imp_RtlCompute37Hash
0x14006debc  nop     dword ptr [rax+rax+00h]
0x14006dec1  mov     edi, eax
0x14006dec3  mov     cl, 2; NewIrql
0x14006dec5  bts     edi, 1Fh
0x14006dec9  call    cs:__imp_KfRaiseIrql
0x14006ded0  nop     dword ptr [rax+rax+00h]
0x14006ded5  mov     ecx, gs:1A4h
0x14006dedd  xorps   xmm0, xmm0
0x14006dee0  mov     ebp, [rsi+8]
0x14006dee3  mov     r13d, ecx
0x14006dee6  and     rbp, r13
0x14006dee9  mov     [rsp+0B8h+arg_0], al
0x14006def0  inc     rbp
0x14006def3  xor     eax, eax
0x14006def5  shl     rbp, 6
0x14006def9  add     rbp, rsi
0x14006defc  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x14006df01  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x14006df06  lock inc dword ptr [rbp+0]
0x14006df0a  mov     rcx, rsi; SpinLock
0x14006df0d  call    cs:__imp_KeTestSpinLock
0x14006df14  nop     dword ptr [rax+rax+00h]
0x14006df19  test    al, al
0x14006df1b  jnz     short loc_14006DF4A
0x14006df1d  lock dec dword ptr [rbp+0]
0x14006df21  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x14006df26  mov     rcx, rsi; SpinLock
0x14006df29  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14006df30  nop     dword ptr [rax+rax+00h]
0x14006df35  lock inc dword ptr [rbp+0]
0x14006df39  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14006df3e  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14006df45  nop     dword ptr [rax+rax+00h]
0x14006df4a  xorps   xmm0, xmm0
0x14006df4d  mov     edx, edi; Signature
0x14006df4f  lea     rbp, [rsi+158h]
0x14006df56  mov     rcx, rbp; HashTable
0x14006df59  lea     r8, [rsp+0B8h+Context]; Context
0x14006df5e  movdqu  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x14006df64  call    cs:__imp_RtlLookupEntryHashTable
0x14006df6b  nop     dword ptr [rax+rax+00h]
0x14006df70  mov     rdi, rax
0x14006df73  test    rax, rax
0x14006df76  jz      loc_14006E08F
0x14006df7c  mov     rax, [r14+28h]
0x14006df80  mov     rdx, [rsp+0B8h+Buf2]; Buf2
0x14006df88  mov     rcx, [rax+10h]
0x14006df8c  movzx   ebp, word ptr [rcx+6]
0x14006df90  mov     rcx, [rdi+38h]; Buf1
0x14006df94  mov     r8d, ebp; Size
0x14006df97  call    memcmp
0x14006df9c  test    eax, eax
0x14006df9e  jnz     loc_14006E098
0x14006dfa4  mov     rcx, [rdi+40h]; Buf1
0x14006dfa8  test    rcx, rcx
0x14006dfab  jnz     loc_14006E0B8
0x14006dfb1  test    r12, r12
0x14006dfb4  jnz     loc_14006E098
0x14006dfba  mov     eax, [rsp+0B8h+arg_30]
0x14006dfc1  cmp     eax, [rdi+48h]
0x14006dfc4  jnz     loc_14006E098
0x14006dfca  mov     eax, ebx
0x14006dfcc  xor     eax, [rdi+30h]
0x14006dfcf  test    eax, 0FFFFFFFh
0x14006dfd4  jnz     loc_14006E098
0x14006dfda  mov     r8d, [rsp+0B8h+arg_20]
0x14006dfe2  cmp     r8d, 0FFFFFFFFh
0x14006dfe6  jz      short loc_14006E01D
0x14006dfe8  mov     eax, [rdi+4Ch]
0x14006dfeb  cmp     [rsp+0B8h+arg_28], r15b
0x14006dff3  jnz     loc_14006E0CF
0x14006dff9  mov     ecx, eax
0x14006dffb  mov     edx, r8d
0x14006dffe  and     ecx, 0FFFFFFFEh
0x14006e001  and     edx, 0FFFFFFFEh
0x14006e004  jnz     loc_14006E094
0x14006e00a  test    ecx, ecx
0x14006e00c  jnz     loc_14006E098
0x14006e012  not     al
0x14006e014  xor     al, r8b
0x14006e017  and     al, 1
0x14006e019  test    al, al
0x14006e01b  jz      short loc_14006E098
0x14006e01d  mov     ecx, [r14+14h]
0x14006e021  mov     eax, [rdi+60h]
0x14006e024  cmp     ecx, eax
0x14006e026  mov     rcx, rdi
0x14006e029  jnz     loc_14006E0DA
0x14006e02f  call    IppGetNextHopFromForwardPathUnderLock
0x14006e034  mov     rdi, [rsp+0B8h+Entry]
0x14006e03c  lea     rbp, [rsi+158h]
0x14006e043  mov     r15, rax
0x14006e046  mov     eax, [rsi+8]
0x14006e049  movzx   ecx, [rsp+0B8h+arg_0]; NewIrql
0x14006e051  and     rax, r13
0x14006e054  inc     rax
0x14006e057  shl     rax, 6
0x14006e05b  lock dec dword ptr [rax+rsi]
0x14006e05f  call    cs:__imp_KeLowerIrql
0x14006e066  nop     dword ptr [rax+rax+00h]
0x14006e06b  test    rdi, rdi
0x14006e06e  jnz     short loc_14006E0EB
0x14006e070  mov     rbx, [rsp+0B8h+arg_18]
0x14006e078  mov     rax, r15
0x14006e07b  add     rsp, 80h
0x14006e082  pop     r15
0x14006e084  pop     r14
0x14006e086  pop     r13
0x14006e088  pop     r12
0x14006e08a  pop     rdi
0x14006e08b  pop     rsi
0x14006e08c  pop     rbp
0x14006e08d  retn
0x14006e08f  mov     rdi, r15
0x14006e092  jmp     short loc_14006E046
0x14006e094  cmp     edx, ecx
0x14006e096  jz      short loc_14006E01D
0x14006e098  lea     rbp, [rsi+158h]
0x14006e09f  mov     rcx, rbp; HashTable
0x14006e0a2  lea     rdx, [rsp+0B8h+Context]; Context
0x14006e0a7  call    cs:__imp_RtlGetNextEntryHashTable
0x14006e0ae  nop     dword ptr [rax+rax+00h]
0x14006e0b3  jmp     loc_14006DF70
0x14006e0b8  test    r12, r12
0x14006e0bb  jz      short loc_14006E098
0x14006e0bd  mov     r8, rbp; Size
0x14006e0c0  mov     rdx, r12; Buf2
0x14006e0c3  call    memcmp
0x14006e0c8  test    eax, eax
0x14006e0ca  jmp     loc_14006DFB4
0x14006e0cf  test    r8d, eax
0x14006e0d2  setnz   al
0x14006e0d5  jmp     loc_14006E019
0x14006e0da  call    IppReferenceForwardPath
0x14006e0df  lea     rbp, [rsi+158h]
0x14006e0e6  jmp     loc_14006E046
0x14006e0eb  lea     rdx, [rsp+0B8h+var_58]; LockHandle
0x14006e0f0  mov     rcx, rsi; SpinLock
0x14006e0f3  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14006e0fa  nop     dword ptr [rax+rax+00h]
0x14006e0ff  xor     edx, edx
0x14006e101  cmp     [rsi+8], edx
0x14006e104  jl      short loc_14006E126
0x14006e106  nop     word ptr [rax+rax+00000000h]
0x14006e110  movsxd  rcx, edx
0x14006e113  shl     rcx, 6
0x14006e117  mov     eax, [rcx+rsi+40h]
0x14006e11b  test    eax, eax
0x14006e11d  jnz     short loc_14006E117
0x14006e11f  inc     edx
0x14006e121  cmp     edx, [rsi+8]
0x14006e124  jle     short loc_14006E110
0x14006e126  mov     ecx, [r14+14h]
0x14006e12a  mov     eax, [rdi+60h]
0x14006e12d  cmp     ecx, eax
0x14006e12f  jz      short loc_14006E155
0x14006e131  movzx   r9d, [rsp+0B8h+arg_28]
0x14006e13a  mov     rdx, rdi
0x14006e13d  mov     r8d, [rsp+0B8h+arg_20]
0x14006e145  mov     rcx, r14
0x14006e148  call    IppRefreshForwardPathUnderLock
0x14006e14d  test    al, al
0x14006e14f  jz      loc_14006E1E4
0x14006e155  mov     rcx, rdi
0x14006e158  call    IppGetNextHopFromForwardPathUnderLock
0x14006e15d  mov     r15, rax
0x14006e160  lea     rcx, [rsp+0B8h+var_58]; LockHandle
0x14006e165  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14006e16c  nop     dword ptr [rax+rax+00h]
0x14006e171  mov     rcx, rdi
0x14006e174  call    IppDereferenceForwardPath
0x14006e179  jmp     loc_14006E070
0x14006e17e  and     al, 0FEh
0x14006e180  mov     [rdi+70h], al
0x14006e183  lea     rax, [rdi+20h]
0x14006e187  mov     rdx, [rax]
0x14006e18a  cmp     [rdx+8], rax
0x14006e18e  jnz     short loc_14006E199
0x14006e190  mov     rcx, [rax+8]
0x14006e194  cmp     [rcx], rax
0x14006e197  jz      short loc_14006E1A0
0x14006e199  mov     ecx, 3
0x14006e19e  int     29h; Win8: RtlFailFast(ecx)
0x14006e1a0  mov     [rcx], rdx
0x14006e1a3  xor     r8d, r8d; Context
0x14006e1a6  mov     [rdx+8], rcx
0x14006e1aa  mov     rdx, rdi; Entry
0x14006e1ad  mov     rcx, rbp; HashTable
0x14006e1b0  call    cs:__imp_RtlRemoveEntryHashTable
0x14006e1b7  nop     dword ptr [rax+rax+00h]
0x14006e1bc  mov     edx, 6Eh ; 'n'
0x14006e1c1  mov     [rsp+0B8h+var_98], 80h; int
0x14006e1c9  mov     r8d, 5Ah ; 'Z'
0x14006e1cf  mov     rcx, rbp; HashTable
0x14006e1d2  call    RtlRestructureHashTable
0x14006e1d7  mov     rcx, rdi
0x14006e1da  call    IppDereferenceForwardPath
0x14006e1df  jmp     loc_14006E160
0x14006e1e4  movzx   eax, byte ptr [rdi+70h]
0x14006e1e8  test    al, 1
0x14006e1ea  jz      loc_14006E160
0x14006e1f0  jmp     short loc_14006E17E
```
