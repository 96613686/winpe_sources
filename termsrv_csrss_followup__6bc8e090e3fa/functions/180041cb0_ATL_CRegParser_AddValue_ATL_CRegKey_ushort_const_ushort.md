# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180041cb0`
- end: `0x180042189`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1241`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18004b974`

## callees

- `0x180033f60`
- `0x180034e64`
- `0x18003a634`
- `0x18003de14`
- `0x18003fb5c`
- `0x18003fdf0`
- `0x180041cb0`
- `0x180042190`
- `0x180042308`
- `0x1800424dc`
- `0x18004a138`
- `0x18004d484`
- `0x1800cae70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041ede`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041f7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800420d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004212f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041ede`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041f7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800420d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004212f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180041e4f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180041e71`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180041e4f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180041e71`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041d3d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180041d3d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180041f30`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180041f30`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r13
  HKEY *v5; // r12
  ATL::CRegParser *v6; // r14
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rsi
  WCHAR *k; // r14
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // edi
  HRESULT v21; // edi
  __int64 v22; // rdi
  DWORD v23; // r14d
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int j; // r10d
  unsigned __int8 v28; // al
  int v29; // r10d
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21A0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-2198h] BYREF
  ATL::CRegParser *v37; // [rsp+48h] [rbp-2190h]
  const unsigned __int16 *v38; // [rsp+50h] [rbp-2188h]
  size_t v39; // [rsp+60h] [rbp-2178h]
  struct ATL::CRegKey *v40; // [rsp+68h] [rbp-2170h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-2168h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v43[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v35 = this;
  *(_QWORD *)Data = a2;
  v37 = this;
  v40 = (struct ATL::CRegKey *)a2;
  v38 = a3;
  v41 = a4;
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
      v20 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
      break;
    case 17:
      v22 = -1;
      do
        ++v22;
      while ( String1[v22] );
      *(_DWORD *)Data = v22;
      if ( (v22 & 1) == 0 )
      {
        v23 = (int)v22 / 2;
        lpData = 0;
        v24 = (int)v22 / 2;
        v39 = v24;
        try
        {
          v25 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v25 <= 0x100 )
          {
            v26 = v43;
            lpData = v43;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
            v26 = lpData;
          }
        }
        catch ( ... )
        {
          v8 = 0;
          LODWORD(v22) = *(_DWORD *)Data;
          v26 = lpData;
          v24 = v39;
          v35 = v37;
          v5 = (HKEY *)v40;
          v4 = v38;
          v23 = v39;
        }
        if ( v26 )
        {
          memset_0(v26, 0, v24);
          for ( j = 0; j < (int)v22; j = v29 + 1 )
          {
            v28 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v31 + v30) |= v28 << (4 - 4 * (v29 & 1));
          }
          v20 = RegSetValueExW(*v5, v4, 0, 3u, lpData, v23);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_33:
          v6 = v35;
          break;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    case 19:
      pulOut = 0;
      v35 = 0;
      v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v21 < 0 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        return (unsigned int)v21;
      }
      *(_DWORD *)Data = pulOut;
      v20 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
      break;
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
          v13 = v43;
          lpData = v43;
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
        v5 = *(HKEY **)Data;
        v35 = v37;
        v4 = v38;
      }
      if ( v13 )
      {
        for ( k = String1; *k; v13 += 2 )
        {
          v15 = CharNextW(k);
          if ( *k == 92 && *v15 == 48 )
          {
            *(_WORD *)v13 = 0;
            k = CharNextW(v15);
          }
          else
          {
            *(_WORD *)v13 = *k++;
          }
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
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
        v20 = RegSetValueExW(*v5, v4, 0, 7u, lpData, cbData);
      }
      else
      {
        v20 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      goto LABEL_33;
    default:
LABEL_55:
      Token = ATL::CRegParser::NextToken(v6, v41);
      if ( Token < 0 )
        return (unsigned int)Token;
      return v8;
  }
  if ( !v20 )
    goto LABEL_55;
  return ATL::AtlHresultFromWin32(v20);
}

```

## disassembly

