# DataPackageCloner::CloneToMemoryStream(Windows::Storage::Streams::IRandomAccessStream *,_GUID const &,void * *)

- ea: `0x180078cb0`
- end: `0x180079931`
- name: `?CloneToMemoryStream@DataPackageCloner@@AEAAJPEAUIRandomAccessStream@Streams@Storage@Windows@@AEBU_GUID@@PEAPEAX@Z`
- size: `3201`
- prototype: `__int64 __fastcall(DataPackageCloner *__hidden this, struct Windows::Storage::Streams::IRandomAccessStream *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180076aac`
- `0x180077fbc`

## callees

- `0x180002ad0`
- `0x18000580f`
- `0x18000dfb8`
- `0x1800241e4`
- `0x180043b6c`
- `0x180048954`
- `0x180074efc`
- `0x180078cb0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180078d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180078eb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180078d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180078eb9`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180078d90`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180078d90`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180078ef3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180078ef3`

## string_xrefs

- `0x180078d4e`: `Windows.Storage.Streams.InMemoryRandomAccessStream`
- `0x180078eb2`: `Windows.Storage.Streams.RandomAccessStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DataPackageCloner::CloneToMemoryStream(
        DataPackageCloner *this,
        struct Windows::Storage::Streams::IRandomAccessStream *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  int v14; // eax
  struct Windows::Storage::Streams::IRandomAccessStream *v15; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v19; // rcx
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  HSTRING v23; // rbx
  __int64 v24; // rcx
  int ActivationFactory; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v28; // rcx
  __int64 (__fastcall *v29)(struct Windows::Storage::Streams::IRandomAccessStream *, GUID *, __int64 *); // rbx
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v41; // rcx
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v47; // rcx
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v54; // rcx
  __int64 v55; // rdi
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  __int64 v60; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v61; // rcx
  int v62; // eax
  __int64 v63; // rcx
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v68; // rcx
  int v69; // eax
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v75; // rcx
  int v76; // eax
  struct Windows::Storage::Streams::IRandomAccessStream *v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v83; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v84; // rdx
  struct Windows::Storage::Streams::IRandomAccessStream *v85; // rbx
  struct Windows::Storage::Streams::IRandomAccessStream *v86; // rcx
  int v87; // eax
  __int64 v88; // rcx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v99; // rcx
  __int64 v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rcx
  struct Windows::Storage::Streams::IRandomAccessStream *v106; // rcx
  int v107; // [rsp+20h] [rbp-59h]
  struct Windows::Storage::Streams::IRandomAccessStream *v108; // [rsp+30h] [rbp-49h] BYREF
  __int64 v109; // [rsp+38h] [rbp-41h] BYREF
  __int64 v110; // [rsp+40h] [rbp-39h] BYREF
  __int64 v111; // [rsp+48h] [rbp-31h] BYREF
  char v112; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v113[7]; // [rsp+51h] [rbp-28h] BYREF
  __int64 v114; // [rsp+58h] [rbp-21h] BYREF
  __int64 v115; // [rsp+60h] [rbp-19h] BYREF
  struct Windows::Storage::Streams::IRandomAccessStream *v116; // [rsp+68h] [rbp-11h] BYREF
  __int64 v117; // [rsp+70h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-1h] BYREF
  HSTRING string; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a4 = 0;
  v117 = 0;
  v8 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *, __int64 *))(*(_QWORD *)a2 + 48LL))(
         a2,
         &v117);
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = 196;
LABEL_193:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)v8,
      v107);
    return v8;
  }
  v10 = *((_QWORD *)this + 3) + (unsigned int)v117;
  if ( v10 < *((_QWORD *)this + 3) )
  {
    v8 = -2147024882;
    goto LABEL_192;
  }
  *((_QWORD *)this + 3) = v10;
  v8 = *((_QWORD *)this + 4) < v10 ? 0x8007000E : 0;
  if ( v10 > *((_QWORD *)this + 4) )
  {
LABEL_192:
    v9 = 198;
    goto LABEL_193;
  }
  v108 = 0;
  string = 0;
  v11 = WindowsCreateStringReference(
          L"Windows.Storage.Streams.InMemoryRandomAccessStream",
          0x32u,
          &hstringHeader,
          &string);
  if ( v11 < 0 )
  {
LABEL_196:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
    JUMPOUT(0x180079930LL);
  }
  v108 = 0;
  v116 = 0;
  v8 = RoActivateInstance(string, &v116);
  if ( (v8 & 0x80000000) == 0 )
  {
    v14 = memcmp_0(&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
    v15 = v116;
    if ( !v14 )
    {
      v108 = v116;
      goto LABEL_11;
    }
    v8 = (**(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IRandomAccessStream *, GUID *, struct Windows::Storage::Streams::IRandomAccessStream **))v116)(
           v116,
           &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
           &v108);
    (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v116 + 16LL))(v116);
  }
  v15 = v108;
