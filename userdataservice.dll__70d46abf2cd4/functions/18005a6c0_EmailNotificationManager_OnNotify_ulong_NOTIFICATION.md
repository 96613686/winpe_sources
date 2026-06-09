# EmailNotificationManager::OnNotify(ulong,_NOTIFICATION *)

- ea: `0x18005a6c0`
- end: `0x18005a877`
- name: `?OnNotify@EmailNotificationManager@@UEAAKKPEAU_NOTIFICATION@@@Z`
- size: `439`
- prototype: `unsigned int __fastcall(EmailNotificationManager *__hidden this, unsigned int, struct _NOTIFICATION *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18005a6c0`
- `0x18005a880`
- `0x18007c320`
- `0x18007f160`
- `0x180082f5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a747`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a846`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a747`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a85b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a85b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005a7bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005a7bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005a7a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005a7ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005a7a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005a7ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005a7b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005a7b6`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18005a791`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18005a791`

## pseudocode

```c
__int64 __fastcall EmailNotificationManager::OnNotify(
        EmailNotificationManager *this,
        unsigned int a2,
        struct _NOTIFICATION *a3)
{
  int v3; // edi
  bool v4; // r12
  unsigned int v5; // esi
  __int64 v9; // rcx
  ULONG ulEventType; // edx
  int v11; // esi
  __int64 j; // rcx
  unsigned int v13; // edx
  ULONGLONG TickCount64; // rax
  int v16; // eax
  __int64 v17; // r8
  unsigned int v18[4]; // [rsp+30h] [rbp-78h] BYREF
  __int128 v19; // [rsp+40h] [rbp-68h]
  __int128 i; // [rsp+50h] [rbp-58h]
  int v21; // [rsp+60h] [rbp-48h]

