# WorkThreadManager::CThread::~CThread(void)

- ea: `0x18000ef1c`
- end: `0x18000f002`
- name: `??1CThread@WorkThreadManager@@EEAA@XZ`
- size: `230`
- prototype: `void __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000eee0`

## callees

- `0x18000ef1c`
- `0x18000f008`
- `0x18000f808`
- `0x18000f834`
- `0x18000f888`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000effa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000effa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000efe5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000efe5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000efef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000efef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000efd6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000efd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WorkThreadManager::CThread::~CThread(WorkThreadManager::CThread *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  unsigned int v5; // edx
  HMODULE v6; // rcx
  WorkThreadManager::TaskData *v7; // rcx

  *(_QWORD *)this = &WorkThreadManager::CThread::`vftable';
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 12), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 12));
  }
  WorkThreadManager::TaskData::~TaskData((WorkThreadManager::CThread *)((char *)this + 144));
  v3 = *((_QWORD *)this + 15);
  if ( v3 )
  {
    *((_QWORD *)this + 15) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 14);
  if ( v4 )
  {
    *((_QWORD *)this + 14) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 104);
  v6 = (HMODULE)*((_QWORD *)this + 8);
  if ( v6 )
    FreeLibrary(v6);
  v7 = (WorkThreadManager::TaskData *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v7 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v7, v5);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 48);
  WorkThreadManager::TaskList::Clear((WorkThreadManager::CThread *)((char *)this + 24));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000ef1c  push    rbx
0x18000ef1e  sub     rsp, 20h
0x18000ef22  mov     rbx, rcx
0x18000ef25  lea     rax, ??_7CThread@WorkThreadManager@@6B@; const WorkThreadManager::CThread::`vftable'
0x18000ef2c  mov     [rcx], rax
0x18000ef2f  mov     rcx, [rcx+60h]; pti
0x18000ef33  test    rcx, rcx
0x18000ef36  jnz     loc_18000EFCE
0x18000ef3c  lea     rcx, [rbx+90h]; this
0x18000ef43  call    ??1TaskData@WorkThreadManager@@QEAA@XZ; WorkThreadManager::TaskData::~TaskData(void)
0x18000ef48  nop
0x18000ef49  mov     rcx, [rbx+78h]
0x18000ef4d  test    rcx, rcx
0x18000ef50  jz      short loc_18000EF67
0x18000ef52  mov     qword ptr [rbx+78h], 0
0x18000ef5a  mov     rax, [rcx]
0x18000ef5d  mov     rax, [rax+10h]
0x18000ef61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef66  nop
0x18000ef67  mov     rcx, [rbx+70h]
0x18000ef6b  test    rcx, rcx
0x18000ef6e  jz      short loc_18000EF85
0x18000ef70  mov     qword ptr [rbx+70h], 0
0x18000ef78  mov     rax, [rcx]
0x18000ef7b  mov     rax, [rax+10h]
0x18000ef7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef84  nop
0x18000ef85  lea     rcx, [rbx+68h]
0x18000ef89  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ef8e  mov     rcx, [rbx+40h]; hLibModule
0x18000ef92  test    rcx, rcx
0x18000ef95  jnz     short loc_18000EFFA
0x18000ef97  mov     rcx, [rbx+38h]; this
0x18000ef9b  mov     qword ptr [rbx+38h], 0
0x18000efa3  test    rcx, rcx
0x18000efa6  jnz     short loc_18000EFC7
0x18000efa8  lea     rcx, [rbx+30h]
0x18000efac  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000efb1  lea     rcx, [rbx+18h]; this
0x18000efb5  call    ?Clear@TaskList@WorkThreadManager@@QEAAXXZ; WorkThreadManager::TaskList::Clear(void)
0x18000efba  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000efc1  add     rsp, 20h
0x18000efc5  pop     rbx
0x18000efc6  retn
0x18000efc7  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000efcc  jmp     short loc_18000EFA8
0x18000efce  xor     r9d, r9d; msWindowLength
0x18000efd1  xor     r8d, r8d; msPeriod
0x18000efd4  xor     edx, edx; pftDueTime
0x18000efd6  call    cs:__imp_SetThreadpoolTimer
0x18000efdc  mov     edx, 1; fCancelPendingCallbacks
0x18000efe1  mov     rcx, [rbx+60h]; pti
0x18000efe5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000efeb  mov     rcx, [rbx+60h]; pti
0x18000efef  call    cs:__imp_CloseThreadpoolTimer
0x18000eff5  jmp     loc_18000EF3C
0x18000effa  call    cs:__imp_FreeLibrary
0x18000f000  jmp     short loc_18000EF97
```
