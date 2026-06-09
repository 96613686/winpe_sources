# winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::EnableEffect(winrt::WindowsUdk::Media::Devices::CameraEffect)

- ea: `0x1802e2a7c`
- end: `0x1802e2db5`
- name: `?EnableEffect@CameraConfiguration@implementation@Devices@Media@WindowsUdk@winrt@@QEAAXW4CameraEffect@3456@@Z`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1802e2a50`

## callees

- `0x180025348`
- `0x1800483f4`
- `0x1800ce544`
- `0x1800e488c`
- `0x18012a5f0`
- `0x1802e25cc`
- `0x1802e2a7c`
- `0x1804a2010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x1802e2aa4`
- `MFPlat!MFCreateAttributes` at `0x1802e2aa4`

## string_xrefs

- `0x1802e2c63`: `FRAMESERVER_CONFIGURATION_ALL_APPS`
- `0x1802e2c83`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2cd2`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2ce7`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2cfc`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2d11`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2d34`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2d49`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2d5e`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2d76`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2d8e`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`
- `0x1802e2da3`: `shellcommon\undockeddevkit\libs\windowsudk.media.devices\cameraconfiguration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall winrt::WindowsUdk::Media::Devices::implementation::CameraConfiguration::EnableEffect(
        __int64 a1,
        int a2)
{
  HRESULT v4; // eax
  const wchar_t *v5; // rax
  __int64 v6; // r10
  int v7; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  const wchar_t *v17; // rax
  __int64 v18; // r11
  int v19; // eax
  unsigned int v21; // eax
  int v22; // [rsp+20h] [rbp-60h]
  __int64 v23; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v24; // [rsp+48h] [rbp-38h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+50h] [rbp-30h] BYREF
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  __int64 v27; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v28[2]; // [rsp+68h] [rbp-18h] BYREF
  char v29; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  unsigned int v31; // [rsp+B0h] [rbp+30h] BYREF
  int v32; // [rsp+B8h] [rbp+38h] BYREF

  ppMFAttributes = 0;
  v4 = MFCreateAttributes(&ppMFAttributes, 1u);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v4,
      v22);
  v5 = winrt::hstring::c_str((winrt::hstring *)(a1 + 40));
  v7 = (*(__int64 (__fastcall **)(__int64, const IID *, const wchar_t *))(*(_QWORD *)v6 + 200LL))(
         v6,
         &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
         v5);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v7,
      v22);
  v24 = 0;
  v8 = *(__int64 **)(a1 + 48);
  v9 = *v8;
  v24 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, IMFAttributes *, __int64 **))(v9 + 24))(v8, ppMFAttributes, &v24);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v10,
      v22);
  v23 = 0;
  if ( a2 )
  {
    v21 = wil::verify_hresult<long>(2147942487LL, v11);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)v21,
      v22);
  }
  v12 = *v24;
  v23 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64))(v12 + 280))(v24, 1, 43, 0xFFFFFFFFLL);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v13,
      48);
  v28[0] = 0;
  v31 = 0;
  v26 = 0;
  v32 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned int *, __int64 *))(*(_QWORD *)v23 + 40LL))(
          v23,
          v28,
          &v31,
          &v26);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v14,
      (int)&v32);
  v28[1] = &v23;
  v29 = 1;
  if ( v31 < 0x18 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v32);
  if ( (unsigned int)v32 < 0x20 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v32);
  if ( (*(_BYTE *)(v26 + 24) & 1) != 0 )
    *(_QWORD *)(v26 + 16) = 1;
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 48LL))(v23);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v15,
      (int)&v32);
  wil::com_ptr_t<IMFCameraControlDefaultsCollection,wil::err_exception_policy>::query<IMFCameraControlDefaultsCollectionInternal>(
    &v24,
    &v27);
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v27 + 24LL))(v27, 0, 0);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v16,
      (int)&v32);
  v17 = winrt::hstring::c_str((winrt::hstring *)(a1 + 40));
  v19 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *))(*(_QWORD *)v18 + 88LL))(
          v18,
          v17,
          L"FRAMESERVER_CONFIGURATION_ALL_APPS",
          v24);
  if ( v19 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"shellcommon\\undockeddevkit\\libs\\windowsudk.media.devices\\cameraconfiguration.cpp",
      (const char *)(unsigned int)v19,
      (int)&v32);
  wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v27);
  wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v23);
  wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&v24);
  return wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(&ppMFAttributes);
}

