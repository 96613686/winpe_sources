# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180012cac`
- end: `0x180013067`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `955`
- prototype: `int(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x180012c80`
- `0x180013530`

## callees

- `0x180001938`
- `0x180003b70`
- `0x1800099ac`
- `0x18000f0b0`
- `0x18000f500`
- `0x180010050`
- `0x1800124b4`
- `0x1800127d8`
- `0x180012cac`
- `0x180014270`
- `0x180014300`
- `0x180015010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012f04`
- `msvcrt!memcpy_s` at `0x180012f04`
- `msvcrt!free` at `0x180012fa2`
- `msvcrt!free` at `0x180012fb7`
- `msvcrt!free` at `0x180012fd3`
- `msvcrt!free` at `0x180012ff1`
- `msvcrt!free` at `0x180013014`
- `msvcrt!free` at `0x180012fa2`
- `msvcrt!free` at `0x180012fb7`
- `msvcrt!free` at `0x180012fd3`
- `msvcrt!free` at `0x180012ff1`
- `msvcrt!free` at `0x180013014`
- `msvcrt!malloc` at `0x180012e0b`
- `msvcrt!malloc` at `0x180012e0b`
- `KERNEL32!GetModuleHandleA` at `0x180012eaf`
- `KERNEL32!GetModuleHandleA` at `0x180012eaf`
- `KERNEL32!GetModuleFileNameA` at `0x180012d59`
- `KERNEL32!GetModuleFileNameA` at `0x180012d59`
- `KERNEL32!MultiByteToWideChar` at `0x180012e4d`
- `KERNEL32!MultiByteToWideChar` at `0x180012e4d`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  const unsigned __int16 *i; // rax
  int Error; // ebx
  HMODULE v10; // r15
  DWORD ModuleFileNameA; // eax
  __int64 v12; // r14
  __int64 v13; // rax
  int v14; // ecx
  unsigned __int64 v15; // rsi
  _QWORD *v16; // rbx
  __int64 v17; // rax
  void *v18; // rsp
  WCHAR *lpWideCharStr; // rdi
  _QWORD *v20; // rax
  __int64 v21; // rcx
  const unsigned __int16 *v22; // rsi
  unsigned __int16 *v23; // r8
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  int v26; // edi
  const unsigned __int16 *v27; // r9
  unsigned int v28; // eax
  void *v29; // rcx
  void *v30; // rcx
  unsigned int v31; // edi
  void *v32; // rcx
  void *v34; // rcx
  void *v35; // rcx
  WCHAR WideCharStr[4]; // [rsp+30h] [rbp+0h] BYREF
  __int128 v37; // [rsp+38h] [rbp+8h]
  int v38; // [rsp+48h] [rbp+18h]
  CHAR Filename[272]; // [rsp+60h] [rbp+30h] BYREF
  unsigned __int16 Source[520]; // [rsp+170h] [rbp+140h] BYREF
  unsigned __int16 v41; // [rsp+580h] [rbp+550h] BYREF
  _BYTE Destination[1054]; // [rsp+582h] [rbp+552h] BYREF

  *(_QWORD *)WideCharStr = &ATL::CRegObject::`vftable';
  v38 = 0;
  v4 = a4;
  v37 = 0;
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
    goto LABEL_57;
  v10 = hInstance;
  ModuleFileNameA = GetModuleFileNameA(hInstance, Filename, 0x104u);
  if ( !ModuleFileNameA )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_57:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
    return (unsigned int)Error;
  }
  if ( ModuleFileNameA == 260 )
  {
    Error = -2147024774;
    goto LABEL_57;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( Filename[v13] );
  v14 = 2 * v13 + 2;
  if ( (unsigned __int64)(2LL * (int)v13 + 2147483650LL) > 0xFFFFFFFF )
    goto LABEL_60;
  v15 = v14;
  v16 = 0;
  if ( v14 <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v14, 0xFFFFFFFF) )
  {
    v17 = v15 + 15;
    if ( v15 + 15 < v15 )
      v17 = 0xFFFFFFFFFFFFFF0LL;
    v18 = alloca(v17 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = WideCharStr;
  }
  else
  {
    if ( ~v15 < 0x10 )
      ATL::AtlThrowImpl(-2147024809);
    v20 = malloc(v15 + 16);
    if ( v20 )
    {
      *v20 = 0;
      lpWideCharStr = (WCHAR *)(v20 + 2);
      v16 = v20;
    }
    else
    {
      lpWideCharStr = 0;
    }
  }
  if ( !lpWideCharStr || (*lpWideCharStr = 0, !MultiByteToWideChar(3u, 0, Filename, -1, lpWideCharStr, v15 >> 1)) )
  {
    while ( v16 )
    {
      v35 = v16;
      v16 = (_QWORD *)*v16;
      free(v35);
    }
LABEL_60:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
    return 2147942414LL;
  }
  v21 = 0;
  v22 = lpWideCharStr;
  do
  {
    if ( !*lpWideCharStr )
      break;
    Source[v21] = *lpWideCharStr;
    if ( *lpWideCharStr == 39 && (unsigned int)v21 < 0x206 )
    {
      LODWORD(v21) = v21 + 1;
      Source[(unsigned int)v21] = 39;
    }
    ++lpWideCharStr;
    v21 = (unsigned int)(v21 + 1);
  }
  while ( (unsigned int)v21 < 0x207 );
  Source[v21] = 0;
  if ( !v10 || v10 == GetModuleHandleA(0) )
  {
    v41 = 34;
    v24 = -1;
    do
      ++v24;
    while ( Source[v24] );
    if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v24 + 1)) )
    {
      while ( v16 )
      {
        v34 = v16;
        v16 = (_QWORD *)*v16;
        free(v34);
      }
      Error = -2147467259;
      goto LABEL_57;
    }
    do
      ++v12;
    while ( *(_WORD *)&Destination[2 * v12 - 2] );
    v25 = 2LL * (int)v12 + 2;
    *(_WORD *)&Destination[2 * (int)v12 - 2] = 34;
    if ( v25 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v25 - 2] = 0;
    v23 = &v41;
  }
  else
  {
    v23 = Source;
  }
  v26 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module", v23);
  if ( v26 < 0 )
  {
    while ( v16 )
    {
      v29 = v16;
      v16 = (_QWORD *)*v16;
      free(v29);
    }
    goto LABEL_45;
  }
  v26 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)WideCharStr, L"Module_Raw", Source);
  if ( v26 < 0 )
  {
    while ( v16 )
    {
      v30 = v16;
      v16 = (_QWORD *)*v16;
      free(v30);
    }
LABEL_45:
    Error = v26;
    goto LABEL_57;
  }
  if ( a3 )
    v28 = ATL::CRegObject::ResourceRegister((ATL::CRegObject *)WideCharStr, v22, a2, v27);
  else
    v28 = ATL::CRegObject::ResourceUnregister((ATL::CRegObject *)WideCharStr, v22, a2, v27);
  v31 = v28;
  while ( v16 )
  {
    v32 = v16;
    v16 = (_QWORD *)*v16;
    free(v32);
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)WideCharStr);
  return v31;
}

```

