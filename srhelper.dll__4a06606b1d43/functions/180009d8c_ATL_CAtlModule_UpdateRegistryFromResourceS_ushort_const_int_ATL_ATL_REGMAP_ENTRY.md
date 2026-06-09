# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180009d8c`
- end: `0x18000a0ca`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a0e0`

## callees

- `0x180001a78`
- `0x180007120`
- `0x1800072a8`
- `0x180007bf4`
- `0x18000857c`
- `0x180008e78`
- `0x180009d8c`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009f6a`
- `msvcrt!memcpy_s` at `0x180009f6a`
- `KERNEL32!GetModuleHandleW` at `0x180009f09`
- `KERNEL32!GetModuleHandleW` at `0x180009f09`
- `KERNEL32!LeaveCriticalSection` at `0x180009e48`
- `KERNEL32!LeaveCriticalSection` at `0x180009fdc`
- `KERNEL32!LeaveCriticalSection` at `0x18000a021`
- `KERNEL32!LeaveCriticalSection` at `0x180009e48`
- `KERNEL32!LeaveCriticalSection` at `0x180009fdc`
- `KERNEL32!LeaveCriticalSection` at `0x18000a021`
- `KERNEL32!EnterCriticalSection` at `0x180009e2d`
- `KERNEL32!EnterCriticalSection` at `0x180009f19`
- `KERNEL32!EnterCriticalSection` at `0x180009fb7`
- `KERNEL32!EnterCriticalSection` at `0x180009ffc`
- `KERNEL32!EnterCriticalSection` at `0x180009e2d`
- `KERNEL32!EnterCriticalSection` at `0x180009f19`
- `KERNEL32!EnterCriticalSection` at `0x180009fb7`
- `KERNEL32!EnterCriticalSection` at `0x180009ffc`
- `KERNEL32!GetModuleFileNameW` at `0x180009e8e`
- `KERNEL32!GetModuleFileNameW` at `0x180009e8e`

## string_xrefs

