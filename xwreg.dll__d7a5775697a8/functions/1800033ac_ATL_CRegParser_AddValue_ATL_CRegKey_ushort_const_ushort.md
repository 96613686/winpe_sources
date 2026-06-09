# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800033ac`
- end: `0x18000392c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800055a0`

## callees

- `0x180002ab8`
- `0x180002b1c`
- `0x180002d54`
- `0x1800033ac`
- `0x180003934`
- `0x180003bb4`
- `0x180003ca8`
- `0x180004b60`
- `0x180005ef0`
- `0x1800127d6`
- `0x180012800`
- `0x1800128c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800035ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003681`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000387f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800038d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800035ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003681`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000387f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800038d6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003569`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003585`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003569`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180003585`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003447`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180003447`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000363a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000363a`

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
0x1800033ac  push    rbx
0x1800033ae  push    rsi
0x1800033af  push    rdi
0x1800033b0  push    r12
0x1800033b2  push    r13
0x1800033b4  push    r14
0x1800033b6  push    r15
0x1800033b8  mov     eax, 21B0h
0x1800033bd  call    _alloca_probe
0x1800033c2  sub     rsp, rax
0x1800033c5  mov     rax, cs:__security_cookie
0x1800033cc  xor     rax, rsp
0x1800033cf  mov     [rsp+21E8h+var_48], rax
0x1800033d7  mov     r14, r8
0x1800033da  mov     [rsp+21E8h+lpValueName], r8
0x1800033df  mov     r12, rdx
0x1800033e2  mov     [rsp+21E8h+var_2198], rdx
0x1800033e7  mov     r15, rcx
0x1800033ea  mov     [rsp+21E8h+var_21B0], rcx
0x1800033ef  mov     qword ptr [rsp+21E8h+Data], rdx
0x1800033f4  mov     [rsp+21E8h+var_2190], rcx
0x1800033f9  mov     [rsp+21E8h+var_2170], rdx
0x1800033fe  mov     [rsp+21E8h+var_2188], r8
0x180003403  mov     [rsp+21E8h+var_2168], r9
0x18000340b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180003413  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003418  xor     ebx, ebx
0x18000341a  test    eax, eax
0x18000341c  js      loc_180003909
0x180003422  mov     edi, ebx
0x180003424  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000342b  cmp     edi, 4
0x18000342e  jnb     loc_180003904
0x180003434  movsxd  rsi, edi
0x180003437  add     rsi, rsi
0x18000343a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000343f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180003447  call    cs:__imp_lstrcmpiW
0x18000344d  test    eax, eax
0x18000344f  jz      short loc_180003455
0x180003451  inc     edi
0x180003453  jmp     short loc_18000342B
0x180003455  movzx   edi, word ptr [r13+rsi*8+8]
0x18000345b  mov     rcx, r15; this
0x18000345e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180003463  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18000346b  mov     rcx, r15; this
0x18000346e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003473  test    eax, eax
0x180003475  js      loc_180003909
0x18000347b  mov     r13d, 8
0x180003481  cmp     di, r13w
0x180003485  jz      loc_180003899
0x18000348b  cmp     di, 11h
0x18000348f  jz      loc_180003698
0x180003495  cmp     di, 13h
0x180003499  jz      loc_18000361F
0x18000349f  mov     eax, 4008h
0x1800034a4  cmp     di, ax
0x1800034a7  jnz     loc_1800038EB
0x1800034ad  lea     rcx, [rsp+21E8h+String1]
0x1800034b5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800034b9  mov     rax, rsi
0x1800034bc  inc     rax
0x1800034bf  cmp     [rcx+rax*2], bx
0x1800034c3  jnz     short loc_1800034BC
0x1800034c5  add     eax, 2
0x1800034c8  mov     [rsp+21E8h+var_2158], rbx
0x1800034d0  movsxd  rcx, eax
0x1800034d3  mov     r15d, 2
0x1800034d9  mov     edx, r15d
0x1800034dc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800034e1  cmp     rax, 100h
0x1800034e7  jbe     short loc_180003503
0x1800034e9  mov     rdx, rax
0x1800034ec  lea     rcx, [rsp+21E8h+var_2158]
0x1800034f4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800034f9  mov     rdi, [rsp+21E8h+var_2158]
0x180003501  jmp     short loc_180003513
0x180003503  lea     rdi, [rsp+21E8h+var_2150]
0x18000350b  mov     [rsp+21E8h+var_2158], rdi
0x180003513  mov     r13, [rsp+21E8h+var_2198]
0x180003518  jmp     short loc_180003545
0x18000351a  xor     ebx, ebx
0x18000351c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180003520  lea     r15d, [rbx+2]
0x180003524  mov     rdi, [rsp+21E8h+var_2158]
0x18000352c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180003531  mov     rax, [rsp+21E8h+var_2190]
0x180003536  mov     [rsp+21E8h+var_21B0], rax
0x18000353b  mov     rax, [rsp+21E8h+var_2188]
0x180003540  mov     [rsp+21E8h+lpValueName], rax
0x180003545  test    rdi, rdi
0x180003548  jz      loc_180003603
0x18000354e  lea     r14, [rsp+21E8h+String1]
0x180003556  cmp     [rsp+21E8h+String1], bx
0x18000355e  jz      short loc_18000359F
0x180003560  mov     r12d, 30h ; '0'
0x180003566  mov     rcx, r14; lpsz
0x180003569  call    cs:__imp_CharNextW
0x18000356f  movzx   ecx, word ptr [r14]
0x180003573  cmp     cx, 5Ch ; '\'
0x180003577  jnz     short loc_180003590
0x180003579  cmp     [rax], r12w
0x18000357d  jnz     short loc_180003590
0x18000357f  mov     [rdi], bx
0x180003582  mov     rcx, rax; lpsz
0x180003585  call    cs:__imp_CharNextW
0x18000358b  mov     r14, rax
0x18000358e  jmp     short loc_180003596
0x180003590  mov     [rdi], cx
0x180003593  add     r14, r15
0x180003596  add     rdi, r15
0x180003599  cmp     [r14], bx
0x18000359d  jnz     short loc_180003566
0x18000359f  mov     dword ptr [rdi], 0
0x1800035a5  mov     r8, [rsp+21E8h+var_2158]
0x1800035ad  test    r8, r8
0x1800035b0  jz      short loc_1800035F8
0x1800035b2  mov     r10d, ebx
0x1800035b5  mov     r9, r8
0x1800035b8  mov     rcx, rsi
0x1800035bb  inc     rcx
0x1800035be  cmp     [r9+rcx*2], bx
0x1800035c3  jnz     short loc_1800035BB
0x1800035c5  inc     ecx
0x1800035c7  lea     r9, [r9+rcx*2]
0x1800035cb  lea     r10d, [r10+rcx*2]
0x1800035cf  cmp     ecx, 1
0x1800035d2  jnz     short loc_1800035B8
0x1800035d4  mov     [rsp+21E8h+cbData], r10d; cbData
0x1800035d9  mov     [rsp+21E8h+lpData], r8; lpData
0x1800035de  lea     r9d, [rcx+6]; dwType
0x1800035e2  xor     r8d, r8d; Reserved
0x1800035e5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x1800035ea  mov     rcx, [r13+0]; hKey
0x1800035ee  call    cs:__imp_RegSetValueExW
0x1800035f4  mov     edi, eax
0x1800035f6  jmp     short loc_180003608
0x1800035f8  mov     ecx, 80004005h; int
0x1800035fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003603  mov     edi, 0Eh
0x180003608  lea     rcx, [rsp+21E8h+var_2158]
0x180003610  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180003615  mov     r15, [rsp+21E8h+var_21B0]
0x18000361a  jmp     loc_1800038DE
0x18000361f  mov     [rsp+21E8h+pulOut], ebx
0x180003623  mov     [rsp+21E8h+var_21B0], rbx
0x180003628  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18000362d  xor     r8d, r8d; dwFlags
0x180003630  xor     edx, edx; lcid
0x180003632  lea     rcx, [rsp+21E8h+String1]; strIn
0x18000363a  call    cs:__imp_VarUI4FromStr
0x180003640  mov     edi, eax
0x180003642  test    eax, eax
0x180003644  jns     short loc_180003657
0x180003646  lea     rcx, [rsp+21E8h+var_21B0]
0x18000364b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003650  mov     eax, edi
0x180003652  jmp     loc_180003909
0x180003657  mov     eax, [rsp+21E8h+pulOut]
0x18000365b  mov     dword ptr [rsp+21E8h+Data], eax
0x18000365f  mov     [rsp+21E8h+cbData], 4; cbData
0x180003667  lea     rax, [rsp+21E8h+Data]
0x18000366c  mov     [rsp+21E8h+lpData], rax; lpData
0x180003671  mov     r9d, 4; dwType
0x180003677  xor     r8d, r8d; Reserved
0x18000367a  mov     rdx, r14; lpValueName
0x18000367d  mov     rcx, [r12]; hKey
0x180003681  call    cs:__imp_RegSetValueExW
0x180003687  mov     edi, eax
0x180003689  lea     rcx, [rsp+21E8h+var_21B0]
0x18000368e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003693  jmp     loc_1800038DE
0x180003698  lea     rax, [rsp+21E8h+String1]
0x1800036a0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800036a4  inc     rsi
0x1800036a7  cmp     [rax+rsi*2], bx
0x1800036ab  jnz     short loc_1800036A4
0x1800036ad  mov     dword ptr [rsp+21E8h+Data], esi
0x1800036b1  test    sil, 1
0x1800036b5  jz      short loc_1800036C1
0x1800036b7  mov     eax, 80004005h
0x1800036bc  jmp     loc_180003909
0x1800036c1  mov     eax, esi
0x1800036c3  cdq
0x1800036c4  mov     r15d, 2
0x1800036ca  idiv    r15d
0x1800036cd  movsxd  r14, eax
0x1800036d0  mov     [rsp+21E8h+var_2158], rbx
0x1800036d8  mov     rdi, r14
0x1800036db  mov     [rsp+21E8h+var_2178], r14
0x1800036e0  lea     edx, [r15-1]
0x1800036e4  mov     rcx, r14
0x1800036e7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800036ec  cmp     rax, 100h
0x1800036f2  jbe     short loc_18000370E
0x1800036f4  mov     rdx, rax
0x1800036f7  lea     rcx, [rsp+21E8h+var_2158]
0x1800036ff  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003704  mov     rcx, [rsp+21E8h+var_2158]
0x18000370c  jmp     short loc_18000371E
0x18000370e  lea     rcx, [rsp+21E8h+var_2150]
0x180003716  mov     [rsp+21E8h+var_2158], rcx
0x18000371e  mov     r15, [rsp+21E8h+var_2198]
0x180003723  jmp     short loc_180003758
0x180003725  xor     ebx, ebx
0x180003727  lea     r13d, [rbx+8]
0x18000372b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18000372f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180003737  mov     rdi, [rsp+21E8h+var_2178]
0x18000373c  mov     rax, [rsp+21E8h+var_2190]
0x180003741  mov     [rsp+21E8h+var_21B0], rax
0x180003746  mov     r15, [rsp+21E8h+var_2170]
0x18000374b  mov     rax, [rsp+21E8h+var_2188]
0x180003750  mov     [rsp+21E8h+lpValueName], rax
0x180003755  mov     r14d, edi
0x180003758  test    rcx, rcx
0x18000375b  jnz     short loc_18000376F
0x18000375d  lea     rcx, [rsp+21E8h+var_2158]
0x180003765  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000376a  jmp     loc_1800036B7
0x18000376f  mov     r8, rdi; Size
0x180003772  xor     edx, edx; Val
0x180003774  call    memset_0
0x180003779  mov     r10d, ebx
0x18000377c  test    esi, esi
0x18000377e  jle     loc_18000385C
0x180003784  mov     r12d, 30h ; '0'
0x18000378a  mov     eax, r10d
0x18000378d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180003795  cmp     edx, 61h ; 'a'
0x180003798  ja      short loc_180003807
0x18000379a  jz      loc_180003827
0x1800037a0  cmp     edx, 38h ; '8'
0x1800037a3  ja      short loc_1800037D9
0x1800037a5  jz      short loc_1800037D1
0x1800037a7  mov     ecx, edx
0x1800037a9  sub     ecx, r12d
0x1800037ac  jz      short loc_1800037D1
0x1800037ae  sub     ecx, 1
0x1800037b1  jz      short loc_1800037D1
0x1800037b3  sub     ecx, 1
0x1800037b6  jz      short loc_1800037D1
0x1800037b8  sub     ecx, 1
0x1800037bb  jz      short loc_1800037D1
0x1800037bd  sub     ecx, 1
0x1800037c0  jz      short loc_1800037D1
0x1800037c2  sub     ecx, 1
0x1800037c5  jz      short loc_1800037D1
0x1800037c7  sub     ecx, 1
0x1800037ca  jz      short loc_1800037D1
0x1800037cc  cmp     ecx, 1
0x1800037cf  jnz     short loc_180003822
0x1800037d1  mov     r9d, edx
0x1800037d4  sub     r9d, r12d
0x1800037d7  jmp     short loc_18000382B
0x1800037d9  mov     r9d, edx
0x1800037dc  mov     ecx, edx
0x1800037de  sub     ecx, 39h ; '9'
0x1800037e1  jz      short loc_1800037D1
0x1800037e3  sub     ecx, r13d
0x1800037e6  jz      short loc_180003801
0x1800037e8  sub     ecx, 1
0x1800037eb  jz      short loc_180003801
0x1800037ed  sub     ecx, 1
0x1800037f0  jz      short loc_180003801
0x1800037f2  sub     ecx, 1
0x1800037f5  jz      short loc_180003801
0x1800037f7  sub     ecx, 1
0x1800037fa  jz      short loc_180003801
0x1800037fc  cmp     ecx, 1
0x1800037ff  jnz     short loc_180003822
0x180003801  add     r9d, 0FFFFFFC9h
0x180003805  jmp     short loc_18000382B
0x180003807  mov     ecx, edx
0x180003809  sub     ecx, 62h ; 'b'
0x18000380c  jz      short loc_180003827
0x18000380e  sub     ecx, 1
0x180003811  jz      short loc_180003827
0x180003813  sub     ecx, 1
0x180003816  jz      short loc_180003827
0x180003818  sub     ecx, 1
0x18000381b  jz      short loc_180003827
0x18000381d  cmp     ecx, 1
0x180003820  jz      short loc_180003827
0x180003822  mov     r9d, ebx
0x180003825  jmp     short loc_18000382B
0x180003827  lea     r9d, [rdx-57h]
0x18000382b  mov     r8d, r10d
0x18000382e  shr     r8, 1
0x180003831  mov     rdx, [rsp+21E8h+var_2158]
0x180003839  mov     eax, r10d
0x18000383c  and     eax, 1
0x18000383f  shl     eax, 2
0x180003842  mov     ecx, 4
0x180003847  sub     ecx, eax
0x180003849  shl     r9b, cl
0x18000384c  or      [r8+rdx], r9b
0x180003850  inc     r10d
  ... truncated ...
```
