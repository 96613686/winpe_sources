# LruCleanupDpcRoutine

- ea: `0x1400749b0`
- end: `0x140074de5`
- name: `LruCleanupDpcRoutine`
- size: `1077`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14002f200`
- `0x14002f230`
- `0x1400749b0`
- `0x140074df0`
- `0x140074f90`
- `0x140075068`
- `0x1400772e0`
- `0x140114a7c`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074a78`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074bfa`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074a78`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074bfa`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140074b61`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140074c3d`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140074b61`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140074c3d`
- `ntoskrnl!KeReadStateEvent` at `0x1401c60bf`
- `ntoskrnl!KeReadStateEvent` at `0x1401c60d4`
- `ntoskrnl!KeReadStateEvent` at `0x1401c60e9`
- `ntoskrnl!KeReadStateEvent` at `0x1401c60fe`
- `ntoskrnl!KeReadStateEvent` at `0x1401c60bf`
- `ntoskrnl!KeReadStateEvent` at `0x1401c60d4`
- `ntoskrnl!KeReadStateEvent` at `0x1401c60e9`
- `ntoskrnl!KeReadStateEvent` at `0x1401c60fe`
- `ntoskrnl!KeInsertQueueDpc` at `0x1401c613f`
- `ntoskrnl!KeInsertQueueDpc` at `0x1401c613f`
- `NDIS!NdisReleaseRWLock` at `0x140074aaa`
- `NDIS!NdisReleaseRWLock` at `0x140074c2c`
- `NDIS!NdisReleaseRWLock` at `0x140074aaa`
- `NDIS!NdisReleaseRWLock` at `0x140074c2c`

## pseudocode

```c
void __fastcall LruCleanupDpcRoutine(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  int v4; // eax
  unsigned int v5; // esi
  __int16 v6; // r15
  unsigned int v7; // ebp
  unsigned __int64 v8; // r12
  unsigned int v9; // eax
  __int64 v10; // rbx
  unsigned __int64 v11; // r13
  _QWORD **v12; // rdi
  _QWORD *v13; // rcx
  _DWORD *v14; // rcx
  _QWORD *v15; // rbp
  signed __int64 v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rbx
  _DWORD *v19; // rdx
  _QWORD *v20; // rax
  UCHAR v21; // al
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // r8d
  char StateEvent; // si
  char v26; // di
  char v27; // bl
  LONG v28; // eax
  __int64 v29; // [rsp+48h] [rbp-170h]
  __int64 LockState; // [rsp+50h] [rbp-168h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-160h]
  struct _KDPC_WATCHDOG_INFORMATION WatchdogInformation; // [rsp+60h] [rbp-158h] BYREF
  _BYTE v33[128]; // [rsp+80h] [rbp-138h] BYREF
  _BYTE v34[128]; // [rsp+100h] [rbp-B8h] BYREF

  v4 = 0;
  LOWORD(LockState) = 0;
  v5 = (unsigned int)SystemArgument2;
  BYTE2(LockState) = 0;
  v6 = (__int16)SystemArgument1;
  memset(&WatchdogInformation, 0, sizeof(WatchdogInformation));
  if ( (_WORD)SystemArgument1 )
  {
    v7 = (_DWORD)SystemArgument2 + 1;
  }
  else
  {
    if ( *(_DWORD *)(pRemoteEndpointTable + 12) < *(_DWORD *)pRemoteEndpointTable )
      v4 = *(_DWORD *)(pRemoteEndpointTable + 12);
    *(_DWORD *)(pRemoteEndpointTable + 12) = v4;
    v5 = *(_DWORD *)(pRemoteEndpointTable + 12);
    v7 = *(_DWORD *)pRemoteEndpointTable;
  }
  HIDWORD(LockState) = v7;
  v8 = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
  while ( 1 )
  {
    if ( v5 >= v7 )
    {
LABEL_11:
      if ( v6 )
        return;
      goto LABEL_12;
    }
    v9 = WfpAleGetAndWriteLockPartition(v5, &LockState);
    v10 = pRemoteEndpointTable;
    v11 = (unsigned __int64)v9 << 7;
    v31 = v9;
    v12 = (_QWORD **)(v11 + pRemoteEndpointTable + 112);
    v13 = *v12;
    if ( *v12 != v12 )
      break;
    if ( gWfpPerProContext )
    {
      v14 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
      if ( *v14 == 4 )
        *v14 = 0;
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v10 + v11 + 64), (PLOCK_STATE_EX)&LockState);
LABEL_10:
    ++v5;
  }
  do
  {
    v15 = v13 - 1;
    v16 = _InterlockedExchangeAdd64(v13 + 4, 0);
    v17 = *v13;
    if ( (unsigned int)((v8 - v16) / 0x3E8) >= *((_DWORD *)v13 + 5)
                                             / (unsigned int)*((unsigned __int16 *)&LifetimeFactor
                                                             + CurrentLifeTimeThresholdIndex) )
    {
      if ( *(_QWORD **)(v17 + 8) != v13 || (v20 = (_QWORD *)v13[1], (_QWORD *)*v20 != v13) )
        __fastfail(3u);
      *v20 = v17;
      *(_QWORD *)(v17 + 8) = v20;
      if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 1) != 0 )
      {
        memset(v34, 0, sizeof(v34));
        memset(v33, 0, sizeof(v33));
        ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
          *((unsigned __int16 *)v15 - 222),
          (unsigned int)v34,
          *(v15 - 3),
          scopeid_unspecified.0,
          *((_WORD *)v15 - 221));
        ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
          *((unsigned __int16 *)v15 - 222),
          (unsigned int)v33,
          *(v15 - 59),
          scopeid_unspecified.0,
          *((_WORD *)v15 - 220));
        if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 1) != 0 )
        {
          v21 = SOCKADDR_SIZE(*((_WORD *)v15 - 222));
          LOWORD(v29) = *((_WORD *)&LifetimeFactor + v22);
          McTemplateK0qbr0br0xxqh_EtwWriteTransfer(
            v23,
            v22,
            v24,
            v21,
            (__int64)v34,
            (__int64)v33,
            v8,
            v16,
            *((_DWORD *)v15 + 7),
            v29,
            LockState);
        }
      }
      WfpAleDeleteRemoteEndpointLru(v15);
    }
    KeQueryDpcWatchdogInformation(&WatchdogInformation);
    if ( WatchdogInformation.DpcTimeLimit
      && WatchdogInformation.DpcTimeCount < 25 * WatchdogInformation.DpcTimeLimit / 0x64 )
    {
      break;
    }
    v13 = (_QWORD *)v17;
  }
  while ( (_QWORD **)v17 != v12 );
  *(_QWORD *)(pRemoteEndpointTable + v11 + 128) = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
  RtlRestructureHashTable((PRTL_DYNAMIC_HASH_TABLE)(v11 + pRemoteEndpointTable + 72), 0);
  v18 = pRemoteEndpointTable;
  if ( gWfpPerProContext )
  {
    v19 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v19 == 4 )
      *v19 = 0;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v18 + v11 + 64), (PLOCK_STATE_EX)&LockState);
  KeQueryDpcWatchdogInformation(&WatchdogInformation);
  if ( WatchdogInformation.DpcWatchdogLimit
    && WatchdogInformation.DpcWatchdogCount < 25 * WatchdogInformation.DpcWatchdogLimit / 0x64 )
  {
    goto LABEL_11;
  }
  if ( !WatchdogInformation.DpcTimeLimit
    || WatchdogInformation.DpcTimeCount >= 25 * WatchdogInformation.DpcTimeLimit / 0x64 )
  {
    v7 = HIDWORD(LockState);
    goto LABEL_10;
  }
  if ( v6 )
    return;
  if ( v31 >= HIDWORD(LockState) )
  {
LABEL_12:
    *(_DWORD *)(pRemoteEndpointTable + 12) = v5 + 1;
    return;
  }
  *(_DWORD *)(pRemoteEndpointTable + 12) = v5 + 1;
  if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 8) != 0 )
  {
    StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
    v26 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
    v27 = KeReadStateEvent(HighNonPagedPoolEvent);
    v28 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredContext);
    McTemplateK0qqqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
      (unsigned int)DPC_CLEANUP,
      (unsigned int)MICROSOFT_TCPIP_PROVIDER,
      v28,
      v27,
      v26,
      StateEvent);
  }
  KeInsertQueueDpc(&LruCleanupDpc, 0, 0);
}

