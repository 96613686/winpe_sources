# StaIfSupportedThreadPoolFactoryBase<CFolderPicker,0>::_CreateObject(IUnknown *,_GUID const &,void * *)

- ea: `0x18005a798`
- end: `0x18005a8ab`
- name: `?_CreateObject@?$StaIfSupportedThreadPoolFactoryBase@VCFolderPicker@@$0A@@@IEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004d250`

## callees

- `0x180003d24`
- `0x1800160c0`
- `0x18004714c`
- `0x18005a798`
- `0x18005b2c0`
- `0x180076a7c`
- `0x180085010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18005a7d7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18005a7d7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005a853`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18005a853`

## pseudocode

```c
__int64 __fastcall StaIfSupportedThreadPoolFactoryBase<CFolderPicker,0>::_CreateObject(
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
  v7 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1390acf51d11074e2a586070f25dbf13_>,_lambda_1390acf51d11074e2a586070f25dbf13_>(
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
0x18005a798  mov     [rsp-18h+arg_0], rbx
0x18005a79d  mov     [rsp-18h+arg_10], r8
0x18005a7a2  mov     [rsp-18h+arg_8], rdx
0x18005a7a7  push    rbp
0x18005a7a8  push    rsi
0x18005a7a9  push    rdi
0x18005a7aa  mov     rbp, rsp
0x18005a7ad  sub     rsp, 50h
0x18005a7b1  mov     rsi, r9
0x18005a7b4  mov     rdi, rcx
0x18005a7b7  mov     qword ptr [r9], 0
0x18005a7be  mov     dword ptr [rbp+arg_10], 0
0x18005a7c5  lea     rdx, [rbp+arg_10]
0x18005a7c9  mov     ecx, 1
0x18005a7ce  call    ?GetCallingProcessId@CallerIdentity@@YAJW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAK@Z; CallerIdentity::GetCallingProcessId(RUNTIMEBROKER_CALLERIDENTITY_CHECK,ulong *)
0x18005a7d3  test    eax, eax
0x18005a7d5  jns     short loc_18005A7E1
0x18005a7d7  call    cs:__imp_SHTaskPoolGetUniqueContext
0x18005a7dd  mov     ebx, eax
0x18005a7df  jmp     short loc_18005A7E8
0x18005a7e1  mov     ebx, dword ptr [rbp+arg_10]
0x18005a7e4  bts     ebx, 1Eh
0x18005a7e8  mov     dword ptr [rbp+arg_10], 0
0x18005a7ef  mov     [rbp+arg_8], 0
0x18005a7f7  mov     [rbp+var_20], rdi
0x18005a7fb  lea     rax, [rbp+arg_8]
0x18005a7ff  mov     [rbp+var_18], rax
0x18005a803  lea     rax, [rbp+arg_10]
0x18005a807  mov     [rbp+var_10], rax
0x18005a80b  lea     rdx, [rbp+var_20]
0x18005a80f  lea     rcx, [rbp+arg_18]
0x18005a813  call    ??$Make@V?$CTaskWrapper@V_lambda_1390acf51d11074e2a586070f25dbf13_@@@ComTaskPool@Internal@Windows@@V_lambda_1390acf51d11074e2a586070f25dbf13_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_1390acf51d11074e2a586070f25dbf13_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_1390acf51d11074e2a586070f25dbf13_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_1390acf51d11074e2a586070f25dbf13_>,_lambda_1390acf51d11074e2a586070f25dbf13_>(_lambda_1390acf51d11074e2a586070f25dbf13_ &&)
0x18005a818  mov     rdi, [rax]
0x18005a81b  mov     qword ptr [rax], 0
0x18005a822  mov     rcx, [rbp+arg_18]
0x18005a826  test    rcx, rcx
0x18005a829  jz      short loc_18005A838
0x18005a82b  mov     [rbp+arg_18], 0
0x18005a833  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18005a838  mov     [rsp+50h+var_28], 0
0x18005a841  mov     [rsp+50h+var_30], rdi
0x18005a846  xor     r9d, r9d
0x18005a849  mov     r8d, ebx
0x18005a84c  lea     edx, [r9+21h]
0x18005a850  lea     ecx, [rdx-20h]
0x18005a853  call    cs:__imp_SHTaskPoolQueueTask
0x18005a859  mov     ebx, eax
0x18005a85b  test    rdi, rdi
0x18005a85e  jz      short loc_18005A870
0x18005a860  mov     rax, [rdi]
0x18005a863  mov     rcx, rdi
0x18005a866  mov     rax, [rax+10h]
0x18005a86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a86f  nop
0x18005a870  test    ebx, ebx
0x18005a872  js      short loc_18005A893
0x18005a874  mov     ebx, dword ptr [rbp+arg_10]
0x18005a877  test    ebx, ebx
0x18005a879  js      short loc_18005A893
0x18005a87b  xor     r9d, r9d; bool
0x18005a87e  mov     r8, rsi; void **
0x18005a881  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x18005a888  lea     rcx, [rbp+arg_8]; this
0x18005a88c  call    ?_Unmarshal@CMarshaledInterface@@AEAAJAEBU_GUID@@PEAPEAX_N@Z; CMarshaledInterface::_Unmarshal(_GUID const &,void * *,bool)
0x18005a891  mov     ebx, eax
0x18005a893  lea     rcx, [rbp+arg_8]
0x18005a897  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005a89c  mov     eax, ebx
0x18005a89e  mov     rbx, [rsp+50h+arg_0]
0x18005a8a3  add     rsp, 50h
0x18005a8a7  pop     rdi
0x18005a8a8  pop     rsi
0x18005a8a9  pop     rbp
0x18005a8aa  retn
```
