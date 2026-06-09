# CreateAndRegisterClassFactories(void)

- ea: `0x180033238`
- end: `0x18003380b`
- name: `?CreateAndRegisterClassFactories@@YAJXZ`
- size: `1491`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180033814`

## callees

- `0x180008e64`
- `0x180033238`
- `0x1800370fc`
- `0x1800371d4`
- `0x1800372ac`
- `0x180038998`
- `0x1800dd930`
- `0x1800de0fc`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003364d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003364d`

## string_xrefs

- `0x18003354f`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x18003359d`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x1800336b1`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180033714`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180033749`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x18003377f`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x1800337b5`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 CreateAndRegisterClassFactories(void)
{
  __int64 v0; // r14
  char *v1; // rax
  __int64 v2; // rbx
  _QWORD *v3; // rdi
  __int64 v4; // r13
  char *v5; // rax
  __int64 v6; // rbx
  _QWORD *v7; // rdi
  __int64 v8; // r12
  char *v9; // rax
  __int64 v10; // rbx
  _QWORD *v11; // rdi
  __int64 v12; // r15
  char *v13; // rax
  __int64 v14; // rbx
  _QWORD *v15; // rdi
  int updated; // eax
  unsigned int v17; // ebx
  __int64 v18; // rsi
  int v19; // eax
  __int64 v20; // rdi
  HRESULT Instance; // eax
  __int64 v22; // rdx
  __int64 v23; // rbx
  LPVOID v24; // rcx
  int ppv; // [rsp+28h] [rbp-49h]
  HRESULT v27; // [rsp+48h] [rbp-29h]
  __int64 v28; // [rsp+50h] [rbp-21h] BYREF
  __int64 v29; // [rsp+58h] [rbp-19h] BYREF
  __int64 v30; // [rsp+60h] [rbp-11h] BYREF
  __int64 v31; // [rsp+68h] [rbp-9h]
  __int64 v32; // [rsp+70h] [rbp-1h]
  __int64 v33; // [rsp+78h] [rbp+7h]
  __int64 v34; // [rsp+80h] [rbp+Fh]
  __int128 v35; // [rsp+88h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v0 = 0;
  v31 = 0;
  v1 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v2 = (__int64)v1;
  if ( !v1 )
  {
    v17 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
      (const char *)0x8007000ELL,
      ppv);
    goto LABEL_48;
  }
  v3 = v1 + 8;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v1 + 8);
  *(_DWORD *)(v2 + 44) = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IClassFactory'};
  *v3 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v2 = &ServiceClassFactoryT<UpdateSessionOrchestrator>::`vftable'{for `IClassFactory'};
  *v3 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *(_BYTE *)(v2 + 48) = 0;
  *(_QWORD *)(v2 + 56) = 0;
  ((void (__fastcall *)(__int64))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,1,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::AddRef)(v2);
  v31 = v2;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v0 = qword_180150768;
  qword_180150768 = v2;
  v31 = v0;
  v4 = 0;
  v32 = 0;
  v5 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (__int64)v5;
  if ( v5 )
  {
    v7 = v5 + 8;
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v5 + 8);
    *(_DWORD *)(v6 + 44) = 1;
    *(_QWORD *)v6 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IClassFactory'};
    *v7 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v6 = &ServiceClassFactoryT<UxUpdateManager>::`vftable'{for `IClassFactory'};
    *v7 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *(_BYTE *)(v6 + 48) = 0;
    *(_QWORD *)(v6 + 56) = 0;
    ((void (__fastcall *)(__int64))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,1,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::AddRef)(v6);
    v32 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v4 = qword_180150770;
    qword_180150770 = v6;
    v32 = v4;
    v8 = 0;
    v33 = 0;
    v9 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v10 = (__int64)v9;
    if ( !v9 )
    {
      v17 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x229,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
        (const char *)0x8007000ELL,
        ppv);
