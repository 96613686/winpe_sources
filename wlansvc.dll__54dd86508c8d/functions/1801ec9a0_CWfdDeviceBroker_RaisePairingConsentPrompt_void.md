# CWfdDeviceBroker::RaisePairingConsentPrompt(void)

- ea: `0x1801ec9a0`
- end: `0x1801ecd12`
- name: `?RaisePairingConsentPrompt@CWfdDeviceBroker@@QEAAXXZ`
- size: `882`
- prototype: `void __fastcall(CWfdDeviceBroker *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801ed1f0`

## callees

- `0x180011530`
- `0x1800727d4`
- `0x18007d770`
- `0x1800bd620`
- `0x1800dccc8`
- `0x1800e09a0`
- `0x1801ebb90`
- `0x1801ec3b0`
- `0x1801ec9a0`
- `0x1801ed2d8`
- `0x1802083fc`
- `0x18021e25c`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eca89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801eca89`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801ecca2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801ecca2`

## string_xrefs

- `0x1801ecaa5`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ecb0b`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ecb47`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ecbd1`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ecc3a`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ecc6b`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801eccf9`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801eca93`: `[WfdDeviceBroker] Failed to create CLSID_DeviceConsentProvider object`
- `0x1801ecaac`: `CWfdDeviceBroker::RaisePairingConsentPrompt`
- `0x1801ecb12`: `CWfdDeviceBroker::RaisePairingConsentPrompt`
- `0x1801ecb4e`: `CWfdDeviceBroker::RaisePairingConsentPrompt`
- `0x1801ecbd8`: `CWfdDeviceBroker::RaisePairingConsentPrompt`
- `0x1801ecc41`: `CWfdDeviceBroker::RaisePairingConsentPrompt`
- `0x1801ecc72`: `CWfdDeviceBroker::RaisePairingConsentPrompt`
- `0x1801ecd00`: `CWfdDeviceBroker::RaisePairingConsentPrompt`
- `0x1801ecc28`: `[WfdDeviceBroker] Error while waiting for the user to response to consent prompt`
- `0x1801ecbbf`: `[WfdDeviceBroker] spConsentProvider->RequestConsentResponse failed`
- `0x1801ecb35`: `[WfdDeviceBroker] CallerIdentity::GetPackageSidStringFromProcess failed`
- `0x1801ecaf9`: `[WfdDeviceBroker] MakeAndInitialize<ConsentProviderCallback> failed`
- `0x1801ecc59`: `[WfdDeviceBroker] User did not allow pairing to continue`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CWfdDeviceBroker::RaisePairingConsentPrompt(CWfdDeviceBroker *this)
{
  __int64 v2; // r9
  __int64 v3; // r8
  PVOID *v4; // rcx
  unsigned int v5; // edx
  HRESULT v6; // eax
  int v7; // eax
  unsigned __int16 **v8; // r8
  int PackageSidStringFromProcess; // eax
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // r9d
  __int64 v13; // rbx
  const struct std::nothrow_t *v14; // rdx
  void **v15; // [rsp+40h] [rbp-19h] BYREF
  void *v16; // [rsp+48h] [rbp-11h]
  _QWORD v17[5]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v18; // [rsp+78h] [rbp+1Fh]
  char v19; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v20; // [rsp+C8h] [rbp+6Fh] BYREF
  LPVOID ppv; // [rsp+D0h] [rbp+77h] BYREF
  LPWSTR StringSid; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( !*(_QWORD *)this && !*((_QWORD *)this + 1)
    || (v2 = *((_QWORD *)this + 2)) == 0
    || (v3 = *((_QWORD *)this + 3)) == 0 )
  {
    WFDSvc::CWFDSvcException::Throw(
      -2147024809,
      "CWfdDeviceBroker::RaisePairingConsentPrompt",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
      0x76u,
      L"Invalid arguments");
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF__MAC_SDDl(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      10,
      v3,
      v2,
      v3,
      *((_DWORD *)this + 8),
      *((_DWORD *)this + 9),
      *((_BYTE *)this + 40));
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 40) )
  {
    v15 = &CAutoPtr<WFDSvc::ASP::CASPPublicationPrefix,DefaultArrayDeleter>::`vftable';
    v16 = 0;
    CWfdDeviceBroker::AllocateAndEncodeAepIdString(*((_QWORD *)this + 2), &v15);
    CComInitialization::CComInitialization((CComInitialization *)&v19, v5);
    ppv = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v6 = CoCreateInstance(&CLSID_DeviceConsentProvider, 0, 1u, &GUID_34c879f6_4e0e_4162_8f8e_5ac257a857b4, &ppv);
    if ( v6 < 0 )
      WFDSvc::CWFDSvcException::Throw(
        v6,
        "CWfdDeviceBroker::RaisePairingConsentPrompt",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0x8Cu,
        L"[WfdDeviceBroker] Failed to create CLSID_DeviceConsentProvider object");
    v17[1] = 7;
    v18 = 0;
    v17[3] = 0;
    v17[4] = 0;
    v17[0] = 0;
    v17[2] = *((_QWORD *)this + 3);
    v20 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    v7 = Microsoft::WRL::Details::MakeAndInitialize<ConsentProviderCallback,IConsentResponseCallback,>(&v20);
    if ( v7 < 0 )
      WFDSvc::CWFDSvcException::Throw(
        v7,
        "CWfdDeviceBroker::RaisePairingConsentPrompt",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0x9Cu,
        L"[WfdDeviceBroker] MakeAndInitialize<ConsentProviderCallback> failed");
    StringSid = 0;
    PackageSidStringFromProcess = CallerIdentity::GetPackageSidStringFromProcess(*((_DWORD *)this + 9), &StringSid, v8);
    if ( PackageSidStringFromProcess < 0 )
      WFDSvc::CWFDSvcException::Throw(
        PackageSidStringFromProcess,
        "CWfdDeviceBroker::RaisePairingConsentPrompt",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0xA3u,
        L"[WfdDeviceBroker] CallerIdentity::GetPackageSidStringFromProcess failed");
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 11, &WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids);
    }
    v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPWSTR, _QWORD *, _DWORD, _DWORD, __int64))(*(_QWORD *)ppv + 24LL))(
            ppv,
            0,
            StringSid,
            v17,
            *((_DWORD *)this + 9),
            *((_DWORD *)this + 8),
            v20);
    if ( v10 < 0 )
      WFDSvc::CWFDSvcException::Throw(
        v10,
        "CWfdDeviceBroker::RaisePairingConsentPrompt",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0xB0u,
        L"[WfdDeviceBroker] spConsentProvider->RequestConsentResponse failed");
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, &WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids);
    }
    v13 = v20;
    if ( !wil::handle_wait(*(wil **)(v20 + 48), (void *)0xFFFFFFFFLL, v11, v12) )
      WFDSvc::CWFDSvcException::Throw(
        -2147024891,
        "CWfdDeviceBroker::RaisePairingConsentPrompt",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0xB8u,
        L"[WfdDeviceBroker] Error while waiting for the user to response to consent prompt");
    if ( *(_DWORD *)(v13 + 56) != 1 )
      WFDSvc::CWFDSvcException::Throw(
        -2147024891,
        "CWfdDeviceBroker::RaisePairingConsentPrompt",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0xBDu,
        L"[WfdDeviceBroker] User did not allow pairing to continue");
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    CoUninitialize();
    operator delete(v16, v14);
  }
  else if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 105) >= 3u && (*((_BYTE *)v4 + 108) & 1) != 0 )
  {
    WPP_SF_(v4[12], 13, &WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids);
  }
}

