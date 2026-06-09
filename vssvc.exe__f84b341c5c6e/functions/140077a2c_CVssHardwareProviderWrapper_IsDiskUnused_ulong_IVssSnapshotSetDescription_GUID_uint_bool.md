# CVssHardwareProviderWrapper::IsDiskUnused(ulong,IVssSnapshotSetDescription *,_GUID *,uint,bool)

- ea: `0x140077a2c`
- end: `0x140078550`
- name: `?IsDiskUnused@CVssHardwareProviderWrapper@@AEAA_NKPEAVIVssSnapshotSetDescription@@PEAU_GUID@@I_N@Z`
- size: `2852`
- prototype: `bool __fastcall(CVssHardwareProviderWrapper *__hidden this, unsigned int, struct IVssSnapshotSetDescription *, struct _GUID *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140063f60`

## callees

- `0x140008450`
- `0x1400088fc`
- `0x140009444`
- `0x140011a90`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x14003c160`
- `0x14003fc04`
- `0x140049ec4`
- `0x140065a90`
- `0x140077a2c`
- `0x140091560`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140078210`
- `OLEAUT32!__imp_SysFreeString` at `0x1400782ba`
- `OLEAUT32!__imp_SysFreeString` at `0x140078375`
- `OLEAUT32!__imp_SysFreeString` at `0x140078210`
- `OLEAUT32!__imp_SysFreeString` at `0x1400782ba`
- `OLEAUT32!__imp_SysFreeString` at `0x140078375`

## string_xrefs

