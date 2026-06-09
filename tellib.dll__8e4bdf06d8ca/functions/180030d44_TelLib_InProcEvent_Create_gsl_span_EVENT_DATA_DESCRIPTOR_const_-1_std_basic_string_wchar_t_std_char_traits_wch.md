# TelLib::InProcEvent::Create(gsl::span<_EVENT_DATA_DESCRIPTOR const,-1>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180030d44`
- end: `0x180031c01`
- name: `?Create@InProcEvent@TelLib@@SA?AV?$shared_ptr@VAsimovSyntheticEvent@Diagnostics@Microsoft@@@std@@V?$span@$$CBU_EVENT_DATA_DESCRIPTOR@@$0?0@gsl@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `3773`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030bd0`

## callees

- `0x180024e2c`
- `0x180024fb0`
- `0x180028188`
- `0x18002f89c`
- `0x180030a8c`
- `0x180030d44`
- `0x180031c08`
- `0x180031e2c`
- `0x1800326cc`
- `0x180032df0`
- `0x180033210`
- `0x1800333b0`
- `0x180034000`
- `0x180035c10`
- `0x18004be98`
- `0x180055e08`
- `0x1800aac70`
- `0x1800bc2e0`
- `0x1800d2b24`
- `0x18012de40`
- `0x18012de64`
- `0x18012e324`
- `0x18012eb08`
- `0x180346010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180031b77`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180031b77`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x180031b84`
- `msvcp_win!?_Xbad_alloc@std@@YAXXZ` at `0x180031b84`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180030e24`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180031946`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180031a22`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180030e24`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180031946`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180031a22`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180030de2`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180030de2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003113e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800315f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003113e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800315f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031619`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031155`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031155`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003162d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003162d`

## string_xrefs

- `0x1800310e2`: `tempData`
- `0x18003132a`: `tempData`
- `0x180031b70`: `JsonVector - exceeded maximum capacity`
- `0x180031a64`: `onecore\base\telemetry\utc\service\maininproc\inprocevent.cpp`
- `0x180031a8a`: `onecore\base\telemetry\utc\service\maininproc\inprocevent.cpp`
- `0x180031aa2`: `onecore\base\telemetry\utc\service\maininproc\inprocevent.cpp`
- `0x180031aba`: `onecore\base\telemetry\utc\service\maininproc\inprocevent.cpp`
- `0x180031ae2`: `onecore\base\telemetry\utc\service\maininproc\inprocevent.cpp`
- `0x180031afa`: `onecore\base\telemetry\utc\service\maininproc\inprocevent.cpp`
- `0x180031b12`: `onecore\base\telemetry\utc\service\maininproc\inprocevent.cpp`
- `0x180031be7`: `onecore\base\telemetry\utc\service\maininproc\inprocevent.cpp`
- `0x180031ba5`: `[ERROR:FieldToJson(ExtraMetadataBytes=%u)]`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
_QWORD *__fastcall TelLib::InProcEvent::Create(__int64 a1, char **a2)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // rsi
  __int64 v4; // r12
  int v5; // r14d
  char *v6; // r15
  char *v7; // r13
  unsigned __int64 v8; // rbx
  size_t v10; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // r12
  __int64 v13; // rbx
  void *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  char v17; // r9
  char v18; // dl
  void **v19; // rcx
  _DWORD *v20; // rdi
  _QWORD *v21; // r13
  __int64 v22; // rcx
  _BYTE *v23; // rax
  void *v24; // rcx
  _DWORD *v25; // rbx
  void *v26; // r15
  unsigned __int8 *v27; // r14
  unsigned int v28; // edi
  int v29; // ecx
  HANDLE ProcessHeap; // rax
  void *v31; // rax
  unsigned __int8 *v32; // rax
  unsigned int v33; // edi
  unsigned int v34; // edi
  unsigned int v35; // esi
  int v36; // edi
  __int64 v37; // rcx
  __int64 v38; // rax
  unsigned int i; // edx
  __int64 v40; // r9
  const wchar_t *v41; // r10
  _WORD *v42; // r11
  unsigned int v43; // r9d
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned int j; // edx
  __int64 v47; // r10
  const wchar_t *v48; // r11
  _WORD *v49; // rdi
  __int64 v50; // r8
  __int64 v51; // r12
  __int64 v52; // rcx
  int v53; // r15d
  void **v54; // rsi
  _DWORD *v55; // r14
  __int64 v56; // rdx
  __int64 v57; // r11
  __int64 v58; // r10
  __int64 v59; // rdx
  __int64 v60; // rcx
  _QWORD *v61; // rbx
  void *v62; // rdx
  void *v63; // rdx
  char *v64; // rdi
  __int64 v65; // r8
  __int64 v66; // r8
  __int64 v67; // r8
  unsigned int v68; // r9d
  std::_Ref_count_base *v69; // rcx
  _QWORD *v70; // rdx
  void *v71; // rbx
  HANDLE v72; // rax
  void *v73; // rbx
  HANDLE v74; // rax
  void *v75; // rcx
  const struct std::nothrow_t *v76; // rdx
  void *v78; // rdx
  void *v79; // rcx
  void *v80; // rcx
  void *v81; // rdx
  void *v82; // rdx
  void *v83; // rcx
  void *v84; // rcx
  void *v85; // rdx
  void *v86; // rcx
  void *v87; // rdx
  void *v88; // rcx
  void *v89; // rdx
  void *v90; // rcx
  void *v91; // rdx
  char v92; // al
  unsigned int v93; // edx
  int v94; // r8d
  int v96; // [rsp+20h] [rbp-E0h]
  struct JsonEventReaderBase::FieldInfo *v97; // [rsp+20h] [rbp-E0h]
  void *v98[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *v99[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v100; // [rsp+60h] [rbp-A0h]
  __int128 v101; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v102[4]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v103; // [rsp+A0h] [rbp-60h]
  char v104; // [rsp+A2h] [rbp-5Eh]
  int v105; // [rsp+A4h] [rbp-5Ch]
  _DWORD *v106; // [rsp+A8h] [rbp-58h]
  __int64 v107; // [rsp+B0h] [rbp-50h]
  unsigned int v108; // [rsp+B8h] [rbp-48h]
  int v109; // [rsp+BCh] [rbp-44h]
  void *v110; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v111; // [rsp+C8h] [rbp-38h]
  LPVOID v112; // [rsp+D0h] [rbp-30h]
  __int64 v113; // [rsp+D8h] [rbp-28h]
  char v114; // [rsp+E0h] [rbp-20h]
  LPVOID lpMem; // [rsp+E8h] [rbp-18h]
  __int64 v116; // [rsp+F0h] [rbp-10h]
  char v117; // [rsp+F8h] [rbp-8h]
  _QWORD v118[2]; // [rsp+100h] [rbp+0h] BYREF
  void *v119[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v120; // [rsp+120h] [rbp+20h]
  __int64 v121; // [rsp+128h] [rbp+28h]
  int v122; // [rsp+134h] [rbp+34h]
  void *v123[2]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int64 v124; // [rsp+158h] [rbp+58h]
  __m256i v125; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int8 *v126; // [rsp+180h] [rbp+80h]
  unsigned __int64 v127; // [rsp+188h] [rbp+88h]
  void *v128[2]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int8 *v129; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v130; // [rsp+1A8h] [rbp+A8h]
  void *v131[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int8 *v132; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v133; // [rsp+1C8h] [rbp+C8h]
  void *v134[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int8 *v135; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v136; // [rsp+1E8h] [rbp+E8h]
  void *v137[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int64 v138; // [rsp+208h] [rbp+108h]
  _BYTE v139[697]; // [rsp+210h] [rbp+110h] BYREF
  char v140; // [rsp+4C9h] [rbp+3C9h]
  wil::details::in1diag3 *retaddr; // [rsp+708h] [rbp+608h]

  *(_QWORD *)&v101 = a1;
  v121 = a1;
  v100 = 0;
  v7 = *a2;
  if ( *a2 )
  {
    v6 = a2[1];
    v5 = 2;
    if ( *((_DWORD *)v6 + 3) != 2 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\maininproc\\inprocevent.cpp",
        (const char *)0x8007000DLL,
        v96);
    v8 = *((unsigned int *)v6 + 2);
    v2 = *(_QWORD *)v6;
    if ( *(_QWORD *)v6 || !*((_DWORD *)v6 + 2) )
    {
      if ( (unsigned int)v8 < 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x78,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\maininproc\\inprocevent.cpp",
          (const char *)0x8007000DLL,
          v96);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TvsWarningFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TvsWarningFixes>::GetImpl'::`2'::impl) )
      {
        if ( v8 <= 2 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x56,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\maininproc\\inprocevent.cpp",
            (const char *)0x8007000DLL,
            v96);
      }
      else if ( v8 <= 2 )
      {
        goto LABEL_7;
      }
      v118[0] = v2 + 2;
      v123[0] = (void *)strnlen((const char *)(v2 + 2), v8 - 2);
      if ( (unsigned __int64)v7 > 1 )
      {
        if ( *((_DWORD *)v6 + 7) != 1 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xDA,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\maininproc\\inprocevent.cpp",
            (const char *)0x8007000DLL,
            v96);
        v3 = *((unsigned int *)v6 + 6);
        v4 = *((_QWORD *)v6 + 2);
        if ( v4 )
        {
          if ( v3 >= 2 )
          {
            v92 = 0;
            goto LABEL_142;
          }
        }
        else if ( *((_DWORD *)v6 + 6) )
        {
          goto LABEL_7;
        }
        v92 = 1;
LABEL_142:
        if ( v92 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xE0,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\maininproc\\inprocevent.cpp",
            (const char *)0x8007000DLL,
            v96);
        v2 = 2;
        v5 = 0;
        v93 = 0;
        while ( v2 < v3 )
        {
          v94 = *(unsigned __int8 *)(v4 + v2);
          if ( v93 <= 0x15 )
          {
            v5 |= (v94 ^ 0x80) << (21 - v93);
            v93 += 7;
          }
          ++v2;
          if ( (v94 & 0x80u) == 0 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TvsWarningFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TvsWarningFixes>::GetImpl'::`2'::impl) )
            {
              if ( (v2 & 0x8000000000000000uLL) != 0LL || v2 >= v3 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x56,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\maininproc\\inprocevent.cpp",
                  (const char *)0x8007000DLL,
                  v96);
            }
            if ( v2 < v3 )
            {
              v99[0] = (void *)(v4 + v2);
              v98[0] = (void *)strnlen((const char *)(v4 + v2), v3 - v2);
              v2 += (unsigned __int64)v98[0] + (v98[0] != (void *)(v3 - v2));
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TvsWarningFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TvsWarningFixes>::GetImpl'::`2'::impl) )
                goto LABEL_8;
              goto LABEL_12;
            }
            goto LABEL_7;
          }
        }
        goto LABEL_7;
      }
    }
  }
  while ( 1 )
  {
LABEL_7:
    _o_terminate();
    __debugbreak();
LABEL_8:
    if ( (v2 & 0x8000000000000000uLL) != 0LL || v2 >= v3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\maininproc\\inprocevent.cpp",
        (const char *)0x8007000DLL,
        v96);
LABEL_12:
    if ( v2 < v3 )
    {
      v10 = strnlen((const char *)(v2 + v4), v3 - v2);
      v11 = v10 + v2 + (v10 != v3 - v2);
      if ( v3 >= v11 )
      {
        v3 -= v11;
        if ( v3 != -1 )
        {
          v125.m256i_i32[1] = 0;
          v125.m256i_i64[1] = (__int64)v99[0];
          v125.m256i_i64[2] = (__int64)v98[0];
          v7 -= 2;
          if ( v7 != (char *)-1LL )
            break;
        }
      }
    }
  }
  v12 = v11 + v4;
  v99[0] = v7;
  v99[1] = v6 + 32;
  TelLib::InProcEvent::FlattenEventData(v119, v99);
  *(_OWORD *)v99 = *(_OWORD *)&v125.m256i_u64[1];
  v13 = Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(&v125, v99);
  v118[1] = v123[0];
  v14 = (void *)Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(v137, v118);
  v15 = std::wstring::_Append<wchar_t>(v14);
  std::wstring::wstring(v123, v15);
  v100 = 16;
  std::wstring::wstring(v134, v16, v123, v13);
  v100 = 48;
  if ( v124 > 7 )
  {
    v78 = (void *)(2 * v124 + 2);
    v99[0] = v78;
    v79 = v123[0];
    v98[0] = v123[0];
    if ( (unsigned __int64)v78 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v98, (unsigned __int64 *)v99);
      v79 = v98[0];
      v78 = v99[0];
    }
    operator delete(v79, (const struct std::nothrow_t *)v78);
  }
  if ( v138 > 7 )
  {
    v80 = v137[0];
    v81 = (void *)(2 * v138 + 2);
    v99[0] = v81;
    v98[0] = v137[0];
    if ( (unsigned __int64)v81 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v98, (unsigned __int64 *)v99);
      v81 = v99[0];
      v80 = v98[0];
    }
    operator delete(v80, (const struct std::nothrow_t *)v81);
  }
  v137[2] = 0;
  v138 = 7;
  LOWORD(v137[0]) = 0;
  if ( v125.m256i_i64[3] > 7uLL )
  {
    v82 = (void *)(2 * v125.m256i_i64[3] + 2);
    v99[0] = v82;
    v83 = (void *)v125.m256i_i64[0];
    v98[0] = (void *)v125.m256i_i64[0];
    if ( (unsigned __int64)v82 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v98, (unsigned __int64 *)v99);
      v82 = v99[0];
      v83 = v98[0];
    }
    operator delete(v83, (const struct std::nothrow_t *)v82);
  }
  v125.m256i_i64[2] = 0;
  v125.m256i_i64[3] = 7;
  v125.m256i_i16[0] = 0;
  v17 = (v5 & 0x1000000) == 0 && (v5 & 0x800000) != 0;
  if ( (v5 & 0x400000) != 0 )
  {
    v18 = 0;
  }
  else if ( (v5 & 0x40000) != 0 )
  {
    v18 = 1;
  }
  else
  {
    v18 = 0;
    if ( (v5 & 0x200000) != 0 )
      v18 = 2;
  }
  v19 = v134;
  if ( v136 > 7 )
    v19 = (void **)v134[0];
  v123[0] = v19;
  v123[1] = v135;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
    (unsigned int)v139,
    (unsigned int)v123,
    0,
    0,
    v17,
    v18,
    0,
    3);
  v100 = 112;
  v140 |= 0x10u;
  v20 = operator new(0x4B0u);
  v123[0] = v20;
  *(_OWORD *)v20 = 0;
  v20[2] = 1;
  v20[3] = 1;
  *(_QWORD *)v20 = &std::_Ref_count_obj2<Microsoft::Diagnostics::AsimovSyntheticEvent>::`vftable';
  Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(v20 + 4, v139);
  v21 = (_QWORD *)v101;
  *(_QWORD *)v101 = v20 + 4;
  v21[1] = v20;
  v100 = 241;
  Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v139);
  v22 = *v21;
  v23 = (_BYTE *)(*v21 + 696LL);
  if ( (v5 & 0x8000000) != 0 )
    *v23 |= 1u;
  if ( (v5 & 0x4000000) != 0 )
    *v23 |= 2u;
  if ( (v5 & 0x2000000) != 0 )
    *(_BYTE *)(v22 + 288) = 2;
  if ( (v5 & 0x20000) != 0 )
    *(_BYTE *)(v22 + 288) = 1;
  v103 = 12032;
  v102[1] = 10000000;
  v102[3] = 1;
  v102[2] = 0;
  v102[0] = &JsonEventReaderTraceLogging::`vftable';
  v24 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  lpMem = 0;
  v116 = 0;
  v117 = 0;
  v25 = (_DWORD *)(*v21 + 16LL);
  v26 = v119[0];
  v27 = (unsigned __int8 *)((char *)v119[1] - (char *)v119[0]);
  v123[0] = L"tempData";
  v123[1] = (void *)8;
  *(_QWORD *)&v101 = v25;
  DWORD2(v101) = 0;
  HIDWORD(v101) = v122;
  v111 = (unsigned __int8 *)(v12 + (unsigned int)v3);
  if ( !(_DWORD)v3 )
  {
LABEL_39:
    LODWORD(v113) = v3;
    memset_0(v24, 0, (unsigned int)(2 * v3));
    v104 = 0;
    v105 = 0;
    v106 = v25;
    v107 = 0;
    v108 = 0;
    v109 = (int)v27;
    v110 = v26;
    *(_OWORD *)v125.m256i_i8 = v101;
    v27 = 0;
    *(_OWORD *)&v125.m256i_u64[2] = 0u;
    JsonEventReaderTraceLogging::InitInfo((JsonEventReaderBase *)v102, (struct JsonEventReaderBase::FieldInfo *)&v125);
    if ( v108 )
      goto LABEL_46;
    v32 = v126;
    v33 = v127;
    if ( (v127 & 0x10000000) != 0 )
      v32 = (unsigned __int8 *)JsonEventReaderTraceLogging::SkipStructMetadata(
                                 (JsonEventReaderTraceLogging *)v102,
                                 v126,
                                 HIWORD(v127));
    if ( v32 == v111 )
      goto LABEL_43;
    goto LABEL_176;
  }
  v28 = 15;
  if ( (unsigned int)v3 > 0xF )
  {
    LODWORD(v98[0]) = 0;
    _BitScanReverse((unsigned int *)&v29, v3);
    v28 = -2;
    if ( 2 << v29 )
    {
      v28 = (2 << v29) - 1;
    }
    else if ( (_DWORD)v3 == -1 )
    {
      std::_Xlength_error("JsonVector - exceeded maximum capacity");
    }
  }
  ProcessHeap = GetProcessHeap();
  v31 = HeapAlloc(ProcessHeap, 0, 2LL * v28);
  v24 = v31;
  if ( v31 )
  {
    v112 = v31;
    HIDWORD(v113) = v28;
    goto LABEL_39;
  }
  std::_Xbad_alloc();
  __debugbreak();
