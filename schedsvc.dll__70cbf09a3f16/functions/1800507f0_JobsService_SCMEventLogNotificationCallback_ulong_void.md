# JobsService::SCMEventLogNotificationCallback(ulong,void *)

- ea: `0x1800507f0`
- end: `0x1800508de`
- name: `?SCMEventLogNotificationCallback@JobsService@@CAXKPEAX@Z`
- size: `238`
- prototype: `static void(unsigned int, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800507f0`
- `0x180050a38`
- `0x180054084`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005088f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005088f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005084e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005084e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800508c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800508c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180050865`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180050865`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800508b9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800508b9`

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
    _InterlockedExchange(&v6, _InterlockedCompareExchange(&dword_1800BD53C, 0, 0) != 0);
    if ( _InterlockedCompareExchange(&v6, 0, 0) )
    {
      v3 = (RTL_SRWLOCK *)(a2 + 264);
      AcquireSRWLockExclusive((PSRWLOCK)a2 + 33);
      ThreadpoolWork = CreateThreadpoolWork(
                         (PTP_WORK_CALLBACK)JobsService::SCMEventLogNotificationWorker,
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
0x1800507f0  test    cl, 9
0x1800507f3  jz      locret_1800508DD
0x1800507f9  mov     [rsp+arg_8], rbx
0x1800507fe  push    rdi
0x1800507ff  sub     rsp, 20h
0x180050803  xchg    ecx, cs:?s_dwLastNotificationMaskReceived@JobsService@@0KA; ulong JobsService::s_dwLastNotificationMaskReceived
0x180050809  xor     eax, eax
0x18005080b  mov     [rsp+28h+arg_0], 0
0x180050813  xchg    eax, [rsp+28h+arg_0]
0x180050817  mov     rdi, rdx
0x18005081a  lock inc cs:?s_sync@ShutdownMgr@@0USync@1@A; ShutdownMgr::Sync ShutdownMgr::s_sync
0x180050821  xor     ecx, ecx
0x180050823  xor     eax, eax
0x180050825  lock cmpxchg cs:dword_1800BD53C, ecx
0x18005082d  setnz   cl
0x180050830  xchg    ecx, [rsp+28h+arg_0]
0x180050834  xor     ecx, ecx
0x180050836  xor     eax, eax
0x180050838  lock cmpxchg [rsp+28h+arg_0], ecx
0x18005083e  jz      loc_1800508C8
0x180050844  lea     rbx, [rdx+108h]
0x18005084b  mov     rcx, rbx; SRWLock
0x18005084e  call    cs:__imp_AcquireSRWLockExclusive
0x180050854  lea     r8, [rdi+0B8h]; pcbe
0x18005085b  mov     rdx, rdi; pv
0x18005085e  lea     rcx, ?SCMEventLogNotificationWorker@JobsService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180050865  call    cs:__imp_CreateThreadpoolWork
0x18005086b  test    rax, rax
0x18005086e  jnz     short loc_1800508B6
0x180050870  mov     rax, cs:WPP_GLOBAL_Control
0x180050877  lea     rcx, WPP_GLOBAL_Control
0x18005087e  cmp     rax, rcx
0x180050881  jz      short loc_1800508BF
0x180050883  test    byte ptr [rax+1Ch], 4
0x180050887  jz      short loc_1800508BF
0x180050889  cmp     byte ptr [rax+19h], 2
0x18005088d  jb      short loc_1800508BF
0x18005088f  call    cs:__imp_GetLastError
0x180050895  mov     rcx, cs:WPP_GLOBAL_Control
0x18005089c  lea     r8, WPP_e3966bf9b81b3ab085a9dfdc4dace9ef_Traceguids
0x1800508a3  mov     edx, 1Dh
0x1800508a8  mov     r9d, eax
0x1800508ab  mov     rcx, [rcx+10h]
0x1800508af  call    WPP_SF_d
0x1800508b4  jmp     short loc_1800508BF
0x1800508b6  mov     rcx, rax; pwk
0x1800508b9  call    cs:__imp_SubmitThreadpoolWork
0x1800508bf  mov     rcx, rbx; SRWLock
0x1800508c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800508c8  xor     eax, eax
0x1800508ca  xchg    eax, [rsp+28h+arg_0]
0x1800508ce  call    ?Unguard@ShutdownMgr@@KAXXZ; ShutdownMgr::Unguard(void)
0x1800508d3  mov     rbx, [rsp+28h+arg_8]
0x1800508d8  add     rsp, 20h
0x1800508dc  pop     rdi
0x1800508dd  retn
```
