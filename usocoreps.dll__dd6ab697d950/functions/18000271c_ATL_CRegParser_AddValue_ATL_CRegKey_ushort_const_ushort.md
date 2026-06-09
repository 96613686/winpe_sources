# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000271c`
- end: `0x180002cf0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180003b5c`

## callees

- `0x180001510`
- `0x180002106`
- `0x18000271c`
- `0x180002cf8`
- `0x180002f18`
- `0x180002f30`
- `0x180003110`
- `0x1800031f4`
- `0x180004e40`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002a05`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002a05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800029a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002a3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002c3e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800029a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002a3d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180002c3e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000291c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002938`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002cc0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000291c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002938`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002cc0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800027ad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800027ad`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  HKEY *v5; // r12
  LPCWSTR *v6; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rax
  int v12; // eax
  BYTE *v13; // rdi
  const WCHAR *v14; // r13
  WCHAR *i; // r14
  const WCHAR *v16; // rax
  DWORD v17; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // esi
  const BYTE *v22; // rax
  DWORD v23; // r9d
  __int64 v24; // r14
  DWORD v25; // r12d
  size_t v26; // rdi
  BYTE *v27; // rcx
  HKEY *v28; // rsi
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  DWORD cbData; // [rsp+28h] [rbp-22D0h]
  ULONG pulOut; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v36; // [rsp+38h] [rbp-22C0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22B8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22B0h]
  ATL::CRegParser *v39; // [rsp+50h] [rbp-22A8h]
  const WCHAR *v40; // [rsp+60h] [rbp-2298h]
  struct ATL::CRegKey *v41; // [rsp+70h] [rbp-2288h]
  size_t v42; // [rsp+78h] [rbp-2280h]
  struct ATL::CRegKey *v43; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v44; // [rsp+88h] [rbp-2270h]
  BYTE *v45; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v48[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  WCHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v41 = (struct ATL::CRegKey *)a2;
  v6 = this;
  v36 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v39 = (ATL::CRegParser *)this;
  v43 = (struct ATL::CRegKey *)a2;
  v40 = a3;
  v44 = a4;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return -2147352567;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
      *v6 = CharNextW(*v6);
    result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
    if ( result >= 0 )
    {
      if ( v10 == 8 )
      {
        v32 = -1;
        do
          ++v32;
        while ( String1[v32] );
        cbData = 2 * v32 + 2;
        v22 = (const BYTE *)String1;
        v23 = 1;
        goto LABEL_47;
      }
      if ( v10 != 17 )
      {
        if ( v10 != 19 )
        {
          if ( v10 != 16392 )
          {
LABEL_93:
            Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v44);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = v11 + 2;
          lpData = 0;
          try
          {
            if ( !v12 )
              goto LABEL_24;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
              ATL::AtlThrowImpl(-2147024809);
            if ( (unsigned __int64)(2LL * v12) > 0x100 )
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v12);
              v13 = lpData;
            }
            else
            {
LABEL_24:
              v13 = v48;
              lpData = v48;
            }
          }
          catch ( ... )
          {
            v8 = 0;
            v13 = lpData;
            v5 = *(HKEY **)Data;
            v36 = v39;
            v14 = v40;
            goto LABEL_26;
          }
          v14 = lpValueName;
LABEL_26:
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v16 = CharNextW(i);
              if ( *i == 92 && *v16 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v16);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            v17 = 0;
            v18 = lpData;
            do
            {
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)&v18[2 * v19] );
              v20 = (unsigned int)(v19 + 1);
              v18 += 2 * v20;
              v17 += 2 * v20;
            }
            while ( (_DWORD)v20 != 1 );
            v21 = RegSetValueExW(*v5, v14, 0, 7u, lpData, v17);
            v13 = lpData;
          }
          else
          {
            v21 = 14;
          }
          if ( v13 != v48 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_42;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v22 = Data;
        v23 = 4;
LABEL_47:
        v21 = RegSetValueExW(*v5, a3, 0, v23, v22, cbData);
LABEL_43:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
        goto LABEL_93;
      }
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      *(_DWORD *)Data = v24;
      if ( (v24 & 1) != 0 )
        return -2147467259;
      try
      {
        v25 = (int)v24 / 2;
        v45 = 0;
        v26 = (int)v24 / 2;
        v42 = v26;
        if ( !((int)v24 / 2) )
          goto LABEL_56;
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v26) )
          ATL::AtlThrowImpl(-2147024809);
        if ( v26 > 0x100 )
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v45, v26);
          v27 = v45;
        }
        else
        {
LABEL_56:
          v27 = v46;
          v45 = v46;
        }
        v28 = (HKEY *)v41;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v24) = *(_DWORD *)Data;
        v27 = v45;
        v26 = v42;
        v36 = v39;
        v28 = (HKEY *)v43;
        lpValueName = v40;
        v25 = v42;
      }
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v45);
        return -2147467259;
      }
      memset_0(v27, 0, v26);
      v29 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_88:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, v45, v25);
        if ( v45 != v46 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v45);
