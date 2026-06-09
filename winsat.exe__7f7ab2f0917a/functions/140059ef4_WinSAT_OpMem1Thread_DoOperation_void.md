# WinSAT::OpMem1Thread::DoOperation(void)

- ea: `0x140059ef4`
- end: `0x14005c142`
- name: `?DoOperation@OpMem1Thread@WinSAT@@QEAAKXZ`
- size: `8782`
- prototype: `unsigned int __fastcall(WinSAT::OpMem1Thread *__hidden this)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14005c150`

## callees

- `0x140003560`
- `0x1400040d0`
- `0x140004170`
- `0x140004348`
- `0x14000449c`
- `0x140007f14`
- `0x140008178`
- `0x1400083a4`
- `0x1400085b4`
- `0x14000a8d8`
- `0x140011f58`
- `0x140016588`
- `0x140016954`
- `0x140017af0`
- `0x14001827c`
- `0x14002093c`
- `0x1400219d0`
- `0x14003ec14`
- `0x14004fce4`
- `0x1400530a8`
- `0x140058488`
- `0x1400584b0`
- `0x140058818`
- `0x140059010`
- `0x140059158`
- `0x140059ef4`
- `0x14005c9b4`
- `0x14005cb00`
- `0x14005cc74`
- `0x14005ed80`
- `0x14005eecc`
- `0x14005ef98`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14005a606`
- `KERNEL32!GetTickCount` at `0x14005a701`
- `KERNEL32!GetTickCount` at `0x14005a8aa`
- `KERNEL32!GetTickCount` at `0x14005a924`
- `KERNEL32!GetTickCount` at `0x14005a954`
- `KERNEL32!GetTickCount` at `0x14005a606`
- `KERNEL32!GetTickCount` at `0x14005a701`
- `KERNEL32!GetTickCount` at `0x14005a8aa`
- `KERNEL32!GetTickCount` at `0x14005a924`
- `KERNEL32!GetTickCount` at `0x14005a954`
- `KERNEL32!EnterCriticalSection` at `0x140059fc7`
- `KERNEL32!EnterCriticalSection` at `0x14005a2a7`
- `KERNEL32!EnterCriticalSection` at `0x14005acea`
- `KERNEL32!EnterCriticalSection` at `0x14005c00c`
- `KERNEL32!EnterCriticalSection` at `0x140059fc7`
- `KERNEL32!EnterCriticalSection` at `0x14005a2a7`
- `KERNEL32!EnterCriticalSection` at `0x14005acea`
- `KERNEL32!EnterCriticalSection` at `0x14005c00c`
- `KERNEL32!LeaveCriticalSection` at `0x14005a00c`
- `KERNEL32!LeaveCriticalSection` at `0x14005a4bb`
- `KERNEL32!LeaveCriticalSection` at `0x14005bf6f`
- `KERNEL32!LeaveCriticalSection` at `0x14005a00c`
- `KERNEL32!LeaveCriticalSection` at `0x14005a4bb`
- `KERNEL32!LeaveCriticalSection` at `0x14005bf6f`
- `KERNEL32!GetCurrentThreadId` at `0x14005a2f7`
- `KERNEL32!GetCurrentThreadId` at `0x14005a2f7`
- `KERNEL32!GetThreadPriority` at `0x14005a050`
- `KERNEL32!GetThreadPriority` at `0x14005a050`
- `KERNEL32!GetCurrentThread` at `0x140059f50`
- `KERNEL32!GetCurrentThread` at `0x14005a047`
- `KERNEL32!GetCurrentThread` at `0x140059f50`
- `KERNEL32!GetCurrentThread` at `0x14005a047`
- `KERNEL32!GetLastError` at `0x140059f7d`
- `KERNEL32!GetLastError` at `0x14005a0ed`
- `KERNEL32!GetLastError` at `0x14005a150`
- `KERNEL32!GetLastError` at `0x14005a1c8`
- `KERNEL32!GetLastError` at `0x14005bfc1`
- `KERNEL32!GetLastError` at `0x140059f7d`
- `KERNEL32!GetLastError` at `0x14005a0ed`
- `KERNEL32!GetLastError` at `0x14005a150`
- `KERNEL32!GetLastError` at `0x14005a1c8`
- `KERNEL32!GetLastError` at `0x14005bfc1`
- `KERNEL32!Sleep` at `0x14005a078`
- `KERNEL32!Sleep` at `0x14005a8a0`
- `KERNEL32!Sleep` at `0x14005a078`
- `KERNEL32!Sleep` at `0x14005a8a0`
- `KERNEL32!VirtualLock` at `0x14005a138`
- `KERNEL32!VirtualLock` at `0x14005a1b0`
- `KERNEL32!VirtualLock` at `0x14005a138`
- `KERNEL32!VirtualLock` at `0x14005a1b0`
- `KERNEL32!VirtualAlloc` at `0x14005a0d1`
- `KERNEL32!VirtualAlloc` at `0x14005a0d1`
- `KERNEL32!VirtualFree` at `0x14005a185`
- `KERNEL32!VirtualFree` at `0x14005a1fd`
- `KERNEL32!VirtualFree` at `0x14005bfb7`
- `KERNEL32!VirtualFree` at `0x14005a185`
- `KERNEL32!VirtualFree` at `0x14005a1fd`
- `KERNEL32!VirtualFree` at `0x14005bfb7`
- `KERNEL32!SetThreadPriority` at `0x140059f5d`
- `KERNEL32!SetThreadPriority` at `0x140059f5d`
- `KERNEL32!SetLastError` at `0x14005a035`
- `KERNEL32!SetLastError` at `0x14005bfa6`
- `KERNEL32!SetLastError` at `0x14005c0f8`
- `KERNEL32!SetLastError` at `0x14005a035`
- `KERNEL32!SetLastError` at `0x14005bfa6`
- `KERNEL32!SetLastError` at `0x14005c0f8`

## string_xrefs

- `0x14005a477`: `  -- Copy Routine = `
- `0x14005a059`: `Adjusted the priority of the Memory copy thread to %d`
- `0x14005ada2`: `  --          cummulative copy seconds : `
- `0x14005af3c`: `  --                 buffer copy count : `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinSAT::OpMem1Thread::DoOperation(WinSAT::OpMem1Thread *this)
{
  HANDLE CurrentThread; // rax
  int v3; // r8d
  __int64 v4; // rdx
  const unsigned __int16 *v5; // rbx
  __int64 *v6; // rcx
  __int64 *v7; // rax
  __int64 *v8; // rax
  __int64 *v9; // rax
  HANDLE v11; // rax
  int ThreadPriority; // eax
  int v13; // r9d
  char *v14; // rax
  char *v15; // r15
  SIZE_T v16; // rbx
  __int64 v17; // r14
  BOOL v18; // eax
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // rax
  __int64 *v22; // rax
  __int64 *v23; // rax
  __int64 *v24; // rax
  __int64 v25; // rbx
  DWORD CurrentThreadId; // eax
  __int64 *v27; // rax
  __int64 *v28; // rax
  __int64 *v29; // rax
  const wchar_t *v30; // rdx
  __int64 *v31; // rax
  __int64 *v32; // rax
  __int64 *v33; // rax
  __int64 *v34; // rax
  __int64 *v35; // rax
  __int64 v36; // rax
  __int64 *v37; // rax
  unsigned __int64 v38; // r12
  __int64 *v39; // rax
  __int64 *v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 *v43; // rax
  __int64 *v44; // rax
  __int64 *v45; // rax
  __int64 v46; // rbx
  __int64 v47; // rdx
  int v48; // ebx
  __int64 v49; // rbx
  __int64 v50; // rdx
  __int64 v51; // rcx
  DWORD TickCount; // eax
  __int64 v53; // rcx
  __int64 v54; // r8
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // rax
  unsigned __int64 v57; // rbx
  unsigned int v58; // eax
  unsigned int v59; // r9d
  unsigned int v60; // r8d
  mlib *v61; // rcx
  __int64 v62; // rbx
  mlib *v63; // rcx
  __int64 PerformanceFrequency64; // rax
  double v65; // xmm1_8
  __int64 v66; // rdx
  double v67; // xmm0_8
  double v68; // xmm0_8
  __int64 v69; // rbx
  double v70; // xmm6_8
  double v71; // xmm6_8
  __int64 v72; // rcx
  double v73; // xmm4_8
  __int64 v74; // rdx
  __int64 v75; // rcx
  double v76; // xmm7_8
  double v77; // xmm7_8
  __int64 v78; // r12
  double v79; // xmm0_8
  double v80; // xmm7_8
  double v81; // xmm6_8
  SIZE_T v82; // rbx
  double v83; // xmm5_8
  double v84; // xmm5_8
  __int64 v85; // rcx
  __int64 v86; // rdx
  double v87; // xmm2_8
  double v88; // xmm3_8
  double v89; // xmm3_8
  __int64 v90; // rcx
  double v91; // xmm8_8
  double v92; // xmm8_8
  double v93; // xmm2_8
  __int64 v94; // rcx
  double v95; // xmm1_8
  __int64 v96; // rcx
  double v97; // xmm1_8
  __int64 v98; // rcx
  double v99; // xmm0_8
  __int64 *v100; // rax
  __int64 *v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 *v104; // rax
  __int64 *v105; // rax
  __int64 *v106; // rax
  __int64 *v107; // rax
  __int64 *v108; // rax
  __int64 v109; // rax
  __int64 *v110; // rax
  __int64 v111; // rax
  __int64 *v112; // rax
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
  __int64 v128; // rax
  __int64 *v129; // rax
  __int64 v130; // rax
  __int64 *v131; // rax
  const wchar_t *v132; // rdx
  __int64 *v133; // rax
  __int64 *v134; // rax
  __int64 *v135; // rax
  __int64 *v136; // rax
  __int64 *v137; // rax
  __int64 *v138; // rax
  __int64 *v139; // rax
  __int64 *v140; // rax
  __int64 *v141; // rax
  __int64 *v142; // rax
  __int64 v143; // rax
  __int64 v144; // rax
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
  __int64 v169; // rcx
  __int64 v170; // r8
  __int64 v171; // rax
  unsigned __int64 v172; // r12
  __int64 *v173; // rax
  __int64 v174; // rax
  __int64 v175; // rax
  __int64 v176; // r8
  double v177; // xmm1_8
  double v178; // xmm1_8
  __int64 v179; // rcx
  double v180; // xmm0_8
  __int64 v181; // rax
  int v182; // r8d
  __int64 *v183; // rax
  __int64 v184; // rax
  __int64 v185; // rax
  __int64 v186; // r8
  double v187; // xmm1_8
  double v188; // xmm1_8
  __int64 v189; // rcx
  double v190; // xmm0_8
  __int64 v191; // rax
  int v192; // r8d
  __int64 *v193; // rax
  __int64 v194; // rax
  __int64 v195; // rax
  __int64 v196; // r8
  double v197; // xmm1_8
  double v198; // xmm1_8
  __int64 v199; // rcx
  double v200; // xmm0_8
  __int64 v201; // rax
  int v202; // r8d
  __int64 *v203; // rax
  __int64 v204; // rax
  __int64 v205; // rax
  __int64 v206; // r8
  double v207; // xmm1_8
  double v208; // xmm1_8
  __int64 v209; // rcx
  double v210; // xmm0_8
  __int64 v211; // rax
  __int64 v212; // r8
  __int64 *v213; // rax
  __int64 v214; // rax
  __int64 v215; // rax
  __int64 *v216; // rax
  __int64 *v217; // rax
  const wchar_t *v218; // rdx
  __int64 *v219; // rax
  bool v220; // bl
  int v221; // r8d
  __int64 v222; // rdx
  _DWORD *v223; // rbx
  const unsigned __int16 *v224; // rax
  __int64 *v225; // rbx
  const unsigned __int16 *v226; // rax
  __int64 *v227; // rax
  DWORD v228; // ebx
  __int64 v229; // rdi
  const unsigned __int16 *v230; // rbx
  __int64 *v231; // rax
  __int64 *v232; // rax
  __int64 *v233; // rax
  __int64 v234; // [rsp+20h] [rbp-308h]
  DWORD v235; // [rsp+30h] [rbp-2F8h] BYREF
  bool v236; // [rsp+34h] [rbp-2F4h]
  char v237; // [rsp+35h] [rbp-2F3h]
  char v238; // [rsp+36h] [rbp-2F2h]
  int v239; // [rsp+38h] [rbp-2F0h]
  unsigned int v240; // [rsp+3Ch] [rbp-2ECh] BYREF
  char v241; // [rsp+40h] [rbp-2E8h]
  unsigned int v242; // [rsp+44h] [rbp-2E4h]
  unsigned __int64 v243; // [rsp+48h] [rbp-2E0h]
  SIZE_T v244; // [rsp+50h] [rbp-2D8h]
  int v245; // [rsp+58h] [rbp-2D0h]
  unsigned int v246; // [rsp+5Ch] [rbp-2CCh]
  unsigned int v247; // [rsp+60h] [rbp-2C8h]
  __int64 v248; // [rsp+68h] [rbp-2C0h] BYREF
  __int64 v249; // [rsp+70h] [rbp-2B8h] BYREF
  unsigned int v250; // [rsp+78h] [rbp-2B0h]
  void *v251; // [rsp+80h] [rbp-2A8h]
  void (__fastcall *v252)(char *, void *, _QWORD); // [rsp+88h] [rbp-2A0h] BYREF
  __int64 PerformanceCounter64; // [rsp+90h] [rbp-298h]
  unsigned __int64 v254; // [rsp+98h] [rbp-290h]
  __int64 v255; // [rsp+A0h] [rbp-288h]
  __int64 v256; // [rsp+A8h] [rbp-280h]
  WCHAR Buffer[256]; // [rsp+B0h] [rbp-278h] BYREF
  DWORD dwErrCode; // [rsp+2B0h] [rbp-78h]
  char v259; // [rsp+2B4h] [rbp-74h]
  __int64 v260; // [rsp+2B8h] [rbp-70h]

  PerformanceCounter64 = (__int64)this;
  if ( !*(_BYTE *)(*((_QWORD *)this + 18) + 737LL) )
  {
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, 15) )
    {
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 18) + 772LL), 1u);
      dwErrCode = GetLastError();
      v259 = 1;
      v260 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v3 = 624;
      v4 = 600;
LABEL_4:
      v5 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)v4, v3, *(_DWORD *)this);
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
      v6 = (__int64 *)(*((_QWORD *)this + 17) + 240LL);
LABEL_5:
      v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v6, (__int64)v5);
      v8 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v7, 10);
      v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, (__int64)Buffer);
      std::endl(v9);
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
      WinSAT::OpStatus::SetResult((char *)this + 400, 5, v5, Buffer);
      SetLastError(dwErrCode);
      return dwErrCode;
    }
    v11 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v11);
    Log_Text_F(
      "base\\winsat\\memory\\memat.cpp",
      610,
      "Adjusted the priority of the Memory copy thread to %d",
      ThreadPriority);
  }
  Sleep(1u);
  try
  {
    SampleManager::ClearAndReserve((WinSAT::OpMem1Thread *)((char *)this + 152), 0x4000u);
  }
  catch ( ... )
  {
    v229 = PerformanceCounter64;
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(PerformanceCounter64 + 144) + 772LL));
    dwErrCode = 8;
    v259 = 1;
    v260 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v230 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x279, 625, *(_DWORD *)v229);
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(v229 + 120));
    v231 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*(_QWORD *)(v229 + 136) + 240LL),
             (__int64)v230);
    v232 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v231, 10);
    v233 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v232, (__int64)Buffer);
    std::endl(v233);
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v229 + 120));
    WinSAT::OpStatus::SetResult(v229 + 400, 5, v230, Buffer);
    SetLastError(dwErrCode);
    return dwErrCode;
  }
  v244 = *((_QWORD *)this + 2) + 2LL * *((_QWORD *)this + 1);
  v13 = *(_BYTE *)(*((_QWORD *)this + 18) + 736LL) != 0 ? 0x200 : 0;
  v239 = 4;
  v14 = (char *)VirtualAlloc(0, v244, 0x1000u, v13 + 4);
  v15 = v14;
  if ( !v14 )
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 18) + 772LL), 1u);
    dwErrCode = GetLastError();
    v259 = 1;
    v260 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v3 = 626;
    v4 = 668;
    goto LABEL_4;
  }
  *((_QWORD *)this + 3) = v14;
  v16 = *((_QWORD *)this + 1);
  v17 = *((_QWORD *)this + 2);
  if ( !VirtualLock(v14, v16) )
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 18) + 772LL), 1u);
    dwErrCode = GetLastError();
    v259 = 1;
    v260 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    VirtualFree(v15, 0, 0x8000u);
    v3 = 627;
    v4 = 702;
    goto LABEL_4;
  }
  v251 = &v15[v17 + v16];
  v18 = VirtualLock(v251, *((_QWORD *)this + 1));
  v19 = *((_QWORD *)this + 18);
  if ( !v18 )
  {
    _InterlockedAdd((volatile signed __int32 *)(v19 + 772), 1u);
    dwErrCode = GetLastError();
    v259 = 1;
    v260 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    VirtualFree(v15, 0, 0x8000u);
    v3 = 628;
    v4 = 724;
    goto LABEL_4;
  }
  v20 = *(unsigned int *)(v19 + 716);
  v242 = *(_DWORD *)(v19 + 744);
  v250 = *(_DWORD *)(v19 + 748);
  v248 = 0;
  v249 = 0;
  v252 = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  GetFuncPtr(v19 + 728, &v248, &v249, &v252);
  *((_QWORD *)this + 5) = *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(*((_QWORD *)this + 18) + 40LL);
  v21 = *((_QWORD *)this + 1);
  if ( v20 <= v21 )
    v21 = v20;
  v254 = v21;
  if ( *(_BYTE *)(*((_QWORD *)this + 18) + 33LL) )
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
    v22 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 16) + 240LL),
            (__int64)L"> CPU(");
    v23 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v22, *(_DWORD *)this);
    v24 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v23, (__int64)L")  TID: ");
    v240 = 4;
    v25 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v24, &v240);
    CurrentThreadId = GetCurrentThreadId();
    v27 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v25, CurrentThreadId);
    *(_DWORD *)((char *)v27 + *(int *)(*v27 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v27 + *(int *)(*v27 + 4) + 88) = 32;
    *(__int64 *)((char *)v27 + *(int *)(*v27 + 4) + 40) = 0;
    v28 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, (__int64)L"\n");
    v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, (__int64)L"  -- Running at ");
    v30 = L"NORMAL";
    if ( !*(_BYTE *)(*((_QWORD *)this + 18) + 737LL) )
      v30 = L"HIGH";
    v31 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, (__int64)v30);
    v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, (__int64)L" priority\n");
    v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, (__int64)L"  -- Allocated ");
    v34 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v33, v244);
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, (__int64)L" (0x");
    v240 = 4;
    v36 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, &v240);
    v37 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v36, v244);
    *(_DWORD *)((char *)v37 + *(int *)(*v37 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v37 + *(int *)(*v37 + 4) + 88) = 32;
    v38 = 0;
    *(__int64 *)((char *)v37 + *(int *)(*v37 + 4) + 40) = 0;
    v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v37, (__int64)L") bytes\n");
    v40 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, (__int64)L"  -- Affinity Mask ");
    v240 = 8;
    v41 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v40, &v240);
    v42 = std::basic_ostream<unsigned short>::operator<<(v41, *((_DWORD *)this + 68));
    *(_DWORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v42 + 4LL) + v42 + 40) = 0;
    v43 = (__int64 *)std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, "\n");
    v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v43, (__int64)L"  -- Copy Routine = ");
    v45 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v44,
            (unsigned __int64 **)(*((_QWORD *)this + 18) + 728LL));
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, "\n");
    std::basic_ostream<unsigned short>::flush(*((_QWORD *)this + 16) + 240LL);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
  }
  else
  {
    v38 = 0;
  }
  if ( v252 )
  {
    v46 = *((_QWORD *)this + 18);
    v234 = mlib::m_traits<unsigned short>::CStrlen(L"memcpy", 0x10000);
    if ( !(unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
                          v46 + 728,
                          v47,
                          **(_QWORD **)(v46 + 728),
                          L"memcpy") )
    {
      v48 = 1;
LABEL_32:
      v239 = v48;
      goto LABEL_33;
    }
    v49 = *((_QWORD *)this + 18);
    v234 = mlib::m_traits<unsigned short>::CStrlen(L"memcpy_inl", 0x10000);
    if ( !(unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei_str(
                          v49 + 728,
                          v50,
                          **(_QWORD **)(v49 + 728),
                          L"memcpy_inl") )
    {
      v48 = 2;
      goto LABEL_32;
    }
  }
  if ( v249 )
  {
    v48 = 3;
    goto LABEL_32;
  }
  if ( !v248 )
  {
    if ( !v252 )
    {
      v220 = 0;
      WinSAT::OpStatus::SetResult((char *)this + 400, 5, L"Internal Error", 0);
      SetLastError(0xDu);
      goto LABEL_155;
    }
    v48 = 5;
    goto LABEL_32;
  }
  v48 = 4;
LABEL_33:
  v236 = 0;
  v244 = 0;
  v51 = *((_QWORD *)this + 18);
  *((_QWORD *)this + 43) = v51 + 764;
  *((_QWORD *)this + 44) = v51 + 768;
  *((_QWORD *)this + 45) = v51 + 772;
  *((_QWORD *)this + 46) = v51 + 776;
  *((_QWORD *)this + 47) = v51 + 780;
  *((_QWORD *)this + 48) = v51 + 760;
  *((_DWORD *)this + 98) = *(_DWORD *)(v51 + 68);
  TickCount = GetTickCount();
  v53 = *((_QWORD *)this + 18);
  v255 = TickCount + (int)(*(double *)(v53 + 680) * 1000.0);
  v256 = TickCount + (int)(*(double *)(v53 + 688) * 1000.0);
  v238 = *(_BYTE *)(v53 + 696);
  v237 = 0;
  PerformanceCounter64 = mlib::QueryPerformanceCounter64((mlib *)v53);
  v246 = -1;
  v247 = 0;
  v245 = 0;
  v241 = *(_BYTE *)(*((_QWORD *)this + 18) + 697LL);
  *((_QWORD *)this + 38) = __rdtsc();
  while ( !WinSAT::OpMem1Thread::ExitLoop(this) || v238 )
  {
    v54 = *((_QWORD *)this + 19);
    v55 = (*((_QWORD *)this + 21) - v54) >> 3;
    if ( v55 < *((_QWORD *)this + 33) && (*((_QWORD *)this + 20) - v54) >> 3 >= v55 )
      SampleManager::GrowSizeBy((WinSAT::OpMem1Thread *)((char *)this + 152), 0x4000u);
    if ( !WinSAT::OpMem1Thread::Rendevous(this) )
      break;
    v235 = GetTickCount();
    v240 = 0;
    if ( v242 )
    {
      while ( 1 )
      {
        if ( v48 == 1 || v48 == 2 )
        {
          v243 = __rdtsc();
          memcpy_0(v251, v15, *((_QWORD *)this + 1));
          goto LABEL_51;
        }
        if ( v48 == 3 )
        {
          v243 = __rdtsc();
          ((void (__fastcall *)(char *, void *, _QWORD, __int64, unsigned __int64))v249)(
            v15,
            v251,
            *((_QWORD *)this + 1),
            1,
            v254);
          goto LABEL_51;
        }
        if ( v48 == 4 )
          break;
        if ( v48 == 5 )
        {
          v243 = __rdtsc();
          v252(v15, v251, *((_QWORD *)this + 1));
LABEL_51:
          v57 = __rdtsc();
          v56 = v243;
          goto LABEL_52;
        }
        v56 = 0;
        v243 = 0;
        v57 = 0;
LABEL_52:
        if ( !v237 )
        {
          SampleManager::AddSample((WinSAT::OpMem1Thread *)((char *)this + 152), v57 - v56);
          v244 += v57 - v243;
        }
        if ( !**((_DWORD **)this + 46) && !**((_DWORD **)this + 45) )
        {
          ++v240;
          v48 = v239;
          if ( v240 < v242 )
            continue;
        }
        goto LABEL_57;
      }
      v243 = __rdtsc();
      ((void (__fastcall *)(char *, void *, _QWORD, __int64, __int64))v248)(v15, v251, *((_QWORD *)this + 1), 1, v234);
      goto LABEL_51;
    }
LABEL_57:
    if ( **((_DWORD **)this + 46) || **((_DWORD **)this + 45) )
      break;
    if ( !v241 )
      Sleep(*(_DWORD *)(*((_QWORD *)this + 18) + 704LL));
    ++v245;
    v58 = GetTickCount() - v235;
    v59 = v247;
    if ( v58 > v247 )
      v59 = v58;
    v247 = v59;
    v60 = v246;
    if ( v58 < v246 )
      v60 = v58;
    v246 = v60;
    if ( v58 >= 0xA )
    {
      if ( v58 < 0x4B )
        v242 += v242 >> 1;
    }
    else
    {
      v242 *= 2;
    }
    v48 = v239;
    if ( !v237 && !v238 )
    {
      SampleManager::Process((WinSAT::OpMem1Thread *)((char *)this + 152), v250);
      if ( GetTickCount() >= (unsigned int)v255 && *((_BYTE *)this + 256) )
      {
        v38 = __rdtsc();
        _InterlockedAdd(*((volatile signed __int32 **)this + 48), 1u);
        goto LABEL_76;
      }
      if ( GetTickCount() >= (unsigned int)v256 )
      {
        _InterlockedAdd(*((volatile signed __int32 **)this + 48), 1u);
LABEL_76:
        v237 = 1;
      }
    }
  }
  if ( **((_DWORD **)this + 46) )
    goto LABEL_153;
  v61 = (mlib *)**((unsigned int **)this + 45);
  if ( (_DWORD)v61 )
    goto LABEL_153;
  v62 = mlib::QueryPerformanceCounter64(v61);
  *((_QWORD *)this + 39) = __rdtsc();
  PerformanceFrequency64 = mlib::QueryPerformanceFrequency64(v63);
  if ( PerformanceFrequency64 < 0 )
    v65 = (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1))
        + (double)(int)(PerformanceFrequency64 & 1 | ((unsigned __int64)PerformanceFrequency64 >> 1));
  else
    v65 = (double)(int)PerformanceFrequency64;
  v66 = PerformanceCounter64;
  if ( PerformanceCounter64 < 0 )
    v67 = (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1))
        + (double)(int)(PerformanceCounter64 & 1 | ((unsigned __int64)PerformanceCounter64 >> 1));
  else
    v67 = (double)(int)PerformanceCounter64;
  *((double *)this + 35) = v67 / v65;
  if ( v62 < 0 )
    v68 = (double)(int)(v62 & 1 | ((unsigned __int64)v62 >> 1)) + (double)(int)(v62 & 1 | ((unsigned __int64)v62 >> 1));
  else
    v68 = (double)(int)v62;
  *((double *)this + 36) = v68 / v65;
  v69 = v62 - v66;
  if ( v69 < 0 )
    v70 = (double)(int)(v69 & 1 | ((unsigned __int64)v69 >> 1)) + (double)(int)(v69 & 1 | ((unsigned __int64)v69 >> 1));
  else
    v70 = (double)(int)v69;
  v71 = v70 / v65;
  *((double *)this + 37) = v71;
  v72 = *((_QWORD *)this + 5);
  if ( v72 < 0 )
    v73 = (double)(int)(v72 & 1 | ((unsigned __int64)v72 >> 1)) + (double)(int)(v72 & 1 | ((unsigned __int64)v72 >> 1));
  else
    v73 = (double)(int)v72;
  v74 = *((_QWORD *)this + 38);
  v75 = *((_QWORD *)this + 39) - v74;
  if ( v75 < 0 )
    v76 = (double)(int)(v75 & 1 | ((unsigned __int64)v75 >> 1)) + (double)(int)(v75 & 1 | ((unsigned __int64)v75 >> 1));
  else
    v76 = (double)(int)v75;
  v77 = v76 / v73;
  *((double *)this + 40) = v77;
  if ( v38 )
  {
    v78 = v38 - v74;
    if ( v78 < 0 )
      v79 = (double)(int)(v78 & 1 | ((unsigned __int64)v78 >> 1))
          + (double)(int)(v78 & 1 | ((unsigned __int64)v78 >> 1));
    else
      v79 = (double)(int)v78;
    *((double *)this + 8) = v79 / v73;
  }
  *(_QWORD *)&v80 = COERCE_UNSIGNED_INT64(v77 - v71) & _xmm;
  v81 = v71 / 1000.0 * 5.0;
  v236 = v80 > v81;
  v82 = v244;
  v83 = (v244 & 0x8000000000000000uLL) != 0LL
      ? (double)(int)(v244 & 1 | (v244 >> 1)) + (double)(int)(v244 & 1 | (v244 >> 1))
      : (double)(int)v244;
  v84 = v83 / v73;
  *((double *)this + 7) = v84;
  v85 = (__int64)(*((_QWORD *)this + 20) - *((_QWORD *)this + 19)) >> 3;
  *((_QWORD *)this + 4) = v85;
  v86 = *((_QWORD *)this + 1);
  v87 = v86 < 0
      ? (double)(int)(v86 & 1 | ((unsigned __int64)v86 >> 1)) + (double)(int)(v86 & 1 | ((unsigned __int64)v86 >> 1))
      : (double)(int)v86;
  v88 = v85 < 0
      ? (double)(int)(v85 & 1 | ((unsigned __int64)v85 >> 1)) + (double)(int)(v85 & 1 | ((unsigned __int64)v85 >> 1))
      : (double)(int)v85;
  v89 = v88 * v87;
  *((double *)this + 6) = v89;
  v90 = *((_QWORD *)this + 25);
  v91 = v90 < 0
      ? (double)(int)(v90 & 1 | ((unsigned __int64)v90 >> 1)) + (double)(int)(v90 & 1 | ((unsigned __int64)v90 >> 1))
      : (double)(int)v90;
  v92 = v91 / v73;
  v93 = v87 + v87;
  v94 = *((_QWORD *)this + 29);
  v95 = v94 < 0
      ? (double)(int)(v94 & 1 | ((unsigned __int64)v94 >> 1)) + (double)(int)(v94 & 1 | ((unsigned __int64)v94 >> 1))
      : (double)(int)v94;
  *((double *)this + 9) = v93 / (v95 / v73);
  *((double *)this + 10) = v93 / v92;
  v96 = *((_QWORD *)this + 23);
  v97 = v96 < 0
      ? (double)(int)(v96 & 1 | ((unsigned __int64)v96 >> 1)) + (double)(int)(v96 & 1 | ((unsigned __int64)v96 >> 1))
      : (double)(int)v96;
  *((double *)this + 11) = v93 / (v97 / v73);
  v98 = *((_QWORD *)this + 24);
  v99 = v98 < 0
      ? (double)(int)(v98 & 1 | ((unsigned __int64)v98 >> 1)) + (double)(int)(v98 & 1 | ((unsigned __int64)v98 >> 1))
      : (double)(int)v98;
  *((double *)this + 12) = v93 / (v99 / v73);
  *((double *)this + 13) = (v89 + v89) / v84;
  if ( !*(_BYTE *)(*((_QWORD *)this + 18) + 33LL) )
  {
LABEL_153:
    v220 = v236;
  }
  else
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
    v100 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"> CPU(");
    v101 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v100, *(_DWORD *)this);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v101, (__int64)L")\n");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(
      (__int64 *)(*((_QWORD *)this + 16) + 240LL),
      (__int64)L"  --                     elapsed ticks : ");
    v235 = 12;
    v102 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(*((_QWORD *)this + 16) + 240LL, &v235);
    v103 = std::basic_ostream<unsigned short>::operator<<(v102, v82);
    *(_DWORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v103 + 4LL) + v103 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v103, "\n");
    v104 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --          cummulative copy seconds : ");
    *(_DWORD *)((char *)v104 + *(int *)(*v104 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v104 + *(int *)(*v104 + 4) + 32) = 9;
    *(__int64 *)((char *)v104 + *(int *)(*v104 + 4) + 40) = 10;
    v105 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v104, *((double *)this + 7));
    *(_DWORD *)((char *)v105 + *(int *)(*v105 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v105 + *(int *)(*v105 + 4) + 88) = 32;
    *(__int64 *)((char *)v105 + *(int *)(*v105 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v105, (__int64)L"\n");
    v106 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --               good data duration  : ");
    *(_DWORD *)((char *)v106 + *(int *)(*v106 + 4) + 24) |= 0x2080u;
    *(__int64 *)((char *)v106 + *(int *)(*v106 + 4) + 32) = 9;
    *(__int64 *)((char *)v106 + *(int *)(*v106 + 4) + 40) = 0;
    v107 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v106, *((double *)this + 8));
    *(_DWORD *)((char *)v107 + *(int *)(*v107 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v107 + *(int *)(*v107 + 4) + 88) = 32;
    *(__int64 *)((char *)v107 + *(int *)(*v107 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v107, (__int64)L"\n");
    v108 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                       min seconds : ");
    *(_DWORD *)((char *)v108 + *(int *)(*v108 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v108 + *(int *)(*v108 + 4) + 32) = 9;
    *(__int64 *)((char *)v108 + *(int *)(*v108 + 4) + 40) = 10;
    v109 = std::basic_ostream<unsigned short>::operator<<((__int64)v108, v92);
    *(_DWORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v109 + 4LL) + v109 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v109, "\n");
    v110 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                 buffer copy count : ");
    v235 = 12;
    v111 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v110, &v235);
    v112 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v111, *((_QWORD *)this + 4));
    *(_DWORD *)((char *)v112 + *(int *)(*v112 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v112 + *(int *)(*v112 + 4) + 88) = 32;
    *(__int64 *)((char *)v112 + *(int *)(*v112 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v112, (__int64)L"\n");
    v113 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                               B/s : ");
    *(_DWORD *)((char *)v113 + *(int *)(*v113 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v113 + *(int *)(*v113 + 4) + 32) = 1;
    *(__int64 *)((char *)v113 + *(int *)(*v113 + 4) + 40) = 13;
    v114 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v113, *((double *)this + 9));
    *(_DWORD *)((char *)v114 + *(int *)(*v114 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v114 + *(int *)(*v114 + 4) + 88) = 32;
    *(__int64 *)((char *)v114 + *(int *)(*v114 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v114, (__int64)L"\n");
    v115 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                         B/s (min) : ");
    *(_DWORD *)((char *)v115 + *(int *)(*v115 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v115 + *(int *)(*v115 + 4) + 32) = 1;
    *(__int64 *)((char *)v115 + *(int *)(*v115 + 4) + 40) = 13;
    v116 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v115, *((double *)this + 10));
    *(_DWORD *)((char *)v116 + *(int *)(*v116 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v116 + *(int *)(*v116 + 4) + 88) = 32;
    *(__int64 *)((char *)v116 + *(int *)(*v116 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v116, (__int64)L"\n");
    v117 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                       B/s (median): ");
    *(_DWORD *)((char *)v117 + *(int *)(*v117 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v117 + *(int *)(*v117 + 4) + 32) = 1;
    *(__int64 *)((char *)v117 + *(int *)(*v117 + 4) + 40) = 13;
    v118 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v117, *((double *)this + 11));
    *(_DWORD *)((char *)v118 + *(int *)(*v118 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v118 + *(int *)(*v118 + 4) + 88) = 32;
    *(__int64 *)((char *)v118 + *(int *)(*v118 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v118, (__int64)L"\n");
    v119 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                         B/s(mean) : ");
    *(_DWORD *)((char *)v119 + *(int *)(*v119 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v119 + *(int *)(*v119 + 4) + 32) = 1;
    *(__int64 *)((char *)v119 + *(int *)(*v119 + 4) + 40) = 13;
    v120 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v119, *((double *)this + 12));
    *(_DWORD *)((char *)v120 + *(int *)(*v120 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v120 + *(int *)(*v120 + 4) + 88) = 32;
    *(__int64 *)((char *)v120 + *(int *)(*v120 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v120, (__int64)L"\n");
    v121 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                       B/s (mean2) : ");
    *(_DWORD *)((char *)v121 + *(int *)(*v121 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v121 + *(int *)(*v121 + 4) + 32) = 1;
    *(__int64 *)((char *)v121 + *(int *)(*v121 + 4) + 40) = 13;
    v122 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v121, *((double *)this + 13));
    *(_DWORD *)((char *)v122 + *(int *)(*v122 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v122 + *(int *)(*v122 + 4) + 88) = 32;
    *(__int64 *)((char *)v122 + *(int *)(*v122 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v122, (__int64)L"\n");
    v123 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                      Elapsed Secs : ");
    *(_DWORD *)((char *)v123 + *(int *)(*v123 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v123 + *(int *)(*v123 + 4) + 32) = 9;
    *(__int64 *)((char *)v123 + *(int *)(*v123 + 4) + 40) = 21;
    v124 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v123, *((double *)this + 37));
    *(_DWORD *)((char *)v124 + *(int *)(*v124 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v124 + *(int *)(*v124 + 4) + 88) = 32;
    *(__int64 *)((char *)v124 + *(int *)(*v124 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v124, (__int64)L"\n");
    v125 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                RDTSC Elapsed Secs : ");
    *(_DWORD *)((char *)v125 + *(int *)(*v125 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v125 + *(int *)(*v125 + 4) + 32) = 9;
    *(__int64 *)((char *)v125 + *(int *)(*v125 + 4) + 40) = 21;
    v126 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v125, *((double *)this + 40));
    *(_DWORD *)((char *)v126 + *(int *)(*v126 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v126 + *(int *)(*v126 + 4) + 88) = 32;
    *(__int64 *)((char *)v126 + *(int *)(*v126 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v126, (__int64)L"\n");
    v127 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                         diff secs : ");
    *(_DWORD *)((char *)v127 + *(int *)(*v127 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v127 + *(int *)(*v127 + 4) + 32) = 9;
    *(__int64 *)((char *)v127 + *(int *)(*v127 + 4) + 40) = 21;
    v128 = std::basic_ostream<unsigned short>::operator<<((__int64)v127, v80);
    *(_DWORD *)(*(int *)(*(_QWORD *)v128 + 4LL) + v128 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v128 + 4LL) + v128 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v128 + 4LL) + v128 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v128, "\n");
    v129 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                  max allowed diff : ");
    *(_DWORD *)((char *)v129 + *(int *)(*v129 + 4) + 24) |= 0x2090u;
    *(__int64 *)((char *)v129 + *(int *)(*v129 + 4) + 32) = 9;
    *(__int64 *)((char *)v129 + *(int *)(*v129 + 4) + 40) = 21;
    v130 = std::basic_ostream<unsigned short>::operator<<((__int64)v129, v81);
    *(_DWORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v130 + 4LL) + v130 + 40) = 0;
    v131 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  - ");
    v132 = L"Delta VIOLATION!";
    if ( !v236 )
      v132 = L"delta OK";
    v133 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v131, (__int64)v132);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v133, (__int64)L"\n");
    v134 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --             measurment loop count : ");
    v135 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v134, v245);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v135, (__int64)L"\n");
    v136 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                 sample block size : ");
    v137 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v136, v242);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v137, (__int64)L"\n");
    v138 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                 min loop duration : ");
    v139 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v138, v246);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v139, (__int64)L"\n");
    v140 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"  --                 max loop duration : ");
    v141 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v140, v247);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v141, (__int64)L"\n");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(
      (__int64 *)(*((_QWORD *)this + 16) + 240LL),
      (__int64)L"  -- Statistics --\n");
    v142 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       + Total Samples : ");
    v235 = 12;
    v143 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v142, &v235);
    v144 = std::basic_ostream<unsigned short>::operator<<(
             v143,
             (__int64)(*((_QWORD *)this + 20) - *((_QWORD *)this + 19)) >> 3);
    *(_DWORD *)(*(int *)(*(_QWORD *)v144 + 4LL) + v144 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v144 + 4LL) + v144 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v144 + 4LL) + v144 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v144, "\n");
    v145 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +           min : ");
    v235 = 12;
    v146 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v145, &v235);
    v147 = std::basic_ostream<unsigned short>::operator<<(v146, *((_QWORD *)this + 25));
    *(_DWORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v147 + 4LL) + v147 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v147, "\n");
    v148 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +lower quartile : ");
    v235 = 12;
    v149 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v148, &v235);
    v150 = std::basic_ostream<unsigned short>::operator<<(v149, *((_QWORD *)this + 29));
    *(_DWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v150 + 4LL) + v150 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v150, "\n");
    v151 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +        median : ");
    v235 = 12;
    v152 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v151, &v235);
    v153 = std::basic_ostream<unsigned short>::operator<<(v152, *((_QWORD *)this + 23));
    *(_DWORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v153 + 4LL) + v153 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v153, "\n");
    v154 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +          mean : ");
    v235 = 12;
    v155 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v154, &v235);
    v156 = std::basic_ostream<unsigned short>::operator<<(v155, *((_QWORD *)this + 24));
    *(_DWORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v156 + 4LL) + v156 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v156, "\n");
    v157 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +upper quartile : ");
    v235 = 12;
    v158 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v157, &v235);
    v159 = std::basic_ostream<unsigned short>::operator<<(v158, *((_QWORD *)this + 28));
    *(_DWORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v159 + 4LL) + v159 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v159, "\n");
    v160 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +           max : ");
    v235 = 12;
    v161 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v160, &v235);
    v162 = std::basic_ostream<unsigned short>::operator<<(v161, *((_QWORD *)this + 26));
    *(_DWORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v162 + 4LL) + v162 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v162, "\n");
    v163 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +         range : ");
    v235 = 12;
    v164 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v163, &v235);
    v165 = std::basic_ostream<unsigned short>::operator<<(v164, *((_QWORD *)this + 27));
    *(_DWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v165 + 4LL) + v165 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v165, "\n");
    v166 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +      IQ range : ");
    v235 = 12;
    v167 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v166, &v235);
    v168 = std::basic_ostream<unsigned short>::operator<<(v167, *((_QWORD *)this + 30));
    *(_DWORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v168 + 4LL) + v168 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v168, "\n");
    v169 = *((_QWORD *)this + 25);
    v170 = *((_QWORD *)this + 23);
    v244 = v170 - v169;
    v171 = *((_QWORD *)this + 29);
    v249 = v171 - v169;
    v248 = v170 - v171;
    v172 = v169 * (unsigned __int64)v250 / 0x186A0;
    v173 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +    median-Min : ");
    v235 = 12;
    v174 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v173, &v235);
    v175 = std::basic_ostream<unsigned short>::operator<<(v174, v244);
    *(_DWORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v175 + 4LL) + v175 + 40) = 0;
    v176 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v175, " ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 32) = 2;
    *(_QWORD *)(*(int *)(*(_QWORD *)v176 + 4LL) + v176 + 40) = 3;
    if ( (v244 & 0x8000000000000000uLL) != 0LL )
      v177 = (double)(int)(v244 & 1 | (v244 >> 1)) + (double)(int)(v244 & 1 | (v244 >> 1));
    else
      v177 = (double)(int)v244;
    v178 = v177 * 100.0;
    v179 = *((_QWORD *)this + 25);
    if ( v179 < 0 )
      v180 = (double)(int)(v179 & 1 | ((unsigned __int64)v179 >> 1))
           + (double)(int)(v179 & 1 | ((unsigned __int64)v179 >> 1));
    else
      v180 = (double)(int)v179;
    v181 = std::basic_ostream<unsigned short>::operator<<(v176, v178 / v180);
    *(_DWORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v181 + 4LL) + v181 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v181, "% of min \n", v182);
    v183 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +        lq-Min : ");
    v235 = 12;
    v184 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v183, &v235);
    v185 = std::basic_ostream<unsigned short>::operator<<(v184, v249);
    *(_DWORD *)(*(int *)(*(_QWORD *)v185 + 4LL) + v185 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v185 + 4LL) + v185 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v185 + 4LL) + v185 + 40) = 0;
    v186 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v185, " ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v186 + 4LL) + v186 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v186 + 4LL) + v186 + 32) = 2;
    *(_QWORD *)(*(int *)(*(_QWORD *)v186 + 4LL) + v186 + 40) = 3;
    if ( v249 < 0 )
      v187 = (double)(int)(v249 & 1 | ((unsigned __int64)v249 >> 1))
           + (double)(int)(v249 & 1 | ((unsigned __int64)v249 >> 1));
    else
      v187 = (double)(int)v249;
    v188 = v187 * 100.0;
    v189 = *((_QWORD *)this + 25);
    if ( v189 < 0 )
      v190 = (double)(int)(v189 & 1 | ((unsigned __int64)v189 >> 1))
           + (double)(int)(v189 & 1 | ((unsigned __int64)v189 >> 1));
    else
      v190 = (double)(int)v189;
    v191 = std::basic_ostream<unsigned short>::operator<<(v186, v188 / v190);
    *(_DWORD *)(*(int *)(*(_QWORD *)v191 + 4LL) + v191 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v191 + 4LL) + v191 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v191 + 4LL) + v191 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v191, "% of min \n", v192);
    v193 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +     median-lq : ");
    v235 = 12;
    v194 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v193, &v235);
    v195 = std::basic_ostream<unsigned short>::operator<<(v194, v248);
    *(_DWORD *)(*(int *)(*(_QWORD *)v195 + 4LL) + v195 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v195 + 4LL) + v195 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v195 + 4LL) + v195 + 40) = 0;
    v196 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v195, " ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v196 + 4LL) + v196 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v196 + 4LL) + v196 + 32) = 2;
    *(_QWORD *)(*(int *)(*(_QWORD *)v196 + 4LL) + v196 + 40) = 3;
    if ( v248 < 0 )
      v197 = (double)(int)(v248 & 1 | ((unsigned __int64)v248 >> 1))
           + (double)(int)(v248 & 1 | ((unsigned __int64)v248 >> 1));
    else
      v197 = (double)(int)v248;
    v198 = v197 * 100.0;
    v199 = *((_QWORD *)this + 29);
    if ( v199 < 0 )
      v200 = (double)(int)(v199 & 1 | ((unsigned __int64)v199 >> 1))
           + (double)(int)(v199 & 1 | ((unsigned __int64)v199 >> 1));
    else
      v200 = (double)(int)v199;
    v201 = std::basic_ostream<unsigned short>::operator<<(v196, v198 / v200);
    *(_DWORD *)(*(int *)(*(_QWORD *)v201 + 4LL) + v201 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v201 + 4LL) + v201 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v201 + 4LL) + v201 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v201, "% of lq \n", v202);
    v203 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +         Limit : ");
    v235 = 12;
    v204 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v203, &v235);
    v205 = std::basic_ostream<unsigned short>::operator<<(v204, v172);
    v206 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v205, " ");
    *(_DWORD *)(*(int *)(*(_QWORD *)v206 + 4LL) + v206 + 24) |= 0x2090u;
    *(_QWORD *)(*(int *)(*(_QWORD *)v206 + 4LL) + v206 + 32) = 2;
    *(_QWORD *)(*(int *)(*(_QWORD *)v206 + 4LL) + v206 + 40) = 3;
    if ( (v172 & 0x8000000000000000uLL) != 0LL )
      v207 = (double)(int)(v172 & 1 | (v172 >> 1)) + (double)(int)(v172 & 1 | (v172 >> 1));
    else
      v207 = (double)(int)v172;
    v208 = v207 * 100.0;
    v209 = *((_QWORD *)this + 25);
    if ( v209 < 0 )
      v210 = (double)(int)(v209 & 1 | ((unsigned __int64)v209 >> 1))
           + (double)(int)(v209 & 1 | ((unsigned __int64)v209 >> 1));
    else
      v210 = (double)(int)v209;
    v211 = std::basic_ostream<unsigned short>::operator<<(v206, v208 / v210);
    *(_DWORD *)(*(int *)(*(_QWORD *)v211 + 4LL) + v211 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v211 + 4LL) + v211 + 88) = 32;
    v212 = *(int *)(*(_QWORD *)v211 + 4LL);
    *(_QWORD *)(v212 + v211 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v211, "% of min \n", v212);
    v213 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +           Sum : ");
    v235 = 12;
    v214 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v213, &v235);
    v215 = std::basic_ostream<unsigned short>::operator<<(v214, *((_QWORD *)this + 22));
    *(_DWORD *)(*(int *)(*(_QWORD *)v215 + 4LL) + v215 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v215 + 4LL) + v215 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v215 + 4LL) + v215 + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v215, "\n");
    v216 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 16) + 240LL),
             (__int64)L"                       +        Status : ");
    v235 = 12;
    v217 = (__int64 *)mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v216, &v235);
    v218 = L"GOOD";
    if ( !*((_BYTE *)this + 256) )
      v218 = L"BAD";
    v219 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v217, (__int64)v218);
    *(_DWORD *)((char *)v219 + *(int *)(*v219 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v219 + *(int *)(*v219 + 4) + 88) = 32;
    *(__int64 *)((char *)v219 + *(int *)(*v219 + 4) + 40) = 0;
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v219, "\n");
    std::endl(*((_QWORD *)this + 16) + 240LL);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
    v220 = v236;
  }
LABEL_155:
  if ( !VirtualFree(v15, 0, 0x8000u) )
  {
    dwErrCode = GetLastError();
    v259 = 1;
    v260 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v5 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x488, 630, *(_DWORD *)this);
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 15));
    v6 = (__int64 *)(*((_QWORD *)this + 17) + 240LL);
    goto LABEL_5;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 18) + 776LL) )
  {
    v221 = 631;
    v222 = 1179;
    goto LABEL_161;
  }
  if ( *(int *)(*((_QWORD *)this + 18) + 772LL) <= 0 )
  {
    if ( v220 )
    {
      v225 = (__int64 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw)
                       + 240);
      v226 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x4A9, 663, *(_DWORD *)this);
      v227 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v225, (__int64)v226);
      std::endl(v227);
      *((_BYTE *)this + 336) = 1;
    }
    v223 = (_DWORD *)((char *)this + 400);
    *((_DWORD *)this + 100) = 6;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((__int64)this + 408);
    *((_BYTE *)this + 416) = 0;
  }
  else
  {
    v221 = 632;
    v222 = 1184;
LABEL_161:
    v223 = (_DWORD *)((char *)this + 400);
    v224 = mlib::MUISpf_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)v222, v221, *(_DWORD *)this, v234);
    WinSAT::OpStatus::SetResult((char *)this + 400, 5, v224, 0);
  }
  v228 = *v223 != 6 ? 0xD : 0;
  SetLastError(v228);
  return v228;
}

```

