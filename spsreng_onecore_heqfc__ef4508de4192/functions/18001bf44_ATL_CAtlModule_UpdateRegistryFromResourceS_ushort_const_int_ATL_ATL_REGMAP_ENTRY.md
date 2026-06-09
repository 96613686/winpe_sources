# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001bf44`
- end: `0x18001c1c4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `11`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bb60`
- `0x18001bb80`
- `0x18001bba0`
- `0x18001bbc0`
- `0x18001bbe0`
- `0x18001bc00`
- `0x18001bc20`
- `0x18001bc40`
- `0x18001bc60`
- `0x18001bc80`
- `0x18001c1e0`

## callees

- `0x1800034b0`
- `0x180003640`
- `0x18000d234`
- `0x180014f98`
- `0x1800158b0`
- `0x180016670`
- `0x180016f48`
- `0x180019680`
- `0x18001ac10`
- `0x18001bf44`
- `0x18001c818`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c08f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c08f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001c04a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001c04a`

## string_xrefs

- `0x18001c191`: `REGISTRY`

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
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  _OWORD v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  char v26; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v28; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v29[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v30[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v22[0] = &ATL::CRegObject::`vftable';
  v22[1] = 0;
  v22[2] = 0;
  v23 = 0;
  memset(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v24);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v22);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v22,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v22);
  if ( Error >= 0 )
  {
    v20 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
      goto LABEL_24;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
      Error = -2147024774;
      goto LABEL_24;
    }
    ATL::CAtlModule::EscapeSingleQuote(v30, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v28 = 34;
      if ( !ocscpy_s(v29, v14, v30) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        Error = -2147467259;
        goto LABEL_24;
      }
      v17 = -1;
      do
        ++v17;
      while ( v29[v17 - 1] );
      v29[(int)v17 - 1] = 34;
      v18 = 2LL * (int)v17 + 2;
      if ( v18 >= 0x418 )
        _report_rangecheckfailure(v18, v16);
      *(unsigned __int16 *)((char *)&v29[-1] + v18) = 0;
      v15 = &v28;
    }
    else
    {
      v15 = v30;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v22, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v22, L"Module_Raw", v30);
    if ( Error < 0 )
      goto LABEL_23;
    v21 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v19 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v22, Filename, a2, L"REGISTRY", 1);
LABEL_30:
        Error = v19;
LABEL_32:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
        goto LABEL_23;
      }
    }
    else if ( a2 )
    {
      v19 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v22, Filename, a2, L"REGISTRY", 0);
      goto LABEL_30;
    }
    Error = -2147024809;
    goto LABEL_32;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v22);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001bf44  push    rbp
