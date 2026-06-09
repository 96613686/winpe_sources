# WinSAT::MemAssessment1::Start(WinSAT::OpStatus &,CSmartPtr<mlib::MEvent>)

- ea: `0x14005f020`
- end: `0x14005fba8`
- name: `?Start@MemAssessment1@WinSAT@@UEAA_NAEAVOpStatus@2@V?$CSmartPtr@VMEvent@mlib@@@@@Z`
- size: `2952`
- prototype: `__int64 __fastcall(WinSAT::MemAssessment1 *this)`
- caller_count: `0`
- callee_count: `29`
- tags: `broker_com_uri`

## callees

- `0x140001a70`
- `0x140003164`
- `0x140003611`
- `0x140004170`
- `0x140004348`
- `0x14000449c`
- `0x140008178`
- `0x1400085b4`
- `0x14000f858`
- `0x140011f58`
- `0x140016264`
- `0x140016588`
- `0x1400168b4`
- `0x140016d04`
- `0x140017af0`
- `0x14001827c`
- `0x140018968`
- `0x1400219d0`
- `0x14003ec14`
- `0x14004fe00`
- `0x1400530a8`
- `0x140058d50`
- `0x1400590b0`
- `0x140059b90`
- `0x140059d54`
- `0x14005ef98`
- `0x14005f020`
- `0x14005fc20`
- `0x140113220`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x14005f1b1`
- `KERNEL32!IsProcessorFeaturePresent` at `0x14005f1b1`
- `KERNEL32!GetThreadPriority` at `0x14005f78a`
- `KERNEL32!GetThreadPriority` at `0x14005f78a`
- `KERNEL32!GetCurrentThread` at `0x14005f727`
- `KERNEL32!GetCurrentThread` at `0x14005f781`
- `KERNEL32!GetCurrentThread` at `0x14005f727`
- `KERNEL32!GetCurrentThread` at `0x14005f781`
- `KERNEL32!GetLastError` at `0x14005f682`
- `KERNEL32!GetLastError` at `0x14005f747`
- `KERNEL32!GetLastError` at `0x14005f8c8`
- `KERNEL32!GetLastError` at `0x14005f682`
- `KERNEL32!GetLastError` at `0x14005f747`
- `KERNEL32!GetLastError` at `0x14005f8c8`
- `KERNEL32!DuplicateHandle` at `0x14005f9cf`
- `KERNEL32!DuplicateHandle` at `0x14005f9cf`
- `KERNEL32!ResumeThread` at `0x14005f917`
- `KERNEL32!ResumeThread` at `0x14005fa2f`
- `KERNEL32!ResumeThread` at `0x14005fa8e`
- `KERNEL32!ResumeThread` at `0x14005f917`
- `KERNEL32!ResumeThread` at `0x14005fa2f`
- `KERNEL32!ResumeThread` at `0x14005fa8e`
- `KERNEL32!SetProcessWorkingSetSize` at `0x14005f636`
- `KERNEL32!SetProcessWorkingSetSize` at `0x14005f636`
- `KERNEL32!GetProcessWorkingSetSize` at `0x14005f609`
- `KERNEL32!GetProcessWorkingSetSize` at `0x14005f609`
- `KERNEL32!WaitForSingleObject` at `0x14005f925`
- `KERNEL32!WaitForSingleObject` at `0x14005fa9c`
- `KERNEL32!WaitForSingleObject` at `0x14005f925`
- `KERNEL32!WaitForSingleObject` at `0x14005fa9c`
- `KERNEL32!SetThreadPriority` at `0x14005f735`
- `KERNEL32!SetThreadPriority` at `0x14005f735`
- `KERNEL32!GetPriorityClass` at `0x14005f652`
- `KERNEL32!GetPriorityClass` at `0x14005f652`
- `KERNEL32!GetCurrentProcess` at `0x14005f5f6`
- `KERNEL32!GetCurrentProcess` at `0x14005f627`
- `KERNEL32!GetCurrentProcess` at `0x14005f649`
- `KERNEL32!GetCurrentProcess` at `0x14005f65e`
- `KERNEL32!GetCurrentProcess` at `0x14005f994`
- `KERNEL32!GetCurrentProcess` at `0x14005f9aa`
- `KERNEL32!GetCurrentProcess` at `0x14005f5f6`
- `KERNEL32!GetCurrentProcess` at `0x14005f627`
- `KERNEL32!GetCurrentProcess` at `0x14005f649`
- `KERNEL32!GetCurrentProcess` at `0x14005f65e`
- `KERNEL32!GetCurrentProcess` at `0x14005f994`
- `KERNEL32!GetCurrentProcess` at `0x14005f9aa`
- `KERNEL32!SetPriorityClass` at `0x14005f66c`
- `KERNEL32!SetPriorityClass` at `0x14005f66c`
- `msvcrt!_beginthreadex` at `0x14005fa08`
- `msvcrt!_beginthreadex` at `0x14005fa08`

## string_xrefs

- `0x14005f1bb`: `MemCopy_128_SSE_UCW_BPF16K_NBT`
- `0x14005f5d8`: `>            Test in non-cached memory : YES`
- `0x14005f3dc`: `>                    Number of Threads : `
- `0x14005f793`: `Adjusted the priority of Memory Assessment thread to %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall WinSAT::MemAssessment1::Start(WinSAT::MemAssessment1 *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 *v6; // rbx
  unsigned __int64 **v7; // rax
  __int64 *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  struct MCFunctionMapStruct near **i; // rbx
  unsigned __int16 v21; // r9
  const unsigned __int16 *v22; // rax
  __int64 *v23; // rax
  __int64 *v24; // rax
  DWORD v25; // eax
  int *v26; // r15
  __int64 *v27; // rbx
  unsigned __int64 **v28; // rax
  __int64 *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  int *v33; // r15
  __int64 *v34; // rbx
  unsigned __int64 **v35; // rax
  __int64 *v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  char v40; // r15
  unsigned int v41; // ecx
  __int64 *v42; // rax
  __int64 *v43; // rax
  __int64 *v44; // rax
  __int64 *v45; // rax
  __int64 *v46; // rax
  __int64 v47; // rax
  __int64 *v48; // rax
  __int64 *v49; // rax
  __int64 *v50; // rbx
  unsigned __int64 **v51; // rax
  __int64 *v52; // rax
  __int64 *v53; // rax
  __int64 v54; // rax
  __int64 *v55; // rax
  __int64 *v56; // rax
  __int64 *v57; // rbx
  unsigned __int64 **v58; // rax
  __int64 *v59; // rax
  __int64 *v60; // rax
  __int64 v61; // rax
  __int64 *v62; // rax
  __int64 *v63; // rax
  __int64 *v64; // rax
  HANDLE CurrentProcess; // rax
  SIZE_T v66; // rbx
  HANDLE v67; // rax
  HANDLE v68; // rax
  HANDLE v69; // rax
  unsigned __int16 v70; // r9
  __int64 v71; // rdx
  int v72; // r8d
  const unsigned __int16 *v73; // rax
  __int64 *v74; // rax
  __int64 *v75; // rax
  __int64 *v76; // rax
  __int64 v77; // rax
  __int64 v78; // rcx
  HANDLE CurrentThread; // rax
  HANDLE v81; // rax
  int ThreadPriority; // eax
  unsigned __int64 v83; // rax
  void *v84; // rax
  char v85; // cl
  unsigned int v86; // ebx
  unsigned int v87; // eax
  void *v88; // r10
  __int64 v89; // rcx
  unsigned int v90; // ebx
  unsigned __int16 v91; // r9
  const unsigned __int16 *v92; // rax
  WCHAR *v93; // r9
  HANDLE v94; // rdi
  void *v95; // rbx
  HANDLE v96; // rax
  uintptr_t v97; // rax
  unsigned int v98; // ebx
  unsigned __int16 v99; // r9
  __int64 *v100; // rax
  __int64 *v101; // rax
  __int64 *v102; // rax
  __int64 v103; // rax
  __int64 v104; // rcx
  WinSAT::MemAssessment1 *v105; // rdi
  unsigned __int16 v106; // r9
  const unsigned __int16 *v107; // rax
  __int64 v108; // rbx
  __int64 *v109; // rax
  __int64 *v110; // rax
  __int64 *v111; // rax
  __int64 v112; // rax
  DWORD v113; // [rsp+40h] [rbp-4B8h] BYREF
  char v114; // [rsp+44h] [rbp-4B4h]
  unsigned int ThrdAddr; // [rsp+48h] [rbp-4B0h] BYREF
  __int64 v116; // [rsp+50h] [rbp-4A8h]
  ULONG_PTR MaximumWorkingSetSize; // [rsp+58h] [rbp-4A0h] BYREF
  void *v118; // [rsp+60h] [rbp-498h] BYREF
  ULONG_PTR MinimumWorkingSetSize; // [rsp+68h] [rbp-490h] BYREF
  WinSAT::MemAssessment1 *v120; // [rsp+70h] [rbp-488h]
  __int64 v121; // [rsp+78h] [rbp-480h]
  __int64 v122; // [rsp+80h] [rbp-478h]
  WCHAR Buffer[256]; // [rsp+90h] [rbp-468h] BYREF
  DWORD LastError; // [rsp+290h] [rbp-268h]
  char v125; // [rsp+294h] [rbp-264h]
  __int64 v126; // [rsp+298h] [rbp-260h]
  WCHAR v127[256]; // [rsp+2A0h] [rbp-258h] BYREF
  int v128; // [rsp+4A0h] [rbp-58h]
  char v129; // [rsp+4A4h] [rbp-54h]
  __int64 v130; // [rsp+4A8h] [rbp-50h]

  v3 = a3;
  v116 = a3;
  v120 = this;
  v121 = a2;
  v122 = a3;
  if ( *((_DWORD *)this + 14) == 4 )
  {
    *(_DWORD *)a2 = 4;
    goto LABEL_77;
  }
  if ( *((_DWORD *)this + 14) == 6 )
  {
    *(_DWORD *)a2 = 6;
LABEL_77:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a2 + 8);
    *(_BYTE *)(a2 + 16) = 0;
    goto LABEL_78;
  }
  if ( *((_BYTE *)this + 32) )
  {
    v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
           (__int64 *)(*((_QWORD *)this + 2) + 240LL),
           (__int64)L">              Block size specified as : ");
    v7 = (unsigned __int64 **)WSfx(&ThrdAddr, *((unsigned int *)this + 177));
    v8 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v6, v7);
    v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, "  (");
    v10 = std::basic_ostream<unsigned short>::operator<<(v9, *((_DWORD *)this + 177));
    v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, " bytes)");
    std::endl(v11);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&ThrdAddr);
    v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 2) + 240LL),
            (__int64)L">                      Max Sample Size : ");
    v13 = std::basic_ostream<unsigned short>::operator<<((__int64)v12, *((_DWORD *)this + 185));
    v14 = (__int64 *)std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, "\n");
    v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v14,
            (__int64)L">                Min Sample Block Size : ");
    v16 = std::basic_ostream<unsigned short>::operator<<((__int64)v15, *((_DWORD *)this + 186));
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v16, "\n");
    if ( *((_DWORD *)this + 178) != 64 )
    {
      v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              (__int64 *)(*((_QWORD *)this + 2) + 240LL),
              (__int64)L">      Destination offset specified as : ");
      v18 = std::basic_ostream<unsigned short>::operator<<((__int64)v17, *((_DWORD *)this + 178));
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, "\n");
    }
    std::basic_ostream<unsigned short>::flush(*((_QWORD *)this + 2) + 240LL);
  }
  if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank((char *)this + 728) )
  {
    if ( IsProcessorFeaturePresent(6u) )
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
        (__int64)this + 728,
        (__int64)L"MemCopy_128_SSE_UCW_BPF16K_NBT",
        v19);
      goto LABEL_10;
    }
    WinSAT::MemAssessment1::DoCleanUp(this);
    *((_DWORD *)this + 14) = 5;
    v22 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x6F1, 610, v21);
    WinSAT::OpStatus::SetResult(a2, *((unsigned int *)this + 14), v22, 0);
    v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 3) + 240LL),
            (__int64)L"ERROR: ");
    v24 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v23,
            (unsigned __int64 **)(a2 + 8));
    std::endl(v24);
