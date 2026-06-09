# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001f1cc`
- end: `0x18001f43c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f6d0`

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
- `0x18001f1cc`
- `0x18001f6ec`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f317`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f317`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f2d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f2d2`

## string_xrefs

- `0x18001f3ff`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
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
    if ( ModuleFileNameW != 260 )
    {
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
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v18;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
      goto LABEL_23;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    Error = -2147024774;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001f1cc  push    rbp
0x18001f1ce  push    rbx
0x18001f1cf  push    rsi
0x18001f1d0  push    rdi
0x18001f1d1  push    r12
0x18001f1d3  push    r14
0x18001f1d5  push    r15
0x18001f1d7  lea     rbp, [rsp-9E0h]
0x18001f1df  sub     rsp, 0AE0h
0x18001f1e6  mov     rax, cs:__security_cookie
0x18001f1ed  xor     rax, rsp
0x18001f1f0  mov     [rbp+0A10h+var_40], rax
0x18001f1f7  mov     rbx, r9
0x18001f1fa  mov     r14d, r8d
0x18001f1fd  mov     r15d, edx
0x18001f200  mov     rsi, rcx
0x18001f203  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001f20a  mov     [rsp+0B10h+var_AD0], rax
0x18001f20f  xor     r12d, r12d
0x18001f212  mov     [rsp+0B10h+var_AC8], r12
0x18001f217  mov     [rsp+0B10h+var_AC0], r12
0x18001f21c  mov     [rsp+0B10h+var_AB8], r12d
0x18001f221  xorps   xmm0, xmm0
0x18001f224  xor     eax, eax
0x18001f226  movups  [rsp+0B10h+var_AB0], xmm0
0x18001f22b  movups  [rsp+0B10h+var_AA0], xmm0
0x18001f230  mov     [rbp+0A10h+var_A90], rax
0x18001f234  mov     [rbp+0A10h+var_A88], r12b
0x18001f238  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001f23d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001f242  mov     edi, eax
0x18001f244  test    eax, eax
0x18001f246  jns     short loc_18001F275
0x18001f248  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f24d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001f252  mov     eax, edi
0x18001f254  mov     rcx, [rbp+0A10h+var_40]
0x18001f25b  xor     rcx, rsp; StackCookie
0x18001f25e  call    __security_check_cookie
0x18001f263  add     rsp, 0AE0h
0x18001f26a  pop     r15
0x18001f26c  pop     r14
0x18001f26e  pop     r12
0x18001f270  pop     rdi
0x18001f271  pop     rsi
0x18001f272  pop     rbx
0x18001f273  pop     rbp
0x18001f274  retn
0x18001f275  test    rbx, rbx
0x18001f278  jz      short loc_18001F299
0x18001f27a  jmp     short loc_18001F291
0x18001f27c  mov     r8, [rbx+8]; unsigned __int16 *
0x18001f280  mov     rdx, rax; unsigned __int16 *
0x18001f283  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f288  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001f28d  lea     rbx, [rbx+10h]
0x18001f291  mov     rax, [rbx]
0x18001f294  test    rax, rax
0x18001f297  jnz     short loc_18001F27C
0x18001f299  mov     rax, [rsi]
0x18001f29c  lea     rdx, [rsp+0B10h+var_AD0]
0x18001f2a1  mov     rcx, rsi
0x18001f2a4  mov     rax, [rax+28h]
0x18001f2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2ad  mov     ebx, eax
0x18001f2af  test    eax, eax
0x18001f2b1  js      loc_18001F3E5
0x18001f2b7  mov     [rsp+0B10h+var_AE0], r12
0x18001f2bc  mov     rbx, cs:hInstance
0x18001f2c3  mov     edi, 104h
0x18001f2c8  mov     r8d, edi; nSize
0x18001f2cb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001f2cf  mov     rcx, rbx; hModule
0x18001f2d2  call    cs:__imp_GetModuleFileNameW
0x18001f2d8  test    eax, eax
0x18001f2da  jnz     short loc_18001F2E8
0x18001f2dc  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001f2e1  mov     ebx, eax
0x18001f2e3  jmp     loc_18001F3DB
0x18001f2e8  cmp     eax, edi
0x18001f2ea  jnz     short loc_18001F300
0x18001f2ec  lea     rcx, [rsp+0B10h+var_AE0]
0x18001f2f1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f2f6  mov     ebx, 8007007Ah
0x18001f2fb  jmp     loc_18001F3E5
0x18001f300  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001f304  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001f30b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001f310  test    rbx, rbx
0x18001f313  jz      short loc_18001F32B
0x18001f315  xor     ecx, ecx; lpModuleName
0x18001f317  call    cs:__imp_GetModuleHandleW
0x18001f31d  cmp     rbx, rax
0x18001f320  jz      short loc_18001F32B
0x18001f322  lea     r8, [rbp+0A10h+var_450]
0x18001f329  jmp     short loc_18001F3A6
0x18001f32b  mov     ebx, 22h ; '"'
0x18001f330  mov     [rbp+0A10h+var_870], bx
0x18001f337  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001f33e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001f345  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001f34a  test    al, al
0x18001f34c  jnz     short loc_18001F362
0x18001f34e  lea     rcx, [rsp+0B10h+var_AE0]
0x18001f353  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f358  mov     ebx, 80004005h
0x18001f35d  jmp     loc_18001F3E5
0x18001f362  lea     rcx, [rbp+0A10h+var_870]
0x18001f369  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f36d  inc     rax
0x18001f370  cmp     [rcx+rax*2], r12w
0x18001f375  jnz     short loc_18001F36D
0x18001f377  cdqe
0x18001f379  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001f381  lea     rcx, ds:2[rax*2]
0x18001f389  cmp     rcx, 418h
0x18001f390  jnb     loc_18001F436
0x18001f396  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001f39f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001f3a6  lea     rdx, aModule; "Module"
0x18001f3ad  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f3b2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001f3b7  mov     ebx, eax
0x18001f3b9  test    eax, eax
0x18001f3bb  js      short loc_18001F3DB
0x18001f3bd  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001f3c4  lea     rdx, aModuleRaw; "Module_Raw"
0x18001f3cb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f3d0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001f3d5  mov     ebx, eax
0x18001f3d7  test    eax, eax
0x18001f3d9  jns     short loc_18001F3F6
0x18001f3db  lea     rcx, [rsp+0B10h+var_AE0]
0x18001f3e0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f3e5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f3ea  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001f3ef  mov     eax, ebx
0x18001f3f1  jmp     loc_18001F254
0x18001f3f6  movzx   r8d, r15w; unsigned __int16 *
0x18001f3fa  mov     [rsp+0B10h+var_AD8], r12
0x18001f3ff  lea     r9, aRegistry; "REGISTRY"
0x18001f406  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001f40a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001f40f  test    r14d, r14d
0x18001f412  jz      short loc_18001F41E
0x18001f414  mov     [rsp+0B10h+var_AF0], 1
0x18001f41c  jmp     short loc_18001F423
0x18001f41e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001f423  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001f428  mov     ebx, eax
0x18001f42a  lea     rcx, [rsp+0B10h+var_AD8]
0x18001f42f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001f434  jmp     short loc_18001F3DB
0x18001f436  call    __report_rangecheckfailure
```
