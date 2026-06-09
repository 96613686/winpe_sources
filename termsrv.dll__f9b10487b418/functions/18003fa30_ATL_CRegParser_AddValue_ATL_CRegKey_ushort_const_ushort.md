# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18003fa30`
- end: `0x18003ffb0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180049454`

## callees

- `0x1800321f0`
- `0x1800330c4`
- `0x18003864c`
- `0x18003bc94`
- `0x18003d940`
- `0x18003dbc8`
- `0x18003fa30`
- `0x18003ffb8`
- `0x180040124`
- `0x180047cd8`
- `0x18004ae74`
- `0x1800c4da0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fc72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fd05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ff03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ff5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fc72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003fd05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ff03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ff5a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003fbed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003fc09`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003fbed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003fc09`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003facb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003facb`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18003fcbe`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18003fcbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v6; // r15
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  HKEY *v14; // r13
  WCHAR *j; // r14
  const WCHAR *v16; // rax
  DWORD cbData; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // edi
  HRESULT v22; // edi
  __int64 v23; // rsi
  DWORD v24; // r14d
  size_t v25; // rdi
  unsigned __int64 v26; // rax
  BYTE *v27; // rcx
  HKEY *v28; // r15
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21B0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-21A8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-21A0h]
  HKEY *v38; // [rsp+50h] [rbp-2198h]
  ATL::CRegParser *v39; // [rsp+58h] [rbp-2190h]
  const WCHAR *v40; // [rsp+60h] [rbp-2188h]
  size_t v41; // [rsp+70h] [rbp-2178h]
  HKEY *v42; // [rsp+78h] [rbp-2170h]
  unsigned __int16 *v43; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v38 = a2;
  v6 = this;
  v35 = this;
  *(_QWORD *)Data = a2;
  v39 = this;
  v42 = a2;
  v40 = a3;
  v43 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result < 0 )
    return result;
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
      return 2147614729LL;
    if ( !lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace(v6);
  result = ATL::CRegParser::NextToken(v6, String1);
  if ( (int)result < 0 )
    return result;
  switch ( v10 )
  {
    case 8:
      v32 = -1;
      do
        ++v32;
      while ( String1[v32] );
      v21 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
      goto LABEL_80;
    case 17:
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      *(_DWORD *)Data = v23;
      if ( (v23 & 1) != 0 )
        return 2147500037LL;
      v24 = (int)v23 / 2;
      lpData = 0;
      v25 = (int)v23 / 2;
      v41 = v25;
      try
      {
        v26 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v26 <= 0x100 )
        {
          v27 = v45;
          lpData = v45;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v26);
          v27 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v23) = *(_DWORD *)Data;
        v27 = lpData;
        v25 = v41;
        v35 = v39;
        v28 = v42;
        lpValueName = v40;
        v24 = v41;
        goto LABEL_47;
      }
      v28 = v38;
LABEL_47:
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_76:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_34;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_74:
            v31 = v30 - 87;
            goto LABEL_75;
          }
LABEL_73:
          v31 = 0;
          goto LABEL_75;
        }
        if ( v30 == 97 )
          goto LABEL_74;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_61;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_73;
        v31 = v30 - 55;
LABEL_75:
        lpData[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v23 )
          goto LABEL_76;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_73;
LABEL_61:
      v31 = v30 - 48;
      goto LABEL_75;
    case 19:
      pulOut = 0;
      v35 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v21 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
      return (unsigned int)v22;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      lpData = 0;
      try
      {
        v12 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v12 <= 0x100 )
        {
          v13 = v45;
          lpData = v45;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
          v13 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        v13 = lpData;
        v14 = *(HKEY **)Data;
        v35 = v39;
        lpValueName = v40;
        goto LABEL_18;
      }
      v14 = v38;
LABEL_18:
      if ( v13 )
      {
        for ( j = String1; *j; v13 += 2 )
        {
          v16 = CharNextW(j);
          if ( *j == 92 && *v16 == 48 )
          {
            *(_WORD *)v13 = 0;
            j = CharNextW(v16);
          }
          else
          {
            *(_WORD *)v13 = *j++;
          }
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v18 = lpData;
        do
        {
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)&v18[2 * v19] );
          v20 = (unsigned int)(v19 + 1);
          v18 += 2 * v20;
          cbData += 2 * v20;
        }
        while ( (_DWORD)v20 != 1 );
        v21 = RegSetValueExW(*v14, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_34:
      v6 = v35;
LABEL_80:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v43);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_82;
  }
}

```

