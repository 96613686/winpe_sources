# ATL::CComObject<RegisteredTaskImpl>::`vector deleting destructor'(uint)

- ea: `0x18000acd0`
- end: `0x18000aee3`
- name: `??_E?$CComObject@VRegisteredTaskImpl@@@ATL@@UEAAPEAXI@Z`
- size: `531`
- prototype: `__int64 __fastcall(RegisteredTaskImpl *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000acd0`
- `0x18000b15c`
- `0x18000b17c`
- `0x18000b3e0`
- `0x180054010`

## import_xrefs

- `msvcrt!free` at `0x18000ae4c`
- `msvcrt!free` at `0x18000ae75`
- `msvcrt!free` at `0x18000ae4c`
- `msvcrt!free` at `0x18000ae75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000add5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000add5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad1c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000aed7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000aed7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae36`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ad6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae36`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
RegisteredTaskImpl *__fastcall ATL::CComObject<RegisteredTaskImpl>::`vector deleting destructor'(
        RegisteredTaskImpl *this,
        char a2)
{
  __int64 v4; // r12
  char *v5; // rsi
  __int64 v6; // rcx
  _WORD *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  void *v10; // rcx

  *(_QWORD *)this = &ATL::CComObject<RegisteredTaskImpl>::`vftable'{for `ATL::IDispatchImpl<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &ATL::CComObject<RegisteredTaskImpl>::`vftable'{for `ITaskNotificationSink'};
  *((_DWORD *)this + 4) = -1073741823;
  v4 = 0;
  v5 = (char *)this + 16;
  if ( !this )
    v5 = 0;
  if ( v5 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  if ( *((_QWORD *)this + 20) )
  {
    v4 = *((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = 0;
  }
  v6 = *((_QWORD *)this + 19);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 19) = 0;
  }
  if ( *((_QWORD *)this + 13) < 8u )
    v7 = (_WORD *)((char *)this + 80);
  else
    v7 = (_WORD *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 12) = 0;
  *v7 = 0;
  SysFreeString(*((BSTR *)this + 14));
  *((_QWORD *)this + 14) = 0;
  SysFreeString(*((BSTR *)this + 15));
  *((_QWORD *)this + 15) = 0;
  v8 = *((_QWORD *)this + 18);
  if ( v8 && this != (RegisteredTaskImpl *)-144LL )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)this + 18) = 0;
  }
  v9 = *((_QWORD *)this + 17);
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 16) = 0;
  if ( v5 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  if ( v4 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v4);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)this = &RegisteredTaskImpl::`vftable'{for `ATL::IDispatchImpl<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &RegisteredTaskImpl::`vftable'{for `ITaskNotificationSink'};
  *((_DWORD *)this + 18) = 2118807369;
  RegisteredTaskImpl::FinalRelease(this);
  UniSession::~UniSession((RegisteredTaskImpl *)((char *)this + 128));
  SysFreeString(*((BSTR *)this + 15));
  SysFreeString(*((BSTR *)this + 14));
  if ( *((_QWORD *)this + 13) >= 8u )
  {
    v10 = (void *)*((_QWORD *)this + 10);
    if ( v10 )
      free(v10);
  }
  *((_QWORD *)this + 13) = 7;
  *((_QWORD *)this + 12) = 0;
  *((_WORD *)this + 40) = 0;
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((RegisteredTaskImpl *)((char *)this + 24));
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x18000acd0  push    rbx
0x18000acd2  push    rbp
0x18000acd3  push    rsi
0x18000acd4  push    rdi
0x18000acd5  push    r12
0x18000acd7  push    r13
0x18000acd9  push    r14
0x18000acdb  push    r15
0x18000acdd  sub     rsp, 28h
0x18000ace1  mov     r13d, edx
0x18000ace4  mov     rbx, rcx
0x18000ace7  lea     rax, ??_7?$CComObject@VRegisteredTaskImpl@@@ATL@@6B?$IDispatchImpl@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<RegisteredTaskImpl>::`vftable'{for `ATL::IDispatchImpl<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x18000acee  mov     [rcx], rax
0x18000acf1  lea     rax, ??_7?$CComObject@VRegisteredTaskImpl@@@ATL@@6BITaskNotificationSink@@@; const ATL::CComObject<RegisteredTaskImpl>::`vftable'{for `ITaskNotificationSink'}
0x18000acf8  mov     [rcx+8], rax
0x18000acfc  mov     dword ptr [rcx+10h], 0C0000001h
0x18000ad03  xor     ebp, ebp
0x18000ad05  mov     r12d, ebp
0x18000ad08  lea     rsi, [rcx+10h]
0x18000ad0c  test    rcx, rcx
0x18000ad0f  cmovz   rsi, rbp
0x18000ad13  test    rsi, rsi
0x18000ad16  jz      short loc_18000AD22
0x18000ad18  lea     rcx, [rsi+8]; lpCriticalSection
0x18000ad1c  call    cs:__imp_EnterCriticalSection
0x18000ad22  mov     rax, [rbx+0A0h]
0x18000ad29  test    rax, rax
0x18000ad2c  jnz     loc_18000AEA4
0x18000ad32  mov     rcx, [rbx+98h]
0x18000ad39  test    rcx, rcx
0x18000ad3c  jnz     loc_18000AEB3
0x18000ad42  cmp     qword ptr [rbx+68h], 8
0x18000ad47  jb      loc_18000AECB
0x18000ad4d  mov     rcx, [rbx+50h]
0x18000ad51  mov     [rbx+60h], rbp
0x18000ad55  mov     [rcx], bp
0x18000ad58  mov     rcx, [rbx+70h]; bstrString
0x18000ad5c  call    cs:__imp_SysFreeString
0x18000ad62  mov     [rbx+70h], rbp
0x18000ad66  mov     rcx, [rbx+78h]; bstrString
0x18000ad6a  call    cs:__imp_SysFreeString
0x18000ad70  mov     [rbx+78h], rbp
0x18000ad74  lea     rbp, [rbx+90h]
0x18000ad7b  mov     rcx, [rbp+0]
0x18000ad7f  test    rcx, rcx
0x18000ad82  jz      short loc_18000AD9D
0x18000ad84  test    rbp, rbp
0x18000ad87  jz      short loc_18000AD9D
0x18000ad89  mov     rax, [rcx]
0x18000ad8c  mov     rax, [rax+10h]
0x18000ad90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad95  mov     qword ptr [rbp+0], 0
0x18000ad9d  mov     rcx, [rbx+88h]
0x18000ada4  test    rcx, rcx
0x18000ada7  jz      short loc_18000ADBC
0x18000ada9  mov     eax, 0FFFFFFFFh
0x18000adae  lock xadd [rcx+8], eax
0x18000adb3  cmp     eax, 1
0x18000adb6  jz      loc_18000AE8F
0x18000adbc  xor     ebp, ebp
0x18000adbe  mov     [rbx+88h], rbp
0x18000adc5  mov     [rbx+80h], rbp
0x18000adcc  test    rsi, rsi
0x18000adcf  jz      short loc_18000ADDB
0x18000add1  lea     rcx, [rsi+8]; lpCriticalSection
0x18000add5  call    cs:__imp_LeaveCriticalSection
0x18000addb  test    r12, r12
0x18000adde  jnz     loc_18000AED4
0x18000ade4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000adeb  mov     rax, [rcx]
0x18000adee  mov     rax, [rax+10h]
0x18000adf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf7  nop
0x18000adf8  lea     rax, ??_7RegisteredTaskImpl@@6B?$IDispatchImpl@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const RegisteredTaskImpl::`vftable'{for `ATL::IDispatchImpl<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x18000adff  mov     [rbx], rax
0x18000ae02  lea     rax, ??_7RegisteredTaskImpl@@6BITaskNotificationSink@@@; const RegisteredTaskImpl::`vftable'{for `ITaskNotificationSink'}
0x18000ae09  mov     [rbx+8], rax
0x18000ae0d  mov     dword ptr [rbx+48h], 7E4A6F49h
0x18000ae14  mov     rcx, rbx; this
0x18000ae17  call    ?FinalRelease@RegisteredTaskImpl@@QEAAXXZ; RegisteredTaskImpl::FinalRelease(void)
0x18000ae1c  lea     rcx, [rbx+80h]; this
0x18000ae23  call    ??1UniSession@@QEAA@XZ; UniSession::~UniSession(void)
0x18000ae28  mov     rcx, [rbx+78h]; bstrString
0x18000ae2c  call    cs:__imp_SysFreeString
0x18000ae32  mov     rcx, [rbx+70h]; bstrString
0x18000ae36  call    cs:__imp_SysFreeString
0x18000ae3c  cmp     qword ptr [rbx+68h], 8
0x18000ae41  jb      short loc_18000AE52
0x18000ae43  mov     rcx, [rbx+50h]; Block
0x18000ae47  test    rcx, rcx
0x18000ae4a  jz      short loc_18000AE52
0x18000ae4c  call    cs:__imp_free
0x18000ae52  mov     qword ptr [rbx+68h], 7
0x18000ae5a  mov     [rbx+60h], rbp
0x18000ae5e  mov     [rbx+50h], bp
0x18000ae62  lea     rcx, [rbx+18h]; this
0x18000ae66  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x18000ae6b  nop
0x18000ae6c  test    r13b, 1
0x18000ae70  jz      short loc_18000AE7B
0x18000ae72  mov     rcx, rbx; Block
0x18000ae75  call    cs:__imp_free
0x18000ae7b  mov     rax, rbx
0x18000ae7e  add     rsp, 28h
0x18000ae82  pop     r15
0x18000ae84  pop     r14
0x18000ae86  pop     r13
0x18000ae88  pop     r12
0x18000ae8a  pop     rdi
0x18000ae8b  pop     rsi
0x18000ae8c  pop     rbp
0x18000ae8d  pop     rbx
0x18000ae8e  retn
0x18000ae8f  mov     rax, [rcx]
0x18000ae92  mov     edx, 1
0x18000ae97  mov     rax, [rax]
0x18000ae9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae9f  jmp     loc_18000ADBC
0x18000aea4  mov     r12, rax
0x18000aea7  mov     [rbx+0A0h], rbp
0x18000aeae  jmp     loc_18000AD32
0x18000aeb3  mov     rax, [rcx]
0x18000aeb6  mov     rax, [rax+10h]
0x18000aeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aebf  mov     [rbx+98h], rbp
0x18000aec6  jmp     loc_18000AD42
0x18000aecb  lea     rcx, [rbx+50h]
0x18000aecf  jmp     loc_18000AD51
0x18000aed4  mov     rcx, r12
0x18000aed7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000aedd  jmp     loc_18000ADE4
```