LABEL_11:
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)v8,
      v107);
    v16 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  v109 = 0;
  v17 = (**(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IRandomAccessStream *, GUID *, __int64 *))v15)(
          v15,
          &GUID_905a0fe6_bc53_11df_8c49_001e4fc686da,
          &v109);
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v17,
      v107);
    v18 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return v8;
  }
  v110 = 0;
  string = 0;
  v20 = WindowsCreateStringReference(L"Windows.Storage.Streams.RandomAccessStream", 0x2Au, &hstringHeader, &string);
  if ( v20 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
    goto LABEL_196;
  }
  v23 = string;
  v24 = v110;
  if ( v110 )
  {
    v110 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  ActivationFactory = RoGetActivationFactory(v23, &GUID_524cedcf_6e29_4ce5_9573_6b753db66c3a, &v110);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v107);
    v26 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return v8;
  }
  v111 = 0;
  if ( (*(int (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *, _QWORD, __int64 *))(*(_QWORD *)a2 + 64LL))(
         a2,
         0,
         &v111) < 0 )
  {
    v29 = **(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IRandomAccessStream *, GUID *, __int64 *))a2;
    v30 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v29(a2, &GUID_905a0fe2_bc53_11df_8c49_001e4fc686da, &v111);
    v8 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
        (const char *)(unsigned int)v31,
        v107);
      v32 = v111;
      if ( v111 )
      {
        v111 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      v33 = v110;
      if ( v110 )
      {
        v110 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v34 = v109;
      if ( v109 )
      {
        v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v35 = v108;
      if ( v108 )
      {
        v108 = 0;
        (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v35 + 16LL))(v35);
      }
      return v8;
    }
  }
  v114 = 0;
  v36 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v110 + 48LL))(
          v110,
          v111,
          v109,
          &v114);
  v8 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v36,
      v107);
    v37 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    v41 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    return v8;
  }
  v42 = WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<unsigned __int64,unsigned __int64>,Windows::Foundation::IAsyncOperationWithProgress<unsigned __int64,unsigned __int64>>(v114);
  v8 = v42;
  if ( v42 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v42,
      v107);
    v43 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v45 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    v46 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v47 + 16LL))(v47);
    }
    return v8;
  }
  v115 = 0;
  v112 = 0;
  v48 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v109 + 56LL))(v109, &v115);
  v8 = v48;
  if ( v48 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v48,
      v107);
    v49 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    }
    v50 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    }
    v51 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    v52 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    v53 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    v54 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v54 + 16LL))(v54);
    }
    return v8;
  }
  v55 = v115;
  v8 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Foundation::IAsyncOperation<bool>>(v115);
  if ( (v8 & 0x80000000) != 0
    || (v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v55 + 64LL))(v55, &v112), (v8 & 0x80000000) != 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)v8,
      v107);
    v101 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v101 + 16LL))(v101);
    }
    v102 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v102 + 16LL))(v102);
    }
    v103 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 16LL))(v103);
    }
    v104 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
    }
    v105 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
    }
    v106 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v106 + 16LL))(v106);
    }
    return v8;
  }
  if ( !v112 )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE6,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)0x8000FFFFLL,
      v107);
    v56 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    }
    v57 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
    }
    v58 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    }
    v59 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    }
    v60 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
    }
    v61 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v61 + 16LL))(v61);
    }
    return v8;
  }
  v62 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *, _QWORD))(*(_QWORD *)v108 + 88LL))(
          v108,
          0);
  v8 = v62;
  if ( v62 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v62,
      v107);
    v63 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    v64 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v65 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    }
    v66 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
    }
    v67 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
    }
    v68 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v68 + 16LL))(v68);
    }
    return v8;
  }
  v113[0] = 0;
  v69 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *, _BYTE *))(*(_QWORD *)v108 + 112LL))(
          v108,
          v113);
  v8 = v69;
  if ( v69 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v69,
      v107);
    v70 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
    }
    v71 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    }
    v72 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    v73 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    }
    v74 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    }
    v75 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v75 + 16LL))(v75);
    }
    return v8;
  }
  if ( v113[0] )
  {
    v116 = 0;
    v76 = CreateReadOnlyWrapperOnRandomAccessStream(v108, &v116);
    v8 = v76;
    if ( v76 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
        (const char *)(unsigned int)v76,
        v107);
      v77 = v116;
      if ( v116 )
      {
        v116 = 0;
        (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v77 + 16LL))(v77);
      }
      v78 = v115;
      if ( v115 )
      {
        v115 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      }
      v79 = v114;
      if ( v114 )
      {
        v114 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
      }
      v80 = v111;
      if ( v111 )
      {
        v111 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      }
      v81 = v110;
      if ( v110 )
      {
        v110 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
      }
      v82 = v109;
      if ( v109 )
      {
        v109 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
      }
      v83 = v108;
      if ( v108 )
      {
        v108 = 0;
        (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v83 + 16LL))(v83);
      }
      return v8;
    }
    v84 = v116;
    if ( v108 != v116 )
    {
      v85 = v116;
      if ( v116 )
      {
        (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v116 + 8LL))(v116);
        v84 = v116;
      }
      v86 = v108;
      v108 = v85;
      if ( v86 )
      {
        (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v86 + 16LL))(v86);
        v84 = v116;
      }
    }
    if ( v84 )
    {
      v116 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v84 + 16LL))(v84);
    }
  }
  v87 = (**(__int64 (__fastcall ***)(struct Windows::Storage::Streams::IRandomAccessStream *, const struct _GUID *, void **))v108)(
          v108,
          a3,
          a4);
  v8 = v87;
  if ( v87 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF4,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v87,
      v107);
    v88 = v115;
    if ( v115 )
    {
      v115 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
    }
    v89 = v114;
    if ( v114 )
    {
      v114 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
    }
    v90 = v111;
    if ( v111 )
    {
      v111 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
    }
    v91 = v110;
    if ( v110 )
    {
      v110 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    }
    v92 = v109;
    if ( v109 )
    {
      v109 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
    }
    v93 = v108;
    if ( v108 )
    {
      v108 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v93 + 16LL))(v93);
    }
    return v8;
  }
  v94 = v115;
  if ( v115 )
  {
    v115 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
  }
  v95 = v114;
  if ( v114 )
  {
    v114 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v95 + 16LL))(v95);
  }
  v96 = v111;
  if ( v111 )
  {
    v111 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v96 + 16LL))(v96);
  }
  v97 = v110;
  if ( v110 )
  {
    v110 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
  }
  v98 = v109;
  if ( v109 )
  {
    v109 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v98 + 16LL))(v98);
  }
  v99 = v108;
  if ( v108 )
  {
    v108 = 0;
    (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStream *))(*(_QWORD *)v99 + 16LL))(v99);
  }
  return 0;
}

