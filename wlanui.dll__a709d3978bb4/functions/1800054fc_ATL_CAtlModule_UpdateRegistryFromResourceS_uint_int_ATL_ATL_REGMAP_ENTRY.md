# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800054fc`
- end: `0x180005813`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005b60`

## callees

- `0x180001b98`
- `0x180002bcc`
- `0x180002dc8`
- `0x180003834`
- `0x180003e5c`
- `0x180004828`
- `0x1800054fc`
- `0x18001bf40`
- `0x18001d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800056ce`
- `msvcrt!memcpy_s` at `0x1800056ce`
- `KERNEL32!GetModuleHandleW` at `0x180005676`
- `KERNEL32!GetModuleHandleW` at `0x180005676`
- `KERNEL32!EnterCriticalSection` at `0x18000559d`
- `KERNEL32!EnterCriticalSection` at `0x180005686`
- `KERNEL32!EnterCriticalSection` at `0x18000571b`
- `KERNEL32!EnterCriticalSection` at `0x18000575c`
- `KERNEL32!EnterCriticalSection` at `0x18000559d`
- `KERNEL32!EnterCriticalSection` at `0x180005686`
- `KERNEL32!EnterCriticalSection` at `0x18000571b`
- `KERNEL32!EnterCriticalSection` at `0x18000575c`
- `KERNEL32!GetModuleFileNameW` at `0x180005601`
- `KERNEL32!GetModuleFileNameW` at `0x180005601`
- `KERNEL32!LeaveCriticalSection` at `0x1800055b8`
- `KERNEL32!LeaveCriticalSection` at `0x180005740`
- `KERNEL32!LeaveCriticalSection` at `0x18000577e`
- `KERNEL32!LeaveCriticalSection` at `0x1800055b8`
- `KERNEL32!LeaveCriticalSection` at `0x180005740`
- `KERNEL32!LeaveCriticalSection` at `0x18000577e`

## string_xrefs

- `0x1800057a0`: `REGISTRY`

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
  unsigned __int16 v17; // r8
  unsigned __int16 *v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  int v22; // ebx
  int v23; // ebx
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v29; // [rsp+78h] [rbp-88h]
  unsigned __int16 Source[520]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v26[0] = 0;
  v26[1] = 0;
  v25 = &ATL::CRegObject::`vftable';
  v27 = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v8 >= 0 )
  {
    v29 = 1;
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
          ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v25);
    if ( v11 < 0 )
      goto LABEL_33;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v11 = -2147024774;
        goto LABEL_33;
      }
      v15 = Filename;
      v16 = 0;
      do
      {
        v17 = *v15;
        if ( !*v15 )
          break;
        Source[v16] = v17;
        if ( v17 == 39 && (unsigned int)v16 < 0x206 )
        {
          LODWORD(v16) = v16 + 1;
          Source[(unsigned int)v16] = 39;
        }
        ++v15;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 0x207 );
      Source[v16] = 0;
      if ( !v12 || v12 == GetModuleHandleW(0) )
      {
        v19 = -1;
        v32 = 34;
        v20 = -1;
        do
          ++v20;
        while ( Source[v20] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v20 + 1)) )
        {
          v11 = -2147467259;
          goto LABEL_33;
        }
        do
          ++v19;
        while ( *(_WORD *)&Destination[2 * v19 - 2] );
        v21 = 2LL * (int)v19 + 2;
        *(_WORD *)&Destination[2 * (int)v19 - 2] = 34;
        if ( v21 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v21 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v18 = &v32;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v18 = Source;
      }
      v22 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module", v18);
      LeaveCriticalSection(&CriticalSection);
      v11 = v22 == 0 ? 0x8007000E : 0;
      if ( v11 < 0 )
      {
LABEL_33:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v23 == 0 ? 0x8007000E : 0;
      if ( v23 )
        Error = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v25,
                  Filename,
                  (const unsigned __int16 *)a2,
                  L"REGISTRY",
                  a3 != 0);
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v11 = Error;
    goto LABEL_33;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800054fc  mov     [rsp-8+arg_10], rbx
