# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000316c`
- end: `0x18000353d`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `977`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000d678`

## callees

- `0x180002158`
- `0x180002274`
- `0x18000273c`
- `0x18000316c`
- `0x1800037c0`
- `0x18000454c`
- `0x180004ce0`
- `0x18000ccc4`
- `0x18000f7f4`
- `0x180035b9a`
- `0x180035bd0`
- `0x180035c60`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800031da`
- `KERNEL32!lstrcmpiW` at `0x1800031da`
- `USER32!CharNextW` at `0x1800032ba`
- `USER32!CharNextW` at `0x1800032d6`
- `USER32!CharNextW` at `0x1800032ba`
- `USER32!CharNextW` at `0x1800032d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003339`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800033b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003339`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800033b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800034f1`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000336e`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000336e`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v7; // r12
  __int64 result; // rax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r9d
  BYTE *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // ebx
  HRESULT v21; // ebx
  HKEY v22; // rcx
  __int64 v23; // rdi
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int i; // r10d
  unsigned __int8 v28; // al
  int v29; // r10d
  char v30; // dl
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdi
  int Token; // eax
  unsigned int v35; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  ATL::CRegParser *v37; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[264]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v37 = this;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v7);
    result = ATL::CRegParser::NextToken(v7, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v33 = -1;
        do
          ++v33;
        while ( String1[v33] );
        v20 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
        goto LABEL_49;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v37 = 0;
          v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v21 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
            return (unsigned int)v21;
          }
          v22 = *a2;
          *(_DWORD *)Data = pulOut;
          v20 = RegSetValueExW(v22, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_51:
            Token = ATL::CRegParser::NextToken(v7, a4);
            v35 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v35;
          }
          lpData = 0;
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2);
          if ( v12 <= 0x100 )
          {
            v13 = v40;
            lpData = v40;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
            v13 = lpData;
          }
          if ( v13 )
          {
            v14 = String1;
            if ( String1[0] )
            {
              do
              {
                v15 = CharNextW(v14);
                if ( *v14 == 92 && *v15 == 48 )
                {
                  *(_WORD *)v13 = 0;
                  v14 = CharNextW(v15);
                }
                else
                {
                  *(_WORD *)v13 = *v14++;
                }
                v13 += 2;
              }
              while ( *v14 );
              v7 = v37;
            }
            *(_DWORD *)v13 = 0;
            cbData = 0;
            v17 = lpData;
            do
            {
              v18 = -1;
              do
                ++v18;
              while ( *(_WORD *)&v17[2 * v18] );
              v19 = (unsigned int)(v18 + 1);
              v17 += 2 * v19;
              cbData += 2 * v19;
            }
            while ( (_DWORD)v19 != 1 );
            v20 = RegSetValueExW(*a2, a3, 0, 7u, lpData, cbData);
          }
          else
          {
            v20 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_49:
        if ( v20 )
          return ATL::AtlHresultFromWin32(v20);
        goto LABEL_51;
      }
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      if ( (v23 & 1) == 0 )
      {
        lpData = 0;
        v24 = (int)v23 / 2;
        v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1);
        if ( v25 <= 0x100 )
        {
          v26 = v40;
          lpData = v40;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
          v26 = lpData;
        }
        if ( v26 )
        {
          memset_0(v26, 0, v24);
          for ( i = 0; i < (int)v23; *(_BYTE *)(v32 + v31) |= v28 << (4 - 4 * v30) )
          {
            v28 = ATL::CRegParser::ChToByte(String1[i]);
            v30 = v29 & 1;
            i = v29 + 1;
          }
          v20 = RegSetValueExW(*a2, a3, 0, 3u, lpData, v24);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_49;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000316c  push    rbp
0x18000316e  push    rbx
0x18000316f  push    rsi
0x180003170  push    rdi
0x180003171  push    r12
0x180003173  push    r13
0x180003175  push    r14
0x180003177  push    r15
0x180003179  lea     rbp, [rsp-2078h]
0x180003181  mov     eax, 2178h
0x180003186  call    _alloca_probe
0x18000318b  sub     rsp, rax
0x18000318e  mov     rax, cs:__security_cookie
0x180003195  xor     rax, rsp
0x180003198  mov     [rbp+20B0h+var_50], rax
0x18000319f  mov     r14, rdx
0x1800031a2  mov     [rsp+21B0h+var_2178], rcx
0x1800031a7  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x1800031ab  mov     r13, r9
0x1800031ae  mov     r15, r8
0x1800031b1  mov     r12, rcx
0x1800031b4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800031b9  xor     esi, esi
0x1800031bb  test    eax, eax
0x1800031bd  js      loc_18000351A
0x1800031c3  mov     ebx, esi
0x1800031c5  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800031cc  movsxd  rdi, ebx
0x1800031cf  lea     rcx, [rbp+20B0h+String1]; lpString1
0x1800031d3  add     rdi, rdi
0x1800031d6  mov     rdx, [rax+rdi*8]; lpString2
0x1800031da  call    cs:__imp_lstrcmpiW
0x1800031e0  test    eax, eax
0x1800031e2  jz      short loc_1800031FC
0x1800031e4  inc     ebx
0x1800031e6  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800031ed  cmp     ebx, 4
0x1800031f0  jb      short loc_1800031CC
0x1800031f2  mov     eax, 80020009h
0x1800031f7  jmp     loc_18000351A
0x1800031fc  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003203  mov     rcx, r12; this
0x180003206  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18000320b  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180003210  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180003214  mov     rcx, r12; this
0x180003217  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000321c  test    eax, eax
0x18000321e  js      loc_18000351A
0x180003224  cmp     bx, 8
0x180003228  jz      loc_1800034BD
0x18000322e  cmp     bx, 11h
0x180003232  jz      loc_1800033C9
0x180003238  cmp     bx, 13h
0x18000323c  jz      loc_180003357
0x180003242  mov     eax, 4008h
0x180003247  cmp     bx, ax
0x18000324a  jnz     loc_180003506
0x180003250  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003254  mov     [rsp+21B0h+var_2160], rsi
0x180003259  mov     rax, rdi
0x18000325c  lea     rcx, [rbp+20B0h+String1]
0x180003260  inc     rax
0x180003263  cmp     [rcx+rax*2], si
0x180003267  jnz     short loc_180003260
0x180003269  add     eax, 2
0x18000326c  mov     edx, 2
0x180003271  movsxd  rcx, eax
0x180003274  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180003279  cmp     rax, 100h
0x18000327f  jbe     short loc_180003295
0x180003281  mov     rdx, rax
0x180003284  lea     rcx, [rsp+21B0h+var_2160]
0x180003289  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000328e  mov     rbx, [rsp+21B0h+var_2160]
0x180003293  jmp     short loc_18000329F
0x180003295  lea     rbx, [rsp+21B0h+var_2158]
0x18000329a  mov     [rsp+21B0h+var_2160], rbx
0x18000329f  test    rbx, rbx
0x1800032a2  jz      loc_180003343
0x1800032a8  xor     eax, eax
0x1800032aa  lea     rsi, [rbp+20B0h+String1]
0x1800032ae  cmp     [rbp+20B0h+String1], ax
0x1800032b2  jz      short loc_1800032F7
0x1800032b4  xor     r12d, r12d
0x1800032b7  mov     rcx, rsi; lpsz
0x1800032ba  call    cs:__imp_CharNextW
0x1800032c0  movzx   ecx, word ptr [rsi]
0x1800032c3  cmp     cx, 5Ch ; '\'
0x1800032c7  jnz     short loc_1800032E1
0x1800032c9  cmp     word ptr [rax], 30h ; '0'
0x1800032cd  jnz     short loc_1800032E1
0x1800032cf  mov     rcx, rax; lpsz
0x1800032d2  mov     [rbx], r12w
0x1800032d6  call    cs:__imp_CharNextW
0x1800032dc  mov     rsi, rax
0x1800032df  jmp     short loc_1800032E8
0x1800032e1  mov     [rbx], cx
0x1800032e4  add     rsi, 2
0x1800032e8  add     rbx, 2
0x1800032ec  cmp     [rsi], r12w
0x1800032f0  jnz     short loc_1800032B7
0x1800032f2  mov     r12, [rsp+21B0h+var_2178]
0x1800032f7  xor     esi, esi
0x1800032f9  mov     [rbx], esi
0x1800032fb  mov     r9d, esi
0x1800032fe  mov     r10, [rsp+21B0h+var_2160]
0x180003303  mov     r8, r10
0x180003306  mov     rcx, rdi
0x180003309  inc     rcx
0x18000330c  cmp     [r8+rcx*2], si
0x180003311  jnz     short loc_180003309
0x180003313  inc     ecx
0x180003315  lea     r8, [r8+rcx*2]
0x180003319  lea     r9d, [r9+rcx*2]
0x18000331d  cmp     ecx, 1
0x180003320  jnz     short loc_180003306
0x180003322  mov     [rsp+21B0h+cbData], r9d; cbData
0x180003327  xor     r8d, r8d; Reserved
0x18000332a  lea     r9d, [rcx+6]; dwType
0x18000332e  mov     [rsp+21B0h+lpData], r10; lpData
0x180003333  mov     rcx, [r14]; hKey
0x180003336  mov     rdx, r15; lpValueName
0x180003339  call    cs:__imp_RegSetValueExW
0x18000333f  mov     ebx, eax
0x180003341  jmp     short loc_180003348
0x180003343  mov     ebx, 0Eh
0x180003348  lea     rcx, [rsp+21B0h+var_2160]
0x18000334d  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180003352  jmp     loc_1800034F9
0x180003357  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x18000335c  mov     [rsp+21B0h+pulOut], esi
0x180003360  xor     r8d, r8d; dwFlags
0x180003363  mov     [rsp+21B0h+var_2178], rsi
0x180003368  xor     edx, edx; lcid
0x18000336a  lea     rcx, [rbp+20B0h+String1]; strIn
0x18000336e  call    cs:__imp_VarUI4FromStr
0x180003374  mov     ebx, eax
0x180003376  test    eax, eax
0x180003378  jns     short loc_18000338B
0x18000337a  lea     rcx, [rsp+21B0h+var_2178]
0x18000337f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180003384  mov     eax, ebx
0x180003386  jmp     loc_18000351A
0x18000338b  mov     eax, [rsp+21B0h+pulOut]
0x18000338f  mov     ecx, 4
0x180003394  mov     [rsp+21B0h+cbData], ecx; cbData
0x180003398  mov     r9d, ecx; dwType
0x18000339b  mov     rcx, [r14]; hKey
0x18000339e  xor     r8d, r8d; Reserved
0x1800033a1  mov     dword ptr [rsp+21B0h+Data], eax
0x1800033a5  mov     rdx, r15; lpValueName
0x1800033a8  lea     rax, [rsp+21B0h+Data]
0x1800033ad  mov     [rsp+21B0h+lpData], rax; lpData
0x1800033b2  call    cs:__imp_RegSetValueExW
0x1800033b8  lea     rcx, [rsp+21B0h+var_2178]
0x1800033bd  mov     ebx, eax
0x1800033bf  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800033c4  jmp     loc_1800034F9
0x1800033c9  lea     rax, [rbp+20B0h+String1]
0x1800033cd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800033d1  inc     rdi
0x1800033d4  cmp     [rax+rdi*2], si
0x1800033d8  jnz     short loc_1800033D1
0x1800033da  test    dil, 1
0x1800033de  jz      short loc_1800033EA
0x1800033e0  mov     eax, 80004005h
0x1800033e5  jmp     loc_18000351A
0x1800033ea  mov     eax, edi
0x1800033ec  mov     [rsp+21B0h+var_2160], 0
0x1800033f5  cdq
0x1800033f6  sub     eax, edx
0x1800033f8  mov     edx, 1
0x1800033fd  sar     eax, 1
0x1800033ff  movsxd  rsi, eax
0x180003402  mov     rcx, rsi
0x180003405  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000340a  cmp     rax, 100h
0x180003410  jbe     short loc_180003426
0x180003412  mov     rdx, rax
0x180003415  lea     rcx, [rsp+21B0h+var_2160]
0x18000341a  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000341f  mov     rcx, [rsp+21B0h+var_2160]
0x180003424  jmp     short loc_180003430
0x180003426  lea     rcx, [rsp+21B0h+var_2158]; void *
0x18000342b  mov     [rsp+21B0h+var_2160], rcx
0x180003430  test    rcx, rcx
0x180003433  jnz     short loc_180003441
0x180003435  lea     rcx, [rsp+21B0h+var_2160]
0x18000343a  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000343f  jmp     short loc_1800033E0
0x180003441  mov     r8, rsi; Size
0x180003444  xor     edx, edx; Val
0x180003446  call    memset_0
0x18000344b  xor     eax, eax
0x18000344d  mov     r10d, eax
0x180003450  test    edi, edi
0x180003452  jle     short loc_18000348A
0x180003454  mov     r8, [rsp+21B0h+var_2160]
0x180003459  mov     ecx, r10d
0x18000345c  mov     r9d, r10d
0x18000345f  shr     r9, 1
0x180003462  movzx   ecx, [rbp+rcx*2+20B0h+String1]; unsigned __int16
0x180003467  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18000346c  mov     edx, r10d
0x18000346f  mov     ecx, 4
0x180003474  and     edx, 1
0x180003477  inc     r10d
0x18000347a  shl     edx, 2
0x18000347d  sub     ecx, edx
0x18000347f  shl     al, cl
0x180003481  or      [r9+r8], al
0x180003485  cmp     r10d, edi
0x180003488  jl      short loc_180003454
0x18000348a  mov     rax, [rsp+21B0h+var_2160]
0x18000348f  mov     r9d, 3; dwType
0x180003495  mov     rcx, [r14]; hKey
0x180003498  xor     r8d, r8d; Reserved
0x18000349b  mov     [rsp+21B0h+cbData], esi; cbData
0x18000349f  mov     rdx, r15; lpValueName
0x1800034a2  mov     [rsp+21B0h+lpData], rax; lpData
0x1800034a7  call    cs:__imp_RegSetValueExW
0x1800034ad  lea     rcx, [rsp+21B0h+var_2160]
0x1800034b2  mov     ebx, eax
0x1800034b4  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800034b9  xor     esi, esi
0x1800034bb  jmp     short loc_1800034F9
0x1800034bd  lea     rax, [rbp+20B0h+String1]
0x1800034c1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800034c5  inc     rdi
0x1800034c8  cmp     [rax+rdi*2], si
0x1800034cc  jnz     short loc_1800034C5
0x1800034ce  mov     rcx, [r14]; hKey
0x1800034d1  lea     eax, ds:2[rdi*2]
0x1800034d8  mov     [rsp+21B0h+cbData], eax; cbData
0x1800034dc  mov     r9d, 1; dwType
0x1800034e2  lea     rax, [rbp+20B0h+String1]
0x1800034e6  xor     r8d, r8d; Reserved
0x1800034e9  mov     rdx, r15; lpValueName
0x1800034ec  mov     [rsp+21B0h+lpData], rax; lpData
0x1800034f1  call    cs:__imp_RegSetValueExW
0x1800034f7  mov     ebx, eax
0x1800034f9  test    ebx, ebx
0x1800034fb  jz      short loc_180003506
0x1800034fd  mov     ecx, ebx; unsigned int
0x1800034ff  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180003504  jmp     short loc_18000351A
0x180003506  mov     rdx, r13; unsigned __int16 *
0x180003509  mov     rcx, r12; this
0x18000350c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003511  test    eax, eax
0x180003513  mov     ecx, esi
0x180003515  cmovs   ecx, eax
0x180003518  mov     eax, ecx
0x18000351a  mov     rcx, [rbp+20B0h+var_50]
0x180003521  xor     rcx, rsp; StackCookie
0x180003524  call    __security_check_cookie
0x180003529  add     rsp, 2178h
0x180003530  pop     r15
0x180003532  pop     r14
0x180003534  pop     r13
0x180003536  pop     r12
0x180003538  pop     rdi
0x180003539  pop     rsi
0x18000353a  pop     rbx
0x18000353b  pop     rbp
0x18000353c  retn
```
