# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)

- ea: `0x140007a18`
- end: `0x140007a6f`
- name: `?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ`
- size: `87`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007860`
- `0x140008130`
- `0x14001d390`
- `0x14001f110`
- `0x140020910`
- `0x1400211a0`
- `0x140033eb0`
- `0x140033f20`
- `0x140033f90`
- `0x140034000`
- `0x1400346b0`
- `0x140037780`
- `0x14003ddc0`
- `0x14003de30`

## callees

- `0x140007a18`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140007a4e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140007a4e`

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
0x140007a18  sub     rsp, 38h
0x140007a1c  mov     rax, cs:__security_cookie
0x140007a23  xor     rax, rsp
0x140007a26  mov     [rsp+38h+var_10], rax
0x140007a2b  mov     ecx, [rcx+38h]
0x140007a2e  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x140007a36  mov     eax, [rsp+38h+var_18]
0x140007a3a  lock cmpxchg [rsp+38h+var_18], ecx
0x140007a40  cmp     [rsp+38h+var_18], 4
0x140007a45  jnz     short loc_140007A5B
0x140007a47  xor     edx, edx
0x140007a49  mov     ecx, 8000000Eh
0x140007a4e  call    cs:__imp_RoOriginateError
0x140007a54  mov     eax, 8000000Eh
0x140007a59  jmp     short loc_140007A5D
0x140007a5b  xor     eax, eax
0x140007a5d  mov     rcx, [rsp+38h+var_10]
0x140007a62  xor     rcx, rsp; StackCookie
0x140007a65  call    __security_check_cookie
0x140007a6a  add     rsp, 38h
0x140007a6e  retn
```
