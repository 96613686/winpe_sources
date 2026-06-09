# TransportRelay::Configure(std::shared_ptr<Transport>,std::shared_ptr<Transport>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bool,ulong)

- ea: `0x1400ee9a8`
- end: `0x1400eec68`
- name: `?Configure@TransportRelay@@QEAAXV?$shared_ptr@VTransport@@@std@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@_NK@Z`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400f1f44`

## callees

- `0x1400027fc`
- `0x140008760`
- `0x14000aeec`
- `0x14002dd18`
- `0x1400341ac`
- `0x1400ee9a8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400eeba7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400eeba7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400ee9da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400ee9da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ee9e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ee9e0`

## string_xrefs

- `0x1400eec56`: `onecore\vm\compute\common\transport\transportrelay.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TransportRelay::Configure(__int64 a1, _QWORD *a2, _QWORD *a3, void *a4, char a5)
{
  __int64 v9; // rbp
  int v10; // eax
  int v11; // eax
  _QWORD *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rcx
  volatile signed __int32 *v18; // rdi
  __int64 v19; // rcx
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx
  unsigned int v22; // [rsp+20h] [rbp-78h]
  __int64 v23; // [rsp+40h] [rbp-58h] BYREF
  __int64 v24[10]; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v26; // [rsp+A0h] [rbp+8h] BYREF
  _QWORD *v27; // [rsp+A8h] [rbp+10h]
  _QWORD *v28; // [rsp+B0h] [rbp+18h]
  void *v29; // [rsp+B8h] [rbp+20h]

  v29 = a4;
  v28 = a3;
  v27 = a2;
  v9 = a1 + 120;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 120));
  *(_DWORD *)(v9 + 8) = GetCurrentThreadId();
  v26 = v9;
  v10 = *(_DWORD *)(a1 + 136);
  if ( v10 )
  {
    if ( v10 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\transportrelay.cpp",
        (const char *)0x139F,
        v22);
    v11 = 3;
  }
  else
  {
    v11 = 1;
  }
  *(_DWORD *)(a1 + 136) = v11;
  v12 = (_QWORD *)(a1 + 200);
  std::wstring::operator=(a1 + 200, a4);
  *(_BYTE *)(a1 + 232) = a5;
  v13 = *a2;
  v14 = a2[1];
  *a2 = 0;
  a2[1] = 0;
  *(_QWORD *)(a1 + 8) = v13;
  v15 = *(volatile signed __int32 **)(a1 + 16);
  *(_QWORD *)(a1 + 16) = v14;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v16 = *a3;
  v17 = a3[1];
  *a3 = 0;
  a3[1] = 0;
  *(_QWORD *)(a1 + 24) = v16;
  v18 = *(volatile signed __int32 **)(a1 + 32);
  *(_QWORD *)(a1 + 32) = v17;
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  *(_DWORD *)(a1 + 88) = 0x4000;
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8), a1);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24), a1);
  v19 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
  if ( *(_DWORD *)v19 > 4u
    && (*(_QWORD *)(v19 + 16) & 0x80u) != 0LL
    && (*(_QWORD *)(v19 + 24) & 0x80LL) == *(_QWORD *)(v19 + 24) )
  {
    v26 = *(_QWORD *)(a1 + 24);
    v23 = *(_QWORD *)(a1 + 8);
    if ( *(_QWORD *)(a1 + 224) > 7u )
      v12 = (_QWORD *)*v12;
    v24[0] = (__int64)v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v19,
      (__int64)v24,
      (__int64)&v23,
      (__int64)&v26);
  }
  *(_DWORD *)(v9 + 8) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v9);
  v20 = (volatile signed __int32 *)a2[1];
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v21 = (volatile signed __int32 *)a3[1];
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  std::wstring::~wstring(a4);
}