LABEL_40:
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      goto LABEL_44;
    }
    v11 = v9 + 8;
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v9 + 8);
    *(_DWORD *)(v10 + 44) = 1;
    *(_QWORD *)v10 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IClassFactory'};
    *v11 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v10 = &ServiceClassFactoryT<UniversalOrchestrator>::`vftable'{for `IClassFactory'};
    *v11 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *(_BYTE *)(v10 + 48) = 0;
    *(_QWORD *)(v10 + 56) = 0;
    ((void (__fastcall *)(__int64))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,1,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::AddRef)(v10);
    v33 = v10;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v8 = qword_180150780;
    qword_180150780 = v10;
    v33 = v8;
    v12 = 0;
    v34 = 0;
    v13 = (char *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v14 = (__int64)v13;
    if ( !v13 )
    {
      v17 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22D,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
        (const char *)0x8007000ELL,
        ppv);
LABEL_36:
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      goto LABEL_40;
    }
    v15 = v13 + 8;
    Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(v13 + 8);
    *(_DWORD *)(v14 + 44) = 1;
    *(_QWORD *)v14 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IClassFactory'};
    *v15 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v14 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `IClassFactory'};
    *v15 = &ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *(_BYTE *)(v14 + 48) = 0;
    *(_QWORD *)(v14 + 56) = 0;
    ((void (__fastcall *)(__int64))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,1,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *>,Microsoft::WRL::FtmBase>::AddRef)(v14);
    v34 = v14;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v12 = qword_180150788;
    qword_180150788 = v14;
    v34 = v12;
    v28 = 0;
    updated = Microsoft::WRL::Details::MakeAndInitialize<ServiceClassFactoryT<WindowsUpdateAdministration>,ServiceClassFactoryT<WindowsUpdateAdministration>,>(&v28);
    v17 = updated;
    if ( updated < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x231,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
        (const char *)(unsigned int)updated,
        ppv);
      v18 = v28;
LABEL_32:
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      goto LABEL_36;
    }
    v18 = qword_180150790;
    qword_180150790 = v28;
    v28 = v18;
    v29 = 0;
    v19 = Microsoft::WRL::Details::MakeAndInitialize<ServiceClassFactoryT<UsoSvc>,ServiceClassFactoryT<UsoSvc>,>(&v29);
    v17 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
        (const char *)(unsigned int)v19,
        ppv);
      v20 = v29;
LABEL_30:
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      goto LABEL_32;
    }
    v20 = qword_180150778;
    qword_180150778 = v29;
    v29 = v20;
    v30 = 0;
    Instance = Microsoft::WRL::Details::MakeAndInitialize<ServiceClassFactoryT<UsoCapabilities>,ServiceClassFactoryT<UsoCapabilities>,>(&v30);
    v27 = Instance;
    if ( Instance >= 0 )
    {
      v23 = qword_180150798;
      qword_180150798 = v30;
      v30 = v23;
      v24 = ::ppv;
      ::ppv = 0;
      if ( v24 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
      Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &::ppv);
      v27 = Instance;
      if ( Instance >= 0 )
      {
        v35 = 0;
        ppv = 5;
        Instance = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), __int128 *, GUID *))(*(_QWORD *)::ppv + 24LL))(
                     ::ppv,
                     ConnectCallback,
                     &v35,
                     &GUID_000001da_0000_0000_c000_000000000046);
        v27 = Instance;
        if ( Instance >= 0 )
        {
          v27 = 0;
          goto LABEL_27;
        }
        v22 = 575;
      }
      else
      {
        v22 = 572;
      }
    }
    else
    {
      v22 = 569;
      v23 = v30;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
LABEL_27:
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v17 = v27;
    goto LABEL_30;
  }
  v17 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x225,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
    (const char *)0x8007000ELL,
    ppv);
LABEL_44:
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
LABEL_48:
  if ( v0 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v0 + 16LL))(v0);
  return v17;
}

```

## disassembly

