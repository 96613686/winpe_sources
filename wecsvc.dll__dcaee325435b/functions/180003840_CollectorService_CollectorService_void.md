# CollectorService::CollectorService(void)

- ea: `0x180003840`
- end: `0x180003a47`
- name: `??0CollectorService@@QEAA@XZ`
- size: `519`
- prototype: `CollectorService *__fastcall(CollectorService *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180002694`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003430`
- `0x180003840`
- `0x180003b0c`
- `0x180003d10`
- `0x180003e3c`
- `0x180007e38`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038c0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003875`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003885`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003875`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180003885`
- `ADVAPI32!EventRegister` at `0x1800039c3`
- `ADVAPI32!EventRegister` at `0x1800039c3`

## string_xrefs

- `0x18000390c`: `admin\wmi\events\forwarding\collector\service\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CollectorService *__fastcall CollectorService::CollectorService(CollectorService *this)
{
  struct AbstractEventProcessorManager **v2; // r14
  HANDLE EventW; // rbx
  DWORD LastError; // ebx
  _QWORD *v5; // rax
  ULONGLONG *v6; // rbx
  ULONGLONG *v7; // rcx
  SubscriptionManager *v8; // rax
  SubscriptionManager *v9; // rax
  GUID ProviderId; // [rsp+20h] [rbp-50h] BYREF
  void **pExceptionObject; // [rsp+30h] [rbp-40h] BYREF
  char v13; // [rsp+38h] [rbp-38h]
  const char *v14; // [rsp+40h] [rbp-30h]
  __int64 v15; // [rsp+48h] [rbp-28h]
  __int64 v16; // [rsp+50h] [rbp-20h]
  DWORD v17; // [rsp+58h] [rbp-18h]
  int v18; // [rsp+5Ch] [rbp-14h]
  int v19; // [rsp+60h] [rbp-10h]
  SubscriptionManager *v20; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)this = 0;
  v2 = (struct AbstractEventProcessorManager **)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 24), 0, 0);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 64), 0, 0);
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 14) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  wmi::AutoHandle::Close((CollectorService *)((char *)this + 112));
  *((_QWORD *)this + 14) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, LastError);
    }
    v13 = 0;
    v14 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v15 = 0;
    v16 = 0;
    v17 = LastError;
    v18 = -1;
    v19 = 203;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v5 = operator new(0x10u);
  if ( v5 )
  {
    v5[1] = 0;
    *v5 = &wmi::RefBase::`vftable';
    *((_DWORD *)v5 + 2) = 0;
    *v5 = &EventProcessorManager::`vftable';
  }
  else
  {
    v5 = 0;
  }
  wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(v2, v5);
  v6 = (ULONGLONG *)operator new(0x10u);
  v20 = (SubscriptionManager *)v6;
  if ( v6 )
  {
    ProviderId = (GUID)EVENTCOLLECTOR_PROVIDER;
    *v6 = (ULONGLONG)&VistaEventReporter::`vftable';
    v6[1] = 0;
    EventRegister(&ProviderId, 0, 0, v6 + 1);
  }
  else
  {
    v6 = 0;
  }
  v20 = 0;
  v7 = (ULONGLONG *)*((_QWORD *)this + 2);
  if ( v6 != v7 && v7 )
    (*(void (__fastcall **)(ULONGLONG *, __int64))*v7)(v7, 1);
  *((_QWORD *)this + 2) = v6;
  std::auto_ptr<AbstractEventReporter>::~auto_ptr<AbstractEventReporter>(&v20);
  v8 = (SubscriptionManager *)operator new(0x90u);
  v20 = v8;
  if ( v8 )
    v9 = SubscriptionManager::SubscriptionManager(v8, *v2, *((struct AbstractEventReporter **)this + 2));
  else
    v9 = 0;
  wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(this, v9);
  return this;
}

```

## disassembly

```asm
0x180003840  mov     [rsp-28h+arg_10], rbx
0x180003845  mov     [rsp-28h+arg_0], rcx
0x18000384a  push    rbp
0x18000384b  push    rsi
0x18000384c  push    rdi
0x18000384d  push    r14
0x18000384f  push    r15
0x180003851  mov     rbp, rsp
0x180003854  sub     rsp, 70h
0x180003858  mov     rsi, rcx
0x18000385b  xor     r15d, r15d
0x18000385e  mov     [rcx], r15
0x180003861  lea     r14, [rcx+8]
0x180003865  mov     [r14], r15
0x180003868  mov     [rcx+10h], r15
0x18000386c  add     rcx, 18h; lpCriticalSection
0x180003870  xor     r8d, r8d; Flags
0x180003873  xor     edx, edx; dwSpinCount
0x180003875  call    cs:__imp_InitializeCriticalSectionEx
0x18000387b  nop
0x18000387c  lea     rcx, [rsi+40h]; lpCriticalSection
0x180003880  xor     r8d, r8d; Flags
0x180003883  xor     edx, edx; dwSpinCount
0x180003885  call    cs:__imp_InitializeCriticalSectionEx
0x18000388b  nop
0x18000388c  mov     [rsi+68h], r15d
0x180003890  lea     rdi, [rsi+70h]
0x180003894  mov     [rdi], r15
0x180003897  xor     r9d, r9d; lpName
0x18000389a  xor     r8d, r8d; bInitialState
0x18000389d  lea     edx, [r15+1]; bManualReset
0x1800038a1  xor     ecx, ecx; lpEventAttributes
0x1800038a3  call    cs:__imp_CreateEventW
0x1800038a9  mov     rbx, rax
0x1800038ac  mov     rcx, rdi; this
0x1800038af  call    ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
0x1800038b4  mov     [rdi], rbx
0x1800038b7  test    rbx, rbx
0x1800038ba  jnz     loc_18000394C
0x1800038c0  call    cs:__imp_GetLastError
0x1800038c6  mov     ebx, eax
0x1800038c8  mov     eax, 507h
0x1800038cd  test    ebx, ebx
0x1800038cf  cmovz   ebx, eax
0x1800038d2  lea     rax, WPP_GLOBAL_Control
0x1800038d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038e0  cmp     rcx, rax
0x1800038e3  jz      short loc_180003908
0x1800038e5  test    byte ptr [rcx+1Ch], 10h
0x1800038e9  jz      short loc_180003908
0x1800038eb  cmp     byte ptr [rcx+19h], 2
0x1800038ef  jb      short loc_180003908
0x1800038f1  lea     edx, [r15+0Bh]
0x1800038f5  mov     r9d, ebx
0x1800038f8  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x1800038ff  mov     rcx, [rcx+10h]
0x180003903  call    WPP_SF_D
0x180003908  mov     [rbp+var_38], r15b
0x18000390c  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180003913  mov     [rbp+var_30], rax
0x180003917  mov     [rbp+var_28], r15
0x18000391b  mov     [rbp+var_20], r15
0x18000391f  mov     [rbp+var_18], ebx
0x180003922  mov     [rbp+var_14], 0FFFFFFFFh
0x180003929  mov     [rbp+var_10], 0CBh
0x180003930  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180003937  mov     [rbp+pExceptionObject], rax
0x18000393b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180003942  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180003946  call    _CxxThrowException_0
0x18000394c  mov     ecx, 10h; dwBytes
0x180003951  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003956  test    rax, rax
0x180003959  jz      short loc_180003979
0x18000395b  mov     [rax+8], r15
0x18000395f  lea     rcx, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180003966  mov     [rax], rcx
0x180003969  mov     [rax+8], r15d
0x18000396d  lea     rcx, ??_7EventProcessorManager@@6B@; const EventProcessorManager::`vftable'
0x180003974  mov     [rax], rcx
0x180003977  jmp     short loc_18000397C
0x180003979  mov     rax, r15
0x18000397c  mov     rdx, rax
0x18000397f  mov     rcx, r14
0x180003982  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x180003987  mov     ecx, 10h; dwBytes
0x18000398c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003991  mov     rbx, rax
0x180003994  mov     [rbp+arg_8], rax
0x180003998  test    rax, rax
0x18000399b  jz      short loc_1800039CB
0x18000399d  movups  xmm0, cs:EVENTCOLLECTOR_PROVIDER
0x1800039a4  movdqu  xmmword ptr [rbp+ProviderId.Data1], xmm0
0x1800039a9  lea     rax, ??_7VistaEventReporter@@6B@; const VistaEventReporter::`vftable'
0x1800039b0  mov     [rbx], rax
0x1800039b3  lea     r9, [rbx+8]; RegHandle
0x1800039b7  mov     [r9], r15
0x1800039ba  xor     r8d, r8d; CallbackContext
0x1800039bd  xor     edx, edx; EnableCallback
0x1800039bf  lea     rcx, [rbp+ProviderId]; ProviderId
0x1800039c3  call    cs:__imp_EventRegister
0x1800039c9  jmp     short loc_1800039CE
0x1800039cb  mov     rbx, r15
0x1800039ce  mov     [rbp+arg_8], r15
0x1800039d2  mov     rcx, [rsi+10h]
0x1800039d6  cmp     rbx, rcx
0x1800039d9  jz      short loc_1800039F0
0x1800039db  test    rcx, rcx
0x1800039de  jz      short loc_1800039F0
0x1800039e0  mov     rax, [rcx]
0x1800039e3  mov     edx, 1
0x1800039e8  mov     rax, [rax]
0x1800039eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f0  mov     [rsi+10h], rbx
0x1800039f4  lea     rcx, [rbp+arg_8]
0x1800039f8  call    ??1?$auto_ptr@VAbstractEventReporter@@@std@@QEAA@XZ; std::auto_ptr<AbstractEventReporter>::~auto_ptr<AbstractEventReporter>(void)
0x1800039fd  mov     ecx, 90h; dwBytes
0x180003a02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a07  mov     [rbp+arg_8], rax
0x180003a0b  test    rax, rax
0x180003a0e  jz      short loc_180003A21
0x180003a10  mov     r8, [rsi+10h]; struct AbstractEventReporter *
0x180003a14  mov     rdx, [r14]; struct AbstractEventProcessorManager *
0x180003a17  mov     rcx, rax; this
0x180003a1a  call    ??0SubscriptionManager@@QEAA@AEAVAbstractEventProcessorManager@@AEAVAbstractEventReporter@@@Z; SubscriptionManager::SubscriptionManager(AbstractEventProcessorManager &,AbstractEventReporter &)
0x180003a1f  jmp     short loc_180003A24
0x180003a21  mov     rax, r15
0x180003a24  mov     rdx, rax
0x180003a27  mov     rcx, rsi
0x180003a2a  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x180003a2f  nop
0x180003a30  mov     rax, rsi
0x180003a33  mov     rbx, [rsp+70h+arg_10]
0x180003a3b  add     rsp, 70h
0x180003a3f  pop     r15
0x180003a41  pop     r14
0x180003a43  pop     rdi
0x180003a44  pop     rsi
0x180003a45  pop     rbp
0x180003a46  retn
```
