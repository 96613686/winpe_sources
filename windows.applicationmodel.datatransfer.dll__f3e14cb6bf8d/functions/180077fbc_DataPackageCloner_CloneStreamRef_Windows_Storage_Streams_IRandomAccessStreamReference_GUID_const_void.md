# DataPackageCloner::CloneStreamRef(Windows::Storage::Streams::IRandomAccessStreamReference *,_GUID const &,void * *)

- ea: `0x180077fbc`
- end: `0x180078ca7`
- name: `?CloneStreamRef@DataPackageCloner@@AEAAJPEAUIRandomAccessStreamReference@Streams@Storage@Windows@@AEBU_GUID@@PEAPEAX@Z`
- size: `3307`
- prototype: `__int64 __fastcall(DataPackageCloner *__hidden this, struct Windows::Storage::Streams::IRandomAccessStreamReference *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007659c`
- `0x180076aac`

## callees

- `0x180002ad0`
- `0x180008b68`
- `0x180043b6c`
- `0x180048954`
- `0x180076f60`
- `0x180077fbc`
- `0x180078cb0`
- `0x180079938`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007863f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800786e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007876f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078908`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007894f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078603`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007863f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800786e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007876f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078810`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180078908`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007894f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007823d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800786a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800787ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800789fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007823d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800786a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800787ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800789fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800786bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800787e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800786bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800787e7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800780c6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800780c6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180078277`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180078a36`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180078277`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180078a36`

## string_xrefs

