# Windows::System::Internal::UserManagerStatics::~UserManagerStatics(void)

- ea: `0x180089b44`
- end: `0x180089e3f`
- name: `??1UserManagerStatics@Internal@System@Windows@@UEAA@XZ`
- size: `763`
- prototype: `void __fastcall(Windows::System::Internal::UserManagerStatics *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008ac90`

## callees

- `0x180005628`
- `0x180007920`
- `0x18000ce48`
- `0x18000fd2c`
- `0x180076ccc`
- `0x18007efd4`
- `0x180089b1c`
- `0x180089b44`
- `0x180089e48`
- `0x1800bef34`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089cfa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089d40`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089d95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089dde`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089deb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089e1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089cfa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089d40`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089d95`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089dde`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089deb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180089e1c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180089c6c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180089cb0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180089c6c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180089cb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180089c5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180089c9e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180089c5a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180089c9e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180089c79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180089cbd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180089c79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180089cbd`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180089cda`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180089cda`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::System::Internal::UserManagerStatics::~UserManagerStatics(
        Windows::System::Internal::UserManagerStatics *this)
{
  char *v2; // rdi
  __int64 v3; // rcx
  struct _TP_TIMER *v4; // rcx
  struct _TP_TIMER *v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)this = &Windows::System::Internal::UserManagerStatics::`vftable'{for `IActivationFactory'};
  *((_QWORD *)this + 1) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::Internal::IUserManagerStatics,Windows::System::Internal::IUserManagerStatics2,Windows::System::Internal::IUserManagerStatics3,Windows::System::Internal::IUserManagerStatics4,Windows::System::Internal::IUserManagerStatics5,Windows::System::Internal::IUserManagerStatics6,Windows::System::Internal::IUserManagerStatics7,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)this + 5) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::IUserManagerStatics'};
  *((_QWORD *)this + 6) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserManagerStatics2,Windows::System::Internal::IUserManagerStatics3,Windows::System::Internal::IUserManagerStatics4,Windows::System::Internal::IUserManagerStatics5,Windows::System::Internal::IUserManagerStatics6,Windows::System::Internal::IUserManagerStatics7,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'};
  *((_QWORD *)this + 7) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::IUserManagerStatics3'};
  *((_QWORD *)this + 8) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserManagerStatics4,Windows::System::Internal::IUserManagerStatics5,Windows::System::Internal::IUserManagerStatics6,Windows::System::Internal::IUserManagerStatics7,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'};
  *((_QWORD *)this + 9) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::IUserManagerStatics5'};
  *((_QWORD *)this + 10) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserManagerStatics6,Windows::System::Internal::IUserManagerStatics7,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'};
  *((_QWORD *)this + 11) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::IUserManagerStatics7'};
  *((_QWORD *)this + 12) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'};
  *((_QWORD *)this + 13) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::ISignInStateManager2'};
  *((_QWORD *)this + 14) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'};
  *((_QWORD *)this + 15) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserDataManagerStatics>'};
  *((_QWORD *)this + 16) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'};
  *((_QWORD *)this + 17) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserDataManagerStatics3>'};
  *((_QWORD *)this + 18) = &Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'};
  if ( g_userManagerStatics == this )
  {
    g_userManagerStatics = 0;
    Windows::System::Internal::UserManagerStatics::s_Initialized = 0;
  }
  v2 = (char *)this + 904;
  v3 = *((_QWORD *)this + 113);
  if ( v3 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 104LL))(v3, *((_QWORD *)this + 112));
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 122);
  if ( v4 )
  {
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 122), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 122));
    *((_QWORD *)this + 122) = 0;
  }
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 124);
  if ( v5 )
  {
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 124), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 124));
    *((_QWORD *)this + 124) = 0;
  }
  if ( *((_QWORD *)this + 121) )
  {
    RtlUnsubscribeWnfStateChangeNotification();
    *((_QWORD *)this + 121) = 0;
  }
  Windows::System::Internal::StaticsCache::UnregisterStatic(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 23);
  v6 = *((_QWORD *)this + 114);
  if ( v6 )
  {
    *((_QWORD *)this + 114) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
  SecHandleTable::Table::~Table((Windows::System::Internal::UserManagerStatics *)((char *)this + 856));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 816));
  Windows::Internal::Events::HeapEventStore::~HeapEventStore((Windows::System::Internal::UserManagerStatics *)((char *)this + 792));
  Windows::Internal::Events::HeapEventStore::~HeapEventStore((Windows::System::Internal::UserManagerStatics *)((char *)this + 760));
  Windows::Internal::Events::HeapEventStore::~HeapEventStore((Windows::System::Internal::UserManagerStatics *)((char *)this + 728));
  Windows::Internal::Events::HeapEventStore::~HeapEventStore((Windows::System::Internal::UserManagerStatics *)((char *)this + 696));
  Windows::Internal::Events::HeapEventStore::~HeapEventStore((Windows::System::Internal::UserManagerStatics *)((char *)this + 664));
  std::_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::WeakRef,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::WeakRef>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,Microsoft::WRL::WeakRef,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Microsoft::WRL::WeakRef>>,0>>((char *)this + 640);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 584);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 568);
  Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>((char *)this + 552);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 536);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 528);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 11);
  Windows::System::Internal::Implementation::UserOnlineConversionTracker::~UserOnlineConversionTracker((Windows::System::Internal::UserManagerStatics *)((char *)this + 384));
  Windows::System::Internal::Implementation::SignInTracker::~SignInTracker((Windows::System::Internal::UserManagerStatics *)((char *)this + 320));
  Windows::System::Internal::Implementation::SignInTracker::~SignInTracker((Windows::System::Internal::UserManagerStatics *)((char *)this + 256));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  *((_DWORD *)this + 47) = -1073741823;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x180089b44  mov     [rsp+arg_0], rbx
