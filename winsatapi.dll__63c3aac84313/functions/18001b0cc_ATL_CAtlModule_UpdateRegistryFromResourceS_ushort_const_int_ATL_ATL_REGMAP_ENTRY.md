# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001b0cc`
- end: `0x18001b354`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `648`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b370`

## callees

- `0x180005c20`
- `0x180013a68`
- `0x180015290`
- `0x1800158f0`
- `0x1800161a0`
- `0x180016a68`
- `0x180018798`
- `0x180019e70`
- `0x18001b0cc`
- `0x18001b5c0`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001b1da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001b1da`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b21f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b21f`

## string_xrefs

- `0x18001b321`: `REGISTRY`

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
  _QWORD *v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  __int64 v26; // [rsp+90h] [rbp-70h]
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v28; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v29[527]; // [rsp+2B2h] [rbp+1B2h] BYREF
  unsigned __int16 v30[520]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v26 = -2;
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
    ATL::CAtlModule::EscapeSingleQuote(v30, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v28 = 34;
      if ( !ocscpy_s(v29, v14, v30) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        Error = -2147467259;
        goto LABEL_24;
      }
      v16 = -1;
      do
        ++v16;
      while ( v29[v16 - 1] );
      v29[(int)v16 - 1] = 34;
      v17 = 2LL * (int)v16 + 2;
      if ( v17 >= 0x418 )
        _report_rangecheckfailure();
      *(unsigned __int16 *)((char *)&v29[-1] + v17) = 0;
      v15 = &v28;
    }
    else
    {
      v15 = v30;
    }
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( Error < 0 )
      goto LABEL_23;
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v30);
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
0x18001b0cc  push    rbp
0x18001b0ce  push    rbx
0x18001b0cf  push    rsi
0x18001b0d0  push    rdi
0x18001b0d1  push    r12
0x18001b0d3  push    r14
0x18001b0d5  push    r15
0x18001b0d7  lea     rbp, [rsp-9F0h]
0x18001b0df  sub     rsp, 0AF0h
0x18001b0e6  mov     [rbp+0A20h+var_A90], 0FFFFFFFFFFFFFFFEh
0x18001b0ee  mov     rax, cs:__security_cookie
0x18001b0f5  xor     rax, rsp
0x18001b0f8  mov     [rbp+0A20h+var_40], rax
0x18001b0ff  mov     rbx, r9
0x18001b102  mov     r15d, r8d
0x18001b105  mov     rdi, rdx
0x18001b108  mov     r14, rcx
0x18001b10b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001b112  mov     [rsp+0B20h+var_AE0], rax
0x18001b117  xor     r12d, r12d
0x18001b11a  mov     [rsp+0B20h+var_AD8], r12
0x18001b11f  mov     [rsp+0B20h+var_AD0], r12
0x18001b124  mov     [rsp+0B20h+var_AC8], r12d
0x18001b129  xorps   xmm0, xmm0
0x18001b12c  xor     eax, eax
0x18001b12e  movups  [rsp+0B20h+var_AC0], xmm0
0x18001b133  movups  [rsp+0B20h+var_AB0], xmm0
0x18001b138  mov     [rbp+0A20h+var_AA0], rax
0x18001b13c  mov     [rbp+0A20h+var_A98], r12b
0x18001b140  lea     rcx, [rsp+0B20h+var_AC0]; this
0x18001b145  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001b14a  mov     esi, eax
0x18001b14c  test    eax, eax
0x18001b14e  jns     short loc_18001B17D
0x18001b150  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b155  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001b15a  mov     eax, esi
0x18001b15c  mov     rcx, [rbp+0A20h+var_40]
0x18001b163  xor     rcx, rsp; StackCookie
0x18001b166  call    __security_check_cookie
0x18001b16b  add     rsp, 0AF0h
0x18001b172  pop     r15
0x18001b174  pop     r14
0x18001b176  pop     r12
0x18001b178  pop     rdi
0x18001b179  pop     rsi
0x18001b17a  pop     rbx
0x18001b17b  pop     rbp
0x18001b17c  retn
0x18001b17d  test    rbx, rbx
0x18001b180  jz      short loc_18001B1A1
0x18001b182  jmp     short loc_18001B199
0x18001b184  mov     r8, [rbx+8]; unsigned __int16 *
0x18001b188  mov     rdx, rax; unsigned __int16 *
0x18001b18b  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b190  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001b195  lea     rbx, [rbx+10h]
0x18001b199  mov     rax, [rbx]
0x18001b19c  test    rax, rax
0x18001b19f  jnz     short loc_18001B184
0x18001b1a1  mov     rax, [r14]
0x18001b1a4  lea     rdx, [rsp+0B20h+var_AE0]
0x18001b1a9  mov     rcx, r14
0x18001b1ac  mov     rax, [rax+28h]
0x18001b1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1b5  mov     ebx, eax
0x18001b1b7  test    eax, eax
0x18001b1b9  js      loc_18001B2ED
0x18001b1bf  mov     [rsp+0B20h+var_AF0], r12
0x18001b1c4  mov     rbx, cs:hModule
0x18001b1cb  mov     esi, 104h
0x18001b1d0  mov     r8d, esi; nSize
0x18001b1d3  lea     rdx, [rbp+0A20h+Filename]; lpFilename
0x18001b1d7  mov     rcx, rbx; hModule
0x18001b1da  call    cs:__imp_GetModuleFileNameW
0x18001b1e0  test    eax, eax
0x18001b1e2  jnz     short loc_18001B1F0
0x18001b1e4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001b1e9  mov     ebx, eax
0x18001b1eb  jmp     loc_18001B2E3
0x18001b1f0  cmp     eax, esi
0x18001b1f2  jnz     short loc_18001B208
0x18001b1f4  lea     rcx, [rsp+0B20h+var_AF0]
0x18001b1f9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001b1fe  mov     ebx, 8007007Ah
0x18001b203  jmp     loc_18001B2ED
0x18001b208  lea     r8, [rbp+0A20h+Filename]; unsigned __int16 *
0x18001b20c  lea     rcx, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001b213  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001b218  test    rbx, rbx
0x18001b21b  jz      short loc_18001B233
0x18001b21d  xor     ecx, ecx; lpModuleName
0x18001b21f  call    cs:__imp_GetModuleHandleW
0x18001b225  cmp     rbx, rax
0x18001b228  jz      short loc_18001B233
0x18001b22a  lea     r8, [rbp+0A20h+var_450]
0x18001b231  jmp     short loc_18001B2AE
0x18001b233  mov     ebx, 22h ; '"'
0x18001b238  mov     [rbp+0A20h+var_870], bx
0x18001b23f  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001b246  lea     rcx, [rbp+0A20h+var_86E]; unsigned __int16 *
0x18001b24d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001b252  test    al, al
0x18001b254  jnz     short loc_18001B26A
0x18001b256  lea     rcx, [rsp+0B20h+var_AF0]
0x18001b25b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001b260  mov     ebx, 80004005h
0x18001b265  jmp     loc_18001B2ED
0x18001b26a  lea     rcx, [rbp+0A20h+var_870]
0x18001b271  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b275  inc     rax
0x18001b278  cmp     [rcx+rax*2], r12w
0x18001b27d  jnz     short loc_18001B275
0x18001b27f  cdqe
0x18001b281  mov     [rbp+rax*2+0A20h+var_870], bx
0x18001b289  lea     rcx, ds:2[rax*2]
0x18001b291  cmp     rcx, 418h
0x18001b298  jnb     loc_18001B34E
0x18001b29e  mov     [rbp+rcx+0A20h+var_870], r12w
0x18001b2a7  lea     r8, [rbp+0A20h+var_870]; unsigned __int16 *
0x18001b2ae  lea     rdx, aModule; "Module"
0x18001b2b5  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b2ba  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001b2bf  mov     ebx, eax
0x18001b2c1  test    eax, eax
0x18001b2c3  js      short loc_18001B2E3
0x18001b2c5  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001b2cc  lea     rdx, aModuleRaw; "Module_Raw"
0x18001b2d3  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b2d8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001b2dd  mov     ebx, eax
0x18001b2df  test    eax, eax
0x18001b2e1  jns     short loc_18001B2FE
0x18001b2e3  lea     rcx, [rsp+0B20h+var_AF0]
0x18001b2e8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001b2ed  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b2f2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001b2f7  mov     eax, ebx
0x18001b2f9  jmp     loc_18001B15C
0x18001b2fe  mov     [rsp+0B20h+var_AE8], r12
0x18001b303  test    r15d, r15d
0x18001b306  jz      short loc_18001B317
0x18001b308  test    rdi, rdi
0x18001b30b  jz      short loc_18001B33D
0x18001b30d  mov     [rsp+0B20h+var_B00], 1
0x18001b315  jmp     short loc_18001B321
0x18001b317  test    rdi, rdi
0x18001b31a  jz      short loc_18001B33D
0x18001b31c  mov     [rsp+0B20h+var_B00], r12d; int
0x18001b321  lea     r9, aRegistry; "REGISTRY"
0x18001b328  mov     r8, rdi; unsigned __int16 *
0x18001b32b  lea     rdx, [rbp+0A20h+Filename]; unsigned __int16 *
0x18001b32f  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b334  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001b339  mov     ebx, eax
0x18001b33b  jmp     short loc_18001B342
0x18001b33d  mov     ebx, 80070057h
0x18001b342  lea     rcx, [rsp+0B20h+var_AE8]
0x18001b347  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001b34c  jmp     short loc_18001B2E3
0x18001b34e  call    __report_rangecheckfailure
```
