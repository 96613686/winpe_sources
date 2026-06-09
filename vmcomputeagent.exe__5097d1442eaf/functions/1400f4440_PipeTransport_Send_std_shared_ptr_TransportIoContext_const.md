# PipeTransport::Send(std::shared_ptr<TransportIoContext> const &)

- ea: `0x1400f4440`
- end: `0x1400f46e1`
- name: `?Send@PipeTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
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
- `0x1400f35c8`
- `0x1400f3e98`
- `0x1400f4440`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f4530`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f4551`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f4530`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f4551`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f44e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f44e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f45f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f4663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f45f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400f4663`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400f45c8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1400f45c8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400f461a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400f462e`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400f461a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1400f462e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400f45ed`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400f45ed`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400f4647`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1400f4647`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall PipeTransport::Send(__int64 a1, __int64 *a2)
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
  NumberOfBytesTransferred = 2;
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
    *(_DWORD *)(*a2 + 16) = 2;
    *(_DWORD *)(*a2 + 44) = 0;
    StartThreadpoolIo(*(PTP_IO *)(a1 + 16));
    if ( WriteFile(
           *(HANDLE *)(a1 + 8),
           (LPCVOID)(*(_QWORD *)(*a2 + 24) + *(unsigned int *)(*a2 + 36)),
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
    wil::details::ScopeExitFnGuard__lambda_54abbe46d0aa2fa479494c59264baf06___::operator()(v11);
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
0x1400f4440  mov     [rsp-8+arg_10], rbx
0x1400f4445  mov     [rsp-8+arg_18], rsi
0x1400f444a  push    rbp
0x1400f444b  push    rdi
0x1400f444c  push    r12
0x1400f444e  push    r14
0x1400f4450  push    r15
0x1400f4452  lea     rbp, [rsp-0E0h]
0x1400f445a  sub     rsp, 1E0h
0x1400f4461  mov     rax, cs:__security_cookie
0x1400f4468  xor     rax, rsp
0x1400f446b  mov     [rbp+100h+var_30], rax
0x1400f4472  mov     rdi, rdx
0x1400f4475  mov     rsi, rcx
0x1400f4478  xor     edx, edx; Val
0x1400f447a  mov     r8d, 150h; Size
0x1400f4480  lea     rcx, [rbp+100h+var_180]; void *
0x1400f4484  call    memset_0
0x1400f4489  mov     rbx, [rdi]
0x1400f448c  mov     [rsp+200h+NumberOfBytesTransferred], 2
0x1400f4494  mov     [rsp+200h+var_1C8], rbx
0x1400f4499  mov     [rsp+200h+var_1D0], rsi
0x1400f449e  lea     rdx, aPipetransportI_0; "PipeTransport_IoStart"
0x1400f44a5  lea     rcx, [rbp+100h+var_180]
0x1400f44a9  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400f44ae  lea     r12, ??_7PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::`vftable'
0x1400f44b5  mov     [rbp+100h+var_180], r12
0x1400f44b9  lea     rax, [rbx+28h]
0x1400f44bd  mov     [rsp+200h+lpOverlapped], rax
0x1400f44c2  lea     r9, [rsp+200h+NumberOfBytesTransferred]
0x1400f44c7  lea     r8, [rsp+200h+var_1C8]
0x1400f44cc  lea     rdx, [rsp+200h+var_1D0]
0x1400f44d1  lea     rcx, [rbp+100h+var_180]
0x1400f44d5  call    ??$StartActivity@PEAVPipeTransport@@PEAVTransportIoContext@@IAEAK@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEAVPipeTransport@@$$QEAPEAVTransportIoContext@@$$QEAIAEAK@Z; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::StartActivity<PipeTransport *,TransportIoContext *,uint,ulong &>(PipeTransport * &&,TransportIoContext * &&,uint &&,ulong &)
0x1400f44da  nop
0x1400f44db  lea     r14, [rsi+20h]
0x1400f44df  mov     rcx, r14; SRWLock
0x1400f44e2  call    cs:__imp_AcquireSRWLockExclusive
0x1400f44e8  mov     [rsp+200h+var_1D0], r14
0x1400f44ed  mov     eax, [rsi+2Ch]
0x1400f44f0  sub     eax, 4
0x1400f44f3  mov     r15d, 1
0x1400f44f9  cmp     eax, r15d
0x1400f44fc  jbe     short loc_1400F453B
0x1400f44fe  mov     rax, [rdi]
0x1400f4501  mov     dword ptr [rax+30h], 139Fh
0x1400f4508  xor     ebx, ebx
0x1400f450a  mov     [rsp+200h+NumberOfBytesTransferred], ebx
0x1400f450e  mov     rdx, [rdi]
0x1400f4511  add     rdx, 30h ; '0'
0x1400f4515  lea     r8, [rsp+200h+NumberOfBytesTransferred]
0x1400f451a  lea     rcx, [rbp+100h+var_180]
0x1400f451e  call    ??$Stop@AEAKH@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)
0x1400f4523  nop
0x1400f4524  test    r14, r14
0x1400f4527  jz      loc_1400F469D
0x1400f452d  mov     rcx, r14; SRWLock
0x1400f4530  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f4536  jmp     loc_1400F469D
0x1400f453b  mov     rdx, rdi
0x1400f453e  mov     rcx, rsi
0x1400f4541  call    ?MapAdd@PipeTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; PipeTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x1400f4546  nop
0x1400f4547  xor     ebx, ebx
0x1400f4549  test    r14, r14
0x1400f454c  jz      short loc_1400F4557
0x1400f454e  mov     rcx, r14; SRWLock
0x1400f4551  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f4557  or      ecx, 0FFFFFFFFh
0x1400f455a  mov     [rsp+200h+var_188], ecx
0x1400f455e  mov     [rsp+200h+var_190], r15b
0x1400f4563  xorps   xmm0, xmm0
0x1400f4566  movups  [rsp+200h+var_1C0], xmm0
0x1400f456b  movups  [rsp+200h+var_1B0], xmm0
0x1400f4570  movups  [rsp+200h+var_1A0], xmm0
0x1400f4575  mov     qword ptr [rsp+200h+var_1C0], rsi
0x1400f457a  lea     rax, [rsp+200h+var_190]
0x1400f457f  mov     qword ptr [rsp+200h+var_1C0+8], rax
0x1400f4584  mov     qword ptr [rsp+200h+var_1B0], rdi
0x1400f4589  lea     rax, [rbp+100h+var_180]
0x1400f458d  mov     qword ptr [rsp+200h+var_1B0+8], rax
0x1400f4592  lea     rax, [rsp+200h+var_188]
0x1400f4597  mov     qword ptr [rsp+200h+var_1A0], rax
0x1400f459c  mov     word ptr [rsp+200h+var_1A0+8], 100h
0x1400f45a3  mov     rax, [rdi]
0x1400f45a6  mov     [rax+30h], ecx
0x1400f45a9  mov     rax, [rdi]
0x1400f45ac  movups  xmmword ptr [rax+58h], xmm0
0x1400f45b0  movups  xmmword ptr [rax+68h], xmm0
0x1400f45b4  mov     rax, [rdi]
0x1400f45b7  mov     dword ptr [rax+10h], 2
0x1400f45be  mov     rax, [rdi]
0x1400f45c1  mov     [rax+2Ch], ebx
0x1400f45c4  mov     rcx, [rsi+10h]; pio
0x1400f45c8  call    cs:__imp_StartThreadpoolIo
0x1400f45ce  mov     r8, [rdi]
0x1400f45d1  lea     rax, [r8+58h]
0x1400f45d5  mov     edx, [r8+24h]
0x1400f45d9  add     rdx, [r8+18h]; lpBuffer
0x1400f45dd  mov     [rsp+200h+lpOverlapped], rax; lpOverlapped
0x1400f45e2  xor     r9d, r9d; lpNumberOfBytesWritten
0x1400f45e5  mov     r8d, [r8+28h]; nNumberOfBytesToWrite
0x1400f45e9  mov     rcx, [rsi+8]; hFile
0x1400f45ed  call    cs:__imp_WriteFile
0x1400f45f3  test    eax, eax
0x1400f45f5  jnz     short loc_1400F4626
0x1400f45f7  call    cs:__imp_GetLastError
0x1400f45fd  mov     ecx, eax
0x1400f45ff  mov     [rsp+200h+var_188], eax
0x1400f4603  cmp     eax, 3E5h
0x1400f4608  jnz     short loc_1400F4610
0x1400f460a  mov     [rsp+200h+var_190], bl
0x1400f460e  jmp     short loc_1400F4679
0x1400f4610  mov     rax, [rdi]
0x1400f4613  mov     [rax+30h], ecx
0x1400f4616  mov     rcx, [rsi+10h]; pio
0x1400f461a  call    cs:__imp_CancelThreadpoolIo
0x1400f4620  mov     ecx, [rsp+200h+var_188]
0x1400f4624  jmp     short loc_1400F4679
0x1400f4626  mov     [rsp+200h+NumberOfBytesTransferred], ebx
0x1400f462a  mov     rcx, [rsi+10h]; pio
0x1400f462e  call    cs:__imp_CancelThreadpoolIo
0x1400f4634  mov     rdx, [rdi]
0x1400f4637  add     rdx, 58h ; 'X'; lpOverlapped
0x1400f463b  xor     r9d, r9d; bWait
0x1400f463e  lea     r8, [rsp+200h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400f4643  mov     rcx, [rsi+8]; hFile
0x1400f4647  call    cs:__imp_GetOverlappedResult
0x1400f464d  test    eax, eax
0x1400f464f  jz      short loc_1400F4663
0x1400f4651  mov     rax, [rdi]
0x1400f4654  mov     [rax+30h], ebx
0x1400f4657  mov     rcx, [rdi]
0x1400f465a  mov     eax, [rsp+200h+NumberOfBytesTransferred]
0x1400f465e  mov     [rcx+2Ch], eax
0x1400f4661  jmp     short loc_1400F466F
0x1400f4663  call    cs:__imp_GetLastError
0x1400f4669  mov     rcx, [rdi]
0x1400f466c  mov     [rcx+30h], eax
0x1400f466f  mov     rax, [rdi]
0x1400f4672  mov     ecx, [rax+30h]
0x1400f4675  mov     [rsp+200h+var_188], ecx
0x1400f4679  cmp     ecx, 6Dh ; 'm'
0x1400f467c  jnz     short loc_1400F468D
0x1400f467e  mov     rax, [rsi]
0x1400f4681  mov     rcx, rsi
0x1400f4684  mov     rax, [rax+28h]
0x1400f4688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f468d  mov     r15b, [rsp+200h+var_190]
0x1400f4692  lea     rcx, [rsp+200h+var_1C0]
0x1400f4697  call    wil__details__ScopeExitFnGuard__lambda_54abbe46d0aa2fa479494c59264baf06_____operator__
0x1400f469c  nop
0x1400f469d  mov     [rbp+100h+var_180], r12
0x1400f46a1  lea     rcx, [rbp+100h+var_180]
0x1400f46a5  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400f46aa  lea     rcx, [rbp+100h+var_180]
0x1400f46ae  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0CAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,512,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400f46b3  mov     al, r15b
0x1400f46b6  mov     rcx, [rbp+100h+var_30]
0x1400f46bd  xor     rcx, rsp; StackCookie
0x1400f46c0  call    __security_check_cookie
0x1400f46c5  lea     r11, [rsp+200h+var_20]
0x1400f46cd  mov     rbx, [r11+40h]
0x1400f46d1  mov     rsi, [r11+48h]
0x1400f46d5  mov     rsp, r11
0x1400f46d8  pop     r15
0x1400f46da  pop     r14
0x1400f46dc  pop     r12
0x1400f46de  pop     rdi
0x1400f46df  pop     rbp
0x1400f46e0  retn
```
