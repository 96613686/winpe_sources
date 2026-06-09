# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180085dc0`
- end: `0x180086376`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1462`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800879c4`

## callees

- `0x180080fb0`
- `0x180081b40`
- `0x1800857e8`
- `0x180085820`
- `0x1800858f4`
- `0x180085dc0`
- `0x18008637c`
- `0x180086560`
- `0x1800868b8`
- `0x180086fa0`
- `0x1800880e8`
- `0x1800bced0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180086066`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180086066`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180085f95`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180085fb1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180085f95`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180085fb1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008601a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800860b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800862cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180086323`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008601a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800860b3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800862cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180086323`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180085e5b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180085e5b`

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
  ATL::CRegParser *v34; // [rsp+30h] [rbp-21B8h] BYREF
  LPCWSTR lpValueName; // [rsp+38h] [rbp-21B0h]
  HKEY *v36; // [rsp+40h] [rbp-21A8h]
  ATL::CRegParser *v37; // [rsp+48h] [rbp-21A0h]
  const WCHAR *v38; // [rsp+50h] [rbp-2198h]
  size_t v39; // [rsp+60h] [rbp-2188h]
  HKEY *v40; // [rsp+68h] [rbp-2180h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-2178h]
  ULONG pulOut; // [rsp+78h] [rbp-2170h] BYREF
  BYTE Data[16]; // [rsp+80h] [rbp-2168h] BYREF
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v36 = a2;
  v6 = this;
  v34 = this;
  *(_QWORD *)Data = a2;
  v37 = this;
  v40 = a2;
  v38 = a3;
  v41 = a4;
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
      memset_0(&lpData, 0, 0x108u);
      lpData = 0;
      v25 = (int)v23 / 2;
      v39 = v25;
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
        v25 = v39;
        v34 = v37;
        v28 = v40;
        lpValueName = v38;
        v24 = v39;
        goto LABEL_47;
      }
      v28 = v36;
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
      v34 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v21 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v34);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v34);
      return (unsigned int)v22;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      memset_0(&lpData, 0, 0x108u);
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
        v34 = v37;
        lpValueName = v38;
        goto LABEL_18;
      }
      v14 = v36;
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
      v6 = v34;
