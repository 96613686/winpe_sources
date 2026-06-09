# WorkThreadManager::s_ClearOrGetNextTask(WorkThreadManager::CThread *)

- ea: `0x180019918`
- end: `0x180019bcd`
- name: `?s_ClearOrGetNextTask@WorkThreadManager@@CAXPEAVCThread@1@@Z`
- size: `693`
- prototype: `void __fastcall(struct WorkThreadManager::CThread *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x180019474`

## callees

- `0x18000d6bc`
- `0x18000f7d4`
- `0x18000f808`
- `0x18000f834`
- `0x180019918`
- `0x180035cd4`
- `0x180036350`
- `0x180037590`
- `0x1800375b0`
- `0x180037784`
- `0x1800377e0`
- `0x180039180`
- `0x18003b10c`
- `0x18006d924`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019981`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019abf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019981`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019abf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180019aa7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180019aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180019a9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800199d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019b21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800199d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019b21`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall WorkThreadManager::s_ClearOrGetNextTask(struct WorkThreadManager::CThread *a1)
{
  WorkThreadManager::TaskData *v2; // rdi
  __int64 v3; // rax
  char v4; // bl
  DWORD TickCount; // eax
  __int64 v6; // rax
  unsigned int v7; // edx
  WorkThreadManager::TaskData *v8; // rcx
  __int64 v9; // rcx
  const struct wil::wob_ticket *v10; // rdx
  unsigned int v11; // edx
  HANDLE CurrentThread; // rax
  WorkThreadManager::TaskData *v13; // r14
  __int64 v14; // rax
  unsigned int v15; // edx
  WorkThreadManager::TaskData *v16; // rcx
  WorkThreadManager::TaskData *v17; // rbx
  DWORD v18; // eax
  unsigned int v19; // edx
  RTL_SRWLOCK *v20; // [rsp+20h] [rbp-89h] BYREF
  _DWORD v21[2]; // [rsp+28h] [rbp-81h] BYREF
  char v22; // [rsp+30h] [rbp-79h]
  __int64 v23; // [rsp+38h] [rbp-71h] BYREF
  int v24; // [rsp+40h] [rbp-69h]
  __int64 v25; // [rsp+48h] [rbp-61h]
  char v26; // [rsp+50h] [rbp-59h]
  __int16 v27; // [rsp+51h] [rbp-58h]
  char v28; // [rsp+53h] [rbp-56h]
  __int64 v29; // [rsp+54h] [rbp-55h]
  __int128 v30; // [rsp+60h] [rbp-49h]
  _QWORD v31[2]; // [rsp+70h] [rbp-39h] BYREF
  __int64 v32; // [rsp+80h] [rbp-29h] BYREF
  int v33; // [rsp+88h] [rbp-21h]
  __int64 v34; // [rsp+90h] [rbp-19h]
  char v35; // [rsp+98h] [rbp-11h] BYREF
  __int16 v36; // [rsp+99h] [rbp-10h]
  char v37; // [rsp+9Bh] [rbp-Eh]
  __int64 v38; // [rsp+9Ch] [rbp-Dh]
  __int64 v39; // [rsp+A8h] [rbp-1h]
  __int64 v40; // [rsp+B0h] [rbp+7h]
  _QWORD v41[9]; // [rsp+B8h] [rbp+Fh] BYREF
  WorkThreadManager::TaskData *v42; // [rsp+110h] [rbp+67h] BYREF
  WorkThreadManager::TaskData *v43; // [rsp+118h] [rbp+6Fh] BYREF
  WorkThreadManager::TaskData *v44; // [rsp+120h] [rbp+77h] BYREF
  RTL_SRWLOCK *v45; // [rsp+128h] [rbp+7Fh] BYREF

  v32 = 1;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41[1] = v41;
  v41[0] = v41;
  AcquireSRWLockExclusive(&WorkThreadManager::s_rwLock);
  v20 = &WorkThreadManager::s_rwLock;
  WorkThreadManager::s_anyThreadMadeProgress = 1;
  WorkThreadManager::TaskList::PopFront((char *)a1 + 24, &v42);
  v2 = v42;
  if ( v42 )
  {
    v4 = 0;
    TickCount = GetTickCount();
    v6 = WorkThreadManager::CThread::SetThreadTask(a1, &v23, v2, TickCount);
    WorkThreadManager::TaskData::operator=(&v32, v6);
    WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)&v23);
    v8 = v2;
    v2 = 0;
    v42 = 0;
    if ( v8 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v8, v7);
  }
  else
  {
    v3 = WorkThreadManager::CThread::ClearThreadTask(a1, &v23);
    WorkThreadManager::TaskData::operator=(&v32, v3);
    WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)&v23);
    *((_BYTE *)a1 + 41) = 1;
    v4 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
    &v20,
    0);
  WorkThreadManager::CThread::AdjustThreadPriority(v9, (__int64)v21, SWORD2(v32));
  wil::set_wob_ticket((wil *)&v35, v10);
  v23 = 1;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31[1] = v31;
  v31[0] = v31;
  WorkThreadManager::TaskData::operator=(&v32, &v23);
  WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)&v23);
  if ( v22 && v21[0] )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, v21[1]);
  }
  if ( v4 )
  {
    v13 = 0;
    v43 = 0;
    AcquireSRWLockExclusive(&WorkThreadManager::s_rwLock);
    v45 = &WorkThreadManager::s_rwLock;
    *((_BYTE *)a1 + 41) = 0;
    v14 = WorkThreadManager::TaskList::PopFront(&WorkThreadManager::s_taskFloodingList, &v44);
    wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
      &v42,
      v14);
    v16 = v44;
    v44 = 0;
    if ( v16 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v16, v15);
    v17 = v42;
    if ( v42
      && *((_DWORD *)v42 + 2) == *((_DWORD *)a1 + 38)
      && (unsigned __int8)WorkThreadManager::CThread::Eligible(a1, *(unsigned int *)v42, *((unsigned int *)v42 + 1)) )
    {
      v18 = GetTickCount();
      WorkThreadManager::CThread::SetThreadTask(a1, &v23, v17, v18);
      WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)&v23);
      v2 = 0;
      v42 = 0;
      if ( v17 )
        WorkThreadManager::TaskData::`scalar deleting destructor'(v17, v19);
    }
    else
    {
      wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
        &v43,
        &v42);
      v2 = v42;
      v13 = v43;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v45,
      0);
    if ( v13 )
    {
      v43 = 0;
      v44 = v13;
      WorkThreadManager::s_AttachAndRecoverTask(&v44);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v45);
  }
  if ( v2 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v2, v11);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v20);
  WorkThreadManager::TaskData::~TaskData((WorkThreadManager::TaskData *)&v32);
}