- `0x18000a057`: `REGISTRY`

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
      goto LABEL_39;
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
            Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v25, Filename, a2, L"REGISTRY", 1);
            goto LABEL_11;
          }
        }
        else if ( a2 )
        {
          Error = ATL::CRegObject::RegisterFromResource((const WCHAR *)&v25, Filename, a2, L"REGISTRY", 0);
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
0x180009d8c  mov     [rsp-8+arg_10], rbx
0x180009d91  push    rbp
0x180009d92  push    rsi
0x180009d93  push    rdi
0x180009d94  push    r12
0x180009d96  push    r13
0x180009d98  push    r14
0x180009d9a  push    r15
0x180009d9c  lea     rbp, [rsp-9D0h]
0x180009da4  sub     rsp, 0AD0h
0x180009dab  mov     rax, cs:__security_cookie
0x180009db2  xor     rax, rsp
0x180009db5  mov     [rbp+0A00h+var_40], rax
0x180009dbc  xor     r13d, r13d
0x180009dbf  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180009dc6  xorps   xmm0, xmm0
0x180009dc9  mov     [rsp+0B00h+var_AD0], rax
0x180009dce  xor     eax, eax
0x180009dd0  mov     [rsp+0B00h+var_AC8], r13
0x180009dd5  mov     r15, rcx
0x180009dd8  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180009ddd  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x180009de2  mov     [rsp+0B00h+var_AC0], r13
0x180009de7  mov     rbx, r9
0x180009dea  mov     [rsp+0B00h+var_AB8], r13d
0x180009def  mov     r12d, r8d
0x180009df2  mov     [rsp+0B00h+var_A88], r13b
0x180009df7  mov     r14, rdx
0x180009dfa  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180009dff  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x180009e04  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180009e09  mov     edi, eax
0x180009e0b  test    eax, eax
0x180009e0d  js      loc_18000A08E
0x180009e13  mov     [rsp+0B00h+var_A88], 1
0x180009e18  test    rbx, rbx
0x180009e1b  jz      short loc_180009E5A
0x180009e1d  jmp     short loc_180009E52
0x180009e1f  mov     rsi, [rbx+8]
0x180009e23  test    rsi, rsi
0x180009e26  jz      short loc_180009E4E
0x180009e28  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009e2d  call    cs:__imp_EnterCriticalSection
0x180009e33  mov     r8, rsi; unsigned __int16 *
0x180009e36  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180009e3b  mov     rdx, rdi; unsigned __int16 *
0x180009e3e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009e43  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009e48  call    cs:__imp_LeaveCriticalSection
0x180009e4e  add     rbx, 10h
0x180009e52  mov     rdi, [rbx]
0x180009e55  test    rdi, rdi
0x180009e58  jnz     short loc_180009E1F
0x180009e5a  mov     rax, [r15]
0x180009e5d  lea     rdx, [rsp+0B00h+var_AD0]
0x180009e62  mov     rcx, r15
0x180009e65  mov     rax, [rax+28h]
0x180009e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e6e  mov     ebx, eax
0x180009e70  test    eax, eax
0x180009e72  js      loc_18000A080
0x180009e78  mov     rbx, cs:hInstance
0x180009e7f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180009e83  mov     edi, 104h
0x180009e88  mov     rcx, rbx; hModule
0x180009e8b  mov     r8d, edi; nSize
0x180009e8e  call    cs:__imp_GetModuleFileNameW
0x180009e94  test    eax, eax
0x180009e96  jnz     short loc_180009EA4
0x180009e98  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009e9d  mov     ebx, eax
0x180009e9f  jmp     loc_18000A080
0x180009ea4  cmp     eax, edi
0x180009ea6  jnz     short loc_180009EB2
0x180009ea8  mov     ebx, 8007007Ah
0x180009ead  jmp     loc_18000A080
0x180009eb2  lea     rdx, [rbp+0A00h+Filename]
0x180009eb6  mov     ecx, r13d
0x180009eb9  mov     r9d, 27h ; '''
0x180009ebf  movzx   r8d, word ptr [rdx]
0x180009ec3  test    r8w, r8w
0x180009ec7  jz      short loc_180009EF9
0x180009ec9  mov     [rbp+rcx*2+0A00h+Source], r8w
0x180009ed2  cmp     r8w, r9w
0x180009ed6  jnz     short loc_180009EEB
0x180009ed8  cmp     ecx, 206h
0x180009ede  jnb     short loc_180009EEB
0x180009ee0  inc     ecx
0x180009ee2  mov     [rbp+rcx*2+0A00h+Source], r9w
0x180009eeb  add     rdx, 2
0x180009eef  inc     ecx
0x180009ef1  cmp     ecx, 207h
0x180009ef7  jb      short loc_180009EBF
0x180009ef9  mov     [rbp+rcx*2+0A00h+Source], r13w
0x180009f02  test    rbx, rbx
0x180009f05  jz      short loc_180009F2B
0x180009f07  xor     ecx, ecx; lpModuleName
0x180009f09  call    cs:__imp_GetModuleHandleW
0x180009f0f  cmp     rbx, rax
0x180009f12  jz      short loc_180009F2B
0x180009f14  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009f19  call    cs:__imp_EnterCriticalSection
0x180009f1f  lea     r8, [rbp+0A00h+Source]
0x180009f26  jmp     loc_180009FC4
0x180009f2b  mov     edi, 22h ; '"'
0x180009f30  lea     rcx, [rbp+0A00h+Source]
0x180009f37  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009f3b  mov     [rbp+0A00h+var_460], di
0x180009f42  mov     rax, rbx
0x180009f45  inc     rax
0x180009f48  cmp     [rcx+rax*2], r13w
0x180009f4d  jnz     short loc_180009F45
0x180009f4f  inc     eax
0x180009f51  lea     r8, [rbp+0A00h+Source]; Source
0x180009f58  movsxd  r9, eax
0x180009f5b  lea     rcx, [rbp+0A00h+Destination]; Destination
0x180009f62  add     r9, r9; SourceSize
0x180009f65  mov     edx, 414h; DestinationSize
0x180009f6a  call    cs:__imp_memcpy_s
0x180009f70  test    eax, eax
0x180009f72  jnz     loc_18000A07B
0x180009f78  lea     rax, [rbp+0A00h+var_460]
0x180009f7f  inc     rbx
0x180009f82  cmp     [rax+rbx*2], r13w
0x180009f87  jnz     short loc_180009F7F
0x180009f89  movsxd  rax, ebx
0x180009f8c  lea     rcx, ds:2[rax*2]
0x180009f94  mov     [rbp+rax*2+0A00h+var_460], di
0x180009f9c  cmp     rcx, 418h
0x180009fa3  jnb     loc_18000A0C4
0x180009fa9  mov     [rbp+rcx+0A00h+var_460], r13w
0x180009fb2  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009fb7  call    cs:__imp_EnterCriticalSection
0x180009fbd  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x180009fc4  lea     rdx, aModule; "Module"
0x180009fcb  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180009fd0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180009fd5  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009fda  mov     ebx, eax
0x180009fdc  call    cs:__imp_LeaveCriticalSection
0x180009fe2  neg     ebx
0x180009fe4  mov     edi, 8007000Eh
0x180009fe9  sbb     ebx, ebx
0x180009feb  not     ebx
0x180009fed  and     ebx, edi
0x180009fef  test    ebx, ebx
0x180009ff1  js      loc_18000A080
0x180009ff7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180009ffc  call    cs:__imp_EnterCriticalSection
0x18000a002  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x18000a009  lea     rdx, aModuleRaw; "Module_Raw"
0x18000a010  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000a015  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000a01a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000a01f  mov     ebx, eax
0x18000a021  call    cs:__imp_LeaveCriticalSection
0x18000a027  mov     ecx, ebx
0x18000a029  neg     ecx
0x18000a02b  sbb     eax, eax
0x18000a02d  not     eax
0x18000a02f  and     eax, edi
0x18000a031  test    ebx, ebx
0x18000a033  jz      loc_180009E9D
0x18000a039  test    r12d, r12d
0x18000a03c  jz      short loc_18000A04D
0x18000a03e  test    r14, r14
0x18000a041  jz      short loc_18000A074
0x18000a043  mov     [rsp+0B00h+var_AE0], 1
0x18000a04b  jmp     short loc_18000A057
0x18000a04d  test    r14, r14
0x18000a050  jz      short loc_18000A074
0x18000a052  mov     [rsp+0B00h+var_AE0], r13d; int
0x18000a057  lea     r9, aRegistry; "REGISTRY"
0x18000a05e  mov     r8, r14; unsigned __int16 *
0x18000a061  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000a065  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000a06a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000a06f  jmp     loc_180009E9D
0x18000a074  mov     ebx, 80070057h
0x18000a079  jmp     short loc_18000A080
0x18000a07b  mov     ebx, 80004005h
0x18000a080  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000a085  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000a08a  mov     eax, ebx
0x18000a08c  jmp     short loc_18000A09A
0x18000a08e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000a093  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000a098  mov     eax, edi
0x18000a09a  mov     rcx, [rbp+0A00h+var_40]
0x18000a0a1  xor     rcx, rsp; StackCookie
0x18000a0a4  call    __security_check_cookie
0x18000a0a9  mov     rbx, [rsp+0B00h+arg_10]
0x18000a0b1  add     rsp, 0AD0h
0x18000a0b8  pop     r15
0x18000a0ba  pop     r14
0x18000a0bc  pop     r13
0x18000a0be  pop     r12
0x18000a0c0  pop     rdi
0x18000a0c1  pop     rsi
0x18000a0c2  pop     rbp
0x18000a0c3  retn
0x18000a0c4  call    __report_rangecheckfailure
```
