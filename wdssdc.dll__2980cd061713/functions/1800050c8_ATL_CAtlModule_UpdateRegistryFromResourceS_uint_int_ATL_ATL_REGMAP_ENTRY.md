# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800050c8`
- end: `0x1800053fc`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `820`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800050b0`
- `0x180008980`
- `0x180008ab0`

## callees

- `0x1800015b0`
- `0x1800016fc`
- `0x1800025fe`
- `0x180002718`
- `0x18000291c`
- `0x180002c10`
- `0x18000331c`
- `0x1800038ec`
- `0x1800043c0`
- `0x1800050c8`
- `0x18000cc10`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000537b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000537b`
- `KERNEL32!GetModuleHandleW` at `0x18000522e`
- `KERNEL32!GetModuleHandleW` at `0x18000522e`
- `KERNEL32!LeaveCriticalSection` at `0x180005307`
- `KERNEL32!LeaveCriticalSection` at `0x180005351`
- `KERNEL32!LeaveCriticalSection` at `0x180005307`
- `KERNEL32!LeaveCriticalSection` at `0x180005351`
- `KERNEL32!GetModuleFileNameW` at `0x1800051b3`
- `KERNEL32!GetModuleFileNameW` at `0x1800051b3`
- `KERNEL32!EnterCriticalSection` at `0x180005244`
- `KERNEL32!EnterCriticalSection` at `0x1800052dc`
- `KERNEL32!EnterCriticalSection` at `0x180005329`
- `KERNEL32!EnterCriticalSection` at `0x180005244`
- `KERNEL32!EnterCriticalSection` at `0x1800052dc`
- `KERNEL32!EnterCriticalSection` at `0x180005329`

## string_xrefs

- `0x18000539c`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v4; // r14
  int v5; // edi
  int v9; // esi
  signed int v10; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v14; // rdx
  unsigned int v15; // ecx
  __int64 v16; // r9
  unsigned __int16 v17; // r8
  unsigned __int16 *v18; // r8
  unsigned __int16 *v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rax
  size_t v22; // r8
  unsigned __int64 v23; // rax
  int v24; // ebx
  int v25; // ebx
  void **v27; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+48h] [rbp-B8h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v31; // [rsp+78h] [rbp-88h]
  unsigned __int16 Src[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v4 = ATL::_pAtlModule;
  v5 = 0;
  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v31 = 0;
  v9 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v9 >= 0 )
  {
    v31 = 1;
    if ( a4 )
    {
      while ( *(_QWORD *)a4 )
      {
        ATL::CRegObject::AddReplacement(
          (ATL::CRegObject *)&v27,
          *(const unsigned __int16 **)a4,
          *((const unsigned __int16 **)a4 + 1));
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v10 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v4 + 40LL))(v4, &v27);
    if ( v10 < 0 )
      goto LABEL_32;
    v11 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_31:
      v10 = Error;
      goto LABEL_32;
    }
    if ( ModuleFileNameW == 260 )
    {
      v10 = -2147024774;
    }
    else
    {
      v14 = Filename;
      v15 = 0;
      v16 = 39;
      do
      {
        v17 = *v14;
        if ( !*v14 )
          break;
        Src[v15] = v17;
        if ( v17 == 39 && v15 < 0x206 )
          Src[++v15] = 39;
        ++v14;
        ++v15;
      }
      while ( v15 < 0x207 );
      Src[v15] = 0;
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v19 = Src;
        v20 = -1;
        v34 = 34;
        v21 = -1;
        do
          ++v21;
        while ( Src[v21] );
        v22 = 2LL * ((int)v21 + 1);
        if ( v22 )
        {
          if ( v22 > 0x414 )
          {
            *(_DWORD *)_o__errno(Src, v14, v22, v16) = 34;
            invalid_parameter_noinfo();
            v10 = -2147467259;
            goto LABEL_32;
          }
          memcpy_0(v35, Src, v22);
        }
        do
          ++v20;
        while ( *(_WORD *)&v35[2 * v20 - 2] );
        *(_WORD *)&v35[2 * (int)v20 - 2] = 34;
        v23 = 2LL * (int)v20 + 2;
        if ( v23 >= 0x418 )
          _report_rangecheckfailure(v19, v14, v22, v16);
        *(_WORD *)&v35[v23 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v18 = &v34;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v18 = Src;
      }
      v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module", v18);
      LeaveCriticalSection(&CriticalSection);
      v10 = v24 == 0 ? 0x8007000E : 0;
      if ( v10 >= 0 )
      {
        EnterCriticalSection(&CriticalSection);
        v25 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module_Raw", Src);
        LeaveCriticalSection(&CriticalSection);
        Error = v25 == 0 ? 0x8007000E : 0;
        if ( v25 )
        {
          LOBYTE(v5) = a3 != 0;
          Error = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)&v27,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    v5);
        }
        goto LABEL_31;
      }
    }