LABEL_176:
  v108 = 13;
  LODWORD(v97) = (_DWORD)v111 - (_DWORD)v32;
  (*(void (**)(_QWORD *, __int128 *, void **, const wchar_t *, ...))(v102[0] + 8LL))(
    v102,
    &v101,
    v123,
    L"[ERROR:FieldToJson(ExtraMetadataBytes=%u)]",
    v97);
  if ( v108 != (_DWORD)v27 )
    goto LABEL_46;
  v33 = v127;
LABEL_43:
  v34 = v33 >> 28;
  if ( (v34 & 2) != 0 )
  {
    (*(void (__fastcall **)(_QWORD *, __m256i *))(v102[0] + 32LL))(v102, &v125);
  }
  else if ( (v34 & 1) != 0 )
  {
    (*(void (__fastcall **)(_QWORD *, __m256i *))(v102[0] + 40LL))(v102, &v125);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *, __m256i *))(v102[0] + 48LL))(v102, &v125);
  }
LABEL_46:
  if ( v108 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\maininproc\\inprocevent.cpp",
      (const char *)v108,
      (unsigned int)v97);
  v35 = (unsigned int)v27;
  v36 = v25[2];
  if ( !v36
    || (v37 = *(_QWORD *)v25, *(_BYTE *)(*(_QWORD *)v25 + 7LL) < 0xFEu)
    || (v38 = (2 * (*(_DWORD *)(v37 + 4) & 0xFFFFFFu) + 15) >> 2, (_DWORD)v38 == *(_DWORD *)(v37 + 8)) )
  {
LABEL_60:
    v43 = (unsigned int)v27;
    if ( !v36 )
      goto LABEL_83;
  }
  else
  {
    for ( i = *(_DWORD *)(v37 + 4 * v38);
          *(_BYTE *)(v37 + 4LL * i + 7) == 0xFD || (*(_DWORD *)(v37 + 4LL * i + 4) & 0xFFFFFF) != 4;
          i = *(_DWORD *)(v37 + 4LL * i) )
    {
LABEL_57:
      if ( i == *(_DWORD *)(v37 + 8) )
        goto LABEL_60;
    }
    v40 = 4;
    v41 = L"data";
    v42 = (_WORD *)(v37 + 12 + 4LL * i);
    while ( v40 )
    {
      if ( *v42 != *v41 )
        goto LABEL_57;
      --v40;
      ++v42;
      ++v41;
    }
    v35 = i;
    v43 = (unsigned int)v27;
  }
  v44 = *(_QWORD *)v25;
  if ( *(_BYTE *)(*(_QWORD *)v25 + 7LL) >= 0xFEu )
  {
    v45 = (2 * (*(_DWORD *)(v44 + 4) & 0xFFFFFFu) + 15) >> 2;
    if ( (_DWORD)v45 != *(_DWORD *)(v44 + 8) )
    {
      for ( j = *(_DWORD *)(v44 + 4 * v45);
            *(_BYTE *)(v44 + 4LL * j + 7) == 0xFD || (*(_DWORD *)(v44 + 4LL * j + 4) & 0xFFFFFF) != 8;
            j = *(_DWORD *)(v44 + 4LL * j) )
      {
LABEL_70:
        if ( j == *(_DWORD *)(v44 + 8) )
          goto LABEL_73;
      }
      v47 = 8;
      v48 = L"tempData";
      v49 = (_WORD *)(v44 + 12 + 4LL * j);
      while ( v47 )
      {
        if ( *v49 != *v48 )
          goto LABEL_70;
        --v47;
        ++v49;
        ++v48;
      }
      v43 = j;
    }
  }
