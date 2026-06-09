# CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo(ushort const *,CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>> &,CVssAutoString<CVssAutoCOMPtr<ushort *>> &,_DO_DEVINFO_DATA &)

- ea: `0x1400b4284`
- end: `0x1400b474b`
- name: `?GetHiddenVolumeDevinfo@CVssHardwareProviderWrapper@@AEAA_NPEBGAEAV?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@AEAV?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@AEAU_DO_DEVINFO_DATA@@@Z`
- size: `1223`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400638d4`
- `0x140063f60`

## callees

- `0x140009a40`
- `0x140011a90`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140028b48`
- `0x140091560`
- `0x1400921dc`
- `0x1400b3618`
- `0x1400b3e84`
- `0x1400b4284`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400b4607`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400b4607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b46d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b46d8`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400b44a1`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400b44a1`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1400b4586`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1400b4586`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1400b4533`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1400b4533`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400b440a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400b440a`

## string_xrefs

- `0x1400b42c4`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400b446e`: `DevObjCreateDeviceInfoList(NULL, NULL, NULL, NULL, NULL)`
- `0x1400b46c2`: `DevObjGetDeviceRegistryProperty(devInfo, NULL, &, [%d], &)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5)
{
  CVssHardwareProviderWrapper *v8; // rcx
  bool v9; // dl
  bool v10; // bl
  __int64 DeviceInfoList; // rbx
  unsigned int i; // ebx
  int DeviceRegistryProperty; // eax
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v16; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v17; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+64h] [rbp-9Ch]
  int v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[120]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+E8h] [rbp-18h]
  LPVOID v24[14]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v25; // [rsp+170h] [rbp+70h] BYREF
  __int128 v26; // [rsp+180h] [rbp+80h]
  __int128 v27; // [rsp+190h] [rbp+90h]
  GUID v28; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v29[208]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v30[104]; // [rsp+280h] [rbp+180h] BYREF

  v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v17 = L"CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo";
  v18 = L"CORHDELC";
  v19 = 3276;
  v20 = 1;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v24, (__int64)&v16, 0);
  v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v17 = L"CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo";
  v18 = L"CORHDELC";
  v19 = 3278;
  v20 = 1;
  v21 = 255;
  v23 = 0x1000000;
  memset_0(v22, 0, sizeof(v22));
  CVssFunctionTracer::Trace(v24, &v16, L"Get info on hidden volume devnode %s...", a2);
  if ( CVssHardwareProviderWrapper::GetDosDevice(v8, a2, v30, 0x64u) )
  {
    v28 = GUID_DEVCLASS_VOLUME;
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(a3);
    *(_QWORD *)(a3 + 8) = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v17 = L"CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo";
      v18 = L"CORHDELC";
      v19 = 3294;
      v20 = 1;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::TranslateWin32Error(v24, &v16, L"DevObjCreateDeviceInfoList(NULL, NULL, NULL, NULL, NULL)");
    }
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &v28, 0, 2, 0, 0) )
    {
      v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v17 = L"CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo";
      v18 = L"CORHDELC";
      v19 = 3304;
      v20 = 1;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::TranslateWin32Error(
        v24,
        &v16,
        L"DevObjGetClassDevs(&, NULL, NULL, DOGCF_PRESENT, NULL, NULL)");
    }
    for ( i = 0; ; ++i )
    {
      v25 = 0;
      v26 = 0;
      v27 = 0;
      LODWORD(v25) = 48;
      if ( !(unsigned int)DevObjEnumDeviceInfo(*(_QWORD *)(a3 + 8), i, &v25) )
        break;
      v15 = 0;
      memset_0(v29, 0, 0xC8u);
      DeviceRegistryProperty = DevObjGetDeviceRegistryProperty(*(_QWORD *)(a3 + 8), &v25, 14, &v15, v29, 198, 0);
      v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v20 = 1;
      v21 = 255;
      v23 = 0x1000000;
      v17 = L"CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo";
      v18 = L"CORHDELC";
      if ( !DeviceRegistryProperty )
      {
        v19 = 3342;
        memset_0(v22, 0, sizeof(v22));
        CVssFunctionTracer::TranslateWin32Error(
          v24,
          &v16,
          L"DevObjGetDeviceRegistryProperty(devInfo, NULL, &, [%d], &)",
          i);
      }
      v19 = 3346;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::Trace(v24, &v16, L"Examining device %s", v29);
      if ( !(unsigned int)_o__wcsicmp(v29, v30) )
      {
        v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v17 = L"CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo";
        v18 = L"CORHDELC";
        v19 = 3352;
        v20 = 1;
        v21 = 255;
        v23 = 0x1000000;
        memset_0(v22, 0, sizeof(v22));
        CVssFunctionTracer::Trace(v24, &v16, L"Found volume device -- %s", v30);
        CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom(a4, v30);
        *a5 = v25;
        a5[1] = v26;
        a5[2] = v27;
        v9 = 1;
        goto LABEL_3;
      }
    }
    if ( GetLastError() != 259 )
    {
      v16 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v17 = L"CVssHardwareProviderWrapper::GetHiddenVolumeDevinfo";
      v18 = L"CORHDELC";
      v19 = 3321;
      v20 = 1;
      v21 = 255;
      v23 = 0x1000000;
      memset_0(v22, 0, sizeof(v22));
      CVssFunctionTracer::TranslateWin32Error(v24, &v16, L"DevObjEnumDeviceInfo(devInfo, NULL, &, [%d], &)", i);
    }
  }
  v9 = 0;
LABEL_3:
  v10 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v24, v9);
  CVssFunctionTracer::~CVssFunctionTracer(v24);
  return v10;
}

```

