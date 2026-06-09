# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000445c`
- end: `0x180004a55`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1529`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800087a0`

## callees

- `0x18000445c`
- `0x180004b7c`
- `0x180004df4`
- `0x180004ec8`
- `0x180006904`
- `0x180007a34`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800b0890`

## import_xrefs

- `USER32!CharNextW` at `0x180004651`
- `USER32!CharNextW` at `0x18000466d`
- `USER32!CharNextW` at `0x180004a25`
- `USER32!CharNextW` at `0x180004651`
- `USER32!CharNextW` at `0x18000466d`
- `USER32!CharNextW` at `0x180004a25`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000473f`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000473f`
- `KERNEL32!lstrcmpiW` at `0x1800044ea`
- `KERNEL32!lstrcmpiW` at `0x1800044ea`
- `ADVAPI32!RegSetValueExW` at `0x1800046da`
- `ADVAPI32!RegSetValueExW` at `0x180004778`
- `ADVAPI32!RegSetValueExW` at `0x18000498c`
- `ADVAPI32!RegSetValueExW` at `0x1800049f9`
- `ADVAPI32!RegSetValueExW` at `0x1800046da`
- `ADVAPI32!RegSetValueExW` at `0x180004778`
- `ADVAPI32!RegSetValueExW` at `0x18000498c`
- `ADVAPI32!RegSetValueExW` at `0x1800049f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

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
0x18000445c  push    rbx
0x18000445e  push    rsi
0x18000445f  push    rdi
0x180004460  push    r12
0x180004462  push    r13
0x180004464  push    r14
0x180004466  push    r15
0x180004468  mov     eax, 22C0h
0x18000446d  call    _alloca_probe
0x180004472  sub     rsp, rax
0x180004475  mov     rax, cs:__security_cookie
0x18000447c  xor     rax, rsp
0x18000447f  mov     [rsp+22F8h+var_48], rax
0x180004487  mov     r14, r8
0x18000448a  mov     [rsp+22F8h+lpValueName], r8
0x18000448f  mov     r12, rdx
0x180004492  mov     [rsp+22F8h+var_2288], rdx
0x180004497  mov     r15, rcx
0x18000449a  mov     [rsp+22F8h+var_22C0], rcx
0x18000449f  mov     [rsp+22F8h+var_22B0], rdx
0x1800044a4  mov     [rsp+22F8h+var_22A0], rcx
0x1800044a9  mov     [rsp+22F8h+var_2280], rdx
0x1800044ae  mov     [rsp+22F8h+var_2298], r8
0x1800044b3  mov     [rsp+22F8h+var_2278], r9
0x1800044bb  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800044c3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800044c8  xor     ebx, ebx
0x1800044ca  test    eax, eax
0x1800044cc  js      short loc_180004500
0x1800044ce  mov     edi, ebx
0x1800044d0  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800044d7  movsxd  rsi, edi
0x1800044da  add     rsi, rsi
0x1800044dd  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800044e2  lea     rcx, [rsp+22F8h+String1]; lpString1
0x1800044ea  call    cs:__imp_lstrcmpiW
0x1800044f0  test    eax, eax
0x1800044f2  jz      short loc_180004523
0x1800044f4  inc     edi
0x1800044f6  cmp     edi, 4
0x1800044f9  jb      short loc_1800044D7
0x1800044fb  mov     eax, 80020009h
0x180004500  mov     rcx, [rsp+22F8h+var_48]
0x180004508  xor     rcx, rsp; StackCookie
0x18000450b  call    __security_check_cookie
0x180004510  add     rsp, 22C0h
0x180004517  pop     r15
0x180004519  pop     r14
0x18000451b  pop     r13
0x18000451d  pop     r12
0x18000451f  pop     rdi
0x180004520  pop     rsi
0x180004521  pop     rbx
0x180004522  retn
0x180004523  movzx   edi, word ptr [r13+rsi*8+8]
0x180004529  mov     esi, 13h
0x18000452e  mov     rdx, [r15]
0x180004531  movzx   ecx, word ptr [rdx]
0x180004534  sub     ecx, 9
0x180004537  jz      loc_180004A22
0x18000453d  sub     ecx, 1
0x180004540  jz      loc_180004A22
0x180004546  sub     ecx, 3
0x180004549  jz      loc_180004A22
0x18000454f  cmp     ecx, esi
0x180004551  jz      loc_180004A22
0x180004557  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000455f  mov     rcx, r15; this
0x180004562  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004567  test    eax, eax
0x180004569  js      short loc_180004500
0x18000456b  mov     r13d, 8
0x180004571  cmp     di, r13w
0x180004575  jz      loc_1800049BC
0x18000457b  cmp     di, 11h
0x18000457f  jz      loc_180004782
0x180004585  cmp     di, si
0x180004588  jz      loc_180004721
0x18000458e  mov     eax, 4008h
0x180004593  cmp     di, ax
0x180004596  jnz     loc_180004A06
0x18000459c  lea     rcx, [rsp+22F8h+String1]
0x1800045a4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800045a8  mov     rax, rsi
0x1800045ab  inc     rax
0x1800045ae  cmp     [rcx+rax*2], bx
0x1800045b2  jnz     short loc_1800045AB
0x1800045b4  add     eax, 2
0x1800045b7  mov     [rsp+22F8h+var_2158], rbx
0x1800045bf  test    eax, eax
0x1800045c1  jz      short loc_1800045F4
0x1800045c3  movsxd  rcx, eax
0x1800045c6  xor     edx, edx
0x1800045c8  mov     rax, rsi
0x1800045cb  div     rcx
0x1800045ce  cmp     rax, 2
0x1800045d2  jb      loc_180004A33
0x1800045d8  lea     rdx, [rcx+rcx]
0x1800045dc  cmp     rdx, 100h
0x1800045e3  jbe     short loc_1800045F4
0x1800045e5  lea     rcx, [rsp+22F8h+var_2158]
0x1800045ed  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800045f2  jmp     short loc_180004604
0x1800045f4  lea     rax, [rsp+22F8h+var_2150]
0x1800045fc  mov     [rsp+22F8h+var_2158], rax
0x180004604  mov     r13, [rsp+22F8h+lpValueName]
0x180004609  jmp     short loc_180004625
0x18000460b  xor     ebx, ebx
0x18000460d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004611  mov     r12, [rsp+22F8h+var_22B0]
0x180004616  mov     rax, [rsp+22F8h+var_22A0]
0x18000461b  mov     [rsp+22F8h+var_22C0], rax
0x180004620  mov     r13, [rsp+22F8h+var_2298]
0x180004625  mov     rdi, [rsp+22F8h+var_2158]
0x18000462d  test    rdi, rdi
0x180004630  jz      loc_1800046E4
0x180004636  lea     r14, [rsp+22F8h+String1]
0x18000463e  cmp     [rsp+22F8h+String1], bx
0x180004646  jz      short loc_180004689
0x180004648  mov     r15d, 30h ; '0'
0x18000464e  mov     rcx, r14; lpsz
0x180004651  call    cs:__imp_CharNextW
0x180004657  movzx   ecx, word ptr [r14]
0x18000465b  cmp     cx, 5Ch ; '\'
0x18000465f  jnz     short loc_180004678
0x180004661  cmp     [rax], r15w
0x180004665  jnz     short loc_180004678
0x180004667  mov     [rdi], bx
0x18000466a  mov     rcx, rax; lpsz
0x18000466d  call    cs:__imp_CharNextW
0x180004673  mov     r14, rax
0x180004676  jmp     short loc_18000467F
0x180004678  mov     [rdi], cx
0x18000467b  add     r14, 2
0x18000467f  add     rdi, 2
0x180004683  cmp     [r14], bx
0x180004687  jnz     short loc_18000464E
0x180004689  mov     dword ptr [rdi], 0
0x18000468f  mov     r8, [rsp+22F8h+var_2158]
0x180004697  test    r8, r8
0x18000469a  jz      loc_180004A3E
0x1800046a0  mov     r10d, ebx
0x1800046a3  mov     r9, r8
0x1800046a6  mov     rcx, rsi
0x1800046a9  inc     rcx
0x1800046ac  cmp     [r9+rcx*2], bx
0x1800046b1  jnz     short loc_1800046A9
0x1800046b3  inc     ecx
0x1800046b5  lea     r9, [r9+rcx*2]
0x1800046b9  lea     r10d, [r10+rcx*2]
0x1800046bd  cmp     ecx, 1
0x1800046c0  jnz     short loc_1800046A6
0x1800046c2  mov     [rsp+22F8h+cbData], r10d; cbData
0x1800046c7  mov     [rsp+22F8h+lpData], r8; lpData
0x1800046cc  lea     r9d, [rcx+6]; dwType
0x1800046d0  xor     r8d, r8d; Reserved
0x1800046d3  mov     rdx, r13; lpValueName
0x1800046d6  mov     rcx, [r12]; hKey
0x1800046da  call    cs:__imp_RegSetValueExW
0x1800046e0  mov     edi, eax
0x1800046e2  jmp     short loc_1800046E9
0x1800046e4  mov     edi, 0Eh
0x1800046e9  lea     rax, [rsp+22F8h+var_2150]
0x1800046f1  cmp     [rsp+22F8h+var_2158], rax
0x1800046f9  jz      short loc_180004708
0x1800046fb  lea     rcx, [rsp+22F8h+var_2158]
0x180004703  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004708  mov     r15, [rsp+22F8h+var_22C0]
0x18000470d  test    edi, edi
0x18000470f  jz      loc_180004A06
0x180004715  mov     ecx, edi; unsigned int
0x180004717  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000471c  jmp     loc_180004500
0x180004721  mov     [rsp+22F8h+pulOut], ebx
0x180004725  mov     [rsp+22F8h+var_2270], rbx
0x18000472d  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180004732  xor     r8d, r8d; dwFlags
0x180004735  xor     edx, edx; lcid
0x180004737  lea     rcx, [rsp+22F8h+String1]; strIn
0x18000473f  call    cs:__imp_VarUI4FromStr
0x180004745  test    eax, eax
0x180004747  jns     short loc_18000474E
0x180004749  jmp     loc_180004500
0x18000474e  mov     eax, [rsp+22F8h+pulOut]
0x180004752  mov     dword ptr [rsp+22F8h+Data], eax
0x180004756  mov     [rsp+22F8h+cbData], 4; cbData
0x18000475e  lea     rax, [rsp+22F8h+Data]
0x180004763  mov     [rsp+22F8h+lpData], rax; lpData
0x180004768  mov     r9d, 4; dwType
0x18000476e  xor     r8d, r8d; Reserved
0x180004771  mov     rdx, r14; lpValueName
0x180004774  mov     rcx, [r12]; hKey
0x180004778  call    cs:__imp_RegSetValueExW
0x18000477e  mov     edi, eax
0x180004780  jmp     short loc_18000470D
0x180004782  lea     rax, [rsp+22F8h+String1]
0x18000478a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000478e  mov     r14, rsi
0x180004791  inc     r14
0x180004794  cmp     [rax+r14*2], bx
0x180004799  jnz     short loc_180004791
0x18000479b  mov     [rsp+22F8h+var_22B4], r14d
0x1800047a0  test    r14b, 1
0x1800047a4  jnz     loc_180004871
0x1800047aa  mov     eax, r14d
0x1800047ad  cdq
0x1800047ae  sub     eax, edx
0x1800047b0  sar     eax, 1
0x1800047b2  movsxd  r12, eax
0x1800047b5  mov     dword ptr [rsp+22F8h+Data], r12d
0x1800047ba  mov     dword ptr [rsp+22F8h+var_22B0], r12d
0x1800047bf  mov     [rsp+22F8h+var_2268], rbx
0x1800047c7  mov     rdi, r12
0x1800047ca  test    eax, eax
0x1800047cc  jnz     short loc_1800047D3
0x1800047ce  mov     rdx, rbx
0x1800047d1  jmp     short loc_1800047E8
0x1800047d3  xor     edx, edx
0x1800047d5  mov     rax, rsi
0x1800047d8  div     rdi
0x1800047db  cmp     rax, 1
0x1800047df  jb      loc_180004A49
0x1800047e5  mov     rdx, rdi
0x1800047e8  cmp     rdx, 100h
0x1800047ef  jbe     short loc_180004800
0x1800047f1  lea     rcx, [rsp+22F8h+var_2268]
0x1800047f9  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800047fe  jmp     short loc_180004810
0x180004800  lea     rax, [rsp+22F8h+var_2260]
0x180004808  mov     [rsp+22F8h+var_2268], rax
0x180004810  mov     rsi, [rsp+22F8h+var_2288]
0x180004815  jmp     short loc_180004845
0x180004817  movsxd  rdi, dword ptr [rsp+22F8h+Data]
0x18000481c  xor     ebx, ebx
0x18000481e  lea     r13d, [rbx+8]
0x180004822  mov     r14d, [rsp+22F8h+var_22B4]
0x180004827  mov     r12d, dword ptr [rsp+22F8h+var_22B0]
0x18000482c  mov     rax, [rsp+22F8h+var_22A0]
0x180004831  mov     [rsp+22F8h+var_22C0], rax
0x180004836  mov     rsi, [rsp+22F8h+var_2280]
0x18000483b  mov     rax, [rsp+22F8h+var_2298]
0x180004840  mov     [rsp+22F8h+lpValueName], rax
0x180004845  mov     rcx, [rsp+22F8h+var_2268]; void *
0x18000484d  test    rcx, rcx
0x180004850  jnz     short loc_18000487B
0x180004852  lea     rax, [rsp+22F8h+var_2260]
0x18000485a  cmp     [rsp+22F8h+var_2268], rax
0x180004862  jz      short loc_180004871
0x180004864  lea     rcx, [rsp+22F8h+var_2268]
0x18000486c  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004871  mov     eax, 80004005h
0x180004876  jmp     loc_180004500
0x18000487b  mov     r8, rdi; Size
0x18000487e  xor     edx, edx; Val
0x180004880  call    memset_0
0x180004885  mov     r10d, ebx
0x180004888  test    r14d, r14d
0x18000488b  jle     loc_180004969
0x180004891  mov     r15d, 30h ; '0'
0x180004897  mov     eax, r10d
0x18000489a  movzx   edx, [rsp+rax*2+22F8h+String1]
0x1800048a2  cmp     edx, 61h ; 'a'
0x1800048a5  ja      short loc_180004914
0x1800048a7  jz      loc_180004934
0x1800048ad  cmp     edx, 38h ; '8'
0x1800048b0  ja      short loc_1800048E6
0x1800048b2  jz      short loc_1800048DE
0x1800048b4  mov     ecx, edx
0x1800048b6  sub     ecx, r15d
0x1800048b9  jz      short loc_1800048DE
0x1800048bb  sub     ecx, 1
0x1800048be  jz      short loc_1800048DE
0x1800048c0  sub     ecx, 1
0x1800048c3  jz      short loc_1800048DE
0x1800048c5  sub     ecx, 1
0x1800048c8  jz      short loc_1800048DE
0x1800048ca  sub     ecx, 1
0x1800048cd  jz      short loc_1800048DE
0x1800048cf  sub     ecx, 1
0x1800048d2  jz      short loc_1800048DE
0x1800048d4  sub     ecx, 1
0x1800048d7  jz      short loc_1800048DE
0x1800048d9  cmp     ecx, 1
0x1800048dc  jnz     short loc_18000492F
0x1800048de  mov     r9d, edx
0x1800048e1  sub     r9d, r15d
0x1800048e4  jmp     short loc_180004938
0x1800048e6  mov     r9d, edx
0x1800048e9  mov     ecx, edx
0x1800048eb  sub     ecx, 39h ; '9'
0x1800048ee  jz      short loc_1800048DE
0x1800048f0  sub     ecx, r13d
0x1800048f3  jz      short loc_18000490E
0x1800048f5  sub     ecx, 1
0x1800048f8  jz      short loc_18000490E
0x1800048fa  sub     ecx, 1
0x1800048fd  jz      short loc_18000490E
0x1800048ff  sub     ecx, 1
0x180004902  jz      short loc_18000490E
0x180004904  sub     ecx, 1
  ... truncated ...
```
