# ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18001ae4c`
- end: `0x18001b0c4`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `632`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `9`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ad40`
- `0x18001ad60`
- `0x18001ad80`
- `0x18001ada0`
- `0x18001adc0`
- `0x18001ade0`
- `0x18001ae00`
- `0x18001ae20`
- `0x18001b360`

## callees

- `0x180005c20`
- `0x180013a68`
- `0x180015290`
- `0x1800158f0`
- `0x1800161a0`
- `0x180016a68`
- `0x180018798`
- `0x180019e70`
- `0x18001ae4c`
- `0x18001b5c0`
- `0x18002dec0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001af5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001af5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001af9f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001af9f`

## string_xrefs

- `0x18001b087`: `REGISTRY`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResourceS(
        ATL::CAtlModule *this,
        unsigned __int16 a2,
        int a3,
        struct ATL::_ATL_REGMAP_ENTRY *a4)
{
  int v8; // edi
  int Error; // ebx
  HMODULE v11; // rbx
  DWORD ModuleFileNameW; // eax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned __int16 *v15; // r8
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  int v18; // eax
  _QWORD *v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+58h] [rbp-A8h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25; // [rsp+88h] [rbp-78h]
  __int64 v26; // [rsp+90h] [rbp-70h]
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v28; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v29[527]; // [rsp+2B2h] [rbp+1B2h] BYREF
  unsigned __int16 v30[520]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v26 = -2;
  v21[0] = &ATL::CRegObject::`vftable';
  v21[1] = 0;
  v21[2] = 0;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  v8 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)v23);
  if ( v8 < 0 )
  {
    ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
    return (unsigned int)v8;
  }
  if ( a4 )
  {
    while ( *(_QWORD *)a4 )
    {
      ATL::CRegObject::AddReplacement(
        (ATL::CRegObject *)v21,
        *(const unsigned __int16 **)a4,
        *((const unsigned __int16 **)a4 + 1));
      a4 = (struct ATL::_ATL_REGMAP_ENTRY *)((char *)a4 + 16);
    }
  }
  Error = (*(__int64 (__fastcall **)(ATL::CAtlModule *, _QWORD *))(*(_QWORD *)this + 40LL))(this, v21);
  if ( Error >= 0 )
  {
    v19 = 0;
    v11 = hModule;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( !ModuleFileNameW )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_23:
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
      goto LABEL_24;
    }
    if ( ModuleFileNameW != 260 )
    {
      ATL::CAtlModule::EscapeSingleQuote(v30, v13, Filename);
      if ( !v11 || v11 == GetModuleHandleW(0) )
      {
        v28 = 34;
        if ( !ocscpy_s(v29, v14, v30) )
        {
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
          Error = -2147467259;
          goto LABEL_24;
        }
        v16 = -1;
        do
          ++v16;
        while ( v29[v16 - 1] );
        v29[(int)v16 - 1] = 34;
        v17 = 2LL * (int)v16 + 2;
        if ( v17 >= 0x418 )
          _report_rangecheckfailure();
        *(unsigned __int16 *)((char *)&v29[-1] + v17) = 0;
        v15 = &v28;
      }
      else
      {
        v15 = v30;
      }
      Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module", v15);
      if ( Error >= 0 )
      {
        Error = ATL::CRegObject::AddReplacement((ATL::CRegObject *)v21, L"Module_Raw", v30);
        if ( Error >= 0 )
        {
          v20 = 0;
          if ( a3 )
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    1);
          else
            v18 = ATL::CRegObject::RegisterFromResource(
                    (ATL::CRegObject *)v21,
                    Filename,
                    (const unsigned __int16 *)a2,
                    L"REGISTRY",
                    0);
          Error = v18;
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
        }
      }
      goto LABEL_23;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
    Error = -2147024774;
  }
