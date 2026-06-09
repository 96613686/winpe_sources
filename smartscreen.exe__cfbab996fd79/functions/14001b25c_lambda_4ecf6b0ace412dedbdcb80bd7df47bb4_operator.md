# _lambda_4ecf6b0ace412dedbdcb80bd7df47bb4_::operator()

- ea: `0x14001b25c`
- end: `0x14001b3a7`
- name: `_lambda_4ecf6b0ace412dedbdcb80bd7df47bb4_::operator()`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001a840`

## callees

- `0x140002990`
- `0x140006d90`
- `0x1400174e4`
- `0x14001afa0`
- `0x14001b25c`
- `0x14001b3b0`
- `0x14001b490`
- `0x140026c20`
- `0x140027134`
- `0x1400309e0`

## string_xrefs

- `0x14001b342`: `Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.AppReputationResult>`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_4ecf6b0ace412dedbdcb80bd7df47bb4_::operator()(__int64 **a1, _QWORD *a2, __int64 a3)
{
  __int64 *v6; // r9
  char v7; // r8
  __int64 v8; // rbx
  void *v9; // rax
  int v10; // r9d
  unsigned int v11; // ebx
  int v13; // [rsp+30h] [rbp-69h] BYREF
  __int64 v14; // [rsp+34h] [rbp-65h]
  __int64 v15; // [rsp+40h] [rbp-59h]
  void *v16; // [rsp+48h] [rbp-51h]
  _BYTE v17[8]; // [rsp+50h] [rbp-49h] BYREF
  std::_Ref_count_base *v18; // [rsp+58h] [rbp-41h]
  __int64 v19; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v21[32]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v22; // [rsp+A8h] [rbp+Fh]
  __int64 v23; // [rsp+B0h] [rbp+17h]
  char v24; // [rsp+B8h] [rbp+1Fh]
  _QWORD *v25; // [rsp+C0h] [rbp+27h]

  v25 = a2;
  v15 = a3;
  com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>(
    v17,
    *a1[3]);
  v19 = *a2;
  *a2 = 0;
  std::wstring::wstring(v20);
  std::wstring::wstring(v21);
  v22 = *v6;
  v23 = v6[1];
  *v6 = 0;
  v6[1] = 0;
  v24 = v7;
  v8 = **a1;
  v13 = 3;
  v14 = 128;
  v9 = operator new(0x78u, (const struct std::nothrow_t *)std::nothrow);
  v16 = v9;
  if ( v9 )
    v9 = (void *)Windows::Internal::COperationLambdaVar_0__lambda_ff1938da65d60cabaa1a6e57ec4bb303__Windows::Internal::CBasicResult_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_2___::COperationLambdaVar_0__lambda_ff1938da65d60cabaa1a6e57ec4bb303__Windows::Internal::CBasicResult_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_2_____lambda_ff1938da65d60cabaa1a6e57ec4bb303___(
                   v9,
                   &v19);
  v11 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<enum Windows::Internal::Security::SmartScreen::AppReputationResult,2>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
          v8,
          (unsigned int)&v13,
          (unsigned int)L"Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.AppReputationResult>",
          v10,
          (__int64)v9);
  lambda_ff1938da65d60cabaa1a6e57ec4bb303_::__lambda_ff1938da65d60cabaa1a6e57ec4bb303_(&v19);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a3);
  return v11;
}

```

## disassembly

