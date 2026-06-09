# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000db0c`
- end: `0x18000de4a`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `830`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000de60`

## callees

- `0x180001dc8`
- `0x180008a9c`
- `0x180008e28`
- `0x1800098f4`
- `0x18000ac0c`
- `0x18000bfbc`
- `0x18000db0c`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000dcea`
- `msvcrt!memcpy_s` at `0x18000dcea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000dc0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000dc0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dc89`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dbc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dda1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dbc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dda1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dbad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dbad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dc99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dd7c`

## string_xrefs

- `0x18000ddd7`: `REGISTRY`

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
0x18000db0c  mov     [rsp-8+arg_10], rbx
0x18000db11  push    rbp
0x18000db12  push    rsi
0x18000db13  push    rdi
0x18000db14  push    r12
0x18000db16  push    r13
0x18000db18  push    r14
0x18000db1a  push    r15
0x18000db1c  lea     rbp, [rsp-9D0h]
0x18000db24  sub     rsp, 0AD0h
0x18000db2b  mov     rax, cs:__security_cookie
0x18000db32  xor     rax, rsp
0x18000db35  mov     [rbp+0A00h+var_40], rax
0x18000db3c  xor     r13d, r13d
0x18000db3f  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000db46  xorps   xmm0, xmm0
0x18000db49  mov     [rsp+0B00h+var_AD0], rax
0x18000db4e  xor     eax, eax
0x18000db50  mov     [rsp+0B00h+var_AC8], r13
0x18000db55  mov     r15, rcx
0x18000db58  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000db5d  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000db62  mov     [rsp+0B00h+var_AC0], r13
0x18000db67  mov     rbx, r9
0x18000db6a  mov     [rsp+0B00h+var_AB8], r13d
0x18000db6f  mov     r12d, r8d
0x18000db72  mov     [rsp+0B00h+var_A88], r13b
0x18000db77  mov     r14, rdx
0x18000db7a  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000db7f  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000db84  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000db89  mov     edi, eax
0x18000db8b  test    eax, eax
0x18000db8d  js      loc_18000DE0E
0x18000db93  mov     [rsp+0B00h+var_A88], 1
0x18000db98  test    rbx, rbx
0x18000db9b  jz      short loc_18000DBDA
0x18000db9d  jmp     short loc_18000DBD2
0x18000db9f  mov     rsi, [rbx+8]
0x18000dba3  test    rsi, rsi
0x18000dba6  jz      short loc_18000DBCE
0x18000dba8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000dbad  call    cs:__imp_EnterCriticalSection
0x18000dbb3  mov     r8, rsi; unsigned __int16 *
0x18000dbb6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000dbbb  mov     rdx, rdi; unsigned __int16 *
0x18000dbbe  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000dbc3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000dbc8  call    cs:__imp_LeaveCriticalSection
0x18000dbce  add     rbx, 10h
0x18000dbd2  mov     rdi, [rbx]
0x18000dbd5  test    rdi, rdi
0x18000dbd8  jnz     short loc_18000DB9F
0x18000dbda  mov     rax, [r15]
0x18000dbdd  lea     rdx, [rsp+0B00h+var_AD0]
0x18000dbe2  mov     rcx, r15
0x18000dbe5  mov     rax, [rax+28h]
0x18000dbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbee  mov     ebx, eax
0x18000dbf0  test    eax, eax
0x18000dbf2  js      loc_18000DE00
0x18000dbf8  mov     rbx, cs:hInstance
0x18000dbff  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000dc03  mov     edi, 104h
0x18000dc08  mov     rcx, rbx; hModule
0x18000dc0b  mov     r8d, edi; nSize
0x18000dc0e  call    cs:__imp_GetModuleFileNameW
0x18000dc14  test    eax, eax
0x18000dc16  jnz     short loc_18000DC24
0x18000dc18  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000dc1d  mov     ebx, eax
0x18000dc1f  jmp     loc_18000DE00
0x18000dc24  cmp     eax, edi
0x18000dc26  jnz     short loc_18000DC32
0x18000dc28  mov     ebx, 8007007Ah
0x18000dc2d  jmp     loc_18000DE00
0x18000dc32  lea     rdx, [rbp+0A00h+Filename]
0x18000dc36  mov     ecx, r13d
0x18000dc39  mov     r9d, 27h ; '''
0x18000dc3f  movzx   r8d, word ptr [rdx]
0x18000dc43  test    r8w, r8w
0x18000dc47  jz      short loc_18000DC79
0x18000dc49  mov     [rbp+rcx*2+0A00h+Source], r8w
0x18000dc52  cmp     r8w, r9w
0x18000dc56  jnz     short loc_18000DC6B
0x18000dc58  cmp     ecx, 206h
0x18000dc5e  jnb     short loc_18000DC6B
0x18000dc60  inc     ecx
0x18000dc62  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000dc6b  add     rdx, 2
0x18000dc6f  inc     ecx
0x18000dc71  cmp     ecx, 207h
0x18000dc77  jb      short loc_18000DC3F
0x18000dc79  mov     [rbp+rcx*2+0A00h+Source], r13w
0x18000dc82  test    rbx, rbx
0x18000dc85  jz      short loc_18000DCAB
0x18000dc87  xor     ecx, ecx; lpModuleName
0x18000dc89  call    cs:__imp_GetModuleHandleW
0x18000dc8f  cmp     rbx, rax
0x18000dc92  jz      short loc_18000DCAB
0x18000dc94  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000dc99  call    cs:__imp_EnterCriticalSection
0x18000dc9f  lea     r8, [rbp+0A00h+Source]
0x18000dca6  jmp     loc_18000DD44
0x18000dcab  mov     edi, 22h ; '"'
0x18000dcb0  lea     rcx, [rbp+0A00h+Source]
0x18000dcb7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000dcbb  mov     [rbp+0A00h+var_460], di
0x18000dcc2  mov     rax, rbx
0x18000dcc5  inc     rax
0x18000dcc8  cmp     [rcx+rax*2], r13w
0x18000dccd  jnz     short loc_18000DCC5
0x18000dccf  inc     eax
0x18000dcd1  lea     r8, [rbp+0A00h+Source]; Source
0x18000dcd8  movsxd  r9, eax
0x18000dcdb  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000dce2  add     r9, r9; SourceSize
0x18000dce5  mov     edx, 414h; DestinationSize
0x18000dcea  call    cs:__imp_memcpy_s
0x18000dcf0  test    eax, eax
0x18000dcf2  jnz     loc_18000DDFB
0x18000dcf8  lea     rax, [rbp+0A00h+var_460]
0x18000dcff  inc     rbx
0x18000dd02  cmp     [rax+rbx*2], r13w
0x18000dd07  jnz     short loc_18000DCFF
0x18000dd09  movsxd  rax, ebx
0x18000dd0c  lea     rcx, ds:2[rax*2]
0x18000dd14  mov     [rbp+rax*2+0A00h+var_460], di
0x18000dd1c  cmp     rcx, 418h
0x18000dd23  jnb     loc_18000DE44
0x18000dd29  mov     [rbp+rcx+0A00h+var_460], r13w
0x18000dd32  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000dd37  call    cs:__imp_EnterCriticalSection
0x18000dd3d  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000dd44  lea     rdx, aModule; "Module"
0x18000dd4b  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000dd50  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000dd55  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000dd5a  mov     ebx, eax
0x18000dd5c  call    cs:__imp_LeaveCriticalSection
0x18000dd62  neg     ebx
0x18000dd64  mov     edi, 8007000Eh
0x18000dd69  sbb     ebx, ebx
0x18000dd6b  not     ebx
0x18000dd6d  and     ebx, edi
0x18000dd6f  test    ebx, ebx
0x18000dd71  js      loc_18000DE00
0x18000dd77  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000dd7c  call    cs:__imp_EnterCriticalSection
0x18000dd82  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x18000dd89  lea     rdx, aModuleRaw; "Module_Raw"
0x18000dd90  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000dd95  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000dd9a  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000dd9f  mov     ebx, eax
0x18000dda1  call    cs:__imp_LeaveCriticalSection
0x18000dda7  mov     ecx, ebx
0x18000dda9  neg     ecx
0x18000ddab  sbb     eax, eax
0x18000ddad  not     eax
0x18000ddaf  and     eax, edi
0x18000ddb1  test    ebx, ebx
0x18000ddb3  jz      loc_18000DC1D
0x18000ddb9  test    r12d, r12d
0x18000ddbc  jz      short loc_18000DDCD
0x18000ddbe  test    r14, r14
0x18000ddc1  jz      short loc_18000DDF4
0x18000ddc3  mov     [rsp+0B00h+var_AE0], 1
0x18000ddcb  jmp     short loc_18000DDD7
0x18000ddcd  test    r14, r14
0x18000ddd0  jz      short loc_18000DDF4
0x18000ddd2  mov     [rsp+0B00h+var_AE0], r13d; int
0x18000ddd7  lea     r9, aRegistry; "REGISTRY"
0x18000ddde  mov     r8, r14; unsigned __int16 *
0x18000dde1  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000dde5  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000ddea  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000ddef  jmp     loc_18000DC1D
0x18000ddf4  mov     ebx, 80070057h
0x18000ddf9  jmp     short loc_18000DE00
0x18000ddfb  mov     ebx, 80004005h
0x18000de00  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000de05  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000de0a  mov     eax, ebx
0x18000de0c  jmp     short loc_18000DE1A
0x18000de0e  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000de13  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000de18  mov     eax, edi
0x18000de1a  mov     rcx, [rbp+0A00h+var_40]
0x18000de21  xor     rcx, rsp; StackCookie
0x18000de24  call    __security_check_cookie
0x18000de29  mov     rbx, [rsp+0B00h+arg_10]
0x18000de31  add     rsp, 0AD0h
0x18000de38  pop     r15
0x18000de3a  pop     r14
0x18000de3c  pop     r13
0x18000de3e  pop     r12
0x18000de40  pop     rdi
0x18000de41  pop     rsi
0x18000de42  pop     rbp
0x18000de43  retn
0x18000de44  call    __report_rangecheckfailure
```
