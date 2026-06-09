# CVssHardwareProviderWrapper::GetVolumeDevinfo(ushort const *,CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>> &,CVssAutoString<CVssAutoCOMPtr<ushort *>> &,_DO_DEVINFO_DATA &)

- ea: `0x1400b4754`
- end: `0x1400b4d27`
- name: `?GetVolumeDevinfo@CVssHardwareProviderWrapper@@AEAA_NPEBGAEAV?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@AEAV?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@AEAU_DO_DEVINFO_DATA@@@Z`
- size: `1491`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

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
- `0x140040a40`
- `0x140091560`
- `0x1400921dc`
- `0x1400b22f8`
- `0x1400b3618`
- `0x1400b3e84`
- `0x1400b4754`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400b4b1e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400b4b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b4a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b4cad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b4a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400b4cad`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400b49c9`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400b49c9`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400b492f`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400b492f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400b4a2a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400b4a7f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400b4a2a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400b4a7f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400b4898`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400b4898`

## string_xrefs

- `0x1400b4794`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400b4aa6`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400b4b39`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400b4c47`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400b4cbe`: `base\stor\vss\modules\coord\src\hwdelete.cxx`
- `0x1400b48fc`: `DevObjCreateDeviceInfoList(NULL, NULL, NULL, NULL, NULL)`
- `0x1400b4ae1`: `Volume device path: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CVssHardwareProviderWrapper::GetVolumeDevinfo(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5)
{
  CVssHardwareProviderWrapper *v8; // rcx
  bool v9; // bl
  __int64 DeviceInfoList; // rbx
  unsigned int i; // edi
  const unsigned __int16 *v12; // rbx
  int DeviceInterfaceDetail; // eax
  CVssHardwareProviderWrapper *v14; // rcx
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v17; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v18; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v19; // [rsp+48h] [rbp-B8h]
  int v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+54h] [rbp-ACh]
  int v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[120]; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+D8h] [rbp-28h]
  void **v25; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v26; // [rsp+F0h] [rbp-10h]
  LPVOID v27[14]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v28[2]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v29; // [rsp+190h] [rbp+90h] BYREF
  __int128 v30; // [rsp+1A0h] [rbp+A0h]
  __int128 v31; // [rsp+1B0h] [rbp+B0h]
  unsigned __int16 v32[104]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v33[104]; // [rsp+290h] [rbp+190h] BYREF

  v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v18 = L"CVssHardwareProviderWrapper::GetVolumeDevinfo";
  v19 = L"CORHDELC";
  v20 = 3170;
  v21 = 1;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v27, (__int64)&v17, 0);
  v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
  v18 = L"CVssHardwareProviderWrapper::GetVolumeDevinfo";
  v19 = L"CORHDELC";
  v20 = 3172;
  v21 = 1;
  v22 = 255;
  v24 = 0x1000000;
  memset_0(v23, 0, sizeof(v23));
  CVssFunctionTracer::Trace(v27, &v17, L"Get info on volume devnode %s...", a2);
  if ( CVssHardwareProviderWrapper::GetDosDevice(v8, a2, v32, 0x64u) )
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(a3);
    *(_QWORD *)(a3 + 8) = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v18 = L"CVssHardwareProviderWrapper::GetVolumeDevinfo";
      v19 = L"CORHDELC";
      v20 = 3185;
      v21 = 1;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::TranslateWin32Error(v27, &v17, L"DevObjCreateDeviceInfoList(NULL, NULL, NULL, NULL, NULL)");
    }
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_VOLUME, 0, 16, 0, 0) )
    {
      v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v18 = L"CVssHardwareProviderWrapper::GetVolumeDevinfo";
      v19 = L"CORHDELC";
      v20 = 3195;
      v21 = 1;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::TranslateWin32Error(
        v27,
        &v17,
        L"DevObjGetClassDevs(&, NULL, NULL, DOGCF_DEVICEINTERFACE, NULL, NULL)");
    }
    memset(v28, 0, sizeof(v28));
    LODWORD(v28[0]) = 32;
    for ( i = 0; (unsigned int)DevObjEnumDeviceInterfaces(*(_QWORD *)(a3 + 8), 0, &GUID_DEVINTERFACE_VOLUME, i, v28); ++i )
    {
      v26 = 0;
      v25 = &CVssAuto<unsigned short * *,CVssAutoCppPtr_Storage<unsigned short * *>>::`vftable';
      v29 = 0;
      v30 = 0;
      v31 = 0;
      LODWORD(v29) = 48;
      v16 = 0;
      DevObjGetDeviceInterfaceDetail(*(_QWORD *)(a3 + 8), v28, 0, 0, &v16, 0);
      if ( GetLastError() != 122 || !v16 )
      {
        v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v18 = L"CVssHardwareProviderWrapper::GetVolumeDevinfo";
        v19 = L"CORHDELC";
        v20 = 3235;
        v21 = 1;
        v22 = 255;
        v24 = 0x1000000;
        memset_0(v23, 0, sizeof(v23));
        CVssFunctionTracer::TranslateWin32Error(
          v27,
          &v17,
          L"DevObjGetDeviceInterfaceDetail(devInfo, &, NULL, 0, &, NULL)");
      }
      CVssAutoCppPtr_Storage<unsigned char *>::AllocateBytes(&v25);
      v12 = v26;
      *(_DWORD *)v26 = 8;
      DeviceInterfaceDetail = DevObjGetDeviceInterfaceDetail(*(_QWORD *)(a3 + 8), v28, v12, v16, 0, &v29);
      v21 = 1;
      v22 = 255;
      v24 = 0x1000000;
      v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v18 = L"CVssHardwareProviderWrapper::GetVolumeDevinfo";
      v19 = L"CORHDELC";
      if ( !DeviceInterfaceDetail )
      {
        v20 = 3243;
        memset_0(v23, 0, sizeof(v23));
        CVssFunctionTracer::TranslateWin32Error(
          v27,
          &v17,
          L"DevObjGetDeviceInterfaceDetail(devInfo, &, detail, dwBytes, NULL, &)");
      }
      v20 = 3246;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::Trace(v27, &v17, L"Volume device path: %s", v12 + 2);
      if ( CVssHardwareProviderWrapper::GetDosDevice(v14, v12 + 2, v33, 0x64u) && !(unsigned int)_o__wcsicmp(v33, v32) )
      {
        v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
        v18 = L"CVssHardwareProviderWrapper::GetVolumeDevinfo";
        v19 = L"CORHDELC";
        v20 = 3256;
        v21 = 1;
        v22 = 255;
        v24 = 0x1000000;
        memset_0(v23, 0, sizeof(v23));
        CVssFunctionTracer::Trace(v27, &v17, L"Found volume device -- %s", v32);
        CVssAutoString<CVssAutoCOMPtr<unsigned short *>>::CopyFrom(a4, v32);
        *a5 = v29;
        a5[1] = v30;
        a5[2] = v31;
        v9 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v27, 1);
        CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>::~CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>(&v25);
        goto LABEL_16;
      }
      CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>::~CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>(&v25);
    }
    if ( GetLastError() != 259 )
    {
      v17 = L"base\\stor\\vss\\modules\\coord\\src\\hwdelete.cxx";
      v18 = L"CVssHardwareProviderWrapper::GetVolumeDevinfo";
      v19 = L"CORHDELC";
      v20 = 3212;
      v21 = 1;
      v22 = 255;
      v24 = 0x1000000;
      memset_0(v23, 0, sizeof(v23));
      CVssFunctionTracer::TranslateWin32Error(v27, &v17, L"DevObjEnumDeviceInterfaces(devInfo, NULL, &, [%d], &)", i);
    }
  }
  v9 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v27, 0);
