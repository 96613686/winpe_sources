# ATL::CRegParser::PreProcessBuffer(char *,char * *)

- ea: `0x1800111c8`
- end: `0x180011441`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEADPEAPEAD@Z`
- size: `633`
- prototype: `int(ATL::CRegParser *__hidden this, char *, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001167c`

## callees

- `0x180003b70`
- `0x180009994`
- `0x18000f68c`
- `0x18000fe68`
- `0x1800111c8`
- `0x180014270`

## import_xrefs

- `msvcrt!strncpy_s` at `0x180011317`
- `msvcrt!strncpy_s` at `0x180011317`
- `ole32!CoTaskMemAlloc` at `0x180011233`
- `ole32!CoTaskMemAlloc` at `0x180011233`
- `ole32!CoTaskMemFree` at `0x1800112b9`
- `ole32!CoTaskMemFree` at `0x1800113e1`
- `ole32!CoTaskMemFree` at `0x1800112b9`
- `ole32!CoTaskMemFree` at `0x1800113e1`
- `USER32!CharNextA` at `0x18001125b`
- `USER32!CharNextA` at `0x180011270`
- `USER32!CharNextA` at `0x180011293`
- `USER32!CharNextA` at `0x1800112da`
- `USER32!CharNextA` at `0x1800113b7`
- `USER32!CharNextA` at `0x18001125b`
- `USER32!CharNextA` at `0x180011270`
- `USER32!CharNextA` at `0x180011293`
- `USER32!CharNextA` at `0x1800112da`
- `USER32!CharNextA` at `0x1800113b7`
- `KERNEL32!lstrcmpiA` at `0x180011360`
- `KERNEL32!lstrcmpiA` at `0x180011360`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCSTR *this, char *a2, char **a3)
{
  LPSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  _BYTE *v8; // rax
  CHAR v9; // cl
  bool v10; // zf
  const CHAR *v11; // rcx
  CHAR v12; // al
  unsigned int v13; // eax
  LPSTR v14; // rax
  unsigned int v15; // ebx
  const CHAR *v17; // rbp
  errno_t v18; // eax
  LPCSTR v19; // rdi
  int v20; // ebx
  unsigned int v21; // edx
  const WCHAR *v22; // rdx
  const CHAR *i; // rax
  _DWORD v24[2]; // [rsp+20h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-50h]
  char Destination[32]; // [rsp+30h] [rbp-48h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v24[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v24[1] = v7;
  v8 = CoTaskMemAlloc((unsigned int)v7);
  pv = v8;
  if ( !v8 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *v8 = 0;
  *this = v4;
  v9 = *v4;
  if ( !*v4 )
  {
LABEL_15:
    v15 = 0;
    *a3 = v8;
    pv = 0;
    goto LABEL_16;
  }
  while ( 1 )
  {
    v10 = v9 == 37;
    v11 = v4;
    if ( !v10 )
      goto LABEL_12;
    v4 = CharNextA(v4);
    *this = v4;
    v12 = *v4;
    if ( *v4 != 37 )
      break;
    v11 = v4;
LABEL_12:
    v13 = (unsigned int)CharNextA(v11);
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v4, v13 - (_DWORD)v4) )
      goto LABEL_45;
LABEL_13:
    v14 = CharNextA(*this);
    *this = v14;
    v4 = v14;
    v9 = *v14;
    if ( !*v14 )
    {
      v8 = pv;
      goto LABEL_15;
    }
  }
  if ( !v4 )
    goto LABEL_34;
  v17 = 0;
  while ( v12 )
  {
    if ( v12 == 37 )
    {
      v17 = v4;
      break;
    }
    v4 = CharNextA(v4);
    v12 = *v4;
  }
  if ( !v17 )
  {
LABEL_34:
    v15 = -2147352567;
    goto LABEL_16;
  }
  if ( v17 - *this > 31 )
  {
    v15 = -2147467259;
    goto LABEL_16;
  }
  v18 = strncpy_s(Destination, 0x20u, *this, (int)v17 - *(_DWORD *)this);
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
  v20 = 0;
  if ( *((int *)v19 + 6) <= 0 )
    goto LABEL_34;
  while ( lstrcmpiA(*(LPCSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
    goto LABEL_34;
  if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
  {
    ATL::_AtlRaiseException(0xC000008C, v21);
    __debugbreak();
  }
  v22 = *(const WCHAR **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  if ( !v22 )
    goto LABEL_34;
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::AddString((ATL::CRegParser::CParseBuffer *)v24, v22) )
  {
    for ( i = *this; i != v17; *this = i )
      i = CharNextA(i);
    goto LABEL_13;
  }
LABEL_45:
  v15 = -2147024882;
LABEL_16:
  CoTaskMemFree(pv);
  return v15;
}

```

## disassembly

```asm
0x1800111c8  mov     [rsp+arg_8], rbx
0x1800111cd  mov     [rsp+arg_18], rbp
0x1800111d2  push    rsi
0x1800111d3  push    rdi
0x1800111d4  push    r14
0x1800111d6  sub     rsp, 60h
0x1800111da  mov     rax, cs:__security_cookie
0x1800111e1  xor     rax, rsp
0x1800111e4  mov     [rsp+78h+var_28], rax
0x1800111e9  mov     r14, r8
0x1800111ec  mov     rbx, rdx
0x1800111ef  mov     rsi, rcx
0x1800111f2  test    rdx, rdx
0x1800111f5  jz      loc_1800113EE
0x1800111fb  test    r8, r8
0x1800111fe  jz      loc_1800113EE
0x180011204  mov     qword ptr [r8], 0
0x18001120b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001120f  inc     rax
0x180011212  cmp     byte ptr [rdx+rax], 0
0x180011216  jnz     short loc_18001120F
0x180011218  add     eax, eax
0x18001121a  mov     [rsp+78h+var_58], 0
0x180011222  cmp     eax, 64h ; 'd'
0x180011225  mov     ecx, 3E8h
0x18001122a  cmovl   eax, ecx
0x18001122d  mov     ecx, eax; cb
0x18001122f  mov     [rsp+78h+var_54], eax
0x180011233  call    cs:__imp_CoTaskMemAlloc
0x180011239  mov     [rsp+78h+pv], rax
0x18001123e  test    rax, rax
0x180011241  jz      loc_1800113DE
0x180011247  mov     byte ptr [rax], 0
0x18001124a  mov     [rsi], rbx
0x18001124d  mov     cl, [rbx]
0x18001124f  test    cl, cl
0x180011251  jz      short loc_1800112AA
0x180011253  cmp     cl, 25h ; '%'
0x180011256  mov     rcx, rbx; lpsz
0x180011259  jnz     short loc_180011270
0x18001125b  call    cs:__imp_CharNextA
0x180011261  mov     rbx, rax
0x180011264  mov     [rsi], rax
0x180011267  mov     al, [rax]
0x180011269  cmp     al, 25h ; '%'
0x18001126b  jnz     short loc_1800112C6
0x18001126d  mov     rcx, rbx; lpsz
0x180011270  call    cs:__imp_CharNextA
0x180011276  mov     rdx, rbx; char *
0x180011279  lea     rcx, [rsp+78h+var_58]; this
0x18001127e  sub     eax, ebx
0x180011280  mov     r8d, eax; int
0x180011283  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBDH@Z; ATL::CRegParser::CParseBuffer::Append(char const *,int)
0x180011288  test    eax, eax
0x18001128a  jz      loc_1800113D4
0x180011290  mov     rcx, [rsi]; lpsz
0x180011293  call    cs:__imp_CharNextA
0x180011299  mov     [rsi], rax
0x18001129c  mov     rbx, rax
0x18001129f  mov     cl, [rax]
0x1800112a1  test    cl, cl
0x1800112a3  jnz     short loc_180011253
0x1800112a5  mov     rax, [rsp+78h+pv]
0x1800112aa  xor     ebx, ebx
0x1800112ac  mov     [r14], rax
0x1800112af  mov     [rsp+78h+pv], rbx
0x1800112b4  mov     rcx, [rsp+78h+pv]; pv
0x1800112b9  call    cs:__imp_CoTaskMemFree
0x1800112bf  mov     eax, ebx
0x1800112c1  jmp     loc_1800113F3
0x1800112c6  test    rbx, rbx
0x1800112c9  jz      loc_180011371
0x1800112cf  xor     ebp, ebp
0x1800112d1  jmp     short loc_1800112E5
0x1800112d3  cmp     al, 25h ; '%'
0x1800112d5  jz      short loc_1800112EB
0x1800112d7  mov     rcx, rbx; lpsz
0x1800112da  call    cs:__imp_CharNextA
0x1800112e0  mov     rbx, rax
0x1800112e3  mov     al, [rax]
0x1800112e5  test    al, al
0x1800112e7  jnz     short loc_1800112D3
0x1800112e9  jmp     short loc_1800112EE
0x1800112eb  mov     rbp, rbx
0x1800112ee  test    rbp, rbp
0x1800112f1  jz      short loc_180011371
0x1800112f3  mov     rax, rbp
0x1800112f6  sub     rax, [rsi]
0x1800112f9  cmp     rax, 1Fh
0x1800112fd  jg      loc_1800113CA
0x180011303  mov     r8, [rsi]; Source
0x180011306  lea     rcx, [rsp+78h+Destination]; Destination
0x18001130b  mov     eax, ebp
0x18001130d  mov     edx, 20h ; ' '; SizeInBytes
0x180011312  sub     eax, [rsi]
0x180011314  movsxd  r9, eax; MaxCount
0x180011317  call    cs:__imp_strncpy_s
0x18001131d  test    eax, eax
0x18001131f  jz      short loc_180011345
0x180011321  cmp     eax, 0Ch
0x180011324  jz      loc_180011436
0x18001132a  cmp     eax, 16h
0x18001132d  jz      loc_18001142B
0x180011333  cmp     eax, 22h ; '"'
0x180011336  jz      loc_18001142B
0x18001133c  cmp     eax, 50h ; 'P'
0x18001133f  jnz     loc_180011420
0x180011345  mov     rdi, [rsi+8]
0x180011349  xor     ebx, ebx
0x18001134b  cmp     [rdi+18h], ebx
0x18001134e  jle     short loc_180011371
0x180011350  mov     rcx, [rdi+8]
0x180011354  lea     rdx, [rsp+78h+Destination]; lpString2
0x180011359  movsxd  rax, ebx
0x18001135c  mov     rcx, [rcx+rax*8]; lpString1
0x180011360  call    cs:__imp_lstrcmpiA
0x180011366  test    eax, eax
0x180011368  jz      short loc_18001137B
0x18001136a  inc     ebx
0x18001136c  cmp     ebx, [rdi+18h]
0x18001136f  jl      short loc_180011350
0x180011371  mov     ebx, 80020009h
0x180011376  jmp     loc_1800112B4
0x18001137b  cmp     ebx, 0FFFFFFFFh
0x18001137e  jz      short loc_180011371
0x180011380  test    ebx, ebx
0x180011382  js      loc_180011415
0x180011388  cmp     ebx, [rdi+18h]
0x18001138b  jge     loc_180011415
0x180011391  mov     rax, [rdi+10h]
0x180011395  movsxd  rcx, ebx
0x180011398  mov     rdx, [rax+rcx*8]; lpWideCharStr
0x18001139c  test    rdx, rdx
0x18001139f  jz      short loc_180011371
0x1800113a1  lea     rcx, [rsp+78h+var_58]; this
0x1800113a6  call    ?AddString@CParseBuffer@CRegParser@ATL@@QEAAHPEBG@Z; ATL::CRegParser::CParseBuffer::AddString(ushort const *)
0x1800113ab  test    eax, eax
0x1800113ad  jz      short loc_1800113D4
0x1800113af  mov     rax, [rsi]
0x1800113b2  jmp     short loc_1800113C0
0x1800113b4  mov     rcx, rax; lpsz
0x1800113b7  call    cs:__imp_CharNextA
0x1800113bd  mov     [rsi], rax
0x1800113c0  cmp     rax, rbp
0x1800113c3  jnz     short loc_1800113B4
0x1800113c5  jmp     loc_180011290
0x1800113ca  mov     ebx, 80004005h
0x1800113cf  jmp     loc_1800112B4
0x1800113d4  mov     ebx, 8007000Eh
0x1800113d9  jmp     loc_1800112B4
0x1800113de  mov     rcx, rax; pv
0x1800113e1  call    cs:__imp_CoTaskMemFree
0x1800113e7  mov     eax, 8007000Eh
0x1800113ec  jmp     short loc_1800113F3
0x1800113ee  mov     eax, 80004003h
0x1800113f3  mov     rcx, [rsp+78h+var_28]
0x1800113f8  xor     rcx, rsp; StackCookie
0x1800113fb  call    __security_check_cookie
0x180011400  lea     r11, [rsp+78h+var_18]
0x180011405  mov     rbx, [r11+28h]
0x180011409  mov     rbp, [r11+38h]
0x18001140d  mov     rsp, r11
0x180011410  pop     r14
0x180011412  pop     rdi
0x180011413  pop     rsi
0x180011414  retn
0x180011415  mov     ecx, 0C000008Ch; unsigned int
0x18001141a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18001141f  int     3; Trap to Debugger
0x180011420  mov     ecx, 80004005h; int
0x180011425  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001142b  mov     ecx, 80070057h; int
0x180011430  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011436  mov     ecx, 8007000Eh; int
0x18001143b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
