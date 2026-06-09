# CThreadPool::Terminate(int)

- ea: `0x180093550`
- end: `0x180093649`
- name: `?Terminate@CThreadPool@@QEAAJH@Z`
- size: `249`
- prototype: `__int64 __fastcall(CThreadPool *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004cfb0`
- `0x180093078`
- `0x1800931cc`

## callees

- `0x180093058`
- `0x180093438`
- `0x180093550`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180093581`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180093581`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800935b6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800935b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180093610`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180093610`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180093606`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180093606`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180093627`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180093627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180093590`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CThreadPool::Terminate(CThreadPool *this, int a2)
{
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  void *v6; // rcx
  struct CDispatchContext *v7; // rax
  struct CDispatchContext *v8; // rdi
  struct _TP_CLEANUP_GROUP *v9; // rcx
  struct _TP_POOL *v10; // rcx
  char *v12; // [rsp+20h] [rbp-18h] BYREF
  int v13; // [rsp+28h] [rbp-10h]

  if ( *((_QWORD *)this + 1) )
  {
    do
    {
      v5 = *((_DWORD *)this + 4);
      v4 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, v5 | 0x40000000, v5);
    }
    while ( v5 != v4 );
    if ( v4 )
      WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF);
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 1) = 0;
  }
  if ( a2 )
  {
    v12 = (char *)this + 136;
    v13 = 1;
    AcquireSRWLockExclusive((PSRWLOCK)this + 17);
    while ( 1 )
    {
      v7 = CThreadPool::PopFrontWorkItemQueue(this);
      v8 = v7;
      if ( !v7 )
        break;
      (*(void (__fastcall **)(struct CDispatchContext *))(*(_QWORD *)v7 + 32LL))(v7);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 1) + 8LL))(*((_QWORD *)v8 + 1));
    }
    CAutoLockExclusive::~CAutoLockExclusive((CAutoLockExclusive *)&v12);
  }
  v9 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 5);
  if ( v9 )
  {
    CloseThreadpoolCleanupGroupMembers(v9, 0, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
  v10 = (struct _TP_POOL *)*((_QWORD *)this + 4);
  if ( v10 )
  {
    CloseThreadpool(v10);
    *((_QWORD *)this + 4) = 0;
  }
  *((_DWORD *)this + 6) = 0;
  return 0;
}

```

## disassembly

```asm
0x180093550  mov     [rsp+arg_0], rbx
0x180093555  push    rdi
0x180093556  sub     rsp, 30h
0x18009355a  mov     edi, edx
0x18009355c  mov     rbx, rcx
0x18009355f  cmp     qword ptr [rcx+8], 0
0x180093564  jz      short loc_180093587
0x180093566  mov     eax, [rcx+10h]
0x180093569  mov     edx, eax
0x18009356b  bts     edx, 1Eh
0x18009356f  lock cmpxchg [rcx+10h], edx
0x180093574  jnz     short loc_180093566
0x180093576  test    eax, eax
0x180093578  jz      short loc_180093587
0x18009357a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009357d  mov     rcx, [rcx+8]; hHandle
0x180093581  call    cs:__imp_WaitForSingleObject
0x180093587  mov     rcx, [rbx+8]; hObject
0x18009358b  test    rcx, rcx
0x18009358e  jz      short loc_18009359E
0x180093590  call    cs:__imp_CloseHandle
0x180093596  mov     qword ptr [rbx+8], 0
0x18009359e  test    edi, edi
0x1800935a0  jz      short loc_1800935F8
0x1800935a2  lea     rcx, [rbx+88h]; SRWLock
0x1800935a9  mov     [rsp+38h+var_18], rcx
0x1800935ae  mov     [rsp+38h+var_10], 1
0x1800935b6  call    cs:__imp_AcquireSRWLockExclusive
0x1800935bc  nop
0x1800935bd  jmp     short loc_1800935DE
0x1800935bf  mov     rcx, [rdi]
0x1800935c2  mov     rax, [rcx+20h]
0x1800935c6  mov     rcx, rdi
0x1800935c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800935ce  mov     rcx, [rdi+8]
0x1800935d2  mov     rax, [rcx]
0x1800935d5  mov     rax, [rax+8]
0x1800935d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800935de  mov     rcx, rbx; this
0x1800935e1  call    ?PopFrontWorkItemQueue@CThreadPool@@AEAAPEAVCDispatchContext@@XZ; CThreadPool::PopFrontWorkItemQueue(void)
0x1800935e6  test    rax, rax
0x1800935e9  mov     rdi, rax
0x1800935ec  jnz     short loc_1800935BF
0x1800935ee  lea     rcx, [rsp+38h+var_18]; this
0x1800935f3  call    ??1CAutoLockExclusive@@QEAA@XZ; CAutoLockExclusive::~CAutoLockExclusive(void)
0x1800935f8  mov     rcx, [rbx+28h]; ptpcg
0x1800935fc  test    rcx, rcx
0x1800935ff  jz      short loc_18009361E
0x180093601  xor     r8d, r8d; pvCleanupContext
0x180093604  xor     edx, edx; fCancelPendingCallbacks
0x180093606  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18009360c  mov     rcx, [rbx+28h]; ptpcg
0x180093610  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180093616  mov     qword ptr [rbx+28h], 0
0x18009361e  mov     rcx, [rbx+20h]; ptpp
0x180093622  test    rcx, rcx
0x180093625  jz      short loc_180093635
0x180093627  call    cs:__imp_CloseThreadpool
0x18009362d  mov     qword ptr [rbx+20h], 0
0x180093635  mov     dword ptr [rbx+18h], 0
0x18009363c  xor     eax, eax
0x18009363e  mov     rbx, [rsp+38h+arg_0]
0x180093643  add     rsp, 30h
0x180093647  pop     rdi
0x180093648  retn
```
