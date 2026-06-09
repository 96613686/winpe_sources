# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18003142c`
- end: `0x18003169c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180031930`

## callees

- `0x180019a20`
- `0x180019e50`
- `0x18002f054`
- `0x18002f17c`
- `0x18002f530`
- `0x18002fb5c`
- `0x18002ffc4`
- `0x1800301ec`
- `0x18003091c`
- `0x18003142c`
- `0x180031964`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180031532`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180031532`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031577`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031577`

## string_xrefs

- `0x18003165f`: `REGISTRY`

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
0x18003142c  push    rbp
0x18003142e  push    rbx
0x18003142f  push    rsi
0x180031430  push    rdi
0x180031431  push    r12
0x180031433  push    r14
0x180031435  push    r15
0x180031437  lea     rbp, [rsp-9E0h]
0x18003143f  sub     rsp, 0AE0h
0x180031446  mov     rax, cs:__security_cookie
0x18003144d  xor     rax, rsp
0x180031450  mov     [rbp+0A10h+var_40], rax
0x180031457  mov     rbx, r9
0x18003145a  mov     r14d, r8d
0x18003145d  mov     r15d, edx
0x180031460  mov     rsi, rcx
0x180031463  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18003146a  mov     [rsp+0B10h+var_AD0], rax
0x18003146f  xor     r12d, r12d
0x180031472  mov     [rsp+0B10h+var_AC8], r12
0x180031477  mov     [rsp+0B10h+var_AC0], r12
0x18003147c  mov     [rsp+0B10h+var_AB8], r12d
0x180031481  xorps   xmm0, xmm0
0x180031484  xor     eax, eax
0x180031486  movups  [rsp+0B10h+var_AB0], xmm0
0x18003148b  movups  [rsp+0B10h+var_AA0], xmm0
0x180031490  mov     [rbp+0A10h+var_A90], rax
0x180031494  mov     [rbp+0A10h+var_A88], r12b
0x180031498  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18003149d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800314a2  mov     edi, eax
0x1800314a4  test    eax, eax
0x1800314a6  jns     short loc_1800314D5
0x1800314a8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800314ad  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800314b2  mov     eax, edi
0x1800314b4  mov     rcx, [rbp+0A10h+var_40]
0x1800314bb  xor     rcx, rsp; StackCookie
0x1800314be  call    __security_check_cookie
0x1800314c3  add     rsp, 0AE0h
0x1800314ca  pop     r15
0x1800314cc  pop     r14
0x1800314ce  pop     r12
0x1800314d0  pop     rdi
0x1800314d1  pop     rsi
0x1800314d2  pop     rbx
0x1800314d3  pop     rbp
0x1800314d4  retn
0x1800314d5  test    rbx, rbx
0x1800314d8  jz      short loc_1800314F9
0x1800314da  jmp     short loc_1800314F1
0x1800314dc  mov     r8, [rbx+8]; unsigned __int16 *
0x1800314e0  mov     rdx, rax; unsigned __int16 *
0x1800314e3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800314e8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800314ed  lea     rbx, [rbx+10h]
0x1800314f1  mov     rax, [rbx]
0x1800314f4  test    rax, rax
0x1800314f7  jnz     short loc_1800314DC
0x1800314f9  mov     rax, [rsi]
0x1800314fc  lea     rdx, [rsp+0B10h+var_AD0]
0x180031501  mov     rcx, rsi
0x180031504  mov     rax, [rax+28h]
0x180031508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003150d  mov     ebx, eax
0x18003150f  test    eax, eax
0x180031511  js      loc_180031645
0x180031517  mov     [rsp+0B10h+var_AE0], r12
0x18003151c  mov     rbx, cs:hModule
0x180031523  mov     edi, 104h
0x180031528  mov     r8d, edi; nSize
0x18003152b  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18003152f  mov     rcx, rbx; hModule
0x180031532  call    cs:__imp_GetModuleFileNameW
0x180031538  test    eax, eax
0x18003153a  jnz     short loc_180031548
0x18003153c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180031541  mov     ebx, eax
0x180031543  jmp     loc_18003163B
0x180031548  cmp     eax, edi
0x18003154a  jnz     short loc_180031560
0x18003154c  lea     rcx, [rsp+0B10h+var_AE0]
0x180031551  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180031556  mov     ebx, 8007007Ah
0x18003155b  jmp     loc_180031645
0x180031560  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180031564  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18003156b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180031570  test    rbx, rbx
0x180031573  jz      short loc_18003158B
0x180031575  xor     ecx, ecx; lpModuleName
0x180031577  call    cs:__imp_GetModuleHandleW
0x18003157d  cmp     rbx, rax
0x180031580  jz      short loc_18003158B
0x180031582  lea     r8, [rbp+0A10h+var_450]
0x180031589  jmp     short loc_180031606
0x18003158b  mov     ebx, 22h ; '"'
0x180031590  mov     [rbp+0A10h+var_870], bx
0x180031597  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18003159e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x1800315a5  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x1800315aa  test    al, al
0x1800315ac  jnz     short loc_1800315C2
0x1800315ae  lea     rcx, [rsp+0B10h+var_AE0]
0x1800315b3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800315b8  mov     ebx, 80004005h
0x1800315bd  jmp     loc_180031645
0x1800315c2  lea     rcx, [rbp+0A10h+var_870]
0x1800315c9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800315cd  inc     rax
0x1800315d0  cmp     [rcx+rax*2], r12w
0x1800315d5  jnz     short loc_1800315CD
0x1800315d7  cdqe
0x1800315d9  mov     [rbp+rax*2+0A10h+var_870], bx
0x1800315e1  lea     rcx, ds:2[rax*2]
0x1800315e9  cmp     rcx, 418h
0x1800315f0  jnb     loc_180031696
0x1800315f6  mov     [rbp+rcx+0A10h+var_870], r12w
0x1800315ff  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180031606  lea     rdx, aModule; "Module"
0x18003160d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180031612  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180031617  mov     ebx, eax
0x180031619  test    eax, eax
0x18003161b  js      short loc_18003163B
0x18003161d  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180031624  lea     rdx, aModuleRaw; "Module_Raw"
0x18003162b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180031630  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180031635  mov     ebx, eax
0x180031637  test    eax, eax
0x180031639  jns     short loc_180031656
0x18003163b  lea     rcx, [rsp+0B10h+var_AE0]
0x180031640  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180031645  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18003164a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18003164f  mov     eax, ebx
0x180031651  jmp     loc_1800314B4
0x180031656  movzx   r8d, r15w; unsigned __int16 *
0x18003165a  mov     [rsp+0B10h+var_AD8], r12
0x18003165f  lea     r9, aRegistry; "REGISTRY"
0x180031666  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18003166a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18003166f  test    r14d, r14d
0x180031672  jz      short loc_18003167E
0x180031674  mov     [rsp+0B10h+var_AF0], 1
0x18003167c  jmp     short loc_180031683
0x18003167e  mov     [rsp+0B10h+var_AF0], r12d; int
0x180031683  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180031688  mov     ebx, eax
0x18003168a  lea     rcx, [rsp+0B10h+var_AD8]
0x18003168f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180031694  jmp     short loc_18003163B
0x180031696  call    __report_rangecheckfailure
```
