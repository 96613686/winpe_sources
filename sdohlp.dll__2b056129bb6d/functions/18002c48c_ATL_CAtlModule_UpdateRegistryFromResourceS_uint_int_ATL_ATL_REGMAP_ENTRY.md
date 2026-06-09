# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18002c48c`
- end: `0x18002c6ce`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `578`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18002c460`
- `0x18002c930`

## callees

- `0x180023d88`
- `0x180024850`
- `0x180024d54`
- `0x180025590`
- `0x180025fc0`
- `0x180027878`
- `0x18002a3d0`
- `0x18002c48c`
- `0x18002ca30`
- `0x180055030`
- `0x180058010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18002c542`
- `KERNEL32!GetModuleFileNameW` at `0x18002c542`
- `KERNEL32!GetModuleHandleW` at `0x18002c588`
- `KERNEL32!GetModuleHandleW` at `0x18002c588`

## string_xrefs

- `0x18002c691`: `REGISTRY`

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
    if ( ModuleFileNameW != 260 )
    {
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
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v21, L"Module_Raw", v27);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v18;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
      goto LABEL_21;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    Error = -2147024774;
  }
LABEL_22:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002c48c  mov     [rsp-8+arg_10], rbx
0x18002c491  push    rbp
0x18002c492  push    rsi
0x18002c493  push    rdi
0x18002c494  push    r14
0x18002c496  push    r15
0x18002c498  lea     rbp, [rsp-9C0h]
0x18002c4a0  sub     rsp, 0AC0h
0x18002c4a7  mov     rax, cs:__security_cookie
0x18002c4ae  xor     rax, rsp
0x18002c4b1  mov     [rbp+9E0h+var_30], rax
0x18002c4b8  mov     rbx, r9
0x18002c4bb  mov     esi, r8d
0x18002c4be  mov     r14d, edx
0x18002c4c1  mov     rdi, rcx
0x18002c4c4  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18002c4cb  mov     [rsp+0AE0h+var_AA0], rax
0x18002c4d0  xorps   xmm0, xmm0
0x18002c4d3  movdqu  [rsp+0AE0h+var_A98], xmm0
0x18002c4d9  xor     r15d, r15d
0x18002c4dc  mov     [rsp+0AE0h+var_A88], r15d
0x18002c4e1  test    r9, r9
0x18002c4e4  jz      short loc_18002C508
0x18002c4e6  mov     rax, [r9]
0x18002c4e9  jmp     short loc_18002C503
0x18002c4eb  mov     r8, [rbx+8]; unsigned __int16 *
0x18002c4ef  mov     rdx, rax; unsigned __int16 *
0x18002c4f2  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c4f7  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002c4fc  lea     rbx, [rbx+10h]
0x18002c500  mov     rax, [rbx]
0x18002c503  test    rax, rax
0x18002c506  jnz     short loc_18002C4EB
0x18002c508  mov     rax, [rdi]
0x18002c50b  lea     rdx, [rsp+0AE0h+var_AA0]
0x18002c510  mov     rcx, rdi
0x18002c513  mov     rax, [rax+28h]
0x18002c517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c51c  mov     ebx, eax
0x18002c51e  test    eax, eax
0x18002c520  js      loc_18002C656
0x18002c526  mov     [rsp+0AE0h+var_AB0], r15
0x18002c52b  mov     rbx, cs:hModule
0x18002c532  mov     edi, 104h
0x18002c537  mov     r8d, edi; nSize
0x18002c53a  lea     rdx, [rsp+0AE0h+Filename]; lpFilename
0x18002c53f  mov     rcx, rbx; hModule
0x18002c542  call    cs:__imp_GetModuleFileNameW
0x18002c548  test    eax, eax
0x18002c54a  jnz     short loc_18002C558
0x18002c54c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002c551  mov     ebx, eax
0x18002c553  jmp     loc_18002C64C
0x18002c558  cmp     eax, edi
0x18002c55a  jnz     short loc_18002C570
0x18002c55c  lea     rcx, [rsp+0AE0h+var_AB0]
0x18002c561  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c566  mov     ebx, 8007007Ah
0x18002c56b  jmp     loc_18002C656
0x18002c570  lea     r8, [rsp+0AE0h+Filename]; unsigned __int16 *
0x18002c575  lea     rcx, [rbp+9E0h+var_440]; unsigned __int16 *
0x18002c57c  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18002c581  test    rbx, rbx
0x18002c584  jz      short loc_18002C59C
0x18002c586  xor     ecx, ecx; lpModuleName
0x18002c588  call    cs:__imp_GetModuleHandleW
0x18002c58e  cmp     rbx, rax
0x18002c591  jz      short loc_18002C59C
0x18002c593  lea     r8, [rbp+9E0h+var_440]
0x18002c59a  jmp     short loc_18002C617
0x18002c59c  mov     ebx, 22h ; '"'
0x18002c5a1  mov     [rbp+9E0h+var_860], bx
0x18002c5a8  lea     r8, [rbp+9E0h+var_440]; unsigned __int16 *
0x18002c5af  lea     rcx, [rbp+9E0h+var_85E]; unsigned __int16 *
0x18002c5b6  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18002c5bb  test    al, al
0x18002c5bd  jnz     short loc_18002C5D3
0x18002c5bf  lea     rcx, [rsp+0AE0h+var_AB0]
0x18002c5c4  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c5c9  mov     ebx, 80004005h
0x18002c5ce  jmp     loc_18002C656
0x18002c5d3  lea     rcx, [rbp+9E0h+var_860]
0x18002c5da  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c5de  inc     rax
0x18002c5e1  cmp     [rcx+rax*2], r15w
0x18002c5e6  jnz     short loc_18002C5DE
0x18002c5e8  cdqe
0x18002c5ea  mov     [rbp+rax*2+9E0h+var_860], bx
0x18002c5f2  lea     rcx, ds:2[rax*2]
0x18002c5fa  cmp     rcx, 418h
0x18002c601  jnb     loc_18002C6C8
0x18002c607  mov     [rbp+rcx+9E0h+var_860], r15w
0x18002c610  lea     r8, [rbp+9E0h+var_860]; unsigned __int16 *
0x18002c617  lea     rdx, aModule; "Module"
0x18002c61e  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c623  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002c628  mov     ebx, eax
0x18002c62a  test    eax, eax
0x18002c62c  js      short loc_18002C64C
0x18002c62e  lea     r8, [rbp+9E0h+var_440]; unsigned __int16 *
0x18002c635  lea     rdx, aModuleRaw; "Module_Raw"
0x18002c63c  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c641  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18002c646  mov     ebx, eax
0x18002c648  test    eax, eax
0x18002c64a  jns     short loc_18002C688
0x18002c64c  lea     rcx, [rsp+0AE0h+var_AB0]
0x18002c651  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c656  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c65b  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18002c660  mov     eax, ebx
0x18002c662  mov     rcx, [rbp+9E0h+var_30]
0x18002c669  xor     rcx, rsp; StackCookie
0x18002c66c  call    __security_check_cookie
0x18002c671  mov     rbx, [rsp+0AE0h+arg_10]
0x18002c679  add     rsp, 0AC0h
0x18002c680  pop     r15
0x18002c682  pop     r14
0x18002c684  pop     rdi
0x18002c685  pop     rsi
0x18002c686  pop     rbp
0x18002c687  retn
0x18002c688  movzx   r8d, r14w; unsigned __int16 *
0x18002c68c  mov     [rsp+0AE0h+var_AA8], r15
0x18002c691  lea     r9, aRegistry; "REGISTRY"
0x18002c698  lea     rdx, [rsp+0AE0h+Filename]; unsigned __int16 *
0x18002c69d  lea     rcx, [rsp+0AE0h+var_AA0]; this
0x18002c6a2  test    esi, esi
0x18002c6a4  jz      short loc_18002C6B0
0x18002c6a6  mov     [rsp+0AE0h+var_AC0], 1
0x18002c6ae  jmp     short loc_18002C6B5
0x18002c6b0  mov     [rsp+0AE0h+var_AC0], r15d; int
0x18002c6b5  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18002c6ba  mov     ebx, eax
0x18002c6bc  lea     rcx, [rsp+0AE0h+var_AA8]
0x18002c6c1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002c6c6  jmp     short loc_18002C64C
0x18002c6c8  call    __report_rangecheckfailure
```
