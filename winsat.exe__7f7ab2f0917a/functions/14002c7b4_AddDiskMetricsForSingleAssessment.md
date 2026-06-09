# AddDiskMetricsForSingleAssessment

- ea: `0x14002c7b4`
- end: `0x14002d514`
- name: `AddDiskMetricsForSingleAssessment`
- size: `3424`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x14002e2ac`

## callees

- `0x140001abc`
- `0x14000367d`
- `0x140005d78`
- `0x140005f10`
- `0x1400143a0`
- `0x140016d04`
- `0x14002c7b4`
- `0x14002d6f4`
- `0x14002d7e8`
- `0x140032bd0`
- `0x140032dd4`
- `0x140034728`
- `0x1400347f4`
- `0x140035134`
- `0x140039638`
- `0x14003a360`
- `0x1400543b4`
- `0x1400544d0`
- `0x14005478c`
- `0x1400547f8`
- `0x14005497c`
- `0x1401131a6`
- `0x140113220`

## import_xrefs

- `msvcrt!wcstoul` at `0x14002c899`
- `msvcrt!wcstoul` at `0x14002c899`

## string_xrefs

- `0x14002c9d7`: `AvailableTempFileSize`
- `0x14002ccc3`: `PerDiskData/Zone/ETWData/NonAssessmentIOs/Reads/Count`
- `0x14002cd11`: `PerDiskData/Zone/ETWData/NonAssessmentIOs/Writes/Count`
- `0x14002cdac`: `PerDiskData/Zone/ETWData/AssessmentIOs/ServiceTime`
- `0x14002cdf9`: `PerDiskData/Zone/ETWData/NonAssessmentIOs/Reads/ServiceTime`
- `0x14002ce47`: `PerDiskData/Zone/ETWData/NonAssessmentIOs/Writes/ServiceTime`
- `0x14002ce94`: `PerDiskData/Zone/ETWData/NonAssessmentIOs/Flushes/ServiceTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AddDiskMetricsForSingleAssessment(__int64 a1)
{
  int v2; // r14d
  int NodeValue; // ebx
  int v4; // ebx
  int v5; // r8d
  int v6; // ebx
  int NodesText; // edi
  __int64 v8; // rcx
  void *v9; // rbx
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // rcx
  double v14; // xmm0_8
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // esi
  __int64 v19; // rcx
  void *v20; // rbx
  unsigned int v21; // r8d
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // esi
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned int v29; // ebx
  __int64 v30; // rcx
  double v31; // xmm0_8
  __int64 ExistingDiskMetricResult; // rax
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // ebx
  __int64 v36; // rcx
  double v37; // xmm0_8
  __int64 v38; // rax
  int v39; // r8d
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  int v43; // r8d
  double v44; // xmm9_8
  double v45; // xmm8_8
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  int v49; // r8d
  double v50; // xmm7_8
  double v51; // xmm6_8
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  void *v58; // rbx
  __int64 v59; // [rsp+30h] [rbp-D0h] BYREF
  const char *v60; // [rsp+38h] [rbp-C8h] BYREF
  int v61; // [rsp+40h] [rbp-C0h]
  double X; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  void *Block[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+70h] [rbp-90h]
  unsigned int v67; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v68; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v69; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v70; // [rsp+88h] [rbp-78h] BYREF
  __int64 v71; // [rsp+90h] [rbp-70h] BYREF
  const char *v72; // [rsp+98h] [rbp-68h] BYREF
  int v73; // [rsp+A0h] [rbp-60h]
  _BYTE v74[40]; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v75[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-28h]
  __int64 v77; // [rsp+E8h] [rbp-18h] BYREF
  int v78; // [rsp+F0h] [rbp-10h] BYREF
  int v79; // [rsp+F4h] [rbp-Ch]
  double v80; // [rsp+F8h] [rbp-8h] BYREF
  int v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+104h] [rbp+4h]

  v75[1] = 0;
  v77 = 0;
  v80 = 0.0;
  v82 = 0;
  *(_OWORD *)Block = 0;
  v66 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v64);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v59);
  v2 = -1;
  v81 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v78 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &X,
    L"PerDiskData/Zone/ModeFlags");
  NodeValue = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&X, 0, (unsigned int)&v64, (__int64)&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&X);
  if ( NodeValue < 0 )
  {
    v4 = 0;
LABEL_97:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v59);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v64);
    return (unsigned int)v4;
  }
  v75[0] = wcstoul(*(const wchar_t **)(v64 + 24), 0, 16);
  if ( !v75[0] )
  {
    v60 = "base\\winsat\\exe\\processresults.cpp";
    v61 = 2359;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &X,
      &qword_14012B318);
    WriteWinsatError(10099, &X, &v60);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&X);
    v4 = -2147467259;
    goto LABEL_97;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &X,
    L"PerDiskData/Zone/IoSize");
  v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&X, 0, (unsigned int)&v77, (__int64)&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&X);
  if ( v4 < 0 )
  {
    v61 = 2369;
LABEL_96:
    v60 = "base\\winsat\\exe\\processresults.cpp";
    WriteWinsatError(10099, &v59, &v60);
    goto LABEL_97;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &X,
    L"PerDiskData/Zone/ETWData/AssessmentIOs/ActualInterferencePercentage");
  v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&X, 0, (unsigned int)&v77 + 4, (__int64)&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&X);
  if ( v4 < 0 )
  {
    v61 = 2376;
    goto LABEL_96;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &X,
    L"PerDiskData/Zone/ETWData/AssessmentIOs/PermittedInterferencePercentage");
  v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&X, 0, (unsigned int)&v78, (__int64)&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&X);
  if ( v4 < 0 )
  {
    v61 = 2382;
    goto LABEL_96;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v69,
    L"AvailableTempFileSize");
  LOBYTE(v5) = 1;
  v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v69, v5, (unsigned int)&X, (__int64)&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v69);
  if ( v4 < 0 )
  {
    v61 = 2399;
    goto LABEL_96;
  }
  v6 = v75[0];
  if ( (v75[0] & 0x3000000) != 0 )
  {
    v79 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &X,
      L"PerDiskData/Zone/ETWData/Throughput");
    NodesText = mlib::XmlDOM::GetNodesText(a1, &X, Block, &v59);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&X);
    if ( NodesText < 0 )
    {
      v61 = 2416;
LABEL_16:
      v60 = "base\\winsat\\exe\\processresults.cpp";
      WriteWinsatError(10099, &v59, &v60);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v59);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v64);
      v9 = Block[0];
      if ( Block[0] )
      {
        std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
          v8,
          Block[0],
          Block[1]);
        operator delete(v9);
      }
      return (unsigned int)NodesText;
    }
    v80 = AverageTextValues(Block);
    v12 = v6 & 0x1F00000F;
    if ( v12 == 16777217 )
    {
      if ( (_DWORD)v77 != 0x10000 )
        goto LABEL_29;
      ScaleAScoreAscending_0(v11, 6);
      v14 = Soften(v13, &qword_14012B318);
      v81 = 6771;
      goto LABEL_28;
    }
    if ( v12 == 16777218 )
    {
      if ( (_DWORD)v77 != 0x4000 )
        goto LABEL_29;
      ScaleAScoreAscending_0(v11, 7);
      v14 = Soften(v15, &qword_14012B318);
      v81 = 6766;
      goto LABEL_28;
    }
    if ( v12 == 33554433 && (_DWORD)v77 == 0x10000 )
    {
      ScaleAScoreAscending_0(v11, 6);
      v14 = Soften(v16, &qword_14012B318);
      v81 = 6772;
LABEL_28:
      *(double *)si128.m128i_i64 = v14;
    }