```

## disassembly

```asm
0x1400749b0  mov     [rsp+arg_8], rbx
0x1400749b5  mov     [rsp+arg_10], rbp
0x1400749ba  push    rsi
0x1400749bb  push    rdi
0x1400749bc  push    r12
0x1400749be  push    r14
0x1400749c0  push    r15
0x1400749c2  sub     rsp, 190h
0x1400749c9  mov     rax, cs:__security_cookie
0x1400749d0  xor     rax, rsp
0x1400749d3  mov     [rsp+1B8h+var_38], rax
0x1400749db  xor     eax, eax
0x1400749dd  xorps   xmm0, xmm0
0x1400749e0  mov     word ptr [rsp+1B8h+LockState.OldIrql], ax
0x1400749e5  mov     rsi, r9
0x1400749e8  mov     [rsp+1B8h+LockState.Flags], al
0x1400749ec  mov     r15, r8
0x1400749ef  mov     [rsp+1B8h+WatchdogInformation.Reserved], eax
0x1400749f3  movups  xmmword ptr [rsp+1B8h+WatchdogInformation.DpcTimeLimit], xmm0
0x1400749f8  test    r8w, r8w
0x1400749fc  jz      loc_140074CB0
0x140074a02  lea     ebp, [r9+1]
0x140074a06  mov     rax, 0FFFFF78000000008h
0x140074a10  mov     [rsp+1B8h+var_164], ebp
0x140074a14  mov     [rsp+1B8h+arg_0], r13
0x140074a1c  mov     rcx, [rax]
0x140074a1f  mov     rax, 346DC5D63886594Bh
0x140074a29  mul     rcx
0x140074a2c  mov     r12, rdx
0x140074a2f  shr     r12, 0Bh
0x140074a33  cmp     esi, ebp
0x140074a35  jnb     loc_140074ABD
0x140074a3b  mov     ecx, esi
0x140074a3d  lea     rdx, [rsp+1B8h+LockState]
0x140074a42  call    WfpAleGetAndWriteLockPartition
0x140074a47  mov     rbx, cs:pRemoteEndpointTable
0x140074a4e  mov     r13d, eax
0x140074a51  shl     r13, 7
0x140074a55  mov     [rsp+1B8h+var_160], eax
0x140074a59  lea     rdi, [rbx+70h]
0x140074a5d  add     rdi, r13
0x140074a60  mov     rcx, [rdi]
0x140074a63  cmp     rcx, rdi
0x140074a66  jnz     loc_140074B05
0x140074a6c  cmp     cs:gWfpPerProContext, 0
0x140074a74  jz      short loc_140074AA0
0x140074a76  xor     ecx, ecx; ProcNumber
0x140074a78  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140074a7f  nop     dword ptr [rax+rax+00h]
0x140074a84  lea     ecx, [rax+rax*8]
0x140074a87  mov     rax, cs:gWfpPerProContext
0x140074a8e  shl     ecx, 3
0x140074a91  mov     rcx, [rcx+rax]
0x140074a95  cmp     dword ptr [rcx], 4
0x140074a98  jnz     short loc_140074AA0
0x140074a9a  mov     dword ptr [rcx], 0
0x140074aa0  mov     rcx, [rbx+r13+40h]; Lock
0x140074aa5  lea     rdx, [rsp+1B8h+LockState]; LockState
0x140074aaa  call    cs:__imp_NdisReleaseRWLock
0x140074ab1  nop     dword ptr [rax+rax+00h]
0x140074ab6  inc     esi
0x140074ab8  jmp     loc_140074A33
0x140074abd  test    r15w, r15w
0x140074ac1  jnz     short loc_140074AD0
0x140074ac3  mov     rax, cs:pRemoteEndpointTable
0x140074aca  lea     ecx, [rsi+1]
0x140074acd  mov     [rax+0Ch], ecx
0x140074ad0  mov     r13, [rsp+1B8h+arg_0]
0x140074ad8  mov     rcx, [rsp+1B8h+var_38]
0x140074ae0  xor     rcx, rsp; StackCookie
0x140074ae3  call    __security_check_cookie
0x140074ae8  lea     r11, [rsp+1B8h+var_28]
0x140074af0  mov     rbx, [r11+38h]
0x140074af4  mov     rbp, [r11+40h]
0x140074af8  mov     rsp, r11
0x140074afb  pop     r15
0x140074afd  pop     r14
0x140074aff  pop     r12
0x140074b01  pop     rdi
0x140074b02  pop     rsi
0x140074b03  retn
0x140074b05  lea     rbp, [rcx-8]
0x140074b09  xor     r14d, r14d
0x140074b0c  lock xadd [rbp+28h], r14
0x140074b12  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x140074b19  lea     rdx, LifetimeFactor
0x140074b20  mov     rbx, [rcx]
0x140074b23  movzx   r8d, word ptr [rdx+rax*2]
0x140074b28  xor     edx, edx
0x140074b2a  mov     eax, [rbp+1Ch]
0x140074b2d  div     r8d
0x140074b30  mov     r8, r12
0x140074b33  sub     r8, r14
0x140074b36  mov     r9d, eax
0x140074b39  mov     rax, 624DD2F1A9FBE77h
0x140074b43  mul     r8
0x140074b46  sub     r8, rdx
0x140074b49  shr     r8, 1
0x140074b4c  add     r8, rdx
0x140074b4f  shr     r8, 9
0x140074b53  cmp     r8d, r9d
0x140074b56  jnb     loc_140074C9A
0x140074b5c  lea     rcx, [rsp+1B8h+WatchdogInformation]; WatchdogInformation
0x140074b61  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140074b68  nop     dword ptr [rax+rax+00h]
0x140074b6d  mov     eax, [rsp+1B8h+WatchdogInformation.DpcTimeLimit]
0x140074b71  test    eax, eax
0x140074b73  jz      short loc_140074B88
0x140074b75  imul    ecx, eax, 19h
0x140074b78  mov     eax, 51EB851Fh
0x140074b7d  mul     ecx
0x140074b7f  shr     edx, 5
0x140074b82  cmp     [rsp+1B8h+WatchdogInformation.DpcTimeCount], edx
0x140074b86  jb      short loc_140074B94
0x140074b88  mov     rcx, rbx
0x140074b8b  cmp     rbx, rdi
0x140074b8e  jnz     loc_140074B05
0x140074b94  mov     rax, 0FFFFF78000000008h
0x140074b9e  mov     [rsp+1B8h+var_198], 0; int
0x140074ba6  mov     r8d, 19h
0x140074bac  mov     rcx, [rax]
0x140074baf  mov     rax, 346DC5D63886594Bh
0x140074bb9  mul     rcx
0x140074bbc  mov     rax, cs:pRemoteEndpointTable
0x140074bc3  shr     rdx, 0Bh
0x140074bc7  mov     [rax+r13+80h], rdx
0x140074bcf  mov     edx, 258h
0x140074bd4  mov     rcx, cs:pRemoteEndpointTable
0x140074bdb  add     rcx, 48h ; 'H'
0x140074bdf  add     rcx, r13; HashTable
0x140074be2  call    RtlRestructureHashTable
0x140074be7  cmp     cs:gWfpPerProContext, 0
0x140074bef  mov     rbx, cs:pRemoteEndpointTable
0x140074bf6  jz      short loc_140074C22
0x140074bf8  xor     ecx, ecx; ProcNumber
0x140074bfa  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140074c01  nop     dword ptr [rax+rax+00h]
0x140074c06  lea     edx, [rax+rax*8]
0x140074c09  mov     rax, cs:gWfpPerProContext
0x140074c10  shl     edx, 3
0x140074c13  mov     rdx, [rdx+rax]
0x140074c17  cmp     dword ptr [rdx], 4
0x140074c1a  jnz     short loc_140074C22
0x140074c1c  mov     dword ptr [rdx], 0
0x140074c22  mov     rcx, [rbx+r13+40h]; Lock
0x140074c27  lea     rdx, [rsp+1B8h+LockState]; LockState
0x140074c2c  call    cs:__imp_NdisReleaseRWLock
0x140074c33  nop     dword ptr [rax+rax+00h]
0x140074c38  lea     rcx, [rsp+1B8h+WatchdogInformation]; WatchdogInformation
0x140074c3d  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140074c44  nop     dword ptr [rax+rax+00h]
0x140074c49  mov     eax, [rsp+1B8h+WatchdogInformation.DpcWatchdogLimit]
0x140074c4d  test    eax, eax
0x140074c4f  jz      short loc_140074C68
0x140074c51  imul    ecx, eax, 19h
0x140074c54  mov     eax, 51EB851Fh
0x140074c59  mul     ecx
0x140074c5b  shr     edx, 5
0x140074c5e  cmp     [rsp+1B8h+WatchdogInformation.DpcWatchdogCount], edx
0x140074c62  jb      loc_140074ABD
0x140074c68  mov     eax, [rsp+1B8h+WatchdogInformation.DpcTimeLimit]
0x140074c6c  test    eax, eax
0x140074c6e  jz      loc_140074DDC
0x140074c74  imul    ecx, eax, 19h
0x140074c77  mov     eax, 51EB851Fh
0x140074c7c  mul     ecx
0x140074c7e  shr     edx, 5
0x140074c81  cmp     [rsp+1B8h+WatchdogInformation.DpcTimeCount], edx
0x140074c85  jnb     loc_140074DDC
0x140074c8b  test    r15w, r15w
0x140074c8f  jnz     loc_140074AD0
0x140074c95  jmp     loc_1401C6094
0x140074c9a  cmp     [rbx+8], rcx
0x140074c9e  jnz     short loc_140074CA9
0x140074ca0  mov     rax, [rcx+8]
0x140074ca4  cmp     [rax], rcx
0x140074ca7  jz      short loc_140074CD3
0x140074ca9  mov     ecx, 3
0x140074cae  int     29h; Win8: RtlFailFast(ecx)
0x140074cb0  mov     rdx, cs:pRemoteEndpointTable
0x140074cb7  mov     ecx, [rdx+0Ch]
0x140074cba  cmp     ecx, [rdx]
0x140074cbc  cmovb   eax, ecx
0x140074cbf  mov     [rdx+0Ch], eax
0x140074cc2  mov     rax, cs:pRemoteEndpointTable
0x140074cc9  mov     esi, [rax+0Ch]
0x140074ccc  mov     ebp, [rax]
0x140074cce  jmp     loc_140074A06
0x140074cd3  mov     [rax], rbx
0x140074cd6  mov     [rbx+8], rax
0x140074cda  test    byte ptr cs:WPP_MAIN_CB+14Ah, 1
0x140074ce1  jnz     short loc_140074CF0
0x140074ce3  mov     rcx, rbp
0x140074ce6  call    WfpAleDeleteRemoteEndpointLru
0x140074ceb  jmp     loc_140074B5C
0x140074cf0  xor     edx, edx; Val
0x140074cf2  lea     rcx, [rsp+1B8h+var_B8]; void *
0x140074cfa  mov     r8d, 80h; Size
0x140074d00  call    memset
0x140074d05  xor     edx, edx; Val
0x140074d07  lea     rcx, [rsp+1B8h+var_138]; void *
0x140074d0f  mov     r8d, 80h; Size
0x140074d15  call    memset
0x140074d1a  movzx   eax, word ptr [rbp-1BAh]
0x140074d21  lea     rdx, [rsp+1B8h+var_B8]
0x140074d29  mov     r9d, dword ptr cs:scopeid_unspecified
0x140074d30  mov     r8, [rbp-18h]
0x140074d34  movzx   ecx, word ptr [rbp-1BCh]
0x140074d3b  mov     word ptr [rsp+1B8h+var_198], ax
0x140074d40  call    INETADDR_SETSOCKADDR
0x140074d45  movzx   edx, word ptr [rbp-1B8h]
0x140074d4c  mov     r9d, dword ptr cs:scopeid_unspecified
0x140074d53  mov     r8, [rbp-1D8h]
0x140074d5a  movzx   ecx, word ptr [rbp-1BCh]
0x140074d61  mov     word ptr [rsp+1B8h+var_198], dx
0x140074d66  lea     rdx, [rsp+1B8h+var_138]
0x140074d6e  call    INETADDR_SETSOCKADDR
0x140074d73  test    byte ptr cs:WPP_MAIN_CB+14Ah, 1
0x140074d7a  jz      loc_140074CE3
0x140074d80  movzx   ecx, word ptr [rbp-1BCh]; af
0x140074d87  movsxd  rdx, cs:CurrentLifeTimeThresholdIndex
0x140074d8e  call    SOCKADDR_SIZE
0x140074d93  movzx   r9d, al
0x140074d97  lea     rax, LifetimeFactor
0x140074d9e  movzx   eax, word ptr [rax+rdx*2]
0x140074da2  mov     word ptr [rsp+1B8h+var_170], ax
0x140074da7  mov     eax, [rbp+1Ch]
0x140074daa  mov     [rsp+1B8h+var_178], eax
0x140074dae  lea     rax, [rsp+1B8h+var_138]
0x140074db6  mov     [rsp+1B8h+var_180], r14
0x140074dbb  mov     [rsp+1B8h+var_188], r12
0x140074dc0  mov     [rsp+1B8h+var_190], rax
0x140074dc5  lea     rax, [rsp+1B8h+var_B8]
0x140074dcd  mov     qword ptr [rsp+1B8h+var_198], rax
0x140074dd2  call    McTemplateK0qbr0br0xxqh_EtwWriteTransfer
0x140074dd7  jmp     loc_140074CE3
0x140074ddc  mov     ebp, [rsp+1B8h+var_164]
0x140074de0  jmp     loc_140074AB6
0x1401c6094  mov     eax, [rsp+1B8h+var_160]
0x1401c6098  cmp     eax, [rsp+1B8h+var_164]
0x1401c609c  jnb     loc_140074AC3
0x1401c60a2  mov     rax, cs:pRemoteEndpointTable
0x1401c60a9  lea     ecx, [rsi+1]
0x1401c60ac  mov     [rax+0Ch], ecx
0x1401c60af  test    byte ptr cs:WPP_MAIN_CB+14Ah, 8
0x1401c60b6  jz      short loc_1401C6133
0x1401c60b8  mov     rcx, cs:LowNonPagedPoolEvent; Event
0x1401c60bf  call    cs:__imp_KeReadStateEvent
0x1401c60c6  nop     dword ptr [rax+rax+00h]
0x1401c60cb  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; Event
0x1401c60d2  mov     esi, eax
0x1401c60d4  call    cs:__imp_KeReadStateEvent
0x1401c60db  nop     dword ptr [rax+rax+00h]
0x1401c60e0  mov     rcx, cs:HighNonPagedPoolEvent; Event
0x1401c60e7  mov     edi, eax
0x1401c60e9  call    cs:__imp_KeReadStateEvent
0x1401c60f0  nop     dword ptr [rax+rax+00h]
0x1401c60f5  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; Event
0x1401c60fc  mov     ebx, eax
0x1401c60fe  call    cs:__imp_KeReadStateEvent
0x1401c6105  nop     dword ptr [rax+rax+00h]
0x1401c610a  mov     dword ptr [rsp+1B8h+var_188], esi
0x1401c610e  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401c6115  mov     r9d, eax
0x1401c6118  mov     dword ptr [rsp+1B8h+var_190], edi
0x1401c611c  lea     rdx, DPC_CLEANUP
0x1401c6123  mov     [rsp+1B8h+var_198], ebx
0x1401c6127  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c612e  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401c6133  xor     r8d, r8d; SystemArgument2
0x1401c6136  lea     rcx, LruCleanupDpc; Dpc
0x1401c613d  xor     edx, edx; SystemArgument1
0x1401c613f  call    cs:__imp_KeInsertQueueDpc
0x1401c6146  nop     dword ptr [rax+rax+00h]
0x1401c614b  nop
0x1401c614c  jmp     loc_140074AD0
```
