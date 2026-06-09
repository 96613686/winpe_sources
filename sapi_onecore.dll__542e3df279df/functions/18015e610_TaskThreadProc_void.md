# TaskThreadProc(void *)

- ea: `0x18015e610`
- end: `0x18015e7b6`
- name: `?TaskThreadProc@@YAIPEAX@Z`
- size: `422`
- prototype: `unsigned int __fastcall(CSpTaskManager *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180045938`
- `0x18015e2b4`
- `0x18015e610`
- `0x18015eef0`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x18015e7a0`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x18015e7a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015e730`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015e78d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015e730`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18015e78d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015e695`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18015e695`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e6b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e715`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e6b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015e715`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e6ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e77b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e6ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015e77b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015e6e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18015e6e0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18015e798`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18015e798`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18015e627`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18015e627`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18015e676`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x18015e676`

## pseudocode

```c
__int64 __fastcall TaskThreadProc(CSpTaskManager *this)
{
  void *v3; // rcx
  __int64 i; // rbx
  __int64 v5; // rax
  struct CSpReoccTask *v6; // rdx
  void *v7; // rbx
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp+8h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 CompletionKey; // [rsp+60h] [rbp+18h] BYREF

  if ( CoInitializeEx(0, 2u) < 0 )
    return 0xFFFFFFFFLL;
  while ( 1 )
  {
    do
    {
      v3 = (void *)*((_QWORD *)this + 38);
      NumberOfBytesTransferred = 0;
      CompletionKey = 0;
      Overlapped = 0;
      if ( !v3 )
      {
        WaitForSingleObject(*((HANDLE *)this + 39), 0xFFFFFFFF);
        break;
      }
    }
    while ( !GetQueuedCompletionStatus(v3, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF)
         && (int)SpHrFromLastWin32Error() < 0 );
    if ( !*((_DWORD *)this + 84) )
      break;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    for ( i = *((_QWORD *)this + 15); i; i = *(_QWORD *)(i + 56) )
    {
      if ( !*(_DWORD *)i )
      {
        v5 = *(_QWORD *)(i + 48);
        if ( v5 )
          *(_DWORD *)(v5 + 72) = 0;
        *(_DWORD *)i = 1;
        *(_DWORD *)(i + 64) = GetCurrentThreadId();
        break;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( i )
    {
      (***(void (__fastcall ****)(_QWORD, _QWORD, __int64))(i + 8))(*(_QWORD *)(i + 8), *(_QWORD *)(i + 16), i + 40);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      CSpBasicQueue<TMTASKNODE,1,1>::Remove((char *)this + 120, i);
      if ( *(_DWORD *)i == 2 )
        SetEvent(*((HANDLE *)this + 13));
      v6 = *(struct CSpReoccTask **)(i + 48);
      if ( v6 )
      {
        if ( !*((_DWORD *)v6 + 18) || *(_DWORD *)i == 2 )
          *(_DWORD *)i = 3;
        else
          CSpTaskManager::_QueueReoccTask(this, v6);
      }
      else
      {
        *(_DWORD *)i = 3;
        *(_QWORD *)(i + 56) = *((_QWORD *)this + 18);
        *((_QWORD *)this + 18) = i;
      }
      v7 = *(void **)(i + 24);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      if ( v7 )
        SetEvent(v7);
    }
  }
  CoUninitialize();
  _o__endthreadex(0);
  return 0;
}

```

## disassembly

```asm
0x18015e610  mov     [rsp+arg_18], rbx
0x18015e615  push    rsi
0x18015e616  push    rdi
0x18015e617  push    r14
0x18015e619  sub     rsp, 30h
0x18015e61d  mov     rdi, rcx
0x18015e620  mov     edx, 2; dwCoInit
0x18015e625  xor     ecx, ecx; pvReserved
0x18015e627  call    cs:__imp_CoInitializeEx
0x18015e62d  test    eax, eax
0x18015e62f  jns     short loc_18015E639
0x18015e631  or      eax, 0FFFFFFFFh
0x18015e634  jmp     loc_18015E7A8
0x18015e639  mov     rcx, [rdi+130h]; CompletionPort
0x18015e640  mov     [rsp+48h+NumberOfBytesTransferred], 0
0x18015e648  mov     [rsp+48h+CompletionKey], 0
0x18015e651  mov     [rsp+48h+Overlapped], 0
0x18015e65a  test    rcx, rcx
0x18015e65d  jz      short loc_18015E68B
0x18015e65f  lea     r9, [rsp+48h+Overlapped]; lpOverlapped
0x18015e664  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18015e66c  lea     r8, [rsp+48h+CompletionKey]; lpCompletionKey
0x18015e671  lea     rdx, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18015e676  call    cs:__imp_GetQueuedCompletionStatus
0x18015e67c  test    eax, eax
0x18015e67e  jnz     short loc_18015E69B
0x18015e680  call    ?SpHrFromLastWin32Error@@YAJXZ; SpHrFromLastWin32Error(void)
0x18015e685  test    eax, eax
0x18015e687  js      short loc_18015E639
0x18015e689  jmp     short loc_18015E69B
0x18015e68b  mov     rcx, [rdi+138h]; hHandle
0x18015e692  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18015e695  call    cs:__imp_WaitForSingleObject
0x18015e69b  mov     eax, [rdi+150h]
0x18015e6a1  test    eax, eax
0x18015e6a3  jz      loc_18015E798
0x18015e6a9  lea     rsi, [rdi+10h]
0x18015e6ad  mov     rcx, rsi; lpCriticalSection
0x18015e6b0  call    cs:__imp_EnterCriticalSection
0x18015e6b6  mov     rbx, [rdi+78h]
0x18015e6ba  test    rbx, rbx
0x18015e6bd  jz      short loc_18015E6E9
0x18015e6bf  cmp     dword ptr [rbx], 0
0x18015e6c2  jz      short loc_18015E6CA
0x18015e6c4  mov     rbx, [rbx+38h]
0x18015e6c8  jmp     short loc_18015E6BA
0x18015e6ca  mov     rax, [rbx+30h]
0x18015e6ce  test    rax, rax
0x18015e6d1  jz      short loc_18015E6DA
0x18015e6d3  mov     dword ptr [rax+48h], 0
0x18015e6da  mov     dword ptr [rbx], 1
0x18015e6e0  call    cs:__imp_GetCurrentThreadId
0x18015e6e6  mov     [rbx+40h], eax
0x18015e6e9  mov     rcx, rsi; lpCriticalSection
0x18015e6ec  call    cs:__imp_LeaveCriticalSection
0x18015e6f2  test    rbx, rbx
0x18015e6f5  jz      loc_18015E639
0x18015e6fb  mov     rcx, [rbx+8]
0x18015e6ff  lea     r8, [rbx+28h]
0x18015e703  mov     rdx, [rbx+10h]
0x18015e707  mov     rax, [rcx]
0x18015e70a  mov     rax, [rax]
0x18015e70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015e712  mov     rcx, rsi; lpCriticalSection
0x18015e715  call    cs:__imp_EnterCriticalSection
0x18015e71b  mov     rdx, rbx
0x18015e71e  lea     rcx, [rdi+78h]
0x18015e722  call    ?Remove@?$CSpBasicQueue@UTMTASKNODE@@$00$00@@QEAAHPEAUTMTASKNODE@@@Z; CSpBasicQueue<TMTASKNODE,1,1>::Remove(TMTASKNODE *)
0x18015e727  cmp     dword ptr [rbx], 2
0x18015e72a  jnz     short loc_18015E736
0x18015e72c  mov     rcx, [rdi+68h]; hEvent
0x18015e730  call    cs:__imp_SetEvent
0x18015e736  mov     rdx, [rbx+30h]; struct CSpReoccTask *
0x18015e73a  test    rdx, rdx
0x18015e73d  jz      short loc_18015E75C
0x18015e73f  cmp     dword ptr [rdx+48h], 0
0x18015e743  jz      short loc_18015E754
0x18015e745  cmp     dword ptr [rbx], 2
0x18015e748  jz      short loc_18015E754
0x18015e74a  mov     rcx, rdi; this
0x18015e74d  call    ?_QueueReoccTask@CSpTaskManager@@QEAAXPEAVCSpReoccTask@@@Z; CSpTaskManager::_QueueReoccTask(CSpReoccTask *)
0x18015e752  jmp     short loc_18015E774
0x18015e754  mov     dword ptr [rbx], 3
0x18015e75a  jmp     short loc_18015E774
0x18015e75c  mov     dword ptr [rbx], 3
0x18015e762  mov     rax, [rdi+90h]
0x18015e769  mov     [rbx+38h], rax
0x18015e76d  mov     [rdi+90h], rbx
0x18015e774  mov     rbx, [rbx+18h]
0x18015e778  mov     rcx, rsi; lpCriticalSection
0x18015e77b  call    cs:__imp_LeaveCriticalSection
0x18015e781  test    rbx, rbx
0x18015e784  jz      loc_18015E639
0x18015e78a  mov     rcx, rbx; hEvent
0x18015e78d  call    cs:__imp_SetEvent
0x18015e793  jmp     loc_18015E639
0x18015e798  call    cs:__imp_CoUninitialize
0x18015e79e  xor     ecx, ecx
0x18015e7a0  call    cs:__imp__o__endthreadex
0x18015e7a6  xor     eax, eax
0x18015e7a8  mov     rbx, [rsp+48h+arg_18]
0x18015e7ad  add     rsp, 30h
0x18015e7b1  pop     r14
0x18015e7b3  pop     rdi
0x18015e7b4  pop     rsi
0x18015e7b5  retn
```
