# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180038990`
- end: `0x180038e44`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1204`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18003a3fc`

## callees

- `0x180002da0`
- `0x1800039e4`
- `0x180013410`
- `0x180038440`
- `0x1800384f4`
- `0x180038990`
- `0x180038e4c`
- `0x180038f5c`
- `0x1800397ac`
- `0x18003aa64`
- `0x18003aa98`
- `0x18003ab04`
- `0x18003abe4`
- `0x18005b890`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180038bad`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180038bad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038dc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038dc4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180038b25`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180038b40`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180038b25`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180038b40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180038a18`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180038a18`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        struct ATL::CRegKey *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // r13
  ATL::CRegKey *v5; // r12
  ATL::CRegParser *v6; // r14
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  WCHAR *j; // rsi
  const WCHAR *v15; // rax
  LSTATUS v16; // edi
  HRESULT v17; // edi
  __int64 v18; // rdi
  DWORD cbData; // r14d
  size_t v20; // rsi
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  unsigned int v23; // r10d
  unsigned int v24; // edx
  char v25; // r9
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-21A0h] BYREF
  ATL::CRegParser *v29; // [rsp+48h] [rbp-2190h]
  struct ATL::CRegKey *v30; // [rsp+50h] [rbp-2188h]
  const unsigned __int16 *v31; // [rsp+60h] [rbp-2178h]
  size_t v32; // [rsp+70h] [rbp-2168h]
  unsigned __int16 *v33; // [rsp+78h] [rbp-2160h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v35[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v28[0] = this;
  v29 = this;
  v30 = a2;
  v31 = a3;
  v33 = a4;
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
      v16 = ATL::CRegKey::SetStringValue(v5, v4, String1, 1u);
      goto LABEL_70;
    case 17:
      v18 = -1;
      do
        ++v18;
      while ( String1[v18] );
      pulOut = v18;
      if ( (v18 & 1) != 0 )
        return 2147500037LL;
      cbData = (int)v18 / 2;
      lpData = 0;
      v20 = (int)v18 / 2;
      v32 = v20;
      try
      {
        v21 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v21 <= 0x100 )
        {
          v22 = v35;
          lpData = v35;
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
        LODWORD(v18) = pulOut;
        v22 = lpData;
        v20 = v32;
        v28[0] = v29;
        v5 = v30;
        v4 = v31;
        cbData = v32;
      }
      if ( !v22 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v22, 0, v20);
      v23 = 0;
      if ( (int)v18 <= 0 )
      {
LABEL_68:
        v16 = RegSetValueExW(*(HKEY *)v5, v4, 0, 3u, lpData, cbData);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_27;
      }
      while ( 1 )
      {
        v24 = String1[v23];
        if ( v24 > 0x61 )
        {
          if ( v24 == 98 || v24 == 99 || v24 == 100 || v24 - 101 < 2 )
          {
LABEL_66:
            v25 = v24 - 87;
            goto LABEL_67;
          }
LABEL_65:
          v25 = 0;
          goto LABEL_67;
        }
        if ( v24 == 97 )
          goto LABEL_66;
        if ( v24 <= 0x38 )
          break;
        if ( v24 == 57 )
          goto LABEL_53;
        if ( v24 != 65 && v24 != 66 && v24 != 67 && v24 != 68 && v24 - 69 > 1 )
          goto LABEL_65;
        v25 = v24 - 55;
LABEL_67:
        lpData[(unsigned __int64)v23 >> 1] |= v25 << (4 - 4 * (v23 & 1));
        if ( (int)++v23 >= (int)v18 )
          goto LABEL_68;
      }
      if ( v24 != 56 && v24 != 48 && v24 != 49 && v24 != 50 && v24 != 51 && v24 != 52 && v24 != 53 && v24 - 54 > 1 )
        goto LABEL_65;
