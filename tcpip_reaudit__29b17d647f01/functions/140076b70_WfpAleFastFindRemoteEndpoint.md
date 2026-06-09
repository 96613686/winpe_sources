# WfpAleFastFindRemoteEndpoint

- ea: `0x140076b70`
- end: `0x1400771d9`
- name: `WfpAleFastFindRemoteEndpoint`
- size: `1641`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140097800`

## callees

- `0x140076b70`
- `0x1400773a8`
- `0x140077580`
- `0x14008b220`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400770ac`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1400770ac`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140076df9`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140076df9`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076ca1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076cf8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076d8d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076fb2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076ca1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076cf8`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076d8d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140076fb2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076c65`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076d51`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076c65`
- `ntoskrnl!KeGetCurrentIrql` at `0x140076d51`
- `ntoskrnl!KeReadStateEvent` at `0x140077016`
- `ntoskrnl!KeReadStateEvent` at `0x14007702b`
- `ntoskrnl!KeReadStateEvent` at `0x140077040`
- `ntoskrnl!KeReadStateEvent` at `0x140077055`
- `ntoskrnl!KeReadStateEvent` at `0x140077016`
- `ntoskrnl!KeReadStateEvent` at `0x14007702b`
- `ntoskrnl!KeReadStateEvent` at `0x140077040`
- `ntoskrnl!KeReadStateEvent` at `0x140077055`
- `ntoskrnl!KeInsertQueueDpc` at `0x140076ea6`
- `ntoskrnl!KeInsertQueueDpc` at `0x140076ea6`
- `NETIO!RtlComputeToeplitzHash` at `0x140076bac`
- `NETIO!RtlComputeToeplitzHash` at `0x140076bce`
- `NETIO!RtlComputeToeplitzHash` at `0x140076bf4`
- `NETIO!RtlComputeToeplitzHash` at `0x140076c31`
- `NETIO!RtlComputeToeplitzHash` at `0x140077106`
- `NETIO!RtlComputeToeplitzHash` at `0x14007712d`
- `NETIO!RtlComputeToeplitzHash` at `0x140076bac`
- `NETIO!RtlComputeToeplitzHash` at `0x140076bce`
- `NETIO!RtlComputeToeplitzHash` at `0x140076bf4`
- `NETIO!RtlComputeToeplitzHash` at `0x140076c31`
- `NETIO!RtlComputeToeplitzHash` at `0x140077106`
- `NETIO!RtlComputeToeplitzHash` at `0x14007712d`
- `NDIS!NdisAcquireRWLockRead` at `0x140076c83`
- `NDIS!NdisAcquireRWLockRead` at `0x140076d6f`
- `NDIS!NdisAcquireRWLockRead` at `0x140076c83`
- `NDIS!NdisAcquireRWLockRead` at `0x140076d6f`
- `NDIS!NdisReleaseRWLock` at `0x140076d2c`
- `NDIS!NdisReleaseRWLock` at `0x140076fe7`
- `NDIS!NdisReleaseRWLock` at `0x140076d2c`
- `NDIS!NdisReleaseRWLock` at `0x140076fe7`

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
      v38 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters);
      v39 = KeReadStateEvent(*(PRKEVENT *)&WPP_MAIN_CB.DeviceType);
      v40 = KeReadStateEvent((PRKEVENT)WPP_MAIN_CB.Dpc.DeferredRoutine);
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
0x140076b70  mov     r11, rsp
0x140076b73  mov     [r11+10h], rbx
0x140076b77  push    rbp
0x140076b78  push    rsi
0x140076b79  push    rdi
0x140076b7a  push    r12
0x140076b7c  push    r13
0x140076b7e  push    r14
0x140076b80  push    r15
0x140076b82  sub     rsp, 60h
0x140076b86  mov     r8d, [rcx+1E8h]
0x140076b8d  xor     eax, eax
0x140076b8f  mov     r13, rdx
0x140076b92  mov     [r11+8], ax
0x140076b97  mov     rdx, [rcx+20h]
0x140076b9b  mov     r14, rcx
0x140076b9e  lea     rcx, TcpToeplitzHashContext
0x140076ba5  mov     [r11+0Ah], al
0x140076ba9  xor     r9d, r9d
0x140076bac  call    cs:__imp_RtlComputeToeplitzHash
0x140076bb3  nop     dword ptr [rax+rax+00h]
0x140076bb8  lea     rdx, [r14+40h]
0x140076bbc  xor     r9d, r9d
0x140076bbf  mov     r8d, 4
0x140076bc5  lea     rcx, TcpToeplitzHashContext
0x140076bcc  mov     ebx, eax
0x140076bce  call    cs:__imp_RtlComputeToeplitzHash
0x140076bd5  nop     dword ptr [rax+rax+00h]
0x140076bda  lea     rdx, [r14+3Eh]
0x140076bde  xor     r9d, r9d
0x140076be1  mov     edi, eax
0x140076be3  lea     rcx, TcpToeplitzHashContext
0x140076bea  xor     edi, ebx
0x140076bec  mov     ebx, 2
0x140076bf1  mov     r8d, ebx
0x140076bf4  call    cs:__imp_RtlComputeToeplitzHash
0x140076bfb  nop     dword ptr [rax+rax+00h]
0x140076c00  mov     ecx, [r14+28h]
0x140076c04  mov     esi, eax
0x140076c06  xor     esi, edi
0x140076c08  cmp     ecx, 3Ah ; ':'
0x140076c0b  jz      loc_1400770C5
0x140076c11  cmp     ecx, 1
0x140076c14  jz      loc_1400771A9
0x140076c1a  lea     rdx, [r14+1F0h]
0x140076c21  xor     r9d, r9d
0x140076c24  mov     r8d, 8
0x140076c2a  lea     rcx, TcpToeplitzHashContext
0x140076c31  call    cs:__imp_RtlComputeToeplitzHash
0x140076c38  nop     dword ptr [rax+rax+00h]
0x140076c3d  mov     rcx, cs:pRemoteEndpointTable
0x140076c44  mov     ebx, eax
0x140076c46  mov     eax, esi
0x140076c48  xor     rbx, rax
0x140076c4b  mov     eax, 80000000h
0x140076c50  mov     r15d, [rcx+8]
0x140076c54  or      rbx, rax
0x140076c57  mov     ebp, ebx
0x140076c59  and     ebp, r15d
0x140076c5c  mov     edi, ebp
0x140076c5e  shl     rdi, 7
0x140076c62  add     rdi, rcx
0x140076c65  call    cs:__imp_KeGetCurrentIrql
0x140076c6c  nop     dword ptr [rax+rax+00h]
0x140076c71  mov     rcx, [rdi+40h]; Lock
0x140076c75  lea     rdx, [rsp+98h+LockState]; LockState
0x140076c7d  xor     r8d, r8d; Flags
0x140076c80  movzx   esi, al
0x140076c83  call    cs:__imp_NdisAcquireRWLockRead
0x140076c8a  nop     dword ptr [rax+rax+00h]
0x140076c8f  cmp     sil, 2
0x140076c93  jz      short loc_140076CD2
0x140076c95  cmp     cs:gWfpPerProContext, 0
0x140076c9d  jz      short loc_140076CD2
0x140076c9f  xor     ecx, ecx; ProcNumber
0x140076ca1  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076ca8  nop     dword ptr [rax+rax+00h]
0x140076cad  lea     ecx, [rax+rax*8]
0x140076cb0  mov     rax, cs:gWfpPerProContext
0x140076cb7  shl     ecx, 3
0x140076cba  mov     rcx, [rcx+rax]
0x140076cbe  mov     rax, ds:0FFFFF78000000008h
0x140076cc8  mov     [rcx+8], rax
0x140076ccc  mov     dword ptr [rcx], 4
0x140076cd2  mov     rcx, cs:pRemoteEndpointTable
0x140076cd9  cmp     r15d, [rcx+8]
0x140076cdd  jz      loc_140076DCF
0x140076ce3  mov     edi, ebp
0x140076ce5  shl     rdi, 7
0x140076ce9  add     rdi, rcx
0x140076cec  cmp     cs:gWfpPerProContext, 0
0x140076cf4  jz      short loc_140076D20
0x140076cf6  xor     ecx, ecx; ProcNumber
0x140076cf8  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076cff  nop     dword ptr [rax+rax+00h]
0x140076d04  lea     edx, [rax+rax*8]
0x140076d07  mov     rax, cs:gWfpPerProContext
0x140076d0e  shl     edx, 3
0x140076d11  mov     rdx, [rdx+rax]
0x140076d15  cmp     dword ptr [rdx], 4
0x140076d18  jnz     short loc_140076D20
0x140076d1a  mov     dword ptr [rdx], 0
0x140076d20  mov     rcx, [rdi+40h]; Lock
0x140076d24  lea     rdx, [rsp+98h+LockState]; LockState
0x140076d2c  call    cs:__imp_NdisReleaseRWLock
0x140076d33  nop     dword ptr [rax+rax+00h]
0x140076d38  mov     rcx, cs:pRemoteEndpointTable
0x140076d3f  mov     ebp, ebx
0x140076d41  mov     r15d, [rcx+8]
0x140076d45  and     ebp, r15d
0x140076d48  mov     edi, ebp
0x140076d4a  shl     rdi, 7
0x140076d4e  add     rdi, rcx
0x140076d51  call    cs:__imp_KeGetCurrentIrql
0x140076d58  nop     dword ptr [rax+rax+00h]
0x140076d5d  mov     rcx, [rdi+40h]; Lock
0x140076d61  lea     rdx, [rsp+98h+LockState]; LockState
0x140076d69  xor     r8d, r8d; Flags
0x140076d6c  movzx   esi, al
0x140076d6f  call    cs:__imp_NdisAcquireRWLockRead
0x140076d76  nop     dword ptr [rax+rax+00h]
0x140076d7b  cmp     sil, 2
0x140076d7f  jz      short loc_140076DBE
0x140076d81  cmp     cs:gWfpPerProContext, 0
0x140076d89  jz      short loc_140076DBE
0x140076d8b  xor     ecx, ecx; ProcNumber
0x140076d8d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076d94  nop     dword ptr [rax+rax+00h]
0x140076d99  lea     ecx, [rax+rax*8]
0x140076d9c  mov     rax, cs:gWfpPerProContext
0x140076da3  shl     ecx, 3
0x140076da6  mov     rcx, [rcx+rax]
0x140076daa  mov     rax, ds:0FFFFF78000000008h
0x140076db4  mov     [rcx+8], rax
0x140076db8  mov     dword ptr [rcx], 4
0x140076dbe  mov     rcx, cs:pRemoteEndpointTable
0x140076dc5  cmp     r15d, [rcx+8]
0x140076dc9  jnz     loc_140076CE3
0x140076dcf  add     rcx, 48h ; 'H'
0x140076dd3  mov     r15d, ebp
0x140076dd6  shl     r15, 7
0x140076dda  lea     r8, [rsp+98h+Context]; Context
0x140076ddf  xorps   xmm0, xmm0
0x140076de2  mov     r12d, ebp
0x140076de5  xor     eax, eax
0x140076de7  add     rcx, r15; HashTable
0x140076dea  xor     edi, edi
0x140076dec  mov     [rsp+98h+Context.Signature], rax
0x140076df1  mov     rdx, rbx; Signature
0x140076df4  movups  xmmword ptr [rsp+98h+Context.ChainHead], xmm0
0x140076df9  call    cs:__imp_RtlLookupEntryHashTable
0x140076e00  nop     dword ptr [rax+rax+00h]
0x140076e05  test    rax, rax
0x140076e08  jz      short loc_140076E27
0x140076e0a  lea     r11, [rax-240h]
0x140076e11  mov     rdx, r14
0x140076e14  mov     rcx, r11
0x140076e17  call    WfpAlepIsSameEndpoint
0x140076e1c  test    al, al
0x140076e1e  jz      loc_140077099
0x140076e24  mov     rdi, r11
0x140076e27  mov     rbx, 0FFFFF78000000008h
0x140076e31  mov     r14, 346DC5D63886594Bh
0x140076e3b  mov     rax, r14
0x140076e3e  mov     rcx, [rbx]
0x140076e41  mul     rcx
0x140076e44  mov     rax, cs:pRemoteEndpointTable
0x140076e4b  mov     rcx, rdx
0x140076e4e  shr     rcx, 0Bh
0x140076e52  sub     rcx, [r15+rax+80h]
0x140076e5a  mov     rax, 624DD2F1A9FBE77h
0x140076e64  mul     rcx
0x140076e67  movsxd  rax, cs:CurrentLifeTimeThresholdIndex
0x140076e6e  sub     rcx, rdx
0x140076e71  shr     rcx, 1
0x140076e74  add     rcx, rdx
0x140076e77  lea     rdx, LruDpcThreshold
0x140076e7e  movzx   eax, word ptr [rdx+rax*2]
0x140076e82  shr     rcx, 9
0x140076e86  cmp     ecx, eax
0x140076e88  jbe     short loc_140076EB2
0x140076e8a  test    byte ptr cs:WPP_MAIN_CB+14Ah, 8
0x140076e91  jnz     loc_14007700F
0x140076e97  mov     r8, r12; SystemArgument2
0x140076e9a  lea     rcx, LruCleanupDpc; Dpc
0x140076ea1  mov     edx, 1; SystemArgument1
0x140076ea6  call    cs:__imp_KeInsertQueueDpc
0x140076ead  nop     dword ptr [rax+rax+00h]
0x140076eb2  test    rdi, rdi
0x140076eb5  jz      loc_140076F9F
0x140076ebb  cmp     cs:gAleDebugEnabled, 0
0x140076ec2  jz      short loc_140076EDE
0x140076ec4  mov     rax, [rdi+98h]
0x140076ecb  mov     rcx, 0BADBADFABADBADFAh
0x140076ed5  cmp     rax, rcx
0x140076ed8  jz      short loc_140076EDE
0x140076eda  lock inc dword ptr [rax+10h]
0x140076ede  lea     rax, [rdi+80h]
0x140076ee5  mov     [rsp+98h+arg_10], rax
0x140076eed  mov     rax, [rsp+98h+arg_10]
0x140076ef5  mov     [rsp+98h+arg_10], rax
0x140076efd  mov     rax, [rsp+98h+arg_10]
0x140076f05  movzx   r9d, byte ptr [rax+5]
0x140076f0a  mov     rcx, [rsp+98h+arg_10]
0x140076f12  mov     ecx, [rcx]
0x140076f14  test    cl, 2
0x140076f17  jnz     loc_140077150
0x140076f1d  test    cl, 1
0x140076f20  jz      loc_140077142
0x140076f26  mov     rdx, [rsp+98h+arg_10]
0x140076f2e  lea     r8d, [rcx+4]
0x140076f32  mov     eax, ecx
0x140076f34  lock cmpxchg [rdx], r8d
0x140076f39  cmp     ecx, eax
0x140076f3b  jnz     short loc_140076F0A
0x140076f3d  mov     eax, [rdi+30h]
0x140076f40  bt      eax, 1Eh
0x140076f44  jb      loc_1400770BD
0x140076f4a  mov     eax, [rdi+118h]
0x140076f50  test    al, 1
0x140076f52  jnz     loc_1400770BD
0x140076f58  mov     eax, [rdi+0C8h]
0x140076f5e  test    al, 4
0x140076f60  jnz     loc_1400770BD
0x140076f66  mov     ecx, [rdi+30h]
0x140076f69  and     ecx, 0C000h
0x140076f6f  cmp     ecx, 0C000h
0x140076f75  jz      loc_1400770BD
0x140076f7b  mov     ecx, [rdi+30h]
0x140076f7e  mov     r8b, 1
0x140076f81  bt      ecx, 0Fh
0x140076f85  jb      short loc_140076F9B
0x140076f87  mov     rcx, [rbx]
0x140076f8a  mov     rax, r14
0x140076f8d  mul     rcx
0x140076f90  shr     rdx, 0Bh
0x140076f94  xchg    rdx, [rdi+220h]
0x140076f9b  mov     [r13+0], r8b
0x140076f9f  cmp     cs:gWfpPerProContext, 0
0x140076fa7  mov     rbx, cs:pRemoteEndpointTable
0x140076fae  jz      short loc_140076FDA
0x140076fb0  xor     ecx, ecx; ProcNumber
0x140076fb2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140076fb9  nop     dword ptr [rax+rax+00h]
0x140076fbe  lea     edx, [rax+rax*8]
0x140076fc1  mov     rax, cs:gWfpPerProContext
0x140076fc8  shl     edx, 3
0x140076fcb  mov     rdx, [rdx+rax]
0x140076fcf  cmp     dword ptr [rdx], 4
0x140076fd2  jnz     short loc_140076FDA
0x140076fd4  mov     dword ptr [rdx], 0
0x140076fda  mov     rcx, [rbx+r15+40h]; Lock
0x140076fdf  lea     rdx, [rsp+98h+LockState]; LockState
0x140076fe7  call    cs:__imp_NdisReleaseRWLock
0x140076fee  nop     dword ptr [rax+rax+00h]
0x140076ff3  mov     rbx, [rsp+98h+arg_8]
0x140076ffb  mov     rax, rdi
0x140076ffe  add     rsp, 60h
0x140077002  pop     r15
0x140077004  pop     r14
0x140077006  pop     r13
0x140077008  pop     r12
0x14007700a  pop     rdi
0x14007700b  pop     rsi
0x14007700c  pop     rbp
0x14007700d  retn
0x14007700f  mov     rcx, cs:LowNonPagedPoolEvent; Event
0x140077016  call    cs:__imp_KeReadStateEvent
0x14007701d  nop     dword ptr [rax+rax+00h]
0x140077022  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+28h; Event
0x140077029  mov     ebp, eax
0x14007702b  call    cs:__imp_KeReadStateEvent
0x140077032  nop     dword ptr [rax+rax+00h]
0x140077037  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; Event
0x14007703e  mov     esi, eax
0x140077040  call    cs:__imp_KeReadStateEvent
0x140077047  nop     dword ptr [rax+rax+00h]
0x14007704c  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine; Event
0x140077053  mov     ebx, eax
0x140077055  call    cs:__imp_KeReadStateEvent
0x14007705c  nop     dword ptr [rax+rax+00h]
0x140077061  mov     [rsp+98h+var_68], ebp
0x140077065  lea     r8, MICROSOFT_TCPIP_PROVIDER
0x14007706c  mov     r9d, eax
0x14007706f  mov     [rsp+98h+var_70], esi
0x140077073  lea     rdx, DPC_CLEANUP
0x14007707a  mov     [rsp+98h+var_78], ebx
0x14007707e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140077085  call    McTemplateK0qqqq_EtwWriteTransfer
0x14007708a  mov     rbx, 0FFFFF78000000008h
0x140077094  jmp     loc_140076E97
0x140077099  mov     rcx, cs:pRemoteEndpointTable
0x1400770a0  lea     rdx, [rsp+98h+Context]; Context
0x1400770a5  add     rcx, 48h ; 'H'
0x1400770a9  add     rcx, r15; HashTable
0x1400770ac  call    cs:__imp_RtlGetNextEntryHashTable
0x1400770b3  nop     dword ptr [rax+rax+00h]
0x1400770b8  jmp     loc_140076E05
0x1400770bd  xor     r8b, r8b
0x1400770c0  jmp     loc_140076F9B
  ... truncated ...
```
