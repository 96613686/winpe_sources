# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x18000728c`
- end: `0x1800078b6`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1578`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007ee0`

## callees

- `0x180006b44`
- `0x180006b74`
- `0x18000728c`
- `0x1800078c8`
- `0x180007d20`
- `0x180007d34`
- `0x18002fda9`
- `0x18002ffd0`
- `0x1800369a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007536`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800075ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800077ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007536`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800075ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800077ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800074ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800074c8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007869`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800074ac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800074c8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007869`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007309`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007327`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007347`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007365`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007309`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007327`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007347`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007365`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180007596`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180007596`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
{
  const WCHAR *v4; // r12
  HKEY *v5; // r13
  LPCWSTR *v6; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int64 v10; // rax
  int v11; // edi
  BYTE *v12; // rdi
  WCHAR *i; // r14
  const WCHAR *v14; // rax
  LSTATUS v15; // esi
  DWORD v16; // r9d
  BYTE *v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  const BYTE *v20; // rax
  DWORD v21; // r9d
  __int64 v22; // rdi
  size_t v23; // r12
  BYTE *v24; // rcx
  int v25; // r10d
  __int64 v26; // r11
  unsigned int v27; // edx
  char v28; // r9
  __int64 v29; // rsi
  int Token; // eax
  DWORD cbData; // [rsp+28h] [rbp-22C0h]
  ATL::CRegParser *v32; // [rsp+30h] [rbp-22B8h]
  ULONG pulOut; // [rsp+70h] [rbp-2278h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-2270h] BYREF
  BYTE *v39; // [rsp+80h] [rbp-2268h] BYREF
  _BYTE v40[264]; // [rsp+88h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+190h] [rbp-2158h] BYREF
  _BYTE v42[264]; // [rsp+198h] [rbp-2150h] BYREF
  wchar_t String1[4096]; // [rsp+2A0h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v32 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    if ( lstrcmpiW(String1, L"S") )
    {
      if ( lstrcmpiW(String1, L"M") )
      {
        if ( lstrcmpiW(String1, L"D") )
        {
          if ( lstrcmpiW(String1, L"B") )
            return -2147352567;
          v9 = 17;
        }
        else
        {
          v9 = 19;
        }
      }
      else
      {
        v9 = 16392;
      }
    }
    else
    {
      v9 = 8;
    }
    while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
      *v6 = CharNextW(*v6);
    result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
    if ( result >= 0 )
    {
      if ( v9 == 8 )
      {
        v29 = -1;
        do
          ++v29;
        while ( String1[v29] );
        cbData = 2 * v29 + 2;
        v20 = (const BYTE *)String1;
        v21 = 1;
        goto LABEL_48;
      }
      if ( v9 != 17 )
      {
        if ( v9 != 19 )
        {
          v10 = -1;
          do
            ++v10;
          while ( String1[v10] );
          v11 = v10 + 2;
          memset_0(&lpData, 0, 0x108u);
          try
          {
            lpData = 0;
            if ( !v11 )
              goto LABEL_25;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v11 < 2 )
              ATL::AtlThrowImpl(-2147024362);
            if ( (unsigned __int64)(2LL * v11) > 0x100 )
            {
              ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v11);
              v12 = lpData;
            }
            else
            {
LABEL_25:
              v12 = v42;
              lpData = v42;
            }
          }
          catch ( ... )
          {
            v8 = 0;
            v12 = lpData;
            v32 = (ATL::CRegParser *)this;
            v5 = *(HKEY **)Data;
            v4 = a3;
          }
          if ( v12 )
          {
            for ( i = String1; *i; v12 += 2 )
            {
              v14 = CharNextW(i);
              if ( *i == 92 && *v14 == 48 )
              {
                *(_WORD *)v12 = 0;
                i = CharNextW(v14);
              }
              else
              {
                *(_WORD *)v12 = *i++;
              }
            }
            *(_DWORD *)v12 = 0;
            v12 = lpData;
            if ( lpData )
            {
              v16 = 0;
              v17 = lpData;
              do
              {
                v18 = -1;
                do
                  ++v18;
                while ( *(_WORD *)&v17[2 * v18] );
                v19 = (unsigned int)(v18 + 1);
                v17 += 2 * v19;
                v16 += 2 * v19;
              }
              while ( (_DWORD)v19 != 1 );
              v15 = RegSetValueExW(*v5, v4, 0, 7u, lpData, v16);
              v12 = lpData;
            }
            else
            {
              v15 = 13;
            }
          }
          else
          {
            v15 = 14;
          }
          if ( v12 != v42 )
            ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&lpData);
LABEL_43:
          v6 = (LPCWSTR *)v32;
          goto LABEL_44;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v20 = Data;
        v21 = 4;
LABEL_48:
        v15 = RegSetValueExW(*v5, v4, 0, v21, v20, cbData);
LABEL_44:
        if ( v15 )
          return ATL::AtlHresultFromWin32(v15);
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, a4);
        if ( Token < 0 )
          return Token;
        return v8;
      }
      v22 = -1;
      do
        ++v22;
      while ( String1[v22] );
      *(_DWORD *)Data = v22;
      if ( (v22 & 1) != 0 )
        return -2147467259;
      v23 = (int)v22 / 2;
      pulOut = (int)v22 / 2;
      memset_0(&v39, 0, 0x108u);
      v39 = 0;
      if ( !(_DWORD)v23 )
        goto LABEL_56;
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v23) )
        ATL::AtlThrowImpl(-2147024362);
      if ( v23 > 0x100 )
      {
        ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v39, v23);
        v24 = v39;
      }
      else
      {
LABEL_56:
        v24 = v40;
        v39 = v40;
      }
      if ( !v24 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v39);
        return -2147467259;
      }
      memset_0(v24, 0, v23);
      v25 = 0;
      if ( (int)v22 <= 0 )
      {
LABEL_88:
        v15 = RegSetValueExW(*v5, a3, 0, 3u, v39, v23);
        if ( v39 != v40 )
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v39);
        goto LABEL_43;
      }
      v26 = 0;
      while ( 1 )
      {
        v27 = String1[v26];
        if ( v27 > 0x61 )
        {
          if ( v27 == 98 || v27 == 99 || v27 == 100 || v27 - 101 < 2 )
          {
LABEL_86:
            v28 = v27 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v28 = 0;
          goto LABEL_87;
        }
        if ( v27 == 97 )
          goto LABEL_86;
        if ( v27 <= 0x38 )
          break;
        if ( v27 == 57 )
          goto LABEL_73;
        if ( v27 != 65 && v27 != 66 && v27 != 67 && v27 != 68 && v27 - 69 > 1 )
          goto LABEL_85;
        v28 = v27 - 55;
LABEL_87:
        v39[v25 / 2] |= v28 << (4 - 4 * (v25 & 1));
        ++v25;
        if ( ++v26 >= (int)v22 )
          goto LABEL_88;
      }
      if ( v27 != 56 && v27 != 48 && v27 != 49 && v27 != 50 && v27 != 51 && v27 != 52 && v27 != 53 && v27 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v28 = v27 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000728c  push    rbx
0x18000728e  push    rsi
0x18000728f  push    rdi
0x180007290  push    r12
0x180007292  push    r13
0x180007294  push    r14
0x180007296  push    r15
0x180007298  mov     eax, 22B0h
0x18000729d  call    _alloca_probe
0x1800072a2  sub     rsp, rax
0x1800072a5  mov     rax, cs:__security_cookie
0x1800072ac  xor     rax, rsp
0x1800072af  mov     [rsp+22E8h+var_48], rax
0x1800072b7  mov     r12, r8
0x1800072ba  mov     [rsp+22E8h+lpValueName], r8
0x1800072bf  mov     r13, rdx
0x1800072c2  mov     r15, rcx
0x1800072c5  mov     [rsp+22E8h+var_22B8], rcx
0x1800072ca  mov     qword ptr [rsp+22E8h+Data], rdx
0x1800072cf  mov     [rsp+22E8h+var_22B0], rcx
0x1800072d4  mov     [rsp+22E8h+var_2288], rdx
0x1800072d9  mov     [rsp+22E8h+var_22A8], r8
0x1800072de  mov     [rsp+22E8h+var_2280], r9
0x1800072e3  lea     rdx, [rsp+22E8h+String1]; wchar_t *
0x1800072eb  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800072f0  xor     ebx, ebx
0x1800072f2  test    eax, eax
0x1800072f4  js      loc_18000787C
0x1800072fa  lea     rdx, String2; "S"
0x180007301  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180007309  call    cs:__imp_lstrcmpiW
0x18000730f  test    eax, eax
0x180007311  jnz     short loc_180007318
0x180007313  lea     edi, [rbx+8]
0x180007316  jmp     short loc_180007376
0x180007318  lea     rdx, aM; "M"
0x18000731f  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180007327  call    cs:__imp_lstrcmpiW
0x18000732d  test    eax, eax
0x18000732f  jnz     short loc_180007338
0x180007331  mov     edi, 4008h
0x180007336  jmp     short loc_180007376
0x180007338  lea     rdx, aD; "D"
0x18000733f  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180007347  call    cs:__imp_lstrcmpiW
0x18000734d  test    eax, eax
0x18000734f  jnz     short loc_180007356
0x180007351  lea     edi, [rax+13h]
0x180007354  jmp     short loc_180007376
0x180007356  lea     rdx, aB; "B"
0x18000735d  lea     rcx, [rsp+22E8h+String1]; lpString1
0x180007365  call    cs:__imp_lstrcmpiW
0x18000736b  test    eax, eax
0x18000736d  jnz     loc_180007877
0x180007373  lea     edi, [rax+11h]
0x180007376  mov     rdx, [r15]
0x180007379  movzx   ecx, word ptr [rdx]
0x18000737c  sub     ecx, 9
0x18000737f  jz      loc_180007866
0x180007385  sub     ecx, 1
0x180007388  jz      loc_180007866
0x18000738e  sub     ecx, 3
0x180007391  jz      loc_180007866
0x180007397  cmp     ecx, 13h
0x18000739a  jz      loc_180007866
0x1800073a0  lea     rdx, [rsp+22E8h+String1]; wchar_t *
0x1800073a8  mov     rcx, r15; this
0x1800073ab  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800073b0  test    eax, eax
0x1800073b2  js      loc_18000787C
0x1800073b8  cmp     edi, 8
0x1800073bb  jz      loc_18000781D
0x1800073c1  cmp     edi, 11h
0x1800073c4  jz      loc_1800075D8
0x1800073ca  cmp     edi, 13h
0x1800073cd  jz      loc_180007580
0x1800073d3  cmp     edi, 4008h
0x1800073d9  jnz     loc_180007850
0x1800073df  lea     rcx, [rsp+22E8h+String1]
0x1800073e7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800073eb  mov     rax, rsi
0x1800073ee  inc     rax
0x1800073f1  cmp     [rcx+rax*2], bx
0x1800073f5  jnz     short loc_1800073EE
0x1800073f7  lea     edi, [rax+2]
0x1800073fa  xor     edx, edx; Val
0x1800073fc  mov     r8d, 108h; Size
0x180007402  lea     rcx, [rsp+22E8h+var_2158]; void *
0x18000740a  call    memset_0
0x18000740f  mov     [rsp+22E8h+var_2158], rbx
0x180007417  test    edi, edi
0x180007419  jz      short loc_180007454
0x18000741b  movsxd  rcx, edi
0x18000741e  xor     edx, edx
0x180007420  mov     rax, rsi
0x180007423  div     rcx
0x180007426  cmp     rax, 2
0x18000742a  jb      loc_18000789F
0x180007430  lea     rdx, [rcx+rcx]
0x180007434  cmp     rdx, 100h
0x18000743b  jbe     short loc_180007454
0x18000743d  lea     rcx, [rsp+22E8h+var_2158]
0x180007445  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000744a  mov     rdi, [rsp+22E8h+var_2158]
0x180007452  jmp     short loc_180007464
0x180007454  lea     rdi, [rsp+22E8h+var_2150]
0x18000745c  mov     [rsp+22E8h+var_2158], rdi
0x180007464  jmp     short loc_180007488
0x180007466  xor     ebx, ebx
0x180007468  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000746c  mov     rdi, [rsp+22E8h+var_2158]
0x180007474  mov     rax, [rsp+22E8h+var_22B0]
0x180007479  mov     [rsp+22E8h+var_22B8], rax
0x18000747e  mov     r13, qword ptr [rsp+22E8h+Data]
0x180007483  mov     r12, [rsp+22E8h+var_22A8]
0x180007488  test    rdi, rdi
0x18000748b  jz      loc_180007548
0x180007491  lea     r14, [rsp+22E8h+String1]
0x180007499  cmp     [rsp+22E8h+String1], bx
0x1800074a1  jz      short loc_1800074E4
0x1800074a3  mov     r15d, 30h ; '0'
0x1800074a9  mov     rcx, r14; lpsz
0x1800074ac  call    cs:__imp_CharNextW
0x1800074b2  movzx   ecx, word ptr [r14]
0x1800074b6  cmp     cx, 5Ch ; '\'
0x1800074ba  jnz     short loc_1800074D3
0x1800074bc  cmp     [rax], r15w
0x1800074c0  jnz     short loc_1800074D3
0x1800074c2  mov     [rdi], bx
0x1800074c5  mov     rcx, rax; lpsz
0x1800074c8  call    cs:__imp_CharNextW
0x1800074ce  mov     r14, rax
0x1800074d1  jmp     short loc_1800074DA
0x1800074d3  mov     [rdi], cx
0x1800074d6  add     r14, 2
0x1800074da  add     rdi, 2
0x1800074de  cmp     [r14], bx
0x1800074e2  jnz     short loc_1800074A9
0x1800074e4  mov     dword ptr [rdi], 0
0x1800074ea  mov     rdi, [rsp+22E8h+var_2158]
0x1800074f2  test    rdi, rdi
0x1800074f5  jnz     short loc_1800074FC
0x1800074f7  lea     esi, [rdi+0Dh]
0x1800074fa  jmp     short loc_18000754D
0x1800074fc  mov     r9d, ebx
0x1800074ff  mov     r8, rdi
0x180007502  mov     rcx, rsi
0x180007505  inc     rcx
0x180007508  cmp     [r8+rcx*2], bx
0x18000750d  jnz     short loc_180007505
0x18000750f  inc     ecx
0x180007511  lea     r8, [r8+rcx*2]
0x180007515  lea     r9d, [r9+rcx*2]
0x180007519  cmp     ecx, 1
0x18000751c  jnz     short loc_180007502
0x18000751e  mov     [rsp+22E8h+cbData], r9d; cbData
0x180007523  mov     [rsp+22E8h+lpData], rdi; lpData
0x180007528  lea     r9d, [rcx+6]; dwType
0x18000752c  xor     r8d, r8d; Reserved
0x18000752f  mov     rdx, r12; lpValueName
0x180007532  mov     rcx, [r13+0]; hKey
0x180007536  call    cs:__imp_RegSetValueExW
0x18000753c  mov     esi, eax
0x18000753e  mov     rdi, [rsp+22E8h+var_2158]
0x180007546  jmp     short loc_18000754D
0x180007548  mov     esi, 0Eh
0x18000754d  lea     rax, [rsp+22E8h+var_2150]
0x180007555  cmp     rdi, rax
0x180007558  jz      short loc_180007567
0x18000755a  lea     rcx, [rsp+22E8h+var_2158]
0x180007562  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x180007567  mov     r15, [rsp+22E8h+var_22B8]
0x18000756c  test    esi, esi
0x18000756e  jz      loc_180007850
0x180007574  mov     ecx, esi; unsigned int
0x180007576  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000757b  jmp     loc_18000787C
0x180007580  mov     [rsp+22E8h+pulOut], ebx
0x180007584  lea     r9, [rsp+22E8h+pulOut]; pulOut
0x180007589  xor     r8d, r8d; dwFlags
0x18000758c  xor     edx, edx; lcid
0x18000758e  lea     rcx, [rsp+22E8h+String1]; strIn
0x180007596  call    cs:__imp_VarUI4FromStr
0x18000759c  test    eax, eax
0x18000759e  js      loc_18000787C
0x1800075a4  mov     eax, [rsp+22E8h+pulOut]
0x1800075a8  mov     dword ptr [rsp+22E8h+Data], eax
0x1800075ac  mov     [rsp+22E8h+cbData], 4; cbData
0x1800075b4  lea     rax, [rsp+22E8h+Data]
0x1800075b9  mov     r9d, 4; dwType
0x1800075bf  mov     [rsp+22E8h+lpData], rax; lpData
0x1800075c4  xor     r8d, r8d; Reserved
0x1800075c7  mov     rdx, r12; lpValueName
0x1800075ca  mov     rcx, [r13+0]; hKey
0x1800075ce  call    cs:__imp_RegSetValueExW
0x1800075d4  mov     esi, eax
0x1800075d6  jmp     short loc_18000756C
0x1800075d8  lea     rax, [rsp+22E8h+String1]
0x1800075e0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800075e4  mov     rdi, rsi
0x1800075e7  inc     rdi
0x1800075ea  cmp     [rax+rdi*2], bx
0x1800075ee  jnz     short loc_1800075E7
0x1800075f0  mov     dword ptr [rsp+22E8h+Data], edi
0x1800075f4  test    dil, 1
0x1800075f8  jnz     loc_1800076C1
0x1800075fe  mov     eax, edi
0x180007600  cdq
0x180007601  sub     eax, edx
0x180007603  sar     eax, 1
0x180007605  movsxd  r12, eax
0x180007608  mov     [rsp+22E8h+pulOut], r12d
0x18000760d  xor     edx, edx; Val
0x18000760f  mov     r8d, 108h; Size
0x180007615  lea     rcx, [rsp+22E8h+var_2268]; void *
0x18000761d  call    memset_0
0x180007622  mov     [rsp+22E8h+var_2268], rbx
0x18000762a  mov     r14, r12
0x18000762d  mov     [rsp+22E8h+var_2290], r12
0x180007632  test    r12d, r12d
0x180007635  jz      short loc_18000766C
0x180007637  xor     edx, edx
0x180007639  mov     rax, rsi
0x18000763c  div     r14
0x18000763f  cmp     rax, 1
0x180007643  jb      loc_1800078AA
0x180007649  cmp     r12, 100h
0x180007650  jbe     short loc_18000766C
0x180007652  mov     rdx, r12
0x180007655  lea     rcx, [rsp+22E8h+var_2268]
0x18000765d  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007662  mov     rcx, [rsp+22E8h+var_2268]
0x18000766a  jmp     short loc_18000767C
0x18000766c  lea     rcx, [rsp+22E8h+var_2260]
0x180007674  mov     [rsp+22E8h+var_2268], rcx
0x18000767c  mov     rsi, [rsp+22E8h+lpValueName]
0x180007681  jmp     short loc_1800076AF
0x180007683  xor     ebx, ebx
0x180007685  mov     edi, dword ptr [rsp+22E8h+Data]
0x180007689  mov     r12d, [rsp+22E8h+pulOut]
0x18000768e  mov     rcx, [rsp+22E8h+var_2268]; void *
0x180007696  mov     r14, [rsp+22E8h+var_2290]
0x18000769b  mov     rax, [rsp+22E8h+var_22B0]
0x1800076a0  mov     [rsp+22E8h+var_22B8], rax
0x1800076a5  mov     r13, [rsp+22E8h+var_2288]
0x1800076aa  mov     rsi, [rsp+22E8h+var_22A8]
0x1800076af  test    rcx, rcx
0x1800076b2  jnz     short loc_1800076CB
0x1800076b4  lea     rcx, [rsp+22E8h+var_2268]
0x1800076bc  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x1800076c1  mov     eax, 80004005h
0x1800076c6  jmp     loc_18000787C
0x1800076cb  mov     r8, r14; Size
0x1800076ce  xor     edx, edx; Val
0x1800076d0  call    memset_0
0x1800076d5  mov     r10d, ebx
0x1800076d8  movsxd  rdi, edi
0x1800076db  test    rdi, rdi
0x1800076de  jle     loc_1800077CB
0x1800076e4  mov     r11, rbx
0x1800076e7  mov     r15d, 30h ; '0'
0x1800076ed  movzx   edx, [rsp+r11*2+22E8h+String1]
0x1800076f6  cmp     edx, 61h ; 'a'
0x1800076f9  ja      short loc_180007768
0x1800076fb  jz      loc_180007788
0x180007701  cmp     edx, 38h ; '8'
0x180007704  ja      short loc_18000773A
0x180007706  jz      short loc_180007732
0x180007708  mov     ecx, edx
0x18000770a  sub     ecx, r15d
0x18000770d  jz      short loc_180007732
0x18000770f  sub     ecx, 1
0x180007712  jz      short loc_180007732
0x180007714  sub     ecx, 1
0x180007717  jz      short loc_180007732
0x180007719  sub     ecx, 1
0x18000771c  jz      short loc_180007732
0x18000771e  sub     ecx, 1
0x180007721  jz      short loc_180007732
0x180007723  sub     ecx, 1
0x180007726  jz      short loc_180007732
0x180007728  sub     ecx, 1
0x18000772b  jz      short loc_180007732
0x18000772d  cmp     ecx, 1
0x180007730  jnz     short loc_180007783
0x180007732  mov     r9d, edx
0x180007735  sub     r9d, r15d
0x180007738  jmp     short loc_18000778C
0x18000773a  mov     r9d, edx
0x18000773d  mov     ecx, edx
0x18000773f  sub     ecx, 39h ; '9'
0x180007742  jz      short loc_180007732
0x180007744  sub     ecx, 8
0x180007747  jz      short loc_180007762
0x180007749  sub     ecx, 1
0x18000774c  jz      short loc_180007762
0x18000774e  sub     ecx, 1
0x180007751  jz      short loc_180007762
0x180007753  sub     ecx, 1
0x180007756  jz      short loc_180007762
  ... truncated ...
```
