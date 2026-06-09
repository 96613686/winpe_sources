# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140005034`
- end: `0x140005377`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `835`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140005390`

## callees

- `0x1400014f0`
- `0x1400017a0`
- `0x140001e22`
- `0x140002228`
- `0x14000259c`
- `0x140002fc8`
- `0x1400034ec`
- `0x140003fac`
- `0x140005034`
- `0x1400075dc`
- `0x140008010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400052e8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400052e8`
- `KERNEL32!EnterCriticalSection` at `0x1400050d5`
- `KERNEL32!EnterCriticalSection` at `0x1400051bf`
- `KERNEL32!EnterCriticalSection` at `0x14000525e`
- `KERNEL32!EnterCriticalSection` at `0x14000529f`
- `KERNEL32!EnterCriticalSection` at `0x1400050d5`
- `KERNEL32!EnterCriticalSection` at `0x1400051bf`
- `KERNEL32!EnterCriticalSection` at `0x14000525e`
- `KERNEL32!EnterCriticalSection` at `0x14000529f`
- `KERNEL32!LeaveCriticalSection` at `0x1400050f0`
- `KERNEL32!LeaveCriticalSection` at `0x140005283`
- `KERNEL32!LeaveCriticalSection` at `0x1400052c4`
- `KERNEL32!LeaveCriticalSection` at `0x1400050f0`
- `KERNEL32!LeaveCriticalSection` at `0x140005283`
- `KERNEL32!LeaveCriticalSection` at `0x1400052c4`
- `KERNEL32!GetModuleHandleW` at `0x1400051af`
- `KERNEL32!GetModuleHandleW` at `0x1400051af`
- `KERNEL32!GetModuleFileNameW` at `0x140005136`
- `KERNEL32!GetModuleFileNameW` at `0x140005136`

## string_xrefs

- `0x14000531a`: `REGISTRY`

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
      goto LABEL_33;
    v12 = hInstance;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
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
            goto LABEL_33;
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
        {
          if ( a3 )
          {
            if ( a2 )
            {
              Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 1);
              goto LABEL_32;
            }
          }
          else if ( a2 )
          {
            Error = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v27, Filename, a2, L"REGISTRY", 0);
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
0x140005034  mov     [rsp-8+arg_10], rbx
0x140005039  push    rbp
0x14000503a  push    rsi
0x14000503b  push    rdi
0x14000503c  push    r12
0x14000503e  push    r13
0x140005040  push    r14
0x140005042  push    r15
0x140005044  lea     rbp, [rsp-9D0h]
0x14000504c  sub     rsp, 0AD0h
0x140005053  mov     rax, cs:__security_cookie
0x14000505a  xor     rax, rsp
0x14000505d  mov     [rbp+0A00h+var_40], rax
0x140005064  mov     rbx, r9
0x140005067  mov     r12d, r8d
0x14000506a  mov     r14, rdx
0x14000506d  mov     r15, rcx
0x140005070  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x140005077  mov     [rsp+0B00h+var_AD0], rax
0x14000507c  xor     r13d, r13d
0x14000507f  mov     [rsp+0B00h+var_AC8], r13
0x140005084  mov     [rsp+0B00h+var_AC0], r13
0x140005089  mov     [rsp+0B00h+var_AB8], r13d
0x14000508e  xorps   xmm0, xmm0
0x140005091  xor     eax, eax
0x140005093  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x140005098  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x14000509d  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x1400050a2  mov     [rsp+0B00h+var_A88], r13b
0x1400050a7  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x1400050ac  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400050b1  mov     edi, eax
0x1400050b3  test    eax, eax
0x1400050b5  js      loc_14000533B
0x1400050bb  mov     [rsp+0B00h+var_A88], 1
0x1400050c0  test    rbx, rbx
0x1400050c3  jz      short loc_140005102
0x1400050c5  jmp     short loc_1400050FA
0x1400050c7  mov     rsi, [rbx+8]
0x1400050cb  test    rsi, rsi
0x1400050ce  jz      short loc_1400050F6
0x1400050d0  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400050d5  call    cs:__imp_EnterCriticalSection
0x1400050db  mov     r8, rsi; unsigned __int16 *
0x1400050de  mov     rdx, rdi; unsigned __int16 *
0x1400050e1  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1400050e6  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1400050eb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400050f0  call    cs:__imp_LeaveCriticalSection
0x1400050f6  add     rbx, 10h
0x1400050fa  mov     rdi, [rbx]
0x1400050fd  test    rdi, rdi
0x140005100  jnz     short loc_1400050C7
0x140005102  mov     rax, [r15]
0x140005105  lea     rdx, [rsp+0B00h+var_AD0]
0x14000510a  mov     rcx, r15
0x14000510d  mov     rax, [rax+28h]
0x140005111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005116  mov     ebx, eax
0x140005118  test    eax, eax
0x14000511a  js      loc_1400052DA
0x140005120  mov     rbx, cs:hInstance
0x140005127  mov     edi, 104h
0x14000512c  mov     r8d, edi; nSize
0x14000512f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x140005133  mov     rcx, rbx; hModule
0x140005136  call    cs:__imp_GetModuleFileNameW
0x14000513c  test    eax, eax
0x14000513e  jnz     short loc_14000514A
0x140005140  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140005145  jmp     loc_1400052D8
0x14000514a  cmp     eax, edi
0x14000514c  jnz     short loc_140005158
0x14000514e  mov     ebx, 8007007Ah
0x140005153  jmp     loc_1400052DA
0x140005158  lea     rdx, [rbp+0A00h+Filename]
0x14000515c  mov     ecx, r13d
0x14000515f  mov     r9d, 27h ; '''
0x140005165  movzx   r8d, word ptr [rdx]
0x140005169  test    r8w, r8w
0x14000516d  jz      short loc_14000519F
0x14000516f  mov     [rbp+rcx*2+0A00h+Src], r8w
0x140005178  cmp     r8w, r9w
0x14000517c  jnz     short loc_140005191
0x14000517e  cmp     ecx, 206h
0x140005184  jnb     short loc_140005191
0x140005186  inc     ecx
0x140005188  mov     [rbp+rcx*2+0A00h+Src], r9w
0x140005191  add     rdx, 2
0x140005195  inc     ecx
0x140005197  cmp     ecx, 207h
0x14000519d  jb      short loc_140005165
0x14000519f  mov     [rbp+rcx*2+0A00h+Src], r13w
0x1400051a8  test    rbx, rbx
0x1400051ab  jz      short loc_1400051D1
0x1400051ad  xor     ecx, ecx; lpModuleName
0x1400051af  call    cs:__imp_GetModuleHandleW
0x1400051b5  cmp     rbx, rax
0x1400051b8  jz      short loc_1400051D1
0x1400051ba  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400051bf  call    cs:__imp_EnterCriticalSection
0x1400051c5  lea     r8, [rbp+0A00h+Src]
0x1400051cc  jmp     loc_14000526B
0x1400051d1  mov     edi, 22h ; '"'
0x1400051d6  mov     [rbp+0A00h+var_460], di
0x1400051dd  lea     rcx, [rbp+0A00h+Src]
0x1400051e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400051e8  mov     rax, rbx
0x1400051eb  inc     rax
0x1400051ee  cmp     [rcx+rax*2], r13w
0x1400051f3  jnz     short loc_1400051EB
0x1400051f5  inc     eax
0x1400051f7  movsxd  r8, eax
0x1400051fa  add     r8, r8; Size
0x1400051fd  jz      short loc_14000521F
0x1400051ff  cmp     r8, 414h
0x140005206  ja      loc_1400052E8
0x14000520c  lea     rdx, [rbp+0A00h+Src]; Src
0x140005213  lea     rcx, [rbp+0A00h+var_45E]; void *
0x14000521a  call    memcpy_0
0x14000521f  lea     rax, [rbp+0A00h+var_460]
0x140005226  inc     rbx
0x140005229  cmp     [rax+rbx*2], r13w
0x14000522e  jnz     short loc_140005226
0x140005230  movsxd  rax, ebx
0x140005233  mov     [rbp+rax*2+0A00h+var_460], di
0x14000523b  lea     rcx, ds:2[rax*2]
0x140005243  cmp     rcx, 418h
0x14000524a  jnb     loc_140005371
0x140005250  mov     [rbp+rcx+0A00h+var_460], r13w
0x140005259  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000525e  call    cs:__imp_EnterCriticalSection
0x140005264  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x14000526b  lea     rdx, aModule; "Module"
0x140005272  lea     rcx, [rsp+0B00h+var_AC8]; this
0x140005277  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000527c  mov     ebx, eax
0x14000527e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x140005283  call    cs:__imp_LeaveCriticalSection
0x140005289  neg     ebx
0x14000528b  sbb     ebx, ebx
0x14000528d  mov     edi, 8007000Eh
0x140005292  not     ebx
0x140005294  and     ebx, edi
0x140005296  test    ebx, ebx
0x140005298  js      short loc_1400052DA
0x14000529a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x14000529f  call    cs:__imp_EnterCriticalSection
0x1400052a5  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x1400052ac  lea     rdx, aModuleRaw; "Module_Raw"
0x1400052b3  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1400052b8  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1400052bd  mov     ebx, eax
0x1400052bf  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1400052c4  call    cs:__imp_LeaveCriticalSection
0x1400052ca  mov     ecx, ebx
0x1400052cc  neg     ecx
0x1400052ce  sbb     eax, eax
0x1400052d0  not     eax
0x1400052d2  and     eax, edi
0x1400052d4  test    ebx, ebx
0x1400052d6  jnz     short loc_1400052FC
0x1400052d8  mov     ebx, eax
0x1400052da  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1400052df  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1400052e4  mov     eax, ebx
0x1400052e6  jmp     short loc_140005347
0x1400052e8  call    cs:__imp__o__errno
0x1400052ee  mov     [rax], edi
0x1400052f0  call    _invalid_parameter_noinfo
0x1400052f5  mov     ebx, 80004005h
0x1400052fa  jmp     short loc_1400052DA
0x1400052fc  test    r12d, r12d
0x1400052ff  jz      short loc_140005310
0x140005301  test    r14, r14
0x140005304  jz      short loc_140005334
0x140005306  mov     [rsp+0B00h+var_AE0], 1
0x14000530e  jmp     short loc_14000531A
0x140005310  test    r14, r14
0x140005313  jz      short loc_140005334
0x140005315  mov     [rsp+0B00h+var_AE0], r13d; int
0x14000531a  lea     r9, aRegistry; "REGISTRY"
0x140005321  mov     r8, r14; unsigned __int16 *
0x140005324  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x140005328  lea     rcx, [rsp+0B00h+var_AD0]; this
0x14000532d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x140005332  jmp     short loc_1400052D8
0x140005334  mov     ebx, 80070057h
0x140005339  jmp     short loc_1400052DA
0x14000533b  lea     rcx, [rsp+0B00h+var_AD0]; this
0x140005340  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x140005345  mov     eax, edi
0x140005347  mov     rcx, [rbp+0A00h+var_40]
0x14000534e  xor     rcx, rsp; StackCookie
0x140005351  call    __security_check_cookie
0x140005356  mov     rbx, [rsp+0B00h+arg_10]
0x14000535e  add     rsp, 0AD0h
0x140005365  pop     r15
0x140005367  pop     r14
0x140005369  pop     r13
0x14000536b  pop     r12
0x14000536d  pop     rdi
0x14000536e  pop     rsi
0x14000536f  pop     rbp
0x140005370  retn
0x140005371  call    __report_rangecheckfailure
```
