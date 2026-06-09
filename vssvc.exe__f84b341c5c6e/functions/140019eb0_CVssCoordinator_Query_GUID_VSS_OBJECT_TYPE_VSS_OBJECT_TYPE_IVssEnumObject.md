# CVssCoordinator::Query(_GUID,_VSS_OBJECT_TYPE,_VSS_OBJECT_TYPE,IVssEnumObject * *)

- ea: `0x140019eb0`
- end: `0x14001b7fd`
- name: `?Query@CVssCoordinator@@UEAAJU_GUID@@W4_VSS_OBJECT_TYPE@@1PEAPEAUIVssEnumObject@@@Z`
- size: `6477`
- prototype: `int(CVssCoordinator *__hidden this, struct _GUID *__struct_ptr, enum _VSS_OBJECT_TYPE, enum _VSS_OBJECT_TYPE, struct IVssEnumObject **)`
- caller_count: `0`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1400088fc`
- `0x140008a3c`
- `0x1400137c0`
- `0x1400138e0`
- `0x1400139c0`
- `0x140013c60`
- `0x140013d30`
- `0x140015e38`
- `0x140016db0`
- `0x14001940c`
- `0x140019990`
- `0x140019bf0`
- `0x140019e30`
- `0x140019eb0`
- `0x14001b804`
- `0x14001b9c0`
- `0x14001c878`
- `0x14001ca34`
- `0x14001cafc`
- `0x14003a930`
- `0x14003c160`
- `0x140040944`
- `0x140042acc`
- `0x1400433b8`
- `0x140043a6c`
- `0x140043b1c`
- `0x140049ec4`
- `0x14004ee3c`
- `0x1400562c8`
- `0x140069108`
- `0x14006c8c4`
- `0x14006c8f4`
- `0x140070fcc`
- `0x140091560`
- `0x14009197c`
- `0x1400921dc`
- `0x140099808`
- `0x14009dbe8`
- `0x14009ddc0`
- `0x1400cdfa4`
- `0x1400da308`
- `0x1400da314`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140019fc1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001a61c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001a809`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001a97f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001ae4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140019fc1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001a61c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001a809`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001a97f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001ae4c`
- `VssTrace!__imp_VssTraceMessage` at `0x14001b2de`
- `VssTrace!__imp_VssTraceMessage` at `0x14001b63d`
- `VssTrace!__imp_VssTraceMessage` at `0x14001b726`
- `VssTrace!__imp_VssTraceMessage` at `0x14001b2de`
- `VssTrace!__imp_VssTraceMessage` at `0x14001b63d`
- `VssTrace!__imp_VssTraceMessage` at `0x14001b726`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001a8da`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001aa57`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001ac40`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001ac6b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001b01d`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001a8da`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001aa57`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001ac40`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001ac6b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001b01d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001a01f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001a67a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001aeaa`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001a01f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001a67a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001aeaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a7b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a7cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a7e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a7fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a92f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a95b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aa8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aa9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001afd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b04b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a7b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a7cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a7e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a7fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a92f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a95b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001a971`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aa8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aa9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001aac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001afd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14001b04b`

## string_xrefs

