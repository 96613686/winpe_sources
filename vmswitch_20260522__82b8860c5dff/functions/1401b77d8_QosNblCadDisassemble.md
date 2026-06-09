# QosNblCadDisassemble

- ea: `0x1401b77d8`
- end: `0x1401b7a9f`
- name: `QosNblCadDisassemble`
- size: `711`
- prototype: `__int64 __usercall@<rax>(PNET_BUFFER_LIST SrcNetBufferList@<rcx>, int, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1401b7d18`

## callees

- `0x140099f04`
- `0x1401b77b0`
- `0x1401b77d8`
- `0x1401b7bfc`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1401b7a02`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1401b7a02`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1401b7a63`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1401b7a63`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401b7a78`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401b7a78`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401b7a10`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401b7a10`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401b794a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401b794a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401b7829`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401b7829`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b785f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b785f`
- `NDIS!NdisFreeNetBufferList` at `0x1401b796d`
- `NDIS!NdisFreeNetBufferList` at `0x1401b796d`
- `NDIS!NdisAllocateNetBufferList` at `0x1401b78b1`
- `NDIS!NdisAllocateNetBufferList` at `0x1401b78b1`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1401b78cb`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1401b78cb`

## pseudocode

```c
__int64 __fastcall QosNblCadDisassemble(
        PNET_BUFFER_LIST SrcNetBufferList,
        __int64 a2,
        unsigned int a3,
        int a4,
        int a5,
        __int64 *a6,
        char a7)
{
  struct _NPAGED_LOOKASIDE_LIST *v9; // rcx
  __int64 v11; // r13
  KSPIN_LOCK *v12; // rax
  KSPIN_LOCK *v13; // rdi
  unsigned int v14; // ebx
  int NetBufferCount; // eax
  int v16; // edx
  unsigned int v17; // r14d
  int v18; // eax
  unsigned int i; // r12d
  struct _NET_BUFFER_LIST *NetBufferList; // rax
  struct _NET_BUFFER_LIST *v21; // r13
  _NET_BUFFER_LIST_CONTEXT *Context; // rcx
  __int64 v23; // rbx
  __int64 v24; // rdx
  struct _NET_BUFFER_LIST *v25; // rax
  __int64 v26; // rdx
  _QWORD *v27; // r8
  unsigned int v28; // eax
  _QWORD *j; // rcx
  _QWORD *v30; // rdx
  _QWORD *v31; // rax
  KSPIN_LOCK *v32; // rcx
  _QWORD *v33; // r8
  char *v34; // rdi
  char **v35; // r9
  char *v36; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-58h] BYREF

  v9 = QosgNblCadLookasideList;
  *(_OWORD *)a6 = 0;
  a6[2] = 0;
  v11 = a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v12 = (KSPIN_LOCK *)ExAllocateFromNPagedLookasideList(v9);
  v13 = v12;
  if ( v12 )
  {
    *(_OWORD *)v12 = 0;
    *((_OWORD *)v12 + 1) = 0;
    *((_OWORD *)v12 + 2) = 0;
    v12[6] = 0;
    KeInitializeSpinLock(v12 + 2);
    v13[5] = (KSPIN_LOCK)(v13 + 4);
    v13[4] = (KSPIN_LOCK)(v13 + 4);
    v13[3] = (KSPIN_LOCK)SrcNetBufferList;
    NetBufferCount = QosGetNetBufferCount(SrcNetBufferList, 0);
    v17 = v16 + 1;
    v18 = NetBufferCount - a3;
    if ( v18 )
    {
      v17 = a4 + 1;
      if ( a4 == -1 )
        v17 = v18 + 1;
    }
    for ( i = 0; i < v17; ++i )
    {
      NetBufferList = NdisAllocateNetBufferList(*(NDIS_HANDLE *)(v11 + 40), 0x70u, 0);
      v21 = NetBufferList;
      if ( !NetBufferList )
      {
        v14 = -1073741670;
        ExFreeToNPagedLookasideList(QosgNblCadLookasideList, v13);
        goto LABEL_11;
      }
      NdisCopySendNetBufferListInfo(NetBufferList, SrcNetBufferList);
      Context = v21->Context;
      v21->SourceHandle = *(void **)(a2 + 32);
      v23 = (__int64)Context + Context->Offset;
      memset((void *)(v23 + 16), 0, 0x70u);
      v24 = a6[1];
      *(_QWORD *)(v23 + 48) = a2;
      *(_QWORD *)(v23 + 32) = v13;
      *(_QWORD *)(v23 + 40) = v21;
      *(_DWORD *)(v23 + 56) = 0;
      QosNblChainInsert(a6, v24, v21);
      v11 = a2;
    }
    v26 = *a6;
    v27 = 0;
    *(_QWORD *)(v26 + 8) = SrcNetBufferList->FirstNetBuffer;
    v28 = 0;
    SrcNetBufferList->Link.Region = 0;
    for ( j = *(_QWORD **)(v26 + 8); v28 < a3; j = (_QWORD *)*j )
    {
      ++v28;
      v27 = j;
    }
    *v27 = 0;
    v30 = *(_QWORD **)v26;
    if ( v30 )
    {
      if ( a4 == 1 )
      {
        v30[1] = j;
      }
      else if ( j )
      {
        do
        {
          v31 = (_QWORD *)*j;
          v30[1] = j;
          *j = 0;
          j = v31;
          v30 = (_QWORD *)*v30;
        }
        while ( v31 );
      }
    }
    else
    {
      SrcNetBufferList->Link.Region = (unsigned __int64)j;
    }
    _InterlockedAdd((volatile signed __int32 *)v13 + 12, *((_DWORD *)a6 + 4));
    v32 = v13 + 2;
    if ( a7 )
      KeAcquireInStackQueuedSpinLockAtDpcLevel(v32, &LockHandle);
    else
      KeAcquireInStackQueuedSpinLock(v32, &LockHandle);
    v33 = (_QWORD *)*a6;
    if ( *a6 )
    {
      v34 = (char *)(v13 + 4);
      do
      {
        v35 = (char **)*((_QWORD *)v34 + 1);
        if ( *v35 != v34 )
          __fastfail(3u);
        v36 = (char *)(*(unsigned __int16 *)(v33[2] + 10LL) + v33[2] + 16LL);
        *(_QWORD *)v36 = v34;
        *((_QWORD *)v36 + 1) = v35;
        *v35 = v36;
        *((_QWORD *)v34 + 1) = v36;
        v33 = (_QWORD *)*v33;
      }
      while ( v33 );
    }
    v14 = 0;
    if ( a7 )
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    else
      KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  else
  {
    v14 = -1073741670;
LABEL_11:
    while ( *a6 )
    {
      v25 = (struct _NET_BUFFER_LIST *)QosNblChainRemove(a6);
      NdisFreeNetBufferList(v25);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x1401b77d8  mov     r11, rsp
0x1401b77db  mov     [r11+8], rbx
0x1401b77df  mov     [r11+18h], r8d
0x1401b77e3  mov     [r11+10h], rdx
0x1401b77e7  push    rbp
0x1401b77e8  push    rsi
0x1401b77e9  push    rdi
0x1401b77ea  push    r12
0x1401b77ec  push    r13
0x1401b77ee  push    r14
0x1401b77f0  push    r15
0x1401b77f2  sub     rsp, 40h
0x1401b77f6  mov     rsi, [rsp+78h+arg_28]
0x1401b77fe  xor     eax, eax
0x1401b7800  xorps   xmm0, xmm0
0x1401b7803  xorps   xmm1, xmm1
0x1401b7806  mov     rbp, rcx
0x1401b7809  mov     r15d, r9d
0x1401b780c  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x1401b7813  mov     ebx, r8d
0x1401b7816  movups  xmmword ptr [rsi], xmm1
0x1401b7819  mov     [rsi+10h], rax
0x1401b781d  mov     r13, rdx
0x1401b7820  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1401b7825  mov     [r11-48h], rax
0x1401b7829  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401b7830  nop     dword ptr [rax+rax+00h]
0x1401b7835  mov     rdi, rax
0x1401b7838  test    rax, rax
0x1401b783b  jnz     short loc_1401B7847
0x1401b783d  mov     ebx, 0C000009Ah
0x1401b7842  jmp     loc_1401B7956
0x1401b7847  xorps   xmm0, xmm0
0x1401b784a  lea     rcx, [rdi+10h]; SpinLock
0x1401b784e  movups  xmmword ptr [rdi], xmm0
0x1401b7851  xor     eax, eax
0x1401b7853  movups  xmmword ptr [rdi+10h], xmm0
0x1401b7857  movups  xmmword ptr [rdi+20h], xmm0
0x1401b785b  mov     [rdi+30h], rax
0x1401b785f  call    cs:__imp_KeInitializeSpinLock
0x1401b7866  nop     dword ptr [rax+rax+00h]
0x1401b786b  lea     rax, [rdi+20h]
0x1401b786f  xor     edx, edx
0x1401b7871  mov     [rax+8], rax
0x1401b7875  mov     rcx, rbp
0x1401b7878  mov     [rax], rax
0x1401b787b  mov     [rdi+18h], rbp
0x1401b787f  call    QosGetNetBufferCount
0x1401b7884  lea     r14d, [rdx+1]
0x1401b7888  sub     eax, ebx
0x1401b788a  jz      short loc_1401B789A
0x1401b788c  lea     r14d, [r15+1]
0x1401b7890  cmp     r15d, 0FFFFFFFFh
0x1401b7894  jnz     short loc_1401B789A
0x1401b7896  lea     r14d, [rax+1]
0x1401b789a  xor     r12d, r12d
0x1401b789d  cmp     r12d, r14d
0x1401b78a0  jnb     loc_1401B797B
0x1401b78a6  mov     rcx, [r13+28h]; PoolHandle
0x1401b78aa  xor     r8d, r8d; ContextBackFill
0x1401b78ad  lea     edx, [r8+70h]; ContextSize
0x1401b78b1  call    cs:__imp_NdisAllocateNetBufferList
0x1401b78b8  nop     dword ptr [rax+rax+00h]
0x1401b78bd  mov     r13, rax
0x1401b78c0  test    rax, rax
0x1401b78c3  jz      short loc_1401B793B
0x1401b78c5  mov     rdx, rbp; SrcNetBufferList
0x1401b78c8  mov     rcx, rax; DestNetBufferList
0x1401b78cb  call    cs:__imp_NdisCopySendNetBufferListInfo
0x1401b78d2  nop     dword ptr [rax+rax+00h]
0x1401b78d7  mov     rcx, [rsp+78h+arg_8]
0x1401b78df  xor     edx, edx; Val
0x1401b78e1  mov     rax, [rcx+20h]
0x1401b78e5  lea     r8d, [rdx+70h]; Size
0x1401b78e9  mov     rcx, [r13+10h]
0x1401b78ed  mov     [r13+78h], rax
0x1401b78f1  movzx   ebx, word ptr [rcx+0Ah]
0x1401b78f5  add     rbx, rcx
0x1401b78f8  lea     rcx, [rbx+10h]; void *
0x1401b78fc  call    memset
0x1401b7901  mov     rax, [rsp+78h+arg_8]
0x1401b7909  mov     r8, r13
0x1401b790c  mov     rdx, [rsi+8]
0x1401b7910  mov     rcx, rsi
0x1401b7913  mov     [rbx+30h], rax
0x1401b7917  mov     [rbx+20h], rdi
0x1401b791b  mov     [rbx+28h], r13
0x1401b791f  mov     dword ptr [rbx+38h], 0
0x1401b7926  call    QosNblChainInsert
0x1401b792b  mov     r13, [rsp+78h+arg_8]
0x1401b7933  inc     r12d
0x1401b7936  jmp     loc_1401B789D
0x1401b793b  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x1401b7942  mov     rdx, rdi; Entry
0x1401b7945  mov     ebx, 0C000009Ah
0x1401b794a  call    cs:__imp_ExFreeToNPagedLookasideList
0x1401b7951  nop     dword ptr [rax+rax+00h]
0x1401b7956  mov     r8, [rsi]
0x1401b7959  test    r8, r8
0x1401b795c  jz      loc_1401B7A84
0x1401b7962  mov     rcx, rsi
0x1401b7965  call    QosNblChainRemove
0x1401b796a  mov     rcx, rax; NetBufferList
0x1401b796d  call    cs:__imp_NdisFreeNetBufferList
0x1401b7974  nop     dword ptr [rax+rax+00h]
0x1401b7979  jmp     short loc_1401B7956
0x1401b797b  mov     rax, [rbp+8]
0x1401b797f  xor     r14d, r14d
0x1401b7982  mov     rdx, [rsi]
0x1401b7985  mov     r8d, r14d
0x1401b7988  mov     ebx, [rsp+78h+arg_10]
0x1401b798f  mov     [rdx+8], rax
0x1401b7993  mov     eax, r14d
0x1401b7996  mov     [rbp+8], r14
0x1401b799a  mov     rcx, [rdx+8]
0x1401b799e  test    ebx, ebx
0x1401b79a0  jz      short loc_1401B79AE
0x1401b79a2  inc     eax
0x1401b79a4  mov     r8, rcx
0x1401b79a7  mov     rcx, [rcx]
0x1401b79aa  cmp     eax, ebx
0x1401b79ac  jb      short loc_1401B79A2
0x1401b79ae  mov     [r8], r14
0x1401b79b1  mov     rdx, [rdx]
0x1401b79b4  test    rdx, rdx
0x1401b79b7  jz      short loc_1401B79E1
0x1401b79b9  cmp     r15d, 1
0x1401b79bd  jnz     short loc_1401B79C5
0x1401b79bf  mov     [rdx+8], rcx
0x1401b79c3  jmp     short loc_1401B79E5
0x1401b79c5  test    rcx, rcx
0x1401b79c8  jz      short loc_1401B79E5
0x1401b79ca  mov     rax, [rcx]
0x1401b79cd  mov     [rdx+8], rcx
0x1401b79d1  mov     [rcx], r14
0x1401b79d4  mov     rcx, rax
0x1401b79d7  mov     rdx, [rdx]
0x1401b79da  test    rax, rax
0x1401b79dd  jnz     short loc_1401B79CA
0x1401b79df  jmp     short loc_1401B79E5
0x1401b79e1  mov     [rbp+8], rcx
0x1401b79e5  mov     eax, [rsi+10h]
0x1401b79e8  lock add [rdi+30h], eax
0x1401b79ec  mov     bpl, [rsp+78h+arg_30]
0x1401b79f4  lea     rcx, [rdi+10h]; SpinLock
0x1401b79f8  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1401b79fd  test    bpl, bpl
0x1401b7a00  jz      short loc_1401B7A10
0x1401b7a02  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1401b7a09  nop     dword ptr [rax+rax+00h]
0x1401b7a0e  jmp     short loc_1401B7A1C
0x1401b7a10  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1401b7a17  nop     dword ptr [rax+rax+00h]
0x1401b7a1c  mov     r8, [rsi]
0x1401b7a1f  test    r8, r8
0x1401b7a22  jz      short loc_1401B7A56
0x1401b7a24  add     rdi, 20h ; ' '
0x1401b7a28  mov     r9, [rdi+8]
0x1401b7a2c  cmp     [r9], rdi
0x1401b7a2f  jnz     short loc_1401B7A71
0x1401b7a31  mov     rcx, [r8+10h]
0x1401b7a35  movzx   eax, word ptr [rcx+0Ah]
0x1401b7a39  lea     rdx, [rcx+10h]
0x1401b7a3d  add     rdx, rax
0x1401b7a40  mov     [rdx], rdi
0x1401b7a43  mov     [rdx+8], r9
0x1401b7a47  mov     [r9], rdx
0x1401b7a4a  mov     [rdi+8], rdx
0x1401b7a4e  mov     r8, [r8]
0x1401b7a51  test    r8, r8
0x1401b7a54  jnz     short loc_1401B7A28
0x1401b7a56  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1401b7a5b  mov     ebx, r14d
0x1401b7a5e  test    bpl, bpl
0x1401b7a61  jz      short loc_1401B7A78
0x1401b7a63  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1401b7a6a  nop     dword ptr [rax+rax+00h]
0x1401b7a6f  jmp     short loc_1401B7A84
0x1401b7a71  mov     ecx, 3
0x1401b7a76  int     29h; Win8: RtlFailFast(ecx)
0x1401b7a78  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401b7a7f  nop     dword ptr [rax+rax+00h]
0x1401b7a84  mov     eax, ebx
0x1401b7a86  mov     rbx, [rsp+78h+arg_0]
0x1401b7a8e  add     rsp, 40h
0x1401b7a92  pop     r15
0x1401b7a94  pop     r14
0x1401b7a96  pop     r13
0x1401b7a98  pop     r12
0x1401b7a9a  pop     rdi
0x1401b7a9b  pop     rsi
0x1401b7a9c  pop     rbp
0x1401b7a9d  retn
```
