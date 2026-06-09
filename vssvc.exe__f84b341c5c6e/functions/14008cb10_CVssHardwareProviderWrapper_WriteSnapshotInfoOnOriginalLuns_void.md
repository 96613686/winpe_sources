# CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns(void)

- ea: `0x14008cb10`
- end: `0x14008d21d`
- name: `?WriteSnapshotInfoOnOriginalLuns@CVssHardwareProviderWrapper@@AEAAXXZ`
- size: `1805`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14008c610`

## callees

- `0x1400088fc`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140025b00`
- `0x14003c160`
- `0x14003fc04`
- `0x140049ec4`
- `0x140069108`
- `0x140069dbc`
- `0x14008cb10`
- `0x140091560`
- `0x1400921dc`
- `0x1400bf618`
- `0x1400f4010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14008d0d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14008d100`
- `OLEAUT32!__imp_SysFreeString` at `0x14008d10b`
- `OLEAUT32!__imp_SysFreeString` at `0x14008d1e7`
- `OLEAUT32!__imp_SysFreeString` at `0x14008d0d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14008d100`
- `OLEAUT32!__imp_SysFreeString` at `0x14008d10b`
- `OLEAUT32!__imp_SysFreeString` at `0x14008d1e7`

## string_xrefs

- `0x14008cb4b`: `CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns`
- `0x14008cd76`: `CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns`
- `0x14008cf34`: `CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns`
- `0x14008d0f0`: `CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns`
- `0x14008d12e`: `CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns`
- `0x14008d18a`: `CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns`
- `0x14008d16b`: `StringCchCopyW()`
- `0x14008d1c0`: `StringCchCopyW()`
- `0x14008cfea`: `Original volume %s also lies on %s. It already has LUN id{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns(CVssHardwareProviderWrapper *this)
{
  __int64 v2; // rdx
  unsigned int i; // r15d
  int v4; // ebx
  unsigned int j; // r14d
  int v6; // ebx
  bool v7; // al
  __int64 v8; // [rsp+28h] [rbp-D8h]
  __int64 v9; // [rsp+30h] [rbp-D0h]
  __int64 v10; // [rsp+38h] [rbp-C8h]
  __int64 v11; // [rsp+40h] [rbp-C0h]
  __int64 v12; // [rsp+48h] [rbp-B8h]
  __int64 v13; // [rsp+50h] [rbp-B0h]
  __int64 v14; // [rsp+58h] [rbp-A8h]
  __int64 v15; // [rsp+60h] [rbp-A0h]
  __int64 v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  int v19[2]; // [rsp+80h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v21; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v22; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v23; // [rsp+A0h] [rbp-60h]
  int v24; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+ACh] [rbp-54h]
  int v26; // [rsp+B0h] [rbp-50h]
  _BYTE v27[120]; // [rsp+B8h] [rbp-48h] BYREF
  int v28; // [rsp+130h] [rbp+30h]
  unsigned int v29; // [rsp+138h] [rbp+38h] BYREF
  unsigned int v30; // [rsp+13Ch] [rbp+3Ch] BYREF
  __int64 v31; // [rsp+140h] [rbp+40h] BYREF
  BSTR v32; // [rsp+148h] [rbp+48h] BYREF
  __int64 v33; // [rsp+150h] [rbp+50h] BYREF
  BSTR v34; // [rsp+158h] [rbp+58h] BYREF
  GUID v35; // [rsp+160h] [rbp+60h] BYREF
  int v36[4]; // [rsp+170h] [rbp+70h] BYREF
  LPVOID v37; // [rsp+180h] [rbp+80h] BYREF
  int v38; // [rsp+188h] [rbp+88h]
  __int64 v39; // [rsp+1F0h] [rbp+F0h]
  GUID pguid; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v41[264]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v42[264]; // [rsp+420h] [rbp+320h] BYREF

  v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
  v23 = L"CORHWUTC";
  v24 = 673;
  v25 = 1;
  v26 = 255;
  v28 = 0x1000000;
  memset_0(v27, 0, sizeof(v27));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v37, (__int64)&v21, 0);
  v39 = 0;
  v29 = 0;
  ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>(v36);
  v38 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 14) + 88LL))(
          *((_QWORD *)this + 14),
          &v29);
  v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
  v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
  v23 = L"CORHWUTC";
  v24 = 682;
  v25 = 1;
  v26 = 255;
  v28 = 0x1000000;
  memset_0(v27, 0, sizeof(v27));
  CVssFunctionTracer::CheckForErrorInternal(&v37, &v21, L"IVssSnapshotSetDescription::GetSnapshotCount");
  for ( i = 0; i < v29; ++i )
  {
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v19);
    v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)this + 14) + 112LL))(
            *((_QWORD *)this + 14),
            i,
            v19);
    v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
    v23 = L"CORHWUTC";
    v24 = 691;
    v25 = 1;
    v26 = 255;
    v28 = 0x1000000;
    memset_0(v27, 0, sizeof(v27));
    CVssFunctionTracer::CheckForErrorInternal(&v37, &v21, L"IVssSnapshotSetDescription::GetSnapshotDescription");
    v32 = 0;
    v34 = 0;
    v38 = (*(__int64 (__fastcall **)(_QWORD, BSTR *, BSTR *))(**(_QWORD **)v19 + 80LL))(*(_QWORD *)v19, &v32, &v34);
    v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
    v23 = L"CORHWUTC";
    v24 = 696;
    v25 = 1;
    v26 = 255;
    v28 = 0x1000000;
    memset_0(v27, 0, sizeof(v27));
    CVssFunctionTracer::CheckForErrorInternal(&v37, &v21, L"IVssSnaphotDescription::GetOrigin");
    v30 = 0;
    pguid = GUID_NULL;
    LODWORD(v33) = 0;
    memset_0(v42, 0, 0x208u);
    v4 = StringCchCopyW(v42, 0x104u, v34);
    v38 = v4;
    if ( v4 < 0 )
    {
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
      v23 = L"CORHWUTC";
      v24 = 706;
      v25 = 1;
      v26 = 255;
      v28 = 0x1000000;
      memset_0(v27, 0, sizeof(v27));
      CVssFunctionTracer::TranslateGenericError(&v37, &v21, (unsigned int)v4, L"StringCchCopyW()");
    }
    (*(void (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v19 + 160LL))(*(_QWORD *)v19, &v30);
    v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
    v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
    v23 = L"CORHWUTC";
    v24 = 710;
    v25 = 1;
    v26 = 255;
    v28 = 0x1000000;
    memset_0(v27, 0, sizeof(v27));
    CVssFunctionTracer::CheckForErrorInternal(&v37, &v21, L"IVssSnaphotDescription::GetLunCount");
    for ( j = 0; j < v30; ++j )
    {
      ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v31);
      bstrString = 0;
      memset_0(v41, 0, 0x208u);
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v19 + 176LL))(*(_QWORD *)v19, j, &v31);
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
      v23 = L"CORHWUTC";
      v24 = 719;
      v25 = 1;
      v26 = 255;
      v28 = 0x1000000;
      memset_0(v27, 0, sizeof(v27));
      CVssFunctionTracer::CheckForErrorInternal(&v37, &v21, L"IVssSnaphotDescription::GetLunMapping");
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v31 + 48LL))(v31, &bstrString);
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
      v23 = L"CORHWUTC";
      v24 = 722;
      v25 = 1;
      v26 = 255;
      v28 = 0x1000000;
      memset_0(v27, 0, sizeof(v27));
      CVssFunctionTracer::CheckForErrorInternal(&v37, &v21, L"IVssSnaphotDescription::GetSourceDevice");
      v6 = StringCchCopyW(v41, 0x104u, bstrString);
      v38 = v6;
      if ( v6 < 0 )
      {
        v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
        v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
        v23 = L"CORHWUTC";
        v24 = 726;
        v25 = 1;
        v26 = 255;
        v28 = 0x1000000;
        memset_0(v27, 0, sizeof(v27));
        CVssFunctionTracer::TranslateGenericError(&v37, &v21, (unsigned int)v6, L"StringCchCopyW()");
      }
      v7 = CVssHardwareProviderWrapper::MoveDiskToDetectSnapState(
             (__int64)this,
             v41,
             *(__int64 *)v19,
             (__int64)v36,
             &pguid,
             (unsigned int *)&v33);
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\hwutils.cxx";
      v25 = 1;
      v26 = 255;
      v28 = 0x1000000;
      v22 = L"CVssHardwareProviderWrapper::WriteSnapshotInfoOnOriginalLuns";
      v23 = L"CORHWUTC";
      if ( v7 )
      {
        v24 = 737;
        memset_0(v27, 0, sizeof(v27));
        LODWORD(v18) = pguid.Data4[7];
        LODWORD(v17) = pguid.Data4[6];
        LODWORD(v16) = pguid.Data4[5];
        LODWORD(v15) = pguid.Data4[4];
        LODWORD(v14) = pguid.Data4[3];
        LODWORD(v13) = pguid.Data4[2];
        LODWORD(v12) = pguid.Data4[1];
        LODWORD(v11) = pguid.Data4[0];
        LODWORD(v10) = pguid.Data3;
        LODWORD(v9) = pguid.Data2;
        LODWORD(v8) = pguid.Data1;
        CVssFunctionTracer::Trace(
          &v37,
          &v21,
          L"Device %s for original volume %s given LUN id{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
          v41,
          v42,
          v8,
          v9,
          v10,
          v11,
          v12,
          v13,
          v14,
          v15,
          v16,
          v17,
          v18);
      }
      else
      {
        v24 = 735;
        memset_0(v27, 0, sizeof(v27));
        LODWORD(v18) = pguid.Data4[7];
        LODWORD(v17) = pguid.Data4[6];
        LODWORD(v16) = pguid.Data4[5];
        LODWORD(v15) = pguid.Data4[4];
        LODWORD(v14) = pguid.Data4[3];
        LODWORD(v13) = pguid.Data4[2];
        LODWORD(v12) = pguid.Data4[1];
        LODWORD(v11) = pguid.Data4[0];
        LODWORD(v10) = pguid.Data3;
        LODWORD(v9) = pguid.Data2;
        LODWORD(v8) = pguid.Data1;
        CVssFunctionTracer::Trace(
          &v37,
          &v21,
          L"Original volume %s also lies on %s. It already has LUN id{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
          v42,
          v41,
          v8,
          v9,
          v10,
          v11,
          v12,
          v13,
          v14,
          v15,
          v16,
          v17,
          v18);
      }
      v35 = pguid;
      (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v31 + 88LL))(v31, &v35);
      SysFreeString(bstrString);
      ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v31);
    }
    SysFreeString(v34);
    SysFreeString(v32);
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v19);
  }
  ATL::CSimpleArray<_HRESOURCE *,ATL::CSimpleArrayEqualHelper<_HRESOURCE *>>::~CSimpleArray<_HRESOURCE *,ATL::CSimpleArrayEqualHelper<_HRESOURCE *>>(
    v36,
    v2);
  SysFreeString(0);
  CVssFunctionTracer::~CVssFunctionTracer(&v37);
}

```