```asm
0x14001b25c  mov     [rsp-8+arg_18], rbx
0x14001b261  push    rbp
0x14001b262  push    rsi
0x14001b263  push    rdi
0x14001b264  push    r14
0x14001b266  push    r15
0x14001b268  lea     rbp, [rsp-37h]
0x14001b26d  sub     rsp, 0D0h
0x14001b274  mov     rax, cs:__security_cookie
0x14001b27b  xor     rax, rsp
0x14001b27e  mov     [rbp+57h+var_28], rax
0x14001b282  mov     r15, r8
0x14001b285  mov     r14, rdx
0x14001b288  mov     rsi, rcx
0x14001b28b  mov     [rbp+57h+var_30], rdx
0x14001b28f  mov     [rbp+57h+var_B0], r8
0x14001b293  mov     rbx, [rcx+8]
0x14001b297  mov     rdi, [rcx+10h]
0x14001b29b  mov     rdx, [rcx+18h]
0x14001b29f  mov     rdx, [rdx]
0x14001b2a2  lea     rcx, [rbp+57h+var_A0]
0x14001b2a6  call    ??0?$marshaled_ptr@UIWindow@SmartScreen@Security@Internal@Windows@@@com@@QEAA@PEAUIWindow@SmartScreen@Security@Internal@Windows@@@Z; com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>(Windows::Internal::Security::SmartScreen::IWindow *)
0x14001b2ab  mov     r9, rax
0x14001b2ae  mov     rcx, [rsi+20h]
0x14001b2b2  mov     r8b, [rcx+0D0h]
0x14001b2b9  mov     rcx, [r14]
0x14001b2bc  mov     [rbp+57h+var_90], rcx
0x14001b2c0  mov     qword ptr [r14], 0
0x14001b2c7  mov     rdx, rbx
0x14001b2ca  lea     rcx, [rbp+57h+var_88]
0x14001b2ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14001b2d3  mov     rdx, rdi
0x14001b2d6  lea     rcx, [rbp+57h+var_68]
0x14001b2da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14001b2df  mov     rcx, [r9]
0x14001b2e2  mov     [rbp+57h+var_48], rcx
0x14001b2e6  mov     rax, [r9+8]
0x14001b2ea  mov     [rbp+57h+var_40], rax
0x14001b2ee  mov     qword ptr [r9], 0
0x14001b2f5  mov     qword ptr [r9+8], 0
0x14001b2fd  mov     [rbp+57h+var_38], r8b
0x14001b301  mov     rax, [rsi]
0x14001b304  mov     rbx, [rax]
0x14001b307  mov     [rbp+57h+var_C0], 3
0x14001b30e  mov     [rbp+57h+var_BC], 80h
0x14001b316  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001b31d  mov     ecx, 78h ; 'x'; unsigned __int64
0x14001b322  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001b327  mov     [rbp+57h+var_A8], rax
0x14001b32b  test    rax, rax
0x14001b32e  jz      short loc_14001B33D
0x14001b330  lea     rdx, [rbp+57h+var_90]
0x14001b334  mov     rcx, rax
0x14001b337  call    Windows__Internal__COperationLambdaVar_0__lambda_ff1938da65d60cabaa1a6e57ec4bb303__Windows__Internal__CBasicResult_enum_Windows__Internal__Security__SmartScreen__AppReputationResult_2_____COperationLambdaVar_0__lambda_ff1938da65d60cabaa1a6e57ec4bb303__Windows__Internal__CBasicResult_enum_Windows__Internal__Security__SmartScreen__AppReputationResult_2_____lambda_ff1938da65d60cabaa1a6e57ec4bb303___
0x14001b33c  nop
0x14001b33d  mov     [rsp+0F0h+var_D0], rax
0x14001b342  lea     r8, aWindowsFoundat_7; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x14001b349  lea     rdx, [rbp+57h+var_C0]
0x14001b34d  mov     rcx, rbx
0x14001b350  call    ??$MakeAsyncHelper@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@UINilDelegate@Internal@3@V?$CBasicResult@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@$01@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@$01@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<Windows::Internal::Security::SmartScreen::AppReputationResult,2>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<Windows::Internal::Security::SmartScreen::AppReputationResult,2>> *)
0x14001b355  mov     ebx, eax
0x14001b357  lea     rcx, [rbp+57h+var_90]
0x14001b35b  call    _lambda_ff1938da65d60cabaa1a6e57ec4bb303_____lambda_ff1938da65d60cabaa1a6e57ec4bb303_
0x14001b360  nop
0x14001b361  mov     rcx, [rbp+57h+var_98]; this
0x14001b365  test    rcx, rcx
0x14001b368  jz      short loc_14001B370
0x14001b36a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001b36f  nop
0x14001b370  mov     rcx, r14
0x14001b373  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001b378  nop
0x14001b379  mov     rcx, r15
0x14001b37c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001b381  mov     eax, ebx
0x14001b383  mov     rcx, [rbp+57h+var_28]
0x14001b387  xor     rcx, rsp; StackCookie
0x14001b38a  call    __security_check_cookie
0x14001b38f  mov     rbx, [rsp+0F0h+arg_18]
0x14001b397  add     rsp, 0D0h
0x14001b39e  pop     r15
0x14001b3a0  pop     r14
0x14001b3a2  pop     rdi
0x14001b3a3  pop     rsi
0x14001b3a4  pop     rbp
0x14001b3a5  retn
```
