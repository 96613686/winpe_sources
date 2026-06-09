# NotificationServiceImpl::~NotificationServiceImpl(void)

- ea: `0x18006a8fc`
- end: `0x18006ab06`
- name: `??1NotificationServiceImpl@@UEAA@XZ`
- size: `522`
- prototype: `void __fastcall(NotificationServiceImpl *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ad20`

## callees

- `0x18000af1c`
- `0x18000ba54`
- `0x18000fe2c`
- `0x180033884`
- `0x18006a8fc`
- `0x18006b4f8`
- `0x18006cc58`
- `0x180074b2c`
- `0x180074c2c`
- `0x180074d00`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006aa4f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006aa59`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006aaa6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006aa4f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006aa59`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006aaa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a9e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a9e5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006a95e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18006a95e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006a9aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006a9aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006a9b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006a9b7`

## pseudocode

```c
void __fastcall NotificationServiceImpl::~NotificationServiceImpl(NotificationServiceImpl *this)
{
  struct _TP_WORK *v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  char *v6; // rcx
  __int64 v7; // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  void *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9

  *(_QWORD *)this = &NotificationServiceImpl::`vftable'{for `INotificationService'};
  *((_QWORD *)this + 1) = &NotificationServiceImpl::`vftable'{for `IWNPTransportInternalEvents2'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  if ( *((_QWORD *)this + 41) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 41) = 0;
  }
  NotificationServiceImpl::DeleteKADetectorRegistrationTimer(this);
  NotificationServiceImpl::UnregisterKADetector(this);
  NotificationServiceImpl::UnInitializeFastKADetectionOnWifi(this);
  NotificationServiceImpl::WaitForDisconnect(this);
  NotificationServiceImpl::DeleteKADetectorRegistrationTimer(this);
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 42);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 42));
    *((_QWORD *)this + 42) = 0;
  }
  NotificationServiceImpl::ClearOutstandingRequestList(v2, (struct _LIST_ENTRY *)this + 10);
  v6 = (char *)*((_QWORD *)this + 17);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 17) = 0;
  }
  v7 = *((_QWORD *)this + 13);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 16LL))(v7, 1);
    *((_QWORD *)this + 13) = 0;
  }
  v8 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 16);
  if ( v8 )
  {
    (**v8)(v8, 1);
    *((_QWORD *)this + 16) = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 112, v3, v4, v5);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 120, v9, v10, v11);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  _InterlockedDecrement(&g_Count);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 352, v12, v13, v14);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>((char *)this + 240);
  v18 = (void *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 26) = 0;
  if ( v18 )
    MemoryFree(v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 152, v15, v16, v17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 120, v19, v20, v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 112, v22, v23, v24);
  *(_QWORD *)this = &INotificationService::`vftable';
}

```

## disassembly

