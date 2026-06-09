# ATL::CRegObject::ResourceRegisterSz(ushort const *,ushort const *,ushort const *)

- ea: `0x1800125c4`
- end: `0x1800127d0`
- name: `?ResourceRegisterSz@CRegObject@ATL@@QEAAJPEBG00@Z`
- size: `524`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, LPCWCH lpWideCharStr, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180013070`

## callees

- `0x180003b70`
- `0x1800099ac`
- `0x180011800`
- `0x1800125c4`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `msvcrt!free` at `0x18001277c`
- `msvcrt!free` at `0x180012791`
- `msvcrt!free` at `0x18001277c`
- `msvcrt!free` at `0x180012791`
- `msvcrt!malloc` at `0x18001267e`
- `msvcrt!malloc` at `0x1800126f9`
- `msvcrt!malloc` at `0x18001267e`
- `msvcrt!malloc` at `0x1800126f9`
- `KERNEL32!WideCharToMultiByte` at `0x1800126bf`
- `KERNEL32!WideCharToMultiByte` at `0x18001273f`
- `KERNEL32!WideCharToMultiByte` at `0x1800126bf`
- `KERNEL32!WideCharToMultiByte` at `0x18001273f`

## string_xrefs

- `0x18001271d`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ResourceRegisterSz(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        LPCWCH lpWideCharStr,
        const unsigned __int16 *a4)
{
  _QWORD *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rsi
  unsigned __int64 v10; // rax
  void *v11; // rsp
  CHAR *v12; // rdi
  _QWORD *v13; // rax
  const char *v14; // rsi
  CHAR *p_lpMultiByteStr; // rdi
  _QWORD *v16; // rax
  const char *v17; // r9
  unsigned int v18; // edi
  void *v19; // rcx
  void *v21; // rcx
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-20h] BYREF
  int cbMultiByte; // [rsp+28h] [rbp-18h]
  LPCCH lpDefaultChar; // [rsp+30h] [rbp-10h]
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-8h]
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF

  if ( !lpWideCharStr )
    return 2147942487LL;
  v7 = 0;
  v8 = -1;
  do
    ++v8;
  while ( lpWideCharStr[v8] );
  v9 = 2LL * ((int)v8 + 1);
  if ( (unsigned __int64)(v9 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_16;
  if ( (int)v9 <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)v9, (unsigned __int64)a2) )
  {
    v10 = (int)v9 + 15LL;
    if ( v10 < (int)v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
    v12 = MultiByteStr;
  }
  else
  {
    if ( (unsigned __int64)~(__int64)(int)v9 < 0x10 )
      ATL::AtlThrowImpl(-2147024809);
    v13 = malloc((int)v9 + 16LL);
    if ( v13 )
    {
      *v13 = 0;
      v12 = (CHAR *)(v13 + 2);
      v7 = v13;
    }
    else
    {
      v12 = 0;
    }
  }
  if ( v12 )
  {
    lpUsedDefaultChar = 0;
    lpDefaultChar = 0;
    cbMultiByte = v9;
    *v12 = 0;
    v14 = (const char *)((unsigned __int64)v12
                       & -(__int64)(WideCharToMultiByte(
                                      3u,
                                      0,
                                      lpWideCharStr,
                                      -1,
                                      v12,
                                      cbMultiByte,
                                      lpDefaultChar,
                                      lpUsedDefaultChar) != 0));
  }
  else
  {
LABEL_16:
    v14 = 0;
  }
  if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x12, (unsigned __int64)a2) )
  {
    p_lpMultiByteStr = (CHAR *)&lpMultiByteStr;
  }
  else
  {
    v16 = malloc(0x22u);
    if ( v16 )
    {
      *v16 = v7;
      p_lpMultiByteStr = (CHAR *)(v16 + 2);
      v7 = v16;
    }
    else
    {
      p_lpMultiByteStr = 0;
    }
  }
  if ( p_lpMultiByteStr )
  {
    *p_lpMultiByteStr = 0;
    v17 = (const char *)((unsigned __int64)p_lpMultiByteStr
                       & -(__int64)(WideCharToMultiByte(3u, 0, L"REGISTRY", -1, p_lpMultiByteStr, 18, 0, 0) != 0));
  }
  else
  {
    v17 = 0;
  }
  if ( v14 && v17 )
  {
    v18 = ATL::CRegObject::RegisterFromResource(this, a2, v14, v17, 1);
    while ( v7 )
    {
      v19 = v7;
      v7 = (_QWORD *)*v7;
      free(v19);
    }
    return v18;
  }
  else
  {
    while ( v7 )
    {
      v21 = v7;
      v7 = (_QWORD *)*v7;
      free(v21);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800125c4  push    rbp
0x1800125c6  push    rbx
0x1800125c7  push    rsi
0x1800125c8  push    rdi
0x1800125c9  push    r12
0x1800125cb  push    r13
0x1800125cd  push    r14
0x1800125cf  push    r15
0x1800125d1  sub     rsp, 58h
0x1800125d5  lea     rbp, [rsp+40h]
0x1800125da  mov     rax, cs:__security_cookie
0x1800125e1  xor     rax, rbp
0x1800125e4  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x1800125e8  xor     r13d, r13d
0x1800125eb  mov     r14, r8
0x1800125ee  mov     r15, rdx
0x1800125f1  mov     r12, rcx
0x1800125f4  test    r8, r8
0x1800125f7  jz      loc_1800127A3
0x1800125fd  mov     ebx, r13d
0x180012600  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012604  inc     rax
0x180012607  cmp     [r8+rax*2], r13w
0x18001260c  jnz     short loc_180012604
0x18001260e  inc     eax
0x180012610  movsxd  rcx, eax
0x180012613  mov     eax, 80000000h
0x180012618  lea     rsi, [rcx+rcx]
0x18001261c  mov     ecx, 0FFFFFFFFh
0x180012621  add     rax, rsi
0x180012624  cmp     rax, rcx
0x180012627  ja      loc_1800126CF
0x18001262d  movsxd  rdi, esi
0x180012630  cmp     esi, 400h
0x180012636  jg      short loc_18001266A
0x180012638  mov     rcx, rdi; this
0x18001263b  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180012640  test    al, al
0x180012642  jz      short loc_18001266A
0x180012644  lea     rax, [rdi+0Fh]
0x180012648  cmp     rax, rdi
0x18001264b  ja      short loc_180012657
0x18001264d  mov     rax, 0FFFFFFFFFFFFFF0h
0x180012657  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001265b  call    _alloca_probe
0x180012660  sub     rsp, rax
0x180012663  lea     rdi, [rsp+90h+MultiByteStr]
0x180012668  jmp     short loc_180012698
0x18001266a  mov     rax, rdi
0x18001266d  not     rax
0x180012670  cmp     rax, 10h
0x180012674  jb      loc_1800127C5
0x18001267a  lea     rcx, [rdi+10h]; Size
0x18001267e  call    cs:__imp_malloc
0x180012684  test    rax, rax
0x180012687  jnz     short loc_18001268E
0x180012689  mov     rdi, r13
0x18001268c  jmp     short loc_180012698
0x18001268e  mov     [rax], r13
0x180012691  lea     rdi, [rax+10h]
0x180012695  mov     rbx, rax
0x180012698  test    rdi, rdi
0x18001269b  jz      short loc_1800126CF
0x18001269d  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800126a2  xor     edx, edx; dwFlags
0x1800126a4  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x1800126a9  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800126ad  mov     [rsp+90h+cbMultiByte], esi; cbMultiByte
0x1800126b1  mov     r8, r14; lpWideCharStr
0x1800126b4  mov     [rdi], r13b
0x1800126b7  lea     ecx, [rdx+3]; CodePage
0x1800126ba  mov     [rsp+90h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800126bf  call    cs:__imp_WideCharToMultiByte
0x1800126c5  neg     eax
0x1800126c7  sbb     rsi, rsi
0x1800126ca  and     rsi, rdi
0x1800126cd  jmp     short loc_1800126D2
0x1800126cf  mov     rsi, r13
0x1800126d2  mov     r14d, 12h
0x1800126d8  mov     ecx, r14d; this
0x1800126db  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800126e0  test    al, al
0x1800126e2  jz      short loc_1800126F4
0x1800126e4  mov     eax, dword ptr [rsp+90h+var_90]
0x1800126e7  sub     rsp, 20h
0x1800126eb  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x1800126f0  mov     eax, [rdi]
0x1800126f2  jmp     short loc_180012713
0x1800126f4  mov     ecx, 22h ; '"'; Size
0x1800126f9  call    cs:__imp_malloc
0x1800126ff  test    rax, rax
0x180012702  jnz     short loc_180012709
0x180012704  mov     rdi, r13
0x180012707  jmp     short loc_180012713
0x180012709  mov     [rax], rbx
0x18001270c  lea     rdi, [rax+10h]
0x180012710  mov     rbx, rax
0x180012713  test    rdi, rdi
0x180012716  jz      short loc_18001274F
0x180012718  mov     [rsp+0B0h+var_78], r13; lpUsedDefaultChar
0x18001271d  lea     r8, WideCharStr; "REGISTRY"
0x180012724  xor     edx, edx; dwFlags
0x180012726  mov     [rsp+0B0h+var_80], r13; lpDefaultChar
0x18001272b  mov     [rsp+0B0h+var_88], r14d; cbMultiByte
0x180012730  or      r9d, 0FFFFFFFFh; cchWideChar
0x180012734  mov     [rdi], r13b
0x180012737  mov     [rsp+0B0h+var_90], rdi; lpMultiByteStr
0x18001273c  lea     ecx, [rdx+3]; CodePage
0x18001273f  call    cs:__imp_WideCharToMultiByte
0x180012745  neg     eax
0x180012747  sbb     r9, r9
0x18001274a  and     r9, rdi
0x18001274d  jmp     short loc_180012752
0x18001274f  mov     r9, r13; char *
0x180012752  test    rsi, rsi
0x180012755  jz      short loc_180012797
0x180012757  test    r9, r9
0x18001275a  jz      short loc_180012797
0x18001275c  mov     r8, rsi; char *
0x18001275f  mov     dword ptr [rsp+0B0h+var_90], 1; int
0x180012767  mov     rdx, r15; unsigned __int16 *
0x18001276a  mov     rcx, r12; this
0x18001276d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)
0x180012772  mov     edi, eax
0x180012774  jmp     short loc_180012782
0x180012776  mov     rcx, rbx; Block
0x180012779  mov     rbx, [rbx]
0x18001277c  call    cs:__imp_free
0x180012782  test    rbx, rbx
0x180012785  jnz     short loc_180012776
0x180012787  mov     eax, edi
0x180012789  jmp     short loc_1800127A8
0x18001278b  mov     rcx, rbx; Block
0x18001278e  mov     rbx, [rbx]
0x180012791  call    cs:__imp_free
0x180012797  test    rbx, rbx
0x18001279a  jnz     short loc_18001278B
0x18001279c  mov     eax, 8007000Eh
0x1800127a1  jmp     short loc_1800127A8
0x1800127a3  mov     eax, 80070057h
0x1800127a8  mov     rcx, qword ptr [rbp+50h+MultiByteStr]
0x1800127ac  xor     rcx, rbp; StackCookie
0x1800127af  call    __security_check_cookie
0x1800127b4  lea     rsp, [rbp+18h]
0x1800127b8  pop     r15
0x1800127ba  pop     r14
0x1800127bc  pop     r13
0x1800127be  pop     r12
0x1800127c0  pop     rdi
0x1800127c1  pop     rsi
0x1800127c2  pop     rbx
0x1800127c3  pop     rbp
0x1800127c4  retn
0x1800127c5  mov     ecx, 80070057h; int
0x1800127ca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
