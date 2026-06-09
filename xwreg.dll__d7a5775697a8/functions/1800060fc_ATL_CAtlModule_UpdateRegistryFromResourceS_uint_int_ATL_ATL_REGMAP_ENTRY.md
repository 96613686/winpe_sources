# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800060fc`
- end: `0x18000636c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006600`

## callees

- `0x180002238`
- `0x180002b1c`
- `0x180002dd8`
- `0x180003330`
- `0x180003b90`
- `0x180004718`
- `0x180004a90`
- `0x1800053f0`
- `0x1800060fc`
- `0x18000661c`
- `0x180012800`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006247`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006247`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006202`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180006202`

## string_xrefs

- `0x18000632f`: `REGISTRY`

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
0x1800060fc  push    rbp
0x1800060fe  push    rbx
0x1800060ff  push    rsi
0x180006100  push    rdi
0x180006101  push    r12
0x180006103  push    r14
0x180006105  push    r15
0x180006107  lea     rbp, [rsp-9E0h]
0x18000610f  sub     rsp, 0AE0h
0x180006116  mov     rax, cs:__security_cookie
0x18000611d  xor     rax, rsp
0x180006120  mov     [rbp+0A10h+var_40], rax
0x180006127  mov     rbx, r9
0x18000612a  mov     r14d, r8d
0x18000612d  mov     r15d, edx
0x180006130  mov     rsi, rcx
0x180006133  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000613a  mov     [rsp+0B10h+var_AD0], rax
0x18000613f  xor     r12d, r12d
0x180006142  mov     [rsp+0B10h+var_AC8], r12
0x180006147  mov     [rsp+0B10h+var_AC0], r12
0x18000614c  mov     [rsp+0B10h+var_AB8], r12d
0x180006151  xorps   xmm0, xmm0
0x180006154  xor     eax, eax
0x180006156  movups  [rsp+0B10h+var_AB0], xmm0
0x18000615b  movups  [rsp+0B10h+var_AA0], xmm0
0x180006160  mov     [rbp+0A10h+var_A90], rax
0x180006164  mov     [rbp+0A10h+var_A88], r12b
0x180006168  lea     rcx, [rsp+0B10h+var_AB0]; this
0x18000616d  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180006172  mov     edi, eax
0x180006174  test    eax, eax
0x180006176  jns     short loc_1800061A5
0x180006178  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000617d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006182  mov     eax, edi
0x180006184  mov     rcx, [rbp+0A10h+var_40]
0x18000618b  xor     rcx, rsp; StackCookie
0x18000618e  call    __security_check_cookie
0x180006193  add     rsp, 0AE0h
0x18000619a  pop     r15
0x18000619c  pop     r14
0x18000619e  pop     r12
0x1800061a0  pop     rdi
0x1800061a1  pop     rsi
0x1800061a2  pop     rbx
0x1800061a3  pop     rbp
0x1800061a4  retn
0x1800061a5  test    rbx, rbx
0x1800061a8  jz      short loc_1800061C9
0x1800061aa  jmp     short loc_1800061C1
0x1800061ac  mov     r8, [rbx+8]; unsigned __int16 *
0x1800061b0  mov     rdx, rax; unsigned __int16 *
0x1800061b3  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800061b8  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800061bd  lea     rbx, [rbx+10h]
0x1800061c1  mov     rax, [rbx]
0x1800061c4  test    rax, rax
0x1800061c7  jnz     short loc_1800061AC
0x1800061c9  mov     rax, [rsi]
0x1800061cc  lea     rdx, [rsp+0B10h+var_AD0]
0x1800061d1  mov     rcx, rsi
0x1800061d4  mov     rax, [rax+28h]
0x1800061d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061dd  mov     ebx, eax
0x1800061df  test    eax, eax
0x1800061e1  js      loc_180006315
0x1800061e7  mov     [rsp+0B10h+var_AE0], r12
0x1800061ec  mov     rbx, cs:hModule
0x1800061f3  mov     edi, 104h
0x1800061f8  mov     r8d, edi; nSize
0x1800061fb  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x1800061ff  mov     rcx, rbx; hModule
0x180006202  call    cs:__imp_GetModuleFileNameW
0x180006208  test    eax, eax
0x18000620a  jnz     short loc_180006218
0x18000620c  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180006211  mov     ebx, eax
0x180006213  jmp     loc_18000630B
0x180006218  cmp     eax, edi
0x18000621a  jnz     short loc_180006230
0x18000621c  lea     rcx, [rsp+0B10h+var_AE0]
0x180006221  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006226  mov     ebx, 8007007Ah
0x18000622b  jmp     loc_180006315
0x180006230  lea     r8, [rbp+0A10h+Filename]; unsigned __int16 *
0x180006234  lea     rcx, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000623b  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x180006240  test    rbx, rbx
0x180006243  jz      short loc_18000625B
0x180006245  xor     ecx, ecx; lpModuleName
0x180006247  call    cs:__imp_GetModuleHandleW
0x18000624d  cmp     rbx, rax
0x180006250  jz      short loc_18000625B
0x180006252  lea     r8, [rbp+0A10h+var_450]
0x180006259  jmp     short loc_1800062D6
0x18000625b  mov     ebx, 22h ; '"'
0x180006260  mov     [rbp+0A10h+var_870], bx
0x180006267  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x18000626e  lea     rcx, [rbp+0A10h+var_86E]; unsigned __int16 *
0x180006275  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18000627a  test    al, al
0x18000627c  jnz     short loc_180006292
0x18000627e  lea     rcx, [rsp+0B10h+var_AE0]
0x180006283  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006288  mov     ebx, 80004005h
0x18000628d  jmp     loc_180006315
0x180006292  lea     rcx, [rbp+0A10h+var_870]
0x180006299  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000629d  inc     rax
0x1800062a0  cmp     [rcx+rax*2], r12w
0x1800062a5  jnz     short loc_18000629D
0x1800062a7  cdqe
0x1800062a9  mov     [rbp+rax*2+0A10h+var_870], bx
0x1800062b1  lea     rcx, ds:2[rax*2]
0x1800062b9  cmp     rcx, 418h
0x1800062c0  jnb     loc_180006366
0x1800062c6  mov     [rbp+rcx+0A10h+var_870], r12w
0x1800062cf  lea     r8, [rbp+0A10h+var_870]; unsigned __int16 *
0x1800062d6  lea     rdx, aModule; "Module"
0x1800062dd  lea     rcx, [rsp+0B10h+var_AD0]; this
0x1800062e2  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x1800062e7  mov     ebx, eax
0x1800062e9  test    eax, eax
0x1800062eb  js      short loc_18000630B
0x1800062ed  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800062f4  lea     rdx, aModuleRaw; "Module_Raw"
0x1800062fb  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180006300  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180006305  mov     ebx, eax
0x180006307  test    eax, eax
0x180006309  jns     short loc_180006326
0x18000630b  lea     rcx, [rsp+0B10h+var_AE0]
0x180006310  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006315  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000631a  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000631f  mov     eax, ebx
0x180006321  jmp     loc_180006184
0x180006326  movzx   r8d, r15w; unsigned __int16 *
0x18000632a  mov     [rsp+0B10h+var_AD8], r12
0x18000632f  lea     r9, aRegistry; "REGISTRY"
0x180006336  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x18000633a  lea     rcx, [rsp+0B10h+var_AD0]; this
0x18000633f  test    r14d, r14d
0x180006342  jz      short loc_18000634E
0x180006344  mov     [rsp+0B10h+var_AF0], 1
0x18000634c  jmp     short loc_180006353
0x18000634e  mov     [rsp+0B10h+var_AF0], r12d; int
0x180006353  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180006358  mov     ebx, eax
0x18000635a  lea     rcx, [rsp+0B10h+var_AD8]
0x18000635f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006364  jmp     short loc_18000630B
0x180006366  call    __report_rangecheckfailure
```
