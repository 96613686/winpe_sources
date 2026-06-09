# WanIpSendPackets

- ea: `0x140015440`
- end: `0x140015b75`
- name: `WanIpSendPackets`
- size: `1845`
- prototype: `void __fastcall(char *Entry, unsigned __int8, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140001dd0`
- `0x1400050b0`
- `0x14000f728`
- `0x140015440`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14001582a`
- `ntoskrnl!RtlCompareMemory` at `0x140015874`
- `ntoskrnl!RtlCompareMemory` at `0x14001582a`
- `ntoskrnl!RtlCompareMemory` at `0x140015874`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400159c4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400159c4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400154d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400154d2`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400156b8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140015aad`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400156b8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140015aad`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015508`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015508`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400156cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400157ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400158b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015ac5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400156cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400157ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400158b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015ac5`
- `NETIO!NetioAdvanceNetBufferList` at `0x140015a3d`
- `NETIO!NetioAdvanceNetBufferList` at `0x140015a3d`
- `NETIO!NetioDereferenceNetBufferList` at `0x140015911`
- `NETIO!NetioDereferenceNetBufferList` at `0x140015911`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14001580a`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x14001580a`
- `NETIO!NetioRetreatNetBufferList` at `0x1400155d0`
- `NETIO!NetioRetreatNetBufferList` at `0x1400155d0`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferList` at `0x1400158d6`
- `NETIO!NetioAllocateAndReferenceCloneNetBufferList` at `0x1400158d6`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400157a3`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400157a3`
- `NDIS!NdisSendNetBufferLists` at `0x140015712`
- `NDIS!NdisSendNetBufferLists` at `0x140015712`
- `NDIS!NdisFreeNetBufferListContext` at `0x140015a29`
- `NDIS!NdisFreeNetBufferListContext` at `0x140015a29`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400155a2`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400155a2`

## pseudocode

