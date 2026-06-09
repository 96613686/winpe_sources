# WfpAleFastFindRemoteEndpoint

- ea: `0x1400768d0`
- end: `0x140076f39`
- name: `WfpAleFastFindRemoteEndpoint`
- size: `1641`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140096950`

## callees

- `0x1400768d0`
- `0x140077108`
- `0x1400772e0`
- `0x14008a370`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140076e0c`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140076e0c`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140076b59`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140076b59`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076a01`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076a58`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076aed`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076d12`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076a01`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076a58`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076aed`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076d12`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400769c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076ab1`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400769c5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076ab1`
- `ntoskrnl!KeReadStateEvent` at `0x140076d76`
- `ntoskrnl!KeReadStateEvent` at `0x140076d8b`
- `ntoskrnl!KeReadStateEvent` at `0x140076da0`
- `ntoskrnl!KeReadStateEvent` at `0x140076db5`
- `ntoskrnl!KeReadStateEvent` at `0x140076d76`
- `ntoskrnl!KeReadStateEvent` at `0x140076d8b`
- `ntoskrnl!KeReadStateEvent` at `0x140076da0`
- `ntoskrnl!KeReadStateEvent` at `0x140076db5`
- `ntoskrnl!KeInsertQueueDpc` at `0x140076c06`
- `ntoskrnl!KeInsertQueueDpc` at `0x140076c06`
- `NETIO!RtlComputeToeplitzHash` at `0x14007690c`
- `NETIO!RtlComputeToeplitzHash` at `0x14007692e`
- `NETIO!RtlComputeToeplitzHash` at `0x140076954`
- `NETIO!RtlComputeToeplitzHash` at `0x140076991`
- `NETIO!RtlComputeToeplitzHash` at `0x140076e66`
- `NETIO!RtlComputeToeplitzHash` at `0x140076e8d`
- `NETIO!RtlComputeToeplitzHash` at `0x14007690c`
- `NETIO!RtlComputeToeplitzHash` at `0x14007692e`
- `NETIO!RtlComputeToeplitzHash` at `0x140076954`
- `NETIO!RtlComputeToeplitzHash` at `0x140076991`
- `NETIO!RtlComputeToeplitzHash` at `0x140076e66`
- `NETIO!RtlComputeToeplitzHash` at `0x140076e8d`
- `NDIS!NdisAcquireRWLockRead` at `0x1400769e3`
- `NDIS!NdisAcquireRWLockRead` at `0x140076acf`
- `NDIS!NdisAcquireRWLockRead` at `0x1400769e3`
- `NDIS!NdisAcquireRWLockRead` at `0x140076acf`
- `NDIS!NdisReleaseRWLock` at `0x140076a8c`
- `NDIS!NdisReleaseRWLock` at `0x140076d47`
- `NDIS!NdisReleaseRWLock` at `0x140076a8c`
- `NDIS!NdisReleaseRWLock` at `0x140076d47`

## pseudocode

```c
__int64 __fastcall WfpAleFastFindRemoteEndpoint(__int64 a1, char *a2)
{
  __int64 v2; // r8
  __int64 v4; // rdx
  int v6; // ebx
  int v7; // edi
  int v8; // eax
  int v9; // ecx
  unsigned int v10; // esi
  unsigned int v11; // eax
  int v12; // r15d
  ULONG_PTR v13; // rbx
  unsigned int v14; // ebp
  unsigned __int64 v15; // rdi
  KIRQL CurrentIrql; // si
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned __int64 v19; // rdi
  _DWORD *v20; // rdx
  int v21; // r15d
  unsigned __int64 v22; // rdi
  KIRQL v23; // si
  __int64 v24; // rcx
  unsigned __int64 v25; // r15
  unsigned __int64 v26; // r12
  __int64 v27; // rdi
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  __int64 v29; // r11
  __int64 v30; // rax
  char v31; // r9
  unsigned __int32 v32; // ecx
  char v33; // r8
  __int64 v34; // rbx
  _DWORD *v35; // rdx
  char StateEvent; // bp
  char v38; // si
  char v39; // bl
  LONG v40; // eax
  __int64 v41; // rdx
  char v42; // cl
  int v43; // ebx
  unsigned int v44; // eax
  int v45; // ecx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+40h] [rbp-58h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+A0h] [rbp+8h] BYREF
  unsigned __int32 *v48; // [rsp+B0h] [rbp+18h]

  v2 = *(unsigned int *)(a1 + 488);
  *(_WORD *)&LockState.OldIrql = 0;
  v4 = *(_QWORD *)(a1 + 32);
  LockState.Flags = 0;
  v6 = RtlComputeToeplitzHash(TcpToeplitzHashContext, v4, v2, 0);
  v7 = v6 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, a1 + 64, 4, 0);
  v8 = RtlComputeToeplitzHash(TcpToeplitzHashContext, a1 + 62, 2, 0);
  v9 = *(_DWORD *)(a1 + 40);
  v10 = v7 ^ v8;
  if ( v9 == 58 )
  {
    if ( *(_WORD *)(a1 + 60) != 23 )
      goto LABEL_3;
    v41 = a1 + 568;
    v42 = *(_BYTE *)(a1 + 568);
    if ( (unsigned __int8)(v42 + 123) <= 3u || (unsigned __int8)(v42 + 0x80) <= 1u )
      goto LABEL_3;
  }
  else
  {
    if ( v9 != 1 )
      goto LABEL_3;
    if ( *(_WORD *)(a1 + 60) != 2 )
      goto LABEL_3;
    v41 = a1 + 568;
    v44 = *(unsigned __int8 *)(a1 + 568);
    if ( (unsigned __int8)v44 <= 0x12u )
    {
      v45 = 419585;
      if ( _bittest(&v45, v44) )
        goto LABEL_3;
    }
  }
  v43 = v10 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, v41, 1, 0);
  v10 = v43 ^ RtlComputeToeplitzHash(TcpToeplitzHashContext, a1 + 569, 1, 0);
