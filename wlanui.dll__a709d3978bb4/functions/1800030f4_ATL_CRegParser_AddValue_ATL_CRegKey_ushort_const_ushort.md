# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800030f4`
- end: `0x1800035f0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800049ec`

## callees

- `0x1800030f4`
- `0x1800035f8`
- `0x180003858`
- `0x180003870`
- `0x180003da4`
- `0x180003fe0`
- `0x18001bf0a`
- `0x18001bf40`
- `0x18001c000`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000316d`
- `KERNEL32!lstrcmpiW` at `0x18000316d`
- `USER32!CharNextW` at `0x1800031bd`
- `USER32!CharNextW` at `0x18000328d`
- `USER32!CharNextW` at `0x1800032a9`
- `USER32!CharNextW` at `0x1800031bd`
- `USER32!CharNextW` at `0x18000328d`
- `USER32!CharNextW` at `0x1800032a9`
- `ADVAPI32!RegSetValueExW` at `0x18000331a`
- `ADVAPI32!RegSetValueExW` at `0x180003393`
- `ADVAPI32!RegSetValueExW` at `0x180003535`
- `ADVAPI32!RegSetValueExW` at `0x18000331a`
- `ADVAPI32!RegSetValueExW` at `0x180003393`
- `ADVAPI32!RegSetValueExW` at `0x180003535`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000335d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000335d`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v5; // r15
  const WCHAR *v6; // r14
  HRESULT result; // eax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // eax
  LSTATUS v21; // edi
  LSTATUS v22; // eax
  __int64 v23; // rsi
  size_t v24; // rbx
  BYTE *v25; // rcx
  int v26; // r10d
  unsigned int v27; // r9d
  char v28; // r9
  unsigned __int64 v29; // r8
  char v30; // r9
  __int64 v31; // rdi
  int Token; // eax
  int v33; // ecx
  ULONG pulOut[2]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE *v36; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[264]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE *lpData; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v39[264]; // [rsp+158h] [rbp+58h] BYREF
  OLECHAR String1[4096]; // [rsp+260h] [rbp+160h] BYREF

  *(_QWORD *)Data = a4;
  *(_QWORD *)pulOut = a3;
  v5 = a4;
  v6 = a3;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( result < 0 )
    return result;
  v9 = 0;
  while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
  {
    if ( (unsigned int)++v9 >= 4 )
      return -2147352567;
  }
  v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
  while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
    *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  result = ATL::CRegParser::NextToken(this, String1);
  if ( result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v31 = -1;
    do
      ++v31;
    while ( String1[v31] );
    v22 = RegSetValueExW(*a2, v6, 0, 1u, (const BYTE *)String1, 2 * v31 + 2);
    goto LABEL_43;
  }
  if ( v10 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    if ( (v23 & 1) != 0 )
      return -2147467259;
    v36 = 0;
    v24 = (int)v23 / 2;
    if ( !((int)v23 / 2) )
      goto LABEL_51;
    if ( !(0xFFFFFFFFFFFFFFFFuLL / v24) )
      ATL::AtlThrowImpl(-2147024809);
    if ( v24 > 0x100 )
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v36, v24);
      v25 = v36;
    }
    else
    {
LABEL_51:
      v25 = v37;
      v36 = v37;
    }
    if ( !v25 )
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
      return -2147467259;
    }
    memset_0(v25, 0, v24);
    v26 = 0;
    if ( (int)v23 <= 0 )
      goto LABEL_83;
    while ( 1 )
    {
      v27 = String1[v26];
      if ( v27 > 0x61 )
      {
        if ( v27 == 98 || v27 == 99 || v27 == 100 || v27 - 101 < 2 )
        {
LABEL_80:
          v28 = v27 - 87;
          goto LABEL_81;
        }
LABEL_79:
        v28 = 0;
        goto LABEL_81;
      }
      if ( v27 == 97 )
        goto LABEL_80;
      if ( v27 <= 0x38 )
        break;
      if ( v27 == 57 )
        goto LABEL_67;
      if ( v27 != 65 && v27 != 66 && v27 != 67 && v27 != 68 && v27 - 69 > 1 )
        goto LABEL_79;
      v28 = v27 - 55;
LABEL_81:
      v29 = (unsigned __int64)(unsigned int)v26 >> 1;
      v30 = v28 << (4 - 4 * (v26++ & 1));
      v36[v29] |= v30;
      if ( v26 >= (int)v23 )
      {
        v6 = *(const WCHAR **)pulOut;
LABEL_83:
        v21 = RegSetValueExW(*a2, v6, 0, 3u, v36, (int)v23 / 2);
        if ( v36 != v37 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
        v5 = *(unsigned __int16 **)Data;
LABEL_86:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
LABEL_91:
        Token = ATL::CRegParser::NextToken(this, v5);
        v33 = 0;
        if ( Token < 0 )
          return Token;
        return v33;
      }
    }
    if ( v27 != 56 && v27 != 48 && v27 != 49 && v27 != 50 && v27 != 51 && v27 != 52 && v27 != 53 && v27 - 54 > 1 )
      goto LABEL_79;
LABEL_67:
    v28 = v27 - 48;
    goto LABEL_81;
  }
  if ( v10 != 19 )
  {
    if ( v10 == 16392 )
    {
      lpData = 0;
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      v12 = (int)v11 + 2;
      if ( (_DWORD)v11 == -2 )
        goto LABEL_23;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * v12 <= 0x100 )
      {
LABEL_23:
        v13 = v39;
        lpData = v39;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2 * v12);
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
          v6 = *(const WCHAR **)pulOut;
          v5 = *(unsigned __int16 **)Data;
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
        v20 = RegSetValueExW(*a2, v6, 0, 7u, lpData, cbData);
        v13 = lpData;
        v21 = v20;
      }
      else
      {
        v21 = 14;
      }
      if ( v13 != v39 )
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
      goto LABEL_86;
    }
    goto LABEL_91;
  }
  pulOut[0] = 0;
  result = VarUI4FromStr(String1, 0, 0, pulOut);
  if ( result >= 0 )
  {
    *(_DWORD *)Data = pulOut[0];
    v22 = RegSetValueExW(*a2, v6, 0, 4u, Data, 4u);
LABEL_43:
    v21 = v22;
    goto LABEL_86;
  }
  return result;
}

