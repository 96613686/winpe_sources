# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000830c`
- end: `0x180008583`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `631`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800082f0`
- `0x180008820`

## callees

- `0x180001b50`
- `0x180002570`
- `0x1800025e0`
- `0x180005798`
- `0x1800058f8`
- `0x180005da0`
- `0x18000655c`
- `0x180006d68`
- `0x18000764c`
- `0x18000830c`
- `0x18000883c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800083ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800083ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000843b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000843b`

## string_xrefs

- `0x180008510`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // eax
  int Error; // ebx
  HMODULE v10; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int16 *v14; // r8
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  int v17; // eax
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
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v23);
  if ( v8 < 0 )
  {
    Error = v8;
    goto LABEL_28;
  }
  v25 = 1;
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
    v10 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147024774;
        goto LABEL_28;
      }
      ATL::CAtlModule::EscapeSingleQuote(v29, v12, Filename);
      if ( !v10 || v10 == GetModuleHandleW(0) )
      {
        v27 = 34;
        if ( !ocscpy_s(v28, v13, v29) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_28;
        }
        v15 = -1;
        do
          ++v15;
        while ( v28[v15 - 1] );
        v28[(int)v15 - 1] = 34;
        v16 = 2LL * (int)v15 + 2;
        if ( v16 >= 0x418 )
          _report_rangecheckfailure();
        *(unsigned __int16 *)((char *)&v28[-1] + v16) = 0;
        v14 = &v27;
      }
      else
      {
        v14 = v29;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v14);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v17 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v17 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v17;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  }
LABEL_28:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000830c  mov     [rsp-8+arg_10], rbx
0x180008311  push    rbp
0x180008312  push    rsi
0x180008313  push    rdi
0x180008314  push    r14
0x180008316  push    r15
0x180008318  lea     rbp, [rsp-9E0h]
0x180008320  sub     rsp, 0AE0h
0x180008327  mov     rax, cs:__security_cookie
0x18000832e  xor     rax, rsp
0x180008331  mov     [rbp+0A00h+var_30], rax
0x180008338  mov     rbx, r9
0x18000833b  mov     esi, r8d
0x18000833e  mov     r14d, edx
0x180008341  mov     rdi, rcx
0x180008344  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000834b  mov     [rsp+0B00h+var_AC0], rax
0x180008350  xor     r15d, r15d
0x180008353  mov     [rsp+0B00h+var_AB8], r15
0x180008358  mov     [rsp+0B00h+var_AB0], r15
0x18000835d  mov     [rsp+0B00h+var_AA8], r15d
0x180008362  xorps   xmm0, xmm0
0x180008365  xor     eax, eax
0x180008367  movups  [rsp+0B00h+var_AA0], xmm0
0x18000836c  movups  [rsp+0B00h+var_A90], xmm0
0x180008371  mov     [rbp+0A00h+var_A80], rax
0x180008375  mov     [rbp+0A00h+var_A78], r15b
0x180008379  lea     rcx, [rsp+0B00h+var_AA0]; this
0x18000837e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008383  test    eax, eax
0x180008385  js      loc_180008549
0x18000838b  mov     [rbp+0A00h+var_A78], 1
0x18000838f  test    rbx, rbx
0x180008392  jz      short loc_1800083B3
0x180008394  jmp     short loc_1800083AB
0x180008396  mov     r8, [rbx+8]; unsigned __int16 *
0x18000839a  mov     rdx, rax; unsigned __int16 *
0x18000839d  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800083a2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800083a7  lea     rbx, [rbx+10h]
0x1800083ab  mov     rax, [rbx]
0x1800083ae  test    rax, rax
0x1800083b1  jnz     short loc_180008396
0x1800083b3  mov     rax, [rdi]
0x1800083b6  lea     rdx, [rsp+0B00h+var_AC0]
0x1800083bb  mov     rcx, rdi
0x1800083be  mov     rax, [rax+28h]
0x1800083c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c7  mov     ebx, eax
0x1800083c9  test    eax, eax
0x1800083cb  js      loc_18000854B
0x1800083d1  mov     [rsp+0B00h+var_AD0], r15
0x1800083d6  mov     rbx, cs:hModule
0x1800083dd  mov     edi, 104h
0x1800083e2  mov     r8d, edi; nSize
0x1800083e5  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800083e9  mov     rcx, rbx; hModule
0x1800083ec  call    cs:__imp_GetModuleFileNameW
0x1800083f2  test    eax, eax
0x1800083f4  jnz     short loc_18000840C
0x1800083f6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800083fb  mov     ebx, eax
0x1800083fd  lea     rcx, [rsp+0B00h+var_AD0]
0x180008402  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008407  jmp     loc_18000854B
0x18000840c  cmp     eax, edi
0x18000840e  jnz     short loc_180008424
0x180008410  lea     rcx, [rsp+0B00h+var_AD0]
0x180008415  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000841a  mov     ebx, 8007007Ah
0x18000841f  jmp     loc_18000854B
0x180008424  lea     r8, [rbp+0A00h+Filename]; unsigned __int16 *
0x180008428  lea     rcx, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000842f  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180008434  test    rbx, rbx
0x180008437  jz      short loc_18000844F
0x180008439  xor     ecx, ecx; lpModuleName
0x18000843b  call    cs:__imp_GetModuleHandleW
0x180008441  cmp     rbx, rax
0x180008444  jz      short loc_18000844F
0x180008446  lea     r8, [rbp+0A00h+var_440]
0x18000844d  jmp     short loc_1800084CA
0x18000844f  mov     ebx, 22h ; '"'
0x180008454  mov     [rbp+0A00h+var_860], bx
0x18000845b  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x180008462  lea     rcx, [rbp+0A00h+var_85E]; unsigned __int16 *
0x180008469  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000846e  test    al, al
0x180008470  jnz     short loc_180008486
0x180008472  lea     rcx, [rsp+0B00h+var_AD0]
0x180008477  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000847c  mov     ebx, 80004005h
0x180008481  jmp     loc_18000854B
0x180008486  lea     rcx, [rbp+0A00h+var_860]
0x18000848d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008491  inc     rax
0x180008494  cmp     [rcx+rax*2], r15w
0x180008499  jnz     short loc_180008491
0x18000849b  cdqe
0x18000849d  mov     [rbp+rax*2+0A00h+var_860], bx
0x1800084a5  lea     rcx, ds:2[rax*2]
0x1800084ad  cmp     rcx, 418h
0x1800084b4  jnb     loc_18000857D
0x1800084ba  mov     [rbp+rcx+0A00h+var_860], r15w
0x1800084c3  lea     r8, [rbp+0A00h+var_860]; unsigned __int16 *
0x1800084ca  lea     rdx, aModule; "Module"
0x1800084d1  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800084d6  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800084db  mov     ebx, eax
0x1800084dd  test    eax, eax
0x1800084df  js      loc_1800083FD
0x1800084e5  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x1800084ec  lea     rdx, aModuleRaw; "Module_Raw"
0x1800084f3  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800084f8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800084fd  mov     ebx, eax
0x1800084ff  test    eax, eax
0x180008501  js      loc_1800083FD
0x180008507  movzx   r8d, r14w; unsigned __int16 *
0x18000850b  mov     [rsp+0B00h+var_AC8], r15
0x180008510  lea     r9, aRegistry; "REGISTRY"
0x180008517  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000851b  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180008520  test    esi, esi
0x180008522  jz      short loc_18000852E
0x180008524  mov     [rsp+0B00h+var_AE0], 1
0x18000852c  jmp     short loc_180008533
0x18000852e  mov     [rsp+0B00h+var_AE0], r15d; int
0x180008533  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008538  mov     ebx, eax
0x18000853a  lea     rcx, [rsp+0B00h+var_AC8]
0x18000853f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008544  jmp     loc_1800083FD
0x180008549  mov     ebx, eax
0x18000854b  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180008550  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008555  mov     eax, ebx
0x180008557  mov     rcx, [rbp+0A00h+var_30]
0x18000855e  xor     rcx, rsp; StackCookie
0x180008561  call    __security_check_cookie
0x180008566  mov     rbx, [rsp+0B00h+arg_10]
0x18000856e  add     rsp, 0AE0h
0x180008575  pop     r15
0x180008577  pop     r14
0x180008579  pop     rdi
0x18000857a  pop     rsi
0x18000857b  pop     rbp
0x18000857c  retn
0x18000857d  call    __report_rangecheckfailure
```
