# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x1800486bc`
- end: `0x1800487e6`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180048a7c`

## callees

- `0x18001c96c`
- `0x180042dec`
- `0x1800486bc`
- `0x180048d94`
- `0x180048eec`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048787`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048787`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180048778`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180048778`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4ExtendedExecutionForegroundResult_Foreground_ExtendedExecution_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4ExtendedExecutionForegroundResult_Foreground_ExtendedExecution_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_W4ExtendedExecutionForegroundResult_Foreground_ExtendedExecution_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4ExtendedExecutionForegroundResult_Foreground_ExtendedExecution_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4ExtendedExecutionForegroundResult_Foreground_ExtendedExecution_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4ExtendedExecutionForegroundResult_Foreground_ExtendedExecution_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4ExtendedExecutionForegroundResult_Foreground_ExtendedExecution_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_W4ExtendedExecutionForegroundResult_Foreground_ExtendedExecution_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *v3 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>'};
    v3[1] = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v3 + 11) = 1;
    if ( v5 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
    *((_DWORD *)v3 + 12) = 0;
    *v3 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>'::`2'::FTMEventDelegate::`vftable';
    v3[7] = 0;
    v3[1] = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>'::`2'::FTMEventDelegate::`vftable';
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
0x1800486bc  mov     [rsp+arg_10], rbx
0x1800486c1  mov     [rsp+arg_18], rsi
0x1800486c6  push    rdi
0x1800486c7  sub     rsp, 20h
0x1800486cb  mov     rsi, rcx
0x1800486ce  mov     qword ptr [rcx], 0
0x1800486d5  mov     ecx, 40h ; '@'; unsigned __int64
0x1800486da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800486e1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800486e6  mov     [rsp+28h+arg_8], rax
0x1800486eb  mov     rdi, rax
0x1800486ee  test    rax, rax
0x1800486f1  jnz     short loc_1800486FD
0x1800486f3  mov     ebx, 8007000Eh
0x1800486f8  jmp     loc_1800487CA
0x1800486fd  mov     rcx, rdi
0x180048700  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Microsoft::WRL::FtmBase>(void)
0x180048705  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004870c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>'}
0x180048713  mov     [rdi], rax
0x180048716  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004871d  mov     [rdi+8], rax
0x180048721  mov     dword ptr [rdi+2Ch], 1
0x180048728  test    rcx, rcx
0x18004872b  jz      short loc_180048739
0x18004872d  mov     rax, [rcx]
0x180048730  mov     rax, [rax+8]
0x180048734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048739  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>'}
0x180048740  mov     dword ptr [rdi+30h], 0
0x180048747  mov     [rdi], rax
0x18004874a  mov     r9d, 1F0003h; dwDesiredAccess
0x180048750  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180048757  mov     qword ptr [rdi+38h], 0
0x18004875f  xor     r8d, r8d; dwFlags
0x180048762  mov     [rdi+8], rax
0x180048766  xor     edx, edx; lpName
0x180048768  mov     [rsp+28h+arg_0], rdi
0x18004876d  xor     ecx, ecx; lpEventAttributes
0x18004876f  mov     [rsp+28h+arg_8], 0
0x180048778  call    cs:__imp_CreateEventExW
0x18004877e  mov     [rdi+38h], rax
0x180048782  test    rax, rax
0x180048785  jnz     short loc_1800487AC
0x180048787  call    cs:__imp_GetLastError
0x18004878d  mov     ebx, eax
0x18004878f  test    eax, eax
0x180048791  jle     short loc_18004879C
0x180048793  movzx   ebx, ax
0x180048796  or      ebx, 80070000h
0x18004879c  test    ebx, ebx
0x18004879e  jns     short loc_1800487AC
0x1800487a0  lea     rcx, [rsp+28h+arg_0]
0x1800487a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800487aa  jmp     short loc_1800487CA
0x1800487ac  mov     rax, [rdi]
0x1800487af  mov     rcx, rdi
0x1800487b2  mov     rax, [rax+8]
0x1800487b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487bb  lea     rcx, [rsp+28h+arg_0]
0x1800487c0  mov     [rsi], rdi
0x1800487c3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800487c8  xor     ebx, ebx
0x1800487ca  lea     rcx, [rsp+28h+arg_8]
0x1800487cf  call    ??1?$MakeAllocator@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVRestrictedAppContainer@Core@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::~MakeAllocator<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Core::RestrictedAppContainer *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Core::RestrictedAppContainer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>(void)
0x1800487d4  mov     rsi, [rsp+28h+arg_18]
0x1800487d9  mov     eax, ebx
0x1800487db  mov     rbx, [rsp+28h+arg_10]
0x1800487e0  add     rsp, 20h
0x1800487e4  pop     rdi
0x1800487e5  retn
```
