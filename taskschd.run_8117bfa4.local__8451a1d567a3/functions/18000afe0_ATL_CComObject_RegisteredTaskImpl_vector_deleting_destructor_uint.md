# ATL::CComObject<RegisteredTaskImpl>::`vector deleting destructor'(uint)

- ea: `0x18000afe0`
- end: `0x18000b22a`
- name: `??_E?$CComObject@VRegisteredTaskImpl@@@ATL@@UEAAPEAXI@Z`
- size: `586`
- prototype: `__int64 __fastcall(RegisteredTaskImpl *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000afe0`
- `0x18000b55c`
- `0x18000b584`
- `0x18000b7c0`
- `0x180058010`

## import_xrefs

- `msvcrt!free` at `0x18000b180`
- `msvcrt!free` at `0x18000b1af`
- `msvcrt!free` at `0x18000b180`
- `msvcrt!free` at `0x18000b1af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b0f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b0f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b02c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b02c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000b218`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000b218`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b072`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b086`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b154`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b164`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b072`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b086`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b154`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b164`

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
0x18000afe0  push    rbx
0x18000afe2  push    rbp
0x18000afe3  push    rsi
0x18000afe4  push    rdi
0x18000afe5  push    r12
0x18000afe7  push    r13
0x18000afe9  push    r14
0x18000afeb  push    r15
0x18000afed  sub     rsp, 28h
0x18000aff1  mov     r13d, edx
0x18000aff4  mov     rbx, rcx
0x18000aff7  lea     rax, ??_7?$CComObject@VRegisteredTaskImpl@@@ATL@@6B?$IDispatchImpl@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<RegisteredTaskImpl>::`vftable'{for `ATL::IDispatchImpl<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x18000affe  mov     [rcx], rax
0x18000b001  lea     rax, ??_7?$CComObject@VRegisteredTaskImpl@@@ATL@@6BITaskNotificationSink@@@; const ATL::CComObject<RegisteredTaskImpl>::`vftable'{for `ITaskNotificationSink'}
0x18000b008  mov     [rcx+8], rax
0x18000b00c  mov     dword ptr [rcx+10h], 0C0000001h
0x18000b013  xor     ebp, ebp
0x18000b015  mov     r12d, ebp
0x18000b018  lea     rsi, [rcx+10h]
0x18000b01c  test    rcx, rcx
0x18000b01f  cmovz   rsi, rbp
0x18000b023  test    rsi, rsi
0x18000b026  jz      short loc_18000B038
0x18000b028  lea     rcx, [rsi+8]; lpCriticalSection
0x18000b02c  call    cs:__imp_EnterCriticalSection
0x18000b033  nop     dword ptr [rax+rax+00h]
0x18000b038  mov     rax, [rbx+0A0h]
0x18000b03f  test    rax, rax
0x18000b042  jnz     loc_18000B1E5
0x18000b048  mov     rcx, [rbx+98h]
0x18000b04f  test    rcx, rcx
0x18000b052  jnz     loc_18000B1F4
0x18000b058  cmp     qword ptr [rbx+68h], 8
0x18000b05d  jb      loc_18000B20C
0x18000b063  mov     rcx, [rbx+50h]
0x18000b067  mov     [rbx+60h], rbp
0x18000b06b  mov     [rcx], bp
0x18000b06e  mov     rcx, [rbx+70h]; bstrString
0x18000b072  call    cs:__imp_SysFreeString
0x18000b079  nop     dword ptr [rax+rax+00h]
0x18000b07e  mov     [rbx+70h], rbp
0x18000b082  mov     rcx, [rbx+78h]; bstrString
0x18000b086  call    cs:__imp_SysFreeString
0x18000b08d  nop     dword ptr [rax+rax+00h]
0x18000b092  mov     [rbx+78h], rbp
0x18000b096  lea     rbp, [rbx+90h]
0x18000b09d  mov     rcx, [rbp+0]
0x18000b0a1  test    rcx, rcx
0x18000b0a4  jz      short loc_18000B0BF
0x18000b0a6  test    rbp, rbp
0x18000b0a9  jz      short loc_18000B0BF
0x18000b0ab  mov     rax, [rcx]
0x18000b0ae  mov     rax, [rax+10h]
0x18000b0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b7  mov     qword ptr [rbp+0], 0
0x18000b0bf  mov     rcx, [rbx+88h]
0x18000b0c6  test    rcx, rcx
0x18000b0c9  jz      short loc_18000B0DE
0x18000b0cb  mov     eax, 0FFFFFFFFh
0x18000b0d0  lock xadd [rcx+8], eax
0x18000b0d5  cmp     eax, 1
0x18000b0d8  jz      loc_18000B1D0
0x18000b0de  xor     ebp, ebp
0x18000b0e0  mov     [rbx+88h], rbp
0x18000b0e7  mov     [rbx+80h], rbp
0x18000b0ee  test    rsi, rsi
0x18000b0f1  jz      short loc_18000B103
0x18000b0f3  lea     rcx, [rsi+8]; lpCriticalSection
0x18000b0f7  call    cs:__imp_LeaveCriticalSection
0x18000b0fe  nop     dword ptr [rax+rax+00h]
0x18000b103  test    r12, r12
0x18000b106  jnz     loc_18000B215
0x18000b10c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b113  mov     rax, [rcx]
0x18000b116  mov     rax, [rax+10h]
0x18000b11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11f  nop
0x18000b120  lea     rax, ??_7RegisteredTaskImpl@@6B?$IDispatchImpl@UIRegisteredTask@@$1?_GUID_9c86f320_dee3_4dd1_b972_a303f26b061e@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const RegisteredTaskImpl::`vftable'{for `ATL::IDispatchImpl<IRegisteredTask,&__s_GUID const _GUID_9c86f320_dee3_4dd1_b972_a303f26b061e,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>'}
0x18000b127  mov     [rbx], rax
0x18000b12a  lea     rax, ??_7RegisteredTaskImpl@@6BITaskNotificationSink@@@; const RegisteredTaskImpl::`vftable'{for `ITaskNotificationSink'}
0x18000b131  mov     [rbx+8], rax
0x18000b135  mov     dword ptr [rbx+48h], 7E4A6F49h
0x18000b13c  mov     rcx, rbx; this
0x18000b13f  call    ?FinalRelease@RegisteredTaskImpl@@QEAAXXZ; RegisteredTaskImpl::FinalRelease(void)
0x18000b144  lea     rcx, [rbx+80h]; this
0x18000b14b  call    ??1UniSession@@QEAA@XZ; UniSession::~UniSession(void)
0x18000b150  mov     rcx, [rbx+78h]; bstrString
0x18000b154  call    cs:__imp_SysFreeString
0x18000b15b  nop     dword ptr [rax+rax+00h]
0x18000b160  mov     rcx, [rbx+70h]; bstrString
0x18000b164  call    cs:__imp_SysFreeString
0x18000b16b  nop     dword ptr [rax+rax+00h]
0x18000b170  cmp     qword ptr [rbx+68h], 8
0x18000b175  jb      short loc_18000B18C
0x18000b177  mov     rcx, [rbx+50h]; Block
0x18000b17b  test    rcx, rcx
0x18000b17e  jz      short loc_18000B18C
0x18000b180  call    cs:__imp_free
0x18000b187  nop     dword ptr [rax+rax+00h]
0x18000b18c  mov     qword ptr [rbx+68h], 7
0x18000b194  mov     [rbx+60h], rbp
0x18000b198  mov     [rbx+50h], bp
0x18000b19c  lea     rcx, [rbx+18h]; this
0x18000b1a0  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x18000b1a5  nop
0x18000b1a6  test    r13b, 1
0x18000b1aa  jz      short loc_18000B1BB
0x18000b1ac  mov     rcx, rbx; Block
0x18000b1af  call    cs:__imp_free
0x18000b1b6  nop     dword ptr [rax+rax+00h]
0x18000b1bb  mov     rax, rbx
0x18000b1be  add     rsp, 28h
0x18000b1c2  pop     r15
0x18000b1c4  pop     r14
0x18000b1c6  pop     r13
0x18000b1c8  pop     r12
0x18000b1ca  pop     rdi
0x18000b1cb  pop     rsi
0x18000b1cc  pop     rbp
0x18000b1cd  pop     rbx
0x18000b1ce  retn
0x18000b1d0  mov     rax, [rcx]
0x18000b1d3  mov     edx, 1
0x18000b1d8  mov     rax, [rax]
0x18000b1db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1e0  jmp     loc_18000B0DE
0x18000b1e5  mov     r12, rax
0x18000b1e8  mov     [rbx+0A0h], rbp
0x18000b1ef  jmp     loc_18000B048
0x18000b1f4  mov     rax, [rcx]
0x18000b1f7  mov     rax, [rax+10h]
0x18000b1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b200  mov     [rbx+98h], rbp
0x18000b207  jmp     loc_18000B058
0x18000b20c  lea     rcx, [rbx+50h]
0x18000b210  jmp     loc_18000B067
0x18000b215  mov     rcx, r12
0x18000b218  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000b21f  nop     dword ptr [rax+rax+00h]
0x18000b224  jmp     loc_18000B10C
```
