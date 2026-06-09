# ProcessAllResultsFromNode(IXMLDOMDocument2 *,bool,bool)

- ea: `0x140033bf4`
- end: `0x1400342ae`
- name: `?ProcessAllResultsFromNode@@YAJPEAUIXMLDOMDocument2@@_N1@Z`
- size: `1722`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, bool, bool)`
- caller_count: `2`
- callee_count: `31`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001a54c`
- `0x14001e350`

## callees

- `0x140004348`
- `0x140005b80`
- `0x140005d78`
- `0x140005f10`
- `0x140005f4c`
- `0x140006d74`
- `0x14000712c`
- `0x1400085b4`
- `0x14000861c`
- `0x1400086f8`
- `0x140016d04`
- `0x140017af0`
- `0x14001827c`
- `0x1400182f8`
- `0x14002d51c`
- `0x14002d874`
- `0x14002de00`
- `0x14002e2ac`
- `0x14002e924`
- `0x14002f40c`
- `0x14002fb28`
- `0x14002fe20`
- `0x1400329dc`
- `0x140032c20`
- `0x140033bf4`
- `0x1400382ec`
- `0x14003ec14`
- `0x1400543b4`
- `0x1400547f8`
- `0x1400548e0`
- `0x1400551d0`

## string_xrefs

