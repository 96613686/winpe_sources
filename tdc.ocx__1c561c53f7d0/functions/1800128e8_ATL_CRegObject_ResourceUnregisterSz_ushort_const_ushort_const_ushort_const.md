# ATL::CRegObject::ResourceUnregisterSz(ushort const *,ushort const *,ushort const *)

- ea: `0x1800128e8`
- end: `0x180012af1`
- name: `?ResourceUnregisterSz@CRegObject@ATL@@QEAAJPEBG00@Z`
- size: `521`
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
- `0x1800128e8`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `msvcrt!free` at `0x180012a9d`
- `msvcrt!free` at `0x180012ab2`
- `msvcrt!free` at `0x180012a9d`
- `msvcrt!free` at `0x180012ab2`
- `msvcrt!malloc` at `0x1800129a2`
- `msvcrt!malloc` at `0x180012a1d`
- `msvcrt!malloc` at `0x1800129a2`
- `msvcrt!malloc` at `0x180012a1d`
- `KERNEL32!WideCharToMultiByte` at `0x1800129e3`
- `KERNEL32!WideCharToMultiByte` at `0x180012a63`
- `KERNEL32!WideCharToMultiByte` at `0x1800129e3`
- `KERNEL32!WideCharToMultiByte` at `0x180012a63`

## string_xrefs

