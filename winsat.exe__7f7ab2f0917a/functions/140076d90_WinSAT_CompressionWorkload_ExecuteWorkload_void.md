# WinSAT::CompressionWorkload::ExecuteWorkload(void)

- ea: `0x140076d90`
- end: `0x140078adb`
- name: `?ExecuteWorkload@CompressionWorkload@WinSAT@@MEAAKXZ`
- size: `7499`
- prototype: `unsigned int __fastcall(WinSAT::CompressionWorkload *__hidden this)`
- caller_count: `0`
- callee_count: `27`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004170`
- `0x140004348`
- `0x140007f14`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x140011f58`
- `0x140016588`
- `0x140017af0`
- `0x1400191c0`
- `0x14002093c`
- `0x14004fce4`
- `0x14004fe00`
- `0x1400530a8`
- `0x140058488`
- `0x1400584b0`
- `0x140058818`
- `0x140059010`
- `0x14005cc74`
- `0x14005ed80`
- `0x14007616c`
- `0x1400761b4`
- `0x140076d90`
- `0x140079b30`
- `0x140113220`
- `0x1401180e8`
- `0x14011860c`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140076e0a`
- `KERNEL32!GetTickCount` at `0x140076f30`
- `KERNEL32!GetTickCount` at `0x140077272`
- `KERNEL32!GetTickCount` at `0x14007738d`
- `KERNEL32!GetTickCount` at `0x1400773b6`
- `KERNEL32!GetTickCount` at `0x140076e0a`
- `KERNEL32!GetTickCount` at `0x140076f30`
- `KERNEL32!GetTickCount` at `0x140077272`
- `KERNEL32!GetTickCount` at `0x14007738d`
- `KERNEL32!GetTickCount` at `0x1400773b6`
- `KERNEL32!EnterCriticalSection` at `0x1400771b9`
- `KERNEL32!EnterCriticalSection` at `0x1400772da`
- `KERNEL32!EnterCriticalSection` at `0x140077768`
- `KERNEL32!EnterCriticalSection` at `0x1400789b0`
- `KERNEL32!EnterCriticalSection` at `0x1400771b9`
- `KERNEL32!EnterCriticalSection` at `0x1400772da`
- `KERNEL32!EnterCriticalSection` at `0x140077768`
- `KERNEL32!EnterCriticalSection` at `0x1400789b0`
- `KERNEL32!LeaveCriticalSection` at `0x140077219`
- `KERNEL32!LeaveCriticalSection` at `0x14007899b`
- `KERNEL32!LeaveCriticalSection` at `0x140078a84`
- `KERNEL32!LeaveCriticalSection` at `0x140077219`
- `KERNEL32!LeaveCriticalSection` at `0x14007899b`
- `KERNEL32!LeaveCriticalSection` at `0x140078a84`
- `KERNEL32!Sleep` at `0x140077268`
- `KERNEL32!Sleep` at `0x140077268`
- `KERNEL32!SetLastError` at `0x140078a98`
- `KERNEL32!SetLastError` at `0x140078a98`
- `ntdll!RtlCompressBuffer` at `0x14007701d`
- `ntdll!RtlCompressBuffer` at `0x14007701d`
- `ntdll!RtlDecompressBuffer` at `0x14007709e`
- `ntdll!RtlDecompressBuffer` at `0x14007709e`
- `ntdll!RtlNtStatusToDosError` at `0x14007718e`
- `ntdll!RtlNtStatusToDosError` at `0x1400772af`
- `ntdll!RtlNtStatusToDosError` at `0x14007718e`
- `ntdll!RtlNtStatusToDosError` at `0x1400772af`

## string_xrefs

- `0x1400771c2`: `base\winsat\cpu\compression.cpp`
- `0x1400772e3`: `base\winsat\cpu\compression.cpp`
- `0x1400789ce`: `base\winsat\cpu\compression.cpp`
- `0x140078a2f`: `base\winsat\cpu\compression.cpp`

## pseudocode

```c
__int64 __fastcall WinSAT::CompressionWorkload::ExecuteWorkload(WinSAT::CompressionWorkload *this)
{
  _DWORD *v1; // rax
  int v3; // ecx
  unsigned int v4; // edx
  DWORD TickCount; // eax
  __int64 v6; // rcx
  __int64 v7; // r13
  unsigned __int64 v8; // r15
  char v9; // r14
  double v10; // xmm0_8
  int v11; // edx
  double v12; // xmm0_8
  __int64 v13; // rdx
  int **v14; // rdi
  SampleManager *v15; // r12
  int **v16; // rbx
  int **v17; // r10
  SampleManager *v18; // rdi
  unsigned __int64 v19; // rcx
  int **v20; // r10
  DWORD v21; // eax
  volatile signed __int32 **v22; // rcx
  unsigned int v23; // eax
  volatile signed __int32 **v24; // r14
  volatile signed __int32 **v25; // r8
  unsigned int v26; // r14d
  unsigned __int8 *v27; // rax
  __int64 v28; // r8
  UCHAR *v29; // r10
  int v30; // ecx
  unsigned __int64 v31; // r9
  int v32; // edi
  int v33; // ecx
  NTSTATUS v34; // ecx
  int v35; // eax
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rbx
  ULONG v38; // eax
  __int64 v39; // rbx
  const unsigned __int16 *v40; // rax
  __int64 *v41; // rax
  __int64 *v42; // rax
  __int64 *v43; // rax
  int *v44; // rax
  volatile signed __int32 *v45; // rax
  unsigned int v46; // eax
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  int v49; // r14d
  ULONG v50; // eax
  __int64 v51; // rbx
  const unsigned __int16 *v52; // rax
  __int64 *v53; // rax
  __int64 *v54; // rax
  __int64 *v55; // rax
  mlib *v56; // rcx
  unsigned int v57; // r12d
  __int64 v58; // rbx
  mlib *v59; // rcx
  __int64 PerformanceFrequency64; // rax
  double v61; // xmm1_8
  __int64 v62; // r14
  double v63; // xmm0_8
  double v64; // xmm0_8
  __int64 v65; // rbx
  double v66; // xmm6_8
  __int64 v67; // rcx
  double v68; // xmm6_8
  double v69; // xmm2_8
  __int64 v70; // rdx
  __int64 v71; // rcx
  double v72; // xmm7_8
  double v73; // xmm7_8
  __int64 v74; // r15
  double v75; // xmm0_8
  __int64 v76; // r14
  double v77; // xmm7_8
  double v78; // xmm6_8
  double v79; // xmm3_8
  double v80; // xmm3_8
  __int64 v81; // rcx
  double v82; // xmm0_8
  unsigned __int64 v83; // rax
  double v84; // xmm4_8
  __int64 v85; // rcx
  double v86; // xmm8_8
  __int64 v87; // rcx
  double v88; // xmm8_8
  double v89; // xmm9_8
  __int64 v90; // rax
  __int64 v91; // rcx
  double v92; // xmm9_8
  double v93; // xmm5_8
  double v94; // xmm1_8
  __int64 v95; // rcx
  double v96; // xmm0_8
  __int64 *v97; // rax
  __int64 *v98; // rax
  __int64 *v99; // rax
  __int64 *v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 *v103; // rax
  __int64 *v104; // rax
  __int64 *v105; // rax
  __int64 *v106; // rax
  __int64 *v107; // rax
  __int64 v108; // rax
  __int64 *v109; // rax
  __int64 v110; // rax
  __int64 *v111; // rax
  __int64 v112; // rax
  __int64 *v113; // rax
  __int64 *v114; // rax
  __int64 *v115; // rax
  __int64 *v116; // rax
  __int64 *v117; // rax
  __int64 *v118; // rax
  __int64 *v119; // rax
  __int64 *v120; // rax
  __int64 *v121; // rax
  __int64 *v122; // rax
  __int64 *v123; // rax
  __int64 *v124; // rax
  __int64 *v125; // rax
  __int64 *v126; // rax
  __int64 *v127; // rax
  __int64 *v128; // rax
  __int64 v129; // rax
  __int64 *v130; // rax
  __int64 *v131; // rax
  __int64 *v132; // rax
  const wchar_t *v133; // rdx
  __int64 *v134; // rax
  __int64 *v135; // rax
  __int64 *v136; // rax
  __int64 *v137; // rax
  __int64 *v138; // rax
  __int64 *v139; // rax
  __int64 *v140; // rax
  __int64 *v141; // rax
  __int64 *v142; // rax
  __int64 *v143; // rax
  __int64 *v144; // rax
  __int64 *v145; // rax
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 *v148; // rax
  __int64 v149; // rax
  __int64 v150; // rax
  __int64 *v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 *v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 *v157; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 *v160; // rax
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 *v163; // rax
  __int64 v164; // rax
  __int64 v165; // rax
  __int64 *v166; // rax
  __int64 v167; // rax
  __int64 v168; // rax
  __int64 *v169; // rax
  __int64 v170; // rax
  __int64 v171; // rax
  __int64 v172; // rcx
  __int64 v173; // rdi
  __int64 v174; // r15
  __int64 v175; // r14
  __int64 v176; // r15
  unsigned __int64 v177; // rbx
  __int64 *v178; // rax
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // r8
  double v182; // xmm1_8
  __int64 v183; // rcx
  double v184; // xmm1_8
  double v185; // xmm0_8
  __int64 v186; // rax
  __int64 v187; // rax
  int v188; // r8d
  __int64 *v189; // rax
  __int64 v190; // rax
  __int64 v191; // rax
  __int64 v192; // r8
  double v193; // xmm1_8
  __int64 v194; // rcx
  double v195; // xmm1_8
  double v196; // xmm0_8
  __int64 v197; // rax
  __int64 v198; // rax
  int v199; // r8d
  __int64 *v200; // rax
  __int64 v201; // rax
  __int64 v202; // rax
  __int64 v203; // r8
  double v204; // xmm1_8
  __int64 v205; // rcx
  double v206; // xmm1_8
  double v207; // xmm0_8
  __int64 v208; // rax
  __int64 v209; // rax
  int v210; // r8d
  __int64 *v211; // rax
  __int64 v212; // rax
  __int64 v213; // rax
  __int64 v214; // r8
  double v215; // xmm1_8
  __int64 v216; // rcx
  double v217; // xmm1_8
  double v218; // xmm0_8
  __int64 v219; // rax
  __int64 v220; // rax
  __int64 v221; // r8
  __int64 *v222; // rax
  __int64 v223; // rax
  __int64 v224; // rax
  __int64 *v225; // rax
  __int64 *v226; // rax
  const wchar_t *v227; // rdx
  __int64 *v228; // rax
  const unsigned __int16 *v229; // rbx
  __int64 *v230; // rax
  _DWORD *v231; // rdi
  __int64 v232; // rax
  unsigned int v233; // ebx
  __int64 v234; // rdi
  unsigned __int16 v235; // r9
  const unsigned __int16 *v236; // rax
  __int64 v237; // rax
  DWORD v238; // ebx
  ULONG CompressedBufferSize[2]; // [rsp+28h] [rbp-E0h]
  int v241; // [rsp+48h] [rbp-C0h] BYREF
  char v242; // [rsp+4Ch] [rbp-BCh]
  char v243; // [rsp+4Dh] [rbp-BBh]
  unsigned int v244; // [rsp+50h] [rbp-B8h]
  int v245; // [rsp+54h] [rbp-B4h]
  ULONG FinalUncompressedSize; // [rsp+58h] [rbp-B0h] BYREF
  NTSTATUS Status; // [rsp+5Ch] [rbp-ACh]
  unsigned __int16 v248[4]; // [rsp+60h] [rbp-A8h]
  int **v249; // [rsp+68h] [rbp-A0h]
  unsigned int v250; // [rsp+70h] [rbp-98h]
  int v251; // [rsp+74h] [rbp-94h]
  int v252; // [rsp+78h] [rbp-90h]
  unsigned int v253; // [rsp+7Ch] [rbp-8Ch]
  unsigned int v254; // [rsp+80h] [rbp-88h]
  unsigned __int64 v255; // [rsp+88h] [rbp-80h]
  unsigned __int64 v256; // [rsp+90h] [rbp-78h]
  __int64 v257; // [rsp+98h] [rbp-70h]
  __int64 v258; // [rsp+A0h] [rbp-68h]
  __int64 v259; // [rsp+A8h] [rbp-60h]
  __int64 v260; // [rsp+B0h] [rbp-58h]
  __int64 PerformanceCounter64; // [rsp+B8h] [rbp-50h]
  WCHAR Buffer[256]; // [rsp+C8h] [rbp-40h] BYREF
  ULONG v263; // [rsp+2C8h] [rbp+1C0h]
  char v264; // [rsp+2CCh] [rbp+1C4h]
  __int64 v265; // [rsp+2D0h] [rbp+1C8h]

  v1 = (_DWORD *)*((_QWORD *)this + 106);
  v257 = 0;
  v3 = v1[2091];
  v4 = v1[2092];
  v250 = v1[2093];
  FinalUncompressedSize = 0;
  LODWORD(v256) = v3;
  v244 = v4;
  TickCount = GetTickCount();
  v6 = *((_QWORD *)this + 106);
  v7 = 0;
  v8 = 0;
  v242 = 0;
  v9 = *(_BYTE *)(v6 + 8360);
  v10 = *(double *)(v6 + 8344) * 1000.0;
  v243 = v9;
  v11 = (int)v10;
  v12 = *(double *)(v6 + 8352) * 1000.0;
  v259 = TickCount + v11;
  v13 = TickCount + (int)v12;
  LOBYTE(TickCount) = *(_BYTE *)(v6 + 8378);
  v260 = v13;
  v251 = 0;
  v253 = -1;
  v254 = 0;
  v252 = 0;
  LOBYTE(v245) = TickCount;
  PerformanceCounter64 = mlib::QueryPerformanceCounter64((mlib *)v6);
  v14 = (int **)((char *)this + 32);
  v15 = (WinSAT::CompressionWorkload *)((char *)this + 648);
  *((_QWORD *)this + 99) = __rdtsc();
  v16 = (int **)((char *)this + 32);
  while ( 1 )
  {
    if ( WinSAT::MPWorkload::ExitLoop(this) )
    {
      v249 = v14;
      v16 = v14;
      v17 = v14;
      v18 = v15;
      if ( !v9 )
        break;
      v14 = (int **)((char *)this + 32);
    }
    v15 = (WinSAT::CompressionWorkload *)((char *)this + 648);
    v19 = (__int64)(*((_QWORD *)this + 83) - *((_QWORD *)this + 81)) >> 3;
    if ( v19 >= *((_QWORD *)this + 95) )
    {
      v20 = v16;
    }
    else
    {
      if ( (__int64)(*((_QWORD *)this + 82) - *(_QWORD *)v15) >> 3 >= v19 )
        SampleManager::GrowSizeBy((WinSAT::CompressionWorkload *)((char *)this + 648), (unsigned int)v256);
      v20 = v14;
    }
    v249 = v20;
    v18 = (WinSAT::CompressionWorkload *)((char *)this + 648);
    if ( !WinSAT::MPWorkload::Rendevous(this) )
      break;
    v21 = GetTickCount();
    v22 = (volatile signed __int32 **)((char *)this + 64);
    v241 = v21;
    v23 = 0;
    v16 = (int **)((char *)this + 32);
    v24 = (volatile signed __int32 **)((char *)this + 64);
    while ( 1 )
    {
      v25 = v24;
      *(_DWORD *)v248 = v23;
      v26 = v244;
      if ( v23 >= v244 )
        break;
      FinalUncompressedSize = 0;
      v25 = v22;
      v16 = (int **)((char *)this + 32);
      if ( **((_DWORD **)this + 4) )
        break;
      v24 = (volatile signed __int32 **)((char *)this + 64);
      if ( **((_DWORD **)this + 8) )
        goto LABEL_40;
      Status = 0;
      LODWORD(v249) = 0;
      *((_QWORD *)this + 123) = RotatingBuffer::RotateBuffer((WinSAT::CompressionWorkload *)((char *)this + 880));
      v27 = RotatingBuffer::RotateBuffer((WinSAT::CompressionWorkload *)((char *)this + 928));
      v28 = *((unsigned int *)this + 244);
      v29 = v27;
      *((_QWORD *)this + 124) = v27;
      v258 = v28 + v7;
      v30 = *((_DWORD *)this + 214);
      v255 = __rdtsc();
      v31 = v255;
      if ( v30 )
      {
        if ( v30 != 1 )
        {
          v34 = Status;
          v32 = 87;
          goto LABEL_29;
        }
        v32 = (unsigned int)XpressEncode(
                              *((_QWORD *)this + 108),
                              (_DWORD)v29,
                              *((_DWORD *)this + 253),
                              *((_QWORD *)this + 123),
                              v28) == 0
            ? 0x3EB
            : 0;
      }
      else
      {
        v32 = RtlCompressBuffer(
                2u,
                *((PUCHAR *)this + 123),
                v28,
                v29,
                *((_DWORD *)this + 253),
                0x400u,
                &FinalUncompressedSize,
                *((PVOID *)this + 125));
      }
      if ( v32 )
      {
        v34 = Status;
        goto LABEL_28;
      }
      v33 = *((_DWORD *)this + 214);
      LODWORD(v249) = FinalUncompressedSize;
      if ( !v33 )
      {
        v34 = RtlDecompressBuffer(
                2u,
                *((PUCHAR *)this + 123),
                *((_DWORD *)this + 244),
                *((PUCHAR *)this + 124),
                FinalUncompressedSize,
                &FinalUncompressedSize);
LABEL_28:
        v31 = v255;
        goto LABEL_29;
      }
      if ( v33 != 1 )
      {
        v34 = 87;
        goto LABEL_28;
      }
      v35 = XpressDecode(
              *((_QWORD *)this + 109),
              *((_QWORD *)this + 124),
              *((_DWORD *)this + 253),
              *((_DWORD *)this + 253),
              *((_QWORD *)this + 123),
              *((_DWORD *)this + 244));
      v34 = Status;
      v31 = v255;
      if ( !v35 )
        v32 = 1003;
LABEL_29:
      v36 = __rdtsc();
      v7 = v258 + (unsigned int)v249;
      if ( v32 == 279 )
      {
        ++v251;
      }
      else
      {
        if ( v32 )
        {
          _InterlockedIncrement(*v24);
          v50 = RtlNtStatusToDosError(v32);
          v264 = 1;
          v263 = v50;
          v265 = 0;
          mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
          EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
          v51 = *((_QWORD *)this + 2);
          CompressedBufferSize[0] = *((_DWORD *)this + 22);
          v52 = mlib::MUISpf_(
                  (mlib *)"base\\winsat\\cpu\\compression.cpp",
                  (const char *)0x217,
                  507,
                  v248[0],
                  *(_QWORD *)CompressedBufferSize);
          v53 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v51 + 240), (__int64)v52);
          v54 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v53, 10);
          v55 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, (__int64)Buffer);
          std::endl(v55);
          if ( v32 == -1073741789 )
            std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              *((_QWORD *)this + 2) + 240LL,
              "BUFFER TOO SMALL!\n");