  v3 = 0;
  v4 = 0;
  v21 = 0;
  v5 = 0;
  *(_OWORD *)v18 = 0;
  v19 = 0;
  for ( i = 0; v5 < a2; ++v5 )
  {
    v9 = v5;
    ulEventType = a3[v9].ulEventType;
    if ( ulEventType == 32 || ulEventType == 4 || ulEventType == 8 || ulEventType == 16 || ulEventType == 64 )
    {
      v16 = EmailNotificationManager::_IsRelevantChange(
              this,
              ulEventType,
              (const struct _OBJECT_NOTIFICATION *)&a3[v9].info,
              v4,
              v18);
      if ( v16 < 0 )
        Log_HREvent_9((unsigned int)v16, 0, v17, 437);
      v3 = v21;
    }
    else if ( ulEventType == 0x80000000 )
    {
      v21 = ++v3;
      v4 = 1;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
      utl::_HashTable<unsigned long,utl::pair<unsigned long const,bool>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,bool>>,0>::clear((char *)this + 224);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
    }
  }
  v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  for ( j = 0; j != 13; ++j )
  {
    v13 = v18[j];
    if ( v13 )
    {
      v11 = 1;
      *(_DWORD *)(*((_QWORD *)this + 13) + 4 * j) += v13;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( v11 )
  {
    if ( IsThreadpoolTimerSet(*((PTP_TIMER *)this + 5)) )
    {
      SetThreadpoolTimer(*((PTP_TIMER *)this + 5), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 5), 1);
    }
    TickCount64 = GetTickCount64();
    if ( TickCount64 - _InterlockedCompareExchange64((volatile signed __int64 *)this + 6, 0, 0) >= *((_QWORD *)this + 4) )
    {
      NotificationManagerBase::_NotifyChanges(
        (EmailNotificationManager *)((char *)this + 16),
        _InterlockedExchange((volatile __int32 *)this + 14, 0) + 1);
    }
    else
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 14);
      SetThreadpoolTimer(*((PTP_TIMER *)this + 5), (PFILETIME)this + 3, 0, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005a6c0  mov     rax, rsp
0x18005a6c3  push    rbx
0x18005a6c4  push    rbp
0x18005a6c5  push    rsi
0x18005a6c6  push    rdi
0x18005a6c7  push    r12
0x18005a6c9  push    r14
0x18005a6cb  push    r15
0x18005a6cd  sub     rsp, 70h
0x18005a6d1  xorps   xmm0, xmm0
0x18005a6d4  xor     edi, edi
0x18005a6d6  xor     r12b, r12b
0x18005a6d9  mov     [rax-48h], edi
0x18005a6dc  xor     esi, esi
0x18005a6de  mov     r15, r8
0x18005a6e1  mov     r14d, edx
0x18005a6e4  mov     rbp, rcx
0x18005a6e7  movups  xmmword ptr [rax-78h], xmm0
0x18005a6eb  movups  xmmword ptr [rax-68h], xmm0
0x18005a6ef  movups  xmmword ptr [rax-58h], xmm0
0x18005a6f3  test    edx, edx
0x18005a6f5  jz      short loc_18005A741
0x18005a6f7  mov     eax, esi
0x18005a6f9  imul    rcx, rax, 58h ; 'X'
0x18005a6fd  mov     edx, [rcx+r15]; unsigned int
0x18005a701  cmp     edx, 20h ; ' '
0x18005a704  jz      loc_18005A7F5
0x18005a70a  cmp     edx, 4
0x18005a70d  jz      loc_18005A7F5
0x18005a713  cmp     edx, 8
0x18005a716  jz      loc_18005A7F5
0x18005a71c  cmp     edx, 10h
0x18005a71f  jz      loc_18005A7F5
0x18005a725  cmp     edx, 40h ; '@'
0x18005a728  jz      loc_18005A7F5
0x18005a72e  cmp     edx, 80000000h
0x18005a734  jz      loc_18005A833
0x18005a73a  inc     esi
0x18005a73c  cmp     esi, r14d
0x18005a73f  jb      short loc_18005A6F7
0x18005a741  lea     rcx, [rbp+40h]; lpCriticalSection
0x18005a745  xor     esi, esi
0x18005a747  call    cs:__imp_EnterCriticalSection
0x18005a74d  xor     ecx, ecx
0x18005a74f  mov     edx, [rsp+rcx*4+0A8h+var_78]
0x18005a753  test    edx, edx
0x18005a755  jnz     short loc_18005A77F
0x18005a757  inc     rcx
0x18005a75a  cmp     rcx, 0Dh
0x18005a75e  jnz     short loc_18005A74F
0x18005a760  lea     rcx, [rbp+40h]; lpCriticalSection
0x18005a764  call    cs:__imp_LeaveCriticalSection
0x18005a76a  test    esi, esi
0x18005a76c  jnz     short loc_18005A78D
0x18005a76e  xor     eax, eax
0x18005a770  add     rsp, 70h
0x18005a774  pop     r15
0x18005a776  pop     r14
0x18005a778  pop     r12
0x18005a77a  pop     rdi
0x18005a77b  pop     rsi
0x18005a77c  pop     rbp
0x18005a77d  pop     rbx
0x18005a77e  retn
0x18005a77f  mov     rax, [rbp+68h]
0x18005a783  mov     esi, 1
0x18005a788  add     [rax+rcx*4], edx
0x18005a78b  jmp     short loc_18005A757
0x18005a78d  mov     rcx, [rbp+28h]; pti
0x18005a791  call    cs:__imp_IsThreadpoolTimerSet
0x18005a797  test    eax, eax
0x18005a799  jz      short loc_18005A7BC
0x18005a79b  mov     rcx, [rbp+28h]; pti
0x18005a79f  xor     r9d, r9d; msWindowLength
0x18005a7a2  xor     r8d, r8d; msPeriod
0x18005a7a5  xor     edx, edx; pftDueTime
0x18005a7a7  call    cs:__imp_SetThreadpoolTimer
0x18005a7ad  mov     rcx, [rbp+28h]; pti
0x18005a7b1  mov     edx, 1; fCancelPendingCallbacks
0x18005a7b6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005a7bc  call    cs:__imp_GetTickCount64
0x18005a7c2  xor     ecx, ecx
0x18005a7c4  mov     rdx, rax
0x18005a7c7  xor     eax, eax
0x18005a7c9  lock cmpxchg [rbp+30h], rcx
0x18005a7cf  sub     rdx, rax
0x18005a7d2  cmp     rdx, [rbp+20h]
0x18005a7d6  jnb     short loc_18005A81E
0x18005a7d8  lock inc dword ptr [rbp+38h]
0x18005a7dc  mov     rcx, [rbp+28h]; pti
0x18005a7e0  lea     rdx, [rbp+18h]; pftDueTime
0x18005a7e4  xor     r9d, r9d; msWindowLength
0x18005a7e7  xor     r8d, r8d; msPeriod
0x18005a7ea  call    cs:__imp_SetThreadpoolTimer
0x18005a7f0  jmp     loc_18005A76E
0x18005a7f5  lea     rax, [rsp+0A8h+var_78]
0x18005a7fa  mov     r9b, r12b; bool
0x18005a7fd  lea     r8, [r15+8]
0x18005a801  mov     [rsp+0A8h+var_88], rax; unsigned int *
0x18005a806  add     r8, rcx; struct _OBJECT_NOTIFICATION *
0x18005a809  mov     rcx, rbp; this
0x18005a80c  call    ?_IsRelevantChange@EmailNotificationManager@@AEAAJKAEBU_OBJECT_NOTIFICATION@@_NPEAK@Z; EmailNotificationManager::_IsRelevantChange(ulong,_OBJECT_NOTIFICATION const &,bool,ulong *)
0x18005a811  test    eax, eax
0x18005a813  js      short loc_18005A866
0x18005a815  mov     edi, [rsp+0A8h+var_48]
0x18005a819  jmp     loc_18005A73A
0x18005a81e  xor     edx, edx
0x18005a820  lea     rcx, [rbp+10h]; this
0x18005a824  xchg    edx, [rbp+38h]
0x18005a827  inc     edx; unsigned int
0x18005a829  call    ?_NotifyChanges@NotificationManagerBase@@AEAAXK@Z; NotificationManagerBase::_NotifyChanges(ulong)
0x18005a82e  jmp     loc_18005A76E
0x18005a833  lea     rbx, [rbp+0B8h]
0x18005a83a  inc     edi
0x18005a83c  mov     rcx, rbx; lpCriticalSection
0x18005a83f  mov     [rsp+0A8h+var_48], edi
0x18005a843  mov     r12b, 1
0x18005a846  call    cs:__imp_EnterCriticalSection
0x18005a84c  lea     rcx, [rbp+0E0h]
0x18005a853  call    ?clear@?$_HashTable@KU?$pair@$$CBK_N@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBK_N@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,bool>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,bool>>,0>::clear(void)
0x18005a858  mov     rcx, rbx; lpCriticalSection
0x18005a85b  call    cs:__imp_LeaveCriticalSection
0x18005a861  jmp     loc_18005A73A
0x18005a866  xor     edx, edx
0x18005a868  mov     r9d, 1B5h
0x18005a86e  mov     ecx, eax
0x18005a870  call    Log_HREvent_9
0x18005a875  jmp     short loc_18005A815
```
