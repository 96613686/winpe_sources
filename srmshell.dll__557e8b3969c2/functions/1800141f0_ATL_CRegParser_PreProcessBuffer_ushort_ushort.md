# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1800141f0`
- end: `0x1800144cf`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `735`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800147c0`

## callees

- `0x1800065bc`
- `0x180012d20`
- `0x1800141f0`
- `0x180015ac8`
- `0x18001b420`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180014333`
- `msvcrt!wcsncpy_s` at `0x180014333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014458`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001427a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001427a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001439f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001439f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014369`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014369`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800142c4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800142f5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014400`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014429`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800142c4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800142f5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014400`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180014429`
- `KERNEL32!lstrcmpiW` at `0x180014387`
- `KERNEL32!lstrcmpiW` at `0x180014387`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
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
  __int64 v26; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

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
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
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
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_51:
    v25 = 0;
    pv = 0;
    v26 = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v15, 1) )
      goto LABEL_55;
LABEL_49:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_51;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_48;
  }
  if ( !v13 )
    goto LABEL_54;
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
    goto LABEL_54;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v25 = -2147467259;
    goto LABEL_52;
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
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
  {
LABEL_34:
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
LABEL_54:
    v25 = -2147352567;
    goto LABEL_52;
  }
  v28 = 0;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v25 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x1800141f0  mov     [rsp-8+arg_8], rbx
