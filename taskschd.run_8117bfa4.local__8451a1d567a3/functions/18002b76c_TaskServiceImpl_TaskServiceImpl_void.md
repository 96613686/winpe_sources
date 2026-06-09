# TaskServiceImpl::~TaskServiceImpl(void)

- ea: `0x18002b76c`
- end: `0x18002b825`
- name: `??1TaskServiceImpl@@QEAA@XZ`
- size: `185`
- prototype: `void __fastcall(TaskServiceImpl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b5d0`

## callees

- `0x18000b55c`
- `0x18000b584`
- `0x18002b82c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b7bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b7bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b7d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b7e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b7f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b7d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b7e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b7f6`

## pseudocode

```c
void __fastcall TaskServiceImpl::~TaskServiceImpl(TaskServiceImpl *this)
{
  *((_DWORD *)this + 59) = 2118800201;
  *(_QWORD *)this = &TaskServiceImpl::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &TaskServiceImpl::`vftable'{for `ITaskSchedulerEx2'};
  *((_QWORD *)this + 2) = &TaskServiceImpl::`vftable'{for `IMaintenanceScheduler'};
  *((_QWORD *)this + 3) = &TaskServiceImpl::`vftable'{for `ISupportErrorInfo'};
  UniSession::~UniSession((TaskServiceImpl *)((char *)this + 304));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  SysFreeString(*((BSTR *)this + 32));
  SysFreeString(*((BSTR *)this + 31));
  SysFreeString(*((BSTR *)this + 30));
  TaskServiceImpl::_MAINTENANCE_POLICY::~_MAINTENANCE_POLICY((TaskServiceImpl *)((char *)this + 160));
  TaskServiceImpl::_MAINTENANCE_POLICY::~_MAINTENANCE_POLICY((TaskServiceImpl *)((char *)this + 88));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((TaskServiceImpl *)((char *)this + 40));
}

```

## disassembly

```asm
0x18002b76c  push    rbx
0x18002b76e  sub     rsp, 20h
0x18002b772  lea     rax, ??_7TaskServiceImpl@@6B?$IDispatchImpl@UITaskService@@$1?_GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85@@3U__s_GUID@@B$1?LIBID_TaskScheduler@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const TaskServiceImpl::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'}
0x18002b779  mov     dword ptr [rcx+0ECh], 7E4A5349h
0x18002b783  mov     [rcx], rax
0x18002b786  mov     rbx, rcx
0x18002b789  lea     rax, ??_7TaskServiceImpl@@6BITaskSchedulerEx2@@@; const TaskServiceImpl::`vftable'{for `ITaskSchedulerEx2'}
0x18002b790  mov     [rcx+8], rax
0x18002b794  lea     rax, ??_7TaskServiceImpl@@6BIMaintenanceScheduler@@@; const TaskServiceImpl::`vftable'{for `IMaintenanceScheduler'}
0x18002b79b  mov     [rcx+10h], rax
0x18002b79f  lea     rax, ??_7TaskServiceImpl@@6BISupportErrorInfo@@@; const TaskServiceImpl::`vftable'{for `ISupportErrorInfo'}
0x18002b7a6  mov     [rcx+18h], rax
0x18002b7aa  add     rcx, 130h; this
0x18002b7b1  call    ??1UniSession@@QEAA@XZ; UniSession::~UniSession(void)
0x18002b7b6  lea     rcx, [rbx+108h]; lpCriticalSection
0x18002b7bd  call    cs:__imp_DeleteCriticalSection
0x18002b7c4  nop     dword ptr [rax+rax+00h]
0x18002b7c9  mov     rcx, [rbx+100h]; bstrString
0x18002b7d0  call    cs:__imp_SysFreeString
0x18002b7d7  nop     dword ptr [rax+rax+00h]
0x18002b7dc  mov     rcx, [rbx+0F8h]; bstrString
0x18002b7e3  call    cs:__imp_SysFreeString
0x18002b7ea  nop     dword ptr [rax+rax+00h]
0x18002b7ef  mov     rcx, [rbx+0F0h]; bstrString
0x18002b7f6  call    cs:__imp_SysFreeString
0x18002b7fd  nop     dword ptr [rax+rax+00h]
0x18002b802  lea     rcx, [rbx+0A0h]; this
0x18002b809  call    ??1_MAINTENANCE_POLICY@TaskServiceImpl@@QEAA@XZ; TaskServiceImpl::_MAINTENANCE_POLICY::~_MAINTENANCE_POLICY(void)
0x18002b80e  lea     rcx, [rbx+58h]; this
0x18002b812  call    ??1_MAINTENANCE_POLICY@TaskServiceImpl@@QEAA@XZ; TaskServiceImpl::_MAINTENANCE_POLICY::~_MAINTENANCE_POLICY(void)
0x18002b817  lea     rcx, [rbx+28h]; this
0x18002b81b  add     rsp, 20h
0x18002b81f  pop     rbx
0x18002b820  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
