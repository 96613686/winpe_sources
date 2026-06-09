# CVssCoordinator::SetContext(long)

- ea: `0x140005050`
- end: `0x140005c32`
- name: `?SetContext@CVssCoordinator@@UEAAJJ@Z`
- size: `3042`
- prototype: `__int64 __fastcall(CVssCoordinator *this, unsigned int)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140001d54`
- `0x140005050`
- `0x140006020`
- `0x140007060`
- `0x140011440`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140013d30`
- `0x140015950`
- `0x140015e38`
- `0x14001940c`
- `0x140019990`
- `0x140019bf0`
- `0x140030230`
- `0x14004ee3c`
- `0x140091560`
- `0x1400921dc`
- `0x14009b734`
- `0x1400da314`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140005145`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140005737`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140005145`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140005737`
- `VssTrace!__imp_VssTraceMessage` at `0x140005265`
- `VssTrace!__imp_VssTraceMessage` at `0x140005849`
- `VssTrace!__imp_VssTraceMessage` at `0x140005265`
- `VssTrace!__imp_VssTraceMessage` at `0x140005849`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400051aa`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140005799`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400051aa`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140005799`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140005198`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140005787`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140005198`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140005787`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005a9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140005a9d`

## string_xrefs

- `0x140005b11`: `The context is already frozen`

## pseudocode

