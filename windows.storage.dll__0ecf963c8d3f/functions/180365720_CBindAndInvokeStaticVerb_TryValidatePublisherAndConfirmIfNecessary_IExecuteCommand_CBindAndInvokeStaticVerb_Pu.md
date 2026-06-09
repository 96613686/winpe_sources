# CBindAndInvokeStaticVerb::TryValidatePublisherAndConfirmIfNecessary(IExecuteCommand *,CBindAndInvokeStaticVerb::PublisherValidationResult *)

- ea: `0x180365720`
- end: `0x180365c98`
- name: `?TryValidatePublisherAndConfirmIfNecessary@CBindAndInvokeStaticVerb@@AEAAJPEAUIExecuteCommand@@PEAW4PublisherValidationResult@1@@Z`
- size: `1400`
- prototype: `__int64 __fastcall(CBindAndInvokeStaticVerb *__hidden this, struct IExecuteCommand *, enum CBindAndInvokeStaticVerb::PublisherValidationResult *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180150e94`

## callees

- `0x18000d6cc`
- `0x18000ee84`
- `0x1800371a8`
- `0x1800432f0`
- `0x1800d13a0`
- `0x1801daaf0`
- `0x1801dc4c0`
- `0x18026c22c`
- `0x180302dcc`
- `0x180365720`
- `0x180365ca0`
- `0x180365ccc`
- `0x180365f4c`
- `0x1803a4cb0`
- `0x180536d10`
- `0x180538070`
- `0x1805f9a24`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180365a52`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180365a52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803658b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803659e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803659f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365b52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365b98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365c66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803658b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803659e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803659f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365b52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365b98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365c2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180365c66`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CBindAndInvokeStaticVerb::TryValidatePublisherAndConfirmIfNecessary(
        CBindAndInvokeStaticVerb *this,
        struct IExecuteCommand *a2,
        enum CBindAndInvokeStaticVerb::PublisherValidationResult *a3)
{
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, __int64, _QWORD, __int64); // rbx
  __int64 v8; // rax
  const unsigned __int16 *v9; // rbx
  unsigned __int16 **v10; // r12
  int v11; // eax
  unsigned int v12; // ebx
  int v14; // r13d
  unsigned __int16 *v15; // rbx
  __int64 v16; // rsi
  unsigned int (__fastcall *v17)(__int64, __int64, unsigned __int16 **, _QWORD); // rdi
  __int64 v18; // rax
  int v19; // edi
  unsigned __int16 *v20; // rdi
  unsigned __int16 **v21; // rax
  int v22; // eax
  unsigned int v23; // edi
  unsigned __int16 **v24; // rax
  int v25; // eax
  unsigned int v26; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  LPVOID *v28; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  char v30; // [rsp+40h] [rbp-C0h]
  enum CBindAndInvokeStaticVerb::PublisherValidationResult *v31; // [rsp+48h] [rbp-B8h]
  unsigned int v32; // [rsp+54h] [rbp-ACh]
  LPCWCH lpString1; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v34; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v38; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v39; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v40[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v31 = a3;
  *(_DWORD *)a3 = 0;
  pv = 0;
  v6 = *((_QWORD *)this + 11);
  v7 = *(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v6 + 24LL);
  v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
  v7(v6, 458756, 0, v8);
  v9 = (const unsigned __int16 *)pv;
  wil::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v40);
  v40[0] = &DefaultAssocTelemetry::PublisherProtectedLaunch::`vftable';
  DefaultAssocTelemetry::PublisherProtectedLaunch::StartActivity(
    (DefaultAssocTelemetry::PublisherProtectedLaunch *)v40,
    v9);
  v34 = 0;
  ((void (__fastcall *)(struct IExecuteCommand *, GUID *, unsigned __int16 **))a2->lpVtbl->QueryInterface)(
    a2,
    &GUID_8e4a24b2_65d8_45b9_9e55_b76292bf44bb,
    &v34);
  v10 = (unsigned __int16 **)((char *)this + 256);
  if ( v34 )
  {
    LODWORD(lpString1) = 0;
    if ( (*(int (__fastcall **)(unsigned __int16 *, unsigned __int16 *, LPCWCH *))(*(_QWORD *)v34 + 24LL))(
           v34,
           *v10,
           &lpString1) >= 0 )
    {
      if ( (_DWORD)lpString1 )
      {
        *(_DWORD *)a3 = 1;
        DefaultAssocTelemetry::PublisherProtectedLaunch::Stop(
          (DefaultAssocTelemetry::PublisherProtectedLaunch *)v40,
          (const unsigned __int16 *)pv,
          1);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v34);
LABEL_53:
        DefaultAssocTelemetry::PublisherProtectedLaunch::~PublisherProtectedLaunch((DefaultAssocTelemetry::PublisherProtectedLaunch *)v40);
        if ( pv )
          CoTaskMemFree(pv);
        return 0;
      }
    }
  }
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v34);
  v37 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v11 = SHAssocEnumHandlersForProtocolByApplicationInternal(*v10, ASSOC_FILTER_NONE);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F1,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
LABEL_7:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    DefaultAssocTelemetry::PublisherProtectedLaunch::~PublisherProtectedLaunch((DefaultAssocTelemetry::PublisherProtectedLaunch *)v40);
    if ( pv )
      CoTaskMemFree(pv);
    return v12;
  }
  v14 = 0;
  v36 = 0;
  v15 = 0;
  v34 = 0;
  v38 = 0;
  do
  {
    v16 = v37;
    v17 = *(unsigned int (__fastcall **)(__int64, __int64, unsigned __int16 **, _QWORD))(*(_QWORD *)v37 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    if ( v17(v16, 1, &v36, 0) )
      break;
    v18 = *(_QWORD *)v36;
    v28 = &v38;
    v29 = 0;
    v30 = 1;
    v19 = (*(__int64 (__fastcall **)(unsigned __int16 *, unsigned __int64 *))(v18 + 32))(v36, &v29);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v28);
    if ( v19 >= 0 )
    {
      v20 = v36;
      if ( v15 != v36 )
      {
        if ( v36 )
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v36 + 8LL))(v36);
        v39 = v15;
        v15 = v20;
        v34 = v20;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
      }
      ++v14;
    }
  }
  while ( v14 <= 1 );
  if ( v14 != 1 )
  {
    if ( !v14 && *((_QWORD *)this + 13) && !(unsigned int)IsFileExtension(*v10) )
    {
      lpString1 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&lpString1);
      if ( (int)SHCreateAssocHandler(64, *v10, *v10, &lpString1) >= 0 )
      {
        v39 = 0;
        v24 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v39);
        v25 = CBindAndInvokeStaticVerb::InvokeHandler(this, (struct IAssocHandler *)lpString1, v24);
        v12 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1428,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
            (const char *)(unsigned int)v25,
            bIgnoreCase);
          if ( v39 )
            CoTaskMemFree(v39);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&lpString1);
          if ( v38 )
            CoTaskMemFree(v38);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
          goto LABEL_7;
        }
        *(_DWORD *)v31 = 4;
        DefaultAssocTelemetry::PublisherProtectedLaunch::Stop(
          (DefaultAssocTelemetry::PublisherProtectedLaunch *)v40,
          v39,
          4);
        if ( v39 )
          CoTaskMemFree(v39);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&lpString1);
LABEL_50:
        if ( v38 )
          CoTaskMemFree(v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        goto LABEL_53;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&lpString1);
    }
LABEL_47:
    v26 = *((_DWORD *)this + 104);
    v28 = (LPVOID *)this;
    v29 = __PAIR64__(v32, v26);
    v30 = 1;
    *((_DWORD *)this + 104) = 257;
    if ( (*((_BYTE *)this + 248) & 0x40) != 0 )
      *((_DWORD *)this + 104) = 265;
    CBindAndInvokeStaticVerb::InvokeOpenWith(this);
    *((_DWORD *)this + 104) = v26;
    *(_DWORD *)v31 = 3;
    DefaultAssocTelemetry::PublisherProtectedLaunch::Stop(
      (DefaultAssocTelemetry::PublisherProtectedLaunch *)v40,
      &WindowName,
      3);
    goto LABEL_50;
  }
  if ( !*((_QWORD *)this + 13) )
    goto LABEL_47;
  lpString1 = 0;
  v21 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString1);
  v22 = CBindAndInvokeStaticVerb::InvokeHandler(this, (struct IAssocHandler *)v15, v21);
  v23 = v22;
  if ( v22 >= 0 )
  {
    if ( CompareStringOrdinal(lpString1, -1, *v10, -1, 1) != 2 )
      SetDefaultAssociationForAssocHandler(*v10);
    *(_DWORD *)v31 = 2;
    DefaultAssocTelemetry::PublisherProtectedLaunch::Stop(
      (DefaultAssocTelemetry::PublisherProtectedLaunch *)v40,
      lpString1,
      2);
    if ( lpString1 )
      CoTaskMemFree((LPVOID)lpString1);
    goto LABEL_50;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1405,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\execassoc.cpp",
    (const char *)(unsigned int)v22,
    bIgnoreCase);
  if ( lpString1 )
    CoTaskMemFree((LPVOID)lpString1);
  if ( v38 )
    CoTaskMemFree(v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  DefaultAssocTelemetry::PublisherProtectedLaunch::~PublisherProtectedLaunch((DefaultAssocTelemetry::PublisherProtectedLaunch *)v40);
  if ( pv )
    CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x180365720  mov     [rsp-8+arg_18], rbx
0x180365725  push    rbp
0x180365726  push    rsi
0x180365727  push    rdi
0x180365728  push    r12
0x18036572a  push    r13
0x18036572c  push    r14
0x18036572e  push    r15
0x180365730  lea     rbp, [rsp-0F0h]
0x180365738  sub     rsp, 1F0h
0x18036573f  mov     rax, cs:__security_cookie
0x180365746  xor     rax, rsp
0x180365749  mov     [rbp+120h+var_40], rax
0x180365750  mov     r13, r8
0x180365753  mov     [rsp+220h+var_1D8], r8
0x180365758  mov     rsi, rdx
0x18036575b  mov     r14, rcx
0x18036575e  xor     r15d, r15d
0x180365761  mov     [r8], r15d
0x180365764  mov     [rsp+220h+pv], r15
0x180365769  mov     rdi, [rcx+58h]
0x18036576d  mov     rax, [rdi]
0x180365770  mov     rbx, [rax+18h]
0x180365774  lea     rcx, [rsp+220h+pv]
0x180365779  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18036577e  mov     r9, rax
0x180365781  xor     r8d, r8d
0x180365784  mov     edx, 70004h
0x180365789  mov     rcx, rdi
0x18036578c  mov     rax, rbx
0x18036578f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180365794  mov     rbx, [rsp+220h+pv]
0x180365799  lea     rdx, aPublisherprote; "PublisherProtectedLaunch"
0x1803657a0  lea     rcx, [rbp+120h+var_190]; struct wil::details::IFailureCallback *
0x1803657a4  call    ??0?$ActivityBase@VDefaultAssocLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DefaultAssocLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1803657a9  lea     rax, ??_7PublisherProtectedLaunch@DefaultAssocTelemetry@@6B@; const DefaultAssocTelemetry::PublisherProtectedLaunch::`vftable'
0x1803657b0  mov     [rbp+120h+var_190], rax
0x1803657b4  mov     rdx, rbx; unsigned __int16 *
0x1803657b7  lea     rcx, [rbp+120h+var_190]; this
0x1803657bb  call    ?StartActivity@PublisherProtectedLaunch@DefaultAssocTelemetry@@QEAAXPEBG@Z; DefaultAssocTelemetry::PublisherProtectedLaunch::StartActivity(ushort const *)
0x1803657c0  nop
0x1803657c1  mov     [rsp+220h+var_1C0], r15
0x1803657c6  mov     rax, [rsi]
0x1803657c9  lea     r8, [rsp+220h+var_1C0]
0x1803657ce  lea     rdx, _GUID_8e4a24b2_65d8_45b9_9e55_b76292bf44bb
0x1803657d5  mov     rcx, rsi
0x1803657d8  mov     rax, [rax]
0x1803657db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803657e0  nop
0x1803657e1  mov     rcx, [rsp+220h+var_1C0]
0x1803657e6  lea     r12, [r14+100h]
0x1803657ed  test    rcx, rcx
0x1803657f0  jz      short loc_180365842
0x1803657f2  mov     dword ptr [rsp+220h+lpString1], r15d
0x1803657f7  mov     rax, [rcx]
0x1803657fa  lea     r8, [rsp+220h+lpString1]
0x1803657ff  mov     rdx, [r12]
0x180365803  mov     rax, [rax+18h]
0x180365807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036580c  test    eax, eax
0x18036580e  js      short loc_180365842
0x180365810  cmp     dword ptr [rsp+220h+lpString1], r15d
0x180365815  jz      short loc_180365842
0x180365817  mov     r15d, 1
0x18036581d  mov     [r13+0], r15d
0x180365821  mov     r8d, r15d; int
0x180365824  mov     rdx, [rsp+220h+pv]; unsigned __int16 *
0x180365829  lea     rcx, [rbp+120h+var_190]; this
0x18036582d  call    ?Stop@PublisherProtectedLaunch@DefaultAssocTelemetry@@QEAAXPEBGH@Z; DefaultAssocTelemetry::PublisherProtectedLaunch::Stop(ushort const *,int)
0x180365832  nop
0x180365833  lea     rcx, [rsp+220h+var_1C0]
0x180365838  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18036583d  jmp     loc_180365C52
0x180365842  lea     rcx, [rsp+220h+var_1C0]
0x180365847  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18036584c  mov     [rsp+220h+var_1A8], r15
0x180365851  lea     rcx, [rsp+220h+var_1A8]
0x180365856  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036585b  lea     r9, [rsp+220h+var_1A8]
0x180365860  lea     r8, _GUID_973810ae_9599_4b88_9e4d_6ee98c9552da
0x180365867  xor     edx, edx; enum ASSOC_FILTER
0x180365869  mov     rcx, [r12]; unsigned __int16 *
0x18036586d  call    SHAssocEnumHandlersForProtocolByApplicationInternal
0x180365872  mov     ebx, eax
0x180365874  test    eax, eax
0x180365876  jns     short loc_1803658C0
0x180365878  mov     rcx, [rbp+128h]; this
0x18036587f  mov     r9d, eax; char *
0x180365882  lea     r8, aOnecoreuapShel_58; "onecoreuap\\shell\\windows.storage\\exe"...
0x180365889  mov     edx, 13F1h; void *
0x18036588e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180365893  nop
0x180365894  lea     rcx, [rsp+220h+var_1A8]
0x180365899  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036589e  nop
0x18036589f  lea     rcx, [rbp+120h+var_190]; this
0x1803658a3  call    ??1PublisherProtectedLaunch@DefaultAssocTelemetry@@QEAA@XZ; DefaultAssocTelemetry::PublisherProtectedLaunch::~PublisherProtectedLaunch(void)
0x1803658a8  nop
0x1803658a9  mov     rcx, [rsp+220h+pv]; pv
0x1803658ae  test    rcx, rcx
0x1803658b1  jz      short loc_1803658B9
0x1803658b3  call    cs:__imp_CoTaskMemFree
0x1803658b9  mov     eax, ebx
0x1803658bb  jmp     loc_180365C6E
0x1803658c0  mov     r13d, r15d
0x1803658c3  mov     [rsp+220h+var_1B0], r15
0x1803658c8  mov     rbx, r15
0x1803658cb  mov     [rsp+220h+var_1C0], rbx
0x1803658d0  mov     [rbp+120h+var_1A0], r15
0x1803658d4  mov     r15d, 1
0x1803658da  mov     rsi, [rsp+220h+var_1A8]
0x1803658df  mov     rax, [rsi]
0x1803658e2  mov     rdi, [rax+18h]
0x1803658e6  lea     rcx, [rsp+220h+var_1B0]
0x1803658eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803658f0  xor     r9d, r9d
0x1803658f3  lea     r8, [rsp+220h+var_1B0]
0x1803658f8  mov     edx, r15d
0x1803658fb  mov     rcx, rsi
0x1803658fe  mov     rax, rdi
0x180365901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180365906  xor     esi, esi
0x180365908  test    eax, eax
0x18036590a  jnz     short loc_180365989
0x18036590c  mov     rcx, [rsp+220h+var_1B0]
0x180365911  mov     rax, [rcx]
0x180365914  lea     rdx, [rbp+120h+var_1A0]
0x180365918  mov     [rsp+220h+var_1F0], rdx
0x18036591d  mov     [rsp+220h+var_1E8], rsi
0x180365922  mov     [rsp+220h+var_1E0], r15b
0x180365927  lea     rdx, [rsp+220h+var_1E8]
0x18036592c  mov     rax, [rax+20h]
0x180365930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180365935  mov     edi, eax
0x180365937  lea     rcx, [rsp+220h+var_1F0]
0x18036593c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180365941  shr     edi, 1Fh
0x180365944  xor     dil, r15b
0x180365947  jz      short loc_180365980
0x180365949  mov     rdi, [rsp+220h+var_1B0]
0x18036594e  cmp     rbx, rdi
0x180365951  jz      short loc_18036597D
0x180365953  test    rdi, rdi
0x180365956  jz      short loc_180365968
0x180365958  mov     rax, [rdi]
0x18036595b  mov     rcx, rdi
0x18036595e  mov     rax, [rax+8]
0x180365962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180365967  nop
0x180365968  mov     [rbp+120h+var_198], rbx
0x18036596c  mov     rbx, rdi
0x18036596f  mov     [rsp+220h+var_1C0], rbx
0x180365974  lea     rcx, [rbp+120h+var_198]
0x180365978  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036597d  add     r13d, r15d
0x180365980  cmp     r13d, r15d
0x180365983  jle     loc_1803658DA
0x180365989  cmp     r13d, r15d
0x18036598c  jnz     loc_180365A9F
0x180365992  cmp     [r14+68h], rsi
0x180365996  jz      loc_180365BB5
0x18036599c  mov     [rsp+220h+lpString1], rsi
0x1803659a1  lea     rcx, [rsp+220h+lpString1]
0x1803659a6  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1803659ab  mov     r8, rax; unsigned __int16 **
0x1803659ae  mov     rdx, rbx; struct IAssocHandler *
0x1803659b1  mov     rcx, r14; this
0x1803659b4  call    ?InvokeHandler@CBindAndInvokeStaticVerb@@AEAAJPEAUIAssocHandler@@PEAPEAG@Z; CBindAndInvokeStaticVerb::InvokeHandler(IAssocHandler *,ushort * *)
0x1803659b9  mov     edi, eax
0x1803659bb  test    eax, eax
0x1803659bd  jns     short loc_180365A3E
0x1803659bf  mov     rcx, [rbp+128h]; this
0x1803659c6  mov     r9d, eax; char *
0x1803659c9  lea     r8, aOnecoreuapShel_58; "onecoreuap\\shell\\windows.storage\\exe"...
0x1803659d0  mov     edx, 1405h; void *
0x1803659d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803659da  nop
0x1803659db  mov     rcx, [rsp+220h+lpString1]; pv
0x1803659e0  test    rcx, rcx
0x1803659e3  jz      short loc_1803659EC
0x1803659e5  call    cs:__imp_CoTaskMemFree
0x1803659eb  nop
0x1803659ec  mov     rcx, [rbp+120h+var_1A0]; pv
0x1803659f0  test    rcx, rcx
0x1803659f3  jz      short loc_1803659FC
0x1803659f5  call    cs:__imp_CoTaskMemFree
0x1803659fb  nop
0x1803659fc  lea     rcx, [rsp+220h+var_1C0]
0x180365a01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365a06  nop
0x180365a07  lea     rcx, [rsp+220h+var_1B0]
0x180365a0c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365a11  nop
0x180365a12  lea     rcx, [rsp+220h+var_1A8]
0x180365a17  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365a1c  nop
0x180365a1d  lea     rcx, [rbp+120h+var_190]; this
0x180365a21  call    ??1PublisherProtectedLaunch@DefaultAssocTelemetry@@QEAA@XZ; DefaultAssocTelemetry::PublisherProtectedLaunch::~PublisherProtectedLaunch(void)
0x180365a26  nop
0x180365a27  mov     rcx, [rsp+220h+pv]; pv
0x180365a2c  test    rcx, rcx
0x180365a2f  jz      short loc_180365A37
0x180365a31  call    cs:__imp_CoTaskMemFree
0x180365a37  mov     eax, edi
0x180365a39  jmp     loc_180365C6E
0x180365a3e  mov     [rsp+220h+bIgnoreCase], r15d; bIgnoreCase
0x180365a43  or      edx, 0FFFFFFFFh; cchCount1
0x180365a46  mov     r9d, edx; cchCount2
0x180365a49  mov     r8, [r12]; lpString2
0x180365a4d  mov     rcx, [rsp+220h+lpString1]; lpString1
0x180365a52  call    cs:__imp_CompareStringOrdinal
0x180365a58  mov     edi, 2
0x180365a5d  cmp     eax, edi
0x180365a5f  jz      short loc_180365A6D
0x180365a61  mov     r8, rbx
0x180365a64  mov     rcx, [r12]; unsigned __int16 *
0x180365a68  call    SetDefaultAssociationForAssocHandler
0x180365a6d  mov     rax, [rsp+220h+var_1D8]
0x180365a72  mov     [rax], edi
0x180365a74  mov     r8d, edi; int
0x180365a77  mov     rdx, [rsp+220h+lpString1]; unsigned __int16 *
0x180365a7c  lea     rcx, [rbp+120h+var_190]; this
0x180365a80  call    ?Stop@PublisherProtectedLaunch@DefaultAssocTelemetry@@QEAAXPEBGH@Z; DefaultAssocTelemetry::PublisherProtectedLaunch::Stop(ushort const *,int)
0x180365a85  nop
0x180365a86  mov     rcx, [rsp+220h+lpString1]; pv
0x180365a8b  test    rcx, rcx
0x180365a8e  jz      loc_180365C21
0x180365a94  call    cs:__imp_CoTaskMemFree
0x180365a9a  jmp     loc_180365C21
0x180365a9f  test    r13d, r13d
0x180365aa2  jnz     loc_180365BB5
0x180365aa8  cmp     [r14+68h], rsi
0x180365aac  jz      loc_180365BB5
0x180365ab2  mov     rcx, [r12]; unsigned __int16 *
0x180365ab6  call    ?IsFileExtension@@YAHPEBG@Z; IsFileExtension(ushort const *)
0x180365abb  test    eax, eax
0x180365abd  jnz     loc_180365BB5
0x180365ac3  mov     [rsp+220h+lpString1], rsi
0x180365ac8  lea     rcx, [rsp+220h+lpString1]
0x180365acd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365ad2  lea     r9, [rsp+220h+lpString1]
0x180365ad7  mov     r8, [r12]
0x180365adb  mov     rdx, r8
0x180365ade  lea     ecx, [r13+40h]
0x180365ae2  call    SHCreateAssocHandler
0x180365ae7  test    eax, eax
0x180365ae9  js      loc_180365BAB
0x180365aef  mov     [rbp+120h+var_198], rsi
0x180365af3  lea     rcx, [rbp+120h+var_198]
0x180365af7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180365afc  mov     r8, rax; unsigned __int16 **
0x180365aff  mov     rdx, [rsp+220h+lpString1]; struct IAssocHandler *
0x180365b04  mov     rcx, r14; this
0x180365b07  call    ?InvokeHandler@CBindAndInvokeStaticVerb@@AEAAJPEAUIAssocHandler@@PEAPEAG@Z; CBindAndInvokeStaticVerb::InvokeHandler(IAssocHandler *,ushort * *)
0x180365b0c  mov     ebx, eax
0x180365b0e  test    eax, eax
0x180365b10  jns     short loc_180365B73
0x180365b12  mov     rcx, [rbp+128h]; this
0x180365b19  mov     r9d, eax; char *
0x180365b1c  lea     r8, aOnecoreuapShel_58; "onecoreuap\\shell\\windows.storage\\exe"...
0x180365b23  mov     edx, 1428h; void *
0x180365b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180365b2d  nop
0x180365b2e  mov     rcx, [rbp+120h+var_198]; pv
0x180365b32  test    rcx, rcx
0x180365b35  jz      short loc_180365B3E
0x180365b37  call    cs:__imp_CoTaskMemFree
0x180365b3d  nop
0x180365b3e  lea     rcx, [rsp+220h+lpString1]
0x180365b43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365b48  nop
0x180365b49  mov     rcx, [rbp+120h+var_1A0]; pv
0x180365b4d  test    rcx, rcx
0x180365b50  jz      short loc_180365B59
0x180365b52  call    cs:__imp_CoTaskMemFree
0x180365b58  nop
0x180365b59  lea     rcx, [rsp+220h+var_1C0]
0x180365b5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365b63  nop
0x180365b64  lea     rcx, [rsp+220h+var_1B0]
0x180365b69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365b6e  jmp     loc_180365894
0x180365b73  mov     r8d, 4; int
0x180365b79  mov     rax, [rsp+220h+var_1D8]
0x180365b7e  mov     [rax], r8d
0x180365b81  mov     rdx, [rbp+120h+var_198]; unsigned __int16 *
0x180365b85  lea     rcx, [rbp+120h+var_190]; this
0x180365b89  call    ?Stop@PublisherProtectedLaunch@DefaultAssocTelemetry@@QEAAXPEBGH@Z; DefaultAssocTelemetry::PublisherProtectedLaunch::Stop(ushort const *,int)
0x180365b8e  nop
0x180365b8f  mov     rcx, [rbp+120h+var_198]; pv
0x180365b93  test    rcx, rcx
0x180365b96  jz      short loc_180365B9F
0x180365b98  call    cs:__imp_CoTaskMemFree
0x180365b9e  nop
0x180365b9f  lea     rcx, [rsp+220h+lpString1]
0x180365ba4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365ba9  jmp     short loc_180365C21
0x180365bab  lea     rcx, [rsp+220h+lpString1]
0x180365bb0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180365bb5  mov     ebx, [r14+1A0h]
  ... truncated ...
```
