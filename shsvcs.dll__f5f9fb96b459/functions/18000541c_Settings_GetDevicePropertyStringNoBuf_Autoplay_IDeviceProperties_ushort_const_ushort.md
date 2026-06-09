# Settings::GetDevicePropertyStringNoBuf(Autoplay::IDeviceProperties *,ushort const *,ushort * *)

- ea: `0x18000541c`
- end: `0x1800055ae`
- name: `?GetDevicePropertyStringNoBuf@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAPEAG@Z`
- size: `402`
- prototype: `__int64 __fastcall(Settings *this, struct Autoplay::IDeviceProperties *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015900`

## callees

- `0x180005010`
- `0x18000541c`
- `0x180006024`
- `0x1800062e0`
- `0x180006470`
- `0x180006578`
- `0x18002ecec`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000553f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000553f`

## pseudocode

```c
__int64 __fastcall Settings::GetDevicePropertyStringNoBuf(
        Settings *this,
        struct Autoplay::IDeviceProperties *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 v4; // rax
  int DeviceGroupPropertySizeHelper; // ebx
  int v9; // eax
  unsigned int *v10; // r9
  LPVOID v11; // rax
  void *v12; // rdi
  unsigned __int8 *v14; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v15; // [rsp+30h] [rbp-D0h] BYREF
  void **v16; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+50h] [rbp-B0h]
  struct Autoplay::IDeviceProperties *v19; // [rsp+58h] [rbp-A8h]
  unsigned __int8 **v20; // [rsp+60h] [rbp-A0h]
  _BYTE v21[528]; // [rsp+70h] [rbp-90h] BYREF

  v4 = *(_QWORD *)this;
  LODWORD(v15) = 0;
  DeviceGroupPropertySizeHelper = (*(__int64 (__fastcall **)(Settings *, struct Autoplay::IDeviceProperties *, unsigned __int8 **, unsigned __int16 **))(v4 + 56))(
                                    this,
                                    a2,
                                    &v15,
                                    a4);
  if ( DeviceGroupPropertySizeHelper == -2147467259 )
  {
    v18 = -2147467259;
    v16 = &Settings::CMultiDeviceGroupSinglePropertySize::`vftable';
    v19 = a2;
    v20 = &v15;
    v17 = 0;
    DeviceGroupPropertySizeHelper = Settings::CMultiDeviceGroupEnum::Init((Settings::CMultiDeviceGroupEnum *)&v17, this);
    if ( DeviceGroupPropertySizeHelper >= 0 )
      DeviceGroupPropertySizeHelper = Settings::CMultiDeviceGroupEnumBase::Run((Settings::CMultiDeviceGroupEnumBase *)&v16);
    Settings::CMultiDeviceGroupEnum::~CMultiDeviceGroupEnum((Settings::CMultiDeviceGroupEnum *)&v17);
    if ( DeviceGroupPropertySizeHelper == -2147467259 )
    {
      v9 = (*(__int64 (__fastcall **)(Settings *, const WCHAR *, _BYTE *, __int64))(*(_QWORD *)this + 24LL))(
             this,
             L"DeviceGroup",
             v21,
             260);
      LODWORD(v15) = 0;
      DeviceGroupPropertySizeHelper = v9;
      if ( v9 >= 0 )
        DeviceGroupPropertySizeHelper = Settings::_GetDeviceGroupPropertySizeHelper(
                                          (Settings *)v21,
                                          (const unsigned __int16 *)a2,
                                          (const unsigned __int16 *)&v15,
                                          v10);
      if ( DeviceGroupPropertySizeHelper == -2147467259 )
        DeviceGroupPropertySizeHelper = Settings::_GetDeviceClassPropertySize(
                                          this,
                                          a2,
                                          (const unsigned __int16 *)&v15,
                                          v10);
    }
  }
  *(_QWORD *)a3 = 0;
  if ( DeviceGroupPropertySizeHelper >= 0 )
  {
    LODWORD(v15) = (_DWORD)v15 + 2;
    v11 = CoTaskMemAlloc((unsigned int)v15);
    v12 = v11;
    if ( v11 )
    {
      LODWORD(v14) = (_DWORD)v15;
      DeviceGroupPropertySizeHelper = Settings::_GetDevicePropertyGeneric(
                                        this,
                                        a2,
                                        (const unsigned __int16 *)1,
                                        (__int64)v11,
                                        v14);
      if ( DeviceGroupPropertySizeHelper >= 0 )
        *(_QWORD *)a3 = v12;
      else
        CoTaskMemFree(v12);
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
0x18000541c  mov     [rsp-8+arg_18], rbx
0x180005421  push    rbp
0x180005422  push    rsi
0x180005423  push    rdi
0x180005424  push    r14
0x180005426  push    r15
0x180005428  lea     rbp, [rsp-190h]
0x180005430  sub     rsp, 290h
0x180005437  mov     rax, cs:__security_cookie
0x18000543e  xor     rax, rsp
0x180005441  mov     [rbp+1B0h+var_30], rax
0x180005448  mov     rax, [rcx]
0x18000544b  mov     r15, r8
0x18000544e  lea     r8, [rsp+2B0h+var_280]
0x180005453  mov     dword ptr [rsp+2B0h+var_280], 0
0x18000545b  mov     r14, rdx
0x18000545e  mov     rsi, rcx
0x180005461  mov     rax, [rax+38h]
0x180005465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000546a  mov     edi, 80004005h
0x18000546f  mov     ebx, eax
0x180005471  cmp     eax, edi
0x180005473  jnz     loc_180005527
0x180005479  lea     rax, ??_7CMultiDeviceGroupSinglePropertySize@Settings@@6B@; const Settings::CMultiDeviceGroupSinglePropertySize::`vftable'
0x180005480  mov     [rsp+2B0h+var_260], edi
0x180005484  mov     [rsp+2B0h+var_278], rax
0x180005489  lea     rcx, [rsp+2B0h+var_270]; this
0x18000548e  lea     rax, [rsp+2B0h+var_280]
0x180005493  mov     [rsp+2B0h+var_258], r14
0x180005498  xorps   xmm0, xmm0
0x18000549b  mov     [rsp+2B0h+var_250], rax
0x1800054a0  mov     rdx, rsi; struct Autoplay::IDeviceProperties *
0x1800054a3  movdqu  [rsp+2B0h+var_270], xmm0
0x1800054a9  call    ?Init@CMultiDeviceGroupEnum@Settings@@QEAAJPEAVIDeviceProperties@Autoplay@@@Z; Settings::CMultiDeviceGroupEnum::Init(Autoplay::IDeviceProperties *)
0x1800054ae  mov     ebx, eax
0x1800054b0  test    eax, eax
0x1800054b2  js      short loc_1800054C0
0x1800054b4  lea     rcx, [rsp+2B0h+var_278]; this
0x1800054b9  call    ?Run@CMultiDeviceGroupEnumBase@Settings@@QEAAJXZ; Settings::CMultiDeviceGroupEnumBase::Run(void)
0x1800054be  mov     ebx, eax
0x1800054c0  lea     rcx, [rsp+2B0h+var_270]; this
0x1800054c5  call    ??1CMultiDeviceGroupEnum@Settings@@QEAA@XZ; Settings::CMultiDeviceGroupEnum::~CMultiDeviceGroupEnum(void)
0x1800054ca  cmp     ebx, edi
0x1800054cc  jnz     short loc_180005527
0x1800054ce  mov     rax, [rsi]
0x1800054d1  lea     r8, [rsp+2B0h+var_240]
0x1800054d6  mov     r9d, 104h
0x1800054dc  lea     rdx, pszCustomPropertyName; "DeviceGroup"
0x1800054e3  mov     rcx, rsi
0x1800054e6  mov     rax, [rax+18h]
0x1800054ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ef  mov     dword ptr [rsp+2B0h+var_280], 0
0x1800054f7  mov     ebx, eax
0x1800054f9  test    eax, eax
0x1800054fb  js      short loc_180005511
0x1800054fd  lea     r8, [rsp+2B0h+var_280]; unsigned __int16 *
0x180005502  mov     rdx, r14; unsigned __int16 *
0x180005505  lea     rcx, [rsp+2B0h+var_240]; this
0x18000550a  call    ?_GetDeviceGroupPropertySizeHelper@Settings@@YAJPEBG0PEAK@Z; Settings::_GetDeviceGroupPropertySizeHelper(ushort const *,ushort const *,ulong *)
0x18000550f  mov     ebx, eax
0x180005511  cmp     ebx, edi
0x180005513  jnz     short loc_180005527
0x180005515  lea     r8, [rsp+2B0h+var_280]; unsigned __int16 *
0x18000551a  mov     rdx, r14; struct Autoplay::IDeviceProperties *
0x18000551d  mov     rcx, rsi; this
0x180005520  call    ?_GetDeviceClassPropertySize@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGPEAK@Z; Settings::_GetDeviceClassPropertySize(Autoplay::IDeviceProperties *,ushort const *,ulong *)
0x180005525  mov     ebx, eax
0x180005527  mov     qword ptr [r15], 0
0x18000552e  test    ebx, ebx
0x180005530  js      short loc_180005586
0x180005532  mov     eax, dword ptr [rsp+2B0h+var_280]
0x180005536  add     eax, 2
0x180005539  mov     ecx, eax; cb
0x18000553b  mov     dword ptr [rsp+2B0h+var_280], eax
0x18000553f  call    cs:__imp_CoTaskMemAlloc
0x180005545  mov     rdi, rax
0x180005548  test    rax, rax
0x18000554b  jz      short loc_180005581
0x18000554d  mov     r8d, dword ptr [rsp+2B0h+var_280]
0x180005552  mov     r9, rax; unsigned int
0x180005555  mov     dword ptr [rsp+2B0h+var_290], r8d; unsigned __int8 *
0x18000555a  mov     rdx, r14; struct Autoplay::IDeviceProperties *
0x18000555d  mov     r8d, 1; unsigned __int16 *
0x180005563  mov     rcx, rsi; this
0x180005566  call    ?_GetDevicePropertyGeneric@Settings@@YAJPEAVIDeviceProperties@Autoplay@@PEBGKPEAEK@Z; Settings::_GetDevicePropertyGeneric(Autoplay::IDeviceProperties *,ushort const *,ulong,uchar *,ulong)
0x18000556b  mov     ebx, eax
0x18000556d  test    eax, eax
0x18000556f  jns     short loc_18000557C
0x180005571  mov     rcx, rdi; pv
0x180005574  call    cs:__imp_CoTaskMemFree
0x18000557a  jmp     short loc_180005586
0x18000557c  mov     [r15], rdi
0x18000557f  jmp     short loc_180005586
0x180005581  mov     ebx, 8007000Eh
0x180005586  mov     eax, ebx
0x180005588  mov     rcx, [rbp+1B0h+var_30]
0x18000558f  xor     rcx, rsp; StackCookie
0x180005592  call    __security_check_cookie
0x180005597  mov     rbx, [rsp+2B0h+arg_18]
0x18000559f  add     rsp, 290h
0x1800055a6  pop     r15
0x1800055a8  pop     r14
0x1800055aa  pop     rdi
0x1800055ab  pop     rsi
0x1800055ac  pop     rbp
0x1800055ad  retn
```
