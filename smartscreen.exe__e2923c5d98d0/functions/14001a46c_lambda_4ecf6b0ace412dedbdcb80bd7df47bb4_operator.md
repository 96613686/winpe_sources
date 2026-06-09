# _lambda_4ecf6b0ace412dedbdcb80bd7df47bb4_::operator()

- ea: `0x14001a46c`
- end: `0x14001a5b6`
- name: `_lambda_4ecf6b0ace412dedbdcb80bd7df47bb4_::operator()`
- size: `330`
- prototype: `__int64 __fastcall(__int64 **, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140019b18`

## callees

- `0x14000287c`
- `0x140006a00`
- `0x1400174f4`
- `0x14001a1b8`
- `0x14001a46c`
- `0x14001a5bc`
- `0x14001a69c`
- `0x140025aa0`
- `0x140025fc0`
- `0x14002f710`

## string_xrefs

- `0x14001a552`: `Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.AppReputationResult>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_4ecf6b0ace412dedbdcb80bd7df47bb4_::operator()(__int64 **a1, _QWORD *a2, __int64 a3)
{
  __int64 *v6; // rbx
  __int64 *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 *v12; // r9
  char v13; // r8
  __int64 v14; // rbx
  void *v15; // rax
  int v16; // r9d
  unsigned int v17; // ebx
  int v19; // [rsp+30h] [rbp-69h] BYREF
  __int64 v20; // [rsp+34h] [rbp-65h]
  __int64 v21; // [rsp+40h] [rbp-59h]
  void *v22; // [rsp+48h] [rbp-51h]
  _BYTE v23[8]; // [rsp+50h] [rbp-49h] BYREF
  std::_Ref_count_base *v24; // [rsp+58h] [rbp-41h]
  __int64 v25; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v26[32]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v27[32]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+Fh]
  __int64 v29; // [rsp+B0h] [rbp+17h]
  char v30; // [rsp+B8h] [rbp+1Fh]
  _QWORD *v31; // [rsp+C0h] [rbp+27h]

  v31 = a2;
  v21 = a3;
  v6 = a1[1];
  v7 = a1[2];
  v8 = com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>(
         v23,
         *a1[3]);
  LOBYTE(v9) = *((_BYTE *)a1[4] + 208);
  v25 = *a2;
  *a2 = 0;
  std::wstring::wstring(v26, v6, v9, v8);
  std::wstring::wstring(v27, v7, v10, v11);
  v28 = *v12;
  v29 = v12[1];
  *v12 = 0;
  v12[1] = 0;
  v30 = v13;
  v14 = **a1;
  v19 = 3;
  v20 = 128;
  v15 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v22 = v15;
  if ( v15 )
    v15 = (void *)Windows::Internal::COperationLambdaVar_0__lambda_ff1938da65d60cabaa1a6e57ec4bb303__Windows::Internal::CBasicResult_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_2___::COperationLambdaVar_0__lambda_ff1938da65d60cabaa1a6e57ec4bb303__Windows::Internal::CBasicResult_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_2_____lambda_ff1938da65d60cabaa1a6e57ec4bb303___(
                    v15,
                    &v25);
  v17 = Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<enum Windows::Internal::Security::SmartScreen::AppReputationResult,2>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
          v14,
          (unsigned int)&v19,
          (unsigned int)L"Windows.Foundation.IAsyncOperation`1<Windows.Internal.Security.SmartScreen.AppReputationResult>",
          v16,
          (__int64)v15);
  lambda_ff1938da65d60cabaa1a6e57ec4bb303_::__lambda_ff1938da65d60cabaa1a6e57ec4bb303_(&v25);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a2);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(a3);
  return v17;
}

