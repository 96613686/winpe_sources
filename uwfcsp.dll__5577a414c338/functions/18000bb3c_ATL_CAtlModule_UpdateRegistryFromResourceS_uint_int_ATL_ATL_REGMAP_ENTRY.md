# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000bb3c`
- end: `0x18000be53`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `791`
- prototype: `__int64 __fastcall(ATL::CAtlModule *this, unsigned __int16, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c1a0`

## callees

- `0x180003da8`
- `0x180007df8`
- `0x180008358`
- `0x180008c58`
- `0x1800094e8`
- `0x18000a348`
- `0x18000bb3c`
- `0x18001a210`
- `0x18001b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bd0e`
- `msvcrt!memcpy_s` at `0x18000bd0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bc41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bc41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bcb6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000bcb6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bbf8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bdbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bbf8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bd80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bdbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bbdd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bcc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bd5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bd9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bbdd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bcc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bd5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bd9c`

## string_xrefs

- `0x18000bde0`: `REGISTRY`

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
  BOOL v22; // ebx
  BOOL v23; // ebx
  void **v25; // [rsp+30h] [rbp-D0h] BYREF
  void *v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  _RTL_CRITICAL_SECTION CriticalSection; // [rsp+50h] [rbp-B0h] BYREF
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
          ATL::CExpansionVector::Add(v26, v10, v9);
          LeaveCriticalSection(&CriticalSection);
        }
        a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
      }
    }
    v11 = (*(__int64 (__fastcall **)(ATL::CAtlModule *, void ***))(*(_QWORD *)this + 40LL))(this, &v25);
    if ( v11 < 0 )
      goto LABEL_33;
    v12 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
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
      v22 = ATL::CExpansionVector::Add(v26, L"Module", v18);
      LeaveCriticalSection(&CriticalSection);
      v11 = !v22 ? 0x8007000E : 0;
      if ( v11 < 0 )
      {
LABEL_33:
        ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v25);
        return (unsigned int)v11;
      }
      EnterCriticalSection(&CriticalSection);
      v23 = ATL::CExpansionVector::Add(v26, L"Module_Raw", Source);
      LeaveCriticalSection(&CriticalSection);
      Error = !v23 ? 0x8007000E : 0;
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
0x18000bb3c  mov     [rsp-8+arg_10], rbx
0x18000bb41  push    rbp
0x18000bb42  push    rsi
0x18000bb43  push    rdi
0x18000bb44  push    r12
0x18000bb46  push    r13
0x18000bb48  push    r14
0x18000bb4a  push    r15
0x18000bb4c  lea     rbp, [rsp-9D0h]
0x18000bb54  sub     rsp, 0AD0h
0x18000bb5b  mov     rax, cs:__security_cookie
0x18000bb62  xor     rax, rsp
0x18000bb65  mov     [rbp+0A00h+var_40], rax
0x18000bb6c  xor     r13d, r13d
0x18000bb6f  mov     r12d, edx
0x18000bb72  xorps   xmm0, xmm0
0x18000bb75  mov     [rsp+0B00h+var_AC8], r13
0x18000bb7a  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18000bb81  mov     [rsp+0B00h+var_AC0], r13
0x18000bb86  mov     [rsp+0B00h+var_AD0], rax
0x18000bb8b  mov     r14, rcx
0x18000bb8e  xor     eax, eax
0x18000bb90  mov     [rsp+0B00h+var_AB8], r13d
0x18000bb95  lea     rcx, [rsp+0B00h+CriticalSection]; this
0x18000bb9a  mov     [rsp+0B00h+CriticalSection.SpinCount], rax
0x18000bb9f  mov     rbx, r9
0x18000bba2  mov     [rsp+0B00h+var_A88], r13b
0x18000bba7  mov     r15d, r8d
0x18000bbaa  movups  xmmword ptr [rsp+0B00h+CriticalSection.DebugInfo], xmm0
0x18000bbaf  movups  xmmword ptr [rsp+0B00h+CriticalSection.OwningThread], xmm0
0x18000bbb4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000bbb9  mov     edi, eax
0x18000bbbb  test    eax, eax
0x18000bbbd  js      loc_18000BE17
0x18000bbc3  mov     [rsp+0B00h+var_A88], 1
0x18000bbc8  test    rbx, rbx
0x18000bbcb  jz      short loc_18000BC0A
0x18000bbcd  jmp     short loc_18000BC02
0x18000bbcf  mov     rsi, [rbx+8]
0x18000bbd3  test    rsi, rsi
0x18000bbd6  jz      short loc_18000BBFE
0x18000bbd8  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bbdd  call    cs:__imp_EnterCriticalSection
0x18000bbe3  mov     r8, rsi; unsigned __int16 *
0x18000bbe6  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000bbeb  mov     rdx, rdi; unsigned __int16 *
0x18000bbee  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000bbf3  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bbf8  call    cs:__imp_LeaveCriticalSection
0x18000bbfe  add     rbx, 10h
0x18000bc02  mov     rdi, [rbx]
0x18000bc05  test    rdi, rdi
0x18000bc08  jnz     short loc_18000BBCF
0x18000bc0a  mov     rax, [r14]
0x18000bc0d  lea     rdx, [rsp+0B00h+var_AD0]
0x18000bc12  mov     rcx, r14
0x18000bc15  mov     rax, [rax+28h]
0x18000bc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc1e  mov     ebx, eax
0x18000bc20  test    eax, eax
0x18000bc22  js      loc_18000BE09
0x18000bc28  mov     rbx, cs:hModule
0x18000bc2f  lea     rdx, [rbp+0A00h+Filename]; lpFilename
0x18000bc36  mov     edi, 104h
0x18000bc3b  mov     rcx, rbx; hModule
0x18000bc3e  mov     r8d, edi; nSize
0x18000bc41  call    cs:__imp_GetModuleFileNameW
0x18000bc47  test    eax, eax
0x18000bc49  jnz     short loc_18000BC57
0x18000bc4b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bc50  mov     ebx, eax
0x18000bc52  jmp     loc_18000BE09
0x18000bc57  cmp     eax, edi
0x18000bc59  jnz     short loc_18000BC65
0x18000bc5b  mov     ebx, 8007007Ah
0x18000bc60  jmp     loc_18000BE09
0x18000bc65  lea     rdx, [rbp+0A00h+Filename]
0x18000bc6c  mov     ecx, r13d
0x18000bc6f  mov     r9d, 27h ; '''
0x18000bc75  movzx   r8d, word ptr [rdx]
0x18000bc79  test    r8w, r8w
0x18000bc7d  jz      short loc_18000BCA9
0x18000bc7f  mov     [rbp+rcx*2+0A00h+Source], r8w
0x18000bc85  cmp     r8w, r9w
0x18000bc89  jnz     short loc_18000BC9B
0x18000bc8b  cmp     ecx, 206h
0x18000bc91  jnb     short loc_18000BC9B
0x18000bc93  inc     ecx
0x18000bc95  mov     [rbp+rcx*2+0A00h+Source], r9w
0x18000bc9b  add     rdx, 2
0x18000bc9f  inc     ecx
0x18000bca1  cmp     ecx, 207h
0x18000bca7  jb      short loc_18000BC75
0x18000bca9  mov     [rbp+rcx*2+0A00h+Source], r13w
0x18000bcaf  test    rbx, rbx
0x18000bcb2  jz      short loc_18000BCD5
0x18000bcb4  xor     ecx, ecx; lpModuleName
0x18000bcb6  call    cs:__imp_GetModuleHandleW
0x18000bcbc  cmp     rbx, rax
0x18000bcbf  jz      short loc_18000BCD5
0x18000bcc1  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bcc6  call    cs:__imp_EnterCriticalSection
0x18000bccc  lea     r8, [rbp+0A00h+Source]
0x18000bcd0  jmp     loc_18000BD68
0x18000bcd5  mov     edi, 22h ; '"'
0x18000bcda  lea     rcx, [rbp+0A00h+Source]
0x18000bcde  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bce2  mov     [rbp+0A00h+var_460], di
0x18000bce9  mov     rax, rbx
0x18000bcec  inc     rax
0x18000bcef  cmp     [rcx+rax*2], r13w
0x18000bcf4  jnz     short loc_18000BCEC
0x18000bcf6  inc     eax
0x18000bcf8  lea     r8, [rbp+0A00h+Source]; Source
0x18000bcfc  movsxd  r9, eax
0x18000bcff  lea     rcx, [rbp+0A00h+Destination]; Destination
0x18000bd06  add     r9, r9; SourceSize
0x18000bd09  mov     edx, 414h; DestinationSize
0x18000bd0e  call    cs:__imp_memcpy_s
0x18000bd14  test    eax, eax
0x18000bd16  jnz     loc_18000BE04
0x18000bd1c  lea     rax, [rbp+0A00h+var_460]
0x18000bd23  inc     rbx
0x18000bd26  cmp     [rax+rbx*2], r13w
0x18000bd2b  jnz     short loc_18000BD23
0x18000bd2d  movsxd  rax, ebx
0x18000bd30  lea     rcx, ds:2[rax*2]
0x18000bd38  mov     [rbp+rax*2+0A00h+var_460], di
0x18000bd40  cmp     rcx, 418h
0x18000bd47  jnb     loc_18000BE4D
0x18000bd4d  mov     [rbp+rcx+0A00h+var_460], r13w
0x18000bd56  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bd5b  call    cs:__imp_EnterCriticalSection
0x18000bd61  lea     r8, [rbp+0A00h+var_460]; unsigned __int16 *
0x18000bd68  lea     rdx, aModule; "Module"
0x18000bd6f  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000bd74  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000bd79  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bd7e  mov     ebx, eax
0x18000bd80  call    cs:__imp_LeaveCriticalSection
0x18000bd86  neg     ebx
0x18000bd88  mov     edi, 8007000Eh
0x18000bd8d  sbb     ebx, ebx
0x18000bd8f  not     ebx
0x18000bd91  and     ebx, edi
0x18000bd93  test    ebx, ebx
0x18000bd95  js      short loc_18000BE09
0x18000bd97  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bd9c  call    cs:__imp_EnterCriticalSection
0x18000bda2  lea     r8, [rbp+0A00h+Source]; unsigned __int16 *
0x18000bda6  lea     rdx, aModuleRaw; "Module_Raw"
0x18000bdad  lea     rcx, [rsp+0B00h+var_AC8]; this
0x18000bdb2  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x18000bdb7  lea     rcx, [rsp+0B00h+CriticalSection]; lpCriticalSection
0x18000bdbc  mov     ebx, eax
0x18000bdbe  call    cs:__imp_LeaveCriticalSection
0x18000bdc4  mov     ecx, ebx
0x18000bdc6  neg     ecx
0x18000bdc8  sbb     eax, eax
0x18000bdca  not     eax
0x18000bdcc  and     eax, edi
0x18000bdce  test    ebx, ebx
0x18000bdd0  jz      loc_18000BC50
0x18000bdd6  mov     eax, r13d
0x18000bdd9  movzx   r8d, r12w; unsigned __int16 *
0x18000bddd  test    r15d, r15d
0x18000bde0  lea     r9, aRegistry; "REGISTRY"
0x18000bde7  lea     rdx, [rbp+0A00h+Filename]; unsigned __int16 *
0x18000bdee  setnz   al
0x18000bdf1  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000bdf6  mov     [rsp+0B00h+var_AE0], eax; int
0x18000bdfa  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18000bdff  jmp     loc_18000BC50
0x18000be04  mov     ebx, 80004005h
0x18000be09  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000be0e  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000be13  mov     eax, ebx
0x18000be15  jmp     short loc_18000BE23
0x18000be17  lea     rcx, [rsp+0B00h+var_AD0]; this
0x18000be1c  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18000be21  mov     eax, edi
0x18000be23  mov     rcx, [rbp+0A00h+var_40]
0x18000be2a  xor     rcx, rsp; StackCookie
0x18000be2d  call    __security_check_cookie
0x18000be32  mov     rbx, [rsp+0B00h+arg_10]
0x18000be3a  add     rsp, 0AD0h
0x18000be41  pop     r15
0x18000be43  pop     r14
0x18000be45  pop     r13
0x18000be47  pop     r12
0x18000be49  pop     rdi
0x18000be4a  pop     rsi
0x18000be4b  pop     rbp
0x18000be4c  retn
0x18000be4d  call    __report_rangecheckfailure
```
