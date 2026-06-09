# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180003c7c`
- end: `0x180003f81`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `773`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000420c`

## callees

- `0x1800015b0`
- `0x1800031f8`
- `0x18000335c`
- `0x180003c7c`
- `0x180005404`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180003dc2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180003dc2`
- `KERNEL32!lstrcmpiW` at `0x180003e22`
- `KERNEL32!lstrcmpiW` at `0x180003e22`
- `KERNEL32!LeaveCriticalSection` at `0x180003e45`
- `KERNEL32!LeaveCriticalSection` at `0x180003e45`
- `KERNEL32!EnterCriticalSection` at `0x180003dfe`
- `KERNEL32!EnterCriticalSection` at `0x180003dfe`
- `USER32!CharNextW` at `0x180003d46`
- `USER32!CharNextW` at `0x180003d81`
- `USER32!CharNextW` at `0x180003ea8`
- `USER32!CharNextW` at `0x180003ed8`
- `USER32!CharNextW` at `0x180003d46`
- `USER32!CharNextW` at `0x180003d81`
- `USER32!CharNextW` at `0x180003ea8`
- `USER32!CharNextW` at `0x180003ed8`
- `ole32!CoTaskMemFree` at `0x180003cf9`
- `ole32!CoTaskMemFree` at `0x180003f09`
- `ole32!CoTaskMemFree` at `0x180003cf9`
- `ole32!CoTaskMemFree` at `0x180003f09`
- `ole32!CoTaskMemAlloc` at `0x180003d11`
- `ole32!CoTaskMemAlloc` at `0x180003d11`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned int v3; // ebx
  unsigned __int16 *v5; // rdi
  __int64 v7; // rax
  int v8; // eax
  unsigned __int64 v9; // rcx
  _WORD *v10; // rax
  WCHAR v12; // cx
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rsi
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rbp
  int v20; // r14d
  __int64 v21; // rdi
  unsigned int v22; // edx
  const unsigned __int16 *v23; // rdi
  __int64 v24; // r8
  const WCHAR *i; // rax
  LPWSTR v26; // rax
  _DWORD v27[2]; // [rsp+20h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-90h]
  WCHAR String2[32]; // [rsp+30h] [rbp-88h] BYREF

  v3 = 0;
  v5 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = 2 * v7;
  v27[0] = 0;
  if ( v8 < 100 )
    v8 = 1000;
  v27[1] = v8;
  v9 = 2LL * (unsigned int)v8;
  if ( v9 > 0xFFFFFFFF )
  {
    v10 = 0;
LABEL_9:
    CoTaskMemFree(v10);
    return 2147942414LL;
  }
  v10 = CoTaskMemAlloc((unsigned int)v9);
  pv = v10;
  if ( !v10 )
    goto LABEL_9;
  *v10 = 0;
  *(_QWORD *)this = v5;
  v12 = *v5;
  if ( !*v5 )
  {
LABEL_49:
    pv = 0;
    *a3 = v10;
    goto LABEL_50;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v5;
LABEL_46:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v15, 1) )
        break;
      goto LABEL_47;
    }
    v13 = CharNextW(v5);
    *(_QWORD *)this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_46;
    }
    v16 = 0;
    if ( !v13 )
      goto LABEL_16;
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
LABEL_16:
      v3 = -2147352567;
      goto LABEL_50;
    }
    v17 = ((__int64)v16 - *(_QWORD *)this) >> 1;
    if ( v17 > 31 )
    {
      v3 = -2147467259;
      goto LABEL_50;
    }
    v18 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v17);
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
    EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 32));
    v20 = 0;
    v21 = 0;
    if ( *(int *)(v19 + 24) <= 0 )
      goto LABEL_32;
    while ( lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)(v19 + 8) + 8 * v21), String2) )
    {
      ++v20;
      ++v21;
      if ( v20 >= *(_DWORD *)(v19 + 24) )
        goto LABEL_32;
    }
    if ( v21 == -1 )
    {
LABEL_32:
      v23 = 0;
    }
    else
    {
      if ( v21 < 0 || v20 >= *(_DWORD *)(v19 + 24) )
      {
        ATL::_AtlRaiseException(0xC000008C, v22);
        __debugbreak();
      }
      v23 = *(const unsigned __int16 **)(*(_QWORD *)(v19 + 16) + 8 * v21);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 32));
    if ( !v23 )
      goto LABEL_16;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v23, v24) )
      break;
    for ( i = *(const WCHAR **)this; i != v16; *(_QWORD *)this = i )
      i = CharNextW(i);
LABEL_47:
    v26 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v26;
    v5 = v26;
    v12 = *v26;
    if ( !*v26 )
    {
      v10 = pv;
      goto LABEL_49;
    }
  }
  v3 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v3;
}

