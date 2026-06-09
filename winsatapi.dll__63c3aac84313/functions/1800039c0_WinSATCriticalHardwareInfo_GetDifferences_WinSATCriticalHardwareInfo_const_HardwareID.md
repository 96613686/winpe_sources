# WinSATCriticalHardwareInfo::GetDifferences(WinSATCriticalHardwareInfo const &,HardwareID)

- ea: `0x1800039c0`
- end: `0x180004039`
- name: `?GetDifferences@WinSATCriticalHardwareInfo@@QEBA?AW4HardwareID@@AEBU1@W42@@Z`
- size: `1657`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004114`

## callees

- `0x1800039c0`
- `0x18000cad4`
- `0x18000e6ac`
- `0x18002a714`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003c76`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003c76`
- `KERNEL32!lstrcmpW` at `0x180003e8e`
- `KERNEL32!lstrcmpW` at `0x180003f8f`
- `KERNEL32!lstrcmpW` at `0x180003e8e`
- `KERNEL32!lstrcmpW` at `0x180003f8f`

## string_xrefs

- `0x180003a10`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003a59`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003ad1`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003b3a`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003b6a`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003b9c`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003ce2`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003d37`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003dc5`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003e40`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003e70`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003ead`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003ee7`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003f27`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003f5f`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003fb1`: `base\winsat\common\loadrecentresults.cpp`
- `0x180003ff4`: `base\winsat\common\loadrecentresults.cpp`
- `0x180004016`: `base\winsat\common\loadrecentresults.cpp`

## pseudocode

