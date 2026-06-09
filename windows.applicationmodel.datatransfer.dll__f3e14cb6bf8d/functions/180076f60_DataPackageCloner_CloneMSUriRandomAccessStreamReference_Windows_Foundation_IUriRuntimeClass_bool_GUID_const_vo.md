# DataPackageCloner::CloneMSUriRandomAccessStreamReference(Windows::Foundation::IUriRuntimeClass *,bool,_GUID const &,void * *)

- ea: `0x180076f60`
- end: `0x18007747f`
- name: `?CloneMSUriRandomAccessStreamReference@DataPackageCloner@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@_NAEBU_GUID@@PEAPEAX@Z`
- size: `1311`
- prototype: `__int64 __fastcall(DataPackageCloner *__hidden this, struct Windows::Foundation::IUriRuntimeClass *, bool, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180077fbc`

## callees

- `0x180002ad0`
- `0x180008b68`
- `0x180043b6c`
- `0x180048954`
- `0x180076f60`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800770bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180077030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800770bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800772da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007739a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077422`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077075`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800772da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007739a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077422`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180076fc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180076fc1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800771ad`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800771ad`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller_ForPackage` at `0x1800770de`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller_ForPackage` at `0x1800770de`

## string_xrefs

- `0x18007716c`: `Windows.Storage.Streams.RandomAccessStreamReference`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DataPackageCloner::CloneMSUriRandomAccessStreamReference(
        HSTRING *this,
        struct Windows::Foundation::IUriRuntimeClass *a2,
        unsigned __int8 a3,
        const struct _GUID *a4,
        void **a5)
{
  int v6; // r15d
  HRESULT v9; // eax
  unsigned int v10; // ebx
  LPVOID v11; // rcx
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, struct Windows::Foundation::IUriRuntimeClass *, PCWSTR, LPVOID *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v16; // eax
  LPVOID v17; // rcx
  int v18; // ebx
  PCWSTR v19; // rax
  int StorageItemFromPath_FullTrustCaller_ForPackage; // eax
  __int64 v21; // rcx
  LPVOID v22; // rcx
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  HSTRING v26; // rbx
  __int64 v27; // rcx
  int ActivationFactory; // eax
  __int64 v29; // rcx
  __int64 v30; // rcx
  LPVOID v31; // rcx
  int v32; // eax
  __int64 (__fastcall ***v33)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  LPVOID v36; // rcx
  int v37; // eax
  __int64 (__fastcall ***v38)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  LPVOID v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  LPVOID v45; // rcx
  int ppv; // [rsp+20h] [rbp-51h]
  int ppva; // [rsp+20h] [rbp-51h]
  LPVOID v48; // [rsp+30h] [rbp-41h] BYREF
  __int64 v49; // [rsp+38h] [rbp-39h] BYREF
  __int64 v50; // [rsp+40h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-29h] BYREF
  __int64 v52; // [rsp+50h] [rbp-21h]
  __int64 v53; // [rsp+58h] [rbp-19h]
  __int64 (__fastcall ***v54)(_QWORD, const struct _GUID *, void **); // [rsp+60h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-9h] BYREF
  HSTRING string; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v6 = a3;
  *a5 = 0;
  v48 = 0;
  v9 = CoCreateInstance(
         &GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169,
         0,
         1u,
         &GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7,
         &v48);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x184,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    v11 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v10;
  }
  pv = 0;
  v52 = 0;
  v53 = 0;
  v13 = v48;
  v14 = *(__int64 (__fastcall **)(LPVOID, struct Windows::Foundation::IUriRuntimeClass *, PCWSTR, LPVOID *))(*(_QWORD *)v48 + 40LL);
  v52 = -1;
  v53 = -1;
  StringRawBuffer = WindowsGetStringRawBuffer(this[5], 0);
  v16 = v14(v13, a2, StringRawBuffer, &pv);
  v10 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x189,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v16,
      ppv);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v52 = 0;
    v53 = 0;
    v17 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v10;
  }
  v50 = 0;
  v18 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v50);
  v19 = WindowsGetStringRawBuffer(this[5], 0);
  ppva = v18;
  StorageItemFromPath_FullTrustCaller_ForPackage = CreateStorageItemFromPath_FullTrustCaller_ForPackage(
                                                     pv,
                                                     (unsigned int)((v6 << 7) + 64),
                                                     v19,
                                                     &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea);
  v10 = StorageItemFromPath_FullTrustCaller_ForPackage;
  if ( StorageItemFromPath_FullTrustCaller_ForPackage < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)StorageItemFromPath_FullTrustCaller_ForPackage,
      ppva);
    v21 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v52 = 0;
    v53 = 0;
    v22 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v10;
  }
  v49 = 0;
  string = 0;
  v23 = WindowsCreateStringReference(
          L"Windows.Storage.Streams.RandomAccessStreamReference",
          0x33u,
          &hstringHeader,
          &string);
  if ( v23 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    JUMPOUT(0x18007747ELL);
  }
  v26 = string;
  v27 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  ActivationFactory = RoGetActivationFactory(v26, &GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964, &v49);
  v10 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)ActivationFactory,
      ppva);
    v29 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v52 = 0;
    v53 = 0;
    v31 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
    }
    return v10;
  }
  v54 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 48LL))(v49, v50, &v54);
  v10 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x197,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v32,
      ppva);
    v33 = v54;
    if ( v54 )
    {
      v54 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v33)[2])(v33);
    }
    v34 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v52 = 0;
    v53 = 0;
    v36 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
    }
    return v10;
  }
  v37 = (**v54)(v54, a4, a5);
  v10 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v37,
      ppva);
    v38 = v54;
    if ( v54 )
    {
      v54 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v38)[2])(v38);
    }
    v39 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v52 = 0;
    v53 = 0;
    v41 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v41 + 16LL))(v41);
    }
    return v10;
  }
  v42 = v54;
  if ( v54 )
  {
    v54 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v42)[2])(v42);
  }
  v43 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v52 = 0;
  v53 = 0;
  v45 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v45 + 16LL))(v45);
  }
  return 0;
}

```