- `0x140077a6e`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140077b4a`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140077c5f`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140077f45`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140077fcf`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400782c1`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140078413`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x140078074`: `Opening snapshot device: %s ...`
- `0x140077c08`: `  - Deleted snapshot[%d] {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}`
- `0x140077b10`: `Checking if the disk %d is in use by other un-deleted snapshots in the set`
- `0x140077f91`: `Snapshot already deleted. Continuing with the next one...`
- `0x140078480`: `CreateFile(%s) failed with [0x%08lx]`
- `0x14007827b`: `Failure in opening the snapshot device [0x%08lx].`
- `0x1400784ee`: `The LUN lun wasn't found in any other non-deleted snapshot.  It can be freed.`
- `0x14007833d`: `The LUN was found as part of the non-deleted snapshot volume. The LUN cannot be freed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall CVssHardwareProviderWrapper::IsDiskUnused(
        CVssHardwareProviderWrapper *this,
        unsigned int a2,
        struct IVssSnapshotSetDescription *a3,
        struct _GUID *a4,
        unsigned int a5,
        bool a6)
{
  struct IVssSnapshotSetDescription *v7; // rbx
  unsigned int v9; // r12d
  __int64 v10; // rax
  __int64 v11; // r14
  unsigned int i; // r14d
  unsigned int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // ebx
  int v17; // ebx
  unsigned int *j; // rdx
  unsigned int v19; // edi
  bool v20; // bl
  unsigned int v21; // ebx
  BSTR v22; // rbx
  __int64 v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+28h] [rbp-D8h]
  __int64 v26; // [rsp+30h] [rbp-D0h]
  __int64 v27; // [rsp+38h] [rbp-C8h]
  __int64 v28; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v37; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v38; // [rsp+9Ch] [rbp-64h]
  const unsigned __int16 *v39; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v40; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v41; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+BCh] [rbp-44h]
  int v44; // [rsp+C0h] [rbp-40h]
  _BYTE v45[120]; // [rsp+C8h] [rbp-38h] BYREF
  int v46; // [rsp+140h] [rbp+40h]
  const unsigned __int16 *v47; // [rsp+150h] [rbp+50h] BYREF
  __int128 v48; // [rsp+158h] [rbp+58h]
  __int128 v49; // [rsp+168h] [rbp+68h]
  _WORD v50[2]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v51; // [rsp+17Ch] [rbp+7Ch]
  __int64 v52; // [rsp+188h] [rbp+88h]
  __int64 v53; // [rsp+190h] [rbp+90h]
  int v54; // [rsp+198h] [rbp+98h]
  unsigned int *v55; // [rsp+1A0h] [rbp+A0h]
  __int16 v56; // [rsp+1A8h] [rbp+A8h]
  void **v57; // [rsp+1B0h] [rbp+B0h]
  __int64 v58; // [rsp+1B8h] [rbp+B8h]
  int v59; // [rsp+1F0h] [rbp+F0h]
  struct IVssSnapshotSetDescription *v60; // [rsp+200h] [rbp+100h]
  const unsigned __int16 *v61; // [rsp+208h] [rbp+108h] BYREF
  const wchar_t *v62; // [rsp+210h] [rbp+110h]
  const unsigned __int16 *v63; // [rsp+218h] [rbp+118h]
  int v64; // [rsp+220h] [rbp+120h]
  int v65; // [rsp+224h] [rbp+124h]
  int v66; // [rsp+228h] [rbp+128h]
  _BYTE v67[120]; // [rsp+230h] [rbp+130h] BYREF
  int v68; // [rsp+2A8h] [rbp+1A8h]
  LPVOID v69; // [rsp+2B0h] [rbp+1B0h] BYREF
  int v70; // [rsp+2B8h] [rbp+1B8h]
  _QWORD v71[3]; // [rsp+320h] [rbp+220h] BYREF
  int v72; // [rsp+338h] [rbp+238h]
  int v73; // [rsp+33Ch] [rbp+23Ch]
  int v74; // [rsp+340h] [rbp+240h]
  char v75[120]; // [rsp+348h] [rbp+248h] BYREF
  int v76; // [rsp+3C0h] [rbp+2C0h]
  __int128 v77; // [rsp+3C8h] [rbp+2C8h] BYREF

  v7 = a3;
  v60 = a3;
  v38 = a2;
  v47 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  *(_QWORD *)&v48 = L"CVssHardwareProviderWrapper::IsDiskUnused";
  *((_QWORD *)&v48 + 1) = L"CORHDELC";
  *(_QWORD *)&v49 = 0x100000971LL;
  DWORD2(v49) = 255;
  v59 = 0x1000000;
  memset_0(v50, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v69, (__int64)&v47, 0);
  v47 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  *(_QWORD *)&v48 = L"CVssHardwareProviderWrapper::IsDiskUnused";
  *((_QWORD *)&v48 + 1) = L"CORHDELC";
  *(_QWORD *)&v49 = 0x100000974LL;
  DWORD2(v49) = 255;
  v59 = 0x1000000;
  memset_0(v50, 0, 0x78u);
  CVssFunctionTracer::Trace(
    &v69,
    &v47,
    L"Checking if the disk %d is in use by other un-deleted snapshots in the set",
    a2);
  v9 = 0;
  if ( a5 )
  {
    v10 = 0;
    v35 = 0;
    do
    {
      v11 = v10;
      v47 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      *(_QWORD *)&v48 = L"CVssHardwareProviderWrapper::IsDiskUnused";
      *((_QWORD *)&v48 + 1) = L"CORHDELC";
      *(_QWORD *)&v49 = 0x100000977LL;
      DWORD2(v49) = 255;
      v59 = 0x1000000;
      memset_0(v50, 0, 0x78u);
      LODWORD(v34) = a4[v11].Data4[7];
      LODWORD(v33) = a4[v11].Data4[6];
      LODWORD(v32) = a4[v11].Data4[5];
      LODWORD(v31) = a4[v11].Data4[4];
      LODWORD(v30) = a4[v11].Data4[3];
      LODWORD(v29) = a4[v11].Data4[2];
      LODWORD(v28) = a4[v11].Data4[1];
      LODWORD(v27) = a4[v11].Data4[0];
      LODWORD(v26) = a4[v11].Data3;
      LODWORD(v25) = a4[v11].Data2;
      LODWORD(v24) = a4[v11].Data1;
      CVssFunctionTracer::Trace(
        &v69,
        &v47,
        L"  - Deleted snapshot[%d] {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
        v9++,
        v24,
        v25,
        v26,
        v27,
        v28,
        v29,
        v30,
        v31,
        v32,
        v33,
        v34);
      v10 = ++v35;
    }
    while ( v9 < a5 );
    v7 = v60;
  }
  v37 = 0;
  v70 = (*(__int64 (__fastcall **)(struct IVssSnapshotSetDescription *, unsigned int *))(*(_QWORD *)v7 + 88LL))(
          v7,
          &v37);
  v47 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  *(_QWORD *)&v48 = L"CVssHardwareProviderWrapper::IsDiskUnused";
  *((_QWORD *)&v48 + 1) = L"CORHDELC";
  *(_QWORD *)&v49 = 0x10000097CLL;
  DWORD2(v49) = 255;
  v59 = 0x1000000;
  memset_0(v50, 0, 0x78u);
  CVssFunctionTracer::CheckForErrorInternal(&v69, &v47, L"IVssSnapshotSetDescription::GetSnapshotCount");
  for ( i = 0; i < v37; ++i )
  {
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v40 = L"CVssHardwareProviderWrapper::IsDiskUnused";
    v41 = L"CORHDELC";
    v42 = 2433;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::Trace(&v69, &v39, L"Getting snapshot with index %d...", i);
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v35);
    v70 = (*(__int64 (__fastcall **)(struct IVssSnapshotSetDescription *, _QWORD, __int64 *))(*(_QWORD *)v7 + 112LL))(
            v7,
            i,
            &v35);
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v40 = L"CVssHardwareProviderWrapper::IsDiskUnused";
    v41 = L"CORHDELC";
    v42 = 2439;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::CheckForErrorInternal(&v69, &v39, L"IVssSnapshotSetDescription::GetSnapshotDescription");
    v77 = 0;
    v70 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v35 + 24LL))(v35, &v77);
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v40 = L"CVssHardwareProviderWrapper::IsDiskUnused";
    v41 = L"CORHDELC";
    v42 = 2444;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    CVssFunctionTracer::CheckForErrorInternal(&v69, &v39, L"IVssSnapshotDescription::GetSnapshotId");
    v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
    v40 = L"CVssHardwareProviderWrapper::IsDiskUnused";
    v41 = L"CORHDELC";
    v42 = 2446;
    v43 = 1;
    v44 = 255;
    v46 = 0x1000000;
    memset_0(v45, 0, sizeof(v45));
    LODWORD(v33) = HIBYTE(v77);
    LODWORD(v32) = BYTE14(v77);
    LODWORD(v31) = BYTE13(v77);
    LODWORD(v30) = BYTE12(v77);
    LODWORD(v29) = BYTE11(v77);
    LODWORD(v28) = BYTE10(v77);
    LODWORD(v27) = BYTE9(v77);
    LODWORD(v26) = BYTE8(v77);
    LODWORD(v25) = WORD3(v77);
    LODWORD(v24) = WORD2(v77);
    CVssFunctionTracer::Trace(
      &v69,
      &v39,
      L"Snapshot ID = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
      (unsigned int)v77,
      v24,
      v25,
      v26,
      v27,
      v28,
      v29,
      v30,
      v31,
      v32,
      v33);
    v13 = 0;
    if ( !a5 )
      goto LABEL_14;
    do
    {
      v14 = v13;
      v15 = v77 - *(_QWORD *)&a4[v14].Data1;
      if ( (_QWORD)v77 == *(_QWORD *)&a4[v14].Data1 )
        v15 = *((_QWORD *)&v77 + 1) - *(_QWORD *)a4[v14].Data4;
      if ( !v15 )
        break;
      ++v13;
    }
    while ( v13 < a5 );
    if ( v13 < a5 )
    {
      v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v40 = L"CVssHardwareProviderWrapper::IsDiskUnused";
      v41 = L"CORHDELC";
      v42 = 2459;
      v43 = 1;
      v44 = 255;
      v46 = 0x1000000;
      memset_0(v45, 0, sizeof(v45));
      CVssFunctionTracer::Trace(&v69, &v39, L"Snapshot already deleted. Continuing with the next one...");
    }
    else
    {
LABEL_14:
      bstrString = 0;
      v70 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v35 + 128LL))(v35, &bstrString);
      v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v40 = L"CVssHardwareProviderWrapper::IsDiskUnused";
      v41 = L"CORHDELC";
      v42 = 2467;
      v43 = 1;
      v44 = 255;
      v46 = 0x1000000;
      memset_0(v45, 0, sizeof(v45));
      CVssFunctionTracer::CheckForErrorInternal(&v69, &v39, L"IVssSnapshotDescription::GetDeviceName");
      v39 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v40 = L"CVssHardwareProviderWrapper::IsDiskUnused";
      v41 = L"CORHDELC";
      v42 = 2469;
      v43 = 1;
      v44 = 255;
      v46 = 0x1000000;
      memset_0(v45, 0, sizeof(v45));
      CVssFunctionTracer::Trace(&v69, &v39, L"Opening snapshot device: %s ...", bstrString);
      v47 = 0;
      v50[0] = 0;
      v51 = 0;
      v52 = 0;
      v53 = 0;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      v58 = 0;
      v57 = &CVssAutoCOMPtr<_VDS_LUN_INFORMATION *>::`vftable';
      v48 = 0;
      v49 = 0;
      v16 = CVssIOCTLChannel::Open((CVssIOCTLChannel *)&v47, (__int64)&v69, bstrString, 0, 0, 0, 0, 3u, 0x80u);
      v70 = v16;
      if ( v16 < 0 )
      {
        v61 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v62 = L"CVssHardwareProviderWrapper::IsDiskUnused";
        v63 = L"CORHDELC";
        v64 = 2476;
        v65 = 1;
        v66 = 255;
        v68 = 0x1000000;
        memset_0(v67, 0, sizeof(v67));
        CVssFunctionTracer::Trace(&v69, &v61, L"Failure in opening the snapshot device [0x%08lx].", (unsigned int)v16);
        v19 = v70;
        if ( v70 != -2147212536 && !a6 )
        {
          v22 = bstrString;
          v61 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v62 = L"CVssHardwareProviderWrapper::IsDiskUnused";
          v63 = L"CORHDELC";
          v64 = 2486;
          v65 = 1;
          v66 = 255;
          v68 = 0x1000000;
          memset_0(v67, 0, sizeof(v67));
          LODWORD(v25) = v19;
          CVssFunctionTracer::TranslateGenericError(&v69, &v61, v19, L"CreateFile(%s) failed with [0x%08lx]", v22, v25);
        }
      }
      else
      {
        LOBYTE(v25) = 0;
        v17 = CVssIOCTLChannel::Call(&v47, &v69, 5636096, 0, 0, v25, 0);
        v70 = v17;
        if ( v17 < 0 )
        {
          v71[0] = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
          v71[1] = L"CVssHardwareProviderWrapper::IsDiskUnused";
          v71[2] = L"CORHDELC";
          v72 = 2493;
          v73 = 1;
          v74 = 255;
          v76 = 0x1000000;
          memset_0(v75, 0, sizeof(v75));
          CVssFunctionTracer::Trace(
            &v69,
            v71,
            L"Failed to get extents for the snapshot device. [0x%08lx].",
            (unsigned int)v17);
          if ( !a6 )
          {
            v21 = v70;
            v61 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
            v62 = L"CVssHardwareProviderWrapper::IsDiskUnused";
            v63 = L"CORHDELC";
            v64 = 2499;
            v65 = 1;
            v66 = 255;
            v68 = 0x1000000;
            memset_0(v67, 0, sizeof(v67));
            LODWORD(v24) = v21;
            CVssFunctionTracer::TranslateGenericError(
              &v69,
              &v61,
              v21,
              L"IOCTL_VOLUME_GET_VOLUME_DISK_EXTENTS failed with [0x%08lx]",
              v24);
          }
        }
        else
        {
          for ( j = v55 + 2; j < &v55[6 * *v55 + 2]; j += 6 )
          {
            if ( *j == v38 )
            {
              v61 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
              v62 = L"CVssHardwareProviderWrapper::IsDiskUnused";
              v63 = L"CORHDELC";
              v64 = 2521;
              v65 = 1;
              v66 = 255;
              v68 = 0x1000000;
              memset_0(v67, 0, sizeof(v67));
              CVssFunctionTracer::Trace(
                &v69,
                &v61,
                L"The LUN was found as part of the non-deleted snapshot volume. The LUN cannot be freed.");
              v20 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v69, 0);
              CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v47);
              SysFreeString(bstrString);
              ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v35);
              goto LABEL_30;
            }
          }
        }
      }
      CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)&v47);
      SysFreeString(bstrString);
    }
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v35);
    v7 = v60;
  }
  v61 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v62 = L"CVssHardwareProviderWrapper::IsDiskUnused";
  v63 = L"CORHDELC";
  v64 = 2527;
  v65 = 1;
  v66 = 255;
  v68 = 0x1000000;
  memset_0(v67, 0, sizeof(v67));
  CVssFunctionTracer::Trace(
    &v69,
    &v61,
    L"The LUN lun wasn't found in any other non-deleted snapshot.  It can be freed.");
  v20 = CVssFunctionTracer::Exit((CVssFunctionTracer *)&v69, 1);
