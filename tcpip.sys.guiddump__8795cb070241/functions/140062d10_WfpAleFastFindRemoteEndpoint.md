# WfpAleFastFindRemoteEndpoint

- ea: `0x140062d10`
- end: `0x140063379`
- name: `WfpAleFastFindRemoteEndpoint`
- size: `1641`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14005d740`

## callees

- `0x140062d10`
- `0x140063548`
- `0x140063720`
- `0x1400ad6a0`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14006324c`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14006324c`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140062f99`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140062f99`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062e41`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062e98`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062f2d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063152`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062e41`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062e98`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140062f2d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063152`
- `ntoskrnl!KeGetCurrentIrql` at `0x140062e05`
- `ntoskrnl!KeGetCurrentIrql` at `0x140062ef1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140062e05`
- `ntoskrnl!KeGetCurrentIrql` at `0x140062ef1`
- `ntoskrnl!KeReadStateEvent` at `0x1400631b6`
- `ntoskrnl!KeReadStateEvent` at `0x1400631cb`
- `ntoskrnl!KeReadStateEvent` at `0x1400631e0`
- `ntoskrnl!KeReadStateEvent` at `0x1400631f5`
- `ntoskrnl!KeReadStateEvent` at `0x1400631b6`
- `ntoskrnl!KeReadStateEvent` at `0x1400631cb`
- `ntoskrnl!KeReadStateEvent` at `0x1400631e0`
- `ntoskrnl!KeReadStateEvent` at `0x1400631f5`
- `ntoskrnl!KeInsertQueueDpc` at `0x140063046`
- `ntoskrnl!KeInsertQueueDpc` at `0x140063046`
- `NETIO!RtlComputeToeplitzHash` at `0x140062d4c`
- `NETIO!RtlComputeToeplitzHash` at `0x140062d6e`
- `NETIO!RtlComputeToeplitzHash` at `0x140062d94`
- `NETIO!RtlComputeToeplitzHash` at `0x140062dd1`
- `NETIO!RtlComputeToeplitzHash` at `0x1400632a6`
- `NETIO!RtlComputeToeplitzHash` at `0x1400632cd`
- `NETIO!RtlComputeToeplitzHash` at `0x140062d4c`
- `NETIO!RtlComputeToeplitzHash` at `0x140062d6e`
- `NETIO!RtlComputeToeplitzHash` at `0x140062d94`
- `NETIO!RtlComputeToeplitzHash` at `0x140062dd1`
- `NETIO!RtlComputeToeplitzHash` at `0x1400632a6`
- `NETIO!RtlComputeToeplitzHash` at `0x1400632cd`
- `NDIS!NdisAcquireRWLockRead` at `0x140062e23`
- `NDIS!NdisAcquireRWLockRead` at `0x140062f0f`
- `NDIS!NdisAcquireRWLockRead` at `0x140062e23`
- `NDIS!NdisAcquireRWLockRead` at `0x140062f0f`
- `NDIS!NdisReleaseRWLock` at `0x140062ecc`
- `NDIS!NdisReleaseRWLock` at `0x140063187`
- `NDIS!NdisReleaseRWLock` at `0x140062ecc`
- `NDIS!NdisReleaseRWLock` at `0x140063187`

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
    if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
    {
      StateEvent = KeReadStateEvent(LowNonPagedPoolEvent);
      v38 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
      v39 = KeReadStateEvent(HighNonPagedPoolEvent);
      v40 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Queue.Wcb.CurrentIrp);
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
0x140062d10  mov     r11, rsp
0x140062d13  mov     [r11+10h], rbx
0x140062d17  push    rbp
0x140062d18  push    rsi
0x140062d19  push    rdi
0x140062d1a  push    r12
0x140062d1c  push    r13
0x140062d1e  push    r14
0x140062d20  push    r15
0x140062d22  sub     rsp, 60h
0x140062d26  mov     r8d, [rcx+1E8h]
0x140062d2d  xor     eax, eax
0x140062d2f  mov     r13, rdx
0x140062d32  mov     [r11+8], ax
0x140062d37  mov     rdx, [rcx+20h]
0x140062d3b  mov     r14, rcx
0x140062d3e  lea     rcx, TcpToeplitzHashContext
0x140062d45  mov     [r11+0Ah], al
0x140062d49  xor     r9d, r9d
0x140062d4c  call    cs:__imp_RtlComputeToeplitzHash
0x140062d53  nop     dword ptr [rax+rax+00h]
0x140062d58  lea     rdx, [r14+40h]
0x140062d5c  xor     r9d, r9d
0x140062d5f  mov     r8d, 4
0x140062d65  lea     rcx, TcpToeplitzHashContext
0x140062d6c  mov     ebx, eax
0x140062d6e  call    cs:__imp_RtlComputeToeplitzHash
0x140062d75  nop     dword ptr [rax+rax+00h]
0x140062d7a  lea     rdx, [r14+3Eh]
0x140062d7e  xor     r9d, r9d
0x140062d81  mov     edi, eax
0x140062d83  lea     rcx, TcpToeplitzHashContext
0x140062d8a  xor     edi, ebx
0x140062d8c  mov     ebx, 2
0x140062d91  mov     r8d, ebx
0x140062d94  call    cs:__imp_RtlComputeToeplitzHash
0x140062d9b  nop     dword ptr [rax+rax+00h]
0x140062da0  mov     ecx, [r14+28h]
0x140062da4  mov     esi, eax
0x140062da6  xor     esi, edi
0x140062da8  cmp     ecx, 3Ah ; ':'
0x140062dab  jz      loc_140063265
0x140062db1  cmp     ecx, 1
0x140062db4  jz      loc_140063349
0x140062dba  lea     rdx, [r14+1F0h]
0x140062dc1  xor     r9d, r9d
0x140062dc4  mov     r8d, 8
0x140062dca  lea     rcx, TcpToeplitzHashContext
0x140062dd1  call    cs:__imp_RtlComputeToeplitzHash
0x140062dd8  nop     dword ptr [rax+rax+00h]
0x140062ddd  mov     rcx, cs:pRemoteEndpointTable
0x140062de4  mov     ebx, eax
0x140062de6  mov     eax, esi
0x140062de8  xor     rbx, rax
0x140062deb  mov     eax, 80000000h
0x140062df0  mov     r15d, [rcx+8]
0x140062df4  or      rbx, rax
0x140062df7  mov     ebp, ebx
0x140062df9  and     ebp, r15d
0x140062dfc  mov     edi, ebp
0x140062dfe  shl     rdi, 7
0x140062e02  add     rdi, rcx
0x140062e05  call    cs:__imp_KeGetCurrentIrql
0x140062e0c  nop     dword ptr [rax+rax+00h]
0x140062e11  mov     rcx, [rdi+40h]; Lock
0x140062e15  lea     rdx, [rsp+98h+LockState]; LockState
0x140062e1d  xor     r8d, r8d; Flags
0x140062e20  movzx   esi, al
0x140062e23  call    cs:__imp_NdisAcquireRWLockRead
0x140062e2a  nop     dword ptr [rax+rax+00h]
0x140062e2f  cmp     sil, 2
0x140062e33  jz      short loc_140062E72
0x140062e35  cmp     cs:gWfpPerProContext, 0
0x140062e3d  jz      short loc_140062E72
0x140062e3f  xor     ecx, ecx; ProcNumber
0x140062e41  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140062e48  nop     dword ptr [rax+rax+00h]
0x140062e4d  lea     ecx, [rax+rax*8]
0x140062e50  mov     rax, cs:gWfpPerProContext
0x140062e57  shl     ecx, 3
0x140062e5a  mov     rcx, [rcx+rax]
0x140062e5e  mov     rax, ds:0FFFFF78000000008h
0x140062e68  mov     [rcx+8], rax
0x140062e6c  mov     dword ptr [rcx], 4
0x140062e72  mov     rcx, cs:pRemoteEndpointTable
0x140062e79  cmp     r15d, [rcx+8]
0x140062e7d  jz      loc_140062F6F
0x140062e83  mov     edi, ebp
0x140062e85  shl     rdi, 7
0x140062e89  add     rdi, rcx
0x140062e8c  cmp     cs:gWfpPerProContext, 0
0x140062e94  jz      short loc_140062EC0
0x140062e96  xor     ecx, ecx; ProcNumber
0x140062e98  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140062e9f  nop     dword ptr [rax+rax+00h]
0x140062ea4  lea     edx, [rax+rax*8]
0x140062ea7  mov     rax, cs:gWfpPerProContext
0x140062eae  shl     edx, 3
0x140062eb1  mov     rdx, [rdx+rax]
0x140062eb5  cmp     dword ptr [rdx], 4
0x140062eb8  jnz     short loc_140062EC0
0x140062eba  mov     dword ptr [rdx], 0
0x140062ec0  mov     rcx, [rdi+40h]; Lock
0x140062ec4  lea     rdx, [rsp+98h+LockState]; LockState
0x140062ecc  call    cs:__imp_NdisReleaseRWLock
0x140062ed3  nop     dword ptr [rax+rax+00h]
0x140062ed8  mov     rcx, cs:pRemoteEndpointTable
0x140062edf  mov     ebp, ebx
0x140062ee1  mov     r15d, [rcx+8]
0x140062ee5  and     ebp, r15d
0x140062ee8  mov     edi, ebp
0x140062eea  shl     rdi, 7
0x140062eee  add     rdi, rcx
0x140062ef1  call    cs:__imp_KeGetCurrentIrql
0x140062ef8  nop     dword ptr [rax+rax+00h]
0x140062efd  mov     rcx, [rdi+40h]; Lock
0x140062f01  lea     rdx, [rsp+98h+LockState]; LockState
0x140062f09  xor     r8d, r8d; Flags
0x140062f0c  movzx   esi, al
0x140062f0f  call    cs:__imp_NdisAcquireRWLockRead
0x140062f16  nop     dword ptr [rax+rax+00h]
0x140062f1b  cmp     sil, 2
0x140062f1f  jz      short loc_140062F5E
0x140062f21  cmp     cs:gWfpPerProContext, 0
0x140062f29  jz      short loc_140062F5E
0x140062f2b  xor     ecx, ecx; ProcNumber
0x140062f2d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140062f34  nop     dword ptr [rax+rax+00h]
0x140062f39  lea     ecx, [rax+rax*8]
0x140062f3c  mov     rax, cs:gWfpPerProContext
0x140062f43  shl     ecx, 3
0x140062f46  mov     rcx, [rcx+rax]
0x140062f4a  mov     rax, ds:0FFFFF78000000008h
0x140062f54  mov     [rcx+8], rax
0x140062f58  mov     dword ptr [rcx], 4
0x140062f5e  mov     rcx, cs:pRemoteEndpointTable
0x140062f65  cmp     r15d, [rcx+8]
0x140062f69  jnz     loc_140062E83
0x140062f6f  add     rcx, 48h ; 'H'
0x140062f73  mov     r15d, ebp
0x140062f76  shl     r15, 7
0x140062f7a  lea     r8, [rsp+98h+Context]; Context
0x140062f7f  xorps   xmm0, xmm0
0x140062f82  mov     r12d, ebp
0x140062f85  xor     eax, eax
0x140062f87  add     rcx, r15; HashTable
0x140062f8a  xor     edi, edi
0x140062f8c  mov     [rsp+98h+Context.Signature], rax
0x140062f91  mov     rdx, rbx; Signature
0x140062f94  movups  xmmword ptr [rsp+98h+Context.ChainHead], xmm0
0x140062f99  call    cs:__imp_RtlLookupEntryHashTable
0x140062fa0  nop     dword ptr [rax+rax+00h]
0x140062fa5  test    rax, rax
0x140062fa8  jz      short loc_140062FC7
0x140062faa  lea     r11, [rax-240h]
0x140062fb1  mov     rdx, r14
0x140062fb4  mov     rcx, r11
0x140062fb7  call    WfpAlepIsSameEndpoint
0x140062fbc  test    al, al
0x140062fbe  jz      loc_140063239
0x140062fc4  mov     rdi, r11
0x140062fc7  mov     rbx, 0FFFFF78000000008h
0x140062fd1  mov     r14, 346DC5D63886594Bh
0x140062fdb  mov     rax, r14
0x140062fde  mov     rcx, [rbx]
0x140062fe1  mul     rcx
0x140062fe4  mov     rax, cs:pRemoteEndpointTable
0x140062feb  mov     rcx, rdx
0x140062fee  shr     rcx, 0Bh
0x140062ff2  sub     rcx, [r15+rax+80h]
0x140062ffa  mov     rax, 624DD2F1A9FBE77h
0x140063004  mul     rcx
0x140063007  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x14006300e  sub     rcx, rdx
0x140063011  shr     rcx, 1
0x140063014  add     rcx, rdx
0x140063017  lea     rdx, LruDpcThreshold
0x14006301e  movzx   eax, word ptr [rdx+rax*2]
0x140063022  shr     rcx, 9
0x140063026  cmp     ecx, eax
0x140063028  jbe     short loc_140063052
0x14006302a  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+2, 8
0x140063031  jnz     loc_1400631AF
0x140063037  mov     r8, r12; SystemArgument2
0x14006303a  lea     rcx, LruCleanupDpc; Dpc
0x140063041  mov     edx, 1; SystemArgument1
0x140063046  call    cs:__imp_KeInsertQueueDpc
0x14006304d  nop     dword ptr [rax+rax+00h]
0x140063052  test    rdi, rdi
0x140063055  jz      loc_14006313F
0x14006305b  cmp     cs:gAleDebugEnabled, 0
0x140063062  jz      short loc_14006307E
0x140063064  mov     rax, [rdi+98h]
0x14006306b  mov     rcx, 0BADBADFABADBADFAh
0x140063075  cmp     rax, rcx
0x140063078  jz      short loc_14006307E
0x14006307a  lock inc dword ptr [rax+10h]
0x14006307e  lea     rax, [rdi+80h]
0x140063085  mov     [rsp+98h+arg_10], rax
0x14006308d  mov     rax, [rsp+98h+arg_10]
0x140063095  mov     [rsp+98h+arg_10], rax
0x14006309d  mov     rax, [rsp+98h+arg_10]
0x1400630a5  movzx   r9d, byte ptr [rax+5]
0x1400630aa  mov     rcx, [rsp+98h+arg_10]
0x1400630b2  mov     ecx, [rcx]
0x1400630b4  test    cl, 2
0x1400630b7  jnz     loc_1400632F0
0x1400630bd  test    cl, 1
0x1400630c0  jz      loc_1400632E2
0x1400630c6  mov     rdx, [rsp+98h+arg_10]
0x1400630ce  lea     r8d, [rcx+4]
0x1400630d2  mov     eax, ecx
0x1400630d4  lock cmpxchg [rdx], r8d
0x1400630d9  cmp     ecx, eax
0x1400630db  jnz     short loc_1400630AA
0x1400630dd  mov     eax, [rdi+30h]
0x1400630e0  bt      eax, 1Eh
0x1400630e4  jb      loc_14006325D
0x1400630ea  mov     eax, [rdi+118h]
0x1400630f0  test    al, 1
0x1400630f2  jnz     loc_14006325D
0x1400630f8  mov     eax, [rdi+0C8h]
0x1400630fe  test    al, 4
0x140063100  jnz     loc_14006325D
0x140063106  mov     ecx, [rdi+30h]
0x140063109  and     ecx, 0C000h
0x14006310f  cmp     ecx, 0C000h
0x140063115  jz      loc_14006325D
0x14006311b  mov     ecx, [rdi+30h]
0x14006311e  mov     r8b, 1
0x140063121  bt      ecx, 0Fh
0x140063125  jb      short loc_14006313B
0x140063127  mov     rcx, [rbx]
0x14006312a  mov     rax, r14
0x14006312d  mul     rcx
0x140063130  shr     rdx, 0Bh
0x140063134  xchg    rdx, [rdi+220h]
0x14006313b  mov     [r13+0], r8b
0x14006313f  cmp     cs:gWfpPerProContext, 0
0x140063147  mov     rbx, cs:pRemoteEndpointTable
0x14006314e  jz      short loc_14006317A
0x140063150  xor     ecx, ecx; ProcNumber
0x140063152  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140063159  nop     dword ptr [rax+rax+00h]
0x14006315e  lea     edx, [rax+rax*8]
0x140063161  mov     rax, cs:gWfpPerProContext
0x140063168  shl     edx, 3
0x14006316b  mov     rdx, [rdx+rax]
0x14006316f  cmp     dword ptr [rdx], 4
0x140063172  jnz     short loc_14006317A
0x140063174  mov     dword ptr [rdx], 0
0x14006317a  mov     rcx, [rbx+r15+40h]; Lock
0x14006317f  lea     rdx, [rsp+98h+LockState]; LockState
0x140063187  call    cs:__imp_NdisReleaseRWLock
0x14006318e  nop     dword ptr [rax+rax+00h]
0x140063193  mov     rbx, [rsp+98h+arg_8]
0x14006319b  mov     rax, rdi
0x14006319e  add     rsp, 60h
0x1400631a2  pop     r15
0x1400631a4  pop     r14
0x1400631a6  pop     r13
0x1400631a8  pop     r12
0x1400631aa  pop     rdi
0x1400631ab  pop     rsi
0x1400631ac  pop     rbp
0x1400631ad  retn
0x1400631af  mov     rcx, cs:LowNonPagedPoolEvent; Event
0x1400631b6  call    cs:__imp_KeReadStateEvent
0x1400631bd  nop     dword ptr [rax+rax+00h]
0x1400631c2  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+18h; Event
0x1400631c9  mov     ebp, eax
0x1400631cb  call    cs:__imp_KeReadStateEvent
0x1400631d2  nop     dword ptr [rax+rax+00h]
0x1400631d7  mov     rcx, cs:HighNonPagedPoolEvent; Event
0x1400631de  mov     esi, eax
0x1400631e0  call    cs:__imp_KeReadStateEvent
0x1400631e7  nop     dword ptr [rax+rax+00h]
0x1400631ec  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h; Event
0x1400631f3  mov     ebx, eax
0x1400631f5  call    cs:__imp_KeReadStateEvent
0x1400631fc  nop     dword ptr [rax+rax+00h]
0x140063201  mov     [rsp+98h+var_68], ebp
0x140063205  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x14006320c  mov     r9d, eax
0x14006320f  mov     [rsp+98h+var_70], esi
0x140063213  lea     rdx, DPC_CLEANUP
0x14006321a  mov     [rsp+98h+var_78], ebx
0x14006321e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140063225  call    McTemplateK0qqqq_EtwWriteTransfer
0x14006322a  mov     rbx, 0FFFFF78000000008h
0x140063234  jmp     loc_140063037
0x140063239  mov     rcx, cs:pRemoteEndpointTable
0x140063240  lea     rdx, [rsp+98h+Context]; Context
0x140063245  add     rcx, 48h ; 'H'
0x140063249  add     rcx, r15; HashTable
0x14006324c  call    cs:__imp_RtlGetNextEntryHashTable
0x140063253  nop     dword ptr [rax+rax+00h]
0x140063258  jmp     loc_140062FA5
0x14006325d  xor     r8b, r8b
0x140063260  jmp     loc_14006313B
  ... truncated ...
```
