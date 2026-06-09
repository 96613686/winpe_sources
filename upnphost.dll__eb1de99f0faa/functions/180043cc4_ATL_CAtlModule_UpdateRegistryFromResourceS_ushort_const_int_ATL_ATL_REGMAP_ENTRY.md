# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180043cc4`
- end: `0x180043f44`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `640`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043f60`

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
- `0x180043cc4`
- `0x1800444a0`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180043dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180043dca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043e0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043e0f`

## string_xrefs

- `0x180043f11`: `REGISTRY`

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
0x180043cc4  push    rbp
0x180043cc6  push    rbx
0x180043cc7  push    rsi
0x180043cc8  push    rdi
0x180043cc9  push    r12
0x180043ccb  push    r14
0x180043ccd  push    r15
0x180043ccf  lea     rbp, [rsp-9E0h]
0x180043cd7  sub     rsp, 0AE0h
0x180043cde  mov     rax, cs:__security_cookie
0x180043ce5  xor     rax, rsp
0x180043ce8  mov     [rbp+0A10h+var_40], rax
0x180043cef  xor     r12d, r12d
0x180043cf2  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180043cf9  xorps   xmm0, xmm0
0x180043cfc  mov     [rsp+0B10h+var_AD0], rax
0x180043d01  xor     eax, eax
0x180043d03  mov     [rsp+0B10h+var_AC8], r12
0x180043d08  mov     r14, rcx
0x180043d0b  mov     [rbp+0A10h+var_A90], rax
0x180043d0f  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180043d14  mov     [rsp+0B10h+var_AC0], r12
0x180043d19  mov     rbx, r9
0x180043d1c  mov     [rsp+0B10h+var_AB8], r12d
0x180043d21  mov     r15d, r8d
0x180043d24  mov     [rbp+0A10h+var_A88], r12b
0x180043d28  mov     rdi, rdx
0x180043d2b  movups  [rsp+0B10h+var_AB0], xmm0
0x180043d30  movups  [rsp+0B10h+var_AA0], xmm0
0x180043d35  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180043d3a  mov     esi, eax
0x180043d3c  test    eax, eax
0x180043d3e  jns     short loc_180043D6D
0x180043d40  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043d45  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180043d4a  mov     eax, esi
0x180043d4c  mov     rcx, [rbp+0A10h+var_40]
0x180043d53  xor     rcx, rsp; StackCookie
0x180043d56  call    __security_check_cookie
0x180043d5b  add     rsp, 0AE0h
0x180043d62  pop     r15
0x180043d64  pop     r14
0x180043d66  pop     r12
0x180043d68  pop     rdi
0x180043d69  pop     rsi
0x180043d6a  pop     rbx
0x180043d6b  pop     rbp
0x180043d6c  retn
0x180043d6d  test    rbx, rbx
0x180043d70  jz      short loc_180043D91
0x180043d72  jmp     short loc_180043D89
0x180043d74  mov     r8, [rbx+8]; unsigned __int16 *
0x180043d78  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043d7d  mov     rdx, rax; unsigned __int16 *
0x180043d80  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180043d85  lea     rbx, [rbx+10h]
0x180043d89  mov     rax, [rbx]
0x180043d8c  test    rax, rax
0x180043d8f  jnz     short loc_180043D74
0x180043d91  mov     rax, [r14]
0x180043d94  lea     rdx, [rsp+0B10h+var_AD0]
0x180043d99  mov     rcx, r14
0x180043d9c  mov     rax, [rax+28h]
0x180043da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043da5  mov     ebx, eax
0x180043da7  test    eax, eax
0x180043da9  js      loc_180043EDD
0x180043daf  mov     rbx, cs:hModule
0x180043db6  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180043dba  mov     esi, 104h
0x180043dbf  mov     [rsp+0B10h+var_AE0], r12
0x180043dc4  mov     r8d, esi; nSize
0x180043dc7  mov     rcx, rbx; hModule
0x180043dca  call    cs:__imp_GetModuleFileNameW
0x180043dd0  test    eax, eax
0x180043dd2  jnz     short loc_180043DE0
0x180043dd4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180043dd9  mov     ebx, eax
0x180043ddb  jmp     loc_180043ED3
0x180043de0  cmp     eax, esi
0x180043de2  jnz     short loc_180043DF8
0x180043de4  lea     rcx, [rsp+0B10h+var_AE0]
0x180043de9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180043dee  mov     ebx, 8007007Ah
0x180043df3  jmp     loc_180043EDD
0x180043df8  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180043dfc  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180043e03  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180043e08  test    rbx, rbx
0x180043e0b  jz      short loc_180043E23
0x180043e0d  xor     ecx, ecx; lpModuleName
0x180043e0f  call    cs:__imp_GetModuleHandleW
0x180043e15  cmp     rbx, rax
0x180043e18  jz      short loc_180043E23
0x180043e1a  lea     r8, [rbp+0A10h+var_450]
0x180043e21  jmp     short loc_180043E9E
0x180043e23  mov     ebx, 22h ; '"'
0x180043e28  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180043e2f  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180043e36  mov     [rbp+0A10h+var_870], bx
0x180043e3d  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180043e42  test    al, al
0x180043e44  jnz     short loc_180043E5A
0x180043e46  lea     rcx, [rsp+0B10h+var_AE0]
0x180043e4b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180043e50  mov     ebx, 80004005h
0x180043e55  jmp     loc_180043EDD
0x180043e5a  lea     rcx, [rbp+0A10h+var_870]
0x180043e61  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043e65  inc     rax
0x180043e68  cmp     [rcx+rax*2], r12w
0x180043e6d  jnz     short loc_180043E65
0x180043e6f  cdqe
0x180043e71  lea     rcx, ds:2[rax*2]
0x180043e79  mov     [rbp+rax*2+0A10h+var_870], bx
0x180043e81  cmp     rcx, 418h
0x180043e88  jnb     loc_180043F3E
0x180043e8e  mov     [rbp+rcx+0A10h+var_870], r12w
0x180043e97  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180043e9e  lea     rdx, aModule; "Module"
0x180043ea5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043eaa  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180043eaf  mov     ebx, eax
0x180043eb1  test    eax, eax
0x180043eb3  js      short loc_180043ED3
0x180043eb5  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180043ebc  lea     rdx, aModuleRaw; "Module_Raw"
0x180043ec3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043ec8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180043ecd  mov     ebx, eax
0x180043ecf  test    eax, eax
0x180043ed1  jns     short loc_180043EEE
0x180043ed3  lea     rcx, [rsp+0B10h+var_AE0]
0x180043ed8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180043edd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043ee2  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180043ee7  mov     eax, ebx
0x180043ee9  jmp     loc_180043D4C
0x180043eee  mov     [rsp+0B10h+var_AD8], r12
0x180043ef3  test    r15d, r15d
0x180043ef6  jz      short loc_180043F07
0x180043ef8  test    rdi, rdi
0x180043efb  jz      short loc_180043F2D
0x180043efd  mov     [rsp+0B10h+var_AF0], 1
0x180043f05  jmp     short loc_180043F11
0x180043f07  test    rdi, rdi
0x180043f0a  jz      short loc_180043F2D
0x180043f0c  mov     [rsp+0B10h+var_AF0], r12d; int
0x180043f11  lea     r9, aRegistry; "REGISTRY"
0x180043f18  mov     r8, rdi; unsigned __int16 *
0x180043f1b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180043f1f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180043f24  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180043f29  mov     ebx, eax
0x180043f2b  jmp     short loc_180043F32
0x180043f2d  mov     ebx, 80070057h
0x180043f32  lea     rcx, [rsp+0B10h+var_AD8]
0x180043f37  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180043f3c  jmp     short loc_180043ED3
0x180043f3e  call    __report_rangecheckfailure
```