- `0x140033d06`: `/WinSAT/SystemConfig/Graphics/PixelShader3OrBetter`
- `0x140033d7a`: `INFO: Can't find the shader 3.0 flag in the XML output`
- `0x140033d8e`: `Can't find the shader 3.0 flag in the XML output`
- `0x140033dbe`: `/WinSAT/SystemConfig/Memory/TotalPhysical/Bytes`
- `0x140033e25`: `INFO: Can't find physical memory size in XML output`
- `0x140033e39`: `Can't find physical memory size in XML output`
- `0x140033e52`: `/WinSAT/SystemConfig/Graphics/LDDM`
- `0x140033eb9`: `INFO: Can't find primary adapter WDDM flag in XML output`
- `0x140033ecd`: `Can't find primary adapter WDDM flag in XML output`
- `0x140033ede`: `/WinSAT/SystemConfig/Graphics/D3D9OrBetter`
- `0x140033f45`: `INFO: Can't find primary adapter driver version in XML output`
- `0x140033f59`: `Can't find primary adapter driver version in XML output`
- `0x140033f6a`: `/WinSAT/SystemConfig/OSVersion/Major`
- `0x140033fd1`: `INFO: Can't find operating system major version number in XML output`
- `0x140033fe5`: `Can't find operating system major version number in XML output`
- `0x140033ffd`: `/WinSAT/SystemConfig/Processor/Instance/X64Running`
- `0x140034040`: `Can't find 64-bit running flag in XML output`
- `0x1400340a8`: `ERROR: %#08X  ProcessAllResultsFromNode::ComputeWinCRSScore failed.`
- `0x140034199`: `ERROR: %#08X  ProcessAllResultsFromNode::WriteMetricsToStream failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ProcessAllResultsFromNode(struct IXMLDOMDocument2 *a1, char a2, char a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  int IsFormalFlag; // ebx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // r8d
  int NodeValue; // ebx
  __int64 v13; // rax
  __int64 *v14; // rax
  int v15; // r8d
  __int64 v16; // rax
  __int64 *v17; // rax
  int v18; // r8d
  __int64 v19; // rax
  __int64 *v20; // rax
  int v21; // r8d
  __int64 v22; // rax
  __int64 *v23; // rax
  int v24; // r8d
  __int64 v25; // rax
  __int64 *v26; // rax
  int v27; // r8d
  int v28; // eax
  __int64 *v29; // rcx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  char v35[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  struct IXMLDOMDocument2 *v38; // [rsp+48h] [rbp-B8h] BYREF
  struct IXMLDOMDocument2 *v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v40[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41[30]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+1A8h] [rbp+A8h] BYREF

  v39 = 0;
  v38 = 0;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v37);
  v6 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
  std::flush(v6 + 240);
  v7 = CSmartPtr<mlib::handle_ostreamT<char,std::char_traits<char>>>::operator*();
  std::flush(v7 + 240);
  IsFormalFlag = ComputeCPUMetric(a1);
  if ( IsFormalFlag >= 0 )
  {
    IsFormalFlag = ComputeMemoryMetric(a1);
    if ( IsFormalFlag >= 0 )
    {
      IsFormalFlag = ComputeD3DMetrics(a1);
      if ( IsFormalFlag >= 0 )
      {
        LOBYTE(v9) = a3;
        IsFormalFlag = ComputeGraphicsMetrics(a1, 0, v9);
        if ( IsFormalFlag >= 0 )
        {
          IsFormalFlag = ComputeDiskMetrics(a1);
          if ( IsFormalFlag >= 0 )
          {
            dbl_140168908 = 0.0;
            qword_140168910 = 0;
            dbl_1401688A0 = 0.0;
            IsFormalFlag = ComputeMediaExDecodeMetrics();
            if ( IsFormalFlag >= 0 )
            {
              if ( a2 )
                DisplayMetrics();
              v10 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
              std::flush(v10 + 240);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                &v42,
                L"/WinSAT/SystemConfig/Graphics/PixelShader3OrBetter");
              LOBYTE(v11) = 1;
              NodeValue = mlib::XmlDOM::GetNodeValue(
                            (_DWORD)a1,
                            (unsigned int)&v42,
                            v11,
                            (unsigned int)&qword_1401C3350,
                            (__int64)&v37);
              mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
              if ( NodeValue < 0 )
              {
                if ( App::s_IsPrivateBld && App::s_Verbose )
                {
                  v13 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
                  v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                          (__int64 *)(v13 + 240),
                          (__int64)L"INFO: Can't find the shader 3.0 flag in the XML output");
                  std::endl(v14);
                }
                Log_Text_F(
                  "base\\winsat\\exe\\processresults.cpp",
                  4530,
                  "Can't find the shader 3.0 flag in the XML output");
              }
              v35[0] = 0;
              IsFormalFlag = GetIsFormalFlag(a1, v35);
              if ( IsFormalFlag >= 0 )
              {
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v42,
                  L"/WinSAT/SystemConfig/Memory/TotalPhysical/Bytes");
                LOBYTE(v15) = 1;
                IsFormalFlag = mlib::XmlDOM::GetNodeValue(
                                 (_DWORD)a1,
                                 (unsigned int)&v42,
                                 v15,
                                 (unsigned int)&qword_1401C3300,
                                 (__int64)&v37);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
                if ( IsFormalFlag < 0 )
                {
                  if ( App::s_IsPrivateBld && App::s_Verbose )
                  {
                    v16 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
                    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                            (__int64 *)(v16 + 240),
                            (__int64)L"INFO: Can't find physical memory size in XML output");
                    std::endl(v17);
                  }
                  Log_Text_F(
                    "base\\winsat\\exe\\processresults.cpp",
                    4552,
                    "Can't find physical memory size in XML output");
                  goto LABEL_52;
                }
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v42,
                  L"/WinSAT/SystemConfig/Graphics/LDDM");
                LOBYTE(v18) = 1;
                IsFormalFlag = mlib::XmlDOM::GetNodeValue(
                                 (_DWORD)a1,
                                 (unsigned int)&v42,
                                 v18,
                                 (unsigned int)&byte_1401C3308,
                                 (__int64)&v37);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
                if ( IsFormalFlag < 0 )
                {
                  if ( App::s_IsPrivateBld && App::s_Verbose )
                  {
                    v19 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
                    v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                            (__int64 *)(v19 + 240),
                            (__int64)L"INFO: Can't find primary adapter WDDM flag in XML output");
                    std::endl(v20);
                  }
                  Log_Text_F(
                    "base\\winsat\\exe\\processresults.cpp",
                    4564,
                    "Can't find primary adapter WDDM flag in XML output");
                  goto LABEL_52;
                }
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v42,
                  L"/WinSAT/SystemConfig/Graphics/D3D9OrBetter");
                LOBYTE(v21) = 1;
                IsFormalFlag = mlib::XmlDOM::GetNodeValue(
                                 (_DWORD)a1,
                                 (unsigned int)&v42,
                                 v21,
                                 (unsigned int)&qword_1401C3338,
                                 (__int64)&v37);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
                if ( IsFormalFlag < 0 )
                {
                  if ( App::s_IsPrivateBld && App::s_Verbose )
                  {
                    v22 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
                    v23 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                            (__int64 *)(v22 + 240),
                            (__int64)L"INFO: Can't find primary adapter driver version in XML output");
                    std::endl(v23);
                  }
                  Log_Text_F(
                    "base\\winsat\\exe\\processresults.cpp",
                    4576,
                    "Can't find primary adapter driver version in XML output");
                  goto LABEL_52;
                }
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v42,
                  L"/WinSAT/SystemConfig/OSVersion/Major");
                LOBYTE(v24) = 1;
                IsFormalFlag = mlib::XmlDOM::GetNodeValue(
                                 (_DWORD)a1,
                                 (unsigned int)&v42,
                                 v24,
                                 (unsigned int)&dword_1401C330C,
                                 (__int64)&v37);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
                if ( IsFormalFlag < 0 )
                {
                  if ( App::s_IsPrivateBld && App::s_Verbose )
                  {
                    v25 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
                    v26 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                            (__int64 *)(v25 + 240),
                            (__int64)L"INFO: Can't find operating system major version number in XML output");
                    std::endl(v26);
                  }
                  Log_Text_F(
                    "base\\winsat\\exe\\processresults.cpp",
                    4592,
                    "Can't find operating system major version number in XML output");
                  goto LABEL_52;
                }
                LOBYTE(v42) = 0;
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v36,
                  L"/WinSAT/SystemConfig/Processor/Instance/X64Running");
                LOBYTE(v27) = 1;
                IsFormalFlag = mlib::XmlDOM::GetNodeValue(
                                 (_DWORD)a1,
                                 (unsigned int)&v36,
                                 v27,
                                 (unsigned int)&v42,
                                 (__int64)&v37);
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v36);
                if ( IsFormalFlag < 0 )
                {
                  Log_Text_F(
                    "base\\winsat\\exe\\processresults.cpp",
                    4607,
                    "Can't find 64-bit running flag in XML output");
                  goto LABEL_52;
                }
                mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  &v36,
                  4096);
                mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                  v41,
                  &v36);
                mlib::XmlStream::XmlStream((__int64)v40, v41, 1);
                v28 = ComputeWinCRSScore(v40, v35[0], v42, (__int64)a1);
                IsFormalFlag = v28;
                if ( v28 >= 0 )
                {
                  std::basic_ostream<unsigned short>::flush(v41);
                  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v42);
                  v30 = mlib::XmlDOM::LoadDocument(&v36, &v39, &v42);
                  IsFormalFlag = v30;
                  if ( v30 >= 0 )
                  {
                    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
                    mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v41);
                    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v36);
                    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                      &v42,
                      4096);
                    mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                      v41,
                      &v42);
                    mlib::XmlStream::XmlStream((__int64)v40, v41, 1);
                    v31 = WriteMetricsToStream((mlib::XmlStream *)v40);
                    IsFormalFlag = v31;
                    if ( v31 >= 0 )
                    {
                      std::basic_ostream<unsigned short>::flush(v41);
                      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(&v36);
                      v32 = mlib::XmlDOM::LoadDocument(&v42, &v38, &v36);
                      IsFormalFlag = v32;
                      if ( v32 >= 0 )
                      {
                        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v36);
                        mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v41);
                        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
                        v33 = AddWinCrsAndMetricsToResultNode(a1, v39, v38);
                        IsFormalFlag = v33;
                        if ( v33 >= 0 )
                          IsFormalFlag = 0;
                        else
                          Log_Text_F(
                            "base\\winsat\\exe\\processresults.cpp",
                            4657,
                            "ERROR: %#08X  ProcessAllResultsFromNode::AddWinCrsAndMetricsToResultNode failed.",
                            v33);
                        goto LABEL_52;
                      }
                      Log_Text_F(
                        "base\\winsat\\exe\\processresults.cpp",
                        4650,
                        "ERROR: %#08X  ProcessAllResultsFromNode::LoadDocument2 failed.",
                        v32);
                      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v36);
                    }
                    else
                    {
                      Log_Text_F(
                        "base\\winsat\\exe\\processresults.cpp",
                        4642,
                        "ERROR: %#08X  ProcessAllResultsFromNode::WriteMetricsToStream failed.",
                        v31);
                    }
                    mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v41);
                    v29 = &v42;
LABEL_41:
                    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v29);
                    goto LABEL_52;
                  }
                  Log_Text_F(
                    "base\\winsat\\exe\\processresults.cpp",
                    4629,
                    "ERROR: %#08X  ProcessAllResultsFromNode::LoadDocument failed.",
                    v30);
                  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v42);
                }
                else
                {
                  Log_Text_F(
                    "base\\winsat\\exe\\processresults.cpp",
                    4621,
                    "ERROR: %#08X  ProcessAllResultsFromNode::ComputeWinCRSScore failed.",
                    v28);
                }
                mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v41);
                v29 = &v36;
                goto LABEL_41;
              }
            }
          }
        }
      }
    }
  }
LABEL_52:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v37);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&v38);
  ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&v39);
  return (unsigned int)IsFormalFlag;
}

```

