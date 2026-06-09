# ATL::CAtlModule::UpdateRegistryFromResource(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800089b4`
- end: `0x180008d4e`
- name: `?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `922`
- prototype: `int(ATL::CAtlModule *__hidden this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x180008d60`

## callees

- `0x180006864`
- `0x18000693c`
- `0x180006ad0`
- `0x180006ba4`
- `0x1800087c8`
- `0x1800089b4`
- `0x18002fda9`
- `0x18002fe45`
- `0x18002fe99`
- `0x18002ffd0`
- `0x18003017c`
- `0x180036a10`
- `0x180036a90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008abf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008abf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008b36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008b46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008c70`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008a3a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008a3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008b70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008c9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a44`

## string_xrefs

- `0x180008cf4`: `REGISTRY`
- `0x180008d1f`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResource(
        ATL::CAtlModule *this,
        const wchar_t *a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  signed int LastError; // eax
  signed int v9; // ebx
  signed int Error; // eax
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  WCHAR *v13; // r8
  wchar_t *v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // ebx
  wchar_t *v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rax
  size_t v22; // r8
  unsigned __int64 v23; // rax
  int v24; // ebx
  int v25; // ebx
  void **v27; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v28[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v29; // [rsp+58h] [rbp-A8h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+60h] [rbp-A0h] BYREF
  char v31; // [rsp+88h] [rbp-78h]
  WCHAR Filename[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v33; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v34[1054]; // [rsp+2A2h] [rbp+1A2h] BYREF
  wchar_t Src[520]; // [rsp+6C0h] [rbp+5C0h] BYREF

  memset_0(&v27, 0, 0x50u);
  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v31 = 0;
  if ( InitializeCriticalSectionEx(&CriticalSection, 0, 0) )
    goto LABEL_5;
  LastError = GetLastError();
  v9 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v9 = LastError;
  if ( v9 >= 0 )
  {
LABEL_5:
    v31 = 1;
    if ( a4 )
    {
      while ( *(_QWORD *)a4 )
      {
        ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v27, *(const wchar_t **)a4, *((const wchar_t **)a4 + 1));
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v27);
    if ( Error < 0 )
      goto LABEL_35;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_35:
      v9 = Error;
      goto LABEL_36;
    }
    if ( ModuleFileNameW != 260 )
    {
      v13 = Filename;
      v14 = Src;
      v15 = 0;
      v16 = 519;
      do
      {
        v17 = *v13;
        if ( !(_WORD)v17 )
          break;
        *v14++ = v17;
        if ( (_WORD)v17 == 39 && ++v15 < 0x207 )
          *v14++ = 39;
        ++v13;
        ++v15;
      }
      while ( v15 < 0x207 );
      *v14 = 0;
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v33 = 34;
        v19 = Src;
        v20 = -1;
        v21 = -1;
        do
          ++v21;
        while ( Src[v21] );
        v22 = 2LL * ((int)v21 + 1);
        if ( v22 )
        {
          if ( v22 > 0x416 )
          {
            *(_DWORD *)o__errno_0(Src, v17, v22, v16) = 34;
            invalid_parameter_noinfo();
            v9 = -2147467259;
            goto LABEL_36;
          }
          memmove(v34, Src, v22);
        }
        do
          ++v20;
        while ( *(_WORD *)&v34[2 * v20 - 2] );
        *(_WORD *)&v34[2 * (int)v20 - 2] = 34;
        v23 = 2LL * (int)v20 + 2;
        if ( v23 >= 0x418 )
          _report_rangecheckfailure(v19, v17, v22, v16);
        *(_WORD *)&v34[v23 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v24 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module", &v33);
        LeaveCriticalSection(&CriticalSection);
        v9 = v24 == 0 ? 0x8007000E : 0;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v18 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v28, L"Module", Src);
        LeaveCriticalSection(&CriticalSection);
        v9 = v18 == 0 ? 0x8007000E : 0;
      }
      if ( v9 < 0 )
        goto LABEL_36;
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
            v9 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 1);
            goto LABEL_36;
          }
        }
        else if ( a2 )
        {
          v9 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 0);
          goto LABEL_36;
        }
        v9 = -2147024809;
        goto LABEL_36;
      }
      goto LABEL_35;
    }
    v9 = -2147024774;
  }
