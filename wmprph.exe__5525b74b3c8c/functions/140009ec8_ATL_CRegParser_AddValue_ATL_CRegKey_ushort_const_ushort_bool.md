# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x140009ec8`
- end: `0x14000a4de`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1558`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, struct ATL::CRegKey *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000bbf0`

## callees

- `0x140001390`
- `0x140001d26`
- `0x140009ec8`
- `0x14000b134`
- `0x14000ca78`
- `0x14000e380`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000a03a`
- `ADVAPI32!RegSetValueExW` at `0x14000a304`
- `ADVAPI32!RegSetValueExW` at `0x14000a03a`
- `ADVAPI32!RegSetValueExW` at `0x14000a304`
- `KERNEL32!lstrcpynW` at `0x14000a405`
- `KERNEL32!lstrcpynW` at `0x14000a405`
- `KERNEL32!lstrcmpiW` at `0x140009f53`
- `KERNEL32!lstrcmpiW` at `0x14000a2b3`
- `KERNEL32!lstrcmpiW` at `0x140009f53`
- `KERNEL32!lstrcmpiW` at `0x14000a2b3`
- `USER32!CharPrevW` at `0x14000a3de`
- `USER32!CharPrevW` at `0x14000a3de`
- `USER32!CharNextW` at `0x140009fb2`
- `USER32!CharNextW` at `0x14000a35d`
- `USER32!CharNextW` at `0x14000a36a`
- `USER32!CharNextW` at `0x14000a38e`
- `USER32!CharNextW` at `0x140009fb2`
- `USER32!CharNextW` at `0x14000a35d`
- `USER32!CharNextW` at `0x14000a36a`
- `USER32!CharNextW` at `0x14000a38e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140009fd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a05d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a0fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a10b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a24d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a273`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a281`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a316`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a494`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a4a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a4b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140009fd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a05d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a0fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a10b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a24d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a273`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a281`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a316`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a494`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a4a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000a4b4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140009f0a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140009f86`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000a0da`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000a25f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140009f0a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140009f86`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000a0da`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000a25f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000a41e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000a42d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000a440`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000a460`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000a41e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000a42d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000a440`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000a460`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000a00d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000a00d`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5)
{
  const WCHAR *v6; // r15
  unsigned __int16 *v8; // rax
  WCHAR *v9; // r12
  int Token; // ebx
  int v12; // ebx
  __int16 v13; // si
  unsigned __int16 *v14; // rdi
  WCHAR *v15; // rbx
  HKEY v16; // rcx
  unsigned __int16 *v17; // rsi
  int v18; // esi
  WCHAR *v19; // rcx
  __int64 v20; // r14
  unsigned __int64 cbData; // r13
  __int64 v22; // rax
  void *v23; // rsp
  unsigned __int16 **lpData; // r15
  _QWORD *v25; // rax
  WCHAR *v26; // rcx
  unsigned int v27; // r9d
  unsigned int v28; // r8d
  char v29; // r8
  unsigned __int64 v30; // rdx
  char v31; // al
  __int64 v32; // rax
  const BYTE *v33; // rcx
  WCHAR *v34; // r13
  __int64 v35; // r14
  int v36; // esi
  const WCHAR *v37; // r12
  unsigned __int16 *v38; // r14
  const WCHAR *v39; // rsi
  const WCHAR *v40; // r15
  __int64 v41; // rax
  WCHAR *v42; // rcx
  unsigned __int16 *v43; // [rsp+30h] [rbp+0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp+8h] BYREF
  LPCWSTR v45; // [rsp+40h] [rbp+10h]
  ULONG pulOut; // [rsp+48h] [rbp+18h] BYREF
  HKEY *v47; // [rsp+50h] [rbp+20h]
  LPWSTR v48; // [rsp+58h] [rbp+28h]
  ATL::CRegParser *v49; // [rsp+60h] [rbp+30h]

  v49 = this;
  v43 = a4;
  v6 = a3;
  v45 = a3;
  v47 = a2;
  v8 = (unsigned __int16 *)malloc(0x2000u);
  *(_QWORD *)Data = v8;
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  Token = ATL::CRegParser::NextToken(this, v8);
  if ( Token < 0 )
    goto LABEL_75;
  v12 = 0;
  while ( lstrcmpiW(v9, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v12]) )
  {
    if ( (unsigned int)++v12 >= 3 )
    {
      Token = -2147352567;
      goto LABEL_75;
    }
  }
  v13 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v12 + 4);
  v14 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v14 )
    goto LABEL_74;
  while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
    *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  Token = ATL::CRegParser::NextToken(this, v14);
  if ( Token < 0 )
  {
    free(v14);
LABEL_75:
    free(v9);
    return (unsigned int)Token;
  }
  pulOut = 0;
  v15 = 0;
  if ( v13 == 8 )
  {
    v32 = -1;
    v33 = (const BYTE *)v14;
    v34 = 0;
    if ( a5 )
    {
      do
        ++v32;
      while ( v14[v32] );
      if ( (int)v32 > 4094 )
        goto LABEL_71;
      v34 = (WCHAR *)malloc(0x2000u);
      if ( !v34 )
      {
        free(v14);
LABEL_74:
        Token = -2147024882;
        goto LABEL_75;
      }
      v35 = *((_QWORD *)this + 1);
      v36 = 0;
      if ( *(int *)(v35 + 8) > 0 )
      {
        while ( lstrcmpiW(**(LPCWSTR **)(*(_QWORD *)v35 + 8LL * v36), L"Module") )
        {
          if ( ++v36 >= *(_DWORD *)(v35 + 8) )
            goto LABEL_79;
        }
        v37 = *(const WCHAR **)(*(_QWORD *)(*(_QWORD *)v35 + 8LL * v36) + 8LL);
        if ( v37 )
        {
          v38 = v14;
          if ( !*v37 )
          {
LABEL_99:
            v17 = v43;
            if ( v38 != v43 && *CharPrevW(v14, v38) == 34 )
            {
              v33 = (const BYTE *)v14;
            }
            else
            {
              *v34 = 0;
              lstrcpynW(v34, v14, v38 - v14);
              _o_wcscat_s(v34, 4096, L"\"");
              _o_wcscat_s(v34, 4096, v37);
              _o_wcscat_s(v34, 4096, L"\"");
              v41 = -1;
              do
                ++v41;
              while ( v37[v41] );
              _o_wcscat_s(v34, 4096, &v38[v41]);
              v33 = (const BYTE *)v34;
            }
            v9 = *(WCHAR **)Data;
            v32 = -1;
            v6 = v45;
            do
LABEL_81:
              ++v32;
            while ( *(_WORD *)&v33[2 * v32] );
            RegSetValueExW(*v47, v6, 0, 1u, v33, 2 * v32 + 2);
            if ( v34 )
              free(v34);
            goto LABEL_21;
          }
          if ( *v14 )
          {
LABEL_87:
            v39 = v38;
            v40 = v37;
            while ( *v40 )
            {
              if ( *v39 == *v40 )
              {
                v48 = CharNextW(v39);
                if ( (char *)v48 - (char *)v39 == (char *)CharNextW(v40) - (char *)v40 )
                {
                  do
                  {
                    if ( v39 >= v48 )
                      break;
                    ++v40;
                    ++v39;
                  }
                  while ( *v39 != *v40 );
                  if ( *v39 )
                    continue;
                }
              }
              if ( *v40 )
              {
                v38 = CharNextW(v38);
                if ( *v38 )
                  goto LABEL_87;
                goto LABEL_93;
              }
              break;
            }
            if ( !v38 )
              goto LABEL_93;
            goto LABEL_99;
          }
        }
LABEL_93:
        v9 = *(WCHAR **)Data;
LABEL_79:
        v6 = v45;
        v33 = (const BYTE *)v14;
        v32 = -1;
        goto LABEL_80;
      }
      v32 = -1;
      v33 = (const BYTE *)v14;
    }
LABEL_80:
    v17 = v43;
    goto LABEL_81;
  }
  if ( v13 != 17 )
  {
    if ( v13 == 19 )
    {
      VarUI4FromStr(v14, 0, 0, &pulOut);
      v16 = *a2;
      *(_DWORD *)Data = pulOut;
      RegSetValueExW(v16, v6, 0, 4u, Data, 4u);
    }
    goto LABEL_20;
  }
  v20 = -1;
  do
    ++v20;
  while ( v14[v20] );
  if ( (v20 & 1) != 0 )
  {
LABEL_71:
    free(v14);
    Token = -2147467259;
    goto LABEL_75;
  }
  cbData = (int)v20 / 2;
  if ( cbData <= 0x400
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(
         (ATL::_ATL_SAFE_ALLOCA_IMPL *)((int)v20 / 2),
         (unsigned int)((int)v20 >> 31)) )
  {
    v22 = cbData + 15;
    if ( cbData + 15 < cbData )
      v22 = 0xFFFFFFFFFFFFFF0LL;
    v23 = alloca(v22 & 0xFFFFFFFFFFFFFFF0uLL);
    lpData = &v43;
  }
  else if ( cbData + 16 >= cbData && (v25 = malloc(cbData + 16)) != 0 )
  {
    *v25 = 0;
    lpData = (unsigned __int16 **)(v25 + 2);
    v15 = (WCHAR *)v25;
  }
  else
  {
    lpData = 0;
  }
  if ( lpData )
  {
    memset_0(lpData, 0, cbData);
    v27 = 0;
    if ( (int)v20 <= 0 )
    {
LABEL_67:
      RegSetValueExW(*v47, v45, 0, 3u, (const BYTE *)lpData, cbData);
LABEL_20:
      v17 = v43;
LABEL_21:
      v18 = ATL::CRegParser::NextToken(v49, v17);
      if ( v18 >= 0 )
      {
        free(v14);
        v42 = v9;
        while ( 1 )
        {
          free(v42);
          if ( !v15 )
            break;
          v42 = v15;
          v15 = *(WCHAR **)v15;
        }
        return 0;
      }
      else
      {
        free(v14);
        v19 = v9;
        while ( 1 )
        {
          free(v19);
          if ( !v15 )
            break;
          v19 = v15;
          v15 = *(WCHAR **)v15;
        }
        return (unsigned int)v18;
      }
    }
    while ( 1 )
    {
      v28 = v14[v27];
      if ( v28 > 0x61 )
      {
        if ( v28 == 98 || v28 == 99 || v28 == 100 || v28 - 101 < 2 )
        {
LABEL_65:
          v29 = v28 - 87;
          goto LABEL_66;
        }
LABEL_64:
        v29 = 0;
        goto LABEL_66;
      }
      if ( v28 == 97 )
        goto LABEL_65;
      if ( v28 <= 0x38 )
        break;
      if ( v28 == 57 )
        goto LABEL_52;
      if ( v28 != 65 && v28 != 66 && v28 != 67 && v28 != 68 && v28 - 69 > 1 )
        goto LABEL_64;
      v29 = v28 - 55;
LABEL_66:
      v30 = (unsigned __int64)v27 >> 1;
      v31 = 4 * (v27++ & 1);
      *((_BYTE *)lpData + v30) |= v29 << (4 - v31);
      if ( (int)v27 >= (int)v20 )
        goto LABEL_67;
    }
    if ( v28 != 56 && v28 != 48 && v28 != 49 && v28 != 50 && v28 != 51 && v28 != 52 && v28 != 53 && v28 - 54 > 1 )
      goto LABEL_64;
LABEL_52:
    v29 = v28 - 48;
    goto LABEL_66;
  }
  free(v14);
  v26 = v9;
  while ( 1 )
  {
    free(v26);
    if ( !v15 )
      break;
    v26 = v15;
    v15 = *(WCHAR **)v15;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x140009ec8  push    rbp
0x140009eca  push    rbx
0x140009ecb  push    rsi
0x140009ecc  push    rdi
0x140009ecd  push    r12
0x140009ecf  push    r13
0x140009ed1  push    r14
0x140009ed3  push    r15
0x140009ed5  sub     rsp, 78h
0x140009ed9  lea     rbp, [rsp+30h]
0x140009ede  mov     rax, cs:__security_cookie
0x140009ee5  xor     rax, rbp
0x140009ee8  mov     [rbp+80h+var_48], rax
0x140009eec  mov     r14, rcx
0x140009eef  mov     [rbp+80h+var_50], rcx
0x140009ef3  mov     ecx, 2000h; Size
0x140009ef8  mov     [rbp+80h+var_80], r9
0x140009efc  mov     r15, r8
0x140009eff  mov     [rbp+80h+var_70], r8
0x140009f03  mov     r13, rdx
0x140009f06  mov     [rbp+80h+var_60], rdx
0x140009f0a  call    cs:__imp_malloc
0x140009f10  xor     esi, esi
0x140009f12  mov     qword ptr [rbp+80h+Data], rax
0x140009f16  mov     r12, rax
0x140009f19  test    rax, rax
0x140009f1c  jnz     short loc_140009F28
0x140009f1e  mov     eax, 8007000Eh
0x140009f23  jmp     loc_14000A4C1
0x140009f28  mov     rdx, r12; unsigned __int16 *
0x140009f2b  mov     rcx, r14; this
0x140009f2e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009f33  mov     ebx, eax
0x140009f35  test    eax, eax
0x140009f37  js      loc_14000A27E
0x140009f3d  mov     ebx, esi
0x140009f3f  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140009f46  movsxd  rdi, ebx
0x140009f49  mov     rcx, r12; lpString1
0x140009f4c  add     rdi, rdi
0x140009f4f  mov     rdx, [rax+rdi*8]; lpString2
0x140009f53  call    cs:__imp_lstrcmpiW
0x140009f59  test    eax, eax
0x140009f5b  jz      short loc_140009F75
0x140009f5d  inc     ebx
0x140009f5f  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140009f66  cmp     ebx, 3
0x140009f69  jb      short loc_140009F46
0x140009f6b  mov     ebx, 80020009h
0x140009f70  jmp     loc_14000A27E
0x140009f75  lea     rsi, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140009f7c  mov     ecx, 2000h; Size
0x140009f81  movzx   esi, word ptr [rsi+rdi*8+8]
0x140009f86  call    cs:__imp_malloc
0x140009f8c  mov     rdi, rax
0x140009f8f  test    rax, rax
0x140009f92  jz      loc_14000A279
0x140009f98  mov     rcx, [r14]; lpsz
0x140009f9b  movzx   edx, word ptr [rcx]
0x140009f9e  sub     edx, 9
0x140009fa1  jz      short loc_140009FB2
0x140009fa3  sub     edx, 1
0x140009fa6  jz      short loc_140009FB2
0x140009fa8  sub     edx, 3
0x140009fab  jz      short loc_140009FB2
0x140009fad  cmp     edx, 13h
0x140009fb0  jnz     short loc_140009FBD
0x140009fb2  call    cs:__imp_CharNextW
0x140009fb8  mov     [r14], rax
0x140009fbb  jmp     short loc_140009F98
0x140009fbd  mov     rdx, rdi; unsigned __int16 *
0x140009fc0  mov     rcx, r14; this
0x140009fc3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009fc8  xor     r8d, r8d; dwFlags
0x140009fcb  mov     ebx, eax
0x140009fcd  test    eax, eax
0x140009fcf  jns     short loc_140009FDF
0x140009fd1  mov     rcx, rdi; Block
0x140009fd4  call    cs:__imp_free
0x140009fda  jmp     loc_14000A27E
0x140009fdf  mov     eax, 8
0x140009fe4  mov     [rbp+80h+pulOut], r8d
0x140009fe8  mov     rbx, r8
0x140009feb  cmp     si, ax
0x140009fee  jz      loc_14000A222
0x140009ff4  cmp     si, 11h
0x140009ff8  jz      short loc_14000A06B
0x140009ffa  mov     eax, 13h
0x140009fff  cmp     si, ax
0x14000a002  jnz     short loc_14000A040
0x14000a004  lea     r9, [rbp+80h+pulOut]; pulOut
0x14000a008  xor     edx, edx; lcid
0x14000a00a  mov     rcx, rdi; strIn
0x14000a00d  call    cs:__imp_VarUI4FromStr
0x14000a013  mov     eax, [rbp+80h+pulOut]
0x14000a016  mov     r9d, 4; dwType
0x14000a01c  mov     rcx, [r13+0]; hKey
0x14000a020  mov     rdx, r15; lpValueName
0x14000a023  mov     dword ptr [rbp+80h+Data], eax
0x14000a026  lea     rax, [rbp+80h+Data]
0x14000a02a  mov     [rsp+0B0h+cbData], 4; cbData
0x14000a032  mov     [rsp+0B0h+lpData], rax; lpData
0x14000a037  xor     r8d, r8d; Reserved
0x14000a03a  call    cs:__imp_RegSetValueExW
0x14000a040  mov     rsi, [rbp+80h+var_80]
0x14000a044  mov     rcx, [rbp+80h+var_50]; this
0x14000a048  mov     rdx, rsi; unsigned __int16 *
0x14000a04b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000a050  mov     esi, eax
0x14000a052  mov     rcx, rdi; Block
0x14000a055  test    eax, eax
0x14000a057  jns     loc_14000A4A3
0x14000a05d  call    cs:__imp_free
0x14000a063  mov     rcx, r12
0x14000a066  jmp     loc_14000A494
0x14000a06b  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000a06f  inc     r14
0x14000a072  cmp     [rdi+r14*2], r8w
0x14000a077  jnz     short loc_14000A06F
0x14000a079  test    r14b, 1
0x14000a07d  jnz     loc_14000A24A
0x14000a083  mov     eax, r14d
0x14000a086  cdq; unsigned __int64
0x14000a087  sub     eax, edx
0x14000a089  sar     eax, 1
0x14000a08b  movsxd  r13, eax
0x14000a08e  cmp     r13, 400h
0x14000a095  ja      short loc_14000A0CC
0x14000a097  mov     rcx, r13; this
0x14000a09a  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x14000a09f  xor     r8d, r8d
0x14000a0a2  test    al, al
0x14000a0a4  jz      short loc_14000A0CC
0x14000a0a6  lea     rax, [r13+0Fh]
0x14000a0aa  cmp     rax, r13
0x14000a0ad  ja      short loc_14000A0B9
0x14000a0af  mov     rax, 0FFFFFFFFFFFFFF0h
0x14000a0b9  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000a0bd  call    _alloca_probe
0x14000a0c2  sub     rsp, rax
0x14000a0c5  lea     r15, [rsp+0B0h+var_80]
0x14000a0ca  jmp     short loc_14000A0F2
0x14000a0cc  lea     rcx, [r13+10h]; Size
0x14000a0d0  cmp     rcx, r13
0x14000a0d3  jnb     short loc_14000A0DA
0x14000a0d5  mov     r15, r8
0x14000a0d8  jmp     short loc_14000A0F2
0x14000a0da  call    cs:__imp_malloc
0x14000a0e0  xor     r8d, r8d
0x14000a0e3  test    rax, rax
0x14000a0e6  jz      short loc_14000A0D5
0x14000a0e8  mov     [rax], r8
0x14000a0eb  lea     r15, [rax+10h]
0x14000a0ef  mov     rbx, rax
0x14000a0f2  test    r15, r15
0x14000a0f5  jnz     short loc_14000A120
0x14000a0f7  mov     rcx, rdi; Block
0x14000a0fa  call    cs:__imp_free
0x14000a100  mov     rcx, r12
0x14000a103  jmp     short loc_14000A10B
0x14000a105  mov     rcx, rbx; Block
0x14000a108  mov     rbx, [rbx]
0x14000a10b  call    cs:__imp_free
0x14000a111  test    rbx, rbx
0x14000a114  jnz     short loc_14000A105
0x14000a116  mov     eax, 80004005h
0x14000a11b  jmp     loc_14000A4C1
0x14000a120  mov     r8, r13; Size
0x14000a123  xor     edx, edx; Val
0x14000a125  mov     rcx, r15; void *
0x14000a128  call    memset_0
0x14000a12d  xor     eax, eax
0x14000a12f  mov     r9d, eax
0x14000a132  test    r14d, r14d
0x14000a135  jle     loc_14000A202
0x14000a13b  mov     eax, r9d
0x14000a13e  movzx   r8d, word ptr [rdi+rax*2]
0x14000a143  cmp     r8d, 61h ; 'a'
0x14000a147  ja      short loc_14000A1B4
0x14000a149  jz      loc_14000A1D5
0x14000a14f  cmp     r8d, 38h ; '8'
0x14000a153  ja      short loc_14000A188
0x14000a155  jz      short loc_14000A182
0x14000a157  mov     ecx, r8d
0x14000a15a  sub     ecx, 30h ; '0'
0x14000a15d  jz      short loc_14000A182
0x14000a15f  sub     ecx, 1
0x14000a162  jz      short loc_14000A182
0x14000a164  sub     ecx, 1
0x14000a167  jz      short loc_14000A182
0x14000a169  sub     ecx, 1
0x14000a16c  jz      short loc_14000A182
0x14000a16e  sub     ecx, 1
0x14000a171  jz      short loc_14000A182
0x14000a173  sub     ecx, 1
0x14000a176  jz      short loc_14000A182
0x14000a178  sub     ecx, 1
0x14000a17b  jz      short loc_14000A182
0x14000a17d  cmp     ecx, 1
0x14000a180  jnz     short loc_14000A1D0
0x14000a182  sub     r8b, 30h ; '0'
0x14000a186  jmp     short loc_14000A1D9
0x14000a188  mov     ecx, r8d
0x14000a18b  sub     ecx, 39h ; '9'
0x14000a18e  jz      short loc_14000A182
0x14000a190  sub     ecx, 8
0x14000a193  jz      short loc_14000A1AE
0x14000a195  sub     ecx, 1
0x14000a198  jz      short loc_14000A1AE
0x14000a19a  sub     ecx, 1
0x14000a19d  jz      short loc_14000A1AE
0x14000a19f  sub     ecx, 1
0x14000a1a2  jz      short loc_14000A1AE
0x14000a1a4  sub     ecx, 1
0x14000a1a7  jz      short loc_14000A1AE
0x14000a1a9  cmp     ecx, 1
0x14000a1ac  jnz     short loc_14000A1D0
0x14000a1ae  sub     r8b, 37h ; '7'
0x14000a1b2  jmp     short loc_14000A1D9
0x14000a1b4  mov     ecx, r8d
0x14000a1b7  sub     ecx, 62h ; 'b'
0x14000a1ba  jz      short loc_14000A1D5
0x14000a1bc  sub     ecx, 1
0x14000a1bf  jz      short loc_14000A1D5
0x14000a1c1  sub     ecx, 1
0x14000a1c4  jz      short loc_14000A1D5
0x14000a1c6  sub     ecx, 1
0x14000a1c9  jz      short loc_14000A1D5
0x14000a1cb  cmp     ecx, 1
0x14000a1ce  jz      short loc_14000A1D5
0x14000a1d0  xor     r8b, r8b
0x14000a1d3  jmp     short loc_14000A1D9
0x14000a1d5  sub     r8b, 57h ; 'W'
0x14000a1d9  mov     eax, r9d
0x14000a1dc  mov     edx, r9d
0x14000a1df  and     eax, 1
0x14000a1e2  shr     rdx, 1
0x14000a1e5  shl     eax, 2
0x14000a1e8  mov     ecx, 4
0x14000a1ed  sub     ecx, eax
0x14000a1ef  inc     r9d
0x14000a1f2  shl     r8b, cl
0x14000a1f5  or      [rdx+r15], r8b
0x14000a1f9  cmp     r9d, r14d
0x14000a1fc  jl      loc_14000A13B
0x14000a202  mov     rcx, [rbp+80h+var_60]
0x14000a206  mov     r9d, 3
0x14000a20c  mov     rdx, [rbp+80h+var_70]
0x14000a210  mov     [rsp+0B0h+cbData], r13d
0x14000a215  mov     [rsp+0B0h+lpData], r15
0x14000a21a  mov     rcx, [rcx]
0x14000a21d  jmp     loc_14000A037
0x14000a222  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a226  mov     rcx, rdi
0x14000a229  mov     r13, r8
0x14000a22c  cmp     [rbp+80h+arg_20], r8b
0x14000a233  jz      loc_14000A2D3
0x14000a239  inc     rax
0x14000a23c  cmp     [rdi+rax*2], r8w
0x14000a241  jnz     short loc_14000A239
0x14000a243  cmp     eax, 0FFEh
0x14000a248  jle     short loc_14000A25A
0x14000a24a  mov     rcx, rdi; Block
0x14000a24d  call    cs:__imp_free
0x14000a253  mov     ebx, 80004005h
0x14000a258  jmp     short loc_14000A27E
0x14000a25a  mov     ecx, 2000h; Size
0x14000a25f  call    cs:__imp_malloc
0x14000a265  xor     r8d, r8d
0x14000a268  mov     r13, rax
0x14000a26b  test    rax, rax
0x14000a26e  jnz     short loc_14000A28E
0x14000a270  mov     rcx, rdi; Block
0x14000a273  call    cs:__imp_free
0x14000a279  mov     ebx, 8007000Eh
0x14000a27e  mov     rcx, r12; Block
0x14000a281  call    cs:__imp_free
0x14000a287  mov     eax, ebx
0x14000a289  jmp     loc_14000A4C1
0x14000a28e  mov     r14, [r14+8]
0x14000a292  mov     esi, r8d
0x14000a295  cmp     [r14+8], r8d
0x14000a299  jle     loc_14000A47D
0x14000a29f  mov     rax, [r14]
0x14000a2a2  lea     rdx, aModule; "Module"
0x14000a2a9  movsxd  r15, esi
0x14000a2ac  mov     rcx, [rax+r15*8]
0x14000a2b0  mov     rcx, [rcx]; lpString1
0x14000a2b3  call    cs:__imp_lstrcmpiW
0x14000a2b9  xor     r8d, r8d
0x14000a2bc  test    eax, eax
0x14000a2be  jz      short loc_14000A321
0x14000a2c0  inc     esi
0x14000a2c2  cmp     esi, [r14+8]
0x14000a2c6  jl      short loc_14000A29F
0x14000a2c8  mov     r15, [rbp+80h+var_70]
0x14000a2cc  mov     rcx, rdi
0x14000a2cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000a2d3  mov     rsi, [rbp+80h+var_80]
0x14000a2d7  inc     rax
  ... truncated ...
```