LABEL_78:
    v104 = v3;
LABEL_79:
    CSmartPtr<mlib::MEvent>::Release(v104);
    return 1;
  }
LABEL_10:
  v113 = 0;
  for ( i = &MCFunctionMap; i[1]; i += 4 )
  {
    if ( i[2]
      && !(unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei((char *)this + 728)
      || !(unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::comparei((char *)this + 728) )
    {
      v25 = *((_DWORD *)i + 1);
      v113 = v25;
      goto LABEL_19;
    }
  }
  v25 = v113;
LABEL_19:
  v26 = (int *)((char *)this + 708);
  if ( (unsigned __int8)AlignDwordP2Up(*((unsigned int *)this + 177), (char *)this + 708, v25) && *((_BYTE *)this + 32) )
  {
    v27 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 2) + 240LL),
            (__int64)L">               Block size adjusted to : ");
    v28 = (unsigned __int64 **)WSfx(&ThrdAddr, (unsigned int)*v26);
    v29 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v27, v28);
    v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, "  (");
    v31 = std::basic_ostream<unsigned short>::operator<<(v30, *v26);
    v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v31, " bytes)");
    std::endl(v32);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&ThrdAddr);
  }
  v33 = (int *)((char *)this + 712);
  if ( (unsigned __int8)AlignDwordP2Up(*((unsigned int *)this + 178), (char *)this + 712, v113) && *((_BYTE *)this + 32) )
  {
    v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 2) + 240LL),
            (__int64)L">       Destination offset adjusted to : ");
    v35 = (unsigned __int64 **)WSfx(&ThrdAddr, (unsigned int)*v33);
    v36 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v34, v35);
    v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v36, "  (");
    v38 = std::basic_ostream<unsigned short>::operator<<(v37, *v33);
    v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v38, " bytes)");
    std::endl(v39);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&ThrdAddr);
  }
  if ( *((_BYTE *)this + 676) )
  {
    v40 = 1;
    *((_DWORD *)this + 17) = 1;
  }
  else
  {
    v41 = *(_DWORD *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)this + 40)
                    + 452);
    *((_DWORD *)this + 17) = v41;
    v40 = 1;
    if ( v41 > 0x40 )
      *((_DWORD *)this + 17) = 64;
  }
  if ( *((_BYTE *)this + 32) )
  {
    v42 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 2) + 240LL),
            (__int64)L">                    Number of Threads : ");
    v43 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v42, *((_DWORD *)this + 17));
    v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v43, (__int64)L"\n");
    v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v44,
            (__int64)L">                Page Size Granularity : ");
    v46 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, (__int64)L"0x");
    v113 = 4;
    v47 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v46, &v113);
    v48 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v47, *((_DWORD *)this + 18));
    *(_DWORD *)((char *)v48 + *(int *)(*v48 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v48 + *(int *)(*v48 + 4) + 88) = 32;
    *(__int64 *)((char *)v48 + *(int *)(*v48 + 4) + 40) = 0;
    v49 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, (__int64)L"\n");
    v50 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v49,
            (__int64)L">                           Block Size : ");
    v51 = (unsigned __int64 **)WSfx(&v118, *((unsigned int *)this + 177));
    v52 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v50, v51);
    v53 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v52, (__int64)L" (0x");
    v113 = 4;
    v54 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v53, &v113);
    v55 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v54, *((_DWORD *)this + 177));
    *(_DWORD *)((char *)v55 + *(int *)(*v55 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v55 + *(int *)(*v55 + 4) + 88) = 32;
    *(__int64 *)((char *)v55 + *(int *)(*v55 + 4) + 40) = 0;
    v56 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, (__int64)L")\n");
    v57 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v56,
            (__int64)L">                   Destination Offset : ");
    v58 = (unsigned __int64 **)WSfx(&ThrdAddr, *((unsigned int *)this + 178));
    v59 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v57, v58);
    v60 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v59, (__int64)L" (0x");
    v113 = 4;
    v61 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v60, &v113);
    v62 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v61, *((_DWORD *)this + 178));
    *(_DWORD *)((char *)v62 + *(int *)(*v62 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v62 + *(int *)(*v62 + 4) + 88) = 32;
    *(__int64 *)((char *)v62 + *(int *)(*v62 + 4) + 40) = 0;
    v63 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v62, (__int64)L")");
    std::endl(v63);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&ThrdAddr);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v118);
    if ( *((_BYTE *)this + 736) )
    {
      v64 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              (__int64 *)(*((_QWORD *)this + 2) + 240LL),
              (__int64)L">            Test in non-cached memory : YES");
      std::endl(v64);
    }
  }
  MinimumWorkingSetSize = 0;
  MaximumWorkingSetSize = 0;
  CurrentProcess = GetCurrentProcess();
  GetProcessWorkingSetSize(CurrentProcess, &MinimumWorkingSetSize, &MaximumWorkingSetSize);
  v66 = MaximumWorkingSetSize
      + (unsigned int)(*((_DWORD *)this + 17) * (*((_DWORD *)this + 178) + 2 * *((_DWORD *)this + 177)));
  v67 = GetCurrentProcess();
  SetProcessWorkingSetSize(v67, v66, v66);
  if ( !*((_BYTE *)this + 737) )
  {
    v68 = GetCurrentProcess();
    *((_DWORD *)this + 181) = GetPriorityClass(v68);
    v69 = GetCurrentProcess();
    if ( !SetPriorityClass(v69, 0x80u) )
    {
      WinSAT::MemAssessment1::DoCleanUp(this);
      LastError = GetLastError();
      v125 = 1;
      v126 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v71 = 1902;
      v72 = 614;
LABEL_35:
      *((_DWORD *)this + 14) = 5;
      v73 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)v71, v72, v70);
      WinSAT::OpStatus::SetResult(a2, *((unsigned int *)this + 14), v73, Buffer);
      v74 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
              (__int64 *)(*((_QWORD *)this + 3) + 240LL),
              (unsigned __int64 **)(a2 + 8));
      v75 = (__int64 *)std::endl(v74);
      v76 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v75, a2 + 24);
      v77 = std::endl(v76);
      std::endl(v77);
      v78 = v3;