## disassembly

```asm
0x180012cac  push    rbp
0x180012cae  push    rsi
0x180012caf  push    rdi
0x180012cb0  push    r12
0x180012cb2  push    r13
0x180012cb4  push    r14
0x180012cb6  push    r15
0x180012cb8  sub     rsp, 9B0h
0x180012cbf  lea     rbp, [rsp+30h]
0x180012cc4  mov     [rbp+9B0h+arg_10], rbx
0x180012ccb  mov     rax, cs:__security_cookie
0x180012cd2  xor     rax, rbp
0x180012cd5  mov     [rbp+9B0h+var_40], rax
0x180012cdc  xor     esi, esi
0x180012cde  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180012ce5  mov     qword ptr [rbp+9B0h+WideCharStr], rax
0x180012ce9  xorps   xmm0, xmm0
0x180012cec  mov     [rbp+9B0h+var_998], esi
0x180012cef  mov     rbx, r9
0x180012cf2  mov     r13d, r8d
0x180012cf5  mov     r12d, edx
0x180012cf8  mov     rdi, rcx
0x180012cfb  movdqu  [rbp+9B0h+var_9A8], xmm0
0x180012d00  test    r9, r9
0x180012d03  jz      short loc_180012D26
0x180012d05  mov     rax, [r9]
0x180012d08  jmp     short loc_180012D21
0x180012d0a  mov     r8, [rbx+8]; unsigned __int16 *
0x180012d0e  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x180012d12  mov     rdx, rax; unsigned __int16 *
0x180012d15  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180012d1a  lea     rbx, [rbx+10h]
0x180012d1e  mov     rax, [rbx]
0x180012d21  test    rax, rax
0x180012d24  jnz     short loc_180012D0A
0x180012d26  mov     rax, [rdi]
0x180012d29  lea     rdx, [rbp+9B0h+WideCharStr]
0x180012d2d  mov     rcx, rdi
0x180012d30  mov     rax, [rax+28h]
0x180012d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d39  mov     ebx, eax
0x180012d3b  test    eax, eax
0x180012d3d  js      loc_180013001
0x180012d43  mov     r15, cs:hInstance
0x180012d4a  lea     rdx, [rbp+9B0h+Filename]; lpFilename
0x180012d4e  mov     ebx, 104h
0x180012d53  mov     rcx, r15; hModule
0x180012d56  mov     r8d, ebx; nSize
0x180012d59  call    cs:__imp_GetModuleFileNameA
0x180012d5f  xor     r8d, r8d
0x180012d62  test    eax, eax
0x180012d64  jnz     short loc_180012D72
0x180012d66  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180012d6b  mov     ebx, eax
0x180012d6d  jmp     loc_180013001
0x180012d72  cmp     eax, ebx
0x180012d74  jnz     short loc_180012D80
0x180012d76  mov     ebx, 8007007Ah
0x180012d7b  jmp     loc_180013001
0x180012d80  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012d84  lea     rcx, [rbp+9B0h+Filename]
0x180012d88  mov     rax, r14
0x180012d8b  inc     rax
0x180012d8e  cmp     [rcx+rax], r8b
0x180012d92  jnz     short loc_180012D8B
0x180012d94  cdqe
0x180012d96  mov     edx, 0FFFFFFFFh; unsigned __int64
0x180012d9b  lea     rcx, ds:2[rax*2]
0x180012da3  mov     eax, 80000000h
0x180012da8  add     rax, rcx
0x180012dab  cmp     rax, rdx
0x180012dae  ja      loc_18001301F
0x180012db4  movsxd  rsi, ecx
0x180012db7  mov     rbx, r8
0x180012dba  cmp     ecx, 400h
0x180012dc0  jg      short loc_180012DF7
0x180012dc2  mov     rcx, rsi; this
0x180012dc5  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180012dca  xor     r8d, r8d
0x180012dcd  test    al, al
0x180012dcf  jz      short loc_180012DF7
0x180012dd1  lea     rax, [rsi+0Fh]
0x180012dd5  cmp     rax, rsi
0x180012dd8  ja      short loc_180012DE4
0x180012dda  mov     rax, 0FFFFFFFFFFFFFF0h
0x180012de4  and     rax, 0FFFFFFFFFFFFFFF0h
0x180012de8  call    _alloca_probe
0x180012ded  sub     rsp, rax
0x180012df0  lea     rdi, [rsp+9E0h+WideCharStr]
0x180012df5  jmp     short loc_180012E28
0x180012df7  mov     rax, rsi
0x180012dfa  not     rax
0x180012dfd  cmp     rax, 10h
0x180012e01  jb      loc_18001305C
0x180012e07  lea     rcx, [rsi+10h]; Size
0x180012e0b  call    cs:__imp_malloc
0x180012e11  xor     r8d, r8d
0x180012e14  test    rax, rax
0x180012e17  jnz     short loc_180012E1E
0x180012e19  mov     edi, r8d
0x180012e1c  jmp     short loc_180012E28
0x180012e1e  mov     [rax], r8
0x180012e21  lea     rdi, [rax+10h]
0x180012e25  mov     rbx, rax
0x180012e28  test    rdi, rdi
0x180012e2b  jz      loc_18001301A
0x180012e31  xor     edx, edx; dwFlags
0x180012e33  mov     [rdi], r8w
0x180012e37  shr     rsi, 1
0x180012e3a  lea     r8, [rbp+9B0h+Filename]; lpMultiByteStr
0x180012e3e  mov     [rsp+9E0h+cchWideChar], esi; cchWideChar
0x180012e42  mov     r9d, r14d; cbMultiByte
0x180012e45  mov     [rsp+9E0h+lpWideCharStr], rdi; lpWideCharStr
0x180012e4a  lea     ecx, [rdx+3]; CodePage
0x180012e4d  call    cs:__imp_MultiByteToWideChar
0x180012e53  xor     r8d, r8d
0x180012e56  test    eax, eax
0x180012e58  jz      loc_18001301A
0x180012e5e  mov     ecx, r8d
0x180012e61  lea     r9d, [r8+27h]
0x180012e65  mov     rsi, rdi
0x180012e68  movzx   edx, word ptr [rdi]
0x180012e6b  test    dx, dx
0x180012e6e  jz      short loc_180012E9F
0x180012e70  mov     [rbp+rcx*2+9B0h+Source], dx
0x180012e78  cmp     [rdi], r9w
0x180012e7c  jnz     short loc_180012E91
0x180012e7e  cmp     ecx, 206h
0x180012e84  jnb     short loc_180012E91
0x180012e86  inc     ecx
0x180012e88  mov     [rbp+rcx*2+9B0h+Source], r9w
0x180012e91  add     rdi, 2
0x180012e95  inc     ecx
0x180012e97  cmp     ecx, 207h
0x180012e9d  jb      short loc_180012E68
0x180012e9f  mov     [rbp+rcx*2+9B0h+Source], r8w
0x180012ea8  test    r15, r15
0x180012eab  jz      short loc_180012EC6
0x180012ead  xor     ecx, ecx; lpModuleName
0x180012eaf  call    cs:__imp_GetModuleHandleA
0x180012eb5  cmp     r15, rax
0x180012eb8  jz      short loc_180012EC6
0x180012eba  lea     r8, [rbp+9B0h+Source]
0x180012ec1  jmp     loc_180012F53
0x180012ec6  mov     edi, 22h ; '"'
0x180012ecb  lea     rcx, [rbp+9B0h+Source]
0x180012ed2  mov     [rbp+9B0h+var_460], di
0x180012ed9  mov     rax, r14
0x180012edc  xor     r15d, r15d
0x180012edf  inc     rax
0x180012ee2  cmp     [rcx+rax*2], r15w
0x180012ee7  jnz     short loc_180012EDF
0x180012ee9  inc     eax
0x180012eeb  lea     r8, [rbp+9B0h+Source]; Source
0x180012ef2  movsxd  r9, eax
0x180012ef5  lea     rcx, [rbp+9B0h+Destination]; Destination
0x180012efc  add     r9, r9; SourceSize
0x180012eff  mov     edx, 414h; DestinationSize
0x180012f04  call    cs:__imp_memcpy_s
0x180012f0a  test    eax, eax
0x180012f0c  jnz     loc_180012FF7
0x180012f12  lea     rax, [rbp+9B0h+var_460]
0x180012f19  inc     r14
0x180012f1c  cmp     [rax+r14*2], r15w
0x180012f21  jnz     short loc_180012F19
0x180012f23  movsxd  rax, r14d
0x180012f26  lea     rcx, ds:2[rax*2]
0x180012f2e  mov     [rbp+rax*2+9B0h+var_460], di
0x180012f36  cmp     rcx, 418h
0x180012f3d  jnb     loc_180013056
0x180012f43  mov     [rbp+rcx+9B0h+var_460], r15w
0x180012f4c  lea     r8, [rbp+9B0h+var_460]; unsigned __int16 *
0x180012f53  lea     rdx, aModule; "Module"
0x180012f5a  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x180012f5e  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180012f63  mov     edi, eax
0x180012f65  test    eax, eax
0x180012f67  js      short loc_180012FA8
0x180012f69  lea     r8, [rbp+9B0h+Source]; unsigned __int16 *
0x180012f70  lea     rdx, aModuleRaw; "Module_Raw"
0x180012f77  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x180012f7b  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180012f80  mov     edi, eax
0x180012f82  test    eax, eax
0x180012f84  js      short loc_180012FBD
0x180012f86  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x180012f8a  mov     r8d, r12d; unsigned int
0x180012f8d  mov     rdx, rsi; unsigned __int16 *
0x180012f90  test    r13d, r13d
0x180012f93  jz      short loc_180012FC4
0x180012f95  call    ?ResourceRegister@CRegObject@ATL@@QEAAJPEBGI0@Z; ATL::CRegObject::ResourceRegister(ushort const *,uint,ushort const *)
0x180012f9a  jmp     short loc_180012FC9
0x180012f9c  mov     rcx, rbx; Block
0x180012f9f  mov     rbx, [rbx]
0x180012fa2  call    cs:__imp_free
0x180012fa8  test    rbx, rbx
0x180012fab  jnz     short loc_180012F9C
0x180012fad  mov     ebx, edi
0x180012faf  jmp     short loc_180013001
0x180012fb1  mov     rcx, rbx; Block
0x180012fb4  mov     rbx, [rbx]
0x180012fb7  call    cs:__imp_free
0x180012fbd  test    rbx, rbx
0x180012fc0  jnz     short loc_180012FB1
0x180012fc2  jmp     short loc_180012FAD
0x180012fc4  call    ?ResourceUnregister@CRegObject@ATL@@QEAAJPEBGI0@Z; ATL::CRegObject::ResourceUnregister(ushort const *,uint,ushort const *)
0x180012fc9  mov     edi, eax
0x180012fcb  jmp     short loc_180012FD9
0x180012fcd  mov     rcx, rbx; Block
0x180012fd0  mov     rbx, [rbx]
0x180012fd3  call    cs:__imp_free
0x180012fd9  test    rbx, rbx
0x180012fdc  jnz     short loc_180012FCD
0x180012fde  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x180012fe2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180012fe7  mov     eax, edi
0x180012fe9  jmp     short loc_18001302D
0x180012feb  mov     rcx, rbx; Block
0x180012fee  mov     rbx, [rbx]
0x180012ff1  call    cs:__imp_free
0x180012ff7  test    rbx, rbx
0x180012ffa  jnz     short loc_180012FEB
0x180012ffc  mov     ebx, 80004005h
0x180013001  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x180013005  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001300a  mov     eax, ebx
0x18001300c  jmp     short loc_18001302D
0x18001300e  mov     rcx, rbx; Block
0x180013011  mov     rbx, [rbx]
0x180013014  call    cs:__imp_free
0x18001301a  test    rbx, rbx
0x18001301d  jnz     short loc_18001300E
0x18001301f  lea     rcx, [rbp+9B0h+WideCharStr]; this
0x180013023  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180013028  mov     eax, 8007000Eh
0x18001302d  mov     rcx, [rbp+9B0h+var_40]
0x180013034  xor     rcx, rbp; StackCookie
0x180013037  call    __security_check_cookie
0x18001303c  mov     rbx, [rbp+9B0h+arg_10]
0x180013043  lea     rsp, [rbp+980h]
0x18001304a  pop     r15
0x18001304c  pop     r14
0x18001304e  pop     r13
0x180013050  pop     r12
0x180013052  pop     rdi
0x180013053  pop     rsi
0x180013054  pop     rbp
0x180013055  retn
0x180013056  call    __report_rangecheckfailure
0x18001305c  mov     ecx, 80070057h; int
0x180013061  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
