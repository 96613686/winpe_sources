# PipeTransport::Receive(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140298a70`
- end: `0x140298d09`
- name: `?Receive@PipeTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `665`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x140020890`
- `0x14002f9e8`
- `0x14006e5a4`
- `0x1401332f0`
- `0x140134048`
- `0x140297e64`
- `0x140298408`
- `0x14029859c`
- `0x140298898`
- `0x140298a70`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140298c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140298c9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140298c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140298c9a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140298bcf`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140298bcf`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140298c37`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140298c55`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140298c37`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140298c55`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140298bfa`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x140298bfa`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140298c74`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140298c74`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall PipeTransport::Receive(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  char v5; // si
  __int64 v6; // rax
  DWORD LastError; // ecx
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v11[6]; // [rsp+40h] [rbp-C0h] BYREF
  char v12; // [rsp+70h] [rbp-90h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+74h] [rbp-8Ch] BYREF
  int v14; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v15[336]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v15, 0, sizeof(v15));
  v4 = *a2;
  NumberOfBytesTransferred = 3;
  v9 = v4;
  v10 = a1;
  ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Start<PipeTransport *,TransportIoContext *,unsigned int,unsigned long &>(
    (unsigned int)v15,
    (unsigned int)&v10,
    (unsigned int)&v9,
    (unsigned int)&NumberOfBytesTransferred,
    v4 + 40);
  v9 = 0;
  wil::AcquireSRWLockExclusive(&v9, a1 + 32);
  v5 = 1;
  if ( (unsigned int)(*(_DWORD *)(a1 + 44) - 4) <= 1 )
  {
    PipeTransport::MapAdd(a1, a2);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v9);
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
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v9);
  }
  ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::~PipeTransport_IoStart((ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart *)v15);
  return v5;
}