```

## disassembly

```asm
0x1800030f4  push    rbp
0x1800030f6  push    rbx
0x1800030f7  push    rsi
0x1800030f8  push    rdi
0x1800030f9  push    r12
0x1800030fb  push    r13
0x1800030fd  push    r14
0x1800030ff  push    r15
0x180003101  lea     rbp, [rsp-2178h]
0x180003109  mov     eax, 2278h
0x18000310e  call    _alloca_probe
0x180003113  sub     rsp, rax
0x180003116  mov     rax, cs:__security_cookie
0x18000311d  xor     rax, rsp
0x180003120  mov     [rbp+21B0h+var_50], rax
0x180003127  mov     r13, rdx
0x18000312a  mov     qword ptr [rsp+22B0h+Data], r9
0x18000312f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180003136  mov     qword ptr [rsp+22B0h+pulOut], r8
0x18000313b  mov     r15, r9
0x18000313e  mov     r14, r8
0x180003141  mov     r12, rcx
0x180003144  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003149  xor     esi, esi
0x18000314b  test    eax, eax
0x18000314d  js      loc_1800035AC
0x180003153  mov     ebx, esi
0x180003155  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000315c  movsxd  rdi, ebx
0x18000315f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x180003166  add     rdi, rdi
0x180003169  mov     rdx, [rax+rdi*8]; lpString2
0x18000316d  call    cs:__imp_lstrcmpiW
0x180003173  test    eax, eax
0x180003175  jz      short loc_18000318F
0x180003177  inc     ebx
0x180003179  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003180  cmp     ebx, 4
0x180003183  jb      short loc_18000315C
0x180003185  mov     eax, 80020009h
0x18000318a  jmp     loc_1800035AC
0x18000318f  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003196  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18000319b  mov     edi, 13h
0x1800031a0  mov     rdx, [r12]
0x1800031a4  movzx   ecx, word ptr [rdx]
0x1800031a7  sub     ecx, 9
0x1800031aa  jz      short loc_1800031BA
0x1800031ac  sub     ecx, 1
0x1800031af  jz      short loc_1800031BA
0x1800031b1  sub     ecx, 3
0x1800031b4  jz      short loc_1800031BA
0x1800031b6  cmp     ecx, edi
0x1800031b8  jnz     short loc_1800031C9
0x1800031ba  mov     rcx, rdx; lpsz
0x1800031bd  call    cs:__imp_CharNextW
0x1800031c3  mov     [r12], rax
0x1800031c7  jmp     short loc_1800031A0
0x1800031c9  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x1800031d0  mov     rcx, r12; this
0x1800031d3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800031d8  test    eax, eax
0x1800031da  js      loc_1800035AC
0x1800031e0  mov     eax, 8
0x1800031e5  cmp     bx, ax
0x1800031e8  jz      loc_180003567
0x1800031ee  cmp     bx, 11h
0x1800031f2  jz      loc_1800033A0
0x1800031f8  cmp     bx, di
0x1800031fb  jz      loc_180003348
0x180003201  mov     eax, 4008h
0x180003206  cmp     bx, ax
0x180003209  jnz     loc_180003598
0x18000320f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003213  mov     [rbp+21B0h+var_2160], rsi
0x180003217  mov     rax, rdi
0x18000321a  lea     rcx, [rbp+21B0h+String1]
0x180003221  inc     rax
0x180003224  cmp     [rcx+rax*2], si
0x180003228  jnz     short loc_180003221
0x18000322a  add     eax, 2
0x18000322d  movsxd  rcx, eax
0x180003230  jz      short loc_180003260
0x180003232  xor     edx, edx
0x180003234  mov     rax, rdi
0x180003237  div     rcx
0x18000323a  cmp     rax, 2
0x18000323e  jb      loc_1800035DA
0x180003244  lea     rdx, [rcx+rcx]
0x180003248  cmp     rdx, 100h
0x18000324f  jbe     short loc_180003260
0x180003251  lea     rcx, [rbp+21B0h+var_2160]
0x180003255  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000325a  mov     rbx, [rbp+21B0h+var_2160]
0x18000325e  jmp     short loc_180003268
0x180003260  lea     rbx, [rbp+21B0h+var_2158]
0x180003264  mov     [rbp+21B0h+var_2160], rbx
0x180003268  test    rbx, rbx
0x18000326b  jz      loc_180003328
0x180003271  xor     eax, eax
0x180003273  lea     rsi, [rbp+21B0h+String1]
0x18000327a  cmp     [rbp+21B0h+String1], ax
0x180003281  jz      short loc_1800032CF
0x180003283  lea     r14d, [rax+30h]
0x180003287  xor     r15d, r15d
0x18000328a  mov     rcx, rsi; lpsz
0x18000328d  call    cs:__imp_CharNextW
0x180003293  movzx   ecx, word ptr [rsi]
0x180003296  cmp     cx, 5Ch ; '\'
0x18000329a  jnz     short loc_1800032B4
0x18000329c  cmp     [rax], r14w
0x1800032a0  jnz     short loc_1800032B4
0x1800032a2  mov     rcx, rax; lpsz
0x1800032a5  mov     [rbx], r15w
0x1800032a9  call    cs:__imp_CharNextW
0x1800032af  mov     rsi, rax
0x1800032b2  jmp     short loc_1800032BB
0x1800032b4  mov     [rbx], cx
0x1800032b7  add     rsi, 2
0x1800032bb  add     rbx, 2
0x1800032bf  cmp     [rsi], r15w
0x1800032c3  jnz     short loc_18000328A
0x1800032c5  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x1800032ca  mov     r15, qword ptr [rsp+22B0h+Data]
0x1800032cf  xor     esi, esi
0x1800032d1  mov     [rbx], esi
0x1800032d3  mov     r8, [rbp+21B0h+var_2160]
0x1800032d7  test    r8, r8
0x1800032da  jz      loc_1800035E5
0x1800032e0  mov     r10d, esi
0x1800032e3  mov     r9, r8
0x1800032e6  mov     rcx, rdi
0x1800032e9  inc     rcx
0x1800032ec  cmp     [r9+rcx*2], si
0x1800032f1  jnz     short loc_1800032E9
0x1800032f3  inc     ecx
0x1800032f5  lea     r9, [r9+rcx*2]
0x1800032f9  lea     r10d, [r10+rcx*2]
0x1800032fd  cmp     ecx, 1
0x180003300  jnz     short loc_1800032E6
0x180003302  mov     [rsp+22B0h+cbData], r10d; cbData
0x180003307  lea     r9d, [rcx+6]; dwType
0x18000330b  mov     rcx, [r13+0]; hKey
0x18000330f  mov     rdx, r14; lpValueName
0x180003312  mov     [rsp+22B0h+lpData], r8; lpData
0x180003317  xor     r8d, r8d; Reserved
0x18000331a  call    cs:__imp_RegSetValueExW
0x180003320  mov     rbx, [rbp+21B0h+var_2160]
0x180003324  mov     edi, eax
0x180003326  jmp     short loc_18000332D
0x180003328  mov     edi, 0Eh
0x18000332d  lea     rax, [rbp+21B0h+var_2158]
0x180003331  cmp     rbx, rax
0x180003334  jz      loc_18000355A
0x18000333a  lea     rcx, [rbp+21B0h+var_2160]
0x18000333e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003343  jmp     loc_18000355A
0x180003348  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x18000334d  mov     [rsp+22B0h+pulOut], esi
0x180003351  xor     r8d, r8d; dwFlags
0x180003354  lea     rcx, [rbp+21B0h+String1]; strIn
0x18000335b  xor     edx, edx; lcid
0x18000335d  call    cs:__imp_VarUI4FromStr
0x180003363  test    eax, eax
0x180003365  js      loc_1800035AC
0x18000336b  mov     eax, [rsp+22B0h+pulOut]
0x18000336f  mov     ecx, 4
0x180003374  mov     dword ptr [rsp+22B0h+Data], eax
0x180003378  mov     r9d, ecx; dwType
0x18000337b  mov     [rsp+22B0h+cbData], ecx; cbData
0x18000337f  lea     rax, [rsp+22B0h+Data]
0x180003384  mov     rcx, [r13+0]; hKey
0x180003388  xor     r8d, r8d; Reserved
0x18000338b  mov     rdx, r14; lpValueName
0x18000338e  mov     [rsp+22B0h+lpData], rax; lpData
0x180003393  call    cs:__imp_RegSetValueExW
0x180003399  mov     edi, eax
0x18000339b  jmp     loc_18000355A
0x1800033a0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800033a4  lea     rax, [rbp+21B0h+String1]
0x1800033ab  mov     rsi, rdi
0x1800033ae  xor     ecx, ecx
0x1800033b0  inc     rsi
0x1800033b3  cmp     [rax+rsi*2], cx
0x1800033b7  jnz     short loc_1800033B0
0x1800033b9  test    sil, 1
0x1800033bd  jnz     short loc_18000341D
0x1800033bf  mov     eax, esi
0x1800033c1  mov     [rsp+22B0h+var_2270], rcx
0x1800033c6  cdq
0x1800033c7  sub     eax, edx
0x1800033c9  sar     eax, 1
0x1800033cb  movsxd  r15, eax
0x1800033ce  mov     rbx, r15
0x1800033d1  jz      short loc_180003402
0x1800033d3  xor     edx, edx
0x1800033d5  mov     rax, rdi
0x1800033d8  div     rbx
0x1800033db  cmp     rax, 1
0x1800033df  jb      loc_1800035CF
0x1800033e5  cmp     rbx, 100h
0x1800033ec  jbe     short loc_180003402
0x1800033ee  mov     rdx, rbx
0x1800033f1  lea     rcx, [rsp+22B0h+var_2270]
0x1800033f6  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800033fb  mov     rcx, [rsp+22B0h+var_2270]
0x180003400  jmp     short loc_18000340C
0x180003402  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180003407  mov     [rsp+22B0h+var_2270], rcx
0x18000340c  xor     edi, edi
0x18000340e  test    rcx, rcx
0x180003411  jnz     short loc_180003427
0x180003413  lea     rcx, [rsp+22B0h+var_2270]
0x180003418  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000341d  mov     eax, 80004005h
0x180003422  jmp     loc_1800035AC
0x180003427  mov     r8, rbx; Size
0x18000342a  xor     edx, edx; Val
0x18000342c  call    memset_0
0x180003431  mov     r10d, edi
0x180003434  test    esi, esi
0x180003436  jle     loc_180003516
0x18000343c  mov     r14d, 30h ; '0'
0x180003442  mov     eax, r10d
0x180003445  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x18000344e  cmp     r9d, 61h ; 'a'
0x180003452  ja      short loc_1800034BE
0x180003454  jz      loc_1800034DF
0x18000345a  cmp     r9d, 38h ; '8'
0x18000345e  ja      short loc_180003492
0x180003460  jz      short loc_18000348D
0x180003462  mov     ecx, r9d
0x180003465  sub     ecx, r14d
0x180003468  jz      short loc_18000348D
0x18000346a  sub     ecx, 1
0x18000346d  jz      short loc_18000348D
0x18000346f  sub     ecx, 1
0x180003472  jz      short loc_18000348D
0x180003474  sub     ecx, 1
0x180003477  jz      short loc_18000348D
0x180003479  sub     ecx, 1
0x18000347c  jz      short loc_18000348D
0x18000347e  sub     ecx, 1
0x180003481  jz      short loc_18000348D
0x180003483  sub     ecx, 1
0x180003486  jz      short loc_18000348D
0x180003488  cmp     ecx, 1
0x18000348b  jnz     short loc_1800034DA
0x18000348d  sub     r9b, r14b
0x180003490  jmp     short loc_1800034E3
0x180003492  mov     ecx, r9d
0x180003495  sub     ecx, 39h ; '9'
0x180003498  jz      short loc_18000348D
0x18000349a  sub     ecx, 8
0x18000349d  jz      short loc_1800034B8
0x18000349f  sub     ecx, 1
0x1800034a2  jz      short loc_1800034B8
0x1800034a4  sub     ecx, 1
0x1800034a7  jz      short loc_1800034B8
0x1800034a9  sub     ecx, 1
0x1800034ac  jz      short loc_1800034B8
0x1800034ae  sub     ecx, 1
0x1800034b1  jz      short loc_1800034B8
0x1800034b3  cmp     ecx, 1
0x1800034b6  jnz     short loc_1800034DA
0x1800034b8  sub     r9b, 37h ; '7'
0x1800034bc  jmp     short loc_1800034E3
0x1800034be  mov     ecx, r9d
0x1800034c1  sub     ecx, 62h ; 'b'
0x1800034c4  jz      short loc_1800034DF
0x1800034c6  sub     ecx, 1
0x1800034c9  jz      short loc_1800034DF
0x1800034cb  sub     ecx, 1
0x1800034ce  jz      short loc_1800034DF
0x1800034d0  sub     ecx, 1
0x1800034d3  jz      short loc_1800034DF
0x1800034d5  cmp     ecx, 1
0x1800034d8  jz      short loc_1800034DF
0x1800034da  mov     r9b, dil
0x1800034dd  jmp     short loc_1800034E3
0x1800034df  sub     r9b, 57h ; 'W'
0x1800034e3  mov     rdx, [rsp+22B0h+var_2270]
0x1800034e8  mov     eax, r10d
0x1800034eb  and     eax, 1
0x1800034ee  mov     r8d, r10d
0x1800034f1  shl     eax, 2
0x1800034f4  mov     ecx, 4
0x1800034f9  shr     r8, 1
0x1800034fc  sub     ecx, eax
0x1800034fe  shl     r9b, cl
0x180003501  inc     r10d
0x180003504  or      [r8+rdx], r9b
0x180003508  cmp     r10d, esi
0x18000350b  jl      loc_180003442
0x180003511  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180003516  mov     rax, [rsp+22B0h+var_2270]
0x18000351b  mov     r9d, 3; dwType
0x180003521  mov     rcx, [r13+0]; hKey
0x180003525  xor     r8d, r8d; Reserved
0x180003528  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
