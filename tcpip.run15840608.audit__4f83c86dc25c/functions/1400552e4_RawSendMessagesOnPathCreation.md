# RawSendMessagesOnPathCreation

- ea: `0x1400552e4`
- end: `0x140055965`
- name: `RawSendMessagesOnPathCreation`
- size: `1665`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140054e48`

## callees

- `0x140004070`
- `0x140005480`
- `0x140013140`
- `0x1400148e0`
- `0x14001ea80`
- `0x14001eb30`
- `0x140045860`
- `0x140049760`
- `0x1400552e4`
- `0x140057040`
- `0x140071ac0`
- `0x140072c40`
- `0x1400b4570`
- `0x1400b870c`
- `0x1400cc110`
- `0x1400cd2c0`
- `0x140110de0`
- `0x14011d80c`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140055551`
- `ntoskrnl!KfRaiseIrql` at `0x1400557fd`
- `ntoskrnl!KfRaiseIrql` at `0x140055551`
- `ntoskrnl!KfRaiseIrql` at `0x1400557fd`
- `ntoskrnl!KeLowerIrql` at `0x14005557d`
- `ntoskrnl!KeLowerIrql` at `0x140055865`
- `ntoskrnl!KeLowerIrql` at `0x14005557d`
- `ntoskrnl!KeLowerIrql` at `0x140055865`
- `ntoskrnl!MmSizeOfMdl` at `0x1400556d3`
- `ntoskrnl!MmSizeOfMdl` at `0x1400556d3`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400558df`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400558df`
- `ntoskrnl!IoBuildPartialMdl` at `0x140055769`
- `ntoskrnl!IoBuildPartialMdl` at `0x140055769`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c742c`
- `ntoskrnl!PsGetProcessStartKey` at `0x1401c742c`
- `ntoskrnl!PsGetProcessId` at `0x1401c73ed`
- `ntoskrnl!PsGetProcessId` at `0x1401c73ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005592e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005592e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005588f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005588f`
- `ntoskrnl!ExAllocatePool2` at `0x1400556ec`
- `ntoskrnl!ExAllocatePool2` at `0x1400556ec`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140055378`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140055378`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x140055463`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x140055463`

## pseudocode

```c
__int64 __fastcall RawSendMessagesOnPathCreation(
        int a1,
        __int64 a2,
        char a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        struct _KSPIN_LOCK_QUEUE *a7,
        int a8,
        __int64 a9,
        __int64 a10,
        void (__fastcall *a11)(__int64, _QWORD, __int64),
        __int64 a12)
{
  __int64 v12; // r15
  __int64 v13; // rsi
  __int64 v14; // rdi
  int v18; // r12d
  __int64 v19; // rax
  __int64 v20; // rbx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  _QWORD *v25; // r10
  __int16 v26; // r8
  PMDL v27; // rcx
  KIRQL v28; // al
  unsigned __int64 v29; // r9
  __int64 v30; // rsi
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned int v35; // ecx
  unsigned int v36; // eax
  struct _MDL *Pool2; // rax
  __int64 v38; // rax
  __int64 (__fastcall *v39)(__int128 *); // rax
  int v40; // eax
  KIRQL v41; // al
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rcx
  ADDRESS_FAMILY *v46; // rbx
  int v47; // edx
  ADDRESS_FAMILY *v48; // rax
  __int64 *v49; // rbx
  __int64 v50; // rbx
  __int64 v51; // rcx
  __int64 v52; // rax
  int v53; // edx
  __int64 v54; // rcx
  ADDRESS_FAMILY *v55; // rbx
  int v56; // esi
  int v57; // ebx
  int v58; // edx
  ADDRESS_FAMILY v59; // cx
  UCHAR v60; // al
  int v61; // r8d
  __int64 v62; // r9
  int v63; // [rsp+28h] [rbp-E8h]
  KIRQL NewIrql; // [rsp+90h] [rbp-80h]
  unsigned int v65; // [rsp+94h] [rbp-7Ch]
  ULONG Length[2]; // [rsp+98h] [rbp-78h]
  ADDRESS_FAMILY *Lengtha; // [rsp+98h] [rbp-78h]
  _QWORD *VirtualAddressa; // [rsp+A0h] [rbp-70h]
  unsigned __int64 VirtualAddressb; // [rsp+A0h] [rbp-70h]
  __int64 v71; // [rsp+A8h] [rbp-68h]
  _QWORD v72[18]; // [rsp+D0h] [rbp-40h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+160h] [rbp+50h] BYREF
  __int128 v74; // [rsp+178h] [rbp+68h] BYREF
  _QWORD *v75; // [rsp+188h] [rbp+78h]
  __int64 v76; // [rsp+190h] [rbp+80h]

  v12 = 0;
  v13 = (__int64)a5;
  v14 = a4;
  v18 = a1;
  LockHandle.LockQueue.Next = a7;
  if ( a1 < 0 )
    goto LABEL_24;
  if ( !(unsigned __int8)NetioNcmFastCheckIsAoAcCapable()
    || !a5
    || (v32 = *a5, !*(_BYTE *)(*(_QWORD *)(*a5 + 8) + 88LL)) )
  {
    if ( a3 || (*(_DWORD *)(a2 + 24) & 0x20) != 0 )
      goto LABEL_5;
    memset(v72, 0, 0x88u);
    v76 = 0;
    v75 = v72;
    *((_QWORD *)&v74 + 1) = a9;
    v38 = *(_QWORD *)(v14 + 48);
    *(_QWORD *)&v74 = a5;
    v39 = *(__int64 (__fastcall **)(__int128 *))(v38 + 80);
    v40 = (char *)v39 == (char *)IpNlpQueryPathInformation ? IpNlpQueryPathInformation(&v74) : v39(&v74);
    v18 = v40;
    if ( v40 >= 0 )
    {
      if ( v72[14] )
      {
        if ( (unsigned int)NlppNextHopAddressType(v72[14]) == 4 )
          v18 = -1073741790;
      }
      else
      {
        v18 = -1073741251;
      }
      InetDereferenceNextHopAf(v14);
      if ( v18 >= 0 )
      {
LABEL_5:
        v19 = PplAllocateFromLookasideList(RawSendMessageListPool);
        v12 = v19;
        if ( v19 )
        {
          *(_DWORD *)(v19 + 24) = 1;
          v18 = 259;
          *(_QWORD *)(v19 + 16) = a2;
          *(_QWORD *)(v19 + 32) = 0;
          *(_QWORD *)(v19 + 8) = a12;
          *(_QWORD *)v19 = a11;
          v65 = 0;
          *(_DWORD *)(v19 + 40) = 0;
          while ( a10 )
          {
            v20 = PplAllocateFromLookasideList(RawSendMessagesPool);
            if ( !v20 )
              goto LABEL_22;
            v21 = 0xFFFF;
            v22 = *(_QWORD *)(a10 + 24);
            if ( *(_WORD *)(v14 + 24) != 23 )
              v21 = 65515;
            if ( v22 > v21 )
            {
              PplFreeToLookasideList(RawSendMessagesPool);
              *(_DWORD *)(v12 + 40) = -1073741306;
              break;
            }
            if ( v22 )
            {
              v23 = *(unsigned int *)(a10 + 16);
              v24 = *(_QWORD *)(a10 + 8);
              if ( (_DWORD)v23 )
              {
                v35 = *(_DWORD *)(a10 + 24);
                if ( v35 >= *(_DWORD *)(v24 + 40) - (int)v23 )
                  v35 = *(_DWORD *)(v24 + 40) - v23;
                *(_QWORD *)Length = v35;
                VirtualAddressb = v23 + *(_QWORD *)(v24 + 32) + *(unsigned int *)(v24 + 44);
                v36 = MmSizeOfMdl((PVOID)VirtualAddressb, v35);
                Pool2 = (struct _MDL *)ExAllocatePool2(66, v36, 1297113426);
                *(_QWORD *)&v74 = Pool2;
                *(_QWORD *)v20 = Pool2;
                if ( !Pool2 )
                  goto LABEL_21;
                Pool2->Next = 0;
                Pool2->ByteCount = Length[0];
                Pool2->ByteOffset = VirtualAddressb & 0xFFF;
                Pool2->MdlFlags = 0;
                Pool2->Size = 8 * ((((VirtualAddressb & 0xFFF) + *(_QWORD *)Length + 4095LL) >> 12) + 6);
                Pool2->StartVa = (PVOID)(VirtualAddressb & 0xFFFFFFFFFFFFF000uLL);
                IoBuildPartialMdl(*(PMDL *)(a10 + 8), Pool2, (PVOID)VirtualAddressb, Length[0]);
                v24 = v74;
                **(_QWORD **)v20 = **(_QWORD **)(a10 + 8);
              }
              else
              {
                *(_QWORD *)v20 = 0;
              }
            }
            else
            {
              v24 = 0;
              *(_QWORD *)v20 = 0;
            }
            LOBYTE(v63) = 0;
            VirtualAddressa = (_QWORD *)NetioAllocateAndReferenceNetBufferAndNetBufferList(
                                          RawSendMessagesDatagramsComplete,
                                          v20,
                                          v24,
                                          0,
                                          *(_DWORD *)(a10 + 24),
                                          v63);
            v25 = VirtualAddressa;
            if ( !VirtualAddressa )
            {
              v27 = *(PMDL *)v20;
              if ( *(_QWORD *)v20 )
              {
                if ( (v27->MdlFlags & 0x20) != 0 )
                  MmUnmapLockedPages(v27->MappedSystemVa, *(PMDL *)v20);
                ExFreePoolWithTag(*(PVOID *)v20, 0);
                *(_QWORD *)v20 = 0;
              }
LABEL_21:
              PplFreeToLookasideList(RawSendMessagesPool);
LABEL_22:
              *(_DWORD *)(v12 + 40) = -1073741801;
              break;
            }
            *(_QWORD *)(v20 + 8) = v12;
            *(_QWORD *)(v12 + 32) += *(_QWORD *)(a10 + 24);
            _InterlockedIncrement((volatile signed __int32 *)(v12 + 24));
            ++v65;
            if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
            {
              v41 = KfRaiseIrql(2u);
              v42 = *(_QWORD *)(a2 + 56);
              NewIrql = v41;
              LOBYTE(v43) = v42 != v14;
              v44 = InetFormatLocalSockAddrAtDispatchLevel(v42, v43, *(_QWORD *)(a2 + 112), 0);
              v45 = *(_QWORD *)(a2 + 56);
              v46 = (ADDRESS_FAMILY *)v44;
              LOBYTE(v47) = v45 != v14;
              v48 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                        *(unsigned __int16 *)(v45 + 24),
                                        v47,
                                        1,
                                        *(_QWORD *)(v13 + 16),
                                        *(_DWORD *)(v13 + 8),
                                        0);
              if ( dword_1402241D4 )
              {
                v74 = 0;
                if ( SBYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
                {
                  v59 = *v48;
                  *(_QWORD *)&v74 = a2;
                  SOCKADDR_SIZE(v59);
                  v60 = SOCKADDR_SIZE(*v46);
                  McTemplateK0pqqqqbr4qbr6_EtwWriteTransfer(
                    (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                    (unsigned int)RAW_ENDPOINT_SEND_MESSAGES,
                    (unsigned int)&v74,
                    a2,
                    *(_DWORD *)(a2 + 64),
                    v65,
                    *(_DWORD *)(a10 + 24),
                    v60,
                    (__int64)v46,
                    v61,
                    v62);
                }
              }
              KeLowerIrql(NewIrql);
              v25 = VirtualAddressa;
            }
            if ( *(_WORD *)(v14 + 24) == 23
              && *(_DWORD *)(a2 + 64) == 58
              && (v49 = (__int64 *)v25[1], *((_DWORD *)v49 + 6)) )
            {
              v26 = 2;
              if ( v49 )
              {
                do
                {
                  IppFillChecksumAtOffset(0, 2, v49);
                  v49 = (__int64 *)*v49;
                }
                while ( v49 );
                v13 = (__int64)a5;
                v26 = 2;
                LODWORD(v25) = (_DWORD)VirtualAddressa;
              }
            }
            else
            {
              v26 = -1;
            }
            InetSendDatagramsOnPathAf(
              v14,
              (_DWORD)v25,
              LockHandle.LockQueue.Next,
              a8,
              a9,
              v13,
              0,
              *(_DWORD *)(a2 + 64),
              *(_QWORD *)(a2 + 88),
              0,
              0,
              v26,
              0,
              0,
              0,
              *(_QWORD *)(a2 + 72),
              *(_QWORD *)(v12 + 32));
            a10 = *(_QWORD *)a10;
          }
          v28 = KfRaiseIrql(2u);
          v29 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
          *(_QWORD *)(v29 + *(_QWORD *)(v14 + 128) + 16) += v65;
          KeLowerIrql(v28);
        }
        else
        {
          v18 = -1073741801;
        }
      }
    }
LABEL_24:
    if ( !v13 )
      goto LABEL_26;
    goto LABEL_25;
  }
  LODWORD(v32) = HIDWORD(KeGetPcr()[1].LockArray);
  v18 = -1073741634;
  v33 = 320 * v32;
  ++*((_QWORD *)TcpipGlobalCounters + 40 * v32 + 10);
  if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
  {
    v51 = *(_QWORD *)(a2 + 56);
    LOBYTE(v33) = v51 != v14;
    v52 = InetFormatLocalSockAddrAtDispatchLevel(v51, v33, *(_QWORD *)(a2 + 112), 0);
    v54 = *(_QWORD *)(a2 + 56);
    v55 = (ADDRESS_FAMILY *)v52;
    v71 = v52;
    LOBYTE(v53) = v54 != v14;
    Lengtha = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                  *(unsigned __int16 *)(v54 + 24),
                                  v53,
                                  1,
                                  a5[2],
                                  *((_DWORD *)a5 + 2),
                                  0);
    if ( dword_1402241D4 )
    {
      LockHandle.LockQueue = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredContext) < 0 )
      {
        PsGetProcessId(*(PEPROCESS *)(a2 + 72));
        LockHandle.LockQueue.Lock = 0;
        LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a2;
        v56 = SOCKADDR_SIZE(*Lengtha);
        v57 = SOCKADDR_SIZE(*v55);
        PsGetProcessStartKey(*(_QWORD *)(a2 + 72));
        McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          v58,
          (unsigned int)&LockHandle,
          3,
          a2,
          v57,
          v71,
          v56,
          (__int64)Lengtha);
        v14 = a4;
        v13 = (__int64)a5;
      }
    }
  }
