# WinSAT::CompressionWorkload::SetupWorkload(void)

- ea: `0x140078e90`
- end: `0x140079659`
- name: `?SetupWorkload@CompressionWorkload@WinSAT@@MEAAKXZ`
- size: `1993`
- prototype: `unsigned int __fastcall(WinSAT::CompressionWorkload *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400040d0`
- `0x140004348`
- `0x14000449c`
- `0x140005f10`
- `0x140007f14`
- `0x140008178`
- `0x1400085b4`
- `0x140011f58`
- `0x140016d04`
- `0x140017af0`
- `0x14001827c`
- `0x1400219d0`
- `0x14003a150`
- `0x14003ec14`
- `0x14004fce4`
- `0x1400530a8`
- `0x1400584b0`
- `0x14005ef98`
- `0x14007066c`
- `0x140076b98`
- `0x140078b6c`
- `0x140078e90`
- `0x1400796f8`
- `0x140113220`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140078f4f`
- `KERNEL32!EnterCriticalSection` at `0x140079072`
- `KERNEL32!EnterCriticalSection` at `0x1400791d6`
- `KERNEL32!EnterCriticalSection` at `0x140078f4f`
- `KERNEL32!EnterCriticalSection` at `0x140079072`
- `KERNEL32!EnterCriticalSection` at `0x1400791d6`
- `KERNEL32!LeaveCriticalSection` at `0x140078f8e`
- `KERNEL32!LeaveCriticalSection` at `0x1400790b1`
- `KERNEL32!LeaveCriticalSection` at `0x14007961f`
- `KERNEL32!LeaveCriticalSection` at `0x140078f8e`
- `KERNEL32!LeaveCriticalSection` at `0x1400790b1`
- `KERNEL32!LeaveCriticalSection` at `0x14007961f`
- `KERNEL32!GetCurrentThreadId` at `0x140079237`
- `KERNEL32!GetCurrentThreadId` at `0x140079237`
- `KERNEL32!GetThreadPriority` at `0x140078ed4`
- `KERNEL32!GetThreadPriority` at `0x140078fd5`
- `KERNEL32!GetThreadPriority` at `0x140078ed4`
- `KERNEL32!GetThreadPriority` at `0x140078fd5`
- `KERNEL32!GetCurrentThread` at `0x140078ecb`
- `KERNEL32!GetCurrentThread` at `0x140078ee9`
- `KERNEL32!GetCurrentThread` at `0x140078fcc`
- `KERNEL32!GetCurrentThread` at `0x140078ecb`
- `KERNEL32!GetCurrentThread` at `0x140078ee9`
- `KERNEL32!GetCurrentThread` at `0x140078fcc`
- `KERNEL32!GetLastError` at `0x140078f02`
- `KERNEL32!GetLastError` at `0x140078f02`
- `KERNEL32!Sleep` at `0x140078fc6`
- `KERNEL32!Sleep` at `0x140078fc6`
- `KERNEL32!SetThreadPriority` at `0x140078ef4`
- `KERNEL32!SetThreadPriority` at `0x140078ef4`
- `KERNEL32!SetLastError` at `0x140078fb0`
- `KERNEL32!SetLastError` at `0x1400790cd`
- `KERNEL32!SetLastError` at `0x140078fb0`
- `KERNEL32!SetLastError` at `0x1400790cd`

## string_xrefs

- `0x140078fde`: `CPU Compression thread priority changed to %d`
- `0x140078eda`: `base\winsat\cpu\compression.cpp`
- `0x1400792c1`: `\n  -- Uncompressed Buffer Size =`
- `0x1400793b5`: `\n  -- Compressed Buffer Size =`
- `0x1400795d5`: `-- Thread Error   & `
- `0x1400795af`: `-- Completion Ctr & `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall WinSAT::CompressionWorkload::SetupWorkload(WinSAT::CompressionWorkload *this)
{
  int v2; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v4; // rax
  const unsigned __int16 *v5; // rbx
  __int64 *v6; // rax
  __int64 *v7; // rax
  __int64 *v8; // rax
  HANDLE v10; // rax
  int ThreadPriority; // eax
  unsigned int v12; // ecx
  unsigned int v13; // eax
  DWORD v14; // eax
  DWORD v15; // esi
  const unsigned __int16 *v16; // rbx
  __int64 *v17; // rax
  __int64 *v18; // rax
  __int64 *v19; // rax
  DWORD flProtect; // esi
  int RB; // eax
  int v22; // edx
  int v23; // ebx
  __int64 *v24; // rax
  int v25; // ebx
  __int64 *v26; // rax
  __int64 *v27; // rax
  __int64 *v28; // rax
  __int64 *v29; // rax
  __int64 v30; // rbx
  DWORD CurrentThreadId; // eax
  __int64 *v32; // rax
  __int64 *v33; // rax
  const wchar_t *v34; // rdx
  __int64 *v35; // rax
  __int64 *v36; // rax
  __int64 *v37; // rax
  __int64 *v38; // rax
  __int64 *v39; // rax
  __int64 v40; // rax
  __int64 *v41; // rax
  __int64 *v42; // rax
  __int64 *v43; // rax
  __int64 *v44; // rax
  __int64 *v45; // rax
  __int64 *v46; // rax
  __int64 *v47; // rax
  __int64 *v48; // rax
  __int64 *v49; // rax
  __int64 *v50; // rax
  __int64 *v51; // rax
  __int64 v52; // rax
  __int64 *v53; // rax
  __int64 *v54; // rax
  __int64 *v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 *v58; // rax
  __int64 *v59; // rax
  __int64 v60; // rbx
  mlib *v61; // rcx
  unsigned __int64 PerformanceFrequency64; // rax
  __int64 *v63; // rax
  __int64 v64; // rax
  __int64 *v65; // rax
  __int64 *v66; // rax
  __int64 v67; // rax
  __int64 *v68; // rax
  __int64 *v69; // rax
  __int64 v70; // rax
  __int64 *v71; // rax
  __int64 *v72; // rax
  __int64 v73; // rax
  __int64 *v74; // rax
  __int64 *v75; // rax
  __int64 v76; // rax
  __int64 *v77; // rax
  __int64 *v78; // rax
  __int64 v79; // rax
  int v80; // [rsp+28h] [rbp-D8h]
  int v81; // [rsp+28h] [rbp-D8h]
  __int64 v82[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwErrCode; // [rsp+250h] [rbp+150h]
  char v85; // [rsp+254h] [rbp+154h]
  __int64 v86; // [rsp+258h] [rbp+158h]

  v2 = *((_DWORD *)this + 192);
  CurrentThread = GetCurrentThread();
  if ( GetThreadPriority(CurrentThread) != v2 )
  {
    v4 = GetCurrentThread();
    if ( !SetThreadPriority(v4, v2) )
    {
      dwErrCode = GetLastError();
      v85 = 1;
      v86 = 0;
      mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
      _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
      v5 = mlib::MUISpf_((mlib *)"base\\winsat\\cpu\\compression.cpp", (const char *)0x9E, 500, *((_DWORD *)this + 22));
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             (__int64 *)(*((_QWORD *)this + 2) + 240LL),
             (__int64)v5);
      v7 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v6, 10);
      v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, (__int64)Buffer);
      std::endl(v8);
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
      WinSAT::OpStatus::SetResult((char *)this + 96, 5, v5, Buffer);
      SetLastError(dwErrCode);
      return dwErrCode;
    }
    Sleep(1u);
    v10 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v10);
    Log_Text_F(
      "base\\winsat\\cpu\\compression.cpp",
      180,
      "CPU Compression thread priority changed to %d",
      ThreadPriority);
  }
  v12 = *(_DWORD *)(*((_QWORD *)this + 106) + 8432LL);
  if ( !v12 )
    return 160;
  v13 = *((_DWORD *)this + 252) / v12;
  *((_DWORD *)this + 244) = v13;
  v14 = WinSAT::CompressionWorkload::SetupWorkSpace(this, v13);
  v15 = v14;
  if ( v14 )
  {
    dwErrCode = v14;
    v85 = 1;
    v86 = 0;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
    _InterlockedIncrement(*((volatile signed __int32 **)this + 4));
    v16 = mlib::MUISpf_((mlib *)"base\\winsat\\cpu\\compression.cpp", (const char *)0xCE, 501, *((_DWORD *)this + 22));
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 2) + 240LL),
            (__int64)v16);
    v18 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v17, 10);
    v19 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, (__int64)Buffer);
    std::endl(v19);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    WinSAT::OpStatus::SetResult((char *)this + 96, 5, v16, v15);
    SetLastError(v15);
    return v15;
  }
  flProtect = *(_BYTE *)(*((_QWORD *)this + 106) + 8377LL) != 0 ? 4 : 516;
  RB = RotatingBuffer::CreateRB(
         (WinSAT::CompressionWorkload *)((char *)this + 880),
         (__int64)this + 1024,
         v80,
         *((unsigned __int8 *)this + 1032),
         flProtect);
  if ( RB < 0 )
  {
    v22 = RB;
    return WinSAT::CompressionWorkload::DumpCreateRBError(this, v22);
  }
  v23 = *((unsigned __int8 *)this + 1032);
  v24 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v82);
  v25 = RotatingBuffer::CreateRB((WinSAT::CompressionWorkload *)((char *)this + 928), (__int64)v24, v81, v23, flProtect);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v82);
  if ( v25 < 0 )
  {
    v22 = v25;
    return WinSAT::CompressionWorkload::DumpCreateRBError(this, v22);
  }
  *((_DWORD *)this + 253) = *((_DWORD *)this + 244) + *((_DWORD *)this + 254);
  *((_QWORD *)this + 105) = *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(*((_QWORD *)this + 106) + 40LL);
  if ( *((_BYTE *)this + 24) )
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
    v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 1) + 240LL),
            (__int64)L"> CPU(");
    v27 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v26, *((_DWORD *)this + 22));
    v28 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v27, (__int64)L")  ");
    v29 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, (__int64)L"TID: ");
    LODWORD(v82[0]) = 4;
    v30 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v29, v82);
    CurrentThreadId = GetCurrentThreadId();
    v32 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v30, CurrentThreadId);
    *(_DWORD *)((char *)v32 + *(int *)(*v32 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v32 + *(int *)(*v32 + 4) + 88) = 32;
    *(__int64 *)((char *)v32 + *(int *)(*v32 + 4) + 40) = 0;
    v33 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, (__int64)L"\n  -- Running at ");
    v34 = L"NORMAL";
    if ( !*(_BYTE *)(*((_QWORD *)this + 106) + 8376LL) )
      v34 = L"HIGH";
    v35 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v33, (__int64)v34);
    v36 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, (__int64)L" priority");
    v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v36,
            (__int64)L"\n  -- Uncompressed Buffer Size =");
    v38 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v37, *((_DWORD *)this + 252));
    v39 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v38, (__int64)L" (0x");
    LODWORD(v82[0]) = 4;
    v40 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v39, v82);
    v41 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v40, *((_DWORD *)this + 252));
    *(_DWORD *)((char *)v41 + *(int *)(*v41 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v41 + *(int *)(*v41 + 4) + 88) = 32;
    *(__int64 *)((char *)v41 + *(int *)(*v41 + 4) + 40) = 0;
    v42 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v41, (__int64)L") bytes");
    v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v42, (__int64)L"\n  -- Num regions = ");
    v44 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(
                       (__int64)v43,
                       *(_DWORD *)(*((_QWORD *)this + 106) + 8432LL));
    v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, (__int64)L"   region size= ");
    v46 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(
                       (__int64)v45,
                       *((_DWORD *)this + 252) / *(_DWORD *)(*((_QWORD *)this + 106) + 8432LL));
    v47 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v46, (__int64)L"\n  -- Block Size = ");
    v48 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v47, *((_DWORD *)this + 244));
    v49 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            v48,
            (__int64)L"\n  -- Compressed Buffer Size =");
    v50 = (__int64 *)std::basic_ostream<unsigned short>::operator<<((__int64)v49, *((_DWORD *)this + 253));
    v51 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, (__int64)L" (0x");
    LODWORD(v82[0]) = 4;
    v52 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v51, v82);
    v53 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v52, *((_DWORD *)this + 253));
    *(_DWORD *)((char *)v53 + *(int *)(*v53 + 4) + 24) |= 0x201u;
    *(_WORD *)((char *)v53 + *(int *)(*v53 + 4) + 88) = 32;
    *(__int64 *)((char *)v53 + *(int *)(*v53 + 4) + 40) = 0;
    v54 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v53, (__int64)L") bytes");
    v55 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v54, (__int64)L"\n  -- Affinity Mask ");
    LODWORD(v82[0]) = 8;
    v56 = mlib::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, v82);
    v57 = std::basic_ostream<unsigned short>::operator<<(v56, *((_DWORD *)this + 194));
    *(_DWORD *)(*(int *)(*(_QWORD *)v57 + 4LL) + v57 + 24) |= 0x201u;
    *(_WORD *)(*(int *)(*(_QWORD *)v57 + 4LL) + v57 + 88) = 32;
    *(_QWORD *)(*(int *)(*(_QWORD *)v57 + 4LL) + v57 + 40) = 0;
    std::basic_ostream<unsigned short>::operator<<(v57, 10);
    v58 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 1) + 240LL),
            (__int64)L"> Populate From '");
    v59 = mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v58,
            (unsigned __int64 **)this + 128);
    std::basic_ostream<unsigned short>::operator<<(v59, 10);
    v60 = *((_QWORD *)this + 1);
    PerformanceFrequency64 = mlib::QueryPerformanceFrequency64(v61);
    mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
      v60,
      L"\n  -- Performance Counter Frequency     = %11I64u",
      PerformanceFrequency64);
    mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
      *((_QWORD *)this + 1),
      L"\n  -- CPU Time Stamp Freq               = %11I64u",
      *((_QWORD *)this + 105));
    mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
      *((_QWORD *)this + 1),
      L"\n  -- Time Stamp Counts Per millisecond = %11I64u\n",
      *((_QWORD *)this + 105) / 0x3E8uLL);
    std::basic_ostream<unsigned short>::flush(*((_QWORD *)this + 1) + 240LL);
    v63 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(*((_QWORD *)this + 1) + 240LL),
            (__int64)L"-- Cancel Flag    & ");
    v64 = std::basic_ostream<unsigned short>::operator<<(v63, *((_QWORD *)this + 4));
    v65 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v64, 10);
    v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, (__int64)L"-- Spin Lock-E    & ");
    v67 = std::basic_ostream<unsigned short>::operator<<(v66, *((_QWORD *)this + 5));
    v68 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v67, 10);
    v69 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v68, (__int64)L"-- Spin Lock-L    & ");
    v70 = std::basic_ostream<unsigned short>::operator<<(v69, *((_QWORD *)this + 6));
    v71 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v70, 10);
    v72 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v71, (__int64)L"-- Completion Ctr & ");
    v73 = std::basic_ostream<unsigned short>::operator<<(v72, *((_QWORD *)this + 7));
    v74 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v73, 10);
    v75 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v74, (__int64)L"-- Thread Error   & ");
    v76 = std::basic_ostream<unsigned short>::operator<<(v75, *((_QWORD *)this + 8));
    v77 = (__int64 *)std::basic_ostream<unsigned short>::operator<<(v76, 10);
    v78 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v77, (__int64)L"-- Sleep Tick     & ");
    v79 = std::basic_ostream<unsigned short>::operator<<(v78, *((_QWORD *)this + 9));
    std::endl(v79);
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 10));
  }
  return 0;
}

```

