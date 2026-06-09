# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180003b40`
- end: `0x18000406d`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1325`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000b6fc`

## callees

- `0x180003b40`
- `0x180004074`
- `0x1800041e0`
- `0x1800041f8`
- `0x180004bdc`
- `0x18000a924`
- `0x180012d6e`
- `0x180012db0`
- `0x180012e40`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180003bb9`
- `KERNEL32!lstrcmpiW` at `0x180003bb9`
- `ADVAPI32!RegSetValueExW` at `0x180003d7e`
- `ADVAPI32!RegSetValueExW` at `0x180003e03`
- `ADVAPI32!RegSetValueExW` at `0x180003fab`
- `ADVAPI32!RegSetValueExW` at `0x180003d7e`
- `ADVAPI32!RegSetValueExW` at `0x180003e03`
- `ADVAPI32!RegSetValueExW` at `0x180003fab`
- `USER32!CharNextW` at `0x180003c0f`
- `USER32!CharNextW` at `0x180003ce5`
- `USER32!CharNextW` at `0x180003d07`
- `USER32!CharNextW` at `0x180003c0f`
- `USER32!CharNextW` at `0x180003ce5`
- `USER32!CharNextW` at `0x180003d07`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003dc7`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180003dc7`

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
0x180003b40  push    rbp
0x180003b42  push    rbx
0x180003b43  push    rsi
0x180003b44  push    rdi
0x180003b45  push    r12
0x180003b47  push    r13
0x180003b49  push    r14
0x180003b4b  push    r15
0x180003b4d  lea     rbp, [rsp-2178h]
0x180003b55  mov     eax, 2278h
0x180003b5a  call    _alloca_probe
0x180003b5f  sub     rsp, rax
0x180003b62  mov     rax, cs:__security_cookie
0x180003b69  xor     rax, rsp
0x180003b6c  mov     [rbp+21B0h+var_50], rax
0x180003b73  mov     r13, rdx
0x180003b76  mov     qword ptr [rsp+22B0h+Data], r9
0x180003b7b  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180003b82  mov     qword ptr [rsp+22B0h+pulOut], r8
0x180003b87  mov     r15, r9
0x180003b8a  mov     r14, r8
0x180003b8d  mov     r12, rcx
0x180003b90  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003b95  xor     esi, esi
0x180003b97  test    eax, eax
0x180003b99  js      loc_180004028
0x180003b9f  mov     ebx, esi
0x180003ba1  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003ba8  movsxd  rdi, ebx
0x180003bab  lea     rcx, [rbp+21B0h+String1]; lpString1
0x180003bb2  add     rdi, rdi
0x180003bb5  mov     rdx, [rax+rdi*8]; lpString2
0x180003bb9  call    cs:__imp_lstrcmpiW
0x180003bc0  nop     dword ptr [rax+rax+00h]
0x180003bc5  test    eax, eax
0x180003bc7  jz      short loc_180003BE1
0x180003bc9  inc     ebx
0x180003bcb  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003bd2  cmp     ebx, 4
0x180003bd5  jb      short loc_180003BA8
0x180003bd7  mov     eax, 80020009h
0x180003bdc  jmp     loc_180004028
0x180003be1  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003be8  movzx   ebx, word ptr [rbx+rdi*8+8]
0x180003bed  mov     edi, 13h
0x180003bf2  mov     rdx, [r12]
0x180003bf6  movzx   ecx, word ptr [rdx]
0x180003bf9  sub     ecx, 9
0x180003bfc  jz      short loc_180003C0C
0x180003bfe  sub     ecx, 1
0x180003c01  jz      short loc_180003C0C
0x180003c03  sub     ecx, 3
0x180003c06  jz      short loc_180003C0C
0x180003c08  cmp     ecx, edi
0x180003c0a  jnz     short loc_180003C21
0x180003c0c  mov     rcx, rdx; lpsz
0x180003c0f  call    cs:__imp_CharNextW
0x180003c16  nop     dword ptr [rax+rax+00h]
0x180003c1b  mov     [r12], rax
0x180003c1f  jmp     short loc_180003BF2
0x180003c21  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180003c28  mov     rcx, r12; this
0x180003c2b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003c30  test    eax, eax
0x180003c32  js      loc_180004028
0x180003c38  mov     eax, 8
0x180003c3d  cmp     bx, ax
0x180003c40  jz      loc_180003FE3
0x180003c46  cmp     bx, 11h
0x180003c4a  jz      loc_180003E16
0x180003c50  cmp     bx, di
0x180003c53  jz      loc_180003DB2
0x180003c59  mov     eax, 4008h
0x180003c5e  cmp     bx, ax
0x180003c61  jnz     loc_180004014
0x180003c67  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003c6b  mov     [rbp+21B0h+var_2160], rsi
0x180003c6f  mov     rax, rdi
0x180003c72  lea     rcx, [rbp+21B0h+String1]
0x180003c79  inc     rax
0x180003c7c  cmp     [rcx+rax*2], si
0x180003c80  jnz     short loc_180003C79
0x180003c82  add     eax, 2
0x180003c85  movsxd  rcx, eax
0x180003c88  jz      short loc_180003CB8
0x180003c8a  xor     edx, edx
0x180003c8c  mov     rax, rdi
0x180003c8f  div     rcx
0x180003c92  cmp     rax, 2
0x180003c96  jb      loc_180004057
0x180003c9c  lea     rdx, [rcx+rcx]
0x180003ca0  cmp     rdx, 100h
0x180003ca7  jbe     short loc_180003CB8
0x180003ca9  lea     rcx, [rbp+21B0h+var_2160]
0x180003cad  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003cb2  mov     rbx, [rbp+21B0h+var_2160]
0x180003cb6  jmp     short loc_180003CC0
0x180003cb8  lea     rbx, [rbp+21B0h+var_2158]
0x180003cbc  mov     [rbp+21B0h+var_2160], rbx
0x180003cc0  test    rbx, rbx
0x180003cc3  jz      loc_180003D92
0x180003cc9  xor     eax, eax
0x180003ccb  lea     rsi, [rbp+21B0h+String1]
0x180003cd2  cmp     [rbp+21B0h+String1], ax
0x180003cd9  jz      short loc_180003D33
0x180003cdb  lea     r14d, [rax+30h]
0x180003cdf  xor     r15d, r15d
0x180003ce2  mov     rcx, rsi; lpsz
0x180003ce5  call    cs:__imp_CharNextW
0x180003cec  nop     dword ptr [rax+rax+00h]
0x180003cf1  movzx   ecx, word ptr [rsi]
0x180003cf4  cmp     cx, 5Ch ; '\'
0x180003cf8  jnz     short loc_180003D18
0x180003cfa  cmp     [rax], r14w
0x180003cfe  jnz     short loc_180003D18
0x180003d00  mov     rcx, rax; lpsz
0x180003d03  mov     [rbx], r15w
0x180003d07  call    cs:__imp_CharNextW
0x180003d0e  nop     dword ptr [rax+rax+00h]
0x180003d13  mov     rsi, rax
0x180003d16  jmp     short loc_180003D1F
0x180003d18  mov     [rbx], cx
0x180003d1b  add     rsi, 2
0x180003d1f  add     rbx, 2
0x180003d23  cmp     [rsi], r15w
0x180003d27  jnz     short loc_180003CE2
0x180003d29  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180003d2e  mov     r15, qword ptr [rsp+22B0h+Data]
0x180003d33  xor     esi, esi
0x180003d35  mov     [rbx], esi
0x180003d37  mov     r8, [rbp+21B0h+var_2160]
0x180003d3b  test    r8, r8
0x180003d3e  jz      loc_180004062
0x180003d44  mov     r10d, esi
0x180003d47  mov     r9, r8
0x180003d4a  mov     rcx, rdi
0x180003d4d  inc     rcx
0x180003d50  cmp     [r9+rcx*2], si
0x180003d55  jnz     short loc_180003D4D
0x180003d57  inc     ecx
0x180003d59  lea     r9, [r9+rcx*2]
0x180003d5d  lea     r10d, [r10+rcx*2]
0x180003d61  cmp     ecx, 1
0x180003d64  jnz     short loc_180003D4A
0x180003d66  mov     [rsp+22B0h+cbData], r10d; cbData
0x180003d6b  lea     r9d, [rcx+6]; dwType
0x180003d6f  mov     rcx, [r13+0]; hKey
0x180003d73  mov     rdx, r14; lpValueName
0x180003d76  mov     [rsp+22B0h+lpData], r8; lpData
0x180003d7b  xor     r8d, r8d; Reserved
0x180003d7e  call    cs:__imp_RegSetValueExW
0x180003d85  nop     dword ptr [rax+rax+00h]
0x180003d8a  mov     rbx, [rbp+21B0h+var_2160]
0x180003d8e  mov     edi, eax
0x180003d90  jmp     short loc_180003D97
0x180003d92  mov     edi, 0Eh
0x180003d97  lea     rax, [rbp+21B0h+var_2158]
0x180003d9b  cmp     rbx, rax
0x180003d9e  jz      loc_180003FD6
0x180003da4  lea     rcx, [rbp+21B0h+var_2160]
0x180003da8  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003dad  jmp     loc_180003FD6
0x180003db2  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x180003db7  mov     [rsp+22B0h+pulOut], esi
0x180003dbb  xor     r8d, r8d; dwFlags
0x180003dbe  lea     rcx, [rbp+21B0h+String1]; strIn
0x180003dc5  xor     edx, edx; lcid
0x180003dc7  call    cs:__imp_VarUI4FromStr
0x180003dce  nop     dword ptr [rax+rax+00h]
0x180003dd3  test    eax, eax
0x180003dd5  js      loc_180004028
0x180003ddb  mov     eax, [rsp+22B0h+pulOut]
0x180003ddf  mov     ecx, 4
0x180003de4  mov     dword ptr [rsp+22B0h+Data], eax
0x180003de8  mov     r9d, ecx; dwType
0x180003deb  mov     [rsp+22B0h+cbData], ecx; cbData
0x180003def  lea     rax, [rsp+22B0h+Data]
0x180003df4  mov     rcx, [r13+0]; hKey
0x180003df8  xor     r8d, r8d; Reserved
0x180003dfb  mov     rdx, r14; lpValueName
0x180003dfe  mov     [rsp+22B0h+lpData], rax; lpData
0x180003e03  call    cs:__imp_RegSetValueExW
0x180003e0a  nop     dword ptr [rax+rax+00h]
0x180003e0f  mov     edi, eax
0x180003e11  jmp     loc_180003FD6
0x180003e16  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003e1a  lea     rax, [rbp+21B0h+String1]
0x180003e21  mov     rsi, rdi
0x180003e24  xor     ecx, ecx
0x180003e26  inc     rsi
0x180003e29  cmp     [rax+rsi*2], cx
0x180003e2d  jnz     short loc_180003E26
0x180003e2f  test    sil, 1
0x180003e33  jnz     short loc_180003E93
0x180003e35  mov     eax, esi
0x180003e37  mov     [rsp+22B0h+var_2270], rcx
0x180003e3c  cdq
0x180003e3d  sub     eax, edx
0x180003e3f  sar     eax, 1
0x180003e41  movsxd  r15, eax
0x180003e44  mov     rbx, r15
0x180003e47  jz      short loc_180003E78
0x180003e49  xor     edx, edx
0x180003e4b  mov     rax, rdi
0x180003e4e  div     rbx
0x180003e51  cmp     rax, 1
0x180003e55  jb      loc_18000404C
0x180003e5b  cmp     rbx, 100h
0x180003e62  jbe     short loc_180003E78
0x180003e64  mov     rdx, rbx
0x180003e67  lea     rcx, [rsp+22B0h+var_2270]
0x180003e6c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003e71  mov     rcx, [rsp+22B0h+var_2270]
0x180003e76  jmp     short loc_180003E82
0x180003e78  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180003e7d  mov     [rsp+22B0h+var_2270], rcx
0x180003e82  xor     edi, edi
0x180003e84  test    rcx, rcx
0x180003e87  jnz     short loc_180003E9D
0x180003e89  lea     rcx, [rsp+22B0h+var_2270]
0x180003e8e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003e93  mov     eax, 80004005h
0x180003e98  jmp     loc_180004028
0x180003e9d  mov     r8, rbx; Size
0x180003ea0  xor     edx, edx; Val
0x180003ea2  call    memset_0
0x180003ea7  mov     r10d, edi
0x180003eaa  test    esi, esi
0x180003eac  jle     loc_180003F8C
0x180003eb2  mov     r14d, 30h ; '0'
0x180003eb8  mov     eax, r10d
0x180003ebb  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x180003ec4  cmp     r9d, 61h ; 'a'
0x180003ec8  ja      short loc_180003F34
0x180003eca  jz      loc_180003F55
0x180003ed0  cmp     r9d, 38h ; '8'
0x180003ed4  ja      short loc_180003F08
0x180003ed6  jz      short loc_180003F03
0x180003ed8  mov     ecx, r9d
0x180003edb  sub     ecx, r14d
0x180003ede  jz      short loc_180003F03
0x180003ee0  sub     ecx, 1
0x180003ee3  jz      short loc_180003F03
0x180003ee5  sub     ecx, 1
0x180003ee8  jz      short loc_180003F03
0x180003eea  sub     ecx, 1
0x180003eed  jz      short loc_180003F03
0x180003eef  sub     ecx, 1
0x180003ef2  jz      short loc_180003F03
0x180003ef4  sub     ecx, 1
0x180003ef7  jz      short loc_180003F03
0x180003ef9  sub     ecx, 1
0x180003efc  jz      short loc_180003F03
0x180003efe  cmp     ecx, 1
0x180003f01  jnz     short loc_180003F50
0x180003f03  sub     r9b, r14b
0x180003f06  jmp     short loc_180003F59
0x180003f08  mov     ecx, r9d
0x180003f0b  sub     ecx, 39h ; '9'
0x180003f0e  jz      short loc_180003F03
0x180003f10  sub     ecx, 8
0x180003f13  jz      short loc_180003F2E
0x180003f15  sub     ecx, 1
0x180003f18  jz      short loc_180003F2E
0x180003f1a  sub     ecx, 1
0x180003f1d  jz      short loc_180003F2E
0x180003f1f  sub     ecx, 1
0x180003f22  jz      short loc_180003F2E
0x180003f24  sub     ecx, 1
0x180003f27  jz      short loc_180003F2E
0x180003f29  cmp     ecx, 1
0x180003f2c  jnz     short loc_180003F50
0x180003f2e  sub     r9b, 37h ; '7'
0x180003f32  jmp     short loc_180003F59
0x180003f34  mov     ecx, r9d
0x180003f37  sub     ecx, 62h ; 'b'
0x180003f3a  jz      short loc_180003F55
0x180003f3c  sub     ecx, 1
0x180003f3f  jz      short loc_180003F55
0x180003f41  sub     ecx, 1
0x180003f44  jz      short loc_180003F55
0x180003f46  sub     ecx, 1
0x180003f49  jz      short loc_180003F55
0x180003f4b  cmp     ecx, 1
0x180003f4e  jz      short loc_180003F55
0x180003f50  mov     r9b, dil
0x180003f53  jmp     short loc_180003F59
0x180003f55  sub     r9b, 57h ; 'W'
0x180003f59  mov     rdx, [rsp+22B0h+var_2270]
0x180003f5e  mov     eax, r10d
0x180003f61  and     eax, 1
0x180003f64  mov     r8d, r10d
0x180003f67  shl     eax, 2
0x180003f6a  mov     ecx, 4
0x180003f6f  shr     r8, 1
0x180003f72  sub     ecx, eax
0x180003f74  shl     r9b, cl
0x180003f77  inc     r10d
0x180003f7a  or      [r8+rdx], r9b
0x180003f7e  cmp     r10d, esi
  ... truncated ...
```
