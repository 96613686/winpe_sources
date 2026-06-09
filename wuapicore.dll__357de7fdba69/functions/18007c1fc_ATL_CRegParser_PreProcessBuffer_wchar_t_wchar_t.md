# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x18007c1fc`
- end: `0x18007c603`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `1031`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007da88`

## callees

- `0x180004d50`
- `0x18007c128`
- `0x18007c1fc`
- `0x18009b00c`
- `0x18009b050`
- `0x18009d258`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c4f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c4f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c4ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c4ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c28b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007c28b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c5a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007c5a1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c2f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c305`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c311`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c31d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c36c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c382`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c3ff`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c44b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c555`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c56e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c2f9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c305`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c311`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c31d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c36c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c382`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c3ff`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c44b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c555`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18007c56e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c4d7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007c4d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, wchar_t *a2, wchar_t **a3)
{
  const wchar_t *v3; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  bool v10; // al
  int v11; // r13d
  char v12; // r12
  char v13; // r15
  wchar_t *v14; // rax
  const WCHAR *v15; // rax
  const WCHAR *v16; // rax
  const WCHAR *v17; // rax
  const wchar_t *v18; // rax
  const wchar_t *v19; // rdx
  LPWSTR v20; // rax
  WCHAR v21; // cx
  const WCHAR *v22; // r15
  __int64 v23; // rax
  int v24; // eax
  LPCWSTR v25; // rdi
  int v26; // r12d
  __int64 v27; // r14
  const wchar_t *v28; // r14
  __int64 v29; // r8
  const WCHAR *i; // rax
  wchar_t *v31; // rcx
  char v33; // [rsp+20h] [rbp-59h]
  char v34; // [rsp+21h] [rbp-58h]
  bool v35; // [rsp+22h] [rbp-57h]
  LPVOID pv[2]; // [rsp+28h] [rbp-51h] BYREF
  __int64 v37; // [rsp+38h] [rbp-41h]
  wchar_t **v38; // [rsp+40h] [rbp-39h]
  WCHAR String2[32]; // [rsp+50h] [rbp-29h] BYREF

  v38 = a3;
  v3 = a2;
  v5 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  *(_OWORD *)pv = 0;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(pv[0]) = 0;
  HIDWORD(pv[0]) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv[1] = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv[1] = 0;
  }
  if ( !v9 )
  {
LABEL_12:
    v5 = -2147024882;
    goto LABEL_74;
  }
  *this = v3;
  v10 = ATL::_AtlRegisterPerUser;
  v35 = ATL::_AtlRegisterPerUser;
  v11 = 0;
  v12 = 0;
  v34 = 0;
  v13 = 0;
  v33 = 0;
  if ( *v3 )
  {
    while ( 1 )
    {
      if ( !v10 )
        goto LABEL_35;
      if ( !v11 )
      {
        v14 = wcsstr(v3, L"HKCR");
        if ( v14 )
        {
          if ( v14 == *this )
          {
            v15 = CharNextW(*this);
            *this = v15;
            v16 = CharNextW(v15);
            *this = v16;
            v17 = CharNextW(v16);
            *this = v17;
            *this = CharNextW(v17);
            v37 = 0;
            if ( !ATL::CRegParser::CParseBuffer::Append(
                    (ATL::CRegParser::CParseBuffer *)pv,
                    L"HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClasses",
                    31) )
              goto LABEL_12;
            v12 = 1;
            v34 = 1;
          }
        }
      }
      if ( **this == 39 )
      {
        if ( !v13 )
        {
          v13 = 1;
          v33 = 1;
          goto LABEL_35;
        }
        if ( *CharNextW(*this) == 39 )
        {
          v18 = CharNextW(*this);
          *this = v18;
          if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v18, 1) )
            goto LABEL_12;
          goto LABEL_35;
        }
        v13 = 0;
        v33 = 0;
      }
      else if ( v13 )
      {
        goto LABEL_35;
      }
      if ( **this == 123 )
      {
        ++v11;
      }
      else if ( **this == 125 && !--v11 && v12 == 1 )
      {
        v37 = 0;
        if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, L"\r\n\t}\r\n}\r\n", 9) )
          goto LABEL_12;
        v12 = 0;
        v34 = 0;
      }
LABEL_35:
      v19 = *this;
      if ( **this != 37 )
        goto LABEL_38;
      v20 = CharNextW(*this);
      *this = v20;
      v21 = *v20;
      if ( *v20 == 37 )
      {
        v19 = v20;
LABEL_38:
        if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v19, 1) )
          goto LABEL_12;
        goto LABEL_70;
      }
      v22 = 0;
      if ( !v20 )
        goto LABEL_41;
      while ( v21 )
      {
        if ( v21 == 37 )
        {
          v22 = v20;
          break;
        }
        v20 = CharNextW(v20);
        v21 = *v20;
      }
      if ( !v22 )
      {
LABEL_41:
        v5 = -2147352567;
        goto LABEL_74;
      }
      v23 = v22 - *this;
      if ( v23 > 31 )
      {
        v5 = -2147467259;
        goto LABEL_74;
      }
      v24 = o_wcsncpy_s_0(String2, 32, *this, (int)v23);
      if ( v24 )
      {
        if ( v24 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v24 == 22 || v24 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v24 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      v25 = this[1];
      EnterCriticalSection((LPCRITICAL_SECTION)(v25 + 16));
      v26 = 0;
      v27 = 0;
      if ( *((int *)v25 + 6) <= 0 )
        goto LABEL_57;
      while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v25 + 1) + 8 * v27), String2) )
      {
        ++v26;
        ++v27;
        if ( v26 >= *((_DWORD *)v25 + 6) )
          goto LABEL_57;
      }
      if ( v27 == -1 )
      {
LABEL_57:
        v28 = 0;
      }
      else
      {
        if ( v27 < 0 || v26 >= *((_DWORD *)v25 + 6) )
          ATL::AtlThrowImpl(-2147483637);
        v28 = *(const wchar_t **)(*((_QWORD *)v25 + 2) + 8 * v27);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v25 + 16));
      if ( !v28 )
        goto LABEL_41;
      v37 = 0;
      v29 = -1;
      do
        ++v29;
      while ( v28[v29] );
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v28, v29) )
        goto LABEL_12;
      for ( i = *this; i != v22; *this = i )
        i = CharNextW(i);
      v12 = v34;
      v13 = v33;
LABEL_70:
      v3 = CharNextW(*this);
      *this = v3;
      if ( !*v3 )
        break;
      v10 = v35;
    }
  }
  v31 = (wchar_t *)pv[1];
  pv[1] = 0;
  *v38 = v31;
LABEL_74:
  CoTaskMemFree(pv[1]);
  return v5;
}

```

