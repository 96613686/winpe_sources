# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180006374`
- end: `0x1800065f4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006610`

## callees

- `0x180002238`
- `0x180002b1c`
- `0x180002dd8`
- `0x180003330`
- `0x180003b90`
- `0x180004718`
- `0x180004a90`
- `0x1800053f0`
- `0x180006374`
- `0x18000661c`
- `0x180012800`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800064bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000647a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000647a`

## string_xrefs

- `0x1800065c1`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // esi
  int LastErrorHRESULT; // ebx
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
  LastErrorHRESULT = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( LastErrorHRESULT >= 0 )
  {
    v19 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_24;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      LastErrorHRESULT = -2147024774;
      goto LABEL_24;
    }
    ATL::CAtlModule::EscapeSingleQuote(v29, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v27 = 34;
      if ( !ocscpy_s(v28, v14, v29) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        LastErrorHRESULT = -2147467259;
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
    LastErrorHRESULT = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( LastErrorHRESULT < 0 )
      goto LABEL_23;
    LastErrorHRESULT = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
    if ( LastErrorHRESULT < 0 )
      goto LABEL_23;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_30:
        LastErrorHRESULT = v18;
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
    LastErrorHRESULT = -2147024809;
    goto LABEL_32;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)LastErrorHRESULT;
}

```

## disassembly

