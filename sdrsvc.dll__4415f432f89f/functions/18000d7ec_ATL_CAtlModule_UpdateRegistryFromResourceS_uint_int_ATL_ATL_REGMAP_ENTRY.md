# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000d7ec`
- end: `0x18000db03`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b868`
- `0x18000d5b4`
- `0x18000d7a0`
- `0x18000d7c0`
- `0x18000de50`

## callees

- `0x180001dc8`
- `0x180008a9c`
- `0x180008e28`
- `0x1800098f4`
- `0x18000ac0c`
- `0x18000bfbc`
- `0x18000d7ec`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d9be`
- `msvcrt!memcpy_s` at `0x18000d9be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000d8f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000d8f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d966`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d966`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d8a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000da30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000da6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d8a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000da30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000da6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d88d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d976`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d88d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d976`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000da4c`

## string_xrefs

- `0x18000da90`: `REGISTRY`

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
0x18000d7ec  mov     [rsp-8+arg_10], rbx
0x18000d7f1  push    rbp
0x18000d7f2  push    rsi
0x18000d7f3  push    rdi
0x18000d7f4  push    r12
0x18000d7f6  push    r13
0x18000d7f8  push    r14
0x18000d7fa  push    r15
0x18000d7fc  lea     rbp, [rsp-9D0h]
0x18000d804  sub     rsp, 0AD0h
0x18000d80b  mov     rax, cs:__security_cookie
0x18000d812  xor     rax, rsp
0x18000d815  mov     [rbp+0A00h+var_40], rax
0x18000d81c  xor     r13d, r13d
0x18000d81f  mov     r12d, edx
0x18000d822  xorps   xmm0, xmm0
0x18000d825  mov     [rsp+0B00h+var_AC8], r13
0x18000d82a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000d831  mov     [rsp+0B00h+var_AC0], r13
0x18000d836  mov     [rsp+0B00h+var_AD0], rax
0x18000d83b  mov     r14, rcx
0x18000d83e  xor     eax, eax
0x18000d840  mov     [rsp+0B00h+var_AB8], r13d
0x18000d845  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000d84a  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000d84f  mov     rbx, r9
0x18000d852  mov     [rsp+0B00h+var_A88], r13b
0x18000d857  mov     r15d, r8d
0x18000d85a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000d85f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000d864  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000d869  mov     edi, eax
0x18000d86b  test    eax, eax
0x18000d86d  js      loc_18000DAC7
0x18000d873  mov     [rsp+0B00h+var_A88], 1
0x18000d878  test    rbx, rbx
0x18000d87b  jz      short loc_18000D8BA
0x18000d87d  jmp     short loc_18000D8B2
0x18000d87f  mov     rsi, [rbx+8]
0x18000d883  test    rsi, rsi
0x18000d886  jz      short loc_18000D8AE
0x18000d888  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000d88d  call    cs:__imp_EnterCriticalSection
0x18000d893  mov     r8, rsi; unsigned __int16 *
0x18000d896  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000d89b  mov     rdx, rdi; unsigned __int16 *
0x18000d89e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000d8a3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000d8a8  call    cs:__imp_LeaveCriticalSection
0x18000d8ae  add     rbx, 10h
0x18000d8b2  mov     rdi, [rbx]
0x18000d8b5  test    rdi, rdi
0x18000d8b8  jnz     short loc_18000D87F
0x18000d8ba  mov     rax, [r14]
0x18000d8bd  lea     rdx, [rsp+0B00h+var_AD0]
0x18000d8c2  mov     rcx, r14
0x18000d8c5  mov     rax, [rax+28h]
0x18000d8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ce  mov     ebx, eax
0x18000d8d0  test    eax, eax
0x18000d8d2  js      loc_18000DAB9
0x18000d8d8  mov     rbx, cs:hInstance
0x18000d8df  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000d8e6  mov     edi, 104h
0x18000d8eb  mov     rcx, rbx; hModule
0x18000d8ee  mov     r8d, edi; nSize
0x18000d8f1  call    cs:__imp_GetModuleFileNameW
0x18000d8f7  test    eax, eax
0x18000d8f9  jnz     short loc_18000D907
0x18000d8fb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000d900  mov     ebx, eax
0x18000d902  jmp     loc_18000DAB9
0x18000d907  cmp     eax, edi
0x18000d909  jnz     short loc_18000D915
0x18000d90b  mov     ebx, 8007007Ah
0x18000d910  jmp     loc_18000DAB9
0x18000d915  lea     rdx, [rbp+0A00h+Filename]
0x18000d91c  mov     ecx, r13d
0x18000d91f  mov     r9d, 27h ; '''
0x18000d925  movzx   r8d, word ptr [rdx]
0x18000d929  test    r8w, r8w
0x18000d92d  jz      short loc_18000D959
0x18000d92f  mov     [rbp+rcx*2+0A00h+Source], r8w
0x18000d935  cmp     r8w, r9w
0x18000d939  jnz     short loc_18000D94B
0x18000d93b  cmp     ecx, 206h
0x18000d941  jnb     short loc_18000D94B
0x18000d943  inc     ecx
0x18000d945  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000d94b  add     rdx, 2
0x18000d94f  inc     ecx
0x18000d951  cmp     ecx, 207h
0x18000d957  jb      short loc_18000D925
0x18000d959  mov     [rbp+rcx*2+0A00h+Source], r13w
0x18000d95f  test    rbx, rbx
0x18000d962  jz      short loc_18000D985
0x18000d964  xor     ecx, ecx; lpModuleName
0x18000d966  call    cs:__imp_GetModuleHandleW
0x18000d96c  cmp     rbx, rax
0x18000d96f  jz      short loc_18000D985
0x18000d971  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000d976  call    cs:__imp_EnterCriticalSection
0x18000d97c  lea     r8, [rbp+0A00h+Source]
0x18000d980  jmp     loc_18000DA18
0x18000d985  mov     edi, 22h ; '"'
0x18000d98a  lea     rcx, [rbp+0A00h+Source]
0x18000d98e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d992  mov     [rbp+0A00h+var_460], di
0x18000d999  mov     rax, rbx
0x18000d99c  inc     rax
0x18000d99f  cmp     [rcx+rax*2], r13w
0x18000d9a4  jnz     short loc_18000D99C
0x18000d9a6  inc     eax
0x18000d9a8  lea     r8, [rbp+0A00h+Source]; Source
0x18000d9ac  movsxd  r9, eax
0x18000d9af  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000d9b6  add     r9, r9; SourceSize
0x18000d9b9  mov     edx, 414h; DestinationSize
0x18000d9be  call    cs:__imp_memcpy_s
0x18000d9c4  test    eax, eax
0x18000d9c6  jnz     loc_18000DAB4
0x18000d9cc  lea     rax, [rbp+0A00h+var_460]
0x18000d9d3  inc     rbx
0x18000d9d6  cmp     [rax+rbx*2], r13w
0x18000d9db  jnz     short loc_18000D9D3
0x18000d9dd  movsxd  rax, ebx
0x18000d9e0  lea     rcx, ds:2[rax*2]
0x18000d9e8  mov     [rbp+rax*2+0A00h+var_460], di
0x18000d9f0  cmp     rcx, 418h
0x18000d9f7  jnb     loc_18000DAFD
0x18000d9fd  mov     [rbp+rcx+0A00h+var_460], r13w
0x18000da06  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000da0b  call    cs:__imp_EnterCriticalSection
0x18000da11  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000da18  lea     rdx, aModule; "Module"
0x18000da1f  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000da24  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000da29  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000da2e  mov     ebx, eax
0x18000da30  call    cs:__imp_LeaveCriticalSection
0x18000da36  neg     ebx
0x18000da38  mov     edi, 8007000Eh
0x18000da3d  sbb     ebx, ebx
0x18000da3f  not     ebx
0x18000da41  and     ebx, edi
0x18000da43  test    ebx, ebx
0x18000da45  js      short loc_18000DAB9
0x18000da47  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000da4c  call    cs:__imp_EnterCriticalSection
0x18000da52  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x18000da56  lea     rdx, aModuleRaw; "Module_Raw"
0x18000da5d  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000da62  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000da67  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000da6c  mov     ebx, eax
0x18000da6e  call    cs:__imp_LeaveCriticalSection
0x18000da74  mov     ecx, ebx
0x18000da76  neg     ecx
0x18000da78  sbb     eax, eax
0x18000da7a  not     eax
0x18000da7c  and     eax, edi
0x18000da7e  test    ebx, ebx
0x18000da80  jz      loc_18000D900
0x18000da86  mov     eax, r13d
0x18000da89  movzx   r8d, r12w; unsigned __int16 *
0x18000da8d  test    r15d, r15d
0x18000da90  lea     r9, aRegistry; "REGISTRY"
0x18000da97  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000da9e  setnz   al
0x18000daa1  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000daa6  mov     [rsp+0B00h+var_AE0], eax; int
0x18000daaa  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000daaf  jmp     loc_18000D900
0x18000dab4  mov     ebx, 80004005h
0x18000dab9  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000dabe  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000dac3  mov     eax, ebx
0x18000dac5  jmp     short loc_18000DAD3
0x18000dac7  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000dacc  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000dad1  mov     eax, edi
0x18000dad3  mov     rcx, [rbp+0A00h+var_40]
0x18000dada  xor     rcx, rsp; StackCookie
0x18000dadd  call    __security_check_cookie
0x18000dae2  mov     rbx, [rsp+0B00h+arg_10]
0x18000daea  add     rsp, 0AD0h
0x18000daf1  pop     r15
0x18000daf3  pop     r14
0x18000daf5  pop     r13
0x18000daf7  pop     r12
0x18000daf9  pop     rdi
0x18000dafa  pop     rsi
0x18000dafb  pop     rbp
0x18000dafc  retn
0x18000dafd  call    __report_rangecheckfailure
```