LABEL_39:
          LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
          v16 = (int **)((char *)this + 32);
LABEL_40:
          v25 = (volatile signed __int32 **)((char *)this + 64);
LABEL_41:
          v26 = v244;
          break;
        }
        if ( v34 )
        {
          _InterlockedIncrement(*v24);
          v38 = RtlNtStatusToDosError(v34);
          v264 = 1;
          v263 = v38;
          v265 = 0;
          mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
          EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
          v39 = *((_QWORD *)this + 2);
          CompressedBufferSize[0] = *((_DWORD *)this + 22);
          v40 = mlib::MUISpf_(
                  (mlib *)"base\\winsat\\cpu\\compression.cpp",
                  (const char *)0x22A,
                  508,
                  v248[0],
                  *(_QWORD *)CompressedBufferSize);
          v41 = std::operator<<<unsigned short,std::char_traits<unsigned short>>((__int64 *)(v39 + 240), (__int64)v40);
          v42 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v41, 10);
          v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, (__int64)Buffer);
          std::endl(v43);
          goto LABEL_39;
        }
      }
      if ( !v242 )
      {
        v37 = v36 - v31;
        SampleManager::AddSample((WinSAT::CompressionWorkload *)((char *)this + 648), v36 - v31);
        v257 += v37;
      }
      v25 = (volatile signed __int32 **)((char *)this + 64);
      v16 = (int **)((char *)this + 32);
      if ( **((_DWORD **)this + 4) || **v24 )
        goto LABEL_41;
      v22 = (volatile signed __int32 **)((char *)this + 64);
      v23 = *(_DWORD *)v248 + 1;
    }
    v44 = *v16;
    v17 = v16;
    v249 = v16;
    v18 = (WinSAT::CompressionWorkload *)((char *)this + 648);
    if ( *v44 )
      break;
    v45 = *v25;
    v249 = v16;
    if ( *v45 )
      break;
    if ( !(_BYTE)v245 )
      Sleep(*(_DWORD *)(*((_QWORD *)this + 106) + 8332LL));
    ++v252;
    v46 = GetTickCount() - v241;
    v47 = v254;
    if ( v46 > v254 )
      v47 = v46;
    v254 = v47;
    v48 = v253;
    if ( v46 < v253 )
      v48 = v46;
    v253 = v48;
    if ( v46 < 0xA )
    {
      v49 = 2 * v26;
      goto LABEL_56;
    }
    if ( v46 < 0x4B )
    {
      v49 = (v26 >> 1) + v26;
LABEL_56:
      v244 = v49;
    }
    v9 = v243;
    if ( !v242 && !v243 )
    {
      SampleManager::Process((WinSAT::CompressionWorkload *)((char *)this + 648), v250);
      if ( GetTickCount() >= (unsigned int)v259 && *((_BYTE *)this + 752) )
      {
        v8 = __rdtsc();
        _InterlockedIncrement(*((volatile signed __int32 **)this + 7));
        goto LABEL_64;
      }
      if ( GetTickCount() >= (unsigned int)v260 )
      {
        _InterlockedIncrement(*((volatile signed __int32 **)this + 7));
LABEL_64:
        v242 = 1;
      }
    }
    v14 = (int **)((char *)this + 32);
  }
  if ( !**v17 )
  {
    v56 = (mlib *)**((unsigned int **)this + 8);
    if ( !(_DWORD)v56 )
    {
      v57 = v250;
      if ( !*((_BYTE *)v18 + 105) )
        SampleManager::Process(v18, v250);
      v58 = mlib::QueryPerformanceCounter64(v56);
      *((_QWORD *)this + 100) = __rdtsc();
      PerformanceFrequency64 = mlib::QueryPerformanceFrequency64(v59);
      if ( PerformanceFrequency64 < 0 )
        v61 = (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1))
            + (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1));
      else
        v61 = (double)(int)PerformanceFrequency64;
      v62 = PerformanceCounter64;
      if ( PerformanceCounter64 < 0 )
        v63 = (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1))
            + (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1));
      else
        v63 = (double)(int)PerformanceCounter64;
      *((double *)this + 136) = v63 / v61;
      if ( v58 < 0 )
        v64 = (double)(int)(v58 & 1 | ((unsigned __int64)v58 >> 1))
            + (double)(int)(v58 & 1 | ((unsigned __int64)v58 >> 1));
      else
        v64 = (double)(int)v58;
      v65 = v58 - v62;
      *((double *)this + 137) = v64 / v61;
      if ( v65 < 0 )
        v66 = (double)(int)(v65 & 1 | ((unsigned __int64)v65 >> 1))
            + (double)(int)(v65 & 1 | ((unsigned __int64)v65 >> 1));
      else
        v66 = (double)(int)v65;
      v67 = *((_QWORD *)this + 105);
      v68 = v66 / v61;
      *((double *)this + 138) = v68;
      if ( v67 < 0 )
        v69 = (double)(int)(v67 & 1 | ((unsigned __int64)v67 >> 1))
            + (double)(int)(v67 & 1 | ((unsigned __int64)v67 >> 1));
      else
        v69 = (double)(int)v67;
      v70 = *((_QWORD *)this + 99);
      v71 = *((_QWORD *)this + 100) - v70;
      if ( v71 < 0 )
        v72 = (double)(int)(v71 & 1 | ((unsigned __int64)v71 >> 1))
            + (double)(int)(v71 & 1 | ((unsigned __int64)v71 >> 1));
      else
        v72 = (double)(int)v71;
      v73 = v72 / v69;
      *((double *)this + 139) = v73;
      if ( v8 )
      {
        v74 = v8 - v70;
        if ( v74 < 0 )
          v75 = (double)(int)(v74 & 1 | ((unsigned __int64)v74 >> 1))
              + (double)(int)(v74 & 1 | ((unsigned __int64)v74 >> 1));
        else
          v75 = (double)(int)v74;
        *((double *)this + 140) = v75 / v69;
      }
      v76 = v257;
      *(_QWORD *)&v77 = COERCE_UNSIGNED_INT64(v73 - v68) & _xmm;
      v78 = v68 / 1000.0 * 5.0;
      *((_BYTE *)this + 808) = v77 > v78;
      if ( v76 < 0 )
        v79 = (double)(int)(v76 & 1 | ((unsigned __int64)v76 >> 1))
            + (double)(int)(v76 & 1 | ((unsigned __int64)v76 >> 1));
      else
        v79 = (double)(int)v76;
      v80 = v79 / v69;
      *((double *)this + 130) = v80;
      v81 = (__int64)(*((_QWORD *)v18 + 1) - *(_QWORD *)v18) >> 3;
      if ( v81 < 0 )
      {
        v83 = ((__int64)(*((_QWORD *)v18 + 1) - *(_QWORD *)v18) >> 3) & 1
            | ((unsigned __int64)((__int64)(*((_QWORD *)v18 + 1) - *(_QWORD *)v18) >> 3) >> 1);
        v82 = (double)(int)v83 + (double)(int)v83;
      }
      else
      {
        v82 = (double)(int)v81;
      }
      *((double *)this + 131) = v82;
      if ( v7 < 0 )
        v84 = (double)(int)(v7 & 1 | ((unsigned __int64)v7 >> 1)) + (double)(int)(v7 & 1 | ((unsigned __int64)v7 >> 1));
      else
        v84 = (double)(int)v7;
      v85 = *((_QWORD *)this + 87);
      *((double *)this + 132) = v84;
      if ( v85 < 0 )
        v86 = (double)(int)(v85 & 1 | ((unsigned __int64)v85 >> 1))
            + (double)(int)(v85 & 1 | ((unsigned __int64)v85 >> 1));
      else
        v86 = (double)(int)v85;
      v87 = *((_QWORD *)this + 91);
      v88 = v86 / v69;
      if ( v87 < 0 )
      {
        v90 = *((_QWORD *)this + 91) & 1LL | (*((_QWORD *)this + 91) >> 1);
        v89 = (double)(int)v90 + (double)(int)v90;
      }
      else
      {
        v89 = (double)(int)v87;
      }
      v91 = *((_QWORD *)this + 85);
      v92 = v89 / v69;
      v93 = (double)*((int *)this + 244);
      *((double *)this + 133) = v93 / v88;
      *((double *)this + 103) = v93 / v92;
      if ( v91 < 0 )
        v94 = (double)(int)(v91 & 1 | ((unsigned __int64)v91 >> 1))
            + (double)(int)(v91 & 1 | ((unsigned __int64)v91 >> 1));
      else
        v94 = (double)(int)v91;
      v95 = *((_QWORD *)this + 86);
      *((double *)this + 134) = v93 / (v94 / v69);
      if ( v95 < 0 )
        v96 = (double)(int)(v95 & 1 | ((unsigned __int64)v95 >> 1))
            + (double)(int)(v95 & 1 | ((unsigned __int64)v95 >> 1));
      else
        v96 = (double)(int)v95;
      *((double *)this + 135) = v84 / v80;
      *((double *)this + 104) = v93 / (v96 / v69);
      if ( *((_BYTE *)this + 24) )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v97 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"> CPU(");
        v98 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v97, *((_DWORD *)this + 22));
        v99 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v98, (__int64)L")\n");
        v100 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 v99,
                 (__int64)L"  --                     elapsed ticks : ");
        v241 = 12;
        v101 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v100, &v241);
        v102 = std::basic_ostream<unsigned short>::operator<<(v101, v76);
        *(_DWORD *)(*(int *)(*(_QWORD *)v102 + 4LL) + v102 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v102 + 4LL) + v102 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v102 + 4LL) + v102 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v102, "\n");
        v103 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --               cummulative seconds : ");
        *(_DWORD *)((char *)v103 + *(int *)(*v103 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v103 + *(int *)(*v103 + 4) + 32) = 9;
        *(__int64 *)((char *)v103 + *(int *)(*v103 + 4) + 40) = 0;
        v104 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v103, *((double *)this + 130));
        *(_DWORD *)((char *)v104 + *(int *)(*v104 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v104 + *(int *)(*v104 + 4) + 88) = 32;
        *(__int64 *)((char *)v104 + *(int *)(*v104 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v104, (__int64)L"\n");
        v105 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --               good data duration  : ");
        *(_DWORD *)((char *)v105 + *(int *)(*v105 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v105 + *(int *)(*v105 + 4) + 32) = 9;
        *(__int64 *)((char *)v105 + *(int *)(*v105 + 4) + 40) = 0;
        v106 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v105, *((double *)this + 140));
        *(_DWORD *)((char *)v106 + *(int *)(*v106 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v106 + *(int *)(*v106 + 4) + 88) = 32;
        *(__int64 *)((char *)v106 + *(int *)(*v106 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v106, (__int64)L"\n");
        v107 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --               Measured Value Secs : ");
        *(_DWORD *)((char *)v107 + *(int *)(*v107 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v107 + *(int *)(*v107 + 4) + 32) = 9;
        *(__int64 *)((char *)v107 + *(int *)(*v107 + 4) + 40) = 0;
        v108 = std::basic_ostream<unsigned short>::operator<<((__int64)v107, v92);
        *(_DWORD *)(*(int *)(*(_QWORD *)v108 + 4LL) + v108 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v108 + 4LL) + v108 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v108 + 4LL) + v108 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v108, "\n");
        v109 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                       min seconds : ");
        *(_DWORD *)((char *)v109 + *(int *)(*v109 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v109 + *(int *)(*v109 + 4) + 32) = 9;
        *(__int64 *)((char *)v109 + *(int *)(*v109 + 4) + 40) = 0;
        v110 = std::basic_ostream<unsigned short>::operator<<((__int64)v109, v88);
        *(_DWORD *)(*(int *)(*(_QWORD *)v110 + 4LL) + v110 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v110 + 4LL) + v110 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v110 + 4LL) + v110 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v110, "\n");
        v111 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                 buffer pass count : ");
        v241 = 12;
        v112 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v111, &v241);
        v113 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v112, *((double *)this + 131));
        *(_DWORD *)((char *)v113 + *(int *)(*v113 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v113 + *(int *)(*v113 + 4) + 88) = 32;
        *(__int64 *)((char *)v113 + *(int *)(*v113 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v113, (__int64)L"\n");
        v114 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --             total bytes processed : ");
        *(_DWORD *)((char *)v114 + *(int *)(*v114 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v114 + *(int *)(*v114 + 4) + 32) = 0;
        *(__int64 *)((char *)v114 + *(int *)(*v114 + 4) + 40) = 0;
        v115 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v114, *((double *)this + 132));
        *(_DWORD *)((char *)v115 + *(int *)(*v115 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v115 + *(int *)(*v115 + 4) + 88) = 32;
        *(__int64 *)((char *)v115 + *(int *)(*v115 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v115, (__int64)L"\n");
        v116 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                               B/s : ");
        *(_DWORD *)((char *)v116 + *(int *)(*v116 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v116 + *(int *)(*v116 + 4) + 32) = 0;
        *(__int64 *)((char *)v116 + *(int *)(*v116 + 4) + 40) = 0;
        v117 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v116, *((double *)this + 103));
        *(_DWORD *)((char *)v117 + *(int *)(*v117 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v117 + *(int *)(*v117 + 4) + 88) = 32;
        *(__int64 *)((char *)v117 + *(int *)(*v117 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v117, (__int64)L"\n");
        v118 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                      B/s (median) : ");
        *(_DWORD *)((char *)v118 + *(int *)(*v118 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v118 + *(int *)(*v118 + 4) + 32) = 0;
        *(__int64 *)((char *)v118 + *(int *)(*v118 + 4) + 40) = 0;
        v119 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v118, *((double *)this + 134));
        *(_DWORD *)((char *)v119 + *(int *)(*v119 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v119 + *(int *)(*v119 + 4) + 88) = 32;
        *(__int64 *)((char *)v119 + *(int *)(*v119 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v119, (__int64)L"\n");
        v120 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                         B/s(mean) : ");
        *(_DWORD *)((char *)v120 + *(int *)(*v120 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v120 + *(int *)(*v120 + 4) + 32) = 0;
        *(__int64 *)((char *)v120 + *(int *)(*v120 + 4) + 40) = 0;
        v121 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v120, *((double *)this + 104));
        *(_DWORD *)((char *)v121 + *(int *)(*v121 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v121 + *(int *)(*v121 + 4) + 88) = 32;
        *(__int64 *)((char *)v121 + *(int *)(*v121 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v121, (__int64)L"\n");
        v122 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                       B/s (mean2) : ");
        *(_DWORD *)((char *)v122 + *(int *)(*v122 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v122 + *(int *)(*v122 + 4) + 32) = 0;
        *(__int64 *)((char *)v122 + *(int *)(*v122 + 4) + 40) = 0;
        v123 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v122, *((double *)this + 104));
        *(_DWORD *)((char *)v123 + *(int *)(*v123 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v123 + *(int *)(*v123 + 4) + 88) = 32;
        *(__int64 *)((char *)v123 + *(int *)(*v123 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v123, (__int64)L"\n");
        v124 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                  QPC Elapsed Secs : ");
        *(_DWORD *)((char *)v124 + *(int *)(*v124 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v124 + *(int *)(*v124 + 4) + 32) = 9;
        *(__int64 *)((char *)v124 + *(int *)(*v124 + 4) + 40) = 0;
        v125 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v124, *((double *)this + 138));
        *(_DWORD *)((char *)v125 + *(int *)(*v125 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v125 + *(int *)(*v125 + 4) + 88) = 32;
        *(__int64 *)((char *)v125 + *(int *)(*v125 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v125, (__int64)L"\n");
        v126 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                RDTSC Elapsed Secs : ");
        *(_DWORD *)((char *)v126 + *(int *)(*v126 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v126 + *(int *)(*v126 + 4) + 32) = 9;
        *(__int64 *)((char *)v126 + *(int *)(*v126 + 4) + 40) = 0;
        v127 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v126, *((double *)this + 139));
        *(_DWORD *)((char *)v127 + *(int *)(*v127 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v127 + *(int *)(*v127 + 4) + 88) = 32;
        *(__int64 *)((char *)v127 + *(int *)(*v127 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v127, (__int64)L"\n");
        v128 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                         diff secs : ");
        *(_DWORD *)((char *)v128 + *(int *)(*v128 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v128 + *(int *)(*v128 + 4) + 32) = 9;
        *(__int64 *)((char *)v128 + *(int *)(*v128 + 4) + 40) = 0;
        v129 = std::basic_ostream<unsigned short>::operator<<((__int64)v128, v77);
        *(_DWORD *)(*(int *)(*(_QWORD *)v129 + 4LL) + v129 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v129 + 4LL) + v129 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v129 + 4LL) + v129 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v129, "\n");
        v130 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                  max allowed diff : ");
        *(_DWORD *)((char *)v130 + *(int *)(*v130 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v130 + *(int *)(*v130 + 4) + 32) = 9;
        *(__int64 *)((char *)v130 + *(int *)(*v130 + 4) + 40) = 0;
        v131 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v130, v78);
        *(_DWORD *)((char *)v131 + *(int *)(*v131 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v131 + *(int *)(*v131 + 4) + 88) = 32;
        *(__int64 *)((char *)v131 + *(int *)(*v131 + 4) + 40) = 0;
        v132 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v131, (__int64)L"  - ");
        v133 = L"Delta VIOLATION!";
        if ( !*((_BYTE *)this + 808) )
          v133 = L"delta OK";
        v134 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v132, (__int64)v133);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v134, (__int64)L"\n");
        v135 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --               Zero filled buffers : ");
        v136 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v135, v251);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v136, (__int64)L"\n");
        v137 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --             measurment loop count : ");
        v138 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v137, v252);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v138, (__int64)L"\n");
        v139 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                 sample block size : ");
        v140 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v139, v244);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v140, (__int64)L"\n");
        v141 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                 min loop duration : ");
        v142 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v141, v253);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, (__int64)L"\n");
        v143 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                 max loop duration : ");
        v144 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v143, v254);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v144, (__int64)L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          (__int64 *)(*((_QWORD *)this + 1) + 240LL),
          (__int64)L"  -- Statistics --\n");
        v145 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       + Total Samples : ");
        v241 = 12;
        v146 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, &v241);
        v147 = std::basic_ostream<unsigned short>::operator<<(
                 v146,
                 (__int64)(*((_QWORD *)v18 + 1) - *(_QWORD *)v18) >> 3);
        *(_DWORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v147, "\n");
        v148 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +           min : ");
        v241 = 12;
        v149 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v148, &v241);
        v150 = std::basic_ostream<unsigned short>::operator<<(v149, *((_QWORD *)this + 87));
        *(_DWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v150, "\n");
        v151 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +lower quartile : ");
        v241 = 12;
        v152 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v151, &v241);
        v153 = std::basic_ostream<unsigned short>::operator<<(v152, *((_QWORD *)this + 91));
        *(_DWORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v153, "\n");
        v154 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +        median : ");
        v241 = 12;
        v155 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v154, &v241);
        v156 = std::basic_ostream<unsigned short>::operator<<(v155, *((_QWORD *)this + 85));
        *(_DWORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v156, "\n");
        v157 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +          mean : ");
        v241 = 12;
        v158 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v157, &v241);
        v159 = std::basic_ostream<unsigned short>::operator<<(v158, *((_QWORD *)this + 86));
        *(_DWORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v159, "\n");
        v160 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +upper quartile : ");
        v241 = 12;
        v161 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v160, &v241);
        v162 = std::basic_ostream<unsigned short>::operator<<(v161, *((_QWORD *)this + 90));
        *(_DWORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v162, "\n");
        v163 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +           max : ");
        v241 = 12;
        v164 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v163, &v241);
        v165 = std::basic_ostream<unsigned short>::operator<<(v164, *((_QWORD *)this + 88));
        *(_DWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v165, "\n");
        v166 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +         range : ");
        v241 = 12;
        v167 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v166, &v241);
        v168 = std::basic_ostream<unsigned short>::operator<<(v167, *((_QWORD *)this + 89));
        *(_DWORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v168, "\n");
        v169 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +      IQ range : ");
        v241 = 12;
        v170 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v169, &v241);
        v171 = std::basic_ostream<unsigned short>::operator<<(v170, *((_QWORD *)this + 92));
        *(_DWORD *)(*(int *)(*(_QWORD *)v171 + 4LL) + v171 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v171 + 4LL) + v171 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v171 + 4LL) + v171 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v171, "\n");
        v172 = *((_QWORD *)this + 87);
        v173 = *((_QWORD *)this + 91) - v172;
        v174 = *((_QWORD *)this + 85);
        v175 = v174 - *((_QWORD *)this + 91);
        v176 = v174 - v172;
        v177 = v172 * (unsigned __int64)v57 / 0x186A0;
        v178 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +    median-Min : ");
        v241 = 12;
        v179 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v178, &v241);
        v180 = std::basic_ostream<unsigned short>::operator<<(v179, v176);
        *(_DWORD *)(*(int *)(*(_QWORD *)v180 + 4LL) + v180 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v180 + 4LL) + v180 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v180 + 4LL) + v180 + 40) = 0;
        v181 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v180, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 40) = 3;
        if ( v176 < 0 )
          v182 = (double)(int)(v176 & 1 | ((unsigned __int64)v176 >> 1))
               + (double)(int)(v176 & 1 | ((unsigned __int64)v176 >> 1));
        else
          v182 = (double)(int)v176;
        v183 = *((_QWORD *)this + 87);
        v184 = v182 * 100.0;
        if ( v183 < 0 )
        {
          v186 = *((_QWORD *)this + 87) & 1LL | (*((_QWORD *)this + 87) >> 1);
          v185 = (double)(int)v186 + (double)(int)v186;
        }
        else
        {
          v185 = (double)(int)v183;
        }
        v187 = std::basic_ostream<unsigned short>::operator<<(v181, v184 / v185);
        *(_DWORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v187, "% of min \n", v188);
        v189 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +        lq-Min : ");
        v241 = 12;
        v190 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v189, &v241);
        v191 = std::basic_ostream<unsigned short>::operator<<(v190, v173);
        *(_DWORD *)(*(int *)(*(_QWORD *)v191 + 4LL) + v191 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v191 + 4LL) + v191 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v191 + 4LL) + v191 + 40) = 0;
        v192 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v191, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v192 + 4LL) + v192 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v192 + 4LL) + v192 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v192 + 4LL) + v192 + 40) = 3;
        if ( v173 < 0 )
          v193 = (double)(int)(v173 & 1 | ((unsigned __int64)v173 >> 1))
               + (double)(int)(v173 & 1 | ((unsigned __int64)v173 >> 1));
        else
          v193 = (double)(int)v173;
        v194 = *((_QWORD *)this + 87);
        v195 = v193 * 100.0;
        if ( v194 < 0 )
        {
          v197 = *((_QWORD *)this + 87) & 1LL | (*((_QWORD *)this + 87) >> 1);
          v196 = (double)(int)v197 + (double)(int)v197;
        }
        else
        {
          v196 = (double)(int)v194;
        }
        v198 = std::basic_ostream<unsigned short>::operator<<(v192, v195 / v196);
        *(_DWORD *)(*(int *)(*(_QWORD *)v198 + 4LL) + v198 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v198 + 4LL) + v198 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v198 + 4LL) + v198 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v198, "% of min \n", v199);
        v200 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +     median-lq : ");
        v241 = 12;
        v201 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v200, &v241);
        v202 = std::basic_ostream<unsigned short>::operator<<(v201, v175);
        *(_DWORD *)(*(int *)(*(_QWORD *)v202 + 4LL) + v202 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v202 + 4LL) + v202 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v202 + 4LL) + v202 + 40) = 0;
        v203 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v202, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v203 + 4LL) + v203 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v203 + 4LL) + v203 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v203 + 4LL) + v203 + 40) = 3;
        if ( v175 < 0 )
          v204 = (double)(int)(v175 & 1 | ((unsigned __int64)v175 >> 1))
               + (double)(int)(v175 & 1 | ((unsigned __int64)v175 >> 1));
        else
          v204 = (double)(int)v175;
        v205 = *((_QWORD *)this + 91);
        v206 = v204 * 100.0;
        if ( v205 < 0 )
        {
          v208 = *((_QWORD *)this + 91) & 1LL | (*((_QWORD *)this + 91) >> 1);
          v207 = (double)(int)v208 + (double)(int)v208;
        }
        else
        {
          v207 = (double)(int)v205;
        }
        v209 = std::basic_ostream<unsigned short>::operator<<(v203, v206 / v207);
        *(_DWORD *)(*(int *)(*(_QWORD *)v209 + 4LL) + v209 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v209 + 4LL) + v209 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v209 + 4LL) + v209 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v209, "% of lq \n", v210);
        v211 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +         Limit : ");
        v241 = 12;
        v212 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v211, &v241);
        v213 = std::basic_ostream<unsigned short>::operator<<(v212, v177);
        v214 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v213, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v214 + 4LL) + v214 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v214 + 4LL) + v214 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v214 + 4LL) + v214 + 40) = 3;
        if ( (v177 & 0x8000000000000000uLL) != 0LL )
          v215 = (double)(int)(v177 & 1 | (v177 >> 1)) + (double)(int)(v177 & 1 | (v177 >> 1));
        else
          v215 = (double)(int)v177;
        v216 = *((_QWORD *)this + 87);
        v217 = v215 * 100.0;
        if ( v216 < 0 )
        {
          v219 = *((_QWORD *)this + 87) & 1LL | (*((_QWORD *)this + 87) >> 1);
          v218 = (double)(int)v219 + (double)(int)v219;
        }
        else
        {
          v218 = (double)(int)v216;
        }
        v220 = std::basic_ostream<unsigned short>::operator<<(v214, v217 / v218);
        *(_DWORD *)(*(int *)(*(_QWORD *)v220 + 4LL) + v220 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v220 + 4LL) + v220 + 88) = 32;
        v221 = *(int *)(*(_QWORD *)v220 + 4LL);
        *(_QWORD *)(v221 + v220 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v220, "% of min \n", v221);
        v222 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +           Sum : ");
        v241 = 12;
        v223 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v222, &v241);
        v224 = std::basic_ostream<unsigned short>::operator<<(v223, *((_QWORD *)this + 84));
        *(_DWORD *)(*(int *)(*(_QWORD *)v224 + 4LL) + v224 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v224 + 4LL) + v224 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v224 + 4LL) + v224 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v224, "\n");
        v225 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +        Status : ");
        v241 = 12;
        v226 = (__int64 *)mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v225, &v241);
        v227 = L"GOOD";
        if ( !*((_BYTE *)this + 752) )
          v227 = L"BAD";
        v228 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v226, (__int64)v227);
        *(_DWORD *)((char *)v228 + *(int *)(*v228 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v228 + *(int *)(*v228 + 4) + 88) = 32;
        *(__int64 *)((char *)v228 + *(int *)(*v228 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v228, "\n");
        std::endl(*((_QWORD *)this + 1) + 240LL);
        LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      }
    }
  }
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  if ( **v249 <= 0 )
  {
    if ( *((_BYTE *)this + 808) )
    {
      v232 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
      v233 = *((_DWORD *)this + 22);
      v234 = v232;
      v236 = mlib::MUIStr_((mlib *)"base\\winsat\\cpu\\compression.cpp", (const char *)0x32F, 549, v235);
      mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfb(v234, v236, v233);
      v237 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
      std::endl(v237 + 240);
    }
    v231 = (_DWORD *)((char *)this + 96);
    *((_DWORD *)this + 24) = 6;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)this + 104);
    *((_BYTE *)this + 112) = 0;
  }
  else
  {
    v229 = mlib::MUISpf_((mlib *)"base\\winsat\\cpu\\compression.cpp", (const char *)0x324, 509, *((_DWORD *)this + 22));
    v230 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 2) + 240LL),
             (__int64)v229);
    std::endl(v230);
    v231 = (_DWORD *)((char *)this + 96);
    WinSAT::OpStatus::SetResult((char *)this + 96, 5, v229, 0);
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  v238 = *v231 != 6 ? 0xD : 0;
  SetLastError(v238);
  return v238;
}

