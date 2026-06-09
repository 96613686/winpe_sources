# winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::TryEnableEffect(winrt::WindowsUdk::Media::Devices::CameraEffect)

- ea: `0x1802e3784`
- end: `0x1802e3c99`
- name: `?TryEnableEffect@CameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@QEAA_NW4CameraEffect@3456@@Z`
- size: `1301`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1802e3750`

## callees

- `0x180025348`
- `0x1800ce544`
- `0x1800e488c`
- `0x1802e25cc`
- `0x1802e3784`
- `0x1804a2010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x1802e37af`
- `MFPlat!MFCreateAttributes` at `0x1802e37af`

## string_xrefs

- `0x1802e3adb`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x1802e3b8e`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3ba2`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3bb7`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3bcc`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3be0`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3bf5`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3c0a`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3c1f`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3c33`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3c48`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3c5d`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3c71`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3c86`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char __fastcall winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::TryEnableEffect(
        __int64 a1,
        int a2)
{
  HRESULT v4; // eax
  const wchar_t *v5; // r8
  __int64 v6; // r9
  int v7; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  const wchar_t *v21; // rax
  __int64 v22; // r10
  int v23; // eax
  const char *v24; // r9
  char result; // al
  int v26; // eax
  int v27; // [rsp+20h] [rbp-68h]
  __int64 v28; // [rsp+40h] [rbp-48h] BYREF
  __int64 *v29; // [rsp+48h] [rbp-40h] BYREF
  IMFAttributes *v30; // [rsp+50h] [rbp-38h] BYREF
  __int64 v31; // [rsp+58h] [rbp-30h] BYREF
  __int64 v32; // [rsp+60h] [rbp-28h] BYREF
  __int64 v33; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v35; // [rsp+A0h] [rbp+18h] BYREF
  int v36; // [rsp+A8h] [rbp+20h] BYREF

  v30 = 0;
  v4 = MFCreateAttributes(&v30, 1u);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)(unsigned int)v4,
        v27);
    v5 = winrt::hstring::c_str((winrt::hstring *)(a1 + 40));
    v7 = (*(__int64 (__fastcall **)(__int64, const IID *, const wchar_t *))(*(_QWORD *)v6 + 200LL))(
           v6,
           &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
           v5);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)(unsigned int)v7,
        v27);
    v29 = 0;
    v8 = *(__int64 **)(a1 + 48);
    v9 = *v8;
    v29 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, IMFAttributes *, __int64 **))(v9 + 24))(v8, v30, &v29);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE1,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)(unsigned int)v10,
        v27);
    v28 = 0;
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        v11 = *v29;
        v28 = 0;
        v12 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v11 + 280))(v29, 1, 41, 0xFFFFFFFFLL);
        if ( v12 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x114,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
            (const char *)(unsigned int)v12,
            40);
        v33 = 0;
        v35 = 0;
        v31 = 0;
        v36 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *, __int64 *))(*(_QWORD *)v28 + 40LL))(
                v28,
                &v33,
                &v35,
                &v31);
        if ( v13 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x11B,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
            (const char *)(unsigned int)v13,
            (int)&v36);
        if ( v35 >= 0x18 && (unsigned int)v36 >= 0x20 )
        {
          if ( (*(_BYTE *)(v31 + 24) & 1) != 0 )
            *(_QWORD *)(v31 + 16) = 1;
          v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28);
          if ( v14 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x120,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
              (const char *)(unsigned int)v14,
              (int)&v36);
