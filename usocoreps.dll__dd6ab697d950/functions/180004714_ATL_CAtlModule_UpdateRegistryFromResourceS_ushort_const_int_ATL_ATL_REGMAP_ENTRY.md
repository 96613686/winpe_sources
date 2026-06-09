# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x180004714`
- end: `0x180004a57`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `835`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004a70`

## callees

- `0x180001510`
- `0x180001550`
- `0x1800020ca`
- `0x180002338`
- `0x18000246c`
- `0x180002ef4`
- `0x1800031ac`
- `0x180003978`
- `0x180004714`
- `0x180004ea0`
- `0x180006010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800049c8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800049c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004816`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004816`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000488f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000488f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000489f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000493e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000497f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800047b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000489f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000493e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000497f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800049a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800049a4`

## string_xrefs

- `0x1800049fa`: `REGISTRY`

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
0x180004714  mov     [rsp-8+arg_10], rbx
0x180004719  push    rbp
0x18000471a  push    rsi
0x18000471b  push    rdi
0x18000471c  push    r12
0x18000471e  push    r13
0x180004720  push    r14
0x180004722  push    r15
0x180004724  lea     rbp, [rsp-9D0h]
0x18000472c  sub     rsp, 0AD0h
0x180004733  mov     rax, cs:__security_cookie
0x18000473a  xor     rax, rsp
0x18000473d  mov     [rbp+0A00h+var_40], rax
0x180004744  mov     rbx, r9
0x180004747  mov     r12d, r8d
0x18000474a  mov     r14, rdx
0x18000474d  mov     r15, rcx
0x180004750  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x180004757  mov     [rsp+0B00h+var_AD0], rax
0x18000475c  xor     r13d, r13d
0x18000475f  mov     [rsp+0B00h+var_AC8], r13
0x180004764  mov     [rsp+0B00h+var_AC0], r13
0x180004769  mov     [rsp+0B00h+var_AB8], r13d
0x18000476e  xorps   xmm0, xmm0
0x180004771  xor     eax, eax
0x180004773  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x180004778  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000477d  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x180004782  mov     [rsp+0B00h+var_A88], r13b
0x180004787  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000478c  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004791  mov     edi, eax
0x180004793  test    eax, eax
0x180004795  js      loc_180004A1B
0x18000479b  mov     [rsp+0B00h+var_A88], 1
0x1800047a0  test    rbx, rbx
0x1800047a3  jz      short loc_1800047E2
0x1800047a5  jmp     short loc_1800047DA
0x1800047a7  mov     rsi, [rbx+8]
0x1800047ab  test    rsi, rsi
0x1800047ae  jz      short loc_1800047D6
0x1800047b0  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800047b5  call    cs:__imp_EnterCriticalSection
0x1800047bb  mov     r8, rsi; unsigned __int16 *
0x1800047be  mov     rdx, rdi; unsigned __int16 *
0x1800047c1  lea     rcx, [rsp+0B00h+var_AC8]; this
0x1800047c6  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800047cb  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800047d0  call    cs:__imp_LeaveCriticalSection
0x1800047d6  add     rbx, 10h
0x1800047da  mov     rdi, [rbx]
0x1800047dd  test    rdi, rdi
0x1800047e0  jnz     short loc_1800047A7
0x1800047e2  mov     rax, [r15]
0x1800047e5  lea     rdx, [rsp+0B00h+var_AD0]
0x1800047ea  mov     rcx, r15
0x1800047ed  mov     rax, [rax+28h]
0x1800047f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047f6  mov     ebx, eax
0x1800047f8  test    eax, eax
0x1800047fa  js      loc_1800049BA
0x180004800  mov     rbx, cs:hModule
0x180004807  mov     edi, 104h
0x18000480c  mov     r8d, edi; nSize
0x18000480f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x180004813  mov     rcx, rbx; hModule
0x180004816  call    cs:__imp_GetModuleFileNameW
0x18000481c  test    eax, eax
0x18000481e  jnz     short loc_18000482A
0x180004820  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004825  jmp     loc_1800049B8
0x18000482a  cmp     eax, edi
0x18000482c  jnz     short loc_180004838
0x18000482e  mov     ebx, 8007007Ah
0x180004833  jmp     loc_1800049BA
0x180004838  lea     rdx, [rbp+0A00h+Filename]
0x18000483c  mov     ecx, r13d
0x18000483f  mov     r9d, 27h ; '''
0x180004845  movzx   r8d, word ptr [rdx]
0x180004849  test    r8w, r8w
0x18000484d  jz      short loc_18000487F
0x18000484f  mov     [rbp+rcx*2+0A00h+Src], r8w
0x180004858  cmp     r8w, r9w
0x18000485c  jnz     short loc_180004871
0x18000485e  cmp     ecx, 206h
0x180004864  jnb     short loc_180004871
0x180004866  inc     ecx
0x180004868  mov     [rbp+rcx*2+0A00h+Src], r9w
0x180004871  add     rdx, 2
0x180004875  inc     ecx
0x180004877  cmp     ecx, 207h
0x18000487d  jb      short loc_180004845
0x18000487f  mov     [rbp+rcx*2+0A00h+Src], r13w
0x180004888  test    rbx, rbx
0x18000488b  jz      short loc_1800048B1
0x18000488d  xor     ecx, ecx; lpModuleName
0x18000488f  call    cs:__imp_GetModuleHandleW
0x180004895  cmp     rbx, rax
0x180004898  jz      short loc_1800048B1
0x18000489a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000489f  call    cs:__imp_EnterCriticalSection
0x1800048a5  lea     r8, [rbp+0A00h+Src]
0x1800048ac  jmp     loc_18000494B
0x1800048b1  mov     edi, 22h ; '"'
0x1800048b6  mov     [rbp+0A00h+var_460], di
0x1800048bd  lea     rcx, [rbp+0A00h+Src]
0x1800048c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800048c8  mov     rax, rbx
0x1800048cb  inc     rax
0x1800048ce  cmp     [rcx+rax*2], r13w
0x1800048d3  jnz     short loc_1800048CB
0x1800048d5  inc     eax
0x1800048d7  movsxd  r8, eax
0x1800048da  add     r8, r8; Size
0x1800048dd  jz      short loc_1800048FF
0x1800048df  cmp     r8, 414h
0x1800048e6  ja      loc_1800049C8
0x1800048ec  lea     rdx, [rbp+0A00h+Src]; Src
0x1800048f3  lea     rcx, [rbp+0A00h+var_45E]; void *
0x1800048fa  call    memcpy_0
0x1800048ff  lea     rax, [rbp+0A00h+var_460]
0x180004906  inc     rbx
0x180004909  cmp     [rax+rbx*2], r13w
0x18000490e  jnz     short loc_180004906
0x180004910  movsxd  rax, ebx
0x180004913  mov     [rbp+rax*2+0A00h+var_460], di
0x18000491b  lea     rcx, ds:2[rax*2]
0x180004923  cmp     rcx, 418h
0x18000492a  jnb     loc_180004A51
0x180004930  mov     [rbp+rcx+0A00h+var_460], r13w
0x180004939  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000493e  call    cs:__imp_EnterCriticalSection
0x180004944  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000494b  lea     rdx, aModule; "Module"
0x180004952  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004957  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000495c  mov     ebx, eax
0x18000495e  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x180004963  call    cs:__imp_LeaveCriticalSection
0x180004969  neg     ebx
0x18000496b  sbb     ebx, ebx
0x18000496d  mov     edi, 8007000Eh
0x180004972  not     ebx
0x180004974  and     ebx, edi
0x180004976  test    ebx, ebx
0x180004978  js      short loc_1800049BA
0x18000497a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000497f  call    cs:__imp_EnterCriticalSection
0x180004985  lea     r8, [rbp+0A00h+Src]; unsigned __int16 *
0x18000498c  lea     rdx, aModuleRaw; "Module_Raw"
0x180004993  lea     rcx, [rsp+0B00h+var_AC8]; this
0x180004998  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000499d  mov     ebx, eax
0x18000499f  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x1800049a4  call    cs:__imp_LeaveCriticalSection
0x1800049aa  mov     ecx, ebx
0x1800049ac  neg     ecx
0x1800049ae  sbb     eax, eax
0x1800049b0  not     eax
0x1800049b2  and     eax, edi
0x1800049b4  test    ebx, ebx
0x1800049b6  jnz     short loc_1800049DC
0x1800049b8  mov     ebx, eax
0x1800049ba  lea     rcx, [rsp+0B00h+var_AD0]; this
0x1800049bf  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x1800049c4  mov     eax, ebx
0x1800049c6  jmp     short loc_180004A27
0x1800049c8  call    cs:__imp__o__errno
0x1800049ce  mov     [rax], edi
0x1800049d0  call    _invalid_parameter_noinfo
0x1800049d5  mov     ebx, 80004005h
0x1800049da  jmp     short loc_1800049BA
0x1800049dc  test    r12d, r12d
0x1800049df  jz      short loc_1800049F0
0x1800049e1  test    r14, r14
0x1800049e4  jz      short loc_180004A14
0x1800049e6  mov     [rsp+0B00h+var_AE0], 1
0x1800049ee  jmp     short loc_1800049FA
0x1800049f0  test    r14, r14
0x1800049f3  jz      short loc_180004A14
0x1800049f5  mov     [rsp+0B00h+var_AE0], r13d; int
0x1800049fa  lea     r9, aRegistry; "REGISTRY"
0x180004a01  mov     r8, r14; unsigned __int16 *
0x180004a04  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x180004a08  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180004a0d  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180004a12  jmp     short loc_1800049B8
0x180004a14  mov     ebx, 80070057h
0x180004a19  jmp     short loc_1800049BA
0x180004a1b  lea     rcx, [rsp+0B00h+var_AD0]; this
0x180004a20  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180004a25  mov     eax, edi
0x180004a27  mov     rcx, [rbp+0A00h+var_40]
0x180004a2e  xor     rcx, rsp; StackCookie
0x180004a31  call    __security_check_cookie
0x180004a36  mov     rbx, [rsp+0B00h+arg_10]
0x180004a3e  add     rsp, 0AD0h
0x180004a45  pop     r15
0x180004a47  pop     r14
0x180004a49  pop     r13
0x180004a4b  pop     r12
0x180004a4d  pop     rdi
0x180004a4e  pop     rsi
0x180004a4f  pop     rbp
0x180004a50  retn
0x180004a51  call    __report_rangecheckfailure
```
