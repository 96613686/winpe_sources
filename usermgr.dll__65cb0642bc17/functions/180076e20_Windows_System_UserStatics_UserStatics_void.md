# Windows::System::UserStatics::~UserStatics(void)

- ea: `0x180076e20`
- end: `0x180077060`
- name: `??1UserStatics@System@Windows@@UEAA@XZ`
- size: `576`
- prototype: `void __fastcall(Windows::System::UserStatics *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180077b10`

## callees

- `0x18000ce48`
- `0x180025cd4`
- `0x180037cb8`
- `0x180037e98`
- `0x18003b578`
- `0x180052e00`
- `0x180076c98`
- `0x180076ccc`
- `0x180076d00`
- `0x180076d34`
- `0x180076d68`
- `0x180076e20`
- `0x18007efd4`
- `0x1800ec010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180076f4b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180076f91`
- `msvcrt!??3@YAXPEAX@Z` at `0x180076f4b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180076f91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180076fcb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180076fe8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180077001`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007703e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180076fcb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180076fe8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180077001`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007703e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076e70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076e70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::System::UserStatics::~UserStatics(Windows::System::UserStatics *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  __int64 *v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // r14
  __int64 v6; // rcx
  __int64 i; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  _QWORD v11[9]; // [rsp+20h] [rbp-48h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::System::UserStatics::`vftable';
  *((_QWORD *)this + 1) = &Windows::System::UserStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Implements<Windows::System::IUserStatics,Windows::System::IUserStatics2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserStaticsInternal>>>>'};
  *((_QWORD *)this + 5) = &Windows::System::UserStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Windows::System::IUserStatics,Windows::System::IUserStatics2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserStaticsInternal>>>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Implements<Windows::System::IUserStatics,Windows::System::IUserStatics2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserStaticsInternal>>>>'};
  *((_QWORD *)this + 6) = &Windows::System::UserStatics::`vftable'{for `Windows::System::IUserStatics2'};
  *((_QWORD *)this + 7) = &Windows::System::UserStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserStaticsInternal>>'};
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 296);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  v12 = v2;
  v3 = (__int64 *)*((_QWORD *)this + 44);
  v4 = *v3;
  while ( (__int64 *)v4 != v3 )
  {
    v5 = *(_QWORD *)(v4 + 40);
    v11[0] = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    v11[1] = *(_QWORD *)(v4 + 48);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 56LL))(v5);
    wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(v11);
    if ( !*(_BYTE *)(v4 + 25) )
    {
      v6 = *(_QWORD *)(v4 + 16);
      if ( *(_BYTE *)(v6 + 25) )
      {
        for ( i = *(_QWORD *)(v4 + 8); !*(_BYTE *)(i + 25) && v4 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v4 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(v6);
      }
      v4 = i;
    }
  }
  Windows::System::Internal::StaticsCache::UnregisterStatic(this);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
  std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>((char *)this + 480);
  std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>((char *)this + 464);
  v9 = *((_QWORD *)this + 55);
  if ( v9 )
  {
    std::vector<Microsoft::WRL::WeakRef>::_Destroy(v8, v9, *((_QWORD *)this + 56));
    operator delete(*((void **)this + 55));
    *((_QWORD *)this + 55) = 0;
    *((_QWORD *)this + 56) = 0;
    *((_QWORD *)this + 57) = 0;
  }
  v10 = *((_QWORD *)this + 52);
  if ( v10 )
  {
    std::vector<Microsoft::WRL::WeakRef>::_Destroy(v8, v10, *((_QWORD *)this + 53));
    operator delete(*((void **)this + 52));
    *((_QWORD *)this + 52) = 0;
    *((_QWORD *)this + 53) = 0;
    *((_QWORD *)this + 54) = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 408);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  std::_Tree<std::_Tmap_traits<unsigned int,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>>>,0>>((char *)this + 352);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>((char *)this + 336);
  DeleteCriticalSection(v2);
  std::_Tree<std::_Tmap_traits<unsigned int,unsigned long,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,unsigned long>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,unsigned long,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,unsigned long>>,0>>((char *)this + 272);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  std::_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::WeakRef,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::WeakRef>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::WeakRef,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::WeakRef>>,0>>((char *)this + 216);
  std::_Tree<std::_Tmap_traits<HSTRING__ *,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<HSTRING__ *>,std::allocator<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<HSTRING__ *,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<HSTRING__ *>,std::allocator<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>((char *)this + 200);
  std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>((char *)this + 184);
  std::_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<std::pair<unsigned int,unsigned long>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<unsigned int,unsigned long>>,std::allocator<std::pair<std::pair<unsigned int,unsigned long> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>((char *)this + 168);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  *((_DWORD *)this + 25) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x180076e20  push    rbx