LABEL_73:
  v50 = *(_QWORD *)v25;
  if ( *(_BYTE *)(v44 + 4LL * v43 + 7) >= 0xFEu )
  {
    v51 = v35;
    if ( *(_BYTE *)(v44 + 4LL * v35 + 7) < 0xFEu )
      __int2c();
    v52 = v43 + ((2 * (*(_DWORD *)(v44 + 4LL * v43 + 4) & 0xFFFFFFu) + 15) >> 2);
    v53 = *(_DWORD *)(v50 + 4LL * v43 + 8);
    if ( (_DWORD)v52 != v53 )
    {
      LODWORD(v98[0]) = (_DWORD)v27;
      v54 = v98;
      v55 = (_DWORD *)(v50 + 4 * v52);
      do
      {
        while ( 1 )
        {
          v56 = (unsigned int)*v55;
          v57 = *(_QWORD *)v25;
          v58 = *(_QWORD *)v25 + 4 * v56;
          if ( *(_BYTE *)(v58 + 7) != 0xFD )
            break;
          if ( (_DWORD)v56 == v53 )
            goto LABEL_81;
          LODWORD(v52) = *v55;
          v55 = (_DWORD *)(*(_QWORD *)v25 + 4 * v56);
        }
        *v55 = *(_DWORD *)v58;
        *(_DWORD *)v54 = v56;
        v54 = (void **)v58;
        *(_DWORD *)v58 = v56;
      }
      while ( (_DWORD)v56 != v53 );
      *(_DWORD *)(v50 + 4LL * v43 + 8) = v52;
      v57 = *(_QWORD *)v25;
LABEL_81:
      v27 = 0;
      if ( LODWORD(v98[0]) )
      {
        v59 = *(unsigned int *)(v57 + 4 * v51 + 8);
        *(_DWORD *)(v57 + 4 * v51 + 8) = *(_DWORD *)v54;
        v60 = *(_QWORD *)v25;
        *(_DWORD *)v54 = *(_DWORD *)(*(_QWORD *)v25 + 4 * v59);
        *(_DWORD *)(v60 + 4 * v59) = v98[0];
      }
    }
  }
