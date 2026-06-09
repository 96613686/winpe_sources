# IppFindNextHopInForwardPathSet

- ea: `0x140091ae0`
- end: `0x140091eb2`
- name: `IppFindNextHopInForwardPathSet`
- size: `978`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140091840`
- `0x140112800`

## callees

- `0x140074f90`
- `0x140091ae0`
- `0x140091ec0`
- `0x14010c5c0`
- `0x14010d0a8`
- `0x14011515c`
- `0x1401bfe60`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140091b89`
- `ntoskrnl!KfRaiseIrql` at `0x140091b89`
- `ntoskrnl!KeLowerIrql` at `0x140091d1f`
- `ntoskrnl!KeLowerIrql` at `0x140091d1f`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140091e70`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140091e70`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140091d67`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140091d67`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140091c24`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140091c24`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140091be9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140091db3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140091be9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140091db3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140091bfe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140091e25`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140091bfe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140091e25`
- `ntoskrnl!KeTestSpinLock` at `0x140091bcd`
- `ntoskrnl!KeTestSpinLock` at `0x140091bcd`
- `NETIO!RtlCompute37Hash` at `0x140091b50`
- `NETIO!RtlCompute37Hash` at `0x140091b75`
- `NETIO!RtlCompute37Hash` at `0x140091b50`
- `NETIO!RtlCompute37Hash` at `0x140091b75`

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
0x140091ae0  mov     [rsp+arg_18], rbx
0x140091ae5  mov     [rsp+Buf2], r8
0x140091aea  push    rbp
0x140091aeb  push    rsi
0x140091aec  push    rdi
0x140091aed  push    r12
0x140091aef  push    r13
0x140091af1  push    r14
0x140091af3  push    r15
0x140091af5  sub     rsp, 80h
0x140091afc  xor     eax, eax
0x140091afe  mov     [rsp+0B8h+Entry], 0
0x140091b0a  mov     [rsp+0B8h+Context.Signature], rax
0x140091b0f  lea     rsi, [rcx+500h]
0x140091b16  mov     qword ptr [rsp+0B8h+var_58.OldIrql], rax
0x140091b1b  mov     r14, rcx
0x140091b1e  mov     rax, [rcx+28h]
0x140091b22  xorps   xmm0, xmm0
0x140091b25  movups  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x140091b2a  mov     ebx, r9d
0x140091b2d  mov     r9, r8
0x140091b30  xorps   xmm1, xmm1
0x140091b33  mov     r12, rdx
0x140091b36  movups  xmmword ptr [rsp+0B8h+var_58.LockQueue.Next], xmm1
0x140091b3b  mov     rcx, [rax+10h]
0x140091b3f  mov     rdx, r9
0x140091b42  xor     r15d, r15d
0x140091b45  movzx   r8d, word ptr [rcx+6]
0x140091b4a  mov     ecx, cs:g_37HashSeed
0x140091b50  call    cs:__imp_RtlCompute37Hash
0x140091b57  nop     dword ptr [rax+rax+00h]
0x140091b5c  mov     edi, eax
0x140091b5e  test    r12, r12
0x140091b61  jz      short loc_140091B83
0x140091b63  mov     rax, [r14+28h]
0x140091b67  mov     rdx, r12
0x140091b6a  mov     rcx, [rax+10h]
0x140091b6e  movzx   r8d, word ptr [rcx+6]
0x140091b73  mov     ecx, edi
0x140091b75  call    cs:__imp_RtlCompute37Hash
0x140091b7c  nop     dword ptr [rax+rax+00h]
0x140091b81  mov     edi, eax
0x140091b83  mov     cl, 2; NewIrql
0x140091b85  bts     edi, 1Fh
0x140091b89  call    cs:__imp_KfRaiseIrql
0x140091b90  nop     dword ptr [rax+rax+00h]
0x140091b95  mov     ecx, gs:1A4h
0x140091b9d  xorps   xmm0, xmm0
0x140091ba0  mov     ebp, [rsi+8]
0x140091ba3  mov     r13d, ecx
0x140091ba6  and     rbp, r13
0x140091ba9  mov     [rsp+0B8h+arg_0], al
0x140091bb0  inc     rbp
0x140091bb3  xor     eax, eax
0x140091bb5  shl     rbp, 6
0x140091bb9  add     rbp, rsi
0x140091bbc  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140091bc1  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140091bc6  lock inc dword ptr [rbp+0]
0x140091bca  mov     rcx, rsi; SpinLock
0x140091bcd  call    cs:__imp_KeTestSpinLock
0x140091bd4  nop     dword ptr [rax+rax+00h]
0x140091bd9  test    al, al
0x140091bdb  jnz     short loc_140091C0A
0x140091bdd  lock dec dword ptr [rbp+0]
0x140091be1  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x140091be6  mov     rcx, rsi; SpinLock
0x140091be9  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140091bf0  nop     dword ptr [rax+rax+00h]
0x140091bf5  lock inc dword ptr [rbp+0]
0x140091bf9  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x140091bfe  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140091c05  nop     dword ptr [rax+rax+00h]
0x140091c0a  xorps   xmm0, xmm0
0x140091c0d  mov     edx, edi; Signature
0x140091c0f  lea     rbp, [rsi+158h]
0x140091c16  mov     rcx, rbp; HashTable
0x140091c19  lea     r8, [rsp+0B8h+Context]; Context
0x140091c1e  movdqu  xmmword ptr [rsp+0B8h+Context.ChainHead], xmm0
0x140091c24  call    cs:__imp_RtlLookupEntryHashTable
0x140091c2b  nop     dword ptr [rax+rax+00h]
0x140091c30  mov     rdi, rax
0x140091c33  test    rax, rax
0x140091c36  jz      loc_140091D4F
0x140091c3c  mov     rax, [r14+28h]
0x140091c40  mov     rdx, [rsp+0B8h+Buf2]; Buf2
0x140091c48  mov     rcx, [rax+10h]
0x140091c4c  movzx   ebp, word ptr [rcx+6]
0x140091c50  mov     rcx, [rdi+38h]; Buf1
0x140091c54  mov     r8d, ebp; Size
0x140091c57  call    memcmp
0x140091c5c  test    eax, eax
0x140091c5e  jnz     loc_140091D58
0x140091c64  mov     rcx, [rdi+40h]; Buf1
0x140091c68  test    rcx, rcx
0x140091c6b  jnz     loc_140091D78
0x140091c71  test    r12, r12
0x140091c74  jnz     loc_140091D58
0x140091c7a  mov     eax, [rsp+0B8h+arg_30]
0x140091c81  cmp     eax, [rdi+48h]
0x140091c84  jnz     loc_140091D58
0x140091c8a  mov     eax, ebx
0x140091c8c  xor     eax, [rdi+30h]
0x140091c8f  test    eax, 0FFFFFFFh
0x140091c94  jnz     loc_140091D58
0x140091c9a  mov     r8d, [rsp+0B8h+arg_20]
0x140091ca2  cmp     r8d, 0FFFFFFFFh
0x140091ca6  jz      short loc_140091CDD
0x140091ca8  mov     eax, [rdi+4Ch]
0x140091cab  cmp     [rsp+0B8h+arg_28], r15b
0x140091cb3  jnz     loc_140091D8F
0x140091cb9  mov     ecx, eax
0x140091cbb  mov     edx, r8d
0x140091cbe  and     ecx, 0FFFFFFFEh
0x140091cc1  and     edx, 0FFFFFFFEh
0x140091cc4  jnz     loc_140091D54
0x140091cca  test    ecx, ecx
0x140091ccc  jnz     loc_140091D58
0x140091cd2  not     al
0x140091cd4  xor     al, r8b
0x140091cd7  and     al, 1
0x140091cd9  test    al, al
0x140091cdb  jz      short loc_140091D58
0x140091cdd  mov     ecx, [r14+14h]
0x140091ce1  mov     eax, [rdi+60h]
0x140091ce4  cmp     ecx, eax
0x140091ce6  mov     rcx, rdi
0x140091ce9  jnz     loc_140091D9A
0x140091cef  call    IppGetNextHopFromForwardPathUnderLock
0x140091cf4  mov     rdi, [rsp+0B8h+Entry]
0x140091cfc  lea     rbp, [rsi+158h]
0x140091d03  mov     r15, rax
0x140091d06  mov     eax, [rsi+8]
0x140091d09  movzx   ecx, [rsp+0B8h+arg_0]; NewIrql
0x140091d11  and     rax, r13
0x140091d14  inc     rax
0x140091d17  shl     rax, 6
0x140091d1b  lock dec dword ptr [rax+rsi]
0x140091d1f  call    cs:__imp_KeLowerIrql
0x140091d26  nop     dword ptr [rax+rax+00h]
0x140091d2b  test    rdi, rdi
0x140091d2e  jnz     short loc_140091DAB
0x140091d30  mov     rbx, [rsp+0B8h+arg_18]
0x140091d38  mov     rax, r15
0x140091d3b  add     rsp, 80h
0x140091d42  pop     r15
0x140091d44  pop     r14
0x140091d46  pop     r13
0x140091d48  pop     r12
0x140091d4a  pop     rdi
0x140091d4b  pop     rsi
0x140091d4c  pop     rbp
0x140091d4d  retn
0x140091d4f  mov     rdi, r15
0x140091d52  jmp     short loc_140091D06
0x140091d54  cmp     edx, ecx
0x140091d56  jz      short loc_140091CDD
0x140091d58  lea     rbp, [rsi+158h]
0x140091d5f  mov     rcx, rbp; HashTable
0x140091d62  lea     rdx, [rsp+0B8h+Context]; Context
0x140091d67  call    cs:__imp_RtlGetNextEntryHashTable
0x140091d6e  nop     dword ptr [rax+rax+00h]
0x140091d73  jmp     loc_140091C30
0x140091d78  test    r12, r12
0x140091d7b  jz      short loc_140091D58
0x140091d7d  mov     r8, rbp; Size
0x140091d80  mov     rdx, r12; Buf2
0x140091d83  call    memcmp
0x140091d88  test    eax, eax
0x140091d8a  jmp     loc_140091C74
0x140091d8f  test    r8d, eax
0x140091d92  setnz   al
0x140091d95  jmp     loc_140091CD9
0x140091d9a  call    IppReferenceForwardPath
0x140091d9f  lea     rbp, [rsi+158h]
0x140091da6  jmp     loc_140091D06
0x140091dab  lea     rdx, [rsp+0B8h+var_58]; LockHandle
0x140091db0  mov     rcx, rsi; SpinLock
0x140091db3  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140091dba  nop     dword ptr [rax+rax+00h]
0x140091dbf  xor     edx, edx
0x140091dc1  cmp     [rsi+8], edx
0x140091dc4  jl      short loc_140091DE6
0x140091dc6  nop     word ptr [rax+rax+00000000h]
0x140091dd0  movsxd  rcx, edx
0x140091dd3  shl     rcx, 6
0x140091dd7  mov     eax, [rcx+rsi+40h]
0x140091ddb  test    eax, eax
0x140091ddd  jnz     short loc_140091DD7
0x140091ddf  inc     edx
0x140091de1  cmp     edx, [rsi+8]
0x140091de4  jle     short loc_140091DD0
0x140091de6  mov     ecx, [r14+14h]
0x140091dea  mov     eax, [rdi+60h]
0x140091ded  cmp     ecx, eax
0x140091def  jz      short loc_140091E15
0x140091df1  movzx   r9d, [rsp+0B8h+arg_28]
0x140091dfa  mov     rdx, rdi
0x140091dfd  mov     r8d, [rsp+0B8h+arg_20]
0x140091e05  mov     rcx, r14
0x140091e08  call    IppRefreshForwardPathUnderLock
0x140091e0d  test    al, al
0x140091e0f  jz      loc_140091EA4
0x140091e15  mov     rcx, rdi
0x140091e18  call    IppGetNextHopFromForwardPathUnderLock
0x140091e1d  mov     r15, rax
0x140091e20  lea     rcx, [rsp+0B8h+var_58]; LockHandle
0x140091e25  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140091e2c  nop     dword ptr [rax+rax+00h]
0x140091e31  mov     rcx, rdi
0x140091e34  call    IppDereferenceForwardPath
0x140091e39  jmp     loc_140091D30
0x140091e3e  and     al, 0FEh
0x140091e40  mov     [rdi+70h], al
0x140091e43  lea     rax, [rdi+20h]
0x140091e47  mov     rdx, [rax]
0x140091e4a  cmp     [rdx+8], rax
0x140091e4e  jnz     short loc_140091E59
0x140091e50  mov     rcx, [rax+8]
0x140091e54  cmp     [rcx], rax
0x140091e57  jz      short loc_140091E60
0x140091e59  mov     ecx, 3
0x140091e5e  int     29h; Win8: RtlFailFast(ecx)
0x140091e60  mov     [rcx], rdx
0x140091e63  xor     r8d, r8d; Context
0x140091e66  mov     [rdx+8], rcx
0x140091e6a  mov     rdx, rdi; Entry
0x140091e6d  mov     rcx, rbp; HashTable
0x140091e70  call    cs:__imp_RtlRemoveEntryHashTable
0x140091e77  nop     dword ptr [rax+rax+00h]
0x140091e7c  mov     edx, 6Eh ; 'n'
0x140091e81  mov     [rsp+0B8h+var_98], 80h; int
0x140091e89  mov     r8d, 5Ah ; 'Z'
0x140091e8f  mov     rcx, rbp; HashTable
0x140091e92  call    RtlRestructureHashTable
0x140091e97  mov     rcx, rdi
0x140091e9a  call    IppDereferenceForwardPath
0x140091e9f  jmp     loc_140091E20
0x140091ea4  movzx   eax, byte ptr [rdi+70h]
0x140091ea8  test    al, 1
0x140091eaa  jz      loc_140091E20
0x140091eb0  jmp     short loc_140091E3E
```
