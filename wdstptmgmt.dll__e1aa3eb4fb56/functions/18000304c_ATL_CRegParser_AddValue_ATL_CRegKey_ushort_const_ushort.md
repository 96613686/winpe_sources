# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000304c`
- end: `0x18000353f`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1267`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180004f1c`

## callees

- `0x180002a88`
- `0x180002ae8`
- `0x180002ba4`
- `0x18000304c`
- `0x180003548`
- `0x180003820`
- `0x180003f04`
- `0x180004040`
- `0x180004594`
- `0x180005614`
- `0x18001e9c2`
- `0x18001e9f0`
- `0x18001eab0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800030d1`
- `KERNEL32!lstrcmpiW` at `0x1800030d1`
- `ADVAPI32!RegSetValueExW` at `0x180003283`
- `ADVAPI32!RegSetValueExW` at `0x18000331d`
- `ADVAPI32!RegSetValueExW` at `0x180003486`
- `ADVAPI32!RegSetValueExW` at `0x1800034e0`
- `ADVAPI32!RegSetValueExW` at `0x180003283`
- `ADVAPI32!RegSetValueExW` at `0x18000331d`
- `ADVAPI32!RegSetValueExW` at `0x180003486`
- `ADVAPI32!RegSetValueExW` at `0x1800034e0`
- `USER32!CharNextW` at `0x1800031f1`
- `USER32!CharNextW` at `0x180003213`
- `USER32!CharNextW` at `0x1800031f1`
- `USER32!CharNextW` at `0x180003213`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800032d0`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800032d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r13
  HKEY *v5; // r12
  ATL::CRegParser *v6; // r15
  __int64 result; // rax
  unsigned int v8; // ebx
  int v9; // edi
  LPCWSTR *i; // rsi
  __int16 v11; // di
  __int64 v12; // rax
  unsigned __int64 v13; // rax
  BYTE *v14; // rdi
  WCHAR *j; // r15
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
  __int64 v28; // r9
  unsigned __int8 v29; // al
  unsigned int v30; // r10d
  __int64 v31; // r9
  __int64 v32; // r11
  __int64 v33; // rsi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-21A0h] BYREF
  ATL::CRegParser *v37; // [rsp+40h] [rbp-2198h] BYREF
  ATL::CRegParser *v38; // [rsp+48h] [rbp-2190h]
  struct CRegKey *v39; // [rsp+50h] [rbp-2188h]
  const unsigned __int16 *v40; // [rsp+60h] [rbp-2178h]
  size_t v41; // [rsp+70h] [rbp-2168h]
  unsigned __int16 *v42; // [rsp+78h] [rbp-2160h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v44[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v38 = this;
  v37 = this;
  v39 = (struct CRegKey *)a2;
  v40 = a3;
  v42 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result < 0 )
    return result;
  v9 = 0;
  for ( i = (LPCWSTR *)&`ATL::CRegParser::VTFromRegType'::`2'::map; ; i += 2 )
  {
    if ( (unsigned __int64)v9 >= 4 )
      return 2147614729LL;
    if ( !lstrcmpiW(String1, *i) )
      break;
    ++v9;
  }
  v11 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
  ATL::CRegParser::SkipWhiteSpace(v6);
  result = ATL::CRegParser::NextToken(v6, String1);
  if ( (int)result < 0 )
    return result;
  if ( v11 == 8 )
  {
    v33 = -1;
    do
      ++v33;
    while ( String1[v33] );
    v21 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
    goto LABEL_53;
  }
  if ( v11 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    *(_DWORD *)Data = v23;
    if ( (v23 & 1) == 0 )
    {
      v24 = (int)v23 / 2;
      pulOut = (int)v23 / 2;
      lpData = 0;
      v25 = (int)v23 / 2;
      v41 = v25;
      try
      {
        v26 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v26 <= 0x100 )
        {
          v27 = v44;
          lpData = v44;
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
        v24 = pulOut;
        v27 = lpData;
        v25 = v41;
        v38 = v37;
        v5 = (HKEY *)v39;
        v4 = v40;
      }
      if ( v27 )
      {
        memset_0(v27, 0, v25);
        if ( (int)v23 > 0 )
        {
          v28 = 0;
          do
          {
            v29 = ATL::CRegParser::ChToByte(String1[v28]);
            lpData[(unsigned __int64)v30 >> 1] |= v29 << (4 - 4 * (v30 & 1));
            v28 = v31 + 1;
          }
          while ( v28 < v32 );
        }
        v21 = RegSetValueExW(*v5, v4, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_53;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
    }
    return 2147500037LL;
  }
  if ( v11 != 19 )
  {
    if ( v11 == 16392 )
    {
      v12 = -1;
      do
        ++v12;
      while ( String1[v12] );
      lpData = 0;
      try
      {
        v13 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v13 <= 0x100 )
        {
          v14 = v44;
          lpData = v44;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v13);
          v14 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        v14 = lpData;
        v38 = v37;
        v5 = (HKEY *)v39;
        v4 = v40;
      }
      if ( v14 )
      {
        for ( j = String1; *j; v14 += 2 )
        {
          v16 = CharNextW(j);
          if ( *j == 92 && *v16 == 48 )
          {
            *(_WORD *)v14 = 0;
            j = CharNextW(v16);
          }
          else
          {
            *(_WORD *)v14 = *j++;
          }
        }
        *(_WORD *)v14 = 0;
        *((_WORD *)v14 + 1) = 0;
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
        v21 = RegSetValueExW(*v5, v4, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      goto LABEL_53;
    }
LABEL_56:
    Token = ATL::CRegParser::NextToken(v6, v42);
    if ( Token < 0 )
      return (unsigned int)Token;
    return v8;
  }
  pulOut = 0;
  v37 = 0;
  v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
  if ( v22 < 0 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
    return (unsigned int)v22;
  }
  *(_DWORD *)Data = pulOut;
  v21 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
LABEL_53:
  if ( !v21 )
  {
    v6 = v38;
    goto LABEL_56;
  }
  return ATL::AtlHresultFromWin32(v21);
}

```

## disassembly

```asm
0x18000304c  push    rbx
0x18000304e  push    rsi
0x18000304f  push    rdi
0x180003050  push    r12
0x180003052  push    r13
0x180003054  push    r14
0x180003056  push    r15
0x180003058  mov     eax, 21A0h
0x18000305d  call    _alloca_probe
0x180003062  sub     rsp, rax
0x180003065  mov     rax, cs:__security_cookie
0x18000306c  xor     rax, rsp
0x18000306f  mov     [rsp+21D8h+var_48], rax
0x180003077  mov     r13, r8
0x18000307a  mov     r12, rdx
0x18000307d  mov     r15, rcx
0x180003080  mov     [rsp+21D8h+var_2190], rcx
0x180003085  mov     [rsp+21D8h+var_2198], rcx
0x18000308a  mov     [rsp+21D8h+var_2188], rdx
0x18000308f  mov     [rsp+21D8h+var_2178], r8
0x180003094  mov     [rsp+21D8h+var_2160], r9
0x180003099  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x1800030a1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800030a6  xor     ebx, ebx
0x1800030a8  test    eax, eax
0x1800030aa  js      loc_18000351B
0x1800030b0  mov     edi, ebx
0x1800030b2  lea     rsi, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800030b9  movsxd  r14, edi
0x1800030bc  cmp     r14, 4
0x1800030c0  jnb     loc_180003516
0x1800030c6  mov     rdx, [rsi]; lpString2
0x1800030c9  lea     rcx, [rsp+21D8h+String1]; lpString1
0x1800030d1  call    cs:__imp_lstrcmpiW
0x1800030d8  nop     dword ptr [rax+rax+00h]
0x1800030dd  test    eax, eax
0x1800030df  jz      short loc_1800030E9
0x1800030e1  inc     edi
0x1800030e3  add     rsi, 10h
0x1800030e7  jmp     short loc_1800030B9
0x1800030e9  add     r14, r14
0x1800030ec  lea     rdi, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800030f3  movzx   edi, word ptr [rdi+r14*8+8]
0x1800030f9  mov     rcx, r15; this
0x1800030fc  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180003101  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180003109  mov     rcx, r15; this
0x18000310c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003111  test    eax, eax
0x180003113  js      loc_18000351B
0x180003119  cmp     di, 8
0x18000311d  jz      loc_1800034A3
0x180003123  cmp     di, 11h
0x180003127  jz      loc_18000333A
0x18000312d  cmp     di, 13h
0x180003131  jz      loc_1800032B5
0x180003137  mov     eax, 4008h
0x18000313c  cmp     di, ax
0x18000313f  jnz     loc_180003500
0x180003145  lea     rcx, [rsp+21D8h+String1]
0x18000314d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003151  mov     rax, rsi
0x180003154  inc     rax
0x180003157  cmp     [rcx+rax*2], bx
0x18000315b  jnz     short loc_180003154
0x18000315d  mov     r14d, 2
0x180003163  add     eax, r14d
0x180003166  mov     [rsp+21D8h+var_2158], rbx
0x18000316e  movsxd  rcx, eax
0x180003171  mov     edx, r14d
0x180003174  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180003179  cmp     rax, 100h
0x18000317f  jbe     short loc_18000319B
0x180003181  mov     rdx, rax
0x180003184  lea     rcx, [rsp+21D8h+var_2158]
0x18000318c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003191  mov     rdi, [rsp+21D8h+var_2158]
0x180003199  jmp     short loc_1800031AB
0x18000319b  lea     rdi, [rsp+21D8h+var_2150]
0x1800031a3  mov     [rsp+21D8h+var_2158], rdi
0x1800031ab  jmp     short loc_1800031D3
0x1800031ad  xor     ebx, ebx
0x1800031af  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800031b3  lea     r14d, [rbx+2]
0x1800031b7  mov     rdi, [rsp+21D8h+var_2158]
0x1800031bf  mov     rax, [rsp+21D8h+var_2198]
0x1800031c4  mov     [rsp+21D8h+var_2190], rax
0x1800031c9  mov     r12, [rsp+21D8h+var_2188]
0x1800031ce  mov     r13, [rsp+21D8h+var_2178]
0x1800031d3  test    rdi, rdi
0x1800031d6  jz      loc_18000329E
0x1800031dc  lea     r15, [rsp+21D8h+String1]
0x1800031e4  cmp     [rsp+21D8h+String1], bx
0x1800031ec  jz      short loc_180003234
0x1800031ee  mov     rcx, r15; lpsz
0x1800031f1  call    cs:__imp_CharNextW
0x1800031f8  nop     dword ptr [rax+rax+00h]
0x1800031fd  movzx   ecx, word ptr [r15]
0x180003201  cmp     cx, 5Ch ; '\'
0x180003205  jnz     short loc_180003224
0x180003207  cmp     word ptr [rax], 30h ; '0'
0x18000320b  jnz     short loc_180003224
0x18000320d  mov     [rdi], bx
0x180003210  mov     rcx, rax; lpsz
0x180003213  call    cs:__imp_CharNextW
0x18000321a  nop     dword ptr [rax+rax+00h]
0x18000321f  mov     r15, rax
0x180003222  jmp     short loc_18000322A
0x180003224  mov     [rdi], cx
0x180003227  add     r15, r14
0x18000322a  add     rdi, 2
0x18000322e  cmp     [r15], bx
0x180003232  jnz     short loc_1800031EE
0x180003234  mov     [rdi], bx
0x180003237  mov     [rdi+r14], bx
0x18000323c  mov     r8, [rsp+21D8h+var_2158]
0x180003244  test    r8, r8
0x180003247  jz      short loc_180003293
0x180003249  mov     r10d, ebx
0x18000324c  mov     r9, r8
0x18000324f  mov     rcx, rsi
0x180003252  inc     rcx
0x180003255  cmp     [r9+rcx*2], bx
0x18000325a  jnz     short loc_180003252
0x18000325c  inc     ecx
0x18000325e  lea     r9, [r9+rcx*2]
0x180003262  lea     r10d, [r10+rcx*2]
0x180003266  cmp     ecx, 1
0x180003269  jnz     short loc_18000324F
0x18000326b  mov     [rsp+21D8h+cbData], r10d; cbData
0x180003270  mov     [rsp+21D8h+lpData], r8; lpData
0x180003275  lea     r9d, [rcx+6]; dwType
0x180003279  xor     r8d, r8d; Reserved
0x18000327c  mov     rdx, r13; lpValueName
0x18000327f  mov     rcx, [r12]; hKey
0x180003283  call    cs:__imp_RegSetValueExW
0x18000328a  nop     dword ptr [rax+rax+00h]
0x18000328f  mov     edi, eax
0x180003291  jmp     short loc_1800032A3
0x180003293  mov     ecx, 80004005h; int
0x180003298  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000329e  mov     edi, 0Eh
0x1800032a3  lea     rcx, [rsp+21D8h+var_2158]
0x1800032ab  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800032b0  jmp     loc_1800034EE
0x1800032b5  mov     [rsp+21D8h+pulOut], ebx
0x1800032b9  mov     [rsp+21D8h+var_2198], rbx
0x1800032be  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x1800032c3  xor     r8d, r8d; dwFlags
0x1800032c6  xor     edx, edx; lcid
0x1800032c8  lea     rcx, [rsp+21D8h+String1]; strIn
0x1800032d0  call    cs:__imp_VarUI4FromStr
0x1800032d7  nop     dword ptr [rax+rax+00h]
0x1800032dc  mov     edi, eax
0x1800032de  test    eax, eax
0x1800032e0  jns     short loc_1800032F3
0x1800032e2  lea     rcx, [rsp+21D8h+var_2198]
0x1800032e7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800032ec  mov     eax, edi
0x1800032ee  jmp     loc_18000351B
0x1800032f3  mov     eax, [rsp+21D8h+pulOut]
0x1800032f7  mov     dword ptr [rsp+21D8h+Data], eax
0x1800032fb  mov     [rsp+21D8h+cbData], 4; cbData
0x180003303  lea     rax, [rsp+21D8h+Data]
0x180003308  mov     [rsp+21D8h+lpData], rax; lpData
0x18000330d  mov     r9d, 4; dwType
0x180003313  xor     r8d, r8d; Reserved
0x180003316  mov     rdx, r13; lpValueName
0x180003319  mov     rcx, [r12]; hKey
0x18000331d  call    cs:__imp_RegSetValueExW
0x180003324  nop     dword ptr [rax+rax+00h]
0x180003329  mov     edi, eax
0x18000332b  lea     rcx, [rsp+21D8h+var_2198]
0x180003330  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003335  jmp     loc_1800034EE
0x18000333a  lea     rax, [rsp+21D8h+String1]
0x180003342  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003346  inc     rsi
0x180003349  cmp     [rax+rsi*2], bx
0x18000334d  jnz     short loc_180003346
0x18000334f  mov     dword ptr [rsp+21D8h+Data], esi
0x180003353  test    sil, 1
0x180003357  jz      short loc_180003363
0x180003359  mov     eax, 80004005h
0x18000335e  jmp     loc_18000351B
0x180003363  mov     eax, esi
0x180003365  cdq
0x180003366  mov     r14d, 2
0x18000336c  idiv    r14d
0x18000336f  movsxd  r14, eax
0x180003372  mov     [rsp+21D8h+pulOut], r14d
0x180003377  mov     [rsp+21D8h+var_2158], rbx
0x18000337f  mov     rdi, r14
0x180003382  mov     [rsp+21D8h+var_2168], r14
0x180003387  mov     edx, 1
0x18000338c  mov     rcx, r14
0x18000338f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180003394  cmp     rax, 100h
0x18000339a  jbe     short loc_1800033B6
0x18000339c  mov     rdx, rax
0x18000339f  lea     rcx, [rsp+21D8h+var_2158]
0x1800033a7  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800033ac  mov     rcx, [rsp+21D8h+var_2158]
0x1800033b4  jmp     short loc_1800033C6
0x1800033b6  lea     rcx, [rsp+21D8h+var_2150]
0x1800033be  mov     [rsp+21D8h+var_2158], rcx
0x1800033c6  jmp     short loc_1800033F4
0x1800033c8  xor     ebx, ebx
0x1800033ca  mov     esi, dword ptr [rsp+21D8h+Data]
0x1800033ce  mov     r14d, [rsp+21D8h+pulOut]
0x1800033d3  mov     rcx, [rsp+21D8h+var_2158]; void *
0x1800033db  mov     rdi, [rsp+21D8h+var_2168]
0x1800033e0  mov     rax, [rsp+21D8h+var_2198]
0x1800033e5  mov     [rsp+21D8h+var_2190], rax
0x1800033ea  mov     r12, [rsp+21D8h+var_2188]
0x1800033ef  mov     r13, [rsp+21D8h+var_2178]
0x1800033f4  test    rcx, rcx
0x1800033f7  jnz     short loc_18000340B
0x1800033f9  lea     rcx, [rsp+21D8h+var_2158]
0x180003401  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180003406  jmp     loc_180003359
0x18000340b  mov     r8, rdi; Size
0x18000340e  xor     edx, edx; Val
0x180003410  call    memset_0
0x180003415  mov     r10d, ebx
0x180003418  movsxd  r11, esi
0x18000341b  test    esi, esi
0x18000341d  jle     short loc_180003464
0x18000341f  mov     r9, rbx
0x180003422  movzx   ecx, [rsp+r9*2+21D8h+String1]; unsigned __int16
0x18000342b  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180003430  movzx   r8d, al
0x180003434  mov     eax, r10d
0x180003437  and     eax, 1
0x18000343a  shl     eax, 2
0x18000343d  mov     ecx, 4
0x180003442  sub     ecx, eax
0x180003444  shl     r8d, cl
0x180003447  mov     ecx, r10d
0x18000344a  shr     rcx, 1
0x18000344d  mov     rax, [rsp+21D8h+var_2158]
0x180003455  or      [rcx+rax], r8b
0x180003459  inc     r10d
0x18000345c  inc     r9
0x18000345f  cmp     r9, r11
0x180003462  jl      short loc_180003422
0x180003464  mov     [rsp+21D8h+cbData], r14d; cbData
0x180003469  mov     rax, [rsp+21D8h+var_2158]
0x180003471  mov     [rsp+21D8h+lpData], rax; lpData
0x180003476  mov     r9d, 3; dwType
0x18000347c  xor     r8d, r8d; Reserved
0x18000347f  mov     rdx, r13; lpValueName
0x180003482  mov     rcx, [r12]; hKey
0x180003486  call    cs:__imp_RegSetValueExW
0x18000348d  nop     dword ptr [rax+rax+00h]
0x180003492  mov     edi, eax
0x180003494  lea     rcx, [rsp+21D8h+var_2158]
0x18000349c  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800034a1  jmp     short loc_1800034EE
0x1800034a3  lea     rax, [rsp+21D8h+String1]
0x1800034ab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800034af  inc     rsi
0x1800034b2  cmp     [rax+rsi*2], bx
0x1800034b6  jnz     short loc_1800034AF
0x1800034b8  lea     eax, ds:2[rsi*2]
0x1800034bf  mov     [rsp+21D8h+cbData], eax; cbData
0x1800034c3  lea     rax, [rsp+21D8h+String1]
0x1800034cb  mov     [rsp+21D8h+lpData], rax; lpData
0x1800034d0  mov     r9d, 1; dwType
0x1800034d6  xor     r8d, r8d; Reserved
0x1800034d9  mov     rdx, r13; lpValueName
0x1800034dc  mov     rcx, [r12]; hKey
0x1800034e0  call    cs:__imp_RegSetValueExW
0x1800034e7  nop     dword ptr [rax+rax+00h]
0x1800034ec  mov     edi, eax
0x1800034ee  test    edi, edi
0x1800034f0  jz      short loc_1800034FB
0x1800034f2  mov     ecx, edi; unsigned int
0x1800034f4  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800034f9  jmp     short loc_18000351B
0x1800034fb  mov     r15, [rsp+21D8h+var_2190]
0x180003500  mov     rdx, [rsp+21D8h+var_2160]; unsigned __int16 *
0x180003505  mov     rcx, r15; this
0x180003508  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000350d  test    eax, eax
0x18000350f  cmovs   ebx, eax
0x180003512  mov     eax, ebx
0x180003514  jmp     short loc_18000351B
0x180003516  mov     eax, 80020009h
0x18000351b  mov     rcx, [rsp+21D8h+var_48]
0x180003523  xor     rcx, rsp; StackCookie
0x180003526  call    __security_check_cookie
0x18000352b  add     rsp, 21A0h
0x180003532  pop     r15
0x180003534  pop     r14
0x180003536  pop     r13
0x180003538  pop     r12
0x18000353a  pop     rdi
0x18000353b  pop     rsi
0x18000353c  pop     rbx
  ... truncated ...
```
