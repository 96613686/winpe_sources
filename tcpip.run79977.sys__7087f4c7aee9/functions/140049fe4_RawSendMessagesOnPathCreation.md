# RawSendMessagesOnPathCreation

- ea: `0x140049fe4`
- end: `0x14004a7bf`
- name: `RawSendMessagesOnPathCreation`
- size: `2011`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14004b10c`

## callees

- `0x140013140`
- `0x1400143c0`
- `0x14002f4a0`
- `0x140030620`
- `0x140039b00`
- `0x14003b920`
- `0x140049fe4`
- `0x140052870`
- `0x140054010`
- `0x140058870`
- `0x14005e920`
- `0x140083f6c`
- `0x140096560`
- `0x1400b7ca0`
- `0x1400b7d50`
- `0x1400c3440`
- `0x1401067a0`
- `0x14011393c`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14004a448`
- `ntoskrnl!KfRaiseIrql` at `0x14004a67d`
- `ntoskrnl!KfRaiseIrql` at `0x14004a448`
- `ntoskrnl!KfRaiseIrql` at `0x14004a67d`
- `ntoskrnl!KeLowerIrql` at `0x14004a51c`
- `ntoskrnl!KeLowerIrql` at `0x14004a6a9`
- `ntoskrnl!KeLowerIrql` at `0x14004a51c`
- `ntoskrnl!KeLowerIrql` at `0x14004a6a9`
- `ntoskrnl!MmSizeOfMdl` at `0x14004a33f`
- `ntoskrnl!MmSizeOfMdl` at `0x14004a33f`
- `ntoskrnl!MmUnmapLockedPages` at `0x14004a63d`
- `ntoskrnl!MmUnmapLockedPages` at `0x14004a63d`
- `ntoskrnl!IoBuildPartialMdl` at `0x14004a3d5`
- `ntoskrnl!IoBuildPartialMdl` at `0x14004a3d5`
- `ntoskrnl!PsGetProcessStartKey` at `0x14004a184`
- `ntoskrnl!PsGetProcessStartKey` at `0x14004a184`
- `ntoskrnl!PsGetProcessId` at `0x14004a145`
- `ntoskrnl!PsGetProcessId` at `0x14004a145`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004a6f9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004a6f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a64e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a64e`
- `ntoskrnl!ExAllocatePool2` at `0x14004a358`
- `ntoskrnl!ExAllocatePool2` at `0x14004a358`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14004a078`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14004a078`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14004a40c`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14004a40c`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14004a59e`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14004a59e`

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
  __int64 v15; // r14
  int PathInfoAf; // r12d
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r10
  ADDRESS_FAMILY *v24; // rbx
  int v25; // edx
  int v26; // esi
  int v27; // ebx
  int v28; // edx
  __int64 v29; // rax
  __int64 v30; // rbx
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // rdx
  unsigned int v35; // ecx
  unsigned int v36; // eax
  struct _MDL *Pool2; // rax
  __int64 v38; // rax
  KIRQL v39; // al
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // r10
  ADDRESS_FAMILY *v44; // rbx
  int v45; // edx
  ADDRESS_FAMILY *v46; // rax
  ADDRESS_FAMILY v47; // cx
  UCHAR v48; // al
  int v49; // r8d
  __int64 v50; // r9
  __int64 *v51; // rbx
  __int16 v52; // bx
  PMDL v53; // rcx
  KIRQL v54; // al
  unsigned __int64 v55; // r9
  __int64 v56; // rsi
  __int64 v57; // rbx
  __int64 v58; // r8
  __int64 v60; // [rsp+20h] [rbp-F0h]
  int v61; // [rsp+28h] [rbp-E8h]
  KIRQL NewIrql; // [rsp+90h] [rbp-80h]
  unsigned int v63; // [rsp+94h] [rbp-7Ch]
  ADDRESS_FAMILY *VirtualAddress; // [rsp+98h] [rbp-78h]
  unsigned __int64 VirtualAddressa; // [rsp+98h] [rbp-78h]
  PVOID VirtualAddressb; // [rsp+98h] [rbp-78h]
  __int64 v67; // [rsp+A0h] [rbp-70h]
  ULONG Length[2]; // [rsp+C8h] [rbp-48h]
  _QWORD v70[17]; // [rsp+E0h] [rbp-30h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+170h] [rbp+60h] BYREF
  __int128 v72; // [rsp+188h] [rbp+78h] BYREF

  v12 = 0;
  v13 = (__int64)a5;
  v14 = a4;
  v15 = a10;
  PathInfoAf = a1;
  LockHandle.LockQueue.Next = a7;
  if ( a1 < 0 )
    goto LABEL_57;
  if ( !(unsigned __int8)NetioNcmFastCheckIsAoAcCapable()
    || !a5
    || (v19 = *a5, !*(_BYTE *)(*(_QWORD *)(*a5 + 8) + 88LL)) )
  {
    if ( a3 || (*(_DWORD *)(a2 + 24) & 0x20) != 0 )
      goto LABEL_17;
    memset(v70, 0, sizeof(v70));
    PathInfoAf = InetQueryPathInfoAf(v14, (_DWORD)a5, a9, (unsigned int)v70, 0);
    if ( PathInfoAf >= 0 )
    {
      if ( v70[14] )
      {
        if ( (unsigned int)NlppNextHopAddressType(v70[14]) == 4 )
          PathInfoAf = -1073741790;
      }
      else
      {
        PathInfoAf = -1073741251;
      }
      InetDereferenceNextHopAf(v14);
      if ( PathInfoAf >= 0 )
      {
LABEL_17:
        v29 = PplAllocateFromLookasideList(RawSendMessageListPool);
        v12 = v29;
        if ( v29 )
        {
          *(_DWORD *)(v29 + 24) = 1;
          PathInfoAf = 259;
          *(_QWORD *)(v29 + 16) = a2;
          *(_QWORD *)(v29 + 32) = 0;
          *(_QWORD *)(v29 + 8) = a12;
          *(_QWORD *)v29 = a11;
          v63 = 0;
          *(_DWORD *)(v29 + 40) = 0;
          if ( a10 )
          {
            while ( 1 )
            {
              v30 = PplAllocateFromLookasideList(RawSendMessagesPool);
              if ( !v30 )
                goto LABEL_55;
              v31 = 0xFFFF;
              v32 = *(_QWORD *)(v15 + 24);
              if ( *(_WORD *)(v14 + 24) != 23 )
                v31 = 65515;
              if ( v32 > v31 )
                break;
              if ( v32 )
              {
                v34 = *(unsigned int *)(v15 + 16);
                v33 = *(_QWORD *)(v15 + 8);
                if ( (_DWORD)v34 )
                {
                  v35 = *(_DWORD *)(v15 + 24);
                  if ( v35 >= *(_DWORD *)(v33 + 40) - (int)v34 )
                    v35 = *(_DWORD *)(v33 + 40) - v34;
                  *(_QWORD *)Length = v35;
                  VirtualAddressa = v34 + *(_QWORD *)(v33 + 32) + *(unsigned int *)(v33 + 44);
                  v36 = MmSizeOfMdl((PVOID)VirtualAddressa, v35);
                  Pool2 = (struct _MDL *)ExAllocatePool2(66, v36, 1297113426);
                  *(_QWORD *)&v72 = Pool2;
                  *(_QWORD *)v30 = Pool2;
                  if ( !Pool2 )
                    goto LABEL_54;
                  Pool2->Next = 0;
                  Pool2->ByteCount = Length[0];
                  Pool2->ByteOffset = VirtualAddressa & 0xFFF;
                  Pool2->MdlFlags = 0;
                  Pool2->Size = 8 * ((((VirtualAddressa & 0xFFF) + *(_QWORD *)Length + 4095LL) >> 12) + 6);
                  Pool2->StartVa = (PVOID)(VirtualAddressa & 0xFFFFFFFFFFFFF000uLL);
                  IoBuildPartialMdl(*(PMDL *)(v15 + 8), Pool2, (PVOID)VirtualAddressa, Length[0]);
                  v33 = v72;
                  **(_QWORD **)v30 = **(_QWORD **)(v15 + 8);
                }
                else
                {
                  *(_QWORD *)v30 = 0;
                }
              }
              else
              {
                v33 = 0;
                *(_QWORD *)v30 = 0;
              }
              LOBYTE(v61) = 0;
              v38 = NetioAllocateAndReferenceNetBufferAndNetBufferList(
                      RawSendMessagesDatagramsComplete,
                      v30,
                      v33,
                      0,
                      *(_DWORD *)(v15 + 24),
                      v61);
              VirtualAddressb = (PVOID)v38;
              if ( !v38 )
              {
                v53 = *(PMDL *)v30;
                if ( *(_QWORD *)v30 )
                {
                  if ( (v53->MdlFlags & 0x20) != 0 )
                    MmUnmapLockedPages(v53->MappedSystemVa, *(PMDL *)v30);
                  ExFreePoolWithTag(*(PVOID *)v30, 0);
                  *(_QWORD *)v30 = 0;
                }
LABEL_54:
                PplFreeToLookasideList(RawSendMessagesPool);
LABEL_55:
                *(_DWORD *)(v12 + 40) = -1073741801;
                goto LABEL_56;
              }
              *(_QWORD *)(v30 + 8) = v12;
              *(_QWORD *)(v12 + 32) += *(_QWORD *)(v15 + 24);
              _InterlockedIncrement((volatile signed __int32 *)(v12 + 24));
              ++v63;
              if ( SBYTE2(WPP_MAIN_CB.Reserved) < 0 )
              {
                v39 = KfRaiseIrql(2u);
                v40 = *(_QWORD *)(a2 + 56);
                NewIrql = v39;
                LOBYTE(v41) = v40 != v14;
                v42 = InetFormatLocalSockAddrAtDispatchLevel(v40, v41, *(_QWORD *)(a2 + 112), 0);
                v43 = *(_QWORD *)(a2 + 56);
                v44 = (ADDRESS_FAMILY *)v42;
                LOBYTE(v45) = v43 != v14;
                v46 = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                          *(unsigned __int16 *)(v43 + 24),
                                          v45,
                                          1,
                                          *(_QWORD *)(v13 + 16),
                                          *(_DWORD *)(v13 + 8),
                                          0);
                if ( dword_1402201D4 )
                {
                  v72 = 0;
                  if ( SBYTE2(WPP_MAIN_CB.Reserved) < 0 )
                  {
                    v47 = *v46;
                    *(_QWORD *)&v72 = a2;
                    SOCKADDR_SIZE(v47);
                    v48 = SOCKADDR_SIZE(*v44);
                    McTemplateK0pqqqqbr4qbr6_EtwWriteTransfer(
                      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
                      (unsigned int)&RAW_ENDPOINT_SEND_MESSAGES,
                      (unsigned int)&v72,
                      a2,
                      *(_DWORD *)(a2 + 64),
                      v63,
                      *(_DWORD *)(v15 + 24),
                      v48,
                      (__int64)v44,
                      v49,
                      v50);
                  }
                }
                KeLowerIrql(NewIrql);
                v38 = (__int64)VirtualAddressb;
              }
              if ( *(_WORD *)(v14 + 24) == 23
                && *(_DWORD *)(a2 + 64) == 58
                && (v51 = *(__int64 **)(v38 + 8), *((_DWORD *)v51 + 6)) )
              {
                if ( v51 )
                {
                  do
                  {
                    IppFillChecksumAtOffset(0, 2, v51);
                    v51 = (__int64 *)*v51;
                  }
                  while ( v51 );
                  v13 = (__int64)a5;
                  v38 = (__int64)VirtualAddressb;
                }
                v52 = 2;
              }
              else
              {
                v52 = -1;
              }
              if ( LOBYTE(WPP_MAIN_CB.DeviceExtension) )
              {
                LODWORD(v60) = 1;
                NdisNblTrackerTransferOwnership(v38, 0, RawNblTracker, 159, v60);
              }
              InetSendDatagramsOnPathAf(
                v14,
                (_DWORD)VirtualAddressb,
                LockHandle.LockQueue.Next,
                a8,
                a9,
                v13,
                0,
                *(_DWORD *)(a2 + 64),
                *(_QWORD *)(a2 + 88),
                0,
                0,
                v52,
                0,
                0,
                0,
                *(_QWORD *)(a2 + 72),
                *(_QWORD *)(v12 + 32));
              v15 = *(_QWORD *)v15;
              if ( !v15 )
                goto LABEL_56;
            }
            PplFreeToLookasideList(RawSendMessagesPool);
            *(_DWORD *)(v12 + 40) = -1073741306;
          }
LABEL_56:
          v54 = KfRaiseIrql(2u);
          v55 = (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 6;
          *(_QWORD *)(v55 + *(_QWORD *)(v14 + 128) + 16) += v63;
          KeLowerIrql(v54);
        }
        else
        {
          PathInfoAf = -1073741801;
        }
      }
    }
LABEL_57:
    if ( !v13 )
      goto LABEL_59;
    goto LABEL_58;
  }
  LODWORD(v19) = HIDWORD(KeGetPcr()[1].LockArray);
  PathInfoAf = -1073741634;
  v20 = 320 * v19;
  ++*((_QWORD *)TcpipGlobalCounters + 40 * v19 + 10);
  if ( *((char *)&WPP_MAIN_CB.Reserved + 8) < 0 )
  {
    v21 = *(_QWORD *)(a2 + 56);
    LOBYTE(v20) = v21 != v14;
    v22 = InetFormatLocalSockAddrAtDispatchLevel(v21, v20, *(_QWORD *)(a2 + 112), 0);
    v23 = *(_QWORD *)(a2 + 56);
    v24 = (ADDRESS_FAMILY *)v22;
    v67 = v22;
    LOBYTE(v25) = v23 != v14;
    VirtualAddress = (ADDRESS_FAMILY *)InetFormatSockAddrAtDispatchLevel(
                                         *(unsigned __int16 *)(v23 + 24),
                                         v25,
                                         1,
                                         a5[2],
                                         *((_DWORD *)a5 + 2),
                                         0);
    if ( dword_1402201D4 )
    {
      LockHandle.LockQueue = 0;
      if ( *((char *)&WPP_MAIN_CB.Reserved + 8) < 0 )
      {
        PsGetProcessId(*(PEPROCESS *)(a2 + 72));
        LockHandle.LockQueue.Lock = 0;
        LockHandle.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)a2;
        v26 = SOCKADDR_SIZE(*VirtualAddress);
        v27 = SOCKADDR_SIZE(*v24);
        PsGetProcessStartKey(*(_QWORD *)(a2 + 72));
        McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          v28,
          (unsigned int)&LockHandle,
          3,
          a2,
          v27,
          v67,
          v26,
          (__int64)VirtualAddress);
        v14 = a4;
        v13 = (__int64)a5;
      }
    }
  }
LABEL_58:
  InetLeavePathAf(v14, v13);
LABEL_59:
  v56 = a6;
  if ( a6 )
  {
    if ( a6 != *(_QWORD *)(a2 + 112) )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      RtlAcquireWriteLock(a2, &LockHandle);
      v57 = *(_QWORD *)(a2 + 112);
      *(_QWORD *)(a2 + 112) = a6;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v56 = v57;
    }
    InetDereferenceLocalAddressAf(*(_QWORD *)(a2 + 120), v56);
  }
  if ( v14 != *(_QWORD *)(a2 + 120) && v14 )
    InetDereferenceAf(v14);
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 24), 0xFFFFFFFF) != 1 )
      return 259;
    PathInfoAf = *(_DWORD *)(v12 + 40);
    v58 = *(_QWORD *)(v12 + 32);
  }
  else
  {
    v58 = 0;
  }
  a11(a12, (unsigned int)PathInfoAf, v58);
  RawDereferenceEndpoint(a2);
  if ( v12 )
    PplFreeToLookasideList(RawSendMessageListPool);
  return 259;
}

```