0x180005501  push    rbp
0x180005502  push    rsi
0x180005503  push    rdi
0x180005504  push    r12
0x180005506  push    r13
0x180005508  push    r14
0x18000550a  push    r15
0x18000550c  lea     rbp, [rsp-9D0h]
0x180005514  sub     rsp, 0AD0h
0x18000551b  mov     rax, cs:__security_cookie
0x180005522  xor     rax, rsp
0x180005525  mov     [rbp+0A00h+var_40], rax
0x18000552c  xor     r13d, r13d
0x18000552f  mov     r12d, edx
0x180005532  xorps   xmm0, xmm0
0x180005535  mov     [rsp+0B00h+var_AC8], r13
0x18000553a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005541  mov     [rsp+0B00h+var_AC0], r13
0x180005546  mov     [rsp+0B00h+var_AD0], rax
0x18000554b  mov     r14, rcx
0x18000554e  xor     eax, eax
0x180005550  mov     [rsp+0B00h+var_AB8], r13d
0x180005555  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000555a  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000555f  mov     rbx, r9
0x180005562  mov     [rsp+0B00h+var_A88], r13b
0x180005567  mov     r15d, r8d
0x18000556a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000556f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180005574  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005579  mov     edi, eax
0x18000557b  test    eax, eax
0x18000557d  js      loc_1800057D7
0x180005583  mov     [rsp+0B00h+var_A88], 1
0x180005588  test    rbx, rbx
0x18000558b  jz      short loc_1800055CA
0x18000558d  jmp     short loc_1800055C2
0x18000558f  mov     rsi, [rbx+8]
0x180005593  test    rsi, rsi
0x180005596  jz      short loc_1800055BE
0x180005598  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000559d  call    cs:__imp_EnterCriticalSection
0x1800055a3  mov     r8, rsi; unsigned __int16 *
0x1800055a6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800055ab  mov     rdx, rdi; unsigned __int16 *
0x1800055ae  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800055b3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800055b8  call    cs:__imp_LeaveCriticalSection
0x1800055be  add     rbx, 10h
0x1800055c2  mov     rdi, [rbx]
0x1800055c5  test    rdi, rdi
0x1800055c8  jnz     short loc_18000558F
0x1800055ca  mov     rax, [r14]
0x1800055cd  lea     rdx, [rsp+0B00h+var_AD0]
0x1800055d2  mov     rcx, r14
0x1800055d5  mov     rax, [rax+28h]
0x1800055d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055de  mov     ebx, eax
0x1800055e0  test    eax, eax
0x1800055e2  js      loc_1800057C9
0x1800055e8  mov     rbx, cs:hModule
0x1800055ef  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800055f6  mov     edi, 104h
0x1800055fb  mov     rcx, rbx; hModule
0x1800055fe  mov     r8d, edi; nSize
0x180005601  call    cs:__imp_GetModuleFileNameW
0x180005607  test    eax, eax
0x180005609  jnz     short loc_180005617
0x18000560b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180005610  mov     ebx, eax
0x180005612  jmp     loc_1800057C9
0x180005617  cmp     eax, edi
0x180005619  jnz     short loc_180005625
0x18000561b  mov     ebx, 8007007Ah
0x180005620  jmp     loc_1800057C9
0x180005625  lea     rdx, [rbp+0A00h+Filename]
0x18000562c  mov     ecx, r13d
0x18000562f  mov     r9d, 27h ; '''
0x180005635  movzx   r8d, word ptr [rdx]
0x180005639  test    r8w, r8w
0x18000563d  jz      short loc_180005669
0x18000563f  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180005645  cmp     r8w, r9w
0x180005649  jnz     short loc_18000565B
0x18000564b  cmp     ecx, 206h
0x180005651  jnb     short loc_18000565B
0x180005653  inc     ecx
0x180005655  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000565b  add     rdx, 2
0x18000565f  inc     ecx
0x180005661  cmp     ecx, 207h
0x180005667  jb      short loc_180005635
0x180005669  mov     [rbp+rcx*2+0A00h+Source], r13w
0x18000566f  test    rbx, rbx
0x180005672  jz      short loc_180005695
0x180005674  xor     ecx, ecx; lpModuleName
0x180005676  call    cs:__imp_GetModuleHandleW
0x18000567c  cmp     rbx, rax
0x18000567f  jz      short loc_180005695
0x180005681  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005686  call    cs:__imp_EnterCriticalSection
0x18000568c  lea     r8, [rbp+0A00h+Source]
0x180005690  jmp     loc_180005728
0x180005695  mov     edi, 22h ; '"'
0x18000569a  lea     rcx, [rbp+0A00h+Source]
0x18000569e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800056a2  mov     [rbp+0A00h+var_460], di
0x1800056a9  mov     rax, rbx
0x1800056ac  inc     rax
0x1800056af  cmp     [rcx+rax*2], r13w
0x1800056b4  jnz     short loc_1800056AC
0x1800056b6  inc     eax
0x1800056b8  lea     r8, [rbp+0A00h+Source]; Source
0x1800056bc  movsxd  r9, eax
0x1800056bf  lea     rcx, [rbp+0A00h+Destination]; Destination
0x1800056c6  add     r9, r9; SourceSize
0x1800056c9  mov     edx, 414h; DestinationSize
0x1800056ce  call    cs:__imp_memcpy_s
0x1800056d4  test    eax, eax
0x1800056d6  jnz     loc_1800057C4
0x1800056dc  lea     rax, [rbp+0A00h+var_460]
0x1800056e3  inc     rbx
0x1800056e6  cmp     [rax+rbx*2], r13w
0x1800056eb  jnz     short loc_1800056E3
0x1800056ed  movsxd  rax, ebx
0x1800056f0  lea     rcx, ds:2[rax*2]
0x1800056f8  mov     [rbp+rax*2+0A00h+var_460], di
0x180005700  cmp     rcx, 418h
0x180005707  jnb     loc_18000580D
0x18000570d  mov     [rbp+rcx+0A00h+var_460], r13w
0x180005716  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000571b  call    cs:__imp_EnterCriticalSection
0x180005721  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180005728  lea     rdx, aModule; "Module"
0x18000572f  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005734  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005739  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000573e  mov     ebx, eax
0x180005740  call    cs:__imp_LeaveCriticalSection
0x180005746  neg     ebx
0x180005748  mov     edi, 8007000Eh
0x18000574d  sbb     ebx, ebx
0x18000574f  not     ebx
0x180005751  and     ebx, edi
0x180005753  test    ebx, ebx
0x180005755  js      short loc_1800057C9
0x180005757  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000575c  call    cs:__imp_EnterCriticalSection
0x180005762  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180005766  lea     rdx, aModuleRaw; "Module_Raw"
0x18000576d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005772  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005777  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000577c  mov     ebx, eax
0x18000577e  call    cs:__imp_LeaveCriticalSection
0x180005784  mov     ecx, ebx
0x180005786  neg     ecx
0x180005788  sbb     eax, eax
0x18000578a  not     eax
0x18000578c  and     eax, edi
0x18000578e  test    ebx, ebx
0x180005790  jz      loc_180005610
0x180005796  mov     eax, r13d
0x180005799  movzx   r8d, r12w; unsigned __int16 *
0x18000579d  test    r15d, r15d
0x1800057a0  lea     r9, aRegistry; "REGISTRY"
0x1800057a7  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x1800057ae  setnz   al
0x1800057b1  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800057b6  mov     [rsp+0B00h+var_AE0], eax; int
0x1800057ba  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x1800057bf  jmp     loc_180005610
0x1800057c4  mov     ebx, 80004005h
0x1800057c9  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800057ce  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800057d3  mov     eax, ebx
0x1800057d5  jmp     short loc_1800057E3
0x1800057d7  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800057dc  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800057e1  mov     eax, edi
0x1800057e3  mov     rcx, [rbp+0A00h+var_40]
0x1800057ea  xor     rcx, rsp; StackCookie
0x1800057ed  call    __security_check_cookie
0x1800057f2  mov     rbx, [rsp+0B00h+arg_10]
0x1800057fa  add     rsp, 0AD0h
0x180005801  pop     r15
0x180005803  pop     r14
0x180005805  pop     r13
0x180005807  pop     r12
0x180005809  pop     rdi
0x18000580a  pop     rsi
0x18000580b  pop     rbp
0x18000580c  retn
0x18000580d  call    __report_rangecheckfailure
```
