# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18004858c`
- end: `0x1800486b6`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800488e8`

## callees

- `0x18001c96c`
- `0x180042dec`
- `0x18004858c`
- `0x180048d94`
- `0x180048eec`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048657`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180048648`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180048648`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  _QWORD *v3; // rdi
  signed int v4; // ebx
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  _QWORD *v9; // [rsp+30h] [rbp+8h] BYREF
  void *v10; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v2;
  v3 = v2;
  if ( v2 )
  {
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Microsoft::WRL::FtmBase>(v2);
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>'};
    v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_DWORD *)v3 + 11) = 1;
    if ( v5 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
    *((_DWORD *)v3 + 12) = 0;
    *v3 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>'::`2'::FTMEventDelegate::`vftable';
    v3[7] = 0;
    v3[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v9 = v3;
    v10 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v3[7] = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_QWORD *))(*v3 + 8LL))(v3);
      *a1 = v3;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
      v4 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  __1__MakeAllocator_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVRestrictedAppContainer_Core_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Details_WRL_Microsoft__QEAA_XZ(&v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004858c  mov     [rsp+arg_10], rbx
0x180048591  mov     [rsp+arg_18], rsi
0x180048596  push    rdi
0x180048597  sub     rsp, 20h
0x18004859b  mov     rsi, rcx
0x18004859e  mov     qword ptr [rcx], 0
0x1800485a5  mov     ecx, 40h ; '@'; unsigned __int64
0x1800485aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800485b1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800485b6  mov     [rsp+28h+arg_8], rax
0x1800485bb  mov     rdi, rax
0x1800485be  test    rax, rax
0x1800485c1  jnz     short loc_1800485CD
0x1800485c3  mov     ebx, 8007000Eh
0x1800485c8  jmp     loc_18004869A
0x1800485cd  mov     rcx, rdi
0x1800485d0  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Microsoft::WRL::FtmBase>(void)
0x1800485d5  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800485dc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>'}
0x1800485e3  mov     [rdi], rax
0x1800485e6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800485ed  mov     [rdi+8], rax
0x1800485f1  mov     dword ptr [rdi+2Ch], 1
0x1800485f8  test    rcx, rcx
0x1800485fb  jz      short loc_180048609
0x1800485fd  mov     rax, [rcx]
0x180048600  mov     rax, [rax+8]
0x180048604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048609  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>'}
0x180048610  mov     dword ptr [rdi+30h], 0
0x180048617  mov     [rdi], rax
0x18004861a  mov     r9d, 1F0003h; dwDesiredAccess
0x180048620  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180048627  mov     qword ptr [rdi+38h], 0
0x18004862f  xor     r8d, r8d; dwFlags
0x180048632  mov     [rdi+8], rax
0x180048636  xor     edx, edx; lpName
0x180048638  mov     [rsp+28h+arg_0], rdi
0x18004863d  xor     ecx, ecx; lpEventAttributes
0x18004863f  mov     [rsp+28h+arg_8], 0
0x180048648  call    cs:__imp_CreateEventExW
0x18004864e  mov     [rdi+38h], rax
0x180048652  test    rax, rax
0x180048655  jnz     short loc_18004867C
0x180048657  call    cs:__imp_GetLastError
0x18004865d  mov     ebx, eax
0x18004865f  test    eax, eax
0x180048661  jle     short loc_18004866C
0x180048663  movzx   ebx, ax
0x180048666  or      ebx, 80070000h
0x18004866c  test    ebx, ebx
0x18004866e  jns     short loc_18004867C
0x180048670  lea     rcx, [rsp+28h+arg_0]
0x180048675  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004867a  jmp     short loc_18004869A
0x18004867c  mov     rax, [rdi]
0x18004867f  mov     rcx, rdi
0x180048682  mov     rax, [rax+8]
0x180048686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004868b  lea     rcx, [rsp+28h+arg_0]
0x180048690  mov     [rsi], rdi
0x180048693  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180048698  xor     ebx, ebx
0x18004869a  lea     rcx, [rsp+28h+arg_8]
0x18004869f  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x1800486a4  mov     rsi, [rsp+28h+arg_18]
0x1800486a9  mov     eax, ebx
0x1800486ab  mov     rbx, [rsp+28h+arg_10]
0x1800486b0  add     rsp, 20h
0x1800486b4  pop     rdi
0x1800486b5  retn
```
