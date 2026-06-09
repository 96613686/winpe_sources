# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800088f0`
- end: `0x180008b60`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `6`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008840`
- `0x180008860`
- `0x180008880`
- `0x1800088b0`
- `0x1800088d0`
- `0x180008df0`

## callees

- `0x180002248`
- `0x180002d78`
- `0x1800032e0`
- `0x180003b10`
- `0x180004370`
- `0x180005f7c`
- `0x180006920`
- `0x180007700`
- `0x1800088f0`
- `0x180008e0c`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800089f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800089f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a3b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a3b`

## string_xrefs

- `0x180008b23`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
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
    if ( ModuleFileNameW != 260 )
    {
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
      if ( LastErrorHRESULT >= 0 )
      {
        LastErrorHRESULT = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v29);
        if ( LastErrorHRESULT >= 0 )
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
          LastErrorHRESULT = v18;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
      goto LABEL_23;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    LastErrorHRESULT = -2147024774;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)LastErrorHRESULT;
}

```

## disassembly

```asm
0x1800088f0  push    rbp
0x1800088f2  push    rbx
0x1800088f3  push    rsi
0x1800088f4  push    rdi
0x1800088f5  push    r12
0x1800088f7  push    r14
0x1800088f9  push    r15
0x1800088fb  lea     rbp, [rsp-9E0h]
0x180008903  sub     rsp, 0AE0h
0x18000890a  mov     rax, cs:__security_cookie
0x180008911  xor     rax, rsp
0x180008914  mov     [rbp+0A10h+var_40], rax
0x18000891b  mov     rbx, r9
0x18000891e  mov     r14d, r8d
0x180008921  mov     r15d, edx
0x180008924  mov     rsi, rcx
0x180008927  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000892e  mov     [rsp+0B10h+var_AD0], rax
0x180008933  xor     r12d, r12d
0x180008936  mov     [rsp+0B10h+var_AC8], r12
0x18000893b  mov     [rsp+0B10h+var_AC0], r12
0x180008940  mov     [rsp+0B10h+var_AB8], r12d
0x180008945  xorps   xmm0, xmm0
0x180008948  xor     eax, eax
0x18000894a  movups  [rsp+0B10h+var_AB0], xmm0
0x18000894f  movups  [rsp+0B10h+var_AA0], xmm0
0x180008954  mov     [rbp+0A10h+var_A90], rax
0x180008958  mov     [rbp+0A10h+var_A88], r12b
0x18000895c  lea     rcx, [rsp+0B10h+var_AB0]; this
0x180008961  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180008966  mov     edi, eax
0x180008968  test    eax, eax
0x18000896a  jns     short loc_180008999
0x18000896c  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008971  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008976  mov     eax, edi
0x180008978  mov     rcx, [rbp+0A10h+var_40]
0x18000897f  xor     rcx, rsp; StackCookie
0x180008982  call    __security_check_cookie
0x180008987  add     rsp, 0AE0h
0x18000898e  pop     r15
0x180008990  pop     r14
0x180008992  pop     r12
0x180008994  pop     rdi
0x180008995  pop     rsi
0x180008996  pop     rbx
0x180008997  pop     rbp
0x180008998  retn
0x180008999  test    rbx, rbx
0x18000899c  jz      short loc_1800089BD
0x18000899e  jmp     short loc_1800089B5
0x1800089a0  mov     r8, [rbx+8]; unsigned __int16 *
0x1800089a4  mov     rdx, rax; unsigned __int16 *
0x1800089a7  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800089ac  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800089b1  lea     rbx, [rbx+10h]
0x1800089b5  mov     rax, [rbx]
0x1800089b8  test    rax, rax
0x1800089bb  jnz     short loc_1800089A0
0x1800089bd  mov     rax, [rsi]
0x1800089c0  lea     rdx, [rsp+0B10h+var_AD0]
0x1800089c5  mov     rcx, rsi
0x1800089c8  mov     rax, [rax+28h]
0x1800089cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089d1  mov     ebx, eax
0x1800089d3  test    eax, eax
0x1800089d5  js      loc_180008B09
0x1800089db  mov     [rsp+0B10h+var_AE0], r12
0x1800089e0  mov     rbx, cs:hModule
0x1800089e7  mov     edi, 104h
0x1800089ec  mov     r8d, edi; nSize
0x1800089ef  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800089f3  mov     rcx, rbx; hModule
0x1800089f6  call    cs:__imp_GetModuleFileNameW
0x1800089fc  test    eax, eax
0x1800089fe  jnz     short loc_180008A0C
0x180008a00  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180008a05  mov     ebx, eax
0x180008a07  jmp     loc_180008AFF
0x180008a0c  cmp     eax, edi
0x180008a0e  jnz     short loc_180008A24
0x180008a10  lea     rcx, [rsp+0B10h+var_AE0]
0x180008a15  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008a1a  mov     ebx, 8007007Ah
0x180008a1f  jmp     loc_180008B09
0x180008a24  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180008a28  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x180008a2f  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180008a34  test    rbx, rbx
0x180008a37  jz      short loc_180008A4F
0x180008a39  xor     ecx, ecx; lpModuleName
0x180008a3b  call    cs:__imp_GetModuleHandleW
0x180008a41  cmp     rbx, rax
0x180008a44  jz      short loc_180008A4F
0x180008a46  lea     r8, [rbp+0A10h+var_450]
0x180008a4d  jmp     short loc_180008ACA
0x180008a4f  mov     ebx, 22h ; '"'
0x180008a54  mov     [rbp+0A10h+var_870], bx
0x180008a5b  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180008a62  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180008a69  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x180008a6e  test    al, al
0x180008a70  jnz     short loc_180008A86
0x180008a72  lea     rcx, [rsp+0B10h+var_AE0]
0x180008a77  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008a7c  mov     ebx, 80004005h
0x180008a81  jmp     loc_180008B09
0x180008a86  lea     rcx, [rbp+0A10h+var_870]
0x180008a8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008a91  inc     rax
0x180008a94  cmp     [rcx+rax*2], r12w
0x180008a99  jnz     short loc_180008A91
0x180008a9b  cdqe
0x180008a9d  mov     [rbp+rax*2+0A10h+var_870], bx
0x180008aa5  lea     rcx, ds:2[rax*2]
0x180008aad  cmp     rcx, 418h
0x180008ab4  jnb     loc_180008B5A
0x180008aba  mov     [rbp+rcx+0A10h+var_870], r12w
0x180008ac3  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x180008aca  lea     rdx, aModule; "Module"
0x180008ad1  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008ad6  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180008adb  mov     ebx, eax
0x180008add  test    eax, eax
0x180008adf  js      short loc_180008AFF
0x180008ae1  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x180008ae8  lea     rdx, aModuleRaw; "Module_Raw"
0x180008aef  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008af4  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180008af9  mov     ebx, eax
0x180008afb  test    eax, eax
0x180008afd  jns     short loc_180008B1A
0x180008aff  lea     rcx, [rsp+0B10h+var_AE0]
0x180008b04  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008b09  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008b0e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008b13  mov     eax, ebx
0x180008b15  jmp     loc_180008978
0x180008b1a  movzx   r8d, r15w; unsigned __int16 *
0x180008b1e  mov     [rsp+0B10h+var_AD8], r12
0x180008b23  lea     r9, aRegistry_0; "REGISTRY"
0x180008b2a  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180008b2e  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008b33  test    r14d, r14d
0x180008b36  jz      short loc_180008B42
0x180008b38  mov     [rsp+0B10h+var_AF0], 1
0x180008b40  jmp     short loc_180008B47
0x180008b42  mov     [rsp+0B10h+var_AF0], r12d; int
0x180008b47  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180008b4c  mov     ebx, eax
0x180008b4e  lea     rcx, [rsp+0B10h+var_AD8]
0x180008b53  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180008b58  jmp     short loc_180008AFF
0x180008b5a  call    __report_rangecheckfailure
```
