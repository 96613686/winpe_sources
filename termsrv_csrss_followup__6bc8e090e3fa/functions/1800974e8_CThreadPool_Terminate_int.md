# CThreadPool::Terminate(int)

- ea: `0x1800974e8`
- end: `0x180097606`
- name: `?Terminate@CThreadPool@@QEAAJH@Z`
- size: `286`
- prototype: `__int64 __fastcall(CThreadPool *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004f5e0`
- `0x180096f18`
- `0x180097114`

## callees

- `0x180096ef0`
- `0x1800973bc`
- `0x1800974e8`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180097519`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180097519`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009755a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009755a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800975c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800975c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800975b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800975b0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800975dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800975dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009752e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009752e`

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
0x1800974e8  mov     [rsp+arg_0], rbx
0x1800974ed  push    rdi
0x1800974ee  sub     rsp, 30h
0x1800974f2  mov     edi, edx
0x1800974f4  mov     rbx, rcx
0x1800974f7  cmp     qword ptr [rcx+8], 0
0x1800974fc  jz      short loc_180097525
0x1800974fe  mov     eax, [rcx+10h]
0x180097501  mov     edx, eax
0x180097503  bts     edx, 1Eh
0x180097507  lock cmpxchg [rcx+10h], edx
0x18009750c  jnz     short loc_1800974FE
0x18009750e  test    eax, eax
0x180097510  jz      short loc_180097525
0x180097512  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180097515  mov     rcx, [rcx+8]; hHandle
0x180097519  call    cs:__imp_WaitForSingleObject
0x180097520  nop     dword ptr [rax+rax+00h]
0x180097525  mov     rcx, [rbx+8]; hObject
0x180097529  test    rcx, rcx
0x18009752c  jz      short loc_180097542
0x18009752e  call    cs:__imp_CloseHandle
0x180097535  nop     dword ptr [rax+rax+00h]
0x18009753a  mov     qword ptr [rbx+8], 0
0x180097542  test    edi, edi
0x180097544  jz      short loc_1800975A2
0x180097546  lea     rcx, [rbx+88h]; SRWLock
0x18009754d  mov     [rsp+38h+var_18], rcx
0x180097552  mov     [rsp+38h+var_10], 1
0x18009755a  call    cs:__imp_AcquireSRWLockExclusive
0x180097561  nop     dword ptr [rax+rax+00h]
0x180097566  nop
0x180097567  jmp     short loc_180097588
0x180097569  mov     rcx, [rdi]
0x18009756c  mov     rax, [rcx+20h]
0x180097570  mov     rcx, rdi
0x180097573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097578  mov     rcx, [rdi+8]
0x18009757c  mov     rax, [rcx]
0x18009757f  mov     rax, [rax+8]
0x180097583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097588  mov     rcx, rbx; this
0x18009758b  call    ?PopFrontWorkItemQueue@CThreadPool@@AEAAPEAVCDispatchContext@@XZ; CThreadPool::PopFrontWorkItemQueue(void)
0x180097590  test    rax, rax
0x180097593  mov     rdi, rax
0x180097596  jnz     short loc_180097569
0x180097598  lea     rcx, [rsp+38h+var_18]; this
0x18009759d  call    ??1CAutoLockExclusive@@QEAA@XZ; CAutoLockExclusive::~CAutoLockExclusive(void)
0x1800975a2  mov     rcx, [rbx+28h]; ptpcg
0x1800975a6  test    rcx, rcx
0x1800975a9  jz      short loc_1800975D4
0x1800975ab  xor     r8d, r8d; pvCleanupContext
0x1800975ae  xor     edx, edx; fCancelPendingCallbacks
0x1800975b0  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800975b7  nop     dword ptr [rax+rax+00h]
0x1800975bc  mov     rcx, [rbx+28h]; ptpcg
0x1800975c0  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800975c7  nop     dword ptr [rax+rax+00h]
0x1800975cc  mov     qword ptr [rbx+28h], 0
0x1800975d4  mov     rcx, [rbx+20h]; ptpp
0x1800975d8  test    rcx, rcx
0x1800975db  jz      short loc_1800975F1
0x1800975dd  call    cs:__imp_CloseThreadpool
0x1800975e4  nop     dword ptr [rax+rax+00h]
0x1800975e9  mov     qword ptr [rbx+20h], 0
0x1800975f1  mov     dword ptr [rbx+18h], 0
0x1800975f8  xor     eax, eax
0x1800975fa  mov     rbx, [rsp+38h+arg_0]
0x1800975ff  add     rsp, 30h
0x180097603  pop     rdi
0x180097604  retn
```
