# Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo__Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo___Windows::Internal::ComTaskPoolHandler__lambda_b5cb27011e492c86acddc5c69a1ff404___

- ea: `0x14000c61c`
- end: `0x14000c707`
- name: `Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo__Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo___Windows::Internal::ComTaskPoolHandler__lambda_b5cb27011e492c86acddc5c69a1ff404___`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c508`

## callees

- `0x14000c61c`
- `0x14000c710`
- `0x14000c8c0`
- `0x14001d500`
- `0x140027134`
- `0x14006a010`

## string_xrefs

- `0x14000c68a`: `Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo__Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo___Windows::Internal::ComTaskPoolHandler__lambda_b5cb27011e492c86acddc5c69a1ff404___(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  void *v7; // rax
  void (__fastcall ***v8)(_QWORD, __int64); // rdi
  void *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  int v12; // edi
  void *v14; // [rsp+20h] [rbp-28h]

  v7 = operator new(0xE0u, (const struct std::nothrow_t *)std::nothrow);
  v14 = v7;
  if ( v7 )
    v8 = (void (__fastcall ***)(_QWORD, __int64))Windows::Internal::COperationLambdaVar_0__lambda_b5cb27011e492c86acddc5c69a1ff404__Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo___::COperationLambdaVar_0__lambda_b5cb27011e492c86acddc5c69a1ff404__Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo_____lambda_b5cb27011e492c86acddc5c69a1ff404___(
                                                   v7,
                                                   a4);
  else
    v8 = 0;
  *a2 = 0;
  if ( !v8 )
    return (unsigned int)-2147024882;
  v9 = operator new(0x160u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v9
    || (v10 = Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
                v9,
                a1,
                L"Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo>",
                1,
                v14),
        (v11 = v10) == 0) )
  {
    (**v8)(v8, 1);
    return (unsigned int)-2147024882;
  }
  *(_QWORD *)(v10 + 264) = v8;
  v12 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(v10 + 8);
  if ( v12 >= 0 )
  {
    *a2 = v11 + 184;
    v11 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 8) + 16LL))(v11 + 8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000c61c  mov     [rsp+arg_0], rbx
0x14000c621  push    rbp
0x14000c622  push    rsi
0x14000c623  push    rdi
0x14000c624  sub     rsp, 30h
0x14000c628  mov     rbx, r9
0x14000c62b  mov     rsi, rdx
0x14000c62e  mov     rbp, rcx
0x14000c631  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c638  mov     ecx, 0E0h; unsigned __int64
0x14000c63d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000c642  mov     [rsp+48h+var_28], rax
0x14000c647  test    rax, rax
0x14000c64a  jz      short loc_14000C65C
0x14000c64c  mov     rdx, rbx
0x14000c64f  mov     rcx, rax
0x14000c652  call    Windows__Internal__COperationLambdaVar_0__lambda_b5cb27011e492c86acddc5c69a1ff404__Windows__Internal__CMarshaledInterfaceResult_Windows__Internal__Security__SmartScreen__IUriReputationExperienceInfo_____COperationLambdaVar_0__lambda_b5cb27011e492c86acddc5c69a1ff404__Windows__Internal__CMarshaledInterfaceResult_Windows__Internal__Security__SmartScreen__IUriReputationExperienceInfo_____lambda_b5cb27011e492c86acddc5c69a1ff404___
0x14000c657  mov     rdi, rax
0x14000c65a  jmp     short loc_14000C65E
0x14000c65c  xor     edi, edi
0x14000c65e  mov     qword ptr [rsi], 0
0x14000c665  test    rdi, rdi
0x14000c668  jz      loc_14000C6F2
0x14000c66e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c675  mov     ecx, 160h; unsigned __int64
0x14000c67a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000c67f  test    rax, rax
0x14000c682  jz      short loc_14000C6DE
0x14000c684  mov     r9d, 1
0x14000c68a  lea     r8, aWindowsFoundat_10; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x14000c691  mov     rdx, rbp
0x14000c694  mov     rcx, rax
0x14000c697  call    ??0?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAA@$$QEAVComTaskPoolHandler@12@QEBGW4TrustLevel@@@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel)
0x14000c69c  mov     rbx, rax
0x14000c69f  test    rax, rax
0x14000c6a2  jz      short loc_14000C6DE
0x14000c6a4  mov     [rax+108h], rdi
0x14000c6ab  lea     rcx, [rax+8]
0x14000c6af  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x14000c6b4  mov     edi, eax
0x14000c6b6  test    eax, eax
0x14000c6b8  js      short loc_14000C6C6
0x14000c6ba  lea     rax, [rbx+0B8h]
0x14000c6c1  mov     [rsi], rax
0x14000c6c4  xor     ebx, ebx
0x14000c6c6  test    rbx, rbx
0x14000c6c9  jz      short loc_14000C6DC
0x14000c6cb  lea     rcx, [rbx+8]
0x14000c6cf  mov     rax, [rcx]
0x14000c6d2  mov     rax, [rax+10h]
0x14000c6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c6db  nop
0x14000c6dc  jmp     short loc_14000C6F7
0x14000c6de  mov     rax, [rdi]
0x14000c6e1  mov     edx, 1
0x14000c6e6  mov     rcx, rdi
0x14000c6e9  mov     rax, [rax]
0x14000c6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c6f1  nop
0x14000c6f2  mov     edi, 8007000Eh
0x14000c6f7  mov     eax, edi
0x14000c6f9  mov     rbx, [rsp+48h+arg_0]
0x14000c6fe  add     rsp, 30h
0x14000c702  pop     rdi
0x14000c703  pop     rsi
0x14000c704  pop     rbp
0x14000c705  retn
```