## disassembly

```asm
0x140059ef4  mov     rax, rsp
0x140059ef7  mov     [rax+10h], rbx
0x140059efb  mov     [rax+18h], rsi
0x140059eff  push    rdi
0x140059f00  push    r12
0x140059f02  push    r13
0x140059f04  push    r14
0x140059f06  push    r15
0x140059f08  sub     rsp, 300h
0x140059f0f  movaps  xmmword ptr [rax-38h], xmm6
0x140059f13  movaps  xmmword ptr [rax-48h], xmm7
0x140059f17  movaps  xmmword ptr [rax-58h], xmm8
0x140059f1c  mov     rax, cs:__security_cookie
0x140059f23  xor     rax, rsp
0x140059f26  mov     [rsp+328h+var_68], rax
0x140059f2e  mov     rdi, rcx
0x140059f31  mov     [rsp+328h+var_298], rcx
0x140059f39  mov     rax, [rcx+90h]
0x140059f40  xor     r13d, r13d
0x140059f43  cmp     [rax+2E1h], r13b
0x140059f4a  jnz     loc_14005A071
0x140059f50  call    cs:__imp_GetCurrentThread
0x140059f56  mov     rcx, rax; hThread
0x140059f59  lea     edx, [r13+0Fh]; nPriority
0x140059f5d  call    cs:__imp_SetThreadPriority
0x140059f63  test    eax, eax
0x140059f65  jnz     loc_14005A047
0x140059f6b  mov     rax, [rdi+90h]
0x140059f72  lea     esi, [r13+1]
0x140059f76  lock add [rax+304h], esi
0x140059f7d  call    cs:__imp_GetLastError
0x140059f83  mov     [rsp+328h+dwErrCode], eax
0x140059f8a  mov     [rsp+328h+var_74], sil
0x140059f92  mov     [rsp+328h+var_70], r13
0x140059f9a  lea     rcx, [rsp+328h+Buffer]; lpBuffer
0x140059fa2  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140059fa7  mov     r8d, 270h; int
0x140059fad  lea     edx, [r8-18h]; char *
0x140059fb1  mov     r9d, [rdi]; unsigned __int16
0x140059fb4  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x140059fbb  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x140059fc0  mov     rbx, rax
0x140059fc3  mov     rcx, [rdi+78h]; lpCriticalSection
0x140059fc7  call    cs:__imp_EnterCriticalSection
0x140059fcd  mov     rcx, [rdi+88h]
0x140059fd4  add     rcx, 0F0h
0x140059fdb  mov     rdx, rbx
0x140059fde  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140059fe3  mov     edx, 0Ah
0x140059fe8  mov     rcx, rax
0x140059feb  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140059ff0  lea     rdx, [rsp+328h+Buffer]
0x140059ff8  mov     rcx, rax
0x140059ffb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a000  mov     rcx, rax
0x14005a003  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005a008  mov     rcx, [rdi+78h]; lpCriticalSection
0x14005a00c  call    cs:__imp_LeaveCriticalSection
0x14005a012  lea     rcx, [rdi+190h]
0x14005a019  lea     r9, [rsp+328h+Buffer]
0x14005a021  mov     r8, rbx
0x14005a024  mov     edx, 5
0x14005a029  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGAEBV?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>> const &)
0x14005a02e  mov     ecx, [rsp+328h+dwErrCode]; dwErrCode
0x14005a035  call    cs:__imp_SetLastError
0x14005a03b  mov     eax, [rsp+328h+dwErrCode]
0x14005a042  jmp     loc_14005C106
0x14005a047  call    cs:__imp_GetCurrentThread
0x14005a04d  mov     rcx, rax; hThread
0x14005a050  call    cs:__imp_GetThreadPriority
0x14005a056  mov     r9d, eax
0x14005a059  lea     r8, aAdjustedThePri; "Adjusted the priority of the Memory cop"...
0x14005a060  mov     edx, 262h
0x14005a065  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005a06c  call    Log_Text_F
0x14005a071  mov     esi, 1
0x14005a076  mov     ecx, esi; dwMilliseconds
0x14005a078  call    cs:__imp_Sleep
0x14005a07e  nop
0x14005a07f  lea     rcx, [rdi+98h]; this
0x14005a086  mov     edx, 4000h; unsigned __int64
0x14005a08b  call    ?ClearAndReserve@SampleManager@@QEAAX_K@Z; SampleManager::ClearAndReserve(unsigned __int64)
0x14005a090  nop
0x14005a091  mov     rcx, [rdi+8]
0x14005a095  mov     rax, [rdi+10h]
0x14005a099  lea     rdx, [rax+rcx*2]; dwSize
0x14005a09d  mov     [rsp+328h+var_2D8], rdx
0x14005a0a2  mov     rax, [rdi+90h]
0x14005a0a9  mov     cl, [rax+2E0h]
0x14005a0af  neg     cl
0x14005a0b1  sbb     r9d, r9d
0x14005a0b4  and     r9d, 200h
0x14005a0bb  mov     r12d, 4
0x14005a0c1  mov     [rsp+328h+var_2F0], r12d
0x14005a0c6  add     r9d, r12d; flProtect
0x14005a0c9  xor     ecx, ecx; lpAddress
0x14005a0cb  mov     r8d, 1000h; flAllocationType
0x14005a0d1  call    cs:__imp_VirtualAlloc
0x14005a0d7  mov     r15, rax
0x14005a0da  test    rax, rax
0x14005a0dd  jnz     short loc_14005A126
0x14005a0df  mov     rax, [rdi+90h]
0x14005a0e6  lock add [rax+304h], esi
0x14005a0ed  call    cs:__imp_GetLastError
0x14005a0f3  mov     [rsp+328h+dwErrCode], eax
0x14005a0fa  mov     [rsp+328h+var_74], sil
0x14005a102  mov     [rsp+328h+var_70], r13
0x14005a10a  lea     rcx, [rsp+328h+Buffer]; lpBuffer
0x14005a112  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005a117  mov     r8d, 272h
0x14005a11d  lea     edx, [r8+2Ah]
0x14005a121  jmp     loc_140059FB1
0x14005a126  mov     [rdi+18h], r15
0x14005a12a  mov     rbx, [rdi+8]
0x14005a12e  mov     r14, [rdi+10h]
0x14005a132  mov     rdx, rbx; dwSize
0x14005a135  mov     rcx, r15; lpAddress
0x14005a138  call    cs:__imp_VirtualLock
0x14005a13e  test    eax, eax
0x14005a140  jnz     short loc_14005A19A
0x14005a142  mov     rax, [rdi+90h]
0x14005a149  lock add [rax+304h], esi
0x14005a150  call    cs:__imp_GetLastError
0x14005a156  mov     [rsp+328h+dwErrCode], eax
0x14005a15d  mov     [rsp+328h+var_74], sil
0x14005a165  mov     [rsp+328h+var_70], r13
0x14005a16d  lea     rcx, [rsp+328h+Buffer]; lpBuffer
0x14005a175  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005a17a  xor     edx, edx; dwSize
0x14005a17c  mov     r8d, 8000h; dwFreeType
0x14005a182  mov     rcx, r15; lpAddress
0x14005a185  call    cs:__imp_VirtualFree
0x14005a18b  mov     r8d, 273h
0x14005a191  lea     edx, [r8+4Bh]
0x14005a195  jmp     loc_140059FB1
0x14005a19a  lea     rax, [r14+rbx]
0x14005a19e  add     rax, r15
0x14005a1a1  mov     [rsp+328h+var_2A8], rax
0x14005a1a9  mov     rdx, [rdi+8]; dwSize
0x14005a1ad  mov     rcx, rax; lpAddress
0x14005a1b0  call    cs:__imp_VirtualLock
0x14005a1b6  mov     rcx, [rdi+90h]
0x14005a1bd  test    eax, eax
0x14005a1bf  jnz     short loc_14005A212
0x14005a1c1  lock add [rcx+304h], esi
0x14005a1c8  call    cs:__imp_GetLastError
0x14005a1ce  mov     [rsp+328h+dwErrCode], eax
0x14005a1d5  mov     [rsp+328h+var_74], sil
0x14005a1dd  mov     [rsp+328h+var_70], r13
0x14005a1e5  lea     rcx, [rsp+328h+Buffer]; lpBuffer
0x14005a1ed  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14005a1f2  xor     edx, edx; dwSize
0x14005a1f4  mov     r8d, 8000h; dwFreeType
0x14005a1fa  mov     rcx, r15; lpAddress
0x14005a1fd  call    cs:__imp_VirtualFree
0x14005a203  mov     r8d, 274h
0x14005a209  lea     edx, [r8+60h]
0x14005a20d  jmp     loc_140059FB1
0x14005a212  mov     ebx, [rcx+2CCh]
0x14005a218  mov     eax, [rcx+2E8h]
0x14005a21e  mov     [rsp+328h+var_2E4], eax
0x14005a222  mov     eax, [rcx+2ECh]
0x14005a228  mov     [rsp+328h+var_2B0], eax
0x14005a22c  mov     [rsp+328h+var_2C0], r13
0x14005a231  mov     [rsp+328h+var_2B8], r13
0x14005a236  mov     [rsp+328h+var_2A0], r13
0x14005a23e  mov     [rdi+38h], r13
0x14005a242  mov     [rdi+48h], r13
0x14005a246  mov     [rdi+50h], r13
0x14005a24a  add     rcx, 2D8h
0x14005a251  lea     r9, [rsp+328h+var_2A0]
0x14005a259  lea     r8, [rsp+328h+var_2B8]
0x14005a25e  lea     rdx, [rsp+328h+var_2C0]
0x14005a263  call    GetFuncPtr
0x14005a268  mov     rcx, [rdi+90h]
0x14005a26f  add     rcx, 28h ; '('
0x14005a273  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005a278  mov     rax, [rax]
0x14005a27b  mov     [rdi+28h], rax
0x14005a27f  mov     rax, [rdi+8]
0x14005a283  cmp     rbx, rax
0x14005a286  cmovbe  rax, rbx
0x14005a28a  mov     [rsp+328h+var_290], rax
0x14005a292  mov     rax, [rdi+90h]
0x14005a299  cmp     [rax+21h], r13b
0x14005a29d  jz      loc_14005A4C3
0x14005a2a3  mov     rcx, [rdi+78h]; lpCriticalSection
0x14005a2a7  call    cs:__imp_EnterCriticalSection
0x14005a2ad  mov     rcx, [rdi+80h]
0x14005a2b4  mov     r14d, 0F0h
0x14005a2ba  add     rcx, r14
0x14005a2bd  lea     rdx, aCpu; "> CPU("
0x14005a2c4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a2c9  mov     edx, [rdi]
0x14005a2cb  mov     rcx, rax
0x14005a2ce  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005a2d3  mov     rcx, rax
0x14005a2d6  lea     rdx, aTid; ")  TID: "
0x14005a2dd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a2e2  mov     [rsp+328h+var_2EC], r12d
0x14005a2e7  lea     rdx, [rsp+328h+var_2EC]
0x14005a2ec  mov     rcx, rax
0x14005a2ef  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzrightobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzrightobj const &)
0x14005a2f4  mov     rbx, rax
0x14005a2f7  call    cs:__imp_GetCurrentThreadId
0x14005a2fd  mov     edx, eax
0x14005a2ff  mov     rcx, rbx
0x14005a302  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005a307  mov     rcx, [rax]
0x14005a30a  movsxd  rdx, dword ptr [rcx+4]
0x14005a30e  mov     r13d, 201h
0x14005a314  or      [rdx+rax+18h], r13d
0x14005a319  mov     rcx, [rax]
0x14005a31c  movsxd  rdx, dword ptr [rcx+4]
0x14005a320  mov     ebx, 20h ; ' '
0x14005a325  mov     [rdx+rax+58h], bx
0x14005a32a  mov     rcx, [rax]
0x14005a32d  movsxd  rdx, dword ptr [rcx+4]
0x14005a331  mov     qword ptr [rdx+rax+28h], 0
0x14005a33a  lea     rdx, asc_14012B970; "\n"
0x14005a341  mov     rcx, rax
0x14005a344  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a349  mov     rcx, rax
0x14005a34c  lea     rdx, aRunningAt; "  -- Running at "
0x14005a353  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a358  mov     rcx, [rdi+90h]
0x14005a35f  lea     r8, aHigh; "HIGH"
0x14005a366  lea     rdx, aNormal_1; "NORMAL"
0x14005a36d  cmp     byte ptr [rcx+2E1h], 0
0x14005a374  cmovz   rdx, r8
0x14005a378  mov     rcx, rax
0x14005a37b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a380  mov     rcx, rax
0x14005a383  lea     rdx, aPriority; " priority\n"
0x14005a38a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a38f  mov     rcx, rax
0x14005a392  lea     rdx, aAllocated; "  -- Allocated "
0x14005a399  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a39e  mov     rdx, [rsp+328h+var_2D8]
0x14005a3a3  mov     rcx, rax
0x14005a3a6  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x14005a3ab  mov     rcx, rax
0x14005a3ae  lea     rdx, a0x_0; " (0x"
0x14005a3b5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a3ba  mov     [rsp+328h+var_2EC], r12d
0x14005a3bf  lea     rdx, [rsp+328h+var_2EC]
0x14005a3c4  mov     rcx, rax
0x14005a3c7  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x14005a3cc  mov     rdx, [rsp+328h+var_2D8]
0x14005a3d1  mov     rcx, rax
0x14005a3d4  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x14005a3d9  mov     rcx, [rax]
0x14005a3dc  movsxd  rdx, dword ptr [rcx+4]
0x14005a3e0  or      [rdx+rax+18h], r13d
0x14005a3e5  mov     rcx, [rax]
0x14005a3e8  movsxd  rdx, dword ptr [rcx+4]
0x14005a3ec  mov     [rdx+rax+58h], bx
0x14005a3f1  mov     rcx, [rax]
0x14005a3f4  movsxd  rdx, dword ptr [rcx+4]
0x14005a3f8  xor     r12d, r12d
0x14005a3fb  mov     [rdx+rax+28h], r12
0x14005a400  lea     rdx, aBytes_2; ") bytes\n"
0x14005a407  mov     rcx, rax
0x14005a40a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a40f  mov     rcx, rax
0x14005a412  lea     rdx, aAffinityMask_0; "  -- Affinity Mask "
0x14005a419  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a41e  mov     [rsp+328h+var_2EC], 8
0x14005a426  lea     rdx, [rsp+328h+var_2EC]
0x14005a42b  mov     rcx, rax
0x14005a42e  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x14005a433  mov     edx, [rdi+110h]
0x14005a439  mov     rcx, rax
0x14005a43c  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005a441  mov     rcx, [rax]
0x14005a444  movsxd  rdx, dword ptr [rcx+4]
0x14005a448  or      [rdx+rax+18h], r13d
0x14005a44d  mov     rcx, [rax]
0x14005a450  movsxd  rdx, dword ptr [rcx+4]
0x14005a454  mov     [rdx+rax+58h], bx
0x14005a459  mov     rcx, [rax]
0x14005a45c  movsxd  rdx, dword ptr [rcx+4]
0x14005a460  mov     [rdx+rax+28h], r12
0x14005a465  lea     rdx, asc_14012B93C; "\n"
0x14005a46c  mov     rcx, rax
0x14005a46f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005a474  mov     rcx, rax
0x14005a477  lea     rdx, aCopyRoutine; "  -- Copy Routine = "
0x14005a47e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005a483  mov     rdx, [rdi+90h]
0x14005a48a  add     rdx, 2D8h
0x14005a491  mov     rcx, rax
0x14005a494  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005a499  mov     rcx, rax
0x14005a49c  lea     rdx, asc_14012B93C; "\n"
0x14005a4a3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005a4a8  mov     rcx, [rdi+80h]
0x14005a4af  add     rcx, r14
0x14005a4b2  call    ?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x14005a4b7  mov     rcx, [rdi+78h]; lpCriticalSection
  ... truncated ...
```