## disassembly

```asm
0x18003fa30  push    rbx
0x18003fa32  push    rsi
0x18003fa33  push    rdi
0x18003fa34  push    r12
0x18003fa36  push    r13
0x18003fa38  push    r14
0x18003fa3a  push    r15
0x18003fa3c  mov     eax, 21B0h
0x18003fa41  call    _alloca_probe
0x18003fa46  sub     rsp, rax
0x18003fa49  mov     rax, cs:__security_cookie
0x18003fa50  xor     rax, rsp
0x18003fa53  mov     [rsp+21E8h+var_48], rax
0x18003fa5b  mov     r14, r8
0x18003fa5e  mov     [rsp+21E8h+lpValueName], r8
0x18003fa63  mov     r12, rdx
0x18003fa66  mov     [rsp+21E8h+var_2198], rdx
0x18003fa6b  mov     r15, rcx
0x18003fa6e  mov     [rsp+21E8h+var_21B0], rcx
0x18003fa73  mov     qword ptr [rsp+21E8h+Data], rdx
0x18003fa78  mov     [rsp+21E8h+var_2190], rcx
0x18003fa7d  mov     [rsp+21E8h+var_2170], rdx
0x18003fa82  mov     [rsp+21E8h+var_2188], r8
0x18003fa87  mov     [rsp+21E8h+var_2168], r9
0x18003fa8f  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18003fa97  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003fa9c  xor     ebx, ebx
0x18003fa9e  test    eax, eax
0x18003faa0  js      loc_18003FF8D
0x18003faa6  mov     edi, ebx
0x18003faa8  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18003faaf  cmp     edi, 4
0x18003fab2  jnb     loc_18003FF88
0x18003fab8  movsxd  rsi, edi
0x18003fabb  add     rsi, rsi
0x18003fabe  mov     rdx, [r13+rsi*8+0]; lpString2
0x18003fac3  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18003facb  call    cs:__imp_lstrcmpiW
0x18003fad1  test    eax, eax
0x18003fad3  jz      short loc_18003FAD9
0x18003fad5  inc     edi
0x18003fad7  jmp     short loc_18003FAAF
0x18003fad9  movzx   edi, word ptr [r13+rsi*8+8]
0x18003fadf  mov     rcx, r15; this
0x18003fae2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18003fae7  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18003faef  mov     rcx, r15; this
0x18003faf2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003faf7  test    eax, eax
0x18003faf9  js      loc_18003FF8D
0x18003faff  mov     r13d, 8
0x18003fb05  cmp     di, r13w
0x18003fb09  jz      loc_18003FF1D
0x18003fb0f  cmp     di, 11h
0x18003fb13  jz      loc_18003FD1C
0x18003fb19  cmp     di, 13h
0x18003fb1d  jz      loc_18003FCA3
0x18003fb23  mov     eax, 4008h
0x18003fb28  cmp     di, ax
0x18003fb2b  jnz     loc_18003FF6F
0x18003fb31  lea     rcx, [rsp+21E8h+String1]
0x18003fb39  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003fb3d  mov     rax, rsi
0x18003fb40  inc     rax
0x18003fb43  cmp     [rcx+rax*2], bx
0x18003fb47  jnz     short loc_18003FB40
0x18003fb49  add     eax, 2
0x18003fb4c  mov     [rsp+21E8h+var_2158], rbx
0x18003fb54  movsxd  rcx, eax
0x18003fb57  mov     r15d, 2
0x18003fb5d  mov     edx, r15d
0x18003fb60  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003fb65  cmp     rax, 100h
0x18003fb6b  jbe     short loc_18003FB87
0x18003fb6d  mov     rdx, rax
0x18003fb70  lea     rcx, [rsp+21E8h+var_2158]
0x18003fb78  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003fb7d  mov     rdi, [rsp+21E8h+var_2158]
0x18003fb85  jmp     short loc_18003FB97
0x18003fb87  lea     rdi, [rsp+21E8h+var_2150]
0x18003fb8f  mov     [rsp+21E8h+var_2158], rdi
0x18003fb97  mov     r13, [rsp+21E8h+var_2198]
0x18003fb9c  jmp     short loc_18003FBC9
0x18003fb9e  xor     ebx, ebx
0x18003fba0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003fba4  lea     r15d, [rbx+2]
0x18003fba8  mov     rdi, [rsp+21E8h+var_2158]
0x18003fbb0  mov     r13, qword ptr [rsp+21E8h+Data]
0x18003fbb5  mov     rax, [rsp+21E8h+var_2190]
0x18003fbba  mov     [rsp+21E8h+var_21B0], rax
0x18003fbbf  mov     rax, [rsp+21E8h+var_2188]
0x18003fbc4  mov     [rsp+21E8h+lpValueName], rax
0x18003fbc9  test    rdi, rdi
0x18003fbcc  jz      loc_18003FC87
0x18003fbd2  lea     r14, [rsp+21E8h+String1]
0x18003fbda  cmp     [rsp+21E8h+String1], bx
0x18003fbe2  jz      short loc_18003FC23
0x18003fbe4  mov     r12d, 30h ; '0'
0x18003fbea  mov     rcx, r14; lpsz
0x18003fbed  call    cs:__imp_CharNextW
0x18003fbf3  movzx   ecx, word ptr [r14]
0x18003fbf7  cmp     cx, 5Ch ; '\'
0x18003fbfb  jnz     short loc_18003FC14
0x18003fbfd  cmp     [rax], r12w
0x18003fc01  jnz     short loc_18003FC14
0x18003fc03  mov     [rdi], bx
0x18003fc06  mov     rcx, rax; lpsz
0x18003fc09  call    cs:__imp_CharNextW
0x18003fc0f  mov     r14, rax
0x18003fc12  jmp     short loc_18003FC1A
0x18003fc14  mov     [rdi], cx
0x18003fc17  add     r14, r15
0x18003fc1a  add     rdi, r15
0x18003fc1d  cmp     [r14], bx
0x18003fc21  jnz     short loc_18003FBEA
0x18003fc23  mov     dword ptr [rdi], 0
0x18003fc29  mov     r8, [rsp+21E8h+var_2158]
0x18003fc31  test    r8, r8
0x18003fc34  jz      short loc_18003FC7C
0x18003fc36  mov     r10d, ebx
0x18003fc39  mov     r9, r8
0x18003fc3c  mov     rcx, rsi
0x18003fc3f  inc     rcx
0x18003fc42  cmp     [r9+rcx*2], bx
0x18003fc47  jnz     short loc_18003FC3F
0x18003fc49  inc     ecx
0x18003fc4b  lea     r9, [r9+rcx*2]
0x18003fc4f  lea     r10d, [r10+rcx*2]
0x18003fc53  cmp     ecx, 1
0x18003fc56  jnz     short loc_18003FC3C
0x18003fc58  mov     [rsp+21E8h+cbData], r10d; cbData
0x18003fc5d  mov     [rsp+21E8h+lpData], r8; lpData
0x18003fc62  lea     r9d, [rcx+6]; dwType
0x18003fc66  xor     r8d, r8d; Reserved
0x18003fc69  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18003fc6e  mov     rcx, [r13+0]; hKey
0x18003fc72  call    cs:__imp_RegSetValueExW
0x18003fc78  mov     edi, eax
0x18003fc7a  jmp     short loc_18003FC8C
0x18003fc7c  mov     ecx, 80004005h; int
0x18003fc81  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003fc87  mov     edi, 0Eh
0x18003fc8c  lea     rcx, [rsp+21E8h+var_2158]
0x18003fc94  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003fc99  mov     r15, [rsp+21E8h+var_21B0]
0x18003fc9e  jmp     loc_18003FF62
0x18003fca3  mov     [rsp+21E8h+pulOut], ebx
0x18003fca7  mov     [rsp+21E8h+var_21B0], rbx
0x18003fcac  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18003fcb1  xor     r8d, r8d; dwFlags
0x18003fcb4  xor     edx, edx; lcid
0x18003fcb6  lea     rcx, [rsp+21E8h+String1]; strIn
0x18003fcbe  call    cs:__imp_VarUI4FromStr
0x18003fcc4  mov     edi, eax
0x18003fcc6  test    eax, eax
0x18003fcc8  jns     short loc_18003FCDB
0x18003fcca  lea     rcx, [rsp+21E8h+var_21B0]
0x18003fccf  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003fcd4  mov     eax, edi
0x18003fcd6  jmp     loc_18003FF8D
0x18003fcdb  mov     eax, [rsp+21E8h+pulOut]
0x18003fcdf  mov     dword ptr [rsp+21E8h+Data], eax
0x18003fce3  mov     [rsp+21E8h+cbData], 4; cbData
0x18003fceb  lea     rax, [rsp+21E8h+Data]
0x18003fcf0  mov     [rsp+21E8h+lpData], rax; lpData
0x18003fcf5  mov     r9d, 4; dwType
0x18003fcfb  xor     r8d, r8d; Reserved
0x18003fcfe  mov     rdx, r14; lpValueName
0x18003fd01  mov     rcx, [r12]; hKey
0x18003fd05  call    cs:__imp_RegSetValueExW
0x18003fd0b  mov     edi, eax
0x18003fd0d  lea     rcx, [rsp+21E8h+var_21B0]
0x18003fd12  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003fd17  jmp     loc_18003FF62
0x18003fd1c  lea     rax, [rsp+21E8h+String1]
0x18003fd24  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003fd28  inc     rsi
0x18003fd2b  cmp     [rax+rsi*2], bx
0x18003fd2f  jnz     short loc_18003FD28
0x18003fd31  mov     dword ptr [rsp+21E8h+Data], esi
0x18003fd35  test    sil, 1
0x18003fd39  jz      short loc_18003FD45
0x18003fd3b  mov     eax, 80004005h
0x18003fd40  jmp     loc_18003FF8D
0x18003fd45  mov     eax, esi
0x18003fd47  cdq
0x18003fd48  mov     r15d, 2
0x18003fd4e  idiv    r15d
0x18003fd51  movsxd  r14, eax
0x18003fd54  mov     [rsp+21E8h+var_2158], rbx
0x18003fd5c  mov     rdi, r14
0x18003fd5f  mov     [rsp+21E8h+var_2178], r14
0x18003fd64  lea     edx, [r15-1]
0x18003fd68  mov     rcx, r14
0x18003fd6b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003fd70  cmp     rax, 100h
0x18003fd76  jbe     short loc_18003FD92
0x18003fd78  mov     rdx, rax
0x18003fd7b  lea     rcx, [rsp+21E8h+var_2158]
0x18003fd83  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003fd88  mov     rcx, [rsp+21E8h+var_2158]
0x18003fd90  jmp     short loc_18003FDA2
0x18003fd92  lea     rcx, [rsp+21E8h+var_2150]
0x18003fd9a  mov     [rsp+21E8h+var_2158], rcx
0x18003fda2  mov     r15, [rsp+21E8h+var_2198]
0x18003fda7  jmp     short loc_18003FDDC
0x18003fda9  xor     ebx, ebx
0x18003fdab  lea     r13d, [rbx+8]
0x18003fdaf  mov     esi, dword ptr [rsp+21E8h+Data]
0x18003fdb3  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18003fdbb  mov     rdi, [rsp+21E8h+var_2178]
0x18003fdc0  mov     rax, [rsp+21E8h+var_2190]
0x18003fdc5  mov     [rsp+21E8h+var_21B0], rax
0x18003fdca  mov     r15, [rsp+21E8h+var_2170]
0x18003fdcf  mov     rax, [rsp+21E8h+var_2188]
0x18003fdd4  mov     [rsp+21E8h+lpValueName], rax
0x18003fdd9  mov     r14d, edi
0x18003fddc  test    rcx, rcx
0x18003fddf  jnz     short loc_18003FDF3
0x18003fde1  lea     rcx, [rsp+21E8h+var_2158]
0x18003fde9  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003fdee  jmp     loc_18003FD3B
0x18003fdf3  mov     r8, rdi; Size
0x18003fdf6  xor     edx, edx; Val
0x18003fdf8  call    memset_0
0x18003fdfd  mov     r10d, ebx
0x18003fe00  test    esi, esi
0x18003fe02  jle     loc_18003FEE0
0x18003fe08  mov     r12d, 30h ; '0'
0x18003fe0e  mov     eax, r10d
0x18003fe11  movzx   edx, [rsp+rax*2+21E8h+String1]
0x18003fe19  cmp     edx, 61h ; 'a'
0x18003fe1c  ja      short loc_18003FE8B
0x18003fe1e  jz      loc_18003FEAB
0x18003fe24  cmp     edx, 38h ; '8'
0x18003fe27  ja      short loc_18003FE5D
0x18003fe29  jz      short loc_18003FE55
0x18003fe2b  mov     ecx, edx
0x18003fe2d  sub     ecx, r12d
0x18003fe30  jz      short loc_18003FE55
0x18003fe32  sub     ecx, 1
0x18003fe35  jz      short loc_18003FE55
0x18003fe37  sub     ecx, 1
0x18003fe3a  jz      short loc_18003FE55
0x18003fe3c  sub     ecx, 1
0x18003fe3f  jz      short loc_18003FE55
0x18003fe41  sub     ecx, 1
0x18003fe44  jz      short loc_18003FE55
0x18003fe46  sub     ecx, 1
0x18003fe49  jz      short loc_18003FE55
0x18003fe4b  sub     ecx, 1
0x18003fe4e  jz      short loc_18003FE55
0x18003fe50  cmp     ecx, 1
0x18003fe53  jnz     short loc_18003FEA6
0x18003fe55  mov     r9d, edx
0x18003fe58  sub     r9d, r12d
0x18003fe5b  jmp     short loc_18003FEAF
0x18003fe5d  mov     r9d, edx
0x18003fe60  mov     ecx, edx
0x18003fe62  sub     ecx, 39h ; '9'
0x18003fe65  jz      short loc_18003FE55
0x18003fe67  sub     ecx, r13d
0x18003fe6a  jz      short loc_18003FE85
0x18003fe6c  sub     ecx, 1
0x18003fe6f  jz      short loc_18003FE85
0x18003fe71  sub     ecx, 1
0x18003fe74  jz      short loc_18003FE85
0x18003fe76  sub     ecx, 1
0x18003fe79  jz      short loc_18003FE85
0x18003fe7b  sub     ecx, 1
0x18003fe7e  jz      short loc_18003FE85
0x18003fe80  cmp     ecx, 1
0x18003fe83  jnz     short loc_18003FEA6
0x18003fe85  add     r9d, 0FFFFFFC9h
0x18003fe89  jmp     short loc_18003FEAF
0x18003fe8b  mov     ecx, edx
0x18003fe8d  sub     ecx, 62h ; 'b'
0x18003fe90  jz      short loc_18003FEAB
0x18003fe92  sub     ecx, 1
0x18003fe95  jz      short loc_18003FEAB
0x18003fe97  sub     ecx, 1
0x18003fe9a  jz      short loc_18003FEAB
0x18003fe9c  sub     ecx, 1
0x18003fe9f  jz      short loc_18003FEAB
0x18003fea1  cmp     ecx, 1
0x18003fea4  jz      short loc_18003FEAB
0x18003fea6  mov     r9d, ebx
0x18003fea9  jmp     short loc_18003FEAF
0x18003feab  lea     r9d, [rdx-57h]
0x18003feaf  mov     r8d, r10d
0x18003feb2  shr     r8, 1
0x18003feb5  mov     rdx, [rsp+21E8h+var_2158]
0x18003febd  mov     eax, r10d
0x18003fec0  and     eax, 1
0x18003fec3  shl     eax, 2
0x18003fec6  mov     ecx, 4
0x18003fecb  sub     ecx, eax
0x18003fecd  shl     r9b, cl
0x18003fed0  or      [r8+rdx], r9b
0x18003fed4  inc     r10d
  ... truncated ...
```
