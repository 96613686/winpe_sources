# SocketTransport::InternalConnect(std::shared_ptr<TransportIoContext> const &)

- ea: `0x1400c4d40`
- end: `0x1400c5175`
- name: `?InternalConnect@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `1077`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140257090`

## callees

- `0x140022ca0`
- `0x140022d94`
- `0x14004c898`
- `0x140061c3c`
- `0x14006caac`
- `0x140080180`
- `0x1400c4154`
- `0x1400c4d40`
- `0x1400e9724`
- `0x1400ec27c`
- `0x1400fe974`
- `0x1400ffe6c`
- `0x1401332f0`
- `0x140134048`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400c4e31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400c4e31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400c4fbd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1400c4fbd`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400c509d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400c509d`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400c50fe`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400c50fe`
- `WS2_32!WSASocketW` at `0x1400c4e9f`
- `WS2_32!WSASocketW` at `0x1400c4e9f`
- `WS2_32!__imp_bind` at `0x1400c4f3f`
- `WS2_32!__imp_bind` at `0x1400c4f3f`
- `WS2_32!__imp_htons` at `0x1400c506f`
- `WS2_32!__imp_htons` at `0x1400c506f`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c4f50`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c4f78`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c50e6`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c4f50`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c4f78`
- `WS2_32!__imp_WSAGetLastError` at `0x1400c50e6`

## string_xrefs

- `0x1400c4dfb`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c4f66`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c4f8e`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c4fe1`: `onecore\vm\compute\common\transport\sockettransport.cpp`
- `0x1400c5114`: `onecore\vm\compute\common\transport\sockettransport.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SocketTransport::InternalConnect(char *pv, __int64 *a2)
{
  SOCKET *v4; // r15
  int *v5; // rsi
  unsigned int v6; // r14d
  SOCKET v7; // rax
  int v8; // r8d
  unsigned int v9; // eax
  unsigned int Error; // eax
  PTP_IO *v11; // rdi
  PTP_IO ThreadpoolIo; // rax
  const char *v13; // r9
  u_short v14; // cx
  __int64 v15; // rax
  unsigned int v16; // ebx
  GROUP g; // [rsp+20h] [rbp-E0h]
  GROUP ga; // [rsp+20h] [rbp-E0h]
  char *v19; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v20[4]; // [rsp+48h] [rbp-B8h] BYREF
  char v21; // [rsp+68h] [rbp-98h] BYREF
  _QWORD name[16]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v23[42]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  memset_0(v23, 0, sizeof(v23));
  v19 = pv;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v23);
  v23[0] = &ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable';
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::StartActivity<SocketTransport *,unsigned short const (&)[8]>(
    v23,
    &v19,
    L"Connect");
  memset_0(name, 0, sizeof(name));
  Vml::VmSlimReaderWriterLock::AcquireExclusive((Vml::VmSlimReaderWriterLock *)(pv + 200));
  v19 = pv + 200;
  if ( *((_DWORD *)pv + 57) != 3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x296,
      (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
      (const char *)0x139F,
      g);
  *((_DWORD *)pv + 57) = 4;
  pv[109] = 1;
  SocketTransport::MapAdd(pv, a2);
  *((_DWORD *)pv + 52) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)pv + 25);
  v21 = 1;
  v20[3] = 256;
  v20[0] = pv;
  v20[1] = &v21;
  v20[2] = a2;
  v4 = (SOCKET *)(pv + 120);
  v5 = (int *)(pv + 100);
  v6 = 36;
  if ( *((_QWORD *)pv + 15) == -1 )
  {
    v7 = WSASocketW(*v5, 1, *((_DWORD *)pv + 26), 0, 0, 1u);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(
      pv + 120,
      v7);
    if ( *v4 == -1 )
    {
      Error = WSAGetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2C7,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)Error,
        ga);
    }
    memset_0((char *)name + 2, 0, 0x7Eu);
    if ( *v5 == 34 )
    {
      v8 = 36;
      LOWORD(name[0]) = 34;
      HIDWORD(name[0]) = 0;
      memset(&name[1], 0, 28);
    }
    else if ( *v5 == 2 )
    {
      v8 = 16;
      name[0] = 2;
    }
    else
    {
      v8 = 28;
      LODWORD(name[0]) = 23;
      *(_OWORD *)&name[1] = 0;
    }
    if ( bind(*v4, (const struct sockaddr *)name, v8) == -1 )
    {
      v9 = WSAGetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2EE,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)v9,
        ga);
    }
  }
  v11 = (PTP_IO *)(pv + 136);
  if ( !*((_QWORD *)pv + 17) )
  {
    ThreadpoolIo = CreateThreadpoolIo((HANDLE)*v4, SocketTransport::IoCompletionCallback, pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(
      pv + 136,
      ThreadpoolIo);
    if ( !*v11 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2FE,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        v13);
  }
  memset_0((char *)name + 2, 0, 0x7Eu);
  if ( *v5 == 34 )
  {
    LOWORD(name[0]) = 34;
    HIDWORD(name[0]) = *((_DWORD *)pv + 15);
    name[1] = *((_QWORD *)pv + 8);
    LODWORD(name[2]) = *((_DWORD *)pv + 18);
    *(_OWORD *)((char *)&name[2] + 4) = *(_OWORD *)(pv + 76);
  }
  else
  {
    if ( *v5 == 2 )
    {
      v6 = 16;
      LOWORD(name[0]) = 2;
      HIDWORD(name[0]) = *((_DWORD *)pv + 4);
      v14 = *((_WORD *)pv + 10);
    }
    else
    {
      v6 = 28;
      LOWORD(name[0]) = 23;
      *(_OWORD *)&name[1] = *((_OWORD *)pv + 2);
      v14 = *((_WORD *)pv + 24);
    }
    WORD1(name[0]) = htons(v14);
  }
  v15 = *a2;
  *(_OWORD *)(v15 + 88) = 0;
  *(_OWORD *)(v15 + 104) = 0;
  *(_DWORD *)(*a2 + 16) = 1;
  StartThreadpoolIo(*v11);
  if ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD))pv + 24))(*((_QWORD *)pv + 15), name, v6, 0) )
  {
    v16 = WSAGetLastError();
    if ( v16 != 997 )
    {
      CancelThreadpoolIo(*v11);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x332,
        (unsigned int)"onecore\\vm\\compute\\common\\transport\\sockettransport.cpp",
        (const char *)v16,
        0);
    }
  }
  v21 = 0;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v23);
  wil::details::ScopeExitFnGuard__lambda_44953ebd727ee55672ca284b01c7d0b0___::operator()(v20);
  ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::~SocketTransport_Connect((ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect *)v23);
}

```