```

## disassembly

```asm
0x140076d90  mov     rax, rsp
0x140076d93  push    rbp
0x140076d94  push    rbx
0x140076d95  push    rsi
0x140076d96  push    rdi
0x140076d97  push    r12
0x140076d99  push    r13
0x140076d9b  push    r14
0x140076d9d  push    r15
0x140076d9f  lea     rbp, [rax-268h]
0x140076da6  sub     rsp, 328h
0x140076dad  movaps  xmmword ptr [rax-58h], xmm6
0x140076db1  movaps  xmmword ptr [rax-68h], xmm7
0x140076db5  movaps  xmmword ptr [rax-78h], xmm8
0x140076dba  movaps  xmmword ptr [rax-88h], xmm9
0x140076dc2  mov     rax, cs:__security_cookie
0x140076dc9  xor     rax, rsp
0x140076dcc  mov     [rbp+260h+var_90], rax
0x140076dd3  mov     rax, [rcx+350h]
0x140076dda  mov     rsi, rcx
0x140076ddd  mov     [rbp+260h+var_2D0], 0
0x140076de5  mov     ecx, [rax+20ACh]
0x140076deb  mov     edx, [rax+20B0h]
0x140076df1  mov     eax, [rax+20B4h]
0x140076df7  mov     [rsp+360h+var_2F8], eax
0x140076dfb  mov     [rsp+360h+FinalUncompressedSize], 0
0x140076e03  mov     dword ptr [rbp+260h+var_2D8], ecx
0x140076e06  mov     [rsp+360h+var_318], edx
0x140076e0a  call    cs:__imp_GetTickCount
0x140076e10  mov     rcx, [rsi+350h]; this
0x140076e17  xor     r13d, r13d
0x140076e1a  movsd   xmm8, cs:__real@408f400000000000
0x140076e23  xor     r15d, r15d
0x140076e26  mov     [rsp+360h+var_31C], r13b
0x140076e2b  movsd   xmm0, qword ptr [rcx+2098h]
0x140076e33  mov     r14b, [rcx+20A8h]
0x140076e3a  mulsd   xmm0, xmm8
0x140076e3f  mov     [rsp+360h+var_31B], r14b
0x140076e44  cvttsd2si rdx, xmm0
0x140076e49  movsd   xmm0, qword ptr [rcx+20A0h]
0x140076e51  add     edx, eax
0x140076e53  mulsd   xmm0, xmm8
0x140076e58  mov     [rbp+260h+var_2C0], rdx
0x140076e5c  cvttsd2si rdx, xmm0
0x140076e61  add     edx, eax
0x140076e63  mov     al, [rcx+20BAh]
0x140076e69  mov     [rbp+260h+var_2B8], rdx
0x140076e6d  xor     edx, edx
0x140076e6f  mov     [rsp+360h+var_2F4], edx
0x140076e73  or      edx, 0FFFFFFFFh
0x140076e76  mov     [rsp+360h+var_2EC], edx
0x140076e7a  xor     edx, edx
0x140076e7c  mov     [rsp+360h+var_2E8], edx
0x140076e80  mov     [rsp+360h+var_2F0], edx
0x140076e84  mov     byte ptr [rsp+360h+var_314], al
0x140076e88  call    ?QueryPerformanceCounter64@mlib@@YA_KXZ; mlib::QueryPerformanceCounter64(void)
0x140076e8d  mov     [rbp+260h+var_2B0], rax
0x140076e91  rdtsc
0x140076e93  shl     rdx, 20h
0x140076e97  lea     rdi, [rsi+20h]
0x140076e9b  or      rax, rdx
0x140076e9e  lea     r12, [rsi+288h]
0x140076ea5  mov     [rsi+318h], rax
0x140076eac  mov     rbx, rdi
0x140076eaf  mov     rcx, rsi; this
0x140076eb2  call    ?ExitLoop@MPWorkload@WinSAT@@IEBA_NXZ; WinSAT::MPWorkload::ExitLoop(void)
0x140076eb7  test    al, al
0x140076eb9  jz      short loc_140076ED6
0x140076ebb  mov     [rsp+360h+var_300], rdi
0x140076ec0  mov     rbx, rdi
0x140076ec3  mov     r10, rdi
0x140076ec6  mov     rdi, r12
0x140076ec9  test    r14b, r14b
0x140076ecc  jz      loc_1400773D6
0x140076ed2  lea     rdi, [rsi+20h]
0x140076ed6  lea     r12, [rsi+288h]
0x140076edd  mov     rcx, [r12+10h]
0x140076ee2  sub     rcx, [r12]
0x140076ee6  sar     rcx, 3
0x140076eea  cmp     rcx, [r12+70h]
0x140076eef  jnb     short loc_140076F15
0x140076ef1  mov     rax, [rsi+290h]
0x140076ef8  sub     rax, [r12]
0x140076efc  sar     rax, 3
0x140076f00  cmp     rax, rcx
0x140076f03  jb      short loc_140076F10
0x140076f05  mov     edx, dword ptr [rbp+260h+var_2D8]; unsigned __int64
0x140076f08  mov     rcx, r12; this
0x140076f0b  call    ?GrowSizeBy@SampleManager@@QEAAX_K@Z; SampleManager::GrowSizeBy(unsigned __int64)
0x140076f10  mov     r10, rdi
0x140076f13  jmp     short loc_140076F18
0x140076f15  mov     r10, rbx
0x140076f18  mov     rcx, rsi; this
0x140076f1b  mov     [rsp+360h+var_300], r10
0x140076f20  mov     rdi, r12
0x140076f23  call    ?Rendevous@MPWorkload@WinSAT@@IEBA_NXZ; WinSAT::MPWorkload::Rendevous(void)
0x140076f28  test    al, al
0x140076f2a  jz      loc_1400773D6
0x140076f30  call    cs:__imp_GetTickCount
0x140076f36  lea     rcx, [rsi+40h]
0x140076f3a  mov     [rsp+360h+var_320], eax
0x140076f3e  xor     eax, eax
0x140076f40  lea     rbx, [rsi+20h]
0x140076f44  mov     r14, rcx
0x140076f47  mov     r8, r14
0x140076f4a  mov     dword ptr [rsp+360h+var_308], eax
0x140076f4e  mov     r14d, [rsp+360h+var_318]
0x140076f53  cmp     eax, r14d
0x140076f56  jnb     loc_14007722B
0x140076f5c  lea     rdx, [rsi+20h]
0x140076f60  mov     [rsp+360h+FinalUncompressedSize], 0
0x140076f68  mov     rax, [rdx]
0x140076f6b  mov     r8, rcx
0x140076f6e  mov     rbx, rdx
0x140076f71  mov     ecx, [rax]
0x140076f73  test    ecx, ecx
0x140076f75  jnz     loc_14007722B
0x140076f7b  lea     r14, [rsi+40h]
0x140076f7f  mov     rax, [r14]
0x140076f82  mov     ecx, [rax]
0x140076f84  test    ecx, ecx
0x140076f86  jnz     loc_140077223
0x140076f8c  mov     [rsp+360h+Status], ecx
0x140076f90  mov     dword ptr [rsp+360h+var_300], ecx
0x140076f94  lea     rcx, [rsi+370h]; this
0x140076f9b  call    ?RotateBuffer@RotatingBuffer@@QEAAPEAEXZ; RotatingBuffer::RotateBuffer(void)
0x140076fa0  lea     rcx, [rsi+3A0h]; this
0x140076fa7  mov     [rsi+3D8h], rax
0x140076fae  call    ?RotateBuffer@RotatingBuffer@@QEAAPEAEXZ; RotatingBuffer::RotateBuffer(void)
0x140076fb3  mov     r8d, [rsi+3D0h]; UncompressedBufferSize
0x140076fba  mov     r10, rax
0x140076fbd  mov     [rsi+3E0h], rax
0x140076fc4  lea     rax, [r8+r13]
0x140076fc8  mov     [rbp+260h+var_2C8], rax
0x140076fcc  rdtsc
0x140076fce  mov     ecx, [rsi+358h]
0x140076fd4  shl     rdx, 20h
0x140076fd8  or      rax, rdx
0x140076fdb  mov     [rbp+260h+var_2E0], rax
0x140076fdf  mov     r9, rax
0x140076fe2  test    ecx, ecx
0x140076fe4  jnz     short loc_140077027
0x140076fe6  mov     rdx, [rsi+3E8h]
0x140076fed  lea     rax, [rsp+360h+FinalUncompressedSize]
0x140076ff2  mov     [rsp+360h+WorkSpace], rdx; WorkSpace
0x140076ff7  mov     ecx, 2; CompressionFormatAndEngine
0x140076ffc  mov     edx, [rsi+3F4h]
0x140077002  mov     r9, r10; CompressedBuffer
0x140077005  mov     [rsp+360h+FinalCompressedSize], rax; FinalCompressedSize
0x14007700a  mov     [rsp+360h+UncompressedChunkSize], 400h; UncompressedChunkSize
0x140077012  mov     [rsp+360h+CompressedBufferSize], edx; CompressedBufferSize
0x140077016  mov     rdx, [rsi+3D8h]; UncompressedBuffer
0x14007701d  call    cs:__imp_RtlCompressBuffer
0x140077023  mov     edi, eax
0x140077025  jmp     short loc_14007705E
0x140077027  cmp     ecx, 1
0x14007702a  jnz     loc_1400770FA
0x140077030  mov     r9, [rsi+3D8h]
0x140077037  mov     rdx, r10
0x14007703a  mov     rcx, [rsi+360h]
0x140077041  mov     [rsp+360h+CompressedBufferSize], r8d
0x140077046  mov     r8d, [rsi+3F4h]
0x14007704d  call    XpressEncode
0x140077052  neg     eax
0x140077054  sbb     edi, edi
0x140077056  not     edi
0x140077058  and     edi, 3EBh
0x14007705e  test    edi, edi
0x140077060  jnz     loc_140077105
0x140077066  mov     ecx, [rsi+358h]
0x14007706c  mov     eax, [rsp+360h+FinalUncompressedSize]
0x140077070  mov     dword ptr [rsp+360h+var_300], eax
0x140077074  test    ecx, ecx
0x140077076  jnz     short loc_1400770A8
0x140077078  mov     r9, [rsi+3E0h]; CompressedBuffer
0x14007707f  lea     rdx, [rsp+360h+FinalUncompressedSize]
0x140077084  mov     r8d, [rsi+3D0h]; UncompressedBufferSize
0x14007708b  lea     ecx, [rdi+2]; CompressionFormat
0x14007708e  mov     qword ptr [rsp+360h+UncompressedChunkSize], rdx; FinalUncompressedSize
0x140077093  mov     rdx, [rsi+3D8h]; UncompressedBuffer
0x14007709a  mov     [rsp+360h+CompressedBufferSize], eax; CompressedBufferSize
0x14007709e  call    cs:__imp_RtlDecompressBuffer
0x1400770a4  mov     ecx, eax
0x1400770a6  jmp     short loc_140077109
0x1400770a8  cmp     ecx, 1
0x1400770ab  jnz     short loc_1400770F3
0x1400770ad  mov     eax, [rsi+3D0h]
0x1400770b3  mov     r8d, [rsi+3F4h]
0x1400770ba  mov     r9d, r8d
0x1400770bd  mov     rdx, [rsi+3E0h]
0x1400770c4  mov     rcx, [rsi+368h]
0x1400770cb  mov     [rsp+360h+UncompressedChunkSize], eax
0x1400770cf  mov     rax, [rsi+3D8h]
0x1400770d6  mov     qword ptr [rsp+360h+CompressedBufferSize], rax
0x1400770db  call    XpressDecode
0x1400770e0  mov     ecx, [rsp+360h+Status]
0x1400770e4  mov     r9, [rbp+260h+var_2E0]
0x1400770e8  test    eax, eax
0x1400770ea  jnz     short loc_14007710D
0x1400770ec  mov     edi, 3EBh
0x1400770f1  jmp     short loc_14007710D
0x1400770f3  mov     ecx, 57h ; 'W'
0x1400770f8  jmp     short loc_140077109
0x1400770fa  mov     ecx, [rsp+360h+Status]
0x1400770fe  mov     edi, 57h ; 'W'
0x140077103  jmp     short loc_14007710D
0x140077105  mov     ecx, [rsp+360h+Status]; Status
0x140077109  mov     r9, [rbp+260h+var_2E0]
0x14007710d  rdtsc
0x14007710f  mov     r13d, dword ptr [rsp+360h+var_300]
0x140077114  add     r13, [rbp+260h+var_2C8]
0x140077118  shl     rdx, 20h
0x14007711c  or      rax, rdx
0x14007711f  mov     rbx, rax
0x140077122  cmp     edi, 117h
0x140077128  jnz     short loc_140077130
0x14007712a  inc     [rsp+360h+var_2F4]
0x14007712e  jmp     short loc_14007713C
0x140077130  test    edi, edi
0x140077132  jnz     loc_1400772A7
0x140077138  test    ecx, ecx
0x14007713a  jnz     short loc_140077188
0x14007713c  cmp     [rsp+360h+var_31C], 0
0x140077141  jnz     short loc_140077155
0x140077143  sub     rbx, r9
0x140077146  mov     rcx, r12; this
0x140077149  mov     rdx, rbx; unsigned __int64
0x14007714c  call    ?AddSample@SampleManager@@QEAAX_K@Z; SampleManager::AddSample(unsigned __int64)
0x140077151  add     [rbp+260h+var_2D0], rbx
0x140077155  lea     rdx, [rsi+20h]
0x140077159  mov     r8, r14
0x14007715c  mov     rax, [rdx]
0x14007715f  mov     rbx, rdx
0x140077162  mov     ecx, [rax]
0x140077164  test    ecx, ecx
0x140077166  jnz     loc_140077226
0x14007716c  mov     rax, [r14]
0x14007716f  mov     ecx, [rax]
0x140077171  test    ecx, ecx
0x140077173  jnz     loc_140077226
0x140077179  mov     eax, dword ptr [rsp+360h+var_308]
0x14007717d  lea     rcx, [rsi+40h]
0x140077181  inc     eax
0x140077183  jmp     loc_140076F47
0x140077188  mov     rax, [r14]
0x14007718b  lock inc dword ptr [rax]
0x14007718e  call    cs:__imp_RtlNtStatusToDosError
0x140077194  lea     rcx, [rbp+260h+Buffer]; lpBuffer
0x140077198  mov     [rbp+260h+var_9C], 1
0x14007719f  mov     [rbp+260h+var_A0], eax
0x1400771a5  mov     [rbp+260h+var_98], 0
0x1400771b0  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x1400771b5  mov     rcx, [rsi+50h]; lpCriticalSection
0x1400771b9  call    cs:__imp_EnterCriticalSection
0x1400771bf  mov     eax, [rsi+58h]
0x1400771c2  lea     rcx, aBaseWinsatCpuC_0; "base\\winsat\\cpu\\compression.cpp"
0x1400771c9  mov     r9d, dword ptr [rsp+360h+var_308]; unsigned __int16
0x1400771ce  mov     r8d, 1FCh; int
0x1400771d4  mov     rbx, [rsi+10h]
0x1400771d8  mov     [rsp+360h+CompressedBufferSize], eax
0x1400771dc  lea     edx, [r8+2Eh]; char *
0x1400771e0  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x1400771e5  mov     rdx, rax
0x1400771e8  lea     rcx, [rbx+0F0h]
0x1400771ef  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400771f4  mov     edx, 0Ah
0x1400771f9  mov     rcx, rax
0x1400771fc  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140077201  lea     rdx, [rbp+260h+Buffer]
0x140077205  mov     rcx, rax
0x140077208  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007720d  mov     rcx, rax
0x140077210  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140077215  mov     rcx, [rsi+50h]; lpCriticalSection
0x140077219  call    cs:__imp_LeaveCriticalSection
0x14007721f  lea     rbx, [rsi+20h]
0x140077223  mov     r8, r14
0x140077226  mov     r14d, [rsp+360h+var_318]
0x14007722b  mov     rax, [rbx]
0x14007722e  mov     r10, rbx
0x140077231  mov     [rsp+360h+var_300], rbx
0x140077236  mov     rdi, r12
0x140077239  mov     ecx, [rax]
0x14007723b  test    ecx, ecx
0x14007723d  jnz     loc_1400773D6
0x140077243  mov     rax, [r8]
0x140077246  mov     [rsp+360h+var_300], rbx
0x14007724b  mov     ecx, [rax]
0x14007724d  test    ecx, ecx
0x14007724f  jnz     loc_1400773D6
0x140077255  cmp     byte ptr [rsp+360h+var_314], cl
0x140077259  jnz     short loc_14007726E
0x14007725b  mov     rcx, [rsi+350h]
0x140077262  mov     ecx, [rcx+208Ch]; dwMilliseconds
0x140077268  call    cs:__imp_Sleep
0x14007726e  inc     [rsp+360h+var_2F0]
0x140077272  call    cs:__imp_GetTickCount
0x140077278  sub     eax, [rsp+360h+var_320]
0x14007727c  mov     ecx, [rsp+360h+var_2E8]
0x140077280  cmp     eax, ecx
  ... truncated ...
```