```

## disassembly

```asm
0x1801ec9a0  push    rbp
0x1801ec9a2  push    rbx
0x1801ec9a3  push    rdi
0x1801ec9a4  push    r15
0x1801ec9a6  lea     rbp, [rsp-3Fh]
0x1801ec9ab  sub     rsp, 98h
0x1801ec9b2  mov     rbx, rcx
0x1801ec9b5  xor     edi, edi
0x1801ec9b7  cmp     [rcx], rdi
0x1801ec9ba  jnz     short loc_1801EC9C6
0x1801ec9bc  cmp     [rcx+8], rdi
0x1801ec9c0  jz      loc_1801ECCE7
0x1801ec9c6  mov     r9, [rcx+10h]
0x1801ec9ca  test    r9, r9
0x1801ec9cd  jz      loc_1801ECCE7
0x1801ec9d3  mov     r8, [rcx+18h]
0x1801ec9d7  test    r8, r8
0x1801ec9da  jz      loc_1801ECCE7
0x1801ec9e0  lea     r15, WPP_GLOBAL_Control
0x1801ec9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ec9ee  cmp     rcx, r15
0x1801ec9f1  jz      short loc_1801ECA2F
0x1801ec9f3  cmp     byte ptr [rcx+69h], 3
0x1801ec9f7  jb      short loc_1801ECA2F
0x1801ec9f9  test    byte ptr [rcx+6Ch], 1
0x1801ec9fd  jz      short loc_1801ECA2F
0x1801ec9ff  movzx   eax, byte ptr [rbx+28h]
0x1801eca03  mov     edx, 0Ah
0x1801eca08  mov     [rsp+0B0h+var_78], eax
0x1801eca0c  mov     eax, [rbx+24h]
0x1801eca0f  mov     dword ptr [rsp+0B0h+var_80], eax
0x1801eca13  mov     eax, [rbx+20h]
0x1801eca16  mov     [rsp+0B0h+var_88], eax
0x1801eca1a  mov     [rsp+0B0h+ppv], r8
0x1801eca1f  mov     rcx, [rcx+60h]
0x1801eca23  call    WPP_SF__MAC_SDDl
0x1801eca28  mov     rcx, cs:WPP_GLOBAL_Control
0x1801eca2f  cmp     [rbx+28h], dil
0x1801eca33  jz      loc_1801ECCBF
0x1801eca39  lea     rax, ??_7?$CAutoPtr@UCASPPublicationPrefix@ASP@WFDSvc@@UDefaultArrayDeleter@@@@6B@; const CAutoPtr<WFDSvc::ASP::CASPPublicationPrefix,DefaultArrayDeleter>::`vftable'
0x1801eca40  mov     [rbp+57h+var_70], rax
0x1801eca44  mov     [rbp+57h+var_68], rdi
0x1801eca48  lea     rdx, [rbp+57h+var_70]
0x1801eca4c  mov     rcx, [rbx+10h]
0x1801eca50  call    ?AllocateAndEncodeAepIdString@CWfdDeviceBroker@@CAXPEAY05EAEAV?$CAutoPtr@GUDefaultArrayDeleter@@@@@Z; CWfdDeviceBroker::AllocateAndEncodeAepIdString(uchar (*)[6],CAutoPtr<ushort,DefaultArrayDeleter> &)
0x1801eca55  lea     rcx, [rbp+57h+arg_0]; this
0x1801eca59  call    ??0CComInitialization@@QEAA@K@Z; CComInitialization::CComInitialization(ulong)
0x1801eca5e  nop
0x1801eca5f  mov     [rbp+57h+arg_10], rdi
0x1801eca63  lea     rcx, [rbp+57h+arg_10]
0x1801eca67  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801eca6c  lea     rax, [rbp+57h+arg_10]
0x1801eca70  mov     [rsp+0B0h+ppv], rax; ppv
0x1801eca75  lea     r9, _GUID_34c879f6_4e0e_4162_8f8e_5ac257a857b4; riid
0x1801eca7c  xor     edx, edx; pUnkOuter
0x1801eca7e  lea     r8d, [rdx+1]; dwClsContext
0x1801eca82  lea     rcx, CLSID_DeviceConsentProvider; rclsid
0x1801eca89  call    cs:__imp_CoCreateInstance
0x1801eca8f  test    eax, eax
0x1801eca91  jns     short loc_1801ECABB
0x1801eca93  lea     rcx, aWfddevicebroke_6; "[WfdDeviceBroker] Failed to create CLSI"...
0x1801eca9a  mov     [rsp+0B0h+ppv], rcx; unsigned __int16 *
0x1801eca9f  mov     r9d, 8Ch; unsigned int
0x1801ecaa5  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ecaac  lea     rdx, aCwfddevicebrok_6; "CWfdDeviceBroker::RaisePairingConsentPr"...
0x1801ecab3  mov     ecx, eax; int
0x1801ecab5  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ecabb  mov     [rbp+57h+var_58], 7
0x1801ecac3  xorps   xmm0, xmm0
0x1801ecac6  movdqu  [rbp+57h+var_38], xmm0
0x1801ecacb  mov     [rbp+57h+var_48], rdi
0x1801ecacf  mov     [rbp+57h+var_40], rdi
0x1801ecad3  mov     [rbp+57h+var_60], rdi
0x1801ecad7  mov     rax, [rbx+18h]
0x1801ecadb  mov     [rbp+57h+var_50], rax
0x1801ecadf  mov     [rbp+57h+arg_8], rdi
0x1801ecae3  lea     rcx, [rbp+57h+arg_8]
0x1801ecae7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801ecaec  lea     rcx, [rbp+57h+arg_8]
0x1801ecaf0  call    ??$MakeAndInitialize@VConsentProviderCallback@@UIConsentResponseCallback@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIConsentResponseCallback@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ConsentProviderCallback,IConsentResponseCallback,>(IConsentResponseCallback * *)
0x1801ecaf5  test    eax, eax
0x1801ecaf7  jns     short loc_1801ECB21
0x1801ecaf9  lea     rcx, aWfddevicebroke; "[WfdDeviceBroker] MakeAndInitialize<Con"...
0x1801ecb00  mov     [rsp+0B0h+ppv], rcx; unsigned __int16 *
0x1801ecb05  mov     r9d, 9Ch; unsigned int
0x1801ecb0b  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ecb12  lea     rdx, aCwfddevicebrok_6; "CWfdDeviceBroker::RaisePairingConsentPr"...
0x1801ecb19  mov     ecx, eax; int
0x1801ecb1b  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ecb21  mov     [rbp+57h+StringSid], rdi
0x1801ecb25  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1801ecb29  mov     ecx, [rbx+24h]; dwProcessId
0x1801ecb2c  call    ?GetPackageSidStringFromProcess@CallerIdentity@@YAJKPEAPEAG@Z; CallerIdentity::GetPackageSidStringFromProcess(ulong,ushort * *)
0x1801ecb31  test    eax, eax
0x1801ecb33  jns     short loc_1801ECB5D
0x1801ecb35  lea     rcx, aWfddevicebroke_5; "[WfdDeviceBroker] CallerIdentity::GetPa"...
0x1801ecb3c  mov     [rsp+0B0h+ppv], rcx; unsigned __int16 *
0x1801ecb41  mov     r9d, 0A3h; unsigned int
0x1801ecb47  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ecb4e  lea     rdx, aCwfddevicebrok_6; "CWfdDeviceBroker::RaisePairingConsentPr"...
0x1801ecb55  mov     ecx, eax; int
0x1801ecb57  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ecb5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ecb64  cmp     rcx, r15
0x1801ecb67  jz      short loc_1801ECB8A
0x1801ecb69  cmp     byte ptr [rcx+69h], 3
0x1801ecb6d  jb      short loc_1801ECB8A
0x1801ecb6f  test    byte ptr [rcx+6Ch], 1
0x1801ecb73  jz      short loc_1801ECB8A
0x1801ecb75  mov     edx, 0Bh
0x1801ecb7a  lea     r8, WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids
0x1801ecb81  mov     rcx, [rcx+60h]
0x1801ecb85  call    WPP_SF_
0x1801ecb8a  mov     rcx, [rbp+57h+arg_10]
0x1801ecb8e  mov     rdx, [rbp+57h+arg_8]
0x1801ecb92  mov     rax, [rcx]
0x1801ecb95  mov     [rsp+0B0h+var_80], rdx
0x1801ecb9a  mov     edx, [rbx+20h]
0x1801ecb9d  mov     [rsp+0B0h+var_88], edx
0x1801ecba1  mov     edx, [rbx+24h]
0x1801ecba4  mov     dword ptr [rsp+0B0h+ppv], edx
0x1801ecba8  lea     r9, [rbp+57h+var_60]
0x1801ecbac  mov     r8, [rbp+57h+StringSid]
0x1801ecbb0  xor     edx, edx
0x1801ecbb2  mov     rax, [rax+18h]
0x1801ecbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ecbbb  test    eax, eax
0x1801ecbbd  jns     short loc_1801ECBE7
0x1801ecbbf  lea     rcx, aWfddevicebroke_2; "[WfdDeviceBroker] spConsentProvider->Re"...
0x1801ecbc6  mov     [rsp+0B0h+ppv], rcx; unsigned __int16 *
0x1801ecbcb  mov     r9d, 0B0h; unsigned int
0x1801ecbd1  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ecbd8  lea     rdx, aCwfddevicebrok_6; "CWfdDeviceBroker::RaisePairingConsentPr"...
0x1801ecbdf  mov     ecx, eax; int
0x1801ecbe1  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ecbe7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ecbee  cmp     rcx, r15
0x1801ecbf1  jz      short loc_1801ECC14
0x1801ecbf3  cmp     byte ptr [rcx+69h], 3
0x1801ecbf7  jb      short loc_1801ECC14
0x1801ecbf9  test    byte ptr [rcx+6Ch], 1
0x1801ecbfd  jz      short loc_1801ECC14
0x1801ecbff  mov     edx, 0Ch
0x1801ecc04  lea     r8, WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids
0x1801ecc0b  mov     rcx, [rcx+60h]
0x1801ecc0f  call    WPP_SF_
0x1801ecc14  mov     rbx, [rbp+57h+arg_8]
0x1801ecc18  or      edx, 0FFFFFFFFh; void *
0x1801ecc1b  mov     rcx, [rbx+30h]; this
0x1801ecc1f  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1801ecc24  test    al, al
0x1801ecc26  jnz     short loc_1801ECC53
0x1801ecc28  lea     rax, aWfddevicebroke_3; "[WfdDeviceBroker] Error while waiting f"...
0x1801ecc2f  mov     [rsp+0B0h+ppv], rax; unsigned __int16 *
0x1801ecc34  mov     r9d, 0B8h; unsigned int
0x1801ecc3a  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ecc41  lea     rdx, aCwfddevicebrok_6; "CWfdDeviceBroker::RaisePairingConsentPr"...
0x1801ecc48  mov     ecx, 80070005h; int
0x1801ecc4d  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ecc53  cmp     dword ptr [rbx+38h], 1
0x1801ecc57  jz      short loc_1801ECC84
0x1801ecc59  lea     rax, aWfddevicebroke_4; "[WfdDeviceBroker] User did not allow pa"...
0x1801ecc60  mov     [rsp+0B0h+ppv], rax; unsigned __int16 *
0x1801ecc65  mov     r9d, 0BDh; unsigned int
0x1801ecc6b  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ecc72  lea     rdx, aCwfddevicebrok_6; "CWfdDeviceBroker::RaisePairingConsentPr"...
0x1801ecc79  mov     ecx, 80070005h; int
0x1801ecc7e  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ecc84  lea     rcx, [rbp+57h+StringSid]
0x1801ecc88  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801ecc8d  nop
0x1801ecc8e  lea     rcx, [rbp+57h+arg_8]
0x1801ecc92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801ecc97  nop
0x1801ecc98  lea     rcx, [rbp+57h+arg_10]
0x1801ecc9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801ecca1  nop
0x1801ecca2  call    cs:__imp_CoUninitialize
0x1801ecca8  nop
0x1801ecca9  mov     rcx, [rbp+57h+var_68]; void *
0x1801eccad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801eccb2  add     rsp, 98h
0x1801eccb9  pop     r15
0x1801eccbb  pop     rdi
0x1801eccbc  pop     rbx
0x1801eccbd  pop     rbp
0x1801eccbe  retn
0x1801eccbf  cmp     rcx, r15
0x1801eccc2  jz      short loc_1801ECCB2
0x1801eccc4  cmp     byte ptr [rcx+69h], 3
0x1801eccc8  jb      short loc_1801ECCB2
0x1801eccca  test    byte ptr [rcx+6Ch], 1
0x1801eccce  jz      short loc_1801ECCB2
0x1801eccd0  mov     edx, 0Dh
0x1801eccd5  lea     r8, WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids
0x1801eccdc  mov     rcx, [rcx+60h]
0x1801ecce0  call    WPP_SF_
0x1801ecce5  jmp     short loc_1801ECCB2
0x1801ecce7  lea     rax, aInvalidArgumen_2; "Invalid arguments"
0x1801eccee  mov     [rsp+0B0h+ppv], rax; unsigned __int16 *
0x1801eccf3  mov     r9d, 76h ; 'v'; unsigned int
0x1801eccf9  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ecd00  lea     rdx, aCwfddevicebrok_6; "CWfdDeviceBroker::RaisePairingConsentPr"...
0x1801ecd07  mov     ecx, 80070057h; int
0x1801ecd0c  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
```