LABEL_16:
  CVssFunctionTracer::~CVssFunctionTracer(v27);
  return v9;
}

```

## disassembly

```asm
0x1400b4754  mov     [rsp-8+arg_0], rbx
0x1400b4759  push    rbp
0x1400b475a  push    rsi
0x1400b475b  push    rdi
0x1400b475c  push    r12
0x1400b475e  push    r13
0x1400b4760  push    r14
0x1400b4762  push    r15
0x1400b4764  lea     rbp, [rsp-270h]
0x1400b476c  sub     rsp, 370h
0x1400b4773  mov     rax, cs:__security_cookie
0x1400b477a  xor     rax, rsp
0x1400b477d  mov     [rbp+2A0h+var_40], rax
0x1400b4784  mov     r15, r9
0x1400b4787  mov     rsi, r8
0x1400b478a  mov     rbx, rdx
0x1400b478d  mov     r14, [rbp+2A0h+arg_20]
0x1400b4794  lea     rdi, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400b479b  mov     [rsp+3A0h+var_368], rdi
0x1400b47a0  lea     rax, aCvsshardwarepr_58; "CVssHardwareProviderWrapper::GetVolumeD"...
0x1400b47a7  mov     [rsp+3A0h+var_360], rax
0x1400b47ac  lea     rax, aCorhdelc; "CORHDELC"
0x1400b47b3  mov     [rsp+3A0h+var_358], rax
0x1400b47b8  mov     [rsp+3A0h+var_350], 0C62h
0x1400b47c0  mov     r13d, 1
0x1400b47c6  mov     [rsp+3A0h+var_34C], r13d
0x1400b47cb  mov     [rsp+3A0h+var_348], 0FFh
0x1400b47d3  xor     r12d, r12d
0x1400b47d6  mov     [rbp+2A0h+var_2C8], 1000000h
0x1400b47dd  xor     edx, edx; Val
0x1400b47df  lea     r8d, [r13+77h]; Size
0x1400b47e3  lea     rcx, [rsp+3A0h+var_340]; void *
0x1400b47e8  call    memset_0
0x1400b47ed  xor     r8d, r8d
0x1400b47f0  lea     rdx, [rsp+3A0h+var_368]
0x1400b47f5  lea     rcx, [rbp+2A0h+var_2A0]
0x1400b47f9  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1400b47fe  nop
0x1400b47ff  mov     [rsp+3A0h+var_368], rdi
0x1400b4804  lea     rax, aCvsshardwarepr_58; "CVssHardwareProviderWrapper::GetVolumeD"...
0x1400b480b  mov     [rsp+3A0h+var_360], rax
0x1400b4810  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4817  mov     [rsp+3A0h+var_358], rax
0x1400b481c  mov     [rsp+3A0h+var_350], 0C64h
0x1400b4824  mov     [rsp+3A0h+var_34C], r13d
0x1400b4829  mov     [rsp+3A0h+var_348], 0FFh
0x1400b4831  mov     [rbp+2A0h+var_2C8], 1000000h
0x1400b4838  xor     edx, edx; Val
0x1400b483a  lea     r8d, [r13+77h]; Size
0x1400b483e  lea     rcx, [rsp+3A0h+var_340]; void *
0x1400b4843  call    memset_0
0x1400b4848  mov     r9, rbx
0x1400b484b  lea     r8, aGetInfoOnVolum; "Get info on volume devnode %s..."
0x1400b4852  lea     rdx, [rsp+3A0h+var_368]
0x1400b4857  lea     rcx, [rbp+2A0h+var_2A0]
0x1400b485b  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400b4860  lea     r9d, [r13+63h]; unsigned int
0x1400b4864  lea     r8, [rbp+2A0h+var_1E0]; unsigned __int16 *
0x1400b486b  mov     rdx, rbx; unsigned __int16 *
0x1400b486e  call    ?GetDosDevice@CVssHardwareProviderWrapper@@AEAA_NPEBGPEAGK@Z; CVssHardwareProviderWrapper::GetDosDevice(ushort const *,ushort *,ulong)
0x1400b4873  test    al, al
0x1400b4875  jnz     short loc_1400B4889
0x1400b4877  xor     edx, edx; bool
0x1400b4879  lea     rcx, [rbp+2A0h+var_2A0]; this
0x1400b487d  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x1400b4882  mov     bl, al
0x1400b4884  jmp     loc_1400B4BEF
0x1400b4889  mov     [rsp+3A0h+var_380], r12
0x1400b488e  xor     r9d, r9d
0x1400b4891  xor     r8d, r8d
0x1400b4894  xor     edx, edx
0x1400b4896  xor     ecx, ecx
0x1400b4898  call    cs:__imp_DevObjCreateDeviceInfoList
0x1400b489e  mov     rbx, rax
0x1400b48a1  mov     rcx, rsi
0x1400b48a4  call    ?Close@?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@QEAAXXZ; CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>::Close(void)
0x1400b48a9  mov     [rsi+8], rbx
0x1400b48ad  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400b48b1  jnz     short loc_1400B4912
0x1400b48b3  mov     [rsp+3A0h+var_368], rdi
0x1400b48b8  lea     rax, aCvsshardwarepr_58; "CVssHardwareProviderWrapper::GetVolumeD"...
0x1400b48bf  mov     [rsp+3A0h+var_360], rax
0x1400b48c4  lea     rax, aCorhdelc; "CORHDELC"
0x1400b48cb  mov     [rsp+3A0h+var_358], rax
0x1400b48d0  mov     [rsp+3A0h+var_350], 0C71h
0x1400b48d8  mov     [rsp+3A0h+var_34C], r13d
0x1400b48dd  mov     [rsp+3A0h+var_348], 0FFh
0x1400b48e5  mov     [rbp+2A0h+var_2C8], 1000000h
0x1400b48ec  xor     edx, edx; Val
0x1400b48ee  lea     r8d, [rbx+79h]; Size
0x1400b48f2  lea     rcx, [rsp+3A0h+var_340]; void *
0x1400b48f7  call    memset_0
0x1400b48fc  lea     r8, aDevobjcreatede_0; "DevObjCreateDeviceInfoList(NULL, NULL, "...
0x1400b4903  lea     rdx, [rsp+3A0h+var_368]
0x1400b4908  lea     rcx, [rbp+2A0h+var_2A0]
0x1400b490c  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400b4912  mov     [rsp+3A0h+var_378], r12
0x1400b4917  mov     [rsp+3A0h+var_380], r12
0x1400b491c  mov     r9d, 10h
0x1400b4922  xor     r8d, r8d
0x1400b4925  lea     rdx, GUID_DEVINTERFACE_VOLUME
0x1400b492c  mov     rcx, rbx
0x1400b492f  call    cs:__imp_DevObjGetClassDevs
0x1400b4935  test    eax, eax
0x1400b4937  jnz     short loc_1400B4998
0x1400b4939  mov     [rsp+3A0h+var_368], rdi
0x1400b493e  lea     rax, aCvsshardwarepr_58; "CVssHardwareProviderWrapper::GetVolumeD"...
0x1400b4945  mov     [rsp+3A0h+var_360], rax
0x1400b494a  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4951  mov     [rsp+3A0h+var_358], rax
0x1400b4956  mov     [rsp+3A0h+var_350], 0C7Bh
0x1400b495e  mov     [rsp+3A0h+var_34C], r13d
0x1400b4963  mov     [rsp+3A0h+var_348], 0FFh
0x1400b496b  mov     [rbp+2A0h+var_2C8], 1000000h
0x1400b4972  xor     edx, edx; Val
0x1400b4974  lea     r8d, [rdx+78h]; Size
0x1400b4978  lea     rcx, [rsp+3A0h+var_340]; void *
0x1400b497d  call    memset_0
0x1400b4982  lea     r8, aDevobjgetclass_1; "DevObjGetClassDevs(&, NULL, NULL, DOGCF"...
0x1400b4989  lea     rdx, [rsp+3A0h+var_368]
0x1400b498e  lea     rcx, [rbp+2A0h+var_2A0]
0x1400b4992  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400b4998  xorps   xmm0, xmm0
0x1400b499b  movups  [rbp+2A0h+var_230], xmm0
0x1400b499f  movups  [rbp+2A0h+var_220], xmm0
0x1400b49a6  mov     dword ptr [rbp+2A0h+var_230], 20h ; ' '
0x1400b49ad  mov     edi, r12d
0x1400b49b0  lea     rax, [rbp+2A0h+var_230]
0x1400b49b4  mov     [rsp+3A0h+var_380], rax
0x1400b49b9  mov     r9d, edi
0x1400b49bc  lea     r8, GUID_DEVINTERFACE_VOLUME
0x1400b49c3  xor     edx, edx
0x1400b49c5  mov     rcx, [rsi+8]
0x1400b49c9  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1400b49cf  test    eax, eax
0x1400b49d1  jz      loc_1400B4CAD
0x1400b49d7  mov     [rbp+2A0h+var_2B0], r12
0x1400b49db  lea     rax, ??_7?$CVssAuto@PEAPEAGV?$CVssAutoCppPtr_Storage@PEAPEAG@@@@6B@; const CVssAuto<ushort * *,CVssAutoCppPtr_Storage<ushort * *>>::`vftable'
0x1400b49e2  mov     [rbp+2A0h+var_2B8], rax
0x1400b49e6  xorps   xmm0, xmm0
0x1400b49e9  movups  [rbp+2A0h+var_210], xmm0
0x1400b49f0  movups  [rbp+2A0h+var_200], xmm0
0x1400b49f7  movups  [rbp+2A0h+var_1F0], xmm0
0x1400b49fe  mov     dword ptr [rbp+2A0h+var_210], 30h ; '0'
0x1400b4a08  mov     [rsp+3A0h+var_370], r12d
0x1400b4a0d  mov     [rsp+3A0h+var_378], r12
0x1400b4a12  lea     rax, [rsp+3A0h+var_370]
0x1400b4a17  mov     [rsp+3A0h+var_380], rax
0x1400b4a1c  xor     r9d, r9d
0x1400b4a1f  xor     r8d, r8d
0x1400b4a22  lea     rdx, [rbp+2A0h+var_230]
0x1400b4a26  mov     rcx, [rsi+8]
0x1400b4a2a  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1400b4a30  call    cs:__imp_GetLastError
0x1400b4a36  cmp     eax, 7Ah ; 'z'
0x1400b4a39  jnz     loc_1400B4C47
0x1400b4a3f  mov     edx, [rsp+3A0h+var_370]
0x1400b4a43  test    edx, edx
0x1400b4a45  jz      loc_1400B4C47
0x1400b4a4b  lea     rcx, [rbp+2A0h+var_2B8]
0x1400b4a4f  call    ?AllocateBytes@?$CVssAutoCppPtr_Storage@PEAE@@QEAAXK@Z; CVssAutoCppPtr_Storage<uchar *>::AllocateBytes(ulong)
0x1400b4a54  mov     rbx, [rbp+2A0h+var_2B0]
0x1400b4a58  mov     dword ptr [rbx], 8
0x1400b4a5e  lea     rax, [rbp+2A0h+var_210]
0x1400b4a65  mov     [rsp+3A0h+var_378], rax
0x1400b4a6a  mov     [rsp+3A0h+var_380], r12
0x1400b4a6f  mov     r9d, [rsp+3A0h+var_370]
0x1400b4a74  mov     r8, rbx
0x1400b4a77  lea     rdx, [rbp+2A0h+var_230]
0x1400b4a7b  mov     rcx, [rsi+8]
0x1400b4a7f  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1400b4a85  mov     [rsp+3A0h+var_34C], r13d
0x1400b4a8a  mov     [rsp+3A0h+var_348], 0FFh
0x1400b4a92  mov     [rbp+2A0h+var_2C8], 1000000h
0x1400b4a99  xor     edx, edx; Val
0x1400b4a9b  lea     r8d, [rdx+78h]; Size
0x1400b4a9f  lea     rcx, [rsp+3A0h+var_340]; void *
0x1400b4aa4  test    eax, eax
0x1400b4aa6  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400b4aad  mov     [rsp+3A0h+var_368], rax
0x1400b4ab2  lea     rax, aCvsshardwarepr_58; "CVssHardwareProviderWrapper::GetVolumeD"...
0x1400b4ab9  mov     [rsp+3A0h+var_360], rax
0x1400b4abe  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4ac5  mov     [rsp+3A0h+var_358], rax
0x1400b4aca  jz      loc_1400B4C24
0x1400b4ad0  mov     [rsp+3A0h+var_350], 0CAEh
0x1400b4ad8  call    memset_0
0x1400b4add  lea     r9, [rbx+4]
0x1400b4ae1  lea     r8, aVolumeDevicePa; "Volume device path: %s"
0x1400b4ae8  lea     rdx, [rsp+3A0h+var_368]
0x1400b4aed  lea     rcx, [rbp+2A0h+var_2A0]
0x1400b4af1  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400b4af6  mov     r9d, 64h ; 'd'; unsigned int
0x1400b4afc  lea     r8, [rbp+2A0h+var_110]; unsigned __int16 *
0x1400b4b03  lea     rdx, [rbx+4]; unsigned __int16 *
0x1400b4b07  call    ?GetDosDevice@CVssHardwareProviderWrapper@@AEAA_NPEBGPEAGK@Z; CVssHardwareProviderWrapper::GetDosDevice(ushort const *,ushort *,ulong)
0x1400b4b0c  test    al, al
0x1400b4b0e  jz      short loc_1400B4B28
0x1400b4b10  lea     rdx, [rbp+2A0h+var_1E0]
0x1400b4b17  lea     rcx, [rbp+2A0h+var_110]
0x1400b4b1e  call    cs:__imp__o__wcsicmp
0x1400b4b24  test    eax, eax
0x1400b4b26  jz      short loc_1400B4B39
0x1400b4b28  lea     rcx, [rbp+2A0h+var_2B8]
0x1400b4b2c  call    ??1?$CVssAuto@PEAPEAU_VSS_DISK_ID@@V?$CVssAutoCppPtr_Storage@PEAPEAU_VSS_DISK_ID@@@@@@UEAA@XZ; CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>::~CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>(void)
0x1400b4b31  add     edi, r13d
0x1400b4b34  jmp     loc_1400B49B0
0x1400b4b39  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400b4b40  mov     [rsp+3A0h+var_368], rax
0x1400b4b45  lea     rax, aCvsshardwarepr_58; "CVssHardwareProviderWrapper::GetVolumeD"...
0x1400b4b4c  mov     [rsp+3A0h+var_360], rax
0x1400b4b51  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4b58  mov     [rsp+3A0h+var_358], rax
0x1400b4b5d  mov     [rsp+3A0h+var_350], 0CB8h
0x1400b4b65  mov     [rsp+3A0h+var_34C], r13d
0x1400b4b6a  mov     [rsp+3A0h+var_348], 0FFh
0x1400b4b72  mov     [rbp+2A0h+var_2C8], 1000000h
0x1400b4b79  xor     edx, edx; Val
0x1400b4b7b  lea     r8d, [rdx+78h]; Size
0x1400b4b7f  lea     rcx, [rsp+3A0h+var_340]; void *
0x1400b4b84  call    memset_0
0x1400b4b89  lea     r9, [rbp+2A0h+var_1E0]
0x1400b4b90  lea     r8, aFoundVolumeDev; "Found volume device -- %s"
0x1400b4b97  lea     rdx, [rsp+3A0h+var_368]
0x1400b4b9c  lea     rcx, [rbp+2A0h+var_2A0]
0x1400b4ba0  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400b4ba5  lea     rdx, [rbp+2A0h+var_1E0]
0x1400b4bac  mov     rcx, r15
0x1400b4baf  call    ?CopyFrom@?$CVssAutoString@V?$CVssAutoCOMPtr@PEAG@@@@QEAAXPEBG@Z; CVssAutoString<CVssAutoCOMPtr<ushort *>>::CopyFrom(ushort const *)
0x1400b4bb4  movups  xmm0, [rbp+2A0h+var_210]
0x1400b4bbb  movups  xmmword ptr [r14], xmm0
0x1400b4bbf  movups  xmm1, [rbp+2A0h+var_200]
0x1400b4bc6  movups  xmmword ptr [r14+10h], xmm1
0x1400b4bcb  movups  xmm0, [rbp+2A0h+var_1F0]
0x1400b4bd2  movups  xmmword ptr [r14+20h], xmm0
0x1400b4bd7  mov     dl, r13b; bool
0x1400b4bda  lea     rcx, [rbp+2A0h+var_2A0]; this
0x1400b4bde  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x1400b4be3  mov     bl, al
0x1400b4be5  lea     rcx, [rbp+2A0h+var_2B8]
0x1400b4be9  call    ??1?$CVssAuto@PEAPEAU_VSS_DISK_ID@@V?$CVssAutoCppPtr_Storage@PEAPEAU_VSS_DISK_ID@@@@@@UEAA@XZ; CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>::~CVssAuto<_VSS_DISK_ID * *,CVssAutoCppPtr_Storage<_VSS_DISK_ID * *>>(void)
0x1400b4bee  nop
0x1400b4bef  lea     rcx, [rbp+2A0h+var_2A0]; this
0x1400b4bf3  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400b4bf8  mov     al, bl
0x1400b4bfa  mov     rcx, [rbp+2A0h+var_40]
0x1400b4c01  xor     rcx, rsp; StackCookie
0x1400b4c04  call    __security_check_cookie
0x1400b4c09  mov     rbx, [rsp+3A0h+arg_0]
0x1400b4c11  add     rsp, 370h
0x1400b4c18  pop     r15
0x1400b4c1a  pop     r14
0x1400b4c1c  pop     r13
0x1400b4c1e  pop     r12
0x1400b4c20  pop     rdi
0x1400b4c21  pop     rsi
0x1400b4c22  pop     rbp
0x1400b4c23  retn
0x1400b4c24  mov     [rsp+3A0h+var_350], 0CABh
0x1400b4c2c  call    memset_0
0x1400b4c31  lea     r8, aDevobjgetdevic_1; "DevObjGetDeviceInterfaceDetail(devInfo,"...
0x1400b4c38  lea     rdx, [rsp+3A0h+var_368]
0x1400b4c3d  lea     rcx, [rbp+2A0h+var_2A0]
0x1400b4c41  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400b4c47  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400b4c4e  mov     [rsp+3A0h+var_368], rax
0x1400b4c53  lea     rax, aCvsshardwarepr_58; "CVssHardwareProviderWrapper::GetVolumeD"...
0x1400b4c5a  mov     [rsp+3A0h+var_360], rax
0x1400b4c5f  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4c66  mov     [rsp+3A0h+var_358], rax
0x1400b4c6b  mov     [rsp+3A0h+var_350], 0CA3h
0x1400b4c73  mov     [rsp+3A0h+var_34C], r13d
0x1400b4c78  mov     [rsp+3A0h+var_348], 0FFh
0x1400b4c80  mov     [rbp+2A0h+var_2C8], 1000000h
0x1400b4c87  xor     edx, edx; Val
0x1400b4c89  lea     r8d, [rdx+78h]; Size
0x1400b4c8d  lea     rcx, [rsp+3A0h+var_340]; void *
0x1400b4c92  call    memset_0
0x1400b4c97  lea     r8, aDevobjgetdevic_2; "DevObjGetDeviceInterfaceDetail(devInfo,"...
0x1400b4c9e  lea     rdx, [rsp+3A0h+var_368]
0x1400b4ca3  lea     rcx, [rbp+2A0h+var_2A0]
0x1400b4ca7  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x1400b4cad  call    cs:__imp_GetLastError
0x1400b4cb3  cmp     eax, 103h
0x1400b4cb8  jz      loc_1400B4877
0x1400b4cbe  lea     rax, aBaseStorVssMod_22; "base\\stor\\vss\\modules\\coord\\src\\h"...
0x1400b4cc5  mov     [rsp+3A0h+var_368], rax
0x1400b4cca  lea     rax, aCvsshardwarepr_58; "CVssHardwareProviderWrapper::GetVolumeD"...
0x1400b4cd1  mov     [rsp+3A0h+var_360], rax
0x1400b4cd6  lea     rax, aCorhdelc; "CORHDELC"
0x1400b4cdd  mov     [rsp+3A0h+var_358], rax
0x1400b4ce2  mov     [rsp+3A0h+var_350], 0C8Ch
0x1400b4cea  mov     [rsp+3A0h+var_34C], r13d
0x1400b4cef  mov     [rsp+3A0h+var_348], 0FFh
0x1400b4cf7  mov     [rbp+2A0h+var_2C8], 1000000h
0x1400b4cfe  xor     edx, edx; Val
0x1400b4d00  lea     r8d, [rdx+78h]; Size
0x1400b4d04  lea     rcx, [rsp+3A0h+var_340]; void *
0x1400b4d09  call    memset_0
0x1400b4d0e  mov     r9d, edi
  ... truncated ...
```
