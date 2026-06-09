# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180009a6c`
- end: `0x180009d83`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180009a40`
- `0x18000a0d0`

## callees

- `0x180001a78`
- `0x180007120`
- `0x1800072a8`
- `0x180007bf4`
- `0x18000857c`
- `0x180008e78`
- `0x180009a6c`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009c3e`
- `msvcrt!memcpy_s` at `0x180009c3e`
- `KERNEL32!GetModuleHandleW` at `0x180009be6`
- `KERNEL32!GetModuleHandleW` at `0x180009be6`
- `KERNEL32!LeaveCriticalSection` at `0x180009b28`
- `KERNEL32!LeaveCriticalSection` at `0x180009cb0`
- `KERNEL32!LeaveCriticalSection` at `0x180009cee`
- `KERNEL32!LeaveCriticalSection` at `0x180009b28`
- `KERNEL32!LeaveCriticalSection` at `0x180009cb0`
- `KERNEL32!LeaveCriticalSection` at `0x180009cee`
- `KERNEL32!EnterCriticalSection` at `0x180009b0d`
- `KERNEL32!EnterCriticalSection` at `0x180009bf6`
- `KERNEL32!EnterCriticalSection` at `0x180009c8b`
- `KERNEL32!EnterCriticalSection` at `0x180009ccc`
- `KERNEL32!EnterCriticalSection` at `0x180009b0d`
- `KERNEL32!EnterCriticalSection` at `0x180009bf6`
- `KERNEL32!EnterCriticalSection` at `0x180009c8b`
- `KERNEL32!EnterCriticalSection` at `0x180009ccc`
- `KERNEL32!GetModuleFileNameW` at `0x180009b71`
- `KERNEL32!GetModuleFileNameW` at `0x180009b71`

## string_xrefs

