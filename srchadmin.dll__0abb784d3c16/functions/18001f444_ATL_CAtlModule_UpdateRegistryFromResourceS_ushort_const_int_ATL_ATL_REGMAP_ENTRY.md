# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001f444`
- end: `0x18001f6c4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f6e0`

## callees

- `0x180005cc0`
- `0x1800061b0`
- `0x180010680`
- `0x18001a324`
- `0x18001a798`
- `0x18001b010`
- `0x18001c838`
- `0x18001cde8`
- `0x18001e190`
- `0x18001f444`
- `0x18001f6ec`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f58f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f58f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f54a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f54a`

## string_xrefs

- `0x18001f691`: `REGISTRY`

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
  _QWORD *v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-C8h] BYREF
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
    v11 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ResultFromLastError();
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
0x18001f444  push    rbp
0x18001f446  push    rbx
0x18001f447  push    rsi
0x18001f448  push    rdi
0x18001f449  push    r12
0x18001f44b  push    r14
0x18001f44d  push    r15
0x18001f44f  lea     rbp, [rsp-9E0h]
0x18001f457  sub     rsp, 0AE0h
0x18001f45e  mov     rax, cs:__security_cookie
0x18001f465  xor     rax, rsp
0x18001f468  mov     [rbp+0A10h+var_40], rax
0x18001f46f  mov     rbx, r9
0x18001f472  mov     r15d, r8d
0x18001f475  mov     rdi, rdx
0x18001f478  mov     r14, rcx
0x18001f47b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001f482  mov     [rsp+0B10h+var_AD0], rax
0x18001f487  xor     r12d, r12d
0x18001f48a  mov     [rsp+0B10h+var_AC8], r12
0x18001f48f  mov     [rsp+0B10h+var_AC0], r12
0x18001f494  mov     [rsp+0B10h+var_AB8], r12d
0x18001f499  xorps   xmm0, xmm0
0x18001f49c  xor     eax, eax
0x18001f49e  movups  [rsp+0B10h+var_AB0], xmm0
0x18001f4a3  movups  [rsp+0B10h+var_AA0], xmm0
0x18001f4a8  mov     [rbp+0A10h+var_A90], rax
0x18001f4ac  mov     [rbp+0A10h+var_A88], r12b
0x18001f4b0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001f4b5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001f4ba  mov     esi, eax
0x18001f4bc  test    eax, eax
0x18001f4be  jns     short loc_18001F4ED
0x18001f4c0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f4c5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001f4ca  mov     eax, esi
0x18001f4cc  mov     rcx, [rbp+0A10h+var_40]
0x18001f4d3  xor     rcx, rsp; StackCookie
0x18001f4d6  call    __security_check_cookie
0x18001f4db  add     rsp, 0AE0h
0x18001f4e2  pop     r15
0x18001f4e4  pop     r14
0x18001f4e6  pop     r12
0x18001f4e8  pop     rdi
0x18001f4e9  pop     rsi
0x18001f4ea  pop     rbx
0x18001f4eb  pop     rbp
0x18001f4ec  retn
0x18001f4ed  test    rbx, rbx
0x18001f4f0  jz      short loc_18001F511
0x18001f4f2  jmp     short loc_18001F509
0x18001f4f4  mov     r8, [rbx+8]; unsigned __int16 *
0x18001f4f8  mov     rdx, rax; unsigned __int16 *
0x18001f4fb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f500  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001f505  lea     rbx, [rbx+10h]
0x18001f509  mov     rax, [rbx]
0x18001f50c  test    rax, rax
0x18001f50f  jnz     short loc_18001F4F4
0x18001f511  mov     rax, [r14]
0x18001f514  lea     rdx, [rsp+0B10h+var_AD0]
0x18001f519  mov     rcx, r14
0x18001f51c  mov     rax, [rax+28h]
0x18001f520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f525  mov     ebx, eax
0x18001f527  test    eax, eax
0x18001f529  js      loc_18001F65D
0x18001f52f  mov     [rsp+0B10h+var_AE0], r12
0x18001f534  mov     rbx, cs:hInstance
0x18001f53b  mov     esi, 104h
0x18001f540  mov     r8d, esi; nSize
0x18001f543  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001f547  mov     rcx, rbx; hModule
0x18001f54a  call    cs:__imp_GetModuleFileNameW
0x18001f550  test    eax, eax
0x18001f552  jnz     short loc_18001F560
0x18001f554  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001f559  mov     ebx, eax
0x18001f55b  jmp     loc_18001F653
0x18001f560  cmp     eax, esi
0x18001f562  jnz     short loc_18001F578
0x18001f564  lea     rcx, [rsp+0B10h+var_AE0]
0x18001f569  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f56e  mov     ebx, 8007007Ah
0x18001f573  jmp     loc_18001F65D
0x18001f578  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001f57c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001f583  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001f588  test    rbx, rbx
0x18001f58b  jz      short loc_18001F5A3
0x18001f58d  xor     ecx, ecx; lpModuleName
0x18001f58f  call    cs:__imp_GetModuleHandleW
0x18001f595  cmp     rbx, rax
0x18001f598  jz      short loc_18001F5A3
0x18001f59a  lea     r8, [rbp+0A10h+var_450]
0x18001f5a1  jmp     short loc_18001F61E
0x18001f5a3  mov     ebx, 22h ; '"'
0x18001f5a8  mov     [rbp+0A10h+var_870], bx
0x18001f5af  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001f5b6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001f5bd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001f5c2  test    al, al
0x18001f5c4  jnz     short loc_18001F5DA
0x18001f5c6  lea     rcx, [rsp+0B10h+var_AE0]
0x18001f5cb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f5d0  mov     ebx, 80004005h
0x18001f5d5  jmp     loc_18001F65D
0x18001f5da  lea     rcx, [rbp+0A10h+var_870]
0x18001f5e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f5e5  inc     rax
0x18001f5e8  cmp     [rcx+rax*2], r12w
0x18001f5ed  jnz     short loc_18001F5E5
0x18001f5ef  cdqe
0x18001f5f1  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001f5f9  lea     rcx, ds:2[rax*2]
0x18001f601  cmp     rcx, 418h
0x18001f608  jnb     loc_18001F6BE
0x18001f60e  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001f617  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001f61e  lea     rdx, aModule; "Module"
0x18001f625  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f62a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001f62f  mov     ebx, eax
0x18001f631  test    eax, eax
0x18001f633  js      short loc_18001F653
0x18001f635  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001f63c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001f643  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f648  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001f64d  mov     ebx, eax
0x18001f64f  test    eax, eax
0x18001f651  jns     short loc_18001F66E
0x18001f653  lea     rcx, [rsp+0B10h+var_AE0]
0x18001f658  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f65d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f662  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001f667  mov     eax, ebx
0x18001f669  jmp     loc_18001F4CC
0x18001f66e  mov     [rsp+0B10h+var_AD8], r12
0x18001f673  test    r15d, r15d
0x18001f676  jz      short loc_18001F687
0x18001f678  test    rdi, rdi
0x18001f67b  jz      short loc_18001F6AD
0x18001f67d  mov     [rsp+0B10h+var_AF0], 1
0x18001f685  jmp     short loc_18001F691
0x18001f687  test    rdi, rdi
0x18001f68a  jz      short loc_18001F6AD
0x18001f68c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001f691  lea     r9, aRegistry; "REGISTRY"
0x18001f698  mov     r8, rdi; unsigned __int16 *
0x18001f69b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001f69f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f6a4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001f6a9  mov     ebx, eax
0x18001f6ab  jmp     short loc_18001F6B2
0x18001f6ad  mov     ebx, 80070057h
0x18001f6b2  lea     rcx, [rsp+0B10h+var_AD8]
0x18001f6b7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f6bc  jmp     short loc_18001F653
0x18001f6be  call    __report_rangecheckfailure
```
