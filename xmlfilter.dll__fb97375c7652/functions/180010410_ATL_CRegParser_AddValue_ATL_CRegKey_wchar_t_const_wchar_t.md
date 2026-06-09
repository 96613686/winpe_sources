# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x180010410`
- end: `0x1800109e4`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800126ec`

## callees

- `0x1800020e0`
- `0x180002b38`
- `0x180010410`
- `0x1800109ec`
- `0x180010c0c`
- `0x180011478`
- `0x180011a14`
- `0x180011ca0`
- `0x180014400`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800106f9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800106f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010610`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001062c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800109b4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010610`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001062c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800109b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010699`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010731`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010932`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010699`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010731`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010932`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800104a1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800104a1`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
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
  wchar_t *v44; // [rsp+88h] [rbp-2270h]
  BYTE *v45; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v48[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

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
              ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData);
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
            ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&lpData);
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
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v45);
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
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v45);
        return -2147467259;
      }
      memset_0(v27, 0, v26);
      v29 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_88:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, v45, v25);
        if ( v45 != v46 )
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v45);
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
0x180010410  push    rbx
0x180010412  push    rsi
0x180010413  push    rdi
0x180010414  push    r12
0x180010416  push    r13
0x180010418  push    r14
0x18001041a  push    r15
0x18001041c  mov     eax, 22C0h
0x180010421  call    _alloca_probe
0x180010426  sub     rsp, rax
0x180010429  mov     rax, cs:__security_cookie
0x180010430  xor     rax, rsp
0x180010433  mov     [rsp+22F8h+var_48], rax
0x18001043b  mov     r14, r8
0x18001043e  mov     [rsp+22F8h+lpValueName], r8
0x180010443  mov     r12, rdx
0x180010446  mov     [rsp+22F8h+var_2288], rdx
0x18001044b  mov     r15, rcx
0x18001044e  mov     [rsp+22F8h+var_22C0], rcx
0x180010453  mov     qword ptr [rsp+22F8h+Data], rdx
0x180010458  mov     [rsp+22F8h+var_22A8], rcx
0x18001045d  mov     [rsp+22F8h+var_2278], rdx
0x180010465  mov     [rsp+22F8h+var_2298], r8
0x18001046a  mov     [rsp+22F8h+var_2270], r9
0x180010472  lea     rdx, [rsp+22F8h+String1]; wchar_t *
0x18001047a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001047f  xor     ebx, ebx
0x180010481  test    eax, eax
0x180010483  js      short loc_1800104B7
0x180010485  mov     edi, ebx
0x180010487  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18001048e  movsxd  rsi, edi
0x180010491  add     rsi, rsi
0x180010494  mov     rdx, [r13+rsi*8+0]; lpString2
0x180010499  lea     rcx, [rsp+22F8h+String1]; lpString1
0x1800104a1  call    cs:__imp_lstrcmpiW
0x1800104a7  test    eax, eax
0x1800104a9  jz      short loc_1800104DA
0x1800104ab  inc     edi
0x1800104ad  cmp     edi, 4
0x1800104b0  jb      short loc_18001048E
0x1800104b2  mov     eax, 80020009h
0x1800104b7  mov     rcx, [rsp+22F8h+var_48]
0x1800104bf  xor     rcx, rsp; StackCookie
0x1800104c2  call    __security_check_cookie
0x1800104c7  add     rsp, 22C0h
0x1800104ce  pop     r15
0x1800104d0  pop     r14
0x1800104d2  pop     r13
0x1800104d4  pop     r12
0x1800104d6  pop     rdi
0x1800104d7  pop     rsi
0x1800104d8  pop     rbx
0x1800104d9  retn
0x1800104da  movzx   edi, word ptr [r13+rsi*8+8]
0x1800104e0  mov     esi, 13h
0x1800104e5  mov     rdx, [r15]
0x1800104e8  movzx   ecx, word ptr [rdx]
0x1800104eb  sub     ecx, 9
0x1800104ee  jz      loc_1800109B1
0x1800104f4  sub     ecx, 1
0x1800104f7  jz      loc_1800109B1
0x1800104fd  sub     ecx, 3
0x180010500  jz      loc_1800109B1
0x180010506  cmp     ecx, esi
0x180010508  jz      loc_1800109B1
0x18001050e  lea     rdx, [rsp+22F8h+String1]; wchar_t *
0x180010516  mov     rcx, r15; this
0x180010519  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001051e  test    eax, eax
0x180010520  js      short loc_1800104B7
0x180010522  mov     r13d, 8
0x180010528  cmp     di, r13w
0x18001052c  jz      loc_180010962
0x180010532  cmp     di, 11h
0x180010536  jz      loc_18001073B
0x18001053c  cmp     di, si
0x18001053f  jz      loc_1800106E3
0x180010545  mov     eax, 4008h
0x18001054a  cmp     di, ax
0x18001054d  jnz     loc_180010995
0x180010553  lea     rcx, [rsp+22F8h+String1]
0x18001055b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001055f  mov     rax, rsi
0x180010562  inc     rax
0x180010565  cmp     [rcx+rax*2], bx
0x180010569  jnz     short loc_180010562
0x18001056b  add     eax, 2
0x18001056e  mov     [rsp+22F8h+var_2158], rbx
0x180010576  test    eax, eax
0x180010578  jz      short loc_1800105B3
0x18001057a  movsxd  rcx, eax
0x18001057d  xor     edx, edx
0x18001057f  mov     rax, rsi
0x180010582  div     rcx
0x180010585  cmp     rax, 2
0x180010589  jb      loc_1800109C2
0x18001058f  lea     rdx, [rcx+rcx]
0x180010593  cmp     rdx, 100h
0x18001059a  jbe     short loc_1800105B3
0x18001059c  lea     rcx, [rsp+22F8h+var_2158]
0x1800105a4  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800105a9  mov     rdi, [rsp+22F8h+var_2158]
0x1800105b1  jmp     short loc_1800105C3
0x1800105b3  lea     rdi, [rsp+22F8h+var_2150]
0x1800105bb  mov     [rsp+22F8h+var_2158], rdi
0x1800105c3  mov     r13, [rsp+22F8h+lpValueName]
0x1800105c8  jmp     short loc_1800105EC
0x1800105ca  xor     ebx, ebx
0x1800105cc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800105d0  mov     rdi, [rsp+22F8h+var_2158]
0x1800105d8  mov     r12, qword ptr [rsp+22F8h+Data]
0x1800105dd  mov     rax, [rsp+22F8h+var_22A8]
0x1800105e2  mov     [rsp+22F8h+var_22C0], rax
0x1800105e7  mov     r13, [rsp+22F8h+var_2298]
0x1800105ec  test    rdi, rdi
0x1800105ef  jz      loc_1800106AB
0x1800105f5  lea     r14, [rsp+22F8h+String1]
0x1800105fd  cmp     [rsp+22F8h+String1], bx
0x180010605  jz      short loc_180010648
0x180010607  mov     r15d, 30h ; '0'
0x18001060d  mov     rcx, r14; lpsz
0x180010610  call    cs:__imp_CharNextW
0x180010616  movzx   ecx, word ptr [r14]
0x18001061a  cmp     cx, 5Ch ; '\'
0x18001061e  jnz     short loc_180010637
0x180010620  cmp     [rax], r15w
0x180010624  jnz     short loc_180010637
0x180010626  mov     [rdi], bx
0x180010629  mov     rcx, rax; lpsz
0x18001062c  call    cs:__imp_CharNextW
0x180010632  mov     r14, rax
0x180010635  jmp     short loc_18001063E
0x180010637  mov     [rdi], cx
0x18001063a  add     r14, 2
0x18001063e  add     rdi, 2
0x180010642  cmp     [r14], bx
0x180010646  jnz     short loc_18001060D
0x180010648  mov     dword ptr [rdi], 0
0x18001064e  mov     r8, [rsp+22F8h+var_2158]
0x180010656  test    r8, r8
0x180010659  jz      loc_1800109CD
0x18001065f  mov     r10d, ebx
0x180010662  mov     r9, r8
0x180010665  mov     rcx, rsi
0x180010668  inc     rcx
0x18001066b  cmp     [r9+rcx*2], bx
0x180010670  jnz     short loc_180010668
0x180010672  inc     ecx
0x180010674  lea     r9, [r9+rcx*2]
0x180010678  lea     r10d, [r10+rcx*2]
0x18001067c  cmp     ecx, 1
0x18001067f  jnz     short loc_180010665
0x180010681  mov     [rsp+22F8h+cbData], r10d; cbData
0x180010686  mov     [rsp+22F8h+lpData], r8; lpData
0x18001068b  lea     r9d, [rcx+6]; dwType
0x18001068f  xor     r8d, r8d; Reserved
0x180010692  mov     rdx, r13; lpValueName
0x180010695  mov     rcx, [r12]; hKey
0x180010699  call    cs:__imp_RegSetValueExW
0x18001069f  mov     esi, eax
0x1800106a1  mov     rdi, [rsp+22F8h+var_2158]
0x1800106a9  jmp     short loc_1800106B0
0x1800106ab  mov     esi, 0Eh
0x1800106b0  lea     rax, [rsp+22F8h+var_2150]
0x1800106b8  cmp     rdi, rax
0x1800106bb  jz      short loc_1800106CA
0x1800106bd  lea     rcx, [rsp+22F8h+var_2158]
0x1800106c5  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x1800106ca  mov     r15, [rsp+22F8h+var_22C0]
0x1800106cf  test    esi, esi
0x1800106d1  jz      loc_180010995
0x1800106d7  mov     ecx, esi; unsigned int
0x1800106d9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800106de  jmp     loc_1800104B7
0x1800106e3  mov     [rsp+22F8h+pulOut], ebx
0x1800106e7  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x1800106ec  xor     r8d, r8d; dwFlags
0x1800106ef  xor     edx, edx; lcid
0x1800106f1  lea     rcx, [rsp+22F8h+String1]; strIn
0x1800106f9  call    cs:__imp_VarUI4FromStr
0x1800106ff  test    eax, eax
0x180010701  js      loc_1800104B7
0x180010707  mov     eax, [rsp+22F8h+pulOut]
0x18001070b  mov     dword ptr [rsp+22F8h+Data], eax
0x18001070f  mov     [rsp+22F8h+cbData], 4; cbData
0x180010717  lea     rax, [rsp+22F8h+Data]
0x18001071c  mov     r9d, 4; dwType
0x180010722  mov     [rsp+22F8h+lpData], rax; lpData
0x180010727  xor     r8d, r8d; Reserved
0x18001072a  mov     rdx, r14; lpValueName
0x18001072d  mov     rcx, [r12]; hKey
0x180010731  call    cs:__imp_RegSetValueExW
0x180010737  mov     esi, eax
0x180010739  jmp     short loc_1800106CF
0x18001073b  lea     rax, [rsp+22F8h+String1]
0x180010743  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180010747  mov     r14, rsi
0x18001074a  inc     r14
0x18001074d  cmp     [rax+r14*2], bx
0x180010752  jnz     short loc_18001074A
0x180010754  mov     dword ptr [rsp+22F8h+Data], r14d
0x180010759  test    r14b, 1
0x18001075d  jnz     loc_180010817
0x180010763  mov     eax, r14d
0x180010766  cdq
0x180010767  sub     eax, edx
0x180010769  sar     eax, 1
0x18001076b  movsxd  r12, eax
0x18001076e  mov     [rsp+22F8h+var_2268], rbx
0x180010776  mov     rdi, r12
0x180010779  mov     [rsp+22F8h+var_2280], r12
0x18001077e  test    eax, eax
0x180010780  jz      short loc_1800107B7
0x180010782  xor     edx, edx
0x180010784  mov     rax, rsi
0x180010787  div     rdi
0x18001078a  cmp     rax, 1
0x18001078e  jb      loc_1800109D8
0x180010794  cmp     rdi, 100h
0x18001079b  jbe     short loc_1800107B7
0x18001079d  mov     rdx, rdi
0x1800107a0  lea     rcx, [rsp+22F8h+var_2268]
0x1800107a8  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800107ad  mov     rcx, [rsp+22F8h+var_2268]
0x1800107b5  jmp     short loc_1800107C7
0x1800107b7  lea     rcx, [rsp+22F8h+var_2260]
0x1800107bf  mov     [rsp+22F8h+var_2268], rcx
0x1800107c7  mov     rsi, [rsp+22F8h+var_2288]
0x1800107cc  jmp     short loc_180010805
0x1800107ce  xor     ebx, ebx
0x1800107d0  lea     r13d, [rbx+8]
0x1800107d4  mov     r14d, dword ptr [rsp+22F8h+Data]
0x1800107d9  mov     rcx, [rsp+22F8h+var_2268]; void *
0x1800107e1  mov     rdi, [rsp+22F8h+var_2280]
0x1800107e6  mov     rax, [rsp+22F8h+var_22A8]
0x1800107eb  mov     [rsp+22F8h+var_22C0], rax
0x1800107f0  mov     rsi, [rsp+22F8h+var_2278]
0x1800107f8  mov     rax, [rsp+22F8h+var_2298]
0x1800107fd  mov     [rsp+22F8h+lpValueName], rax
0x180010802  mov     r12d, edi
0x180010805  test    rcx, rcx
0x180010808  jnz     short loc_180010821
0x18001080a  lea     rcx, [rsp+22F8h+var_2268]
0x180010812  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x180010817  mov     eax, 80004005h
0x18001081c  jmp     loc_1800104B7
0x180010821  mov     r8, rdi; Size
0x180010824  xor     edx, edx; Val
0x180010826  call    memset_0
0x18001082b  mov     r10d, ebx
0x18001082e  test    r14d, r14d
0x180010831  jle     loc_18001090F
0x180010837  mov     r15d, 30h ; '0'
0x18001083d  mov     eax, r10d
0x180010840  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180010848  cmp     edx, 61h ; 'a'
0x18001084b  ja      short loc_1800108BA
0x18001084d  jz      loc_1800108DA
0x180010853  cmp     edx, 38h ; '8'
0x180010856  ja      short loc_18001088C
0x180010858  jz      short loc_180010884
0x18001085a  mov     ecx, edx
0x18001085c  sub     ecx, r15d
0x18001085f  jz      short loc_180010884
0x180010861  sub     ecx, 1
0x180010864  jz      short loc_180010884
0x180010866  sub     ecx, 1
0x180010869  jz      short loc_180010884
0x18001086b  sub     ecx, 1
0x18001086e  jz      short loc_180010884
0x180010870  sub     ecx, 1
0x180010873  jz      short loc_180010884
0x180010875  sub     ecx, 1
0x180010878  jz      short loc_180010884
0x18001087a  sub     ecx, 1
0x18001087d  jz      short loc_180010884
0x18001087f  cmp     ecx, 1
0x180010882  jnz     short loc_1800108D5
0x180010884  mov     r9d, edx
0x180010887  sub     r9d, r15d
0x18001088a  jmp     short loc_1800108DE
0x18001088c  mov     r9d, edx
0x18001088f  mov     ecx, edx
0x180010891  sub     ecx, 39h ; '9'
0x180010894  jz      short loc_180010884
0x180010896  sub     ecx, r13d
0x180010899  jz      short loc_1800108B4
0x18001089b  sub     ecx, 1
0x18001089e  jz      short loc_1800108B4
0x1800108a0  sub     ecx, 1
0x1800108a3  jz      short loc_1800108B4
0x1800108a5  sub     ecx, 1
0x1800108a8  jz      short loc_1800108B4
0x1800108aa  sub     ecx, 1
0x1800108ad  jz      short loc_1800108B4
0x1800108af  cmp     ecx, 1
0x1800108b2  jnz     short loc_1800108D5
0x1800108b4  add     r9d, 0FFFFFFC9h
0x1800108b8  jmp     short loc_1800108DE
  ... truncated ...
```
