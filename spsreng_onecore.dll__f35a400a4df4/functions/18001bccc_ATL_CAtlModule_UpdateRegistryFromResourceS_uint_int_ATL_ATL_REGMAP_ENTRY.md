# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001bccc`
- end: `0x18001bf3c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bb40`
- `0x18001bca0`
- `0x18001c1d0`

## callees

- `0x1800034b0`
- `0x180003640`
- `0x18000d234`
- `0x180014f98`
- `0x1800158b0`
- `0x180016670`
- `0x180016f48`
- `0x180019680`
- `0x18001ac10`
- `0x18001bccc`
- `0x18001c818`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001be17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001be17`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bdd2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bdd2`

## string_xrefs

- `0x18001beff`: `REGISTRY`

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
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  _OWORD v24[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  char v26; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v28; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v29[527]; // [rsp+2A2h] [rbp+1A2h] BYREF
  unsigned __int16 v30[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v22[0] = &ATL::CRegObject::`vftable';
  v22[1] = 0;
  v22[2] = 0;
  v23 = 0;
  memset(v24, 0, sizeof(v24));
  v25 = 0;
  v26 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v24);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v22);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v22,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v22);
  if ( Error >= 0 )
  {
    v20 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
      goto LABEL_24;
    }
    if ( ModuleFileNameW != 260 )
    {
      ATL::CAtlModule::EscapeSingleQuote(v30, v13, Filename);
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v28 = 34;
        if ( !ocscpy_s(v29, v14, v30) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
          Error = -2147467259;
          goto LABEL_24;
        }
        v17 = -1;
        do
          ++v17;
        while ( v29[v17 - 1] );
        v29[(int)v17 - 1] = 34;
        v18 = 2LL * (int)v17 + 2;
        if ( v18 >= 0x418 )
          _report_rangecheckfailure(v18, v16);
        *(unsigned __int16 *)((char *)&v29[-1] + v18) = 0;
        v15 = &v28;
      }
      else
      {
        v15 = v30;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v22, L"Module", v15);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v22, L"Module_Raw", v30);
        if ( Error >= 0 )
        {
          v21 = 0;
          if ( a3 )
            v19 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v22,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v19 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v22,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v19;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
        }
      }
      goto LABEL_23;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
    Error = -2147024774;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v22);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001bccc  push    rbp
0x18001bcce  push    rbx
0x18001bccf  push    rsi
0x18001bcd0  push    rdi
0x18001bcd1  push    r12
0x18001bcd3  push    r14
0x18001bcd5  push    r15
0x18001bcd7  lea     rbp, [rsp-9E0h]
0x18001bcdf  sub     rsp, 0AE0h
0x18001bce6  mov     rax, cs:__security_cookie
0x18001bced  xor     rax, rsp
0x18001bcf0  mov     [rbp+0A10h+var_40], rax
0x18001bcf7  mov     rbx, r9
0x18001bcfa  mov     r14d, r8d
0x18001bcfd  mov     r15d, edx
0x18001bd00  mov     rsi, rcx
0x18001bd03  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001bd0a  mov     [rsp+0B10h+var_AD0], rax
0x18001bd0f  xor     r12d, r12d
0x18001bd12  mov     [rsp+0B10h+var_AC8], r12
0x18001bd17  mov     [rsp+0B10h+var_AC0], r12
0x18001bd1c  mov     [rsp+0B10h+var_AB8], r12d
0x18001bd21  xorps   xmm0, xmm0
0x18001bd24  xor     eax, eax
0x18001bd26  movups  [rsp+0B10h+var_AB0], xmm0
0x18001bd2b  movups  [rsp+0B10h+var_AA0], xmm0
0x18001bd30  mov     [rbp+0A10h+var_A90], rax
0x18001bd34  mov     [rbp+0A10h+var_A88], r12b
0x18001bd38  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18001bd3d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001bd42  mov     edi, eax
0x18001bd44  test    eax, eax
0x18001bd46  jns     short loc_18001BD75
0x18001bd48  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bd4d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001bd52  mov     eax, edi
0x18001bd54  mov     rcx, [rbp+0A10h+var_40]
0x18001bd5b  xor     rcx, rsp; StackCookie
0x18001bd5e  call    __security_check_cookie
0x18001bd63  add     rsp, 0AE0h
0x18001bd6a  pop     r15
0x18001bd6c  pop     r14
0x18001bd6e  pop     r12
0x18001bd70  pop     rdi
0x18001bd71  pop     rsi
0x18001bd72  pop     rbx
0x18001bd73  pop     rbp
0x18001bd74  retn
0x18001bd75  test    rbx, rbx
0x18001bd78  jz      short loc_18001BD99
0x18001bd7a  jmp     short loc_18001BD91
0x18001bd7c  mov     r8, [rbx+8]; unsigned __int16 *
0x18001bd80  mov     rdx, rax; unsigned __int16 *
0x18001bd83  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bd88  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001bd8d  lea     rbx, [rbx+10h]
0x18001bd91  mov     rax, [rbx]
0x18001bd94  test    rax, rax
0x18001bd97  jnz     short loc_18001BD7C
0x18001bd99  mov     rax, [rsi]
0x18001bd9c  lea     rdx, [rsp+0B10h+var_AD0]
0x18001bda1  mov     rcx, rsi
0x18001bda4  mov     rax, [rax+28h]
0x18001bda8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdad  mov     ebx, eax
0x18001bdaf  test    eax, eax
0x18001bdb1  js      loc_18001BEE5
0x18001bdb7  mov     [rsp+0B10h+var_AE0], r12
0x18001bdbc  mov     rbx, cs:hModule
0x18001bdc3  mov     edi, 104h
0x18001bdc8  mov     r8d, edi; nSize
0x18001bdcb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18001bdcf  mov     rcx, rbx; hModule
0x18001bdd2  call    cs:__imp_GetModuleFileNameW
0x18001bdd8  test    eax, eax
0x18001bdda  jnz     short loc_18001BDE8
0x18001bddc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001bde1  mov     ebx, eax
0x18001bde3  jmp     loc_18001BEDB
0x18001bde8  cmp     eax, edi
0x18001bdea  jnz     short loc_18001BE00
0x18001bdec  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bdf1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bdf6  mov     ebx, 8007007Ah
0x18001bdfb  jmp     loc_18001BEE5
0x18001be00  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001be04  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001be0b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001be10  test    rbx, rbx
0x18001be13  jz      short loc_18001BE2B
0x18001be15  xor     ecx, ecx; lpModuleName
0x18001be17  call    cs:__imp_GetModuleHandleW
0x18001be1d  cmp     rbx, rax
0x18001be20  jz      short loc_18001BE2B
0x18001be22  lea     r8, [rbp+0A10h+var_450]
0x18001be29  jmp     short loc_18001BEA6
0x18001be2b  mov     ebx, 22h ; '"'
0x18001be30  mov     [rbp+0A10h+var_870], bx
0x18001be37  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001be3e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18001be45  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001be4a  test    al, al
0x18001be4c  jnz     short loc_18001BE62
0x18001be4e  lea     rcx, [rsp+0B10h+var_AE0]
0x18001be53  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001be58  mov     ebx, 80004005h
0x18001be5d  jmp     loc_18001BEE5
0x18001be62  lea     rcx, [rbp+0A10h+var_870]
0x18001be69  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001be6d  inc     rax
0x18001be70  cmp     [rcx+rax*2], r12w
0x18001be75  jnz     short loc_18001BE6D
0x18001be77  cdqe
0x18001be79  mov     [rbp+rax*2+0A10h+var_870], bx
0x18001be81  lea     rcx, ds:2[rax*2]
0x18001be89  cmp     rcx, 418h
0x18001be90  jnb     loc_18001BF36
0x18001be96  mov     [rbp+rcx+0A10h+var_870], r12w
0x18001be9f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18001bea6  lea     rdx, aModule; "Module"
0x18001bead  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001beb2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001beb7  mov     ebx, eax
0x18001beb9  test    eax, eax
0x18001bebb  js      short loc_18001BEDB
0x18001bebd  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18001bec4  lea     rdx, aModuleRaw; "Module_Raw"
0x18001becb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bed0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001bed5  mov     ebx, eax
0x18001bed7  test    eax, eax
0x18001bed9  jns     short loc_18001BEF6
0x18001bedb  lea     rcx, [rsp+0B10h+var_AE0]
0x18001bee0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bee5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001beea  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001beef  mov     eax, ebx
0x18001bef1  jmp     loc_18001BD54
0x18001bef6  movzx   r8d, r15w; unsigned __int16 *
0x18001befa  mov     [rsp+0B10h+var_AD8], r12
0x18001beff  lea     r9, aRegistry; "REGISTRY"
0x18001bf06  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18001bf0a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18001bf0f  test    r14d, r14d
0x18001bf12  jz      short loc_18001BF1E
0x18001bf14  mov     [rsp+0B10h+var_AF0], 1
0x18001bf1c  jmp     short loc_18001BF23
0x18001bf1e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18001bf23  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001bf28  mov     ebx, eax
0x18001bf2a  lea     rcx, [rsp+0B10h+var_AD8]
0x18001bf2f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001bf34  jmp     short loc_18001BEDB
0x18001bf36  call    __report_rangecheckfailure
```