- `0x180078236`: `Windows.Storage.Streams.RandomAccessStreamReference`
- `0x1800789f5`: `Windows.Storage.Streams.RandomAccessStreamReference`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall DataPackageCloner::CloneStreamRef(
        DataPackageCloner *this,
        struct Windows::Storage::Streams::IRandomAccessStreamReference *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, GUID *, __int64); // rbx
  __int64 v16; // rax
  int v17; // eax
  HSTRING v18; // rcx
  __int64 v19; // rcx
  void **v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  HSTRING v23; // rcx
  __int64 v24; // rcx
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  int v28; // eax
  struct Windows::Foundation::IUriRuntimeClass *v29; // rcx
  __int64 v30; // rcx
  HSTRING v31; // rcx
  __int64 v32; // rcx
  int v33; // eax
  __int64 (__fastcall ***v34)(_QWORD, const struct _GUID *, void **); // rcx
  struct Windows::Foundation::IUriRuntimeClass *v35; // rcx
  __int64 v36; // rcx
  HSTRING v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  __int64 (__fastcall ***v40)(_QWORD, const struct _GUID *, void **); // rcx
  struct Windows::Foundation::IUriRuntimeClass *v41; // rcx
  __int64 v42; // rcx
  HSTRING v43; // rcx
  __int64 v44; // rcx
  __int64 (__fastcall ***v45)(_QWORD, const struct _GUID *, void **); // rcx
  struct Windows::Foundation::IUriRuntimeClass *v46; // rcx
  __int64 v47; // rcx
  void *v48; // rcx
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, GUID *, __int64); // rbx
  __int64 v51; // rax
  int v52; // eax
  struct Windows::Foundation::IUriRuntimeClass *v53; // rcx
  __int64 v54; // rcx
  int v55; // eax
  struct Windows::Foundation::IUriRuntimeClass *v56; // rcx
  __int64 v57; // rcx
  struct Windows::Foundation::IUriRuntimeClass *v58; // rdi
  __int64 (__fastcall *v59)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v60; // eax
  struct Windows::Foundation::IUriRuntimeClass *v61; // rcx
  __int64 v62; // rcx
  HSTRING v63; // rbx
  HRESULT v64; // eax
  int v65; // edx
  unsigned int v66; // r8d
  HRESULT v67; // eax
  struct Windows::Foundation::IUriRuntimeClass *v68; // rcx
  __int64 v69; // rcx
  int v70; // eax
  struct Windows::Foundation::IUriRuntimeClass *v71; // rcx
  __int64 v72; // rcx
  HSTRING v73; // rbx
  HRESULT v74; // eax
  int v75; // edx
  unsigned int v76; // r8d
  HRESULT v77; // eax
  struct Windows::Foundation::IUriRuntimeClass *v78; // rcx
  __int64 v79; // rcx
  int v80; // eax
  struct Windows::Foundation::IUriRuntimeClass *v81; // rcx
  __int64 v82; // rcx
  int v83; // eax
  struct Windows::Foundation::IUriRuntimeClass *v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rdi
  __int64 (__fastcall *v87)(__int64, GUID *, __int64); // rbx
  __int64 v88; // rax
  int v89; // eax
  struct Windows::Foundation::IUriRuntimeClass *v90; // rcx
  __int64 v91; // rcx
  HRESULT v92; // eax
  int v93; // edx
  unsigned int v94; // r8d
  HSTRING v95; // rbx
  HSTRING v96; // rcx
  int ActivationFactory; // eax
  HSTRING v98; // rcx
  struct Windows::Foundation::IUriRuntimeClass *v99; // rcx
  __int64 v100; // rcx
  int v101; // eax
  __int64 (__fastcall ***v102)(_QWORD, const struct _GUID *, void **); // rcx
  HSTRING v103; // rcx
  struct Windows::Foundation::IUriRuntimeClass *v104; // rcx
  __int64 v105; // rcx
  int v106; // eax
  __int64 (__fastcall ***v107)(_QWORD, const struct _GUID *, void **); // rcx
  HSTRING v108; // rcx
  struct Windows::Foundation::IUriRuntimeClass *v109; // rcx
  __int64 v110; // rcx
  __int64 (__fastcall ***v111)(_QWORD, const struct _GUID *, void **); // rcx
  HSTRING v112; // rcx
  __int64 v113; // rcx
  int v114; // [rsp+20h] [rbp-49h]
  int v115; // [rsp+20h] [rbp-49h]
  int v116; // [rsp+20h] [rbp-49h]
  struct Windows::Foundation::IUriRuntimeClass *v117; // [rsp+30h] [rbp-39h] BYREF
  __int64 v118; // [rsp+38h] [rbp-31h] BYREF
  HSTRING string2; // [rsp+40h] [rbp-29h] BYREF
  INT32 result[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v121)(_QWORD, const struct _GUID *, void **); // [rsp+50h] [rbp-19h] BYREF
  int v122; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a4 = 0;
  v118 = 0;
  v7 = (**(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IRandomAccessStreamReference *, GUID *, __int64 *))a2)(
         a2,
         &GUID_3fe8e0e3_eb50_4682_b91d_21028012a049,
         &v118);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v7,
      v114);
    v9 = v118;
    if ( v118 )
    {
      v118 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v8;
  }
  v122 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v118 + 24LL))(v118, &v122);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v11,
      v114);
    v12 = v118;
    if ( v118 )
    {
      v118 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v8;
  }
  switch ( v122 )
  {
    case 1:
      v117 = 0;
      v86 = v118;
      v87 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v118 + 32LL);
      v88 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v117);
      v89 = v87(v86, &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea, v88);
      v8 = v89;
      if ( v89 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11D,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
          (const char *)(unsigned int)v89,
          v114);
        v90 = v117;
        if ( v117 )
        {
          v117 = 0;
          (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v90 + 16LL))(v90);
        }
        v91 = v118;
        if ( v118 )
        {
          v118 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        }
        return v8;
      }
      string2 = 0;
      string = 0;
      v92 = WindowsCreateStringReference(
              L"Windows.Storage.Streams.RandomAccessStreamReference",
              0x33u,
              &hstringHeader,
              &string);
      if ( v92 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v92, v93, v94);
