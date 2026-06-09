# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000858c`
- end: `0x180008814`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `648`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008830`

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
- `0x18000858c`
- `0x18000883c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000866c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000866c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800086bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800086bb`

## string_xrefs

- `0x1800087aa`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
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
    goto LABEL_32;
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
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_9:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_32;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      Error = -2147024774;
      goto LABEL_32;
    }
    ATL::CAtlModule::EscapeSingleQuote(v29, v12, Filename);
    if ( !v10 || v10 == GetModuleHandleW(0) )
    {
      v27 = 34;
      if ( !ocscpy_s(v28, v13, v29) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_32;
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
    if ( Error < 0 )
      goto LABEL_9;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
    if ( Error < 0 )
      goto LABEL_9;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v17 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_28:
        Error = v17;
LABEL_30:
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        goto LABEL_9;
      }
    }
    else if ( a2 )
    {
      v17 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 0);
      goto LABEL_28;
    }
    Error = -2147024809;
    goto LABEL_30;
  }
LABEL_32:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000858c  mov     [rsp-8+arg_10], rbx
0x180008591  push    rbp
0x180008592  push    rsi
0x180008593  push    rdi
0x180008594  push    r14
0x180008596  push    r15
0x180008598  lea     rbp, [rsp-9E0h]
0x1800085a0  sub     rsp, 0AE0h
0x1800085a7  mov     rax, cs:__security_cookie
0x1800085ae  xor     rax, rsp
0x1800085b1  mov     [rbp+0A00h+var_30], rax
0x1800085b8  mov     rbx, r9
0x1800085bb  mov     r14d, r8d
0x1800085be  mov     rdi, rdx
0x1800085c1  mov     rsi, rcx
0x1800085c4  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800085cb  mov     [rsp+0B00h+var_AC0], rax
0x1800085d0  xor     r15d, r15d
0x1800085d3  mov     [rsp+0B00h+var_AB8], r15
0x1800085d8  mov     [rsp+0B00h+var_AB0], r15
0x1800085dd  mov     [rsp+0B00h+var_AA8], r15d
0x1800085e2  xorps   xmm0, xmm0
0x1800085e5  xor     eax, eax
0x1800085e7  movups  [rsp+0B00h+var_AA0], xmm0
0x1800085ec  movups  [rsp+0B00h+var_A90], xmm0
0x1800085f1  mov     [rbp+0A00h+var_A80], rax
0x1800085f5  mov     [rbp+0A00h+var_A78], r15b
0x1800085f9  lea     rcx, [rsp+0B00h+var_AA0]; this
0x1800085fe  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180008603  test    eax, eax
0x180008605  js      loc_1800087DA
0x18000860b  mov     [rbp+0A00h+var_A78], 1
0x18000860f  test    rbx, rbx
0x180008612  jz      short loc_180008633
0x180008614  jmp     short loc_18000862B
0x180008616  mov     r8, [rbx+8]; unsigned __int16 *
0x18000861a  mov     rdx, rax; unsigned __int16 *
0x18000861d  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180008622  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180008627  lea     rbx, [rbx+10h]
0x18000862b  mov     rax, [rbx]
0x18000862e  test    rax, rax
0x180008631  jnz     short loc_180008616
0x180008633  mov     rax, [rsi]
0x180008636  lea     rdx, [rsp+0B00h+var_AC0]
0x18000863b  mov     rcx, rsi
0x18000863e  mov     rax, [rax+28h]
0x180008642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008647  mov     ebx, eax
0x180008649  test    eax, eax
0x18000864b  js      loc_1800087DC
0x180008651  mov     [rsp+0B00h+var_AD0], r15
0x180008656  mov     rbx, cs:hModule
0x18000865d  mov     esi, 104h
0x180008662  mov     r8d, esi; nSize
0x180008665  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180008669  mov     rcx, rbx; hModule
0x18000866c  call    cs:__imp_GetModuleFileNameW
0x180008672  test    eax, eax
0x180008674  jnz     short loc_18000868C
0x180008676  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000867b  mov     ebx, eax
0x18000867d  lea     rcx, [rsp+0B00h+var_AD0]
0x180008682  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008687  jmp     loc_1800087DC
0x18000868c  cmp     eax, esi
0x18000868e  jnz     short loc_1800086A4
0x180008690  lea     rcx, [rsp+0B00h+var_AD0]
0x180008695  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000869a  mov     ebx, 8007007Ah
0x18000869f  jmp     loc_1800087DC
0x1800086a4  lea     r8, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800086a8  lea     rcx, [rbp+0A00h+var_440]; unsigned __int16 *
0x1800086af  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x1800086b4  test    rbx, rbx
0x1800086b7  jz      short loc_1800086CF
0x1800086b9  xor     ecx, ecx; lpModuleName
0x1800086bb  call    cs:__imp_GetModuleHandleW
0x1800086c1  cmp     rbx, rax
0x1800086c4  jz      short loc_1800086CF
0x1800086c6  lea     r8, [rbp+0A00h+var_440]
0x1800086cd  jmp     short loc_18000874A
0x1800086cf  mov     ebx, 22h ; '"'
0x1800086d4  mov     [rbp+0A00h+var_860], bx
0x1800086db  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x1800086e2  lea     rcx, [rbp+0A00h+var_85E]; unsigned __int16 *
0x1800086e9  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x1800086ee  test    al, al
0x1800086f0  jnz     short loc_180008706
0x1800086f2  lea     rcx, [rsp+0B00h+var_AD0]
0x1800086f7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800086fc  mov     ebx, 80004005h
0x180008701  jmp     loc_1800087DC
0x180008706  lea     rcx, [rbp+0A00h+var_860]
0x18000870d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008711  inc     rax
0x180008714  cmp     [rcx+rax*2], r15w
0x180008719  jnz     short loc_180008711
0x18000871b  cdqe
0x18000871d  mov     [rbp+rax*2+0A00h+var_860], bx
0x180008725  lea     rcx, ds:2[rax*2]
0x18000872d  cmp     rcx, 418h
0x180008734  jnb     loc_18000880E
0x18000873a  mov     [rbp+rcx+0A00h+var_860], r15w
0x180008743  lea     r8, [rbp+0A00h+var_860]; unsigned __int16 *
0x18000874a  lea     rdx, aModule; "Module"
0x180008751  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180008756  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000875b  mov     ebx, eax
0x18000875d  test    eax, eax
0x18000875f  js      loc_18000867D
0x180008765  lea     r8, [rbp+0A00h+var_440]; unsigned __int16 *
0x18000876c  lea     rdx, aModuleRaw; "Module_Raw"
0x180008773  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180008778  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000877d  mov     ebx, eax
0x18000877f  test    eax, eax
0x180008781  js      loc_18000867D
0x180008787  mov     [rsp+0B00h+var_AC8], r15
0x18000878c  test    r14d, r14d
0x18000878f  jz      short loc_1800087A0
0x180008791  test    rdi, rdi
0x180008794  jz      short loc_1800087C6
0x180008796  mov     [rsp+0B00h+var_AE0], 1
0x18000879e  jmp     short loc_1800087AA
0x1800087a0  test    rdi, rdi
0x1800087a3  jz      short loc_1800087C6
0x1800087a5  mov     [rsp+0B00h+var_AE0], r15d; int
0x1800087aa  lea     r9, aRegistry; "REGISTRY"
0x1800087b1  mov     r8, rdi; unsigned __int16 *
0x1800087b4  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800087b8  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800087bd  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800087c2  mov     ebx, eax
0x1800087c4  jmp     short loc_1800087CB
0x1800087c6  mov     ebx, 80070057h
0x1800087cb  lea     rcx, [rsp+0B00h+var_AC8]
0x1800087d0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800087d5  jmp     loc_18000867D
0x1800087da  mov     ebx, eax
0x1800087dc  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800087e1  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800087e6  mov     eax, ebx
0x1800087e8  mov     rcx, [rbp+0A00h+var_30]
0x1800087ef  xor     rcx, rsp; StackCookie
0x1800087f2  call    __security_check_cookie
0x1800087f7  mov     rbx, [rsp+0B00h+arg_10]
0x1800087ff  add     rsp, 0AE0h
0x180008806  pop     r15
0x180008808  pop     r14
0x18000880a  pop     rdi
0x18000880b  pop     rsi
0x18000880c  pop     rbp
0x18000880d  retn
0x18000880e  call    __report_rangecheckfailure
```
