# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001aadc`
- end: `0x18001ad4c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001afe0`

## callees

- `0x1800026f8`
- `0x180014db0`
- `0x180017fa4`
- `0x1800180ec`
- `0x1800184b0`
- `0x1800192a4`
- `0x180019614`
- `0x180019e0c`
- `0x18001aadc`
- `0x18001b014`
- `0x180028f60`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001abe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001abe2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ac27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001ac27`

## string_xrefs

- `0x18001ad0a`: `REGISTRY`

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
0x18001aadc  push    rbp
0x18001aade  push    rbx
0x18001aadf  push    rsi
0x18001aae0  push    rdi
0x18001aae1  push    r12
0x18001aae3  push    r14
0x18001aae5  push    r15
0x18001aae7  lea     rbp, [rsp-9E0h]
0x18001aaef  sub     rsp, 0AE0h
0x18001aaf6  mov     rax, cs:__security_cookie
0x18001aafd  xor     rax, rsp
0x18001ab00  mov     [rbp+0A10h+var_40], rax
0x18001ab07  xor     r12d, r12d
0x18001ab0a  mov     r15d, edx
0x18001ab0d  xorps   xmm0, xmm0
0x18001ab10  mov     [rsp+0B10h+var_AC8], r12
0x18001ab15  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001ab1c  mov     [rsp+0B10h+var_AC0], r12
0x18001ab21  mov     [rsp+0B10h+var_AD0], rax
0x18001ab26  mov     rsi, rcx
0x18001ab29  xor     eax, eax
0x18001ab2b  mov     [rsp+0B10h+var_AB8], r12d
0x18001ab30  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001ab35  mov     [rbp+0A10h+var_A90], rax
0x18001ab39  mov     rbx, r9
0x18001ab3c  mov     [rbp+0A10h+var_A88], r12b
0x18001ab40  mov     r14d, r8d
0x18001ab43  movups  [rsp+0B10h+var_AB0], xmm0
0x18001ab48  movups  [rsp+0B10h+var_AA0], xmm0
0x18001ab4d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001ab52  mov     edi, eax
0x18001ab54  test    eax, eax
0x18001ab56  jns     short loc_18001AB85
0x18001ab58  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ab5d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001ab62  mov     eax, edi
0x18001ab64  mov     rcx, [rbp+0A10h+var_40]
0x18001ab6b  xor     rcx, rsp; StackCookie
0x18001ab6e  call    __security_check_cookie
0x18001ab73  add     rsp, 0AE0h
0x18001ab7a  pop     r15
0x18001ab7c  pop     r14
0x18001ab7e  pop     r12
0x18001ab80  pop     rdi
0x18001ab81  pop     rsi
0x18001ab82  pop     rbx
0x18001ab83  pop     rbp
0x18001ab84  retn
0x18001ab85  test    rbx, rbx
0x18001ab88  jz      short loc_18001ABA9
0x18001ab8a  jmp     short loc_18001ABA1
0x18001ab8c  mov     r8, [rbx+8]; unsigned __int16 *
0x18001ab90  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ab95  mov     rdx, rax; unsigned __int16 *
0x18001ab98  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001ab9d  lea     rbx, [rbx+10h]
0x18001aba1  mov     rax, [rbx]
0x18001aba4  test    rax, rax
0x18001aba7  jnz     short loc_18001AB8C
0x18001aba9  mov     rax, [rsi]
0x18001abac  lea     rdx, [rsp+0B10h+var_AD0]
0x18001abb1  mov     rcx, rsi
0x18001abb4  mov     rax, [rax+28h]
0x18001abb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abbd  mov     ebx, eax
0x18001abbf  test    eax, eax
0x18001abc1  js      loc_18001ACF5
0x18001abc7  mov     rbx, cs:hInstance
0x18001abce  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001abd2  mov     edi, 104h
0x18001abd7  mov     [rsp+0B10h+var_AE0], r12
0x18001abdc  mov     r8d, edi; nSize
0x18001abdf  mov     rcx, rbx; hModule
0x18001abe2  call    cs:__imp_GetModuleFileNameW
0x18001abe8  test    eax, eax
0x18001abea  jnz     short loc_18001ABF8
0x18001abec  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001abf1  mov     ebx, eax
0x18001abf3  jmp     loc_18001ACEB
0x18001abf8  cmp     eax, edi
0x18001abfa  jnz     short loc_18001AC10
0x18001abfc  lea     rcx, [rsp+0B10h+var_AE0]
0x18001ac01  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ac06  mov     ebx, 8007007Ah
0x18001ac0b  jmp     loc_18001ACF5
0x18001ac10  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001ac14  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001ac1b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001ac20  test    rbx, rbx
0x18001ac23  jz      short loc_18001AC3B
0x18001ac25  xor     ecx, ecx; lpModuleName
0x18001ac27  call    cs:__imp_GetModuleHandleW
0x18001ac2d  cmp     rbx, rax
0x18001ac30  jz      short loc_18001AC3B
0x18001ac32  lea     r8, [rbp+0A10h+var_450]
0x18001ac39  jmp     short loc_18001ACB6
0x18001ac3b  mov     ebx, 22h ; '"'
0x18001ac40  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001ac47  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001ac4e  mov     [rbp+0A10h+var_870], bx
0x18001ac55  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001ac5a  test    al, al
0x18001ac5c  jnz     short loc_18001AC72
0x18001ac5e  lea     rcx, [rsp+0B10h+var_AE0]
0x18001ac63  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ac68  mov     ebx, 80004005h
0x18001ac6d  jmp     loc_18001ACF5
0x18001ac72  lea     rcx, [rbp+0A10h+var_870]
0x18001ac79  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ac7d  inc     rax
0x18001ac80  cmp     [rcx+rax*2], r12w
0x18001ac85  jnz     short loc_18001AC7D
0x18001ac87  cdqe
0x18001ac89  lea     rcx, ds:2[rax*2]
0x18001ac91  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001ac99  cmp     rcx, 418h
0x18001aca0  jnb     loc_18001AD46
0x18001aca6  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001acaf  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001acb6  lea     rdx, aModule; "Module"
0x18001acbd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001acc2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001acc7  mov     ebx, eax
0x18001acc9  test    eax, eax
0x18001accb  js      short loc_18001ACEB
0x18001accd  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001acd4  lea     rdx, aModuleRaw; "Module_Raw"
0x18001acdb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ace0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001ace5  mov     ebx, eax
0x18001ace7  test    eax, eax
0x18001ace9  jns     short loc_18001AD06
0x18001aceb  lea     rcx, [rsp+0B10h+var_AE0]
0x18001acf0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001acf5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001acfa  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001acff  mov     eax, ebx
0x18001ad01  jmp     loc_18001AB64
0x18001ad06  movzx   r8d, r15w; unsigned __int16 *
0x18001ad0a  lea     r9, aRegistry; "REGISTRY"
0x18001ad11  mov     [rsp+0B10h+var_AD8], r12
0x18001ad16  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001ad1a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001ad1f  test    r14d, r14d
0x18001ad22  jz      short loc_18001AD2E
0x18001ad24  mov     [rsp+0B10h+var_AF0], 1
0x18001ad2c  jmp     short loc_18001AD33
0x18001ad2e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001ad33  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001ad38  lea     rcx, [rsp+0B10h+var_AD8]
0x18001ad3d  mov     ebx, eax
0x18001ad3f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ad44  jmp     short loc_18001ACEB
0x18001ad46  call    __report_rangecheckfailure
```
