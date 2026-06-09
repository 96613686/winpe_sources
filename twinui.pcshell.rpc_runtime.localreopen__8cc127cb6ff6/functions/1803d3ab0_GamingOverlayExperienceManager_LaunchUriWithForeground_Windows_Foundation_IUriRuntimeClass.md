# GamingOverlayExperienceManager::LaunchUriWithForeground(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x1803d3ab0`
- end: `0x1803d3f68`
- name: `?LaunchUriWithForeground@GamingOverlayExperienceManager@@UEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `1208`
- prototype: `__int64 __fastcall(GamingOverlayExperienceManager *__hidden this, struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x1801ee548`
- `0x1802a2e34`
- `0x1802bbaf8`
- `0x180356360`
- `0x180356edc`
- `0x180364a24`
- `0x1803d3ab0`
- `0x1806ad154`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3b86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3c37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3d22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3d96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3e20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3e50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3e9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3f20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3f32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3b86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3c37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3d22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3d96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3def`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3e20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3e35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3e50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3e9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3f20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803d3f32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803d3b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803d3edf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803d3b9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803d3edf`
- `SHELL32!ShellExecuteExW` at `0x1803d3ef7`
- `SHELL32!ShellExecuteExW` at `0x1803d3ef7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall GamingOverlayExperienceManager::LaunchUriWithForeground(
        GamingOverlayExperienceManager *this,
        struct Windows::Foundation::IUriRuntimeClass *a2)
{
  int v4; // eax
  __int64 (__fastcall *v5)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  const wchar_t *StringRawBuffer; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, SID *, GUID *, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, struct Windows::Foundation::IUriRuntimeClass *, __int64 *); // rbx
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // ebx
  __int64 (__fastcall *v22)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int v23; // eax
  unsigned int v24; // ebx
  const char *v25; // r9
  unsigned int LastError; // ebx
  int v27; // [rsp+20h] [rbp-C8h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v29[8]; // [rsp+A0h] [rbp-48h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-40h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-38h] BYREF
  __int64 v32; // [rsp+B8h] [rbp-30h] BYREF
  HSTRING v33; // [rsp+C0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 37) + 24LL))(*((_QWORD *)this + 37));
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x630,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)(unsigned int)v4,
      v27);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_50902630>::GetImpl'::`2'::impl) )
  {
    string = 0;
    v5 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 136LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = v5(a2, &string);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x636,
        (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
        (const char *)(unsigned int)v6,
        v27);
      WindowsDeleteString(string);
      return v7;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !wcscmp_0(StringRawBuffer, L"windows.gaming") )
    {
      v32 = 0;
      v10 = *((_QWORD *)this + 39);
      v11 = *(__int64 (__fastcall **)(__int64, SID *, GUID *, __int64 *))(*(_QWORD *)v10 + 24LL);
      Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(&v32);
      v12 = v11(v10, &SID_GamingPostureController, &GUID_b525603c_e3b6_51fa_bdfc_1ac36cf03dc8, &v32);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v31 = 0;
        v14 = v32;
        v15 = *(__int64 (__fastcall **)(__int64, struct Windows::Foundation::IUriRuntimeClass *, __int64 *))(*(_QWORD *)v32 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        v16 = v15(v14, a2, &v31);
        v17 = v16;
        if ( v16 >= 0 )
        {
          v18 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(v31);
          v19 = v18;
          if ( v18 >= 0 )
          {
            v29[0] = 0;
            v20 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v31 + 64LL))(v31, v29);
            v21 = v20;
            if ( v20 >= 0 )
            {
              if ( v29[0] )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
                Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(&v32);
                WindowsDeleteString(string);
                return 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x642,
                  (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
                  (const char *)0x80004005LL,
                  v27);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
                Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(&v32);
                WindowsDeleteString(string);
                return 2147500037LL;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x641,
                (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
                (const char *)(unsigned int)v20,
                v27);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
              Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(&v32);
              WindowsDeleteString(string);
              return v21;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x63E,
              (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
              (const char *)(unsigned int)v18,
              v27);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(&v32);
            WindowsDeleteString(string);
            return v19;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x63D,
            (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
            (const char *)(unsigned int)v16,
            v27);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
          Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(&v32);
          WindowsDeleteString(string);
          return v17;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x63A,
          (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
          (const char *)(unsigned int)v12,
          v27);
        Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(&v32);
        WindowsDeleteString(string);
        return v13;
      }
    }
    WindowsDeleteString(string);
  }
  v33 = 0;
  v22 = *(__int64 (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  v33 = 0;
  v23 = v22(a2, &v33);
  v24 = v23;
  if ( v23 >= 0 )
  {
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    pExecInfo.cbSize = 112;
    pExecInfo.fMask = 67109888;
    pExecInfo.lpVerb = L"open";
    pExecInfo.lpFile = WindowsGetStringRawBuffer(v33, 0);
    pExecInfo.nShow = 1;
    if ( ShellExecuteExW(&pExecInfo) )
    {
      WindowsDeleteString(v33);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x655,
                    (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
                    v25);
      WindowsDeleteString(v33);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64A,
      (unsigned int)"pcshell\\twinui\\gamingoverlayexperiencemanager\\lib\\GamingOverlayExperienceManager.cpp",
      (const char *)(unsigned int)v23,
      v27);
    WindowsDeleteString(v33);
    return v24;
  }
}

```

## disassembly

```asm
0x1803d3ab0  mov     [rsp+arg_10], rbx
0x1803d3ab5  push    rsi
0x1803d3ab6  push    rdi
0x1803d3ab7  push    r14
0x1803d3ab9  sub     rsp, 0D0h
0x1803d3ac0  mov     rax, cs:__security_cookie
0x1803d3ac7  xor     rax, rsp
0x1803d3aca  mov     [rsp+0E8h+var_20], rax
0x1803d3ad2  mov     r14, rdx
0x1803d3ad5  mov     rdi, rcx
0x1803d3ad8  mov     rcx, [rcx+128h]
0x1803d3adf  mov     rax, [rcx]
0x1803d3ae2  mov     rax, [rax+18h]
0x1803d3ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d3aeb  mov     rcx, [rsp+0E8h]; this
0x1803d3af3  lea     rsi, aPcshellTwinuiG_2; "pcshell\\twinui\\gamingoverlayexperienc"...
0x1803d3afa  test    eax, eax
0x1803d3afc  jns     short loc_1803D3B0E
0x1803d3afe  mov     r9d, eax; char *
0x1803d3b01  mov     r8, rsi; unsigned int
0x1803d3b04  mov     edx, 630h; void *
0x1803d3b09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803d3b0e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_50902630@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_50902630@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630> `wil::Feature<__WilFeatureTraits_Feature_50902630>::GetImpl(void)'::`2'::impl
0x1803d3b15  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_50902630@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50902630>::__private_IsEnabled(void)
0x1803d3b1a  test    al, al
0x1803d3b1c  jz      loc_1803D3E3B
0x1803d3b22  mov     [rsp+0E8h+string], 0
0x1803d3b2e  mov     rax, [r14]
0x1803d3b31  mov     rbx, [rax+88h]
0x1803d3b38  xor     ecx, ecx; string
0x1803d3b3a  call    cs:__imp_WindowsDeleteString
0x1803d3b40  mov     [rsp+0E8h+string], 0
0x1803d3b4c  lea     rdx, [rsp+0E8h+string]
0x1803d3b54  mov     rcx, r14
0x1803d3b57  mov     rax, rbx
0x1803d3b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d3b5f  mov     ebx, eax
0x1803d3b61  test    eax, eax
0x1803d3b63  jns     short loc_1803D3B93
0x1803d3b65  mov     rcx, [rsp+0E8h]; this
0x1803d3b6d  mov     r9d, eax; char *
0x1803d3b70  mov     r8, rsi; unsigned int
0x1803d3b73  mov     edx, 636h; void *
0x1803d3b78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d3b7d  nop
0x1803d3b7e  mov     rcx, [rsp+0E8h+string]; string
0x1803d3b86  call    cs:__imp_WindowsDeleteString
0x1803d3b8c  mov     eax, ebx
0x1803d3b8e  jmp     loc_1803D3F43
0x1803d3b93  xor     edx, edx; length
0x1803d3b95  mov     rcx, [rsp+0E8h+string]; string
0x1803d3b9d  call    cs:__imp_WindowsGetStringRawBuffer
0x1803d3ba3  lea     rdx, aWindowsGaming; "windows.gaming"
0x1803d3baa  mov     rcx, rax; String1
0x1803d3bad  call    wcscmp_0
0x1803d3bb2  test    eax, eax
0x1803d3bb4  jnz     loc_1803D3E2D
0x1803d3bba  mov     [rsp+0E8h+var_30], 0
0x1803d3bc6  mov     rdi, [rdi+138h]
0x1803d3bcd  mov     rax, [rdi]
0x1803d3bd0  mov     rbx, [rax+18h]
0x1803d3bd4  lea     rcx, [rsp+0E8h+var_30]
0x1803d3bdc  call    ?InternalRelease@?$ComPtr@UIUpdateViewValueSet@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(void)
0x1803d3be1  lea     r9, [rsp+0E8h+var_30]
0x1803d3be9  lea     r8, _GUID_b525603c_e3b6_51fa_bdfc_1ac36cf03dc8
0x1803d3bf0  lea     rdx, SID_GamingPostureController
0x1803d3bf7  mov     rcx, rdi
0x1803d3bfa  mov     rax, rbx
0x1803d3bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d3c02  mov     ebx, eax
0x1803d3c04  test    eax, eax
0x1803d3c06  jns     short loc_1803D3C44
0x1803d3c08  mov     rcx, [rsp+0E8h]; this
0x1803d3c10  mov     r9d, eax; char *
0x1803d3c13  mov     r8, rsi; unsigned int
0x1803d3c16  mov     edx, 63Ah; void *
0x1803d3c1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d3c20  nop
0x1803d3c21  lea     rcx, [rsp+0E8h+var_30]
0x1803d3c29  call    ?InternalRelease@?$ComPtr@UIUpdateViewValueSet@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(void)
0x1803d3c2e  nop
0x1803d3c2f  mov     rcx, [rsp+0E8h+string]; string
0x1803d3c37  call    cs:__imp_WindowsDeleteString
0x1803d3c3d  mov     eax, ebx
0x1803d3c3f  jmp     loc_1803D3F43
0x1803d3c44  mov     [rsp+0E8h+var_38], 0
0x1803d3c50  mov     rdi, [rsp+0E8h+var_30]
0x1803d3c58  mov     rax, [rdi]
0x1803d3c5b  mov     rbx, [rax+40h]
0x1803d3c5f  lea     rcx, [rsp+0E8h+var_38]
0x1803d3c67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d3c6c  lea     r8, [rsp+0E8h+var_38]
0x1803d3c74  mov     rdx, r14
0x1803d3c77  mov     rcx, rdi
0x1803d3c7a  mov     rax, rbx
0x1803d3c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d3c82  mov     ebx, eax
0x1803d3c84  test    eax, eax
0x1803d3c86  jns     short loc_1803D3CD2
0x1803d3c88  mov     rcx, [rsp+0E8h]; this
0x1803d3c90  mov     r9d, eax; char *
0x1803d3c93  mov     r8, rsi; unsigned int
0x1803d3c96  mov     edx, 63Dh; void *
0x1803d3c9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d3ca0  nop
0x1803d3ca1  lea     rcx, [rsp+0E8h+var_38]
0x1803d3ca9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d3cae  nop
0x1803d3caf  lea     rcx, [rsp+0E8h+var_30]
0x1803d3cb7  call    ?InternalRelease@?$ComPtr@UIUpdateViewValueSet@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(void)
0x1803d3cbc  nop
0x1803d3cbd  mov     rcx, [rsp+0E8h+string]; string
0x1803d3cc5  call    cs:__imp_WindowsDeleteString
0x1803d3ccb  mov     eax, ebx
0x1803d3ccd  jmp     loc_1803D3F43
0x1803d3cd2  mov     rcx, [rsp+0E8h+var_38]
0x1803d3cda  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x1803d3cdf  mov     ebx, eax
0x1803d3ce1  test    eax, eax
0x1803d3ce3  jns     short loc_1803D3D2F
0x1803d3ce5  mov     rcx, [rsp+0E8h]; this
0x1803d3ced  mov     r9d, eax; char *
0x1803d3cf0  mov     r8, rsi; unsigned int
0x1803d3cf3  mov     edx, 63Eh; void *
0x1803d3cf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d3cfd  nop
0x1803d3cfe  lea     rcx, [rsp+0E8h+var_38]
0x1803d3d06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d3d0b  nop
0x1803d3d0c  lea     rcx, [rsp+0E8h+var_30]
0x1803d3d14  call    ?InternalRelease@?$ComPtr@UIUpdateViewValueSet@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(void)
0x1803d3d19  nop
0x1803d3d1a  mov     rcx, [rsp+0E8h+string]; string
0x1803d3d22  call    cs:__imp_WindowsDeleteString
0x1803d3d28  mov     eax, ebx
0x1803d3d2a  jmp     loc_1803D3F43
0x1803d3d2f  mov     [rsp+0E8h+var_48], 0
0x1803d3d37  mov     rcx, [rsp+0E8h+var_38]
0x1803d3d3f  mov     rax, [rcx]
0x1803d3d42  lea     rdx, [rsp+0E8h+var_48]
0x1803d3d4a  mov     rax, [rax+40h]
0x1803d3d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d3d53  mov     ebx, eax
0x1803d3d55  test    eax, eax
0x1803d3d57  jns     short loc_1803D3DA3
0x1803d3d59  mov     rcx, [rsp+0E8h]; this
0x1803d3d61  mov     r9d, eax; char *
0x1803d3d64  mov     r8, rsi; unsigned int
0x1803d3d67  mov     edx, 641h; void *
0x1803d3d6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d3d71  nop
0x1803d3d72  lea     rcx, [rsp+0E8h+var_38]
0x1803d3d7a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d3d7f  nop
0x1803d3d80  lea     rcx, [rsp+0E8h+var_30]
0x1803d3d88  call    ?InternalRelease@?$ComPtr@UIUpdateViewValueSet@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(void)
0x1803d3d8d  nop
0x1803d3d8e  mov     rcx, [rsp+0E8h+string]; string
0x1803d3d96  call    cs:__imp_WindowsDeleteString
0x1803d3d9c  mov     eax, ebx
0x1803d3d9e  jmp     loc_1803D3F43
0x1803d3da3  cmp     [rsp+0E8h+var_48], 0
0x1803d3dab  jnz     short loc_1803D3DFC
0x1803d3dad  mov     rcx, [rsp+0E8h]; this
0x1803d3db5  mov     ebx, 80004005h
0x1803d3dba  mov     r9d, ebx; char *
0x1803d3dbd  mov     r8, rsi; unsigned int
0x1803d3dc0  mov     edx, 642h; void *
0x1803d3dc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d3dca  nop
0x1803d3dcb  lea     rcx, [rsp+0E8h+var_38]
0x1803d3dd3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d3dd8  nop
0x1803d3dd9  lea     rcx, [rsp+0E8h+var_30]
0x1803d3de1  call    ?InternalRelease@?$ComPtr@UIUpdateViewValueSet@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(void)
0x1803d3de6  nop
0x1803d3de7  mov     rcx, [rsp+0E8h+string]; string
0x1803d3def  call    cs:__imp_WindowsDeleteString
0x1803d3df5  mov     eax, ebx
0x1803d3df7  jmp     loc_1803D3F43
0x1803d3dfc  lea     rcx, [rsp+0E8h+var_38]
0x1803d3e04  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803d3e09  nop
0x1803d3e0a  lea     rcx, [rsp+0E8h+var_30]
0x1803d3e12  call    ?InternalRelease@?$ComPtr@UIUpdateViewValueSet@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUpdateViewValueSet>::InternalRelease(void)
0x1803d3e17  nop
0x1803d3e18  mov     rcx, [rsp+0E8h+string]; string
0x1803d3e20  call    cs:__imp_WindowsDeleteString
0x1803d3e26  xor     eax, eax
0x1803d3e28  jmp     loc_1803D3F43
0x1803d3e2d  mov     rcx, [rsp+0E8h+string]; string
0x1803d3e35  call    cs:__imp_WindowsDeleteString
0x1803d3e3b  mov     [rsp+0E8h+var_28], 0
0x1803d3e47  mov     rax, [r14]
0x1803d3e4a  mov     rbx, [rax+30h]
0x1803d3e4e  xor     ecx, ecx; string
0x1803d3e50  call    cs:__imp_WindowsDeleteString
0x1803d3e56  mov     [rsp+0E8h+var_28], 0
0x1803d3e62  lea     rdx, [rsp+0E8h+var_28]
0x1803d3e6a  mov     rcx, r14
0x1803d3e6d  mov     rax, rbx
0x1803d3e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803d3e75  mov     ebx, eax
0x1803d3e77  test    eax, eax
0x1803d3e79  jns     short loc_1803D3EA9
0x1803d3e7b  mov     rcx, [rsp+0E8h]; this
0x1803d3e83  mov     r9d, eax; char *
0x1803d3e86  mov     r8, rsi; unsigned int
0x1803d3e89  mov     edx, 64Ah; void *
0x1803d3e8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803d3e93  nop
0x1803d3e94  mov     rcx, [rsp+0E8h+var_28]; string
0x1803d3e9c  call    cs:__imp_WindowsDeleteString
0x1803d3ea2  mov     eax, ebx
0x1803d3ea4  jmp     loc_1803D3F43
0x1803d3ea9  mov     ebx, 70h ; 'p'
0x1803d3eae  mov     r8d, ebx; Size
0x1803d3eb1  xor     edx, edx; Val
0x1803d3eb3  lea     rcx, [rsp+0E8h+pExecInfo]; void *
0x1803d3eb8  call    memset_0
0x1803d3ebd  mov     [rsp+0E8h+pExecInfo.cbSize], ebx
0x1803d3ec1  mov     [rsp+0E8h+pExecInfo.fMask], 4000400h
0x1803d3ec9  lea     rax, Operation; "open"
0x1803d3ed0  mov     [rsp+0E8h+pExecInfo.lpVerb], rax
0x1803d3ed5  xor     edx, edx; length
0x1803d3ed7  mov     rcx, [rsp+0E8h+var_28]; string
0x1803d3edf  call    cs:__imp_WindowsGetStringRawBuffer
0x1803d3ee5  mov     [rsp+0E8h+pExecInfo.lpFile], rax
0x1803d3eea  mov     [rsp+0E8h+pExecInfo.nShow], 1
0x1803d3ef2  lea     rcx, [rsp+0E8h+pExecInfo]; pExecInfo
0x1803d3ef7  call    cs:__imp_ShellExecuteExW
0x1803d3efd  test    eax, eax
0x1803d3eff  jnz     short loc_1803D3F2A
0x1803d3f01  mov     rcx, [rsp+0E8h]; this
0x1803d3f09  mov     r8, rsi; unsigned int
0x1803d3f0c  mov     edx, 655h; void *
0x1803d3f11  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1803d3f16  mov     ebx, eax
0x1803d3f18  mov     rcx, [rsp+0E8h+var_28]; string
0x1803d3f20  call    cs:__imp_WindowsDeleteString
0x1803d3f26  mov     eax, ebx
0x1803d3f28  jmp     short loc_1803D3F43
0x1803d3f2a  mov     rcx, [rsp+0E8h+var_28]; string
0x1803d3f32  call    cs:__imp_WindowsDeleteString
0x1803d3f38  xor     eax, eax
0x1803d3f3a  jmp     short loc_1803D3F43
0x1803d3f3c  mov     eax, dword ptr [rsp+0E8h+string]
0x1803d3f43  mov     rcx, [rsp+0E8h+var_20]
0x1803d3f4b  xor     rcx, rsp; StackCookie
0x1803d3f4e  call    __security_check_cookie
0x1803d3f53  mov     rbx, [rsp+0E8h+arg_10]
0x1803d3f5b  add     rsp, 0D0h
0x1803d3f62  pop     r14
0x1803d3f64  pop     rdi
0x1803d3f65  pop     rsi
0x1803d3f66  retn
```