```asm
0x180033238  mov     rax, rsp
0x18003323b  mov     [rax+8], rbx
0x18003323f  mov     [rax+10h], rsi
0x180033243  mov     [rax+18h], rdi
0x180033247  push    rbp
0x180033248  push    r12
0x18003324a  push    r13
0x18003324c  push    r14
0x18003324e  push    r15
0x180033250  lea     rbp, [rax-5Fh]
0x180033254  sub     rsp, 0A0h
0x18003325b  mov     rax, cs:__security_cookie
0x180033262  xor     rax, rsp
0x180033265  mov     [rbp+57h+var_30], rax
0x180033269  xor     esi, esi
0x18003326b  mov     r14d, esi
0x18003326e  mov     [rbp+57h+var_60], rsi
0x180033272  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180033279  lea     ecx, [rsi+40h]; unsigned __int64
0x18003327c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033281  mov     rbx, rax
0x180033284  test    rax, rax
0x180033287  jz      loc_1800337A9
0x18003328d  lea     rdi, [rax+8]
0x180033291  mov     rcx, rdi
0x180033294  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180033299  lea     r15d, [rsi+1]
0x18003329d  mov     [rbx+2Ch], r15d
0x1800332a1  lea     r12, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIClassFactory@@VFtmBase@23@@WRL@Microsoft@@6BIClassFactory@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IClassFactory'}
0x1800332a8  mov     [rbx], r12
0x1800332ab  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800332b2  mov     [rdi], rax
0x1800332b5  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800332bc  test    rcx, rcx
0x1800332bf  jz      short loc_1800332CE
0x1800332c1  mov     rax, [rcx]
0x1800332c4  mov     rax, [rax+8]
0x1800332c8  call    _guard_dispatch_icall
0x1800332cd  nop
0x1800332ce  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateSessionOrchestrator@@@@6BIClassFactory@@@; const ServiceClassFactoryT<UpdateSessionOrchestrator>::`vftable'{for `IClassFactory'}
0x1800332d5  mov     [rbx], rax
0x1800332d8  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800332df  mov     [rdi], rax
0x1800332e2  mov     [rbx+30h], sil
0x1800332e6  mov     [rbx+38h], rsi
0x1800332ea  mov     rcx, rbx
0x1800332ed  mov     rax, cs:off_1800F62A8
0x1800332f4  call    _guard_dispatch_icall
0x1800332f9  nop
0x1800332fa  mov     [rbp+57h+var_60], rbx
0x1800332fe  mov     rax, [rbx]
0x180033301  mov     rcx, rbx
0x180033304  mov     rax, [rax+10h]
0x180033308  call    _guard_dispatch_icall
0x18003330d  nop
0x18003330e  mov     r14, cs:qword_180150768
0x180033315  mov     cs:qword_180150768, rbx
0x18003331c  mov     [rbp+57h+var_60], r14
0x180033320  mov     r13, rsi
0x180033323  mov     [rbp+57h+var_58], rsi
0x180033327  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003332e  mov     ecx, 40h ; '@'; unsigned __int64
0x180033333  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033338  mov     rbx, rax
0x18003333b  test    rax, rax
0x18003333e  jz      loc_180033773
0x180033344  lea     rdi, [rax+8]
0x180033348  mov     rcx, rdi
0x18003334b  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x180033350  mov     [rbx+2Ch], r15d
0x180033354  mov     [rbx], r12
0x180033357  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003335e  mov     [rdi], rax
0x180033361  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180033368  test    rcx, rcx
0x18003336b  jz      short loc_18003337A
0x18003336d  mov     rax, [rcx]
0x180033370  mov     rax, [rax+8]
0x180033374  call    _guard_dispatch_icall
0x180033379  nop
0x18003337a  lea     rax, ??_7?$ServiceClassFactoryT@VUxUpdateManager@@@@6BIClassFactory@@@; const ServiceClassFactoryT<UxUpdateManager>::`vftable'{for `IClassFactory'}
0x180033381  mov     [rbx], rax
0x180033384  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003338b  mov     [rdi], rax
0x18003338e  mov     [rbx+30h], sil
0x180033392  mov     [rbx+38h], rsi
0x180033396  mov     rcx, rbx
0x180033399  mov     rax, cs:off_1800F6278
0x1800333a0  call    _guard_dispatch_icall
0x1800333a5  nop
0x1800333a6  mov     [rbp+57h+var_58], rbx
0x1800333aa  mov     rax, [rbx]
0x1800333ad  mov     rcx, rbx
0x1800333b0  mov     rax, [rax+10h]
0x1800333b4  call    _guard_dispatch_icall
0x1800333b9  nop
0x1800333ba  mov     r13, cs:qword_180150770
0x1800333c1  mov     cs:qword_180150770, rbx
0x1800333c8  mov     [rbp+57h+var_58], r13
0x1800333cc  mov     r12, rsi
0x1800333cf  mov     [rbp+57h+var_50], rsi
0x1800333d3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800333da  mov     ecx, 40h ; '@'; unsigned __int64
0x1800333df  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800333e4  mov     rbx, rax
0x1800333e7  test    rax, rax
0x1800333ea  jz      loc_18003373D
0x1800333f0  lea     rdi, [rax+8]
0x1800333f4  mov     rcx, rdi
0x1800333f7  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1800333fc  mov     [rbx+2Ch], r15d
0x180033400  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIClassFactory@@VFtmBase@23@@WRL@Microsoft@@6BIClassFactory@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IClassFactory'}
0x180033407  mov     [rbx], rax
0x18003340a  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180033411  mov     [rdi], rax
0x180033414  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003341b  test    rcx, rcx
0x18003341e  jz      short loc_18003342D
0x180033420  mov     rax, [rcx]
0x180033423  mov     rax, [rax+8]
0x180033427  call    _guard_dispatch_icall
0x18003342c  nop
0x18003342d  lea     rax, ??_7?$ServiceClassFactoryT@VUniversalOrchestrator@@@@6BIClassFactory@@@; const ServiceClassFactoryT<UniversalOrchestrator>::`vftable'{for `IClassFactory'}
0x180033434  mov     [rbx], rax
0x180033437  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003343e  mov     [rdi], rax
0x180033441  mov     [rbx+30h], sil
0x180033445  mov     [rbx+38h], rsi
0x180033449  mov     rcx, rbx
0x18003344c  mov     rax, cs:off_1800F6248
0x180033453  call    _guard_dispatch_icall
0x180033458  nop
0x180033459  mov     [rbp+57h+var_50], rbx
0x18003345d  mov     rax, [rbx]
0x180033460  mov     rcx, rbx
0x180033463  mov     rax, [rax+10h]
0x180033467  call    _guard_dispatch_icall
0x18003346c  nop
0x18003346d  mov     r12, cs:qword_180150780
0x180033474  mov     cs:qword_180150780, rbx
0x18003347b  mov     [rbp+57h+var_50], r12
0x18003347f  mov     r15, rsi
0x180033482  mov     [rbp+57h+var_48], rsi
0x180033486  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003348d  mov     ecx, 40h ; '@'; unsigned __int64
0x180033492  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033497  mov     rbx, rax
0x18003349a  test    rax, rax
0x18003349d  jz      loc_180033708
0x1800334a3  lea     rdi, [rax+8]
0x1800334a7  mov     rcx, rdi
0x1800334aa  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
0x1800334af  mov     dword ptr [rbx+2Ch], 1
0x1800334b6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIClassFactory@@VFtmBase@23@@WRL@Microsoft@@6BIClassFactory@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IClassFactory'}
0x1800334bd  mov     [rbx], rax
0x1800334c0  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800334c7  mov     [rdi], rax
0x1800334ca  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800334d1  test    rcx, rcx
0x1800334d4  jz      short loc_1800334E3
0x1800334d6  mov     rax, [rcx]
0x1800334d9  mov     rax, [rax+8]
0x1800334dd  call    _guard_dispatch_icall
0x1800334e2  nop
0x1800334e3  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6BIClassFactory@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `IClassFactory'}
0x1800334ea  mov     [rbx], rax
0x1800334ed  lea     rax, ??_7?$ServiceClassFactoryT@VUpdateOrchestrator@@@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const ServiceClassFactoryT<UpdateOrchestrator>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800334f4  mov     [rdi], rax
0x1800334f7  mov     [rbx+30h], sil
0x1800334fb  mov     [rbx+38h], rsi
0x1800334ff  mov     rcx, rbx
0x180033502  mov     rax, cs:off_1800F6218
0x180033509  call    _guard_dispatch_icall
0x18003350e  nop
0x18003350f  mov     [rbp+57h+var_48], rbx
0x180033513  mov     rax, [rbx]
0x180033516  mov     rcx, rbx
0x180033519  mov     rax, [rax+10h]
0x18003351d  call    _guard_dispatch_icall
0x180033522  nop
0x180033523  mov     r15, cs:qword_180150788
0x18003352a  mov     cs:qword_180150788, rbx
0x180033531  mov     [rbp+57h+var_48], r15
0x180033535  mov     [rbp+57h+var_78], rsi
0x180033539  lea     rcx, [rbp+57h+var_78]
0x18003353d  call    ??$MakeAndInitialize@V?$ServiceClassFactoryT@VWindowsUpdateAdministration@@@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$ServiceClassFactoryT@VWindowsUpdateAdministration@@@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ServiceClassFactoryT<WindowsUpdateAdministration>,ServiceClassFactoryT<WindowsUpdateAdministration>,>(ServiceClassFactoryT<WindowsUpdateAdministration> * *)
0x180033542  mov     ebx, eax
0x180033544  test    eax, eax
0x180033546  jns     short loc_180033569
0x180033548  mov     rcx, [rbp+5Fh]; this
0x18003354c  mov     r9d, eax; char *
0x18003354f  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180033556  mov     edx, 231h; void *
0x18003355b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033560  mov     rsi, [rbp+57h+var_78]
0x180033564  jmp     loc_1800336F1
0x180033569  mov     rsi, cs:qword_180150790
0x180033570  mov     rax, [rbp+57h+var_78]
0x180033574  mov     cs:qword_180150790, rax
0x18003357b  mov     [rbp+57h+var_78], rsi
0x18003357f  mov     [rbp+57h+var_70], 0
0x180033587  lea     rcx, [rbp+57h+var_70]
0x18003358b  call    ??$MakeAndInitialize@V?$ServiceClassFactoryT@VUsoSvc@@@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$ServiceClassFactoryT@VUsoSvc@@@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ServiceClassFactoryT<UsoSvc>,ServiceClassFactoryT<UsoSvc>,>(ServiceClassFactoryT<UsoSvc> * *)
0x180033590  mov     ebx, eax
0x180033592  test    eax, eax
0x180033594  jns     short loc_1800335B7
0x180033596  mov     rcx, [rbp+5Fh]; this
0x18003359a  mov     r9d, eax; char *
0x18003359d  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800335a4  mov     edx, 235h; void *
0x1800335a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335ae  mov     rdi, [rbp+57h+var_70]
0x1800335b2  jmp     loc_1800336DC
0x1800335b7  mov     rdi, cs:qword_180150778
0x1800335be  mov     rax, [rbp+57h+var_70]
0x1800335c2  mov     cs:qword_180150778, rax
0x1800335c9  mov     [rbp+57h+var_70], rdi
0x1800335cd  mov     [rbp+57h+var_68], 0
0x1800335d5  lea     rcx, [rbp+57h+var_68]
0x1800335d9  call    ??$MakeAndInitialize@V?$ServiceClassFactoryT@VUsoCapabilities@@@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$ServiceClassFactoryT@VUsoCapabilities@@@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ServiceClassFactoryT<UsoCapabilities>,ServiceClassFactoryT<UsoCapabilities>,>(ServiceClassFactoryT<UsoCapabilities> * *)
0x1800335de  mov     [rbp+57h+var_80], eax
0x1800335e1  test    eax, eax
0x1800335e3  jns     short loc_1800335F3
0x1800335e5  mov     edx, 239h
0x1800335ea  mov     rbx, [rbp+57h+var_68]
0x1800335ee  jmp     loc_1800336AA
0x1800335f3  mov     rbx, cs:qword_180150798
0x1800335fa  mov     rax, [rbp+57h+var_68]
0x1800335fe  mov     cs:qword_180150798, rax
0x180033605  mov     [rbp+57h+var_68], rbx
0x180033609  mov     rcx, cs:ppv
0x180033610  mov     cs:ppv, 0
0x18003361b  test    rcx, rcx
0x18003361e  jz      short loc_18003362D
0x180033620  mov     rax, [rcx]
0x180033623  mov     rax, [rax+10h]
0x180033627  call    _guard_dispatch_icall
0x18003362c  nop
0x18003362d  lea     rax, ppv
0x180033634  mov     [rsp+0C0h+ppv], rax; ppv
0x180033639  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180033640  xor     edx, edx; pUnkOuter
0x180033642  lea     r8d, [rdx+1]; dwClsContext
0x180033646  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18003364d  call    cs:__imp_CoCreateInstance
0x180033653  mov     [rbp+57h+var_80], eax
0x180033656  test    eax, eax
0x180033658  jns     short loc_180033661
0x18003365a  mov     edx, 23Ch
0x18003365f  jmp     short loc_1800336AA
0x180033661  xorps   xmm0, xmm0
0x180033664  movups  [rbp+57h+var_40], xmm0
0x180033668  mov     rcx, cs:ppv
0x18003366f  mov     rax, [rcx]
0x180033672  mov     [rsp+0C0h+var_98], 0
0x18003367b  mov     dword ptr [rsp+0C0h+ppv], 5; int
0x180033683  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x18003368a  lea     r8, [rbp+57h+var_40]
0x18003368e  lea     rdx, ?ConnectCallback@@YAJPEAUtagComCallData@@@Z; ConnectCallback(tagComCallData *)
0x180033695  mov     rax, [rax+18h]
0x180033699  call    _guard_dispatch_icall
0x18003369e  mov     [rbp+57h+var_80], eax
0x1800336a1  test    eax, eax
0x1800336a3  jns     short loc_1800336BF
0x1800336a5  mov     edx, 23Fh; void *
0x1800336aa  mov     rcx, [rbp+5Fh]; this
0x1800336ae  mov     r9d, eax; char *
0x1800336b1  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800336b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800336bd  jmp     short loc_1800336C4
0x1800336bf  xor     eax, eax
0x1800336c1  mov     [rbp+57h+var_80], eax
0x1800336c4  test    rbx, rbx
0x1800336c7  jz      short loc_1800336D9
0x1800336c9  mov     rax, [rbx]
0x1800336cc  mov     rcx, rbx
0x1800336cf  mov     rax, [rax+10h]
0x1800336d3  call    _guard_dispatch_icall
0x1800336d8  nop
0x1800336d9  mov     ebx, [rbp+57h+var_80]
0x1800336dc  test    rdi, rdi
0x1800336df  jz      short loc_1800336F1
0x1800336e1  mov     rax, [rdi]
0x1800336e4  mov     rcx, rdi
0x1800336e7  mov     rax, [rax+10h]
0x1800336eb  call    _guard_dispatch_icall
0x1800336f0  nop
0x1800336f1  test    rsi, rsi
0x1800336f4  jz      short loc_180033706
0x1800336f6  mov     rax, [rsi]
0x1800336f9  mov     rcx, rsi
0x1800336fc  mov     rax, [rax+10h]
0x180033700  call    _guard_dispatch_icall
0x180033705  nop
0x180033706  jmp     short loc_180033726
0x180033708  mov     rcx, [rbp+5Fh]; this
0x18003370c  mov     ebx, 8007000Eh
0x180033711  mov     r9d, ebx; char *
0x180033714  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18003371b  mov     edx, 22Dh; void *
  ... truncated ...
```