## disassembly

```asm
0x14008cb10  push    rbp
0x14008cb12  push    rbx
0x14008cb13  push    rsi
0x14008cb14  push    rdi
0x14008cb15  push    r12
0x14008cb17  push    r13
0x14008cb19  push    r14
0x14008cb1b  push    r15
0x14008cb1d  lea     rbp, [rsp-548h]
0x14008cb25  sub     rsp, 648h
0x14008cb2c  mov     rax, cs:__security_cookie
0x14008cb33  xor     rax, rsp
0x14008cb36  mov     [rbp+580h+var_50], rax
0x14008cb3d  mov     r13, rcx
0x14008cb40  lea     rsi, aBaseStorVssMod_21; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x14008cb47  mov     [rbp+580h+var_5F0], rsi
0x14008cb4b  lea     rbx, aCvsshardwarepr_53; "CVssHardwareProviderWrapper::WriteSnaps"...
0x14008cb52  mov     [rbp+580h+var_5E8], rbx
0x14008cb56  lea     r14, aCorhwutc; "CORHWUTC"
0x14008cb5d  mov     [rbp+580h+var_5E0], r14
0x14008cb61  mov     [rbp+580h+var_5D8], 2A1h
0x14008cb68  mov     edi, 1
0x14008cb6d  mov     [rbp+580h+var_5D4], edi
0x14008cb70  mov     r15d, 0FFh
0x14008cb76  mov     [rbp+580h+var_5D0], r15d
0x14008cb7a  xor     r12d, r12d
0x14008cb7d  mov     [rbp+580h+var_550], 1000000h
0x14008cb84  xor     edx, edx; Val
0x14008cb86  lea     r8d, [rdi+77h]; Size
0x14008cb8a  lea     rcx, [rbp+580h+var_5C8]; void *
0x14008cb8e  call    memset_0
0x14008cb93  xor     r8d, r8d
0x14008cb96  lea     rdx, [rbp+580h+var_5F0]
0x14008cb9a  lea     rcx, [rbp+580h+var_500]
0x14008cba1  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x14008cba6  nop
0x14008cba7  mov     [rbp+580h+var_490], r12
0x14008cbae  mov     [rbp+580h+var_548], r12d
0x14008cbb2  lea     rcx, [rbp+580h+var_510]
0x14008cbb6  call    ??0?$CSimpleArray@UCVssSnapshotShareInfo@@V?$CSimpleArrayEqualHelper@UCVssSnapshotShareInfo@@@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>(void)
0x14008cbbb  nop
0x14008cbbc  mov     rcx, [r13+70h]
0x14008cbc0  mov     rax, [rcx]
0x14008cbc3  lea     rdx, [rbp+580h+var_548]
0x14008cbc7  mov     rax, [rax+58h]
0x14008cbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cbd0  mov     [rbp+580h+var_4F8], eax
0x14008cbd6  mov     [rbp+580h+var_5F0], rsi
0x14008cbda  mov     [rbp+580h+var_5E8], rbx
0x14008cbde  mov     [rbp+580h+var_5E0], r14
0x14008cbe2  mov     [rbp+580h+var_5D8], 2AAh
0x14008cbe9  mov     [rbp+580h+var_5D4], edi
0x14008cbec  mov     [rbp+580h+var_5D0], r15d
0x14008cbf0  mov     [rbp+580h+var_550], 1000000h
0x14008cbf7  xor     edx, edx; Val
0x14008cbf9  lea     r8d, [rdi+77h]; Size
0x14008cbfd  lea     rcx, [rbp+580h+var_5C8]; void *
0x14008cc01  call    memset_0
0x14008cc06  lea     r8, aIvsssnapshotse_8; "IVssSnapshotSetDescription::GetSnapshot"...
0x14008cc0d  lea     rdx, [rbp+580h+var_5F0]
0x14008cc11  lea     rcx, [rbp+580h+var_500]
0x14008cc18  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14008cc1d  mov     r15d, r12d
0x14008cc20  cmp     r15d, [rbp+580h+var_548]
0x14008cc24  jnb     loc_14008D1DB
0x14008cc2a  lea     rcx, [rbp+580h+var_600]
0x14008cc2e  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14008cc33  nop
0x14008cc34  mov     rcx, [r13+70h]
0x14008cc38  mov     rax, [rcx]
0x14008cc3b  lea     r8, [rbp+580h+var_600]
0x14008cc3f  mov     edx, r15d
0x14008cc42  mov     rax, [rax+70h]
0x14008cc46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cc4b  mov     [rbp+580h+var_4F8], eax
0x14008cc51  mov     [rbp+580h+var_5F0], rsi
0x14008cc55  mov     [rbp+580h+var_5E8], rbx
0x14008cc59  mov     [rbp+580h+var_5E0], r14
0x14008cc5d  mov     [rbp+580h+var_5D8], 2B3h
0x14008cc64  mov     [rbp+580h+var_5D4], edi
0x14008cc67  mov     [rbp+580h+var_5D0], 0FFh
0x14008cc6e  mov     [rbp+580h+var_550], 1000000h
0x14008cc75  xor     edx, edx; Val
0x14008cc77  lea     r8d, [rdx+78h]; Size
0x14008cc7b  lea     rcx, [rbp+580h+var_5C8]; void *
0x14008cc7f  call    memset_0
0x14008cc84  lea     r8, aIvsssnapshotse; "IVssSnapshotSetDescription::GetSnapshot"...
0x14008cc8b  lea     rdx, [rbp+580h+var_5F0]
0x14008cc8f  lea     rcx, [rbp+580h+var_500]
0x14008cc96  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14008cc9b  mov     [rbp+580h+var_538], r12
0x14008cc9f  mov     [rbp+580h+var_528], r12
0x14008cca3  mov     rcx, qword ptr [rbp+580h+var_600]
0x14008cca7  mov     rax, [rcx]
0x14008ccaa  lea     r8, [rbp+580h+var_528]
0x14008ccae  lea     rdx, [rbp+580h+var_538]
0x14008ccb2  mov     rax, [rax+50h]
0x14008ccb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ccbb  mov     [rbp+580h+var_4F8], eax
0x14008ccc1  mov     [rbp+580h+var_5F0], rsi
0x14008ccc5  mov     [rbp+580h+var_5E8], rbx
0x14008ccc9  mov     [rbp+580h+var_5E0], r14
0x14008cccd  mov     [rbp+580h+var_5D8], 2B8h
0x14008ccd4  mov     [rbp+580h+var_5D4], edi
0x14008ccd7  mov     [rbp+580h+var_5D0], 0FFh
0x14008ccde  mov     [rbp+580h+var_550], 1000000h
0x14008cce5  xor     edx, edx; Val
0x14008cce7  lea     r8d, [rdx+78h]; Size
0x14008cceb  lea     rcx, [rbp+580h+var_5C8]; void *
0x14008ccef  call    memset_0
0x14008ccf4  lea     r8, aIvsssnaphotdes; "IVssSnaphotDescription::GetOrigin"
0x14008ccfb  lea     rdx, [rbp+580h+var_5F0]
0x14008ccff  lea     rcx, [rbp+580h+var_500]
0x14008cd06  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14008cd0b  mov     [rbp+580h+var_544], r12d
0x14008cd0f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14008cd16  movdqu  xmmword ptr [rbp+580h+var_480.Data1], xmm0
0x14008cd1e  mov     dword ptr [rbp+580h+var_530], r12d
0x14008cd22  xor     edx, edx; Val
0x14008cd24  mov     r8d, 208h; Size
0x14008cd2a  lea     rcx, [rbp+580h+var_260]; void *
0x14008cd31  call    memset_0
0x14008cd36  mov     r8, [rbp+580h+var_528]; unsigned __int16 *
0x14008cd3a  mov     edx, 104h; unsigned __int64
0x14008cd3f  lea     rcx, [rbp+580h+var_260]; unsigned __int16 *
0x14008cd46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14008cd4b  mov     ebx, eax
0x14008cd4d  mov     [rbp+580h+var_4F8], eax
0x14008cd53  test    eax, eax
0x14008cd55  js      loc_14008D186
0x14008cd5b  mov     rcx, qword ptr [rbp+580h+var_600]
0x14008cd5f  mov     rax, [rcx]
0x14008cd62  lea     rdx, [rbp+580h+var_544]
0x14008cd66  mov     rax, [rax+0A0h]
0x14008cd6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008cd72  mov     [rbp+580h+var_5F0], rsi
0x14008cd76  lea     rbx, aCvsshardwarepr_53; "CVssHardwareProviderWrapper::WriteSnaps"...
0x14008cd7d  mov     [rbp+580h+var_5E8], rbx
0x14008cd81  mov     [rbp+580h+var_5E0], r14
0x14008cd85  mov     [rbp+580h+var_5D8], 2C6h
0x14008cd8c  mov     [rbp+580h+var_5D4], edi
0x14008cd8f  mov     [rbp+580h+var_5D0], 0FFh
0x14008cd96  mov     [rbp+580h+var_550], 1000000h
0x14008cd9d  xor     edx, edx; Val
0x14008cd9f  lea     r8d, [rdx+78h]; Size
0x14008cda3  lea     rcx, [rbp+580h+var_5C8]; void *
0x14008cda7  call    memset_0
0x14008cdac  lea     r8, aIvsssnaphotdes_1; "IVssSnaphotDescription::GetLunCount"
0x14008cdb3  lea     rdx, [rbp+580h+var_5F0]
0x14008cdb7  lea     rcx, [rbp+580h+var_500]
0x14008cdbe  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14008cdc3  mov     r14d, r12d
0x14008cdc6  cmp     r14d, [rbp+580h+var_544]
0x14008cdca  jnb     loc_14008D0FC
0x14008cdd0  lea     rcx, [rbp+580h+var_540]
0x14008cdd4  call    ??0?$CComPtr@UIMultiInterfacePublisherFilter@@@ATL@@QEAA@XZ; ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(void)
0x14008cdd9  nop
0x14008cdda  mov     [rbp+580h+bstrString], r12
0x14008cdde  xor     edx, edx; Val
0x14008cde0  mov     r8d, 208h; Size
0x14008cde6  lea     rcx, [rbp+580h+var_470]; void *
0x14008cded  call    memset_0
0x14008cdf2  mov     rcx, qword ptr [rbp+580h+var_600]
0x14008cdf6  mov     rax, [rcx]
0x14008cdf9  lea     r8, [rbp+580h+var_540]
0x14008cdfd  mov     edx, r14d
0x14008ce00  mov     rax, [rax+0B0h]
0x14008ce07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ce0c  mov     [rbp+580h+var_5F0], rsi
0x14008ce10  mov     [rbp+580h+var_5E8], rbx
0x14008ce14  lea     rax, aCorhwutc; "CORHWUTC"
0x14008ce1b  mov     [rbp+580h+var_5E0], rax
0x14008ce1f  mov     [rbp+580h+var_5D8], 2CFh
0x14008ce26  mov     [rbp+580h+var_5D4], edi
0x14008ce29  mov     [rbp+580h+var_5D0], 0FFh
0x14008ce30  mov     [rbp+580h+var_550], 1000000h
0x14008ce37  xor     edx, edx; Val
0x14008ce39  lea     r8d, [rdx+78h]; Size
0x14008ce3d  lea     rcx, [rbp+580h+var_5C8]; void *
0x14008ce41  call    memset_0
0x14008ce46  lea     r8, aIvsssnaphotdes_2; "IVssSnaphotDescription::GetLunMapping"
0x14008ce4d  lea     rdx, [rbp+580h+var_5F0]
0x14008ce51  lea     rcx, [rbp+580h+var_500]
0x14008ce58  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14008ce5d  mov     rcx, [rbp+580h+var_540]
0x14008ce61  mov     rax, [rcx]
0x14008ce64  lea     rdx, [rbp+580h+bstrString]
0x14008ce68  mov     rax, [rax+30h]
0x14008ce6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ce71  mov     [rbp+580h+var_5F0], rsi
0x14008ce75  mov     [rbp+580h+var_5E8], rbx
0x14008ce79  lea     rax, aCorhwutc; "CORHWUTC"
0x14008ce80  mov     [rbp+580h+var_5E0], rax
0x14008ce84  mov     [rbp+580h+var_5D8], 2D2h
0x14008ce8b  mov     [rbp+580h+var_5D4], edi
0x14008ce8e  mov     [rbp+580h+var_5D0], 0FFh
0x14008ce95  mov     [rbp+580h+var_550], 1000000h
0x14008ce9c  xor     edx, edx; Val
0x14008ce9e  lea     r8d, [rdx+78h]; Size
0x14008cea2  lea     rcx, [rbp+580h+var_5C8]; void *
0x14008cea6  call    memset_0
0x14008ceab  lea     r8, aIvsssnaphotdes_0; "IVssSnaphotDescription::GetSourceDevice"
0x14008ceb2  lea     rdx, [rbp+580h+var_5F0]
0x14008ceb6  lea     rcx, [rbp+580h+var_500]
0x14008cebd  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x14008cec2  mov     r8, [rbp+580h+bstrString]; unsigned __int16 *
0x14008cec6  mov     edx, 104h; unsigned __int64
0x14008cecb  lea     rcx, [rbp+580h+var_470]; unsigned __int16 *
0x14008ced2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14008ced7  mov     ebx, eax
0x14008ced9  mov     [rbp+580h+var_4F8], eax
0x14008cedf  test    eax, eax
0x14008cee1  js      loc_14008D12A
0x14008cee7  lea     rax, [rbp+580h+var_530]
0x14008ceeb  mov     [rsp+680h+var_658], rax; __int64
0x14008cef0  lea     rax, [rbp+580h+var_480]
0x14008cef7  mov     [rsp+680h+pguid], rax; pguid
0x14008cefc  lea     r9, [rbp+580h+var_510]; int
0x14008cf00  mov     r8, qword ptr [rbp+580h+var_600]; int
0x14008cf04  lea     rdx, [rbp+580h+var_470]; int
0x14008cf0b  mov     rcx, r13; int
0x14008cf0e  call    ?MoveDiskToDetectSnapState@CVssHardwareProviderWrapper@@AEAA_NPEBGPEAVIVssSnapshotDescription@@AEAV?$CVssSimpleArray@K@@AEAU_GUID@@AEAK@Z; CVssHardwareProviderWrapper::MoveDiskToDetectSnapState(ushort const *,IVssSnapshotDescription *,CVssSimpleArray<ulong> &,_GUID &,ulong &)
0x14008cf13  mov     [rbp+580h+var_5F0], rsi
0x14008cf17  mov     [rbp+580h+var_5D4], edi
0x14008cf1a  mov     [rbp+580h+var_5D0], 0FFh
0x14008cf21  mov     [rbp+580h+var_550], 1000000h
0x14008cf28  xor     edx, edx; Val
0x14008cf2a  lea     r8d, [rdx+78h]; Size
0x14008cf2e  lea     rcx, [rbp+580h+var_5C8]; void *
0x14008cf32  test    al, al
0x14008cf34  lea     rax, aCvsshardwarepr_53; "CVssHardwareProviderWrapper::WriteSnaps"...
0x14008cf3b  mov     [rbp+580h+var_5E8], rax
0x14008cf3f  lea     rax, aCorhwutc; "CORHWUTC"
0x14008cf46  mov     [rbp+580h+var_5E0], rax
0x14008cf4a  jnz     loc_14008CFF6
0x14008cf50  mov     [rbp+580h+var_5D8], 2DFh
0x14008cf57  call    memset_0
0x14008cf5c  movzx   eax, [rbp+580h+var_480.Data4+7]
0x14008cf63  movzx   ecx, [rbp+580h+var_480.Data4+6]
0x14008cf6a  movzx   edx, [rbp+580h+var_480.Data4+5]
0x14008cf71  movzx   r8d, [rbp+580h+var_480.Data4+4]
0x14008cf79  movzx   r9d, [rbp+580h+var_480.Data4+3]
0x14008cf81  movzx   r10d, [rbp+580h+var_480.Data4+2]
0x14008cf89  movzx   r11d, [rbp+580h+var_480.Data4+1]
0x14008cf91  movzx   ebx, [rbp+580h+var_480.Data4]
0x14008cf98  movzx   edi, [rbp+580h+var_480.Data3]
0x14008cf9f  movzx   esi, [rbp+580h+var_480.Data2]
0x14008cfa6  mov     dword ptr [rsp+680h+var_608], eax
0x14008cfaa  mov     dword ptr [rsp+680h+var_610], ecx
0x14008cfae  mov     dword ptr [rsp+680h+var_618], edx
0x14008cfb2  mov     dword ptr [rsp+680h+var_620], r8d
0x14008cfb7  mov     dword ptr [rsp+680h+var_628], r9d
0x14008cfbc  mov     dword ptr [rsp+680h+var_630], r10d
0x14008cfc1  mov     dword ptr [rsp+680h+var_638], r11d
0x14008cfc6  mov     dword ptr [rsp+680h+var_640], ebx
0x14008cfca  mov     dword ptr [rsp+680h+var_648], edi
0x14008cfce  mov     dword ptr [rsp+680h+var_650], esi
0x14008cfd2  mov     eax, [rbp+580h+var_480.Data1]
0x14008cfd8  mov     dword ptr [rsp+680h+var_658], eax
0x14008cfdc  lea     rax, [rbp+580h+var_470]
0x14008cfe3  lea     r9, [rbp+580h+var_260]
0x14008cfea  lea     r8, aOriginalVolume; "Original volume %s also lies on %s. It "...
0x14008cff1  jmp     loc_14008D097
0x14008cff6  mov     [rbp+580h+var_5D8], 2E1h
0x14008cffd  call    memset_0
0x14008d002  movzx   eax, [rbp+580h+var_480.Data4+7]
0x14008d009  movzx   ecx, [rbp+580h+var_480.Data4+6]
0x14008d010  movzx   edx, [rbp+580h+var_480.Data4+5]
0x14008d017  movzx   r8d, [rbp+580h+var_480.Data4+4]
0x14008d01f  movzx   r9d, [rbp+580h+var_480.Data4+3]
0x14008d027  movzx   r10d, [rbp+580h+var_480.Data4+2]
0x14008d02f  movzx   r11d, [rbp+580h+var_480.Data4+1]
0x14008d037  movzx   ebx, [rbp+580h+var_480.Data4]
0x14008d03e  movzx   edi, [rbp+580h+var_480.Data3]
0x14008d045  movzx   esi, [rbp+580h+var_480.Data2]
0x14008d04c  mov     dword ptr [rsp+680h+var_608], eax
0x14008d050  mov     dword ptr [rsp+680h+var_610], ecx
0x14008d054  mov     dword ptr [rsp+680h+var_618], edx
0x14008d058  mov     dword ptr [rsp+680h+var_620], r8d
0x14008d05d  mov     dword ptr [rsp+680h+var_628], r9d
0x14008d062  mov     dword ptr [rsp+680h+var_630], r10d
0x14008d067  mov     dword ptr [rsp+680h+var_638], r11d
0x14008d06c  mov     dword ptr [rsp+680h+var_640], ebx
0x14008d070  mov     dword ptr [rsp+680h+var_648], edi
0x14008d074  mov     dword ptr [rsp+680h+var_650], esi
0x14008d078  mov     eax, [rbp+580h+var_480.Data1]
0x14008d07e  mov     dword ptr [rsp+680h+var_658], eax
0x14008d082  lea     rax, [rbp+580h+var_260]
0x14008d089  lea     r9, [rbp+580h+var_470]
0x14008d090  lea     r8, aDeviceSForOrig; "Device %s for original volume %s given "...
0x14008d097  mov     [rsp+680h+pguid], rax
0x14008d09c  lea     rdx, [rbp+580h+var_5F0]
0x14008d0a0  lea     rcx, [rbp+580h+var_500]
0x14008d0a7  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14008d0ac  mov     rcx, [rbp+580h+var_540]
0x14008d0b0  movaps  xmm0, xmmword ptr [rbp+580h+var_480.Data1]
0x14008d0b7  movdqa  [rbp+580h+var_520], xmm0
0x14008d0bc  mov     rax, [rcx]
0x14008d0bf  lea     rdx, [rbp+580h+var_520]
0x14008d0c3  mov     rax, [rax+58h]
  ... truncated ...
```
