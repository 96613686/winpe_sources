# PenWorkspace::Discover::RecentAppsCache::LoadOEMApps(_FILETIME,int *)

- ea: `0x18033ad58`
- end: `0x18033b07b`
- name: `?LoadOEMApps@RecentAppsCache@Discover@PenWorkspace@@AEAAJU_FILETIME@@PEAH@Z`
- size: `803`
- prototype: `__int64 __fastcall(PenWorkspace::Discover::RecentAppsCache *__hidden this, struct _FILETIME, int *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18045e0cc`

## callees

- `0x1800134f8`
- `0x18001f6e0`
- `0x1800237c8`
- `0x180031c70`
- `0x18005a710`
- `0x1800c1b9c`
- `0x1800c1c00`
- `0x1800ecfc0`
- `0x1802f324c`
- `0x18033ad58`
- `0x18033b084`
- `0x18033b0b8`
- `0x180356360`
- `0x18045cd6c`
- `0x18045f754`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033af3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033af83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033afe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033aff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033af3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033af83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033afe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033aff7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033aeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033af72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033afb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033aeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033af72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033afb9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18033ade1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18033ade1`

## string_xrefs

- `0x18033adf4`: `pcshell\twinui\penworkspace\broker\lib\recentappscache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall PenWorkspace::Discover::RecentAppsCache::LoadOEMApps(
        PenWorkspace::Discover::RecentAppsCache *this,
        struct _FILETIME a2,
        int *a3,
        __int64 a4)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  LPVOID v11; // rdi
  void (__fastcall *v12)(LPVOID, __int64, __int64 *); // rbx
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int (__fastcall *v23)(__int64 *, HSTRING *); // r14
  HSTRING v24; // rdi
  HSTRING v25; // rcx
  __int64 v26; // rax
  HSTRING *v27; // r8
  const unsigned __int16 *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  int ppv; // [rsp+20h] [rbp-99h]
  HSTRING v34; // [rsp+30h] [rbp-89h] BYREF
  HSTRING v35; // [rsp+38h] [rbp-81h] BYREF
  HSTRING string; // [rsp+40h] [rbp-79h] BYREF
  __int64 v37; // [rsp+48h] [rbp-71h] BYREF
  LPVOID v38; // [rsp+50h] [rbp-69h] BYREF
  const unsigned __int16 *StringRawBuffer; // [rsp+58h] [rbp-61h] BYREF
  struct _FILETIME v40; // [rsp+60h] [rbp-59h] BYREF
  __int64 v41; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v42; // [rsp+70h] [rbp-49h] BYREF
  int v43; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v44[2]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v45[8]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v46; // [rsp+98h] [rbp-21h] BYREF
  int v47; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v48[8]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-9h]
  _BYTE v50[32]; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *a3 = 0;
  v34 = (HSTRING)(*(_QWORD *)&a2 + 100000000LL);
  v40 = (struct _FILETIME)(*(_QWORD *)&a2 + 100000000LL);
  v38 = 0;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease)(
    &v38,
    a2,
    a3,
    a4);
  v6 = CoCreateInstance(
         &GUID_9280e842_f931_4d24_b074_739fb4da43f4,
         0,
         1u,
         &GUID_9302a129_7433_42a0_9cb8_5da5964f2756,
         &v38);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"pcshell\\twinui\\penworkspace\\broker\\lib\\recentappscache.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    goto LABEL_30;
  }
  v37 = 0;
  v11 = v38;
  v12 = *(void (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v38 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v12(v11, 1, &v37);
  v13 = v37;
  if ( !v37 )
    goto LABEL_29;
  v41 = v37;
  Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v41);
  v42 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v13 + 24LL))(v13, &v42);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"desktop\\internal\\shell\\inc\\private\\objectarrayadapter.h",
      (const char *)(unsigned int)v14,
      ppv);
  details::ObjectArrayAdapterImpl<IPenWorkspaceLayoutItem,Microsoft::WRL::ComPtr<IPenWorkspaceLayoutItem>>::Iterator::Iterator(
    &v43,
    &v41,
    0);
  details::ObjectArrayAdapterImpl<IPenWorkspaceLayoutItem,Microsoft::WRL::ComPtr<IPenWorkspaceLayoutItem>>::Iterator::Iterator(
    &v47,
    &v41,
    v42);
  while ( v43 != v47 || v44[1] != v49 )
  {
    v18 = (__int64 *)v44[0];
    v46 = v44[0];
    if ( v44[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v44[0] + 8LL))(v44[0]);
    string = 0;
    v35 = 0;
    v19 = *v18;
    string = 0;
    if ( (*(int (__fastcall **)(__int64 *, HSTRING *))(v19 + 24))(v18, &string) < 0 )
    {
      v23 = *(int (__fastcall **)(__int64 *, HSTRING *))(*v18 + 32);
      v24 = v35;
      if ( v35 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v45);
        WindowsDeleteString(v24);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v45);
      }
      v35 = 0;
      if ( v23(v18, &v35) >= 0 )
      {
        v25 = v35;
        if ( !v35 )
          goto LABEL_23;
        StringRawBuffer = WindowsGetStringRawBuffer(v35, 0);
        v34 = 0;
        WindowsDeleteString(0);
        v34 = 0;
        v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v50, &StringRawBuffer);
        if ( (int)PenWorkspace::Discover::GetApplicationUserModelIdFromLinkFile(
                    *(HSTRING *)(v26 + 24),
                    (HSTRING)&v34,
                    v27) >= 0 )
        {
          v28 = WindowsGetStringRawBuffer(v34, 0);
          if ( (int)PenWorkspace::Discover::RecentAppsCache::PrependDefaultApp(this, v28, &v40) >= 0 )
          {
            PenWorkspaceBrokerTelemetry::OemAppLoaded<unsigned short const * &>(&StringRawBuffer);
            ++*a3;
          }
        }
        WindowsDeleteString(v34);
        v34 = 0;
      }
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( (int)PenWorkspace::Discover::RecentAppsCache::PrependDefaultApp(this, StringRawBuffer, &v40) >= 0 )
      {
        PenWorkspaceBrokerTelemetry::OemAppLoaded<unsigned short const * &>(&StringRawBuffer);
        ++*a3;
      }
    }
    v25 = v35;
