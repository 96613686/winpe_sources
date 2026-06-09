# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000fb2c`
- end: `0x18000fd9c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010030`

## callees

- `0x180001b98`
- `0x180002274`
- `0x18000282c`
- `0x180002f10`
- `0x180004528`
- `0x180008604`
- `0x18000c784`
- `0x18000d3ec`
- `0x18000fb2c`
- `0x180020448`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000fc77`
- `KERNEL32!GetModuleHandleW` at `0x18000fc77`
- `KERNEL32!GetModuleFileNameW` at `0x18000fc32`
- `KERNEL32!GetModuleFileNameW` at `0x18000fc32`

## string_xrefs

- `0x18000fd5a`: `REGISTRY`

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
0x18000fb2c  push    rbp
0x18000fb2e  push    rbx
0x18000fb2f  push    rsi
0x18000fb30  push    rdi
0x18000fb31  push    r12
0x18000fb33  push    r14
0x18000fb35  push    r15
0x18000fb37  lea     rbp, [rsp-9E0h]
0x18000fb3f  sub     rsp, 0AE0h
0x18000fb46  mov     rax, cs:__security_cookie
0x18000fb4d  xor     rax, rsp
0x18000fb50  mov     [rbp+0A10h+var_40], rax
0x18000fb57  xor     r12d, r12d
0x18000fb5a  mov     r15d, edx
0x18000fb5d  xorps   xmm0, xmm0
0x18000fb60  mov     [rsp+0B10h+var_AC8], r12
0x18000fb65  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000fb6c  mov     [rsp+0B10h+var_AC0], r12
0x18000fb71  mov     [rsp+0B10h+var_AD0], rax
0x18000fb76  mov     rsi, rcx
0x18000fb79  xor     eax, eax
0x18000fb7b  mov     [rsp+0B10h+var_AB8], r12d
0x18000fb80  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000fb85  mov     [rbp+0A10h+var_A90], rax
0x18000fb89  mov     rbx, r9
0x18000fb8c  mov     [rbp+0A10h+var_A88], r12b
0x18000fb90  mov     r14d, r8d
0x18000fb93  movups  [rsp+0B10h+var_AB0], xmm0
0x18000fb98  movups  [rsp+0B10h+var_AA0], xmm0
0x18000fb9d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000fba2  mov     edi, eax
0x18000fba4  test    eax, eax
0x18000fba6  jns     short loc_18000FBD5
0x18000fba8  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fbad  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000fbb2  mov     eax, edi
0x18000fbb4  mov     rcx, [rbp+0A10h+var_40]
0x18000fbbb  xor     rcx, rsp; StackCookie
0x18000fbbe  call    __security_check_cookie
0x18000fbc3  add     rsp, 0AE0h
0x18000fbca  pop     r15
0x18000fbcc  pop     r14
0x18000fbce  pop     r12
0x18000fbd0  pop     rdi
0x18000fbd1  pop     rsi
0x18000fbd2  pop     rbx
0x18000fbd3  pop     rbp
0x18000fbd4  retn
0x18000fbd5  test    rbx, rbx
0x18000fbd8  jz      short loc_18000FBF9
0x18000fbda  jmp     short loc_18000FBF1
0x18000fbdc  mov     r8, [rbx+8]; unsigned __int16 *
0x18000fbe0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fbe5  mov     rdx, rax; unsigned __int16 *
0x18000fbe8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000fbed  lea     rbx, [rbx+10h]
0x18000fbf1  mov     rax, [rbx]
0x18000fbf4  test    rax, rax
0x18000fbf7  jnz     short loc_18000FBDC
0x18000fbf9  mov     rax, [rsi]
0x18000fbfc  lea     rdx, [rsp+0B10h+var_AD0]
0x18000fc01  mov     rcx, rsi
0x18000fc04  mov     rax, [rax+28h]
0x18000fc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc0d  mov     ebx, eax
0x18000fc0f  test    eax, eax
0x18000fc11  js      loc_18000FD45
0x18000fc17  mov     rbx, cs:hInstance
0x18000fc1e  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000fc22  mov     edi, 104h
0x18000fc27  mov     [rsp+0B10h+var_AE0], r12
0x18000fc2c  mov     r8d, edi; nSize
0x18000fc2f  mov     rcx, rbx; hModule
0x18000fc32  call    cs:__imp_GetModuleFileNameW
0x18000fc38  test    eax, eax
0x18000fc3a  jnz     short loc_18000FC48
0x18000fc3c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000fc41  mov     ebx, eax
0x18000fc43  jmp     loc_18000FD3B
0x18000fc48  cmp     eax, edi
0x18000fc4a  jnz     short loc_18000FC60
0x18000fc4c  lea     rcx, [rsp+0B10h+var_AE0]
0x18000fc51  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fc56  mov     ebx, 8007007Ah
0x18000fc5b  jmp     loc_18000FD45
0x18000fc60  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000fc64  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000fc6b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000fc70  test    rbx, rbx
0x18000fc73  jz      short loc_18000FC8B
0x18000fc75  xor     ecx, ecx; lpModuleName
0x18000fc77  call    cs:__imp_GetModuleHandleW
0x18000fc7d  cmp     rbx, rax
0x18000fc80  jz      short loc_18000FC8B
0x18000fc82  lea     r8, [rbp+0A10h+var_450]
0x18000fc89  jmp     short loc_18000FD06
0x18000fc8b  mov     ebx, 22h ; '"'
0x18000fc90  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000fc97  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000fc9e  mov     [rbp+0A10h+var_870], bx
0x18000fca5  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000fcaa  test    al, al
0x18000fcac  jnz     short loc_18000FCC2
0x18000fcae  lea     rcx, [rsp+0B10h+var_AE0]
0x18000fcb3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fcb8  mov     ebx, 80004005h
0x18000fcbd  jmp     loc_18000FD45
0x18000fcc2  lea     rcx, [rbp+0A10h+var_870]
0x18000fcc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fccd  inc     rax
0x18000fcd0  cmp     [rcx+rax*2], r12w
0x18000fcd5  jnz     short loc_18000FCCD
0x18000fcd7  cdqe
0x18000fcd9  lea     rcx, ds:2[rax*2]
0x18000fce1  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000fce9  cmp     rcx, 418h
0x18000fcf0  jnb     loc_18000FD96
0x18000fcf6  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000fcff  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000fd06  lea     rdx, aModule; "Module"
0x18000fd0d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fd12  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000fd17  mov     ebx, eax
0x18000fd19  test    eax, eax
0x18000fd1b  js      short loc_18000FD3B
0x18000fd1d  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000fd24  lea     rdx, aModuleRaw; "Module_Raw"
0x18000fd2b  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fd30  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000fd35  mov     ebx, eax
0x18000fd37  test    eax, eax
0x18000fd39  jns     short loc_18000FD56
0x18000fd3b  lea     rcx, [rsp+0B10h+var_AE0]
0x18000fd40  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fd45  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fd4a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000fd4f  mov     eax, ebx
0x18000fd51  jmp     loc_18000FBB4
0x18000fd56  movzx   r8d, r15w; unsigned __int16 *
0x18000fd5a  lea     r9, aRegistry; "REGISTRY"
0x18000fd61  mov     [rsp+0B10h+var_AD8], r12
0x18000fd66  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000fd6a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000fd6f  test    r14d, r14d
0x18000fd72  jz      short loc_18000FD7E
0x18000fd74  mov     [rsp+0B10h+var_AF0], 1
0x18000fd7c  jmp     short loc_18000FD83
0x18000fd7e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000fd83  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000fd88  lea     rcx, [rsp+0B10h+var_AD8]
0x18000fd8d  mov     ebx, eax
0x18000fd8f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000fd94  jmp     short loc_18000FD3B
0x18000fd96  call    __report_rangecheckfailure
```