LABEL_30:
  CVssFunctionTracer::~CVssFunctionTracer(&v69);
  return v20;
}

```

## disassembly

```asm
0x140077a2c  mov     [rsp-8+arg_0], rbx
0x140077a31  push    rbp
0x140077a32  push    rsi
0x140077a33  push    rdi
0x140077a34  push    r12
0x140077a36  push    r13
0x140077a38  push    r14
0x140077a3a  push    r15
0x140077a3c  lea     rbp, [rsp-2E0h]
0x140077a44  sub     rsp, 3E0h
0x140077a4b  mov     rax, cs:__security_cookie
0x140077a52  xor     rax, rsp
0x140077a55  mov     [rbp+310h+var_38], rax
0x140077a5c  mov     r15, r9
0x140077a5f  mov     rbx, r8
0x140077a62  mov     [rbp+310h+var_210], rbx
0x140077a69  mov     edi, edx
0x140077a6b  mov     [rbp+310h+var_374], edx
0x140077a6e  lea     r14, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140077a75  mov     [rbp+310h+var_2C0], r14
0x140077a79  lea     r12, aCvsshardwarepr_28; "CVssHardwareProviderWrapper::IsDiskUnus"...
0x140077a80  mov     qword ptr [rbp+310h+var_2B8], r12
0x140077a84  lea     r13, aCorhdelc; "CORHDELC"
0x140077a8b  mov     qword ptr [rbp+310h+var_2B8+8], r13
0x140077a8f  mov     dword ptr [rbp+310h+var_2A8], 971h
0x140077a96  mov     dword ptr [rbp+310h+var_2A8+4], 1
0x140077a9d  mov     dword ptr [rbp+310h+var_2A8+8], 0FFh
0x140077aa4  xor     esi, esi
0x140077aa6  mov     [rbp+310h+var_220], 1000000h
0x140077ab0  xor     edx, edx; Val
0x140077ab2  lea     r8d, [rsi+78h]; Size
0x140077ab6  lea     rcx, [rbp+310h+var_298]; void *
0x140077aba  call    memset_0
0x140077abf  xor     r8d, r8d
0x140077ac2  lea     rdx, [rbp+310h+var_2C0]
0x140077ac6  lea     rcx, [rbp+310h+var_160]
0x140077acd  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140077ad2  nop
0x140077ad3  mov     [rbp+310h+var_2C0], r14
0x140077ad7  mov     qword ptr [rbp+310h+var_2B8], r12
0x140077adb  mov     qword ptr [rbp+310h+var_2B8+8], r13
0x140077adf  mov     dword ptr [rbp+310h+var_2A8], 974h
0x140077ae6  mov     dword ptr [rbp+310h+var_2A8+4], 1
0x140077aed  mov     dword ptr [rbp+310h+var_2A8+8], 0FFh
0x140077af4  mov     [rbp+310h+var_220], 1000000h
0x140077afe  xor     edx, edx; Val
0x140077b00  lea     r8d, [rsi+78h]; Size
0x140077b04  lea     rcx, [rbp+310h+var_298]; void *
0x140077b08  call    memset_0
0x140077b0d  mov     r9d, edi
0x140077b10  lea     r8, aCheckingIfTheD; "Checking if the disk %d is in use by ot"...
0x140077b17  lea     rdx, [rbp+310h+var_2C0]
0x140077b1b  lea     rcx, [rbp+310h+var_160]
0x140077b22  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140077b27  mov     r12d, esi
0x140077b2a  mov     r13d, [rbp+310h+arg_20]
0x140077b31  test    r13d, r13d
0x140077b34  jz      loc_140077C43
0x140077b3a  lea     rcx, [rbp+310h+var_298]; void *
0x140077b3e  mov     eax, esi
0x140077b40  mov     [rbp+310h+var_388], rax
0x140077b44  mov     r14, rax
0x140077b47  add     r14, r14
0x140077b4a  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140077b51  mov     [rbp+310h+var_2C0], rax
0x140077b55  lea     rax, aCvsshardwarepr_28; "CVssHardwareProviderWrapper::IsDiskUnus"...
0x140077b5c  mov     qword ptr [rbp+310h+var_2B8], rax
0x140077b60  lea     rax, aCorhdelc; "CORHDELC"
0x140077b67  mov     qword ptr [rbp+310h+var_2B8+8], rax
0x140077b6b  mov     dword ptr [rbp+310h+var_2A8], 977h
0x140077b72  mov     dword ptr [rbp+310h+var_2A8+4], 1
0x140077b79  mov     dword ptr [rbp+310h+var_2A8+8], 0FFh
0x140077b80  mov     [rbp+310h+var_220], 1000000h
0x140077b8a  xor     edx, edx; Val
0x140077b8c  lea     r8d, [rdx+78h]; Size
0x140077b90  call    memset_0
0x140077b95  movzx   eax, byte ptr [r15+r14*8+0Fh]
0x140077b9b  movzx   ecx, byte ptr [r15+r14*8+0Eh]
0x140077ba1  movzx   edx, byte ptr [r15+r14*8+0Dh]
0x140077ba7  movzx   r8d, byte ptr [r15+r14*8+0Ch]
0x140077bad  movzx   r9d, byte ptr [r15+r14*8+0Bh]
0x140077bb3  movzx   r10d, byte ptr [r15+r14*8+0Ah]
0x140077bb9  movzx   r11d, byte ptr [r15+r14*8+9]
0x140077bbf  movzx   ebx, byte ptr [r15+r14*8+8]
0x140077bc5  movzx   edi, word ptr [r15+r14*8+6]
0x140077bcb  movzx   esi, word ptr [r15+r14*8+4]
0x140077bd1  mov     dword ptr [rsp+410h+var_3A0], eax
0x140077bd5  mov     dword ptr [rsp+410h+var_3A8], ecx
0x140077bd9  mov     dword ptr [rsp+410h+var_3B0], edx
0x140077bdd  mov     dword ptr [rsp+410h+var_3B8], r8d
0x140077be2  mov     dword ptr [rsp+410h+var_3C0], r9d
0x140077be7  mov     dword ptr [rsp+410h+var_3C8], r10d
0x140077bec  mov     dword ptr [rsp+410h+var_3D0], r11d
0x140077bf1  mov     dword ptr [rsp+410h+var_3D8], ebx
0x140077bf5  mov     dword ptr [rsp+410h+var_3E0], edi
0x140077bf9  mov     dword ptr [rsp+410h+var_3E8], esi
0x140077bfd  mov     eax, [r15+r14*8]
0x140077c01  mov     dword ptr [rsp+410h+var_3F0], eax
0x140077c05  mov     r9d, r12d
0x140077c08  lea     r8, aDeletedSnapsho; "  - Deleted snapshot[%d] {%.8x-%.4x-%.4"...
0x140077c0f  lea     rdx, [rbp+310h+var_2C0]
0x140077c13  lea     rcx, [rbp+310h+var_160]
0x140077c1a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140077c1f  inc     r12d
0x140077c22  mov     rax, [rbp+310h+var_388]
0x140077c26  inc     rax
0x140077c29  mov     [rbp+310h+var_388], rax
0x140077c2d  cmp     r12d, r13d
0x140077c30  lea     rcx, [rbp+310h+var_298]
0x140077c34  jb      loc_140077B44
0x140077c3a  mov     rbx, [rbp+310h+var_210]
0x140077c41  xor     esi, esi
0x140077c43  mov     [rbp+310h+var_378], esi
0x140077c46  mov     rax, [rbx]
0x140077c49  lea     rdx, [rbp+310h+var_378]
0x140077c4d  mov     rcx, rbx
0x140077c50  mov     rax, [rax+58h]
0x140077c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077c59  mov     [rbp+310h+var_158], eax
0x140077c5f  lea     rdi, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140077c66  mov     [rbp+310h+var_2C0], rdi
0x140077c6a  lea     rax, aCvsshardwarepr_28; "CVssHardwareProviderWrapper::IsDiskUnus"...
0x140077c71  mov     qword ptr [rbp+310h+var_2B8], rax
0x140077c75  lea     rax, aCorhdelc; "CORHDELC"
0x140077c7c  mov     qword ptr [rbp+310h+var_2B8+8], rax
0x140077c80  mov     dword ptr [rbp+310h+var_2A8], 97Ch
0x140077c87  mov     dword ptr [rbp+310h+var_2A8+4], 1
0x140077c8e  mov     dword ptr [rbp+310h+var_2A8+8], 0FFh
0x140077c95  mov     [rbp+310h+var_220], 1000000h
0x140077c9f  xor     edx, edx; Val
0x140077ca1  lea     r8d, [rdx+78h]; Size
0x140077ca5  lea     rcx, [rbp+310h+var_298]; void *
0x140077ca9  call    memset_0
0x140077cae  lea     r8, aIvsssnapshotse_8; "IVssSnapshotSetDescription::GetSnapshot"...
0x140077cb5  lea     rdx, [rbp+310h+var_2C0]
0x140077cb9  lea     rcx, [rbp+310h+var_160]
0x140077cc0  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x140077cc5  mov     r14d, esi
0x140077cc8  mov     r12b, [rbp+310h+arg_28]
0x140077ccf  lea     rax, aCvsshardwarepr_28; "CVssHardwareProviderWrapper::IsDiskUnus"...
0x140077cd6  xor     edx, edx; Val
0x140077cd8  lea     r8d, [rdx+78h]; Size
0x140077cdc  cmp     r14d, [rbp+310h+var_378]
0x140077ce0  jnb     loc_14007849E
0x140077ce6  mov     [rbp+310h+var_370], rdi
0x140077cea  mov     [rbp+310h+var_368], rax
0x140077cee  lea     rax, aCorhdelc; "CORHDELC"
0x140077cf5  mov     [rbp+310h+var_360], rax
0x140077cf9  mov     [rbp+310h+var_358], 981h
0x140077d00  mov     [rbp+310h+var_354], 1
0x140077d07  mov     [rbp+310h+var_350], 0FFh
0x140077d0e  mov     [rbp+310h+var_2D0], 1000000h
0x140077d15  lea     rcx, [rbp+310h+var_348]; void *
0x140077d19  call    memset_0
0x140077d1e  mov     r9d, r14d
0x140077d21  lea     r8, aGettingSnapsho; "Getting snapshot with index %d..."
0x140077d28  lea     rdx, [rbp+310h+var_370]
0x140077d2c  lea     rcx, [rbp+310h+var_160]
0x140077d33  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140077d38  lea     rcx, [rbp+310h+var_388]
0x140077d3c  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x140077d41  nop
0x140077d42  mov     rax, [rbx]
0x140077d45  lea     r8, [rbp+310h+var_388]
0x140077d49  mov     edx, r14d
0x140077d4c  mov     rcx, rbx
0x140077d4f  mov     rax, [rax+70h]
0x140077d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077d58  mov     [rbp+310h+var_158], eax
0x140077d5e  mov     [rbp+310h+var_370], rdi
0x140077d62  lea     rbx, aCvsshardwarepr_28; "CVssHardwareProviderWrapper::IsDiskUnus"...
0x140077d69  mov     [rbp+310h+var_368], rbx
0x140077d6d  lea     rax, aCorhdelc; "CORHDELC"
0x140077d74  mov     [rbp+310h+var_360], rax
0x140077d78  mov     [rbp+310h+var_358], 987h
0x140077d7f  mov     [rbp+310h+var_354], 1
0x140077d86  mov     [rbp+310h+var_350], 0FFh
0x140077d8d  mov     [rbp+310h+var_2D0], 1000000h
0x140077d94  xor     edx, edx; Val
0x140077d96  lea     r8d, [rdx+78h]; Size
0x140077d9a  lea     rcx, [rbp+310h+var_348]; void *
0x140077d9e  call    memset_0
0x140077da3  lea     r8, aIvsssnapshotse; "IVssSnapshotSetDescription::GetSnapshot"...
0x140077daa  lea     rdx, [rbp+310h+var_370]
0x140077dae  lea     rcx, [rbp+310h+var_160]
0x140077db5  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x140077dba  xorps   xmm0, xmm0
0x140077dbd  movups  [rbp+310h+var_48], xmm0
0x140077dc4  mov     rcx, [rbp+310h+var_388]
0x140077dc8  mov     rax, [rcx]
0x140077dcb  lea     rdx, [rbp+310h+var_48]
0x140077dd2  mov     rax, [rax+18h]
0x140077dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077ddb  mov     [rbp+310h+var_158], eax
0x140077de1  mov     [rbp+310h+var_370], rdi
0x140077de5  mov     [rbp+310h+var_368], rbx
0x140077de9  lea     rax, aCorhdelc; "CORHDELC"
0x140077df0  mov     [rbp+310h+var_360], rax
0x140077df4  mov     [rbp+310h+var_358], 98Ch
0x140077dfb  mov     [rbp+310h+var_354], 1
0x140077e02  mov     [rbp+310h+var_350], 0FFh
0x140077e09  mov     [rbp+310h+var_2D0], 1000000h
0x140077e10  xor     edx, edx; Val
0x140077e12  lea     r8d, [rdx+78h]; Size
0x140077e16  lea     rcx, [rbp+310h+var_348]; void *
0x140077e1a  call    memset_0
0x140077e1f  lea     r8, aIvsssnapshotde_17; "IVssSnapshotDescription::GetSnapshotId"
0x140077e26  lea     rdx, [rbp+310h+var_370]
0x140077e2a  lea     rcx, [rbp+310h+var_160]
0x140077e31  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x140077e36  mov     [rbp+310h+var_370], rdi
0x140077e3a  mov     [rbp+310h+var_368], rbx
0x140077e3e  lea     rax, aCorhdelc; "CORHDELC"
0x140077e45  mov     [rbp+310h+var_360], rax
0x140077e49  mov     [rbp+310h+var_358], 98Eh
0x140077e50  mov     [rbp+310h+var_354], 1
0x140077e57  mov     [rbp+310h+var_350], 0FFh
0x140077e5e  mov     [rbp+310h+var_2D0], 1000000h
0x140077e65  xor     edx, edx; Val
0x140077e67  lea     r8d, [rdx+78h]; Size
0x140077e6b  lea     rcx, [rbp+310h+var_348]; void *
0x140077e6f  call    memset_0
0x140077e74  movzx   eax, byte ptr [rbp+310h+var_48+0Fh]
0x140077e7b  movzx   ecx, byte ptr [rbp+310h+var_48+0Eh]
0x140077e82  movzx   edx, byte ptr [rbp+310h+var_48+0Dh]
0x140077e89  movzx   r8d, byte ptr [rbp+310h+var_48+0Ch]
0x140077e91  movzx   r9d, byte ptr [rbp+310h+var_48+0Bh]
0x140077e99  movzx   r10d, byte ptr [rbp+310h+var_48+0Ah]
0x140077ea1  movzx   r11d, byte ptr [rbp+310h+var_48+9]
0x140077ea9  movzx   ebx, byte ptr [rbp+310h+var_48+8]
0x140077eb0  movzx   edi, word ptr [rbp+310h+var_48+6]
0x140077eb7  movzx   esi, word ptr [rbp+310h+var_48+4]
0x140077ebe  mov     dword ptr [rsp+410h+var_3A8], eax
0x140077ec2  mov     dword ptr [rsp+410h+var_3B0], ecx
0x140077ec6  mov     dword ptr [rsp+410h+var_3B8], edx
0x140077eca  mov     dword ptr [rsp+410h+var_3C0], r8d
0x140077ecf  mov     dword ptr [rsp+410h+var_3C8], r9d
0x140077ed4  mov     dword ptr [rsp+410h+var_3D0], r10d
0x140077ed9  mov     dword ptr [rsp+410h+var_3D8], r11d
0x140077ede  mov     dword ptr [rsp+410h+var_3E0], ebx
0x140077ee2  mov     dword ptr [rsp+410h+var_3E8], edi
0x140077ee6  mov     dword ptr [rsp+410h+var_3F0], esi
0x140077eea  mov     r9d, dword ptr [rbp+310h+var_48]
0x140077ef1  lea     r8, aSnapshotId8x4x; "Snapshot ID = {%.8x-%.4x-%.4x-%.2x%.2x-"...
0x140077ef8  lea     rdx, [rbp+310h+var_370]
0x140077efc  lea     rcx, [rbp+310h+var_160]
0x140077f03  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140077f08  xor     esi, esi
0x140077f0a  mov     edx, esi
0x140077f0c  test    r13d, r13d
0x140077f0f  jz      loc_140077FAE
0x140077f15  mov     ecx, edx
0x140077f17  shl     rcx, 4
0x140077f1b  mov     rax, qword ptr [rbp+310h+var_48]
0x140077f22  sub     rax, [rcx+r15]
0x140077f26  jnz     short loc_140077F34
0x140077f28  mov     rax, qword ptr [rbp+310h+var_48+8]
0x140077f2f  sub     rax, [rcx+r15+8]
0x140077f34  test    rax, rax
0x140077f37  jz      short loc_140077F40
0x140077f39  inc     edx
0x140077f3b  cmp     edx, r13d
0x140077f3e  jb      short loc_140077F15
0x140077f40  cmp     edx, r13d
0x140077f43  jnb     short loc_140077FAE
0x140077f45  lea     rdi, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140077f4c  mov     [rbp+310h+var_370], rdi
0x140077f50  lea     rax, aCvsshardwarepr_28; "CVssHardwareProviderWrapper::IsDiskUnus"...
0x140077f57  mov     [rbp+310h+var_368], rax
0x140077f5b  lea     rax, aCorhdelc; "CORHDELC"
0x140077f62  mov     [rbp+310h+var_360], rax
0x140077f66  mov     [rbp+310h+var_358], 99Bh
0x140077f6d  mov     [rbp+310h+var_354], 1
0x140077f74  mov     [rbp+310h+var_350], 0FFh
0x140077f7b  mov     [rbp+310h+var_2D0], 1000000h
0x140077f82  xor     edx, edx; Val
0x140077f84  lea     r8d, [rdx+78h]; Size
0x140077f88  lea     rcx, [rbp+310h+var_348]; void *
0x140077f8c  call    memset_0
0x140077f91  lea     r8, aSnapshotAlread; "Snapshot already deleted. Continuing wi"...
0x140077f98  lea     rdx, [rbp+310h+var_370]
0x140077f9c  lea     rcx, [rbp+310h+var_160]
0x140077fa3  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140077fa8  nop
0x140077fa9  jmp     loc_1400782C8
0x140077fae  mov     [rbp+310h+bstrString], rsi
0x140077fb2  mov     rcx, [rbp+310h+var_388]
0x140077fb6  mov     rax, [rcx]
0x140077fb9  lea     rdx, [rbp+310h+bstrString]
0x140077fbd  mov     rax, [rax+80h]
0x140077fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077fc9  mov     [rbp+310h+var_158], eax
0x140077fcf  lea     rdi, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x140077fd6  mov     [rbp+310h+var_370], rdi
0x140077fda  lea     rbx, aCvsshardwarepr_28; "CVssHardwareProviderWrapper::IsDiskUnus"...
0x140077fe1  mov     [rbp+310h+var_368], rbx
0x140077fe5  lea     rax, aCorhdelc; "CORHDELC"
0x140077fec  mov     [rbp+310h+var_360], rax
0x140077ff0  mov     [rbp+310h+var_358], 9A3h
0x140077ff7  mov     [rbp+310h+var_354], 1
  ... truncated ...
```
