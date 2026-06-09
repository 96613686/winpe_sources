# VmTask::InitializeTaskRepository(void)

- ea: `0x140229838`
- end: `0x14022a2ad`
- name: `?InitializeTaskRepository@VmTask@@AEAAXXZ`
- size: `2677`
- prototype: `void __fastcall(VmTask *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1406467b4`

## callees

- `0x140022640`
- `0x140034404`
- `0x140043dc8`
- `0x14005c630`
- `0x1400634f4`
- `0x14008f798`
- `0x1400ee214`
- `0x140188e18`
- `0x140229838`
- `0x14022a2b4`
- `0x14022a8c4`
- `0x14022abe0`
- `0x14022ae54`
- `0x14022b4c8`
- `0x14025ecdc`
- `0x1402af2e8`
- `0x1404828e0`
- `0x140646484`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14022a06c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14022a06c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14022a045`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14022a045`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14022a203`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14022a203`

## string_xrefs

- `0x1402298a2`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x14022994a`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229996`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229a19`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229a5a`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229acd`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229b0e`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229b7f`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229bc0`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229c3c`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229c7d`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229cf0`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229d31`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229da4`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229de5`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229e58`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229e99`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229f0a`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229f4b`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x140229fc9`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x14022a00a`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x14022a0c1`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x14022a13a`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x14022a286`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x14022a29b`: `onecore\vm\vmms\taskmgr\vmtask.cpp`
- `0x1402298c2`: `owner_sid`
- `0x14022992c`: `owner_sid`
- `0x140229bef`: `scheduled_start_time`
- `0x140229c1e`: `scheduled_start_time`
- `0x1402299cc`: `task_type`
- `0x1402299fb`: `task_type`
- `0x140229981`: `%hs failed to retrieve owner_sid from repository! HRESULT = 0x%08lX\n`
- `0x14022997a`: `VmTask::InitializeTaskRepository`
- `0x140229a3e`: `VmTask::InitializeTaskRepository`
- `0x140229af2`: `VmTask::InitializeTaskRepository`
- `0x140229ba4`: `VmTask::InitializeTaskRepository`
- `0x140229c61`: `VmTask::InitializeTaskRepository`
- `0x140229d15`: `VmTask::InitializeTaskRepository`
- `0x140229dc9`: `VmTask::InitializeTaskRepository`
- `0x140229e7d`: `VmTask::InitializeTaskRepository`
- `0x140229f2f`: `VmTask::InitializeTaskRepository`
- `0x140229fee`: `VmTask::InitializeTaskRepository`
- `0x14022a11e`: `VmTask::InitializeTaskRepository`
- `0x140229a45`: `%hs failed to retrieve task_type from repository! HRESULT = 0x%08lX\n`
- `0x140229c68`: `%hs failed to retrieve scheduled_start_time from repository! HRESULT = 0x%08lX\n`
- `0x14022a125`: `%hs failed to retrieve child task count! HRESULT = 0x%08lX\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall VmTask::InitializeTaskRepository(struct IVmTaskRepository **this)
{
  int v2; // eax
  unsigned int v3; // esi
  __m128i si128; // xmm6
  HLOCAL *v5; // r8
  int v6; // eax
  int v7; // eax
  unsigned int v8; // esi
  int v9; // eax
  int v10; // eax
  unsigned int v11; // esi
  int v12; // eax
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  int v16; // eax
  unsigned int v17; // esi
  int v18; // eax
  int v19; // eax
  unsigned int v20; // esi
  int v21; // eax
  int v22; // eax
  unsigned int v23; // esi
  int v24; // eax
  int v25; // eax
  unsigned int v26; // esi
  int v27; // eax
  int v28; // eax
  unsigned int v29; // esi
  int v30; // eax
  int v31; // eax
  unsigned int v32; // esi
  int v33; // eax
  int v34; // eax
  struct VmTask *v35; // rbx
  int v36; // eax
  int v37; // eax
  unsigned int v38; // esi
  struct VmTask *v39; // rbx
  unsigned int i; // esi
  __int128 *p_Src; // rdx
  int v42; // eax
  int v43; // eax
  VmTaskManager *v44; // [rsp+28h] [rbp-49h] BYREF
  struct VmTask *v45; // [rsp+30h] [rbp-41h] BYREF
  char *v46[2]; // [rsp+38h] [rbp-39h] BYREF
  LPCWSTR StringSid; // [rsp+48h] [rbp-29h] BYREF
  __int64 v48; // [rsp+50h] [rbp-21h] BYREF
  __int64 v49; // [rsp+58h] [rbp-19h] BYREF
  HLOCAL hMem[2]; // [rsp+60h] [rbp-11h] BYREF
  __m128i v51; // [rsp+70h] [rbp-1h]
  __int128 Src; // [rsp+80h] [rbp+Fh] BYREF
  __m128i v53; // [rsp+90h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  StringSid = 0;
  v48 = 0;
  *(_OWORD *)v46 = 0;
  VmTaskRepositoryAutoLock::VmTaskRepositoryAutoLock((VmTaskRepositoryAutoLock *)v46, this[36], 1);
  if ( SLODWORD(v46[1]) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE8C,
      (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
      (const char *)LODWORD(v46[1]),
      (int)v44);
  v2 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, LPCWSTR *))(*(_QWORD *)this[36]
                                                                                                  + 168LL))(
         this[36],
         L"owner_sid",
         &StringSid);
  v3 = v2;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v2 >= 0 )
  {
    Vml::VmSid::Assign((Vml::VmSid *)(this + 23), StringSid);
  }
  else
  {
    if ( v2 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve owner_sid from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v3);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEA1,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v3,
        (int)v44);
    }
    *(_OWORD *)hMem = 0;
    v51 = si128;
    LOWORD(hMem[0]) = 0;
    Vml::VmSid::ToString(this + 23, hMem);
    v5 = hMem;
    if ( v51.m128i_i64[1] > 7uLL )
      v5 = (HLOCAL *)hMem[0];
    v6 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, HLOCAL *))(*(_QWORD *)this[36] + 176LL))(
           this[36],
           L"owner_sid",
           v5);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE9A,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v6,
        (int)v44);
    std::wstring::_Tidy_deallocate(hMem);
  }
  v7 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, char *))(*(_QWORD *)this[36]
                                                                                               + 136LL))(
         this[36],
         L"task_type",
         (char *)this + 128);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( v7 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve task_type from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v8);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEBA,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v8,
        (int)v44);
    }
    v9 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, _QWORD))(*(_QWORD *)this[36]
                                                                                                 + 144LL))(
           this[36],
           L"task_type",
           *((int *)this + 32));
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEB3,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v9,
        (int)v44);
  }
  v10 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, char *))(*(_QWORD *)this[36]
                                                                                                + 136LL))(
          this[36],
          L"max_progress",
          (char *)this + 360);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( v10 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve max_progress from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v11);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xED0,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v11,
        (int)v44);
    }
    v12 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, struct IVmTaskRepository *))(*(_QWORD *)this[36] + 144LL))(
            this[36],
            L"max_progress",
            this[45]);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEC9,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v12,
        (int)v44);
  }
  v13 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this[36] + 136LL))(
          this[36],
          L"flags",
          &v48);
  v14 = v13;
  if ( v13 >= 0 )
  {
    *((_DWORD *)this + 42) = v48;
  }
  else
  {
    if ( v13 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve flags from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v14);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEE5,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v14,
        (int)v44);
    }
    v15 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, _QWORD))(*(_QWORD *)this[36]
                                                                                                  + 144LL))(
            this[36],
            L"flags",
            *((unsigned int *)this + 42));
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEDE,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v15,
        (int)v44);
  }
  v16 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, char *))(*(_QWORD *)this[36]
                                                                                                + 136LL))(
          this[36],
          L"scheduled_start_time",
          (char *)this + 280);
  v17 = v16;
  if ( v16 < 0 )
  {
    if ( v16 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve scheduled_start_time from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v17);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF01,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v17,
        (int)v44);
    }
    v18 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, struct IVmTaskRepository *))(*(_QWORD *)this[36] + 144LL))(
            this[36],
            L"scheduled_start_time",
            this[35]);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEFA,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v18,
        (int)v44);
  }
  v19 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, char *))(*(_QWORD *)this[36]
                                                                                                + 136LL))(
          this[36],
          L"submit_time",
          (char *)this + 264);
  v20 = v19;
  if ( v19 < 0 )
  {
    if ( v19 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve submit_time from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v20);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF17,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v20,
        (int)v44);
    }
    v21 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, struct IVmTaskRepository *))(*(_QWORD *)this[36] + 144LL))(
            this[36],
            L"submit_time",
            this[33]);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF10,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v21,
        (int)v44);
  }
  v22 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, char *))(*(_QWORD *)this[36]
                                                                                                + 136LL))(
          this[36],
          L"last_state_change",
          (char *)this + 384);
  v23 = v22;
  if ( v22 < 0 )
  {
    if ( v22 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve last_state_change from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v23);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF2D,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v23,
        (int)v44);
    }
    v24 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, struct IVmTaskRepository *))(*(_QWORD *)this[36] + 144LL))(
            this[36],
            L"last_state_change",
            this[48]);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF26,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v24,
        (int)v44);
  }
  v25 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, char *))(*(_QWORD *)this[36]
                                                                                                + 136LL))(
          this[36],
          L"start_time",
          (char *)this + 272);
  v26 = v25;
  if ( v25 < 0 )
  {
    if ( v25 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve start_time from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v26);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF43,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v26,
        (int)v44);
    }
    v27 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, struct IVmTaskRepository *))(*(_QWORD *)this[36] + 144LL))(
            this[36],
            L"start_time",
            this[34]);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF3C,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v27,
        (int)v44);
  }
  v28 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this[36] + 136LL))(
          this[36],
          L"result_code",
          &v48);
  v29 = v28;
  if ( v28 >= 0 )
  {
    *((_DWORD *)this + 106) = v48;
  }
  else
  {
    if ( v28 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve result_code from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v29);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF58,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v29,
        (int)v44);
    }
    v30 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, _QWORD))(*(_QWORD *)this[36]
                                                                                                  + 144LL))(
            this[36],
            L"result_code",
            *((int *)this + 106));
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF51,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v30,
        (int)v44);
  }
  v31 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this[36] + 136LL))(
          this[36],
          L"state",
          &v48);
  v32 = v31;
  if ( v31 >= 0 )
  {
    v34 = v48;
    *((_DWORD *)this + 86) = v48;
    if ( v34 == 1 && !this[54] )
    {
      v44 = 0;
      v35 = 0;
      EnterCriticalSection(&Vml::VmSingletonObject<VmTaskManager,VmTaskManager>::gm_SingletonLock);
      v45 = 0;
      if ( (unsigned __int8)Vml::VmSingletonObject<VmTaskManager,VmTaskManager>::TryOpenSharedInternal(&v45) )
        v35 = v45;
      LeaveCriticalSection(&Vml::VmSingletonObject<VmTaskManager,VmTaskManager>::gm_SingletonLock);
      Vml::VmComPtr<VmTaskManager>::Attach<VmTaskManager>(&v44, v35);
      if ( v44 )
        VmTaskManager::UpdateTaskExpiration(v44, (struct VmTask *)this, 0xFFFFFFFF);
      Vml::VmComPtr<WmiCimElementCapabilitiesResolver>::~VmComPtr<WmiCimElementCapabilitiesResolver>(&v44);
    }
  }
  else
  {
    if ( v31 != -2147024894 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
        VmlDebugTrace(
          0x4000,
          L"%hs failed to retrieve state from repository! HRESULT = 0x%08lX\n",
          "VmTask::InitializeTaskRepository",
          v32);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF73,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)v32,
        (int)v44);
    }
    v33 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, _QWORD))(*(_QWORD *)this[36]
                                                                                                  + 144LL))(
            this[36],
            L"state",
            *((int *)this + 86));
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF6C,
        (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
        (const char *)(unsigned int)v33,
        (int)v44);
  }
  v36 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *))(*(_QWORD *)this[36] + 88LL))(this[36]);
  if ( v36 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF8A,
      (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
      (const char *)(unsigned int)v36,
      (int)v44);
  v49 = 0;
  v37 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this[36] + 136LL))(
          this[36],
          L"children/count",
          &v49);
  v38 = v37;
  if ( v37 >= 0 )
  {
    *((_DWORD *)this + 120) = 0;
    v39 = 0;
    v44 = 0;
    for ( i = 0; i < v49; v39 = v44 )
    {
      Src = 0;
      v53 = si128;
      LOWORD(Src) = 0;
      hMem[1] = 0;
      hMem[0] = 0;
      Vml::FormatString(&Src, (wchar_t *)L"children/child[%u]");
      p_Src = &Src;
      if ( v53.m128i_i64[1] > 7uLL )
        p_Src = (__int128 *)Src;
      v42 = (*(__int64 (__fastcall **)(struct IVmTaskRepository *, __int128 *, HLOCAL *))(*(_QWORD *)this[36] + 168LL))(
              this[36],
              p_Src,
              hMem);
      if ( v42 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFAF,
          (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
          (const char *)(unsigned int)v42,
          (int)v44);
      v44 = 0;
      v45 = v39;
      Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v45);
      v43 = VmTask::LoadChildTask((VmTask *)this, (unsigned __int16 *)hMem[0], &v44);
      if ( v43 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFB2,
          (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
          (const char *)(unsigned int)v43,
          (int)v44);
      if ( hMem[0] )
        LocalFree(hMem[0]);
      std::wstring::_Tidy_deallocate(&Src);
      ++i;
    }
    *((_DWORD *)this + 120) = 1;
    if ( v39 )
      VmTask::NotifySubTaskChange((VmTask *)this, v39);
    Vml::VmComPtr<VmmsClusterVmSwitchConnection>::~VmComPtr<VmmsClusterVmSwitchConnection>(&v44);
  }
  else if ( v37 != -2147024894 )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
      VmlDebugTrace(
        0x4000,
        L"%hs failed to retrieve child task count! HRESULT = 0x%08lX\n",
        "VmTask::InitializeTaskRepository",
        v38);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF9E,
      (unsigned int)"onecore\\vm\\vmms\\taskmgr\\vmtask.cpp",
      (const char *)v38,
      (int)v44);
  }
  VmTaskRepositoryAutoLock::~VmTaskRepositoryAutoLock((VmTaskRepositoryAutoLock *)v46);
}

```

