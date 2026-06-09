# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x180011e40`
- end: `0x1800120f8`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `696`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012378`

## callees

- `0x1800020e0`
- `0x180010a20`
- `0x180011478`
- `0x180011e40`
- `0x1800137dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180011f81`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180011f81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011eea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012087`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011ecc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011ecc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011f16`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011f47`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180012034`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001205d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011f16`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180011f47`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180012034`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18001205d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011fcb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180011fcb`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, wchar_t *a2, wchar_t **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  wchar_t *v9; // rax
  wchar_t *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const wchar_t *v15; // rdx
  const WCHAR *v16; // rsi
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdi
  int v20; // ebx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  const wchar_t *v23; // rdx
  __int64 v24; // r8
  const WCHAR *i; // rax
  __int64 v26; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v28; // [rsp+30h] [rbp-29h]
  WCHAR String2[32]; // [rsp+40h] [rbp-19h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v26) = 0;
  HIDWORD(v26) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (wchar_t *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_50:
    v22 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_51;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v4;
LABEL_47:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v15, 1) )
        break;
      goto LABEL_48;
    }
    v13 = CharNextW(v4);
    *(_QWORD *)this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_47;
    }
    if ( !v13 )
      goto LABEL_34;
    v16 = 0;
    while ( v14 )
    {
      if ( v14 == 37 )
      {
        v16 = v13;
        break;
      }
      v13 = CharNextW(v13);
      v14 = *v13;
    }
    if ( !v16 )
    {
LABEL_34:
      v22 = -2147352567;
      goto LABEL_51;
    }
    v17 = ((__int64)v16 - *(_QWORD *)this) >> 1;
    if ( v17 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_51;
    }
    v18 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v17, v26);
    if ( v18 )
    {
      if ( v18 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v18 == 22 || v18 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v18 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v19 = *((_QWORD *)this + 1);
    v20 = 0;
    if ( *(int *)(v19 + 24) <= 0 )
      goto LABEL_34;
    while ( lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)(v19 + 8) + 8LL * v20), String2) )
    {
      if ( ++v20 >= *(_DWORD *)(v19 + 24) )
        goto LABEL_34;
    }
    if ( v20 == -1 )
      goto LABEL_34;
    if ( v20 < 0 || v20 >= *(_DWORD *)(v19 + 24) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v23 = *(const wchar_t **)(*(_QWORD *)(v19 + 16) + 8LL * v20);
    if ( !v23 )
      goto LABEL_34;
    v28 = 0;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v23, v24) )
      break;
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_48:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (wchar_t *)pv;
      goto LABEL_50;
    }
  }
  v22 = -2147024882;
LABEL_51:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x180011e40  mov     [rsp-8+arg_8], rbx
0x180011e45  mov     [rsp-8+arg_18], rsi
0x180011e4a  push    rbp
0x180011e4b  push    rdi
0x180011e4c  push    r12
0x180011e4e  push    r14
0x180011e50  push    r15
0x180011e52  lea     rbp, [rsp-37h]
0x180011e57  sub     rsp, 90h
0x180011e5e  mov     rax, cs:__security_cookie
0x180011e65  xor     rax, rsp
0x180011e68  mov     [rbp+57h+var_30], rax
0x180011e6c  mov     r15, r8
0x180011e6f  mov     rbx, rdx
0x180011e72  mov     r14, rcx
0x180011e75  xor     r12d, r12d
0x180011e78  test    rdx, rdx
0x180011e7b  jz      loc_18001209F
0x180011e81  test    r8, r8
0x180011e84  jz      loc_18001209F
0x180011e8a  mov     [r8], r12
0x180011e8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011e91  inc     rax
0x180011e94  cmp     [rdx+rax*2], r12w
0x180011e99  jnz     short loc_180011E91
0x180011e9b  add     eax, eax
0x180011e9d  mov     ecx, 3E8h
0x180011ea2  cmp     eax, 64h ; 'd'
0x180011ea5  cmovl   eax, ecx
0x180011ea8  mov     [rbp+57h+var_90], r12d
0x180011eac  mov     [rbp+57h+var_8C], eax
0x180011eaf  mov     ecx, eax
0x180011eb1  add     rcx, rcx
0x180011eb4  mov     eax, 0FFFFFFFFh
0x180011eb9  cmp     rcx, rax
0x180011ebc  jbe     short loc_180011ECA
0x180011ebe  mov     rax, r12
0x180011ec1  mov     rdx, r12
0x180011ec4  mov     [rbp+57h+pv], rdx
0x180011ec8  jmp     short loc_180011EE2
0x180011eca  mov     ecx, ecx; cb
0x180011ecc  call    cs:__imp_CoTaskMemAlloc
0x180011ed2  mov     rdx, rax
0x180011ed5  mov     [rbp+57h+pv], rax
0x180011ed9  test    rax, rax
0x180011edc  jz      short loc_180011EE2
0x180011ede  mov     [rax], r12w
0x180011ee2  test    rax, rax
0x180011ee5  jnz     short loc_180011EFA
0x180011ee7  mov     rcx, rax; pv
0x180011eea  call    cs:__imp_CoTaskMemFree
0x180011ef0  mov     eax, 8007000Eh
0x180011ef5  jmp     loc_1800120A4
0x180011efa  mov     [r14], rbx
0x180011efd  movzx   eax, word ptr [rbx]
0x180011f00  test    ax, ax
0x180011f03  jz      loc_180012079
0x180011f09  cmp     ax, 25h ; '%'
0x180011f0d  jnz     loc_180012044
0x180011f13  mov     rcx, rbx; lpsz
0x180011f16  call    cs:__imp_CharNextW
0x180011f1c  mov     [r14], rax
0x180011f1f  movzx   ecx, word ptr [rax]
0x180011f22  cmp     cx, 25h ; '%'
0x180011f26  jnz     short loc_180011F30
0x180011f28  mov     rdx, rax
0x180011f2b  jmp     loc_180012047
0x180011f30  test    rax, rax
0x180011f33  jz      loc_180011FDC
0x180011f39  mov     rsi, r12
0x180011f3c  jmp     short loc_180011F50
0x180011f3e  cmp     cx, 25h ; '%'
0x180011f42  jz      short loc_180011F57
0x180011f44  mov     rcx, rax; lpsz
0x180011f47  call    cs:__imp_CharNextW
0x180011f4d  movzx   ecx, word ptr [rax]
0x180011f50  test    cx, cx
0x180011f53  jnz     short loc_180011F3E
0x180011f55  jmp     short loc_180011F5A
0x180011f57  mov     rsi, rax
0x180011f5a  test    rsi, rsi
0x180011f5d  jz      short loc_180011FDC
0x180011f5f  mov     rax, rsi
0x180011f62  sub     rax, [r14]
0x180011f65  sar     rax, 1
0x180011f68  cmp     rax, 1Fh
0x180011f6c  jg      loc_180012091
0x180011f72  movsxd  r9, eax
0x180011f75  mov     r8, [r14]
0x180011f78  mov     edx, 20h ; ' '
0x180011f7d  lea     rcx, [rbp+57h+String2]
0x180011f81  call    cs:__imp__o_wcsncpy_s
0x180011f87  test    eax, eax
0x180011f89  jz      short loc_180011FAF
0x180011f8b  cmp     eax, 0Ch
0x180011f8e  jz      loc_1800120ED
0x180011f94  cmp     eax, 16h
0x180011f97  jz      loc_1800120E2
0x180011f9d  cmp     eax, 22h ; '"'
0x180011fa0  jz      loc_1800120E2
0x180011fa6  cmp     eax, 50h ; 'P'
0x180011fa9  jnz     loc_1800120D7
0x180011faf  mov     rdi, [r14+8]
0x180011fb3  mov     ebx, r12d
0x180011fb6  cmp     [rdi+18h], r12d
0x180011fba  jle     short loc_180011FDC
0x180011fbc  movsxd  rax, ebx
0x180011fbf  mov     rcx, [rdi+8]
0x180011fc3  lea     rdx, [rbp+57h+String2]; lpString2
0x180011fc7  mov     rcx, [rcx+rax*8]; lpString1
0x180011fcb  call    cs:__imp_lstrcmpiW
0x180011fd1  test    eax, eax
0x180011fd3  jz      short loc_180011FE6
0x180011fd5  inc     ebx
0x180011fd7  cmp     ebx, [rdi+18h]
0x180011fda  jl      short loc_180011FBC
0x180011fdc  mov     ebx, 80020009h
0x180011fe1  jmp     loc_180012083
0x180011fe6  cmp     ebx, 0FFFFFFFFh
0x180011fe9  jz      short loc_180011FDC
0x180011feb  test    ebx, ebx
0x180011fed  js      loc_1800120CC
0x180011ff3  cmp     ebx, [rdi+18h]
0x180011ff6  jge     loc_1800120CC
0x180011ffc  movsxd  rcx, ebx
0x180011fff  mov     rax, [rdi+10h]
0x180012003  mov     rdx, [rax+rcx*8]; wchar_t *
0x180012007  test    rdx, rdx
0x18001200a  jz      short loc_180011FDC
0x18001200c  mov     [rbp+57h+var_80], r12
0x180012010  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012014  inc     r8; int
0x180012017  cmp     [rdx+r8*2], r12w
0x18001201c  jnz     short loc_180012014
0x18001201e  lea     rcx, [rbp+57h+var_90]; this
0x180012022  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180012027  nop
0x180012028  test    eax, eax
0x18001202a  jz      short loc_180012098
0x18001202c  mov     rax, [r14]
0x18001202f  jmp     short loc_18001203D
0x180012031  mov     rcx, rax; lpsz
0x180012034  call    cs:__imp_CharNextW
0x18001203a  mov     [r14], rax
0x18001203d  cmp     rax, rsi
0x180012040  jnz     short loc_180012031
0x180012042  jmp     short loc_18001205A
0x180012044  mov     rdx, rbx; wchar_t *
0x180012047  mov     r8d, 1; int
0x18001204d  lea     rcx, [rbp+57h+var_90]; this
0x180012051  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180012056  test    eax, eax
0x180012058  jz      short loc_180012098
0x18001205a  mov     rcx, [r14]; lpsz
0x18001205d  call    cs:__imp_CharNextW
0x180012063  mov     rbx, rax
0x180012066  mov     [r14], rax
0x180012069  movzx   eax, word ptr [rax]
0x18001206c  test    ax, ax
0x18001206f  jnz     loc_180011F09
0x180012075  mov     rdx, [rbp+57h+pv]
0x180012079  mov     ebx, r12d
0x18001207c  mov     [rbp+57h+pv], r12
0x180012080  mov     [r15], rdx
0x180012083  mov     rcx, [rbp+57h+pv]; pv
0x180012087  call    cs:__imp_CoTaskMemFree
0x18001208d  mov     eax, ebx
0x18001208f  jmp     short loc_1800120A4
0x180012091  mov     ebx, 80004005h
0x180012096  jmp     short loc_180012083
0x180012098  mov     ebx, 8007000Eh
0x18001209d  jmp     short loc_180012083
0x18001209f  mov     eax, 80004003h
0x1800120a4  mov     rcx, [rbp+57h+var_30]
0x1800120a8  xor     rcx, rsp; StackCookie
0x1800120ab  call    __security_check_cookie
0x1800120b0  lea     r11, [rsp+0B0h+var_20]
0x1800120b8  mov     rbx, [r11+38h]
0x1800120bc  mov     rsi, [r11+48h]
0x1800120c0  mov     rsp, r11
0x1800120c3  pop     r15
0x1800120c5  pop     r14
0x1800120c7  pop     r12
0x1800120c9  pop     rdi
0x1800120ca  pop     rbp
0x1800120cb  retn
0x1800120cc  mov     ecx, 0C000008Ch; unsigned int
0x1800120d1  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800120d6  int     3; Trap to Debugger
0x1800120d7  mov     ecx, 80004005h; int
0x1800120dc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800120e2  mov     ecx, 80070057h; int
0x1800120e7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800120ed  mov     ecx, 8007000Eh; int
0x1800120f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