## disassembly

```asm
0x140033bf4  mov     [rsp-8+arg_0], rbx
0x140033bf9  mov     [rsp-8+arg_8], rsi
0x140033bfe  push    rbp
0x140033bff  push    rdi
0x140033c00  push    r12
0x140033c02  push    r14
0x140033c04  push    r15
0x140033c06  lea     rbp, [rsp-60h]
0x140033c0b  sub     rsp, 160h
0x140033c12  mov     r14b, r8b
0x140033c15  mov     sil, dl
0x140033c18  mov     rdi, rcx
0x140033c1b  xor     r15d, r15d
0x140033c1e  mov     [rsp+180h+var_130], r15
0x140033c23  mov     [rsp+180h+var_138], r15
0x140033c28  lea     rcx, [rsp+180h+var_140]
0x140033c2d  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x140033c32  nop
0x140033c33  lea     r12, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x140033c3a  mov     rcx, r12
0x140033c3d  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140033c42  lea     rcx, [rax+0F0h]
0x140033c49  call    ?flush@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::flush(std::basic_ostream<ushort> &)
0x140033c4e  call    ??D?$CSmartPtr@V?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@@@QEBAAEAV?$handle_ostreamT@DU?$char_traits@D@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<char,std::char_traits<char>>>::operator*(void)
0x140033c53  lea     rcx, [rax+0F0h]
0x140033c5a  call    ?flush@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::flush(std::basic_ostream<ushort> &)
0x140033c5f  mov     rcx, rdi
0x140033c62  call    ComputeCPUMetric
0x140033c67  mov     ebx, eax
0x140033c69  test    eax, eax
0x140033c6b  js      loc_140034270
0x140033c71  mov     rcx, rdi
0x140033c74  call    ComputeMemoryMetric
0x140033c79  mov     ebx, eax
0x140033c7b  test    eax, eax
0x140033c7d  js      loc_140034270
0x140033c83  mov     rcx, rdi
0x140033c86  call    ComputeD3DMetrics
0x140033c8b  mov     ebx, eax
0x140033c8d  test    eax, eax
0x140033c8f  js      loc_140034270
0x140033c95  mov     r8b, r14b
0x140033c98  xor     edx, edx
0x140033c9a  mov     rcx, rdi
0x140033c9d  call    ComputeGraphicsMetrics
0x140033ca2  mov     ebx, eax
0x140033ca4  test    eax, eax
0x140033ca6  js      loc_140034270
0x140033cac  mov     rcx, rdi
0x140033caf  call    ComputeDiskMetrics
0x140033cb4  mov     ebx, eax
0x140033cb6  test    eax, eax
0x140033cb8  js      loc_140034270
0x140033cbe  xorps   xmm0, xmm0
0x140033cc1  movsd   cs:dbl_140168908, xmm0
0x140033cc9  movsd   cs:qword_140168910, xmm0
0x140033cd1  movsd   cs:dbl_1401688A0, xmm0
0x140033cd9  call    ComputeMediaExDecodeMetrics
0x140033cde  mov     ebx, eax
0x140033ce0  test    eax, eax
0x140033ce2  js      loc_140034270
0x140033ce8  test    sil, sil
0x140033ceb  jz      short loc_140033CF2
0x140033ced  call    DisplayMetrics
0x140033cf2  mov     rcx, r12
0x140033cf5  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140033cfa  lea     rcx, [rax+0F0h]
0x140033d01  call    ?flush@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::flush(std::basic_ostream<ushort> &)
0x140033d06  lea     rdx, aWinsatSystemco_2; "/WinSAT/SystemConfig/Graphics/PixelShad"...
0x140033d0d  lea     rcx, [rbp+80h+arg_18]
0x140033d14  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140033d19  nop
0x140033d1a  lea     rax, [rsp+180h+var_140]
0x140033d1f  mov     [rsp+180h+var_160], rax
0x140033d24  lea     r9, qword_1401C3350
0x140033d2b  mov     r8b, 1
0x140033d2e  lea     rdx, [rbp+80h+arg_18]
0x140033d35  mov     rcx, rdi
0x140033d38  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_NPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,bool &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140033d3d  mov     ebx, eax
0x140033d3f  lea     rcx, [rbp+80h+arg_18]
0x140033d46  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140033d4b  mov     r14d, 0F0h
0x140033d51  lea     rsi, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x140033d58  test    ebx, ebx
0x140033d5a  jns     short loc_140033DA2
0x140033d5c  cmp     cs:?s_IsPrivateBld@App@@2_NA, r15b; bool App::s_IsPrivateBld
0x140033d63  jz      short loc_140033D8E
0x140033d65  cmp     cs:?s_Verbose@App@@2_NA, r15b; bool App::s_Verbose
0x140033d6c  jz      short loc_140033D8E
0x140033d6e  mov     rcx, r12
0x140033d71  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140033d76  lea     rcx, [r14+rax]
0x140033d7a  lea     rdx, aInfoCanTFindTh; "INFO: Can't find the shader 3.0 flag in"...
0x140033d81  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140033d86  mov     rcx, rax
0x140033d89  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140033d8e  lea     r8, aCanTFindTheSha; "Can't find the shader 3.0 flag in the X"...
0x140033d95  mov     edx, 11B2h
0x140033d9a  mov     rcx, rsi
0x140033d9d  call    Log_Text_F
0x140033da2  mov     [rsp+180h+var_150], r15b
0x140033da7  lea     rdx, [rsp+180h+var_150]
0x140033dac  mov     rcx, rdi
0x140033daf  call    GetIsFormalFlag
0x140033db4  mov     ebx, eax
0x140033db6  test    eax, eax
0x140033db8  js      loc_140034270
0x140033dbe  lea     rdx, aWinsatSystemco_6; "/WinSAT/SystemConfig/Memory/TotalPhysic"...
0x140033dc5  lea     rcx, [rbp+80h+arg_18]
0x140033dcc  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140033dd1  nop
0x140033dd2  lea     rax, [rsp+180h+var_140]
0x140033dd7  mov     [rsp+180h+var_160], rax
0x140033ddc  lea     r9, qword_1401C3300
0x140033de3  mov     r8b, 1
0x140033de6  lea     rdx, [rbp+80h+arg_18]
0x140033ded  mov     rcx, rdi
0x140033df0  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_KPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,unsigned __int64 &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140033df5  mov     ebx, eax
0x140033df7  lea     rcx, [rbp+80h+arg_18]
0x140033dfe  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140033e03  test    ebx, ebx
0x140033e05  jns     short loc_140033E52
0x140033e07  cmp     cs:?s_IsPrivateBld@App@@2_NA, r15b; bool App::s_IsPrivateBld
0x140033e0e  jz      short loc_140033E39
0x140033e10  cmp     cs:?s_Verbose@App@@2_NA, r15b; bool App::s_Verbose
0x140033e17  jz      short loc_140033E39
0x140033e19  mov     rcx, r12
0x140033e1c  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140033e21  lea     rcx, [r14+rax]
0x140033e25  lea     rdx, aInfoCanTFindPh; "INFO: Can't find physical memory size i"...
0x140033e2c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140033e31  mov     rcx, rax
0x140033e34  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140033e39  lea     r8, aCanTFindPhysic; "Can't find physical memory size in XML "...
0x140033e40  mov     edx, 11C8h
0x140033e45  mov     rcx, rsi
0x140033e48  call    Log_Text_F
0x140033e4d  jmp     loc_140034270
0x140033e52  lea     rdx, aWinsatSystemco_3; "/WinSAT/SystemConfig/Graphics/LDDM"
0x140033e59  lea     rcx, [rbp+80h+arg_18]
0x140033e60  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140033e65  nop
0x140033e66  lea     rax, [rsp+180h+var_140]
0x140033e6b  mov     [rsp+180h+var_160], rax
0x140033e70  lea     r9, byte_1401C3308
0x140033e77  mov     r8b, 1
0x140033e7a  lea     rdx, [rbp+80h+arg_18]
0x140033e81  mov     rcx, rdi
0x140033e84  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_NPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,bool &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140033e89  mov     ebx, eax
0x140033e8b  lea     rcx, [rbp+80h+arg_18]
0x140033e92  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140033e97  test    ebx, ebx
0x140033e99  jns     short loc_140033EDE
0x140033e9b  cmp     cs:?s_IsPrivateBld@App@@2_NA, r15b; bool App::s_IsPrivateBld
0x140033ea2  jz      short loc_140033ECD
0x140033ea4  cmp     cs:?s_Verbose@App@@2_NA, r15b; bool App::s_Verbose
0x140033eab  jz      short loc_140033ECD
0x140033ead  mov     rcx, r12
0x140033eb0  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140033eb5  lea     rcx, [r14+rax]
0x140033eb9  lea     rdx, aInfoCanTFindPr_0; "INFO: Can't find primary adapter WDDM f"...
0x140033ec0  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140033ec5  mov     rcx, rax
0x140033ec8  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140033ecd  lea     r8, aCanTFindPrimar; "Can't find primary adapter WDDM flag in"...
0x140033ed4  mov     edx, 11D4h
0x140033ed9  jmp     loc_140033E45
0x140033ede  lea     rdx, aWinsatSystemco_0; "/WinSAT/SystemConfig/Graphics/D3D9OrBet"...
0x140033ee5  lea     rcx, [rbp+80h+arg_18]
0x140033eec  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140033ef1  nop
0x140033ef2  lea     rax, [rsp+180h+var_140]
0x140033ef7  mov     [rsp+180h+var_160], rax
0x140033efc  lea     r9, qword_1401C3338
0x140033f03  mov     r8b, 1
0x140033f06  lea     rdx, [rbp+80h+arg_18]
0x140033f0d  mov     rcx, rdi
0x140033f10  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_NPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,bool &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140033f15  mov     ebx, eax
0x140033f17  lea     rcx, [rbp+80h+arg_18]
0x140033f1e  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140033f23  test    ebx, ebx
0x140033f25  jns     short loc_140033F6A
0x140033f27  cmp     cs:?s_IsPrivateBld@App@@2_NA, r15b; bool App::s_IsPrivateBld
0x140033f2e  jz      short loc_140033F59
0x140033f30  cmp     cs:?s_Verbose@App@@2_NA, r15b; bool App::s_Verbose
0x140033f37  jz      short loc_140033F59
0x140033f39  mov     rcx, r12
0x140033f3c  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140033f41  lea     rcx, [r14+rax]
0x140033f45  lea     rdx, aInfoCanTFindPr; "INFO: Can't find primary adapter driver"...
0x140033f4c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140033f51  mov     rcx, rax
0x140033f54  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140033f59  lea     r8, aCanTFindPrimar_0; "Can't find primary adapter driver versi"...
0x140033f60  mov     edx, 11E0h
0x140033f65  jmp     loc_140033E45
0x140033f6a  lea     rdx, aWinsatSystemco_1; "/WinSAT/SystemConfig/OSVersion/Major"
0x140033f71  lea     rcx, [rbp+80h+arg_18]
0x140033f78  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x140033f7d  nop
0x140033f7e  lea     rax, [rsp+180h+var_140]
0x140033f83  mov     [rsp+180h+var_160], rax
0x140033f88  lea     r9, dword_1401C330C
0x140033f8f  mov     r8b, 1
0x140033f92  lea     rdx, [rbp+80h+arg_18]
0x140033f99  mov     rcx, rdi
0x140033f9c  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEAKPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,ulong &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140033fa1  mov     ebx, eax
0x140033fa3  lea     rcx, [rbp+80h+arg_18]
0x140033faa  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140033faf  test    ebx, ebx
0x140033fb1  jns     short loc_140033FF6
0x140033fb3  cmp     cs:?s_IsPrivateBld@App@@2_NA, r15b; bool App::s_IsPrivateBld
0x140033fba  jz      short loc_140033FE5
0x140033fbc  cmp     cs:?s_Verbose@App@@2_NA, r15b; bool App::s_Verbose
0x140033fc3  jz      short loc_140033FE5
0x140033fc5  mov     rcx, r12
0x140033fc8  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140033fcd  lea     rcx, [r14+rax]
0x140033fd1  lea     rdx, aInfoCanTFindOp; "INFO: Can't find operating system major"...
0x140033fd8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140033fdd  mov     rcx, rax
0x140033fe0  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140033fe5  lea     r8, aCanTFindOperat; "Can't find operating system major versi"...
0x140033fec  mov     edx, 11F0h
0x140033ff1  jmp     loc_140033E45
0x140033ff6  mov     byte ptr [rbp+80h+arg_18], r15b
0x140033ffd  lea     rdx, aWinsatSystemco; "/WinSAT/SystemConfig/Processor/Instance"...
0x140034004  lea     rcx, [rsp+180h+var_148]
0x140034009  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14003400e  nop
0x14003400f  lea     rax, [rsp+180h+var_140]
0x140034014  mov     [rsp+180h+var_160], rax
0x140034019  lea     r9, [rbp+80h+arg_18]
0x140034020  mov     r8b, 1
0x140034023  lea     rdx, [rsp+180h+var_148]
0x140034028  mov     rcx, rdi
0x14003402b  call    ?GetNodeValue@XmlDOM@mlib@@SAJPEAUIXMLDOMNode@@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@_NAEA_NPEAV42@@Z; mlib::XmlDOM::GetNodeValue(IXMLDOMNode *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool,bool &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x140034030  mov     ebx, eax
0x140034032  lea     rcx, [rsp+180h+var_148]
0x140034037  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003403c  test    ebx, ebx
0x14003403e  jns     short loc_140034051
0x140034040  lea     r8, aCanTFind64BitR; "Can't find 64-bit running flag in XML o"...
0x140034047  mov     edx, 11FFh
0x14003404c  jmp     loc_140033E45
0x140034051  mov     r14d, 1000h
0x140034057  mov     edx, r14d
0x14003405a  lea     rcx, [rsp+180h+var_148]
0x14003405f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x140034064  nop
0x140034065  lea     rdx, [rsp+180h+var_148]
0x14003406a  lea     rcx, [rsp+180h+var_110]
0x14003406f  call    ??0?$fundamental_ostringstream@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@V?$allocator@G@2@@mlib@@QEAA@AEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@@Z; mlib::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x140034074  nop
0x140034075  mov     r8b, 1
0x140034078  lea     rdx, [rsp+180h+var_110]
0x14003407d  lea     rcx, [rsp+180h+var_128]
0x140034082  call    ??0XmlStream@mlib@@QEAA@AEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@_N@Z; mlib::XmlStream::XmlStream(std::basic_ostream<ushort> &,bool)
0x140034087  mov     r9, rdi
0x14003408a  mov     r8b, byte ptr [rbp+80h+arg_18]
0x140034091  mov     dl, [rsp+180h+var_150]
0x140034095  lea     rcx, [rsp+180h+var_128]; this
0x14003409a  call    ComputeWinCRSScore
0x14003409f  mov     ebx, eax
0x1400340a1  test    eax, eax
0x1400340a3  jns     short loc_1400340D7
0x1400340a5  mov     r9d, eax
0x1400340a8  lea     r8, aError08xProces_3; "ERROR: %#08X  ProcessAllResultsFromNode"...
0x1400340af  mov     edx, 120Dh
0x1400340b4  mov     rcx, rsi
0x1400340b7  call    Log_Text_F
0x1400340bc  nop
0x1400340bd  lea     rcx, [rsp+180h+var_110]
0x1400340c2  call    ??_D?$fundamental_ostringstream@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@V?$allocator@G@2@@mlib@@QEAAXXZ; mlib::fundamental_ostringstream<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x1400340c7  nop
0x1400340c8  lea     rcx, [rsp+180h+var_148]
0x1400340cd  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x1400340d2  jmp     loc_140034270
0x1400340d7  lea     rcx, [rsp+180h+var_110]
0x1400340dc  call    ?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x1400340e1  lea     rcx, [rbp+80h+arg_18]
0x1400340e8  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x1400340ed  nop
0x1400340ee  lea     r8, [rbp+80h+arg_18]
0x1400340f5  lea     rdx, [rsp+180h+var_130]
0x1400340fa  lea     rcx, [rsp+180h+var_148]
0x1400340ff  call    ?LoadDocument@XmlDOM@mlib@@SAJAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@PEAPEAUIXMLDOMDocument2@@PEAV32@_N@Z; mlib::XmlDOM::LoadDocument(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMDocument2 * *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,bool)
0x140034104  mov     ebx, eax
0x140034106  test    eax, eax
0x140034108  jns     short loc_140034130
0x14003410a  mov     r9d, eax
0x14003410d  lea     r8, aError08xProces_4; "ERROR: %#08X  ProcessAllResultsFromNode"...
0x140034114  mov     edx, 1215h
0x140034119  mov     rcx, rsi
0x14003411c  call    Log_Text_F
  ... truncated ...
```