LABEL_53:
      v25 = v24 - 48;
      goto LABEL_67;
    case 19:
      pulOut = 0;
      v28[0] = 0;
      v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v17 >= 0 )
      {
        v16 = ATL::CRegKey::SetDWORDValue(v5, v4, pulOut);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v28);
        goto LABEL_70;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v28);
      return (unsigned int)v17;
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
          v13 = v35;
          lpData = v35;
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
        v28[0] = v29;
        v5 = v30;
        v4 = v31;
      }
      if ( v13 )
      {
        for ( j = String1; *j; v13 += 2 )
        {
          v15 = CharNextW(j);
          if ( *j == 92 && *v15 == 48 )
          {
            *(_WORD *)v13 = 0;
            j = CharNextW(v15);
          }
          else
          {
            *(_WORD *)v13 = *j++;
          }
        }
        *(_DWORD *)v13 = 0;
        v16 = ATL::CRegKey::SetMultiStringValue(v5, v4, (const unsigned __int16 *)lpData);
      }
      else
      {
        v16 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_27:
      v6 = (ATL::CRegParser *)v28[0];
LABEL_70:
      if ( v16 )
      {
        return ATL::AtlHresultFromWin32(v16);
      }
      else
      {
LABEL_72:
        Token = ATL::CRegParser::NextToken(v6, v33);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_72;
  }
}