## disassembly

```asm
0x140229838  mov     rax, rsp
0x14022983b  mov     [rax+10h], rbx
0x14022983f  mov     [rax+18h], rsi
0x140229843  push    rbp
0x140229844  push    rdi
0x140229845  push    r15
0x140229847  lea     rbp, [rax-5Fh]
0x14022984b  sub     rsp, 0B0h
0x140229852  movaps  xmmword ptr [rax-28h], xmm6
0x140229856  mov     rax, cs:__security_cookie
0x14022985d  xor     rax, rsp
0x140229860  mov     [rbp+57h+var_28], rax
0x140229864  mov     rdi, rcx
0x140229867  mov     [rbp+57h+StringSid], 0
0x14022986f  mov     [rbp+57h+var_78], 0
0x140229877  xorps   xmm0, xmm0
0x14022987a  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14022987e  mov     r8d, 1; int
0x140229884  mov     rdx, [rcx+120h]; struct IVmTaskRepository *
0x14022988b  lea     rcx, [rbp+57h+var_90]; this
0x14022988f  call    ??0VmTaskRepositoryAutoLock@@QEAA@PEAVIVmTaskRepository@@H@Z; VmTaskRepositoryAutoLock::VmTaskRepositoryAutoLock(IVmTaskRepository *,int)
0x140229894  nop
0x140229895  mov     r9d, dword ptr [rbp+57h+var_90+8]; char *
0x140229899  mov     rcx, [rbp+5Fh]; this
0x14022989d  test    r9d, r9d
0x1402298a0  jns     short loc_1402298B4
0x1402298a2  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x1402298a9  mov     edx, 0E8Ch; void *
0x1402298ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402298b4  mov     rcx, [rdi+120h]
0x1402298bb  mov     rax, [rcx]
0x1402298be  lea     r8, [rbp+57h+StringSid]
0x1402298c2  lea     rdx, ?TASK_CONFIGURATION_OWNER_SID_XPATH@@3QBGB; "owner_sid"
0x1402298c9  mov     rax, [rax+0A8h]
0x1402298d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402298d5  mov     esi, eax
0x1402298d7  mov     r15d, 80070002h
0x1402298dd  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1402298e5  test    eax, eax
0x1402298e7  jns     loc_1402299A8
0x1402298ed  cmp     eax, r15d
0x1402298f0  jnz     short loc_140229967
0x1402298f2  xorps   xmm0, xmm0
0x1402298f5  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x1402298f9  movdqu  [rbp+57h+var_58], xmm6
0x1402298fe  xor     eax, eax
0x140229900  mov     word ptr [rbp+57h+hMem], ax
0x140229904  lea     rcx, [rdi+0B8h]
0x14022990b  lea     rdx, [rbp+57h+hMem]
0x14022990f  call    ?ToString@VmSid@Vml@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Vml::VmSid::ToString(std::wstring &)
0x140229914  mov     rcx, [rdi+120h]
0x14022991b  mov     rax, [rcx]
0x14022991e  lea     r8, [rbp+57h+hMem]
0x140229922  cmp     qword ptr [rbp+57h+var_58+8], 7
0x140229927  cmova   r8, [rbp+57h+hMem]
0x14022992c  lea     rdx, ?TASK_CONFIGURATION_OWNER_SID_XPATH@@3QBGB; "owner_sid"
0x140229933  mov     rax, [rax+0B0h]
0x14022993a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14022993f  mov     rcx, [rbp+5Fh]; this
0x140229943  test    eax, eax
0x140229945  jns     short loc_14022995C
0x140229947  mov     r9d, eax; char *
0x14022994a  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229951  mov     edx, 0E9Ah; void *
0x140229956  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14022995c  lea     rcx, [rbp+57h+hMem]
0x140229960  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140229965  jmp     short loc_1402299B8
0x140229967  mov     ebx, 4000h
0x14022996c  mov     ecx, ebx
0x14022996e  call    VmlIsDebugTraceEnabled
0x140229973  test    eax, eax
0x140229975  jz      short loc_14022998F
0x140229977  mov     r9d, esi
0x14022997a  lea     r8, aVmtaskInitiali; "VmTask::InitializeTaskRepository"
0x140229981  lea     rdx, aHsFailedToRetr_0; "%hs failed to retrieve owner_sid from r"...
0x140229988  mov     ecx, ebx
0x14022998a  call    VmlDebugTrace
0x14022998f  mov     rcx, [rbp+5Fh]; this
0x140229993  mov     r9d, esi; char *
0x140229996  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x14022999d  mov     edx, 0EA1h; void *
0x1402299a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402299a8  lea     rcx, [rdi+0B8h]; this
0x1402299af  mov     rdx, [rbp+57h+StringSid]; StringSid
0x1402299b3  call    ?Assign@VmSid@Vml@@QEAAXPEBG@Z; Vml::VmSid::Assign(ushort const *)
0x1402299b8  mov     rcx, [rdi+120h]
0x1402299bf  lea     rbx, [rdi+80h]
0x1402299c6  mov     rax, [rcx]
0x1402299c9  mov     r8, rbx
0x1402299cc  lea     rdx, ?TASK_CONFIGURATION_TASK_TYPE_XPATH@@3QBGB; "task_type"
0x1402299d3  mov     rax, [rax+88h]
0x1402299da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402299df  mov     esi, eax
0x1402299e1  test    eax, eax
0x1402299e3  jns     loc_140229A6C
0x1402299e9  cmp     eax, r15d
0x1402299ec  jnz     short loc_140229A2B
0x1402299ee  mov     rcx, [rdi+120h]
0x1402299f5  mov     rax, [rcx]
0x1402299f8  movsxd  r8, dword ptr [rbx]
0x1402299fb  lea     rdx, ?TASK_CONFIGURATION_TASK_TYPE_XPATH@@3QBGB; "task_type"
0x140229a02  mov     rax, [rax+90h]
0x140229a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229a0e  mov     rcx, [rbp+5Fh]; this
0x140229a12  test    eax, eax
0x140229a14  jns     short loc_140229A6C
0x140229a16  mov     r9d, eax; char *
0x140229a19  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229a20  mov     edx, 0EB3h; void *
0x140229a25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229a2b  mov     ebx, 4000h
0x140229a30  mov     ecx, ebx
0x140229a32  call    VmlIsDebugTraceEnabled
0x140229a37  test    eax, eax
0x140229a39  jz      short loc_140229A53
0x140229a3b  mov     r9d, esi
0x140229a3e  lea     r8, aVmtaskInitiali; "VmTask::InitializeTaskRepository"
0x140229a45  lea     rdx, aHsFailedToRetr_9; "%hs failed to retrieve task_type from r"...
0x140229a4c  mov     ecx, ebx
0x140229a4e  call    VmlDebugTrace
0x140229a53  mov     rcx, [rbp+5Fh]; this
0x140229a57  mov     r9d, esi; char *
0x140229a5a  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229a61  mov     edx, 0EBAh; void *
0x140229a66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229a6c  mov     rcx, [rdi+120h]
0x140229a73  lea     rbx, [rdi+168h]
0x140229a7a  mov     rax, [rcx]
0x140229a7d  mov     r8, rbx
0x140229a80  lea     rdx, ?TASK_CONFIGURATION_MAX_PROGRESS_XPATH@@3QBGB; "max_progress"
0x140229a87  mov     rax, [rax+88h]
0x140229a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229a93  mov     esi, eax
0x140229a95  test    eax, eax
0x140229a97  jns     loc_140229B20
0x140229a9d  cmp     eax, r15d
0x140229aa0  jnz     short loc_140229ADF
0x140229aa2  mov     rcx, [rdi+120h]
0x140229aa9  mov     rax, [rcx]
0x140229aac  mov     r8, [rbx]
0x140229aaf  lea     rdx, ?TASK_CONFIGURATION_MAX_PROGRESS_XPATH@@3QBGB; "max_progress"
0x140229ab6  mov     rax, [rax+90h]
0x140229abd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229ac2  mov     rcx, [rbp+5Fh]; this
0x140229ac6  test    eax, eax
0x140229ac8  jns     short loc_140229B20
0x140229aca  mov     r9d, eax; char *
0x140229acd  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229ad4  mov     edx, 0EC9h; void *
0x140229ad9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229adf  mov     ebx, 4000h
0x140229ae4  mov     ecx, ebx
0x140229ae6  call    VmlIsDebugTraceEnabled
0x140229aeb  test    eax, eax
0x140229aed  jz      short loc_140229B07
0x140229aef  mov     r9d, esi
0x140229af2  lea     r8, aVmtaskInitiali; "VmTask::InitializeTaskRepository"
0x140229af9  lea     rdx, aHsFailedToRetr_7; "%hs failed to retrieve max_progress fro"...
0x140229b00  mov     ecx, ebx
0x140229b02  call    VmlDebugTrace
0x140229b07  mov     rcx, [rbp+5Fh]; this
0x140229b0b  mov     r9d, esi; char *
0x140229b0e  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229b15  mov     edx, 0ED0h; void *
0x140229b1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229b20  mov     rcx, [rdi+120h]
0x140229b27  mov     rax, [rcx]
0x140229b2a  lea     r8, [rbp+57h+var_78]
0x140229b2e  lea     rdx, ?TASK_CONFIGURATION_FLAGS_XPATH@@3QBGB; "flags"
0x140229b35  mov     rax, [rax+88h]
0x140229b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229b41  mov     esi, eax
0x140229b43  test    eax, eax
0x140229b45  jns     loc_140229BD2
0x140229b4b  cmp     eax, r15d
0x140229b4e  jnz     short loc_140229B91
0x140229b50  mov     rcx, [rdi+120h]
0x140229b57  mov     rax, [rcx]
0x140229b5a  mov     r8d, [rdi+0A8h]
0x140229b61  lea     rdx, ?TASK_CONFIGURATION_FLAGS_XPATH@@3QBGB; "flags"
0x140229b68  mov     rax, [rax+90h]
0x140229b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229b74  mov     rcx, [rbp+5Fh]; this
0x140229b78  test    eax, eax
0x140229b7a  jns     short loc_140229BDB
0x140229b7c  mov     r9d, eax; char *
0x140229b7f  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229b86  mov     edx, 0EDEh; void *
0x140229b8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229b91  mov     ebx, 4000h
0x140229b96  mov     ecx, ebx
0x140229b98  call    VmlIsDebugTraceEnabled
0x140229b9d  test    eax, eax
0x140229b9f  jz      short loc_140229BB9
0x140229ba1  mov     r9d, esi
0x140229ba4  lea     r8, aVmtaskInitiali; "VmTask::InitializeTaskRepository"
0x140229bab  lea     rdx, aHsFailedToRetr; "%hs failed to retrieve flags from repos"...
0x140229bb2  mov     ecx, ebx
0x140229bb4  call    VmlDebugTrace
0x140229bb9  mov     rcx, [rbp+5Fh]; this
0x140229bbd  mov     r9d, esi; char *
0x140229bc0  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229bc7  mov     edx, 0EE5h; void *
0x140229bcc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229bd2  mov     eax, dword ptr [rbp+57h+var_78]
0x140229bd5  mov     [rdi+0A8h], eax
0x140229bdb  mov     rcx, [rdi+120h]
0x140229be2  lea     rbx, [rdi+118h]
0x140229be9  mov     rax, [rcx]
0x140229bec  mov     r8, rbx
0x140229bef  lea     rdx, ?TASK_CONFIGURATION_SCHEDULED_START_TIME_XPATH@@3QBGB; "scheduled_start_time"
0x140229bf6  mov     rax, [rax+88h]
0x140229bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229c02  mov     esi, eax
0x140229c04  test    eax, eax
0x140229c06  jns     loc_140229C8F
0x140229c0c  cmp     eax, r15d
0x140229c0f  jnz     short loc_140229C4E
0x140229c11  mov     rcx, [rdi+120h]
0x140229c18  mov     rax, [rcx]
0x140229c1b  mov     r8, [rbx]
0x140229c1e  lea     rdx, ?TASK_CONFIGURATION_SCHEDULED_START_TIME_XPATH@@3QBGB; "scheduled_start_time"
0x140229c25  mov     rax, [rax+90h]
0x140229c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229c31  mov     rcx, [rbp+5Fh]; this
0x140229c35  test    eax, eax
0x140229c37  jns     short loc_140229C8F
0x140229c39  mov     r9d, eax; char *
0x140229c3c  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229c43  mov     edx, 0EFAh; void *
0x140229c48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229c4e  mov     ebx, 4000h
0x140229c53  mov     ecx, ebx
0x140229c55  call    VmlIsDebugTraceEnabled
0x140229c5a  test    eax, eax
0x140229c5c  jz      short loc_140229C76
0x140229c5e  mov     r9d, esi
0x140229c61  lea     r8, aVmtaskInitiali; "VmTask::InitializeTaskRepository"
0x140229c68  lea     rdx, aHsFailedToRetr_10; "%hs failed to retrieve scheduled_start_"...
0x140229c6f  mov     ecx, ebx
0x140229c71  call    VmlDebugTrace
0x140229c76  mov     rcx, [rbp+5Fh]; this
0x140229c7a  mov     r9d, esi; char *
0x140229c7d  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229c84  mov     edx, 0F01h; void *
0x140229c89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229c8f  mov     rcx, [rdi+120h]
0x140229c96  lea     rbx, [rdi+108h]
0x140229c9d  mov     rax, [rcx]
0x140229ca0  mov     r8, rbx
0x140229ca3  lea     rdx, ?TASK_CONFIGURATION_SUBMIT_TIME_XPATH@@3QBGB; "submit_time"
0x140229caa  mov     rax, [rax+88h]
0x140229cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229cb6  mov     esi, eax
0x140229cb8  test    eax, eax
0x140229cba  jns     loc_140229D43
0x140229cc0  cmp     eax, r15d
0x140229cc3  jnz     short loc_140229D02
0x140229cc5  mov     rcx, [rdi+120h]
0x140229ccc  mov     rax, [rcx]
0x140229ccf  mov     r8, [rbx]
0x140229cd2  lea     rdx, ?TASK_CONFIGURATION_SUBMIT_TIME_XPATH@@3QBGB; "submit_time"
0x140229cd9  mov     rax, [rax+90h]
0x140229ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229ce5  mov     rcx, [rbp+5Fh]; this
0x140229ce9  test    eax, eax
0x140229ceb  jns     short loc_140229D43
0x140229ced  mov     r9d, eax; char *
0x140229cf0  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229cf7  mov     edx, 0F10h; void *
0x140229cfc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229d02  mov     ebx, 4000h
0x140229d07  mov     ecx, ebx
0x140229d09  call    VmlIsDebugTraceEnabled
0x140229d0e  test    eax, eax
0x140229d10  jz      short loc_140229D2A
0x140229d12  mov     r9d, esi
0x140229d15  lea     r8, aVmtaskInitiali; "VmTask::InitializeTaskRepository"
0x140229d1c  lea     rdx, aHsFailedToRetr_6; "%hs failed to retrieve submit_time from"...
0x140229d23  mov     ecx, ebx
0x140229d25  call    VmlDebugTrace
0x140229d2a  mov     rcx, [rbp+5Fh]; this
0x140229d2e  mov     r9d, esi; char *
0x140229d31  lea     r8, aOnecoreVmVmmsT_3; "onecore\\vm\\vmms\\taskmgr\\vmtask.cpp"
0x140229d38  mov     edx, 0F17h; void *
0x140229d3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140229d43  mov     rcx, [rdi+120h]
0x140229d4a  lea     rbx, [rdi+180h]
0x140229d51  mov     rax, [rcx]
0x140229d54  mov     r8, rbx
0x140229d57  lea     rdx, ?TASK_CONFIGURATION_LAST_STATE_CHANGE_TIME_XPATH@@3QBGB; "last_state_change"
0x140229d5e  mov     rax, [rax+88h]
0x140229d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140229d6a  mov     esi, eax
0x140229d6c  test    eax, eax
0x140229d6e  jns     loc_140229DF7
0x140229d74  cmp     eax, r15d
0x140229d77  jnz     short loc_140229DB6
0x140229d79  mov     rcx, [rdi+120h]
  ... truncated ...
```
