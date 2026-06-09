# Settings::GetDevicePropertyAsMultiSz(Autoplay::IDeviceProperties *,ushort const *,_WORD_BLOB * *)

- ea: `0x180005e80`
- end: `0x18000601c`
- name: `?GetDevicePropertyAsMultiSz@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAPEAU_WORD_BLOB@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(Settings *this, struct Autoplay::IDeviceProperties *, unsigned __int16 *, struct _WORD_BLOB **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019280`
- `0x18002b780`

## callees

- `0x180005010`
- `0x180005e80`
- `0x180006024`
- `0x1800062e0`
- `0x180006470`
- `0x180006578`
- `0x18002ecec`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005f9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005f9e`

## pseudocode

```c
__int64 __fastcall Settings::GetDevicePropertyAsMultiSz(
        Settings *this,
        struct Autoplay::IDeviceProperties *a2,
        unsigned __int16 *a3,
        struct _WORD_BLOB **a4)
{
  __int64 v4; // rax
  int DeviceGroupPropertySizeHelper; // ebx
  int v9; // eax
  unsigned int *v10; // r9
  _DWORD *v11; // rax
  void *v12; // rdi
  int v13; // r10d
  unsigned __int8 *v15; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  void **v17; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+50h] [rbp-B0h]
  struct Autoplay::IDeviceProperties *v20; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v21; // [rsp+60h] [rbp-A0h]
  _BYTE v22[528]; // [rsp+70h] [rbp-90h] BYREF

  v4 = *(_QWORD *)this;
  *(_DWORD *)v16 = 0;
  DeviceGroupPropertySizeHelper = (*(__int64 (__fastcall **)(Settings *, struct Autoplay::IDeviceProperties *, unsigned __int16 *, struct _WORD_BLOB **))(v4 + 56))(
                                    this,
                                    a2,
                                    v16,
                                    a4);
  if ( DeviceGroupPropertySizeHelper == -2147467259 )
  {
    v19 = -2147467259;
    v17 = &Settings::CMultiDeviceGroupSinglePropertySize::`vftable';
    v20 = a2;
    v21 = v16;
    v18 = 0;
    DeviceGroupPropertySizeHelper = Settings::CMultiDeviceGroupEnum::Init((Settings::CMultiDeviceGroupEnum *)&v18, this);
    if ( DeviceGroupPropertySizeHelper >= 0 )
      DeviceGroupPropertySizeHelper = Settings::CMultiDeviceGroupEnumBase::Run((Settings::CMultiDeviceGroupEnumBase *)&v17);
    Settings::CMultiDeviceGroupEnum::~CMultiDeviceGroupEnum((Settings::CMultiDeviceGroupEnum *)&v18);
    if ( DeviceGroupPropertySizeHelper == -2147467259 )
    {
      v9 = (*(__int64 (__fastcall **)(Settings *, const WCHAR *, _BYTE *, __int64))(*(_QWORD *)this + 24LL))(
             this,
             L"DeviceGroup",
             v22,
             260);
      *(_DWORD *)v16 = 0;
      DeviceGroupPropertySizeHelper = v9;
      if ( v9 >= 0 )
        DeviceGroupPropertySizeHelper = Settings::_GetDeviceGroupPropertySizeHelper(
                                          (Settings *)v22,
                                          (const unsigned __int16 *)a2,
                                          v16,
                                          v10);
      if ( DeviceGroupPropertySizeHelper == -2147467259 )
        DeviceGroupPropertySizeHelper = Settings::_GetDeviceClassPropertySize(this, a2, v16, v10);
    }
  }
  *(_QWORD *)a3 = 0;
  if ( DeviceGroupPropertySizeHelper >= 0 )
  {
    v11 = CoTaskMemAlloc(*(unsigned int *)v16 + 10LL);
    v12 = v11;
    if ( v11 )
    {
      v13 = *(_DWORD *)v16 + 2;
      *v11 = ((unsigned __int64)*(unsigned int *)v16 + 2) >> 1;
      LODWORD(v15) = v13;
      DeviceGroupPropertySizeHelper = Settings::_GetDevicePropertyGeneric(
                                        this,
                                        a2,
                                        (const unsigned __int16 *)7,
                                        (__int64)(v11 + 1),
                                        v15);
      if ( DeviceGroupPropertySizeHelper < 0 )
        CoTaskMemFree(v12);
      else
        *(_QWORD *)a3 = v12;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)DeviceGroupPropertySizeHelper;
}

```

## disassembly

```asm
0x180005e80  mov     [rsp-8+arg_18], rbx
0x180005e85  push    rbp
0x180005e86  push    rsi
0x180005e87  push    rdi
0x180005e88  push    r14
0x180005e8a  push    r15
0x180005e8c  lea     rbp, [rsp-190h]
0x180005e94  sub     rsp, 290h
0x180005e9b  mov     rax, cs:__security_cookie
0x180005ea2  xor     rax, rsp
0x180005ea5  mov     [rbp+1B0h+var_30], rax
0x180005eac  mov     rax, [rcx]
0x180005eaf  mov     r15, r8
0x180005eb2  lea     r8, [rsp+2B0h+var_280]
0x180005eb7  mov     dword ptr [rsp+2B0h+var_280], 0
0x180005ebf  mov     r14, rdx
0x180005ec2  mov     rsi, rcx
0x180005ec5  mov     rax, [rax+38h]
0x180005ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ece  mov     edi, 80004005h
0x180005ed3  mov     ebx, eax
0x180005ed5  cmp     eax, edi
0x180005ed7  jnz     loc_180005F8B
0x180005edd  lea     rax, ??_7CMultiDeviceGroupSinglePropertySize@Settings@@6B@; const Settings::CMultiDeviceGroupSinglePropertySize::`vftable'
0x180005ee4  mov     [rsp+2B0h+var_260], edi
0x180005ee8  mov     [rsp+2B0h+var_278], rax
0x180005eed  lea     rcx, [rsp+2B0h+var_270]; this
0x180005ef2  lea     rax, [rsp+2B0h+var_280]
0x180005ef7  mov     [rsp+2B0h+var_258], r14
0x180005efc  xorps   xmm0, xmm0
0x180005eff  mov     [rsp+2B0h+var_250], rax
0x180005f04  mov     rdx, rsi; struct Autoplay::IDeviceProperties *
0x180005f07  movdqu  [rsp+2B0h+var_270], xmm0
0x180005f0d  call    ?Init@CMultiDeviceGroupEnum@Settings@@QEAAJPEAVIDeviceProperties@Autoplay@@@Z; Settings::CMultiDeviceGroupEnum::Init(Autoplay::IDeviceProperties *)
0x180005f12  mov     ebx, eax
0x180005f14  test    eax, eax
0x180005f16  js      short loc_180005F24
0x180005f18  lea     rcx, [rsp+2B0h+var_278]; this
0x180005f1d  call    ?Run@CMultiDeviceGroupEnumBase@Settings@@QEAAJXZ; Settings::CMultiDeviceGroupEnumBase::Run(void)
0x180005f22  mov     ebx, eax
0x180005f24  lea     rcx, [rsp+2B0h+var_270]; this
0x180005f29  call    ??1CMultiDeviceGroupEnum@Settings@@QEAA@XZ; Settings::CMultiDeviceGroupEnum::~CMultiDeviceGroupEnum(void)
0x180005f2e  cmp     ebx, edi
0x180005f30  jnz     short loc_180005F8B
0x180005f32  mov     rax, [rsi]
0x180005f35  lea     r8, [rsp+2B0h+var_240]
0x180005f3a  mov     r9d, 104h
0x180005f40  lea     rdx, pszCustomPropertyName; "DeviceGroup"
0x180005f47  mov     rcx, rsi
0x180005f4a  mov     rax, [rax+18h]
0x180005f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f53  mov     dword ptr [rsp+2B0h+var_280], 0
0x180005f5b  mov     ebx, eax
0x180005f5d  test    eax, eax
0x180005f5f  js      short loc_180005F75
0x180005f61  lea     r8, [rsp+2B0h+var_280]; unsigned __int16 *
0x180005f66  mov     rdx, r14; unsigned __int16 *
0x180005f69  lea     rcx, [rsp+2B0h+var_240]; this
0x180005f6e  call    ?_GetDeviceGroupPropertySizeHelper@Settings@@YAJPEBG0PEAK@Z; Settings::_GetDeviceGroupPropertySizeHelper(ushort const *,ushort const *,ulong *)
0x180005f73  mov     ebx, eax
0x180005f75  cmp     ebx, edi
0x180005f77  jnz     short loc_180005F8B
0x180005f79  lea     r8, [rsp+2B0h+var_280]; unsigned __int16 *
0x180005f7e  mov     rdx, r14; struct Autoplay::IDeviceProperties *
0x180005f81  mov     rcx, rsi; this
0x180005f84  call    ?_GetDeviceClassPropertySize@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAK@Z; Settings::_GetDeviceClassPropertySize(Autoplay::IDeviceProperties *,ushort const *,ulong *)
0x180005f89  mov     ebx, eax
0x180005f8b  mov     qword ptr [r15], 0
0x180005f92  test    ebx, ebx
0x180005f94  js      short loc_180005FF4
0x180005f96  mov     ecx, dword ptr [rsp+2B0h+var_280]
0x180005f9a  add     rcx, 0Ah; cb
0x180005f9e  call    cs:__imp_CoTaskMemAlloc
0x180005fa4  mov     rdi, rax
0x180005fa7  test    rax, rax
0x180005faa  jz      short loc_180005FEF
0x180005fac  mov     r8d, dword ptr [rsp+2B0h+var_280]
0x180005fb1  mov     rdx, r14; struct Autoplay::IDeviceProperties *
0x180005fb4  mov     rcx, rsi; this
0x180005fb7  lea     r9, [r8+2]
0x180005fbb  shr     r9, 1
0x180005fbe  lea     r10d, [r8+2]
0x180005fc2  mov     [rax], r9d
0x180005fc5  mov     r8d, 7; unsigned __int16 *
0x180005fcb  lea     r9, [rax+4]; unsigned int
0x180005fcf  mov     dword ptr [rsp+2B0h+var_290], r10d; unsigned __int8 *
0x180005fd4  call    ?_GetDevicePropertyGeneric@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGKPEAEK@Z; Settings::_GetDevicePropertyGeneric(Autoplay::IDeviceProperties *,ushort const *,ulong,uchar *,ulong)
0x180005fd9  mov     ebx, eax
0x180005fdb  test    eax, eax
0x180005fdd  js      short loc_180005FE4
0x180005fdf  mov     [r15], rdi
0x180005fe2  jmp     short loc_180005FF4
0x180005fe4  mov     rcx, rdi; pv
0x180005fe7  call    cs:__imp_CoTaskMemFree
0x180005fed  jmp     short loc_180005FF4
0x180005fef  mov     ebx, 8007000Eh
0x180005ff4  mov     eax, ebx
0x180005ff6  mov     rcx, [rbp+1B0h+var_30]
0x180005ffd  xor     rcx, rsp; StackCookie
0x180006000  call    __security_check_cookie
0x180006005  mov     rbx, [rsp+2B0h+arg_18]
0x18000600d  add     rsp, 290h
0x180006014  pop     r15
0x180006016  pop     r14
0x180006018  pop     rdi
0x180006019  pop     rsi
0x18000601a  pop     rbp
0x18000601b  retn
```
