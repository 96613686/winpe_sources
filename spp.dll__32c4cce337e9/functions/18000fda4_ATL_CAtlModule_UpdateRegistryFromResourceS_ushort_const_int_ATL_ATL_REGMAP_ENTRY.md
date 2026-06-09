# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000fda4`
- end: `0x180010024`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010040`

## callees

- `0x180001b98`
- `0x180002274`
- `0x18000282c`
- `0x180002f10`
- `0x180004528`
- `0x180008604`
- `0x18000c784`
- `0x18000d3ec`
- `0x18000fda4`
- `0x180020448`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000feef`
- `KERNEL32!GetModuleHandleW` at `0x18000feef`
- `KERNEL32!GetModuleFileNameW` at `0x18000feaa`
- `KERNEL32!GetModuleFileNameW` at `0x18000feaa`

## string_xrefs

- `0x18000fff1`: `REGISTRY`

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
  v24 = 0;
  v21[2] = 0;
  v22 = 0;
  v25 = 0;
  memset(v23, 0, sizeof(v23));
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
    v11 = hInstance;
    v19 = 0;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
      v17 = 2LL * (int)v16 + 2;
      v28[(int)v16 - 1] = 34;
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
0x18000fda4  push    rbp
0x18000fda6  push    rbx
0x18000fda7  push    rsi
0x18000fda8  push    rdi
0x18000fda9  push    r12
0x18000fdab  push    r14
0x18000fdad  push    r15
0x18000fdaf  lea     rbp, [rsp-9E0h]
0x18000fdb7  sub     rsp, 0AE0h
0x18000fdbe  mov     rax, cs:__security_cookie
0x18000fdc5  xor     rax, rsp
0x18000fdc8  mov     [rbp+0A10h+var_40], rax
0x18000fdcf  xor     r12d, r12d
0x18000fdd2  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000fdd9  xorps   xmm0, xmm0
0x18000fddc  mov     [rsp+0B10h+var_AD0], rax
0x18000fde1  xor     eax, eax
0x18000fde3  mov     [rsp+0B10h+var_AC8], r12
0x18000fde8  mov     r14, rcx
0x18000fdeb  mov     [rbp+0A10h+var_A90], rax
0x18000fdef  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000fdf4  mov     [rsp+0B10h+var_AC0], r12
0x18000fdf9  mov     rbx, r9
0x18000fdfc  mov     [rsp+0B10h+var_AB8], r12d
0x18000fe01  mov     r15d, r8d
0x18000fe04  mov     [rbp+0A10h+var_A88], r12b
0x18000fe08  mov     rdi, rdx
0x18000fe0b  movups  [rsp+0B10h+var_AB0], xmm0
0x18000fe10  movups  [rsp+0B10h+var_AA0], xmm0
0x18000fe15  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000fe1a  mov     esi, eax
0x18000fe1c  test    eax, eax
0x18000fe1e  jns     short loc_18000FE4D
0x18000fe20  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fe25  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000fe2a  mov     eax, esi
0x18000fe2c  mov     rcx, [rbp+0A10h+var_40]
0x18000fe33  xor     rcx, rsp; StackCookie
0x18000fe36  call    __security_check_cookie
0x18000fe3b  add     rsp, 0AE0h
0x18000fe42  pop     r15
0x18000fe44  pop     r14
0x18000fe46  pop     r12
0x18000fe48  pop     rdi
0x18000fe49  pop     rsi
0x18000fe4a  pop     rbx
0x18000fe4b  pop     rbp
0x18000fe4c  retn
0x18000fe4d  test    rbx, rbx
0x18000fe50  jz      short loc_18000FE71
0x18000fe52  jmp     short loc_18000FE69
0x18000fe54  mov     r8, [rbx+8]; unsigned __int16 *
0x18000fe58  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fe5d  mov     rdx, rax; unsigned __int16 *
0x18000fe60  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000fe65  lea     rbx, [rbx+10h]
0x18000fe69  mov     rax, [rbx]
0x18000fe6c  test    rax, rax
0x18000fe6f  jnz     short loc_18000FE54
0x18000fe71  mov     rax, [r14]
0x18000fe74  lea     rdx, [rsp+0B10h+var_AD0]
0x18000fe79  mov     rcx, r14
0x18000fe7c  mov     rax, [rax+28h]
0x18000fe80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe85  mov     ebx, eax
0x18000fe87  test    eax, eax
0x18000fe89  js      loc_18000FFBD
0x18000fe8f  mov     rbx, cs:hInstance
0x18000fe96  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000fe9a  mov     esi, 104h
0x18000fe9f  mov     [rsp+0B10h+var_AE0], r12
0x18000fea4  mov     r8d, esi; nSize
0x18000fea7  mov     rcx, rbx; hModule
0x18000feaa  call    cs:__imp_GetModuleFileNameW
0x18000feb0  test    eax, eax
0x18000feb2  jnz     short loc_18000FEC0
0x18000feb4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000feb9  mov     ebx, eax
0x18000febb  jmp     loc_18000FFB3
0x18000fec0  cmp     eax, esi
0x18000fec2  jnz     short loc_18000FED8
0x18000fec4  lea     rcx, [rsp+0B10h+var_AE0]
0x18000fec9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fece  mov     ebx, 8007007Ah
0x18000fed3  jmp     loc_18000FFBD
0x18000fed8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000fedc  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000fee3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000fee8  test    rbx, rbx
0x18000feeb  jz      short loc_18000FF03
0x18000feed  xor     ecx, ecx; lpModuleName
0x18000feef  call    cs:__imp_GetModuleHandleW
0x18000fef5  cmp     rbx, rax
0x18000fef8  jz      short loc_18000FF03
0x18000fefa  lea     r8, [rbp+0A10h+var_450]
0x18000ff01  jmp     short loc_18000FF7E
0x18000ff03  mov     ebx, 22h ; '"'
0x18000ff08  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000ff0f  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000ff16  mov     [rbp+0A10h+var_870], bx
0x18000ff1d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000ff22  test    al, al
0x18000ff24  jnz     short loc_18000FF3A
0x18000ff26  lea     rcx, [rsp+0B10h+var_AE0]
0x18000ff2b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000ff30  mov     ebx, 80004005h
0x18000ff35  jmp     loc_18000FFBD
0x18000ff3a  lea     rcx, [rbp+0A10h+var_870]
0x18000ff41  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ff45  inc     rax
0x18000ff48  cmp     [rcx+rax*2], r12w
0x18000ff4d  jnz     short loc_18000FF45
0x18000ff4f  cdqe
0x18000ff51  lea     rcx, ds:2[rax*2]
0x18000ff59  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000ff61  cmp     rcx, 418h
0x18000ff68  jnb     loc_18001001E
0x18000ff6e  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000ff77  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000ff7e  lea     rdx, aModule; "Module"
0x18000ff85  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000ff8a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000ff8f  mov     ebx, eax
0x18000ff91  test    eax, eax
0x18000ff93  js      short loc_18000FFB3
0x18000ff95  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000ff9c  lea     rdx, aModuleRaw; "Module_Raw"
0x18000ffa3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000ffa8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000ffad  mov     ebx, eax
0x18000ffaf  test    eax, eax
0x18000ffb1  jns     short loc_18000FFCE
0x18000ffb3  lea     rcx, [rsp+0B10h+var_AE0]
0x18000ffb8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000ffbd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000ffc2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000ffc7  mov     eax, ebx
0x18000ffc9  jmp     loc_18000FE2C
0x18000ffce  mov     [rsp+0B10h+var_AD8], r12
0x18000ffd3  test    r15d, r15d
0x18000ffd6  jz      short loc_18000FFE7
0x18000ffd8  test    rdi, rdi
0x18000ffdb  jz      short loc_18001000D
0x18000ffdd  mov     [rsp+0B10h+var_AF0], 1
0x18000ffe5  jmp     short loc_18000FFF1
0x18000ffe7  test    rdi, rdi
0x18000ffea  jz      short loc_18001000D
0x18000ffec  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000fff1  lea     r9, aRegistry; "REGISTRY"
0x18000fff8  mov     r8, rdi; unsigned __int16 *
0x18000fffb  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000ffff  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180010004  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180010009  mov     ebx, eax
0x18001000b  jmp     short loc_180010012
0x18001000d  mov     ebx, 80070057h
0x180010012  lea     rcx, [rsp+0B10h+var_AD8]
0x180010017  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001001c  jmp     short loc_18000FFB3
0x18001001e  call    __report_rangecheckfailure
```
