# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800257c8`
- end: `0x180025d48`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18002a62c`

## callees

- `0x1800241bb`
- `0x180024610`
- `0x180024850`
- `0x180024cd0`
- `0x1800257c8`
- `0x180025d50`
- `0x180025fe4`
- `0x1800268c8`
- `0x180029ac0`
- `0x18002c1a4`
- `0x180055030`
- `0x1800550f0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180025a0a`
- `ADVAPI32!RegSetValueExW` at `0x180025a9d`
- `ADVAPI32!RegSetValueExW` at `0x180025c9b`
- `ADVAPI32!RegSetValueExW` at `0x180025cf2`
- `ADVAPI32!RegSetValueExW` at `0x180025a0a`
- `ADVAPI32!RegSetValueExW` at `0x180025a9d`
- `ADVAPI32!RegSetValueExW` at `0x180025c9b`
- `ADVAPI32!RegSetValueExW` at `0x180025cf2`
- `KERNEL32!lstrcmpiW` at `0x180025863`
- `KERNEL32!lstrcmpiW` at `0x180025863`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180025a56`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180025a56`
- `USER32!CharNextW` at `0x180025985`
- `USER32!CharNextW` at `0x1800259a1`
- `USER32!CharNextW` at `0x180025985`
- `USER32!CharNextW` at `0x1800259a1`

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
0x1800257c8  push    rbx
0x1800257ca  push    rsi
0x1800257cb  push    rdi
0x1800257cc  push    r12
0x1800257ce  push    r13
0x1800257d0  push    r14
0x1800257d2  push    r15
0x1800257d4  mov     eax, 21B0h
0x1800257d9  call    _alloca_probe
0x1800257de  sub     rsp, rax
0x1800257e1  mov     rax, cs:__security_cookie
0x1800257e8  xor     rax, rsp
0x1800257eb  mov     [rsp+21E8h+var_48], rax
0x1800257f3  mov     r14, r8
0x1800257f6  mov     [rsp+21E8h+lpValueName], r8
0x1800257fb  mov     r12, rdx
0x1800257fe  mov     [rsp+21E8h+var_2198], rdx
0x180025803  mov     r15, rcx
0x180025806  mov     [rsp+21E8h+var_21B0], rcx
0x18002580b  mov     qword ptr [rsp+21E8h+Data], rdx
0x180025810  mov     [rsp+21E8h+var_2190], rcx
0x180025815  mov     [rsp+21E8h+var_2170], rdx
0x18002581a  mov     [rsp+21E8h+var_2188], r8
0x18002581f  mov     [rsp+21E8h+var_2168], r9
0x180025827  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18002582f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180025834  xor     ebx, ebx
0x180025836  test    eax, eax
0x180025838  js      loc_180025D25
0x18002583e  mov     edi, ebx
0x180025840  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180025847  cmp     edi, 4
0x18002584a  jnb     loc_180025D20
0x180025850  movsxd  rsi, edi
0x180025853  add     rsi, rsi
0x180025856  mov     rdx, [r13+rsi*8+0]; lpString2
0x18002585b  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180025863  call    cs:__imp_lstrcmpiW
0x180025869  test    eax, eax
0x18002586b  jz      short loc_180025871
0x18002586d  inc     edi
0x18002586f  jmp     short loc_180025847
0x180025871  movzx   edi, word ptr [r13+rsi*8+8]
0x180025877  mov     rcx, r15; this
0x18002587a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18002587f  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180025887  mov     rcx, r15; this
0x18002588a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002588f  test    eax, eax
0x180025891  js      loc_180025D25
0x180025897  mov     r13d, 8
0x18002589d  cmp     di, r13w
0x1800258a1  jz      loc_180025CB5
0x1800258a7  cmp     di, 11h
0x1800258ab  jz      loc_180025AB4
0x1800258b1  cmp     di, 13h
0x1800258b5  jz      loc_180025A3B
0x1800258bb  mov     eax, 4008h
0x1800258c0  cmp     di, ax
0x1800258c3  jnz     loc_180025D07
0x1800258c9  lea     rcx, [rsp+21E8h+String1]
0x1800258d1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800258d5  mov     rax, rsi
0x1800258d8  inc     rax
0x1800258db  cmp     [rcx+rax*2], bx
0x1800258df  jnz     short loc_1800258D8
0x1800258e1  add     eax, 2
0x1800258e4  mov     [rsp+21E8h+var_2158], rbx
0x1800258ec  movsxd  rcx, eax
0x1800258ef  mov     r15d, 2
0x1800258f5  mov     edx, r15d
0x1800258f8  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800258fd  cmp     rax, 100h
0x180025903  jbe     short loc_18002591F
0x180025905  mov     rdx, rax
0x180025908  lea     rcx, [rsp+21E8h+var_2158]
0x180025910  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180025915  mov     rdi, [rsp+21E8h+var_2158]
0x18002591d  jmp     short loc_18002592F
0x18002591f  lea     rdi, [rsp+21E8h+var_2150]
0x180025927  mov     [rsp+21E8h+var_2158], rdi
0x18002592f  mov     r13, [rsp+21E8h+var_2198]
0x180025934  jmp     short loc_180025961
0x180025936  xor     ebx, ebx
0x180025938  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002593c  lea     r15d, [rbx+2]
0x180025940  mov     rdi, [rsp+21E8h+var_2158]
0x180025948  mov     r13, qword ptr [rsp+21E8h+Data]
0x18002594d  mov     rax, [rsp+21E8h+var_2190]
0x180025952  mov     [rsp+21E8h+var_21B0], rax
0x180025957  mov     rax, [rsp+21E8h+var_2188]
0x18002595c  mov     [rsp+21E8h+lpValueName], rax
0x180025961  test    rdi, rdi
0x180025964  jz      loc_180025A1F
0x18002596a  lea     r14, [rsp+21E8h+String1]
0x180025972  cmp     [rsp+21E8h+String1], bx
0x18002597a  jz      short loc_1800259BB
0x18002597c  mov     r12d, 30h ; '0'
0x180025982  mov     rcx, r14; lpsz
0x180025985  call    cs:__imp_CharNextW
0x18002598b  movzx   ecx, word ptr [r14]
0x18002598f  cmp     cx, 5Ch ; '\'
0x180025993  jnz     short loc_1800259AC
0x180025995  cmp     [rax], r12w
0x180025999  jnz     short loc_1800259AC
0x18002599b  mov     [rdi], bx
0x18002599e  mov     rcx, rax; lpsz
0x1800259a1  call    cs:__imp_CharNextW
0x1800259a7  mov     r14, rax
0x1800259aa  jmp     short loc_1800259B2
0x1800259ac  mov     [rdi], cx
0x1800259af  add     r14, r15
0x1800259b2  add     rdi, r15
0x1800259b5  cmp     [r14], bx
0x1800259b9  jnz     short loc_180025982
0x1800259bb  mov     dword ptr [rdi], 0
0x1800259c1  mov     r8, [rsp+21E8h+var_2158]
0x1800259c9  test    r8, r8
0x1800259cc  jz      short loc_180025A14
0x1800259ce  mov     r10d, ebx
0x1800259d1  mov     r9, r8
0x1800259d4  mov     rcx, rsi
0x1800259d7  inc     rcx
0x1800259da  cmp     [r9+rcx*2], bx
0x1800259df  jnz     short loc_1800259D7
0x1800259e1  inc     ecx
0x1800259e3  lea     r9, [r9+rcx*2]
0x1800259e7  lea     r10d, [r10+rcx*2]
0x1800259eb  cmp     ecx, 1
0x1800259ee  jnz     short loc_1800259D4
0x1800259f0  mov     [rsp+21E8h+cbData], r10d; cbData
0x1800259f5  mov     [rsp+21E8h+lpData], r8; lpData
0x1800259fa  lea     r9d, [rcx+6]; dwType
0x1800259fe  xor     r8d, r8d; Reserved
0x180025a01  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180025a06  mov     rcx, [r13+0]; hKey
0x180025a0a  call    cs:__imp_RegSetValueExW
0x180025a10  mov     edi, eax
0x180025a12  jmp     short loc_180025A24
0x180025a14  mov     ecx, 80004005h; int
0x180025a19  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180025a1f  mov     edi, 0Eh
0x180025a24  lea     rcx, [rsp+21E8h+var_2158]
0x180025a2c  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180025a31  mov     r15, [rsp+21E8h+var_21B0]
0x180025a36  jmp     loc_180025CFA
0x180025a3b  mov     [rsp+21E8h+pulOut], ebx
0x180025a3f  mov     [rsp+21E8h+var_21B0], rbx
0x180025a44  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180025a49  xor     r8d, r8d; dwFlags
0x180025a4c  xor     edx, edx; lcid
0x180025a4e  lea     rcx, [rsp+21E8h+String1]; strIn
0x180025a56  call    cs:__imp_VarUI4FromStr
0x180025a5c  mov     edi, eax
0x180025a5e  test    eax, eax
0x180025a60  jns     short loc_180025A73
0x180025a62  lea     rcx, [rsp+21E8h+var_21B0]
0x180025a67  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180025a6c  mov     eax, edi
0x180025a6e  jmp     loc_180025D25
0x180025a73  mov     eax, [rsp+21E8h+pulOut]
0x180025a77  mov     dword ptr [rsp+21E8h+Data], eax
0x180025a7b  mov     [rsp+21E8h+cbData], 4; cbData
0x180025a83  lea     rax, [rsp+21E8h+Data]
0x180025a88  mov     [rsp+21E8h+lpData], rax; lpData
0x180025a8d  mov     r9d, 4; dwType
0x180025a93  xor     r8d, r8d; Reserved
0x180025a96  mov     rdx, r14; lpValueName
0x180025a99  mov     rcx, [r12]; hKey
0x180025a9d  call    cs:__imp_RegSetValueExW
0x180025aa3  mov     edi, eax
0x180025aa5  lea     rcx, [rsp+21E8h+var_21B0]
0x180025aaa  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180025aaf  jmp     loc_180025CFA
0x180025ab4  lea     rax, [rsp+21E8h+String1]
0x180025abc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180025ac0  inc     rsi
0x180025ac3  cmp     [rax+rsi*2], bx
0x180025ac7  jnz     short loc_180025AC0
0x180025ac9  mov     dword ptr [rsp+21E8h+Data], esi
0x180025acd  test    sil, 1
0x180025ad1  jz      short loc_180025ADD
0x180025ad3  mov     eax, 80004005h
0x180025ad8  jmp     loc_180025D25
0x180025add  mov     eax, esi
0x180025adf  cdq
0x180025ae0  mov     r15d, 2
0x180025ae6  idiv    r15d
0x180025ae9  movsxd  r14, eax
0x180025aec  mov     [rsp+21E8h+var_2158], rbx
0x180025af4  mov     rdi, r14
0x180025af7  mov     [rsp+21E8h+var_2178], r14
0x180025afc  lea     edx, [r15-1]
0x180025b00  mov     rcx, r14
0x180025b03  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180025b08  cmp     rax, 100h
0x180025b0e  jbe     short loc_180025B2A
0x180025b10  mov     rdx, rax
0x180025b13  lea     rcx, [rsp+21E8h+var_2158]
0x180025b1b  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180025b20  mov     rcx, [rsp+21E8h+var_2158]
0x180025b28  jmp     short loc_180025B3A
0x180025b2a  lea     rcx, [rsp+21E8h+var_2150]
0x180025b32  mov     [rsp+21E8h+var_2158], rcx
0x180025b3a  mov     r15, [rsp+21E8h+var_2198]
0x180025b3f  jmp     short loc_180025B74
0x180025b41  xor     ebx, ebx
0x180025b43  lea     r13d, [rbx+8]
0x180025b47  mov     esi, dword ptr [rsp+21E8h+Data]
0x180025b4b  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180025b53  mov     rdi, [rsp+21E8h+var_2178]
0x180025b58  mov     rax, [rsp+21E8h+var_2190]
0x180025b5d  mov     [rsp+21E8h+var_21B0], rax
0x180025b62  mov     r15, [rsp+21E8h+var_2170]
0x180025b67  mov     rax, [rsp+21E8h+var_2188]
0x180025b6c  mov     [rsp+21E8h+lpValueName], rax
0x180025b71  mov     r14d, edi
0x180025b74  test    rcx, rcx
0x180025b77  jnz     short loc_180025B8B
0x180025b79  lea     rcx, [rsp+21E8h+var_2158]
0x180025b81  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180025b86  jmp     loc_180025AD3
0x180025b8b  mov     r8, rdi; Size
0x180025b8e  xor     edx, edx; Val
0x180025b90  call    memset_0
0x180025b95  mov     r10d, ebx
0x180025b98  test    esi, esi
0x180025b9a  jle     loc_180025C78
0x180025ba0  mov     r12d, 30h ; '0'
0x180025ba6  mov     eax, r10d
0x180025ba9  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180025bb1  cmp     edx, 61h ; 'a'
0x180025bb4  ja      short loc_180025C23
0x180025bb6  jz      loc_180025C43
0x180025bbc  cmp     edx, 38h ; '8'
0x180025bbf  ja      short loc_180025BF5
0x180025bc1  jz      short loc_180025BED
0x180025bc3  mov     ecx, edx
0x180025bc5  sub     ecx, r12d
0x180025bc8  jz      short loc_180025BED
0x180025bca  sub     ecx, 1
0x180025bcd  jz      short loc_180025BED
0x180025bcf  sub     ecx, 1
0x180025bd2  jz      short loc_180025BED
0x180025bd4  sub     ecx, 1
0x180025bd7  jz      short loc_180025BED
0x180025bd9  sub     ecx, 1
0x180025bdc  jz      short loc_180025BED
0x180025bde  sub     ecx, 1
0x180025be1  jz      short loc_180025BED
0x180025be3  sub     ecx, 1
0x180025be6  jz      short loc_180025BED
0x180025be8  cmp     ecx, 1
0x180025beb  jnz     short loc_180025C3E
0x180025bed  mov     r9d, edx
0x180025bf0  sub     r9d, r12d
0x180025bf3  jmp     short loc_180025C47
0x180025bf5  mov     r9d, edx
0x180025bf8  mov     ecx, edx
0x180025bfa  sub     ecx, 39h ; '9'
0x180025bfd  jz      short loc_180025BED
0x180025bff  sub     ecx, r13d
0x180025c02  jz      short loc_180025C1D
0x180025c04  sub     ecx, 1
0x180025c07  jz      short loc_180025C1D
0x180025c09  sub     ecx, 1
0x180025c0c  jz      short loc_180025C1D
0x180025c0e  sub     ecx, 1
0x180025c11  jz      short loc_180025C1D
0x180025c13  sub     ecx, 1
0x180025c16  jz      short loc_180025C1D
0x180025c18  cmp     ecx, 1
0x180025c1b  jnz     short loc_180025C3E
0x180025c1d  add     r9d, 0FFFFFFC9h
0x180025c21  jmp     short loc_180025C47
0x180025c23  mov     ecx, edx
0x180025c25  sub     ecx, 62h ; 'b'
0x180025c28  jz      short loc_180025C43
0x180025c2a  sub     ecx, 1
0x180025c2d  jz      short loc_180025C43
0x180025c2f  sub     ecx, 1
0x180025c32  jz      short loc_180025C43
0x180025c34  sub     ecx, 1
0x180025c37  jz      short loc_180025C43
0x180025c39  cmp     ecx, 1
0x180025c3c  jz      short loc_180025C43
0x180025c3e  mov     r9d, ebx
0x180025c41  jmp     short loc_180025C47
0x180025c43  lea     r9d, [rdx-57h]
0x180025c47  mov     r8d, r10d
0x180025c4a  shr     r8, 1
0x180025c4d  mov     rdx, [rsp+21E8h+var_2158]
0x180025c55  mov     eax, r10d
0x180025c58  and     eax, 1
0x180025c5b  shl     eax, 2
0x180025c5e  mov     ecx, 4
0x180025c63  sub     ecx, eax
0x180025c65  shl     r9b, cl
0x180025c68  or      [r8+rdx], r9b
0x180025c6c  inc     r10d
  ... truncated ...
```
