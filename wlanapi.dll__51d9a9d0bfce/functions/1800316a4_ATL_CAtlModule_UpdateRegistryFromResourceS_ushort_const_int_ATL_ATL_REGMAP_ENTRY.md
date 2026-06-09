# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800316a4`
- end: `0x180031924`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180031940`

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
- `0x1800316a4`
- `0x180031964`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800317aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800317aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800317ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800317ef`

## string_xrefs

- `0x1800318f1`: `REGISTRY`

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
0x1800316a4  push    rbp
0x1800316a6  push    rbx
0x1800316a7  push    rsi
0x1800316a8  push    rdi
0x1800316a9  push    r12
0x1800316ab  push    r14
0x1800316ad  push    r15
0x1800316af  lea     rbp, [rsp-9E0h]
0x1800316b7  sub     rsp, 0AE0h
0x1800316be  mov     rax, cs:__security_cookie
0x1800316c5  xor     rax, rsp
0x1800316c8  mov     [rbp+0A10h+var_40], rax
0x1800316cf  mov     rbx, r9
0x1800316d2  mov     r15d, r8d
0x1800316d5  mov     rdi, rdx
0x1800316d8  mov     r14, rcx
0x1800316db  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800316e2  mov     [rsp+0B10h+var_AD0], rax
0x1800316e7  xor     r12d, r12d
0x1800316ea  mov     [rsp+0B10h+var_AC8], r12
0x1800316ef  mov     [rsp+0B10h+var_AC0], r12
0x1800316f4  mov     [rsp+0B10h+var_AB8], r12d
0x1800316f9  xorps   xmm0, xmm0
0x1800316fc  xor     eax, eax
0x1800316fe  movups  [rsp+0B10h+var_AB0], xmm0
0x180031703  movups  [rsp+0B10h+var_AA0], xmm0
0x180031708  mov     [rbp+0A10h+var_A90], rax
0x18003170c  mov     [rbp+0A10h+var_A88], r12b
0x180031710  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180031715  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18003171a  mov     esi, eax
0x18003171c  test    eax, eax
0x18003171e  jns     short loc_18003174D
0x180031720  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180031725  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18003172a  mov     eax, esi
0x18003172c  mov     rcx, [rbp+0A10h+var_40]
0x180031733  xor     rcx, rsp; StackCookie
0x180031736  call    __security_check_cookie
0x18003173b  add     rsp, 0AE0h
0x180031742  pop     r15
0x180031744  pop     r14
0x180031746  pop     r12
0x180031748  pop     rdi
0x180031749  pop     rsi
0x18003174a  pop     rbx
0x18003174b  pop     rbp
0x18003174c  retn
0x18003174d  test    rbx, rbx
0x180031750  jz      short loc_180031771
0x180031752  jmp     short loc_180031769
0x180031754  mov     r8, [rbx+8]; unsigned __int16 *
0x180031758  mov     rdx, rax; unsigned __int16 *
0x18003175b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180031760  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180031765  lea     rbx, [rbx+10h]
0x180031769  mov     rax, [rbx]
0x18003176c  test    rax, rax
0x18003176f  jnz     short loc_180031754
0x180031771  mov     rax, [r14]
0x180031774  lea     rdx, [rsp+0B10h+var_AD0]
0x180031779  mov     rcx, r14
0x18003177c  mov     rax, [rax+28h]
0x180031780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031785  mov     ebx, eax
0x180031787  test    eax, eax
0x180031789  js      loc_1800318BD
0x18003178f  mov     [rsp+0B10h+var_AE0], r12
0x180031794  mov     rbx, cs:hModule
0x18003179b  mov     esi, 104h
0x1800317a0  mov     r8d, esi; nSize
0x1800317a3  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800317a7  mov     rcx, rbx; hModule
0x1800317aa  call    cs:__imp_GetModuleFileNameW
0x1800317b0  test    eax, eax
0x1800317b2  jnz     short loc_1800317C0
0x1800317b4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800317b9  mov     ebx, eax
0x1800317bb  jmp     loc_1800318B3
0x1800317c0  cmp     eax, esi
0x1800317c2  jnz     short loc_1800317D8
0x1800317c4  lea     rcx, [rsp+0B10h+var_AE0]
0x1800317c9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800317ce  mov     ebx, 8007007Ah
0x1800317d3  jmp     loc_1800318BD
0x1800317d8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800317dc  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800317e3  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800317e8  test    rbx, rbx
0x1800317eb  jz      short loc_180031803
0x1800317ed  xor     ecx, ecx; lpModuleName
0x1800317ef  call    cs:__imp_GetModuleHandleW
0x1800317f5  cmp     rbx, rax
0x1800317f8  jz      short loc_180031803
0x1800317fa  lea     r8, [rbp+0A10h+var_450]
0x180031801  jmp     short loc_18003187E
0x180031803  mov     ebx, 22h ; '"'
0x180031808  mov     [rbp+0A10h+var_870], bx
0x18003180f  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180031816  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18003181d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180031822  test    al, al
0x180031824  jnz     short loc_18003183A
0x180031826  lea     rcx, [rsp+0B10h+var_AE0]
0x18003182b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180031830  mov     ebx, 80004005h
0x180031835  jmp     loc_1800318BD
0x18003183a  lea     rcx, [rbp+0A10h+var_870]
0x180031841  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031845  inc     rax
0x180031848  cmp     [rcx+rax*2], r12w
0x18003184d  jnz     short loc_180031845
0x18003184f  cdqe
0x180031851  mov     [rbp+rax*2+0A10h+var_870], bx
0x180031859  lea     rcx, ds:2[rax*2]
0x180031861  cmp     rcx, 418h
0x180031868  jnb     loc_18003191E
0x18003186e  mov     [rbp+rcx+0A10h+var_870], r12w
0x180031877  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18003187e  lea     rdx, aModule; "Module"
0x180031885  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18003188a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18003188f  mov     ebx, eax
0x180031891  test    eax, eax
0x180031893  js      short loc_1800318B3
0x180031895  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18003189c  lea     rdx, aModuleRaw; "Module_Raw"
0x1800318a3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800318a8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800318ad  mov     ebx, eax
0x1800318af  test    eax, eax
0x1800318b1  jns     short loc_1800318CE
0x1800318b3  lea     rcx, [rsp+0B10h+var_AE0]
0x1800318b8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800318bd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800318c2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800318c7  mov     eax, ebx
0x1800318c9  jmp     loc_18003172C
0x1800318ce  mov     [rsp+0B10h+var_AD8], r12
0x1800318d3  test    r15d, r15d
0x1800318d6  jz      short loc_1800318E7
0x1800318d8  test    rdi, rdi
0x1800318db  jz      short loc_18003190D
0x1800318dd  mov     [rsp+0B10h+var_AF0], 1
0x1800318e5  jmp     short loc_1800318F1
0x1800318e7  test    rdi, rdi
0x1800318ea  jz      short loc_18003190D
0x1800318ec  mov     [rsp+0B10h+var_AF0], r12d; int
0x1800318f1  lea     r9, aRegistry; "REGISTRY"
0x1800318f8  mov     r8, rdi; unsigned __int16 *
0x1800318fb  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800318ff  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180031904  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180031909  mov     ebx, eax
0x18003190b  jmp     short loc_180031912
0x18003190d  mov     ebx, 80070057h
0x180031912  lea     rcx, [rsp+0B10h+var_AD8]
0x180031917  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003191c  jmp     short loc_1800318B3
0x18003191e  call    __report_rangecheckfailure
```