- `0x180012a41`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ResourceUnregisterSz(
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
    v18 = ATL::CRegObject::RegisterFromResource(this, a2, v14, v17, 0);
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
0x1800128e8  push    rbp
0x1800128ea  push    rbx
0x1800128eb  push    rsi
0x1800128ec  push    rdi
0x1800128ed  push    r12
0x1800128ef  push    r13
0x1800128f1  push    r14
0x1800128f3  push    r15
0x1800128f5  sub     rsp, 58h
0x1800128f9  lea     rbp, [rsp+40h]
0x1800128fe  mov     rax, cs:__security_cookie
0x180012905  xor     rax, rbp
0x180012908  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x18001290c  xor     r13d, r13d
0x18001290f  mov     r14, r8
0x180012912  mov     r15, rdx
0x180012915  mov     r12, rcx
0x180012918  test    r8, r8
0x18001291b  jz      loc_180012AC4
0x180012921  mov     ebx, r13d
0x180012924  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012928  inc     rax
0x18001292b  cmp     [r8+rax*2], r13w
0x180012930  jnz     short loc_180012928
0x180012932  inc     eax
0x180012934  movsxd  rcx, eax
0x180012937  mov     eax, 80000000h
0x18001293c  lea     rsi, [rcx+rcx]
0x180012940  mov     ecx, 0FFFFFFFFh
0x180012945  add     rax, rsi
0x180012948  cmp     rax, rcx
0x18001294b  ja      loc_1800129F3
0x180012951  movsxd  rdi, esi
0x180012954  cmp     esi, 400h
0x18001295a  jg      short loc_18001298E
0x18001295c  mov     rcx, rdi; this
0x18001295f  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180012964  test    al, al
0x180012966  jz      short loc_18001298E
0x180012968  lea     rax, [rdi+0Fh]
0x18001296c  cmp     rax, rdi
0x18001296f  ja      short loc_18001297B
0x180012971  mov     rax, 0FFFFFFFFFFFFFF0h
0x18001297b  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001297f  call    _alloca_probe
0x180012984  sub     rsp, rax
0x180012987  lea     rdi, [rsp+90h+MultiByteStr]
0x18001298c  jmp     short loc_1800129BC
0x18001298e  mov     rax, rdi
0x180012991  not     rax
0x180012994  cmp     rax, 10h
0x180012998  jb      loc_180012AE6
0x18001299e  lea     rcx, [rdi+10h]; Size
0x1800129a2  call    cs:__imp_malloc
0x1800129a8  test    rax, rax
0x1800129ab  jnz     short loc_1800129B2
0x1800129ad  mov     rdi, r13
0x1800129b0  jmp     short loc_1800129BC
0x1800129b2  mov     [rax], r13
0x1800129b5  lea     rdi, [rax+10h]
0x1800129b9  mov     rbx, rax
0x1800129bc  test    rdi, rdi
0x1800129bf  jz      short loc_1800129F3
0x1800129c1  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800129c6  xor     edx, edx; dwFlags
0x1800129c8  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x1800129cd  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800129d1  mov     [rsp+90h+cbMultiByte], esi; cbMultiByte
0x1800129d5  mov     r8, r14; lpWideCharStr
0x1800129d8  mov     [rdi], r13b
0x1800129db  lea     ecx, [rdx+3]; CodePage
0x1800129de  mov     [rsp+90h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800129e3  call    cs:__imp_WideCharToMultiByte
0x1800129e9  neg     eax
0x1800129eb  sbb     rsi, rsi
0x1800129ee  and     rsi, rdi
0x1800129f1  jmp     short loc_1800129F6
0x1800129f3  mov     rsi, r13
0x1800129f6  mov     r14d, 12h
0x1800129fc  mov     ecx, r14d; this
0x1800129ff  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180012a04  test    al, al
0x180012a06  jz      short loc_180012A18
0x180012a08  mov     eax, dword ptr [rsp+90h+var_90]
0x180012a0b  sub     rsp, 20h
0x180012a0f  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x180012a14  mov     eax, [rdi]
0x180012a16  jmp     short loc_180012A37
0x180012a18  mov     ecx, 22h ; '"'; Size
0x180012a1d  call    cs:__imp_malloc
0x180012a23  test    rax, rax
0x180012a26  jnz     short loc_180012A2D
0x180012a28  mov     rdi, r13
0x180012a2b  jmp     short loc_180012A37
0x180012a2d  mov     [rax], rbx
0x180012a30  lea     rdi, [rax+10h]
0x180012a34  mov     rbx, rax
0x180012a37  test    rdi, rdi
0x180012a3a  jz      short loc_180012A73
0x180012a3c  mov     [rsp+0B0h+var_78], r13; lpUsedDefaultChar
0x180012a41  lea     r8, WideCharStr; "REGISTRY"
0x180012a48  xor     edx, edx; dwFlags
0x180012a4a  mov     [rsp+0B0h+var_80], r13; lpDefaultChar
0x180012a4f  mov     [rsp+0B0h+var_88], r14d; cbMultiByte
0x180012a54  or      r9d, 0FFFFFFFFh; cchWideChar
0x180012a58  mov     [rdi], r13b
0x180012a5b  mov     [rsp+0B0h+var_90], rdi; lpMultiByteStr
0x180012a60  lea     ecx, [rdx+3]; CodePage
0x180012a63  call    cs:__imp_WideCharToMultiByte
0x180012a69  neg     eax
0x180012a6b  sbb     r9, r9
0x180012a6e  and     r9, rdi
0x180012a71  jmp     short loc_180012A76
0x180012a73  mov     r9, r13; char *
0x180012a76  test    rsi, rsi
0x180012a79  jz      short loc_180012AB8
0x180012a7b  test    r9, r9
0x180012a7e  jz      short loc_180012AB8
0x180012a80  mov     r8, rsi; char *
0x180012a83  mov     dword ptr [rsp+0B0h+var_90], r13d; int
0x180012a88  mov     rdx, r15; unsigned __int16 *
0x180012a8b  mov     rcx, r12; this
0x180012a8e  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)
0x180012a93  mov     edi, eax
0x180012a95  jmp     short loc_180012AA3
0x180012a97  mov     rcx, rbx; Block
0x180012a9a  mov     rbx, [rbx]
0x180012a9d  call    cs:__imp_free
0x180012aa3  test    rbx, rbx
0x180012aa6  jnz     short loc_180012A97
0x180012aa8  mov     eax, edi
0x180012aaa  jmp     short loc_180012AC9
0x180012aac  mov     rcx, rbx; Block
0x180012aaf  mov     rbx, [rbx]
0x180012ab2  call    cs:__imp_free
0x180012ab8  test    rbx, rbx
0x180012abb  jnz     short loc_180012AAC
0x180012abd  mov     eax, 8007000Eh
0x180012ac2  jmp     short loc_180012AC9
0x180012ac4  mov     eax, 80070057h
0x180012ac9  mov     rcx, qword ptr [rbp+50h+MultiByteStr]
0x180012acd  xor     rcx, rbp; StackCookie
0x180012ad0  call    __security_check_cookie
0x180012ad5  lea     rsp, [rbp+18h]
0x180012ad9  pop     r15
0x180012adb  pop     r14
0x180012add  pop     r13
0x180012adf  pop     r12
0x180012ae1  pop     rdi
0x180012ae2  pop     rsi
0x180012ae3  pop     rbx
0x180012ae4  pop     rbp
0x180012ae5  retn
0x180012ae6  mov     ecx, 80070057h; int
0x180012aeb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