LABEL_83:
  if ( !v43 )
    __int2c();
  *(_BYTE *)(*(_QWORD *)v25 + 4LL * v43 + 7) = -3;
  v61 = (_QWORD *)*v21;
  *(struct _GUID *)v125.m256i_i8 = s_sevilleGroupId;
  *(_OWORD *)&v125.m256i_u64[2] = 0;
  v126 = v27;
  v127 = (unsigned __int64)v27;
  v62 = &qword_18043B2B0;
  if ( (unsigned __int64)qword_18043B2C8 > 7 )
    v62 = (void *)qword_18043B2B0;
  std::wstring::_Construct<2,wchar_t const *>(&v125.m256i_u64[2], v62, qword_18043B2C0);
  *(_OWORD *)v128 = 0;
  v129 = v27;
  v130 = (unsigned __int64)v27;
  std::wstring::_Construct<1,wchar_t *>(v128, L"SEVILLE", 7);
  *(_OWORD *)v131 = 0;
  v132 = v27;
  v133 = (unsigned __int64)v27;
  v63 = &TelLib::g_tenantToken;
  if ( (unsigned __int64)qword_18043B2A8 > 7 )
    v63 = (void *)TelLib::g_tenantToken;
  std::wstring::_Construct<2,wchar_t const *>(v131, v63, qword_18043B2A0);
  v64 = (char *)operator new(0x80u);
  *(_QWORD *)&v101 = v64;
  *(_OWORD *)v64 = 0;
  *((_DWORD *)v64 + 2) = 1;
  *((_DWORD *)v64 + 3) = 1;
  *(_QWORD *)v64 = &std::_Ref_count_obj2<Microsoft::Diagnostics::ProviderGroupInfo>::`vftable';
  *((_OWORD *)v64 + 1) = *(_OWORD *)v125.m256i_i8;
  std::wstring::wstring(v64 + 32, &v125.m256i_u64[2]);
  std::wstring::wstring(v65 + 48, v128);
  std::wstring::wstring(v66 + 80, v131);
  v100 = 497;
  *(_QWORD *)&v101 = v67;
  *((_QWORD *)&v101 + 1) = v64;
  *(_OWORD *)v123 = 0;
  if ( (unsigned __int8 *)v61[72] == v27 )
  {
    _InterlockedAdd((volatile signed __int32 *)v64 + 2, v68);
    v61[72] = v67;
    v69 = (std::_Ref_count_base *)v61[73];
    v61[73] = v64;
    if ( v69 )
      std::_Ref_count_base::_Decref(v69);
  }
  if ( (unsigned __int8 *)v61[48] == v27 )
  {
    v70 = (_QWORD *)(v61[72] + 80LL);
    if ( v61 + 46 != v70 )
    {
      if ( *(_QWORD *)(v61[72] + 104LL) > 7u )
        v70 = (_QWORD *)*v70;
      std::wstring::assign(v61 + 46, v70, *(_QWORD *)(v61[72] + 96LL));
    }
  }
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v64);
  if ( v133 > 7 )
  {
    v84 = v131[0];
    v85 = (void *)(2 * v133 + 2);
    v99[0] = v85;
    v98[0] = v131[0];
    if ( (unsigned __int64)v85 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v98, (unsigned __int64 *)v99);
      v85 = v99[0];
      v84 = v98[0];
    }
    operator delete(v84, (const struct std::nothrow_t *)v85);
  }
  if ( v130 > 7 )
  {
    v86 = v128[0];
    v87 = (void *)(2 * v130 + 2);
    v99[0] = v87;
    v98[0] = v128[0];
    if ( (unsigned __int64)v87 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v98, (unsigned __int64 *)v99);
      v87 = v99[0];
      v86 = v98[0];
    }
    operator delete(v86, (const struct std::nothrow_t *)v87);
  }
  if ( v127 > 7 )
  {
    v88 = (void *)v125.m256i_i64[2];
    v89 = (void *)(2 * v127 + 2);
    v99[0] = v89;
    v98[0] = (void *)v125.m256i_i64[2];
    if ( (unsigned __int64)v89 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v98, (unsigned __int64 *)v99);
      v89 = v99[0];
      v88 = v98[0];
    }
    operator delete(v88, (const struct std::nothrow_t *)v89);
  }
  v71 = lpMem;
  if ( lpMem )
  {
    v72 = GetProcessHeap();
    HeapFree(v72, 0, v71);
  }
  v73 = v112;
  if ( v112 )
  {
    v74 = GetProcessHeap();
    HeapFree(v74, 0, v73);
  }
  v102[0] = &JsonEventReaderBase::`vftable';
  if ( v136 > 7 )
  {
    v90 = v134[0];
    v91 = (void *)(2 * v136 + 2);
    v99[0] = v91;
    v98[0] = v134[0];
    if ( (unsigned __int64)v91 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v98, (unsigned __int64 *)v99);
      v91 = v99[0];
      v90 = v98[0];
    }
    operator delete(v90, (const struct std::nothrow_t *)v91);
  }
  v135 = v27;
  v136 = 7;
  LOWORD(v134[0]) = (_WORD)v27;
  v75 = v119[0];
  if ( v119[0] )
  {
    v76 = (const struct std::nothrow_t *)(v120 - (unsigned __int64)v119[0]);
    v98[0] = (void *)(v120 - (unsigned __int64)v119[0]);
    v99[0] = v119[0];
    if ( v120 - (unsigned __int64)v119[0] >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v99, (unsigned __int64 *)v98);
      v75 = v99[0];
      v76 = (const struct std::nothrow_t *)v98[0];
    }
    operator delete(v75, v76);
  }
  return v21;
}

