# TcpEnumerateConnections

- ea: `0x140037370`
- end: `0x14003851d`
- name: `TcpEnumerateConnections`
- size: `4525`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140035810`
- `0x140036e50`

## callees

- `0x14000ad68`
- `0x14002f230`
- `0x140032740`
- `0x140037370`
- `0x140038530`
- `0x140039860`
- `0x14004c550`
- `0x14004df9c`
- `0x1400b0778`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400373eb`
- `ntoskrnl!KfRaiseIrql` at `0x1400373eb`
- `ntoskrnl!KeLowerIrql` at `0x1400374b6`
- `ntoskrnl!KeLowerIrql` at `0x1400382d3`
- `ntoskrnl!KeLowerIrql` at `0x1400374b6`
- `ntoskrnl!KeLowerIrql` at `0x1400382d3`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400373c4`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400373c4`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14003784e`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x1400378aa`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x140037aea`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14003808c`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x1400381c3`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x1400384da`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14003784e`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x1400378aa`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x140037aea`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x14003808c`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x1400381c3`
- `ntoskrnl!RtlEndWeakEnumerationHashTable` at `0x1400384da`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14003752e`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x140037887`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x1400378de`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x14003752e`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x140037887`
- `ntoskrnl!RtlWeaklyEnumerateEntryHashTable` at `0x1400378de`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x140037518`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x140037868`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x1400378c4`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x140037518`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x140037868`
- `ntoskrnl!RtlInitWeakEnumerationHashTable` at `0x1400378c4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140037437`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140037437`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400374fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037827`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037ac2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037b56`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037b95`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003816b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400384ad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400374fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037827`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037ac2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037b56`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037b95`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003816b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400384ad`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003744e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003744e`
- `ntoskrnl!PsGetProcessId` at `0x1400376bd`
- `ntoskrnl!PsGetProcessId` at `0x140038404`
- `ntoskrnl!PsGetProcessId` at `0x1400376bd`
- `ntoskrnl!PsGetProcessId` at `0x140038404`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003756f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003791e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037afb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003809d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038119`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400381d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400384eb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003756f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003791e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037afb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003809d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140038119`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400381d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400384eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037805`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037a85`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037b1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037b75`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003814b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003848b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037805`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037a85`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037b1b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140037b75`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003814b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003848b`
- `ntoskrnl!KeTestSpinLock` at `0x140037415`
- `ntoskrnl!KeTestSpinLock` at `0x140037415`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003757e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003792e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140038128`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003757e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003792e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140038128`
- `NETIO!NetioQueryFlowTrafficClass` at `0x140038299`
- `NETIO!NetioQueryFlowTrafficClass` at `0x140038299`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400373d9`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400373d9`

## pseudocode

```c
__int64 __fastcall TcpEnumerateConnections(unsigned __int16 a1, __int64 a2, __int64 a3, __int64 a4, int a5, _DWORD *a6)
{
  __int64 v6; // rsi
  __int64 v8; // r14
  KIRQL v9; // bl
  struct _LIST_ENTRY *v10; // r15
  struct _LIST_ENTRY *Flink; // r8
  int v12; // esi
  PRTL_DYNAMIC_HASH_TABLE *v13; // r12
  PKSPIN_LOCK v14; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v15; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v16; // rbx
  KIRQL v17; // r15
  struct _LIST_ENTRY *v18; // rdx
  __int16 v19; // r10
  struct _LIST_ENTRY *v20; // r9
  __int64 v21; // rcx
  struct _LIST_ENTRY *v22; // r11
  __int64 v23; // r8
  struct _LIST_ENTRY *v24; // r8
  __int16 Signature_high; // r9
  __int64 v26; // rcx
  struct _LIST_ENTRY *v27; // r10
  __int64 v28; // rdx
  ULONG_PTR Signature; // rsi
  ULONG_PTR v30; // rsi
  _QWORD *v31; // rcx
  __int64 v32; // r14
  PKSPIN_LOCK v33; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v34; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v35; // rbx
  KIRQL v36; // r9
  struct _LIST_ENTRY *v37; // rdx
  __int16 Flink_high; // r10
  __int64 v39; // r14
  __int64 v40; // rcx
  __int128 *v41; // r11
  __int64 v42; // r8
  __int64 v43; // r14
  __int16 v44; // r8
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rax
  signed __int64 v48; // rax
  bool v49; // cc
  signed __int64 v50; // rax
  PKSPIN_LOCK v51; // rbx
  signed __int64 v52; // rax
  signed __int64 v53; // rax
  PKSPIN_LOCK v54; // rbx
  PKSPIN_LOCK v55; // rbx
  int Blink; // eax
  struct _LIST_ENTRY v57; // xmm0
  char v58; // al
  __m128i *v59; // rdx
  int v60; // r9d
  int v61; // eax
  struct _LIST_ENTRY v62; // xmm0
  char v63; // al
  __m128i *v64; // r8
  int v65; // r8d
  int v66; // eax
  __int128 v67; // xmm0
  char v68; // al
  __m128i *v69; // rdx
  int v70; // r10d
  int v71; // eax
  LIST_ENTRY Linkage; // xmm0
  char v73; // al
  __m128i *v74; // r8
  int v75; // r8d
  struct _LIST_ENTRY **p_Blink; // rbx
  KIRQL v78; // si
  PKSPIN_LOCK v79; // rbx
  struct _LIST_ENTRY *v80; // rcx
  PKSPIN_LOCK v81; // rbx
  int ThreadObjectCompartmentId; // [rsp+30h] [rbp-D0h]
  int v84; // [rsp+40h] [rbp-C0h]
  struct _KLOCK_QUEUE_HANDLE v85; // [rsp+48h] [rbp-B8h] BYREF
  struct _LIST_ENTRY *v86; // [rsp+60h] [rbp-A0h]
  __int64 v87; // [rsp+68h] [rbp-98h] BYREF
  __int64 v88; // [rsp+70h] [rbp-90h]
  struct _RTL_DYNAMIC_HASH_TABLE_ENUMERATOR Enumerator; // [rsp+78h] [rbp-88h] BYREF
  __m128i v90; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v91; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v92; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v93; // [rsp+D0h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+E0h] [rbp-20h] BYREF

  v6 = a1;
  memset(&Enumerator, 0, sizeof(Enumerator));
  v87 = 0;
  v8 = a3;
  memset(&v85, 0, sizeof(v85));
  v88 = a3;
  KeQuerySystemTimePrecise(&v87);
  ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v9 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement(&dword_14022A198);
  if ( !KeTestSpinLock(&qword_14022A190) )
  {
    _InterlockedDecrement(&dword_14022A198);
    KeAcquireInStackQueuedSpinLockAtDpcLevel(&qword_14022A190, &LockHandle);
    _InterlockedIncrement(&dword_14022A198);
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v10 = (struct _LIST_ENTRY *)*((_QWORD *)&TcpInetTransport + v6 + 44);
  v86 = v10;
  if ( v10
    && (Flink = v10[1].Flink,
        (_InterlockedExchangeAdd64(
           (volatile signed __int64 *)((char *)Flink->Flink
                                     + (unsigned int)(LODWORD(Flink[1].Flink)
                                                    * (HIDWORD(KeGetPcr()[1].LockArray) % HIDWORD(Flink[1].Flink)))),
           2u)
       & 1) != 0) )
  {
    _InterlockedAdd64((volatile signed __int64 *)&Flink[1].Blink, 2u);
    _InterlockedDecrement(&dword_14022A198);
    KeLowerIrql(v9);
  }
  else
  {
    _InterlockedDecrement(&dword_14022A198);
    KeLowerIrql(v9);
    if ( !v10 )
      return 0;
  }
  v12 = 0;
LABEL_7:
  v84 = v12;
  if ( (unsigned __int16)v12 >= (unsigned __int16)PartitionCount )
  {
    InetDereferenceAf(v10);
    return 0;
  }
  v13 = (PRTL_DYNAMIC_HASH_TABLE *)((char *)PartitionTable + 192 * (unsigned __int16)v12);
  v14 = (PKSPIN_LOCK)*v13;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&(*v13)->Flags, &v85);
  while ( *((_DWORD *)v14 + 2) )
    ;
  RtlInitWeakEnumerationHashTable(v13[1], &Enumerator);
  while ( 1 )
  {
    v15 = RtlWeaklyEnumerateEntryHashTable(v13[1], &Enumerator);
    if ( !v15 )
      break;
    if ( *a6 == a5 )
    {
      RtlEndWeakEnumerationHashTable(v13[1], &Enumerator);
      KeReleaseInStackQueuedSpinLock(&v85);
      InetDereferenceAf(v86);
      return 261;
    }
    v16 = v15 - 2;
    if ( _InterlockedIncrement64((volatile signed __int64 *)&v15[-2].Linkage.Blink) <= 1 )
      __fastfail(0xEu);
    KeReleaseInStackQueuedSpinLock(&v85);
    v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v16);
    if ( ((__int64)v16[5].Linkage.Flink & 2) != 0
      && (v18 = v16[1].Linkage.Flink, v18 == v86)
      && v16[46].Linkage.Flink->Flink == (struct _LIST_ENTRY *)ThreadObjectCompartmentId )
    {
      v19 = WORD2(v16[4].Signature);
      v20 = v16[1].Linkage.Blink->Flink[1].Flink;
      v21 = 56LL * (unsigned int)*a6;
      v22 = v20->Flink;
      v23 = v21 + a2 + 8;
      if ( LOWORD(v18[1].Blink) == 23 )
      {
        Blink = (int)v20->Blink;
        *(_WORD *)(v21 + a2 + 2) = v19;
        *(_DWORD *)(v21 + a2 + 4) = 0;
        *(_WORD *)(v21 + a2) = 23;
        v57 = *v22;
        *(_DWORD *)(v21 + a2 + 24) = Blink;
        *(struct _LIST_ENTRY *)v23 = v57;
        v58 = *(_BYTE *)v23;
        if ( *(_BYTE *)v23 == 0xFF )
        {
          v60 = *(_BYTE *)(v23 + 1) & 0xF;
        }
        else
        {
          v90 = 0;
          if ( (v23 & 1) != 0 )
          {
            v59 = &v90;
            v90 = *(__m128i *)v23;
            v58 = _mm_cvtsi128_si32(v90);
          }
          else
          {
            v59 = (__m128i *)(v21 + a2 + 8);
          }
          if ( (v58 != -2 || (v59->m128i_i8[1] & 0xC0) != 0x80)
            && (v59->m128i_i16[0]
             || v59->m128i_i16[1]
             || v59->m128i_i16[2]
             || v59->m128i_i16[3]
             || v59->m128i_i16[4]
             || v59->m128i_i16[5]
             || v59->m128i_i16[6]
             || v59->m128i_i16[7] != 256) )
          {
            if ( (unsigned __int8)v59->m128i_i16[0] == 0xFE && (HIBYTE(v59->m128i_i16[0]) & 0xC0) == 0xC0 )
              v60 = 5;
            else
              v60 = 14;
          }
          else
          {
            v60 = 2;
          }
        }
        if ( !*(_WORD *)v23
          && !*(_WORD *)(v23 + 2)
          && !*(_WORD *)(v23 + 4)
          && !*(_WORD *)(v23 + 6)
          && !*(_WORD *)(v23 + 8)
          && !*(_WORD *)(v23 + 10)
          && !*(_WORD *)(v23 + 12)
          && *(_WORD *)(v23 + 14) == 256
          || v60 == 14 )
        {
          *(_DWORD *)(v21 + a2 + 24) = 0;
        }
        if ( *(_DWORD *)(v21 + a2 + 24) >> 28 == v60 )
          *(_DWORD *)(v21 + a2 + 24) &= 0xFFFFFFFu;
      }
      else
      {
        *(_DWORD *)(v21 + a2 + 4) = v22->Flink;
        *(_WORD *)(v21 + a2) = 2;
        *(_WORD *)(v21 + a2 + 2) = v19;
        *(_QWORD *)v23 = 0;
      }
      v24 = v16[1].Linkage.Blink;
      Signature_high = HIWORD(v16[4].Signature);
      v26 = 56LL * (unsigned int)*a6;
      v27 = v24[1].Flink;
      v28 = v26 + a2 + 36;
      if ( LOWORD(v16[1].Linkage.Flink[1].Blink) == 23 )
      {
        v61 = (int)v24->Blink;
        *(_DWORD *)(v26 + a2 + 32) = 0;
        *(_WORD *)(v26 + a2 + 28) = 23;
        *(_WORD *)(v26 + a2 + 30) = Signature_high;
        v62 = *v27;
        *(_DWORD *)(v26 + a2 + 52) = v61;
        *(struct _LIST_ENTRY *)v28 = v62;
        v63 = *(_BYTE *)v28;
        if ( *(_BYTE *)v28 == 0xFF )
        {
          v65 = *(_BYTE *)(v28 + 1) & 0xF;
        }
        else
        {
          v91 = 0;
          if ( (v28 & 1) != 0 )
          {
            v64 = &v91;
            v91 = *(__m128i *)v28;
            v63 = _mm_cvtsi128_si32(v91);
          }
          else
          {
            v64 = (__m128i *)(v26 + a2 + 36);
          }
          if ( (v63 != -2 || (v64->m128i_i8[1] & 0xC0) != 0x80)
            && (v64->m128i_i16[0]
             || v64->m128i_i16[1]
             || v64->m128i_i16[2]
             || v64->m128i_i16[3]
             || v64->m128i_i16[4]
             || v64->m128i_i16[5]
             || v64->m128i_i16[6]
             || v64->m128i_i16[7] != 256) )
          {
            if ( (unsigned __int8)v64->m128i_i16[0] == 0xFE && (HIBYTE(v64->m128i_i16[0]) & 0xC0) == 0xC0 )
              v65 = 5;
            else
              v65 = 14;
          }
          else
          {
            v65 = 2;
          }
        }
        if ( !*(_WORD *)v28
          && !*(_WORD *)(v28 + 2)
          && !*(_WORD *)(v28 + 4)
          && !*(_WORD *)(v28 + 6)
          && !*(_WORD *)(v28 + 8)
          && !*(_WORD *)(v28 + 10)
          && !*(_WORD *)(v28 + 12)
          && *(_WORD *)(v28 + 14) == 256
          || v65 == 14 )
        {
          *(_DWORD *)(v26 + a2 + 52) = 0;
        }
        if ( *(_DWORD *)(v26 + a2 + 52) >> 28 == v65 )
          *(_DWORD *)(v26 + a2 + 52) &= 0xFFFFFFFu;
      }
      else
      {
        *(_DWORD *)(v26 + a2 + 32) = v27->Flink;
        *(_WORD *)(v26 + a2 + 28) = 2;
        *(_WORD *)(v26 + a2 + 30) = Signature_high;
        *(_QWORD *)v28 = 0;
      }
      if ( v8 )
      {
        *(_BYTE *)(32LL * (unsigned int)*a6 + v8) = BYTE1(v16[33].Linkage.Flink) & 1;
        *(_BYTE *)(32LL * (unsigned int)*a6 + v8 + 1) = (BYTE1(v16[33].Linkage.Flink) & 4) != 0;
        *(_BYTE *)(32LL * (unsigned int)*a6 + v8 + 2) = (v16[33].Signature & 0x400) != 0;
        *(_DWORD *)(32LL * (unsigned int)*a6 + v8 + 4) = LOBYTE(v16[33].Linkage.Blink);
        *(_DWORD *)(32LL * (unsigned int)*a6 + v8 + 8) = BYTE1(v16[33].Linkage.Blink);
        *(_DWORD *)(32LL * (unsigned int)*a6 + v8 + 12) = (unsigned int)PsGetProcessId((PEPROCESS)v16[35].Linkage.Blink);
        *(_QWORD *)(32LL * (unsigned int)*a6 + v8 + 16) = v16[36].Linkage.Flink;
        *(_QWORD *)(32LL * (unsigned int)*a6 + v8 + 24) = v16[37].Linkage.Blink;
        *(_BYTE *)(32LL * (unsigned int)*a6 + v8 + 3) = 0;
      }
      if ( a4 )
      {
        *(_BYTE *)(a4 + 24LL * (unsigned int)*a6 + 4) = (BYTE1(v16[33].Linkage.Flink) & 0x20) == 0;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6) = LODWORD(v16[4].Signature) + 1;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6 + 8) = 0;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6 + 12) = (int)(HIDWORD(v16[31].Linkage.Blink) << 8) >> 8;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6 + 16) = (signed __int64)(v87 - (unsigned __int64)v16[37].Linkage.Flink)
                                                        / 10000;
        Signature = v16[37].Signature;
        if ( Signature )
        {
          v30 = Signature + 632;
          if ( *(_QWORD *)(v30 + 24) )
          {
            RtlAcquireReadLockAtDpcLevel((PKSPIN_LOCK)v30);
            v31 = *(_QWORD **)(v30 + 24);
            if ( v31 )
            {
              v32 = 0;
              if ( (*(_DWORD *)(v30 + 16) & 0x20) == 0 )
              {
                if ( v31[1] )
                  v31 += 2;
                v32 = *v31;
                if ( (int)EQoSReferenceQoSFlow(*v31) < 0 )
                  v32 = 0;
              }
              _InterlockedDecrement((volatile signed __int32 *)(v30 + 8));
              if ( v32 )
              {
                *(_BYTE *)(a4 + 24LL * (unsigned int)*a6 + 20) = NetioQueryFlowTrafficClass(v32);
                EQoSDereferenceQoSFlow(v32);
                goto LABEL_34;
              }
            }
            else
            {
              _InterlockedDecrement((volatile signed __int32 *)(v30 + 8));
            }
          }
        }
        *(_BYTE *)(a4 + 24LL * (unsigned int)*a6 + 20) = 0;
      }
