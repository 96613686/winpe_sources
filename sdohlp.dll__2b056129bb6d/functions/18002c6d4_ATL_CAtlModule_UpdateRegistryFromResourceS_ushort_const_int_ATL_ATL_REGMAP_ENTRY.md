# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18002c6d4`
- end: `0x18002c92a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `598`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18002c940`

## callees

- `0x180023d88`
- `0x180024850`
- `0x180024d54`
- `0x180025590`
- `0x180025fc0`
- `0x180027878`
- `0x18002a3d0`
- `0x18002c6d4`
- `0x18002ca30`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18002c78a`
- `KERNEL32!GetModuleFileNameW` at `0x18002c78a`
- `KERNEL32!GetModuleHandleW` at `0x18002c7d0`
- `KERNEL32!GetModuleHandleW` at `0x18002c7d0`

## string_xrefs

- `0x18002c8f3`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 **a4)
{
  const unsigned __int16 **v4; // rbx
  const unsigned __int16 *i; // rax
  int Error; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int16 *v14; // r8
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  void **v21; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v25; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v26[527]; // [rsp+282h] [rbp+182h] BYREF
  unsigned __int16 v27[520]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v4 = a4;
  v21 = &ATL::CRegObject::`vftable';
  v22 = 0;
  v23 = 0;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, i, v4[1]);
      v4 += 2;
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v21);
  if ( Error >= 0 )
  {
    v19 = 0;
    v10 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_21:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_22;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      Error = -2147024774;
      goto LABEL_22;
    }
    ATL::CAtlModule::EscapeSingleQuote(v27, v12, Filename);
    if ( !v10 || v10 == GetModuleHandleW(0) )
    {
      v25 = 34;
      if ( !ocscpy_s(v26, v13, v27) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_22;
      }
      v15 = -1;
      do
        ++v15;
      while ( v26[v15 - 1] );
      v26[(int)v15 - 1] = 34;
      v16 = 2LL * (int)v15 + 2;
      if ( v16 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v26[-1] + v16) = 0;
      v14 = &v25;
    }
    else
    {
      v14 = v27;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, L"Module", v14);
    if ( Error < 0 )
      goto LABEL_21;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, L"Module_Raw", v27);
    if ( Error < 0 )
      goto LABEL_21;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v21, Filename, a2, L"REGISTRY", 1);
LABEL_28:
        Error = v18;
LABEL_30:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_21;
      }
    }
    else if ( a2 )
    {
      v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v21, Filename, a2, L"REGISTRY", 0);
      goto LABEL_28;
    }
    Error = -2147024809;
    goto LABEL_30;
  }
