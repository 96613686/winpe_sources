# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180043a4c`
- end: `0x180043cbc`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043f50`

## callees

- `0x18003a560`
- `0x18003a5a0`
- `0x18003c5c8`
- `0x18003cdd0`
- `0x18003d9d0`
- `0x18003df80`
- `0x18003ef04`
- `0x18003fd38`
- `0x180041918`
- `0x180043a4c`
- `0x1800444a0`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180043b52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180043b52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043b97`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043b97`

## string_xrefs

- `0x180043c7a`: `REGISTRY`

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
0x180043a4c  push    rbp
0x180043a4e  push    rbx
0x180043a4f  push    rsi
0x180043a50  push    rdi
0x180043a51  push    r12
0x180043a53  push    r14
0x180043a55  push    r15
0x180043a57  lea     rbp, [rsp-9E0h]
0x180043a5f  sub     rsp, 0AE0h
0x180043a66  mov     rax, cs:__security_cookie
0x180043a6d  xor     rax, rsp
0x180043a70  mov     [rbp+0A10h+var_40], rax
0x180043a77  xor     r12d, r12d
0x180043a7a  mov     r15d, edx
0x180043a7d  xorps   xmm0, xmm0
0x180043a80  mov     [rsp+0B10h+var_AC8], r12
0x180043a85  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180043a8c  mov     [rsp+0B10h+var_AC0], r12
0x180043a91  mov     [rsp+0B10h+var_AD0], rax
0x180043a96  mov     rsi, rcx
0x180043a99  xor     eax, eax
0x180043a9b  mov     [rsp+0B10h+var_AB8], r12d
0x180043aa0  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180043aa5  mov     [rbp+0A10h+var_A90], rax
0x180043aa9  mov     rbx, r9
0x180043aac  mov     [rbp+0A10h+var_A88], r12b
0x180043ab0  mov     r14d, r8d
0x180043ab3  movups  [rsp+0B10h+var_AB0], xmm0
0x180043ab8  movups  [rsp+0B10h+var_AA0], xmm0
0x180043abd  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180043ac2  mov     edi, eax
0x180043ac4  test    eax, eax
0x180043ac6  jns     short loc_180043AF5
0x180043ac8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043acd  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180043ad2  mov     eax, edi
0x180043ad4  mov     rcx, [rbp+0A10h+var_40]
0x180043adb  xor     rcx, rsp; StackCookie
0x180043ade  call    __security_check_cookie
0x180043ae3  add     rsp, 0AE0h
0x180043aea  pop     r15
0x180043aec  pop     r14
0x180043aee  pop     r12
0x180043af0  pop     rdi
0x180043af1  pop     rsi
0x180043af2  pop     rbx
0x180043af3  pop     rbp
0x180043af4  retn
0x180043af5  test    rbx, rbx
0x180043af8  jz      short loc_180043B19
0x180043afa  jmp     short loc_180043B11
0x180043afc  mov     r8, [rbx+8]; unsigned __int16 *
0x180043b00  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043b05  mov     rdx, rax; unsigned __int16 *
0x180043b08  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180043b0d  lea     rbx, [rbx+10h]
0x180043b11  mov     rax, [rbx]
0x180043b14  test    rax, rax
0x180043b17  jnz     short loc_180043AFC
0x180043b19  mov     rax, [rsi]
0x180043b1c  lea     rdx, [rsp+0B10h+var_AD0]
0x180043b21  mov     rcx, rsi
0x180043b24  mov     rax, [rax+28h]
0x180043b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b2d  mov     ebx, eax
0x180043b2f  test    eax, eax
0x180043b31  js      loc_180043C65
0x180043b37  mov     rbx, cs:hModule
0x180043b3e  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180043b42  mov     edi, 104h
0x180043b47  mov     [rsp+0B10h+var_AE0], r12
0x180043b4c  mov     r8d, edi; nSize
0x180043b4f  mov     rcx, rbx; hModule
0x180043b52  call    cs:__imp_GetModuleFileNameW
0x180043b58  test    eax, eax
0x180043b5a  jnz     short loc_180043B68
0x180043b5c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180043b61  mov     ebx, eax
0x180043b63  jmp     loc_180043C5B
0x180043b68  cmp     eax, edi
0x180043b6a  jnz     short loc_180043B80
0x180043b6c  lea     rcx, [rsp+0B10h+var_AE0]
0x180043b71  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180043b76  mov     ebx, 8007007Ah
0x180043b7b  jmp     loc_180043C65
0x180043b80  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180043b84  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180043b8b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180043b90  test    rbx, rbx
0x180043b93  jz      short loc_180043BAB
0x180043b95  xor     ecx, ecx; lpModuleName
0x180043b97  call    cs:__imp_GetModuleHandleW
0x180043b9d  cmp     rbx, rax
0x180043ba0  jz      short loc_180043BAB
0x180043ba2  lea     r8, [rbp+0A10h+var_450]
0x180043ba9  jmp     short loc_180043C26
0x180043bab  mov     ebx, 22h ; '"'
0x180043bb0  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180043bb7  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180043bbe  mov     [rbp+0A10h+var_870], bx
0x180043bc5  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180043bca  test    al, al
0x180043bcc  jnz     short loc_180043BE2
0x180043bce  lea     rcx, [rsp+0B10h+var_AE0]
0x180043bd3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180043bd8  mov     ebx, 80004005h
0x180043bdd  jmp     loc_180043C65
0x180043be2  lea     rcx, [rbp+0A10h+var_870]
0x180043be9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043bed  inc     rax
0x180043bf0  cmp     [rcx+rax*2], r12w
0x180043bf5  jnz     short loc_180043BED
0x180043bf7  cdqe
0x180043bf9  lea     rcx, ds:2[rax*2]
0x180043c01  mov     [rbp+rax*2+0A10h+var_870], bx
0x180043c09  cmp     rcx, 418h
0x180043c10  jnb     loc_180043CB6
0x180043c16  mov     [rbp+rcx+0A10h+var_870], r12w
0x180043c1f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180043c26  lea     rdx, aModule; "Module"
0x180043c2d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043c32  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180043c37  mov     ebx, eax
0x180043c39  test    eax, eax
0x180043c3b  js      short loc_180043C5B
0x180043c3d  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180043c44  lea     rdx, aModuleRaw; "Module_Raw"
0x180043c4b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043c50  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180043c55  mov     ebx, eax
0x180043c57  test    eax, eax
0x180043c59  jns     short loc_180043C76
0x180043c5b  lea     rcx, [rsp+0B10h+var_AE0]
0x180043c60  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180043c65  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043c6a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180043c6f  mov     eax, ebx
0x180043c71  jmp     loc_180043AD4
0x180043c76  movzx   r8d, r15w; unsigned __int16 *
0x180043c7a  lea     r9, aRegistry; "REGISTRY"
0x180043c81  mov     [rsp+0B10h+var_AD8], r12
0x180043c86  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180043c8a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043c8f  test    r14d, r14d
0x180043c92  jz      short loc_180043C9E
0x180043c94  mov     [rsp+0B10h+var_AF0], 1
0x180043c9c  jmp     short loc_180043CA3
0x180043c9e  mov     [rsp+0B10h+var_AF0], r12d; int
0x180043ca3  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180043ca8  lea     rcx, [rsp+0B10h+var_AD8]
0x180043cad  mov     ebx, eax
0x180043caf  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180043cb4  jmp     short loc_180043C5B
0x180043cb6  call    __report_rangecheckfailure
```