LABEL_24:
          wil::com_ptr_t<IMFCameraControlDefaultsCollection,wil::err_exception_policy>::query<IMFCameraControlDefaultsCollectionInternal>(
            &v29,
            &v32);
          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v32 + 24LL))(v32, 0, 0);
          if ( v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x138,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
              (const char *)(unsigned int)v20,
              (int)&v36);
          v21 = winrt::hstring::c_str((winrt::hstring *)(a1 + 40));
          v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *))(*(_QWORD *)v22 + 88LL))(
                  v22,
                  v21,
                  L"FRAMESERVER_CONFIGURATION_ALL_APPS",
                  v29);
          if ( v23 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x139,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
              (const char *)(unsigned int)v23,
              (int)&v36);
          wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v32);
          wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v28);
          wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v29);
          wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v30);
          return 1;
        }
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x120,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
            (const char *)(unsigned int)v15,
            (int)&v36);
      }
    }
    else
    {
      v16 = *v29;
      v28 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v16 + 280))(v29, 1, 43, 0xFFFFFFFFLL);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xEF,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
          (const char *)(unsigned int)v17,
          48);
      v33 = 0;
      v35 = 0;
      v31 = 0;
      v36 = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, __int64 *, unsigned int *, __int64 *))(*(_QWORD *)v28 + 40LL))(
              v28,
              &v33,
              &v35,
              &v31);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF6,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
          (const char *)(unsigned int)v18,
          (int)&v36);
      if ( v35 >= 0x18 && (unsigned int)v36 >= 0x20 )
      {
        if ( (*(_BYTE *)(v31 + 24) & 1) != 0 )
          *(_QWORD *)(v31 + 16) = 1;
        v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28);
        if ( v19 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xFB,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
            (const char *)(unsigned int)v19,
            (int)&v36);
        goto LABEL_24;
      }
      v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
          (const char *)(unsigned int)v26,
          (int)&v36);
    }
    wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v28);
    wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v29);
    wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v30);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x13E,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      v24);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1802e3784  mov     rax, rsp