```

## disassembly

```asm
0x140298a70  mov     [rsp-8+arg_10], rbx
0x140298a75  push    rbp
0x140298a76  push    rsi
0x140298a77  push    rdi
0x140298a78  lea     rbp, [rsp-0E0h]
0x140298a80  sub     rsp, 1E0h
0x140298a87  mov     rax, cs:__security_cookie
0x140298a8e  xor     rax, rsp
0x140298a91  mov     [rbp+0F0h+var_20], rax
0x140298a98  mov     rbx, rdx
0x140298a9b  mov     rdi, rcx
0x140298a9e  xor     edx, edx; Val
0x140298aa0  mov     r8d, 150h; Size
0x140298aa6  lea     rcx, [rbp+0F0h+var_170]; void *
0x140298aaa  call    memset_0
0x140298aaf  mov     rax, [rbx]
0x140298ab2  mov     [rsp+1F0h+NumberOfBytesTransferred], 3
0x140298aba  mov     [rsp+1F0h+var_1C0], rax
0x140298abf  mov     [rsp+1F0h+var_1B8], rdi
0x140298ac4  add     rax, 28h ; '('
0x140298ac8  mov     [rsp+1F0h+lpOverlapped], rax
0x140298acd  lea     r9, [rsp+1F0h+NumberOfBytesTransferred]
0x140298ad2  lea     r8, [rsp+1F0h+var_1C0]
0x140298ad7  lea     rdx, [rsp+1F0h+var_1B8]
0x140298adc  lea     rcx, [rbp+0F0h+var_170]
0x140298ae0  call    ??$Start@PEAVPipeTransport@@PEAVTransportIoContext@@IAEAK@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@SA?AV0123@$$QEAPEAVPipeTransport@@$$QEAPEAVTransportIoContext@@$$QEAIAEAK@Z; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Start<PipeTransport *,TransportIoContext *,uint,ulong &>(PipeTransport * &&,TransportIoContext * &&,uint &&,ulong &)
0x140298ae5  nop
0x140298ae6  mov     [rsp+1F0h+var_1C0], 0
0x140298aef  lea     rdx, [rdi+20h]
0x140298af3  lea     rcx, [rsp+1F0h+var_1C0]
0x140298af8  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x140298afd  nop
0x140298afe  mov     eax, [rdi+2Ch]
0x140298b01  sub     eax, 4
0x140298b04  mov     esi, 1
0x140298b09  cmp     eax, esi
0x140298b0b  jbe     short loc_140298B44
0x140298b0d  mov     rax, [rbx]
0x140298b10  mov     dword ptr [rax+30h], 139Fh
0x140298b17  mov     [rsp+1F0h+NumberOfBytesTransferred], 0
0x140298b1f  mov     rdx, [rbx]
0x140298b22  add     rdx, 30h ; '0'
0x140298b26  lea     r8, [rsp+1F0h+NumberOfBytesTransferred]
0x140298b2b  lea     rcx, [rbp+0F0h+var_170]
0x140298b2f  call    ??$Stop@AEAKH@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)
0x140298b34  nop
0x140298b35  lea     rcx, [rsp+1F0h+var_1C0]
0x140298b3a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140298b3f  jmp     loc_140298CDA
0x140298b44  mov     rdx, rbx
0x140298b47  mov     rcx, rdi
0x140298b4a  call    ?MapAdd@PipeTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; PipeTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x140298b4f  nop
0x140298b50  lea     rcx, [rsp+1F0h+var_1C0]
0x140298b55  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140298b5a  or      ecx, 0FFFFFFFFh
0x140298b5d  mov     [rsp+1F0h+var_178], ecx
0x140298b61  mov     [rsp+1F0h+var_180], sil
0x140298b66  xorps   xmm0, xmm0
0x140298b69  movups  [rsp+1F0h+var_1B0], xmm0
0x140298b6e  movups  [rsp+1F0h+var_1A0], xmm0
0x140298b73  movups  [rsp+1F0h+var_190], xmm0
0x140298b78  mov     qword ptr [rsp+1F0h+var_1B0], rdi
0x140298b7d  lea     rax, [rsp+1F0h+var_180]
0x140298b82  mov     qword ptr [rsp+1F0h+var_1B0+8], rax
0x140298b87  mov     qword ptr [rsp+1F0h+var_1A0], rbx
0x140298b8c  lea     rax, [rbp+0F0h+var_170]
0x140298b90  mov     qword ptr [rsp+1F0h+var_1A0+8], rax
0x140298b95  lea     rax, [rsp+1F0h+var_178]
0x140298b9a  mov     qword ptr [rsp+1F0h+var_190], rax
0x140298b9f  mov     word ptr [rsp+1F0h+var_190+8], 100h
0x140298ba6  mov     rax, [rbx]
0x140298ba9  mov     [rax+30h], ecx
0x140298bac  mov     rax, [rbx]
0x140298baf  movups  xmmword ptr [rax+58h], xmm0
0x140298bb3  movups  xmmword ptr [rax+68h], xmm0
0x140298bb7  mov     rax, [rbx]
0x140298bba  mov     dword ptr [rax+10h], 3
0x140298bc1  mov     rax, [rbx]
0x140298bc4  mov     dword ptr [rax+2Ch], 0
0x140298bcb  mov     rcx, [rdi+10h]; pio
0x140298bcf  call    cs:__imp_StartThreadpoolIo
0x140298bd6  nop     dword ptr [rax+rax+00h]
0x140298bdb  mov     r8, [rbx]
0x140298bde  lea     rax, [r8+58h]
0x140298be2  mov     edx, [r8+24h]
0x140298be6  add     rdx, [r8+18h]; lpBuffer
0x140298bea  mov     [rsp+1F0h+lpOverlapped], rax; lpOverlapped
0x140298bef  xor     r9d, r9d; lpNumberOfBytesRead
0x140298bf2  mov     r8d, [r8+28h]; nNumberOfBytesToRead
0x140298bf6  mov     rcx, [rdi+8]; hFile
0x140298bfa  call    cs:__imp_ReadFile
0x140298c01  nop     dword ptr [rax+rax+00h]
0x140298c06  test    eax, eax
0x140298c08  jnz     short loc_140298C49
0x140298c0a  call    cs:__imp_GetLastError
0x140298c11  nop     dword ptr [rax+rax+00h]
0x140298c16  mov     ecx, eax
0x140298c18  mov     [rsp+1F0h+var_178], eax
0x140298c1c  cmp     eax, 3E5h
0x140298c21  jnz     short loc_140298C2D
0x140298c23  mov     [rsp+1F0h+var_180], 0
0x140298c28  jmp     loc_140298CB6
0x140298c2d  mov     rax, [rbx]
0x140298c30  mov     [rax+30h], ecx
0x140298c33  mov     rcx, [rdi+10h]; pio
0x140298c37  call    cs:__imp_CancelThreadpoolIo
0x140298c3e  nop     dword ptr [rax+rax+00h]
0x140298c43  mov     ecx, [rsp+1F0h+var_178]
0x140298c47  jmp     short loc_140298CB6
0x140298c49  mov     [rsp+1F0h+NumberOfBytesTransferred], 0
0x140298c51  mov     rcx, [rdi+10h]; pio
0x140298c55  call    cs:__imp_CancelThreadpoolIo
0x140298c5c  nop     dword ptr [rax+rax+00h]
0x140298c61  mov     rdx, [rbx]
0x140298c64  add     rdx, 58h ; 'X'; lpOverlapped
0x140298c68  xor     r9d, r9d; bWait
0x140298c6b  lea     r8, [rsp+1F0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140298c70  mov     rcx, [rdi+8]; hFile
0x140298c74  call    cs:__imp_GetOverlappedResult
0x140298c7b  nop     dword ptr [rax+rax+00h]
0x140298c80  test    eax, eax
0x140298c82  jz      short loc_140298C9A
0x140298c84  mov     rax, [rbx]
0x140298c87  mov     dword ptr [rax+30h], 0
0x140298c8e  mov     rcx, [rbx]
0x140298c91  mov     eax, [rsp+1F0h+NumberOfBytesTransferred]
0x140298c95  mov     [rcx+2Ch], eax
0x140298c98  jmp     short loc_140298CAC
0x140298c9a  call    cs:__imp_GetLastError
0x140298ca1  nop     dword ptr [rax+rax+00h]
0x140298ca6  mov     rcx, [rbx]
0x140298ca9  mov     [rcx+30h], eax
0x140298cac  mov     rax, [rbx]
0x140298caf  mov     ecx, [rax+30h]
0x140298cb2  mov     [rsp+1F0h+var_178], ecx
0x140298cb6  cmp     ecx, 6Dh ; 'm'
0x140298cb9  jnz     short loc_140298CCA
0x140298cbb  mov     rax, [rdi]
0x140298cbe  mov     rcx, rdi
0x140298cc1  mov     rax, [rax+28h]
0x140298cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140298cca  mov     sil, [rsp+1F0h+var_180]
0x140298ccf  lea     rcx, [rsp+1F0h+var_1B0]
0x140298cd4  call    wil__details__ScopeExitFnGuard__lambda_b263ccb67e1715abdebcfb11bf1a72cb_____operator__
0x140298cd9  nop
0x140298cda  lea     rcx, [rbp+0F0h+var_170]; this
0x140298cde  call    ??1PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::~PipeTransport_IoStart(void)
0x140298ce3  mov     al, sil
0x140298ce6  mov     rcx, [rbp+0F0h+var_20]
0x140298ced  xor     rcx, rsp; StackCookie
0x140298cf0  call    __security_check_cookie
0x140298cf5  mov     rbx, [rsp+1F0h+arg_10]
0x140298cfd  add     rsp, 1E0h
0x140298d04  pop     rdi
0x140298d05  pop     rsi
0x140298d06  pop     rbp
0x140298d07  retn
```
