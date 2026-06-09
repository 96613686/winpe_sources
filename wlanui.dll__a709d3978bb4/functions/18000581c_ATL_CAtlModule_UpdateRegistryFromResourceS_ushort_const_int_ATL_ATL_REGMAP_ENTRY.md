# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000581c`
- end: `0x180005b5a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005b70`

## callees

- `0x180001b98`
- `0x180002bcc`
- `0x180002dc8`
- `0x180003834`
- `0x180003e5c`
- `0x180004828`
- `0x18000581c`
- `0x18001bf40`
- `0x18001d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800059fa`
- `msvcrt!memcpy_s` at `0x1800059fa`
- `KERNEL32!GetModuleHandleW` at `0x180005999`
- `KERNEL32!GetModuleHandleW` at `0x180005999`
- `KERNEL32!EnterCriticalSection` at `0x1800058bd`
- `KERNEL32!EnterCriticalSection` at `0x1800059a9`
- `KERNEL32!EnterCriticalSection` at `0x180005a47`
- `KERNEL32!EnterCriticalSection` at `0x180005a8c`
- `KERNEL32!EnterCriticalSection` at `0x1800058bd`
- `KERNEL32!EnterCriticalSection` at `0x1800059a9`
- `KERNEL32!EnterCriticalSection` at `0x180005a47`
- `KERNEL32!EnterCriticalSection` at `0x180005a8c`
- `KERNEL32!GetModuleFileNameW` at `0x18000591e`
- `KERNEL32!GetModuleFileNameW` at `0x18000591e`
- `KERNEL32!LeaveCriticalSection` at `0x1800058d8`
- `KERNEL32!LeaveCriticalSection` at `0x180005a6c`
- `KERNEL32!LeaveCriticalSection` at `0x180005ab1`
- `KERNEL32!LeaveCriticalSection` at `0x1800058d8`
- `KERNEL32!LeaveCriticalSection` at `0x180005a6c`
- `KERNEL32!LeaveCriticalSection` at `0x180005ab1`

## string_xrefs

