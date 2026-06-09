# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000be5c`
- end: `0x18000c19a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c1b0`

## callees

- `0x180003da8`
- `0x180007df8`
- `0x180008358`
- `0x180008c58`
- `0x1800094e8`
- `0x18000a348`
- `0x18000be5c`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c03a`
- `msvcrt!memcpy_s` at `0x18000c03a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bf5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bf5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bfd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bfd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c0ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c0f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bf18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c0ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c0f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000befd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bfe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c087`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c0cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000befd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bfe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c087`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c0cc`

## string_xrefs

- `0x18000c127`: `REGISTRY`

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
  BOOL v22; // ebx
  BOOL v23; // ebx
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  void *v26[2]; // [rsp+38h] [rbp-C8h] BYREF
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
          ATL::CExpansionVector::Add(v26, v10, v9);
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
      v22 = ATL::CExpansionVector::Add(v26, L"Module", v18);
      LeaveCriticalSection(&CriticalSection);
      v11 = !v22 ? 0x8007000E : 0;
      if ( v11 < 0 )
      {
LABEL_39:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add(v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = !v23 ? 0x8007000E : 0;
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
0x18000be5c  mov     [rsp-8+arg_10], rbx
0x18000be61  push    rbp
0x18000be62  push    rsi
0x18000be63  push    rdi
0x18000be64  push    r12
0x18000be66  push    r13
0x18000be68  push    r14
0x18000be6a  push    r15
0x18000be6c  lea     rbp, [rsp-9D0h]
0x18000be74  sub     rsp, 0AD0h
0x18000be7b  mov     rax, cs:__security_cookie
0x18000be82  xor     rax, rsp
0x18000be85  mov     [rbp+0A00h+var_40], rax
0x18000be8c  xor     r13d, r13d
0x18000be8f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000be96  xorps   xmm0, xmm0
0x18000be99  mov     [rsp+0B00h+var_AD0], rax
0x18000be9e  xor     eax, eax
0x18000bea0  mov     [rsp+0B00h+var_AC8], r13
0x18000bea5  mov     r15, rcx
0x18000bea8  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000bead  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000beb2  mov     [rsp+0B00h+var_AC0], r13
0x18000beb7  mov     rbx, r9
0x18000beba  mov     [rsp+0B00h+var_AB8], r13d
0x18000bebf  mov     r12d, r8d
0x18000bec2  mov     [rsp+0B00h+var_A88], r13b
0x18000bec7  mov     r14, rdx
0x18000beca  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000becf  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000bed4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000bed9  mov     edi, eax
0x18000bedb  test    eax, eax
0x18000bedd  js      loc_18000C15E
0x18000bee3  mov     [rsp+0B00h+var_A88], 1
0x18000bee8  test    rbx, rbx
0x18000beeb  jz      short loc_18000BF2A
0x18000beed  jmp     short loc_18000BF22
0x18000beef  mov     rsi, [rbx+8]
0x18000bef3  test    rsi, rsi
0x18000bef6  jz      short loc_18000BF1E
0x18000bef8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000befd  call    cs:__imp_EnterCriticalSection
0x18000bf03  mov     r8, rsi; unsigned __int16 *
0x18000bf06  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000bf0b  mov     rdx, rdi; unsigned __int16 *
0x18000bf0e  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000bf13  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bf18  call    cs:__imp_LeaveCriticalSection
0x18000bf1e  add     rbx, 10h
0x18000bf22  mov     rdi, [rbx]
0x18000bf25  test    rdi, rdi
0x18000bf28  jnz     short loc_18000BEEF
0x18000bf2a  mov     rax, [r15]
0x18000bf2d  lea     rdx, [rsp+0B00h+var_AD0]
0x18000bf32  mov     rcx, r15
0x18000bf35  mov     rax, [rax+28h]
0x18000bf39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf3e  mov     ebx, eax
0x18000bf40  test    eax, eax
0x18000bf42  js      loc_18000C150
0x18000bf48  mov     rbx, cs:hModule
0x18000bf4f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000bf53  mov     edi, 104h
0x18000bf58  mov     rcx, rbx; hModule
0x18000bf5b  mov     r8d, edi; nSize
0x18000bf5e  call    cs:__imp_GetModuleFileNameW
0x18000bf64  test    eax, eax
0x18000bf66  jnz     short loc_18000BF74
0x18000bf68  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bf6d  mov     ebx, eax
0x18000bf6f  jmp     loc_18000C150
0x18000bf74  cmp     eax, edi
0x18000bf76  jnz     short loc_18000BF82
0x18000bf78  mov     ebx, 8007007Ah
0x18000bf7d  jmp     loc_18000C150
0x18000bf82  lea     rdx, [rbp+0A00h+Filename]
0x18000bf86  mov     ecx, r13d
0x18000bf89  mov     r9d, 27h ; '''
0x18000bf8f  movzx   r8d, word ptr [rdx]
0x18000bf93  test    r8w, r8w
0x18000bf97  jz      short loc_18000BFC9
0x18000bf99  mov     [rbp+rcx*2+0A00h+Source], r8w
0x18000bfa2  cmp     r8w, r9w
0x18000bfa6  jnz     short loc_18000BFBB
0x18000bfa8  cmp     ecx, 206h
0x18000bfae  jnb     short loc_18000BFBB
0x18000bfb0  inc     ecx
0x18000bfb2  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000bfbb  add     rdx, 2
0x18000bfbf  inc     ecx
0x18000bfc1  cmp     ecx, 207h
0x18000bfc7  jb      short loc_18000BF8F
0x18000bfc9  mov     [rbp+rcx*2+0A00h+Source], r13w
0x18000bfd2  test    rbx, rbx
0x18000bfd5  jz      short loc_18000BFFB
0x18000bfd7  xor     ecx, ecx; lpModuleName
0x18000bfd9  call    cs:__imp_GetModuleHandleW
0x18000bfdf  cmp     rbx, rax
0x18000bfe2  jz      short loc_18000BFFB
0x18000bfe4  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bfe9  call    cs:__imp_EnterCriticalSection
0x18000bfef  lea     r8, [rbp+0A00h+Source]
0x18000bff6  jmp     loc_18000C094
0x18000bffb  mov     edi, 22h ; '"'
0x18000c000  lea     rcx, [rbp+0A00h+Source]
0x18000c007  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c00b  mov     [rbp+0A00h+var_460], di
0x18000c012  mov     rax, rbx
0x18000c015  inc     rax
0x18000c018  cmp     [rcx+rax*2], r13w
0x18000c01d  jnz     short loc_18000C015
0x18000c01f  inc     eax
0x18000c021  lea     r8, [rbp+0A00h+Source]; Source
0x18000c028  movsxd  r9, eax
0x18000c02b  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000c032  add     r9, r9; SourceSize
0x18000c035  mov     edx, 414h; DestinationSize
0x18000c03a  call    cs:__imp_memcpy_s
0x18000c040  test    eax, eax
0x18000c042  jnz     loc_18000C14B
0x18000c048  lea     rax, [rbp+0A00h+var_460]
0x18000c04f  inc     rbx
0x18000c052  cmp     [rax+rbx*2], r13w
0x18000c057  jnz     short loc_18000C04F
0x18000c059  movsxd  rax, ebx
0x18000c05c  lea     rcx, ds:2[rax*2]
0x18000c064  mov     [rbp+rax*2+0A00h+var_460], di
0x18000c06c  cmp     rcx, 418h
0x18000c073  jnb     loc_18000C194
0x18000c079  mov     [rbp+rcx+0A00h+var_460], r13w
0x18000c082  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000c087  call    cs:__imp_EnterCriticalSection
0x18000c08d  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000c094  lea     rdx, aModule; "Module"
0x18000c09b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000c0a0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000c0a5  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000c0aa  mov     ebx, eax
0x18000c0ac  call    cs:__imp_LeaveCriticalSection
0x18000c0b2  neg     ebx
0x18000c0b4  mov     edi, 8007000Eh
0x18000c0b9  sbb     ebx, ebx
0x18000c0bb  not     ebx
0x18000c0bd  and     ebx, edi
0x18000c0bf  test    ebx, ebx
0x18000c0c1  js      loc_18000C150
0x18000c0c7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000c0cc  call    cs:__imp_EnterCriticalSection
0x18000c0d2  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x18000c0d9  lea     rdx, aModuleRaw; "Module_Raw"
0x18000c0e0  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000c0e5  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000c0ea  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000c0ef  mov     ebx, eax
0x18000c0f1  call    cs:__imp_LeaveCriticalSection
0x18000c0f7  mov     ecx, ebx
0x18000c0f9  neg     ecx
0x18000c0fb  sbb     eax, eax
0x18000c0fd  not     eax
0x18000c0ff  and     eax, edi
0x18000c101  test    ebx, ebx
0x18000c103  jz      loc_18000BF6D
0x18000c109  test    r12d, r12d
0x18000c10c  jz      short loc_18000C11D
0x18000c10e  test    r14, r14
0x18000c111  jz      short loc_18000C144
0x18000c113  mov     [rsp+0B00h+var_AE0], 1
0x18000c11b  jmp     short loc_18000C127
0x18000c11d  test    r14, r14
0x18000c120  jz      short loc_18000C144
0x18000c122  mov     [rsp+0B00h+var_AE0], r13d; int
0x18000c127  lea     r9, aRegistry; "REGISTRY"
0x18000c12e  mov     r8, r14; unsigned __int16 *
0x18000c131  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000c135  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000c13a  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000c13f  jmp     loc_18000BF6D
0x18000c144  mov     ebx, 80070057h
0x18000c149  jmp     short loc_18000C150
0x18000c14b  mov     ebx, 80004005h
0x18000c150  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000c155  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c15a  mov     eax, ebx
0x18000c15c  jmp     short loc_18000C16A
0x18000c15e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000c163  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000c168  mov     eax, edi
0x18000c16a  mov     rcx, [rbp+0A00h+var_40]
0x18000c171  xor     rcx, rsp; StackCookie
0x18000c174  call    __security_check_cookie
0x18000c179  mov     rbx, [rsp+0B00h+arg_10]
0x18000c181  add     rsp, 0AD0h
0x18000c188  pop     r15
0x18000c18a  pop     r14
0x18000c18c  pop     r13
0x18000c18e  pop     r12
0x18000c190  pop     rdi
0x18000c191  pop     rsi
0x18000c192  pop     rbp
0x18000c193  retn
0x18000c194  call    __report_rangecheckfailure
```
