# PipeTransport::Receive(std::shared_ptr<TransportIoContext> const &)

- ea: `0x1400f4190`
- end: `0x1400f4431`
- name: `?Receive@PipeTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `673`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140005360`
- `0x140006098`
- `0x14005f06c`
- `0x14005f364`
- `0x140060364`
- `0x1400f2bf8`
- `0x1400f30c0`
- `0x1400f367c`
- `0x1400f3e98`
- `0x1400f4190`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f4280`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f42a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f4280`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f42a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f4232`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f4232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f4347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f43b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f4347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f43b3`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400f4318`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400f4318`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400f436a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400f437e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400f436a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400f437e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400f433d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400f433d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400f4397`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400f4397`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall PipeTransport::Receive(__int64 a1, __int64 *a2)
{
  __int64 v4; // rbx
  char v5; // r15
  __int64 v6; // rax
  DWORD LastError; // ecx
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v11[6]; // [rsp+40h] [rbp-C0h] BYREF
  char v12; // [rsp+70h] [rbp-90h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+74h] [rbp-8Ch] BYREF
  int v14; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v15[42]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v15, 0, sizeof(v15));
  v4 = *a2;
  NumberOfBytesTransferred = 3;
  v10 = v4;
  v9 = a1;
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "PipeTransport_IoStart");
  v15[0] = &ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::`vftable';
  ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::StartActivity<PipeTransport *,TransportIoContext *,unsigned int,unsigned long &>(
    (unsigned int)v15,
    (unsigned int)&v9,
    (unsigned int)&v10,
    (unsigned int)&NumberOfBytesTransferred,
    v4 + 40);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
  v9 = a1 + 32;
  v5 = 1;
  if ( (unsigned int)(*(_DWORD *)(a1 + 44) - 4) <= 1 )
  {
    PipeTransport::MapAdd(a1, a2);
    if ( a1 != -32 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    v14 = -1;
    v12 = 1;
    v11[5] = 256;
    v11[0] = a1;
    v11[1] = &v12;
    v11[2] = a2;
    v11[3] = v15;
    v11[4] = &v14;
    *(_DWORD *)(*a2 + 48) = -1;
    v6 = *a2;
    *(_OWORD *)(v6 + 88) = 0;
    *(_OWORD *)(v6 + 104) = 0;
    *(_DWORD *)(*a2 + 16) = 3;
    *(_DWORD *)(*a2 + 44) = 0;
    StartThreadpoolIo(*(PTP_IO *)(a1 + 16));
    if ( ReadFile(
           *(HANDLE *)(a1 + 8),
           (LPVOID)(*(_QWORD *)(*a2 + 24) + *(unsigned int *)(*a2 + 36)),
           *(_DWORD *)(*a2 + 40),
           0,
           (LPOVERLAPPED)(*a2 + 88)) )
    {
      NumberOfBytesTransferred = 0;
      CancelThreadpoolIo(*(PTP_IO *)(a1 + 16));
      if ( GetOverlappedResult(*(HANDLE *)(a1 + 8), (LPOVERLAPPED)(*a2 + 88), &NumberOfBytesTransferred, 0) )
      {
        *(_DWORD *)(*a2 + 48) = 0;
        *(_DWORD *)(*a2 + 44) = NumberOfBytesTransferred;
      }
      else
      {
        *(_DWORD *)(*a2 + 48) = GetLastError();
      }
      LastError = *(_DWORD *)(*a2 + 48);
      v14 = LastError;
    }
    else
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError == 997 )
      {
        v12 = 0;
      }
      else
      {
        *(_DWORD *)(*a2 + 48) = LastError;
        CancelThreadpoolIo(*(PTP_IO *)(a1 + 16));
        LastError = v14;
      }
    }
    if ( LastError == 109 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    v5 = v12;
    wil::details::ScopeExitFnGuard__lambda_b263ccb67e1715abdebcfb11bf1a72cb___::operator()(v11);
  }
  else
  {
    *(_DWORD *)(*a2 + 48) = 5023;
    NumberOfBytesTransferred = 0;
    ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<unsigned long &,int>(
      v15,
      *a2 + 48,
      &NumberOfBytesTransferred);
    if ( a1 != -32 )
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
  }
  v15[0] = &ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(v15);
  return v5;
}

```

## disassembly

