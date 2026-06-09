# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000418c`
- end: `0x18000445a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `718`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004698`

## callees

- `0x18000362c`
- `0x180003870`
- `0x18000418c`
- `0x180005b7c`
- `0x18001bf40`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800042c0`
- `msvcrt!wcsncpy_s` at `0x1800042c0`
- `KERNEL32!lstrcmpiW` at `0x180004315`
- `KERNEL32!lstrcmpiW` at `0x180004315`
- `KERNEL32!EnterCriticalSection` at `0x1800042f6`
- `KERNEL32!EnterCriticalSection` at `0x1800042f6`
- `KERNEL32!LeaveCriticalSection` at `0x18000432d`
- `KERNEL32!LeaveCriticalSection` at `0x18000432d`
- `ole32!CoTaskMemFree` at `0x18000420b`
- `ole32!CoTaskMemFree` at `0x1800043e1`
- `ole32!CoTaskMemFree` at `0x18000420b`
- `ole32!CoTaskMemFree` at `0x1800043e1`
- `ole32!CoTaskMemAlloc` at `0x18000421d`
- `ole32!CoTaskMemAlloc` at `0x18000421d`
- `USER32!CharNextW` at `0x180004250`
- `USER32!CharNextW` at `0x180004281`
- `USER32!CharNextW` at `0x18000438a`
- `USER32!CharNextW` at `0x1800043b4`
- `USER32!CharNextW` at `0x180004250`
- `USER32!CharNextW` at `0x180004281`
- `USER32!CharNextW` at `0x18000438a`
- `USER32!CharNextW` at `0x1800043b4`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  errno_t v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  wchar_t Destination[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v26[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v26[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_49:
    v25 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_50;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_46:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
      goto LABEL_53;
LABEL_47:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_49;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_46;
  }
  if ( !v13 )
    goto LABEL_52;
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
    goto LABEL_52;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_50;
  }
  v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
  if ( v18 )
  {
    if ( v18 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v18 == 22 || v18 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v18 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v19 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  v20 = 0;
  if ( *((int *)v19 + 6) <= 0 )
    goto LABEL_32;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_32;
  }
  if ( v20 == -1 )
  {
LABEL_32:
    v22 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v22 )
  {
LABEL_52:
    v25 = -2147352567;
    goto LABEL_50;
  }
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_47;
  }
LABEL_53:
  v25 = -2147024882;
LABEL_50:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x18000418c  mov     [rsp+arg_8], rbx
0x180004191  mov     [rsp+arg_18], rbp
0x180004196  push    rsi
0x180004197  push    rdi
0x180004198  push    r12
0x18000419a  push    r14
0x18000419c  push    r15
0x18000419e  sub     rsp, 80h
0x1800041a5  mov     rax, cs:__security_cookie
0x1800041ac  xor     rax, rsp
0x1800041af  mov     [rsp+0A8h+var_38], rax
0x1800041b4  xor     r12d, r12d
0x1800041b7  mov     r15, r8
0x1800041ba  mov     rbx, rdx
0x1800041bd  mov     r14, rcx
0x1800041c0  test    rdx, rdx
0x1800041c3  jz      loc_180004400
0x1800041c9  test    r8, r8
0x1800041cc  jz      loc_180004400
0x1800041d2  mov     [r8], r12
0x1800041d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800041d9  inc     rax
0x1800041dc  cmp     [rdx+rax*2], r12w
0x1800041e1  jnz     short loc_1800041D9
0x1800041e3  add     eax, eax
0x1800041e5  mov     [rsp+0A8h+var_88], r12d
0x1800041ea  cmp     eax, 64h ; 'd'
0x1800041ed  mov     ecx, 3E8h
0x1800041f2  cmovl   eax, ecx
0x1800041f5  mov     ecx, eax
0x1800041f7  mov     [rsp+0A8h+var_84], eax
0x1800041fb  add     rcx, rcx
0x1800041fe  mov     eax, 0FFFFFFFFh
0x180004203  cmp     rcx, rax
0x180004206  jbe     short loc_18000421B
0x180004208  mov     rcx, r12; pv
0x18000420b  call    cs:__imp_CoTaskMemFree
0x180004211  mov     eax, 8007000Eh
0x180004216  jmp     loc_180004405
0x18000421b  mov     ecx, ecx; cb
0x18000421d  call    cs:__imp_CoTaskMemAlloc
0x180004223  mov     [rsp+0A8h+pv], rax
0x180004228  mov     rcx, rax
0x18000422b  test    rax, rax
0x18000422e  jz      short loc_18000420B
0x180004230  mov     [rax], r12w
0x180004234  mov     [r14], rbx
0x180004237  movzx   eax, word ptr [rbx]
0x18000423a  test    ax, ax
0x18000423d  jz      loc_1800043D1
0x180004243  cmp     ax, 25h ; '%'
0x180004247  jnz     loc_18000439A
0x18000424d  mov     rcx, rbx; lpsz
0x180004250  call    cs:__imp_CharNextW
0x180004256  mov     [r14], rax
0x180004259  movzx   ecx, word ptr [rax]
0x18000425c  cmp     cx, 25h ; '%'
0x180004260  jnz     short loc_18000426A
0x180004262  mov     rdx, rax
0x180004265  jmp     loc_18000439D
0x18000426a  test    rax, rax
0x18000426d  jz      loc_1800043F2
0x180004273  mov     rdi, r12
0x180004276  jmp     short loc_18000428A
0x180004278  cmp     cx, 25h ; '%'
0x18000427c  jz      short loc_180004291
0x18000427e  mov     rcx, rax; lpsz
0x180004281  call    cs:__imp_CharNextW
0x180004287  movzx   ecx, word ptr [rax]
0x18000428a  test    cx, cx
0x18000428d  jnz     short loc_180004278
0x18000428f  jmp     short loc_180004294
0x180004291  mov     rdi, rax
0x180004294  test    rdi, rdi
0x180004297  jz      loc_1800043F2
0x18000429d  mov     rax, rdi
0x1800042a0  sub     rax, [r14]
0x1800042a3  sar     rax, 1
0x1800042a6  cmp     rax, 1Fh
0x1800042aa  jg      loc_1800043EB
0x1800042b0  mov     r8, [r14]; Source
0x1800042b3  lea     rcx, [rsp+0A8h+Destination]; Destination
0x1800042b8  movsxd  r9, eax; MaxCount
0x1800042bb  mov     edx, 20h ; ' '; SizeInWords
0x1800042c0  call    cs:__imp_wcsncpy_s
0x1800042c6  test    eax, eax
0x1800042c8  jz      short loc_1800042EE
0x1800042ca  cmp     eax, 0Ch
0x1800042cd  jz      loc_18000444F
0x1800042d3  cmp     eax, 16h
0x1800042d6  jz      loc_180004444
0x1800042dc  cmp     eax, 22h ; '"'
0x1800042df  jz      loc_180004444
0x1800042e5  cmp     eax, 50h ; 'P'
0x1800042e8  jnz     loc_180004439
0x1800042ee  mov     rsi, [r14+8]
0x1800042f2  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800042f6  call    cs:__imp_EnterCriticalSection
0x1800042fc  mov     ebx, r12d
0x1800042ff  cmp     [rsi+18h], r12d
0x180004303  jle     short loc_180004326
0x180004305  mov     rcx, [rsi+8]
0x180004309  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x18000430e  movsxd  rax, ebx
0x180004311  mov     rcx, [rcx+rax*8]; lpString1
0x180004315  call    cs:__imp_lstrcmpiW
0x18000431b  test    eax, eax
0x18000431d  jz      short loc_180004364
0x18000431f  inc     ebx
0x180004321  cmp     ebx, [rsi+18h]
0x180004324  jl      short loc_180004305
0x180004326  mov     rbx, r12
0x180004329  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000432d  call    cs:__imp_LeaveCriticalSection
0x180004333  test    rbx, rbx
0x180004336  jz      loc_1800043F2
0x18000433c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180004340  inc     r8; int
0x180004343  cmp     [rbx+r8*2], r12w
0x180004348  jnz     short loc_180004340
0x18000434a  mov     rdx, rbx; unsigned __int16 *
0x18000434d  lea     rcx, [rsp+0A8h+var_88]; this
0x180004352  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180004357  test    eax, eax
0x180004359  jz      loc_1800043F9
0x18000435f  mov     rax, [r14]
0x180004362  jmp     short loc_180004393
0x180004364  cmp     ebx, 0FFFFFFFFh
0x180004367  jz      short loc_180004326
0x180004369  test    ebx, ebx
0x18000436b  js      loc_18000442E
0x180004371  cmp     ebx, [rsi+18h]
0x180004374  jge     loc_18000442E
0x18000437a  mov     rax, [rsi+10h]
0x18000437e  movsxd  rcx, ebx
0x180004381  mov     rbx, [rax+rcx*8]
0x180004385  jmp     short loc_180004329
0x180004387  mov     rcx, rax; lpsz
0x18000438a  call    cs:__imp_CharNextW
0x180004390  mov     [r14], rax
0x180004393  cmp     rax, rdi
0x180004396  jnz     short loc_180004387
0x180004398  jmp     short loc_1800043B1
0x18000439a  mov     rdx, rbx; unsigned __int16 *
0x18000439d  mov     r8d, 1; int
0x1800043a3  lea     rcx, [rsp+0A8h+var_88]; this
0x1800043a8  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800043ad  test    eax, eax
0x1800043af  jz      short loc_1800043F9
0x1800043b1  mov     rcx, [r14]; lpsz
0x1800043b4  call    cs:__imp_CharNextW
0x1800043ba  mov     rbx, rax
0x1800043bd  mov     [r14], rax
0x1800043c0  movzx   eax, word ptr [rax]
0x1800043c3  test    ax, ax
0x1800043c6  jnz     loc_180004243
0x1800043cc  mov     rcx, [rsp+0A8h+pv]
0x1800043d1  mov     ebx, r12d
0x1800043d4  mov     [rsp+0A8h+pv], r12
0x1800043d9  mov     [r15], rcx
0x1800043dc  mov     rcx, [rsp+0A8h+pv]; pv
0x1800043e1  call    cs:__imp_CoTaskMemFree
0x1800043e7  mov     eax, ebx
0x1800043e9  jmp     short loc_180004405
0x1800043eb  mov     ebx, 80004005h
0x1800043f0  jmp     short loc_1800043DC
0x1800043f2  mov     ebx, 80020009h
0x1800043f7  jmp     short loc_1800043DC
0x1800043f9  mov     ebx, 8007000Eh
0x1800043fe  jmp     short loc_1800043DC
0x180004400  mov     eax, 80004003h
0x180004405  mov     rcx, [rsp+0A8h+var_38]
0x18000440a  xor     rcx, rsp; StackCookie
0x18000440d  call    __security_check_cookie
0x180004412  lea     r11, [rsp+0A8h+var_28]
0x18000441a  mov     rbx, [r11+38h]
0x18000441e  mov     rbp, [r11+48h]
0x180004422  mov     rsp, r11
0x180004425  pop     r15
0x180004427  pop     r14
0x180004429  pop     r12
0x18000442b  pop     rdi
0x18000442c  pop     rsi
0x18000442d  retn
0x18000442e  mov     ecx, 0C000008Ch; unsigned int
0x180004433  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180004438  int     3; Trap to Debugger
0x180004439  mov     ecx, 80004005h; int
0x18000443e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004444  mov     ecx, 80070057h; int
0x180004449  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000444f  mov     ecx, 8007000Eh; int
0x180004454  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
