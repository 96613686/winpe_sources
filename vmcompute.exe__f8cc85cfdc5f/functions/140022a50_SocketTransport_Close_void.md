# SocketTransport::Close(void)

- ea: `0x140022a50`
- end: `0x140022c99`
- name: `?Close@SocketTransport@@UEAAXXZ`
- size: `585`
- prototype: `void __fastcall(SocketTransport *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140256e78`

## callees

- `0x140022a50`
- `0x140022ca0`
- `0x140022cd4`
- `0x140022d94`
- `0x140022e84`
- `0x140022ea4`
- `0x140061c3c`
- `0x14007fe20`
- `0x14007fea8`
- `0x1400e9750`
- `0x1400e982c`
- `0x1400e9898`
- `0x1400ec27c`
- `0x1400f92ac`
- `0x1400fe974`
- `0x1401332f0`
- `0x140134048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140022b32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140022c38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140022b32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140022c38`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x140022b85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x140022bbf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x140022b85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x140022bbf`
- `WS2_32!__imp_closesocket` at `0x140022bec`
- `WS2_32!__imp_closesocket` at `0x140022bec`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140022b63`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140022bae`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140022b63`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140022bae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SocketTransport::Close(SocketTransport *this)
{
  char v2; // si
  PTP_IO *v3; // rsi
  SOCKET v4; // rsi
  _QWORD v5[2]; // [rsp+20h] [rbp-E0h] BYREF
  void **v6; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v7[272]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v8[8]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v9[48]; // [rsp+150h] [rbp+50h] BYREF

  memset_0(&v6, 0, 0x150u);
  v5[0] = this;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v6);
  v6 = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::StartActivity<SocketTransport *>(&v6, v5);
  v2 = 0;
  Vml::VmSlimReaderWriterLock::AcquireExclusive((SocketTransport *)((char *)this + 200));
  if ( *((_DWORD *)this + 57) != 9 )
  {
    v2 = 1;
    *((_DWORD *)this + 57) = 9;
    while ( *((_DWORD *)this + 56) )
      Vml::VmConditionVariable::Sleep(
        (SocketTransport *)((char *)this + 216),
        (SocketTransport *)((char *)this + 200),
        1,
        0xFFFFFFFF);
    v5[0] = this;
    ComputeService::Diagnostics::TraceProvider::Transport_IoSummary<SocketTransport *,unsigned __int64 &,unsigned __int64 &>(
      v5,
      (char *)this + 376,
      (char *)this + 368);
  }
  *((_DWORD *)this + 52) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
  if ( v2 )
  {
    v3 = (PTP_IO *)((char *)this + 136);
    if ( *((_QWORD *)this + 15) != -1 )
    {
      if ( *v3 )
        CancelIoEx(*((HANDLE *)this + 15), 0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(
        (char *)this + 120,
        -1);
    }
    if ( *v3 )
    {
      WaitForThreadpoolIoCallbacks(*v3, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(
        (char *)this + 136,
        0);
    }
    if ( *((_QWORD *)this + 16) )
    {
      CancelIoEx(*((HANDLE *)this + 14), 0);
      WaitForThreadpoolIoCallbacks(*((PTP_IO *)this + 16), 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(
        (char *)this + 128,
        0);
    }
    v4 = *((_QWORD *)this + 14);
    if ( v4 != -1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v5);
      closesocket(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v5);
    }
    *((_QWORD *)this + 14) = -1;
    Vml::VmSlimReaderWriterLock::AcquireExclusive((SocketTransport *)((char *)this + 200));
    if ( *((_BYTE *)this + 232) )
    {
      *((_DWORD *)this + 57) = 3;
      *((_BYTE *)this + 110) = 0;
      *((_BYTE *)this + 109) = 0;
    }
    *((_DWORD *)this + 52) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 25);
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v6);
  v6 = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v6);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v9);
  wil::details::shared_object<wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ComputeService::Diagnostics::TraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(v8);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ComputeService::Diagnostics::TraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ComputeService::Diagnostics::TraceProvider,_TlgReflectorTag_Param0IsProviderType>(v7);
}

