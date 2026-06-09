# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)

- ea: `0x140007df8`
- end: `0x140007e56`
- name: `?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ`
- size: `94`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007c30`
- `0x140008540`
- `0x14001e390`
- `0x140020230`
- `0x140021a60`
- `0x140022300`
- `0x140035370`
- `0x1400353f0`
- `0x140035470`
- `0x1400354f0`
- `0x140035bc0`
- `0x140038ce0`
- `0x14003f4b0`
- `0x14003f530`

## callees

- `0x140007df8`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140007e2e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140007e2e`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(
        __int64 a1)
{
  signed __int32 v1; // ecx
  signed __int32 v3; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_DWORD *)(a1 + 56);
  v3 = -2;
  _InterlockedCompareExchange(&v3, v1, -2);
  if ( v3 != 4 )
    return 0;
  RoOriginateError(2147483662LL, 0);
  return 2147483662LL;
}

```

## disassembly

```asm
0x140007df8  sub     rsp, 38h
0x140007dfc  mov     rax, cs:__security_cookie
0x140007e03  xor     rax, rsp
0x140007e06  mov     [rsp+38h+var_10], rax
0x140007e0b  mov     ecx, [rcx+38h]
0x140007e0e  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x140007e16  mov     eax, [rsp+38h+var_18]
0x140007e1a  lock cmpxchg [rsp+38h+var_18], ecx
0x140007e20  cmp     [rsp+38h+var_18], 4
0x140007e25  jnz     short loc_140007E41
0x140007e27  xor     edx, edx
0x140007e29  mov     ecx, 8000000Eh
0x140007e2e  call    cs:__imp_RoOriginateError
0x140007e35  nop     dword ptr [rax+rax+00h]
0x140007e3a  mov     eax, 8000000Eh
0x140007e3f  jmp     short loc_140007E43
0x140007e41  xor     eax, eax
0x140007e43  mov     rcx, [rsp+38h+var_10]
0x140007e48  xor     rcx, rsp; StackCookie
0x140007e4b  call    __security_check_cookie
0x140007e50  add     rsp, 38h
0x140007e54  retn
```