- `0x180009d10`: `REGISTRY`

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
  v8 = ATL::CComCriticalSection::Init(&CriticalSection);
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
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
                  (const WCHAR *)&v25,
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
0x180009a6c  mov     [rsp-8+arg_10], rbx
0x180009a71  push    rbp
0x180009a72  push    rsi
0x180009a73  push    rdi
0x180009a74  push    r12
0x180009a76  push    r13
0x180009a78  push    r14
0x180009a7a  push    r15
0x180009a7c  lea     rbp, [rsp-9D0h]
0x180009a84  sub     rsp, 0AD0h
0x180009a8b  mov     rax, cs:__security_cookie
0x180009a92  xor     rax, rsp
0x180009a95  mov     [rbp+0A00h+var_40], rax
0x180009a9c  xor     r13d, r13d
0x180009a9f  mov     r12d, edx
0x180009aa2  xorps   xmm0, xmm0
0x180009aa5  mov     [rsp+0B00h+var_AC8], r13
0x180009aaa  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180009ab1  mov     [rsp+0B00h+var_AC0], r13
0x180009ab6  mov     [rsp+0B00h+var_AD0], rax
0x180009abb  mov     r14, rcx
0x180009abe  xor     eax, eax
0x180009ac0  mov     [rsp+0B00h+var_AB8], r13d
0x180009ac5  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180009aca  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180009acf  mov     rbx, r9
0x180009ad2  mov     [rsp+0B00h+var_A88], r13b
0x180009ad7  mov     r15d, r8d
0x180009ada  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180009adf  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180009ae4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180009ae9  mov     edi, eax
0x180009aeb  test    eax, eax
0x180009aed  js      loc_180009D47
0x180009af3  mov     [rsp+0B00h+var_A88], 1
0x180009af8  test    rbx, rbx
0x180009afb  jz      short loc_180009B3A
0x180009afd  jmp     short loc_180009B32
0x180009aff  mov     rsi, [rbx+8]
0x180009b03  test    rsi, rsi
0x180009b06  jz      short loc_180009B2E
0x180009b08  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009b0d  call    cs:__imp_EnterCriticalSection
0x180009b13  mov     r8, rsi; unsigned __int16 *
0x180009b16  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180009b1b  mov     rdx, rdi; unsigned __int16 *
0x180009b1e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009b23  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009b28  call    cs:__imp_LeaveCriticalSection
0x180009b2e  add     rbx, 10h
0x180009b32  mov     rdi, [rbx]
0x180009b35  test    rdi, rdi
0x180009b38  jnz     short loc_180009AFF
0x180009b3a  mov     rax, [r14]
0x180009b3d  lea     rdx, [rsp+0B00h+var_AD0]
0x180009b42  mov     rcx, r14
0x180009b45  mov     rax, [rax+28h]
0x180009b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b4e  mov     ebx, eax
0x180009b50  test    eax, eax
0x180009b52  js      loc_180009D39
0x180009b58  mov     rbx, cs:hInstance
0x180009b5f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180009b66  mov     edi, 104h
0x180009b6b  mov     rcx, rbx; hModule
0x180009b6e  mov     r8d, edi; nSize
0x180009b71  call    cs:__imp_GetModuleFileNameW
0x180009b77  test    eax, eax
0x180009b79  jnz     short loc_180009B87
0x180009b7b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009b80  mov     ebx, eax
0x180009b82  jmp     loc_180009D39
0x180009b87  cmp     eax, edi
0x180009b89  jnz     short loc_180009B95
0x180009b8b  mov     ebx, 8007007Ah
0x180009b90  jmp     loc_180009D39
0x180009b95  lea     rdx, [rbp+0A00h+Filename]
0x180009b9c  mov     ecx, r13d
0x180009b9f  mov     r9d, 27h ; '''
0x180009ba5  movzx   r8d, word ptr [rdx]
0x180009ba9  test    r8w, r8w
0x180009bad  jz      short loc_180009BD9
0x180009baf  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180009bb5  cmp     r8w, r9w
0x180009bb9  jnz     short loc_180009BCB
0x180009bbb  cmp     ecx, 206h
0x180009bc1  jnb     short loc_180009BCB
0x180009bc3  inc     ecx
0x180009bc5  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180009bcb  add     rdx, 2
0x180009bcf  inc     ecx
0x180009bd1  cmp     ecx, 207h
0x180009bd7  jb      short loc_180009BA5
0x180009bd9  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180009bdf  test    rbx, rbx
0x180009be2  jz      short loc_180009C05
0x180009be4  xor     ecx, ecx; lpModuleName
0x180009be6  call    cs:__imp_GetModuleHandleW
0x180009bec  cmp     rbx, rax
0x180009bef  jz      short loc_180009C05
0x180009bf1  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009bf6  call    cs:__imp_EnterCriticalSection
0x180009bfc  lea     r8, [rbp+0A00h+Source]
0x180009c00  jmp     loc_180009C98
0x180009c05  mov     edi, 22h ; '"'
0x180009c0a  lea     rcx, [rbp+0A00h+Source]
0x180009c0e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009c12  mov     [rbp+0A00h+var_460], di
0x180009c19  mov     rax, rbx
0x180009c1c  inc     rax
0x180009c1f  cmp     [rcx+rax*2], r13w
0x180009c24  jnz     short loc_180009C1C
0x180009c26  inc     eax
0x180009c28  lea     r8, [rbp+0A00h+Source]; Source
0x180009c2c  movsxd  r9, eax
0x180009c2f  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180009c36  add     r9, r9; SourceSize
0x180009c39  mov     edx, 414h; DestinationSize
0x180009c3e  call    cs:__imp_memcpy_s
0x180009c44  test    eax, eax
0x180009c46  jnz     loc_180009D34
0x180009c4c  lea     rax, [rbp+0A00h+var_460]
0x180009c53  inc     rbx
0x180009c56  cmp     [rax+rbx*2], r13w
0x180009c5b  jnz     short loc_180009C53
0x180009c5d  movsxd  rax, ebx
0x180009c60  lea     rcx, ds:2[rax*2]
0x180009c68  mov     [rbp+rax*2+0A00h+var_460], di
0x180009c70  cmp     rcx, 418h
0x180009c77  jnb     loc_180009D7D
0x180009c7d  mov     [rbp+rcx+0A00h+var_460], r13w
0x180009c86  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009c8b  call    cs:__imp_EnterCriticalSection
0x180009c91  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180009c98  lea     rdx, aModule; "Module"
0x180009c9f  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180009ca4  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009ca9  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009cae  mov     ebx, eax
0x180009cb0  call    cs:__imp_LeaveCriticalSection
0x180009cb6  neg     ebx
0x180009cb8  mov     edi, 8007000Eh
0x180009cbd  sbb     ebx, ebx
0x180009cbf  not     ebx
0x180009cc1  and     ebx, edi
0x180009cc3  test    ebx, ebx
0x180009cc5  js      short loc_180009D39
0x180009cc7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009ccc  call    cs:__imp_EnterCriticalSection
0x180009cd2  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x180009cd6  lea     rdx, aModuleRaw; "Module_Raw"
0x180009cdd  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180009ce2  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009ce7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009cec  mov     ebx, eax
0x180009cee  call    cs:__imp_LeaveCriticalSection
0x180009cf4  mov     ecx, ebx
0x180009cf6  neg     ecx
0x180009cf8  sbb     eax, eax
0x180009cfa  not     eax
0x180009cfc  and     eax, edi
0x180009cfe  test    ebx, ebx
0x180009d00  jz      loc_180009B80
0x180009d06  mov     eax, r13d
0x180009d09  movzx   r8d, r12w; unsigned __int16 *
0x180009d0d  test    r15d, r15d
0x180009d10  lea     r9, aRegistry; "REGISTRY"
0x180009d17  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180009d1e  setnz   al
0x180009d21  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180009d26  mov     [rsp+0B00h+var_AE0], eax; int
0x180009d2a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180009d2f  jmp     loc_180009B80
0x180009d34  mov     ebx, 80004005h
0x180009d39  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180009d3e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009d43  mov     eax, ebx
0x180009d45  jmp     short loc_180009D53
0x180009d47  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180009d4c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180009d51  mov     eax, edi
0x180009d53  mov     rcx, [rbp+0A00h+var_40]
0x180009d5a  xor     rcx, rsp; StackCookie
0x180009d5d  call    __security_check_cookie
0x180009d62  mov     rbx, [rsp+0B00h+arg_10]
0x180009d6a  add     rsp, 0AD0h
0x180009d71  pop     r15
0x180009d73  pop     r14
0x180009d75  pop     r13
0x180009d77  pop     r12
0x180009d79  pop     rdi
0x180009d7a  pop     rsi
0x180009d7b  pop     rbp
0x180009d7c  retn
0x180009d7d  call    __report_rangecheckfailure
```
