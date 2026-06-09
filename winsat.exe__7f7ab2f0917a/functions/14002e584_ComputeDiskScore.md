# ComputeDiskScore

- ea: `0x14002e584`
- end: `0x14002e91b`
- name: `ComputeDiskScore`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002fe20`

## callees

- `0x140005d78`
- `0x1400085b4`
- `0x140016d04`
- `0x140018968`
- `0x14002c48c`
- `0x14002e584`
- `0x14003ec14`
- `0x140052fac`
- `0x14005354c`
- `0x1400535e4`
- `0x140053bf0`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002e73b`
- `KERNEL32!GetLastError` at `0x14002e867`
- `KERNEL32!GetLastError` at `0x14002e73b`
- `KERNEL32!GetLastError` at `0x14002e867`

## string_xrefs

- `0x14002e67e`: `Using the sequential read subscore (capped at 5.9) for final disk score rather than the combined sequential + random disk subscores.`
- `0x14002e6e1`: `RandomReadDiskScore`
- `0x14002e76e`: `ERROR: Can't write random read disk score (throughput) to the registry %u: %s`
- `0x14002e787`: `> Wrote random read disk score (throughput) to the registry %u`
- `0x14002e7a8`: `Skipping Registry Entry for random read disk score`
- `0x14002e80c`: `SequentialReadDiskScore`
- `0x14002e89a`: `ERROR: Can't write sequential read disk score (throughput) to the registry %u: %s`
- `0x14002e8b3`: `> Wrote sequential read disk score (throughput) to the registry %u`
- `0x14002e8d4`: `Skipping Registry Entry for sequential read disk score`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void ComputeDiskScore()
{
  double v0; // xmm1_8
  double v1; // xmm8_8
  double v2; // xmm0_8
  double v3; // xmm7_8
  double *i; // rax
  double v5; // xmm2_8
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  _QWORD v10[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v11[10]; // [rsp+48h] [rbp-C0h] BYREF
  CHAR Buffer[256]; // [rsp+98h] [rbp-70h] BYREF
  DWORD LastError; // [rsp+198h] [rbp+90h]
  char v14; // [rsp+19Ch] [rbp+94h]
  __int64 v15; // [rsp+1A0h] [rbp+98h]

  v0 = DOUBLE_1_797693134862316e308;
  v1 = DOUBLE_1_797693134862316e308;
  v2 = DOUBLE_1_797693134862316e308;
  v3 = DOUBLE_1_797693134862316e308;
  for ( i = (double *)xmmword_1401C63C0; i != *(&xmmword_1401C63C0 + 1); i += 7 )
  {
    if ( *(_DWORD *)i == 17301505 )
    {
      if ( *((_DWORD *)i + 6) == 0x10000 && !*((_DWORD *)i + 9) )
      {
        v0 = i[1];
        v1 = i[5];
      }
    }
    else if ( *(_DWORD *)i == 16777218 && *((_DWORD *)i + 6) == 0x4000 && !*((_DWORD *)i + 9) )
    {
      v2 = i[1];
      v3 = i[5];
    }
  }
  if ( v0 == 1.797693134862316e308 || v2 == 1.797693134862316e308 )
  {
    dbl_140168930 = DOUBLE_1_797693134862316e308;
  }
  else
  {
    v5 = fmin(5.9, v0);
    dbl_140168930 = (v2 + v0) * 0.5;
    if ( v5 > dbl_140168930 )
    {
      dbl_140168930 = v5;
      Log_Text_F(
        (__int64)"base\\winsat\\exe\\processresults.cpp",
        1302,
        "Using the sequential read subscore (capped at 5.9) for final disk score rather than the combined sequential + ra"
        "ndom disk subscores.");
    }
    if ( v3 != 1.797693134862316e308 )
    {
      if ( App::s_isAxeMode
        || (v6 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
            !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v6))
        || App::s_WsSwapTest
        || !App::s_RegistryCreated )
      {
        Log_Text_F(
          (__int64)"base\\winsat\\exe\\processresults.cpp",
          1326,
          "Skipping Registry Entry for random read disk score");
      }
      else
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v10,
          L"RandomReadDiskScore");
        mlib::DWORDReg::DWORDReg(v11);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v10);
        v7 = (unsigned int)(int)(v3 * 1024.0);
        mlib::DWORDReg::operator=(v11, v7);
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v11) )
        {
          LastError = GetLastError();
          v14 = 1;
          v15 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          Log_Text_F(
            (__int64)"base\\winsat\\exe\\processresults.cpp",
            1319,
            "ERROR: Can't write random read disk score (throughput) to the registry %u: %s",
            v7,
            Buffer);
        }
        else
        {
          Log_Text_F(
            (__int64)"base\\winsat\\exe\\processresults.cpp",
            1323,
            "> Wrote random read disk score (throughput) to the registry %u",
            v7);
        }
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v11);
      }
    }
    if ( v1 != 1.797693134862316e308 )
    {
      if ( App::s_isAxeMode
        || (v8 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&App::s_xmlTestFile),
            !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(v8))
        || App::s_WsSwapTest
        || !App::s_RegistryCreated )
      {
        Log_Text_F(
          (__int64)"base\\winsat\\exe\\processresults.cpp",
          1352,
          "Skipping Registry Entry for sequential read disk score");
      }
      else
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
          v10,
          L"SequentialReadDiskScore");
        mlib::DWORDReg::DWORDReg(v11);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v10);
        v9 = (unsigned int)(int)(v1 * 1024.0);
        mlib::DWORDReg::operator=(v11, v9);
        if ( (unsigned int)mlib::MRegistryRWBase::write((mlib::MRegistryRWBase *)v11) )
        {
          LastError = GetLastError();
          v14 = 1;
          v15 = 0;
          mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(Buffer);
          Log_Text_F(
            (__int64)"base\\winsat\\exe\\processresults.cpp",
            1346,
            "ERROR: Can't write sequential read disk score (throughput) to the registry %u: %s",
            v9,
            Buffer);
        }
        else
        {
          Log_Text_F(
            (__int64)"base\\winsat\\exe\\processresults.cpp",
            1349,
            "> Wrote sequential read disk score (throughput) to the registry %u",
            v9);
        }
        mlib::DWORDReg::~DWORDReg((mlib::DWORDReg *)v11);
      }
    }
  }
}