- `0x180005ae7`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        const unsigned __int16 *a2,
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
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Source[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v32; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v25 = &ATL::CRegObject::`vftable';
  v26[0] = 0;
  v26[1] = 0;
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
      goto LABEL_39;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v11 = -2147024774;
        goto LABEL_39;
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
          goto LABEL_39;
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
LABEL_39:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v23 == 0 ? 0x8007000E : 0;
      if ( v23 )
      {
        if ( a3 )
        {
          if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, a2, L"REGISTRY", 1);
            goto LABEL_11;
          }
        }
        else if ( a2 )
        {
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v25, Filename, a2, L"REGISTRY", 0);
          goto LABEL_11;
        }
        v11 = -2147024809;
        goto LABEL_39;
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
LABEL_11:
    v11 = Error;
    goto LABEL_39;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000581c  mov     [rsp-8+arg_10], rbx
0x180005821  push    rbp
0x180005822  push    rsi
0x180005823  push    rdi
0x180005824  push    r12
0x180005826  push    r13
0x180005828  push    r14
0x18000582a  push    r15
0x18000582c  lea     rbp, [rsp-9D0h]
0x180005834  sub     rsp, 0AD0h
0x18000583b  mov     rax, cs:__security_cookie
0x180005842  xor     rax, rsp
0x180005845  mov     [rbp+0A00h+var_40], rax
0x18000584c  xor     r13d, r13d
0x18000584f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180005856  xorps   xmm0, xmm0
0x180005859  mov     [rsp+0B00h+var_AD0], rax
0x18000585e  xor     eax, eax
0x180005860  mov     [rsp+0B00h+var_AC8], r13
0x180005865  mov     r15, rcx
0x180005868  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000586d  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180005872  mov     [rsp+0B00h+var_AC0], r13
0x180005877  mov     rbx, r9
0x18000587a  mov     [rsp+0B00h+var_AB8], r13d
0x18000587f  mov     r12d, r8d
0x180005882  mov     [rsp+0B00h+var_A88], r13b
0x180005887  mov     r14, rdx
0x18000588a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000588f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180005894  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005899  mov     edi, eax
0x18000589b  test    eax, eax
0x18000589d  js      loc_180005B1E
0x1800058a3  mov     [rsp+0B00h+var_A88], 1
0x1800058a8  test    rbx, rbx
0x1800058ab  jz      short loc_1800058EA
0x1800058ad  jmp     short loc_1800058E2
0x1800058af  mov     rsi, [rbx+8]
0x1800058b3  test    rsi, rsi
0x1800058b6  jz      short loc_1800058DE
0x1800058b8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800058bd  call    cs:__imp_EnterCriticalSection
0x1800058c3  mov     r8, rsi; unsigned __int16 *
0x1800058c6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800058cb  mov     rdx, rdi; unsigned __int16 *
0x1800058ce  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800058d3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800058d8  call    cs:__imp_LeaveCriticalSection
0x1800058de  add     rbx, 10h
0x1800058e2  mov     rdi, [rbx]
0x1800058e5  test    rdi, rdi
0x1800058e8  jnz     short loc_1800058AF
0x1800058ea  mov     rax, [r15]
0x1800058ed  lea     rdx, [rsp+0B00h+var_AD0]
0x1800058f2  mov     rcx, r15
0x1800058f5  mov     rax, [rax+28h]
0x1800058f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058fe  mov     ebx, eax
0x180005900  test    eax, eax
0x180005902  js      loc_180005B10
0x180005908  mov     rbx, cs:hModule
0x18000590f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180005913  mov     edi, 104h
0x180005918  mov     rcx, rbx; hModule
0x18000591b  mov     r8d, edi; nSize
0x18000591e  call    cs:__imp_GetModuleFileNameW
0x180005924  test    eax, eax
0x180005926  jnz     short loc_180005934
0x180005928  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000592d  mov     ebx, eax
0x18000592f  jmp     loc_180005B10
0x180005934  cmp     eax, edi
0x180005936  jnz     short loc_180005942
0x180005938  mov     ebx, 8007007Ah
0x18000593d  jmp     loc_180005B10
0x180005942  lea     rdx, [rbp+0A00h+Filename]
0x180005946  mov     ecx, r13d
0x180005949  mov     r9d, 27h ; '''
0x18000594f  movzx   r8d, word ptr [rdx]
0x180005953  test    r8w, r8w
0x180005957  jz      short loc_180005989
0x180005959  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180005962  cmp     r8w, r9w
0x180005966  jnz     short loc_18000597B
0x180005968  cmp     ecx, 206h
0x18000596e  jnb     short loc_18000597B
0x180005970  inc     ecx
0x180005972  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000597b  add     rdx, 2
0x18000597f  inc     ecx
0x180005981  cmp     ecx, 207h
0x180005987  jb      short loc_18000594F
0x180005989  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180005992  test    rbx, rbx
0x180005995  jz      short loc_1800059BB
0x180005997  xor     ecx, ecx; lpModuleName
0x180005999  call    cs:__imp_GetModuleHandleW
0x18000599f  cmp     rbx, rax
0x1800059a2  jz      short loc_1800059BB
0x1800059a4  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800059a9  call    cs:__imp_EnterCriticalSection
0x1800059af  lea     r8, [rbp+0A00h+Source]
0x1800059b6  jmp     loc_180005A54
0x1800059bb  mov     edi, 22h ; '"'
0x1800059c0  lea     rcx, [rbp+0A00h+Source]
0x1800059c7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800059cb  mov     [rbp+0A00h+var_460], di
0x1800059d2  mov     rax, rbx
0x1800059d5  inc     rax
0x1800059d8  cmp     [rcx+rax*2], r13w
0x1800059dd  jnz     short loc_1800059D5
0x1800059df  inc     eax
0x1800059e1  lea     r8, [rbp+0A00h+Source]; Source
0x1800059e8  movsxd  r9, eax
0x1800059eb  lea     rcx, [rbp+0A00h+Destination]; Destination
0x1800059f2  add     r9, r9; SourceSize
0x1800059f5  mov     edx, 414h; DestinationSize
0x1800059fa  call    cs:__imp_memcpy_s
0x180005a00  test    eax, eax
0x180005a02  jnz     loc_180005B0B
0x180005a08  lea     rax, [rbp+0A00h+var_460]
0x180005a0f  inc     rbx
0x180005a12  cmp     [rax+rbx*2], r13w
0x180005a17  jnz     short loc_180005A0F
0x180005a19  movsxd  rax, ebx
0x180005a1c  lea     rcx, ds:2[rax*2]
0x180005a24  mov     [rbp+rax*2+0A00h+var_460], di
0x180005a2c  cmp     rcx, 418h
0x180005a33  jnb     loc_180005B54
0x180005a39  mov     [rbp+rcx+0A00h+var_460], r13w
0x180005a42  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005a47  call    cs:__imp_EnterCriticalSection
0x180005a4d  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180005a54  lea     rdx, aModule; "Module"
0x180005a5b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005a60  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005a65  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005a6a  mov     ebx, eax
0x180005a6c  call    cs:__imp_LeaveCriticalSection
0x180005a72  neg     ebx
0x180005a74  mov     edi, 8007000Eh
0x180005a79  sbb     ebx, ebx
0x180005a7b  not     ebx
0x180005a7d  and     ebx, edi
0x180005a7f  test    ebx, ebx
0x180005a81  js      loc_180005B10
0x180005a87  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005a8c  call    cs:__imp_EnterCriticalSection
0x180005a92  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180005a99  lea     rdx, aModuleRaw; "Module_Raw"
0x180005aa0  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180005aa5  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180005aaa  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180005aaf  mov     ebx, eax
0x180005ab1  call    cs:__imp_LeaveCriticalSection
0x180005ab7  mov     ecx, ebx
0x180005ab9  neg     ecx
0x180005abb  sbb     eax, eax
0x180005abd  not     eax
0x180005abf  and     eax, edi
0x180005ac1  test    ebx, ebx
0x180005ac3  jz      loc_18000592D
0x180005ac9  test    r12d, r12d
0x180005acc  jz      short loc_180005ADD
0x180005ace  test    r14, r14
0x180005ad1  jz      short loc_180005B04
0x180005ad3  mov     [rsp+0B00h+var_AE0], 1
0x180005adb  jmp     short loc_180005AE7
0x180005add  test    r14, r14
0x180005ae0  jz      short loc_180005B04
0x180005ae2  mov     [rsp+0B00h+var_AE0], r13d; int
0x180005ae7  lea     r9, aRegistry; "REGISTRY"
0x180005aee  mov     r8, r14; unsigned __int16 *
0x180005af1  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180005af5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005afa  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180005aff  jmp     loc_18000592D
0x180005b04  mov     ebx, 80070057h
0x180005b09  jmp     short loc_180005B10
0x180005b0b  mov     ebx, 80004005h
0x180005b10  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005b15  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005b1a  mov     eax, ebx
0x180005b1c  jmp     short loc_180005B2A
0x180005b1e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180005b23  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180005b28  mov     eax, edi
0x180005b2a  mov     rcx, [rbp+0A00h+var_40]
0x180005b31  xor     rcx, rsp; StackCookie
0x180005b34  call    __security_check_cookie
0x180005b39  mov     rbx, [rsp+0B00h+arg_10]
0x180005b41  add     rsp, 0AD0h
0x180005b48  pop     r15
0x180005b4a  pop     r14
0x180005b4c  pop     r13
0x180005b4e  pop     r12
0x180005b50  pop     rdi
0x180005b51  pop     rsi
0x180005b52  pop     rbp
0x180005b53  retn
0x180005b54  call    __report_rangecheckfailure
```