## disassembly

```asm
0x180076f60  mov     [rsp-8+arg_10], rbx
0x180076f65  push    rbp
0x180076f66  push    rsi
0x180076f67  push    rdi
0x180076f68  push    r12
0x180076f6a  push    r13
0x180076f6c  push    r14
0x180076f6e  push    r15
0x180076f70  lea     rbp, [rsp-1Fh]
0x180076f75  sub     rsp, 90h
0x180076f7c  mov     rax, cs:__security_cookie
0x180076f83  xor     rax, rsp
0x180076f86  mov     [rbp+4Fh+var_38], rax
0x180076f8a  mov     r13, r9
0x180076f8d  movzx   r15d, r8b
0x180076f91  mov     r12, rdx
0x180076f94  mov     rsi, rcx
0x180076f97  mov     r14, [rbp+4Fh+arg_20]
0x180076f9b  xor     edi, edi
0x180076f9d  mov     [r14], rdi
0x180076fa0  mov     [rbp+4Fh+var_90], rdi
0x180076fa4  lea     rax, [rbp+4Fh+var_90]
0x180076fa8  mov     qword ptr [rsp+0C0h+ppv], rax; int
0x180076fad  lea     r9, _GUID_428bb582_2a87_4ea0_b529_30067cc4a4d7; riid
0x180076fb4  xor     edx, edx; pUnkOuter
0x180076fb6  lea     r8d, [rdi+1]; dwClsContext
0x180076fba  lea     rcx, _GUID_a8ca4495_65ab_4333_9ff9_4feb6fbf5169; rclsid
0x180076fc1  call    cs:__imp_CoCreateInstance
0x180076fc7  mov     ebx, eax
0x180076fc9  test    eax, eax
0x180076fcb  jns     short loc_180077007
0x180076fcd  mov     rcx, [rbp+57h]; this
0x180076fd1  mov     r9d, eax; char *
0x180076fd4  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180076fdb  mov     edx, 184h; void *
0x180076fe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076fe5  nop
0x180076fe6  mov     rcx, [rbp+4Fh+var_90]
0x180076fea  test    rcx, rcx
0x180076fed  jz      short loc_180077000
0x180076fef  mov     [rbp+4Fh+var_90], rdi
0x180076ff3  mov     rax, [rcx]
0x180076ff6  mov     rax, [rax+10h]
0x180076ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076fff  nop
0x180077000  mov     eax, ebx
0x180077002  jmp     loc_180077450
0x180077007  mov     [rbp+4Fh+pv], rdi
0x18007700b  mov     [rbp+4Fh+var_70], rdi
0x18007700f  mov     [rbp+4Fh+var_68], rdi
0x180077013  mov     rdi, [rbp+4Fh+var_90]
0x180077017  mov     rax, [rdi]
0x18007701a  mov     rbx, [rax+28h]
0x18007701e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077022  mov     [rbp+4Fh+var_70], rax
0x180077026  mov     [rbp+4Fh+var_68], rax
0x18007702a  xor     edx, edx; length
0x18007702c  mov     rcx, [rsi+28h]; string
0x180077030  call    cs:__imp_WindowsGetStringRawBuffer
0x180077036  lea     r9, [rbp+4Fh+pv]
0x18007703a  mov     r8, rax
0x18007703d  mov     rdx, r12
0x180077040  mov     rcx, rdi
0x180077043  mov     rax, rbx
0x180077046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007704b  mov     ebx, eax
0x18007704d  xor     edi, edi
0x18007704f  test    eax, eax
0x180077051  jns     short loc_1800770A6
0x180077053  mov     rcx, [rbp+57h]; this
0x180077057  mov     r9d, eax; char *
0x18007705a  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180077061  mov     edx, 189h; void *
0x180077066  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007706b  nop
0x18007706c  mov     rcx, [rbp+4Fh+pv]; pv
0x180077070  test    rcx, rcx
0x180077073  jz      short loc_18007707F
0x180077075  call    cs:__imp_CoTaskMemFree
0x18007707b  mov     [rbp+4Fh+pv], rdi
0x18007707f  mov     [rbp+4Fh+var_70], rdi
0x180077083  mov     [rbp+4Fh+var_68], rdi
0x180077087  mov     rcx, [rbp+4Fh+var_90]
0x18007708b  test    rcx, rcx
0x18007708e  jz      short loc_1800770A1
0x180077090  mov     [rbp+4Fh+var_90], rdi
0x180077094  mov     rax, [rcx]
0x180077097  mov     rax, [rax+10h]
0x18007709b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800770a0  nop
0x1800770a1  jmp     loc_180077000
0x1800770a6  mov     [rbp+4Fh+var_80], rdi
0x1800770aa  lea     rcx, [rbp+4Fh+var_80]
0x1800770ae  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x1800770b3  mov     rbx, rax
0x1800770b6  xor     edx, edx; length
0x1800770b8  mov     rcx, [rsi+28h]; string
0x1800770bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800770c2  mov     edx, r15d
0x1800770c5  shl     edx, 7
0x1800770c8  add     edx, 40h ; '@'
0x1800770cb  mov     qword ptr [rsp+0C0h+ppv], rbx; int
0x1800770d0  lea     r9, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x1800770d7  mov     r8, rax
0x1800770da  mov     rcx, [rbp+4Fh+pv]
0x1800770de  call    cs:__imp_CreateStorageItemFromPath_FullTrustCaller_ForPackage
0x1800770e4  mov     ebx, eax
0x1800770e6  test    eax, eax
0x1800770e8  jns     short loc_180077157
0x1800770ea  mov     rcx, [rbp+57h]; this
0x1800770ee  mov     r9d, eax; char *
0x1800770f1  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800770f8  mov     edx, 191h; void *
0x1800770fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077102  nop
0x180077103  mov     rcx, [rbp+4Fh+var_80]
0x180077107  test    rcx, rcx
0x18007710a  jz      short loc_18007711D
0x18007710c  mov     [rbp+4Fh+var_80], rdi
0x180077110  mov     rax, [rcx]
0x180077113  mov     rax, [rax+10h]
0x180077117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007711c  nop
0x18007711d  mov     rcx, [rbp+4Fh+pv]; pv
0x180077121  test    rcx, rcx
0x180077124  jz      short loc_180077130
0x180077126  call    cs:__imp_CoTaskMemFree
0x18007712c  mov     [rbp+4Fh+pv], rdi
0x180077130  mov     [rbp+4Fh+var_70], rdi
0x180077134  mov     [rbp+4Fh+var_68], rdi
0x180077138  mov     rcx, [rbp+4Fh+var_90]
0x18007713c  test    rcx, rcx
0x18007713f  jz      short loc_180077152
0x180077141  mov     [rbp+4Fh+var_90], rdi
0x180077145  mov     rax, [rcx]
0x180077148  mov     rax, [rax+10h]
0x18007714c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077151  nop
0x180077152  jmp     loc_180077000
0x180077157  mov     [rbp+4Fh+var_88], rdi
0x18007715b  mov     [rbp+4Fh+string], rdi
0x18007715f  lea     r9, [rbp+4Fh+string]; string
0x180077163  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x180077167  mov     edx, 33h ; '3'; length
0x18007716c  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_RandomAccessStreamReference@@3QBGB; "Windows.Storage.Streams.RandomAccessStr"...
0x180077173  call    cs:__imp_WindowsCreateStringReference
0x180077179  test    eax, eax
0x18007717b  js      loc_180077477
0x180077181  mov     rbx, [rbp+4Fh+string]
0x180077185  mov     rcx, [rbp+4Fh+var_88]
0x180077189  test    rcx, rcx
0x18007718c  jz      short loc_18007719F
0x18007718e  mov     [rbp+4Fh+var_88], rdi
0x180077192  mov     rax, [rcx]
0x180077195  mov     rax, [rax+10h]
0x180077199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007719e  nop
0x18007719f  lea     r8, [rbp+4Fh+var_88]
0x1800771a3  lea     rdx, _GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964
0x1800771aa  mov     rcx, rbx
0x1800771ad  call    cs:__imp_RoGetActivationFactory
0x1800771b3  mov     ebx, eax
0x1800771b5  test    eax, eax
0x1800771b7  jns     loc_180077244
0x1800771bd  mov     rcx, [rbp+57h]; this
0x1800771c1  mov     r9d, eax; char *
0x1800771c4  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800771cb  mov     edx, 194h; void *
0x1800771d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800771d5  nop
0x1800771d6  mov     rcx, [rbp+4Fh+var_88]
0x1800771da  test    rcx, rcx
0x1800771dd  jz      short loc_1800771F0
0x1800771df  mov     [rbp+4Fh+var_88], rdi
0x1800771e3  mov     rax, [rcx]
0x1800771e6  mov     rax, [rax+10h]
0x1800771ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800771ef  nop
0x1800771f0  mov     rcx, [rbp+4Fh+var_80]
0x1800771f4  test    rcx, rcx
0x1800771f7  jz      short loc_18007720A
0x1800771f9  mov     [rbp+4Fh+var_80], rdi
0x1800771fd  mov     rax, [rcx]
0x180077200  mov     rax, [rax+10h]
0x180077204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077209  nop
0x18007720a  mov     rcx, [rbp+4Fh+pv]; pv
0x18007720e  test    rcx, rcx
0x180077211  jz      short loc_18007721D
0x180077213  call    cs:__imp_CoTaskMemFree
0x180077219  mov     [rbp+4Fh+pv], rdi
0x18007721d  mov     [rbp+4Fh+var_70], rdi
0x180077221  mov     [rbp+4Fh+var_68], rdi
0x180077225  mov     rcx, [rbp+4Fh+var_90]
0x180077229  test    rcx, rcx
0x18007722c  jz      short loc_18007723F
0x18007722e  mov     [rbp+4Fh+var_90], rdi
0x180077232  mov     rax, [rcx]
0x180077235  mov     rax, [rax+10h]
0x180077239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007723e  nop
0x18007723f  jmp     loc_180077000
0x180077244  mov     [rbp+4Fh+var_60], rdi
0x180077248  mov     rcx, [rbp+4Fh+var_88]
0x18007724c  mov     rax, [rcx]
0x18007724f  lea     r8, [rbp+4Fh+var_60]
0x180077253  mov     rdx, [rbp+4Fh+var_80]
0x180077257  mov     rax, [rax+30h]
0x18007725b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077260  mov     ebx, eax
0x180077262  test    eax, eax
0x180077264  jns     loc_18007730B
0x18007726a  mov     rcx, [rbp+57h]; this
0x18007726e  mov     r9d, eax; char *
0x180077271  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180077278  mov     edx, 197h; void *
0x18007727d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077282  nop
0x180077283  mov     rcx, [rbp+4Fh+var_60]
0x180077287  test    rcx, rcx
0x18007728a  jz      short loc_18007729D
0x18007728c  mov     [rbp+4Fh+var_60], rdi
0x180077290  mov     rax, [rcx]
0x180077293  mov     rax, [rax+10h]
0x180077297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007729c  nop
0x18007729d  mov     rcx, [rbp+4Fh+var_88]
0x1800772a1  test    rcx, rcx
0x1800772a4  jz      short loc_1800772B7
0x1800772a6  mov     [rbp+4Fh+var_88], rdi
0x1800772aa  mov     rax, [rcx]
0x1800772ad  mov     rax, [rax+10h]
0x1800772b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772b6  nop
0x1800772b7  mov     rcx, [rbp+4Fh+var_80]
0x1800772bb  test    rcx, rcx
0x1800772be  jz      short loc_1800772D1
0x1800772c0  mov     [rbp+4Fh+var_80], rdi
0x1800772c4  mov     rax, [rcx]
0x1800772c7  mov     rax, [rax+10h]
0x1800772cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772d0  nop
0x1800772d1  mov     rcx, [rbp+4Fh+pv]; pv
0x1800772d5  test    rcx, rcx
0x1800772d8  jz      short loc_1800772E4
0x1800772da  call    cs:__imp_CoTaskMemFree
0x1800772e0  mov     [rbp+4Fh+pv], rdi
0x1800772e4  mov     [rbp+4Fh+var_70], rdi
0x1800772e8  mov     [rbp+4Fh+var_68], rdi
0x1800772ec  mov     rcx, [rbp+4Fh+var_90]
0x1800772f0  test    rcx, rcx
0x1800772f3  jz      short loc_180077306
0x1800772f5  mov     [rbp+4Fh+var_90], rdi
0x1800772f9  mov     rax, [rcx]
0x1800772fc  mov     rax, [rax+10h]
0x180077300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077305  nop
0x180077306  jmp     loc_180077000
0x18007730b  mov     rcx, [rbp+4Fh+var_60]
0x18007730f  mov     rax, [rcx]
0x180077312  mov     r8, r14
0x180077315  mov     rdx, r13
0x180077318  mov     rax, [rax]
0x18007731b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077320  mov     ebx, eax
0x180077322  test    eax, eax
0x180077324  jns     loc_1800773CB
0x18007732a  mov     rcx, [rbp+57h]; this
0x18007732e  mov     r9d, eax; char *
0x180077331  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180077338  mov     edx, 198h; void *
0x18007733d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077342  nop
0x180077343  mov     rcx, [rbp+4Fh+var_60]
0x180077347  test    rcx, rcx
0x18007734a  jz      short loc_18007735D
0x18007734c  mov     [rbp+4Fh+var_60], rdi
0x180077350  mov     rax, [rcx]
0x180077353  mov     rax, [rax+10h]
0x180077357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007735c  nop
0x18007735d  mov     rcx, [rbp+4Fh+var_88]
0x180077361  test    rcx, rcx
0x180077364  jz      short loc_180077377
0x180077366  mov     [rbp+4Fh+var_88], rdi
0x18007736a  mov     rax, [rcx]
0x18007736d  mov     rax, [rax+10h]
0x180077371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077376  nop
0x180077377  mov     rcx, [rbp+4Fh+var_80]
0x18007737b  test    rcx, rcx
0x18007737e  jz      short loc_180077391
0x180077380  mov     [rbp+4Fh+var_80], rdi
0x180077384  mov     rax, [rcx]
0x180077387  mov     rax, [rax+10h]
0x18007738b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077390  nop
0x180077391  mov     rcx, [rbp+4Fh+pv]; pv
0x180077395  test    rcx, rcx
0x180077398  jz      short loc_1800773A4
  ... truncated ...
```