LABEL_24:
  ATL::CRegObject::~CRegObject((ATL::CRegObject *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001ae4c  push    rbp
0x18001ae4e  push    rbx
0x18001ae4f  push    rsi
0x18001ae50  push    rdi
0x18001ae51  push    r12
0x18001ae53  push    r14
0x18001ae55  push    r15
0x18001ae57  lea     rbp, [rsp-9F0h]
0x18001ae5f  sub     rsp, 0AF0h
0x18001ae66  mov     [rbp+0A20h+var_A90], 0FFFFFFFFFFFFFFFEh
0x18001ae6e  mov     rax, cs:__security_cookie
0x18001ae75  xor     rax, rsp
0x18001ae78  mov     [rbp+0A20h+var_40], rax
0x18001ae7f  mov     rbx, r9
0x18001ae82  mov     r14d, r8d
0x18001ae85  mov     r15d, edx
0x18001ae88  mov     rsi, rcx
0x18001ae8b  lea     rax, ??_7CRegObject@ATL@@6B@; const ATL::CRegObject::`vftable'
0x18001ae92  mov     [rsp+0B20h+var_AE0], rax
0x18001ae97  xor     r12d, r12d
0x18001ae9a  mov     [rsp+0B20h+var_AD8], r12
0x18001ae9f  mov     [rsp+0B20h+var_AD0], r12
0x18001aea4  mov     [rsp+0B20h+var_AC8], r12d
0x18001aea9  xorps   xmm0, xmm0
0x18001aeac  xor     eax, eax
0x18001aeae  movups  [rsp+0B20h+var_AC0], xmm0
0x18001aeb3  movups  [rsp+0B20h+var_AB0], xmm0
0x18001aeb8  mov     [rbp+0A20h+var_AA0], rax
0x18001aebc  mov     [rbp+0A20h+var_A98], r12b
0x18001aec0  lea     rcx, [rsp+0B20h+var_AC0]; this
0x18001aec5  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x18001aeca  mov     edi, eax
0x18001aecc  test    eax, eax
0x18001aece  jns     short loc_18001AEFD
0x18001aed0  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001aed5  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001aeda  mov     eax, edi
0x18001aedc  mov     rcx, [rbp+0A20h+var_40]
0x18001aee3  xor     rcx, rsp; StackCookie
0x18001aee6  call    __security_check_cookie
0x18001aeeb  add     rsp, 0AF0h
0x18001aef2  pop     r15
0x18001aef4  pop     r14
0x18001aef6  pop     r12
0x18001aef8  pop     rdi
0x18001aef9  pop     rsi
0x18001aefa  pop     rbx
0x18001aefb  pop     rbp
0x18001aefc  retn
0x18001aefd  test    rbx, rbx
0x18001af00  jz      short loc_18001AF21
0x18001af02  jmp     short loc_18001AF19
0x18001af04  mov     r8, [rbx+8]; unsigned __int16 *
0x18001af08  mov     rdx, rax; unsigned __int16 *
0x18001af0b  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001af10  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001af15  lea     rbx, [rbx+10h]
0x18001af19  mov     rax, [rbx]
0x18001af1c  test    rax, rax
0x18001af1f  jnz     short loc_18001AF04
0x18001af21  mov     rax, [rsi]
0x18001af24  lea     rdx, [rsp+0B20h+var_AE0]
0x18001af29  mov     rcx, rsi
0x18001af2c  mov     rax, [rax+28h]
0x18001af30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af35  mov     ebx, eax
0x18001af37  test    eax, eax
0x18001af39  js      loc_18001B06D
0x18001af3f  mov     [rsp+0B20h+var_AF0], r12
0x18001af44  mov     rbx, cs:hModule
0x18001af4b  mov     edi, 104h
0x18001af50  mov     r8d, edi; nSize
0x18001af53  lea     rdx, [rbp+0A20h+Filename]; lpFilename
0x18001af57  mov     rcx, rbx; hModule
0x18001af5a  call    cs:__imp_GetModuleFileNameW
0x18001af60  test    eax, eax
0x18001af62  jnz     short loc_18001AF70
0x18001af64  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001af69  mov     ebx, eax
0x18001af6b  jmp     loc_18001B063
0x18001af70  cmp     eax, edi
0x18001af72  jnz     short loc_18001AF88
0x18001af74  lea     rcx, [rsp+0B20h+var_AF0]
0x18001af79  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001af7e  mov     ebx, 8007007Ah
0x18001af83  jmp     loc_18001B06D
0x18001af88  lea     r8, [rbp+0A20h+Filename]; unsigned __int16 *
0x18001af8c  lea     rcx, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001af93  call    ?EscapeSingleQuote@CAtlModule@ATL@@SAXPEAG_KPEBG@Z; ATL::CAtlModule::EscapeSingleQuote(ushort *,unsigned __int64,ushort const *)
0x18001af98  test    rbx, rbx
0x18001af9b  jz      short loc_18001AFB3
0x18001af9d  xor     ecx, ecx; lpModuleName
0x18001af9f  call    cs:__imp_GetModuleHandleW
0x18001afa5  cmp     rbx, rax
0x18001afa8  jz      short loc_18001AFB3
0x18001afaa  lea     r8, [rbp+0A20h+var_450]
0x18001afb1  jmp     short loc_18001B02E
0x18001afb3  mov     ebx, 22h ; '"'
0x18001afb8  mov     [rbp+0A20h+var_870], bx
0x18001afbf  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001afc6  lea     rcx, [rbp+0A20h+var_86E]; unsigned __int16 *
0x18001afcd  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x18001afd2  test    al, al
0x18001afd4  jnz     short loc_18001AFEA
0x18001afd6  lea     rcx, [rsp+0B20h+var_AF0]
0x18001afdb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001afe0  mov     ebx, 80004005h
0x18001afe5  jmp     loc_18001B06D
0x18001afea  lea     rcx, [rbp+0A20h+var_870]
0x18001aff1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001aff5  inc     rax
0x18001aff8  cmp     [rcx+rax*2], r12w
0x18001affd  jnz     short loc_18001AFF5
0x18001afff  cdqe
0x18001b001  mov     [rbp+rax*2+0A20h+var_870], bx
0x18001b009  lea     rcx, ds:2[rax*2]
0x18001b011  cmp     rcx, 418h
0x18001b018  jnb     loc_18001B0BE
0x18001b01e  mov     [rbp+rcx+0A20h+var_870], r12w
0x18001b027  lea     r8, [rbp+0A20h+var_870]; unsigned __int16 *
0x18001b02e  lea     rdx, aModule; "Module"
0x18001b035  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b03a  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001b03f  mov     ebx, eax
0x18001b041  test    eax, eax
0x18001b043  js      short loc_18001B063
0x18001b045  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x18001b04c  lea     rdx, aModuleRaw; "Module_Raw"
0x18001b053  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b058  call    ?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x18001b05d  mov     ebx, eax
0x18001b05f  test    eax, eax
0x18001b061  jns     short loc_18001B07E
0x18001b063  lea     rcx, [rsp+0B20h+var_AF0]
0x18001b068  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001b06d  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b072  call    ??1CRegObject@ATL@@UEAA@XZ; ATL::CRegObject::~CRegObject(void)
0x18001b077  mov     eax, ebx
0x18001b079  jmp     loc_18001AEDC
0x18001b07e  movzx   r8d, r15w; unsigned __int16 *
0x18001b082  mov     [rsp+0B20h+var_AE8], r12
0x18001b087  lea     r9, aRegistry; "REGISTRY"
0x18001b08e  lea     rdx, [rbp+0A20h+Filename]; unsigned __int16 *
0x18001b092  lea     rcx, [rsp+0B20h+var_AE0]; this
0x18001b097  test    r14d, r14d
0x18001b09a  jz      short loc_18001B0A6
0x18001b09c  mov     [rsp+0B20h+var_B00], 1
0x18001b0a4  jmp     short loc_18001B0AB
0x18001b0a6  mov     [rsp+0B20h+var_B00], r12d; int
0x18001b0ab  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)
0x18001b0b0  mov     ebx, eax
0x18001b0b2  lea     rcx, [rsp+0B20h+var_AE8]
0x18001b0b7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001b0bc  jmp     short loc_18001B063
0x18001b0be  call    __report_rangecheckfailure
```