```

## disassembly

```asm
0x14002e584  mov     rax, rsp
0x14002e587  mov     [rax+8], rbx
0x14002e58b  mov     [rax+10h], rsi
0x14002e58f  push    rbp
0x14002e590  lea     rbp, [rax-0E8h]
0x14002e597  sub     rsp, 1E0h
0x14002e59e  movaps  xmmword ptr [rax-18h], xmm6
0x14002e5a2  movaps  xmmword ptr [rax-28h], xmm7
0x14002e5a6  movaps  xmmword ptr [rax-38h], xmm8
0x14002e5ab  mov     rax, cs:__security_cookie
0x14002e5b2  xor     rax, rsp
0x14002e5b5  mov     [rbp+0E0h+var_40], rax
0x14002e5bc  movsd   xmm6, cs:__real@7fefffffffffffff
0x14002e5c4  movaps  xmm1, xmm6
0x14002e5c7  movaps  xmm8, xmm6
0x14002e5cb  movaps  xmm0, xmm6
0x14002e5ce  movaps  xmm7, xmm6
0x14002e5d1  mov     rax, qword ptr cs:xmmword_1401C63C0
0x14002e5d8  cmp     rax, qword ptr cs:xmmword_1401C63C0+8
0x14002e5df  jz      short loc_14002E62C
0x14002e5e1  cmp     dword ptr [rax], 1080001h
0x14002e5e7  jnz     short loc_14002E605
0x14002e5e9  cmp     dword ptr [rax+18h], 10000h
0x14002e5f0  jnz     short loc_14002E626
0x14002e5f2  cmp     dword ptr [rax+24h], 0
0x14002e5f6  jnz     short loc_14002E626
0x14002e5f8  movsd   xmm1, qword ptr [rax+8]
0x14002e5fd  movsd   xmm8, qword ptr [rax+28h]
0x14002e603  jmp     short loc_14002E626
0x14002e605  cmp     dword ptr [rax], 1000002h
0x14002e60b  jnz     short loc_14002E626
0x14002e60d  cmp     dword ptr [rax+18h], 4000h
0x14002e614  jnz     short loc_14002E626
0x14002e616  cmp     dword ptr [rax+24h], 0
0x14002e61a  jnz     short loc_14002E626
0x14002e61c  movsd   xmm0, qword ptr [rax+8]
0x14002e621  movsd   xmm7, qword ptr [rax+28h]
0x14002e626  add     rax, 38h ; '8'
0x14002e62a  jmp     short loc_14002E5D8
0x14002e62c  ucomisd xmm1, xmm6
0x14002e630  jp      short loc_14002E634
0x14002e632  jz      short loc_14002E63C
0x14002e634  ucomisd xmm0, xmm6
0x14002e638  jp      short loc_14002E649
0x14002e63a  jnz     short loc_14002E649
0x14002e63c  movsd   cs:dbl_140168930, xmm6
0x14002e644  jmp     loc_14002E8E8
0x14002e649  movsd   xmm2, cs:__real@401799999999999a
0x14002e651  minsd   xmm2, xmm1
0x14002e655  addsd   xmm0, xmm1
0x14002e659  mulsd   xmm0, cs:__real@3fe0000000000000
0x14002e661  movsd   cs:dbl_140168930, xmm0
0x14002e669  lea     rsi, aBaseWinsatExeP; "base\\winsat\\exe\\processresults.cpp"
0x14002e670  comisd  xmm2, xmm0
0x14002e674  jbe     short loc_14002E692
0x14002e676  movsd   cs:dbl_140168930, xmm2
0x14002e67e  lea     r8, aUsingTheSequen; "Using the sequential read subscore (cap"...
0x14002e685  mov     edx, 516h
0x14002e68a  mov     rcx, rsi
0x14002e68d  call    Log_Text_F
0x14002e692  ucomisd xmm7, xmm6
0x14002e696  jp      short loc_14002E69E
0x14002e698  jz      loc_14002E7BC
0x14002e69e  cmp     cs:?s_isAxeMode@App@@2_NA, 0; bool App::s_isAxeMode
0x14002e6a5  jnz     loc_14002E7A8
0x14002e6ab  lea     rcx, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x14002e6b2  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002e6b7  mov     rcx, rax
0x14002e6ba  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x14002e6bf  test    al, al
0x14002e6c1  jz      loc_14002E7A8
0x14002e6c7  cmp     cs:?s_WsSwapTest@App@@2_NA, 0; bool App::s_WsSwapTest
0x14002e6ce  jnz     loc_14002E7A8
0x14002e6d4  cmp     cs:?s_RegistryCreated@App@@2_NA, 0; bool App::s_RegistryCreated
0x14002e6db  jz      loc_14002E7A8
0x14002e6e1  lea     rdx, aRandomreaddisk; "RandomReadDiskScore"
0x14002e6e8  lea     rcx, [rsp+1E0h+var_1B0]
0x14002e6ed  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002e6f2  nop
0x14002e6f3  lea     r8, [rsp+1E0h+var_1B0]
0x14002e6f8  mov     rdx, cs:qword_1401C6370
0x14002e6ff  lea     rcx, [rsp+1E0h+var_1A0]
0x14002e704  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002e709  nop
0x14002e70a  lea     rcx, [rsp+1E0h+var_1B0]
0x14002e70f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002e714  mulsd   xmm7, cs:__real@4090000000000000
0x14002e71c  cvttsd2si rbx, xmm7
0x14002e721  mov     edx, ebx
0x14002e723  lea     rcx, [rsp+1E0h+var_1A0]
0x14002e728  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x14002e72d  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14002e732  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x14002e737  test    eax, eax
0x14002e739  jz      short loc_14002E784
0x14002e73b  call    cs:__imp_GetLastError
0x14002e741  mov     [rbp+0E0h+var_50], eax
0x14002e747  mov     [rbp+0E0h+var_4C], 1
0x14002e74e  mov     [rbp+0E0h+var_48], 0
0x14002e759  lea     rcx, [rbp+0E0h+Buffer]; lpBuffer
0x14002e75d  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x14002e762  lea     rax, [rbp+0E0h+Buffer]
0x14002e766  mov     [rsp+1E0h+var_1C0], rax
0x14002e76b  mov     r9d, ebx
0x14002e76e  lea     r8, aErrorCanTWrite_2; "ERROR: Can't write random read disk sco"...
0x14002e775  mov     edx, 527h
0x14002e77a  mov     rcx, rsi
0x14002e77d  call    Log_Text_F
0x14002e782  jmp     short loc_14002E79C
0x14002e784  mov     r9d, ebx
0x14002e787  lea     r8, aWroteRandomRea_0; "> Wrote random read disk score (through"...
0x14002e78e  mov     edx, 52Bh
0x14002e793  mov     rcx, rsi
0x14002e796  call    Log_Text_F
0x14002e79b  nop
0x14002e79c  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14002e7a1  call    ??1DWORDReg@mlib@@UEAA@XZ; mlib::DWORDReg::~DWORDReg(void)
0x14002e7a6  jmp     short loc_14002E7BC
0x14002e7a8  lea     r8, aSkippingRegist_8; "Skipping Registry Entry for random read"...
0x14002e7af  mov     edx, 52Eh
0x14002e7b4  mov     rcx, rsi
0x14002e7b7  call    Log_Text_F
0x14002e7bc  ucomisd xmm8, xmm6
0x14002e7c1  jp      short loc_14002E7C9
0x14002e7c3  jz      loc_14002E8E8
0x14002e7c9  cmp     cs:?s_isAxeMode@App@@2_NA, 0; bool App::s_isAxeMode
0x14002e7d0  jnz     loc_14002E8D4
0x14002e7d6  lea     rcx, ?s_xmlTestFile@App@@2V?$CSmartPtr@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@@A; CSmartPtr<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>> App::s_xmlTestFile
0x14002e7dd  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14002e7e2  mov     rcx, rax
0x14002e7e5  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x14002e7ea  test    al, al
0x14002e7ec  jz      loc_14002E8D4
0x14002e7f2  cmp     cs:?s_WsSwapTest@App@@2_NA, 0; bool App::s_WsSwapTest
0x14002e7f9  jnz     loc_14002E8D4
0x14002e7ff  cmp     cs:?s_RegistryCreated@App@@2_NA, 0; bool App::s_RegistryCreated
0x14002e806  jz      loc_14002E8D4
0x14002e80c  lea     rdx, aSequentialread_1; "SequentialReadDiskScore"
0x14002e813  lea     rcx, [rsp+1E0h+var_1B0]
0x14002e818  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x14002e81d  nop
0x14002e81e  lea     r8, [rsp+1E0h+var_1B0]
0x14002e823  mov     rdx, cs:qword_1401C6370
0x14002e82a  lea     rcx, [rsp+1E0h+var_1A0]
0x14002e82f  call    ??0DWORDReg@mlib@@QEAA@AEBVRegistryBaseKey@1@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@1@_N@Z; mlib::DWORDReg::DWORDReg(mlib::RegistryBaseKey const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,bool)
0x14002e834  nop
0x14002e835  lea     rcx, [rsp+1E0h+var_1B0]
0x14002e83a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14002e83f  mulsd   xmm8, cs:__real@4090000000000000
0x14002e848  cvttsd2si rbx, xmm8
0x14002e84d  mov     edx, ebx
0x14002e84f  lea     rcx, [rsp+1E0h+var_1A0]
0x14002e854  call    ??4DWORDReg@mlib@@QEAAAEAV01@K@Z; mlib::DWORDReg::operator=(ulong)
0x14002e859  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14002e85e  call    ?write@MRegistryRWBase@mlib@@UEAAHXZ; mlib::MRegistryRWBase::write(void)
0x14002e863  test    eax, eax
0x14002e865  jz      short loc_14002E8B0
0x14002e867  call    cs:__imp_GetLastError
0x14002e86d  mov     [rbp+0E0h+var_50], eax
0x14002e873  mov     [rbp+0E0h+var_4C], 1
0x14002e87a  mov     [rbp+0E0h+var_48], 0
0x14002e885  lea     rcx, [rbp+0E0h+Buffer]; lpBuffer
0x14002e889  call    ?fmt_desc@?$WinErrorT@DU?$char_traits@D@std@@V?$m_traits@D@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<char,std::char_traits<char>,mlib::m_traits<char>>::fmt_desc(void)
0x14002e88e  lea     rax, [rbp+0E0h+Buffer]
0x14002e892  mov     [rsp+1E0h+var_1C0], rax
0x14002e897  mov     r9d, ebx
0x14002e89a  lea     r8, aErrorCanTWrite_7; "ERROR: Can't write sequential read disk"...
0x14002e8a1  mov     edx, 542h
0x14002e8a6  mov     rcx, rsi
0x14002e8a9  call    Log_Text_F
0x14002e8ae  jmp     short loc_14002E8C8
0x14002e8b0  mov     r9d, ebx
0x14002e8b3  lea     r8, aWroteSequentia; "> Wrote sequential read disk score (thr"...
0x14002e8ba  mov     edx, 545h
0x14002e8bf  mov     rcx, rsi
0x14002e8c2  call    Log_Text_F
0x14002e8c7  nop
0x14002e8c8  lea     rcx, [rsp+1E0h+var_1A0]; this
0x14002e8cd  call    ??1DWORDReg@mlib@@UEAA@XZ; mlib::DWORDReg::~DWORDReg(void)
0x14002e8d2  jmp     short loc_14002E8E8
0x14002e8d4  lea     r8, aSkippingRegist_7; "Skipping Registry Entry for sequential "...
0x14002e8db  mov     edx, 548h
0x14002e8e0  mov     rcx, rsi
0x14002e8e3  call    Log_Text_F
0x14002e8e8  mov     rcx, [rbp+0E0h+var_40]
0x14002e8ef  xor     rcx, rsp; StackCookie
0x14002e8f2  call    __security_check_cookie
0x14002e8f7  lea     r11, [rsp+1E0h+var_s0]
0x14002e8ff  mov     rbx, [r11+10h]
0x14002e903  mov     rsi, [r11+18h]
0x14002e907  movaps  xmm6, xmmword ptr [r11-10h]
0x14002e90c  movaps  xmm7, xmmword ptr [r11-20h]
0x14002e911  movaps  xmm8, xmmword ptr [r11-30h]
0x14002e916  mov     rsp, r11
0x14002e919  pop     rbp
0x14002e91a  retn
```
