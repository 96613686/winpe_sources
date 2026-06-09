# CWfdDeviceBroker::AepAccessCheck(void)

- ea: `0x1801ebf94`
- end: `0x1801ec3a8`
- name: `?AepAccessCheck@CWfdDeviceBroker@@QEAAXXZ`
- size: `1044`
- prototype: `void __fastcall(CWfdDeviceBroker *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800b1ef8`
- `0x1801ec860`
- `0x1801ed0fc`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180069080`
- `0x1800716ec`
- `0x1800727d4`
- `0x180072800`
- `0x180073c18`
- `0x180075bac`
- `0x18007d770`
- `0x1800bd620`
- `0x180106340`
- `0x1801ebf94`
- `0x1801ec3b0`
- `0x1801ed2d8`
- `0x18021e25c`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801ec1e3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801ec1e3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801ec32a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801ec32a`

## string_xrefs

- `0x1801ec082`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x1801ec0b5`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ec193`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ec22d`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ec2cf`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ec2fd`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ec38f`: `onecoreuap\net\wlan\autocfg\wlansvcext\wfddevicebroker\src\wfddevicebroker.cpp`
- `0x1801ec181`: `CreateWithProcessId failed`
- `0x1801ec0a3`: `[WfdDeviceBroker] Failed to create RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess object`
- `0x1801ec0bc`: `CWfdDeviceBroker::AepAccessCheck`
- `0x1801ec19a`: `CWfdDeviceBroker::AepAccessCheck`
- `0x1801ec234`: `CWfdDeviceBroker::AepAccessCheck`
- `0x1801ec2d6`: `CWfdDeviceBroker::AepAccessCheck`
- `0x1801ec304`: `CWfdDeviceBroker::AepAccessCheck`
- `0x1801ec396`: `CWfdDeviceBroker::AepAccessCheck`
- `0x1801ec2eb`: `[WfdDeviceBroker] ICapabilityAccess::AccessCheck returned non 'Allowed' value`
- `0x1801ec2bd`: `AccessCheck failed`
- `0x1801ec21b`: `[WfdDeviceBroker] ICapabilityAccess::put_TargetObjectId failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall CWfdDeviceBroker::AepAccessCheck(CWfdDeviceBroker *this)
{
  __int64 v2; // r9
  __int64 v3; // r8
  PVOID *v4; // rcx
  unsigned int v5; // edx
  int v6; // eax
  __int64 v7; // r14
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD, _QWORD, int, __int64 **); // rsi
  int v9; // ebx
  unsigned int v10; // edi
  __int64 v11; // rax
  unsigned int v12; // eax
  int v13; // ebx
  __int64 *v14; // rbx
  __int64 v15; // rsi
  WCHAR *v16; // rdi
  unsigned __int64 v17; // rcx
  signed int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  unsigned int v21; // eax
  int v22; // ebx
  const struct std::nothrow_t *v23; // rdx
  _BYTE v24[4]; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-35h] BYREF
  int v26; // [rsp+48h] [rbp-31h] BYREF
  __int64 *v27; // [rsp+50h] [rbp-29h] BYREF
  __int64 v28; // [rsp+58h] [rbp-21h] BYREF
  void **v29; // [rsp+60h] [rbp-19h] BYREF
  PCWSTR sourceString; // [rsp+68h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v32; // [rsp+88h] [rbp+Fh]

  if ( !*(_QWORD *)this && !*((_QWORD *)this + 1)
    || (v2 = *((_QWORD *)this + 2)) == 0
    || (v3 = *((_QWORD *)this + 3)) == 0 )
  {
    WFDSvc::CWFDSvcException::Throw(
      -2147024809,
      "CWfdDeviceBroker::AepAccessCheck",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
      0xCCu,
      L"Invalid arguments");
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF__MAC_SDDl(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      14,
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
    v29 = &CAutoPtr<WFDSvc::ASP::CASPPublicationPrefix,DefaultArrayDeleter>::`vftable';
    sourceString = 0;
    CWfdDeviceBroker::AllocateAndEncodeAepIdString(*((_QWORD *)this + 2), &v29);
    CComInitialization::CComInitialization((CComInitialization *)v24, v5);
    v28 = 0;
    v27 = 0;
    v26 = 3;
    v32 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.CapabilityAccess.CapabilityAccess",
      0x33u,
      0x32u);
    v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
           v32,
           &v28);
    if ( v6 < 0 )
      WFDSvc::CWFDSvcException::Throw(
        v6,
        "CWfdDeviceBroker::AepAccessCheck",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0xE6u,
        L"[WfdDeviceBroker] Failed to create RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess object");
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, &WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids);
    }
    v7 = v28;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, int, __int64 **))(*(_QWORD *)v28 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v9 = *((_DWORD *)this + 8);
    v10 = *((_DWORD *)this + 9);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &c_szCapabilityWiFiDirect);
    v12 = v8(v7, 0, *(_QWORD *)(v11 + 24), v10, v9, &v27);
    v13 = v12;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, &WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids, v12);
    }
    if ( v13 < 0 )
      WFDSvc::CWFDSvcException::Throw(
        v13,
        "CWfdDeviceBroker::AepAccessCheck",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0xEFu,
        L"CreateWithProcessId failed");
    v14 = v27;
    v15 = *v27;
    v32 = 0;
    v16 = (WCHAR *)sourceString;
    v25 = 0;
    v17 = -1;
    do
      ++v17;
    while ( sourceString[v17] );
    v18 = ULongLongToULong(v17, &v25);
    if ( v18 < 0 )
    {
      RaiseException(v18, 1u, 0, 0);
      __debugbreak();
    }
    v19 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v25);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v16, v19, v25);
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v15 + 104))(v14, v32);
    if ( v20 < 0 )
      WFDSvc::CWFDSvcException::Throw(
        v20,
        "CWfdDeviceBroker::AepAccessCheck",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0xF5u,
        L"[WfdDeviceBroker] ICapabilityAccess::put_TargetObjectId failed");
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, &WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids);
    }
    v21 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v27 + 152))(v27, &v26);
    v22 = v21;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, &WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids, v21);
    }
    if ( v22 < 0 )
      WFDSvc::CWFDSvcException::Throw(
        v22,
        "CWfdDeviceBroker::AepAccessCheck",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0xFDu,
        L"AccessCheck failed");
    if ( v26 != 3 )
      WFDSvc::CWFDSvcException::Throw(
        -2147024891,
        "CWfdDeviceBroker::AepAccessCheck",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfddevicebroker\\src\\wfddevicebroker.cpp",
        0x103u,
        L"[WfdDeviceBroker] ICapabilityAccess::AccessCheck returned non 'Allowed' value");
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    CoUninitialize();
    operator delete(v16, v23);
  }
  else if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 105) >= 3u && (*((_BYTE *)v4 + 108) & 1) != 0 )
  {
    WPP_SF_(v4[12], 19, &WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids);
  }
}

