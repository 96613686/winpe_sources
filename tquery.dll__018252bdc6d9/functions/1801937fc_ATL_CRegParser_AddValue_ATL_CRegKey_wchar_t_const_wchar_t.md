# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x1801937fc`
- end: `0x180193d7c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180198b48`

## callees

- `0x180177dc8`
- `0x180188d90`
- `0x180189cce`
- `0x18019257c`
- `0x180192700`
- `0x180192b38`
- `0x1801937fc`
- `0x180193d84`
- `0x180193f0c`
- `0x180197c10`
- `0x18019a334`
- `0x180294310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180193a3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180193ad1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180193ccf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180193d26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180193a3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180193ad1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180193ccf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180193d26`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801939b9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801939d5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801939b9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801939d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180193897`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180193897`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180193a8a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180193a8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(ATL::CRegParser *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
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
  wchar_t *v43; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  wchar_t String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

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
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v26);
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
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_76:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, lpData, v24);
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
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
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
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
      ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
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
0x1801937fc  push    rbx
0x1801937fe  push    rsi
0x1801937ff  push    rdi
0x180193800  push    r12
0x180193802  push    r13
0x180193804  push    r14
0x180193806  push    r15
0x180193808  mov     eax, 21B0h
0x18019380d  call    _alloca_probe
0x180193812  sub     rsp, rax
0x180193815  mov     rax, cs:__security_cookie
0x18019381c  xor     rax, rsp
0x18019381f  mov     [rsp+21E8h+var_48], rax
0x180193827  mov     r14, r8
0x18019382a  mov     [rsp+21E8h+lpValueName], r8
0x18019382f  mov     r12, rdx
0x180193832  mov     [rsp+21E8h+var_2198], rdx
0x180193837  mov     r15, rcx
0x18019383a  mov     [rsp+21E8h+var_21B0], rcx
0x18019383f  mov     qword ptr [rsp+21E8h+Data], rdx
0x180193844  mov     [rsp+21E8h+var_2190], rcx
0x180193849  mov     [rsp+21E8h+var_2170], rdx
0x18019384e  mov     [rsp+21E8h+var_2188], r8
0x180193853  mov     [rsp+21E8h+var_2168], r9
0x18019385b  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x180193863  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180193868  xor     ebx, ebx
0x18019386a  test    eax, eax
0x18019386c  js      loc_180193D59
0x180193872  mov     edi, ebx
0x180193874  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18019387b  cmp     edi, 4
0x18019387e  jnb     loc_180193D54
0x180193884  movsxd  rsi, edi
0x180193887  add     rsi, rsi
0x18019388a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18019388f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180193897  call    cs:__imp_lstrcmpiW
0x18019389d  test    eax, eax
0x18019389f  jz      short loc_1801938A5
0x1801938a1  inc     edi
0x1801938a3  jmp     short loc_18019387B
0x1801938a5  movzx   edi, word ptr [r13+rsi*8+8]
0x1801938ab  mov     rcx, r15; this
0x1801938ae  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1801938b3  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x1801938bb  mov     rcx, r15; this
0x1801938be  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1801938c3  test    eax, eax
0x1801938c5  js      loc_180193D59
0x1801938cb  mov     r13d, 8
0x1801938d1  cmp     di, r13w
0x1801938d5  jz      loc_180193CE9
0x1801938db  cmp     di, 11h
0x1801938df  jz      loc_180193AE8
0x1801938e5  cmp     di, 13h
0x1801938e9  jz      loc_180193A6F
0x1801938ef  mov     eax, 4008h
0x1801938f4  cmp     di, ax
0x1801938f7  jnz     loc_180193D3B
0x1801938fd  lea     rcx, [rsp+21E8h+String1]
0x180193905  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180193909  mov     rax, rsi
0x18019390c  inc     rax
0x18019390f  cmp     [rcx+rax*2], bx
0x180193913  jnz     short loc_18019390C
0x180193915  add     eax, 2
0x180193918  mov     [rsp+21E8h+var_2158], rbx
0x180193920  movsxd  rcx, eax
0x180193923  mov     r15d, 2
0x180193929  mov     edx, r15d
0x18019392c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180193931  cmp     rax, 100h
0x180193937  jbe     short loc_180193953
0x180193939  mov     rdx, rax
0x18019393c  lea     rcx, [rsp+21E8h+var_2158]
0x180193944  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180193949  mov     rdi, [rsp+21E8h+var_2158]
0x180193951  jmp     short loc_180193963
0x180193953  lea     rdi, [rsp+21E8h+var_2150]
0x18019395b  mov     [rsp+21E8h+var_2158], rdi
0x180193963  mov     r13, [rsp+21E8h+var_2198]
0x180193968  jmp     short loc_180193995
0x18019396a  xor     ebx, ebx
0x18019396c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180193970  lea     r15d, [rbx+2]
0x180193974  mov     rdi, [rsp+21E8h+var_2158]
0x18019397c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180193981  mov     rax, [rsp+21E8h+var_2190]
0x180193986  mov     [rsp+21E8h+var_21B0], rax
0x18019398b  mov     rax, [rsp+21E8h+var_2188]
0x180193990  mov     [rsp+21E8h+lpValueName], rax
0x180193995  test    rdi, rdi
0x180193998  jz      loc_180193A53
0x18019399e  lea     r14, [rsp+21E8h+String1]
0x1801939a6  cmp     [rsp+21E8h+String1], bx
0x1801939ae  jz      short loc_1801939EF
0x1801939b0  mov     r12d, 30h ; '0'
0x1801939b6  mov     rcx, r14; lpsz
0x1801939b9  call    cs:__imp_CharNextW
0x1801939bf  movzx   ecx, word ptr [r14]
0x1801939c3  cmp     cx, 5Ch ; '\'
0x1801939c7  jnz     short loc_1801939E0
0x1801939c9  cmp     [rax], r12w
0x1801939cd  jnz     short loc_1801939E0
0x1801939cf  mov     [rdi], bx
0x1801939d2  mov     rcx, rax; lpsz
0x1801939d5  call    cs:__imp_CharNextW
0x1801939db  mov     r14, rax
0x1801939de  jmp     short loc_1801939E6
0x1801939e0  mov     [rdi], cx
0x1801939e3  add     r14, r15
0x1801939e6  add     rdi, r15
0x1801939e9  cmp     [r14], bx
0x1801939ed  jnz     short loc_1801939B6
0x1801939ef  mov     dword ptr [rdi], 0
0x1801939f5  mov     r8, [rsp+21E8h+var_2158]
0x1801939fd  test    r8, r8
0x180193a00  jz      short loc_180193A48
0x180193a02  mov     r10d, ebx
0x180193a05  mov     r9, r8
0x180193a08  mov     rcx, rsi
0x180193a0b  inc     rcx
0x180193a0e  cmp     [r9+rcx*2], bx
0x180193a13  jnz     short loc_180193A0B
0x180193a15  inc     ecx
0x180193a17  lea     r9, [r9+rcx*2]
0x180193a1b  lea     r10d, [r10+rcx*2]
0x180193a1f  cmp     ecx, 1
0x180193a22  jnz     short loc_180193A08
0x180193a24  mov     [rsp+21E8h+cbData], r10d; cbData
0x180193a29  mov     [rsp+21E8h+lpData], r8; lpData
0x180193a2e  lea     r9d, [rcx+6]; dwType
0x180193a32  xor     r8d, r8d; Reserved
0x180193a35  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180193a3a  mov     rcx, [r13+0]; hKey
0x180193a3e  call    cs:__imp_RegSetValueExW
0x180193a44  mov     edi, eax
0x180193a46  jmp     short loc_180193A58
0x180193a48  mov     ecx, 80004005h; int
0x180193a4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180193a53  mov     edi, 0Eh
0x180193a58  lea     rcx, [rsp+21E8h+var_2158]
0x180193a60  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x180193a65  mov     r15, [rsp+21E8h+var_21B0]
0x180193a6a  jmp     loc_180193D2E
0x180193a6f  mov     [rsp+21E8h+pulOut], ebx
0x180193a73  mov     [rsp+21E8h+var_21B0], rbx
0x180193a78  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180193a7d  xor     r8d, r8d; dwFlags
0x180193a80  xor     edx, edx; lcid
0x180193a82  lea     rcx, [rsp+21E8h+String1]; strIn
0x180193a8a  call    cs:__imp_VarUI4FromStr
0x180193a90  mov     edi, eax
0x180193a92  test    eax, eax
0x180193a94  jns     short loc_180193AA7
0x180193a96  lea     rcx, [rsp+21E8h+var_21B0]
0x180193a9b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180193aa0  mov     eax, edi
0x180193aa2  jmp     loc_180193D59
0x180193aa7  mov     eax, [rsp+21E8h+pulOut]
0x180193aab  mov     dword ptr [rsp+21E8h+Data], eax
0x180193aaf  mov     [rsp+21E8h+cbData], 4; cbData
0x180193ab7  lea     rax, [rsp+21E8h+Data]
0x180193abc  mov     [rsp+21E8h+lpData], rax; lpData
0x180193ac1  mov     r9d, 4; dwType
0x180193ac7  xor     r8d, r8d; Reserved
0x180193aca  mov     rdx, r14; lpValueName
0x180193acd  mov     rcx, [r12]; hKey
0x180193ad1  call    cs:__imp_RegSetValueExW
0x180193ad7  mov     edi, eax
0x180193ad9  lea     rcx, [rsp+21E8h+var_21B0]
0x180193ade  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180193ae3  jmp     loc_180193D2E
0x180193ae8  lea     rax, [rsp+21E8h+String1]
0x180193af0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180193af4  inc     rsi
0x180193af7  cmp     [rax+rsi*2], bx
0x180193afb  jnz     short loc_180193AF4
0x180193afd  mov     dword ptr [rsp+21E8h+Data], esi
0x180193b01  test    sil, 1
0x180193b05  jz      short loc_180193B11
0x180193b07  mov     eax, 80004005h
0x180193b0c  jmp     loc_180193D59
0x180193b11  mov     eax, esi
0x180193b13  cdq
0x180193b14  mov     r15d, 2
0x180193b1a  idiv    r15d
0x180193b1d  movsxd  r14, eax
0x180193b20  mov     [rsp+21E8h+var_2158], rbx
0x180193b28  mov     rdi, r14
0x180193b2b  mov     [rsp+21E8h+var_2178], r14
0x180193b30  lea     edx, [r15-1]
0x180193b34  mov     rcx, r14
0x180193b37  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180193b3c  cmp     rax, 100h
0x180193b42  jbe     short loc_180193B5E
0x180193b44  mov     rdx, rax
0x180193b47  lea     rcx, [rsp+21E8h+var_2158]
0x180193b4f  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180193b54  mov     rcx, [rsp+21E8h+var_2158]
0x180193b5c  jmp     short loc_180193B6E
0x180193b5e  lea     rcx, [rsp+21E8h+var_2150]
0x180193b66  mov     [rsp+21E8h+var_2158], rcx
0x180193b6e  mov     r15, [rsp+21E8h+var_2198]
0x180193b73  jmp     short loc_180193BA8
0x180193b75  xor     ebx, ebx
0x180193b77  lea     r13d, [rbx+8]
0x180193b7b  mov     esi, dword ptr [rsp+21E8h+Data]
0x180193b7f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180193b87  mov     rdi, [rsp+21E8h+var_2178]
0x180193b8c  mov     rax, [rsp+21E8h+var_2190]
0x180193b91  mov     [rsp+21E8h+var_21B0], rax
0x180193b96  mov     r15, [rsp+21E8h+var_2170]
0x180193b9b  mov     rax, [rsp+21E8h+var_2188]
0x180193ba0  mov     [rsp+21E8h+lpValueName], rax
0x180193ba5  mov     r14d, edi
0x180193ba8  test    rcx, rcx
0x180193bab  jnz     short loc_180193BBF
0x180193bad  lea     rcx, [rsp+21E8h+var_2158]
0x180193bb5  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x180193bba  jmp     loc_180193B07
0x180193bbf  mov     r8, rdi; Size
0x180193bc2  xor     edx, edx; Val
0x180193bc4  call    memset_0
0x180193bc9  mov     r10d, ebx
0x180193bcc  test    esi, esi
0x180193bce  jle     loc_180193CAC
0x180193bd4  mov     r12d, 30h ; '0'
0x180193bda  mov     eax, r10d
0x180193bdd  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180193be5  cmp     edx, 61h ; 'a'
0x180193be8  ja      short loc_180193C57
0x180193bea  jz      loc_180193C77
0x180193bf0  cmp     edx, 38h ; '8'
0x180193bf3  ja      short loc_180193C29
0x180193bf5  jz      short loc_180193C21
0x180193bf7  mov     ecx, edx
0x180193bf9  sub     ecx, r12d
0x180193bfc  jz      short loc_180193C21
0x180193bfe  sub     ecx, 1
0x180193c01  jz      short loc_180193C21
0x180193c03  sub     ecx, 1
0x180193c06  jz      short loc_180193C21
0x180193c08  sub     ecx, 1
0x180193c0b  jz      short loc_180193C21
0x180193c0d  sub     ecx, 1
0x180193c10  jz      short loc_180193C21
0x180193c12  sub     ecx, 1
0x180193c15  jz      short loc_180193C21
0x180193c17  sub     ecx, 1
0x180193c1a  jz      short loc_180193C21
0x180193c1c  cmp     ecx, 1
0x180193c1f  jnz     short loc_180193C72
0x180193c21  mov     r9d, edx
0x180193c24  sub     r9d, r12d
0x180193c27  jmp     short loc_180193C7B
0x180193c29  mov     r9d, edx
0x180193c2c  mov     ecx, edx
0x180193c2e  sub     ecx, 39h ; '9'
0x180193c31  jz      short loc_180193C21
0x180193c33  sub     ecx, r13d
0x180193c36  jz      short loc_180193C51
0x180193c38  sub     ecx, 1
0x180193c3b  jz      short loc_180193C51
0x180193c3d  sub     ecx, 1
0x180193c40  jz      short loc_180193C51
0x180193c42  sub     ecx, 1
0x180193c45  jz      short loc_180193C51
0x180193c47  sub     ecx, 1
0x180193c4a  jz      short loc_180193C51
0x180193c4c  cmp     ecx, 1
0x180193c4f  jnz     short loc_180193C72
0x180193c51  add     r9d, 0FFFFFFC9h
0x180193c55  jmp     short loc_180193C7B
0x180193c57  mov     ecx, edx
0x180193c59  sub     ecx, 62h ; 'b'
0x180193c5c  jz      short loc_180193C77
0x180193c5e  sub     ecx, 1
0x180193c61  jz      short loc_180193C77
0x180193c63  sub     ecx, 1
0x180193c66  jz      short loc_180193C77
0x180193c68  sub     ecx, 1
0x180193c6b  jz      short loc_180193C77
0x180193c6d  cmp     ecx, 1
0x180193c70  jz      short loc_180193C77
0x180193c72  mov     r9d, ebx
0x180193c75  jmp     short loc_180193C7B
0x180193c77  lea     r9d, [rdx-57h]
0x180193c7b  mov     r8d, r10d
0x180193c7e  shr     r8, 1
0x180193c81  mov     rdx, [rsp+21E8h+var_2158]
0x180193c89  mov     eax, r10d
0x180193c8c  and     eax, 1
0x180193c8f  shl     eax, 2
0x180193c92  mov     ecx, 4
0x180193c97  sub     ecx, eax
0x180193c99  shl     r9b, cl
0x180193c9c  or      [r8+rdx], r9b
0x180193ca0  inc     r10d
  ... truncated ...
```