0x180076e22  push    rbp
0x180076e23  push    rsi
0x180076e24  push    rdi
0x180076e25  push    r14
0x180076e27  push    r15
0x180076e29  sub     rsp, 38h
0x180076e2d  mov     rsi, rcx
0x180076e30  lea     rax, ??_7UserStatics@System@Windows@@6B@; const Windows::System::UserStatics::`vftable'
0x180076e37  mov     [rcx], rax
0x180076e3a  lea     rax, ??_7UserStatics@System@Windows@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$Implements@UIUserStatics@System@Windows@@UIUserStatics2@23@U?$CloakedIid@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@23@@Details@23@@Details@WRL@Microsoft@@@; const Windows::System::UserStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Implements<Windows::System::IUserStatics,Windows::System::IUserStatics2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserStaticsInternal>>>>'}
0x180076e41  mov     [rcx+8], rax
0x180076e45  lea     rax, ??_7UserStatics@System@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@UIUserStatics@System@Windows@@UIUserStatics2@23@U?$CloakedIid@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$Implements@UIUserStatics@System@Windows@@UIUserStatics2@23@U?$CloakedIid@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@23@@234@@Details@WRL@Microsoft@@@; const Windows::System::UserStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Windows::System::IUserStatics,Windows::System::IUserStatics2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserStaticsInternal>>>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::Implements<Windows::System::IUserStatics,Windows::System::IUserStatics2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserStaticsInternal>>>>'}
0x180076e4c  mov     [rcx+28h], rax
0x180076e50  lea     rax, ??_7UserStatics@System@Windows@@6BIUserStatics2@12@@; const Windows::System::UserStatics::`vftable'{for `Windows::System::IUserStatics2'}
0x180076e57  mov     [rcx+30h], rax
0x180076e5b  lea     rax, ??_7UserStatics@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIUserStaticsInternal@Implementation@Internal@System@Windows@@@23@@Details@WRL@Microsoft@@@; const Windows::System::UserStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserStaticsInternal>>'}
0x180076e62  mov     [rcx+38h], rax
0x180076e66  lea     rbp, [rcx+128h]
0x180076e6d  mov     rcx, rbp; lpCriticalSection
0x180076e70  call    cs:__imp_EnterCriticalSection
0x180076e76  mov     [rsp+68h+arg_0], rbp
0x180076e7b  lea     r15, [rsi+160h]
0x180076e82  mov     rdi, [r15]
0x180076e85  mov     rbx, [rdi]
0x180076e88  cmp     rbx, rdi
0x180076e8b  jz      short loc_180076F02
0x180076e8d  mov     r14, [rbx+28h]
0x180076e91  mov     [rsp+68h+var_48], r14
0x180076e96  test    r14, r14
0x180076e99  jz      short loc_180076EAB
0x180076e9b  mov     rax, [r14]
0x180076e9e  mov     rcx, r14
0x180076ea1  mov     rax, [rax+8]
0x180076ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076eaa  nop
0x180076eab  mov     rdx, [rbx+30h]
0x180076eaf  mov     [rsp+68h+var_40], rdx
0x180076eb4  mov     rax, [r14]
0x180076eb7  mov     rcx, r14
0x180076eba  mov     rax, [rax+38h]
0x180076ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076ec3  lea     rcx, [rsp+68h+var_48]
0x180076ec8  call    ??1?$com_ptr_t@VSetAutologonForUserAsyncOperation@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::SetAutologonForUserAsyncOperation,wil::err_exception_policy>(void)
0x180076ecd  cmp     byte ptr [rbx+19h], 0
0x180076ed1  jnz     short loc_180076E88
0x180076ed3  mov     rcx, [rbx+10h]
0x180076ed7  cmp     byte ptr [rcx+19h], 0
0x180076edb  jnz     short loc_180076EE7
0x180076edd  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>>::_Min(std::_Tree_node<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>,void *> *)
0x180076ee2  mov     rbx, rax
0x180076ee5  jmp     short loc_180076E88
0x180076ee7  mov     rax, [rbx+8]
0x180076eeb  jmp     short loc_180076EFA
0x180076eed  cmp     rbx, [rax+10h]
0x180076ef1  jnz     short loc_180076EE2
0x180076ef3  mov     rbx, rax
0x180076ef6  mov     rax, [rax+8]
0x180076efa  cmp     byte ptr [rax+19h], 0
0x180076efe  jz      short loc_180076EED
0x180076f00  jmp     short loc_180076EE2
0x180076f02  mov     rcx, rsi; struct IActivationFactory *
0x180076f05  call    ?UnregisterStatic@StaticsCache@Internal@System@Windows@@SAXPEAUIActivationFactory@@@Z; Windows::System::Internal::StaticsCache::UnregisterStatic(IActivationFactory *)
0x180076f0a  lea     rcx, [rsp+68h+arg_0]
0x180076f0f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180076f14  lea     rcx, [rsi+1E0h]
0x180076f1b  call    ??1?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>(void)
0x180076f20  lea     rcx, [rsi+1D0h]
0x180076f27  call    ??1?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>(void)
0x180076f2c  mov     rdx, [rsi+1B8h]
0x180076f33  test    rdx, rdx
0x180076f36  jz      short loc_180076F72
0x180076f38  mov     r8, [rsi+1C0h]
0x180076f3f  call    ?_Destroy@?$vector@VWeakRef@WRL@Microsoft@@V?$allocator@VWeakRef@WRL@Microsoft@@@std@@@std@@IEAAXPEAVWeakRef@WRL@Microsoft@@0@Z; std::vector<Microsoft::WRL::WeakRef>::_Destroy(Microsoft::WRL::WeakRef *,Microsoft::WRL::WeakRef *)
0x180076f44  mov     rcx, [rsi+1B8h]
0x180076f4b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180076f51  mov     qword ptr [rsi+1B8h], 0
0x180076f5c  mov     qword ptr [rsi+1C0h], 0
0x180076f67  mov     qword ptr [rsi+1C8h], 0
0x180076f72  mov     rdx, [rsi+1A0h]
0x180076f79  test    rdx, rdx
0x180076f7c  jz      short loc_180076FB8
0x180076f7e  mov     r8, [rsi+1A8h]
0x180076f85  call    ?_Destroy@?$vector@VWeakRef@WRL@Microsoft@@V?$allocator@VWeakRef@WRL@Microsoft@@@std@@@std@@IEAAXPEAVWeakRef@WRL@Microsoft@@0@Z; std::vector<Microsoft::WRL::WeakRef>::_Destroy(Microsoft::WRL::WeakRef *,Microsoft::WRL::WeakRef *)
0x180076f8a  mov     rcx, [rsi+1A0h]
0x180076f91  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180076f97  mov     qword ptr [rsi+1A0h], 0
0x180076fa2  mov     qword ptr [rsi+1A8h], 0
0x180076fad  mov     qword ptr [rsi+1B0h], 0
0x180076fb8  lea     rcx, [rsi+198h]
0x180076fbf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180076fc4  lea     rcx, [rsi+170h]; lpCriticalSection
0x180076fcb  call    cs:__imp_DeleteCriticalSection
0x180076fd1  mov     rcx, r15
0x180076fd4  call    ??1?$_Tree@V?$_Tmap_traits@IU?$pair@V?$com_ptr_t@UIWebAccountMonitor2@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@UEventRegistrationToken@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIU?$pair@V?$com_ptr_t@UIWebAccountMonitor2@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@UEventRegistrationToken@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>,std::less<uint>,std::allocator<std::pair<uint const,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>>>,0>>::~_Tree<std::_Tmap_traits<uint,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>,std::less<uint>,std::allocator<std::pair<uint const,std::pair<wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebAccountMonitor2,wil::err_exception_policy>,EventRegistrationToken>>>,0>>(void)
0x180076fd9  lea     rcx, [rsi+150h]
0x180076fe0  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,uint>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,uint,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,uint>>,0>>(void)
0x180076fe5  mov     rcx, rbp; lpCriticalSection
0x180076fe8  call    cs:__imp_DeleteCriticalSection
0x180076fee  lea     rcx, [rsi+110h]
0x180076ff5  call    ??1?$_Tree@V?$_Tmap_traits@IKU?$less@I@std@@V?$allocator@U?$pair@$$CBIK@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,ulong,std::less<uint>,std::allocator<std::pair<uint const,ulong>>,0>>::~_Tree<std::_Tmap_traits<uint,ulong,std::less<uint>,std::allocator<std::pair<uint const,ulong>>,0>>(void)
0x180076ffa  lea     rcx, [rsi+0E8h]; lpCriticalSection
0x180077001  call    cs:__imp_DeleteCriticalSection
0x180077007  lea     rcx, [rsi+0D8h]
0x18007700e  call    ??1?$_Tree@V?$_Tmap_traits@IVWeakRef@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIVWeakRef@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,Microsoft::WRL::WeakRef,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::WeakRef>>,0>>::~_Tree<std::_Tmap_traits<uint,Microsoft::WRL::WeakRef,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::WeakRef>>,0>>(void)
0x180077013  lea     rcx, [rsi+0C8h]
0x18007701a  call    ??1?$_Tree@V?$_Tmap_traits@PEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@PEAUHSTRING__@@@std@@V?$allocator@U?$pair@QEAUHSTRING__@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<HSTRING__ *,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<HSTRING__ *>,std::allocator<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<HSTRING__ *,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<HSTRING__ *>,std::allocator<std::pair<HSTRING__ * const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>(void)
0x18007701f  lea     rcx, [rsi+0B8h]
0x180077026  call    ??1?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>(void)
0x18007702b  lea     rcx, [rsi+0A8h]
0x180077032  call    ??1?$_Tree@V?$_Tmap_traits@U?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@U?$less@U?$pair@IK@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@IK@std@@V?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>::~_Tree<std::_Tmap_traits<std::pair<uint,ulong>,Microsoft::WRL::ComPtr<Windows::System::IUser>,std::less<std::pair<uint,ulong>>,std::allocator<std::pair<std::pair<uint,ulong> const,Microsoft::WRL::ComPtr<Windows::System::IUser>>>,0>>(void)
0x180077037  lea     rcx, [rsi+80h]; lpCriticalSection
0x18007703e  call    cs:__imp_DeleteCriticalSection
0x180077044  mov     dword ptr [rsi+64h], 0C0000001h
0x18007704b  lea     rcx, [rsi+20h]
0x18007704f  add     rsp, 38h
0x180077053  pop     r15
0x180077055  pop     r14
0x180077057  pop     rdi
0x180077058  pop     rsi
0x180077059  pop     rbp
0x18007705a  pop     rbx
0x18007705b  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
