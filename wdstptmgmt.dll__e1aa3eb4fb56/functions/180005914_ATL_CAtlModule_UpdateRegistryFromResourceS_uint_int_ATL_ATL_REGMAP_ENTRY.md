# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180005914`
- end: `0x180005c20`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `780`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800058d0`
- `0x180008830`

## callees

- `0x180002454`
- `0x180002ae8`
- `0x180002c34`
- `0x180002fb0`
- `0x1800037f8`
- `0x18000452c`
- `0x180004c9c`
- `0x180005914`
- `0x18001e9f0`
- `0x180020010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180005af4`
- `msvcrt!memcpy_s` at `0x180005af4`
- `KERNEL32!GetModuleHandleW` at `0x180005a98`
- `KERNEL32!GetModuleHandleW` at `0x180005a98`
- `KERNEL32!GetModuleFileNameW` at `0x180005a09`
- `KERNEL32!GetModuleFileNameW` at `0x180005a09`

## string_xrefs

- `0x180005b9e`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v7; // rsi
  int v8; // edi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v13; // rdx
  unsigned int i; // ecx
  unsigned __int16 v15; // r8
  unsigned __int16 *v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rax
  unsigned __int64 v19; // rax
  int v20; // eax
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  _OWORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+80h] [rbp-80h]
  char v27; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 Source[520]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v30; // [rsp+6B0h] [rbp+5B0h] BYREF
  _BYTE Destination[1054]; // [rsp+6B2h] [rbp+5B2h] BYREF

  v7 = ATL::_pAtlModule;
  v23[0] = &ATL::CRegObject::`vftable';
  v23[1] = 0;
  v23[2] = 0;
  v24 = 0;
  memset(v25, 0, sizeof(v25));
  v26 = 0;
  v27 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v25);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v23,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, _QWORD *))(*(_QWORD *)v7 + 40LL))(v7, v23);
  if ( Error < 0 )
    goto LABEL_30;
  v21 = 0;
  v11 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_29:
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    goto LABEL_30;
  }
  if ( ModuleFileNameW == 260 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
    Error = -2147024774;
LABEL_30:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
    return (unsigned int)Error;
  }
  v13 = Filename;
  for ( i = 0; i < 0x207; ++i )
  {
    v15 = *v13;
    if ( !*v13 )
      break;
    Source[i] = v15;
    if ( v15 == 39 && i < 0x206 )
      Source[++i] = 39;
    ++v13;
  }
  Source[i] = 0;
  if ( v11 && v11 != GetModuleHandleW(0) )
  {
    v16 = Source;
LABEL_27:
    Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v23, L"Module", v16);
    if ( Error >= 0 )
    {
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v23, L"Module_Raw", Source);
      if ( Error >= 0 )
      {
        v22 = 0;
        if ( a3 )
          v20 = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)v23,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  1);
        else
          v20 = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)v23,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  0);
        Error = v20;
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v22);
      }
    }
    goto LABEL_29;
  }
  v30 = 34;
  v17 = -1;
  v18 = -1;
  do
    ++v18;
  while ( Source[v18] );
  if ( !memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v18 + 1)) )
  {
    do
      ++v17;
    while ( *(_WORD *)&Destination[2 * v17 - 2] );
    *(_WORD *)&Destination[2 * (int)v17 - 2] = 34;
    v19 = 2LL * (int)v17 + 2;
    if ( v19 >= 0x418 )
      _report_rangecheckfailure();
    *(_WORD *)&Destination[v19 - 2] = 0;
    v16 = &v30;
    goto LABEL_27;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v21);
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v23);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180005914  mov     [rsp-8+arg_0], rbx
0x180005919  mov     [rsp-8+arg_10], rsi
0x18000591e  push    rbp
0x18000591f  push    rdi
0x180005920  push    r12
0x180005922  push    r14
0x180005924  push    r15
0x180005926  lea     rbp, [rsp-9E0h]
0x18000592e  sub     rsp, 0AE0h
0x180005935  mov     rax, cs:__security_cookie
0x18000593c  xor     rax, rsp
0x18000593f  mov     [rbp+0A00h+var_30], rax
0x180005946  mov     rbx, r9
0x180005949  mov     r14d, r8d
0x18000594c  mov     r15d, edx
0x18000594f  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005956  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000595d  mov     [rsp+0B00h+var_AC0], rax
0x180005962  xor     r12d, r12d
0x180005965  mov     [rsp+0B00h+var_AB8], r12
0x18000596a  mov     [rsp+0B00h+var_AB0], r12
0x18000596f  mov     [rsp+0B00h+var_AA8], r12d
0x180005974  xorps   xmm0, xmm0
0x180005977  xor     eax, eax
0x180005979  movups  [rsp+0B00h+var_AA0], xmm0
0x18000597e  movups  [rsp+0B00h+var_A90], xmm0
0x180005983  mov     [rbp+0A00h+var_A80], rax
0x180005987  mov     [rbp+0A00h+var_A78], r12b
0x18000598b  lea     rcx, [rsp+0B00h+var_AA0]; this
0x180005990  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180005995  mov     edi, eax
0x180005997  test    eax, eax
0x180005999  jns     short loc_1800059AC
0x18000599b  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800059a0  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800059a5  mov     eax, edi
0x1800059a7  jmp     loc_180005BF4
0x1800059ac  test    rbx, rbx
0x1800059af  jz      short loc_1800059D0
0x1800059b1  jmp     short loc_1800059C8
0x1800059b3  mov     r8, [rbx+8]; unsigned __int16 *
0x1800059b7  mov     rdx, rax; unsigned __int16 *
0x1800059ba  lea     rcx, [rsp+0B00h+var_AC0]; this
0x1800059bf  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800059c4  lea     rbx, [rbx+10h]
0x1800059c8  mov     rax, [rbx]
0x1800059cb  test    rax, rax
0x1800059ce  jnz     short loc_1800059B3
0x1800059d0  mov     rax, [rsi]
0x1800059d3  lea     rdx, [rsp+0B00h+var_AC0]
0x1800059d8  mov     rcx, rsi
0x1800059db  mov     rax, [rax+28h]
0x1800059df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e4  mov     ebx, eax
0x1800059e6  test    eax, eax
0x1800059e8  js      loc_180005B87
0x1800059ee  mov     [rsp+0B00h+var_AD0], r12
0x1800059f3  mov     rbx, cs:hModule
0x1800059fa  mov     edi, 104h
0x1800059ff  mov     r8d, edi; nSize
0x180005a02  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180005a06  mov     rcx, rbx; hModule
0x180005a09  call    cs:__imp_GetModuleFileNameW
0x180005a10  nop     dword ptr [rax+rax+00h]
0x180005a15  test    eax, eax
0x180005a17  jnz     short loc_180005A25
0x180005a19  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005a1e  mov     ebx, eax
0x180005a20  jmp     loc_180005B7D
0x180005a25  cmp     eax, edi
0x180005a27  jnz     short loc_180005A3D
0x180005a29  lea     rcx, [rsp+0B00h+var_AD0]
0x180005a2e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005a33  mov     ebx, 8007007Ah
0x180005a38  jmp     loc_180005B87
0x180005a3d  lea     rdx, [rbp+0A00h+Filename]
0x180005a41  mov     ecx, r12d
0x180005a44  mov     r9d, 27h ; '''
0x180005a4a  movzx   r8d, word ptr [rdx]
0x180005a4e  test    r8w, r8w
0x180005a52  jz      short loc_180005A86
0x180005a54  mov     eax, ecx
0x180005a56  mov     [rbp+rax*2+0A00h+Source], r8w
0x180005a5f  cmp     r8w, r9w
0x180005a63  jnz     short loc_180005A78
0x180005a65  cmp     ecx, 206h
0x180005a6b  jnb     short loc_180005A78
0x180005a6d  inc     ecx
0x180005a6f  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180005a78  add     rdx, 2
0x180005a7c  inc     ecx
0x180005a7e  cmp     ecx, 207h
0x180005a84  jb      short loc_180005A4A
0x180005a86  mov     eax, ecx
0x180005a88  mov     [rbp+rax*2+0A00h+Source], r12w
0x180005a91  test    rbx, rbx
0x180005a94  jz      short loc_180005AB5
0x180005a96  xor     ecx, ecx; lpModuleName
0x180005a98  call    cs:__imp_GetModuleHandleW
0x180005a9f  nop     dword ptr [rax+rax+00h]
0x180005aa4  cmp     rbx, rax
0x180005aa7  jz      short loc_180005AB5
0x180005aa9  lea     r8, [rbp+0A00h+Source]
0x180005ab0  jmp     loc_180005B48
0x180005ab5  mov     edi, 22h ; '"'
0x180005aba  mov     [rbp+0A00h+var_450], di
0x180005ac1  lea     rcx, [rbp+0A00h+Source]
0x180005ac8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005acc  mov     rax, rbx
0x180005acf  inc     rax
0x180005ad2  cmp     [rcx+rax*2], r12w
0x180005ad7  jnz     short loc_180005ACF
0x180005ad9  inc     eax
0x180005adb  movsxd  r9, eax
0x180005ade  add     r9, r9; SourceSize
0x180005ae1  lea     r8, [rbp+0A00h+Source]; Source
0x180005ae8  mov     edx, 414h; DestinationSize
0x180005aed  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180005af4  call    cs:__imp_memcpy_s
0x180005afb  nop     dword ptr [rax+rax+00h]
0x180005b00  test    eax, eax
0x180005b02  jnz     loc_180005BDB
0x180005b08  lea     rax, [rbp+0A00h+var_450]
0x180005b0f  inc     rbx
0x180005b12  cmp     [rax+rbx*2], r12w
0x180005b17  jnz     short loc_180005B0F
0x180005b19  movsxd  rax, ebx
0x180005b1c  mov     [rbp+rax*2+0A00h+var_450], di
0x180005b24  lea     rax, ds:2[rax*2]
0x180005b2c  cmp     rax, 418h
0x180005b32  jnb     loc_180005BD5
0x180005b38  mov     [rbp+rax+0A00h+var_450], r12w
0x180005b41  lea     r8, [rbp+0A00h+var_450]; unsigned __int16 *
0x180005b48  lea     rdx, aModule; "Module"
0x180005b4f  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180005b54  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180005b59  mov     ebx, eax
0x180005b5b  test    eax, eax
0x180005b5d  js      short loc_180005B7D
0x180005b5f  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180005b66  lea     rdx, aModuleRaw; "Module_Raw"
0x180005b6d  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180005b72  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180005b77  mov     ebx, eax
0x180005b79  test    eax, eax
0x180005b7b  jns     short loc_180005B95
0x180005b7d  lea     rcx, [rsp+0B00h+var_AD0]
0x180005b82  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005b87  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180005b8c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005b91  mov     eax, ebx
0x180005b93  jmp     short loc_180005BF4
0x180005b95  movzx   r8d, r15w; unsigned __int16 *
0x180005b99  mov     [rsp+0B00h+var_AC8], r12
0x180005b9e  lea     r9, aRegistry; "REGISTRY"
0x180005ba5  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180005ba9  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180005bae  test    r14d, r14d
0x180005bb1  jz      short loc_180005BBD
0x180005bb3  mov     [rsp+0B00h+var_AE0], 1
0x180005bbb  jmp     short loc_180005BC2
0x180005bbd  mov     [rsp+0B00h+var_AE0], r12d; int
0x180005bc2  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180005bc7  mov     ebx, eax
0x180005bc9  lea     rcx, [rsp+0B00h+var_AC8]
0x180005bce  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005bd3  jmp     short loc_180005B7D
0x180005bd5  call    __report_rangecheckfailure
0x180005bdb  lea     rcx, [rsp+0B00h+var_AD0]
0x180005be0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005be5  lea     rcx, [rsp+0B00h+var_AC0]; this
0x180005bea  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005bef  mov     eax, 80004005h
0x180005bf4  mov     rcx, [rbp+0A00h+var_30]
0x180005bfb  xor     rcx, rsp; StackCookie
0x180005bfe  call    __security_check_cookie
0x180005c03  lea     r11, [rsp+0B00h+var_20]
0x180005c0b  mov     rbx, [r11+30h]
0x180005c0f  mov     rsi, [r11+40h]
0x180005c13  mov     rsp, r11
0x180005c16  pop     r15
0x180005c18  pop     r14
0x180005c1a  pop     r12
0x180005c1c  pop     rdi
0x180005c1d  pop     rbp
0x180005c1e  retn
```
