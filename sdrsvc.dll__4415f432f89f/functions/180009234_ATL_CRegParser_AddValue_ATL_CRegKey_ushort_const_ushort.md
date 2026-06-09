# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180009234`
- end: `0x1800096fe`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1226`
- prototype: `HRESULT __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c254`

## callees

- `0x180009234`
- `0x180009704`
- `0x180009918`
- `0x18000ab34`
- `0x18000b130`
- `0x18002170a`
- `0x180021740`
- `0x1800217d0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800092fd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800093c9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800093e5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800092fd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800093c9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800093e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000944d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800094c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009664`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000944d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800094c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009664`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800092ad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800092ad`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180009490`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180009490`

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
  DWORD cbData; // r9d
  BYTE *v17; // r8
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
    goto LABEL_42;
  }
  if ( v10 != 17 )
  {
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
        if ( (_DWORD)v11 == -2 || 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 || 2 * v12 <= 0x100 )
        {
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
        goto LABEL_85;
      }
      goto LABEL_90;
    }
    pulOut[0] = 0;
    result = VarUI4FromStr(String1, 0, 0, pulOut);
    if ( result < 0 )
      return result;
    *(_DWORD *)Data = pulOut[0];
    v22 = RegSetValueExW(*a2, v6, 0, 4u, Data, 4u);
LABEL_42:
    v21 = v22;
    goto LABEL_85;
  }
  v23 = -1;
  do
    ++v23;
  while ( String1[v23] );
  if ( (v23 & 1) != 0 )
    return -2147467259;
  v36 = 0;
  v24 = (int)v23 / 2;
  if ( (int)v23 / 2 && 0xFFFFFFFFFFFFFFFFuLL / v24 && v24 > 0x100 )
  {
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v36, v24);
    v25 = v36;
  }
  else
  {
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
    goto LABEL_82;
  do
  {
    v27 = String1[v26];
    if ( v27 > 0x61 )
    {
      if ( v27 != 98 && v27 != 99 && v27 != 100 && v27 - 101 >= 2 )
        goto LABEL_78;
    }
    else if ( v27 != 97 )
    {
      if ( v27 > 0x38 )
      {
        if ( v27 == 57 )
          goto LABEL_66;
        if ( v27 == 65 || v27 == 66 || v27 == 67 || v27 == 68 || v27 - 69 <= 1 )
        {
          v28 = v27 - 55;
          goto LABEL_80;
        }
      }
      else if ( v27 == 56 || v27 == 48 || v27 == 49 || v27 == 50 || v27 == 51 || v27 == 52 || v27 == 53 || v27 - 54 <= 1 )
      {
LABEL_66:
        v28 = v27 - 48;
        goto LABEL_80;
      }
LABEL_78:
      v28 = 0;
      goto LABEL_80;
    }
    v28 = v27 - 87;
LABEL_80:
    v29 = (unsigned __int64)(unsigned int)v26 >> 1;
    v30 = v28 << (4 - 4 * (v26++ & 1));
    v36[v29] |= v30;
  }
  while ( v26 < (int)v23 );
  v6 = *(const WCHAR **)pulOut;
LABEL_82:
  v21 = RegSetValueExW(*a2, v6, 0, 3u, v36, (int)v23 / 2);
  if ( v36 != v37 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
  v5 = *(unsigned __int16 **)Data;
LABEL_85:
  if ( v21 )
    return ATL::AtlHresultFromWin32(v21);
LABEL_90:
  Token = ATL::CRegParser::NextToken(this, v5);
  v33 = 0;
  if ( Token < 0 )
    return Token;
  return v33;
}

```

## disassembly

