# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000ce24`
- end: `0x18000d150`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `812`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ce10`
- `0x1800117f0`
- `0x180011910`

## callees

- `0x180001a68`
- `0x180002eb8`
- `0x180003814`
- `0x180003ad0`
- `0x1800041b8`
- `0x180008180`
- `0x18000b518`
- `0x18000ce24`
- `0x180012db0`
- `0x180014010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000cff0`
- `msvcrt!memcpy_s` at `0x18000cff0`
- `KERNEL32!GetModuleHandleW` at `0x18000cf83`
- `KERNEL32!GetModuleHandleW` at `0x18000cf83`
- `KERNEL32!LeaveCriticalSection` at `0x18000d06e`
- `KERNEL32!LeaveCriticalSection` at `0x18000d0bf`
- `KERNEL32!LeaveCriticalSection` at `0x18000d06e`
- `KERNEL32!LeaveCriticalSection` at `0x18000d0bf`
- `KERNEL32!EnterCriticalSection` at `0x18000cf99`
- `KERNEL32!EnterCriticalSection` at `0x18000d043`
- `KERNEL32!EnterCriticalSection` at `0x18000d094`
- `KERNEL32!EnterCriticalSection` at `0x18000cf99`
- `KERNEL32!EnterCriticalSection` at `0x18000d043`
- `KERNEL32!EnterCriticalSection` at `0x18000d094`
- `KERNEL32!GetModuleFileNameW` at `0x18000cf02`
- `KERNEL32!GetModuleFileNameW` at `0x18000cf02`

## string_xrefs

- `0x18000d0dd`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v4; // rsi
  int v7; // edi
  signed int v8; // ebx
  HMODULE v9; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v12; // rdx
  __int64 v13; // rcx
  unsigned __int16 v14; // r8
  unsigned __int16 *v15; // r8
  __int64 v16; // rbx
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  int v19; // ebx
  int v20; // ebx
  const unsigned __int16 *v21; // r8
  void **v23; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v25; // [rsp+48h] [rbp-B8h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
  char v27; // [rsp+78h] [rbp-88h]
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 Source[520]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v30; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE Destination[1054]; // [rsp+6A2h] [rbp+5A2h] BYREF

  v4 = ATL::_pAtlModule;
  v23 = &ATL::CRegObject::`vftable';
  v24[0] = 0;
  v24[1] = 0;
  v25 = 0;
  v27 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v7 >= 0 )
  {
    v27 = 1;
    if ( a4 )
    {
      while ( *(_QWORD *)a4 )
      {
        ATL::CRegObject::AddReplacement(
          (ATL::CRegObject *)&v23,
          *(const unsigned __int16 **)a4,
          *((const unsigned __int16 **)a4 + 1));
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v8 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v4 + 40LL))(v4, &v23);
    if ( v8 < 0 )
      goto LABEL_34;
    v9 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW )
    {
      if ( ModuleFileNameW == 260 )
      {
        v8 = -2147024774;
        goto LABEL_34;
      }
      v12 = Filename;
      v13 = 0;
      do
      {
        v14 = *v12;
        if ( !*v12 )
          break;
        Source[v13] = v14;
        if ( v14 == 39 && (unsigned int)v13 < 0x206 )
        {
          LODWORD(v13) = v13 + 1;
          Source[(unsigned int)v13] = 39;
        }
        ++v12;
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < 0x207 );
      Source[v13] = 0;
      if ( !v9 || v9 == GetModuleHandleW(0) )
      {
        v16 = -1;
        v30 = 34;
        v17 = -1;
        do
          ++v17;
        while ( Source[v17] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v17 + 1)) )
        {
          v8 = -2147467259;
          goto LABEL_34;
        }
        do
          ++v16;
        while ( *(_WORD *)&Destination[2 * v16 - 2] );
        v18 = 2LL * (int)v16 + 2;
        *(_WORD *)&Destination[2 * (int)v16 - 2] = 34;
        if ( v18 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v18 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v15 = &v30;
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v15 = Source;
      }
      v19 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v24, L"Module", v15);
      LeaveCriticalSection(&CriticalSection);
      v8 = v19 == 0 ? 0x8007000E : 0;
      if ( v8 < 0 )
      {
LABEL_34:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v23);
        return (unsigned int)v8;
      }
      EnterCriticalSection(&CriticalSection);
      v20 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v24, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v20 == 0 ? 0x8007000E : 0;
      if ( v20 )
      {
        if ( a3 )
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v23, Filename, v21, L"REGISTRY", 1);
        else
          Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v23, Filename, v21, L"REGISTRY", 0);
      }
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v8 = Error;
    goto LABEL_34;
  }
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v23);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ce24  push    rbp
0x18000ce26  push    rbx
0x18000ce27  push    rsi
0x18000ce28  push    rdi
0x18000ce29  push    r14
0x18000ce2b  push    r15
0x18000ce2d  lea     rbp, [rsp-9D8h]
0x18000ce35  sub     rsp, 0AD8h
0x18000ce3c  mov     rax, cs:__security_cookie
0x18000ce43  xor     rax, rsp
0x18000ce46  mov     [rbp+0A00h+var_40], rax
0x18000ce4d  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ce54  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000ce5b  xor     r15d, r15d
0x18000ce5e  mov     [rsp+0B00h+var_AD0], rax
0x18000ce63  xorps   xmm0, xmm0
0x18000ce66  mov     [rsp+0B00h+var_AC8], r15
0x18000ce6b  xor     eax, eax
0x18000ce6d  mov     [rsp+0B00h+var_AC0], r15
0x18000ce72  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000ce77  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000ce7c  mov     rbx, r9
0x18000ce7f  mov     [rsp+0B00h+var_AB8], r15d
0x18000ce84  mov     r14d, r8d
0x18000ce87  mov     [rsp+0B00h+var_A88], r15b
0x18000ce8c  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000ce91  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000ce96  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000ce9b  mov     edi, eax
0x18000ce9d  test    eax, eax
0x18000ce9f  js      loc_18000D11E
0x18000cea5  mov     [rsp+0B00h+var_A88], 1
0x18000ceaa  test    rbx, rbx
0x18000cead  jz      short loc_18000CECE
0x18000ceaf  jmp     short loc_18000CEC6
0x18000ceb1  mov     r8, [rbx+8]; unsigned __int16 *
0x18000ceb5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000ceba  mov     rdx, rax; unsigned __int16 *
0x18000cebd  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18000cec2  lea     rbx, [rbx+10h]
0x18000cec6  mov     rax, [rbx]
0x18000cec9  test    rax, rax
0x18000cecc  jnz     short loc_18000CEB1
0x18000cece  mov     rax, [rsi]
0x18000ced1  lea     rdx, [rsp+0B00h+var_AD0]
0x18000ced6  mov     rcx, rsi
0x18000ced9  mov     rax, [rax+28h]
0x18000cedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee2  mov     ebx, eax
0x18000cee4  test    eax, eax
0x18000cee6  js      loc_18000D110
0x18000ceec  mov     rbx, cs:hModule
0x18000cef3  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000cef7  mov     edi, 104h
0x18000cefc  mov     rcx, rbx; hModule
0x18000ceff  mov     r8d, edi; nSize
0x18000cf02  call    cs:__imp_GetModuleFileNameW
0x18000cf09  nop     dword ptr [rax+rax+00h]
0x18000cf0e  test    eax, eax
0x18000cf10  jnz     short loc_18000CF1E
0x18000cf12  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000cf17  mov     ebx, eax
0x18000cf19  jmp     loc_18000D110
0x18000cf1e  cmp     eax, edi
0x18000cf20  jnz     short loc_18000CF2C
0x18000cf22  mov     ebx, 8007007Ah
0x18000cf27  jmp     loc_18000D110
0x18000cf2c  lea     rdx, [rbp+0A00h+Filename]
0x18000cf30  mov     ecx, r15d
0x18000cf33  mov     r9d, 27h ; '''
0x18000cf39  movzx   r8d, word ptr [rdx]
0x18000cf3d  test    r8w, r8w
0x18000cf41  jz      short loc_18000CF73
0x18000cf43  mov     [rbp+rcx*2+0A00h+Source], r8w
0x18000cf4c  cmp     r8w, r9w
0x18000cf50  jnz     short loc_18000CF65
0x18000cf52  cmp     ecx, 206h
0x18000cf58  jnb     short loc_18000CF65
0x18000cf5a  inc     ecx
0x18000cf5c  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000cf65  add     rdx, 2
0x18000cf69  inc     ecx
0x18000cf6b  cmp     ecx, 207h
0x18000cf71  jb      short loc_18000CF39
0x18000cf73  mov     [rbp+rcx*2+0A00h+Source], r15w
0x18000cf7c  test    rbx, rbx
0x18000cf7f  jz      short loc_18000CFB1
0x18000cf81  xor     ecx, ecx; lpModuleName
0x18000cf83  call    cs:__imp_GetModuleHandleW
0x18000cf8a  nop     dword ptr [rax+rax+00h]
0x18000cf8f  cmp     rbx, rax
0x18000cf92  jz      short loc_18000CFB1
0x18000cf94  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000cf99  call    cs:__imp_EnterCriticalSection
0x18000cfa0  nop     dword ptr [rax+rax+00h]
0x18000cfa5  lea     r8, [rbp+0A00h+Source]
0x18000cfac  jmp     loc_18000D056
0x18000cfb1  mov     edi, 22h ; '"'
0x18000cfb6  lea     rcx, [rbp+0A00h+Source]
0x18000cfbd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000cfc1  mov     [rbp+0A00h+var_460], di
0x18000cfc8  mov     rax, rbx
0x18000cfcb  inc     rax
0x18000cfce  cmp     [rcx+rax*2], r15w
0x18000cfd3  jnz     short loc_18000CFCB
0x18000cfd5  inc     eax
0x18000cfd7  lea     r8, [rbp+0A00h+Source]; Source
0x18000cfde  movsxd  r9, eax
0x18000cfe1  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000cfe8  add     r9, r9; SourceSize
0x18000cfeb  mov     edx, 414h; DestinationSize
0x18000cff0  call    cs:__imp_memcpy_s
0x18000cff7  nop     dword ptr [rax+rax+00h]
0x18000cffc  test    eax, eax
0x18000cffe  jnz     loc_18000D10B
0x18000d004  lea     rax, [rbp+0A00h+var_460]
0x18000d00b  inc     rbx
0x18000d00e  cmp     [rax+rbx*2], r15w
0x18000d013  jnz     short loc_18000D00B
0x18000d015  movsxd  rax, ebx
0x18000d018  lea     rcx, ds:2[rax*2]
0x18000d020  mov     [rbp+rax*2+0A00h+var_460], di
0x18000d028  cmp     rcx, 418h
0x18000d02f  jnb     loc_18000D14A
0x18000d035  mov     [rbp+rcx+0A00h+var_460], r15w
0x18000d03e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000d043  call    cs:__imp_EnterCriticalSection
0x18000d04a  nop     dword ptr [rax+rax+00h]
0x18000d04f  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000d056  lea     rdx, aModule; "Module"
0x18000d05d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000d062  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000d067  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000d06c  mov     ebx, eax
0x18000d06e  call    cs:__imp_LeaveCriticalSection
0x18000d075  nop     dword ptr [rax+rax+00h]
0x18000d07a  neg     ebx
0x18000d07c  mov     edi, 8007000Eh
0x18000d081  sbb     ebx, ebx
0x18000d083  not     ebx
0x18000d085  and     ebx, edi
0x18000d087  test    ebx, ebx
0x18000d089  js      loc_18000D110
0x18000d08f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000d094  call    cs:__imp_EnterCriticalSection
0x18000d09b  nop     dword ptr [rax+rax+00h]
0x18000d0a0  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x18000d0a7  lea     rdx, aModuleRaw; "Module_Raw"
0x18000d0ae  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000d0b3  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000d0b8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000d0bd  mov     ebx, eax
0x18000d0bf  call    cs:__imp_LeaveCriticalSection
0x18000d0c6  nop     dword ptr [rax+rax+00h]
0x18000d0cb  mov     ecx, ebx
0x18000d0cd  neg     ecx
0x18000d0cf  sbb     eax, eax
0x18000d0d1  not     eax
0x18000d0d3  and     eax, edi
0x18000d0d5  test    ebx, ebx
0x18000d0d7  jz      loc_18000CF17
0x18000d0dd  lea     r9, aRegistry; "REGISTRY"
0x18000d0e4  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000d0e8  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000d0ed  test    r14d, r14d
0x18000d0f0  jz      short loc_18000D0FC
0x18000d0f2  mov     [rsp+0B00h+var_AE0], 1
0x18000d0fa  jmp     short loc_18000D101
0x18000d0fc  mov     [rsp+0B00h+var_AE0], r15d; int
0x18000d101  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000d106  jmp     loc_18000CF17
0x18000d10b  mov     ebx, 80004005h
0x18000d110  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000d115  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000d11a  mov     eax, ebx
0x18000d11c  jmp     short loc_18000D12A
0x18000d11e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000d123  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000d128  mov     eax, edi
0x18000d12a  mov     rcx, [rbp+0A00h+var_40]
0x18000d131  xor     rcx, rsp; StackCookie
0x18000d134  call    __security_check_cookie
0x18000d139  add     rsp, 0AD8h
0x18000d140  pop     r15
0x18000d142  pop     r14
0x18000d144  pop     rdi
0x18000d145  pop     rsi
0x18000d146  pop     rbx
0x18000d147  pop     rbp
0x18000d148  retn
0x18000d14a  call    __report_rangecheckfailure
```
