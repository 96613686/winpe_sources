# ATL::CRegParser::AddValue(ATL::CRegKey &,char const *,char *)

- ea: `0x18000f804`
- end: `0x18000fe2c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBDPEAD@Z`
- size: `1576`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const char *, char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180011b0c`

## callees

- `0x180003b70`
- `0x1800099ac`
- `0x18000f804`
- `0x18000fe34`
- `0x180010074`
- `0x180010f34`
- `0x180011060`
- `0x18001423e`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `msvcrt!free` at `0x18000fb8b`
- `msvcrt!free` at `0x18000fba3`
- `msvcrt!free` at `0x18000fbcc`
- `msvcrt!free` at `0x18000fb8b`
- `msvcrt!free` at `0x18000fba3`
- `msvcrt!free` at `0x18000fbcc`
- `msvcrt!malloc` at `0x18000faec`
- `msvcrt!malloc` at `0x18000faec`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000fb4a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000fb4a`
- `USER32!CharNextA` at `0x18000f8b3`
- `USER32!CharNextA` at `0x18000f98b`
- `USER32!CharNextA` at `0x18000f9a3`
- `USER32!CharNextA` at `0x18000f8b3`
- `USER32!CharNextA` at `0x18000f98b`
- `USER32!CharNextA` at `0x18000f9a3`
- `KERNEL32!IsDBCSLeadByte` at `0x18000f9b2`
- `KERNEL32!IsDBCSLeadByte` at `0x18000f9b2`
- `KERNEL32!lstrcmpiA` at `0x18000f872`
- `KERNEL32!lstrcmpiA` at `0x18000f872`
- `KERNEL32!MultiByteToWideChar` at `0x18000fb30`
- `KERNEL32!MultiByteToWideChar` at `0x18000fb30`
- `ADVAPI32!RegSetValueExA` at `0x18000fa24`
- `ADVAPI32!RegSetValueExA` at `0x18000fb7b`
- `ADVAPI32!RegSetValueExA` at `0x18000fd61`
- `ADVAPI32!RegSetValueExA` at `0x18000fdbc`
- `ADVAPI32!RegSetValueExA` at `0x18000fa24`
- `ADVAPI32!RegSetValueExA` at `0x18000fb7b`
- `ADVAPI32!RegSetValueExA` at `0x18000fd61`
- `ADVAPI32!RegSetValueExA` at `0x18000fdbc`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(ATL::CRegParser *this, HKEY *a2, const char *a3, char *a4)
{
  char *v5; // r14
  __int64 result; // rax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  CHAR *v13; // rbx
  CHAR *i; // rdi
  const CHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  unsigned int v19; // ecx
  LSTATUS v20; // eax
  LSTATUS v21; // edi
  __int64 v22; // rax
  int v23; // ecx
  _QWORD *v24; // rbx
  unsigned __int64 v25; // rdi
  __int64 v26; // rax
  void *v27; // rsp
  WCHAR *v28; // r14
  _QWORD *v29; // rax
  HRESULT v30; // edi
  HKEY v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  __int64 v35; // rdi
  size_t v36; // rbx
  BYTE *v37; // rcx
  __int64 v38; // r10
  int v39; // r9d
  char v40; // r9
  unsigned __int64 v41; // r8
  char v42; // r9
  __int64 v43; // rsi
  int Token; // eax
  unsigned int v45; // ecx
  WCHAR WideCharStr[2]; // [rsp+30h] [rbp+0h] BYREF
  char *v47; // [rsp+38h] [rbp+8h]
  BYTE Data[16]; // [rsp+40h] [rbp+10h] BYREF
  BYTE *v49; // [rsp+50h] [rbp+20h] BYREF
  _BYTE v50[264]; // [rsp+58h] [rbp+28h] BYREF
  BYTE *lpData; // [rsp+160h] [rbp+130h] BYREF
  CHAR v52[264]; // [rsp+168h] [rbp+138h] BYREF
  CHAR String1[4096]; // [rsp+270h] [rbp+240h] BYREF

  v47 = a4;
  v5 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( (int)result < 0 )
    return result;
  v9 = 0;
  while ( lstrcmpiA(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
  {
    if ( (unsigned int)++v9 >= 4 )
      return 2147614729LL;
  }
  v10 = (__int16)(&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9 + 1];
  while ( **(_BYTE **)this == 9 || **(_BYTE **)this == 10 || **(_BYTE **)this == 13 || **(_BYTE **)this == 32 )
    *(_QWORD *)this = CharNextA(*(LPCSTR *)this);
  result = ATL::CRegParser::NextToken(this, String1);
  if ( (int)result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v43 = -1;
    do
      ++v43;
    while ( String1[v43] );
    v21 = RegSetValueExA(*a2, a3, 0, 1u, (const BYTE *)String1, v43 + 1);
    goto LABEL_65;
  }
  if ( v10 == 17 )
  {
    v35 = -1;
    do
      ++v35;
    while ( String1[v35] );
    if ( (v35 & 1) != 0 )
      return 2147500037LL;
    v49 = 0;
    v36 = (int)v35 / 2;
    if ( !((int)v35 / 2) )
      goto LABEL_77;
    if ( !(0xFFFFFFFFFFFFFFFFuLL / v36) )
      ATL::AtlThrowImpl(-2147024809);
    if ( v36 > 0x100 )
    {
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(&v49, v36);
      v37 = v49;
    }
    else
    {
LABEL_77:
      v37 = v50;
      v49 = v50;
    }
    if ( !v37 )
    {
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&v49);
      return 2147500037LL;
    }
    memset_0(v37, 0, v36);
    v38 = 0;
    if ( (int)v35 <= 0 )
    {
LABEL_108:
      v21 = RegSetValueExA(*a2, a3, 0, 3u, v49, (int)v35 / 2);
      if ( v49 != v50 )
        ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&v49);
      goto LABEL_64;
    }
    while ( 1 )
    {
      v39 = String1[v38];
      if ( String1[v38] > 97 )
      {
        if ( v39 == 98 || v39 == 99 || v39 == 100 || (unsigned int)(v39 - 101) < 2 )
        {
LABEL_106:
          v40 = v39 - 87;
          goto LABEL_107;
        }
LABEL_105:
        v40 = 0;
        goto LABEL_107;
      }
      if ( String1[v38] == 97 )
        goto LABEL_106;
      if ( (char)v39 <= 56 )
        break;
      if ( v39 == 57 )
        goto LABEL_93;
      if ( v39 != 65 && v39 != 66 && v39 != 67 && v39 != 68 && (unsigned int)(v39 - 69) > 1 )
        goto LABEL_105;
      v40 = v39 - 55;
LABEL_107:
      v41 = (unsigned __int64)(unsigned int)v38 >> 1;
      v42 = v40 << (4 - 4 * (v38 & 1));
      v38 = (unsigned int)(v38 + 1);
      v49[v41] |= v42;
      if ( (int)v38 >= (int)v35 )
        goto LABEL_108;
    }
    if ( (_BYTE)v39 != 56
      && v39 != 48
      && v39 != 49
      && v39 != 50
      && v39 != 51
      && v39 != 52
      && v39 != 53
      && (unsigned int)(v39 - 54) > 1 )
    {
      goto LABEL_105;
    }
LABEL_93:
    v40 = v39 - 48;
    goto LABEL_107;
  }
  if ( v10 != 19 )
  {
    if ( v10 != 16392 )
    {
LABEL_113:
      Token = ATL::CRegParser::NextToken(this, v5);
      v45 = 0;
      if ( Token < 0 )
        return (unsigned int)Token;
      return v45;
    }
    lpData = 0;
    v11 = -1;
    do
      ++v11;
    while ( String1[v11] );
    v12 = (int)v11 + 2;
    if ( (_DWORD)v11 == -2 )
      goto LABEL_23;
    if ( !(0xFFFFFFFFFFFFFFFFuLL / v12) )
      ATL::AtlThrowImpl(-2147024809);
    if ( v12 <= 0x100 )
    {
LABEL_23:
      v13 = v52;
      lpData = (BYTE *)v52;
    }
    else
    {
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
      v13 = (CHAR *)lpData;
    }
    if ( v13 )
    {
      for ( i = String1; *i; ++v13 )
      {
        v15 = CharNextA(i);
        if ( *i == 92 && *v15 == 48 )
        {
          *v13 = 0;
          i = CharNextA(v15);
        }
        else
        {
          *v13 = *i;
          if ( IsDBCSLeadByte(*i) )
          {
            ++v13;
            if ( !*++i )
              break;
            *v13 = *i;
          }
          ++i;
        }
      }
      *(_WORD *)v13 = 0;
      if ( !lpData )
        ATL::AtlThrowImpl(-2147467259);
      cbData = 0;
      v17 = lpData;
      do
      {
        v18 = -1;
        do
          ++v18;
        while ( v17[v18] );
        v19 = v18 + 1;
        cbData += v19;
        v17 += v19;
      }
      while ( v19 != 1 );
      v20 = RegSetValueExA(*a2, a3, 0, 7u, lpData, cbData);
      v13 = (CHAR *)lpData;
      v21 = v20;
    }
    else
    {
      v21 = 14;
    }
    if ( v13 != v52 )
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
LABEL_65:
    if ( v21 )
      return ATL::AtlHresultFromWin32(v21);
    goto LABEL_113;
  }
  *(_DWORD *)WideCharStr = 0;
  v22 = -1;
  do
    ++v22;
  while ( String1[v22] );
  v23 = 2 * v22 + 2;
  if ( (unsigned __int64)(2LL * (int)v22 + 2147483650LL) > 0xFFFFFFFF )
    return 2147942414LL;
  v24 = 0;
  v25 = v23;
  if ( v23 <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v23, 0xFFFFFFFF) )
  {
    v26 = v25 + 15;
    if ( v25 + 15 < v25 )
      v26 = 0xFFFFFFFFFFFFFF0LL;
    v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
    v28 = WideCharStr;
  }
  else
  {
    if ( ~v25 < 0x10 )
      ATL::AtlThrowImpl(-2147024809);
    v29 = malloc(v25 + 16);
    if ( v29 )
    {
      *v29 = 0;
      v28 = (WCHAR *)(v29 + 2);
      v24 = v29;
    }
    else
    {
      v28 = 0;
    }
  }
  if ( !v28 || (*v28 = 0, !MultiByteToWideChar(3u, 0, String1, -1, v28, v25 >> 1)) )
  {
    while ( v24 )
    {
      v34 = v24;
      v24 = (_QWORD *)*v24;
      free(v34);
    }
    return 2147942414LL;
  }
  v30 = VarUI4FromStr(v28, 0, 0, (ULONG *)WideCharStr);
  if ( v30 >= 0 )
  {
    v31 = *a2;
    *(_DWORD *)Data = *(_DWORD *)WideCharStr;
    v21 = RegSetValueExA(v31, a3, 0, 4u, Data, 4u);
    while ( v24 )
    {
      v33 = v24;
      v24 = (_QWORD *)*v24;
      free(v33);
    }
LABEL_64:
    v5 = v47;
    goto LABEL_65;
  }
  while ( v24 )
  {
    v32 = v24;
    v24 = (_QWORD *)*v24;
    free(v32);
  }
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x18000f804  push    rbp
0x18000f806  push    rbx
0x18000f807  push    rsi
0x18000f808  push    rdi
0x18000f809  push    r12
0x18000f80b  push    r13
0x18000f80d  push    r14
0x18000f80f  push    r15
0x18000f811  mov     eax, 1288h
0x18000f816  call    _alloca_probe
0x18000f81b  sub     rsp, rax
0x18000f81e  lea     rbp, [rsp+30h]
0x18000f823  mov     rax, cs:__security_cookie
0x18000f82a  xor     rax, rbp
0x18000f82d  mov     [rbp+1290h+var_50], rax
0x18000f834  mov     r12, rdx
0x18000f837  mov     [rbp+1290h+var_1288], r9
0x18000f83b  lea     rdx, [rbp+1290h+String1]; char *
0x18000f842  mov     r14, r9
0x18000f845  mov     r13, r8
0x18000f848  mov     r15, rcx
0x18000f84b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x18000f850  test    eax, eax
0x18000f852  js      loc_18000FDDD
0x18000f858  xor     ebx, ebx
0x18000f85a  lea     rsi, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBDAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(char const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(char const *,ushort &)'::`2'::map
0x18000f861  movsxd  rdi, ebx
0x18000f864  lea     rcx, [rbp+1290h+String1]; lpString1
0x18000f86b  add     rdi, rdi
0x18000f86e  mov     rdx, [rsi+rdi*8]; lpString2
0x18000f872  call    cs:__imp_lstrcmpiA
0x18000f878  test    eax, eax
0x18000f87a  jz      short loc_18000F88D
0x18000f87c  inc     ebx
0x18000f87e  cmp     ebx, 4
0x18000f881  jb      short loc_18000F861
0x18000f883  mov     eax, 80020009h
0x18000f888  jmp     loc_18000FDDD
0x18000f88d  movzx   ebx, word ptr [rsi+rdi*8+8]
0x18000f892  mov     edi, 13h
0x18000f897  mov     rdx, [r15]
0x18000f89a  movsx   ecx, byte ptr [rdx]
0x18000f89d  sub     ecx, 9
0x18000f8a0  jz      short loc_18000F8B0
0x18000f8a2  sub     ecx, 1
0x18000f8a5  jz      short loc_18000F8B0
0x18000f8a7  sub     ecx, 3
0x18000f8aa  jz      short loc_18000F8B0
0x18000f8ac  cmp     ecx, edi
0x18000f8ae  jnz     short loc_18000F8BE
0x18000f8b0  mov     rcx, rdx; lpsz
0x18000f8b3  call    cs:__imp_CharNextA
0x18000f8b9  mov     [r15], rax
0x18000f8bc  jmp     short loc_18000F897
0x18000f8be  lea     rdx, [rbp+1290h+String1]; char *
0x18000f8c5  mov     rcx, r15; this
0x18000f8c8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAD@Z; ATL::CRegParser::NextToken(char *)
0x18000f8cd  test    eax, eax
0x18000f8cf  js      loc_18000FDDD
0x18000f8d5  mov     eax, 8
0x18000f8da  cmp     bx, ax
0x18000f8dd  jz      loc_18000FD85
0x18000f8e3  cmp     bx, 11h
0x18000f8e7  jz      loc_18000FBE1
0x18000f8ed  cmp     bx, di
0x18000f8f0  jz      loc_18000FA5B
0x18000f8f6  mov     eax, 4008h
0x18000f8fb  cmp     bx, ax
0x18000f8fe  jnz     loc_18000FDC9
0x18000f904  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f908  mov     [rbp+1290h+var_1160], 0
0x18000f913  mov     rax, rsi
0x18000f916  lea     rcx, [rbp+1290h+String1]
0x18000f91d  inc     rax
0x18000f920  cmp     byte ptr [rcx+rax], 0
0x18000f924  jnz     short loc_18000F91D
0x18000f926  add     eax, 2
0x18000f929  movsxd  rcx, eax
0x18000f92c  jz      short loc_18000F961
0x18000f92e  xor     edx, edx
0x18000f930  mov     rax, rsi
0x18000f933  div     rcx
0x18000f936  cmp     rax, 1
0x18000f93a  jb      loc_18000FE0B
0x18000f940  cmp     rcx, 100h
0x18000f947  jbe     short loc_18000F961
0x18000f949  mov     rdx, rcx
0x18000f94c  lea     rcx, [rbp+1290h+var_1160]
0x18000f953  call    ?AllocateHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000f958  mov     rbx, [rbp+1290h+var_1160]
0x18000f95f  jmp     short loc_18000F96F
0x18000f961  lea     rbx, [rbp+1290h+var_1158]
0x18000f968  mov     [rbp+1290h+var_1160], rbx
0x18000f96f  test    rbx, rbx
0x18000f972  jz      loc_18000FA35
0x18000f978  cmp     [rbp+1290h+String1], 0
0x18000f97f  lea     rdi, [rbp+1290h+String1]
0x18000f986  jz      short loc_18000F9D5
0x18000f988  mov     rcx, rdi; lpsz
0x18000f98b  call    cs:__imp_CharNextA
0x18000f991  mov     cl, [rdi]
0x18000f993  cmp     cl, 5Ch ; '\'
0x18000f996  jnz     short loc_18000F9AE
0x18000f998  cmp     byte ptr [rax], 30h ; '0'
0x18000f99b  jnz     short loc_18000F9AE
0x18000f99d  mov     rcx, rax; lpsz
0x18000f9a0  mov     byte ptr [rbx], 0
0x18000f9a3  call    cs:__imp_CharNextA
0x18000f9a9  mov     rdi, rax
0x18000f9ac  jmp     short loc_18000F9CD
0x18000f9ae  mov     [rbx], cl
0x18000f9b0  mov     cl, [rdi]; TestChar
0x18000f9b2  call    cs:__imp_IsDBCSLeadByte
0x18000f9b8  test    eax, eax
0x18000f9ba  jz      short loc_18000F9CA
0x18000f9bc  inc     rbx
0x18000f9bf  inc     rdi
0x18000f9c2  mov     al, [rdi]
0x18000f9c4  test    al, al
0x18000f9c6  jz      short loc_18000F9D5
0x18000f9c8  mov     [rbx], al
0x18000f9ca  inc     rdi
0x18000f9cd  inc     rbx
0x18000f9d0  cmp     byte ptr [rdi], 0
0x18000f9d3  jnz     short loc_18000F988
0x18000f9d5  mov     word ptr [rbx], 0
0x18000f9da  mov     r8, [rbp+1290h+var_1160]
0x18000f9e1  test    r8, r8
0x18000f9e4  jz      loc_18000FE16
0x18000f9ea  xor     r10d, r10d
0x18000f9ed  mov     r9, r8
0x18000f9f0  mov     rcx, rsi
0x18000f9f3  inc     rcx
0x18000f9f6  cmp     byte ptr [r9+rcx], 0
0x18000f9fb  jnz     short loc_18000F9F3
0x18000f9fd  inc     ecx
0x18000f9ff  mov     eax, ecx
0x18000fa01  add     r10d, ecx
0x18000fa04  add     r9, rax
0x18000fa07  cmp     ecx, 1
0x18000fa0a  jnz     short loc_18000F9F0
0x18000fa0c  mov     [rsp+12C0h+cbData], r10d; cbData
0x18000fa11  lea     r9d, [rcx+6]; dwType
0x18000fa15  mov     rcx, [r12]; hKey
0x18000fa19  mov     rdx, r13; lpValueName
0x18000fa1c  mov     [rsp+12C0h+lpData], r8; lpData
0x18000fa21  xor     r8d, r8d; Reserved
0x18000fa24  call    cs:__imp_RegSetValueExA
0x18000fa2a  mov     rbx, [rbp+1290h+var_1160]
0x18000fa31  mov     edi, eax
0x18000fa33  jmp     short loc_18000FA3A
0x18000fa35  mov     edi, 0Eh
0x18000fa3a  lea     rax, [rbp+1290h+var_1158]
0x18000fa41  cmp     rbx, rax
0x18000fa44  jz      loc_18000FBB2
0x18000fa4a  lea     rcx, [rbp+1290h+var_1160]
0x18000fa51  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000fa56  jmp     loc_18000FBB2
0x18000fa5b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000fa5f  mov     dword ptr [rbp+1290h+WideCharStr], 0
0x18000fa66  mov     rax, rsi
0x18000fa69  lea     rcx, [rbp+1290h+String1]
0x18000fa70  inc     rax
0x18000fa73  cmp     byte ptr [rcx+rax], 0
0x18000fa77  jnz     short loc_18000FA70
0x18000fa79  cdqe
0x18000fa7b  mov     edx, 0FFFFFFFFh; unsigned __int64
0x18000fa80  lea     rcx, ds:2[rax*2]
0x18000fa88  mov     eax, 80000000h
0x18000fa8d  add     rax, rcx
0x18000fa90  cmp     rax, rdx
0x18000fa93  ja      loc_18000FBD7
0x18000fa99  xor     ebx, ebx
0x18000fa9b  movsxd  rdi, ecx
0x18000fa9e  cmp     ecx, 400h
0x18000faa4  jg      short loc_18000FAD8
0x18000faa6  mov     rcx, rdi; this
0x18000faa9  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000faae  test    al, al
0x18000fab0  jz      short loc_18000FAD8
0x18000fab2  lea     rax, [rdi+0Fh]
0x18000fab6  cmp     rax, rdi
0x18000fab9  ja      short loc_18000FAC5
0x18000fabb  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000fac5  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000fac9  call    _alloca_probe
0x18000face  sub     rsp, rax
0x18000fad1  lea     r14, [rsp+12C0h+WideCharStr]
0x18000fad6  jmp     short loc_18000FB06
0x18000fad8  mov     rax, rdi
0x18000fadb  not     rax
0x18000fade  cmp     rax, 10h
0x18000fae2  jb      loc_18000FE21
0x18000fae8  lea     rcx, [rdi+10h]; Size
0x18000faec  call    cs:__imp_malloc
0x18000faf2  test    rax, rax
0x18000faf5  jnz     short loc_18000FAFC
0x18000faf7  xor     r14d, r14d
0x18000fafa  jmp     short loc_18000FB06
0x18000fafc  mov     [rax], rbx
0x18000faff  lea     r14, [rax+10h]
0x18000fb03  mov     rbx, rax
0x18000fb06  test    r14, r14
0x18000fb09  jz      loc_18000FBD2
0x18000fb0f  xor     eax, eax
0x18000fb11  shr     rdi, 1
0x18000fb14  mov     [rsp+12C0h+cbData], edi; cchWideChar
0x18000fb18  lea     r8, [rbp+1290h+String1]; lpMultiByteStr
0x18000fb1f  mov     r9d, esi; cbMultiByte
0x18000fb22  mov     [r14], ax
0x18000fb26  xor     edx, edx; dwFlags
0x18000fb28  mov     [rsp+12C0h+lpData], r14; lpWideCharStr
0x18000fb2d  lea     ecx, [rax+3]; CodePage
0x18000fb30  call    cs:__imp_MultiByteToWideChar
0x18000fb36  test    eax, eax
0x18000fb38  jz      loc_18000FBD2
0x18000fb3e  lea     r9, [rbp+1290h+WideCharStr]; pulOut
0x18000fb42  xor     r8d, r8d; dwFlags
0x18000fb45  xor     edx, edx; lcid
0x18000fb47  mov     rcx, r14; strIn
0x18000fb4a  call    cs:__imp_VarUI4FromStr
0x18000fb50  mov     edi, eax
0x18000fb52  test    eax, eax
0x18000fb54  js      short loc_18000FB91
0x18000fb56  mov     eax, dword ptr [rbp+1290h+WideCharStr]
0x18000fb59  mov     ecx, 4
0x18000fb5e  mov     [rsp+12C0h+cbData], ecx; cbData
0x18000fb62  mov     r9d, ecx; dwType
0x18000fb65  mov     rcx, [r12]; hKey
0x18000fb69  xor     r8d, r8d; Reserved
0x18000fb6c  mov     dword ptr [rbp+1290h+Data], eax
0x18000fb6f  mov     rdx, r13; lpValueName
0x18000fb72  lea     rax, [rbp+1290h+Data]
0x18000fb76  mov     [rsp+12C0h+lpData], rax; lpData
0x18000fb7b  call    cs:__imp_RegSetValueExA
0x18000fb81  mov     edi, eax
0x18000fb83  jmp     short loc_18000FBA9
0x18000fb85  mov     rcx, rbx; Block
0x18000fb88  mov     rbx, [rbx]
0x18000fb8b  call    cs:__imp_free
0x18000fb91  test    rbx, rbx
0x18000fb94  jnz     short loc_18000FB85
0x18000fb96  mov     eax, edi
0x18000fb98  jmp     loc_18000FDDD
0x18000fb9d  mov     rcx, rbx; Block
0x18000fba0  mov     rbx, [rbx]
0x18000fba3  call    cs:__imp_free
0x18000fba9  test    rbx, rbx
0x18000fbac  jnz     short loc_18000FB9D
0x18000fbae  mov     r14, [rbp+1290h+var_1288]
0x18000fbb2  test    edi, edi
0x18000fbb4  jz      loc_18000FDC9
0x18000fbba  mov     ecx, edi; unsigned int
0x18000fbbc  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000fbc1  jmp     loc_18000FDDD
0x18000fbc6  mov     rcx, rbx; Block
0x18000fbc9  mov     rbx, [rbx]
0x18000fbcc  call    cs:__imp_free
0x18000fbd2  test    rbx, rbx
0x18000fbd5  jnz     short loc_18000FBC6
0x18000fbd7  mov     eax, 8007000Eh
0x18000fbdc  jmp     loc_18000FDDD
0x18000fbe1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000fbe5  lea     rax, [rbp+1290h+String1]
0x18000fbec  mov     rdi, rsi
0x18000fbef  inc     rdi
0x18000fbf2  cmp     byte ptr [rax+rdi], 0
0x18000fbf6  jnz     short loc_18000FBEF
0x18000fbf8  test    dil, 1
0x18000fbfc  jnz     short loc_18000FC58
0x18000fbfe  mov     eax, edi
0x18000fc00  mov     [rbp+1290h+var_1270], 0
0x18000fc08  cdq
0x18000fc09  sub     eax, edx
0x18000fc0b  sar     eax, 1
0x18000fc0d  movsxd  r14, eax
0x18000fc10  mov     rbx, r14
0x18000fc13  jz      short loc_18000FC42
0x18000fc15  xor     edx, edx
0x18000fc17  mov     rax, rsi
0x18000fc1a  div     rbx
0x18000fc1d  cmp     rax, 1
0x18000fc21  jb      loc_18000FE00
0x18000fc27  cmp     rbx, 100h
0x18000fc2e  jbe     short loc_18000FC42
0x18000fc30  mov     rdx, rbx
0x18000fc33  lea     rcx, [rbp+1290h+var_1270]
0x18000fc37  call    ?AllocateHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000fc3c  mov     rcx, [rbp+1290h+var_1270]
0x18000fc40  jmp     short loc_18000FC4A
0x18000fc42  lea     rcx, [rbp+1290h+var_1268]; void *
0x18000fc46  mov     [rbp+1290h+var_1270], rcx
0x18000fc4a  test    rcx, rcx
0x18000fc4d  jnz     short loc_18000FC62
0x18000fc4f  lea     rcx, [rbp+1290h+var_1270]
0x18000fc53  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000fc58  mov     eax, 80004005h
0x18000fc5d  jmp     loc_18000FDDD
0x18000fc62  mov     r8, rbx; Size
0x18000fc65  xor     edx, edx; Val
  ... truncated ...
```