## disassembly

```asm
0x140078e90  mov     [rsp-8+arg_8], rbx
0x140078e95  mov     [rsp-8+arg_10], rsi
0x140078e9a  push    rbp
0x140078e9b  push    rdi
0x140078e9c  push    r12
0x140078e9e  push    r14
0x140078ea0  push    r15
0x140078ea2  lea     rbp, [rsp-170h]
0x140078eaa  sub     rsp, 270h
0x140078eb1  mov     rax, cs:__security_cookie
0x140078eb8  xor     rax, rsp
0x140078ebb  mov     [rbp+190h+var_30], rax
0x140078ec2  mov     rdi, rcx
0x140078ec5  mov     ebx, [rcx+300h]
0x140078ecb  call    cs:__imp_GetCurrentThread
0x140078ed1  mov     rcx, rax; hThread
0x140078ed4  call    cs:__imp_GetThreadPriority
0x140078eda  lea     r14, aBaseWinsatCpuC_0; "base\\winsat\\cpu\\compression.cpp"
0x140078ee1  cmp     eax, ebx
0x140078ee3  jz      loc_140078FF2
0x140078ee9  call    cs:__imp_GetCurrentThread
0x140078eef  mov     edx, ebx; nPriority
0x140078ef1  mov     rcx, rax; hThread
0x140078ef4  call    cs:__imp_SetThreadPriority
0x140078efa  test    eax, eax
0x140078efc  jnz     loc_140078FC1
0x140078f02  call    cs:__imp_GetLastError
0x140078f08  mov     [rbp+190h+dwErrCode], eax
0x140078f0e  mov     [rbp+190h+var_3C], 1
0x140078f15  mov     [rbp+190h+var_38], 0
0x140078f20  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x140078f25  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140078f2a  mov     rax, [rdi+20h]
0x140078f2e  lock inc dword ptr [rax]
0x140078f31  mov     r8d, 1F4h; int
0x140078f37  mov     r9d, [rdi+58h]; unsigned __int16
0x140078f3b  mov     edx, 9Eh; char *
0x140078f40  mov     rcx, r14; this
0x140078f43  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x140078f48  mov     rbx, rax
0x140078f4b  mov     rcx, [rdi+50h]; lpCriticalSection
0x140078f4f  call    cs:__imp_EnterCriticalSection
0x140078f55  mov     rcx, [rdi+10h]
0x140078f59  add     rcx, 0F0h
0x140078f60  mov     rdx, rbx
0x140078f63  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140078f68  mov     edx, 0Ah
0x140078f6d  mov     rcx, rax
0x140078f70  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140078f75  lea     rdx, [rsp+290h+Buffer]
0x140078f7a  mov     rcx, rax
0x140078f7d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140078f82  mov     rcx, rax
0x140078f85  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140078f8a  mov     rcx, [rdi+50h]; lpCriticalSection
0x140078f8e  call    cs:__imp_LeaveCriticalSection
0x140078f94  lea     rcx, [rdi+60h]
0x140078f98  lea     r9, [rsp+290h+Buffer]
0x140078f9d  mov     r8, rbx
0x140078fa0  mov     edx, 5
0x140078fa5  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGAEBV?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>> const &)
0x140078faa  mov     ecx, [rbp+190h+dwErrCode]; dwErrCode
0x140078fb0  call    cs:__imp_SetLastError
0x140078fb6  mov     eax, [rbp+190h+dwErrCode]
0x140078fbc  jmp     loc_14007962E
0x140078fc1  mov     ecx, 1; dwMilliseconds
0x140078fc6  call    cs:__imp_Sleep
0x140078fcc  call    cs:__imp_GetCurrentThread
0x140078fd2  mov     rcx, rax; hThread
0x140078fd5  call    cs:__imp_GetThreadPriority
0x140078fdb  mov     r9d, eax
0x140078fde  lea     r8, aCpuCompression_0; "CPU Compression thread priority changed"...
0x140078fe5  mov     edx, 0B4h
0x140078fea  mov     rcx, r14
0x140078fed  call    Log_Text_F
0x140078ff2  mov     rax, [rdi+350h]
0x140078ff9  mov     ecx, [rax+20F0h]
0x140078fff  test    ecx, ecx
0x140079001  jz      loc_140079629
0x140079007  xor     edx, edx
0x140079009  mov     eax, [rdi+3F0h]
0x14007900f  div     ecx
0x140079011  mov     [rdi+3D0h], eax
0x140079017  mov     edx, eax; unsigned int
0x140079019  mov     rcx, rdi; this
0x14007901c  call    ?SetupWorkSpace@CompressionWorkload@WinSAT@@AEAAKK@Z; WinSAT::CompressionWorkload::SetupWorkSpace(ulong)
0x140079021  mov     esi, eax
0x140079023  test    eax, eax
0x140079025  jz      loc_1400790DA
0x14007902b  mov     [rbp+190h+dwErrCode], eax
0x140079031  mov     [rbp+190h+var_3C], 1
0x140079038  mov     [rbp+190h+var_38], 0
0x140079043  lea     rcx, [rsp+290h+Buffer]; lpBuffer
0x140079048  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14007904d  mov     rcx, [rdi+20h]
0x140079051  lock inc dword ptr [rcx]
0x140079054  mov     r8d, 1F5h; int
0x14007905a  mov     r9d, [rdi+58h]; unsigned __int16
0x14007905e  mov     edx, 0CEh; char *
0x140079063  mov     rcx, r14; this
0x140079066  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x14007906b  mov     rbx, rax
0x14007906e  mov     rcx, [rdi+50h]; lpCriticalSection
0x140079072  call    cs:__imp_EnterCriticalSection
0x140079078  mov     rcx, [rdi+10h]
0x14007907c  add     rcx, 0F0h
0x140079083  mov     rdx, rbx
0x140079086  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007908b  mov     edx, 0Ah
0x140079090  mov     rcx, rax
0x140079093  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x140079098  lea     rdx, [rsp+290h+Buffer]
0x14007909d  mov     rcx, rax
0x1400790a0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400790a5  mov     rcx, rax
0x1400790a8  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x1400790ad  mov     rcx, [rdi+50h]; lpCriticalSection
0x1400790b1  call    cs:__imp_LeaveCriticalSection
0x1400790b7  lea     rcx, [rdi+60h]
0x1400790bb  mov     r9d, esi
0x1400790be  mov     r8, rbx
0x1400790c1  mov     edx, 5
0x1400790c6  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGK@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,ulong)
0x1400790cb  mov     ecx, esi; dwErrCode
0x1400790cd  call    cs:__imp_SetLastError
0x1400790d3  mov     eax, esi
0x1400790d5  jmp     loc_14007962E
0x1400790da  mov     r8, [rdi+350h]
0x1400790e1  mov     al, [r8+20B9h]
0x1400790e8  neg     al
0x1400790ea  sbb     esi, esi
0x1400790ec  and     esi, 0FFFFFE00h
0x1400790f2  add     esi, 204h
0x1400790f8  lea     r12, [rdi+400h]
0x1400790ff  movzx   eax, byte ptr [rdi+408h]
0x140079106  lea     rcx, [rdi+370h]; this
0x14007910d  mov     [rsp+290h+flProtect], esi; flProtect
0x140079111  mov     [rsp+290h+var_260], eax; int
0x140079115  mov     [rsp+290h+var_270], r12; __int64
0x14007911a  xor     r9d, r9d
0x14007911d  mov     r8d, [r8+20F0h]
0x140079124  mov     edx, [rdi+3F0h]
0x14007912a  call    ?CreateRB@RotatingBuffer@@QEAAJKKKAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@HHK@Z; RotatingBuffer::CreateRB(ulong,ulong,ulong,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,int,int,ulong)
0x14007912f  test    eax, eax
0x140079131  jns     short loc_140079142
0x140079133  mov     edx, eax; int
0x140079135  mov     rcx, rdi; this
0x140079138  call    ?DumpCreateRBError@CompressionWorkload@WinSAT@@AEAAKJ@Z; WinSAT::CompressionWorkload::DumpCreateRBError(long)
0x14007913d  jmp     loc_14007962E
0x140079142  movzx   ebx, byte ptr [rdi+408h]
0x140079149  lea     rcx, [rsp+290h+var_250]
0x14007914e  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140079153  nop
0x140079154  mov     r8, [rdi+350h]
0x14007915b  lea     rcx, [rdi+3A0h]; this
0x140079162  mov     [rsp+290h+flProtect], esi; flProtect
0x140079166  mov     [rsp+290h+var_260], ebx; int
0x14007916a  mov     [rsp+290h+var_270], rax; __int64
0x14007916f  mov     r9d, [rdi+3F8h]
0x140079176  mov     r8d, [r8+20F0h]
0x14007917d  mov     edx, [rdi+3F0h]
0x140079183  call    ?CreateRB@RotatingBuffer@@QEAAJKKKAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@HHK@Z; RotatingBuffer::CreateRB(ulong,ulong,ulong,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,int,int,ulong)
0x140079188  mov     ebx, eax
0x14007918a  lea     rcx, [rsp+290h+var_250]
0x14007918f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140079194  test    ebx, ebx
0x140079196  jns     short loc_14007919C
0x140079198  mov     edx, ebx
0x14007919a  jmp     short loc_140079135
0x14007919c  mov     eax, [rdi+3F8h]
0x1400791a2  add     eax, [rdi+3D0h]
0x1400791a8  mov     [rdi+3F4h], eax
0x1400791ae  mov     rcx, [rdi+350h]
0x1400791b5  add     rcx, 28h ; '('
0x1400791b9  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x1400791be  mov     rax, [rax]
0x1400791c1  mov     [rdi+348h], rax
0x1400791c8  cmp     byte ptr [rdi+18h], 0
0x1400791cc  jz      loc_140079625
0x1400791d2  mov     rcx, [rdi+50h]; lpCriticalSection
0x1400791d6  call    cs:__imp_EnterCriticalSection
0x1400791dc  mov     rcx, [rdi+8]
0x1400791e0  mov     r15d, 0F0h
0x1400791e6  add     rcx, r15
0x1400791e9  lea     rdx, aCpu; "> CPU("
0x1400791f0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400791f5  mov     edx, [rdi+58h]
0x1400791f8  mov     rcx, rax
0x1400791fb  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140079200  mov     rcx, rax
0x140079203  lea     rdx, asc_140141108; ")  "
0x14007920a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007920f  mov     rcx, rax
0x140079212  lea     rdx, aTid_0; "TID: "
0x140079219  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007921e  mov     esi, 4
0x140079223  mov     [rsp+290h+var_250], esi
0x140079227  lea     rdx, [rsp+290h+var_250]
0x14007922c  mov     rcx, rax
0x14007922f  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzrightobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzrightobj const &)
0x140079234  mov     rbx, rax
0x140079237  call    cs:__imp_GetCurrentThreadId
0x14007923d  mov     edx, eax
0x14007923f  mov     rcx, rbx
0x140079242  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140079247  mov     rcx, [rax]
0x14007924a  movsxd  rdx, dword ptr [rcx+4]
0x14007924e  mov     ebx, 201h
0x140079253  or      [rdx+rax+18h], ebx
0x140079257  mov     rcx, [rax]
0x14007925a  movsxd  rdx, dword ptr [rcx+4]
0x14007925e  lea     r14d, [rsi+1Ch]
0x140079262  mov     [rdx+rax+58h], r14w
0x140079268  mov     rcx, [rax]
0x14007926b  movsxd  rdx, dword ptr [rcx+4]
0x14007926f  mov     qword ptr [rdx+rax+28h], 0
0x140079278  lea     rdx, aRunningAt_0; "\n  -- Running at "
0x14007927f  mov     rcx, rax
0x140079282  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140079287  mov     rcx, [rdi+350h]
0x14007928e  lea     r8, aHigh; "HIGH"
0x140079295  lea     rdx, aNormal_1; "NORMAL"
0x14007929c  cmp     byte ptr [rcx+20B8h], 0
0x1400792a3  cmovz   rdx, r8
0x1400792a7  mov     rcx, rax
0x1400792aa  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400792af  mov     rcx, rax
0x1400792b2  lea     rdx, aPriority_0; " priority"
0x1400792b9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400792be  mov     rcx, rax
0x1400792c1  lea     rdx, aUncompressedBu; "\n  -- Uncompressed Buffer Size ="
0x1400792c8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400792cd  mov     edx, [rdi+3F0h]
0x1400792d3  mov     rcx, rax
0x1400792d6  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x1400792db  mov     rcx, rax
0x1400792de  lea     rdx, a0x_0; " (0x"
0x1400792e5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400792ea  mov     [rsp+290h+var_250], esi
0x1400792ee  lea     rdx, [rsp+290h+var_250]
0x1400792f3  mov     rcx, rax
0x1400792f6  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x1400792fb  mov     edx, [rdi+3F0h]
0x140079301  mov     rcx, rax
0x140079304  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140079309  mov     rcx, [rax]
0x14007930c  movsxd  rdx, dword ptr [rcx+4]
0x140079310  or      [rdx+rax+18h], ebx
0x140079314  mov     rcx, [rax]
0x140079317  movsxd  rdx, dword ptr [rcx+4]
0x14007931b  mov     [rdx+rax+58h], r14w
0x140079321  mov     rcx, [rax]
0x140079324  movsxd  rdx, dword ptr [rcx+4]
0x140079328  mov     qword ptr [rdx+rax+28h], 0
0x140079331  lea     rdx, aBytes_3; ") bytes"
0x140079338  mov     rcx, rax
0x14007933b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140079340  mov     rcx, rax
0x140079343  lea     rdx, aNumRegions; "\n  -- Num regions = "
0x14007934a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14007934f  mov     rdx, [rdi+350h]
0x140079356  mov     edx, [rdx+20F0h]
0x14007935c  mov     rcx, rax
0x14007935f  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140079364  mov     rcx, rax
0x140079367  lea     rdx, aRegionSize; "   region size= "
0x14007936e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140079373  mov     r8, rax
0x140079376  mov     rcx, [rdi+350h]
0x14007937d  xor     edx, edx
0x14007937f  mov     eax, [rdi+3F0h]
0x140079385  div     dword ptr [rcx+20F0h]
0x14007938b  mov     edx, eax
0x14007938d  mov     rcx, r8
0x140079390  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140079395  mov     rcx, rax
0x140079398  lea     rdx, aBlockSize; "\n  -- Block Size = "
0x14007939f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400793a4  mov     edx, [rdi+3D0h]
0x1400793aa  mov     rcx, rax
0x1400793ad  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x1400793b2  mov     rcx, rax
0x1400793b5  lea     rdx, aCompressedBuff; "\n  -- Compressed Buffer Size ="
0x1400793bc  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400793c1  mov     edx, [rdi+3F4h]
0x1400793c7  mov     rcx, rax
0x1400793ca  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x1400793cf  mov     rcx, rax
0x1400793d2  lea     rdx, a0x_0; " (0x"
0x1400793d9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400793de  mov     [rsp+290h+var_250], esi
0x1400793e2  lea     rdx, [rsp+290h+var_250]
0x1400793e7  mov     rcx, rax
0x1400793ea  call    ??$?6GU?$char_traits@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBU_lzhexobj@0@@Z; mlib::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,mlib::_lzhexobj const &)
0x1400793ef  mov     edx, [rdi+3F4h]
0x1400793f5  mov     rcx, rax
0x1400793f8  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x1400793fd  mov     rcx, [rax]
0x140079400  movsxd  r8, dword ptr [rcx+4]
0x140079404  or      [r8+rax+18h], ebx
  ... truncated ...
```
