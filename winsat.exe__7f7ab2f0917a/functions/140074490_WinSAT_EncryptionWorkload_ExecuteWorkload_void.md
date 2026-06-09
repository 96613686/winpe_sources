# WinSAT::EncryptionWorkload::ExecuteWorkload(void)

- ea: `0x140074490`
- end: `0x140076166`
- name: `?ExecuteWorkload@EncryptionWorkload@WinSAT@@MEAAKXZ`
- size: `7382`
- prototype: `unsigned int __fastcall(WinSAT::EncryptionWorkload *__hidden this)`
- caller_count: `0`
- callee_count: `30`
- tags: ``

## callees

- `0x140003560`
- `0x140004170`
- `0x140004348`
- `0x14000449c`
- `0x140005cf4`
- `0x140005f4c`
- `0x14000695c`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x140011f58`
- `0x140015ccc`
- `0x140016588`
- `0x140016d04`
- `0x140017af0`
- `0x140019a1c`
- `0x14002093c`
- `0x14003a150`
- `0x140058488`
- `0x1400584b0`
- `0x140058818`
- `0x140059010`
- `0x14005cc74`
- `0x14005ed80`
- `0x140074340`
- `0x140074490`
- `0x14007616c`
- `0x1400761b4`
- `0x140079b30`
- `0x140118008`

## import_xrefs

- `ADVAPI32!CryptEncrypt` at `0x140074704`
- `ADVAPI32!CryptEncrypt` at `0x140074704`
- `ADVAPI32!CryptDecrypt` at `0x140074737`
- `ADVAPI32!CryptDecrypt` at `0x140074737`
- `ADVAPI32!CryptCreateHash` at `0x140074772`
- `ADVAPI32!CryptCreateHash` at `0x140074772`
- `ADVAPI32!CryptHashData` at `0x14007478e`
- `ADVAPI32!CryptHashData` at `0x14007478e`
- `ADVAPI32!CryptDestroyHash` at `0x1400747a1`
- `ADVAPI32!CryptDestroyHash` at `0x1400747a1`
- `KERNEL32!GetTickCount` at `0x1400744ec`
- `KERNEL32!GetTickCount` at `0x1400745e2`
- `KERNEL32!GetTickCount` at `0x140074991`
- `KERNEL32!GetTickCount` at `0x1400749e2`
- `KERNEL32!GetTickCount` at `0x140074a12`
- `KERNEL32!GetTickCount` at `0x1400744ec`
- `KERNEL32!GetTickCount` at `0x1400745e2`
- `KERNEL32!GetTickCount` at `0x140074991`
- `KERNEL32!GetTickCount` at `0x1400749e2`
- `KERNEL32!GetTickCount` at `0x140074a12`
- `KERNEL32!EnterCriticalSection` at `0x1400747dd`
- `KERNEL32!EnterCriticalSection` at `0x1400748ca`
- `KERNEL32!EnterCriticalSection` at `0x140074dde`
- `KERNEL32!EnterCriticalSection` at `0x140076018`
- `KERNEL32!EnterCriticalSection` at `0x1400747dd`
- `KERNEL32!EnterCriticalSection` at `0x1400748ca`
- `KERNEL32!EnterCriticalSection` at `0x140074dde`
- `KERNEL32!EnterCriticalSection` at `0x140076018`
- `KERNEL32!LeaveCriticalSection` at `0x14007484a`
- `KERNEL32!LeaveCriticalSection` at `0x140074937`
- `KERNEL32!LeaveCriticalSection` at `0x140076009`
- `KERNEL32!LeaveCriticalSection` at `0x14007611f`
- `KERNEL32!LeaveCriticalSection` at `0x14007484a`
- `KERNEL32!LeaveCriticalSection` at `0x140074937`
- `KERNEL32!LeaveCriticalSection` at `0x140076009`
- `KERNEL32!LeaveCriticalSection` at `0x14007611f`
- `KERNEL32!GetLastError` at `0x140074a35`
- `KERNEL32!GetLastError` at `0x140074a35`
- `KERNEL32!Sleep` at `0x140074987`
- `KERNEL32!Sleep` at `0x140074987`
- `KERNEL32!SetLastError` at `0x140076132`
- `KERNEL32!SetLastError` at `0x140076132`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
DWORD __fastcall WinSAT::EncryptionWorkload::ExecuteWorkload(WinSAT::EncryptionWorkload *this)
{
  __int64 v2; // r15
  _DWORD *v3; // rax
  unsigned int v4; // r13d
  DWORD TickCount; // eax
  __int64 v6; // rdx
  char v7; // di
  __int64 v8; // r14
  unsigned __int64 v9; // rsi
  __int64 PerformanceCounter64; // r12
  unsigned __int64 v11; // rcx
  DWORD i; // eax
  unsigned __int8 *v13; // rax
  unsigned __int8 *v14; // rax
  int v15; // ecx
  int v16; // r8d
  unsigned __int64 v17; // rax
  mlib::MUILoader *v18; // rax
  __int64 *v19; // rax
  mlib::MUILoader *v20; // rax
  __int64 *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  DWORD v25; // eax
  DWORD LastError; // eax
  mlib *v28; // rcx
  __int64 v29; // rdi
  mlib *v30; // rcx
  __int64 PerformanceFrequency64; // rax
  double v32; // xmm1_8
  double v33; // xmm0_8
  double v34; // xmm0_8
  __int64 v35; // rdi
  double v36; // xmm6_8
  double v37; // xmm6_8
  __int64 v38; // rcx
  double v39; // xmm2_8
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  double v43; // xmm7_8
  double v44; // xmm7_8
  __int64 v45; // rsi
  double v46; // xmm0_8
  double v47; // xmm7_8
  double v48; // xmm6_8
  double v49; // xmm3_8
  double v50; // xmm3_8
  __int64 v51; // rcx
  double v52; // xmm0_8
  __int64 v53; // rax
  double v54; // xmm4_8
  __int64 v55; // rcx
  double v56; // xmm8_8
  __int64 v57; // rax
  double v58; // xmm8_8
  __int64 v59; // rcx
  double v60; // xmm9_8
  __int64 v61; // rax
  double v62; // xmm9_8
  double v63; // xmm5_8
  __int64 v64; // rcx
  double v65; // xmm1_8
  __int64 v66; // rax
  __int64 v67; // rcx
  double v68; // xmm0_8
  __int64 v69; // rax
  __int64 *v70; // rax
  __int64 *v71; // rax
  __int64 *v72; // rax
  __int64 *v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 *v76; // rax
  __int64 *v77; // rax
  __int64 *v78; // rax
  __int64 *v79; // rax
  __int64 *v80; // rax
  __int64 v81; // rax
  __int64 *v82; // rax
  __int64 *v83; // rax
  __int64 v84; // rax
  __int64 *v85; // rax
  __int64 v86; // rax
  __int64 *v87; // rax
  __int64 v88; // rax
  __int64 *v89; // rax
  __int64 *v90; // rax
  __int64 *v91; // rax
  __int64 *v92; // rax
  __int64 *v93; // rax
  __int64 *v94; // rax
  __int64 *v95; // rax
  __int64 *v96; // rax
  __int64 *v97; // rax
  __int64 *v98; // rax
  __int64 *v99; // rax
  __int64 *v100; // rax
  __int64 *v101; // rax
  __int64 *v102; // rax
  __int64 *v103; // rax
  __int64 *v104; // rax
  __int64 v105; // rax
  __int64 *v106; // rax
  __int64 *v107; // rax
  __int64 *v108; // rax
  const wchar_t *v109; // rdx
  __int64 *v110; // rax
  __int64 *v111; // rax
  __int64 *v112; // rax
  __int64 *v113; // rax
  __int64 *v114; // rax
  __int64 *v115; // rax
  __int64 *v116; // rax
  __int64 *v117; // rax
  __int64 *v118; // rax
  __int64 *v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 *v122; // rax
  __int64 v123; // rax
  __int64 v124; // rax
  __int64 *v125; // rax
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 *v128; // rax
  __int64 v129; // rax
  __int64 v130; // rax
  __int64 *v131; // rax
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 *v134; // rax
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 *v137; // rax
  __int64 v138; // rax
  __int64 v139; // rax
  __int64 *v140; // rax
  __int64 v141; // rax
  __int64 v142; // rax
  __int64 *v143; // rax
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rcx
  __int64 v147; // r15
  __int64 v148; // rsi
  __int64 v149; // r14
  unsigned __int64 v150; // rdi
  __int64 *v151; // rax
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // r8
  double v155; // xmm1_8
  double v156; // xmm1_8
  __int64 v157; // rcx
  double v158; // xmm0_8
  __int64 v159; // rax
  __int64 v160; // rax
  int v161; // r8d
  __int64 *v162; // rax
  __int64 v163; // rax
  __int64 v164; // rax
  __int64 v165; // r8
  double v166; // xmm1_8
  double v167; // xmm1_8
  __int64 v168; // rcx
  double v169; // xmm0_8
  __int64 v170; // rax
  __int64 v171; // rax
  int v172; // r8d
  __int64 *v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // r8
  double v177; // xmm1_8
  double v178; // xmm1_8
  __int64 v179; // rcx
  double v180; // xmm0_8
  __int64 v181; // rax
  __int64 v182; // rax
  int v183; // r8d
  __int64 *v184; // rax
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // r8
  double v188; // xmm1_8
  double v189; // xmm1_8
  __int64 v190; // rcx
  double v191; // xmm0_8
  __int64 v192; // rax
  __int64 v193; // rax
  __int64 v194; // r8
  __int64 *v195; // rax
  __int64 v196; // rax
  __int64 v197; // rax
  __int64 *v198; // rax
  __int64 *v199; // rax
  const wchar_t *v200; // rdx
  __int64 *v201; // rax
  mlib::MUILoader *v202; // rax
  _DWORD *v203; // rdi
  __int64 *v204; // rcx
  mlib::MUILoader *v205; // rax
  __int64 v206; // rdx
  __int64 v207; // rax
  DWORD v208; // ebx
  DWORD pdwDataLen[2]; // [rsp+48h] [rbp-C0h] BYREF
  HCRYPTHASH phHash; // [rsp+50h] [rbp-B8h] BYREF
  int v211; // [rsp+58h] [rbp-B0h]
  unsigned int v212; // [rsp+5Ch] [rbp-ACh]
  unsigned int v213; // [rsp+60h] [rbp-A8h]
  unsigned int v214; // [rsp+64h] [rbp-A4h]
  int v215; // [rsp+68h] [rbp-A0h]
  unsigned int v216; // [rsp+6Ch] [rbp-9Ch]
  DWORD v217; // [rsp+70h] [rbp-98h]
  unsigned __int64 *v218; // [rsp+78h] [rbp-90h] BYREF
  unsigned __int64 *v219; // [rsp+80h] [rbp-88h] BYREF
  __int64 v220; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int64 v221; // [rsp+90h] [rbp-78h]
  __int64 v222; // [rsp+98h] [rbp-70h] BYREF
  __int64 v223; // [rsp+A0h] [rbp-68h]
  __int64 v224; // [rsp+A8h] [rbp-60h]
  _BYTE v225[112]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v226; // [rsp+168h] [rbp+60h] BYREF
  __int64 v227; // [rsp+170h] [rbp+68h] BYREF
  char v228; // [rsp+178h] [rbp+70h]
  unsigned __int64 v229; // [rsp+180h] [rbp+78h]

  v2 = 0;
  v3 = (_DWORD *)*((_QWORD *)this + 106);
  v216 = v3[2091];
  v4 = v3[2092];
  v214 = v3[2093];
  pdwDataLen[0] = 0;
  TickCount = GetTickCount();
  v6 = *((_QWORD *)this + 106);
  v223 = TickCount + (int)(*(double *)(v6 + 8344) * 1000.0);
  v224 = TickCount + (int)(*(double *)(v6 + 8352) * 1000.0);
  v7 = *(_BYTE *)(v6 + 8360);
  LOBYTE(v227) = v7;
  v8 = 0;
  LOBYTE(v226) = 0;
  v9 = 0;
  v212 = -1;
  v213 = 0;
  v211 = 0;
  v228 = *(_BYTE *)(v6 + 8378);
  PerformanceCounter64 = mlib::QueryPerformanceCounter64(0);
  *((_QWORD *)this + 99) = __rdtsc();
  while ( !WinSAT::MPWorkload::ExitLoop(this) && !v7 )
  {
    v11 = (__int64)(*((_QWORD *)this + 83) - *((_QWORD *)this + 81)) >> 3;
    if ( v11 < *((_QWORD *)this + 95) && (__int64)(*((_QWORD *)this + 82) - *((_QWORD *)this + 81)) >> 3 >= v11 )
      SampleManager::GrowSizeBy((WinSAT::EncryptionWorkload *)((char *)this + 648), v216);
    if ( !WinSAT::MPWorkload::Rendevous(this) )
      break;
    v217 = GetTickCount();
    for ( i = 0; ; i = pdwDataLen[1] + 1 )
    {
      pdwDataLen[1] = i;
      if ( i >= v4 )
        goto LABEL_38;
      pdwDataLen[0] = *((_DWORD *)this + 244);
      if ( **((_DWORD **)this + 4) || **((_DWORD **)this + 8) )
        goto LABEL_38;
      v13 = RotatingBuffer::RotateBuffer((WinSAT::EncryptionWorkload *)((char *)this + 856));
      *((_QWORD *)this + 123) = v13;
      if ( !v13
        || (v14 = RotatingBuffer::RotateBuffer((WinSAT::EncryptionWorkload *)((char *)this + 904)),
            (*((_QWORD *)this + 124) = v14) == 0) )
      {
        LastError = GetLastError();
        return WinSAT::EncryptionWorkload::DumpRotateBufferError(this, LastError);
      }
      LODWORD(phHash) = 0;
      v215 = 0;
      memcpy_0(v14, *((const void **)this + 123), *((unsigned int *)this + 244));
      v15 = *((_DWORD *)this + 238);
      if ( v15 == 2 )
      {
        pdwDataLen[0] = *((_DWORD *)this + 252);
        v221 = __rdtsc();
        XpressCrc32(*((_QWORD *)this + 124), *((unsigned int *)this + 252));
        v16 = 1;
        LODWORD(phHash) = 1;
        goto LABEL_27;
      }
      v221 = __rdtsc();
      if ( v15 )
      {
        if ( v15 == 1 )
        {
          phHash = 0;
          CryptCreateHash(*((_QWORD *)this + 120), 0x8004u, 0, 0, &phHash);
          LODWORD(v229) = CryptHashData(phHash, *((const BYTE **)this + 124), *((_DWORD *)this + 252), 0);
          if ( phHash )
            CryptDestroyHash(phHash);
          LODWORD(phHash) = 1;
        }
        else
        {
          LODWORD(v229) = 0;
        }
      }
      else
      {
        LODWORD(v229) = CryptEncrypt(
                          *((_QWORD *)this + 121),
                          0,
                          1,
                          0,
                          *((BYTE **)this + 124),
                          pdwDataLen,
                          *((_DWORD *)this + 252));
        if ( !(_DWORD)v229 )
        {
          v16 = 0;
          goto LABEL_27;
        }
        LODWORD(phHash) = CryptDecrypt(*((_QWORD *)this + 121), 0, 1, 0, *((BYTE **)this + 124), pdwDataLen);
      }
      v16 = v229;
LABEL_27:
      v17 = __rdtsc();
      v229 = v17;
      v8 += pdwDataLen[0];
      if ( !v16 )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v18 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v225, 535);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          &v220,
          (__int64)v18);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          (__int64 *)&v218,
          1024);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
          &v218,
          *(_QWORD *)(v220 + 24),
          pdwDataLen[1],
          *((unsigned int *)this + 22));
        v19 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 2) + 240LL),
                &v218);
        std::endl(v19);
        LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v215 = 1;
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v218);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v220);
        v17 = v229;
      }
      if ( !(_DWORD)phHash )
        break;
      if ( v215 )
        goto LABEL_37;
      if ( !(_BYTE)v226 )
      {
        v229 = v17 - v221;
        SampleManager::AddSample((WinSAT::EncryptionWorkload *)((char *)this + 648), v17 - v221);
        v2 += v229;
      }
      if ( **((_DWORD **)this + 4) || **((_DWORD **)this + 8) )
        goto LABEL_38;
    }
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    v20 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v225, 536);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v222,
      (__int64)v20);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      (__int64 *)&v219,
      1024);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      &v219,
      *(_QWORD *)(v222 + 24),
      pdwDataLen[1],
      *((unsigned int *)this + 22));
    v21 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 2) + 240LL),
            &v219);
    std::endl(v21);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v219);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v222);
LABEL_37:
    _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
LABEL_38:
    if ( **((_DWORD **)this + 4) || **((_DWORD **)this + 8) )
      break;
    if ( !v228 )
      Sleep(*(_DWORD *)(*((_QWORD *)this + 106) + 8332LL));
    ++v211;
    v22 = GetTickCount() - v217;
    v23 = v213;
    if ( v22 > v213 )
      v23 = v22;
    v213 = v23;
    v24 = v212;
    if ( v22 < v212 )
      v24 = v22;
    v212 = v24;
    if ( v22 >= 0xA )
    {
      if ( v22 < 0x4B )
        v4 += v4 >> 1;
    }
    else
    {
      v4 *= 2;
    }
    if ( (_BYTE)v226 )
      goto LABEL_2;
    SampleManager::Process((WinSAT::EncryptionWorkload *)((char *)this + 648), v214);
    if ( GetTickCount() >= (unsigned int)v223 && *((_BYTE *)this + 752) )
    {
      v9 = __rdtsc();
      LOBYTE(v226) = 1;
      _InterlockedIncrement(*((volatile signed __int32 **)this + 7));
LABEL_2:
      v7 = v227;
      continue;
    }
    v25 = GetTickCount();
    v7 = v227;
    if ( v25 >= (unsigned int)v224 )
    {
      LOBYTE(v226) = 1;
      _InterlockedIncrement(*((volatile signed __int32 **)this + 7));
    }
  }
  if ( !**((_DWORD **)this + 4) )
  {
    v28 = (mlib *)**((unsigned int **)this + 8);
    if ( !(_DWORD)v28 )
    {
      if ( !*((_BYTE *)this + 753) )
        SampleManager::Process((WinSAT::EncryptionWorkload *)((char *)this + 648), v214);
      v29 = mlib::QueryPerformanceCounter64(v28);
      *((_QWORD *)this + 100) = __rdtsc();
      PerformanceFrequency64 = mlib::QueryPerformanceFrequency64(v30);
      if ( PerformanceFrequency64 < 0 )
        v32 = (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1))
            + (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1));
      else
        v32 = (double)(int)PerformanceFrequency64;
      if ( PerformanceCounter64 < 0 )
        v33 = (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1))
            + (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1));
      else
        v33 = (double)(int)PerformanceCounter64;
      *((double *)this + 135) = v33 / v32;
      if ( v29 < 0 )
        v34 = (double)(int)(v29 & 1 | ((unsigned __int64)v29 >> 1))
            + (double)(int)(v29 & 1 | ((unsigned __int64)v29 >> 1));
      else
        v34 = (double)(int)v29;
      *((double *)this + 136) = v34 / v32;
      v35 = v29 - PerformanceCounter64;
      if ( v35 < 0 )
        v36 = (double)(int)(v35 & 1 | ((unsigned __int64)v35 >> 1))
            + (double)(int)(v35 & 1 | ((unsigned __int64)v35 >> 1));
      else
        v36 = (double)(int)v35;
      v37 = v36 / v32;
      *((double *)this + 137) = v37;
      v38 = *((_QWORD *)this + 105);
      if ( v38 < 0 )
      {
        v40 = *((_QWORD *)this + 105) & 1LL | ((unsigned __int64)v38 >> 1);
        v39 = (double)(int)v40 + (double)(int)v40;
      }
      else
      {
        v39 = (double)(int)v38;
      }
      v41 = *((_QWORD *)this + 99);
      v42 = *((_QWORD *)this + 100) - v41;
      if ( v42 < 0 )
        v43 = (double)(int)(v42 & 1 | ((unsigned __int64)v42 >> 1))
            + (double)(int)(v42 & 1 | ((unsigned __int64)v42 >> 1));
      else
        v43 = (double)(int)v42;
      v44 = v43 / v39;
      *((double *)this + 138) = v44;
      if ( v9 )
      {
        v45 = v9 - v41;
        if ( v45 < 0 )
          v46 = (double)(int)(v45 & 1 | ((unsigned __int64)v45 >> 1))
              + (double)(int)(v45 & 1 | ((unsigned __int64)v45 >> 1));
        else
          v46 = (double)(int)v45;
        *((double *)this + 139) = v46 / v39;
      }
      *(_QWORD *)&v47 = COERCE_UNSIGNED_INT64(v44 - v37) & _xmm;
      v48 = v37 / 1000.0 * 5.0;
      *((_BYTE *)this + 808) = v47 > v48;
      if ( v2 < 0 )
        v49 = (double)(int)(v2 & 1 | ((unsigned __int64)v2 >> 1)) + (double)(int)(v2 & 1 | ((unsigned __int64)v2 >> 1));
      else
        v49 = (double)(int)v2;
      v50 = v49 / v39;
      *((double *)this + 129) = v50;
      v51 = (__int64)(*((_QWORD *)this + 82) - *((_QWORD *)this + 81)) >> 3;
      if ( v51 < 0 )
      {
        v53 = ((__int64)(*((_QWORD *)this + 82) - *((_QWORD *)this + 81)) >> 3) & 1 | ((unsigned __int64)v51 >> 1);
        v52 = (double)(int)v53 + (double)(int)v53;
      }
      else
      {
        v52 = (double)(int)v51;
      }
      *((double *)this + 130) = v52;
      if ( v8 < 0 )
        v54 = (double)(int)(v8 & 1 | ((unsigned __int64)v8 >> 1)) + (double)(int)(v8 & 1 | ((unsigned __int64)v8 >> 1));
      else
        v54 = (double)(int)v8;
      *((double *)this + 131) = v54;
      v55 = *((_QWORD *)this + 87);
      if ( v55 < 0 )
      {
        v57 = *((_QWORD *)this + 87) & 1LL | ((unsigned __int64)v55 >> 1);
        v56 = (double)(int)v57 + (double)(int)v57;
      }
      else
      {
        v56 = (double)(int)v55;
      }
      v58 = v56 / v39;
      v59 = *((_QWORD *)this + 91);
      if ( v59 < 0 )
      {
        v61 = *((_QWORD *)this + 91) & 1LL | ((unsigned __int64)v59 >> 1);
        v60 = (double)(int)v61 + (double)(int)v61;
      }
      else
      {
        v60 = (double)(int)v59;
      }
      v62 = v60 / v39;
      v63 = (double)*((int *)this + 252);
      *((double *)this + 103) = v63 / v62;
      *((double *)this + 132) = v63 / v58;
      v64 = *((_QWORD *)this + 85);
      if ( v64 < 0 )
      {
        v66 = *((_QWORD *)this + 85) & 1LL | ((unsigned __int64)v64 >> 1);
        v65 = (double)(int)v66 + (double)(int)v66;
      }
      else
      {
        v65 = (double)(int)v64;
      }
      *((double *)this + 133) = v63 / (v65 / v39);
      v67 = *((_QWORD *)this + 86);
      if ( v67 < 0 )
      {
        v69 = *((_QWORD *)this + 86) & 1LL | ((unsigned __int64)v67 >> 1);
        v68 = (double)(int)v69 + (double)(int)v69;
      }
      else
      {
        v68 = (double)(int)v67;
      }
      *((double *)this + 104) = v63 / (v68 / v39);
      *((double *)this + 134) = v54 / v50;
      if ( *((_BYTE *)this + 24) )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
        v70 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"> CPU(");
        v71 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v70, *((_DWORD *)this + 22));
        v72 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v71, (__int64)L")\n");
        v73 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                v72,
                (__int64)L"  --                     elapsed ticks : ");
        LODWORD(v226) = 12;
        v74 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v73, &v226);
        v75 = std::basic_ostream<unsigned short>::operator<<(v74, v2);
        *(_DWORD *)(*(int *)(*(_QWORD *)v75 + 4LL) + v75 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v75 + 4LL) + v75 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v75 + 4LL) + v75 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v75, "\n");
        v76 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --               cummulative seconds : ");
        *(_DWORD *)((char *)v76 + *(int *)(*v76 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v76 + *(int *)(*v76 + 4) + 32) = 9;
        *(__int64 *)((char *)v76 + *(int *)(*v76 + 4) + 40) = 0;
        v77 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v76, *((double *)this + 129));
        *(_DWORD *)((char *)v77 + *(int *)(*v77 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v77 + *(int *)(*v77 + 4) + 88) = 32;
        *(__int64 *)((char *)v77 + *(int *)(*v77 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v77, (__int64)L"\n");
        v78 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --               good data duration  : ");
        *(_DWORD *)((char *)v78 + *(int *)(*v78 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v78 + *(int *)(*v78 + 4) + 32) = 9;
        *(__int64 *)((char *)v78 + *(int *)(*v78 + 4) + 40) = 0;
        v79 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v78, *((double *)this + 139));
        *(_DWORD *)((char *)v79 + *(int *)(*v79 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v79 + *(int *)(*v79 + 4) + 88) = 32;
        *(__int64 *)((char *)v79 + *(int *)(*v79 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v79, (__int64)L"\n");
        v80 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --                      cipher size  : ");
        LODWORD(v226) = 12;
        v81 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v80, &v226);
        v82 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v81, *((_DWORD *)this + 252));
        *(_DWORD *)((char *)v82 + *(int *)(*v82 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v82 + *(int *)(*v82 + 4) + 88) = 32;
        *(__int64 *)((char *)v82 + *(int *)(*v82 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v82, (__int64)L"\n");
        v83 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --               Measured Value Secs : ");
        *(_DWORD *)((char *)v83 + *(int *)(*v83 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v83 + *(int *)(*v83 + 4) + 32) = 9;
        *(__int64 *)((char *)v83 + *(int *)(*v83 + 4) + 40) = 0;
        v84 = std::basic_ostream<unsigned short>::operator<<((__int64)v83, v62);
        *(_DWORD *)(*(int *)(*(_QWORD *)v84 + 4LL) + v84 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v84 + 4LL) + v84 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v84 + 4LL) + v84 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v84, "\n");
        v85 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --                       min seconds : ");
        *(_DWORD *)((char *)v85 + *(int *)(*v85 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v85 + *(int *)(*v85 + 4) + 32) = 9;
        *(__int64 *)((char *)v85 + *(int *)(*v85 + 4) + 40) = 0;
        v86 = std::basic_ostream<unsigned short>::operator<<((__int64)v85, v58);
        *(_DWORD *)(*(int *)(*(_QWORD *)v86 + 4LL) + v86 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v86 + 4LL) + v86 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v86 + 4LL) + v86 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v86, "\n");
        v87 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --                 buffer pass count : ");
        LODWORD(v226) = 12;
        v88 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v87, &v226);
        v89 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v88, *((double *)this + 130));
        *(_DWORD *)((char *)v89 + *(int *)(*v89 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v89 + *(int *)(*v89 + 4) + 88) = 32;
        *(__int64 *)((char *)v89 + *(int *)(*v89 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v89, (__int64)L"\n");
        v90 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --             total bytes processed : ");
        *(_DWORD *)((char *)v90 + *(int *)(*v90 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v90 + *(int *)(*v90 + 4) + 32) = 0;
        *(__int64 *)((char *)v90 + *(int *)(*v90 + 4) + 40) = 0;
        v91 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v90, *((double *)this + 131));
        *(_DWORD *)((char *)v91 + *(int *)(*v91 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v91 + *(int *)(*v91 + 4) + 88) = 32;
        *(__int64 *)((char *)v91 + *(int *)(*v91 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v91, (__int64)L"\n");
        v92 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --                               B/s : ");
        *(_DWORD *)((char *)v92 + *(int *)(*v92 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v92 + *(int *)(*v92 + 4) + 32) = 0;
        *(__int64 *)((char *)v92 + *(int *)(*v92 + 4) + 40) = 0;
        v93 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v92, *((double *)this + 103));
        *(_DWORD *)((char *)v93 + *(int *)(*v93 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v93 + *(int *)(*v93 + 4) + 88) = 32;
        *(__int64 *)((char *)v93 + *(int *)(*v93 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v93, (__int64)L"\n");
        v94 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --                      B/s (median) : ");
        *(_DWORD *)((char *)v94 + *(int *)(*v94 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v94 + *(int *)(*v94 + 4) + 32) = 0;
        *(__int64 *)((char *)v94 + *(int *)(*v94 + 4) + 40) = 0;
        v95 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v94, *((double *)this + 133));
        *(_DWORD *)((char *)v95 + *(int *)(*v95 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v95 + *(int *)(*v95 + 4) + 88) = 32;
        *(__int64 *)((char *)v95 + *(int *)(*v95 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v95, (__int64)L"\n");
        v96 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --                         B/s(mean) : ");
        *(_DWORD *)((char *)v96 + *(int *)(*v96 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v96 + *(int *)(*v96 + 4) + 32) = 0;
        *(__int64 *)((char *)v96 + *(int *)(*v96 + 4) + 40) = 0;
        v97 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v96, *((double *)this + 104));
        *(_DWORD *)((char *)v97 + *(int *)(*v97 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v97 + *(int *)(*v97 + 4) + 88) = 32;
        *(__int64 *)((char *)v97 + *(int *)(*v97 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v97, (__int64)L"\n");
        v98 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                (__int64)L"  --                       B/s (mean2) : ");
        *(_DWORD *)((char *)v98 + *(int *)(*v98 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v98 + *(int *)(*v98 + 4) + 32) = 0;
        *(__int64 *)((char *)v98 + *(int *)(*v98 + 4) + 40) = 0;
        v99 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v98, *((double *)this + 104));
        *(_DWORD *)((char *)v99 + *(int *)(*v99 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v99 + *(int *)(*v99 + 4) + 88) = 32;
        *(__int64 *)((char *)v99 + *(int *)(*v99 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v99, (__int64)L"\n");
        v100 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                      Elapsed Secs : ");
        *(_DWORD *)((char *)v100 + *(int *)(*v100 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v100 + *(int *)(*v100 + 4) + 32) = 9;
        *(__int64 *)((char *)v100 + *(int *)(*v100 + 4) + 40) = 0;
        v101 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v100, *((double *)this + 137));
        *(_DWORD *)((char *)v101 + *(int *)(*v101 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v101 + *(int *)(*v101 + 4) + 88) = 32;
        *(__int64 *)((char *)v101 + *(int *)(*v101 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v101, (__int64)L"\n");
        v102 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                RDTSC Elapsed Secs : ");
        *(_DWORD *)((char *)v102 + *(int *)(*v102 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v102 + *(int *)(*v102 + 4) + 32) = 9;
        *(__int64 *)((char *)v102 + *(int *)(*v102 + 4) + 40) = 0;
        v103 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v102, *((double *)this + 138));
        *(_DWORD *)((char *)v103 + *(int *)(*v103 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v103 + *(int *)(*v103 + 4) + 88) = 32;
        *(__int64 *)((char *)v103 + *(int *)(*v103 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v103, (__int64)L"\n");
        v104 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                         diff secs : ");
        *(_DWORD *)((char *)v104 + *(int *)(*v104 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v104 + *(int *)(*v104 + 4) + 32) = 9;
        *(__int64 *)((char *)v104 + *(int *)(*v104 + 4) + 40) = 0;
        v105 = std::basic_ostream<unsigned short>::operator<<((__int64)v104, v47);
        *(_DWORD *)(*(int *)(*(_QWORD *)v105 + 4LL) + v105 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v105 + 4LL) + v105 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v105 + 4LL) + v105 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v105, "\n");
        v106 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                  max allowed diff : ");
        *(_DWORD *)((char *)v106 + *(int *)(*v106 + 4) + 24) |= 0x2080u;
        *(__int64 *)((char *)v106 + *(int *)(*v106 + 4) + 32) = 9;
        *(__int64 *)((char *)v106 + *(int *)(*v106 + 4) + 40) = 0;
        v107 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v106, v48);
        *(_DWORD *)((char *)v107 + *(int *)(*v107 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v107 + *(int *)(*v107 + 4) + 88) = 32;
        *(__int64 *)((char *)v107 + *(int *)(*v107 + 4) + 40) = 0;
        v108 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v107, (__int64)L"  - ");
        v109 = L"Delta VIOLATION!";
        if ( !*((_BYTE *)this + 808) )
          v109 = L"delta OK";
        v110 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v108, (__int64)v109);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v110, (__int64)L"\n");
        v111 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --             measurment loop count : ");
        v112 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v111, v211);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v112, (__int64)L"\n");
        v113 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                 sample block size : ");
        v114 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v113, v4);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v114, (__int64)L"\n");
        v115 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                 min loop duration : ");
        v116 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v115, v212);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v116, (__int64)L"\n");
        v117 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"  --                 max loop duration : ");
        v118 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v117, v213);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v118, (__int64)L"\n");
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(
          (__int64 *)(*((_QWORD *)this + 1) + 240LL),
          (__int64)L"  -- Statistics --\n");
        v119 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       + Total Samples : ");
        LODWORD(v226) = 12;
        v120 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v119, &v226);
        v121 = std::basic_ostream<unsigned short>::operator<<(
                 v120,
                 (__int64)(*((_QWORD *)this + 82) - *((_QWORD *)this + 81)) >> 3);
        *(_DWORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v121 + 4LL) + v121 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v121, "\n");
        v122 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +           min : ");
        LODWORD(v226) = 12;
        v123 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v122, &v226);
        v124 = std::basic_ostream<unsigned short>::operator<<(v123, *((_QWORD *)this + 87));
        *(_DWORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v124 + 4LL) + v124 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v124, "\n");
        v125 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +lower quartile : ");
        LODWORD(v226) = 12;
        v126 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v125, &v226);
        v127 = std::basic_ostream<unsigned short>::operator<<(v126, *((_QWORD *)this + 91));
        *(_DWORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v127 + 4LL) + v127 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v127, "\n");
        v128 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +        median : ");
        LODWORD(v226) = 12;
        v129 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v128, &v226);
        v130 = std::basic_ostream<unsigned short>::operator<<(v129, *((_QWORD *)this + 85));
        *(_DWORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v130, "\n");
        v131 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +          mean : ");
        LODWORD(v226) = 12;
        v132 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v131, &v226);
        v133 = std::basic_ostream<unsigned short>::operator<<(v132, *((_QWORD *)this + 86));
        *(_DWORD *)(*(int *)(*(_QWORD *)v133 + 4LL) + v133 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v133 + 4LL) + v133 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v133 + 4LL) + v133 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v133, "\n");
        v134 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +upper quartile : ");
        LODWORD(v226) = 12;
        v135 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v134, &v226);
        v136 = std::basic_ostream<unsigned short>::operator<<(v135, *((_QWORD *)this + 90));
        *(_DWORD *)(*(int *)(*(_QWORD *)v136 + 4LL) + v136 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v136 + 4LL) + v136 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v136 + 4LL) + v136 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v136, "\n");
        v137 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +           max : ");
        LODWORD(v226) = 12;
        v138 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, &v226);
        v139 = std::basic_ostream<unsigned short>::operator<<(v138, *((_QWORD *)this + 88));
        *(_DWORD *)(*(int *)(*(_QWORD *)v139 + 4LL) + v139 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v139 + 4LL) + v139 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v139 + 4LL) + v139 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v139, "\n");
        v140 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +         range : ");
        LODWORD(v226) = 12;
        v141 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v140, &v226);
        v142 = std::basic_ostream<unsigned short>::operator<<(v141, *((_QWORD *)this + 89));
        *(_DWORD *)(*(int *)(*(_QWORD *)v142 + 4LL) + v142 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v142 + 4LL) + v142 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v142 + 4LL) + v142 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, "\n");
        v143 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +      IQ range : ");
        LODWORD(v226) = 12;
        v144 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v143, &v226);
        v145 = std::basic_ostream<unsigned short>::operator<<(v144, *((_QWORD *)this + 92));
        *(_DWORD *)(*(int *)(*(_QWORD *)v145 + 4LL) + v145 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v145 + 4LL) + v145 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v145 + 4LL) + v145 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, "\n");
        v146 = *((_QWORD *)this + 87);
        v147 = *((_QWORD *)this + 85) - v146;
        v148 = *((_QWORD *)this + 91) - v146;
        v149 = *((_QWORD *)this + 85) - *((_QWORD *)this + 91);
        v150 = v146 * (unsigned __int64)v214 / 0x186A0;
        v151 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +    median-Min : ");
        LODWORD(v226) = 12;
        v152 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v151, &v226);
        v153 = std::basic_ostream<unsigned short>::operator<<(v152, v147);
        *(_DWORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 40) = 0;
        v154 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v153, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v154 + 4LL) + v154 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v154 + 4LL) + v154 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v154 + 4LL) + v154 + 40) = 3;
        if ( v147 < 0 )
          v155 = (double)(int)(v147 & 1 | ((unsigned __int64)v147 >> 1))
               + (double)(int)(v147 & 1 | ((unsigned __int64)v147 >> 1));
        else
          v155 = (double)(int)v147;
        v156 = v155 * 100.0;
        v157 = *((_QWORD *)this + 87);
        if ( v157 < 0 )
        {
          v159 = *((_QWORD *)this + 87) & 1LL | ((unsigned __int64)v157 >> 1);
          v158 = (double)(int)v159 + (double)(int)v159;
        }
        else
        {
          v158 = (double)(int)v157;
        }
        v160 = std::basic_ostream<unsigned short>::operator<<(v154, v156 / v158);
        *(_DWORD *)(*(int *)(*(_QWORD *)v160 + 4LL) + v160 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v160 + 4LL) + v160 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v160 + 4LL) + v160 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v160, "% of min \n", v161);
        v162 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +        lq-Min : ");
        LODWORD(v226) = 12;
        v163 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v162, &v226);
        v164 = std::basic_ostream<unsigned short>::operator<<(v163, v148);
        *(_DWORD *)(*(int *)(*(_QWORD *)v164 + 4LL) + v164 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v164 + 4LL) + v164 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v164 + 4LL) + v164 + 40) = 0;
        v165 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v164, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 40) = 3;
        if ( v148 < 0 )
          v166 = (double)(int)(v148 & 1 | ((unsigned __int64)v148 >> 1))
               + (double)(int)(v148 & 1 | ((unsigned __int64)v148 >> 1));
        else
          v166 = (double)(int)v148;
        v167 = v166 * 100.0;
        v168 = *((_QWORD *)this + 87);
        if ( v168 < 0 )
        {
          v170 = *((_QWORD *)this + 87) & 1LL | ((unsigned __int64)v168 >> 1);
          v169 = (double)(int)v170 + (double)(int)v170;
        }
        else
        {
          v169 = (double)(int)v168;
        }
        v171 = std::basic_ostream<unsigned short>::operator<<(v165, v167 / v169);
        *(_DWORD *)(*(int *)(*(_QWORD *)v171 + 4LL) + v171 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v171 + 4LL) + v171 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v171 + 4LL) + v171 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v171, "% of min \n", v172);
        v173 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +     median-lq : ");
        LODWORD(v226) = 12;
        v174 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v173, &v226);
        v175 = std::basic_ostream<unsigned short>::operator<<(v174, v149);
        *(_DWORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 40) = 0;
        v176 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v175, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 40) = 3;
        if ( v149 < 0 )
          v177 = (double)(int)(v149 & 1 | ((unsigned __int64)v149 >> 1))
               + (double)(int)(v149 & 1 | ((unsigned __int64)v149 >> 1));
        else
          v177 = (double)(int)v149;
        v178 = v177 * 100.0;
        v179 = *((_QWORD *)this + 91);
        if ( v179 < 0 )
        {
          v181 = *((_QWORD *)this + 91) & 1LL | ((unsigned __int64)v179 >> 1);
          v180 = (double)(int)v181 + (double)(int)v181;
        }
        else
        {
          v180 = (double)(int)v179;
        }
        v182 = std::basic_ostream<unsigned short>::operator<<(v176, v178 / v180);
        *(_DWORD *)(*(int *)(*(_QWORD *)v182 + 4LL) + v182 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v182 + 4LL) + v182 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v182 + 4LL) + v182 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v182, "% of lq \n", v183);
        v184 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +         Limit : ");
        LODWORD(v226) = 12;
        v185 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v184, &v226);
        v186 = std::basic_ostream<unsigned short>::operator<<(v185, v150);
        v187 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v186, " ");
        *(_DWORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 24) |= 0x2090u;
        *(_QWORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 32) = 2;
        *(_QWORD *)(*(int *)(*(_QWORD *)v187 + 4LL) + v187 + 40) = 3;
        if ( (v150 & 0x8000000000000000uLL) != 0LL )
          v188 = (double)(int)(v150 & 1 | (v150 >> 1)) + (double)(int)(v150 & 1 | (v150 >> 1));
        else
          v188 = (double)(int)v150;
        v189 = v188 * 100.0;
        v190 = *((_QWORD *)this + 87);
        if ( v190 < 0 )
        {
          v192 = *((_QWORD *)this + 87) & 1LL | ((unsigned __int64)v190 >> 1);
          v191 = (double)(int)v192 + (double)(int)v192;
        }
        else
        {
          v191 = (double)(int)v190;
        }
        v193 = std::basic_ostream<unsigned short>::operator<<(v187, v189 / v191);
        *(_DWORD *)(*(int *)(*(_QWORD *)v193 + 4LL) + v193 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v193 + 4LL) + v193 + 88) = 32;
        v194 = *(int *)(*(_QWORD *)v193 + 4LL);
        *(_QWORD *)(v194 + v193 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v193, "% of min \n", v194);
        v195 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +           Sum : ");
        LODWORD(v226) = 12;
        v196 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v195, &v226);
        v197 = std::basic_ostream<unsigned short>::operator<<(v196, *((_QWORD *)this + 84));
        *(_DWORD *)(*(int *)(*(_QWORD *)v197 + 4LL) + v197 + 24) |= 0x201u;
        *(_WORD *)(*(int *)(*(_QWORD *)v197 + 4LL) + v197 + 88) = 32;
        *(_QWORD *)(*(int *)(*(_QWORD *)v197 + 4LL) + v197 + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v197, "\n");
        v198 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                 (__int64 *)(*((_QWORD *)this + 1) + 240LL),
                 (__int64)L"                       +        Status : ");
        LODWORD(v226) = 12;
        v199 = (__int64 *)mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v198, &v226);
        v200 = L"GOOD";
        if ( !*((_BYTE *)this + 752) )
          v200 = L"BAD";
        v201 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v199, (__int64)v200);
        *(_DWORD *)((char *)v201 + *(int *)(*v201 + 4) + 24) |= 0x201u;
        *(_WORD *)((char *)v201 + *(int *)(*v201 + 4) + 88) = 32;
        *(__int64 *)((char *)v201 + *(int *)(*v201 + 4) + 40) = 0;
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v201, "\n");
        std::endl(*((_QWORD *)this + 1) + 240LL);
        LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      }
    }
  }
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  if ( **((int **)this + 4) > 0 )
  {
    v202 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v225, 509);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v227,
      (__int64)v202);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v226,
      1024);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      &v226,
      *(_QWORD *)(v227 + 24),
      *((unsigned int *)this + 22));
    v203 = (_DWORD *)((char *)this + 96);
    WinSAT::OpStatus::SetResult((char *)this + 96, 5, *(_QWORD *)(v226 + 24), 0);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v226);
    v204 = &v227;
    goto LABEL_139;
  }
  if ( *((_BYTE *)this + 808) )
  {
    v205 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v225, 549);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v226,
      (__int64)v205);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
      &v226,
      v206,
      10);
    v207 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
    mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
      v207,
      *(_QWORD *)(v226 + 24),
      *((unsigned int *)this + 22));
    v203 = (_DWORD *)((char *)this + 96);
    *((_DWORD *)this + 24) = 6;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)this + 104);
    *((_BYTE *)this + 112) = 0;
    v204 = &v226;
LABEL_139:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v204);
  }
  else
  {
    v203 = (_DWORD *)((char *)this + 96);
    *((_DWORD *)this + 24) = 6;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)this + 104);
    *((_BYTE *)this + 112) = 0;
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  v208 = *v203 != 6 ? 0xD : 0;
  SetLastError(v208);
  return v208;
}

```

