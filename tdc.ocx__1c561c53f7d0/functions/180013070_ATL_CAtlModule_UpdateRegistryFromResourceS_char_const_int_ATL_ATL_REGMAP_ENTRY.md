# ATL::CAtlModule::UpdateRegistryFromResourceS(char const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180013070`
- end: `0x180013524`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBDHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `1204`
- prototype: `int(ATL::CAtlModule *__hidden this, const char *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x180013540`

## callees

- `0x180001938`
- `0x180003b70`
- `0x1800099ac`
- `0x18000f0b0`
- `0x18000f500`
- `0x180010050`
- `0x1800125c4`
- `0x1800128e8`
- `0x180013070`
- `0x180014270`
- `0x180014300`
- `0x180015010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800132d8`
- `msvcrt!memcpy_s` at `0x1800132d8`
- `msvcrt!free` at `0x1800133da`
- `msvcrt!free` at `0x1800133f2`
- `msvcrt!free` at `0x18001347d`
- `msvcrt!free` at `0x18001349b`
- `msvcrt!free` at `0x1800134e3`
- `msvcrt!free` at `0x180013506`
- `msvcrt!free` at `0x1800133da`
- `msvcrt!free` at `0x1800133f2`
- `msvcrt!free` at `0x18001347d`
- `msvcrt!free` at `0x18001349b`
- `msvcrt!free` at `0x1800134e3`
- `msvcrt!free` at `0x180013506`
- `msvcrt!malloc` at `0x1800131cb`
- `msvcrt!malloc` at `0x180013413`
- `msvcrt!malloc` at `0x1800131cb`
- `msvcrt!malloc` at `0x180013413`
- `KERNEL32!GetModuleHandleA` at `0x180013270`
- `KERNEL32!GetModuleHandleA` at `0x180013270`
- `KERNEL32!GetModuleFileNameA` at `0x18001311f`
- `KERNEL32!GetModuleFileNameA` at `0x18001311f`
- `KERNEL32!MultiByteToWideChar` at `0x18001320e`
- `KERNEL32!MultiByteToWideChar` at `0x18001344e`
- `KERNEL32!MultiByteToWideChar` at `0x18001320e`
- `KERNEL32!MultiByteToWideChar` at `0x18001344e`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const char *a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  const unsigned __int16 *i; // rax
  int Error; // ebx
  HMODULE v10; // r14
  DWORD ModuleFileNameA; // eax
  __int64 v12; // rax
  int v13; // ecx
  unsigned __int64 v14; // rsi
  _QWORD *v15; // rbx
  __int64 v16; // rax
  void *v17; // rsp
  WCHAR *lpWideCharStr; // rdi
  _QWORD *v19; // rax
  __int64 v20; // rcx
  const unsigned __int16 *v21; // r15
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  int v26; // edi
  __int64 v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rsi
  __int64 v30; // rax
  void *v31; // rsp
  WCHAR *v32; // rdi
  void *v33; // rcx
  void *v34; // rcx
  _QWORD *v35; // rax
  const unsigned __int16 *v36; // r9
  unsigned int v37; // eax
  unsigned int v38; // edi
  void *v39; // rcx
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  WCHAR WideCharStr[4]; // [rsp+30h] [rbp+0h] BYREF
  __int128 v45; // [rsp+38h] [rbp+8h]
  int v46; // [rsp+48h] [rbp+18h]
  CHAR Filename[272]; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 Source[520]; // [rsp+170h] [rbp+140h] BYREF
  unsigned __int16 v49; // [rsp+580h] [rbp+550h] BYREF
  _BYTE Destination[1054]; // [rsp+582h] [rbp+552h] BYREF

  *(_QWORD *)WideCharStr = &ATL::CRegObject::`vftable';
  v46 = 0;
  v4 = a4;
  v45 = 0;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, i, v4[1]);
      v4 += 2;
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, WCHAR *))(*(_QWORD *)this + 40LL))(this, WideCharStr);
  if ( Error < 0 )
    goto LABEL_76;
  v10 = hInstance;
  ModuleFileNameA = GetModuleFileNameA(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameA )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_76:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
    return (unsigned int)Error;
  }
  if ( ModuleFileNameA == 260 )
  {
    Error = -2147024774;
    goto LABEL_76;
  }
  v12 = -1;
  do
    ++v12;
  while ( Filename[v12] );
  v13 = 2 * v12 + 2;
  if ( (unsigned __int64)(2LL * (int)v12 + 2147483650LL) > 0xFFFFFFFF )
  {
LABEL_72:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
    return 2147942414LL;
  }
  v14 = v13;
  v15 = 0;
  if ( v13 <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v13, 0xFFFFFFFF) )
  {
    v16 = v14 + 15;
    if ( v14 + 15 < v14 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = WideCharStr;
  }
  else
  {
    if ( ~v14 < 0x10 )
      goto LABEL_81;
    v19 = malloc(v14 + 16);
    if ( v19 )
    {
      *v19 = 0;
      lpWideCharStr = (WCHAR *)(v19 + 2);
      v15 = v19;
    }
    else
    {
      lpWideCharStr = 0;
    }
  }
  if ( !lpWideCharStr || (*lpWideCharStr = 0, !MultiByteToWideChar(3u, 0, Filename, -1, lpWideCharStr, v14 >> 1)) )
  {
    while ( v15 )
    {
      v43 = v15;
      v15 = (_QWORD *)*v15;
      free(v43);
    }
    goto LABEL_72;
  }
  v20 = 0;
  v21 = lpWideCharStr;
  do
  {
    if ( !*lpWideCharStr )
      break;
    Source[v20] = *lpWideCharStr;
    if ( *lpWideCharStr == 39 && (unsigned int)v20 < 0x206 )
    {
      LODWORD(v20) = v20 + 1;
      Source[(unsigned int)v20] = 39;
    }
    ++lpWideCharStr;
    v20 = (unsigned int)(v20 + 1);
  }
  while ( (unsigned int)v20 < 0x207 );
  Source[v20] = 0;
  if ( !v10 || v10 == GetModuleHandleA(0) )
  {
    v49 = 34;
    v23 = -1;
    do
      ++v23;
    while ( Source[v23] );
    if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v23 + 1)) )
    {
      while ( v15 )
      {
        v42 = v15;
        v15 = (_QWORD *)*v15;
        free(v42);
      }
      Error = -2147467259;
      goto LABEL_76;
    }
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)&Destination[2 * v24 - 2] );
    v25 = 2LL * (int)v24 + 2;
    *(_WORD *)&Destination[2 * (int)v24 - 2] = 34;
    if ( v25 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v25 - 2] = 0;
    v22 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module", &v49);
  }
  else
  {
    v22 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module", Source);
  }
  v26 = v22;
  if ( v22 < 0 )
  {
    while ( v15 )
    {
      v33 = v15;
      v15 = (_QWORD *)*v15;
      free(v33);
    }
    goto LABEL_53;
  }
  v26 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module_Raw", Source);
  if ( v26 < 0 )
  {
    while ( v15 )
    {
      v34 = v15;
      v15 = (_QWORD *)*v15;
      free(v34);
    }
LABEL_53:
    Error = v26;
    goto LABEL_76;
  }
  if ( !a2 )
    goto LABEL_71;
  v27 = -1;
  do
    ++v27;
  while ( a2[v27] );
  v28 = 2LL * ((int)v27 + 1);
  if ( (unsigned __int64)(v28 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_71;
  v29 = (int)v28;
  if ( (int)v28 > 1024
    || !ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)v28, 0xFFFFFFFF) )
  {
    if ( ~v29 >= 0x10 )
    {
      v35 = malloc(v29 + 16);
      if ( v35 )
      {
        *v35 = v15;
        v32 = (WCHAR *)(v35 + 2);
        v15 = v35;
      }
      else
      {
        v32 = 0;
      }
      goto LABEL_61;
    }
LABEL_81:
    ATL::AtlThrowImpl(-2147024809);
  }
  v30 = v29 + 15;
  if ( v29 + 15 < v29 )
    v30 = 0xFFFFFFFFFFFFFF0LL;
  v31 = alloca(v30 & 0xFFFFFFFFFFFFFFF0uLL);
  v32 = WideCharStr;
LABEL_61:
  if ( !v32 || (*v32 = 0, !MultiByteToWideChar(3u, 0, a2, -1, v32, v29 >> 1)) )
  {
LABEL_71:
    while ( v15 )
    {
      v41 = v15;
      v15 = (_QWORD *)*v15;
      free(v41);
    }
    goto LABEL_72;
  }
  if ( a3 )
    v37 = ATL::CRegObject::ResourceRegisterSz((ATL::CRegObject *)WideCharStr, v21, v32, v36);
  else
    v37 = ATL::CRegObject::ResourceUnregisterSz((ATL::CRegObject *)WideCharStr, v21, v32, v36);
  v38 = v37;
  while ( v15 )
  {
    v39 = v15;
    v15 = (_QWORD *)*v15;
    free(v39);
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
  return v38;
}

```

