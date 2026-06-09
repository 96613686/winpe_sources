# AppointmentNotificationManager::OnEvent(ulong,ulong,PIMEVENT const *)

- ea: `0x18005b1e0`
- end: `0x18005b347`
- name: `?OnEvent@AppointmentNotificationManager@@UEAAJKKPEBUPIMEVENT@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(AppointmentNotificationManager *__hidden this, unsigned int, unsigned int, const struct PIMEVENT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18005b1e0`
- `0x18005b350`
- `0x1800729b8`
- `0x18007c320`
- `0x180082f5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b247`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b2fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b247`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005b2fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b264`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b264`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005b313`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005b2b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005b2b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b2a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b2e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b2a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b2e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005b2b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005b2b0`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18005b28b`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18005b28b`

## pseudocode

```c
__int64 __fastcall AppointmentNotificationManager::OnEvent(
        AppointmentNotificationManager *this,
        char a2,
        unsigned int a3,
        const struct PIMEVENT *a4)
{
  __int64 i; // rbx
  int v8; // eax
  __int64 v9; // r8
  int v10; // esi
  __int64 j; // rcx
  unsigned int v12; // edx
  ULONGLONG TickCount64; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  unsigned int v16[4]; // [rsp+30h] [rbp-68h] BYREF
  __int128 v17; // [rsp+40h] [rbp-58h]
  __int128 v18; // [rsp+50h] [rbp-48h]
  __int64 v19; // [rsp+60h] [rbp-38h]

  v19 = 0;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( (a2 & 8) != 0 )
  {
    v15 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 168);
    HIDWORD(v19) = 1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
    utl::_HashTable<unsigned long,utl::pair<unsigned long const,bool>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,bool>>,0>::clear((char *)this + 248);
    LeaveCriticalSection(v15);
  }
  else
  {
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v8 = AppointmentNotificationManager::IsChangeRelevant(this, (const struct PIMEVENT *)((char *)a4 + 96 * i), v16);
      if ( v8 < 0 )
        Log_HREvent_2((unsigned int)v8, 0, v9, 279);
    }
  }
  v10 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  for ( j = 0; j != 14; ++j )
  {
    v12 = v16[j];
    if ( v12 )
    {
      v10 = 1;
      *(_DWORD *)(*((_QWORD *)this + 13) + 4 * j) += v12;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( v10 )
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
        (AppointmentNotificationManager *)((char *)this + 16),
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
0x18005b1e0  push    rbx
0x18005b1e2  push    rbp
0x18005b1e3  push    rsi
0x18005b1e4  push    rdi
0x18005b1e5  sub     rsp, 78h
0x18005b1e9  xorps   xmm0, xmm0
0x18005b1ec  xor     eax, eax
0x18005b1ee  mov     [rsp+98h+var_38], rax
0x18005b1f3  mov     rbp, r9
0x18005b1f6  mov     esi, r8d
0x18005b1f9  mov     rdi, rcx
0x18005b1fc  movups  xmmword ptr [rsp+98h+var_68], xmm0
0x18005b201  movups  [rsp+98h+var_58], xmm0
0x18005b206  movups  [rsp+98h+var_48], xmm0
0x18005b20b  test    dl, 8
0x18005b20e  jnz     loc_18005B2EC
0x18005b214  xor     ebx, ebx
0x18005b216  test    r8d, r8d
0x18005b219  jz      short loc_18005B241
0x18005b21b  lea     rdx, [rbx+rbx*2]
0x18005b21f  mov     rcx, rdi; this
0x18005b222  shl     rdx, 5
0x18005b226  lea     r8, [rsp+98h+var_68]; unsigned int *
0x18005b22b  add     rdx, rbp; struct PIMEVENT *
0x18005b22e  call    ?IsChangeRelevant@AppointmentNotificationManager@@AEAAJAEBUPIMEVENT@@PEAK@Z; AppointmentNotificationManager::IsChangeRelevant(PIMEVENT const &,ulong *)
0x18005b233  test    eax, eax
0x18005b235  js      loc_18005B333
0x18005b23b  inc     ebx
0x18005b23d  cmp     ebx, esi
0x18005b23f  jb      short loc_18005B21B
0x18005b241  lea     rcx, [rdi+40h]; lpCriticalSection
0x18005b245  xor     esi, esi
0x18005b247  call    cs:__imp_EnterCriticalSection
0x18005b24d  xor     ecx, ecx
0x18005b24f  mov     edx, [rsp+rcx*4+98h+var_68]
0x18005b253  test    edx, edx
0x18005b255  jnz     short loc_18005B279
0x18005b257  inc     rcx
0x18005b25a  cmp     rcx, 0Eh
0x18005b25e  jnz     short loc_18005B24F
0x18005b260  lea     rcx, [rdi+40h]; lpCriticalSection
0x18005b264  call    cs:__imp_LeaveCriticalSection
0x18005b26a  test    esi, esi
0x18005b26c  jnz     short loc_18005B287
0x18005b26e  xor     eax, eax
0x18005b270  add     rsp, 78h
0x18005b274  pop     rdi
0x18005b275  pop     rsi
0x18005b276  pop     rbp
0x18005b277  pop     rbx
0x18005b278  retn
0x18005b279  mov     rax, [rdi+68h]
0x18005b27d  mov     esi, 1
0x18005b282  add     [rax+rcx*4], edx
0x18005b285  jmp     short loc_18005B257
0x18005b287  mov     rcx, [rdi+28h]; pti
0x18005b28b  call    cs:__imp_IsThreadpoolTimerSet
0x18005b291  test    eax, eax
0x18005b293  jz      short loc_18005B2B6
0x18005b295  mov     rcx, [rdi+28h]; pti
0x18005b299  xor     r9d, r9d; msWindowLength
0x18005b29c  xor     r8d, r8d; msPeriod
0x18005b29f  xor     edx, edx; pftDueTime
0x18005b2a1  call    cs:__imp_SetThreadpoolTimer
0x18005b2a7  mov     rcx, [rdi+28h]; pti
0x18005b2ab  mov     edx, 1; fCancelPendingCallbacks
0x18005b2b0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005b2b6  call    cs:__imp_GetTickCount64
0x18005b2bc  xor     ecx, ecx
0x18005b2be  mov     rdx, rax
0x18005b2c1  xor     eax, eax
0x18005b2c3  lock cmpxchg [rdi+30h], rcx
0x18005b2c9  sub     rdx, rax
0x18005b2cc  cmp     rdx, [rdi+20h]
0x18005b2d0  jnb     short loc_18005B31E
0x18005b2d2  lock inc dword ptr [rdi+38h]
0x18005b2d6  mov     rcx, [rdi+28h]; pti
0x18005b2da  lea     rdx, [rdi+18h]; pftDueTime
0x18005b2de  xor     r9d, r9d; msWindowLength
0x18005b2e1  xor     r8d, r8d; msPeriod
0x18005b2e4  call    cs:__imp_SetThreadpoolTimer
0x18005b2ea  jmp     short loc_18005B26E
0x18005b2ec  lea     rbx, [rcx+0A8h]
0x18005b2f3  mov     dword ptr [rsp+98h+var_38+4], 1
0x18005b2fb  mov     rcx, rbx; lpCriticalSection
0x18005b2fe  call    cs:__imp_EnterCriticalSection
0x18005b304  lea     rcx, [rdi+0F8h]
0x18005b30b  call    ?clear@?$_HashTable@KU?$pair@$$CBK_N@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBK_N@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,bool>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,bool>>,0>::clear(void)
0x18005b310  mov     rcx, rbx; lpCriticalSection
0x18005b313  call    cs:__imp_LeaveCriticalSection
0x18005b319  jmp     loc_18005B241
0x18005b31e  xor     edx, edx
0x18005b320  lea     rcx, [rdi+10h]; this
0x18005b324  xchg    edx, [rdi+38h]
0x18005b327  inc     edx; unsigned int
0x18005b329  call    ?_NotifyChanges@NotificationManagerBase@@AEAAXK@Z; NotificationManagerBase::_NotifyChanges(ulong)
0x18005b32e  jmp     loc_18005B26E
0x18005b333  xor     edx, edx
0x18005b335  mov     r9d, 117h
0x18005b33b  mov     ecx, eax
0x18005b33d  call    Log_HREvent_2
0x18005b342  jmp     loc_18005B23B
```
