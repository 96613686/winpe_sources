# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18002f5ac`
- end: `0x18002f99f`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1011`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180030acc`

## callees

- `0x180019a20`
- `0x18001a5bc`
- `0x18002ef64`
- `0x18002f054`
- `0x18002f0f8`
- `0x18002f5ac`
- `0x18002f9a8`
- `0x18002fb80`
- `0x18002fd04`
- `0x180030264`
- `0x180031188`
- `0x180031288`
- `0x1800600d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f7da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f903`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f953`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f7da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f903`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f953`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002f715`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002f730`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002f715`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002f730`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f626`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f626`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002f794`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002f794`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r12
  HKEY *v5; // r15
  ATL::CRegParser *v6; // r13
  __int64 result; // rax
  unsigned int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  WCHAR *i; // rsi
  const WCHAR *v15; // rax
  LSTATUS v16; // edi
  HRESULT v17; // edi
  __int64 v18; // rdi
  DWORD cbData; // esi
  size_t v20; // r14
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  int j; // r10d
  unsigned __int8 v24; // al
  int v25; // r10d
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-2198h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-2190h] BYREF
  ATL::CRegParser *v32; // [rsp+40h] [rbp-2188h] BYREF
  struct ATL::CRegKey *v33; // [rsp+48h] [rbp-2180h]
  const unsigned __int16 *v34; // [rsp+50h] [rbp-2178h]
  size_t v35; // [rsp+60h] [rbp-2168h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-2160h]
  BYTE *lpData; // [rsp+70h] [rbp-2158h] BYREF
  _BYTE v38[264]; // [rsp+78h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+180h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v32 = this;
  v33 = (struct ATL::CRegKey *)a2;
  v34 = a3;
  v36 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v6);
    result = ATL::CRegParser::NextToken(v6, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v28 = -1;
        do
          ++v28;
        while ( String1[v28] );
        v16 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v28 + 2);
        goto LABEL_46;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v32 = 0;
          v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v17 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
            return (unsigned int)v17;
          }
          *(_DWORD *)Data = pulOut;
          v16 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_48:
            Token = ATL::CRegParser::NextToken(v6, v36);
            if ( Token < 0 )
              return (unsigned int)Token;
            return v8;
          }
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
              v13 = v38;
              lpData = v38;
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
            v6 = v32;
            v5 = (HKEY *)v33;
            v4 = v34;
          }
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v15 = CharNextW(i);
              if ( *i == 92 && *v15 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v15);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, (const unsigned __int16 *)lpData);
          }
          else
          {
            v16 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_46:
        if ( v16 )
          return ATL::AtlHresultFromWin32(v16);
        goto LABEL_48;
      }
      v18 = -1;
      do
        ++v18;
      while ( String1[v18] );
      *(_DWORD *)Data = v18;
      if ( (v18 & 1) == 0 )
      {
        cbData = (int)v18 / 2;
        lpData = 0;
        v20 = (int)v18 / 2;
        v35 = v20;
        try
        {
          v21 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v21 <= 0x100 )
          {
            v22 = v38;
            lpData = v38;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v21);
            v22 = lpData;
          }
        }
        catch ( ... )
        {
          v8 = 0;
          LODWORD(v18) = *(_DWORD *)Data;
          v22 = lpData;
          v20 = v35;
          v6 = v32;
          v5 = (HKEY *)v33;
          v4 = v34;
          cbData = v35;
        }
        if ( v22 )
        {
          memset_0(v22, 0, v20);
          for ( j = 0; j < (int)v18; j = v25 + 1 )
          {
            v24 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v27 + v26) |= v24 << (4 - 4 * (v25 & 1));
          }
          v16 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_46;
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
0x18002f5ac  push    rbx
0x18002f5ae  push    rsi
0x18002f5af  push    rdi
0x18002f5b0  push    r12
0x18002f5b2  push    r13
0x18002f5b4  push    r14
0x18002f5b6  push    r15
0x18002f5b8  mov     eax, 2190h
0x18002f5bd  call    _alloca_probe
0x18002f5c2  sub     rsp, rax
0x18002f5c5  mov     rax, cs:__security_cookie
0x18002f5cc  xor     rax, rsp
0x18002f5cf  mov     [rsp+21C8h+var_48], rax
0x18002f5d7  mov     r12, r8
0x18002f5da  mov     r15, rdx
0x18002f5dd  mov     r13, rcx
0x18002f5e0  mov     [rsp+21C8h+var_2188], rcx
0x18002f5e5  mov     [rsp+21C8h+var_2180], rdx
0x18002f5ea  mov     [rsp+21C8h+var_2178], r8
0x18002f5ef  mov     [rsp+21C8h+var_2160], r9
0x18002f5f4  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x18002f5fc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f601  xor     ebx, ebx
0x18002f603  test    eax, eax
0x18002f605  js      loc_18002F97C
0x18002f60b  mov     edi, ebx
0x18002f60d  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18002f614  movsxd  rsi, edi
0x18002f617  add     rsi, rsi
0x18002f61a  mov     rdx, [r14+rsi*8]; lpString2
0x18002f61e  lea     rcx, [rsp+21C8h+String1]; lpString1
0x18002f626  call    cs:__imp_lstrcmpiW
0x18002f62c  test    eax, eax
0x18002f62e  jz      short loc_18002F641
0x18002f630  inc     edi
0x18002f632  cmp     edi, 4
0x18002f635  jb      short loc_18002F614
0x18002f637  mov     eax, 80020009h
0x18002f63c  jmp     loc_18002F97C
0x18002f641  movzx   edi, word ptr [r14+rsi*8+8]
0x18002f647  mov     rcx, r13; this
0x18002f64a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18002f64f  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x18002f657  mov     rcx, r13; this
0x18002f65a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f65f  test    eax, eax
0x18002f661  js      loc_18002F97C
0x18002f667  cmp     di, 8
0x18002f66b  jz      loc_18002F917
0x18002f671  cmp     di, 11h
0x18002f675  jz      loc_18002F7F1
0x18002f67b  cmp     di, 13h
0x18002f67f  jz      loc_18002F779
0x18002f685  mov     eax, 4008h
0x18002f68a  cmp     di, ax
0x18002f68d  jnz     loc_18002F968
0x18002f693  lea     rax, [rsp+21C8h+String1]
0x18002f69b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002f69f  inc     rdi
0x18002f6a2  cmp     [rax+rdi*2], bx
0x18002f6a6  jnz     short loc_18002F69F
0x18002f6a8  add     edi, 2
0x18002f6ab  mov     [rsp+21C8h+var_2158], rbx
0x18002f6b0  movsxd  rcx, edi
0x18002f6b3  mov     edx, 2
0x18002f6b8  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002f6bd  cmp     rax, 100h
0x18002f6c3  jbe     short loc_18002F6D9
0x18002f6c5  mov     rdx, rax
0x18002f6c8  lea     rcx, [rsp+21C8h+var_2158]
0x18002f6cd  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002f6d2  mov     rdi, [rsp+21C8h+var_2158]
0x18002f6d7  jmp     short loc_18002F6E3
0x18002f6d9  lea     rdi, [rsp+21C8h+var_2150]
0x18002f6de  mov     [rsp+21C8h+var_2158], rdi
0x18002f6e3  jmp     short loc_18002F6FB
0x18002f6e5  xor     ebx, ebx
0x18002f6e7  mov     rdi, [rsp+21C8h+var_2158]
0x18002f6ec  mov     r13, [rsp+21C8h+var_2188]
0x18002f6f1  mov     r15, [rsp+21C8h+var_2180]
0x18002f6f6  mov     r12, [rsp+21C8h+var_2178]
0x18002f6fb  test    rdi, rdi
0x18002f6fe  jz      short loc_18002F765
0x18002f700  lea     rsi, [rsp+21C8h+String1]
0x18002f708  cmp     [rsp+21C8h+String1], bx
0x18002f710  jz      short loc_18002F74B
0x18002f712  mov     rcx, rsi; lpsz
0x18002f715  call    cs:__imp_CharNextW
0x18002f71b  movzx   ecx, word ptr [rsi]
0x18002f71e  cmp     cx, 5Ch ; '\'
0x18002f722  jnz     short loc_18002F73B
0x18002f724  cmp     word ptr [rax], 30h ; '0'
0x18002f728  jnz     short loc_18002F73B
0x18002f72a  mov     [rdi], bx
0x18002f72d  mov     rcx, rax; lpsz
0x18002f730  call    cs:__imp_CharNextW
0x18002f736  mov     rsi, rax
0x18002f739  jmp     short loc_18002F742
0x18002f73b  mov     [rdi], cx
0x18002f73e  add     rsi, 2
0x18002f742  add     rdi, 2
0x18002f746  cmp     [rsi], bx
0x18002f749  jnz     short loc_18002F712
0x18002f74b  mov     dword ptr [rdi], 0
0x18002f751  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x18002f756  mov     rdx, r12; unsigned __int16 *
0x18002f759  mov     rcx, r15; this
0x18002f75c  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x18002f761  mov     edi, eax
0x18002f763  jmp     short loc_18002F76A
0x18002f765  mov     edi, 0Eh
0x18002f76a  lea     rcx, [rsp+21C8h+var_2158]
0x18002f76f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002f774  jmp     loc_18002F95B
0x18002f779  mov     [rsp+21C8h+pulOut], ebx
0x18002f77d  mov     [rsp+21C8h+var_2188], rbx
0x18002f782  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x18002f787  xor     r8d, r8d; dwFlags
0x18002f78a  xor     edx, edx; lcid
0x18002f78c  lea     rcx, [rsp+21C8h+String1]; strIn
0x18002f794  call    cs:__imp_VarUI4FromStr
0x18002f79a  mov     edi, eax
0x18002f79c  test    eax, eax
0x18002f79e  jns     short loc_18002F7B1
0x18002f7a0  lea     rcx, [rsp+21C8h+var_2188]
0x18002f7a5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002f7aa  mov     eax, edi
0x18002f7ac  jmp     loc_18002F97C
0x18002f7b1  mov     eax, [rsp+21C8h+pulOut]
0x18002f7b5  mov     dword ptr [rsp+21C8h+Data], eax
0x18002f7b9  mov     [rsp+21C8h+cbData], 4; cbData
0x18002f7c1  lea     rax, [rsp+21C8h+Data]
0x18002f7c6  mov     [rsp+21C8h+lpData], rax; lpData
0x18002f7cb  mov     r9d, 4; dwType
0x18002f7d1  xor     r8d, r8d; Reserved
0x18002f7d4  mov     rdx, r12; lpValueName
0x18002f7d7  mov     rcx, [r15]; hKey
0x18002f7da  call    cs:__imp_RegSetValueExW
0x18002f7e0  mov     edi, eax
0x18002f7e2  lea     rcx, [rsp+21C8h+var_2188]
0x18002f7e7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002f7ec  jmp     loc_18002F95B
0x18002f7f1  lea     rax, [rsp+21C8h+String1]
0x18002f7f9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002f7fd  inc     rdi
0x18002f800  cmp     [rax+rdi*2], bx
0x18002f804  jnz     short loc_18002F7FD
0x18002f806  mov     dword ptr [rsp+21C8h+Data], edi
0x18002f80a  test    dil, 1
0x18002f80e  jz      short loc_18002F81A
0x18002f810  mov     eax, 80004005h
0x18002f815  jmp     loc_18002F97C
0x18002f81a  mov     eax, edi
0x18002f81c  cdq
0x18002f81d  sub     eax, edx
0x18002f81f  sar     eax, 1
0x18002f821  movsxd  rsi, eax
0x18002f824  mov     [rsp+21C8h+var_2158], rbx
0x18002f829  mov     r14, rsi
0x18002f82c  mov     [rsp+21C8h+var_2168], rsi
0x18002f831  mov     edx, 1
0x18002f836  mov     rcx, rsi
0x18002f839  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002f83e  cmp     rax, 100h
0x18002f844  jbe     short loc_18002F85A
0x18002f846  mov     rdx, rax
0x18002f849  lea     rcx, [rsp+21C8h+var_2158]
0x18002f84e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002f853  mov     rcx, [rsp+21C8h+var_2158]
0x18002f858  jmp     short loc_18002F864
0x18002f85a  lea     rcx, [rsp+21C8h+var_2150]
0x18002f85f  mov     [rsp+21C8h+var_2158], rcx
0x18002f864  jmp     short loc_18002F888
0x18002f866  xor     ebx, ebx
0x18002f868  mov     edi, dword ptr [rsp+21C8h+Data]
0x18002f86c  mov     rcx, [rsp+21C8h+var_2158]; void *
0x18002f871  mov     r14, [rsp+21C8h+var_2168]
0x18002f876  mov     r13, [rsp+21C8h+var_2188]
0x18002f87b  mov     r15, [rsp+21C8h+var_2180]
0x18002f880  mov     r12, [rsp+21C8h+var_2178]
0x18002f885  mov     esi, r14d
0x18002f888  test    rcx, rcx
0x18002f88b  jnz     short loc_18002F89C
0x18002f88d  lea     rcx, [rsp+21C8h+var_2158]
0x18002f892  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002f897  jmp     loc_18002F810
0x18002f89c  mov     r8, r14; Size
0x18002f89f  xor     edx, edx; Val
0x18002f8a1  call    memset_0
0x18002f8a6  mov     r10d, ebx
0x18002f8a9  test    edi, edi
0x18002f8ab  jle     short loc_18002F8E6
0x18002f8ad  mov     r9d, r10d
0x18002f8b0  shr     r9, 1
0x18002f8b3  mov     r8, [rsp+21C8h+var_2158]
0x18002f8b8  mov     ecx, r10d
0x18002f8bb  movzx   ecx, [rsp+rcx*2+21C8h+String1]; unsigned __int16
0x18002f8c3  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18002f8c8  mov     edx, r10d
0x18002f8cb  and     edx, 1
0x18002f8ce  shl     edx, 2
0x18002f8d1  mov     ecx, 4
0x18002f8d6  sub     ecx, edx
0x18002f8d8  shl     al, cl
0x18002f8da  or      [r9+r8], al
0x18002f8de  inc     r10d
0x18002f8e1  cmp     r10d, edi
0x18002f8e4  jl      short loc_18002F8AD
0x18002f8e6  mov     rax, [rsp+21C8h+var_2158]
0x18002f8eb  mov     [rsp+21C8h+cbData], esi; cbData
0x18002f8ef  mov     [rsp+21C8h+lpData], rax; lpData
0x18002f8f4  mov     r9d, 3; dwType
0x18002f8fa  xor     r8d, r8d; Reserved
0x18002f8fd  mov     rdx, r12; lpValueName
0x18002f900  mov     rcx, [r15]; hKey
0x18002f903  call    cs:__imp_RegSetValueExW
0x18002f909  mov     edi, eax
0x18002f90b  lea     rcx, [rsp+21C8h+var_2158]
0x18002f910  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002f915  jmp     short loc_18002F95B
0x18002f917  lea     rax, [rsp+21C8h+String1]
0x18002f91f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002f923  inc     rdi
0x18002f926  cmp     [rax+rdi*2], bx
0x18002f92a  jnz     short loc_18002F923
0x18002f92c  lea     eax, ds:2[rdi*2]
0x18002f933  mov     [rsp+21C8h+cbData], eax; cbData
0x18002f937  lea     rax, [rsp+21C8h+String1]
0x18002f93f  mov     [rsp+21C8h+lpData], rax; lpData
0x18002f944  mov     r9d, 1; dwType
0x18002f94a  xor     r8d, r8d; Reserved
0x18002f94d  mov     rdx, r12; lpValueName
0x18002f950  mov     rcx, [r15]; hKey
0x18002f953  call    cs:__imp_RegSetValueExW
0x18002f959  mov     edi, eax
0x18002f95b  test    edi, edi
0x18002f95d  jz      short loc_18002F968
0x18002f95f  mov     ecx, edi; unsigned int
0x18002f961  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002f966  jmp     short loc_18002F97C
0x18002f968  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x18002f96d  mov     rcx, r13; this
0x18002f970  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f975  test    eax, eax
0x18002f977  cmovs   ebx, eax
0x18002f97a  mov     eax, ebx
0x18002f97c  mov     rcx, [rsp+21C8h+var_48]
0x18002f984  xor     rcx, rsp; StackCookie
0x18002f987  call    __security_check_cookie
0x18002f98c  add     rsp, 2190h
0x18002f993  pop     r15
0x18002f995  pop     r14
0x18002f997  pop     r13
0x18002f999  pop     r12
0x18002f99b  pop     rdi
0x18002f99c  pop     rsi
0x18002f99d  pop     rbx
0x18002f99e  retn
```
