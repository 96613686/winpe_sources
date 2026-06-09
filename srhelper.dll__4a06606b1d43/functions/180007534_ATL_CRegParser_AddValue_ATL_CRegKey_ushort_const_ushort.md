# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180007534`
- end: `0x1800079fe`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1226`
- prototype: `HRESULT __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000902c`

## callees

- `0x180007534`
- `0x180007a04`
- `0x180007c18`
- `0x1800083c4`
- `0x180008700`
- `0x1800157be`
- `0x1800157f0`
- `0x180015880`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800075ad`
- `KERNEL32!lstrcmpiW` at `0x1800075ad`
- `USER32!CharNextW` at `0x1800075fd`
- `USER32!CharNextW` at `0x1800076c9`
- `USER32!CharNextW` at `0x1800076e5`
- `USER32!CharNextW` at `0x1800075fd`
- `USER32!CharNextW` at `0x1800076c9`
- `USER32!CharNextW` at `0x1800076e5`
- `ADVAPI32!RegSetValueExW` at `0x18000774d`
- `ADVAPI32!RegSetValueExW` at `0x1800077c6`
- `ADVAPI32!RegSetValueExW` at `0x180007964`
- `ADVAPI32!RegSetValueExW` at `0x18000774d`
- `ADVAPI32!RegSetValueExW` at `0x1800077c6`
- `ADVAPI32!RegSetValueExW` at `0x180007964`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180007790`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180007790`

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
0x180007534  push    rbp
0x180007536  push    rbx
0x180007537  push    rsi
0x180007538  push    rdi
0x180007539  push    r12
0x18000753b  push    r13
0x18000753d  push    r14
0x18000753f  push    r15
0x180007541  lea     rbp, [rsp-2178h]
0x180007549  mov     eax, 2278h
0x18000754e  call    _alloca_probe
0x180007553  sub     rsp, rax
0x180007556  mov     rax, cs:__security_cookie
0x18000755d  xor     rax, rsp
0x180007560  mov     [rbp+21B0h+var_50], rax
0x180007567  mov     r13, rdx
0x18000756a  mov     qword ptr [rsp+22B0h+Data], r9
0x18000756f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180007576  mov     qword ptr [rsp+22B0h+pulOut], r8
0x18000757b  mov     r15, r9
0x18000757e  mov     r14, r8
0x180007581  mov     r12, rcx
0x180007584  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007589  xor     esi, esi
0x18000758b  test    eax, eax
0x18000758d  js      loc_1800079DB
0x180007593  mov     ebx, esi
0x180007595  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000759c  movsxd  rdi, ebx
0x18000759f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x1800075a6  add     rdi, rdi
0x1800075a9  mov     rdx, [rax+rdi*8]; lpString2
0x1800075ad  call    cs:__imp_lstrcmpiW
0x1800075b3  test    eax, eax
0x1800075b5  jz      short loc_1800075CF
0x1800075b7  inc     ebx
0x1800075b9  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800075c0  cmp     ebx, 4
0x1800075c3  jb      short loc_18000759C
0x1800075c5  mov     eax, 80020009h
0x1800075ca  jmp     loc_1800079DB
0x1800075cf  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800075d6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1800075db  mov     edi, 13h
0x1800075e0  mov     rdx, [r12]
0x1800075e4  movzx   ecx, word ptr [rdx]
0x1800075e7  sub     ecx, 9
0x1800075ea  jz      short loc_1800075FA
0x1800075ec  sub     ecx, 1
0x1800075ef  jz      short loc_1800075FA
0x1800075f1  sub     ecx, 3
0x1800075f4  jz      short loc_1800075FA
0x1800075f6  cmp     ecx, edi
0x1800075f8  jnz     short loc_180007609
0x1800075fa  mov     rcx, rdx; lpsz
0x1800075fd  call    cs:__imp_CharNextW
0x180007603  mov     [r12], rax
0x180007607  jmp     short loc_1800075E0
0x180007609  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180007610  mov     rcx, r12; this
0x180007613  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007618  test    eax, eax
0x18000761a  js      loc_1800079DB
0x180007620  mov     eax, 8
0x180007625  cmp     bx, ax
0x180007628  jz      loc_180007996
0x18000762e  cmp     bx, 11h
0x180007632  jz      loc_1800077D3
0x180007638  cmp     bx, di
0x18000763b  jz      loc_18000777B
0x180007641  mov     eax, 4008h
0x180007646  cmp     bx, ax
0x180007649  jnz     loc_1800079C7
0x18000764f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007653  mov     [rbp+21B0h+var_2160], rsi
0x180007657  mov     rax, rdi
0x18000765a  lea     rcx, [rbp+21B0h+String1]
0x180007661  inc     rax
0x180007664  cmp     [rcx+rax*2], si
0x180007668  jnz     short loc_180007661
0x18000766a  add     eax, 2
0x18000766d  movsxd  rcx, eax
0x180007670  jz      short loc_18000769C
0x180007672  xor     edx, edx
0x180007674  mov     rax, rdi
0x180007677  div     rcx
0x18000767a  cmp     rax, 2
0x18000767e  jb      short loc_18000769C
0x180007680  lea     rdx, [rcx+rcx]
0x180007684  cmp     rdx, 100h
0x18000768b  jbe     short loc_18000769C
0x18000768d  lea     rcx, [rbp+21B0h+var_2160]
0x180007691  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007696  mov     rbx, [rbp+21B0h+var_2160]
0x18000769a  jmp     short loc_1800076A4
0x18000769c  lea     rbx, [rbp+21B0h+var_2158]
0x1800076a0  mov     [rbp+21B0h+var_2160], rbx
0x1800076a4  test    rbx, rbx
0x1800076a7  jz      loc_18000775B
0x1800076ad  xor     eax, eax
0x1800076af  lea     rsi, [rbp+21B0h+String1]
0x1800076b6  cmp     [rbp+21B0h+String1], ax
0x1800076bd  jz      short loc_18000770B
0x1800076bf  lea     r14d, [rax+30h]
0x1800076c3  xor     r15d, r15d
0x1800076c6  mov     rcx, rsi; lpsz
0x1800076c9  call    cs:__imp_CharNextW
0x1800076cf  movzx   ecx, word ptr [rsi]
0x1800076d2  cmp     cx, 5Ch ; '\'
0x1800076d6  jnz     short loc_1800076F0
0x1800076d8  cmp     [rax], r14w
0x1800076dc  jnz     short loc_1800076F0
0x1800076de  mov     rcx, rax; lpsz
0x1800076e1  mov     [rbx], r15w
0x1800076e5  call    cs:__imp_CharNextW
0x1800076eb  mov     rsi, rax
0x1800076ee  jmp     short loc_1800076F7
0x1800076f0  mov     [rbx], cx
0x1800076f3  add     rsi, 2
0x1800076f7  add     rbx, 2
0x1800076fb  cmp     [rsi], r15w
0x1800076ff  jnz     short loc_1800076C6
0x180007701  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180007706  mov     r15, qword ptr [rsp+22B0h+Data]
0x18000770b  xor     esi, esi
0x18000770d  mov     [rbx], esi
0x18000770f  mov     r9d, esi
0x180007712  mov     r10, [rbp+21B0h+var_2160]
0x180007716  mov     r8, r10
0x180007719  mov     rcx, rdi
0x18000771c  inc     rcx
0x18000771f  cmp     [r8+rcx*2], si
0x180007724  jnz     short loc_18000771C
0x180007726  inc     ecx
0x180007728  lea     r8, [r8+rcx*2]
0x18000772c  lea     r9d, [r9+rcx*2]
0x180007730  cmp     ecx, 1
0x180007733  jnz     short loc_180007719
0x180007735  mov     [rsp+22B0h+cbData], r9d; cbData
0x18000773a  xor     r8d, r8d; Reserved
0x18000773d  lea     r9d, [rcx+6]; dwType
0x180007741  mov     [rsp+22B0h+lpData], r10; lpData
0x180007746  mov     rcx, [r13+0]; hKey
0x18000774a  mov     rdx, r14; lpValueName
0x18000774d  call    cs:__imp_RegSetValueExW
0x180007753  mov     rbx, [rbp+21B0h+var_2160]
0x180007757  mov     edi, eax
0x180007759  jmp     short loc_180007760
0x18000775b  mov     edi, 0Eh
0x180007760  lea     rax, [rbp+21B0h+var_2158]
0x180007764  cmp     rbx, rax
0x180007767  jz      loc_180007989
0x18000776d  lea     rcx, [rbp+21B0h+var_2160]
0x180007771  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180007776  jmp     loc_180007989
0x18000777b  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x180007780  mov     [rsp+22B0h+pulOut], esi
0x180007784  xor     r8d, r8d; dwFlags
0x180007787  lea     rcx, [rbp+21B0h+String1]; strIn
0x18000778e  xor     edx, edx; lcid
0x180007790  call    cs:__imp_VarUI4FromStr
0x180007796  test    eax, eax
0x180007798  js      loc_1800079DB
0x18000779e  mov     eax, [rsp+22B0h+pulOut]
0x1800077a2  mov     ecx, 4
0x1800077a7  mov     dword ptr [rsp+22B0h+Data], eax
0x1800077ab  mov     r9d, ecx; dwType
0x1800077ae  mov     [rsp+22B0h+cbData], ecx; cbData
0x1800077b2  lea     rax, [rsp+22B0h+Data]
0x1800077b7  mov     rcx, [r13+0]; hKey
0x1800077bb  xor     r8d, r8d; Reserved
0x1800077be  mov     rdx, r14; lpValueName
0x1800077c1  mov     [rsp+22B0h+lpData], rax; lpData
0x1800077c6  call    cs:__imp_RegSetValueExW
0x1800077cc  mov     edi, eax
0x1800077ce  jmp     loc_180007989
0x1800077d3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800077d7  lea     rax, [rbp+21B0h+String1]
0x1800077de  mov     rsi, rdi
0x1800077e1  xor     ecx, ecx
0x1800077e3  inc     rsi
0x1800077e6  cmp     [rax+rsi*2], cx
0x1800077ea  jnz     short loc_1800077E3
0x1800077ec  test    sil, 1
0x1800077f0  jnz     short loc_18000784C
0x1800077f2  mov     eax, esi
0x1800077f4  mov     [rsp+22B0h+var_2270], rcx
0x1800077f9  cdq
0x1800077fa  sub     eax, edx
0x1800077fc  sar     eax, 1
0x1800077fe  movsxd  r15, eax
0x180007801  mov     rbx, r15
0x180007804  jz      short loc_180007831
0x180007806  xor     edx, edx
0x180007808  mov     rax, rdi
0x18000780b  div     rbx
0x18000780e  cmp     rax, 1
0x180007812  jb      short loc_180007831
0x180007814  cmp     rbx, 100h
0x18000781b  jbe     short loc_180007831
0x18000781d  mov     rdx, rbx
0x180007820  lea     rcx, [rsp+22B0h+var_2270]
0x180007825  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000782a  mov     rcx, [rsp+22B0h+var_2270]
0x18000782f  jmp     short loc_18000783B
0x180007831  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180007836  mov     [rsp+22B0h+var_2270], rcx
0x18000783b  xor     edi, edi
0x18000783d  test    rcx, rcx
0x180007840  jnz     short loc_180007856
0x180007842  lea     rcx, [rsp+22B0h+var_2270]
0x180007847  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000784c  mov     eax, 80004005h
0x180007851  jmp     loc_1800079DB
0x180007856  mov     r8, rbx; Size
0x180007859  xor     edx, edx; Val
0x18000785b  call    memset_0
0x180007860  mov     r10d, edi
0x180007863  test    esi, esi
0x180007865  jle     loc_180007945
0x18000786b  mov     r14d, 30h ; '0'
0x180007871  mov     eax, r10d
0x180007874  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x18000787d  cmp     r9d, 61h ; 'a'
0x180007881  ja      short loc_1800078ED
0x180007883  jz      loc_18000790E
0x180007889  cmp     r9d, 38h ; '8'
0x18000788d  ja      short loc_1800078C1
0x18000788f  jz      short loc_1800078BC
0x180007891  mov     ecx, r9d
0x180007894  sub     ecx, r14d
0x180007897  jz      short loc_1800078BC
0x180007899  sub     ecx, 1
0x18000789c  jz      short loc_1800078BC
0x18000789e  sub     ecx, 1
0x1800078a1  jz      short loc_1800078BC
0x1800078a3  sub     ecx, 1
0x1800078a6  jz      short loc_1800078BC
0x1800078a8  sub     ecx, 1
0x1800078ab  jz      short loc_1800078BC
0x1800078ad  sub     ecx, 1
0x1800078b0  jz      short loc_1800078BC
0x1800078b2  sub     ecx, 1
0x1800078b5  jz      short loc_1800078BC
0x1800078b7  cmp     ecx, 1
0x1800078ba  jnz     short loc_180007909
0x1800078bc  sub     r9b, r14b
0x1800078bf  jmp     short loc_180007912
0x1800078c1  mov     ecx, r9d
0x1800078c4  sub     ecx, 39h ; '9'
0x1800078c7  jz      short loc_1800078BC
0x1800078c9  sub     ecx, 8
0x1800078cc  jz      short loc_1800078E7
0x1800078ce  sub     ecx, 1
0x1800078d1  jz      short loc_1800078E7
0x1800078d3  sub     ecx, 1
0x1800078d6  jz      short loc_1800078E7
0x1800078d8  sub     ecx, 1
0x1800078db  jz      short loc_1800078E7
0x1800078dd  sub     ecx, 1
0x1800078e0  jz      short loc_1800078E7
0x1800078e2  cmp     ecx, 1
0x1800078e5  jnz     short loc_180007909
0x1800078e7  sub     r9b, 37h ; '7'
0x1800078eb  jmp     short loc_180007912
0x1800078ed  mov     ecx, r9d
0x1800078f0  sub     ecx, 62h ; 'b'
0x1800078f3  jz      short loc_18000790E
0x1800078f5  sub     ecx, 1
0x1800078f8  jz      short loc_18000790E
0x1800078fa  sub     ecx, 1
0x1800078fd  jz      short loc_18000790E
0x1800078ff  sub     ecx, 1
0x180007902  jz      short loc_18000790E
0x180007904  cmp     ecx, 1
0x180007907  jz      short loc_18000790E
0x180007909  mov     r9b, dil
0x18000790c  jmp     short loc_180007912
0x18000790e  sub     r9b, 57h ; 'W'
0x180007912  mov     rdx, [rsp+22B0h+var_2270]
0x180007917  mov     eax, r10d
0x18000791a  and     eax, 1
0x18000791d  mov     r8d, r10d
0x180007920  shl     eax, 2
0x180007923  mov     ecx, 4
0x180007928  shr     r8, 1
0x18000792b  sub     ecx, eax
0x18000792d  shl     r9b, cl
0x180007930  inc     r10d
0x180007933  or      [r8+rdx], r9b
0x180007937  cmp     r10d, esi
0x18000793a  jl      loc_180007871
0x180007940  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180007945  mov     rax, [rsp+22B0h+var_2270]
0x18000794a  mov     r9d, 3; dwType
0x180007950  mov     rcx, [r13+0]; hKey
0x180007954  xor     r8d, r8d; Reserved
0x180007957  mov     [rsp+22B0h+cbData], r15d; cbData
0x18000795c  mov     rdx, r14; lpValueName
0x18000795f  mov     [rsp+22B0h+lpData], rax; lpData
  ... truncated ...
```
