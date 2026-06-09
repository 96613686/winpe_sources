# CVssCoordinator::AddToSnapshotSet(ushort *,_GUID,_GUID *)

- ea: `0x140002270`
- end: `0x14000300b`
- name: `?AddToSnapshotSet@CVssCoordinator@@UEAAJPEAGU_GUID@@PEAU2@@Z`
- size: `3483`
- prototype: `__int64 __fastcall(CVssCoordinator *this, unsigned __int16 *, struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x140002270`
- `0x140003014`
- `0x14000400c`
- `0x140011440`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013c60`
- `0x140013d30`
- `0x140015950`
- `0x140015e38`
- `0x140019990`
- `0x140019bf0`
- `0x140030230`
- `0x14004ee3c`
- `0x1400718a0`
- `0x140091560`
- `0x1400921dc`
- `0x140099808`
- `0x1400da308`
- `0x1400da314`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002371`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000282c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002371`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000282c`
- `VssTrace!__imp_VssTraceMessage` at `0x14000249f`
- `VssTrace!__imp_VssTraceMessage` at `0x140002956`
- `VssTrace!__imp_VssTraceMessage` at `0x14000249f`
- `VssTrace!__imp_VssTraceMessage` at `0x140002956`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400023e0`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000289d`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400023e0`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000289d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400023ce`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000288b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400023ce`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000288b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400024bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000297d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140002c8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400024bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000297d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140002c8d`

## string_xrefs

