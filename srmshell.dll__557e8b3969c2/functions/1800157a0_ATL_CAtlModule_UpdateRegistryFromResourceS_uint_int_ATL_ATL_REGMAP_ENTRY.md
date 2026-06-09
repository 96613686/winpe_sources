# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800157a0`
- end: `0x180015ac1`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `801`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, __int64, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015790`

## callees

- `0x180001c38`
- `0x18000968c`
- `0x18001202c`
- `0x1800122cc`
- `0x180012e1c`
- `0x180014950`
- `0x1800157a0`
- `0x18001b420`
- `0x180020010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001596a`
- `msvcrt!memcpy_s` at `0x18001596a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180015869`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180015869`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800158e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800158e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001591f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800159e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001591f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800159e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800158f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800159b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a02`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800158f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800159b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a02`

## string_xrefs

- `0x180015a56`: `REGISTRY`
- `0x180015a74`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        __int64 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  struct ATL::CAtlModule *v5; // rdi
  signed int v6; // ebx
  HMODULE v7; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned int Error; // eax
  WCHAR *v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 v12; // r8
  int v13; // ebx
  __int64 v14; // rbx
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  int v17; // ebx
  const unsigned __int16 *v18; // r8
  void **v20; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+60h] [rbp-A0h] BYREF
  char v24; // [rsp+88h] [rbp-78h]
  _QWORD *v25; // [rsp+90h] [rbp-70h]
  __int64 v26; // [rsp+98h] [rbp-68h]
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 Source[520]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v29; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE Destination[1054]; // [rsp+6C2h] [rbp+5C2h] BYREF

  v5 = ATL::_pAtlModule;
  v20 = &ATL::CRegObject::`vftable';
  v25 = v21;
  v21[0] = 0;
  v21[1] = 0;
  v22 = 0;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v24 = 0;
  v6 = ATL::CComCriticalSection::Init(&CriticalSection);
  if ( v6 >= 0 )
  {
    v24 = 1;
    v6 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, void ***))(*(_QWORD *)v5 + 40LL))(v5, &v20);
    if ( v6 >= 0 )
    {
      v26 = 0;
      v7 = hInstance;
      ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
      if ( !ModuleFileNameW )
      {
        Error = ATL::AtlHresultFromLastError();
LABEL_5:
        v6 = Error;
        goto LABEL_30;
      }
      if ( ModuleFileNameW == 260 )
      {
        v6 = -2147024774;
        goto LABEL_30;
      }
      v10 = Filename;
      v11 = 0;
      do
      {
        v12 = *v10;
        if ( !*v10 )
          break;
        Source[v11] = v12;
        if ( v12 == 39 && (unsigned int)v11 < 0x206 )
        {
          LODWORD(v11) = v11 + 1;
          Source[(unsigned int)v11] = 39;
        }
        ++v10;
        v11 = (unsigned int)(v11 + 1);
      }
      while ( (unsigned int)v11 < 0x207 );
      Source[v11] = 0;
      if ( !v7 || v7 == GetModuleHandleW(0) )
      {
        v29 = 34;
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( Source[v15] );
        if ( memcpy_s(Destination, 0x414u, Source, 2LL * ((int)v15 + 1)) )
        {
          v6 = -2147467259;
          goto LABEL_30;
        }
        do
          ++v14;
        while ( *(_WORD *)&Destination[2 * v14 - 2] );
        *(_WORD *)&Destination[2 * (int)v14 - 2] = 34;
        v16 = 2LL * (int)v14 + 2;
        if ( v16 >= 0x418 )
          _report_rangecheckfailure();
        *(_WORD *)&Destination[v16 - 2] = 0;
        EnterCriticalSection(&CriticalSection);
        v13 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v21, L"Module", &v29);
        LeaveCriticalSection(&CriticalSection);
      }
      else
      {
        EnterCriticalSection(&CriticalSection);
        v13 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v21, L"Module", Source);
        LeaveCriticalSection(&CriticalSection);
      }
      v6 = v13 == 0 ? 0x8007000E : 0;
      if ( v6 < 0 )
        goto LABEL_30;
      EnterCriticalSection(&CriticalSection);
      v17 = ATL::CExpansionVector::Add((ATL::CExpansionVector *)v21, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = v17 == 0 ? 0x8007000E : 0;
      if ( !v17 )
        goto LABEL_5;
      if ( a3 )
        v6 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v20, Filename, v18, L"REGISTRY", 1);
      else
        v6 = ATL::CRegObject::RegisterFromResource((ATL::CRegObject *)&v20, Filename, v18, L"REGISTRY", 0);
    }
  }
LABEL_30:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800157a0  push    rbp
0x1800157a2  push    rbx
0x1800157a3  push    rsi
0x1800157a4  push    rdi
0x1800157a5  push    r14
0x1800157a7  lea     rbp, [rsp-9F0h]
0x1800157af  sub     rsp, 0AF0h
0x1800157b6  mov     rax, cs:__security_cookie
0x1800157bd  xor     rax, rsp
0x1800157c0  mov     [rbp+0A10h+var_30], rax
0x1800157c7  mov     esi, r8d
0x1800157ca  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800157d1  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x1800157d8  mov     [rsp+0B10h+var_AD0], rax
0x1800157dd  lea     rax, [rsp+0B10h+var_AC8]
0x1800157e2  mov     [rbp+0A10h+var_A80], rax
0x1800157e6  xor     r14d, r14d
0x1800157e9  mov     [rsp+0B10h+var_AC8], r14
0x1800157ee  mov     [rsp+0B10h+var_AC0], r14
0x1800157f3  mov     [rsp+0B10h+var_AB8], r14d
0x1800157f8  lea     rax, [rsp+0B10h+CriticalSection]
0x1800157fd  mov     [rsp+0B10h+var_AE0], rax
0x180015802  xorps   xmm0, xmm0
0x180015805  xor     eax, eax
0x180015807  movups  xmmword ptr [rsp+0B10h+CriticalSection.DebugInfo], xmm0
0x18001580c  movups  xmmword ptr [rsp+0B10h+CriticalSection.OwningThread], xmm0
0x180015811  mov     [rbp+0A10h+CriticalSection.SpinCount], rax
0x180015815  mov     [rbp+0A10h+var_A88], r14b
0x180015819  lea     rcx, [rsp+0B10h+CriticalSection]; this
0x18001581e  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180015823  mov     ebx, eax
0x180015825  test    eax, eax
0x180015827  js      loc_180015A92
0x18001582d  mov     [rbp+0A10h+var_A88], 1
0x180015831  mov     rax, [rdi]
0x180015834  lea     rdx, [rsp+0B10h+var_AD0]
0x180015839  mov     rcx, rdi
0x18001583c  mov     rax, [rax+28h]
0x180015840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015845  mov     ebx, eax
0x180015847  test    eax, eax
0x180015849  js      loc_180015A92
0x18001584f  mov     [rbp+0A10h+var_A78], r14
0x180015853  mov     rbx, cs:hInstance
0x18001585a  mov     edi, 104h
0x18001585f  mov     r8d, edi; nSize
0x180015862  lea     rdx, [rbp+0A10h+Filename]; lpFilename
0x180015866  mov     rcx, rbx; hModule
0x180015869  call    cs:__imp_GetModuleFileNameW
0x18001586f  test    eax, eax
0x180015871  jnz     short loc_180015880
0x180015873  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180015878  nop
0x180015879  mov     ebx, eax
0x18001587b  jmp     loc_180015A92
0x180015880  cmp     eax, edi
0x180015882  jnz     short loc_18001588E
0x180015884  mov     ebx, 8007007Ah
0x180015889  jmp     loc_180015A92
0x18001588e  lea     rdx, [rbp+0A10h+Filename]
0x180015892  mov     ecx, r14d
0x180015895  mov     r9d, 27h ; '''
0x18001589b  movzx   r8d, word ptr [rdx]
0x18001589f  test    r8w, r8w
0x1800158a3  jz      short loc_1800158D5
0x1800158a5  mov     [rbp+rcx*2+0A10h+Source], r8w
0x1800158ae  cmp     r8w, r9w
0x1800158b2  jnz     short loc_1800158C7
0x1800158b4  cmp     ecx, 206h
0x1800158ba  jnb     short loc_1800158C7
0x1800158bc  inc     ecx
0x1800158be  mov     [rbp+rcx*2+0A10h+Source], r9w
0x1800158c7  add     rdx, 2
0x1800158cb  inc     ecx
0x1800158cd  cmp     ecx, 207h
0x1800158d3  jb      short loc_18001589B
0x1800158d5  mov     [rbp+rcx*2+0A10h+Source], r14w
0x1800158de  test    rbx, rbx
0x1800158e1  jz      short loc_18001592B
0x1800158e3  xor     ecx, ecx; lpModuleName
0x1800158e5  call    cs:__imp_GetModuleHandleW
0x1800158eb  cmp     rbx, rax
0x1800158ee  jz      short loc_18001592B
0x1800158f0  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x1800158f5  call    cs:__imp_EnterCriticalSection
0x1800158fb  mov     [rsp+0B10h+var_AE0], r14
0x180015900  lea     r8, [rbp+0A10h+Source]; unsigned __int16 *
0x180015907  lea     rdx, aModule; "Module"
0x18001590e  lea     rcx, [rsp+0B10h+var_AC8]; this
0x180015913  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180015918  mov     ebx, eax
0x18001591a  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x18001591f  call    cs:__imp_LeaveCriticalSection
0x180015925  nop
0x180015926  jmp     loc_1800159E8
0x18001592b  mov     edi, 22h ; '"'
0x180015930  mov     [rbp+0A10h+var_450], di
0x180015937  lea     rcx, [rbp+0A10h+Source]
0x18001593e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015942  mov     rax, rbx
0x180015945  inc     rax
0x180015948  cmp     [rcx+rax*2], r14w
0x18001594d  jnz     short loc_180015945
0x18001594f  inc     eax
0x180015951  movsxd  r9, eax
0x180015954  add     r9, r9; SourceSize
0x180015957  lea     r8, [rbp+0A10h+Source]; Source
0x18001595e  mov     edx, 414h; DestinationSize
0x180015963  lea     rcx, [rbp+0A10h+Destination]; Destination
0x18001596a  call    cs:__imp_memcpy_s
0x180015970  test    eax, eax
0x180015972  jnz     loc_180015A8D
0x180015978  lea     rax, [rbp+0A10h+var_450]
0x18001597f  inc     rbx
0x180015982  cmp     [rax+rbx*2], r14w
0x180015987  jnz     short loc_18001597F
0x180015989  movsxd  rax, ebx
0x18001598c  mov     [rbp+rax*2+0A10h+var_450], di
0x180015994  lea     rcx, ds:2[rax*2]
0x18001599c  cmp     rcx, 418h
0x1800159a3  jnb     loc_180015ABB
0x1800159a9  mov     [rbp+rcx+0A10h+var_450], r14w
0x1800159b2  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x1800159b7  call    cs:__imp_EnterCriticalSection
0x1800159bd  mov     [rsp+0B10h+var_AE0], r14
0x1800159c2  lea     r8, [rbp+0A10h+var_450]; unsigned __int16 *
0x1800159c9  lea     rdx, aModule; "Module"
0x1800159d0  lea     rcx, [rsp+0B10h+var_AC8]; this
0x1800159d5  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800159da  mov     ebx, eax
0x1800159dc  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x1800159e1  call    cs:__imp_LeaveCriticalSection
0x1800159e7  nop
0x1800159e8  neg     ebx
0x1800159ea  sbb     ebx, ebx
0x1800159ec  mov     edi, 8007000Eh
0x1800159f1  not     ebx
0x1800159f3  and     ebx, edi
0x1800159f5  test    ebx, ebx
0x1800159f7  js      loc_180015A8B
0x1800159fd  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180015a02  call    cs:__imp_EnterCriticalSection
0x180015a08  mov     [rsp+0B10h+var_AE0], r14
0x180015a0d  lea     r8, [rbp+0A10h+Source]; unsigned __int16 *
0x180015a14  lea     rdx, aModuleRaw; "Module_Raw"
0x180015a1b  lea     rcx, [rsp+0B10h+var_AC8]; this
0x180015a20  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180015a25  mov     ebx, eax
0x180015a27  lea     rcx, [rsp+0B10h+CriticalSection]; lpCriticalSection
0x180015a2c  call    cs:__imp_LeaveCriticalSection
0x180015a32  nop
0x180015a33  mov     ecx, ebx
0x180015a35  neg     ecx
0x180015a37  sbb     eax, eax
0x180015a39  not     eax
0x180015a3b  and     eax, edi
0x180015a3d  test    ebx, ebx
0x180015a3f  jz      loc_180015879
0x180015a45  mov     [rsp+0B10h+var_AE0], r14
0x180015a4a  test    esi, esi
0x180015a4c  jz      short loc_180015A6F
0x180015a4e  mov     [rsp+0B10h+var_AF0], 1; int
0x180015a56  lea     r9, aRegistry; "REGISTRY"
0x180015a5d  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180015a61  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180015a66  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180015a6b  mov     ebx, eax
0x180015a6d  jmp     short loc_180015A8B
0x180015a6f  mov     [rsp+0B10h+var_AF0], r14d; int
0x180015a74  lea     r9, aRegistry; "REGISTRY"
0x180015a7b  lea     rdx, [rbp+0A10h+Filename]; unsigned __int16 *
0x180015a7f  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180015a84  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x180015a89  mov     ebx, eax
0x180015a8b  jmp     short loc_180015A92
0x180015a8d  mov     ebx, 80004005h
0x180015a92  lea     rcx, [rsp+0B10h+var_AD0]; this
0x180015a97  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x180015a9c  mov     eax, ebx
0x180015a9e  mov     rcx, [rbp+0A10h+var_30]
0x180015aa5  xor     rcx, rsp; StackCookie
0x180015aa8  call    __security_check_cookie
0x180015aad  add     rsp, 0AF0h
0x180015ab4  pop     r14
0x180015ab6  pop     rdi
0x180015ab7  pop     rsi
0x180015ab8  pop     rbx
0x180015ab9  pop     rbp
0x180015aba  retn
0x180015abb  call    __report_rangecheckfailure
```