```c
void __fastcall WanIpSendPackets(char *Entry, unsigned __int8 a2, _QWORD *a3)
{
  PNET_BUFFER_LIST *p_NetBufferLists; // rsi
  unsigned __int8 v5; // bp
  __int64 v7; // r13
  char v8; // r14
  char v9; // cl
  KSPIN_LOCK *v10; // rcx
  PKSPIN_LOCK *v11; // rbx
  KIRQL v12; // al
  int v13; // ecx
  _DWORD *v14; // r12
  __int64 v15; // rbx
  struct _NET_BUFFER_LIST *v16; // rbp
  struct _NET_BUFFER *FirstNetBuffer; // rcx
  NDIS_STATUS PacketIPInfo; // esi
  PNET_BUFFER v19; // rbx
  char *v20; // rsi
  PMDL CurrentMdl; // r10
  char *MappedSystemVa; // rax
  char *v23; // rdx
  __int16 v24; // ax
  NDIS_HANDLE v25; // rcx
  PNET_BUFFER_LIST *v26; // rbx
  ULONG v27; // r9d
  NDIS_HANDLE v28; // rcx
  __int64 v29; // xmm0_8
  PKSPIN_LOCK *v30; // rcx
  KIRQL v31; // r14
  PNET_BUFFER_LIST *p_Next; // rbx
  PNET_BUFFER_LIST v33; // rcx
  PNET_BUFFER_LIST n; // rax
  unsigned int k; // ebx
  unsigned int *v36; // rcx
  __int64 v37; // rax
  unsigned int m; // ebx
  unsigned int v39; // ebx
  PNET_BUFFER_LIST v40; // r14
  struct _NET_BUFFER_LIST *Alignment; // rbx
  struct _NET_BUFFER_LIST *v42; // rax
  unsigned int j; // ebx
  struct _NET_BUFFER_LIST *v44; // rax
  KIRQL v45; // [rsp+30h] [rbp-C8h]
  char v47; // [rsp+32h] [rbp-C6h]
  unsigned int i; // [rsp+38h] [rbp-C0h]
  __int128 Source2; // [rsp+40h] [rbp-B8h] BYREF
  ULONG SendFlags; // [rsp+50h] [rbp-A8h]
  PNET_BUFFER_LIST NetBufferLists; // [rsp+58h] [rbp-A0h] BYREF
  PNET_BUFFER_LIST *v52; // [rsp+60h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-88h] BYREF
  int v54; // [rsp+78h] [rbp-80h]
  __int16 v55; // [rsp+7Ch] [rbp-7Ch]

  NetBufferLists = 0;
  p_NetBufferLists = &NetBufferLists;
  v52 = &NetBufferLists;
  v47 = 0;
  v5 = a2;
  v7 = 0;
  SendFlags = a2 != 0;
  v8 = Entry[4];
  v9 = byte_1400099E6;
  if ( !v8 )
    v9 = byte_140009B06;
  if ( v9 )
  {
    v10 = (KSPIN_LOCK *)*((_QWORD *)Entry + 10);
    v11 = (PKSPIN_LOCK *)(Entry + 80);
    *(_QWORD *)&Source2 = Entry + 80;
    v12 = KeAcquireSpinLockRaiseToDpc(v10);
    v13 = *((_DWORD *)Entry + 25);
    v14 = Entry + 100;
    v45 = v12;
    if ( v13 == 3 )
    {
      KeReleaseSpinLock(*v11, v12);
      v30 = (PKSPIN_LOCK *)(Entry + 80);
    }
    else
    {
      if ( *((_DWORD *)Entry + 31) == 2 )
      {
        v7 = *((_QWORD *)Entry + 2);
        if ( v13 )
          KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v7 + 56));
        v47 = 1;
        _InterlockedIncrement((volatile signed __int32 *)Entry + 24);
        for ( i = 0; ; ++i )
        {
          if ( !a3 )
          {
            if ( *v14 )
              KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v7 + 56));
            KeReleaseSpinLock(*((PKSPIN_LOCK *)Entry + 10), v45);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
              WanpDeleteConnEntry(Entry);
            v27 = SendFlags;
            *p_NetBufferLists = 0;
            v28 = (NDIS_HANDLE)qword_1400099E8;
            if ( !v8 )
              v28 = NdisBindingHandle;
            NdisSendNetBufferLists(v28, NetBufferLists, 0, v27);
            return;
          }
          v15 = a3[1];
          if ( (*(_DWORD *)(v15 + 136) & 0x20000000) != 0 )
          {
            v37 = NetioAllocateAndReferenceCloneNetBufferList(a3[1], v5);
            v16 = (struct _NET_BUFFER_LIST *)v37;
            if ( !v37 )
            {
              PacketIPInfo = -1073741670;
LABEL_66:
              v30 = (PKSPIN_LOCK *)(Entry + 80);
              v39 = 0;
              *(_QWORD *)&Source2 = Entry + 80;
              if ( i )
              {
                do
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
                    WanpDeleteConnEntry(Entry);
                  ++v39;
                }
                while ( v39 < i );
                v30 = (PKSPIN_LOCK *)Source2;
              }
              v40 = NetBufferLists;
              if ( NetBufferLists )
              {
                do
                {
                  Alignment = (struct _NET_BUFFER_LIST *)v40->Link.Alignment;
                  NdisFreeNetBufferListContext(v40, 8u);
                  NetioAdvanceNetBufferList(v40, 14);
                  v40 = Alignment;
                }
                while ( Alignment );
                v30 = (PKSPIN_LOCK *)Source2;
              }
              p_Next = v52;
              do
              {
                v42 = (struct _NET_BUFFER_LIST *)a3[1];
                *p_Next = v42;
                p_Next = &v42->Next;
                _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)Entry + 1) + 312LL));
                a3 = (_QWORD *)*a3;
              }
              while ( a3 );
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
              {
                WanpDeleteConnEntry(Entry);
                v30 = (PKSPIN_LOCK *)Source2;
                v5 = a2;
                v31 = v45;
                *p_Next = 0;
                goto LABEL_78;
              }
              v5 = a2;
              v31 = v45;
LABEL_92:
              *(_QWORD *)&Source2 = v30;
              goto LABEL_43;
            }
            *(_QWORD *)(v37 + 208) = *(unsigned int *)(v15 + 208);
            *(_QWORD *)(v37 + 144) = *(_QWORD *)(v15 + 144);
            NetioDereferenceNetBufferList(v15, a2);
            a3[1] = v16;
          }
          else
          {
            v16 = (struct _NET_BUFFER_LIST *)a3[1];
          }
          if ( *v14 == 1 )
          {
            FirstNetBuffer = v16->FirstNetBuffer;
            Source2 = 0;
            PacketIPInfo = GetPacketIPInfo(FirstNetBuffer);
            if ( PacketIPInfo )
            {
              for ( j = 0; j < i; ++j )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
                  WanpDeleteConnEntry(Entry);
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
                WanpDeleteConnEntry(Entry);
              goto LABEL_87;
            }
            if ( RtlCompareMemory(Entry + 48, (char *)&Source2 + 8, 8u) != 8 )
            {
              if ( *((_QWORD *)Entry + 7) )
              {
                for ( k = 1; ; ++k )
                {
                  v36 = (unsigned int *)*((_QWORD *)Entry + 7);
                  if ( k >= *v36 )
                    break;
                  if ( RtlCompareMemory(&v36[4 * k + 1], &Source2, 0x10u) == 16 )
                    goto LABEL_15;
                }
              }
              if ( !g_bDisableSpoofingProtection )
              {
                _InterlockedIncrement((volatile signed __int32 *)Entry + 66);
                for ( m = 0; m < i; ++m )
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
                    WanpDeleteConnEntry(Entry);
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 24, 0xFFFFFFFF) == 1 )
                  WanpDeleteConnEntry(Entry);
                PacketIPInfo = 0;
LABEL_87:
                v5 = a2;
                v31 = v45;
                goto LABEL_88;
              }
            }
          }
LABEL_15:
          PacketIPInfo = NdisAllocateNetBufferListContext(v16, 8u, 0, 0x7750444Eu);
          if ( PacketIPInfo < 0 )
            goto LABEL_66;
          *(_QWORD *)&v16->Context->ContextData[v16->Context->Offset] = Entry;
          PacketIPInfo = NetioRetreatNetBufferList(v16, 14, 0);
          if ( PacketIPInfo < 0 )
            goto LABEL_66;
          v19 = v16->FirstNetBuffer;
          v20 = 0;
          for ( *(_QWORD *)&Source2 = 0; v19; v19 = (PNET_BUFFER)v19->Link.Alignment )
          {
            _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)Entry + 1) + 280LL));
            CurrentMdl = v19->CurrentMdl;
            if ( CurrentMdl->ByteCount - v19->CurrentMdlOffset < 0xE
              || ((CurrentMdl->MdlFlags & 5) == 0
                ? (MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(CurrentMdl, 0, MmCached, 0, 0, 0x40000000u))
                : (MappedSystemVa = (char *)CurrentMdl->MappedSystemVa),
                  (v23 = &MappedSystemVa[v19->CurrentMdlOffset], ((unsigned __int8)v23 & 1) != 0) || !v23) )
            {
              v29 = *(_QWORD *)(Entry + 108);
              v54 = *((_DWORD *)Entry + 29);
              v55 = *((_WORD *)Entry + 60);
              v53 = v29;
              RtlCopyKernelBufferToMdl(&v53, v19->Link.Region, v19->CurrentMdlOffset, 14, &Source2);
            }
            else
            {
              if ( v20 )
              {
                *(_QWORD *)v23 = *(_QWORD *)v20;
                *((_DWORD *)v23 + 2) = *((_DWORD *)v20 + 2);
                v24 = *((_WORD *)v20 + 6);
              }
              else
              {
                v20 = &MappedSystemVa[v19->CurrentMdlOffset];
                *(_QWORD *)v23 = *(_QWORD *)(Entry + 108);
                *((_DWORD *)v23 + 2) = *((_DWORD *)Entry + 29);
                v24 = *((_WORD *)Entry + 60);
              }
              *((_WORD *)v23 + 6) = v24;
            }
          }
          v25 = (NDIS_HANDLE)qword_1400099E8;
          v26 = v52;
          p_NetBufferLists = &v16->Next;
          if ( !v8 )
            v25 = NdisBindingHandle;
          v16->SourceHandle = v25;
          v52 = &v16->Next;
          *v26 = v16;
          _InterlockedIncrement((volatile signed __int32 *)Entry + 24);
          a3 = (_QWORD *)*a3;
          v5 = a2;
        }
      }
      KeReleaseSpinLock(*v11, v12);
      v30 = (PKSPIN_LOCK *)(Entry + 80);
      *(_QWORD *)&Source2 = Entry + 80;
    }
    v31 = v45;
  }
  else
  {
    v30 = (PKSPIN_LOCK *)(Entry + 80);
    v31 = 0;
    *(_QWORD *)&Source2 = Entry + 80;
    v14 = Entry + 100;
  }
  PacketIPInfo = 65539;
  if ( a3 )
  {
LABEL_88:
    p_Next = v52;
    do
    {
      v44 = (struct _NET_BUFFER_LIST *)a3[1];
      *p_Next = v44;
      p_Next = &v44->Next;
      a3 = (_QWORD *)*a3;
    }
    while ( a3 );
    v14 = Entry + 100;
    v30 = (PKSPIN_LOCK *)(Entry + 80);
    goto LABEL_92;
  }
  p_Next = &NetBufferLists;
LABEL_43:
  *p_Next = 0;
  if ( v47 )
  {
LABEL_78:
    if ( *v14 )
    {
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v7 + 56));
      v30 = (PKSPIN_LOCK *)Source2;
    }
    KeReleaseSpinLock(*v30, v31);
  }
  v33 = NetBufferLists;
  for ( n = NetBufferLists; n; n = (PNET_BUFFER_LIST)n->Link.Alignment )
    n->Status = PacketIPInfo;
  NetioDereferenceNetBufferListChain(v33, v5);
}

```