0x18001bf46  push    rbx
0x18001bf47  push    rsi
0x18001bf48  push    rdi
0x18001bf49  push    r12
0x18001bf4b  push    r14
0x18001bf4d  push    r15
0x18001bf4f  lea     rbp, [rsp-9E0h]
0x18001bf57  sub     rsp, 0AE0h
0x18001bf5e  mov     rax, cs:__security_cookie
0x18001bf65  xor     rax, rsp
0x18001bf68  mov     [rbp+0A10h+var_40], rax
0x18001bf6f  mov     rbx, r9
0x18001bf72  mov     r15d, r8d
0x18001bf75  mov     rdi, rdx
0x18001bf78  mov     r14, rcx
0x18001bf7b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001bf82  mov     [rsp+0B10h+var_AD0], rax
0x18001bf87  xor     r12d, r12d
0x18001bf8a  mov     [rsp+0B10h+var_AC8], r12
0x18001bf8f  mov     [rsp+0B10h+var_AC0], r12
0x18001bf94  mov     [rsp+0B10h+var_AB8], r12d
0x18001bf99  xorps   xmm0, xmm0
0x18001bf9c  xor     eax, eax
0x18001bf9e  movups  [rsp+0B10h+var_AB0], xmm0
0x18001bfa3  movups  [rsp+0B10h+var_AA0], xmm0
0x18001bfa8  mov     [rbp+0A10h+var_A90], rax
0x18001bfac  mov     [rbp+0A10h+var_A88], r12b
0x18001bfb0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001bfb5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001bfba  mov     esi, eax
0x18001bfbc  test    eax, eax
0x18001bfbe  jns     short loc_18001BFED
0x18001bfc0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bfc5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001bfca  mov     eax, esi
0x18001bfcc  mov     rcx, [rbp+0A10h+var_40]
0x18001bfd3  xor     rcx, rsp; StackCookie
0x18001bfd6  call    __security_check_cookie
0x18001bfdb  add     rsp, 0AE0h
0x18001bfe2  pop     r15
0x18001bfe4  pop     r14
0x18001bfe6  pop     r12
0x18001bfe8  pop     rdi
0x18001bfe9  pop     rsi
0x18001bfea  pop     rbx
0x18001bfeb  pop     rbp
0x18001bfec  retn
0x18001bfed  test    rbx, rbx
0x18001bff0  jz      short loc_18001C011
0x18001bff2  jmp     short loc_18001C009
0x18001bff4  mov     r8, [rbx+8]; unsigned __int16 *
0x18001bff8  mov     rdx, rax; unsigned __int16 *
0x18001bffb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c000  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001c005  lea     rbx, [rbx+10h]
0x18001c009  mov     rax, [rbx]
0x18001c00c  test    rax, rax
0x18001c00f  jnz     short loc_18001BFF4
0x18001c011  mov     rax, [r14]
0x18001c014  lea     rdx, [rsp+0B10h+var_AD0]
0x18001c019  mov     rcx, r14
0x18001c01c  mov     rax, [rax+28h]
0x18001c020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c025  mov     ebx, eax
0x18001c027  test    eax, eax
0x18001c029  js      loc_18001C15D
0x18001c02f  mov     [rsp+0B10h+var_AE0], r12
0x18001c034  mov     rbx, cs:hModule
0x18001c03b  mov     esi, 104h
0x18001c040  mov     r8d, esi; nSize
0x18001c043  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001c047  mov     rcx, rbx; hModule
0x18001c04a  call    cs:__imp_GetModuleFileNameW
0x18001c050  test    eax, eax
0x18001c052  jnz     short loc_18001C060
0x18001c054  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001c059  mov     ebx, eax
0x18001c05b  jmp     loc_18001C153
0x18001c060  cmp     eax, esi
0x18001c062  jnz     short loc_18001C078
0x18001c064  lea     rcx, [rsp+0B10h+var_AE0]
0x18001c069  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001c06e  mov     ebx, 8007007Ah
0x18001c073  jmp     loc_18001C15D
0x18001c078  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001c07c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001c083  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001c088  test    rbx, rbx
0x18001c08b  jz      short loc_18001C0A3
0x18001c08d  xor     ecx, ecx; lpModuleName
0x18001c08f  call    cs:__imp_GetModuleHandleW
0x18001c095  cmp     rbx, rax
0x18001c098  jz      short loc_18001C0A3
0x18001c09a  lea     r8, [rbp+0A10h+var_450]
0x18001c0a1  jmp     short loc_18001C11E
0x18001c0a3  mov     ebx, 22h ; '"'
0x18001c0a8  mov     [rbp+0A10h+var_870], bx
0x18001c0af  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001c0b6  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001c0bd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001c0c2  test    al, al
0x18001c0c4  jnz     short loc_18001C0DA
0x18001c0c6  lea     rcx, [rsp+0B10h+var_AE0]
0x18001c0cb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001c0d0  mov     ebx, 80004005h
0x18001c0d5  jmp     loc_18001C15D
0x18001c0da  lea     rcx, [rbp+0A10h+var_870]
0x18001c0e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c0e5  inc     rax
0x18001c0e8  cmp     [rcx+rax*2], r12w
0x18001c0ed  jnz     short loc_18001C0E5
0x18001c0ef  cdqe
0x18001c0f1  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001c0f9  lea     rcx, ds:2[rax*2]
0x18001c101  cmp     rcx, 418h
0x18001c108  jnb     loc_18001C1BE
0x18001c10e  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001c117  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001c11e  lea     rdx, aModule; "Module"
0x18001c125  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c12a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001c12f  mov     ebx, eax
0x18001c131  test    eax, eax
0x18001c133  js      short loc_18001C153
0x18001c135  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001c13c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001c143  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c148  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001c14d  mov     ebx, eax
0x18001c14f  test    eax, eax
0x18001c151  jns     short loc_18001C16E
0x18001c153  lea     rcx, [rsp+0B10h+var_AE0]
0x18001c158  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001c15d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c162  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001c167  mov     eax, ebx
0x18001c169  jmp     loc_18001BFCC
0x18001c16e  mov     [rsp+0B10h+var_AD8], r12
0x18001c173  test    r15d, r15d
0x18001c176  jz      short loc_18001C187
0x18001c178  test    rdi, rdi
0x18001c17b  jz      short loc_18001C1AD
0x18001c17d  mov     [rsp+0B10h+var_AF0], 1
0x18001c185  jmp     short loc_18001C191
0x18001c187  test    rdi, rdi
0x18001c18a  jz      short loc_18001C1AD
0x18001c18c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001c191  lea     r9, aRegistry; "REGISTRY"
0x18001c198  mov     r8, rdi; unsigned __int16 *
0x18001c19b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001c19f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001c1a4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001c1a9  mov     ebx, eax
0x18001c1ab  jmp     short loc_18001C1B2
0x18001c1ad  mov     ebx, 80070057h
0x18001c1b2  lea     rcx, [rsp+0B10h+var_AD8]
0x18001c1b7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001c1bc  jmp     short loc_18001C153
0x18001c1be  call    __report_rangecheckfailure
```