```c
__int64 __fastcall CVssCoordinator::SetContext(CVssCoordinator *this, unsigned int a2)
{
  int v4; // eax
  const unsigned __int16 **v5; // rcx
  int v6; // r14d
  int v7; // ebx
  bool v8; // dl
  unsigned int v9; // eax
  bool v10; // al
  int v11; // eax
  const unsigned __int16 **v12; // rcx
  __int64 v13; // rcx
  _QWORD *v14; // rbx
  __int64 i; // rbx
  wchar_t *v16; // rcx
  unsigned int v17; // ebx
  __int64 v19; // [rsp+20h] [rbp-288h]
  const unsigned __int16 **v20; // [rsp+50h] [rbp-258h] BYREF
  const unsigned __int16 *v21; // [rsp+58h] [rbp-250h] BYREF
  const wchar_t *v22; // [rsp+60h] [rbp-248h]
  const unsigned __int16 *v23; // [rsp+68h] [rbp-240h]
  __int64 v24; // [rsp+70h] [rbp-238h]
  int v25; // [rsp+78h] [rbp-230h]
  _BYTE v26[120]; // [rsp+80h] [rbp-228h] BYREF
  int v27; // [rsp+F8h] [rbp-1B0h]
  _DWORD v28[2]; // [rsp+100h] [rbp-1A8h] BYREF
  unsigned int v29; // [rsp+108h] [rbp-1A0h]
  const unsigned __int16 *v30; // [rsp+110h] [rbp-198h]
  const unsigned __int16 *v31; // [rsp+118h] [rbp-190h]
  __int64 v32; // [rsp+120h] [rbp-188h]
  const unsigned __int16 *v33; // [rsp+128h] [rbp-180h]
  unsigned int v34; // [rsp+130h] [rbp-178h]
  DWORD TickCount; // [rsp+134h] [rbp-174h]
  int v36; // [rsp+138h] [rbp-170h]
  __int128 v37; // [rsp+140h] [rbp-168h]
  __int128 v38; // [rsp+150h] [rbp-158h]
  const unsigned __int16 **v39; // [rsp+160h] [rbp-148h]
  const unsigned __int16 *v40; // [rsp+170h] [rbp-138h] BYREF
  const unsigned __int16 *v41; // [rsp+178h] [rbp-130h]
  const unsigned __int16 *v42; // [rsp+180h] [rbp-128h]
  __int64 v43; // [rsp+188h] [rbp-120h]
  __int64 v44; // [rsp+190h] [rbp-118h]
  const wchar_t *Src; // [rsp+198h] [rbp-110h] BYREF
  unsigned int v46; // [rsp+1A0h] [rbp-108h]
  DWORD v47; // [rsp+1A4h] [rbp-104h]
  int v48; // [rsp+1A8h] [rbp-100h]
  __int128 v49; // [rsp+1B0h] [rbp-F8h]
  __int128 v50; // [rsp+1C0h] [rbp-E8h]
  const unsigned __int16 **v51; // [rsp+1D0h] [rbp-D8h]
  int v52; // [rsp+210h] [rbp-98h]
  int v53; // [rsp+228h] [rbp-80h] BYREF
  char *v54; // [rsp+230h] [rbp-78h] BYREF
  char v55; // [rsp+238h] [rbp-70h]
  _com_error *v56; // [rsp+240h] [rbp-68h] BYREF
  const std::exception *v57; // [rsp+248h] [rbp-60h] BYREF
  _QWORD v58[2]; // [rsp+250h] [rbp-58h] BYREF
  __m128i si128; // [rsp+260h] [rbp-48h]

  v40 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v41 = L"CVssCoordinator::SetContext";
  v42 = L"CORCOORC";
  v43 = 0x1000009E8LL;
  LODWORD(v44) = 255;
  v52 = 0x1000000;
  memset_0(&Src, 0, 0x78u);
  v29 = 0;
  v33 = L"CVssCoordinator::SetContext";
  v30 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v31 = L"CORCOORC";
  v32 = 0x1000009E8LL;
  TickCount = GetTickCount();
  v28[1] = -1;
  v36 = 255;
  v28[0] = 0;
  v39 = 0;
  v37 = 0;
  v38 = 0;
  v20 = 0;
  if ( (int)VssGetTracingContextPerThread(&v20) < 0 )
  {
    v5 = v39;
  }
  else
  {
    v4 = VssSetTracingContextPerThread(v28);
    v5 = v39;
    if ( v4 >= 0 )
      v5 = v20;
    v39 = v5;
  }
  if ( v5 )
    v34 = *((_DWORD *)v5 + 12) + 1;
  else
    v34 = 0;
  v6 = 160;
  v7 = 160;
  if ( v36 != 255 )
    v7 = v36;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v28) )
    VssTraceMessage(v30, v31, (unsigned int)v32, v34, HIDWORD(v32), v33, L"ENTER", v7, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v40);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( a2 == -1 )
    {
      if ( !CVssSidCollection::IsClientValidRequestor((PSECURITY_DESCRIPTOR *)this + 23) )
      {
        v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
        v22 = L"CVssCoordinator::SetContext";
        v23 = L"CORCOORC";
        v24 = 0x1000009F1LL;
        v25 = 255;
        v27 = 0x1000000;
        memset_0(v26, 0, sizeof(v26));
        CVssFunctionTracer::Throw(
          v28,
          &v21,
          2147942405LL,
          L"The  client process is not running under a valid user account for requestor");
      }
LABEL_38:
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v22 = L"CVssCoordinator::SetContext";
      v23 = L"CORCOORC";
      v24 = 0x100000A23LL;
      v25 = 255;
      v27 = 0x1000000;
      memset_0(v26, 0, sizeof(v26));
      CVssFunctionTracer::Trace(v28, &v21, L"Parameters: \nlContext = %ld\n", a2);
      v54 = (char *)this + 16;
      v55 = 0;
      v21 = L"base\\stor\\vss\\inc\\vs_types.hxx";
      v22 = L"CVssAutomaticLock2::CVssAutomaticLock2";
      v23 = L"INCTYPEH";
      v24 = 0xB00000100LL;
      v25 = 255;
      v27 = 0x1000000;
      memset_0(v26, 0, sizeof(v26));
      LODWORD(v41) = 0;
      Src = v22;
      v42 = v21;
      v43 = (__int64)v23;
      v44 = v24;
      v47 = GetTickCount();
      v48 = v25;
      v40 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
      v51 = 0;
      v49 = 0;
      v50 = 0;
      v20 = 0;
      if ( (int)VssGetTracingContextPerThread(&v20) < 0 )
      {
        v12 = v51;
      }
      else
      {
        v11 = VssSetTracingContextPerThread(&v40);
        v12 = v51;
        if ( v11 >= 0 )
          v12 = v20;
        v51 = v12;
      }
      if ( v12 )
        v46 = *((_DWORD *)v12 + 12) + 1;
      else
        v46 = 0;
      if ( v48 != 255 )
        v6 = v48;
      if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v40) )
        VssTraceMessage(v42, v43, (unsigned int)v44, v46, HIDWORD(v44), Src, L"ENTER", v6, 0);
      CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v21);
      CVssCriticalSection::Lock((LPCRITICAL_SECTION)((char *)this + 16));
      v55 = 1;
      CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v40);
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v22 = L"CVssCoordinator::SetContext";
      v23 = L"CORCOORC";
      v24 = 0xD00000A2ELL;
      v25 = 255;
      v27 = 0x1000000;
      memset_0(v26, 0, sizeof(v26));
      CVssFunctionTracer::AddOperation((__int64)v28, (__int64)&v21, 301u);
      v40 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v41 = L"CVssCoordinator::SetContext";
      v42 = L"CORCOORC";
      v43 = 0xD00000A2FLL;
      LODWORD(v44) = 255;
      v52 = 0x1000000;
      memset_0(&Src, 0, 0x78u);
      v20 = &v40;
      CVssResource::LoadStringW(v13, v58, 5012);
      v14 = v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v14 = (_QWORD *)v58[0];
      v21 = v40;
      v23 = v42;
      v22 = v41;
      v24 = v43;
      v27 = v52;
      v25 = v44;
      HIBYTE(v52) = 0;
      memcpy_0(v26, &Src, sizeof(v26));
      CVssFunctionTracer::AddContextInternal((__int64)v28, (__int64)&v21, 2, (__int64)v14, L"Coordinator");
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v58[0], 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v58[0]) = 0;
      if ( HIBYTE(v52) )
      {
        for ( i = 0; i != 15; ++i )
        {
          v16 = (wchar_t *)(&Src)[i];
          if ( v16 )
          {
            CoTaskMemFree(v16);
            (&Src)[i] = 0;
          }
        }
      }
      if ( *((_BYTE *)this + 156) )
      {
        v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
        v22 = L"CVssCoordinator::SetContext";
        v23 = L"CORCOORC";
        v24 = 0x100000A33LL;
        v25 = 255;
        v27 = 0x1000000;
        memset_0(v26, 0, sizeof(v26));
        CVssFunctionTracer::Throw(v28, &v21, 2147754753LL, L"The context is already frozen");
      }
      if ( *((_BYTE *)this + 157) && (*((_DWORD *)this + 38) == -1 || ((a2 ^ *((_DWORD *)this + 38)) & 0xFD3FFFFF) != 0) )
      {
        v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
        v22 = L"CVssCoordinator::SetContext";
        v23 = L"CORCOORC";
        v24 = 0x100000A3BLL;
        v25 = 255;
        v27 = 0x1000000;
        memset_0(v26, 0, sizeof(v26));
        CVssFunctionTracer::Throw(
          v28,
          &v21,
          2147754753LL,
          L"The context is prefrozen, and being changed in an invalid manner.");
      }
      *((_DWORD *)this + 38) = a2;
      CVssCoordinator::PreFreezeContext(this);
      CVssAutomaticLock2::~CVssAutomaticLock2((LPCRITICAL_SECTION *)&v54);
      goto LABEL_69;
    }
    if ( (a2 & 0x20000) != 0 && (a2 & 0x40000) != 0 )
    {
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v22 = L"CVssCoordinator::SetContext";
      v23 = L"CORCOORC";
      v24 = 0x1000009F6LL;
      v25 = 255;
      v27 = 0x1000000;
      memset_0(v26, 0, sizeof(v26));
      LODWORD(v19) = a2;
      CVssFunctionTracer::Throw(
        v28,
        &v21,
        2147754779LL,
        L"Invalid context - both plex and differential specified 0x%08lx",
        v19);
    }
    if ( (a2 & 0x1000000) != 0 )
    {
      *((_BYTE *)this + 304) = 1;
      a2 &= ~0x1000000u;
    }
    v9 = a2 & 0xF939FF5D;
    if ( (a2 & 0xF939FF5D) != 0 )
    {
      if ( v9 == 13 )
      {
LABEL_31:
        if ( !((bool (__fastcall *)(DWORD, bool))IsInGroup)(0x220u, v8) )
        {
          v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
          v22 = L"CVssCoordinator::SetContext";
          v23 = L"CORCOORC";
          v24 = 0x100000A17LL;
          v25 = 255;
          v27 = 0x1000000;
          memset_0(v26, 0, sizeof(v26));
          CVssFunctionTracer::Throw(v28, &v21, 2147942405LL, L"The client is not a administrator");
        }
        goto LABEL_38;
      }
      if ( v9 != 9 && v9 != 16 && v9 != 25 )
      {
        if ( v9 != 29 )
        {
          v10 = ((bool (__fastcall *)(DWORD, bool))IsInGroup)(0x220u, v8);
          HIDWORD(v24) = 1;
          v25 = 255;
          v27 = 0x1000000;
          v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
          v22 = L"CVssCoordinator::SetContext";
          v23 = L"CORCOORC";
          if ( !v10 )
          {
            LODWORD(v24) = 2588;
            memset_0(v26, 0, sizeof(v26));
            CVssFunctionTracer::Throw(v28, &v21, 2147942405LL, L"The client is not a administrator");
          }
          LODWORD(v24) = 2590;
          memset_0(v26, 0, sizeof(v26));
          LODWORD(v19) = a2;
          CVssFunctionTracer::Throw(v28, &v21, 2147754779LL, L"Invalid context 0x%08lx", v19);
        }
        goto LABEL_31;
      }
    }
    if ( !((bool (*)(void))IsBackupOperator)() )
    {
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v22 = L"CVssCoordinator::SetContext";
      v23 = L"CORCOORC";
      v24 = 0x100000A09LL;
      v25 = 255;
      v27 = 0x1000000;
      memset_0(v26, 0, sizeof(v26));
      CVssFunctionTracer::Throw(v28, &v21, 2147942405LL, L"The client is not a backup operator");
    }
    if ( (a2 & 0x20) != 0 && !(unsigned int)CVssSKU::IsTransportableAllowed() )
    {
      v21 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
      v22 = L"CVssCoordinator::SetContext";
      v23 = L"CORCOORC";
      v24 = 0x100000A0FLL;
      v25 = 255;
      v27 = 0x1000000;
      memset_0(v26, 0, sizeof(v26));
      CVssFunctionTracer::Throw(v28, &v21, 2147754779LL, L"The server does not support transportable shadows");
    }
    goto LABEL_38;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v53) )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)v28,
        v53,
        L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
        L"CORCOORC",
        L"CVssCoordinator::SetContext",
        0xA46u,
        HIDWORD(v32));
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_140005BE9);
      goto LABEL_69;
    }
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v56) )
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)v28,
        v56,
        L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
        L"CORCOORC",
        L"CVssCoordinator::SetContext",
        0xA46u,
        HIDWORD(v32));
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)v28,
        L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
        L"CORCOORC",
        L"CVssCoordinator::SetContext",
        0xA46u,
        HIDWORD(v32));
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_140005BED);
      goto LABEL_69;
    }
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v57) )
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)v28,
        v57,
        L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx",
        L"CORCOORC",
        L"CVssCoordinator::SetContext",
        0xA46u,
        HIDWORD(v32));
  }
LABEL_69:
  v17 = v29;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)v28);
  return v17;
}

```