```

## disassembly

```asm
0x1802e2a7c  mov     [rsp-18h+arg_0], rbx
0x1802e2a81  push    rbp
0x1802e2a82  push    rsi
0x1802e2a83  push    rdi
0x1802e2a84  mov     rbp, rsp
0x1802e2a87  sub     rsp, 80h
0x1802e2a8e  mov     ebx, edx
0x1802e2a90  mov     rdi, rcx
0x1802e2a93  mov     [rbp+ppMFAttributes], 0
0x1802e2a9b  mov     edx, 1; cInitialSize
0x1802e2aa0  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x1802e2aa4  call    cs:__imp_MFCreateAttributes
0x1802e2aaa  mov     rcx, [rbp+18h]; this
0x1802e2aae  test    eax, eax
0x1802e2ab0  js      loc_1802E2CE4
0x1802e2ab6  mov     r10, [rbp+ppMFAttributes]
0x1802e2aba  lea     rcx, [rdi+28h]; this
0x1802e2abe  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1802e2ac3  mov     rdx, [r10]
0x1802e2ac6  mov     r9, [rdx+0C8h]
0x1802e2acd  mov     r8, rax
0x1802e2ad0  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x1802e2ad7  mov     rcx, r10
0x1802e2ada  mov     rax, r9
0x1802e2add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2ae2  mov     rcx, [rbp+18h]; this
0x1802e2ae6  test    eax, eax
0x1802e2ae8  js      loc_1802E2CF9
0x1802e2aee  mov     [rbp+var_38], 0
0x1802e2af6  mov     rcx, [rdi+30h]
0x1802e2afa  mov     rax, [rcx]
0x1802e2afd  mov     [rbp+var_38], 0
0x1802e2b05  lea     r8, [rbp+var_38]
0x1802e2b09  mov     rdx, [rbp+ppMFAttributes]
0x1802e2b0d  mov     rax, [rax+18h]
0x1802e2b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2b16  mov     rcx, [rbp+18h]; this
0x1802e2b1a  test    eax, eax
0x1802e2b1c  js      loc_1802E2D0E
0x1802e2b22  mov     [rbp+var_40], 0
0x1802e2b2a  test    ebx, ebx
0x1802e2b2c  jnz     loc_1802E2D23
0x1802e2b32  mov     rcx, [rbp+var_38]
0x1802e2b36  mov     rax, [rcx]
0x1802e2b39  mov     [rbp+var_40], 0
0x1802e2b41  lea     rdx, [rbp+var_40]
0x1802e2b45  mov     [rsp+80h+var_58], rdx
0x1802e2b4a  mov     [rsp+80h+var_60], 30h ; '0'; int
0x1802e2b52  or      r9d, 0FFFFFFFFh
0x1802e2b56  lea     edx, [rbx+1]
0x1802e2b59  lea     r8d, [rbx+2Bh]
0x1802e2b5d  mov     rax, [rax+118h]
0x1802e2b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2b69  mov     rcx, [rbp+18h]; this
0x1802e2b6d  test    eax, eax
0x1802e2b6f  js      loc_1802E2D46
0x1802e2b75  mov     [rbp+var_18], 0
0x1802e2b7d  mov     [rbp+arg_10], ebx
0x1802e2b80  mov     [rbp+var_28], 0
0x1802e2b88  mov     [rbp+arg_18], ebx
0x1802e2b8b  mov     rcx, [rbp+var_40]
0x1802e2b8f  mov     rax, [rcx]
0x1802e2b92  lea     rdx, [rbp+arg_18]
0x1802e2b96  mov     qword ptr [rsp+80h+var_60], rdx; int
0x1802e2b9b  lea     r9, [rbp+var_28]
0x1802e2b9f  lea     r8, [rbp+arg_10]
0x1802e2ba3  lea     rdx, [rbp+var_18]
0x1802e2ba7  mov     rax, [rax+28h]
0x1802e2bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2bb0  mov     rcx, [rbp+18h]; this
0x1802e2bb4  test    eax, eax
0x1802e2bb6  js      loc_1802E2D5B
0x1802e2bbc  lea     rax, [rbp+var_40]
0x1802e2bc0  mov     [rbp+var_10], rax
0x1802e2bc4  mov     [rbp+var_8], 1
0x1802e2bc8  cmp     [rbp+arg_10], 18h
0x1802e2bcc  setb    al
0x1802e2bcf  mov     rcx, [rbp+18h]; this
0x1802e2bd3  test    al, al
0x1802e2bd5  jnz     loc_1802E2D70
0x1802e2bdb  cmp     [rbp+arg_18], 20h ; ' '
0x1802e2bdf  setb    al
0x1802e2be2  mov     rcx, [rbp+18h]; this
0x1802e2be6  test    al, al
0x1802e2be8  jnz     loc_1802E2D88
0x1802e2bee  mov     rax, [rbp+var_28]
0x1802e2bf2  test    byte ptr [rax+18h], 1
0x1802e2bf6  jz      short loc_1802E2C00
0x1802e2bf8  mov     qword ptr [rax+10h], 1
0x1802e2c00  mov     rcx, [rbp+var_40]
0x1802e2c04  mov     rax, [rcx]
0x1802e2c07  mov     rax, [rax+30h]
0x1802e2c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2c10  mov     rcx, [rbp+18h]; this
0x1802e2c14  test    eax, eax
0x1802e2c16  js      loc_1802E2DA0
0x1802e2c1c  lea     rdx, [rbp+var_20]
0x1802e2c20  lea     rcx, [rbp+var_38]
0x1802e2c24  call    ??$query@UIMFCameraControlDefaultsCollectionInternal@@@?$com_ptr_t@UIMFCameraControlDefaultsCollection@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollection,wil::err_exception_policy>::query<IMFCameraControlDefaultsCollectionInternal>(void)
0x1802e2c29  nop
0x1802e2c2a  mov     rcx, [rbp+var_20]
0x1802e2c2e  mov     rax, [rcx]
0x1802e2c31  xor     r8d, r8d
0x1802e2c34  xor     edx, edx
0x1802e2c36  mov     rax, [rax+18h]
0x1802e2c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2c3f  mov     rcx, [rbp+18h]; this
0x1802e2c43  test    eax, eax
0x1802e2c45  js      loc_1802E2CCF
0x1802e2c4b  mov     r11, [rdi+38h]
0x1802e2c4f  lea     rcx, [rdi+28h]; this
0x1802e2c53  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1802e2c58  mov     rdx, [r11]
0x1802e2c5b  mov     r10, [rdx+58h]
0x1802e2c5f  mov     r9, [rbp+var_38]
0x1802e2c63  lea     r8, aFrameserverCon; "FRAMESERVER_CONFIGURATION_ALL_APPS"
0x1802e2c6a  mov     rdx, rax
0x1802e2c6d  mov     rcx, r11
0x1802e2c70  mov     rax, r10
0x1802e2c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802e2c78  mov     rcx, [rbp+18h]; this
0x1802e2c7c  test    eax, eax
0x1802e2c7e  jns     short loc_1802E2C95
0x1802e2c80  mov     r9d, eax; char *
0x1802e2c83  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2c8a  mov     edx, 0D5h; void *
0x1802e2c8f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802e2c94  nop
0x1802e2c95  lea     rcx, [rbp+var_20]
0x1802e2c99  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e2c9e  nop
0x1802e2c9f  lea     rcx, [rbp+var_40]
0x1802e2ca3  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e2ca8  nop
0x1802e2ca9  lea     rcx, [rbp+var_38]
0x1802e2cad  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e2cb2  nop
0x1802e2cb3  lea     rcx, [rbp+ppMFAttributes]
0x1802e2cb7  call    ??1?$com_ptr_t@UIMFCameraControlDefaultsCollectionInternal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>::~com_ptr_t<IMFCameraControlDefaultsCollectionInternal,wil::err_exception_policy>(void)
0x1802e2cbc  mov     rbx, [rsp+80h+arg_0]
0x1802e2cc4  add     rsp, 80h
0x1802e2ccb  pop     rdi
0x1802e2ccc  pop     rsi
0x1802e2ccd  pop     rbp
0x1802e2cce  retn
0x1802e2ccf  mov     r9d, eax; char *
0x1802e2cd2  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2cd9  mov     edx, 0D4h; void *
0x1802e2cde  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2ce4  mov     r9d, eax; char *
0x1802e2ce7  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2cee  mov     edx, 0A5h; void *
0x1802e2cf3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2cf9  mov     r9d, eax; char *
0x1802e2cfc  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2d03  mov     edx, 0A6h; void *
0x1802e2d08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2d0e  mov     r9d, eax; char *
0x1802e2d11  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2d18  mov     edx, 0A8h; void *
0x1802e2d1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2d23  mov     ecx, 80070057h
0x1802e2d28  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1802e2d2d  mov     r9d, eax; char *
0x1802e2d30  mov     rcx, [rbp+18h]; this
0x1802e2d34  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2d3b  mov     edx, 0D0h; void *
0x1802e2d40  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2d46  mov     r9d, eax; char *
0x1802e2d49  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2d50  mov     edx, 0B5h; void *
0x1802e2d55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2d5b  mov     r9d, eax; char *
0x1802e2d5e  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2d65  mov     edx, 0BCh; void *
0x1802e2d6a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2d70  mov     r9d, 8000FFFFh; char *
0x1802e2d76  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2d7d  mov     edx, 0C3h; void *
0x1802e2d82  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2d88  mov     r9d, 8000FFFFh; char *
0x1802e2d8e  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2d95  mov     edx, 0C4h; void *
0x1802e2d9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802e2da0  mov     r9d, eax; char *
0x1802e2da3  lea     r8, aShellcommonUnd_43; "shellcommon\\undockeddevkit\\libs\\wind"...
0x1802e2daa  mov     edx, 0C1h; void *
0x1802e2daf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
