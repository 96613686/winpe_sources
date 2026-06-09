# DeleteIsolationContainer

- ea: `0x18004a380`
- end: `0x18004a562`
- name: `DeleteIsolationContainer`
- size: `482`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001a88c`
- `0x180042ca0`
- `0x180042dec`
- `0x18004834c`
- `0x180048550`
- `0x180048c08`
- `0x1800498cc`
- `0x180049c64`
- `0x18004a124`
- `0x18004a380`
- `0x18004a678`
- `0x18004a6e0`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a3fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a4d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a51b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a3fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a4d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a51b`
- `USERENV!DeleteAppContainerProfile` at `0x18004a533`
- `USERENV!DeleteAppContainerProfile` at `0x18004a533`

## pseudocode

```c
__int64 __fastcall DeleteIsolationContainer(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int EmbeddedContainerIsolationPolicy; // ebx
  int v5; // ebx
  DWORD v6; // ecx
  int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  DWORD v11; // ecx
  int v12; // eax
  __int64 v13; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+38h] [rbp-21h] BYREF
  _OWORD v15[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v16; // [rsp+60h] [rbp+7h]
  _BYTE hstringHeader[32]; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v18; // [rsp+88h] [rbp+2Fh]
  __int64 v19; // [rsp+98h] [rbp+3Fh]

  v16 = 0;
  v19 = 0;
  memset(v15, 0, sizeof(v15));
  memset(hstringHeader, 0, sizeof(hstringHeader));
  v18 = 0;
  GetManifestProperties(a1, a2, a3, 0, (struct _ISOLATION_MANIFSET_PROPERTIES *)hstringHeader);
  EmbeddedContainerIsolationPolicy = GetEmbeddedContainerIsolationPolicy(
                                       (struct _UNICODE_STRING *)hstringHeader,
                                       (struct _ISOLATION_CONTAINER *)v15);
  if ( EmbeddedContainerIsolationPolicy < 0 )
  {
    IsolationApi::TelemetryHelper::LogContainerNotFoundError(a3);
    v5 = EmbeddedContainerIsolationPolicy | 0x10000000;
LABEL_3:
    v6 = v5;
    goto LABEL_4;
  }
  if ( HIDWORD(v15[0]) )
  {
    if ( HIDWORD(v15[0]) != 1 )
      return 0;
    v6 = 87;
LABEL_4:
    SetLastError(v6);
    return 0;
  }
  if ( RunningInAppContainer() )
  {
    v14 = 0;
    *(_QWORD *)&hstringHeader[24] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)hstringHeader,
      L"Windows.ApplicationModel.Core.RestrictedAppContainer",
      0x35u,
      0x34u);
    v8 = GetActivationFactoryHelper<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::IRestrictedAppContainerStatics>>(
           *(_QWORD *)&hstringHeader[24],
           &v14);
    if ( v8 < 0 )
      goto LABEL_16;
    Microsoft::WRL::Wrappers::HStringReference::HStringReference(hstringHeader, v15);
    v9 = v14;
    v13 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v14 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    v8 = v10(v9, *(_QWORD *)&hstringHeader[24], &v13);
    if ( v8 >= 0 )
      v8 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v13);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
    if ( v8 < 0 )
    {
LABEL_16:
      IsolationApi::TelemetryHelper::LogDeleteContainerError(v8);
      v11 = (unsigned __int16)v8;
      if ( (v8 & 0x1FFF0000) != 0x70000 )
        v11 = v8;
      SetLastError(v11);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      return 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  }
  else
  {
    v12 = DeleteAppContainerProfile(*(_QWORD *)&v15[0]);
    v5 = v12;
    if ( v12 < 0 )
    {
      IsolationApi::TelemetryHelper::LogDeleteContainerError(v12);
      if ( (v5 & 0x1FFF0000) == 0x70000 )
        v5 = (unsigned __int16)v5;
      goto LABEL_3;
    }
  }
  SetLastError(0);
  IsolationApi::TelemetryHelper::LogDeleteIsolationContainerSuccess();
  return 1;
}

```

## disassembly