```asm
0x1400f4190  mov     [rsp-8+arg_10], rbx
0x1400f4195  mov     [rsp-8+arg_18], rsi
0x1400f419a  push    rbp
0x1400f419b  push    rdi
0x1400f419c  push    r12
0x1400f419e  push    r14
0x1400f41a0  push    r15
0x1400f41a2  lea     rbp, [rsp-0E0h]
0x1400f41aa  sub     rsp, 1E0h
0x1400f41b1  mov     rax, cs:__security_cookie
0x1400f41b8  xor     rax, rsp
0x1400f41bb  mov     [rbp+100h+var_30], rax
0x1400f41c2  mov     rdi, rdx
0x1400f41c5  mov     rsi, rcx
0x1400f41c8  xor     edx, edx; Val
0x1400f41ca  mov     r8d, 150h; Size
0x1400f41d0  lea     rcx, [rbp+100h+var_180]; void *
0x1400f41d4  call    memset_0
0x1400f41d9  mov     rbx, [rdi]
0x1400f41dc  mov     [rsp+200h+NumberOfBytesTransferred], 3
0x1400f41e4  mov     [rsp+200h+var_1C8], rbx
0x1400f41e9  mov     [rsp+200h+var_1D0], rsi
0x1400f41ee  lea     rdx, aPipetransportI_0; "PipeTransport_IoStart"
0x1400f41f5  lea     rcx, [rbp+100h+var_180]
0x1400f41f9  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400f41fe  lea     r12, ??_7PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::`vftable'
0x1400f4205  mov     [rbp+100h+var_180], r12
0x1400f4209  lea     rax, [rbx+28h]
0x1400f420d  mov     [rsp+200h+lpOverlapped], rax
0x1400f4212  lea     r9, [rsp+200h+NumberOfBytesTransferred]
0x1400f4217  lea     r8, [rsp+200h+var_1C8]
0x1400f421c  lea     rdx, [rsp+200h+var_1D0]
0x1400f4221  lea     rcx, [rbp+100h+var_180]
0x1400f4225  call    ??$StartActivity@PEAVPipeTransport@@PEAVTransportIoContext@@IAEAK@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVPipeTransport@@$$QEAPEAVTransportIoContext@@$$QEAIAEAK@Z; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::StartActivity<PipeTransport *,TransportIoContext *,uint,ulong &>(PipeTransport * &&,TransportIoContext * &&,uint &&,ulong &)
0x1400f422a  nop
0x1400f422b  lea     r14, [rsi+20h]
0x1400f422f  mov     rcx, r14; SRWLock
0x1400f4232  call    cs:__imp_AcquireSRWLockExclusive
0x1400f4238  mov     [rsp+200h+var_1D0], r14
0x1400f423d  mov     eax, [rsi+2Ch]
0x1400f4240  sub     eax, 4
0x1400f4243  mov     r15d, 1
0x1400f4249  cmp     eax, r15d
0x1400f424c  jbe     short loc_1400F428B
0x1400f424e  mov     rax, [rdi]
0x1400f4251  mov     dword ptr [rax+30h], 139Fh
0x1400f4258  xor     ebx, ebx
0x1400f425a  mov     [rsp+200h+NumberOfBytesTransferred], ebx
0x1400f425e  mov     rdx, [rdi]
0x1400f4261  add     rdx, 30h ; '0'
0x1400f4265  lea     r8, [rsp+200h+NumberOfBytesTransferred]
0x1400f426a  lea     rcx, [rbp+100h+var_180]
0x1400f426e  call    ??$Stop@AEAKH@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)
0x1400f4273  nop
0x1400f4274  test    r14, r14
0x1400f4277  jz      loc_1400F43ED
0x1400f427d  mov     rcx, r14; SRWLock
0x1400f4280  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f4286  jmp     loc_1400F43ED
0x1400f428b  mov     rdx, rdi
0x1400f428e  mov     rcx, rsi
0x1400f4291  call    ?MapAdd@PipeTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; PipeTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x1400f4296  nop
0x1400f4297  xor     ebx, ebx
0x1400f4299  test    r14, r14
0x1400f429c  jz      short loc_1400F42A7
0x1400f429e  mov     rcx, r14; SRWLock
0x1400f42a1  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f42a7  or      ecx, 0FFFFFFFFh
0x1400f42aa  mov     [rsp+200h+var_188], ecx
0x1400f42ae  mov     [rsp+200h+var_190], r15b
0x1400f42b3  xorps   xmm0, xmm0
0x1400f42b6  movups  [rsp+200h+var_1C0], xmm0
0x1400f42bb  movups  [rsp+200h+var_1B0], xmm0
0x1400f42c0  movups  [rsp+200h+var_1A0], xmm0
0x1400f42c5  mov     qword ptr [rsp+200h+var_1C0], rsi
0x1400f42ca  lea     rax, [rsp+200h+var_190]
0x1400f42cf  mov     qword ptr [rsp+200h+var_1C0+8], rax
0x1400f42d4  mov     qword ptr [rsp+200h+var_1B0], rdi
0x1400f42d9  lea     rax, [rbp+100h+var_180]
0x1400f42dd  mov     qword ptr [rsp+200h+var_1B0+8], rax
0x1400f42e2  lea     rax, [rsp+200h+var_188]
0x1400f42e7  mov     qword ptr [rsp+200h+var_1A0], rax
0x1400f42ec  mov     word ptr [rsp+200h+var_1A0+8], 100h
0x1400f42f3  mov     rax, [rdi]
0x1400f42f6  mov     [rax+30h], ecx
0x1400f42f9  mov     rax, [rdi]
0x1400f42fc  movups  xmmword ptr [rax+58h], xmm0
0x1400f4300  movups  xmmword ptr [rax+68h], xmm0
0x1400f4304  mov     rax, [rdi]
0x1400f4307  mov     dword ptr [rax+10h], 3
0x1400f430e  mov     rax, [rdi]
0x1400f4311  mov     [rax+2Ch], ebx
0x1400f4314  mov     rcx, [rsi+10h]; pio
0x1400f4318  call    cs:__imp_StartThreadpoolIo
0x1400f431e  mov     r8, [rdi]
0x1400f4321  lea     rax, [r8+58h]
0x1400f4325  mov     edx, [r8+24h]
0x1400f4329  add     rdx, [r8+18h]; lpBuffer
0x1400f432d  mov     [rsp+200h+lpOverlapped], rax; lpOverlapped
0x1400f4332  xor     r9d, r9d; lpNumberOfBytesRead
0x1400f4335  mov     r8d, [r8+28h]; nNumberOfBytesToRead
0x1400f4339  mov     rcx, [rsi+8]; hFile
0x1400f433d  call    cs:__imp_ReadFile
0x1400f4343  test    eax, eax
0x1400f4345  jnz     short loc_1400F4376
0x1400f4347  call    cs:__imp_GetLastError
0x1400f434d  mov     ecx, eax
0x1400f434f  mov     [rsp+200h+var_188], eax
0x1400f4353  cmp     eax, 3E5h
0x1400f4358  jnz     short loc_1400F4360
0x1400f435a  mov     [rsp+200h+var_190], bl
0x1400f435e  jmp     short loc_1400F43C9
0x1400f4360  mov     rax, [rdi]
0x1400f4363  mov     [rax+30h], ecx
0x1400f4366  mov     rcx, [rsi+10h]; pio
0x1400f436a  call    cs:__imp_CancelThreadpoolIo
0x1400f4370  mov     ecx, [rsp+200h+var_188]
0x1400f4374  jmp     short loc_1400F43C9
0x1400f4376  mov     [rsp+200h+NumberOfBytesTransferred], ebx
0x1400f437a  mov     rcx, [rsi+10h]; pio
0x1400f437e  call    cs:__imp_CancelThreadpoolIo
0x1400f4384  mov     rdx, [rdi]
0x1400f4387  add     rdx, 58h ; 'X'; lpOverlapped
0x1400f438b  xor     r9d, r9d; bWait
0x1400f438e  lea     r8, [rsp+200h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400f4393  mov     rcx, [rsi+8]; hFile
0x1400f4397  call    cs:__imp_GetOverlappedResult
0x1400f439d  test    eax, eax
0x1400f439f  jz      short loc_1400F43B3
0x1400f43a1  mov     rax, [rdi]
0x1400f43a4  mov     [rax+30h], ebx
0x1400f43a7  mov     rcx, [rdi]
0x1400f43aa  mov     eax, [rsp+200h+NumberOfBytesTransferred]
0x1400f43ae  mov     [rcx+2Ch], eax
0x1400f43b1  jmp     short loc_1400F43BF
0x1400f43b3  call    cs:__imp_GetLastError
0x1400f43b9  mov     rcx, [rdi]
0x1400f43bc  mov     [rcx+30h], eax
0x1400f43bf  mov     rax, [rdi]
0x1400f43c2  mov     ecx, [rax+30h]
0x1400f43c5  mov     [rsp+200h+var_188], ecx
0x1400f43c9  cmp     ecx, 6Dh ; 'm'
0x1400f43cc  jnz     short loc_1400F43DD
0x1400f43ce  mov     rax, [rsi]
0x1400f43d1  mov     rcx, rsi
0x1400f43d4  mov     rax, [rax+28h]
0x1400f43d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f43dd  mov     r15b, [rsp+200h+var_190]
0x1400f43e2  lea     rcx, [rsp+200h+var_1C0]
0x1400f43e7  call    wil__details__ScopeExitFnGuard__lambda_b263ccb67e1715abdebcfb11bf1a72cb_____operator__
0x1400f43ec  nop
0x1400f43ed  mov     [rbp+100h+var_180], r12
0x1400f43f1  lea     rcx, [rbp+100h+var_180]
0x1400f43f5  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400f43fa  lea     rcx, [rbp+100h+var_180]
0x1400f43fe  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400f4403  mov     al, r15b
0x1400f4406  mov     rcx, [rbp+100h+var_30]
0x1400f440d  xor     rcx, rsp; StackCookie
0x1400f4410  call    __security_check_cookie
0x1400f4415  lea     r11, [rsp+200h+var_20]
0x1400f441d  mov     rbx, [r11+40h]
0x1400f4421  mov     rsi, [r11+48h]
0x1400f4425  mov     rsp, r11
0x1400f4428  pop     r15
0x1400f442a  pop     r14
0x1400f442c  pop     r12
0x1400f442e  pop     rdi
0x1400f442f  pop     rbp
0x1400f4430  retn
```