- `0x14001b5cd`: `Cannot create enumerator instance. [0x%08lx]`
- `0x14001b74b`: `Cannot create enumerator instance. [0x%08lx]`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall CVssCoordinator::Query(
        PSECURITY_DESCRIPTOR *this,
        struct _GUID *a2,
        enum _VSS_OBJECT_TYPE a3,
        enum _VSS_OBJECT_TYPE a4,
        struct IVssEnumObject **a5)
{
  __int64 v9; // rax
  unsigned int v10; // ebx
  __int64 i; // rbx
  void *v12; // rcx
  bool IsClientValidRequestor; // al
  const unsigned __int16 **v14; // rdi
  __int64 v15; // rcx
  struct _GUID *p_Buf1; // rbx
  __int64 j; // rbx
  void *v18; // rcx
  CVssCoordinator *v19; // rbx
  struct VSS_OBJECT_PROP_Array *v20; // rax
  struct VSS_OBJECT_PROP_Array *v21; // r13
  int v22; // r12d
  CVssCoordinator *v23; // rax
  unsigned int v24; // ebx
  __int64 m; // rbx
  void *v26; // rcx
  CVssCoordinator *v27; // rbx
  int v28; // ebx
  BOOL v29; // esi
  DWORD v30; // edi
  unsigned int v31; // r8d
  __int64 n; // rbx
  void *v33; // rcx
  unsigned int v34; // r15d
  DWORD v35; // r14d
  unsigned int v36; // r8d
  unsigned int v38; // esi
  __int64 v39; // r12
  int v40; // edi
  struct _GUID v41; // xmm6
  __int64 v42; // r15
  CVssCoordinator *v43; // rax
  unsigned int v44; // ebx
  __int64 k; // rbx
  void *v46; // rcx
  struct _VSS_OBJECT_PROP *v47; // rbx
  int v48; // edi
  unsigned int v49; // ebx
  int v50; // eax
  int v51; // ebx
  CVssDebugInfo *v52; // rax
  int v53; // r9d
  CVssDebugInfo *v54; // rax
  int v55; // r9d
  __int64 v56; // [rsp+20h] [rbp-3B8h]
  __int64 v57; // [rsp+20h] [rbp-3B8h]
  __int64 v58; // [rsp+20h] [rbp-3B8h]
  __int64 v59; // [rsp+28h] [rbp-3B0h]
  __int64 v60; // [rsp+28h] [rbp-3B0h]
  __int64 v61; // [rsp+28h] [rbp-3B0h]
  __int64 v62; // [rsp+30h] [rbp-3A8h]
  __int64 v63; // [rsp+30h] [rbp-3A8h]
  __int64 v64; // [rsp+30h] [rbp-3A8h]
  __int64 v65; // [rsp+38h] [rbp-3A0h]
  __int64 v66; // [rsp+38h] [rbp-3A0h]
  __int64 v67; // [rsp+38h] [rbp-3A0h]
  __int64 v68; // [rsp+40h] [rbp-398h]
  __int64 v69; // [rsp+40h] [rbp-398h]
  __int64 v70; // [rsp+40h] [rbp-398h]
  __int64 v71; // [rsp+48h] [rbp-390h]
  __int64 v72; // [rsp+48h] [rbp-390h]
  __int64 v73; // [rsp+50h] [rbp-388h]
  __int64 v74; // [rsp+58h] [rbp-380h]
  __int64 v75; // [rsp+60h] [rbp-378h]
  __int64 v76; // [rsp+68h] [rbp-370h]
  __int64 v77; // [rsp+70h] [rbp-368h]
  const unsigned __int16 **v78; // [rsp+90h] [rbp-348h] BYREF
  __int64 v79; // [rsp+98h] [rbp-340h] BYREF
  CVssCoordinator *v80[2]; // [rsp+A0h] [rbp-338h] BYREF
  const wchar_t *v81; // [rsp+B0h] [rbp-328h] BYREF
  const wchar_t *v82; // [rsp+B8h] [rbp-320h]
  const wchar_t *v83; // [rsp+C0h] [rbp-318h]
  int v84; // [rsp+C8h] [rbp-310h]
  unsigned int v85; // [rsp+CCh] [rbp-30Ch]
  unsigned int v86; // [rsp+D0h] [rbp-308h]
  LPVOID v87[15]; // [rsp+D8h] [rbp-300h] BYREF
  int v88; // [rsp+150h] [rbp-288h]
  unsigned __int64 v89; // [rsp+160h] [rbp-278h] BYREF
  int Instance; // [rsp+168h] [rbp-270h]
  const unsigned __int16 *v91; // [rsp+170h] [rbp-268h]
  const unsigned __int16 *v92; // [rsp+178h] [rbp-260h]
  unsigned int v93; // [rsp+180h] [rbp-258h]
  unsigned int v94; // [rsp+184h] [rbp-254h]
  const wchar_t *v95; // [rsp+188h] [rbp-250h]
  unsigned int v96; // [rsp+190h] [rbp-248h]
  DWORD v97; // [rsp+194h] [rbp-244h]
  unsigned int v98; // [rsp+198h] [rbp-240h]
  LPVOID pv[2]; // [rsp+1A0h] [rbp-238h]
  LPVOID v100[2]; // [rsp+1B0h] [rbp-228h]
  CVssCoordinator *v101; // [rsp+1C0h] [rbp-218h]
  int v102; // [rsp+1D0h] [rbp-208h] BYREF
  const unsigned __int16 **v103; // [rsp+1D8h] [rbp-200h]
  _DWORD v104[2]; // [rsp+1E0h] [rbp-1F8h] BYREF
  int v105; // [rsp+1E8h] [rbp-1F0h]
  const unsigned __int16 *v106; // [rsp+1F0h] [rbp-1E8h]
  const unsigned __int16 *v107; // [rsp+1F8h] [rbp-1E0h]
  unsigned int v108; // [rsp+200h] [rbp-1D8h]
  unsigned int v109; // [rsp+204h] [rbp-1D4h]
  const unsigned __int16 *v110; // [rsp+208h] [rbp-1D0h]
  unsigned int v111; // [rsp+210h] [rbp-1C8h]
  DWORD TickCount; // [rsp+214h] [rbp-1C4h]
  unsigned int v113; // [rsp+218h] [rbp-1C0h]
  LPVOID v114[2]; // [rsp+220h] [rbp-1B8h]
  LPVOID v115[2]; // [rsp+230h] [rbp-1A8h]
  __int64 v116; // [rsp+240h] [rbp-198h]
  const unsigned __int16 *v117; // [rsp+250h] [rbp-188h] BYREF
  const wchar_t *v118; // [rsp+258h] [rbp-180h]
  const unsigned __int16 *v119; // [rsp+260h] [rbp-178h]
  int v120; // [rsp+268h] [rbp-170h]
  unsigned int v121; // [rsp+26Ch] [rbp-16Ch]
  unsigned int v122; // [rsp+270h] [rbp-168h]
  _QWORD Src[15]; // [rsp+278h] [rbp-160h] BYREF
  int v124; // [rsp+2F0h] [rbp-E8h]
  struct _VSS_OBJECT_PROP *v125[2]; // [rsp+300h] [rbp-D8h] BYREF
  _QWORD v126[4]; // [rsp+310h] [rbp-C8h] BYREF
  _BYTE v127[48]; // [rsp+330h] [rbp-A8h] BYREF
  struct _GUID Buf1; // [rsp+360h] [rbp-78h] BYREF
  __m128i si128; // [rsp+370h] [rbp-68h]