```

## disassembly

```asm
0x1801ebf94  push    rbp
0x1801ebf96  push    rbx
0x1801ebf97  push    rsi
0x1801ebf98  push    rdi
0x1801ebf99  push    r12
0x1801ebf9b  push    r14
0x1801ebf9d  lea     rbp, [rsp-2Fh]
0x1801ebfa2  sub     rsp, 0A8h
0x1801ebfa9  mov     rax, cs:__security_cookie
0x1801ebfb0  xor     rax, rsp
0x1801ebfb3  mov     [rbp+57h+var_40], rax
0x1801ebfb7  mov     rdi, rcx
0x1801ebfba  xor     r12d, r12d
0x1801ebfbd  cmp     [rcx], r12
0x1801ebfc0  jnz     short loc_1801EBFCC
0x1801ebfc2  cmp     [rcx+8], r12
0x1801ebfc6  jz      loc_1801EC37D
0x1801ebfcc  mov     r9, [rcx+10h]
0x1801ebfd0  test    r9, r9
0x1801ebfd3  jz      loc_1801EC37D
0x1801ebfd9  mov     r8, [rcx+18h]
0x1801ebfdd  test    r8, r8
0x1801ebfe0  jz      loc_1801EC37D
0x1801ebfe6  lea     rbx, WPP_GLOBAL_Control
0x1801ebfed  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ebff4  cmp     rcx, rbx
0x1801ebff7  jz      short loc_1801EC035
0x1801ebff9  cmp     byte ptr [rcx+69h], 3
0x1801ebffd  jb      short loc_1801EC035
0x1801ebfff  test    byte ptr [rcx+6Ch], 1
0x1801ec003  jz      short loc_1801EC035
0x1801ec005  movzx   eax, byte ptr [rdi+28h]
0x1801ec009  mov     edx, 0Eh
0x1801ec00e  mov     [rsp+0D0h+var_98], eax
0x1801ec012  mov     eax, [rdi+24h]
0x1801ec015  mov     [rsp+0D0h+var_A0], eax
0x1801ec019  mov     eax, [rdi+20h]
0x1801ec01c  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1801ec020  mov     [rsp+0D0h+var_B0], r8
0x1801ec025  mov     rcx, [rcx+60h]
0x1801ec029  call    WPP_SF__MAC_SDDl
0x1801ec02e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ec035  cmp     [rdi+28h], r12b
0x1801ec039  jz      loc_1801EC355
0x1801ec03f  lea     rax, ??_7?$CAutoPtr@UCASPPublicationPrefix@ASP@WFDSvc@@UDefaultArrayDeleter@@@@6B@; const CAutoPtr<WFDSvc::ASP::CASPPublicationPrefix,DefaultArrayDeleter>::`vftable'
0x1801ec046  mov     [rbp+57h+var_70], rax
0x1801ec04a  mov     [rbp+57h+sourceString], r12
0x1801ec04e  lea     rdx, [rbp+57h+var_70]
0x1801ec052  mov     rcx, [rdi+10h]
0x1801ec056  call    ?AllocateAndEncodeAepIdString@CWfdDeviceBroker@@CAXPEAY05EAEAV?$CAutoPtr@GUDefaultArrayDeleter@@@@@Z; CWfdDeviceBroker::AllocateAndEncodeAepIdString(uchar (*)[6],CAutoPtr<ushort,DefaultArrayDeleter> &)
0x1801ec05b  lea     rcx, [rbp+57h+var_90]; this
0x1801ec05f  call    ??0CComInitialization@@QEAA@K@Z; CComInitialization::CComInitialization(ulong)
0x1801ec064  nop
0x1801ec065  mov     [rbp+57h+var_78], r12
0x1801ec069  mov     [rbp+57h+var_80], r12
0x1801ec06d  mov     [rbp+57h+var_88], 3
0x1801ec074  mov     [rbp+57h+var_48], r12
0x1801ec078  mov     r9d, 32h ; '2'; unsigned int
0x1801ec07e  lea     r8d, [r9+1]; unsigned int
0x1801ec082  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x1801ec089  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801ec08d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801ec092  lea     rdx, [rbp+57h+var_78]
0x1801ec096  mov     rcx, [rbp+57h+var_48]
0x1801ec09a  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x1801ec09f  test    eax, eax
0x1801ec0a1  jns     short loc_1801EC0CB
0x1801ec0a3  lea     rcx, aWfddevicebroke_0; "[WfdDeviceBroker] Failed to create Runt"...
0x1801ec0aa  mov     [rsp+0D0h+var_B0], rcx; unsigned __int16 *
0x1801ec0af  mov     r9d, 0E6h; unsigned int
0x1801ec0b5  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ec0bc  lea     rdx, aCwfddevicebrok_1; "CWfdDeviceBroker::AepAccessCheck"
0x1801ec0c3  mov     ecx, eax; int
0x1801ec0c5  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ec0cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ec0d2  cmp     rcx, rbx
0x1801ec0d5  jz      short loc_1801EC0F8
0x1801ec0d7  cmp     byte ptr [rcx+69h], 3
0x1801ec0db  jb      short loc_1801EC0F8
0x1801ec0dd  test    byte ptr [rcx+6Ch], 1
0x1801ec0e1  jz      short loc_1801EC0F8
0x1801ec0e3  mov     edx, 0Fh
0x1801ec0e8  lea     r8, WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids
0x1801ec0ef  mov     rcx, [rcx+60h]
0x1801ec0f3  call    WPP_SF_
0x1801ec0f8  mov     r14, [rbp+57h+var_78]
0x1801ec0fc  mov     rax, [r14]
0x1801ec0ff  mov     rsi, [rax+38h]
0x1801ec103  lea     rcx, [rbp+57h+var_80]
0x1801ec107  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801ec10c  mov     ebx, [rdi+20h]
0x1801ec10f  mov     edi, [rdi+24h]
0x1801ec112  lea     rdx, ?c_szCapabilityWiFiDirect@@3QEBGEB; ushort const * const c_szCapabilityWiFiDirect
0x1801ec119  lea     rcx, [rbp+57h+hstringHeader]
0x1801ec11d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ec122  nop
0x1801ec123  lea     rcx, [rbp+57h+var_80]
0x1801ec127  mov     [rsp+0D0h+var_A8], rcx
0x1801ec12c  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1801ec130  mov     r9d, edi
0x1801ec133  mov     r8, [rax+18h]
0x1801ec137  xor     edx, edx
0x1801ec139  mov     rcx, r14
0x1801ec13c  mov     rax, rsi
0x1801ec13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec144  mov     ebx, eax
0x1801ec146  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ec14d  lea     r14, WPP_GLOBAL_Control
0x1801ec154  cmp     rcx, r14
0x1801ec157  jz      short loc_1801EC17D
0x1801ec159  cmp     byte ptr [rcx+69h], 3
0x1801ec15d  jb      short loc_1801EC17D
0x1801ec15f  test    byte ptr [rcx+6Ch], 1
0x1801ec163  jz      short loc_1801EC17D
0x1801ec165  mov     edx, 10h
0x1801ec16a  mov     r9d, eax
0x1801ec16d  lea     r8, WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids
0x1801ec174  mov     rcx, [rcx+60h]
0x1801ec178  call    WPP_SF_d
0x1801ec17d  test    ebx, ebx
0x1801ec17f  jns     short loc_1801EC1A9
0x1801ec181  lea     rax, aCreatewithproc; "CreateWithProcessId failed"
0x1801ec188  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x1801ec18d  mov     r9d, 0EFh; unsigned int
0x1801ec193  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ec19a  lea     rdx, aCwfddevicebrok_1; "CWfdDeviceBroker::AepAccessCheck"
0x1801ec1a1  mov     ecx, ebx; int
0x1801ec1a3  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ec1a9  mov     rbx, [rbp+57h+var_80]
0x1801ec1ad  mov     rsi, [rbx]
0x1801ec1b0  mov     [rbp+57h+var_48], r12
0x1801ec1b4  mov     rdi, [rbp+57h+sourceString]
0x1801ec1b8  mov     [rbp+57h+var_8C], r12d
0x1801ec1bc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801ec1c0  inc     rcx; unsigned __int64
0x1801ec1c3  cmp     [rdi+rcx*2], r12w
0x1801ec1c8  jnz     short loc_1801EC1C0
0x1801ec1ca  lea     rdx, [rbp+57h+var_8C]; unsigned int *
0x1801ec1ce  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1801ec1d3  test    eax, eax
0x1801ec1d5  jns     short loc_1801EC1EA
0x1801ec1d7  xor     r9d, r9d; lpArguments
0x1801ec1da  xor     r8d, r8d; nNumberOfArguments
0x1801ec1dd  lea     edx, [r9+1]; dwExceptionFlags
0x1801ec1e1  mov     ecx, eax; dwExceptionCode
0x1801ec1e3  call    cs:__imp_RaiseException
0x1801ec1e9  int     3; Trap to Debugger
0x1801ec1ea  mov     ecx, [rbp+57h+var_8C]; unsigned int
0x1801ec1ed  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801ec1f2  mov     r9d, [rbp+57h+var_8C]; unsigned int
0x1801ec1f6  mov     r8d, eax; unsigned int
0x1801ec1f9  mov     rdx, rdi; sourceString
0x1801ec1fc  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1801ec200  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801ec205  nop
0x1801ec206  mov     rdx, [rbp+57h+var_48]
0x1801ec20a  mov     rcx, rbx
0x1801ec20d  mov     rax, [rsi+68h]
0x1801ec211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec216  nop
0x1801ec217  test    eax, eax
0x1801ec219  jns     short loc_1801EC243
0x1801ec21b  lea     rcx, aWfddevicebroke_1; "[WfdDeviceBroker] ICapabilityAccess::pu"...
0x1801ec222  mov     [rsp+0D0h+var_B0], rcx; unsigned __int16 *
0x1801ec227  mov     r9d, 0F5h; unsigned int
0x1801ec22d  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ec234  lea     rdx, aCwfddevicebrok_1; "CWfdDeviceBroker::AepAccessCheck"
0x1801ec23b  mov     ecx, eax; int
0x1801ec23d  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ec243  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ec24a  cmp     rcx, r14
0x1801ec24d  jz      short loc_1801EC270
0x1801ec24f  cmp     byte ptr [rcx+69h], 3
0x1801ec253  jb      short loc_1801EC270
0x1801ec255  test    byte ptr [rcx+6Ch], 1
0x1801ec259  jz      short loc_1801EC270
0x1801ec25b  mov     edx, 11h
0x1801ec260  lea     r8, WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids
0x1801ec267  mov     rcx, [rcx+60h]
0x1801ec26b  call    WPP_SF_
0x1801ec270  mov     rcx, [rbp+57h+var_80]
0x1801ec274  mov     rax, [rcx]
0x1801ec277  lea     rdx, [rbp+57h+var_88]
0x1801ec27b  mov     rax, [rax+98h]
0x1801ec282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ec287  mov     ebx, eax
0x1801ec289  mov     rcx, cs:WPP_GLOBAL_Control
0x1801ec290  cmp     rcx, r14
0x1801ec293  jz      short loc_1801EC2B9
0x1801ec295  cmp     byte ptr [rcx+69h], 3
0x1801ec299  jb      short loc_1801EC2B9
0x1801ec29b  test    byte ptr [rcx+6Ch], 1
0x1801ec29f  jz      short loc_1801EC2B9
0x1801ec2a1  mov     edx, 12h
0x1801ec2a6  mov     r9d, eax
0x1801ec2a9  lea     r8, WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids
0x1801ec2b0  mov     rcx, [rcx+60h]
0x1801ec2b4  call    WPP_SF_d
0x1801ec2b9  test    ebx, ebx
0x1801ec2bb  jns     short loc_1801EC2E5
0x1801ec2bd  lea     rax, aAccesscheckFai; "AccessCheck failed"
0x1801ec2c4  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x1801ec2c9  mov     r9d, 0FDh; unsigned int
0x1801ec2cf  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ec2d6  lea     rdx, aCwfddevicebrok_1; "CWfdDeviceBroker::AepAccessCheck"
0x1801ec2dd  mov     ecx, ebx; int
0x1801ec2df  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ec2e5  cmp     [rbp+57h+var_88], 3
0x1801ec2e9  jz      short loc_1801EC316
0x1801ec2eb  lea     rax, aWfddevicebroke_7; "[WfdDeviceBroker] ICapabilityAccess::Ac"...
0x1801ec2f2  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x1801ec2f7  mov     r9d, 103h; unsigned int
0x1801ec2fd  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ec304  lea     rdx, aCwfddevicebrok_1; "CWfdDeviceBroker::AepAccessCheck"
0x1801ec30b  mov     ecx, 80070005h; int
0x1801ec310  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x1801ec316  lea     rcx, [rbp+57h+var_80]
0x1801ec31a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801ec31f  nop
0x1801ec320  lea     rcx, [rbp+57h+var_78]
0x1801ec324  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801ec329  nop
0x1801ec32a  call    cs:__imp_CoUninitialize
0x1801ec330  nop
0x1801ec331  mov     rcx, rdi; void *
0x1801ec334  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801ec339  mov     rcx, [rbp+57h+var_40]
0x1801ec33d  xor     rcx, rsp; StackCookie
0x1801ec340  call    __security_check_cookie
0x1801ec345  add     rsp, 0A8h
0x1801ec34c  pop     r14
0x1801ec34e  pop     r12
0x1801ec350  pop     rdi
0x1801ec351  pop     rsi
0x1801ec352  pop     rbx
0x1801ec353  pop     rbp
0x1801ec354  retn
0x1801ec355  cmp     rcx, rbx
0x1801ec358  jz      short loc_1801EC339
0x1801ec35a  cmp     byte ptr [rcx+69h], 3
0x1801ec35e  jb      short loc_1801EC339
0x1801ec360  test    byte ptr [rcx+6Ch], 1
0x1801ec364  jz      short loc_1801EC339
0x1801ec366  mov     edx, 13h
0x1801ec36b  lea     r8, WPP_c78a48f1e3aa3681843a5f193f9486e3_Traceguids
0x1801ec372  mov     rcx, [rcx+60h]
0x1801ec376  call    WPP_SF_
0x1801ec37b  jmp     short loc_1801EC339
0x1801ec37d  lea     rax, aInvalidArgumen_2; "Invalid arguments"
0x1801ec384  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x1801ec389  mov     r9d, 0CCh; unsigned int
0x1801ec38f  lea     r8, aOnecoreuapNetW_50; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x1801ec396  lea     rdx, aCwfddevicebrok_1; "CWfdDeviceBroker::AepAccessCheck"
0x1801ec39d  mov     ecx, 80070057h; int
0x1801ec3a2  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
```
