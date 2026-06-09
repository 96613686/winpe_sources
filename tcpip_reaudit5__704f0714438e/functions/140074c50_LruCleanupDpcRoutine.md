# LruCleanupDpcRoutine

- ea: `0x140074c50`
- end: `0x140075085`
- name: `LruCleanupDpcRoutine`
- size: `1077`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14002f4a0`
- `0x14002f4d0`
- `0x140074c50`
- `0x140075090`
- `0x140075230`
- `0x140075308`
- `0x140077580`
- `0x140114bbc`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074d18`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074e9a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074d18`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140074e9a`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140074e01`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140074edd`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140074e01`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x140074edd`
- `ntoskrnl!KeReadStateEvent` at `0x1401c61ff`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6214`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6229`
- `ntoskrnl!KeReadStateEvent` at `0x1401c623e`
- `ntoskrnl!KeReadStateEvent` at `0x1401c61ff`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6214`
- `ntoskrnl!KeReadStateEvent` at `0x1401c6229`
- `ntoskrnl!KeReadStateEvent` at `0x1401c623e`
- `ntoskrnl!KeInsertQueueDpc` at `0x1401c627f`
- `ntoskrnl!KeInsertQueueDpc` at `0x1401c627f`
- `NDIS!NdisReleaseRWLock` at `0x140074d4a`
- `NDIS!NdisReleaseRWLock` at `0x140074ecc`
- `NDIS!NdisReleaseRWLock` at `0x140074d4a`
- `NDIS!NdisReleaseRWLock` at `0x140074ecc`

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
    v26 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
    v27 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.DeviceType);
    v28 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredRoutine);
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
0x140074c50  mov     [rsp+arg_8], rbx
0x140074c55  mov     [rsp+arg_10], rbp
0x140074c5a  push    rsi
0x140074c5b  push    rdi
0x140074c5c  push    r12
0x140074c5e  push    r14
0x140074c60  push    r15
0x140074c62  sub     rsp, 190h
0x140074c69  mov     rax, cs:__security_cookie
0x140074c70  xor     rax, rsp
0x140074c73  mov     [rsp+1B8h+var_38], rax
0x140074c7b  xor     eax, eax
0x140074c7d  xorps   xmm0, xmm0
0x140074c80  mov     word ptr [rsp+1B8h+LockState.OldIrql], ax
0x140074c85  mov     rsi, r9
0x140074c88  mov     [rsp+1B8h+LockState.Flags], al
0x140074c8c  mov     r15, r8
0x140074c8f  mov     [rsp+1B8h+WatchdogInformation.Reserved], eax
0x140074c93  movups  xmmword ptr [rsp+1B8h+WatchdogInformation.DpcTimeLimit], xmm0
0x140074c98  test    r8w, r8w
0x140074c9c  jz      loc_140074F50
0x140074ca2  lea     ebp, [r9+1]
0x140074ca6  mov     rax, 0FFFFF78000000008h
0x140074cb0  mov     [rsp+1B8h+var_164], ebp
0x140074cb4  mov     [rsp+1B8h+arg_0], r13
0x140074cbc  mov     rcx, [rax]
0x140074cbf  mov     rax, 346DC5D63886594Bh
0x140074cc9  mul     rcx
0x140074ccc  mov     r12, rdx
0x140074ccf  shr     r12, 0Bh
0x140074cd3  cmp     esi, ebp
0x140074cd5  jnb     loc_140074D5D
0x140074cdb  mov     ecx, esi
0x140074cdd  lea     rdx, [rsp+1B8h+LockState]
0x140074ce2  call    WfpAleGetAndWriteLockPartition
0x140074ce7  mov     rbx, cs:pRemoteEndpointTable
0x140074cee  mov     r13d, eax
0x140074cf1  shl     r13, 7
0x140074cf5  mov     [rsp+1B8h+var_160], eax
0x140074cf9  lea     rdi, [rbx+70h]
0x140074cfd  add     rdi, r13
0x140074d00  mov     rcx, [rdi]
0x140074d03  cmp     rcx, rdi
0x140074d06  jnz     loc_140074DA5
0x140074d0c  cmp     cs:gWfpPerProContext, 0
0x140074d14  jz      short loc_140074D40
0x140074d16  xor     ecx, ecx; ProcNumber
0x140074d18  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140074d1f  nop     dword ptr [rax+rax+00h]
0x140074d24  lea     ecx, [rax+rax*8]
0x140074d27  mov     rax, cs:gWfpPerProContext
0x140074d2e  shl     ecx, 3
0x140074d31  mov     rcx, [rcx+rax]
0x140074d35  cmp     dword ptr [rcx], 4
0x140074d38  jnz     short loc_140074D40
0x140074d3a  mov     dword ptr [rcx], 0
0x140074d40  mov     rcx, [rbx+r13+40h]; Lock
0x140074d45  lea     rdx, [rsp+1B8h+LockState]; LockState
0x140074d4a  call    cs:__imp_NdisReleaseRWLock
0x140074d51  nop     dword ptr [rax+rax+00h]
0x140074d56  inc     esi
0x140074d58  jmp     loc_140074CD3
0x140074d5d  test    r15w, r15w
0x140074d61  jnz     short loc_140074D70
0x140074d63  mov     rax, cs:pRemoteEndpointTable
0x140074d6a  lea     ecx, [rsi+1]
0x140074d6d  mov     [rax+0Ch], ecx
0x140074d70  mov     r13, [rsp+1B8h+arg_0]
0x140074d78  mov     rcx, [rsp+1B8h+var_38]
0x140074d80  xor     rcx, rsp; StackCookie
0x140074d83  call    __security_check_cookie
0x140074d88  lea     r11, [rsp+1B8h+var_28]
0x140074d90  mov     rbx, [r11+38h]
0x140074d94  mov     rbp, [r11+40h]
0x140074d98  mov     rsp, r11
0x140074d9b  pop     r15
0x140074d9d  pop     r14
0x140074d9f  pop     r12
0x140074da1  pop     rdi
0x140074da2  pop     rsi
0x140074da3  retn
0x140074da5  lea     rbp, [rcx-8]
0x140074da9  xor     r14d, r14d
0x140074dac  lock xadd [rbp+28h], r14
0x140074db2  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x140074db9  lea     rdx, LifetimeFactor
0x140074dc0  mov     rbx, [rcx]
0x140074dc3  movzx   r8d, word ptr [rdx+rax*2]
0x140074dc8  xor     edx, edx
0x140074dca  mov     eax, [rbp+1Ch]
0x140074dcd  div     r8d
0x140074dd0  mov     r8, r12
0x140074dd3  sub     r8, r14
0x140074dd6  mov     r9d, eax
0x140074dd9  mov     rax, 624DD2F1A9FBE77h
0x140074de3  mul     r8
0x140074de6  sub     r8, rdx
0x140074de9  shr     r8, 1
0x140074dec  add     r8, rdx
0x140074def  shr     r8, 9
0x140074df3  cmp     r8d, r9d
0x140074df6  jnb     loc_140074F3A
0x140074dfc  lea     rcx, [rsp+1B8h+WatchdogInformation]; WatchdogInformation
0x140074e01  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140074e08  nop     dword ptr [rax+rax+00h]
0x140074e0d  mov     eax, [rsp+1B8h+WatchdogInformation.DpcTimeLimit]
0x140074e11  test    eax, eax
0x140074e13  jz      short loc_140074E28
0x140074e15  imul    ecx, eax, 19h
0x140074e18  mov     eax, 51EB851Fh
0x140074e1d  mul     ecx
0x140074e1f  shr     edx, 5
0x140074e22  cmp     [rsp+1B8h+WatchdogInformation.DpcTimeCount], edx
0x140074e26  jb      short loc_140074E34
0x140074e28  mov     rcx, rbx
0x140074e2b  cmp     rbx, rdi
0x140074e2e  jnz     loc_140074DA5
0x140074e34  mov     rax, 0FFFFF78000000008h
0x140074e3e  mov     [rsp+1B8h+var_198], 0; int
0x140074e46  mov     r8d, 19h
0x140074e4c  mov     rcx, [rax]
0x140074e4f  mov     rax, 346DC5D63886594Bh
0x140074e59  mul     rcx
0x140074e5c  mov     rax, cs:pRemoteEndpointTable
0x140074e63  shr     rdx, 0Bh
0x140074e67  mov     [rax+r13+80h], rdx
0x140074e6f  mov     edx, 258h
0x140074e74  mov     rcx, cs:pRemoteEndpointTable
0x140074e7b  add     rcx, 48h ; 'H'
0x140074e7f  add     rcx, r13; HashTable
0x140074e82  call    RtlRestructureHashTable
0x140074e87  cmp     cs:gWfpPerProContext, 0
0x140074e8f  mov     rbx, cs:pRemoteEndpointTable
0x140074e96  jz      short loc_140074EC2
0x140074e98  xor     ecx, ecx; ProcNumber
0x140074e9a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140074ea1  nop     dword ptr [rax+rax+00h]
0x140074ea6  lea     edx, [rax+rax*8]
0x140074ea9  mov     rax, cs:gWfpPerProContext
0x140074eb0  shl     edx, 3
0x140074eb3  mov     rdx, [rdx+rax]
0x140074eb7  cmp     dword ptr [rdx], 4
0x140074eba  jnz     short loc_140074EC2
0x140074ebc  mov     dword ptr [rdx], 0
0x140074ec2  mov     rcx, [rbx+r13+40h]; Lock
0x140074ec7  lea     rdx, [rsp+1B8h+LockState]; LockState
0x140074ecc  call    cs:__imp_NdisReleaseRWLock
0x140074ed3  nop     dword ptr [rax+rax+00h]
0x140074ed8  lea     rcx, [rsp+1B8h+WatchdogInformation]; WatchdogInformation
0x140074edd  call    cs:__imp_KeQueryDpcWatchdogInformation
0x140074ee4  nop     dword ptr [rax+rax+00h]
0x140074ee9  mov     eax, [rsp+1B8h+WatchdogInformation.DpcWatchdogLimit]
0x140074eed  test    eax, eax
0x140074eef  jz      short loc_140074F08
0x140074ef1  imul    ecx, eax, 19h
0x140074ef4  mov     eax, 51EB851Fh
0x140074ef9  mul     ecx
0x140074efb  shr     edx, 5
0x140074efe  cmp     [rsp+1B8h+WatchdogInformation.DpcWatchdogCount], edx
0x140074f02  jb      loc_140074D5D
0x140074f08  mov     eax, [rsp+1B8h+WatchdogInformation.DpcTimeLimit]
0x140074f0c  test    eax, eax
0x140074f0e  jz      loc_14007507C
0x140074f14  imul    ecx, eax, 19h
0x140074f17  mov     eax, 51EB851Fh
0x140074f1c  mul     ecx
0x140074f1e  shr     edx, 5
0x140074f21  cmp     [rsp+1B8h+WatchdogInformation.DpcTimeCount], edx
0x140074f25  jnb     loc_14007507C
0x140074f2b  test    r15w, r15w
0x140074f2f  jnz     loc_140074D70
0x140074f35  jmp     loc_1401C61D4
0x140074f3a  cmp     [rbx+8], rcx
0x140074f3e  jnz     short loc_140074F49
0x140074f40  mov     rax, [rcx+8]
0x140074f44  cmp     [rax], rcx
0x140074f47  jz      short loc_140074F73
0x140074f49  mov     ecx, 3
0x140074f4e  int     29h; Win8: RtlFailFast(ecx)
0x140074f50  mov     rdx, cs:pRemoteEndpointTable
0x140074f57  mov     ecx, [rdx+0Ch]
0x140074f5a  cmp     ecx, [rdx]
0x140074f5c  cmovb   eax, ecx
0x140074f5f  mov     [rdx+0Ch], eax
0x140074f62  mov     rax, cs:pRemoteEndpointTable
0x140074f69  mov     esi, [rax+0Ch]
0x140074f6c  mov     ebp, [rax]
0x140074f6e  jmp     loc_140074CA6
0x140074f73  mov     [rax], rbx
0x140074f76  mov     [rbx+8], rax
0x140074f7a  test    byte ptr cs:WPP_MAIN_CB+14Ah, 1
0x140074f81  jnz     short loc_140074F90
0x140074f83  mov     rcx, rbp
0x140074f86  call    WfpAleDeleteRemoteEndpointLru
0x140074f8b  jmp     loc_140074DFC
0x140074f90  xor     edx, edx; Val
0x140074f92  lea     rcx, [rsp+1B8h+var_B8]; void *
0x140074f9a  mov     r8d, 80h; Size
0x140074fa0  call    memset
0x140074fa5  xor     edx, edx; Val
0x140074fa7  lea     rcx, [rsp+1B8h+var_138]; void *
0x140074faf  mov     r8d, 80h; Size
0x140074fb5  call    memset
0x140074fba  movzx   eax, word ptr [rbp-1BAh]
0x140074fc1  lea     rdx, [rsp+1B8h+var_B8]
0x140074fc9  mov     r9d, dword ptr cs:scopeid_unspecified
0x140074fd0  mov     r8, [rbp-18h]
0x140074fd4  movzx   ecx, word ptr [rbp-1BCh]
0x140074fdb  mov     word ptr [rsp+1B8h+var_198], ax
0x140074fe0  call    INETADDR_SETSOCKADDR
0x140074fe5  movzx   edx, word ptr [rbp-1B8h]
0x140074fec  mov     r9d, dword ptr cs:scopeid_unspecified
0x140074ff3  mov     r8, [rbp-1D8h]
0x140074ffa  movzx   ecx, word ptr [rbp-1BCh]
0x140075001  mov     word ptr [rsp+1B8h+var_198], dx
0x140075006  lea     rdx, [rsp+1B8h+var_138]
0x14007500e  call    INETADDR_SETSOCKADDR
0x140075013  test    byte ptr cs:WPP_MAIN_CB+14Ah, 1
0x14007501a  jz      loc_140074F83
0x140075020  movzx   ecx, word ptr [rbp-1BCh]; af
0x140075027  movsxd  rdx, cs:CurrentLifeTimeThresholdIndex
0x14007502e  call    SOCKADDR_SIZE
0x140075033  movzx   r9d, al
0x140075037  lea     rax, LifetimeFactor
0x14007503e  movzx   eax, word ptr [rax+rdx*2]
0x140075042  mov     word ptr [rsp+1B8h+var_170], ax
0x140075047  mov     eax, [rbp+1Ch]
0x14007504a  mov     [rsp+1B8h+var_178], eax
0x14007504e  lea     rax, [rsp+1B8h+var_138]
0x140075056  mov     [rsp+1B8h+var_180], r14
0x14007505b  mov     [rsp+1B8h+var_188], r12
0x140075060  mov     [rsp+1B8h+var_190], rax
0x140075065  lea     rax, [rsp+1B8h+var_B8]
0x14007506d  mov     qword ptr [rsp+1B8h+var_198], rax
0x140075072  call    McTemplateK0qbr0br0xxqh_EtwWriteTransfer
0x140075077  jmp     loc_140074F83
0x14007507c  mov     ebp, [rsp+1B8h+var_164]
0x140075080  jmp     loc_140074D56
0x1401c61d4  mov     eax, [rsp+1B8h+var_160]
0x1401c61d8  cmp     eax, [rsp+1B8h+var_164]
0x1401c61dc  jnb     loc_140074D63
0x1401c61e2  mov     rax, cs:pRemoteEndpointTable
0x1401c61e9  lea     ecx, [rsi+1]
0x1401c61ec  mov     [rax+0Ch], ecx
0x1401c61ef  test    byte ptr cs:WPP_MAIN_CB+14Ah, 8
0x1401c61f6  jz      short loc_1401C6273
0x1401c61f8  mov     rcx, cs:LowNonPagedPoolEvent; Event
0x1401c61ff  call    cs:__imp_KeReadStateEvent
0x1401c6206  nop     dword ptr [rax+rax+00h]
0x1401c620b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h; Event
0x1401c6212  mov     esi, eax
0x1401c6214  call    cs:__imp_KeReadStateEvent
0x1401c621b  nop     dword ptr [rax+rax+00h]
0x1401c6220  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; Event
0x1401c6227  mov     edi, eax
0x1401c6229  call    cs:__imp_KeReadStateEvent
0x1401c6230  nop     dword ptr [rax+rax+00h]
0x1401c6235  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; Event
0x1401c623c  mov     ebx, eax
0x1401c623e  call    cs:__imp_KeReadStateEvent
0x1401c6245  nop     dword ptr [rax+rax+00h]
0x1401c624a  mov     dword ptr [rsp+1B8h+var_188], esi
0x1401c624e  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401c6255  mov     r9d, eax
0x1401c6258  mov     dword ptr [rsp+1B8h+var_190], edi
0x1401c625c  lea     rdx, DPC_CLEANUP
0x1401c6263  mov     [rsp+1B8h+var_198], ebx
0x1401c6267  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c626e  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401c6273  xor     r8d, r8d; SystemArgument2
0x1401c6276  lea     rcx, LruCleanupDpc; Dpc
0x1401c627d  xor     edx, edx; SystemArgument1
0x1401c627f  call    cs:__imp_KeInsertQueueDpc
0x1401c6286  nop     dword ptr [rax+rax+00h]
0x1401c628b  nop
0x1401c628c  jmp     loc_140074D70
```