LABEL_175:
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
        goto LABEL_176;
      }
      v95 = string;
      v96 = string2;
      if ( string2 )
      {
        string2 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v96 + 16LL))(v96);
      }
      ActivationFactory = RoGetActivationFactory(v95, &GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964, &string2);
      v8 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
          (const char *)(unsigned int)ActivationFactory,
          v114);
        v98 = string2;
        if ( string2 )
        {
          string2 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v98 + 16LL))(v98);
        }
        v99 = v117;
        if ( v117 )
        {
          v117 = 0;
          (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v99 + 16LL))(v99);
        }
        v100 = v118;
        if ( v118 )
        {
          v118 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v100 + 16LL))(v100);
        }
        return v8;
      }
      v121 = 0;
      v101 = (*(__int64 (__fastcall **)(HSTRING, struct Windows::Foundation::IUriRuntimeClass *, _QWORD))(*(_QWORD *)string2 + 48LL))(
               string2,
               v117,
               &v121);
      v8 = v101;
      if ( v101 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x124,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
          (const char *)(unsigned int)v101,
          v114);
        v102 = v121;
        if ( v121 )
        {
          v121 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v102)[2])(v102);
        }
        v103 = string2;
        if ( string2 )
        {
          string2 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v103 + 16LL))(v103);
        }
        v104 = v117;
        if ( v117 )
        {
          v117 = 0;
          (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v104 + 16LL))(v104);
        }
        v105 = v118;
        if ( v118 )
        {
          v118 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
        }
        return v8;
      }
      v106 = (**v121)(v121, a3, a4);
      v8 = v106;
      if ( v106 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x126,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
          (const char *)(unsigned int)v106,
          v114);
        v107 = v121;
        if ( v121 )
        {
          v121 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v107)[2])(v107);
        }
        v108 = string2;
        if ( string2 )
        {
          string2 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v108 + 16LL))(v108);
        }
        v109 = v117;
        if ( v117 )
        {
          v117 = 0;
          (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v109 + 16LL))(v109);
        }
        v110 = v118;
        if ( v118 )
        {
          v118 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v110 + 16LL))(v110);
        }
        return v8;
      }
      v111 = v121;
      if ( v121 )
      {
        v121 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v111)[2])(v111);
      }
      v112 = string2;
      if ( string2 )
      {
        string2 = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v112 + 16LL))(v112);
      }
      break;
    case 2:
      v117 = 0;
      v49 = v118;
      v50 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v118 + 32LL);
      v51 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v117);
      v52 = v50(v49, &GUID_9e365e57_48b2_4160_956f_c7385120bbfc, v51);
      v8 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13E,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
          (const char *)(unsigned int)v52,
          v114);
        v53 = v117;
        if ( v117 )
        {
          v117 = 0;
          (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v53 + 16LL))(v53);
        }
        v54 = v118;
        if ( v118 )
        {
          v118 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
        }
        return v8;
      }
      if ( *((_BYTE *)this + 16) )
      {
        v55 = DataPackageCloner::CloneUriRandomAccessStreamReference(this, v117, a3, a4);
        v8 = v55;
        if ( v55 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x142,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
            (const char *)(unsigned int)v55,
            v114);
          v56 = v117;
          if ( v117 )
          {
            v117 = 0;
            (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v56 + 16LL))(v56);
          }
          v57 = v118;
          if ( v118 )
          {
            v118 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          }
          return v8;
        }
      }
      else
      {
        string2 = 0;
        v58 = v117;
        v59 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)v117
                                                                                                  + 136LL);
        WindowsDeleteString(0);
        string2 = 0;
        v60 = v59(v58, &string2);
        v8 = v60;
        if ( v60 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x148,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
            (const char *)(unsigned int)v60,
            v114);
          WindowsDeleteString(string2);
          string2 = 0;
          v61 = v117;
          if ( v117 )
          {
            v117 = 0;
            (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v61 + 16LL))(v61);
          }
          v62 = v118;
          if ( v118 )
          {
            v118 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          }
          return v8;
        }
        result[0] = 0;
        v63 = string2;
        string = 0;
        v64 = WindowsCreateStringReference(L"ms-appdata", 0xAu, &hstringHeader, &string);
        if ( v64 < 0 )
        {
LABEL_176:
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v64, v65, v66);
          __debugbreak();
        }
        v67 = WindowsCompareStringOrdinal(string, v63, result);
        v8 = v67;
        if ( v67 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14D,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
            (const char *)(unsigned int)v67,
            v114);
          WindowsDeleteString(string2);
          string2 = 0;
          v68 = v117;
          if ( v117 )
          {
            v117 = 0;
            (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v68 + 16LL))(v68);
          }
          v69 = v118;
          if ( v118 )
          {
            v118 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
          }
          return v8;
        }
        if ( result[0] )
        {
          v73 = string2;
          string = 0;
          v74 = WindowsCreateStringReference(L"ms-appx", 7u, &hstringHeader, &string);
          if ( v74 < 0 )
          {
            Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v74, v75, v76);
            JUMPOUT(0x180078CA6LL);
          }
          v77 = WindowsCompareStringOrdinal(string, v73, result);
          v8 = v77;
          if ( v77 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x155,
              (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
              (const char *)(unsigned int)v77,
              v114);
            WindowsDeleteString(string2);
            string2 = 0;
            v78 = v117;
            if ( v117 )
            {
              v117 = 0;
              (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v78 + 16LL))(v78);
            }
            v79 = v118;
            if ( v118 )
            {
              v118 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
            }
            return v8;
          }
          if ( result[0] )
          {
            v83 = DataPackageCloner::CloneUriRandomAccessStreamReference(this, v117, a3, a4);
            v8 = v83;
            if ( v83 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x15D,
                (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
                (const char *)(unsigned int)v83,
                v114);
              WindowsDeleteString(string2);
              string2 = 0;
              v84 = v117;
              if ( v117 )
              {
                v117 = 0;
                (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v84 + 16LL))(v84);
              }
              v85 = v118;
              if ( v118 )
              {
                v118 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
              }
              return v8;
            }
          }
          else
          {
            v80 = DataPackageCloner::CloneMSUriRandomAccessStreamReference(this, v117, 0, a3, a4);
            v8 = v80;
            if ( v80 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x158,
                (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
                (const char *)(unsigned int)v80,
                v116);
              WindowsDeleteString(string2);
              string2 = 0;
              v81 = v117;
              if ( v117 )
              {
                v117 = 0;
                (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v81 + 16LL))(v81);
              }
              v82 = v118;
              if ( v118 )
              {
                v118 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
              }
              return v8;
            }
          }
        }
        else
        {
          v70 = DataPackageCloner::CloneMSUriRandomAccessStreamReference(this, v117, 1, a3, a4);
          v8 = v70;
          if ( v70 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x151,
              (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
              (const char *)(unsigned int)v70,
              v115);
            WindowsDeleteString(string2);
            string2 = 0;
            v71 = v117;
            if ( v117 )
            {
              v117 = 0;
              (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v71 + 16LL))(v71);
            }
            v72 = v118;
            if ( v118 )
            {
              v118 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
            }
            return v8;
          }
        }
        WindowsDeleteString(string2);
      }
      break;
    case 3:
      string2 = 0;
      v14 = v118;
      v15 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v118 + 32LL);
      v16 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&string2);
      v17 = v15(v14, &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, v16);
      v8 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12D,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
          (const char *)(unsigned int)v17,
          v114);
        v18 = string2;
        if ( string2 )
        {
          string2 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v19 = v118;
        if ( v118 )
        {
          v118 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        return v8;
      }
      *(_QWORD *)result = 0;
      v20 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(result);
      v21 = DataPackageCloner::CloneToMemoryStream(
              this,
              (struct Windows::Storage::Streams::IRandomAccessStream *)string2,
              &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
              v20);
      v8 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x130,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
          (const char *)(unsigned int)v21,
          v114);
        v22 = *(_QWORD *)result;
        if ( *(_QWORD *)result )
        {
          *(_QWORD *)result = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        }
        v23 = string2;
        if ( string2 )
        {
          string2 = 0;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = v118;
        if ( v118 )
        {
          v118 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        return v8;
      }
      v117 = 0;
      string = 0;
      v25 = WindowsCreateStringReference(
              L"Windows.Storage.Streams.RandomAccessStreamReference",
              0x33u,
              &hstringHeader,
              &string);
      if ( v25 >= 0 )
      {
        v28 = RoGetActivationFactory(string, &GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964, &v117);
        v8 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x133,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
            (const char *)(unsigned int)v28,
            v114);
          v29 = v117;
          if ( v117 )
          {
            v117 = 0;
            (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v29 + 16LL))(v29);
          }
          v30 = *(_QWORD *)result;
          if ( *(_QWORD *)result )
          {
            *(_QWORD *)result = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          }
          v31 = string2;
          if ( string2 )
          {
            string2 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v31 + 16LL))(v31);
          }
          v32 = v118;
          if ( v118 )
          {
            v118 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          }
          return v8;
        }
        v121 = 0;
        v33 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, _QWORD, _QWORD))(*(_QWORD *)v117 + 64LL))(
                v117,
                *(_QWORD *)result,
                &v121);
        v8 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x136,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
            (const char *)(unsigned int)v33,
            v114);
          v34 = v121;
          if ( v121 )
          {
            v121 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v34)[2])(v34);
          }
          v35 = v117;
          if ( v117 )
          {
            v117 = 0;
            (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v35 + 16LL))(v35);
          }
          v36 = *(_QWORD *)result;
          if ( *(_QWORD *)result )
          {
            *(_QWORD *)result = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          }
          v37 = string2;
          if ( string2 )
          {
            string2 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v37 + 16LL))(v37);
          }
          v38 = v118;
          if ( v118 )
          {
            v118 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          }
          return v8;
        }
        v39 = (**v121)(v121, a3, a4);
        v8 = v39;
        if ( v39 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
            (const char *)(unsigned int)v39,
            v114);
          v40 = v121;
          if ( v121 )
          {
            v121 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v40)[2])(v40);
          }
          v41 = v117;
          if ( v117 )
          {
            v117 = 0;
            (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v41 + 16LL))(v41);
          }
          v42 = *(_QWORD *)result;
          if ( *(_QWORD *)result )
          {
            *(_QWORD *)result = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          }
          v43 = string2;
          if ( string2 )
          {
            string2 = 0;
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v43 + 16LL))(v43);
          }
          v44 = v118;
          if ( v118 )
          {
            v118 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          }
          return v8;
        }
        v45 = v121;
        if ( v121 )
        {
          v121 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v45)[2])(v45);
        }
        v46 = v117;
        if ( v117 )
        {
          v117 = 0;
          (*(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *))(*(_QWORD *)v46 + 16LL))(v46);
        }
        v47 = *(_QWORD *)result;
        if ( *(_QWORD *)result )
        {
          *(_QWORD *)result = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        }
        v48 = string2;
        if ( string2 )
        {
          string2 = 0;
LABEL_170:
          (*(void (__fastcall **)(void *))(*(_QWORD *)v48 + 16LL))(v48);
          goto LABEL_171;
        }
        goto LABEL_171;
      }
      goto LABEL_175;
    default:
      v8 = -2147418113;
      RoOriginateError(2147549183LL, 0);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x167,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
        (const char *)0x8000FFFFLL,
        v114);
      v13 = v118;
      if ( v118 )
      {
        v118 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return v8;
  }
  v48 = v117;
  if ( v117 )
  {
    v117 = 0;
    goto LABEL_170;
  }
