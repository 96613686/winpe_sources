# SocketTransport::Disconnect(void)

- ea: `0x140060480`
- end: `0x140060631`
- name: `?Disconnect@SocketTransport@@UEAAXXZ`
- size: `433`
- prototype: `void __fastcall(SocketTransport *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x14005dbb0`
- `0x14005e870`
- `0x14005efac`
- `0x14005f2e4`
- `0x140060248`
- `0x140060480`
- `0x140061428`
- `0x1400623a4`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140060595`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140060595`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140060538`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400605be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140060538`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400605be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400604ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140060576`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400604ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140060576`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140060505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006057c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140060505`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14006057c`
- `WS2_32!__imp_shutdown` at `0x14006054f`
- `WS2_32!__imp_shutdown` at `0x14006054f`
- `WS2_32!__imp_WSAGetLastError` at `0x140060559`
- `WS2_32!__imp_WSAGetLastError` at `0x140060559`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SocketTransport::Disconnect(SocketTransport *this)
{
  unsigned int Error; // eax
  unsigned int v3; // r8d
  bool v5; // si
  char v6; // r14
  unsigned int v7; // [rsp+20h] [rbp-E0h] BYREF
  SocketTransport *v8; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v9[42]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  memset_0(v9, 0, sizeof(v9));
  v8 = this;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    "SocketTransport_Disconnect");
  v9[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::StartActivity<SocketTransport *>(v9, &v8);
  LOBYTE(v7) = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 25);
  *((_DWORD *)this + 52) = GetCurrentThreadId();
  if ( *((_DWORD *)this + 57) == 6 )
  {
    *((_DWORD *)this + 57) = 7;
    ++*((_DWORD *)this + 56);
    *((_DWORD *)this + 52) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
    ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::SocketTransport_DisconnectShutdown((ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect *)v9);
    if ( shutdown(*((_QWORD *)this + 15), 1) )
    {
      Error = WSAGetLastError();
      wil::details::in1diag3::Log_Win32(retaddr, (void *)0x482, v3, (const char *)Error, v7);
    }
    AcquireSRWLockExclusive((PSRWLOCK)this + 25);
    *((_DWORD *)this + 52) = GetCurrentThreadId();
    if ( (*((_DWORD *)this + 56))-- == 1 )
      WakeAllConditionVariable((PCONDITION_VARIABLE)this + 27);
  }
  v5 = 0;
  if ( *((_BYTE *)this + 109) )
  {
    v6 = *((_BYTE *)this + 110);
    *((_BYTE *)this + 110) = 1;
    v5 = v6 == 0;
    LOBYTE(v7) = v6 == 0;
  }
  *((_DWORD *)this + 52) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
  if ( v5 )
    (*(void (__fastcall **)(_QWORD, SocketTransport *))(**((_QWORD **)this + 18) + 24LL))(*((_QWORD *)this + 18), this);
  v8 = this;
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::Stop<SocketTransport *,bool &>(v9, &v8, &v7);
  v9[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v9);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(v9);
}

