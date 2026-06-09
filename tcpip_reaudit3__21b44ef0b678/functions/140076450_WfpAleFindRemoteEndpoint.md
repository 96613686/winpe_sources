# WfpAleFindRemoteEndpoint

- ea: `0x140076450`
- end: `0x140076b65`
- name: `WfpAleFindRemoteEndpoint`
- size: `1813`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140054cb0`
- `0x14011d094`

## callees

- `0x140076450`
- `0x1400773a8`
- `0x140077580`
- `0x1400d2400`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140076a66`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140076a66`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400767d0`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1400767d0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007667b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400766d2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076763`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076966`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14007667b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400766d2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076763`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076966`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076641`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076729`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076641`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076729`
- `ntoskrnl!KeReadStateEvent` at `0x1400769c4`
- `ntoskrnl!KeReadStateEvent` at `0x1400769da`
- `ntoskrnl!KeReadStateEvent` at `0x1400769ef`
- `ntoskrnl!KeReadStateEvent` at `0x140076a04`
- `ntoskrnl!KeReadStateEvent` at `0x1400769c4`
- `ntoskrnl!KeReadStateEvent` at `0x1400769da`
- `ntoskrnl!KeReadStateEvent` at `0x1400769ef`
- `ntoskrnl!KeReadStateEvent` at `0x140076a04`
- `ntoskrnl!KeInsertQueueDpc` at `0x14007687f`
- `ntoskrnl!KeInsertQueueDpc` at `0x14007687f`
- `NETIO!RtlComputeToeplitzHash` at `0x14007658c`
- `NETIO!RtlComputeToeplitzHash` at `0x1400765ae`
- `NETIO!RtlComputeToeplitzHash` at `0x1400765cf`
- `NETIO!RtlComputeToeplitzHash` at `0x14007660b`
- `NETIO!RtlComputeToeplitzHash` at `0x140076add`
- `NETIO!RtlComputeToeplitzHash` at `0x140076b04`
- `NETIO!RtlComputeToeplitzHash` at `0x14007658c`
- `NETIO!RtlComputeToeplitzHash` at `0x1400765ae`
- `NETIO!RtlComputeToeplitzHash` at `0x1400765cf`
- `NETIO!RtlComputeToeplitzHash` at `0x14007660b`
- `NETIO!RtlComputeToeplitzHash` at `0x140076add`
- `NETIO!RtlComputeToeplitzHash` at `0x140076b04`
- `NDIS!NdisAcquireRWLockRead` at `0x14007665e`
- `NDIS!NdisAcquireRWLockRead` at `0x140076746`
- `NDIS!NdisAcquireRWLockRead` at `0x14007665e`
- `NDIS!NdisAcquireRWLockRead` at `0x140076746`
- `NDIS!NdisReleaseRWLock` at `0x140076702`
- `NDIS!NdisReleaseRWLock` at `0x14007699a`
- `NDIS!NdisReleaseRWLock` at `0x140076702`
- `NDIS!NdisReleaseRWLock` at `0x14007699a`

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
      v51 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
      v52 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.DeviceType);
      v53 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredRoutine);
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
0x140076450  push    rbp
0x140076452  push    rbx
0x140076453  push    rsi
0x140076454  push    rdi
0x140076455  push    r12
0x140076457  push    r13
0x140076459  push    r14
0x14007645b  push    r15
0x14007645d  lea     rbp, [rsp-1D8h]
0x140076465  sub     rsp, 2D8h
0x14007646c  mov     r13, [rbp+210h+arg_60]
0x140076473  xor     eax, eax
0x140076475  mov     ebx, r8d
0x140076478  mov     word ptr [rbp+210h+LockState.OldIrql], ax
0x14007647f  movzx   edi, dx
0x140076482  mov     [rbp+210h+LockState.Flags], al
0x140076488  mov     r14, rcx
0x14007648b  xor     r12d, r12d
0x14007648e  xor     edx, edx; Val
0x140076490  mov     [r13+0], r12
0x140076494  mov     r8d, 278h; Size
0x14007649a  lea     rcx, [rsp+310h+var_2B8]; void *
0x14007649f  mov     rsi, r9
0x1400764a2  call    memset
0x1400764a7  cmp     [rbp+210h+arg_38], r12b
0x1400764ae  jz      short loc_1400764B8
0x1400764b0  lock or [rbp+210h+var_288], 1000000h
0x1400764b8  mov     rax, [rsi+10h]
0x1400764bc  mov     rdx, [rbp+210h+arg_28]
0x1400764c3  mov     [rbp+210h+var_C8], r14
0x1400764ca  mov     r14d, 2
0x1400764d0  mov     [rbp+210h+var_27C], di
0x1400764d4  mov     [rbp+210h+var_290], ebx
0x1400764d7  mov     rcx, [rax]
0x1400764da  movzx   eax, [rbp+210h+arg_48]
0x1400764e1  mov     [rbp+210h+var_CC], al
0x1400764e7  movzx   eax, [rbp+210h+arg_50]
0x1400764ee  mov     [rbp+210h+var_CB], al
0x1400764f4  movzx   eax, [rbp+210h+arg_58]
0x1400764fb  mov     [rbp+210h+var_50], al
0x140076501  mov     rax, [rsi+8]
0x140076505  mov     [rbp+210h+var_D8], rcx
0x14007650c  mov     [rsp+310h+var_298], rdx
0x140076511  mov     rcx, [rax+10h]
0x140076515  mov     [rbp+210h+var_E0], rcx
0x14007651c  cmp     r14w, di
0x140076520  jnz     short loc_140076556
0x140076522  mov     r8d, 4
0x140076528  mov     [rbp+210h+var_D0], r8d
0x14007652f  cmp     ebx, 1
0x140076532  jnz     short loc_14007656C
0x140076534  mov     rcx, [rbp+210h+arg_40]
0x14007653b  mov     eax, [rcx]
0x14007653d  mov     [rbp+210h+var_278], eax
0x140076540  movzx   eax, byte ptr [rcx+4]
0x140076544  mov     [rbp+210h+var_80], al
0x14007654a  movzx   eax, byte ptr [rcx+5]
0x14007654e  mov     [rbp+210h+var_7F], al
0x140076554  jmp     short loc_140076582
0x140076556  mov     r8d, 10h
0x14007655c  mov     [rbp+210h+var_D0], r8d
0x140076563  cmp     ebx, 3Ah ; ':'
0x140076566  jz      loc_140076B56
0x14007656c  movzx   eax, [rbp+210h+arg_20]
0x140076573  mov     [rbp+210h+var_27A], ax
0x140076577  movzx   eax, [rbp+210h+arg_30]
0x14007657e  mov     word ptr [rbp+210h+var_278], ax
0x140076582  xor     r9d, r9d
0x140076585  lea     rcx, TcpToeplitzHashContext
0x14007658c  call    cs:__imp_RtlComputeToeplitzHash
0x140076593  nop     dword ptr [rax+rax+00h]
0x140076598  xor     r9d, r9d
0x14007659b  lea     rdx, [rbp+210h+var_278]
0x14007659f  mov     r8d, 4
0x1400765a5  lea     rcx, TcpToeplitzHashContext
0x1400765ac  mov     ebx, eax
0x1400765ae  call    cs:__imp_RtlComputeToeplitzHash
0x1400765b5  nop     dword ptr [rax+rax+00h]
0x1400765ba  xor     r9d, r9d
0x1400765bd  lea     rdx, [rbp+210h+var_27A]
0x1400765c1  mov     edi, eax
0x1400765c3  lea     rcx, TcpToeplitzHashContext
0x1400765ca  mov     r8d, r14d
0x1400765cd  xor     edi, ebx
0x1400765cf  call    cs:__imp_RtlComputeToeplitzHash
0x1400765d6  nop     dword ptr [rax+rax+00h]
0x1400765db  mov     ecx, [rbp+210h+var_290]
0x1400765de  mov     esi, eax
0x1400765e0  xor     esi, edi
0x1400765e2  cmp     ecx, 3Ah ; ':'
0x1400765e5  jz      loc_140076A9A
0x1400765eb  cmp     ecx, 1
0x1400765ee  jz      loc_140076B19
0x1400765f4  xor     r9d, r9d
0x1400765f7  lea     rdx, [rbp+210h+var_C8]
0x1400765fe  mov     r8d, 8
0x140076604  lea     rcx, TcpToeplitzHashContext
0x14007660b  call    cs:__imp_RtlComputeToeplitzHash
0x140076612  nop     dword ptr [rax+rax+00h]
0x140076617  mov     rcx, cs:pRemoteEndpointTable
0x14007661e  mov     ebx, eax
0x140076620  mov     eax, esi
0x140076622  xor     rbx, rax
0x140076625  mov     eax, 80000000h
0x14007662a  mov     r15d, [rcx+8]
0x14007662e  or      rbx, rax
0x140076631  mov     r14d, ebx
0x140076634  and     r14d, r15d
0x140076637  mov     edi, r14d
0x14007663a  shl     rdi, 7
0x14007663e  add     rdi, rcx
0x140076641  call    cs:__imp_KeGetCurrentIrql
0x140076648  nop     dword ptr [rax+rax+00h]
0x14007664d  mov     rcx, [rdi+40h]; Lock
0x140076651  lea     rdx, [rbp+210h+LockState]; LockState
0x140076658  xor     r8d, r8d; Flags
0x14007665b  movzx   esi, al
0x14007665e  call    cs:__imp_NdisAcquireRWLockRead
0x140076665  nop     dword ptr [rax+rax+00h]
0x14007666a  cmp     sil, 2
0x14007666e  jz      short loc_1400766AC
0x140076670  cmp     cs:gWfpPerProContext, r12
0x140076677  jz      short loc_1400766AC
0x140076679  xor     ecx, ecx; ProcNumber
0x14007667b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076682  nop     dword ptr [rax+rax+00h]
0x140076687  lea     ecx, [rax+rax*8]
0x14007668a  mov     rax, cs:gWfpPerProContext
0x140076691  shl     ecx, 3
0x140076694  mov     rcx, [rcx+rax]
0x140076698  mov     rax, ds:0FFFFF78000000008h
0x1400766a2  mov     [rcx+8], rax
0x1400766a6  mov     dword ptr [rcx], 4
0x1400766ac  mov     rcx, cs:pRemoteEndpointTable
0x1400766b3  cmp     r15d, [rcx+8]
0x1400766b7  jz      loc_1400767A5
0x1400766bd  mov     edi, r14d
0x1400766c0  shl     rdi, 7
0x1400766c4  add     rdi, rcx
0x1400766c7  cmp     cs:gWfpPerProContext, r12
0x1400766ce  jz      short loc_1400766F7
0x1400766d0  xor     ecx, ecx; ProcNumber
0x1400766d2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400766d9  nop     dword ptr [rax+rax+00h]
0x1400766de  lea     edx, [rax+rax*8]
0x1400766e1  mov     rax, cs:gWfpPerProContext
0x1400766e8  shl     edx, 3
0x1400766eb  mov     rdx, [rdx+rax]
0x1400766ef  cmp     dword ptr [rdx], 4
0x1400766f2  jnz     short loc_1400766F7
0x1400766f4  mov     [rdx], r12d
0x1400766f7  mov     rcx, [rdi+40h]; Lock
0x1400766fb  lea     rdx, [rbp+210h+LockState]; LockState
0x140076702  call    cs:__imp_NdisReleaseRWLock
0x140076709  nop     dword ptr [rax+rax+00h]
0x14007670e  mov     rcx, cs:pRemoteEndpointTable
0x140076715  mov     r14d, ebx
0x140076718  mov     r15d, [rcx+8]
0x14007671c  and     r14d, r15d
0x14007671f  mov     edi, r14d
0x140076722  shl     rdi, 7
0x140076726  add     rdi, rcx
0x140076729  call    cs:__imp_KeGetCurrentIrql
0x140076730  nop     dword ptr [rax+rax+00h]
0x140076735  mov     rcx, [rdi+40h]; Lock
0x140076739  lea     rdx, [rbp+210h+LockState]; LockState
0x140076740  xor     r8d, r8d; Flags
0x140076743  movzx   esi, al
0x140076746  call    cs:__imp_NdisAcquireRWLockRead
0x14007674d  nop     dword ptr [rax+rax+00h]
0x140076752  cmp     sil, 2
0x140076756  jz      short loc_140076794
0x140076758  cmp     cs:gWfpPerProContext, r12
0x14007675f  jz      short loc_140076794
0x140076761  xor     ecx, ecx; ProcNumber
0x140076763  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007676a  nop     dword ptr [rax+rax+00h]
0x14007676f  lea     ecx, [rax+rax*8]
0x140076772  mov     rax, cs:gWfpPerProContext
0x140076779  shl     ecx, 3
0x14007677c  mov     rcx, [rcx+rax]
0x140076780  mov     rax, ds:0FFFFF78000000008h
0x14007678a  mov     [rcx+8], rax
0x14007678e  mov     dword ptr [rcx], 4
0x140076794  mov     rcx, cs:pRemoteEndpointTable
0x14007679b  cmp     r15d, [rcx+8]
0x14007679f  jnz     loc_1400766BD
0x1400767a5  add     rcx, 48h ; 'H'
0x1400767a9  mov     r15d, r14d
0x1400767ac  shl     r15, 7
0x1400767b0  lea     r8, [rsp+310h+Context]; Context
0x1400767b5  xorps   xmm0, xmm0
0x1400767b8  xor     eax, eax
0x1400767ba  add     rcx, r15; HashTable
0x1400767bd  mov     [rsp+310h+Context.Signature], rax
0x1400767c2  mov     rdi, r12
0x1400767c5  mov     rdx, rbx; Signature
0x1400767c8  movups  xmmword ptr [rsp+310h+Context.ChainHead], xmm0
0x1400767cd  mov     r12d, r14d
0x1400767d0  call    cs:__imp_RtlLookupEntryHashTable
0x1400767d7  nop     dword ptr [rax+rax+00h]
0x1400767dc  test    rax, rax
0x1400767df  jz      short loc_140076800
0x1400767e1  lea     r11, [rax-240h]
0x1400767e8  mov     rcx, r11
0x1400767eb  lea     rdx, [rsp+310h+var_2B8]
0x1400767f0  call    WfpAlepIsSameEndpoint
0x1400767f5  test    al, al
0x1400767f7  jz      loc_140076A53
0x1400767fd  mov     rdi, r11
0x140076800  mov     rsi, 0FFFFF78000000008h
0x14007680a  mov     rbx, 346DC5D63886594Bh
0x140076814  mov     rax, rbx
0x140076817  mov     rcx, [rsi]
0x14007681a  mul     rcx
0x14007681d  mov     rax, cs:pRemoteEndpointTable
0x140076824  mov     rcx, rdx
0x140076827  shr     rcx, 0Bh
0x14007682b  sub     rcx, [r15+rax+80h]
0x140076833  mov     rax, 624DD2F1A9FBE77h
0x14007683d  mul     rcx
0x140076840  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x140076847  sub     rcx, rdx
0x14007684a  shr     rcx, 1
0x14007684d  add     rcx, rdx
0x140076850  lea     rdx, LruDpcThreshold
0x140076857  movzx   eax, word ptr [rdx+rax*2]
0x14007685b  shr     rcx, 9
0x14007685f  cmp     ecx, eax
0x140076861  jbe     short loc_14007688B
0x140076863  test    byte ptr cs:WPP_MAIN_CB+14Ah, 8
0x14007686a  jnz     loc_1400769BD
0x140076870  mov     r8, r12; SystemArgument2
0x140076873  lea     rcx, LruCleanupDpc; Dpc
0x14007687a  mov     edx, 1; SystemArgument1
0x14007687f  call    cs:__imp_KeInsertQueueDpc
0x140076886  nop     dword ptr [rax+rax+00h]
0x14007688b  test    rdi, rdi
0x14007688e  jz      loc_140076953
0x140076894  cmp     cs:gAleDebugEnabled, 0
0x14007689b  jz      short loc_1400768B7
0x14007689d  mov     rax, [rdi+98h]
0x1400768a4  mov     rcx, 0BADBADFABADBADFAh
0x1400768ae  cmp     rax, rcx
0x1400768b1  jz      short loc_1400768B7
0x1400768b3  lock inc dword ptr [rax+10h]
0x1400768b7  lea     rax, [rdi+80h]
0x1400768be  mov     [rbp+210h+arg_60], rax
0x1400768c5  mov     rax, [rbp+210h+arg_60]
0x1400768cc  mov     [rbp+210h+arg_60], rax
0x1400768d3  mov     rax, [rbp+210h+arg_60]
0x1400768da  movzx   r9d, byte ptr [rax+5]
0x1400768df  mov     rcx, [rbp+210h+arg_60]
0x1400768e6  mov     ecx, [rcx]
0x1400768e8  test    cl, 2
0x1400768eb  jnz     short loc_140076953
0x1400768ed  test    cl, 1
0x1400768f0  jz      loc_140076B3F
0x1400768f6  mov     rdx, [rbp+210h+arg_60]
0x1400768fd  lea     r8d, [rcx+4]
0x140076901  mov     eax, ecx
0x140076903  lock cmpxchg [rdx], r8d
0x140076908  cmp     ecx, eax
0x14007690a  jnz     short loc_1400768DF
0x14007690c  mov     ecx, [rdi+30h]
0x14007690f  bt      ecx, 0Fh
0x140076913  jb      short loc_140076936
0x140076915  test    [rbp+210h+arg_48], 2
0x14007691c  jnz     loc_140076A77
0x140076922  mov     rcx, [rsi]
0x140076925  mov     rax, rbx
0x140076928  mul     rcx
0x14007692b  shr     rdx, 0Bh
0x14007692f  xchg    rdx, [rdi+220h]
0x140076936  mov     eax, [rdi+30h]
0x140076939  bt      eax, 14h
0x14007693d  jb      short loc_14007694F
0x14007693f  cmp     [rbp+210h+arg_58], 0
0x140076946  jz      short loc_14007694F
0x140076948  mov     byte ptr [rdi+1EEh], 1
0x14007694f  mov     [r13+0], rdi
0x140076953  cmp     cs:gWfpPerProContext, 0
0x14007695b  mov     rbx, cs:pRemoteEndpointTable
0x140076962  jz      short loc_14007698E
0x140076964  xor     ecx, ecx; ProcNumber
0x140076966  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14007696d  nop     dword ptr [rax+rax+00h]
0x140076972  lea     edx, [rax+rax*8]
0x140076975  mov     rax, cs:gWfpPerProContext
0x14007697c  shl     edx, 3
0x14007697f  mov     rdx, [rdx+rax]
0x140076983  cmp     dword ptr [rdx], 4
0x140076986  jnz     short loc_14007698E
0x140076988  mov     dword ptr [rdx], 0
0x14007698e  mov     rcx, [rbx+r15+40h]; Lock
0x140076993  lea     rdx, [rbp+210h+LockState]; LockState
0x14007699a  call    cs:__imp_NdisReleaseRWLock
0x1400769a1  nop     dword ptr [rax+rax+00h]
0x1400769a6  xor     eax, eax
0x1400769a8  add     rsp, 2D8h
  ... truncated ...
```