LABEL_42:
        v6 = (LPCWSTR *)v36;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_86:
            v31 = v30 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v31 = 0;
          goto LABEL_87;
        }
        if ( v30 == 97 )
          goto LABEL_86;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_73;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_85;
        v31 = v30 - 55;
LABEL_87:
        v45[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v24 )
          goto LABEL_88;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v31 = v30 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000271c  push    rbx
0x18000271e  push    rsi
0x18000271f  push    rdi
0x180002720  push    r12
0x180002722  push    r13
0x180002724  push    r14
0x180002726  push    r15
0x180002728  mov     eax, 22C0h
0x18000272d  call    _alloca_probe
0x180002732  sub     rsp, rax
0x180002735  mov     rax, cs:__security_cookie
0x18000273c  xor     rax, rsp
0x18000273f  mov     [rsp+22F8h+var_48], rax
0x180002747  mov     r14, r8
0x18000274a  mov     [rsp+22F8h+lpValueName], r8
0x18000274f  mov     r12, rdx
0x180002752  mov     [rsp+22F8h+var_2288], rdx
0x180002757  mov     r15, rcx
0x18000275a  mov     [rsp+22F8h+var_22C0], rcx
0x18000275f  mov     qword ptr [rsp+22F8h+Data], rdx
0x180002764  mov     [rsp+22F8h+var_22A8], rcx
0x180002769  mov     [rsp+22F8h+var_2278], rdx
0x180002771  mov     [rsp+22F8h+var_2298], r8
0x180002776  mov     [rsp+22F8h+var_2270], r9
0x18000277e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180002786  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000278b  xor     ebx, ebx
0x18000278d  test    eax, eax
0x18000278f  js      short loc_1800027C3
0x180002791  mov     edi, ebx
0x180002793  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000279a  movsxd  rsi, edi
0x18000279d  add     rsi, rsi
0x1800027a0  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800027a5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x1800027ad  call    cs:__imp_lstrcmpiW
0x1800027b3  test    eax, eax
0x1800027b5  jz      short loc_1800027E6
0x1800027b7  inc     edi
0x1800027b9  cmp     edi, 4
0x1800027bc  jb      short loc_18000279A
0x1800027be  mov     eax, 80020009h
0x1800027c3  mov     rcx, [rsp+22F8h+var_48]
0x1800027cb  xor     rcx, rsp; StackCookie
0x1800027ce  call    __security_check_cookie
0x1800027d3  add     rsp, 22C0h
0x1800027da  pop     r15
0x1800027dc  pop     r14
0x1800027de  pop     r13
0x1800027e0  pop     r12
0x1800027e2  pop     rdi
0x1800027e3  pop     rsi
0x1800027e4  pop     rbx
0x1800027e5  retn
0x1800027e6  movzx   edi, word ptr [r13+rsi*8+8]
0x1800027ec  mov     esi, 13h
0x1800027f1  mov     rdx, [r15]
0x1800027f4  movzx   ecx, word ptr [rdx]
0x1800027f7  sub     ecx, 9
0x1800027fa  jz      loc_180002CBD
0x180002800  sub     ecx, 1
0x180002803  jz      loc_180002CBD
0x180002809  sub     ecx, 3
0x18000280c  jz      loc_180002CBD
0x180002812  cmp     ecx, esi
0x180002814  jz      loc_180002CBD
0x18000281a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180002822  mov     rcx, r15; this
0x180002825  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000282a  test    eax, eax
0x18000282c  js      short loc_1800027C3
0x18000282e  mov     r13d, 8
0x180002834  cmp     di, r13w
0x180002838  jz      loc_180002C6E
0x18000283e  cmp     di, 11h
0x180002842  jz      loc_180002A47
0x180002848  cmp     di, si
0x18000284b  jz      loc_1800029EF
0x180002851  mov     eax, 4008h
0x180002856  cmp     di, ax
0x180002859  jnz     loc_180002CA1
0x18000285f  lea     rcx, [rsp+22F8h+String1]
0x180002867  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000286b  mov     rax, rsi
0x18000286e  inc     rax
0x180002871  cmp     [rcx+rax*2], bx
0x180002875  jnz     short loc_18000286E
0x180002877  add     eax, 2
0x18000287a  mov     [rsp+22F8h+var_2158], rbx
0x180002882  test    eax, eax
0x180002884  jz      short loc_1800028BF
0x180002886  movsxd  rcx, eax
0x180002889  xor     edx, edx
0x18000288b  mov     rax, rsi
0x18000288e  div     rcx
0x180002891  cmp     rax, 2
0x180002895  jb      loc_180002CCE
0x18000289b  lea     rdx, [rcx+rcx]
0x18000289f  cmp     rdx, 100h
0x1800028a6  jbe     short loc_1800028BF
0x1800028a8  lea     rcx, [rsp+22F8h+var_2158]
0x1800028b0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800028b5  mov     rdi, [rsp+22F8h+var_2158]
0x1800028bd  jmp     short loc_1800028CF
0x1800028bf  lea     rdi, [rsp+22F8h+var_2150]
0x1800028c7  mov     [rsp+22F8h+var_2158], rdi
0x1800028cf  mov     r13, [rsp+22F8h+lpValueName]
0x1800028d4  jmp     short loc_1800028F8
0x1800028d6  xor     ebx, ebx
0x1800028d8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800028dc  mov     rdi, [rsp+22F8h+var_2158]
0x1800028e4  mov     r12, qword ptr [rsp+22F8h+Data]
0x1800028e9  mov     rax, [rsp+22F8h+var_22A8]
0x1800028ee  mov     [rsp+22F8h+var_22C0], rax
0x1800028f3  mov     r13, [rsp+22F8h+var_2298]
0x1800028f8  test    rdi, rdi
0x1800028fb  jz      loc_1800029B7
0x180002901  lea     r14, [rsp+22F8h+String1]
0x180002909  cmp     [rsp+22F8h+String1], bx
0x180002911  jz      short loc_180002954
0x180002913  mov     r15d, 30h ; '0'
0x180002919  mov     rcx, r14; lpsz
0x18000291c  call    cs:__imp_CharNextW
0x180002922  movzx   ecx, word ptr [r14]
0x180002926  cmp     cx, 5Ch ; '\'
0x18000292a  jnz     short loc_180002943
0x18000292c  cmp     [rax], r15w
0x180002930  jnz     short loc_180002943
0x180002932  mov     [rdi], bx
0x180002935  mov     rcx, rax; lpsz
0x180002938  call    cs:__imp_CharNextW
0x18000293e  mov     r14, rax
0x180002941  jmp     short loc_18000294A
0x180002943  mov     [rdi], cx
0x180002946  add     r14, 2
0x18000294a  add     rdi, 2
0x18000294e  cmp     [r14], bx
0x180002952  jnz     short loc_180002919
0x180002954  mov     dword ptr [rdi], 0
0x18000295a  mov     r8, [rsp+22F8h+var_2158]
0x180002962  test    r8, r8
0x180002965  jz      loc_180002CD9
0x18000296b  mov     r10d, ebx
0x18000296e  mov     r9, r8
0x180002971  mov     rcx, rsi
0x180002974  inc     rcx
0x180002977  cmp     [r9+rcx*2], bx
0x18000297c  jnz     short loc_180002974
0x18000297e  inc     ecx
0x180002980  lea     r9, [r9+rcx*2]
0x180002984  lea     r10d, [r10+rcx*2]
0x180002988  cmp     ecx, 1
0x18000298b  jnz     short loc_180002971
0x18000298d  mov     [rsp+22F8h+cbData], r10d; cbData
0x180002992  mov     [rsp+22F8h+lpData], r8; lpData
0x180002997  lea     r9d, [rcx+6]; dwType
0x18000299b  xor     r8d, r8d; Reserved
0x18000299e  mov     rdx, r13; lpValueName
0x1800029a1  mov     rcx, [r12]; hKey
0x1800029a5  call    cs:__imp_RegSetValueExW
0x1800029ab  mov     esi, eax
0x1800029ad  mov     rdi, [rsp+22F8h+var_2158]
0x1800029b5  jmp     short loc_1800029BC
0x1800029b7  mov     esi, 0Eh
0x1800029bc  lea     rax, [rsp+22F8h+var_2150]
0x1800029c4  cmp     rdi, rax
0x1800029c7  jz      short loc_1800029D6
0x1800029c9  lea     rcx, [rsp+22F8h+var_2158]
0x1800029d1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800029d6  mov     r15, [rsp+22F8h+var_22C0]
0x1800029db  test    esi, esi
0x1800029dd  jz      loc_180002CA1
0x1800029e3  mov     ecx, esi; unsigned int
0x1800029e5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800029ea  jmp     loc_1800027C3
0x1800029ef  mov     [rsp+22F8h+pulOut], ebx
0x1800029f3  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x1800029f8  xor     r8d, r8d; dwFlags
0x1800029fb  xor     edx, edx; lcid
0x1800029fd  lea     rcx, [rsp+22F8h+String1]; strIn
0x180002a05  call    cs:__imp_VarUI4FromStr
0x180002a0b  test    eax, eax
0x180002a0d  js      loc_1800027C3
0x180002a13  mov     eax, [rsp+22F8h+pulOut]
0x180002a17  mov     dword ptr [rsp+22F8h+Data], eax
0x180002a1b  mov     [rsp+22F8h+cbData], 4; cbData
0x180002a23  lea     rax, [rsp+22F8h+Data]
0x180002a28  mov     r9d, 4; dwType
0x180002a2e  mov     [rsp+22F8h+lpData], rax; lpData
0x180002a33  xor     r8d, r8d; Reserved
0x180002a36  mov     rdx, r14; lpValueName
0x180002a39  mov     rcx, [r12]; hKey
0x180002a3d  call    cs:__imp_RegSetValueExW
0x180002a43  mov     esi, eax
0x180002a45  jmp     short loc_1800029DB
0x180002a47  lea     rax, [rsp+22F8h+String1]
0x180002a4f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002a53  mov     r14, rsi
0x180002a56  inc     r14
0x180002a59  cmp     [rax+r14*2], bx
0x180002a5e  jnz     short loc_180002A56
0x180002a60  mov     dword ptr [rsp+22F8h+Data], r14d
0x180002a65  test    r14b, 1
0x180002a69  jnz     loc_180002B23
0x180002a6f  mov     eax, r14d
0x180002a72  cdq
0x180002a73  sub     eax, edx
0x180002a75  sar     eax, 1
0x180002a77  movsxd  r12, eax
0x180002a7a  mov     [rsp+22F8h+var_2268], rbx
0x180002a82  mov     rdi, r12
0x180002a85  mov     [rsp+22F8h+var_2280], r12
0x180002a8a  test    eax, eax
0x180002a8c  jz      short loc_180002AC3
0x180002a8e  xor     edx, edx
0x180002a90  mov     rax, rsi
0x180002a93  div     rdi
0x180002a96  cmp     rax, 1
0x180002a9a  jb      loc_180002CE4
0x180002aa0  cmp     rdi, 100h
0x180002aa7  jbe     short loc_180002AC3
0x180002aa9  mov     rdx, rdi
0x180002aac  lea     rcx, [rsp+22F8h+var_2268]
0x180002ab4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002ab9  mov     rcx, [rsp+22F8h+var_2268]
0x180002ac1  jmp     short loc_180002AD3
0x180002ac3  lea     rcx, [rsp+22F8h+var_2260]
0x180002acb  mov     [rsp+22F8h+var_2268], rcx
0x180002ad3  mov     rsi, [rsp+22F8h+var_2288]
0x180002ad8  jmp     short loc_180002B11
0x180002ada  xor     ebx, ebx
0x180002adc  lea     r13d, [rbx+8]
0x180002ae0  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180002ae5  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180002aed  mov     rdi, [rsp+22F8h+var_2280]
0x180002af2  mov     rax, [rsp+22F8h+var_22A8]
0x180002af7  mov     [rsp+22F8h+var_22C0], rax
0x180002afc  mov     rsi, [rsp+22F8h+var_2278]
0x180002b04  mov     rax, [rsp+22F8h+var_2298]
0x180002b09  mov     [rsp+22F8h+lpValueName], rax
0x180002b0e  mov     r12d, edi
0x180002b11  test    rcx, rcx
0x180002b14  jnz     short loc_180002B2D
0x180002b16  lea     rcx, [rsp+22F8h+var_2268]
0x180002b1e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002b23  mov     eax, 80004005h
0x180002b28  jmp     loc_1800027C3
0x180002b2d  mov     r8, rdi; Size
0x180002b30  xor     edx, edx; Val
0x180002b32  call    memset_0
0x180002b37  mov     r10d, ebx
0x180002b3a  test    r14d, r14d
0x180002b3d  jle     loc_180002C1B
0x180002b43  mov     r15d, 30h ; '0'
0x180002b49  mov     eax, r10d
0x180002b4c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180002b54  cmp     edx, 61h ; 'a'
0x180002b57  ja      short loc_180002BC6
0x180002b59  jz      loc_180002BE6
0x180002b5f  cmp     edx, 38h ; '8'
0x180002b62  ja      short loc_180002B98
0x180002b64  jz      short loc_180002B90
0x180002b66  mov     ecx, edx
0x180002b68  sub     ecx, r15d
0x180002b6b  jz      short loc_180002B90
0x180002b6d  sub     ecx, 1
0x180002b70  jz      short loc_180002B90
0x180002b72  sub     ecx, 1
0x180002b75  jz      short loc_180002B90
0x180002b77  sub     ecx, 1
0x180002b7a  jz      short loc_180002B90
0x180002b7c  sub     ecx, 1
0x180002b7f  jz      short loc_180002B90
0x180002b81  sub     ecx, 1
0x180002b84  jz      short loc_180002B90
0x180002b86  sub     ecx, 1
0x180002b89  jz      short loc_180002B90
0x180002b8b  cmp     ecx, 1
0x180002b8e  jnz     short loc_180002BE1
0x180002b90  mov     r9d, edx
0x180002b93  sub     r9d, r15d
0x180002b96  jmp     short loc_180002BEA
0x180002b98  mov     r9d, edx
0x180002b9b  mov     ecx, edx
0x180002b9d  sub     ecx, 39h ; '9'
0x180002ba0  jz      short loc_180002B90
0x180002ba2  sub     ecx, r13d
0x180002ba5  jz      short loc_180002BC0
0x180002ba7  sub     ecx, 1
0x180002baa  jz      short loc_180002BC0
0x180002bac  sub     ecx, 1
0x180002baf  jz      short loc_180002BC0
0x180002bb1  sub     ecx, 1
0x180002bb4  jz      short loc_180002BC0
0x180002bb6  sub     ecx, 1
0x180002bb9  jz      short loc_180002BC0
0x180002bbb  cmp     ecx, 1
0x180002bbe  jnz     short loc_180002BE1
0x180002bc0  add     r9d, 0FFFFFFC9h
0x180002bc4  jmp     short loc_180002BEA
  ... truncated ...
```
