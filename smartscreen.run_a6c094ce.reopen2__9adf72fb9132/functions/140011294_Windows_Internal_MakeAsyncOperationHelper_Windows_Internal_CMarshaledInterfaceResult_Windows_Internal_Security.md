# Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::Security::SmartScreen::UriReputationResult *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>> *)

- ea: `0x140011294`
- end: `0x140011358`
- name: `??$MakeAsyncOperationHelper@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@Windows@@PEAVUriReputationResult@SmartScreen@Security@23@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@Windows@@@01@@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003ca14`

## callees

- `0x140011294`
- `0x140011360`
- `0x14001e4d8`
- `0x140027134`
- `0x14006a010`

## string_xrefs

- `0x1400112d8`: `Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.UriReputationResult>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::Security::SmartScreen::UriReputationResult *,Windows::Internal::ComTaskPoolHandler>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        void (__fastcall ***a4)(_QWORD, __int64))
{
  void *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // edi

  *a2 = 0;
  if ( !a4 )
    return (unsigned int)-2147024882;
  v7 = operator new(0x160u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v7
    || (v8 = Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
               v7,
               a1,
               L"Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.UriReputationResult>",
               1),
        (v9 = v8) == 0) )
  {
    (**a4)(a4, 1);
    return (unsigned int)-2147024882;
  }
  *(_QWORD *)(v8 + 264) = a4;
  v10 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(v8 + 8);
  if ( v10 >= 0 )
  {
    *a2 = v9 + 184;
    v9 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v9 + 8) + 16LL))(v9 + 8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140011294  mov     [rsp+arg_0], rbx
0x140011299  mov     [rsp+arg_10], rsi
0x14001129e  push    rdi
0x14001129f  sub     rsp, 20h
0x1400112a3  mov     rdi, r9
0x1400112a6  mov     rsi, rdx
0x1400112a9  mov     rbx, rcx
0x1400112ac  mov     qword ptr [rdx], 0
0x1400112b3  test    r9, r9
0x1400112b6  jz      loc_140011340
0x1400112bc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400112c3  mov     ecx, 160h; unsigned __int64
0x1400112c8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400112cd  test    rax, rax
0x1400112d0  jz      short loc_14001132C
0x1400112d2  mov     r9d, 1
0x1400112d8  lea     r8, aWindowsFoundat_0; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x1400112df  mov     rdx, rbx
0x1400112e2  mov     rcx, rax
0x1400112e5  call    ??0?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAA@$$QEAVComTaskPoolHandler@12@QEBGW4TrustLevel@@@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel)
0x1400112ea  mov     rbx, rax
0x1400112ed  test    rax, rax
0x1400112f0  jz      short loc_14001132C
0x1400112f2  mov     [rax+108h], rdi
0x1400112f9  lea     rcx, [rax+8]
0x1400112fd  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x140011302  mov     edi, eax
0x140011304  test    eax, eax
0x140011306  js      short loc_140011314
0x140011308  lea     rax, [rbx+0B8h]
0x14001130f  mov     [rsi], rax
0x140011312  xor     ebx, ebx
0x140011314  test    rbx, rbx
0x140011317  jz      short loc_14001132A
0x140011319  lea     rcx, [rbx+8]
0x14001131d  mov     rax, [rcx]
0x140011320  mov     rax, [rax+10h]
0x140011324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011329  nop
0x14001132a  jmp     short loc_140011345
0x14001132c  mov     rax, [rdi]
0x14001132f  mov     edx, 1
0x140011334  mov     rcx, rdi
0x140011337  mov     rax, [rax]
0x14001133a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001133f  nop
0x140011340  mov     edi, 8007000Eh
0x140011345  mov     eax, edi
0x140011347  mov     rbx, [rsp+28h+arg_0]
0x14001134c  mov     rsi, [rsp+28h+arg_10]
0x140011351  add     rsp, 20h
0x140011355  pop     rdi
0x140011356  retn
```
