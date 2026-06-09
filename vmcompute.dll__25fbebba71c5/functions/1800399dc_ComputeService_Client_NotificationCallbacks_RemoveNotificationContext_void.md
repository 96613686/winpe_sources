# ComputeService::Client::NotificationCallbacks::RemoveNotificationContext(void *)

- ea: `0x1800399dc`
- end: `0x180039bd2`
- name: `?RemoveNotificationContext@NotificationCallbacks@Client@ComputeService@@AEAA_NPEAX@Z`
- size: `502`
- prototype: `bool __fastcall(ComputeService::Client::NotificationCallbacks *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180039cdc`

## callees

- `0x180003388`
- `0x18000d108`
- `0x180011a60`
- `0x1800188a4`
- `0x180023c14`
- `0x1800392c8`
- `0x1800399dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039a02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039af9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039a02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180039af9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039add`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039b1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039add`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039b1d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180039b2d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180039b2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039b61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039b61`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180039b76`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180039b76`

## string_xrefs

- `0x180039bbf`: `onecore\vm\compute\dll\lib\core\notificationcallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ComputeService::Client::NotificationCallbacks::RemoveNotificationContext(
        RTL_SRWLOCK *this,
        unsigned __int64 a2)
{
  char v4; // r15
  __int64 v5; // rdi
  RTL_SRWLOCK *v6; // r12
  _QWORD *Ptr; // rdx
  _QWORD *v8; // rcx
  _QWORD *v9; // rax
  __int64 **v10; // rcx
  _QWORD *v11; // rdx
  __int64 i; // rcx
  __int64 *j; // rcx
  __int64 v14; // rax
  void *v15; // r14
  void *v16; // rsi
  int v17; // r14d
  int v18; // eax
  wil *v19; // rcx
  unsigned int v21; // eax
  const char *v22; // [rsp+28h] [rbp-70h]
  int v23; // [rsp+20h] [rbp-78h]
  __int64 v24; // [rsp+38h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = 0;
  v5 = 0;
  v24 = 0;
  v6 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  Ptr = this[3].Ptr;
  v8 = (_QWORD *)Ptr[1];
  v9 = Ptr;
  while ( !*((_BYTE *)v8 + 25) )
  {
    if ( v8[4] >= a2 )
    {
      v9 = v8;
      v8 = (_QWORD *)*v8;
    }
    else
    {
      v8 = (_QWORD *)v8[2];
    }
  }
  if ( !*((_BYTE *)v9 + 25) && a2 >= v9[4] && v9 != Ptr )
  {
    v5 = v9[5];
    v9[5] = 0;
    v24 = v5;
    v10 = (__int64 **)v9[2];
    v11 = v9;
    if ( *((_BYTE *)v10 + 25) )
    {
      for ( i = v9[1]; !*(_BYTE *)(i + 25) && v9 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v9 = (_QWORD *)i;
    }
    else
    {
      for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        ;
    }
    v14 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Extract(&this[3], v11);
    v15 = (void *)v14;
    v16 = *(void **)(v14 + 40);
    if ( v16 )
    {
      ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(*(ComputeService::Client::NotificationCallbacks::NotificationContext **)(v14 + 40));
      operator delete(v16, 0x68u);
    }
    operator delete(v15, 0x30u);
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( v5 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(v5 + 72));
    v17 = *(_DWORD *)(v5 + 64);
    v4 = 1;
    *(_BYTE *)(v5 + 68) = 1;
    if ( v5 != -72 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v5 + 72));
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v5 + 80));
    try
    {
      v18 = ComputeService::Client::InvokeRpcFunction<long (*)(void *),void * &>(
              (__int64 (__fastcall *)(_QWORD))this[1].Ptr,
              (_QWORD *)v5);
      v19 = retaddr;
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x125,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
          (const char *)(unsigned int)v18,
          v23);
    }
    catch ( ... )
    {
      v21 = wil::ResultFromCaughtException(v19);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\notificationcallbacks.cpp",
        (const char *)v21,
        (int)"Unregister notification failed",
        v22);
      v4 = 1;
      v5 = v24;
    }
    if ( v17 == GetCurrentThreadId() )
    {
      SubmitThreadpoolWork(*(PTP_WORK *)(v5 + 88));
      v5 = 0;
    }
    else
    {
      ComputeService::Client::NotificationCallbacks::CleanupNotificationContext((PTP_WAIT *)v5);
    }
  }
  if ( v5 )
  {
    ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext((ComputeService::Client::NotificationCallbacks::NotificationContext *)v5);
    operator delete((void *)v5, 0x68u);
  }
  return v4;
}

```

