# ATL::CAtlModule::UpdateRegistryFromResource(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800063ec`
- end: `0x180006705`
- name: `?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `793`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x180006710`

## callees

- `0x1800063ec`
- `0x180006864`
- `0x18000693c`
- `0x180006ad0`
- `0x180006ba4`
- `0x1800087c8`
- `0x18002fda9`
- `0x18002fe45`
- `0x18002fe99`
- `0x18002ffd0`
- `0x18003017c`
- `0x180036a10`
- `0x180036a90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800064f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800064f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006568`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006568`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006578`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006613`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006654`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006578`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006613`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006654`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006472`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006472`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006679`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000647c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000647c`

## string_xrefs

- `0x1800066e8`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResource(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  signed int LastError; // eax
  signed int v10; // ebx
  signed int Error; // eax
  HMODULE v12; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v14; // r8
  wchar_t *v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // r9
  __int64 v18; // rdx
  wchar_t *v19; // r8
  wchar_t *v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rax
  size_t v23; // r8
  unsigned __int64 v24; // rax
  int v25; // ebx
  int v26; // ebx
  void **v28; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v29[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v30; // [rsp+48h] [rbp-B8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v32; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t v34; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v35[1054]; // [rsp+292h] [rbp+192h] BYREF
  wchar_t Src[520]; // [rsp+6B0h] [rbp+5B0h] BYREF

  memset_0(&v28, 0, 0x50u);
  v28 = &ATL::CRegObject::`vftable';
  v8 = 0;
  v29[0] = 0;
  v29[1] = 0;
  v30 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v32 = 0;
  if ( !InitializeCriticalSectionEx(&CriticalSection, 0, 0) )
  {
    LastError = GetLastError();
    v10 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v10 = LastError;
    if ( v10 < 0 )
      goto LABEL_35;
  }
  v32 = 1;
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v28, *(const wchar_t **)a4, *((const wchar_t **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v28);
  if ( Error < 0 )
    goto LABEL_34;
  v12 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_34:
    v10 = Error;
    goto LABEL_35;
  }
  if ( ModuleFileNameW == 260 )
  {
    v10 = -2147024774;
    goto LABEL_35;
  }
  v14 = Filename;
  v15 = Src;
  v16 = 0;
  v17 = 519;
  do
  {
    v18 = *v14;
    if ( !(_WORD)v18 )
      break;
    *v15++ = v18;
    if ( (_WORD)v18 == 39 && ++v16 < 0x207 )
      *v15++ = 39;
    ++v14;
    ++v16;
  }
  while ( v16 < 0x207 );
  *v15 = 0;
  if ( v12 && v12 != GetModuleHandleW(0) )
  {
    EnterCriticalSection(&CriticalSection);
    v19 = Src;
    goto LABEL_31;
  }
  v34 = 34;
  v20 = Src;
  v21 = -1;
  v22 = -1;
  do
    ++v22;
  while ( Src[v22] );
  v23 = 2LL * ((int)v22 + 1);
  if ( !v23 )
  {
    do
LABEL_28:
      ++v21;
    while ( *(_WORD *)&v35[2 * v21 - 2] );
    *(_WORD *)&v35[2 * (int)v21 - 2] = 34;
    v24 = 2LL * (int)v21 + 2;
    if ( v24 >= 0x418 )
      _report_rangecheckfailure(v20, v18, v23, v17);
    *(_WORD *)&v35[v24 - 2] = 0;
    EnterCriticalSection(&CriticalSection);
    v19 = &v34;
LABEL_31:
    v25 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v29, L"Module", v19);
    LeaveCriticalSection(&CriticalSection);
    v10 = v25 == 0 ? 0x8007000E : 0;
    if ( v10 >= 0 )
    {
      EnterCriticalSection(&CriticalSection);
      v26 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v29, L"Module_Raw", Src);
      LeaveCriticalSection(&CriticalSection);
      Error = v26 == 0 ? 0x8007000E : 0;
      if ( v26 )
      {
        LOBYTE(v8) = a3 != 0;
        Error = ATL::CRegObject::RegisterFromResource(
                  (ATL::CRegObject *)&v28,
                  Filename,
                  (const wchar_t *)a2,
                  L"REGISTRY",
                  v8);
      }
      goto LABEL_34;
    }
