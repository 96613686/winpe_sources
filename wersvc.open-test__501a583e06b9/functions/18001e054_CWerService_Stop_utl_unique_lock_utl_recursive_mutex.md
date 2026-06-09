# CWerService::_Stop(utl::unique_lock<utl::recursive_mutex> &)

- ea: `0x18001e054`
- end: `0x18001e1c9`
- name: `?_Stop@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(CWerService *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800181f8`
- `0x180018a70`
- `0x18001d92c`

## callees

- `0x18000cb10`
- `0x180014008`
- `0x18001d7c0`
- `0x18001e054`
- `0x18001e1d0`
- `0x18002d1f0`
- `0x18002de78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e0c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e0c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e095`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e142`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e142`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001e0b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001e0b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001e0a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001e0a9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001e115`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001e115`

## string_xrefs

- `0x18001e183`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWerService::_Stop(struct _TP_CLEANUP_GROUP **this, __int64 a2, unsigned int a3)
{
  struct _TP_CLEANUP_GROUP *v5; // rsi
  __int64 result; // rax
  struct _TP_CLEANUP_GROUP *v7; // rcx
  struct _TP_CLEANUP_GROUP *v8; // rcx
  struct _TP_CLEANUP_GROUP *v9; // rcx
  __int64 v10; // rdx
  int inited; // eax
  unsigned int v12; // r8d
  int v13; // [rsp+20h] [rbp-28h] BYREF
  __m128i si128; // [rsp+28h] [rbp-20h] BYREF
  __int64 v15; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  CWerService::_SetServiceStatus((CWerService *)this, 3u, a3);
  v5 = this[28];
  if ( v5 )
  {
    this[28] = 0;
    if ( !*(_BYTE *)(a2 + 8) )
      __int2c();
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)a2);
    *(_BYTE *)(a2 + 8) = 0;
    CloseThreadpoolCleanupGroupMembers(v5, 1, 0);
    CloseThreadpoolCleanupGroup(v5);
    if ( !*(_QWORD *)a2 || *(_BYTE *)(a2 + 8) )
      __int2c();
    EnterCriticalSection(*(LPCRITICAL_SECTION *)a2);
    *(_BYTE *)(a2 + 8) = 1;
  }
  result = CWerService::_SuspendWork(this, a2);
  if ( (int)result >= 0 )
  {
    v7 = this[43];
    this[43] = 0;
    if ( (unsigned __int64)v7 + 1 > 1 )
      CloseHandle(v7);
    v8 = this[42];
    if ( v8 )
    {
      UnregisterWaitEx(v8, 0);
      this[42] = 0;
    }
    v9 = this[41];
    this[41] = 0;
    if ( (unsigned __int64)v9 + 1 > 1 )
      CloseHandle(v9);
    CHandleMonitor::Cleanup((CHandleMonitor *)(this + 10));
    LOBYTE(v13) = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v15 = -1;
    inited = TerminationStore::InitStore((TerminationStore *)&v13, v10);
    if ( inited < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
        (const char *)(unsigned int)inited,
        v13);
    utl::vector<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>,utl::allocator<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>>>::~vector<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>,utl::allocator<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>>>(&si128);
    CWerService::_SetServiceStatus((CWerService *)this, 1u, v12);
    this[38] = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001e054  mov     [rsp+arg_0], rbx
0x18001e059  mov     [rsp+arg_8], rsi
0x18001e05e  push    rdi
0x18001e05f  sub     rsp, 40h
0x18001e063  mov     rdi, rdx
0x18001e066  mov     rbx, rcx
0x18001e069  mov     edx, 3; unsigned int
0x18001e06e  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x18001e073  mov     rsi, [rbx+0E0h]
0x18001e07a  test    rsi, rsi
0x18001e07d  jz      short loc_18001E0D2
0x18001e07f  mov     qword ptr [rbx+0E0h], 0
0x18001e08a  cmp     byte ptr [rdi+8], 0
0x18001e08e  jnz     short loc_18001E092
0x18001e090  int     2Ch; Windows NT - assertion failure
0x18001e092  mov     rcx, [rdi]; lpCriticalSection
0x18001e095  call    cs:__imp_LeaveCriticalSection
0x18001e09b  mov     byte ptr [rdi+8], 0
0x18001e09f  xor     r8d, r8d; pvCleanupContext
0x18001e0a2  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18001e0a6  mov     rcx, rsi; ptpcg
0x18001e0a9  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001e0af  mov     rcx, rsi; ptpcg
0x18001e0b2  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001e0b8  mov     rcx, [rdi]; lpCriticalSection
0x18001e0bb  test    rcx, rcx
0x18001e0be  jz      short loc_18001E0C6
0x18001e0c0  cmp     byte ptr [rdi+8], 0
0x18001e0c4  jz      short loc_18001E0C8
0x18001e0c6  int     2Ch; Windows NT - assertion failure
0x18001e0c8  call    cs:__imp_EnterCriticalSection
0x18001e0ce  mov     byte ptr [rdi+8], 1
0x18001e0d2  mov     rdx, rdi
0x18001e0d5  mov     rcx, rbx
0x18001e0d8  call    ?_SuspendWork@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_SuspendWork(utl::unique_lock<utl::recursive_mutex> &)
0x18001e0dd  test    eax, eax
0x18001e0df  js      loc_18001E1B9
0x18001e0e5  mov     rcx, [rbx+158h]; hObject
0x18001e0ec  mov     qword ptr [rbx+158h], 0
0x18001e0f7  lea     rax, [rcx+1]
0x18001e0fb  cmp     rax, 1
0x18001e0ff  jbe     short loc_18001E107
0x18001e101  call    cs:__imp_CloseHandle
0x18001e107  mov     rcx, [rbx+150h]; WaitHandle
0x18001e10e  test    rcx, rcx
0x18001e111  jz      short loc_18001E126
0x18001e113  xor     edx, edx; CompletionEvent
0x18001e115  call    cs:__imp_UnregisterWaitEx
0x18001e11b  mov     qword ptr [rbx+150h], 0
0x18001e126  mov     rcx, [rbx+148h]; hObject
0x18001e12d  mov     qword ptr [rbx+148h], 0
0x18001e138  lea     rax, [rcx+1]
0x18001e13c  cmp     rax, 1
0x18001e140  jbe     short loc_18001E148
0x18001e142  call    cs:__imp_CloseHandle
0x18001e148  lea     rcx, [rbx+50h]; this
0x18001e14c  call    ?Cleanup@CHandleMonitor@@QEAAJXZ; CHandleMonitor::Cleanup(void)
0x18001e151  mov     byte ptr [rsp+48h+var_28], 0; int
0x18001e156  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18001e15e  movdqu  [rsp+48h+var_20], xmm0
0x18001e164  mov     [rsp+48h+var_10], 0FFFFFFFFFFFFFFFFh
0x18001e16d  lea     rcx, [rsp+48h+var_28]; this
0x18001e172  call    ?InitStore@TerminationStore@@AEAAJXZ; TerminationStore::InitStore(void)
0x18001e177  test    eax, eax
0x18001e179  jns     short loc_18001E195
0x18001e17b  mov     rcx, [rsp+48h]; this
0x18001e180  mov     r9d, eax; char *
0x18001e183  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18001e18a  mov     edx, 20h ; ' '; void *
0x18001e18f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e194  nop
0x18001e195  lea     rcx, [rsp+48h+var_20]
0x18001e19a  call    ??1?$vector@V?$unique_ptr@UTerminationItem@@U?$default_delete@UTerminationItem@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UTerminationItem@@U?$default_delete@UTerminationItem@@@utl@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>,utl::allocator<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>>>::~vector<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>,utl::allocator<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>>>(void)
0x18001e19f  mov     edx, 1; unsigned int
0x18001e1a4  mov     rcx, rbx; this
0x18001e1a7  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x18001e1ac  mov     qword ptr [rbx+130h], 0
0x18001e1b7  xor     eax, eax
0x18001e1b9  mov     rbx, [rsp+48h+arg_0]
0x18001e1be  mov     rsi, [rsp+48h+arg_8]
0x18001e1c3  add     rsp, 40h
0x18001e1c7  pop     rdi
0x18001e1c8  retn
```
