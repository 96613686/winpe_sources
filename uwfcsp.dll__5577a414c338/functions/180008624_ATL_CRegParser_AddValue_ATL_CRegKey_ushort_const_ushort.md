# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180008624`
- end: `0x180008b20`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `HRESULT __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000a50c`

## callees

- `0x180008624`
- `0x180008b28`
- `0x180008c7c`
- `0x180008c94`
- `0x180009288`
- `0x1800096e4`
- `0x18001a1d6`
- `0x18001a210`
- `0x18001a2d0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000888d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000888d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800086ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087bd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087d9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800086ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087bd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800087d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000884a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800088c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008a65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000884a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800088c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008a65`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000869d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000869d`

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
0x180008624  push    rbp
0x180008626  push    rbx
0x180008627  push    rsi
0x180008628  push    rdi
0x180008629  push    r12
0x18000862b  push    r13
0x18000862d  push    r14
0x18000862f  push    r15
0x180008631  lea     rbp, [rsp-2178h]
0x180008639  mov     eax, 2278h
0x18000863e  call    _alloca_probe
0x180008643  sub     rsp, rax
0x180008646  mov     rax, cs:__security_cookie
0x18000864d  xor     rax, rsp
0x180008650  mov     [rbp+21B0h+var_50], rax
0x180008657  mov     r13, rdx
0x18000865a  mov     qword ptr [rsp+22B0h+Data], r9
0x18000865f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180008666  mov     qword ptr [rsp+22B0h+pulOut], r8
0x18000866b  mov     r15, r9
0x18000866e  mov     r14, r8
0x180008671  mov     r12, rcx
0x180008674  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008679  xor     esi, esi
0x18000867b  test    eax, eax
0x18000867d  js      loc_180008ADC
0x180008683  mov     ebx, esi
0x180008685  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000868c  movsxd  rdi, ebx
0x18000868f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x180008696  add     rdi, rdi
0x180008699  mov     rdx, [rax+rdi*8]; lpString2
0x18000869d  call    cs:__imp_lstrcmpiW
0x1800086a3  test    eax, eax
0x1800086a5  jz      short loc_1800086BF
0x1800086a7  inc     ebx
0x1800086a9  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800086b0  cmp     ebx, 4
0x1800086b3  jb      short loc_18000868C
0x1800086b5  mov     eax, 80020009h
0x1800086ba  jmp     loc_180008ADC
0x1800086bf  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800086c6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1800086cb  mov     edi, 13h
0x1800086d0  mov     rdx, [r12]
0x1800086d4  movzx   ecx, word ptr [rdx]
0x1800086d7  sub     ecx, 9
0x1800086da  jz      short loc_1800086EA
0x1800086dc  sub     ecx, 1
0x1800086df  jz      short loc_1800086EA
0x1800086e1  sub     ecx, 3
0x1800086e4  jz      short loc_1800086EA
0x1800086e6  cmp     ecx, edi
0x1800086e8  jnz     short loc_1800086F9
0x1800086ea  mov     rcx, rdx; lpsz
0x1800086ed  call    cs:__imp_CharNextW
0x1800086f3  mov     [r12], rax
0x1800086f7  jmp     short loc_1800086D0
0x1800086f9  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180008700  mov     rcx, r12; this
0x180008703  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008708  test    eax, eax
0x18000870a  js      loc_180008ADC
0x180008710  mov     eax, 8
0x180008715  cmp     bx, ax
0x180008718  jz      loc_180008A97
0x18000871e  cmp     bx, 11h
0x180008722  jz      loc_1800088D0
0x180008728  cmp     bx, di
0x18000872b  jz      loc_180008878
0x180008731  mov     eax, 4008h
0x180008736  cmp     bx, ax
0x180008739  jnz     loc_180008AC8
0x18000873f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008743  mov     [rbp+21B0h+var_2160], rsi
0x180008747  mov     rax, rdi
0x18000874a  lea     rcx, [rbp+21B0h+String1]
0x180008751  inc     rax
0x180008754  cmp     [rcx+rax*2], si
0x180008758  jnz     short loc_180008751
0x18000875a  add     eax, 2
0x18000875d  movsxd  rcx, eax
0x180008760  jz      short loc_180008790
0x180008762  xor     edx, edx
0x180008764  mov     rax, rdi
0x180008767  div     rcx
0x18000876a  cmp     rax, 2
0x18000876e  jb      loc_180008B0A
0x180008774  lea     rdx, [rcx+rcx]
0x180008778  cmp     rdx, 100h
0x18000877f  jbe     short loc_180008790
0x180008781  lea     rcx, [rbp+21B0h+var_2160]
0x180008785  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000878a  mov     rbx, [rbp+21B0h+var_2160]
0x18000878e  jmp     short loc_180008798
0x180008790  lea     rbx, [rbp+21B0h+var_2158]
0x180008794  mov     [rbp+21B0h+var_2160], rbx
0x180008798  test    rbx, rbx
0x18000879b  jz      loc_180008858
0x1800087a1  xor     eax, eax
0x1800087a3  lea     rsi, [rbp+21B0h+String1]
0x1800087aa  cmp     [rbp+21B0h+String1], ax
0x1800087b1  jz      short loc_1800087FF
0x1800087b3  lea     r14d, [rax+30h]
0x1800087b7  xor     r15d, r15d
0x1800087ba  mov     rcx, rsi; lpsz
0x1800087bd  call    cs:__imp_CharNextW
0x1800087c3  movzx   ecx, word ptr [rsi]
0x1800087c6  cmp     cx, 5Ch ; '\'
0x1800087ca  jnz     short loc_1800087E4
0x1800087cc  cmp     [rax], r14w
0x1800087d0  jnz     short loc_1800087E4
0x1800087d2  mov     rcx, rax; lpsz
0x1800087d5  mov     [rbx], r15w
0x1800087d9  call    cs:__imp_CharNextW
0x1800087df  mov     rsi, rax
0x1800087e2  jmp     short loc_1800087EB
0x1800087e4  mov     [rbx], cx
0x1800087e7  add     rsi, 2
0x1800087eb  add     rbx, 2
0x1800087ef  cmp     [rsi], r15w
0x1800087f3  jnz     short loc_1800087BA
0x1800087f5  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x1800087fa  mov     r15, qword ptr [rsp+22B0h+Data]
0x1800087ff  xor     esi, esi
0x180008801  mov     [rbx], esi
0x180008803  mov     r8, [rbp+21B0h+var_2160]
0x180008807  test    r8, r8
0x18000880a  jz      loc_180008B15
0x180008810  mov     r10d, esi
0x180008813  mov     r9, r8
0x180008816  mov     rcx, rdi
0x180008819  inc     rcx
0x18000881c  cmp     [r9+rcx*2], si
0x180008821  jnz     short loc_180008819
0x180008823  inc     ecx
0x180008825  lea     r9, [r9+rcx*2]
0x180008829  lea     r10d, [r10+rcx*2]
0x18000882d  cmp     ecx, 1
0x180008830  jnz     short loc_180008816
0x180008832  mov     [rsp+22B0h+cbData], r10d; cbData
0x180008837  lea     r9d, [rcx+6]; dwType
0x18000883b  mov     rcx, [r13+0]; hKey
0x18000883f  mov     rdx, r14; lpValueName
0x180008842  mov     [rsp+22B0h+lpData], r8; lpData
0x180008847  xor     r8d, r8d; Reserved
0x18000884a  call    cs:__imp_RegSetValueExW
0x180008850  mov     rbx, [rbp+21B0h+var_2160]
0x180008854  mov     edi, eax
0x180008856  jmp     short loc_18000885D
0x180008858  mov     edi, 0Eh
0x18000885d  lea     rax, [rbp+21B0h+var_2158]
0x180008861  cmp     rbx, rax
0x180008864  jz      loc_180008A8A
0x18000886a  lea     rcx, [rbp+21B0h+var_2160]
0x18000886e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180008873  jmp     loc_180008A8A
0x180008878  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x18000887d  mov     [rsp+22B0h+pulOut], esi
0x180008881  xor     r8d, r8d; dwFlags
0x180008884  lea     rcx, [rbp+21B0h+String1]; strIn
0x18000888b  xor     edx, edx; lcid
0x18000888d  call    cs:__imp_VarUI4FromStr
0x180008893  test    eax, eax
0x180008895  js      loc_180008ADC
0x18000889b  mov     eax, [rsp+22B0h+pulOut]
0x18000889f  mov     ecx, 4
0x1800088a4  mov     dword ptr [rsp+22B0h+Data], eax
0x1800088a8  mov     r9d, ecx; dwType
0x1800088ab  mov     [rsp+22B0h+cbData], ecx; cbData
0x1800088af  lea     rax, [rsp+22B0h+Data]
0x1800088b4  mov     rcx, [r13+0]; hKey
0x1800088b8  xor     r8d, r8d; Reserved
0x1800088bb  mov     rdx, r14; lpValueName
0x1800088be  mov     [rsp+22B0h+lpData], rax; lpData
0x1800088c3  call    cs:__imp_RegSetValueExW
0x1800088c9  mov     edi, eax
0x1800088cb  jmp     loc_180008A8A
0x1800088d0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800088d4  lea     rax, [rbp+21B0h+String1]
0x1800088db  mov     rsi, rdi
0x1800088de  xor     ecx, ecx
0x1800088e0  inc     rsi
0x1800088e3  cmp     [rax+rsi*2], cx
0x1800088e7  jnz     short loc_1800088E0
0x1800088e9  test    sil, 1
0x1800088ed  jnz     short loc_18000894D
0x1800088ef  mov     eax, esi
0x1800088f1  mov     [rsp+22B0h+var_2270], rcx
0x1800088f6  cdq
0x1800088f7  sub     eax, edx
0x1800088f9  sar     eax, 1
0x1800088fb  movsxd  r15, eax
0x1800088fe  mov     rbx, r15
0x180008901  jz      short loc_180008932
0x180008903  xor     edx, edx
0x180008905  mov     rax, rdi
0x180008908  div     rbx
0x18000890b  cmp     rax, 1
0x18000890f  jb      loc_180008AFF
0x180008915  cmp     rbx, 100h
0x18000891c  jbe     short loc_180008932
0x18000891e  mov     rdx, rbx
0x180008921  lea     rcx, [rsp+22B0h+var_2270]
0x180008926  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000892b  mov     rcx, [rsp+22B0h+var_2270]
0x180008930  jmp     short loc_18000893C
0x180008932  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180008937  mov     [rsp+22B0h+var_2270], rcx
0x18000893c  xor     edi, edi
0x18000893e  test    rcx, rcx
0x180008941  jnz     short loc_180008957
0x180008943  lea     rcx, [rsp+22B0h+var_2270]
0x180008948  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000894d  mov     eax, 80004005h
0x180008952  jmp     loc_180008ADC
0x180008957  mov     r8, rbx; Size
0x18000895a  xor     edx, edx; Val
0x18000895c  call    memset_0
0x180008961  mov     r10d, edi
0x180008964  test    esi, esi
0x180008966  jle     loc_180008A46
0x18000896c  mov     r14d, 30h ; '0'
0x180008972  mov     eax, r10d
0x180008975  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x18000897e  cmp     r9d, 61h ; 'a'
0x180008982  ja      short loc_1800089EE
0x180008984  jz      loc_180008A0F
0x18000898a  cmp     r9d, 38h ; '8'
0x18000898e  ja      short loc_1800089C2
0x180008990  jz      short loc_1800089BD
0x180008992  mov     ecx, r9d
0x180008995  sub     ecx, r14d
0x180008998  jz      short loc_1800089BD
0x18000899a  sub     ecx, 1
0x18000899d  jz      short loc_1800089BD
0x18000899f  sub     ecx, 1
0x1800089a2  jz      short loc_1800089BD
0x1800089a4  sub     ecx, 1
0x1800089a7  jz      short loc_1800089BD
0x1800089a9  sub     ecx, 1
0x1800089ac  jz      short loc_1800089BD
0x1800089ae  sub     ecx, 1
0x1800089b1  jz      short loc_1800089BD
0x1800089b3  sub     ecx, 1
0x1800089b6  jz      short loc_1800089BD
0x1800089b8  cmp     ecx, 1
0x1800089bb  jnz     short loc_180008A0A
0x1800089bd  sub     r9b, r14b
0x1800089c0  jmp     short loc_180008A13
0x1800089c2  mov     ecx, r9d
0x1800089c5  sub     ecx, 39h ; '9'
0x1800089c8  jz      short loc_1800089BD
0x1800089ca  sub     ecx, 8
0x1800089cd  jz      short loc_1800089E8
0x1800089cf  sub     ecx, 1
0x1800089d2  jz      short loc_1800089E8
0x1800089d4  sub     ecx, 1
0x1800089d7  jz      short loc_1800089E8
0x1800089d9  sub     ecx, 1
0x1800089dc  jz      short loc_1800089E8
0x1800089de  sub     ecx, 1
0x1800089e1  jz      short loc_1800089E8
0x1800089e3  cmp     ecx, 1
0x1800089e6  jnz     short loc_180008A0A
0x1800089e8  sub     r9b, 37h ; '7'
0x1800089ec  jmp     short loc_180008A13
0x1800089ee  mov     ecx, r9d
0x1800089f1  sub     ecx, 62h ; 'b'
0x1800089f4  jz      short loc_180008A0F
0x1800089f6  sub     ecx, 1
0x1800089f9  jz      short loc_180008A0F
0x1800089fb  sub     ecx, 1
0x1800089fe  jz      short loc_180008A0F
0x180008a00  sub     ecx, 1
0x180008a03  jz      short loc_180008A0F
0x180008a05  cmp     ecx, 1
0x180008a08  jz      short loc_180008A0F
0x180008a0a  mov     r9b, dil
0x180008a0d  jmp     short loc_180008A13
0x180008a0f  sub     r9b, 57h ; 'W'
0x180008a13  mov     rdx, [rsp+22B0h+var_2270]
0x180008a18  mov     eax, r10d
0x180008a1b  and     eax, 1
0x180008a1e  mov     r8d, r10d
0x180008a21  shl     eax, 2
0x180008a24  mov     ecx, 4
0x180008a29  shr     r8, 1
0x180008a2c  sub     ecx, eax
0x180008a2e  shl     r9b, cl
0x180008a31  inc     r10d
0x180008a34  or      [r8+rdx], r9b
0x180008a38  cmp     r10d, esi
0x180008a3b  jl      loc_180008972
0x180008a41  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180008a46  mov     rax, [rsp+22B0h+var_2270]
0x180008a4b  mov     r9d, 3; dwType
0x180008a51  mov     rcx, [r13+0]; hKey
0x180008a55  xor     r8d, r8d; Reserved
0x180008a58  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
