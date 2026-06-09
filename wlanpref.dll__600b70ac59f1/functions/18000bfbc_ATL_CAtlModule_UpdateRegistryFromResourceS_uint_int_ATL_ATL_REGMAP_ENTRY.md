# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000bfbc`
- end: `0x18000c22c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `13`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000be30`
- `0x18000be50`
- `0x18000be70`
- `0x18000be90`
- `0x18000beb0`
- `0x18000bed0`
- `0x18000bef0`
- `0x18000bf10`
- `0x18000bf30`
- `0x18000bf50`
- `0x18000bf70`
- `0x18000bf90`
- `0x18000c4c0`

## callees

- `0x180001c08`
- `0x180002cc0`
- `0x180003674`
- `0x1800042d0`
- `0x180004c4c`
- `0x18000777c`
- `0x1800080a0`
- `0x18000acc0`
- `0x18000bfbc`
- `0x18000c510`
- `0x18002d840`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c107`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c107`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c0c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c0c2`

## string_xrefs

- `0x18000c1ef`: `REGISTRY`

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
0x18000bfbc  push    rbp
0x18000bfbe  push    rbx
0x18000bfbf  push    rsi
0x18000bfc0  push    rdi
0x18000bfc1  push    r12
0x18000bfc3  push    r14
0x18000bfc5  push    r15
0x18000bfc7  lea     rbp, [rsp-9E0h]
0x18000bfcf  sub     rsp, 0AE0h
0x18000bfd6  mov     rax, cs:__security_cookie
0x18000bfdd  xor     rax, rsp
0x18000bfe0  mov     [rbp+0A10h+var_40], rax
0x18000bfe7  mov     rbx, r9
0x18000bfea  mov     r14d, r8d
0x18000bfed  mov     r15d, edx
0x18000bff0  mov     rsi, rcx
0x18000bff3  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000bffa  mov     [rsp+0B10h+var_AD0], rax
0x18000bfff  xor     r12d, r12d
0x18000c002  mov     [rsp+0B10h+var_AC8], r12
0x18000c007  mov     [rsp+0B10h+var_AC0], r12
0x18000c00c  mov     [rsp+0B10h+var_AB8], r12d
0x18000c011  xorps   xmm0, xmm0
0x18000c014  xor     eax, eax
0x18000c016  movups  [rsp+0B10h+var_AB0], xmm0
0x18000c01b  movups  [rsp+0B10h+var_AA0], xmm0
0x18000c020  mov     [rbp+0A10h+var_A90], rax
0x18000c024  mov     [rbp+0A10h+var_A88], r12b
0x18000c028  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000c02d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18000c032  mov     edi, eax
0x18000c034  test    eax, eax
0x18000c036  jns     short loc_18000C065
0x18000c038  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c03d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c042  mov     eax, edi
0x18000c044  mov     rcx, [rbp+0A10h+var_40]
0x18000c04b  xor     rcx, rsp; StackCookie
0x18000c04e  call    __security_check_cookie
0x18000c053  add     rsp, 0AE0h
0x18000c05a  pop     r15
0x18000c05c  pop     r14
0x18000c05e  pop     r12
0x18000c060  pop     rdi
0x18000c061  pop     rsi
0x18000c062  pop     rbx
0x18000c063  pop     rbp
0x18000c064  retn
0x18000c065  test    rbx, rbx
0x18000c068  jz      short loc_18000C089
0x18000c06a  jmp     short loc_18000C081
0x18000c06c  mov     r8, [rbx+8]; unsigned __int16 *
0x18000c070  mov     rdx, rax; unsigned __int16 *
0x18000c073  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c078  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c07d  lea     rbx, [rbx+10h]
0x18000c081  mov     rax, [rbx]
0x18000c084  test    rax, rax
0x18000c087  jnz     short loc_18000C06C
0x18000c089  mov     rax, [rsi]
0x18000c08c  lea     rdx, [rsp+0B10h+var_AD0]
0x18000c091  mov     rcx, rsi
0x18000c094  mov     rax, [rax+28h]
0x18000c098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c09d  mov     ebx, eax
0x18000c09f  test    eax, eax
0x18000c0a1  js      loc_18000C1D5
0x18000c0a7  mov     [rsp+0B10h+var_AE0], r12
0x18000c0ac  mov     rbx, cs:hModule
0x18000c0b3  mov     edi, 104h
0x18000c0b8  mov     r8d, edi; nSize
0x18000c0bb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x18000c0bf  mov     rcx, rbx; hModule
0x18000c0c2  call    cs:__imp_GetModuleFileNameW
0x18000c0c8  test    eax, eax
0x18000c0ca  jnz     short loc_18000C0D8
0x18000c0cc  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c0d1  mov     ebx, eax
0x18000c0d3  jmp     loc_18000C1CB
0x18000c0d8  cmp     eax, edi
0x18000c0da  jnz     short loc_18000C0F0
0x18000c0dc  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c0e1  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c0e6  mov     ebx, 8007007Ah
0x18000c0eb  jmp     loc_18000C1D5
0x18000c0f0  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000c0f4  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c0fb  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18000c100  test    rbx, rbx
0x18000c103  jz      short loc_18000C11B
0x18000c105  xor     ecx, ecx; lpModuleName
0x18000c107  call    cs:__imp_GetModuleHandleW
0x18000c10d  cmp     rbx, rax
0x18000c110  jz      short loc_18000C11B
0x18000c112  lea     r8, [rbp+0A10h+var_450]
0x18000c119  jmp     short loc_18000C196
0x18000c11b  mov     ebx, 22h ; '"'
0x18000c120  mov     [rbp+0A10h+var_870], bx
0x18000c127  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c12e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x18000c135  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000c13a  test    al, al
0x18000c13c  jnz     short loc_18000C152
0x18000c13e  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c143  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c148  mov     ebx, 80004005h
0x18000c14d  jmp     loc_18000C1D5
0x18000c152  lea     rcx, [rbp+0A10h+var_870]
0x18000c159  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c15d  inc     rax
0x18000c160  cmp     [rcx+rax*2], r12w
0x18000c165  jnz     short loc_18000C15D
0x18000c167  cdqe
0x18000c169  mov     [rbp+rax*2+0A10h+var_870], bx
0x18000c171  lea     rcx, ds:2[rax*2]
0x18000c179  cmp     rcx, 418h
0x18000c180  jnb     loc_18000C226
0x18000c186  mov     [rbp+rcx+0A10h+var_870], r12w
0x18000c18f  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x18000c196  lea     rdx, aModule; "Module"
0x18000c19d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c1a2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c1a7  mov     ebx, eax
0x18000c1a9  test    eax, eax
0x18000c1ab  js      short loc_18000C1CB
0x18000c1ad  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000c1b4  lea     rdx, aModuleRaw; "Module_Raw"
0x18000c1bb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c1c0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000c1c5  mov     ebx, eax
0x18000c1c7  test    eax, eax
0x18000c1c9  jns     short loc_18000C1E6
0x18000c1cb  lea     rcx, [rsp+0B10h+var_AE0]
0x18000c1d0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c1d5  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c1da  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c1df  mov     eax, ebx
0x18000c1e1  jmp     loc_18000C044
0x18000c1e6  movzx   r8d, r15w; unsigned __int16 *
0x18000c1ea  mov     [rsp+0B10h+var_AD8], r12
0x18000c1ef  lea     r9, aRegistry; "REGISTRY"
0x18000c1f6  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000c1fa  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000c1ff  test    r14d, r14d
0x18000c202  jz      short loc_18000C20E
0x18000c204  mov     [rsp+0B10h+var_AF0], 1
0x18000c20c  jmp     short loc_18000C213
0x18000c20e  mov     [rsp+0B10h+var_AF0], r12d; int
0x18000c213  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000c218  mov     ebx, eax
0x18000c21a  lea     rcx, [rsp+0B10h+var_AD8]
0x18000c21f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c224  jmp     short loc_18000C1CB
0x18000c226  call    __report_rangecheckfailure
```