## disassembly

```asm
0x180013070  push    rbp
0x180013072  push    rsi
0x180013073  push    rdi
0x180013074  push    r12
0x180013076  push    r13
0x180013078  push    r14
0x18001307a  push    r15
0x18001307c  sub     rsp, 9B0h
0x180013083  lea     rbp, [rsp+30h]
0x180013088  mov     [rbp+9B0h+arg_10], rbx
0x18001308f  mov     rax, cs:__security_cookie
0x180013096  xor     rax, rbp
0x180013099  mov     [rbp+9B0h+var_40], rax
0x1800130a0  xor     r15d, r15d
0x1800130a3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800130aa  mov     qword ptr [rbp+9B0h+WideCharStr], rax
0x1800130ae  xorps   xmm0, xmm0
0x1800130b1  mov     [rbp+9B0h+var_998], r15d
0x1800130b5  mov     rbx, r9
0x1800130b8  mov     r13d, r8d
0x1800130bb  mov     r12, rdx
0x1800130be  mov     rdi, rcx
0x1800130c1  movdqu  [rbp+9B0h+var_9A8], xmm0
0x1800130c6  test    r9, r9
0x1800130c9  jz      short loc_1800130EC
0x1800130cb  mov     rax, [r9]
0x1800130ce  jmp     short loc_1800130E7
0x1800130d0  mov     r8, [rbx+8]; unsigned __int16 *
0x1800130d4  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x1800130d8  mov     rdx, rax; unsigned __int16 *
0x1800130db  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800130e0  lea     rbx, [rbx+10h]
0x1800130e4  mov     rax, [rbx]
0x1800130e7  test    rax, rax
0x1800130ea  jnz     short loc_1800130D0
0x1800130ec  mov     rax, [rdi]
0x1800130ef  lea     rdx, [rbp+9B0h+WideCharStr]
0x1800130f3  mov     rcx, rdi
0x1800130f6  mov     rax, [rax+28h]
0x1800130fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130ff  mov     ebx, eax
0x180013101  test    eax, eax
0x180013103  js      loc_1800134F3
0x180013109  mov     r14, cs:hInstance
0x180013110  lea     rdx, [rbp+9B0h+Filename]; lpFilename
0x180013114  mov     ebx, 104h
0x180013119  mov     rcx, r14; hModule
0x18001311c  mov     r8d, ebx; nSize
0x18001311f  call    cs:__imp_GetModuleFileNameA
0x180013125  test    eax, eax
0x180013127  jnz     short loc_180013135
0x180013129  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001312e  mov     ebx, eax
0x180013130  jmp     loc_1800134F3
0x180013135  cmp     eax, ebx
0x180013137  jnz     short loc_180013143
0x180013139  mov     ebx, 8007007Ah
0x18001313e  jmp     loc_1800134F3
0x180013143  lea     rcx, [rbp+9B0h+Filename]
0x180013147  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001314b  inc     rax
0x18001314e  cmp     [rcx+rax], r15b
0x180013152  jnz     short loc_18001314B
0x180013154  cdqe
0x180013156  mov     edx, 0FFFFFFFFh; unsigned __int64
0x18001315b  lea     rcx, ds:2[rax*2]
0x180013163  mov     eax, 80000000h
0x180013168  add     rax, rcx
0x18001316b  cmp     rax, rdx
0x18001316e  ja      loc_1800134A6
0x180013174  movsxd  rsi, ecx
0x180013177  mov     rbx, r15
0x18001317a  mov     rdi, 0FFFFFFFFFFFFFF0h
0x180013184  cmp     ecx, 400h
0x18001318a  jg      short loc_1800131B7
0x18001318c  mov     rcx, rsi; this
0x18001318f  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180013194  test    al, al
0x180013196  jz      short loc_1800131B7
0x180013198  lea     rax, [rsi+0Fh]
0x18001319c  cmp     rax, rsi
0x18001319f  ja      short loc_1800131A4
0x1800131a1  mov     rax, rdi
0x1800131a4  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800131a8  call    _alloca_probe
0x1800131ad  sub     rsp, rax
0x1800131b0  lea     rdi, [rsp+9E0h+WideCharStr]
0x1800131b5  jmp     short loc_1800131E5
0x1800131b7  mov     rax, rsi
0x1800131ba  not     rax
0x1800131bd  cmp     rax, 10h
0x1800131c1  jb      loc_180013519
0x1800131c7  lea     rcx, [rsi+10h]; Size
0x1800131cb  call    cs:__imp_malloc
0x1800131d1  test    rax, rax
0x1800131d4  jnz     short loc_1800131DB
0x1800131d6  mov     rdi, r15
0x1800131d9  jmp     short loc_1800131E5
0x1800131db  mov     [rax], r15
0x1800131de  lea     rdi, [rax+10h]
0x1800131e2  mov     rbx, rax
0x1800131e5  test    rdi, rdi
0x1800131e8  jz      loc_18001350C
0x1800131ee  shr     rsi, 1
0x1800131f1  lea     r8, [rbp+9B0h+Filename]; lpMultiByteStr
0x1800131f5  mov     [rsp+9E0h+cchWideChar], esi; cchWideChar
0x1800131f9  xor     edx, edx; dwFlags
0x1800131fb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800131ff  mov     [rdi], r15w
0x180013203  mov     r9d, esi; cbMultiByte
0x180013206  mov     [rsp+9E0h+lpWideCharStr], rdi; lpWideCharStr
0x18001320b  lea     ecx, [rsi+4]; CodePage
0x18001320e  call    cs:__imp_MultiByteToWideChar
0x180013214  test    eax, eax
0x180013216  jz      loc_18001350C
0x18001321c  mov     ecx, r15d
0x18001321f  lea     r9d, [rsi+28h]
0x180013223  mov     r15, rdi
0x180013226  xor     r8d, r8d
0x180013229  movzx   edx, word ptr [rdi]
0x18001322c  test    dx, dx
0x18001322f  jz      short loc_180013260
0x180013231  mov     [rbp+rcx*2+9B0h+Source], dx
0x180013239  cmp     [rdi], r9w
0x18001323d  jnz     short loc_180013252
0x18001323f  cmp     ecx, 206h
0x180013245  jnb     short loc_180013252
0x180013247  inc     ecx
0x180013249  mov     [rbp+rcx*2+9B0h+Source], r9w
0x180013252  add     rdi, 2
0x180013256  inc     ecx
0x180013258  cmp     ecx, 207h
0x18001325e  jb      short loc_180013229
0x180013260  mov     [rbp+rcx*2+9B0h+Source], r8w
0x180013269  test    r14, r14
0x18001326c  jz      short loc_18001329A
0x18001326e  xor     ecx, ecx; lpModuleName
0x180013270  call    cs:__imp_GetModuleHandleA
0x180013276  cmp     r14, rax
0x180013279  jz      short loc_18001329A
0x18001327b  lea     r8, [rbp+9B0h+Source]; unsigned __int16 *
0x180013282  lea     rdx, aModule; "Module"
0x180013289  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x18001328d  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180013292  xor     r14d, r14d
0x180013295  jmp     loc_180013339
0x18001329a  mov     edi, 22h ; '"'
0x18001329f  lea     rcx, [rbp+9B0h+Source]
0x1800132a6  mov     [rbp+9B0h+var_460], di
0x1800132ad  mov     rax, rsi
0x1800132b0  xor     r14d, r14d
0x1800132b3  inc     rax
0x1800132b6  cmp     [rcx+rax*2], r14w
0x1800132bb  jnz     short loc_1800132B3
0x1800132bd  inc     eax
0x1800132bf  lea     r8, [rbp+9B0h+Source]; Source
0x1800132c6  movsxd  r9, eax
0x1800132c9  lea     rcx, [rbp+9B0h+Destination]; Destination
0x1800132d0  add     r9, r9; SourceSize
0x1800132d3  mov     edx, 414h; DestinationSize
0x1800132d8  call    cs:__imp_memcpy_s
0x1800132de  test    eax, eax
0x1800132e0  jnz     loc_1800134E9
0x1800132e6  lea     rcx, [rbp+9B0h+var_460]
0x1800132ed  mov     rax, rsi
0x1800132f0  inc     rax
0x1800132f3  cmp     [rcx+rax*2], r14w
0x1800132f8  jnz     short loc_1800132F0
0x1800132fa  cdqe
0x1800132fc  lea     rcx, ds:2[rax*2]
0x180013304  mov     [rbp+rax*2+9B0h+var_460], di
0x18001330c  cmp     rcx, 418h
0x180013313  jnb     loc_180013513
0x180013319  mov     [rbp+rcx+9B0h+var_460], r14w
0x180013322  lea     r8, [rbp+9B0h+var_460]; unsigned __int16 *
0x180013329  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x18001332d  lea     rdx, aModule; "Module"
0x180013334  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180013339  mov     edi, eax
0x18001333b  test    eax, eax
0x18001333d  js      loc_1800133E0
0x180013343  lea     r8, [rbp+9B0h+Source]; unsigned __int16 *
0x18001334a  lea     rdx, aModuleRaw; "Module_Raw"
0x180013351  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x180013355  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001335a  mov     edi, eax
0x18001335c  test    eax, eax
0x18001335e  js      loc_1800133F8
0x180013364  test    r12, r12
0x180013367  jz      loc_1800134A1
0x18001336d  mov     rax, rsi
0x180013370  inc     rax
0x180013373  cmp     [r12+rax], r14b
0x180013377  jnz     short loc_180013370
0x180013379  inc     eax
0x18001337b  mov     edx, 0FFFFFFFFh; unsigned __int64
0x180013380  movsxd  rcx, eax
0x180013383  mov     eax, 80000000h
0x180013388  add     rcx, rcx
0x18001338b  add     rax, rcx
0x18001338e  cmp     rax, rdx
0x180013391  ja      loc_1800134A1
0x180013397  movsxd  rsi, ecx
0x18001339a  cmp     ecx, 400h
0x1800133a0  jg      short loc_1800133FF
0x1800133a2  mov     rcx, rsi; this
0x1800133a5  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800133aa  test    al, al
0x1800133ac  jz      short loc_1800133FF
0x1800133ae  lea     rax, [rsi+0Fh]
0x1800133b2  cmp     rax, rsi
0x1800133b5  ja      short loc_1800133C1
0x1800133b7  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800133c1  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800133c5  call    _alloca_probe
0x1800133ca  sub     rsp, rax
0x1800133cd  lea     rdi, [rsp+9E0h+WideCharStr]
0x1800133d2  jmp     short loc_18001342D
0x1800133d4  mov     rcx, rbx; Block
0x1800133d7  mov     rbx, [rbx]
0x1800133da  call    cs:__imp_free
0x1800133e0  test    rbx, rbx
0x1800133e3  jnz     short loc_1800133D4
0x1800133e5  mov     ebx, edi
0x1800133e7  jmp     loc_1800134F3
0x1800133ec  mov     rcx, rbx; Block
0x1800133ef  mov     rbx, [rbx]
0x1800133f2  call    cs:__imp_free
0x1800133f8  test    rbx, rbx
0x1800133fb  jnz     short loc_1800133EC
0x1800133fd  jmp     short loc_1800133E5
0x1800133ff  mov     rax, rsi
0x180013402  not     rax
0x180013405  cmp     rax, 10h
0x180013409  jb      loc_180013519
0x18001340f  lea     rcx, [rsi+10h]; Size
0x180013413  call    cs:__imp_malloc
0x180013419  test    rax, rax
0x18001341c  jnz     short loc_180013423
0x18001341e  mov     rdi, r14
0x180013421  jmp     short loc_18001342D
0x180013423  mov     [rax], rbx
0x180013426  lea     rdi, [rax+10h]
0x18001342a  mov     rbx, rax
0x18001342d  test    rdi, rdi
0x180013430  jz      short loc_1800134A1
0x180013432  xor     edx, edx; dwFlags
0x180013434  shr     rsi, 1
0x180013437  mov     [rsp+9E0h+cchWideChar], esi; cchWideChar
0x18001343b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001343f  mov     r8, r12; lpMultiByteStr
0x180013442  mov     [rdi], r14w
0x180013446  mov     [rsp+9E0h+lpWideCharStr], rdi; lpWideCharStr
0x18001344b  lea     ecx, [rdx+3]; CodePage
0x18001344e  call    cs:__imp_MultiByteToWideChar
0x180013454  test    eax, eax
0x180013456  jz      short loc_1800134A1
0x180013458  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x18001345c  mov     r8, rdi; lpWideCharStr
0x18001345f  mov     rdx, r15; unsigned __int16 *
0x180013462  test    r13d, r13d
0x180013465  jz      short loc_18001346E
0x180013467  call    ?ResourceRegisterSz@CRegObject@ATL@@QEAAJPEBG00@Z; ATL::CRegObject::ResourceRegisterSz(ushort const *,ushort const *,ushort const *)
0x18001346c  jmp     short loc_180013473
0x18001346e  call    ?ResourceUnregisterSz@CRegObject@ATL@@QEAAJPEBG00@Z; ATL::CRegObject::ResourceUnregisterSz(ushort const *,ushort const *,ushort const *)
0x180013473  mov     edi, eax
0x180013475  jmp     short loc_180013483
0x180013477  mov     rcx, rbx; Block
0x18001347a  mov     rbx, [rbx]
0x18001347d  call    cs:__imp_free
0x180013483  test    rbx, rbx
0x180013486  jnz     short loc_180013477
0x180013488  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x18001348c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180013491  mov     eax, edi
0x180013493  jmp     short loc_1800134B4
0x180013495  mov     rcx, rbx; Block
0x180013498  mov     rbx, [rbx]
0x18001349b  call    cs:__imp_free
0x1800134a1  test    rbx, rbx
0x1800134a4  jnz     short loc_180013495
0x1800134a6  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x1800134aa  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800134af  mov     eax, 8007000Eh
0x1800134b4  mov     rcx, [rbp+9B0h+var_40]
0x1800134bb  xor     rcx, rbp; StackCookie
0x1800134be  call    __security_check_cookie
0x1800134c3  mov     rbx, [rbp+9B0h+arg_10]
0x1800134ca  lea     rsp, [rbp+980h]
0x1800134d1  pop     r15
0x1800134d3  pop     r14
0x1800134d5  pop     r13
0x1800134d7  pop     r12
0x1800134d9  pop     rdi
0x1800134da  pop     rsi
0x1800134db  pop     rbp
0x1800134dc  retn
0x1800134dd  mov     rcx, rbx; Block
0x1800134e0  mov     rbx, [rbx]
0x1800134e3  call    cs:__imp_free
  ... truncated ...
```
