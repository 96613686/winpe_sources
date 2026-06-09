# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180003b8c`
- end: `0x18000410c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800078b0`

## callees

- `0x180002d14`
- `0x180002d78`
- `0x18000325c`
- `0x180003b8c`
- `0x180004114`
- `0x180004394`
- `0x180004488`
- `0x180006b10`
- `0x18000851c`
- `0x180032a02`
- `0x180032a30`
- `0x180032af0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003dce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003e61`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000405f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003dce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003e61`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000405f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800040b6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003d49`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003d65`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003d49`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003d65`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003c27`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003c27`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003e1a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003e1a`

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
0x180003b8c  push    rbx
0x180003b8e  push    rsi
0x180003b8f  push    rdi
0x180003b90  push    r12
0x180003b92  push    r13
0x180003b94  push    r14
0x180003b96  push    r15
0x180003b98  mov     eax, 21B0h
0x180003b9d  call    _alloca_probe
0x180003ba2  sub     rsp, rax
0x180003ba5  mov     rax, cs:__security_cookie
0x180003bac  xor     rax, rsp
0x180003baf  mov     [rsp+21E8h+var_48], rax
0x180003bb7  mov     r14, r8
0x180003bba  mov     [rsp+21E8h+lpValueName], r8
0x180003bbf  mov     r12, rdx
0x180003bc2  mov     [rsp+21E8h+var_2198], rdx
0x180003bc7  mov     r15, rcx
0x180003bca  mov     [rsp+21E8h+var_21B0], rcx
0x180003bcf  mov     qword ptr [rsp+21E8h+Data], rdx
0x180003bd4  mov     [rsp+21E8h+var_2190], rcx
0x180003bd9  mov     [rsp+21E8h+var_2170], rdx
0x180003bde  mov     [rsp+21E8h+var_2188], r8
0x180003be3  mov     [rsp+21E8h+var_2168], r9
0x180003beb  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180003bf3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003bf8  xor     ebx, ebx
0x180003bfa  test    eax, eax
0x180003bfc  js      loc_1800040E9
0x180003c02  mov     edi, ebx
0x180003c04  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003c0b  cmp     edi, 4
0x180003c0e  jnb     loc_1800040E4
0x180003c14  movsxd  rsi, edi
0x180003c17  add     rsi, rsi
0x180003c1a  mov     rdx, [r13+rsi*8+0]; lpString2
0x180003c1f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180003c27  call    cs:__imp_lstrcmpiW
0x180003c2d  test    eax, eax
0x180003c2f  jz      short loc_180003C35
0x180003c31  inc     edi
0x180003c33  jmp     short loc_180003C0B
0x180003c35  movzx   edi, word ptr [r13+rsi*8+8]
0x180003c3b  mov     rcx, r15; this
0x180003c3e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180003c43  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180003c4b  mov     rcx, r15; this
0x180003c4e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003c53  test    eax, eax
0x180003c55  js      loc_1800040E9
0x180003c5b  mov     r13d, 8
0x180003c61  cmp     di, r13w
0x180003c65  jz      loc_180004079
0x180003c6b  cmp     di, 11h
0x180003c6f  jz      loc_180003E78
0x180003c75  cmp     di, 13h
0x180003c79  jz      loc_180003DFF
0x180003c7f  mov     eax, 4008h
0x180003c84  cmp     di, ax
0x180003c87  jnz     loc_1800040CB
0x180003c8d  lea     rcx, [rsp+21E8h+String1]
0x180003c95  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003c99  mov     rax, rsi
0x180003c9c  inc     rax
0x180003c9f  cmp     [rcx+rax*2], bx
0x180003ca3  jnz     short loc_180003C9C
0x180003ca5  add     eax, 2
0x180003ca8  mov     [rsp+21E8h+var_2158], rbx
0x180003cb0  movsxd  rcx, eax
0x180003cb3  mov     r15d, 2
0x180003cb9  mov     edx, r15d
0x180003cbc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180003cc1  cmp     rax, 100h
0x180003cc7  jbe     short loc_180003CE3
0x180003cc9  mov     rdx, rax
0x180003ccc  lea     rcx, [rsp+21E8h+var_2158]
0x180003cd4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003cd9  mov     rdi, [rsp+21E8h+var_2158]
0x180003ce1  jmp     short loc_180003CF3
0x180003ce3  lea     rdi, [rsp+21E8h+var_2150]
0x180003ceb  mov     [rsp+21E8h+var_2158], rdi
0x180003cf3  mov     r13, [rsp+21E8h+var_2198]
0x180003cf8  jmp     short loc_180003D25
0x180003cfa  xor     ebx, ebx
0x180003cfc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003d00  lea     r15d, [rbx+2]
0x180003d04  mov     rdi, [rsp+21E8h+var_2158]
0x180003d0c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180003d11  mov     rax, [rsp+21E8h+var_2190]
0x180003d16  mov     [rsp+21E8h+var_21B0], rax
0x180003d1b  mov     rax, [rsp+21E8h+var_2188]
0x180003d20  mov     [rsp+21E8h+lpValueName], rax
0x180003d25  test    rdi, rdi
0x180003d28  jz      loc_180003DE3
0x180003d2e  lea     r14, [rsp+21E8h+String1]
0x180003d36  cmp     [rsp+21E8h+String1], bx
0x180003d3e  jz      short loc_180003D7F
0x180003d40  mov     r12d, 30h ; '0'
0x180003d46  mov     rcx, r14; lpsz
0x180003d49  call    cs:__imp_CharNextW
0x180003d4f  movzx   ecx, word ptr [r14]
0x180003d53  cmp     cx, 5Ch ; '\'
0x180003d57  jnz     short loc_180003D70
0x180003d59  cmp     [rax], r12w
0x180003d5d  jnz     short loc_180003D70
0x180003d5f  mov     [rdi], bx
0x180003d62  mov     rcx, rax; lpsz
0x180003d65  call    cs:__imp_CharNextW
0x180003d6b  mov     r14, rax
0x180003d6e  jmp     short loc_180003D76
0x180003d70  mov     [rdi], cx
0x180003d73  add     r14, r15
0x180003d76  add     rdi, r15
0x180003d79  cmp     [r14], bx
0x180003d7d  jnz     short loc_180003D46
0x180003d7f  mov     dword ptr [rdi], 0
0x180003d85  mov     r8, [rsp+21E8h+var_2158]
0x180003d8d  test    r8, r8
0x180003d90  jz      short loc_180003DD8
0x180003d92  mov     r10d, ebx
0x180003d95  mov     r9, r8
0x180003d98  mov     rcx, rsi
0x180003d9b  inc     rcx
0x180003d9e  cmp     [r9+rcx*2], bx
0x180003da3  jnz     short loc_180003D9B
0x180003da5  inc     ecx
0x180003da7  lea     r9, [r9+rcx*2]
0x180003dab  lea     r10d, [r10+rcx*2]
0x180003daf  cmp     ecx, 1
0x180003db2  jnz     short loc_180003D98
0x180003db4  mov     [rsp+21E8h+cbData], r10d; cbData
0x180003db9  mov     [rsp+21E8h+lpData], r8; lpData
0x180003dbe  lea     r9d, [rcx+6]; dwType
0x180003dc2  xor     r8d, r8d; Reserved
0x180003dc5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180003dca  mov     rcx, [r13+0]; hKey
0x180003dce  call    cs:__imp_RegSetValueExW
0x180003dd4  mov     edi, eax
0x180003dd6  jmp     short loc_180003DE8
0x180003dd8  mov     ecx, 80004005h; int
0x180003ddd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003de3  mov     edi, 0Eh
0x180003de8  lea     rcx, [rsp+21E8h+var_2158]
0x180003df0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180003df5  mov     r15, [rsp+21E8h+var_21B0]
0x180003dfa  jmp     loc_1800040BE
0x180003dff  mov     [rsp+21E8h+pulOut], ebx
0x180003e03  mov     [rsp+21E8h+var_21B0], rbx
0x180003e08  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180003e0d  xor     r8d, r8d; dwFlags
0x180003e10  xor     edx, edx; lcid
0x180003e12  lea     rcx, [rsp+21E8h+String1]; strIn
0x180003e1a  call    cs:__imp_VarUI4FromStr
0x180003e20  mov     edi, eax
0x180003e22  test    eax, eax
0x180003e24  jns     short loc_180003E37
0x180003e26  lea     rcx, [rsp+21E8h+var_21B0]
0x180003e2b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003e30  mov     eax, edi
0x180003e32  jmp     loc_1800040E9
0x180003e37  mov     eax, [rsp+21E8h+pulOut]
0x180003e3b  mov     dword ptr [rsp+21E8h+Data], eax
0x180003e3f  mov     [rsp+21E8h+cbData], 4; cbData
0x180003e47  lea     rax, [rsp+21E8h+Data]
0x180003e4c  mov     [rsp+21E8h+lpData], rax; lpData
0x180003e51  mov     r9d, 4; dwType
0x180003e57  xor     r8d, r8d; Reserved
0x180003e5a  mov     rdx, r14; lpValueName
0x180003e5d  mov     rcx, [r12]; hKey
0x180003e61  call    cs:__imp_RegSetValueExW
0x180003e67  mov     edi, eax
0x180003e69  lea     rcx, [rsp+21E8h+var_21B0]
0x180003e6e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003e73  jmp     loc_1800040BE
0x180003e78  lea     rax, [rsp+21E8h+String1]
0x180003e80  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003e84  inc     rsi
0x180003e87  cmp     [rax+rsi*2], bx
0x180003e8b  jnz     short loc_180003E84
0x180003e8d  mov     dword ptr [rsp+21E8h+Data], esi
0x180003e91  test    sil, 1
0x180003e95  jz      short loc_180003EA1
0x180003e97  mov     eax, 80004005h
0x180003e9c  jmp     loc_1800040E9
0x180003ea1  mov     eax, esi
0x180003ea3  cdq
0x180003ea4  mov     r15d, 2
0x180003eaa  idiv    r15d
0x180003ead  movsxd  r14, eax
0x180003eb0  mov     [rsp+21E8h+var_2158], rbx
0x180003eb8  mov     rdi, r14
0x180003ebb  mov     [rsp+21E8h+var_2178], r14
0x180003ec0  lea     edx, [r15-1]
0x180003ec4  mov     rcx, r14
0x180003ec7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180003ecc  cmp     rax, 100h
0x180003ed2  jbe     short loc_180003EEE
0x180003ed4  mov     rdx, rax
0x180003ed7  lea     rcx, [rsp+21E8h+var_2158]
0x180003edf  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003ee4  mov     rcx, [rsp+21E8h+var_2158]
0x180003eec  jmp     short loc_180003EFE
0x180003eee  lea     rcx, [rsp+21E8h+var_2150]
0x180003ef6  mov     [rsp+21E8h+var_2158], rcx
0x180003efe  mov     r15, [rsp+21E8h+var_2198]
0x180003f03  jmp     short loc_180003F38
0x180003f05  xor     ebx, ebx
0x180003f07  lea     r13d, [rbx+8]
0x180003f0b  mov     esi, dword ptr [rsp+21E8h+Data]
0x180003f0f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180003f17  mov     rdi, [rsp+21E8h+var_2178]
0x180003f1c  mov     rax, [rsp+21E8h+var_2190]
0x180003f21  mov     [rsp+21E8h+var_21B0], rax
0x180003f26  mov     r15, [rsp+21E8h+var_2170]
0x180003f2b  mov     rax, [rsp+21E8h+var_2188]
0x180003f30  mov     [rsp+21E8h+lpValueName], rax
0x180003f35  mov     r14d, edi
0x180003f38  test    rcx, rcx
0x180003f3b  jnz     short loc_180003F4F
0x180003f3d  lea     rcx, [rsp+21E8h+var_2158]
0x180003f45  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180003f4a  jmp     loc_180003E97
0x180003f4f  mov     r8, rdi; Size
0x180003f52  xor     edx, edx; Val
0x180003f54  call    memset_0
0x180003f59  mov     r10d, ebx
0x180003f5c  test    esi, esi
0x180003f5e  jle     loc_18000403C
0x180003f64  mov     r12d, 30h ; '0'
0x180003f6a  mov     eax, r10d
0x180003f6d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180003f75  cmp     edx, 61h ; 'a'
0x180003f78  ja      short loc_180003FE7
0x180003f7a  jz      loc_180004007
0x180003f80  cmp     edx, 38h ; '8'
0x180003f83  ja      short loc_180003FB9
0x180003f85  jz      short loc_180003FB1
0x180003f87  mov     ecx, edx
0x180003f89  sub     ecx, r12d
0x180003f8c  jz      short loc_180003FB1
0x180003f8e  sub     ecx, 1
0x180003f91  jz      short loc_180003FB1
0x180003f93  sub     ecx, 1
0x180003f96  jz      short loc_180003FB1
0x180003f98  sub     ecx, 1
0x180003f9b  jz      short loc_180003FB1
0x180003f9d  sub     ecx, 1
0x180003fa0  jz      short loc_180003FB1
0x180003fa2  sub     ecx, 1
0x180003fa5  jz      short loc_180003FB1
0x180003fa7  sub     ecx, 1
0x180003faa  jz      short loc_180003FB1
0x180003fac  cmp     ecx, 1
0x180003faf  jnz     short loc_180004002
0x180003fb1  mov     r9d, edx
0x180003fb4  sub     r9d, r12d
0x180003fb7  jmp     short loc_18000400B
0x180003fb9  mov     r9d, edx
0x180003fbc  mov     ecx, edx
0x180003fbe  sub     ecx, 39h ; '9'
0x180003fc1  jz      short loc_180003FB1
0x180003fc3  sub     ecx, r13d
0x180003fc6  jz      short loc_180003FE1
0x180003fc8  sub     ecx, 1
0x180003fcb  jz      short loc_180003FE1
0x180003fcd  sub     ecx, 1
0x180003fd0  jz      short loc_180003FE1
0x180003fd2  sub     ecx, 1
0x180003fd5  jz      short loc_180003FE1
0x180003fd7  sub     ecx, 1
0x180003fda  jz      short loc_180003FE1
0x180003fdc  cmp     ecx, 1
0x180003fdf  jnz     short loc_180004002
0x180003fe1  add     r9d, 0FFFFFFC9h
0x180003fe5  jmp     short loc_18000400B
0x180003fe7  mov     ecx, edx
0x180003fe9  sub     ecx, 62h ; 'b'
0x180003fec  jz      short loc_180004007
0x180003fee  sub     ecx, 1
0x180003ff1  jz      short loc_180004007
0x180003ff3  sub     ecx, 1
0x180003ff6  jz      short loc_180004007
0x180003ff8  sub     ecx, 1
0x180003ffb  jz      short loc_180004007
0x180003ffd  cmp     ecx, 1
0x180004000  jz      short loc_180004007
0x180004002  mov     r9d, ebx
0x180004005  jmp     short loc_18000400B
0x180004007  lea     r9d, [rdx-57h]
0x18000400b  mov     r8d, r10d
0x18000400e  shr     r8, 1
0x180004011  mov     rdx, [rsp+21E8h+var_2158]
0x180004019  mov     eax, r10d
0x18000401c  and     eax, 1
0x18000401f  shl     eax, 2
0x180004022  mov     ecx, 4
0x180004027  sub     ecx, eax
0x180004029  shl     r9b, cl
0x18000402c  or      [r8+rdx], r9b
0x180004030  inc     r10d
  ... truncated ...
```
