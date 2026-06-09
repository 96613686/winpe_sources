# StaIfSupportedThreadPoolFactoryBase<CPickerFileType,0>::_CreateObject(IUnknown *,_GUID const &,void * *)

- ea: `0x18005a8b4`
- end: `0x18005a9c7`
- name: `?_CreateObject@?$StaIfSupportedThreadPoolFactoryBase@VCPickerFileType@@$0A@@@IEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004d270`

## callees

- `0x180003d24`
- `0x1800160c0`
- `0x180047290`
- `0x18005a8b4`
- `0x18005b2c0`
- `0x180076a7c`
- `0x180085010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18005a8f3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18005a8f3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005a96f`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005a96f`

## pseudocode

```c
__int64 __fastcall StaIfSupportedThreadPoolFactoryBase<CPickerFileType,0>::_CreateObject(
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
  v7 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_f5778cdd95a577744c4a246013152ec5_>,_lambda_f5778cdd95a577744c4a246013152ec5_>(
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
0x18005a8b4  mov     [rsp-18h+arg_0], rbx
0x18005a8b9  mov     [rsp-18h+arg_10], r8
0x18005a8be  mov     [rsp-18h+arg_8], rdx
0x18005a8c3  push    rbp
0x18005a8c4  push    rsi
0x18005a8c5  push    rdi
0x18005a8c6  mov     rbp, rsp
0x18005a8c9  sub     rsp, 50h
0x18005a8cd  mov     rsi, r9
0x18005a8d0  mov     rdi, rcx
0x18005a8d3  mov     qword ptr [r9], 0
0x18005a8da  mov     dword ptr [rbp+arg_10], 0
0x18005a8e1  lea     rdx, [rbp+arg_10]
0x18005a8e5  mov     ecx, 1
0x18005a8ea  call    ?GetCallingProcessId@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAK@Z; CallerIdentity::GetCallingProcessId(RUNTIMEBROKER_CALLERIDENTITY_CHECK,ulong *)
0x18005a8ef  test    eax, eax
0x18005a8f1  jns     short loc_18005A8FD
0x18005a8f3  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18005a8f9  mov     ebx, eax
0x18005a8fb  jmp     short loc_18005A904
0x18005a8fd  mov     ebx, dword ptr [rbp+arg_10]
0x18005a900  bts     ebx, 1Eh
0x18005a904  mov     dword ptr [rbp+arg_10], 0
0x18005a90b  mov     [rbp+arg_8], 0
0x18005a913  mov     [rbp+var_20], rdi
0x18005a917  lea     rax, [rbp+arg_8]
0x18005a91b  mov     [rbp+var_18], rax
0x18005a91f  lea     rax, [rbp+arg_10]
0x18005a923  mov     [rbp+var_10], rax
0x18005a927  lea     rdx, [rbp+var_20]
0x18005a92b  lea     rcx, [rbp+arg_18]
0x18005a92f  call    ??$Make@V?$CTaskWrapper@V_lambda_f5778cdd95a577744c4a246013152ec5_@@@ComTaskPool@Internal@Windows@@V_lambda_f5778cdd95a577744c4a246013152ec5_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_f5778cdd95a577744c4a246013152ec5_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_f5778cdd95a577744c4a246013152ec5_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_f5778cdd95a577744c4a246013152ec5_>,_lambda_f5778cdd95a577744c4a246013152ec5_>(_lambda_f5778cdd95a577744c4a246013152ec5_ &&)
0x18005a934  mov     rdi, [rax]
0x18005a937  mov     qword ptr [rax], 0
0x18005a93e  mov     rcx, [rbp+arg_18]
0x18005a942  test    rcx, rcx
0x18005a945  jz      short loc_18005A954
0x18005a947  mov     [rbp+arg_18], 0
0x18005a94f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18005a954  mov     [rsp+50h+var_28], 0
0x18005a95d  mov     [rsp+50h+var_30], rdi
0x18005a962  xor     r9d, r9d
0x18005a965  mov     r8d, ebx
0x18005a968  lea     edx, [r9+21h]
0x18005a96c  lea     ecx, [rdx-20h]
0x18005a96f  call    cs:__imp_SHTaskPoolQueueTask
0x18005a975  mov     ebx, eax
0x18005a977  test    rdi, rdi
0x18005a97a  jz      short loc_18005A98C
0x18005a97c  mov     rax, [rdi]
0x18005a97f  mov     rcx, rdi
0x18005a982  mov     rax, [rax+10h]
0x18005a986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a98b  nop
0x18005a98c  test    ebx, ebx
0x18005a98e  js      short loc_18005A9AF
0x18005a990  mov     ebx, dword ptr [rbp+arg_10]
0x18005a993  test    ebx, ebx
0x18005a995  js      short loc_18005A9AF
0x18005a997  xor     r9d, r9d; bool
0x18005a99a  mov     r8, rsi; void **
0x18005a99d  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x18005a9a4  lea     rcx, [rbp+arg_8]; this
0x18005a9a8  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x18005a9ad  mov     ebx, eax
0x18005a9af  lea     rcx, [rbp+arg_8]
0x18005a9b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a9b8  mov     eax, ebx
0x18005a9ba  mov     rbx, [rsp+50h+arg_0]
0x18005a9bf  add     rsp, 50h
0x18005a9c3  pop     rdi
0x18005a9c4  pop     rsi
0x18005a9c5  pop     rbp
0x18005a9c6  retn
```