```

## disassembly

```asm
0x180030d44  push    rbp
0x180030d46  push    rbx
0x180030d47  push    rsi
0x180030d48  push    rdi
0x180030d49  push    r12
0x180030d4b  push    r13
0x180030d4d  push    r14
0x180030d4f  push    r15
0x180030d51  lea     rbp, [rsp-5C8h]
0x180030d59  sub     rsp, 6C8h
0x180030d60  mov     rax, cs:__security_cookie
0x180030d67  xor     rax, rsp
0x180030d6a  mov     [rbp+600h+var_50], rax
0x180030d71  mov     [rsp+700h+var_690], rcx
0x180030d76  mov     [rbp+600h+var_5D8], rcx
0x180030d7a  mov     [rsp+700h+var_6A0], 0
0x180030d82  mov     r13, [rdx]
0x180030d85  test    r13, r13
0x180030d88  jz      short loc_180030DE2
0x180030d8a  mov     r15, [rdx+8]
0x180030d8e  mov     rcx, [rbp+608h]; this
0x180030d95  mov     r14d, 2
0x180030d9b  cmp     [r15+0Ch], r14d
0x180030d9f  jnz     loc_180031A5E
0x180030da5  mov     ebx, [r15+8]
0x180030da9  mov     rdi, [r15]
0x180030dac  test    rdi, rdi
0x180030daf  jz      loc_180031A76
0x180030db5  mov     rcx, [rbp+608h]; this
0x180030dbc  cmp     ebx, r14d
0x180030dbf  jb      loc_180031A84
0x180030dc5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TvsWarningFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TvsWarningFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TvsWarningFixes> `wil::Feature<__WilFeatureTraits_Feature_TvsWarningFixes>::GetImpl(void)'::`2'::impl
0x180030dcc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TvsWarningFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TvsWarningFixes>::__private_IsEnabled(void)
0x180030dd1  test    al, al
0x180030dd3  jnz     loc_180031927
0x180030dd9  cmp     rbx, r14
0x180030ddc  ja      loc_180031937
0x180030de2  call    cs:__imp__o_terminate
0x180030de9  nop     dword ptr [rax+rax+00h]
0x180030dee  int     3; Trap to Debugger
0x180030def  test    rdi, rdi
0x180030df2  js      loc_180031847
0x180030df8  cmp     rdi, rsi
0x180030dfb  jnb     loc_180031847
0x180030e01  xor     al, al
0x180030e03  mov     rcx, [rbp+608h]; this
0x180030e0a  test    al, al
0x180030e0c  jnz     loc_180031B0C
0x180030e12  cmp     rdi, rsi
0x180030e15  jnb     short loc_180030DE2
0x180030e17  mov     rbx, rsi
0x180030e1a  sub     rbx, rdi
0x180030e1d  lea     rcx, [rdi+r12]; String
0x180030e21  mov     rdx, rbx; MaxCount
0x180030e24  call    cs:__imp_strnlen
0x180030e2b  nop     dword ptr [rax+rax+00h]
0x180030e30  xor     ecx, ecx
0x180030e32  cmp     rax, rbx
0x180030e35  setnz   cl
0x180030e38  lea     rdx, [rdi+rcx]
0x180030e3c  add     rdx, rax
0x180030e3f  cmp     rsi, rdx
0x180030e42  jb      short loc_180030DE2
0x180030e44  sub     rsi, rdx
0x180030e47  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180030e4b  jz      short loc_180030DE2
0x180030e4d  xor     eax, eax
0x180030e4f  mov     dword ptr [rbp+600h+var_5A0+4], eax
0x180030e52  mov     rax, [rsp+700h+var_6B0]
0x180030e57  mov     [rbp+600h+var_5A0+8], rax
0x180030e5b  mov     rax, [rsp+700h+var_6C0]
0x180030e60  mov     [rbp+600h+var_590], rax
0x180030e64  add     r13, 0FFFFFFFFFFFFFFFEh
0x180030e68  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180030e6c  jz      loc_180030DE2
0x180030e72  add     r12, rdx
0x180030e75  mov     [rsp+700h+var_6B0], r13
0x180030e7a  lea     rax, [r15+20h]
0x180030e7e  mov     [rsp+700h+var_6B0+8], rax
0x180030e83  lea     rdx, [rsp+700h+var_6B0]
0x180030e88  lea     rcx, [rbp+600h+var_5F0]
0x180030e8c  call    ?FlattenEventData@InProcEvent@TelLib@@CA?AV?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@V?$span@$$CBU_EVENT_DATA_DESCRIPTOR@@$0?0@gsl@@@Z; TelLib::InProcEvent::FlattenEventData(gsl::span<_EVENT_DATA_DESCRIPTOR const,-1>)
0x180030e91  nop
0x180030e92  movups  xmm0, xmmword ptr [rbp+600h+var_5A0+8]
0x180030e96  movdqu  xmmword ptr [rsp+700h+var_6B0], xmm0
0x180030e9c  lea     rdx, [rsp+700h+var_6B0]
0x180030ea1  lea     rcx, [rbp+600h+var_5A0]
0x180030ea5  call    ?MultiByteStringToWideString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(std::string_view,ulong)
0x180030eaa  mov     rbx, rax
0x180030ead  mov     rax, [rbp+600h+var_600]
0x180030eb1  mov     [rbp+600h+var_600], rax
0x180030eb5  mov     rax, [rbp+600h+var_5C0]
0x180030eb9  mov     [rbp+600h+var_5F8], rax
0x180030ebd  lea     rdx, [rbp+600h+var_600]
0x180030ec1  lea     rcx, [rbp+600h+var_510]
0x180030ec8  call    ?MultiByteStringToWideString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(std::string_view,ulong)
0x180030ecd  nop
0x180030ece  mov     r13d, 1
0x180030ed4  mov     r8d, r13d
0x180030ed7  lea     rdx, PathName; "."
0x180030ede  mov     rcx, rax; Src
0x180030ee1  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180030ee6  mov     rdx, rax
0x180030ee9  lea     rcx, [rbp+600h+var_5C0]
0x180030eed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180030ef2  mov     [rsp+700h+var_6A0], 10h
0x180030efa  mov     r9, rbx
0x180030efd  lea     r8, [rbp+600h+var_5C0]
0x180030f01  lea     rcx, [rbp+600h+var_530]
0x180030f08  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x180030f0d  mov     [rsp+700h+var_6A0], 30h ; '0'
0x180030f15  mov     edi, 1000h
0x180030f1a  mov     rdx, [rbp+600h+var_5A8]
0x180030f1e  lea     ebx, [r13+6]
0x180030f22  cmp     rdx, rbx
0x180030f25  ja      loc_1800316DD
0x180030f2b  mov     rdx, [rbp+600h+var_4F8]
0x180030f32  cmp     rdx, rbx
0x180030f35  ja      loc_180031706
0x180030f3b  xor     r15d, r15d
0x180030f3e  mov     [rbp+600h+var_500], r15
0x180030f45  mov     [rbp+600h+var_4F8], rbx
0x180030f4c  mov     word ptr [rbp+600h+var_510], r15w
0x180030f54  mov     rdx, [rbp+600h+var_588]
0x180030f58  cmp     rdx, rbx
0x180030f5b  ja      loc_180031732
0x180030f61  mov     [rbp+600h+var_590], r15
0x180030f65  mov     [rbp+600h+var_588], rbx
0x180030f69  mov     word ptr [rbp+600h+var_5A0], r15w
0x180030f6e  bt      r14d, 18h
0x180030f73  jb      loc_1800316D5
0x180030f79  movzx   r9d, r15b
0x180030f7d  bt      r14d, 17h
0x180030f82  cmovb   r9d, r13d
0x180030f86  bt      r14d, 16h
0x180030f8b  jnb     loc_180031B24
0x180030f91  mov     dl, r15b
0x180030f94  mov     r8, r15
0x180030f97  lea     rcx, [rbp+600h+var_530]
0x180030f9e  cmp     [rbp+600h+var_518], rbx
0x180030fa5  cmova   rcx, [rbp+600h+var_530]
0x180030fad  mov     rax, [rbp+600h+var_520]
0x180030fb4  mov     [rbp+600h+var_5C0], rcx
0x180030fb8  mov     [rbp+600h+var_5C0+8], rax
0x180030fbc  mov     [rsp+700h+var_6C8], 3
0x180030fc1  mov     [rsp+700h+var_6D0], r15b
0x180030fc6  mov     [rsp+700h+var_6D8], dl
0x180030fca  mov     byte ptr [rsp+700h+var_6E0], r9b
0x180030fcf  xor     r9d, r9d
0x180030fd2  lea     rdx, [rbp+600h+var_5C0]
0x180030fd6  lea     rcx, [rbp+600h+var_4F0]
0x180030fdd  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@AEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_NVAsimovSyntheticType@12@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool,Microsoft::Diagnostics::AsimovSyntheticType)
0x180030fe2  mov     [rsp+700h+var_6A0], 70h ; 'p'
0x180030fea  or      [rbp+600h+var_237], 10h
0x180030ff1  mov     ecx, 4B0h; Size
0x180030ff6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030ffb  mov     rdi, rax
0x180030ffe  mov     [rbp+600h+var_5C0], rax
0x180031002  xorps   xmm0, xmm0
0x180031005  movups  xmmword ptr [rax], xmm0
0x180031008  mov     [rax+8], r13d
0x18003100c  mov     [rax+0Ch], r13d
0x180031010  lea     rax, ??_7?$_Ref_count_obj2@VAsimovSyntheticEvent@Diagnostics@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Diagnostics::AsimovSyntheticEvent>::`vftable'
0x180031017  mov     [rdi], rax
0x18003101a  lea     rbx, [rdi+10h]
0x18003101e  lea     rdx, [rbp+600h+var_4F0]
0x180031025  mov     rcx, rbx
0x180031028  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &&)
0x18003102d  nop
0x18003102e  mov     r13, [rsp+700h+var_690]
0x180031033  mov     [r13+0], rbx
0x180031037  mov     [r13+8], rdi
0x18003103b  mov     [rsp+700h+var_6A0], 0F1h
0x180031043  lea     rcx, [rbp+600h+var_4F0]; this
0x18003104a  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18003104f  mov     rcx, [r13+0]
0x180031053  lea     rax, [rcx+2B8h]
0x18003105a  mov     edx, 1
0x18003105f  bt      r14d, 1Bh
0x180031064  jnb     short loc_180031068
0x180031066  or      [rax], dl
0x180031068  mov     r8d, 2
0x18003106e  bt      r14d, 1Ah
0x180031073  jb      loc_180031B49
0x180031079  bt      r14d, 19h
0x18003107e  jb      loc_180031B51
0x180031084  bt      r14d, 11h
0x180031089  jb      loc_180031B5D
0x18003108f  mov     [rbp+600h+var_660], 2F00h
0x180031095  mov     [rbp+600h+var_678], 989680h
0x18003109d  mov     [rbp+600h+var_668], 1
0x1800310a5  mov     [rbp+600h+var_670], r15
0x1800310a9  lea     rax, ??_7JsonEventReaderTraceLogging@@6B@; const JsonEventReaderTraceLogging::`vftable'
0x1800310b0  mov     [rbp+600h+var_680], rax
0x1800310b4  mov     rcx, r15
0x1800310b7  mov     [rbp+600h+var_630], rcx
0x1800310bb  mov     [rbp+600h+var_628], r15
0x1800310bf  mov     [rbp+600h+var_620], r15b
0x1800310c3  mov     [rbp+600h+lpMem], r15
0x1800310c7  mov     [rbp+600h+var_610], r15
0x1800310cb  mov     [rbp+600h+var_608], r15b
0x1800310cf  mov     rbx, [r13+0]
0x1800310d3  add     rbx, 10h
0x1800310d7  mov     r14, [rbp+600h+var_5E8]
0x1800310db  mov     r15, [rbp+600h+var_5F0]
0x1800310df  sub     r14, r15
0x1800310e2  lea     rax, aTempdata; "tempData"
0x1800310e9  mov     [rbp+600h+var_5C0], rax
0x1800310ed  mov     [rbp+600h+var_5C0+8], 8
0x1800310f5  mov     [rsp+700h+var_690], rbx
0x1800310fa  xor     edi, edi
0x1800310fc  mov     dword ptr [rsp+700h+var_688], edi
0x180031100  mov     eax, [rbp+600h+var_5CC]
0x180031103  mov     dword ptr [rsp+700h+var_688+4], eax
0x180031107  mov     eax, esi
0x180031109  add     rax, r12
0x18003110c  mov     [rbp+600h+var_638], rax
0x180031110  test    esi, esi
0x180031112  jz      short loc_180031176
0x180031114  mov     edi, 0Fh
0x180031119  cmp     esi, edi
0x18003111b  jbe     short loc_18003113E
0x18003111d  mov     dword ptr [rsp+700h+var_6C0], 0
0x180031125  bsr     ecx, esi
0x180031128  mov     eax, r8d
0x18003112b  shl     eax, cl
0x18003112d  dec     eax
0x18003112f  mov     edi, 0FFFFFFFEh
0x180031134  cmp     eax, edi
0x180031136  ja      loc_180031B68
0x18003113c  mov     edi, eax
0x18003113e  call    cs:__imp_GetProcessHeap
0x180031145  nop     dword ptr [rax+rax+00h]
0x18003114a  mov     r8d, edi
0x18003114d  add     r8, r8; dwBytes
0x180031150  xor     edx, edx; dwFlags
0x180031152  mov     rcx, rax; hHeap
0x180031155  call    cs:__imp_HeapAlloc
0x18003115c  nop     dword ptr [rax+rax+00h]
0x180031161  mov     rcx, rax; void *
0x180031164  test    rax, rax
0x180031167  jz      loc_180031B84
0x18003116d  mov     [rbp+600h+var_630], rax
0x180031171  mov     dword ptr [rbp+600h+var_628+4], edi
0x180031174  xor     edi, edi
0x180031176  mov     dword ptr [rbp+600h+var_628], esi
0x180031179  lea     r8d, [rsi+rsi]; Size
0x18003117d  xor     edx, edx; Val
0x18003117f  call    memset_0
0x180031184  mov     [rbp+600h+var_65E], dil
0x180031188  mov     [rbp+600h+var_65C], edi
0x18003118b  mov     [rbp+600h+var_658], rbx
0x18003118f  mov     [rbp+600h+var_650], rdi
0x180031193  mov     dword ptr [rbp+600h+var_648], edi
0x180031196  mov     dword ptr [rbp+600h+var_648+4], r14d
0x18003119a  mov     [rbp+600h+var_640], r15
0x18003119e  mov     rax, [rsp+700h+var_690]
0x1800311a3  mov     [rbp+600h+var_5A0], rax
0x1800311a7  mov     eax, dword ptr [rsp+700h+var_688]
0x1800311ab  mov     dword ptr [rbp+600h+var_5A0+8], eax
0x1800311ae  mov     eax, dword ptr [rsp+700h+var_688+4]
0x1800311b2  mov     dword ptr [rbp+600h+var_5A0+0Ch], eax
0x1800311b5  xor     r14d, r14d
0x1800311b8  mov     [rbp+600h+var_590], r14
0x1800311bc  mov     [rbp+600h+var_588], r14
0x1800311c0  lea     rax, [rbp+600h+var_5A0]
0x1800311c4  mov     [rsp+700h+var_6E0], rax; unsigned int
0x1800311c9  xor     r9d, r9d
0x1800311cc  mov     r8, r12
0x1800311cf  lea     rdx, [rbp+600h+var_5C0]
0x1800311d3  lea     rcx, [rbp+600h+var_680]; this
0x1800311d7  call    ?InitInfo@JsonEventReaderTraceLogging@@AEAAXAEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@PEBE_NAEAUFieldInfo@JsonEventReaderBase@@@Z; JsonEventReaderTraceLogging::InitInfo(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,uchar const *,bool,JsonEventReaderBase::FieldInfo &)
0x1800311dc  cmp     dword ptr [rbp+600h+var_648], r14d
0x1800311e0  jnz     loc_180031BDC
0x1800311e6  mov     rax, [rbp+600h+var_580]
0x1800311ed  mov     edi, dword ptr [rbp+600h+var_578]
0x1800311f3  bt      edi, 1Ch
0x1800311f7  jnb     short loc_18003120D
0x1800311f9  movzx   r8d, word ptr [rbp+600h+var_578+6]; unsigned int
0x180031201  mov     rdx, rax; unsigned __int8 *
0x180031204  lea     rcx, [rbp+600h+var_680]; this
0x180031208  call    ?SkipStructMetadata@JsonEventReaderTraceLogging@@AEBAPEBEPEBEI@Z; JsonEventReaderTraceLogging::SkipStructMetadata(uchar const *,uint)
0x18003120d  cmp     rax, [rbp+600h+var_638]
0x180031211  jnz     loc_180031B91
0x180031217  shr     edi, 1Ch
0x18003121a  mov     r15d, 2
0x180031220  mov     rax, [rbp+600h+var_680]
0x180031224  lea     rdx, [rbp+600h+var_5A0]
0x180031228  lea     rcx, [rbp+600h+var_680]
0x18003122c  test    r15b, dil
0x18003122f  jnz     loc_180031BD3
0x180031235  test    dil, 1
0x180031239  jnz     loc_1800316CC
0x18003123f  mov     rax, [rax+30h]
0x180031243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031248  mov     r9d, dword ptr [rbp+600h+var_648]; char *
0x18003124c  mov     rcx, [rbp+608h]; this
0x180031253  test    r9d, r9d
0x180031256  jnz     loc_180031BE7
0x18003125c  mov     esi, r14d
  ... truncated ...
```
