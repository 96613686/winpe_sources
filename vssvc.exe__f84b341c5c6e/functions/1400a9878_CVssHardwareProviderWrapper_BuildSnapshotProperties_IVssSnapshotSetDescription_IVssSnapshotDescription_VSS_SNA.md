# CVssHardwareProviderWrapper::BuildSnapshotProperties(IVssSnapshotSetDescription *,IVssSnapshotDescription *,_VSS_SNAPSHOT_PROP *)

- ea: `0x1400a9878`
- end: `0x1400aa098`
- name: `?BuildSnapshotProperties@CVssHardwareProviderWrapper@@AEAAXPEAVIVssSnapshotSetDescription@@PEAVIVssSnapshotDescription@@PEAU_VSS_SNAPSHOT_PROP@@@Z`
- size: `2080`
- prototype: `void __fastcall(CVssHardwareProviderWrapper *__hidden this, struct IVssSnapshotSetDescription *, struct IVssSnapshotDescription *, struct _VSS_SNAPSHOT_PROP *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400aa568`
- `0x1400aa874`

## callees

- `0x1400137c0`
- `0x140013b00`
- `0x14001e700`
- `0x14003fc04`
- `0x140091560`
- `0x1400921dc`
- `0x1400921e8`
- `0x1400a9878`
- `0x1400f4010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400aa016`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa025`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa034`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa043`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa052`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa061`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa016`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa025`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa034`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa043`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa052`
- `OLEAUT32!__imp_SysFreeString` at `0x1400aa061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400a9f4a`

## string_xrefs

- `0x1400a9cea`: `IVssSnapshotDescription::GetServiceMachine`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CVssHardwareProviderWrapper::BuildSnapshotProperties(
        CVssHardwareProviderWrapper *this,
        struct IVssSnapshotSetDescription *a2,
        struct IVssSnapshotDescription *a3,
        struct _VSS_SNAPSHOT_PROP *a4)
{
  struct _VSS_SNAPSHOT_PROP *v4; // rsi
  unsigned __int16 *v7; // [rsp+40h] [rbp-228h] BYREF
  LONG v8; // [rsp+48h] [rbp-220h] BYREF
  LONG v9; // [rsp+4Ch] [rbp-21Ch] BYREF
  const unsigned __int16 *v10; // [rsp+50h] [rbp-218h] BYREF
  const unsigned __int16 *v11; // [rsp+58h] [rbp-210h]
  const unsigned __int16 *v12; // [rsp+60h] [rbp-208h]
  int v13; // [rsp+68h] [rbp-200h]
  int v14; // [rsp+6Ch] [rbp-1FCh]
  int v15; // [rsp+70h] [rbp-1F8h]
  _BYTE v16[120]; // [rsp+78h] [rbp-1F0h] BYREF
  int v17; // [rsp+F0h] [rbp-178h]
  struct _VSS_SNAPSHOT_PROP *v18; // [rsp+F8h] [rbp-170h]
  int pExceptionObject; // [rsp+100h] [rbp-168h] BYREF
  LPVOID pv; // [rsp+108h] [rbp-160h] BYREF
  unsigned __int16 *v21; // [rsp+110h] [rbp-158h] BYREF
  unsigned __int16 *v22; // [rsp+118h] [rbp-150h] BYREF
  unsigned __int16 *v23; // [rsp+120h] [rbp-148h] BYREF
  unsigned __int16 *v24; // [rsp+128h] [rbp-140h] BYREF
  BSTR bstrString; // [rsp+130h] [rbp-138h] BYREF
  BSTR v26; // [rsp+138h] [rbp-130h] BYREF
  BSTR v27; // [rsp+140h] [rbp-128h] BYREF
  BSTR v28; // [rsp+148h] [rbp-120h] BYREF
  BSTR v29; // [rsp+150h] [rbp-118h] BYREF
  BSTR v30; // [rsp+158h] [rbp-110h] BYREF
  VSS_TIMESTAMP v31[2]; // [rsp+160h] [rbp-108h] BYREF
  LPVOID v32; // [rsp+170h] [rbp-F8h] BYREF
  int v33; // [rsp+178h] [rbp-F0h]
  unsigned int v34; // [rsp+194h] [rbp-D4h]
  int v35; // [rsp+1E0h] [rbp-88h] BYREF
  struct _VSS_SNAPSHOT_PROP *v36; // [rsp+1E8h] [rbp-80h]
  _com_error *v37; // [rsp+1F0h] [rbp-78h] BYREF
  const std::exception *v38; // [rsp+1F8h] [rbp-70h] BYREF
  VSS_ID v39; // [rsp+200h] [rbp-68h] BYREF
  VSS_ID v40; // [rsp+210h] [rbp-58h] BYREF

