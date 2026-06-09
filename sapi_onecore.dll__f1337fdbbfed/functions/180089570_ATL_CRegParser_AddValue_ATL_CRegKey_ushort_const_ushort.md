# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180089570`
- end: `0x180089af0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18009876c`

## callees

- `0x180046ec0`
- `0x180079e30`
- `0x18007aae4`
- `0x18008096c`
- `0x18008297c`
- `0x180084df0`
- `0x180089570`
- `0x180089ba0`
- `0x180089f98`
- `0x180094abc`
- `0x18009c384`
- `0x18027b320`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800897fe`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800897fe`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18008972d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180089749`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18008972d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180089749`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800897b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180089845`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180089a43`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180089a9a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800897b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180089845`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180089a43`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180089a9a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18008960b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18008960b`

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
0x180089570  push    rbx
0x180089572  push    rsi
0x180089573  push    rdi
0x180089574  push    r12
0x180089576  push    r13
0x180089578  push    r14
0x18008957a  push    r15
0x18008957c  mov     eax, 21B0h
0x180089581  call    _alloca_probe
0x180089586  sub     rsp, rax
0x180089589  mov     rax, cs:__security_cookie
0x180089590  xor     rax, rsp
0x180089593  mov     [rsp+21E8h+var_48], rax
0x18008959b  mov     r14, r8
0x18008959e  mov     [rsp+21E8h+lpValueName], r8
0x1800895a3  mov     r12, rdx
0x1800895a6  mov     [rsp+21E8h+var_2198], rdx
0x1800895ab  mov     r15, rcx
0x1800895ae  mov     [rsp+21E8h+var_21B0], rcx
0x1800895b3  mov     qword ptr [rsp+21E8h+Data], rdx
0x1800895b8  mov     [rsp+21E8h+var_2190], rcx
0x1800895bd  mov     [rsp+21E8h+var_2170], rdx
0x1800895c2  mov     [rsp+21E8h+var_2188], r8
0x1800895c7  mov     [rsp+21E8h+var_2168], r9
0x1800895cf  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x1800895d7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800895dc  xor     ebx, ebx
0x1800895de  test    eax, eax
0x1800895e0  js      loc_180089ACD
0x1800895e6  mov     edi, ebx
0x1800895e8  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800895ef  cmp     edi, 4
0x1800895f2  jnb     loc_180089AC8
0x1800895f8  movsxd  rsi, edi
0x1800895fb  add     rsi, rsi
0x1800895fe  mov     rdx, [r13+rsi*8+0]; lpString2
0x180089603  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18008960b  call    cs:__imp_lstrcmpiW
0x180089611  test    eax, eax
0x180089613  jz      short loc_180089619
0x180089615  inc     edi
0x180089617  jmp     short loc_1800895EF
0x180089619  movzx   edi, word ptr [r13+rsi*8+8]
0x18008961f  mov     rcx, r15; this
0x180089622  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180089627  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18008962f  mov     rcx, r15; this
0x180089632  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180089637  test    eax, eax
0x180089639  js      loc_180089ACD
0x18008963f  mov     r13d, 8
0x180089645  cmp     di, r13w
0x180089649  jz      loc_180089A5D
0x18008964f  cmp     di, 11h
0x180089653  jz      loc_18008985C
0x180089659  cmp     di, 13h
0x18008965d  jz      loc_1800897E3
0x180089663  mov     eax, 4008h
0x180089668  cmp     di, ax
0x18008966b  jnz     loc_180089AAF
0x180089671  lea     rcx, [rsp+21E8h+String1]
0x180089679  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008967d  mov     rax, rsi
0x180089680  inc     rax
0x180089683  cmp     [rcx+rax*2], bx
0x180089687  jnz     short loc_180089680
0x180089689  add     eax, 2
0x18008968c  mov     [rsp+21E8h+var_2158], rbx
0x180089694  movsxd  rcx, eax
0x180089697  mov     r15d, 2
0x18008969d  mov     edx, r15d
0x1800896a0  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800896a5  cmp     rax, 100h
0x1800896ab  jbe     short loc_1800896C7
0x1800896ad  mov     rdx, rax
0x1800896b0  lea     rcx, [rsp+21E8h+var_2158]
0x1800896b8  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800896bd  mov     rdi, [rsp+21E8h+var_2158]
0x1800896c5  jmp     short loc_1800896D7
0x1800896c7  lea     rdi, [rsp+21E8h+var_2150]
0x1800896cf  mov     [rsp+21E8h+var_2158], rdi
0x1800896d7  mov     r13, [rsp+21E8h+var_2198]
0x1800896dc  jmp     short loc_180089709
0x1800896de  xor     ebx, ebx
0x1800896e0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800896e4  lea     r15d, [rbx+2]
0x1800896e8  mov     rdi, [rsp+21E8h+var_2158]
0x1800896f0  mov     r13, qword ptr [rsp+21E8h+Data]
0x1800896f5  mov     rax, [rsp+21E8h+var_2190]
0x1800896fa  mov     [rsp+21E8h+var_21B0], rax
0x1800896ff  mov     rax, [rsp+21E8h+var_2188]
0x180089704  mov     [rsp+21E8h+lpValueName], rax
0x180089709  test    rdi, rdi
0x18008970c  jz      loc_1800897C7
0x180089712  lea     r14, [rsp+21E8h+String1]
0x18008971a  cmp     [rsp+21E8h+String1], bx
0x180089722  jz      short loc_180089763
0x180089724  mov     r12d, 30h ; '0'
0x18008972a  mov     rcx, r14; lpsz
0x18008972d  call    cs:__imp_CharNextW
0x180089733  movzx   ecx, word ptr [r14]
0x180089737  cmp     cx, 5Ch ; '\'
0x18008973b  jnz     short loc_180089754
0x18008973d  cmp     [rax], r12w
0x180089741  jnz     short loc_180089754
0x180089743  mov     [rdi], bx
0x180089746  mov     rcx, rax; lpsz
0x180089749  call    cs:__imp_CharNextW
0x18008974f  mov     r14, rax
0x180089752  jmp     short loc_18008975A
0x180089754  mov     [rdi], cx
0x180089757  add     r14, r15
0x18008975a  add     rdi, r15
0x18008975d  cmp     [r14], bx
0x180089761  jnz     short loc_18008972A
0x180089763  mov     dword ptr [rdi], 0
0x180089769  mov     r8, [rsp+21E8h+var_2158]
0x180089771  test    r8, r8
0x180089774  jz      short loc_1800897BC
0x180089776  mov     r10d, ebx
0x180089779  mov     r9, r8
0x18008977c  mov     rcx, rsi
0x18008977f  inc     rcx
0x180089782  cmp     [r9+rcx*2], bx
0x180089787  jnz     short loc_18008977F
0x180089789  inc     ecx
0x18008978b  lea     r9, [r9+rcx*2]
0x18008978f  lea     r10d, [r10+rcx*2]
0x180089793  cmp     ecx, 1
0x180089796  jnz     short loc_18008977C
0x180089798  mov     [rsp+21E8h+cbData], r10d; cbData
0x18008979d  mov     [rsp+21E8h+lpData], r8; lpData
0x1800897a2  lea     r9d, [rcx+6]; dwType
0x1800897a6  xor     r8d, r8d; Reserved
0x1800897a9  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x1800897ae  mov     rcx, [r13+0]; hKey
0x1800897b2  call    cs:__imp_RegSetValueExW
0x1800897b8  mov     edi, eax
0x1800897ba  jmp     short loc_1800897CC
0x1800897bc  mov     ecx, 80004005h; int
0x1800897c1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800897c7  mov     edi, 0Eh
0x1800897cc  lea     rcx, [rsp+21E8h+var_2158]
0x1800897d4  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800897d9  mov     r15, [rsp+21E8h+var_21B0]
0x1800897de  jmp     loc_180089AA2
0x1800897e3  mov     [rsp+21E8h+pulOut], ebx
0x1800897e7  mov     [rsp+21E8h+var_21B0], rbx
0x1800897ec  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x1800897f1  xor     r8d, r8d; dwFlags
0x1800897f4  xor     edx, edx; lcid
0x1800897f6  lea     rcx, [rsp+21E8h+String1]; strIn
0x1800897fe  call    cs:__imp_VarUI4FromStr
0x180089804  mov     edi, eax
0x180089806  test    eax, eax
0x180089808  jns     short loc_18008981B
0x18008980a  lea     rcx, [rsp+21E8h+var_21B0]
0x18008980f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180089814  mov     eax, edi
0x180089816  jmp     loc_180089ACD
0x18008981b  mov     eax, [rsp+21E8h+pulOut]
0x18008981f  mov     dword ptr [rsp+21E8h+Data], eax
0x180089823  mov     [rsp+21E8h+cbData], 4; cbData
0x18008982b  lea     rax, [rsp+21E8h+Data]
0x180089830  mov     [rsp+21E8h+lpData], rax; lpData
0x180089835  mov     r9d, 4; dwType
0x18008983b  xor     r8d, r8d; Reserved
0x18008983e  mov     rdx, r14; lpValueName
0x180089841  mov     rcx, [r12]; hKey
0x180089845  call    cs:__imp_RegSetValueExW
0x18008984b  mov     edi, eax
0x18008984d  lea     rcx, [rsp+21E8h+var_21B0]
0x180089852  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180089857  jmp     loc_180089AA2
0x18008985c  lea     rax, [rsp+21E8h+String1]
0x180089864  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180089868  inc     rsi
0x18008986b  cmp     [rax+rsi*2], bx
0x18008986f  jnz     short loc_180089868
0x180089871  mov     dword ptr [rsp+21E8h+Data], esi
0x180089875  test    sil, 1
0x180089879  jz      short loc_180089885
0x18008987b  mov     eax, 80004005h
0x180089880  jmp     loc_180089ACD
0x180089885  mov     eax, esi
0x180089887  cdq
0x180089888  mov     r15d, 2
0x18008988e  idiv    r15d
0x180089891  movsxd  r14, eax
0x180089894  mov     [rsp+21E8h+var_2158], rbx
0x18008989c  mov     rdi, r14
0x18008989f  mov     [rsp+21E8h+var_2178], r14
0x1800898a4  lea     edx, [r15-1]
0x1800898a8  mov     rcx, r14
0x1800898ab  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800898b0  cmp     rax, 100h
0x1800898b6  jbe     short loc_1800898D2
0x1800898b8  mov     rdx, rax
0x1800898bb  lea     rcx, [rsp+21E8h+var_2158]
0x1800898c3  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800898c8  mov     rcx, [rsp+21E8h+var_2158]
0x1800898d0  jmp     short loc_1800898E2
0x1800898d2  lea     rcx, [rsp+21E8h+var_2150]
0x1800898da  mov     [rsp+21E8h+var_2158], rcx
0x1800898e2  mov     r15, [rsp+21E8h+var_2198]
0x1800898e7  jmp     short loc_18008991C
0x1800898e9  xor     ebx, ebx
0x1800898eb  lea     r13d, [rbx+8]
0x1800898ef  mov     esi, dword ptr [rsp+21E8h+Data]
0x1800898f3  mov     rcx, [rsp+21E8h+var_2158]; void *
0x1800898fb  mov     rdi, [rsp+21E8h+var_2178]
0x180089900  mov     rax, [rsp+21E8h+var_2190]
0x180089905  mov     [rsp+21E8h+var_21B0], rax
0x18008990a  mov     r15, [rsp+21E8h+var_2170]
0x18008990f  mov     rax, [rsp+21E8h+var_2188]
0x180089914  mov     [rsp+21E8h+lpValueName], rax
0x180089919  mov     r14d, edi
0x18008991c  test    rcx, rcx
0x18008991f  jnz     short loc_180089933
0x180089921  lea     rcx, [rsp+21E8h+var_2158]
0x180089929  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18008992e  jmp     loc_18008987B
0x180089933  mov     r8, rdi; Size
0x180089936  xor     edx, edx; Val
0x180089938  call    memset_0
0x18008993d  mov     r10d, ebx
0x180089940  test    esi, esi
0x180089942  jle     loc_180089A20
0x180089948  mov     r12d, 30h ; '0'
0x18008994e  mov     eax, r10d
0x180089951  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180089959  cmp     edx, 61h ; 'a'
0x18008995c  ja      short loc_1800899CB
0x18008995e  jz      loc_1800899EB
0x180089964  cmp     edx, 38h ; '8'
0x180089967  ja      short loc_18008999D
0x180089969  jz      short loc_180089995
0x18008996b  mov     ecx, edx
0x18008996d  sub     ecx, r12d
0x180089970  jz      short loc_180089995
0x180089972  sub     ecx, 1
0x180089975  jz      short loc_180089995
0x180089977  sub     ecx, 1
0x18008997a  jz      short loc_180089995
0x18008997c  sub     ecx, 1
0x18008997f  jz      short loc_180089995
0x180089981  sub     ecx, 1
0x180089984  jz      short loc_180089995
0x180089986  sub     ecx, 1
0x180089989  jz      short loc_180089995
0x18008998b  sub     ecx, 1
0x18008998e  jz      short loc_180089995
0x180089990  cmp     ecx, 1
0x180089993  jnz     short loc_1800899E6
0x180089995  mov     r9d, edx
0x180089998  sub     r9d, r12d
0x18008999b  jmp     short loc_1800899EF
0x18008999d  mov     r9d, edx
0x1800899a0  mov     ecx, edx
0x1800899a2  sub     ecx, 39h ; '9'
0x1800899a5  jz      short loc_180089995
0x1800899a7  sub     ecx, r13d
0x1800899aa  jz      short loc_1800899C5
0x1800899ac  sub     ecx, 1
0x1800899af  jz      short loc_1800899C5
0x1800899b1  sub     ecx, 1
0x1800899b4  jz      short loc_1800899C5
0x1800899b6  sub     ecx, 1
0x1800899b9  jz      short loc_1800899C5
0x1800899bb  sub     ecx, 1
0x1800899be  jz      short loc_1800899C5
0x1800899c0  cmp     ecx, 1
0x1800899c3  jnz     short loc_1800899E6
0x1800899c5  add     r9d, 0FFFFFFC9h
0x1800899c9  jmp     short loc_1800899EF
0x1800899cb  mov     ecx, edx
0x1800899cd  sub     ecx, 62h ; 'b'
0x1800899d0  jz      short loc_1800899EB
0x1800899d2  sub     ecx, 1
0x1800899d5  jz      short loc_1800899EB
0x1800899d7  sub     ecx, 1
0x1800899da  jz      short loc_1800899EB
0x1800899dc  sub     ecx, 1
0x1800899df  jz      short loc_1800899EB
0x1800899e1  cmp     ecx, 1
0x1800899e4  jz      short loc_1800899EB
0x1800899e6  mov     r9d, ebx
0x1800899e9  jmp     short loc_1800899EF
0x1800899eb  lea     r9d, [rdx-57h]
0x1800899ef  mov     r8d, r10d
0x1800899f2  shr     r8, 1
0x1800899f5  mov     rdx, [rsp+21E8h+var_2158]
0x1800899fd  mov     eax, r10d
0x180089a00  and     eax, 1
0x180089a03  shl     eax, 2
0x180089a06  mov     ecx, 4
0x180089a0b  sub     ecx, eax
0x180089a0d  shl     r9b, cl
0x180089a10  or      [r8+rdx], r9b
0x180089a14  inc     r10d
  ... truncated ...
```
