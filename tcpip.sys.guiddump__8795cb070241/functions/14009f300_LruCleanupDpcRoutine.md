# LruCleanupDpcRoutine

- ea: `0x14009f300`
- end: `0x14009f735`
- name: `LruCleanupDpcRoutine`
- size: `1077`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140063720`
- `0x140071ac0`
- `0x140071af0`
- `0x14009f300`
- `0x14009f740`
- `0x14009f8e0`
- `0x14009f9b8`
- `0x14011eac8`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f3c8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f54a`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f3c8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14009f54a`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14009f4b1`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14009f58d`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14009f4b1`
- `ntoskrnl!KeQueryDpcWatchdogInformation` at `0x14009f58d`
- `ntoskrnl!KeReadStateEvent` at `0x1401ce1f9`
- `ntoskrnl!KeReadStateEvent` at `0x1401ce20e`
- `ntoskrnl!KeReadStateEvent` at `0x1401ce223`
- `ntoskrnl!KeReadStateEvent` at `0x1401ce238`
- `ntoskrnl!KeReadStateEvent` at `0x1401ce1f9`
- `ntoskrnl!KeReadStateEvent` at `0x1401ce20e`
- `ntoskrnl!KeReadStateEvent` at `0x1401ce223`
- `ntoskrnl!KeReadStateEvent` at `0x1401ce238`
- `ntoskrnl!KeInsertQueueDpc` at `0x1401ce279`
- `ntoskrnl!KeInsertQueueDpc` at `0x1401ce279`
- `NDIS!NdisReleaseRWLock` at `0x14009f3fa`
- `NDIS!NdisReleaseRWLock` at `0x14009f57c`
- `NDIS!NdisReleaseRWLock` at `0x14009f3fa`
- `NDIS!NdisReleaseRWLock` at `0x14009f57c`

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
  __int64 v15; // rbp
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
    v15 = (__int64)(v13 - 1);
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
      if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 1) != 0 )
      {
        memset(v34, 0, sizeof(v34));
        memset(v33, 0, sizeof(v33));
        ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
          *(unsigned __int16 *)(v15 - 444),
          (unsigned int)v34,
          *(_QWORD *)(v15 - 24),
          scopeid_unspecified.0,
          *(_WORD *)(v15 - 442));
        ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int16))INETADDR_SETSOCKADDR)(
          *(unsigned __int16 *)(v15 - 444),
          (unsigned int)v33,
          *(_QWORD *)(v15 - 472),
          scopeid_unspecified.0,
          *(_WORD *)(v15 - 440));
        if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 1) != 0 )
        {
          v21 = SOCKADDR_SIZE(*(_WORD *)(v15 - 444));
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
            *(_DWORD *)(v15 + 28),
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
  if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
  {
    StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
    v26 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    v27 = KeReadStateEvent(HighNonPagedPoolEvent);
    v28 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
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
0x14009f300  mov     [rsp+arg_8], rbx
0x14009f305  mov     [rsp+arg_10], rbp
0x14009f30a  push    rsi
0x14009f30b  push    rdi
0x14009f30c  push    r12
0x14009f30e  push    r14
0x14009f310  push    r15
0x14009f312  sub     rsp, 190h
0x14009f319  mov     rax, cs:__security_cookie
0x14009f320  xor     rax, rsp
0x14009f323  mov     [rsp+1B8h+var_38], rax
0x14009f32b  xor     eax, eax
0x14009f32d  xorps   xmm0, xmm0
0x14009f330  mov     word ptr [rsp+1B8h+LockState.OldIrql], ax
0x14009f335  mov     rsi, r9
0x14009f338  mov     [rsp+1B8h+LockState.Flags], al
0x14009f33c  mov     r15, r8
0x14009f33f  mov     [rsp+1B8h+WatchdogInformation.Reserved], eax
0x14009f343  movups  xmmword ptr [rsp+1B8h+WatchdogInformation.DpcTimeLimit], xmm0
0x14009f348  test    r8w, r8w
0x14009f34c  jz      loc_14009F600
0x14009f352  lea     ebp, [r9+1]
0x14009f356  mov     rax, 0FFFFF78000000008h
0x14009f360  mov     [rsp+1B8h+var_164], ebp
0x14009f364  mov     [rsp+1B8h+arg_0], r13
0x14009f36c  mov     rcx, [rax]
0x14009f36f  mov     rax, 346DC5D63886594Bh
0x14009f379  mul     rcx
0x14009f37c  mov     r12, rdx
0x14009f37f  shr     r12, 0Bh
0x14009f383  cmp     esi, ebp
0x14009f385  jnb     loc_14009F40D
0x14009f38b  mov     ecx, esi
0x14009f38d  lea     rdx, [rsp+1B8h+LockState]
0x14009f392  call    WfpAleGetAndWriteLockPartition
0x14009f397  mov     rbx, cs:pRemoteEndpointTable
0x14009f39e  mov     r13d, eax
0x14009f3a1  shl     r13, 7
0x14009f3a5  mov     [rsp+1B8h+var_160], eax
0x14009f3a9  lea     rdi, [rbx+70h]
0x14009f3ad  add     rdi, r13
0x14009f3b0  mov     rcx, [rdi]
0x14009f3b3  cmp     rcx, rdi
0x14009f3b6  jnz     loc_14009F455
0x14009f3bc  cmp     cs:gWfpPerProContext, 0
0x14009f3c4  jz      short loc_14009F3F0
0x14009f3c6  xor     ecx, ecx; ProcNumber
0x14009f3c8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009f3cf  nop     dword ptr [rax+rax+00h]
0x14009f3d4  lea     ecx, [rax+rax*8]
0x14009f3d7  mov     rax, cs:gWfpPerProContext
0x14009f3de  shl     ecx, 3
0x14009f3e1  mov     rcx, [rcx+rax]
0x14009f3e5  cmp     dword ptr [rcx], 4
0x14009f3e8  jnz     short loc_14009F3F0
0x14009f3ea  mov     dword ptr [rcx], 0
0x14009f3f0  mov     rcx, [rbx+r13+40h]; Lock
0x14009f3f5  lea     rdx, [rsp+1B8h+LockState]; LockState
0x14009f3fa  call    cs:__imp_NdisReleaseRWLock
0x14009f401  nop     dword ptr [rax+rax+00h]
0x14009f406  inc     esi
0x14009f408  jmp     loc_14009F383
0x14009f40d  test    r15w, r15w
0x14009f411  jnz     short loc_14009F420
0x14009f413  mov     rax, cs:pRemoteEndpointTable
0x14009f41a  lea     ecx, [rsi+1]
0x14009f41d  mov     [rax+0Ch], ecx
0x14009f420  mov     r13, [rsp+1B8h+arg_0]
0x14009f428  mov     rcx, [rsp+1B8h+var_38]
0x14009f430  xor     rcx, rsp; StackCookie
0x14009f433  call    __security_check_cookie
0x14009f438  lea     r11, [rsp+1B8h+var_28]
0x14009f440  mov     rbx, [r11+38h]
0x14009f444  mov     rbp, [r11+40h]
0x14009f448  mov     rsp, r11
0x14009f44b  pop     r15
0x14009f44d  pop     r14
0x14009f44f  pop     r12
0x14009f451  pop     rdi
0x14009f452  pop     rsi
0x14009f453  retn
0x14009f455  lea     rbp, [rcx-8]
0x14009f459  xor     r14d, r14d
0x14009f45c  lock xadd [rbp+28h], r14
0x14009f462  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x14009f469  lea     rdx, LifetimeFactor
0x14009f470  mov     rbx, [rcx]
0x14009f473  movzx   r8d, word ptr [rdx+rax*2]
0x14009f478  xor     edx, edx
0x14009f47a  mov     eax, [rbp+1Ch]
0x14009f47d  div     r8d
0x14009f480  mov     r8, r12
0x14009f483  sub     r8, r14
0x14009f486  mov     r9d, eax
0x14009f489  mov     rax, 624DD2F1A9FBE77h
0x14009f493  mul     r8
0x14009f496  sub     r8, rdx
0x14009f499  shr     r8, 1
0x14009f49c  add     r8, rdx
0x14009f49f  shr     r8, 9
0x14009f4a3  cmp     r8d, r9d
0x14009f4a6  jnb     loc_14009F5EA
0x14009f4ac  lea     rcx, [rsp+1B8h+WatchdogInformation]; WatchdogInformation
0x14009f4b1  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14009f4b8  nop     dword ptr [rax+rax+00h]
0x14009f4bd  mov     eax, [rsp+1B8h+WatchdogInformation.DpcTimeLimit]
0x14009f4c1  test    eax, eax
0x14009f4c3  jz      short loc_14009F4D8
0x14009f4c5  imul    ecx, eax, 19h
0x14009f4c8  mov     eax, 51EB851Fh
0x14009f4cd  mul     ecx
0x14009f4cf  shr     edx, 5
0x14009f4d2  cmp     [rsp+1B8h+WatchdogInformation.DpcTimeCount], edx
0x14009f4d6  jb      short loc_14009F4E4
0x14009f4d8  mov     rcx, rbx
0x14009f4db  cmp     rbx, rdi
0x14009f4de  jnz     loc_14009F455
0x14009f4e4  mov     rax, 0FFFFF78000000008h
0x14009f4ee  mov     [rsp+1B8h+var_198], 0; int
0x14009f4f6  mov     r8d, 19h
0x14009f4fc  mov     rcx, [rax]
0x14009f4ff  mov     rax, 346DC5D63886594Bh
0x14009f509  mul     rcx
0x14009f50c  mov     rax, cs:pRemoteEndpointTable
0x14009f513  shr     rdx, 0Bh
0x14009f517  mov     [rax+r13+80h], rdx
0x14009f51f  mov     edx, 258h
0x14009f524  mov     rcx, cs:pRemoteEndpointTable
0x14009f52b  add     rcx, 48h ; 'H'
0x14009f52f  add     rcx, r13; HashTable
0x14009f532  call    RtlRestructureHashTable
0x14009f537  cmp     cs:gWfpPerProContext, 0
0x14009f53f  mov     rbx, cs:pRemoteEndpointTable
0x14009f546  jz      short loc_14009F572
0x14009f548  xor     ecx, ecx; ProcNumber
0x14009f54a  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14009f551  nop     dword ptr [rax+rax+00h]
0x14009f556  lea     edx, [rax+rax*8]
0x14009f559  mov     rax, cs:gWfpPerProContext
0x14009f560  shl     edx, 3
0x14009f563  mov     rdx, [rdx+rax]
0x14009f567  cmp     dword ptr [rdx], 4
0x14009f56a  jnz     short loc_14009F572
0x14009f56c  mov     dword ptr [rdx], 0
0x14009f572  mov     rcx, [rbx+r13+40h]; Lock
0x14009f577  lea     rdx, [rsp+1B8h+LockState]; LockState
0x14009f57c  call    cs:__imp_NdisReleaseRWLock
0x14009f583  nop     dword ptr [rax+rax+00h]
0x14009f588  lea     rcx, [rsp+1B8h+WatchdogInformation]; WatchdogInformation
0x14009f58d  call    cs:__imp_KeQueryDpcWatchdogInformation
0x14009f594  nop     dword ptr [rax+rax+00h]
0x14009f599  mov     eax, [rsp+1B8h+WatchdogInformation.DpcWatchdogLimit]
0x14009f59d  test    eax, eax
0x14009f59f  jz      short loc_14009F5B8
0x14009f5a1  imul    ecx, eax, 19h
0x14009f5a4  mov     eax, 51EB851Fh
0x14009f5a9  mul     ecx
0x14009f5ab  shr     edx, 5
0x14009f5ae  cmp     [rsp+1B8h+WatchdogInformation.DpcWatchdogCount], edx
0x14009f5b2  jb      loc_14009F40D
0x14009f5b8  mov     eax, [rsp+1B8h+WatchdogInformation.DpcTimeLimit]
0x14009f5bc  test    eax, eax
0x14009f5be  jz      loc_14009F72C
0x14009f5c4  imul    ecx, eax, 19h
0x14009f5c7  mov     eax, 51EB851Fh
0x14009f5cc  mul     ecx
0x14009f5ce  shr     edx, 5
0x14009f5d1  cmp     [rsp+1B8h+WatchdogInformation.DpcTimeCount], edx
0x14009f5d5  jnb     loc_14009F72C
0x14009f5db  test    r15w, r15w
0x14009f5df  jnz     loc_14009F420
0x14009f5e5  jmp     loc_1401CE1CE
0x14009f5ea  cmp     [rbx+8], rcx
0x14009f5ee  jnz     short loc_14009F5F9
0x14009f5f0  mov     rax, [rcx+8]
0x14009f5f4  cmp     [rax], rcx
0x14009f5f7  jz      short loc_14009F623
0x14009f5f9  mov     ecx, 3
0x14009f5fe  int     29h; Win8: RtlFailFast(ecx)
0x14009f600  mov     rdx, cs:pRemoteEndpointTable
0x14009f607  mov     ecx, [rdx+0Ch]
0x14009f60a  cmp     ecx, [rdx]
0x14009f60c  cmovb   eax, ecx
0x14009f60f  mov     [rdx+0Ch], eax
0x14009f612  mov     rax, cs:pRemoteEndpointTable
0x14009f619  mov     esi, [rax+0Ch]
0x14009f61c  mov     ebp, [rax]
0x14009f61e  jmp     loc_14009F356
0x14009f623  mov     [rax], rbx
0x14009f626  mov     [rbx+8], rax
0x14009f62a  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+2, 1
0x14009f631  jnz     short loc_14009F640
0x14009f633  mov     rcx, rbp
0x14009f636  call    WfpAleDeleteRemoteEndpointLru
0x14009f63b  jmp     loc_14009F4AC
0x14009f640  xor     edx, edx; Val
0x14009f642  lea     rcx, [rsp+1B8h+var_B8]; void *
0x14009f64a  mov     r8d, 80h; Size
0x14009f650  call    memset
0x14009f655  xor     edx, edx; Val
0x14009f657  lea     rcx, [rsp+1B8h+var_138]; void *
0x14009f65f  mov     r8d, 80h; Size
0x14009f665  call    memset
0x14009f66a  movzx   eax, word ptr [rbp-1BAh]
0x14009f671  lea     rdx, [rsp+1B8h+var_B8]
0x14009f679  mov     r9d, dword ptr cs:scopeid_unspecified
0x14009f680  mov     r8, [rbp-18h]
0x14009f684  movzx   ecx, word ptr [rbp-1BCh]
0x14009f68b  mov     word ptr [rsp+1B8h+var_198], ax
0x14009f690  call    INETADDR_SETSOCKADDR
0x14009f695  movzx   edx, word ptr [rbp-1B8h]
0x14009f69c  mov     r9d, dword ptr cs:scopeid_unspecified
0x14009f6a3  mov     r8, [rbp-1D8h]
0x14009f6aa  movzx   ecx, word ptr [rbp-1BCh]
0x14009f6b1  mov     word ptr [rsp+1B8h+var_198], dx
0x14009f6b6  lea     rdx, [rsp+1B8h+var_138]
0x14009f6be  call    INETADDR_SETSOCKADDR
0x14009f6c3  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+2, 1
0x14009f6ca  jz      loc_14009F633
0x14009f6d0  movzx   ecx, word ptr [rbp-1BCh]; af
0x14009f6d7  movsxd  rdx, cs:CurrentLifeTimeThresholdIndex
0x14009f6de  call    SOCKADDR_SIZE
0x14009f6e3  movzx   r9d, al
0x14009f6e7  lea     rax, LifetimeFactor
0x14009f6ee  movzx   eax, word ptr [rax+rdx*2]
0x14009f6f2  mov     word ptr [rsp+1B8h+var_170], ax
0x14009f6f7  mov     eax, [rbp+1Ch]
0x14009f6fa  mov     [rsp+1B8h+var_178], eax
0x14009f6fe  lea     rax, [rsp+1B8h+var_138]
0x14009f706  mov     [rsp+1B8h+var_180], r14
0x14009f70b  mov     [rsp+1B8h+var_188], r12
0x14009f710  mov     [rsp+1B8h+var_190], rax
0x14009f715  lea     rax, [rsp+1B8h+var_B8]
0x14009f71d  mov     qword ptr [rsp+1B8h+var_198], rax
0x14009f722  call    McTemplateK0qbr0br0xxqh_EtwWriteTransfer
0x14009f727  jmp     loc_14009F633
0x14009f72c  mov     ebp, [rsp+1B8h+var_164]
0x14009f730  jmp     loc_14009F406
0x1401ce1ce  mov     eax, [rsp+1B8h+var_160]
0x1401ce1d2  cmp     eax, [rsp+1B8h+var_164]
0x1401ce1d6  jnb     loc_14009F413
0x1401ce1dc  mov     rax, cs:pRemoteEndpointTable
0x1401ce1e3  lea     ecx, [rsi+1]
0x1401ce1e6  mov     [rax+0Ch], ecx
0x1401ce1e9  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+2, 8
0x1401ce1f0  jz      short loc_1401CE26D
0x1401ce1f2  mov     rcx, cs:LowNonPagedPoolEvent; Event
0x1401ce1f9  call    cs:__imp_KeReadStateEvent
0x1401ce200  nop     dword ptr [rax+rax+00h]
0x1401ce205  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h; Event
0x1401ce20c  mov     esi, eax
0x1401ce20e  call    cs:__imp_KeReadStateEvent
0x1401ce215  nop     dword ptr [rax+rax+00h]
0x1401ce21a  mov     rcx, cs:HighNonPagedPoolEvent; Event
0x1401ce221  mov     edi, eax
0x1401ce223  call    cs:__imp_KeReadStateEvent
0x1401ce22a  nop     dword ptr [rax+rax+00h]
0x1401ce22f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h; Event
0x1401ce236  mov     ebx, eax
0x1401ce238  call    cs:__imp_KeReadStateEvent
0x1401ce23f  nop     dword ptr [rax+rax+00h]
0x1401ce244  mov     dword ptr [rsp+1B8h+var_188], esi
0x1401ce248  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x1401ce24f  mov     r9d, eax
0x1401ce252  mov     dword ptr [rsp+1B8h+var_190], edi
0x1401ce256  lea     rdx, DPC_CLEANUP
0x1401ce25d  mov     [rsp+1B8h+var_198], ebx
0x1401ce261  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401ce268  call    McTemplateK0qqqq_EtwWriteTransfer
0x1401ce26d  xor     r8d, r8d; SystemArgument2
0x1401ce270  lea     rcx, LruCleanupDpc; Dpc
0x1401ce277  xor     edx, edx; SystemArgument1
0x1401ce279  call    cs:__imp_KeInsertQueueDpc
0x1401ce280  nop     dword ptr [rax+rax+00h]
0x1401ce285  nop
0x1401ce286  jmp     loc_14009F420
```
