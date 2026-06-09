# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800126ec`
- end: `0x180012ce5`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1529`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180014b28`

## callees

- `0x1800065bc`
- `0x1800126ec`
- `0x180012cec`
- `0x180012e40`
- `0x180013f40`
- `0x180014050`
- `0x18001b3ee`
- `0x18001b420`
- `0x18001b4e0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800129cf`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800129cf`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800128e1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800128fd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180012cb5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800128e1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800128fd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180012cb5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001296a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012a08`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012c1c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012c89`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001296a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012a08`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012c1c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012c89`
- `KERNEL32!lstrcmpiW` at `0x18001277a`
- `KERNEL32!lstrcmpiW` at `0x18001277a`

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
  const WCHAR *v13; // r13
  BYTE *v14; // rdi
  WCHAR *i; // r14
  const WCHAR *v16; // rax
  DWORD cbData; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // edi
  __int64 v22; // r14
  int v23; // eax
  unsigned __int64 v24; // r12
  size_t v25; // rdi
  unsigned __int64 v26; // rdx
  HKEY *v27; // rsi
  unsigned int v28; // r10d
  unsigned int v29; // edx
  char v30; // r9
  __int64 v31; // rsi
  int Token; // eax
  __int64 v33; // [rsp+0h] [rbp-22F8h] BYREF
  BYTE Data[4]; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-22C0h]
  ULONG pulOut; // [rsp+40h] [rbp-22B8h] BYREF
  int v37; // [rsp+44h] [rbp-22B4h]
  struct ATL::CRegKey *v38; // [rsp+48h] [rbp-22B0h]
  LPCWSTR lpValueName; // [rsp+50h] [rbp-22A8h]
  ATL::CRegParser *v40; // [rsp+58h] [rbp-22A0h]
  const WCHAR *v41; // [rsp+60h] [rbp-2298h]
  struct ATL::CRegKey *v42; // [rsp+70h] [rbp-2288h]
  struct ATL::CRegKey *v43; // [rsp+78h] [rbp-2280h]
  unsigned __int16 *v44; // [rsp+80h] [rbp-2278h]
  __int64 v45; // [rsp+88h] [rbp-2270h]
  BYTE *v46; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v47[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v49[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  WCHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v42 = (struct ATL::CRegKey *)a2;
  v6 = this;
  v35 = (ATL::CRegParser *)this;
  v38 = (struct ATL::CRegKey *)a2;
  v40 = (ATL::CRegParser *)this;
  v43 = (struct ATL::CRegKey *)a2;
  v41 = a3;
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
        v31 = -1;
        do
          ++v31;
        while ( String1[v31] );
        v21 = RegSetValueExW(*v5, a3, 0, 1u, (const BYTE *)String1, 2 * v31 + 2);
LABEL_43:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
        goto LABEL_95;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v45 = 0;
          result = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( result < 0 )
            return result;
          *(_DWORD *)Data = pulOut;
          v21 = RegSetValueExW(*v5, a3, 0, 4u, Data, 4u);
          goto LABEL_43;
        }
        if ( v10 != 16392 )
        {
LABEL_95:
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
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData);
          else
LABEL_24:
            lpData = v49;
        }
        catch ( ... )
        {
          v8 = 0;
          v5 = (HKEY *)v38;
          v35 = v40;
          v13 = v41;
          goto LABEL_26;
        }
        v13 = lpValueName;
LABEL_26:
        v14 = lpData;
        if ( lpData )
        {
          for ( i = String1; *i; v14 += 2 )
          {
            v16 = CharNextW(i);
            if ( *i == 92 && *v16 == 48 )
            {
              *(_WORD *)v14 = 0;
              i = CharNextW(v16);
            }
            else
            {
              *(_WORD *)v14 = *i++;
            }
          }
          *(_DWORD *)v14 = 0;
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
          v21 = RegSetValueExW(*v5, v13, 0, 7u, lpData, cbData);
        }
        else
        {
          v21 = 14;
        }
        if ( lpData != v49 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
        goto LABEL_42;
      }
      v22 = -1;
      do
        ++v22;
      while ( String1[v22] );
      v37 = v22;
      if ( (v22 & 1) != 0 )
        return -2147467259;
      v23 = (int)v22 / 2;
      v24 = (int)v22 / 2;
      *(_DWORD *)Data = (int)v22 / 2;
      LODWORD(v38) = (int)v22 / 2;
      v46 = 0;
      try
      {
        v25 = v23;
        if ( v23 )
        {
          if ( !(0xFFFFFFFFFFFFFFFFuLL / v24) )
            ATL::AtlThrowImpl(-2147024809);
          v26 = (int)v22 / 2;
        }
        else
        {
          v26 = 0;
        }
        if ( v26 <= 0x100 )
          v46 = v47;
        else
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v46);
      }
      catch ( ... )
      {
        v25 = *(int *)Data;
        v8 = 0;
        LODWORD(v22) = v37;
        LODWORD(v24) = (_DWORD)v38;
        v35 = v40;
        v27 = (HKEY *)v43;
        lpValueName = v41;
        goto LABEL_59;
      }
      v27 = (HKEY *)v42;
LABEL_59:
      if ( !v46 )
      {
        if ( &v33 != (__int64 *)-152LL )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v46);
        return -2147467259;
      }
      memset_0(v46, 0, v25);
      v28 = 0;
      if ( (int)v22 <= 0 )
      {
LABEL_90:
        v21 = RegSetValueExW(*v27, lpValueName, 0, 3u, v46, v24);
        if ( v46 != v47 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v46);
LABEL_42:
        v6 = (LPCWSTR *)v35;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v29 = String1[v28];
        if ( v29 > 0x61 )
        {
          if ( v29 == 98 || v29 == 99 || v29 == 100 || v29 - 101 < 2 )
          {
LABEL_88:
            v30 = v29 - 87;
            goto LABEL_89;
          }
LABEL_87:
          v30 = 0;
          goto LABEL_89;
        }
        if ( v29 == 97 )
          goto LABEL_88;
        if ( v29 <= 0x38 )
          break;
        if ( v29 == 57 )
          goto LABEL_75;
        if ( v29 != 65 && v29 != 66 && v29 != 67 && v29 != 68 && v29 - 69 > 1 )
          goto LABEL_87;
        v30 = v29 - 55;
LABEL_89:
        v46[(unsigned __int64)v28 >> 1] |= v30 << (4 - 4 * (v28 & 1));
        if ( (int)++v28 >= (int)v22 )
          goto LABEL_90;
      }
      if ( v29 != 56 && v29 != 48 && v29 != 49 && v29 != 50 && v29 != 51 && v29 != 52 && v29 != 53 && v29 - 54 > 1 )
        goto LABEL_87;
LABEL_75:
      v30 = v29 - 48;
      goto LABEL_89;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800126ec  push    rbx
0x1800126ee  push    rsi
0x1800126ef  push    rdi
0x1800126f0  push    r12
0x1800126f2  push    r13
0x1800126f4  push    r14
0x1800126f6  push    r15
0x1800126f8  mov     eax, 22C0h
0x1800126fd  call    _alloca_probe
0x180012702  sub     rsp, rax
0x180012705  mov     rax, cs:__security_cookie
0x18001270c  xor     rax, rsp
0x18001270f  mov     [rsp+22F8h+var_48], rax
0x180012717  mov     r14, r8
0x18001271a  mov     [rsp+22F8h+lpValueName], r8
0x18001271f  mov     r12, rdx
0x180012722  mov     [rsp+22F8h+var_2288], rdx
0x180012727  mov     r15, rcx
0x18001272a  mov     [rsp+22F8h+var_22C0], rcx
0x18001272f  mov     [rsp+22F8h+var_22B0], rdx
0x180012734  mov     [rsp+22F8h+var_22A0], rcx
0x180012739  mov     [rsp+22F8h+var_2280], rdx
0x18001273e  mov     [rsp+22F8h+var_2298], r8
0x180012743  mov     [rsp+22F8h+var_2278], r9
0x18001274b  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180012753  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180012758  xor     ebx, ebx
0x18001275a  test    eax, eax
0x18001275c  js      short loc_180012790
0x18001275e  mov     edi, ebx
0x180012760  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180012767  movsxd  rsi, edi
0x18001276a  add     rsi, rsi
0x18001276d  mov     rdx, [r13+rsi*8+0]; lpString2
0x180012772  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18001277a  call    cs:__imp_lstrcmpiW
0x180012780  test    eax, eax
0x180012782  jz      short loc_1800127B3
0x180012784  inc     edi
0x180012786  cmp     edi, 4
0x180012789  jb      short loc_180012767
0x18001278b  mov     eax, 80020009h
0x180012790  mov     rcx, [rsp+22F8h+var_48]
0x180012798  xor     rcx, rsp; StackCookie
0x18001279b  call    __security_check_cookie
0x1800127a0  add     rsp, 22C0h
0x1800127a7  pop     r15
0x1800127a9  pop     r14
0x1800127ab  pop     r13
0x1800127ad  pop     r12
0x1800127af  pop     rdi
0x1800127b0  pop     rsi
0x1800127b1  pop     rbx
0x1800127b2  retn
0x1800127b3  movzx   edi, word ptr [r13+rsi*8+8]
0x1800127b9  mov     esi, 13h
0x1800127be  mov     rdx, [r15]
0x1800127c1  movzx   ecx, word ptr [rdx]
0x1800127c4  sub     ecx, 9
0x1800127c7  jz      loc_180012CB2
0x1800127cd  sub     ecx, 1
0x1800127d0  jz      loc_180012CB2
0x1800127d6  sub     ecx, 3
0x1800127d9  jz      loc_180012CB2
0x1800127df  cmp     ecx, esi
0x1800127e1  jz      loc_180012CB2
0x1800127e7  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800127ef  mov     rcx, r15; this
0x1800127f2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800127f7  test    eax, eax
0x1800127f9  js      short loc_180012790
0x1800127fb  mov     r13d, 8
0x180012801  cmp     di, r13w
0x180012805  jz      loc_180012C4C
0x18001280b  cmp     di, 11h
0x18001280f  jz      loc_180012A12
0x180012815  cmp     di, si
0x180012818  jz      loc_1800129B1
0x18001281e  mov     eax, 4008h
0x180012823  cmp     di, ax
0x180012826  jnz     loc_180012C96
0x18001282c  lea     rcx, [rsp+22F8h+String1]
0x180012834  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012838  mov     rax, rsi
0x18001283b  inc     rax
0x18001283e  cmp     [rcx+rax*2], bx
0x180012842  jnz     short loc_18001283B
0x180012844  add     eax, 2
0x180012847  mov     [rsp+22F8h+var_2158], rbx
0x18001284f  test    eax, eax
0x180012851  jz      short loc_180012884
0x180012853  movsxd  rcx, eax
0x180012856  xor     edx, edx
0x180012858  mov     rax, rsi
0x18001285b  div     rcx
0x18001285e  cmp     rax, 2
0x180012862  jb      loc_180012CC3
0x180012868  lea     rdx, [rcx+rcx]
0x18001286c  cmp     rdx, 100h
0x180012873  jbe     short loc_180012884
0x180012875  lea     rcx, [rsp+22F8h+var_2158]
0x18001287d  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180012882  jmp     short loc_180012894
0x180012884  lea     rax, [rsp+22F8h+var_2150]
0x18001288c  mov     [rsp+22F8h+var_2158], rax
0x180012894  mov     r13, [rsp+22F8h+lpValueName]
0x180012899  jmp     short loc_1800128B5
0x18001289b  xor     ebx, ebx
0x18001289d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800128a1  mov     r12, [rsp+22F8h+var_22B0]
0x1800128a6  mov     rax, [rsp+22F8h+var_22A0]
0x1800128ab  mov     [rsp+22F8h+var_22C0], rax
0x1800128b0  mov     r13, [rsp+22F8h+var_2298]
0x1800128b5  mov     rdi, [rsp+22F8h+var_2158]
0x1800128bd  test    rdi, rdi
0x1800128c0  jz      loc_180012974
0x1800128c6  lea     r14, [rsp+22F8h+String1]
0x1800128ce  cmp     [rsp+22F8h+String1], bx
0x1800128d6  jz      short loc_180012919
0x1800128d8  mov     r15d, 30h ; '0'
0x1800128de  mov     rcx, r14; lpsz
0x1800128e1  call    cs:__imp_CharNextW
0x1800128e7  movzx   ecx, word ptr [r14]
0x1800128eb  cmp     cx, 5Ch ; '\'
0x1800128ef  jnz     short loc_180012908
0x1800128f1  cmp     [rax], r15w
0x1800128f5  jnz     short loc_180012908
0x1800128f7  mov     [rdi], bx
0x1800128fa  mov     rcx, rax; lpsz
0x1800128fd  call    cs:__imp_CharNextW
0x180012903  mov     r14, rax
0x180012906  jmp     short loc_18001290F
0x180012908  mov     [rdi], cx
0x18001290b  add     r14, 2
0x18001290f  add     rdi, 2
0x180012913  cmp     [r14], bx
0x180012917  jnz     short loc_1800128DE
0x180012919  mov     dword ptr [rdi], 0
0x18001291f  mov     r8, [rsp+22F8h+var_2158]
0x180012927  test    r8, r8
0x18001292a  jz      loc_180012CCE
0x180012930  mov     r10d, ebx
0x180012933  mov     r9, r8
0x180012936  mov     rcx, rsi
0x180012939  inc     rcx
0x18001293c  cmp     [r9+rcx*2], bx
0x180012941  jnz     short loc_180012939
0x180012943  inc     ecx
0x180012945  lea     r9, [r9+rcx*2]
0x180012949  lea     r10d, [r10+rcx*2]
0x18001294d  cmp     ecx, 1
0x180012950  jnz     short loc_180012936
0x180012952  mov     [rsp+22F8h+cbData], r10d; cbData
0x180012957  mov     [rsp+22F8h+lpData], r8; lpData
0x18001295c  lea     r9d, [rcx+6]; dwType
0x180012960  xor     r8d, r8d; Reserved
0x180012963  mov     rdx, r13; lpValueName
0x180012966  mov     rcx, [r12]; hKey
0x18001296a  call    cs:__imp_RegSetValueExW
0x180012970  mov     edi, eax
0x180012972  jmp     short loc_180012979
0x180012974  mov     edi, 0Eh
0x180012979  lea     rax, [rsp+22F8h+var_2150]
0x180012981  cmp     [rsp+22F8h+var_2158], rax
0x180012989  jz      short loc_180012998
0x18001298b  lea     rcx, [rsp+22F8h+var_2158]
0x180012993  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180012998  mov     r15, [rsp+22F8h+var_22C0]
0x18001299d  test    edi, edi
0x18001299f  jz      loc_180012C96
0x1800129a5  mov     ecx, edi; unsigned int
0x1800129a7  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800129ac  jmp     loc_180012790
0x1800129b1  mov     [rsp+22F8h+pulOut], ebx
0x1800129b5  mov     [rsp+22F8h+var_2270], rbx
0x1800129bd  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x1800129c2  xor     r8d, r8d; dwFlags
0x1800129c5  xor     edx, edx; lcid
0x1800129c7  lea     rcx, [rsp+22F8h+String1]; strIn
0x1800129cf  call    cs:__imp_VarUI4FromStr
0x1800129d5  test    eax, eax
0x1800129d7  jns     short loc_1800129DE
0x1800129d9  jmp     loc_180012790
0x1800129de  mov     eax, [rsp+22F8h+pulOut]
0x1800129e2  mov     dword ptr [rsp+22F8h+Data], eax
0x1800129e6  mov     [rsp+22F8h+cbData], 4; cbData
0x1800129ee  lea     rax, [rsp+22F8h+Data]
0x1800129f3  mov     [rsp+22F8h+lpData], rax; lpData
0x1800129f8  mov     r9d, 4; dwType
0x1800129fe  xor     r8d, r8d; Reserved
0x180012a01  mov     rdx, r14; lpValueName
0x180012a04  mov     rcx, [r12]; hKey
0x180012a08  call    cs:__imp_RegSetValueExW
0x180012a0e  mov     edi, eax
0x180012a10  jmp     short loc_18001299D
0x180012a12  lea     rax, [rsp+22F8h+String1]
0x180012a1a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180012a1e  mov     r14, rsi
0x180012a21  inc     r14
0x180012a24  cmp     [rax+r14*2], bx
0x180012a29  jnz     short loc_180012A21
0x180012a2b  mov     [rsp+22F8h+var_22B4], r14d
0x180012a30  test    r14b, 1
0x180012a34  jnz     loc_180012B01
0x180012a3a  mov     eax, r14d
0x180012a3d  cdq
0x180012a3e  sub     eax, edx
0x180012a40  sar     eax, 1
0x180012a42  movsxd  r12, eax
0x180012a45  mov     dword ptr [rsp+22F8h+Data], r12d
0x180012a4a  mov     dword ptr [rsp+22F8h+var_22B0], r12d
0x180012a4f  mov     [rsp+22F8h+var_2268], rbx
0x180012a57  mov     rdi, r12
0x180012a5a  test    eax, eax
0x180012a5c  jnz     short loc_180012A63
0x180012a5e  mov     rdx, rbx
0x180012a61  jmp     short loc_180012A78
0x180012a63  xor     edx, edx
0x180012a65  mov     rax, rsi
0x180012a68  div     rdi
0x180012a6b  cmp     rax, 1
0x180012a6f  jb      loc_180012CD9
0x180012a75  mov     rdx, rdi
0x180012a78  cmp     rdx, 100h
0x180012a7f  jbe     short loc_180012A90
0x180012a81  lea     rcx, [rsp+22F8h+var_2268]
0x180012a89  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180012a8e  jmp     short loc_180012AA0
0x180012a90  lea     rax, [rsp+22F8h+var_2260]
0x180012a98  mov     [rsp+22F8h+var_2268], rax
0x180012aa0  mov     rsi, [rsp+22F8h+var_2288]
0x180012aa5  jmp     short loc_180012AD5
0x180012aa7  movsxd  rdi, dword ptr [rsp+22F8h+Data]
0x180012aac  xor     ebx, ebx
0x180012aae  lea     r13d, [rbx+8]
0x180012ab2  mov     r14d, [rsp+22F8h+var_22B4]
0x180012ab7  mov     r12d, dword ptr [rsp+22F8h+var_22B0]
0x180012abc  mov     rax, [rsp+22F8h+var_22A0]
0x180012ac1  mov     [rsp+22F8h+var_22C0], rax
0x180012ac6  mov     rsi, [rsp+22F8h+var_2280]
0x180012acb  mov     rax, [rsp+22F8h+var_2298]
0x180012ad0  mov     [rsp+22F8h+lpValueName], rax
0x180012ad5  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180012add  test    rcx, rcx
0x180012ae0  jnz     short loc_180012B0B
0x180012ae2  lea     rax, [rsp+22F8h+var_2260]
0x180012aea  cmp     [rsp+22F8h+var_2268], rax
0x180012af2  jz      short loc_180012B01
0x180012af4  lea     rcx, [rsp+22F8h+var_2268]
0x180012afc  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180012b01  mov     eax, 80004005h
0x180012b06  jmp     loc_180012790
0x180012b0b  mov     r8, rdi; Size
0x180012b0e  xor     edx, edx; Val
0x180012b10  call    memset_0
0x180012b15  mov     r10d, ebx
0x180012b18  test    r14d, r14d
0x180012b1b  jle     loc_180012BF9
0x180012b21  mov     r15d, 30h ; '0'
0x180012b27  mov     eax, r10d
0x180012b2a  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180012b32  cmp     edx, 61h ; 'a'
0x180012b35  ja      short loc_180012BA4
0x180012b37  jz      loc_180012BC4
0x180012b3d  cmp     edx, 38h ; '8'
0x180012b40  ja      short loc_180012B76
0x180012b42  jz      short loc_180012B6E
0x180012b44  mov     ecx, edx
0x180012b46  sub     ecx, r15d
0x180012b49  jz      short loc_180012B6E
0x180012b4b  sub     ecx, 1
0x180012b4e  jz      short loc_180012B6E
0x180012b50  sub     ecx, 1
0x180012b53  jz      short loc_180012B6E
0x180012b55  sub     ecx, 1
0x180012b58  jz      short loc_180012B6E
0x180012b5a  sub     ecx, 1
0x180012b5d  jz      short loc_180012B6E
0x180012b5f  sub     ecx, 1
0x180012b62  jz      short loc_180012B6E
0x180012b64  sub     ecx, 1
0x180012b67  jz      short loc_180012B6E
0x180012b69  cmp     ecx, 1
0x180012b6c  jnz     short loc_180012BBF
0x180012b6e  mov     r9d, edx
0x180012b71  sub     r9d, r15d
0x180012b74  jmp     short loc_180012BC8
0x180012b76  mov     r9d, edx
0x180012b79  mov     ecx, edx
0x180012b7b  sub     ecx, 39h ; '9'
0x180012b7e  jz      short loc_180012B6E
0x180012b80  sub     ecx, r13d
0x180012b83  jz      short loc_180012B9E
0x180012b85  sub     ecx, 1
0x180012b88  jz      short loc_180012B9E
0x180012b8a  sub     ecx, 1
0x180012b8d  jz      short loc_180012B9E
0x180012b8f  sub     ecx, 1
0x180012b92  jz      short loc_180012B9E
0x180012b94  sub     ecx, 1
  ... truncated ...
```
