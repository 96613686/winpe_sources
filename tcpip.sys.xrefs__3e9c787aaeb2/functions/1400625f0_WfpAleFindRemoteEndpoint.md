# WfpAleFindRemoteEndpoint

- ea: `0x1400625f0`
- end: `0x140062d05`
- name: `WfpAleFindRemoteEndpoint`
- size: `1813`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140015580`
- `0x140127680`

## callees

- `0x1400625f0`
- `0x140063548`
- `0x140063720`
- `0x1400dff30`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140062c06`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140062c06`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140062970`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140062970`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006281b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062872`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062903`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062b06`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14006281b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062872`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062903`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062b06`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400627e1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400628c9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400627e1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400628c9`
- `ntoskrnl!KeReadStateEvent` at `0x140062b64`
- `ntoskrnl!KeReadStateEvent` at `0x140062b7a`
- `ntoskrnl!KeReadStateEvent` at `0x140062b8f`
- `ntoskrnl!KeReadStateEvent` at `0x140062ba4`
- `ntoskrnl!KeReadStateEvent` at `0x140062b64`
- `ntoskrnl!KeReadStateEvent` at `0x140062b7a`
- `ntoskrnl!KeReadStateEvent` at `0x140062b8f`
- `ntoskrnl!KeReadStateEvent` at `0x140062ba4`
- `ntoskrnl!KeInsertQueueDpc` at `0x140062a1f`
- `ntoskrnl!KeInsertQueueDpc` at `0x140062a1f`
- `NETIO!RtlComputeToeplitzHash` at `0x14006272c`
- `NETIO!RtlComputeToeplitzHash` at `0x14006274e`
- `NETIO!RtlComputeToeplitzHash` at `0x14006276f`
- `NETIO!RtlComputeToeplitzHash` at `0x1400627ab`
- `NETIO!RtlComputeToeplitzHash` at `0x140062c7d`
- `NETIO!RtlComputeToeplitzHash` at `0x140062ca4`
- `NETIO!RtlComputeToeplitzHash` at `0x14006272c`
- `NETIO!RtlComputeToeplitzHash` at `0x14006274e`
- `NETIO!RtlComputeToeplitzHash` at `0x14006276f`
- `NETIO!RtlComputeToeplitzHash` at `0x1400627ab`
- `NETIO!RtlComputeToeplitzHash` at `0x140062c7d`
- `NETIO!RtlComputeToeplitzHash` at `0x140062ca4`
- `NDIS!NdisAcquireRWLockRead` at `0x1400627fe`
- `NDIS!NdisAcquireRWLockRead` at `0x1400628e6`
- `NDIS!NdisAcquireRWLockRead` at `0x1400627fe`
- `NDIS!NdisAcquireRWLockRead` at `0x1400628e6`
- `NDIS!NdisReleaseRWLock` at `0x1400628a2`
- `NDIS!NdisReleaseRWLock` at `0x140062b3a`
- `NDIS!NdisReleaseRWLock` at `0x1400628a2`
- `NDIS!NdisReleaseRWLock` at `0x140062b3a`

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
    if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
    {
      StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
      v51 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      v52 = KeReadStateEvent(HighNonPagedPoolEvent);
      v53 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
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
0x1400625f0  push    rbp
0x1400625f2  push    rbx
0x1400625f3  push    rsi
0x1400625f4  push    rdi
0x1400625f5  push    r12
0x1400625f7  push    r13
0x1400625f9  push    r14
0x1400625fb  push    r15
0x1400625fd  lea     rbp, [rsp-1D8h]
0x140062605  sub     rsp, 2D8h
0x14006260c  mov     r13, [rbp+210h+arg_60]
0x140062613  xor     eax, eax
0x140062615  mov     ebx, r8d
0x140062618  mov     word ptr [rbp+210h+LockState.OldIrql], ax
0x14006261f  movzx   edi, dx
0x140062622  mov     [rbp+210h+LockState.Flags], al
0x140062628  mov     r14, rcx
0x14006262b  xor     r12d, r12d
0x14006262e  xor     edx, edx; Val
0x140062630  mov     [r13+0], r12
0x140062634  mov     r8d, 278h; Size
0x14006263a  lea     rcx, [rsp+310h+var_2B8]; void *
0x14006263f  mov     rsi, r9
0x140062642  call    memset
0x140062647  cmp     [rbp+210h+arg_38], r12b
0x14006264e  jz      short loc_140062658
0x140062650  lock or [rbp+210h+var_288], 1000000h
0x140062658  mov     rax, [rsi+10h]
0x14006265c  mov     rdx, [rbp+210h+arg_28]
0x140062663  mov     [rbp+210h+var_C8], r14
0x14006266a  mov     r14d, 2
0x140062670  mov     [rbp+210h+var_27C], di
0x140062674  mov     [rbp+210h+var_290], ebx
0x140062677  mov     rcx, [rax]
0x14006267a  movzx   eax, [rbp+210h+arg_48]
0x140062681  mov     [rbp+210h+var_CC], al
0x140062687  movzx   eax, [rbp+210h+arg_50]
0x14006268e  mov     [rbp+210h+var_CB], al
0x140062694  movzx   eax, [rbp+210h+arg_58]
0x14006269b  mov     [rbp+210h+var_50], al
0x1400626a1  mov     rax, [rsi+8]
0x1400626a5  mov     [rbp+210h+var_D8], rcx
0x1400626ac  mov     [rsp+310h+var_298], rdx
0x1400626b1  mov     rcx, [rax+10h]
0x1400626b5  mov     [rbp+210h+var_E0], rcx
0x1400626bc  cmp     r14w, di
0x1400626c0  jnz     short loc_1400626F6
0x1400626c2  mov     r8d, 4
0x1400626c8  mov     [rbp+210h+var_D0], r8d
0x1400626cf  cmp     ebx, 1
0x1400626d2  jnz     short loc_14006270C
0x1400626d4  mov     rcx, [rbp+210h+arg_40]
0x1400626db  mov     eax, [rcx]
0x1400626dd  mov     [rbp+210h+var_278], eax
0x1400626e0  movzx   eax, byte ptr [rcx+4]
0x1400626e4  mov     [rbp+210h+var_80], al
0x1400626ea  movzx   eax, byte ptr [rcx+5]
0x1400626ee  mov     [rbp+210h+var_7F], al
0x1400626f4  jmp     short loc_140062722
0x1400626f6  mov     r8d, 10h
0x1400626fc  mov     [rbp+210h+var_D0], r8d
0x140062703  cmp     ebx, 3Ah ; ':'
0x140062706  jz      loc_140062CF6
0x14006270c  movzx   eax, [rbp+210h+arg_20]
0x140062713  mov     [rbp+210h+var_27A], ax
0x140062717  movzx   eax, [rbp+210h+arg_30]
0x14006271e  mov     word ptr [rbp+210h+var_278], ax
0x140062722  xor     r9d, r9d
0x140062725  lea     rcx, TcpToeplitzHashContext
0x14006272c  call    cs:__imp_RtlComputeToeplitzHash
0x140062733  nop     dword ptr [rax+rax+00h]
0x140062738  xor     r9d, r9d
0x14006273b  lea     rdx, [rbp+210h+var_278]
0x14006273f  mov     r8d, 4
0x140062745  lea     rcx, TcpToeplitzHashContext
0x14006274c  mov     ebx, eax
0x14006274e  call    cs:__imp_RtlComputeToeplitzHash
0x140062755  nop     dword ptr [rax+rax+00h]
0x14006275a  xor     r9d, r9d
0x14006275d  lea     rdx, [rbp+210h+var_27A]
0x140062761  mov     edi, eax
0x140062763  lea     rcx, TcpToeplitzHashContext
0x14006276a  mov     r8d, r14d
0x14006276d  xor     edi, ebx
0x14006276f  call    cs:__imp_RtlComputeToeplitzHash
0x140062776  nop     dword ptr [rax+rax+00h]
0x14006277b  mov     ecx, [rbp+210h+var_290]
0x14006277e  mov     esi, eax
0x140062780  xor     esi, edi
0x140062782  cmp     ecx, 3Ah ; ':'
0x140062785  jz      loc_140062C3A
0x14006278b  cmp     ecx, 1
0x14006278e  jz      loc_140062CB9
0x140062794  xor     r9d, r9d
0x140062797  lea     rdx, [rbp+210h+var_C8]
0x14006279e  mov     r8d, 8
0x1400627a4  lea     rcx, TcpToeplitzHashContext
0x1400627ab  call    cs:__imp_RtlComputeToeplitzHash
0x1400627b2  nop     dword ptr [rax+rax+00h]
0x1400627b7  mov     rcx, cs:pRemoteEndpointTable
0x1400627be  mov     ebx, eax
0x1400627c0  mov     eax, esi
0x1400627c2  xor     rbx, rax
0x1400627c5  mov     eax, 80000000h
0x1400627ca  mov     r15d, [rcx+8]
0x1400627ce  or      rbx, rax
0x1400627d1  mov     r14d, ebx
0x1400627d4  and     r14d, r15d
0x1400627d7  mov     edi, r14d
0x1400627da  shl     rdi, 7
0x1400627de  add     rdi, rcx
0x1400627e1  call    cs:__imp_KeGetCurrentIrql
0x1400627e8  nop     dword ptr [rax+rax+00h]
0x1400627ed  mov     rcx, [rdi+40h]; Lock
0x1400627f1  lea     rdx, [rbp+210h+LockState]; LockState
0x1400627f8  xor     r8d, r8d; Flags
0x1400627fb  movzx   esi, al
0x1400627fe  call    cs:__imp_NdisAcquireRWLockRead
0x140062805  nop     dword ptr [rax+rax+00h]
0x14006280a  cmp     sil, 2
0x14006280e  jz      short loc_14006284C
0x140062810  cmp     cs:gWfpPerProContext, r12
0x140062817  jz      short loc_14006284C
0x140062819  xor     ecx, ecx; ProcNumber
0x14006281b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140062822  nop     dword ptr [rax+rax+00h]
0x140062827  lea     ecx, [rax+rax*8]
0x14006282a  mov     rax, cs:gWfpPerProContext
0x140062831  shl     ecx, 3
0x140062834  mov     rcx, [rcx+rax]
0x140062838  mov     rax, ds:0FFFFF78000000008h
0x140062842  mov     [rcx+8], rax
0x140062846  mov     dword ptr [rcx], 4
0x14006284c  mov     rcx, cs:pRemoteEndpointTable
0x140062853  cmp     r15d, [rcx+8]
0x140062857  jz      loc_140062945
0x14006285d  mov     edi, r14d
0x140062860  shl     rdi, 7
0x140062864  add     rdi, rcx
0x140062867  cmp     cs:gWfpPerProContext, r12
0x14006286e  jz      short loc_140062897
0x140062870  xor     ecx, ecx; ProcNumber
0x140062872  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140062879  nop     dword ptr [rax+rax+00h]
0x14006287e  lea     edx, [rax+rax*8]
0x140062881  mov     rax, cs:gWfpPerProContext
0x140062888  shl     edx, 3
0x14006288b  mov     rdx, [rdx+rax]
0x14006288f  cmp     dword ptr [rdx], 4
0x140062892  jnz     short loc_140062897
0x140062894  mov     [rdx], r12d
0x140062897  mov     rcx, [rdi+40h]; Lock
0x14006289b  lea     rdx, [rbp+210h+LockState]; LockState
0x1400628a2  call    cs:__imp_NdisReleaseRWLock
0x1400628a9  nop     dword ptr [rax+rax+00h]
0x1400628ae  mov     rcx, cs:pRemoteEndpointTable
0x1400628b5  mov     r14d, ebx
0x1400628b8  mov     r15d, [rcx+8]
0x1400628bc  and     r14d, r15d
0x1400628bf  mov     edi, r14d
0x1400628c2  shl     rdi, 7
0x1400628c6  add     rdi, rcx
0x1400628c9  call    cs:__imp_KeGetCurrentIrql
0x1400628d0  nop     dword ptr [rax+rax+00h]
0x1400628d5  mov     rcx, [rdi+40h]; Lock
0x1400628d9  lea     rdx, [rbp+210h+LockState]; LockState
0x1400628e0  xor     r8d, r8d; Flags
0x1400628e3  movzx   esi, al
0x1400628e6  call    cs:__imp_NdisAcquireRWLockRead
0x1400628ed  nop     dword ptr [rax+rax+00h]
0x1400628f2  cmp     sil, 2
0x1400628f6  jz      short loc_140062934
0x1400628f8  cmp     cs:gWfpPerProContext, r12
0x1400628ff  jz      short loc_140062934
0x140062901  xor     ecx, ecx; ProcNumber
0x140062903  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14006290a  nop     dword ptr [rax+rax+00h]
0x14006290f  lea     ecx, [rax+rax*8]
0x140062912  mov     rax, cs:gWfpPerProContext
0x140062919  shl     ecx, 3
0x14006291c  mov     rcx, [rcx+rax]
0x140062920  mov     rax, ds:0FFFFF78000000008h
0x14006292a  mov     [rcx+8], rax
0x14006292e  mov     dword ptr [rcx], 4
0x140062934  mov     rcx, cs:pRemoteEndpointTable
0x14006293b  cmp     r15d, [rcx+8]
0x14006293f  jnz     loc_14006285D
0x140062945  add     rcx, 48h ; 'H'
0x140062949  mov     r15d, r14d
0x14006294c  shl     r15, 7
0x140062950  lea     r8, [rsp+310h+Context]; Context
0x140062955  xorps   xmm0, xmm0
0x140062958  xor     eax, eax
0x14006295a  add     rcx, r15; HashTable
0x14006295d  mov     [rsp+310h+Context.Signature], rax
0x140062962  mov     rdi, r12
0x140062965  mov     rdx, rbx; Signature
0x140062968  movups  xmmword ptr [rsp+310h+Context.ChainHead], xmm0
0x14006296d  mov     r12d, r14d
0x140062970  call    cs:__imp_RtlLookupEntryHashTable
0x140062977  nop     dword ptr [rax+rax+00h]
0x14006297c  test    rax, rax
0x14006297f  jz      short loc_1400629A0
0x140062981  lea     r11, [rax-240h]
0x140062988  mov     rcx, r11
0x14006298b  lea     rdx, [rsp+310h+var_2B8]
0x140062990  call    WfpAlepIsSameEndpoint
0x140062995  test    al, al
0x140062997  jz      loc_140062BF3
0x14006299d  mov     rdi, r11
0x1400629a0  mov     rsi, 0FFFFF78000000008h
0x1400629aa  mov     rbx, 346DC5D63886594Bh
0x1400629b4  mov     rax, rbx
0x1400629b7  mov     rcx, [rsi]
0x1400629ba  mul     rcx
0x1400629bd  mov     rax, cs:pRemoteEndpointTable
0x1400629c4  mov     rcx, rdx
0x1400629c7  shr     rcx, 0Bh
0x1400629cb  sub     rcx, [r15+rax+80h]
0x1400629d3  mov     rax, 624DD2F1A9FBE77h
0x1400629dd  mul     rcx
0x1400629e0  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x1400629e7  sub     rcx, rdx
0x1400629ea  shr     rcx, 1
0x1400629ed  add     rcx, rdx
0x1400629f0  lea     rdx, LruDpcThreshold
0x1400629f7  movzx   eax, word ptr [rdx+rax*2]
0x1400629fb  shr     rcx, 9
0x1400629ff  cmp     ecx, eax
0x140062a01  jbe     short loc_140062A2B
0x140062a03  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+2, 8
0x140062a0a  jnz     loc_140062B5D
0x140062a10  mov     r8, r12; SystemArgument2
0x140062a13  lea     rcx, LruCleanupDpc; Dpc
0x140062a1a  mov     edx, 1; SystemArgument1
0x140062a1f  call    cs:__imp_KeInsertQueueDpc
0x140062a26  nop     dword ptr [rax+rax+00h]
0x140062a2b  test    rdi, rdi
0x140062a2e  jz      loc_140062AF3
0x140062a34  cmp     cs:gAleDebugEnabled, 0
0x140062a3b  jz      short loc_140062A57
0x140062a3d  mov     rax, [rdi+98h]
0x140062a44  mov     rcx, 0BADBADFABADBADFAh
0x140062a4e  cmp     rax, rcx
0x140062a51  jz      short loc_140062A57
0x140062a53  lock inc dword ptr [rax+10h]
0x140062a57  lea     rax, [rdi+80h]
0x140062a5e  mov     [rbp+210h+arg_60], rax
0x140062a65  mov     rax, [rbp+210h+arg_60]
0x140062a6c  mov     [rbp+210h+arg_60], rax
0x140062a73  mov     rax, [rbp+210h+arg_60]
0x140062a7a  movzx   r9d, byte ptr [rax+5]
0x140062a7f  mov     rcx, [rbp+210h+arg_60]
0x140062a86  mov     ecx, [rcx]
0x140062a88  test    cl, 2
0x140062a8b  jnz     short loc_140062AF3
0x140062a8d  test    cl, 1
0x140062a90  jz      loc_140062CDF
0x140062a96  mov     rdx, [rbp+210h+arg_60]
0x140062a9d  lea     r8d, [rcx+4]
0x140062aa1  mov     eax, ecx
0x140062aa3  lock cmpxchg [rdx], r8d
0x140062aa8  cmp     ecx, eax
0x140062aaa  jnz     short loc_140062A7F
0x140062aac  mov     ecx, [rdi+30h]
0x140062aaf  bt      ecx, 0Fh
0x140062ab3  jb      short loc_140062AD6
0x140062ab5  test    [rbp+210h+arg_48], 2
0x140062abc  jnz     loc_140062C17
0x140062ac2  mov     rcx, [rsi]
0x140062ac5  mov     rax, rbx
0x140062ac8  mul     rcx
0x140062acb  shr     rdx, 0Bh
0x140062acf  xchg    rdx, [rdi+220h]
0x140062ad6  mov     eax, [rdi+30h]
0x140062ad9  bt      eax, 14h
0x140062add  jb      short loc_140062AEF
0x140062adf  cmp     [rbp+210h+arg_58], 0
0x140062ae6  jz      short loc_140062AEF
0x140062ae8  mov     byte ptr [rdi+1EEh], 1
0x140062aef  mov     [r13+0], rdi
0x140062af3  cmp     cs:gWfpPerProContext, 0
0x140062afb  mov     rbx, cs:pRemoteEndpointTable
0x140062b02  jz      short loc_140062B2E
0x140062b04  xor     ecx, ecx; ProcNumber
0x140062b06  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140062b0d  nop     dword ptr [rax+rax+00h]
0x140062b12  lea     edx, [rax+rax*8]
0x140062b15  mov     rax, cs:gWfpPerProContext
0x140062b1c  shl     edx, 3
0x140062b1f  mov     rdx, [rdx+rax]
0x140062b23  cmp     dword ptr [rdx], 4
0x140062b26  jnz     short loc_140062B2E
0x140062b28  mov     dword ptr [rdx], 0
0x140062b2e  mov     rcx, [rbx+r15+40h]; Lock
0x140062b33  lea     rdx, [rbp+210h+LockState]; LockState
0x140062b3a  call    cs:__imp_NdisReleaseRWLock
0x140062b41  nop     dword ptr [rax+rax+00h]
0x140062b46  xor     eax, eax
0x140062b48  add     rsp, 2D8h
  ... truncated ...
```
