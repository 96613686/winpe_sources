# SetRegistryDiskReadScores(IXMLDOMDocument2 *)

- ea: `0x140034990`
- end: `0x14003512d`
- name: `?SetRegistryDiskReadScores@@YAJPEAUIXMLDOMDocument2@@@Z`
- size: `1949`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config`

## callers

- `0x14002e2ac`

## callees

- `0x140001abc`
- `0x140004348`
- `0x140005d78`
- `0x140005f10`
- `0x140005f4c`
- `0x1400085b4`
- `0x1400143a0`
- `0x140015c28`
- `0x140016480`
- `0x140016d04`
- `0x140017af0`
- `0x140018968`
- `0x140019a1c`
- `0x140019cb0`
- `0x140019e1c`
- `0x14002c48c`
- `0x140034990`
- `0x14003a770`
- `0x14003ec14`
- `0x14004fe00`
- `0x140052fac`
- `0x14005354c`
- `0x1400535e4`
- `0x140053bf0`
- `0x14005497c`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140034aa4`
- `KERNEL32!GetLastError` at `0x140034b19`
- `KERNEL32!GetLastError` at `0x140034f9d`
- `KERNEL32!GetLastError` at `0x140034fe8`
- `KERNEL32!GetLastError` at `0x140034aa4`
- `KERNEL32!GetLastError` at `0x140034b19`
- `KERNEL32!GetLastError` at `0x140034f9d`
- `KERNEL32!GetLastError` at `0x140034fe8`

## string_xrefs