LABEL_25:
  InetLeavePathAf(v14, v13);
LABEL_26:
  v30 = a6;
  if ( a6 )
  {
    if ( a6 != *(_QWORD *)(a2 + 112) )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      RtlAcquireWriteLock(a2, &LockHandle);
      v50 = *(_QWORD *)(a2 + 112);
      *(_QWORD *)(a2 + 112) = a6;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v30 = v50;
    }
    InetDereferenceLocalAddressAf(*(_QWORD *)(a2 + 120), v30);
  }
  if ( v14 != *(_QWORD *)(a2 + 120) && v14 )
    InetDereferenceAf(v14);
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 24), 0xFFFFFFFF) != 1 )
      return 259;
    v18 = *(_DWORD *)(v12 + 40);
    v34 = *(_QWORD *)(v12 + 32);
  }
  else
  {
    v34 = 0;
  }
  a11(a12, (unsigned int)v18, v34);
  RawDereferenceEndpoint(a2);
  if ( v12 )
    PplFreeToLookasideList(RawSendMessageListPool);
  return 259;
}

```

## disassembly

```asm
0x1400552e4  mov     [rsp-8+arg_10], rbx
0x1400552e9  push    rbp
0x1400552ea  push    rsi
0x1400552eb  push    rdi
0x1400552ec  push    r12
0x1400552ee  push    r13
0x1400552f0  push    r14
0x1400552f2  push    r15
0x1400552f4  lea     rbp, [rsp-90h]
0x1400552fc  sub     rsp, 1A0h
0x140055303  mov     rax, cs:__security_cookie
0x14005530a  xor     rax, rsp
0x14005530d  mov     [rbp+0C0h+var_38], rax
0x140055314  mov     rax, [rbp+0C0h+arg_28]
0x14005531b  xor     r15d, r15d
0x14005531e  mov     rsi, [rbp+0C0h+arg_20]
0x140055325  mov     rdi, r9
0x140055328  mov     r14, [rbp+0C0h+arg_48]
0x14005532f  mov     bl, r8b
0x140055332  mov     [rbp+0C0h+var_108], rax
0x140055336  mov     r13, rdx
0x140055339  mov     rax, [rbp+0C0h+arg_30]
0x140055340  mov     r12d, ecx
0x140055343  mov     [rbp+0C0h+LockHandle.LockQueue.Next], rax
0x140055347  mov     rax, [rbp+0C0h+arg_40]
0x14005534e  mov     [rbp+0C0h+var_128], rax
0x140055352  mov     rax, [rbp+0C0h+arg_50]
0x140055359  mov     [rbp+0C0h+var_110], rax
0x14005535d  mov     rax, [rbp+0C0h+arg_58]
0x140055364  mov     [rbp+0C0h+var_118], rax
0x140055368  mov     [rbp+0C0h+VirtualAddress], r9
0x14005536c  mov     [rbp+0C0h+var_120], rsi
0x140055370  test    ecx, ecx
0x140055372  js      loc_140055589
0x140055378  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14005537f  nop     dword ptr [rax+rax+00h]
0x140055384  test    al, al
0x140055386  jnz     loc_14005560D
0x14005538c  test    bl, bl
0x14005538e  jnz     short loc_14005539C
0x140055390  mov     eax, [r13+18h]
0x140055394  test    al, 20h
0x140055396  jz      loc_14005578B
0x14005539c  mov     rcx, cs:RawSendMessageListPool
0x1400553a3  call    PplAllocateFromLookasideList
0x1400553a8  mov     r15, rax
0x1400553ab  test    rax, rax
0x1400553ae  jz      loc_140055666
0x1400553b4  mov     dword ptr [rax+18h], 1
0x1400553bb  mov     r12d, 103h
0x1400553c1  mov     [rax+10h], r13
0x1400553c5  mov     qword ptr [rax+20h], 0
0x1400553cd  mov     rax, [rbp+0C0h+var_118]
0x1400553d1  mov     [r15+8], rax
0x1400553d5  mov     rax, [rbp+0C0h+var_110]
0x1400553d9  mov     [r15], rax
0x1400553dc  mov     [rbp+0C0h+var_13C], 0
0x1400553e3  mov     dword ptr [r15+28h], 0
0x1400553eb  test    r14, r14
0x1400553ee  jz      loc_14005554C
0x1400553f4  mov     rcx, cs:RawSendMessagesPool
0x1400553fb  call    PplAllocateFromLookasideList
0x140055400  mov     rbx, rax
0x140055403  test    rax, rax
0x140055406  jz      loc_140055544
0x14005540c  cmp     word ptr [rdi+18h], 17h
0x140055411  mov     eax, 0FFFFh
0x140055416  mov     rcx, [r14+18h]
0x14005541a  lea     edx, [rax-14h]
0x14005541d  cmovnz  eax, edx
0x140055420  cmp     rcx, rax
0x140055423  ja      loc_1400558ED
0x140055429  test    rcx, rcx
0x14005542c  jz      loc_14005565B
0x140055432  mov     edx, [r14+10h]
0x140055436  mov     r8, [r14+8]
0x14005543a  test    edx, edx
0x14005543c  jnz     loc_1400556A9
0x140055442  mov     qword ptr [rbx], 0
0x140055449  mov     eax, [r14+18h]
0x14005544d  lea     rcx, RawSendMessagesDatagramsComplete
0x140055454  mov     byte ptr [rsp+1D0h+var_1A8], 0
0x140055459  xor     r9d, r9d
0x14005545c  mov     rdx, rbx
0x14005545f  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x140055463  call    cs:__imp_NetioAllocateAndReferenceNetBufferAndNetBufferList
0x14005546a  nop     dword ptr [rax+rax+00h]
0x14005546f  mov     [rbp+0C0h+VirtualAddress], rax
0x140055473  mov     r10, rax
0x140055476  test    rax, rax
0x140055479  jz      loc_140055529
0x14005547f  mov     [rbx+8], r15
0x140055483  mov     rcx, [r14+18h]
0x140055487  add     [r15+20h], rcx
0x14005548b  lock inc dword ptr [r15+18h]
0x140055490  inc     [rbp+0C0h+var_13C]
0x140055493  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+2, 0
0x14005549a  jl      loc_1400557FB
0x1400554a0  cmp     word ptr [rdi+18h], 17h
0x1400554a5  jz      loc_1400558A7
0x1400554ab  mov     r8d, 0FFFFh
0x1400554b1  mov     rax, [r15+20h]
0x1400554b5  xor     ecx, ecx
0x1400554b7  mov     r9d, [rbp+0C0h+arg_38]
0x1400554be  xor     edx, edx
0x1400554c0  mov     [rsp+1D0h+var_150], rax
0x1400554c8  mov     rax, [r13+48h]
0x1400554cc  mov     [rsp+1D0h+var_158], rax
0x1400554d1  mov     rax, [r13+58h]
0x1400554d5  mov     [rsp+1D0h+var_160], ecx
0x1400554d9  mov     [rsp+1D0h+var_168], cx
0x1400554de  mov     word ptr [rsp+1D0h+var_170], dx
0x1400554e3  mov     rdx, r10
0x1400554e6  mov     word ptr [rsp+1D0h+var_178], r8w
0x1400554ec  mov     r8, [rbp+0C0h+LockHandle.LockQueue.Next]
0x1400554f0  mov     dword ptr [rsp+1D0h+var_180], ecx
0x1400554f4  mov     [rsp+1D0h+var_188], rcx
0x1400554f9  mov     [rsp+1D0h+var_190], rax
0x1400554fe  mov     eax, [r13+40h]
0x140055502  mov     [rsp+1D0h+var_198], eax
0x140055506  mov     rax, [rbp+0C0h+var_128]
0x14005550a  mov     [rsp+1D0h+var_1A0], rcx
0x14005550f  mov     rcx, rdi
0x140055512  mov     [rsp+1D0h+var_1A8], rsi
0x140055517  mov     [rsp+1D0h+var_1B0], rax
0x14005551c  call    InetSendDatagramsOnPathAf
0x140055521  mov     r14, [r14]
0x140055524  jmp     loc_1400553EB
0x140055529  mov     rcx, [rbx]
0x14005552c  test    rcx, rcx
0x14005552f  jnz     loc_140055884
0x140055535  mov     rcx, cs:RawSendMessagesPool
0x14005553c  mov     rdx, rbx
0x14005553f  call    PplFreeToLookasideList
0x140055544  mov     dword ptr [r15+28h], 0C0000017h
0x14005554c  mov     ecx, 2; NewIrql
0x140055551  call    cs:__imp_KfRaiseIrql
0x140055558  nop     dword ptr [rax+rax+00h]
0x14005555d  mov     ecx, gs:1A4h
0x140055565  mov     r8, [rdi+80h]
0x14005556c  mov     r9d, ecx
0x14005556f  mov     ecx, [rbp+0C0h+var_13C]
0x140055572  shl     r9, 6
0x140055576  add     [r9+r8+10h], rcx
0x14005557b  mov     cl, al; NewIrql
0x14005557d  call    cs:__imp_KeLowerIrql
0x140055584  nop     dword ptr [rax+rax+00h]
0x140055589  test    rsi, rsi
0x14005558c  jz      short loc_140055599
0x14005558e  mov     rdx, rsi
0x140055591  mov     rcx, rdi
0x140055594  call    InetLeavePathAf
0x140055599  mov     rsi, [rbp+0C0h+var_108]
0x14005559d  test    rsi, rsi
0x1400555a0  jz      short loc_1400555B8
0x1400555a2  cmp     rsi, [r13+70h]
0x1400555a6  jnz     loc_140055909
0x1400555ac  mov     rcx, [r13+78h]
0x1400555b0  mov     rdx, rsi
0x1400555b3  call    InetDereferenceLocalAddressAf
0x1400555b8  cmp     rdi, [r13+78h]
0x1400555bc  jnz     loc_140055942
0x1400555c2  test    r15, r15
0x1400555c5  jz      loc_140055671
0x1400555cb  or      eax, 0FFFFFFFFh
0x1400555ce  lock xadd [r15+18h], eax
0x1400555d4  cmp     eax, 1
0x1400555d7  jz      loc_140055958
0x1400555dd  mov     eax, 103h
0x1400555e2  mov     rcx, [rbp+0C0h+var_38]
0x1400555e9  xor     rcx, rsp; StackCookie
0x1400555ec  call    __security_check_cookie
0x1400555f1  mov     rbx, [rsp+1D0h+arg_10]
0x1400555f9  add     rsp, 1A0h
0x140055600  pop     r15
0x140055602  pop     r14
0x140055604  pop     r13
0x140055606  pop     r12
0x140055608  pop     rdi
0x140055609  pop     rsi
0x14005560a  pop     rbp
0x14005560b  retn
0x14005560d  test    rsi, rsi
0x140055610  jz      loc_14005538C
0x140055616  mov     rax, [rsi]
0x140055619  mov     rcx, [rax+8]
0x14005561d  cmp     [rcx+58h], r15b
0x140055621  jz      loc_14005538C
0x140055627  mov     eax, gs:1A4h
0x14005562f  mov     r12d, 0C00000BEh
0x140055635  lea     rdx, [rax+rax*4]
0x140055639  mov     rax, cs:TcpipGlobalCounters
0x140055640  shl     rdx, 6
0x140055644  inc     qword ptr [rdx+rax+50h]
0x140055649  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, r15b
0x140055650  jge     loc_14005558E
0x140055656  jmp     loc_1401C737A
0x14005565b  xor     r8d, r8d
0x14005565e  mov     [rbx], r8
0x140055661  jmp     loc_140055449
0x140055666  mov     r12d, 0C0000017h
0x14005566c  jmp     loc_140055589
0x140055671  xor     r8d, r8d
0x140055674  mov     rcx, [rbp+0C0h+var_118]
0x140055678  mov     edx, r12d
0x14005567b  mov     rax, [rbp+0C0h+var_110]
0x14005567f  call    _guard_dispatch_icall
0x140055684  mov     rcx, r13
0x140055687  call    RawDereferenceEndpoint
0x14005568c  test    r15, r15
0x14005568f  jz      loc_1400555DD
0x140055695  mov     rcx, cs:RawSendMessageListPool
0x14005569c  mov     rdx, r15
0x14005569f  call    PplFreeToLookasideList
0x1400556a4  jmp     loc_1400555DD
0x1400556a9  mov     ecx, [r14+18h]
0x1400556ad  mov     eax, [r8+28h]
0x1400556b1  sub     eax, edx
0x1400556b3  cmp     ecx, eax
0x1400556b5  cmovnb  ecx, eax
0x1400556b8  mov     eax, [r8+2Ch]
0x1400556bc  add     rax, [r8+20h]
0x1400556c0  add     rax, rdx
0x1400556c3  mov     r9d, ecx
0x1400556c6  mov     edx, ecx; Length
0x1400556c8  mov     rcx, rax; Base
0x1400556cb  mov     qword ptr [rbp+0C0h+Length], r9
0x1400556cf  mov     [rbp+0C0h+VirtualAddress], rax
0x1400556d3  call    cs:__imp_MmSizeOfMdl
0x1400556da  nop     dword ptr [rax+rax+00h]
0x1400556df  mov     edx, eax
0x1400556e1  mov     ecx, 42h ; 'B'
0x1400556e6  mov     r8d, 4D506152h
0x1400556ec  call    cs:__imp_ExAllocatePool2
0x1400556f3  nop     dword ptr [rax+rax+00h]
0x1400556f8  mov     qword ptr [rbp+0C0h+var_58], rax
0x1400556fc  mov     r10, rax
0x1400556ff  mov     [rbx], rax
0x140055702  test    rax, rax
0x140055705  jz      loc_140055535
0x14005570b  mov     r8, [rbp+0C0h+VirtualAddress]; VirtualAddress
0x14005570f  mov     r11d, 0FFFh
0x140055715  mov     r9, qword ptr [rbp+0C0h+Length]; Length
0x140055719  mov     edx, r8d
0x14005571c  mov     qword ptr [rax], 0
0x140055723  mov     eax, edx
0x140055725  and     rax, r11
0x140055728  mov     [r10+28h], r9d
0x14005572c  and     edx, r11d
0x14005572f  mov     [r10+2Ch], edx
0x140055733  lea     rcx, [r9+0FFFh]
0x14005573a  add     rcx, rax
0x14005573d  mov     rdx, r10; TargetMdl
0x140055740  xor     eax, eax
0x140055742  shr     rcx, 0Ch
0x140055746  mov     [r10+0Ah], ax
0x14005574b  add     cx, 6
0x14005574f  shl     cx, 3
0x140055753  mov     rax, r8
0x140055756  and     rax, 0FFFFFFFFFFFFF000h
0x14005575c  mov     [r10+8], cx
0x140055761  mov     [r10+20h], rax
0x140055765  mov     rcx, [r14+8]; SourceMdl
0x140055769  call    cs:__imp_IoBuildPartialMdl
0x140055770  nop     dword ptr [rax+rax+00h]
0x140055775  mov     rax, [r14+8]
0x140055779  mov     rcx, [rbx]
0x14005577c  mov     r8, qword ptr [rbp+0C0h+var_58]
0x140055780  mov     rax, [rax]
0x140055783  mov     [rcx], rax
0x140055786  jmp     loc_140055449
0x14005578b  xor     edx, edx; Val
0x14005578d  lea     rcx, [rbp+0C0h+var_100]; void *
0x140055791  mov     r8d, 88h; Size
0x140055797  call    memset
0x14005579c  lea     rax, [rbp+0C0h+var_100]
0x1400557a0  mov     [rbp+0C0h+var_40], r15
0x1400557a7  mov     [rbp+0C0h+var_48], rax
0x1400557ab  lea     rcx, IpNlpQueryPathInformation
0x1400557b2  mov     rax, [rbp+0C0h+var_128]
0x1400557b6  mov     qword ptr [rbp+0C0h+var_58+8], rax
0x1400557ba  mov     rax, [rdi+30h]
0x1400557be  mov     qword ptr [rbp+0C0h+var_58], rsi
0x1400557c2  mov     rax, [rax+50h]
0x1400557c6  cmp     rax, rcx
0x1400557c9  lea     rcx, [rbp+0C0h+var_58]
0x1400557cd  jnz     loc_14005587A
0x1400557d3  call    IpNlpQueryPathInformation
0x1400557d8  mov     r12d, eax
0x1400557db  test    eax, eax
0x1400557dd  js      loc_140055589
0x1400557e3  mov     rcx, [rbp+0C0h+var_90]
0x1400557e7  test    rcx, rcx
0x1400557ea  jnz     loc_1401C7488
0x1400557f0  mov     r12d, 0C000023Dh
0x1400557f6  jmp     loc_1401C7499
0x1400557fb  mov     cl, 2; NewIrql
0x1400557fd  call    cs:__imp_KfRaiseIrql
0x140055804  nop     dword ptr [rax+rax+00h]
0x140055809  mov     rcx, [r13+38h]
  ... truncated ...
```
