# JobsService::SCMEventLogNotificationCallback(ulong,void *)

- ea: `0x180052d30`
- end: `0x180052e3d`
- name: `?SCMEventLogNotificationCallback@JobsService@@CAXKPEAX@Z`
- size: `269`
- prototype: `static void(unsigned int, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180052d30`
- `0x180052f98`
- `0x180056954`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052ddb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180052d8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180052d8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052e1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052e1a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180052dab`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180052dab`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180052e0b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180052e0b`

## pseudocode

```c
void __fastcall JobsService::SCMEventLogNotificationCallback(char a1, char *a2)
{
  RTL_SRWLOCK *v3; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  DWORD LastError; // eax
  __int32 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( (a1 & 9) != 0 )
  {
    _InterlockedExchange((volatile __int32 *)&JobsService::s_dwLastNotificationMaskReceived, a1);
    v6 = 0;
    _InterlockedExchange(&v6, 0);
    _InterlockedIncrement((volatile signed __int32 *)&ShutdownMgr::s_sync);
    _InterlockedExchange(&v6, _InterlockedCompareExchange(&dword_1800C163C, 0, 0) != 0);
    if ( _InterlockedCompareExchange(&v6, 0, 0) )
    {
      v3 = (RTL_SRWLOCK *)(a2 + 264);
      AcquireSRWLockExclusive((PSRWLOCK)a2 + 33);
      ThreadpoolWork = CreateThreadpoolWork(
                         JobsService::SCMEventLogNotificationWorker,
                         a2,
                         (PTP_CALLBACK_ENVIRON)(a2 + 184));
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids, LastError);
      }
      ReleaseSRWLockExclusive(v3);
    }
    _InterlockedExchange(&v6, 0);
    ShutdownMgr::Unguard();
  }
}

```

## disassembly

```asm
0x180052d30  test    cl, 9
0x180052d33  jz      locret_180052E3B
0x180052d39  mov     [rsp+arg_8], rbx
0x180052d3e  push    rdi
0x180052d3f  sub     rsp, 20h
0x180052d43  xchg    ecx, cs:?s_dwLastNotificationMaskReceived@JobsService@@0KA; ulong JobsService::s_dwLastNotificationMaskReceived
0x180052d49  xor     eax, eax
0x180052d4b  mov     [rsp+28h+arg_0], 0
0x180052d53  xchg    eax, [rsp+28h+arg_0]
0x180052d57  mov     rdi, rdx
0x180052d5a  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x180052d61  xor     ecx, ecx
0x180052d63  xor     eax, eax
0x180052d65  lock cmpxchg cs:dword_1800C163C, ecx
0x180052d6d  setnz   cl
0x180052d70  xchg    ecx, [rsp+28h+arg_0]
0x180052d74  xor     ecx, ecx
0x180052d76  xor     eax, eax
0x180052d78  lock cmpxchg [rsp+28h+arg_0], ecx
0x180052d7e  jz      loc_180052E26
0x180052d84  lea     rbx, [rdx+108h]
0x180052d8b  mov     rcx, rbx; SRWLock
0x180052d8e  call    cs:__imp_AcquireSRWLockExclusive
0x180052d95  nop     dword ptr [rax+rax+00h]
0x180052d9a  lea     r8, [rdi+0B8h]; pcbe
0x180052da1  mov     rdx, rdi; pv
0x180052da4  lea     rcx, ?SCMEventLogNotificationWorker@JobsService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180052dab  call    cs:__imp_CreateThreadpoolWork
0x180052db2  nop     dword ptr [rax+rax+00h]
0x180052db7  test    rax, rax
0x180052dba  jnz     short loc_180052E08
0x180052dbc  mov     rax, cs:WPP_GLOBAL_Control
0x180052dc3  lea     rcx, WPP_GLOBAL_Control
0x180052dca  cmp     rax, rcx
0x180052dcd  jz      short loc_180052E17
0x180052dcf  test    byte ptr [rax+1Ch], 4
0x180052dd3  jz      short loc_180052E17
0x180052dd5  cmp     byte ptr [rax+19h], 2
0x180052dd9  jb      short loc_180052E17
0x180052ddb  call    cs:__imp_GetLastError
0x180052de2  nop     dword ptr [rax+rax+00h]
0x180052de7  mov     rcx, cs:WPP_GLOBAL_Control
0x180052dee  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x180052df5  mov     edx, 1Dh
0x180052dfa  mov     r9d, eax
0x180052dfd  mov     rcx, [rcx+10h]
0x180052e01  call    WPP_SF_d
0x180052e06  jmp     short loc_180052E17
0x180052e08  mov     rcx, rax; pwk
0x180052e0b  call    cs:__imp_SubmitThreadpoolWork
0x180052e12  nop     dword ptr [rax+rax+00h]
0x180052e17  mov     rcx, rbx; SRWLock
0x180052e1a  call    cs:__imp_ReleaseSRWLockExclusive
0x180052e21  nop     dword ptr [rax+rax+00h]
0x180052e26  xor     eax, eax
0x180052e28  xchg    eax, [rsp+28h+arg_0]
0x180052e2c  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x180052e31  mov     rbx, [rsp+28h+arg_8]
0x180052e36  add     rsp, 20h
0x180052e3a  pop     rdi
0x180052e3b  retn
```
