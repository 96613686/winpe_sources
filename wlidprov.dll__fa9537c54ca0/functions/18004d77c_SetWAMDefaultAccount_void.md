# SetWAMDefaultAccount(void)

- ea: `0x18004d77c`
- end: `0x18004d9e6`
- name: `?SetWAMDefaultAccount@@YAJXZ`
- size: `618`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180026a1c`

## callees

- `0x180016758`
- `0x18001a0d0`
- `0x18002ae68`
- `0x180037c98`
- `0x180037ce4`
- `0x18004cfb0`
- `0x18004cffc`
- `0x18004d258`
- `0x18004d398`
- `0x18004d77c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d869`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004d869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004d850`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004d7f7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004d7f7`

## string_xrefs

- `0x18004d873`: `https://login.microsoft.com`
- `0x18004d7cd`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SetWAMDefaultAccount(__int64 a1, const unsigned __int16 *a2)
{
  _QWORD *v2; // rax
  int ActivationFactory; // eax
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, HSTRING, __int64 *); // rsi
  HSTRING v9; // rbx
  _QWORD *v10; // rax
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  int v18; // [rsp+20h] [rbp-49h]
  __int64 v19; // [rsp+30h] [rbp-39h] BYREF
  __int64 v20; // [rsp+38h] [rbp-31h] BYREF
  __int64 v21; // [rsp+40h] [rbp-29h] BYREF
  __int64 v22; // [rsp+48h] [rbp-21h] BYREF
  __int64 v23; // [rsp+50h] [rbp-19h] BYREF
  HSTRING string; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  HSTRING v26; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v23 = 0;
  v22 = 0;
  v2 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[65])a2);
  ActivationFactory = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
                        *v2,
                        &v23);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v5 = 43;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\wamdefaultaccount\\wamdefaultaccount.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v18);
    goto LABEL_22;
  }
  v6 = *(_QWORD *)Windows::Internal::StringReference::StringReference(
                    &string,
                    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager");
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v22);
  v4 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v5 = 44;
    goto LABEL_5;
  }
  v19 = 0;
  v7 = v22;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v22 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  if ( WindowsCreateStringReference(L"consumers", 9u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = string;
  v10 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v26, L"https://login.microsoft.com");
  v11 = v8(v7, *v10, v9, &v19);
  v4 = v11;
  if ( v11 >= 0 )
  {
    v20 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v12 = v19;
    v4 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(v19);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 64LL))(v12, &v20);
    if ( v4 >= 0 )
    {
      v21 = 0;
      v13 = v23;
      v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 240LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      v15 = v14(v13, v20, 0, &v21);
      v4 = v15;
      if ( v15 >= 0 )
      {
        v15 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v21);
        v4 = v15;
        if ( v15 >= 0 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
          v4 = 0;
          goto LABEL_22;
        }
        v16 = 58;
      }
      else
      {
        v16 = 57;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\wamdefaultaccount\\wamdefaultaccount.cpp",
        (const char *)(unsigned int)v15,
        v18);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\wamdefaultaccount\\wamdefaultaccount.cpp",
        (const char *)(unsigned int)v4,
        v18);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\lib\\wamdefaultaccount\\wamdefaultaccount.cpp",
      (const char *)(unsigned int)v11,
      v18);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
