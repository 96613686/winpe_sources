# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180046500`
- end: `0x18004677d`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `637`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180046a20`

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
- `0x180046500`
- `0x180047044`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180046607`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180046607`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046652`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046652`

## string_xrefs

- `0x18004673b`: `REGISTRY`

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

  v21[1] = 0;
  v21[2] = 0;
  v21[0] = &ATL::CRegObject::`vftable';
  v22 = 0;
  v24 = 0;
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
0x180046500  push    rbp
0x180046502  push    rbx
0x180046503  push    rsi
0x180046504  push    rdi
0x180046505  push    r12
0x180046507  push    r14
0x180046509  push    r15
0x18004650b  lea     rbp, [rsp-9E0h]
0x180046513  sub     rsp, 0AE0h
0x18004651a  mov     rax, cs:__security_cookie
0x180046521  xor     rax, rsp
0x180046524  mov     [rbp+0A10h+var_40], rax
0x18004652b  xor     r12d, r12d
0x18004652e  mov     r15d, edx
0x180046531  xorps   xmm0, xmm0
0x180046534  mov     [rsp+0B10h+var_AC8], r12
0x180046539  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180046540  mov     [rsp+0B10h+var_AC0], r12
0x180046545  mov     [rsp+0B10h+var_AD0], rax
0x18004654a  mov     rsi, rcx
0x18004654d  xor     eax, eax
0x18004654f  mov     [rsp+0B10h+var_AB8], r12d
0x180046554  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180046559  mov     [rbp+0A10h+var_A90], rax
0x18004655d  mov     rbx, r9
0x180046560  mov     [rbp+0A10h+var_A88], r12b
0x180046564  mov     r14d, r8d
0x180046567  movups  [rsp+0B10h+var_AB0], xmm0
0x18004656c  movups  [rsp+0B10h+var_AA0], xmm0
0x180046571  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180046576  mov     edi, eax
0x180046578  test    eax, eax
0x18004657a  jns     short loc_1800465AA
0x18004657c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180046581  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180046586  mov     eax, edi
0x180046588  mov     rcx, [rbp+0A10h+var_40]
0x18004658f  xor     rcx, rsp; StackCookie
0x180046592  call    __security_check_cookie
0x180046597  add     rsp, 0AE0h
0x18004659e  pop     r15
0x1800465a0  pop     r14
0x1800465a2  pop     r12
0x1800465a4  pop     rdi
0x1800465a5  pop     rsi
0x1800465a6  pop     rbx
0x1800465a7  pop     rbp
0x1800465a8  retn
0x1800465aa  test    rbx, rbx
0x1800465ad  jz      short loc_1800465CE
0x1800465af  jmp     short loc_1800465C6
0x1800465b1  mov     r8, [rbx+8]; unsigned __int16 *
0x1800465b5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800465ba  mov     rdx, rax; unsigned __int16 *
0x1800465bd  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800465c2  lea     rbx, [rbx+10h]
0x1800465c6  mov     rax, [rbx]
0x1800465c9  test    rax, rax
0x1800465cc  jnz     short loc_1800465B1
0x1800465ce  mov     rax, [rsi]
0x1800465d1  lea     rdx, [rsp+0B10h+var_AD0]
0x1800465d6  mov     rcx, rsi
0x1800465d9  mov     rax, [rax+28h]
0x1800465dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800465e2  mov     ebx, eax
0x1800465e4  test    eax, eax
0x1800465e6  js      loc_180046726
0x1800465ec  mov     rbx, cs:hModule
0x1800465f3  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800465f7  mov     edi, 104h
0x1800465fc  mov     [rsp+0B10h+var_AE0], r12
0x180046601  mov     r8d, edi; nSize
0x180046604  mov     rcx, rbx; hModule
0x180046607  call    cs:__imp_GetModuleFileNameW
0x18004660e  nop     dword ptr [rax+rax+00h]
0x180046613  test    eax, eax
0x180046615  jnz     short loc_180046623
0x180046617  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004661c  mov     ebx, eax
0x18004661e  jmp     loc_18004671C
0x180046623  cmp     eax, edi
0x180046625  jnz     short loc_18004663B
0x180046627  lea     rcx, [rsp+0B10h+var_AE0]
0x18004662c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180046631  mov     ebx, 8007007Ah
0x180046636  jmp     loc_180046726
0x18004663b  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18004663f  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180046646  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18004664b  test    rbx, rbx
0x18004664e  jz      short loc_18004666C
0x180046650  xor     ecx, ecx; lpModuleName
0x180046652  call    cs:__imp_GetModuleHandleW
0x180046659  nop     dword ptr [rax+rax+00h]
0x18004665e  cmp     rbx, rax
0x180046661  jz      short loc_18004666C
0x180046663  lea     r8, [rbp+0A10h+var_450]
0x18004666a  jmp     short loc_1800466E7
0x18004666c  mov     ebx, 22h ; '"'
0x180046671  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180046678  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18004667f  mov     [rbp+0A10h+var_870], bx
0x180046686  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18004668b  test    al, al
0x18004668d  jnz     short loc_1800466A3
0x18004668f  lea     rcx, [rsp+0B10h+var_AE0]
0x180046694  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180046699  mov     ebx, 80004005h
0x18004669e  jmp     loc_180046726
0x1800466a3  lea     rcx, [rbp+0A10h+var_870]
0x1800466aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800466ae  inc     rax
0x1800466b1  cmp     [rcx+rax*2], r12w
0x1800466b6  jnz     short loc_1800466AE
0x1800466b8  cdqe
0x1800466ba  lea     rcx, ds:2[rax*2]
0x1800466c2  mov     [rbp+rax*2+0A10h+var_870], bx
0x1800466ca  cmp     rcx, 418h
0x1800466d1  jnb     loc_180046777
0x1800466d7  mov     [rbp+rcx+0A10h+var_870], r12w
0x1800466e0  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x1800466e7  lea     rdx, aModule; "Module"
0x1800466ee  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800466f3  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800466f8  mov     ebx, eax
0x1800466fa  test    eax, eax
0x1800466fc  js      short loc_18004671C
0x1800466fe  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180046705  lea     rdx, aModuleRaw; "Module_Raw"
0x18004670c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180046711  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180046716  mov     ebx, eax
0x180046718  test    eax, eax
0x18004671a  jns     short loc_180046737
0x18004671c  lea     rcx, [rsp+0B10h+var_AE0]
0x180046721  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180046726  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18004672b  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180046730  mov     eax, ebx
0x180046732  jmp     loc_180046588
0x180046737  movzx   r8d, r15w; unsigned __int16 *
0x18004673b  lea     r9, aRegistry; "REGISTRY"
0x180046742  mov     [rsp+0B10h+var_AD8], r12
0x180046747  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18004674b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180046750  test    r14d, r14d
0x180046753  jz      short loc_18004675F
0x180046755  mov     [rsp+0B10h+var_AF0], 1
0x18004675d  jmp     short loc_180046764
0x18004675f  mov     [rsp+0B10h+var_AF0], r12d; int
0x180046764  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180046769  lea     rcx, [rsp+0B10h+var_AD8]
0x18004676e  mov     ebx, eax
0x180046770  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180046775  jmp     short loc_18004671C
0x180046777  call    __report_rangecheckfailure
```
