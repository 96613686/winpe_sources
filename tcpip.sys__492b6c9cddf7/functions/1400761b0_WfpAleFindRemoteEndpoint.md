# WfpAleFindRemoteEndpoint

- ea: `0x1400761b0`
- end: `0x1400768c5`
- name: `WfpAleFindRemoteEndpoint`
- size: `1813`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140054a10`
- `0x14011cf54`

## callees

- `0x1400761b0`
- `0x140077108`
- `0x1400772e0`
- `0x1400d2620`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400767c6`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400767c6`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140076530`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140076530`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400763db`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076432`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400764c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400766c6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400763db`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076432`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400764c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400766c6`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400763a1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076489`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400763a1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076489`
- `ntoskrnl!KeReadStateEvent` at `0x140076724`
- `ntoskrnl!KeReadStateEvent` at `0x14007673a`
- `ntoskrnl!KeReadStateEvent` at `0x14007674f`
- `ntoskrnl!KeReadStateEvent` at `0x140076764`
- `ntoskrnl!KeReadStateEvent` at `0x140076724`
- `ntoskrnl!KeReadStateEvent` at `0x14007673a`
- `ntoskrnl!KeReadStateEvent` at `0x14007674f`
- `ntoskrnl!KeReadStateEvent` at `0x140076764`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400765df`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400765df`
- `NETIO!RtlComputeToeplitzHash` at `0x1400762ec`
- `NETIO!RtlComputeToeplitzHash` at `0x14007630e`
- `NETIO!RtlComputeToeplitzHash` at `0x14007632f`
- `NETIO!RtlComputeToeplitzHash` at `0x14007636b`
- `NETIO!RtlComputeToeplitzHash` at `0x14007683d`
- `NETIO!RtlComputeToeplitzHash` at `0x140076864`
- `NETIO!RtlComputeToeplitzHash` at `0x1400762ec`
- `NETIO!RtlComputeToeplitzHash` at `0x14007630e`
- `NETIO!RtlComputeToeplitzHash` at `0x14007632f`
- `NETIO!RtlComputeToeplitzHash` at `0x14007636b`
- `NETIO!RtlComputeToeplitzHash` at `0x14007683d`
- `NETIO!RtlComputeToeplitzHash` at `0x140076864`
- `NDIS!NdisAcquireRWLockRead` at `0x1400763be`
- `NDIS!NdisAcquireRWLockRead` at `0x1400764a6`
- `NDIS!NdisAcquireRWLockRead` at `0x1400763be`
- `NDIS!NdisAcquireRWLockRead` at `0x1400764a6`
- `NDIS!NdisReleaseRWLock` at `0x140076462`
- `NDIS!NdisReleaseRWLock` at `0x1400766fa`
- `NDIS!NdisReleaseRWLock` at `0x140076462`
- `NDIS!NdisReleaseRWLock` at `0x1400766fa`

## pseudocode