LABEL_34:
      KeReleaseSpinLock((PKSPIN_LOCK)v16, v17);
      TcpDereferenceTcb(v16);
      ++*a6;
      v33 = (PKSPIN_LOCK)*v13;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&(*v13)->Flags, &v85);
      while ( *((_DWORD *)v33 + 2) )
        ;
      v8 = v88;
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)v16, v17);
      TcpDereferenceTcb(v16);
      v55 = (PKSPIN_LOCK)*v13;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&(*v13)->Flags, &v85);
      while ( *((_DWORD *)v55 + 2) )
        ;
    }
  }
  RtlEndWeakEnumerationHashTable(v13[1], &Enumerator);
  RtlInitWeakEnumerationHashTable(v13[1] + 3, &Enumerator);
  v10 = v86;
  while ( 1 )
  {
    v34 = RtlWeaklyEnumerateEntryHashTable(v13[1] + 3, &Enumerator);
    if ( !v34 )
      break;
    if ( *a6 == a5 )
    {
      RtlEndWeakEnumerationHashTable(v13[1] + 3, &Enumerator);
      KeReleaseInStackQueuedSpinLock(&v85);
      InetDereferenceAf(v10);
      return 261;
    }
    p_Blink = &v34[-1].Linkage.Blink;
    if ( _InterlockedIncrement64((volatile signed __int64 *)&v34[-1].Signature) <= 1 )
      __fastfail(0xEu);
    KeReleaseInStackQueuedSpinLock(&v85);
    v78 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)p_Blink);
    if ( (*((_BYTE *)p_Blink + 138) & 1) != 0
      && (v80 = p_Blink[9], v80 == v10)
      && p_Blink[11][6].Flink->Flink == (struct _LIST_ENTRY *)ThreadObjectCompartmentId )
    {
      INETADDR_SETSOCKADDR(
        LOWORD(v80[1].Blink),
        a2 + 56 * *a6,
        p_Blink[10][1].Flink->Flink,
        p_Blink[10][1].Flink->Blink,
        *((_WORD *)p_Blink + 66));
      INETADDR_SETSOCKADDR(
        LOWORD(p_Blink[9][1].Blink),
        56 * *a6 + a2 + 28,
        (_DWORD)p_Blink + 112,
        *((_DWORD *)p_Blink + 32),
        *((_WORD *)p_Blink + 67));
      if ( v8 )
      {
        *(_BYTE *)(32LL * (unsigned int)*a6 + v8) = (*((_BYTE *)p_Blink + 138) & 0x10) != 0;
        *(_BYTE *)(32LL * (unsigned int)*a6 + v8 + 1) = (*((_BYTE *)p_Blink + 138) & 0x20) != 0;
        *(_BYTE *)(32LL * (unsigned int)*a6 + v8 + 2) = *((_BYTE *)p_Blink + 138) >> 7;
        *(_DWORD *)(32LL * (unsigned int)*a6 + v8 + 4) = *((unsigned __int8 *)p_Blink + 171);
        *(_DWORD *)(32LL * (unsigned int)*a6 + v8 + 8) = *((unsigned __int8 *)p_Blink + 170);
        *(_DWORD *)(32LL * (unsigned int)*a6 + v8 + 12) = (unsigned int)PsGetProcessId((PEPROCESS)p_Blink[11][3].Blink);
        *(_QWORD *)(32LL * (unsigned int)*a6 + v8 + 24) = 0;
        *(_QWORD *)(32LL * (unsigned int)*a6 + v8 + 16) = 0;
        *(_BYTE *)(32LL * (unsigned int)*a6 + v8 + 3) = 0;
      }
      if ( a4 )
      {
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6) = 4;
        *(_BYTE *)(a4 + 24LL * (unsigned int)*a6 + 4) = 0;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6 + 8) = 0;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6 + 12) = (int)(*((_DWORD *)p_Blink + 44) << 8) >> 8;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)p_Blink, v78);
      TcpDereferenceSynTcb(p_Blink);
      ++*a6;
      v81 = (PKSPIN_LOCK)*v13;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&(*v13)->Flags, &v85);
      while ( *((_DWORD *)v81 + 2) )
        ;
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)p_Blink, v78);
      TcpDereferenceSynTcb(p_Blink);
      v79 = (PKSPIN_LOCK)*v13;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&(*v13)->Flags, &v85);
      while ( *((_DWORD *)v79 + 2) )
        ;
    }
  }
  RtlEndWeakEnumerationHashTable(v13[1] + 3, &Enumerator);
  RtlInitWeakEnumerationHashTable(v13[1] + 1, &Enumerator);
  while ( 1 )
  {
    v35 = RtlWeaklyEnumerateEntryHashTable(v13[1] + 1, &Enumerator);
    if ( !v35 )
    {
      RtlEndWeakEnumerationHashTable(v13[1] + 1, &Enumerator);
      KeReleaseInStackQueuedSpinLock(&v85);
      HIWORD(v12) = HIWORD(v84);
      LOWORD(v12) = v84 + 1;
      goto LABEL_7;
    }
    if ( *a6 == a5 )
      break;
    if ( _InterlockedIncrement64((volatile signed __int64 *)&v35[2].Signature) <= 1 )
      __fastfail(0xEu);
    KeReleaseInStackQueuedSpinLock(&v85);
    v36 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v35[2].Linkage.Blink);
    if ( BYTE1(v35[3].Linkage.Flink)
      && (v37 = v35[2].Linkage.Flink, v37 == v10)
      && v35[5].Linkage.Blink->Flink == (struct _LIST_ENTRY *)ThreadObjectCompartmentId )
    {
      Flink_high = HIWORD(v35[3].Linkage.Flink);
      v39 = *(_QWORD *)(v35[3].Signature + 16);
      v40 = 56LL * (unsigned int)*a6;
      v41 = *(__int128 **)v39;
      v42 = v40 + a2 + 8;
      if ( LOWORD(v37[1].Blink) == 23 )
      {
        v66 = *(_DWORD *)(v39 + 8);
        v43 = a2;
        *(_WORD *)(v40 + a2) = 23;
        *(_WORD *)(v40 + a2 + 2) = Flink_high;
        *(_DWORD *)(v40 + a2 + 4) = 0;
        v67 = *v41;
        *(_DWORD *)(v40 + a2 + 24) = v66;
        *(_OWORD *)v42 = v67;
        v68 = *(_BYTE *)v42;
        if ( *(_BYTE *)v42 == 0xFF )
        {
          v70 = *(_BYTE *)(v42 + 1) & 0xF;
        }
        else
        {
          v92 = 0;
          if ( (v42 & 1) != 0 )
          {
            v69 = &v92;
            v92 = *(__m128i *)v42;
            v68 = _mm_cvtsi128_si32(v92);
          }
          else
          {
            v69 = (__m128i *)(v40 + a2 + 8);
          }
          if ( (v68 != -2 || (v69->m128i_i8[1] & 0xC0) != 0x80)
            && (v69->m128i_i16[0]
             || v69->m128i_i16[1]
             || v69->m128i_i16[2]
             || v69->m128i_i16[3]
             || v69->m128i_i16[4]
             || v69->m128i_i16[5]
             || v69->m128i_i16[6]
             || v69->m128i_i16[7] != 256) )
          {
            if ( (unsigned __int8)v69->m128i_i16[0] == 0xFE && (HIBYTE(v69->m128i_i16[0]) & 0xC0) == 0xC0 )
              v70 = 5;
            else
              v70 = 14;
          }
          else
          {
            v70 = 2;
          }
        }
        if ( !*(_WORD *)v42
          && !*(_WORD *)(v42 + 2)
          && !*(_WORD *)(v42 + 4)
          && !*(_WORD *)(v42 + 6)
          && !*(_WORD *)(v42 + 8)
          && !*(_WORD *)(v42 + 10)
          && !*(_WORD *)(v42 + 12)
          && *(_WORD *)(v42 + 14) == 256
          || v70 == 14 )
        {
          *(_DWORD *)(v40 + a2 + 24) = 0;
        }
        if ( *(_DWORD *)(v40 + a2 + 24) >> 28 == v70 )
          *(_DWORD *)(v40 + a2 + 24) &= 0xFFFFFFFu;
      }
      else
      {
        v43 = a2;
        *(_DWORD *)(v40 + a2 + 4) = *(_DWORD *)v41;
        *(_WORD *)(v40 + a2) = 2;
        *(_WORD *)(v40 + a2 + 2) = Flink_high;
        *(_QWORD *)v42 = 0;
      }
      v44 = (__int16)v35[3].Linkage.Blink;
      v45 = 56LL * (unsigned int)*a6;
      v46 = v43 + v45 + 36;
      if ( LOWORD(v35[2].Linkage.Flink[1].Blink) == 23 )
      {
        v71 = HIDWORD(v35[4].Signature);
        *(_DWORD *)(v45 + v43 + 32) = 0;
        *(_WORD *)(v45 + v43 + 28) = 23;
        *(_WORD *)(v45 + v43 + 30) = v44;
        Linkage = v35[4].Linkage;
        *(_DWORD *)(v45 + v43 + 52) = v71;
        *(LIST_ENTRY *)v46 = Linkage;
        v73 = *(_BYTE *)v46;
        if ( *(_BYTE *)v46 == 0xFF )
        {
          v75 = *(_BYTE *)(v46 + 1) & 0xF;
        }
        else
        {
          v93 = 0;
          if ( (v46 & 1) != 0 )
          {
            v74 = &v93;
            v93 = *(__m128i *)v46;
            v73 = _mm_cvtsi128_si32(v93);
          }
          else
          {
            v74 = (__m128i *)(v43 + v45 + 36);
          }
          if ( (v73 != -2 || (v74->m128i_i8[1] & 0xC0) != 0x80)
            && (v74->m128i_i16[0]
             || v74->m128i_i16[1]
             || v74->m128i_i16[2]
             || v74->m128i_i16[3]
             || v74->m128i_i16[4]
             || v74->m128i_i16[5]
             || v74->m128i_i16[6]
             || (v10 = v86, v74->m128i_i16[7] != 256)) )
          {
            if ( (unsigned __int8)v74->m128i_i16[0] == 0xFE && (HIBYTE(v74->m128i_i16[0]) & 0xC0) == 0xC0 )
              v75 = 5;
            else
              v75 = 14;
          }
          else
          {
            v75 = 2;
          }
        }
        if ( !*(_WORD *)v46
          && !*(_WORD *)(v46 + 2)
          && !*(_WORD *)(v46 + 4)
          && !*(_WORD *)(v46 + 6)
          && !*(_WORD *)(v46 + 8)
          && !*(_WORD *)(v46 + 10)
          && !*(_WORD *)(v46 + 12)
          && *(_WORD *)(v46 + 14) == 256
          || v75 == 14 )
        {
          *(_DWORD *)(v45 + v43 + 52) = 0;
        }
        if ( *(_DWORD *)(v45 + v43 + 52) >> 28 == v75 )
          *(_DWORD *)(v45 + v43 + 52) &= 0xFFFFFFFu;
      }
      else
      {
        *(_DWORD *)(v45 + v43 + 32) = v35[4].Linkage.Flink;
        *(_WORD *)(v45 + v43 + 28) = 2;
        *(_WORD *)(v45 + v43 + 30) = v44;
        *(_QWORD *)v46 = 0;
      }
      v8 = v88;
      if ( v88 )
      {
        v47 = 32LL * (unsigned int)*a6;
        *(_OWORD *)(v47 + v88) = 0;
        *(_OWORD *)(v47 + v8 + 16) = 0;
      }
      if ( a4 )
      {
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6) = 11;
        *(_BYTE *)(a4 + 24LL * (unsigned int)*a6 + 4) = 0;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6 + 8) = 0;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6 + 12) = 6;
        *(_DWORD *)(a4 + 24LL * (unsigned int)*a6 + 16) = (signed __int64)(v87 - v35[6].Signature) / 10000;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)&v35[2].Linkage.Blink, v36);
      v48 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v35[2].Signature, 0xFFFFFFFFFFFFFFFFuLL);
      v49 = v48 <= 1;
      v50 = v48 - 1;
      if ( v49 )
      {
        if ( v50 )
          __fastfail(0xEu);
        TcpCleanupTimeWaitTcb(v35);
      }
      ++*a6;
      v51 = (PKSPIN_LOCK)*v13;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&(*v13)->Flags, &v85);
      while ( *((_DWORD *)v51 + 2) )
        ;
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)&v35[2].Linkage.Blink, v36);
      v52 = _InterlockedExchangeAdd64((volatile signed __int64 *)&v35[2].Signature, 0xFFFFFFFFFFFFFFFFuLL);
      v49 = v52 <= 1;
      v53 = v52 - 1;
      if ( v49 )
      {
        if ( v53 )
          __fastfail(0xEu);
        TcpCleanupTimeWaitTcb(v35);
      }
      v54 = (PKSPIN_LOCK)*v13;
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&(*v13)->Flags, &v85);
      while ( *((_DWORD *)v54 + 2) )
        ;
    }
  }
  RtlEndWeakEnumerationHashTable(v13[1] + 1, &Enumerator);
  KeReleaseInStackQueuedSpinLock(&v85);
  InetDereferenceAf(v10);
  return 261;
}