```

## disassembly

```asm
0x140022a50  push    rbp
0x140022a52  push    rbx
0x140022a53  push    rsi
0x140022a54  push    rdi
0x140022a55  push    r13
0x140022a57  push    r14
0x140022a59  lea     rbp, [rsp-98h]
0x140022a61  sub     rsp, 198h
0x140022a68  mov     rax, cs:__security_cookie
0x140022a6f  xor     rax, rsp
0x140022a72  mov     [rbp+0C0h+var_40], rax
0x140022a79  mov     rdi, rcx
0x140022a7c  xor     edx, edx; Val
0x140022a7e  mov     r8d, 150h; Size
0x140022a84  lea     rcx, [rsp+1C0h+var_190]; void *
0x140022a89  call    memset_0
0x140022a8e  mov     [rsp+1C0h+var_1A0], rdi
0x140022a93  lea     rdx, aSockettranspor_2; "SocketTransport_Close"
0x140022a9a  lea     rcx, [rsp+1C0h+var_190]; struct wil::details::IFailureCallback *
0x140022a9f  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140022aa4  lea     r13, ??_7SocketTransport_Close@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::`vftable'
0x140022aab  mov     [rsp+1C0h+var_190], r13
0x140022ab0  lea     rdx, [rsp+1C0h+var_1A0]
0x140022ab5  lea     rcx, [rsp+1C0h+var_190]
0x140022aba  call    ??$StartActivity@PEAVSocketTransport@@@SocketTransport_Close@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_Close::StartActivity<SocketTransport *>(SocketTransport * &&)
0x140022abf  nop
0x140022ac0  xor     sil, sil
0x140022ac3  lea     rbx, [rdi+0C8h]
0x140022aca  mov     rcx, rbx; this
0x140022acd  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140022ad2  cmp     dword ptr [rdi+0E4h], 9
0x140022ad9  jz      short loc_140022B28
0x140022adb  mov     esi, 1
0x140022ae0  mov     dword ptr [rdi+0E4h], 9
0x140022aea  jmp     short loc_140022B02
0x140022aec  or      r9d, 0FFFFFFFFh; unsigned int
0x140022af0  mov     r8d, esi; int
0x140022af3  mov     rdx, rbx; struct Vml::VmSlimReaderWriterLock *
0x140022af6  lea     rcx, [rdi+0D8h]; this
0x140022afd  call    ?Sleep@VmConditionVariable@Vml@@QEBAHAEAVVmSlimReaderWriterLock@2@HK@Z; Vml::VmConditionVariable::Sleep(Vml::VmSlimReaderWriterLock &,int,ulong)
0x140022b02  cmp     dword ptr [rdi+0E0h], 0
0x140022b09  ja      short loc_140022AEC
0x140022b0b  mov     [rsp+1C0h+var_1A0], rdi
0x140022b10  lea     r8, [rdi+170h]
0x140022b17  lea     rdx, [rdi+178h]
0x140022b1e  lea     rcx, [rsp+1C0h+var_1A0]
0x140022b23  call    ??$Transport_IoSummary@PEAVSocketTransport@@AEA_KAEA_K@TraceProvider@Diagnostics@ComputeService@@SAX$$QEAPEAVSocketTransport@@AEA_K1@Z; ComputeService::Diagnostics::TraceProvider::Transport_IoSummary<SocketTransport *,unsigned __int64 &,unsigned __int64 &>(SocketTransport * &&,unsigned __int64 &,unsigned __int64 &)
0x140022b28  mov     dword ptr [rbx+8], 0
0x140022b2f  mov     rcx, rbx; SRWLock
0x140022b32  call    cs:__imp_ReleaseSRWLockExclusive
0x140022b39  nop     dword ptr [rax+rax+00h]
0x140022b3e  test    sil, sil
0x140022b41  jz      loc_140022C44
0x140022b47  lea     r14, [rdi+78h]
0x140022b4b  lea     rsi, [rdi+88h]
0x140022b52  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x140022b56  jz      short loc_140022B7B
0x140022b58  cmp     qword ptr [rsi], 0
0x140022b5c  jz      short loc_140022B6F
0x140022b5e  xor     edx, edx; lpOverlapped
0x140022b60  mov     rcx, [r14]; hFile
0x140022b63  call    cs:__imp_CancelIoEx
0x140022b6a  nop     dword ptr [rax+rax+00h]
0x140022b6f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140022b73  mov     rcx, r14
0x140022b76  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(unsigned __int64)
0x140022b7b  mov     rcx, [rsi]; pio
0x140022b7e  test    rcx, rcx
0x140022b81  jz      short loc_140022B9B
0x140022b83  xor     edx, edx; fCancelPendingCallbacks
0x140022b85  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x140022b8c  nop     dword ptr [rax+rax+00h]
0x140022b91  xor     edx, edx
0x140022b93  mov     rcx, rsi
0x140022b96  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?CloseThreadpoolIo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_IO@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(_TP_IO *)
0x140022b9b  lea     rsi, [rdi+80h]
0x140022ba2  cmp     qword ptr [rsi], 0
0x140022ba6  jz      short loc_140022BD5
0x140022ba8  xor     edx, edx; lpOverlapped
0x140022baa  mov     rcx, [rdi+70h]; hFile
0x140022bae  call    cs:__imp_CancelIoEx
0x140022bb5  nop     dword ptr [rax+rax+00h]
0x140022bba  xor     edx, edx; fCancelPendingCallbacks
0x140022bbc  mov     rcx, [rsi]; pio
0x140022bbf  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x140022bc6  nop     dword ptr [rax+rax+00h]
0x140022bcb  xor     edx, edx
0x140022bcd  mov     rcx, rsi
0x140022bd0  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?CloseThreadpoolIo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_IO@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(_TP_IO *)
0x140022bd5  mov     rsi, [rdi+70h]
0x140022bd9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140022bdd  jz      short loc_140022C02
0x140022bdf  lea     rcx, [rsp+1C0h+var_1A0]; this
0x140022be4  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140022be9  mov     rcx, rsi; s
0x140022bec  call    cs:__imp_closesocket
0x140022bf3  nop     dword ptr [rax+rax+00h]
0x140022bf8  lea     rcx, [rsp+1C0h+var_1A0]; this
0x140022bfd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140022c02  mov     qword ptr [rdi+70h], 0FFFFFFFFFFFFFFFFh
0x140022c0a  mov     rcx, rbx; this
0x140022c0d  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x140022c12  cmp     byte ptr [rdi+0E8h], 0
0x140022c19  jz      short loc_140022C2E
0x140022c1b  mov     dword ptr [rdi+0E4h], 3
0x140022c25  xor     eax, eax
0x140022c27  xchg    al, [rdi+6Eh]
0x140022c2a  mov     byte ptr [rdi+6Dh], 0
0x140022c2e  mov     dword ptr [rbx+8], 0
0x140022c35  mov     rcx, rbx; SRWLock
0x140022c38  call    cs:__imp_ReleaseSRWLockExclusive
0x140022c3f  nop     dword ptr [rax+rax+00h]
0x140022c44  lea     rcx, [rsp+1C0h+var_190]
0x140022c49  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140022c4e  mov     [rsp+1C0h+var_190], r13
0x140022c53  lea     rcx, [rsp+1C0h+var_190]
0x140022c58  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140022c5d  lea     rcx, [rbp+0C0h+var_70]; this
0x140022c61  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140022c66  lea     rcx, [rbp+0C0h+var_78]
0x140022c6a  call    ?reset@?$shared_object@V?$ActivityData@VTraceProvider@Diagnostics@ComputeService@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ComputeService::Diagnostics::TraceProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x140022c6f  lea     rcx, [rsp+1C0h+var_188]
0x140022c74  call    ??1?$ActivityData@VTraceProvider@Diagnostics@ComputeService@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ComputeService::Diagnostics::TraceProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<ComputeService::Diagnostics::TraceProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x140022c79  mov     rcx, [rbp+0C0h+var_40]
0x140022c80  xor     rcx, rsp; StackCookie
0x140022c83  call    __security_check_cookie
0x140022c88  add     rsp, 198h
0x140022c8f  pop     r14
0x140022c91  pop     r13
0x140022c93  pop     rdi
0x140022c94  pop     rsi
0x140022c95  pop     rbx
0x140022c96  pop     rbp
0x140022c97  retn
```
