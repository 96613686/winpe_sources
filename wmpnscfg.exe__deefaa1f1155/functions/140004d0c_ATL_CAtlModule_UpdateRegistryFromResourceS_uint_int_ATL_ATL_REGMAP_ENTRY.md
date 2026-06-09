# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140004d0c`
- end: `0x14000502c`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140005380`

## callees

- `0x1400014f0`
- `0x1400017a0`
- `0x140001e22`
- `0x140002228`
- `0x14000259c`
- `0x140002fc8`
- `0x1400034ec`
- `0x140003fac`
- `0x140004d0c`
- `0x1400075dc`
- `0x140008010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004fb1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004fb1`
- `KERNEL32!EnterCriticalSection` at `0x140004dad`
- `KERNEL32!EnterCriticalSection` at `0x140004e94`
- `KERNEL32!EnterCriticalSection` at `0x140004f2a`
- `KERNEL32!EnterCriticalSection` at `0x140004f6b`
- `KERNEL32!EnterCriticalSection` at `0x140004dad`
- `KERNEL32!EnterCriticalSection` at `0x140004e94`
- `KERNEL32!EnterCriticalSection` at `0x140004f2a`
- `KERNEL32!EnterCriticalSection` at `0x140004f6b`
- `KERNEL32!LeaveCriticalSection` at `0x140004dc8`
- `KERNEL32!LeaveCriticalSection` at `0x140004f4f`
- `KERNEL32!LeaveCriticalSection` at `0x140004f8d`
- `KERNEL32!LeaveCriticalSection` at `0x140004dc8`
- `KERNEL32!LeaveCriticalSection` at `0x140004f4f`
- `KERNEL32!LeaveCriticalSection` at `0x140004f8d`
- `KERNEL32!GetModuleHandleW` at `0x140004e84`
- `KERNEL32!GetModuleHandleW` at `0x140004e84`
- `KERNEL32!GetModuleFileNameW` at `0x140004e11`
- `KERNEL32!GetModuleFileNameW` at `0x140004e11`

## string_xrefs

- `0x140004fd6`: `REGISTRY`

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

  v27 = &ATL::CRegObject::`vftable';
  v28[0] = 0;
  v28[1] = 0;
  v29 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v31 = 0;
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
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
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
                    (ATL::CRegObject *)&v27,
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
0x140004d0c  mov     [rsp-8+arg_10], rbx
0x140004d11  push    rbp
0x140004d12  push    rsi
0x140004d13  push    rdi
0x140004d14  push    r12
0x140004d16  push    r13
0x140004d18  push    r14
0x140004d1a  push    r15
0x140004d1c  lea     rbp, [rsp-9D0h]
0x140004d24  sub     rsp, 0AD0h
0x140004d2b  mov     rax, cs:__security_cookie
0x140004d32  xor     rax, rsp
0x140004d35  mov     [rbp+0A00h+var_40], rax
0x140004d3c  mov     rbx, r9
0x140004d3f  mov     r15d, r8d
0x140004d42  mov     r12d, edx
0x140004d45  mov     r14, rcx
0x140004d48  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140004d4f  mov     [rsp+0B00h+var_AD0], rax
0x140004d54  xor     r13d, r13d
0x140004d57  mov     [rsp+0B00h+var_AC8], r13
0x140004d5c  mov     [rsp+0B00h+var_AC0], r13
0x140004d61  mov     [rsp+0B00h+var_AB8], r13d
0x140004d66  xorps   xmm0, xmm0
0x140004d69  xor     eax, eax
0x140004d6b  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x140004d70  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x140004d75  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x140004d7a  mov     [rsp+0B00h+var_A88], r13b
0x140004d7f  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x140004d84  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140004d89  mov     edi, eax
0x140004d8b  test    eax, eax
0x140004d8d  js      loc_140004FF0
0x140004d93  mov     [rsp+0B00h+var_A88], 1
0x140004d98  test    rbx, rbx
0x140004d9b  jz      short loc_140004DDA
0x140004d9d  jmp     short loc_140004DD2
0x140004d9f  mov     rsi, [rbx+8]
0x140004da3  test    rsi, rsi
0x140004da6  jz      short loc_140004DCE
0x140004da8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140004dad  call    cs:__imp_EnterCriticalSection
0x140004db3  mov     r8, rsi; unsigned __int16 *
0x140004db6  mov     rdx, rdi; unsigned __int16 *
0x140004db9  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140004dbe  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140004dc3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140004dc8  call    cs:__imp_LeaveCriticalSection
0x140004dce  add     rbx, 10h
0x140004dd2  mov     rdi, [rbx]
0x140004dd5  test    rdi, rdi
0x140004dd8  jnz     short loc_140004D9F
0x140004dda  mov     rax, [r14]
0x140004ddd  lea     rdx, [rsp+0B00h+var_AD0]
0x140004de2  mov     rcx, r14
0x140004de5  mov     rax, [rax+28h]
0x140004de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004dee  mov     ebx, eax
0x140004df0  test    eax, eax
0x140004df2  js      loc_140004FA3
0x140004df8  mov     rbx, cs:hInstance
0x140004dff  mov     edi, 104h
0x140004e04  mov     r8d, edi; nSize
0x140004e07  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x140004e0e  mov     rcx, rbx; hModule
0x140004e11  call    cs:__imp_GetModuleFileNameW
0x140004e17  test    eax, eax
0x140004e19  jnz     short loc_140004E25
0x140004e1b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140004e20  jmp     loc_140004FA1
0x140004e25  cmp     eax, edi
0x140004e27  jnz     short loc_140004E33
0x140004e29  mov     ebx, 8007007Ah
0x140004e2e  jmp     loc_140004FA3
0x140004e33  lea     rdx, [rbp+0A00h+Filename]
0x140004e3a  mov     ecx, r13d
0x140004e3d  mov     r9d, 27h ; '''
0x140004e43  movzx   r8d, word ptr [rdx]
0x140004e47  test    r8w, r8w
0x140004e4b  jz      short loc_140004E77
0x140004e4d  mov     [rbp+rcx*2+0A00h+Src], r8w
0x140004e53  cmp     r8w, r9w
0x140004e57  jnz     short loc_140004E69
0x140004e59  cmp     ecx, 206h
0x140004e5f  jnb     short loc_140004E69
0x140004e61  inc     ecx
0x140004e63  mov     [rbp+rcx*2+0A00h+Src], r9w
0x140004e69  add     rdx, 2
0x140004e6d  inc     ecx
0x140004e6f  cmp     ecx, 207h
0x140004e75  jb      short loc_140004E43
0x140004e77  mov     [rbp+rcx*2+0A00h+Src], r13w
0x140004e7d  test    rbx, rbx
0x140004e80  jz      short loc_140004EA3
0x140004e82  xor     ecx, ecx; lpModuleName
0x140004e84  call    cs:__imp_GetModuleHandleW
0x140004e8a  cmp     rbx, rax
0x140004e8d  jz      short loc_140004EA3
0x140004e8f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140004e94  call    cs:__imp_EnterCriticalSection
0x140004e9a  lea     r8, [rbp+0A00h+Src]
0x140004e9e  jmp     loc_140004F37
0x140004ea3  mov     edi, 22h ; '"'
0x140004ea8  mov     [rbp+0A00h+var_460], di
0x140004eaf  lea     rcx, [rbp+0A00h+Src]
0x140004eb3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004eb7  mov     rax, rbx
0x140004eba  inc     rax
0x140004ebd  cmp     [rcx+rax*2], r13w
0x140004ec2  jnz     short loc_140004EBA
0x140004ec4  inc     eax
0x140004ec6  movsxd  r8, eax
0x140004ec9  add     r8, r8; Size
0x140004ecc  jz      short loc_140004EEB
0x140004ece  cmp     r8, 414h
0x140004ed5  ja      loc_140004FB1
0x140004edb  lea     rdx, [rbp+0A00h+Src]; Src
0x140004edf  lea     rcx, [rbp+0A00h+var_45E]; void *
0x140004ee6  call    memcpy_0
0x140004eeb  lea     rax, [rbp+0A00h+var_460]
0x140004ef2  inc     rbx
0x140004ef5  cmp     [rax+rbx*2], r13w
0x140004efa  jnz     short loc_140004EF2
0x140004efc  movsxd  rax, ebx
0x140004eff  mov     [rbp+rax*2+0A00h+var_460], di
0x140004f07  lea     rcx, ds:2[rax*2]
0x140004f0f  cmp     rcx, 418h
0x140004f16  jnb     loc_140005026
0x140004f1c  mov     [rbp+rcx+0A00h+var_460], r13w
0x140004f25  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140004f2a  call    cs:__imp_EnterCriticalSection
0x140004f30  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x140004f37  lea     rdx, aModule; "Module"
0x140004f3e  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140004f43  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140004f48  mov     ebx, eax
0x140004f4a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140004f4f  call    cs:__imp_LeaveCriticalSection
0x140004f55  neg     ebx
0x140004f57  sbb     ebx, ebx
0x140004f59  mov     edi, 8007000Eh
0x140004f5e  not     ebx
0x140004f60  and     ebx, edi
0x140004f62  test    ebx, ebx
0x140004f64  js      short loc_140004FA3
0x140004f66  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140004f6b  call    cs:__imp_EnterCriticalSection
0x140004f71  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x140004f75  lea     rdx, aModuleRaw; "Module_Raw"
0x140004f7c  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140004f81  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140004f86  mov     ebx, eax
0x140004f88  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140004f8d  call    cs:__imp_LeaveCriticalSection
0x140004f93  mov     ecx, ebx
0x140004f95  neg     ecx
0x140004f97  sbb     eax, eax
0x140004f99  not     eax
0x140004f9b  and     eax, edi
0x140004f9d  test    ebx, ebx
0x140004f9f  jnz     short loc_140004FC5
0x140004fa1  mov     ebx, eax
0x140004fa3  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140004fa8  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140004fad  mov     eax, ebx
0x140004faf  jmp     short loc_140004FFC
0x140004fb1  call    cs:__imp__o__errno
0x140004fb7  mov     [rax], edi
0x140004fb9  call    _invalid_parameter_noinfo
0x140004fbe  mov     ebx, 80004005h
0x140004fc3  jmp     short loc_140004FA3
0x140004fc5  mov     eax, r13d
0x140004fc8  test    r15d, r15d
0x140004fcb  setnz   al
0x140004fce  movzx   r8d, r12w; unsigned __int16 *
0x140004fd2  mov     [rsp+0B00h+var_AE0], eax; int
0x140004fd6  lea     r9, aRegistry; "REGISTRY"
0x140004fdd  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x140004fe4  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140004fe9  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x140004fee  jmp     short loc_140004FA1
0x140004ff0  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140004ff5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140004ffa  mov     eax, edi
0x140004ffc  mov     rcx, [rbp+0A00h+var_40]
0x140005003  xor     rcx, rsp; StackCookie
0x140005006  call    __security_check_cookie
0x14000500b  mov     rbx, [rsp+0B00h+arg_10]
0x140005013  add     rsp, 0AD0h
0x14000501a  pop     r15
0x14000501c  pop     r14
0x14000501e  pop     r13
0x140005020  pop     r12
0x140005022  pop     rdi
0x140005023  pop     rsi
0x140005024  pop     rbp
0x140005025  retn
0x140005026  call    __report_rangecheckfailure
```
