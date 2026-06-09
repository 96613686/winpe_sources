# ATL::CAtlModule::UpdateRegistryFromResourceS(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800134f8`
- end: `0x1800137b4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `700`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const wchar_t *, int, const wchar_t **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800137d0`

## callees

- `0x1800020e0`
- `0x180002580`
- `0x180002ae2`
- `0x18000fdc8`
- `0x18001008c`
- `0x180010be8`
- `0x180012508`
- `0x1800134f8`
- `0x18001446c`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001374a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001374a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001362a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001362a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800135ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800135ae`

## string_xrefs

- `0x180013786`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const wchar_t *a2,
        int a3,
        const wchar_t **a4)
{
  const wchar_t **v4; // rbx
  const wchar_t *i; // rax
  const wchar_t *v9; // r8
  signed int v10; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  signed int Error; // eax
  WCHAR *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r9
  wchar_t v17; // r8
  wchar_t *v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rax
  size_t v21; // r8
  unsigned __int64 v22; // rcx
  int v23; // eax
  int v24; // eax
  void **v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+38h] [rbp-C8h] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Src[520]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t v31; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v32[1054]; // [rsp+682h] [rbp+582h] BYREF

  v4 = a4;
  v26 = &ATL::CRegObject::`vftable';
  v27 = 0;
  v28 = 0;
  if ( a4 )
  {
    for ( i = *a4; i; i = *v4 )
    {
      v9 = v4[1];
      if ( v9 )
        ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, i, v9);
      v4 += 2;
    }
  }
  v10 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v26);
  if ( v10 < 0 )
    goto LABEL_32;
  v11 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_10:
    v10 = Error;
