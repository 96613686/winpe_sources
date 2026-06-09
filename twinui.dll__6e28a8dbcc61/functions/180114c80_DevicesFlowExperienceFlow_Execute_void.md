# DevicesFlowExperienceFlow::Execute(void)

- ea: `0x180114c80`
- end: `0x18011506b`
- name: `?Execute@DevicesFlowExperienceFlow@@UEAAJXZ`
- size: `1003`
- prototype: `__int64 __fastcall(DevicesFlowExperienceFlow *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x180011884`
- `0x180037e18`
- `0x18003c5e4`
- `0x18003c898`
- `0x180052980`
- `0x1800542a8`
- `0x180114c80`
- `0x18013d330`
- `0x1802a8208`
- `0x1802cfd18`
- `0x1802cff08`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180114eff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180114f33`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180114eff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180114f33`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x180114f94`
- `combase!__imp_CoAllowSetForegroundWindow` at `0x180114f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114ed0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114fe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114e95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114ed0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180114fe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114f19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180114f19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180114d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180114db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180115005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180114d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180114db8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180115005`

## string_xrefs

- `0x180114dd2`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall DevicesFlowExperienceFlow::Execute(DevicesFlowExperienceFlow *this)
{
  _QWORD *v2; // r14
  int v3; // edi
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(__int64, _QWORD, LPVOID *); // rbx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, LPVOID *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v21; // rbx
  const WCHAR *v22; // rax
  DevicesFlowExperienceFlow *v23; // rcx
  int ExperienceManager; // eax
  __int64 v25; // rdx
  HRESULT v26; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-49h]
  HSTRING string; // [rsp+30h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-31h] BYREF
  __int64 v31; // [rsp+40h] [rbp-29h] BYREF
  __int64 v32; // [rsp+48h] [rbp-21h] BYREF
  IUnknown *pUnk; // [rsp+50h] [rbp-19h] BYREF
  LPVOID v34; // [rsp+58h] [rbp-11h] BYREF
  __int64 v35; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  __int64 v37; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v35 = 0;
  v2 = (_QWORD *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&v35);
  v3 = -2147024809;
  *v2 = 0;
  v4 = *((_QWORD *)this + 15);
  if ( !v4 )
    goto LABEL_38;
  v34 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v4 + 64LL);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v34);
  v3 = v5(v4, 0, &v34);
  if ( v3 >= 0 )
    v3 = Microsoft::WRL::ComPtr<IShellItem>::CopyTo(&v34, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, v2);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v34);
  if ( v3 < 0 )
  {
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
    v9 = v3;
LABEL_39:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v35);
    return v9;
  }
  v6 = v35;
  pv = 0;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v35 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v8 = v7(v6, 2147909632LL, &pv);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    goto LABEL_7;
  }
  v34 = pv;
  if ( !IsMsDevicesFlowUri((wchar_t *)pv) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    if ( pv )
      CoTaskMemFree(pv);
    v9 = -2147024809;
    goto LABEL_39;
  }
  v32 = 0;
  v37 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
  v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
          v37,
          &v32);
  v9 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)(unsigned int)v10,
      bIgnoreCase);
LABEL_15:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
LABEL_7:
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_39;
  }
  v11 = v32;
  v31 = 0;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v34);
  v14 = v12(v11, *(_QWORD *)(v13 + 24), &v31);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
LABEL_18:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
    goto LABEL_15;
  }
  v15 = v31;
  string = 0;
  v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31 + 104LL);
  WindowsDeleteString(0);
  string = 0;
  v17 = v16(v15, &string);
  v9 = v17;
  if ( v17 < 0 )
  {
    v18 = (unsigned int)v17;
    v19 = 37;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)v18,
      bIgnoreCase);
LABEL_22:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_18;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"devicediscovery", -1, 0) == 2 )
  {
    v21 = L"Windows.Internal.ShellExperience.DeviceDiscovery";
  }
  else
  {
    v22 = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(v22, -1, L"projection", -1, 0) != 2 )
    {
      v9 = -2147418113;
      v19 = 50;
      v18 = 2147549183LL;
      goto LABEL_21;
    }
    v21 = L"Windows.Internal.ShellExperience.DisplayTopology";
  }
  pUnk = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pUnk);
  ExperienceManager = DevicesFlowExperienceFlow::GetExperienceManager(
                        v23,
                        v21,
                        (struct Windows::Internal::Shell::Experience::IDeviceDiscoveryExperienceManager **)&pUnk);
  v9 = ExperienceManager;
  if ( ExperienceManager < 0 )
  {
    v25 = 54;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)(unsigned int)ExperienceManager,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pUnk);
    goto LABEL_22;
  }
  v26 = CoAllowSetForegroundWindow(pUnk, 0);
  if ( v26 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"shell\\twinui\\devicesflowexperienceflow\\lib\\devicesflowexperienceflow.cpp",
      (const char *)(unsigned int)v26,
      bIgnoreCase);
  ExperienceManager = ((__int64 (__fastcall *)(IUnknown *))pUnk->lpVtbl[2].QueryInterface)(pUnk);
  v9 = ExperienceManager;
  if ( ExperienceManager < 0 )
  {
    v25 = 56;
    goto LABEL_29;
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pUnk);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
  if ( pv )
    CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v35);
  return 0;
}

```