0x1802e3787  mov     [rax+8], rbx
0x1802e378b  mov     [rax+10h], rsi
0x1802e378f  push    rdi
0x1802e3790  push    r14
0x1802e3792  push    r15
0x1802e3794  sub     rsp, 70h
0x1802e3798  mov     ebx, edx
0x1802e379a  mov     rdi, rcx
0x1802e379d  xor     r14d, r14d
0x1802e37a0  mov     [rax-38h], r14
0x1802e37a4  lea     r15d, [r14+1]
0x1802e37a8  mov     edx, r15d; cInitialSize
0x1802e37ab  lea     rcx, [rax-38h]; ppMFAttributes
0x1802e37af  call    cs:__imp_MFCreateAttributes
0x1802e37b5  mov     rcx, [rsp+88h]; this
0x1802e37bd  test    eax, eax
0x1802e37bf  js      loc_1802E3B8B
0x1802e37c5  mov     r9, [rsp+88h+var_38]
0x1802e37ca  lea     rcx, [rdi+28h]; this
0x1802e37ce  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1802e37d3  mov     r8, rax
0x1802e37d6  mov     rax, [r9]
0x1802e37d9  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x1802e37e0  mov     rcx, r9
0x1802e37e3  mov     rax, [rax+0C8h]
0x1802e37ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e37ef  mov     rcx, [rsp+88h]; this
0x1802e37f7  test    eax, eax
0x1802e37f9  js      loc_1802E3B9F
0x1802e37ff  mov     [rsp+88h+var_40], r14
0x1802e3804  mov     rcx, [rdi+30h]
0x1802e3808  mov     rax, [rcx]
0x1802e380b  mov     [rsp+88h+var_40], r14
0x1802e3810  lea     r8, [rsp+88h+var_40]
0x1802e3815  mov     rdx, [rsp+88h+var_38]
0x1802e381a  mov     rax, [rax+18h]
0x1802e381e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3823  mov     rcx, [rsp+88h]; this
0x1802e382b  test    eax, eax
0x1802e382d  js      loc_1802E3BB4
0x1802e3833  mov     [rsp+88h+var_48], r14
0x1802e3838  test    ebx, ebx
0x1802e383a  jz      loc_1802E399F
0x1802e3840  cmp     ebx, 1
0x1802e3843  jz      short loc_1802E386C
0x1802e3845  lea     rcx, [rsp+88h+var_48]
0x1802e384a  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e384f  nop
0x1802e3850  lea     rcx, [rsp+88h+var_40]
0x1802e3855  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e385a  nop
0x1802e385b  lea     rcx, [rsp+88h+var_38]
0x1802e3860  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3865  xor     al, al
0x1802e3867  jmp     loc_1802E3B75
0x1802e386c  mov     rcx, [rsp+88h+var_40]
0x1802e3871  mov     rax, [rcx]
0x1802e3874  mov     [rsp+88h+var_48], r14
0x1802e3879  lea     rdx, [rsp+88h+var_48]
0x1802e387e  mov     [rsp+88h+var_60], rdx
0x1802e3883  mov     [rsp+88h+var_68], 28h ; '('; int
0x1802e388b  or      r9d, 0FFFFFFFFh
0x1802e388f  mov     r8d, 29h ; ')'
0x1802e3895  mov     edx, r15d
0x1802e3898  mov     rax, [rax+118h]
0x1802e389f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e38a4  mov     rcx, [rsp+88h]; this
0x1802e38ac  test    eax, eax
0x1802e38ae  js      loc_1802E3BC9
0x1802e38b4  mov     [rsp+88h+var_20], r14
0x1802e38b9  mov     [rsp+88h+arg_10], r14d
0x1802e38c1  mov     [rsp+88h+var_30], r14
0x1802e38c6  mov     [rsp+88h+arg_18], r14d
0x1802e38ce  mov     rcx, [rsp+88h+var_48]
0x1802e38d3  mov     rax, [rcx]
0x1802e38d6  lea     rdx, [rsp+88h+arg_18]
0x1802e38de  mov     qword ptr [rsp+88h+var_68], rdx; int
0x1802e38e3  lea     r9, [rsp+88h+var_30]
0x1802e38e8  lea     r8, [rsp+88h+arg_10]
0x1802e38f0  lea     rdx, [rsp+88h+var_20]
0x1802e38f5  mov     rax, [rax+28h]
0x1802e38f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e38fe  mov     rcx, [rsp+88h]; this
0x1802e3906  test    eax, eax
0x1802e3908  js      loc_1802E3BDD
0x1802e390e  cmp     [rsp+88h+arg_10], 18h
0x1802e3916  jb      short loc_1802E3957
0x1802e3918  cmp     [rsp+88h+arg_18], 20h ; ' '
0x1802e3920  jb      short loc_1802E3957
0x1802e3922  mov     rax, [rsp+88h+var_30]
0x1802e3927  test    [rax+18h], r15b
0x1802e392b  jz      short loc_1802E3931
0x1802e392d  mov     [rax+10h], r15
0x1802e3931  mov     rcx, [rsp+88h+var_48]
0x1802e3936  mov     rax, [rcx]
0x1802e3939  mov     rax, [rax+30h]
0x1802e393d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3942  mov     rcx, [rsp+88h]; this
0x1802e394a  test    eax, eax
0x1802e394c  js      loc_1802E3BF2
0x1802e3952  jmp     loc_1802E3A8D
0x1802e3957  mov     rcx, [rsp+88h+var_48]
0x1802e395c  mov     rax, [rcx]
0x1802e395f  mov     rax, [rax+30h]
0x1802e3963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3968  mov     rcx, [rsp+88h]; this
0x1802e3970  test    eax, eax
0x1802e3972  js      loc_1802E3C07
0x1802e3978  lea     rcx, [rsp+88h+var_48]
0x1802e397d  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3982  nop
0x1802e3983  lea     rcx, [rsp+88h+var_40]
0x1802e3988  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e398d  nop
0x1802e398e  lea     rcx, [rsp+88h+var_38]
0x1802e3993  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3998  xor     al, al
0x1802e399a  jmp     loc_1802E3B75
0x1802e399f  mov     rcx, [rsp+88h+var_40]
0x1802e39a4  mov     rax, [rcx]
0x1802e39a7  mov     [rsp+88h+var_48], r14
0x1802e39ac  lea     rdx, [rsp+88h+var_48]
0x1802e39b1  mov     [rsp+88h+var_60], rdx
0x1802e39b6  mov     [rsp+88h+var_68], 30h ; '0'; int
0x1802e39be  or      r9d, 0FFFFFFFFh
0x1802e39c2  mov     r8d, 2Bh ; '+'
0x1802e39c8  mov     edx, r15d
0x1802e39cb  mov     rax, [rax+118h]
0x1802e39d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e39d7  mov     rcx, [rsp+88h]; this
0x1802e39df  test    eax, eax
0x1802e39e1  js      loc_1802E3C1C
0x1802e39e7  mov     [rsp+88h+var_20], r14
0x1802e39ec  mov     [rsp+88h+arg_10], r14d
0x1802e39f4  mov     [rsp+88h+var_30], r14
0x1802e39f9  mov     [rsp+88h+arg_18], r14d
0x1802e3a01  mov     rcx, [rsp+88h+var_48]
0x1802e3a06  mov     rax, [rcx]
0x1802e3a09  lea     rdx, [rsp+88h+arg_18]
0x1802e3a11  mov     qword ptr [rsp+88h+var_68], rdx; int
0x1802e3a16  lea     r9, [rsp+88h+var_30]
0x1802e3a1b  lea     r8, [rsp+88h+arg_10]
0x1802e3a23  lea     rdx, [rsp+88h+var_20]
0x1802e3a28  mov     rax, [rax+28h]
0x1802e3a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3a31  mov     rcx, [rsp+88h]; this
0x1802e3a39  test    eax, eax
0x1802e3a3b  js      loc_1802E3C30
0x1802e3a41  cmp     [rsp+88h+arg_10], 18h
0x1802e3a49  jb      loc_1802E3B2E
0x1802e3a4f  cmp     [rsp+88h+arg_18], 20h ; ' '
0x1802e3a57  jb      loc_1802E3B2E
0x1802e3a5d  mov     rax, [rsp+88h+var_30]
0x1802e3a62  test    [rax+18h], r15b
0x1802e3a66  jz      short loc_1802E3A6C
0x1802e3a68  mov     [rax+10h], r15
0x1802e3a6c  mov     rcx, [rsp+88h+var_48]
0x1802e3a71  mov     rax, [rcx]
0x1802e3a74  mov     rax, [rax+30h]
0x1802e3a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3a7d  mov     rcx, [rsp+88h]; this
0x1802e3a85  test    eax, eax
0x1802e3a87  js      loc_1802E3C45
0x1802e3a8d  lea     rdx, [rsp+88h+var_28]
0x1802e3a92  lea     rcx, [rsp+88h+var_40]
0x1802e3a97  call    ??$query@UIMFCameraControlDefaultsCollectionInternal@@@?$com_ptr_t@UIMFCameraControlDefaultsCollection@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollection,wil::err_exception_policy>::query<IMFCameraControlDefaultsCollectionInternal>(void)
0x1802e3a9c  nop
0x1802e3a9d  mov     rcx, [rsp+88h+var_28]
0x1802e3aa2  mov     rax, [rcx]
0x1802e3aa5  xor     r8d, r8d
0x1802e3aa8  xor     edx, edx
0x1802e3aaa  mov     rax, [rax+18h]
0x1802e3aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3ab3  mov     rcx, [rsp+88h]; this
0x1802e3abb  test    eax, eax
0x1802e3abd  js      loc_1802E3C5A
0x1802e3ac3  mov     r10, [rdi+38h]
0x1802e3ac7  lea     rcx, [rdi+28h]; this
0x1802e3acb  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1802e3ad0  mov     rdx, rax
0x1802e3ad3  mov     rax, [r10]
0x1802e3ad6  mov     r9, [rsp+88h+var_40]
0x1802e3adb  lea     r8, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x1802e3ae2  mov     rcx, r10
0x1802e3ae5  mov     rax, [rax+58h]
0x1802e3ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3aee  mov     rcx, [rsp+88h]; this
0x1802e3af6  test    eax, eax
0x1802e3af8  js      loc_1802E3C6E
0x1802e3afe  lea     rcx, [rsp+88h+var_28]
0x1802e3b03  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3b08  nop
0x1802e3b09  lea     rcx, [rsp+88h+var_48]
0x1802e3b0e  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3b13  nop
0x1802e3b14  lea     rcx, [rsp+88h+var_40]
0x1802e3b19  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3b1e  nop
0x1802e3b1f  lea     rcx, [rsp+88h+var_38]
0x1802e3b24  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3b29  mov     al, r15b
0x1802e3b2c  jmp     short loc_1802E3B75
0x1802e3b2e  mov     rcx, [rsp+88h+var_48]
0x1802e3b33  mov     rax, [rcx]
0x1802e3b36  mov     rax, [rax+30h]
0x1802e3b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3b3f  mov     rcx, [rsp+88h]; this
0x1802e3b47  test    eax, eax
0x1802e3b49  js      loc_1802E3C83
0x1802e3b4f  lea     rcx, [rsp+88h+var_48]
0x1802e3b54  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3b59  nop
0x1802e3b5a  lea     rcx, [rsp+88h+var_40]
0x1802e3b5f  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3b64  nop
0x1802e3b65  lea     rcx, [rsp+88h+var_38]
0x1802e3b6a  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3b6f  xor     al, al
0x1802e3b71  jmp     short loc_1802E3B75
0x1802e3b73  xor     al, al
0x1802e3b75  lea     r11, [rsp+88h+var_18]
0x1802e3b7a  mov     rbx, [r11+20h]
0x1802e3b7e  mov     rsi, [r11+28h]
0x1802e3b82  mov     rsp, r11
0x1802e3b85  pop     r15
0x1802e3b87  pop     r14
0x1802e3b89  pop     rdi
0x1802e3b8a  retn
0x1802e3b8b  mov     r9d, eax; char *
0x1802e3b8e  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3b95  mov     edx, 0DEh; void *
0x1802e3b9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3b9f  mov     r9d, eax; char *
0x1802e3ba2  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3ba9  mov     edx, 0DFh; void *
0x1802e3bae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3bb4  mov     r9d, eax; char *
0x1802e3bb7  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3bbe  mov     edx, 0E1h; void *
0x1802e3bc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3bc9  mov     r9d, eax; char *
0x1802e3bcc  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3bd3  mov     edx, 114h; void *
0x1802e3bd8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3bdd  mov     r9d, eax; char *
0x1802e3be0  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3be7  mov     edx, 11Bh; void *
0x1802e3bec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3bf2  mov     r9d, eax; char *
0x1802e3bf5  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3bfc  mov     edx, 120h; void *
0x1802e3c01  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3c07  mov     r9d, eax; char *
0x1802e3c0a  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3c11  mov     edx, 120h; void *
0x1802e3c16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3c1c  mov     r9d, eax; char *
0x1802e3c1f  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3c26  mov     edx, 0EFh; void *
0x1802e3c2b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3c30  mov     r9d, eax; char *
0x1802e3c33  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3c3a  mov     edx, 0F6h; void *
0x1802e3c3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3c45  mov     r9d, eax; char *
0x1802e3c48  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3c4f  mov     edx, 0FBh; void *
0x1802e3c54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3c5a  mov     r9d, eax; char *
0x1802e3c5d  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3c64  mov     edx, 138h; void *
0x1802e3c69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3c6e  mov     r9d, eax; char *
0x1802e3c71  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3c78  mov     edx, 139h; void *
0x1802e3c7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3c83  mov     r9d, eax; char *
0x1802e3c86  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3c8d  mov     edx, 0FBh; void *
0x1802e3c92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