- `0x14003508c`: `Skipping Registry Entry for random read disk score`
- `0x140034ad3`: `ERROR: Can't write wsswap throughput, from the profiler, to the registry %u: %s`
- `0x140034aec`: `> Wrote wsswap throughput, from the profiler, to the registry %u`
- `0x140034b49`: `ERROR: Can't write wsswap interference, from the profiler, to the registry %u: %s`
- `0x140034b63`: `> Wrote wsswap interference, from the profiler, to the registry %u`
- `0x140034cd1`: `INFO: Can't find disk random read scores in XML output`
- `0x140034d88`: `INFO: Can't find disk random read scores in XML output`
- `0x140034ce5`: `Can't find disk random read scores in XML output`
- `0x140034d9c`: `Can't find disk random read scores in XML output`
- `0x140034ef0`: `Disk%sRandomReadThroughput`
- `0x140034fd0`: `ERROR: Can't write random read disk score, from the profiler, to the registry %u: %s`
- `0x140034f44`: `> Wrote random read disk score, from the profiler, to the registry %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall SetRegistryDiskReadScores(struct IXMLDOMDocument2 *a1)
{
  int v2; // r13d
  double *i; // rbx
  unsigned int v4; // edi
  unsigned __int16 v5; // r9
  const unsigned __int16 *v6; // rax
  unsigned __int16 v7; // r9
  const unsigned __int16 *v8; // rax
  int NodesText; // edi
  __int64 v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rcx
  void *v13; // rbx
  unsigned int v15; // r12d
  __int64 v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rcx
  void *v19; // rbx
  char *v20; // rbx
  char *v21; // rcx
  char *v22; // rsi
  _QWORD *v23; // r14
  __int64 v24; // rax
  char *j; // rbx
  unsigned int v26; // edi
  signed int v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v33; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A8h] BYREF
  __int64 Block; // [rsp+68h] [rbp-A0h] BYREF
  void *Block_8[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v39; // [rsp+80h] [rbp-88h]
  double v40; // [rsp+88h] [rbp-80h] BYREF
  void *v41[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-68h]
  _QWORD v43[10]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v44[10]; // [rsp+F8h] [rbp-10h] BYREF
  CHAR Buffer[256]; // [rsp+148h] [rbp+40h] BYREF
  DWORD LastError; // [rsp+248h] [rbp+140h]
  char v47; // [rsp+24Ch] [rbp+144h]
  __int64 v48; // [rsp+250h] [rbp+148h]

  *(_OWORD *)v41 = 0;
  v2 = 0;
  v42 = 0;
  *(_OWORD *)Block_8 = 0;
  v39 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v34);
  for ( i = (double *)xmmword_1401C63C0; i != *(&xmmword_1401C63C0 + 1); i += 7 )
  {
    if ( !*((_DWORD *)i + 9) && (*(_DWORD *)i & 0x10000000) != 0 )
    {
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v35,
        L"WsSwapResult");
      mlib::DWORDReg::DWORDReg(v44);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v35);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v33,
        L"WsSwapInterference");
      mlib::DWORDReg::DWORDReg(v43);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v33);
      v4 = (int)i[5] << 10;
      mlib::DWORDReg::operator=(v44, v4);
      if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v44) )
      {
        LastError = GetLastError();
        v47 = 1;
        v48 = 0;
        mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
        Log_Text_F(
          "base\\winsat\\exe\\processresults.cpp",
          4764,
          "ERROR: Can't write wsswap throughput, from the profiler, to the registry %u: %s",
          v4,
          Buffer);
      }
      else
      {
        Log_Text_F(
          "base\\winsat\\exe\\processresults.cpp",
          4767,
          "> Wrote wsswap throughput, from the profiler, to the registry %u",
          v4);
      }
      mlib::DWORDReg::operator=(v43, *((unsigned int *)i + 7));
      if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v43) )
      {
        LastError = GetLastError();
        v47 = 1;
        v48 = 0;
        mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
        Log_Text_F(
          "base\\winsat\\exe\\processresults.cpp",
          4774,
          "ERROR: Can't write wsswap interference, from the profiler, to the registry %u: %s",
          *((_DWORD *)i + 7),
          Buffer);
      }
      else
      {
        Log_Text_F(
          "base\\winsat\\exe\\processresults.cpp",
          4777,
          "> Wrote wsswap interference, from the profiler, to the registry %u",
          *((_DWORD *)i + 7));
      }
      if ( qword_1401C6668 )
      {
        qword_1401C6668(qword_1401689B8, 11242, v4);
        if ( qword_1401C6668 )
        {
          qword_1401C6668(qword_1401689B8, 11244, *((unsigned __int16 *)i + 14));
          if ( qword_1401C6668 )
            qword_1401C6668(qword_1401689B8, 11243, *((unsigned __int16 *)i + 15));
        }
      }
      mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v43);
      mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v44);
    }
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v31,
    L"/WinSAT/DiskAssessment/PerDiskData/Zone/ModeFlags[@friendlyName='");
  v6 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\processresults.cpp", (const char *)0x12BD, 403, v5);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
    &v31,
    v6);
  v8 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\processresults.cpp", (const char *)0x12BE, 404, v7);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
    &v31,
    v8);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::strip_trailing_ws(&v31);
  v32 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
    &v32,
    v31);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
    &v31,
    L"']/../ETWData/Throughput");
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
    &v32,
    L"']/../../Disk");
  NodesText = mlib::XmlDOM::GetNodesText(a1, &v31, Block_8, &v34);
  if ( NodesText >= 0 )
  {
    v15 = mlib::XmlDOM::GetNodesText(a1, &v32, v41, &v34);
    if ( (v15 & 0x80000000) == 0 )
    {
      v22 = (char *)v41[0];
      v23 = Block_8[0];
      if ( App::s_isAxeMode
        || (v24 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
            !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v24))
        || App::s_WsSwapTest
        || !App::s_RegistryCreated )
      {
        Log_Text_F("base\\winsat\\exe\\processresults.cpp", 4854, "Skipping Registry Entry for random read disk score");
      }
      else
      {
        for ( j = v22; j != v41[1]; j += 8 )
        {
          v36 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v36,
            *(_QWORD *)&v22[8 * v2]);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::substr(
            &v36,
            &v35,
            17);
          v40 = 0.0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v33,
            30);
          Block = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &Block,
            v23[v2]);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::to_double(
            &Block,
            &v40);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
            &v33,
            L"Disk%sRandomReadThroughput",
            *(_QWORD *)(v35 + 24));
          mlib::DWORDReg::DWORDReg(v43);
          v26 = (int)(v40 * 1024.0);
          mlib::DWORDReg::operator=(v43, v26);
          if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v43) )
          {
            LastError = GetLastError();
            v47 = 1;
            v48 = 0;
            mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
            Log_Text_F(
              "base\\winsat\\exe\\processresults.cpp",
              4844,
              "ERROR: Can't write random read disk score, from the profiler, to the registry %u: %s",
              v26,
              Buffer);
            v27 = GetLastError();
            v28 = v27;
            if ( v27 > 0 )
              v28 = (unsigned __int16)v27 | 0x80070000;
            mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v43);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&Block);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v33);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v35);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v36);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v32);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
            mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v34);
            if ( v23 )
            {
              std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
                v29,
                v23,
                Block_8[1]);
              operator delete(v23);
            }
            if ( v22 )
            {
              std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
                v29,
                v22,
                v41[1]);
              operator delete(v22);
            }
            return v28;
          }
          Log_Text_F(
            "base\\winsat\\exe\\processresults.cpp",
            4849,
            "> Wrote random read disk score, from the profiler, to the registry %u",
            v26);
          ++v2;
          mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v43);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&Block);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v33);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v35);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v36);
        }
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v32);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v34);
      if ( v23 )
      {
        std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
          v30,
          v23,
          Block_8[1]);
        operator delete(v23);
      }
      if ( !v22 )
        return v15;
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
        v30,
        v22,
        v41[1]);
      v21 = v22;
    }
    else
    {
      if ( App::s_IsPrivateBld && App::s_Verbose )
      {
        v16 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
        v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                (__int64 *)(v16 + 240),
                (__int64)L"INFO: Can't find disk random read scores in XML output");
        std::endl(v17);
      }
      Log_Text_F("base\\winsat\\exe\\processresults.cpp", 4820, "Can't find disk random read scores in XML output");
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v32);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v34);
      v19 = Block_8[0];
      if ( Block_8[0] )
      {
        std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
          v18,
          Block_8[0],
          Block_8[1]);
        operator delete(v19);
      }
      v20 = (char *)v41[0];
      if ( !v41[0] )
        return v15;
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
        v18,
        v41[0],
        v41[1]);
      v21 = v20;
    }
    operator delete(v21);
    return v15;
  }
  if ( App::s_IsPrivateBld && App::s_Verbose )
  {
    v10 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
    v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64 *)(v10 + 240),
            (__int64)L"INFO: Can't find disk random read scores in XML output");
    std::endl(v11);
  }
  Log_Text_F("base\\winsat\\exe\\processresults.cpp", 4810, "Can't find disk random read scores in XML output");
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v32);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v34);
  v13 = Block_8[0];
  if ( Block_8[0] )
  {
    std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const,std::allocator<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const>>::_Destroy(
      v12,
      Block_8[0],
      Block_8[1]);
    operator delete(v13);
  }
  return (unsigned int)NodesText;
}

```