## disassembly

```asm
0x1400c4d40  mov     [rsp-8+arg_10], rbx
0x1400c4d45  mov     [rsp-8+arg_18], rsi
0x1400c4d4a  push    rbp
0x1400c4d4b  push    rdi
0x1400c4d4c  push    r12
0x1400c4d4e  push    r14
0x1400c4d50  push    r15
0x1400c4d52  lea     rbp, [rsp-150h]
0x1400c4d5a  sub     rsp, 250h
0x1400c4d61  mov     rax, cs:__security_cookie
0x1400c4d68  xor     rax, rsp
0x1400c4d6b  mov     [rbp+170h+var_30], rax
0x1400c4d72  mov     r12, rdx
0x1400c4d75  mov     rbx, rcx
0x1400c4d78  xor     edx, edx; Val
0x1400c4d7a  mov     r8d, 150h; Size
0x1400c4d80  lea     rcx, [rbp+170h+var_180]; void *
0x1400c4d84  call    memset_0
0x1400c4d89  mov     [rsp+270h+var_230], rbx
0x1400c4d8e  lea     rdx, aSockettranspor; "SocketTransport_Connect"
0x1400c4d95  lea     rcx, [rbp+170h+var_180]; struct wil::details::IFailureCallback *
0x1400c4d99  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400c4d9e  lea     rax, ??_7SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::`vftable'
0x1400c4da5  mov     [rbp+170h+var_180], rax
0x1400c4da9  lea     r8, aConnect; "Connect"
0x1400c4db0  lea     rdx, [rsp+270h+var_230]
0x1400c4db5  lea     rcx, [rbp+170h+var_180]
0x1400c4db9  call    ??$StartActivity@PEAVSocketTransport@@AEAY07$$CBG@SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVSocketTransport@@AEAY07$$CBG@Z; ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::StartActivity<SocketTransport *,ushort const (&)[8]>(SocketTransport * &&,ushort const (&)[8])
0x1400c4dbe  nop
0x1400c4dbf  xor     edx, edx; Val
0x1400c4dc1  mov     r8d, 80h; Size
0x1400c4dc7  lea     rcx, [rsp+270h+name]; void *
0x1400c4dcc  call    memset_0
0x1400c4dd1  lea     rdi, [rbx+0C8h]
0x1400c4dd8  mov     rcx, rdi; this
0x1400c4ddb  call    ?AcquireExclusive@VmSlimReaderWriterLock@Vml@@QEAAXXZ; Vml::VmSlimReaderWriterLock::AcquireExclusive(void)
0x1400c4de0  mov     [rsp+270h+var_230], rdi
0x1400c4de5  cmp     dword ptr [rbx+0E4h], 3
0x1400c4dec  jz      short loc_1400C4E0D
0x1400c4dee  mov     rcx, [rbp+178h]; this
0x1400c4df5  mov     r9d, 139Fh; char *
0x1400c4dfb  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c4e02  mov     edx, 296h; void *
0x1400c4e07  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c4e0d  mov     dword ptr [rbx+0E4h], 4
0x1400c4e17  mov     byte ptr [rbx+6Dh], 1
0x1400c4e1b  mov     rdx, r12
0x1400c4e1e  mov     rcx, rbx
0x1400c4e21  call    ?MapAdd@SocketTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; SocketTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x1400c4e26  nop
0x1400c4e27  mov     dword ptr [rdi+8], 0
0x1400c4e2e  mov     rcx, rdi; SRWLock
0x1400c4e31  call    cs:__imp_ReleaseSRWLockExclusive
0x1400c4e38  nop     dword ptr [rax+rax+00h]
0x1400c4e3d  mov     [rsp+270h+var_208], 1
0x1400c4e42  xorps   xmm0, xmm0
0x1400c4e45  movups  [rsp+270h+var_228], xmm0
0x1400c4e4a  movups  [rsp+270h+var_218], xmm0
0x1400c4e4f  mov     qword ptr [rsp+270h+var_228], rbx
0x1400c4e54  lea     rax, [rsp+270h+var_208]
0x1400c4e59  mov     qword ptr [rsp+270h+var_228+8], rax
0x1400c4e5e  mov     qword ptr [rsp+270h+var_218], r12
0x1400c4e63  mov     word ptr [rsp+270h+var_218+8], 100h
0x1400c4e6a  lea     r15, [rbx+78h]
0x1400c4e6e  lea     rsi, [rbx+64h]
0x1400c4e72  mov     edi, 2
0x1400c4e77  lea     r14d, [rdi+22h]
0x1400c4e7b  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1400c4e7f  jnz     loc_1400C4FA0
0x1400c4e85  lea     eax, [rdi-1]
0x1400c4e88  mov     [rsp+270h+dwFlags], eax; dwFlags
0x1400c4e8c  mov     [rsp+270h+g], 0; unsigned int
0x1400c4e94  xor     r9d, r9d; lpProtocolInfo
0x1400c4e97  mov     r8d, [rbx+68h]; protocol
0x1400c4e9b  mov     edx, eax; type
0x1400c4e9d  mov     ecx, [rsi]; af
0x1400c4e9f  call    cs:__imp_WSASocketW
0x1400c4ea6  nop     dword ptr [rax+rax+00h]
0x1400c4eab  mov     rdx, rax
0x1400c4eae  mov     rcx, r15
0x1400c4eb1  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>::reset(unsigned __int64)
0x1400c4eb6  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1400c4eba  jz      loc_1400C4F78
0x1400c4ec0  xor     edx, edx; Val
0x1400c4ec2  lea     r8d, [rdi+7Ch]; Size
0x1400c4ec6  lea     rcx, [rsp+270h+name.sa_data]; void *
0x1400c4ecb  call    memset_0
0x1400c4ed0  lea     eax, [rdi+20h]
0x1400c4ed3  cmp     [rsi], eax
0x1400c4ed5  jnz     short loc_1400C4F0F
0x1400c4ed7  mov     r8d, r14d
0x1400c4eda  mov     [rsp+270h+name.sa_family], ax
0x1400c4edf  mov     dword ptr [rsp+270h+name.sa_data+2], 0
0x1400c4ee7  movsd   xmm0, cs:qword_14030733C
0x1400c4eef  movsd   qword ptr [rsp+270h+name.sa_data+6], xmm0
0x1400c4ef5  mov     eax, cs:dword_140307344
0x1400c4efb  mov     [rbp-80h], eax
0x1400c4efe  mov     dword ptr [rbp-7Ch], 0
0x1400c4f05  movsd   [rbp+170h+var_1E8], xmm0
0x1400c4f0a  mov     [rbp+170h+var_1E0], eax
0x1400c4f0d  jmp     short loc_1400C4F37
0x1400c4f0f  cmp     [rsi], edi
0x1400c4f11  jnz     short loc_1400C4F20
0x1400c4f13  mov     r8d, 10h
0x1400c4f19  mov     qword ptr [rsp+270h+name.sa_family], rdi
0x1400c4f1e  jmp     short loc_1400C4F37
0x1400c4f20  mov     r8d, 1Ch; namelen
0x1400c4f26  mov     dword ptr [rsp+270h+name.sa_family], 17h
0x1400c4f2e  xorps   xmm0, xmm0
0x1400c4f31  movdqu  xmmword ptr [rsp+270h+name.sa_data+6], xmm0
0x1400c4f37  lea     rdx, [rsp+270h+name]; name
0x1400c4f3c  mov     rcx, [r15]; s
0x1400c4f3f  call    cs:__imp_bind
0x1400c4f46  nop     dword ptr [rax+rax+00h]
0x1400c4f4b  cmp     eax, 0FFFFFFFFh
0x1400c4f4e  jnz     short loc_1400C4FA0
0x1400c4f50  call    cs:__imp_WSAGetLastError
0x1400c4f57  nop     dword ptr [rax+rax+00h]
0x1400c4f5c  mov     r9d, eax; char *
0x1400c4f5f  mov     rcx, [rbp+178h]; this
0x1400c4f66  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c4f6d  mov     edx, 2EEh; void *
0x1400c4f72  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c4f78  call    cs:__imp_WSAGetLastError
0x1400c4f7f  nop     dword ptr [rax+rax+00h]
0x1400c4f84  mov     r9d, eax; char *
0x1400c4f87  mov     rcx, [rbp+178h]; this
0x1400c4f8e  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c4f95  mov     edx, 2C7h; void *
0x1400c4f9a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c4fa0  lea     rdi, [rbx+88h]
0x1400c4fa7  cmp     qword ptr [rdi], 0
0x1400c4fab  jnz     short loc_1400C4FF3
0x1400c4fad  xor     r9d, r9d; pcbe
0x1400c4fb0  mov     r8, rbx; pv
0x1400c4fb3  lea     rdx, ?IoCompletionCallback@SocketTransport@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1400c4fba  mov     rcx, [r15]; fl
0x1400c4fbd  call    cs:__imp_CreateThreadpoolIo
0x1400c4fc4  nop     dword ptr [rax+rax+00h]
0x1400c4fc9  mov     rdx, rax
0x1400c4fcc  mov     rcx, rdi
0x1400c4fcf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?CloseThreadpoolIo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_IO@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&CloseThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>::reset(_TP_IO *)
0x1400c4fd4  cmp     qword ptr [rdi], 0
0x1400c4fd8  jnz     short loc_1400C4FF3
0x1400c4fda  mov     rcx, [rbp+178h]; this
0x1400c4fe1  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c4fe8  mov     edx, 2FEh; void *
0x1400c4fed  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400c4ff3  xor     edx, edx; Val
0x1400c4ff5  lea     r8d, [rdx+7Eh]; Size
0x1400c4ff9  lea     rcx, [rsp+270h+name.sa_data]; void *
0x1400c4ffe  call    memset_0
0x1400c5003  mov     eax, 22h ; '"'
0x1400c5008  cmp     [rsi], eax
0x1400c500a  jnz     short loc_1400C5034
0x1400c500c  mov     [rsp+270h+name.sa_family], ax
0x1400c5011  mov     eax, [rbx+3Ch]
0x1400c5014  mov     dword ptr [rsp+270h+name.sa_data+2], eax
0x1400c5018  movsd   xmm0, qword ptr [rbx+40h]
0x1400c501d  movsd   qword ptr [rsp+270h+name.sa_data+6], xmm0
0x1400c5023  mov     eax, [rbx+48h]
0x1400c5026  mov     [rbp-80h], eax
0x1400c5029  movups  xmm0, xmmword ptr [rbx+4Ch]
0x1400c502d  movdqu  xmmword ptr [rbp-7Ch], xmm0
0x1400c5032  jmp     short loc_1400C5080
0x1400c5034  mov     eax, 2
0x1400c5039  cmp     [rsi], eax
0x1400c503b  jnz     short loc_1400C5053
0x1400c503d  lea     r14d, [rax+0Eh]
0x1400c5041  mov     [rsp+270h+name.sa_family], ax
0x1400c5046  mov     eax, [rbx+10h]
0x1400c5049  mov     dword ptr [rsp+270h+name.sa_data+2], eax
0x1400c504d  movzx   ecx, word ptr [rbx+14h]
0x1400c5051  jmp     short loc_1400C506F
0x1400c5053  mov     eax, 17h
0x1400c5058  lea     r14d, [rax+5]
0x1400c505c  mov     [rsp+270h+name.sa_family], ax
0x1400c5061  movups  xmm0, xmmword ptr [rbx+20h]
0x1400c5065  movdqu  xmmword ptr [rsp+270h+name.sa_data+6], xmm0
0x1400c506b  movzx   ecx, word ptr [rbx+30h]; hostshort
0x1400c506f  call    cs:__imp_htons
0x1400c5076  nop     dword ptr [rax+rax+00h]
0x1400c507b  mov     word ptr [rsp+270h+name.sa_data], ax
0x1400c5080  mov     rax, [r12]
0x1400c5084  xorps   xmm0, xmm0
0x1400c5087  movups  xmmword ptr [rax+58h], xmm0
0x1400c508b  movups  xmmword ptr [rax+68h], xmm0
0x1400c508f  mov     rax, [r12]
0x1400c5093  mov     dword ptr [rax+10h], 1
0x1400c509a  mov     rcx, [rdi]; pio
0x1400c509d  call    cs:__imp_StartThreadpoolIo
0x1400c50a4  nop     dword ptr [rax+rax+00h]
0x1400c50a9  mov     rdx, [r12]
0x1400c50ad  add     rdx, 58h ; 'X'
0x1400c50b1  mov     [rsp+270h+var_240], rdx
0x1400c50b6  mov     qword ptr [rsp+270h+dwFlags], 0
0x1400c50bf  mov     [rsp+270h+g], 0; unsigned int
0x1400c50c7  xor     r9d, r9d
0x1400c50ca  mov     r8d, r14d
0x1400c50cd  lea     rdx, [rsp+270h+name]
0x1400c50d2  mov     rcx, [rbx+78h]
0x1400c50d6  mov     rax, [rbx+0C0h]
0x1400c50dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c50e2  test    eax, eax
0x1400c50e4  jnz     short loc_1400C5126
0x1400c50e6  call    cs:__imp_WSAGetLastError
0x1400c50ed  nop     dword ptr [rax+rax+00h]
0x1400c50f2  mov     ebx, eax
0x1400c50f4  cmp     eax, 3E5h
0x1400c50f9  jz      short loc_1400C5126
0x1400c50fb  mov     rcx, [rdi]; pio
0x1400c50fe  call    cs:__imp_CancelThreadpoolIo
0x1400c5105  nop     dword ptr [rax+rax+00h]
0x1400c510a  mov     rcx, [rbp+178h]; this
0x1400c5111  mov     r9d, ebx; char *
0x1400c5114  lea     r8, aOnecoreVmCompu_44; "onecore\\vm\\compute\\common\\transport"...
0x1400c511b  mov     edx, 332h; void *
0x1400c5120  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400c5126  mov     [rsp+270h+var_208], 0
0x1400c512b  lea     rcx, [rbp+170h+var_180]
0x1400c512f  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0BAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,256,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400c5134  nop
0x1400c5135  lea     rcx, [rsp+270h+var_228]
0x1400c513a  call    wil__details__ScopeExitFnGuard__lambda_44953ebd727ee55672ca284b01c7d0b0_____operator__
0x1400c513f  nop
0x1400c5140  lea     rcx, [rbp+170h+var_180]; this
0x1400c5144  call    ??1SocketTransport_Connect@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::SocketTransport_Connect::~SocketTransport_Connect(void)
0x1400c5149  mov     rcx, [rbp+170h+var_30]
0x1400c5150  xor     rcx, rsp; StackCookie
0x1400c5153  call    __security_check_cookie
0x1400c5158  lea     r11, [rsp+270h+var_20]
0x1400c5160  mov     rbx, [r11+40h]
0x1400c5164  mov     rsi, [r11+48h]
0x1400c5168  mov     rsp, r11
0x1400c516b  pop     r15
0x1400c516d  pop     r14
0x1400c516f  pop     r12
0x1400c5171  pop     rdi
0x1400c5172  pop     rbp
0x1400c5173  retn
```
