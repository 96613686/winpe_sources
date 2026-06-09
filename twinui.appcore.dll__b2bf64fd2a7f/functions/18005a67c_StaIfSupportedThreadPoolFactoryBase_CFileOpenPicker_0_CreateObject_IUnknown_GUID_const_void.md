# StaIfSupportedThreadPoolFactoryBase<CFileOpenPicker,0>::_CreateObject(IUnknown *,_GUID const &,void * *)

- ea: `0x18005a67c`
- end: `0x18005a78f`
- name: `?_CreateObject@?$StaIfSupportedThreadPoolFactoryBase@VCFileOpenPicker@@$0A@@@IEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004d210`

## callees

- `0x180003d24`
- `0x1800160c0`
- `0x18004732c`
- `0x18005a67c`
- `0x18005b2c0`
- `0x180076a7c`
- `0x180085010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18005a6bb`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18005a6bb`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005a737`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005a737`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StaIfSupportedThreadPoolFactoryBase<CFileOpenPicker,0>::_CreateObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void **a4)
{
  unsigned int UniqueContext; // ebx
  __int64 *v7; // rax
  __int64 v8; // rdi
  int v9; // ebx
  _QWORD v11[4]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+78h] [rbp+28h] BYREF
  int v13; // [rsp+80h] [rbp+30h] BYREF
  int v14; // [rsp+84h] [rbp+34h]
  __int64 v15; // [rsp+88h] [rbp+38h] BYREF

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
  v11[0] = a1;
  v11[1] = &v12;
  v11[2] = &v13;
  v7 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_fa06935ef5a971a14a2aa459c2f68b8e_>,_lambda_fa06935ef5a971a14a2aa459c2f68b8e_>(
                    &v15,
                    v11);
  v8 = *v7;
  *v7 = 0;
  if ( v15 )
  {
    v15 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  v9 = SHTaskPoolQueueTask(1, 33, UniqueContext);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9 >= 0 )
  {
    v9 = v13;
    if ( v13 >= 0 )
      v9 = CMarshaledInterface::_Unmarshal(
             (CMarshaledInterface *)&v12,
             &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
             a4,
             0);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005a67c  mov     [rsp-18h+arg_0], rbx
0x18005a681  mov     [rsp-18h+arg_10], r8
0x18005a686  mov     [rsp-18h+arg_8], rdx
0x18005a68b  push    rbp
0x18005a68c  push    rsi
0x18005a68d  push    rdi
0x18005a68e  mov     rbp, rsp
0x18005a691  sub     rsp, 50h
0x18005a695  mov     rsi, r9
0x18005a698  mov     rdi, rcx
0x18005a69b  mov     qword ptr [r9], 0
0x18005a6a2  mov     dword ptr [rbp+arg_10], 0
0x18005a6a9  lea     rdx, [rbp+arg_10]
0x18005a6ad  mov     ecx, 1
0x18005a6b2  call    ?GetCallingProcessId@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAK@Z; CallerIdentity::GetCallingProcessId(RUNTIMEBROKER_CALLERIDENTITY_CHECK,ulong *)
0x18005a6b7  test    eax, eax
0x18005a6b9  jns     short loc_18005A6C5
0x18005a6bb  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18005a6c1  mov     ebx, eax
0x18005a6c3  jmp     short loc_18005A6CC
0x18005a6c5  mov     ebx, dword ptr [rbp+arg_10]
0x18005a6c8  bts     ebx, 1Eh
0x18005a6cc  mov     dword ptr [rbp+arg_10], 0
0x18005a6d3  mov     [rbp+arg_8], 0
0x18005a6db  mov     [rbp+var_20], rdi
0x18005a6df  lea     rax, [rbp+arg_8]
0x18005a6e3  mov     [rbp+var_18], rax
0x18005a6e7  lea     rax, [rbp+arg_10]
0x18005a6eb  mov     [rbp+var_10], rax
0x18005a6ef  lea     rdx, [rbp+var_20]
0x18005a6f3  lea     rcx, [rbp+arg_18]
0x18005a6f7  call    ??$Make@V?$CTaskWrapper@V_lambda_fa06935ef5a971a14a2aa459c2f68b8e_@@@ComTaskPool@Internal@Windows@@V_lambda_fa06935ef5a971a14a2aa459c2f68b8e_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_fa06935ef5a971a14a2aa459c2f68b8e_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_fa06935ef5a971a14a2aa459c2f68b8e_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_fa06935ef5a971a14a2aa459c2f68b8e_>,_lambda_fa06935ef5a971a14a2aa459c2f68b8e_>(_lambda_fa06935ef5a971a14a2aa459c2f68b8e_ &&)
0x18005a6fc  mov     rdi, [rax]
0x18005a6ff  mov     qword ptr [rax], 0
0x18005a706  mov     rcx, [rbp+arg_18]
0x18005a70a  test    rcx, rcx
0x18005a70d  jz      short loc_18005A71C
0x18005a70f  mov     [rbp+arg_18], 0
0x18005a717  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18005a71c  mov     [rsp+50h+var_28], 0
0x18005a725  mov     [rsp+50h+var_30], rdi
0x18005a72a  xor     r9d, r9d
0x18005a72d  mov     r8d, ebx
0x18005a730  lea     edx, [r9+21h]
0x18005a734  lea     ecx, [rdx-20h]
0x18005a737  call    cs:__imp_SHTaskPoolQueueTask
0x18005a73d  mov     ebx, eax
0x18005a73f  test    rdi, rdi
0x18005a742  jz      short loc_18005A754
0x18005a744  mov     rax, [rdi]
0x18005a747  mov     rcx, rdi
0x18005a74a  mov     rax, [rax+10h]
0x18005a74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a753  nop
0x18005a754  test    ebx, ebx
0x18005a756  js      short loc_18005A777
0x18005a758  mov     ebx, dword ptr [rbp+arg_10]
0x18005a75b  test    ebx, ebx
0x18005a75d  js      short loc_18005A777
0x18005a75f  xor     r9d, r9d; bool
0x18005a762  mov     r8, rsi; void **
0x18005a765  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x18005a76c  lea     rcx, [rbp+arg_8]; this
0x18005a770  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x18005a775  mov     ebx, eax
0x18005a777  lea     rcx, [rbp+arg_8]
0x18005a77b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a780  mov     eax, ebx
0x18005a782  mov     rbx, [rsp+50h+arg_0]
0x18005a787  add     rsp, 50h
0x18005a78b  pop     rdi
0x18005a78c  pop     rsi
0x18005a78d  pop     rbp
0x18005a78e  retn
```
