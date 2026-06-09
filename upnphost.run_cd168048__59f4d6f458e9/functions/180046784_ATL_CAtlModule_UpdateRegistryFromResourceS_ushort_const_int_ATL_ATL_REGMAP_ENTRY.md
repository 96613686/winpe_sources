# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180046784`
- end: `0x180046a11`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `653`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180046a30`

## callees

- `0x18003cb60`
- `0x18003cba0`
- `0x18003ec5c`
- `0x18003f3c4`
- `0x180040000`
- `0x18004062c`
- `0x18004173c`
- `0x18004260c`
- `0x180044270`
- `0x180046784`
- `0x180047044`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004688b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004688b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800468d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800468d6`

## string_xrefs

- `0x1800469de`: `REGISTRY`

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
    v11 = hModule;
    v19 = 0;
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
0x180046784  push    rbp
0x180046786  push    rbx
0x180046787  push    rsi
0x180046788  push    rdi
0x180046789  push    r12
0x18004678b  push    r14
0x18004678d  push    r15
0x18004678f  lea     rbp, [rsp-9E0h]
0x180046797  sub     rsp, 0AE0h
0x18004679e  mov     rax, cs:__security_cookie
0x1800467a5  xor     rax, rsp
0x1800467a8  mov     [rbp+0A10h+var_40], rax
0x1800467af  xor     r12d, r12d
0x1800467b2  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800467b9  xorps   xmm0, xmm0
0x1800467bc  mov     [rsp+0B10h+var_AD0], rax
0x1800467c1  xor     eax, eax
0x1800467c3  mov     [rsp+0B10h+var_AC8], r12
0x1800467c8  mov     r14, rcx
0x1800467cb  mov     [rbp+0A10h+var_A90], rax
0x1800467cf  lea     rcx, [rsp+0B10h+var_AB0]; this
0x1800467d4  mov     [rsp+0B10h+var_AC0], r12
0x1800467d9  mov     rbx, r9
0x1800467dc  mov     [rsp+0B10h+var_AB8], r12d
0x1800467e1  mov     r15d, r8d
0x1800467e4  mov     [rbp+0A10h+var_A88], r12b
0x1800467e8  mov     rdi, rdx
0x1800467eb  movups  [rsp+0B10h+var_AB0], xmm0
0x1800467f0  movups  [rsp+0B10h+var_AA0], xmm0
0x1800467f5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800467fa  mov     esi, eax
0x1800467fc  test    eax, eax
0x1800467fe  jns     short loc_18004682E
0x180046800  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180046805  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18004680a  mov     eax, esi
0x18004680c  mov     rcx, [rbp+0A10h+var_40]
0x180046813  xor     rcx, rsp; StackCookie
0x180046816  call    __security_check_cookie
0x18004681b  add     rsp, 0AE0h
0x180046822  pop     r15
0x180046824  pop     r14
0x180046826  pop     r12
0x180046828  pop     rdi
0x180046829  pop     rsi
0x18004682a  pop     rbx
0x18004682b  pop     rbp
0x18004682c  retn
0x18004682e  test    rbx, rbx
0x180046831  jz      short loc_180046852
0x180046833  jmp     short loc_18004684A
0x180046835  mov     r8, [rbx+8]; unsigned __int16 *
0x180046839  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18004683e  mov     rdx, rax; unsigned __int16 *
0x180046841  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180046846  lea     rbx, [rbx+10h]
0x18004684a  mov     rax, [rbx]
0x18004684d  test    rax, rax
0x180046850  jnz     short loc_180046835
0x180046852  mov     rax, [r14]
0x180046855  lea     rdx, [rsp+0B10h+var_AD0]
0x18004685a  mov     rcx, r14
0x18004685d  mov     rax, [rax+28h]
0x180046861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046866  mov     ebx, eax
0x180046868  test    eax, eax
0x18004686a  js      loc_1800469AA
0x180046870  mov     rbx, cs:hModule
0x180046877  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18004687b  mov     esi, 104h
0x180046880  mov     [rsp+0B10h+var_AE0], r12
0x180046885  mov     r8d, esi; nSize
0x180046888  mov     rcx, rbx; hModule
0x18004688b  call    cs:__imp_GetModuleFileNameW
0x180046892  nop     dword ptr [rax+rax+00h]
0x180046897  test    eax, eax
0x180046899  jnz     short loc_1800468A7
0x18004689b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800468a0  mov     ebx, eax
0x1800468a2  jmp     loc_1800469A0
0x1800468a7  cmp     eax, esi
0x1800468a9  jnz     short loc_1800468BF
0x1800468ab  lea     rcx, [rsp+0B10h+var_AE0]
0x1800468b0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800468b5  mov     ebx, 8007007Ah
0x1800468ba  jmp     loc_1800469AA
0x1800468bf  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800468c3  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800468ca  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800468cf  test    rbx, rbx
0x1800468d2  jz      short loc_1800468F0
0x1800468d4  xor     ecx, ecx; lpModuleName
0x1800468d6  call    cs:__imp_GetModuleHandleW
0x1800468dd  nop     dword ptr [rax+rax+00h]
0x1800468e2  cmp     rbx, rax
0x1800468e5  jz      short loc_1800468F0
0x1800468e7  lea     r8, [rbp+0A10h+var_450]
0x1800468ee  jmp     short loc_18004696B
0x1800468f0  mov     ebx, 22h ; '"'
0x1800468f5  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800468fc  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180046903  mov     [rbp+0A10h+var_870], bx
0x18004690a  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18004690f  test    al, al
0x180046911  jnz     short loc_180046927
0x180046913  lea     rcx, [rsp+0B10h+var_AE0]
0x180046918  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18004691d  mov     ebx, 80004005h
0x180046922  jmp     loc_1800469AA
0x180046927  lea     rcx, [rbp+0A10h+var_870]
0x18004692e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046932  inc     rax
0x180046935  cmp     [rcx+rax*2], r12w
0x18004693a  jnz     short loc_180046932
0x18004693c  cdqe
0x18004693e  lea     rcx, ds:2[rax*2]
0x180046946  mov     [rbp+rax*2+0A10h+var_870], bx
0x18004694e  cmp     rcx, 418h
0x180046955  jnb     loc_180046A0B
0x18004695b  mov     [rbp+rcx+0A10h+var_870], r12w
0x180046964  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18004696b  lea     rdx, aModule; "Module"
0x180046972  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180046977  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18004697c  mov     ebx, eax
0x18004697e  test    eax, eax
0x180046980  js      short loc_1800469A0
0x180046982  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180046989  lea     rdx, aModuleRaw; "Module_Raw"
0x180046990  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180046995  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18004699a  mov     ebx, eax
0x18004699c  test    eax, eax
0x18004699e  jns     short loc_1800469BB
0x1800469a0  lea     rcx, [rsp+0B10h+var_AE0]
0x1800469a5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800469aa  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800469af  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800469b4  mov     eax, ebx
0x1800469b6  jmp     loc_18004680C
0x1800469bb  mov     [rsp+0B10h+var_AD8], r12
0x1800469c0  test    r15d, r15d
0x1800469c3  jz      short loc_1800469D4
0x1800469c5  test    rdi, rdi
0x1800469c8  jz      short loc_1800469FA
0x1800469ca  mov     [rsp+0B10h+var_AF0], 1
0x1800469d2  jmp     short loc_1800469DE
0x1800469d4  test    rdi, rdi
0x1800469d7  jz      short loc_1800469FA
0x1800469d9  mov     [rsp+0B10h+var_AF0], r12d; int
0x1800469de  lea     r9, aRegistry; "REGISTRY"
0x1800469e5  mov     r8, rdi; unsigned __int16 *
0x1800469e8  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x1800469ec  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800469f1  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800469f6  mov     ebx, eax
0x1800469f8  jmp     short loc_1800469FF
0x1800469fa  mov     ebx, 80070057h
0x1800469ff  lea     rcx, [rsp+0B10h+var_AD8]
0x180046a04  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180046a09  jmp     short loc_1800469A0
0x180046a0b  call    __report_rangecheckfailure
```