- `0x140002584`: `The client process is not running under an administrator account or does not have backup privilege enabled`
- `0x140002a38`: `Snapshot set object not yet created.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVssCoordinator::AddToSnapshotSet(
        CVssCoordinator *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  __int64 v7; // rax
  int v8; // r14d
  int v9; // ebx
  bool v10; // dl
  void *v11; // rcx
  __int64 i; // rbx
  bool v13; // dl
  bool v14; // dl
  __int64 v15; // rax
  struct _GUID *v16; // rsi
  CVssCoordinator *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  struct _GUID *v19; // rax
  __int64 j; // rbx
  void *v21; // rcx
  CVssSnapshotSetObject **v22; // rdi
  char v23; // al
  int v24; // edx
  __int64 v25; // rcx
  _QWORD *v26; // rbx
  __int64 k; // rbx
  void *v28; // rcx
  CVssCoordinator *v29; // r14
  int v30; // ebx
  unsigned int v31; // ebx
  int v32; // ebx
  unsigned int v33; // ebx
  __int64 v35; // [rsp+20h] [rbp-2D8h]
  __int64 v36; // [rsp+20h] [rbp-2D8h]
  __int64 v37; // [rsp+28h] [rbp-2D0h]
  __int64 v38; // [rsp+30h] [rbp-2C8h]
  __int64 v39; // [rsp+38h] [rbp-2C0h]
  __int64 v40; // [rsp+40h] [rbp-2B8h]
  __int64 v41; // [rsp+80h] [rbp-278h] BYREF
  struct _GUID *v42; // [rsp+88h] [rbp-270h] BYREF
  struct _GUID v43; // [rsp+90h] [rbp-268h] BYREF
  const unsigned __int16 *v44; // [rsp+A0h] [rbp-258h] BYREF
  wchar_t *v45; // [rsp+A8h] [rbp-250h]
  const unsigned __int16 *v46; // [rsp+B0h] [rbp-248h]
  __int64 v47; // [rsp+B8h] [rbp-240h]
  int v48; // [rsp+C0h] [rbp-238h]
  LPVOID v49[15]; // [rsp+C8h] [rbp-230h] BYREF
  int v50; // [rsp+140h] [rbp-1B8h]
  CVssCoordinator *v51; // [rsp+148h] [rbp-1B0h]
  _DWORD v52[2]; // [rsp+150h] [rbp-1A8h] BYREF
  int v53; // [rsp+158h] [rbp-1A0h]
  const unsigned __int16 *v54; // [rsp+160h] [rbp-198h]
  const unsigned __int16 *v55; // [rsp+168h] [rbp-190h]
  __int64 v56; // [rsp+170h] [rbp-188h]
  const unsigned __int16 *v57; // [rsp+178h] [rbp-180h]
  unsigned int v58; // [rsp+180h] [rbp-178h]
  DWORD TickCount; // [rsp+184h] [rbp-174h]
  int v60; // [rsp+188h] [rbp-170h]
  __int128 v61; // [rsp+190h] [rbp-168h]
  __int128 v62; // [rsp+1A0h] [rbp-158h]
  __int64 v63; // [rsp+1B0h] [rbp-148h]
  const unsigned __int16 *v64; // [rsp+1C0h] [rbp-138h] BYREF
  const unsigned __int16 *v65; // [rsp+1C8h] [rbp-130h]
  const unsigned __int16 *v66; // [rsp+1D0h] [rbp-128h]
  __int64 v67; // [rsp+1D8h] [rbp-120h]
  __int64 v68; // [rsp+1E0h] [rbp-118h]
  LPVOID pv; // [rsp+1E8h] [rbp-110h] BYREF
  unsigned int v70; // [rsp+1F0h] [rbp-108h]
  DWORD v71; // [rsp+1F4h] [rbp-104h]
  int v72; // [rsp+1F8h] [rbp-100h]
  __int128 v73; // [rsp+200h] [rbp-F8h]
  __int128 v74; // [rsp+210h] [rbp-E8h]
  struct _GUID *v75; // [rsp+220h] [rbp-D8h]
  int v76; // [rsp+260h] [rbp-98h]
  int v77; // [rsp+270h] [rbp-88h] BYREF
  char *v78; // [rsp+278h] [rbp-80h] BYREF
  char v79; // [rsp+280h] [rbp-78h]
  _com_error *v80; // [rsp+288h] [rbp-70h] BYREF
  const std::exception *v81; // [rsp+290h] [rbp-68h] BYREF
  _QWORD v82[2]; // [rsp+298h] [rbp-60h] BYREF
  __m128i si128; // [rsp+2A8h] [rbp-50h]

  v42 = a4;
  v51 = this;
  v64 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v65 = L"CVssCoordinator::AddToSnapshotSet";
  v66 = L"CORCOORC";
  v67 = 0x1000001B5LL;
  LODWORD(v68) = 255;
  v76 = 0x1000000;
  memset_0(&pv, 0, 0x78u);
  v53 = 0;
  v57 = L"CVssCoordinator::AddToSnapshotSet";
  v54 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v55 = L"CORCOORC";
  v56 = 0x1000001B5LL;
  TickCount = GetTickCount();
  v52[1] = -1;
  v60 = 255;
  v52[0] = 0;
  v63 = 0;
  v61 = 0;
  v62 = 0;
  v41 = 0;
  if ( (int)VssGetTracingContextPerThread(&v41) < 0 || (int)VssSetTracingContextPerThread(v52) < 0 )
  {
    v7 = v63;
  }
  else
  {
    v7 = v41;
    v63 = v41;
  }
  if ( v7 )
    v58 = *(_DWORD *)(v7 + 48) + 1;
  else
    v58 = 0;
  v8 = 160;
  v9 = 160;
  if ( v60 != 255 )
    v9 = v60;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v52, HIDWORD(v56)) )
    VssTraceMessage(v54, v55, (unsigned int)v56, v58, HIDWORD(v56), v57, L"ENTER", v9, 0);
  if ( HIBYTE(v76) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v11 = *(&pv + i);
      if ( v11 )
      {
        CoTaskMemFree(v11);
        *(&pv + i) = 0;
      }
    }
  }
  if ( a4 )
    *a4 = GUID_NULL;
  try
  {
    if ( !HasPrivilege((unsigned int)v11, v10) && !IsInGroup(0x227u, v13) && !IsInGroup(0x220u, v14) )
    {
      v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
      v46 = L"CORCOORC";
      v47 = 0x1000001C1LL;
      v48 = 255;
      v50 = 0x1000000;
      memset_0(v49, 0, sizeof(v49));
      CVssFunctionTracer::Throw(
        v52,
        &v44,
        2147942405LL,
        L"The client process is not running under an administrator account or does not have backup privilege enabled");
    }
    v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
    v46 = L"CORCOORC";
    v47 = 0x1000001C5LL;
    v48 = 255;
    v50 = 0x1000000;
    memset_0(v49, 0, sizeof(v49));
    LODWORD(v40) = a3->Data4[1];
    LODWORD(v39) = a3->Data4[0];
    LODWORD(v38) = a3->Data3;
    LODWORD(v37) = a3->Data2;
    LODWORD(v35) = a3->Data1;
    CVssFunctionTracer::Trace(
      v52,
      &v44,
      L"Parameters: VolumeName = %s ProviderId = {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}  pSnapshotId = %p ",
      a2,
      v35,
      v37,
      v38,
      v39,
      v40,
      a3->Data4[2],
      a3->Data4[3],
      a3->Data4[4],
      a3->Data4[5],
      a3->Data4[6],
      a3->Data4[7],
      v42);
    if ( !a2 )
      goto LABEL_67;
    v15 = -1;
    do
      ++v15;
    while ( a2[v15] );
    if ( !v15 )
    {
LABEL_67:
      v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
      v46 = L"CORCOORC";
      v47 = 0x1000001CCLL;
      v48 = 255;
      v50 = 0x1000000;
      memset_0(v49, 0, sizeof(v49));
      CVssFunctionTracer::Throw(v52, &v44, 2147942487LL, L"NULL pwszVolumeName");
    }
    v16 = v42;
    v48 = 255;
    v50 = 0x1000000;
    if ( !v42 )
    {
      v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
      v46 = L"CORCOORC";
      v47 = 0x1000001CELL;
      memset_0(v49, 0, sizeof(v49));
      CVssFunctionTracer::Throw(v52, &v44, 2147942487LL, L"NULL pSnapshotId");
    }
    v17 = v51;
    v18 = (struct _RTL_CRITICAL_SECTION *)((char *)v51 + 16);
    v78 = (char *)v51 + 16;
    v79 = 0;
    v44 = L"base\\stor\\vss\\inc\\vs_types.hxx";
    v45 = L"CVssAutomaticLock2::CVssAutomaticLock2";
    v46 = L"INCTYPEH";
    v47 = 0xB00000100LL;
    memset_0(v49, 0, sizeof(v49));
    LODWORD(v65) = 0;
    pv = v45;
    v66 = v44;
    v67 = (__int64)v46;
    v68 = v47;
    v71 = GetTickCount();
    v72 = v48;
    v64 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
    v75 = 0;
    v73 = 0;
    v74 = 0;
    v42 = 0;
    if ( (int)VssGetTracingContextPerThread(&v42) < 0 || (int)VssSetTracingContextPerThread(&v64) < 0 )
    {
      v19 = v75;
    }
    else
    {
      v19 = v42;
      v75 = v42;
    }
    if ( v19 )
      v70 = v19[3].Data1 + 1;
    else
      v70 = 0;
    if ( v72 != 255 )
      v8 = v72;
    if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v64, HIDWORD(v68)) )
      VssTraceMessage(v66, v67, (unsigned int)v68, v70, HIDWORD(v68), pv, L"ENTER", v8, 0);
    if ( HIBYTE(v50) )
    {
      for ( j = 0; j != 15; ++j )
      {
        v21 = v49[j];
        if ( v21 )
        {
          CoTaskMemFree(v21);
          v49[j] = 0;
        }
      }
      v17 = v51;
    }
    CVssCriticalSection::Lock(v18);
    v79 = 1;
    CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)&v64);
    v22 = (CVssSnapshotSetObject **)((char *)v17 + 120);
    v23 = ATL::CComPtrBase<IXMLDOMNode>::operator==((char *)v17 + 120, 0);
    v48 = 255;
    v50 = 0x1000000;
    if ( v23 )
    {
      v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
      v46 = L"CORCOORC";
      v47 = 0x1000001D5LL;
      memset_0(v49, v24, sizeof(v49));
      CVssFunctionTracer::Throw(v52, &v44, 2147754753LL, L"Snapshot set object not yet created.");
    }
    v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
    v46 = L"CORCOORC";
    v47 = 0xD000001DBLL;
    memset_0(v49, v24, sizeof(v49));
    CVssFunctionTracer::AddOperation(v52, &v44, 303);
    v64 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v65 = L"CVssCoordinator::AddToSnapshotSet";
    v66 = L"CORCOORC";
    v67 = 0xD000001DCLL;
    LODWORD(v68) = 255;
    v76 = 0x1000000;
    memset_0(&pv, 0, 0x78u);
    *(_QWORD *)&v43.Data1 = &v64;
    CVssResource::LoadStringW(v25, v82, 5012);
    if ( si128.m128i_i64[1] <= 7uLL )
      v26 = v82;
    else
      v26 = (_QWORD *)v82[0];
    v44 = v64;
    v46 = v66;
    v45 = (wchar_t *)v65;
    v47 = v67;
    v50 = v76;
    v48 = v68;
    HIBYTE(v76) = 0;
    memcpy_0(v49, &pv, sizeof(v49));
    CVssFunctionTracer::AddContextInternal(v52, &v44, 2, v26, L"Coordinator");
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v82[0], 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v82[0]) = 0;
    if ( HIBYTE(v76) )
    {
      for ( k = 0; k != 15; ++k )
      {
        v28 = *(&pv + k);
        if ( v28 )
        {
          CoTaskMemFree(v28);
          *(&pv + k) = 0;
        }
      }
    }
    LODWORD(v41) = 0;
    v43 = *a3;
    v29 = v51;
    v30 = (*(__int64 (__fastcall **)(CVssCoordinator *, struct _GUID *, unsigned __int16 *, _QWORD, __int64 *))(*(_QWORD *)v51 + 208LL))(
            v51,
            &v43,
            a2,
            0,
            &v41);
    v53 = v30;
    if ( v30 < 0 )
    {
      v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
      v46 = L"CORCOORC";
      v47 = 0x1000001F9LL;
      v48 = 255;
      v50 = 0x1000000;
      memset_0(v49, 0, sizeof(v49));
      LODWORD(v36) = v30;
      CVssFunctionTracer::Throw(
        v52,
        &v44,
        (unsigned int)v30,
        L"IsVolumeSupportedInternal() failed with error code 0x%08lx",
        v36);
    }
    if ( !(_DWORD)v41 )
    {
      v31 = -2147212530;
      if ( !memcmp_0(a3, &GUID_NULL, 0x10u) )
        v31 = -2147212532;
      v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
      v46 = L"CORCOORC";
      v47 = 0x1000001E5LL;
      v48 = 255;
      v50 = 0x1000000;
      memset_0(v49, 0, sizeof(v49));
      CVssFunctionTracer::Throw(v52, &v44, v31, L"Volume not supported");
    }
    CVssProviderManager::SetContextInternal((CVssSnapshotSetObject *)((char *)*v22 + 8), *((_DWORD *)v29 + 38));
    v43 = *a3;
    v32 = CVssSnapshotSetObject::AddToSnapshotSet(*v22, a2, &v43, v16);
    v53 = v32;
    if ( v32 < 0 )
    {
      v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
      v46 = L"CORCOORC";
      v47 = 0x1000001F3LL;
      v48 = 255;
      v50 = 0x1000000;
      memset_0(v49, 0, sizeof(v49));
      LODWORD(v36) = v32;
      CVssFunctionTracer::Throw(v52, &v44, (unsigned int)v32, L"Internal AddToSnapshotSet failed. 0x%08lx", v36);
    }
    CVssAutomaticLock2::~CVssAutomaticLock2((CVssAutomaticLock2 *)&v78);
  }
  catch ( long v77 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)v52,
      v77,
      L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
      L"CORCOORC",
      L"CVssCoordinator::AddToSnapshotSet",
      0x1FDu,
      HIDWORD(v56));
  }
  catch ( _com_error *v80 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)v52,
      v80,
      L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
      L"CORCOORC",
      L"CVssCoordinator::AddToSnapshotSet",
      0x1FDu,
      HIDWORD(v56));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)v52,
      L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
      L"CORCOORC",
      L"CVssCoordinator::AddToSnapshotSet",
      0x1FDu,
      HIDWORD(v56));
  }
  catch ( const std::exception *v81 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)v52,
      v81,
      L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
      L"CORCOORC",
      L"CVssCoordinator::AddToSnapshotSet",
      0x1FDu,
      HIDWORD(v56));
  }
  if ( !HasPrivilege((unsigned int)v11, v10) && !IsInGroup(0x227u, v13) && !IsInGroup(0x220u, v14) )
  {
    v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
    v46 = L"CORCOORC";
    v47 = 0x1000001C1LL;
    v48 = 255;
    v50 = 0x1000000;
    memset_0(v49, 0, sizeof(v49));
    CVssFunctionTracer::Throw(
      v52,
      &v44,
      2147942405LL,
      L"The client process is not running under an administrator account or does not have backup privilege enabled");
  }
  v44 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v45 = (wchar_t *)L"CVssCoordinator::AddToSnapshotSet";
}

```