```c
__int64 __fastcall WfpAleFindRemoteEndpoint(
        __int64 a1,
        __int16 a2,
        int a3,
        __int64 a4,
        __int16 a5,
        __int64 a6,
        __int16 a7,
        char a8,
        __int64 a9,
        char a10,
        char a11,
        char a12,
        volatile signed __int32 *a13)
{
  volatile signed __int32 *v13; // r13
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r8
  int v22; // ebx
  int v23; // edi
  unsigned int v24; // esi
  unsigned int v25; // eax
  int v26; // r15d
  ULONG_PTR v27; // rbx
  unsigned int v28; // r14d
  unsigned __int64 v29; // rdi
  KIRQL CurrentIrql; // si
  __int64 v31; // rcx
  __int64 v32; // rcx
  unsigned __int64 v33; // rdi
  _DWORD *v34; // rdx
  int v35; // r15d
  unsigned __int64 v36; // rdi
  KIRQL v37; // si
  __int64 v38; // rcx
  unsigned __int64 v39; // r15
  __int64 v40; // rdi
  unsigned __int64 v41; // r12
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  __int64 v43; // r11
  __int64 v44; // rax
  char v45; // r9
  unsigned __int32 v46; // ecx
  __int64 v47; // rbx
  _DWORD *v48; // rdx
  char StateEvent; // r14
  char v51; // si
  char v52; // bl
  LONG v53; // eax
  int v54; // ebx
  int v55; // ecx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v57[87]; // [rsp+58h] [rbp-A8h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+328h] [rbp+228h] BYREF

  v13 = a13;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *(_QWORD *)a13 = 0;
  memset(v57, 0, 0x278u);
  if ( a8 )
    _InterlockedOr((volatile signed __int32 *)&v57[6], 0x1000000u);
  v18 = *(__int64 **)(a4 + 16);
  v57[62] = a1;
  WORD2(v57[7]) = a2;
  LODWORD(v57[5]) = a3;
  v19 = *v18;
  BYTE4(v57[61]) = a10;
  BYTE5(v57[61]) = a11;
  LOBYTE(v57[77]) = a12;
  v20 = *(_QWORD *)(a4 + 8);
  v57[60] = v19;
  v57[4] = a6;
  v57[59] = *(_QWORD *)(v20 + 16);
  if ( a2 == 2 )
  {
    v21 = 4;
    LODWORD(v57[61]) = 4;
    if ( a3 == 1 )
    {
LABEL_5:
      LODWORD(v57[8]) = *(_DWORD *)a9;
      LOWORD(v57[71]) = *(_WORD *)(a9 + 4);
      goto LABEL_8;
    }
  }
  else
  {
    v21 = 16;
    LODWORD(v57[61]) = 16;
    if ( a3 == 58 && a2 == 23 )
      goto LABEL_5;
  }
  HIWORD(v57[7]) = a5;
  LOWORD(v57[8]) = a7;
LABEL_8:
  v22 = RtlComputeToeplitzHash(TcpToeplitzHashContext, a6, v21, 0);
  v23 = v22 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, &v57[8], 4, 0);
  v24 = v23 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, (char *)&v57[7] + 6, 2, 0);
  if ( LODWORD(v57[5]) == 58 )
  {
    if ( WORD2(v57[7]) != 23
      || (unsigned __int8)(LOBYTE(v57[71]) + 123) <= 3u
      || (unsigned __int8)(LOBYTE(v57[71]) + 0x80) <= 1u )
    {
      goto LABEL_10;
    }
  }
  else
  {
    if ( LODWORD(v57[5]) != 1 )
      goto LABEL_10;
    if ( WORD2(v57[7]) != 2 )
      goto LABEL_10;
    if ( LOBYTE(v57[71]) <= 0x12u )
    {
      v55 = 419585;
      if ( _bittest(&v55, LOBYTE(v57[71])) )
        goto LABEL_10;
    }
  }
  v54 = v24 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, &v57[71], 1, 0);
  v24 = v54 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, (char *)&v57[71] + 1, 1, 0);
LABEL_10:
  v25 = RtlComputeToeplitzHash(TcpToeplitzHashContext, &v57[62], 8, 0);
  v26 = *(_DWORD *)(pRemoteEndpointTable + 8);
  v27 = v24 ^ (unsigned __int64)v25 | 0x80000000;
  v28 = v26 & v27;
  v29 = pRemoteEndpointTable + ((unsigned __int64)(v26 & (unsigned int)v27) << 7);
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v29 + 64), &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v31 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v31 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v31 = 4;
  }
  v32 = pRemoteEndpointTable;
  if ( v26 != *(_DWORD *)(pRemoteEndpointTable + 8) )
  {
    do
    {
      v33 = v32 + ((unsigned __int64)v28 << 7);
      if ( gWfpPerProContext )
      {
        v34 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        if ( *v34 == 4 )
          *v34 = 0;
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v33 + 64), &LockState);
      v35 = *(_DWORD *)(pRemoteEndpointTable + 8);
      v28 = v35 & v27;
      v36 = pRemoteEndpointTable + ((unsigned __int64)(v35 & (unsigned int)v27) << 7);
      v37 = KeGetCurrentIrql();
      NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v36 + 64), &LockState, 0);
      if ( v37 != 2 && gWfpPerProContext )
      {
        v38 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        *(_QWORD *)(v38 + 8) = MEMORY[0xFFFFF78000000008];
        *(_DWORD *)v38 = 4;
      }
      v32 = pRemoteEndpointTable;
    }
    while ( v35 != *(_DWORD *)(pRemoteEndpointTable + 8) );
  }
  v39 = (unsigned __int64)v28 << 7;
  v40 = 0;
  memset(&Context, 0, sizeof(Context));
  v41 = v28;
  for ( i = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v39 + v32 + 72), v27, &Context);
        i;
        i = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v39 + pRemoteEndpointTable + 72), &Context) )
  {
    if ( (unsigned __int8)WfpAlepIsSameEndpoint(&i[-24], v57) )
    {
      v40 = v43;
      break;
    }
  }
  if ( (unsigned int)((MEMORY[0xFFFFF78000000008] / 0x2710uLL - *(_QWORD *)(v39 + pRemoteEndpointTable + 128)) / 0x3E8) > *((unsigned __int16 *)&LruDpcThreshold + CurrentLifeTimeThresholdIndex) )
  {
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 8) != 0 )
    {
      StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
      v51 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      v52 = KeReadStateEvent(HighNonPagedPoolEvent);
      v53 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredContext);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)DPC_CLEANUP,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v53,
        v52,
        v51,
        StateEvent);
    }
    KeInsertQueueDpc(&LruCleanupDpc, (PVOID)1, (PVOID)v41);
  }
  if ( v40 )
  {
    if ( gAleDebugEnabled )
    {
      v44 = *(_QWORD *)(v40 + 152);
      if ( v44 != 0xBADBADFABADBADFAuLL )
        _InterlockedIncrement((volatile signed __int32 *)(v44 + 16));
    }
    a13 = (volatile signed __int32 *)(v40 + 128);
    v45 = *(_BYTE *)(v40 + 133);
    while ( 1 )
    {
      v46 = *a13;
      if ( (*a13 & 2) != 0 || (v46 & 1) == 0 && (v45 || v46 < 4) )
        break;
      if ( v46 == _InterlockedCompareExchange(a13, v46 + 4, v46) )
      {
        if ( (*(_DWORD *)(v40 + 48) & 0x8000) == 0 )
        {
          if ( (a10 & 2) != 0 )
          {
            if ( a12 )
              WfpRefreshRemoteEndpointLruEntry(v40 + 504, 0, 0);
          }
          else
          {
            _InterlockedExchange64((volatile __int64 *)(v40 + 544), MEMORY[0xFFFFF78000000008] / 0x2710uLL);
          }
        }
        if ( (*(_DWORD *)(v40 + 48) & 0x100000) == 0 && a12 )
          *(_BYTE *)(v40 + 494) = 1;
        *(_QWORD *)v13 = v40;
        break;
      }
    }
  }
  v47 = pRemoteEndpointTable;
  if ( gWfpPerProContext )
  {
    v48 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v48 == 4 )
      *v48 = 0;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v47 + v39 + 64), &LockState);
  return 0;
}

```