LABEL_36:
      CSmartPtr<mlib::MEvent>::Release(v78);
      return v40;
    }
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, 2) )
    {
      WinSAT::MemAssessment1::DoCleanUp(this);
      LastError = GetLastError();
      v125 = 1;
      v126 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      v71 = 1914;
      v72 = 615;
      goto LABEL_35;
    }
    v81 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v81);
    Log_Text_F(
      "base\\winsat\\memory\\memat.cpp",
      1920,
      "Adjusted the priority of Memory Assessment thread to %d",
      ThreadPriority);
  }
  v83 = 8LL * *((unsigned int *)this + 17);
  if ( !is_mul_ok(*((unsigned int *)this + 17), 8u) )
    v83 = -1;
  v84 = operator new[](v83, (const struct std::nothrow_t *)std::nothrow);
  *((_QWORD *)this + 10) = v84;
  if ( !v84 )
  {
    WinSAT::MemAssessment1::DoCleanUp(this);
    LastError = 8;
    v125 = 1;
    v126 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    v71 = 1935;
    v72 = 616;
    goto LABEL_35;
  }
  memset_0(v84, 0, 8LL * *((unsigned int *)this + 17));
  v85 = 1;
  v114 = 1;
  v113 = 0;
  v86 = 0;
  while ( 1 )
  {
    v87 = *((_DWORD *)this + 17);
    if ( v86 >= v87 )
      break;
    try
    {
      v88 = operator new(0x3B8u);
      v118 = v88;
      if ( v88 )
        v89 = WinSAT::OpMem1Thread::OpMem1Thread(
                (__int64)v88,
                v86,
                *((unsigned int *)this + 177),
                *((unsigned int *)this + 178),
                (__int64)this + 608,
                *((_QWORD *)this + 2),
                *((_QWORD *)this + 3),
                (__int64)this);
      else
        v89 = 0;
      *(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v86) = v89;
      if ( WinSAT::OpMem1Thread::CreateThread(
             *(WinSAT::OpMem1Thread **)(*((_QWORD *)this + 10) + 8LL * v86),
             (unsigned int)(1 << v86),
             (void **)this + v86 + 12,
             v86) )
      {
        v113 = GetLastError();
        v85 = 0;
        v114 = 0;
      }
      else
      {
        v85 = v114;
      }
      ++v86;
    }
    catch ( ... )
    {
      v105 = v120;
      WinSAT::MemAssessment1::DoCleanUp(v120);
      v128 = 8;
      v129 = 1;
      v130 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(v127);
      *((_DWORD *)v105 + 14) = 5;
      v107 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x7AD, 616, v106);
      v108 = v121;
      WinSAT::OpStatus::SetResult(v121, *((unsigned int *)v105 + 14), v107, v127);
      v109 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
               (__int64 *)(*((_QWORD *)v105 + 3) + 240LL),
               (unsigned __int64 **)(v108 + 8));
      v110 = (__int64 *)std::endl(v109);
      v111 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v110, v108 + 24);
      v112 = std::endl(v111);
      std::endl(v112);
      v104 = v122;
      goto LABEL_79;
    }
  }
  if ( !v85 )
  {
    v90 = 0;
    if ( v87 )
    {
      do
      {
        if ( (unsigned __int64)(*((_QWORD *)this + v90 + 12) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v90) + 116LL) = 1;
          ResumeThread(*((HANDLE *)this + v90 + 12));
          WaitForSingleObject(*((HANDLE *)this + v90 + 12), 0xFFFFFFFF);
        }
        ++v90;
      }
      while ( v90 < *((_DWORD *)this + 17) );
    }
    WinSAT::MemAssessment1::DoCleanUp(this);
    LastError = v113;
    v125 = 1;
    v126 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    *((_DWORD *)this + 14) = 5;
    v92 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x7D0, 617, v91);
    v93 = Buffer;