## disassembly

```asm
0x180114c80  push    rbp
0x180114c82  push    rbx
0x180114c83  push    rsi
0x180114c84  push    rdi
0x180114c85  push    r14
0x180114c87  push    r15
0x180114c89  lea     rbp, [rsp-2Fh]
0x180114c8e  sub     rsp, 98h
0x180114c95  mov     rax, cs:__security_cookie
0x180114c9c  xor     rax, rsp
0x180114c9f  mov     [rbp+57h+var_38], rax
0x180114ca3  mov     rbx, rcx
0x180114ca6  xor     r15d, r15d
0x180114ca9  lea     rcx, [rbp+57h+var_60]
0x180114cad  mov     [rbp+57h+var_60], r15
0x180114cb1  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x180114cb6  mov     r14, rax
0x180114cb9  mov     edi, 80070057h
0x180114cbe  mov     [rax], r15
0x180114cc1  mov     rsi, [rbx+78h]
0x180114cc5  test    rsi, rsi
0x180114cc8  jz      loc_18011502A
0x180114cce  mov     [rbp+57h+var_68], r15
0x180114cd2  lea     rcx, [rbp+57h+var_68]
0x180114cd6  mov     rdx, [rsi]
0x180114cd9  mov     rbx, [rdx+40h]
0x180114cdd  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114ce2  lea     r8, [rbp+57h+var_68]
0x180114ce6  xor     edx, edx
0x180114ce8  mov     rcx, rsi
0x180114ceb  mov     rax, rbx
0x180114cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114cf3  mov     edi, eax
0x180114cf5  test    eax, eax
0x180114cf7  js      short loc_180114D0E
0x180114cf9  mov     r8, r14
0x180114cfc  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180114d03  lea     rcx, [rbp+57h+var_68]
0x180114d07  call    ?CopyTo@?$ComPtr@UIShellItem@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IShellItem>::CopyTo(_GUID const &,void * *)
0x180114d0c  mov     edi, eax
0x180114d0e  lea     rcx, [rbp+57h+var_68]
0x180114d12  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114d17  test    edi, edi
0x180114d19  js      loc_18011502A
0x180114d1f  mov     rdi, [rbp+57h+var_60]
0x180114d23  lea     rcx, [rbp+57h+pv]
0x180114d27  mov     [rbp+57h+pv], r15
0x180114d2b  xor     edx, edx
0x180114d2d  mov     rax, [rdi]
0x180114d30  mov     rbx, [rax+28h]
0x180114d34  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180114d39  lea     r8, [rbp+57h+pv]
0x180114d3d  mov     edx, 80068000h
0x180114d42  mov     rcx, rdi
0x180114d45  mov     rax, rbx
0x180114d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114d4d  mov     ebx, eax
0x180114d4f  test    eax, eax
0x180114d51  jns     short loc_180114D83
0x180114d53  mov     rcx, [rbp+5Fh]; this
0x180114d57  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x180114d5e  mov     r9d, eax; char *
0x180114d61  mov     edx, 1Ah; void *
0x180114d66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114d6b  mov     rcx, [rbp+57h+pv]; pv
0x180114d6f  test    rcx, rcx
0x180114d72  jz      loc_180115044
0x180114d78  call    cs:__imp_CoTaskMemFree
0x180114d7e  jmp     loc_180115044
0x180114d83  mov     rcx, [rbp+57h+pv]; String1
0x180114d87  mov     [rbp+57h+var_68], rcx
0x180114d8b  call    ?IsMsDevicesFlowUri@@YA_NPEBG@Z; IsMsDevicesFlowUri(ushort const *)
0x180114d90  test    al, al
0x180114d92  jnz     short loc_180114DC8
0x180114d94  mov     rcx, [rbp+5Fh]; this
0x180114d98  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x180114d9f  mov     r9d, 80070057h; char *
0x180114da5  mov     edx, 1Ch; void *
0x180114daa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114daf  mov     rcx, [rbp+57h+pv]; pv
0x180114db3  test    rcx, rcx
0x180114db6  jz      short loc_180114DBE
0x180114db8  call    cs:__imp_CoTaskMemFree
0x180114dbe  mov     ebx, 80070057h
0x180114dc3  jmp     loc_180115044
0x180114dc8  mov     r9d, 16h; unsigned int
0x180114dce  mov     [rbp+57h+var_78], r15
0x180114dd2  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x180114dd9  mov     [rbp+57h+var_40], r15
0x180114ddd  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180114de1  lea     r8d, [r9+1]; unsigned int
0x180114de5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180114dea  mov     rcx, [rbp+57h+var_40]
0x180114dee  lea     rdx, [rbp+57h+var_78]
0x180114df2  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x180114df7  mov     ebx, eax
0x180114df9  test    eax, eax
0x180114dfb  jns     short loc_180114E23
0x180114dfd  mov     rcx, [rbp+5Fh]; this
0x180114e01  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x180114e08  mov     r9d, eax; char *
0x180114e0b  mov     edx, 1Fh; void *
0x180114e10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114e15  lea     rcx, [rbp+57h+var_78]
0x180114e19  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114e1e  jmp     loc_180114D6B
0x180114e23  mov     rdi, [rbp+57h+var_78]
0x180114e27  lea     rcx, [rbp+57h+var_80]
0x180114e2b  mov     [rbp+57h+var_80], r15
0x180114e2f  mov     rax, [rdi]
0x180114e32  mov     rbx, [rax+30h]
0x180114e36  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114e3b  lea     rdx, [rbp+57h+var_68]
0x180114e3f  lea     rcx, [rbp+57h+hstringHeader]
0x180114e43  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180114e48  lea     r8, [rbp+57h+var_80]
0x180114e4c  mov     rcx, rdi
0x180114e4f  mov     rdx, [rax+18h]
0x180114e53  mov     rax, rbx
0x180114e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114e5b  mov     ebx, eax
0x180114e5d  test    eax, eax
0x180114e5f  jns     short loc_180114E84
0x180114e61  mov     rcx, [rbp+5Fh]; this
0x180114e65  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x180114e6c  mov     r9d, eax; char *
0x180114e6f  mov     edx, 22h ; '"'; void *
0x180114e74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114e79  lea     rcx, [rbp+57h+var_80]
0x180114e7d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114e82  jmp     short loc_180114E15
0x180114e84  mov     rdi, [rbp+57h+var_80]
0x180114e88  xor     ecx, ecx; string
0x180114e8a  mov     [rbp+57h+string], r15
0x180114e8e  mov     rax, [rdi]
0x180114e91  mov     rbx, [rax+68h]
0x180114e95  call    cs:__imp_WindowsDeleteString
0x180114e9b  lea     rdx, [rbp+57h+string]
0x180114e9f  mov     [rbp+57h+string], r15
0x180114ea3  mov     rcx, rdi
0x180114ea6  mov     rax, rbx
0x180114ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114eae  mov     ebx, eax
0x180114eb0  test    eax, eax
0x180114eb2  jns     short loc_180114EDC
0x180114eb4  mov     r9d, eax; char *
0x180114eb7  mov     edx, 25h ; '%'; void *
0x180114ebc  mov     rcx, [rbp+5Fh]; this
0x180114ec0  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x180114ec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114ecc  mov     rcx, [rbp+57h+string]; string
0x180114ed0  call    cs:__imp_WindowsDeleteString
0x180114ed6  mov     [rbp+57h+string], r15
0x180114eda  jmp     short loc_180114E79
0x180114edc  mov     rcx, [rbp+57h+string]; string
0x180114ee0  xor     edx, edx; length
0x180114ee2  call    cs:__imp_WindowsGetStringRawBuffer
0x180114ee8  or      ebx, 0FFFFFFFFh
0x180114eeb  mov     [rsp+0C0h+bIgnoreCase], r15d; bIgnoreCase
0x180114ef0  mov     r9d, ebx; cchCount2
0x180114ef3  lea     r8, aDevicediscover; "devicediscovery"
0x180114efa  mov     edx, ebx; cchCount1
0x180114efc  mov     rcx, rax; lpString1
0x180114eff  call    cs:__imp_CompareStringOrdinal
0x180114f05  cmp     eax, 2
0x180114f08  jnz     short loc_180114F13
0x180114f0a  lea     rbx, aWindowsInterna_3; "Windows.Internal.ShellExperience.Device"...
0x180114f11  jmp     short loc_180114F49
0x180114f13  mov     rcx, [rbp+57h+string]; string
0x180114f17  xor     edx, edx; length
0x180114f19  call    cs:__imp_WindowsGetStringRawBuffer
0x180114f1f  mov     r9d, ebx; cchCount2
0x180114f22  mov     [rsp+0C0h+bIgnoreCase], r15d; int
0x180114f27  mov     rcx, rax; lpString1
0x180114f2a  lea     r8, aProjection; "projection"
0x180114f31  mov     edx, ebx; cchCount1
0x180114f33  call    cs:__imp_CompareStringOrdinal
0x180114f39  cmp     eax, 2
0x180114f3c  jnz     loc_180115018
0x180114f42  lea     rbx, aWindowsInterna_38; "Windows.Internal.ShellExperience.Displa"...
0x180114f49  lea     rcx, [rbp+57h+pUnk]
0x180114f4d  mov     [rbp+57h+pUnk], r15
0x180114f51  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114f56  lea     r8, [rbp+57h+pUnk]; struct Windows::Internal::Shell::Experience::IDeviceDiscoveryExperienceManager **
0x180114f5a  mov     rdx, rbx; unsigned __int16 *
0x180114f5d  call    ?GetExperienceManager@DevicesFlowExperienceFlow@@AEAAJPEBGPEAPEAUIDeviceDiscoveryExperienceManager@Experience@Shell@Internal@Windows@@@Z; DevicesFlowExperienceFlow::GetExperienceManager(ushort const *,Windows::Internal::Shell::Experience::IDeviceDiscoveryExperienceManager * *)
0x180114f62  mov     ebx, eax
0x180114f64  test    eax, eax
0x180114f66  jns     short loc_180114F8E
0x180114f68  mov     edx, 36h ; '6'; void *
0x180114f6d  mov     rcx, [rbp+5Fh]; this
0x180114f71  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x180114f78  mov     r9d, eax; char *
0x180114f7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114f80  lea     rcx, [rbp+57h+pUnk]
0x180114f84  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114f89  jmp     loc_180114ECC
0x180114f8e  mov     rcx, [rbp+57h+pUnk]; pUnk
0x180114f92  xor     edx, edx; lpvReserved
0x180114f94  call    cs:__imp_CoAllowSetForegroundWindow
0x180114f9a  test    eax, eax
0x180114f9c  jns     short loc_180114FB6
0x180114f9e  mov     rcx, [rbp+5Fh]; this
0x180114fa2  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x180114fa9  mov     r9d, eax; char *
0x180114fac  mov     edx, 37h ; '7'; void *
0x180114fb1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180114fb6  mov     rcx, [rbp+57h+pUnk]
0x180114fba  mov     rax, [rcx]
0x180114fbd  mov     rax, [rax+30h]
0x180114fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114fc6  mov     ebx, eax
0x180114fc8  test    eax, eax
0x180114fca  jns     short loc_180114FD3
0x180114fcc  mov     edx, 38h ; '8'
0x180114fd1  jmp     short loc_180114F6D
0x180114fd3  lea     rcx, [rbp+57h+pUnk]
0x180114fd7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114fdc  mov     rcx, [rbp+57h+string]; string
0x180114fe0  call    cs:__imp_WindowsDeleteString
0x180114fe6  lea     rcx, [rbp+57h+var_80]
0x180114fea  mov     [rbp+57h+string], r15
0x180114fee  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114ff3  lea     rcx, [rbp+57h+var_78]
0x180114ff7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180114ffc  mov     rcx, [rbp+57h+pv]; pv
0x180115000  test    rcx, rcx
0x180115003  jz      short loc_18011500B
0x180115005  call    cs:__imp_CoTaskMemFree
0x18011500b  lea     rcx, [rbp+57h+var_60]
0x18011500f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180115014  xor     eax, eax
0x180115016  jmp     short loc_18011504F
0x180115018  mov     ebx, 8000FFFFh
0x18011501d  mov     edx, 32h ; '2'
0x180115022  mov     r9d, ebx
0x180115025  jmp     loc_180114EBC
0x18011502a  mov     rcx, [rbp+5Fh]; this
0x18011502e  lea     r8, aShellTwinuiDev; "shell\\twinui\\devicesflowexperienceflo"...
0x180115035  mov     r9d, edi; char *
0x180115038  mov     edx, 17h; void *
0x18011503d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115042  mov     ebx, edi
0x180115044  lea     rcx, [rbp+57h+var_60]
0x180115048  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011504d  mov     eax, ebx
0x18011504f  mov     rcx, [rbp+57h+var_38]
0x180115053  xor     rcx, rsp; StackCookie
0x180115056  call    __security_check_cookie
0x18011505b  add     rsp, 98h
0x180115062  pop     r15
0x180115064  pop     r14
0x180115066  pop     rdi
0x180115067  pop     rsi
0x180115068  pop     rbx
0x180115069  pop     rbp
0x18011506a  retn
```
