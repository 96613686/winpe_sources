# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18003e370`
- end: `0x18003e763`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1011`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18003f67c`

## callees

- `0x1800358c0`
- `0x18003633c`
- `0x18003de64`
- `0x18003dea8`
- `0x18003defc`
- `0x18003e370`
- `0x18003e76c`
- `0x18003e944`
- `0x18003e9cc`
- `0x18003ee34`
- `0x18003fc70`
- `0x18003fd70`
- `0x18006ad80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e59e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e6c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e717`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e59e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e6c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e717`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003e4d9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003e4f4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003e4d9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18003e4f4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003e3ea`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003e3ea`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18003e558`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18003e558`

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
0x18003e370  push    rbx
0x18003e372  push    rsi
0x18003e373  push    rdi
0x18003e374  push    r12
0x18003e376  push    r13
0x18003e378  push    r14
0x18003e37a  push    r15
0x18003e37c  mov     eax, 2190h
0x18003e381  call    _alloca_probe
0x18003e386  sub     rsp, rax
0x18003e389  mov     rax, cs:__security_cookie
0x18003e390  xor     rax, rsp
0x18003e393  mov     [rsp+21C8h+var_48], rax
0x18003e39b  mov     r12, r8
0x18003e39e  mov     r15, rdx
0x18003e3a1  mov     r13, rcx
0x18003e3a4  mov     [rsp+21C8h+var_2188], rcx
0x18003e3a9  mov     [rsp+21C8h+var_2180], rdx
0x18003e3ae  mov     [rsp+21C8h+var_2178], r8
0x18003e3b3  mov     [rsp+21C8h+var_2160], r9
0x18003e3b8  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x18003e3c0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003e3c5  xor     ebx, ebx
0x18003e3c7  test    eax, eax
0x18003e3c9  js      loc_18003E740
0x18003e3cf  mov     edi, ebx
0x18003e3d1  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18003e3d8  movsxd  rsi, edi
0x18003e3db  add     rsi, rsi
0x18003e3de  mov     rdx, [r14+rsi*8]; lpString2
0x18003e3e2  lea     rcx, [rsp+21C8h+String1]; lpString1
0x18003e3ea  call    cs:__imp_lstrcmpiW
0x18003e3f0  test    eax, eax
0x18003e3f2  jz      short loc_18003E405
0x18003e3f4  inc     edi
0x18003e3f6  cmp     edi, 4
0x18003e3f9  jb      short loc_18003E3D8
0x18003e3fb  mov     eax, 80020009h
0x18003e400  jmp     loc_18003E740
0x18003e405  movzx   edi, word ptr [r14+rsi*8+8]
0x18003e40b  mov     rcx, r13; this
0x18003e40e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18003e413  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x18003e41b  mov     rcx, r13; this
0x18003e41e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003e423  test    eax, eax
0x18003e425  js      loc_18003E740
0x18003e42b  cmp     di, 8
0x18003e42f  jz      loc_18003E6DB
0x18003e435  cmp     di, 11h
0x18003e439  jz      loc_18003E5B5
0x18003e43f  cmp     di, 13h
0x18003e443  jz      loc_18003E53D
0x18003e449  mov     eax, 4008h
0x18003e44e  cmp     di, ax
0x18003e451  jnz     loc_18003E72C
0x18003e457  lea     rax, [rsp+21C8h+String1]
0x18003e45f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e463  inc     rdi
0x18003e466  cmp     [rax+rdi*2], bx
0x18003e46a  jnz     short loc_18003E463
0x18003e46c  add     edi, 2
0x18003e46f  mov     [rsp+21C8h+var_2158], rbx
0x18003e474  movsxd  rcx, edi
0x18003e477  mov     edx, 2
0x18003e47c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003e481  cmp     rax, 100h
0x18003e487  jbe     short loc_18003E49D
0x18003e489  mov     rdx, rax
0x18003e48c  lea     rcx, [rsp+21C8h+var_2158]
0x18003e491  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003e496  mov     rdi, [rsp+21C8h+var_2158]
0x18003e49b  jmp     short loc_18003E4A7
0x18003e49d  lea     rdi, [rsp+21C8h+var_2150]
0x18003e4a2  mov     [rsp+21C8h+var_2158], rdi
0x18003e4a7  jmp     short loc_18003E4BF
0x18003e4a9  xor     ebx, ebx
0x18003e4ab  mov     rdi, [rsp+21C8h+var_2158]
0x18003e4b0  mov     r13, [rsp+21C8h+var_2188]
0x18003e4b5  mov     r15, [rsp+21C8h+var_2180]
0x18003e4ba  mov     r12, [rsp+21C8h+var_2178]
0x18003e4bf  test    rdi, rdi
0x18003e4c2  jz      short loc_18003E529
0x18003e4c4  lea     rsi, [rsp+21C8h+String1]
0x18003e4cc  cmp     [rsp+21C8h+String1], bx
0x18003e4d4  jz      short loc_18003E50F
0x18003e4d6  mov     rcx, rsi; lpsz
0x18003e4d9  call    cs:__imp_CharNextW
0x18003e4df  movzx   ecx, word ptr [rsi]
0x18003e4e2  cmp     cx, 5Ch ; '\'
0x18003e4e6  jnz     short loc_18003E4FF
0x18003e4e8  cmp     word ptr [rax], 30h ; '0'
0x18003e4ec  jnz     short loc_18003E4FF
0x18003e4ee  mov     [rdi], bx
0x18003e4f1  mov     rcx, rax; lpsz
0x18003e4f4  call    cs:__imp_CharNextW
0x18003e4fa  mov     rsi, rax
0x18003e4fd  jmp     short loc_18003E506
0x18003e4ff  mov     [rdi], cx
0x18003e502  add     rsi, 2
0x18003e506  add     rdi, 2
0x18003e50a  cmp     [rsi], bx
0x18003e50d  jnz     short loc_18003E4D6
0x18003e50f  mov     dword ptr [rdi], 0
0x18003e515  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x18003e51a  mov     rdx, r12; unsigned __int16 *
0x18003e51d  mov     rcx, r15; this
0x18003e520  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x18003e525  mov     edi, eax
0x18003e527  jmp     short loc_18003E52E
0x18003e529  mov     edi, 0Eh
0x18003e52e  lea     rcx, [rsp+21C8h+var_2158]
0x18003e533  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003e538  jmp     loc_18003E71F
0x18003e53d  mov     [rsp+21C8h+pulOut], ebx
0x18003e541  mov     [rsp+21C8h+var_2188], rbx
0x18003e546  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x18003e54b  xor     r8d, r8d; dwFlags
0x18003e54e  xor     edx, edx; lcid
0x18003e550  lea     rcx, [rsp+21C8h+String1]; strIn
0x18003e558  call    cs:__imp_VarUI4FromStr
0x18003e55e  mov     edi, eax
0x18003e560  test    eax, eax
0x18003e562  jns     short loc_18003E575
0x18003e564  lea     rcx, [rsp+21C8h+var_2188]
0x18003e569  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003e56e  mov     eax, edi
0x18003e570  jmp     loc_18003E740
0x18003e575  mov     eax, [rsp+21C8h+pulOut]
0x18003e579  mov     dword ptr [rsp+21C8h+Data], eax
0x18003e57d  mov     [rsp+21C8h+cbData], 4; cbData
0x18003e585  lea     rax, [rsp+21C8h+Data]
0x18003e58a  mov     [rsp+21C8h+lpData], rax; lpData
0x18003e58f  mov     r9d, 4; dwType
0x18003e595  xor     r8d, r8d; Reserved
0x18003e598  mov     rdx, r12; lpValueName
0x18003e59b  mov     rcx, [r15]; hKey
0x18003e59e  call    cs:__imp_RegSetValueExW
0x18003e5a4  mov     edi, eax
0x18003e5a6  lea     rcx, [rsp+21C8h+var_2188]
0x18003e5ab  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003e5b0  jmp     loc_18003E71F
0x18003e5b5  lea     rax, [rsp+21C8h+String1]
0x18003e5bd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e5c1  inc     rdi
0x18003e5c4  cmp     [rax+rdi*2], bx
0x18003e5c8  jnz     short loc_18003E5C1
0x18003e5ca  mov     dword ptr [rsp+21C8h+Data], edi
0x18003e5ce  test    dil, 1
0x18003e5d2  jz      short loc_18003E5DE
0x18003e5d4  mov     eax, 80004005h
0x18003e5d9  jmp     loc_18003E740
0x18003e5de  mov     eax, edi
0x18003e5e0  cdq
0x18003e5e1  sub     eax, edx
0x18003e5e3  sar     eax, 1
0x18003e5e5  movsxd  rsi, eax
0x18003e5e8  mov     [rsp+21C8h+var_2158], rbx
0x18003e5ed  mov     r14, rsi
0x18003e5f0  mov     [rsp+21C8h+var_2168], rsi
0x18003e5f5  mov     edx, 1
0x18003e5fa  mov     rcx, rsi
0x18003e5fd  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003e602  cmp     rax, 100h
0x18003e608  jbe     short loc_18003E61E
0x18003e60a  mov     rdx, rax
0x18003e60d  lea     rcx, [rsp+21C8h+var_2158]
0x18003e612  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003e617  mov     rcx, [rsp+21C8h+var_2158]
0x18003e61c  jmp     short loc_18003E628
0x18003e61e  lea     rcx, [rsp+21C8h+var_2150]
0x18003e623  mov     [rsp+21C8h+var_2158], rcx
0x18003e628  jmp     short loc_18003E64C
0x18003e62a  xor     ebx, ebx
0x18003e62c  mov     edi, dword ptr [rsp+21C8h+Data]
0x18003e630  mov     rcx, [rsp+21C8h+var_2158]; void *
0x18003e635  mov     r14, [rsp+21C8h+var_2168]
0x18003e63a  mov     r13, [rsp+21C8h+var_2188]
0x18003e63f  mov     r15, [rsp+21C8h+var_2180]
0x18003e644  mov     r12, [rsp+21C8h+var_2178]
0x18003e649  mov     esi, r14d
0x18003e64c  test    rcx, rcx
0x18003e64f  jnz     short loc_18003E660
0x18003e651  lea     rcx, [rsp+21C8h+var_2158]
0x18003e656  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003e65b  jmp     loc_18003E5D4
0x18003e660  mov     r8, r14; Size
0x18003e663  xor     edx, edx; Val
0x18003e665  call    memset_0
0x18003e66a  mov     r10d, ebx
0x18003e66d  test    edi, edi
0x18003e66f  jle     short loc_18003E6AA
0x18003e671  mov     r9d, r10d
0x18003e674  shr     r9, 1
0x18003e677  mov     r8, [rsp+21C8h+var_2158]
0x18003e67c  mov     ecx, r10d
0x18003e67f  movzx   ecx, [rsp+rcx*2+21C8h+String1]; unsigned __int16
0x18003e687  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18003e68c  mov     edx, r10d
0x18003e68f  and     edx, 1
0x18003e692  shl     edx, 2
0x18003e695  mov     ecx, 4
0x18003e69a  sub     ecx, edx
0x18003e69c  shl     al, cl
0x18003e69e  or      [r9+r8], al
0x18003e6a2  inc     r10d
0x18003e6a5  cmp     r10d, edi
0x18003e6a8  jl      short loc_18003E671
0x18003e6aa  mov     rax, [rsp+21C8h+var_2158]
0x18003e6af  mov     [rsp+21C8h+cbData], esi; cbData
0x18003e6b3  mov     [rsp+21C8h+lpData], rax; lpData
0x18003e6b8  mov     r9d, 3; dwType
0x18003e6be  xor     r8d, r8d; Reserved
0x18003e6c1  mov     rdx, r12; lpValueName
0x18003e6c4  mov     rcx, [r15]; hKey
0x18003e6c7  call    cs:__imp_RegSetValueExW
0x18003e6cd  mov     edi, eax
0x18003e6cf  lea     rcx, [rsp+21C8h+var_2158]
0x18003e6d4  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003e6d9  jmp     short loc_18003E71F
0x18003e6db  lea     rax, [rsp+21C8h+String1]
0x18003e6e3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e6e7  inc     rdi
0x18003e6ea  cmp     [rax+rdi*2], bx
0x18003e6ee  jnz     short loc_18003E6E7
0x18003e6f0  lea     eax, ds:2[rdi*2]
0x18003e6f7  mov     [rsp+21C8h+cbData], eax; cbData
0x18003e6fb  lea     rax, [rsp+21C8h+String1]
0x18003e703  mov     [rsp+21C8h+lpData], rax; lpData
0x18003e708  mov     r9d, 1; dwType
0x18003e70e  xor     r8d, r8d; Reserved
0x18003e711  mov     rdx, r12; lpValueName
0x18003e714  mov     rcx, [r15]; hKey
0x18003e717  call    cs:__imp_RegSetValueExW
0x18003e71d  mov     edi, eax
0x18003e71f  test    edi, edi
0x18003e721  jz      short loc_18003E72C
0x18003e723  mov     ecx, edi; unsigned int
0x18003e725  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18003e72a  jmp     short loc_18003E740
0x18003e72c  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x18003e731  mov     rcx, r13; this
0x18003e734  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003e739  test    eax, eax
0x18003e73b  cmovs   ebx, eax
0x18003e73e  mov     eax, ebx
0x18003e740  mov     rcx, [rsp+21C8h+var_48]
0x18003e748  xor     rcx, rsp; StackCookie
0x18003e74b  call    __security_check_cookie
0x18003e750  add     rsp, 2190h
0x18003e757  pop     r15
0x18003e759  pop     r14
0x18003e75b  pop     r13
0x18003e75d  pop     r12
0x18003e75f  pop     rdi
0x18003e760  pop     rsi
0x18003e761  pop     rbx
0x18003e762  retn
```