  v80[0] = (CVssCoordinator *)this;
  v103 = (const unsigned __int16 **)a5;
  v117 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
  v118 = L"CVssCoordinator::Query";
  v119 = L"CORQRYC";
  v120 = 181;
  v121 = 1;
  v122 = 255;
  v124 = 0x1000000;
  memset_0(Src, 0, sizeof(Src));
  v105 = 0;
  v110 = L"CVssCoordinator::Query";
  v106 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
  v107 = L"CORQRYC";
  v108 = 181;
  v109 = 1;
  TickCount = GetTickCount();
  v104[1] = -1;
  v113 = 255;
  v104[0] = 0;
  v116 = 0;
  *(_OWORD *)v114 = 0;
  *(_OWORD *)v115 = 0;
  v79 = 0;
  if ( (int)VssGetTracingContextPerThread(&v79) < 0 || (int)VssSetTracingContextPerThread(v104) < 0 )
  {
    v9 = v116;
  }
  else
  {
    v9 = v79;
    v116 = v79;
  }
  if ( v9 )
    v111 = *(_DWORD *)(v9 + 48) + 1;
  else
    v111 = 0;
  v10 = 160;
  if ( v113 != 255 )
    v10 = v113;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v104, v109) )
    VssTraceMessage(v106, v107, v108, v111, v109, v110, L"ENTER", v10, 0);
  if ( HIBYTE(v124) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v12 = (void *)Src[i];
      if ( v12 )
      {
        CoTaskMemFree(v12);
        Src[i] = 0;
      }
    }
  }
  if ( a5 )
    *a5 = 0;
  IsClientValidRequestor = CVssSidCollection::IsClientValidRequestor(this + 23);
  v85 = 1;
  v86 = 255;
  v88 = 0x1000000;
  v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
  v82 = L"CVssCoordinator::Query";
  v83 = L"CORQRYC";
  if ( !IsClientValidRequestor )
  {
    v84 = 190;
    memset_0(v87, 0, sizeof(v87));
    CVssFunctionTracer::Throw(
      v104,
      &v81,
      2147942405LL,
      L"The  client process is not running under a valid user account for requestor");
  }
  v84 = 194;
  memset_0(v87, 0, sizeof(v87));
  LODWORD(v68) = a2->Data4[2];
  LODWORD(v65) = a2->Data4[1];
  LODWORD(v62) = a2->Data4[0];
  LODWORD(v59) = a2->Data3;
  LODWORD(v56) = a2->Data2;
  CVssFunctionTracer::Trace(
    v104,
    &v81,
    L"Parameters: QueriedObjectId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, eQueriedObjectType = %d, eReturned"
     "ObjectsType = %d, ppEnum = %p",
    a2->Data1,
    v56,
    v59,
    v62,
    v65,
    v68,
    a2->Data4[3],
    a2->Data4[4],
    a2->Data4[5],
    a2->Data4[6],
    a2->Data4[7],
    a3,
    a4,
    v103);
  if ( memcmp_0(a2, &GUID_NULL, 0x10u) )
  {
    v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
    v82 = L"CVssCoordinator::Query";
    v83 = L"CORQRYC";
    v84 = 206;
    v85 = 1;
    v86 = 255;
    v88 = 0x1000000;
    memset_0(v87, 0, sizeof(v87));
    CVssFunctionTracer::Throw(v104, &v81, 2147942487LL, L"Invalid QueriedObjectId");
  }
  if ( a3 != VSS_OBJECT_NONE )
  {
    v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
    v82 = L"CVssCoordinator::Query";
    v83 = L"CORQRYC";
    v84 = 208;
    v85 = 1;
    v86 = 255;
    v88 = 0x1000000;
    memset_0(v87, 0, sizeof(v87));
    CVssFunctionTracer::Throw(v104, &v81, 2147942487LL, L"Invalid eQueriedObjectType");
  }
  if ( a4 != VSS_OBJECT_SNAPSHOT && a4 != VSS_OBJECT_PROVIDER )
  {
    v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
    v82 = L"CVssCoordinator::Query";
    v83 = L"CORQRYC";
    v84 = 211;
    v85 = 1;
    v86 = 255;
    v88 = 0x1000000;
    memset_0(v87, 0, sizeof(v87));
    CVssFunctionTracer::Throw(v104, &v81, 2147942487LL, L"Invalid eReturnedObjectsType");
  }
  v14 = v103;
  v86 = 255;
  v88 = 0x1000000;
  if ( !v103 )
  {
    v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
    v82 = L"CVssCoordinator::Query";
    v83 = L"CORQRYC";
    v84 = 214;
    v85 = 1;
    memset_0(v87, 0, sizeof(v87));
    CVssFunctionTracer::Throw(v104, &v81, 2147942487LL, L"NULL ppEnum");
  }
  v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
  v82 = L"CVssCoordinator::Query";
  v83 = L"CORQRYC";
  v84 = 216;
  v85 = 13;
  memset_0(v87, 0, sizeof(v87));
  CVssFunctionTracer::AddOperation((__int64)v104, (__int64)&v81, 0x132u);
  v117 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
  v118 = L"CVssCoordinator::Query";
  v119 = L"CORQRYC";
  v120 = 217;
  v121 = 13;
  v122 = 255;
  v124 = 0x1000000;
  memset_0(Src, 0, sizeof(Src));
  v78 = &v117;
  CVssResource::LoadStringW(v15, &Buf1, 5012);
  if ( si128.m128i_i64[1] > 7uLL )
    p_Buf1 = *(struct _GUID **)&Buf1.Data1;
  else
    p_Buf1 = &Buf1;
  v81 = v117;
  v83 = v119;
  v82 = v118;
  v84 = v120;
  v85 = v121;
  v88 = v124;
  v86 = v122;
  HIBYTE(v124) = 0;
  memcpy_0(v87, Src, sizeof(v87));
  CVssFunctionTracer::AddContextInternal((__int64)v104, (__int64)&v81, 2, (__int64)p_Buf1, L"Coordinator");
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(*(_QWORD *)&Buf1.Data1, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Buf1.Data1) = 0;
  if ( HIBYTE(v124) )
  {
    for ( j = 0; j != 15; ++j )
    {
      v18 = (void *)Src[j];
      if ( v18 )
      {
        CoTaskMemFree(v18);
        Src[j] = 0;
      }
    }
  }
  v19 = v80[0];
  CVssCoordinator::FreezeContext(v80[0]);
  v20 = (struct VSS_OBJECT_PROP_Array *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v20;
  v78 = (const unsigned __int16 **)v20;
  if ( v20 )
  {
    ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>((char *)v20 + 8);
    *((_DWORD *)v21 + 6) = 0;
    *(_QWORD *)v21 = &VSS_OBJECT_PROP_Array::`vftable';
  }
  else
  {
    v21 = 0;
  }
  if ( !v21 )
  {
    v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
    v82 = L"CVssCoordinator::Query";
    v83 = L"CORQRYC";
    v84 = 225;
    v85 = 1;
    v86 = 255;
    v88 = 0x1000000;
    memset_0(v87, 0, sizeof(v87));
    CVssFunctionTracer::Throw(v104, &v81, 2147942414LL, L"Memory allocation error.");
  }
  ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v78, (__int64)v21);
  v22 = a4 - 3;
  if ( v22 )
  {
    if ( v22 != 1 )
    {
      v51 = v105;
      v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
      v82 = L"CVssCoordinator::Query";
      v83 = L"CORQRYC";
      v84 = 308;
      v85 = 1;
      v86 = 255;
      v88 = 0x1000000;
      memset_0(v87, 0, sizeof(v87));
      LODWORD(v57) = v51;
      CVssFunctionTracer::Throw(v104, &v81, 2147942487LL, L"Cannot create enumerator instance. [0x%08lx]", v57);
    }
    CVssProviderManager::QuerySupportedProvidersIntoArray(*((_DWORD *)v19 + 38), 1, 0, v21);
  }
  else
  {
    v79 = 0;
    CVssProviderManager::GetProviderItfArray(*((unsigned int *)v19 + 38), &v79);
    CVssSnasphotSetIdObserver::CVssSnasphotSetIdObserver((CVssSnasphotSetIdObserver *)v127);
    CVssSnasphotSetIdObserver::StartRecording((CVssSnasphotSetIdObserver *)v127);
    v38 = 0;
    v39 = v79;
    while ( v38 < *(_DWORD *)(v39 + 16) )
    {
      ATL::CComPtr<IVssSnapshotProvider>::CComPtr<IVssSnapshotProvider>(
        &v79,
        (__int64 *)(*(_QWORD *)(v39 + 8) + 8LL * (int)v38));
      if ( ATL::CComPtrBase<IXMLDOMNode>::operator==(&v79, 0) )
      {
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v79);
        ++v38;
      }
      else
      {
        ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(v126);
        *(GUID *)v125 = GUID_NULL;
        v40 = (*(__int64 (__fastcall **)(__int64, struct _VSS_OBJECT_PROP **, __int64, __int64, _QWORD *))(*(_QWORD *)v79 + 48LL))(
                v79,
                v125,
                1,
                3,
                v126);
        v105 = v40;
        v41 = *(struct _GUID *)(*(_QWORD *)v39 + 16LL * (int)v38);
        if ( v40 < 0 )
        {
          v81 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
          v82 = L"CVssCoordinator::Query";
          v83 = L"CORQRYC";
          v84 = 268;
          v85 = 1;
          v86 = 255;
          v88 = 0x1000000;
          memset_0(v87, 0, sizeof(v87));
          *(struct _GUID *)v80 = v41;
          LODWORD(v57) = v40;
          CVssFunctionTracer::TranslateProviderError(v104, &v81, v80, L"Error calling Query(). [0x%08lx]", v57);
        }
        v42 = v126[0];
        Buf1 = *(struct _GUID *)(*(_QWORD *)v39 + 16LL * (int)v38);
        v117 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
        v118 = L"CVssProviderManager::TransferEnumeratorContentsToArray";
        v119 = L"CORPRVMC";
        v120 = 144;
        v121 = 1;
        v122 = 255;
        v124 = 0x1000000;
        memset_0(Src, 0, sizeof(Src));
        Instance = 0;
        v95 = v118;
        v91 = v117;
        v92 = v119;
        v93 = v120;
        v94 = v121;
        v97 = GetTickCount();
        v98 = v122;
        v89 = 0xFFFFFFFF00000000uLL;
        v101 = 0;
        *(_OWORD *)pv = 0;
        *(_OWORD *)v100 = 0;
        v80[0] = 0;
        if ( (int)VssGetTracingContextPerThread(v80) < 0 || (int)VssSetTracingContextPerThread(&v89) < 0 )
        {
          v43 = v101;
        }
        else
        {
          v43 = v80[0];
          v101 = v80[0];
        }
        if ( v43 )
          v96 = *((_DWORD *)v43 + 12) + 1;
        else
          v96 = 0;
        v44 = 160;
        if ( v98 != 255 )
          v44 = v98;
        if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v89, v94) )
          VssTraceMessage(v91, v92, v93, v96, v94, v95, L"ENTER", v44, 0);
        if ( HIBYTE(v124) )
        {
          for ( k = 0; k != 15; ++k )
          {
            v46 = (void *)Src[k];
            if ( v46 )
            {
              CoTaskMemFree(v46);
              Src[k] = 0;
            }
          }
        }
        v102 = 0;
        for ( v125[0] = 0; ; v125[0] = 0 )
        {
          VSS_OBJECT_PROP_Ptr::InitializeAsEmpty((VSS_OBJECT_PROP_Ptr *)v125, (struct CVssFunctionTracer *)&v89);
          v47 = v125[0];
          v48 = (*(__int64 (__fastcall **)(__int64, __int64, struct _VSS_OBJECT_PROP *, int *))(*(_QWORD *)v42 + 24LL))(
                  v42,
                  1,
                  v125[0],
                  &v102);
          Instance = v48;
          if ( v48 == 1 )
            break;
          if ( v48 < 0 )
          {
            v50 = memcmp_0(&Buf1, &GUID_NULL, 0x10u);
            v85 = 1;
            v86 = 255;
            v88 = 0x1000000;
            v81 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
            v82 = L"CVssProviderManager::TransferEnumeratorContentsToArray";
            v83 = L"CORPRVMC";
            if ( !v50 )
            {
              v84 = 175;
              memset_0(v87, 0, sizeof(v87));
              CVssFunctionTracer::TranslateError(&v89, &v81, (unsigned int)v48, L"IVssEnumObject::Next");
            }
            v84 = 173;
            memset_0(v87, 0, sizeof(v87));
            Buf1 = v41;
            CVssFunctionTracer::TranslateProviderError(&v89, &v81, &Buf1, L"IVssEnumObject::Next");
          }
          if ( !(unsigned int)ATL::CSimpleArray<_HRESOURCE *,ATL::CSimpleArrayEqualHelper<_HRESOURCE *>>::Add(
                                (char *)v21 + 8,
                                v125) )
          {
            v81 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
            v82 = L"CVssProviderManager::TransferEnumeratorContentsToArray";
            v83 = L"CORPRVMC";
            v84 = 182;
            v85 = 1;
            v86 = 255;
            v88 = 0x1000000;
            memset_0(v87, 0, sizeof(v87));
            CVssFunctionTracer::Throw(&v89, &v81, 2147942414LL, L"Cannot add element to the array");
          }
        }
        if ( v47 )
        {
          VSS_OBJECT_PROP_Copy::destroy(v47);
          CoTaskMemFree(v47);
        }
        CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v89);
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v126);
        ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v79);
        ++v38;
      }
    }
    CVssSnasphotSetIdObserver::StopRecording((CVssSnasphotSetIdObserver *)v127);
    v49 = 0;
    while ( (signed int)v49 < *((_DWORD *)v21 + 4) )
    {
      Buf1 = *(struct _GUID *)(*(_QWORD *)ATL::CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>::operator[](
                                            (char *)v21 + 8,
                                            v49)
                             + 24LL);
      if ( CVssSnasphotSetIdObserver::IsRecorded((CVssSnasphotSetIdObserver *)v127, &Buf1) )
        ATL::CSimpleArray<VSS_OBJECT_PROP_Ptr,ATL::CSimpleArrayEqualHelper<VSS_OBJECT_PROP_Ptr>>::RemoveAt(
          (char *)v21 + 8,
          v49);
      else
        ++v49;
    }
    CVssSnasphotSetIdObserver::~CVssSnasphotSetIdObserver((CVssSnasphotSetIdObserver *)v127);
    v14 = v103;
  }
  v117 = L"base\\stor\\vss\\modules\\coord\\src\\query.cxx";
  v118 = L"CVssCoordinator::Query";
  v119 = L"CORQRYC";
  v120 = 313;
  v121 = 1;
  v122 = 255;
  v124 = 0x1000000;
  memset_0(Src, 0, sizeof(Src));
  v103 = &v117;
  v81 = L"base\\stor\\vss\\inc\\enum.hxx";
  v82 = L"VssBuildEnumInterface";
  v83 = L"INCENUMH";
  v84 = 210;
  v85 = 11;
  v86 = 255;
  v88 = 0x1000000;
  memset_0(v87, 0, sizeof(v87));
  Instance = 0;
  v95 = v82;
  v91 = v81;
  v92 = v83;
  v93 = v84;
  v94 = v85;
  v97 = GetTickCount();
  v98 = v86;
  v89 = 0xFFFFFFFF00000000uLL;
  v101 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v100 = 0;
  v80[0] = 0;
  if ( (int)VssGetTracingContextPerThread(v80) < 0 || (int)VssSetTracingContextPerThread(&v89) < 0 )
  {
    v23 = v101;
  }
  else
  {
    v23 = v80[0];
    v101 = v80[0];
  }
  if ( v23 )
    v96 = *((_DWORD *)v23 + 12) + 1;
  else
    v96 = 0;
  v24 = 160;
  if ( v98 != 255 )
    v24 = v98;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v89, v94) )
    VssTraceMessage(v91, v92, v93, v96, v94, v95, L"ENTER", v24, 0);
  if ( HIBYTE(v88) )
  {
    for ( m = 0; m != 15; ++m )
    {
      v26 = v87[m];
      if ( v26 )
      {
        CoTaskMemFree(v26);
        v87[m] = 0;
      }
    }
  }
  v80[0] = 0;
  Instance = ATL::CComObject<ATL::CComEnumOnSTL<IVssEnumObject,&__s_GUID const _GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3,_VSS_OBJECT_PROP,VSS_OBJECT_PROP_Copy,VSS_OBJECT_PROP_Array,ATL::CComMultiThreadModel>>::CreateInstance(v80);
  if ( Instance < 0 )
  {
    v52 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)&v81, (const struct CVssDebugInfo *)&v117);
    LODWORD(v57) = v53;
    CVssFunctionTracer::Throw(&v89, v52, 2147942414LL, L"Cannot create enumerator instance. [0x%08lx]", v57);
  }
  v27 = v80[0];
  ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(v80, (__int64)v80[0]);
  v28 = ATL::IEnumOnSTLImpl<IVssEnumObject,&__s_GUID const _GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3,_VSS_OBJECT_PROP,VSS_OBJECT_PROP_Copy,VSS_OBJECT_PROP_Array>::Init(
          v27,
          v21,
          v21);
  Instance = v28;
  if ( v28 < 0 )
  {
    v81 = v117;
    v83 = v119;
    v82 = v118;
    v84 = v120;
    v85 = v121;
    v88 = v124;
    v86 = v122;
    HIBYTE(v124) = 0;
    memcpy_0(v87, Src, sizeof(v87));
    LODWORD(v57) = v28;
    CVssFunctionTracer::TranslateGenericError(
      &v89,
      &v81,
      (unsigned int)v28,
      L"Cannot initialize enumerator instance. [0x%08lx]",
      v57);
  }
  Instance = (**(__int64 (__fastcall ***)(CVssCoordinator *, GUID *, const unsigned __int16 **))v80[0])(
               v80[0],
               &GUID_ae1c7110_2f60_11d3_8a39_00c04f72d8e3,
               v14);
  if ( Instance < 0 )
  {
    v54 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)&v81, (const struct CVssDebugInfo *)&v117);
    LODWORD(v77) = v55;
    LODWORD(v76) = 227;
    LODWORD(v75) = 216;
    LODWORD(v74) = 114;
    LODWORD(v73) = 79;
    LODWORD(v71) = 192;
    LODWORD(v69) = 0;
    LODWORD(v66) = 57;
    LODWORD(v63) = 138;
    LODWORD(v60) = 4563;
    LODWORD(v57) = 12128;
    CVssFunctionTracer::TranslateComError(
      &v89,
      v54,
      L"Error querying the <IEnumInterface> interface with GUID {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}. hr = 0x%08lx",
      2921099536LL,
      v57,
      v60,
      v63,
      v66,
      v69,
      v71,
      v73,
      v74,
      v75,
      v76,
      v77);
  }
  v29 = *((_DWORD *)v21 + 4) == 0;
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)v80);
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v100[0]);
  v100[0] = 0;
  CoTaskMemFree(v100[1]);
  v100[1] = 0;
  v30 = GetTickCount() - v97;
  v31 = 160;
  if ( v98 != 255 )
    v31 = v98;
  LODWORD(v71) = Instance;
  LODWORD(v69) = v30;
  LODWORD(v66) = v30 % 0x3E8;
  LODWORD(v63) = v30 / 0x3E8 % 0x3C;
  LODWORD(v60) = v30 / 0xEA60 % 0x3C;
  LODWORD(v57) = v30 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)&v89,
    L"EXIT",
    v31,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v57,
    v60,
    v63,
    v66,
    v69,
    v71);
  VssSetTracingContextPerThread(v101);
  if ( HIBYTE(v124) )
  {
    for ( n = 0; n != 15; ++n )
    {
      v33 = (void *)Src[n];
      if ( v33 )
      {
        CoTaskMemFree(v33);
        Src[n] = 0;
      }
    }
  }
  v105 = v29;
  ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>((__int64)&v78);
  v34 = v105;
  CoTaskMemFree(v114[0]);
  v114[0] = 0;
  CoTaskMemFree(v114[1]);
  v114[1] = 0;
  CoTaskMemFree(v115[0]);
  v115[0] = 0;
  CoTaskMemFree(v115[1]);
  v115[1] = 0;
  v35 = GetTickCount() - TickCount;
  v36 = 160;
  if ( v113 != 255 )
    v36 = v113;
  LODWORD(v72) = v105;
  LODWORD(v70) = v35;
  LODWORD(v67) = v35 % 0x3E8;
  LODWORD(v64) = v35 / 0x3E8 % 0x3C;
  LODWORD(v61) = v35 / 0xEA60 % 0x3C;
  LODWORD(v58) = v35 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v104,
    L"EXIT",
    v36,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v58,
    v61,
    v64,
    v67,
    v70,
    v72);
  VssSetTracingContextPerThread(v116);
  return v34;
}

```

## disassembly

```asm
0x140019eb0  mov     r11, rsp
0x140019eb3  push    rbx
0x140019eb4  push    rsi
0x140019eb5  push    rdi
0x140019eb6  push    r12
0x140019eb8  push    r13
0x140019eba  push    r14
0x140019ebc  push    r15
0x140019ebe  sub     rsp, 3A0h
0x140019ec5  movaps  xmmword ptr [r11-48h], xmm6
0x140019eca  mov     rax, cs:__security_cookie
0x140019ed1  xor     rax, rsp
0x140019ed4  mov     [rsp+3D8h+var_58], rax
0x140019edc  mov     r12d, r9d
0x140019edf  mov     r13d, r8d
0x140019ee2  mov     r15, rdx
0x140019ee5  mov     rdi, rcx
0x140019ee8  mov     [rsp+3D8h+var_338], rcx
0x140019ef0  mov     rsi, [rsp+3D8h+arg_20]
0x140019ef8  mov     [rsp+3D8h+var_200], rsi
0x140019f00  xor     r14d, r14d
0x140019f03  lea     rax, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\coord\\src\\q"...
0x140019f0a  mov     [r11-188h], rax
0x140019f11  lea     rax, aCvsscoordinato_46; "CVssCoordinator::Query"
0x140019f18  mov     [r11-180h], rax
0x140019f1f  lea     rax, aCorqryc; "CORQRYC"
0x140019f26  mov     [r11-178h], rax
0x140019f2d  mov     [rsp+3D8h+var_170], 0B5h
0x140019f38  mov     [rsp+3D8h+var_16C], 1
0x140019f43  mov     [rsp+3D8h+var_168], 0FFh
0x140019f4e  mov     [rsp+3D8h+var_E8], 1000000h
0x140019f59  xor     edx, edx; Val
0x140019f5b  mov     r8d, 78h ; 'x'; Size
0x140019f61  lea     rcx, [r11-160h]; void *
0x140019f68  call    memset_0
0x140019f6d  mov     [rsp+3D8h+var_1F0], r14d
0x140019f75  mov     rax, [rsp+3D8h+var_180]
0x140019f7d  mov     [rsp+3D8h+var_1D0], rax
0x140019f85  mov     rax, [rsp+3D8h+var_188]
0x140019f8d  mov     [rsp+3D8h+var_1E8], rax
0x140019f95  mov     rax, [rsp+3D8h+var_178]
0x140019f9d  mov     [rsp+3D8h+var_1E0], rax
0x140019fa5  mov     eax, [rsp+3D8h+var_170]
0x140019fac  mov     [rsp+3D8h+var_1D8], eax
0x140019fb3  mov     eax, [rsp+3D8h+var_16C]
0x140019fba  mov     [rsp+3D8h+var_1D4], eax
0x140019fc1  call    cs:__imp_GetTickCount
0x140019fc7  mov     [rsp+3D8h+var_1C4], eax
0x140019fce  mov     [rsp+3D8h+var_1F4], 0FFFFFFFFh
0x140019fd9  mov     eax, [rsp+3D8h+var_168]
0x140019fe0  mov     [rsp+3D8h+var_1C0], eax
0x140019fe7  mov     [rsp+3D8h+var_1F8], r14d
0x140019fef  mov     [rsp+3D8h+var_198], r14
0x140019ff7  xorps   xmm0, xmm0
0x140019ffa  movdqa  xmmword ptr [rsp+3D8h+var_1B8], xmm0
0x14001a003  xorps   xmm1, xmm1
0x14001a006  movdqa  xmmword ptr [rsp+3D8h+var_1A8], xmm1
0x14001a00f  mov     [rsp+3D8h+var_340], r14
0x14001a017  lea     rcx, [rsp+3D8h+var_340]
0x14001a01f  call    cs:__imp_VssGetTracingContextPerThread
0x14001a025  test    eax, eax
0x14001a027  jns     loc_14001AC38
0x14001a02d  mov     rax, [rsp+3D8h+var_198]
0x14001a035  test    rax, rax
0x14001a038  jz      loc_14001B18F
0x14001a03e  mov     eax, [rax+30h]
0x14001a041  inc     eax
0x14001a043  mov     [rsp+3D8h+var_1C8], eax
0x14001a04a  mov     ebx, 0A0h
0x14001a04f  cmp     [rsp+3D8h+var_1C0], 0FFh
0x14001a05a  cmovnz  ebx, [rsp+3D8h+var_1C0]
0x14001a062  mov     edx, [rsp+3D8h+var_1D4]; unsigned int
0x14001a069  lea     rcx, [rsp+3D8h+var_1F8]; this
0x14001a071  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14001a076  test    eax, eax
0x14001a078  jnz     loc_14001B291
0x14001a07e  cmp     byte ptr [rsp+3D8h+var_E8+3], r14b
0x14001a086  jz      short loc_14001A0AA
0x14001a088  mov     rbx, r14
0x14001a08b  nop     dword ptr [rax+rax+00h]
0x14001a090  mov     rcx, [rsp+rbx*8+3D8h+Src]; pv
0x14001a098  test    rcx, rcx
0x14001a09b  jnz     loc_14001AA8B
0x14001a0a1  inc     rbx
0x14001a0a4  cmp     rbx, 0Fh
0x14001a0a8  jnz     short loc_14001A090
0x14001a0aa  test    rsi, rsi
0x14001a0ad  jnz     loc_14001B2E9
0x14001a0b3  lea     rcx, [rdi+0B8h]; this
0x14001a0ba  call    ?IsClientValidRequestor@CVssSidCollection@@QEAA_NXZ; CVssSidCollection::IsClientValidRequestor(void)
0x14001a0bf  mov     [rsp+3D8h+var_30C], 1
0x14001a0ca  mov     [rsp+3D8h+var_308], 0FFh
0x14001a0d5  mov     [rsp+3D8h+var_288], 1000000h
0x14001a0e0  xor     edx, edx; Val
0x14001a0e2  mov     r8d, 78h ; 'x'; Size
0x14001a0e8  lea     rcx, [rsp+3D8h+var_300]; void *
0x14001a0f0  test    al, al
0x14001a0f2  lea     rax, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\coord\\src\\q"...
0x14001a0f9  mov     [rsp+3D8h+var_328], rax
0x14001a101  lea     rax, aCvsscoordinato_46; "CVssCoordinator::Query"
0x14001a108  mov     [rsp+3D8h+var_320], rax
0x14001a110  lea     rax, aCorqryc; "CORQRYC"
0x14001a117  mov     [rsp+3D8h+var_318], rax
0x14001a11f  jz      loc_14001B2F1
0x14001a125  mov     [rsp+3D8h+var_310], 0C2h
0x14001a130  call    memset_0
0x14001a135  movzx   ecx, byte ptr [r15+0Eh]
0x14001a13a  movzx   edx, byte ptr [r15+0Dh]
0x14001a13f  movzx   r8d, byte ptr [r15+0Ch]
0x14001a144  movzx   r9d, byte ptr [r15+0Bh]
0x14001a149  movzx   r10d, byte ptr [r15+0Ah]
0x14001a14e  movzx   r11d, byte ptr [r15+9]
0x14001a153  movzx   ebx, byte ptr [r15+8]
0x14001a158  movzx   edi, word ptr [r15+6]
0x14001a15d  movzx   esi, word ptr [r15+4]
0x14001a162  mov     rax, [rsp+3D8h+var_200]
0x14001a16a  mov     [rsp+3D8h+var_358], rax
0x14001a172  mov     [rsp+3D8h+var_360], r12d
0x14001a177  mov     dword ptr [rsp+3D8h+var_368], r13d
0x14001a17c  movzx   eax, byte ptr [r15+0Fh]
0x14001a181  mov     dword ptr [rsp+3D8h+var_370], eax
0x14001a185  mov     dword ptr [rsp+3D8h+var_378], ecx
0x14001a189  mov     dword ptr [rsp+3D8h+var_380], edx
0x14001a18d  mov     dword ptr [rsp+3D8h+var_388], r8d
0x14001a192  mov     dword ptr [rsp+3D8h+var_390], r9d
0x14001a197  mov     dword ptr [rsp+3D8h+var_398], r10d
0x14001a19c  mov     dword ptr [rsp+3D8h+var_3A0], r11d
0x14001a1a1  mov     dword ptr [rsp+3D8h+var_3A8], ebx
0x14001a1a5  mov     dword ptr [rsp+3D8h+var_3B0], edi
0x14001a1a9  mov     dword ptr [rsp+3D8h+var_3B8], esi
0x14001a1ad  mov     r9d, [r15]
0x14001a1b0  lea     r8, aParametersQuer_0; "Parameters: QueriedObjectId = {%.8x-%.4"...
0x14001a1b7  lea     rdx, [rsp+3D8h+var_328]
0x14001a1bf  lea     rcx, [rsp+3D8h+var_1F8]
0x14001a1c7  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14001a1cc  mov     r8d, 10h; Size
0x14001a1d2  lea     rdx, GUID_NULL; Buf2
0x14001a1d9  mov     rcx, r15; Buf1
0x14001a1dc  call    memcmp_0
0x14001a1e1  test    eax, eax
0x14001a1e3  jnz     loc_14001ABA7
0x14001a1e9  cmp     r13d, 1
0x14001a1ed  jnz     loc_14001B323
0x14001a1f3  cmp     r12d, 3
0x14001a1f7  jnz     loc_14001B3B3
0x14001a1fd  mov     rdi, [rsp+3D8h+var_200]
0x14001a205  mov     [rsp+3D8h+var_308], 0FFh
0x14001a210  mov     [rsp+3D8h+var_288], 1000000h
0x14001a21b  xor     edx, edx; Val
0x14001a21d  mov     r8d, 78h ; 'x'; Size
0x14001a223  lea     rcx, [rsp+3D8h+var_300]; void *
0x14001a22b  test    rdi, rdi
0x14001a22e  jz      loc_14001B44D
0x14001a234  lea     r15, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\coord\\src\\q"...
0x14001a23b  mov     [rsp+3D8h+var_328], r15
0x14001a243  lea     rsi, aCvsscoordinato_46; "CVssCoordinator::Query"
0x14001a24a  mov     [rsp+3D8h+var_320], rsi
0x14001a252  lea     rbx, aCorqryc; "CORQRYC"
0x14001a259  mov     [rsp+3D8h+var_318], rbx
0x14001a261  mov     [rsp+3D8h+var_310], 0D8h
0x14001a26c  mov     [rsp+3D8h+var_30C], 0Dh
0x14001a277  call    memset_0
0x14001a27c  mov     r8d, 132h
0x14001a282  lea     rdx, [rsp+3D8h+var_328]
0x14001a28a  lea     rcx, [rsp+3D8h+var_1F8]
0x14001a292  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x14001a297  mov     [rsp+3D8h+var_188], r15
0x14001a29f  mov     [rsp+3D8h+var_180], rsi
0x14001a2a7  mov     [rsp+3D8h+var_178], rbx
0x14001a2af  mov     [rsp+3D8h+var_170], 0D9h
0x14001a2ba  mov     [rsp+3D8h+var_16C], 0Dh
0x14001a2c5  mov     [rsp+3D8h+var_168], 0FFh
0x14001a2d0  mov     [rsp+3D8h+var_E8], 1000000h
0x14001a2db  xor     edx, edx; Val
0x14001a2dd  mov     r8d, 78h ; 'x'; Size
0x14001a2e3  lea     rcx, [rsp+3D8h+Src]; void *
0x14001a2eb  call    memset_0
0x14001a2f0  lea     rax, [rsp+3D8h+var_188]
0x14001a2f8  mov     [rsp+3D8h+var_348], rax
0x14001a300  mov     r8d, 1394h
0x14001a306  lea     rdx, [rsp+3D8h+Buf1]
0x14001a30e  call    ?LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CVssResource::LoadStringW(uint)
0x14001a313  nop
0x14001a314  cmp     [rsp+3D8h+var_60], 7
0x14001a31d  ja      loc_14001B4B8
0x14001a323  lea     rbx, [rsp+3D8h+Buf1]
0x14001a32b  mov     rax, [rsp+3D8h+var_188]
0x14001a333  mov     [rsp+3D8h+var_328], rax
0x14001a33b  mov     rax, [rsp+3D8h+var_178]
0x14001a343  mov     [rsp+3D8h+var_318], rax
0x14001a34b  mov     rax, [rsp+3D8h+var_180]
0x14001a353  mov     [rsp+3D8h+var_320], rax
0x14001a35b  mov     eax, [rsp+3D8h+var_170]
0x14001a362  mov     [rsp+3D8h+var_310], eax
0x14001a369  mov     eax, [rsp+3D8h+var_16C]
0x14001a370  mov     [rsp+3D8h+var_30C], eax
0x14001a377  movzx   eax, word ptr [rsp+3D8h+var_E8]
0x14001a37f  mov     word ptr [rsp+3D8h+var_288], ax
0x14001a387  movzx   eax, byte ptr [rsp+3D8h+var_E8+2]
0x14001a38f  mov     byte ptr [rsp+3D8h+var_288+2], al
0x14001a396  mov     eax, [rsp+3D8h+var_168]
0x14001a39d  mov     [rsp+3D8h+var_308], eax
0x14001a3a4  movzx   eax, byte ptr [rsp+3D8h+var_E8+3]
0x14001a3ac  mov     byte ptr [rsp+3D8h+var_288+3], al
0x14001a3b3  mov     byte ptr [rsp+3D8h+var_E8+3], 0
0x14001a3bb  mov     r8d, 78h ; 'x'; Size
0x14001a3c1  lea     rdx, [rsp+3D8h+Src]; Src
0x14001a3c9  lea     rcx, [rsp+3D8h+var_300]; void *
0x14001a3d1  call    memcpy_0
0x14001a3d6  lea     rax, aCoordinator; "Coordinator"
0x14001a3dd  mov     [rsp+3D8h+var_3B8], rax
0x14001a3e2  mov     r9, rbx
0x14001a3e5  mov     r8d, 2
0x14001a3eb  lea     rdx, [rsp+3D8h+var_328]
0x14001a3f3  lea     rcx, [rsp+3D8h+var_1F8]
0x14001a3fb  call    ?AddContextInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@W4_VssContextType@@PEBG2@Z; CVssFunctionTracer::AddContextInternal(CVssDebugInfo,_VssContextType,ushort const *,ushort const *)
0x14001a400  nop
0x14001a401  mov     rdx, [rsp+3D8h+var_60]
0x14001a409  cmp     rdx, 7
0x14001a40d  ja      loc_14001B4C5
0x14001a413  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14001a41b  movdqu  xmmword ptr [rsp+370h], xmm0
0x14001a424  mov     word ptr [rsp+3D8h+Buf1], r14w
0x14001a42d  cmp     byte ptr [rsp+3D8h+var_E8+3], 0
0x14001a435  jz      short loc_14001A45A
0x14001a437  mov     rbx, r14
0x14001a43a  nop     word ptr [rax+rax+00h]
0x14001a440  mov     rcx, [rsp+rbx*8+3D8h+Src]; pv
0x14001a448  test    rcx, rcx
0x14001a44b  jnz     loc_14001AA9E
0x14001a451  inc     rbx
0x14001a454  cmp     rbx, 0Fh
0x14001a458  jnz     short loc_14001A440
0x14001a45a  mov     rbx, [rsp+3D8h+var_338]
0x14001a462  mov     rcx, rbx; this
0x14001a465  call    ?FreezeContext@CVssCoordinator@@AEAAXXZ; CVssCoordinator::FreezeContext(void)
0x14001a46a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001a471  mov     ecx, 20h ; ' '; unsigned __int64
0x14001a476  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001a47b  mov     r13, rax
0x14001a47e  mov     [rsp+3D8h+var_348], rax
0x14001a486  test    rax, rax
0x14001a489  jz      loc_14001B0EB
0x14001a48f  lea     rcx, [rax+8]
0x14001a493  call    ??0?$CSimpleArray@UCVssSnapshotShareInfo@@V?$CSimpleArrayEqualHelper@UCVssSnapshotShareInfo@@@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>::CSimpleArray<CVssSnapshotShareInfo,ATL::CSimpleArrayEqualHelper<CVssSnapshotShareInfo>>(void)
0x14001a498  mov     [r13+18h], r14d
0x14001a49c  lea     rax, ??_7VSS_OBJECT_PROP_Array@@6B@; const VSS_OBJECT_PROP_Array::`vftable'
0x14001a4a3  mov     [r13+0], rax
0x14001a4a7  test    r13, r13
0x14001a4aa  jz      loc_14001B4DF
0x14001a4b0  mov     rdx, r13
0x14001a4b3  lea     rcx, [rsp+3D8h+var_348]
0x14001a4bb  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(IUnknown *)
0x14001a4c0  nop
0x14001a4c1  sub     r12d, 3
0x14001a4c5  jz      loc_14001AC8E
0x14001a4cb  cmp     r12d, 1
0x14001a4cf  jnz     loc_14001B562
0x14001a4d5  mov     ecx, [rbx+98h]; int
0x14001a4db  mov     r9, r13; struct VSS_OBJECT_PROP_Array *
0x14001a4de  xor     r8d, r8d; unsigned __int16 *
0x14001a4e1  movzx   edx, r12b; bool
0x14001a4e5  call    ?QuerySupportedProvidersIntoArray@CVssProviderManager@@SAXJ_NPEAGPEAVVSS_OBJECT_PROP_Array@@@Z; CVssProviderManager::QuerySupportedProvidersIntoArray(long,bool,ushort *,VSS_OBJECT_PROP_Array *)
0x14001a4ea  mov     [rsp+3D8h+var_188], r15
0x14001a4f2  mov     [rsp+3D8h+var_180], rsi
0x14001a4fa  lea     rax, aCorqryc; "CORQRYC"
0x14001a501  mov     [rsp+3D8h+var_178], rax
0x14001a509  mov     [rsp+3D8h+var_170], 139h
0x14001a514  mov     [rsp+3D8h+var_16C], 1
0x14001a51f  mov     [rsp+3D8h+var_168], 0FFh
0x14001a52a  mov     [rsp+3D8h+var_E8], 1000000h
0x14001a535  xor     edx, edx; Val
0x14001a537  mov     r8d, 78h ; 'x'; Size
0x14001a53d  lea     rcx, [rsp+3D8h+Src]; void *
0x14001a545  call    memset_0
0x14001a54a  lea     rax, [rsp+3D8h+var_188]
0x14001a552  mov     [rsp+3D8h+var_200], rax
0x14001a55a  lea     rax, aBaseStorVssInc_6; "base\\stor\\vss\\inc\\enum.hxx"
0x14001a561  mov     [rsp+3D8h+var_328], rax
0x14001a569  lea     rax, aVssbuildenumin; "VssBuildEnumInterface"
0x14001a570  mov     [rsp+3D8h+var_320], rax
0x14001a578  lea     rax, aIncenumh; "INCENUMH"
0x14001a57f  mov     [rsp+3D8h+var_318], rax
0x14001a587  mov     [rsp+3D8h+var_310], 0D2h
0x14001a592  mov     [rsp+3D8h+var_30C], 0Bh
0x14001a59d  mov     [rsp+3D8h+var_308], 0FFh
0x14001a5a8  mov     [rsp+3D8h+var_288], 1000000h
0x14001a5b3  xor     edx, edx; Val
0x14001a5b5  mov     r8d, 78h ; 'x'; Size
0x14001a5bb  lea     rcx, [rsp+3D8h+var_300]; void *
0x14001a5c3  call    memset_0
0x14001a5c8  mov     [rsp+3D8h+var_270], r14d
0x14001a5d0  mov     rax, [rsp+3D8h+var_320]
0x14001a5d8  mov     [rsp+3D8h+var_250], rax
0x14001a5e0  mov     rax, [rsp+3D8h+var_328]
0x14001a5e8  mov     [rsp+3D8h+var_268], rax
0x14001a5f0  mov     rax, [rsp+3D8h+var_318]
0x14001a5f8  mov     [rsp+3D8h+var_260], rax
0x14001a600  mov     eax, [rsp+3D8h+var_310]
0x14001a607  mov     [rsp+3D8h+var_258], eax
  ... truncated ...
```