```

## disassembly

```asm
0x1400ee9a8  mov     [rsp+arg_18], r9
0x1400ee9ad  mov     [rsp+arg_10], r8
0x1400ee9b2  mov     [rsp+arg_8], rdx
0x1400ee9b7  push    rbx
0x1400ee9b8  push    rbp
0x1400ee9b9  push    rsi
0x1400ee9ba  push    rdi
0x1400ee9bb  push    r12
0x1400ee9bd  push    r13
0x1400ee9bf  push    r14
0x1400ee9c1  push    r15
0x1400ee9c3  sub     rsp, 58h
0x1400ee9c7  mov     r12, r9
0x1400ee9ca  mov     rsi, r8
0x1400ee9cd  mov     r15, rdx
0x1400ee9d0  mov     rbx, rcx
0x1400ee9d3  lea     rbp, [rcx+78h]
0x1400ee9d7  mov     rcx, rbp; SRWLock
0x1400ee9da  call    cs:__imp_AcquireSRWLockExclusive
0x1400ee9e0  call    cs:__imp_GetCurrentThreadId
0x1400ee9e6  mov     [rbp+8], eax
0x1400ee9e9  mov     [rsp+98h+arg_0], rbp
0x1400ee9f1  mov     eax, [rbx+88h]
0x1400ee9f7  test    eax, eax
0x1400ee9f9  jz      short loc_1400EEA0B
0x1400ee9fb  cmp     eax, 2
0x1400ee9fe  jnz     loc_1400EEC48
0x1400eea04  mov     eax, 3
0x1400eea09  jmp     short loc_1400EEA10
0x1400eea0b  mov     eax, 1
0x1400eea10  mov     [rbx+88h], eax
0x1400eea16  lea     r14, [rbx+0C8h]
0x1400eea1d  mov     rdx, r12
0x1400eea20  mov     rcx, r14
0x1400eea23  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400eea28  mov     al, [rsp+98h+arg_20]
0x1400eea2f  mov     [rbx+0E8h], al
0x1400eea35  mov     rax, [r15]
0x1400eea38  mov     rcx, [r15+8]
0x1400eea3c  mov     qword ptr [r15], 0
0x1400eea43  mov     qword ptr [r15+8], 0
0x1400eea4b  mov     [rbx+8], rax
0x1400eea4f  mov     rdi, [rbx+10h]
0x1400eea53  mov     [rbx+10h], rcx
0x1400eea57  or      r13d, 0FFFFFFFFh
0x1400eea5b  test    rdi, rdi
0x1400eea5e  jz      short loc_1400EEA97
0x1400eea60  mov     eax, r13d
0x1400eea63  lock xadd [rdi+8], eax
0x1400eea68  add     eax, r13d
0x1400eea6b  jnz     short loc_1400EEA97
0x1400eea6d  mov     rax, [rdi]
0x1400eea70  mov     rcx, rdi
0x1400eea73  mov     rax, [rax]
0x1400eea76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eea7b  mov     eax, r13d
0x1400eea7e  lock xadd [rdi+0Ch], eax
0x1400eea83  add     eax, r13d
0x1400eea86  jnz     short loc_1400EEA97
0x1400eea88  mov     rax, [rdi]
0x1400eea8b  mov     rcx, rdi
0x1400eea8e  mov     rax, [rax+8]
0x1400eea92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eea97  mov     rax, [rsi]
0x1400eea9a  mov     rcx, [rsi+8]
0x1400eea9e  mov     qword ptr [rsi], 0
0x1400eeaa5  mov     qword ptr [rsi+8], 0
0x1400eeaad  mov     [rbx+18h], rax
0x1400eeab1  mov     rdi, [rbx+20h]
0x1400eeab5  mov     [rbx+20h], rcx
0x1400eeab9  test    rdi, rdi
0x1400eeabc  jz      short loc_1400EEAF5
0x1400eeabe  mov     eax, r13d
0x1400eeac1  lock xadd [rdi+8], eax
0x1400eeac6  add     eax, r13d
0x1400eeac9  jnz     short loc_1400EEAF5
0x1400eeacb  mov     rax, [rdi]
0x1400eeace  mov     rcx, rdi
0x1400eead1  mov     rax, [rax]
0x1400eead4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eead9  mov     eax, r13d
0x1400eeadc  lock xadd [rdi+0Ch], eax
0x1400eeae1  add     eax, r13d
0x1400eeae4  jnz     short loc_1400EEAF5
0x1400eeae6  mov     rax, [rdi]
0x1400eeae9  mov     rcx, rdi
0x1400eeaec  mov     rax, [rax+8]
0x1400eeaf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eeaf5  mov     dword ptr [rbx+58h], 4000h
0x1400eeafc  mov     rcx, [rbx+8]
0x1400eeb00  mov     rax, [rcx]
0x1400eeb03  mov     rdx, rbx
0x1400eeb06  mov     rax, [rax+8]
0x1400eeb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eeb0f  mov     rcx, [rbx+18h]
0x1400eeb13  mov     rax, [rcx]
0x1400eeb16  mov     rdx, rbx
0x1400eeb19  mov     rax, [rax+8]
0x1400eeb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eeb22  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400eeb27  mov     rcx, [rax+8]; int
0x1400eeb2b  mov     eax, [rcx]
0x1400eeb2d  cmp     eax, 4
0x1400eeb30  jbe     short loc_1400EEB9D
0x1400eeb32  mov     rdx, [rcx+18h]
0x1400eeb36  mov     rax, [rcx+10h]
0x1400eeb3a  test    al, al
0x1400eeb3c  jns     short loc_1400EEB9D
0x1400eeb3e  mov     rax, rdx
0x1400eeb41  and     eax, 80h
0x1400eeb46  cmp     rax, rdx
0x1400eeb49  jnz     short loc_1400EEB9D
0x1400eeb4b  mov     rax, [rbx+18h]
0x1400eeb4f  mov     [rsp+98h+arg_0], rax
0x1400eeb57  mov     rax, [rbx+8]
0x1400eeb5b  mov     [rsp+98h+var_58], rax
0x1400eeb60  cmp     qword ptr [r14+18h], 7
0x1400eeb65  jbe     short loc_1400EEB6A
0x1400eeb67  mov     r14, [r14]
0x1400eeb6a  mov     [rsp+98h+var_50], r14
0x1400eeb6f  lea     rax, [rsp+98h+arg_0]
0x1400eeb77  mov     [rsp+98h+var_68], rax; __int64
0x1400eeb7c  lea     rax, [rsp+98h+var_58]
0x1400eeb81  mov     [rsp+98h+var_70], rax; __int64
0x1400eeb86  lea     rax, [rsp+98h+var_50]
0x1400eeb8b  mov     [rsp+98h+var_78], rax; __int64
0x1400eeb90  lea     rdx, dword_14013B9BC
0x1400eeb97  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1400eeb9c  nop
0x1400eeb9d  mov     dword ptr [rbp+8], 0
0x1400eeba4  mov     rcx, rbp; SRWLock
0x1400eeba7  call    cs:__imp_ReleaseSRWLockExclusive
0x1400eebad  nop
0x1400eebae  mov     rbx, [r15+8]
0x1400eebb2  test    rbx, rbx
0x1400eebb5  jz      short loc_1400EEBEF
0x1400eebb7  mov     eax, r13d
0x1400eebba  lock xadd [rbx+8], eax
0x1400eebbf  add     eax, r13d
0x1400eebc2  jnz     short loc_1400EEBEF
0x1400eebc4  mov     rax, [rbx]
0x1400eebc7  mov     rcx, rbx
0x1400eebca  mov     rax, [rax]
0x1400eebcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eebd2  mov     eax, r13d
0x1400eebd5  lock xadd [rbx+0Ch], eax
0x1400eebda  add     eax, r13d
0x1400eebdd  jnz     short loc_1400EEBEF
0x1400eebdf  mov     rax, [rbx]
0x1400eebe2  mov     rcx, rbx
0x1400eebe5  mov     rax, [rax+8]
0x1400eebe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eebee  nop
0x1400eebef  mov     rbx, [rsi+8]
0x1400eebf3  test    rbx, rbx
0x1400eebf6  jz      short loc_1400EEC30
0x1400eebf8  mov     eax, r13d
0x1400eebfb  lock xadd [rbx+8], eax
0x1400eec00  add     eax, r13d
0x1400eec03  jnz     short loc_1400EEC30
0x1400eec05  mov     rax, [rbx]
0x1400eec08  mov     rcx, rbx
0x1400eec0b  mov     rax, [rax]
0x1400eec0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eec13  mov     eax, r13d
0x1400eec16  lock xadd [rbx+0Ch], eax
0x1400eec1b  add     eax, r13d
0x1400eec1e  jnz     short loc_1400EEC30
0x1400eec20  mov     rax, [rbx]
0x1400eec23  mov     rcx, rbx
0x1400eec26  mov     rax, [rax+8]
0x1400eec2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400eec2f  nop
0x1400eec30  mov     rcx, r12; void *
0x1400eec33  add     rsp, 58h
0x1400eec37  pop     r15
0x1400eec39  pop     r14
0x1400eec3b  pop     r13
0x1400eec3d  pop     r12
0x1400eec3f  pop     rdi
0x1400eec40  pop     rsi
0x1400eec41  pop     rbp
0x1400eec42  pop     rbx
0x1400eec43  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400eec48  mov     rcx, [rsp+98h]; this
0x1400eec50  mov     r9d, 139Fh; char *
0x1400eec56  lea     r8, aOnecoreVmCompu_0; "onecore\\vm\\compute\\common\\transport"...
0x1400eec5d  mov     edx, 67h ; 'g'; void *
0x1400eec62  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
