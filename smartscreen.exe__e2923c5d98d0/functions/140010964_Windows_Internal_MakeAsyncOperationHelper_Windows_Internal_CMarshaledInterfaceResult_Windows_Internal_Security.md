# Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::Security::SmartScreen::UriReputationResult *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>> *)

- ea: `0x140010964`
- end: `0x140010a27`
- name: `??$MakeAsyncOperationHelper@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@Windows@@PEAVUriReputationResult@SmartScreen@Security@23@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@Windows@@@01@@Z`
- size: `195`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003b390`

## callees

- `0x140010964`
- `0x140010a30`
- `0x14001d4d4`
- `0x140025fc0`
- `0x140068010`

## string_xrefs

- `0x1400109a8`: `Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.UriReputationResult>`

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
  v7 = operator new(0x160u, (const struct std::nothrow_t *)&std::nothrow);
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
0x140010964  mov     [rsp+arg_0], rbx
0x140010969  mov     [rsp+arg_10], rsi
0x14001096e  push    rdi
0x14001096f  sub     rsp, 20h
0x140010973  mov     rdi, r9
0x140010976  mov     rsi, rdx
0x140010979  mov     rbx, rcx
0x14001097c  mov     qword ptr [rdx], 0
0x140010983  test    r9, r9
0x140010986  jz      loc_140010A10
0x14001098c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010993  mov     ecx, 160h; unsigned __int64
0x140010998  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001099d  test    rax, rax
0x1400109a0  jz      short loc_1400109FC
0x1400109a2  mov     r9d, 1
0x1400109a8  lea     r8, aWindowsFoundat_0; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x1400109af  mov     rdx, rbx
0x1400109b2  mov     rcx, rax
0x1400109b5  call    ??0?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAA@$$QEAVComTaskPoolHandler@12@QEBGW4TrustLevel@@@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel)
0x1400109ba  mov     rbx, rax
0x1400109bd  test    rax, rax
0x1400109c0  jz      short loc_1400109FC
0x1400109c2  mov     [rax+108h], rdi
0x1400109c9  lea     rcx, [rax+8]
0x1400109cd  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x1400109d2  mov     edi, eax
0x1400109d4  test    eax, eax
0x1400109d6  js      short loc_1400109E4
0x1400109d8  lea     rax, [rbx+0B8h]
0x1400109df  mov     [rsi], rax
0x1400109e2  xor     ebx, ebx
0x1400109e4  test    rbx, rbx
0x1400109e7  jz      short loc_1400109FA
0x1400109e9  lea     rcx, [rbx+8]
0x1400109ed  mov     rax, [rcx]
0x1400109f0  mov     rax, [rax+10h]
0x1400109f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400109f9  nop
0x1400109fa  jmp     short loc_140010A15
0x1400109fc  mov     rax, [rdi]
0x1400109ff  mov     edx, 1
0x140010a04  mov     rcx, rdi
0x140010a07  mov     rax, [rax]
0x140010a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a0f  nop
0x140010a10  mov     edi, 8007000Eh
0x140010a15  mov     eax, edi
0x140010a17  mov     rbx, [rsp+28h+arg_0]
0x140010a1c  mov     rsi, [rsp+28h+arg_10]
0x140010a21  add     rsp, 20h
0x140010a25  pop     rdi
0x140010a26  retn
```