```

## disassembly

```asm
0x140060480  push    rbp
0x140060482  push    rbx
0x140060483  push    rsi
0x140060484  push    rdi
0x140060485  push    r12
0x140060487  push    r14
0x140060489  lea     rbp, [rsp-98h]
0x140060491  sub     rsp, 198h
0x140060498  mov     rax, cs:__security_cookie
0x14006049f  xor     rax, rsp
0x1400604a2  mov     [rbp+0C0h+var_40], rax
0x1400604a9  mov     rbx, rcx
0x1400604ac  xor     edx, edx; Val
0x1400604ae  mov     r8d, 150h; Size
0x1400604b4  lea     rcx, [rsp+1C0h+var_190]; void *
0x1400604b9  call    memset_0
0x1400604be  mov     [rsp+1C0h+var_198], rbx
0x1400604c3  lea     rdx, aSockettranspor_3; "SocketTransport_Disconnect"
0x1400604ca  lea     rcx, [rsp+1C0h+var_190]
0x1400604cf  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400604d4  lea     r12, ??_7SocketTransport_Disconnect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::`vftable'
0x1400604db  mov     [rsp+1C0h+var_190], r12
0x1400604e0  lea     rdx, [rsp+1C0h+var_198]
0x1400604e5  lea     rcx, [rsp+1C0h+var_190]
0x1400604ea  call    ??$StartActivity@PEAVSocketTransport@@@SocketTransport_Disconnect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::StartActivity<SocketTransport *>(SocketTransport * &&)
0x1400604ef  nop
0x1400604f0  mov     byte ptr [rsp+1C0h+var_1A0], 0; unsigned int
0x1400604f5  lea     rdi, [rbx+0C8h]
0x1400604fc  mov     rcx, rdi; SRWLock
0x1400604ff  call    cs:__imp_AcquireSRWLockExclusive
0x140060505  call    cs:__imp_GetCurrentThreadId
0x14006050b  mov     [rdi+8], eax
0x14006050e  mov     r14d, 1
0x140060514  cmp     dword ptr [rbx+0E4h], 6
0x14006051b  jnz     short loc_14006059B
0x14006051d  mov     dword ptr [rbx+0E4h], 7
0x140060527  add     [rbx+0E0h], r14d
0x14006052e  mov     dword ptr [rdi+8], 0
0x140060535  mov     rcx, rdi; SRWLock
0x140060538  call    cs:__imp_ReleaseSRWLockExclusive
0x14006053e  lea     rcx, [rsp+1C0h+var_190]; this
0x140060543  call    ?SocketTransport_DisconnectShutdown@SocketTransport_Disconnect@TraceProvider@Diagnostics@ComputeService@@QEAAXXZ; ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::SocketTransport_DisconnectShutdown(void)
0x140060548  mov     edx, r14d; how
0x14006054b  mov     rcx, [rbx+78h]; s
0x14006054f  call    cs:__imp_shutdown
0x140060555  test    eax, eax
0x140060557  jz      short loc_140060573
0x140060559  call    cs:__imp_WSAGetLastError
0x14006055f  mov     r9d, eax; char *
0x140060562  mov     rcx, [rbp+0C8h]; this
0x140060569  mov     edx, 482h; void *
0x14006056e  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x140060573  mov     rcx, rdi; SRWLock
0x140060576  call    cs:__imp_AcquireSRWLockExclusive
0x14006057c  call    cs:__imp_GetCurrentThreadId
0x140060582  mov     [rdi+8], eax
0x140060585  add     dword ptr [rbx+0E0h], 0FFFFFFFFh
0x14006058c  jnz     short loc_14006059B
0x14006058e  lea     rcx, [rbx+0D8h]; ConditionVariable
0x140060595  call    cs:__imp_WakeAllConditionVariable
0x14006059b  xor     sil, sil
0x14006059e  cmp     [rbx+6Dh], sil
0x1400605a2  jz      short loc_1400605B4
0x1400605a4  xchg    r14b, [rbx+6Eh]
0x1400605a8  test    r14b, r14b
0x1400605ab  setz    sil
0x1400605af  mov     byte ptr [rsp+1C0h+var_1A0], sil
0x1400605b4  mov     dword ptr [rdi+8], 0
0x1400605bb  mov     rcx, rdi; SRWLock
0x1400605be  call    cs:__imp_ReleaseSRWLockExclusive
0x1400605c4  test    sil, sil
0x1400605c7  jz      short loc_1400605DF
0x1400605c9  mov     rcx, [rbx+90h]
0x1400605d0  mov     rax, [rcx]
0x1400605d3  mov     rdx, rbx
0x1400605d6  mov     rax, [rax+18h]
0x1400605da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400605df  mov     [rsp+1C0h+var_198], rbx
0x1400605e4  lea     r8, [rsp+1C0h+var_1A0]
0x1400605e9  lea     rdx, [rsp+1C0h+var_198]
0x1400605ee  lea     rcx, [rsp+1C0h+var_190]
0x1400605f3  call    ??$Stop@PEAVSocketTransport@@AEA_N@SocketTransport_Disconnect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@AEA_N@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_Disconnect::Stop<SocketTransport *,bool &>(SocketTransport * &&,bool &)
0x1400605f8  nop
0x1400605f9  mov     [rsp+1C0h+var_190], r12
0x1400605fe  lea     rcx, [rsp+1C0h+var_190]
0x140060603  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140060608  lea     rcx, [rsp+1C0h+var_190]
0x14006060d  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140060612  mov     rcx, [rbp+0C0h+var_40]
0x140060619  xor     rcx, rsp; StackCookie
0x14006061c  call    __security_check_cookie
0x140060621  add     rsp, 198h
0x140060628  pop     r14
0x14006062a  pop     r12
0x14006062c  pop     rdi
0x14006062d  pop     rsi
0x14006062e  pop     rbx
0x14006062f  pop     rbp
0x140060630  retn
```
