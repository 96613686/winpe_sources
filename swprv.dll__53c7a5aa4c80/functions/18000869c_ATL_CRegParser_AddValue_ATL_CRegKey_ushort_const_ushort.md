# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000869c`
- end: `0x180008c1c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000bf80`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180007e18`
- `0x180007f50`
- `0x180008094`
- `0x18000869c`
- `0x180008c24`
- `0x180008efc`
- `0x180009588`
- `0x18000a8f0`
- `0x18000ca34`
- `0x180041990`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008859`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008875`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008859`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008875`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800088de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008971`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008b6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008bc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800088de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008971`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008b6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008bc6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008737`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008737`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000892a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000892a`

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
0x18000869c  push    rbx
0x18000869e  push    rsi
0x18000869f  push    rdi
0x1800086a0  push    r12
0x1800086a2  push    r13
0x1800086a4  push    r14
0x1800086a6  push    r15
0x1800086a8  mov     eax, 21B0h
0x1800086ad  call    _alloca_probe
0x1800086b2  sub     rsp, rax
0x1800086b5  mov     rax, cs:__security_cookie
0x1800086bc  xor     rax, rsp
0x1800086bf  mov     [rsp+21E8h+var_48], rax
0x1800086c7  mov     r14, r8
0x1800086ca  mov     [rsp+21E8h+lpValueName], r8
0x1800086cf  mov     r12, rdx
0x1800086d2  mov     [rsp+21E8h+var_2198], rdx
0x1800086d7  mov     r15, rcx
0x1800086da  mov     [rsp+21E8h+var_21B0], rcx
0x1800086df  mov     qword ptr [rsp+21E8h+Data], rdx
0x1800086e4  mov     [rsp+21E8h+var_2190], rcx
0x1800086e9  mov     [rsp+21E8h+var_2170], rdx
0x1800086ee  mov     [rsp+21E8h+var_2188], r8
0x1800086f3  mov     [rsp+21E8h+var_2168], r9
0x1800086fb  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180008703  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008708  xor     ebx, ebx
0x18000870a  test    eax, eax
0x18000870c  js      loc_180008BF9
0x180008712  mov     edi, ebx
0x180008714  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000871b  cmp     edi, 4
0x18000871e  jnb     loc_180008BF4
0x180008724  movsxd  rsi, edi
0x180008727  add     rsi, rsi
0x18000872a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000872f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180008737  call    cs:__imp_lstrcmpiW
0x18000873d  test    eax, eax
0x18000873f  jz      short loc_180008745
0x180008741  inc     edi
0x180008743  jmp     short loc_18000871B
0x180008745  movzx   edi, word ptr [r13+rsi*8+8]
0x18000874b  mov     rcx, r15; this
0x18000874e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180008753  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18000875b  mov     rcx, r15; this
0x18000875e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008763  test    eax, eax
0x180008765  js      loc_180008BF9
0x18000876b  mov     r13d, 8
0x180008771  cmp     di, r13w
0x180008775  jz      loc_180008B89
0x18000877b  cmp     di, 11h
0x18000877f  jz      loc_180008988
0x180008785  cmp     di, 13h
0x180008789  jz      loc_18000890F
0x18000878f  mov     eax, 4008h
0x180008794  cmp     di, ax
0x180008797  jnz     loc_180008BDB
0x18000879d  lea     rcx, [rsp+21E8h+String1]
0x1800087a5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800087a9  mov     rax, rsi
0x1800087ac  inc     rax
0x1800087af  cmp     [rcx+rax*2], bx
0x1800087b3  jnz     short loc_1800087AC
0x1800087b5  add     eax, 2
0x1800087b8  mov     [rsp+21E8h+var_2158], rbx
0x1800087c0  movsxd  rcx, eax
0x1800087c3  mov     r15d, 2
0x1800087c9  mov     edx, r15d
0x1800087cc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800087d1  cmp     rax, 100h
0x1800087d7  jbe     short loc_1800087F3
0x1800087d9  mov     rdx, rax
0x1800087dc  lea     rcx, [rsp+21E8h+var_2158]
0x1800087e4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800087e9  mov     rdi, [rsp+21E8h+var_2158]
0x1800087f1  jmp     short loc_180008803
0x1800087f3  lea     rdi, [rsp+21E8h+var_2150]
0x1800087fb  mov     [rsp+21E8h+var_2158], rdi
0x180008803  mov     r13, [rsp+21E8h+var_2198]
0x180008808  jmp     short loc_180008835
0x18000880a  xor     ebx, ebx
0x18000880c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008810  lea     r15d, [rbx+2]
0x180008814  mov     rdi, [rsp+21E8h+var_2158]
0x18000881c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180008821  mov     rax, [rsp+21E8h+var_2190]
0x180008826  mov     [rsp+21E8h+var_21B0], rax
0x18000882b  mov     rax, [rsp+21E8h+var_2188]
0x180008830  mov     [rsp+21E8h+lpValueName], rax
0x180008835  test    rdi, rdi
0x180008838  jz      loc_1800088F3
0x18000883e  lea     r14, [rsp+21E8h+String1]
0x180008846  cmp     [rsp+21E8h+String1], bx
0x18000884e  jz      short loc_18000888F
0x180008850  mov     r12d, 30h ; '0'
0x180008856  mov     rcx, r14; lpsz
0x180008859  call    cs:__imp_CharNextW
0x18000885f  movzx   ecx, word ptr [r14]
0x180008863  cmp     cx, 5Ch ; '\'
0x180008867  jnz     short loc_180008880
0x180008869  cmp     [rax], r12w
0x18000886d  jnz     short loc_180008880
0x18000886f  mov     [rdi], bx
0x180008872  mov     rcx, rax; lpsz
0x180008875  call    cs:__imp_CharNextW
0x18000887b  mov     r14, rax
0x18000887e  jmp     short loc_180008886
0x180008880  mov     [rdi], cx
0x180008883  add     r14, r15
0x180008886  add     rdi, r15
0x180008889  cmp     [r14], bx
0x18000888d  jnz     short loc_180008856
0x18000888f  mov     dword ptr [rdi], 0
0x180008895  mov     r8, [rsp+21E8h+var_2158]
0x18000889d  test    r8, r8
0x1800088a0  jz      short loc_1800088E8
0x1800088a2  mov     r10d, ebx
0x1800088a5  mov     r9, r8
0x1800088a8  mov     rcx, rsi
0x1800088ab  inc     rcx
0x1800088ae  cmp     [r9+rcx*2], bx
0x1800088b3  jnz     short loc_1800088AB
0x1800088b5  inc     ecx
0x1800088b7  lea     r9, [r9+rcx*2]
0x1800088bb  lea     r10d, [r10+rcx*2]
0x1800088bf  cmp     ecx, 1
0x1800088c2  jnz     short loc_1800088A8
0x1800088c4  mov     [rsp+21E8h+cbData], r10d; cbData
0x1800088c9  mov     [rsp+21E8h+lpData], r8; lpData
0x1800088ce  lea     r9d, [rcx+6]; dwType
0x1800088d2  xor     r8d, r8d; Reserved
0x1800088d5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x1800088da  mov     rcx, [r13+0]; hKey
0x1800088de  call    cs:__imp_RegSetValueExW
0x1800088e4  mov     edi, eax
0x1800088e6  jmp     short loc_1800088F8
0x1800088e8  mov     ecx, 80004005h; int
0x1800088ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800088f3  mov     edi, 0Eh
0x1800088f8  lea     rcx, [rsp+21E8h+var_2158]
0x180008900  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180008905  mov     r15, [rsp+21E8h+var_21B0]
0x18000890a  jmp     loc_180008BCE
0x18000890f  mov     [rsp+21E8h+pulOut], ebx
0x180008913  mov     [rsp+21E8h+var_21B0], rbx
0x180008918  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18000891d  xor     r8d, r8d; dwFlags
0x180008920  xor     edx, edx; lcid
0x180008922  lea     rcx, [rsp+21E8h+String1]; strIn
0x18000892a  call    cs:__imp_VarUI4FromStr
0x180008930  mov     edi, eax
0x180008932  test    eax, eax
0x180008934  jns     short loc_180008947
0x180008936  lea     rcx, [rsp+21E8h+var_21B0]
0x18000893b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008940  mov     eax, edi
0x180008942  jmp     loc_180008BF9
0x180008947  mov     eax, [rsp+21E8h+pulOut]
0x18000894b  mov     dword ptr [rsp+21E8h+Data], eax
0x18000894f  mov     [rsp+21E8h+cbData], 4; cbData
0x180008957  lea     rax, [rsp+21E8h+Data]
0x18000895c  mov     [rsp+21E8h+lpData], rax; lpData
0x180008961  mov     r9d, 4; dwType
0x180008967  xor     r8d, r8d; Reserved
0x18000896a  mov     rdx, r14; lpValueName
0x18000896d  mov     rcx, [r12]; hKey
0x180008971  call    cs:__imp_RegSetValueExW
0x180008977  mov     edi, eax
0x180008979  lea     rcx, [rsp+21E8h+var_21B0]
0x18000897e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008983  jmp     loc_180008BCE
0x180008988  lea     rax, [rsp+21E8h+String1]
0x180008990  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008994  inc     rsi
0x180008997  cmp     [rax+rsi*2], bx
0x18000899b  jnz     short loc_180008994
0x18000899d  mov     dword ptr [rsp+21E8h+Data], esi
0x1800089a1  test    sil, 1
0x1800089a5  jz      short loc_1800089B1
0x1800089a7  mov     eax, 80004005h
0x1800089ac  jmp     loc_180008BF9
0x1800089b1  mov     eax, esi
0x1800089b3  cdq
0x1800089b4  mov     r15d, 2
0x1800089ba  idiv    r15d
0x1800089bd  movsxd  r14, eax
0x1800089c0  mov     [rsp+21E8h+var_2158], rbx
0x1800089c8  mov     rdi, r14
0x1800089cb  mov     [rsp+21E8h+var_2178], r14
0x1800089d0  lea     edx, [r15-1]
0x1800089d4  mov     rcx, r14
0x1800089d7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800089dc  cmp     rax, 100h
0x1800089e2  jbe     short loc_1800089FE
0x1800089e4  mov     rdx, rax
0x1800089e7  lea     rcx, [rsp+21E8h+var_2158]
0x1800089ef  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800089f4  mov     rcx, [rsp+21E8h+var_2158]
0x1800089fc  jmp     short loc_180008A0E
0x1800089fe  lea     rcx, [rsp+21E8h+var_2150]
0x180008a06  mov     [rsp+21E8h+var_2158], rcx
0x180008a0e  mov     r15, [rsp+21E8h+var_2198]
0x180008a13  jmp     short loc_180008A48
0x180008a15  xor     ebx, ebx
0x180008a17  lea     r13d, [rbx+8]
0x180008a1b  mov     esi, dword ptr [rsp+21E8h+Data]
0x180008a1f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180008a27  mov     rdi, [rsp+21E8h+var_2178]
0x180008a2c  mov     rax, [rsp+21E8h+var_2190]
0x180008a31  mov     [rsp+21E8h+var_21B0], rax
0x180008a36  mov     r15, [rsp+21E8h+var_2170]
0x180008a3b  mov     rax, [rsp+21E8h+var_2188]
0x180008a40  mov     [rsp+21E8h+lpValueName], rax
0x180008a45  mov     r14d, edi
0x180008a48  test    rcx, rcx
0x180008a4b  jnz     short loc_180008A5F
0x180008a4d  lea     rcx, [rsp+21E8h+var_2158]
0x180008a55  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180008a5a  jmp     loc_1800089A7
0x180008a5f  mov     r8, rdi; Size
0x180008a62  xor     edx, edx; Val
0x180008a64  call    memset_0
0x180008a69  mov     r10d, ebx
0x180008a6c  test    esi, esi
0x180008a6e  jle     loc_180008B4C
0x180008a74  mov     r12d, 30h ; '0'
0x180008a7a  mov     eax, r10d
0x180008a7d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180008a85  cmp     edx, 61h ; 'a'
0x180008a88  ja      short loc_180008AF7
0x180008a8a  jz      loc_180008B17
0x180008a90  cmp     edx, 38h ; '8'
0x180008a93  ja      short loc_180008AC9
0x180008a95  jz      short loc_180008AC1
0x180008a97  mov     ecx, edx
0x180008a99  sub     ecx, r12d
0x180008a9c  jz      short loc_180008AC1
0x180008a9e  sub     ecx, 1
0x180008aa1  jz      short loc_180008AC1
0x180008aa3  sub     ecx, 1
0x180008aa6  jz      short loc_180008AC1
0x180008aa8  sub     ecx, 1
0x180008aab  jz      short loc_180008AC1
0x180008aad  sub     ecx, 1
0x180008ab0  jz      short loc_180008AC1
0x180008ab2  sub     ecx, 1
0x180008ab5  jz      short loc_180008AC1
0x180008ab7  sub     ecx, 1
0x180008aba  jz      short loc_180008AC1
0x180008abc  cmp     ecx, 1
0x180008abf  jnz     short loc_180008B12
0x180008ac1  mov     r9d, edx
0x180008ac4  sub     r9d, r12d
0x180008ac7  jmp     short loc_180008B1B
0x180008ac9  mov     r9d, edx
0x180008acc  mov     ecx, edx
0x180008ace  sub     ecx, 39h ; '9'
0x180008ad1  jz      short loc_180008AC1
0x180008ad3  sub     ecx, r13d
0x180008ad6  jz      short loc_180008AF1
0x180008ad8  sub     ecx, 1
0x180008adb  jz      short loc_180008AF1
0x180008add  sub     ecx, 1
0x180008ae0  jz      short loc_180008AF1
0x180008ae2  sub     ecx, 1
0x180008ae5  jz      short loc_180008AF1
0x180008ae7  sub     ecx, 1
0x180008aea  jz      short loc_180008AF1
0x180008aec  cmp     ecx, 1
0x180008aef  jnz     short loc_180008B12
0x180008af1  add     r9d, 0FFFFFFC9h
0x180008af5  jmp     short loc_180008B1B
0x180008af7  mov     ecx, edx
0x180008af9  sub     ecx, 62h ; 'b'
0x180008afc  jz      short loc_180008B17
0x180008afe  sub     ecx, 1
0x180008b01  jz      short loc_180008B17
0x180008b03  sub     ecx, 1
0x180008b06  jz      short loc_180008B17
0x180008b08  sub     ecx, 1
0x180008b0b  jz      short loc_180008B17
0x180008b0d  cmp     ecx, 1
0x180008b10  jz      short loc_180008B17
0x180008b12  mov     r9d, ebx
0x180008b15  jmp     short loc_180008B1B
0x180008b17  lea     r9d, [rdx-57h]
0x180008b1b  mov     r8d, r10d
0x180008b1e  shr     r8, 1
0x180008b21  mov     rdx, [rsp+21E8h+var_2158]
0x180008b29  mov     eax, r10d
0x180008b2c  and     eax, 1
0x180008b2f  shl     eax, 2
0x180008b32  mov     ecx, 4
0x180008b37  sub     ecx, eax
0x180008b39  shl     r9b, cl
0x180008b3c  or      [r8+rdx], r9b
0x180008b40  inc     r10d
  ... truncated ...
```
