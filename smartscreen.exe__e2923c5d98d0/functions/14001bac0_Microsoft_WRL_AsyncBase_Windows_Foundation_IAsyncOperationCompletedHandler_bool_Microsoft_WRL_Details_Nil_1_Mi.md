# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::ErrorCode(long *)

- ea: `0x14001bac0`
- end: `0x14001bb26`
- name: `?ErrorCode@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXPEAJ@Z`
- size: `102`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000dbf0`
- `0x14000f030`
- `0x1400131e0`
- `0x14001b1b0`
- `0x140034070`
- `0x140034120`
- `0x140034cc0`
- `0x140034d60`
- `0x1400363a0`
- `0x1400377f0`
- `0x14003dea0`

## callees

- `0x14001bac0`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x14001bb0e`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x14001bb0e`

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
0x14001bac0  sub     rsp, 38h
0x14001bac4  mov     rax, cs:__security_cookie
0x14001bacb  xor     rax, rsp
0x14001bace  mov     [rsp+38h+var_10], rax
0x14001bad3  mov     r8d, [rcx+38h]
0x14001bad7  mov     r9, rcx
0x14001bada  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x14001bae2  mov     eax, [rsp+38h+var_18]
0x14001bae6  lock cmpxchg [rsp+38h+var_18], r8d
0x14001baed  cmp     [rsp+38h+var_18], 3
0x14001baf2  jz      short loc_14001BAFC
0x14001baf4  mov     dword ptr [rdx], 0
0x14001bafa  jmp     short loc_14001BB14
0x14001bafc  mov     eax, [rdx]
0x14001bafe  mov     ecx, [rcx+3Ch]
0x14001bb01  lock cmpxchg [rdx], ecx
0x14001bb05  mov     rcx, [r9+30h]
0x14001bb09  test    rcx, rcx
0x14001bb0c  jz      short loc_14001BB14
0x14001bb0e  call    cs:__imp_SetRestrictedErrorInfo
0x14001bb14  mov     rcx, [rsp+38h+var_10]
0x14001bb19  xor     rcx, rsp; StackCookie
0x14001bb1c  call    __security_check_cookie
0x14001bb21  add     rsp, 38h
0x14001bb25  retn
```