```c
__int64 __fastcall WinSATCriticalHardwareInfo::GetDifferences(__int64 a1, __int64 a2, __int16 a3)
{
  signed int v3; // ebp
  __int64 v7; // r9
  __int64 v8; // r9
  signed int i; // ebp
  int v10; // r9d
  int v11; // r9d
  __int64 v12; // r9
  unsigned __int64 j; // r14
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned __int64 *v17; // rcx
  unsigned __int64 *v18; // rax
  unsigned __int64 cchCount2; // r13
  unsigned __int64 v20; // r12
  const WCHAR *v21; // r8
  const WCHAR *lpString2; // rdx
  int v23; // eax
  __int64 v24; // r9
  signed int k; // r14d
  __int64 v26; // r9
  signed int m; // r14d
  __int64 v28; // r9
  int v29; // r9d
  __int64 v30; // r9
  __int64 v32; // [rsp+30h] [rbp-58h]
  __int64 v33; // [rsp+38h] [rbp-50h]
  __int64 v34; // [rsp+40h] [rbp-48h]
  __int64 v35; // [rsp+50h] [rbp-38h]
  _DWORD *v36; // [rsp+A8h] [rbp+20h]

  v3 = 0;
  if ( (a3 & 1) != 0 && !(unsigned __int8)EqualsBiosList<WinsatSystemBoardInfo>(a1 + 8, a2 + 8) )
  {
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      755,
      "We could not find a match for WinsatSystemBoardInfo");
    v7 = *(_QWORD *)(a1 + 8);
    if ( (int)(-1431655765 * ((*(_QWORD *)(a1 + 16) - v7) >> 3)) > 0 )
    {
      do
      {
        LODWORD(v32) = *(_DWORD *)(v7 + 24LL * v3 + 16);
        Log_Text_F(
          "base\\winsat\\common\\loadrecentresults.cpp",
          757,
          "SystemBoardInfo_1[%d]: Manufacturer:%ws, Product:%ws, Type:%lu",
          (unsigned int)v3,
          *(_QWORD *)(*(_QWORD *)(v7 + 24LL * v3) + 24LL),
          *(_QWORD *)(*(_QWORD *)(v7 + 24LL * v3 + 8) + 24LL),
          v32);
        v7 = *(_QWORD *)(a1 + 8);
        ++v3;
      }
      while ( v3 < (int)(-1431655765 * ((*(_QWORD *)(a1 + 16) - v7) >> 3)) );
    }
    v8 = *(_QWORD *)(a2 + 8);
    for ( i = 0; i < (int)(-1431655765 * ((*(_QWORD *)(a2 + 16) - v8) >> 3)); ++i )
    {
      LODWORD(v32) = *(_DWORD *)(v8 + 24LL * i + 16);
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        760,
        "SystemBoardInfo_2[%d]: Manufacturer:%ws, Product:%ws, Type:%lu",
        (unsigned int)i,
        *(_QWORD *)(*(_QWORD *)(v8 + 24LL * i) + 24LL),
        *(_QWORD *)(*(_QWORD *)(v8 + 24LL * i + 8) + 24LL),
        v32);
      v8 = *(_QWORD *)(a2 + 8);
    }
    v3 = 1;
  }
  if ( (a3 & 2) != 0 )
  {
    v10 = *(_DWORD *)(a1 + 32);
    if ( v10 != *(_DWORD *)(a2 + 32) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        768,
        "We could not find a match for CpuManufacturer CPU1:%lu, CPU2:%lu",
        v10,
        *(_DWORD *)(a2 + 32));
      v3 |= 2u;
    }
  }
  if ( (a3 & 4) != 0 )
  {
    v11 = *(_DWORD *)(a1 + 36);
    if ( v11 != *(_DWORD *)(a2 + 36) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        775,
        "We could not find a match for HARDWAREID_CPU_SIG CPUSig1:%lu, CPUSig2:%lu",
        v11,
        *(_DWORD *)(a2 + 36));
      v3 |= 4u;
    }
  }
  if ( (a3 & 8) != 0 )
  {
    v12 = *(_QWORD *)(a1 + 40);
    if ( v12 != *(_QWORD *)(a2 + 40) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        782,
        "We could not find a match for HARDWAREID_MEM_SIZE Size1:%lu Size2:%lu",
        v12,
        *(_QWORD *)(a2 + 40));
      v3 |= 8u;
    }
  }
  if ( (a3 & 0x10) != 0 )
  {
    if ( *(_QWORD *)(a1 + 64) - *(_QWORD *)(a1 + 56) == *(_QWORD *)(a2 + 64) - *(_QWORD *)(a2 + 56) )
    {
      for ( j = 0; ; ++j )
      {
        v14 = *(_QWORD *)(a1 + 56);
        if ( j >= 0xCCCCCCCCCCCCCCCDuLL * ((*(_QWORD *)(a1 + 64) - v14) >> 3) )
          break;
        v15 = 40 * j + *(_QWORD *)(a2 + 56);
        v16 = v14 + 40 * j;
        v36 = (_DWORD *)v15;
        v35 = v16;
        if ( *(_DWORD *)v16 != *(_DWORD *)v15 )
          goto LABEL_36;
        v17 = *(unsigned __int64 **)(v16 + 8);
        v18 = *(unsigned __int64 **)(v15 + 8);
        cchCount2 = *v17;
        v20 = *v18;
        if ( *v17 )
        {
          if ( !v20 )
            goto LABEL_36;
          v21 = (const WCHAR *)v17[3];
          lpString2 = (const WCHAR *)v18[3];
          v23 = cchCount2 >= v20
              ? CompareStringW(0x400u, 0x1001u, v21, v20, lpString2, v20)
              : CompareStringW(0x400u, 0x1001u, v21, cchCount2, lpString2, cchCount2);
          if ( v23 != 2 || cchCount2 != v20 )
            goto LABEL_36;
          v15 = (__int64)v36;
        }
        else if ( v20 )
        {
          goto LABEL_36;
        }
        if ( !mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::eqi(
                (unsigned __int64 **)(v35 + 16),
                (unsigned __int64 **)(v15 + 16))
          || *(_DWORD *)(v35 + 24) != v36[6]
          || *(_DWORD *)(v35 + 28) != v36[7]
          || *(_DWORD *)(v35 + 32) != v36[8] )
        {
          goto LABEL_36;
        }
      }
    }
    else
    {
LABEL_36:
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        789,
        "We could not find a match for HARDWAREID_MEM_DIMMS");
      v24 = *(_QWORD *)(a1 + 56);
      for ( k = 0; k < (int)(-858993459 * ((*(_QWORD *)(a1 + 64) - v24) >> 3)); ++k )
      {
        LODWORD(v34) = *(_DWORD *)(v24 + 40LL * k + 32);
        LODWORD(v33) = *(_DWORD *)(v24 + 40LL * k + 28);
        LODWORD(v32) = *(_DWORD *)(v24 + 40LL * k + 24);
        Log_Text_F(
          "base\\winsat\\common\\loadrecentresults.cpp",
          791,
          "SystemBoardInfo_1[%d]: Manufacturer:%ws, Part_Number:%ws, Form_Factor:%lu Type:%lu Type_Detail:%lu\n",
          (unsigned int)k,
          *(_QWORD *)(*(_QWORD *)(v24 + 40LL * k + 8) + 24LL),
          *(_QWORD *)(*(_QWORD *)(v24 + 40LL * k + 16) + 24LL),
          v32,
          v33,
          v34);
        v24 = *(_QWORD *)(a1 + 56);
      }
      v26 = *(_QWORD *)(a2 + 56);
      for ( m = 0; m < (int)(-858993459 * ((*(_QWORD *)(a2 + 64) - v26) >> 3)); ++m )
      {
        LODWORD(v34) = *(_DWORD *)(v26 + 40LL * m + 32);
        LODWORD(v33) = *(_DWORD *)(v26 + 40LL * m + 28);
        LODWORD(v32) = *(_DWORD *)(v26 + 40LL * m + 24);
        Log_Text_F(
          "base\\winsat\\common\\loadrecentresults.cpp",
          794,
          "SystemBoardInfo_1[%d]: Manufacturer:%ws, Part_Number:%ws, Form_Factor:%lu Type:%lu Type_Detail:%lu\n",
          (unsigned int)m,
          *(_QWORD *)(*(_QWORD *)(v26 + 40LL * m + 8) + 24LL),
          *(_QWORD *)(*(_QWORD *)(v26 + 40LL * m + 16) + 24LL),
          v32,
          v33,
          v34);
        v26 = *(_QWORD *)(a2 + 56);
      }
      v3 |= 0x10u;
    }
  }
  if ( (a3 & 0x20) != 0 )
  {
    v28 = *(_QWORD *)(a1 + 88);
    if ( v28 != *(_QWORD *)(a2 + 88) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        803,
        "We could not find a match for HARDWAREID_DISK_SIZE Size1:%u Size2:%u",
        v28,
        *(_QWORD *)(a2 + 88));
      v3 |= 0x20u;
    }
  }
  if ( (a3 & 0x40) != 0 )
  {
    v29 = *(_DWORD *)(a1 + 84);
    if ( v29 != *(_DWORD *)(a2 + 84) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        810,
        "We could not find a match for HARDWAREID_DISK_NUMBER DiskNum1:%lu DiskNum2:%lu",
        v29,
        *(_DWORD *)(a2 + 84));
      v3 |= 0x40u;
    }
  }
  if ( (a3 & 0x80u) != 0 && lstrcmpW((LPCWSTR)(a1 + 96), (LPCWSTR)(a2 + 96)) )
  {
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      817,
      "We could not find a match for AdapterPnpIdStr String1:%ws String2:%ws\n",
      a1 + 96,
      a2 + 96);
    v3 |= 0x80u;
  }
  if ( (a3 & 0x100) != 0 )
  {
    v30 = *(_QWORD *)(a1 + 232);
    if ( v30 != *(_QWORD *)(a2 + 232) )
    {
      Log_Text_F(
        "base\\winsat\\common\\loadrecentresults.cpp",
        824,
        "We could not find a match for DriverVersion Version1:%lu Version2:%lu",
        v30,
        *(_QWORD *)(a2 + 232));
      v3 |= 0x100u;
    }
  }
  if ( (a3 & 0x200) != 0
    && (*(_BYTE *)(a1 + 225) != *(_BYTE *)(a2 + 225) || *(_BYTE *)(a1 + 224) != *(_BYTE *)(a2 + 224)) )
  {
    Log_Text_F("base\\winsat\\common\\loadrecentresults.cpp", 831, "We could not find a match for fHasWDDMDriver");
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      832,
      "fHasWDDMDriver1:%d fHasWDDMDriver2:%d, IsWDDMDriver1:%d, IsWDDMDriver2:%d",
      *(unsigned __int8 *)(a1 + 225),
      *(unsigned __int8 *)(a2 + 225),
      *(unsigned __int8 *)(a1 + 224),
      *(unsigned __int8 *)(a2 + 224));
    v3 |= 0x200u;
  }
  if ( (a3 & 0x400) != 0 && lstrcmpW((LPCWSTR)(a1 + 240), (LPCWSTR)(a2 + 240)) )
  {
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      839,
      "We could not find a match for WinsatVersionStr Version1:%ws Version2:%ws\n",
      a1 + 240,
      a2 + 240);
    v3 |= 0x400u;
  }
  if ( (a3 & 0x800) != 0 && *(_BYTE *)(a1 + 368) != *(_BYTE *)(a2 + 368) )
  {
    Log_Text_F("base\\winsat\\common\\loadrecentresults.cpp", 846, "We could not find a match for Is64Bit");
    Log_Text_F(
      "base\\winsat\\common\\loadrecentresults.cpp",
      847,
      "Is64Bit1:%d Is64Bit2:%d",
      *(unsigned __int8 *)(a1 + 368),
      *(unsigned __int8 *)(a2 + 368));
    v3 |= 0x800u;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800039c0  mov     rax, rsp
0x1800039c3  push    rbp
0x1800039c4  push    rsi
0x1800039c5  push    rdi
0x1800039c6  sub     rsp, 70h
0x1800039ca  mov     [rax+8], rbx
0x1800039ce  xor     ebp, ebp
0x1800039d0  mov     [rax+10h], r12
0x1800039d4  mov     ebx, r8d
0x1800039d7  mov     [rax-20h], r14
0x1800039db  mov     rsi, rdx
0x1800039de  mov     [rax-28h], r15
0x1800039e2  mov     rdi, rcx
0x1800039e5  test    r8b, 1
0x1800039e9  jz      loc_180003B19
0x1800039ef  add     rdx, 8
0x1800039f3  add     rcx, 8
0x1800039f7  call    ??$EqualsBiosList@UWinsatSystemBoardInfo@@@@YA_NAEBV?$vector@UWinsatSystemBoardInfo@@V?$allocator@UWinsatSystemBoardInfo@@@std@@@std@@0@Z; EqualsBiosList<WinsatSystemBoardInfo>(std::vector<WinsatSystemBoardInfo> const &,std::vector<WinsatSystemBoardInfo> const &)
0x1800039fc  test    al, al
0x1800039fe  jnz     loc_180003B19
0x180003a04  lea     r8, aWeCouldNotFind_9; "We could not find a match for WinsatSys"...
0x180003a0b  mov     edx, 2F3h
0x180003a10  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003a17  call    Log_Text_F
0x180003a1c  mov     r9, [rdi+8]
0x180003a20  mov     r12, 0AAAAAAAAAAAAAAABh
0x180003a2a  mov     rax, [rdi+10h]
0x180003a2e  sub     rax, r9
0x180003a31  sar     rax, 3
0x180003a35  imul    rax, r12
0x180003a39  test    eax, eax
0x180003a3b  jle     short loc_180003A9C
0x180003a3d  movsxd  rax, ebp
0x180003a40  lea     rcx, [rax+rax*2]
0x180003a44  mov     rdx, [r9+rcx*8+8]
0x180003a49  mov     r8, [r9+rcx*8]
0x180003a4d  mov     eax, [r9+rcx*8+10h]
0x180003a52  mov     r9d, ebp
0x180003a55  mov     dword ptr [rsp+88h+var_58], eax
0x180003a59  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003a60  mov     rax, [rdx+18h]
0x180003a64  mov     edx, 2F5h
0x180003a69  mov     qword ptr [rsp+88h+cchCount2], rax
0x180003a6e  mov     rax, [r8+18h]
0x180003a72  lea     r8, aSystemboardinf; "SystemBoardInfo_1[%d]: Manufacturer:%ws"...
0x180003a79  mov     [rsp+88h+lpString2], rax
0x180003a7e  call    Log_Text_F
0x180003a83  mov     r9, [rdi+8]
0x180003a87  inc     ebp
0x180003a89  mov     rax, [rdi+10h]
0x180003a8d  sub     rax, r9
0x180003a90  sar     rax, 3
0x180003a94  imul    rax, r12
0x180003a98  cmp     ebp, eax
0x180003a9a  jl      short loc_180003A3D
0x180003a9c  mov     r9, [rsi+8]
0x180003aa0  xor     ebp, ebp
0x180003aa2  mov     rax, [rsi+10h]
0x180003aa6  sub     rax, r9
0x180003aa9  sar     rax, 3
0x180003aad  imul    rax, r12
0x180003ab1  test    eax, eax
0x180003ab3  jle     short loc_180003B14
0x180003ab5  movsxd  rax, ebp
0x180003ab8  lea     rcx, [rax+rax*2]
0x180003abc  mov     rdx, [r9+rcx*8+8]
0x180003ac1  mov     r8, [r9+rcx*8]
0x180003ac5  mov     eax, [r9+rcx*8+10h]
0x180003aca  mov     r9d, ebp
0x180003acd  mov     dword ptr [rsp+88h+var_58], eax
0x180003ad1  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003ad8  mov     rax, [rdx+18h]
0x180003adc  mov     edx, 2F8h
0x180003ae1  mov     qword ptr [rsp+88h+cchCount2], rax
0x180003ae6  mov     rax, [r8+18h]
0x180003aea  lea     r8, aSystemboardinf_1; "SystemBoardInfo_2[%d]: Manufacturer:%ws"...
0x180003af1  mov     [rsp+88h+lpString2], rax
0x180003af6  call    Log_Text_F
0x180003afb  mov     r9, [rsi+8]
0x180003aff  inc     ebp
0x180003b01  mov     rax, [rsi+10h]
0x180003b05  sub     rax, r9
0x180003b08  sar     rax, 3
0x180003b0c  imul    rax, r12
0x180003b10  cmp     ebp, eax
0x180003b12  jl      short loc_180003AB5
0x180003b14  mov     ebp, 1
0x180003b19  test    bl, 2
0x180003b1c  jz      short loc_180003B49
0x180003b1e  mov     eax, [rsi+20h]
0x180003b21  mov     r9d, [rdi+20h]
0x180003b25  cmp     r9d, eax
0x180003b28  jz      short loc_180003B49
0x180003b2a  lea     r8, aWeCouldNotFind_8; "We could not find a match for CpuManufa"...
0x180003b31  mov     dword ptr [rsp+88h+lpString2], eax
0x180003b35  mov     edx, 300h
0x180003b3a  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003b41  call    Log_Text_F
0x180003b46  or      ebp, 2
0x180003b49  test    bl, 4
0x180003b4c  jz      short loc_180003B79
0x180003b4e  mov     eax, [rsi+24h]
0x180003b51  mov     r9d, [rdi+24h]
0x180003b55  cmp     r9d, eax
0x180003b58  jz      short loc_180003B79
0x180003b5a  lea     r8, aWeCouldNotFind_10; "We could not find a match for HARDWAREI"...
0x180003b61  mov     dword ptr [rsp+88h+lpString2], eax
0x180003b65  mov     edx, 307h
0x180003b6a  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003b71  call    Log_Text_F
0x180003b76  or      ebp, 4
0x180003b79  test    bl, 8
0x180003b7c  jz      short loc_180003BAB
0x180003b7e  mov     rax, [rsi+28h]
0x180003b82  mov     r9, [rdi+28h]
0x180003b86  cmp     r9, rax
0x180003b89  jz      short loc_180003BAB
0x180003b8b  lea     r8, aWeCouldNotFind; "We could not find a match for HARDWAREI"...
0x180003b92  mov     [rsp+88h+lpString2], rax
0x180003b97  mov     edx, 30Eh
0x180003b9c  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003ba3  call    Log_Text_F
0x180003ba8  or      ebp, 8
0x180003bab  test    bl, 10h
0x180003bae  jz      loc_180003E15
0x180003bb4  mov     rcx, [rsi+40h]
0x180003bb8  mov     r15, 0CCCCCCCCCCCCCCCDh
0x180003bc2  mov     rax, [rdi+40h]
0x180003bc6  sub     rcx, [rsi+38h]
0x180003bca  sub     rax, [rdi+38h]
0x180003bce  mov     [rsp+88h+arg_10], r13
0x180003bd6  cmp     rax, rcx
0x180003bd9  jnz     loc_180003CD6
0x180003bdf  xor     r14d, r14d
0x180003be2  mov     rdx, [rdi+38h]
0x180003be6  mov     rax, [rdi+40h]
0x180003bea  sub     rax, rdx
0x180003bed  sar     rax, 3
0x180003bf1  imul    rax, r15
0x180003bf5  cmp     r14, rax
0x180003bf8  jnb     loc_180003E0D
0x180003bfe  mov     r8, [rsi+38h]
0x180003c02  lea     rax, [r14+r14*4]
0x180003c06  lea     rcx, ds:0[rax*8]
0x180003c0e  add     r8, rcx
0x180003c11  add     rcx, rdx
0x180003c14  mov     [rsp+88h+arg_18], r8
0x180003c1c  mov     [rsp+88h+var_38], rcx
0x180003c21  mov     eax, [r8]
0x180003c24  cmp     [rcx], eax
0x180003c26  jnz     loc_180003CD6
0x180003c2c  mov     rcx, [rcx+8]
0x180003c30  mov     rax, [r8+8]
0x180003c34  mov     r13, [rcx]
0x180003c37  mov     r12, [rax]
0x180003c3a  test    r13, r13
0x180003c3d  jz      short loc_180003C90
0x180003c3f  test    r12, r12
0x180003c42  jz      loc_180003CD6
0x180003c48  mov     r8, [rcx+18h]; lpString1
0x180003c4c  mov     ecx, 400h; Locale
0x180003c51  mov     rdx, [rax+18h]
0x180003c55  cmp     r13, r12
0x180003c58  jnb     short loc_180003C64
0x180003c5a  mov     [rsp+88h+cchCount2], r13d
0x180003c5f  mov     r9d, r13d
0x180003c62  jmp     short loc_180003C6C
0x180003c64  mov     [rsp+88h+cchCount2], r12d; cchCount2
0x180003c69  mov     r9d, r12d; cchCount1
0x180003c6c  mov     [rsp+88h+lpString2], rdx; lpString2
0x180003c71  mov     edx, 1001h; dwCmpFlags
0x180003c76  call    cs:__imp_CompareStringW
0x180003c7c  add     eax, 0FFFFFFFEh
0x180003c7f  jnz     short loc_180003CD6
0x180003c81  cmp     r13, r12
0x180003c84  jnz     short loc_180003CD6
0x180003c86  mov     r8, [rsp+88h+arg_18]
0x180003c8e  jmp     short loc_180003C95
0x180003c90  test    r12, r12
0x180003c93  jnz     short loc_180003CD6
0x180003c95  mov     r13, [rsp+88h+var_38]
0x180003c9a  lea     rdx, [r8+10h]
0x180003c9e  lea     rcx, [r13+10h]
0x180003ca2  call    ?eqi@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NAEBV12@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::eqi(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x180003ca7  test    al, al
0x180003ca9  jz      short loc_180003CD6
0x180003cab  mov     rcx, [rsp+88h+arg_18]
0x180003cb3  mov     eax, [rcx+18h]
0x180003cb6  cmp     [r13+18h], eax
0x180003cba  jnz     short loc_180003CD6
0x180003cbc  mov     eax, [rcx+1Ch]
0x180003cbf  cmp     [r13+1Ch], eax
0x180003cc3  jnz     short loc_180003CD6
0x180003cc5  mov     eax, [rcx+20h]
0x180003cc8  cmp     [r13+20h], eax
0x180003ccc  jnz     short loc_180003CD6
0x180003cce  inc     r14
0x180003cd1  jmp     loc_180003BE2
0x180003cd6  lea     r8, aWeCouldNotFind_4; "We could not find a match for HARDWAREI"...
0x180003cdd  mov     edx, 315h
0x180003ce2  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003ce9  call    Log_Text_F
0x180003cee  mov     r9, [rdi+38h]
0x180003cf2  xor     r14d, r14d
0x180003cf5  mov     rax, [rdi+40h]
0x180003cf9  sub     rax, r9
0x180003cfc  sar     rax, 3
0x180003d00  imul    rax, r15
0x180003d04  test    eax, eax
0x180003d06  jle     short loc_180003D7C
0x180003d08  movsxd  rax, r14d
0x180003d0b  lea     rcx, [rax+rax*4]
0x180003d0f  mov     eax, [r9+rcx*8+20h]
0x180003d14  mov     rdx, [r9+rcx*8+10h]
0x180003d19  mov     r8, [r9+rcx*8+8]
0x180003d1e  mov     [rsp+88h+var_48], eax
0x180003d22  mov     eax, [r9+rcx*8+1Ch]
0x180003d27  mov     dword ptr [rsp+88h+var_50], eax
0x180003d2b  mov     eax, [r9+rcx*8+18h]
0x180003d30  mov     r9d, r14d
0x180003d33  mov     dword ptr [rsp+88h+var_58], eax
0x180003d37  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003d3e  mov     rax, [rdx+18h]
0x180003d42  mov     edx, 317h
0x180003d47  mov     qword ptr [rsp+88h+cchCount2], rax
0x180003d4c  mov     rax, [r8+18h]
0x180003d50  lea     r8, aSystemboardinf_0; "SystemBoardInfo_1[%d]: Manufacturer:%ws"...
0x180003d57  mov     [rsp+88h+lpString2], rax
0x180003d5c  call    Log_Text_F
0x180003d61  mov     r9, [rdi+38h]
0x180003d65  inc     r14d
0x180003d68  mov     rax, [rdi+40h]
0x180003d6c  sub     rax, r9
0x180003d6f  sar     rax, 3
0x180003d73  imul    rax, r15
0x180003d77  cmp     r14d, eax
0x180003d7a  jl      short loc_180003D08
0x180003d7c  mov     r9, [rsi+38h]
0x180003d80  xor     r14d, r14d
0x180003d83  mov     rax, [rsi+40h]
0x180003d87  sub     rax, r9
0x180003d8a  sar     rax, 3
0x180003d8e  imul    rax, r15
0x180003d92  test    eax, eax
0x180003d94  jle     short loc_180003E0A
0x180003d96  movsxd  rax, r14d
0x180003d99  lea     rcx, [rax+rax*4]
0x180003d9d  mov     eax, [r9+rcx*8+20h]
0x180003da2  mov     rdx, [r9+rcx*8+10h]
0x180003da7  mov     r8, [r9+rcx*8+8]
0x180003dac  mov     [rsp+88h+var_48], eax
0x180003db0  mov     eax, [r9+rcx*8+1Ch]
0x180003db5  mov     dword ptr [rsp+88h+var_50], eax
0x180003db9  mov     eax, [r9+rcx*8+18h]
0x180003dbe  mov     r9d, r14d
0x180003dc1  mov     dword ptr [rsp+88h+var_58], eax
0x180003dc5  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003dcc  mov     rax, [rdx+18h]
0x180003dd0  mov     edx, 31Ah
0x180003dd5  mov     qword ptr [rsp+88h+cchCount2], rax
0x180003dda  mov     rax, [r8+18h]
0x180003dde  lea     r8, aSystemboardinf_0; "SystemBoardInfo_1[%d]: Manufacturer:%ws"...
0x180003de5  mov     [rsp+88h+lpString2], rax
0x180003dea  call    Log_Text_F
0x180003def  mov     r9, [rsi+38h]
0x180003df3  inc     r14d
0x180003df6  mov     rax, [rsi+40h]
0x180003dfa  sub     rax, r9
0x180003dfd  sar     rax, 3
0x180003e01  imul    rax, r15
0x180003e05  cmp     r14d, eax
0x180003e08  jl      short loc_180003D96
0x180003e0a  or      ebp, 10h
0x180003e0d  mov     r13, [rsp+88h+arg_10]
0x180003e15  mov     r12, [rsp+88h+arg_8]
0x180003e1d  test    bl, 20h
0x180003e20  jz      short loc_180003E4F
0x180003e22  mov     rax, [rsi+58h]
0x180003e26  mov     r9, [rdi+58h]
0x180003e2a  cmp     r9, rax
0x180003e2d  jz      short loc_180003E4F
0x180003e2f  lea     r8, aWeCouldNotFind_3; "We could not find a match for HARDWAREI"...
0x180003e36  mov     [rsp+88h+lpString2], rax
0x180003e3b  mov     edx, 323h
0x180003e40  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003e47  call    Log_Text_F
0x180003e4c  or      ebp, 20h
0x180003e4f  test    bl, 40h
0x180003e52  jz      short loc_180003E7F
0x180003e54  mov     eax, [rsi+54h]
0x180003e57  mov     r9d, [rdi+54h]
0x180003e5b  cmp     r9d, eax
0x180003e5e  jz      short loc_180003E7F
0x180003e60  lea     r8, aWeCouldNotFind_7; "We could not find a match for HARDWAREI"...
0x180003e67  mov     dword ptr [rsp+88h+lpString2], eax
0x180003e6b  mov     edx, 32Ah
0x180003e70  lea     rcx, aBaseWinsatComm_0; "base\\winsat\\common\\loadrecentresults"...
0x180003e77  call    Log_Text_F
0x180003e7c  or      ebp, 40h
0x180003e7f  test    bl, bl
  ... truncated ...
```
