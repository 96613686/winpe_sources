# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::UI::Core::CoreAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)

- ea: `0x180021b70`
- end: `0x180021cb9`
- name: `?Start@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CoreAsyncActionName@Core@UI@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ`
- size: `329`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180021b70`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180021bf4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180021bf4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021cb2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021c2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021c2f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180021c9d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180021c9d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::UI::Core::CoreAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(
        __int64 a1)
{
  signed __int32 v1; // edx
  signed __int32 v3; // eax
  int v4; // ebx
  __int64 v5; // rsi
  __int64 v6; // rbp
  HRESULT v7; // eax
  void (__fastcall *v8)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64); // rax
  signed __int32 v10[4]; // [rsp+40h] [rbp-78h] BYREF
  GUID v11; // [rsp+50h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-58h] BYREF
  HSTRING string; // [rsp+78h] [rbp-40h] BYREF

  v1 = *(_DWORD *)(a1 + 56);
  v10[0] = -2;
  _InterlockedCompareExchange(v10, v1, -2);
  if ( v10[0] == -1 && (v3 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), 0, -1), v3 == v10[0]) )
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 136LL))(a1);
    if ( v4 >= 0
      && InitOnceExecuteOnce(
           &Microsoft::WRL::gCausalityInitOnce,
           Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality,
           0,
           0)
      && Microsoft::WRL::gCausality )
    {
      v5 = *(_QWORD *)Microsoft::WRL::gCausality;
      v6 = *(unsigned int *)(a1 + 64);
      string = 0;
      v7 = WindowsCreateStringReference(
             L"Windows.Foundation.IAsyncAction Windows.UI.Core.CoreDispatcher",
             0x3Eu,
             &hstringHeader,
             &string);
      if ( v7 < 0 )
      {
        RaiseException(v7, 1u, 0, 0);
        JUMPOUT(0x180021CB8LL);
      }
      v8 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, HSTRING, __int64))(v5 + 48);
      v11 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v8(Microsoft::WRL::gCausality, 0, 2, &v11, a1, string, v6);
    }
  }
  else
  {
    v4 = -2147483635;
    RoOriginateError(2147483661LL, 0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180021b70  push    rbx
0x180021b72  push    rbp
0x180021b73  push    rsi
0x180021b74  push    rdi
0x180021b75  sub     rsp, 98h
0x180021b7c  mov     rax, cs:__security_cookie
0x180021b83  xor     rax, rsp
0x180021b86  mov     [rsp+0B8h+var_38], rax
0x180021b8e  mov     edx, [rcx+38h]
0x180021b91  mov     rdi, rcx
0x180021b94  mov     [rsp+0B8h+var_78], 0FFFFFFFEh
0x180021b9c  mov     eax, [rsp+0B8h+var_78]
0x180021ba0  lock cmpxchg [rsp+0B8h+var_78], edx
0x180021ba6  cmp     [rsp+0B8h+var_78], 0FFFFFFFFh
0x180021bab  jnz     loc_180021C94
0x180021bb1  xor     edx, edx
0x180021bb3  mov     eax, 0FFFFFFFFh
0x180021bb8  lock cmpxchg [rcx+38h], edx
0x180021bbd  cmp     eax, [rsp+0B8h+var_78]
0x180021bc1  jnz     loc_180021C94
0x180021bc7  mov     rax, [rcx]
0x180021bca  mov     rax, [rax+88h]
0x180021bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021bd6  mov     ebx, eax
0x180021bd8  test    eax, eax
0x180021bda  js      loc_180021C76
0x180021be0  xor     r9d, r9d; Context
0x180021be3  lea     rdx, ?InitCausality@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180021bea  xor     r8d, r8d; Parameter
0x180021bed  lea     rcx, ?gCausalityInitOnce@WRL@Microsoft@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180021bf4  call    cs:__imp_InitOnceExecuteOnce
0x180021bfa  test    eax, eax
0x180021bfc  jz      short loc_180021C76
0x180021bfe  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180021c05  test    rax, rax
0x180021c08  jz      short loc_180021C76
0x180021c0a  mov     rsi, [rax]
0x180021c0d  lea     r9, [rsp+0B8h+string]; string
0x180021c12  mov     ebp, [rdi+40h]
0x180021c15  lea     r8, [rsp+0B8h+hstringHeader]; hstringHeader
0x180021c1a  mov     edx, 3Eh ; '>'; length
0x180021c1f  mov     [rsp+0B8h+string], 0
0x180021c28  lea     rcx, ?CoreAsyncActionName@Core@UI@Windows@@3QBGB; "Windows.Foundation.IAsyncAction Windows"...
0x180021c2f  call    cs:__imp_WindowsCreateStringReference
0x180021c35  test    eax, eax
0x180021c37  js      short loc_180021CA5
0x180021c39  mov     rcx, [rsp+0B8h+string]
0x180021c3e  lea     r9, [rsp+0B8h+var_68]
0x180021c43  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180021c4a  mov     rax, [rsi+30h]
0x180021c4e  xor     edx, edx
0x180021c50  mov     [rsp+0B8h+var_88], rbp
0x180021c55  mov     r8d, 2
0x180021c5b  mov     [rsp+0B8h+var_90], rcx
0x180021c60  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180021c67  movaps  [rsp+0B8h+var_68], xmm0
0x180021c6c  mov     [rsp+0B8h+var_98], rdi
0x180021c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c76  mov     eax, ebx
0x180021c78  mov     rcx, [rsp+0B8h+var_38]
0x180021c80  xor     rcx, rsp; StackCookie
0x180021c83  call    __security_check_cookie
0x180021c88  add     rsp, 98h
0x180021c8f  pop     rdi
0x180021c90  pop     rsi
0x180021c91  pop     rbp
0x180021c92  pop     rbx
0x180021c93  retn
0x180021c94  mov     ebx, 8000000Dh
0x180021c99  xor     edx, edx
0x180021c9b  mov     ecx, ebx
0x180021c9d  call    cs:__imp_RoOriginateError
0x180021ca3  jmp     short loc_180021C76
0x180021ca5  xor     r9d, r9d; lpArguments
0x180021ca8  xor     r8d, r8d; nNumberOfArguments
0x180021cab  mov     edx, 1; dwExceptionFlags
0x180021cb0  mov     ecx, eax; dwExceptionCode
0x180021cb2  call    cs:__imp_RaiseException
```
