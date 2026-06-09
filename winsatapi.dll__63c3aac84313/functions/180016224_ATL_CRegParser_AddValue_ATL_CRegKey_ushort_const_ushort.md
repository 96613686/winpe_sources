# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180016224`
- end: `0x180016790`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1388`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18001a0e0`

## callees

- `0x1800151bb`
- `0x1800151ec`
- `0x180015290`
- `0x1800157e0`
- `0x180016224`
- `0x180016798`
- `0x180016a8c`
- `0x1800171e0`
- `0x180019370`
- `0x18001aaf4`
- `0x18001abbc`
- `0x18002dec0`
- `0x18002df80`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800164be`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800164be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016472`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800166e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001673a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016472`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800166e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001673a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800163ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016409`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800163ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016409`
- `KERNEL32!lstrcmpiW` at `0x1800162cb`
- `KERNEL32!lstrcmpiW` at `0x1800162cb`

## pseudocode

```c
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
  LPCWSTR lpValueName; // [rsp+40h] [rbp-21A8h]
  HKEY *v37; // [rsp+48h] [rbp-21A0h]
  HKEY *v38; // [rsp+50h] [rbp-2198h]
  ATL::CRegParser *v39; // [rsp+58h] [rbp-2190h]
  const WCHAR *v40; // [rsp+60h] [rbp-2188h]
  size_t v41; // [rsp+70h] [rbp-2178h]
  HKEY *v42; // [rsp+78h] [rbp-2170h]
  unsigned __int16 *v43; // [rsp+80h] [rbp-2168h]
  __int64 v44; // [rsp+88h] [rbp-2160h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  v44 = -2;
  lpValueName = a3;
  v38 = a2;
  v6 = this;
  v35 = this;
  v37 = a2;
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
      pulOut = v23;
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
          v27 = v46;
          lpData = v46;
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
        LODWORD(v23) = pulOut;
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
        v21 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)a2, a3, pulOut);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
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
          v13 = v46;
          lpData = v46;
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
        v14 = v37;
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
0x180016224  push    rbx
0x180016226  push    rsi
0x180016227  push    rdi
0x180016228  push    r12
0x18001622a  push    r13
0x18001622c  push    r14
0x18001622e  push    r15
0x180016230  mov     eax, 21B0h
0x180016235  call    _alloca_probe
0x18001623a  sub     rsp, rax
0x18001623d  mov     [rsp+21E8h+var_2160], 0FFFFFFFFFFFFFFFEh
0x180016249  mov     rax, cs:__security_cookie
0x180016250  xor     rax, rsp
0x180016253  mov     [rsp+21E8h+var_48], rax
0x18001625b  mov     r14, r8
0x18001625e  mov     [rsp+21E8h+lpValueName], r8
0x180016263  mov     r12, rdx
0x180016266  mov     [rsp+21E8h+var_2198], rdx
0x18001626b  mov     r15, rcx
0x18001626e  mov     [rsp+21E8h+var_21B0], rcx
0x180016273  mov     [rsp+21E8h+var_21A0], rdx
0x180016278  mov     [rsp+21E8h+var_2190], rcx
0x18001627d  mov     [rsp+21E8h+var_2170], rdx
0x180016282  mov     [rsp+21E8h+var_2188], r8
0x180016287  mov     [rsp+21E8h+var_2168], r9
0x18001628f  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180016297  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001629c  xor     ebx, ebx
0x18001629e  test    eax, eax
0x1800162a0  js      loc_18001676D
0x1800162a6  mov     edi, ebx
0x1800162a8  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800162af  cmp     edi, 4
0x1800162b2  jnb     loc_180016768
0x1800162b8  movsxd  rsi, edi
0x1800162bb  add     rsi, rsi
0x1800162be  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800162c3  lea     rcx, [rsp+21E8h+String1]; lpString1
0x1800162cb  call    cs:__imp_lstrcmpiW
0x1800162d1  test    eax, eax
0x1800162d3  jz      short loc_1800162D9
0x1800162d5  inc     edi
0x1800162d7  jmp     short loc_1800162AF
0x1800162d9  movzx   edi, word ptr [r13+rsi*8+8]
0x1800162df  mov     rcx, r15; this
0x1800162e2  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800162e7  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x1800162ef  mov     rcx, r15; this
0x1800162f2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800162f7  test    eax, eax
0x1800162f9  js      loc_18001676D
0x1800162ff  mov     r13d, 8
0x180016305  cmp     di, r13w
0x180016309  jz      loc_1800166FD
0x18001630f  cmp     di, 11h
0x180016313  jz      loc_1800164FC
0x180016319  cmp     di, 13h
0x18001631d  jz      loc_1800164A3
0x180016323  mov     eax, 4008h
0x180016328  cmp     di, ax
0x18001632b  jnz     loc_18001674F
0x180016331  lea     rcx, [rsp+21E8h+String1]
0x180016339  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001633d  mov     rax, rsi
0x180016340  inc     rax
0x180016343  cmp     [rcx+rax*2], bx
0x180016347  jnz     short loc_180016340
0x180016349  add     eax, 2
0x18001634c  mov     [rsp+21E8h+var_2158], rbx
0x180016354  movsxd  rcx, eax
0x180016357  mov     r15d, 2
0x18001635d  mov     edx, r15d
0x180016360  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180016365  cmp     rax, 100h
0x18001636b  jbe     short loc_180016387
0x18001636d  mov     rdx, rax
0x180016370  lea     rcx, [rsp+21E8h+var_2158]
0x180016378  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001637d  mov     rdi, [rsp+21E8h+var_2158]
0x180016385  jmp     short loc_180016397
0x180016387  lea     rdi, [rsp+21E8h+var_2150]
0x18001638f  mov     [rsp+21E8h+var_2158], rdi
0x180016397  mov     r13, [rsp+21E8h+var_2198]
0x18001639c  jmp     short loc_1800163C9
0x18001639e  xor     ebx, ebx
0x1800163a0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800163a4  lea     r15d, [rbx+2]
0x1800163a8  mov     rdi, [rsp+21E8h+var_2158]
0x1800163b0  mov     r13, [rsp+21E8h+var_21A0]
0x1800163b5  mov     rax, [rsp+21E8h+var_2190]
0x1800163ba  mov     [rsp+21E8h+var_21B0], rax
0x1800163bf  mov     rax, [rsp+21E8h+var_2188]
0x1800163c4  mov     [rsp+21E8h+lpValueName], rax
0x1800163c9  test    rdi, rdi
0x1800163cc  jz      loc_180016487
0x1800163d2  lea     r14, [rsp+21E8h+String1]
0x1800163da  cmp     [rsp+21E8h+String1], bx
0x1800163e2  jz      short loc_180016423
0x1800163e4  mov     r12d, 30h ; '0'
0x1800163ea  mov     rcx, r14; lpsz
0x1800163ed  call    cs:__imp_CharNextW
0x1800163f3  movzx   ecx, word ptr [r14]
0x1800163f7  cmp     cx, 5Ch ; '\'
0x1800163fb  jnz     short loc_180016414
0x1800163fd  cmp     [rax], r12w
0x180016401  jnz     short loc_180016414
0x180016403  mov     [rdi], bx
0x180016406  mov     rcx, rax; lpsz
0x180016409  call    cs:__imp_CharNextW
0x18001640f  mov     r14, rax
0x180016412  jmp     short loc_18001641A
0x180016414  mov     [rdi], cx
0x180016417  add     r14, r15
0x18001641a  add     rdi, r15
0x18001641d  cmp     [r14], bx
0x180016421  jnz     short loc_1800163EA
0x180016423  mov     dword ptr [rdi], 0
0x180016429  mov     r8, [rsp+21E8h+var_2158]
0x180016431  test    r8, r8
0x180016434  jz      short loc_18001647C
0x180016436  mov     r10d, ebx
0x180016439  mov     r9, r8
0x18001643c  mov     rcx, rsi
0x18001643f  inc     rcx
0x180016442  cmp     [r9+rcx*2], bx
0x180016447  jnz     short loc_18001643F
0x180016449  inc     ecx
0x18001644b  lea     r9, [r9+rcx*2]
0x18001644f  lea     r10d, [r10+rcx*2]
0x180016453  cmp     ecx, 1
0x180016456  jnz     short loc_18001643C
0x180016458  mov     [rsp+21E8h+cbData], r10d; cbData
0x18001645d  mov     [rsp+21E8h+lpData], r8; lpData
0x180016462  lea     r9d, [rcx+6]; dwType
0x180016466  xor     r8d, r8d; Reserved
0x180016469  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18001646e  mov     rcx, [r13+0]; hKey
0x180016472  call    cs:__imp_RegSetValueExW
0x180016478  mov     edi, eax
0x18001647a  jmp     short loc_18001648C
0x18001647c  mov     ecx, 80004005h; int
0x180016481  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180016487  mov     edi, 0Eh
0x18001648c  lea     rcx, [rsp+21E8h+var_2158]
0x180016494  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180016499  mov     r15, [rsp+21E8h+var_21B0]
0x18001649e  jmp     loc_180016742
0x1800164a3  mov     [rsp+21E8h+pulOut], ebx
0x1800164a7  mov     [rsp+21E8h+var_21B0], rbx
0x1800164ac  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x1800164b1  xor     r8d, r8d; dwFlags
0x1800164b4  xor     edx, edx; lcid
0x1800164b6  lea     rcx, [rsp+21E8h+String1]; strIn
0x1800164be  call    cs:__imp_VarUI4FromStr
0x1800164c4  mov     edi, eax
0x1800164c6  test    eax, eax
0x1800164c8  jns     short loc_1800164DB
0x1800164ca  lea     rcx, [rsp+21E8h+var_21B0]
0x1800164cf  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800164d4  mov     eax, edi
0x1800164d6  jmp     loc_18001676D
0x1800164db  mov     r8d, [rsp+21E8h+pulOut]; unsigned int
0x1800164e0  mov     rdx, r14; unsigned __int16 *
0x1800164e3  mov     rcx, r12; this
0x1800164e6  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800164eb  mov     edi, eax
0x1800164ed  lea     rcx, [rsp+21E8h+var_21B0]
0x1800164f2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800164f7  jmp     loc_180016742
0x1800164fc  lea     rax, [rsp+21E8h+String1]
0x180016504  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016508  inc     rsi
0x18001650b  cmp     [rax+rsi*2], bx
0x18001650f  jnz     short loc_180016508
0x180016511  mov     [rsp+21E8h+pulOut], esi
0x180016515  test    sil, 1
0x180016519  jz      short loc_180016525
0x18001651b  mov     eax, 80004005h
0x180016520  jmp     loc_18001676D
0x180016525  mov     eax, esi
0x180016527  cdq
0x180016528  mov     r15d, 2
0x18001652e  idiv    r15d
0x180016531  movsxd  r14, eax
0x180016534  mov     [rsp+21E8h+var_2158], rbx
0x18001653c  mov     rdi, r14
0x18001653f  mov     [rsp+21E8h+var_2178], r14
0x180016544  lea     edx, [r15-1]
0x180016548  mov     rcx, r14
0x18001654b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180016550  cmp     rax, 100h
0x180016556  jbe     short loc_180016572
0x180016558  mov     rdx, rax
0x18001655b  lea     rcx, [rsp+21E8h+var_2158]
0x180016563  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180016568  mov     rcx, [rsp+21E8h+var_2158]
0x180016570  jmp     short loc_180016582
0x180016572  lea     rcx, [rsp+21E8h+var_2150]
0x18001657a  mov     [rsp+21E8h+var_2158], rcx
0x180016582  mov     r15, [rsp+21E8h+var_2198]
0x180016587  jmp     short loc_1800165BC
0x180016589  xor     ebx, ebx
0x18001658b  lea     r13d, [rbx+8]
0x18001658f  mov     esi, [rsp+21E8h+pulOut]
0x180016593  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18001659b  mov     rdi, [rsp+21E8h+var_2178]
0x1800165a0  mov     rax, [rsp+21E8h+var_2190]
0x1800165a5  mov     [rsp+21E8h+var_21B0], rax
0x1800165aa  mov     r15, [rsp+21E8h+var_2170]
0x1800165af  mov     rax, [rsp+21E8h+var_2188]
0x1800165b4  mov     [rsp+21E8h+lpValueName], rax
0x1800165b9  mov     r14d, edi
0x1800165bc  test    rcx, rcx
0x1800165bf  jnz     short loc_1800165D3
0x1800165c1  lea     rcx, [rsp+21E8h+var_2158]
0x1800165c9  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800165ce  jmp     loc_18001651B
0x1800165d3  mov     r8, rdi; Size
0x1800165d6  xor     edx, edx; Val
0x1800165d8  call    memset_0
0x1800165dd  mov     r10d, ebx
0x1800165e0  test    esi, esi
0x1800165e2  jle     loc_1800166C0
0x1800165e8  mov     r12d, 30h ; '0'
0x1800165ee  mov     eax, r10d
0x1800165f1  movzx   edx, [rsp+rax*2+21E8h+String1]
0x1800165f9  cmp     edx, 61h ; 'a'
0x1800165fc  ja      short loc_18001666B
0x1800165fe  jz      loc_18001668B
0x180016604  cmp     edx, 38h ; '8'
0x180016607  ja      short loc_18001663D
0x180016609  jz      short loc_180016635
0x18001660b  mov     ecx, edx
0x18001660d  sub     ecx, r12d
0x180016610  jz      short loc_180016635
0x180016612  sub     ecx, 1
0x180016615  jz      short loc_180016635
0x180016617  sub     ecx, 1
0x18001661a  jz      short loc_180016635
0x18001661c  sub     ecx, 1
0x18001661f  jz      short loc_180016635
0x180016621  sub     ecx, 1
0x180016624  jz      short loc_180016635
0x180016626  sub     ecx, 1
0x180016629  jz      short loc_180016635
0x18001662b  sub     ecx, 1
0x18001662e  jz      short loc_180016635
0x180016630  cmp     ecx, 1
0x180016633  jnz     short loc_180016686
0x180016635  mov     r9d, edx
0x180016638  sub     r9d, r12d
0x18001663b  jmp     short loc_18001668F
0x18001663d  mov     r9d, edx
0x180016640  mov     ecx, edx
0x180016642  sub     ecx, 39h ; '9'
0x180016645  jz      short loc_180016635
0x180016647  sub     ecx, r13d
0x18001664a  jz      short loc_180016665
0x18001664c  sub     ecx, 1
0x18001664f  jz      short loc_180016665
0x180016651  sub     ecx, 1
0x180016654  jz      short loc_180016665
0x180016656  sub     ecx, 1
0x180016659  jz      short loc_180016665
0x18001665b  sub     ecx, 1
0x18001665e  jz      short loc_180016665
0x180016660  cmp     ecx, 1
0x180016663  jnz     short loc_180016686
0x180016665  add     r9d, 0FFFFFFC9h
0x180016669  jmp     short loc_18001668F
0x18001666b  mov     ecx, edx
0x18001666d  sub     ecx, 62h ; 'b'
0x180016670  jz      short loc_18001668B
0x180016672  sub     ecx, 1
0x180016675  jz      short loc_18001668B
0x180016677  sub     ecx, 1
0x18001667a  jz      short loc_18001668B
0x18001667c  sub     ecx, 1
0x18001667f  jz      short loc_18001668B
0x180016681  cmp     ecx, 1
0x180016684  jz      short loc_18001668B
0x180016686  mov     r9d, ebx
0x180016689  jmp     short loc_18001668F
0x18001668b  lea     r9d, [rdx-57h]
0x18001668f  mov     r8d, r10d
0x180016692  shr     r8, 1
0x180016695  mov     rdx, [rsp+21E8h+var_2158]
0x18001669d  mov     eax, r10d
0x1800166a0  and     eax, 1
0x1800166a3  shl     eax, 2
0x1800166a6  mov     ecx, 4
0x1800166ab  sub     ecx, eax
0x1800166ad  shl     r9b, cl
0x1800166b0  or      [r8+rdx], r9b
0x1800166b4  inc     r10d
0x1800166b7  cmp     r10d, esi
0x1800166ba  jl      loc_1800165EE
0x1800166c0  mov     rax, [rsp+21E8h+var_2158]
0x1800166c8  mov     [rsp+21E8h+cbData], r14d; cbData
0x1800166cd  mov     [rsp+21E8h+lpData], rax; lpData
  ... truncated ...
```
