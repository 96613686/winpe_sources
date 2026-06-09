# QosNblCadDisassemble

- ea: `0x1401b7848`
- end: `0x1401b7b0f`
- name: `QosNblCadDisassemble`
- size: `711`
- prototype: `__int64 __usercall@<rax>(PNET_BUFFER_LIST SrcNetBufferList@<rcx>, int, __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1401b7d88`

## callees

- `0x140099f04`
- `0x1401b7820`
- `0x1401b7848`
- `0x1401b7c6c`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1401b7a72`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1401b7a72`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1401b7ad3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1401b7ad3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401b7ae8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401b7ae8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401b7a80`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401b7a80`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401b79ba`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1401b79ba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401b7899`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401b7899`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b78cf`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b78cf`
- `NDIS!NdisFreeNetBufferList` at `0x1401b79dd`
- `NDIS!NdisFreeNetBufferList` at `0x1401b79dd`
- `NDIS!NdisAllocateNetBufferList` at `0x1401b7921`
- `NDIS!NdisAllocateNetBufferList` at `0x1401b7921`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1401b793b`
- `NDIS!NdisCopySendNetBufferListInfo` at `0x1401b793b`

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
0x1401b7848  mov     r11, rsp
0x1401b784b  mov     [r11+8], rbx
0x1401b784f  mov     [r11+18h], r8d
0x1401b7853  mov     [r11+10h], rdx
0x1401b7857  push    rbp
0x1401b7858  push    rsi
0x1401b7859  push    rdi
0x1401b785a  push    r12
0x1401b785c  push    r13
0x1401b785e  push    r14
0x1401b7860  push    r15
0x1401b7862  sub     rsp, 40h
0x1401b7866  mov     rsi, [rsp+78h+arg_28]
0x1401b786e  xor     eax, eax
0x1401b7870  xorps   xmm0, xmm0
0x1401b7873  xorps   xmm1, xmm1
0x1401b7876  mov     rbp, rcx
0x1401b7879  mov     r15d, r9d
0x1401b787c  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x1401b7883  mov     ebx, r8d
0x1401b7886  movups  xmmword ptr [rsi], xmm1
0x1401b7889  mov     [rsi+10h], rax
0x1401b788d  mov     r13, rdx
0x1401b7890  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1401b7895  mov     [r11-48h], rax
0x1401b7899  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1401b78a0  nop     dword ptr [rax+rax+00h]
0x1401b78a5  mov     rdi, rax
0x1401b78a8  test    rax, rax
0x1401b78ab  jnz     short loc_1401B78B7
0x1401b78ad  mov     ebx, 0C000009Ah
0x1401b78b2  jmp     loc_1401B79C6
0x1401b78b7  xorps   xmm0, xmm0
0x1401b78ba  lea     rcx, [rdi+10h]; SpinLock
0x1401b78be  movups  xmmword ptr [rdi], xmm0
0x1401b78c1  xor     eax, eax
0x1401b78c3  movups  xmmword ptr [rdi+10h], xmm0
0x1401b78c7  movups  xmmword ptr [rdi+20h], xmm0
0x1401b78cb  mov     [rdi+30h], rax
0x1401b78cf  call    cs:__imp_KeInitializeSpinLock
0x1401b78d6  nop     dword ptr [rax+rax+00h]
0x1401b78db  lea     rax, [rdi+20h]
0x1401b78df  xor     edx, edx
0x1401b78e1  mov     [rax+8], rax
0x1401b78e5  mov     rcx, rbp
0x1401b78e8  mov     [rax], rax
0x1401b78eb  mov     [rdi+18h], rbp
0x1401b78ef  call    QosGetNetBufferCount
0x1401b78f4  lea     r14d, [rdx+1]
0x1401b78f8  sub     eax, ebx
0x1401b78fa  jz      short loc_1401B790A
0x1401b78fc  lea     r14d, [r15+1]
0x1401b7900  cmp     r15d, 0FFFFFFFFh
0x1401b7904  jnz     short loc_1401B790A
0x1401b7906  lea     r14d, [rax+1]
0x1401b790a  xor     r12d, r12d
0x1401b790d  cmp     r12d, r14d
0x1401b7910  jnb     loc_1401B79EB
0x1401b7916  mov     rcx, [r13+28h]; PoolHandle
0x1401b791a  xor     r8d, r8d; ContextBackFill
0x1401b791d  lea     edx, [r8+70h]; ContextSize
0x1401b7921  call    cs:__imp_NdisAllocateNetBufferList
0x1401b7928  nop     dword ptr [rax+rax+00h]
0x1401b792d  mov     r13, rax
0x1401b7930  test    rax, rax
0x1401b7933  jz      short loc_1401B79AB
0x1401b7935  mov     rdx, rbp; SrcNetBufferList
0x1401b7938  mov     rcx, rax; DestNetBufferList
0x1401b793b  call    cs:__imp_NdisCopySendNetBufferListInfo
0x1401b7942  nop     dword ptr [rax+rax+00h]
0x1401b7947  mov     rcx, [rsp+78h+arg_8]
0x1401b794f  xor     edx, edx; Val
0x1401b7951  mov     rax, [rcx+20h]
0x1401b7955  lea     r8d, [rdx+70h]; Size
0x1401b7959  mov     rcx, [r13+10h]
0x1401b795d  mov     [r13+78h], rax
0x1401b7961  movzx   ebx, word ptr [rcx+0Ah]
0x1401b7965  add     rbx, rcx
0x1401b7968  lea     rcx, [rbx+10h]; void *
0x1401b796c  call    memset
0x1401b7971  mov     rax, [rsp+78h+arg_8]
0x1401b7979  mov     r8, r13
0x1401b797c  mov     rdx, [rsi+8]
0x1401b7980  mov     rcx, rsi
0x1401b7983  mov     [rbx+30h], rax
0x1401b7987  mov     [rbx+20h], rdi
0x1401b798b  mov     [rbx+28h], r13
0x1401b798f  mov     dword ptr [rbx+38h], 0
0x1401b7996  call    QosNblChainInsert
0x1401b799b  mov     r13, [rsp+78h+arg_8]
0x1401b79a3  inc     r12d
0x1401b79a6  jmp     loc_1401B790D
0x1401b79ab  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x1401b79b2  mov     rdx, rdi; Entry
0x1401b79b5  mov     ebx, 0C000009Ah
0x1401b79ba  call    cs:__imp_ExFreeToNPagedLookasideList
0x1401b79c1  nop     dword ptr [rax+rax+00h]
0x1401b79c6  mov     r8, [rsi]
0x1401b79c9  test    r8, r8
0x1401b79cc  jz      loc_1401B7AF4
0x1401b79d2  mov     rcx, rsi
0x1401b79d5  call    QosNblChainRemove
0x1401b79da  mov     rcx, rax; NetBufferList
0x1401b79dd  call    cs:__imp_NdisFreeNetBufferList
0x1401b79e4  nop     dword ptr [rax+rax+00h]
0x1401b79e9  jmp     short loc_1401B79C6
0x1401b79eb  mov     rax, [rbp+8]
0x1401b79ef  xor     r14d, r14d
0x1401b79f2  mov     rdx, [rsi]
0x1401b79f5  mov     r8d, r14d
0x1401b79f8  mov     ebx, [rsp+78h+arg_10]
0x1401b79ff  mov     [rdx+8], rax
0x1401b7a03  mov     eax, r14d
0x1401b7a06  mov     [rbp+8], r14
0x1401b7a0a  mov     rcx, [rdx+8]
0x1401b7a0e  test    ebx, ebx
0x1401b7a10  jz      short loc_1401B7A1E
0x1401b7a12  inc     eax
0x1401b7a14  mov     r8, rcx
0x1401b7a17  mov     rcx, [rcx]
0x1401b7a1a  cmp     eax, ebx
0x1401b7a1c  jb      short loc_1401B7A12
0x1401b7a1e  mov     [r8], r14
0x1401b7a21  mov     rdx, [rdx]
0x1401b7a24  test    rdx, rdx
0x1401b7a27  jz      short loc_1401B7A51
0x1401b7a29  cmp     r15d, 1
0x1401b7a2d  jnz     short loc_1401B7A35
0x1401b7a2f  mov     [rdx+8], rcx
0x1401b7a33  jmp     short loc_1401B7A55
0x1401b7a35  test    rcx, rcx
0x1401b7a38  jz      short loc_1401B7A55
0x1401b7a3a  mov     rax, [rcx]
0x1401b7a3d  mov     [rdx+8], rcx
0x1401b7a41  mov     [rcx], r14
0x1401b7a44  mov     rcx, rax
0x1401b7a47  mov     rdx, [rdx]
0x1401b7a4a  test    rax, rax
0x1401b7a4d  jnz     short loc_1401B7A3A
0x1401b7a4f  jmp     short loc_1401B7A55
0x1401b7a51  mov     [rbp+8], rcx
0x1401b7a55  mov     eax, [rsi+10h]
0x1401b7a58  lock add [rdi+30h], eax
0x1401b7a5c  mov     bpl, [rsp+78h+arg_30]
0x1401b7a64  lea     rcx, [rdi+10h]; SpinLock
0x1401b7a68  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1401b7a6d  test    bpl, bpl
0x1401b7a70  jz      short loc_1401B7A80
0x1401b7a72  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1401b7a79  nop     dword ptr [rax+rax+00h]
0x1401b7a7e  jmp     short loc_1401B7A8C
0x1401b7a80  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1401b7a87  nop     dword ptr [rax+rax+00h]
0x1401b7a8c  mov     r8, [rsi]
0x1401b7a8f  test    r8, r8
0x1401b7a92  jz      short loc_1401B7AC6
0x1401b7a94  add     rdi, 20h ; ' '
0x1401b7a98  mov     r9, [rdi+8]
0x1401b7a9c  cmp     [r9], rdi
0x1401b7a9f  jnz     short loc_1401B7AE1
0x1401b7aa1  mov     rcx, [r8+10h]
0x1401b7aa5  movzx   eax, word ptr [rcx+0Ah]
0x1401b7aa9  lea     rdx, [rcx+10h]
0x1401b7aad  add     rdx, rax
0x1401b7ab0  mov     [rdx], rdi
0x1401b7ab3  mov     [rdx+8], r9
0x1401b7ab7  mov     [r9], rdx
0x1401b7aba  mov     [rdi+8], rdx
0x1401b7abe  mov     r8, [r8]
0x1401b7ac1  test    r8, r8
0x1401b7ac4  jnz     short loc_1401B7A98
0x1401b7ac6  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1401b7acb  mov     ebx, r14d
0x1401b7ace  test    bpl, bpl
0x1401b7ad1  jz      short loc_1401B7AE8
0x1401b7ad3  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1401b7ada  nop     dword ptr [rax+rax+00h]
0x1401b7adf  jmp     short loc_1401B7AF4
0x1401b7ae1  mov     ecx, 3
0x1401b7ae6  int     29h; Win8: RtlFailFast(ecx)
0x1401b7ae8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401b7aef  nop     dword ptr [rax+rax+00h]
0x1401b7af4  mov     eax, ebx
0x1401b7af6  mov     rbx, [rsp+78h+arg_0]
0x1401b7afe  add     rsp, 40h
0x1401b7b02  pop     r15
0x1401b7b04  pop     r14
0x1401b7b06  pop     r13
0x1401b7b08  pop     r12
0x1401b7b0a  pop     rdi
0x1401b7b0b  pop     rsi
0x1401b7b0c  pop     rbp
0x1401b7b0d  retn
```