```asm
0x180009234  push    rbp
0x180009236  push    rbx
0x180009237  push    rsi
0x180009238  push    rdi
0x180009239  push    r12
0x18000923b  push    r13
0x18000923d  push    r14
0x18000923f  push    r15
0x180009241  lea     rbp, [rsp-2178h]
0x180009249  mov     eax, 2278h
0x18000924e  call    _alloca_probe
0x180009253  sub     rsp, rax
0x180009256  mov     rax, cs:__security_cookie
0x18000925d  xor     rax, rsp
0x180009260  mov     [rbp+21B0h+var_50], rax
0x180009267  mov     r13, rdx
0x18000926a  mov     qword ptr [rsp+22B0h+Data], r9
0x18000926f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180009276  mov     qword ptr [rsp+22B0h+pulOut], r8
0x18000927b  mov     r15, r9
0x18000927e  mov     r14, r8
0x180009281  mov     r12, rcx
0x180009284  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009289  xor     esi, esi
0x18000928b  test    eax, eax
0x18000928d  js      loc_1800096DB
0x180009293  mov     ebx, esi
0x180009295  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000929c  movsxd  rdi, ebx
0x18000929f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x1800092a6  add     rdi, rdi
0x1800092a9  mov     rdx, [rax+rdi*8]; lpString2
0x1800092ad  call    cs:__imp_lstrcmpiW
0x1800092b3  test    eax, eax
0x1800092b5  jz      short loc_1800092CF
0x1800092b7  inc     ebx
0x1800092b9  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800092c0  cmp     ebx, 4
0x1800092c3  jb      short loc_18000929C
0x1800092c5  mov     eax, 80020009h
0x1800092ca  jmp     loc_1800096DB
0x1800092cf  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800092d6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1800092db  mov     edi, 13h
0x1800092e0  mov     rdx, [r12]
0x1800092e4  movzx   ecx, word ptr [rdx]
0x1800092e7  sub     ecx, 9
0x1800092ea  jz      short loc_1800092FA
0x1800092ec  sub     ecx, 1
0x1800092ef  jz      short loc_1800092FA
0x1800092f1  sub     ecx, 3
0x1800092f4  jz      short loc_1800092FA
0x1800092f6  cmp     ecx, edi
0x1800092f8  jnz     short loc_180009309
0x1800092fa  mov     rcx, rdx; lpsz
0x1800092fd  call    cs:__imp_CharNextW
0x180009303  mov     [r12], rax
0x180009307  jmp     short loc_1800092E0
0x180009309  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180009310  mov     rcx, r12; this
0x180009313  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009318  test    eax, eax
0x18000931a  js      loc_1800096DB
0x180009320  mov     eax, 8
0x180009325  cmp     bx, ax
0x180009328  jz      loc_180009696
0x18000932e  cmp     bx, 11h
0x180009332  jz      loc_1800094D3
0x180009338  cmp     bx, di
0x18000933b  jz      loc_18000947B
0x180009341  mov     eax, 4008h
0x180009346  cmp     bx, ax
0x180009349  jnz     loc_1800096C7
0x18000934f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180009353  mov     [rbp+21B0h+var_2160], rsi
0x180009357  mov     rax, rdi
0x18000935a  lea     rcx, [rbp+21B0h+String1]
0x180009361  inc     rax
0x180009364  cmp     [rcx+rax*2], si
0x180009368  jnz     short loc_180009361
0x18000936a  add     eax, 2
0x18000936d  movsxd  rcx, eax
0x180009370  jz      short loc_18000939C
0x180009372  xor     edx, edx
0x180009374  mov     rax, rdi
0x180009377  div     rcx
0x18000937a  cmp     rax, 2
0x18000937e  jb      short loc_18000939C
0x180009380  lea     rdx, [rcx+rcx]
0x180009384  cmp     rdx, 100h
0x18000938b  jbe     short loc_18000939C
0x18000938d  lea     rcx, [rbp+21B0h+var_2160]
0x180009391  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180009396  mov     rbx, [rbp+21B0h+var_2160]
0x18000939a  jmp     short loc_1800093A4
0x18000939c  lea     rbx, [rbp+21B0h+var_2158]
0x1800093a0  mov     [rbp+21B0h+var_2160], rbx
0x1800093a4  test    rbx, rbx
0x1800093a7  jz      loc_18000945B
0x1800093ad  xor     eax, eax
0x1800093af  lea     rsi, [rbp+21B0h+String1]
0x1800093b6  cmp     [rbp+21B0h+String1], ax
0x1800093bd  jz      short loc_18000940B
0x1800093bf  lea     r14d, [rax+30h]
0x1800093c3  xor     r15d, r15d
0x1800093c6  mov     rcx, rsi; lpsz
0x1800093c9  call    cs:__imp_CharNextW
0x1800093cf  movzx   ecx, word ptr [rsi]
0x1800093d2  cmp     cx, 5Ch ; '\'
0x1800093d6  jnz     short loc_1800093F0
0x1800093d8  cmp     [rax], r14w
0x1800093dc  jnz     short loc_1800093F0
0x1800093de  mov     rcx, rax; lpsz
0x1800093e1  mov     [rbx], r15w
0x1800093e5  call    cs:__imp_CharNextW
0x1800093eb  mov     rsi, rax
0x1800093ee  jmp     short loc_1800093F7
0x1800093f0  mov     [rbx], cx
0x1800093f3  add     rsi, 2
0x1800093f7  add     rbx, 2
0x1800093fb  cmp     [rsi], r15w
0x1800093ff  jnz     short loc_1800093C6
0x180009401  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180009406  mov     r15, qword ptr [rsp+22B0h+Data]
0x18000940b  xor     esi, esi
0x18000940d  mov     [rbx], esi
0x18000940f  mov     r9d, esi
0x180009412  mov     r10, [rbp+21B0h+var_2160]
0x180009416  mov     r8, r10
0x180009419  mov     rcx, rdi
0x18000941c  inc     rcx
0x18000941f  cmp     [r8+rcx*2], si
0x180009424  jnz     short loc_18000941C
0x180009426  inc     ecx
0x180009428  lea     r8, [r8+rcx*2]
0x18000942c  lea     r9d, [r9+rcx*2]
0x180009430  cmp     ecx, 1
0x180009433  jnz     short loc_180009419
0x180009435  mov     [rsp+22B0h+cbData], r9d; cbData
0x18000943a  xor     r8d, r8d; Reserved
0x18000943d  lea     r9d, [rcx+6]; dwType
0x180009441  mov     [rsp+22B0h+lpData], r10; lpData
0x180009446  mov     rcx, [r13+0]; hKey
0x18000944a  mov     rdx, r14; lpValueName
0x18000944d  call    cs:__imp_RegSetValueExW
0x180009453  mov     rbx, [rbp+21B0h+var_2160]
0x180009457  mov     edi, eax
0x180009459  jmp     short loc_180009460
0x18000945b  mov     edi, 0Eh
0x180009460  lea     rax, [rbp+21B0h+var_2158]
0x180009464  cmp     rbx, rax
0x180009467  jz      loc_180009689
0x18000946d  lea     rcx, [rbp+21B0h+var_2160]
0x180009471  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180009476  jmp     loc_180009689
0x18000947b  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x180009480  mov     [rsp+22B0h+pulOut], esi
0x180009484  xor     r8d, r8d; dwFlags
0x180009487  lea     rcx, [rbp+21B0h+String1]; strIn
0x18000948e  xor     edx, edx; lcid
0x180009490  call    cs:__imp_VarUI4FromStr
0x180009496  test    eax, eax
0x180009498  js      loc_1800096DB
0x18000949e  mov     eax, [rsp+22B0h+pulOut]
0x1800094a2  mov     ecx, 4
0x1800094a7  mov     dword ptr [rsp+22B0h+Data], eax
0x1800094ab  mov     r9d, ecx; dwType
0x1800094ae  mov     [rsp+22B0h+cbData], ecx; cbData
0x1800094b2  lea     rax, [rsp+22B0h+Data]
0x1800094b7  mov     rcx, [r13+0]; hKey
0x1800094bb  xor     r8d, r8d; Reserved
0x1800094be  mov     rdx, r14; lpValueName
0x1800094c1  mov     [rsp+22B0h+lpData], rax; lpData
0x1800094c6  call    cs:__imp_RegSetValueExW
0x1800094cc  mov     edi, eax
0x1800094ce  jmp     loc_180009689
0x1800094d3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800094d7  lea     rax, [rbp+21B0h+String1]
0x1800094de  mov     rsi, rdi
0x1800094e1  xor     ecx, ecx
0x1800094e3  inc     rsi
0x1800094e6  cmp     [rax+rsi*2], cx
0x1800094ea  jnz     short loc_1800094E3
0x1800094ec  test    sil, 1
0x1800094f0  jnz     short loc_18000954C
0x1800094f2  mov     eax, esi
0x1800094f4  mov     [rsp+22B0h+var_2270], rcx
0x1800094f9  cdq
0x1800094fa  sub     eax, edx
0x1800094fc  sar     eax, 1
0x1800094fe  movsxd  r15, eax
0x180009501  mov     rbx, r15
0x180009504  jz      short loc_180009531
0x180009506  xor     edx, edx
0x180009508  mov     rax, rdi
0x18000950b  div     rbx
0x18000950e  cmp     rax, 1
0x180009512  jb      short loc_180009531
0x180009514  cmp     rbx, 100h
0x18000951b  jbe     short loc_180009531
0x18000951d  mov     rdx, rbx
0x180009520  lea     rcx, [rsp+22B0h+var_2270]
0x180009525  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000952a  mov     rcx, [rsp+22B0h+var_2270]
0x18000952f  jmp     short loc_18000953B
0x180009531  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180009536  mov     [rsp+22B0h+var_2270], rcx
0x18000953b  xor     edi, edi
0x18000953d  test    rcx, rcx
0x180009540  jnz     short loc_180009556
0x180009542  lea     rcx, [rsp+22B0h+var_2270]
0x180009547  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000954c  mov     eax, 80004005h
0x180009551  jmp     loc_1800096DB
0x180009556  mov     r8, rbx; Size
0x180009559  xor     edx, edx; Val
0x18000955b  call    memset_0
0x180009560  mov     r10d, edi
0x180009563  test    esi, esi
0x180009565  jle     loc_180009645
0x18000956b  mov     r14d, 30h ; '0'
0x180009571  mov     eax, r10d
0x180009574  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x18000957d  cmp     r9d, 61h ; 'a'
0x180009581  ja      short loc_1800095ED
0x180009583  jz      loc_18000960E
0x180009589  cmp     r9d, 38h ; '8'
0x18000958d  ja      short loc_1800095C1
0x18000958f  jz      short loc_1800095BC
0x180009591  mov     ecx, r9d
0x180009594  sub     ecx, r14d
0x180009597  jz      short loc_1800095BC
0x180009599  sub     ecx, 1
0x18000959c  jz      short loc_1800095BC
0x18000959e  sub     ecx, 1
0x1800095a1  jz      short loc_1800095BC
0x1800095a3  sub     ecx, 1
0x1800095a6  jz      short loc_1800095BC
0x1800095a8  sub     ecx, 1
0x1800095ab  jz      short loc_1800095BC
0x1800095ad  sub     ecx, 1
0x1800095b0  jz      short loc_1800095BC
0x1800095b2  sub     ecx, 1
0x1800095b5  jz      short loc_1800095BC
0x1800095b7  cmp     ecx, 1
0x1800095ba  jnz     short loc_180009609
0x1800095bc  sub     r9b, r14b
0x1800095bf  jmp     short loc_180009612
0x1800095c1  mov     ecx, r9d
0x1800095c4  sub     ecx, 39h ; '9'
0x1800095c7  jz      short loc_1800095BC
0x1800095c9  sub     ecx, 8
0x1800095cc  jz      short loc_1800095E7
0x1800095ce  sub     ecx, 1
0x1800095d1  jz      short loc_1800095E7
0x1800095d3  sub     ecx, 1
0x1800095d6  jz      short loc_1800095E7
0x1800095d8  sub     ecx, 1
0x1800095db  jz      short loc_1800095E7
0x1800095dd  sub     ecx, 1
0x1800095e0  jz      short loc_1800095E7
0x1800095e2  cmp     ecx, 1
0x1800095e5  jnz     short loc_180009609
0x1800095e7  sub     r9b, 37h ; '7'
0x1800095eb  jmp     short loc_180009612
0x1800095ed  mov     ecx, r9d
0x1800095f0  sub     ecx, 62h ; 'b'
0x1800095f3  jz      short loc_18000960E
0x1800095f5  sub     ecx, 1
0x1800095f8  jz      short loc_18000960E
0x1800095fa  sub     ecx, 1
0x1800095fd  jz      short loc_18000960E
0x1800095ff  sub     ecx, 1
0x180009602  jz      short loc_18000960E
0x180009604  cmp     ecx, 1
0x180009607  jz      short loc_18000960E
0x180009609  mov     r9b, dil
0x18000960c  jmp     short loc_180009612
0x18000960e  sub     r9b, 57h ; 'W'
0x180009612  mov     rdx, [rsp+22B0h+var_2270]
0x180009617  mov     eax, r10d
0x18000961a  and     eax, 1
0x18000961d  mov     r8d, r10d
0x180009620  shl     eax, 2
0x180009623  mov     ecx, 4
0x180009628  shr     r8, 1
0x18000962b  sub     ecx, eax
0x18000962d  shl     r9b, cl
0x180009630  inc     r10d
0x180009633  or      [r8+rdx], r9b
0x180009637  cmp     r10d, esi
0x18000963a  jl      loc_180009571
0x180009640  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180009645  mov     rax, [rsp+22B0h+var_2270]
0x18000964a  mov     r9d, 3; dwType
0x180009650  mov     rcx, [r13+0]; hKey
0x180009654  xor     r8d, r8d; Reserved
0x180009657  mov     [rsp+22B0h+cbData], r15d; cbData
0x18000965c  mov     rdx, r14; lpValueName
0x18000965f  mov     [rsp+22B0h+lpData], rax; lpData
  ... truncated ...
```