```asm
0x180006374  push    rbp
0x180006376  push    rbx
0x180006377  push    rsi
0x180006378  push    rdi
0x180006379  push    r12
0x18000637b  push    r14
0x18000637d  push    r15
0x18000637f  lea     rbp, [rsp-9E0h]
0x180006387  sub     rsp, 0AE0h
0x18000638e  mov     rax, cs:__security_cookie
0x180006395  xor     rax, rsp
0x180006398  mov     [rbp+0A10h+var_40], rax
0x18000639f  mov     rbx, r9
0x1800063a2  mov     r15d, r8d
0x1800063a5  mov     rdi, rdx
0x1800063a8  mov     r14, rcx
0x1800063ab  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800063b2  mov     [rsp+0B10h+var_AD0], rax
0x1800063b7  xor     r12d, r12d
0x1800063ba  mov     [rsp+0B10h+var_AC8], r12
0x1800063bf  mov     [rsp+0B10h+var_AC0], r12
0x1800063c4  mov     [rsp+0B10h+var_AB8], r12d
0x1800063c9  xorps   xmm0, xmm0
0x1800063cc  xor     eax, eax
0x1800063ce  movups  [rsp+0B10h+var_AB0], xmm0
0x1800063d3  movups  [rsp+0B10h+var_AA0], xmm0
0x1800063d8  mov     [rbp+0A10h+var_A90], rax
0x1800063dc  mov     [rbp+0A10h+var_A88], r12b
0x1800063e0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x1800063e5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800063ea  mov     esi, eax
0x1800063ec  test    eax, eax
0x1800063ee  jns     short loc_18000641D
0x1800063f0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800063f5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800063fa  mov     eax, esi
0x1800063fc  mov     rcx, [rbp+0A10h+var_40]
0x180006403  xor     rcx, rsp; StackCookie
0x180006406  call    __security_check_cookie
0x18000640b  add     rsp, 0AE0h
0x180006412  pop     r15
0x180006414  pop     r14
0x180006416  pop     r12
0x180006418  pop     rdi
0x180006419  pop     rsi
0x18000641a  pop     rbx
0x18000641b  pop     rbp
0x18000641c  retn
0x18000641d  test    rbx, rbx
0x180006420  jz      short loc_180006441
0x180006422  jmp     short loc_180006439
0x180006424  mov     r8, [rbx+8]; unsigned __int16 *
0x180006428  mov     rdx, rax; unsigned __int16 *
0x18000642b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180006430  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006435  lea     rbx, [rbx+10h]
0x180006439  mov     rax, [rbx]
0x18000643c  test    rax, rax
0x18000643f  jnz     short loc_180006424
0x180006441  mov     rax, [r14]
0x180006444  lea     rdx, [rsp+0B10h+var_AD0]
0x180006449  mov     rcx, r14
0x18000644c  mov     rax, [rax+28h]
0x180006450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006455  mov     ebx, eax
0x180006457  test    eax, eax
0x180006459  js      loc_18000658D
0x18000645f  mov     [rsp+0B10h+var_AE0], r12
0x180006464  mov     rbx, cs:hModule
0x18000646b  mov     esi, 104h
0x180006470  mov     r8d, esi; nSize
0x180006473  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180006477  mov     rcx, rbx; hModule
0x18000647a  call    cs:__imp_GetModuleFileNameW
0x180006480  test    eax, eax
0x180006482  jnz     short loc_180006490
0x180006484  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180006489  mov     ebx, eax
0x18000648b  jmp     loc_180006583
0x180006490  cmp     eax, esi
0x180006492  jnz     short loc_1800064A8
0x180006494  lea     rcx, [rsp+0B10h+var_AE0]
0x180006499  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000649e  mov     ebx, 8007007Ah
0x1800064a3  jmp     loc_18000658D
0x1800064a8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800064ac  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800064b3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800064b8  test    rbx, rbx
0x1800064bb  jz      short loc_1800064D3
0x1800064bd  xor     ecx, ecx; lpModuleName
0x1800064bf  call    cs:__imp_GetModuleHandleW
0x1800064c5  cmp     rbx, rax
0x1800064c8  jz      short loc_1800064D3
0x1800064ca  lea     r8, [rbp+0A10h+var_450]
0x1800064d1  jmp     short loc_18000654E
0x1800064d3  mov     ebx, 22h ; '"'
0x1800064d8  mov     [rbp+0A10h+var_870], bx
0x1800064df  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800064e6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x1800064ed  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x1800064f2  test    al, al
0x1800064f4  jnz     short loc_18000650A
0x1800064f6  lea     rcx, [rsp+0B10h+var_AE0]
0x1800064fb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006500  mov     ebx, 80004005h
0x180006505  jmp     loc_18000658D
0x18000650a  lea     rcx, [rbp+0A10h+var_870]
0x180006511  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006515  inc     rax
0x180006518  cmp     [rcx+rax*2], r12w
0x18000651d  jnz     short loc_180006515
0x18000651f  cdqe
0x180006521  mov     [rbp+rax*2+0A10h+var_870], bx
0x180006529  lea     rcx, ds:2[rax*2]
0x180006531  cmp     rcx, 418h
0x180006538  jnb     loc_1800065EE
0x18000653e  mov     [rbp+rcx+0A10h+var_870], r12w
0x180006547  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000654e  lea     rdx, aModule; "Module"
0x180006555  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000655a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000655f  mov     ebx, eax
0x180006561  test    eax, eax
0x180006563  js      short loc_180006583
0x180006565  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000656c  lea     rdx, aModuleRaw; "Module_Raw"
0x180006573  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180006578  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000657d  mov     ebx, eax
0x18000657f  test    eax, eax
0x180006581  jns     short loc_18000659E
0x180006583  lea     rcx, [rsp+0B10h+var_AE0]
0x180006588  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000658d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180006592  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006597  mov     eax, ebx
0x180006599  jmp     loc_1800063FC
0x18000659e  mov     [rsp+0B10h+var_AD8], r12
0x1800065a3  test    r15d, r15d
0x1800065a6  jz      short loc_1800065B7
0x1800065a8  test    rdi, rdi
0x1800065ab  jz      short loc_1800065DD
0x1800065ad  mov     [rsp+0B10h+var_AF0], 1
0x1800065b5  jmp     short loc_1800065C1
0x1800065b7  test    rdi, rdi
0x1800065ba  jz      short loc_1800065DD
0x1800065bc  mov     [rsp+0B10h+var_AF0], r12d; int
0x1800065c1  lea     r9, aRegistry; "REGISTRY"
0x1800065c8  mov     r8, rdi; unsigned __int16 *
0x1800065cb  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800065cf  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800065d4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800065d9  mov     ebx, eax
0x1800065db  jmp     short loc_1800065E2
0x1800065dd  mov     ebx, 80070057h
0x1800065e2  lea     rcx, [rsp+0B10h+var_AD8]
0x1800065e7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800065ec  jmp     short loc_180006583
0x1800065ee  call    __report_rangecheckfailure
```