LABEL_171:
  v113 = v118;
  if ( v118 )
  {
    v118 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  }
  return 0;
}

```

## disassembly

```asm
0x180077fbc  push    rbp
0x180077fbe  push    rbx
0x180077fbf  push    rsi
0x180077fc0  push    rdi
0x180077fc1  push    r12
0x180077fc3  push    r14
0x180077fc5  push    r15
0x180077fc7  lea     rbp, [rsp-27h]
0x180077fcc  sub     rsp, 90h
0x180077fd3  mov     rax, cs:__security_cookie
0x180077fda  xor     rax, rsp
0x180077fdd  mov     [rbp+57h+var_40], rax
0x180077fe1  mov     r14, r9
0x180077fe4  mov     r15, r8
0x180077fe7  mov     r9, rdx
0x180077fea  mov     rsi, rcx
0x180077fed  xor     r12d, r12d
0x180077ff0  mov     [r14], r12
0x180077ff3  mov     [rbp+57h+var_88], r12
0x180077ff7  mov     rax, [rdx]
0x180077ffa  lea     r8, [rbp+57h+var_88]
0x180077ffe  lea     rdx, _GUID_3fe8e0e3_eb50_4682_b91d_21028012a049
0x180078005  mov     rcx, r9
0x180078008  mov     rax, [rax]
0x18007800b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078010  mov     ebx, eax
0x180078012  test    eax, eax
0x180078014  jns     short loc_180078050
0x180078016  mov     rcx, [rbp+5Fh]; this
0x18007801a  mov     r9d, eax; char *
0x18007801d  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180078024  mov     edx, 114h; void *
0x180078029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007802e  nop
0x18007802f  mov     rcx, [rbp+57h+var_88]
0x180078033  test    rcx, rcx
0x180078036  jz      short loc_180078049
0x180078038  mov     [rbp+57h+var_88], r12
0x18007803c  mov     rax, [rcx]
0x18007803f  mov     rax, [rax+10h]
0x180078043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078048  nop
0x180078049  mov     eax, ebx
0x18007804b  jmp     loc_180078C69
0x180078050  mov     [rbp+57h+var_68], r12d
0x180078054  mov     rcx, [rbp+57h+var_88]
0x180078058  mov     rax, [rcx]
0x18007805b  lea     rdx, [rbp+57h+var_68]
0x18007805f  mov     rax, [rax+18h]
0x180078063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078068  mov     ebx, eax
0x18007806a  test    eax, eax
0x18007806c  jns     short loc_1800780A3
0x18007806e  mov     rcx, [rbp+5Fh]; this
0x180078072  mov     r9d, eax; char *
0x180078075  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18007807c  mov     edx, 117h; void *
0x180078081  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078086  nop
0x180078087  mov     rcx, [rbp+57h+var_88]
0x18007808b  test    rcx, rcx
0x18007808e  jz      short loc_1800780A1
0x180078090  mov     [rbp+57h+var_88], r12
0x180078094  mov     rax, [rcx]
0x180078097  mov     rax, [rax+10h]
0x18007809b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800780a0  nop
0x1800780a1  jmp     short loc_180078049
0x1800780a3  mov     ecx, [rbp+57h+var_68]
0x1800780a6  sub     ecx, 1
0x1800780a9  jz      loc_18007895B
0x1800780af  sub     ecx, 1
0x1800780b2  jz      loc_1800784F6
0x1800780b8  cmp     ecx, 1
0x1800780bb  jz      short loc_180078107
0x1800780bd  xor     edx, edx
0x1800780bf  mov     ebx, 8000FFFFh
0x1800780c4  mov     ecx, ebx
0x1800780c6  call    cs:__imp_RoOriginateError
0x1800780cc  mov     rcx, [rbp+5Fh]; this
0x1800780d0  mov     r9d, ebx; char *
0x1800780d3  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800780da  mov     edx, 167h; void *
0x1800780df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800780e4  nop
0x1800780e5  mov     rdx, [rbp+57h+var_88]
0x1800780e9  test    rdx, rdx
0x1800780ec  jz      short loc_180078102
0x1800780ee  mov     [rbp+57h+var_88], r12
0x1800780f2  mov     rcx, [rdx]
0x1800780f5  mov     rax, [rcx+10h]
0x1800780f9  mov     rcx, rdx
0x1800780fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078101  nop
0x180078102  jmp     loc_180078049
0x180078107  mov     [rbp+57h+string2], r12
0x18007810b  mov     rdi, [rbp+57h+var_88]
0x18007810f  mov     rax, [rdi]
0x180078112  mov     rbx, [rax+20h]
0x180078116  lea     rcx, [rbp+57h+string2]
0x18007811a  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18007811f  mov     r8, rax
0x180078122  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180078129  mov     rcx, rdi
0x18007812c  mov     rax, rbx
0x18007812f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078134  mov     ebx, eax
0x180078136  test    eax, eax
0x180078138  jns     short loc_18007818C
0x18007813a  mov     rcx, [rbp+5Fh]; this
0x18007813e  mov     r9d, eax; char *
0x180078141  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180078148  mov     edx, 12Dh; void *
0x18007814d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078152  nop
0x180078153  mov     rcx, [rbp+57h+string2]
0x180078157  test    rcx, rcx
0x18007815a  jz      short loc_18007816D
0x18007815c  mov     [rbp+57h+string2], r12
0x180078160  mov     rax, [rcx]
0x180078163  mov     rax, [rax+10h]
0x180078167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007816c  nop
0x18007816d  mov     rcx, [rbp+57h+var_88]
0x180078171  test    rcx, rcx
0x180078174  jz      short loc_180078187
0x180078176  mov     [rbp+57h+var_88], r12
0x18007817a  mov     rax, [rcx]
0x18007817d  mov     rax, [rax+10h]
0x180078181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078186  nop
0x180078187  jmp     loc_180078049
0x18007818c  mov     qword ptr [rbp+57h+result], r12
0x180078190  lea     rcx, [rbp+57h+result]
0x180078194  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180078199  mov     r9, rax; void **
0x18007819c  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da; struct _GUID *
0x1800781a3  mov     rdx, [rbp+57h+string2]; struct Windows::Storage::Streams::IRandomAccessStream *
0x1800781a7  mov     rcx, rsi; this
0x1800781aa  call    ?CloneToMemoryStream@DataPackageCloner@@AEAAJPEAUIRandomAccessStream@Streams@Storage@Windows@@AEBU_GUID@@PEAPEAX@Z; DataPackageCloner::CloneToMemoryStream(Windows::Storage::Streams::IRandomAccessStream *,_GUID const &,void * *)
0x1800781af  mov     ebx, eax
0x1800781b1  test    eax, eax
0x1800781b3  jns     short loc_180078221
0x1800781b5  mov     rcx, [rbp+5Fh]; this
0x1800781b9  mov     r9d, eax; char *
0x1800781bc  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800781c3  mov     edx, 130h; void *
0x1800781c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800781cd  nop
0x1800781ce  mov     rcx, qword ptr [rbp+57h+result]
0x1800781d2  test    rcx, rcx
0x1800781d5  jz      short loc_1800781E8
0x1800781d7  mov     qword ptr [rbp+57h+result], r12
0x1800781db  mov     rax, [rcx]
0x1800781de  mov     rax, [rax+10h]
0x1800781e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781e7  nop
0x1800781e8  mov     rcx, [rbp+57h+string2]
0x1800781ec  test    rcx, rcx
0x1800781ef  jz      short loc_180078202
0x1800781f1  mov     [rbp+57h+string2], r12
0x1800781f5  mov     rax, [rcx]
0x1800781f8  mov     rax, [rax+10h]
0x1800781fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078201  nop
0x180078202  mov     rcx, [rbp+57h+var_88]
0x180078206  test    rcx, rcx
0x180078209  jz      short loc_18007821C
0x18007820b  mov     [rbp+57h+var_88], r12
0x18007820f  mov     rax, [rcx]
0x180078212  mov     rax, [rax+10h]
0x180078216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007821b  nop
0x18007821c  jmp     loc_180078049
0x180078221  mov     [rbp+57h+var_90], r12
0x180078225  mov     [rbp+57h+string], r12
0x180078229  lea     r9, [rbp+57h+string]; string
0x18007822d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180078231  mov     edx, 33h ; '3'; length
0x180078236  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_RandomAccessStreamReference@@3QBGB; "Windows.Storage.Streams.RandomAccessStr"...
0x18007823d  call    cs:__imp_WindowsCreateStringReference
0x180078243  test    eax, eax
0x180078245  js      loc_180078C8F
0x18007824b  mov     rbx, [rbp+57h+string]
0x18007824f  mov     rcx, [rbp+57h+var_90]
0x180078253  test    rcx, rcx
0x180078256  jz      short loc_180078269
0x180078258  mov     [rbp+57h+var_90], r12
0x18007825c  mov     rax, [rcx]
0x18007825f  mov     rax, [rax+10h]
0x180078263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078268  nop
0x180078269  lea     r8, [rbp+57h+var_90]
0x18007826d  lea     rdx, _GUID_857309dc_3fbf_4e7d_986f_ef3b1a07a964
0x180078274  mov     rcx, rbx
0x180078277  call    cs:__imp_RoGetActivationFactory
0x18007827d  mov     ebx, eax
0x18007827f  test    eax, eax
0x180078281  jns     loc_18007830D
0x180078287  mov     rcx, [rbp+5Fh]; this
0x18007828b  mov     r9d, eax; char *
0x18007828e  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180078295  mov     edx, 133h; void *
0x18007829a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007829f  nop
0x1800782a0  mov     rcx, [rbp+57h+var_90]
0x1800782a4  test    rcx, rcx
0x1800782a7  jz      short loc_1800782BA
0x1800782a9  mov     [rbp+57h+var_90], r12
0x1800782ad  mov     rax, [rcx]
0x1800782b0  mov     rax, [rax+10h]
0x1800782b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782b9  nop
0x1800782ba  mov     rcx, qword ptr [rbp+57h+result]
0x1800782be  test    rcx, rcx
0x1800782c1  jz      short loc_1800782D4
0x1800782c3  mov     qword ptr [rbp+57h+result], r12
0x1800782c7  mov     rax, [rcx]
0x1800782ca  mov     rax, [rax+10h]
0x1800782ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782d3  nop
0x1800782d4  mov     rcx, [rbp+57h+string2]
0x1800782d8  test    rcx, rcx
0x1800782db  jz      short loc_1800782EE
0x1800782dd  mov     [rbp+57h+string2], r12
0x1800782e1  mov     rax, [rcx]
0x1800782e4  mov     rax, [rax+10h]
0x1800782e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782ed  nop
0x1800782ee  mov     rcx, [rbp+57h+var_88]
0x1800782f2  test    rcx, rcx
0x1800782f5  jz      short loc_180078308
0x1800782f7  mov     [rbp+57h+var_88], r12
0x1800782fb  mov     rax, [rcx]
0x1800782fe  mov     rax, [rax+10h]
0x180078302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078307  nop
0x180078308  jmp     loc_180078049
0x18007830d  mov     [rbp+57h+var_70], r12
0x180078311  mov     rcx, [rbp+57h+var_90]
0x180078315  mov     rax, [rcx]
0x180078318  lea     r8, [rbp+57h+var_70]
0x18007831c  mov     rdx, qword ptr [rbp+57h+result]
0x180078320  mov     rax, [rax+40h]
0x180078324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078329  mov     ebx, eax
0x18007832b  test    eax, eax
0x18007832d  jns     loc_1800783D3
0x180078333  mov     rcx, [rbp+5Fh]; this
0x180078337  mov     r9d, eax; char *
0x18007833a  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180078341  mov     edx, 136h; void *
0x180078346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007834b  nop
0x18007834c  mov     rcx, [rbp+57h+var_70]
0x180078350  test    rcx, rcx
0x180078353  jz      short loc_180078366
0x180078355  mov     [rbp+57h+var_70], r12
0x180078359  mov     rax, [rcx]
0x18007835c  mov     rax, [rax+10h]
0x180078360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078365  nop
0x180078366  mov     rcx, [rbp+57h+var_90]
0x18007836a  test    rcx, rcx
0x18007836d  jz      short loc_180078380
0x18007836f  mov     [rbp+57h+var_90], r12
0x180078373  mov     rax, [rcx]
0x180078376  mov     rax, [rax+10h]
0x18007837a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007837f  nop
0x180078380  mov     rcx, qword ptr [rbp+57h+result]
0x180078384  test    rcx, rcx
0x180078387  jz      short loc_18007839A
0x180078389  mov     qword ptr [rbp+57h+result], r12
0x18007838d  mov     rax, [rcx]
0x180078390  mov     rax, [rax+10h]
0x180078394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078399  nop
0x18007839a  mov     rcx, [rbp+57h+string2]
0x18007839e  test    rcx, rcx
0x1800783a1  jz      short loc_1800783B4
0x1800783a3  mov     [rbp+57h+string2], r12
0x1800783a7  mov     rax, [rcx]
0x1800783aa  mov     rax, [rax+10h]
0x1800783ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800783b3  nop
0x1800783b4  mov     rcx, [rbp+57h+var_88]
0x1800783b8  test    rcx, rcx
0x1800783bb  jz      short loc_1800783CE
0x1800783bd  mov     [rbp+57h+var_88], r12
0x1800783c1  mov     rax, [rcx]
0x1800783c4  mov     rax, [rax+10h]
0x1800783c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800783cd  nop
0x1800783ce  jmp     loc_180078049
0x1800783d3  mov     rcx, [rbp+57h+var_70]
0x1800783d7  mov     rax, [rcx]
0x1800783da  mov     r8, r14
0x1800783dd  mov     rdx, r15
0x1800783e0  mov     rax, [rax]
  ... truncated ...
```