```

## disassembly

```asm
0x180038990  push    rbx
0x180038992  push    rsi
0x180038993  push    rdi
0x180038994  push    r12
0x180038996  push    r13
0x180038998  push    r14
0x18003899a  push    r15
0x18003899c  mov     eax, 21A0h
0x1800389a1  call    _alloca_probe
0x1800389a6  sub     rsp, rax
0x1800389a9  mov     rax, cs:__security_cookie
0x1800389b0  xor     rax, rsp
0x1800389b3  mov     [rsp+21D8h+var_48], rax
0x1800389bb  mov     r13, r8
0x1800389be  mov     r12, rdx
0x1800389c1  mov     r14, rcx
0x1800389c4  mov     [rsp+21D8h+var_21A0], rcx
0x1800389c9  mov     [rsp+21D8h+var_2190], rcx
0x1800389ce  mov     [rsp+21D8h+var_2188], rdx
0x1800389d3  mov     [rsp+21D8h+var_2178], r8
0x1800389d8  mov     [rsp+21D8h+var_2160], r9
0x1800389dd  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x1800389e5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800389ea  xor     ebx, ebx
0x1800389ec  test    eax, eax
0x1800389ee  js      loc_180038E21
0x1800389f4  mov     edi, ebx
0x1800389f6  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800389fd  cmp     edi, 4
0x180038a00  jnb     loc_180038E1C
0x180038a06  movsxd  rsi, edi
0x180038a09  add     rsi, rsi
0x180038a0c  mov     rdx, [r15+rsi*8]; lpString2
0x180038a10  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180038a18  call    cs:__imp_lstrcmpiW
0x180038a1e  test    eax, eax
0x180038a20  jz      short loc_180038A26
0x180038a22  inc     edi
0x180038a24  jmp     short loc_1800389FD
0x180038a26  movzx   edi, word ptr [r15+rsi*8+8]
0x180038a2c  mov     rcx, r14; this
0x180038a2f  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180038a34  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180038a3c  mov     rcx, r14; this
0x180038a3f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180038a44  test    eax, eax
0x180038a46  js      loc_180038E21
0x180038a4c  mov     r15d, 8
0x180038a52  cmp     di, r15w
0x180038a56  jz      loc_180038DDE
0x180038a5c  cmp     di, 11h
0x180038a60  jz      loc_180038BEB
0x180038a66  cmp     di, 13h
0x180038a6a  jz      loc_180038B92
0x180038a70  mov     eax, 4008h
0x180038a75  cmp     di, ax
0x180038a78  jnz     loc_180038E06
0x180038a7e  lea     rax, [rsp+21D8h+String1]
0x180038a86  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180038a8a  inc     rdi
0x180038a8d  cmp     [rax+rdi*2], bx
0x180038a91  jnz     short loc_180038A8A
0x180038a93  add     edi, 2
0x180038a96  mov     [rsp+21D8h+var_2158], rbx
0x180038a9e  movsxd  rcx, edi
0x180038aa1  mov     r14d, 2
0x180038aa7  mov     edx, r14d
0x180038aaa  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180038aaf  cmp     rax, 100h
0x180038ab5  jbe     short loc_180038AD1
0x180038ab7  mov     rdx, rax
0x180038aba  lea     rcx, [rsp+21D8h+var_2158]
0x180038ac2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180038ac7  mov     rdi, [rsp+21D8h+var_2158]
0x180038acf  jmp     short loc_180038AE1
0x180038ad1  lea     rdi, [rsp+21D8h+var_2150]
0x180038ad9  mov     [rsp+21D8h+var_2158], rdi
0x180038ae1  jmp     short loc_180038B05
0x180038ae3  xor     ebx, ebx
0x180038ae5  lea     r14d, [rbx+2]
0x180038ae9  mov     rdi, [rsp+21D8h+var_2158]
0x180038af1  mov     rax, [rsp+21D8h+var_2190]
0x180038af6  mov     [rsp+21D8h+var_21A0], rax
0x180038afb  mov     r12, [rsp+21D8h+var_2188]
0x180038b00  mov     r13, [rsp+21D8h+var_2178]
0x180038b05  test    rdi, rdi
0x180038b08  jz      short loc_180038B76
0x180038b0a  lea     rsi, [rsp+21D8h+String1]
0x180038b12  cmp     [rsp+21D8h+String1], bx
0x180038b1a  jz      short loc_180038B59
0x180038b1c  mov     r15d, 30h ; '0'
0x180038b22  mov     rcx, rsi; lpsz
0x180038b25  call    cs:__imp_CharNextW
0x180038b2b  movzx   ecx, word ptr [rsi]
0x180038b2e  cmp     cx, 5Ch ; '\'
0x180038b32  jnz     short loc_180038B4B
0x180038b34  cmp     [rax], r15w
0x180038b38  jnz     short loc_180038B4B
0x180038b3a  mov     [rdi], bx
0x180038b3d  mov     rcx, rax; lpsz
0x180038b40  call    cs:__imp_CharNextW
0x180038b46  mov     rsi, rax
0x180038b49  jmp     short loc_180038B51
0x180038b4b  mov     [rdi], cx
0x180038b4e  add     rsi, r14
0x180038b51  add     rdi, r14
0x180038b54  cmp     [rsi], bx
0x180038b57  jnz     short loc_180038B22
0x180038b59  mov     dword ptr [rdi], 0
0x180038b5f  mov     r8, [rsp+21D8h+var_2158]; unsigned __int16 *
0x180038b67  mov     rdx, r13; unsigned __int16 *
0x180038b6a  mov     rcx, r12; this
0x180038b6d  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x180038b72  mov     edi, eax
0x180038b74  jmp     short loc_180038B7B
0x180038b76  mov     edi, 0Eh
0x180038b7b  lea     rcx, [rsp+21D8h+var_2158]
0x180038b83  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180038b88  mov     r14, [rsp+21D8h+var_21A0]
0x180038b8d  jmp     loc_180038DF9
0x180038b92  mov     [rsp+21D8h+pulOut], ebx
0x180038b96  mov     [rsp+21D8h+var_21A0], rbx
0x180038b9b  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x180038ba0  xor     r8d, r8d; dwFlags
0x180038ba3  xor     edx, edx; lcid
0x180038ba5  lea     rcx, [rsp+21D8h+String1]; strIn
0x180038bad  call    cs:__imp_VarUI4FromStr
0x180038bb3  mov     edi, eax
0x180038bb5  test    eax, eax
0x180038bb7  jns     short loc_180038BCA
0x180038bb9  lea     rcx, [rsp+21D8h+var_21A0]
0x180038bbe  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180038bc3  mov     eax, edi
0x180038bc5  jmp     loc_180038E21
0x180038bca  mov     r8d, [rsp+21D8h+pulOut]; unsigned int
0x180038bcf  mov     rdx, r13; unsigned __int16 *
0x180038bd2  mov     rcx, r12; this
0x180038bd5  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180038bda  mov     edi, eax
0x180038bdc  lea     rcx, [rsp+21D8h+var_21A0]
0x180038be1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180038be6  jmp     loc_180038DF9
0x180038beb  lea     rax, [rsp+21D8h+String1]
0x180038bf3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180038bf7  inc     rdi
0x180038bfa  cmp     [rax+rdi*2], bx
0x180038bfe  jnz     short loc_180038BF7
0x180038c00  mov     [rsp+21D8h+pulOut], edi
0x180038c04  test    dil, 1
0x180038c08  jz      short loc_180038C14
0x180038c0a  mov     eax, 80004005h
0x180038c0f  jmp     loc_180038E21
0x180038c14  mov     eax, edi
0x180038c16  cdq
0x180038c17  mov     r14d, 2
0x180038c1d  idiv    r14d
0x180038c20  movsxd  r14, eax
0x180038c23  mov     [rsp+21D8h+var_2158], rbx
0x180038c2b  mov     rsi, r14
0x180038c2e  mov     [rsp+21D8h+var_2168], r14
0x180038c33  mov     edx, 1
0x180038c38  mov     rcx, r14
0x180038c3b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180038c40  cmp     rax, 100h
0x180038c46  jbe     short loc_180038C62
0x180038c48  mov     rdx, rax
0x180038c4b  lea     rcx, [rsp+21D8h+var_2158]
0x180038c53  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180038c58  mov     rcx, [rsp+21D8h+var_2158]
0x180038c60  jmp     short loc_180038C72
0x180038c62  lea     rcx, [rsp+21D8h+var_2150]
0x180038c6a  mov     [rsp+21D8h+var_2158], rcx
0x180038c72  jmp     short loc_180038C9E
0x180038c74  xor     ebx, ebx
0x180038c76  mov     edi, [rsp+21D8h+pulOut]
0x180038c7a  mov     rcx, [rsp+21D8h+var_2158]; void *
0x180038c82  mov     rsi, [rsp+21D8h+var_2168]
0x180038c87  mov     rax, [rsp+21D8h+var_2190]
0x180038c8c  mov     [rsp+21D8h+var_21A0], rax
0x180038c91  mov     r12, [rsp+21D8h+var_2188]
0x180038c96  mov     r13, [rsp+21D8h+var_2178]
0x180038c9b  mov     r14d, esi
0x180038c9e  test    rcx, rcx
0x180038ca1  jnz     short loc_180038CB5
0x180038ca3  lea     rcx, [rsp+21D8h+var_2158]
0x180038cab  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180038cb0  jmp     loc_180038C0A
0x180038cb5  mov     r8, rsi; Size
0x180038cb8  xor     edx, edx; Val
0x180038cba  call    memset_0
0x180038cbf  mov     r10d, ebx
0x180038cc2  test    edi, edi
0x180038cc4  jle     loc_180038DA2
0x180038cca  mov     r15d, 30h ; '0'
0x180038cd0  mov     eax, r10d
0x180038cd3  movzx   edx, [rsp+rax*2+21D8h+String1]
0x180038cdb  cmp     edx, 61h ; 'a'
0x180038cde  ja      short loc_180038D4D
0x180038ce0  jz      loc_180038D6D
0x180038ce6  cmp     edx, 38h ; '8'
0x180038ce9  ja      short loc_180038D1F
0x180038ceb  jz      short loc_180038D17
0x180038ced  mov     ecx, edx
0x180038cef  sub     ecx, r15d
0x180038cf2  jz      short loc_180038D17
0x180038cf4  sub     ecx, 1
0x180038cf7  jz      short loc_180038D17
0x180038cf9  sub     ecx, 1
0x180038cfc  jz      short loc_180038D17
0x180038cfe  sub     ecx, 1
0x180038d01  jz      short loc_180038D17
0x180038d03  sub     ecx, 1
0x180038d06  jz      short loc_180038D17
0x180038d08  sub     ecx, 1
0x180038d0b  jz      short loc_180038D17
0x180038d0d  sub     ecx, 1
0x180038d10  jz      short loc_180038D17
0x180038d12  cmp     ecx, 1
0x180038d15  jnz     short loc_180038D68
0x180038d17  mov     r9d, edx
0x180038d1a  sub     r9d, r15d
0x180038d1d  jmp     short loc_180038D71
0x180038d1f  mov     r9d, edx
0x180038d22  mov     ecx, edx
0x180038d24  sub     ecx, 39h ; '9'
0x180038d27  jz      short loc_180038D17
0x180038d29  sub     ecx, 8
0x180038d2c  jz      short loc_180038D47
0x180038d2e  sub     ecx, 1
0x180038d31  jz      short loc_180038D47
0x180038d33  sub     ecx, 1
0x180038d36  jz      short loc_180038D47
0x180038d38  sub     ecx, 1
0x180038d3b  jz      short loc_180038D47
0x180038d3d  sub     ecx, 1
0x180038d40  jz      short loc_180038D47
0x180038d42  cmp     ecx, 1
0x180038d45  jnz     short loc_180038D68
0x180038d47  add     r9d, 0FFFFFFC9h
0x180038d4b  jmp     short loc_180038D71
0x180038d4d  mov     ecx, edx
0x180038d4f  sub     ecx, 62h ; 'b'
0x180038d52  jz      short loc_180038D6D
0x180038d54  sub     ecx, 1
0x180038d57  jz      short loc_180038D6D
0x180038d59  sub     ecx, 1
0x180038d5c  jz      short loc_180038D6D
0x180038d5e  sub     ecx, 1
0x180038d61  jz      short loc_180038D6D
0x180038d63  cmp     ecx, 1
0x180038d66  jz      short loc_180038D6D
0x180038d68  mov     r9d, ebx
0x180038d6b  jmp     short loc_180038D71
0x180038d6d  lea     r9d, [rdx-57h]
0x180038d71  mov     r8d, r10d
0x180038d74  shr     r8, 1
0x180038d77  mov     rdx, [rsp+21D8h+var_2158]
0x180038d7f  mov     eax, r10d
0x180038d82  and     eax, 1
0x180038d85  shl     eax, 2
0x180038d88  mov     ecx, 4
0x180038d8d  sub     ecx, eax
0x180038d8f  shl     r9b, cl
0x180038d92  or      [r8+rdx], r9b
0x180038d96  inc     r10d
0x180038d99  cmp     r10d, edi
0x180038d9c  jl      loc_180038CD0
0x180038da2  mov     rax, [rsp+21D8h+var_2158]
0x180038daa  mov     [rsp+21D8h+cbData], r14d; cbData
0x180038daf  mov     [rsp+21D8h+lpData], rax; lpData
0x180038db4  mov     r9d, 3; dwType
0x180038dba  xor     r8d, r8d; Reserved
0x180038dbd  mov     rdx, r13; lpValueName
0x180038dc0  mov     rcx, [r12]; hKey
0x180038dc4  call    cs:__imp_RegSetValueExW
0x180038dca  mov     edi, eax
0x180038dcc  lea     rcx, [rsp+21D8h+var_2158]
0x180038dd4  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180038dd9  jmp     loc_180038B88
0x180038dde  mov     r9d, 1; unsigned int
0x180038de4  lea     r8, [rsp+21D8h+String1]; unsigned __int16 *
0x180038dec  mov     rdx, r13; unsigned __int16 *
0x180038def  mov     rcx, r12; this
0x180038df2  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180038df7  mov     edi, eax
0x180038df9  test    edi, edi
0x180038dfb  jz      short loc_180038E06
0x180038dfd  mov     ecx, edi; unsigned int
0x180038dff  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180038e04  jmp     short loc_180038E21
0x180038e06  mov     rdx, [rsp+21D8h+var_2160]; unsigned __int16 *
0x180038e0b  mov     rcx, r14; this
0x180038e0e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180038e13  test    eax, eax
0x180038e15  cmovs   ebx, eax
0x180038e18  mov     eax, ebx
0x180038e1a  jmp     short loc_180038E21
0x180038e1c  mov     eax, 80020009h
0x180038e21  mov     rcx, [rsp+21D8h+var_48]
0x180038e29  xor     rcx, rsp; StackCookie
  ... truncated ...
```