LABEL_73:
    WinSAT::OpStatus::SetResult(a2, *((unsigned int *)this + 14), v92, v93);
    v100 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 3) + 240LL),
             (unsigned __int64 **)(a2 + 8));
    v101 = (__int64 *)std::endl(v100);
    v102 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v101, a2 + 24);
    v103 = std::endl(v102);
    std::endl(v103);
    goto LABEL_74;
  }
  if ( *(_QWORD *)(v3 + 8) )
  {
    v94 = GetCurrentProcess();
    v95 = *(void **)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(v116);
    v96 = GetCurrentProcess();
    if ( !DuplicateHandle(v96, v95, v94, (LPHANDLE)this + 11, 0, 0, 2u) )
    {
      v40 = 0;
LABEL_74:
      v78 = v116;
      goto LABEL_36;
    }
    v3 = v116;
  }
  ThrdAddr = 0;
  v97 = _beginthreadex(0, 0, WinSAT::MemAssessment1::WaitForCompletionThread, this, 0, &ThrdAddr);
  v98 = 0;
  if ( v97 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( *((_DWORD *)this + 17) )
    {
      do
      {
        if ( (unsigned __int64)(*((_QWORD *)this + v98 + 12) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * v98) + 116LL) = 1;
          ResumeThread(*((HANDLE *)this + v98 + 12));
          WaitForSingleObject(*((HANDLE *)this + v98 + 12), 0xFFFFFFFF);
        }
        ++v98;
      }
      while ( v98 < *((_DWORD *)this + 17) );
    }
    WinSAT::MemAssessment1::DoCleanUp(this);
    v128 = v113;
    v129 = 1;
    v130 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(v127);
    *((_DWORD *)this + 14) = 5;
    v92 = mlib::MUIStr_((mlib *)"base\\winsat\\memory\\memat.cpp", (const char *)0x811, 618, v99);
    v93 = v127;
    goto LABEL_73;
  }
  *((_QWORD *)this + 81) = v97;
  if ( *((_DWORD *)this + 17) )
  {
    do
      ResumeThread(*((HANDLE *)this + v98++ + 12));
    while ( v98 < *((_DWORD *)this + 17) );
  }
  *((_DWORD *)this + 14) = 4;
  *(_DWORD *)a2 = 4;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(a2 + 8);
  *(_BYTE *)(a2 + 16) = 0;
  CSmartPtr<mlib::MEvent>::Release(v3);
  return 0;
}