LABEL_80:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v41);
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
0x180085dc0  push    rbx
0x180085dc2  push    rsi
0x180085dc3  push    rdi
0x180085dc4  push    r12
0x180085dc6  push    r13
0x180085dc8  push    r14
0x180085dca  push    r15
0x180085dcc  mov     eax, 21B0h
0x180085dd1  call    _alloca_probe
0x180085dd6  sub     rsp, rax
0x180085dd9  mov     rax, cs:__security_cookie
0x180085de0  xor     rax, rsp
0x180085de3  mov     [rsp+21E8h+var_48], rax
0x180085deb  mov     r14, r8
0x180085dee  mov     [rsp+21E8h+lpValueName], r8
0x180085df3  mov     r12, rdx
0x180085df6  mov     [rsp+21E8h+var_21A8], rdx
0x180085dfb  mov     r15, rcx
0x180085dfe  mov     [rsp+21E8h+var_21B8], rcx
0x180085e03  mov     qword ptr [rsp+21E8h+Data], rdx
0x180085e0b  mov     [rsp+21E8h+var_21A0], rcx
0x180085e10  mov     [rsp+21E8h+var_2180], rdx
0x180085e15  mov     [rsp+21E8h+var_2198], r8
0x180085e1a  mov     [rsp+21E8h+var_2178], r9
0x180085e1f  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180085e27  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180085e2c  xor     ebx, ebx
0x180085e2e  test    eax, eax
0x180085e30  js      loc_180086353
0x180085e36  mov     edi, ebx
0x180085e38  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180085e3f  cmp     edi, 4
0x180085e42  jnb     loc_18008634E
0x180085e48  movsxd  rsi, edi
0x180085e4b  add     rsi, rsi
0x180085e4e  mov     rdx, [r13+rsi*8+0]; lpString2
0x180085e53  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180085e5b  call    cs:__imp_lstrcmpiW
0x180085e61  test    eax, eax
0x180085e63  jz      short loc_180085E69
0x180085e65  inc     edi
0x180085e67  jmp     short loc_180085E3F
0x180085e69  movzx   edi, word ptr [r13+rsi*8+8]
0x180085e6f  mov     rcx, r15; this
0x180085e72  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180085e77  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180085e7f  mov     rcx, r15; this
0x180085e82  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180085e87  test    eax, eax
0x180085e89  js      loc_180086353
0x180085e8f  mov     r13d, 8
0x180085e95  cmp     di, r13w
0x180085e99  jz      loc_1800862E6
0x180085e9f  cmp     di, 11h
0x180085ea3  jz      loc_1800860CA
0x180085ea9  cmp     di, 13h
0x180085ead  jz      loc_18008604B
0x180085eb3  mov     eax, 4008h
0x180085eb8  cmp     di, ax
0x180085ebb  jnz     loc_180086338
0x180085ec1  lea     rcx, [rsp+21E8h+String1]
0x180085ec9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180085ecd  mov     rax, rsi
0x180085ed0  inc     rax
0x180085ed3  cmp     [rcx+rax*2], bx
0x180085ed7  jnz     short loc_180085ED0
0x180085ed9  lea     edi, [rax+2]
0x180085edc  xor     edx, edx; Val
0x180085ede  mov     r8d, 108h; Size
0x180085ee4  lea     rcx, [rsp+21E8h+var_2158]; void *
0x180085eec  call    memset_0
0x180085ef1  mov     [rsp+21E8h+var_2158], rbx
0x180085ef9  movsxd  rcx, edi
0x180085efc  mov     r15d, 2
0x180085f02  mov     edx, r15d
0x180085f05  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180085f0a  cmp     rax, 100h
0x180085f10  jbe     short loc_180085F2C
0x180085f12  mov     rdx, rax
0x180085f15  lea     rcx, [rsp+21E8h+var_2158]
0x180085f1d  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180085f22  mov     rdi, [rsp+21E8h+var_2158]
0x180085f2a  jmp     short loc_180085F3C
0x180085f2c  lea     rdi, [rsp+21E8h+var_2150]
0x180085f34  mov     [rsp+21E8h+var_2158], rdi
0x180085f3c  mov     r13, [rsp+21E8h+var_21A8]
0x180085f41  jmp     short loc_180085F71
0x180085f43  xor     ebx, ebx
0x180085f45  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180085f49  lea     r15d, [rbx+2]
0x180085f4d  mov     rdi, [rsp+21E8h+var_2158]
0x180085f55  mov     r13, qword ptr [rsp+21E8h+Data]
0x180085f5d  mov     rax, [rsp+21E8h+var_21A0]
0x180085f62  mov     [rsp+21E8h+var_21B8], rax
0x180085f67  mov     rax, [rsp+21E8h+var_2198]
0x180085f6c  mov     [rsp+21E8h+lpValueName], rax
0x180085f71  test    rdi, rdi
0x180085f74  jz      loc_18008602F
0x180085f7a  lea     r14, [rsp+21E8h+String1]
0x180085f82  cmp     [rsp+21E8h+String1], bx
0x180085f8a  jz      short loc_180085FCB
0x180085f8c  mov     r12d, 30h ; '0'
0x180085f92  mov     rcx, r14; lpsz
0x180085f95  call    cs:__imp_CharNextW
0x180085f9b  movzx   ecx, word ptr [r14]
0x180085f9f  cmp     cx, 5Ch ; '\'
0x180085fa3  jnz     short loc_180085FBC
0x180085fa5  cmp     [rax], r12w
0x180085fa9  jnz     short loc_180085FBC
0x180085fab  mov     [rdi], bx
0x180085fae  mov     rcx, rax; lpsz
0x180085fb1  call    cs:__imp_CharNextW
0x180085fb7  mov     r14, rax
0x180085fba  jmp     short loc_180085FC2
0x180085fbc  mov     [rdi], cx
0x180085fbf  add     r14, r15
0x180085fc2  add     rdi, r15
0x180085fc5  cmp     [r14], bx
0x180085fc9  jnz     short loc_180085F92
0x180085fcb  mov     dword ptr [rdi], 0
0x180085fd1  mov     r8, [rsp+21E8h+var_2158]
0x180085fd9  test    r8, r8
0x180085fdc  jz      short loc_180086024
0x180085fde  mov     r10d, ebx
0x180085fe1  mov     r9, r8
0x180085fe4  mov     rcx, rsi
0x180085fe7  inc     rcx
0x180085fea  cmp     [r9+rcx*2], bx
0x180085fef  jnz     short loc_180085FE7
0x180085ff1  inc     ecx
0x180085ff3  lea     r9, [r9+rcx*2]
0x180085ff7  lea     r10d, [r10+rcx*2]
0x180085ffb  cmp     ecx, 1
0x180085ffe  jnz     short loc_180085FE4
0x180086000  mov     [rsp+21E8h+cbData], r10d; cbData
0x180086005  mov     [rsp+21E8h+lpData], r8; lpData
0x18008600a  lea     r9d, [rcx+6]; dwType
0x18008600e  xor     r8d, r8d; Reserved
0x180086011  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180086016  mov     rcx, [r13+0]; hKey
0x18008601a  call    cs:__imp_RegSetValueExW
0x180086020  mov     edi, eax
0x180086022  jmp     short loc_180086034
0x180086024  mov     ecx, 80004005h; int
0x180086029  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008602f  mov     edi, 0Eh
0x180086034  lea     rcx, [rsp+21E8h+var_2158]
0x18008603c  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180086041  mov     r15, [rsp+21E8h+var_21B8]
0x180086046  jmp     loc_18008632B
0x18008604b  mov     [rsp+21E8h+pulOut], ebx
0x18008604f  mov     [rsp+21E8h+var_21B8], rbx
0x180086054  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180086059  xor     r8d, r8d; dwFlags
0x18008605c  xor     edx, edx; lcid
0x18008605e  lea     rcx, [rsp+21E8h+String1]; strIn
0x180086066  call    cs:__imp_VarUI4FromStr
0x18008606c  mov     edi, eax
0x18008606e  test    eax, eax
0x180086070  jns     short loc_180086083
0x180086072  lea     rcx, [rsp+21E8h+var_21B8]
0x180086077  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18008607c  mov     eax, edi
0x18008607e  jmp     loc_180086353
0x180086083  mov     eax, [rsp+21E8h+pulOut]
0x180086087  mov     dword ptr [rsp+21E8h+Data], eax
0x18008608e  mov     [rsp+21E8h+cbData], 4; cbData
0x180086096  lea     rax, [rsp+21E8h+Data]
0x18008609e  mov     [rsp+21E8h+lpData], rax; lpData
0x1800860a3  mov     r9d, 4; dwType
0x1800860a9  xor     r8d, r8d; Reserved
0x1800860ac  mov     rdx, r14; lpValueName
0x1800860af  mov     rcx, [r12]; hKey
0x1800860b3  call    cs:__imp_RegSetValueExW
0x1800860b9  mov     edi, eax
0x1800860bb  lea     rcx, [rsp+21E8h+var_21B8]
0x1800860c0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800860c5  jmp     loc_18008632B
0x1800860ca  lea     rax, [rsp+21E8h+String1]
0x1800860d2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800860d6  inc     rsi
0x1800860d9  cmp     [rax+rsi*2], bx
0x1800860dd  jnz     short loc_1800860D6
0x1800860df  mov     dword ptr [rsp+21E8h+Data], esi
0x1800860e6  test    sil, 1
0x1800860ea  jz      short loc_1800860F6
0x1800860ec  mov     eax, 80004005h
0x1800860f1  jmp     loc_180086353
0x1800860f6  mov     eax, esi
0x1800860f8  cdq
0x1800860f9  mov     r15d, 2
0x1800860ff  idiv    r15d
0x180086102  movsxd  r14, eax
0x180086105  xor     edx, edx; Val
0x180086107  mov     r8d, 108h; Size
0x18008610d  lea     rcx, [rsp+21E8h+var_2158]; void *
0x180086115  call    memset_0
0x18008611a  mov     [rsp+21E8h+var_2158], rbx
0x180086122  mov     rdi, r14
0x180086125  mov     [rsp+21E8h+var_2188], r14
0x18008612a  lea     edx, [r15-1]
0x18008612e  mov     rcx, r14
0x180086131  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180086136  cmp     rax, 100h
0x18008613c  jbe     short loc_180086158
0x18008613e  mov     rdx, rax
0x180086141  lea     rcx, [rsp+21E8h+var_2158]
0x180086149  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18008614e  mov     rcx, [rsp+21E8h+var_2158]
0x180086156  jmp     short loc_180086168
0x180086158  lea     rcx, [rsp+21E8h+var_2150]
0x180086160  mov     [rsp+21E8h+var_2158], rcx
0x180086168  mov     r15, [rsp+21E8h+var_21A8]
0x18008616d  jmp     short loc_1800861A5
0x18008616f  xor     ebx, ebx
0x180086171  lea     r13d, [rbx+8]
0x180086175  mov     esi, dword ptr [rsp+21E8h+Data]
0x18008617c  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180086184  mov     rdi, [rsp+21E8h+var_2188]
0x180086189  mov     rax, [rsp+21E8h+var_21A0]
0x18008618e  mov     [rsp+21E8h+var_21B8], rax
0x180086193  mov     r15, [rsp+21E8h+var_2180]
0x180086198  mov     rax, [rsp+21E8h+var_2198]
0x18008619d  mov     [rsp+21E8h+lpValueName], rax
0x1800861a2  mov     r14d, edi
0x1800861a5  test    rcx, rcx
0x1800861a8  jnz     short loc_1800861BC
0x1800861aa  lea     rcx, [rsp+21E8h+var_2158]
0x1800861b2  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800861b7  jmp     loc_1800860EC
0x1800861bc  mov     r8, rdi; Size
0x1800861bf  xor     edx, edx; Val
0x1800861c1  call    memset_0
0x1800861c6  mov     r10d, ebx
0x1800861c9  test    esi, esi
0x1800861cb  jle     loc_1800862A9
0x1800861d1  mov     r12d, 30h ; '0'
0x1800861d7  mov     eax, r10d
0x1800861da  movzx   edx, [rsp+rax*2+21E8h+String1]
0x1800861e2  cmp     edx, 61h ; 'a'
0x1800861e5  ja      short loc_180086254
0x1800861e7  jz      loc_180086274
0x1800861ed  cmp     edx, 38h ; '8'
0x1800861f0  ja      short loc_180086226
0x1800861f2  jz      short loc_18008621E
0x1800861f4  mov     ecx, edx
0x1800861f6  sub     ecx, r12d
0x1800861f9  jz      short loc_18008621E
0x1800861fb  sub     ecx, 1
0x1800861fe  jz      short loc_18008621E
0x180086200  sub     ecx, 1
0x180086203  jz      short loc_18008621E
0x180086205  sub     ecx, 1
0x180086208  jz      short loc_18008621E
0x18008620a  sub     ecx, 1
0x18008620d  jz      short loc_18008621E
0x18008620f  sub     ecx, 1
0x180086212  jz      short loc_18008621E
0x180086214  sub     ecx, 1
0x180086217  jz      short loc_18008621E
0x180086219  cmp     ecx, 1
0x18008621c  jnz     short loc_18008626F
0x18008621e  mov     r9d, edx
0x180086221  sub     r9d, r12d
0x180086224  jmp     short loc_180086278
0x180086226  mov     r9d, edx
0x180086229  mov     ecx, edx
0x18008622b  sub     ecx, 39h ; '9'
0x18008622e  jz      short loc_18008621E
0x180086230  sub     ecx, r13d
0x180086233  jz      short loc_18008624E
0x180086235  sub     ecx, 1
0x180086238  jz      short loc_18008624E
0x18008623a  sub     ecx, 1
0x18008623d  jz      short loc_18008624E
0x18008623f  sub     ecx, 1
0x180086242  jz      short loc_18008624E
0x180086244  sub     ecx, 1
0x180086247  jz      short loc_18008624E
0x180086249  cmp     ecx, 1
0x18008624c  jnz     short loc_18008626F
0x18008624e  add     r9d, 0FFFFFFC9h
0x180086252  jmp     short loc_180086278
0x180086254  mov     ecx, edx
0x180086256  sub     ecx, 62h ; 'b'
0x180086259  jz      short loc_180086274
0x18008625b  sub     ecx, 1
0x18008625e  jz      short loc_180086274
0x180086260  sub     ecx, 1
0x180086263  jz      short loc_180086274
0x180086265  sub     ecx, 1
0x180086268  jz      short loc_180086274
0x18008626a  cmp     ecx, 1
0x18008626d  jz      short loc_180086274
0x18008626f  mov     r9d, ebx
0x180086272  jmp     short loc_180086278
0x180086274  lea     r9d, [rdx-57h]
0x180086278  mov     r8d, r10d
0x18008627b  shr     r8, 1
0x18008627e  mov     rdx, [rsp+21E8h+var_2158]
  ... truncated ...
```
