# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140005834`
- end: `0x140005b77`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `835`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140005b90`

## callees

- `0x140001490`
- `0x1400014d0`
- `0x140001d8a`
- `0x140001ff4`
- `0x1400021e4`
- `0x140002a18`
- `0x14000380c`
- `0x140004698`
- `0x140005834`
- `0x140006694`
- `0x140007010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005ae8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005ae8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400059af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400059af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140005936`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140005936`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400058f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005a83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400058f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005a83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005ac4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400058d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400059bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005a5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005a9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400058d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400059bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005a5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005a9f`

## string_xrefs

- `0x140005b1a`: `REGISTRY`

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
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Src[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v34; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v35[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
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
      goto LABEL_33;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_32;
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
            goto LABEL_33;
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
        {
          if ( a3 )
          {
            if ( a2 )
            {
              Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v27, Filename, a2, L"REGISTRY", 1);
              goto LABEL_32;
            }
          }
          else if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v27, Filename, a2, L"REGISTRY", 0);
            goto LABEL_32;
          }
          v11 = -2147024809;
          goto LABEL_33;
        }
LABEL_32:
        v11 = Error;
      }
    }
LABEL_33:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
    return (unsigned int)v11;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140005834  mov     [rsp-8+arg_10], rbx
0x140005839  push    rbp
0x14000583a  push    rsi
0x14000583b  push    rdi
0x14000583c  push    r12
0x14000583e  push    r13
0x140005840  push    r14
0x140005842  push    r15
0x140005844  lea     rbp, [rsp-9D0h]
0x14000584c  sub     rsp, 0AD0h
0x140005853  mov     rax, cs:__security_cookie
0x14000585a  xor     rax, rsp
0x14000585d  mov     [rbp+0A00h+var_40], rax
0x140005864  xor     r13d, r13d
0x140005867  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x14000586e  xorps   xmm0, xmm0
0x140005871  mov     [rsp+0B00h+var_AD0], rax
0x140005876  xor     eax, eax
0x140005878  mov     [rsp+0B00h+var_AC8], r13
0x14000587d  mov     r15, rcx
0x140005880  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x140005885  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x14000588a  mov     [rsp+0B00h+var_AC0], r13
0x14000588f  mov     rbx, r9
0x140005892  mov     [rsp+0B00h+var_AB8], r13d
0x140005897  mov     r12d, r8d
0x14000589a  mov     [rsp+0B00h+var_A88], r13b
0x14000589f  mov     r14, rdx
0x1400058a2  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x1400058a7  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x1400058ac  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400058b1  mov     edi, eax
0x1400058b3  test    eax, eax
0x1400058b5  js      loc_140005B3B
0x1400058bb  mov     [rsp+0B00h+var_A88], 1
0x1400058c0  test    rbx, rbx
0x1400058c3  jz      short loc_140005902
0x1400058c5  jmp     short loc_1400058FA
0x1400058c7  mov     rsi, [rbx+8]
0x1400058cb  test    rsi, rsi
0x1400058ce  jz      short loc_1400058F6
0x1400058d0  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400058d5  call    cs:__imp_EnterCriticalSection
0x1400058db  mov     r8, rsi; unsigned __int16 *
0x1400058de  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1400058e3  mov     rdx, rdi; unsigned __int16 *
0x1400058e6  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1400058eb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400058f0  call    cs:__imp_LeaveCriticalSection
0x1400058f6  add     rbx, 10h
0x1400058fa  mov     rdi, [rbx]
0x1400058fd  test    rdi, rdi
0x140005900  jnz     short loc_1400058C7
0x140005902  mov     rax, [r15]
0x140005905  lea     rdx, [rsp+0B00h+var_AD0]
0x14000590a  mov     rcx, r15
0x14000590d  mov     rax, [rax+28h]
0x140005911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005916  mov     ebx, eax
0x140005918  test    eax, eax
0x14000591a  js      loc_140005ADA
0x140005920  mov     rbx, cs:hModule
0x140005927  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x14000592b  mov     edi, 104h
0x140005930  mov     rcx, rbx; hModule
0x140005933  mov     r8d, edi; nSize
0x140005936  call    cs:__imp_GetModuleFileNameW
0x14000593c  test    eax, eax
0x14000593e  jnz     short loc_14000594A
0x140005940  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140005945  jmp     loc_140005AD8
0x14000594a  cmp     eax, edi
0x14000594c  jnz     short loc_140005958
0x14000594e  mov     ebx, 8007007Ah
0x140005953  jmp     loc_140005ADA
0x140005958  lea     rdx, [rbp+0A00h+Filename]
0x14000595c  mov     ecx, r13d
0x14000595f  mov     r9d, 27h ; '''
0x140005965  movzx   r8d, word ptr [rdx]
0x140005969  test    r8w, r8w
0x14000596d  jz      short loc_14000599F
0x14000596f  mov     [rbp+rcx*2+0A00h+Src], r8w
0x140005978  cmp     r8w, r9w
0x14000597c  jnz     short loc_140005991
0x14000597e  cmp     ecx, 206h
0x140005984  jnb     short loc_140005991
0x140005986  inc     ecx
0x140005988  mov     [rbp+rcx*2+0A00h+Src], r9w
0x140005991  add     rdx, 2
0x140005995  inc     ecx
0x140005997  cmp     ecx, 207h
0x14000599d  jb      short loc_140005965
0x14000599f  mov     [rbp+rcx*2+0A00h+Src], r13w
0x1400059a8  test    rbx, rbx
0x1400059ab  jz      short loc_1400059D1
0x1400059ad  xor     ecx, ecx; lpModuleName
0x1400059af  call    cs:__imp_GetModuleHandleW
0x1400059b5  cmp     rbx, rax
0x1400059b8  jz      short loc_1400059D1
0x1400059ba  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400059bf  call    cs:__imp_EnterCriticalSection
0x1400059c5  lea     r8, [rbp+0A00h+Src]
0x1400059cc  jmp     loc_140005A6B
0x1400059d1  mov     edi, 22h ; '"'
0x1400059d6  lea     rcx, [rbp+0A00h+Src]
0x1400059dd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400059e1  mov     [rbp+0A00h+var_460], di
0x1400059e8  mov     rax, rbx
0x1400059eb  inc     rax
0x1400059ee  cmp     [rcx+rax*2], r13w
0x1400059f3  jnz     short loc_1400059EB
0x1400059f5  inc     eax
0x1400059f7  movsxd  r8, eax
0x1400059fa  add     r8, r8; Size
0x1400059fd  jz      short loc_140005A1F
0x1400059ff  cmp     r8, 414h
0x140005a06  ja      loc_140005AE8
0x140005a0c  lea     rdx, [rbp+0A00h+Src]; Src
0x140005a13  lea     rcx, [rbp+0A00h+var_45E]; void *
0x140005a1a  call    memcpy_0
0x140005a1f  lea     rax, [rbp+0A00h+var_460]
0x140005a26  inc     rbx
0x140005a29  cmp     [rax+rbx*2], r13w
0x140005a2e  jnz     short loc_140005A26
0x140005a30  movsxd  rax, ebx
0x140005a33  lea     rcx, ds:2[rax*2]
0x140005a3b  mov     [rbp+rax*2+0A00h+var_460], di
0x140005a43  cmp     rcx, 418h
0x140005a4a  jnb     loc_140005B71
0x140005a50  mov     [rbp+rcx+0A00h+var_460], r13w
0x140005a59  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140005a5e  call    cs:__imp_EnterCriticalSection
0x140005a64  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x140005a6b  lea     rdx, aModule; "Module"
0x140005a72  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140005a77  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140005a7c  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140005a81  mov     ebx, eax
0x140005a83  call    cs:__imp_LeaveCriticalSection
0x140005a89  neg     ebx
0x140005a8b  mov     edi, 8007000Eh
0x140005a90  sbb     ebx, ebx
0x140005a92  not     ebx
0x140005a94  and     ebx, edi
0x140005a96  test    ebx, ebx
0x140005a98  js      short loc_140005ADA
0x140005a9a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140005a9f  call    cs:__imp_EnterCriticalSection
0x140005aa5  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x140005aac  lea     rdx, aModuleRaw; "Module_Raw"
0x140005ab3  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140005ab8  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140005abd  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140005ac2  mov     ebx, eax
0x140005ac4  call    cs:__imp_LeaveCriticalSection
0x140005aca  mov     ecx, ebx
0x140005acc  neg     ecx
0x140005ace  sbb     eax, eax
0x140005ad0  not     eax
0x140005ad2  and     eax, edi
0x140005ad4  test    ebx, ebx
0x140005ad6  jnz     short loc_140005AFC
0x140005ad8  mov     ebx, eax
0x140005ada  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140005adf  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140005ae4  mov     eax, ebx
0x140005ae6  jmp     short loc_140005B47
0x140005ae8  call    cs:__imp__o__errno
0x140005aee  mov     [rax], edi
0x140005af0  call    _invalid_parameter_noinfo
0x140005af5  mov     ebx, 80004005h
0x140005afa  jmp     short loc_140005ADA
0x140005afc  test    r12d, r12d
0x140005aff  jz      short loc_140005B10
0x140005b01  test    r14, r14
0x140005b04  jz      short loc_140005B34
0x140005b06  mov     [rsp+0B00h+var_AE0], 1
0x140005b0e  jmp     short loc_140005B1A
0x140005b10  test    r14, r14
0x140005b13  jz      short loc_140005B34
0x140005b15  mov     [rsp+0B00h+var_AE0], r13d; int
0x140005b1a  lea     r9, aRegistry; "REGISTRY"
0x140005b21  mov     r8, r14; unsigned __int16 *
0x140005b24  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x140005b28  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140005b2d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x140005b32  jmp     short loc_140005AD8
0x140005b34  mov     ebx, 80070057h
0x140005b39  jmp     short loc_140005ADA
0x140005b3b  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140005b40  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140005b45  mov     eax, edi
0x140005b47  mov     rcx, [rbp+0A00h+var_40]
0x140005b4e  xor     rcx, rsp; StackCookie
0x140005b51  call    __security_check_cookie
0x140005b56  mov     rbx, [rsp+0B00h+arg_10]
0x140005b5e  add     rsp, 0AD0h
0x140005b65  pop     r15
0x140005b67  pop     r14
0x140005b69  pop     r13
0x140005b6b  pop     r12
0x140005b6d  pop     rdi
0x140005b6e  pop     rsi
0x140005b6f  pop     rbp
0x140005b70  retn
0x140005b71  call    __report_rangecheckfailure
```