## disassembly

```asm
0x140005050  mov     r11, rsp
0x140005053  mov     [r11+18h], rbx
0x140005057  mov     [r11+20h], rsi
0x14000505b  push    rdi
0x14000505c  push    r12
0x14000505e  push    r13
0x140005060  push    r14
0x140005062  push    r15
0x140005064  sub     rsp, 280h
0x14000506b  mov     rax, cs:__security_cookie
0x140005072  xor     rax, rsp
0x140005075  mov     [rsp+2A8h+var_38], rax
0x14000507d  mov     edi, edx
0x14000507f  mov     rsi, rcx
0x140005082  xor     r12d, r12d
0x140005085  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14000508c  mov     [r11-138h], rax
0x140005093  lea     rax, aCvsscoordinato_0; "CVssCoordinator::SetContext"
0x14000509a  mov     [r11-130h], rax
0x1400050a1  lea     rax, aCorcoorc; "CORCOORC"
0x1400050a8  mov     [r11-128h], rax
0x1400050af  mov     dword ptr [rsp+2A8h+var_120], 9E8h
0x1400050ba  lea     r13d, [r12+1]
0x1400050bf  mov     [r11-11Ch], r13d
0x1400050c6  mov     r15d, 0FFh
0x1400050cc  mov     [r11-118h], r15d
0x1400050d3  mov     [rsp+2A8h+var_98], 1000000h
0x1400050de  xor     edx, edx; Val
0x1400050e0  lea     r8d, [r12+78h]; Size
0x1400050e5  lea     rcx, [r11-110h]; void *
0x1400050ec  call    memset_0
0x1400050f1  mov     [rsp+2A8h+var_1A0], r12d
0x1400050f9  mov     rax, [rsp+2A8h+var_130]
0x140005101  mov     [rsp+2A8h+var_180], rax
0x140005109  mov     rax, [rsp+2A8h+var_138]
0x140005111  mov     [rsp+2A8h+var_198], rax
0x140005119  mov     rax, [rsp+2A8h+var_128]
0x140005121  mov     [rsp+2A8h+var_190], rax
0x140005129  mov     eax, dword ptr [rsp+2A8h+var_120]
0x140005130  mov     dword ptr [rsp+2A8h+var_188], eax
0x140005137  mov     eax, dword ptr [rsp+2A8h+var_120+4]
0x14000513e  mov     dword ptr [rsp+2A8h+var_188+4], eax
0x140005145  call    cs:__imp_GetTickCount
0x14000514b  mov     [rsp+2A8h+var_174], eax
0x140005152  mov     [rsp+2A8h+var_1A4], 0FFFFFFFFh
0x14000515d  mov     eax, dword ptr [rsp+2A8h+var_118]
0x140005164  mov     [rsp+2A8h+var_170], eax
0x14000516b  mov     [rsp+2A8h+var_1A8], r12d
0x140005173  mov     [rsp+2A8h+var_148], r12
0x14000517b  xorps   xmm0, xmm0
0x14000517e  movups  [rsp+2A8h+var_168], xmm0
0x140005186  movups  [rsp+2A8h+var_158], xmm0
0x14000518e  mov     [rsp+2A8h+var_258], r12
0x140005193  lea     rcx, [rsp+2A8h+var_258]
0x140005198  call    cs:__imp_VssGetTracingContextPerThread
0x14000519e  test    eax, eax
0x1400051a0  js      short loc_1400051CA
0x1400051a2  lea     rcx, [rsp+2A8h+var_1A8]
0x1400051aa  call    cs:__imp_VssSetTracingContextPerThread
0x1400051b0  mov     rcx, [rsp+2A8h+var_148]
0x1400051b8  test    eax, eax
0x1400051ba  cmovns  rcx, [rsp+2A8h+var_258]
0x1400051c0  mov     [rsp+2A8h+var_148], rcx
0x1400051c8  jmp     short loc_1400051D2
0x1400051ca  mov     rcx, [rsp+2A8h+var_148]
0x1400051d2  test    rcx, rcx
0x1400051d5  jz      short loc_1400051E6
0x1400051d7  mov     eax, [rcx+30h]
0x1400051da  add     eax, r13d
0x1400051dd  mov     [rsp+2A8h+var_178], eax
0x1400051e4  jmp     short loc_1400051EE
0x1400051e6  mov     [rsp+2A8h+var_178], r12d
0x1400051ee  mov     r14d, 0A0h
0x1400051f4  mov     ebx, r14d
0x1400051f7  cmp     [rsp+2A8h+var_170], r15d
0x1400051ff  cmovnz  ebx, [rsp+2A8h+var_170]
0x140005207  lea     rcx, [rsp+2A8h+var_1A8]; this
0x14000520f  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140005214  test    eax, eax
0x140005216  jz      short loc_14000526D
0x140005218  mov     [rsp+2A8h+var_268], r12
0x14000521d  mov     [rsp+2A8h+var_270], ebx
0x140005221  lea     rbx, aEnter; "ENTER"
0x140005228  mov     [rsp+2A8h+var_278], rbx
0x14000522d  mov     rax, [rsp+2A8h+var_180]
0x140005235  mov     [rsp+2A8h+var_280], rax
0x14000523a  mov     eax, dword ptr [rsp+2A8h+var_188+4]
0x140005241  mov     dword ptr [rsp+2A8h+var_288], eax
0x140005245  mov     r9d, [rsp+2A8h+var_178]
0x14000524d  mov     r8d, dword ptr [rsp+2A8h+var_188]
0x140005255  mov     rdx, [rsp+2A8h+var_190]
0x14000525d  mov     rcx, [rsp+2A8h+var_198]
0x140005265  call    cs:__imp_VssTraceMessage
0x14000526b  jmp     short loc_140005274
0x14000526d  lea     rbx, aEnter; "ENTER"
0x140005274  lea     rcx, [rsp+2A8h+var_138]; this
0x14000527c  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140005281  nop
0x140005282  cmp     edi, 0FFFFFFFFh
0x140005285  jnz     loc_140005312
0x14000528b  lea     rcx, [rsi+0B8h]; this
0x140005292  call    ?IsClientValidRequestor@CVssSidCollection@@QEAA_NXZ; CVssSidCollection::IsClientValidRequestor(void)
0x140005297  test    al, al
0x140005299  jnz     loc_140005614
0x14000529f  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x1400052a6  mov     [rsp+2A8h+var_250], rax
0x1400052ab  lea     rax, aCvsscoordinato_0; "CVssCoordinator::SetContext"
0x1400052b2  mov     [rsp+2A8h+var_248], rax
0x1400052b7  lea     rax, aCorcoorc; "CORCOORC"
0x1400052be  mov     [rsp+2A8h+var_240], rax
0x1400052c3  mov     dword ptr [rsp+2A8h+var_238], 9F1h
0x1400052cb  mov     dword ptr [rsp+2A8h+var_238+4], r13d
0x1400052d0  mov     [rsp+2A8h+var_230], r15d
0x1400052d5  mov     [rsp+2A8h+var_1B0], 1000000h
0x1400052e0  xor     edx, edx; Val
0x1400052e2  lea     r8d, [rdi+79h]; Size
0x1400052e6  lea     rcx, [rsp+2A8h+var_228]; void *
0x1400052ee  call    memset_0
0x1400052f3  lea     r9, aTheClientProce_2; "The  client process is not running unde"...
0x1400052fa  mov     r8d, 80070005h
0x140005300  lea     rdx, [rsp+2A8h+var_250]
0x140005305  lea     rcx, [rsp+2A8h+var_1A8]
0x14000530d  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140005312  bt      edi, 11h
0x140005316  jnb     short loc_140005395
0x140005318  bt      edi, 12h
0x14000531c  jnb     short loc_140005395
0x14000531e  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x140005325  mov     [rsp+2A8h+var_250], rax
0x14000532a  lea     rax, aCvsscoordinato_0; "CVssCoordinator::SetContext"
0x140005331  mov     [rsp+2A8h+var_248], rax
0x140005336  lea     rax, aCorcoorc; "CORCOORC"
0x14000533d  mov     [rsp+2A8h+var_240], rax
0x140005342  mov     dword ptr [rsp+2A8h+var_238], 9F6h
0x14000534a  mov     dword ptr [rsp+2A8h+var_238+4], r13d
0x14000534f  mov     [rsp+2A8h+var_230], r15d
0x140005354  mov     [rsp+2A8h+var_1B0], 1000000h
0x14000535f  xor     edx, edx; Val
0x140005361  lea     r8d, [rdx+78h]; Size
0x140005365  lea     rcx, [rsp+2A8h+var_228]; void *
0x14000536d  call    memset_0
0x140005372  mov     dword ptr [rsp+2A8h+var_288], edi
0x140005376  lea     r9, aInvalidContext; "Invalid context - both plex and differe"...
0x14000537d  mov     r8d, 8004231Bh
0x140005383  lea     rdx, [rsp+2A8h+var_250]
0x140005388  lea     rcx, [rsp+2A8h+var_1A8]
0x140005390  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140005395  bt      edi, 18h
0x140005399  jnb     short loc_1400053A6
0x14000539b  mov     [rsi+130h], r13b
0x1400053a2  btr     edi, 18h
0x1400053a6  mov     eax, edi
0x1400053a8  and     eax, 0F939FF5Dh
0x1400053ad  jz      loc_140005516
0x1400053b3  cmp     eax, 0Dh
0x1400053b6  jz      loc_140005491
0x1400053bc  cmp     eax, 9
0x1400053bf  jz      loc_140005516
0x1400053c5  cmp     eax, 10h
0x1400053c8  jz      loc_140005516
0x1400053ce  cmp     eax, 19h
0x1400053d1  jz      loc_140005516
0x1400053d7  cmp     eax, 1Dh
0x1400053da  jz      loc_140005491
0x1400053e0  mov     ecx, 220h; nSubAuthority1
0x1400053e5  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x1400053ea  mov     dword ptr [rsp+2A8h+var_238+4], r13d
0x1400053ef  mov     [rsp+2A8h+var_230], r15d
0x1400053f4  mov     [rsp+2A8h+var_1B0], 1000000h
0x1400053ff  xor     edx, edx; Val
0x140005401  lea     r8d, [rdx+78h]; Size
0x140005405  lea     rcx, [rsp+2A8h+var_228]; void *
0x14000540d  test    al, al
0x14000540f  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x140005416  mov     [rsp+2A8h+var_250], rax
0x14000541b  lea     rax, aCvsscoordinato_0; "CVssCoordinator::SetContext"
0x140005422  mov     [rsp+2A8h+var_248], rax
0x140005427  lea     rax, aCorcoorc; "CORCOORC"
0x14000542e  mov     [rsp+2A8h+var_240], rax
0x140005433  jnz     short loc_140005461
0x140005435  mov     dword ptr [rsp+2A8h+var_238], 0A1Ch
0x14000543d  call    memset_0
0x140005442  lea     r9, aTheClientIsNot; "The client is not a administrator"
0x140005449  mov     r8d, 80070005h
0x14000544f  lea     rdx, [rsp+2A8h+var_250]
0x140005454  lea     rcx, [rsp+2A8h+var_1A8]
0x14000545c  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140005461  mov     dword ptr [rsp+2A8h+var_238], 0A1Eh
0x140005469  call    memset_0
0x14000546e  mov     dword ptr [rsp+2A8h+var_288], edi
0x140005472  lea     r9, aInvalidContext_0; "Invalid context 0x%08lx"
0x140005479  mov     r8d, 8004231Bh
0x14000547f  lea     rdx, [rsp+2A8h+var_250]
0x140005484  lea     rcx, [rsp+2A8h+var_1A8]
0x14000548c  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140005491  mov     ecx, 220h; nSubAuthority1
0x140005496  call    ?IsInGroup@@YA_NK_N@Z; IsInGroup(ulong,bool)
0x14000549b  test    al, al
0x14000549d  jnz     loc_140005614
0x1400054a3  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x1400054aa  mov     [rsp+2A8h+var_250], rax
0x1400054af  lea     rax, aCvsscoordinato_0; "CVssCoordinator::SetContext"
0x1400054b6  mov     [rsp+2A8h+var_248], rax
0x1400054bb  lea     rax, aCorcoorc; "CORCOORC"
0x1400054c2  mov     [rsp+2A8h+var_240], rax
0x1400054c7  mov     dword ptr [rsp+2A8h+var_238], 0A17h
0x1400054cf  mov     dword ptr [rsp+2A8h+var_238+4], r13d
0x1400054d4  mov     [rsp+2A8h+var_230], r15d
0x1400054d9  mov     [rsp+2A8h+var_1B0], 1000000h
0x1400054e4  xor     edx, edx; Val
0x1400054e6  lea     r8d, [rdx+78h]; Size
0x1400054ea  lea     rcx, [rsp+2A8h+var_228]; void *
0x1400054f2  call    memset_0
0x1400054f7  lea     r9, aTheClientIsNot; "The client is not a administrator"
0x1400054fe  mov     r8d, 80070005h
0x140005504  lea     rdx, [rsp+2A8h+var_250]
0x140005509  lea     rcx, [rsp+2A8h+var_1A8]
0x140005511  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140005516  call    ?IsBackupOperator@@YA_NXZ; IsBackupOperator(void)
0x14000551b  test    al, al
0x14000551d  jnz     short loc_140005592
0x14000551f  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x140005526  mov     [rsp+2A8h+var_250], rax
0x14000552b  lea     rax, aCvsscoordinato_0; "CVssCoordinator::SetContext"
0x140005532  mov     [rsp+2A8h+var_248], rax
0x140005537  lea     rax, aCorcoorc; "CORCOORC"
0x14000553e  mov     [rsp+2A8h+var_240], rax
0x140005543  mov     dword ptr [rsp+2A8h+var_238], 0A09h
0x14000554b  mov     dword ptr [rsp+2A8h+var_238+4], r13d
0x140005550  mov     [rsp+2A8h+var_230], r15d
0x140005555  mov     [rsp+2A8h+var_1B0], 1000000h
0x140005560  xor     edx, edx; Val
0x140005562  lea     r8d, [rdx+78h]; Size
0x140005566  lea     rcx, [rsp+2A8h+var_228]; void *
0x14000556e  call    memset_0
0x140005573  lea     r9, aTheClientIsNot_0; "The client is not a backup operator"
0x14000557a  mov     r8d, 80070005h
0x140005580  lea     rdx, [rsp+2A8h+var_250]
0x140005585  lea     rcx, [rsp+2A8h+var_1A8]
0x14000558d  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140005592  test    dil, 20h
0x140005596  jz      short loc_140005614
0x140005598  call    ?IsTransportableAllowed@CVssSKU@@SAHXZ; CVssSKU::IsTransportableAllowed(void)
0x14000559d  test    eax, eax
0x14000559f  jnz     short loc_140005614
0x1400055a1  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x1400055a8  mov     [rsp+2A8h+var_250], rax
0x1400055ad  lea     rax, aCvsscoordinato_0; "CVssCoordinator::SetContext"
0x1400055b4  mov     [rsp+2A8h+var_248], rax
0x1400055b9  lea     rax, aCorcoorc; "CORCOORC"
0x1400055c0  mov     [rsp+2A8h+var_240], rax
0x1400055c5  mov     dword ptr [rsp+2A8h+var_238], 0A0Fh
0x1400055cd  mov     dword ptr [rsp+2A8h+var_238+4], r13d
0x1400055d2  mov     [rsp+2A8h+var_230], r15d
0x1400055d7  mov     [rsp+2A8h+var_1B0], 1000000h
0x1400055e2  xor     edx, edx; Val
0x1400055e4  lea     r8d, [rdx+78h]; Size
0x1400055e8  lea     rcx, [rsp+2A8h+var_228]; void *
0x1400055f0  call    memset_0
0x1400055f5  lea     r9, aTheServerDoesN; "The server does not support transportab"...
0x1400055fc  mov     r8d, 8004231Bh
0x140005602  lea     rdx, [rsp+2A8h+var_250]
0x140005607  lea     rcx, [rsp+2A8h+var_1A8]
0x14000560f  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140005614  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14000561b  mov     [rsp+2A8h+var_250], rax
0x140005620  lea     rax, aCvsscoordinato_0; "CVssCoordinator::SetContext"
0x140005627  mov     [rsp+2A8h+var_248], rax
0x14000562c  lea     rax, aCorcoorc; "CORCOORC"
0x140005633  mov     [rsp+2A8h+var_240], rax
0x140005638  mov     dword ptr [rsp+2A8h+var_238], 0A23h
0x140005640  mov     dword ptr [rsp+2A8h+var_238+4], r13d
0x140005645  mov     [rsp+2A8h+var_230], r15d
0x14000564a  mov     [rsp+2A8h+var_1B0], 1000000h
0x140005655  xor     edx, edx; Val
0x140005657  lea     r8d, [rdx+78h]; Size
0x14000565b  lea     rcx, [rsp+2A8h+var_228]; void *
0x140005663  call    memset_0
0x140005668  mov     r9d, edi
0x14000566b  lea     r8, aParametersLcon; "Parameters: \nlContext = %ld\n"
0x140005672  lea     rdx, [rsp+2A8h+var_250]
0x140005677  lea     rcx, [rsp+2A8h+var_1A8]
0x14000567f  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140005684  lea     r15, [rsi+10h]
0x140005688  mov     [rsp+2A8h+var_78], r15
0x140005690  mov     [rsp+2A8h+var_70], r12b
0x140005698  lea     rax, aBaseStorVssInc_3; "base\\stor\\vss\\inc\\vs_types.hxx"
0x14000569f  mov     [rsp+2A8h+var_250], rax
0x1400056a4  lea     rax, aCvssautomaticl_0; "CVssAutomaticLock2::CVssAutomaticLock2"
0x1400056ab  mov     [rsp+2A8h+var_248], rax
0x1400056b0  lea     rax, aInctypeh; "INCTYPEH"
0x1400056b7  mov     [rsp+2A8h+var_240], rax
0x1400056bc  mov     dword ptr [rsp+2A8h+var_238], 100h
0x1400056c4  mov     dword ptr [rsp+2A8h+var_238+4], 0Bh
0x1400056cc  mov     [rsp+2A8h+var_230], 0FFh
0x1400056d4  mov     [rsp+2A8h+var_1B0], 1000000h
0x1400056df  xor     edx, edx; Val
0x1400056e1  lea     r8d, [rdx+78h]; Size
0x1400056e5  lea     rcx, [rsp+2A8h+var_228]; void *
0x1400056ed  call    memset_0
  ... truncated ...
```
