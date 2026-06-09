# D3DCommon::ProcessLog(ushort const *,std::vector<D3DCommon::_AssessmentResults,std::allocator<D3DCommon::_AssessmentResults>> &)

- ea: `0x1400816c0`
- end: `0x140081d44`
- name: `?ProcessLog@D3DCommon@@YAJPEBGAEAV?$vector@U_AssessmentResults@D3DCommon@@V?$allocator@U_AssessmentResults@D3DCommon@@@std@@@std@@@Z`
- size: `1668`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140079e98`

## callees

- `0x140003611`
- `0x14000367d`
- `0x140004348`
- `0x14000449c`
- `0x140005cf4`
- `0x14000695c`
- `0x140016d04`
- `0x140017af0`
- `0x14007fa4c`
- `0x1400816c0`
- `0x1400820d0`
- `0x140113220`

## import_xrefs

- `ADVAPI32!OpenTraceW` at `0x14008184a`
- `ADVAPI32!OpenTraceW` at `0x14008184a`
- `ADVAPI32!CloseTrace` at `0x14008187e`
- `ADVAPI32!CloseTrace` at `0x14008187e`
- `ADVAPI32!ProcessTrace` at `0x1400818d7`
- `ADVAPI32!ProcessTrace` at `0x1400818d7`
- `KERNEL32!GetLastError` at `0x14008185b`
- `KERNEL32!GetLastError` at `0x14008185b`

## string_xrefs

- `0x140081754`: `D3DCommon::ProcessLog`
- `0x14008177b`: `D3DCommon::ProcessLog`
- `0x140081782`: `pwsPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall D3DCommon::ProcessLog(WCHAR *a1, _QWORD *a2)
{
  _QWORD *v2; // r15
  mlib::MUILoader *v4; // rdx
  __int64 *v5; // rax
  __int64 *v6; // rax
  signed int LastError; // eax
  signed int v9; // r14d
  bool v10; // cc
  unsigned int v11; // r13d
  double v12; // xmm9_8
  double v13; // xmm7_8
  double v14; // xmm8_8
  __int64 v15; // r12
  __int64 *v16; // rdx
  __int64 v17; // rdi
  __int64 v18; // r12
  char v19; // cl
  double v20; // xmm6_8
  unsigned __int64 v21; // rax
  double v22; // xmm0_8
  __int64 v23; // rcx
  double v24; // xmm0_8
  unsigned __int64 v25; // rax
  double v26; // xmm0_8
  __int64 v27; // rcx
  double v28; // xmm0_8
  double v29; // xmm6_8
  double v30; // xmm1_8
  __int64 v31; // [rsp+0h] [rbp-368h] BYREF
  unsigned int v32; // [rsp+20h] [rbp-348h]
  unsigned __int64 *v33; // [rsp+28h] [rbp-340h] BYREF
  TRACEHANDLE TraceHandle; // [rsp+30h] [rbp-338h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-330h]
  __int64 v36; // [rsp+40h] [rbp-328h]
  _BYTE v37[40]; // [rsp+48h] [rbp-320h] BYREF
  _BYTE v38[192]; // [rsp+70h] [rbp-2F8h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+130h] [rbp-238h] BYREF

  v2 = a2;
  v35 = a2;
  if ( D3DCommon::g_bVerbose && D3DCommon::g_phStdOut )
  {
    v4 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v37, 101);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      (__int64 *)&v33,
      (__int64)v4);
    v5 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
           (__int64 *)(D3DCommon::g_phStdOut + 240),
           &v33);
    v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, (__int64)L"D3DCommon::ProcessLog");
    std::endl(v6);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v33);
  }
  if ( !a1 )
  {
    D3DCommon::ERR((D3DCommon *)0x6A, (unsigned __int16)L"pwsPath", L"D3DCommon::ProcessLog");
    return 2147942487LL;
  }
  TraceHandle = 0;
  memset_0(&D3DCommon::gs_AssessmentData, 0, 0x300u);
  *(__m128i *)&D3DCommon::gs_uThreadIds = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  qword_1401C3B60 = (__int64)D3DCommon::gs_uThreadIds;
  D3DCommon::gs_bProcessingError = 0;
  D3DCommon::g_llPerfFreq = 0;
  D3DCommon::g_uNumberOfProcessors = 0;
  word_1401CABE0 = 0;
  word_1401CADF0 = 0;
  v2[1] = *v2;
  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileName = a1;
  Logfile.LoggerName = 0;
  Logfile.EventCallback = (PEVENT_CALLBACK)D3DCommon::LogCallback;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)D3DCommon::BufferCallback;
  Logfile.LogfileHeader.ReservedFlags = 2;
  TraceHandle = OpenTraceW(&Logfile);
  if ( TraceHandle == -1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    v10 = LastError <= 0;
  }
  else
  {
    LastError = ProcessTrace(&TraceHandle, 1u, 0, 0);
    v9 = LastError;
    v10 = LastError <= 0;
    if ( !LastError )
    {
      v9 = 0;
      v11 = 0;
      v32 = 0;
      v12 = DOUBLE_1000_0;
      v13 = DOUBLE_2_220446049250313eN16;
      v14 = DOUBLE_9_5367431640625eN7;
      while ( v11 < 6 )
      {
        v15 = v11;
        v36 = v11;
        if ( *((_DWORD *)&D3DCommon::gs_uThreadIds + v11) == -1 )
          break;
        try
        {
          v9 = 0;
          memset_0(v38, 0, 0xB8u);
          std::vector<D3DCommon::_AssessmentResults>::push_back(v2, v38);
        }
        catch ( std::bad_alloc )
        {
          v16 = &v31;
          LODWORD(v33) = -2147024882;
          v9 = -2147024882;
          v11 = v32;
          v2 = v35;
          v12 = DOUBLE_1000_0;
          v13 = DOUBLE_2_220446049250313eN16;
          v14 = DOUBLE_9_5367431640625eN7;
          v15 = v36;
        }
        v17 = v15 << 7;
        v18 = 184 * v15;
        *(_DWORD *)(v18 + *v2 + 160) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 112);
        *(_DWORD *)(v18 + *v2 + 164) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 116);
        if ( !*((_BYTE *)&D3DCommon::gs_AssessmentData + v17 + 1)
          || (v19 = 1, *((_BYTE *)&D3DCommon::gs_AssessmentData + v17)) )
        {
          v19 = 0;
        }
        *(_BYTE *)(v18 + *v2 + 172) = v19;
        if ( *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 4) > 2u
          && *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 8) > 2u )
        {
          v20 = (double)(int)D3DCommon::g_llPerfFreq;
          *(double *)(v18 + *v2) = (double)*(int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 4)
                                 * (double)(int)D3DCommon::g_llPerfFreq
                                 / (double)(*(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 56)
                                          - *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 16));
          *(double *)(v18 + *v2 + 8) = (double)*(int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 8)
                                     * v20
                                     / (double)(*(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 56)
                                              - *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 48));
          *(double *)(v18 + *v2 + 64) = (double)(*(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 56)
                                               - *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 16))
                                      / v20;
          *(double *)(v18 + *v2 + 72) = (double)(*(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 56)
                                               - *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 48))
                                      / v20;
          if ( v9 < 0 )
          {
            D3DCommon::ERR((D3DCommon *)0x71, (unsigned __int16)v16);
            goto LABEL_10;
          }
          *(_DWORD *)(v18 + *v2 + 16) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 4);
          *(_DWORD *)(v18 + *v2 + 20) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 8);
          *(_DWORD *)(v18 + *v2 + 24) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 12);
          v21 = *(unsigned __int64 *)((char *)&D3DCommon::gs_AssessmentData + v17 + 64)
              / *(unsigned int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 4);
          if ( (v21 & 0x8000000000000000uLL) != 0LL )
            v22 = (double)(int)(v21 & 1 | (v21 >> 1)) + (double)(int)(v21 & 1 | (v21 >> 1));
          else
            v22 = (double)(int)v21;
          *(double *)(v18 + *v2 + 32) = v22;
          v23 = *(__int64 *)((char *)&D3DCommon::gs_AssessmentData + v17 + 72)
              - *(_QWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 64)
              * *(_QWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 64)
              / (unsigned __int64)*(unsigned int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 4);
          if ( v23 < 0 )
            v24 = (double)(int)(v23 & 1 | ((unsigned __int64)v23 >> 1))
                + (double)(int)(v23 & 1 | ((unsigned __int64)v23 >> 1));
          else
            v24 = (double)(int)v23;
          *(double *)(v18 + *v2 + 40) = sqrt_0(v24 / (double)*(int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 4));
          v25 = *(unsigned __int64 *)((char *)&D3DCommon::gs_AssessmentData + v17 + 80)
              / *(unsigned int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 8);
          if ( (v25 & 0x8000000000000000uLL) != 0LL )
            v26 = (double)(int)(v25 & 1 | (v25 >> 1)) + (double)(int)(v25 & 1 | (v25 >> 1));
          else
            v26 = (double)(int)v25;
          *(double *)(v18 + *v2 + 48) = v26;
          v27 = *(__int64 *)((char *)&D3DCommon::gs_AssessmentData + v17 + 88)
              - *(_QWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 80)
              * *(_QWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 80)
              / (unsigned __int64)*(unsigned int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 8);
          if ( v27 < 0 )
            v28 = (double)(int)(v27 & 1 | ((unsigned __int64)v27 >> 1))
                + (double)(int)(v27 & 1 | ((unsigned __int64)v27 >> 1));
          else
            v28 = (double)(int)v27;
          *(double *)(v18 + *v2 + 56) = sqrt_0(v28 / (double)*(int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 8));
          v29 = v20 / v12;
          *(double *)(v18 + *v2 + 32) = *(double *)(v18 + *v2 + 32) / v29;
          *(double *)(v18 + *v2 + 40) = *(double *)(v18 + *v2 + 40) / v29;
          *(double *)(v18 + *v2 + 48) = *(double *)(v18 + *v2 + 48) / v29;
          *(double *)(v18 + *v2 + 56) = *(double *)(v18 + *v2 + 56) / v29;
          *(_QWORD *)(v18 + *v2 + 88) = *(struct D3DCommon::_AssessmentData near **)((char *)&D3DCommon::gs_AssessmentData
                                                                                   + v17
                                                                                   + 16);
          *(_QWORD *)(v18 + *v2 + 96) = *(struct D3DCommon::_AssessmentData near **)((char *)&D3DCommon::gs_AssessmentData
                                                                                   + v17
                                                                                   + 24);
          *(_QWORD *)(v18 + *v2 + 104) = *(struct D3DCommon::_AssessmentData near **)((char *)&D3DCommon::gs_AssessmentData
                                                                                    + v17
                                                                                    + 32);
          *(_QWORD *)(v18 + *v2 + 112) = *(struct D3DCommon::_AssessmentData near **)((char *)&D3DCommon::gs_AssessmentData
                                                                                    + v17
                                                                                    + 40);
          *(_QWORD *)(v18 + *v2 + 120) = *(struct D3DCommon::_AssessmentData near **)((char *)&D3DCommon::gs_AssessmentData
                                                                                    + v17
                                                                                    + 48);
          *(_QWORD *)(v18 + *v2 + 128) = *(struct D3DCommon::_AssessmentData near **)((char *)&D3DCommon::gs_AssessmentData
                                                                                    + v17
                                                                                    + 56);
          *(_QWORD *)(v18 + *v2 + 136) = D3DCommon::g_llPerfFreq;
          *(_DWORD *)(v18 + *v2 + 144) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 96);
          *(_DWORD *)(v18 + *v2 + 148) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 100);
          *(_DWORD *)(v18 + *v2 + 152) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 104);
          *(_DWORD *)(v18 + *v2 + 156) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 108);
          *(_DWORD *)(v18 + *v2 + 168) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 124);
          if ( *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 120) )
          {
            v30 = *(double *)(v18 + *v2);
            if ( v30 > v13 )
            {
              *(double *)(v18 + *v2 + 80) = (double)*(int *)((char *)&D3DCommon::gs_AssessmentData + v17 + 120)
                                          * v30
                                          * v14;
              *(_DWORD *)(v18 + *v2 + 176) = *(_DWORD *)((char *)&D3DCommon::gs_AssessmentData + v17 + 120);
            }
          }
        }
        v32 = ++v11;
      }
      goto LABEL_10;
    }
  }
  if ( !v10 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
  if ( TraceHandle != -1 )
    CloseTrace(TraceHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400816c0  mov     rax, rsp
0x1400816c3  mov     [rax+18h], rbx
0x1400816c7  mov     [rax+20h], rsi
0x1400816cb  push    rdi
0x1400816cc  push    r12
0x1400816ce  push    r13
0x1400816d0  push    r14
0x1400816d2  push    r15
0x1400816d4  sub     rsp, 340h
0x1400816db  movaps  xmmword ptr [rax-38h], xmm6
0x1400816df  movaps  xmmword ptr [rax-48h], xmm7
0x1400816e3  movaps  xmmword ptr [rax-58h], xmm8
0x1400816e8  movaps  xmmword ptr [rax-68h], xmm9
0x1400816ed  mov     rax, cs:__security_cookie
0x1400816f4  xor     rax, rsp
0x1400816f7  mov     [rsp+368h+var_78], rax
0x1400816ff  mov     r15, rdx
0x140081702  mov     rdi, rcx
0x140081705  mov     [rsp+368h+var_330], rdx
0x14008170a  xor     esi, esi
0x14008170c  cmp     cs:?g_bVerbose@D3DCommon@@3_NA, sil; bool D3DCommon::g_bVerbose
0x140081713  jz      short loc_140081773
0x140081715  cmp     cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA, rsi; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x14008171c  jz      short loc_140081773
0x14008171e  lea     edx, [rsi+65h]; unsigned __int16
0x140081721  lea     rcx, [rsp+368h+var_320]; this
0x140081726  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x14008172b  mov     rdx, rax
0x14008172e  lea     rcx, [rsp+368h+var_340]
0x140081733  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x140081738  nop
0x140081739  mov     rcx, cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x140081740  add     rcx, 0F0h
0x140081747  lea     rdx, [rsp+368h+var_340]
0x14008174c  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140081751  mov     rcx, rax
0x140081754  lea     rdx, aD3dcommonProce; "D3DCommon::ProcessLog"
0x14008175b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140081760  mov     rcx, rax
0x140081763  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140081768  nop
0x140081769  lea     rcx, [rsp+368h+var_340]
0x14008176e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140081773  test    rdi, rdi
0x140081776  jnz     short loc_140081798
0x140081778  lea     ecx, [rdi+6Ah]; this
0x14008177b  lea     r8, aD3dcommonProce; "D3DCommon::ProcessLog"
0x140081782  lea     rdx, aPwspath; "pwsPath"
0x140081789  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x14008178e  mov     eax, 80070057h
0x140081793  jmp     loc_140081887
0x140081798  mov     [rsp+368h+TraceHandle], rsi
0x14008179d  xor     edx, edx; Val
0x14008179f  mov     r8d, 300h; Size
0x1400817a5  lea     rbx, ?gs_AssessmentData@D3DCommon@@3PAU_AssessmentData@1@A; D3DCommon::_AssessmentData near * D3DCommon::gs_AssessmentData
0x1400817ac  mov     rcx, rbx; void *
0x1400817af  call    memset_0
0x1400817b4  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1400817bc  movups  cs:?gs_uThreadIds@D3DCommon@@3PAKA, xmm0; ulong near * D3DCommon::gs_uThreadIds
0x1400817c3  movq    cs:qword_1401C3B60, xmm0
0x1400817cb  mov     cs:?gs_bProcessingError@D3DCommon@@3_NA, sil; bool D3DCommon::gs_bProcessingError
0x1400817d2  mov     cs:?g_llPerfFreq@D3DCommon@@3_JA, rsi; __int64 D3DCommon::g_llPerfFreq
0x1400817d9  mov     cs:?g_uNumberOfProcessors@D3DCommon@@3IA, esi; uint D3DCommon::g_uNumberOfProcessors
0x1400817df  mov     cs:word_1401CABE0, si
0x1400817e6  mov     cs:word_1401CADF0, si
0x1400817ed  mov     rax, [r15]
0x1400817f0  mov     [r15+8], rax
0x1400817f4  xor     edx, edx; Val
0x1400817f6  mov     r8d, 1C0h; Size
0x1400817fc  lea     rcx, [rsp+368h+Logfile]; void *
0x140081804  call    memset_0
0x140081809  mov     [rsp+368h+Logfile.LogFileName], rdi
0x140081811  mov     [rsp+368h+Logfile.LoggerName], rsi
0x140081819  lea     rax, ?LogCallback@D3DCommon@@YAXPEAU_EVENT_TRACE@@@Z; D3DCommon::LogCallback(_EVENT_TRACE *)
0x140081820  mov     qword ptr [rsp+368h+Logfile.1A8h], rax
0x140081828  lea     rax, ?BufferCallback@D3DCommon@@YAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; D3DCommon::BufferCallback(_EVENT_TRACE_LOGFILEW *)
0x14008182f  mov     [rsp+368h+Logfile.BufferCallback], rax
0x140081837  mov     [rsp+368h+Logfile.LogfileHeader.ReservedFlags], 2
0x140081842  lea     rcx, [rsp+368h+Logfile]; Logfile
0x14008184a  call    cs:__imp_OpenTraceW
0x140081850  mov     [rsp+368h+TraceHandle], rax
0x140081855  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140081859  jnz     short loc_1400818C8
0x14008185b  call    cs:__imp_GetLastError
0x140081861  mov     r14d, eax
0x140081864  test    eax, eax
0x140081866  jle     short loc_140081873
0x140081868  movzx   r14d, ax
0x14008186c  or      r14d, 80070000h
0x140081873  mov     rcx, [rsp+368h+TraceHandle]; TraceHandle
0x140081878  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14008187c  jz      short loc_140081884
0x14008187e  call    cs:__imp_CloseTrace
0x140081884  mov     eax, r14d
0x140081887  mov     rcx, [rsp+368h+var_78]
0x14008188f  xor     rcx, rsp; StackCookie
0x140081892  call    __security_check_cookie
0x140081897  lea     r11, [rsp+368h+var_28]
0x14008189f  mov     rbx, [r11+40h]
0x1400818a3  mov     rsi, [r11+48h]
0x1400818a7  movaps  xmm6, xmmword ptr [r11-10h]
0x1400818ac  movaps  xmm7, xmmword ptr [r11-20h]
0x1400818b1  movaps  xmm8, xmmword ptr [r11-30h]
0x1400818b6  movaps  xmm9, xmmword ptr [r11-40h]
0x1400818bb  mov     rsp, r11
0x1400818be  pop     r15
0x1400818c0  pop     r14
0x1400818c2  pop     r13
0x1400818c4  pop     r12
0x1400818c6  pop     rdi
0x1400818c7  retn
0x1400818c8  xor     r9d, r9d; EndTime
0x1400818cb  xor     r8d, r8d; StartTime
0x1400818ce  lea     edx, [r9+1]; HandleCount
0x1400818d2  lea     rcx, [rsp+368h+TraceHandle]; HandleArray
0x1400818d7  call    cs:__imp_ProcessTrace
0x1400818dd  mov     r14d, eax
0x1400818e0  test    eax, eax
0x1400818e2  jnz     short loc_140081866
0x1400818e4  mov     r14d, esi
0x1400818e7  mov     r13d, esi
0x1400818ea  mov     [rsp+368h+var_348], esi
0x1400818ee  movsd   xmm9, cs:__real@408f400000000000
0x1400818f7  movsd   xmm7, cs:__real@3cb0000000000000
0x1400818ff  movsd   xmm8, cs:__real@3eb0000000000000
0x140081908  cmp     r13d, 6
0x14008190c  jnb     loc_140081873
0x140081912  mov     r12d, r13d
0x140081915  mov     [rsp+368h+var_328], r12
0x14008191a  lea     rax, ?gs_uThreadIds@D3DCommon@@3PAKA; ulong near * D3DCommon::gs_uThreadIds
0x140081921  cmp     dword ptr [rax+r12*4], 0FFFFFFFFh
0x140081926  jz      loc_140081873
0x14008192c  mov     r14d, esi
0x14008192f  xor     edx, edx; Val
0x140081931  mov     r8d, 0B8h; Size
0x140081937  lea     rcx, [rsp+368h+var_2F8]; void *
0x14008193c  call    memset_0
0x140081941  lea     rdx, [rsp+368h+var_2F8]
0x140081946  mov     rcx, r15
0x140081949  call    ?push_back@?$vector@U_AssessmentResults@D3DCommon@@V?$allocator@U_AssessmentResults@D3DCommon@@@std@@@std@@QEAAX$$QEAU_AssessmentResults@D3DCommon@@@Z; std::vector<D3DCommon::_AssessmentResults>::push_back(D3DCommon::_AssessmentResults &&)
0x14008194e  nop
0x14008194f  jmp     short loc_140081988
0x140081951  xor     esi, esi
0x140081953  lea     rbx, ?gs_AssessmentData@D3DCommon@@3PAU_AssessmentData@1@A; D3DCommon::_AssessmentData near * D3DCommon::gs_AssessmentData
0x14008195a  mov     r14d, dword ptr [rsp+368h+var_340]
0x14008195f  mov     r13d, [rsp+368h+var_348]
0x140081964  mov     r15, [rsp+368h+var_330]
0x140081969  movsd   xmm9, cs:__real@408f400000000000
0x140081972  movsd   xmm7, cs:__real@3cb0000000000000
0x14008197a  movsd   xmm8, cs:__real@3eb0000000000000
0x140081983  mov     r12, [rsp+368h+var_328]
0x140081988  mov     rdi, r12
0x14008198b  shl     rdi, 7
0x14008198f  imul    r12, 0B8h
0x140081996  mov     rcx, [r15]
0x140081999  mov     eax, [rdi+rbx+70h]
0x14008199d  mov     [r12+rcx+0A0h], eax
0x1400819a5  mov     rcx, [r15]
0x1400819a8  mov     eax, [rdi+rbx+74h]
0x1400819ac  mov     [r12+rcx+0A4h], eax
0x1400819b4  cmp     [rdi+rbx+1], sil
0x1400819b9  jz      short loc_1400819C3
0x1400819bb  cmp     [rdi+rbx], sil
0x1400819bf  mov     cl, 1
0x1400819c1  jz      short loc_1400819C6
0x1400819c3  mov     cl, sil
0x1400819c6  mov     rax, [r15]
0x1400819c9  mov     [r12+rax+0ACh], cl
0x1400819d1  cmp     dword ptr [rdi+rbx+4], 2
0x1400819d6  jbe     loc_140081D37
0x1400819dc  cmp     dword ptr [rdi+rbx+8], 2
0x1400819e1  jbe     loc_140081D37
0x1400819e7  xorps   xmm6, xmm6
0x1400819ea  cvtsi2sd xmm6, cs:?g_llPerfFreq@D3DCommon@@3_JA; __int64 D3DCommon::g_llPerfFreq
0x1400819f3  mov     eax, [rdi+rbx+4]
0x1400819f7  xorps   xmm1, xmm1
0x1400819fa  cvtsi2sd xmm1, rax
0x1400819ff  mulsd   xmm1, xmm6
0x140081a03  mov     rax, [rdi+rbx+38h]
0x140081a08  sub     rax, [rdi+rbx+10h]
0x140081a0d  xorps   xmm0, xmm0
0x140081a10  cvtsi2sd xmm0, rax
0x140081a15  divsd   xmm1, xmm0
0x140081a19  mov     rax, [r15]
0x140081a1c  movsd   qword ptr [r12+rax], xmm1
0x140081a22  mov     eax, [rdi+rbx+8]
0x140081a26  xorps   xmm1, xmm1
0x140081a29  cvtsi2sd xmm1, rax
0x140081a2e  mulsd   xmm1, xmm6
0x140081a32  mov     rax, [rdi+rbx+38h]
0x140081a37  sub     rax, [rdi+rbx+30h]
0x140081a3c  xorps   xmm0, xmm0
0x140081a3f  cvtsi2sd xmm0, rax
0x140081a44  divsd   xmm1, xmm0
0x140081a48  mov     rax, [r15]
0x140081a4b  movsd   qword ptr [r12+rax+8], xmm1
0x140081a52  mov     rax, [rdi+rbx+38h]
0x140081a57  sub     rax, [rdi+rbx+10h]
0x140081a5c  xorps   xmm0, xmm0
0x140081a5f  cvtsi2sd xmm0, rax
0x140081a64  divsd   xmm0, xmm6
0x140081a68  mov     rax, [r15]
0x140081a6b  movsd   qword ptr [r12+rax+40h], xmm0
0x140081a72  mov     rax, [rdi+rbx+38h]
0x140081a77  sub     rax, [rdi+rbx+30h]
0x140081a7c  xorps   xmm0, xmm0
0x140081a7f  cvtsi2sd xmm0, rax
0x140081a84  divsd   xmm0, xmm6
0x140081a88  mov     rax, [r15]
0x140081a8b  movsd   qword ptr [r12+rax+48h], xmm0
0x140081a92  test    r14d, r14d
0x140081a95  jns     short loc_140081AA6
0x140081a97  mov     ecx, 71h ; 'q'; this
0x140081a9c  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140081aa1  jmp     loc_140081873
0x140081aa6  mov     rcx, [r15]
0x140081aa9  mov     eax, [rdi+rbx+4]
0x140081aad  mov     [r12+rcx+10h], eax
0x140081ab2  mov     rcx, [r15]
0x140081ab5  mov     eax, [rdi+rbx+8]
0x140081ab9  mov     [r12+rcx+14h], eax
0x140081abe  mov     rcx, [r15]
0x140081ac1  mov     eax, [rdi+rbx+0Ch]
0x140081ac5  mov     [r12+rcx+18h], eax
0x140081aca  mov     ecx, [rdi+rbx+4]
0x140081ace  xor     edx, edx
0x140081ad0  mov     rax, [rdi+rbx+40h]
0x140081ad5  div     rcx
0x140081ad8  mov     rcx, rax
0x140081adb  xorps   xmm0, xmm0
0x140081ade  test    rax, rax
0x140081ae1  js      short loc_140081AEA
0x140081ae3  cvtsi2sd xmm0, rax
0x140081ae8  jmp     short loc_140081AFC
0x140081aea  shr     rax, 1
0x140081aed  and     ecx, 1
0x140081af0  or      rax, rcx
0x140081af3  cvtsi2sd xmm0, rax
0x140081af8  addsd   xmm0, xmm0
0x140081afc  mov     rax, [r15]
0x140081aff  movsd   qword ptr [r12+rax+20h], xmm0
0x140081b06  mov     rax, [rdi+rbx+40h]
0x140081b0b  mov     r8d, [rdi+rbx+4]
0x140081b10  imul    rax, rax
0x140081b14  xor     edx, edx
0x140081b16  div     r8
0x140081b19  mov     rcx, [rdi+rbx+48h]
0x140081b1e  sub     rcx, rax
0x140081b21  xorps   xmm0, xmm0
0x140081b24  js      short loc_140081B2D
0x140081b26  cvtsi2sd xmm0, rcx
0x140081b2b  jmp     short loc_140081B42
0x140081b2d  mov     rax, rcx
0x140081b30  shr     rax, 1
0x140081b33  and     ecx, 1
0x140081b36  or      rax, rcx
0x140081b39  cvtsi2sd xmm0, rax
0x140081b3e  addsd   xmm0, xmm0
0x140081b42  xorps   xmm1, xmm1
0x140081b45  cvtsi2sd xmm1, r8
0x140081b4a  divsd   xmm0, xmm1; X
0x140081b4e  call    sqrt_0
0x140081b53  mov     rax, [r15]
0x140081b56  movsd   qword ptr [r12+rax+28h], xmm0
0x140081b5d  mov     ecx, [rdi+rbx+8]
0x140081b61  xor     edx, edx
0x140081b63  mov     rax, [rdi+rbx+50h]
0x140081b68  div     rcx
0x140081b6b  mov     rcx, rax
0x140081b6e  xorps   xmm0, xmm0
0x140081b71  test    rax, rax
0x140081b74  js      short loc_140081B7D
0x140081b76  cvtsi2sd xmm0, rax
0x140081b7b  jmp     short loc_140081B8F
0x140081b7d  shr     rax, 1
0x140081b80  and     ecx, 1
0x140081b83  or      rax, rcx
0x140081b86  cvtsi2sd xmm0, rax
0x140081b8b  addsd   xmm0, xmm0
0x140081b8f  mov     rax, [r15]
0x140081b92  movsd   qword ptr [r12+rax+30h], xmm0
0x140081b99  mov     rax, [rdi+rbx+50h]
0x140081b9e  mov     r8d, [rdi+rbx+8]
0x140081ba3  imul    rax, rax
0x140081ba7  xor     edx, edx
0x140081ba9  div     r8
0x140081bac  mov     rcx, [rdi+rbx+58h]
0x140081bb1  sub     rcx, rax
0x140081bb4  xorps   xmm0, xmm0
0x140081bb7  js      short loc_140081BC0
0x140081bb9  cvtsi2sd xmm0, rcx
0x140081bbe  jmp     short loc_140081BD5
0x140081bc0  mov     rax, rcx
0x140081bc3  shr     rax, 1
0x140081bc6  and     ecx, 1
0x140081bc9  or      rax, rcx
0x140081bcc  cvtsi2sd xmm0, rax
0x140081bd1  addsd   xmm0, xmm0
0x140081bd5  xorps   xmm1, xmm1
0x140081bd8  cvtsi2sd xmm1, r8
  ... truncated ...
```
