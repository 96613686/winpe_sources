# ContactNotificationManager::OnEvent(ulong,ulong,PIMEVENT const *)

- ea: `0x180064b80`
- end: `0x180064ce6`
- name: `?OnEvent@ContactNotificationManager@@UEAAJKKPEBUPIMEVENT@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(ContactNotificationManager *__hidden this, unsigned int, unsigned int, const struct PIMEVENT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180064b80`
- `0x180064cec`
- `0x18007c320`
- `0x1800813e8`
- `0x180082f5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064bbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064c9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064bbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064c9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064cb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064cb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064c52`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180064c52`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064c3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064c80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064c3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180064c80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064c4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180064c4c`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180064c27`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180064c27`

## pseudocode

```c
__int64 __fastcall ContactNotificationManager::OnEvent(
        ContactNotificationManager *this,
        char a2,
        unsigned int a3,
        const struct PIMEVENT *a4)
{
  __int64 i; // rbx
  int v8; // esi
  __int64 j; // rcx
  unsigned int v10; // edx
  int v12; // eax
  __int64 v13; // r8
  ULONGLONG TickCount64; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  unsigned int v16[4]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v17; // [rsp+40h] [rbp-48h]
  int v18; // [rsp+50h] [rbp-38h]

  v18 = 0;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  if ( (a2 & 8) != 0 )
  {
    v15 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 168);
    v18 = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
    utl::_HashTable<unsigned long,utl::pair<unsigned long const,bool>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,bool>>,0>::clear((char *)this + 208);
    LeaveCriticalSection(v15);
  }
  else
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v12 = ContactNotificationManager::IsChangeRelevant(this, (const struct PIMEVENT *)((char *)a4 + 96 * i), v16);
      if ( v12 < 0 )
        Log_HREvent_22((unsigned int)v12, 0, v13, 195);
    }
  }
  v8 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  for ( j = 0; j != 9; ++j )
  {
    v10 = v16[j];
    if ( v10 )
    {
      v8 = 1;
      *(_DWORD *)(*((_QWORD *)this + 13) + 4 * j) += v10;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( v8 )
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
        (ContactNotificationManager *)((char *)this + 16),
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
0x180064b80  push    rbx
0x180064b82  push    rbp
0x180064b83  push    rsi
0x180064b84  push    rdi
0x180064b85  sub     rsp, 68h
0x180064b89  xor     eax, eax
0x180064b8b  xorps   xmm0, xmm0
0x180064b8e  mov     [rsp+88h+var_38], eax
0x180064b92  mov     rbp, r9
0x180064b95  mov     esi, r8d
0x180064b98  mov     rdi, rcx
0x180064b9b  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x180064ba0  movups  [rsp+88h+var_48], xmm0
0x180064ba5  test    dl, 8
0x180064ba8  jnz     loc_180064C8B
0x180064bae  xor     ebx, ebx
0x180064bb0  test    r8d, r8d
0x180064bb3  jnz     short loc_180064BFB
0x180064bb5  lea     rcx, [rdi+40h]; lpCriticalSection
0x180064bb9  xor     esi, esi
0x180064bbb  call    cs:__imp_EnterCriticalSection
0x180064bc1  xor     ecx, ecx
0x180064bc3  mov     edx, [rsp+rcx*4+88h+var_58]
0x180064bc7  test    edx, edx
0x180064bc9  jnz     short loc_180064BED
0x180064bcb  inc     rcx
0x180064bce  cmp     rcx, 9
0x180064bd2  jnz     short loc_180064BC3
0x180064bd4  lea     rcx, [rdi+40h]; lpCriticalSection
0x180064bd8  call    cs:__imp_LeaveCriticalSection
0x180064bde  test    esi, esi
0x180064be0  jnz     short loc_180064C23
0x180064be2  xor     eax, eax
0x180064be4  add     rsp, 68h
0x180064be8  pop     rdi
0x180064be9  pop     rsi
0x180064bea  pop     rbp
0x180064beb  pop     rbx
0x180064bec  retn
0x180064bed  mov     rax, [rdi+68h]
0x180064bf1  mov     esi, 1
0x180064bf6  add     [rax+rcx*4], edx
0x180064bf9  jmp     short loc_180064BCB
0x180064bfb  lea     rdx, [rbx+rbx*2]
0x180064bff  mov     rcx, rdi; this
0x180064c02  shl     rdx, 5
0x180064c06  lea     r8, [rsp+88h+var_58]; unsigned int *
0x180064c0b  add     rdx, rbp; struct PIMEVENT *
0x180064c0e  call    ?IsChangeRelevant@ContactNotificationManager@@AEAAJAEBUPIMEVENT@@PEAK@Z; ContactNotificationManager::IsChangeRelevant(PIMEVENT const &,ulong *)
0x180064c13  test    eax, eax
0x180064c15  js      loc_180064CD2
0x180064c1b  inc     ebx
0x180064c1d  cmp     ebx, esi
0x180064c1f  jb      short loc_180064BFB
0x180064c21  jmp     short loc_180064BB5
0x180064c23  mov     rcx, [rdi+28h]; pti
0x180064c27  call    cs:__imp_IsThreadpoolTimerSet
0x180064c2d  test    eax, eax
0x180064c2f  jz      short loc_180064C52
0x180064c31  mov     rcx, [rdi+28h]; pti
0x180064c35  xor     r9d, r9d; msWindowLength
0x180064c38  xor     r8d, r8d; msPeriod
0x180064c3b  xor     edx, edx; pftDueTime
0x180064c3d  call    cs:__imp_SetThreadpoolTimer
0x180064c43  mov     rcx, [rdi+28h]; pti
0x180064c47  mov     edx, 1; fCancelPendingCallbacks
0x180064c4c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180064c52  call    cs:__imp_GetTickCount64
0x180064c58  xor     ecx, ecx
0x180064c5a  mov     rdx, rax
0x180064c5d  xor     eax, eax
0x180064c5f  lock cmpxchg [rdi+30h], rcx
0x180064c65  sub     rdx, rax
0x180064c68  cmp     rdx, [rdi+20h]
0x180064c6c  jnb     short loc_180064CBD
0x180064c6e  lock inc dword ptr [rdi+38h]
0x180064c72  mov     rcx, [rdi+28h]; pti
0x180064c76  lea     rdx, [rdi+18h]; pftDueTime
0x180064c7a  xor     r9d, r9d; msWindowLength
0x180064c7d  xor     r8d, r8d; msPeriod
0x180064c80  call    cs:__imp_SetThreadpoolTimer
0x180064c86  jmp     loc_180064BE2
0x180064c8b  lea     rbx, [rcx+0A8h]
0x180064c92  mov     [rsp+88h+var_38], 1
0x180064c9a  mov     rcx, rbx; lpCriticalSection
0x180064c9d  call    cs:__imp_EnterCriticalSection
0x180064ca3  lea     rcx, [rdi+0D0h]
0x180064caa  call    ?clear@?$_HashTable@KU?$pair@$$CBK_N@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBK_N@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,bool>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,bool>>,0>::clear(void)
0x180064caf  mov     rcx, rbx; lpCriticalSection
0x180064cb2  call    cs:__imp_LeaveCriticalSection
0x180064cb8  jmp     loc_180064BB5
0x180064cbd  xor     edx, edx
0x180064cbf  lea     rcx, [rdi+10h]; this
0x180064cc3  xchg    edx, [rdi+38h]
0x180064cc6  inc     edx; unsigned int
0x180064cc8  call    ?_NotifyChanges@NotificationManagerBase@@AEAAXK@Z; NotificationManagerBase::_NotifyChanges(ulong)
0x180064ccd  jmp     loc_180064BE2
0x180064cd2  xor     edx, edx
0x180064cd4  mov     r9d, 0C3h
0x180064cda  mov     ecx, eax
0x180064cdc  call    Log_HREvent_22
0x180064ce1  jmp     loc_180064C1B
```
