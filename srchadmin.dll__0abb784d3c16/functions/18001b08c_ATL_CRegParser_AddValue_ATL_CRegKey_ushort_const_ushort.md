# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18001b08c`
- end: `0x18001b60c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001e340`

## callees

- `0x180005cc0`
- `0x18000687c`
- `0x18000cd9c`
- `0x18001a1e4`
- `0x18001a324`
- `0x18001a6d0`
- `0x18001b08c`
- `0x18001b644`
- `0x18001b8e0`
- `0x18001d3b0`
- `0x18001ef88`
- `0x180030350`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b2ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b361`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b55f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b5b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b2ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b361`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b55f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b5b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001b127`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001b127`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b249`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b265`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b249`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001b265`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001b31a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001b31a`

## pseudocode

```c
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
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
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
0x18001b08c  push    rbx
0x18001b08e  push    rsi
0x18001b08f  push    rdi
0x18001b090  push    r12
0x18001b092  push    r13
0x18001b094  push    r14
0x18001b096  push    r15
0x18001b098  mov     eax, 21B0h
0x18001b09d  call    _alloca_probe
0x18001b0a2  sub     rsp, rax
0x18001b0a5  mov     rax, cs:__security_cookie
0x18001b0ac  xor     rax, rsp
0x18001b0af  mov     [rsp+21E8h+var_48], rax
0x18001b0b7  mov     r14, r8
0x18001b0ba  mov     [rsp+21E8h+lpValueName], r8
0x18001b0bf  mov     r12, rdx
0x18001b0c2  mov     [rsp+21E8h+var_2198], rdx
0x18001b0c7  mov     r15, rcx
0x18001b0ca  mov     [rsp+21E8h+var_21B0], rcx
0x18001b0cf  mov     qword ptr [rsp+21E8h+Data], rdx
0x18001b0d4  mov     [rsp+21E8h+var_2190], rcx
0x18001b0d9  mov     [rsp+21E8h+var_2170], rdx
0x18001b0de  mov     [rsp+21E8h+var_2188], r8
0x18001b0e3  mov     [rsp+21E8h+var_2168], r9
0x18001b0eb  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18001b0f3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001b0f8  xor     ebx, ebx
0x18001b0fa  test    eax, eax
0x18001b0fc  js      loc_18001B5E9
0x18001b102  mov     edi, ebx
0x18001b104  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001b10b  cmp     edi, 4
0x18001b10e  jnb     loc_18001B5E4
0x18001b114  movsxd  rsi, edi
0x18001b117  add     rsi, rsi
0x18001b11a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001b11f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18001b127  call    cs:__imp_lstrcmpiW
0x18001b12d  test    eax, eax
0x18001b12f  jz      short loc_18001B135
0x18001b131  inc     edi
0x18001b133  jmp     short loc_18001B10B
0x18001b135  movzx   edi, word ptr [r13+rsi*8+8]
0x18001b13b  mov     rcx, r15; this
0x18001b13e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001b143  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18001b14b  mov     rcx, r15; this
0x18001b14e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001b153  test    eax, eax
0x18001b155  js      loc_18001B5E9
0x18001b15b  mov     r13d, 8
0x18001b161  cmp     di, r13w
0x18001b165  jz      loc_18001B579
0x18001b16b  cmp     di, 11h
0x18001b16f  jz      loc_18001B378
0x18001b175  cmp     di, 13h
0x18001b179  jz      loc_18001B2FF
0x18001b17f  mov     eax, 4008h
0x18001b184  cmp     di, ax
0x18001b187  jnz     loc_18001B5CB
0x18001b18d  lea     rcx, [rsp+21E8h+String1]
0x18001b195  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b199  mov     rax, rsi
0x18001b19c  inc     rax
0x18001b19f  cmp     [rcx+rax*2], bx
0x18001b1a3  jnz     short loc_18001B19C
0x18001b1a5  add     eax, 2
0x18001b1a8  mov     [rsp+21E8h+var_2158], rbx
0x18001b1b0  movsxd  rcx, eax
0x18001b1b3  mov     r15d, 2
0x18001b1b9  mov     edx, r15d
0x18001b1bc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001b1c1  cmp     rax, 100h
0x18001b1c7  jbe     short loc_18001B1E3
0x18001b1c9  mov     rdx, rax
0x18001b1cc  lea     rcx, [rsp+21E8h+var_2158]
0x18001b1d4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001b1d9  mov     rdi, [rsp+21E8h+var_2158]
0x18001b1e1  jmp     short loc_18001B1F3
0x18001b1e3  lea     rdi, [rsp+21E8h+var_2150]
0x18001b1eb  mov     [rsp+21E8h+var_2158], rdi
0x18001b1f3  mov     r13, [rsp+21E8h+var_2198]
0x18001b1f8  jmp     short loc_18001B225
0x18001b1fa  xor     ebx, ebx
0x18001b1fc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b200  lea     r15d, [rbx+2]
0x18001b204  mov     rdi, [rsp+21E8h+var_2158]
0x18001b20c  mov     r13, qword ptr [rsp+21E8h+Data]
0x18001b211  mov     rax, [rsp+21E8h+var_2190]
0x18001b216  mov     [rsp+21E8h+var_21B0], rax
0x18001b21b  mov     rax, [rsp+21E8h+var_2188]
0x18001b220  mov     [rsp+21E8h+lpValueName], rax
0x18001b225  test    rdi, rdi
0x18001b228  jz      loc_18001B2E3
0x18001b22e  lea     r14, [rsp+21E8h+String1]
0x18001b236  cmp     [rsp+21E8h+String1], bx
0x18001b23e  jz      short loc_18001B27F
0x18001b240  mov     r12d, 30h ; '0'
0x18001b246  mov     rcx, r14; lpsz
0x18001b249  call    cs:__imp_CharNextW
0x18001b24f  movzx   ecx, word ptr [r14]
0x18001b253  cmp     cx, 5Ch ; '\'
0x18001b257  jnz     short loc_18001B270
0x18001b259  cmp     [rax], r12w
0x18001b25d  jnz     short loc_18001B270
0x18001b25f  mov     [rdi], bx
0x18001b262  mov     rcx, rax; lpsz
0x18001b265  call    cs:__imp_CharNextW
0x18001b26b  mov     r14, rax
0x18001b26e  jmp     short loc_18001B276
0x18001b270  mov     [rdi], cx
0x18001b273  add     r14, r15
0x18001b276  add     rdi, r15
0x18001b279  cmp     [r14], bx
0x18001b27d  jnz     short loc_18001B246
0x18001b27f  mov     dword ptr [rdi], 0
0x18001b285  mov     r8, [rsp+21E8h+var_2158]
0x18001b28d  test    r8, r8
0x18001b290  jz      short loc_18001B2D8
0x18001b292  mov     r10d, ebx
0x18001b295  mov     r9, r8
0x18001b298  mov     rcx, rsi
0x18001b29b  inc     rcx
0x18001b29e  cmp     [r9+rcx*2], bx
0x18001b2a3  jnz     short loc_18001B29B
0x18001b2a5  inc     ecx
0x18001b2a7  lea     r9, [r9+rcx*2]
0x18001b2ab  lea     r10d, [r10+rcx*2]
0x18001b2af  cmp     ecx, 1
0x18001b2b2  jnz     short loc_18001B298
0x18001b2b4  mov     [rsp+21E8h+cbData], r10d; cbData
0x18001b2b9  mov     [rsp+21E8h+lpData], r8; lpData
0x18001b2be  lea     r9d, [rcx+6]; dwType
0x18001b2c2  xor     r8d, r8d; Reserved
0x18001b2c5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18001b2ca  mov     rcx, [r13+0]; hKey
0x18001b2ce  call    cs:__imp_RegSetValueExW
0x18001b2d4  mov     edi, eax
0x18001b2d6  jmp     short loc_18001B2E8
0x18001b2d8  mov     ecx, 80004005h; int
0x18001b2dd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001b2e3  mov     edi, 0Eh
0x18001b2e8  lea     rcx, [rsp+21E8h+var_2158]
0x18001b2f0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001b2f5  mov     r15, [rsp+21E8h+var_21B0]
0x18001b2fa  jmp     loc_18001B5BE
0x18001b2ff  mov     [rsp+21E8h+pulOut], ebx
0x18001b303  mov     [rsp+21E8h+var_21B0], rbx
0x18001b308  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18001b30d  xor     r8d, r8d; dwFlags
0x18001b310  xor     edx, edx; lcid
0x18001b312  lea     rcx, [rsp+21E8h+String1]; strIn
0x18001b31a  call    cs:__imp_VarUI4FromStr
0x18001b320  mov     edi, eax
0x18001b322  test    eax, eax
0x18001b324  jns     short loc_18001B337
0x18001b326  lea     rcx, [rsp+21E8h+var_21B0]
0x18001b32b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001b330  mov     eax, edi
0x18001b332  jmp     loc_18001B5E9
0x18001b337  mov     eax, [rsp+21E8h+pulOut]
0x18001b33b  mov     dword ptr [rsp+21E8h+Data], eax
0x18001b33f  mov     [rsp+21E8h+cbData], 4; cbData
0x18001b347  lea     rax, [rsp+21E8h+Data]
0x18001b34c  mov     [rsp+21E8h+lpData], rax; lpData
0x18001b351  mov     r9d, 4; dwType
0x18001b357  xor     r8d, r8d; Reserved
0x18001b35a  mov     rdx, r14; lpValueName
0x18001b35d  mov     rcx, [r12]; hKey
0x18001b361  call    cs:__imp_RegSetValueExW
0x18001b367  mov     edi, eax
0x18001b369  lea     rcx, [rsp+21E8h+var_21B0]
0x18001b36e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001b373  jmp     loc_18001B5BE
0x18001b378  lea     rax, [rsp+21E8h+String1]
0x18001b380  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b384  inc     rsi
0x18001b387  cmp     [rax+rsi*2], bx
0x18001b38b  jnz     short loc_18001B384
0x18001b38d  mov     dword ptr [rsp+21E8h+Data], esi
0x18001b391  test    sil, 1
0x18001b395  jz      short loc_18001B3A1
0x18001b397  mov     eax, 80004005h
0x18001b39c  jmp     loc_18001B5E9
0x18001b3a1  mov     eax, esi
0x18001b3a3  cdq
0x18001b3a4  mov     r15d, 2
0x18001b3aa  idiv    r15d
0x18001b3ad  movsxd  r14, eax
0x18001b3b0  mov     [rsp+21E8h+var_2158], rbx
0x18001b3b8  mov     rdi, r14
0x18001b3bb  mov     [rsp+21E8h+var_2178], r14
0x18001b3c0  lea     edx, [r15-1]
0x18001b3c4  mov     rcx, r14
0x18001b3c7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001b3cc  cmp     rax, 100h
0x18001b3d2  jbe     short loc_18001B3EE
0x18001b3d4  mov     rdx, rax
0x18001b3d7  lea     rcx, [rsp+21E8h+var_2158]
0x18001b3df  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001b3e4  mov     rcx, [rsp+21E8h+var_2158]
0x18001b3ec  jmp     short loc_18001B3FE
0x18001b3ee  lea     rcx, [rsp+21E8h+var_2150]
0x18001b3f6  mov     [rsp+21E8h+var_2158], rcx
0x18001b3fe  mov     r15, [rsp+21E8h+var_2198]
0x18001b403  jmp     short loc_18001B438
0x18001b405  xor     ebx, ebx
0x18001b407  lea     r13d, [rbx+8]
0x18001b40b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18001b40f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18001b417  mov     rdi, [rsp+21E8h+var_2178]
0x18001b41c  mov     rax, [rsp+21E8h+var_2190]
0x18001b421  mov     [rsp+21E8h+var_21B0], rax
0x18001b426  mov     r15, [rsp+21E8h+var_2170]
0x18001b42b  mov     rax, [rsp+21E8h+var_2188]
0x18001b430  mov     [rsp+21E8h+lpValueName], rax
0x18001b435  mov     r14d, edi
0x18001b438  test    rcx, rcx
0x18001b43b  jnz     short loc_18001B44F
0x18001b43d  lea     rcx, [rsp+21E8h+var_2158]
0x18001b445  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001b44a  jmp     loc_18001B397
0x18001b44f  mov     r8, rdi; Size
0x18001b452  xor     edx, edx; Val
0x18001b454  call    memset_0
0x18001b459  mov     r10d, ebx
0x18001b45c  test    esi, esi
0x18001b45e  jle     loc_18001B53C
0x18001b464  mov     r12d, 30h ; '0'
0x18001b46a  mov     eax, r10d
0x18001b46d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x18001b475  cmp     edx, 61h ; 'a'
0x18001b478  ja      short loc_18001B4E7
0x18001b47a  jz      loc_18001B507
0x18001b480  cmp     edx, 38h ; '8'
0x18001b483  ja      short loc_18001B4B9
0x18001b485  jz      short loc_18001B4B1
0x18001b487  mov     ecx, edx
0x18001b489  sub     ecx, r12d
0x18001b48c  jz      short loc_18001B4B1
0x18001b48e  sub     ecx, 1
0x18001b491  jz      short loc_18001B4B1
0x18001b493  sub     ecx, 1
0x18001b496  jz      short loc_18001B4B1
0x18001b498  sub     ecx, 1
0x18001b49b  jz      short loc_18001B4B1
0x18001b49d  sub     ecx, 1
0x18001b4a0  jz      short loc_18001B4B1
0x18001b4a2  sub     ecx, 1
0x18001b4a5  jz      short loc_18001B4B1
0x18001b4a7  sub     ecx, 1
0x18001b4aa  jz      short loc_18001B4B1
0x18001b4ac  cmp     ecx, 1
0x18001b4af  jnz     short loc_18001B502
0x18001b4b1  mov     r9d, edx
0x18001b4b4  sub     r9d, r12d
0x18001b4b7  jmp     short loc_18001B50B
0x18001b4b9  mov     r9d, edx
0x18001b4bc  mov     ecx, edx
0x18001b4be  sub     ecx, 39h ; '9'
0x18001b4c1  jz      short loc_18001B4B1
0x18001b4c3  sub     ecx, r13d
0x18001b4c6  jz      short loc_18001B4E1
0x18001b4c8  sub     ecx, 1
0x18001b4cb  jz      short loc_18001B4E1
0x18001b4cd  sub     ecx, 1
0x18001b4d0  jz      short loc_18001B4E1
0x18001b4d2  sub     ecx, 1
0x18001b4d5  jz      short loc_18001B4E1
0x18001b4d7  sub     ecx, 1
0x18001b4da  jz      short loc_18001B4E1
0x18001b4dc  cmp     ecx, 1
0x18001b4df  jnz     short loc_18001B502
0x18001b4e1  add     r9d, 0FFFFFFC9h
0x18001b4e5  jmp     short loc_18001B50B
0x18001b4e7  mov     ecx, edx
0x18001b4e9  sub     ecx, 62h ; 'b'
0x18001b4ec  jz      short loc_18001B507
0x18001b4ee  sub     ecx, 1
0x18001b4f1  jz      short loc_18001B507
0x18001b4f3  sub     ecx, 1
0x18001b4f6  jz      short loc_18001B507
0x18001b4f8  sub     ecx, 1
0x18001b4fb  jz      short loc_18001B507
0x18001b4fd  cmp     ecx, 1
0x18001b500  jz      short loc_18001B507
0x18001b502  mov     r9d, ebx
0x18001b505  jmp     short loc_18001B50B
0x18001b507  lea     r9d, [rdx-57h]
0x18001b50b  mov     r8d, r10d
0x18001b50e  shr     r8, 1
0x18001b511  mov     rdx, [rsp+21E8h+var_2158]
0x18001b519  mov     eax, r10d
0x18001b51c  and     eax, 1
0x18001b51f  shl     eax, 2
0x18001b522  mov     ecx, 4
0x18001b527  sub     ecx, eax
0x18001b529  shl     r9b, cl
0x18001b52c  or      [r8+rdx], r9b
0x18001b530  inc     r10d
  ... truncated ...
```