LABEL_35:
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v28);
    return (unsigned int)v10;
  }
  if ( v23 <= 0x416 )
  {
    memmove(v35, Src, v23);
    goto LABEL_28;
  }
  *(_DWORD *)o__errno_0(Src, v18, v23, v17) = 34;
  invalid_parameter_noinfo();
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v28);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800063ec  push    rbp
0x1800063ee  push    rbx
0x1800063ef  push    rsi
0x1800063f0  push    rdi
0x1800063f1  push    r12
0x1800063f3  push    r14
0x1800063f5  push    r15
0x1800063f7  lea     rbp, [rsp-9D0h]
0x1800063ff  sub     rsp, 0AD0h
0x180006406  mov     rax, cs:__security_cookie
0x18000640d  xor     rax, rsp
0x180006410  mov     [rbp+0A00h+var_40], rax
0x180006417  mov     rsi, r9
0x18000641a  mov     r15d, r8d
0x18000641d  mov     r12d, edx
0x180006420  mov     r14, rcx
0x180006423  xor     edx, edx; Val
0x180006425  lea     r8d, [rdx+50h]; Size
0x180006429  lea     rcx, [rsp+0B00h+var_AD0]; void *
0x18000642e  call    memset_0
0x180006433  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000643a  mov     [rsp+0B00h+var_AD0], rax
0x18000643f  xor     edi, edi
0x180006441  mov     [rsp+0B00h+var_AC8], rdi
0x180006446  mov     [rsp+0B00h+var_AC0], rdi
0x18000644b  mov     [rsp+0B00h+var_AB8], edi
0x18000644f  xorps   xmm0, xmm0
0x180006452  xor     eax, eax
0x180006454  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180006459  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000645e  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180006463  mov     [rsp+0B00h+var_A88], dil
0x180006468  xor     r8d, r8d; Flags
0x18000646b  xor     edx, edx; dwSpinCount
0x18000646d  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006472  call    cs:__imp_InitializeCriticalSectionEx
0x180006478  test    eax, eax
0x18000647a  jnz     short loc_180006498
0x18000647c  call    cs:__imp_GetLastError
0x180006482  movzx   ebx, ax
0x180006485  or      ebx, 80070000h
0x18000648b  test    eax, eax
0x18000648d  cmovle  ebx, eax
0x180006490  test    ebx, ebx
0x180006492  js      loc_18000668F
0x180006498  mov     [rsp+0B00h+var_A88], 1
0x18000649d  test    rsi, rsi
0x1800064a0  jz      short loc_1800064C1
0x1800064a2  jmp     short loc_1800064B9
0x1800064a4  mov     r8, [rsi+8]; wchar_t *
0x1800064a8  mov     rdx, rax; wchar_t *
0x1800064ab  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800064b0  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x1800064b5  lea     rsi, [rsi+10h]
0x1800064b9  mov     rax, [rsi]
0x1800064bc  test    rax, rax
0x1800064bf  jnz     short loc_1800064A4
0x1800064c1  mov     rax, [r14]
0x1800064c4  lea     rdx, [rsp+0B00h+var_AD0]
0x1800064c9  mov     rcx, r14
0x1800064cc  mov     rax, [rax+28h]
0x1800064d0  call    _guard_dispatch_icall
0x1800064d5  test    eax, eax
0x1800064d7  js      loc_18000668D
0x1800064dd  mov     rbx, cs:hModule
0x1800064e4  mov     esi, 104h
0x1800064e9  mov     r8d, esi; nSize
0x1800064ec  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x1800064f0  mov     rcx, rbx; hModule
0x1800064f3  call    cs:__imp_GetModuleFileNameW
0x1800064f9  test    eax, eax
0x1800064fb  jnz     short loc_180006507
0x1800064fd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180006502  jmp     loc_18000668D
0x180006507  cmp     eax, esi
0x180006509  jnz     short loc_180006515
0x18000650b  mov     ebx, 8007007Ah
0x180006510  jmp     loc_18000668F
0x180006515  lea     r8, [rbp+0A00h+Filename]
0x180006519  lea     rax, [rbp+0A00h+Src]
0x180006520  mov     ecx, edi
0x180006522  mov     r10d, 27h ; '''
0x180006528  mov     r9d, 207h
0x18000652e  movzx   edx, word ptr [r8]
0x180006532  test    dx, dx
0x180006535  jz      short loc_18000655E
0x180006537  mov     [rax], dx
0x18000653a  add     rax, 2
0x18000653e  cmp     dx, r10w
0x180006542  jnz     short loc_180006553
0x180006544  inc     ecx
0x180006546  cmp     ecx, r9d
0x180006549  jnb     short loc_180006553
0x18000654b  mov     [rax], r10w
0x18000654f  add     rax, 2
0x180006553  add     r8, 2
0x180006557  inc     ecx
0x180006559  cmp     ecx, r9d
0x18000655c  jb      short loc_18000652E
0x18000655e  mov     [rax], di
0x180006561  test    rbx, rbx
0x180006564  jz      short loc_18000658A
0x180006566  xor     ecx, ecx; lpModuleName
0x180006568  call    cs:__imp_GetModuleHandleW
0x18000656e  cmp     rbx, rax
0x180006571  jz      short loc_18000658A
0x180006573  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006578  call    cs:__imp_EnterCriticalSection
0x18000657e  lea     r8, [rbp+0A00h+Src]
0x180006585  jmp     loc_180006620
0x18000658a  mov     esi, 22h ; '"'
0x18000658f  mov     [rbp+0A00h+var_870], si
0x180006596  lea     rcx, [rbp+0A00h+Src]
0x18000659d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800065a1  mov     rax, rbx
0x1800065a4  inc     rax
0x1800065a7  cmp     [rcx+rax*2], di
0x1800065ab  jnz     short loc_1800065A4
0x1800065ad  inc     eax
0x1800065af  movsxd  r8, eax
0x1800065b2  add     r8, r8; Size
0x1800065b5  jz      short loc_1800065D7
0x1800065b7  cmp     r8, 416h
0x1800065be  ja      loc_1800066BC
0x1800065c4  lea     rdx, [rbp+0A00h+Src]; Src
0x1800065cb  lea     rcx, [rbp+0A00h+var_86E]; void *
0x1800065d2  call    memmove
0x1800065d7  lea     rax, [rbp+0A00h+var_870]
0x1800065de  inc     rbx
0x1800065e1  cmp     [rax+rbx*2], di
0x1800065e5  jnz     short loc_1800065DE
0x1800065e7  movsxd  rax, ebx
0x1800065ea  mov     [rbp+rax*2+0A00h+var_870], si
0x1800065f2  lea     rax, ds:2[rax*2]
0x1800065fa  cmp     rax, 418h
0x180006600  jnb     loc_1800066FF
0x180006606  mov     [rbp+rax+0A00h+var_870], di
0x18000660e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006613  call    cs:__imp_EnterCriticalSection
0x180006619  lea     r8, [rbp+0A00h+var_870]; wchar_t *
0x180006620  lea     rdx, aModule; "Module"
0x180006627  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000662c  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180006631  mov     ebx, eax
0x180006633  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006638  call    cs:__imp_LeaveCriticalSection
0x18000663e  neg     ebx
0x180006640  sbb     ebx, ebx
0x180006642  mov     esi, 8007000Eh
0x180006647  not     ebx
0x180006649  and     ebx, esi
0x18000664b  test    ebx, ebx
0x18000664d  js      short loc_18000668F
0x18000664f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006654  call    cs:__imp_EnterCriticalSection
0x18000665a  lea     r8, [rbp+0A00h+Src]; wchar_t *
0x180006661  lea     rdx, aModuleRaw; "Module_Raw"
0x180006668  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000666d  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180006672  mov     ebx, eax
0x180006674  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180006679  call    cs:__imp_LeaveCriticalSection
0x18000667f  mov     ecx, ebx
0x180006681  neg     ecx
0x180006683  sbb     eax, eax
0x180006685  not     eax
0x180006687  and     eax, esi
0x180006689  test    ebx, ebx
0x18000668b  jnz     short loc_1800066D9
0x18000668d  mov     ebx, eax
0x18000668f  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180006694  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180006699  mov     eax, ebx
0x18000669b  mov     rcx, [rbp+0A00h+var_40]
0x1800066a2  xor     rcx, rsp; StackCookie
0x1800066a5  call    __security_check_cookie
0x1800066aa  add     rsp, 0AD0h
0x1800066b1  pop     r15
0x1800066b3  pop     r14
0x1800066b5  pop     r12
0x1800066b7  pop     rdi
0x1800066b8  pop     rsi
0x1800066b9  pop     rbx
0x1800066ba  pop     rbp
0x1800066bb  retn
0x1800066bc  call    _o__errno_0
0x1800066c1  mov     [rax], esi
0x1800066c3  call    _invalid_parameter_noinfo
0x1800066c8  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800066cd  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800066d2  mov     eax, 80004005h
0x1800066d7  jmp     short loc_18000669B
0x1800066d9  test    r15d, r15d
0x1800066dc  setnz   dil
0x1800066e0  movzx   r8d, r12w; wchar_t *
0x1800066e4  mov     [rsp+0B00h+var_AE0], edi; int
0x1800066e8  lea     r9, aRegistry; "REGISTRY"
0x1800066ef  lea     rdx, [rbp+0A00h+Filename]; wchar_t *
0x1800066f3  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800066f8  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x1800066fd  jmp     short loc_18000668D
0x1800066ff  call    __report_rangecheckfailure
```