## disassembly

```asm
0x1800399dc  push    rsi
0x1800399de  push    rdi
0x1800399df  push    r12
0x1800399e1  push    r13
0x1800399e3  push    r14
0x1800399e5  push    r15
0x1800399e7  sub     rsp, 68h
0x1800399eb  mov     rsi, rdx
0x1800399ee  mov     r13, rcx
0x1800399f1  xor     r15b, r15b
0x1800399f4  xor     edi, edi
0x1800399f6  mov     [rsp+98h+var_60], rdi
0x1800399fb  lea     r12, [rcx+28h]
0x1800399ff  mov     rcx, r12; SRWLock
0x180039a02  call    cs:__imp_AcquireSRWLockExclusive
0x180039a09  nop     dword ptr [rax+rax+00h]
0x180039a0e  mov     rdx, [r13+18h]
0x180039a12  mov     rcx, [rdx+8]
0x180039a16  mov     rax, rdx
0x180039a19  jmp     short loc_180039A2D
0x180039a1b  cmp     [rcx+20h], rsi
0x180039a1f  jnb     short loc_180039A27
0x180039a21  mov     rcx, [rcx+10h]
0x180039a25  jmp     short loc_180039A2D
0x180039a27  mov     rax, rcx
0x180039a2a  mov     rcx, [rcx]
0x180039a2d  cmp     byte ptr [rcx+19h], 0
0x180039a31  jz      short loc_180039A1B
0x180039a33  cmp     byte ptr [rax+19h], 0
0x180039a37  jnz     loc_180039AD5
0x180039a3d  cmp     rsi, [rax+20h]
0x180039a41  jb      loc_180039AD5
0x180039a47  cmp     rax, rdx
0x180039a4a  jz      loc_180039AD5
0x180039a50  mov     rdi, [rax+28h]
0x180039a54  mov     qword ptr [rax+28h], 0
0x180039a5c  mov     [rsp+98h+var_60], rdi
0x180039a61  mov     rcx, [rax+10h]
0x180039a65  mov     rdx, rax
0x180039a68  cmp     byte ptr [rcx+19h], 0
0x180039a6c  jz      short loc_180039A89
0x180039a6e  mov     rcx, [rax+8]
0x180039a72  jmp     short loc_180039A81
0x180039a74  cmp     rax, [rcx+10h]
0x180039a78  jnz     short loc_180039A9E
0x180039a7a  mov     rax, rcx
0x180039a7d  mov     rcx, [rcx+8]
0x180039a81  cmp     byte ptr [rcx+19h], 0
0x180039a85  jz      short loc_180039A74
0x180039a87  jmp     short loc_180039A9E
0x180039a89  mov     rcx, [rcx]
0x180039a8c  cmp     byte ptr [rcx+19h], 0
0x180039a90  jnz     short loc_180039A9E
0x180039a92  mov     rax, [rcx]
0x180039a95  mov     rcx, rax
0x180039a98  cmp     byte ptr [rax+19h], 0
0x180039a9c  jz      short loc_180039A92
0x180039a9e  lea     rcx, [r13+18h]
0x180039aa2  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>)
0x180039aa7  mov     r14, rax
0x180039aaa  mov     rsi, [rax+28h]
0x180039aae  test    rsi, rsi
0x180039ab1  jz      short loc_180039AC8
0x180039ab3  mov     rcx, rsi; this
0x180039ab6  call    ??1NotificationContext@NotificationCallbacks@Client@ComputeService@@QEAA@XZ; ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x180039abb  mov     edx, 68h ; 'h'; unsigned __int64
0x180039ac0  mov     rcx, rsi; void *
0x180039ac3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180039ac8  mov     edx, 30h ; '0'; unsigned __int64
0x180039acd  mov     rcx, r14; void *
0x180039ad0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180039ad5  test    r12, r12
0x180039ad8  jz      short loc_180039AE9
0x180039ada  mov     rcx, r12; SRWLock
0x180039add  call    cs:__imp_ReleaseSRWLockExclusive
0x180039ae4  nop     dword ptr [rax+rax+00h]
0x180039ae9  test    rdi, rdi
0x180039aec  jz      loc_180039B8F
0x180039af2  lea     rsi, [rdi+48h]
0x180039af6  mov     rcx, rsi; SRWLock
0x180039af9  call    cs:__imp_AcquireSRWLockExclusive
0x180039b00  nop     dword ptr [rax+rax+00h]
0x180039b05  mov     r14d, [rdi+40h]
0x180039b09  mov     [rsp+98h+var_68], r14d
0x180039b0e  mov     r15b, 1
0x180039b11  mov     [rdi+44h], r15b
0x180039b15  test    rsi, rsi
0x180039b18  jz      short loc_180039B29
0x180039b1a  mov     rcx, rsi; SRWLock
0x180039b1d  call    cs:__imp_ReleaseSRWLockExclusive
0x180039b24  nop     dword ptr [rax+rax+00h]
0x180039b29  lea     rcx, [rdi+50h]; ConditionVariable
0x180039b2d  call    cs:__imp_WakeAllConditionVariable
0x180039b34  nop     dword ptr [rax+rax+00h]
0x180039b39  nop
0x180039b3a  mov     rdx, rdi
0x180039b3d  mov     rcx, [r13+8]
0x180039b41  call    ??$InvokeRpcFunction@P6AJPEAX@ZAEAPEAX@Client@ComputeService@@YA?A_TP6AJPEAX@ZAEAPEAX@Z
0x180039b46  mov     rcx, [rsp+98h]; this
0x180039b4e  test    eax, eax
0x180039b50  js      short loc_180039BBC
0x180039b52  jmp     short loc_180039B61
0x180039b54  mov     r15b, 1
0x180039b57  mov     rdi, [rsp+98h+var_60]
0x180039b5c  mov     r14d, [rsp+98h+var_68]
0x180039b61  call    cs:__imp_GetCurrentThreadId
0x180039b68  nop     dword ptr [rax+rax+00h]
0x180039b6d  cmp     r14d, eax
0x180039b70  jnz     short loc_180039B86
0x180039b72  mov     rcx, [rdi+58h]; pwk
0x180039b76  call    cs:__imp_SubmitThreadpoolWork
0x180039b7d  nop     dword ptr [rax+rax+00h]
0x180039b82  xor     edi, edi
0x180039b84  jmp     short loc_180039B8F
0x180039b86  mov     rcx, rdi; struct ComputeService::Client::NotificationCallbacks::NotificationContext *
0x180039b89  call    ?CleanupNotificationContext@NotificationCallbacks@Client@ComputeService@@CAXPEAUNotificationContext@123@@Z; ComputeService::Client::NotificationCallbacks::CleanupNotificationContext(ComputeService::Client::NotificationCallbacks::NotificationContext *)
0x180039b8e  nop
0x180039b8f  test    rdi, rdi
0x180039b92  jz      short loc_180039BA9
0x180039b94  mov     rcx, rdi; this
0x180039b97  call    ??1NotificationContext@NotificationCallbacks@Client@ComputeService@@QEAA@XZ; ComputeService::Client::NotificationCallbacks::NotificationContext::~NotificationContext(void)
0x180039b9c  mov     edx, 68h ; 'h'; unsigned __int64
0x180039ba1  mov     rcx, rdi; void *
0x180039ba4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180039ba9  mov     al, r15b
0x180039bac  add     rsp, 68h
0x180039bb0  pop     r15
0x180039bb2  pop     r14
0x180039bb4  pop     r13
0x180039bb6  pop     r12
0x180039bb8  pop     rdi
0x180039bb9  pop     rsi
0x180039bba  retn
0x180039bbc  mov     r9d, eax; char *
0x180039bbf  lea     r8, aOnecoreVmCompu_14; "onecore\\vm\\compute\\dll\\lib\\core\\n"...
0x180039bc6  mov     edx, 125h; void *
0x180039bcb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
