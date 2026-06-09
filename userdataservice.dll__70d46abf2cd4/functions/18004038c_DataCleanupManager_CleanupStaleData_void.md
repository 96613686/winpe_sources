# DataCleanupManager::CleanupStaleData(void)

- ea: `0x18004038c`
- end: `0x180040606`
- name: `?CleanupStaleData@DataCleanupManager@@AEAAJXZ`
- size: `634`
- prototype: `__int64 __fastcall(DataCleanupManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180040310`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x18004038c`
- `0x18004060c`
- `0x18004075c`
- `0x180041094`
- `0x180056e94`
- `0x1800574fc`
- `0x180067898`
- `0x18007bad4`
- `0x1800abeec`
- `0x1800acc34`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800403a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004058e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800403a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004058e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800403c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800405db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800405e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800403c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800405db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800405e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800405cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800405cb`
- `unistore!CreateStoreManager` at `0x180040485`
- `unistore!CreateStoreManager` at `0x180040485`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800403cc`
- `UserDataPlatformHelperUtil!IsCommsSystemService` at `0x1800403cc`

## string_xrefs

- `0x1800403d2`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datacleanup.cpp`

## pseudocode

```c
__int64 __fastcall DataCleanupManager::CleanupStaleData(DataCleanupManager *this)
{
  int v2; // ecx
  BOOL v3; // esi
  DWORD dwLowDateTime; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  DWORD v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  struct _FILETIME v20; // rax
  struct _TP_TIMER *v21; // rcx
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+20h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v2 = *((_DWORD *)this + 10);
  if ( v2 )
  {
    v3 = v2 == 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    dwLowDateTime = 0;
    pftDueTime.dwLowDateTime = 0;
    if ( !(unsigned int)IsCommsSystemService() )
    {
      v7 = CheckAnyPackagePendingInstall((int *)&pftDueTime);
      if ( v7 < 0 )
        Log_HREvent(
          (unsigned int)v7,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          599);
      dwLowDateTime = pftDueTime.dwLowDateTime;
    }
    if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x40000) != 0 )
      McTemplateU0tt_EventWriteTransfer(v6, v5, v3, dwLowDateTime);
    if ( !dwLowDateTime )
    {
      v8 = CleanupAppStores(!v3);
      if ( v8 < 0 )
        Log_HREvent(
          (unsigned int)v8,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          608);
      v9 = CleanupCallHistoryData(0, 0);
      if ( v9 < 0 )
        Log_HREvent(
          (unsigned int)v9,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
          609);
    }
    if ( !v3 )
    {
      pftDueTime.dwLowDateTime = *((_DWORD *)this + 16);
      v10 = pftDueTime.dwLowDateTime;
      UserDataServiceTelemetry::CleanupStaleData<int &>(&pftDueTime);
      if ( v10 )
      {
        pftDueTime = 0;
        v11 = CreateStoreManager(0, &pftDueTime);
        v12 = v11;
        if ( v11 < 0 )
        {
          Log_HREvent(
            (unsigned int)v11,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            620);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&pftDueTime);
          return v12;
        }
        v14 = DataCleanupManager::CleanupEmailSearchResults((LPCRITICAL_SECTION)this);
        if ( v14 < 0 )
          Log_HREvent(
            (unsigned int)v14,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            622);
        v15 = DataCleanupManager::CleanupContactSearchResults((LPCRITICAL_SECTION)this);
        if ( v15 < 0 )
          Log_HREvent(
            (unsigned int)v15,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            623);
        v16 = (*(__int64 (__fastcall **)(struct _FILETIME))(**(_QWORD **)&pftDueTime + 152LL))(pftDueTime);
        if ( v16 < 0 )
          Log_HREvent(
            (unsigned int)v16,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            625);
        v17 = (*(__int64 (__fastcall **)(struct _FILETIME))(**(_QWORD **)&pftDueTime + 168LL))(pftDueTime);
        if ( v17 < 0 )
          Log_HREvent(
            (unsigned int)v17,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            627);
        v18 = DataCleanupManager::_DefragmentKnowledgeForAllSyncPartners(this, *(struct IUSStoreManager **)&pftDueTime);
        if ( v18 < 0 )
          Log_HREvent(
            (unsigned int)v18,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            629);
        v19 = DataCleanupManager::CleanupVolatileDirectory((struct _RTL_CRITICAL_SECTION *)this);
        if ( v19 < 0 )
          Log_HREvent(
            (unsigned int)v19,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datacleanup.cpp",
            631);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&pftDueTime);
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    if ( *((_DWORD *)this + 10) )
    {
      v20 = (struct _FILETIME)-12000000000LL;
      if ( *((_DWORD *)this + 10) != 1 )
        v20 = (struct _FILETIME)-864000000000LL;
      v21 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
      pftDueTime = v20;
      SetThreadpoolTimer(v21, &pftDueTime, 0, 0x5265C00u);
      *((_DWORD *)this + 10) = 2;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    return 0;
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    return 2147943515LL;
  }
}

```