```asm
0x18004a380  mov     [rsp-8+arg_0], rbx
0x18004a385  mov     [rsp-8+arg_8], rdi
0x18004a38a  push    rbp
0x18004a38b  lea     rbp, [rsp-57h]
0x18004a390  sub     rsp, 0B0h
0x18004a397  mov     rax, cs:__security_cookie
0x18004a39e  xor     rax, rsp
0x18004a3a1  mov     [rbp+57h+var_10], rax
0x18004a3a5  xor     eax, eax
0x18004a3a7  xorps   xmm0, xmm0
0x18004a3aa  xorps   xmm1, xmm1
0x18004a3ad  mov     [rbp+57h+var_50], rax
0x18004a3b1  mov     [rbp+57h+var_18], rax
0x18004a3b5  xor     r9d, r9d; struct _ISO_ISOLATION_OPTIONS *
0x18004a3b8  lea     rax, [rbp+57h+hstringHeader]
0x18004a3bc  mov     rdi, r8
0x18004a3bf  mov     [rsp+0B0h+var_90], rax; struct _ISOLATION_MANIFSET_PROPERTIES *
0x18004a3c4  movups  [rbp+57h+var_70], xmm0
0x18004a3c8  movups  [rbp+57h+var_60], xmm0
0x18004a3cc  movups  xmmword ptr [rbp+57h+hstringHeader], xmm1
0x18004a3d0  movups  xmmword ptr [rbp+57h+hstringHeader+10h], xmm1
0x18004a3d4  movups  [rbp+57h+var_28], xmm1
0x18004a3d8  call    ?GetManifestProperties@@YAXPEBG00PEAU_ISO_ISOLATION_OPTIONS@@PEAU_ISOLATION_MANIFSET_PROPERTIES@@@Z; GetManifestProperties(ushort const *,ushort const *,ushort const *,_ISO_ISOLATION_OPTIONS *,_ISOLATION_MANIFSET_PROPERTIES *)
0x18004a3dd  lea     rcx, [rbp+57h+hstringHeader]; struct _UNICODE_STRING *
0x18004a3e1  lea     rdx, [rbp+57h+var_70]; struct _ISOLATION_CONTAINER *
0x18004a3e5  call    GetEmbeddedContainerIsolationPolicy
0x18004a3ea  mov     ebx, eax
0x18004a3ec  test    eax, eax
0x18004a3ee  jns     short loc_18004A40B
0x18004a3f0  mov     rcx, rdi; unsigned __int16 *
0x18004a3f3  call    ?LogContainerNotFoundError@TelemetryHelper@IsolationApi@@SAXPEBG@Z; IsolationApi::TelemetryHelper::LogContainerNotFoundError(ushort const *)
0x18004a3f8  bts     ebx, 1Ch
0x18004a3fc  mov     ecx, ebx; dwErrCode
0x18004a3fe  call    cs:__imp_SetLastError
0x18004a404  xor     eax, eax
0x18004a406  jmp     loc_18004A4E1
0x18004a40b  mov     ecx, dword ptr [rbp+57h+var_70+0Ch]
0x18004a40e  test    ecx, ecx
0x18004a410  jz      short loc_18004A41E
0x18004a412  cmp     ecx, 1
0x18004a415  jnz     short loc_18004A404
0x18004a417  mov     ecx, 57h ; 'W'
0x18004a41c  jmp     short loc_18004A3FE
0x18004a41e  call    ?RunningInAppContainer@@YA_NXZ; RunningInAppContainer(void)
0x18004a423  test    al, al
0x18004a425  jz      loc_18004A52F
0x18004a42b  mov     r9d, 34h ; '4'; unsigned int
0x18004a431  mov     [rbp+57h+var_78], 0
0x18004a439  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Core_RestrictedAppContainer@@3QBGB; "Windows.ApplicationModel.Core.Restricte"...
0x18004a440  mov     qword ptr [rbp+57h+hstringHeader+18h], 0
0x18004a448  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004a44c  lea     r8d, [r9+1]; unsigned int
0x18004a450  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004a455  mov     rcx, qword ptr [rbp+57h+hstringHeader+18h]
0x18004a459  lea     rdx, [rbp+57h+var_78]
0x18004a45d  call    ??$GetActivationFactoryHelper@V?$ComPtr@UIRestrictedAppContainerStatics@Core@ApplicationModel@Windows@@@WRL@Microsoft@@@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRestrictedAppContainerStatics@Core@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; GetActivationFactoryHelper<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::IRestrictedAppContainerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::IRestrictedAppContainerStatics>>)
0x18004a462  mov     ebx, eax
0x18004a464  test    eax, eax
0x18004a466  js      loc_18004A502
0x18004a46c  lea     rdx, [rbp+57h+var_70]
0x18004a470  lea     rcx, [rbp+57h+hstringHeader]
0x18004a474  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004a479  mov     rdi, [rbp+57h+var_78]
0x18004a47d  lea     rcx, [rbp+57h+var_80]
0x18004a481  mov     [rbp+57h+var_80], 0
0x18004a489  mov     rax, [rdi]
0x18004a48c  mov     rbx, [rax+40h]
0x18004a490  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a495  mov     rdx, qword ptr [rbp+57h+hstringHeader+18h]
0x18004a499  lea     r8, [rbp+57h+var_80]
0x18004a49d  mov     rcx, rdi
0x18004a4a0  mov     rax, rbx
0x18004a4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4a8  mov     ebx, eax
0x18004a4aa  test    eax, eax
0x18004a4ac  js      short loc_18004A4B9
0x18004a4ae  mov     rcx, [rbp+57h+var_80]
0x18004a4b2  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x18004a4b7  mov     ebx, eax
0x18004a4b9  lea     rcx, [rbp+57h+var_80]
0x18004a4bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a4c2  test    ebx, ebx
0x18004a4c4  js      short loc_18004A502
0x18004a4c6  lea     rcx, [rbp+57h+var_78]
0x18004a4ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a4cf  xor     ecx, ecx; dwErrCode
0x18004a4d1  call    cs:__imp_SetLastError
0x18004a4d7  call    ?LogDeleteIsolationContainerSuccess@TelemetryHelper@IsolationApi@@SAXXZ; IsolationApi::TelemetryHelper::LogDeleteIsolationContainerSuccess(void)
0x18004a4dc  mov     eax, 1
0x18004a4e1  mov     rcx, [rbp+57h+var_10]
0x18004a4e5  xor     rcx, rsp; StackCookie
0x18004a4e8  call    __security_check_cookie
0x18004a4ed  lea     r11, [rsp+0B0h+var_s0]
0x18004a4f5  mov     rbx, [r11+10h]
0x18004a4f9  mov     rdi, [r11+18h]
0x18004a4fd  mov     rsp, r11
0x18004a500  pop     rbp
0x18004a501  retn
0x18004a502  mov     ecx, ebx; int
0x18004a504  call    ?LogDeleteContainerError@TelemetryHelper@IsolationApi@@SAXJ@Z; IsolationApi::TelemetryHelper::LogDeleteContainerError(long)
0x18004a509  mov     eax, ebx
0x18004a50b  movzx   ecx, bx
0x18004a50e  and     eax, 1FFF0000h
0x18004a513  cmp     eax, 70000h
0x18004a518  cmovnz  ecx, ebx; dwErrCode
0x18004a51b  call    cs:__imp_SetLastError
0x18004a521  lea     rcx, [rbp+57h+var_78]
0x18004a525  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a52a  jmp     loc_18004A404
0x18004a52f  mov     rcx, qword ptr [rbp+57h+var_70]
0x18004a533  call    cs:__imp_DeleteAppContainerProfile
0x18004a539  mov     ebx, eax
0x18004a53b  test    eax, eax
0x18004a53d  jns     short loc_18004A4CF
0x18004a53f  mov     ecx, eax; int
0x18004a541  call    ?LogDeleteContainerError@TelemetryHelper@IsolationApi@@SAXJ@Z; IsolationApi::TelemetryHelper::LogDeleteContainerError(long)
0x18004a546  mov     ecx, ebx
0x18004a548  and     ecx, 1FFF0000h
0x18004a54e  cmp     ecx, 70000h
0x18004a554  jnz     loc_18004A3FC
0x18004a55a  movzx   ebx, bx
0x18004a55d  jmp     loc_18004A3FC
```
