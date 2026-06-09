# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001ad54`
- end: `0x18001afd4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001aff0`

## callees

- `0x1800026f8`
- `0x180014db0`
- `0x180017fa4`
- `0x1800180ec`
- `0x1800184b0`
- `0x1800192a4`
- `0x180019614`
- `0x180019e0c`
- `0x18001ad54`
- `0x18001b014`
- `0x180028f60`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001ae5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001ae5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ae9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ae9f`

## string_xrefs

- `0x18001afa1`: `REGISTRY`

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
      Error = ResultFromLastError();
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
0x18001ad54  push    rbp
0x18001ad56  push    rbx
0x18001ad57  push    rsi
0x18001ad58  push    rdi
0x18001ad59  push    r12
0x18001ad5b  push    r14
0x18001ad5d  push    r15
0x18001ad5f  lea     rbp, [rsp-9E0h]
0x18001ad67  sub     rsp, 0AE0h
0x18001ad6e  mov     rax, cs:__security_cookie
0x18001ad75  xor     rax, rsp
0x18001ad78  mov     [rbp+0A10h+var_40], rax
0x18001ad7f  xor     r12d, r12d
0x18001ad82  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001ad89  xorps   xmm0, xmm0
0x18001ad8c  mov     [rsp+0B10h+var_AD0], rax
0x18001ad91  xor     eax, eax
0x18001ad93  mov     [rsp+0B10h+var_AC8], r12
0x18001ad98  mov     r14, rcx
0x18001ad9b  mov     [rbp+0A10h+var_A90], rax
0x18001ad9f  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001ada4  mov     [rsp+0B10h+var_AC0], r12
0x18001ada9  mov     rbx, r9
0x18001adac  mov     [rsp+0B10h+var_AB8], r12d
0x18001adb1  mov     r15d, r8d
0x18001adb4  mov     [rbp+0A10h+var_A88], r12b
0x18001adb8  mov     rdi, rdx
0x18001adbb  movups  [rsp+0B10h+var_AB0], xmm0
0x18001adc0  movups  [rsp+0B10h+var_AA0], xmm0
0x18001adc5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001adca  mov     esi, eax
0x18001adcc  test    eax, eax
0x18001adce  jns     short loc_18001ADFD
0x18001add0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001add5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001adda  mov     eax, esi
0x18001addc  mov     rcx, [rbp+0A10h+var_40]
0x18001ade3  xor     rcx, rsp; StackCookie
0x18001ade6  call    __security_check_cookie
0x18001adeb  add     rsp, 0AE0h
0x18001adf2  pop     r15
0x18001adf4  pop     r14
0x18001adf6  pop     r12
0x18001adf8  pop     rdi
0x18001adf9  pop     rsi
0x18001adfa  pop     rbx
0x18001adfb  pop     rbp
0x18001adfc  retn
0x18001adfd  test    rbx, rbx
0x18001ae00  jz      short loc_18001AE21
0x18001ae02  jmp     short loc_18001AE19
0x18001ae04  mov     r8, [rbx+8]; unsigned __int16 *
0x18001ae08  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ae0d  mov     rdx, rax; unsigned __int16 *
0x18001ae10  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001ae15  lea     rbx, [rbx+10h]
0x18001ae19  mov     rax, [rbx]
0x18001ae1c  test    rax, rax
0x18001ae1f  jnz     short loc_18001AE04
0x18001ae21  mov     rax, [r14]
0x18001ae24  lea     rdx, [rsp+0B10h+var_AD0]
0x18001ae29  mov     rcx, r14
0x18001ae2c  mov     rax, [rax+28h]
0x18001ae30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae35  mov     ebx, eax
0x18001ae37  test    eax, eax
0x18001ae39  js      loc_18001AF6D
0x18001ae3f  mov     rbx, cs:hInstance
0x18001ae46  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001ae4a  mov     esi, 104h
0x18001ae4f  mov     [rsp+0B10h+var_AE0], r12
0x18001ae54  mov     r8d, esi; nSize
0x18001ae57  mov     rcx, rbx; hModule
0x18001ae5a  call    cs:__imp_GetModuleFileNameW
0x18001ae60  test    eax, eax
0x18001ae62  jnz     short loc_18001AE70
0x18001ae64  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001ae69  mov     ebx, eax
0x18001ae6b  jmp     loc_18001AF63
0x18001ae70  cmp     eax, esi
0x18001ae72  jnz     short loc_18001AE88
0x18001ae74  lea     rcx, [rsp+0B10h+var_AE0]
0x18001ae79  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ae7e  mov     ebx, 8007007Ah
0x18001ae83  jmp     loc_18001AF6D
0x18001ae88  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001ae8c  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001ae93  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001ae98  test    rbx, rbx
0x18001ae9b  jz      short loc_18001AEB3
0x18001ae9d  xor     ecx, ecx; lpModuleName
0x18001ae9f  call    cs:__imp_GetModuleHandleW
0x18001aea5  cmp     rbx, rax
0x18001aea8  jz      short loc_18001AEB3
0x18001aeaa  lea     r8, [rbp+0A10h+var_450]
0x18001aeb1  jmp     short loc_18001AF2E
0x18001aeb3  mov     ebx, 22h ; '"'
0x18001aeb8  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001aebf  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001aec6  mov     [rbp+0A10h+var_870], bx
0x18001aecd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001aed2  test    al, al
0x18001aed4  jnz     short loc_18001AEEA
0x18001aed6  lea     rcx, [rsp+0B10h+var_AE0]
0x18001aedb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001aee0  mov     ebx, 80004005h
0x18001aee5  jmp     loc_18001AF6D
0x18001aeea  lea     rcx, [rbp+0A10h+var_870]
0x18001aef1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001aef5  inc     rax
0x18001aef8  cmp     [rcx+rax*2], r12w
0x18001aefd  jnz     short loc_18001AEF5
0x18001aeff  cdqe
0x18001af01  lea     rcx, ds:2[rax*2]
0x18001af09  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001af11  cmp     rcx, 418h
0x18001af18  jnb     loc_18001AFCE
0x18001af1e  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001af27  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001af2e  lea     rdx, aModule; "Module"
0x18001af35  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001af3a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001af3f  mov     ebx, eax
0x18001af41  test    eax, eax
0x18001af43  js      short loc_18001AF63
0x18001af45  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001af4c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001af53  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001af58  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001af5d  mov     ebx, eax
0x18001af5f  test    eax, eax
0x18001af61  jns     short loc_18001AF7E
0x18001af63  lea     rcx, [rsp+0B10h+var_AE0]
0x18001af68  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001af6d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001af72  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001af77  mov     eax, ebx
0x18001af79  jmp     loc_18001ADDC
0x18001af7e  mov     [rsp+0B10h+var_AD8], r12
0x18001af83  test    r15d, r15d
0x18001af86  jz      short loc_18001AF97
0x18001af88  test    rdi, rdi
0x18001af8b  jz      short loc_18001AFBD
0x18001af8d  mov     [rsp+0B10h+var_AF0], 1
0x18001af95  jmp     short loc_18001AFA1
0x18001af97  test    rdi, rdi
0x18001af9a  jz      short loc_18001AFBD
0x18001af9c  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001afa1  lea     r9, aRegistry; "REGISTRY"
0x18001afa8  mov     r8, rdi; unsigned __int16 *
0x18001afab  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001afaf  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001afb4  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001afb9  mov     ebx, eax
0x18001afbb  jmp     short loc_18001AFC2
0x18001afbd  mov     ebx, 80070057h
0x18001afc2  lea     rcx, [rsp+0B10h+var_AD8]
0x18001afc7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001afcc  jmp     short loc_18001AF63
0x18001afce  call    __report_rangecheckfailure
```