```

## disassembly

```asm
0x14005f020  push    rbx
0x14005f022  push    rsi
0x14005f023  push    rdi
0x14005f024  push    r12
0x14005f026  push    r13
0x14005f028  push    r14
0x14005f02a  push    r15
0x14005f02c  sub     rsp, 4C0h
0x14005f033  mov     rax, cs:__security_cookie
0x14005f03a  xor     rax, rsp
0x14005f03d  mov     [rsp+4F8h+var_48], rax
0x14005f045  mov     rdi, r8
0x14005f048  mov     [rsp+4F8h+var_4A8], r8
0x14005f04d  mov     r12, rdx
0x14005f050  mov     rsi, rcx
0x14005f053  mov     [rsp+4F8h+var_488], rcx
0x14005f058  mov     [rsp+4F8h+var_480], rdx
0x14005f05d  mov     [rsp+4F8h+var_478], r8
0x14005f065  cmp     dword ptr [rcx+38h], 4
0x14005f069  jz      loc_14005FB61
0x14005f06f  cmp     dword ptr [rcx+38h], 6
0x14005f073  jz      loc_14005FB59
0x14005f079  xor     r14d, r14d
0x14005f07c  mov     r13d, 0F0h
0x14005f082  cmp     [rcx+20h], r14b
0x14005f086  jz      loc_14005F199
0x14005f08c  mov     rcx, [rcx+10h]
0x14005f090  add     rcx, r13
0x14005f093  lea     rdx, aBlockSizeSpeci; ">              Block size specified as "...
0x14005f09a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f09f  mov     rbx, rax
0x14005f0a2  mov     edx, [rsi+2C4h]
0x14005f0a8  lea     rcx, [rsp+4F8h+ThrdAddr]
0x14005f0ad  call    WSfx
0x14005f0b2  nop
0x14005f0b3  mov     rdx, rax
0x14005f0b6  mov     rcx, rbx
0x14005f0b9  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005f0be  mov     rcx, rax
0x14005f0c1  lea     rdx, asc_14013ECEC; "  ("
0x14005f0c8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f0cd  mov     edx, [rsi+2C4h]
0x14005f0d3  mov     rcx, rax
0x14005f0d6  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f0db  mov     rcx, rax
0x14005f0de  lea     rdx, aBytes_6; " bytes)"
0x14005f0e5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f0ea  mov     rcx, rax
0x14005f0ed  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005f0f2  nop
0x14005f0f3  lea     rcx, [rsp+4F8h+ThrdAddr]
0x14005f0f8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005f0fd  mov     rcx, [rsi+10h]
0x14005f101  add     rcx, r13
0x14005f104  lea     rdx, aMaxSampleSize; ">                      Max Sample Size "...
0x14005f10b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f110  mov     edx, [rsi+2E4h]
0x14005f116  mov     rcx, rax
0x14005f119  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f11e  mov     rcx, rax
0x14005f121  lea     rbx, asc_14012B93C; "\n"
0x14005f128  mov     rdx, rbx
0x14005f12b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f130  mov     rcx, rax
0x14005f133  lea     rdx, aMinSampleBlock; ">                Min Sample Block Size "...
0x14005f13a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f13f  mov     edx, [rsi+2E8h]
0x14005f145  mov     rcx, rax
0x14005f148  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f14d  mov     rcx, rax
0x14005f150  mov     rdx, rbx
0x14005f153  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f158  cmp     dword ptr [rsi+2C8h], 40h ; '@'
0x14005f15f  jz      short loc_14005F18D
0x14005f161  mov     rcx, [rsi+10h]
0x14005f165  add     rcx, r13
0x14005f168  lea     rdx, aDestinationOff; ">      Destination offset specified as "...
0x14005f16f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f174  mov     edx, [rsi+2C8h]
0x14005f17a  mov     rcx, rax
0x14005f17d  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f182  mov     rcx, rax
0x14005f185  mov     rdx, rbx
0x14005f188  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f18d  mov     rcx, [rsi+10h]
0x14005f191  add     rcx, r13
0x14005f194  call    ?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x14005f199  lea     r15, [rsi+2D8h]
0x14005f1a0  mov     rcx, r15
0x14005f1a3  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x14005f1a8  test    al, al
0x14005f1aa  jz      short loc_14005F1CA
0x14005f1ac  mov     ecx, 6; ProcessorFeature
0x14005f1b1  call    cs:__imp_IsProcessorFeaturePresent
0x14005f1b7  test    eax, eax
0x14005f1b9  jz      short loc_14005F20B
0x14005f1bb  lea     rdx, aMemcopy128SseU; "MemCopy_128_SSE_UCW_BPF16K_NBT"
0x14005f1c2  mov     rcx, r15
0x14005f1c5  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x14005f1ca  mov     [rsp+4F8h+var_4B8], r14d
0x14005f1cf  lea     rbx, ?MCFunctionMap@@3PAUMCFunctionMapStruct@@A; MCFunctionMapStruct near * MCFunctionMap
0x14005f1d6  cmp     [rbx+8], r14
0x14005f1da  jz      loc_14005F278
0x14005f1e0  mov     rdx, [rbx+10h]
0x14005f1e4  test    rdx, rdx
0x14005f1e7  jz      short loc_14005F1F5
0x14005f1e9  mov     rcx, r15
0x14005f1ec  call    ?comparei@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBAHPEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::comparei(ushort const *)
0x14005f1f1  test    eax, eax
0x14005f1f3  jz      short loc_14005F26F
0x14005f1f5  mov     rdx, [rbx+8]
0x14005f1f9  mov     rcx, r15
0x14005f1fc  call    ?comparei@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBAHPEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::comparei(ushort const *)
0x14005f201  test    eax, eax
0x14005f203  jz      short loc_14005F26F
0x14005f205  add     rbx, 20h ; ' '
0x14005f209  jmp     short loc_14005F1D6
0x14005f20b  mov     rcx, rsi; this
0x14005f20e  call    ?DoCleanUp@MemAssessment1@WinSAT@@AEAAXXZ; WinSAT::MemAssessment1::DoCleanUp(void)
0x14005f213  mov     dword ptr [rsi+38h], 5
0x14005f21a  mov     edx, 6F1h; char *
0x14005f21f  mov     r8d, 262h; int
0x14005f225  lea     rcx, aBaseWinsatMemo; "base\\winsat\\memory\\memat.cpp"
0x14005f22c  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14005f231  xor     r9d, r9d
0x14005f234  mov     r8, rax
0x14005f237  mov     edx, [rsi+38h]
0x14005f23a  mov     rcx, r12
0x14005f23d  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGK@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,ulong)
0x14005f242  mov     rcx, [rsi+18h]
0x14005f246  add     rcx, r13
0x14005f249  lea     rdx, aError_2; "ERROR: "
0x14005f250  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f255  lea     rdx, [r12+8]
0x14005f25a  mov     rcx, rax
0x14005f25d  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005f262  mov     rcx, rax
0x14005f265  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005f26a  jmp     loc_14005FB78
0x14005f26f  mov     eax, [rbx+4]
0x14005f272  mov     [rsp+4F8h+var_4B8], eax
0x14005f276  jmp     short loc_14005F27C
0x14005f278  mov     eax, [rsp+4F8h+var_4B8]
0x14005f27c  lea     r15, [rsi+2C4h]
0x14005f283  mov     r8d, eax
0x14005f286  mov     rdx, r15
0x14005f289  mov     ecx, [r15]
0x14005f28c  call    AlignDwordP2Up
0x14005f291  test    al, al
0x14005f293  jz      short loc_14005F306
0x14005f295  cmp     [rsi+20h], r14b
0x14005f299  jz      short loc_14005F306
0x14005f29b  mov     rcx, [rsi+10h]
0x14005f29f  add     rcx, r13
0x14005f2a2  lea     rdx, aBlockSizeAdjus; ">               Block size adjusted to "...
0x14005f2a9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f2ae  mov     rbx, rax
0x14005f2b1  mov     edx, [r15]
0x14005f2b4  lea     rcx, [rsp+4F8h+ThrdAddr]
0x14005f2b9  call    WSfx
0x14005f2be  nop
0x14005f2bf  mov     rdx, rax
0x14005f2c2  mov     rcx, rbx
0x14005f2c5  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005f2ca  mov     rcx, rax
0x14005f2cd  lea     rdx, asc_14013ECEC; "  ("
0x14005f2d4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f2d9  mov     edx, [r15]
0x14005f2dc  mov     rcx, rax
0x14005f2df  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f2e4  mov     rcx, rax
0x14005f2e7  lea     rdx, aBytes_6; " bytes)"
0x14005f2ee  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f2f3  mov     rcx, rax
0x14005f2f6  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005f2fb  nop
0x14005f2fc  lea     rcx, [rsp+4F8h+ThrdAddr]
0x14005f301  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005f306  lea     r15, [rsi+2C8h]
0x14005f30d  mov     r8d, [rsp+4F8h+var_4B8]
0x14005f312  mov     rdx, r15
0x14005f315  mov     ecx, [r15]
0x14005f318  call    AlignDwordP2Up
0x14005f31d  test    al, al
0x14005f31f  jz      short loc_14005F392
0x14005f321  cmp     [rsi+20h], r14b
0x14005f325  jz      short loc_14005F392
0x14005f327  mov     rcx, [rsi+10h]
0x14005f32b  add     rcx, r13
0x14005f32e  lea     rdx, aDestinationOff_1; ">       Destination offset adjusted to "...
0x14005f335  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f33a  mov     rbx, rax
0x14005f33d  mov     edx, [r15]
0x14005f340  lea     rcx, [rsp+4F8h+ThrdAddr]
0x14005f345  call    WSfx
0x14005f34a  nop
0x14005f34b  mov     rdx, rax
0x14005f34e  mov     rcx, rbx
0x14005f351  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005f356  mov     rcx, rax
0x14005f359  lea     rdx, asc_14013ECEC; "  ("
0x14005f360  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f365  mov     edx, [r15]
0x14005f368  mov     rcx, rax
0x14005f36b  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f370  mov     rcx, rax
0x14005f373  lea     rdx, aBytes_6; " bytes)"
0x14005f37a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14005f37f  mov     rcx, rax
0x14005f382  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14005f387  nop
0x14005f388  lea     rcx, [rsp+4F8h+ThrdAddr]
0x14005f38d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14005f392  cmp     [rsi+2A4h], r14b
0x14005f399  jz      short loc_14005F3A7
0x14005f39b  mov     r15d, 1
0x14005f3a1  mov     [rsi+44h], r15d
0x14005f3a5  jmp     short loc_14005F3CB
0x14005f3a7  lea     rcx, [rsi+28h]
0x14005f3ab  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14005f3b0  mov     ecx, [rax+1C4h]
0x14005f3b6  mov     [rsi+44h], ecx
0x14005f3b9  mov     r15d, 1
0x14005f3bf  cmp     ecx, 40h ; '@'
0x14005f3c2  jbe     short loc_14005F3CB
0x14005f3c4  mov     dword ptr [rsi+44h], 40h ; '@'
0x14005f3cb  cmp     [rsi+20h], r14b
0x14005f3cf  jz      loc_14005F5EC
0x14005f3d5  mov     rcx, [rsi+10h]
0x14005f3d9  add     rcx, r13
0x14005f3dc  lea     rdx, aNumberOfThread; ">                    Number of Threads "...
0x14005f3e3  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f3e8  mov     edx, [rsi+44h]
0x14005f3eb  mov     rcx, rax
0x14005f3ee  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f3f3  mov     rcx, rax
0x14005f3f6  lea     rdx, asc_14012B970; "\n"
0x14005f3fd  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f402  mov     rcx, rax
0x14005f405  lea     rdx, aPageSizeGranul; ">                Page Size Granularity "...
0x14005f40c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f411  mov     rcx, rax
0x14005f414  lea     rdx, a0x; "0x"
0x14005f41b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f420  mov     [rsp+4F8h+var_4B8], 4
0x14005f428  lea     rdx, [rsp+4F8h+var_4B8]
0x14005f42d  mov     rcx, rax
0x14005f430  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x14005f435  mov     edx, [rsi+48h]
0x14005f438  mov     rcx, rax
0x14005f43b  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f440  mov     rcx, [rax]
0x14005f443  movsxd  r8, dword ptr [rcx+4]
0x14005f447  or      dword ptr [r8+rax+18h], 201h
0x14005f450  mov     rcx, [rax]
0x14005f453  movsxd  r8, dword ptr [rcx+4]
0x14005f457  mov     word ptr [r8+rax+58h], 20h ; ' '
0x14005f45f  mov     rcx, [rax]
0x14005f462  movsxd  r8, dword ptr [rcx+4]
0x14005f466  mov     [r8+rax+28h], r14
0x14005f46b  lea     rdx, asc_14012B970; "\n"
0x14005f472  mov     rcx, rax
0x14005f475  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f47a  mov     rcx, rax
0x14005f47d  lea     rdx, aBlockSize_0; ">                           Block Size "...
0x14005f484  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f489  mov     rbx, rax
0x14005f48c  mov     edx, [rsi+2C4h]
0x14005f492  lea     rcx, [rsp+4F8h+var_498]
0x14005f497  call    WSfx
0x14005f49c  nop
0x14005f49d  mov     rdx, rax
0x14005f4a0  mov     rcx, rbx
0x14005f4a3  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x14005f4a8  mov     rcx, rax
0x14005f4ab  lea     rdx, a0x_0; " (0x"
0x14005f4b2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f4b7  mov     [rsp+4F8h+var_4B8], 4
0x14005f4bf  lea     rdx, [rsp+4F8h+var_4B8]
0x14005f4c4  mov     rcx, rax
0x14005f4c7  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x14005f4cc  mov     edx, [rsi+2C4h]
0x14005f4d2  mov     rcx, rax
0x14005f4d5  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x14005f4da  mov     rcx, [rax]
0x14005f4dd  movsxd  rdx, dword ptr [rcx+4]
0x14005f4e1  or      dword ptr [rdx+rax+18h], 201h
0x14005f4e9  mov     rcx, [rax]
0x14005f4ec  movsxd  rdx, dword ptr [rcx+4]
0x14005f4f0  mov     word ptr [rdx+rax+58h], 20h ; ' '
0x14005f4f7  mov     rcx, [rax]
0x14005f4fa  movsxd  rdx, dword ptr [rcx+4]
0x14005f4fe  mov     [rdx+rax+28h], r14
0x14005f503  lea     rdx, asc_14013DF14; ")\n"
0x14005f50a  mov     rcx, rax
0x14005f50d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f512  mov     rcx, rax
0x14005f515  lea     rdx, aDestinationOff_0; ">                   Destination Offset "...
0x14005f51c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14005f521  mov     rbx, rax
  ... truncated ...
```
