# CallerIdentity::GetCoreWindowForCurrentThread(_GUID const &,void * *)

- ea: `0x180076014`
- end: `0x180076115`
- name: `?GetCoreWindowForCurrentThread@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007611c`

## callees

- `0x180022fb4`
- `0x18002b1b0`
- `0x180076014`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007606d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007606d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180076054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180076054`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007608e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007608e`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreWindowForCurrentThread(
        CallerIdentity *this,
        const struct _GUID *a2,
        void **a3)
{
  HSTRING v4; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, const struct _GUID *)); // rbx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, const struct _GUID *); // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF

  *(_QWORD *)&a2->Data1 = 0;
  v10 = 0;
  if ( WindowsCreateStringReference(L"Windows.UI.Core.CoreWindow", 0x1Au, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v10);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v10);
  if ( ActivationFactory >= 0 )
  {
    v6 = v10;
    v9 = 0;
    v7 = *(void (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, const struct _GUID *)))(*(_QWORD *)v10 + 48LL);
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v9);
    v7(v6, &v9);
    if ( v9 )
      ActivationFactory = (**v9)(v9, &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f, a2);
    else
      ActivationFactory = -2147023728;
    Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v9);
  }
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v10);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180076014  push    rbp
0x180076016  push    rbx
0x180076017  push    rsi
0x180076018  push    rdi
0x180076019  mov     rbp, rsp
0x18007601c  sub     rsp, 68h
0x180076020  mov     rax, cs:__security_cookie
0x180076027  xor     rax, rsp
0x18007602a  mov     [rbp+var_18], rax
0x18007602e  mov     rsi, rdx
0x180076031  mov     qword ptr [rdx], 0
0x180076038  mov     edx, 1Ah; length
0x18007603d  mov     [rbp+var_40], 0
0x180076045  lea     r9, [rbp+string]; string
0x180076049  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18007604d  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x180076054  call    cs:__imp_WindowsCreateStringReference
0x18007605a  test    eax, eax
0x18007605c  jns     short loc_180076073
0x18007605e  xor     r9d, r9d; lpArguments
0x180076061  xor     r8d, r8d; nNumberOfArguments
0x180076064  mov     ecx, 0C000000Dh; dwExceptionCode
0x180076069  lea     edx, [r9+1]; dwExceptionFlags
0x18007606d  call    cs:__imp_RaiseException
0x180076073  mov     rbx, [rbp+string]
0x180076077  lea     rcx, [rbp+var_40]
0x18007607b  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x180076080  lea     r8, [rbp+var_40]
0x180076084  mov     rcx, rbx
0x180076087  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x18007608e  call    cs:__imp_RoGetActivationFactory
0x180076094  mov     ebx, eax
0x180076096  test    eax, eax
0x180076098  js      short loc_1800760F5
0x18007609a  mov     rdi, [rbp+var_40]
0x18007609e  lea     rcx, [rbp+var_48]
0x1800760a2  mov     [rbp+var_48], 0
0x1800760aa  mov     rax, [rdi]
0x1800760ad  mov     rbx, [rax+30h]
0x1800760b1  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800760b6  lea     rdx, [rbp+var_48]
0x1800760ba  mov     rcx, rdi
0x1800760bd  mov     rax, rbx
0x1800760c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760c5  mov     rcx, [rbp+var_48]
0x1800760c9  test    rcx, rcx
0x1800760cc  jnz     short loc_1800760D5
0x1800760ce  mov     ebx, 80070490h
0x1800760d3  jmp     short loc_1800760EC
0x1800760d5  mov     rax, [rcx]
0x1800760d8  lea     rdx, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x1800760df  mov     r8, rsi
0x1800760e2  mov     rax, [rax]
0x1800760e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760ea  mov     ebx, eax
0x1800760ec  lea     rcx, [rbp+var_48]
0x1800760f0  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800760f5  lea     rcx, [rbp+var_40]
0x1800760f9  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800760fe  mov     eax, ebx
0x180076100  mov     rcx, [rbp+var_18]
0x180076104  xor     rcx, rsp; StackCookie
0x180076107  call    __security_check_cookie
0x18007610c  add     rsp, 68h
0x180076110  pop     rdi
0x180076111  pop     rsi
0x180076112  pop     rbx
0x180076113  pop     rbp
0x180076114  retn
```