## disassembly

```asm
0x140074490  mov     rax, rsp
0x140074493  push    rbp
0x140074494  push    rbx
0x140074495  push    rsi
0x140074496  push    rdi
0x140074497  push    r12
0x140074499  push    r13
0x14007449b  push    r14
0x14007449d  push    r15
0x14007449f  lea     rbp, [rax-58h]
0x1400744a3  sub     rsp, 118h
0x1400744aa  movaps  xmmword ptr [rax-58h], xmm6
0x1400744ae  movaps  xmmword ptr [rax-68h], xmm7
0x1400744b2  movaps  xmmword ptr [rax-78h], xmm8
0x1400744b7  movaps  xmmword ptr [rax-88h], xmm9
0x1400744bf  mov     rbx, rcx
0x1400744c2  xor     r15d, r15d
0x1400744c5  mov     rax, [rcx+350h]
0x1400744cc  mov     ecx, [rax+20ACh]
0x1400744d2  mov     dword ptr [rsp+150h+var_EC], ecx
0x1400744d6  mov     r13d, [rax+20B0h]
0x1400744dd  mov     eax, [rax+20B4h]
0x1400744e3  mov     [rsp+150h+var_F4], eax
0x1400744e7  mov     [rsp+150h+var_110], r15d
0x1400744ec  call    cs:__imp_GetTickCount
0x1400744f2  mov     rdx, [rbx+350h]
0x1400744f9  movsd   xmm0, qword ptr [rdx+2098h]
0x140074501  movsd   xmm8, cs:__real@408f400000000000
0x14007450a  mulsd   xmm0, xmm8
0x14007450f  cvttsd2si rcx, xmm0
0x140074514  add     ecx, eax
0x140074516  mov     [rbp+50h+var_B8], rcx
0x14007451a  movsd   xmm0, qword ptr [rdx+20A0h]
0x140074522  mulsd   xmm0, xmm8
0x140074527  cvttsd2si rcx, xmm0
0x14007452c  add     ecx, eax
0x14007452e  mov     [rbp+50h+var_B0], rcx
0x140074532  mov     dil, [rdx+20A8h]
0x140074539  mov     byte ptr [rbp+50h+arg_8], dil
0x14007453d  xor     r14d, r14d
0x140074540  mov     byte ptr [rbp+50h+arg_0], r14b
0x140074544  xor     esi, esi
0x140074546  or      ecx, 0FFFFFFFFh
0x140074549  mov     [rsp+150h+var_FC], ecx
0x14007454d  xor     r8d, r8d
0x140074550  mov     [rsp+150h+var_F8], r8d
0x140074555  xor     ecx, ecx; this
0x140074557  mov     [rsp+150h+var_100], ecx
0x14007455b  mov     al, [rdx+20BAh]
0x140074561  mov     [rbp+50h+arg_10], al
0x140074564  call    ?QueryPerformanceCounter64@mlib@@YA_KXZ; mlib::QueryPerformanceCounter64(void)
0x140074569  mov     r12, rax
0x14007456c  rdtsc
0x14007456e  shl     rdx, 20h
0x140074572  or      rax, rdx
0x140074575  mov     [rbx+318h], rax
0x14007457c  jmp     short loc_140074582
0x14007457e  mov     dil, byte ptr [rbp+50h+arg_8]
0x140074582  mov     rcx, rbx; this
0x140074585  call    ?ExitLoop@MPWorkload@WinSAT@@IEBA_NXZ; WinSAT::MPWorkload::ExitLoop(void)
0x14007458a  test    al, al
0x14007458c  jnz     loc_140074A4A
0x140074592  test    dil, dil
0x140074595  jnz     loc_140074A4A
0x14007459b  lea     rdi, [rbx+288h]
0x1400745a2  mov     rcx, [rdi+10h]
0x1400745a6  sub     rcx, [rdi]
0x1400745a9  sar     rcx, 3
0x1400745ad  cmp     rcx, [rdi+70h]
0x1400745b1  jnb     short loc_1400745D2
0x1400745b3  mov     rax, [rbx+290h]
0x1400745ba  sub     rax, [rdi]
0x1400745bd  sar     rax, 3
0x1400745c1  cmp     rax, rcx
0x1400745c4  jb      short loc_1400745D2
0x1400745c6  mov     edx, dword ptr [rsp+150h+var_EC]; unsigned __int64
0x1400745ca  mov     rcx, rdi; this
0x1400745cd  call    ?GrowSizeBy@SampleManager@@QEAAX_K@Z; SampleManager::GrowSizeBy(unsigned __int64)
0x1400745d2  mov     rcx, rbx; this
0x1400745d5  call    ?Rendevous@MPWorkload@WinSAT@@IEBA_NXZ; WinSAT::MPWorkload::Rendevous(void)
0x1400745da  test    al, al
0x1400745dc  jz      loc_140074A4A
0x1400745e2  call    cs:__imp_GetTickCount
0x1400745e8  mov     dword ptr [rsp+150h+var_EC+4], eax
0x1400745ec  xor     eax, eax
0x1400745ee  mov     [rsp+150h+var_110+4], eax
0x1400745f2  cmp     eax, r13d
0x1400745f5  jnb     loc_140074959
0x1400745fb  mov     ecx, [rbx+3D0h]
0x140074601  mov     [rsp+150h+var_110], ecx
0x140074605  mov     rcx, [rbx+20h]
0x140074609  mov     edx, [rcx]
0x14007460b  test    edx, edx
0x14007460d  jnz     loc_140074959
0x140074613  mov     rax, [rbx+40h]
0x140074617  mov     ecx, [rax]
0x140074619  test    ecx, ecx
0x14007461b  jnz     loc_140074959
0x140074621  lea     rcx, [rbx+358h]; this
0x140074628  call    ?RotateBuffer@RotatingBuffer@@QEAAPEAEXZ; RotatingBuffer::RotateBuffer(void)
0x14007462d  mov     [rbx+3D8h], rax
0x140074634  test    rax, rax
0x140074637  jz      loc_140074A35
0x14007463d  lea     rcx, [rbx+388h]; this
0x140074644  call    ?RotateBuffer@RotatingBuffer@@QEAAPEAEXZ; RotatingBuffer::RotateBuffer(void)
0x140074649  mov     [rbx+3E0h], rax
0x140074650  test    rax, rax
0x140074653  jz      loc_140074A35
0x140074659  mov     dword ptr [rsp+150h+phHash], 0
0x140074661  mov     [rsp+150h+var_F0], 0
0x140074669  mov     r8d, [rbx+3D0h]; Size
0x140074670  mov     rdx, [rbx+3D8h]; Src
0x140074677  mov     rcx, rax; void *
0x14007467a  call    memcpy_0
0x14007467f  mov     ecx, [rbx+3B8h]
0x140074685  cmp     ecx, 2
0x140074688  jnz     short loc_1400746C3
0x14007468a  mov     eax, [rbx+3F0h]
0x140074690  mov     [rsp+150h+var_110], eax
0x140074694  rdtsc
0x140074696  shl     rdx, 20h
0x14007469a  or      rax, rdx
0x14007469d  mov     [rbp+50h+var_C8], rax
0x1400746a1  mov     edx, [rbx+3F0h]
0x1400746a7  mov     rcx, [rbx+3E0h]
0x1400746ae  call    XpressCrc32
0x1400746b3  mov     r8d, 1
0x1400746b9  mov     dword ptr [rsp+150h+phHash], r8d
0x1400746be  jmp     loc_1400747BC
0x1400746c3  rdtsc
0x1400746c5  shl     rdx, 20h
0x1400746c9  or      rax, rdx
0x1400746cc  mov     [rbp+50h+var_C8], rax
0x1400746d0  test    ecx, ecx
0x1400746d2  jnz     short loc_140074748
0x1400746d4  mov     ecx, [rbx+3F0h]
0x1400746da  mov     [rsp+150h+dwBufLen], ecx; dwBufLen
0x1400746de  lea     rax, [rsp+150h+var_110]
0x1400746e3  mov     [rsp+150h+pdwDataLen], rax; pdwDataLen
0x1400746e8  mov     rcx, [rbx+3E0h]
0x1400746ef  mov     [rsp+150h+pbData], rcx; pbData
0x1400746f4  xor     r9d, r9d; dwFlags
0x1400746f7  xor     edx, edx; hHash
0x1400746f9  lea     r8d, [r9+1]; Final
0x1400746fd  mov     rcx, [rbx+3C8h]; hKey
0x140074704  call    cs:__imp_CryptEncrypt
0x14007470a  mov     dword ptr [rbp+50h+arg_18], eax
0x14007470d  test    eax, eax
0x14007470f  jz      short loc_140074743
0x140074711  lea     rax, [rsp+150h+var_110]
0x140074716  mov     [rsp+150h+pdwDataLen], rax; pdwDataLen
0x14007471b  mov     rcx, [rbx+3E0h]
0x140074722  mov     [rsp+150h+pbData], rcx; pbData
0x140074727  xor     r9d, r9d; dwFlags
0x14007472a  xor     edx, edx; hHash
0x14007472c  lea     r8d, [r9+1]; Final
0x140074730  mov     rcx, [rbx+3C8h]; hKey
0x140074737  call    cs:__imp_CryptDecrypt
0x14007473d  mov     dword ptr [rsp+150h+phHash], eax
0x140074741  jmp     short loc_1400747B8
0x140074743  mov     r8d, eax
0x140074746  jmp     short loc_1400747BC
0x140074748  cmp     ecx, 1
0x14007474b  jnz     short loc_1400747B1
0x14007474d  mov     [rsp+150h+phHash], 0
0x140074756  lea     rax, [rsp+150h+phHash]
0x14007475b  mov     [rsp+150h+pbData], rax; phHash
0x140074760  xor     r9d, r9d; dwFlags
0x140074763  xor     r8d, r8d; hKey
0x140074766  mov     edx, 8004h; Algid
0x14007476b  mov     rcx, [rbx+3C0h]; hProv
0x140074772  call    cs:__imp_CryptCreateHash
0x140074778  xor     r9d, r9d; dwFlags
0x14007477b  mov     r8d, [rbx+3F0h]; dwDataLen
0x140074782  mov     rdx, [rbx+3E0h]; pbData
0x140074789  mov     rcx, [rsp+150h+phHash]; hHash
0x14007478e  call    cs:__imp_CryptHashData
0x140074794  mov     dword ptr [rbp+50h+arg_18], eax
0x140074797  mov     rcx, [rsp+150h+phHash]; hHash
0x14007479c  test    rcx, rcx
0x14007479f  jz      short loc_1400747A7
0x1400747a1  call    cs:__imp_CryptDestroyHash
0x1400747a7  mov     dword ptr [rsp+150h+phHash], 1
0x1400747af  jmp     short loc_1400747B8
0x1400747b1  mov     dword ptr [rbp+50h+arg_18], 0
0x1400747b8  mov     r8d, dword ptr [rbp+50h+arg_18]
0x1400747bc  rdtsc
0x1400747be  shl     rdx, 20h
0x1400747c2  or      rax, rdx
0x1400747c5  mov     [rbp+50h+arg_18], rax
0x1400747c9  mov     ecx, [rsp+150h+var_110]
0x1400747cd  add     r14, rcx
0x1400747d0  test    r8d, r8d
0x1400747d3  jnz     loc_140074870
0x1400747d9  mov     rcx, [rbx+50h]; lpCriticalSection
0x1400747dd  call    cs:__imp_EnterCriticalSection
0x1400747e3  mov     edx, 217h; unsigned __int16
0x1400747e8  lea     rcx, [rbp+50h+var_A8]; this
0x1400747ec  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x1400747f1  mov     rdx, rax
0x1400747f4  lea     rcx, [rbp+50h+var_D0]
0x1400747f8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x1400747fd  nop
0x1400747fe  mov     edx, 400h
0x140074803  lea     rcx, [rsp+150h+var_E0]
0x140074808  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x14007480d  nop
0x14007480e  mov     r9d, [rbx+58h]
0x140074812  mov     r8d, [rsp+150h+var_110+4]
0x140074817  mov     rdx, [rbp+50h+var_D0]
0x14007481b  mov     rdx, [rdx+18h]
0x14007481f  lea     rcx, [rsp+150h+var_E0]
0x140074824  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140074829  mov     rcx, [rbx+10h]
0x14007482d  add     rcx, 0F0h
0x140074834  lea     rdx, [rsp+150h+var_E0]
0x140074839  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007483e  mov     rcx, rax
0x140074841  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140074846  mov     rcx, [rbx+50h]; lpCriticalSection
0x14007484a  call    cs:__imp_LeaveCriticalSection
0x140074850  mov     [rsp+150h+var_F0], 1
0x140074858  lea     rcx, [rsp+150h+var_E0]
0x14007485d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140074862  nop
0x140074863  lea     rcx, [rbp+50h+var_D0]
0x140074867  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14007486c  mov     rax, [rbp+50h+arg_18]
0x140074870  cmp     dword ptr [rsp+150h+phHash], 0
0x140074875  jz      short loc_1400748C6
0x140074877  cmp     [rsp+150h+var_F0], 0
0x14007487c  jnz     loc_140074952
0x140074882  cmp     byte ptr [rbp+50h+arg_0], 0
0x140074886  jnz     short loc_14007489F
0x140074888  sub     rax, [rbp+50h+var_C8]
0x14007488c  mov     [rbp+50h+arg_18], rax
0x140074890  mov     rdx, rax; unsigned __int64
0x140074893  mov     rcx, rdi; this
0x140074896  call    ?AddSample@SampleManager@@QEAAX_K@Z; SampleManager::AddSample(unsigned __int64)
0x14007489b  add     r15, [rbp+50h+arg_18]
0x14007489f  mov     rax, [rbx+20h]
0x1400748a3  mov     ecx, [rax]
0x1400748a5  test    ecx, ecx
0x1400748a7  jnz     loc_140074959
0x1400748ad  mov     rax, [rbx+40h]
0x1400748b1  mov     ecx, [rax]
0x1400748b3  test    ecx, ecx
0x1400748b5  jnz     loc_140074959
0x1400748bb  mov     eax, [rsp+150h+var_110+4]
0x1400748bf  inc     eax
0x1400748c1  jmp     loc_1400745EE
0x1400748c6  mov     rcx, [rbx+50h]; lpCriticalSection
0x1400748ca  call    cs:__imp_EnterCriticalSection
0x1400748d0  mov     edx, 218h; unsigned __int16
0x1400748d5  lea     rcx, [rbp+50h+var_A8]; this
0x1400748d9  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x1400748de  mov     rdx, rax
0x1400748e1  lea     rcx, [rbp+50h+var_C0]
0x1400748e5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x1400748ea  nop
0x1400748eb  mov     edx, 400h
0x1400748f0  lea     rcx, [rsp+150h+var_D8]
0x1400748f5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x1400748fa  nop
0x1400748fb  mov     r9d, [rbx+58h]
0x1400748ff  mov     r8d, [rsp+150h+var_110+4]
0x140074904  mov     rdx, [rbp+50h+var_C0]
0x140074908  mov     rdx, [rdx+18h]
0x14007490c  lea     rcx, [rsp+150h+var_D8]
0x140074911  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x140074916  mov     rcx, [rbx+10h]
0x14007491a  add     rcx, 0F0h
0x140074921  lea     rdx, [rsp+150h+var_D8]
0x140074926  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14007492b  mov     rcx, rax
0x14007492e  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140074933  mov     rcx, [rbx+50h]; lpCriticalSection
0x140074937  call    cs:__imp_LeaveCriticalSection
0x14007493d  nop
0x14007493e  lea     rcx, [rsp+150h+var_D8]
0x140074943  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140074948  nop
0x140074949  lea     rcx, [rbp+50h+var_C0]
0x14007494d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140074952  mov     rax, [rbx+20h]
0x140074956  lock inc dword ptr [rax]
0x140074959  mov     rax, [rbx+20h]
0x14007495d  mov     ecx, [rax]
0x14007495f  test    ecx, ecx
0x140074961  jnz     loc_140074A4A
0x140074967  mov     rax, [rbx+40h]
0x14007496b  mov     ecx, [rax]
0x14007496d  test    ecx, ecx
0x14007496f  jnz     loc_140074A4A
0x140074975  cmp     [rbp+50h+arg_10], cl
0x140074978  jnz     short loc_14007498D
0x14007497a  mov     rcx, [rbx+350h]
0x140074981  mov     ecx, [rcx+208Ch]; dwMilliseconds
0x140074987  call    cs:__imp_Sleep
0x14007498d  inc     [rsp+150h+var_100]
  ... truncated ...
```