## disassembly

```asm
0x140002270  push    rbx
0x140002272  push    rsi
0x140002273  push    rdi
0x140002274  push    r12
0x140002276  push    r13
0x140002278  push    r14
0x14000227a  push    r15
0x14000227c  sub     rsp, 2C0h
0x140002283  mov     rax, cs:__security_cookie
0x14000228a  xor     rax, rsp
0x14000228d  mov     [rsp+2F8h+var_40], rax
0x140002295  mov     rdi, r9
0x140002298  mov     [rsp+2F8h+var_270], r9
0x1400022a0  mov     r13, r8
0x1400022a3  mov     r12, rdx
0x1400022a6  mov     [rsp+2F8h+var_1B0], rcx
0x1400022ae  xor     esi, esi
0x1400022b0  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x1400022b7  mov     [rsp+2F8h+var_138], rax
0x1400022bf  lea     rax, aCvsscoordinato_37; "CVssCoordinator::AddToSnapshotSet"
0x1400022c6  mov     [rsp+2F8h+var_130], rax
0x1400022ce  lea     rax, aCorcoorc; "CORCOORC"
0x1400022d5  mov     [rsp+2F8h+var_128], rax
0x1400022dd  mov     dword ptr [rsp+2F8h+var_120], 1B5h
0x1400022e8  mov     dword ptr [rsp+2F8h+var_120+4], 1
0x1400022f3  mov     dword ptr [rsp+2F8h+var_118], 0FFh
0x1400022fe  mov     [rsp+2F8h+var_98], 1000000h
0x140002309  xor     edx, edx; Val
0x14000230b  mov     r8d, 78h ; 'x'; Size
0x140002311  lea     rcx, [rsp+2F8h+pv]; void *
0x140002319  call    memset_0
0x14000231e  mov     [rsp+2F8h+var_1A0], esi
0x140002325  mov     rax, [rsp+2F8h+var_130]
0x14000232d  mov     [rsp+2F8h+var_180], rax
0x140002335  mov     rax, [rsp+2F8h+var_138]
0x14000233d  mov     [rsp+2F8h+var_198], rax
0x140002345  mov     rax, [rsp+2F8h+var_128]
0x14000234d  mov     [rsp+2F8h+var_190], rax
0x140002355  mov     eax, dword ptr [rsp+2F8h+var_120]
0x14000235c  mov     dword ptr [rsp+2F8h+var_188], eax
0x140002363  mov     eax, dword ptr [rsp+2F8h+var_120+4]
0x14000236a  mov     dword ptr [rsp+2F8h+var_188+4], eax
0x140002371  call    cs:__imp_GetTickCount
0x140002377  mov     [rsp+2F8h+var_174], eax
0x14000237e  mov     [rsp+2F8h+var_1A4], 0FFFFFFFFh
0x140002389  mov     eax, dword ptr [rsp+2F8h+var_118]
0x140002390  mov     [rsp+2F8h+var_170], eax
0x140002397  mov     [rsp+2F8h+var_1A8], esi
0x14000239e  mov     [rsp+2F8h+var_148], rsi
0x1400023a6  xorps   xmm0, xmm0
0x1400023a9  movdqa  [rsp+2F8h+var_168], xmm0
0x1400023b2  xorps   xmm1, xmm1
0x1400023b5  movdqa  [rsp+2F8h+var_158], xmm1
0x1400023be  mov     [rsp+2F8h+var_278], rsi
0x1400023c6  lea     rcx, [rsp+2F8h+var_278]
0x1400023ce  call    cs:__imp_VssGetTracingContextPerThread
0x1400023d4  test    eax, eax
0x1400023d6  js      short loc_1400023FC
0x1400023d8  lea     rcx, [rsp+2F8h+var_1A8]
0x1400023e0  call    cs:__imp_VssSetTracingContextPerThread
0x1400023e6  test    eax, eax
0x1400023e8  js      short loc_1400023FC
0x1400023ea  mov     rax, [rsp+2F8h+var_278]
0x1400023f2  mov     [rsp+2F8h+var_148], rax
0x1400023fa  jmp     short loc_140002404
0x1400023fc  mov     rax, [rsp+2F8h+var_148]
0x140002404  test    rax, rax
0x140002407  jz      short loc_140002417
0x140002409  mov     eax, [rax+30h]
0x14000240c  inc     eax
0x14000240e  mov     [rsp+2F8h+var_178], eax
0x140002415  jmp     short loc_14000241E
0x140002417  mov     [rsp+2F8h+var_178], esi
0x14000241e  mov     r14d, 0A0h
0x140002424  mov     ebx, r14d
0x140002427  cmp     [rsp+2F8h+var_170], 0FFh
0x140002432  cmovnz  ebx, [rsp+2F8h+var_170]
0x14000243a  mov     edx, dword ptr [rsp+2F8h+var_188+4]; unsigned int
0x140002441  lea     rcx, [rsp+2F8h+var_1A8]; this
0x140002449  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14000244e  lea     r15, aEnter; "ENTER"
0x140002455  test    eax, eax
0x140002457  jz      short loc_1400024A5
0x140002459  mov     [rsp+2F8h+var_2B8], rsi
0x14000245e  mov     dword ptr [rsp+2F8h+var_2C0], ebx
0x140002462  mov     [rsp+2F8h+var_2C8], r15
0x140002467  mov     rax, [rsp+2F8h+var_180]
0x14000246f  mov     [rsp+2F8h+var_2D0], rax
0x140002474  mov     eax, dword ptr [rsp+2F8h+var_188+4]
0x14000247b  mov     dword ptr [rsp+2F8h+var_2D8], eax
0x14000247f  mov     r9d, [rsp+2F8h+var_178]
0x140002487  mov     r8d, dword ptr [rsp+2F8h+var_188]
0x14000248f  mov     rdx, [rsp+2F8h+var_190]
0x140002497  mov     rcx, [rsp+2F8h+var_198]
0x14000249f  call    cs:__imp_VssTraceMessage
0x1400024a5  cmp     byte ptr [rsp+2F8h+var_98+3], sil
0x1400024ad  jz      short loc_1400024D6
0x1400024af  mov     rbx, rsi
0x1400024b2  mov     rcx, [rsp+rbx*8+2F8h+pv]; pv
0x1400024ba  test    rcx, rcx
0x1400024bd  jz      short loc_1400024CD
0x1400024bf  call    cs:__imp_CoTaskMemFree
0x1400024c5  mov     [rsp+rbx*8+2F8h+pv], rsi
0x1400024cd  inc     rbx
0x1400024d0  cmp     rbx, 0Fh
0x1400024d4  jnz     short loc_1400024B2
0x1400024d6  test    rdi, rdi
0x1400024d9  jz      short loc_1400024E5
0x1400024db  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400024e2  movups  xmmword ptr [rdi], xmm0
0x1400024e5  call    ?HasPrivilege@@YA_NK_N@Z; HasPrivilege(ulong,bool)
0x1400024ea  test    al, al
0x1400024ec  jnz     loc_1400025A6
0x1400024f2  mov     ecx, 227h; nSubAuthority1
0x1400024f7  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x1400024fc  test    al, al
0x1400024fe  jnz     loc_1400025A6
0x140002504  mov     ecx, 220h; nSubAuthority1
0x140002509  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x14000250e  test    al, al
0x140002510  jnz     loc_1400025A6
0x140002516  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14000251d  mov     [rsp+2F8h+var_258], rax
0x140002525  lea     rax, aCvsscoordinato_37; "CVssCoordinator::AddToSnapshotSet"
0x14000252c  mov     [rsp+2F8h+var_250], rax
0x140002534  lea     rax, aCorcoorc; "CORCOORC"
0x14000253b  mov     [rsp+2F8h+var_248], rax
0x140002543  mov     dword ptr [rsp+2F8h+var_240], 1C1h
0x14000254e  mov     dword ptr [rsp+2F8h+var_240+4], 1
0x140002559  mov     [rsp+2F8h+var_238], 0FFh
0x140002564  mov     [rsp+2F8h+var_1B8], 1000000h
0x14000256f  xor     edx, edx; Val
0x140002571  mov     r8d, 78h ; 'x'; Size
0x140002577  lea     rcx, [rsp+2F8h+var_230]; void *
0x14000257f  call    memset_0
0x140002584  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x14000258b  mov     r8d, 80070005h
0x140002591  lea     rdx, [rsp+2F8h+var_258]
0x140002599  lea     rcx, [rsp+2F8h+var_1A8]
0x1400025a1  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1400025a6  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x1400025ad  mov     [rsp+2F8h+var_258], rax
0x1400025b5  lea     rax, aCvsscoordinato_37; "CVssCoordinator::AddToSnapshotSet"
0x1400025bc  mov     [rsp+2F8h+var_250], rax
0x1400025c4  lea     rax, aCorcoorc; "CORCOORC"
0x1400025cb  mov     [rsp+2F8h+var_248], rax
0x1400025d3  mov     dword ptr [rsp+2F8h+var_240], 1C5h
0x1400025de  mov     dword ptr [rsp+2F8h+var_240+4], 1
0x1400025e9  mov     [rsp+2F8h+var_238], 0FFh
0x1400025f4  mov     [rsp+2F8h+var_1B8], 1000000h
0x1400025ff  xor     edx, edx; Val
0x140002601  mov     r8d, 78h ; 'x'; Size
0x140002607  lea     rcx, [rsp+2F8h+var_230]; void *
0x14000260f  call    memset_0
0x140002614  movzx   ecx, byte ptr [r13+0Eh]
0x140002619  movzx   edx, byte ptr [r13+0Dh]
0x14000261e  movzx   r8d, byte ptr [r13+0Ch]
0x140002623  movzx   r9d, byte ptr [r13+0Bh]
0x140002628  movzx   r10d, byte ptr [r13+0Ah]
0x14000262d  movzx   r11d, byte ptr [r13+9]
0x140002632  movzx   ebx, byte ptr [r13+8]
0x140002637  movzx   edi, word ptr [r13+6]
0x14000263c  movzx   esi, word ptr [r13+4]
0x140002641  mov     rax, [rsp+2F8h+var_270]
0x140002649  mov     [rsp+2F8h+var_280], rax
0x14000264e  movzx   eax, byte ptr [r13+0Fh]
0x140002653  mov     [rsp+2F8h+var_288], eax
0x140002657  mov     [rsp+2F8h+var_290], ecx
0x14000265b  mov     [rsp+2F8h+var_298], edx
0x14000265f  mov     [rsp+2F8h+var_2A0], r8d
0x140002664  mov     [rsp+2F8h+var_2A8], r9d
0x140002669  mov     [rsp+2F8h+var_2B0], r10d
0x14000266e  mov     dword ptr [rsp+2F8h+var_2B8], r11d
0x140002673  mov     dword ptr [rsp+2F8h+var_2C0], ebx
0x140002677  mov     dword ptr [rsp+2F8h+var_2C8], edi
0x14000267b  mov     dword ptr [rsp+2F8h+var_2D0], esi
0x14000267f  mov     eax, [r13+0]
0x140002683  mov     dword ptr [rsp+2F8h+var_2D8], eax
0x140002687  mov     r9, r12
0x14000268a  lea     r8, aParametersVolu; "Parameters: VolumeName = %s ProviderId "...
0x140002691  lea     rdx, [rsp+2F8h+var_258]
0x140002699  lea     rcx, [rsp+2F8h+var_1A8]
0x1400026a1  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400026a6  test    r12, r12
0x1400026a9  jz      loc_140002F3B
0x1400026af  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400026b6  nop     word ptr [rax+rax+00000000h]
0x1400026c0  inc     rax
0x1400026c3  cmp     word ptr [r12+rax*2], 0
0x1400026c9  jnz     short loc_1400026C0
0x1400026cb  test    rax, rax
0x1400026ce  jz      loc_140002F3B
0x1400026d4  mov     rsi, [rsp+2F8h+var_270]
0x1400026dc  mov     [rsp+2F8h+var_238], 0FFh
0x1400026e7  mov     [rsp+2F8h+var_1B8], 1000000h
0x1400026f2  xor     edx, edx; Val
0x1400026f4  mov     r8d, 78h ; 'x'; Size
0x1400026fa  lea     rcx, [rsp+2F8h+var_230]; void *
0x140002702  test    rsi, rsi
0x140002705  jnz     short loc_140002771
0x140002707  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14000270e  mov     [rsp+2F8h+var_258], rax
0x140002716  lea     rax, aCvsscoordinato_37; "CVssCoordinator::AddToSnapshotSet"
0x14000271d  mov     [rsp+2F8h+var_250], rax
0x140002725  lea     rax, aCorcoorc; "CORCOORC"
0x14000272c  mov     [rsp+2F8h+var_248], rax
0x140002734  mov     dword ptr [rsp+2F8h+var_240], 1CEh
0x14000273f  mov     dword ptr [rsp+2F8h+var_240+4], 1
0x14000274a  call    memset_0
0x14000274f  lea     r9, aNullPsnapshoti; "NULL pSnapshotId"
0x140002756  mov     r8d, 80070057h
0x14000275c  lea     rdx, [rsp+2F8h+var_258]
0x140002764  lea     rcx, [rsp+2F8h+var_1A8]
0x14000276c  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140002771  mov     rbx, [rsp+2F8h+var_1B0]
0x140002779  lea     rdi, [rbx+10h]
0x14000277d  mov     [rsp+2F8h+var_80], rdi
0x140002785  mov     [rsp+2F8h+var_78], 0
0x14000278d  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x140002794  mov     [rsp+2F8h+var_258], rax
0x14000279c  lea     rax, aCvssautomaticl_0; "CVssAutomaticLock2::CVssAutomaticLock2"
0x1400027a3  mov     [rsp+2F8h+var_250], rax
0x1400027ab  lea     rax, aInctypeh; "INCTYPEH"
0x1400027b2  mov     [rsp+2F8h+var_248], rax
0x1400027ba  mov     dword ptr [rsp+2F8h+var_240], 100h
0x1400027c5  mov     dword ptr [rsp+2F8h+var_240+4], 0Bh
0x1400027d0  call    memset_0
0x1400027d5  mov     dword ptr [rsp+2F8h+var_130], 0
0x1400027e0  mov     rax, [rsp+2F8h+var_250]
0x1400027e8  mov     [rsp+2F8h+pv], rax
0x1400027f0  mov     rax, [rsp+2F8h+var_258]
0x1400027f8  mov     [rsp+2F8h+var_128], rax
0x140002800  mov     rax, [rsp+2F8h+var_248]
0x140002808  mov     [rsp+2F8h+var_120], rax
0x140002810  mov     eax, dword ptr [rsp+2F8h+var_240]
0x140002817  mov     dword ptr [rsp+2F8h+var_118], eax
0x14000281e  mov     eax, dword ptr [rsp+2F8h+var_240+4]
0x140002825  mov     dword ptr [rsp+2F8h+var_118+4], eax
0x14000282c  call    cs:__imp_GetTickCount
0x140002832  mov     [rsp+2F8h+var_104], eax
0x140002839  mov     dword ptr [rsp+2F8h+var_138+4], 0FFFFFFFFh
0x140002844  mov     eax, [rsp+2F8h+var_238]
0x14000284b  mov     [rsp+2F8h+var_100], eax
0x140002852  xor     eax, eax
0x140002854  mov     dword ptr [rsp+2F8h+var_138], eax
0x14000285b  mov     [rsp+2F8h+var_D8], rax
0x140002863  xorps   xmm0, xmm0
0x140002866  movdqa  [rsp+2F8h+var_F8], xmm0
0x14000286f  xorps   xmm1, xmm1
0x140002872  movdqa  [rsp+2F8h+var_E8], xmm1
0x14000287b  mov     [rsp+2F8h+var_270], rax
0x140002883  lea     rcx, [rsp+2F8h+var_270]
0x14000288b  call    cs:__imp_VssGetTracingContextPerThread
0x140002891  test    eax, eax
0x140002893  js      short loc_1400028B9
0x140002895  lea     rcx, [rsp+2F8h+var_138]
0x14000289d  call    cs:__imp_VssSetTracingContextPerThread
0x1400028a3  test    eax, eax
0x1400028a5  js      short loc_1400028B9
0x1400028a7  mov     rax, [rsp+2F8h+var_270]
0x1400028af  mov     [rsp+2F8h+var_D8], rax
0x1400028b7  jmp     short loc_1400028C1
0x1400028b9  mov     rax, [rsp+2F8h+var_D8]
0x1400028c1  test    rax, rax
0x1400028c4  jz      short loc_1400028D4
0x1400028c6  mov     eax, [rax+30h]
0x1400028c9  inc     eax
0x1400028cb  mov     [rsp+2F8h+var_108], eax
0x1400028d2  jmp     short loc_1400028DF
0x1400028d4  mov     [rsp+2F8h+var_108], 0
0x1400028df  cmp     [rsp+2F8h+var_100], 0FFh
0x1400028ea  cmovnz  r14d, [rsp+2F8h+var_100]
0x1400028f3  mov     edx, dword ptr [rsp+2F8h+var_118+4]; unsigned int
0x1400028fa  lea     rcx, [rsp+2F8h+var_138]; this
0x140002902  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140002907  test    eax, eax
0x140002909  jz      short loc_14000295C
0x14000290b  mov     [rsp+2F8h+var_2B8], 0
0x140002914  mov     dword ptr [rsp+2F8h+var_2C0], r14d
0x140002919  mov     [rsp+2F8h+var_2C8], r15
0x14000291e  mov     rax, [rsp+2F8h+pv]
0x140002926  mov     [rsp+2F8h+var_2D0], rax
0x14000292b  mov     eax, dword ptr [rsp+2F8h+var_118+4]
0x140002932  mov     dword ptr [rsp+2F8h+var_2D8], eax
0x140002936  mov     r9d, [rsp+2F8h+var_108]
0x14000293e  mov     r8d, dword ptr [rsp+2F8h+var_118]
0x140002946  mov     rdx, [rsp+2F8h+var_120]
0x14000294e  mov     rcx, [rsp+2F8h+var_128]
0x140002956  call    cs:__imp_VssTraceMessage
0x14000295c  xor     r15d, r15d
0x14000295f  cmp     byte ptr [rsp+2F8h+var_1B8+3], r15b
0x140002967  jz      short loc_14000299C
0x140002969  mov     ebx, r15d
0x14000296c  nop     dword ptr [rax+00h]
0x140002970  mov     rcx, [rsp+rbx*8+2F8h+var_230]; pv
0x140002978  test    rcx, rcx
0x14000297b  jz      short loc_14000298B
0x14000297d  call    cs:__imp_CoTaskMemFree
0x140002983  mov     [rsp+rbx*8+2F8h+var_230], r15
0x14000298b  inc     rbx
  ... truncated ...
```
