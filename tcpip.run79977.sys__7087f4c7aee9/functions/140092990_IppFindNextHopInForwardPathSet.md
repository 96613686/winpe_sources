# IppFindNextHopInForwardPathSet

- ea: `0x140092990`
- end: `0x140092d62`
- name: `IppFindNextHopInForwardPathSet`
- size: `978`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400926f0`
- `0x140112940`

## callees

- `0x140075230`
- `0x140092990`
- `0x140092d70`
- `0x14010c700`
- `0x14010d1e8`
- `0x14011529c`
- `0x1401bffa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140092a39`
- `ntoskrnl!KfRaiseIrql` at `0x140092a39`
- `ntoskrnl!KeLowerIrql` at `0x140092bcf`
- `ntoskrnl!KeLowerIrql` at `0x140092bcf`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140092d20`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140092d20`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140092c17`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140092c17`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140092ad4`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140092ad4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140092a99`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140092c63`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140092a99`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140092c63`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140092aae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140092cd5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140092aae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140092cd5`
- `ntoskrnl!KeTestSpinLock` at `0x140092a7d`
- `ntoskrnl!KeTestSpinLock` at `0x140092a7d`
- `NETIO!RtlCompute37Hash` at `0x140092a00`
- `NETIO!RtlCompute37Hash` at `0x140092a25`
- `NETIO!RtlCompute37Hash` at `0x140092a00`
- `NETIO!RtlCompute37Hash` at `0x140092a25`

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
0x140092990  mov     [rsp+arg_18], rbx
0x140092995  mov     [rsp+Buf2], r8
0x14009299a  push    rbp
0x14009299b  push    rsi
0x14009299c  push    rdi
0x14009299d  push    r12
0x14009299f  push    r13
0x1400929a1  push    r14
0x1400929a3  push    r15
0x1400929a5  sub     rsp, 80h
0x1400929ac  xor     eax, eax
0x1400929ae  mov     [rsp+0B8h+Entry], 0
0x1400929ba  mov     [rsp+0B8h+Context.Signature], rax
0x1400929bf  lea     rsi, [rcx+500h]
0x1400929c6  mov     qword ptr [rsp+0B8h+var_58.OldIrql], rax
0x1400929cb  mov     r14, rcx
0x1400929ce  mov     rax, [rcx+28h]
0x1400929d2  xorps   xmm0, xmm0
0x1400929d5  movups  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x1400929da  mov     ebx, r9d
0x1400929dd  mov     r9, r8
0x1400929e0  xorps   xmm1, xmm1
0x1400929e3  mov     r12, rdx
0x1400929e6  movups  xmmword ptr [rsp+0B8h+var_58.LockQueue.Next], xmm1
0x1400929eb  mov     rcx, [rax+10h]
0x1400929ef  mov     rdx, r9
0x1400929f2  xor     r15d, r15d
0x1400929f5  movzx   r8d, word ptr [rcx+6]
0x1400929fa  mov     ecx, cs:g_37HashSeed
0x140092a00  call    cs:__imp_RtlCompute37Hash
0x140092a07  nop     dword ptr [rax+rax+00h]
0x140092a0c  mov     edi, eax
0x140092a0e  test    r12, r12
0x140092a11  jz      short loc_140092A33
0x140092a13  mov     rax, [r14+28h]
0x140092a17  mov     rdx, r12
0x140092a1a  mov     rcx, [rax+10h]
0x140092a1e  movzx   r8d, word ptr [rcx+6]
0x140092a23  mov     ecx, edi
0x140092a25  call    cs:__imp_RtlCompute37Hash
0x140092a2c  nop     dword ptr [rax+rax+00h]
0x140092a31  mov     edi, eax
0x140092a33  mov     cl, 2; NewIrql
0x140092a35  bts     edi, 1Fh
0x140092a39  call    cs:__imp_KfRaiseIrql
0x140092a40  nop     dword ptr [rax+rax+00h]
0x140092a45  mov     ecx, gs:1A4h
0x140092a4d  xorps   xmm0, xmm0
0x140092a50  mov     ebp, [rsi+8]
0x140092a53  mov     r13d, ecx
0x140092a56  and     rbp, r13
0x140092a59  mov     [rsp+0B8h+arg_0], al
0x140092a60  inc     rbp
0x140092a63  xor     eax, eax
0x140092a65  shl     rbp, 6
0x140092a69  add     rbp, rsi
0x140092a6c  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140092a71  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140092a76  lock inc dword ptr [rbp+0]
0x140092a7a  mov     rcx, rsi; SpinLock
0x140092a7d  call    cs:__imp_KeTestSpinLock
0x140092a84  nop     dword ptr [rax+rax+00h]
0x140092a89  test    al, al
0x140092a8b  jnz     short loc_140092ABA
0x140092a8d  lock dec dword ptr [rbp+0]
0x140092a91  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x140092a96  mov     rcx, rsi; SpinLock
0x140092a99  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140092aa0  nop     dword ptr [rax+rax+00h]
0x140092aa5  lock inc dword ptr [rbp+0]
0x140092aa9  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x140092aae  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140092ab5  nop     dword ptr [rax+rax+00h]
0x140092aba  xorps   xmm0, xmm0
0x140092abd  mov     edx, edi; Signature
0x140092abf  lea     rbp, [rsi+158h]
0x140092ac6  mov     rcx, rbp; HashTable
0x140092ac9  lea     r8, [rsp+0B8h+Context]; Context
0x140092ace  movdqu  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x140092ad4  call    cs:__imp_RtlLookupEntryHashTable
0x140092adb  nop     dword ptr [rax+rax+00h]
0x140092ae0  mov     rdi, rax
0x140092ae3  test    rax, rax
0x140092ae6  jz      loc_140092BFF
0x140092aec  mov     rax, [r14+28h]
0x140092af0  mov     rdx, [rsp+0B8h+Buf2]; Buf2
0x140092af8  mov     rcx, [rax+10h]
0x140092afc  movzx   ebp, word ptr [rcx+6]
0x140092b00  mov     rcx, [rdi+38h]; Buf1
0x140092b04  mov     r8d, ebp; Size
0x140092b07  call    memcmp
0x140092b0c  test    eax, eax
0x140092b0e  jnz     loc_140092C08
0x140092b14  mov     rcx, [rdi+40h]; Buf1
0x140092b18  test    rcx, rcx
0x140092b1b  jnz     loc_140092C28
0x140092b21  test    r12, r12
0x140092b24  jnz     loc_140092C08
0x140092b2a  mov     eax, [rsp+0B8h+arg_30]
0x140092b31  cmp     eax, [rdi+48h]
0x140092b34  jnz     loc_140092C08
0x140092b3a  mov     eax, ebx
0x140092b3c  xor     eax, [rdi+30h]
0x140092b3f  test    eax, 0FFFFFFFh
0x140092b44  jnz     loc_140092C08
0x140092b4a  mov     r8d, [rsp+0B8h+arg_20]
0x140092b52  cmp     r8d, 0FFFFFFFFh
0x140092b56  jz      short loc_140092B8D
0x140092b58  mov     eax, [rdi+4Ch]
0x140092b5b  cmp     [rsp+0B8h+arg_28], r15b
0x140092b63  jnz     loc_140092C3F
0x140092b69  mov     ecx, eax
0x140092b6b  mov     edx, r8d
0x140092b6e  and     ecx, 0FFFFFFFEh
0x140092b71  and     edx, 0FFFFFFFEh
0x140092b74  jnz     loc_140092C04
0x140092b7a  test    ecx, ecx
0x140092b7c  jnz     loc_140092C08
0x140092b82  not     al
0x140092b84  xor     al, r8b
0x140092b87  and     al, 1
0x140092b89  test    al, al
0x140092b8b  jz      short loc_140092C08
0x140092b8d  mov     ecx, [r14+14h]
0x140092b91  mov     eax, [rdi+60h]
0x140092b94  cmp     ecx, eax
0x140092b96  mov     rcx, rdi
0x140092b99  jnz     loc_140092C4A
0x140092b9f  call    IppGetNextHopFromForwardPathUnderLock
0x140092ba4  mov     rdi, [rsp+0B8h+Entry]
0x140092bac  lea     rbp, [rsi+158h]
0x140092bb3  mov     r15, rax
0x140092bb6  mov     eax, [rsi+8]
0x140092bb9  movzx   ecx, [rsp+0B8h+arg_0]; NewIrql
0x140092bc1  and     rax, r13
0x140092bc4  inc     rax
0x140092bc7  shl     rax, 6
0x140092bcb  lock dec dword ptr [rax+rsi]
0x140092bcf  call    cs:__imp_KeLowerIrql
0x140092bd6  nop     dword ptr [rax+rax+00h]
0x140092bdb  test    rdi, rdi
0x140092bde  jnz     short loc_140092C5B
0x140092be0  mov     rbx, [rsp+0B8h+arg_18]
0x140092be8  mov     rax, r15
0x140092beb  add     rsp, 80h
0x140092bf2  pop     r15
0x140092bf4  pop     r14
0x140092bf6  pop     r13
0x140092bf8  pop     r12
0x140092bfa  pop     rdi
0x140092bfb  pop     rsi
0x140092bfc  pop     rbp
0x140092bfd  retn
0x140092bff  mov     rdi, r15
0x140092c02  jmp     short loc_140092BB6
0x140092c04  cmp     edx, ecx
0x140092c06  jz      short loc_140092B8D
0x140092c08  lea     rbp, [rsi+158h]
0x140092c0f  mov     rcx, rbp; HashTable
0x140092c12  lea     rdx, [rsp+0B8h+Context]; Context
0x140092c17  call    cs:__imp_RtlGetNextEntryHashTable
0x140092c1e  nop     dword ptr [rax+rax+00h]
0x140092c23  jmp     loc_140092AE0
0x140092c28  test    r12, r12
0x140092c2b  jz      short loc_140092C08
0x140092c2d  mov     r8, rbp; Size
0x140092c30  mov     rdx, r12; Buf2
0x140092c33  call    memcmp
0x140092c38  test    eax, eax
0x140092c3a  jmp     loc_140092B24
0x140092c3f  test    r8d, eax
0x140092c42  setnz   al
0x140092c45  jmp     loc_140092B89
0x140092c4a  call    IppReferenceForwardPath
0x140092c4f  lea     rbp, [rsi+158h]
0x140092c56  jmp     loc_140092BB6
0x140092c5b  lea     rdx, [rsp+0B8h+var_58]; LockHandle
0x140092c60  mov     rcx, rsi; SpinLock
0x140092c63  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140092c6a  nop     dword ptr [rax+rax+00h]
0x140092c6f  xor     edx, edx
0x140092c71  cmp     [rsi+8], edx
0x140092c74  jl      short loc_140092C96
0x140092c76  nop     word ptr [rax+rax+00000000h]
0x140092c80  movsxd  rcx, edx
0x140092c83  shl     rcx, 6
0x140092c87  mov     eax, [rcx+rsi+40h]
0x140092c8b  test    eax, eax
0x140092c8d  jnz     short loc_140092C87
0x140092c8f  inc     edx
0x140092c91  cmp     edx, [rsi+8]
0x140092c94  jle     short loc_140092C80
0x140092c96  mov     ecx, [r14+14h]
0x140092c9a  mov     eax, [rdi+60h]
0x140092c9d  cmp     ecx, eax
0x140092c9f  jz      short loc_140092CC5
0x140092ca1  movzx   r9d, [rsp+0B8h+arg_28]
0x140092caa  mov     rdx, rdi
0x140092cad  mov     r8d, [rsp+0B8h+arg_20]
0x140092cb5  mov     rcx, r14
0x140092cb8  call    IppRefreshForwardPathUnderLock
0x140092cbd  test    al, al
0x140092cbf  jz      loc_140092D54
0x140092cc5  mov     rcx, rdi
0x140092cc8  call    IppGetNextHopFromForwardPathUnderLock
0x140092ccd  mov     r15, rax
0x140092cd0  lea     rcx, [rsp+0B8h+var_58]; LockHandle
0x140092cd5  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140092cdc  nop     dword ptr [rax+rax+00h]
0x140092ce1  mov     rcx, rdi
0x140092ce4  call    IppDereferenceForwardPath
0x140092ce9  jmp     loc_140092BE0
0x140092cee  and     al, 0FEh
0x140092cf0  mov     [rdi+70h], al
0x140092cf3  lea     rax, [rdi+20h]
0x140092cf7  mov     rdx, [rax]
0x140092cfa  cmp     [rdx+8], rax
0x140092cfe  jnz     short loc_140092D09
0x140092d00  mov     rcx, [rax+8]
0x140092d04  cmp     [rcx], rax
0x140092d07  jz      short loc_140092D10
0x140092d09  mov     ecx, 3
0x140092d0e  int     29h; Win8: RtlFailFast(ecx)
0x140092d10  mov     [rcx], rdx
0x140092d13  xor     r8d, r8d; Context
0x140092d16  mov     [rdx+8], rcx
0x140092d1a  mov     rdx, rdi; Entry
0x140092d1d  mov     rcx, rbp; HashTable
0x140092d20  call    cs:__imp_RtlRemoveEntryHashTable
0x140092d27  nop     dword ptr [rax+rax+00h]
0x140092d2c  mov     edx, 6Eh ; 'n'
0x140092d31  mov     [rsp+0B8h+var_98], 80h; int
0x140092d39  mov     r8d, 5Ah ; 'Z'
0x140092d3f  mov     rcx, rbp; HashTable
0x140092d42  call    RtlRestructureHashTable
0x140092d47  mov     rcx, rdi
0x140092d4a  call    IppDereferenceForwardPath
0x140092d4f  jmp     loc_140092CD0
0x140092d54  movzx   eax, byte ptr [rdi+70h]
0x140092d58  test    al, 1
0x140092d5a  jz      loc_140092CD0
0x140092d60  jmp     short loc_140092CEE
```
