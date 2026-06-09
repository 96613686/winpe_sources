# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000434c`
- end: `0x1800048cc`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000af10`

## callees

- `0x180002794`
- `0x180002cc0`
- `0x1800034b8`
- `0x18000434c`
- `0x18000497c`
- `0x180004c70`
- `0x1800054a0`
- `0x1800085e0`
- `0x18000ba60`
- `0x18002d80e`
- `0x18002d840`
- `0x18002d900`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800045da`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800045da`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004509`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004525`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004509`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180004525`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000458e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004621`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000481f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004876`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000458e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004621`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000481f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004876`
- `KERNEL32!lstrcmpiW` at `0x1800043e7`
- `KERNEL32!lstrcmpiW` at `0x1800043e7`

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
0x18000434c  push    rbx
0x18000434e  push    rsi
0x18000434f  push    rdi
0x180004350  push    r12
0x180004352  push    r13
0x180004354  push    r14
0x180004356  push    r15
0x180004358  mov     eax, 21B0h
0x18000435d  call    _alloca_probe
0x180004362  sub     rsp, rax
0x180004365  mov     rax, cs:__security_cookie
0x18000436c  xor     rax, rsp
0x18000436f  mov     [rsp+21E8h+var_48], rax
0x180004377  mov     r14, r8
0x18000437a  mov     [rsp+21E8h+lpValueName], r8
0x18000437f  mov     r12, rdx
0x180004382  mov     [rsp+21E8h+var_2198], rdx
0x180004387  mov     r15, rcx
0x18000438a  mov     [rsp+21E8h+var_21B0], rcx
0x18000438f  mov     qword ptr [rsp+21E8h+Data], rdx
0x180004394  mov     [rsp+21E8h+var_2190], rcx
0x180004399  mov     [rsp+21E8h+var_2170], rdx
0x18000439e  mov     [rsp+21E8h+var_2188], r8
0x1800043a3  mov     [rsp+21E8h+var_2168], r9
0x1800043ab  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x1800043b3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800043b8  xor     ebx, ebx
0x1800043ba  test    eax, eax
0x1800043bc  js      loc_1800048A9
0x1800043c2  mov     edi, ebx
0x1800043c4  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800043cb  cmp     edi, 4
0x1800043ce  jnb     loc_1800048A4
0x1800043d4  movsxd  rsi, edi
0x1800043d7  add     rsi, rsi
0x1800043da  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800043df  lea     rcx, [rsp+21E8h+String1]; lpString1
0x1800043e7  call    cs:__imp_lstrcmpiW
0x1800043ed  test    eax, eax
0x1800043ef  jz      short loc_1800043F5
0x1800043f1  inc     edi
0x1800043f3  jmp     short loc_1800043CB
0x1800043f5  movzx   edi, word ptr [r13+rsi*8+8]
0x1800043fb  mov     rcx, r15; this
0x1800043fe  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180004403  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18000440b  mov     rcx, r15; this
0x18000440e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004413  test    eax, eax
0x180004415  js      loc_1800048A9
0x18000441b  mov     r13d, 8
0x180004421  cmp     di, r13w
0x180004425  jz      loc_180004839
0x18000442b  cmp     di, 11h
0x18000442f  jz      loc_180004638
0x180004435  cmp     di, 13h
0x180004439  jz      loc_1800045BF
0x18000443f  mov     eax, 4008h
0x180004444  cmp     di, ax
0x180004447  jnz     loc_18000488B
0x18000444d  lea     rcx, [rsp+21E8h+String1]
0x180004455  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004459  mov     rax, rsi
0x18000445c  inc     rax
0x18000445f  cmp     [rcx+rax*2], bx
0x180004463  jnz     short loc_18000445C
0x180004465  add     eax, 2
0x180004468  mov     [rsp+21E8h+var_2158], rbx
0x180004470  movsxd  rcx, eax
0x180004473  mov     r15d, 2
0x180004479  mov     edx, r15d
0x18000447c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180004481  cmp     rax, 100h
0x180004487  jbe     short loc_1800044A3
0x180004489  mov     rdx, rax
0x18000448c  lea     rcx, [rsp+21E8h+var_2158]
0x180004494  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004499  mov     rdi, [rsp+21E8h+var_2158]
0x1800044a1  jmp     short loc_1800044B3
0x1800044a3  lea     rdi, [rsp+21E8h+var_2150]
0x1800044ab  mov     [rsp+21E8h+var_2158], rdi
0x1800044b3  mov     r13, [rsp+21E8h+var_2198]
0x1800044b8  jmp     short loc_1800044E5
0x1800044ba  xor     ebx, ebx
0x1800044bc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800044c0  lea     r15d, [rbx+2]
0x1800044c4  mov     rdi, [rsp+21E8h+var_2158]
0x1800044cc  mov     r13, qword ptr [rsp+21E8h+Data]
0x1800044d1  mov     rax, [rsp+21E8h+var_2190]
0x1800044d6  mov     [rsp+21E8h+var_21B0], rax
0x1800044db  mov     rax, [rsp+21E8h+var_2188]
0x1800044e0  mov     [rsp+21E8h+lpValueName], rax
0x1800044e5  test    rdi, rdi
0x1800044e8  jz      loc_1800045A3
0x1800044ee  lea     r14, [rsp+21E8h+String1]
0x1800044f6  cmp     [rsp+21E8h+String1], bx
0x1800044fe  jz      short loc_18000453F
0x180004500  mov     r12d, 30h ; '0'
0x180004506  mov     rcx, r14; lpsz
0x180004509  call    cs:__imp_CharNextW
0x18000450f  movzx   ecx, word ptr [r14]
0x180004513  cmp     cx, 5Ch ; '\'
0x180004517  jnz     short loc_180004530
0x180004519  cmp     [rax], r12w
0x18000451d  jnz     short loc_180004530
0x18000451f  mov     [rdi], bx
0x180004522  mov     rcx, rax; lpsz
0x180004525  call    cs:__imp_CharNextW
0x18000452b  mov     r14, rax
0x18000452e  jmp     short loc_180004536
0x180004530  mov     [rdi], cx
0x180004533  add     r14, r15
0x180004536  add     rdi, r15
0x180004539  cmp     [r14], bx
0x18000453d  jnz     short loc_180004506
0x18000453f  mov     dword ptr [rdi], 0
0x180004545  mov     r8, [rsp+21E8h+var_2158]
0x18000454d  test    r8, r8
0x180004550  jz      short loc_180004598
0x180004552  mov     r10d, ebx
0x180004555  mov     r9, r8
0x180004558  mov     rcx, rsi
0x18000455b  inc     rcx
0x18000455e  cmp     [r9+rcx*2], bx
0x180004563  jnz     short loc_18000455B
0x180004565  inc     ecx
0x180004567  lea     r9, [r9+rcx*2]
0x18000456b  lea     r10d, [r10+rcx*2]
0x18000456f  cmp     ecx, 1
0x180004572  jnz     short loc_180004558
0x180004574  mov     [rsp+21E8h+cbData], r10d; cbData
0x180004579  mov     [rsp+21E8h+lpData], r8; lpData
0x18000457e  lea     r9d, [rcx+6]; dwType
0x180004582  xor     r8d, r8d; Reserved
0x180004585  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18000458a  mov     rcx, [r13+0]; hKey
0x18000458e  call    cs:__imp_RegSetValueExW
0x180004594  mov     edi, eax
0x180004596  jmp     short loc_1800045A8
0x180004598  mov     ecx, 80004005h; int
0x18000459d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800045a3  mov     edi, 0Eh
0x1800045a8  lea     rcx, [rsp+21E8h+var_2158]
0x1800045b0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800045b5  mov     r15, [rsp+21E8h+var_21B0]
0x1800045ba  jmp     loc_18000487E
0x1800045bf  mov     [rsp+21E8h+pulOut], ebx
0x1800045c3  mov     [rsp+21E8h+var_21B0], rbx
0x1800045c8  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x1800045cd  xor     r8d, r8d; dwFlags
0x1800045d0  xor     edx, edx; lcid
0x1800045d2  lea     rcx, [rsp+21E8h+String1]; strIn
0x1800045da  call    cs:__imp_VarUI4FromStr
0x1800045e0  mov     edi, eax
0x1800045e2  test    eax, eax
0x1800045e4  jns     short loc_1800045F7
0x1800045e6  lea     rcx, [rsp+21E8h+var_21B0]
0x1800045eb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800045f0  mov     eax, edi
0x1800045f2  jmp     loc_1800048A9
0x1800045f7  mov     eax, [rsp+21E8h+pulOut]
0x1800045fb  mov     dword ptr [rsp+21E8h+Data], eax
0x1800045ff  mov     [rsp+21E8h+cbData], 4; cbData
0x180004607  lea     rax, [rsp+21E8h+Data]
0x18000460c  mov     [rsp+21E8h+lpData], rax; lpData
0x180004611  mov     r9d, 4; dwType
0x180004617  xor     r8d, r8d; Reserved
0x18000461a  mov     rdx, r14; lpValueName
0x18000461d  mov     rcx, [r12]; hKey
0x180004621  call    cs:__imp_RegSetValueExW
0x180004627  mov     edi, eax
0x180004629  lea     rcx, [rsp+21E8h+var_21B0]
0x18000462e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180004633  jmp     loc_18000487E
0x180004638  lea     rax, [rsp+21E8h+String1]
0x180004640  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004644  inc     rsi
0x180004647  cmp     [rax+rsi*2], bx
0x18000464b  jnz     short loc_180004644
0x18000464d  mov     dword ptr [rsp+21E8h+Data], esi
0x180004651  test    sil, 1
0x180004655  jz      short loc_180004661
0x180004657  mov     eax, 80004005h
0x18000465c  jmp     loc_1800048A9
0x180004661  mov     eax, esi
0x180004663  cdq
0x180004664  mov     r15d, 2
0x18000466a  idiv    r15d
0x18000466d  movsxd  r14, eax
0x180004670  mov     [rsp+21E8h+var_2158], rbx
0x180004678  mov     rdi, r14
0x18000467b  mov     [rsp+21E8h+var_2178], r14
0x180004680  lea     edx, [r15-1]
0x180004684  mov     rcx, r14
0x180004687  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000468c  cmp     rax, 100h
0x180004692  jbe     short loc_1800046AE
0x180004694  mov     rdx, rax
0x180004697  lea     rcx, [rsp+21E8h+var_2158]
0x18000469f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800046a4  mov     rcx, [rsp+21E8h+var_2158]
0x1800046ac  jmp     short loc_1800046BE
0x1800046ae  lea     rcx, [rsp+21E8h+var_2150]
0x1800046b6  mov     [rsp+21E8h+var_2158], rcx
0x1800046be  mov     r15, [rsp+21E8h+var_2198]
0x1800046c3  jmp     short loc_1800046F8
0x1800046c5  xor     ebx, ebx
0x1800046c7  lea     r13d, [rbx+8]
0x1800046cb  mov     esi, dword ptr [rsp+21E8h+Data]
0x1800046cf  mov     rcx, [rsp+21E8h+var_2158]; void *
0x1800046d7  mov     rdi, [rsp+21E8h+var_2178]
0x1800046dc  mov     rax, [rsp+21E8h+var_2190]
0x1800046e1  mov     [rsp+21E8h+var_21B0], rax
0x1800046e6  mov     r15, [rsp+21E8h+var_2170]
0x1800046eb  mov     rax, [rsp+21E8h+var_2188]
0x1800046f0  mov     [rsp+21E8h+lpValueName], rax
0x1800046f5  mov     r14d, edi
0x1800046f8  test    rcx, rcx
0x1800046fb  jnz     short loc_18000470F
0x1800046fd  lea     rcx, [rsp+21E8h+var_2158]
0x180004705  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000470a  jmp     loc_180004657
0x18000470f  mov     r8, rdi; Size
0x180004712  xor     edx, edx; Val
0x180004714  call    memset_0
0x180004719  mov     r10d, ebx
0x18000471c  test    esi, esi
0x18000471e  jle     loc_1800047FC
0x180004724  mov     r12d, 30h ; '0'
0x18000472a  mov     eax, r10d
0x18000472d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180004735  cmp     edx, 61h ; 'a'
0x180004738  ja      short loc_1800047A7
0x18000473a  jz      loc_1800047C7
0x180004740  cmp     edx, 38h ; '8'
0x180004743  ja      short loc_180004779
0x180004745  jz      short loc_180004771
0x180004747  mov     ecx, edx
0x180004749  sub     ecx, r12d
0x18000474c  jz      short loc_180004771
0x18000474e  sub     ecx, 1
0x180004751  jz      short loc_180004771
0x180004753  sub     ecx, 1
0x180004756  jz      short loc_180004771
0x180004758  sub     ecx, 1
0x18000475b  jz      short loc_180004771
0x18000475d  sub     ecx, 1
0x180004760  jz      short loc_180004771
0x180004762  sub     ecx, 1
0x180004765  jz      short loc_180004771
0x180004767  sub     ecx, 1
0x18000476a  jz      short loc_180004771
0x18000476c  cmp     ecx, 1
0x18000476f  jnz     short loc_1800047C2
0x180004771  mov     r9d, edx
0x180004774  sub     r9d, r12d
0x180004777  jmp     short loc_1800047CB
0x180004779  mov     r9d, edx
0x18000477c  mov     ecx, edx
0x18000477e  sub     ecx, 39h ; '9'
0x180004781  jz      short loc_180004771
0x180004783  sub     ecx, r13d
0x180004786  jz      short loc_1800047A1
0x180004788  sub     ecx, 1
0x18000478b  jz      short loc_1800047A1
0x18000478d  sub     ecx, 1
0x180004790  jz      short loc_1800047A1
0x180004792  sub     ecx, 1
0x180004795  jz      short loc_1800047A1
0x180004797  sub     ecx, 1
0x18000479a  jz      short loc_1800047A1
0x18000479c  cmp     ecx, 1
0x18000479f  jnz     short loc_1800047C2
0x1800047a1  add     r9d, 0FFFFFFC9h
0x1800047a5  jmp     short loc_1800047CB
0x1800047a7  mov     ecx, edx
0x1800047a9  sub     ecx, 62h ; 'b'
0x1800047ac  jz      short loc_1800047C7
0x1800047ae  sub     ecx, 1
0x1800047b1  jz      short loc_1800047C7
0x1800047b3  sub     ecx, 1
0x1800047b6  jz      short loc_1800047C7
0x1800047b8  sub     ecx, 1
0x1800047bb  jz      short loc_1800047C7
0x1800047bd  cmp     ecx, 1
0x1800047c0  jz      short loc_1800047C7
0x1800047c2  mov     r9d, ebx
0x1800047c5  jmp     short loc_1800047CB
0x1800047c7  lea     r9d, [rdx-57h]
0x1800047cb  mov     r8d, r10d
0x1800047ce  shr     r8, 1
0x1800047d1  mov     rdx, [rsp+21E8h+var_2158]
0x1800047d9  mov     eax, r10d
0x1800047dc  and     eax, 1
0x1800047df  shl     eax, 2
0x1800047e2  mov     ecx, 4
0x1800047e7  sub     ecx, eax
0x1800047e9  shl     r9b, cl
0x1800047ec  or      [r8+rdx], r9b
0x1800047f0  inc     r10d
  ... truncated ...
```
