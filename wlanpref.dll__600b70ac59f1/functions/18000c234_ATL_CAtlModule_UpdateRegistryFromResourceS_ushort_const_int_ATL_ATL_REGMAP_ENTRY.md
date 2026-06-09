# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000c234`
- end: `0x18000c4b4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c4d0`

## callees

- `0x180001c08`
- `0x180002cc0`
- `0x180003674`
- `0x1800042d0`
- `0x180004c4c`
- `0x18000777c`
- `0x1800080a0`
- `0x18000acc0`
- `0x18000c234`
- `0x18000c510`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c37f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c37f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c33a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c33a`

## string_xrefs

- `0x18000c481`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // esi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned __int16 *v15; // r8
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v28[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v29[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v23);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v21,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v19 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_24;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      Error = -2147024774;
      goto LABEL_24;
    }
    ATL::CAtlModule::EscapeSingleQuote(v29, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v27 = 34;
      if ( !ocscpy_s(v28, v14, v29) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_24;
      }
      v16 = -1;
      do
        ++v16;
      while ( v28[v16 - 1] );
      v28[(int)v16 - 1] = 34;
      v17 = 2LL * (int)v16 + 2;
      if ( v17 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v28[-1] + v17) = 0;
      v15 = &v27;
    }
    else
    {
      v15 = v29;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
    if ( Error < 0 )
      goto LABEL_23;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_30:
        Error = v18;
LABEL_32:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_23;
      }
    }
    else if ( a2 )
    {
      v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 0);
      goto LABEL_30;
    }
    Error = -2147024809;
    goto LABEL_32;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000c234  push    rbp
0x18000c236  push    rbx
0x18000c237  push    rsi
0x18000c238  push    rdi
0x18000c239  push    r12
0x18000c23b  push    r14
0x18000c23d  push    r15
0x18000c23f  lea     rbp, [rsp-9E0h]
0x18000c247  sub     rsp, 0AE0h
0x18000c24e  mov     rax, cs:__security_cookie
0x18000c255  xor     rax, rsp
0x18000c258  mov     [rbp+0A10h+var_40], rax
0x18000c25f  mov     rbx, r9
0x18000c262  mov     r15d, r8d
0x18000c265  mov     rdi, rdx
0x18000c268  mov     r14, rcx
0x18000c26b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000c272  mov     [rsp+0B10h+var_AD0], rax
0x18000c277  xor     r12d, r12d
0x18000c27a  mov     [rsp+0B10h+var_AC8], r12
0x18000c27f  mov     [rsp+0B10h+var_AC0], r12
0x18000c284  mov     [rsp+0B10h+var_AB8], r12d
0x18000c289  xorps   xmm0, xmm0
0x18000c28c  xor     eax, eax
0x18000c28e  movups  [rsp+0B10h+var_AB0], xmm0
0x18000c293  movups  [rsp+0B10h+var_AA0], xmm0
0x18000c298  mov     [rbp+0A10h+var_A90], rax
0x18000c29c  mov     [rbp+0A10h+var_A88], r12b
0x18000c2a0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000c2a5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000c2aa  mov     esi, eax
0x18000c2ac  test    eax, eax
0x18000c2ae  jns     short loc_18000C2DD
0x18000c2b0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c2b5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c2ba  mov     eax, esi
0x18000c2bc  mov     rcx, [rbp+0A10h+var_40]
0x18000c2c3  xor     rcx, rsp; StackCookie
0x18000c2c6  call    __security_check_cookie
0x18000c2cb  add     rsp, 0AE0h
0x18000c2d2  pop     r15
0x18000c2d4  pop     r14
0x18000c2d6  pop     r12
0x18000c2d8  pop     rdi
0x18000c2d9  pop     rsi
0x18000c2da  pop     rbx
0x18000c2db  pop     rbp
0x18000c2dc  retn
0x18000c2dd  test    rbx, rbx
0x18000c2e0  jz      short loc_18000C301
0x18000c2e2  jmp     short loc_18000C2F9
0x18000c2e4  mov     r8, [rbx+8]; unsigned __int16 *
0x18000c2e8  mov     rdx, rax; unsigned __int16 *
0x18000c2eb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c2f0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c2f5  lea     rbx, [rbx+10h]
0x18000c2f9  mov     rax, [rbx]
0x18000c2fc  test    rax, rax
0x18000c2ff  jnz     short loc_18000C2E4
0x18000c301  mov     rax, [r14]
0x18000c304  lea     rdx, [rsp+0B10h+var_AD0]
0x18000c309  mov     rcx, r14
0x18000c30c  mov     rax, [rax+28h]
0x18000c310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c315  mov     ebx, eax
0x18000c317  test    eax, eax
0x18000c319  js      loc_18000C44D
0x18000c31f  mov     [rsp+0B10h+var_AE0], r12
0x18000c324  mov     rbx, cs:hModule
0x18000c32b  mov     esi, 104h
0x18000c330  mov     r8d, esi; nSize
0x18000c333  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000c337  mov     rcx, rbx; hModule
0x18000c33a  call    cs:__imp_GetModuleFileNameW
0x18000c340  test    eax, eax
0x18000c342  jnz     short loc_18000C350
0x18000c344  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c349  mov     ebx, eax
0x18000c34b  jmp     loc_18000C443
0x18000c350  cmp     eax, esi
0x18000c352  jnz     short loc_18000C368
0x18000c354  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c359  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c35e  mov     ebx, 8007007Ah
0x18000c363  jmp     loc_18000C44D
0x18000c368  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000c36c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c373  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000c378  test    rbx, rbx
0x18000c37b  jz      short loc_18000C393
0x18000c37d  xor     ecx, ecx; lpModuleName
0x18000c37f  call    cs:__imp_GetModuleHandleW
0x18000c385  cmp     rbx, rax
0x18000c388  jz      short loc_18000C393
0x18000c38a  lea     r8, [rbp+0A10h+var_450]
0x18000c391  jmp     short loc_18000C40E
0x18000c393  mov     ebx, 22h ; '"'
0x18000c398  mov     [rbp+0A10h+var_870], bx
0x18000c39f  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c3a6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000c3ad  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000c3b2  test    al, al
0x18000c3b4  jnz     short loc_18000C3CA
0x18000c3b6  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c3bb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c3c0  mov     ebx, 80004005h
0x18000c3c5  jmp     loc_18000C44D
0x18000c3ca  lea     rcx, [rbp+0A10h+var_870]
0x18000c3d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c3d5  inc     rax
0x18000c3d8  cmp     [rcx+rax*2], r12w
0x18000c3dd  jnz     short loc_18000C3D5
0x18000c3df  cdqe
0x18000c3e1  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000c3e9  lea     rcx, ds:2[rax*2]
0x18000c3f1  cmp     rcx, 418h
0x18000c3f8  jnb     loc_18000C4AE
0x18000c3fe  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000c407  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000c40e  lea     rdx, aModule; "Module"
0x18000c415  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c41a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c41f  mov     ebx, eax
0x18000c421  test    eax, eax
0x18000c423  js      short loc_18000C443
0x18000c425  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c42c  lea     rdx, aModuleRaw; "Module_Raw"
0x18000c433  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c438  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c43d  mov     ebx, eax
0x18000c43f  test    eax, eax
0x18000c441  jns     short loc_18000C45E
0x18000c443  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c448  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c44d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c452  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c457  mov     eax, ebx
0x18000c459  jmp     loc_18000C2BC
0x18000c45e  mov     [rsp+0B10h+var_AD8], r12
0x18000c463  test    r15d, r15d
0x18000c466  jz      short loc_18000C477
0x18000c468  test    rdi, rdi
0x18000c46b  jz      short loc_18000C49D
0x18000c46d  mov     [rsp+0B10h+var_AF0], 1
0x18000c475  jmp     short loc_18000C481
0x18000c477  test    rdi, rdi
0x18000c47a  jz      short loc_18000C49D
0x18000c47c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000c481  lea     r9, aRegistry; "REGISTRY"
0x18000c488  mov     r8, rdi; unsigned __int16 *
0x18000c48b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000c48f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c494  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000c499  mov     ebx, eax
0x18000c49b  jmp     short loc_18000C4A2
0x18000c49d  mov     ebx, 80070057h
0x18000c4a2  lea     rcx, [rsp+0B10h+var_AD8]
0x18000c4a7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c4ac  jmp     short loc_18000C443
0x18000c4ae  call    __report_rangecheckfailure
```