LABEL_32:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v10;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800050c8  mov     [rsp-8+arg_0], rbx
0x1800050cd  mov     [rsp-8+arg_10], rsi
0x1800050d2  push    rbp
0x1800050d3  push    rdi
0x1800050d4  push    r12
0x1800050d6  push    r14
0x1800050d8  push    r15
0x1800050da  lea     rbp, [rsp-9D0h]
0x1800050e2  sub     rsp, 0AD0h
0x1800050e9  mov     rax, cs:__security_cookie
0x1800050f0  xor     rax, rsp
0x1800050f3  mov     [rbp+9F0h+var_30], rax
0x1800050fa  mov     r14, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005101  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005108  xor     edi, edi
0x18000510a  mov     [rsp+0AF0h+var_AC0], rax
0x18000510f  xorps   xmm0, xmm0
0x180005112  mov     r12d, edx
0x180005115  xor     eax, eax
0x180005117  mov     [rsp+0AF0h+var_AB8], rdi
0x18000511c  lea     rcx, [rsp+0AF0h+CriticalSection]; this
0x180005121  mov     [rsp+0AF0h+CriticalSection.SpinCount], rax
0x180005126  mov     rbx, r9
0x180005129  mov     [rsp+0AF0h+var_AB0], rdi
0x18000512e  mov     r15d, r8d
0x180005131  mov     [rsp+0AF0h+var_AA8], edi
0x180005135  movups  xmmword ptr [rsp+0AF0h+CriticalSection.DebugInfo], xmm0
0x18000513a  mov     [rsp+0AF0h+var_A78], dil
0x18000513f  movups  xmmword ptr [rsp+0AF0h+CriticalSection.OwningThread], xmm0
0x180005144  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005149  mov     esi, eax
0x18000514b  test    eax, eax
0x18000514d  js      loc_1800053BE
0x180005153  mov     [rsp+0AF0h+var_A78], 1
0x180005158  test    rbx, rbx
0x18000515b  jz      short loc_18000517C
0x18000515d  jmp     short loc_180005174
0x18000515f  mov     r8, [rbx+8]; unsigned __int16 *
0x180005163  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180005168  mov     rdx, rax; unsigned __int16 *
0x18000516b  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180005170  lea     rbx, [rbx+10h]
0x180005174  mov     rax, [rbx]
0x180005177  test    rax, rax
0x18000517a  jnz     short loc_18000515F
0x18000517c  mov     rax, [r14]
0x18000517f  lea     rdx, [rsp+0AF0h+var_AC0]
0x180005184  mov     rcx, r14
0x180005187  mov     rax, [rax+28h]
0x18000518b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005190  mov     ebx, eax
0x180005192  test    eax, eax
0x180005194  js      loc_18000536D
0x18000519a  mov     rbx, cs:hInstance
0x1800051a1  lea     rdx, [rbp+9F0h+Filename]; lpFilename
0x1800051a8  mov     esi, 104h
0x1800051ad  mov     rcx, rbx; hModule
0x1800051b0  mov     r8d, esi; nSize
0x1800051b3  call    cs:__imp_GetModuleFileNameW
0x1800051ba  nop     dword ptr [rax+rax+00h]
0x1800051bf  test    eax, eax
0x1800051c1  jnz     short loc_1800051CD
0x1800051c3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800051c8  jmp     loc_18000536B
0x1800051cd  cmp     eax, esi
0x1800051cf  jnz     short loc_1800051DB
0x1800051d1  mov     ebx, 8007007Ah
0x1800051d6  jmp     loc_18000536D
0x1800051db  lea     rdx, [rbp+9F0h+Filename]
0x1800051e2  mov     ecx, edi
0x1800051e4  mov     r9d, 27h ; '''
0x1800051ea  movzx   r8d, word ptr [rdx]
0x1800051ee  test    r8w, r8w
0x1800051f2  jz      short loc_180005220
0x1800051f4  mov     eax, ecx
0x1800051f6  mov     [rbp+rax*2+9F0h+Src], r8w
0x1800051fc  cmp     r8w, r9w
0x180005200  jnz     short loc_180005212
0x180005202  cmp     ecx, 206h
0x180005208  jnb     short loc_180005212
0x18000520a  inc     ecx
0x18000520c  mov     [rbp+rcx*2+9F0h+Src], r9w
0x180005212  add     rdx, 2
0x180005216  inc     ecx
0x180005218  cmp     ecx, 207h
0x18000521e  jb      short loc_1800051EA
0x180005220  mov     eax, ecx
0x180005222  mov     [rbp+rax*2+9F0h+Src], di
0x180005227  test    rbx, rbx
0x18000522a  jz      short loc_180005259
0x18000522c  xor     ecx, ecx; lpModuleName
0x18000522e  call    cs:__imp_GetModuleHandleW
0x180005235  nop     dword ptr [rax+rax+00h]
0x18000523a  cmp     rbx, rax
0x18000523d  jz      short loc_180005259
0x18000523f  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180005244  call    cs:__imp_EnterCriticalSection
0x18000524b  nop     dword ptr [rax+rax+00h]
0x180005250  lea     r8, [rbp+9F0h+Src]
0x180005254  jmp     loc_1800052EF
0x180005259  mov     esi, 22h ; '"'
0x18000525e  lea     rcx, [rbp+9F0h+Src]
0x180005262  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005266  mov     [rbp+9F0h+var_450], si
0x18000526d  mov     rax, rbx
0x180005270  inc     rax
0x180005273  cmp     [rcx+rax*2], di
0x180005277  jnz     short loc_180005270
0x180005279  inc     eax
0x18000527b  movsxd  r8, eax
0x18000527e  add     r8, r8; Size
0x180005281  jz      short loc_1800052A0
0x180005283  cmp     r8, 414h
0x18000528a  ja      loc_18000537B
0x180005290  lea     rdx, [rbp+9F0h+Src]; Src
0x180005294  lea     rcx, [rbp+9F0h+var_44E]; void *
0x18000529b  call    memcpy_0
0x1800052a0  lea     rax, [rbp+9F0h+var_450]
0x1800052a7  inc     rbx
0x1800052aa  cmp     [rax+rbx*2], di
0x1800052ae  jnz     short loc_1800052A7
0x1800052b0  movsxd  rax, ebx
0x1800052b3  mov     [rbp+rax*2+9F0h+var_450], si
0x1800052bb  lea     rax, ds:2[rax*2]
0x1800052c3  cmp     rax, 418h
0x1800052c9  jnb     loc_1800053F6
0x1800052cf  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x1800052d4  mov     [rbp+rax+9F0h+var_450], di
0x1800052dc  call    cs:__imp_EnterCriticalSection
0x1800052e3  nop     dword ptr [rax+rax+00h]
0x1800052e8  lea     r8, [rbp+9F0h+var_450]; unsigned __int16 *
0x1800052ef  lea     rdx, aModule; "Module"
0x1800052f6  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x1800052fb  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005300  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180005305  mov     ebx, eax
0x180005307  call    cs:__imp_LeaveCriticalSection
0x18000530e  nop     dword ptr [rax+rax+00h]
0x180005313  neg     ebx
0x180005315  mov     esi, 8007000Eh
0x18000531a  sbb     ebx, ebx
0x18000531c  not     ebx
0x18000531e  and     ebx, esi
0x180005320  test    ebx, ebx
0x180005322  js      short loc_18000536D
0x180005324  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x180005329  call    cs:__imp_EnterCriticalSection
0x180005330  nop     dword ptr [rax+rax+00h]
0x180005335  lea     r8, [rbp+9F0h+Src]; unsigned __int16 *
0x180005339  lea     rdx, aModuleRaw; "Module_Raw"
0x180005340  lea     rcx, [rsp+0AF0h+var_AB8]; this
0x180005345  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000534a  lea     rcx, [rsp+0AF0h+CriticalSection]; lpCriticalSection
0x18000534f  mov     ebx, eax
0x180005351  call    cs:__imp_LeaveCriticalSection
0x180005358  nop     dword ptr [rax+rax+00h]
0x18000535d  mov     ecx, ebx
0x18000535f  neg     ecx
0x180005361  sbb     eax, eax
0x180005363  not     eax
0x180005365  and     eax, esi
0x180005367  test    ebx, ebx
0x180005369  jnz     short loc_180005395
0x18000536b  mov     ebx, eax
0x18000536d  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x180005372  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005377  mov     eax, ebx
0x180005379  jmp     short loc_1800053CA
0x18000537b  call    cs:__imp__o__errno
0x180005382  nop     dword ptr [rax+rax+00h]
0x180005387  mov     [rax], esi
0x180005389  call    _invalid_parameter_noinfo
0x18000538e  mov     ebx, 80004005h
0x180005393  jmp     short loc_18000536D
0x180005395  test    r15d, r15d
0x180005398  movzx   r8d, r12w; unsigned __int16 *
0x18000539c  lea     r9, aRegistry; "REGISTRY"
0x1800053a3  setnz   dil
0x1800053a7  lea     rdx, [rbp+9F0h+Filename]; unsigned __int16 *
0x1800053ae  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x1800053b3  mov     [rsp+0AF0h+var_AD0], edi; int
0x1800053b7  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800053bc  jmp     short loc_18000536B
0x1800053be  lea     rcx, [rsp+0AF0h+var_AC0]; this
0x1800053c3  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800053c8  mov     eax, esi
0x1800053ca  mov     rcx, [rbp+9F0h+var_30]
0x1800053d1  xor     rcx, rsp; StackCookie
0x1800053d4  call    __security_check_cookie
0x1800053d9  lea     r11, [rsp+0AF0h+var_20]
0x1800053e1  mov     rbx, [r11+30h]
0x1800053e5  mov     rsi, [r11+40h]
0x1800053e9  mov     rsp, r11
0x1800053ec  pop     r15
0x1800053ee  pop     r14
0x1800053f0  pop     r12
0x1800053f2  pop     rdi
0x1800053f3  pop     rbp
0x1800053f4  retn
0x1800053f6  call    __report_rangecheckfailure
```