LABEL_29:
    if ( !FindExistingDiskMetricResult(v75) )
    {
LABEL_99:
      std::vector<DiskMetric>::push_back(v17, v75);
      goto LABEL_100;
    }
    goto LABEL_100;
  }
  if ( (v75[0] & 0x10000000) == 0 )
  {
    if ( (v75[0] & 0x4000000) == 0 )
    {
      if ( (v75[0] & 0x8000000) != 0 )
      {
        X = 0.0;
        v79 = 4;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v60,
          L"PerDiskData/Zone/Statistics/AverageIOTime");
        v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v60, v39, (unsigned int)&v80, (__int64)&v59);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v60);
        if ( v4 < 0 )
        {
          v61 = 2688;
          goto LABEL_96;
        }
        v81 = 6767;
        ScaleAScoreDescending_0(v40, 13);
        si128.m128i_i64[0] = Soften(v41, &qword_14012B318);
        std::vector<DiskMetric>::push_back(v42, v75);
        PenaltyFactor::Initialize((PenaltyFactor *)v74, 15.0, 16.0, 100.0);
        v81 = 6769;
        v79 = 6;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v60,
          L"PerDiskData/Zone/Statistics/DecayingAverage");
        v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v60, v43, (unsigned int)&X, (__int64)&v59);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v60);
        if ( v4 < 0 )
        {
          v61 = 2706;
          goto LABEL_96;
        }
        v44 = v80;
        v45 = pow_0(v80 * X, 0.3333333333333333);
        v80 = v45;
        ScaleAScoreDescending_0(v46, 14);
        si128.m128i_i64[0] = Soften(v47, &qword_14012B318);
        si128.m128i_i64[1] = PenaltyFactor::Compute((PenaltyFactor *)v74, v45);
        std::vector<DiskMetric>::push_back(v48, v75);
        PenaltyFactor::Initialize((PenaltyFactor *)v74, 22.0, 30.0, 100.0);
        v81 = 6770;
        v79 = 5;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v60,
          L"PerDiskData/Zone/Statistics/SumNormalizedSquares");
        v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v60, v49, (unsigned int)&X, (__int64)&v59);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v60);
        if ( v4 < 0 )
        {
          v61 = 2727;
          goto LABEL_96;
        }
        v50 = *(double *)&si128.m128i_i64[1] + 0.0;
        v51 = sqrt_0(X) * v44;
        v80 = v51;
        ScaleAScoreDescending_0(v52, 15);
        si128.m128i_i64[0] = Soften(v53, &qword_14012B318);
        si128.m128i_i64[1] = PenaltyFactor::Compute((PenaltyFactor *)v74, v51);
        std::vector<DiskMetric>::push_back(v54, v75);
        v81 = 6768;
        v79 = 7;
        v80 = v51 * v45;
        ScaleAScoreDescending_0(v55, 16);
        si128.m128i_i64[0] = Soften(v56, &qword_14012B318);
        si128.m128i_i64[1] = fmin(1.0, v50 + *(double *)&si128.m128i_i64[1]);
        goto LABEL_99;
      }