LABEL_3:
  v11 = RtlComputeToeplitzHash(TcpToeplitzHashContext, a1 + 496, 8, 0);
  v12 = *(_DWORD *)(pRemoteEndpointTable + 8);
  v13 = v10 ^ (unsigned __int64)v11 | 0x80000000;
  v14 = v12 & v13;
  v15 = pRemoteEndpointTable + ((unsigned __int64)(v12 & (unsigned int)v13) << 7);
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v15 + 64), &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v17 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v17 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v17 = 4;
  }
  v18 = pRemoteEndpointTable;
  if ( v12 != *(_DWORD *)(pRemoteEndpointTable + 8) )
  {
    do
    {
      v19 = v18 + ((unsigned __int64)v14 << 7);
      if ( gWfpPerProContext )
      {
        v20 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        if ( *v20 == 4 )
          *v20 = 0;
      }
      NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v19 + 64), &LockState);
      v21 = *(_DWORD *)(pRemoteEndpointTable + 8);
      v14 = v21 & v13;
      v22 = pRemoteEndpointTable + ((unsigned __int64)(v21 & (unsigned int)v13) << 7);
      v23 = KeGetCurrentIrql();
      NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(v22 + 64), &LockState, 0);
      if ( v23 != 2 && gWfpPerProContext )
      {
        v24 = *(_QWORD *)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        *(_QWORD *)(v24 + 8) = MEMORY[0xFFFFF78000000008];
        *(_DWORD *)v24 = 4;
      }
      v18 = pRemoteEndpointTable;
    }
    while ( v21 != *(_DWORD *)(pRemoteEndpointTable + 8) );
  }
  v25 = (unsigned __int64)v14 << 7;
  v26 = v14;
  v27 = 0;
  memset(&Context, 0, sizeof(Context));
  for ( i = RtlLookupEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v25 + v18 + 72), v13, &Context);
        i;
        i = RtlGetNextEntryHashTable((PRTL_DYNAMIC_HASH_TABLE)(v25 + pRemoteEndpointTable + 72), &Context) )
  {
    if ( (unsigned __int8)WfpAlepIsSameEndpoint(&i[-24], a1) )
    {
      v27 = v29;
      break;
    }
  }
  if ( (unsigned int)((MEMORY[0xFFFFF78000000008] / 0x2710uLL - *(_QWORD *)(v25 + pRemoteEndpointTable + 128)) / 0x3E8) > *((unsigned __int16 *)&LruDpcThreshold + CurrentLifeTimeThresholdIndex) )
  {
    if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 10) & 8) != 0 )
    {
      StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
      v38 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceContext);
      v39 = KeReadStateEvent(HighNonPagedPoolEvent);
      v40 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredContext);
      McTemplateK0qqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)DPC_CLEANUP,
        (unsigned int)MICROSOFT_TCPIP_PROVIDER,
        v40,
        v39,
        v38,
        StateEvent);
    }
    KeInsertQueueDpc(&LruCleanupDpc, (PVOID)1, (PVOID)v26);
  }
  if ( v27 )
  {
    if ( gAleDebugEnabled )
    {
      v30 = *(_QWORD *)(v27 + 152);
      if ( v30 != 0xBADBADFABADBADFAuLL )
        _InterlockedIncrement((volatile signed __int32 *)(v30 + 16));
    }
    v48 = (unsigned __int32 *)(v27 + 128);
    v31 = *(_BYTE *)(v27 + 133);
    do
    {
      v32 = *v48;
      if ( (*v48 & 2) != 0 || (v32 & 1) == 0 && (v31 || v32 < 4) )
      {
        v27 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"WfpAleFastFindRemoteEndpoint",
            37);
        }
        goto LABEL_37;
      }
    }
    while ( v32 != _InterlockedCompareExchange((volatile signed __int32 *)v48, v32 + 4, v32) );
    if ( (*(_DWORD *)(v27 + 48) & 0x40000000) != 0
      || (*(_DWORD *)(v27 + 280) & 1) != 0
      || (*(_DWORD *)(v27 + 200) & 4) != 0
      || (*(_DWORD *)(v27 + 48) & 0xC000) == 0xC000 )
    {
      v33 = 0;
    }
    else
    {
      v33 = 1;
      if ( (*(_DWORD *)(v27 + 48) & 0x8000) == 0 )
        _InterlockedExchange64((volatile __int64 *)(v27 + 544), MEMORY[0xFFFFF78000000008] / 0x2710uLL);
    }
    *a2 = v33;
  }