## disassembly

```asm
0x18007c1fc  mov     [rsp-8+arg_8], rbx
0x18007c201  push    rbp
0x18007c202  push    rsi
0x18007c203  push    rdi
0x18007c204  push    r12
0x18007c206  push    r13
0x18007c208  push    r14
0x18007c20a  push    r15
0x18007c20c  lea     rbp, [rsp-27h]
0x18007c211  sub     rsp, 0A0h
0x18007c218  mov     rax, cs:__security_cookie
0x18007c21f  xor     rax, rsp
0x18007c222  mov     [rbp+57h+var_40], rax
0x18007c226  mov     rax, r8
0x18007c229  mov     [rbp+57h+var_90], rax
0x18007c22d  mov     rdi, rdx
0x18007c230  mov     rsi, rcx
0x18007c233  xor     ebx, ebx
0x18007c235  test    rdx, rdx
0x18007c238  jz      loc_18007C5AB
0x18007c23e  test    rax, rax
0x18007c241  jz      loc_18007C5AB
0x18007c247  mov     [r8], rbx
0x18007c24a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007c24e  inc     rax
0x18007c251  cmp     [rdx+rax*2], bx
0x18007c255  jnz     short loc_18007C24E
0x18007c257  add     eax, eax
0x18007c259  xorps   xmm0, xmm0
0x18007c25c  movups  xmmword ptr [rbp+57h+pv], xmm0
0x18007c260  mov     ecx, 3E8h
0x18007c265  cmp     eax, 64h ; 'd'
0x18007c268  cmovl   eax, ecx
0x18007c26b  mov     dword ptr [rbp+57h+pv], ebx
0x18007c26e  mov     dword ptr [rbp+57h+pv+4], eax
0x18007c271  mov     ecx, eax
0x18007c273  add     rcx, rcx
0x18007c276  mov     eax, 0FFFFFFFFh
0x18007c27b  cmp     rcx, rax
0x18007c27e  jbe     short loc_18007C289
0x18007c280  mov     rax, rbx
0x18007c283  mov     [rbp+57h+pv+8], rbx
0x18007c287  jmp     short loc_18007C29D
0x18007c289  mov     ecx, ecx; cb
0x18007c28b  call    cs:__imp_CoTaskMemAlloc
0x18007c291  mov     [rbp+57h+pv+8], rax
0x18007c295  test    rax, rax
0x18007c298  jz      short loc_18007C29D
0x18007c29a  mov     [rax], bx
0x18007c29d  test    rax, rax
0x18007c2a0  jnz     short loc_18007C2AC
0x18007c2a2  mov     ebx, 8007000Eh
0x18007c2a7  jmp     loc_18007C59D
0x18007c2ac  mov     [rsi], rdi
0x18007c2af  mov     al, cs:?_AtlRegisterPerUser@ATL@@3_NA; bool ATL::_AtlRegisterPerUser
0x18007c2b5  mov     [rbp+57h+var_AE], al
0x18007c2b8  mov     r13d, ebx
0x18007c2bb  mov     r12b, bl
0x18007c2be  mov     [rbp+57h+var_AF], bl
0x18007c2c1  mov     r15b, bl
0x18007c2c4  mov     [rbp+57h+var_B0], bl
0x18007c2c7  cmp     [rdi], bx
0x18007c2ca  jz      loc_18007C58E
0x18007c2d0  cmp     al, 1
0x18007c2d2  jnz     loc_18007C3F3
0x18007c2d8  test    r13d, r13d
0x18007c2db  jnz     short loc_18007C34E
0x18007c2dd  lea     rdx, aHkcr; "HKCR"
0x18007c2e4  mov     rcx, rdi; Str
0x18007c2e7  call    wcsstr
0x18007c2ec  test    rax, rax
0x18007c2ef  jz      short loc_18007C34E
0x18007c2f1  cmp     rax, [rsi]
0x18007c2f4  jnz     short loc_18007C34E
0x18007c2f6  mov     rcx, [rsi]; lpsz
0x18007c2f9  call    cs:__imp_CharNextW
0x18007c2ff  mov     [rsi], rax
0x18007c302  mov     rcx, rax; lpsz
0x18007c305  call    cs:__imp_CharNextW
0x18007c30b  mov     [rsi], rax
0x18007c30e  mov     rcx, rax; lpsz
0x18007c311  call    cs:__imp_CharNextW
0x18007c317  mov     [rsi], rax
0x18007c31a  mov     rcx, rax; lpsz
0x18007c31d  call    cs:__imp_CharNextW
0x18007c323  mov     [rsi], rax
0x18007c326  mov     [rbp+57h+var_98], rbx
0x18007c32a  lea     r8d, [r13+1Fh]; int
0x18007c32e  lea     rdx, aHkcuSoftwareCl; "HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClass"...
0x18007c335  lea     rcx, [rbp+57h+pv]; this
0x18007c339  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18007c33e  nop
0x18007c33f  test    eax, eax
0x18007c341  jz      loc_18007C2A2
0x18007c347  mov     r12b, 1
0x18007c34a  mov     [rbp+57h+var_AF], r12b
0x18007c34e  mov     rcx, [rsi]; lpsz
0x18007c351  mov     edi, 27h ; '''
0x18007c356  cmp     di, [rcx]
0x18007c359  jnz     short loc_18007C3A7
0x18007c35b  test    r15b, r15b
0x18007c35e  jnz     short loc_18007C36C
0x18007c360  mov     r15b, 1
0x18007c363  mov     [rbp+57h+var_B0], r15b
0x18007c367  jmp     loc_18007C3F3
0x18007c36c  call    cs:__imp_CharNextW
0x18007c372  cmp     di, [rax]
0x18007c375  jz      short loc_18007C37F
0x18007c377  mov     r15b, bl
0x18007c37a  mov     [rbp+57h+var_B0], bl
0x18007c37d  jmp     short loc_18007C3AC
0x18007c37f  mov     rcx, [rsi]; lpsz
0x18007c382  call    cs:__imp_CharNextW
0x18007c388  mov     [rsi], rax
0x18007c38b  mov     r8d, 1; int
0x18007c391  mov     rdx, rax; wchar_t *
0x18007c394  lea     rcx, [rbp+57h+pv]; this
0x18007c398  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18007c39d  test    eax, eax
0x18007c39f  jz      loc_18007C2A2
0x18007c3a5  jmp     short loc_18007C3F3
0x18007c3a7  test    r15b, r15b
0x18007c3aa  jnz     short loc_18007C3F3
0x18007c3ac  mov     rax, [rsi]
0x18007c3af  cmp     word ptr [rax], 7Bh ; '{'
0x18007c3b3  jnz     short loc_18007C3BA
0x18007c3b5  inc     r13d
0x18007c3b8  jmp     short loc_18007C3F3
0x18007c3ba  cmp     word ptr [rax], 7Dh ; '}'
0x18007c3be  jnz     short loc_18007C3F3
0x18007c3c0  sub     r13d, 1
0x18007c3c4  jnz     short loc_18007C3F3
0x18007c3c6  cmp     r12b, 1
0x18007c3ca  jnz     short loc_18007C3F3
0x18007c3cc  mov     [rbp+57h+var_98], rbx
0x18007c3d0  lea     r8d, [r13+9]; int
0x18007c3d4  lea     rdx, asc_1800BB3D0; "\r\n\t}\r\n}\r\n"
0x18007c3db  lea     rcx, [rbp+57h+pv]; this
0x18007c3df  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18007c3e4  nop
0x18007c3e5  test    eax, eax
0x18007c3e7  jz      loc_18007C2A2
0x18007c3ed  mov     r12b, bl
0x18007c3f0  mov     [rbp+57h+var_AF], bl
0x18007c3f3  mov     rdx, [rsi]
0x18007c3f6  cmp     word ptr [rdx], 25h ; '%'
0x18007c3fa  jnz     short loc_18007C414
0x18007c3fc  mov     rcx, rdx; lpsz
0x18007c3ff  call    cs:__imp_CharNextW
0x18007c405  mov     [rsi], rax
0x18007c408  movzx   ecx, word ptr [rax]
0x18007c40b  cmp     cx, 25h ; '%'
0x18007c40f  jnz     short loc_18007C430
0x18007c411  mov     rdx, rax; wchar_t *
0x18007c414  mov     r8d, 1; int
0x18007c41a  lea     rcx, [rbp+57h+pv]; this
0x18007c41e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18007c423  test    eax, eax
0x18007c425  jz      loc_18007C2A2
0x18007c42b  jmp     loc_18007C56B
0x18007c430  mov     r15, rbx
0x18007c433  test    rax, rax
0x18007c436  jnz     short loc_18007C454
0x18007c438  mov     ebx, 80020009h
0x18007c43d  jmp     loc_18007C59D
0x18007c442  cmp     cx, 25h ; '%'
0x18007c446  jz      short loc_18007C45B
0x18007c448  mov     rcx, rax; lpsz
0x18007c44b  call    cs:__imp_CharNextW
0x18007c451  movzx   ecx, word ptr [rax]
0x18007c454  test    cx, cx
0x18007c457  jnz     short loc_18007C442
0x18007c459  jmp     short loc_18007C45E
0x18007c45b  mov     r15, rax
0x18007c45e  test    r15, r15
0x18007c461  jz      short loc_18007C438
0x18007c463  mov     rax, r15
0x18007c466  sub     rax, [rsi]
0x18007c469  sar     rax, 1
0x18007c46c  cmp     rax, 1Fh
0x18007c470  jg      loc_18007C587
0x18007c476  movsxd  r9, eax
0x18007c479  mov     r8, [rsi]
0x18007c47c  mov     edx, 20h ; ' '
0x18007c481  lea     rcx, [rbp+57h+String2]
0x18007c485  call    _o_wcsncpy_s_0
0x18007c48a  test    eax, eax
0x18007c48c  jz      short loc_18007C4B2
0x18007c48e  cmp     eax, 0Ch
0x18007c491  jz      loc_18007C5F8
0x18007c497  cmp     eax, 16h
0x18007c49a  jz      loc_18007C5ED
0x18007c4a0  cmp     eax, 22h ; '"'
0x18007c4a3  jz      loc_18007C5ED
0x18007c4a9  cmp     eax, 50h ; 'P'
0x18007c4ac  jnz     loc_18007C5E2
0x18007c4b2  mov     rdi, [rsi+8]
0x18007c4b6  lea     rcx, [rdi+20h]; lpCriticalSection
0x18007c4ba  call    cs:__imp_EnterCriticalSection
0x18007c4c0  mov     r12d, ebx
0x18007c4c3  mov     r14, rbx
0x18007c4c6  cmp     [rdi+18h], ebx
0x18007c4c9  jle     short loc_18007C4ED
0x18007c4cb  mov     rcx, [rdi+8]
0x18007c4cf  lea     rdx, [rbp+57h+String2]; lpString2
0x18007c4d3  mov     rcx, [rcx+r14*8]; lpString1
0x18007c4d7  call    cs:__imp_lstrcmpiW
0x18007c4dd  test    eax, eax
0x18007c4df  jz      short loc_18007C52F
0x18007c4e1  inc     r12d
0x18007c4e4  inc     r14
0x18007c4e7  cmp     r12d, [rdi+18h]
0x18007c4eb  jl      short loc_18007C4CB
0x18007c4ed  mov     r14, rbx
0x18007c4f0  lea     rcx, [rdi+20h]; lpCriticalSection
0x18007c4f4  call    cs:__imp_LeaveCriticalSection
0x18007c4fa  test    r14, r14
0x18007c4fd  jz      loc_18007C438
0x18007c503  mov     [rbp+57h+var_98], rbx
0x18007c507  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007c50b  inc     r8; int
0x18007c50e  cmp     [r14+r8*2], bx
0x18007c513  jnz     short loc_18007C50B
0x18007c515  mov     rdx, r14; wchar_t *
0x18007c518  lea     rcx, [rbp+57h+pv]; this
0x18007c51c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x18007c521  nop
0x18007c522  test    eax, eax
0x18007c524  jz      loc_18007C2A2
0x18007c52a  mov     rax, [rsi]
0x18007c52d  jmp     short loc_18007C55E
0x18007c52f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18007c533  jz      short loc_18007C4ED
0x18007c535  test    r14, r14
0x18007c538  js      loc_18007C5D7
0x18007c53e  cmp     r12d, [rdi+18h]
0x18007c542  jge     loc_18007C5D7
0x18007c548  mov     rax, [rdi+10h]
0x18007c54c  mov     r14, [rax+r14*8]
0x18007c550  jmp     short loc_18007C4F0
0x18007c552  mov     rcx, rax; lpsz
0x18007c555  call    cs:__imp_CharNextW
0x18007c55b  mov     [rsi], rax
0x18007c55e  cmp     rax, r15
0x18007c561  jnz     short loc_18007C552
0x18007c563  mov     r12b, [rbp+57h+var_AF]
0x18007c567  mov     r15b, [rbp+57h+var_B0]
0x18007c56b  mov     rcx, [rsi]; lpsz
0x18007c56e  call    cs:__imp_CharNextW
0x18007c574  mov     rdi, rax
0x18007c577  mov     [rsi], rax
0x18007c57a  cmp     [rax], bx
0x18007c57d  jz      short loc_18007C58E
0x18007c57f  mov     al, [rbp+57h+var_AE]
0x18007c582  jmp     loc_18007C2D0
0x18007c587  mov     ebx, 80004005h
0x18007c58c  jmp     short loc_18007C59D
0x18007c58e  mov     rcx, [rbp+57h+pv+8]
0x18007c592  mov     [rbp+57h+pv+8], rbx
0x18007c596  mov     rax, [rbp+57h+var_90]
0x18007c59a  mov     [rax], rcx
0x18007c59d  mov     rcx, [rbp+57h+pv+8]; pv
0x18007c5a1  call    cs:__imp_CoTaskMemFree
0x18007c5a7  mov     eax, ebx
0x18007c5a9  jmp     short loc_18007C5B0
0x18007c5ab  mov     eax, 80004003h
0x18007c5b0  mov     rcx, [rbp+57h+var_40]
0x18007c5b4  xor     rcx, rsp; StackCookie
0x18007c5b7  call    __security_check_cookie
0x18007c5bc  mov     rbx, [rsp+0D0h+arg_8]
0x18007c5c4  add     rsp, 0A0h
0x18007c5cb  pop     r15
0x18007c5cd  pop     r14
0x18007c5cf  pop     r13
0x18007c5d1  pop     r12
0x18007c5d3  pop     rdi
0x18007c5d4  pop     rsi
0x18007c5d5  pop     rbp
0x18007c5d6  retn
0x18007c5d7  mov     ecx, 8000000Bh; int
0x18007c5dc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18007c5e2  mov     ecx, 80004005h; int
0x18007c5e7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18007c5ed  mov     ecx, 80070057h; int
0x18007c5f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18007c5f8  mov     ecx, 8007000Eh; int
0x18007c5fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