LABEL_36:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v27);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800089b4  push    rbp
0x1800089b6  push    rbx
0x1800089b7  push    rsi
0x1800089b8  push    rdi
0x1800089b9  push    r12
0x1800089bb  push    r14
0x1800089bd  push    r15
0x1800089bf  lea     rbp, [rsp-9E0h]
0x1800089c7  sub     rsp, 0AE0h
0x1800089ce  mov     rax, cs:__security_cookie
0x1800089d5  xor     rax, rsp
0x1800089d8  mov     [rbp+0A10h+var_40], rax
0x1800089df  mov     rdi, r9
0x1800089e2  mov     r15d, r8d
0x1800089e5  mov     rsi, rdx
0x1800089e8  mov     r14, rcx
0x1800089eb  xor     edx, edx; Val
0x1800089ed  lea     r8d, [rdx+50h]; Size
0x1800089f1  lea     rcx, [rsp+0B10h+var_AD0]; void *
0x1800089f6  call    memset_0
0x1800089fb  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180008a02  mov     [rsp+0B10h+var_AD0], rax
0x180008a07  xor     r12d, r12d
0x180008a0a  mov     [rsp+0B10h+var_AC8], r12
0x180008a0f  mov     [rsp+0B10h+var_AC0], r12
0x180008a14  mov     [rsp+0B10h+var_AB8], r12d
0x180008a19  xorps   xmm0, xmm0
0x180008a1c  xor     eax, eax
0x180008a1e  movups  xmmword ptr [rsp+0B10h+CriticalSection.DebugInfo], xmm0
0x180008a23  movups  xmmword ptr [rsp+0B10h+CriticalSection.OwningThread], xmm0
0x180008a28  mov     [rbp+0A10h+CriticalSection.SpinCount], rax
0x180008a2c  mov     [rbp+0A10h+var_A88], r12b
0x180008a30  xor     r8d, r8d; Flags
0x180008a33  xor     edx, edx; dwSpinCount
0x180008a35  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180008a3a  call    cs:__imp_InitializeCriticalSectionEx
0x180008a40  test    eax, eax
0x180008a42  jnz     short loc_180008A60
0x180008a44  call    cs:__imp_GetLastError
0x180008a4a  movzx   ebx, ax
0x180008a4d  or      ebx, 80070000h
0x180008a53  test    eax, eax
0x180008a55  cmovle  ebx, eax
0x180008a58  test    ebx, ebx
0x180008a5a  js      loc_180008CB0
0x180008a60  mov     [rbp+0A10h+var_A88], 1
0x180008a64  test    rdi, rdi
0x180008a67  jz      short loc_180008A88
0x180008a69  jmp     short loc_180008A80
0x180008a6b  mov     r8, [rdi+8]; wchar_t *
0x180008a6f  mov     rdx, rax; wchar_t *
0x180008a72  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008a77  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEB_W0@Z; ATL::CRegObject::AddReplacement(wchar_t const *,wchar_t const *)
0x180008a7c  lea     rdi, [rdi+10h]
0x180008a80  mov     rax, [rdi]
0x180008a83  test    rax, rax
0x180008a86  jnz     short loc_180008A6B
0x180008a88  mov     rax, [r14]
0x180008a8b  lea     rdx, [rsp+0B10h+var_AD0]
0x180008a90  mov     rcx, r14
0x180008a93  mov     rax, [rax+28h]
0x180008a97  call    _guard_dispatch_icall
0x180008a9c  test    eax, eax
0x180008a9e  js      loc_180008CAE
0x180008aa4  mov     [rsp+0B10h+var_AD8], r12
0x180008aa9  mov     rbx, cs:hModule
0x180008ab0  mov     edi, 104h
0x180008ab5  mov     r8d, edi; nSize
0x180008ab8  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180008abc  mov     rcx, rbx; hModule
0x180008abf  call    cs:__imp_GetModuleFileNameW
0x180008ac5  test    eax, eax
0x180008ac7  jnz     short loc_180008AD3
0x180008ac9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008ace  jmp     loc_180008CAE
0x180008ad3  cmp     eax, edi
0x180008ad5  jnz     short loc_180008AE1
0x180008ad7  mov     ebx, 8007007Ah
0x180008adc  jmp     loc_180008CB0
0x180008ae1  lea     r8, [rbp+0A10h+Filename]
0x180008ae5  lea     rax, [rbp+0A10h+Src]
0x180008aec  mov     ecx, r12d
0x180008aef  mov     r10d, 27h ; '''
0x180008af5  mov     r9d, 207h
0x180008afb  movzx   edx, word ptr [r8]
0x180008aff  test    dx, dx
0x180008b02  jz      short loc_180008B2B
0x180008b04  mov     [rax], dx
0x180008b07  add     rax, 2
0x180008b0b  cmp     dx, r10w
0x180008b0f  jnz     short loc_180008B20
0x180008b11  inc     ecx
0x180008b13  cmp     ecx, r9d
0x180008b16  jnb     short loc_180008B20
0x180008b18  mov     [rax], r10w
0x180008b1c  add     rax, 2
0x180008b20  add     r8, 2
0x180008b24  inc     ecx
0x180008b26  cmp     ecx, r9d
0x180008b29  jb      short loc_180008AFB
0x180008b2b  mov     [rax], r12w
0x180008b2f  test    rbx, rbx
0x180008b32  jz      short loc_180008B88
0x180008b34  xor     ecx, ecx; lpModuleName
0x180008b36  call    cs:__imp_GetModuleHandleW
0x180008b3c  cmp     rbx, rax
0x180008b3f  jz      short loc_180008B88
0x180008b41  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180008b46  call    cs:__imp_EnterCriticalSection
0x180008b4c  mov     [rsp+0B10h+var_AE0], r12
0x180008b51  lea     r8, [rbp+0A10h+Src]; wchar_t *
0x180008b58  lea     rdx, aModule; "Module"
0x180008b5f  lea     rcx, [rsp+0B10h+var_AC8]; this
0x180008b64  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180008b69  mov     ebx, eax
0x180008b6b  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180008b70  call    cs:__imp_LeaveCriticalSection
0x180008b76  neg     ebx
0x180008b78  sbb     ebx, ebx
0x180008b7a  not     ebx
0x180008b7c  mov     edi, 8007000Eh
0x180008b81  and     ebx, edi
0x180008b83  jmp     loc_180008C51
0x180008b88  mov     edi, 22h ; '"'
0x180008b8d  mov     [rbp+0A10h+var_870], di
0x180008b94  lea     rcx, [rbp+0A10h+Src]
0x180008b9b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008b9f  mov     rax, rbx
0x180008ba2  inc     rax
0x180008ba5  cmp     [rcx+rax*2], r12w
0x180008baa  jnz     short loc_180008BA2
0x180008bac  inc     eax
0x180008bae  movsxd  r8, eax
0x180008bb1  add     r8, r8; Size
0x180008bb4  jz      short loc_180008BD6
0x180008bb6  cmp     r8, 416h
0x180008bbd  ja      loc_180008C57
0x180008bc3  lea     rdx, [rbp+0A10h+Src]; Src
0x180008bca  lea     rcx, [rbp+0A10h+var_86E]; void *
0x180008bd1  call    memmove
0x180008bd6  lea     rax, [rbp+0A10h+var_870]
0x180008bdd  inc     rbx
0x180008be0  cmp     [rax+rbx*2], r12w
0x180008be5  jnz     short loc_180008BDD
0x180008be7  movsxd  rax, ebx
0x180008bea  mov     [rbp+rax*2+0A10h+var_870], di
0x180008bf2  lea     rax, ds:2[rax*2]
0x180008bfa  cmp     rax, 418h
0x180008c00  jnb     loc_180008D48
0x180008c06  mov     [rbp+rax+0A10h+var_870], r12w
0x180008c0f  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180008c14  call    cs:__imp_EnterCriticalSection
0x180008c1a  mov     [rsp+0B10h+var_AE0], r12
0x180008c1f  lea     r8, [rbp+0A10h+var_870]; wchar_t *
0x180008c26  lea     rdx, aModule; "Module"
0x180008c2d  lea     rcx, [rsp+0B10h+var_AC8]; this
0x180008c32  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180008c37  mov     ebx, eax
0x180008c39  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180008c3e  call    cs:__imp_LeaveCriticalSection
0x180008c44  neg     ebx
0x180008c46  sbb     ebx, ebx
0x180008c48  not     ebx
0x180008c4a  mov     edi, 8007000Eh
0x180008c4f  and     ebx, edi
0x180008c51  test    ebx, ebx
0x180008c53  jns     short loc_180008C6B
0x180008c55  jmp     short loc_180008CB0
0x180008c57  call    _o__errno_0
0x180008c5c  mov     [rax], edi
0x180008c5e  call    _invalid_parameter_noinfo
0x180008c63  nop
0x180008c64  mov     ebx, 80004005h
0x180008c69  jmp     short loc_180008CB0
0x180008c6b  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180008c70  call    cs:__imp_EnterCriticalSection
0x180008c76  mov     [rsp+0B10h+var_AE0], r12
0x180008c7b  lea     r8, [rbp+0A10h+Src]; wchar_t *
0x180008c82  lea     rdx, aModuleRaw; "Module_Raw"
0x180008c89  lea     rcx, [rsp+0B10h+var_AC8]; this
0x180008c8e  call    ?Add@CExpansionVector@ATL@@QEAAHPEB_W0@Z; ATL::CExpansionVector::Add(wchar_t const *,wchar_t const *)
0x180008c93  mov     ebx, eax
0x180008c95  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180008c9a  call    cs:__imp_LeaveCriticalSection
0x180008ca0  mov     ecx, ebx
0x180008ca2  neg     ecx
0x180008ca4  sbb     eax, eax
0x180008ca6  not     eax
0x180008ca8  and     eax, edi
0x180008caa  test    ebx, ebx
0x180008cac  jnz     short loc_180008CDD
0x180008cae  mov     ebx, eax
0x180008cb0  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008cb5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180008cba  mov     eax, ebx
0x180008cbc  mov     rcx, [rbp+0A10h+var_40]
0x180008cc3  xor     rcx, rsp; StackCookie
0x180008cc6  call    __security_check_cookie
0x180008ccb  add     rsp, 0AE0h
0x180008cd2  pop     r15
0x180008cd4  pop     r14
0x180008cd6  pop     r12
0x180008cd8  pop     rdi
0x180008cd9  pop     rsi
0x180008cda  pop     rbx
0x180008cdb  pop     rbp
0x180008cdc  retn
0x180008cdd  mov     [rsp+0B10h+var_AE0], r12
0x180008ce2  test    r15d, r15d
0x180008ce5  jz      short loc_180008D15
0x180008ce7  test    rsi, rsi
0x180008cea  jz      short loc_180008D13
0x180008cec  mov     [rsp+0B10h+var_AF0], 1; int
0x180008cf4  lea     r9, aRegistry; "REGISTRY"
0x180008cfb  mov     r8, rsi; wchar_t *
0x180008cfe  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x180008d02  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008d07  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x180008d0c  mov     ebx, eax
0x180008d0e  jmp     loc_180008C55
0x180008d13  jmp     short loc_180008D3E
0x180008d15  test    rsi, rsi
0x180008d18  jz      short loc_180008D3E
0x180008d1a  mov     [rsp+0B10h+var_AF0], r12d; int
0x180008d1f  lea     r9, aRegistry; "REGISTRY"
0x180008d26  mov     r8, rsi; wchar_t *
0x180008d29  lea     rdx, [rbp+0A10h+Filename]; wchar_t *
0x180008d2d  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180008d32  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z; ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)
0x180008d37  mov     ebx, eax
0x180008d39  jmp     loc_180008C55
0x180008d3e  mov     ebx, 80070057h
0x180008d43  jmp     loc_180008C55
0x180008d48  call    __report_rangecheckfailure
```
