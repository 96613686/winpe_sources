# UdmSvcImpl_ToggleContactMaintenance

- ea: `0x1800a64e0`
- end: `0x1800a66d7`
- name: `UdmSvcImpl_ToggleContactMaintenance`
- size: `503`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180009990`
- `0x1800129a8`
- `0x180020994`
- `0x18002eb3c`
- `0x18006e050`
- `0x180072ccc`
- `0x1800a64e0`
- `0x1800ab3ec`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a65fa`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a66a3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a65fa`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800a66a3`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800a656b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800a656b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800a65e0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800a6689`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800a65e0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800a6689`

## string_xrefs

- `0x1800a6533`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c
__int64 __fastcall UdmSvcImpl_ToggleContactMaintenance(struct __MIDL_UserDataModelService_0001 *a1, int a2)
{
  int ServiceDataSession; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  const unsigned __int16 *v6; // rdx
  UdmMaintenanceAdviseSink *v7; // rbx
  LPVOID Context; // [rsp+30h] [rbp-10h] BYREF
  __int64 v10; // [rsp+38h] [rbp-8h] BYREF
  WINBOOL fPending; // [rsp+60h] [rbp+20h] BYREF
  struct ServiceDataSession *v12; // [rsp+68h] [rbp+28h] BYREF

  v12 = 0;
  ServiceDataSession = GetServiceDataSession(a1, &v12);
  v4 = ServiceDataSession;
  if ( ServiceDataSession >= 0 )
  {
    ServiceDataSession = ServiceDataSession::ValidateCallerSecurity(v12, 0, 0x100000u, 0);
    v4 = ServiceDataSession;
    if ( ServiceDataSession >= 0 )
    {
      fPending = 0;
      Context = 0;
      InitOnceBeginInitialize(&stru_18015E3C8, 0, &fPending, &Context);
      v7 = (UdmMaintenanceAdviseSink *)Context;
      if ( a2 )
      {
        if ( !Context )
        {
          v7 = (UdmMaintenanceAdviseSink *)&qword_18015E3D0;
          UnusedUnknown<IUSAdviseSink>::UnusedUnknown<IUSAdviseSink>(&qword_18015E3D0);
          qword_18015E3E0 = 0;
          dword_18015E3E8 = 0;
          qword_18015E3D0 = (__int64)&UdmMaintenanceAdviseSink::`vftable';
          `vector constructor iterator'(
            qword_18015E3F0,
            8u,
            2u,
            ATL::CComPtr<IUdmMaintenanceTask>::CComPtr<IUdmMaintenanceTask>);
          InitializeCriticalSectionEx(&stru_18015E400, 0, 0);
          v10 = 0;
          InitOnceComplete(&stru_18015E3C8, 0, &qword_18015E3D0);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v10);
        }
        ServiceDataSession = UdmMaintenanceAdviseSink::Initialize(v7, v6);
        v4 = ServiceDataSession;
        if ( ServiceDataSession < 0 )
        {
          v5 = 4555;
          goto LABEL_5;
        }
      }
      else
      {
        if ( !Context )
        {
          v7 = (UdmMaintenanceAdviseSink *)&qword_18015E3D0;
          UnusedUnknown<IUSAdviseSink>::UnusedUnknown<IUSAdviseSink>(&qword_18015E3D0);
          qword_18015E3E0 = 0;
          dword_18015E3E8 = 0;
          qword_18015E3D0 = (__int64)&UdmMaintenanceAdviseSink::`vftable';
          `vector constructor iterator'(
            qword_18015E3F0,
            8u,
            2u,
            ATL::CComPtr<IUdmMaintenanceTask>::CComPtr<IUdmMaintenanceTask>);
          InitializeCriticalSectionEx(&stru_18015E400, 0, 0);
          v10 = 0;
          InitOnceComplete(&stru_18015E3C8, 0, &qword_18015E3D0);
          tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(&v10);
        }
        UdmMaintenanceAdviseSink::Uninitialize(v7);
      }
      v4 = 0;
      goto LABEL_15;
    }
    v5 = 4551;
  }
  else
  {
    v5 = 4549;
  }
