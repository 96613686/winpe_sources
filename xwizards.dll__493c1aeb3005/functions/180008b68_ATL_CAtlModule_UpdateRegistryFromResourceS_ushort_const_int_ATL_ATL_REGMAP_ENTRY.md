# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180008b68`
- end: `0x180008de8`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008e00`

## callees

- `0x180002248`
- `0x180002d78`
- `0x1800032e0`
- `0x180003b10`
- `0x180004370`
- `0x180005f7c`
- `0x180006920`
- `0x180007700`
- `0x180008b68`
- `0x180008e0c`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008c6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008c6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008cb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008cb3`

## string_xrefs

- `0x180008db5`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // esi
  int LastErrorHRESULT; // ebx
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
  LastErrorHRESULT = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( LastErrorHRESULT >= 0 )
  {
    v19 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_24;
    }
    if ( ModuleFileNameW == 260 )
    {
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      LastErrorHRESULT = -2147024774;
      goto LABEL_24;
    }
    ATL::CAtlModule::EscapeSingleQuote(v29, v13, Filename);
    if ( !v11 || v11 == GetModuleHandleW(0) )
    {
      v27 = 34;
      if ( !ocscpy_s(v28, v14, v29) )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
        LastErrorHRESULT = -2147467259;
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
    LastErrorHRESULT = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
    if ( LastErrorHRESULT < 0 )
      goto LABEL_23;
    LastErrorHRESULT = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
    if ( LastErrorHRESULT < 0 )
      goto LABEL_23;
    v20 = 0;
    if ( a3 )
    {
      if ( a2 )
      {
        v18 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)v21, Filename, a2, L"REGISTRY", 1);
LABEL_30:
        LastErrorHRESULT = v18;
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
    LastErrorHRESULT = -2147024809;
    goto LABEL_32;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)LastErrorHRESULT;
}

