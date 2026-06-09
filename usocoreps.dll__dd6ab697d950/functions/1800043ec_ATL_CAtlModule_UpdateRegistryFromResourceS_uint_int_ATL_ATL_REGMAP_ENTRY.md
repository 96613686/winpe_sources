# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800043ec`
- end: `0x18000470c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004a60`

## callees

- `0x180001510`
- `0x180001550`
- `0x1800020ca`
- `0x180002338`
- `0x18000246c`
- `0x180002ef4`
- `0x1800031ac`
- `0x180003978`
- `0x1800043ec`
- `0x180004ea0`
- `0x180006010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004691`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004691`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800044f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800044f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004564`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004564`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000448d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004574`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000460a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000464b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000448d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004574`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000460a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000464b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000462f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000466d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000462f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000466d`

## string_xrefs

- `0x1800046b6`: `REGISTRY`

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
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v31; // [rsp+78h] [rbp-88h]
  unsigned __int16 Src[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v31 = 0;
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
        v34 = 34;
        v20 = -1;
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
        *(_WORD *)&v35[2 * (int)v20 - 2] = 34;
        v23 = 2LL * (int)v20 + 2;
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
0x1800043ec  mov     [rsp-8+arg_10], rbx
0x1800043f1  push    rbp
0x1800043f2  push    rsi
0x1800043f3  push    rdi
0x1800043f4  push    r12
0x1800043f6  push    r13
0x1800043f8  push    r14
0x1800043fa  push    r15
0x1800043fc  lea     rbp, [rsp-9D0h]
0x180004404  sub     rsp, 0AD0h
0x18000440b  mov     rax, cs:__security_cookie
0x180004412  xor     rax, rsp
0x180004415  mov     [rbp+0A00h+var_40], rax
0x18000441c  mov     rbx, r9
0x18000441f  mov     r15d, r8d
0x180004422  mov     r12d, edx
0x180004425  mov     r14, rcx
0x180004428  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000442f  mov     [rsp+0B00h+var_AD0], rax
0x180004434  xor     r13d, r13d
0x180004437  mov     [rsp+0B00h+var_AC8], r13
0x18000443c  mov     [rsp+0B00h+var_AC0], r13
0x180004441  mov     [rsp+0B00h+var_AB8], r13d
0x180004446  xorps   xmm0, xmm0
0x180004449  xor     eax, eax
0x18000444b  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180004450  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180004455  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000445a  mov     [rsp+0B00h+var_A88], r13b
0x18000445f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180004464  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004469  mov     edi, eax
0x18000446b  test    eax, eax
0x18000446d  js      loc_1800046D0
0x180004473  mov     [rsp+0B00h+var_A88], 1
0x180004478  test    rbx, rbx
0x18000447b  jz      short loc_1800044BA
0x18000447d  jmp     short loc_1800044B2
0x18000447f  mov     rsi, [rbx+8]
0x180004483  test    rsi, rsi
0x180004486  jz      short loc_1800044AE
0x180004488  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000448d  call    cs:__imp_EnterCriticalSection
0x180004493  mov     r8, rsi; unsigned __int16 *
0x180004496  mov     rdx, rdi; unsigned __int16 *
0x180004499  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000449e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800044a3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800044a8  call    cs:__imp_LeaveCriticalSection
0x1800044ae  add     rbx, 10h
0x1800044b2  mov     rdi, [rbx]
0x1800044b5  test    rdi, rdi
0x1800044b8  jnz     short loc_18000447F
0x1800044ba  mov     rax, [r14]
0x1800044bd  lea     rdx, [rsp+0B00h+var_AD0]
0x1800044c2  mov     rcx, r14
0x1800044c5  mov     rax, [rax+28h]
0x1800044c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ce  mov     ebx, eax
0x1800044d0  test    eax, eax
0x1800044d2  js      loc_180004683
0x1800044d8  mov     rbx, cs:hModule
0x1800044df  mov     edi, 104h
0x1800044e4  mov     r8d, edi; nSize
0x1800044e7  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800044ee  mov     rcx, rbx; hModule
0x1800044f1  call    cs:__imp_GetModuleFileNameW
0x1800044f7  test    eax, eax
0x1800044f9  jnz     short loc_180004505
0x1800044fb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004500  jmp     loc_180004681
0x180004505  cmp     eax, edi
0x180004507  jnz     short loc_180004513
0x180004509  mov     ebx, 8007007Ah
0x18000450e  jmp     loc_180004683
0x180004513  lea     rdx, [rbp+0A00h+Filename]
0x18000451a  mov     ecx, r13d
0x18000451d  mov     r9d, 27h ; '''
0x180004523  movzx   r8d, word ptr [rdx]
0x180004527  test    r8w, r8w
0x18000452b  jz      short loc_180004557
0x18000452d  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180004533  cmp     r8w, r9w
0x180004537  jnz     short loc_180004549
0x180004539  cmp     ecx, 206h
0x18000453f  jnb     short loc_180004549
0x180004541  inc     ecx
0x180004543  mov     [rbp+rcx*2+0A00h+Src], r9w
0x180004549  add     rdx, 2
0x18000454d  inc     ecx
0x18000454f  cmp     ecx, 207h
0x180004555  jb      short loc_180004523
0x180004557  mov     [rbp+rcx*2+0A00h+Src], r13w
0x18000455d  test    rbx, rbx
0x180004560  jz      short loc_180004583
0x180004562  xor     ecx, ecx; lpModuleName
0x180004564  call    cs:__imp_GetModuleHandleW
0x18000456a  cmp     rbx, rax
0x18000456d  jz      short loc_180004583
0x18000456f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004574  call    cs:__imp_EnterCriticalSection
0x18000457a  lea     r8, [rbp+0A00h+Src]
0x18000457e  jmp     loc_180004617
0x180004583  mov     edi, 22h ; '"'
0x180004588  mov     [rbp+0A00h+var_460], di
0x18000458f  lea     rcx, [rbp+0A00h+Src]
0x180004593  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004597  mov     rax, rbx
0x18000459a  inc     rax
0x18000459d  cmp     [rcx+rax*2], r13w
0x1800045a2  jnz     short loc_18000459A
0x1800045a4  inc     eax
0x1800045a6  movsxd  r8, eax
0x1800045a9  add     r8, r8; Size
0x1800045ac  jz      short loc_1800045CB
0x1800045ae  cmp     r8, 414h
0x1800045b5  ja      loc_180004691
0x1800045bb  lea     rdx, [rbp+0A00h+Src]; Src
0x1800045bf  lea     rcx, [rbp+0A00h+var_45E]; void *
0x1800045c6  call    memcpy_0
0x1800045cb  lea     rax, [rbp+0A00h+var_460]
0x1800045d2  inc     rbx
0x1800045d5  cmp     [rax+rbx*2], r13w
0x1800045da  jnz     short loc_1800045D2
0x1800045dc  movsxd  rax, ebx
0x1800045df  mov     [rbp+rax*2+0A00h+var_460], di
0x1800045e7  lea     rcx, ds:2[rax*2]
0x1800045ef  cmp     rcx, 418h
0x1800045f6  jnb     loc_180004706
0x1800045fc  mov     [rbp+rcx+0A00h+var_460], r13w
0x180004605  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000460a  call    cs:__imp_EnterCriticalSection
0x180004610  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180004617  lea     rdx, aModule; "Module"
0x18000461e  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004623  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004628  mov     ebx, eax
0x18000462a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000462f  call    cs:__imp_LeaveCriticalSection
0x180004635  neg     ebx
0x180004637  sbb     ebx, ebx
0x180004639  mov     edi, 8007000Eh
0x18000463e  not     ebx
0x180004640  and     ebx, edi
0x180004642  test    ebx, ebx
0x180004644  js      short loc_180004683
0x180004646  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000464b  call    cs:__imp_EnterCriticalSection
0x180004651  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x180004655  lea     rdx, aModuleRaw; "Module_Raw"
0x18000465c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004661  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180004666  mov     ebx, eax
0x180004668  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000466d  call    cs:__imp_LeaveCriticalSection
0x180004673  mov     ecx, ebx
0x180004675  neg     ecx
0x180004677  sbb     eax, eax
0x180004679  not     eax
0x18000467b  and     eax, edi
0x18000467d  test    ebx, ebx
0x18000467f  jnz     short loc_1800046A5
0x180004681  mov     ebx, eax
0x180004683  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180004688  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000468d  mov     eax, ebx
0x18000468f  jmp     short loc_1800046DC
0x180004691  call    cs:__imp__o__errno
0x180004697  mov     [rax], edi
0x180004699  call    _invalid_parameter_noinfo
0x18000469e  mov     ebx, 80004005h
0x1800046a3  jmp     short loc_180004683
0x1800046a5  mov     eax, r13d
0x1800046a8  test    r15d, r15d
0x1800046ab  setnz   al
0x1800046ae  movzx   r8d, r12w; unsigned __int16 *
0x1800046b2  mov     [rsp+0B00h+var_AE0], eax; int
0x1800046b6  lea     r9, aRegistry; "REGISTRY"
0x1800046bd  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800046c4  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800046c9  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800046ce  jmp     short loc_180004681
0x1800046d0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800046d5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800046da  mov     eax, edi
0x1800046dc  mov     rcx, [rbp+0A00h+var_40]
0x1800046e3  xor     rcx, rsp; StackCookie
0x1800046e6  call    __security_check_cookie
0x1800046eb  mov     rbx, [rsp+0B00h+arg_10]
0x1800046f3  add     rsp, 0AD0h
0x1800046fa  pop     r15
0x1800046fc  pop     r14
0x1800046fe  pop     r13
0x180004700  pop     r12
0x180004702  pop     rdi
0x180004703  pop     rsi
0x180004704  pop     rbp
0x180004705  retn
0x180004706  call    __report_rangecheckfailure
```