  v4 = a4;
  v36 = a4;
  v18 = a4;
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1134;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v32, (__int64)&v10, 0);
  v8 = 0;
  v40 = 0;
  v39 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  bstrString = 0;
  v9 = 0;
  v31[0] = 0;
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotSetDescription *, VSS_ID *))(*(_QWORD *)a2 + 40LL))(a2, &v40);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1150;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotSetDescription::GetSnapshotSetId");
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, LONG *))(*(_QWORD *)a3 + 64LL))(a3, &v9);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1154;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotSetDescription::GetContext");
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotSetDescription *, LONG *))(*(_QWORD *)a2 + 96LL))(a2, &v8);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1158;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotSetDescription::GetSnapshotCount");
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, VSS_ID *))(*(_QWORD *)a3 + 24LL))(a3, &v39);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1162;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotDescription::GetSnapshotId");
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, VSS_TIMESTAMP *))(*(_QWORD *)a3 + 48LL))(a3, v31);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1166;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotDescription::GetTimestamp");
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, BSTR *, BSTR *))(*(_QWORD *)a3 + 80LL))(
          a3,
          &v29,
          &v30);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1170;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotDescription::GetOrigin");
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, BSTR *))(*(_QWORD *)a3 + 112LL))(a3, &v28);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1174;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotDescription::GetServiceMachine");
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, BSTR *))(*(_QWORD *)a3 + 128LL))(a3, &v27);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1178;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotDescription::GetDeviceName");
  v33 = (*(__int64 (__fastcall **)(struct IVssSnapshotDescription *, BSTR *, BSTR *))(*(_QWORD *)a3 + 144LL))(
          a3,
          &v26,
          &bstrString);
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx";
  v11 = L"CVssHardwareProviderWrapper::BuildSnapshotProperties";
  v12 = L"CORHWPWC";
  v13 = 1182;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CheckForErrorInternal(&v32, &v10, L"IVssSnapshotDescription::GetExposure");
  pv = 0;
  v22 = 0;
  v21 = 0;
  v23 = 0;
  v7 = 0;
  v24 = 0;
  try
  {
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v32, (unsigned __int16 **)&pv, v27);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v32, &v21, v30);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v32, &v22, v29);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v32, &v23, v28);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v32, &v24, v26);
    VssSafeDuplicateStr((struct CVssFunctionTracer *)&v32, &v7, bstrString);
  }
  catch ( long v35 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v32,
      v35,
      L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx",
      L"CORHWPWC",
      L"CVssHardwareProviderWrapper::BuildSnapshotProperties",
      0x4B0u,
      v34);
    v4 = v18;
  }
  catch ( _com_error *v37 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v32,
      v37,
      L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx",
      L"CORHWPWC",
      L"CVssHardwareProviderWrapper::BuildSnapshotProperties",
      0x4B0u,
      v34);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v32,
      L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx",
      L"CORHWPWC",
      L"CVssHardwareProviderWrapper::BuildSnapshotProperties",
      0x4B0u,
      v34);
    v4 = v18;
  }
  catch ( const std::exception *v38 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v32,
      v38,
      L"base\\stor\\vss\\modules\\coord\\src\\hardwrp.cxx",
      L"CORHWPWC",
      L"CVssHardwareProviderWrapper::BuildSnapshotProperties",
      0x4B0u,
      v34);
  }
  if ( v33 < 0 )
  {
    CoTaskMemFree(pv);
    CoTaskMemFree(v22);
    CoTaskMemFree(v21);
    CoTaskMemFree(v23);
    CoTaskMemFree(v24);
    CoTaskMemFree(v7);
    pExceptionObject = v33;
    throw (long *)&pExceptionObject;
  }
  v36->m_SnapshotId = v39;
  v4->m_SnapshotSetId = v40;
  v4->m_ProviderId = *(VSS_ID *)((char *)this + 404);
  v4->m_lSnapshotsCount = v8;
  v4->m_lSnapshotAttributes = v9;
  v4->m_eStatus = VSS_SS_CREATED;
  v4->m_pwszSnapshotDeviceObject = (VSS_PWSZ)pv;
  v4->m_pwszOriginalVolumeName = v21;
  v4->m_pwszOriginatingMachine = v22;
  v4->m_pwszServiceMachine = v23;
  v4->m_pwszExposedName = v24;
  v4->m_pwszExposedPath = v7;
  v4->m_tsCreationTimestamp = v31[0];
  SysFreeString(bstrString);
  SysFreeString(v26);
  SysFreeString(v27);
  SysFreeString(v28);
  SysFreeString(v29);
  SysFreeString(v30);
  CVssFunctionTracer::~CVssFunctionTracer(&v32);
}