```asm
0x18006a8fc  push    rbx
0x18006a8fe  push    rsi
0x18006a8ff  push    rdi
0x18006a900  push    r14
0x18006a902  sub     rsp, 28h
0x18006a906  mov     rbx, rcx
0x18006a909  lea     rax, ??_7NotificationServiceImpl@@6BINotificationService@@@; const NotificationServiceImpl::`vftable'{for `INotificationService'}
0x18006a910  mov     [rcx], rax
0x18006a913  lea     rax, ??_7NotificationServiceImpl@@6BIWNPTransportInternalEvents2@@@; const NotificationServiceImpl::`vftable'{for `IWNPTransportInternalEvents2'}
0x18006a91a  mov     [rcx+8], rax
0x18006a91e  lea     r14, WPP_GLOBAL_Control
0x18006a925  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a92c  cmp     rcx, r14
0x18006a92f  jz      short loc_18006A952
0x18006a931  test    byte ptr [rcx+1Ch], 2
0x18006a935  jz      short loc_18006A952
0x18006a937  cmp     byte ptr [rcx+19h], 6
0x18006a93b  jb      short loc_18006A952
0x18006a93d  mov     edx, 0Ch
0x18006a942  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006a949  mov     rcx, [rcx+10h]
0x18006a94d  call    WPP_SF_
0x18006a952  mov     rcx, [rbx+148h]
0x18006a959  test    rcx, rcx
0x18006a95c  jz      short loc_18006A96F
0x18006a95e  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18006a964  mov     qword ptr [rbx+148h], 0
0x18006a96f  mov     rcx, rbx; this
0x18006a972  call    ?DeleteKADetectorRegistrationTimer@NotificationServiceImpl@@AEAAXXZ; NotificationServiceImpl::DeleteKADetectorRegistrationTimer(void)
0x18006a977  mov     rcx, rbx; this
0x18006a97a  call    ?UnregisterKADetector@NotificationServiceImpl@@AEAAXXZ; NotificationServiceImpl::UnregisterKADetector(void)
0x18006a97f  mov     rcx, rbx; this
0x18006a982  call    ?UnInitializeFastKADetectionOnWifi@NotificationServiceImpl@@AEAAJXZ; NotificationServiceImpl::UnInitializeFastKADetectionOnWifi(void)
0x18006a987  mov     rcx, rbx; this
0x18006a98a  call    ?WaitForDisconnect@NotificationServiceImpl@@AEAAXXZ; NotificationServiceImpl::WaitForDisconnect(void)
0x18006a98f  mov     rcx, rbx; this
0x18006a992  call    ?DeleteKADetectorRegistrationTimer@NotificationServiceImpl@@AEAAXXZ; NotificationServiceImpl::DeleteKADetectorRegistrationTimer(void)
0x18006a997  mov     rcx, [rbx+150h]; pwk
0x18006a99e  mov     edi, 1
0x18006a9a3  test    rcx, rcx
0x18006a9a6  jz      short loc_18006A9C8
0x18006a9a8  mov     edx, edi; fCancelPendingCallbacks
0x18006a9aa  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18006a9b0  mov     rcx, [rbx+150h]; pwk
0x18006a9b7  call    cs:__imp_CloseThreadpoolWork
0x18006a9bd  mov     qword ptr [rbx+150h], 0
0x18006a9c8  lea     rdx, [rbx+0A0h]; struct _LIST_ENTRY *
0x18006a9cf  call    ?ClearOutstandingRequestList@NotificationServiceImpl@@AEAAXPEAU_LIST_ENTRY@@@Z; NotificationServiceImpl::ClearOutstandingRequestList(_LIST_ENTRY *)
0x18006a9d4  mov     rcx, [rbx+88h]; hObject
0x18006a9db  lea     rax, [rcx-1]
0x18006a9df  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006a9e3  ja      short loc_18006A9F6
0x18006a9e5  call    cs:__imp_CloseHandle
0x18006a9eb  mov     qword ptr [rbx+88h], 0
0x18006a9f6  mov     rcx, [rbx+68h]
0x18006a9fa  test    rcx, rcx
0x18006a9fd  jz      short loc_18006AA15
0x18006a9ff  mov     rax, [rcx]
0x18006aa02  mov     edx, edi
0x18006aa04  mov     rax, [rax+10h]
0x18006aa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa0d  mov     qword ptr [rbx+68h], 0
0x18006aa15  mov     rcx, [rbx+80h]
0x18006aa1c  test    rcx, rcx
0x18006aa1f  jz      short loc_18006AA39
0x18006aa21  mov     rax, [rcx]
0x18006aa24  mov     edx, edi
0x18006aa26  mov     rax, [rax]
0x18006aa29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aa2e  mov     qword ptr [rbx+80h], 0
0x18006aa39  lea     rcx, [rbx+70h]
0x18006aa3d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aa42  lea     rcx, [rbx+78h]
0x18006aa46  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aa4b  lea     rcx, [rbx+10h]; lpCriticalSection
0x18006aa4f  call    cs:__imp_DeleteCriticalSection
0x18006aa55  lea     rcx, [rbx+38h]; lpCriticalSection
0x18006aa59  call    cs:__imp_DeleteCriticalSection
0x18006aa5f  lock dec cs:?g_Count@@3JA; long g_Count
0x18006aa66  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aa6d  cmp     rcx, r14
0x18006aa70  jz      short loc_18006AA93
0x18006aa72  test    byte ptr [rcx+1Ch], 2
0x18006aa76  jz      short loc_18006AA93
0x18006aa78  cmp     byte ptr [rcx+19h], 6
0x18006aa7c  jb      short loc_18006AA93
0x18006aa7e  mov     edx, 0Dh
0x18006aa83  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006aa8a  mov     rcx, [rcx+10h]
0x18006aa8e  call    WPP_SF_
0x18006aa93  lea     rcx, [rbx+160h]
0x18006aa9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aa9f  lea     rcx, [rbx+108h]; lpCriticalSection
0x18006aaa6  call    cs:__imp_DeleteCriticalSection
0x18006aaac  lea     rcx, [rbx+0F0h]
0x18006aab3  call    ??1?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(void)
0x18006aab8  mov     rcx, [rbx+0D0h]; void *
0x18006aabf  mov     qword ptr [rbx+0D0h], 0
0x18006aaca  test    rcx, rcx
0x18006aacd  jz      short loc_18006AAD4
0x18006aacf  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18006aad4  lea     rcx, [rbx+98h]
0x18006aadb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aae0  lea     rcx, [rbx+78h]
0x18006aae4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aae9  lea     rcx, [rbx+70h]
0x18006aaed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aaf2  lea     rax, ??_7INotificationService@@6B@; const INotificationService::`vftable'
0x18006aaf9  mov     [rbx], rax
0x18006aafc  add     rsp, 28h
0x18006ab00  pop     r14
0x18006ab02  pop     rdi
0x18006ab03  pop     rsi
0x18006ab04  pop     rbx
0x18006ab05  retn
```
