# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::ErrorCode(long *)

- ea: `0x14001ca80`
- end: `0x14001caed`
- name: `?ErrorCode@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXPEAJ@Z`
- size: `109`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000e320`
- `0x14000f870`
- `0x140013cc0`
- `0x14001c060`
- `0x140035560`
- `0x140035620`
- `0x1400361d0`
- `0x140036270`
- `0x1400378c0`
- `0x140038d60`
- `0x14003f5b0`

## callees

- `0x14001ca80`
- `0x140026c20`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x14001cace`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x14001cace`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::ErrorCode(
        __int64 a1,
        volatile signed __int32 *a2)
{
  __int64 v2; // r8
  __int64 result; // rax
  __int64 v5; // rcx
  signed __int32 v6; // [rsp+20h] [rbp-18h] BYREF

  v2 = *(unsigned int *)(a1 + 56);
  v6 = -2;
  result = (unsigned int)_InterlockedCompareExchange(&v6, v2, -2);
  if ( v6 == 3 )
  {
    result = (unsigned int)_InterlockedCompareExchange(a2, *(_DWORD *)(a1 + 60), *a2);
    v5 = *(_QWORD *)(a1 + 48);
    if ( v5 )
      return SetRestrictedErrorInfo(v5, a2, v2, a1);
  }
  else
  {
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14001ca80  sub     rsp, 38h
0x14001ca84  mov     rax, cs:__security_cookie
0x14001ca8b  xor     rax, rsp
0x14001ca8e  mov     [rsp+38h+var_10], rax
0x14001ca93  mov     r8d, [rcx+38h]
0x14001ca97  mov     r9, rcx
0x14001ca9a  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x14001caa2  mov     eax, [rsp+38h+var_18]
0x14001caa6  lock cmpxchg [rsp+38h+var_18], r8d
0x14001caad  cmp     [rsp+38h+var_18], 3
0x14001cab2  jz      short loc_14001CABC
0x14001cab4  mov     dword ptr [rdx], 0
0x14001caba  jmp     short loc_14001CADA
0x14001cabc  mov     eax, [rdx]
0x14001cabe  mov     ecx, [rcx+3Ch]
0x14001cac1  lock cmpxchg [rdx], ecx
0x14001cac5  mov     rcx, [r9+30h]
0x14001cac9  test    rcx, rcx
0x14001cacc  jz      short loc_14001CADA
0x14001cace  call    cs:__imp_SetRestrictedErrorInfo
0x14001cad5  nop     dword ptr [rax+rax+00h]
0x14001cada  mov     rcx, [rsp+38h+var_10]
0x14001cadf  xor     rcx, rsp; StackCookie
0x14001cae2  call    __security_check_cookie
0x14001cae7  add     rsp, 38h
0x14001caeb  retn
```
