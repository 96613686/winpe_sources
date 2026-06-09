# winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::TryDisableEffect(winrt::WindowsUdk::Media::Devices::CameraEffect)

- ea: `0x1802e3354`
- end: `0x1802e3740`
- name: `?TryDisableEffect@CameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@QEAA_NW4CameraEffect@3456@@Z`
- size: `1004`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1802e3320`

## callees

- `0x180025348`
- `0x1800ce544`
- `0x1800e488c`
- `0x18012a5f0`
- `0x1802e2440`
- `0x1802e25cc`
- `0x1802e3354`
- `0x1804a2010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x1802e338e`
- `MFPlat!MFCreateAttributes` at `0x1802e338e`

## string_xrefs

- `0x1802e3605`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x1802e367a`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e368c`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e36a1`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e36b6`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e36c8`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e36ef`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3704`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e3719`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e372d`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::TryDisableEffect(
        __int64 a1,
        int a2)
{
  char v4; // di
  HRESULT v5; // eax
  const wchar_t *v6; // r8
  __int64 v7; // r9
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rcx
  unsigned int i; // ebx
  __int64 v13; // rsi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // r14
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  bool v19; // zf
  int v20; // eax
  int v21; // eax
  const wchar_t *v22; // rax
  __int64 v23; // r10
  int v24; // eax
  const char *v25; // r9
  char result; // al
  unsigned int v27; // eax
  int *v28; // [rsp+20h] [rbp-78h]
  __int64 v29; // [rsp+30h] [rbp-68h] BYREF
  __int64 v30; // [rsp+38h] [rbp-60h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-58h] BYREF
  __int64 v32; // [rsp+48h] [rbp-50h] BYREF
  __int64 v33; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v34[2]; // [rsp+58h] [rbp-40h] BYREF
  char v35; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 v37; // [rsp+B0h] [rbp+18h] BYREF
  int v38; // [rsp+B8h] [rbp+20h] BYREF

  v4 = 0;
  try
  {
    wil::CoCreateInstance<IMFCameraConfigurationManager,wil::err_exception_policy>(v34);
    ppMFAttributes = 0;
    v5 = MFCreateAttributes(&ppMFAttributes, 1u);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)(unsigned int)v5,
        (int)v28);
    v6 = winrt::hstring::c_str((winrt::hstring *)(a1 + 40));
    v8 = (*(__int64 (__fastcall **)(__int64, const IID *, const wchar_t *))(*(_QWORD *)v7 + 200LL))(
           v7,
           &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
           v6);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)(unsigned int)v8,
        (int)v28);
    v29 = 0;
    v9 = *(_QWORD *)v34[0];
    v29 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, IMFAttributes *, __int64 *))(v9 + 24))(v34[0], ppMFAttributes, &v29);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
        (const char *)(unsigned int)v10,
        (int)v28);
    v11 = v29;
    if ( v29 )
    {
      v30 = 0;
      v33 = 0;
      LODWORD(v37) = 0;
      v32 = 0;
      v38 = 0;
      for ( i = 0; ; ++i )
      {
        if ( i >= (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v11 + 264LL))(v11) )
        {
          wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v30);
          if ( v4 )
          {
            wil::com_ptr_t<IMFCameraControlDefaultsCollection,wil::err_exception_policy>::query<IMFCameraControlDefaultsCollectionInternal>(
              &v29,
              &v37);
            v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v37 + 24LL))(v37, 0, 0);
            if ( v21 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x95,
                (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
                (const char *)(unsigned int)v21,
                (int)v28);
            v22 = winrt::hstring::c_str((winrt::hstring *)(a1 + 40));
            v24 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v23 + 88LL))(
                    v23,
                    v22,
                    L"FRAMESERVER_CONFIGURATION_ALL_APPS",
                    v29);
            if ( v24 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x96,
                (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
                (const char *)(unsigned int)v24,
                (int)v28);
            wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v37);
          }
          break;
        }
        v13 = v29;
        v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 272LL);
        v15 = v30;
        v30 = 0;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        v16 = v14(v13, i, &v30);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5F,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
            (const char *)(unsigned int)v16,
            (int)v28);
        v28 = &v38;
        v17 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v30 + 40LL))(
                v30,
                &v33,
                &v37,
                &v32);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x60,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
            (const char *)(unsigned int)v17,
            (int)&v38);
        v34[1] = &v30;
        v35 = 1;
        if ( (_DWORD)v37 == 24 && v33 )
        {
          if ( !a2 )
          {
            if ( *(_QWORD *)v33 != *(_QWORD *)&GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data1
              || *(_QWORD *)(v33 + 8) != *(_QWORD *)GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data4 )
            {
              goto LABEL_25;
            }
            v19 = *(_DWORD *)(v33 + 16) == 43;
            goto LABEL_22;
          }
          if ( a2 != 1 )
          {
            v27 = wil::verify_hresult<long>(2147942487LL, v18);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x8B,
              (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
              (const char *)v27,
              (int)&v38);
          }
          if ( *(_QWORD *)v33 == *(_QWORD *)&GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data1
            && *(_QWORD *)(v33 + 8) == *(_QWORD *)GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data4 )
          {
            v19 = *(_DWORD *)(v33 + 16) == 41;
LABEL_22:
            if ( v19 && (*(_BYTE *)(v32 + 24) & 1) != 0 )
            {
              v4 = 1;
              *(_QWORD *)(v32 + 16) = 0;
            }
          }
        }