## disassembly

```asm
0x140049fe4  mov     [rsp-8+arg_10], rbx
0x140049fe9  push    rbp
0x140049fea  push    rsi
0x140049feb  push    rdi
0x140049fec  push    r12
0x140049fee  push    r13
0x140049ff0  push    r14
0x140049ff2  push    r15
0x140049ff4  lea     rbp, [rsp-90h]
0x140049ffc  sub     rsp, 1A0h
0x14004a003  mov     rax, cs:__security_cookie
0x14004a00a  xor     rax, rsp
0x14004a00d  mov     [rbp+0C0h+var_38], rax
0x14004a014  mov     rax, [rbp+0C0h+arg_28]
0x14004a01b  xor     r15d, r15d
0x14004a01e  mov     rsi, [rbp+0C0h+arg_20]
0x14004a025  mov     rdi, r9
0x14004a028  mov     r14, [rbp+0C0h+arg_48]
0x14004a02f  mov     bl, r8b
0x14004a032  mov     [rbp+0C0h+var_100], rax
0x14004a036  mov     r13, rdx
0x14004a039  mov     rax, [rbp+0C0h+arg_30]
0x14004a040  mov     r12d, ecx
0x14004a043  mov     [rbp+0C0h+LockHandle.LockQueue.Next], rax
0x14004a047  mov     rax, [rbp+0C0h+arg_40]
0x14004a04e  mov     [rbp+0C0h+var_130], rax
0x14004a052  mov     rax, [rbp+0C0h+arg_50]
0x14004a059  mov     [rbp+0C0h+var_110], rax
0x14004a05d  mov     rax, [rbp+0C0h+arg_58]
0x14004a064  mov     [rbp+0C0h+var_118], rax
0x14004a068  mov     [rbp+0C0h+var_128], r9
0x14004a06c  mov     [rbp+0C0h+var_120], rsi
0x14004a070  test    ecx, ecx
0x14004a072  js      loc_14004A6B5
0x14004a078  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x14004a07f  nop     dword ptr [rax+rax+00h]
0x14004a084  test    al, al
0x14004a086  jz      loc_14004A1DE
0x14004a08c  test    rsi, rsi
0x14004a08f  jz      loc_14004A1DE
0x14004a095  mov     rax, [rsi]
0x14004a098  mov     rcx, [rax+8]
0x14004a09c  cmp     [rcx+58h], r15b
0x14004a0a0  jz      loc_14004A1DE
0x14004a0a6  mov     eax, gs:1A4h
0x14004a0ae  mov     r12d, 0C00000BEh
0x14004a0b4  lea     rdx, [rax+rax*4]
0x14004a0b8  mov     rax, cs:TcpipGlobalCounters
0x14004a0bf  shl     rdx, 6
0x14004a0c3  inc     qword ptr [rdx+rax+50h]
0x14004a0c8  cmp     byte ptr cs:WPP_MAIN_CB+148h, r15b
0x14004a0cf  jge     loc_14004A6BA
0x14004a0d5  mov     rcx, [r13+38h]
0x14004a0d9  xor     r9d, r9d
0x14004a0dc  mov     r8, [r13+70h]
0x14004a0e0  cmp     rcx, rdi
0x14004a0e3  setnz   dl
0x14004a0e6  call    InetFormatLocalSockAddrAtDispatchLevel
0x14004a0eb  mov     r10, [r13+38h]
0x14004a0ef  lea     r8d, [r15+1]
0x14004a0f3  mov     r9, [rsi+10h]
0x14004a0f7  xor     ecx, ecx
0x14004a0f9  mov     word ptr [rsp+1D0h+var_1A8], cx
0x14004a0fe  cmp     r10, rdi
0x14004a101  mov     rbx, rax
0x14004a104  mov     [rbp+0C0h+var_130], rax
0x14004a108  mov     eax, [rsi+8]
0x14004a10b  setnz   dl
0x14004a10e  movzx   ecx, word ptr [r10+18h]
0x14004a113  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14004a117  call    InetFormatSockAddrAtDispatchLevel
0x14004a11c  cmp     cs:dword_1402201D4, r15d
0x14004a123  mov     [rbp+0C0h+VirtualAddress], rax
0x14004a127  jz      loc_14004A6BA
0x14004a12d  cmp     byte ptr cs:WPP_MAIN_CB+148h, r15b
0x14004a134  xorps   xmm0, xmm0
0x14004a137  movups  xmmword ptr [rbp+0C0h+LockHandle.LockQueue.Next], xmm0
0x14004a13b  jge     loc_14004A6BA
0x14004a141  mov     rcx, [r13+48h]; Process
0x14004a145  call    cs:__imp_PsGetProcessId
0x14004a14c  nop     dword ptr [rax+rax+00h]
0x14004a151  mov     rcx, [rsi]
0x14004a154  mov     r14, rax
0x14004a157  mov     [rbp+0C0h+LockHandle.LockQueue.Lock], r15
0x14004a15b  mov     [rbp+0C0h+LockHandle.LockQueue.Next], r13
0x14004a15f  mov     rdx, [rcx+8]
0x14004a163  mov     rcx, [rbp+0C0h+VirtualAddress]
0x14004a167  mov     edi, [rdx+8]
0x14004a16a  movzx   ecx, word ptr [rcx]; af
0x14004a16d  call    SOCKADDR_SIZE
0x14004a172  movzx   ecx, word ptr [rbx]; af
0x14004a175  movzx   esi, al
0x14004a178  call    SOCKADDR_SIZE
0x14004a17d  mov     rcx, [r13+48h]
0x14004a181  movzx   ebx, al
0x14004a184  call    cs:__imp_PsGetProcessStartKey
0x14004a18b  nop     dword ptr [rax+rax+00h]
0x14004a190  mov     [rsp+1D0h+var_170], rax
0x14004a195  lea     r9d, [r15+3]
0x14004a199  mov     rax, [rbp+0C0h+VirtualAddress]
0x14004a19d  lea     r8, [rbp+0C0h+LockHandle]
0x14004a1a1  mov     [rsp+1D0h+var_178], edi
0x14004a1a5  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14004a1ac  mov     dword ptr [rsp+1D0h+var_180], r14d
0x14004a1b1  mov     [rsp+1D0h+var_190], rax
0x14004a1b6  mov     rax, [rbp+0C0h+var_130]
0x14004a1ba  mov     [rsp+1D0h+var_198], esi
0x14004a1be  mov     [rsp+1D0h+var_1A0], rax
0x14004a1c3  mov     dword ptr [rsp+1D0h+var_1A8], ebx
0x14004a1c7  mov     [rsp+1D0h+var_1B0], r13
0x14004a1cc  call    McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer
0x14004a1d1  mov     rdi, [rbp+0C0h+var_128]
0x14004a1d5  mov     rsi, [rbp+0C0h+var_120]
0x14004a1d9  jmp     loc_14004A6BA
0x14004a1de  test    bl, bl
0x14004a1e0  jnz     short loc_14004A254
0x14004a1e2  mov     eax, [r13+18h]
0x14004a1e6  test    al, 20h
0x14004a1e8  jnz     short loc_14004A254
0x14004a1ea  xor     edx, edx; Val
0x14004a1ec  lea     rcx, [rbp+0C0h+var_F0]; void *
0x14004a1f0  mov     r8d, 88h; Size
0x14004a1f6  call    memset
0x14004a1fb  mov     r8, [rbp+0C0h+var_130]
0x14004a1ff  lea     r9, [rbp+0C0h+var_F0]
0x14004a203  mov     rdx, rsi
0x14004a206  mov     [rsp+1D0h+var_1B0], r15
0x14004a20b  mov     rcx, rdi
0x14004a20e  call    InetQueryPathInfoAf
0x14004a213  mov     r12d, eax
0x14004a216  test    eax, eax
0x14004a218  js      loc_14004A6B5
0x14004a21e  mov     rcx, [rbp+0C0h+var_80]
0x14004a222  test    rcx, rcx
0x14004a225  jnz     short loc_14004A22F
0x14004a227  mov     r12d, 0C000023Dh
0x14004a22d  jmp     short loc_14004A240
0x14004a22f  call    NlppNextHopAddressType
0x14004a234  cmp     eax, 4
0x14004a237  mov     edx, 0C0000022h
0x14004a23c  cmovz   r12d, edx
0x14004a240  mov     rdx, rcx
0x14004a243  mov     rcx, rdi
0x14004a246  call    InetDereferenceNextHopAf
0x14004a24b  test    r12d, r12d
0x14004a24e  js      loc_14004A6B5
0x14004a254  mov     rcx, cs:RawSendMessageListPool
0x14004a25b  call    PplAllocateFromLookasideList
0x14004a260  mov     r15, rax
0x14004a263  test    rax, rax
0x14004a266  jnz     short loc_14004A273
0x14004a268  mov     r12d, 0C0000017h
0x14004a26e  jmp     loc_14004A6B5
0x14004a273  mov     dword ptr [rax+18h], 1
0x14004a27a  mov     r12d, 103h
0x14004a280  mov     [rax+10h], r13
0x14004a284  mov     ecx, 2
0x14004a289  mov     qword ptr [rax+20h], 0
0x14004a291  mov     rax, [rbp+0C0h+var_118]
0x14004a295  mov     [r15+8], rax
0x14004a299  mov     rax, [rbp+0C0h+var_110]
0x14004a29d  mov     [r15], rax
0x14004a2a0  mov     [rbp+0C0h+var_13C], 0
0x14004a2a7  mov     dword ptr [r15+28h], 0
0x14004a2af  test    r14, r14
0x14004a2b2  jz      loc_14004A67D
0x14004a2b8  mov     rcx, cs:RawSendMessagesPool
0x14004a2bf  call    PplAllocateFromLookasideList
0x14004a2c4  mov     rbx, rax
0x14004a2c7  test    rax, rax
0x14004a2ca  jz      loc_14004A670
0x14004a2d0  cmp     word ptr [rdi+18h], 17h
0x14004a2d5  mov     eax, 0FFFFh
0x14004a2da  mov     rcx, [r14+18h]
0x14004a2de  lea     edx, [rax-14h]
0x14004a2e1  cmovnz  eax, edx
0x14004a2e4  cmp     rcx, rax
0x14004a2e7  ja      loc_14004A744
0x14004a2ed  test    rcx, rcx
0x14004a2f0  jnz     short loc_14004A2FD
0x14004a2f2  xor     r8d, r8d
0x14004a2f5  mov     [rbx], r8
0x14004a2f8  jmp     loc_14004A3F2
0x14004a2fd  mov     edx, [r14+10h]
0x14004a301  mov     r8, [r14+8]
0x14004a305  test    edx, edx
0x14004a307  jnz     short loc_14004A315
0x14004a309  mov     qword ptr [rbx], 0
0x14004a310  jmp     loc_14004A3F2
0x14004a315  mov     ecx, [r14+18h]
0x14004a319  mov     eax, [r8+28h]
0x14004a31d  sub     eax, edx
0x14004a31f  cmp     ecx, eax
0x14004a321  cmovnb  ecx, eax
0x14004a324  mov     eax, [r8+2Ch]
0x14004a328  add     rax, [r8+20h]
0x14004a32c  add     rax, rdx
0x14004a32f  mov     r9d, ecx
0x14004a332  mov     edx, ecx; Length
0x14004a334  mov     rcx, rax; Base
0x14004a337  mov     qword ptr [rbp+0C0h+Length], r9
0x14004a33b  mov     [rbp+0C0h+VirtualAddress], rax
0x14004a33f  call    cs:__imp_MmSizeOfMdl
0x14004a346  nop     dword ptr [rax+rax+00h]
0x14004a34b  mov     edx, eax
0x14004a34d  mov     ecx, 42h ; 'B'
0x14004a352  mov     r8d, 4D506152h
0x14004a358  call    cs:__imp_ExAllocatePool2
0x14004a35f  nop     dword ptr [rax+rax+00h]
0x14004a364  mov     qword ptr [rbp+0C0h+var_48], rax
0x14004a368  mov     r10, rax
0x14004a36b  mov     [rbx], rax
0x14004a36e  test    rax, rax
0x14004a371  jz      loc_14004A661
0x14004a377  mov     r8, [rbp+0C0h+VirtualAddress]; VirtualAddress
0x14004a37b  mov     r11d, 0FFFh
0x14004a381  mov     r9, qword ptr [rbp+0C0h+Length]; Length
0x14004a385  mov     edx, r8d
0x14004a388  mov     qword ptr [rax], 0
0x14004a38f  mov     eax, edx
0x14004a391  and     rax, r11
0x14004a394  mov     [r10+28h], r9d
0x14004a398  and     edx, r11d
0x14004a39b  mov     [r10+2Ch], edx
0x14004a39f  lea     rcx, [r9+0FFFh]
0x14004a3a6  add     rcx, rax
0x14004a3a9  mov     rdx, r10; TargetMdl
0x14004a3ac  xor     eax, eax
0x14004a3ae  shr     rcx, 0Ch
0x14004a3b2  mov     [r10+0Ah], ax
0x14004a3b7  add     cx, 6
0x14004a3bb  shl     cx, 3
0x14004a3bf  mov     rax, r8
0x14004a3c2  and     rax, 0FFFFFFFFFFFFF000h
0x14004a3c8  mov     [r10+8], cx
0x14004a3cd  mov     [r10+20h], rax
0x14004a3d1  mov     rcx, [r14+8]; SourceMdl
0x14004a3d5  call    cs:__imp_IoBuildPartialMdl
0x14004a3dc  nop     dword ptr [rax+rax+00h]
0x14004a3e1  mov     rax, [r14+8]
0x14004a3e5  mov     rcx, [rbx]
0x14004a3e8  mov     r8, qword ptr [rbp+0C0h+var_48]
0x14004a3ec  mov     rax, [rax]
0x14004a3ef  mov     [rcx], rax
0x14004a3f2  mov     eax, [r14+18h]
0x14004a3f6  lea     rcx, RawSendMessagesDatagramsComplete
0x14004a3fd  mov     byte ptr [rsp+1D0h+var_1A8], 0
0x14004a402  xor     r9d, r9d
0x14004a405  mov     rdx, rbx
0x14004a408  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14004a40c  call    cs:__imp_NetioAllocateAndReferenceNetBufferAndNetBufferList
0x14004a413  nop     dword ptr [rax+rax+00h]
0x14004a418  mov     [rbp+0C0h+VirtualAddress], rax
0x14004a41c  test    rax, rax
0x14004a41f  jz      loc_14004A628
0x14004a425  mov     [rbx+8], r15
0x14004a429  mov     rcx, [r14+18h]
0x14004a42d  add     [r15+20h], rcx
0x14004a431  lock inc dword ptr [r15+18h]
0x14004a436  inc     [rbp+0C0h+var_13C]
0x14004a439  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+2, 0
0x14004a440  jge     loc_14004A52C
0x14004a446  mov     cl, 2; NewIrql
0x14004a448  call    cs:__imp_KfRaiseIrql
0x14004a44f  nop     dword ptr [rax+rax+00h]
0x14004a454  mov     rcx, [r13+38h]
0x14004a458  xor     r9d, r9d
0x14004a45b  mov     r8, [r13+70h]
0x14004a45f  cmp     rcx, rdi
0x14004a462  mov     [rbp+0C0h+NewIrql], al
0x14004a465  setnz   dl
0x14004a468  call    InetFormatLocalSockAddrAtDispatchLevel
0x14004a46d  mov     r10, [r13+38h]
0x14004a471  xor     r8d, r8d
0x14004a474  mov     ecx, [rsi+8]
0x14004a477  cmp     r10, rdi
0x14004a47a  mov     r9, [rsi+10h]
0x14004a47e  mov     rbx, rax
0x14004a481  mov     word ptr [rsp+1D0h+var_1A8], r8w
0x14004a487  setnz   dl
0x14004a48a  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x14004a48e  mov     r8d, 1
0x14004a494  movzx   ecx, word ptr [r10+18h]
0x14004a499  call    InetFormatSockAddrAtDispatchLevel
0x14004a49e  cmp     cs:dword_1402201D4, 0
0x14004a4a5  mov     r9, rax
0x14004a4a8  jz      short loc_14004A519
0x14004a4aa  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+2, 0
0x14004a4b1  xorps   xmm0, xmm0
0x14004a4b4  movups  [rbp+0C0h+var_48], xmm0
0x14004a4b8  jge     short loc_14004A519
0x14004a4ba  movzx   ecx, word ptr [rax]; af
0x14004a4bd  mov     qword ptr [rbp+0C0h+var_48], r13
0x14004a4c1  call    SOCKADDR_SIZE
0x14004a4c6  movzx   ecx, word ptr [rbx]; af
0x14004a4c9  movzx   r8d, al
0x14004a4cd  call    SOCKADDR_SIZE
0x14004a4d2  mov     [rsp+1D0h+var_180], r9
0x14004a4d7  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14004a4de  mov     dword ptr [rsp+1D0h+var_188], r8d
  ... truncated ...
```