LABEL_37:
  v34 = pRemoteEndpointTable;
  if ( gWfpPerProContext )
  {
    v35 = *(_DWORD **)(72 * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v35 == 4 )
      *v35 = 0;
  }
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(v34 + v25 + 64), &LockState);
  return v27;
}

```

## disassembly

```asm
0x1400768d0  mov     r11, rsp
0x1400768d3  mov     [r11+10h], rbx
0x1400768d7  push    rbp
0x1400768d8  push    rsi
0x1400768d9  push    rdi
0x1400768da  push    r12
0x1400768dc  push    r13
0x1400768de  push    r14
0x1400768e0  push    r15
0x1400768e2  sub     rsp, 60h
0x1400768e6  mov     r8d, [rcx+1E8h]
0x1400768ed  xor     eax, eax
0x1400768ef  mov     r13, rdx
0x1400768f2  mov     [r11+8], ax
0x1400768f7  mov     rdx, [rcx+20h]
0x1400768fb  mov     r14, rcx
0x1400768fe  lea     rcx, TcpToeplitzHashContext
0x140076905  mov     [r11+0Ah], al
0x140076909  xor     r9d, r9d
0x14007690c  call    cs:__imp_RtlComputeToeplitzHash
0x140076913  nop     dword ptr [rax+rax+00h]
0x140076918  lea     rdx, [r14+40h]
0x14007691c  xor     r9d, r9d
0x14007691f  mov     r8d, 4
0x140076925  lea     rcx, TcpToeplitzHashContext
0x14007692c  mov     ebx, eax
0x14007692e  call    cs:__imp_RtlComputeToeplitzHash
0x140076935  nop     dword ptr [rax+rax+00h]
0x14007693a  lea     rdx, [r14+3Eh]
0x14007693e  xor     r9d, r9d
0x140076941  mov     edi, eax
0x140076943  lea     rcx, TcpToeplitzHashContext
0x14007694a  xor     edi, ebx
0x14007694c  mov     ebx, 2
0x140076951  mov     r8d, ebx
0x140076954  call    cs:__imp_RtlComputeToeplitzHash
0x14007695b  nop     dword ptr [rax+rax+00h]
0x140076960  mov     ecx, [r14+28h]
0x140076964  mov     esi, eax
0x140076966  xor     esi, edi
0x140076968  cmp     ecx, 3Ah ; ':'
0x14007696b  jz      loc_140076E25
0x140076971  cmp     ecx, 1
0x140076974  jz      loc_140076F09
0x14007697a  lea     rdx, [r14+1F0h]
0x140076981  xor     r9d, r9d
0x140076984  mov     r8d, 8
0x14007698a  lea     rcx, TcpToeplitzHashContext
0x140076991  call    cs:__imp_RtlComputeToeplitzHash
0x140076998  nop     dword ptr [rax+rax+00h]
0x14007699d  mov     rcx, cs:pRemoteEndpointTable
0x1400769a4  mov     ebx, eax
0x1400769a6  mov     eax, esi
0x1400769a8  xor     rbx, rax
0x1400769ab  mov     eax, 80000000h
0x1400769b0  mov     r15d, [rcx+8]
0x1400769b4  or      rbx, rax
0x1400769b7  mov     ebp, ebx
0x1400769b9  and     ebp, r15d
0x1400769bc  mov     edi, ebp
0x1400769be  shl     rdi, 7
0x1400769c2  add     rdi, rcx
0x1400769c5  call    cs:__imp_KeGetCurrentIrql
0x1400769cc  nop     dword ptr [rax+rax+00h]
0x1400769d1  mov     rcx, [rdi+40h]; Lock
0x1400769d5  lea     rdx, [rsp+98h+LockState]; LockState
0x1400769dd  xor     r8d, r8d; Flags
0x1400769e0  movzx   esi, al
0x1400769e3  call    cs:__imp_NdisAcquireRWLockRead
0x1400769ea  nop     dword ptr [rax+rax+00h]
0x1400769ef  cmp     sil, 2
0x1400769f3  jz      short loc_140076A32
0x1400769f5  cmp     cs:gWfpPerProContext, 0
0x1400769fd  jz      short loc_140076A32
0x1400769ff  xor     ecx, ecx; ProcNumber
0x140076a01  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076a08  nop     dword ptr [rax+rax+00h]
0x140076a0d  lea     ecx, [rax+rax*8]
0x140076a10  mov     rax, cs:gWfpPerProContext
0x140076a17  shl     ecx, 3
0x140076a1a  mov     rcx, [rcx+rax]
0x140076a1e  mov     rax, ds:0FFFFF78000000008h
0x140076a28  mov     [rcx+8], rax
0x140076a2c  mov     dword ptr [rcx], 4
0x140076a32  mov     rcx, cs:pRemoteEndpointTable
0x140076a39  cmp     r15d, [rcx+8]
0x140076a3d  jz      loc_140076B2F
0x140076a43  mov     edi, ebp
0x140076a45  shl     rdi, 7
0x140076a49  add     rdi, rcx
0x140076a4c  cmp     cs:gWfpPerProContext, 0
0x140076a54  jz      short loc_140076A80
0x140076a56  xor     ecx, ecx; ProcNumber
0x140076a58  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076a5f  nop     dword ptr [rax+rax+00h]
0x140076a64  lea     edx, [rax+rax*8]
0x140076a67  mov     rax, cs:gWfpPerProContext
0x140076a6e  shl     edx, 3
0x140076a71  mov     rdx, [rdx+rax]
0x140076a75  cmp     dword ptr [rdx], 4
0x140076a78  jnz     short loc_140076A80
0x140076a7a  mov     dword ptr [rdx], 0
0x140076a80  mov     rcx, [rdi+40h]; Lock
0x140076a84  lea     rdx, [rsp+98h+LockState]; LockState
0x140076a8c  call    cs:__imp_NdisReleaseRWLock
0x140076a93  nop     dword ptr [rax+rax+00h]
0x140076a98  mov     rcx, cs:pRemoteEndpointTable
0x140076a9f  mov     ebp, ebx
0x140076aa1  mov     r15d, [rcx+8]
0x140076aa5  and     ebp, r15d
0x140076aa8  mov     edi, ebp
0x140076aaa  shl     rdi, 7
0x140076aae  add     rdi, rcx
0x140076ab1  call    cs:__imp_KeGetCurrentIrql
0x140076ab8  nop     dword ptr [rax+rax+00h]
0x140076abd  mov     rcx, [rdi+40h]; Lock
0x140076ac1  lea     rdx, [rsp+98h+LockState]; LockState
0x140076ac9  xor     r8d, r8d; Flags
0x140076acc  movzx   esi, al
0x140076acf  call    cs:__imp_NdisAcquireRWLockRead
0x140076ad6  nop     dword ptr [rax+rax+00h]
0x140076adb  cmp     sil, 2
0x140076adf  jz      short loc_140076B1E
0x140076ae1  cmp     cs:gWfpPerProContext, 0
0x140076ae9  jz      short loc_140076B1E
0x140076aeb  xor     ecx, ecx; ProcNumber
0x140076aed  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076af4  nop     dword ptr [rax+rax+00h]
0x140076af9  lea     ecx, [rax+rax*8]
0x140076afc  mov     rax, cs:gWfpPerProContext
0x140076b03  shl     ecx, 3
0x140076b06  mov     rcx, [rcx+rax]
0x140076b0a  mov     rax, ds:0FFFFF78000000008h
0x140076b14  mov     [rcx+8], rax
0x140076b18  mov     dword ptr [rcx], 4
0x140076b1e  mov     rcx, cs:pRemoteEndpointTable
0x140076b25  cmp     r15d, [rcx+8]
0x140076b29  jnz     loc_140076A43
0x140076b2f  add     rcx, 48h ; 'H'
0x140076b33  mov     r15d, ebp
0x140076b36  shl     r15, 7
0x140076b3a  lea     r8, [rsp+98h+Context]; Context
0x140076b3f  xorps   xmm0, xmm0
0x140076b42  mov     r12d, ebp
0x140076b45  xor     eax, eax
0x140076b47  add     rcx, r15; HashTable
0x140076b4a  xor     edi, edi
0x140076b4c  mov     [rsp+98h+Context.Signature], rax
0x140076b51  mov     rdx, rbx; Signature
0x140076b54  movups  xmmword ptr [rsp+98h+Context.ChainHead], xmm0
0x140076b59  call    cs:__imp_RtlLookupEntryHashTable
0x140076b60  nop     dword ptr [rax+rax+00h]
0x140076b65  test    rax, rax
0x140076b68  jz      short loc_140076B87
0x140076b6a  lea     r11, [rax-240h]
0x140076b71  mov     rdx, r14
0x140076b74  mov     rcx, r11
0x140076b77  call    WfpAlepIsSameEndpoint
0x140076b7c  test    al, al
0x140076b7e  jz      loc_140076DF9
0x140076b84  mov     rdi, r11
0x140076b87  mov     rbx, 0FFFFF78000000008h
0x140076b91  mov     r14, 346DC5D63886594Bh
0x140076b9b  mov     rax, r14
0x140076b9e  mov     rcx, [rbx]
0x140076ba1  mul     rcx
0x140076ba4  mov     rax, cs:pRemoteEndpointTable
0x140076bab  mov     rcx, rdx
0x140076bae  shr     rcx, 0Bh
0x140076bb2  sub     rcx, [r15+rax+80h]
0x140076bba  mov     rax, 624DD2F1A9FBE77h
0x140076bc4  mul     rcx
0x140076bc7  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x140076bce  sub     rcx, rdx
0x140076bd1  shr     rcx, 1
0x140076bd4  add     rcx, rdx
0x140076bd7  lea     rdx, LruDpcThreshold
0x140076bde  movzx   eax, word ptr [rdx+rax*2]
0x140076be2  shr     rcx, 9
0x140076be6  cmp     ecx, eax
0x140076be8  jbe     short loc_140076C12
0x140076bea  test    byte ptr cs:WPP_MAIN_CB+14Ah, 8
0x140076bf1  jnz     loc_140076D6F
0x140076bf7  mov     r8, r12; SystemArgument2
0x140076bfa  lea     rcx, LruCleanupDpc; Dpc
0x140076c01  mov     edx, 1; SystemArgument1
0x140076c06  call    cs:__imp_KeInsertQueueDpc
0x140076c0d  nop     dword ptr [rax+rax+00h]
0x140076c12  test    rdi, rdi
0x140076c15  jz      loc_140076CFF
0x140076c1b  cmp     cs:gAleDebugEnabled, 0
0x140076c22  jz      short loc_140076C3E
0x140076c24  mov     rax, [rdi+98h]
0x140076c2b  mov     rcx, 0BADBADFABADBADFAh
0x140076c35  cmp     rax, rcx
0x140076c38  jz      short loc_140076C3E
0x140076c3a  lock inc dword ptr [rax+10h]
0x140076c3e  lea     rax, [rdi+80h]
0x140076c45  mov     [rsp+98h+arg_10], rax
0x140076c4d  mov     rax, [rsp+98h+arg_10]
0x140076c55  mov     [rsp+98h+arg_10], rax
0x140076c5d  mov     rax, [rsp+98h+arg_10]
0x140076c65  movzx   r9d, byte ptr [rax+5]
0x140076c6a  mov     rcx, [rsp+98h+arg_10]
0x140076c72  mov     ecx, [rcx]
0x140076c74  test    cl, 2
0x140076c77  jnz     loc_140076EB0
0x140076c7d  test    cl, 1
0x140076c80  jz      loc_140076EA2
0x140076c86  mov     rdx, [rsp+98h+arg_10]
0x140076c8e  lea     r8d, [rcx+4]
0x140076c92  mov     eax, ecx
0x140076c94  lock cmpxchg [rdx], r8d
0x140076c99  cmp     ecx, eax
0x140076c9b  jnz     short loc_140076C6A
0x140076c9d  mov     eax, [rdi+30h]
0x140076ca0  bt      eax, 1Eh
0x140076ca4  jb      loc_140076E1D
0x140076caa  mov     eax, [rdi+118h]
0x140076cb0  test    al, 1
0x140076cb2  jnz     loc_140076E1D
0x140076cb8  mov     eax, [rdi+0C8h]
0x140076cbe  test    al, 4
0x140076cc0  jnz     loc_140076E1D
0x140076cc6  mov     ecx, [rdi+30h]
0x140076cc9  and     ecx, 0C000h
0x140076ccf  cmp     ecx, 0C000h
0x140076cd5  jz      loc_140076E1D
0x140076cdb  mov     ecx, [rdi+30h]
0x140076cde  mov     r8b, 1
0x140076ce1  bt      ecx, 0Fh
0x140076ce5  jb      short loc_140076CFB
0x140076ce7  mov     rcx, [rbx]
0x140076cea  mov     rax, r14
0x140076ced  mul     rcx
0x140076cf0  shr     rdx, 0Bh
0x140076cf4  xchg    rdx, [rdi+220h]
0x140076cfb  mov     [r13+0], r8b
0x140076cff  cmp     cs:gWfpPerProContext, 0
0x140076d07  mov     rbx, cs:pRemoteEndpointTable
0x140076d0e  jz      short loc_140076D3A
0x140076d10  xor     ecx, ecx; ProcNumber
0x140076d12  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076d19  nop     dword ptr [rax+rax+00h]
0x140076d1e  lea     edx, [rax+rax*8]
0x140076d21  mov     rax, cs:gWfpPerProContext
0x140076d28  shl     edx, 3
0x140076d2b  mov     rdx, [rdx+rax]
0x140076d2f  cmp     dword ptr [rdx], 4
0x140076d32  jnz     short loc_140076D3A
0x140076d34  mov     dword ptr [rdx], 0
0x140076d3a  mov     rcx, [rbx+r15+40h]; Lock
0x140076d3f  lea     rdx, [rsp+98h+LockState]; LockState
0x140076d47  call    cs:__imp_NdisReleaseRWLock
0x140076d4e  nop     dword ptr [rax+rax+00h]
0x140076d53  mov     rbx, [rsp+98h+arg_8]
0x140076d5b  mov     rax, rdi
0x140076d5e  add     rsp, 60h
0x140076d62  pop     r15
0x140076d64  pop     r14
0x140076d66  pop     r13
0x140076d68  pop     r12
0x140076d6a  pop     rdi
0x140076d6b  pop     rsi
0x140076d6c  pop     rbp
0x140076d6d  retn
0x140076d6f  mov     rcx, cs:LowNonPagedPoolEvent; Event
0x140076d76  call    cs:__imp_KeReadStateEvent
0x140076d7d  nop     dword ptr [rax+rax+00h]
0x140076d82  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; Event
0x140076d89  mov     ebp, eax
0x140076d8b  call    cs:__imp_KeReadStateEvent
0x140076d92  nop     dword ptr [rax+rax+00h]
0x140076d97  mov     rcx, cs:HighNonPagedPoolEvent; Event
0x140076d9e  mov     esi, eax
0x140076da0  call    cs:__imp_KeReadStateEvent
0x140076da7  nop     dword ptr [rax+rax+00h]
0x140076dac  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredContext; Event
0x140076db3  mov     ebx, eax
0x140076db5  call    cs:__imp_KeReadStateEvent
0x140076dbc  nop     dword ptr [rax+rax+00h]
0x140076dc1  mov     [rsp+98h+var_68], ebp
0x140076dc5  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x140076dcc  mov     r9d, eax
0x140076dcf  mov     [rsp+98h+var_70], esi
0x140076dd3  lea     rdx, DPC_CLEANUP
0x140076dda  mov     [rsp+98h+var_78], ebx
0x140076dde  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140076de5  call    McTemplateK0qqqq_EtwWriteTransfer
0x140076dea  mov     rbx, 0FFFFF78000000008h
0x140076df4  jmp     loc_140076BF7
0x140076df9  mov     rcx, cs:pRemoteEndpointTable
0x140076e00  lea     rdx, [rsp+98h+Context]; Context
0x140076e05  add     rcx, 48h ; 'H'
0x140076e09  add     rcx, r15; HashTable
0x140076e0c  call    cs:__imp_RtlGetNextEntryHashTable
0x140076e13  nop     dword ptr [rax+rax+00h]
0x140076e18  jmp     loc_140076B65
0x140076e1d  xor     r8b, r8b
0x140076e20  jmp     loc_140076CFB
  ... truncated ...
```