LABEL_25:
        v35 = 0;
        v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 48LL))(v30);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x65,
            (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
            (const char *)(unsigned int)v20,
            (int)&v38);
        v11 = v29;
      }
    }
    wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v29);
    wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&ppMFAttributes);
    wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(v34);
    result = v4;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x9C,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      v25);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1802e3354  mov     [rsp+arg_0], rbx
0x1802e3359  mov     [rsp+arg_8], rsi
0x1802e335e  push    rdi
0x1802e335f  push    r12
0x1802e3361  push    r13
0x1802e3363  push    r14
0x1802e3365  push    r15
0x1802e3367  sub     rsp, 70h
0x1802e336b  mov     r15d, edx
0x1802e336e  mov     r13, rcx
0x1802e3371  xor     esi, esi
0x1802e3373  mov     dil, sil
0x1802e3376  lea     rcx, [rsp+98h+var_40]
0x1802e337b  call    ??$CoCreateInstance@UIMFCameraConfigurationManager@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIMFCameraConfigurationManager@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IMFCameraConfigurationManager,wil::err_exception_policy>(_GUID const &,ulong)
0x1802e3380  nop
0x1802e3381  mov     [rsp+98h+ppMFAttributes], rsi
0x1802e3386  lea     edx, [rsi+1]; cInitialSize
0x1802e3389  lea     rcx, [rsp+98h+ppMFAttributes]; ppMFAttributes
0x1802e338e  call    cs:__imp_MFCreateAttributes
0x1802e3394  mov     rcx, [rsp+98h]; this
0x1802e339c  test    eax, eax
0x1802e339e  js      loc_1802E3677
0x1802e33a4  mov     r9, [rsp+98h+ppMFAttributes]
0x1802e33a9  lea     rcx, [r13+28h]; this
0x1802e33ad  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1802e33b2  mov     r8, rax
0x1802e33b5  mov     rax, [r9]
0x1802e33b8  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x1802e33bf  mov     rcx, r9
0x1802e33c2  mov     rax, [rax+0C8h]
0x1802e33c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e33ce  mov     rcx, [rsp+98h]; this
0x1802e33d6  test    eax, eax
0x1802e33d8  js      loc_1802E3689
0x1802e33de  mov     [rsp+98h+var_68], rsi
0x1802e33e3  mov     rcx, [rsp+98h+var_40]
0x1802e33e8  mov     rax, [rcx]
0x1802e33eb  mov     [rsp+98h+var_68], rsi
0x1802e33f0  lea     r8, [rsp+98h+var_68]
0x1802e33f5  mov     rdx, [rsp+98h+ppMFAttributes]
0x1802e33fa  mov     rax, [rax+18h]
0x1802e33fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3403  mov     rcx, [rsp+98h]; this
0x1802e340b  test    eax, eax
0x1802e340d  js      loc_1802E369E
0x1802e3413  mov     rcx, [rsp+98h+var_68]
0x1802e3418  test    rcx, rcx
0x1802e341b  jz      loc_1802E3636
0x1802e3421  mov     [rsp+98h+var_60], rsi
0x1802e3426  mov     [rsp+98h+var_48], rsi
0x1802e342b  mov     dword ptr [rsp+98h+arg_10], esi
0x1802e3432  mov     [rsp+98h+var_50], rsi
0x1802e3437  mov     [rsp+98h+arg_18], esi
0x1802e343e  mov     ebx, esi
0x1802e3440  mov     rax, [rcx]
0x1802e3443  mov     rax, [rax+108h]
0x1802e344a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e344f  cmp     ebx, eax
0x1802e3451  jnb     loc_1802E359E
0x1802e3457  mov     rsi, [rsp+98h+var_68]
0x1802e345c  mov     rax, [rsi]
0x1802e345f  mov     r14, [rax+110h]
0x1802e3466  mov     rcx, [rsp+98h+var_60]
0x1802e346b  mov     [rsp+98h+var_60], 0
0x1802e3474  test    rcx, rcx
0x1802e3477  jz      short loc_1802E3486
0x1802e3479  mov     rax, [rcx]
0x1802e347c  mov     rax, [rax+10h]
0x1802e3480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3485  nop
0x1802e3486  lea     r8, [rsp+98h+var_60]
0x1802e348b  mov     edx, ebx
0x1802e348d  mov     rcx, rsi
0x1802e3490  mov     rax, r14
0x1802e3493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3498  mov     rcx, [rsp+98h]; this
0x1802e34a0  xor     esi, esi
0x1802e34a2  test    eax, eax
0x1802e34a4  js      loc_1802E36B3
0x1802e34aa  mov     rcx, [rsp+98h+var_60]
0x1802e34af  mov     rax, [rcx]
0x1802e34b2  lea     rdx, [rsp+98h+arg_18]
0x1802e34ba  mov     qword ptr [rsp+98h+var_78], rdx; int
0x1802e34bf  lea     r9, [rsp+98h+var_50]
0x1802e34c4  lea     r8, [rsp+98h+arg_10]
0x1802e34cc  lea     rdx, [rsp+98h+var_48]
0x1802e34d1  mov     rax, [rax+28h]
0x1802e34d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e34da  mov     rcx, [rsp+98h]; this
0x1802e34e2  test    eax, eax
0x1802e34e4  js      loc_1802E36C5
0x1802e34ea  lea     rax, [rsp+98h+var_60]
0x1802e34ef  mov     [rsp+98h+var_38], rax
0x1802e34f4  mov     [rsp+98h+var_30], 1
0x1802e34f9  cmp     dword ptr [rsp+98h+arg_10], 18h
0x1802e3501  jnz     short loc_1802E356C
0x1802e3503  mov     rcx, [rsp+98h+var_48]
0x1802e3508  test    rcx, rcx
0x1802e350b  jz      short loc_1802E356C
0x1802e350d  test    r15d, r15d
0x1802e3510  jz      short loc_1802E353B
0x1802e3512  cmp     r15d, 1
0x1802e3516  jnz     loc_1802E36DA
0x1802e351c  mov     rax, [rcx]
0x1802e351f  cmp     rax, qword ptr cs:_GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data1
0x1802e3526  jnz     short loc_1802E356C
0x1802e3528  mov     rax, [rcx+8]
0x1802e352c  cmp     rax, qword ptr cs:_GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data4
0x1802e3533  jnz     short loc_1802E356C
0x1802e3535  cmp     dword ptr [rcx+10h], 29h ; ')'
0x1802e3539  jmp     short loc_1802E3558
0x1802e353b  mov     rax, [rcx]
0x1802e353e  cmp     rax, qword ptr cs:_GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data1
0x1802e3545  jnz     short loc_1802E356C
0x1802e3547  mov     rax, [rcx+8]
0x1802e354b  cmp     rax, qword ptr cs:_GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data4
0x1802e3552  jnz     short loc_1802E356C
0x1802e3554  cmp     dword ptr [rcx+10h], 2Bh ; '+'
0x1802e3558  jnz     short loc_1802E356C
0x1802e355a  mov     rax, [rsp+98h+var_50]
0x1802e355f  test    byte ptr [rax+18h], 1
0x1802e3563  jz      short loc_1802E356C
0x1802e3565  mov     dil, 1
0x1802e3568  mov     [rax+10h], rsi
0x1802e356c  mov     [rsp+98h+var_30], sil
0x1802e3571  mov     rcx, [rsp+98h+var_60]
0x1802e3576  mov     rax, [rcx]
0x1802e3579  mov     rax, [rax+30h]
0x1802e357d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3582  mov     rcx, [rsp+98h]; this
0x1802e358a  test    eax, eax
0x1802e358c  js      loc_1802E3701
0x1802e3592  inc     ebx
0x1802e3594  mov     rcx, [rsp+98h+var_68]
0x1802e3599  jmp     loc_1802E3440
0x1802e359e  lea     rcx, [rsp+98h+var_60]
0x1802e35a3  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e35a8  test    dil, dil
0x1802e35ab  jz      loc_1802E3636
0x1802e35b1  lea     rdx, [rsp+98h+arg_10]
0x1802e35b9  lea     rcx, [rsp+98h+var_68]
0x1802e35be  call    ??$query@UIMFCameraControlDefaultsCollectionInternal@@@?$com_ptr_t@UIMFCameraControlDefaultsCollection@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollection,wil::err_exception_policy>::query<IMFCameraControlDefaultsCollectionInternal>(void)
0x1802e35c3  nop
0x1802e35c4  mov     rcx, [rsp+98h+arg_10]
0x1802e35cc  mov     rax, [rcx]
0x1802e35cf  xor     r8d, r8d
0x1802e35d2  xor     edx, edx
0x1802e35d4  mov     rax, [rax+18h]
0x1802e35d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e35dd  mov     rcx, [rsp+98h]; this
0x1802e35e5  test    eax, eax
0x1802e35e7  js      loc_1802E3716
0x1802e35ed  mov     r10, [r13+38h]
0x1802e35f1  lea     rcx, [r13+28h]; this
0x1802e35f5  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1802e35fa  mov     rdx, rax
0x1802e35fd  mov     rax, [r10]
0x1802e3600  mov     r9, [rsp+98h+var_68]
0x1802e3605  lea     r8, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x1802e360c  mov     rcx, r10
0x1802e360f  mov     rax, [rax+58h]
0x1802e3613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e3618  mov     rcx, [rsp+98h]; this
0x1802e3620  test    eax, eax
0x1802e3622  js      loc_1802E372A
0x1802e3628  lea     rcx, [rsp+98h+arg_10]
0x1802e3630  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3635  nop
0x1802e3636  lea     rcx, [rsp+98h+var_68]
0x1802e363b  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3640  nop
0x1802e3641  lea     rcx, [rsp+98h+ppMFAttributes]
0x1802e3646  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e364b  nop
0x1802e364c  lea     rcx, [rsp+98h+var_40]
0x1802e3651  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e3656  mov     al, dil
0x1802e3659  jmp     short loc_1802E365D
0x1802e365b  xor     al, al
0x1802e365d  lea     r11, [rsp+98h+var_28]
0x1802e3662  mov     rbx, [r11+30h]
0x1802e3666  mov     rsi, [r11+38h]
0x1802e366a  mov     rsp, r11
0x1802e366d  pop     r15
0x1802e366f  pop     r14
0x1802e3671  pop     r13
0x1802e3673  pop     r12
0x1802e3675  pop     rdi
0x1802e3676  retn
0x1802e3677  mov     r9d, eax; char *
0x1802e367a  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3681  lea     edx, [rsi+4Fh]; void *
0x1802e3684  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3689  mov     r9d, eax; char *
0x1802e368c  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3693  mov     edx, 50h ; 'P'; void *
0x1802e3698  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e369e  mov     r9d, eax; char *
0x1802e36a1  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e36a8  mov     edx, 52h ; 'R'; void *
0x1802e36ad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e36b3  mov     r9d, eax; char *
0x1802e36b6  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e36bd  lea     edx, [rsi+5Fh]; void *
0x1802e36c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e36c5  mov     r9d, eax; char *
0x1802e36c8  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e36cf  mov     edx, 60h ; '`'; void *
0x1802e36d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e36da  mov     ecx, 80070057h
0x1802e36df  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1802e36e4  mov     r9d, eax; char *
0x1802e36e7  mov     rcx, [rsp+98h]; this
0x1802e36ef  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e36f6  mov     edx, 8Bh; void *
0x1802e36fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3701  mov     r9d, eax; char *
0x1802e3704  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e370b  mov     edx, 65h ; 'e'; void *
0x1802e3710  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e3716  mov     r9d, eax; char *
0x1802e3719  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3720  mov     edx, 95h; void *
0x1802e3725  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e372a  mov     r9d, eax; char *
0x1802e372d  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e3734  mov     edx, 96h; void *
0x1802e3739  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