## disassembly

```asm
0x140034990  mov     rax, rsp
0x140034993  mov     [rax+10h], rbx
0x140034997  mov     [rax+18h], rsi
0x14003499b  push    rbp
0x14003499c  push    rdi
0x14003499d  push    r12
0x14003499f  push    r13
0x1400349a1  push    r14
0x1400349a3  lea     rbp, [rax-198h]
0x1400349aa  sub     rsp, 270h
0x1400349b1  movaps  xmmword ptr [rax-38h], xmm6
0x1400349b5  mov     rax, cs:__security_cookie
0x1400349bc  xor     rax, rsp
0x1400349bf  mov     [rbp+190h+var_40], rax
0x1400349c6  mov     rsi, rcx
0x1400349c9  xorps   xmm0, xmm0
0x1400349cc  movdqu  xmmword ptr [rbp+190h+var_208], xmm0
0x1400349d1  xor     r13d, r13d
0x1400349d4  mov     [rbp+190h+var_1F8], r13
0x1400349d8  movdqu  xmmword ptr [rsp+290h+Block+8], xmm0
0x1400349de  mov     [rsp+290h+var_218], r13
0x1400349e3  lea     rcx, [rsp+290h+var_248]
0x1400349e8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x1400349ed  nop
0x1400349ee  mov     rbx, qword ptr cs:xmmword_1401C63C0
0x1400349f5  lea     r14, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x1400349fc  cmp     rbx, qword ptr cs:xmmword_1401C63C0+8
0x140034a03  jz      loc_140034BF8
0x140034a09  cmp     [rbx+24h], r13d
0x140034a0d  jnz     loc_140034BEF
0x140034a13  test    dword ptr [rbx], 10000000h
0x140034a19  jz      loc_140034BEF
0x140034a1f  lea     rdx, aWsswapresult; "WsSwapResult"
0x140034a26  lea     rcx, [rsp+290h+var_240]
0x140034a2b  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140034a30  nop
0x140034a31  lea     r8, [rsp+290h+var_240]
0x140034a36  mov     rdx, cs:qword_1401C6370
0x140034a3d  lea     rcx, [rbp+190h+var_1A0]
0x140034a41  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x140034a46  nop
0x140034a47  lea     rcx, [rsp+290h+var_240]
0x140034a4c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140034a51  lea     rdx, aWsswapinterfer; "WsSwapInterference"
0x140034a58  lea     rcx, [rsp+290h+var_250]
0x140034a5d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140034a62  nop
0x140034a63  lea     r8, [rsp+290h+var_250]
0x140034a68  mov     rdx, cs:qword_1401C6370
0x140034a6f  lea     rcx, [rbp+190h+var_1F0]
0x140034a73  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x140034a78  nop
0x140034a79  lea     rcx, [rsp+290h+var_250]
0x140034a7e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140034a83  cvttsd2si rdi, qword ptr [rbx+28h]
0x140034a89  shl     edi, 0Ah
0x140034a8c  mov     edx, edi
0x140034a8e  lea     rcx, [rbp+190h+var_1A0]
0x140034a92  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x140034a97  lea     rcx, [rbp+190h+var_1A0]; this
0x140034a9b  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x140034aa0  test    eax, eax
0x140034aa2  jz      short loc_140034AE9
0x140034aa4  call    cs:__imp_GetLastError
0x140034aaa  mov     [rbp+190h+var_50], eax
0x140034ab0  mov     [rbp+190h+var_4C], 1
0x140034ab7  mov     [rbp+190h+var_48], r13
0x140034abe  lea     rcx, [rbp+190h+Buffer]; lpBuffer
0x140034ac2  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x140034ac7  lea     rax, [rbp+190h+Buffer]
0x140034acb  mov     [rsp+290h+var_270], rax
0x140034ad0  mov     r9d, edi
0x140034ad3  lea     r8, aErrorCanTWrite_6; "ERROR: Can't write wsswap throughput, f"...
0x140034ada  mov     edx, 129Ch
0x140034adf  mov     rcx, r14
0x140034ae2  call    Log_Text_F
0x140034ae7  jmp     short loc_140034B00
0x140034ae9  mov     r9d, edi
0x140034aec  lea     r8, aWroteWsswapThr; "> Wrote wsswap throughput, from the pro"...
0x140034af3  mov     edx, 129Fh
0x140034af8  mov     rcx, r14
0x140034afb  call    Log_Text_F
0x140034b00  mov     edx, [rbx+1Ch]
0x140034b03  lea     rcx, [rbp+190h+var_1F0]
0x140034b07  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x140034b0c  lea     rcx, [rbp+190h+var_1F0]; this
0x140034b10  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x140034b15  test    eax, eax
0x140034b17  jz      short loc_140034B5F
0x140034b19  call    cs:__imp_GetLastError
0x140034b1f  mov     [rbp+190h+var_50], eax
0x140034b25  mov     [rbp+190h+var_4C], 1
0x140034b2c  mov     [rbp+190h+var_48], r13
0x140034b33  lea     rcx, [rbp+190h+Buffer]; lpBuffer
0x140034b37  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x140034b3c  lea     rax, [rbp+190h+Buffer]
0x140034b40  mov     [rsp+290h+var_270], rax
0x140034b45  mov     r9d, [rbx+1Ch]
0x140034b49  lea     r8, aErrorCanTWrite_17; "ERROR: Can't write wsswap interference,"...
0x140034b50  mov     edx, 12A6h
0x140034b55  mov     rcx, r14
0x140034b58  call    Log_Text_F
0x140034b5d  jmp     short loc_140034B77
0x140034b5f  mov     r9d, [rbx+1Ch]
0x140034b63  lea     r8, aWroteWsswapInt; "> Wrote wsswap interference, from the p"...
0x140034b6a  mov     edx, 12A9h
0x140034b6f  mov     rcx, r14
0x140034b72  call    Log_Text_F
0x140034b77  mov     rax, cs:qword_1401C6668
0x140034b7e  test    rax, rax
0x140034b81  jz      short loc_140034BDC
0x140034b83  mov     r8d, edi
0x140034b86  mov     edx, 2BEAh
0x140034b8b  lea     rcx, qword_1401689B8
0x140034b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034b97  mov     rax, cs:qword_1401C6668
0x140034b9e  test    rax, rax
0x140034ba1  jz      short loc_140034BDC
0x140034ba3  movzx   r8d, word ptr [rbx+1Ch]
0x140034ba8  mov     edx, 2BECh
0x140034bad  lea     rcx, qword_1401689B8
0x140034bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034bb9  mov     rax, cs:qword_1401C6668
0x140034bc0  test    rax, rax
0x140034bc3  jz      short loc_140034BDC
0x140034bc5  movzx   r8d, word ptr [rbx+1Eh]
0x140034bca  mov     edx, 2BEBh
0x140034bcf  lea     rcx, qword_1401689B8
0x140034bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034bdb  nop
0x140034bdc  lea     rcx, [rbp+190h+var_1F0]; this
0x140034be0  call    ??1DWORDReg@mlib@@UEAA@XZ; mlib::DWORDReg::~DWORDReg(void)
0x140034be5  nop
0x140034be6  lea     rcx, [rbp+190h+var_1A0]; this
0x140034bea  call    ??1DWORDReg@mlib@@UEAA@XZ; mlib::DWORDReg::~DWORDReg(void)
0x140034bef  add     rbx, 38h ; '8'
0x140034bf3  jmp     loc_1400349FC
0x140034bf8  lea     rdx, aWinsatDiskasse_0; "/WinSAT/DiskAssessment/PerDiskData/Zone"...
0x140034bff  lea     rcx, [rsp+290h+var_260]
0x140034c04  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140034c09  nop
0x140034c0a  mov     edx, 12BDh; char *
0x140034c0f  mov     r8d, 193h; int
0x140034c15  mov     rcx, r14; this
0x140034c18  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140034c1d  mov     rdx, rax
0x140034c20  lea     rcx, [rsp+290h+var_260]
0x140034c25  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x140034c2a  mov     edx, 12BEh; char *
0x140034c2f  mov     r8d, 194h; int
0x140034c35  mov     rcx, r14; this
0x140034c38  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140034c3d  mov     rdx, rax
0x140034c40  lea     rcx, [rsp+290h+var_260]
0x140034c45  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x140034c4a  lea     rcx, [rsp+290h+var_260]
0x140034c4f  call    ?strip_trailing_ws@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::strip_trailing_ws(void)
0x140034c54  mov     [rsp+290h+var_258], r13
0x140034c59  mov     rdx, [rsp+290h+var_260]
0x140034c5e  lea     rcx, [rsp+290h+var_258]
0x140034c63  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140034c68  nop
0x140034c69  lea     rdx, aEtwdataThrough; "']/../ETWData/Throughput"
0x140034c70  lea     rcx, [rsp+290h+var_260]
0x140034c75  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x140034c7a  lea     rdx, aDisk_3; "']/../../Disk"
0x140034c81  lea     rcx, [rsp+290h+var_258]
0x140034c86  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x140034c8b  lea     r9, [rsp+290h+var_248]
0x140034c90  lea     r8, [rsp+290h+Block+8]
0x140034c95  lea     rdx, [rsp+290h+var_260]
0x140034c9a  mov     rcx, rsi
0x140034c9d  call    ?GetNodesText@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAV42@@Z; mlib::XmlDOM::GetNodesText(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140034ca2  mov     edi, eax
0x140034ca4  test    eax, eax
0x140034ca6  jns     loc_140034D42
0x140034cac  cmp     cs:?s_IsPrivateBld@App@@2_NA, r13b; bool App::s_IsPrivateBld
0x140034cb3  jz      short loc_140034CE5
0x140034cb5  cmp     cs:?s_Verbose@App@@2_NA, r13b; bool App::s_Verbose
0x140034cbc  jz      short loc_140034CE5
0x140034cbe  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x140034cc5  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140034cca  lea     rcx, [rax+0F0h]
0x140034cd1  lea     rdx, aInfoCanTFindDi; "INFO: Can't find disk random read score"...
0x140034cd8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140034cdd  mov     rcx, rax
0x140034ce0  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140034ce5  lea     r8, aCanTFindDiskRa; "Can't find disk random read scores in X"...
0x140034cec  mov     edx, 12CAh
0x140034cf1  mov     rcx, r14
0x140034cf4  call    Log_Text_F
0x140034cf9  nop
0x140034cfa  lea     rcx, [rsp+290h+var_258]
0x140034cff  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140034d04  nop
0x140034d05  lea     rcx, [rsp+290h+var_260]
0x140034d0a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140034d0f  nop
0x140034d10  lea     rcx, [rsp+290h+var_248]
0x140034d15  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140034d1a  nop
0x140034d1b  mov     rbx, [rsp+290h+Block+8]
0x140034d20  test    rbx, rbx
0x140034d23  jz      short loc_140034D3B
0x140034d25  mov     r8, [rsp+290h+var_220]
0x140034d2a  mov     rdx, rbx
0x140034d2d  call    ?_Destroy@?$vector@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140034d32  mov     rcx, rbx; Block
0x140034d35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140034d3a  nop
0x140034d3b  mov     eax, edi
0x140034d3d  jmp     loc_1400350FD
0x140034d42  lea     r9, [rsp+290h+var_248]
0x140034d47  lea     r8, [rbp+190h+var_208]
0x140034d4b  lea     rdx, [rsp+290h+var_258]
0x140034d50  mov     rcx, rsi
0x140034d53  call    ?GetNodesText@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@AEAV?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@PEAV42@@Z; mlib::XmlDOM::GetNodesText(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140034d58  mov     r12d, eax
0x140034d5b  test    eax, eax
0x140034d5d  jns     loc_140034E13
0x140034d63  cmp     cs:?s_IsPrivateBld@App@@2_NA, r13b; bool App::s_IsPrivateBld
0x140034d6a  jz      short loc_140034D9C
0x140034d6c  cmp     cs:?s_Verbose@App@@2_NA, r13b; bool App::s_Verbose
0x140034d73  jz      short loc_140034D9C
0x140034d75  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x140034d7c  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140034d81  lea     rcx, [rax+0F0h]
0x140034d88  lea     rdx, aInfoCanTFindDi; "INFO: Can't find disk random read score"...
0x140034d8f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140034d94  mov     rcx, rax
0x140034d97  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140034d9c  lea     r8, aCanTFindDiskRa; "Can't find disk random read scores in X"...
0x140034da3  mov     edx, 12D4h
0x140034da8  mov     rcx, r14
0x140034dab  call    Log_Text_F
0x140034db0  nop
0x140034db1  lea     rcx, [rsp+290h+var_258]
0x140034db6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140034dbb  nop
0x140034dbc  lea     rcx, [rsp+290h+var_260]
0x140034dc1  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140034dc6  nop
0x140034dc7  lea     rcx, [rsp+290h+var_248]
0x140034dcc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140034dd1  nop
0x140034dd2  mov     rbx, [rsp+290h+Block+8]
0x140034dd7  test    rbx, rbx
0x140034dda  jz      short loc_140034DF2
0x140034ddc  mov     r8, [rsp+290h+var_220]
0x140034de1  mov     rdx, rbx
0x140034de4  call    ?_Destroy@?$vector@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140034de9  mov     rcx, rbx; Block
0x140034dec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140034df1  nop
0x140034df2  mov     rbx, [rbp+190h+var_208]
0x140034df6  test    rbx, rbx
0x140034df9  jz      loc_1400350FA
0x140034dff  mov     r8, [rbp+190h+var_208+8]
0x140034e03  mov     rdx, rbx
0x140034e06  call    ?_Destroy@?$vector@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@$$CBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const,std::allocator<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140034e0b  mov     rcx, rbx
0x140034e0e  jmp     loc_1400350F5
0x140034e13  mov     rsi, [rbp+190h+var_208]
0x140034e17  mov     r14, [rsp+290h+Block+8]
0x140034e1c  cmp     cs:?s_isAxeMode@App@@2_NA, r13b; bool App::s_isAxeMode
0x140034e23  jnz     loc_14003508C
0x140034e29  lea     rcx, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x140034e30  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140034e35  mov     rcx, rax
0x140034e38  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x140034e3d  test    al, al
0x140034e3f  jz      loc_14003508C
0x140034e45  cmp     cs:?s_WsSwapTest@App@@2_NA, r13b; bool App::s_WsSwapTest
0x140034e4c  jnz     loc_14003508C
0x140034e52  cmp     cs:?s_RegistryCreated@App@@2_NA, r13b; bool App::s_RegistryCreated
0x140034e59  jz      loc_14003508C
0x140034e5f  mov     rbx, rsi
0x140034e62  xorps   xmm6, xmm6
0x140034e65  cmp     rbx, [rbp+190h+var_208+8]
0x140034e69  jz      loc_1400350A5
0x140034e6f  mov     [rsp+290h+var_238], 0
0x140034e78  movsxd  rdi, r13d
0x140034e7b  mov     rdx, [rsi+rdi*8]
0x140034e7f  lea     rcx, [rsp+290h+var_238]
0x140034e84  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140034e89  nop
0x140034e8a  mov     rax, [rsp+290h+var_238]
0x140034e8f  mov     r9, [rax]
0x140034e92  sub     r9, 11h
0x140034e96  mov     r8d, 11h
0x140034e9c  lea     rdx, [rsp+290h+var_240]
0x140034ea1  lea     rcx, [rsp+290h+var_238]
0x140034ea6  call    ?substr@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@_K0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::substr(unsigned __int64,unsigned __int64)
0x140034eab  nop
0x140034eac  movsd   [rbp+190h+var_210], xmm6
0x140034eb1  mov     edx, 1Eh
0x140034eb6  lea     rcx, [rsp+290h+var_250]
0x140034ebb  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140034ec0  nop
0x140034ec1  mov     [rsp+290h+Block], 0
  ... truncated ...
```
