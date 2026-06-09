# ATL::CComObject<TaskServiceImpl>::`vector deleting destructor'(uint)

- ea: `0x18000a740`
- end: `0x18000a848`
- name: `??_E?$CComObject@VTaskServiceImpl@@@ATL@@UEAAPEAXI@Z`
- size: `264`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a740`
- `0x18000a850`
- `0x18000a884`
- `0x18000b15c`
- `0x18000b17c`
- `0x180054010`

## import_xrefs

- `msvcrt!free` at `0x18000a834`
- `msvcrt!free` at `0x18000a834`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a7e1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a7e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a7ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a7fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a808`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a7ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a7fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a808`

## pseudocode

```c
char *__fastcall ATL::CComObject<TaskServiceImpl>::`vector deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 8) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<TaskServiceImpl>::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)Block + 1) = &ATL::CComObject<TaskServiceImpl>::`vftable'{for `ITaskSchedulerEx2'};
  *((_QWORD *)Block + 2) = &ATL::CComObject<TaskServiceImpl>::`vftable'{for `IMaintenanceScheduler'};
  *((_QWORD *)Block + 3) = &ATL::CComObject<TaskServiceImpl>::`vftable'{for `ISupportErrorInfo'};
  TaskServiceImpl::FinalRelease((TaskServiceImpl *)Block);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *((_DWORD *)Block + 59) = 2118800201;
  *(_QWORD *)Block = &TaskServiceImpl::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)Block + 1) = &TaskServiceImpl::`vftable'{for `ITaskSchedulerEx2'};
  *((_QWORD *)Block + 2) = &TaskServiceImpl::`vftable'{for `IMaintenanceScheduler'};
  *((_QWORD *)Block + 3) = &TaskServiceImpl::`vftable'{for `ISupportErrorInfo'};
  UniSession::~UniSession((UniSession *)(Block + 304));
  DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 264));
  SysFreeString(*((BSTR *)Block + 32));
  SysFreeString(*((BSTR *)Block + 31));
  SysFreeString(*((BSTR *)Block + 30));
  TaskServiceImpl::_MAINTENANCE_POLICY::~_MAINTENANCE_POLICY((TaskServiceImpl::_MAINTENANCE_POLICY *)(Block + 160));
  TaskServiceImpl::_MAINTENANCE_POLICY::~_MAINTENANCE_POLICY((TaskServiceImpl::_MAINTENANCE_POLICY *)(Block + 88));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(Block + 40));
  if ( (a2 & 1) != 0 )
    free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000a740  mov     [rsp+arg_0], rbx
0x18000a745  push    rdi
0x18000a746  sub     rsp, 20h
0x18000a74a  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6B?$IDispatchImpl@UITaskService@@$1?_GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85@@3U__s_GUID@@B$1?LIBID_TaskScheduler@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'}
0x18000a751  mov     dword ptr [rcx+20h], 0C0000001h
0x18000a758  mov     [rcx], rax
0x18000a75b  mov     ebx, edx
0x18000a75d  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BITaskSchedulerEx2@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ITaskSchedulerEx2'}
0x18000a764  mov     rdi, rcx
0x18000a767  mov     [rcx+8], rax
0x18000a76b  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BIMaintenanceScheduler@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `IMaintenanceScheduler'}
0x18000a772  mov     [rcx+10h], rax
0x18000a776  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ISupportErrorInfo'}
0x18000a77d  mov     [rcx+18h], rax
0x18000a781  call    ?FinalRelease@TaskServiceImpl@@QEAAXXZ; TaskServiceImpl::FinalRelease(void)
0x18000a786  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a78d  mov     rax, [rcx]
0x18000a790  mov     rax, [rax+10h]
0x18000a794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a799  lea     rax, ??_7TaskServiceImpl@@6B?$IDispatchImpl@UITaskService@@$1?_GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85@@3U__s_GUID@@B$1?LIBID_TaskScheduler@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const TaskServiceImpl::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'}
0x18000a7a0  mov     dword ptr [rdi+0ECh], 7E4A5349h
0x18000a7aa  mov     [rdi], rax
0x18000a7ad  lea     rcx, [rdi+130h]; this
0x18000a7b4  lea     rax, ??_7TaskServiceImpl@@6BITaskSchedulerEx2@@@; const TaskServiceImpl::`vftable'{for `ITaskSchedulerEx2'}
0x18000a7bb  mov     [rdi+8], rax
0x18000a7bf  lea     rax, ??_7TaskServiceImpl@@6BIMaintenanceScheduler@@@; const TaskServiceImpl::`vftable'{for `IMaintenanceScheduler'}
0x18000a7c6  mov     [rdi+10h], rax
0x18000a7ca  lea     rax, ??_7TaskServiceImpl@@6BISupportErrorInfo@@@; const TaskServiceImpl::`vftable'{for `ISupportErrorInfo'}
0x18000a7d1  mov     [rdi+18h], rax
0x18000a7d5  call    ??1UniSession@@QEAA@XZ; UniSession::~UniSession(void)
0x18000a7da  lea     rcx, [rdi+108h]; lpCriticalSection
0x18000a7e1  call    cs:__imp_DeleteCriticalSection
0x18000a7e7  mov     rcx, [rdi+100h]; bstrString
0x18000a7ee  call    cs:__imp_SysFreeString
0x18000a7f4  mov     rcx, [rdi+0F8h]; bstrString
0x18000a7fb  call    cs:__imp_SysFreeString
0x18000a801  mov     rcx, [rdi+0F0h]; bstrString
0x18000a808  call    cs:__imp_SysFreeString
0x18000a80e  lea     rcx, [rdi+0A0h]; this
0x18000a815  call    ??1_MAINTENANCE_POLICY@TaskServiceImpl@@QEAA@XZ; TaskServiceImpl::_MAINTENANCE_POLICY::~_MAINTENANCE_POLICY(void)
0x18000a81a  lea     rcx, [rdi+58h]; this
0x18000a81e  call    ??1_MAINTENANCE_POLICY@TaskServiceImpl@@QEAA@XZ; TaskServiceImpl::_MAINTENANCE_POLICY::~_MAINTENANCE_POLICY(void)
0x18000a823  lea     rcx, [rdi+28h]; this
0x18000a827  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x18000a82c  test    bl, 1
0x18000a82f  jz      short loc_18000A83A
0x18000a831  mov     rcx, rdi; Block
0x18000a834  call    cs:__imp_free
0x18000a83a  mov     rbx, [rsp+28h+arg_0]
0x18000a83f  mov     rax, rdi
0x18000a842  add     rsp, 20h
0x18000a846  pop     rdi
0x18000a847  retn
```