```

## disassembly

```asm
0x14001a46c  mov     [rsp-8+arg_18], rbx
0x14001a471  push    rbp
0x14001a472  push    rsi
0x14001a473  push    rdi
0x14001a474  push    r14
0x14001a476  push    r15
0x14001a478  lea     rbp, [rsp-37h]
0x14001a47d  sub     rsp, 0D0h
0x14001a484  mov     rax, cs:__security_cookie
0x14001a48b  xor     rax, rsp
0x14001a48e  mov     [rbp+57h+var_28], rax
0x14001a492  mov     r15, r8
0x14001a495  mov     r14, rdx
0x14001a498  mov     rsi, rcx
0x14001a49b  mov     [rbp+57h+var_30], rdx
0x14001a49f  mov     [rbp+57h+var_B0], r8
0x14001a4a3  mov     rbx, [rcx+8]
0x14001a4a7  mov     rdi, [rcx+10h]
0x14001a4ab  mov     rdx, [rcx+18h]
0x14001a4af  mov     rdx, [rdx]
0x14001a4b2  lea     rcx, [rbp+57h+var_A0]
0x14001a4b6  call    ??0?$marshaled_ptr@UIWindow@SmartScreen@Security@Internal@Windows@@@com@@QEAA@PEAUIWindow@SmartScreen@Security@Internal@Windows@@@Z; com::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>::marshaled_ptr<Windows::Internal::Security::SmartScreen::IWindow>(Windows::Internal::Security::SmartScreen::IWindow *)
0x14001a4bb  mov     r9, rax
0x14001a4be  mov     rcx, [rsi+20h]
0x14001a4c2  mov     r8b, [rcx+0D0h]
0x14001a4c9  mov     rcx, [r14]
0x14001a4cc  mov     [rbp+57h+var_90], rcx
0x14001a4d0  mov     qword ptr [r14], 0
0x14001a4d7  mov     rdx, rbx
0x14001a4da  lea     rcx, [rbp+57h+var_88]
0x14001a4de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14001a4e3  mov     rdx, rdi
0x14001a4e6  lea     rcx, [rbp+57h+var_68]
0x14001a4ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14001a4ef  mov     rcx, [r9]
0x14001a4f2  mov     [rbp+57h+var_48], rcx
0x14001a4f6  mov     rax, [r9+8]
0x14001a4fa  mov     [rbp+57h+var_40], rax
0x14001a4fe  mov     qword ptr [r9], 0
0x14001a505  mov     qword ptr [r9+8], 0
0x14001a50d  mov     [rbp+57h+var_38], r8b
0x14001a511  mov     rax, [rsi]
0x14001a514  mov     rbx, [rax]
0x14001a517  mov     [rbp+57h+var_C0], 3
0x14001a51e  mov     [rbp+57h+var_BC], 80h
0x14001a526  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001a52d  mov     ecx, 78h ; 'x'; unsigned __int64
0x14001a532  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001a537  mov     [rbp+57h+var_A8], rax
0x14001a53b  test    rax, rax
0x14001a53e  jz      short loc_14001A54D
0x14001a540  lea     rdx, [rbp+57h+var_90]
0x14001a544  mov     rcx, rax
0x14001a547  call    Windows__Internal__COperationLambdaVar_0__lambda_ff1938da65d60cabaa1a6e57ec4bb303__Windows__Internal__CBasicResult_enum_Windows__Internal__Security__SmartScreen__AppReputationResult_2_____COperationLambdaVar_0__lambda_ff1938da65d60cabaa1a6e57ec4bb303__Windows__Internal__CBasicResult_enum_Windows__Internal__Security__SmartScreen__AppReputationResult_2_____lambda_ff1938da65d60cabaa1a6e57ec4bb303___
0x14001a54c  nop
0x14001a54d  mov     [rsp+0F0h+var_D0], rax
0x14001a552  lea     r8, aWindowsFoundat_7; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x14001a559  lea     rdx, [rbp+57h+var_C0]
0x14001a55d  mov     rcx, rbx
0x14001a560  call    ??$MakeAsyncHelper@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@UINilDelegate@Internal@3@V?$CBasicResult@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@$01@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@$01@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<Windows::Internal::Security::SmartScreen::AppReputationResult,2>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<Windows::Internal::Security::SmartScreen::AppReputationResult,2>> *)
0x14001a565  mov     ebx, eax
0x14001a567  lea     rcx, [rbp+57h+var_90]
0x14001a56b  call    _lambda_ff1938da65d60cabaa1a6e57ec4bb303_____lambda_ff1938da65d60cabaa1a6e57ec4bb303_
0x14001a570  nop
0x14001a571  mov     rcx, [rbp+57h+var_98]; this
0x14001a575  test    rcx, rcx
0x14001a578  jz      short loc_14001A580
0x14001a57a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14001a57f  nop
0x14001a580  mov     rcx, r14
0x14001a583  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001a588  nop
0x14001a589  mov     rcx, r15
0x14001a58c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001a591  mov     eax, ebx
0x14001a593  mov     rcx, [rbp+57h+var_28]
0x14001a597  xor     rcx, rsp; StackCookie
0x14001a59a  call    __security_check_cookie
0x14001a59f  mov     rbx, [rsp+0F0h+arg_18]
0x14001a5a7  add     rsp, 0D0h
0x14001a5ae  pop     r15
0x14001a5b0  pop     r14
0x14001a5b2  pop     rdi
0x14001a5b3  pop     rsi
0x14001a5b4  pop     rbp
0x14001a5b5  retn
```