## disassembly

```asm
0x18004038c  mov     [rsp-18h+arg_8], rbx
0x180040391  mov     [rsp-18h+arg_10], rsi
0x180040396  push    rbp
0x180040397  push    rdi
0x180040398  push    r14
0x18004039a  mov     rbp, rsp
0x18004039d  sub     rsp, 30h
0x1800403a1  mov     rdi, rcx
0x1800403a4  xor     esi, esi
0x1800403a6  call    cs:__imp_EnterCriticalSection
0x1800403ac  mov     ecx, [rdi+28h]
0x1800403af  test    ecx, ecx
0x1800403b1  jz      loc_1800405E5
0x1800403b7  cmp     ecx, 1
0x1800403ba  jnz     short loc_1800403BE
0x1800403bc  mov     esi, ecx
0x1800403be  mov     rcx, rdi; lpCriticalSection
0x1800403c1  call    cs:__imp_LeaveCriticalSection
0x1800403c7  xor     ebx, ebx
0x1800403c9  mov     [rbp+pftDueTime.dwLowDateTime], ebx
0x1800403cc  call    cs:__imp_IsCommsSystemService
0x1800403d2  lea     r14, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800403d9  test    eax, eax
0x1800403db  jnz     short loc_1800403FF
0x1800403dd  lea     rcx, [rbp+pftDueTime]; int *
0x1800403e1  call    ?CheckAnyPackagePendingInstall@@YAJPEAH@Z; CheckAnyPackagePendingInstall(int *)
0x1800403e6  test    eax, eax
0x1800403e8  jns     short loc_1800403FC
0x1800403ea  mov     r9d, 257h
0x1800403f0  mov     r8, r14
0x1800403f3  xor     edx, edx
0x1800403f5  mov     ecx, eax
0x1800403f7  call    Log_HREvent
0x1800403fc  mov     ebx, [rbp+pftDueTime.dwLowDateTime]
0x1800403ff  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits+2, 4
0x180040406  jz      short loc_180040413
0x180040408  mov     r9d, ebx
0x18004040b  mov     r8d, esi
0x18004040e  call    McTemplateU0tt_EventWriteTransfer
0x180040413  test    ebx, ebx
0x180040415  jnz     short loc_180040458
0x180040417  mov     ecx, esi
0x180040419  xor     edx, edx; int
0x18004041b  xor     ecx, 1; int
0x18004041e  call    ?CleanupAppStores@@YAJHH@Z; CleanupAppStores(int,int)
0x180040423  test    eax, eax
0x180040425  jns     short loc_180040439
0x180040427  mov     r9d, 260h
0x18004042d  mov     r8, r14
0x180040430  xor     edx, edx
0x180040432  mov     ecx, eax
0x180040434  call    Log_HREvent
0x180040439  xor     edx, edx; unsigned __int16 *
0x18004043b  xor     ecx, ecx; unsigned __int16 *
0x18004043d  call    ?CleanupCallHistoryData@@YAJPEBG0@Z; CleanupCallHistoryData(ushort const *,ushort const *)
0x180040442  test    eax, eax
0x180040444  jns     short loc_180040458
0x180040446  mov     r9d, 261h
0x18004044c  mov     r8, r14
0x18004044f  xor     edx, edx
0x180040451  mov     ecx, eax
0x180040453  call    Log_HREvent
0x180040458  test    esi, esi
0x18004045a  jnz     loc_18004058B
0x180040460  mov     ebx, [rdi+40h]
0x180040463  lea     rcx, [rbp+pftDueTime]
0x180040467  mov     [rbp+pftDueTime.dwLowDateTime], ebx
0x18004046a  call    ??$CleanupStaleData@AEAH@UserDataServiceTelemetry@@SAXAEAH@Z; UserDataServiceTelemetry::CleanupStaleData<int &>(int &)
0x18004046f  test    ebx, ebx
0x180040471  jz      loc_18004058B
0x180040477  lea     rdx, [rbp+pftDueTime]
0x18004047b  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x180040483  xor     ecx, ecx
0x180040485  call    cs:__imp_CreateStoreManager
0x18004048b  mov     ebx, eax
0x18004048d  test    eax, eax
0x18004048f  jns     short loc_1800404B4
0x180040491  mov     r9d, 26Ch
0x180040497  lea     edx, [rsi+1]
0x18004049a  mov     r8, r14
0x18004049d  mov     ecx, eax
0x18004049f  call    Log_HREvent
0x1800404a4  lea     rcx, [rbp+pftDueTime]
0x1800404a8  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800404ad  mov     eax, ebx
0x1800404af  jmp     loc_1800405F3
0x1800404b4  mov     rcx, rdi; lpCriticalSection
0x1800404b7  call    ?CleanupEmailSearchResults@DataCleanupManager@@QEAAJXZ; DataCleanupManager::CleanupEmailSearchResults(void)
0x1800404bc  test    eax, eax
0x1800404be  jns     short loc_1800404D2
0x1800404c0  mov     r9d, 26Eh
0x1800404c6  mov     r8, r14
0x1800404c9  xor     edx, edx
0x1800404cb  mov     ecx, eax
0x1800404cd  call    Log_HREvent
0x1800404d2  mov     rcx, rdi; lpCriticalSection
0x1800404d5  call    ?CleanupContactSearchResults@DataCleanupManager@@QEAAJXZ; DataCleanupManager::CleanupContactSearchResults(void)
0x1800404da  test    eax, eax
0x1800404dc  jns     short loc_1800404F0
0x1800404de  mov     r9d, 26Fh
0x1800404e4  mov     r8, r14
0x1800404e7  xor     edx, edx
0x1800404e9  mov     ecx, eax
0x1800404eb  call    Log_HREvent
0x1800404f0  mov     rcx, qword ptr [rbp+pftDueTime.dwLowDateTime]
0x1800404f4  mov     rax, [rcx]
0x1800404f7  mov     rax, [rax+98h]
0x1800404fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040503  test    eax, eax
0x180040505  jns     short loc_180040519
0x180040507  mov     r9d, 271h
0x18004050d  mov     r8, r14
0x180040510  xor     edx, edx
0x180040512  mov     ecx, eax
0x180040514  call    Log_HREvent
0x180040519  mov     rcx, qword ptr [rbp+pftDueTime.dwLowDateTime]
0x18004051d  mov     rax, [rcx]
0x180040520  mov     rax, [rax+0A8h]
0x180040527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004052c  test    eax, eax
0x18004052e  jns     short loc_180040542
0x180040530  mov     r9d, 273h
0x180040536  mov     r8, r14
0x180040539  xor     edx, edx
0x18004053b  mov     ecx, eax
0x18004053d  call    Log_HREvent
0x180040542  mov     rdx, qword ptr [rbp+pftDueTime.dwLowDateTime]; struct IUSStoreManager *
0x180040546  mov     rcx, rdi; this
0x180040549  call    ?_DefragmentKnowledgeForAllSyncPartners@DataCleanupManager@@AEAAJPEAUIUSStoreManager@@@Z; DataCleanupManager::_DefragmentKnowledgeForAllSyncPartners(IUSStoreManager *)
0x18004054e  test    eax, eax
0x180040550  jns     short loc_180040564
0x180040552  mov     r9d, 275h
0x180040558  mov     r8, r14
0x18004055b  xor     edx, edx
0x18004055d  mov     ecx, eax
0x18004055f  call    Log_HREvent
0x180040564  mov     rcx, rdi; this
0x180040567  call    ?CleanupVolatileDirectory@DataCleanupManager@@QEAAJXZ; DataCleanupManager::CleanupVolatileDirectory(void)
0x18004056c  test    eax, eax
0x18004056e  jns     short loc_180040582
0x180040570  mov     r9d, 277h
0x180040576  mov     r8, r14
0x180040579  xor     edx, edx
0x18004057b  mov     ecx, eax
0x18004057d  call    Log_HREvent
0x180040582  lea     rcx, [rbp+pftDueTime]
0x180040586  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18004058b  mov     rcx, rdi; lpCriticalSection
0x18004058e  call    cs:__imp_EnterCriticalSection
0x180040594  cmp     dword ptr [rdi+28h], 0
0x180040598  jz      short loc_1800405D8
0x18004059a  cmp     dword ptr [rdi+28h], 1
0x18004059e  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800405a2  mov     rcx, 0FFFFFF36D5964000h
0x1800405ac  mov     rax, 0FFFFFFFD34BE8800h
0x1800405b6  cmovnz  rax, rcx
0x1800405ba  mov     r9d, 5265C00h; msWindowLength
0x1800405c0  mov     rcx, [rdi+30h]; pti
0x1800405c4  xor     r8d, r8d; msPeriod
0x1800405c7  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x1800405cb  call    cs:__imp_SetThreadpoolTimer
0x1800405d1  mov     dword ptr [rdi+28h], 2
0x1800405d8  mov     rcx, rdi; lpCriticalSection
0x1800405db  call    cs:__imp_LeaveCriticalSection
0x1800405e1  xor     eax, eax
0x1800405e3  jmp     short loc_1800405F3
0x1800405e5  mov     rcx, rdi; lpCriticalSection
0x1800405e8  call    cs:__imp_LeaveCriticalSection
0x1800405ee  mov     eax, 8007045Bh
0x1800405f3  mov     rbx, [rsp+30h+arg_8]
0x1800405f8  mov     rsi, [rsp+30h+arg_10]
0x1800405fd  add     rsp, 30h
0x180040601  pop     r14
0x180040603  pop     rdi
0x180040604  pop     rbp
0x180040605  retn
```