```

## disassembly

```asm
0x180078cb0  push    rbp
0x180078cb2  push    rbx
0x180078cb3  push    rsi
0x180078cb4  push    rdi
0x180078cb5  push    r12
0x180078cb7  push    r14
0x180078cb9  push    r15
0x180078cbb  lea     rbp, [rsp-27h]
0x180078cc0  sub     rsp, 0A0h
0x180078cc7  mov     rax, cs:__security_cookie
0x180078cce  xor     rax, rsp
0x180078cd1  mov     [rbp+57h+var_38], rax
0x180078cd5  mov     r14, r9
0x180078cd8  mov     r15, r8
0x180078cdb  mov     rsi, rdx
0x180078cde  mov     rdi, rcx
0x180078ce1  xor     r12d, r12d
0x180078ce4  mov     [r9], r12
0x180078ce7  mov     [rbp+57h+var_60], r12
0x180078ceb  mov     rax, [rdx]
0x180078cee  lea     rdx, [rbp+57h+var_60]
0x180078cf2  mov     rcx, rsi
0x180078cf5  mov     rax, [rax+30h]
0x180078cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078cfe  mov     ebx, eax
0x180078d00  test    eax, eax
0x180078d02  jns     short loc_180078D0E
0x180078d04  mov     edx, 0C4h
0x180078d09  jmp     loc_1800798EE
0x180078d0e  mov     edx, dword ptr [rbp+57h+var_60]
0x180078d11  add     rdx, [rdi+18h]
0x180078d15  cmp     rdx, [rdi+18h]
0x180078d19  jb      loc_1800798E4
0x180078d1f  mov     [rdi+18h], rdx
0x180078d23  cmp     [rdi+20h], rdx
0x180078d27  sbb     ebx, ebx
0x180078d29  and     ebx, 8007000Eh
0x180078d2f  cmp     rdx, [rdi+20h]
0x180078d33  ja      loc_1800798E9
0x180078d39  mov     [rbp+57h+var_A0], r12
0x180078d3d  mov     [rbp+57h+string], r12
0x180078d41  lea     r9, [rbp+57h+string]; string
0x180078d45  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180078d49  mov     edx, 32h ; '2'; length
0x180078d4e  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_InMemoryRandomAccessStream@@3QBGB; "Windows.Storage.Streams.InMemoryRandomA"...
0x180078d55  call    cs:__imp_WindowsCreateStringReference
0x180078d5b  test    eax, eax
0x180078d5d  js      loc_180079929
0x180078d63  mov     rbx, [rbp+57h+string]
0x180078d67  mov     rcx, [rbp+57h+var_A0]
0x180078d6b  test    rcx, rcx
0x180078d6e  jz      short loc_180078D81
0x180078d70  mov     [rbp+57h+var_A0], r12
0x180078d74  mov     rax, [rcx]
0x180078d77  mov     rax, [rax+10h]
0x180078d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078d80  nop
0x180078d81  mov     [rbp+57h+var_A0], r12
0x180078d85  mov     [rbp+57h+var_68], r12
0x180078d89  lea     rdx, [rbp+57h+var_68]
0x180078d8d  mov     rcx, rbx
0x180078d90  call    cs:__imp_RoActivateInstance
0x180078d96  mov     ebx, eax
0x180078d98  test    eax, eax
0x180078d9a  js      short loc_180078DEB
0x180078d9c  mov     r8d, 10h; Size
0x180078da2  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180078da9  lea     rcx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da; Buf1
0x180078db0  call    memcmp_0
0x180078db5  mov     rcx, [rbp+57h+var_68]
0x180078db9  test    eax, eax
0x180078dbb  jnz     short loc_180078DC3
0x180078dbd  mov     [rbp+57h+var_A0], rcx
0x180078dc1  jmp     short loc_180078DEF
0x180078dc3  mov     rax, [rcx]
0x180078dc6  lea     r8, [rbp+57h+var_A0]
0x180078dca  lea     rdx, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180078dd1  mov     rax, [rax]
0x180078dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078dd9  mov     ebx, eax
0x180078ddb  mov     rcx, [rbp+57h+var_68]
0x180078ddf  mov     rax, [rcx]
0x180078de2  mov     rax, [rax+10h]
0x180078de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078deb  mov     rcx, [rbp+57h+var_A0]
0x180078def  test    ebx, ebx
0x180078df1  jns     short loc_180078E2B
0x180078df3  mov     rcx, [rbp+5Fh]; this
0x180078df7  mov     r9d, ebx; char *
0x180078dfa  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180078e01  mov     edx, 0C9h; void *
0x180078e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078e0b  nop
0x180078e0c  mov     rcx, [rbp+57h+var_A0]
0x180078e10  test    rcx, rcx
0x180078e13  jz      short loc_180078E26
0x180078e15  mov     [rbp+57h+var_A0], r12
0x180078e19  mov     rax, [rcx]
0x180078e1c  mov     rax, [rax+10h]
0x180078e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e25  nop
0x180078e26  jmp     loc_180079901
0x180078e2b  mov     [rbp+57h+var_98], r12
0x180078e2f  mov     rax, [rcx]
0x180078e32  lea     r8, [rbp+57h+var_98]
0x180078e36  lea     rdx, _GUID_905a0fe6_bc53_11df_8c49_001e4fc686da
0x180078e3d  mov     rax, [rax]
0x180078e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e45  mov     ebx, eax
0x180078e47  test    eax, eax
0x180078e49  jns     short loc_180078E9D
0x180078e4b  mov     rcx, [rbp+5Fh]; this
0x180078e4f  mov     r9d, eax; char *
0x180078e52  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180078e59  mov     edx, 0CCh; void *
0x180078e5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078e63  nop
0x180078e64  mov     rcx, [rbp+57h+var_98]
0x180078e68  test    rcx, rcx
0x180078e6b  jz      short loc_180078E7E
0x180078e6d  mov     [rbp+57h+var_98], r12
0x180078e71  mov     rax, [rcx]
0x180078e74  mov     rax, [rax+10h]
0x180078e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e7d  nop
0x180078e7e  mov     rcx, [rbp+57h+var_A0]
0x180078e82  test    rcx, rcx
0x180078e85  jz      short loc_180078E98
0x180078e87  mov     [rbp+57h+var_A0], r12
0x180078e8b  mov     rax, [rcx]
0x180078e8e  mov     rax, [rax+10h]
0x180078e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e97  nop
0x180078e98  jmp     loc_180079901
0x180078e9d  mov     [rbp+57h+var_90], r12
0x180078ea1  mov     [rbp+57h+string], r12
0x180078ea5  lea     r9, [rbp+57h+string]; string
0x180078ea9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180078ead  mov     edx, 2Ah ; '*'; length
0x180078eb2  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_RandomAccessStream@@3QBGB; "Windows.Storage.Streams.RandomAccessStr"...
0x180078eb9  call    cs:__imp_WindowsCreateStringReference
0x180078ebf  test    eax, eax
0x180078ec1  js      loc_180079921
0x180078ec7  mov     rbx, [rbp+57h+string]
0x180078ecb  mov     rcx, [rbp+57h+var_90]
0x180078ecf  test    rcx, rcx
0x180078ed2  jz      short loc_180078EE5
0x180078ed4  mov     [rbp+57h+var_90], r12
0x180078ed8  mov     rax, [rcx]
0x180078edb  mov     rax, [rax+10h]
0x180078edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ee4  nop
0x180078ee5  lea     r8, [rbp+57h+var_90]
0x180078ee9  lea     rdx, _GUID_524cedcf_6e29_4ce5_9573_6b753db66c3a
0x180078ef0  mov     rcx, rbx
0x180078ef3  call    cs:__imp_RoGetActivationFactory
0x180078ef9  mov     ebx, eax
0x180078efb  test    eax, eax
0x180078efd  jns     short loc_180078F6B
0x180078eff  mov     rcx, [rbp+5Fh]; this
0x180078f03  mov     r9d, eax; char *
0x180078f06  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180078f0d  mov     edx, 0CFh; void *
0x180078f12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078f17  nop
0x180078f18  mov     rcx, [rbp+57h+var_90]
0x180078f1c  test    rcx, rcx
0x180078f1f  jz      short loc_180078F32
0x180078f21  mov     [rbp+57h+var_90], r12
0x180078f25  mov     rax, [rcx]
0x180078f28  mov     rax, [rax+10h]
0x180078f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f31  nop
0x180078f32  mov     rcx, [rbp+57h+var_98]
0x180078f36  test    rcx, rcx
0x180078f39  jz      short loc_180078F4C
0x180078f3b  mov     [rbp+57h+var_98], r12
0x180078f3f  mov     rax, [rcx]
0x180078f42  mov     rax, [rax+10h]
0x180078f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f4b  nop
0x180078f4c  mov     rcx, [rbp+57h+var_A0]
0x180078f50  test    rcx, rcx
0x180078f53  jz      short loc_180078F66
0x180078f55  mov     [rbp+57h+var_A0], r12
0x180078f59  mov     rax, [rcx]
0x180078f5c  mov     rax, [rax+10h]
0x180078f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f65  nop
0x180078f66  jmp     loc_180079901
0x180078f6b  mov     [rbp+57h+var_88], r12
0x180078f6f  mov     rax, [rsi]
0x180078f72  lea     r8, [rbp+57h+var_88]
0x180078f76  xor     edx, edx
0x180078f78  mov     rcx, rsi
0x180078f7b  mov     rax, [rax+40h]
0x180078f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f84  test    eax, eax
0x180078f86  jns     loc_180079052
0x180078f8c  mov     rax, [rsi]
0x180078f8f  mov     rbx, [rax]
0x180078f92  mov     rcx, [rbp+57h+var_88]
0x180078f96  test    rcx, rcx
0x180078f99  jz      short loc_180078FAC
0x180078f9b  mov     [rbp+57h+var_88], r12
0x180078f9f  mov     rdx, [rcx]
0x180078fa2  mov     rax, [rdx+10h]
0x180078fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078fab  nop
0x180078fac  lea     r8, [rbp+57h+var_88]
0x180078fb0  lea     rdx, _GUID_905a0fe2_bc53_11df_8c49_001e4fc686da
0x180078fb7  mov     rcx, rsi
0x180078fba  mov     rax, rbx
0x180078fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078fc2  mov     ebx, eax
0x180078fc4  test    eax, eax
0x180078fc6  jns     loc_180079052
0x180078fcc  mov     rcx, [rbp+5Fh]; this
0x180078fd0  mov     r9d, eax; char *
0x180078fd3  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180078fda  mov     edx, 0D8h; void *
0x180078fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078fe4  nop
0x180078fe5  mov     rcx, [rbp+57h+var_88]
0x180078fe9  test    rcx, rcx
0x180078fec  jz      short loc_180078FFF
0x180078fee  mov     [rbp+57h+var_88], r12
0x180078ff2  mov     rax, [rcx]
0x180078ff5  mov     rax, [rax+10h]
0x180078ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ffe  nop
0x180078fff  mov     rcx, [rbp+57h+var_90]
0x180079003  test    rcx, rcx
0x180079006  jz      short loc_180079019
0x180079008  mov     [rbp+57h+var_90], r12
0x18007900c  mov     rax, [rcx]
0x18007900f  mov     rax, [rax+10h]
0x180079013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079018  nop
0x180079019  mov     rcx, [rbp+57h+var_98]
0x18007901d  test    rcx, rcx
0x180079020  jz      short loc_180079033
0x180079022  mov     [rbp+57h+var_98], r12
0x180079026  mov     rax, [rcx]
0x180079029  mov     rax, [rax+10h]
0x18007902d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079032  nop
0x180079033  mov     rcx, [rbp+57h+var_A0]
0x180079037  test    rcx, rcx
0x18007903a  jz      short loc_18007904D
0x18007903c  mov     [rbp+57h+var_A0], r12
0x180079040  mov     rax, [rcx]
0x180079043  mov     rax, [rax+10h]
0x180079047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007904c  nop
0x18007904d  jmp     loc_180079901
0x180079052  mov     [rbp+57h+var_78], r12
0x180079056  mov     rcx, [rbp+57h+var_90]
0x18007905a  mov     rax, [rcx]
0x18007905d  lea     r9, [rbp+57h+var_78]
0x180079061  mov     r8, [rbp+57h+var_98]
0x180079065  mov     rdx, [rbp+57h+var_88]
0x180079069  mov     rax, [rax+30h]
0x18007906d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079072  mov     ebx, eax
0x180079074  test    eax, eax
0x180079076  jns     loc_18007911C
0x18007907c  mov     rcx, [rbp+5Fh]; this
0x180079080  mov     r9d, eax; char *
0x180079083  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18007908a  mov     edx, 0DCh; void *
0x18007908f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079094  nop
0x180079095  mov     rcx, [rbp+57h+var_78]
0x180079099  test    rcx, rcx
0x18007909c  jz      short loc_1800790AF
0x18007909e  mov     [rbp+57h+var_78], r12
0x1800790a2  mov     rax, [rcx]
0x1800790a5  mov     rax, [rax+10h]
0x1800790a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790ae  nop
0x1800790af  mov     rcx, [rbp+57h+var_88]
0x1800790b3  test    rcx, rcx
0x1800790b6  jz      short loc_1800790C9
0x1800790b8  mov     [rbp+57h+var_88], r12
0x1800790bc  mov     rax, [rcx]
0x1800790bf  mov     rax, [rax+10h]
0x1800790c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790c8  nop
0x1800790c9  mov     rcx, [rbp+57h+var_90]
0x1800790cd  test    rcx, rcx
0x1800790d0  jz      short loc_1800790E3
0x1800790d2  mov     [rbp+57h+var_90], r12
0x1800790d6  mov     rax, [rcx]
0x1800790d9  mov     rax, [rax+10h]
0x1800790dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790e2  nop
0x1800790e3  mov     rcx, [rbp+57h+var_98]
0x1800790e7  test    rcx, rcx
0x1800790ea  jz      short loc_1800790FD
  ... truncated ...
```