0x180089b49  push    rdi
0x180089b4a  sub     rsp, 20h
0x180089b4e  mov     rbx, rcx
0x180089b51  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6BIActivationFactory@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `IActivationFactory'}
0x180089b58  mov     [rcx], rax
0x180089b5b  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIUserManagerStatics@Internal@System@Windows@@UIUserManagerStatics2@234@UIUserManagerStatics3@234@UIUserManagerStatics4@234@UIUserManagerStatics5@234@UIUserManagerStatics6@234@UIUserManagerStatics7@234@UISignInStateManager@234@UISignInStateManager2@234@U?$CloakedIid@UIUserManagerPrivate@Implementation@Internal@System@Windows@@@WRL@Microsoft@@U?$CloakedIid@UIUserDataManagerStatics@Internal@System@Windows@@@WRL@Microsoft@@U?$CloakedIid@UIUserDataManagerStatics2@Internal@System@Windows@@@WRL@Microsoft@@U?$CloakedIid@UIUserDataManagerStatics3@Internal@System@Windows@@@WRL@Microsoft@@U?$CloakedIid@UIAccessoriesAppCompatabilityShim@Internal@System@Windows@@@WRL@Microsoft@@@23@@WRL@Microsoft@@@Details@23@VNil@523@V6523@V6523@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::System::Internal::IUserManagerStatics,Windows::System::Internal::IUserManagerStatics2,Windows::System::Internal::IUserManagerStatics3,Windows::System::Internal::IUserManagerStatics4,Windows::System::Internal::IUserManagerStatics5,Windows::System::Internal::IUserManagerStatics6,Windows::System::Internal::IUserManagerStatics7,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180089b62  mov     [rcx+8], rax
0x180089b66  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6BIUserManagerStatics@123@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::IUserManagerStatics'}
0x180089b6d  mov     [rcx+28h], rax
0x180089b71  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUserManagerStatics2@Internal@System@Windows@@UIUserManagerStatics3@567@UIUserManagerStatics4@567@UIUserManagerStatics5@567@UIUserManagerStatics6@567@UIUserManagerStatics7@567@UISignInStateManager@567@UISignInStateManager2@567@U?$CloakedIid@UIUserManagerPrivate@Implementation@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics2@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics3@Internal@System@Windows@@@23@U?$CloakedIid@UIAccessoriesAppCompatabilityShim@Internal@System@Windows@@@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserManagerStatics2,Windows::System::Internal::IUserManagerStatics3,Windows::System::Internal::IUserManagerStatics4,Windows::System::Internal::IUserManagerStatics5,Windows::System::Internal::IUserManagerStatics6,Windows::System::Internal::IUserManagerStatics7,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'}
0x180089b78  mov     [rcx+30h], rax
0x180089b7c  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6BIUserManagerStatics3@123@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::IUserManagerStatics3'}
0x180089b83  mov     [rcx+38h], rax
0x180089b87  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUserManagerStatics4@Internal@System@Windows@@UIUserManagerStatics5@567@UIUserManagerStatics6@567@UIUserManagerStatics7@567@UISignInStateManager@567@UISignInStateManager2@567@U?$CloakedIid@UIUserManagerPrivate@Implementation@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics2@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics3@Internal@System@Windows@@@23@U?$CloakedIid@UIAccessoriesAppCompatabilityShim@Internal@System@Windows@@@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserManagerStatics4,Windows::System::Internal::IUserManagerStatics5,Windows::System::Internal::IUserManagerStatics6,Windows::System::Internal::IUserManagerStatics7,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'}
0x180089b8e  mov     [rcx+40h], rax
0x180089b92  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6BIUserManagerStatics5@123@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::IUserManagerStatics5'}
0x180089b99  mov     [rcx+48h], rax
0x180089b9d  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUserManagerStatics6@Internal@System@Windows@@UIUserManagerStatics7@567@UISignInStateManager@567@UISignInStateManager2@567@U?$CloakedIid@UIUserManagerPrivate@Implementation@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics2@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics3@Internal@System@Windows@@@23@U?$CloakedIid@UIAccessoriesAppCompatabilityShim@Internal@System@Windows@@@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserManagerStatics6,Windows::System::Internal::IUserManagerStatics7,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'}
0x180089ba4  mov     [rcx+50h], rax
0x180089ba8  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6BIUserManagerStatics7@123@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::IUserManagerStatics7'}
0x180089baf  mov     [rcx+58h], rax
0x180089bb3  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISignInStateManager@Internal@System@Windows@@UISignInStateManager2@567@U?$CloakedIid@UIUserManagerPrivate@Implementation@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics2@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics3@Internal@System@Windows@@@23@U?$CloakedIid@UIAccessoriesAppCompatabilityShim@Internal@System@Windows@@@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::ISignInStateManager,Windows::System::Internal::ISignInStateManager2,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'}
0x180089bba  mov     [rcx+60h], rax
0x180089bbe  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6BISignInStateManager2@123@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Windows::System::Internal::ISignInStateManager2'}
0x180089bc5  mov     [rcx+68h], rax
0x180089bc9  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIUserManagerPrivate@Implementation@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics2@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics3@Internal@System@Windows@@@23@U?$CloakedIid@UIAccessoriesAppCompatabilityShim@Internal@System@Windows@@@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::System::Internal::Implementation::IUserManagerPrivate>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'}
0x180089bd0  mov     [rcx+70h], rax
0x180089bd4  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUserDataManagerStatics@Internal@System@Windows@@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserDataManagerStatics>'}
0x180089bdb  mov     [rcx+78h], rax
0x180089bdf  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIUserDataManagerStatics2@Internal@System@Windows@@@23@U?$CloakedIid@UIUserDataManagerStatics3@Internal@System@Windows@@@23@U?$CloakedIid@UIAccessoriesAppCompatabilityShim@Internal@System@Windows@@@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics2>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IUserDataManagerStatics3>,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'}
0x180089be6  mov     [rcx+80h], rax
0x180089bed  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIUserDataManagerStatics3@Internal@System@Windows@@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Internal::IUserDataManagerStatics3>'}
0x180089bf4  mov     [rcx+88h], rax
0x180089bfb  lea     rax, ??_7UserManagerStatics@Internal@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIAccessoriesAppCompatabilityShim@Internal@System@Windows@@@23@@Details@WRL@Microsoft@@@; const Windows::System::Internal::UserManagerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::System::Internal::IAccessoriesAppCompatabilityShim>>'}
0x180089c02  mov     [rcx+90h], rax
0x180089c09  cmp     cs:?g_userManagerStatics@@3PEAVUserManagerStatics@Internal@System@Windows@@EA, rcx; Windows::System::Internal::UserManagerStatics * g_userManagerStatics
0x180089c10  jnz     short loc_180089C24
0x180089c12  mov     cs:?g_userManagerStatics@@3PEAVUserManagerStatics@Internal@System@Windows@@EA, 0; Windows::System::Internal::UserManagerStatics * g_userManagerStatics
0x180089c1d  mov     cs:?s_Initialized@UserManagerStatics@Internal@System@Windows@@0_NA, 0; bool Windows::System::Internal::UserManagerStatics::s_Initialized
0x180089c24  lea     rdi, [rcx+388h]
0x180089c2b  mov     rcx, [rdi]
0x180089c2e  test    rcx, rcx
0x180089c31  jz      short loc_180089C46
0x180089c33  mov     rax, [rcx]
0x180089c36  mov     rdx, [rbx+380h]
0x180089c3d  mov     rax, [rax+68h]
0x180089c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c46  mov     rcx, [rbx+3D0h]; pti
0x180089c4d  test    rcx, rcx
0x180089c50  jz      short loc_180089C8A
0x180089c52  xor     r9d, r9d; msWindowLength
0x180089c55  xor     r8d, r8d; msPeriod
0x180089c58  xor     edx, edx; pftDueTime
0x180089c5a  call    cs:__imp_SetThreadpoolTimer
0x180089c60  mov     edx, 1; fCancelPendingCallbacks
0x180089c65  mov     rcx, [rbx+3D0h]; pti
0x180089c6c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180089c72  mov     rcx, [rbx+3D0h]; pti
0x180089c79  call    cs:__imp_CloseThreadpoolTimer
0x180089c7f  mov     qword ptr [rbx+3D0h], 0
0x180089c8a  mov     rcx, [rbx+3E0h]; pti
0x180089c91  test    rcx, rcx
0x180089c94  jz      short loc_180089CCE
0x180089c96  xor     r9d, r9d; msWindowLength
0x180089c99  xor     r8d, r8d; msPeriod
0x180089c9c  xor     edx, edx; pftDueTime
0x180089c9e  call    cs:__imp_SetThreadpoolTimer
0x180089ca4  mov     edx, 1; fCancelPendingCallbacks
0x180089ca9  mov     rcx, [rbx+3E0h]; pti
0x180089cb0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180089cb6  mov     rcx, [rbx+3E0h]; pti
0x180089cbd  call    cs:__imp_CloseThreadpoolTimer
0x180089cc3  mov     qword ptr [rbx+3E0h], 0
0x180089cce  mov     rcx, [rbx+3C8h]
0x180089cd5  test    rcx, rcx
0x180089cd8  jz      short loc_180089CEB
0x180089cda  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x180089ce0  mov     qword ptr [rbx+3C8h], 0
0x180089ceb  mov     rcx, rbx; struct IActivationFactory *
0x180089cee  call    ?UnregisterStatic@StaticsCache@Internal@System@Windows@@SAXPEAUIActivationFactory@@@Z; Windows::System::Internal::StaticsCache::UnregisterStatic(IActivationFactory *)
0x180089cf3  lea     rcx, [rbx+398h]; lpCriticalSection
0x180089cfa  call    cs:__imp_DeleteCriticalSection
0x180089d00  nop
0x180089d01  mov     rcx, [rbx+390h]
0x180089d08  test    rcx, rcx
0x180089d0b  jz      short loc_180089D25
0x180089d0d  mov     qword ptr [rbx+390h], 0
0x180089d18  mov     rax, [rcx]
0x180089d1b  mov     rax, [rax+10h]
0x180089d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089d24  nop
0x180089d25  mov     rcx, rdi
0x180089d28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180089d2d  lea     rcx, [rbx+358h]; this
0x180089d34  call    ??1Table@SecHandleTable@@UEAA@XZ; SecHandleTable::Table::~Table(void)
0x180089d39  lea     rcx, [rbx+330h]; lpCriticalSection
0x180089d40  call    cs:__imp_DeleteCriticalSection
0x180089d46  lea     rcx, [rbx+318h]; this
0x180089d4d  call    ??1HeapEventStore@Events@Internal@Windows@@QEAA@XZ; Windows::Internal::Events::HeapEventStore::~HeapEventStore(void)
0x180089d52  lea     rcx, [rbx+2F8h]; this
0x180089d59  call    ??1HeapEventStore@Events@Internal@Windows@@QEAA@XZ; Windows::Internal::Events::HeapEventStore::~HeapEventStore(void)
0x180089d5e  lea     rcx, [rbx+2D8h]; this
0x180089d65  call    ??1HeapEventStore@Events@Internal@Windows@@QEAA@XZ; Windows::Internal::Events::HeapEventStore::~HeapEventStore(void)
0x180089d6a  lea     rcx, [rbx+2B8h]; this
0x180089d71  call    ??1HeapEventStore@Events@Internal@Windows@@QEAA@XZ; Windows::Internal::Events::HeapEventStore::~HeapEventStore(void)
0x180089d76  lea     rcx, [rbx+298h]; this
0x180089d7d  call    ??1HeapEventStore@Events@Internal@Windows@@QEAA@XZ; Windows::Internal::Events::HeapEventStore::~HeapEventStore(void)
0x180089d82  lea     rcx, [rbx+280h]
0x180089d89  call    ??1?$_Tree@V?$_Tmap_traits@IVWeakRef@WRL@Microsoft@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIVWeakRef@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,Microsoft::WRL::WeakRef,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::WeakRef>>,0>>::~_Tree<std::_Tmap_traits<uint,Microsoft::WRL::WeakRef,std::less<uint>,std::allocator<std::pair<uint const,Microsoft::WRL::WeakRef>>,0>>(void)
0x180089d8e  lea     rcx, [rbx+258h]; lpCriticalSection
0x180089d95  call    cs:__imp_DeleteCriticalSection
0x180089d9b  lea     rcx, [rbx+248h]
0x180089da2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180089da7  lea     rcx, [rbx+238h]
0x180089dae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180089db3  lea     rcx, [rbx+228h]
0x180089dba  call    ??1?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@UEAA@XZ; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::~GitPtrImpl<Windows::Internal::GitPtr>(void)
0x180089dbf  lea     rcx, [rbx+218h]
0x180089dc6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180089dcb  lea     rcx, [rbx+210h]
0x180089dd2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180089dd7  lea     rcx, [rbx+1E8h]; lpCriticalSection
0x180089dde  call    cs:__imp_DeleteCriticalSection
0x180089de4  lea     rcx, [rbx+1B8h]; lpCriticalSection
0x180089deb  call    cs:__imp_DeleteCriticalSection
0x180089df1  lea     rcx, [rbx+180h]; this
0x180089df8  call    ??1UserOnlineConversionTracker@Implementation@Internal@System@Windows@@QEAA@XZ; Windows::System::Internal::Implementation::UserOnlineConversionTracker::~UserOnlineConversionTracker(void)
0x180089dfd  lea     rcx, [rbx+140h]; this
0x180089e04  call    ??1SignInTracker@Implementation@Internal@System@Windows@@UEAA@XZ; Windows::System::Internal::Implementation::SignInTracker::~SignInTracker(void)
0x180089e09  lea     rcx, [rbx+100h]; this
0x180089e10  call    ??1SignInTracker@Implementation@Internal@System@Windows@@UEAA@XZ; Windows::System::Internal::Implementation::SignInTracker::~SignInTracker(void)
0x180089e15  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x180089e1c  call    cs:__imp_DeleteCriticalSection
0x180089e22  mov     dword ptr [rbx+0BCh], 0C0000001h
0x180089e2c  lea     rcx, [rbx+20h]
0x180089e30  mov     rbx, [rsp+28h+arg_0]
0x180089e35  add     rsp, 20h
0x180089e39  pop     rdi
0x180089e3a  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
