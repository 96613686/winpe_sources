# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800487ec`
- end: `0x1800488e2`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180048c08`

## callees

- `0x18001c96c`
- `0x180042dec`
- `0x1800487ec`
- `0x180048e2c`
- `0x180048eec`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048883`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180048874`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180048874`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_UIAsyncActionCompletedHandler_Foundation_Windows__UIAsyncAction_23___YAJPEAUIAsyncAction_Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  _DWORD *v3; // rdi
  signed int v4; // ebx
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v8; // [rsp+30h] [rbp+8h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v2;
  v3 = v2;
  if ( v2 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(v2);
    v3[12] = 0;
    *(_QWORD *)v3 = &`WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>'::`2'::FTMEventDelegate::`vftable';
    v8 = v3;
    v9 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v3 + 7) = Event;
    if ( Event )
      goto LABEL_8;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(&v9);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800487ec  mov     [rsp+arg_10], rbx
0x1800487f1  mov     [rsp+arg_18], rsi
0x1800487f6  push    rdi
0x1800487f7  sub     rsp, 20h
0x1800487fb  mov     rsi, rcx
0x1800487fe  mov     qword ptr [rcx], 0
0x180048805  mov     ecx, 40h ; '@'; unsigned __int64
0x18004880a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180048811  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048816  mov     [rsp+28h+arg_8], rax
0x18004881b  mov     rdi, rax
0x18004881e  test    rax, rax
0x180048821  jnz     short loc_18004882D
0x180048823  mov     ebx, 8007000Eh
0x180048828  jmp     loc_1800488C6
0x18004882d  mov     rcx, rdi
0x180048830  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>(void)
0x180048835  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6BIAsyncActionCompletedHandler@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncActionCompletedHandler'}
0x18004883c  mov     dword ptr [rdi+30h], 0
0x180048843  mov     [rdi], rax
0x180048846  mov     r9d, 1F0003h; dwDesiredAccess
0x18004884c  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180048853  mov     qword ptr [rdi+38h], 0
0x18004885b  xor     r8d, r8d; dwFlags
0x18004885e  mov     [rdi+8], rax
0x180048862  xor     edx, edx; lpName
0x180048864  mov     [rsp+28h+arg_0], rdi
0x180048869  xor     ecx, ecx; lpEventAttributes
0x18004886b  mov     [rsp+28h+arg_8], 0
0x180048874  call    cs:__imp_CreateEventExW
0x18004887a  mov     [rdi+38h], rax
0x18004887e  test    rax, rax
0x180048881  jnz     short loc_1800488A8
0x180048883  call    cs:__imp_GetLastError
0x180048889  mov     ebx, eax
0x18004888b  test    eax, eax
0x18004888d  jle     short loc_180048898
0x18004888f  movzx   ebx, ax
0x180048892  or      ebx, 80070000h
0x180048898  test    ebx, ebx
0x18004889a  jns     short loc_1800488A8
0x18004889c  lea     rcx, [rsp+28h+arg_0]
0x1800488a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800488a6  jmp     short loc_1800488C6
0x1800488a8  mov     rax, [rdi]
0x1800488ab  mov     rcx, rdi
0x1800488ae  mov     rax, [rax+8]
0x1800488b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488b7  lea     rcx, [rsp+28h+arg_0]
0x1800488bc  mov     [rsi], rdi
0x1800488bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800488c4  xor     ebx, ebx
0x1800488c6  lea     rcx, [rsp+28h+arg_8]
0x1800488cb  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x1800488d0  mov     rsi, [rsp+28h+arg_18]
0x1800488d5  mov     eax, ebx
0x1800488d7  mov     rbx, [rsp+28h+arg_10]
0x1800488dc  add     rsp, 20h
0x1800488e0  pop     rdi
0x1800488e1  retn
```