LABEL_22:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004d77c  push    rbp
0x18004d77e  push    rbx
0x18004d77f  push    rsi
0x18004d780  push    rdi
0x18004d781  lea     rbp, [rsp-3Fh]
0x18004d786  sub     rsp, 0A8h
0x18004d78d  mov     rax, cs:__security_cookie
0x18004d794  xor     rax, rsp
0x18004d797  mov     [rbp+57h+var_28], rax
0x18004d79b  mov     [rbp+57h+var_70], 0
0x18004d7a3  mov     [rbp+57h+var_78], 0
0x18004d7ab  lea     rcx, [rbp+57h+string]; string
0x18004d7af  call    ??$?0$0EB@@StringReference@Internal@Windows@@QEAA@AEAY0EB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[65])
0x18004d7b4  lea     rdx, [rbp+57h+var_70]
0x18004d7b8  mov     rcx, [rax]
0x18004d7bb  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x18004d7c0  mov     ebx, eax
0x18004d7c2  test    eax, eax
0x18004d7c4  jns     short loc_18004D7CD
0x18004d7c6  mov     edx, 2Bh ; '+'
0x18004d7cb  jmp     short loc_18004D808
0x18004d7cd  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18004d7d4  lea     rcx, [rbp+57h+string]; string
0x18004d7d8  call    ??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[70])
0x18004d7dd  mov     rbx, [rax]
0x18004d7e0  lea     rcx, [rbp+57h+var_78]
0x18004d7e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d7e9  lea     r8, [rbp+57h+var_78]
0x18004d7ed  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x18004d7f4  mov     rcx, rbx
0x18004d7f7  call    cs:__imp_RoGetActivationFactory
0x18004d7fd  mov     ebx, eax
0x18004d7ff  test    eax, eax
0x18004d801  jns     short loc_18004D820
0x18004d803  mov     edx, 2Ch ; ','; void *
0x18004d808  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d80f  mov     r9d, eax; char *
0x18004d812  mov     rcx, [rbp+5Fh]; this
0x18004d816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d81b  jmp     loc_18004D9B9
0x18004d820  mov     [rbp+57h+var_90], 0
0x18004d828  mov     rdi, [rbp+57h+var_78]
0x18004d82c  mov     rax, [rdi]
0x18004d82f  mov     rsi, [rax+60h]
0x18004d833  lea     rcx, [rbp+57h+var_90]
0x18004d837  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d83c  lea     r9, [rbp+57h+string]; string
0x18004d840  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18004d844  mov     edx, 9; length
0x18004d849  lea     rcx, sourceString; "consumers"
0x18004d850  call    cs:__imp_WindowsCreateStringReference
0x18004d856  test    eax, eax
0x18004d858  jns     short loc_18004D86F
0x18004d85a  xor     r9d, r9d; lpArguments
0x18004d85d  xor     r8d, r8d; nNumberOfArguments
0x18004d860  lea     edx, [r9+1]; dwExceptionFlags
0x18004d864  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004d869  call    cs:__imp_RaiseException
0x18004d86f  mov     rbx, [rbp+57h+string]
0x18004d873  lea     rdx, aHttpsLoginMicr; "https://login.microsoft.com"
0x18004d87a  lea     rcx, [rbp+57h+var_48]; string
0x18004d87e  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x18004d883  lea     r9, [rbp+57h+var_90]
0x18004d887  mov     r8, rbx
0x18004d88a  mov     rdx, [rax]
0x18004d88d  mov     rcx, rdi
0x18004d890  mov     rax, rsi
0x18004d893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d898  mov     ebx, eax
0x18004d89a  test    eax, eax
0x18004d89c  jns     short loc_18004D8C5
0x18004d89e  mov     rcx, [rbp+5Fh]; this
0x18004d8a2  mov     r9d, eax; char *
0x18004d8a5  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d8ac  mov     edx, 32h ; '2'; void *
0x18004d8b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d8b6  nop
0x18004d8b7  lea     rcx, [rbp+57h+var_90]
0x18004d8bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d8c0  jmp     loc_18004D9B9
0x18004d8c5  mov     [rbp+57h+var_88], 0
0x18004d8cd  lea     rcx, [rbp+57h+var_88]
0x18004d8d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d8d6  mov     rdi, [rbp+57h+var_90]
0x18004d8da  mov     rcx, rdi
0x18004d8dd  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18004d8e2  mov     ebx, eax
0x18004d8e4  test    eax, eax
0x18004d8e6  js      short loc_18004D8FD
0x18004d8e8  mov     rax, [rdi]
0x18004d8eb  lea     rdx, [rbp+57h+var_88]
0x18004d8ef  mov     rcx, rdi
0x18004d8f2  mov     rax, [rax+40h]
0x18004d8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8fb  mov     ebx, eax
0x18004d8fd  test    ebx, ebx
0x18004d8ff  jns     short loc_18004D925
0x18004d901  mov     rcx, [rbp+5Fh]; this
0x18004d905  mov     r9d, ebx; char *
0x18004d908  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d90f  mov     edx, 35h ; '5'; void *
0x18004d914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d919  nop
0x18004d91a  lea     rcx, [rbp+57h+var_88]
0x18004d91e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d923  jmp     short loc_18004D8B7
0x18004d925  mov     [rbp+57h+var_80], 0
0x18004d92d  mov     rdi, [rbp+57h+var_70]
0x18004d931  mov     rax, [rdi]
0x18004d934  mov     rbx, [rax+0F0h]
0x18004d93b  lea     rcx, [rbp+57h+var_80]
0x18004d93f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d944  lea     r9, [rbp+57h+var_80]
0x18004d948  xor     r8d, r8d
0x18004d94b  mov     rdx, [rbp+57h+var_88]
0x18004d94f  mov     rcx, rdi
0x18004d952  mov     rax, rbx
0x18004d955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d95a  mov     ebx, eax
0x18004d95c  test    eax, eax
0x18004d95e  jns     short loc_18004D984
0x18004d960  mov     edx, 39h ; '9'; void *
0x18004d965  lea     r8, aOnecoreuapDsEx_4; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18004d96c  mov     r9d, eax; char *
0x18004d96f  mov     rcx, [rbp+5Fh]; this
0x18004d973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d978  nop
0x18004d979  lea     rcx, [rbp+57h+var_80]
0x18004d97d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d982  jmp     short loc_18004D91A
0x18004d984  mov     rcx, [rbp+57h+var_80]
0x18004d988  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x18004d98d  mov     ebx, eax
0x18004d98f  test    eax, eax
0x18004d991  jns     short loc_18004D99A
0x18004d993  mov     edx, 3Ah ; ':'
0x18004d998  jmp     short loc_18004D965
0x18004d99a  lea     rcx, [rbp+57h+var_80]
0x18004d99e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9a3  nop
0x18004d9a4  lea     rcx, [rbp+57h+var_88]
0x18004d9a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9ad  nop
0x18004d9ae  lea     rcx, [rbp+57h+var_90]
0x18004d9b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9b7  xor     ebx, ebx
0x18004d9b9  lea     rcx, [rbp+57h+var_78]
0x18004d9bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9c2  nop
0x18004d9c3  lea     rcx, [rbp+57h+var_70]
0x18004d9c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d9cc  mov     eax, ebx
0x18004d9ce  mov     rcx, [rbp+57h+var_28]
0x18004d9d2  xor     rcx, rsp; StackCookie
0x18004d9d5  call    __security_check_cookie
0x18004d9da  add     rsp, 0A8h
0x18004d9e1  pop     rdi
0x18004d9e2  pop     rsi
0x18004d9e3  pop     rbx
0x18004d9e4  pop     rbp
0x18004d9e5  retn
```
