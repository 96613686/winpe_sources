# DBLockManager::_AcquireLocks(CallerId const &,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *,DB_LOCK_TYPE const *,int *)

- ea: `0x180027e7c`
- end: `0x180028251`
- name: `?_AcquireLocks@DBLockManager@@AEAAJAEBUCallerId@@KPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@PEBW4DB_LOCK_TYPE@@PEAH@Z`
- size: `981`
- prototype: `__int64 __fastcall(DBLockManager *__hidden this, const struct CallerId *, unsigned int, const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *, const enum DB_LOCK_TYPE *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026870`

## callees

- `0x180002e50`
- `0x180004fc0`
- `0x180005490`
- `0x180022ee0`
- `0x1800253f0`
- `0x180027e7c`
- `0x1800282c0`
- `0x1800287b8`
- `0x180028990`
- `0x1800514c0`
- `0x180062674`
- `0x18006f180`
- `0x180072d34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027ef2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027ef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280c8`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x1800280ba`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x1800280ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002805d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180028206`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002805d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180028206`

## string_xrefs

- `0x180027eac`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180027f54`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180027fa7`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180028036`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x1800281f8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x18002821a`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBLockManager::_AcquireLocks(
        DBLockManager *this,
        const struct CallerId *a2,
        unsigned int a3,
        const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *a4,
        const enum DB_LOCK_TYPE *a5,
        int *a6)
{
  const enum DB_LOCK_TYPE *v10; // r14
  int v11; // eax
  int v12; // r8d
  unsigned int v13; // ebx
  ULONGLONG TickCount64; // r15
  signed int IsShuttingDown; // edi
  int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rdi
  int v19; // r14d
  __int64 v20; // rcx
  __int64 i; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // r9d
  __int64 v25; // r8
  int v26; // eax
  int v28; // eax
  __int64 v29; // rcx
  int v30; // r14d
  signed int LastError; // eax
  int v32; // r8d
  char v33; // di
  int v34; // ecx
  __int64 v35; // r8
  int ProcessIdFromCallerId; // eax
  int v37; // r8d
  int v38; // r9d
  int v39; // edx
  signed int v40; // ecx
  __int64 v41; // rcx
  int v42; // [rsp+20h] [rbp-58h]
  __int64 v43; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v44[16]; // [rsp+38h] [rbp-40h] BYREF
  int v45; // [rsp+90h] [rbp+18h] BYREF
  enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *v46; // [rsp+98h] [rbp+20h]

  v46 = a4;
  if ( !a3 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
      698);
  v10 = a5;
  v11 = DBLockManager::_ValidateLocks(this, a2, a3, a4, a5);
  v13 = v11;
  if ( v11 < 0 )
  {
    Log_UnistoreHREvent(v11, 1, v12, 700, v42);
    return v13;
  }
  v45 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  TickCount64 = 0;
  while ( 1 )
  {
    IsShuttingDown = FailIfServiceIsShuttingDown();
    if ( IsShuttingDown < 0 )
    {
      v38 = 713;
      v39 = 1;
      goto LABEL_61;
    }
    if ( (unsigned int)IsAssociatedWithTerminatedProcess(*(_DWORD *)a2) )
    {
      IsShuttingDown = -2147483622;
      v38 = 718;
      goto LABEL_59;
    }
    if ( !utl::recursive_mutex::_IsOwnedByCurrentThread((DBLockManager *)((char *)this + 8)) )
      Log_AssertionEvent(
        v17,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        722);
    v18 = 0;
LABEL_10:
    if ( (unsigned int)v18 >= a3 )
      break;
    v19 = *((_DWORD *)v46 + v18);
    if ( !utl::recursive_mutex::_IsOwnedByCurrentThread((DBLockManager *)((char *)this + 8)) )
      Log_AssertionEvent(
        v20,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        661);
    if ( v19 == 2147483640 )
      Log_AssertionEvent(
        v20,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        664);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *((_DWORD *)this + 14) )
        goto LABEL_20;
      v22 = 56LL * (unsigned int)i;
      v23 = *((_QWORD *)this + 8);
      if ( v19 == *(_DWORD *)(v22 + v23) )
        break;
    }
    v24 = *(_DWORD *)(v22 + v23 + 4);
    v25 = *((_QWORD *)this + 8);
    if ( !v24 )
    {
LABEL_20:
      v10 = a5;
LABEL_21:
      v18 = (unsigned int)(v18 + 1);
      goto LABEL_10;
    }
    if ( v24 == 1 )
    {
      if ( *(_DWORD *)a2 != *(_DWORD *)(v22 + v23 + 8) )
        goto LABEL_31;
      if ( *((_DWORD *)a2 + 1) == *(_DWORD *)(v22 + v25 + 12) )
        goto LABEL_20;
    }
    if ( v24 == 2 )
    {
      v10 = a5;
      if ( !*((_DWORD *)a5 + v18) )
        goto LABEL_21;
    }
LABEL_31:
    v30 = *(_DWORD *)LockEntries::operator[]((char *)this + 56, i, v25);
    if ( !TickCount64 )
      TickCount64 = GetTickCount64();
    if ( (unsigned int)v45 > 0xDBBA0 )
    {
      Log_AssertionEvent(
        v29,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
        769);
      v38 = 770;
      IsShuttingDown = -2147023436;
LABEL_59:
      v39 = 0;
LABEL_61:
      v40 = IsShuttingDown;
      goto LABEL_51;
    }
    if ( SleepConditionVariableCS((PCONDITION_VARIABLE)this + 6, (PCRITICAL_SECTION)((char *)this + 8), 0x7530u) )
      goto LABEL_44;
    LastError = GetLastError();
    IsShuttingDown = LastError;
    if ( LastError != 1460 && LastError != 258 )
    {
      if ( LastError > 0 )
        IsShuttingDown = (unsigned __int16)LastError | 0x80070000;
      Log_UnistoreHREvent(IsShuttingDown, 0, v32, 799, v42);
      if ( !IsShuttingDown )
        Log_AssertionEvent(
          v41,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dblockmanager.cpp",
          799);
      goto LABEL_52;
    }
    v33 = 0;
    LODWORD(v43) = 0;
    v44[0] = 0;
    if ( (unsigned int)DBLockManager::_GetLockEntryIndex((__int64)this, v30, (unsigned int *)&v43) )
    {
      v43 = *(_QWORD *)(LockEntries::operator[]((char *)this + 56, (unsigned int)v43, v35) + 8);
      ProcessIdFromCallerId = GetProcessIdFromCallerId((const struct CallerId *)&v43, v44);
      if ( ProcessIdFromCallerId < 0 )
        Log_UnistoreHREvent(ProcessIdFromCallerId, 0, v37, 791, v42);
      v33 = v44[0];
    }
    if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x100) != 0 )
      McTemplateU0ddd_EventWriteTransfer(v34, (unsigned int)UnifiedStore_LockNotReleased, v30, 30, v33);
    v45 += 30000;
LABEL_44:
    v10 = a5;
  }
  v45 = 0;
  v26 = DBLockManager::_ClaimLocks(this, a2, a3, v46, v10, &v45);
  IsShuttingDown = v26;
  if ( v26 < 0 )
  {
    v38 = 751;
    v39 = 1;
    v40 = v26;
LABEL_51:
    Log_UnistoreHREvent(v40, v39, v16, v38, v42);
LABEL_52:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    return (unsigned int)IsShuttingDown;
  }
  if ( a6 )
    *a6 = v45;
  if ( TickCount64 )
  {
    v28 = GetTickCount64();
    PerfIncrementCount(8, (unsigned int)(v28 - TickCount64));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return 0;
}

```