## disassembly

```asm
0x1400b4284  mov     [rsp-8+arg_0], rbx
0x1400b4289  push    rbp
0x1400b428a  push    rsi
0x1400b428b  push    rdi
0x1400b428c  push    r12
0x1400b428e  push    r13
0x1400b4290  push    r14
0x1400b4292  push    r15
0x1400b4294  lea     rbp, [rsp-260h]
0x1400b429c  sub     rsp, 360h
0x1400b42a3  mov     rax, cs:__security_cookie
0x1400b42aa  xor     rax, rsp
0x1400b42ad  mov     [rbp+290h+var_40], rax
0x1400b42b4  mov     r14, r9
0x1400b42b7  mov     rdi, r8
0x1400b42ba  mov     rbx, rdx
0x1400b42bd  mov     rsi, [rbp+290h+arg_20]
0x1400b42c4  lea     r13, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400b42cb  mov     [rsp+390h+var_348], r13
0x1400b42d0  lea     rax, aCvsshardwarepr_105; "CVssHardwareProviderWrapper::GetHiddenV"...
0x1400b42d7  mov     [rsp+390h+var_340], rax
0x1400b42dc  lea     rax, aCorhdelc; "CORHDELC"
0x1400b42e3  mov     [rsp+390h+var_338], rax
0x1400b42e8  mov     [rsp+390h+var_330], 0CCCh
0x1400b42f0  mov     r12d, 1
0x1400b42f6  mov     [rsp+390h+var_32C], r12d
0x1400b42fb  mov     [rsp+390h+var_328], 0FFh
0x1400b4303  xor     r15d, r15d
0x1400b4306  mov     [rbp+290h+var_2A8], 1000000h
0x1400b430d  xor     edx, edx; Val
0x1400b430f  lea     r8d, [r12+77h]; Size
0x1400b4314  lea     rcx, [rsp+390h+var_320]; void *
0x1400b4319  call    memset_0
0x1400b431e  xor     r8d, r8d
0x1400b4321  lea     rdx, [rsp+390h+var_348]
0x1400b4326  lea     rcx, [rbp+290h+var_290]
0x1400b432a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400b432f  nop
0x1400b4330  mov     [rsp+390h+var_348], r13
0x1400b4335  lea     rax, aCvsshardwarepr_105; "CVssHardwareProviderWrapper::GetHiddenV"...
0x1400b433c  mov     [rsp+390h+var_340], rax
0x1400b4341  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4348  mov     [rsp+390h+var_338], rax
0x1400b434d  mov     [rsp+390h+var_330], 0CCEh
0x1400b4355  mov     [rsp+390h+var_32C], r12d
0x1400b435a  mov     [rsp+390h+var_328], 0FFh
0x1400b4362  mov     [rbp+290h+var_2A8], 1000000h
0x1400b4369  xor     edx, edx; Val
0x1400b436b  lea     r8d, [r12+77h]; Size
0x1400b4370  lea     rcx, [rsp+390h+var_320]; void *
0x1400b4375  call    memset_0
0x1400b437a  mov     r9, rbx
0x1400b437d  lea     r8, aGetInfoOnHidde; "Get info on hidden volume devnode %s..."
0x1400b4384  lea     rdx, [rsp+390h+var_348]
0x1400b4389  lea     rcx, [rbp+290h+var_290]
0x1400b438d  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400b4392  lea     r9d, [r12+63h]; unsigned int
0x1400b4397  lea     r8, [rbp+290h+var_110]; unsigned __int16 *
0x1400b439e  mov     rdx, rbx; unsigned __int16 *
0x1400b43a1  call    ?GetDosDevice@CVssHardwareProviderWrapper@@AEAA_NPEBGPEAGK@Z; CVssHardwareProviderWrapper::GetDosDevice(ushort const *,ushort *,ulong)
0x1400b43a6  test    al, al
0x1400b43a8  jnz     short loc_1400B43EC
0x1400b43aa  xor     edx, edx; bool
0x1400b43ac  lea     rcx, [rbp+290h+var_290]; this
0x1400b43b0  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x1400b43b5  mov     bl, al
0x1400b43b7  lea     rcx, [rbp+290h+var_290]; this
0x1400b43bb  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400b43c0  mov     al, bl
0x1400b43c2  mov     rcx, [rbp+290h+var_40]
0x1400b43c9  xor     rcx, rsp; StackCookie
0x1400b43cc  call    __security_check_cookie
0x1400b43d1  mov     rbx, [rsp+390h+arg_0]
0x1400b43d9  add     rsp, 360h
0x1400b43e0  pop     r15
0x1400b43e2  pop     r14
0x1400b43e4  pop     r13
0x1400b43e6  pop     r12
0x1400b43e8  pop     rdi
0x1400b43e9  pop     rsi
0x1400b43ea  pop     rbp
0x1400b43eb  retn
0x1400b43ec  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_VOLUME.Data1
0x1400b43f3  movdqu  [rbp+290h+var_1F0], xmm0
0x1400b43fb  mov     [rsp+390h+var_370], r15
0x1400b4400  xor     r9d, r9d
0x1400b4403  xor     r8d, r8d
0x1400b4406  xor     edx, edx
0x1400b4408  xor     ecx, ecx
0x1400b440a  call    cs:__imp_DevObjCreateDeviceInfoList
0x1400b4410  mov     rbx, rax
0x1400b4413  mov     rcx, rdi
0x1400b4416  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x1400b441b  mov     [rdi+8], rbx
0x1400b441f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400b4423  jnz     short loc_1400B4484
0x1400b4425  mov     [rsp+390h+var_348], r13
0x1400b442a  lea     rax, aCvsshardwarepr_105; "CVssHardwareProviderWrapper::GetHiddenV"...
0x1400b4431  mov     [rsp+390h+var_340], rax
0x1400b4436  lea     rax, aCorhdelc; "CORHDELC"
0x1400b443d  mov     [rsp+390h+var_338], rax
0x1400b4442  mov     [rsp+390h+var_330], 0CDEh
0x1400b444a  mov     [rsp+390h+var_32C], r12d
0x1400b444f  mov     [rsp+390h+var_328], 0FFh
0x1400b4457  mov     [rbp+290h+var_2A8], 1000000h
0x1400b445e  xor     edx, edx; Val
0x1400b4460  lea     r8d, [rbx+79h]; Size
0x1400b4464  lea     rcx, [rsp+390h+var_320]; void *
0x1400b4469  call    memset_0
0x1400b446e  lea     r8, aDevobjcreatede_0; "DevObjCreateDeviceInfoList(NULL, NULL, "...
0x1400b4475  lea     rdx, [rsp+390h+var_348]
0x1400b447a  lea     rcx, [rbp+290h+var_290]
0x1400b447e  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400b4484  mov     [rsp+390h+var_368], r15
0x1400b4489  mov     [rsp+390h+var_370], r15
0x1400b448e  mov     r9d, 2
0x1400b4494  xor     r8d, r8d
0x1400b4497  lea     rdx, [rbp+290h+var_1F0]
0x1400b449e  mov     rcx, rbx
0x1400b44a1  call    cs:__imp_DevObjGetClassDevs
0x1400b44a7  test    eax, eax
0x1400b44a9  jnz     short loc_1400B450A
0x1400b44ab  mov     [rsp+390h+var_348], r13
0x1400b44b0  lea     rax, aCvsshardwarepr_105; "CVssHardwareProviderWrapper::GetHiddenV"...
0x1400b44b7  mov     [rsp+390h+var_340], rax
0x1400b44bc  lea     rax, aCorhdelc; "CORHDELC"
0x1400b44c3  mov     [rsp+390h+var_338], rax
0x1400b44c8  mov     [rsp+390h+var_330], 0CE8h
0x1400b44d0  mov     [rsp+390h+var_32C], r12d
0x1400b44d5  mov     [rsp+390h+var_328], 0FFh
0x1400b44dd  mov     [rbp+290h+var_2A8], 1000000h
0x1400b44e4  xor     edx, edx; Val
0x1400b44e6  lea     r8d, [rdx+78h]; Size
0x1400b44ea  lea     rcx, [rsp+390h+var_320]; void *
0x1400b44ef  call    memset_0
0x1400b44f4  lea     r8, aDevobjgetclass_0; "DevObjGetClassDevs(&, NULL, NULL, DOGCF"...
0x1400b44fb  lea     rdx, [rsp+390h+var_348]
0x1400b4500  lea     rcx, [rbp+290h+var_290]
0x1400b4504  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400b450a  mov     ebx, r15d
0x1400b450d  xorps   xmm0, xmm0
0x1400b4510  movups  [rbp+290h+var_220], xmm0
0x1400b4514  movups  [rbp+290h+var_210], xmm0
0x1400b451b  movups  [rbp+290h+var_200], xmm0
0x1400b4522  mov     dword ptr [rbp+290h+var_220], 30h ; '0'
0x1400b4529  lea     r8, [rbp+290h+var_220]
0x1400b452d  mov     edx, ebx
0x1400b452f  mov     rcx, [rdi+8]
0x1400b4533  call    cs:__imp_DevObjEnumDeviceInfo
0x1400b4539  test    eax, eax
0x1400b453b  jz      loc_1400B46D8
0x1400b4541  mov     [rsp+390h+var_350], r15d
0x1400b4546  xor     edx, edx; Val
0x1400b4548  mov     r8d, 0C8h; Size
0x1400b454e  lea     rcx, [rbp+290h+var_1E0]; void *
0x1400b4555  call    memset_0
0x1400b455a  mov     [rsp+390h+var_360], r15
0x1400b455f  mov     dword ptr [rsp+390h+var_368], 0C6h
0x1400b4567  lea     rax, [rbp+290h+var_1E0]
0x1400b456e  mov     [rsp+390h+var_370], rax
0x1400b4573  lea     r9, [rsp+390h+var_350]
0x1400b4578  mov     r8d, 0Eh
0x1400b457e  lea     rdx, [rbp+290h+var_220]
0x1400b4582  mov     rcx, [rdi+8]
0x1400b4586  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x1400b458c  mov     [rsp+390h+var_348], r13
0x1400b4591  mov     [rsp+390h+var_32C], r12d
0x1400b4596  mov     [rsp+390h+var_328], 0FFh
0x1400b459e  mov     [rbp+290h+var_2A8], 1000000h
0x1400b45a5  xor     edx, edx; Val
0x1400b45a7  lea     r8d, [rdx+78h]; Size
0x1400b45ab  lea     rcx, [rsp+390h+var_320]; void *
0x1400b45b0  test    eax, eax
0x1400b45b2  lea     rax, aCvsshardwarepr_105; "CVssHardwareProviderWrapper::GetHiddenV"...
0x1400b45b9  mov     [rsp+390h+var_340], rax
0x1400b45be  lea     rax, aCorhdelc; "CORHDELC"
0x1400b45c5  mov     [rsp+390h+var_338], rax
0x1400b45ca  jz      loc_1400B46B2
0x1400b45d0  mov     [rsp+390h+var_330], 0D12h
0x1400b45d8  call    memset_0
0x1400b45dd  lea     r9, [rbp+290h+var_1E0]
0x1400b45e4  lea     r8, aExaminingDevic; "Examining device %s"
0x1400b45eb  lea     rdx, [rsp+390h+var_348]
0x1400b45f0  lea     rcx, [rbp+290h+var_290]
0x1400b45f4  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400b45f9  lea     rdx, [rbp+290h+var_110]
0x1400b4600  lea     rcx, [rbp+290h+var_1E0]
0x1400b4607  call    cs:__imp__o__wcsicmp
0x1400b460d  test    eax, eax
0x1400b460f  jz      short loc_1400B4619
0x1400b4611  add     ebx, r12d
0x1400b4614  jmp     loc_1400B450D
0x1400b4619  mov     [rsp+390h+var_348], r13
0x1400b461e  lea     rax, aCvsshardwarepr_105; "CVssHardwareProviderWrapper::GetHiddenV"...
0x1400b4625  mov     [rsp+390h+var_340], rax
0x1400b462a  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4631  mov     [rsp+390h+var_338], rax
0x1400b4636  mov     [rsp+390h+var_330], 0D18h
0x1400b463e  mov     [rsp+390h+var_32C], r12d
0x1400b4643  mov     [rsp+390h+var_328], 0FFh
0x1400b464b  mov     [rbp+290h+var_2A8], 1000000h
0x1400b4652  xor     edx, edx; Val
0x1400b4654  lea     r8d, [rdx+78h]; Size
0x1400b4658  lea     rcx, [rsp+390h+var_320]; void *
0x1400b465d  call    memset_0
0x1400b4662  lea     r9, [rbp+290h+var_110]
0x1400b4669  lea     r8, aFoundVolumeDev; "Found volume device -- %s"
0x1400b4670  lea     rdx, [rsp+390h+var_348]
0x1400b4675  lea     rcx, [rbp+290h+var_290]
0x1400b4679  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400b467e  lea     rdx, [rbp+290h+var_110]
0x1400b4685  mov     rcx, r14
0x1400b4688  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x1400b468d  movups  xmm0, [rbp+290h+var_220]
0x1400b4691  movups  xmmword ptr [rsi], xmm0
0x1400b4694  movups  xmm1, [rbp+290h+var_210]
0x1400b469b  movups  xmmword ptr [rsi+10h], xmm1
0x1400b469f  movups  xmm0, [rbp+290h+var_200]
0x1400b46a6  movups  xmmword ptr [rsi+20h], xmm0
0x1400b46aa  mov     dl, r12b
0x1400b46ad  jmp     loc_1400B43AC
0x1400b46b2  mov     [rsp+390h+var_330], 0D0Eh
0x1400b46ba  call    memset_0
0x1400b46bf  mov     r9d, ebx
0x1400b46c2  lea     r8, aDevobjgetdevic_5; "DevObjGetDeviceRegistryProperty(devInfo"...
0x1400b46c9  lea     rdx, [rsp+390h+var_348]
0x1400b46ce  lea     rcx, [rbp+290h+var_290]
0x1400b46d2  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400b46d8  call    cs:__imp_GetLastError
0x1400b46de  cmp     eax, 103h
0x1400b46e3  jz      loc_1400B43AA
0x1400b46e9  mov     [rsp+390h+var_348], r13
0x1400b46ee  lea     rax, aCvsshardwarepr_105; "CVssHardwareProviderWrapper::GetHiddenV"...
0x1400b46f5  mov     [rsp+390h+var_340], rax
0x1400b46fa  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4701  mov     [rsp+390h+var_338], rax
0x1400b4706  mov     [rsp+390h+var_330], 0CF9h
0x1400b470e  mov     [rsp+390h+var_32C], r12d
0x1400b4713  mov     [rsp+390h+var_328], 0FFh
0x1400b471b  mov     [rbp+290h+var_2A8], 1000000h
0x1400b4722  xor     edx, edx; Val
0x1400b4724  lea     r8d, [rdx+78h]; Size
0x1400b4728  lea     rcx, [rsp+390h+var_320]; void *
0x1400b472d  call    memset_0
0x1400b4732  mov     r9d, ebx
0x1400b4735  lea     r8, aDevobjenumdevi_1; "DevObjEnumDeviceInfo(devInfo, NULL, &, "...
0x1400b473c  lea     rdx, [rsp+390h+var_348]
0x1400b4741  lea     rcx, [rbp+290h+var_290]
0x1400b4745  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
```