LABEL_22:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002c6d4  mov     [rsp-8+arg_10], rbx
0x18002c6d9  push    rbp
0x18002c6da  push    rsi
0x18002c6db  push    rdi
0x18002c6dc  push    r14
0x18002c6de  push    r15
0x18002c6e0  lea     rbp, [rsp-9C0h]
0x18002c6e8  sub     rsp, 0AC0h
0x18002c6ef  mov     rax, cs:__security_cookie
0x18002c6f6  xor     rax, rsp
0x18002c6f9  mov     [rbp+9E0h+var_30], rax
0x18002c700  mov     rbx, r9
0x18002c703  mov     r14d, r8d
0x18002c706  mov     rdi, rdx
0x18002c709  mov     rsi, rcx
0x18002c70c  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18002c713  mov     [rsp+0AE0h+var_AA0], rax
0x18002c718  xorps   xmm0, xmm0
0x18002c71b  movdqu  [rsp+0AE0h+var_A98], xmm0
0x18002c721  xor     r15d, r15d
0x18002c724  mov     [rsp+0AE0h+var_A88], r15d
0x18002c729  test    r9, r9
0x18002c72c  jz      short loc_18002C750
0x18002c72e  mov     rax, [r9]
0x18002c731  jmp     short loc_18002C74B
0x18002c733  mov     r8, [rbx+8]; unsigned __int16 *
0x18002c737  mov     rdx, rax; unsigned __int16 *
0x18002c73a  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c73f  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002c744  lea     rbx, [rbx+10h]
0x18002c748  mov     rax, [rbx]
0x18002c74b  test    rax, rax
0x18002c74e  jnz     short loc_18002C733
0x18002c750  mov     rax, [rsi]
0x18002c753  lea     rdx, [rsp+0AE0h+var_AA0]
0x18002c758  mov     rcx, rsi
0x18002c75b  mov     rax, [rax+28h]
0x18002c75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c764  mov     ebx, eax
0x18002c766  test    eax, eax
0x18002c768  js      loc_18002C89E
0x18002c76e  mov     [rsp+0AE0h+var_AB0], r15
0x18002c773  mov     rbx, cs:hModule
0x18002c77a  mov     esi, 104h
0x18002c77f  mov     r8d, esi; nSize
0x18002c782  lea     rdx, [rsp+0AE0h+Filename]; lpFilename
0x18002c787  mov     rcx, rbx; hModule
0x18002c78a  call    cs:__imp_GetModuleFileNameW
0x18002c790  test    eax, eax
0x18002c792  jnz     short loc_18002C7A0
0x18002c794  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002c799  mov     ebx, eax
0x18002c79b  jmp     loc_18002C894
0x18002c7a0  cmp     eax, esi
0x18002c7a2  jnz     short loc_18002C7B8
0x18002c7a4  lea     rcx, [rsp+0AE0h+var_AB0]
0x18002c7a9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c7ae  mov     ebx, 8007007Ah
0x18002c7b3  jmp     loc_18002C89E
0x18002c7b8  lea     r8, [rsp+0AE0h+Filename]; unsigned __int16 *
0x18002c7bd  lea     rcx, [rbp+9E0h+var_440]; unsigned __int16 *
0x18002c7c4  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18002c7c9  test    rbx, rbx
0x18002c7cc  jz      short loc_18002C7E4
0x18002c7ce  xor     ecx, ecx; lpModuleName
0x18002c7d0  call    cs:__imp_GetModuleHandleW
0x18002c7d6  cmp     rbx, rax
0x18002c7d9  jz      short loc_18002C7E4
0x18002c7db  lea     r8, [rbp+9E0h+var_440]
0x18002c7e2  jmp     short loc_18002C85F
0x18002c7e4  mov     ebx, 22h ; '"'
0x18002c7e9  mov     [rbp+9E0h+var_860], bx
0x18002c7f0  lea     r8, [rbp+9E0h+var_440]; unsigned __int16 *
0x18002c7f7  lea     rcx, [rbp+9E0h+var_85E]; unsigned __int16 *
0x18002c7fe  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18002c803  test    al, al
0x18002c805  jnz     short loc_18002C81B
0x18002c807  lea     rcx, [rsp+0AE0h+var_AB0]
0x18002c80c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c811  mov     ebx, 80004005h
0x18002c816  jmp     loc_18002C89E
0x18002c81b  lea     rcx, [rbp+9E0h+var_860]
0x18002c822  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c826  inc     rax
0x18002c829  cmp     [rcx+rax*2], r15w
0x18002c82e  jnz     short loc_18002C826
0x18002c830  cdqe
0x18002c832  mov     [rbp+rax*2+9E0h+var_860], bx
0x18002c83a  lea     rcx, ds:2[rax*2]
0x18002c842  cmp     rcx, 418h
0x18002c849  jnb     loc_18002C924
0x18002c84f  mov     [rbp+rcx+9E0h+var_860], r15w
0x18002c858  lea     r8, [rbp+9E0h+var_860]; unsigned __int16 *
0x18002c85f  lea     rdx, aModule; "Module"
0x18002c866  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c86b  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002c870  mov     ebx, eax
0x18002c872  test    eax, eax
0x18002c874  js      short loc_18002C894
0x18002c876  lea     r8, [rbp+9E0h+var_440]; unsigned __int16 *
0x18002c87d  lea     rdx, aModuleRaw; "Module_Raw"
0x18002c884  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c889  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002c88e  mov     ebx, eax
0x18002c890  test    eax, eax
0x18002c892  jns     short loc_18002C8D0
0x18002c894  lea     rcx, [rsp+0AE0h+var_AB0]
0x18002c899  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c89e  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c8a3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002c8a8  mov     eax, ebx
0x18002c8aa  mov     rcx, [rbp+9E0h+var_30]
0x18002c8b1  xor     rcx, rsp; StackCookie
0x18002c8b4  call    __security_check_cookie
0x18002c8b9  mov     rbx, [rsp+0AE0h+arg_10]
0x18002c8c1  add     rsp, 0AC0h
0x18002c8c8  pop     r15
0x18002c8ca  pop     r14
0x18002c8cc  pop     rdi
0x18002c8cd  pop     rsi
0x18002c8ce  pop     rbp
0x18002c8cf  retn
0x18002c8d0  mov     [rsp+0AE0h+var_AA8], r15
0x18002c8d5  test    r14d, r14d
0x18002c8d8  jz      short loc_18002C8E9
0x18002c8da  test    rdi, rdi
0x18002c8dd  jz      short loc_18002C910
0x18002c8df  mov     [rsp+0AE0h+var_AC0], 1
0x18002c8e7  jmp     short loc_18002C8F3
0x18002c8e9  test    rdi, rdi
0x18002c8ec  jz      short loc_18002C910
0x18002c8ee  mov     [rsp+0AE0h+var_AC0], r15d; int
0x18002c8f3  lea     r9, aRegistry; "REGISTRY"
0x18002c8fa  mov     r8, rdi; unsigned __int16 *
0x18002c8fd  lea     rdx, [rsp+0AE0h+Filename]; unsigned __int16 *
0x18002c902  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c907  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18002c90c  mov     ebx, eax
0x18002c90e  jmp     short loc_18002C915
0x18002c910  mov     ebx, 80070057h
0x18002c915  lea     rcx, [rsp+0AE0h+var_AA8]
0x18002c91a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c91f  jmp     loc_18002C894
0x18002c924  call    __report_rangecheckfailure
```