```

## disassembly

```asm
0x180008b68  push    rbp
0x180008b6a  push    rbx
0x180008b6b  push    rsi
0x180008b6c  push    rdi
0x180008b6d  push    r12
0x180008b6f  push    r14
0x180008b71  push    r15
0x180008b73  lea     rbp, [rsp-9E0h]
0x180008b7b  sub     rsp, 0AE0h
0x180008b82  mov     rax, cs:__security_cookie
0x180008b89  xor     rax, rsp
0x180008b8c  mov     [rbp+0A10h+var_40], rax
0x180008b93  mov     rbx, r9
0x180008b96  mov     r15d, r8d
0x180008b99  mov     rdi, rdx
0x180008b9c  mov     r14, rcx
0x180008b9f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180008ba6  mov     [rsp+0B10h+var_AD0], rax
0x180008bab  xor     r12d, r12d
0x180008bae  mov     [rsp+0B10h+var_AC8], r12
0x180008bb3  mov     [rsp+0B10h+var_AC0], r12
0x180008bb8  mov     [rsp+0B10h+var_AB8], r12d
0x180008bbd  xorps   xmm0, xmm0
0x180008bc0  xor     eax, eax
0x180008bc2  movups  [rsp+0B10h+var_AB0], xmm0
0x180008bc7  movups  [rsp+0B10h+var_AA0], xmm0
0x180008bcc  mov     [rbp+0A10h+var_A90], rax
0x180008bd0  mov     [rbp+0A10h+var_A88], r12b
0x180008bd4  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180008bd9  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180008bde  mov     esi, eax
0x180008be0  test    eax, eax
0x180008be2  jns     short loc_180008C11
0x180008be4  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008be9  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008bee  mov     eax, esi
0x180008bf0  mov     rcx, [rbp+0A10h+var_40]
0x180008bf7  xor     rcx, rsp; StackCookie
0x180008bfa  call    __security_check_cookie
0x180008bff  add     rsp, 0AE0h
0x180008c06  pop     r15
0x180008c08  pop     r14
0x180008c0a  pop     r12
0x180008c0c  pop     rdi
0x180008c0d  pop     rsi
0x180008c0e  pop     rbx
0x180008c0f  pop     rbp
0x180008c10  retn
0x180008c11  test    rbx, rbx
0x180008c14  jz      short loc_180008C35
0x180008c16  jmp     short loc_180008C2D
0x180008c18  mov     r8, [rbx+8]; unsigned __int16 *
0x180008c1c  mov     rdx, rax; unsigned __int16 *
0x180008c1f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008c24  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180008c29  lea     rbx, [rbx+10h]
0x180008c2d  mov     rax, [rbx]
0x180008c30  test    rax, rax
0x180008c33  jnz     short loc_180008C18
0x180008c35  mov     rax, [r14]
0x180008c38  lea     rdx, [rsp+0B10h+var_AD0]
0x180008c3d  mov     rcx, r14
0x180008c40  mov     rax, [rax+28h]
0x180008c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c49  mov     ebx, eax
0x180008c4b  test    eax, eax
0x180008c4d  js      loc_180008D81
0x180008c53  mov     [rsp+0B10h+var_AE0], r12
0x180008c58  mov     rbx, cs:hModule
0x180008c5f  mov     esi, 104h
0x180008c64  mov     r8d, esi; nSize
0x180008c67  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180008c6b  mov     rcx, rbx; hModule
0x180008c6e  call    cs:__imp_GetModuleFileNameW
0x180008c74  test    eax, eax
0x180008c76  jnz     short loc_180008C84
0x180008c78  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180008c7d  mov     ebx, eax
0x180008c7f  jmp     loc_180008D77
0x180008c84  cmp     eax, esi
0x180008c86  jnz     short loc_180008C9C
0x180008c88  lea     rcx, [rsp+0B10h+var_AE0]
0x180008c8d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008c92  mov     ebx, 8007007Ah
0x180008c97  jmp     loc_180008D81
0x180008c9c  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180008ca0  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180008ca7  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180008cac  test    rbx, rbx
0x180008caf  jz      short loc_180008CC7
0x180008cb1  xor     ecx, ecx; lpModuleName
0x180008cb3  call    cs:__imp_GetModuleHandleW
0x180008cb9  cmp     rbx, rax
0x180008cbc  jz      short loc_180008CC7
0x180008cbe  lea     r8, [rbp+0A10h+var_450]
0x180008cc5  jmp     short loc_180008D42
0x180008cc7  mov     ebx, 22h ; '"'
0x180008ccc  mov     [rbp+0A10h+var_870], bx
0x180008cd3  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180008cda  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180008ce1  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180008ce6  test    al, al
0x180008ce8  jnz     short loc_180008CFE
0x180008cea  lea     rcx, [rsp+0B10h+var_AE0]
0x180008cef  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008cf4  mov     ebx, 80004005h
0x180008cf9  jmp     loc_180008D81
0x180008cfe  lea     rcx, [rbp+0A10h+var_870]
0x180008d05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008d09  inc     rax
0x180008d0c  cmp     [rcx+rax*2], r12w
0x180008d11  jnz     short loc_180008D09
0x180008d13  cdqe
0x180008d15  mov     [rbp+rax*2+0A10h+var_870], bx
0x180008d1d  lea     rcx, ds:2[rax*2]
0x180008d25  cmp     rcx, 418h
0x180008d2c  jnb     loc_180008DE2
0x180008d32  mov     [rbp+rcx+0A10h+var_870], r12w
0x180008d3b  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180008d42  lea     rdx, aModule; "Module"
0x180008d49  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008d4e  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180008d53  mov     ebx, eax
0x180008d55  test    eax, eax
0x180008d57  js      short loc_180008D77
0x180008d59  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180008d60  lea     rdx, aModuleRaw; "Module_Raw"
0x180008d67  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008d6c  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180008d71  mov     ebx, eax
0x180008d73  test    eax, eax
0x180008d75  jns     short loc_180008D92
0x180008d77  lea     rcx, [rsp+0B10h+var_AE0]
0x180008d7c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008d81  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008d86  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008d8b  mov     eax, ebx
0x180008d8d  jmp     loc_180008BF0
0x180008d92  mov     [rsp+0B10h+var_AD8], r12
0x180008d97  test    r15d, r15d
0x180008d9a  jz      short loc_180008DAB
0x180008d9c  test    rdi, rdi
0x180008d9f  jz      short loc_180008DD1
0x180008da1  mov     [rsp+0B10h+var_AF0], 1
0x180008da9  jmp     short loc_180008DB5
0x180008dab  test    rdi, rdi
0x180008dae  jz      short loc_180008DD1
0x180008db0  mov     [rsp+0B10h+var_AF0], r12d; int
0x180008db5  lea     r9, aRegistry_0; "REGISTRY"
0x180008dbc  mov     r8, rdi; unsigned __int16 *
0x180008dbf  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180008dc3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008dc8  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008dcd  mov     ebx, eax
0x180008dcf  jmp     short loc_180008DD6
0x180008dd1  mov     ebx, 80070057h
0x180008dd6  lea     rcx, [rsp+0B10h+var_AD8]
0x180008ddb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008de0  jmp     short loc_180008D77
0x180008de2  call    __report_rangecheckfailure
```
