# PipeTransport::Send(std::shared_ptr<TransportIoContext> const &)

- ea: `0x140298d10`
- end: `0x140298fa9`
- name: `?Send@PipeTransport@@UEAA_NAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
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
- `0x140298574`
- `0x140298898`
- `0x140298d10`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140298eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140298f3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140298eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140298f3a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140298e6f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x140298e6f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140298ed7`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140298ef5`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140298ed7`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x140298ef5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140298e9a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140298e9a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140298f14`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x140298f14`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall PipeTransport::Send(__int64 a1, __int64 *a2)
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
  NumberOfBytesTransferred = 2;
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
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v9);
  }
  ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::~PipeTransport_IoStart((ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart *)v15);
  return v5;
}

```

## disassembly

```asm
0x140298d10  mov     [rsp-8+arg_10], rbx
0x140298d15  push    rbp
0x140298d16  push    rsi
0x140298d17  push    rdi
0x140298d18  lea     rbp, [rsp-0E0h]
0x140298d20  sub     rsp, 1E0h
0x140298d27  mov     rax, cs:__security_cookie
0x140298d2e  xor     rax, rsp
0x140298d31  mov     [rbp+0F0h+var_20], rax
0x140298d38  mov     rbx, rdx
0x140298d3b  mov     rdi, rcx
0x140298d3e  xor     edx, edx; Val
0x140298d40  mov     r8d, 150h; Size
0x140298d46  lea     rcx, [rbp+0F0h+var_170]; void *
0x140298d4a  call    memset_0
0x140298d4f  mov     rax, [rbx]
0x140298d52  mov     [rsp+1F0h+NumberOfBytesTransferred], 2
0x140298d5a  mov     [rsp+1F0h+var_1C0], rax
0x140298d5f  mov     [rsp+1F0h+var_1B8], rdi
0x140298d64  add     rax, 28h ; '('
0x140298d68  mov     [rsp+1F0h+lpOverlapped], rax
0x140298d6d  lea     r9, [rsp+1F0h+NumberOfBytesTransferred]
0x140298d72  lea     r8, [rsp+1F0h+var_1C0]
0x140298d77  lea     rdx, [rsp+1F0h+var_1B8]
0x140298d7c  lea     rcx, [rbp+0F0h+var_170]
0x140298d80  call    ??$Start@PEAVPipeTransport@@PEAVTransportIoContext@@IAEAK@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@SA?AV0123@$$QEAPEAVPipeTransport@@$$QEAPEAVTransportIoContext@@$$QEAIAEAK@Z; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Start<PipeTransport *,TransportIoContext *,uint,ulong &>(PipeTransport * &&,TransportIoContext * &&,uint &&,ulong &)
0x140298d85  nop
0x140298d86  mov     [rsp+1F0h+var_1C0], 0
0x140298d8f  lea     rdx, [rdi+20h]
0x140298d93  lea     rcx, [rsp+1F0h+var_1C0]
0x140298d98  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x140298d9d  nop
0x140298d9e  mov     eax, [rdi+2Ch]
0x140298da1  sub     eax, 4
0x140298da4  mov     esi, 1
0x140298da9  cmp     eax, esi
0x140298dab  jbe     short loc_140298DE4
0x140298dad  mov     rax, [rbx]
0x140298db0  mov     dword ptr [rax+30h], 139Fh
0x140298db7  mov     [rsp+1F0h+NumberOfBytesTransferred], 0
0x140298dbf  mov     rdx, [rbx]
0x140298dc2  add     rdx, 30h ; '0'
0x140298dc6  lea     r8, [rsp+1F0h+NumberOfBytesTransferred]
0x140298dcb  lea     rcx, [rbp+0F0h+var_170]
0x140298dcf  call    ??$Stop@AEAKH@PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAAXAEAK$$QEAH@Z; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::Stop<ulong &,int>(ulong &,int &&)
0x140298dd4  nop
0x140298dd5  lea     rcx, [rsp+1F0h+var_1C0]
0x140298dda  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140298ddf  jmp     loc_140298F7A
0x140298de4  mov     rdx, rbx
0x140298de7  mov     rcx, rdi
0x140298dea  call    ?MapAdd@PipeTransport@@AEAAXAEBV?$shared_ptr@VTransportIoContext@@@std@@@Z; PipeTransport::MapAdd(std::shared_ptr<TransportIoContext> const &)
0x140298def  nop
0x140298df0  lea     rcx, [rsp+1F0h+var_1C0]
0x140298df5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140298dfa  or      ecx, 0FFFFFFFFh
0x140298dfd  mov     [rsp+1F0h+var_178], ecx
0x140298e01  mov     [rsp+1F0h+var_180], sil
0x140298e06  xorps   xmm0, xmm0
0x140298e09  movups  [rsp+1F0h+var_1B0], xmm0
0x140298e0e  movups  [rsp+1F0h+var_1A0], xmm0
0x140298e13  movups  [rsp+1F0h+var_190], xmm0
0x140298e18  mov     qword ptr [rsp+1F0h+var_1B0], rdi
0x140298e1d  lea     rax, [rsp+1F0h+var_180]
0x140298e22  mov     qword ptr [rsp+1F0h+var_1B0+8], rax
0x140298e27  mov     qword ptr [rsp+1F0h+var_1A0], rbx
0x140298e2c  lea     rax, [rbp+0F0h+var_170]
0x140298e30  mov     qword ptr [rsp+1F0h+var_1A0+8], rax
0x140298e35  lea     rax, [rsp+1F0h+var_178]
0x140298e3a  mov     qword ptr [rsp+1F0h+var_190], rax
0x140298e3f  mov     word ptr [rsp+1F0h+var_190+8], 100h
0x140298e46  mov     rax, [rbx]
0x140298e49  mov     [rax+30h], ecx
0x140298e4c  mov     rax, [rbx]
0x140298e4f  movups  xmmword ptr [rax+58h], xmm0
0x140298e53  movups  xmmword ptr [rax+68h], xmm0
0x140298e57  mov     rax, [rbx]
0x140298e5a  mov     dword ptr [rax+10h], 2
0x140298e61  mov     rax, [rbx]
0x140298e64  mov     dword ptr [rax+2Ch], 0
0x140298e6b  mov     rcx, [rdi+10h]; pio
0x140298e6f  call    cs:__imp_StartThreadpoolIo
0x140298e76  nop     dword ptr [rax+rax+00h]
0x140298e7b  mov     r8, [rbx]
0x140298e7e  lea     rax, [r8+58h]
0x140298e82  mov     edx, [r8+24h]
0x140298e86  add     rdx, [r8+18h]; lpBuffer
0x140298e8a  mov     [rsp+1F0h+lpOverlapped], rax; lpOverlapped
0x140298e8f  xor     r9d, r9d; lpNumberOfBytesWritten
0x140298e92  mov     r8d, [r8+28h]; nNumberOfBytesToWrite
0x140298e96  mov     rcx, [rdi+8]; hFile
0x140298e9a  call    cs:__imp_WriteFile
0x140298ea1  nop     dword ptr [rax+rax+00h]
0x140298ea6  test    eax, eax
0x140298ea8  jnz     short loc_140298EE9
0x140298eaa  call    cs:__imp_GetLastError
0x140298eb1  nop     dword ptr [rax+rax+00h]
0x140298eb6  mov     ecx, eax
0x140298eb8  mov     [rsp+1F0h+var_178], eax
0x140298ebc  cmp     eax, 3E5h
0x140298ec1  jnz     short loc_140298ECD
0x140298ec3  mov     [rsp+1F0h+var_180], 0
0x140298ec8  jmp     loc_140298F56
0x140298ecd  mov     rax, [rbx]
0x140298ed0  mov     [rax+30h], ecx
0x140298ed3  mov     rcx, [rdi+10h]; pio
0x140298ed7  call    cs:__imp_CancelThreadpoolIo
0x140298ede  nop     dword ptr [rax+rax+00h]
0x140298ee3  mov     ecx, [rsp+1F0h+var_178]
0x140298ee7  jmp     short loc_140298F56
0x140298ee9  mov     [rsp+1F0h+NumberOfBytesTransferred], 0
0x140298ef1  mov     rcx, [rdi+10h]; pio
0x140298ef5  call    cs:__imp_CancelThreadpoolIo
0x140298efc  nop     dword ptr [rax+rax+00h]
0x140298f01  mov     rdx, [rbx]
0x140298f04  add     rdx, 58h ; 'X'; lpOverlapped
0x140298f08  xor     r9d, r9d; bWait
0x140298f0b  lea     r8, [rsp+1F0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140298f10  mov     rcx, [rdi+8]; hFile
0x140298f14  call    cs:__imp_GetOverlappedResult
0x140298f1b  nop     dword ptr [rax+rax+00h]
0x140298f20  test    eax, eax
0x140298f22  jz      short loc_140298F3A
0x140298f24  mov     rax, [rbx]
0x140298f27  mov     dword ptr [rax+30h], 0
0x140298f2e  mov     rcx, [rbx]
0x140298f31  mov     eax, [rsp+1F0h+NumberOfBytesTransferred]
0x140298f35  mov     [rcx+2Ch], eax
0x140298f38  jmp     short loc_140298F4C
0x140298f3a  call    cs:__imp_GetLastError
0x140298f41  nop     dword ptr [rax+rax+00h]
0x140298f46  mov     rcx, [rbx]
0x140298f49  mov     [rcx+30h], eax
0x140298f4c  mov     rax, [rbx]
0x140298f4f  mov     ecx, [rax+30h]
0x140298f52  mov     [rsp+1F0h+var_178], ecx
0x140298f56  cmp     ecx, 6Dh ; 'm'
0x140298f59  jnz     short loc_140298F6A
0x140298f5b  mov     rax, [rdi]
0x140298f5e  mov     rcx, rdi
0x140298f61  mov     rax, [rax+28h]
0x140298f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140298f6a  mov     sil, [rsp+1F0h+var_180]
0x140298f6f  lea     rcx, [rsp+1F0h+var_1B0]
0x140298f74  call    wil__details__ScopeExitFnGuard__lambda_54abbe46d0aa2fa479494c59264baf06_____operator__
0x140298f79  nop
0x140298f7a  lea     rcx, [rbp+0F0h+var_170]; this
0x140298f7e  call    ??1PipeTransport_IoStart@TraceProvider@Diagnostics@ComputeService@@QEAA@XZ; ComputeService::Diagnostics::TraceProvider::PipeTransport_IoStart::~PipeTransport_IoStart(void)
0x140298f83  mov     al, sil
0x140298f86  mov     rcx, [rbp+0F0h+var_20]
0x140298f8d  xor     rcx, rsp; StackCookie
0x140298f90  call    __security_check_cookie
0x140298f95  mov     rbx, [rsp+1F0h+arg_10]
0x140298f9d  add     rsp, 1E0h
0x140298fa4  pop     rdi
0x140298fa5  pop     rsi
0x140298fa6  pop     rbp
0x140298fa7  retn
```