LABEL_100:
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v59);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v64);
      v58 = Block[0];
      if ( Block[0] )
      {
        std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
          v57,
          Block[0],
          Block[1]);
        operator delete(v58);
      }
      return 0;
    }
    v79 = 1;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v60,
      L"PerDiskData/Zone/Statistics/Mean");
    v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v60, 0, (unsigned int)&v80, (__int64)&v59);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v60);
    if ( v4 < 0 )
    {
      v61 = 2600;
      goto LABEL_96;
    }
    v24 = v75[0];
    if ( (v75[0] & 0x4000000) != 0 )
    {
      if ( (v75[0] & 1) != 0 )
      {
        v25 = 9;
        v2 = 6764;
        goto LABEL_73;
      }
      if ( (v75[0] & 2) == 0 )
      {
        v72 = "base\\winsat\\exe\\processresults.cpp";
        v73 = 2614;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v60,
          &qword_14012B318);
        WriteWinsatError(10099, &v60, &v72);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v60);
        goto LABEL_97;
      }
      v2 = 6774;
    }
    v25 = 10;
LABEL_73:
    v81 = v2;
    ScaleAScoreDescending_0(v23, v25);
    si128.m128i_i64[0] = Soften(v26, &qword_14012B318);
    if ( !FindExistingDiskMetricResult(v75) )
    {
      std::vector<DiskMetric>::push_back(v27, v75);
      v24 = v75[0];
    }
    v79 = 2;
    v75[0] = v24 & 0xFFFFFFF0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v60,
      L"PerDiskData/Zone/Statistics/Percentile95th");
    v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v60, 0, (unsigned int)&v80, (__int64)&v59);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v60);
    if ( v4 < 0 )
    {
      v61 = 2634;
      goto LABEL_96;
    }
    v81 = 6763;
    v29 = LODWORD(v80);
    ScaleAScoreDescending_0(v28, 11);
    v31 = Soften(v30, &qword_14012B318);
    *(double *)si128.m128i_i64 = v31;
    ExistingDiskMetricResult = FindExistingDiskMetricResult(v75);
    if ( ExistingDiskMetricResult )
    {
      if ( *(_DWORD *)(ExistingDiskMetricResult + 40) > v29 )
        v29 = *(_DWORD *)(ExistingDiskMetricResult + 40);
      *(_DWORD *)(ExistingDiskMetricResult + 40) = v29;
      *(double *)(ExistingDiskMetricResult + 8) = fmin(*(double *)(ExistingDiskMetricResult + 8), v31);
    }
    else
    {
      std::vector<DiskMetric>::push_back(v33, v75);
    }
    v79 = 3;
    v75[0] &= 0xFFFFFFF0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v60,
      L"PerDiskData/Zone/Statistics/Max");
    v4 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v60, 0, (unsigned int)&v80, (__int64)&v59);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v60);
    if ( v4 < 0 )
    {
      v61 = 2658;
      goto LABEL_96;
    }
    v81 = 6762;
    v35 = LODWORD(v80);
    ScaleAScoreDescending_0(v34, 12);
    v37 = Soften(v36, &qword_14012B318);
    *(double *)si128.m128i_i64 = v37;
    v38 = FindExistingDiskMetricResult(v75);
    if ( v38 )
    {
      if ( *(_DWORD *)(v38 + 40) > v35 )
        v35 = *(_DWORD *)(v38 + 40);
      *(_DWORD *)(v38 + 40) = v35;
      *(double *)(v38 + 8) = fmin(*(double *)(v38 + 8), v37);
      goto LABEL_100;
    }
    goto LABEL_99;
  }
  LODWORD(X) = 0;
  LODWORD(v69) = 0;
  v68 = 0;
  v67 = 0;
  v60 = 0;
  v72 = 0;
  v71 = 0;
  v70 = 0;
  v79 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v63,
    L"PerDiskData/Zone/Throughput");
  v18 = mlib::XmlDOM::GetNodesText(a1, &v63, Block, &v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
  if ( v18 >= 0 )
  {
    v80 = AverageTextValues(Block);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v63,
      L"PerDiskData/Zone/ETWData/AssessmentIOs/Count");
    v18 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v63, 0, (unsigned int)&v67, (__int64)&v59);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
    if ( v18 >= 0 )
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v63,
        L"PerDiskData/Zone/ETWData/NonAssessmentIOs/Reads/Count");
      v18 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v63, 0, (unsigned int)&X, (__int64)&v59);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
      if ( v18 >= 0 )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v63,
          L"PerDiskData/Zone/ETWData/NonAssessmentIOs/Writes/Count");
        v18 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v63, 0, (unsigned int)&v69, (__int64)&v59);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
        if ( v18 >= 0 )
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v63,
            L"PerDiskData/Zone/ETWData/NonAssessmentIOs/Flushes/Count");
          v18 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v63, 0, (unsigned int)&v68, (__int64)&v59);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
          if ( v18 >= 0 )
          {
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              &v63,
              L"PerDiskData/Zone/ETWData/AssessmentIOs/ServiceTime");
            v18 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v63, 0, (unsigned int)&v70, (__int64)&v59);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
            if ( v18 >= 0 )
            {
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v63,
                L"PerDiskData/Zone/ETWData/NonAssessmentIOs/Reads/ServiceTime");
              v18 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v63, 0, (unsigned int)&v60, (__int64)&v59);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
              if ( v18 >= 0 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v63,
                  L"PerDiskData/Zone/ETWData/NonAssessmentIOs/Writes/ServiceTime");
                v18 = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v63, 0, (unsigned int)&v72, (__int64)&v59);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
                if ( v18 >= 0 )
                {
                  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    &v63,
                    L"PerDiskData/Zone/ETWData/NonAssessmentIOs/Flushes/ServiceTime");
                  NodesText = mlib::XmlDOM::GetNodeValue(a1, (unsigned int)&v63, 0, (unsigned int)&v71, (__int64)&v59);
                  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v63);
                  if ( NodesText < 0 )
                  {
                    v61 = 2561;
                    goto LABEL_16;
                  }
                  if ( v67 )
                  {
                    v21 = 100 * (LODWORD(X) + (unsigned int)v69 + (unsigned __int64)v68) / v67;
                    if ( v21 >= 0x64 )
                      v21 = 100;
                  }
                  else
                  {
                    v21 = 0;
                  }
                  if ( v70 )
                  {
                    v22 = 100 * (__int64)&v72[v71 + (_QWORD)v60] / v70;
                    if ( (unsigned int)v22 >= 0x64 )
                      LODWORD(v22) = 100;
                  }
                  else
                  {
                    LODWORD(v22) = 0;
                  }
                  HIDWORD(v77) = v22 | (v21 << 16);
                  goto LABEL_29;
                }
                v61 = 2550;
              }
              else
              {
                v61 = 2539;
              }
            }
            else
            {
              v61 = 2528;
            }
          }
          else
          {
            v61 = 2518;
          }
        }
        else
        {
          v61 = 2508;
        }
      }
      else
      {
        v61 = 2498;
      }
    }
    else
    {
      v61 = 2488;
    }
  }
  else
  {
    v61 = 2472;
  }
  v60 = "base\\winsat\\exe\\processresults.cpp";
  WriteWinsatError(10099, &v59, &v60);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v59);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v64);
  v20 = Block[0];
  if ( Block[0] )
  {
    std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
      v19,
      Block[0],
      Block[1]);
    operator delete(v20);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14002c7b4  mov     rax, rsp