LABEL_5:
  Log_HREvent(
    (unsigned int)ServiceDataSession,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
    v5);
LABEL_15:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v12);
  return v4;
}

```

## disassembly

```asm
0x1800a64e0  mov     [rsp-8+arg_0], rbx
0x1800a64e5  mov     [rsp-8+arg_8], rdi
0x1800a64ea  push    rbp
0x1800a64eb  mov     rbp, rsp
0x1800a64ee  sub     rsp, 40h
0x1800a64f2  mov     edi, edx
0x1800a64f4  mov     [rbp+arg_18], 0
0x1800a64fc  lea     rdx, [rbp+arg_18]; struct ServiceDataSession **
0x1800a6500  call    ?GetServiceDataSession@@YAJPEAU__MIDL_UserDataModelService_0001@@PEAPEAVServiceDataSession@@@Z; GetServiceDataSession(__MIDL_UserDataModelService_0001 *,ServiceDataSession * *)
0x1800a6505  mov     ebx, eax
0x1800a6507  test    eax, eax
0x1800a6509  jns     short loc_1800A6513
0x1800a650b  mov     r9d, 11C5h
0x1800a6511  jmp     short loc_1800A6533
0x1800a6513  mov     rcx, [rbp+arg_18]; this
0x1800a6517  xor     r9d, r9d; int
0x1800a651a  xor     edx, edx; unsigned int
0x1800a651c  mov     r8d, 100000h; unsigned int
0x1800a6522  call    ?ValidateCallerSecurity@ServiceDataSession@@QEAAJKKH@Z; ServiceDataSession::ValidateCallerSecurity(ulong,ulong,int)
0x1800a6527  mov     ebx, eax
0x1800a6529  test    eax, eax
0x1800a652b  jns     short loc_1800A654B
0x1800a652d  mov     r9d, 11C7h
0x1800a6533  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800a653a  mov     edx, 1
0x1800a653f  mov     ecx, eax
0x1800a6541  call    Log_HREvent
0x1800a6546  jmp     loc_1800A66BC
0x1800a654b  lea     r9, [rbp+Context]; lpContext
0x1800a654f  mov     [rbp+fPending], 0
0x1800a6556  lea     r8, [rbp+fPending]; fPending
0x1800a655a  mov     [rbp+Context], 0
0x1800a6562  xor     edx, edx; dwFlags
0x1800a6564  lea     rcx, stru_18015E3C8; lpInitOnce
0x1800a656b  call    cs:__imp_InitOnceBeginInitialize
0x1800a6571  mov     rbx, [rbp+Context]
0x1800a6575  test    edi, edi
0x1800a6577  jz      loc_1800A6626
0x1800a657d  test    rbx, rbx
0x1800a6580  jnz     loc_1800A6609
0x1800a6586  lea     rbx, qword_18015E3D0
0x1800a658d  mov     rcx, rbx
0x1800a6590  call    ??0?$UnusedUnknown@UIUSAdviseSink@@@@QEAA@XZ; UnusedUnknown<IUSAdviseSink>::UnusedUnknown<IUSAdviseSink>(void)
0x1800a6595  mov     edx, 8; unsigned __int64
0x1800a659a  mov     cs:qword_18015E3E0, 0
0x1800a65a5  lea     rcx, ??_7UdmMaintenanceAdviseSink@@6B@; const UdmMaintenanceAdviseSink::`vftable'
0x1800a65ac  mov     cs:dword_18015E3E8, 0
0x1800a65b6  mov     cs:qword_18015E3D0, rcx
0x1800a65bd  lea     r9, ??0?$CComPtr@VIUdmMaintenanceTask@@@ATL@@QEAA@XZ; void *(*)(void *)
0x1800a65c4  lea     rcx, qword_18015E3F0; void *
0x1800a65cb  lea     r8d, [rdx-6]; unsigned __int64
0x1800a65cf  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800a65d4  xor     r8d, r8d; Flags
0x1800a65d7  lea     rcx, stru_18015E400; lpCriticalSection
0x1800a65de  xor     edx, edx; dwSpinCount
0x1800a65e0  call    cs:__imp_InitializeCriticalSectionEx
0x1800a65e6  mov     r8, rbx; lpContext
0x1800a65e9  mov     [rbp+var_8], 0
0x1800a65f1  xor     edx, edx; dwFlags
0x1800a65f3  lea     rcx, stru_18015E3C8; lpInitOnce
0x1800a65fa  call    cs:__imp_InitOnceComplete
0x1800a6600  lea     rcx, [rbp+var_8]
0x1800a6604  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800a6609  mov     rcx, rbx; this
0x1800a660c  call    ?Initialize@UdmMaintenanceAdviseSink@@QEAAJPEBG@Z; UdmMaintenanceAdviseSink::Initialize(ushort const *)
0x1800a6611  mov     ebx, eax
0x1800a6613  test    eax, eax
0x1800a6615  jns     loc_1800A66BA
0x1800a661b  mov     r9d, 11CBh
0x1800a6621  jmp     loc_1800A6533
0x1800a6626  test    rbx, rbx
0x1800a6629  jnz     loc_1800A66B2
0x1800a662f  lea     rbx, qword_18015E3D0
0x1800a6636  mov     rcx, rbx
0x1800a6639  call    ??0?$UnusedUnknown@UIUSAdviseSink@@@@QEAA@XZ; UnusedUnknown<IUSAdviseSink>::UnusedUnknown<IUSAdviseSink>(void)
0x1800a663e  mov     edx, 8; unsigned __int64
0x1800a6643  mov     cs:qword_18015E3E0, 0
0x1800a664e  lea     rcx, ??_7UdmMaintenanceAdviseSink@@6B@; const UdmMaintenanceAdviseSink::`vftable'
0x1800a6655  mov     cs:dword_18015E3E8, 0
0x1800a665f  mov     cs:qword_18015E3D0, rcx
0x1800a6666  lea     r9, ??0?$CComPtr@VIUdmMaintenanceTask@@@ATL@@QEAA@XZ; void *(*)(void *)
0x1800a666d  lea     rcx, qword_18015E3F0; void *
0x1800a6674  lea     r8d, [rdx-6]; unsigned __int64
0x1800a6678  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1800a667d  xor     r8d, r8d; Flags
0x1800a6680  lea     rcx, stru_18015E400; lpCriticalSection
0x1800a6687  xor     edx, edx; dwSpinCount
0x1800a6689  call    cs:__imp_InitializeCriticalSectionEx
0x1800a668f  mov     r8, rbx; lpContext
0x1800a6692  mov     [rbp+var_8], 0
0x1800a669a  xor     edx, edx; dwFlags
0x1800a669c  lea     rcx, stru_18015E3C8; lpInitOnce
0x1800a66a3  call    cs:__imp_InitOnceComplete
0x1800a66a9  lea     rcx, [rbp+var_8]
0x1800a66ad  call    ??1_Initializer@?$_LazyImpl@VComposingStatusChangedEventSink@@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@V?$static_lazy@VComposingStatusChangedEventSink@@$0A@V?$lazy_construct@VComposingStatusChangedEventSink@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<ComposingStatusChangedEventSink,tlx::lazy_construct<ComposingStatusChangedEventSink>,tlx::static_lazy<ComposingStatusChangedEventSink,0,tlx::lazy_construct<ComposingStatusChangedEventSink>>>::_Initializer::~_Initializer(void)
0x1800a66b2  mov     rcx, rbx; this
0x1800a66b5  call    ?Uninitialize@UdmMaintenanceAdviseSink@@QEAAXXZ; UdmMaintenanceAdviseSink::Uninitialize(void)
0x1800a66ba  xor     ebx, ebx
0x1800a66bc  lea     rcx, [rbp+arg_18]
0x1800a66c0  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800a66c5  mov     rdi, [rsp+40h+arg_8]
0x1800a66ca  mov     eax, ebx
0x1800a66cc  mov     rbx, [rsp+40h+arg_0]
0x1800a66d1  add     rsp, 40h
0x1800a66d5  pop     rbp
0x1800a66d6  retn
```
