# CVssCoordinator::DeleteSnapshots(_GUID,_VSS_OBJECT_TYPE,int,long *,_GUID *)

- ea: `0x14001d810`
- end: `0x14001e495`
- name: `?DeleteSnapshots@CVssCoordinator@@UEAAJU_GUID@@W4_VSS_OBJECT_TYPE@@HPEAJPEAU2@@Z`
- size: `3205`
- prototype: `__int64 __fastcall(CVssCoordinator *this, struct _GUID *, enum _VSS_OBJECT_TYPE, unsigned int, int *, struct _GUID *)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x140006020`
- `0x1400088fc`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140013d30`
- `0x140015e38`
- `0x140016db0`
- `0x14001940c`
- `0x140019990`
- `0x140019bf0`
- `0x14001c878`
- `0x14001d810`
- `0x14003c160`
- `0x140042acc`
- `0x14004ee3c`
- `0x140055ba4`
- `0x140091560`
- `0x1400921dc`
- `0x140099808`
- `0x14009f4ac`
- `0x14009f678`
- `0x1400cf0f8`
- `0x1400da314`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001d94b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001d94b`
- `VssTrace!__imp_VssTraceMessage` at `0x14001da73`
- `VssTrace!__imp_VssTraceMessage` at `0x14001da73`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001d9b6`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14001d9b6`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001d9a4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14001d9a4`

## string_xrefs

- `0x14001d898`: `CVssCoordinator::DeleteSnapshots`
- `0x14001daeb`: `CVssCoordinator::DeleteSnapshots`
- `0x14001dc3c`: `CVssCoordinator::DeleteSnapshots`
- `0x14001dd57`: `CVssCoordinator::DeleteSnapshots`
- `0x14001df87`: `CVssCoordinator::DeleteSnapshots`
- `0x14001e076`: `CVssCoordinator::DeleteSnapshots`
- `0x14001e240`: `CVssCoordinator::DeleteSnapshots`
- `0x14001d88a`: `base\stor\vss\modules\coord\src\delete.cxx`
- `0x14001dadc`: `base\stor\vss\modules\coord\src\delete.cxx`
- `0x14001dc1a`: `base\stor\vss\modules\coord\src\delete.cxx`
- `0x14001dd48`: `base\stor\vss\modules\coord\src\delete.cxx`
- `0x14001df78`: `base\stor\vss\modules\coord\src\delete.cxx`
- `0x14001e067`: `base\stor\vss\modules\coord\src\delete.cxx`
- `0x14001e231`: `base\stor\vss\modules\coord\src\delete.cxx`
- `0x14001dbf3`: `Parameters: \n  SourceObjectId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n  eSourceObjectType = %d\n  bForceDelete = %s  plDeletedSnapshots = %p  pNondeletedSnapshotID = %p`
- `0x14001dc88`: `NULL plDeletedSnapshots`
- `0x14001dcdb`: `NULL pNondeletedSnapshotID`
- `0x14001dfdc`: `An AMSI provider has determined that this is an unauthorized request`
- `0x14001e3e1`: `DeleteSnapshots({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %d, %d, [%ld],[{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}]) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CVssCoordinator::DeleteSnapshots(
        CVssCoordinator *this,
        struct _GUID *a2,
        enum _VSS_OBJECT_TYPE a3,
        unsigned int a4,
        int *a5,
        struct _GUID *a6)
{
  CVssCoordinator *v8; // r15
  int v9; // eax
  const unsigned __int16 **v10; // rcx
  int v11; // ebx
  bool IsClientValidRequestor; // al
  const wchar_t *v13; // r14
  int *v14; // r12
  enum _VSS_OBJECT_TYPE v15; // r14d
  bool v16; // zf
  struct _GUID *v17; // r12
  __int64 v18; // rcx
  _OWORD *v19; // rbx
  unsigned int *v21; // rbx
  char v22; // di
  unsigned int v23; // ebx
  CVssCoordinator *v24; // rsi
  int v25; // eax
  struct _GUID v26; // xmm6
  int v27; // eax
  int v28; // ecx
  int v29; // edx
  int v30; // r8d
  int v31; // r9d
  int v32; // r10d
  int v33; // r11d
  int v34; // ebx
  int Data3; // edi
  int Data2; // esi
  int v37; // eax
  unsigned int v38; // ebx
  __int64 v39; // [rsp+20h] [rbp-398h]
  __int64 v40; // [rsp+20h] [rbp-398h]
  __int64 v41; // [rsp+20h] [rbp-398h]
  __int64 v42; // [rsp+28h] [rbp-390h]
  __int64 v43; // [rsp+28h] [rbp-390h]
  __int64 v44; // [rsp+30h] [rbp-388h]
  __int64 v45; // [rsp+30h] [rbp-388h]
  __int64 v46; // [rsp+38h] [rbp-380h]
  __int64 v47; // [rsp+38h] [rbp-380h]
  __int64 v48; // [rsp+40h] [rbp-378h]
  __int64 v49; // [rsp+40h] [rbp-378h]
  __int64 v50; // [rsp+48h] [rbp-370h]
  __int64 v51; // [rsp+50h] [rbp-368h]
  __int64 v52; // [rsp+58h] [rbp-360h]
  __int64 v53; // [rsp+60h] [rbp-358h]
  __int64 v54; // [rsp+68h] [rbp-350h]
  __int64 v55; // [rsp+70h] [rbp-348h]
  const wchar_t *v56; // [rsp+78h] [rbp-340h]
  __int64 v57; // [rsp+78h] [rbp-340h]
  __int64 v58; // [rsp+80h] [rbp-338h]
  __int64 v59; // [rsp+88h] [rbp-330h]
  const unsigned __int16 **v61; // [rsp+F8h] [rbp-2C0h] BYREF
  CVssCoordinator *v62; // [rsp+100h] [rbp-2B8h] BYREF
  int v63; // [rsp+108h] [rbp-2B0h] BYREF
  enum _VSS_OBJECT_TYPE v64; // [rsp+10Ch] [rbp-2ACh]
  int *v65; // [rsp+110h] [rbp-2A8h]
  struct _GUID v66; // [rsp+120h] [rbp-298h] BYREF
  struct _GUID *v67; // [rsp+130h] [rbp-288h]
  struct _GUID *v68; // [rsp+138h] [rbp-280h]
  const unsigned __int16 *v69; // [rsp+140h] [rbp-278h] BYREF
  const unsigned __int16 *v70; // [rsp+148h] [rbp-270h]
  const unsigned __int16 *v71; // [rsp+150h] [rbp-268h]
  int v72; // [rsp+158h] [rbp-260h]
  int v73; // [rsp+15Ch] [rbp-25Ch]
  int v74; // [rsp+160h] [rbp-258h]
  _BYTE Src[120]; // [rsp+168h] [rbp-250h] BYREF
  int v76; // [rsp+1E0h] [rbp-1D8h]
  _DWORD v77[2]; // [rsp+1F0h] [rbp-1C8h] BYREF
  int v78; // [rsp+1F8h] [rbp-1C0h]
  const unsigned __int16 *v79; // [rsp+200h] [rbp-1B8h]
  const unsigned __int16 *v80; // [rsp+208h] [rbp-1B0h]
  unsigned int v81; // [rsp+210h] [rbp-1A8h]
  int v82; // [rsp+214h] [rbp-1A4h]
  const unsigned __int16 *v83; // [rsp+218h] [rbp-1A0h]
  unsigned int v84; // [rsp+220h] [rbp-198h]
  DWORD TickCount; // [rsp+224h] [rbp-194h]
  int v86; // [rsp+228h] [rbp-190h]
  __int128 v87; // [rsp+230h] [rbp-188h]
  __int128 v88; // [rsp+240h] [rbp-178h]
  const unsigned __int16 **v89; // [rsp+250h] [rbp-168h]
  struct _GUID *v90; // [rsp+260h] [rbp-158h]
  const unsigned __int16 *v91; // [rsp+268h] [rbp-150h] BYREF
  const unsigned __int16 *v92; // [rsp+270h] [rbp-148h]
  const unsigned __int16 *v93; // [rsp+278h] [rbp-140h]
  int v94; // [rsp+280h] [rbp-138h]
  int v95; // [rsp+284h] [rbp-134h]
  int v96; // [rsp+288h] [rbp-130h]
  _BYTE v97[120]; // [rsp+290h] [rbp-128h] BYREF
  int v98; // [rsp+308h] [rbp-B0h]
  _OWORD v99[3]; // [rsp+328h] [rbp-90h] BYREF
  unsigned int v100; // [rsp+358h] [rbp-60h]

  v64 = a3;
  v68 = a2;
  v62 = this;
  v90 = a6;
  v65 = a5;
  v67 = a6;
  v69 = L"base\\stor\\vss\\modules\\coord\\src\\delete.cxx";
  v70 = L"CVssCoordinator::DeleteSnapshots";
  v71 = L"CORDELEC";
  v72 = 145;
  v73 = 1;
  v74 = 255;
  v8 = 0;
  v76 = 0x1000000;
  memset_0(Src, 0, sizeof(Src));
  v78 = 0;
  v83 = L"CVssCoordinator::DeleteSnapshots";
  v79 = L"base\\stor\\vss\\modules\\coord\\src\\delete.cxx";
  v80 = L"CORDELEC";
  v81 = 145;
  v82 = 1;
  TickCount = GetTickCount();
  v77[1] = -1;
  v86 = 255;
  v77[0] = 0;
  v89 = 0;
  v87 = 0;
  v88 = 0;
  v61 = 0;
  if ( (int)VssGetTracingContextPerThread(&v61) < 0 )
  {
    v10 = v89;
  }
  else
  {
    v9 = VssSetTracingContextPerThread(v77);
    v10 = v89;
    if ( v9 >= 0 )
      v10 = v61;
    v89 = v10;
  }
  if ( v10 )
    v84 = *((_DWORD *)v10 + 12) + 1;
  else
    v84 = 0;
  v11 = 160;
  if ( v86 != 255 )
    v11 = v86;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v77) )
    VssTraceMessage(v79, v80, v81, v84, v82, v83, L"ENTER", v11, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v69);
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = GUID_NULL;
  IsClientValidRequestor = CVssSidCollection::IsClientValidRequestor((CVssCoordinator *)((char *)this + 184));
  v73 = 1;
  v74 = 255;
  v76 = 0x1000000;
  v69 = L"base\\stor\\vss\\modules\\coord\\src\\delete.cxx";
  v70 = L"CVssCoordinator::DeleteSnapshots";
  v71 = L"CORDELEC";
  if ( !IsClientValidRequestor )
  {
    v72 = 154;
    memset_0(Src, 0, sizeof(Src));
    CVssFunctionTracer::Throw(
      v77,
      &v69,
      2147942405LL,
      L"The  client process is not running under a valid user account for requestor");
  }
  v72 = 158;
  memset_0(Src, 0, sizeof(Src));
  v13 = L"TRUE";
  if ( !a4 )
    v13 = L"FALSE";
  v14 = v65;
  v56 = v13;
  v15 = v64;
  LODWORD(v48) = a2->Data4[2];
  LODWORD(v46) = a2->Data4[1];
  LODWORD(v44) = a2->Data4[0];
  LODWORD(v42) = a2->Data3;
  LODWORD(v39) = a2->Data2;
  CVssFunctionTracer::Trace(
    v77,
    &v69,
    L"Parameters: \n"
     "  SourceObjectId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}\n"
     "  eSourceObjectType = %d\n"
     "  bForceDelete = %s  plDeletedSnapshots = %p  pNondeletedSnapshotID = %p",
    a2->Data1,
    v39,
    v42,
    v44,
    v46,
    v48,
    a2->Data4[3],
    a2->Data4[4],
    a2->Data4[5],
    a2->Data4[6],
    a2->Data4[7],
    v64,
    v56,
    v65,
    a6);
  v16 = v14 == 0;
  v17 = v90;
  v76 = 0x1000000;
  v69 = L"base\\stor\\vss\\modules\\coord\\src\\delete.cxx";
  v70 = L"CVssCoordinator::DeleteSnapshots";
  v71 = L"CORDELEC";
  if ( v16 )
  {
    v72 = 174;
    v73 = 1;
    v74 = 255;
    memset_0(Src, 0, sizeof(Src));
    CVssFunctionTracer::Throw(v77, &v69, 2147942487LL, L"NULL plDeletedSnapshots");
  }
  if ( !v90 )
  {
    v72 = 177;
    v73 = 1;
    v74 = 255;
    memset_0(Src, 0, sizeof(Src));
    CVssFunctionTracer::Throw(v77, &v69, 2147942487LL, L"NULL pNondeletedSnapshotID");
  }
  v72 = 179;
  v73 = 13;
  v74 = 255;
  memset_0(Src, 0, sizeof(Src));
  CVssFunctionTracer::AddOperation(v77, &v69, 305);
  v69 = L"base\\stor\\vss\\modules\\coord\\src\\delete.cxx";
  v70 = L"CVssCoordinator::DeleteSnapshots";
  v71 = L"CORDELEC";
  v72 = 180;
  v73 = 13;
  v74 = 255;
  v76 = 0x1000000;
  memset_0(Src, 0, sizeof(Src));
  v61 = &v69;
  CVssResource::LoadStringW(v18, v99, 5012);
  v19 = v99;
  if ( *((_QWORD *)&v99[1] + 1) > 7u )
    v19 = *(_OWORD **)&v99[0];
  v91 = v69;
  v93 = v71;
  v92 = v70;
  v94 = v72;
  v95 = v73;
  v98 = v76;
  v96 = v74;
  HIBYTE(v76) = 0;
  memcpy_0(v97, Src, sizeof(v97));
  CVssFunctionTracer::AddContextInternal(v77, &v91, 2, v19, L"Coordinator");
  if ( *((_QWORD *)&v99[1] + 1) > 7u )
    std::_Deallocate<16>(*(_QWORD *)&v99[0], 2LL * *((_QWORD *)&v99[1] + 1) + 2);
  v99[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v99[0]) = 0;
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v69);
  if ( qword_14014F9F8
    && *(_BYTE *)(qword_14014F9F8 + 16)
    && (memset(v99, 0, sizeof(v99)),
        *(struct _GUID *)((char *)&v99[1] + 12) = *a2,
        HIDWORD(v99[2]) = v15,
        v100 = a4,
        (int)CVssAmsi::Scan(qword_14014F9F8, v99) >= 0x8000) )
  {
    v91 = L"base\\stor\\vss\\modules\\coord\\src\\delete.cxx";
    v92 = L"CVssCoordinator::DeleteSnapshots";
    v93 = L"CORDELEC";
    v94 = 199;
    v95 = 1;
    v96 = 255;
    v98 = 0x1000000;
    memset_0(v97, 0, sizeof(v97));
    CVssFunctionTracer::Trace(v77, &v91, L"An AMSI provider has determined that this is an unauthorized request");
    *v17 = *a2;
    CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v77);
    return 0;
  }
  else
  {
    v21 = (unsigned int *)v62;
    CVssCoordinator::FreezeContext(v62);
    v63 = 0;
    ATL::CComPtr<IMultiInterfacePublisherFilter>::CComPtr<IMultiInterfacePublisherFilter>(&v61);
    if ( v15 == VSS_OBJECT_SNAPSHOT_SET )
    {
      v66 = *a2;
      CVssCoordinator::DeleteExposuresForSnapshotSet((CVssCoordinator *)v21, &v66);
    }
    else
    {
      if ( v15 != VSS_OBJECT_SNAPSHOT )
      {
        v91 = L"base\\stor\\vss\\modules\\coord\\src\\delete.cxx";
        v92 = L"CVssCoordinator::DeleteSnapshots";
        v93 = L"CORDELEC";
        v94 = 286;
        v95 = 1;
        v96 = 255;
        v98 = 0x1000000;
        memset_0(v97, 0, sizeof(v97));
        LODWORD(v40) = v15;
        CVssFunctionTracer::Throw(v77, &v91, 2147942487LL, L"Invalid type %d", v40);
      }
      v66 = *a2;
      CVssCoordinator::DeleteExposuresForSnapshot((CVssCoordinator *)v21, &v66);
    }
    v62 = 0;
    CVssProviderManager::GetProviderItfArray(v21[38], &v62);
    v22 = 0;
    v23 = 0;
    v24 = v62;
    while ( v23 < *((_DWORD *)v24 + 4) )
    {
      v62 = (CVssCoordinator *)(int)v23;
      ATL::CComPtr<IVssSnapshotProvider>::operator=(&v61, *((_QWORD *)v24 + 1) + 8LL * (int)v23);
      if ( !(unsigned __int8)ATL::CComPtrBase<IXMLDOMNode>::operator==(&v61, 0) )
      {
        v66 = *a2;
        v25 = (*((__int64 (__fastcall **)(const unsigned __int16 **, struct _GUID *, _QWORD, _QWORD, int *, struct _GUID *))*v61
               + 7))(
                v61,
                &v66,
                (unsigned int)v15,
                a4,
                &v63,
                v17);
        v78 = v25;
        *v65 += v63;
        if ( v25 < 0 )
        {
          if ( v25 != -2147212536 )
          {
            v26 = *(struct _GUID *)(*(_QWORD *)v24 + 16LL * (_QWORD)v62);
            v91 = L"base\\stor\\vss\\modules\\coord\\src\\delete.cxx";
            v92 = L"CVssCoordinator::DeleteSnapshots";
            v93 = L"CORDELEC";
            v94 = 264;
            v95 = 1;
            v96 = 255;
            v98 = 0x1000000;
            memset_0(v97, 0, sizeof(v97));
            v66 = v26;
            v27 = v17->Data4[7];
            v28 = v17->Data4[6];
            v29 = v17->Data4[5];
            v30 = v17->Data4[4];
            v31 = v17->Data4[3];
            v32 = v17->Data4[2];
            v33 = v17->Data4[1];
            v34 = v17->Data4[0];
            Data3 = v17->Data3;
            Data2 = v17->Data2;
            LOBYTE(v8) = a4 != 0;
            v62 = v8;
            LODWORD(v59) = v63;
            LODWORD(v58) = (_DWORD)v8;
            LODWORD(v57) = v64;
            LODWORD(v55) = a2->Data4[7];
            LODWORD(v54) = a2->Data4[6];
            LODWORD(v53) = a2->Data4[5];
            LODWORD(v52) = a2->Data4[4];
            LODWORD(v51) = v68->Data4[3];
            LODWORD(v50) = v68->Data4[2];
            LODWORD(v49) = v68->Data4[1];
            LODWORD(v47) = v68->Data4[0];
            LODWORD(v45) = v68->Data3;
            LODWORD(v43) = v68->Data2;
            LODWORD(v41) = v68->Data1;
            CVssFunctionTracer::TranslateProviderError(
              v77,
              &v91,
              &v66,
              L"DeleteSnapshots({%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}, %d, %d, [%ld],[{%.8x-%.4x-%.4x-%.2x%.2"
               "x-%.2x%.2x%.2x%.2x%.2x%.2x}]) failed",
              v41,
              v43,
              v45,
              v47,
              v49,
              v50,
              v51,
              v52,
              v53,
              v54,
              v55,
              v57,
              v58,
              v59,
              v90->Data1,
              Data2,
              Data3,
              v34,
              v33,
              v32,
              v31,
              v30,
              v29,
              v28,
              v27);
          }
          v78 = 0;
        }
        else
        {
          v22 = 1;
        }
      }
      ++v23;
    }
    v37 = v78;
    if ( !v22 )
      v37 = -2147212536;
    v78 = v37;
    ATL::CComPtr<IMultiInterfacePublisherFilter>::~CComPtr<IMultiInterfacePublisherFilter>(&v61);
    v38 = v78;
    if ( v78 >= 0 )
      *v17 = GUID_NULL;
    CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v77);
    return v38;
  }
}