LABEL_32:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v26);
    return (unsigned int)v10;
  }
  if ( ModuleFileNameW == 260 )
  {
    v10 = -2147024774;
    goto LABEL_32;
  }
  v14 = Filename;
  v15 = 0;
  v16 = 39;
  do
  {
    v17 = *v14;
    if ( !*v14 )
      break;
    Src[v15] = v17;
    if ( v17 == 39 && (unsigned int)v15 < 0x206 )
    {
      LODWORD(v15) = v15 + 1;
      Src[(unsigned int)v15] = 39;
    }
    ++v14;
    v15 = (unsigned int)(v15 + 1);
  }
  while ( (unsigned int)v15 < 0x207 );
  Src[v15] = 0;
  if ( v11 && v11 != GetModuleHandleW(0) )
  {
    v18 = Src;
    goto LABEL_30;
  }
  v31 = 34;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( Src[v20] );
  v21 = 2LL * ((int)v20 + 1);
  if ( !v21 )
  {
    do
LABEL_27:
      ++v19;
    while ( *(_WORD *)&v32[2 * v19 - 2] );
    *(_WORD *)&v32[2 * (int)v19 - 2] = 34;
    v22 = 2LL * (int)v19 + 2;
    if ( v22 >= 0x418 )
      _report_rangecheckfailure(v22, v14, v21, v16);
    *(_WORD *)&v32[v22 - 2] = 0;
    v18 = &v31;
LABEL_30:
    v23 = -ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module", v18);
    v10 = v23 == 0 ? 0x8007000E : 0;
    if ( !v23 )
      goto LABEL_32;
    v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module_Raw", Src);
    v10 = v24 == 0 ? 0x8007000E : 0;
    if ( !v24 )
      goto LABEL_32;
    if ( a3 )
    {
      if ( a2 )
      {
        Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v26, Filename, a2, L"REGISTRY", 1);
        goto LABEL_10;
      }
    }
    else if ( a2 )
    {
      Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v26, Filename, a2, L"REGISTRY", 0);
      goto LABEL_10;
    }
    v10 = -2147024809;
    goto LABEL_32;
  }
  if ( v21 <= 0x414 )
  {
    memcpy_0(v32, Src, v21);
    goto LABEL_27;
  }
  *(_DWORD *)_o__errno(Src, v14, v21) = 34;
  invalid_parameter_noinfo();
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v26);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800134f8  mov     [rsp-8+arg_10], rbx
0x1800134fd  push    rbp
0x1800134fe  push    rsi
0x1800134ff  push    rdi
0x180013500  push    r14
0x180013502  push    r15
0x180013504  lea     rbp, [rsp-9B0h]
0x18001350c  sub     rsp, 0AB0h
0x180013513  mov     rax, cs:__security_cookie
0x18001351a  xor     rax, rsp
0x18001351d  mov     [rbp+9D0h+var_30], rax
0x180013524  mov     rbx, r9
0x180013527  mov     r14d, r8d
0x18001352a  mov     rsi, rdx
0x18001352d  mov     rdi, rcx
0x180013530  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180013537  mov     [rsp+0AD0h+var_AA0], rax
0x18001353c  xorps   xmm0, xmm0
0x18001353f  movdqu  [rsp+0AD0h+var_A98], xmm0
0x180013545  xor     r15d, r15d
0x180013548  mov     [rsp+0AD0h+var_A88], r15d
0x18001354d  test    r9, r9
0x180013550  jz      short loc_180013579
0x180013552  mov     rax, [r9]
0x180013555  jmp     short loc_180013574
0x180013557  mov     r8, [rbx+8]; wchar_t *
0x18001355b  test    r8, r8
0x18001355e  jz      short loc_18001356D
0x180013560  mov     rdx, rax; wchar_t *
0x180013563  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180013568  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x18001356d  add     rbx, 10h
0x180013571  mov     rax, [rbx]
0x180013574  test    rax, rax
0x180013577  jnz     short loc_180013557
0x180013579  mov     rax, [rdi]
0x18001357c  lea     rdx, [rsp+0AD0h+var_AA0]
0x180013581  mov     rcx, rdi
0x180013584  mov     rax, [rax+28h]
0x180013588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001358d  mov     ebx, eax
0x18001358f  test    eax, eax
0x180013591  js      loc_180013718
0x180013597  mov     rbx, cs:hModule
0x18001359e  mov     edi, 104h
0x1800135a3  mov     r8d, edi; nSize
0x1800135a6  lea     rdx, [rsp+0AD0h+Filename]; lpFilename
0x1800135ab  mov     rcx, rbx; hModule
0x1800135ae  call    cs:__imp_GetModuleFileNameW
0x1800135b4  test    eax, eax
0x1800135b6  jnz     short loc_1800135C4
0x1800135b8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800135bd  mov     ebx, eax
0x1800135bf  jmp     loc_180013718
0x1800135c4  cmp     eax, edi
0x1800135c6  jnz     short loc_1800135D2
0x1800135c8  mov     ebx, 8007007Ah
0x1800135cd  jmp     loc_180013718
0x1800135d2  lea     rdx, [rsp+0AD0h+Filename]
0x1800135d7  mov     ecx, r15d
0x1800135da  mov     r9d, 27h ; '''
0x1800135e0  movzx   r8d, word ptr [rdx]
0x1800135e4  test    r8w, r8w
0x1800135e8  jz      short loc_18001361A
0x1800135ea  mov     [rbp+rcx*2+9D0h+Src], r8w
0x1800135f3  cmp     r8w, r9w
0x1800135f7  jnz     short loc_18001360C
0x1800135f9  cmp     ecx, 206h
0x1800135ff  jnb     short loc_18001360C
0x180013601  inc     ecx
0x180013603  mov     [rbp+rcx*2+9D0h+Src], r9w
0x18001360c  add     rdx, 2
0x180013610  inc     ecx
0x180013612  cmp     ecx, 207h
0x180013618  jb      short loc_1800135E0
0x18001361a  mov     [rbp+rcx*2+9D0h+Src], r15w
0x180013623  test    rbx, rbx
0x180013626  jz      short loc_180013641
0x180013628  xor     ecx, ecx; lpModuleName
0x18001362a  call    cs:__imp_GetModuleHandleW
0x180013630  cmp     rbx, rax
0x180013633  jz      short loc_180013641
0x180013635  lea     r8, [rbp+9D0h+Src]
0x18001363c  jmp     loc_1800136D0
0x180013641  mov     edi, 22h ; '"'
0x180013646  mov     [rbp+9D0h+var_450], di
0x18001364d  lea     rcx, [rbp+9D0h+Src]
0x180013654  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013658  mov     rax, rbx
0x18001365b  inc     rax
0x18001365e  cmp     [rcx+rax*2], r15w
0x180013663  jnz     short loc_18001365B
0x180013665  inc     eax
0x180013667  movsxd  r8, eax
0x18001366a  add     r8, r8; Size
0x18001366d  jz      short loc_18001368F
0x18001366f  cmp     r8, 414h
0x180013676  ja      loc_18001374A
0x18001367c  lea     rdx, [rbp+9D0h+Src]; Src
0x180013683  lea     rcx, [rbp+9D0h+var_44E]; void *
0x18001368a  call    memcpy_0
0x18001368f  lea     rax, [rbp+9D0h+var_450]
0x180013696  inc     rbx
0x180013699  cmp     [rax+rbx*2], r15w
0x18001369e  jnz     short loc_180013696
0x1800136a0  movsxd  rax, ebx
0x1800136a3  mov     [rbp+rax*2+9D0h+var_450], di
0x1800136ab  lea     rcx, ds:2[rax*2]
0x1800136b3  cmp     rcx, 418h
0x1800136ba  jnb     loc_1800137AE
0x1800136c0  mov     [rbp+rcx+9D0h+var_450], r15w
0x1800136c9  lea     r8, [rbp+9D0h+var_450]; wchar_t *
0x1800136d0  lea     rdx, aModule; "Module"
0x1800136d7  lea     rcx, [rsp+0AD0h+var_A98]; this
0x1800136dc  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x1800136e1  neg     eax
0x1800136e3  sbb     ebx, ebx
0x1800136e5  mov     edi, 8007000Eh
0x1800136ea  not     ebx
0x1800136ec  and     ebx, edi
0x1800136ee  test    ebx, ebx
0x1800136f0  js      short loc_180013718
0x1800136f2  lea     r8, [rbp+9D0h+Src]; wchar_t *
0x1800136f9  lea     rdx, aModuleRaw; "Module_Raw"
0x180013700  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180013705  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x18001370a  mov     ecx, eax
0x18001370c  neg     ecx
0x18001370e  sbb     ebx, ebx
0x180013710  not     ebx
0x180013712  and     ebx, edi
0x180013714  test    eax, eax
0x180013716  jnz     short loc_180013768
0x180013718  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x18001371d  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180013722  mov     eax, ebx
0x180013724  mov     rcx, [rbp+9D0h+var_30]
0x18001372b  xor     rcx, rsp; StackCookie
0x18001372e  call    __security_check_cookie
0x180013733  mov     rbx, [rsp+0AD0h+arg_10]
0x18001373b  add     rsp, 0AB0h
0x180013742  pop     r15
0x180013744  pop     r14
0x180013746  pop     rdi
0x180013747  pop     rsi
0x180013748  pop     rbp
0x180013749  retn
0x18001374a  call    cs:__imp__o__errno
0x180013750  mov     [rax], edi
0x180013752  call    _invalid_parameter_noinfo
0x180013757  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x18001375c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180013761  mov     eax, 80004005h
0x180013766  jmp     short loc_180013724
0x180013768  test    r14d, r14d
0x18001376b  jz      short loc_18001377C
0x18001376d  test    rsi, rsi
0x180013770  jz      short loc_1800137A4
0x180013772  mov     [rsp+0AD0h+var_AB0], 1
0x18001377a  jmp     short loc_180013786
0x18001377c  test    rsi, rsi
0x18001377f  jz      short loc_1800137A4
0x180013781  mov     [rsp+0AD0h+var_AB0], r15d; int
0x180013786  lea     r9, aRegistry; "REGISTRY"
0x18001378d  mov     r8, rsi; wchar_t *
0x180013790  lea     rdx, [rsp+0AD0h+Filename]; wchar_t *
0x180013795  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x18001379a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18001379f  jmp     loc_1800135BD
0x1800137a4  mov     ebx, 80070057h
0x1800137a9  jmp     loc_180013718
0x1800137ae  call    __report_rangecheckfailure
```