```

## disassembly

```asm
0x1400a9878  mov     [rsp+arg_0], rcx
0x1400a987d  push    rbx
0x1400a987e  push    rsi
0x1400a987f  push    rdi
0x1400a9880  push    r12
0x1400a9882  push    r13
0x1400a9884  push    r14
0x1400a9886  push    r15
0x1400a9888  sub     rsp, 230h
0x1400a988f  mov     rax, cs:__security_cookie
0x1400a9896  xor     rax, rsp
0x1400a9899  mov     [rsp+268h+var_48], rax
0x1400a98a1  mov     rsi, r9
0x1400a98a4  mov     rdi, r8
0x1400a98a7  mov     rbx, rdx
0x1400a98aa  mov     [rsp+268h+var_80], r9
0x1400a98b2  mov     [rsp+268h+var_170], r9
0x1400a98ba  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a98c1  mov     [rsp+268h+var_218], rax
0x1400a98c6  lea     rax, aCvsshardwarepr_71; "CVssHardwareProviderWrapper::BuildSnaps"...
0x1400a98cd  mov     [rsp+268h+var_210], rax
0x1400a98d2  lea     r13, aCorhwpwc; "CORHWPWC"
0x1400a98d9  mov     [rsp+268h+var_208], r13
0x1400a98de  mov     [rsp+268h+var_200], 46Eh
0x1400a98e6  mov     [rsp+268h+var_1FC], 1
0x1400a98ee  mov     r12d, 0FFh
0x1400a98f4  mov     [rsp+268h+var_1F8], r12d
0x1400a98f9  xor     r14d, r14d
0x1400a98fc  mov     [rsp+268h+var_178], 1000000h
0x1400a9907  lea     r15d, [r14+78h]
0x1400a990b  mov     r8d, r15d; Size
0x1400a990e  xor     edx, edx; Val
0x1400a9910  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9915  call    memset_0
0x1400a991a  xor     r8d, r8d
0x1400a991d  lea     rdx, [rsp+268h+var_218]
0x1400a9922  lea     rcx, [rsp+268h+var_F8]
0x1400a992a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400a992f  nop
0x1400a9930  mov     [rsp+268h+var_220], r14d
0x1400a9935  xorps   xmm0, xmm0
0x1400a9938  movups  [rsp+268h+var_58], xmm0
0x1400a9940  xorps   xmm1, xmm1
0x1400a9943  movups  [rsp+268h+var_68], xmm1
0x1400a994b  mov     [rsp+268h+var_110], r14
0x1400a9953  mov     [rsp+268h+var_118], r14
0x1400a995b  mov     [rsp+268h+var_120], r14
0x1400a9963  mov     [rsp+268h+var_128], r14
0x1400a996b  mov     [rsp+268h+var_130], r14
0x1400a9973  mov     [rsp+268h+bstrString], r14
0x1400a997b  mov     [rsp+268h+var_21C], r14d
0x1400a9980  mov     [rsp+268h+var_108], r14
0x1400a9988  mov     rax, [rbx]
0x1400a998b  lea     rdx, [rsp+268h+var_58]
0x1400a9993  mov     rcx, rbx
0x1400a9996  mov     rax, [rax+28h]
0x1400a999a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a999f  mov     [rsp+268h+var_F0], eax
0x1400a99a6  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a99ad  mov     [rsp+268h+var_218], rax
0x1400a99b2  lea     rax, aCvsshardwarepr_71; "CVssHardwareProviderWrapper::BuildSnaps"...
0x1400a99b9  mov     [rsp+268h+var_210], rax
0x1400a99be  mov     [rsp+268h+var_208], r13
0x1400a99c3  mov     [rsp+268h+var_200], 47Eh
0x1400a99cb  mov     [rsp+268h+var_1FC], 1
0x1400a99d3  mov     [rsp+268h+var_1F8], r12d
0x1400a99d8  mov     [rsp+268h+var_178], 1000000h
0x1400a99e3  mov     r8d, r15d; Size
0x1400a99e6  xor     edx, edx; Val
0x1400a99e8  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a99ed  call    memset_0
0x1400a99f2  lea     r8, aIvsssnapshotse_9; "IVssSnapshotSetDescription::GetSnapshot"...
0x1400a99f9  lea     rdx, [rsp+268h+var_218]
0x1400a99fe  lea     rcx, [rsp+268h+var_F8]
0x1400a9a06  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9a0b  mov     rax, [rdi]
0x1400a9a0e  lea     rdx, [rsp+268h+var_21C]
0x1400a9a13  mov     rcx, rdi
0x1400a9a16  mov     rax, [rax+40h]
0x1400a9a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9a1f  mov     [rsp+268h+var_F0], eax
0x1400a9a26  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a9a2d  mov     [rsp+268h+var_218], rax
0x1400a9a32  lea     rax, aCvsshardwarepr_71; "CVssHardwareProviderWrapper::BuildSnaps"...
0x1400a9a39  mov     [rsp+268h+var_210], rax
0x1400a9a3e  mov     [rsp+268h+var_208], r13
0x1400a9a43  mov     [rsp+268h+var_200], 482h
0x1400a9a4b  mov     [rsp+268h+var_1FC], 1
0x1400a9a53  mov     [rsp+268h+var_1F8], r12d
0x1400a9a58  mov     [rsp+268h+var_178], 1000000h
0x1400a9a63  mov     r8d, r15d; Size
0x1400a9a66  xor     edx, edx; Val
0x1400a9a68  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9a6d  call    memset_0
0x1400a9a72  lea     r8, aIvsssnapshotse_7; "IVssSnapshotSetDescription::GetContext"
0x1400a9a79  lea     rdx, [rsp+268h+var_218]
0x1400a9a7e  lea     rcx, [rsp+268h+var_F8]
0x1400a9a86  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9a8b  mov     rax, [rbx]
0x1400a9a8e  lea     rdx, [rsp+268h+var_220]
0x1400a9a93  mov     rcx, rbx
0x1400a9a96  mov     rax, [rax+60h]
0x1400a9a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9a9f  mov     [rsp+268h+var_F0], eax
0x1400a9aa6  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a9aad  mov     [rsp+268h+var_218], rax
0x1400a9ab2  lea     rbx, aCvsshardwarepr_71; "CVssHardwareProviderWrapper::BuildSnaps"...
0x1400a9ab9  mov     [rsp+268h+var_210], rbx
0x1400a9abe  mov     [rsp+268h+var_208], r13
0x1400a9ac3  mov     [rsp+268h+var_200], 486h
0x1400a9acb  mov     [rsp+268h+var_1FC], 1
0x1400a9ad3  mov     [rsp+268h+var_1F8], r12d
0x1400a9ad8  mov     [rsp+268h+var_178], 1000000h
0x1400a9ae3  mov     r8d, r15d; Size
0x1400a9ae6  xor     edx, edx; Val
0x1400a9ae8  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9aed  call    memset_0
0x1400a9af2  lea     r8, aIvsssnapshotse_8; "IVssSnapshotSetDescription::GetSnapshot"...
0x1400a9af9  lea     rdx, [rsp+268h+var_218]
0x1400a9afe  lea     rcx, [rsp+268h+var_F8]
0x1400a9b06  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9b0b  mov     rax, [rdi]
0x1400a9b0e  lea     rdx, [rsp+268h+var_68]
0x1400a9b16  mov     rcx, rdi
0x1400a9b19  mov     rax, [rax+18h]
0x1400a9b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9b22  mov     [rsp+268h+var_F0], eax
0x1400a9b29  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a9b30  mov     [rsp+268h+var_218], rax
0x1400a9b35  mov     [rsp+268h+var_210], rbx
0x1400a9b3a  mov     [rsp+268h+var_208], r13
0x1400a9b3f  mov     [rsp+268h+var_200], 48Ah
0x1400a9b47  mov     [rsp+268h+var_1FC], 1
0x1400a9b4f  mov     [rsp+268h+var_1F8], r12d
0x1400a9b54  mov     [rsp+268h+var_178], 1000000h
0x1400a9b5f  mov     r8d, r15d; Size
0x1400a9b62  xor     edx, edx; Val
0x1400a9b64  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9b69  call    memset_0
0x1400a9b6e  lea     r8, aIvsssnapshotde_17; "IVssSnapshotDescription::GetSnapshotId"
0x1400a9b75  lea     rdx, [rsp+268h+var_218]
0x1400a9b7a  lea     rcx, [rsp+268h+var_F8]
0x1400a9b82  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9b87  mov     rax, [rdi]
0x1400a9b8a  lea     rdx, [rsp+268h+var_108]
0x1400a9b92  mov     rcx, rdi
0x1400a9b95  mov     rax, [rax+30h]
0x1400a9b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9b9e  mov     [rsp+268h+var_F0], eax
0x1400a9ba5  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a9bac  mov     [rsp+268h+var_218], rax
0x1400a9bb1  mov     [rsp+268h+var_210], rbx
0x1400a9bb6  mov     [rsp+268h+var_208], r13
0x1400a9bbb  mov     [rsp+268h+var_200], 48Eh
0x1400a9bc3  mov     [rsp+268h+var_1FC], 1
0x1400a9bcb  mov     [rsp+268h+var_1F8], r12d
0x1400a9bd0  mov     [rsp+268h+var_178], 1000000h
0x1400a9bdb  mov     r8d, r15d; Size
0x1400a9bde  xor     edx, edx; Val
0x1400a9be0  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9be5  call    memset_0
0x1400a9bea  lea     r8, aIvsssnapshotde_9; "IVssSnapshotDescription::GetTimestamp"
0x1400a9bf1  lea     rdx, [rsp+268h+var_218]
0x1400a9bf6  lea     rcx, [rsp+268h+var_F8]
0x1400a9bfe  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9c03  mov     rax, [rdi]
0x1400a9c06  lea     r8, [rsp+268h+var_110]
0x1400a9c0e  lea     rdx, [rsp+268h+var_118]
0x1400a9c16  mov     rcx, rdi
0x1400a9c19  mov     rax, [rax+50h]
0x1400a9c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9c22  mov     [rsp+268h+var_F0], eax
0x1400a9c29  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a9c30  mov     [rsp+268h+var_218], rax
0x1400a9c35  mov     [rsp+268h+var_210], rbx
0x1400a9c3a  mov     [rsp+268h+var_208], r13
0x1400a9c3f  mov     [rsp+268h+var_200], 492h
0x1400a9c47  mov     [rsp+268h+var_1FC], 1
0x1400a9c4f  mov     [rsp+268h+var_1F8], r12d
0x1400a9c54  mov     [rsp+268h+var_178], 1000000h
0x1400a9c5f  mov     r8d, r15d; Size
0x1400a9c62  xor     edx, edx; Val
0x1400a9c64  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9c69  call    memset_0
0x1400a9c6e  lea     r8, aIvsssnapshotde_18; "IVssSnapshotDescription::GetOrigin"
0x1400a9c75  lea     rdx, [rsp+268h+var_218]
0x1400a9c7a  lea     rcx, [rsp+268h+var_F8]
0x1400a9c82  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9c87  mov     rax, [rdi]
0x1400a9c8a  lea     rdx, [rsp+268h+var_120]
0x1400a9c92  mov     rcx, rdi
0x1400a9c95  mov     rax, [rax+70h]
0x1400a9c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9c9e  mov     [rsp+268h+var_F0], eax
0x1400a9ca5  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a9cac  mov     [rsp+268h+var_218], rax
0x1400a9cb1  mov     [rsp+268h+var_210], rbx
0x1400a9cb6  mov     [rsp+268h+var_208], r13
0x1400a9cbb  mov     [rsp+268h+var_200], 496h
0x1400a9cc3  mov     [rsp+268h+var_1FC], 1
0x1400a9ccb  mov     [rsp+268h+var_1F8], r12d
0x1400a9cd0  mov     [rsp+268h+var_178], 1000000h
0x1400a9cdb  mov     r8d, r15d; Size
0x1400a9cde  xor     edx, edx; Val
0x1400a9ce0  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9ce5  call    memset_0
0x1400a9cea  lea     r8, aIvsssnapshotde_2; "IVssSnapshotDescription::GetServiceMach"...
0x1400a9cf1  lea     rdx, [rsp+268h+var_218]
0x1400a9cf6  lea     rcx, [rsp+268h+var_F8]
0x1400a9cfe  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9d03  mov     rax, [rdi]
0x1400a9d06  lea     rdx, [rsp+268h+var_128]
0x1400a9d0e  mov     rcx, rdi
0x1400a9d11  mov     rax, [rax+80h]
0x1400a9d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9d1d  mov     [rsp+268h+var_F0], eax
0x1400a9d24  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a9d2b  mov     [rsp+268h+var_218], rax
0x1400a9d30  mov     [rsp+268h+var_210], rbx
0x1400a9d35  mov     [rsp+268h+var_208], r13
0x1400a9d3a  mov     [rsp+268h+var_200], 49Ah
0x1400a9d42  mov     [rsp+268h+var_1FC], 1
0x1400a9d4a  mov     [rsp+268h+var_1F8], r12d
0x1400a9d4f  mov     [rsp+268h+var_178], 1000000h
0x1400a9d5a  mov     r8d, r15d; Size
0x1400a9d5d  xor     edx, edx; Val
0x1400a9d5f  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9d64  call    memset_0
0x1400a9d69  lea     r8, aIvsssnapshotde_10; "IVssSnapshotDescription::GetDeviceName"
0x1400a9d70  lea     rdx, [rsp+268h+var_218]
0x1400a9d75  lea     rcx, [rsp+268h+var_F8]
0x1400a9d7d  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9d82  mov     rax, [rdi]
0x1400a9d85  lea     r8, [rsp+268h+bstrString]
0x1400a9d8d  lea     rdx, [rsp+268h+var_130]
0x1400a9d95  mov     rcx, rdi
0x1400a9d98  mov     rax, [rax+90h]
0x1400a9d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a9da4  mov     [rsp+268h+var_F0], eax
0x1400a9dab  lea     rax, aBaseStorVssMod_19; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400a9db2  mov     [rsp+268h+var_218], rax
0x1400a9db7  mov     [rsp+268h+var_210], rbx
0x1400a9dbc  mov     [rsp+268h+var_208], r13
0x1400a9dc1  mov     [rsp+268h+var_200], 49Eh
0x1400a9dc9  mov     [rsp+268h+var_1FC], 1
0x1400a9dd1  mov     [rsp+268h+var_1F8], r12d
0x1400a9dd6  mov     [rsp+268h+var_178], 1000000h
0x1400a9de1  mov     r8d, r15d; Size
0x1400a9de4  xor     edx, edx; Val
0x1400a9de6  lea     rcx, [rsp+268h+var_1F0]; void *
0x1400a9deb  call    memset_0
0x1400a9df0  lea     r8, aIvsssnapshotde_3; "IVssSnapshotDescription::GetExposure"
0x1400a9df7  lea     rdx, [rsp+268h+var_218]
0x1400a9dfc  lea     rcx, [rsp+268h+var_F8]
0x1400a9e04  call    ?CheckForErrorInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBG@Z; CVssFunctionTracer::CheckForErrorInternal(CVssDebugInfo,ushort const *)
0x1400a9e09  mov     [rsp+268h+pv], r14
0x1400a9e11  mov     [rsp+268h+var_150], r14
0x1400a9e19  mov     [rsp+268h+var_158], r14
0x1400a9e21  mov     [rsp+268h+var_148], r14
0x1400a9e29  mov     [rsp+268h+var_228], r14
0x1400a9e2e  mov     [rsp+268h+var_140], r14
0x1400a9e36  mov     r8, [rsp+268h+var_128]; unsigned __int16 *
0x1400a9e3e  lea     rdx, [rsp+268h+pv]; unsigned __int16 **
0x1400a9e46  lea     rcx, [rsp+268h+var_F8]; struct CVssFunctionTracer *
0x1400a9e4e  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x1400a9e53  mov     r8, [rsp+268h+var_110]; unsigned __int16 *
0x1400a9e5b  lea     rdx, [rsp+268h+var_158]; unsigned __int16 **
0x1400a9e63  lea     rcx, [rsp+268h+var_F8]; struct CVssFunctionTracer *
0x1400a9e6b  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x1400a9e70  mov     r8, [rsp+268h+var_118]; unsigned __int16 *
0x1400a9e78  lea     rdx, [rsp+268h+var_150]; unsigned __int16 **
0x1400a9e80  lea     rcx, [rsp+268h+var_F8]; struct CVssFunctionTracer *
0x1400a9e88  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x1400a9e8d  mov     r8, [rsp+268h+var_120]; unsigned __int16 *
0x1400a9e95  lea     rdx, [rsp+268h+var_148]; unsigned __int16 **
0x1400a9e9d  lea     rcx, [rsp+268h+var_F8]; struct CVssFunctionTracer *
0x1400a9ea5  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x1400a9eaa  mov     r8, [rsp+268h+var_130]; unsigned __int16 *
0x1400a9eb2  lea     rdx, [rsp+268h+var_140]; unsigned __int16 **
0x1400a9eba  lea     rcx, [rsp+268h+var_F8]; struct CVssFunctionTracer *
0x1400a9ec2  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x1400a9ec7  mov     r8, [rsp+268h+bstrString]; unsigned __int16 *
0x1400a9ecf  lea     rdx, [rsp+268h+var_228]; unsigned __int16 **
0x1400a9ed4  lea     rcx, [rsp+268h+var_F8]; struct CVssFunctionTracer *
0x1400a9edc  call    ?VssSafeDuplicateStr@@YAXAEAVCVssFunctionTracer@@AEAPEAGPEBG@Z; VssSafeDuplicateStr(CVssFunctionTracer &,ushort * &,ushort const *)
0x1400a9ee1  nop
0x1400a9ee2  jmp     short loc_1400A9EF5
0x1400a9ee4  jmp     short loc_1400A9EEA
0x1400a9ee6  jmp     short loc_1400A9EEA
0x1400a9ee8  jmp     short $+2
0x1400a9eea  mov     rsi, [rsp+268h+var_170]
0x1400a9ef2  xor     r14d, r14d
0x1400a9ef5  cmp     [rsp+268h+var_F0], r14d
0x1400a9efd  jge     short loc_1400A9F73
0x1400a9eff  mov     rcx, [rsp+268h+pv]; pv
0x1400a9f07  call    cs:__imp_CoTaskMemFree
0x1400a9f0d  mov     rcx, [rsp+268h+var_150]; pv
0x1400a9f15  call    cs:__imp_CoTaskMemFree
0x1400a9f1b  mov     rcx, [rsp+268h+var_158]; pv
0x1400a9f23  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