```

## disassembly

```asm
0x14001d810  mov     r11, rsp
0x14001d813  push    rbx
0x14001d814  push    rsi
0x14001d815  push    rdi
0x14001d816  push    r12
0x14001d818  push    r13
0x14001d81a  push    r14
0x14001d81c  push    r15
0x14001d81e  sub     rsp, 380h
0x14001d825  movaps  xmmword ptr [r11-48h], xmm6
0x14001d82a  mov     rax, cs:__security_cookie
0x14001d831  xor     rax, rsp
0x14001d834  mov     [rsp+3B8h+var_58], rax
0x14001d83c  mov     [rsp+3B8h+var_2C8], r9d
0x14001d844  mov     [rsp+3B8h+var_2AC], r8d
0x14001d84c  mov     r13, rdx
0x14001d84f  mov     [rsp+3B8h+var_280], rdx
0x14001d857  mov     rdi, rcx
0x14001d85a  mov     [rsp+3B8h+var_2B8], rcx
0x14001d862  mov     r12, [rsp+3B8h+arg_28]
0x14001d86a  mov     [rsp+3B8h+var_158], r12
0x14001d872  mov     rsi, [rsp+3B8h+arg_20]
0x14001d87a  mov     [rsp+3B8h+var_2A8], rsi
0x14001d882  mov     [rsp+3B8h+var_288], r12
0x14001d88a  lea     rax, aBaseStorVssMod_30; "base\\stor\\vss\\modules\\coord\\src\\d"...
0x14001d891  mov     [r11-278h], rax
0x14001d898  lea     rax, aCvsscoordinato_36; "CVssCoordinator::DeleteSnapshots"
0x14001d89f  mov     [r11-270h], rax
0x14001d8a6  lea     rax, aCordelec; "CORDELEC"
0x14001d8ad  mov     [r11-268h], rax
0x14001d8b4  mov     [rsp+3B8h+var_260], 91h
0x14001d8bf  mov     r14d, 1
0x14001d8c5  mov     [r11-25Ch], r14d
0x14001d8cc  mov     [rsp+3B8h+var_258], 0FFh
0x14001d8d7  xor     r15d, r15d
0x14001d8da  mov     [rsp+3B8h+var_1D8], 1000000h
0x14001d8e5  xor     edx, edx; Val
0x14001d8e7  lea     r8d, [r14+77h]; Size
0x14001d8eb  lea     rcx, [r11-250h]; void *
0x14001d8f2  call    memset_0
0x14001d8f7  mov     [rsp+3B8h+var_1C0], r15d
0x14001d8ff  mov     rax, [rsp+3B8h+var_270]
0x14001d907  mov     [rsp+3B8h+var_1A0], rax
0x14001d90f  mov     rax, [rsp+3B8h+var_278]
0x14001d917  mov     [rsp+3B8h+var_1B8], rax
0x14001d91f  mov     rax, [rsp+3B8h+var_268]
0x14001d927  mov     [rsp+3B8h+var_1B0], rax
0x14001d92f  mov     eax, [rsp+3B8h+var_260]
0x14001d936  mov     [rsp+3B8h+var_1A8], eax
0x14001d93d  mov     eax, [rsp+3B8h+var_25C]
0x14001d944  mov     [rsp+3B8h+var_1A4], eax
0x14001d94b  call    cs:__imp_GetTickCount
0x14001d951  mov     [rsp+3B8h+var_194], eax
0x14001d958  mov     [rsp+3B8h+var_1C4], 0FFFFFFFFh
0x14001d963  mov     eax, [rsp+3B8h+var_258]
0x14001d96a  mov     [rsp+3B8h+var_190], eax
0x14001d971  mov     [rsp+3B8h+var_1C8], r15d
0x14001d979  mov     [rsp+3B8h+var_168], r15
0x14001d981  xorps   xmm0, xmm0
0x14001d984  movups  [rsp+3B8h+var_188], xmm0
0x14001d98c  movups  [rsp+3B8h+var_178], xmm0
0x14001d994  mov     [rsp+3B8h+var_2C0], r15
0x14001d99c  lea     rcx, [rsp+3B8h+var_2C0]
0x14001d9a4  call    cs:__imp_VssGetTracingContextPerThread
0x14001d9aa  test    eax, eax
0x14001d9ac  js      short loc_14001D9D9
0x14001d9ae  lea     rcx, [rsp+3B8h+var_1C8]
0x14001d9b6  call    cs:__imp_VssSetTracingContextPerThread
0x14001d9bc  mov     rcx, [rsp+3B8h+var_168]
0x14001d9c4  test    eax, eax
0x14001d9c6  cmovns  rcx, [rsp+3B8h+var_2C0]
0x14001d9cf  mov     [rsp+3B8h+var_168], rcx
0x14001d9d7  jmp     short loc_14001D9E1
0x14001d9d9  mov     rcx, [rsp+3B8h+var_168]
0x14001d9e1  test    rcx, rcx
0x14001d9e4  jz      short loc_14001D9F5
0x14001d9e6  mov     eax, [rcx+30h]
0x14001d9e9  add     eax, r14d
0x14001d9ec  mov     [rsp+3B8h+var_198], eax
0x14001d9f3  jmp     short loc_14001D9FD
0x14001d9f5  mov     [rsp+3B8h+var_198], r15d
0x14001d9fd  mov     ebx, 0A0h
0x14001da02  cmp     [rsp+3B8h+var_190], 0FFh
0x14001da0d  cmovnz  ebx, [rsp+3B8h+var_190]
0x14001da15  lea     rcx, [rsp+3B8h+var_1C8]; this
0x14001da1d  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14001da22  test    eax, eax
0x14001da24  jz      short loc_14001DA79
0x14001da26  mov     [rsp+3B8h+var_378], r15
0x14001da2b  mov     dword ptr [rsp+3B8h+var_380], ebx
0x14001da2f  lea     rax, aEnter; "ENTER"
0x14001da36  mov     [rsp+3B8h+var_388], rax
0x14001da3b  mov     rax, [rsp+3B8h+var_1A0]
0x14001da43  mov     [rsp+3B8h+var_390], rax
0x14001da48  mov     eax, [rsp+3B8h+var_1A4]
0x14001da4f  mov     dword ptr [rsp+3B8h+var_398], eax
0x14001da53  mov     r9d, [rsp+3B8h+var_198]
0x14001da5b  mov     r8d, [rsp+3B8h+var_1A8]
0x14001da63  mov     rdx, [rsp+3B8h+var_1B0]
0x14001da6b  mov     rcx, [rsp+3B8h+var_1B8]
0x14001da73  call    cs:__imp_VssTraceMessage
0x14001da79  lea     rcx, [rsp+3B8h+var_278]; this
0x14001da81  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14001da86  nop
0x14001da87  test    rsi, rsi
0x14001da8a  jz      short loc_14001DA90
0x14001da8c  xor     eax, eax
0x14001da8e  mov     [rsi], eax
0x14001da90  test    r12, r12
0x14001da93  jz      short loc_14001DAA2
0x14001da95  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14001da9c  movdqu  xmmword ptr [r12], xmm0
0x14001daa2  lea     rcx, [rdi+0B8h]; this
0x14001daa9  call    ?IsClientValidRequestor@CVssSidCollection@@QEAA_NXZ; CVssSidCollection::IsClientValidRequestor(void)
0x14001daae  mov     [rsp+3B8h+var_25C], r14d
0x14001dab6  mov     [rsp+3B8h+var_258], 0FFh
0x14001dac1  mov     [rsp+3B8h+var_1D8], 1000000h
0x14001dacc  xor     edx, edx; Val
0x14001dace  lea     r8d, [rdx+78h]; Size
0x14001dad2  lea     rcx, [rsp+3B8h+Src]; void *
0x14001dada  test    al, al
0x14001dadc  lea     rax, aBaseStorVssMod_30; "base\\stor\\vss\\modules\\coord\\src\\d"...
0x14001dae3  mov     [rsp+3B8h+var_278], rax
0x14001daeb  lea     rax, aCvsscoordinato_36; "CVssCoordinator::DeleteSnapshots"
0x14001daf2  mov     [rsp+3B8h+var_270], rax
0x14001dafa  lea     rax, aCordelec; "CORDELEC"
0x14001db01  mov     [rsp+3B8h+var_268], rax
0x14001db09  jnz     short loc_14001DB3D
0x14001db0b  mov     [rsp+3B8h+var_260], 9Ah
0x14001db16  call    memset_0
0x14001db1b  lea     r9, aTheClientProce_2; "The  client process is not running unde"...
0x14001db22  mov     r8d, 80070005h
0x14001db28  lea     rdx, [rsp+3B8h+var_278]
0x14001db30  lea     rcx, [rsp+3B8h+var_1C8]
0x14001db38  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14001db3d  mov     [rsp+3B8h+var_260], 9Eh
0x14001db48  call    memset_0
0x14001db4d  lea     rax, aFalse; "FALSE"
0x14001db54  lea     r14, aTrue; "TRUE"
0x14001db5b  cmp     [rsp+3B8h+var_2C8], r15d
0x14001db63  cmovz   r14, rax
0x14001db67  movzx   eax, byte ptr [r13+0Fh]
0x14001db6c  movzx   ecx, byte ptr [r13+0Eh]
0x14001db71  movzx   edx, byte ptr [r13+0Dh]
0x14001db76  movzx   r8d, byte ptr [r13+0Ch]
0x14001db7b  movzx   r9d, byte ptr [r13+0Bh]
0x14001db80  movzx   r10d, byte ptr [r13+0Ah]
0x14001db85  movzx   r11d, byte ptr [r13+9]
0x14001db8a  movzx   ebx, byte ptr [r13+8]
0x14001db8f  movzx   edi, word ptr [r13+6]
0x14001db94  movzx   esi, word ptr [r13+4]
0x14001db99  mov     [rsp+3B8h+var_330], r12
0x14001dba1  mov     r12, [rsp+3B8h+var_2A8]
0x14001dba9  mov     [rsp+3B8h+var_338], r12
0x14001dbb1  mov     [rsp+3B8h+var_340], r14
0x14001dbb6  mov     r14d, [rsp+3B8h+var_2AC]
0x14001dbbe  mov     dword ptr [rsp+3B8h+var_348], r14d
0x14001dbc3  mov     dword ptr [rsp+3B8h+var_350], eax
0x14001dbc7  mov     dword ptr [rsp+3B8h+var_358], ecx
0x14001dbcb  mov     dword ptr [rsp+3B8h+var_360], edx
0x14001dbcf  mov     dword ptr [rsp+3B8h+var_368], r8d
0x14001dbd4  mov     dword ptr [rsp+3B8h+var_370], r9d
0x14001dbd9  mov     dword ptr [rsp+3B8h+var_378], r10d
0x14001dbde  mov     dword ptr [rsp+3B8h+var_380], r11d
0x14001dbe3  mov     dword ptr [rsp+3B8h+var_388], ebx
0x14001dbe7  mov     dword ptr [rsp+3B8h+var_390], edi
0x14001dbeb  mov     dword ptr [rsp+3B8h+var_398], esi
0x14001dbef  mov     r9d, [r13+0]
0x14001dbf3  lea     r8, aParametersSour; "Parameters: \n  SourceObjectId = {%.8x-"...
0x14001dbfa  lea     rdx, [rsp+3B8h+var_278]
0x14001dc02  lea     rcx, [rsp+3B8h+var_1C8]
0x14001dc0a  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14001dc0f  test    r12, r12
0x14001dc12  mov     r12, [rsp+3B8h+var_158]
0x14001dc1a  lea     rax, aBaseStorVssMod_30; "base\\stor\\vss\\modules\\coord\\src\\d"...
0x14001dc21  mov     [rsp+3B8h+var_1D8], 1000000h
0x14001dc2c  lea     rcx, [rsp+3B8h+Src]; void *
0x14001dc34  mov     [rsp+3B8h+var_278], rax
0x14001dc3c  lea     rax, aCvsscoordinato_36; "CVssCoordinator::DeleteSnapshots"
0x14001dc43  mov     [rsp+3B8h+var_270], rax
0x14001dc4b  lea     rax, aCordelec; "CORDELEC"
0x14001dc52  mov     [rsp+3B8h+var_268], rax
0x14001dc5a  jnz     short loc_14001DCAA
0x14001dc5c  mov     [rsp+3B8h+var_260], 0AEh
0x14001dc67  mov     [rsp+3B8h+var_25C], 1
0x14001dc72  mov     [rsp+3B8h+var_258], 0FFh
0x14001dc7d  xor     edx, edx; Val
0x14001dc7f  lea     r8d, [rdx+78h]; Size
0x14001dc83  call    memset_0
0x14001dc88  lea     r9, aNullPldeleteds; "NULL plDeletedSnapshots"
0x14001dc8f  mov     r8d, 80070057h
0x14001dc95  lea     rdx, [rsp+3B8h+var_278]
0x14001dc9d  lea     rcx, [rsp+3B8h+var_1C8]
0x14001dca5  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14001dcaa  xor     edx, edx; Val
0x14001dcac  test    r12, r12
0x14001dcaf  jnz     short loc_14001DCFD
0x14001dcb1  mov     [rsp+3B8h+var_260], 0B1h
0x14001dcbc  mov     [rsp+3B8h+var_25C], 1
0x14001dcc7  mov     [rsp+3B8h+var_258], 0FFh
0x14001dcd2  lea     r8d, [rdx+78h]; Size
0x14001dcd6  call    memset_0
0x14001dcdb  lea     r9, aNullPnondelete; "NULL pNondeletedSnapshotID"
0x14001dce2  mov     r8d, 80070057h
0x14001dce8  lea     rdx, [rsp+3B8h+var_278]
0x14001dcf0  lea     rcx, [rsp+3B8h+var_1C8]
0x14001dcf8  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14001dcfd  mov     [rsp+3B8h+var_260], 0B3h
0x14001dd08  mov     [rsp+3B8h+var_25C], 0Dh
0x14001dd13  mov     esi, 0FFh
0x14001dd18  mov     [rsp+3B8h+var_258], esi
0x14001dd1f  mov     edi, 1
0x14001dd24  lea     ebx, [rdi+77h]
0x14001dd27  mov     r8d, ebx; Size
0x14001dd2a  call    memset_0
0x14001dd2f  lea     r8d, [rsi+32h]
0x14001dd33  lea     rdx, [rsp+3B8h+var_278]
0x14001dd3b  lea     rcx, [rsp+3B8h+var_1C8]
0x14001dd43  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x14001dd48  lea     rax, aBaseStorVssMod_30; "base\\stor\\vss\\modules\\coord\\src\\d"...
0x14001dd4f  mov     [rsp+3B8h+var_278], rax
0x14001dd57  lea     rax, aCvsscoordinato_36; "CVssCoordinator::DeleteSnapshots"
0x14001dd5e  mov     [rsp+3B8h+var_270], rax
0x14001dd66  lea     rax, aCordelec; "CORDELEC"
0x14001dd6d  mov     [rsp+3B8h+var_268], rax
0x14001dd75  mov     [rsp+3B8h+var_260], 0B4h
0x14001dd80  mov     [rsp+3B8h+var_25C], 0Dh
0x14001dd8b  mov     [rsp+3B8h+var_258], esi
0x14001dd92  mov     [rsp+3B8h+var_1D8], 1000000h
0x14001dd9d  mov     r8d, ebx; Size
0x14001dda0  xor     edx, edx; Val
0x14001dda2  lea     rcx, [rsp+3B8h+Src]; void *
0x14001ddaa  call    memset_0
0x14001ddaf  lea     rax, [rsp+3B8h+var_278]
0x14001ddb7  mov     [rsp+3B8h+var_2C0], rax
0x14001ddbf  mov     r8d, 1394h
0x14001ddc5  lea     rdx, [rsp+3B8h+var_90]
0x14001ddcd  call    ?LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CVssResource::LoadStringW(uint)
0x14001ddd2  nop
0x14001ddd3  lea     rbx, [rsp+3B8h+var_90]
0x14001dddb  cmp     qword ptr [rsp+3B8h+var_78], 7
0x14001dde4  cmova   rbx, qword ptr [rsp+3B8h+var_90]
0x14001dded  mov     rax, [rsp+3B8h+var_278]
0x14001ddf5  mov     [rsp+3B8h+var_150], rax
0x14001ddfd  mov     rax, [rsp+3B8h+var_268]
0x14001de05  mov     [rsp+3B8h+var_140], rax
0x14001de0d  mov     rax, [rsp+3B8h+var_270]
0x14001de15  mov     [rsp+3B8h+var_148], rax
0x14001de1d  mov     eax, [rsp+3B8h+var_260]
0x14001de24  mov     [rsp+3B8h+var_138], eax
0x14001de2b  mov     eax, [rsp+3B8h+var_25C]
0x14001de32  mov     [rsp+3B8h+var_134], eax
0x14001de39  movzx   eax, word ptr [rsp+3B8h+var_1D8]
0x14001de41  mov     word ptr [rsp+3B8h+var_B0], ax
0x14001de49  mov     al, byte ptr [rsp+3B8h+var_1D8+2]
0x14001de50  mov     byte ptr [rsp+3B8h+var_B0+2], al
0x14001de57  mov     eax, [rsp+3B8h+var_258]
0x14001de5e  mov     [rsp+3B8h+var_130], eax
0x14001de65  mov     al, byte ptr [rsp+3B8h+var_1D8+3]
0x14001de6c  mov     byte ptr [rsp+3B8h+var_B0+3], al
0x14001de73  mov     byte ptr [rsp+3B8h+var_1D8+3], r15b
0x14001de7b  lea     r8d, [rdi+77h]; Size
0x14001de7f  lea     rdx, [rsp+3B8h+Src]; Src
0x14001de87  lea     rcx, [rsp+3B8h+var_128]; void *
0x14001de8f  call    memcpy_0
0x14001de94  lea     rax, aCoordinator; "Coordinator"
0x14001de9b  mov     [rsp+3B8h+var_398], rax
0x14001dea0  mov     r9, rbx
0x14001dea3  lea     r8d, [rdi+1]
0x14001dea7  lea     rdx, [rsp+3B8h+var_150]
0x14001deaf  lea     rcx, [rsp+3B8h+var_1C8]
0x14001deb7  call    ?AddContextInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@W4_VssContextType@@PEBG2@Z; CVssFunctionTracer::AddContextInternal(CVssDebugInfo,_VssContextType,ushort const *,ushort const *)
0x14001debc  nop
0x14001debd  mov     rdx, qword ptr [rsp+3B8h+var_78]
0x14001dec5  cmp     rdx, 7
0x14001dec9  jbe     short loc_14001DEE0
0x14001decb  lea     rdx, ds:2[rdx*2]
0x14001ded3  mov     rcx, qword ptr [rsp+3B8h+var_90]
0x14001dedb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14001dee0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14001dee8  movdqu  xmmword ptr [rsp+338h], xmm0
0x14001def1  mov     word ptr [rsp+3B8h+var_90], r15w
0x14001defa  lea     rcx, [rsp+3B8h+var_278]; this
0x14001df02  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14001df07  mov     rcx, cs:qword_14014F9F8
0x14001df0e  test    rcx, rcx
0x14001df11  jz      loc_14001E017
0x14001df17  cmp     [rcx+10h], r15b
0x14001df1b  jz      loc_14001E017
0x14001df21  xorps   xmm0, xmm0
0x14001df24  movups  [rsp+3B8h+var_90], xmm0
0x14001df2c  movups  xmmword ptr [rsp+338h], xmm0
0x14001df34  movups  [rsp+3B8h+var_78+8], xmm0
0x14001df3c  movups  xmm0, xmmword ptr [r13+0]
0x14001df41  movdqu  [rsp+3B8h+var_78+4], xmm0
0x14001df4a  mov     [rsp+3B8h+var_64], r14d
0x14001df52  mov     eax, [rsp+3B8h+var_2C8]
0x14001df59  mov     [rsp+3B8h+var_60], eax
0x14001df60  lea     rdx, [rsp+3B8h+var_90]
0x14001df68  call    ?Scan@CVssAmsi@@QEAA?AW4AMSI_RESULT@@PEAXKW4_VSS_AMSI_TYPE@@@Z; CVssAmsi::Scan(void *,ulong,_VSS_AMSI_TYPE)
  ... truncated ...
```
