# Windows::System::Internal::WCOS::WCOSUserManager::RuntimeClassInitialize(void)

- ea: `0x18006a690`
- end: `0x18006a930`
- name: `?RuntimeClassInitialize@WCOSUserManager@WCOS@Internal@System@Windows@@QEAAJXZ`
- size: `672`
- prototype: `__int64 __fastcall(Windows::System::Internal::WCOS::WCOSUserManager *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180062d2c`

## callees

- `0x180005670`
- `0x18000acdc`
- `0x18000ce48`
- `0x18003b578`
- `0x18004e508`
- `0x180053568`
- `0x18006a538`
- `0x18006a690`
- `0x18006a938`
- `0x18006ab4c`
- `0x1800a744c`
- `0x1800a751c`
- `0x1800a769c`
- `0x1800ada10`
- `0x1800b76d0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a6fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006a6fa`
- `SHCORE!SHTaskPoolQueueTask` at `0x18006a71c`
- `SHCORE!SHTaskPoolQueueTask` at `0x18006a71c`

## string_xrefs

- `0x18006a6b4`: `onecore\ds\security\umstartup\usermgr\lib\wcosusermanager.cpp`
- `0x18006a745`: `onecore\ds\security\umstartup\usermgr\lib\wcosusermanager.cpp`
- `0x18006a7b5`: `onecore\ds\security\umstartup\usermgr\lib\wcosusermanager.cpp`
- `0x18006a80c`: `onecore\ds\security\umstartup\usermgr\lib\wcosusermanager.cpp`
- `0x18006a847`: `onecore\ds\security\umstartup\usermgr\lib\wcosusermanager.cpp`
- `0x18006a8d6`: `onecore\ds\security\umstartup\usermgr\lib\wcosusermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::System::Internal::WCOS::WCOSUserManager::RuntimeClassInitialize(
        Windows::System::Internal::WCOS::WCOSUserManager *this)
{
  bool v2; // al
  __int64 *v3; // rax
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  int v6; // esi
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, char *); // r14
  _QWORD *v9; // rcx
  int v10; // eax
  __int64 *v11; // rax
  const char *v12; // r9
  __int64 v13; // rbx
  int v14; // eax
  Windows::System::Internal::WCOS::WCOSUserManager **v15; // rax
  Windows::System::Internal::WCOS::WCOSUserManager *v16; // rbx
  int v17; // eax
  const char *v18; // r9
  __int64 result; // rax
  unsigned int v20; // [rsp+20h] [rbp-48h]
  int v21; // [rsp+20h] [rbp-48h]
  Windows::System::Internal::WCOS::WCOSUserManager *v22; // [rsp+30h] [rbp-38h] BYREF
  __int64 v23; // [rsp+38h] [rbp-30h] BYREF
  __int64 v24; // [rsp+40h] [rbp-28h] BYREF
  _QWORD v25[4]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v27; // [rsp+78h] [rbp+10h] BYREF
  __int64 v28; // [rsp+80h] [rbp+18h] BYREF
  __int64 v29; // [rsp+88h] [rbp+20h] BYREF

  v2 = IsWindowsCoreUserModelEnforced();
  try
  {
    if ( !v2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\wcosusermanager.cpp",
        (const char *)0x32,
        v20);
    v22 = this;
    v3 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_88862feb5430ac9b65bcbc5ad1dc82de_____lambda_88862feb5430ac9b65bcbc5ad1dc82de___(
                      &v27,
                      &v22);
    v4 = *v3;
    *v3 = 0;
    if ( v27 )
    {
      v27 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
    }
    CurrentThreadId = GetCurrentThreadId();
    v21 = v4;
    v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 250);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\wcosusermanager.cpp",
        (const char *)(unsigned int)v6,
        v4);
    Windows::System::Internal::WCOS::WCOSUserManager::GetResourceUserId(this);
    wil::GetActivationFactory<Windows::System::IUserStatics>((const WCHAR *)&v29);
    v7 = v29;
    v8 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v29 + 48LL);
    v9 = (_QWORD *)*((_QWORD *)this + 14);
    *((_QWORD *)this + 14) = 0;
    if ( v9 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v9 + 16LL))(v9, *v9);
    v10 = v8(v7, (char *)this + 112);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\wcosusermanager.cpp",
        (const char *)(unsigned int)v10,
        v21);
    v22 = this;
    v11 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::System::UserWatcher___Windows::System::IUserWatcher____Windows::Foundation::Internal::AggregateType_Windows::System::UserChangedEventArgs___Windows::System::IUserChangedEventArgs_____::___Windows::System::IUserWatcher___Windows::System::IUserChangedEventArgs____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::System::UserWatcher___Windows::System::UserChangedEventArgs____Microsoft::WRL::FtmBase___lambda_0ced93a5fe8e22ce3b3d6fada2c78e9f___1_Windows::System::IUserWatcher___Windows::System::IUserChangedEventArgs_____lambda_0ced93a5fe8e22ce3b3d6fada2c78e9f___(
                       &v27,
                       &v22);
    v13 = *v11;
    v25[0] = *v11;
    *v11 = 0;
    if ( v27 )
    {
      v27 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>,Microsoft::WRL::FtmBase>>::Release();
    }
    if ( !v13 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\wcosusermanager.cpp",
        v12);
    v23 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)this + 14) + 120LL))(
            *((_QWORD *)this + 14),
            v13,
            &v23);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\wcosusermanager.cpp",
        (const char *)(unsigned int)v14,
        v21);
    v22 = this;
    v15 = (Windows::System::Internal::WCOS::WCOSUserManager **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::System::Internal::UserDeletedEventArgs___Windows::System::Internal::IUserDeletedEventArgs_____::___IInspectable___Windows::System::Internal::IUserDeletedEventArgs____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IEventHandler_Windows::System::Internal::UserDeletedEventArgs____Microsoft::WRL::FtmBase___lambda_c45d00c516500c138de57c88f257a910___1_IInspectable___Windows::System::Internal::IUserDeletedEventArgs_____lambda_c45d00c516500c138de57c88f257a910___(
                                                                 &v27,
                                                                 &v22);
    v16 = *v15;
    v22 = *v15;
    *v15 = 0;
    if ( v27 )
    {
      v27 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>,Microsoft::WRL::FtmBase>>::Release();
    }
    wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics>((const WCHAR *)&v28);
    v24 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, Windows::System::Internal::WCOS::WCOSUserManager *, __int64 *))(*(_QWORD *)v28 + 128LL))(
            v28,
            v16,
            &v24);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\wcosusermanager.cpp",
        (const char *)(unsigned int)v17,
        v21);
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(&v29);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x91,
                           (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\wcosusermanager.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x18006a690  mov     [rsp+arg_0], rbx
0x18006a695  push    rsi
0x18006a696  push    rdi
0x18006a697  push    r14
0x18006a699  sub     rsp, 50h
0x18006a69d  mov     rdi, rcx
0x18006a6a0  call    ?IsWindowsCoreUserModelEnforced@@YA_NXZ; IsWindowsCoreUserModelEnforced(void)
0x18006a6a5  test    al, al
0x18006a6a7  jnz     short loc_18006A6C4
0x18006a6a9  mov     rcx, [rsp+68h]; this
0x18006a6ae  mov     r9d, 32h ; '2'; char *
0x18006a6b4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\umstartup\\userm"...
0x18006a6bb  lea     edx, [r9-6]; void *
0x18006a6bf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18006a6c4  mov     [rsp+68h+var_38], rdi
0x18006a6c9  lea     rdx, [rsp+68h+var_38]
0x18006a6ce  lea     rcx, [rsp+68h+arg_8]
0x18006a6d3  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_88862feb5430ac9b65bcbc5ad1dc82de_____lambda_88862feb5430ac9b65bcbc5ad1dc82de___
0x18006a6d8  mov     rbx, [rax]
0x18006a6db  mov     qword ptr [rax], 0
0x18006a6e2  mov     rcx, [rsp+68h+arg_8]
0x18006a6e7  test    rcx, rcx
0x18006a6ea  jz      short loc_18006A6FA
0x18006a6ec  mov     [rsp+68h+arg_8], 0
0x18006a6f5  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18006a6fa  call    cs:__imp_GetCurrentThreadId
0x18006a700  mov     [rsp+68h+var_40], 0
0x18006a709  mov     qword ptr [rsp+68h+var_48], rbx; int
0x18006a70e  mov     r9d, 0FAh
0x18006a714  mov     r8d, eax
0x18006a717  xor     edx, edx
0x18006a719  lea     ecx, [rdx+3]
0x18006a71c  call    cs:__imp_SHTaskPoolQueueTask
0x18006a722  mov     esi, eax
0x18006a724  test    rbx, rbx
0x18006a727  jz      short loc_18006A739
0x18006a729  mov     rdx, [rbx]
0x18006a72c  mov     rcx, rbx
0x18006a72f  mov     rax, [rdx+10h]
0x18006a733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a738  nop
0x18006a739  mov     rcx, [rsp+68h]; this
0x18006a73e  test    esi, esi
0x18006a740  jns     short loc_18006A756
0x18006a742  mov     r9d, esi; char *
0x18006a745  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\umstartup\\userm"...
0x18006a74c  mov     edx, 3Bh ; ';'; void *
0x18006a751  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a756  mov     rcx, rdi; this
0x18006a759  call    ?GetResourceUserId@WCOSUserManager@WCOS@Internal@System@Windows@@AEAAXXZ; Windows::System::Internal::WCOS::WCOSUserManager::GetResourceUserId(void)
0x18006a75e  lea     rcx, [rsp+68h+arg_18]
0x18006a766  call    ??$GetActivationFactory@UIUserStatics@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserStatics@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::IUserStatics>(ushort const *)
0x18006a76b  nop
0x18006a76c  mov     rbx, [rsp+68h+arg_18]
0x18006a774  mov     rax, [rbx]
0x18006a777  mov     r14, [rax+30h]
0x18006a77b  lea     rsi, [rdi+70h]
0x18006a77f  mov     rcx, [rsi]
0x18006a782  mov     qword ptr [rsi], 0
0x18006a789  test    rcx, rcx
0x18006a78c  jz      short loc_18006A79B
0x18006a78e  mov     rdx, [rcx]
0x18006a791  mov     rax, [rdx+10h]
0x18006a795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a79a  nop
0x18006a79b  mov     rdx, rsi
0x18006a79e  mov     rcx, rbx
0x18006a7a1  mov     rax, r14
0x18006a7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a7a9  mov     rcx, [rsp+68h]; this
0x18006a7ae  test    eax, eax
0x18006a7b0  jns     short loc_18006A7C6
0x18006a7b2  mov     r9d, eax; char *
0x18006a7b5  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\umstartup\\userm"...
0x18006a7bc  mov     edx, 42h ; 'B'; void *
0x18006a7c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a7c6  mov     [rsp+68h+var_38], rdi
0x18006a7cb  lea     rdx, [rsp+68h+var_38]
0x18006a7d0  lea     rcx, [rsp+68h+arg_8]
0x18006a7d5  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__System__UserWatcher___Windows__System__IUserWatcher____Windows__Foundation__Internal__AggregateType_Windows__System__UserChangedEventArgs___Windows__System__IUserChangedEventArgs__________Windows__System__IUserWatcher___Windows__System__IUserChangedEventArgs______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__System__UserWatcher___Windows__System__UserChangedEventArgs____Microsoft__WRL__FtmBase___lambda_0ced93a5fe8e22ce3b3d6fada2c78e9f___1_Windows__System__IUserWatcher___Windows__System__IUserChangedEventArgs_____lambda_0ced93a5fe8e22ce3b3d6fada2c78e9f___
0x18006a7da  mov     rbx, [rax]
0x18006a7dd  mov     [rsp+68h+var_20], rbx
0x18006a7e2  mov     qword ptr [rax], 0
0x18006a7e9  mov     rcx, [rsp+68h+arg_8]
0x18006a7ee  test    rcx, rcx
0x18006a7f1  jz      short loc_18006A802
0x18006a7f3  mov     [rsp+68h+arg_8], 0
0x18006a7fc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IEventHandler@PEAVUserDeletedEventArgs@Internal@System@Windows@@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>,Microsoft::WRL::FtmBase>>::Release(void)
0x18006a801  nop
0x18006a802  mov     rcx, [rsp+68h]; this
0x18006a807  test    rbx, rbx
0x18006a80a  jnz     short loc_18006A81B
0x18006a80c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\umstartup\\userm"...
0x18006a813  lea     edx, [rbx+6Fh]; void *
0x18006a816  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18006a81b  mov     [rsp+68h+var_30], 0
0x18006a824  mov     rcx, [rsi]
0x18006a827  mov     rax, [rcx]
0x18006a82a  lea     r8, [rsp+68h+var_30]
0x18006a82f  mov     rdx, rbx
0x18006a832  mov     rax, [rax+78h]
0x18006a836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a83b  mov     rcx, [rsp+68h]; this
0x18006a840  test    eax, eax
0x18006a842  jns     short loc_18006A858
0x18006a844  mov     r9d, eax; char *
0x18006a847  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\umstartup\\userm"...
0x18006a84e  mov     edx, 73h ; 's'; void *
0x18006a853  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a858  mov     [rsp+68h+var_38], rdi
0x18006a85d  lea     rdx, [rsp+68h+var_38]
0x18006a862  lea     rcx, [rsp+68h+arg_8]
0x18006a867  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__System__Internal__UserDeletedEventArgs___Windows__System__Internal__IUserDeletedEventArgs__________IInspectable___Windows__System__Internal__IUserDeletedEventArgs______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__IEventHandler_Windows__System__Internal__UserDeletedEventArgs____Microsoft__WRL__FtmBase___lambda_c45d00c516500c138de57c88f257a910___1_IInspectable___Windows__System__Internal__IUserDeletedEventArgs_____lambda_c45d00c516500c138de57c88f257a910___
0x18006a86c  mov     rbx, [rax]
0x18006a86f  mov     [rsp+68h+var_38], rbx
0x18006a874  mov     qword ptr [rax], 0
0x18006a87b  mov     rcx, [rsp+68h+arg_8]
0x18006a880  test    rcx, rcx
0x18006a883  jz      short loc_18006A894
0x18006a885  mov     [rsp+68h+arg_8], 0
0x18006a88e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IEventHandler@PEAVUserDeletedEventArgs@Internal@System@Windows@@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::Internal::UserDeletedEventArgs *>,Microsoft::WRL::FtmBase>>::Release(void)
0x18006a893  nop
0x18006a894  lea     rcx, [rsp+68h+arg_10]
0x18006a89c  call    ??$GetActivationFactory@UIUserManagerStatics@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UIUserManagerStatics@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::Internal::IUserManagerStatics>(ushort const *)
0x18006a8a1  nop
0x18006a8a2  mov     [rsp+68h+var_28], 0
0x18006a8ab  mov     rcx, [rsp+68h+arg_10]
0x18006a8b3  mov     rax, [rcx]
0x18006a8b6  lea     r8, [rsp+68h+var_28]
0x18006a8bb  mov     rdx, rbx
0x18006a8be  mov     rax, [rax+80h]
0x18006a8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a8ca  mov     rcx, [rsp+68h]; this
0x18006a8cf  test    eax, eax
0x18006a8d1  jns     short loc_18006A8E8
0x18006a8d3  mov     r9d, eax; char *
0x18006a8d6  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\umstartup\\userm"...
0x18006a8dd  mov     edx, 8Dh; void *
0x18006a8e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006a8e8  lea     rcx, [rsp+68h+arg_10]
0x18006a8f0  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x18006a8f5  nop
0x18006a8f6  lea     rcx, [rsp+68h+var_38]
0x18006a8fb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a900  nop
0x18006a901  lea     rcx, [rsp+68h+var_20]
0x18006a906  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a90b  nop
0x18006a90c  lea     rcx, [rsp+68h+arg_18]
0x18006a914  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x18006a919  xor     eax, eax
0x18006a91b  jmp     short loc_18006A921
0x18006a91d  mov     eax, dword ptr [rsp+68h+arg_8]
0x18006a921  mov     rbx, [rsp+68h+arg_0]
0x18006a926  add     rsp, 50h
0x18006a92a  pop     r14
0x18006a92c  pop     rdi
0x18006a92d  pop     rsi
0x18006a92e  retn
```
