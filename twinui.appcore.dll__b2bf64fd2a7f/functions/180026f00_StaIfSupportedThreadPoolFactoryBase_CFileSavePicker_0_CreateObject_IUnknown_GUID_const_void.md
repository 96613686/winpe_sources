# StaIfSupportedThreadPoolFactoryBase<CFileSavePicker,0>::_CreateObject(IUnknown *,_GUID const &,void * *)

- ea: `0x180026f00`
- end: `0x18002702f`
- name: `?_CreateObject@?$StaIfSupportedThreadPoolFactoryBase@VCFileSavePicker@@$0A@@@IEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004d230`

## callees

- `0x180003d24`
- `0x1800181f4`
- `0x1800231c8`
- `0x180026f00`
- `0x18002b1e0`
- `0x18005b2c0`
- `0x180076a7c`
- `0x180085010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x180026f43`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x180026f43`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180026fd3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180026fd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StaIfSupportedThreadPoolFactoryBase<CFileSavePicker,0>::_CreateObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void **a4)
{
  unsigned int UniqueContext; // edi
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // rsi
  int v10; // ebx
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF
  int v13; // [rsp+70h] [rbp+40h] BYREF
  int v14; // [rsp+74h] [rbp+44h]
  _QWORD *v15; // [rsp+78h] [rbp+48h] BYREF

  v14 = HIDWORD(a3);
  v12 = a2;
  *a4 = 0;
  v13 = 0;
  if ( (int)CallerIdentity::GetCallingProcessId(1, &v13) >= 0 )
    UniqueContext = v13 | 0x40000000;
  else
    UniqueContext = SHTaskPoolGetUniqueContext();
  v13 = 0;
  v12 = 0;
  v7 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  v15 = v7;
  v9 = 0;
  if ( v7 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(v7);
    v8[2] = a1;
    v8[3] = &v12;
    v8[4] = &v13;
    *v8 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_cb828247e85a469110af8700874a29c4_>::`vftable';
    v15 = 0;
    v9 = v8;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v15);
  v10 = SHTaskPoolQueueTask(1, 33, UniqueContext);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
  if ( v10 >= 0 )
  {
    v10 = v13;
    if ( v13 >= 0 )
      v10 = CMarshaledInterface::_Unmarshal(
              (CMarshaledInterface *)&v12,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              a4,
              0);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180026f00  mov     [rsp-28h+arg_0], rbx
0x180026f05  mov     [rsp-28h+arg_10], r8
0x180026f0a  mov     [rsp-28h+arg_8], rdx
0x180026f0f  push    rbp
0x180026f10  push    rsi
0x180026f11  push    rdi
0x180026f12  push    r14
0x180026f14  push    r15
0x180026f16  mov     rbp, rsp
0x180026f19  sub     rsp, 30h
0x180026f1d  mov     r14, r9
0x180026f20  mov     r15, rcx
0x180026f23  mov     qword ptr [r9], 0
0x180026f2a  mov     dword ptr [rbp+arg_10], 0
0x180026f31  lea     rdx, [rbp+arg_10]
0x180026f35  mov     ecx, 1
0x180026f3a  call    ?GetCallingProcessId@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAK@Z; CallerIdentity::GetCallingProcessId(RUNTIMEBROKER_CALLERIDENTITY_CHECK,ulong *)
0x180026f3f  test    eax, eax
0x180026f41  jns     short loc_180026F4D
0x180026f43  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180026f49  mov     edi, eax
0x180026f4b  jmp     short loc_180026F54
0x180026f4d  mov     edi, dword ptr [rbp+arg_10]
0x180026f50  bts     edi, 1Eh
0x180026f54  mov     dword ptr [rbp+arg_10], 0
0x180026f5b  mov     [rbp+arg_8], 0
0x180026f63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026f6a  mov     ecx, 28h ; '('; unsigned __int64
0x180026f6f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026f74  mov     rbx, rax
0x180026f77  mov     [rbp+arg_18], rax
0x180026f7b  xor     esi, esi
0x180026f7d  test    rax, rax
0x180026f80  jz      short loc_180026FAF
0x180026f82  mov     rcx, rax
0x180026f85  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>(void)
0x180026f8a  mov     [rbx+10h], r15
0x180026f8e  lea     rax, [rbp+arg_8]
0x180026f92  mov     [rbx+18h], rax
0x180026f96  lea     rax, [rbp+arg_10]
0x180026f9a  mov     [rbx+20h], rax
0x180026f9e  lea     rax, ??_7?$CTaskWrapper@V_lambda_cb828247e85a469110af8700874a29c4_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_cb828247e85a469110af8700874a29c4_>::`vftable'
0x180026fa5  mov     [rbx], rax
0x180026fa8  mov     [rbp+arg_18], rsi
0x180026fac  mov     rsi, rbx
0x180026faf  lea     rcx, [rbp+arg_18]
0x180026fb3  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x180026fb8  mov     [rsp+30h+var_8], 0
0x180026fc1  mov     [rsp+30h+var_10], rsi
0x180026fc6  xor     r9d, r9d
0x180026fc9  mov     r8d, edi
0x180026fcc  lea     edx, [r9+21h]
0x180026fd0  lea     ecx, [rdx-20h]
0x180026fd3  call    cs:__imp_SHTaskPoolQueueTask
0x180026fd9  mov     ebx, eax
0x180026fdb  test    rsi, rsi
0x180026fde  jz      short loc_180026FF0
0x180026fe0  mov     rax, [rsi]
0x180026fe3  mov     rcx, rsi
0x180026fe6  mov     rax, [rax+10h]
0x180026fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026fef  nop
0x180026ff0  test    ebx, ebx
0x180026ff2  js      short loc_180027013
0x180026ff4  mov     ebx, dword ptr [rbp+arg_10]
0x180026ff7  test    ebx, ebx
0x180026ff9  js      short loc_180027013
0x180026ffb  xor     r9d, r9d; bool
0x180026ffe  mov     r8, r14; void **
0x180027001  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x180027008  lea     rcx, [rbp+arg_8]; this
0x18002700c  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x180027011  mov     ebx, eax
0x180027013  lea     rcx, [rbp+arg_8]
0x180027017  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002701c  mov     eax, ebx
0x18002701e  mov     rbx, [rsp+30h+arg_0]
0x180027023  add     rsp, 30h
0x180027027  pop     r15
0x180027029  pop     r14
0x18002702b  pop     rdi
0x18002702c  pop     rsi
0x18002702d  pop     rbp
0x18002702e  retn
```
