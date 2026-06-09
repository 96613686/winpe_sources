# wil::details::RunWhenComplete_IUnknown_Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_____lambda_6a73db1c48dc126f1224b85b4c582466___

- ea: `0x1800133e4`
- end: `0x180013480`
- name: `wil::details::RunWhenComplete_IUnknown_Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_____lambda_6a73db1c48dc126f1224b85b4c582466___`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014fc0`

## callees

- `0x18000b924`
- `0x180012cf0`
- `0x1800133e4`
- `0x1800186c0`
- `0x180029010`

## string_xrefs

- `0x18001343b`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details::RunWhenComplete_IUnknown_Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_____lambda_6a73db1c48dc126f1224b85b4c582466___(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rdi
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = *a2;
  v3 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_::___Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult____enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_enum_Windows::Internal::Security::SmartScreen::AppReputationResult__IUnknown___lambda_9561cba1c609edf37800408a549a8f14___1_Windows::Foundation::IAsyncOperation_enum_Windows::Internal::Security::SmartScreen::AppReputationResult____enum_ABI::Windows::Foundation::AsyncStatus___lambda_9561cba1c609edf37800408a549a8f14___(
                    &v9,
                    &v10);
  v4 = *v3;
  *v3 = 0;
  if ( v9 )
  {
    v9 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::Release();
  }
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 48LL))(a1, v4);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  else
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)0x8007000ELL,
      v7);
  }
  return v5;
}

```

## disassembly

```asm
0x1800133e4  mov     r11, rsp
0x1800133e7  mov     [r11+8], rbx
0x1800133eb  push    rdi; int
0x1800133ec  sub     rsp, 20h
0x1800133f0  mov     rbx, rcx
0x1800133f3  mov     rax, [rdx]
0x1800133f6  mov     [r11+18h], rax
0x1800133fa  lea     rdx, [r11+18h]
0x1800133fe  lea     rcx, [r11+10h]
0x180013402  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_enum_Windows__Internal__Security__SmartScreen__AppReputationResult______Windows__Foundation__IAsyncOperation_enum_Windows__Internal__Security__SmartScreen__AppReputationResult____enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__IAsyncOperationCompletedHandler_enum_Windows__Internal__Security__SmartScreen__AppReputationResult__IUnknown___lambda_9561cba1c609edf37800408a549a8f14___1_Windows__Foundation__IAsyncOperation_enum_Windows__Internal__Security__SmartScreen__AppReputationResult____enum_ABI__Windows__Foundation__AsyncStatus___lambda_9561cba1c609edf37800408a549a8f14___
0x180013407  mov     rdi, [rax]
0x18001340a  mov     qword ptr [rax], 0
0x180013411  mov     rcx, [rsp+28h+arg_8]
0x180013416  test    rcx, rcx
0x180013419  jz      short loc_180013429
0x18001341b  mov     [rsp+28h+arg_8], 0
0x180013424  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UIUnknown@@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,IUnknown>>::Release(void)
0x180013429  test    rdi, rdi
0x18001342c  jnz     short loc_18001344F
0x18001342e  mov     rcx, [rsp+28h]; this
0x180013433  mov     ebx, 8007000Eh
0x180013438  mov     r9d, ebx; char *
0x18001343b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013442  mov     edx, 61Bh; void *
0x180013447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001344c  nop
0x18001344d  jmp     short loc_180013473
0x18001344f  mov     rax, [rbx]
0x180013452  mov     rdx, rdi
0x180013455  mov     rcx, rbx
0x180013458  mov     rax, [rax+30h]
0x18001345c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013461  mov     ebx, eax
0x180013463  mov     rdx, [rdi]
0x180013466  mov     rcx, rdi
0x180013469  mov     rax, [rdx+10h]
0x18001346d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013472  nop
0x180013473  mov     eax, ebx
0x180013475  mov     rbx, [rsp+28h+arg_0]
0x18001347a  add     rsp, 20h
0x18001347e  pop     rdi
0x18001347f  retn
```