```asm
0x180041cb0  push    rbx
0x180041cb2  push    rsi
0x180041cb3  push    rdi
0x180041cb4  push    r12
0x180041cb6  push    r13
0x180041cb8  push    r14
0x180041cba  push    r15
0x180041cbc  mov     eax, 21A0h
0x180041cc1  call    _alloca_probe
0x180041cc6  sub     rsp, rax
0x180041cc9  mov     rax, cs:__security_cookie
0x180041cd0  xor     rax, rsp
0x180041cd3  mov     [rsp+21D8h+var_48], rax
0x180041cdb  mov     r13, r8
0x180041cde  mov     r12, rdx
0x180041ce1  mov     r14, rcx
0x180041ce4  mov     [rsp+21D8h+var_21A0], rcx
0x180041ce9  mov     qword ptr [rsp+21D8h+Data], rdx
0x180041cee  mov     [rsp+21D8h+var_2190], rcx
0x180041cf3  mov     [rsp+21D8h+var_2170], rdx
0x180041cf8  mov     [rsp+21D8h+var_2188], r8
0x180041cfd  mov     [rsp+21D8h+var_2168], r9
0x180041d02  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180041d0a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041d0f  xor     ebx, ebx
0x180041d11  test    eax, eax
0x180041d13  js      loc_180042165
0x180041d19  mov     edi, ebx
0x180041d1b  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180041d22  cmp     edi, 4
0x180041d25  jnb     loc_180042160
0x180041d2b  movsxd  rsi, edi
0x180041d2e  add     rsi, rsi
0x180041d31  mov     rdx, [r15+rsi*8]; lpString2
0x180041d35  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180041d3d  call    cs:__imp_lstrcmpiW
0x180041d44  nop     dword ptr [rax+rax+00h]
0x180041d49  test    eax, eax
0x180041d4b  jz      short loc_180041D51
0x180041d4d  inc     edi
0x180041d4f  jmp     short loc_180041D22
0x180041d51  movzx   edi, word ptr [r15+rsi*8+8]
0x180041d57  mov     rcx, r14; this
0x180041d5a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180041d5f  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180041d67  mov     rcx, r14; this
0x180041d6a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180041d6f  test    eax, eax
0x180041d71  js      loc_180042165
0x180041d77  cmp     di, 8
0x180041d7b  jz      loc_1800420F2
0x180041d81  cmp     di, 11h
0x180041d85  jz      loc_180041F9A
0x180041d8b  cmp     di, 13h
0x180041d8f  jz      loc_180041F15
0x180041d95  mov     eax, 4008h
0x180041d9a  cmp     di, ax
0x180041d9d  jnz     loc_18004214A
0x180041da3  lea     rcx, [rsp+21D8h+String1]
0x180041dab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041daf  mov     rax, rdi
0x180041db2  inc     rax
0x180041db5  cmp     [rcx+rax*2], bx
0x180041db9  jnz     short loc_180041DB2
0x180041dbb  add     eax, 2
0x180041dbe  mov     [rsp+21D8h+var_2158], rbx
0x180041dc6  movsxd  rcx, eax
0x180041dc9  mov     r15d, 2
0x180041dcf  mov     edx, r15d
0x180041dd2  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180041dd7  cmp     rax, 100h
0x180041ddd  jbe     short loc_180041DF9
0x180041ddf  mov     rdx, rax
0x180041de2  lea     rcx, [rsp+21D8h+var_2158]
0x180041dea  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180041def  mov     rsi, [rsp+21D8h+var_2158]
0x180041df7  jmp     short loc_180041E09
0x180041df9  lea     rsi, [rsp+21D8h+var_2150]
0x180041e01  mov     [rsp+21D8h+var_2158], rsi
0x180041e09  jmp     short loc_180041E31
0x180041e0b  xor     ebx, ebx
0x180041e0d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041e11  lea     r15d, [rbx+2]
0x180041e15  mov     rsi, [rsp+21D8h+var_2158]
0x180041e1d  mov     r12, qword ptr [rsp+21D8h+Data]
0x180041e22  mov     rax, [rsp+21D8h+var_2190]
0x180041e27  mov     [rsp+21D8h+var_21A0], rax
0x180041e2c  mov     r13, [rsp+21D8h+var_2188]
0x180041e31  test    rsi, rsi
0x180041e34  jz      loc_180041EF9
0x180041e3a  lea     r14, [rsp+21D8h+String1]
0x180041e42  cmp     [rsp+21D8h+String1], bx
0x180041e4a  jz      short loc_180041E91
0x180041e4c  mov     rcx, r14; lpsz
0x180041e4f  call    cs:__imp_CharNextW
0x180041e56  nop     dword ptr [rax+rax+00h]
0x180041e5b  movzx   ecx, word ptr [r14]
0x180041e5f  cmp     cx, 5Ch ; '\'
0x180041e63  jnz     short loc_180041E82
0x180041e65  cmp     word ptr [rax], 30h ; '0'
0x180041e69  jnz     short loc_180041E82
0x180041e6b  mov     [rsi], bx
0x180041e6e  mov     rcx, rax; lpsz
0x180041e71  call    cs:__imp_CharNextW
0x180041e78  nop     dword ptr [rax+rax+00h]
0x180041e7d  mov     r14, rax
0x180041e80  jmp     short loc_180041E88
0x180041e82  mov     [rsi], cx
0x180041e85  add     r14, r15
0x180041e88  add     rsi, r15
0x180041e8b  cmp     [r14], bx
0x180041e8f  jnz     short loc_180041E4C
0x180041e91  mov     dword ptr [rsi], 0
0x180041e97  mov     r8, [rsp+21D8h+var_2158]
0x180041e9f  test    r8, r8
0x180041ea2  jz      short loc_180041EEE
0x180041ea4  mov     r10d, ebx
0x180041ea7  mov     r9, r8
0x180041eaa  mov     rcx, rdi
0x180041ead  inc     rcx
0x180041eb0  cmp     [r9+rcx*2], bx
0x180041eb5  jnz     short loc_180041EAD
0x180041eb7  inc     ecx
0x180041eb9  lea     r9, [r9+rcx*2]
0x180041ebd  lea     r10d, [r10+rcx*2]
0x180041ec1  cmp     ecx, 1
0x180041ec4  jnz     short loc_180041EAA
0x180041ec6  mov     [rsp+21D8h+cbData], r10d; cbData
0x180041ecb  mov     [rsp+21D8h+lpData], r8; lpData
0x180041ed0  lea     r9d, [rcx+6]; dwType
0x180041ed4  xor     r8d, r8d; Reserved
0x180041ed7  mov     rdx, r13; lpValueName
0x180041eda  mov     rcx, [r12]; hKey
0x180041ede  call    cs:__imp_RegSetValueExW
0x180041ee5  nop     dword ptr [rax+rax+00h]
0x180041eea  mov     edi, eax
0x180041eec  jmp     short loc_180041EFE
0x180041eee  mov     ecx, 80004005h; int
0x180041ef3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180041ef9  mov     edi, 0Eh
0x180041efe  lea     rcx, [rsp+21D8h+var_2158]
0x180041f06  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180041f0b  mov     r14, [rsp+21D8h+var_21A0]
0x180041f10  jmp     loc_18004213D
0x180041f15  mov     [rsp+21D8h+pulOut], ebx
0x180041f19  mov     [rsp+21D8h+var_21A0], rbx
0x180041f1e  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x180041f23  xor     r8d, r8d; dwFlags
0x180041f26  xor     edx, edx; lcid
0x180041f28  lea     rcx, [rsp+21D8h+String1]; strIn
0x180041f30  call    cs:__imp_VarUI4FromStr
0x180041f37  nop     dword ptr [rax+rax+00h]
0x180041f3c  mov     edi, eax
0x180041f3e  test    eax, eax
0x180041f40  jns     short loc_180041F53
0x180041f42  lea     rcx, [rsp+21D8h+var_21A0]
0x180041f47  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180041f4c  mov     eax, edi
0x180041f4e  jmp     loc_180042165
0x180041f53  mov     eax, [rsp+21D8h+pulOut]
0x180041f57  mov     dword ptr [rsp+21D8h+Data], eax
0x180041f5b  mov     [rsp+21D8h+cbData], 4; cbData
0x180041f63  lea     rax, [rsp+21D8h+Data]
0x180041f68  mov     [rsp+21D8h+lpData], rax; lpData
0x180041f6d  mov     r9d, 4; dwType
0x180041f73  xor     r8d, r8d; Reserved
0x180041f76  mov     rdx, r13; lpValueName
0x180041f79  mov     rcx, [r12]; hKey
0x180041f7d  call    cs:__imp_RegSetValueExW
0x180041f84  nop     dword ptr [rax+rax+00h]
0x180041f89  mov     edi, eax
0x180041f8b  lea     rcx, [rsp+21D8h+var_21A0]
0x180041f90  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180041f95  jmp     loc_18004213D
0x180041f9a  lea     rax, [rsp+21D8h+String1]
0x180041fa2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041fa6  inc     rdi
0x180041fa9  cmp     [rax+rdi*2], bx
0x180041fad  jnz     short loc_180041FA6
0x180041faf  mov     dword ptr [rsp+21D8h+Data], edi
0x180041fb3  test    dil, 1
0x180041fb7  jz      short loc_180041FC3
0x180041fb9  mov     eax, 80004005h
0x180041fbe  jmp     loc_180042165
0x180041fc3  mov     eax, edi
0x180041fc5  cdq
0x180041fc6  mov     r15d, 2
0x180041fcc  idiv    r15d
0x180041fcf  movsxd  r14, eax
0x180041fd2  mov     [rsp+21D8h+var_2158], rbx
0x180041fda  mov     rsi, r14
0x180041fdd  mov     [rsp+21D8h+var_2178], r14
0x180041fe2  lea     edx, [r15-1]
0x180041fe6  mov     rcx, r14
0x180041fe9  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180041fee  cmp     rax, 100h
0x180041ff4  jbe     short loc_180042010
0x180041ff6  mov     rdx, rax
0x180041ff9  lea     rcx, [rsp+21D8h+var_2158]
0x180042001  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180042006  mov     rcx, [rsp+21D8h+var_2158]
0x18004200e  jmp     short loc_180042020
0x180042010  lea     rcx, [rsp+21D8h+var_2150]
0x180042018  mov     [rsp+21D8h+var_2158], rcx
0x180042020  jmp     short loc_18004204C
0x180042022  xor     ebx, ebx
0x180042024  mov     edi, dword ptr [rsp+21D8h+Data]
0x180042028  mov     rcx, [rsp+21D8h+var_2158]; void *
0x180042030  mov     rsi, [rsp+21D8h+var_2178]
0x180042035  mov     rax, [rsp+21D8h+var_2190]
0x18004203a  mov     [rsp+21D8h+var_21A0], rax
0x18004203f  mov     r12, [rsp+21D8h+var_2170]
0x180042044  mov     r13, [rsp+21D8h+var_2188]
0x180042049  mov     r14d, esi
0x18004204c  test    rcx, rcx
0x18004204f  jnz     short loc_180042063
0x180042051  lea     rcx, [rsp+21D8h+var_2158]
0x180042059  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18004205e  jmp     loc_180041FB9
0x180042063  mov     r8, rsi; Size
0x180042066  xor     edx, edx; Val
0x180042068  call    memset_0
0x18004206d  mov     r10d, ebx
0x180042070  test    edi, edi
0x180042072  jle     short loc_1800420B0
0x180042074  mov     r9d, r10d
0x180042077  shr     r9, 1
0x18004207a  mov     r8, [rsp+21D8h+var_2158]
0x180042082  mov     ecx, r10d
0x180042085  movzx   ecx, [rsp+rcx*2+21D8h+String1]; unsigned __int16
0x18004208d  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180042092  mov     edx, r10d
0x180042095  and     edx, 1
0x180042098  shl     edx, 2
0x18004209b  mov     ecx, 4
0x1800420a0  sub     ecx, edx
0x1800420a2  shl     al, cl
0x1800420a4  or      [r9+r8], al
0x1800420a8  inc     r10d
0x1800420ab  cmp     r10d, edi
0x1800420ae  jl      short loc_180042074
0x1800420b0  mov     rax, [rsp+21D8h+var_2158]
0x1800420b8  mov     [rsp+21D8h+cbData], r14d; cbData
0x1800420bd  mov     [rsp+21D8h+lpData], rax; lpData
0x1800420c2  mov     r9d, 3; dwType
0x1800420c8  xor     r8d, r8d; Reserved
0x1800420cb  mov     rdx, r13; lpValueName
0x1800420ce  mov     rcx, [r12]; hKey
0x1800420d2  call    cs:__imp_RegSetValueExW
0x1800420d9  nop     dword ptr [rax+rax+00h]
0x1800420de  mov     edi, eax
0x1800420e0  lea     rcx, [rsp+21D8h+var_2158]
0x1800420e8  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800420ed  jmp     loc_180041F0B
0x1800420f2  lea     rax, [rsp+21D8h+String1]
0x1800420fa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800420fe  inc     rdi
0x180042101  cmp     [rax+rdi*2], bx
0x180042105  jnz     short loc_1800420FE
0x180042107  lea     eax, ds:2[rdi*2]
0x18004210e  mov     [rsp+21D8h+cbData], eax; cbData
0x180042112  lea     rax, [rsp+21D8h+String1]
0x18004211a  mov     [rsp+21D8h+lpData], rax; lpData
0x18004211f  mov     r9d, 1; dwType
0x180042125  xor     r8d, r8d; Reserved
0x180042128  mov     rdx, r13; lpValueName
0x18004212b  mov     rcx, [r12]; hKey
0x18004212f  call    cs:__imp_RegSetValueExW
0x180042136  nop     dword ptr [rax+rax+00h]
0x18004213b  mov     edi, eax
0x18004213d  test    edi, edi
0x18004213f  jz      short loc_18004214A
0x180042141  mov     ecx, edi; unsigned int
0x180042143  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180042148  jmp     short loc_180042165
0x18004214a  mov     rdx, [rsp+21D8h+var_2168]; unsigned __int16 *
0x18004214f  mov     rcx, r14; this
0x180042152  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180042157  test    eax, eax
0x180042159  cmovs   ebx, eax
0x18004215c  mov     eax, ebx
0x18004215e  jmp     short loc_180042165
0x180042160  mov     eax, 80020009h
0x180042165  mov     rcx, [rsp+21D8h+var_48]
0x18004216d  xor     rcx, rsp; StackCookie
0x180042170  call    __security_check_cookie
0x180042175  add     rsp, 21A0h
0x18004217c  pop     r15
0x18004217e  pop     r14
0x180042180  pop     r13
0x180042182  pop     r12
0x180042184  pop     rdi
0x180042185  pop     rsi
0x180042186  pop     rbx
0x180042187  retn
```
