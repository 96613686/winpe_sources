# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800166ec`
- end: `0x180016c6c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001ae58`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x180014ae8`
- `0x180014f98`
- `0x180015750`
- `0x1800166ec`
- `0x180016c74`
- `0x180016f6c`
- `0x1800172c8`
- `0x180019d40`
- `0x18001b950`
- `0x1800ff490`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001697a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001697a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001692e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800169c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016bbf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016c16`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001692e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800169c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016bbf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016c16`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800168a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800168c5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800168a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800168c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180016787`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180016787`

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
0x1800166ec  push    rbx
0x1800166ee  push    rsi
0x1800166ef  push    rdi
0x1800166f0  push    r12
0x1800166f2  push    r13
0x1800166f4  push    r14
0x1800166f6  push    r15
0x1800166f8  mov     eax, 21B0h
0x1800166fd  call    _alloca_probe
0x180016702  sub     rsp, rax
0x180016705  mov     rax, cs:__security_cookie
0x18001670c  xor     rax, rsp
0x18001670f  mov     [rsp+21E8h+var_48], rax
0x180016717  mov     r14, r8
0x18001671a  mov     [rsp+21E8h+lpValueName], r8
0x18001671f  mov     r12, rdx
0x180016722  mov     [rsp+21E8h+var_2198], rdx
0x180016727  mov     r15, rcx
0x18001672a  mov     [rsp+21E8h+var_21B0], rcx
0x18001672f  mov     qword ptr [rsp+21E8h+Data], rdx
0x180016734  mov     [rsp+21E8h+var_2190], rcx
0x180016739  mov     [rsp+21E8h+var_2170], rdx
0x18001673e  mov     [rsp+21E8h+var_2188], r8
0x180016743  mov     [rsp+21E8h+var_2168], r9
0x18001674b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180016753  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016758  xor     ebx, ebx
0x18001675a  test    eax, eax
0x18001675c  js      loc_180016C49
0x180016762  mov     edi, ebx
0x180016764  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001676b  cmp     edi, 4
0x18001676e  jnb     loc_180016C44
0x180016774  movsxd  rsi, edi
0x180016777  add     rsi, rsi
0x18001677a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001677f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180016787  call    cs:__imp_lstrcmpiW
0x18001678d  test    eax, eax
0x18001678f  jz      short loc_180016795
0x180016791  inc     edi
0x180016793  jmp     short loc_18001676B
0x180016795  movzx   edi, word ptr [r13+rsi*8+8]
0x18001679b  mov     rcx, r15; this
0x18001679e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800167a3  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x1800167ab  mov     rcx, r15; this
0x1800167ae  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800167b3  test    eax, eax
0x1800167b5  js      loc_180016C49
0x1800167bb  mov     r13d, 8
0x1800167c1  cmp     di, r13w
0x1800167c5  jz      loc_180016BD9
0x1800167cb  cmp     di, 11h
0x1800167cf  jz      loc_1800169D8
0x1800167d5  cmp     di, 13h
0x1800167d9  jz      loc_18001695F
0x1800167df  mov     eax, 4008h
0x1800167e4  cmp     di, ax
0x1800167e7  jnz     loc_180016C2B
0x1800167ed  lea     rcx, [rsp+21E8h+String1]
0x1800167f5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800167f9  mov     rax, rsi
0x1800167fc  inc     rax
0x1800167ff  cmp     [rcx+rax*2], bx
0x180016803  jnz     short loc_1800167FC
0x180016805  add     eax, 2
0x180016808  mov     [rsp+21E8h+var_2158], rbx
0x180016810  movsxd  rcx, eax
0x180016813  mov     r15d, 2
0x180016819  mov     edx, r15d
0x18001681c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180016821  cmp     rax, 100h
0x180016827  jbe     short loc_180016843
0x180016829  mov     rdx, rax
0x18001682c  lea     rcx, [rsp+21E8h+var_2158]
0x180016834  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180016839  mov     rdi, [rsp+21E8h+var_2158]
0x180016841  jmp     short loc_180016853
0x180016843  lea     rdi, [rsp+21E8h+var_2150]
0x18001684b  mov     [rsp+21E8h+var_2158], rdi
0x180016853  mov     r13, [rsp+21E8h+var_2198]
0x180016858  jmp     short loc_180016885
0x18001685a  xor     ebx, ebx
0x18001685c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016860  lea     r15d, [rbx+2]
0x180016864  mov     rdi, [rsp+21E8h+var_2158]
0x18001686c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180016871  mov     rax, [rsp+21E8h+var_2190]
0x180016876  mov     [rsp+21E8h+var_21B0], rax
0x18001687b  mov     rax, [rsp+21E8h+var_2188]
0x180016880  mov     [rsp+21E8h+lpValueName], rax
0x180016885  test    rdi, rdi
0x180016888  jz      loc_180016943
0x18001688e  lea     r14, [rsp+21E8h+String1]
0x180016896  cmp     [rsp+21E8h+String1], bx
0x18001689e  jz      short loc_1800168DF
0x1800168a0  mov     r12d, 30h ; '0'
0x1800168a6  mov     rcx, r14; lpsz
0x1800168a9  call    cs:__imp_CharNextW
0x1800168af  movzx   ecx, word ptr [r14]
0x1800168b3  cmp     cx, 5Ch ; '\'
0x1800168b7  jnz     short loc_1800168D0
0x1800168b9  cmp     [rax], r12w
0x1800168bd  jnz     short loc_1800168D0
0x1800168bf  mov     [rdi], bx
0x1800168c2  mov     rcx, rax; lpsz
0x1800168c5  call    cs:__imp_CharNextW
0x1800168cb  mov     r14, rax
0x1800168ce  jmp     short loc_1800168D6
0x1800168d0  mov     [rdi], cx
0x1800168d3  add     r14, r15
0x1800168d6  add     rdi, r15
0x1800168d9  cmp     [r14], bx
0x1800168dd  jnz     short loc_1800168A6
0x1800168df  mov     dword ptr [rdi], 0
0x1800168e5  mov     r8, [rsp+21E8h+var_2158]
0x1800168ed  test    r8, r8
0x1800168f0  jz      short loc_180016938
0x1800168f2  mov     r10d, ebx
0x1800168f5  mov     r9, r8
0x1800168f8  mov     rcx, rsi
0x1800168fb  inc     rcx
0x1800168fe  cmp     [r9+rcx*2], bx
0x180016903  jnz     short loc_1800168FB
0x180016905  inc     ecx
0x180016907  lea     r9, [r9+rcx*2]
0x18001690b  lea     r10d, [r10+rcx*2]
0x18001690f  cmp     ecx, 1
0x180016912  jnz     short loc_1800168F8
0x180016914  mov     [rsp+21E8h+cbData], r10d; cbData
0x180016919  mov     [rsp+21E8h+lpData], r8; lpData
0x18001691e  lea     r9d, [rcx+6]; dwType
0x180016922  xor     r8d, r8d; Reserved
0x180016925  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18001692a  mov     rcx, [r13+0]; hKey
0x18001692e  call    cs:__imp_RegSetValueExW
0x180016934  mov     edi, eax
0x180016936  jmp     short loc_180016948
0x180016938  mov     ecx, 80004005h; int
0x18001693d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180016943  mov     edi, 0Eh
0x180016948  lea     rcx, [rsp+21E8h+var_2158]
0x180016950  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180016955  mov     r15, [rsp+21E8h+var_21B0]
0x18001695a  jmp     loc_180016C1E
0x18001695f  mov     [rsp+21E8h+pulOut], ebx
0x180016963  mov     [rsp+21E8h+var_21B0], rbx
0x180016968  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18001696d  xor     r8d, r8d; dwFlags
0x180016970  xor     edx, edx; lcid
0x180016972  lea     rcx, [rsp+21E8h+String1]; strIn
0x18001697a  call    cs:__imp_VarUI4FromStr
0x180016980  mov     edi, eax
0x180016982  test    eax, eax
0x180016984  jns     short loc_180016997
0x180016986  lea     rcx, [rsp+21E8h+var_21B0]
0x18001698b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180016990  mov     eax, edi
0x180016992  jmp     loc_180016C49
0x180016997  mov     eax, [rsp+21E8h+pulOut]
0x18001699b  mov     dword ptr [rsp+21E8h+Data], eax
0x18001699f  mov     [rsp+21E8h+cbData], 4; cbData
0x1800169a7  lea     rax, [rsp+21E8h+Data]
0x1800169ac  mov     [rsp+21E8h+lpData], rax; lpData
0x1800169b1  mov     r9d, 4; dwType
0x1800169b7  xor     r8d, r8d; Reserved
0x1800169ba  mov     rdx, r14; lpValueName
0x1800169bd  mov     rcx, [r12]; hKey
0x1800169c1  call    cs:__imp_RegSetValueExW
0x1800169c7  mov     edi, eax
0x1800169c9  lea     rcx, [rsp+21E8h+var_21B0]
0x1800169ce  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800169d3  jmp     loc_180016C1E
0x1800169d8  lea     rax, [rsp+21E8h+String1]
0x1800169e0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800169e4  inc     rsi
0x1800169e7  cmp     [rax+rsi*2], bx
0x1800169eb  jnz     short loc_1800169E4
0x1800169ed  mov     dword ptr [rsp+21E8h+Data], esi
0x1800169f1  test    sil, 1
0x1800169f5  jz      short loc_180016A01
0x1800169f7  mov     eax, 80004005h
0x1800169fc  jmp     loc_180016C49
0x180016a01  mov     eax, esi
0x180016a03  cdq
0x180016a04  mov     r15d, 2
0x180016a0a  idiv    r15d
0x180016a0d  movsxd  r14, eax
0x180016a10  mov     [rsp+21E8h+var_2158], rbx
0x180016a18  mov     rdi, r14
0x180016a1b  mov     [rsp+21E8h+var_2178], r14
0x180016a20  lea     edx, [r15-1]
0x180016a24  mov     rcx, r14
0x180016a27  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180016a2c  cmp     rax, 100h
0x180016a32  jbe     short loc_180016A4E
0x180016a34  mov     rdx, rax
0x180016a37  lea     rcx, [rsp+21E8h+var_2158]
0x180016a3f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180016a44  mov     rcx, [rsp+21E8h+var_2158]
0x180016a4c  jmp     short loc_180016A5E
0x180016a4e  lea     rcx, [rsp+21E8h+var_2150]
0x180016a56  mov     [rsp+21E8h+var_2158], rcx
0x180016a5e  mov     r15, [rsp+21E8h+var_2198]
0x180016a63  jmp     short loc_180016A98
0x180016a65  xor     ebx, ebx
0x180016a67  lea     r13d, [rbx+8]
0x180016a6b  mov     esi, dword ptr [rsp+21E8h+Data]
0x180016a6f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180016a77  mov     rdi, [rsp+21E8h+var_2178]
0x180016a7c  mov     rax, [rsp+21E8h+var_2190]
0x180016a81  mov     [rsp+21E8h+var_21B0], rax
0x180016a86  mov     r15, [rsp+21E8h+var_2170]
0x180016a8b  mov     rax, [rsp+21E8h+var_2188]
0x180016a90  mov     [rsp+21E8h+lpValueName], rax
0x180016a95  mov     r14d, edi
0x180016a98  test    rcx, rcx
0x180016a9b  jnz     short loc_180016AAF
0x180016a9d  lea     rcx, [rsp+21E8h+var_2158]
0x180016aa5  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180016aaa  jmp     loc_1800169F7
0x180016aaf  mov     r8, rdi; Size
0x180016ab2  xor     edx, edx; Val
0x180016ab4  call    memset_0
0x180016ab9  mov     r10d, ebx
0x180016abc  test    esi, esi
0x180016abe  jle     loc_180016B9C
0x180016ac4  mov     r12d, 30h ; '0'
0x180016aca  mov     eax, r10d
0x180016acd  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180016ad5  cmp     edx, 61h ; 'a'
0x180016ad8  ja      short loc_180016B47
0x180016ada  jz      loc_180016B67
0x180016ae0  cmp     edx, 38h ; '8'
0x180016ae3  ja      short loc_180016B19
0x180016ae5  jz      short loc_180016B11
0x180016ae7  mov     ecx, edx
0x180016ae9  sub     ecx, r12d
0x180016aec  jz      short loc_180016B11
0x180016aee  sub     ecx, 1
0x180016af1  jz      short loc_180016B11
0x180016af3  sub     ecx, 1
0x180016af6  jz      short loc_180016B11
0x180016af8  sub     ecx, 1
0x180016afb  jz      short loc_180016B11
0x180016afd  sub     ecx, 1
0x180016b00  jz      short loc_180016B11
0x180016b02  sub     ecx, 1
0x180016b05  jz      short loc_180016B11
0x180016b07  sub     ecx, 1
0x180016b0a  jz      short loc_180016B11
0x180016b0c  cmp     ecx, 1
0x180016b0f  jnz     short loc_180016B62
0x180016b11  mov     r9d, edx
0x180016b14  sub     r9d, r12d
0x180016b17  jmp     short loc_180016B6B
0x180016b19  mov     r9d, edx
0x180016b1c  mov     ecx, edx
0x180016b1e  sub     ecx, 39h ; '9'
0x180016b21  jz      short loc_180016B11
0x180016b23  sub     ecx, r13d
0x180016b26  jz      short loc_180016B41
0x180016b28  sub     ecx, 1
0x180016b2b  jz      short loc_180016B41
0x180016b2d  sub     ecx, 1
0x180016b30  jz      short loc_180016B41
0x180016b32  sub     ecx, 1
0x180016b35  jz      short loc_180016B41
0x180016b37  sub     ecx, 1
0x180016b3a  jz      short loc_180016B41
0x180016b3c  cmp     ecx, 1
0x180016b3f  jnz     short loc_180016B62
0x180016b41  add     r9d, 0FFFFFFC9h
0x180016b45  jmp     short loc_180016B6B
0x180016b47  mov     ecx, edx
0x180016b49  sub     ecx, 62h ; 'b'
0x180016b4c  jz      short loc_180016B67
0x180016b4e  sub     ecx, 1
0x180016b51  jz      short loc_180016B67
0x180016b53  sub     ecx, 1
0x180016b56  jz      short loc_180016B67
0x180016b58  sub     ecx, 1
0x180016b5b  jz      short loc_180016B67
0x180016b5d  cmp     ecx, 1
0x180016b60  jz      short loc_180016B67
0x180016b62  mov     r9d, ebx
0x180016b65  jmp     short loc_180016B6B
0x180016b67  lea     r9d, [rdx-57h]
0x180016b6b  mov     r8d, r10d
0x180016b6e  shr     r8, 1
0x180016b71  mov     rdx, [rsp+21E8h+var_2158]
0x180016b79  mov     eax, r10d
0x180016b7c  and     eax, 1
0x180016b7f  shl     eax, 2
0x180016b82  mov     ecx, 4
0x180016b87  sub     ecx, eax
0x180016b89  shl     r9b, cl
0x180016b8c  or      [r8+rdx], r9b
0x180016b90  inc     r10d
  ... truncated ...
```
