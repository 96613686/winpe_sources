# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x140002424`
- end: `0x140002920`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `HRESULT __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140004954`

## callees

- `0x140001490`
- `0x140001e30`
- `0x140002424`
- `0x140002928`
- `0x140002a3c`
- `0x140003298`
- `0x140003754`
- `0x140003d78`
- `0x140006640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000264a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400026c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140002865`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000264a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400026c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140002865`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400024ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400025bd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400025d9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400024ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400025bd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400025d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000249d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x14000249d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000268d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000268d`

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
0x140002424  push    rbp
0x140002426  push    rbx
0x140002427  push    rsi
0x140002428  push    rdi
0x140002429  push    r12
0x14000242b  push    r13
0x14000242d  push    r14
0x14000242f  push    r15
0x140002431  lea     rbp, [rsp-2178h]
0x140002439  mov     eax, 2278h
0x14000243e  call    _alloca_probe
0x140002443  sub     rsp, rax
0x140002446  mov     rax, cs:__security_cookie
0x14000244d  xor     rax, rsp
0x140002450  mov     [rbp+21B0h+var_50], rax
0x140002457  mov     r13, rdx
0x14000245a  mov     qword ptr [rsp+22B0h+Data], r9
0x14000245f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x140002466  mov     qword ptr [rsp+22B0h+pulOut], r8
0x14000246b  mov     r15, r9
0x14000246e  mov     r14, r8
0x140002471  mov     r12, rcx
0x140002474  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140002479  xor     esi, esi
0x14000247b  test    eax, eax
0x14000247d  js      loc_1400028DC
0x140002483  mov     ebx, esi
0x140002485  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000248c  movsxd  rdi, ebx
0x14000248f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x140002496  add     rdi, rdi
0x140002499  mov     rdx, [rax+rdi*8]; lpString2
0x14000249d  call    cs:__imp_lstrcmpiW
0x1400024a3  test    eax, eax
0x1400024a5  jz      short loc_1400024BF
0x1400024a7  inc     ebx
0x1400024a9  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1400024b0  cmp     ebx, 4
0x1400024b3  jb      short loc_14000248C
0x1400024b5  mov     eax, 80020009h
0x1400024ba  jmp     loc_1400028DC
0x1400024bf  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1400024c6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1400024cb  mov     edi, 13h
0x1400024d0  mov     rdx, [r12]
0x1400024d4  movzx   ecx, word ptr [rdx]
0x1400024d7  sub     ecx, 9
0x1400024da  jz      short loc_1400024EA
0x1400024dc  sub     ecx, 1
0x1400024df  jz      short loc_1400024EA
0x1400024e1  sub     ecx, 3
0x1400024e4  jz      short loc_1400024EA
0x1400024e6  cmp     ecx, edi
0x1400024e8  jnz     short loc_1400024F9
0x1400024ea  mov     rcx, rdx; lpsz
0x1400024ed  call    cs:__imp_CharNextW
0x1400024f3  mov     [r12], rax
0x1400024f7  jmp     short loc_1400024D0
0x1400024f9  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x140002500  mov     rcx, r12; this
0x140002503  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140002508  test    eax, eax
0x14000250a  js      loc_1400028DC
0x140002510  mov     eax, 8
0x140002515  cmp     bx, ax
0x140002518  jz      loc_140002897
0x14000251e  cmp     bx, 11h
0x140002522  jz      loc_1400026D0
0x140002528  cmp     bx, di
0x14000252b  jz      loc_140002678
0x140002531  mov     eax, 4008h
0x140002536  cmp     bx, ax
0x140002539  jnz     loc_1400028C8
0x14000253f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140002543  mov     [rbp+21B0h+var_2160], rsi
0x140002547  mov     rax, rdi
0x14000254a  lea     rcx, [rbp+21B0h+String1]
0x140002551  inc     rax
0x140002554  cmp     [rcx+rax*2], si
0x140002558  jnz     short loc_140002551
0x14000255a  add     eax, 2
0x14000255d  movsxd  rcx, eax
0x140002560  jz      short loc_140002590
0x140002562  xor     edx, edx
0x140002564  mov     rax, rdi
0x140002567  div     rcx
0x14000256a  cmp     rax, 2
0x14000256e  jb      loc_14000290A
0x140002574  lea     rdx, [rcx+rcx]
0x140002578  cmp     rdx, 100h
0x14000257f  jbe     short loc_140002590
0x140002581  lea     rcx, [rbp+21B0h+var_2160]
0x140002585  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000258a  mov     rbx, [rbp+21B0h+var_2160]
0x14000258e  jmp     short loc_140002598
0x140002590  lea     rbx, [rbp+21B0h+var_2158]
0x140002594  mov     [rbp+21B0h+var_2160], rbx
0x140002598  test    rbx, rbx
0x14000259b  jz      loc_140002658
0x1400025a1  xor     eax, eax
0x1400025a3  lea     rsi, [rbp+21B0h+String1]
0x1400025aa  cmp     [rbp+21B0h+String1], ax
0x1400025b1  jz      short loc_1400025FF
0x1400025b3  lea     r14d, [rax+30h]
0x1400025b7  xor     r15d, r15d
0x1400025ba  mov     rcx, rsi; lpsz
0x1400025bd  call    cs:__imp_CharNextW
0x1400025c3  movzx   ecx, word ptr [rsi]
0x1400025c6  cmp     cx, 5Ch ; '\'
0x1400025ca  jnz     short loc_1400025E4
0x1400025cc  cmp     [rax], r14w
0x1400025d0  jnz     short loc_1400025E4
0x1400025d2  mov     rcx, rax; lpsz
0x1400025d5  mov     [rbx], r15w
0x1400025d9  call    cs:__imp_CharNextW
0x1400025df  mov     rsi, rax
0x1400025e2  jmp     short loc_1400025EB
0x1400025e4  mov     [rbx], cx
0x1400025e7  add     rsi, 2
0x1400025eb  add     rbx, 2
0x1400025ef  cmp     [rsi], r15w
0x1400025f3  jnz     short loc_1400025BA
0x1400025f5  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x1400025fa  mov     r15, qword ptr [rsp+22B0h+Data]
0x1400025ff  xor     esi, esi
0x140002601  mov     [rbx], esi
0x140002603  mov     r8, [rbp+21B0h+var_2160]
0x140002607  test    r8, r8
0x14000260a  jz      loc_140002915
0x140002610  mov     r10d, esi
0x140002613  mov     r9, r8
0x140002616  mov     rcx, rdi
0x140002619  inc     rcx
0x14000261c  cmp     [r9+rcx*2], si
0x140002621  jnz     short loc_140002619
0x140002623  inc     ecx
0x140002625  lea     r9, [r9+rcx*2]
0x140002629  lea     r10d, [r10+rcx*2]
0x14000262d  cmp     ecx, 1
0x140002630  jnz     short loc_140002616
0x140002632  mov     [rsp+22B0h+cbData], r10d; cbData
0x140002637  lea     r9d, [rcx+6]; dwType
0x14000263b  mov     rcx, [r13+0]; hKey
0x14000263f  mov     rdx, r14; lpValueName
0x140002642  mov     [rsp+22B0h+lpData], r8; lpData
0x140002647  xor     r8d, r8d; Reserved
0x14000264a  call    cs:__imp_RegSetValueExW
0x140002650  mov     rbx, [rbp+21B0h+var_2160]
0x140002654  mov     edi, eax
0x140002656  jmp     short loc_14000265D
0x140002658  mov     edi, 0Eh
0x14000265d  lea     rax, [rbp+21B0h+var_2158]
0x140002661  cmp     rbx, rax
0x140002664  jz      loc_14000288A
0x14000266a  lea     rcx, [rbp+21B0h+var_2160]
0x14000266e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140002673  jmp     loc_14000288A
0x140002678  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x14000267d  mov     [rsp+22B0h+pulOut], esi
0x140002681  xor     r8d, r8d; dwFlags
0x140002684  lea     rcx, [rbp+21B0h+String1]; strIn
0x14000268b  xor     edx, edx; lcid
0x14000268d  call    cs:__imp_VarUI4FromStr
0x140002693  test    eax, eax
0x140002695  js      loc_1400028DC
0x14000269b  mov     eax, [rsp+22B0h+pulOut]
0x14000269f  mov     ecx, 4
0x1400026a4  mov     dword ptr [rsp+22B0h+Data], eax
0x1400026a8  mov     r9d, ecx; dwType
0x1400026ab  mov     [rsp+22B0h+cbData], ecx; cbData
0x1400026af  lea     rax, [rsp+22B0h+Data]
0x1400026b4  mov     rcx, [r13+0]; hKey
0x1400026b8  xor     r8d, r8d; Reserved
0x1400026bb  mov     rdx, r14; lpValueName
0x1400026be  mov     [rsp+22B0h+lpData], rax; lpData
0x1400026c3  call    cs:__imp_RegSetValueExW
0x1400026c9  mov     edi, eax
0x1400026cb  jmp     loc_14000288A
0x1400026d0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400026d4  lea     rax, [rbp+21B0h+String1]
0x1400026db  mov     rsi, rdi
0x1400026de  xor     ecx, ecx
0x1400026e0  inc     rsi
0x1400026e3  cmp     [rax+rsi*2], cx
0x1400026e7  jnz     short loc_1400026E0
0x1400026e9  test    sil, 1
0x1400026ed  jnz     short loc_14000274D
0x1400026ef  mov     eax, esi
0x1400026f1  mov     [rsp+22B0h+var_2270], rcx
0x1400026f6  cdq
0x1400026f7  sub     eax, edx
0x1400026f9  sar     eax, 1
0x1400026fb  movsxd  r15, eax
0x1400026fe  mov     rbx, r15
0x140002701  jz      short loc_140002732
0x140002703  xor     edx, edx
0x140002705  mov     rax, rdi
0x140002708  div     rbx
0x14000270b  cmp     rax, 1
0x14000270f  jb      loc_1400028FF
0x140002715  cmp     rbx, 100h
0x14000271c  jbe     short loc_140002732
0x14000271e  mov     rdx, rbx
0x140002721  lea     rcx, [rsp+22B0h+var_2270]
0x140002726  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000272b  mov     rcx, [rsp+22B0h+var_2270]
0x140002730  jmp     short loc_14000273C
0x140002732  lea     rcx, [rsp+22B0h+var_2268]; void *
0x140002737  mov     [rsp+22B0h+var_2270], rcx
0x14000273c  xor     edi, edi
0x14000273e  test    rcx, rcx
0x140002741  jnz     short loc_140002757
0x140002743  lea     rcx, [rsp+22B0h+var_2270]
0x140002748  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000274d  mov     eax, 80004005h
0x140002752  jmp     loc_1400028DC
0x140002757  mov     r8, rbx; Size
0x14000275a  xor     edx, edx; Val
0x14000275c  call    memset_0
0x140002761  mov     r10d, edi
0x140002764  test    esi, esi
0x140002766  jle     loc_140002846
0x14000276c  mov     r14d, 30h ; '0'
0x140002772  mov     eax, r10d
0x140002775  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x14000277e  cmp     r9d, 61h ; 'a'
0x140002782  ja      short loc_1400027EE
0x140002784  jz      loc_14000280F
0x14000278a  cmp     r9d, 38h ; '8'
0x14000278e  ja      short loc_1400027C2
0x140002790  jz      short loc_1400027BD
0x140002792  mov     ecx, r9d
0x140002795  sub     ecx, r14d
0x140002798  jz      short loc_1400027BD
0x14000279a  sub     ecx, 1
0x14000279d  jz      short loc_1400027BD
0x14000279f  sub     ecx, 1
0x1400027a2  jz      short loc_1400027BD
0x1400027a4  sub     ecx, 1
0x1400027a7  jz      short loc_1400027BD
0x1400027a9  sub     ecx, 1
0x1400027ac  jz      short loc_1400027BD
0x1400027ae  sub     ecx, 1
0x1400027b1  jz      short loc_1400027BD
0x1400027b3  sub     ecx, 1
0x1400027b6  jz      short loc_1400027BD
0x1400027b8  cmp     ecx, 1
0x1400027bb  jnz     short loc_14000280A
0x1400027bd  sub     r9b, r14b
0x1400027c0  jmp     short loc_140002813
0x1400027c2  mov     ecx, r9d
0x1400027c5  sub     ecx, 39h ; '9'
0x1400027c8  jz      short loc_1400027BD
0x1400027ca  sub     ecx, 8
0x1400027cd  jz      short loc_1400027E8
0x1400027cf  sub     ecx, 1
0x1400027d2  jz      short loc_1400027E8
0x1400027d4  sub     ecx, 1
0x1400027d7  jz      short loc_1400027E8
0x1400027d9  sub     ecx, 1
0x1400027dc  jz      short loc_1400027E8
0x1400027de  sub     ecx, 1
0x1400027e1  jz      short loc_1400027E8
0x1400027e3  cmp     ecx, 1
0x1400027e6  jnz     short loc_14000280A
0x1400027e8  sub     r9b, 37h ; '7'
0x1400027ec  jmp     short loc_140002813
0x1400027ee  mov     ecx, r9d
0x1400027f1  sub     ecx, 62h ; 'b'
0x1400027f4  jz      short loc_14000280F
0x1400027f6  sub     ecx, 1
0x1400027f9  jz      short loc_14000280F
0x1400027fb  sub     ecx, 1
0x1400027fe  jz      short loc_14000280F
0x140002800  sub     ecx, 1
0x140002803  jz      short loc_14000280F
0x140002805  cmp     ecx, 1
0x140002808  jz      short loc_14000280F
0x14000280a  mov     r9b, dil
0x14000280d  jmp     short loc_140002813
0x14000280f  sub     r9b, 57h ; 'W'
0x140002813  mov     rdx, [rsp+22B0h+var_2270]
0x140002818  mov     eax, r10d
0x14000281b  and     eax, 1
0x14000281e  mov     r8d, r10d
0x140002821  shl     eax, 2
0x140002824  mov     ecx, 4
0x140002829  shr     r8, 1
0x14000282c  sub     ecx, eax
0x14000282e  shl     r9b, cl
0x140002831  inc     r10d
0x140002834  or      [r8+rdx], r9b
0x140002838  cmp     r10d, esi
0x14000283b  jl      loc_140002772
0x140002841  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x140002846  mov     rax, [rsp+22B0h+var_2270]
0x14000284b  mov     r9d, 3; dwType
0x140002851  mov     rcx, [r13+0]; hKey
0x140002855  xor     r8d, r8d; Reserved
0x140002858  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
