# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x180006d3c`
- end: `0x180007143`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `1031`
- prototype: `__int64 __fastcall(LPCWSTR *this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000862c`

## callees

- `0x180006c68`
- `0x180006d3c`
- `0x1800078c8`
- `0x18002ffa4`
- `0x18002ffd0`
- `0x1800322d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006dcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006dcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800070e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800070e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ffa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007034`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007034`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e39`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e45`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e51`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e5d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006eac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006ec2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006f3f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006f8b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007095`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800070ae`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e39`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e45`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e51`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006e5d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006eac`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006ec2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006f3f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006f8b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007095`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800070ae`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007017`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007017`

## pseudocode

```c
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
            if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append(
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
          if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v18, 1) )
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
        if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append(
                              (ATL::CRegParser::CParseBuffer *)pv,
                              L"\r\n\t}\r\n}\r\n",
                              9) )
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
        if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v19, 1) )
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
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)pv, v28, v29) )
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
0x180006d3c  mov     [rsp-8+arg_8], rbx
0x180006d41  push    rbp
0x180006d42  push    rsi
0x180006d43  push    rdi
0x180006d44  push    r12
0x180006d46  push    r13
0x180006d48  push    r14
0x180006d4a  push    r15
0x180006d4c  lea     rbp, [rsp-27h]
0x180006d51  sub     rsp, 0A0h
0x180006d58  mov     rax, cs:__security_cookie
0x180006d5f  xor     rax, rsp
0x180006d62  mov     [rbp+57h+var_40], rax
0x180006d66  mov     rax, r8
0x180006d69  mov     [rbp+57h+var_90], rax
0x180006d6d  mov     rdi, rdx
0x180006d70  mov     rsi, rcx
0x180006d73  xor     ebx, ebx
0x180006d75  test    rdx, rdx
0x180006d78  jz      loc_1800070EB
0x180006d7e  test    rax, rax
0x180006d81  jz      loc_1800070EB
0x180006d87  mov     [r8], rbx
0x180006d8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006d8e  inc     rax
0x180006d91  cmp     [rdx+rax*2], bx
0x180006d95  jnz     short loc_180006D8E
0x180006d97  add     eax, eax
0x180006d99  xorps   xmm0, xmm0
0x180006d9c  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180006da0  mov     ecx, 3E8h
0x180006da5  cmp     eax, 64h ; 'd'
0x180006da8  cmovl   eax, ecx
0x180006dab  mov     dword ptr [rbp+57h+pv], ebx
0x180006dae  mov     dword ptr [rbp+57h+pv+4], eax
0x180006db1  mov     ecx, eax
0x180006db3  add     rcx, rcx
0x180006db6  mov     eax, 0FFFFFFFFh
0x180006dbb  cmp     rcx, rax
0x180006dbe  jbe     short loc_180006DC9
0x180006dc0  mov     rax, rbx
0x180006dc3  mov     [rbp+57h+pv+8], rbx
0x180006dc7  jmp     short loc_180006DDD
0x180006dc9  mov     ecx, ecx; cb
0x180006dcb  call    cs:__imp_CoTaskMemAlloc
0x180006dd1  mov     [rbp+57h+pv+8], rax
0x180006dd5  test    rax, rax
0x180006dd8  jz      short loc_180006DDD
0x180006dda  mov     [rax], bx
0x180006ddd  test    rax, rax
0x180006de0  jnz     short loc_180006DEC
0x180006de2  mov     ebx, 8007000Eh
0x180006de7  jmp     loc_1800070DD
0x180006dec  mov     [rsi], rdi
0x180006def  mov     al, cs:?_AtlRegisterPerUser@ATL@@3_NA; bool ATL::_AtlRegisterPerUser
0x180006df5  mov     [rbp+57h+var_AE], al
0x180006df8  mov     r13d, ebx
0x180006dfb  mov     r12b, bl
0x180006dfe  mov     [rbp+57h+var_AF], bl
0x180006e01  mov     r15b, bl
0x180006e04  mov     [rbp+57h+var_B0], bl
0x180006e07  cmp     [rdi], bx
0x180006e0a  jz      loc_1800070CE
0x180006e10  cmp     al, 1
0x180006e12  jnz     loc_180006F33
0x180006e18  test    r13d, r13d
0x180006e1b  jnz     short loc_180006E8E
0x180006e1d  lea     rdx, aHkcr; "HKCR"
0x180006e24  mov     rcx, rdi; Str
0x180006e27  call    wcsstr
0x180006e2c  test    rax, rax
0x180006e2f  jz      short loc_180006E8E
0x180006e31  cmp     rax, [rsi]
0x180006e34  jnz     short loc_180006E8E
0x180006e36  mov     rcx, [rsi]; lpsz
0x180006e39  call    cs:__imp_CharNextW
0x180006e3f  mov     [rsi], rax
0x180006e42  mov     rcx, rax; lpsz
0x180006e45  call    cs:__imp_CharNextW
0x180006e4b  mov     [rsi], rax
0x180006e4e  mov     rcx, rax; lpsz
0x180006e51  call    cs:__imp_CharNextW
0x180006e57  mov     [rsi], rax
0x180006e5a  mov     rcx, rax; lpsz
0x180006e5d  call    cs:__imp_CharNextW
0x180006e63  mov     [rsi], rax
0x180006e66  mov     [rbp+57h+var_98], rbx
0x180006e6a  lea     r8d, [r13+1Fh]; int
0x180006e6e  lea     rdx, aHkcuSoftwareCl; "HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClass"...
0x180006e75  lea     rcx, [rbp+57h+pv]; this
0x180006e79  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180006e7e  nop
0x180006e7f  test    eax, eax
0x180006e81  jz      loc_180006DE2
0x180006e87  mov     r12b, 1
0x180006e8a  mov     [rbp+57h+var_AF], r12b
0x180006e8e  mov     rcx, [rsi]; lpsz
0x180006e91  mov     edi, 27h ; '''
0x180006e96  cmp     di, [rcx]
0x180006e99  jnz     short loc_180006EE7
0x180006e9b  test    r15b, r15b
0x180006e9e  jnz     short loc_180006EAC
0x180006ea0  mov     r15b, 1
0x180006ea3  mov     [rbp+57h+var_B0], r15b
0x180006ea7  jmp     loc_180006F33
0x180006eac  call    cs:__imp_CharNextW
0x180006eb2  cmp     di, [rax]
0x180006eb5  jz      short loc_180006EBF
0x180006eb7  mov     r15b, bl
0x180006eba  mov     [rbp+57h+var_B0], bl
0x180006ebd  jmp     short loc_180006EEC
0x180006ebf  mov     rcx, [rsi]; lpsz
0x180006ec2  call    cs:__imp_CharNextW
0x180006ec8  mov     [rsi], rax
0x180006ecb  mov     r8d, 1; int
0x180006ed1  mov     rdx, rax; wchar_t *
0x180006ed4  lea     rcx, [rbp+57h+pv]; this
0x180006ed8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180006edd  test    eax, eax
0x180006edf  jz      loc_180006DE2
0x180006ee5  jmp     short loc_180006F33
0x180006ee7  test    r15b, r15b
0x180006eea  jnz     short loc_180006F33
0x180006eec  mov     rax, [rsi]
0x180006eef  cmp     word ptr [rax], 7Bh ; '{'
0x180006ef3  jnz     short loc_180006EFA
0x180006ef5  inc     r13d
0x180006ef8  jmp     short loc_180006F33
0x180006efa  cmp     word ptr [rax], 7Dh ; '}'
0x180006efe  jnz     short loc_180006F33
0x180006f00  sub     r13d, 1
0x180006f04  jnz     short loc_180006F33
0x180006f06  cmp     r12b, 1
0x180006f0a  jnz     short loc_180006F33
0x180006f0c  mov     [rbp+57h+var_98], rbx
0x180006f10  lea     r8d, [r13+9]; int
0x180006f14  lea     rdx, asc_18003B7B0; "\r\n\t}\r\n}\r\n"
0x180006f1b  lea     rcx, [rbp+57h+pv]; this
0x180006f1f  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180006f24  nop
0x180006f25  test    eax, eax
0x180006f27  jz      loc_180006DE2
0x180006f2d  mov     r12b, bl
0x180006f30  mov     [rbp+57h+var_AF], bl
0x180006f33  mov     rdx, [rsi]
0x180006f36  cmp     word ptr [rdx], 25h ; '%'
0x180006f3a  jnz     short loc_180006F54
0x180006f3c  mov     rcx, rdx; lpsz
0x180006f3f  call    cs:__imp_CharNextW
0x180006f45  mov     [rsi], rax
0x180006f48  movzx   ecx, word ptr [rax]
0x180006f4b  cmp     cx, 25h ; '%'
0x180006f4f  jnz     short loc_180006F70
0x180006f51  mov     rdx, rax; wchar_t *
0x180006f54  mov     r8d, 1; int
0x180006f5a  lea     rcx, [rbp+57h+pv]; this
0x180006f5e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180006f63  test    eax, eax
0x180006f65  jz      loc_180006DE2
0x180006f6b  jmp     loc_1800070AB
0x180006f70  mov     r15, rbx
0x180006f73  test    rax, rax
0x180006f76  jnz     short loc_180006F94
0x180006f78  mov     ebx, 80020009h
0x180006f7d  jmp     loc_1800070DD
0x180006f82  cmp     cx, 25h ; '%'
0x180006f86  jz      short loc_180006F9B
0x180006f88  mov     rcx, rax; lpsz
0x180006f8b  call    cs:__imp_CharNextW
0x180006f91  movzx   ecx, word ptr [rax]
0x180006f94  test    cx, cx
0x180006f97  jnz     short loc_180006F82
0x180006f99  jmp     short loc_180006F9E
0x180006f9b  mov     r15, rax
0x180006f9e  test    r15, r15
0x180006fa1  jz      short loc_180006F78
0x180006fa3  mov     rax, r15
0x180006fa6  sub     rax, [rsi]
0x180006fa9  sar     rax, 1
0x180006fac  cmp     rax, 1Fh
0x180006fb0  jg      loc_1800070C7
0x180006fb6  movsxd  r9, eax
0x180006fb9  mov     r8, [rsi]
0x180006fbc  mov     edx, 20h ; ' '
0x180006fc1  lea     rcx, [rbp+57h+String2]
0x180006fc5  call    _o_wcsncpy_s_0
0x180006fca  test    eax, eax
0x180006fcc  jz      short loc_180006FF2
0x180006fce  cmp     eax, 0Ch
0x180006fd1  jz      loc_180007138
0x180006fd7  cmp     eax, 16h
0x180006fda  jz      loc_18000712D
0x180006fe0  cmp     eax, 22h ; '"'
0x180006fe3  jz      loc_18000712D
0x180006fe9  cmp     eax, 50h ; 'P'
0x180006fec  jnz     loc_180007122
0x180006ff2  mov     rdi, [rsi+8]
0x180006ff6  lea     rcx, [rdi+20h]; lpCriticalSection
0x180006ffa  call    cs:__imp_EnterCriticalSection
0x180007000  mov     r12d, ebx
0x180007003  mov     r14, rbx
0x180007006  cmp     [rdi+18h], ebx
0x180007009  jle     short loc_18000702D
0x18000700b  mov     rcx, [rdi+8]
0x18000700f  lea     rdx, [rbp+57h+String2]; lpString2
0x180007013  mov     rcx, [rcx+r14*8]; lpString1
0x180007017  call    cs:__imp_lstrcmpiW
0x18000701d  test    eax, eax
0x18000701f  jz      short loc_18000706F
0x180007021  inc     r12d
0x180007024  inc     r14
0x180007027  cmp     r12d, [rdi+18h]
0x18000702b  jl      short loc_18000700B
0x18000702d  mov     r14, rbx
0x180007030  lea     rcx, [rdi+20h]; lpCriticalSection
0x180007034  call    cs:__imp_LeaveCriticalSection
0x18000703a  test    r14, r14
0x18000703d  jz      loc_180006F78
0x180007043  mov     [rbp+57h+var_98], rbx
0x180007047  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000704b  inc     r8; int
0x18000704e  cmp     [r14+r8*2], bx
0x180007053  jnz     short loc_18000704B
0x180007055  mov     rdx, r14; wchar_t *
0x180007058  lea     rcx, [rbp+57h+pv]; this
0x18000705c  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x180007061  nop
0x180007062  test    eax, eax
0x180007064  jz      loc_180006DE2
0x18000706a  mov     rax, [rsi]
0x18000706d  jmp     short loc_18000709E
0x18000706f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180007073  jz      short loc_18000702D
0x180007075  test    r14, r14
0x180007078  js      loc_180007117
0x18000707e  cmp     r12d, [rdi+18h]
0x180007082  jge     loc_180007117
0x180007088  mov     rax, [rdi+10h]
0x18000708c  mov     r14, [rax+r14*8]
0x180007090  jmp     short loc_180007030
0x180007092  mov     rcx, rax; lpsz
0x180007095  call    cs:__imp_CharNextW
0x18000709b  mov     [rsi], rax
0x18000709e  cmp     rax, r15
0x1800070a1  jnz     short loc_180007092
0x1800070a3  mov     r12b, [rbp+57h+var_AF]
0x1800070a7  mov     r15b, [rbp+57h+var_B0]
0x1800070ab  mov     rcx, [rsi]; lpsz
0x1800070ae  call    cs:__imp_CharNextW
0x1800070b4  mov     rdi, rax
0x1800070b7  mov     [rsi], rax
0x1800070ba  cmp     [rax], bx
0x1800070bd  jz      short loc_1800070CE
0x1800070bf  mov     al, [rbp+57h+var_AE]
0x1800070c2  jmp     loc_180006E10
0x1800070c7  mov     ebx, 80004005h
0x1800070cc  jmp     short loc_1800070DD
0x1800070ce  mov     rcx, [rbp+57h+pv+8]
0x1800070d2  mov     [rbp+57h+pv+8], rbx
0x1800070d6  mov     rax, [rbp+57h+var_90]
0x1800070da  mov     [rax], rcx
0x1800070dd  mov     rcx, [rbp+57h+pv+8]; pv
0x1800070e1  call    cs:__imp_CoTaskMemFree
0x1800070e7  mov     eax, ebx
0x1800070e9  jmp     short loc_1800070F0
0x1800070eb  mov     eax, 80004003h
0x1800070f0  mov     rcx, [rbp+57h+var_40]
0x1800070f4  xor     rcx, rsp; StackCookie
0x1800070f7  call    __security_check_cookie
0x1800070fc  mov     rbx, [rsp+0D0h+arg_8]
0x180007104  add     rsp, 0A0h
0x18000710b  pop     r15
0x18000710d  pop     r14
0x18000710f  pop     r13
0x180007111  pop     r12
0x180007113  pop     rdi
0x180007114  pop     rsi
0x180007115  pop     rbp
0x180007116  retn
0x180007117  mov     ecx, 8000000Bh; int
0x18000711c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007122  mov     ecx, 80004005h; int
0x180007127  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000712d  mov     ecx, 80070057h; int
0x180007132  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007138  mov     ecx, 8007000Eh; int
0x18000713d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