0x1800141f5  push    rbp
0x1800141f6  push    rsi
0x1800141f7  push    rdi
0x1800141f8  push    r12
0x1800141fa  push    r13
0x1800141fc  push    r14
0x1800141fe  push    r15
0x180014200  lea     rbp, [rsp-27h]
0x180014205  sub     rsp, 90h
0x18001420c  mov     rax, cs:__security_cookie
0x180014213  xor     rax, rsp
0x180014216  mov     [rbp+57h+var_40], rax
0x18001421a  mov     r12, r8
0x18001421d  mov     rbx, rdx
0x180014220  mov     r14, rcx
0x180014223  xor     r13d, r13d
0x180014226  test    rdx, rdx
0x180014229  jz      loc_180014477
0x18001422f  test    r8, r8
0x180014232  jz      loc_180014477
0x180014238  mov     [r8], r13
0x18001423b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001423f  inc     rax
0x180014242  cmp     [rdx+rax*2], r13w
0x180014247  jnz     short loc_18001423F
0x180014249  add     eax, eax
0x18001424b  mov     ecx, 3E8h
0x180014250  cmp     eax, 64h ; 'd'
0x180014253  cmovl   eax, ecx
0x180014256  mov     dword ptr [rbp+57h+var_A0], r13d
0x18001425a  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18001425d  mov     ecx, eax
0x18001425f  add     rcx, rcx
0x180014262  mov     eax, 0FFFFFFFFh
0x180014267  cmp     rcx, rax
0x18001426a  jbe     short loc_180014278
0x18001426c  mov     rax, r13
0x18001426f  mov     rdx, r13
0x180014272  mov     [rbp+57h+pv], rdx
0x180014276  jmp     short loc_180014290
0x180014278  mov     ecx, ecx; cb
0x18001427a  call    cs:__imp_CoTaskMemAlloc
0x180014280  mov     rdx, rax
0x180014283  mov     [rbp+57h+pv], rax
0x180014287  test    rax, rax
0x18001428a  jz      short loc_180014290
0x18001428c  mov     [rax], r13w
0x180014290  test    rax, rax
0x180014293  jnz     short loc_1800142A8
0x180014295  mov     rcx, rax; pv
0x180014298  call    cs:__imp_CoTaskMemFree
0x18001429e  mov     eax, 8007000Eh
0x1800142a3  jmp     loc_18001447C
0x1800142a8  mov     [r14], rbx
0x1800142ab  movzx   eax, word ptr [rbx]
0x1800142ae  test    ax, ax
0x1800142b1  jz      loc_180014445
0x1800142b7  cmp     ax, 25h ; '%'
0x1800142bb  jnz     loc_180014410
0x1800142c1  mov     rcx, rbx; lpsz
0x1800142c4  call    cs:__imp_CharNextW
0x1800142ca  mov     [r14], rax
0x1800142cd  movzx   ecx, word ptr [rax]
0x1800142d0  cmp     cx, 25h ; '%'
0x1800142d4  jnz     short loc_1800142DE
0x1800142d6  mov     rdx, rax
0x1800142d9  jmp     loc_180014413
0x1800142de  test    rax, rax
0x1800142e1  jz      loc_180014469
0x1800142e7  mov     rdi, r13
0x1800142ea  jmp     short loc_1800142FE
0x1800142ec  cmp     cx, 25h ; '%'
0x1800142f0  jz      short loc_180014305
0x1800142f2  mov     rcx, rax; lpsz
0x1800142f5  call    cs:__imp_CharNextW
0x1800142fb  movzx   ecx, word ptr [rax]
0x1800142fe  test    cx, cx
0x180014301  jnz     short loc_1800142EC
0x180014303  jmp     short loc_180014308
0x180014305  mov     rdi, rax
0x180014308  test    rdi, rdi
0x18001430b  jz      loc_180014469
0x180014311  mov     rax, rdi
0x180014314  sub     rax, [r14]
0x180014317  sar     rax, 1
0x18001431a  cmp     rax, 1Fh
0x18001431e  jg      loc_180014462
0x180014324  movsxd  r9, eax; MaxCount
0x180014327  mov     r8, [r14]; Source
0x18001432a  mov     edx, 20h ; ' '; SizeInWords
0x18001432f  lea     rcx, [rbp+57h+Destination]; Destination
0x180014333  call    cs:__imp_wcsncpy_s
0x180014339  test    eax, eax
0x18001433b  jz      short loc_180014361
0x18001433d  cmp     eax, 0Ch
0x180014340  jz      loc_1800144C4
0x180014346  cmp     eax, 16h
0x180014349  jz      loc_1800144B9
0x18001434f  cmp     eax, 22h ; '"'
0x180014352  jz      loc_1800144B9
0x180014358  cmp     eax, 50h ; 'P'
0x18001435b  jnz     loc_1800144AE
0x180014361  mov     rsi, [r14+8]
0x180014365  lea     rcx, [rsi+20h]; lpCriticalSection
0x180014369  call    cs:__imp_EnterCriticalSection
0x18001436f  mov     ebx, r13d
0x180014372  cmp     [rsi+18h], r13d
0x180014376  jle     short loc_180014398
0x180014378  movsxd  rax, ebx
0x18001437b  mov     rcx, [rsi+8]
0x18001437f  lea     rdx, [rbp+57h+Destination]; lpString2
0x180014383  mov     rcx, [rcx+rax*8]; lpString1
0x180014387  call    cs:__imp_lstrcmpiW
0x18001438d  test    eax, eax
0x18001438f  jz      short loc_1800143DA
0x180014391  inc     ebx
0x180014393  cmp     ebx, [rsi+18h]
0x180014396  jl      short loc_180014378
0x180014398  mov     rbx, r13
0x18001439b  lea     rcx, [rsi+20h]; lpCriticalSection
0x18001439f  call    cs:__imp_LeaveCriticalSection
0x1800143a5  test    rbx, rbx
0x1800143a8  jz      loc_180014469
0x1800143ae  mov     [rbp+57h+var_90], r13
0x1800143b2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800143b6  inc     r8; int
0x1800143b9  cmp     [rbx+r8*2], r13w
0x1800143be  jnz     short loc_1800143B6
0x1800143c0  mov     rdx, rbx; unsigned __int16 *
0x1800143c3  lea     rcx, [rbp+57h+var_A0]; this
0x1800143c7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800143cc  nop
0x1800143cd  test    eax, eax
0x1800143cf  jz      loc_180014470
0x1800143d5  mov     rax, [r14]
0x1800143d8  jmp     short loc_180014409
0x1800143da  cmp     ebx, 0FFFFFFFFh
0x1800143dd  jz      short loc_180014398
0x1800143df  test    ebx, ebx
0x1800143e1  js      loc_1800144A3
0x1800143e7  cmp     ebx, [rsi+18h]
0x1800143ea  jge     loc_1800144A3
0x1800143f0  movsxd  rcx, ebx
0x1800143f3  mov     rax, [rsi+10h]
0x1800143f7  mov     rbx, [rax+rcx*8]
0x1800143fb  jmp     short loc_18001439B
0x1800143fd  mov     rcx, rax; lpsz
0x180014400  call    cs:__imp_CharNextW
0x180014406  mov     [r14], rax
0x180014409  cmp     rax, rdi
0x18001440c  jnz     short loc_1800143FD
0x18001440e  jmp     short loc_180014426
0x180014410  mov     rdx, rbx; unsigned __int16 *
0x180014413  mov     r8d, 1; int
0x180014419  lea     rcx, [rbp+57h+var_A0]; this
0x18001441d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180014422  test    eax, eax
0x180014424  jz      short loc_180014470
0x180014426  mov     rcx, [r14]; lpsz
0x180014429  call    cs:__imp_CharNextW
0x18001442f  mov     rbx, rax
0x180014432  mov     [r14], rax
0x180014435  movzx   eax, word ptr [rax]
0x180014438  test    ax, ax
0x18001443b  jnz     loc_1800142B7
0x180014441  mov     rdx, [rbp+57h+pv]
0x180014445  mov     ebx, r13d
0x180014448  mov     [rbp+57h+pv], r13
0x18001444c  mov     [rbp+57h+var_A0], r13
0x180014450  mov     [r12], rdx
0x180014454  mov     rcx, [rbp+57h+pv]; pv
0x180014458  call    cs:__imp_CoTaskMemFree
0x18001445e  mov     eax, ebx
0x180014460  jmp     short loc_18001447C
0x180014462  mov     ebx, 80004005h
0x180014467  jmp     short loc_180014454
0x180014469  mov     ebx, 80020009h
0x18001446e  jmp     short loc_180014454
0x180014470  mov     ebx, 8007000Eh
0x180014475  jmp     short loc_180014454
0x180014477  mov     eax, 80004003h
0x18001447c  mov     rcx, [rbp+57h+var_40]
0x180014480  xor     rcx, rsp; StackCookie
0x180014483  call    __security_check_cookie
0x180014488  mov     rbx, [rsp+0C0h+arg_8]
0x180014490  add     rsp, 90h
0x180014497  pop     r15
0x180014499  pop     r14
0x18001449b  pop     r13
0x18001449d  pop     r12
0x18001449f  pop     rdi
0x1800144a0  pop     rsi
0x1800144a1  pop     rbp
0x1800144a2  retn
0x1800144a3  mov     ecx, 0C000008Ch; unsigned int
0x1800144a8  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800144ad  int     3; Trap to Debugger
0x1800144ae  mov     ecx, 80004005h; int
0x1800144b3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800144b9  mov     ecx, 80070057h; int
0x1800144be  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800144c4  mov     ecx, 8007000Eh; int
0x1800144c9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