## disassembly

```asm
0x140015440  push    rbp
0x140015442  push    rsi
0x140015443  push    rdi
0x140015444  push    r13
0x140015446  push    r14
0x140015448  push    r15
0x14001544a  sub     rsp, 0C8h
0x140015451  mov     rax, cs:__security_cookie
0x140015458  xor     rax, rsp
0x14001545b  mov     [rsp+0F8h+var_48], rax
0x140015463  xor     eax, eax
0x140015465  mov     [rsp+0F8h+var_C7], dl
0x140015469  mov     [rsp+0F8h+NetBufferLists], rax
0x14001546e  lea     rsi, [rsp+0F8h+NetBufferLists]
0x140015473  mov     [rsp+0F8h+var_98], rsi
0x140015478  mov     r15, r8
0x14001547b  mov     [rsp+0F8h+var_C6], al
0x14001547f  movzx   ebp, dl
0x140015482  mov     [rsp+0F8h+SendFlags], eax
0x140015486  mov     rdi, rcx
0x140015489  mov     r13d, eax
0x14001548c  test    dl, dl
0x14001548e  jnz     loc_14001588E
0x140015494  movzx   r14d, byte ptr [rcx+4]
0x140015499  movzx   ecx, cs:byte_1400099E6
0x1400154a0  test    r14b, r14b
0x1400154a3  movzx   eax, cs:byte_140009B06
0x1400154aa  cmovz   ecx, eax
0x1400154ad  mov     [rsp+0F8h+arg_18], rbx
0x1400154b5  mov     [rsp+0F8h+var_38], r12
0x1400154bd  test    cl, cl
0x1400154bf  jz      loc_14001589B
0x1400154c5  mov     rcx, [rdi+50h]; SpinLock
0x1400154c9  lea     rbx, [rdi+50h]
0x1400154cd  mov     qword ptr [rsp+0F8h+Source2], rbx
0x1400154d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400154d9  nop     dword ptr [rax+rax+00h]
0x1400154de  mov     ecx, [rdi+64h]
0x1400154e1  lea     r12, [rdi+64h]
0x1400154e5  mov     [rsp+0F8h+var_C8], al
0x1400154e9  cmp     ecx, 3
0x1400154ec  jz      loc_1400157B4
0x1400154f2  cmp     dword ptr [rdi+7Ch], 2
0x1400154f6  jnz     loc_1400158B0
0x1400154fc  mov     r13, [rdi+10h]
0x140015500  test    ecx, ecx
0x140015502  jz      short loc_140015514
0x140015504  lea     rcx, [r13+38h]; SpinLock
0x140015508  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001550f  nop     dword ptr [rax+rax+00h]
0x140015514  mov     [rsp+0F8h+var_C6], 1
0x140015519  lock inc dword ptr [rdi+60h]
0x14001551d  mov     [rsp+0F8h+var_C0], 0
0x140015525  test    r15, r15
0x140015528  jz      loc_1400156AD
0x14001552e  mov     rbx, [r15+8]
0x140015532  test    dword ptr [rbx+88h], 20000000h
0x14001553c  jnz     loc_1400158CF
0x140015542  mov     rbp, rbx
0x140015545  cmp     dword ptr [r12], 1
0x14001554a  jnz     short loc_140015591
0x14001554c  mov     rcx, [rbp+8]; NetBuffer
0x140015550  lea     r8, [rsp+0F8h+Source2]
0x140015555  xorps   xmm0, xmm0
0x140015558  lea     rdx, [rsp+0F8h+var_C4]
0x14001555d  xor     eax, eax
0x14001555f  movups  [rsp+0F8h+Source2], xmm0
0x140015564  mov     [rsp+0F8h+var_C4], ax
0x140015569  call    GetPacketIPInfo
0x14001556e  mov     esi, eax
0x140015570  test    eax, eax
0x140015572  jnz     loc_140015AD6
0x140015578  cmp     [rsp+0F8h+var_C4], 2
0x14001557e  jnz     loc_14001581B
0x140015584  mov     ecx, dword ptr [rsp+0F8h+Source2]
0x140015588  cmp     [rdi+18h], ecx
0x14001558b  jnz     loc_140015926
0x140015591  xor     r8d, r8d; ContextBackFill
0x140015594  mov     edx, 8; ContextSize
0x140015599  mov     r9d, 7750444Eh; PoolTag
0x14001559f  mov     rcx, rbp; NetBufferList
0x1400155a2  call    cs:__imp_NdisAllocateNetBufferListContext
0x1400155a9  nop     dword ptr [rax+rax+00h]
0x1400155ae  mov     esi, eax
0x1400155b0  test    eax, eax
0x1400155b2  js      loc_1400159DA
0x1400155b8  mov     rcx, [rbp+10h]
0x1400155bc  xor     r8d, r8d
0x1400155bf  mov     edx, 0Eh
0x1400155c4  movzx   eax, word ptr [rcx+0Ah]
0x1400155c8  mov     [rax+rcx+10h], rdi
0x1400155cd  mov     rcx, rbp
0x1400155d0  call    cs:__imp_NetioRetreatNetBufferList
0x1400155d7  nop     dword ptr [rax+rax+00h]
0x1400155dc  mov     esi, eax
0x1400155de  test    eax, eax
0x1400155e0  js      loc_1400159DA
0x1400155e6  mov     rbx, [rbp+8]
0x1400155ea  xor     esi, esi
0x1400155ec  mov     qword ptr [rsp+0F8h+Source2], 0
0x1400155f5  test    rbx, rbx
0x1400155f8  jz      short loc_140015672
0x1400155fa  nop     word ptr [rax+rax+00h]
0x140015600  mov     rax, [rdi+8]
0x140015604  lock inc qword ptr [rax+118h]
0x14001560c  mov     r10, [rbx+8]
0x140015610  mov     ecx, [r10+28h]
0x140015614  sub     ecx, [rbx+10h]
0x140015617  cmp     ecx, 0Eh
0x14001561a  jb      loc_14001576B
0x140015620  test    byte ptr [r10+0Ah], 5
0x140015625  jz      loc_1400159A6
0x14001562b  mov     rax, [r10+18h]
0x14001562f  mov     edx, [rbx+10h]
0x140015632  add     rdx, rax
0x140015635  test    dl, 1
0x140015638  jnz     loc_14001576B
0x14001563e  test    rdx, rdx
0x140015641  jz      loc_14001576B
0x140015647  test    rsi, rsi
0x14001564a  jnz     loc_140015750
0x140015650  movsd   xmm0, qword ptr [rdi+6Ch]
0x140015655  mov     rsi, rdx
0x140015658  movsd   qword ptr [rdx], xmm0
0x14001565c  mov     eax, [rdi+74h]
0x14001565f  mov     [rdx+8], eax
0x140015662  movzx   eax, word ptr [rdi+78h]
0x140015666  mov     [rdx+0Ch], ax
0x14001566a  mov     rbx, [rbx]
0x14001566d  test    rbx, rbx
0x140015670  jnz     short loc_140015600
0x140015672  mov     rcx, cs:qword_1400099E8
0x140015679  test    r14b, r14b
0x14001567c  mov     rbx, [rsp+0F8h+var_98]
0x140015681  mov     rsi, rbp
0x140015684  cmovz   rcx, cs:NdisBindingHandle
0x14001568c  mov     [rbp+78h], rcx
0x140015690  mov     [rsp+0F8h+var_98], rbp
0x140015695  mov     [rbx], rbp
0x140015698  lock inc dword ptr [rdi+60h]
0x14001569c  mov     r15, [r15]
0x14001569f  inc     [rsp+0F8h+var_C0]
0x1400156a3  movzx   ebp, [rsp+0F8h+var_C7]
0x1400156a8  jmp     loc_140015525
0x1400156ad  cmp     dword ptr [r12], 0
0x1400156b2  jz      short loc_1400156C4
0x1400156b4  lea     rcx, [r13+38h]; SpinLock
0x1400156b8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400156bf  nop     dword ptr [rax+rax+00h]
0x1400156c4  movzx   edx, [rsp+0F8h+var_C8]; NewIrql
0x1400156c9  mov     rcx, [rdi+50h]; SpinLock
0x1400156cd  call    cs:__imp_KeReleaseSpinLock
0x1400156d4  nop     dword ptr [rax+rax+00h]
0x1400156d9  mov     ebp, 0FFFFFFFFh
0x1400156de  lock xadd [rdi+60h], ebp
0x1400156e3  cmp     ebp, 1
0x1400156e6  jz      loc_140015B68
0x1400156ec  mov     r9d, [rsp+0F8h+SendFlags]; SendFlags
0x1400156f1  test    r14b, r14b
0x1400156f4  mov     qword ptr [rsi], 0
0x1400156fb  mov     rcx, cs:qword_1400099E8
0x140015702  cmovz   rcx, cs:NdisBindingHandle; NdisBindingHandle
0x14001570a  xor     r8d, r8d; PortNumber
0x14001570d  mov     rdx, [rsp+0F8h+NetBufferLists]; NetBufferLists
0x140015712  call    cs:__imp_NdisSendNetBufferLists
0x140015719  nop     dword ptr [rax+rax+00h]
0x14001571e  mov     r12, [rsp+0F8h+var_38]
0x140015726  mov     rbx, [rsp+0F8h+arg_18]
0x14001572e  mov     rcx, [rsp+0F8h+var_48]
0x140015736  xor     rcx, rsp; StackCookie
0x140015739  call    __security_check_cookie
0x14001573e  add     rsp, 0C8h
0x140015745  pop     r15
0x140015747  pop     r14
0x140015749  pop     r13
0x14001574b  pop     rdi
0x14001574c  pop     rsi
0x14001574d  pop     rbp
0x14001574e  retn
0x140015750  movsd   xmm0, qword ptr [rsi]
0x140015754  movsd   qword ptr [rdx], xmm0
0x140015758  mov     eax, [rsi+8]
0x14001575b  mov     [rdx+8], eax
0x14001575e  movzx   eax, word ptr [rsi+0Ch]
0x140015762  mov     [rdx+0Ch], ax
0x140015766  jmp     loc_14001566A
0x14001576b  mov     eax, [rdi+74h]
0x14001576e  lea     rcx, [rsp+0F8h+var_88]
0x140015773  movsd   xmm0, qword ptr [rdi+6Ch]
0x140015778  mov     r9d, 0Eh
0x14001577e  mov     [rsp+0F8h+var_80], eax
0x140015782  movzx   eax, word ptr [rdi+78h]
0x140015786  mov     [rsp+0F8h+var_7C], ax
0x14001578b  lea     rax, [rsp+0F8h+Source2]
0x140015790  movsd   [rsp+0F8h+var_88], xmm0
0x140015796  mov     r8d, [rbx+10h]
0x14001579a  mov     rdx, [rbx+8]
0x14001579e  mov     qword ptr [rsp+0F8h+BugCheckOnFailure], rax
0x1400157a3  call    cs:__imp_RtlCopyKernelBufferToMdl
0x1400157aa  nop     dword ptr [rax+rax+00h]
0x1400157af  jmp     loc_14001566A
0x1400157b4  mov     rcx, [rbx]; SpinLock
0x1400157b7  movzx   edx, al; NewIrql
0x1400157ba  call    cs:__imp_KeReleaseSpinLock
0x1400157c1  nop     dword ptr [rax+rax+00h]
0x1400157c6  lea     rcx, [rdi+50h]
0x1400157ca  movzx   r14d, [rsp+0F8h+var_C8]
0x1400157d0  mov     esi, 10003h
0x1400157d5  test    r15, r15
0x1400157d8  jnz     loc_140015B1F
0x1400157de  lea     rbx, [rsp+0F8h+NetBufferLists]
0x1400157e3  cmp     [rsp+0F8h+var_C6], 0
0x1400157e8  mov     qword ptr [rbx], 0
0x1400157ef  jnz     loc_140015AA2
0x1400157f5  mov     rcx, [rsp+0F8h+NetBufferLists]
0x1400157fa  mov     rax, rcx
0x1400157fd  test    rcx, rcx
0x140015800  jnz     loc_140015B55
0x140015806  movzx   edx, bpl
0x14001580a  call    cs:__imp_NetioDereferenceNetBufferListChain
0x140015811  nop     dword ptr [rax+rax+00h]
0x140015816  jmp     loc_14001571E
0x14001581b  lea     rcx, [rdi+30h]; Source1
0x14001581f  mov     r8d, 8; Length
0x140015825  lea     rdx, [rsp+0F8h+Source2+8]; Source2
0x14001582a  call    cs:__imp_RtlCompareMemory
0x140015831  nop     dword ptr [rax+rax+00h]
0x140015836  cmp     rax, 8
0x14001583a  jz      loc_140015591
0x140015840  cmp     qword ptr [rdi+38h], 0
0x140015845  jz      loc_14001594D
0x14001584b  mov     ebx, 1
0x140015850  mov     rcx, [rdi+38h]
0x140015854  cmp     ebx, [rcx]
0x140015856  jnb     loc_14001594D
0x14001585c  add     rcx, 4
0x140015860  mov     eax, ebx
0x140015862  shl     rax, 4
0x140015866  lea     rdx, [rsp+0F8h+Source2]; Source2
0x14001586b  add     rcx, rax; Source1
0x14001586e  mov     r8d, 10h; Length
0x140015874  call    cs:__imp_RtlCompareMemory
0x14001587b  nop     dword ptr [rax+rax+00h]
0x140015880  cmp     rax, 10h
0x140015884  jz      loc_140015591
0x14001588a  inc     ebx
0x14001588c  jmp     short loc_140015850
0x14001588e  mov     [rsp+0F8h+SendFlags], 1
0x140015896  jmp     loc_140015494
0x14001589b  lea     rcx, [rdi+50h]
0x14001589f  xor     r14b, r14b
0x1400158a2  mov     qword ptr [rsp+0F8h+Source2], rcx
0x1400158a7  lea     r12, [rdi+64h]
0x1400158ab  jmp     loc_1400157D0
0x1400158b0  mov     rcx, [rbx]; SpinLock
0x1400158b3  movzx   edx, al; NewIrql
0x1400158b6  call    cs:__imp_KeReleaseSpinLock
0x1400158bd  nop     dword ptr [rax+rax+00h]
0x1400158c2  mov     rcx, rbx
0x1400158c5  mov     qword ptr [rsp+0F8h+Source2], rbx
0x1400158ca  jmp     loc_1400157CA
0x1400158cf  movzx   edx, bpl
0x1400158d3  mov     rcx, rbx
0x1400158d6  call    cs:__imp_NetioAllocateAndReferenceCloneNetBufferList
0x1400158dd  nop     dword ptr [rax+rax+00h]
0x1400158e2  mov     rbp, rax
0x1400158e5  test    rax, rax
0x1400158e8  jz      loc_1400159D5
0x1400158ee  mov     ecx, [rbx+0D0h]
0x1400158f4  movzx   edx, [rsp+0F8h+var_C7]
0x1400158f9  mov     [rax+0D0h], rcx
0x140015900  mov     rcx, [rbx+90h]
0x140015907  mov     [rax+90h], rcx
0x14001590e  mov     rcx, rbx
0x140015911  call    cs:__imp_NetioDereferenceNetBufferList
0x140015918  nop     dword ptr [rax+rax+00h]
0x14001591d  mov     [r15+8], rbp
0x140015921  jmp     loc_140015545
0x140015926  mov     r8, [rdi+38h]
0x14001592a  test    r8, r8
0x14001592d  jz      short loc_14001594D
0x14001592f  mov     r9d, [r8]
0x140015932  mov     edx, 1
0x140015937  cmp     edx, r9d
0x14001593a  jnb     short loc_14001594D
0x14001593c  mov     eax, edx
0x14001593e  cmp     [r8+rax*4+4], ecx
0x140015943  jz      loc_140015591
0x140015949  inc     edx
0x14001594b  jmp     short loc_140015937
0x14001594d  cmp     cs:g_bDisableSpoofingProtection, 0
0x140015954  jnz     loc_140015591
0x14001595a  lock inc dword ptr [rdi+108h]
0x140015961  mov     r14d, [rsp+0F8h+var_C0]
0x140015966  xor     ebx, ebx
0x140015968  mov     ebp, 0FFFFFFFFh
0x14001596d  test    r14d, r14d
0x140015970  jz      short loc_14001598D
0x140015972  mov     eax, ebp
0x140015974  lock xadd [rdi+60h], eax
  ... truncated ...
```
