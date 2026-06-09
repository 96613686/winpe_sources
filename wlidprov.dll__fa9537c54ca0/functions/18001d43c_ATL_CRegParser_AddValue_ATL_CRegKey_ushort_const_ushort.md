# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18001d43c`
- end: `0x18001d8f0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1204`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18001ef4c`

## callees

- `0x18001a0d0`
- `0x18001ac3c`
- `0x18001cb34`
- `0x18001cc14`
- `0x18001cdf0`
- `0x18001d43c`
- `0x18001d8f8`
- `0x18001da2c`
- `0x18001e500`
- `0x18001f81c`
- `0x18001f850`
- `0x18001f8bc`
- `0x18001f99c`
- `0x180053560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d870`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d870`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001d5d1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001d5ec`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001d5d1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001d5ec`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001d4c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001d4c4`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001d659`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001d659`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  WCHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

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
0x18001d43c  push    rbx
0x18001d43e  push    rsi
0x18001d43f  push    rdi
0x18001d440  push    r12
0x18001d442  push    r13
0x18001d444  push    r14
0x18001d446  push    r15
0x18001d448  mov     eax, 21A0h
0x18001d44d  call    _alloca_probe
0x18001d452  sub     rsp, rax
0x18001d455  mov     rax, cs:__security_cookie
0x18001d45c  xor     rax, rsp
0x18001d45f  mov     [rsp+21D8h+var_48], rax
0x18001d467  mov     r13, r8
0x18001d46a  mov     r12, rdx
0x18001d46d  mov     r14, rcx
0x18001d470  mov     [rsp+21D8h+var_21A0], rcx
0x18001d475  mov     [rsp+21D8h+var_2190], rcx
0x18001d47a  mov     [rsp+21D8h+var_2188], rdx
0x18001d47f  mov     [rsp+21D8h+var_2178], r8
0x18001d484  mov     [rsp+21D8h+var_2160], r9
0x18001d489  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x18001d491  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001d496  xor     ebx, ebx
0x18001d498  test    eax, eax
0x18001d49a  js      loc_18001D8CD
0x18001d4a0  mov     edi, ebx
0x18001d4a2  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001d4a9  cmp     edi, 4
0x18001d4ac  jnb     loc_18001D8C8
0x18001d4b2  movsxd  rsi, edi
0x18001d4b5  add     rsi, rsi
0x18001d4b8  mov     rdx, [r15+rsi*8]; lpString2
0x18001d4bc  lea     rcx, [rsp+21D8h+String1]; lpString1
0x18001d4c4  call    cs:__imp_lstrcmpiW
0x18001d4ca  test    eax, eax
0x18001d4cc  jz      short loc_18001D4D2
0x18001d4ce  inc     edi
0x18001d4d0  jmp     short loc_18001D4A9
0x18001d4d2  movzx   edi, word ptr [r15+rsi*8+8]
0x18001d4d8  mov     rcx, r14; this
0x18001d4db  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001d4e0  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x18001d4e8  mov     rcx, r14; this
0x18001d4eb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001d4f0  test    eax, eax
0x18001d4f2  js      loc_18001D8CD
0x18001d4f8  mov     r15d, 8
0x18001d4fe  cmp     di, r15w
0x18001d502  jz      loc_18001D88A
0x18001d508  cmp     di, 11h
0x18001d50c  jz      loc_18001D697
0x18001d512  cmp     di, 13h
0x18001d516  jz      loc_18001D63E
0x18001d51c  mov     eax, 4008h
0x18001d521  cmp     di, ax
0x18001d524  jnz     loc_18001D8B2
0x18001d52a  lea     rax, [rsp+21D8h+String1]
0x18001d532  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d536  inc     rdi
0x18001d539  cmp     [rax+rdi*2], bx
0x18001d53d  jnz     short loc_18001D536
0x18001d53f  add     edi, 2
0x18001d542  mov     [rsp+21D8h+var_2158], rbx
0x18001d54a  movsxd  rcx, edi
0x18001d54d  mov     r14d, 2
0x18001d553  mov     edx, r14d
0x18001d556  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001d55b  cmp     rax, 100h
0x18001d561  jbe     short loc_18001D57D
0x18001d563  mov     rdx, rax
0x18001d566  lea     rcx, [rsp+21D8h+var_2158]
0x18001d56e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001d573  mov     rdi, [rsp+21D8h+var_2158]
0x18001d57b  jmp     short loc_18001D58D
0x18001d57d  lea     rdi, [rsp+21D8h+var_2150]
0x18001d585  mov     [rsp+21D8h+var_2158], rdi
0x18001d58d  jmp     short loc_18001D5B1
0x18001d58f  xor     ebx, ebx
0x18001d591  lea     r14d, [rbx+2]
0x18001d595  mov     rdi, [rsp+21D8h+var_2158]
0x18001d59d  mov     rax, [rsp+21D8h+var_2190]
0x18001d5a2  mov     [rsp+21D8h+var_21A0], rax
0x18001d5a7  mov     r12, [rsp+21D8h+var_2188]
0x18001d5ac  mov     r13, [rsp+21D8h+var_2178]
0x18001d5b1  test    rdi, rdi
0x18001d5b4  jz      short loc_18001D622
0x18001d5b6  lea     rsi, [rsp+21D8h+String1]
0x18001d5be  cmp     [rsp+21D8h+String1], bx
0x18001d5c6  jz      short loc_18001D605
0x18001d5c8  mov     r15d, 30h ; '0'
0x18001d5ce  mov     rcx, rsi; lpsz
0x18001d5d1  call    cs:__imp_CharNextW
0x18001d5d7  movzx   ecx, word ptr [rsi]
0x18001d5da  cmp     cx, 5Ch ; '\'
0x18001d5de  jnz     short loc_18001D5F7
0x18001d5e0  cmp     [rax], r15w
0x18001d5e4  jnz     short loc_18001D5F7
0x18001d5e6  mov     [rdi], bx
0x18001d5e9  mov     rcx, rax; lpsz
0x18001d5ec  call    cs:__imp_CharNextW
0x18001d5f2  mov     rsi, rax
0x18001d5f5  jmp     short loc_18001D5FD
0x18001d5f7  mov     [rdi], cx
0x18001d5fa  add     rsi, r14
0x18001d5fd  add     rdi, r14
0x18001d600  cmp     [rsi], bx
0x18001d603  jnz     short loc_18001D5CE
0x18001d605  mov     dword ptr [rdi], 0
0x18001d60b  mov     r8, [rsp+21D8h+var_2158]; unsigned __int16 *
0x18001d613  mov     rdx, r13; unsigned __int16 *
0x18001d616  mov     rcx, r12; this
0x18001d619  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x18001d61e  mov     edi, eax
0x18001d620  jmp     short loc_18001D627
0x18001d622  mov     edi, 0Eh
0x18001d627  lea     rcx, [rsp+21D8h+var_2158]
0x18001d62f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001d634  mov     r14, [rsp+21D8h+var_21A0]
0x18001d639  jmp     loc_18001D8A5
0x18001d63e  mov     [rsp+21D8h+pulOut], ebx
0x18001d642  mov     [rsp+21D8h+var_21A0], rbx
0x18001d647  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x18001d64c  xor     r8d, r8d; dwFlags
0x18001d64f  xor     edx, edx; lcid
0x18001d651  lea     rcx, [rsp+21D8h+String1]; strIn
0x18001d659  call    cs:__imp_VarUI4FromStr
0x18001d65f  mov     edi, eax
0x18001d661  test    eax, eax
0x18001d663  jns     short loc_18001D676
0x18001d665  lea     rcx, [rsp+21D8h+var_21A0]
0x18001d66a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001d66f  mov     eax, edi
0x18001d671  jmp     loc_18001D8CD
0x18001d676  mov     r8d, [rsp+21D8h+pulOut]; unsigned int
0x18001d67b  mov     rdx, r13; unsigned __int16 *
0x18001d67e  mov     rcx, r12; this
0x18001d681  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001d686  mov     edi, eax
0x18001d688  lea     rcx, [rsp+21D8h+var_21A0]
0x18001d68d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001d692  jmp     loc_18001D8A5
0x18001d697  lea     rax, [rsp+21D8h+String1]
0x18001d69f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001d6a3  inc     rdi
0x18001d6a6  cmp     [rax+rdi*2], bx
0x18001d6aa  jnz     short loc_18001D6A3
0x18001d6ac  mov     [rsp+21D8h+pulOut], edi
0x18001d6b0  test    dil, 1
0x18001d6b4  jz      short loc_18001D6C0
0x18001d6b6  mov     eax, 80004005h
0x18001d6bb  jmp     loc_18001D8CD
0x18001d6c0  mov     eax, edi
0x18001d6c2  cdq
0x18001d6c3  mov     r14d, 2
0x18001d6c9  idiv    r14d
0x18001d6cc  movsxd  r14, eax
0x18001d6cf  mov     [rsp+21D8h+var_2158], rbx
0x18001d6d7  mov     rsi, r14
0x18001d6da  mov     [rsp+21D8h+var_2168], r14
0x18001d6df  mov     edx, 1
0x18001d6e4  mov     rcx, r14
0x18001d6e7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001d6ec  cmp     rax, 100h
0x18001d6f2  jbe     short loc_18001D70E
0x18001d6f4  mov     rdx, rax
0x18001d6f7  lea     rcx, [rsp+21D8h+var_2158]
0x18001d6ff  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001d704  mov     rcx, [rsp+21D8h+var_2158]
0x18001d70c  jmp     short loc_18001D71E
0x18001d70e  lea     rcx, [rsp+21D8h+var_2150]
0x18001d716  mov     [rsp+21D8h+var_2158], rcx
0x18001d71e  jmp     short loc_18001D74A
0x18001d720  xor     ebx, ebx
0x18001d722  mov     edi, [rsp+21D8h+pulOut]
0x18001d726  mov     rcx, [rsp+21D8h+var_2158]; void *
0x18001d72e  mov     rsi, [rsp+21D8h+var_2168]
0x18001d733  mov     rax, [rsp+21D8h+var_2190]
0x18001d738  mov     [rsp+21D8h+var_21A0], rax
0x18001d73d  mov     r12, [rsp+21D8h+var_2188]
0x18001d742  mov     r13, [rsp+21D8h+var_2178]
0x18001d747  mov     r14d, esi
0x18001d74a  test    rcx, rcx
0x18001d74d  jnz     short loc_18001D761
0x18001d74f  lea     rcx, [rsp+21D8h+var_2158]
0x18001d757  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001d75c  jmp     loc_18001D6B6
0x18001d761  mov     r8, rsi; Size
0x18001d764  xor     edx, edx; Val
0x18001d766  call    memset_0
0x18001d76b  mov     r10d, ebx
0x18001d76e  test    edi, edi
0x18001d770  jle     loc_18001D84E
0x18001d776  mov     r15d, 30h ; '0'
0x18001d77c  mov     eax, r10d
0x18001d77f  movzx   edx, [rsp+rax*2+21D8h+String1]
0x18001d787  cmp     edx, 61h ; 'a'
0x18001d78a  ja      short loc_18001D7F9
0x18001d78c  jz      loc_18001D819
0x18001d792  cmp     edx, 38h ; '8'
0x18001d795  ja      short loc_18001D7CB
0x18001d797  jz      short loc_18001D7C3
0x18001d799  mov     ecx, edx
0x18001d79b  sub     ecx, r15d
0x18001d79e  jz      short loc_18001D7C3
0x18001d7a0  sub     ecx, 1
0x18001d7a3  jz      short loc_18001D7C3
0x18001d7a5  sub     ecx, 1
0x18001d7a8  jz      short loc_18001D7C3
0x18001d7aa  sub     ecx, 1
0x18001d7ad  jz      short loc_18001D7C3
0x18001d7af  sub     ecx, 1
0x18001d7b2  jz      short loc_18001D7C3
0x18001d7b4  sub     ecx, 1
0x18001d7b7  jz      short loc_18001D7C3
0x18001d7b9  sub     ecx, 1
0x18001d7bc  jz      short loc_18001D7C3
0x18001d7be  cmp     ecx, 1
0x18001d7c1  jnz     short loc_18001D814
0x18001d7c3  mov     r9d, edx
0x18001d7c6  sub     r9d, r15d
0x18001d7c9  jmp     short loc_18001D81D
0x18001d7cb  mov     r9d, edx
0x18001d7ce  mov     ecx, edx
0x18001d7d0  sub     ecx, 39h ; '9'
0x18001d7d3  jz      short loc_18001D7C3
0x18001d7d5  sub     ecx, 8
0x18001d7d8  jz      short loc_18001D7F3
0x18001d7da  sub     ecx, 1
0x18001d7dd  jz      short loc_18001D7F3
0x18001d7df  sub     ecx, 1
0x18001d7e2  jz      short loc_18001D7F3
0x18001d7e4  sub     ecx, 1
0x18001d7e7  jz      short loc_18001D7F3
0x18001d7e9  sub     ecx, 1
0x18001d7ec  jz      short loc_18001D7F3
0x18001d7ee  cmp     ecx, 1
0x18001d7f1  jnz     short loc_18001D814
0x18001d7f3  add     r9d, 0FFFFFFC9h
0x18001d7f7  jmp     short loc_18001D81D
0x18001d7f9  mov     ecx, edx
0x18001d7fb  sub     ecx, 62h ; 'b'
0x18001d7fe  jz      short loc_18001D819
0x18001d800  sub     ecx, 1
0x18001d803  jz      short loc_18001D819
0x18001d805  sub     ecx, 1
0x18001d808  jz      short loc_18001D819
0x18001d80a  sub     ecx, 1
0x18001d80d  jz      short loc_18001D819
0x18001d80f  cmp     ecx, 1
0x18001d812  jz      short loc_18001D819
0x18001d814  mov     r9d, ebx
0x18001d817  jmp     short loc_18001D81D
0x18001d819  lea     r9d, [rdx-57h]
0x18001d81d  mov     r8d, r10d
0x18001d820  shr     r8, 1
0x18001d823  mov     rdx, [rsp+21D8h+var_2158]
0x18001d82b  mov     eax, r10d
0x18001d82e  and     eax, 1
0x18001d831  shl     eax, 2
0x18001d834  mov     ecx, 4
0x18001d839  sub     ecx, eax
0x18001d83b  shl     r9b, cl
0x18001d83e  or      [r8+rdx], r9b
0x18001d842  inc     r10d
0x18001d845  cmp     r10d, edi
0x18001d848  jl      loc_18001D77C
0x18001d84e  mov     rax, [rsp+21D8h+var_2158]
0x18001d856  mov     [rsp+21D8h+cbData], r14d; cbData
0x18001d85b  mov     [rsp+21D8h+lpData], rax; lpData
0x18001d860  mov     r9d, 3; dwType
0x18001d866  xor     r8d, r8d; Reserved
0x18001d869  mov     rdx, r13; lpValueName
0x18001d86c  mov     rcx, [r12]; hKey
0x18001d870  call    cs:__imp_RegSetValueExW
0x18001d876  mov     edi, eax
0x18001d878  lea     rcx, [rsp+21D8h+var_2158]
0x18001d880  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001d885  jmp     loc_18001D634
0x18001d88a  mov     r9d, 1; unsigned int
0x18001d890  lea     r8, [rsp+21D8h+String1]; unsigned __int16 *
0x18001d898  mov     rdx, r13; unsigned __int16 *
0x18001d89b  mov     rcx, r12; this
0x18001d89e  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18001d8a3  mov     edi, eax
0x18001d8a5  test    edi, edi
0x18001d8a7  jz      short loc_18001D8B2
0x18001d8a9  mov     ecx, edi; unsigned int
0x18001d8ab  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001d8b0  jmp     short loc_18001D8CD
0x18001d8b2  mov     rdx, [rsp+21D8h+var_2160]; unsigned __int16 *
0x18001d8b7  mov     rcx, r14; this
0x18001d8ba  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001d8bf  test    eax, eax
0x18001d8c1  cmovs   ebx, eax
0x18001d8c4  mov     eax, ebx
0x18001d8c6  jmp     short loc_18001D8CD
0x18001d8c8  mov     eax, 80020009h
0x18001d8cd  mov     rcx, [rsp+21D8h+var_48]
0x18001d8d5  xor     rcx, rsp; StackCookie
  ... truncated ...
```