LABEL_23:
    if ( v25 )
      WindowsDeleteString(v25);
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v46, v20, v21, v22);
    ++v43;
    details::ObjectArrayAdapterImpl<IPenWorkspaceLayoutItem,Microsoft::WRL::ComPtr<IPenWorkspaceLayoutItem>>::Iterator::GetCurrentObject(&v43);
  }
  Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(v48, v15, v16, v17);
  Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(v44, v29, v30, v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
LABEL_29:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v7 = 0;
LABEL_30:
  Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v38, v8, v9, v10);
  return v7;
}

```

## disassembly

```asm
0x18033ad58  push    rbp
0x18033ad5a  push    rbx
0x18033ad5b  push    rsi
0x18033ad5c  push    rdi
0x18033ad5d  push    r12
0x18033ad5f  push    r14
0x18033ad61  push    r15
0x18033ad63  lea     rbp, [rsp-27h]
0x18033ad68  sub     rsp, 0E0h
0x18033ad6f  mov     rax, cs:__security_cookie
0x18033ad76  xor     rax, rsp
0x18033ad79  mov     [rbp+57h+var_38], rax
0x18033ad7d  mov     rsi, r8
0x18033ad80  mov     r15, rcx
0x18033ad83  mov     rax, rdx
0x18033ad86  shr     rax, 20h
0x18033ad8a  xor     r12d, r12d
0x18033ad8d  mov     [r8], r12d
0x18033ad90  mov     dword ptr [rsp+110h+var_E0], edx
0x18033ad94  mov     dword ptr [rsp+110h+var_E0+4], eax
0x18033ad98  mov     rax, [rsp+110h+var_E0]
0x18033ad9d  add     rax, 5F5E100h
0x18033ada3  mov     [rsp+110h+var_E0], rax
0x18033ada8  mov     ecx, dword ptr [rsp+110h+var_E0]
0x18033adac  mov     [rbp+57h+var_B0.dwLowDateTime], ecx
0x18033adaf  shr     rax, 20h
0x18033adb3  mov     [rbp+57h+var_B0.dwHighDateTime], eax
0x18033adb6  mov     [rbp+57h+var_C0], r12
0x18033adba  lea     rcx, [rbp+57h+var_C0]
0x18033adbe  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18033adc3  lea     rax, [rbp+57h+var_C0]
0x18033adc7  mov     qword ptr [rsp+110h+ppv], rax; int
0x18033adcc  lea     r9, _GUID_9302a129_7433_42a0_9cb8_5da5964f2756; riid
0x18033add3  xor     edx, edx; pUnkOuter
0x18033add5  lea     r8d, [r12+1]; dwClsContext
0x18033adda  lea     rcx, _GUID_9280e842_f931_4d24_b074_739fb4da43f4; rclsid
0x18033ade1  call    cs:__imp_CoCreateInstance
0x18033ade7  mov     ebx, eax
0x18033ade9  test    eax, eax
0x18033adeb  jns     short loc_18033AE0A
0x18033aded  mov     rcx, [rbp+5Fh]; this
0x18033adf1  mov     r9d, eax; char *
0x18033adf4  lea     r8, aPcshellTwinuiP_0; "pcshell\\twinui\\penworkspace\\broker\\"...
0x18033adfb  mov     edx, 2A9h; void *
0x18033ae00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033ae05  jmp     loc_18033B052
0x18033ae0a  mov     [rbp+57h+var_C8], r12
0x18033ae0e  mov     rdi, [rbp+57h+var_C0]
0x18033ae12  mov     rax, [rdi]
0x18033ae15  mov     rbx, [rax+20h]
0x18033ae19  lea     rcx, [rbp+57h+var_C8]
0x18033ae1d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033ae22  lea     r8, [rbp+57h+var_C8]
0x18033ae26  mov     edx, 1
0x18033ae2b  mov     rcx, rdi
0x18033ae2e  call    rbx
0x18033ae30  mov     rbx, [rbp+57h+var_C8]
0x18033ae34  test    rbx, rbx
0x18033ae37  jz      loc_18033B046
0x18033ae3d  mov     [rbp+57h+var_A8], rbx
0x18033ae41  lea     rcx, [rbp+57h+var_A8]
0x18033ae45  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x18033ae4a  nop
0x18033ae4b  mov     [rbp+57h+var_A0], r12d
0x18033ae4f  mov     rax, [rbx]
0x18033ae52  lea     rdx, [rbp+57h+var_A0]
0x18033ae56  mov     rcx, rbx
0x18033ae59  call    qword ptr [rax+18h]
0x18033ae5c  mov     rcx, [rbp+5Fh]; this
0x18033ae60  test    eax, eax
0x18033ae62  jns     short loc_18033AE79
0x18033ae64  mov     r9d, eax; char *
0x18033ae67  lea     r8, aDesktopInterna_23; "desktop\\internal\\shell\\inc\\private"...
0x18033ae6e  mov     edx, 10h; void *
0x18033ae73  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033ae78  nop
0x18033ae79  xor     r8d, r8d
0x18033ae7c  lea     rdx, [rbp+57h+var_A8]
0x18033ae80  lea     rcx, [rbp+57h+var_98]
0x18033ae84  call    ??0Iterator@?$ObjectArrayAdapterImpl@UIPenWorkspaceLayoutItem@@V?$ComPtr@UIPenWorkspaceLayoutItem@@@WRL@Microsoft@@@details@@QEAA@QEAV12@I@Z; details::ObjectArrayAdapterImpl<IPenWorkspaceLayoutItem,Microsoft::WRL::ComPtr<IPenWorkspaceLayoutItem>>::Iterator::Iterator(details::ObjectArrayAdapterImpl<IPenWorkspaceLayoutItem,Microsoft::WRL::ComPtr<IPenWorkspaceLayoutItem>> * const,uint)
0x18033ae89  nop
0x18033ae8a  mov     r8d, [rbp+57h+var_A0]
0x18033ae8e  lea     rdx, [rbp+57h+var_A8]
0x18033ae92  lea     rcx, [rbp+57h+var_70]
0x18033ae96  call    ??0Iterator@?$ObjectArrayAdapterImpl@UIPenWorkspaceLayoutItem@@V?$ComPtr@UIPenWorkspaceLayoutItem@@@WRL@Microsoft@@@details@@QEAA@QEAV12@I@Z; details::ObjectArrayAdapterImpl<IPenWorkspaceLayoutItem,Microsoft::WRL::ComPtr<IPenWorkspaceLayoutItem>>::Iterator::Iterator(details::ObjectArrayAdapterImpl<IPenWorkspaceLayoutItem,Microsoft::WRL::ComPtr<IPenWorkspaceLayoutItem>> * const,uint)
0x18033ae9b  nop
0x18033ae9c  mov     eax, [rbp+57h+var_70]
0x18033ae9f  cmp     [rbp+57h+var_98], eax
0x18033aea2  jnz     short loc_18033AEB2
0x18033aea4  mov     rax, [rbp+57h+var_60]
0x18033aea8  cmp     [rbp+57h+var_88], rax
0x18033aeac  jz      loc_18033B028
0x18033aeb2  mov     rbx, [rbp+57h+var_90]
0x18033aeb6  mov     [rbp+57h+var_78], rbx
0x18033aeba  test    rbx, rbx
0x18033aebd  jz      short loc_18033AEC9
0x18033aebf  mov     rax, [rbx]
0x18033aec2  mov     rcx, rbx
0x18033aec5  call    qword ptr [rax+8]
0x18033aec8  nop
0x18033aec9  mov     [rbp+57h+string], r12
0x18033aecd  mov     [rsp+110h+var_D8], r12
0x18033aed2  mov     rax, [rbx]
0x18033aed5  mov     [rbp+57h+string], r12
0x18033aed9  lea     rdx, [rbp+57h+string]
0x18033aedd  mov     rcx, rbx
0x18033aee0  call    qword ptr [rax+18h]
0x18033aee3  test    eax, eax
0x18033aee5  js      short loc_18033AF1E
0x18033aee7  xor     edx, edx; length
0x18033aee9  mov     rcx, [rbp+57h+string]; string
0x18033aeed  call    cs:__imp_WindowsGetStringRawBuffer
0x18033aef3  mov     [rbp+57h+var_B8], rax
0x18033aef7  lea     r8, [rbp+57h+var_B0]; struct _FILETIME *
0x18033aefb  mov     rdx, rax; unsigned __int16 *
0x18033aefe  mov     rcx, r15; this
0x18033af01  call    ?PrependDefaultApp@RecentAppsCache@Discover@PenWorkspace@@AEAAJPEBGAEAU_FILETIME@@@Z; PenWorkspace::Discover::RecentAppsCache::PrependDefaultApp(ushort const *,_FILETIME &)
0x18033af06  test    eax, eax
0x18033af08  js      loc_18033AFED
0x18033af0e  lea     rcx, [rbp+57h+var_B8]
0x18033af12  call    ??$OemAppLoaded@AEAPEBG@PenWorkspaceBrokerTelemetry@@SAXAEAPEBG@Z; PenWorkspaceBrokerTelemetry::OemAppLoaded<ushort const * &>(ushort const * &)
0x18033af17  inc     dword ptr [rsi]
0x18033af19  jmp     loc_18033AFED
0x18033af1e  mov     rax, [rbx]
0x18033af21  mov     r14, [rax+20h]
0x18033af25  mov     rdi, [rsp+110h+var_D8]
0x18033af2a  test    rdi, rdi
0x18033af2d  jz      short loc_18033AF4A
0x18033af2f  lea     rcx, [rbp+57h+var_80]; this
0x18033af33  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18033af38  mov     rcx, rdi; string
0x18033af3b  call    cs:__imp_WindowsDeleteString
0x18033af41  lea     rcx, [rbp+57h+var_80]; this
0x18033af45  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18033af4a  mov     [rsp+110h+var_D8], r12
0x18033af4f  lea     rdx, [rsp+110h+var_D8]
0x18033af54  mov     rcx, rbx
0x18033af57  call    r14
0x18033af5a  test    eax, eax
0x18033af5c  js      loc_18033AFED
0x18033af62  mov     rcx, [rsp+110h+var_D8]; string
0x18033af67  test    rcx, rcx
0x18033af6a  jz      loc_18033AFF2
0x18033af70  xor     edx, edx; length
0x18033af72  call    cs:__imp_WindowsGetStringRawBuffer
0x18033af78  mov     [rbp+57h+var_B8], rax
0x18033af7c  mov     [rsp+110h+var_E0], r12
0x18033af81  xor     ecx, ecx; string
0x18033af83  call    cs:__imp_WindowsDeleteString
0x18033af89  mov     [rsp+110h+var_E0], r12
0x18033af8e  lea     rdx, [rbp+57h+var_B8]
0x18033af92  lea     rcx, [rbp+57h+var_58]
0x18033af96  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18033af9b  nop
0x18033af9c  lea     rdx, [rsp+110h+var_E0]; HSTRING
0x18033afa1  mov     rcx, [rax+18h]; string
0x18033afa5  call    ?GetApplicationUserModelIdFromLinkFile@Discover@PenWorkspace@@YAJQEAUHSTRING__@@PEAPEAU3@@Z; PenWorkspace::Discover::GetApplicationUserModelIdFromLinkFile(HSTRING__ * const,HSTRING__ * *)
0x18033afaa  nop
0x18033afab  shr     eax, 1Fh
0x18033afae  xor     al, 1
0x18033afb0  jz      short loc_18033AFDD
0x18033afb2  xor     edx, edx; length
0x18033afb4  mov     rcx, [rsp+110h+var_E0]; string
0x18033afb9  call    cs:__imp_WindowsGetStringRawBuffer
0x18033afbf  lea     r8, [rbp+57h+var_B0]; struct _FILETIME *
0x18033afc3  mov     rdx, rax; unsigned __int16 *
0x18033afc6  mov     rcx, r15; this
0x18033afc9  call    ?PrependDefaultApp@RecentAppsCache@Discover@PenWorkspace@@AEAAJPEBGAEAU_FILETIME@@@Z; PenWorkspace::Discover::RecentAppsCache::PrependDefaultApp(ushort const *,_FILETIME &)
0x18033afce  test    eax, eax
0x18033afd0  js      short loc_18033AFDD
0x18033afd2  lea     rcx, [rbp+57h+var_B8]
0x18033afd6  call    ??$OemAppLoaded@AEAPEBG@PenWorkspaceBrokerTelemetry@@SAXAEAPEBG@Z; PenWorkspaceBrokerTelemetry::OemAppLoaded<ushort const * &>(ushort const * &)
0x18033afdb  inc     dword ptr [rsi]
0x18033afdd  mov     rcx, [rsp+110h+var_E0]; string
0x18033afe2  call    cs:__imp_WindowsDeleteString
0x18033afe8  mov     [rsp+110h+var_E0], r12
0x18033afed  mov     rcx, [rsp+110h+var_D8]; string
0x18033aff2  test    rcx, rcx
0x18033aff5  jz      short loc_18033AFFE
0x18033aff7  call    cs:__imp_WindowsDeleteString
0x18033affd  nop
0x18033affe  mov     rcx, [rbp+57h+string]; string
0x18033b002  test    rcx, rcx
0x18033b005  jz      short loc_18033B00E
0x18033b007  call    cs:__imp_WindowsDeleteString
0x18033b00d  nop
0x18033b00e  lea     rcx, [rbp+57h+var_78]
0x18033b012  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18033b017  inc     [rbp+57h+var_98]
0x18033b01a  lea     rcx, [rbp+57h+var_98]
0x18033b01e  call    ?GetCurrentObject@Iterator@?$ObjectArrayAdapterImpl@UIPenWorkspaceLayoutItem@@V?$ComPtr@UIPenWorkspaceLayoutItem@@@WRL@Microsoft@@@details@@AEAAXXZ; details::ObjectArrayAdapterImpl<IPenWorkspaceLayoutItem,Microsoft::WRL::ComPtr<IPenWorkspaceLayoutItem>>::Iterator::GetCurrentObject(void)
0x18033b023  jmp     loc_18033AE9C
0x18033b028  lea     rcx, [rbp+57h+var_68]
0x18033b02c  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18033b031  nop
0x18033b032  lea     rcx, [rbp+57h+var_90]
0x18033b036  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18033b03b  nop
0x18033b03c  lea     rcx, [rbp+57h+var_A8]
0x18033b040  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033b045  nop
0x18033b046  lea     rcx, [rbp+57h+var_C8]
0x18033b04a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18033b04f  mov     ebx, r12d
0x18033b052  lea     rcx, [rbp+57h+var_C0]
0x18033b056  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18033b05b  mov     eax, ebx
0x18033b05d  mov     rcx, [rbp+57h+var_38]
0x18033b061  xor     rcx, rsp; StackCookie
0x18033b064  call    __security_check_cookie
0x18033b069  add     rsp, 0E0h
0x18033b070  pop     r15
0x18033b072  pop     r14
0x18033b074  pop     r12
0x18033b076  pop     rdi
0x18033b077  pop     rsi
0x18033b078  pop     rbx
0x18033b079  pop     rbp
0x18033b07a  retn
```