0x14002c7b7  push    rbp
0x14002c7b8  push    rbx
0x14002c7b9  push    rsi
0x14002c7ba  push    rdi
0x14002c7bb  push    r14
0x14002c7bd  push    r15
0x14002c7bf  lea     rbp, [rsp-58h]
0x14002c7c4  sub     rsp, 158h
0x14002c7cb  movaps  xmmword ptr [rax-48h], xmm6
0x14002c7cf  movaps  xmmword ptr [rax-58h], xmm7
0x14002c7d3  movaps  xmmword ptr [rax-68h], xmm8
0x14002c7d8  movaps  xmmword ptr [rax-78h], xmm9
0x14002c7dd  mov     rax, cs:__security_cookie
0x14002c7e4  xor     rax, rsp
0x14002c7e7  mov     [rbp+80h+var_78], rax
0x14002c7eb  mov     rdi, rcx
0x14002c7ee  xor     r15d, r15d
0x14002c7f1  mov     [rbp+80h+var_AC], r15d
0x14002c7f5  mov     [rbp+80h+var_98], r15
0x14002c7f9  mov     [rbp+80h+var_88], r15
0x14002c7fd  mov     [rbp+80h+var_7C], r15d
0x14002c801  xorps   xmm0, xmm0
0x14002c804  movdqu  xmmword ptr [rsp+180h+Block], xmm0
0x14002c80a  mov     [rsp+180h+var_110], r15
0x14002c80f  lea     rcx, [rsp+180h+var_128]
0x14002c814  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x14002c819  nop
0x14002c81a  lea     rcx, [rsp+180h+var_150]
0x14002c81f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x14002c824  nop
0x14002c825  or      r14d, 0FFFFFFFFh
0x14002c829  mov     [rbp+80h+var_80], r14d
0x14002c82d  movdqa  xmm0, cs:__xmm@00000000000000007fefffffffffffff
0x14002c835  movups  [rbp+80h+var_A8], xmm0
0x14002c839  mov     [rbp+80h+var_90], r15d
0x14002c83d  lea     rdx, aPerdiskdataZon_6; "PerDiskData/Zone/ModeFlags"
0x14002c844  lea     rcx, [rsp+180h+X]
0x14002c849  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002c84e  nop
0x14002c84f  lea     rax, [rsp+180h+var_150]
0x14002c854  mov     [rsp+180h+var_160], rax
0x14002c859  lea     r9, [rsp+180h+var_128]
0x14002c85e  xor     r8d, r8d
0x14002c861  lea     rdx, [rsp+180h+X]
0x14002c866  mov     rcx, rdi
0x14002c869  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAV42@PEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002c86e  mov     ebx, eax
0x14002c870  lea     rcx, [rsp+180h+X]
0x14002c875  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002c87a  test    ebx, ebx
0x14002c87c  jns     short loc_14002C886
0x14002c87e  mov     ebx, r15d
0x14002c881  jmp     loc_14002D3E0
0x14002c886  mov     esi, 10h
0x14002c88b  mov     r8d, esi; Radix
0x14002c88e  xor     edx, edx; EndPtr
0x14002c890  mov     rcx, [rsp+180h+var_128]
0x14002c895  mov     rcx, [rcx+18h]; String
0x14002c899  call    cs:__imp_wcstoul
0x14002c89f  mov     [rbp+80h+var_B0], eax
0x14002c8a2  lea     rcx, [rsp+180h+X]
0x14002c8a7  test    eax, eax
0x14002c8a9  jnz     short loc_14002C8F5
0x14002c8ab  lea     rax, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14002c8b2  mov     [rsp+180h+var_148], rax
0x14002c8b7  mov     [rsp+180h+var_140], 937h
0x14002c8bf  lea     rdx, qword_14012B318
0x14002c8c6  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002c8cb  nop
0x14002c8cc  mov     ecx, 2773h
0x14002c8d1  lea     r8, [rsp+180h+var_148]
0x14002c8d6  lea     rdx, [rsp+180h+X]
0x14002c8db  call    ?WriteWinsatError@@YAXGAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEBVEfln@2@@Z; WriteWinsatError(ushort,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::Efln const &)
0x14002c8e0  nop
0x14002c8e1  lea     rcx, [rsp+180h+X]
0x14002c8e6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002c8eb  mov     ebx, 80004005h
0x14002c8f0  jmp     loc_14002D3E0
0x14002c8f5  lea     rdx, aPerdiskdataZon_5; "PerDiskData/Zone/IoSize"
0x14002c8fc  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002c901  nop
0x14002c902  lea     rax, [rsp+180h+var_150]
0x14002c907  mov     [rsp+180h+var_160], rax
0x14002c90c  lea     r9, [rbp+80h+var_98]
0x14002c910  xor     r8d, r8d
0x14002c913  lea     rdx, [rsp+180h+X]
0x14002c918  mov     rcx, rdi
0x14002c91b  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAKPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ulong &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002c920  mov     ebx, eax
0x14002c922  lea     rcx, [rsp+180h+X]
0x14002c927  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002c92c  test    ebx, ebx
0x14002c92e  jns     short loc_14002C93D
0x14002c930  mov     [rsp+180h+var_140], 941h
0x14002c938  jmp     loc_14002D3BF
0x14002c93d  lea     rdx, aPerdiskdataZon_11; "PerDiskData/Zone/ETWData/AssessmentIOs/"...
0x14002c944  lea     rcx, [rsp+180h+X]
0x14002c949  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002c94e  nop
0x14002c94f  lea     rax, [rsp+180h+var_150]
0x14002c954  mov     [rsp+180h+var_160], rax
0x14002c959  lea     r9, [rbp+80h+var_98+4]
0x14002c95d  xor     r8d, r8d
0x14002c960  lea     rdx, [rsp+180h+X]
0x14002c965  mov     rcx, rdi
0x14002c968  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAKPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ulong &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002c96d  mov     ebx, eax
0x14002c96f  lea     rcx, [rsp+180h+X]
0x14002c974  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002c979  test    ebx, ebx
0x14002c97b  jns     short loc_14002C98A
0x14002c97d  mov     [rsp+180h+var_140], 948h
0x14002c985  jmp     loc_14002D3BF
0x14002c98a  lea     rdx, aPerdiskdataZon_4; "PerDiskData/Zone/ETWData/AssessmentIOs/"...
0x14002c991  lea     rcx, [rsp+180h+X]
0x14002c996  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002c99b  nop
0x14002c99c  lea     rax, [rsp+180h+var_150]
0x14002c9a1  mov     [rsp+180h+var_160], rax
0x14002c9a6  lea     r9, [rbp+80h+var_90]
0x14002c9aa  xor     r8d, r8d
0x14002c9ad  lea     rdx, [rsp+180h+X]
0x14002c9b2  mov     rcx, rdi
0x14002c9b5  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAKPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ulong &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002c9ba  mov     ebx, eax
0x14002c9bc  lea     rcx, [rsp+180h+X]
0x14002c9c1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002c9c6  test    ebx, ebx
0x14002c9c8  jns     short loc_14002C9D7
0x14002c9ca  mov     [rsp+180h+var_140], 94Eh
0x14002c9d2  jmp     loc_14002D3BF
0x14002c9d7  lea     rdx, aAvailabletempf; "AvailableTempFileSize"
0x14002c9de  lea     rcx, [rbp+80h+var_100]
0x14002c9e2  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002c9e7  nop
0x14002c9e8  lea     rax, [rsp+180h+var_150]
0x14002c9ed  mov     [rsp+180h+var_160], rax
0x14002c9f2  lea     r9, [rsp+180h+X]
0x14002c9f7  mov     r8b, 1
0x14002c9fa  lea     rdx, [rbp+80h+var_100]
0x14002c9fe  mov     rcx, rdi
0x14002ca01  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAKPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ulong &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002ca06  mov     ebx, eax
0x14002ca08  lea     rcx, [rbp+80h+var_100]
0x14002ca0c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ca11  test    ebx, ebx
0x14002ca13  jns     short loc_14002CA22
0x14002ca15  mov     [rsp+180h+var_140], 95Fh
0x14002ca1d  jmp     loc_14002D3BF
0x14002ca22  mov     ebx, [rbp+80h+var_B0]
0x14002ca25  test    ebx, 3000000h
0x14002ca2b  jz      loc_14002CB96
0x14002ca31  mov     [rbp+80h+var_8C], r15d
0x14002ca35  lea     rdx, aPerdiskdataZon_10; "PerDiskData/Zone/ETWData/Throughput"
0x14002ca3c  lea     rcx, [rsp+180h+X]
0x14002ca41  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002ca46  nop
0x14002ca47  lea     r9, [rsp+180h+var_150]
0x14002ca4c  lea     r8, [rsp+180h+Block]
0x14002ca51  lea     rdx, [rsp+180h+X]
0x14002ca56  mov     rcx, rdi
0x14002ca59  call    ?GetNodesText@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAV42@@Z; mlib::XmlDOM::GetNodesText(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002ca5e  mov     edi, eax
0x14002ca60  lea     rcx, [rsp+180h+X]
0x14002ca65  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ca6a  test    edi, edi
0x14002ca6c  jns     short loc_14002CAD3
0x14002ca6e  mov     [rsp+180h+var_140], 970h
0x14002ca76  lea     rax, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14002ca7d  mov     [rsp+180h+var_148], rax
0x14002ca82  mov     ecx, 2773h
0x14002ca87  lea     r8, [rsp+180h+var_148]
0x14002ca8c  lea     rdx, [rsp+180h+var_150]
0x14002ca91  call    ?WriteWinsatError@@YAXGAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEBVEfln@2@@Z; WriteWinsatError(ushort,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::Efln const &)
0x14002ca96  nop
0x14002ca97  lea     rcx, [rsp+180h+var_150]
0x14002ca9c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002caa1  nop
0x14002caa2  lea     rcx, [rsp+180h+var_128]
0x14002caa7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002caac  nop
0x14002caad  mov     rbx, [rsp+180h+Block]
0x14002cab2  test    rbx, rbx
0x14002cab5  jz      short loc_14002CACC
0x14002cab7  mov     r8, [rsp+180h+Block+8]
0x14002cabc  mov     rdx, rbx
0x14002cabf  call    ?_Destroy@?$vector@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002cac4  mov     rcx, rbx; Block
0x14002cac7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002cacc  mov     eax, edi
0x14002cace  jmp     loc_14002D4E0
0x14002cad3  lea     rcx, [rsp+180h+Block]
0x14002cad8  call    AverageTextValues
0x14002cadd  movsd   [rbp+80h+var_88], xmm0
0x14002cae2  and     ebx, 1F00000Fh
0x14002cae8  cmp     ebx, 1000001h
0x14002caee  jnz     short loc_14002CB1C
0x14002caf0  cmp     dword ptr [rbp+80h+var_98], 10000h
0x14002caf7  jnz     loc_14002CB7F
0x14002cafd  mov     edx, 6
0x14002cb02  call    ScaleAScoreAscending_0
0x14002cb07  lea     rdx, qword_14012B318
0x14002cb0e  call    Soften
0x14002cb13  mov     [rbp+80h+var_80], 1A73h
0x14002cb1a  jmp     short loc_14002CB7A
0x14002cb1c  cmp     ebx, 1000002h
0x14002cb22  jnz     short loc_14002CB4C
0x14002cb24  cmp     dword ptr [rbp+80h+var_98], 4000h
0x14002cb2b  jnz     short loc_14002CB7F
0x14002cb2d  mov     edx, 7
0x14002cb32  call    ScaleAScoreAscending_0
0x14002cb37  lea     rdx, qword_14012B318
0x14002cb3e  call    Soften
0x14002cb43  mov     [rbp+80h+var_80], 1A6Eh
0x14002cb4a  jmp     short loc_14002CB7A
0x14002cb4c  cmp     ebx, 2000001h
0x14002cb52  jnz     short loc_14002CB7F
0x14002cb54  cmp     dword ptr [rbp+80h+var_98], 10000h
0x14002cb5b  jnz     short loc_14002CB7F
0x14002cb5d  mov     edx, 6
0x14002cb62  call    ScaleAScoreAscending_0
0x14002cb67  lea     rdx, qword_14012B318
0x14002cb6e  call    Soften
0x14002cb73  mov     [rbp+80h+var_80], 1A74h
0x14002cb7a  movsd   qword ptr [rbp+80h+var_A8], xmm0
0x14002cb7f  lea     rcx, [rbp+80h+var_B0]
0x14002cb83  call    FindExistingDiskMetricResult
0x14002cb88  test    rax, rax
0x14002cb8b  jnz     loc_14002D4A9
0x14002cb91  jmp     loc_14002D49F
0x14002cb96  bt      ebx, 1Ch
0x14002cb9a  jnb     loc_14002CF55
0x14002cba0  mov     dword ptr [rsp+180h+X], r15d
0x14002cba5  mov     dword ptr [rbp+80h+var_100], r15d
0x14002cba9  mov     [rsp+180h+var_104], r15d
0x14002cbae  mov     [rsp+180h+var_108], r15d
0x14002cbb3  mov     [rsp+180h+var_148], r15
0x14002cbb8  mov     [rbp+80h+var_E8], r15
0x14002cbbc  mov     [rbp+80h+var_F0], r15
0x14002cbc0  mov     [rbp+80h+var_F8], r15
0x14002cbc4  mov     [rbp+80h+var_8C], r15d
0x14002cbc8  lea     rdx, aPerdiskdataZon_0; "PerDiskData/Zone/Throughput"
0x14002cbcf  lea     rcx, [rsp+180h+var_130]
0x14002cbd4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002cbd9  nop
0x14002cbda  lea     r9, [rsp+180h+var_150]
0x14002cbdf  lea     r8, [rsp+180h+Block]
0x14002cbe4  lea     rdx, [rsp+180h+var_130]
0x14002cbe9  mov     rcx, rdi
0x14002cbec  call    ?GetNodesText@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAV42@@Z; mlib::XmlDOM::GetNodesText(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002cbf1  mov     esi, eax
0x14002cbf3  lea     rcx, [rsp+180h+var_130]
0x14002cbf8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002cbfd  test    esi, esi
0x14002cbff  jns     short loc_14002CC66
0x14002cc01  mov     [rsp+180h+var_140], 9A8h
0x14002cc09  lea     rax, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14002cc10  mov     [rsp+180h+var_148], rax
0x14002cc15  mov     ecx, 2773h
0x14002cc1a  lea     r8, [rsp+180h+var_148]
0x14002cc1f  lea     rdx, [rsp+180h+var_150]
0x14002cc24  call    ?WriteWinsatError@@YAXGAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEBVEfln@2@@Z; WriteWinsatError(ushort,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::Efln const &)
0x14002cc29  nop
0x14002cc2a  lea     rcx, [rsp+180h+var_150]
0x14002cc2f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002cc34  nop
0x14002cc35  lea     rcx, [rsp+180h+var_128]
0x14002cc3a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002cc3f  nop
0x14002cc40  mov     rbx, [rsp+180h+Block]
0x14002cc45  test    rbx, rbx
0x14002cc48  jz      short loc_14002CC5F
0x14002cc4a  mov     r8, [rsp+180h+Block+8]
0x14002cc4f  mov     rdx, rbx
0x14002cc52  call    ?_Destroy@?$vector@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002cc57  mov     rcx, rbx; Block
0x14002cc5a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002cc5f  mov     eax, esi
0x14002cc61  jmp     loc_14002D4E0
0x14002cc66  lea     rcx, [rsp+180h+Block]
0x14002cc6b  call    AverageTextValues
0x14002cc70  movsd   [rbp+80h+var_88], xmm0
0x14002cc75  lea     rdx, aPerdiskdataZon_9; "PerDiskData/Zone/ETWData/AssessmentIOs/"...
0x14002cc7c  lea     rcx, [rsp+180h+var_130]
0x14002cc81  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002cc86  nop
0x14002cc87  lea     rax, [rsp+180h+var_150]
0x14002cc8c  mov     [rsp+180h+var_160], rax
0x14002cc91  lea     r9, [rsp+180h+var_108]
0x14002cc96  xor     r8d, r8d
0x14002cc99  lea     rdx, [rsp+180h+var_130]
0x14002cc9e  mov     rcx, rdi
0x14002cca1  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAKPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ulong &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x14002cca6  mov     esi, eax
0x14002cca8  lea     rcx, [rsp+180h+var_130]
0x14002ccad  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002ccb2  test    esi, esi
0x14002ccb4  jns     short loc_14002CCC3
0x14002ccb6  mov     [rsp+180h+var_140], 9B8h
  ... truncated ...
```