```

## disassembly

```asm
0x180003c7c  mov     [rsp+arg_8], rbx
0x180003c81  push    rbp
0x180003c82  push    rsi
0x180003c83  push    rdi
0x180003c84  push    r12
0x180003c86  push    r13
0x180003c88  push    r14
0x180003c8a  push    r15
0x180003c8c  sub     rsp, 80h
0x180003c93  mov     rax, cs:__security_cookie
0x180003c9a  xor     rax, rsp
0x180003c9d  mov     [rsp+0B8h+var_48], rax
0x180003ca2  xor     ebx, ebx
0x180003ca4  mov     r13, r8
0x180003ca7  mov     rdi, rdx
0x180003caa  mov     r15, rcx
0x180003cad  test    rdx, rdx
0x180003cb0  jz      loc_180003F27
0x180003cb6  test    r8, r8
0x180003cb9  jz      loc_180003F27
0x180003cbf  mov     [r8], rbx
0x180003cc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003cc6  inc     rax
0x180003cc9  cmp     [rdx+rax*2], bx
0x180003ccd  jnz     short loc_180003CC6
0x180003ccf  add     eax, eax
0x180003cd1  mov     [rsp+0B8h+var_98], ebx
0x180003cd5  cmp     eax, 64h ; 'd'
0x180003cd8  mov     ecx, 3E8h
0x180003cdd  cmovl   eax, ecx
0x180003ce0  mov     ecx, eax
0x180003ce2  mov     [rsp+0B8h+var_94], eax
0x180003ce6  add     rcx, rcx
0x180003ce9  mov     eax, 0FFFFFFFFh
0x180003cee  cmp     rcx, rax
0x180003cf1  jbe     short loc_180003D0F
0x180003cf3  mov     rax, rbx
0x180003cf6  mov     rcx, rax; pv
0x180003cf9  call    cs:__imp_CoTaskMemFree
0x180003d00  nop     dword ptr [rax+rax+00h]
0x180003d05  mov     eax, 8007000Eh
0x180003d0a  jmp     loc_180003F2C
0x180003d0f  mov     ecx, ecx; cb
0x180003d11  call    cs:__imp_CoTaskMemAlloc
0x180003d18  nop     dword ptr [rax+rax+00h]
0x180003d1d  mov     [rsp+0B8h+pv], rax
0x180003d22  test    rax, rax
0x180003d25  jz      short loc_180003CF6
0x180003d27  mov     [rax], bx
0x180003d2a  mov     [r15], rdi
0x180003d2d  movzx   ecx, word ptr [rdi]
0x180003d30  test    cx, cx
0x180003d33  jz      loc_180003EFB
0x180003d39  cmp     cx, 25h ; '%'
0x180003d3d  jnz     loc_180003EBE
0x180003d43  mov     rcx, rdi; lpsz
0x180003d46  call    cs:__imp_CharNextW
0x180003d4d  nop     dword ptr [rax+rax+00h]
0x180003d52  mov     [r15], rax
0x180003d55  movzx   ecx, word ptr [rax]
0x180003d58  cmp     cx, 25h ; '%'
0x180003d5c  jnz     short loc_180003D66
0x180003d5e  mov     rdx, rax
0x180003d61  jmp     loc_180003EC1
0x180003d66  mov     rsi, rbx
0x180003d69  test    rax, rax
0x180003d6c  jnz     short loc_180003D90
0x180003d6e  mov     ebx, 80020009h
0x180003d73  jmp     loc_180003F04
0x180003d78  cmp     cx, 25h ; '%'
0x180003d7c  jz      short loc_180003D97
0x180003d7e  mov     rcx, rax; lpsz
0x180003d81  call    cs:__imp_CharNextW
0x180003d88  nop     dword ptr [rax+rax+00h]
0x180003d8d  movzx   ecx, word ptr [rax]
0x180003d90  test    cx, cx
0x180003d93  jnz     short loc_180003D78
0x180003d95  jmp     short loc_180003D9A
0x180003d97  mov     rsi, rax
0x180003d9a  test    rsi, rsi
0x180003d9d  jz      short loc_180003D6E
0x180003d9f  mov     rax, rsi
0x180003da2  sub     rax, [r15]
0x180003da5  sar     rax, 1
0x180003da8  cmp     rax, 1Fh
0x180003dac  jg      loc_180003F19
0x180003db2  mov     r8, [r15]
0x180003db5  lea     rcx, [rsp+0B8h+String2]
0x180003dba  movsxd  r9, eax
0x180003dbd  mov     edx, 20h ; ' '
0x180003dc2  call    cs:__imp__o_wcsncpy_s
0x180003dc9  nop     dword ptr [rax+rax+00h]
0x180003dce  test    eax, eax
0x180003dd0  jz      short loc_180003DF6
0x180003dd2  cmp     eax, 0Ch
0x180003dd5  jz      loc_180003F76
0x180003ddb  cmp     eax, 16h
0x180003dde  jz      loc_180003F6B
0x180003de4  cmp     eax, 22h ; '"'
0x180003de7  jz      loc_180003F6B
0x180003ded  cmp     eax, 50h ; 'P'
0x180003df0  jnz     loc_180003F60
0x180003df6  mov     rbp, [r15+8]
0x180003dfa  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003dfe  call    cs:__imp_EnterCriticalSection
0x180003e05  nop     dword ptr [rax+rax+00h]
0x180003e0a  mov     r14d, ebx
0x180003e0d  mov     rdi, rbx
0x180003e10  cmp     [rbp+18h], ebx
0x180003e13  jle     short loc_180003E3E
0x180003e15  mov     rcx, [rbp+8]
0x180003e19  lea     rdx, [rsp+0B8h+String2]; lpString2
0x180003e1e  mov     rcx, [rcx+rdi*8]; lpString1
0x180003e22  call    cs:__imp_lstrcmpiW
0x180003e29  nop     dword ptr [rax+rax+00h]
0x180003e2e  test    eax, eax
0x180003e30  jz      short loc_180003E82
0x180003e32  inc     r14d
0x180003e35  inc     rdi
0x180003e38  cmp     r14d, [rbp+18h]
0x180003e3c  jl      short loc_180003E15
0x180003e3e  mov     rdi, rbx
0x180003e41  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003e45  call    cs:__imp_LeaveCriticalSection
0x180003e4c  nop     dword ptr [rax+rax+00h]
0x180003e51  test    rdi, rdi
0x180003e54  jz      loc_180003D6E
0x180003e5a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180003e5e  inc     r8; int
0x180003e61  cmp     [rdi+r8*2], bx
0x180003e66  jnz     short loc_180003E5E
0x180003e68  mov     rdx, rdi; unsigned __int16 *
0x180003e6b  lea     rcx, [rsp+0B8h+var_98]; this
0x180003e70  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003e75  test    eax, eax
0x180003e77  jz      loc_180003F20
0x180003e7d  mov     rax, [r15]
0x180003e80  jmp     short loc_180003EB7
0x180003e82  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180003e86  jz      short loc_180003E3E
0x180003e88  test    rdi, rdi
0x180003e8b  js      loc_180003F55
0x180003e91  cmp     r14d, [rbp+18h]
0x180003e95  jge     loc_180003F55
0x180003e9b  mov     rax, [rbp+10h]
0x180003e9f  mov     rdi, [rax+rdi*8]
0x180003ea3  jmp     short loc_180003E41
0x180003ea5  mov     rcx, rax; lpsz
0x180003ea8  call    cs:__imp_CharNextW
0x180003eaf  nop     dword ptr [rax+rax+00h]
0x180003eb4  mov     [r15], rax
0x180003eb7  cmp     rax, rsi
0x180003eba  jnz     short loc_180003EA5
0x180003ebc  jmp     short loc_180003ED5
0x180003ebe  mov     rdx, rdi; unsigned __int16 *
0x180003ec1  mov     r8d, 1; int
0x180003ec7  lea     rcx, [rsp+0B8h+var_98]; this
0x180003ecc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180003ed1  test    eax, eax
0x180003ed3  jz      short loc_180003F20
0x180003ed5  mov     rcx, [r15]; lpsz
0x180003ed8  call    cs:__imp_CharNextW
0x180003edf  nop     dword ptr [rax+rax+00h]
0x180003ee4  mov     [r15], rax
0x180003ee7  mov     rdi, rax
0x180003eea  movzx   ecx, word ptr [rax]
0x180003eed  test    cx, cx
0x180003ef0  jnz     loc_180003D39
0x180003ef6  mov     rax, [rsp+0B8h+pv]
0x180003efb  mov     [rsp+0B8h+pv], rbx
0x180003f00  mov     [r13+0], rax
0x180003f04  mov     rcx, [rsp+0B8h+pv]; pv
0x180003f09  call    cs:__imp_CoTaskMemFree
0x180003f10  nop     dword ptr [rax+rax+00h]
0x180003f15  mov     eax, ebx
0x180003f17  jmp     short loc_180003F2C
0x180003f19  mov     ebx, 80004005h
0x180003f1e  jmp     short loc_180003F04
0x180003f20  mov     ebx, 8007000Eh
0x180003f25  jmp     short loc_180003F04
0x180003f27  mov     eax, 80004003h
0x180003f2c  mov     rcx, [rsp+0B8h+var_48]
0x180003f31  xor     rcx, rsp; StackCookie
0x180003f34  call    __security_check_cookie
0x180003f39  mov     rbx, [rsp+0B8h+arg_8]
0x180003f41  add     rsp, 80h
0x180003f48  pop     r15
0x180003f4a  pop     r14
0x180003f4c  pop     r13
0x180003f4e  pop     r12
0x180003f50  pop     rdi
0x180003f51  pop     rsi
0x180003f52  pop     rbp
0x180003f53  retn
0x180003f55  mov     ecx, 0C000008Ch; unsigned int
0x180003f5a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003f5f  int     3; Trap to Debugger
0x180003f60  mov     ecx, 80004005h; int
0x180003f65  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003f6b  mov     ecx, 80070057h; int
0x180003f70  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003f76  mov     ecx, 8007000Eh; int
0x180003f7b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
