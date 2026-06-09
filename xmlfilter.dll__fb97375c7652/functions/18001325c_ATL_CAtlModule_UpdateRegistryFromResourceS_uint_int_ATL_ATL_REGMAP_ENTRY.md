# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001325c`
- end: `0x1800134f2`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `662`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, const wchar_t **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180013240`
- `0x1800137c0`

## callees

- `0x1800020e0`
- `0x180002580`
- `0x180002ae2`
- `0x18000fdc8`
- `0x18001008c`
- `0x180010be8`
- `0x180012508`
- `0x18001325c`
- `0x18001446c`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800134a1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800134a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013389`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013389`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180013314`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180013314`

## string_xrefs

- `0x1800134cf`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
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
  wchar_t Src[520]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+470h] [rbp+370h] BYREF
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
LABEL_30:
    v23 = -ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module", v18);
    v10 = v23 == 0 ? 0x8007000E : 0;
    if ( !v23 )
      goto LABEL_32;
    v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)&v27, L"Module_Raw", Src);
    v10 = v24 == 0 ? 0x8007000E : 0;
    if ( !v24 )
      goto LABEL_32;
    Error = ATL::CRegObject::RegisterFromResource(
              (ATL::CRegObject *)&v26,
              Filename,
              (const wchar_t *)a2,
              L"REGISTRY",
              a3 != 0);
    goto LABEL_10;
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
    goto LABEL_30;
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
0x18001325c  mov     [rsp-8+arg_10], rbx
0x180013261  push    rbp
0x180013262  push    rsi
0x180013263  push    rdi
0x180013264  push    r14
0x180013266  push    r15
0x180013268  lea     rbp, [rsp-9B0h]
0x180013270  sub     rsp, 0AB0h
0x180013277  mov     rax, cs:__security_cookie
0x18001327e  xor     rax, rsp
0x180013281  mov     [rbp+9D0h+var_30], rax
0x180013288  mov     rbx, r9
0x18001328b  mov     esi, r8d
0x18001328e  mov     r14d, edx
0x180013291  mov     rdi, rcx
0x180013294  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001329b  mov     [rsp+0AD0h+var_AA0], rax
0x1800132a0  xorps   xmm0, xmm0
0x1800132a3  movdqu  [rsp+0AD0h+var_A98], xmm0
0x1800132a9  xor     r15d, r15d
0x1800132ac  mov     [rsp+0AD0h+var_A88], r15d
0x1800132b1  test    r9, r9
0x1800132b4  jz      short loc_1800132DD
0x1800132b6  mov     rax, [r9]
0x1800132b9  jmp     short loc_1800132D8
0x1800132bb  mov     r8, [rbx+8]; wchar_t *
0x1800132bf  test    r8, r8
0x1800132c2  jz      short loc_1800132D1
0x1800132c4  mov     rdx, rax; wchar_t *
0x1800132c7  lea     rcx, [rsp+0AD0h+var_A98]; this
0x1800132cc  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x1800132d1  add     rbx, 10h
0x1800132d5  mov     rax, [rbx]
0x1800132d8  test    rax, rax
0x1800132db  jnz     short loc_1800132BB
0x1800132dd  mov     rax, [rdi]
0x1800132e0  lea     rdx, [rsp+0AD0h+var_AA0]
0x1800132e5  mov     rcx, rdi
0x1800132e8  mov     rax, [rax+28h]
0x1800132ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132f1  mov     ebx, eax
0x1800132f3  test    eax, eax
0x1800132f5  js      loc_18001346F
0x1800132fb  mov     rbx, cs:hModule
0x180013302  mov     edi, 104h
0x180013307  mov     r8d, edi; nSize
0x18001330a  lea     rdx, [rbp+9D0h+Filename]; lpFilename
0x180013311  mov     rcx, rbx; hModule
0x180013314  call    cs:__imp_GetModuleFileNameW
0x18001331a  test    eax, eax
0x18001331c  jnz     short loc_18001332A
0x18001331e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180013323  mov     ebx, eax
0x180013325  jmp     loc_18001346F
0x18001332a  cmp     eax, edi
0x18001332c  jnz     short loc_180013338
0x18001332e  mov     ebx, 8007007Ah
0x180013333  jmp     loc_18001346F
0x180013338  lea     rdx, [rbp+9D0h+Filename]
0x18001333f  mov     ecx, r15d
0x180013342  mov     r9d, 27h ; '''
0x180013348  movzx   r8d, word ptr [rdx]
0x18001334c  test    r8w, r8w
0x180013350  jz      short loc_18001337C
0x180013352  mov     [rsp+rcx*2+0AD0h+Src], r8w
0x180013358  cmp     r8w, r9w
0x18001335c  jnz     short loc_18001336E
0x18001335e  cmp     ecx, 206h
0x180013364  jnb     short loc_18001336E
0x180013366  inc     ecx
0x180013368  mov     [rsp+rcx*2+0AD0h+Src], r9w
0x18001336e  add     rdx, 2
0x180013372  inc     ecx
0x180013374  cmp     ecx, 207h
0x18001337a  jb      short loc_180013348
0x18001337c  mov     [rsp+rcx*2+0AD0h+Src], r15w
0x180013382  test    rbx, rbx
0x180013385  jz      short loc_18001339E
0x180013387  xor     ecx, ecx; lpModuleName
0x180013389  call    cs:__imp_GetModuleHandleW
0x18001338f  cmp     rbx, rax
0x180013392  jz      short loc_18001339E
0x180013394  lea     r8, [rsp+0AD0h+Src]
0x180013399  jmp     loc_180013429
0x18001339e  mov     edi, 22h ; '"'
0x1800133a3  mov     [rbp+9D0h+var_450], di
0x1800133aa  lea     rcx, [rsp+0AD0h+Src]
0x1800133af  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800133b3  mov     rax, rbx
0x1800133b6  inc     rax
0x1800133b9  cmp     [rcx+rax*2], r15w
0x1800133be  jnz     short loc_1800133B6
0x1800133c0  inc     eax
0x1800133c2  movsxd  r8, eax
0x1800133c5  add     r8, r8; Size
0x1800133c8  jz      short loc_1800133E8
0x1800133ca  cmp     r8, 414h
0x1800133d1  ja      loc_1800134A1
0x1800133d7  lea     rdx, [rsp+0AD0h+Src]; Src
0x1800133dc  lea     rcx, [rbp+9D0h+var_44E]; void *
0x1800133e3  call    memcpy_0
0x1800133e8  lea     rax, [rbp+9D0h+var_450]
0x1800133ef  inc     rbx
0x1800133f2  cmp     [rax+rbx*2], r15w
0x1800133f7  jnz     short loc_1800133EF
0x1800133f9  movsxd  rax, ebx
0x1800133fc  mov     [rbp+rax*2+9D0h+var_450], di
0x180013404  lea     rcx, ds:2[rax*2]
0x18001340c  cmp     rcx, 418h
0x180013413  jnb     loc_1800134EC
0x180013419  mov     [rbp+rcx+9D0h+var_450], r15w
0x180013422  lea     r8, [rbp+9D0h+var_450]; wchar_t *
0x180013429  lea     rdx, aModule; "Module"
0x180013430  lea     rcx, [rsp+0AD0h+var_A98]; this
0x180013435  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x18001343a  neg     eax
0x18001343c  sbb     ebx, ebx
0x18001343e  mov     edi, 8007000Eh
0x180013443  not     ebx
0x180013445  and     ebx, edi
0x180013447  test    ebx, ebx
0x180013449  js      short loc_18001346F
0x18001344b  lea     r8, [rsp+0AD0h+Src]; wchar_t *
0x180013450  lea     rdx, aModuleRaw; "Module_Raw"
0x180013457  lea     rcx, [rsp+0AD0h+var_A98]; this
0x18001345c  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180013461  mov     ecx, eax
0x180013463  neg     ecx
0x180013465  sbb     ebx, ebx
0x180013467  not     ebx
0x180013469  and     ebx, edi
0x18001346b  test    eax, eax
0x18001346d  jnz     short loc_1800134BF
0x18001346f  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x180013474  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180013479  mov     eax, ebx
0x18001347b  mov     rcx, [rbp+9D0h+var_30]
0x180013482  xor     rcx, rsp; StackCookie
0x180013485  call    __security_check_cookie
0x18001348a  mov     rbx, [rsp+0AD0h+arg_10]
0x180013492  add     rsp, 0AB0h
0x180013499  pop     r15
0x18001349b  pop     r14
0x18001349d  pop     rdi
0x18001349e  pop     rsi
0x18001349f  pop     rbp
0x1800134a0  retn
0x1800134a1  call    cs:__imp__o__errno
0x1800134a7  mov     [rax], edi
0x1800134a9  call    _invalid_parameter_noinfo
0x1800134ae  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x1800134b3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800134b8  mov     eax, 80004005h
0x1800134bd  jmp     short loc_18001347B
0x1800134bf  mov     eax, r15d
0x1800134c2  test    esi, esi
0x1800134c4  setnz   al
0x1800134c7  movzx   r8d, r14w; wchar_t *
0x1800134cb  mov     [rsp+0AD0h+var_AB0], eax; int
0x1800134cf  lea     r9, aRegistry; "REGISTRY"
0x1800134d6  lea     rdx, [rbp+9D0h+Filename]; wchar_t *
0x1800134dd  lea     rcx, [rsp+0AD0h+var_AA0]; this
0x1800134e2  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x1800134e7  jmp     loc_180013323
0x1800134ec  call    __report_rangecheckfailure
```
