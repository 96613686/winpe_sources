# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x18007c71c`
- end: `0x18007cd46`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1578`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18007d33c`

## callees

- `0x180004d50`
- `0x18007c004`
- `0x18007c034`
- `0x18007c71c`
- `0x18007d17c`
- `0x18007d190`
- `0x18009ae75`
- `0x18009b050`
- `0x1800a18f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c9c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007ca5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007cc7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007c9c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007ca5e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007cc7d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18007ca26`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18007ca26`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c93c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c958`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007ccf9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c93c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c958`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007ccf9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c799`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c7b7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c7d7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c7f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c799`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c7b7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c7d7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c7f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
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
0x18007c71c  push    rbx
0x18007c71e  push    rsi
0x18007c71f  push    rdi
0x18007c720  push    r12
0x18007c722  push    r13
0x18007c724  push    r14
0x18007c726  push    r15
0x18007c728  mov     eax, 22B0h
0x18007c72d  call    _alloca_probe
0x18007c732  sub     rsp, rax
0x18007c735  mov     rax, cs:__security_cookie
0x18007c73c  xor     rax, rsp
0x18007c73f  mov     [rsp+22E8h+var_48], rax
0x18007c747  mov     r12, r8
0x18007c74a  mov     [rsp+22E8h+lpValueName], r8
0x18007c74f  mov     r13, rdx
0x18007c752  mov     r15, rcx
0x18007c755  mov     [rsp+22E8h+var_22B8], rcx
0x18007c75a  mov     qword ptr [rsp+22E8h+Data], rdx
0x18007c75f  mov     [rsp+22E8h+var_22B0], rcx
0x18007c764  mov     [rsp+22E8h+var_2288], rdx
0x18007c769  mov     [rsp+22E8h+var_22A8], r8
0x18007c76e  mov     [rsp+22E8h+var_2280], r9
0x18007c773  lea     rdx, [rsp+22E8h+String1]; wchar_t *
0x18007c77b  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007c780  xor     ebx, ebx
0x18007c782  test    eax, eax
0x18007c784  js      loc_18007CD0C
0x18007c78a  lea     rdx, aS; "S"
0x18007c791  lea     rcx, [rsp+22E8h+String1]; lpString1
0x18007c799  call    cs:__imp_lstrcmpiW
0x18007c79f  test    eax, eax
0x18007c7a1  jnz     short loc_18007C7A8
0x18007c7a3  lea     edi, [rbx+8]
0x18007c7a6  jmp     short loc_18007C806
0x18007c7a8  lea     rdx, aM; "M"
0x18007c7af  lea     rcx, [rsp+22E8h+String1]; lpString1
0x18007c7b7  call    cs:__imp_lstrcmpiW
0x18007c7bd  test    eax, eax
0x18007c7bf  jnz     short loc_18007C7C8
0x18007c7c1  mov     edi, 4008h
0x18007c7c6  jmp     short loc_18007C806
0x18007c7c8  lea     rdx, aD; "D"
0x18007c7cf  lea     rcx, [rsp+22E8h+String1]; lpString1
0x18007c7d7  call    cs:__imp_lstrcmpiW
0x18007c7dd  test    eax, eax
0x18007c7df  jnz     short loc_18007C7E6
0x18007c7e1  lea     edi, [rax+13h]
0x18007c7e4  jmp     short loc_18007C806
0x18007c7e6  lea     rdx, aB; "B"
0x18007c7ed  lea     rcx, [rsp+22E8h+String1]; lpString1
0x18007c7f5  call    cs:__imp_lstrcmpiW
0x18007c7fb  test    eax, eax
0x18007c7fd  jnz     loc_18007CD07
0x18007c803  lea     edi, [rax+11h]
0x18007c806  mov     rdx, [r15]
0x18007c809  movzx   ecx, word ptr [rdx]
0x18007c80c  sub     ecx, 9
0x18007c80f  jz      loc_18007CCF6
0x18007c815  sub     ecx, 1
0x18007c818  jz      loc_18007CCF6
0x18007c81e  sub     ecx, 3
0x18007c821  jz      loc_18007CCF6
0x18007c827  cmp     ecx, 13h
0x18007c82a  jz      loc_18007CCF6
0x18007c830  lea     rdx, [rsp+22E8h+String1]; wchar_t *
0x18007c838  mov     rcx, r15; this
0x18007c83b  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18007c840  test    eax, eax
0x18007c842  js      loc_18007CD0C
0x18007c848  cmp     edi, 8
0x18007c84b  jz      loc_18007CCAD
0x18007c851  cmp     edi, 11h
0x18007c854  jz      loc_18007CA68
0x18007c85a  cmp     edi, 13h
0x18007c85d  jz      loc_18007CA10
0x18007c863  cmp     edi, 4008h
0x18007c869  jnz     loc_18007CCE0
0x18007c86f  lea     rcx, [rsp+22E8h+String1]
0x18007c877  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007c87b  mov     rax, rsi
0x18007c87e  inc     rax
0x18007c881  cmp     [rcx+rax*2], bx
0x18007c885  jnz     short loc_18007C87E
0x18007c887  lea     edi, [rax+2]
0x18007c88a  xor     edx, edx; Val
0x18007c88c  mov     r8d, 108h; Size
0x18007c892  lea     rcx, [rsp+22E8h+var_2158]; void *
0x18007c89a  call    memset_0
0x18007c89f  mov     [rsp+22E8h+var_2158], rbx
0x18007c8a7  test    edi, edi
0x18007c8a9  jz      short loc_18007C8E4
0x18007c8ab  movsxd  rcx, edi
0x18007c8ae  xor     edx, edx
0x18007c8b0  mov     rax, rsi
0x18007c8b3  div     rcx
0x18007c8b6  cmp     rax, 2
0x18007c8ba  jb      loc_18007CD2F
0x18007c8c0  lea     rdx, [rcx+rcx]
0x18007c8c4  cmp     rdx, 100h
0x18007c8cb  jbe     short loc_18007C8E4
0x18007c8cd  lea     rcx, [rsp+22E8h+var_2158]
0x18007c8d5  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18007c8da  mov     rdi, [rsp+22E8h+var_2158]
0x18007c8e2  jmp     short loc_18007C8F4
0x18007c8e4  lea     rdi, [rsp+22E8h+var_2150]
0x18007c8ec  mov     [rsp+22E8h+var_2158], rdi
0x18007c8f4  jmp     short loc_18007C918
0x18007c8f6  xor     ebx, ebx
0x18007c8f8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007c8fc  mov     rdi, [rsp+22E8h+var_2158]
0x18007c904  mov     rax, [rsp+22E8h+var_22B0]
0x18007c909  mov     [rsp+22E8h+var_22B8], rax
0x18007c90e  mov     r13, qword ptr [rsp+22E8h+Data]
0x18007c913  mov     r12, [rsp+22E8h+var_22A8]
0x18007c918  test    rdi, rdi
0x18007c91b  jz      loc_18007C9D8
0x18007c921  lea     r14, [rsp+22E8h+String1]
0x18007c929  cmp     [rsp+22E8h+String1], bx
0x18007c931  jz      short loc_18007C974
0x18007c933  mov     r15d, 30h ; '0'
0x18007c939  mov     rcx, r14; lpsz
0x18007c93c  call    cs:__imp_CharNextW
0x18007c942  movzx   ecx, word ptr [r14]
0x18007c946  cmp     cx, 5Ch ; '\'
0x18007c94a  jnz     short loc_18007C963
0x18007c94c  cmp     [rax], r15w
0x18007c950  jnz     short loc_18007C963
0x18007c952  mov     [rdi], bx
0x18007c955  mov     rcx, rax; lpsz
0x18007c958  call    cs:__imp_CharNextW
0x18007c95e  mov     r14, rax
0x18007c961  jmp     short loc_18007C96A
0x18007c963  mov     [rdi], cx
0x18007c966  add     r14, 2
0x18007c96a  add     rdi, 2
0x18007c96e  cmp     [r14], bx
0x18007c972  jnz     short loc_18007C939
0x18007c974  mov     dword ptr [rdi], 0
0x18007c97a  mov     rdi, [rsp+22E8h+var_2158]
0x18007c982  test    rdi, rdi
0x18007c985  jnz     short loc_18007C98C
0x18007c987  lea     esi, [rdi+0Dh]
0x18007c98a  jmp     short loc_18007C9DD
0x18007c98c  mov     r9d, ebx
0x18007c98f  mov     r8, rdi
0x18007c992  mov     rcx, rsi
0x18007c995  inc     rcx
0x18007c998  cmp     [r8+rcx*2], bx
0x18007c99d  jnz     short loc_18007C995
0x18007c99f  inc     ecx
0x18007c9a1  lea     r8, [r8+rcx*2]
0x18007c9a5  lea     r9d, [r9+rcx*2]
0x18007c9a9  cmp     ecx, 1
0x18007c9ac  jnz     short loc_18007C992
0x18007c9ae  mov     [rsp+22E8h+cbData], r9d; cbData
0x18007c9b3  mov     [rsp+22E8h+lpData], rdi; lpData
0x18007c9b8  lea     r9d, [rcx+6]; dwType
0x18007c9bc  xor     r8d, r8d; Reserved
0x18007c9bf  mov     rdx, r12; lpValueName
0x18007c9c2  mov     rcx, [r13+0]; hKey
0x18007c9c6  call    cs:__imp_RegSetValueExW
0x18007c9cc  mov     esi, eax
0x18007c9ce  mov     rdi, [rsp+22E8h+var_2158]
0x18007c9d6  jmp     short loc_18007C9DD
0x18007c9d8  mov     esi, 0Eh
0x18007c9dd  lea     rax, [rsp+22E8h+var_2150]
0x18007c9e5  cmp     rdi, rax
0x18007c9e8  jz      short loc_18007C9F7
0x18007c9ea  lea     rcx, [rsp+22E8h+var_2158]
0x18007c9f2  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18007c9f7  mov     r15, [rsp+22E8h+var_22B8]
0x18007c9fc  test    esi, esi
0x18007c9fe  jz      loc_18007CCE0
0x18007ca04  mov     ecx, esi; unsigned int
0x18007ca06  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18007ca0b  jmp     loc_18007CD0C
0x18007ca10  mov     [rsp+22E8h+pulOut], ebx
0x18007ca14  lea     r9, [rsp+22E8h+pulOut]; pulOut
0x18007ca19  xor     r8d, r8d; dwFlags
0x18007ca1c  xor     edx, edx; lcid
0x18007ca1e  lea     rcx, [rsp+22E8h+String1]; strIn
0x18007ca26  call    cs:__imp_VarUI4FromStr
0x18007ca2c  test    eax, eax
0x18007ca2e  js      loc_18007CD0C
0x18007ca34  mov     eax, [rsp+22E8h+pulOut]
0x18007ca38  mov     dword ptr [rsp+22E8h+Data], eax
0x18007ca3c  mov     [rsp+22E8h+cbData], 4; cbData
0x18007ca44  lea     rax, [rsp+22E8h+Data]
0x18007ca49  mov     r9d, 4; dwType
0x18007ca4f  mov     [rsp+22E8h+lpData], rax; lpData
0x18007ca54  xor     r8d, r8d; Reserved
0x18007ca57  mov     rdx, r12; lpValueName
0x18007ca5a  mov     rcx, [r13+0]; hKey
0x18007ca5e  call    cs:__imp_RegSetValueExW
0x18007ca64  mov     esi, eax
0x18007ca66  jmp     short loc_18007C9FC
0x18007ca68  lea     rax, [rsp+22E8h+String1]
0x18007ca70  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007ca74  mov     rdi, rsi
0x18007ca77  inc     rdi
0x18007ca7a  cmp     [rax+rdi*2], bx
0x18007ca7e  jnz     short loc_18007CA77
0x18007ca80  mov     dword ptr [rsp+22E8h+Data], edi
0x18007ca84  test    dil, 1
0x18007ca88  jnz     loc_18007CB51
0x18007ca8e  mov     eax, edi
0x18007ca90  cdq
0x18007ca91  sub     eax, edx
0x18007ca93  sar     eax, 1
0x18007ca95  movsxd  r12, eax
0x18007ca98  mov     [rsp+22E8h+pulOut], r12d
0x18007ca9d  xor     edx, edx; Val
0x18007ca9f  mov     r8d, 108h; Size
0x18007caa5  lea     rcx, [rsp+22E8h+var_2268]; void *
0x18007caad  call    memset_0
0x18007cab2  mov     [rsp+22E8h+var_2268], rbx
0x18007caba  mov     r14, r12
0x18007cabd  mov     [rsp+22E8h+var_2290], r12
0x18007cac2  test    r12d, r12d
0x18007cac5  jz      short loc_18007CAFC
0x18007cac7  xor     edx, edx
0x18007cac9  mov     rax, rsi
0x18007cacc  div     r14
0x18007cacf  cmp     rax, 1
0x18007cad3  jb      loc_18007CD3A
0x18007cad9  cmp     r12, 100h
0x18007cae0  jbe     short loc_18007CAFC
0x18007cae2  mov     rdx, r12
0x18007cae5  lea     rcx, [rsp+22E8h+var_2268]
0x18007caed  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18007caf2  mov     rcx, [rsp+22E8h+var_2268]
0x18007cafa  jmp     short loc_18007CB0C
0x18007cafc  lea     rcx, [rsp+22E8h+var_2260]
0x18007cb04  mov     [rsp+22E8h+var_2268], rcx
0x18007cb0c  mov     rsi, [rsp+22E8h+lpValueName]
0x18007cb11  jmp     short loc_18007CB3F
0x18007cb13  xor     ebx, ebx
0x18007cb15  mov     edi, dword ptr [rsp+22E8h+Data]
0x18007cb19  mov     r12d, [rsp+22E8h+pulOut]
0x18007cb1e  mov     rcx, [rsp+22E8h+var_2268]; void *
0x18007cb26  mov     r14, [rsp+22E8h+var_2290]
0x18007cb2b  mov     rax, [rsp+22E8h+var_22B0]
0x18007cb30  mov     [rsp+22E8h+var_22B8], rax
0x18007cb35  mov     r13, [rsp+22E8h+var_2288]
0x18007cb3a  mov     rsi, [rsp+22E8h+var_22A8]
0x18007cb3f  test    rcx, rcx
0x18007cb42  jnz     short loc_18007CB5B
0x18007cb44  lea     rcx, [rsp+22E8h+var_2268]
0x18007cb4c  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18007cb51  mov     eax, 80004005h
0x18007cb56  jmp     loc_18007CD0C
0x18007cb5b  mov     r8, r14; Size
0x18007cb5e  xor     edx, edx; Val
0x18007cb60  call    memset_0
0x18007cb65  mov     r10d, ebx
0x18007cb68  movsxd  rdi, edi
0x18007cb6b  test    rdi, rdi
0x18007cb6e  jle     loc_18007CC5B
0x18007cb74  mov     r11, rbx
0x18007cb77  mov     r15d, 30h ; '0'
0x18007cb7d  movzx   edx, [rsp+r11*2+22E8h+String1]
0x18007cb86  cmp     edx, 61h ; 'a'
0x18007cb89  ja      short loc_18007CBF8
0x18007cb8b  jz      loc_18007CC18
0x18007cb91  cmp     edx, 38h ; '8'
0x18007cb94  ja      short loc_18007CBCA
0x18007cb96  jz      short loc_18007CBC2
0x18007cb98  mov     ecx, edx
0x18007cb9a  sub     ecx, r15d
0x18007cb9d  jz      short loc_18007CBC2
0x18007cb9f  sub     ecx, 1
0x18007cba2  jz      short loc_18007CBC2
0x18007cba4  sub     ecx, 1
0x18007cba7  jz      short loc_18007CBC2
0x18007cba9  sub     ecx, 1
0x18007cbac  jz      short loc_18007CBC2
0x18007cbae  sub     ecx, 1
0x18007cbb1  jz      short loc_18007CBC2
0x18007cbb3  sub     ecx, 1
0x18007cbb6  jz      short loc_18007CBC2
0x18007cbb8  sub     ecx, 1
0x18007cbbb  jz      short loc_18007CBC2
0x18007cbbd  cmp     ecx, 1
0x18007cbc0  jnz     short loc_18007CC13
0x18007cbc2  mov     r9d, edx
0x18007cbc5  sub     r9d, r15d
0x18007cbc8  jmp     short loc_18007CC1C
0x18007cbca  mov     r9d, edx
0x18007cbcd  mov     ecx, edx
0x18007cbcf  sub     ecx, 39h ; '9'
0x18007cbd2  jz      short loc_18007CBC2
0x18007cbd4  sub     ecx, 8
0x18007cbd7  jz      short loc_18007CBF2
0x18007cbd9  sub     ecx, 1
0x18007cbdc  jz      short loc_18007CBF2
0x18007cbde  sub     ecx, 1
0x18007cbe1  jz      short loc_18007CBF2
0x18007cbe3  sub     ecx, 1
0x18007cbe6  jz      short loc_18007CBF2
  ... truncated ...
```