## disassembly

```asm
0x1400761b0  push    rbp
0x1400761b2  push    rbx
0x1400761b3  push    rsi
0x1400761b4  push    rdi
0x1400761b5  push    r12
0x1400761b7  push    r13
0x1400761b9  push    r14
0x1400761bb  push    r15
0x1400761bd  lea     rbp, [rsp-1D8h]
0x1400761c5  sub     rsp, 2D8h
0x1400761cc  mov     r13, [rbp+210h+arg_60]
0x1400761d3  xor     eax, eax
0x1400761d5  mov     ebx, r8d
0x1400761d8  mov     word ptr [rbp+210h+LockState.OldIrql], ax
0x1400761df  movzx   edi, dx
0x1400761e2  mov     [rbp+210h+LockState.Flags], al
0x1400761e8  mov     r14, rcx
0x1400761eb  xor     r12d, r12d
0x1400761ee  xor     edx, edx; Val
0x1400761f0  mov     [r13+0], r12
0x1400761f4  mov     r8d, 278h; Size
0x1400761fa  lea     rcx, [rsp+310h+var_2B8]; void *
0x1400761ff  mov     rsi, r9
0x140076202  call    memset
0x140076207  cmp     [rbp+210h+arg_38], r12b
0x14007620e  jz      short loc_140076218
0x140076210  lock or [rbp+210h+var_288], 1000000h
0x140076218  mov     rax, [rsi+10h]
0x14007621c  mov     rdx, [rbp+210h+arg_28]
0x140076223  mov     [rbp+210h+var_C8], r14
0x14007622a  mov     r14d, 2
0x140076230  mov     [rbp+210h+var_27C], di
0x140076234  mov     [rbp+210h+var_290], ebx
0x140076237  mov     rcx, [rax]
0x14007623a  movzx   eax, [rbp+210h+arg_48]
0x140076241  mov     [rbp+210h+var_CC], al
0x140076247  movzx   eax, [rbp+210h+arg_50]
0x14007624e  mov     [rbp+210h+var_CB], al
0x140076254  movzx   eax, [rbp+210h+arg_58]
0x14007625b  mov     [rbp+210h+var_50], al
0x140076261  mov     rax, [rsi+8]
0x140076265  mov     [rbp+210h+var_D8], rcx
0x14007626c  mov     [rsp+310h+var_298], rdx
0x140076271  mov     rcx, [rax+10h]
0x140076275  mov     [rbp+210h+var_E0], rcx
0x14007627c  cmp     r14w, di
0x140076280  jnz     short loc_1400762B6
0x140076282  mov     r8d, 4
0x140076288  mov     [rbp+210h+var_D0], r8d
0x14007628f  cmp     ebx, 1
0x140076292  jnz     short loc_1400762CC
0x140076294  mov     rcx, [rbp+210h+arg_40]
0x14007629b  mov     eax, [rcx]
0x14007629d  mov     [rbp+210h+var_278], eax
0x1400762a0  movzx   eax, byte ptr [rcx+4]
0x1400762a4  mov     [rbp+210h+var_80], al
0x1400762aa  movzx   eax, byte ptr [rcx+5]
0x1400762ae  mov     [rbp+210h+var_7F], al
0x1400762b4  jmp     short loc_1400762E2
0x1400762b6  mov     r8d, 10h
0x1400762bc  mov     [rbp+210h+var_D0], r8d
0x1400762c3  cmp     ebx, 3Ah ; ':'
0x1400762c6  jz      loc_1400768B6
0x1400762cc  movzx   eax, [rbp+210h+arg_20]
0x1400762d3  mov     [rbp+210h+var_27A], ax
0x1400762d7  movzx   eax, [rbp+210h+arg_30]
0x1400762de  mov     word ptr [rbp+210h+var_278], ax
0x1400762e2  xor     r9d, r9d
0x1400762e5  lea     rcx, TcpToeplitzHashContext
0x1400762ec  call    cs:__imp_RtlComputeToeplitzHash
0x1400762f3  nop     dword ptr [rax+rax+00h]
0x1400762f8  xor     r9d, r9d
0x1400762fb  lea     rdx, [rbp+210h+var_278]
0x1400762ff  mov     r8d, 4
0x140076305  lea     rcx, TcpToeplitzHashContext
0x14007630c  mov     ebx, eax
0x14007630e  call    cs:__imp_RtlComputeToeplitzHash
0x140076315  nop     dword ptr [rax+rax+00h]
0x14007631a  xor     r9d, r9d
0x14007631d  lea     rdx, [rbp+210h+var_27A]
0x140076321  mov     edi, eax
0x140076323  lea     rcx, TcpToeplitzHashContext
0x14007632a  mov     r8d, r14d
0x14007632d  xor     edi, ebx
0x14007632f  call    cs:__imp_RtlComputeToeplitzHash
0x140076336  nop     dword ptr [rax+rax+00h]
0x14007633b  mov     ecx, [rbp+210h+var_290]
0x14007633e  mov     esi, eax
0x140076340  xor     esi, edi
0x140076342  cmp     ecx, 3Ah ; ':'
0x140076345  jz      loc_1400767FA
0x14007634b  cmp     ecx, 1
0x14007634e  jz      loc_140076879
0x140076354  xor     r9d, r9d
0x140076357  lea     rdx, [rbp+210h+var_C8]
0x14007635e  mov     r8d, 8
0x140076364  lea     rcx, TcpToeplitzHashContext
0x14007636b  call    cs:__imp_RtlComputeToeplitzHash
0x140076372  nop     dword ptr [rax+rax+00h]
0x140076377  mov     rcx, cs:pRemoteEndpointTable
0x14007637e  mov     ebx, eax
0x140076380  mov     eax, esi
0x140076382  xor     rbx, rax
0x140076385  mov     eax, 80000000h
0x14007638a  mov     r15d, [rcx+8]
0x14007638e  or      rbx, rax
0x140076391  mov     r14d, ebx
0x140076394  and     r14d, r15d
0x140076397  mov     edi, r14d
0x14007639a  shl     rdi, 7
0x14007639e  add     rdi, rcx
0x1400763a1  call    cs:__imp_KeGetCurrentIrql
0x1400763a8  nop     dword ptr [rax+rax+00h]
0x1400763ad  mov     rcx, [rdi+40h]; Lock
0x1400763b1  lea     rdx, [rbp+210h+LockState]; LockState
0x1400763b8  xor     r8d, r8d; Flags
0x1400763bb  movzx   esi, al
0x1400763be  call    cs:__imp_NdisAcquireRWLockRead
0x1400763c5  nop     dword ptr [rax+rax+00h]
0x1400763ca  cmp     sil, 2
0x1400763ce  jz      short loc_14007640C
0x1400763d0  cmp     cs:gWfpPerProContext, r12
0x1400763d7  jz      short loc_14007640C
0x1400763d9  xor     ecx, ecx; ProcNumber
0x1400763db  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400763e2  nop     dword ptr [rax+rax+00h]
0x1400763e7  lea     ecx, [rax+rax*8]
0x1400763ea  mov     rax, cs:gWfpPerProContext
0x1400763f1  shl     ecx, 3
0x1400763f4  mov     rcx, [rcx+rax]
0x1400763f8  mov     rax, ds:0FFFFF78000000008h
0x140076402  mov     [rcx+8], rax
0x140076406  mov     dword ptr [rcx], 4
0x14007640c  mov     rcx, cs:pRemoteEndpointTable
0x140076413  cmp     r15d, [rcx+8]
0x140076417  jz      loc_140076505
0x14007641d  mov     edi, r14d
0x140076420  shl     rdi, 7
0x140076424  add     rdi, rcx
0x140076427  cmp     cs:gWfpPerProContext, r12
0x14007642e  jz      short loc_140076457
0x140076430  xor     ecx, ecx; ProcNumber
0x140076432  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076439  nop     dword ptr [rax+rax+00h]
0x14007643e  lea     edx, [rax+rax*8]
0x140076441  mov     rax, cs:gWfpPerProContext
0x140076448  shl     edx, 3
0x14007644b  mov     rdx, [rdx+rax]
0x14007644f  cmp     dword ptr [rdx], 4
0x140076452  jnz     short loc_140076457
0x140076454  mov     [rdx], r12d
0x140076457  mov     rcx, [rdi+40h]; Lock
0x14007645b  lea     rdx, [rbp+210h+LockState]; LockState
0x140076462  call    cs:__imp_NdisReleaseRWLock
0x140076469  nop     dword ptr [rax+rax+00h]
0x14007646e  mov     rcx, cs:pRemoteEndpointTable
0x140076475  mov     r14d, ebx
0x140076478  mov     r15d, [rcx+8]
0x14007647c  and     r14d, r15d
0x14007647f  mov     edi, r14d
0x140076482  shl     rdi, 7
0x140076486  add     rdi, rcx
0x140076489  call    cs:__imp_KeGetCurrentIrql
0x140076490  nop     dword ptr [rax+rax+00h]
0x140076495  mov     rcx, [rdi+40h]; Lock
0x140076499  lea     rdx, [rbp+210h+LockState]; LockState
0x1400764a0  xor     r8d, r8d; Flags
0x1400764a3  movzx   esi, al
0x1400764a6  call    cs:__imp_NdisAcquireRWLockRead
0x1400764ad  nop     dword ptr [rax+rax+00h]
0x1400764b2  cmp     sil, 2
0x1400764b6  jz      short loc_1400764F4
0x1400764b8  cmp     cs:gWfpPerProContext, r12
0x1400764bf  jz      short loc_1400764F4
0x1400764c1  xor     ecx, ecx; ProcNumber
0x1400764c3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400764ca  nop     dword ptr [rax+rax+00h]
0x1400764cf  lea     ecx, [rax+rax*8]
0x1400764d2  mov     rax, cs:gWfpPerProContext
0x1400764d9  shl     ecx, 3
0x1400764dc  mov     rcx, [rcx+rax]
0x1400764e0  mov     rax, ds:0FFFFF78000000008h
0x1400764ea  mov     [rcx+8], rax
0x1400764ee  mov     dword ptr [rcx], 4
0x1400764f4  mov     rcx, cs:pRemoteEndpointTable
0x1400764fb  cmp     r15d, [rcx+8]
0x1400764ff  jnz     loc_14007641D
0x140076505  add     rcx, 48h ; 'H'
0x140076509  mov     r15d, r14d
0x14007650c  shl     r15, 7
0x140076510  lea     r8, [rsp+310h+Context]; Context
0x140076515  xorps   xmm0, xmm0
0x140076518  xor     eax, eax
0x14007651a  add     rcx, r15; HashTable
0x14007651d  mov     [rsp+310h+Context.Signature], rax
0x140076522  mov     rdi, r12
0x140076525  mov     rdx, rbx; Signature
0x140076528  movups  xmmword ptr [rsp+310h+Context.ChainHead], xmm0
0x14007652d  mov     r12d, r14d
0x140076530  call    cs:__imp_RtlLookupEntryHashTable
0x140076537  nop     dword ptr [rax+rax+00h]
0x14007653c  test    rax, rax
0x14007653f  jz      short loc_140076560
0x140076541  lea     r11, [rax-240h]
0x140076548  mov     rcx, r11
0x14007654b  lea     rdx, [rsp+310h+var_2B8]
0x140076550  call    WfpAlepIsSameEndpoint
0x140076555  test    al, al
0x140076557  jz      loc_1400767B3
0x14007655d  mov     rdi, r11
0x140076560  mov     rsi, 0FFFFF78000000008h
0x14007656a  mov     rbx, 346DC5D63886594Bh
0x140076574  mov     rax, rbx
0x140076577  mov     rcx, [rsi]
0x14007657a  mul     rcx
0x14007657d  mov     rax, cs:pRemoteEndpointTable
0x140076584  mov     rcx, rdx
0x140076587  shr     rcx, 0Bh
0x14007658b  sub     rcx, [r15+rax+80h]
0x140076593  mov     rax, 624DD2F1A9FBE77h
0x14007659d  mul     rcx
0x1400765a0  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x1400765a7  sub     rcx, rdx
0x1400765aa  shr     rcx, 1
0x1400765ad  add     rcx, rdx
0x1400765b0  lea     rdx, LruDpcThreshold
0x1400765b7  movzx   eax, word ptr [rdx+rax*2]
0x1400765bb  shr     rcx, 9
0x1400765bf  cmp     ecx, eax
0x1400765c1  jbe     short loc_1400765EB
0x1400765c3  test    byte ptr cs:WPP_MAIN_CB+14Ah, 8
0x1400765ca  jnz     loc_14007671D
0x1400765d0  mov     r8, r12; SystemArgument2
0x1400765d3  lea     rcx, LruCleanupDpc; Dpc
0x1400765da  mov     edx, 1; SystemArgument1
0x1400765df  call    cs:__imp_KeInsertQueueDpc
0x1400765e6  nop     dword ptr [rax+rax+00h]
0x1400765eb  test    rdi, rdi
0x1400765ee  jz      loc_1400766B3
0x1400765f4  cmp     cs:gAleDebugEnabled, 0
0x1400765fb  jz      short loc_140076617
0x1400765fd  mov     rax, [rdi+98h]
0x140076604  mov     rcx, 0BADBADFABADBADFAh
0x14007660e  cmp     rax, rcx
0x140076611  jz      short loc_140076617
0x140076613  lock inc dword ptr [rax+10h]
0x140076617  lea     rax, [rdi+80h]
0x14007661e  mov     [rbp+210h+arg_60], rax
0x140076625  mov     rax, [rbp+210h+arg_60]
0x14007662c  mov     [rbp+210h+arg_60], rax
0x140076633  mov     rax, [rbp+210h+arg_60]
0x14007663a  movzx   r9d, byte ptr [rax+5]
0x14007663f  mov     rcx, [rbp+210h+arg_60]
0x140076646  mov     ecx, [rcx]
0x140076648  test    cl, 2
0x14007664b  jnz     short loc_1400766B3
0x14007664d  test    cl, 1
0x140076650  jz      loc_14007689F
0x140076656  mov     rdx, [rbp+210h+arg_60]
0x14007665d  lea     r8d, [rcx+4]
0x140076661  mov     eax, ecx
0x140076663  lock cmpxchg [rdx], r8d
0x140076668  cmp     ecx, eax
0x14007666a  jnz     short loc_14007663F
0x14007666c  mov     ecx, [rdi+30h]
0x14007666f  bt      ecx, 0Fh
0x140076673  jb      short loc_140076696
0x140076675  test    [rbp+210h+arg_48], 2
0x14007667c  jnz     loc_1400767D7
0x140076682  mov     rcx, [rsi]
0x140076685  mov     rax, rbx
0x140076688  mul     rcx
0x14007668b  shr     rdx, 0Bh
0x14007668f  xchg    rdx, [rdi+220h]
0x140076696  mov     eax, [rdi+30h]
0x140076699  bt      eax, 14h
0x14007669d  jb      short loc_1400766AF
0x14007669f  cmp     [rbp+210h+arg_58], 0
0x1400766a6  jz      short loc_1400766AF
0x1400766a8  mov     byte ptr [rdi+1EEh], 1
0x1400766af  mov     [r13+0], rdi
0x1400766b3  cmp     cs:gWfpPerProContext, 0
0x1400766bb  mov     rbx, cs:pRemoteEndpointTable
0x1400766c2  jz      short loc_1400766EE
0x1400766c4  xor     ecx, ecx; ProcNumber
0x1400766c6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400766cd  nop     dword ptr [rax+rax+00h]
0x1400766d2  lea     edx, [rax+rax*8]
0x1400766d5  mov     rax, cs:gWfpPerProContext
0x1400766dc  shl     edx, 3
0x1400766df  mov     rdx, [rdx+rax]
0x1400766e3  cmp     dword ptr [rdx], 4
0x1400766e6  jnz     short loc_1400766EE
0x1400766e8  mov     dword ptr [rdx], 0
0x1400766ee  mov     rcx, [rbx+r15+40h]; Lock
0x1400766f3  lea     rdx, [rbp+210h+LockState]; LockState
0x1400766fa  call    cs:__imp_NdisReleaseRWLock
0x140076701  nop     dword ptr [rax+rax+00h]
0x140076706  xor     eax, eax
0x140076708  add     rsp, 2D8h
  ... truncated ...
```