```

## disassembly

```asm
0x180019918  push    rbp
0x18001991a  push    rbx
0x18001991b  push    rsi
0x18001991c  push    rdi
0x18001991d  push    r12
0x18001991f  push    r14
0x180019921  push    r15
0x180019923  lea     rbp, [rsp-27h]
0x180019928  sub     rsp, 0D0h
0x18001992f  mov     rsi, rcx
0x180019932  mov     r14d, 1
0x180019938  mov     [rbp+57h+var_80], r14
0x18001993c  xor     r15d, r15d
0x18001993f  mov     [rbp+57h+var_78], r15d
0x180019943  mov     [rbp+57h+var_70], r15
0x180019947  mov     [rbp+57h+var_68], r15b
0x18001994b  xor     eax, eax
0x18001994d  mov     [rbp+57h+var_67], ax
0x180019951  mov     [rbp+57h+var_65], al
0x180019954  mov     [rbp+57h+var_64], rax
0x180019958  mov     [rbp+57h+var_58], r15
0x18001995c  mov     [rbp+57h+var_50], r15
0x180019960  xorps   xmm0, xmm0
0x180019963  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180019967  lea     rax, [rbp+57h+var_48]
0x18001996b  mov     [rbp+57h+var_48+8], rax
0x18001996f  lea     rax, [rbp+57h+var_48]
0x180019973  mov     [rbp+57h+var_48], rax
0x180019977  lea     r12, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; wil::srwlock WorkThreadManager::s_rwLock
0x18001997e  mov     rcx, r12; SRWLock
0x180019981  call    cs:__imp_AcquireSRWLockExclusive
0x180019987  mov     [rsp+100h+var_E0], r12
0x18001998c  mov     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, r14b; bool WorkThreadManager::s_anyThreadMadeProgress
0x180019993  lea     rcx, [rsi+18h]
0x180019997  lea     rdx, [rbp+57h+arg_0]
0x18001999b  call    ?PopFront@TaskList@WorkThreadManager@@QEAA?AV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@XZ; WorkThreadManager::TaskList::PopFront(void)
0x1800199a0  nop
0x1800199a1  mov     rdi, [rbp+57h+arg_0]
0x1800199a5  test    rdi, rdi
0x1800199a8  jnz     short loc_1800199D4
0x1800199aa  lea     rdx, [rbp+57h+var_C8]
0x1800199ae  mov     rcx, rsi
0x1800199b1  call    ?ClearThreadTask@CThread@WorkThreadManager@@QEAA?AUTaskData@2@XZ; WorkThreadManager::CThread::ClearThreadTask(void)
0x1800199b6  mov     rdx, rax
0x1800199b9  lea     rcx, [rbp+57h+var_80]
0x1800199bd  call    ??4TaskData@WorkThreadManager@@QEAAAEAU01@$$QEAU01@@Z; WorkThreadManager::TaskData::operator=(WorkThreadManager::TaskData &&)
0x1800199c2  lea     rcx, [rbp+57h+var_C8]; this
0x1800199c6  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x1800199cb  mov     [rsi+29h], r14b
0x1800199cf  mov     bl, r14b
0x1800199d2  jmp     short loc_180019A18
0x1800199d4  mov     bl, r15b
0x1800199d7  call    cs:__imp_GetTickCount
0x1800199dd  mov     r9d, eax
0x1800199e0  mov     r8, rdi
0x1800199e3  lea     rdx, [rbp+57h+var_C8]
0x1800199e7  mov     rcx, rsi
0x1800199ea  call    ?SetThreadTask@CThread@WorkThreadManager@@QEAA?AUTaskData@2@$$QEAU32@K@Z; WorkThreadManager::CThread::SetThreadTask(WorkThreadManager::TaskData &&,ulong)
0x1800199ef  mov     rdx, rax
0x1800199f2  lea     rcx, [rbp+57h+var_80]
0x1800199f6  call    ??4TaskData@WorkThreadManager@@QEAAAEAU01@$$QEAU01@@Z; WorkThreadManager::TaskData::operator=(WorkThreadManager::TaskData &&)
0x1800199fb  lea     rcx, [rbp+57h+var_C8]; this
0x1800199ff  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180019a04  mov     rcx, rdi; this
0x180019a07  mov     rdi, r15
0x180019a0a  mov     [rbp+57h+arg_0], r15
0x180019a0e  test    rcx, rcx
0x180019a11  jz      short loc_180019A18
0x180019a13  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180019a18  xor     edx, edx
0x180019a1a  lea     rcx, [rsp+100h+var_E0]
0x180019a1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180019a24  mov     r8d, dword ptr [rbp+57h+var_80+4]
0x180019a28  lea     rdx, [rsp+100h+var_D8]
0x180019a2d  call    ?AdjustThreadPriority@CThread@WorkThreadManager@@QEAA@W4TaskOptions@Internal@Windows@@@Z; WorkThreadManager::CThread::AdjustThreadPriority(Windows::Internal::TaskOptions)
0x180019a32  lea     rcx, [rbp+57h+var_68]; this
0x180019a36  call    ?set_wob_ticket@wil@@YA_NAEBUwob_ticket@1@@Z; wil::set_wob_ticket(wil::wob_ticket const &)
0x180019a3b  mov     [rbp+57h+var_C8], 1
0x180019a43  mov     [rbp+57h+var_C0], r15d
0x180019a47  mov     [rbp+57h+var_B8], r15
0x180019a4b  mov     [rbp+57h+var_B0], r15b
0x180019a4f  xor     eax, eax
0x180019a51  mov     [rbp+57h+var_AF], ax
0x180019a55  mov     [rbp+57h+var_AD], al
0x180019a58  mov     [rbp+57h+var_AC], rax
0x180019a5c  xorps   xmm0, xmm0
0x180019a5f  movdqu  [rbp+57h+var_A0], xmm0
0x180019a64  movups  [rbp+57h+var_90], xmm0
0x180019a68  lea     rax, [rbp+57h+var_90]
0x180019a6c  mov     qword ptr [rbp+57h+var_90+8], rax
0x180019a70  lea     rax, [rbp+57h+var_90]
0x180019a74  mov     qword ptr [rbp+57h+var_90], rax
0x180019a78  lea     rdx, [rbp+57h+var_C8]
0x180019a7c  lea     rcx, [rbp+57h+var_80]
0x180019a80  call    ??4TaskData@WorkThreadManager@@QEAAAEAU01@$$QEAU01@@Z; WorkThreadManager::TaskData::operator=(WorkThreadManager::TaskData &&)
0x180019a85  lea     rcx, [rbp+57h+var_C8]; this
0x180019a89  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180019a8e  cmp     [rbp+57h+var_D0], r15b
0x180019a92  jz      short loc_180019AAD
0x180019a94  cmp     [rsp+100h+var_D8], r15d
0x180019a99  jz      short loc_180019AAD
0x180019a9b  call    cs:__imp_GetCurrentThread
0x180019aa1  mov     edx, [rbp+57h+nPriority]; nPriority
0x180019aa4  mov     rcx, rax; hThread
0x180019aa7  call    cs:__imp_SetThreadPriority
0x180019aad  test    bl, bl
0x180019aaf  jz      loc_180019B99
0x180019ab5  mov     r14, r15
0x180019ab8  mov     [rbp+57h+arg_8], r15
0x180019abc  mov     rcx, r12; SRWLock
0x180019abf  call    cs:__imp_AcquireSRWLockExclusive
0x180019ac5  mov     [rbp+57h+arg_18], r12
0x180019ac9  mov     [rsi+29h], r15b
0x180019acd  lea     rdx, [rbp+57h+arg_10]
0x180019ad1  lea     rcx, ?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A; WorkThreadManager::TaskList WorkThreadManager::s_taskFloodingList
0x180019ad8  call    ?PopFront@TaskList@WorkThreadManager@@QEAA?AV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@XZ; WorkThreadManager::TaskList::PopFront(void)
0x180019add  mov     rdx, rax
0x180019ae0  lea     rcx, [rbp+57h+arg_0]
0x180019ae4  call    ??4?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x180019ae9  mov     rcx, [rbp+57h+arg_10]; this
0x180019aed  mov     [rbp+57h+arg_10], r15
0x180019af1  test    rcx, rcx
0x180019af4  jz      short loc_180019AFB
0x180019af6  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180019afb  mov     rbx, [rbp+57h+arg_0]
0x180019aff  test    rbx, rbx
0x180019b02  jz      short loc_180019B58
0x180019b04  mov     eax, [rsi+98h]
0x180019b0a  cmp     [rbx+8], eax
0x180019b0d  jnz     short loc_180019B58
0x180019b0f  mov     r8d, [rbx+4]
0x180019b13  mov     edx, [rbx]
0x180019b15  mov     rcx, rsi
0x180019b18  call    ?Eligible@CThread@WorkThreadManager@@QEBA_NW4TaskApartment@Internal@Windows@@W4TaskOptions@45@@Z; WorkThreadManager::CThread::Eligible(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions)
0x180019b1d  test    al, al
0x180019b1f  jz      short loc_180019B58
0x180019b21  call    cs:__imp_GetTickCount
0x180019b27  mov     r9d, eax
0x180019b2a  mov     r8, rbx
0x180019b2d  lea     rdx, [rbp+57h+var_C8]
0x180019b31  mov     rcx, rsi
0x180019b34  call    ?SetThreadTask@CThread@WorkThreadManager@@QEAA?AUTaskData@2@$$QEAU32@K@Z; WorkThreadManager::CThread::SetThreadTask(WorkThreadManager::TaskData &&,ulong)
0x180019b39  lea     rcx, [rbp+57h+var_C8]; this
0x180019b3d  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180019b42  mov     rdi, r15
0x180019b45  mov     [rbp+57h+arg_0], r15
0x180019b49  test    rbx, rbx
0x180019b4c  jz      short loc_180019B6D
0x180019b4e  mov     rcx, rbx; this
0x180019b51  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180019b56  jmp     short loc_180019B6D
0x180019b58  lea     rdx, [rbp+57h+arg_0]
0x180019b5c  lea     rcx, [rbp+57h+arg_8]
0x180019b60  call    ??4?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x180019b65  mov     rdi, [rbp+57h+arg_0]
0x180019b69  mov     r14, [rbp+57h+arg_8]
0x180019b6d  xor     edx, edx
0x180019b6f  lea     rcx, [rbp+57h+arg_18]
0x180019b73  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180019b78  test    r14, r14
0x180019b7b  jz      short loc_180019B8F
0x180019b7d  mov     [rbp+57h+arg_8], r15
0x180019b81  mov     [rbp+57h+arg_10], r14
0x180019b85  lea     rcx, [rbp+57h+arg_10]
0x180019b89  call    ?s_AttachAndRecoverTask@WorkThreadManager@@CAXV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@@Z; WorkThreadManager::s_AttachAndRecoverTask(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>)
0x180019b8e  nop
0x180019b8f  lea     rcx, [rbp+57h+arg_18]
0x180019b93  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180019b98  nop
0x180019b99  test    rdi, rdi
0x180019b9c  jz      short loc_180019BA7
0x180019b9e  mov     rcx, rdi; this
0x180019ba1  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x180019ba6  nop
0x180019ba7  lea     rcx, [rsp+100h+var_E0]
0x180019bac  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180019bb1  nop
0x180019bb2  lea     rcx, [rbp+57h+var_80]; this
0x180019bb6  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x180019bbb  add     rsp, 0D0h
0x180019bc2  pop     r15
0x180019bc4  pop     r14
0x180019bc6  pop     r12
0x180019bc8  pop     rdi
0x180019bc9  pop     rsi
0x180019bca  pop     rbx
0x180019bcb  pop     rbp
0x180019bcc  retn
```
