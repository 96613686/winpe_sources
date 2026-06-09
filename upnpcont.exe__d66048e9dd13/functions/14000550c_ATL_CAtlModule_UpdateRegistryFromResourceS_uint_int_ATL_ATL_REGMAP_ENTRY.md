# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x14000550c`
- end: `0x14000582c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400054e0`
- `0x140005b80`

## callees

- `0x140001490`
- `0x1400014d0`
- `0x140001d8a`
- `0x140001ff4`
- `0x1400021e4`
- `0x140002a18`
- `0x14000380c`
- `0x140004698`
- `0x14000550c`
- `0x140006694`
- `0x140007010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400057b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400057b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005684`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005684`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140005611`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140005611`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400055c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000574f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000578d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400055c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000574f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000578d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400055ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000572a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000576b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400055ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005694`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000572a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000576b`

## string_xrefs

- `0x1400057cf`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  const unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // rdi
  signed int v11; // ebx
  HMODULE v12; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned __int16 v18; // r8
  unsigned __int16 *v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rax
  size_t v22; // r8
  unsigned __int64 v23; // rcx
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

  v28[0] = 0;
  v28[1] = 0;
  v27 = &ATL::CRegObject::`vftable';
  v29 = 0;
  v31 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v8 = ATL::CComCriticalSection::Init(&CriticalSection);
  if ( v8 >= 0 )
  {
    v31 = 1;
    if ( a4 )
    {
      while ( 1 )
      {
        v10 = *(const unsigned __int16 **)a4;
        if ( !*(_QWORD *)a4 )
          break;
        v9 = (const unsigned __int16 *)*((_QWORD *)a4 + 1);
        if ( v9 )
        {
          EnterCriticalSection(&CriticalSection);
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v27);
    if ( v11 < 0 )
      goto LABEL_34;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_33:
      v11 = Error;
      goto LABEL_34;
    }
    if ( ModuleFileNameW == 260 )
    {
      v11 = -2147024774;
    }
    else
    {
      v15 = Filename;
      v16 = 0;
      v17 = 39;
      do
      {
        v18 = *v15;
        if ( !*v15 )
          break;
        Src[v16] = v18;
        if ( v18 == 39 && (unsigned int)v16 < 0x206 )
        {
          LODWORD(v16) = v16 + 1;
          Src[(unsigned int)v16] = 39;
        }
        ++v15;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 0x207 );
      Src[v16] = 0;
      if ( !v12 || v12 == GetModuleHandleW(0) )
      {
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
            *(_DWORD *)_o__errno(Src, v15, v22, v17) = 34;
            invalid_parameter_noinfo();
            v11 = -2147467259;
            goto LABEL_34;
          }
          memcpy_0(v35, Src, v22);
        }
        do
          ++v20;
        while ( *(_WORD *)&v35[2 * v20 - 2] );
        v23 = 2LL * (int)v20 + 2;
        *(_WORD *)&v35[2 * (int)v20 - 2] = 34;
        if ( v23 >= 0x418 )
          _report_rangecheckfailure(v23, v15, v22, v17);
        *(_WORD *)&v35[v23 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v19 = &v34;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v19 = Src;
      }
      v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module", v19);
      LeaveCriticalSection(&CriticalSection);
      v11 = v24 == 0 ? 0x8007000E : 0;
      if ( v11 >= 0 )
      {
        EnterCriticalSection(&CriticalSection);
        v25 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module_Raw", Src);
        LeaveCriticalSection(&CriticalSection);
        Error = v25 == 0 ? 0x8007000E : 0;
        if ( v25 )
          Error = ATL::CRegObject::RegisterFromResource(
                    (const WCHAR *)&v27,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    a3 != 0);
        goto LABEL_33;
      }
    }
LABEL_34:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v11;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000550c  mov     [rsp-8+arg_10], rbx
0x140005511  push    rbp
0x140005512  push    rsi
0x140005513  push    rdi
0x140005514  push    r12
0x140005516  push    r13
0x140005518  push    r14
0x14000551a  push    r15
0x14000551c  lea     rbp, [rsp-9D0h]
0x140005524  sub     rsp, 0AD0h
0x14000552b  mov     rax, cs:__security_cookie
0x140005532  xor     rax, rsp
0x140005535  mov     [rbp+0A00h+var_40], rax
0x14000553c  xor     r13d, r13d
0x14000553f  mov     r12d, edx
0x140005542  xorps   xmm0, xmm0
0x140005545  mov     [rsp+0B00h+var_AC8], r13
0x14000554a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140005551  mov     [rsp+0B00h+var_AC0], r13
0x140005556  mov     [rsp+0B00h+var_AD0], rax
0x14000555b  mov     r14, rcx
0x14000555e  xor     eax, eax
0x140005560  mov     [rsp+0B00h+var_AB8], r13d
0x140005565  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x14000556a  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x14000556f  mov     rbx, r9
0x140005572  mov     [rsp+0B00h+var_A88], r13b
0x140005577  mov     r15d, r8d
0x14000557a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x14000557f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x140005584  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140005589  mov     edi, eax
0x14000558b  test    eax, eax
0x14000558d  js      loc_1400057F0
0x140005593  mov     [rsp+0B00h+var_A88], 1
0x140005598  test    rbx, rbx
0x14000559b  jz      short loc_1400055DA
0x14000559d  jmp     short loc_1400055D2
0x14000559f  mov     rsi, [rbx+8]
0x1400055a3  test    rsi, rsi
0x1400055a6  jz      short loc_1400055CE
0x1400055a8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400055ad  call    cs:__imp_EnterCriticalSection
0x1400055b3  mov     r8, rsi; unsigned __int16 *
0x1400055b6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1400055bb  mov     rdx, rdi; unsigned __int16 *
0x1400055be  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1400055c3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400055c8  call    cs:__imp_LeaveCriticalSection
0x1400055ce  add     rbx, 10h
0x1400055d2  mov     rdi, [rbx]
0x1400055d5  test    rdi, rdi
0x1400055d8  jnz     short loc_14000559F
0x1400055da  mov     rax, [r14]
0x1400055dd  lea     rdx, [rsp+0B00h+var_AD0]
0x1400055e2  mov     rcx, r14
0x1400055e5  mov     rax, [rax+28h]
0x1400055e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055ee  mov     ebx, eax
0x1400055f0  test    eax, eax
0x1400055f2  js      loc_1400057A3
0x1400055f8  mov     rbx, cs:hModule
0x1400055ff  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x140005606  mov     edi, 104h
0x14000560b  mov     rcx, rbx; hModule
0x14000560e  mov     r8d, edi; nSize
0x140005611  call    cs:__imp_GetModuleFileNameW
0x140005617  test    eax, eax
0x140005619  jnz     short loc_140005625
0x14000561b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140005620  jmp     loc_1400057A1
0x140005625  cmp     eax, edi
0x140005627  jnz     short loc_140005633
0x140005629  mov     ebx, 8007007Ah
0x14000562e  jmp     loc_1400057A3
0x140005633  lea     rdx, [rbp+0A00h+Filename]
0x14000563a  mov     ecx, r13d
0x14000563d  mov     r9d, 27h ; '''
0x140005643  movzx   r8d, word ptr [rdx]
0x140005647  test    r8w, r8w
0x14000564b  jz      short loc_140005677
0x14000564d  mov     [rbp+rcx*2+0A00h+Src], r8w
0x140005653  cmp     r8w, r9w
0x140005657  jnz     short loc_140005669
0x140005659  cmp     ecx, 206h
0x14000565f  jnb     short loc_140005669
0x140005661  inc     ecx
0x140005663  mov     [rbp+rcx*2+0A00h+Src], r9w
0x140005669  add     rdx, 2
0x14000566d  inc     ecx
0x14000566f  cmp     ecx, 207h
0x140005675  jb      short loc_140005643
0x140005677  mov     [rbp+rcx*2+0A00h+Src], r13w
0x14000567d  test    rbx, rbx
0x140005680  jz      short loc_1400056A3
0x140005682  xor     ecx, ecx; lpModuleName
0x140005684  call    cs:__imp_GetModuleHandleW
0x14000568a  cmp     rbx, rax
0x14000568d  jz      short loc_1400056A3
0x14000568f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140005694  call    cs:__imp_EnterCriticalSection
0x14000569a  lea     r8, [rbp+0A00h+Src]
0x14000569e  jmp     loc_140005737
0x1400056a3  mov     edi, 22h ; '"'
0x1400056a8  lea     rcx, [rbp+0A00h+Src]
0x1400056ac  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400056b0  mov     [rbp+0A00h+var_460], di
0x1400056b7  mov     rax, rbx
0x1400056ba  inc     rax
0x1400056bd  cmp     [rcx+rax*2], r13w
0x1400056c2  jnz     short loc_1400056BA
0x1400056c4  inc     eax
0x1400056c6  movsxd  r8, eax
0x1400056c9  add     r8, r8; Size
0x1400056cc  jz      short loc_1400056EB
0x1400056ce  cmp     r8, 414h
0x1400056d5  ja      loc_1400057B1
0x1400056db  lea     rdx, [rbp+0A00h+Src]; Src
0x1400056df  lea     rcx, [rbp+0A00h+var_45E]; void *
0x1400056e6  call    memcpy_0
0x1400056eb  lea     rax, [rbp+0A00h+var_460]
0x1400056f2  inc     rbx
0x1400056f5  cmp     [rax+rbx*2], r13w
0x1400056fa  jnz     short loc_1400056F2
0x1400056fc  movsxd  rax, ebx
0x1400056ff  lea     rcx, ds:2[rax*2]
0x140005707  mov     [rbp+rax*2+0A00h+var_460], di
0x14000570f  cmp     rcx, 418h
0x140005716  jnb     loc_140005826
0x14000571c  mov     [rbp+rcx+0A00h+var_460], r13w
0x140005725  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000572a  call    cs:__imp_EnterCriticalSection
0x140005730  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x140005737  lea     rdx, aModule; "Module"
0x14000573e  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140005743  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140005748  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000574d  mov     ebx, eax
0x14000574f  call    cs:__imp_LeaveCriticalSection
0x140005755  neg     ebx
0x140005757  mov     edi, 8007000Eh
0x14000575c  sbb     ebx, ebx
0x14000575e  not     ebx
0x140005760  and     ebx, edi
0x140005762  test    ebx, ebx
0x140005764  js      short loc_1400057A3
0x140005766  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000576b  call    cs:__imp_EnterCriticalSection
0x140005771  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x140005775  lea     rdx, aModuleRaw; "Module_Raw"
0x14000577c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140005781  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140005786  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000578b  mov     ebx, eax
0x14000578d  call    cs:__imp_LeaveCriticalSection
0x140005793  mov     ecx, ebx
0x140005795  neg     ecx
0x140005797  sbb     eax, eax
0x140005799  not     eax
0x14000579b  and     eax, edi
0x14000579d  test    ebx, ebx
0x14000579f  jnz     short loc_1400057C5
0x1400057a1  mov     ebx, eax
0x1400057a3  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1400057a8  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1400057ad  mov     eax, ebx
0x1400057af  jmp     short loc_1400057FC
0x1400057b1  call    cs:__imp__o__errno
0x1400057b7  mov     [rax], edi
0x1400057b9  call    _invalid_parameter_noinfo
0x1400057be  mov     ebx, 80004005h
0x1400057c3  jmp     short loc_1400057A3
0x1400057c5  mov     eax, r13d
0x1400057c8  movzx   r8d, r12w; unsigned __int16 *
0x1400057cc  test    r15d, r15d
0x1400057cf  lea     r9, aRegistry; "REGISTRY"
0x1400057d6  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1400057dd  setnz   al
0x1400057e0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1400057e5  mov     [rsp+0B00h+var_AE0], eax; int
0x1400057e9  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1400057ee  jmp     short loc_1400057A1
0x1400057f0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1400057f5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1400057fa  mov     eax, edi
0x1400057fc  mov     rcx, [rbp+0A00h+var_40]
0x140005803  xor     rcx, rsp; StackCookie
0x140005806  call    __security_check_cookie
0x14000580b  mov     rbx, [rsp+0B00h+arg_10]
0x140005813  add     rsp, 0AD0h
0x14000581a  pop     r15
0x14000581c  pop     r14
0x14000581e  pop     r13
0x140005820  pop     r12
0x140005822  pop     rdi
0x140005823  pop     rsi
0x140005824  pop     rbp
0x140005825  retn
0x140005826  call    __report_rangecheckfailure
```