## disassembly

```asm
0x180027e7c  mov     [rsp+arg_0], rbx
0x180027e81  mov     [rsp+arg_18], r9
0x180027e86  push    rbp
0x180027e87  push    rsi
0x180027e88  push    rdi
0x180027e89  push    r12
0x180027e8b  push    r13
0x180027e8d  push    r14
0x180027e8f  push    r15
0x180027e91  sub     rsp, 40h
0x180027e95  mov     rbx, r9
0x180027e98  mov     r12d, r8d
0x180027e9b  mov     r13, rdx
0x180027e9e  mov     rbp, rcx
0x180027ea1  test    r8d, r8d
0x180027ea4  jnz     short loc_180027EB8
0x180027ea6  mov     r8d, 2BAh
0x180027eac  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180027eb3  call    Log_AssertionEvent
0x180027eb8  mov     r14, [rsp+78h+arg_20]
0x180027ec0  mov     r9, rbx; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x180027ec3  mov     r8d, r12d; unsigned int
0x180027ec6  mov     [rsp+78h+var_58], r14; enum DB_LOCK_TYPE *
0x180027ecb  mov     rdx, r13; struct CallerId *
0x180027ece  mov     rcx, rbp; this
0x180027ed1  call    ?_ValidateLocks@DBLockManager@@AEAAJAEBUCallerId@@KPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@PEBW4DB_LOCK_TYPE@@@Z; DBLockManager::_ValidateLocks(CallerId const &,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *,DB_LOCK_TYPE const *)
0x180027ed6  mov     ebx, eax
0x180027ed8  test    eax, eax
0x180027eda  js      loc_180028047
0x180027ee0  lea     rbx, [rbp+8]
0x180027ee4  mov     [rsp+78h+arg_10], 0
0x180027eef  mov     rcx, rbx; lpCriticalSection
0x180027ef2  call    cs:__imp_EnterCriticalSection
0x180027ef8  xor     r15d, r15d
0x180027efb  lea     esi, [r15+1]
0x180027eff  call    ?FailIfServiceIsShuttingDown@@YAJXZ; FailIfServiceIsShuttingDown(void)
0x180027f04  mov     edi, eax
0x180027f06  test    eax, eax
0x180027f08  js      loc_180028242
0x180027f0e  mov     ecx, [r13+0]; unsigned int
0x180027f12  call    ?IsAssociatedWithTerminatedProcess@@YAHK@Z; IsAssociatedWithTerminatedProcess(ulong)
0x180027f17  test    eax, eax
0x180027f19  jnz     loc_180028233
0x180027f1f  mov     rcx, rbx; this
0x180027f22  call    ?_IsOwnedByCurrentThread@recursive_mutex@utl@@QEBA_NXZ; utl::recursive_mutex::_IsOwnedByCurrentThread(void)
0x180027f27  test    al, al
0x180027f29  jz      loc_180028030
0x180027f2f  xor     edi, edi
0x180027f31  cmp     edi, r12d
0x180027f34  jnb     short loc_180027FB5
0x180027f36  mov     rcx, [rsp+78h+arg_18]
0x180027f3e  mov     r14d, [rcx+rdi*4]
0x180027f42  mov     rcx, rbx; this
0x180027f45  call    ?_IsOwnedByCurrentThread@recursive_mutex@utl@@QEBA_NXZ; utl::recursive_mutex::_IsOwnedByCurrentThread(void)
0x180027f4a  test    al, al
0x180027f4c  jnz     short loc_180027F60
0x180027f4e  mov     r8d, 295h
0x180027f54  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180027f5b  call    Log_AssertionEvent
0x180027f60  cmp     r14d, 7FFFFFF8h
0x180027f67  jz      short loc_180027FA1
0x180027f69  xor     edx, edx
0x180027f6b  cmp     edx, [rbp+38h]
0x180027f6e  jnb     short loc_180027F95
0x180027f70  mov     eax, edx
0x180027f72  imul    rcx, rax, 38h ; '8'
0x180027f76  mov     rax, [rbp+40h]
0x180027f7a  cmp     r14d, [rcx+rax]
0x180027f7e  jz      short loc_180027F84
0x180027f80  add     edx, esi
0x180027f82  jmp     short loc_180027F6B
0x180027f84  mov     r9d, [rcx+rax+4]
0x180027f89  mov     r8, rax
0x180027f8c  test    r9d, r9d
0x180027f8f  jnz     loc_180028074
0x180027f95  mov     r14, [rsp+78h+arg_20]
0x180027f9d  add     edi, esi
0x180027f9f  jmp     short loc_180027F31
0x180027fa1  mov     r8d, 298h
0x180027fa7  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180027fae  call    Log_AssertionEvent
0x180027fb3  jmp     short loc_180027F69
0x180027fb5  mov     r9, [rsp+78h+arg_18]; enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *
0x180027fbd  lea     rax, [rsp+78h+arg_10]
0x180027fc5  mov     [rsp+78h+var_50], rax; int *
0x180027fca  mov     r8d, r12d; unsigned int
0x180027fcd  mov     rdx, r13; struct CallerId *
0x180027fd0  mov     [rsp+78h+var_58], r14; enum DB_LOCK_TYPE *
0x180027fd5  mov     rcx, rbp; this
0x180027fd8  mov     [rsp+78h+arg_10], 0
0x180027fe3  call    ?_ClaimLocks@DBLockManager@@AEAAJAEBUCallerId@@KPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@PEBW4DB_LOCK_TYPE@@PEAH@Z; DBLockManager::_ClaimLocks(CallerId const &,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *,DB_LOCK_TYPE const *,int *)
0x180027fe8  mov     edi, eax
0x180027fea  test    eax, eax
0x180027fec  js      loc_1800281B4
0x180027ff2  mov     rcx, [rsp+78h+arg_28]
0x180027ffa  test    rcx, rcx
0x180027ffd  jz      short loc_180028008
0x180027fff  mov     eax, [rsp+78h+arg_10]
0x180028006  mov     [rcx], eax
0x180028008  test    r15, r15
0x18002800b  jnz     short loc_18002805D
0x18002800d  mov     rcx, rbx; lpCriticalSection
0x180028010  call    cs:__imp_LeaveCriticalSection
0x180028016  xor     eax, eax
0x180028018  mov     rbx, [rsp+78h+arg_0]
0x180028020  add     rsp, 40h
0x180028024  pop     r15
0x180028026  pop     r14
0x180028028  pop     r13
0x18002802a  pop     r12
0x18002802c  pop     rdi
0x18002802d  pop     rsi
0x18002802e  pop     rbp
0x18002802f  retn
0x180028030  mov     r8d, 2D2h
0x180028036  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18002803d  call    Log_AssertionEvent
0x180028042  jmp     loc_180027F2F
0x180028047  mov     edx, 1
0x18002804c  mov     r9d, 2BCh
0x180028052  mov     ecx, ebx
0x180028054  call    Log_UnistoreHREvent
0x180028059  mov     eax, ebx
0x18002805b  jmp     short loc_180028018
0x18002805d  call    cs:__imp_GetTickCount64
0x180028063  sub     eax, r15d
0x180028066  mov     ecx, 8
0x18002806b  mov     edx, eax
0x18002806d  call    ?PerfIncrementCount@@YAXW4ModelsPerfDataPoint@@K@Z; PerfIncrementCount(ModelsPerfDataPoint,ulong)
0x180028072  jmp     short loc_18002800D
0x180028074  cmp     r9d, esi
0x180028077  jz      loc_18002817A
0x18002807d  cmp     r9d, 2
0x180028081  jz      loc_18002819C
0x180028087  lea     rcx, [rbp+38h]
0x18002808b  call    ??ALockEntries@@QEAAAEAVLockItem@@K@Z; LockEntries::operator[](ulong)
0x180028090  mov     r14d, [rax]
0x180028093  test    r15, r15
0x180028096  jz      loc_180028206
0x18002809c  cmp     [rsp+78h+arg_10], 0DBBA0h
0x1800280a7  ja      loc_180028214
0x1800280ad  lea     rcx, [rbp+30h]; ConditionVariable
0x1800280b1  mov     r8d, 7530h; dwMilliseconds
0x1800280b7  mov     rdx, rbx; CriticalSection
0x1800280ba  call    cs:__imp_SleepConditionVariableCS
0x1800280c0  test    eax, eax
0x1800280c2  jnz     loc_18002816D
0x1800280c8  call    cs:__imp_GetLastError
0x1800280ce  mov     edi, eax
0x1800280d0  cmp     eax, 5B4h
0x1800280d5  jz      short loc_1800280E2
0x1800280d7  cmp     eax, 102h
0x1800280dc  jnz     loc_1800281D3
0x1800280e2  xor     edi, edi
0x1800280e4  mov     dword ptr [rsp+78h+var_48], 0
0x1800280ec  lea     r8, [rsp+78h+var_48]
0x1800280f1  mov     [rsp+78h+var_40], edi
0x1800280f5  mov     edx, r14d
0x1800280f8  mov     rcx, rbp
0x1800280fb  call    ?_GetLockEntryIndex@DBLockManager@@AEAAHW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@PEAK@Z; DBLockManager::_GetLockEntryIndex(__MIDL___MIDL_itf_unistore_0000_0002_0001,ulong *)
0x180028100  test    eax, eax
0x180028102  jz      short loc_180028140
0x180028104  mov     edx, dword ptr [rsp+78h+var_48]
0x180028108  lea     rcx, [rbp+38h]
0x18002810c  call    ??ALockEntries@@QEAAAEAVLockItem@@K@Z; LockEntries::operator[](ulong)
0x180028111  lea     rdx, [rsp+78h+var_40]; unsigned int *
0x180028116  mov     rcx, [rax+8]
0x18002811a  mov     [rsp+78h+var_48], rcx
0x18002811f  lea     rcx, [rsp+78h+var_48]; struct CallerId *
0x180028124  call    ?GetProcessIdFromCallerId@@YAJAEBUCallerId@@PEAK@Z; GetProcessIdFromCallerId(CallerId const &,ulong *)
0x180028129  test    eax, eax
0x18002812b  jns     short loc_18002813C
0x18002812d  xor     edx, edx
0x18002812f  mov     r9d, 317h
0x180028135  mov     ecx, eax
0x180028137  call    Log_UnistoreHREvent
0x18002813c  mov     edi, [rsp+78h+var_40]
0x180028140  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits+1, sil
0x180028147  jz      short loc_180028162
0x180028149  mov     r9d, 1Eh
0x18002814f  mov     dword ptr [rsp+78h+var_58], edi
0x180028153  mov     r8d, r14d
0x180028156  lea     rdx, UnifiedStore_LockNotReleased
0x18002815d  call    McTemplateU0ddd_EventWriteTransfer
0x180028162  add     [rsp+78h+arg_10], 7530h
0x18002816d  mov     r14, [rsp+78h+arg_20]
0x180028175  jmp     loc_180027EFF
0x18002817a  mov     eax, [rcx+rax+8]
0x18002817e  cmp     [r13+0], eax
0x180028182  jnz     loc_180028087
0x180028188  mov     eax, [rcx+r8+0Ch]
0x18002818d  cmp     [r13+4], eax
0x180028191  jnz     loc_18002807D
0x180028197  jmp     loc_180027F95
0x18002819c  mov     r14, [rsp+78h+arg_20]
0x1800281a4  cmp     dword ptr [r14+rdi*4], 0
0x1800281a9  jz      loc_180027F9D
0x1800281af  jmp     loc_180028087
0x1800281b4  mov     r9d, 2EFh
0x1800281ba  mov     edx, esi
0x1800281bc  mov     ecx, eax
0x1800281be  call    Log_UnistoreHREvent
0x1800281c3  mov     rcx, rbx; lpCriticalSection
0x1800281c6  call    cs:__imp_LeaveCriticalSection
0x1800281cc  mov     eax, edi
0x1800281ce  jmp     loc_180028018
0x1800281d3  test    eax, eax
0x1800281d5  jle     short loc_1800281E0
0x1800281d7  movzx   edi, ax
0x1800281da  or      edi, 80070000h
0x1800281e0  mov     esi, 31Fh
0x1800281e5  xor     edx, edx
0x1800281e7  mov     r9d, esi
0x1800281ea  mov     ecx, edi
0x1800281ec  call    Log_UnistoreHREvent
0x1800281f1  test    edi, edi
0x1800281f3  jnz     short loc_1800281C3
0x1800281f5  mov     r8d, esi
0x1800281f8  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800281ff  call    Log_AssertionEvent
0x180028204  jmp     short loc_1800281C3
0x180028206  call    cs:__imp_GetTickCount64
0x18002820c  mov     r15, rax
0x18002820f  jmp     loc_18002809C
0x180028214  mov     r8d, 301h
0x18002821a  lea     rdx, aOnecoreuapBase_52; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180028221  call    Log_AssertionEvent
0x180028226  mov     r9d, 302h
0x18002822c  mov     edi, 800705B4h
0x180028231  jmp     short loc_18002823E
0x180028233  mov     edi, 8000001Ah
0x180028238  mov     r9d, 2CEh
0x18002823e  xor     edx, edx
0x180028240  jmp     short loc_18002824A
0x180028242  mov     r9d, 2C9h
0x180028248  mov     edx, esi
0x18002824a  mov     ecx, edi
0x18002824c  jmp     loc_1800281BE
```
