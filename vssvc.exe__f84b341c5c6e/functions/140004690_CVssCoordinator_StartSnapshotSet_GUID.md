# CVssCoordinator::StartSnapshotSet(_GUID *)

- ea: `0x140004690`
- end: `0x14000503b`
- name: `?StartSnapshotSet@CVssCoordinator@@UEAAJPEAU_GUID@@@Z`
- size: `2475`
- prototype: `__int64 __fastcall(CVssCoordinator *this, struct _GUID *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140003014`
- `0x140003320`
- `0x140004690`
- `0x140006020`
- `0x140007060`
- `0x140011440`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140013d30`
- `0x140015e38`
- `0x140016710`
- `0x140019990`
- `0x140019bf0`
- `0x1400272d8`
- `0x140030230`
- `0x140046a64`
- `0x14004ee3c`
- `0x1400518bc`
- `0x140091560`
- `0x1400921dc`
- `0x140099808`
- `0x1400da314`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140004782`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140004d7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140004782`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140004d7e`
- `VssTrace!__imp_VssTraceMessage` at `0x1400048a0`
- `VssTrace!__imp_VssTraceMessage` at `0x140004e97`
- `VssTrace!__imp_VssTraceMessage` at `0x1400048a0`
- `VssTrace!__imp_VssTraceMessage` at `0x140004e97`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400047e6`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140004de1`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400047e6`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140004de1`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400047d4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140004dcf`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400047d4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140004dcf`

## string_xrefs