```

## disassembly

```asm
0x140037370  push    rbp
0x140037372  push    rbx
0x140037373  push    rsi
0x140037374  push    rdi
0x140037375  push    r13
0x140037377  push    r14
0x140037379  push    r15
0x14003737b  lea     rbp, [rsp-10h]
0x140037380  sub     rsp, 110h
0x140037387  mov     rdi, [rbp+40h+arg_28]
0x14003738b  xorps   xmm0, xmm0
0x14003738e  xor     eax, eax
0x140037390  movzx   esi, cx
0x140037393  lea     rcx, [rsp+140h+var_D8]
0x140037398  mov     qword ptr [rbp+40h+Enumerator.BucketIndex], rax
0x14003739c  movups  xmmword ptr [rsp+140h+Enumerator], xmm0
0x1400373a1  mov     qword ptr [rsp+140h+var_F8.OldIrql], rax
0x1400373a6  mov     r13, r9
0x1400373a9  movups  xmmword ptr [rbp+40h+Enumerator+10h], xmm0
0x1400373ad  mov     [rsp+140h+var_D8], rax
0x1400373b2  mov     r14, r8
0x1400373b5  movups  xmmword ptr [rsp+140h+var_F8.LockQueue.Next], xmm0
0x1400373ba  mov     [rsp+140h+var_D0], r8
0x1400373bf  mov     [rsp+140h+var_108], rdx
0x1400373c4  call    cs:__imp_KeQuerySystemTimePrecise
0x1400373cb  nop     dword ptr [rax+rax+00h]
0x1400373d0  mov     rcx, gs:188h
0x1400373d9  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400373e0  nop     dword ptr [rax+rax+00h]
0x1400373e5  mov     cl, 2; NewIrql
0x1400373e7  mov     [rsp+140h+var_110], eax
0x1400373eb  call    cs:__imp_KfRaiseIrql
0x1400373f2  nop     dword ptr [rax+rax+00h]
0x1400373f7  movzx   ebx, al
0x1400373fa  xorps   xmm0, xmm0
0x1400373fd  xor     eax, eax
0x1400373ff  mov     qword ptr [rbp+40h+LockHandle.OldIrql], rax
0x140037403  movups  xmmword ptr [rbp+40h+LockHandle.LockQueue.Next], xmm0
0x140037407  lock inc cs:dword_14022A198
0x14003740e  lea     rcx, qword_14022A190; SpinLock
0x140037415  call    cs:__imp_KeTestSpinLock
0x14003741c  nop     dword ptr [rax+rax+00h]
0x140037421  test    al, al
0x140037423  jnz     short loc_14003745A
0x140037425  lock dec cs:dword_14022A198
0x14003742c  lea     rdx, [rbp+40h+LockHandle]; LockHandle
0x140037430  lea     rcx, qword_14022A190; SpinLock
0x140037437  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14003743e  nop     dword ptr [rax+rax+00h]
0x140037443  lock inc cs:dword_14022A198
0x14003744a  lea     rcx, [rbp+40h+LockHandle]; LockHandle
0x14003744e  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140037455  nop     dword ptr [rax+rax+00h]
0x14003745a  lea     r15, TcpInetTransport
0x140037461  mov     r15, [r15+rsi*8+160h]
0x140037469  mov     [rsp+140h+var_E0], r15
0x14003746e  test    r15, r15
0x140037471  jz      loc_1400382C9
0x140037477  mov     eax, gs:1A4h
0x14003747f  xor     edx, edx
0x140037481  mov     r8, [r15+10h]
0x140037485  mov     ecx, 2
0x14003748a  div     dword ptr [r8+14h]
0x14003748e  imul    edx, [r8+10h]
0x140037493  mov     eax, edx
0x140037495  add     rax, [r8]
0x140037498  lock xadd [rax], rcx
0x14003749d  test    cl, 1
0x1400374a0  jz      loc_1400382C9
0x1400374a6  lock add qword ptr [r8+18h], 2
0x1400374ac  lock dec cs:dword_14022A198
0x1400374b3  movzx   ecx, bl; NewIrql
0x1400374b6  call    cs:__imp_KeLowerIrql
0x1400374bd  nop     dword ptr [rax+rax+00h]
0x1400374c2  mov     [rsp+140h+var_38], r12
0x1400374ca  xor     esi, esi
0x1400374cc  cmp     si, cs:PartitionCount
0x1400374d3  mov     [rsp+140h+var_100], esi
0x1400374d7  jnb     loc_14003805D
0x1400374dd  movzx   eax, si
0x1400374e0  lea     rdx, [rsp+140h+var_F8]; LockHandle
0x1400374e5  lea     r12, [rax+rax*2]
0x1400374e9  shl     r12, 6
0x1400374ed  add     r12, cs:PartitionTable
0x1400374f4  mov     rbx, [r12]
0x1400374f8  mov     rcx, rbx; SpinLock
0x1400374fb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140037502  nop     dword ptr [rax+rax+00h]
0x140037507  mov     eax, [rbx+8]
0x14003750a  test    eax, eax
0x14003750c  jnz     short loc_140037507
0x14003750e  mov     rcx, [r12+8]; HashTable
0x140037513  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140037518  call    cs:__imp_RtlInitWeakEnumerationHashTable
0x14003751f  nop     dword ptr [rax+rax+00h]
0x140037524  mov     rcx, [r12+8]; HashTable
0x140037529  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x14003752e  call    cs:__imp_RtlWeaklyEnumerateEntryHashTable
0x140037535  nop     dword ptr [rax+rax+00h]
0x14003753a  test    rax, rax
0x14003753d  jz      loc_140037844
0x140037543  mov     ecx, [rbp+40h+arg_20]
0x140037546  cmp     [rdi], ecx
0x140037548  jz      loc_140038082
0x14003754e  lea     rbx, [rax-30h]
0x140037552  mov     eax, 1
0x140037557  lock xadd [rbx+8], rax
0x14003755d  inc     rax
0x140037560  cmp     rax, 1
0x140037564  jle     loc_1400382BD
0x14003756a  lea     rcx, [rsp+140h+var_F8]; LockHandle
0x14003756f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140037576  nop     dword ptr [rax+rax+00h]
0x14003757b  mov     rcx, rbx; SpinLock
0x14003757e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140037585  nop     dword ptr [rax+rax+00h]
0x14003758a  mov     ecx, [rbx+78h]
0x14003758d  movzx   r15d, al
0x140037591  test    cl, 2
0x140037594  jz      loc_140037B6E
0x14003759a  mov     rdx, [rbx+18h]
0x14003759e  cmp     rdx, [rsp+140h+var_E0]
0x1400375a3  jnz     loc_140037B6E
0x1400375a9  mov     rcx, [rbx+450h]
0x1400375b0  mov     eax, [rsp+140h+var_110]
0x1400375b4  cmp     [rcx], eax
0x1400375b6  jnz     loc_140037B6E
0x1400375bc  mov     rax, [rbx+20h]
0x1400375c0  mov     rsi, [rsp+140h+var_108]
0x1400375c5  movzx   r10d, word ptr [rbx+74h]
0x1400375ca  mov     rcx, [rax]
0x1400375cd  mov     eax, [rdi]
0x1400375cf  lea     r8, [rsi+8]
0x1400375d3  mov     r9, [rcx+10h]
0x1400375d7  imul    rcx, rax, 38h ; '8'
0x1400375db  mov     r11, [r9]
0x1400375de  add     r8, rcx
0x1400375e1  cmp     word ptr [rdx+18h], 17h
0x1400375e6  jz      loc_140037BAD
0x1400375ec  mov     eax, [r11]
0x1400375ef  mov     [rcx+rsi+4], eax
0x1400375f3  xor     eax, eax
0x1400375f5  mov     word ptr [rcx+rsi], 2
0x1400375fb  mov     [rcx+rsi+2], r10w
0x140037601  mov     [r8], rax
0x140037604  mov     eax, [rdi]
0x140037606  lea     rdx, [rsi+24h]
0x14003760a  mov     r8, [rbx+20h]
0x14003760e  movzx   r9d, word ptr [rbx+76h]
0x140037613  imul    rcx, rax, 38h ; '8'
0x140037617  mov     rax, [rbx+18h]
0x14003761b  mov     r10, [r8+10h]
0x14003761f  add     rdx, rcx
0x140037622  cmp     word ptr [rax+18h], 17h
0x140037627  jz      loc_140037CC8
0x14003762d  mov     eax, [r10]
0x140037630  mov     [rcx+rsi+20h], eax
0x140037634  xor     eax, eax
0x140037636  mov     word ptr [rcx+rsi+1Ch], 2
0x14003763d  mov     [rcx+rsi+1Eh], r9w
0x140037643  mov     [rdx], rax
0x140037646  test    r14, r14
0x140037649  jz      loc_140037704
0x14003764f  movzx   ecx, byte ptr [rbx+319h]
0x140037656  mov     eax, [rdi]
0x140037658  and     cl, 1
0x14003765b  shl     rax, 5
0x14003765f  mov     [rax+r14], cl
0x140037663  movzx   ecx, byte ptr [rbx+319h]
0x14003766a  mov     eax, [rdi]
0x14003766c  shl     rax, 5
0x140037670  shr     cl, 2
0x140037673  and     cl, 1
0x140037676  mov     [rax+r14+1], cl
0x14003767b  mov     ecx, [rbx+328h]
0x140037681  mov     eax, [rdi]
0x140037683  shl     rax, 5
0x140037687  shr     ecx, 0Ah
0x14003768a  and     cl, 1
0x14003768d  mov     [rax+r14+2], cl
0x140037692  movzx   ecx, byte ptr [rbx+320h]
0x140037699  mov     eax, [rdi]
0x14003769b  shl     rax, 5
0x14003769f  mov     [rax+r14+4], ecx
0x1400376a4  mov     eax, [rdi]
0x1400376a6  movzx   ecx, byte ptr [rbx+321h]
0x1400376ad  shl     rax, 5
0x1400376b1  mov     [rax+r14+8], ecx
0x1400376b6  mov     rcx, [rbx+350h]; Process
0x1400376bd  call    cs:__imp_PsGetProcessId
0x1400376c4  nop     dword ptr [rax+rax+00h]
0x1400376c9  mov     ecx, [rdi]
0x1400376cb  shl     rcx, 5
0x1400376cf  mov     [rcx+r14+0Ch], eax
0x1400376d4  mov     ecx, [rdi]
0x1400376d6  mov     rax, [rbx+360h]
0x1400376dd  shl     rcx, 5
0x1400376e1  mov     [rcx+r14+10h], rax
0x1400376e6  mov     ecx, [rdi]
0x1400376e8  mov     rax, [rbx+380h]
0x1400376ef  shl     rcx, 5
0x1400376f3  mov     [rcx+r14+18h], rax
0x1400376f8  mov     eax, [rdi]
0x1400376fa  shl     rax, 5
0x1400376fe  mov     byte ptr [rax+r14+3], 0
0x140037704  test    r13, r13
0x140037707  jz      loc_1400377FE
0x14003770d  movzx   edx, byte ptr [rbx+319h]
0x140037714  mov     eax, [rdi]
0x140037716  shr     dl, 5
0x140037719  not     dl
0x14003771b  and     dl, 1
0x14003771e  lea     rcx, [rax+rax*2]
0x140037722  mov     [r13+rcx*8+4], dl
0x140037727  mov     eax, [rdi]
0x140037729  mov     edx, [rbx+70h]
0x14003772c  inc     edx
0x14003772e  lea     rcx, [rax+rax*2]
0x140037732  mov     [r13+rcx*8+0], edx
0x140037737  mov     eax, [rdi]
0x140037739  lea     rcx, [rax+rax*2]
0x14003773d  mov     dword ptr [r13+rcx*8+8], 0
0x140037746  mov     eax, [rdi]
0x140037748  mov     edx, [rbx+2F4h]
0x14003774e  shl     edx, 8
0x140037751  sar     edx, 8
0x140037754  lea     rcx, [rax+rax*2]
0x140037758  mov     rax, 346DC5D63886594Bh
0x140037762  mov     [r13+rcx*8+0Ch], edx
0x140037767  mov     rcx, [rsp+140h+var_D8]
0x14003776c  sub     rcx, [rbx+378h]
0x140037773  imul    rcx
0x140037776  sar     rdx, 0Bh
0x14003777a  mov     rax, rdx
0x14003777d  shr     rax, 3Fh
0x140037781  add     rdx, rax
0x140037784  mov     eax, [rdi]
0x140037786  lea     rcx, [rax+rax*2]
0x14003778a  mov     [r13+rcx*8+10h], edx
0x14003778f  mov     rsi, [rbx+388h]
0x140037796  test    rsi, rsi
0x140037799  jz      short loc_1400377F2
0x14003779b  add     rsi, 278h
0x1400377a2  cmp     qword ptr [rsi+18h], 0
0x1400377a7  jz      short loc_1400377F2
0x1400377a9  mov     rcx, rsi; SpinLock
0x1400377ac  call    RtlAcquireReadLockAtDpcLevel
0x1400377b1  mov     rcx, [rsi+18h]
0x1400377b5  test    rcx, rcx
0x1400377b8  jz      loc_1400382FB
0x1400377be  mov     eax, [rsi+10h]
0x1400377c1  xor     r14d, r14d
0x1400377c4  test    al, 20h
0x1400377c6  jnz     short loc_1400377E5
0x1400377c8  cmp     [rcx+8], r14
0x1400377cc  jz      short loc_1400377D2
0x1400377ce  add     rcx, 10h
0x1400377d2  mov     r14, [rcx]
0x1400377d5  mov     rcx, r14
0x1400377d8  call    EQoSReferenceQoSFlow
0x1400377dd  xor     ecx, ecx
0x1400377df  test    eax, eax
0x1400377e1  cmovs   r14, rcx
0x1400377e5  lock dec dword ptr [rsi+8]
0x1400377e9  test    r14, r14
0x1400377ec  jnz     loc_140038296
0x1400377f2  mov     eax, [rdi]
0x1400377f4  lea     rcx, [rax+rax*2]
0x1400377f8  mov     byte ptr [r13+rcx*8+14h], 0
0x1400377fe  movzx   edx, r15b; NewIrql
0x140037802  mov     rcx, rbx; SpinLock
0x140037805  call    cs:__imp_KeReleaseSpinLock
0x14003780c  nop     dword ptr [rax+rax+00h]
0x140037811  mov     rcx, rbx
0x140037814  call    TcpDereferenceTcb
0x140037819  inc     dword ptr [rdi]
0x14003781b  lea     rdx, [rsp+140h+var_F8]; LockHandle
0x140037820  mov     rbx, [r12]
0x140037824  mov     rcx, rbx; SpinLock
0x140037827  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003782e  nop     dword ptr [rax+rax+00h]
0x140037833  mov     eax, [rbx+8]
0x140037836  test    eax, eax
0x140037838  jnz     short loc_140037833
0x14003783a  mov     r14, [rsp+140h+var_D0]
0x14003783f  jmp     loc_140037524
0x140037844  mov     rcx, [r12+8]; HashTable
0x140037849  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x14003784e  call    cs:__imp_RtlEndWeakEnumerationHashTable
0x140037855  nop     dword ptr [rax+rax+00h]
0x14003785a  mov     rcx, [r12+8]
0x14003785f  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140037864  add     rcx, 78h ; 'x'; HashTable
0x140037868  call    cs:__imp_RtlInitWeakEnumerationHashTable
0x14003786f  nop     dword ptr [rax+rax+00h]
0x140037874  mov     r15, [rsp+140h+var_E0]
0x140037879  mov     rcx, [r12+8]
0x14003787e  lea     rdx, [rsp+140h+Enumerator]; Enumerator
0x140037883  add     rcx, 78h ; 'x'; HashTable
0x140037887  call    cs:__imp_RtlWeaklyEnumerateEntryHashTable
  ... truncated ...
```
