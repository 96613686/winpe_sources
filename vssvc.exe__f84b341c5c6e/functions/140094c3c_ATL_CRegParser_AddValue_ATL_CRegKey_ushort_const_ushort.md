# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x140094c3c`
- end: `0x14009502f`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1011`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140097914`

## callees

- `0x140091560`
- `0x1400921dc`
- `0x140093424`
- `0x140093e80`
- `0x140094018`
- `0x140094c3c`
- `0x140095038`
- `0x140095210`
- `0x1400952a0`
- `0x140096dd8`
- `0x14009861c`
- `0x14009871c`
- `0x1400da290`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140094da5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140094dc0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140094da5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140094dc0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140094e6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140094f93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140094fe3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140094e6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140094f93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140094fe3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140094cb6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140094cb6`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140094e24`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140094e24`

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
0x140094c3c  push    rbx
0x140094c3e  push    rsi
0x140094c3f  push    rdi
0x140094c40  push    r12
0x140094c42  push    r13
0x140094c44  push    r14
0x140094c46  push    r15
0x140094c48  mov     eax, 2190h
0x140094c4d  call    _alloca_probe
0x140094c52  sub     rsp, rax
0x140094c55  mov     rax, cs:__security_cookie
0x140094c5c  xor     rax, rsp
0x140094c5f  mov     [rsp+21C8h+var_48], rax
0x140094c67  mov     r12, r8
0x140094c6a  mov     r15, rdx
0x140094c6d  mov     r13, rcx
0x140094c70  mov     [rsp+21C8h+var_2188], rcx
0x140094c75  mov     [rsp+21C8h+var_2180], rdx
0x140094c7a  mov     [rsp+21C8h+var_2178], r8
0x140094c7f  mov     [rsp+21C8h+var_2160], r9
0x140094c84  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x140094c8c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140094c91  xor     ebx, ebx
0x140094c93  test    eax, eax
0x140094c95  js      loc_14009500C
0x140094c9b  mov     edi, ebx
0x140094c9d  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140094ca4  movsxd  rsi, edi
0x140094ca7  add     rsi, rsi
0x140094caa  mov     rdx, [r14+rsi*8]; lpString2
0x140094cae  lea     rcx, [rsp+21C8h+String1]; lpString1
0x140094cb6  call    cs:__imp_lstrcmpiW
0x140094cbc  test    eax, eax
0x140094cbe  jz      short loc_140094CD1
0x140094cc0  inc     edi
0x140094cc2  cmp     edi, 4
0x140094cc5  jb      short loc_140094CA4
0x140094cc7  mov     eax, 80020009h
0x140094ccc  jmp     loc_14009500C
0x140094cd1  movzx   edi, word ptr [r14+rsi*8+8]
0x140094cd7  mov     rcx, r13; this
0x140094cda  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140094cdf  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x140094ce7  mov     rcx, r13; this
0x140094cea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140094cef  test    eax, eax
0x140094cf1  js      loc_14009500C
0x140094cf7  cmp     di, 8
0x140094cfb  jz      loc_140094FA7
0x140094d01  cmp     di, 11h
0x140094d05  jz      loc_140094E81
0x140094d0b  cmp     di, 13h
0x140094d0f  jz      loc_140094E09
0x140094d15  mov     eax, 4008h
0x140094d1a  cmp     di, ax
0x140094d1d  jnz     loc_140094FF8
0x140094d23  lea     rax, [rsp+21C8h+String1]
0x140094d2b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140094d2f  inc     rdi
0x140094d32  cmp     [rax+rdi*2], bx
0x140094d36  jnz     short loc_140094D2F
0x140094d38  add     edi, 2
0x140094d3b  mov     [rsp+21C8h+var_2158], rbx
0x140094d40  movsxd  rcx, edi
0x140094d43  mov     edx, 2
0x140094d48  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140094d4d  cmp     rax, 100h
0x140094d53  jbe     short loc_140094D69
0x140094d55  mov     rdx, rax
0x140094d58  lea     rcx, [rsp+21C8h+var_2158]
0x140094d5d  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140094d62  mov     rdi, [rsp+21C8h+var_2158]
0x140094d67  jmp     short loc_140094D73
0x140094d69  lea     rdi, [rsp+21C8h+var_2150]
0x140094d6e  mov     [rsp+21C8h+var_2158], rdi
0x140094d73  jmp     short loc_140094D8B
0x140094d75  xor     ebx, ebx
0x140094d77  mov     rdi, [rsp+21C8h+var_2158]
0x140094d7c  mov     r13, [rsp+21C8h+var_2188]
0x140094d81  mov     r15, [rsp+21C8h+var_2180]
0x140094d86  mov     r12, [rsp+21C8h+var_2178]
0x140094d8b  test    rdi, rdi
0x140094d8e  jz      short loc_140094DF5
0x140094d90  lea     rsi, [rsp+21C8h+String1]
0x140094d98  cmp     [rsp+21C8h+String1], bx
0x140094da0  jz      short loc_140094DDB
0x140094da2  mov     rcx, rsi; lpsz
0x140094da5  call    cs:__imp_CharNextW
0x140094dab  movzx   ecx, word ptr [rsi]
0x140094dae  cmp     cx, 5Ch ; '\'
0x140094db2  jnz     short loc_140094DCB
0x140094db4  cmp     word ptr [rax], 30h ; '0'
0x140094db8  jnz     short loc_140094DCB
0x140094dba  mov     [rdi], bx
0x140094dbd  mov     rcx, rax; lpsz
0x140094dc0  call    cs:__imp_CharNextW
0x140094dc6  mov     rsi, rax
0x140094dc9  jmp     short loc_140094DD2
0x140094dcb  mov     [rdi], cx
0x140094dce  add     rsi, 2
0x140094dd2  add     rdi, 2
0x140094dd6  cmp     [rsi], bx
0x140094dd9  jnz     short loc_140094DA2
0x140094ddb  mov     dword ptr [rdi], 0
0x140094de1  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x140094de6  mov     rdx, r12; unsigned __int16 *
0x140094de9  mov     rcx, r15; this
0x140094dec  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x140094df1  mov     edi, eax
0x140094df3  jmp     short loc_140094DFA
0x140094df5  mov     edi, 0Eh
0x140094dfa  lea     rcx, [rsp+21C8h+var_2158]
0x140094dff  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140094e04  jmp     loc_140094FEB
0x140094e09  mov     [rsp+21C8h+pulOut], ebx
0x140094e0d  mov     [rsp+21C8h+var_2188], rbx
0x140094e12  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x140094e17  xor     r8d, r8d; dwFlags
0x140094e1a  xor     edx, edx; lcid
0x140094e1c  lea     rcx, [rsp+21C8h+String1]; strIn
0x140094e24  call    cs:__imp_VarUI4FromStr
0x140094e2a  mov     edi, eax
0x140094e2c  test    eax, eax
0x140094e2e  jns     short loc_140094E41
0x140094e30  lea     rcx, [rsp+21C8h+var_2188]
0x140094e35  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140094e3a  mov     eax, edi
0x140094e3c  jmp     loc_14009500C
0x140094e41  mov     eax, [rsp+21C8h+pulOut]
0x140094e45  mov     dword ptr [rsp+21C8h+Data], eax
0x140094e49  mov     [rsp+21C8h+cbData], 4; cbData
0x140094e51  lea     rax, [rsp+21C8h+Data]
0x140094e56  mov     [rsp+21C8h+lpData], rax; lpData
0x140094e5b  mov     r9d, 4; dwType
0x140094e61  xor     r8d, r8d; Reserved
0x140094e64  mov     rdx, r12; lpValueName
0x140094e67  mov     rcx, [r15]; hKey
0x140094e6a  call    cs:__imp_RegSetValueExW
0x140094e70  mov     edi, eax
0x140094e72  lea     rcx, [rsp+21C8h+var_2188]
0x140094e77  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140094e7c  jmp     loc_140094FEB
0x140094e81  lea     rax, [rsp+21C8h+String1]
0x140094e89  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140094e8d  inc     rdi
0x140094e90  cmp     [rax+rdi*2], bx
0x140094e94  jnz     short loc_140094E8D
0x140094e96  mov     dword ptr [rsp+21C8h+Data], edi
0x140094e9a  test    dil, 1
0x140094e9e  jz      short loc_140094EAA
0x140094ea0  mov     eax, 80004005h
0x140094ea5  jmp     loc_14009500C
0x140094eaa  mov     eax, edi
0x140094eac  cdq
0x140094ead  sub     eax, edx
0x140094eaf  sar     eax, 1
0x140094eb1  movsxd  rsi, eax
0x140094eb4  mov     [rsp+21C8h+var_2158], rbx
0x140094eb9  mov     r14, rsi
0x140094ebc  mov     [rsp+21C8h+var_2168], rsi
0x140094ec1  mov     edx, 1
0x140094ec6  mov     rcx, rsi
0x140094ec9  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140094ece  cmp     rax, 100h
0x140094ed4  jbe     short loc_140094EEA
0x140094ed6  mov     rdx, rax
0x140094ed9  lea     rcx, [rsp+21C8h+var_2158]
0x140094ede  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140094ee3  mov     rcx, [rsp+21C8h+var_2158]
0x140094ee8  jmp     short loc_140094EF4
0x140094eea  lea     rcx, [rsp+21C8h+var_2150]
0x140094eef  mov     [rsp+21C8h+var_2158], rcx
0x140094ef4  jmp     short loc_140094F18
0x140094ef6  xor     ebx, ebx
0x140094ef8  mov     edi, dword ptr [rsp+21C8h+Data]
0x140094efc  mov     rcx, [rsp+21C8h+var_2158]; void *
0x140094f01  mov     r14, [rsp+21C8h+var_2168]
0x140094f06  mov     r13, [rsp+21C8h+var_2188]
0x140094f0b  mov     r15, [rsp+21C8h+var_2180]
0x140094f10  mov     r12, [rsp+21C8h+var_2178]
0x140094f15  mov     esi, r14d
0x140094f18  test    rcx, rcx
0x140094f1b  jnz     short loc_140094F2C
0x140094f1d  lea     rcx, [rsp+21C8h+var_2158]
0x140094f22  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140094f27  jmp     loc_140094EA0
0x140094f2c  mov     r8, r14; Size
0x140094f2f  xor     edx, edx; Val
0x140094f31  call    memset_0
0x140094f36  mov     r10d, ebx
0x140094f39  test    edi, edi
0x140094f3b  jle     short loc_140094F76
0x140094f3d  mov     r9d, r10d
0x140094f40  shr     r9, 1
0x140094f43  mov     r8, [rsp+21C8h+var_2158]
0x140094f48  mov     ecx, r10d
0x140094f4b  movzx   ecx, [rsp+rcx*2+21C8h+String1]; unsigned __int16
0x140094f53  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x140094f58  mov     edx, r10d
0x140094f5b  and     edx, 1
0x140094f5e  shl     edx, 2
0x140094f61  mov     ecx, 4
0x140094f66  sub     ecx, edx
0x140094f68  shl     al, cl
0x140094f6a  or      [r9+r8], al
0x140094f6e  inc     r10d
0x140094f71  cmp     r10d, edi
0x140094f74  jl      short loc_140094F3D
0x140094f76  mov     rax, [rsp+21C8h+var_2158]
0x140094f7b  mov     [rsp+21C8h+cbData], esi; cbData
0x140094f7f  mov     [rsp+21C8h+lpData], rax; lpData
0x140094f84  mov     r9d, 3; dwType
0x140094f8a  xor     r8d, r8d; Reserved
0x140094f8d  mov     rdx, r12; lpValueName
0x140094f90  mov     rcx, [r15]; hKey
0x140094f93  call    cs:__imp_RegSetValueExW
0x140094f99  mov     edi, eax
0x140094f9b  lea     rcx, [rsp+21C8h+var_2158]
0x140094fa0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140094fa5  jmp     short loc_140094FEB
0x140094fa7  lea     rax, [rsp+21C8h+String1]
0x140094faf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140094fb3  inc     rdi
0x140094fb6  cmp     [rax+rdi*2], bx
0x140094fba  jnz     short loc_140094FB3
0x140094fbc  lea     eax, ds:2[rdi*2]
0x140094fc3  mov     [rsp+21C8h+cbData], eax; cbData
0x140094fc7  lea     rax, [rsp+21C8h+String1]
0x140094fcf  mov     [rsp+21C8h+lpData], rax; lpData
0x140094fd4  mov     r9d, 1; dwType
0x140094fda  xor     r8d, r8d; Reserved
0x140094fdd  mov     rdx, r12; lpValueName
0x140094fe0  mov     rcx, [r15]; hKey
0x140094fe3  call    cs:__imp_RegSetValueExW
0x140094fe9  mov     edi, eax
0x140094feb  test    edi, edi
0x140094fed  jz      short loc_140094FF8
0x140094fef  mov     ecx, edi; unsigned int
0x140094ff1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140094ff6  jmp     short loc_14009500C
0x140094ff8  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x140094ffd  mov     rcx, r13; this
0x140095000  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140095005  test    eax, eax
0x140095007  cmovs   ebx, eax
0x14009500a  mov     eax, ebx
0x14009500c  mov     rcx, [rsp+21C8h+var_48]
0x140095014  xor     rcx, rsp; StackCookie
0x140095017  call    __security_check_cookie
0x14009501c  add     rsp, 2190h
0x140095023  pop     r15
0x140095025  pop     r14
0x140095027  pop     r13
0x140095029  pop     r12
0x14009502b  pop     rdi
0x14009502c  pop     rsi
0x14009502d  pop     rbx
0x14009502e  retn
```
