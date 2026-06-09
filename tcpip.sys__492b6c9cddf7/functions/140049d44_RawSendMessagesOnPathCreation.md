# RawSendMessagesOnPathCreation

- ea: `0x140049d44`
- end: `0x14004a51f`
- name: `RawSendMessagesOnPathCreation`
- size: `2011`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004ae6c`

## callees

- `0x140013140`
- `0x1400143c0`
- `0x14002f200`
- `0x140030380`
- `0x140039860`
- `0x14003b680`
- `0x140049d44`
- `0x1400525d0`
- `0x140053d70`
- `0x1400585d0`
- `0x14005e680`
- `0x1400830bc`
- `0x1400956b0`
- `0x1400b8080`
- `0x1400b8130`
- `0x1400c3660`
- `0x140106780`
- `0x1401137fc`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14004a1a8`
- `ntoskrnl!KfRaiseIrql` at `0x14004a3dd`
- `ntoskrnl!KfRaiseIrql` at `0x14004a1a8`
- `ntoskrnl!KfRaiseIrql` at `0x14004a3dd`
- `ntoskrnl!KeLowerIrql` at `0x14004a27c`
- `ntoskrnl!KeLowerIrql` at `0x14004a409`
- `ntoskrnl!KeLowerIrql` at `0x14004a27c`
- `ntoskrnl!KeLowerIrql` at `0x14004a409`
- `ntoskrnl!MmSizeOfMdl` at `0x14004a09f`
- `ntoskrnl!MmSizeOfMdl` at `0x14004a09f`
- `ntoskrnl!MmUnmapLockedPages` at `0x14004a39d`
- `ntoskrnl!MmUnmapLockedPages` at `0x14004a39d`
- `ntoskrnl!IoBuildPartialMdl` at `0x14004a135`
- `ntoskrnl!IoBuildPartialMdl` at `0x14004a135`
- `ntoskrnl!PsGetProcessStartKey` at `0x140049ee4`
- `ntoskrnl!PsGetProcessStartKey` at `0x140049ee4`
- `ntoskrnl!PsGetProcessId` at `0x140049ea5`
- `ntoskrnl!PsGetProcessId` at `0x140049ea5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004a459`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004a459`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a3ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a3ae`
- `ntoskrnl!ExAllocatePool2` at `0x14004a0b8`
- `ntoskrnl!ExAllocatePool2` at `0x14004a0b8`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140049dd8`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140049dd8`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14004a16c`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x14004a16c`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14004a2fe`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14004a2fe`

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
                      (unsigned int)RAW_ENDPOINT_SEND_MESSAGES,
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
              if ( TcpipNblTrackerEnabled )
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
0x140049d44  mov     [rsp-8+arg_10], rbx
0x140049d49  push    rbp
0x140049d4a  push    rsi
0x140049d4b  push    rdi
0x140049d4c  push    r12
0x140049d4e  push    r13
0x140049d50  push    r14
0x140049d52  push    r15
0x140049d54  lea     rbp, [rsp-90h]
0x140049d5c  sub     rsp, 1A0h
0x140049d63  mov     rax, cs:__security_cookie
0x140049d6a  xor     rax, rsp
0x140049d6d  mov     [rbp+0C0h+var_38], rax
0x140049d74  mov     rax, [rbp+0C0h+arg_28]
0x140049d7b  xor     r15d, r15d
0x140049d7e  mov     rsi, [rbp+0C0h+arg_20]
0x140049d85  mov     rdi, r9
0x140049d88  mov     r14, [rbp+0C0h+arg_48]
0x140049d8f  mov     bl, r8b
0x140049d92  mov     [rbp+0C0h+var_100], rax
0x140049d96  mov     r13, rdx
0x140049d99  mov     rax, [rbp+0C0h+arg_30]
0x140049da0  mov     r12d, ecx
0x140049da3  mov     [rbp+0C0h+LockHandle.LockQueue.Next], rax
0x140049da7  mov     rax, [rbp+0C0h+arg_40]
0x140049dae  mov     [rbp+0C0h+var_130], rax
0x140049db2  mov     rax, [rbp+0C0h+arg_50]
0x140049db9  mov     [rbp+0C0h+var_110], rax
0x140049dbd  mov     rax, [rbp+0C0h+arg_58]
0x140049dc4  mov     [rbp+0C0h+var_118], rax
0x140049dc8  mov     [rbp+0C0h+var_128], r9
0x140049dcc  mov     [rbp+0C0h+var_120], rsi
0x140049dd0  test    ecx, ecx
0x140049dd2  js      loc_14004A415
0x140049dd8  call    cs:__imp_NetioNcmFastCheckIsAoAcCapable
0x140049ddf  nop     dword ptr [rax+rax+00h]
0x140049de4  test    al, al
0x140049de6  jz      loc_140049F3E
0x140049dec  test    rsi, rsi
0x140049def  jz      loc_140049F3E
0x140049df5  mov     rax, [rsi]
0x140049df8  mov     rcx, [rax+8]
0x140049dfc  cmp     [rcx+58h], r15b
0x140049e00  jz      loc_140049F3E
0x140049e06  mov     eax, gs:1A4h
0x140049e0e  mov     r12d, 0C00000BEh
0x140049e14  lea     rdx, [rax+rax*4]
0x140049e18  mov     rax, cs:TcpipGlobalCounters
0x140049e1f  shl     rdx, 6
0x140049e23  inc     qword ptr [rdx+rax+50h]
0x140049e28  cmp     byte ptr cs:WPP_MAIN_CB+148h, r15b
0x140049e2f  jge     loc_14004A41A
0x140049e35  mov     rcx, [r13+38h]
0x140049e39  xor     r9d, r9d
0x140049e3c  mov     r8, [r13+70h]
0x140049e40  cmp     rcx, rdi
0x140049e43  setnz   dl
0x140049e46  call    InetFormatLocalSockAddrAtDispatchLevel
0x140049e4b  mov     r10, [r13+38h]
0x140049e4f  lea     r8d, [r15+1]
0x140049e53  mov     r9, [rsi+10h]
0x140049e57  xor     ecx, ecx
0x140049e59  mov     word ptr [rsp+1D0h+var_1A8], cx
0x140049e5e  cmp     r10, rdi
0x140049e61  mov     rbx, rax
0x140049e64  mov     [rbp+0C0h+var_130], rax
0x140049e68  mov     eax, [rsi+8]
0x140049e6b  setnz   dl
0x140049e6e  movzx   ecx, word ptr [r10+18h]
0x140049e73  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x140049e77  call    InetFormatSockAddrAtDispatchLevel
0x140049e7c  cmp     cs:dword_1402201D4, r15d
0x140049e83  mov     [rbp+0C0h+VirtualAddress], rax
0x140049e87  jz      loc_14004A41A
0x140049e8d  cmp     byte ptr cs:WPP_MAIN_CB+148h, r15b
0x140049e94  xorps   xmm0, xmm0
0x140049e97  movups  xmmword ptr [rbp+0C0h+LockHandle.LockQueue.Next], xmm0
0x140049e9b  jge     loc_14004A41A
0x140049ea1  mov     rcx, [r13+48h]; Process
0x140049ea5  call    cs:__imp_PsGetProcessId
0x140049eac  nop     dword ptr [rax+rax+00h]
0x140049eb1  mov     rcx, [rsi]
0x140049eb4  mov     r14, rax
0x140049eb7  mov     [rbp+0C0h+LockHandle.LockQueue.Lock], r15
0x140049ebb  mov     [rbp+0C0h+LockHandle.LockQueue.Next], r13
0x140049ebf  mov     rdx, [rcx+8]
0x140049ec3  mov     rcx, [rbp+0C0h+VirtualAddress]
0x140049ec7  mov     edi, [rdx+8]
0x140049eca  movzx   ecx, word ptr [rcx]; af
0x140049ecd  call    SOCKADDR_SIZE
0x140049ed2  movzx   ecx, word ptr [rbx]; af
0x140049ed5  movzx   esi, al
0x140049ed8  call    SOCKADDR_SIZE
0x140049edd  mov     rcx, [r13+48h]
0x140049ee1  movzx   ebx, al
0x140049ee4  call    cs:__imp_PsGetProcessStartKey
0x140049eeb  nop     dword ptr [rax+rax+00h]
0x140049ef0  mov     [rsp+1D0h+var_170], rax
0x140049ef5  lea     r9d, [r15+3]
0x140049ef9  mov     rax, [rbp+0C0h+VirtualAddress]
0x140049efd  lea     r8, [rbp+0C0h+LockHandle]
0x140049f01  mov     [rsp+1D0h+var_178], edi
0x140049f05  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140049f0c  mov     dword ptr [rsp+1D0h+var_180], r14d
0x140049f11  mov     [rsp+1D0h+var_190], rax
0x140049f16  mov     rax, [rbp+0C0h+var_130]
0x140049f1a  mov     [rsp+1D0h+var_198], esi
0x140049f1e  mov     [rsp+1D0h+var_1A0], rax
0x140049f23  mov     dword ptr [rsp+1D0h+var_1A8], ebx
0x140049f27  mov     [rsp+1D0h+var_1B0], r13
0x140049f2c  call    McTemplateK0qpqbr2qbr4qqqx_EtwWriteTransfer
0x140049f31  mov     rdi, [rbp+0C0h+var_128]
0x140049f35  mov     rsi, [rbp+0C0h+var_120]
0x140049f39  jmp     loc_14004A41A
0x140049f3e  test    bl, bl
0x140049f40  jnz     short loc_140049FB4
0x140049f42  mov     eax, [r13+18h]
0x140049f46  test    al, 20h
0x140049f48  jnz     short loc_140049FB4
0x140049f4a  xor     edx, edx; Val
0x140049f4c  lea     rcx, [rbp+0C0h+var_F0]; void *
0x140049f50  mov     r8d, 88h; Size
0x140049f56  call    memset
0x140049f5b  mov     r8, [rbp+0C0h+var_130]
0x140049f5f  lea     r9, [rbp+0C0h+var_F0]
0x140049f63  mov     rdx, rsi
0x140049f66  mov     [rsp+1D0h+var_1B0], r15
0x140049f6b  mov     rcx, rdi
0x140049f6e  call    InetQueryPathInfoAf
0x140049f73  mov     r12d, eax
0x140049f76  test    eax, eax
0x140049f78  js      loc_14004A415
0x140049f7e  mov     rcx, [rbp+0C0h+var_80]
0x140049f82  test    rcx, rcx
0x140049f85  jnz     short loc_140049F8F
0x140049f87  mov     r12d, 0C000023Dh
0x140049f8d  jmp     short loc_140049FA0
0x140049f8f  call    NlppNextHopAddressType
0x140049f94  cmp     eax, 4
0x140049f97  mov     edx, 0C0000022h
0x140049f9c  cmovz   r12d, edx
0x140049fa0  mov     rdx, rcx
0x140049fa3  mov     rcx, rdi
0x140049fa6  call    InetDereferenceNextHopAf
0x140049fab  test    r12d, r12d
0x140049fae  js      loc_14004A415
0x140049fb4  mov     rcx, cs:RawSendMessageListPool
0x140049fbb  call    PplAllocateFromLookasideList
0x140049fc0  mov     r15, rax
0x140049fc3  test    rax, rax
0x140049fc6  jnz     short loc_140049FD3
0x140049fc8  mov     r12d, 0C0000017h
0x140049fce  jmp     loc_14004A415
0x140049fd3  mov     dword ptr [rax+18h], 1
0x140049fda  mov     r12d, 103h
0x140049fe0  mov     [rax+10h], r13
0x140049fe4  mov     ecx, 2
0x140049fe9  mov     qword ptr [rax+20h], 0
0x140049ff1  mov     rax, [rbp+0C0h+var_118]
0x140049ff5  mov     [r15+8], rax
0x140049ff9  mov     rax, [rbp+0C0h+var_110]
0x140049ffd  mov     [r15], rax
0x14004a000  mov     [rbp+0C0h+var_13C], 0
0x14004a007  mov     dword ptr [r15+28h], 0
0x14004a00f  test    r14, r14
0x14004a012  jz      loc_14004A3DD
0x14004a018  mov     rcx, cs:RawSendMessagesPool
0x14004a01f  call    PplAllocateFromLookasideList
0x14004a024  mov     rbx, rax
0x14004a027  test    rax, rax
0x14004a02a  jz      loc_14004A3D0
0x14004a030  cmp     word ptr [rdi+18h], 17h
0x14004a035  mov     eax, 0FFFFh
0x14004a03a  mov     rcx, [r14+18h]
0x14004a03e  lea     edx, [rax-14h]
0x14004a041  cmovnz  eax, edx
0x14004a044  cmp     rcx, rax
0x14004a047  ja      loc_14004A4A4
0x14004a04d  test    rcx, rcx
0x14004a050  jnz     short loc_14004A05D
0x14004a052  xor     r8d, r8d
0x14004a055  mov     [rbx], r8
0x14004a058  jmp     loc_14004A152
0x14004a05d  mov     edx, [r14+10h]
0x14004a061  mov     r8, [r14+8]
0x14004a065  test    edx, edx
0x14004a067  jnz     short loc_14004A075
0x14004a069  mov     qword ptr [rbx], 0
0x14004a070  jmp     loc_14004A152
0x14004a075  mov     ecx, [r14+18h]
0x14004a079  mov     eax, [r8+28h]
0x14004a07d  sub     eax, edx
0x14004a07f  cmp     ecx, eax
0x14004a081  cmovnb  ecx, eax
0x14004a084  mov     eax, [r8+2Ch]
0x14004a088  add     rax, [r8+20h]
0x14004a08c  add     rax, rdx
0x14004a08f  mov     r9d, ecx
0x14004a092  mov     edx, ecx; Length
0x14004a094  mov     rcx, rax; Base
0x14004a097  mov     qword ptr [rbp+0C0h+Length], r9
0x14004a09b  mov     [rbp+0C0h+VirtualAddress], rax
0x14004a09f  call    cs:__imp_MmSizeOfMdl
0x14004a0a6  nop     dword ptr [rax+rax+00h]
0x14004a0ab  mov     edx, eax
0x14004a0ad  mov     ecx, 42h ; 'B'
0x14004a0b2  mov     r8d, 4D506152h
0x14004a0b8  call    cs:__imp_ExAllocatePool2
0x14004a0bf  nop     dword ptr [rax+rax+00h]
0x14004a0c4  mov     qword ptr [rbp+0C0h+var_48], rax
0x14004a0c8  mov     r10, rax
0x14004a0cb  mov     [rbx], rax
0x14004a0ce  test    rax, rax
0x14004a0d1  jz      loc_14004A3C1
0x14004a0d7  mov     r8, [rbp+0C0h+VirtualAddress]; VirtualAddress
0x14004a0db  mov     r11d, 0FFFh
0x14004a0e1  mov     r9, qword ptr [rbp+0C0h+Length]; Length
0x14004a0e5  mov     edx, r8d
0x14004a0e8  mov     qword ptr [rax], 0
0x14004a0ef  mov     eax, edx
0x14004a0f1  and     rax, r11
0x14004a0f4  mov     [r10+28h], r9d
0x14004a0f8  and     edx, r11d
0x14004a0fb  mov     [r10+2Ch], edx
0x14004a0ff  lea     rcx, [r9+0FFFh]
0x14004a106  add     rcx, rax
0x14004a109  mov     rdx, r10; TargetMdl
0x14004a10c  xor     eax, eax
0x14004a10e  shr     rcx, 0Ch
0x14004a112  mov     [r10+0Ah], ax
0x14004a117  add     cx, 6
0x14004a11b  shl     cx, 3
0x14004a11f  mov     rax, r8
0x14004a122  and     rax, 0FFFFFFFFFFFFF000h
0x14004a128  mov     [r10+8], cx
0x14004a12d  mov     [r10+20h], rax
0x14004a131  mov     rcx, [r14+8]; SourceMdl
0x14004a135  call    cs:__imp_IoBuildPartialMdl
0x14004a13c  nop     dword ptr [rax+rax+00h]
0x14004a141  mov     rax, [r14+8]
0x14004a145  mov     rcx, [rbx]
0x14004a148  mov     r8, qword ptr [rbp+0C0h+var_48]
0x14004a14c  mov     rax, [rax]
0x14004a14f  mov     [rcx], rax
0x14004a152  mov     eax, [r14+18h]
0x14004a156  lea     rcx, RawSendMessagesDatagramsComplete
0x14004a15d  mov     byte ptr [rsp+1D0h+var_1A8], 0
0x14004a162  xor     r9d, r9d
0x14004a165  mov     rdx, rbx
0x14004a168  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14004a16c  call    cs:__imp_NetioAllocateAndReferenceNetBufferAndNetBufferList
0x14004a173  nop     dword ptr [rax+rax+00h]
0x14004a178  mov     [rbp+0C0h+VirtualAddress], rax
0x14004a17c  test    rax, rax
0x14004a17f  jz      loc_14004A388
0x14004a185  mov     [rbx+8], r15
0x14004a189  mov     rcx, [r14+18h]
0x14004a18d  add     [r15+20h], rcx
0x14004a191  lock inc dword ptr [r15+18h]
0x14004a196  inc     [rbp+0C0h+var_13C]
0x14004a199  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+2, 0
0x14004a1a0  jge     loc_14004A28C
0x14004a1a6  mov     cl, 2; NewIrql
0x14004a1a8  call    cs:__imp_KfRaiseIrql
0x14004a1af  nop     dword ptr [rax+rax+00h]
0x14004a1b4  mov     rcx, [r13+38h]
0x14004a1b8  xor     r9d, r9d
0x14004a1bb  mov     r8, [r13+70h]
0x14004a1bf  cmp     rcx, rdi
0x14004a1c2  mov     [rbp+0C0h+NewIrql], al
0x14004a1c5  setnz   dl
0x14004a1c8  call    InetFormatLocalSockAddrAtDispatchLevel
0x14004a1cd  mov     r10, [r13+38h]
0x14004a1d1  xor     r8d, r8d
0x14004a1d4  mov     ecx, [rsi+8]
0x14004a1d7  cmp     r10, rdi
0x14004a1da  mov     r9, [rsi+10h]
0x14004a1de  mov     rbx, rax
0x14004a1e1  mov     word ptr [rsp+1D0h+var_1A8], r8w
0x14004a1e7  setnz   dl
0x14004a1ea  mov     dword ptr [rsp+1D0h+var_1B0], ecx
0x14004a1ee  mov     r8d, 1
0x14004a1f4  movzx   ecx, word ptr [r10+18h]
0x14004a1f9  call    InetFormatSockAddrAtDispatchLevel
0x14004a1fe  cmp     cs:dword_1402201D4, 0
0x14004a205  mov     r9, rax
0x14004a208  jz      short loc_14004A279
0x14004a20a  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+2, 0
0x14004a211  xorps   xmm0, xmm0
0x14004a214  movups  [rbp+0C0h+var_48], xmm0
0x14004a218  jge     short loc_14004A279
0x14004a21a  movzx   ecx, word ptr [rax]; af
0x14004a21d  mov     qword ptr [rbp+0C0h+var_48], r13
0x14004a221  call    SOCKADDR_SIZE
0x14004a226  movzx   ecx, word ptr [rbx]; af
0x14004a229  movzx   r8d, al
0x14004a22d  call    SOCKADDR_SIZE
0x14004a232  mov     [rsp+1D0h+var_180], r9
0x14004a237  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14004a23e  mov     dword ptr [rsp+1D0h+var_188], r8d
  ... truncated ...
```
