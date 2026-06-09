# Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo__Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo___Windows::Internal::ComTaskPoolHandler__lambda_b5cb27011e492c86acddc5c69a1ff404___

- ea: `0x14000bfd0`
- end: `0x14000c0ba`
- name: `Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo__Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo___Windows::Internal::ComTaskPoolHandler__lambda_b5cb27011e492c86acddc5c69a1ff404___`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000bebc`

## callees

- `0x14000bfd0`
- `0x14000c0c0`
- `0x14000c270`
- `0x14001c5a0`
- `0x140025fc0`
- `0x140068010`

## string_xrefs

- `0x14000c03e`: `Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.UriReputationExperienceInfo>`

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

  v7 = operator new(0xE0u, (const struct std::nothrow_t *)&std::nothrow);
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
  v9 = operator new(0x160u, (const struct std::nothrow_t *)&std::nothrow);
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
0x14000bfd0  mov     [rsp+arg_0], rbx
0x14000bfd5  push    rbp
0x14000bfd6  push    rsi
0x14000bfd7  push    rdi
0x14000bfd8  sub     rsp, 30h
0x14000bfdc  mov     rbx, r9
0x14000bfdf  mov     rsi, rdx
0x14000bfe2  mov     rbp, rcx
0x14000bfe5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bfec  mov     ecx, 0E0h; unsigned __int64
0x14000bff1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000bff6  mov     [rsp+48h+var_28], rax
0x14000bffb  test    rax, rax
0x14000bffe  jz      short loc_14000C010
0x14000c000  mov     rdx, rbx
0x14000c003  mov     rcx, rax
0x14000c006  call    Windows__Internal__COperationLambdaVar_0__lambda_b5cb27011e492c86acddc5c69a1ff404__Windows__Internal__CMarshaledInterfaceResult_Windows__Internal__Security__SmartScreen__IUriReputationExperienceInfo_____COperationLambdaVar_0__lambda_b5cb27011e492c86acddc5c69a1ff404__Windows__Internal__CMarshaledInterfaceResult_Windows__Internal__Security__SmartScreen__IUriReputationExperienceInfo_____lambda_b5cb27011e492c86acddc5c69a1ff404___
0x14000c00b  mov     rdi, rax
0x14000c00e  jmp     short loc_14000C012
0x14000c010  xor     edi, edi
0x14000c012  mov     qword ptr [rsi], 0
0x14000c019  test    rdi, rdi
0x14000c01c  jz      loc_14000C0A6
0x14000c022  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c029  mov     ecx, 160h; unsigned __int64
0x14000c02e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000c033  test    rax, rax
0x14000c036  jz      short loc_14000C092
0x14000c038  mov     r9d, 1
0x14000c03e  lea     r8, aWindowsFoundat_10; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x14000c045  mov     rdx, rbp
0x14000c048  mov     rcx, rax
0x14000c04b  call    ??0?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAA@$$QEAVComTaskPoolHandler@12@QEBGW4TrustLevel@@@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel)
0x14000c050  mov     rbx, rax
0x14000c053  test    rax, rax
0x14000c056  jz      short loc_14000C092
0x14000c058  mov     [rax+108h], rdi
0x14000c05f  lea     rcx, [rax+8]
0x14000c063  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x14000c068  mov     edi, eax
0x14000c06a  test    eax, eax
0x14000c06c  js      short loc_14000C07A
0x14000c06e  lea     rax, [rbx+0B8h]
0x14000c075  mov     [rsi], rax
0x14000c078  xor     ebx, ebx
0x14000c07a  test    rbx, rbx
0x14000c07d  jz      short loc_14000C090
0x14000c07f  lea     rcx, [rbx+8]
0x14000c083  mov     rax, [rcx]
0x14000c086  mov     rax, [rax+10h]
0x14000c08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c08f  nop
0x14000c090  jmp     short loc_14000C0AB
0x14000c092  mov     rax, [rdi]
0x14000c095  mov     edx, 1
0x14000c09a  mov     rcx, rdi
0x14000c09d  mov     rax, [rax]
0x14000c0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0a5  nop
0x14000c0a6  mov     edi, 8007000Eh
0x14000c0ab  mov     eax, edi
0x14000c0ad  mov     rbx, [rsp+48h+arg_0]
0x14000c0b2  add     rsp, 30h
0x14000c0b6  pop     rdi
0x14000c0b7  pop     rsi
0x14000c0b8  pop     rbp
0x14000c0b9  retn
```