- `0x140004949`: `The client process is not running under an administrator account or does not have backup privilege enabled`
- `0x140004fd2`: `Bad state: attempting to create snapshots in wrong context %ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CVssCoordinator::StartSnapshotSet(CVssCoordinator *this, struct _GUID *a2)
{
  int v4; // eax
  const unsigned __int16 **v5; // rcx
  int v6; // r12d
  int v7; // ebx
  bool v8; // dl
  unsigned int v9; // ecx
  bool v10; // dl
  bool v11; // dl
  unsigned int v12; // eax
  int v13; // ecx
  __int64 v14; // rcx
  _QWORD *v15; // rbx
  CVssSnapshotSetObject **v16; // rbx
  struct CVssSnapshotSetObject *Instance; // rax
  __int64 v18; // rdi
  int v19; // r15d
  int v20; // eax
  const unsigned __int16 **v21; // rcx
  int started; // ebx
  int v23; // ebx
  unsigned int v24; // ebx
  __int64 v26; // [rsp+20h] [rbp-288h]
  __int64 v27; // [rsp+20h] [rbp-288h]
  const unsigned __int16 **v28; // [rsp+50h] [rbp-258h] BYREF
  const unsigned __int16 *v29; // [rsp+58h] [rbp-250h] BYREF
  const wchar_t *v30; // [rsp+60h] [rbp-248h]
  const unsigned __int16 *v31; // [rsp+68h] [rbp-240h]
  __int64 v32; // [rsp+70h] [rbp-238h]
  int v33; // [rsp+78h] [rbp-230h]
  _BYTE v34[120]; // [rsp+80h] [rbp-228h] BYREF
  int v35; // [rsp+F8h] [rbp-1B0h]
  _DWORD v36[2]; // [rsp+100h] [rbp-1A8h] BYREF
  int v37; // [rsp+108h] [rbp-1A0h]
  const unsigned __int16 *v38; // [rsp+110h] [rbp-198h]
  const unsigned __int16 *v39; // [rsp+118h] [rbp-190h]
  __int64 v40; // [rsp+120h] [rbp-188h]
  const unsigned __int16 *v41; // [rsp+128h] [rbp-180h]
  unsigned int v42; // [rsp+130h] [rbp-178h]
  DWORD TickCount; // [rsp+134h] [rbp-174h]
  int v44; // [rsp+138h] [rbp-170h]
  __int128 v45; // [rsp+140h] [rbp-168h]
  __int128 v46; // [rsp+150h] [rbp-158h]
  const unsigned __int16 **v47; // [rsp+160h] [rbp-148h]
  const unsigned __int16 *v48; // [rsp+170h] [rbp-138h] BYREF
  const unsigned __int16 *v49; // [rsp+178h] [rbp-130h]
  const unsigned __int16 *v50; // [rsp+180h] [rbp-128h]
  __int64 v51; // [rsp+188h] [rbp-120h]
  __int64 v52; // [rsp+190h] [rbp-118h]
  const wchar_t *Src; // [rsp+198h] [rbp-110h] BYREF
  unsigned int v54; // [rsp+1A0h] [rbp-108h]
  DWORD v55; // [rsp+1A4h] [rbp-104h]
  int v56; // [rsp+1A8h] [rbp-100h]
  __int128 v57; // [rsp+1B0h] [rbp-F8h]
  __int128 v58; // [rsp+1C0h] [rbp-E8h]
  const unsigned __int16 **v59; // [rsp+1D0h] [rbp-D8h]
  int v60; // [rsp+210h] [rbp-98h]
  int v61; // [rsp+228h] [rbp-80h] BYREF
  _com_error *v62; // [rsp+230h] [rbp-78h] BYREF
  const std::exception *v63; // [rsp+238h] [rbp-70h] BYREF
  _BYTE v64[16]; // [rsp+240h] [rbp-68h] BYREF
  _QWORD v65[2]; // [rsp+250h] [rbp-58h] BYREF
  __m128i si128; // [rsp+260h] [rbp-48h]

  v48 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v49 = L"CVssCoordinator::StartSnapshotSet";
  v50 = L"CORCOORC";
  v51 = 0x100000099LL;
  LODWORD(v52) = 255;
  v60 = 0x1000000;
  memset_0(&Src, 0, 0x78u);
  v37 = 0;
  v41 = L"CVssCoordinator::StartSnapshotSet";
  v38 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v39 = L"CORCOORC";
  v40 = 0x100000099LL;
  TickCount = GetTickCount();
  v36[1] = -1;
  v44 = 255;
  v36[0] = 0;
  v47 = 0;
  v45 = 0;
  v46 = 0;
  v28 = 0;
  if ( (int)VssGetTracingContextPerThread(&v28) < 0 )
  {
    v5 = v47;
  }
  else
  {
    v4 = VssSetTracingContextPerThread(v36);
    v5 = v47;
    if ( v4 >= 0 )
      v5 = v28;
    v47 = v5;
  }
  if ( v5 )
    v42 = *((_DWORD *)v5 + 12) + 1;
  else
    v42 = 0;
  v6 = 160;
  v7 = 160;
  if ( v44 != 255 )
    v7 = v44;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v36) )
    VssTraceMessage(v38, v39, (unsigned int)v40, v42, HIDWORD(v40), v41, L"ENTER", v7, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v48);
  if ( a2 )
    *a2 = GUID_NULL;
  try
  {
    if ( !HasPrivilege(v9, v8) && !IsInGroup(0x227u, v10) && !IsInGroup(0x220u, v11) )
    {
      v29 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v30 = L"CVssCoordinator::StartSnapshotSet";
      v31 = L"CORCOORC";
      v32 = 0x1000000A2LL;
      v33 = 255;
      v35 = 0x1000000;
      memset_0(v34, 0, sizeof(v34));
      CVssFunctionTracer::Throw(
        v36,
        &v29,
        2147942405LL,
        L"The client process is not running under an administrator account or does not have backup privilege enabled");
    }
    v29 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v30 = L"CVssCoordinator::StartSnapshotSet";
    v31 = L"CORCOORC";
    v32 = 0x1000000A6LL;
    v33 = 255;
    v35 = 0x1000000;
    memset_0(v34, 0, sizeof(v34));
    CVssFunctionTracer::Trace(v36, &v29, L"Parameters: pSnapshotSetId = %p", a2);
    if ( !a2 )
    {
      v29 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v30 = L"CVssCoordinator::StartSnapshotSet";
      v31 = L"CORCOORC";
      v32 = 0x1000000ABLL;
      v33 = 255;
      v35 = 0x1000000;
      memset_0(v34, 0, sizeof(v34));
      CVssFunctionTracer::Throw(v36, &v29, 2147942487LL, L"NULL pSnapshotSetId");
    }
    CVssAutomaticLock2::CVssAutomaticLock2((CVssAutomaticLock2 *)v64, (CVssCoordinator *)((char *)this + 16));
    v12 = *((_DWORD *)this + 38) & 0xF939FF5D;
    if ( v12 > 0x1D || (v13 = 570499585, !_bittest(&v13, v12)) )
    {
      v23 = *((_DWORD *)this + 38);
      v29 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v30 = L"CVssCoordinator::StartSnapshotSet";
      v31 = L"CORCOORC";
      v32 = 0x1000000B2LL;
      v33 = 255;
      v35 = 0x1000000;
      memset_0(v34, 0, sizeof(v34));
      LODWORD(v26) = v23;
      CVssFunctionTracer::Throw(
        v36,
        &v29,
        2147754753LL,
        L"Bad state: attempting to create snapshots in wrong context %ld",
        v26);
    }
    v29 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v30 = L"CVssCoordinator::StartSnapshotSet";
    v31 = L"CORCOORC";
    v32 = 0xD000000B5LL;
    v33 = 255;
    v35 = 0x1000000;
    memset_0(v34, 0, sizeof(v34));
    CVssFunctionTracer::AddOperation(v36, &v29, 302);
    v48 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v49 = L"CVssCoordinator::StartSnapshotSet";
    v50 = L"CORCOORC";
    v51 = 0xD000000B6LL;
    LODWORD(v52) = 255;
    v60 = 0x1000000;
    memset_0(&Src, 0, 0x78u);
    v28 = &v48;
    CVssResource::LoadStringW(v14, v65, 5012);
    v15 = v65;
    if ( si128.m128i_i64[1] > 7uLL )
      v15 = (_QWORD *)v65[0];
    v29 = v48;
    v31 = v50;
    v30 = v49;
    v32 = v51;
    v35 = v60;
    v33 = v52;
    HIBYTE(v60) = 0;
    memcpy_0(v34, &Src, sizeof(v34));
    CVssFunctionTracer::AddContextInternal(v36, &v29, 2, v15, L"Coordinator");
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v65[0], 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v65[0]) = 0;
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v48);
    v16 = (CVssSnapshotSetObject **)((char *)this + 120);
    if ( (unsigned __int8)ATL::CComPtrBase<IXMLDOMNode>::operator==((char *)this + 120, 0) )
    {
      Instance = CVssSnapshotSetObject::CreateInstance();
      ATL::CComPtr<IVssSnapshotSetDescription>::operator=((char *)this + 120, Instance);
    }
    CVssCoordinator::PreFreezeContext(this);
    v18 = ATL::CComPtrBase<IGlobalInterfaceTable>::operator->((char *)this + 120);
    v19 = *((_DWORD *)this + 38);
    v29 = L"base\\stor\\vss\\modules\\coord\\src\\provmgr.cxx";
    v30 = L"CVssProviderManager::SetContextInternal";
    v31 = L"CORPRVMC";
    v32 = 0x1000006FELL;
    v33 = 255;
    v35 = 0x1000000;
    memset_0(v34, 0, sizeof(v34));
    LODWORD(v49) = 0;
    Src = v30;
    v50 = v29;
    v51 = (__int64)v31;
    v52 = v32;
    v55 = GetTickCount();
    v56 = v33;
    v48 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
    v59 = 0;
    v57 = 0;
    v58 = 0;
    v28 = 0;
    if ( (int)VssGetTracingContextPerThread(&v28) < 0 )
    {
      v21 = v59;
    }
    else
    {
      v20 = VssSetTracingContextPerThread(&v48);
      v21 = v59;
      if ( v20 >= 0 )
        v21 = v28;
      v59 = v21;
    }
    if ( v21 )
      v54 = *((_DWORD *)v21 + 12) + 1;
    else
      v54 = 0;
    if ( v56 != 255 )
      v6 = v56;
    if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v48) )
      VssTraceMessage(v50, v51, (unsigned int)v52, v54, HIDWORD(v52), Src, L"ENTER", v6, 0);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v29);
    *(_DWORD *)(v18 + 64) = v19;
    *(_BYTE *)(v18 + 68) = 1;
    CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)&v48);
    *((_BYTE *)*v16 + 2540) = *((_BYTE *)this + 304);
    started = CVssSnapshotSetObject::StartSnapshotSet(*v16, a2);
    v37 = started;
    if ( started < 0 )
    {
      v29 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v30 = L"CVssCoordinator::StartSnapshotSet";
      v31 = L"CORCOORC";
      v32 = 0x1000000C7LL;
      v33 = 255;
      v35 = 0x1000000;
      memset_0(v34, 0, sizeof(v34));
      LODWORD(v27) = started;
      CVssFunctionTracer::Throw(v36, &v29, (unsigned int)started, L"Internal StartSnapshotSet failed. 0x%08lx", v27);
    }
    CVssAutomaticLock2::~CVssAutomaticLock2((CVssAutomaticLock2 *)v64);
  }
  catch ( long v61 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)v36,
      v61,
      L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
      L"CORCOORC",
      L"CVssCoordinator::StartSnapshotSet",
      0xCAu,
      HIDWORD(v40));
  }
  catch ( _com_error *v62 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)v36,
      v62,
      L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
      L"CORCOORC",
      L"CVssCoordinator::StartSnapshotSet",
      0xCAu,
      HIDWORD(v40));
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)v36,
      L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
      L"CORCOORC",
      L"CVssCoordinator::StartSnapshotSet",
      0xCAu,
      HIDWORD(v40));
  }
  catch ( const std::exception *v63 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)v36,
      v63,
      L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
      L"CORCOORC",
      L"CVssCoordinator::StartSnapshotSet",
      0xCAu,
      HIDWORD(v40));
  }
  if ( !HasPrivilege(v9, v8) && !IsInGroup(0x227u, v10) && !IsInGroup(0x220u, v11) )
  {
    v29 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
    v30 = L"CVssCoordinator::StartSnapshotSet";
    v31 = L"CORCOORC";
    v32 = 0x1000000A2LL;
    v33 = 255;
    v35 = 0x1000000;
    memset_0(v34, 0, sizeof(v34));
    CVssFunctionTracer::Throw(
      v36,
      &v29,
      2147942405LL,
      L"The client process is not running under an administrator account or does not have backup privilege enabled");
  }
  v29 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v30 = L"CVssCoordinator::StartSnapshotSet";
}

```

## disassembly

```asm
0x140004690  mov     r11, rsp
0x140004693  mov     [r11+18h], rbx
0x140004697  mov     [r11+20h], rsi
0x14000469b  push    rdi
0x14000469c  push    r12
0x14000469e  push    r13
0x1400046a0  push    r14
0x1400046a2  push    r15
0x1400046a4  sub     rsp, 280h
0x1400046ab  mov     rax, cs:__security_cookie
0x1400046b2  xor     rax, rsp
0x1400046b5  mov     [rsp+2A8h+var_38], rax
0x1400046bd  mov     r14, rdx
0x1400046c0  mov     rsi, rcx
0x1400046c3  xor     edi, edi
0x1400046c5  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x1400046cc  mov     [r11-138h], rax
0x1400046d3  lea     rax, aCvsscoordinato_48; "CVssCoordinator::StartSnapshotSet"
0x1400046da  mov     [r11-130h], rax
0x1400046e1  lea     rax, aCorcoorc; "CORCOORC"
0x1400046e8  mov     [r11-128h], rax
0x1400046ef  mov     dword ptr [rsp+2A8h+var_120], 99h
0x1400046fa  lea     r15d, [rdi+1]
0x1400046fe  mov     [r11-11Ch], r15d
0x140004705  mov     r13d, 0FFh
0x14000470b  mov     [r11-118h], r13d
0x140004712  mov     [rsp+2A8h+var_98], 1000000h
0x14000471d  xor     edx, edx; Val
0x14000471f  lea     r8d, [rdi+78h]; Size
0x140004723  lea     rcx, [r11-110h]; void *
0x14000472a  call    memset_0
0x14000472f  mov     [rsp+2A8h+var_1A0], edi
0x140004736  mov     rax, [rsp+2A8h+var_130]
0x14000473e  mov     [rsp+2A8h+var_180], rax
0x140004746  mov     rax, [rsp+2A8h+var_138]
0x14000474e  mov     [rsp+2A8h+var_198], rax
0x140004756  mov     rax, [rsp+2A8h+var_128]
0x14000475e  mov     [rsp+2A8h+var_190], rax
0x140004766  mov     eax, dword ptr [rsp+2A8h+var_120]
0x14000476d  mov     dword ptr [rsp+2A8h+var_188], eax
0x140004774  mov     eax, dword ptr [rsp+2A8h+var_120+4]
0x14000477b  mov     dword ptr [rsp+2A8h+var_188+4], eax
0x140004782  call    cs:__imp_GetTickCount
0x140004788  mov     [rsp+2A8h+var_174], eax
0x14000478f  mov     [rsp+2A8h+var_1A4], 0FFFFFFFFh
0x14000479a  mov     eax, dword ptr [rsp+2A8h+var_118]
0x1400047a1  mov     [rsp+2A8h+var_170], eax
0x1400047a8  mov     [rsp+2A8h+var_1A8], edi
0x1400047af  mov     [rsp+2A8h+var_148], rdi
0x1400047b7  xorps   xmm0, xmm0
0x1400047ba  movups  [rsp+2A8h+var_168], xmm0
0x1400047c2  movups  [rsp+2A8h+var_158], xmm0
0x1400047ca  mov     [rsp+2A8h+var_258], rdi
0x1400047cf  lea     rcx, [rsp+2A8h+var_258]
0x1400047d4  call    cs:__imp_VssGetTracingContextPerThread
0x1400047da  test    eax, eax
0x1400047dc  js      short loc_140004806
0x1400047de  lea     rcx, [rsp+2A8h+var_1A8]
0x1400047e6  call    cs:__imp_VssSetTracingContextPerThread
0x1400047ec  mov     rcx, [rsp+2A8h+var_148]
0x1400047f4  test    eax, eax
0x1400047f6  cmovns  rcx, [rsp+2A8h+var_258]
0x1400047fc  mov     [rsp+2A8h+var_148], rcx
0x140004804  jmp     short loc_14000480E
0x140004806  mov     rcx, [rsp+2A8h+var_148]
0x14000480e  test    rcx, rcx
0x140004811  jz      short loc_140004822
0x140004813  mov     eax, [rcx+30h]
0x140004816  add     eax, r15d
0x140004819  mov     [rsp+2A8h+var_178], eax
0x140004820  jmp     short loc_140004829
0x140004822  mov     [rsp+2A8h+var_178], edi
0x140004829  mov     r12d, 0A0h
0x14000482f  mov     ebx, r12d
0x140004832  cmp     [rsp+2A8h+var_170], r13d
0x14000483a  cmovnz  ebx, [rsp+2A8h+var_170]
0x140004842  lea     rcx, [rsp+2A8h+var_1A8]; this
0x14000484a  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14000484f  lea     r13, aEnter; "ENTER"
0x140004856  test    eax, eax
0x140004858  jz      short loc_1400048A6
0x14000485a  mov     [rsp+2A8h+var_268], rdi
0x14000485f  mov     [rsp+2A8h+var_270], ebx
0x140004863  mov     [rsp+2A8h+var_278], r13
0x140004868  mov     rax, [rsp+2A8h+var_180]
0x140004870  mov     [rsp+2A8h+var_280], rax
0x140004875  mov     eax, dword ptr [rsp+2A8h+var_188+4]
0x14000487c  mov     dword ptr [rsp+2A8h+var_288], eax
0x140004880  mov     r9d, [rsp+2A8h+var_178]
0x140004888  mov     r8d, dword ptr [rsp+2A8h+var_188]
0x140004890  mov     rdx, [rsp+2A8h+var_190]
0x140004898  mov     rcx, [rsp+2A8h+var_198]
0x1400048a0  call    cs:__imp_VssTraceMessage
0x1400048a6  lea     rcx, [rsp+2A8h+var_138]; this
0x1400048ae  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x1400048b3  nop
0x1400048b4  test    r14, r14
0x1400048b7  jz      short loc_1400048C5
0x1400048b9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400048c0  movdqu  xmmword ptr [r14], xmm0
0x1400048c5  call    ?HasPrivilege@@YA_NK_N@Z; HasPrivilege(ulong,bool)
0x1400048ca  test    al, al
0x1400048cc  jnz     loc_140004968
0x1400048d2  mov     ecx, 227h; nSubAuthority1
0x1400048d7  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x1400048dc  test    al, al
0x1400048de  jnz     loc_140004968
0x1400048e4  mov     ecx, 220h; nSubAuthority1
0x1400048e9  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x1400048ee  test    al, al
0x1400048f0  jnz     short loc_140004968
0x1400048f2  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x1400048f9  mov     [rsp+2A8h+var_250], rax
0x1400048fe  lea     rax, aCvsscoordinato_48; "CVssCoordinator::StartSnapshotSet"
0x140004905  mov     [rsp+2A8h+var_248], rax
0x14000490a  lea     rax, aCorcoorc; "CORCOORC"
0x140004911  mov     [rsp+2A8h+var_240], rax
0x140004916  mov     dword ptr [rsp+2A8h+var_238], 0A2h
0x14000491e  mov     dword ptr [rsp+2A8h+var_238+4], r15d
0x140004923  mov     [rsp+2A8h+var_230], 0FFh
0x14000492b  mov     [rsp+2A8h+var_1B0], 1000000h
0x140004936  xor     edx, edx; Val
0x140004938  lea     r8d, [rdx+78h]; Size
0x14000493c  lea     rcx, [rsp+2A8h+var_228]; void *
0x140004944  call    memset_0
0x140004949  lea     r9, aTheClientProce_0; "The client process is not running under"...
0x140004950  mov     r8d, 80070005h
0x140004956  lea     rdx, [rsp+2A8h+var_250]
0x14000495b  lea     rcx, [rsp+2A8h+var_1A8]
0x140004963  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140004968  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14000496f  mov     [rsp+2A8h+var_250], rax
0x140004974  lea     rax, aCvsscoordinato_48; "CVssCoordinator::StartSnapshotSet"
0x14000497b  mov     [rsp+2A8h+var_248], rax
0x140004980  lea     rax, aCorcoorc; "CORCOORC"
0x140004987  mov     [rsp+2A8h+var_240], rax
0x14000498c  mov     dword ptr [rsp+2A8h+var_238], 0A6h
0x140004994  mov     dword ptr [rsp+2A8h+var_238+4], r15d
0x140004999  mov     ebx, 0FFh
0x14000499e  mov     [rsp+2A8h+var_230], ebx
0x1400049a2  mov     [rsp+2A8h+var_1B0], 1000000h
0x1400049ad  xor     edx, edx; Val
0x1400049af  lea     r8d, [rdx+78h]; Size
0x1400049b3  lea     rcx, [rsp+2A8h+var_228]; void *
0x1400049bb  call    memset_0
0x1400049c0  mov     r9, r14
0x1400049c3  lea     r8, aParametersPsna; "Parameters: pSnapshotSetId = %p"
0x1400049ca  lea     rdx, [rsp+2A8h+var_250]
0x1400049cf  lea     rcx, [rsp+2A8h+var_1A8]
0x1400049d7  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400049dc  test    r14, r14
0x1400049df  jnz     short loc_140004A53
0x1400049e1  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x1400049e8  mov     [rsp+2A8h+var_250], rax
0x1400049ed  lea     rax, aCvsscoordinato_48; "CVssCoordinator::StartSnapshotSet"
0x1400049f4  mov     [rsp+2A8h+var_248], rax
0x1400049f9  lea     rax, aCorcoorc; "CORCOORC"
0x140004a00  mov     [rsp+2A8h+var_240], rax
0x140004a05  mov     dword ptr [rsp+2A8h+var_238], 0ABh
0x140004a0d  mov     dword ptr [rsp+2A8h+var_238+4], r15d
0x140004a12  mov     [rsp+2A8h+var_230], ebx
0x140004a16  mov     [rsp+2A8h+var_1B0], 1000000h
0x140004a21  xor     edx, edx; Val
0x140004a23  lea     r8d, [r14+78h]; Size
0x140004a27  lea     rcx, [rsp+2A8h+var_228]; void *
0x140004a2f  call    memset_0
0x140004a34  lea     r9, aNullPsnapshots; "NULL pSnapshotSetId"
0x140004a3b  mov     r8d, 80070057h
0x140004a41  lea     rdx, [rsp+2A8h+var_250]
0x140004a46  lea     rcx, [rsp+2A8h+var_1A8]
0x140004a4e  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140004a53  lea     rdx, [rsi+10h]; struct CVssCriticalSection *
0x140004a57  lea     rcx, [rsp+2A8h+var_68]; this
0x140004a5f  call    ??0CVssAutomaticLock2@@QEAA@AEAVCVssCriticalSection@@@Z; CVssAutomaticLock2::CVssAutomaticLock2(CVssCriticalSection &)
0x140004a64  nop
0x140004a65  mov     eax, [rsi+98h]
0x140004a6b  and     eax, 0F939FF5Dh
0x140004a70  cmp     eax, 1Dh
0x140004a73  ja      loc_140004F71
0x140004a79  mov     ecx, 22012201h
0x140004a7e  bt      ecx, eax
0x140004a81  jnb     loc_140004F71
0x140004a87  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x140004a8e  mov     [rsp+2A8h+var_250], rax
0x140004a93  lea     rax, aCvsscoordinato_48; "CVssCoordinator::StartSnapshotSet"
0x140004a9a  mov     [rsp+2A8h+var_248], rax
0x140004a9f  lea     rax, aCorcoorc; "CORCOORC"
0x140004aa6  mov     [rsp+2A8h+var_240], rax
0x140004aab  mov     dword ptr [rsp+2A8h+var_238], 0B5h
0x140004ab3  mov     dword ptr [rsp+2A8h+var_238+4], 0Dh
0x140004abb  mov     [rsp+2A8h+var_230], ebx
0x140004abf  mov     [rsp+2A8h+var_1B0], 1000000h
0x140004aca  xor     edx, edx; Val
0x140004acc  lea     r8d, [rdx+78h]; Size
0x140004ad0  lea     rcx, [rsp+2A8h+var_228]; void *
0x140004ad8  call    memset_0
0x140004add  mov     r8d, 12Eh
0x140004ae3  lea     rdx, [rsp+2A8h+var_250]
0x140004ae8  lea     rcx, [rsp+2A8h+var_1A8]
0x140004af0  call    ?AddOperation@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@IZZ; CVssFunctionTracer::AddOperation(CVssDebugInfo,uint,...)
0x140004af5  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x140004afc  mov     [rsp+2A8h+var_138], rax
0x140004b04  lea     rax, aCvsscoordinato_48; "CVssCoordinator::StartSnapshotSet"
0x140004b0b  mov     [rsp+2A8h+var_130], rax
0x140004b13  lea     rax, aCorcoorc; "CORCOORC"
0x140004b1a  mov     [rsp+2A8h+var_128], rax
0x140004b22  mov     dword ptr [rsp+2A8h+var_120], 0B6h
0x140004b2d  mov     dword ptr [rsp+2A8h+var_120+4], 0Dh
0x140004b38  mov     dword ptr [rsp+2A8h+var_118], ebx
0x140004b3f  mov     [rsp+2A8h+var_98], 1000000h
0x140004b4a  mov     r15d, 78h ; 'x'
0x140004b50  mov     r8d, r15d; Size
0x140004b53  xor     edx, edx; Val
0x140004b55  lea     rcx, [rsp+2A8h+Src]; void *
0x140004b5d  call    memset_0
0x140004b62  lea     rax, [rsp+2A8h+var_138]
0x140004b6a  mov     [rsp+2A8h+var_258], rax
0x140004b6f  mov     r8d, 1394h
0x140004b75  lea     rdx, [rsp+2A8h+var_58]
0x140004b7d  call    ?LoadStringW@CVssResource@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CVssResource::LoadStringW(uint)
0x140004b82  nop
0x140004b83  lea     rbx, [rsp+2A8h+var_58]
0x140004b8b  cmp     [rsp+2A8h+var_40], 7
0x140004b94  cmova   rbx, [rsp+2A8h+var_58]
0x140004b9d  mov     rax, [rsp+2A8h+var_138]
0x140004ba5  mov     [rsp+2A8h+var_250], rax
0x140004baa  mov     rax, [rsp+2A8h+var_128]
0x140004bb2  mov     [rsp+2A8h+var_240], rax
0x140004bb7  mov     rax, [rsp+2A8h+var_130]
0x140004bbf  mov     [rsp+2A8h+var_248], rax
0x140004bc4  mov     eax, dword ptr [rsp+2A8h+var_120]
0x140004bcb  mov     dword ptr [rsp+2A8h+var_238], eax
0x140004bcf  mov     eax, dword ptr [rsp+2A8h+var_120+4]
0x140004bd6  mov     dword ptr [rsp+2A8h+var_238+4], eax
0x140004bda  movzx   eax, word ptr [rsp+2A8h+var_98]
0x140004be2  mov     word ptr [rsp+2A8h+var_1B0], ax
0x140004bea  mov     al, byte ptr [rsp+2A8h+var_98+2]
0x140004bf1  mov     byte ptr [rsp+2A8h+var_1B0+2], al
0x140004bf8  mov     eax, dword ptr [rsp+2A8h+var_118]
0x140004bff  mov     [rsp+2A8h+var_230], eax
0x140004c03  mov     al, byte ptr [rsp+2A8h+var_98+3]
0x140004c0a  mov     byte ptr [rsp+2A8h+var_1B0+3], al
0x140004c11  mov     byte ptr [rsp+2A8h+var_98+3], dil
0x140004c19  mov     r8d, r15d; Size
0x140004c1c  lea     rdx, [rsp+2A8h+Src]; Src
0x140004c24  lea     rcx, [rsp+2A8h+var_228]; void *
0x140004c2c  call    memcpy_0
0x140004c31  lea     rax, aCoordinator; "Coordinator"
0x140004c38  mov     [rsp+2A8h+var_288], rax
0x140004c3d  mov     r9, rbx
0x140004c40  lea     r8d, [r15-76h]
0x140004c44  lea     rdx, [rsp+2A8h+var_250]
0x140004c49  lea     rcx, [rsp+2A8h+var_1A8]
0x140004c51  call    ?AddContextInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@W4_VssContextType@@PEBG2@Z; CVssFunctionTracer::AddContextInternal(CVssDebugInfo,_VssContextType,ushort const *,ushort const *)
0x140004c56  nop
0x140004c57  mov     rdx, [rsp+2A8h+var_40]
0x140004c5f  cmp     rdx, 7
0x140004c63  jbe     short loc_140004C7A
0x140004c65  lea     rdx, ds:2[rdx*2]
0x140004c6d  mov     rcx, [rsp+2A8h+var_58]
0x140004c75  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140004c7a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140004c82  movdqu  xmmword ptr [rsp+260h], xmm0
0x140004c8b  mov     word ptr [rsp+2A8h+var_58], di
0x140004c93  lea     rcx, [rsp+2A8h+var_138]; this
0x140004c9b  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140004ca0  lea     rbx, [rsi+78h]
0x140004ca4  xor     edx, edx
0x140004ca6  mov     rcx, rbx
0x140004ca9  call    ??8?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEBA_NPEAUIXMLDOMNode@@@Z; ATL::CComPtrBase<IXMLDOMNode>::operator==(IXMLDOMNode *)
0x140004cae  test    al, al
0x140004cb0  jz      short loc_140004CC2
0x140004cb2  call    ?CreateInstance@CVssSnapshotSetObject@@SAPEAV1@XZ; CVssSnapshotSetObject::CreateInstance(void)
0x140004cb7  mov     rdx, rax
0x140004cba  mov     rcx, rbx
0x140004cbd  call    ??4?$CComPtr@VIVssSnapshotSetDescription@@@ATL@@QEAAPEAVIVssSnapshotSetDescription@@PEAV2@@Z; ATL::CComPtr<IVssSnapshotSetDescription>::operator=(IVssSnapshotSetDescription *)
0x140004cc2  mov     rcx, rsi; this
0x140004cc5  call    ?PreFreezeContext@CVssCoordinator@@AEAAXXZ; CVssCoordinator::PreFreezeContext(void)
0x140004cca  mov     rcx, rbx
0x140004ccd  call    ??C?$CComPtrBase@UIGlobalInterfaceTable@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIGlobalInterfaceTable@@@1@XZ; ATL::CComPtrBase<IGlobalInterfaceTable>::operator->(void)
0x140004cd2  mov     rdi, rax
0x140004cd5  mov     r15d, [rsi+98h]
0x140004cdc  lea     rax, aBaseStorVssMod_13; "base\\stor\\vss\\modules\\coord\\src\\p"...
0x140004ce3  mov     [rsp+2A8h+var_250], rax
0x140004ce8  lea     rax, aCvssproviderma_9; "CVssProviderManager::SetContextInternal"
0x140004cef  mov     [rsp+2A8h+var_248], rax
0x140004cf4  lea     rax, aCorprvmc; "CORPRVMC"
0x140004cfb  mov     [rsp+2A8h+var_240], rax
0x140004d00  mov     dword ptr [rsp+2A8h+var_238], 6FEh
0x140004d08  mov     dword ptr [rsp+2A8h+var_238+4], 1
0x140004d10  mov     [rsp+2A8h+var_230], 0FFh
0x140004d18  mov     [rsp+2A8h+var_1B0], 1000000h
0x140004d23  xor     edx, edx; Val
0x140004d25  lea     r8d, [rdx+78h]; Size
0x140004d29  lea     rcx, [rsp+2A8h+var_228]; void *
0x140004d31  call    memset_0
0x140004d36  mov     dword ptr [rsp+2A8h+var_130], 0
0x140004d41  mov     rax, [rsp+2A8h+var_248]
0x140004d46  mov     [rsp+2A8h+Src], rax
0x140004d4e  mov     rax, [rsp+2A8h+var_250]
  ... truncated ...
```
