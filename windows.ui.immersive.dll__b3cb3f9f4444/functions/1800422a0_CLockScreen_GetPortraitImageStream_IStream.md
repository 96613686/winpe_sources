# CLockScreen::GetPortraitImageStream(IStream * *)

- ea: `0x1800422a0`
- end: `0x1800429d5`
- name: `?GetPortraitImageStream@CLockScreen@@UEAAJPEAPEAUIStream@@@Z`
- size: `1845`
- prototype: `__int64 __fastcall(CLockScreen *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000a490`
- `0x18000af00`
- `0x18000b700`
- `0x18000c1b8`
- `0x18000c410`
- `0x180013f14`
- `0x180026440`
- `0x180034d38`
- `0x180035c94`
- `0x18003729c`
- `0x18003c324`
- `0x18003cd00`
- `0x18003fd78`
- `0x18003ff34`
- `0x180042244`
- `0x1800422a0`
- `0x1800429dc`
- `0x180042a08`
- `0x180042a48`
- `0x180042b10`
- `0x1800464f8`
- `0x180046c00`
- `0x180048c30`
- `0x18004ab6c`
- `0x18004ca2c`
- `0x180054130`
- `0x180054ad4`
- `0x1800b2df8`
- `0x1800b9058`
- `0x1800bcbc0`
- `0x1800dce10`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800423f3`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800425d6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800427e7`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800423f3`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800425d6`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800427e7`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x1800424a2`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x180042690`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x180042893`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x1800424a2`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x180042690`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x180042893`

## string_xrefs

- `0x180042778`: `PortraitAssetPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CLockScreen::GetPortraitImageStream(void **this, struct IStream **a2)
{
  bool v4; // dl
  unsigned int v5; // ebx
  int v6; // eax
  const WCHAR *v7; // rbx
  __int64 v8; // r9
  __int64 v9; // rdx
  HRESULT OnlySharedMemoryStream; // eax
  __int64 v11; // rdx
  wil::details::in1diag3 *v12; // rcx
  int v13; // eax
  int Stream; // eax
  __int64 v15; // rdx
  const WCHAR *v16; // rbx
  HRESULT v17; // eax
  __int64 v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  char v20; // r14
  int v21; // r9d
  int v22; // eax
  HRESULT v23; // eax
  __int64 v24; // rdx
  wil::details::in1diag3 *v25; // rcx
  int v26; // eax
  unsigned __int16 HistoryEntryAt; // ax
  int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rdx
  int pstmTemplate; // [rsp+20h] [rbp-E0h]
  int pstmTemplatea; // [rsp+20h] [rbp-E0h]
  int pstmTemplateb; // [rsp+20h] [rbp-E0h]
  int pstmTemplatec; // [rsp+20h] [rbp-E0h]
  int pstmTemplated; // [rsp+20h] [rbp-E0h]
  unsigned int *ppstm; // [rsp+28h] [rbp-D8h]
  LPCWSTR pszFile; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v39[16]; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR v40; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  IStream *v43; // [rsp+60h] [rbp-A0h] BYREF
  IStream *v44; // [rsp+68h] [rbp-98h] BYREF
  IStream *v45[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v46[16]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+94h] [rbp-6Ch]
  _BYTE v49[16]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+E4h] [rbp-1Ch]
  _BYTE v52[16]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v53; // [rsp+130h] [rbp+30h]
  int v54; // [rsp+134h] [rbp+34h]
  _QWORD v55[42]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v56[1664]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _WORD v57[832]; // [rsp+940h] [rbp+840h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+FF8h] [rbp+EF8h]

  wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v55);
  v55[0] = &LockScreenTelemetry::GetPortraitImageStreamActivity::`vftable';
  LockScreenTelemetry::GetPortraitImageStreamActivity::StartActivity((LockScreenTelemetry::GetPortraitImageStreamActivity *)v55);
  if ( !CLockScreen::s_IsSystemProcess() )
  {
    CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(
      (CLockScreenHistory::CSynchronizedOperation *)v39,
      v4);
    *a2 = 0;
    if ( CLockScreen::_s_IsAppContainerProcess() )
    {
      v6 = CheckCallerCapabilityAndReportError(WinCapabilityPicturesLibrarySid, 0x9805u);
      v5 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15F5,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v6,
          pstmTemplate);
LABEL_75:
        CLockScreenHistory::CSynchronizedOperation::~CSynchronizedOperation((CLockScreenHistory::CSynchronizedOperation *)v39);
        goto LABEL_76;
      }
    }
    pszFile = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszFile,
      0);
    if ( CLockScreen::_s_IsSpecificLockScreenLogonImageForced((unsigned __int16 **)&pszFile) )
    {
      v7 = pszFile;
      if ( !pszFile )
      {
        v5 = -2147467261;
        v8 = 2147500035LL;
        v9 = 5633;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)v8,
          pstmTemplate);
LABEL_74:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszFile);
        goto LABEL_75;
      }
      v43 = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
      OnlySharedMemoryStream = SHCreateStreamOnFileEx(v7, 0, 0x80u, 0, 0, &v43);
      v5 = OnlySharedMemoryStream;
      if ( OnlySharedMemoryStream < 0 )
      {
        v11 = 5635;
LABEL_12:
        v12 = retaddr;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          v12,
          (void *)v11,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)OnlySharedMemoryStream,
          pstmTemplatea);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
        goto LABEL_74;
      }
      memset_0(v46, 0, 0x50u);
      OnlySharedMemoryStream = (*(__int64 (__fastcall **)(IStream *, _BYTE *, __int64))(*(_QWORD *)v43 + 96LL))(
                                 v43,
                                 v46,
                                 1);
      v5 = OnlySharedMemoryStream;
      v12 = retaddr;
      if ( OnlySharedMemoryStream < 0 )
      {
        v11 = 5638;
        goto LABEL_13;
      }
      if ( v48 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1607,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)0x8000FFFFLL,
          pstmTemplatea);
      OnlySharedMemoryStream = SHCreateReadOnlySharedMemoryStream(
                                 v43,
                                 v47,
                                 &GUID_0000000c_0000_0000_c000_000000000046,
                                 a2);
      v5 = OnlySharedMemoryStream;
      if ( OnlySharedMemoryStream < 0 )
      {
        v11 = 5641;
        goto LABEL_12;
      }
      wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v55, 0);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
LABEL_47:
      v5 = 0;
      goto LABEL_74;
    }
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
    if ( CLockScreen::_s_IsSpotlightEnabled(0) )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
      v41 = -1;
      v42 = -1;
      v13 = CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(
              0,
              0,
              0,
              (unsigned __int16 **)&v40,
              0);
      if ( v13 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x160F,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v13,
          pstmTemplateb);
LABEL_24:
        CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v56);
        Stream = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreenHistory *)(this + 13));
        v5 = Stream;
        if ( Stream < 0 )
        {
          v15 = 5668;
LABEL_26:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)(unsigned int)Stream,
            pstmTemplateb);
          CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v56);
LABEL_33:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
          goto LABEL_74;
        }
        Stream = CLockScreenHistory::_InitAndEnsureGPEntry(
                   (CLockScreenHistory *)(this + 13),
                   (struct CLockScreenHistory::CLockScreenHistoryEntry *)v56,
                   0x5Au);
        v5 = Stream;
        if ( Stream < 0 )
        {
          v15 = 5669;
          goto LABEL_26;
        }
        Stream = CLockScreenHistory::CLockScreenHistoryEntry::GetStream(
                   (CLockScreenHistory::CLockScreenHistoryEntry *)v56,
                   1,
                   a2);
        v5 = Stream;
        if ( Stream < 0 )
        {
          v15 = 5670;
          goto LABEL_26;
        }
        CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v56);
LABEL_46:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
        goto LABEL_47;
      }
      v16 = v40;
      if ( !v40 || !*v40 )
        goto LABEL_24;
      v44 = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
      v17 = SHCreateStreamOnFileEx(v16, 0, 0x80u, 0, 0, &v44);
      v5 = v17;
      if ( v17 >= 0 )
      {
        memset_0(v49, 0, 0x50u);
        v17 = (*(__int64 (__fastcall **)(IStream *, _BYTE *, __int64))(*(_QWORD *)v44 + 96LL))(v44, v49, 1);
        v5 = v17;
        v19 = retaddr;
        if ( v17 < 0 )
        {
          v18 = 5658;
          goto LABEL_32;
        }
        if ( v51 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x161B,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)0x8000FFFFLL,
            pstmTemplatec);
        v17 = SHCreateReadOnlySharedMemoryStream(v44, v50, &GUID_0000000c_0000_0000_c000_000000000046, a2);
        v5 = v17;
        if ( v17 >= 0 )
        {
          wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v55, 0);
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
          goto LABEL_46;
        }
        v18 = 5661;
      }
      else
      {
        v18 = 5651;
      }
      v19 = retaddr;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        v19,
        (void *)v18,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v17,
        pstmTemplatec);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
      goto LABEL_33;
    }
    v20 = 0;
    if ( CLockScreen::_s_IsSpotlight() && !CLockScreen::_s_IsSpotlightExpired() )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
      v41 = -1;
      v42 = -1;
      v22 = SHRegAllocData(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen\\Creative",
              L"PortraitAssetPath",
              v21,
              (void **)&v40,
              ppstm);
      v5 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x162E,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v22,
          pstmTemplated);
        goto LABEL_33;
      }
      v45[0] = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v45);
      v23 = SHCreateStreamOnFileEx(v40, 0, 0x80u, 0, 0, v45);
      v5 = v23;
      if ( v23 < 0 )
      {
        v24 = 5681;
LABEL_54:
        v25 = retaddr;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          v25,
          (void *)v24,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v23,
          pstmTemplate);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v45);
        goto LABEL_33;
      }
      memset_0(v52, 0, 0x50u);
      v23 = (*(__int64 (__fastcall **)(IStream *, _BYTE *, __int64))(*(_QWORD *)v45[0] + 96LL))(v45[0], v52, 1);
      v5 = v23;
      v25 = retaddr;
      if ( v23 < 0 )
      {
        v24 = 5688;
        goto LABEL_55;
      }
      if ( v54 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1639,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)0x8000FFFFLL,
          pstmTemplate);
      v23 = SHCreateReadOnlySharedMemoryStream(v45[0], v53, &GUID_0000000c_0000_0000_c000_000000000046, a2);
      v5 = v23;
      if ( v23 < 0 )
      {
        v24 = 5691;
        goto LABEL_54;
      }
      v20 = 1;
      wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v55, 0);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v45);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
    }
    v5 = 0;
    if ( v20 )
      goto LABEL_74;
    v26 = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreenHistory *)(this + 13));
    v5 = v26;
    if ( v26 >= 0 )
    {
      CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v57);
      HistoryEntryAt = CLockScreenHistory::s_GetHistoryEntryAt(0, this[13]);
      v28 = CLockScreenHistory::_InitAndEnsureGPEntry(
              (CLockScreenHistory *)(this + 13),
              (struct CLockScreenHistory::CLockScreenHistoryEntry *)v57,
              HistoryEntryAt);
      v5 = v28;
      if ( v28 >= 0 )
      {
        v29 = CLockScreenHistory::CLockScreenHistoryEntry::GetStream(
                (CLockScreenHistory::CLockScreenHistoryEntry *)v57,
                1,
                a2);
        v5 = v29;
        if ( v29 != -2147024894 || v57[0] == 79 )
          v30 = v29;
        else
          v30 = 0;
        wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v55, v30);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1644,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v28,
          pstmTemplate);
      }
      CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v57);
      goto LABEL_74;
    }
    v8 = (unsigned int)v26;
    v9 = 5697;
    goto LABEL_9;
  }
  v5 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15ED,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
    (const char *)0x8000FFFFLL,
    pstmTemplate);
LABEL_76:
  LockScreenTelemetry::GetPortraitImageStreamActivity::~GetPortraitImageStreamActivity((LockScreenTelemetry::GetPortraitImageStreamActivity *)v55);
  return v5;
}

```

## disassembly

```asm
0x1800422a0  mov     [rsp-8+arg_10], rbx
0x1800422a5  push    rbp
0x1800422a6  push    rsi
0x1800422a7  push    r12
0x1800422a9  push    r14
0x1800422ab  push    r15
0x1800422ad  lea     rbp, [rsp-0ED0h]
0x1800422b5  sub     rsp, 0FD0h
0x1800422bc  mov     rax, cs:__security_cookie
0x1800422c3  xor     rax, rsp
0x1800422c6  mov     [rbp+0EF0h+var_30], rax
0x1800422cd  mov     rsi, rdx
0x1800422d0  mov     r15, rcx
0x1800422d3  lea     rdx, aGetportraitima; "GetPortraitImageStreamActivity"
0x1800422da  lea     rcx, [rbp+0EF0h+var_E80]; struct wil::details::IFailureCallback *
0x1800422de  call    ??0?$ActivityBase@VLockScreenLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800422e3  lea     rax, ??_7GetPortraitImageStreamActivity@LockScreenTelemetry@@6B@; const LockScreenTelemetry::GetPortraitImageStreamActivity::`vftable'
0x1800422ea  mov     [rbp+0EF0h+var_E80], rax
0x1800422ee  lea     rcx, [rbp+0EF0h+var_E80]; this
0x1800422f2  call    ?StartActivity@GetPortraitImageStreamActivity@LockScreenTelemetry@@QEAAXXZ; LockScreenTelemetry::GetPortraitImageStreamActivity::StartActivity(void)
0x1800422f7  nop
0x1800422f8  call    ?s_IsSystemProcess@CLockScreen@@SA_NXZ; CLockScreen::s_IsSystemProcess(void)
0x1800422fd  xor     r12d, r12d
0x180042300  test    al, al
0x180042302  jz      short loc_180042329
0x180042304  mov     rcx, [rbp+0EF8h]; this
0x18004230b  mov     ebx, 8000FFFFh
0x180042310  mov     r9d, ebx; char *
0x180042313  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18004231a  mov     edx, 15EDh; void *
0x18004231f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042324  jmp     loc_1800429A2
0x180042329  lea     rcx, [rsp+0FF0h+var_FB8]; this
0x18004232e  call    ??0CSynchronizedOperation@CLockScreenHistory@@QEAA@_N@Z; CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(bool)
0x180042333  nop
0x180042334  mov     [rsi], r12
0x180042337  call    ?_s_IsAppContainerProcess@CLockScreen@@KA_NXZ; CLockScreen::_s_IsAppContainerProcess(void)
0x18004233c  test    al, al
0x18004233e  jz      short loc_180042375
0x180042340  mov     edx, 9805h; unsigned int
0x180042345  mov     ecx, 58h ; 'X'; enum WELL_KNOWN_SID_TYPE
0x18004234a  call    ?CheckCallerCapabilityAndReportError@@YAJW4WELL_KNOWN_SID_TYPE@@IZZ; CheckCallerCapabilityAndReportError(WELL_KNOWN_SID_TYPE,uint,...)
0x18004234f  mov     ebx, eax
0x180042351  test    eax, eax
0x180042353  jns     short loc_180042375
0x180042355  mov     rcx, [rbp+0EF8h]; this
0x18004235c  mov     r9d, eax; char *
0x18004235f  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180042366  mov     edx, 15F5h; void *
0x18004236b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042370  jmp     loc_180042997
0x180042375  mov     [rsp+0FF0h+pszFile], r12
0x18004237a  xor     edx, edx
0x18004237c  lea     rcx, [rsp+0FF0h+pszFile]
0x180042381  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180042386  lea     rcx, [rsp+0FF0h+pszFile]; unsigned __int16 **
0x18004238b  call    ?_s_IsSpecificLockScreenLogonImageForced@CLockScreen@@KA_NPEAPEAG@Z; CLockScreen::_s_IsSpecificLockScreenLogonImageForced(ushort * *)
0x180042390  test    al, al
0x180042392  jz      loc_1800424D9
0x180042398  mov     rbx, [rsp+0FF0h+pszFile]
0x18004239d  test    rbx, rbx
0x1800423a0  jnz     short loc_1800423C7
0x1800423a2  mov     ebx, 80004003h
0x1800423a7  mov     r9d, ebx; char *
0x1800423aa  mov     edx, 1601h; void *
0x1800423af  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x1800423b6  mov     rcx, [rbp+0EF8h]; this
0x1800423bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800423c2  jmp     loc_18004298C
0x1800423c7  mov     [rsp+0FF0h+var_F90], r12
0x1800423cc  lea     rcx, [rsp+0FF0h+var_F90]
0x1800423d1  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800423d6  lea     rax, [rsp+0FF0h+var_F90]
0x1800423db  mov     [rsp+0FF0h+ppstm], rax; ppstm
0x1800423e0  mov     [rsp+0FF0h+pstmTemplate], r12; int
0x1800423e5  xor     r9d, r9d; fCreate
0x1800423e8  xor     edx, edx; grfMode
0x1800423ea  mov     r8d, 80h; dwAttributes
0x1800423f0  mov     rcx, rbx; pszFile
0x1800423f3  call    cs:__imp_SHCreateStreamOnFileEx
0x1800423fa  nop     dword ptr [rax+rax+00h]
0x1800423ff  mov     ebx, eax
0x180042401  test    eax, eax
0x180042403  jns     short loc_180042430
0x180042405  mov     edx, 1603h; void *
0x18004240a  mov     rcx, [rbp+0EF8h]; this
0x180042411  mov     r9d, eax; char *
0x180042414  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18004241b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042420  nop
0x180042421  lea     rcx, [rsp+0FF0h+var_F90]
0x180042426  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18004242b  jmp     loc_18004298C
0x180042430  xor     edx, edx; Val
0x180042432  lea     r8d, [rdx+50h]; Size
0x180042436  lea     rcx, [rbp+0EF0h+var_F70]; void *
0x18004243a  call    memset_0
0x18004243f  mov     rcx, [rsp+0FF0h+var_F90]
0x180042444  mov     rax, [rcx]
0x180042447  mov     r8d, 1
0x18004244d  lea     rdx, [rbp+0EF0h+var_F70]
0x180042451  mov     rax, [rax+60h]
0x180042455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004245a  mov     ebx, eax
0x18004245c  mov     rcx, [rbp+0EF8h]; this
0x180042463  test    eax, eax
0x180042465  jns     short loc_18004246E
0x180042467  mov     edx, 1606h
0x18004246c  jmp     short loc_180042411
0x18004246e  cmp     [rbp+0EF0h+var_F5C], r12d
0x180042472  setz    al
0x180042475  test    al, al
0x180042477  jnz     short loc_180042490
0x180042479  mov     r9d, 8000FFFFh; char *
0x18004247f  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180042486  mov     edx, 1607h; void *
0x18004248b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042490  mov     r9, rsi
0x180042493  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x18004249a  mov     edx, [rbp+0EF0h+var_F60]
0x18004249d  mov     rcx, [rsp+0FF0h+var_F90]
0x1800424a2  call    cs:__imp_SHCreateReadOnlySharedMemoryStream
0x1800424a9  nop     dword ptr [rax+rax+00h]
0x1800424ae  mov     ebx, eax
0x1800424b0  test    eax, eax
0x1800424b2  jns     short loc_1800424BE
0x1800424b4  mov     edx, 1609h
0x1800424b9  jmp     loc_18004240A
0x1800424be  xor     edx, edx
0x1800424c0  lea     rcx, [rbp+0EF0h+var_E80]
0x1800424c4  call    ?Stop@?$ActivityBase@VLockScreenLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800424c9  nop
0x1800424ca  lea     rcx, [rsp+0FF0h+var_F90]
0x1800424cf  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800424d4  jmp     loc_180042722
0x1800424d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x1800424e0  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800424e5  xor     ecx, ecx; this
0x1800424e7  call    ?_s_IsSpotlightEnabled@CLockScreen@@KA_NPEBG@Z; CLockScreen::_s_IsSpotlightEnabled(ushort const *)
0x1800424ec  test    al, al
0x1800424ee  jz      loc_18004272A
0x1800424f4  mov     [rsp+0FF0h+var_FA8], r12
0x1800424f9  mov     [rsp+0FF0h+var_FA0], r12
0x1800424fe  mov     [rsp+0FF0h+var_F98], r12
0x180042503  lea     rcx, [rsp+0FF0h+var_FA8]
0x180042508  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004250d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042511  mov     [rsp+0FF0h+var_FA0], rax
0x180042516  mov     [rsp+0FF0h+var_F98], rax
0x18004251b  mov     [rsp+0FF0h+pstmTemplate], r12; int
0x180042520  lea     r9, [rsp+0FF0h+var_FA8]; unsigned __int16 **
0x180042525  xor     r8d, r8d; unsigned __int16 **
0x180042528  xor     edx, edx; unsigned __int16 *
0x18004252a  xor     ecx, ecx; this
0x18004252c  call    ?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z; CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x180042531  mov     rcx, [rbp+0EF8h]; this
0x180042538  test    eax, eax
0x18004253a  jns     short loc_18004259A
0x18004253c  mov     r9d, eax; char *
0x18004253f  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180042546  mov     edx, 160Fh; void *
0x18004254b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042550  lea     rcx, [rbp+0EF0h+var_D30]; this
0x180042557  call    ??0CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry(void)
0x18004255c  nop
0x18004255d  lea     rcx, [r15+68h]; this
0x180042561  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x180042566  mov     ebx, eax
0x180042568  test    eax, eax
0x18004256a  jns     loc_1800426C4
0x180042570  mov     edx, 1624h; void *
0x180042575  mov     rcx, [rbp+0EF8h]; this
0x18004257c  mov     r9d, eax; char *
0x18004257f  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180042586  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004258b  nop
0x18004258c  lea     rcx, [rbp+0EF0h+var_D30]; this
0x180042593  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x180042598  jmp     short loc_18004260F
0x18004259a  mov     rbx, [rsp+0FF0h+var_FA8]
0x18004259f  test    rbx, rbx
0x1800425a2  jz      short loc_180042550
0x1800425a4  cmp     [rbx], r12w
0x1800425a8  jz      short loc_180042550
0x1800425aa  mov     [rsp+0FF0h+var_F88], r12
0x1800425af  lea     rcx, [rsp+0FF0h+var_F88]
0x1800425b4  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800425b9  lea     rax, [rsp+0FF0h+var_F88]
0x1800425be  mov     [rsp+0FF0h+ppstm], rax; ppstm
0x1800425c3  mov     [rsp+0FF0h+pstmTemplate], r12; int
0x1800425c8  xor     r9d, r9d; fCreate
0x1800425cb  xor     edx, edx; grfMode
0x1800425cd  mov     r8d, 80h; dwAttributes
0x1800425d3  mov     rcx, rbx; pszFile
0x1800425d6  call    cs:__imp_SHCreateStreamOnFileEx
0x1800425dd  nop     dword ptr [rax+rax+00h]
0x1800425e2  mov     ebx, eax
0x1800425e4  test    eax, eax
0x1800425e6  jns     short loc_18004261E
0x1800425e8  mov     edx, 1613h; void *
0x1800425ed  mov     rcx, [rbp+0EF8h]; this
0x1800425f4  mov     r9d, eax; char *
0x1800425f7  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x1800425fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042603  nop
0x180042604  lea     rcx, [rsp+0FF0h+var_F88]
0x180042609  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18004260e  nop
0x18004260f  lea     rcx, [rsp+0FF0h+var_FA8]
0x180042614  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042619  jmp     loc_18004298C
0x18004261e  xor     edx, edx; Val
0x180042620  lea     r8d, [rdx+50h]; Size
0x180042624  lea     rcx, [rbp+0EF0h+var_F20]; void *
0x180042628  call    memset_0
0x18004262d  mov     rcx, [rsp+0FF0h+var_F88]
0x180042632  mov     rax, [rcx]
0x180042635  mov     r8d, 1
0x18004263b  lea     rdx, [rbp+0EF0h+var_F20]
0x18004263f  mov     rax, [rax+60h]
0x180042643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042648  mov     ebx, eax
0x18004264a  mov     rcx, [rbp+0EF8h]; this
0x180042651  test    eax, eax
0x180042653  jns     short loc_18004265C
0x180042655  mov     edx, 161Ah
0x18004265a  jmp     short loc_1800425F4
0x18004265c  cmp     [rbp+0EF0h+var_F0C], r12d
0x180042660  setz    al
0x180042663  test    al, al
0x180042665  jnz     short loc_18004267E
0x180042667  mov     r9d, 8000FFFFh; char *
0x18004266d  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180042674  mov     edx, 161Bh; void *
0x180042679  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004267e  mov     r9, rsi
0x180042681  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x180042688  mov     edx, [rbp+0EF0h+var_F10]
0x18004268b  mov     rcx, [rsp+0FF0h+var_F88]
0x180042690  call    cs:__imp_SHCreateReadOnlySharedMemoryStream
0x180042697  nop     dword ptr [rax+rax+00h]
0x18004269c  mov     ebx, eax
0x18004269e  test    eax, eax
0x1800426a0  jns     short loc_1800426AC
0x1800426a2  mov     edx, 161Dh
0x1800426a7  jmp     loc_1800425ED
0x1800426ac  xor     edx, edx
0x1800426ae  lea     rcx, [rbp+0EF0h+var_E80]
0x1800426b2  call    ?Stop@?$ActivityBase@VLockScreenLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800426b7  nop
0x1800426b8  lea     rcx, [rsp+0FF0h+var_F88]
0x1800426bd  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800426c2  jmp     short loc_180042718
0x1800426c4  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x1800426ca  lea     rdx, [rbp+0EF0h+var_D30]; struct CLockScreenHistory::CLockScreenHistoryEntry *
0x1800426d1  lea     rcx, [r15+68h]; this
0x1800426d5  call    ?_InitAndEnsureGPEntry@CLockScreenHistory@@IEAAJPEAVCLockScreenHistoryEntry@1@G@Z; CLockScreenHistory::_InitAndEnsureGPEntry(CLockScreenHistory::CLockScreenHistoryEntry *,ushort)
0x1800426da  mov     ebx, eax
0x1800426dc  test    eax, eax
0x1800426de  jns     short loc_1800426EA
0x1800426e0  mov     edx, 1625h
0x1800426e5  jmp     loc_180042575
0x1800426ea  mov     r8, rsi; struct IStream **
0x1800426ed  mov     dl, 1; bool
0x1800426ef  lea     rcx, [rbp+0EF0h+var_D30]; this
0x1800426f6  call    ?GetStream@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJ_NPEAPEAUIStream@@@Z; CLockScreenHistory::CLockScreenHistoryEntry::GetStream(bool,IStream * *)
0x1800426fb  mov     ebx, eax
0x1800426fd  test    eax, eax
0x1800426ff  jns     short loc_18004270B
0x180042701  mov     edx, 1626h
0x180042706  jmp     loc_180042575
0x18004270b  lea     rcx, [rbp+0EF0h+var_D30]; this
0x180042712  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x180042717  nop
0x180042718  lea     rcx, [rsp+0FF0h+var_FA8]
0x18004271d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042722  mov     ebx, r12d
0x180042725  jmp     loc_18004298C
0x18004272a  mov     r14b, r12b
0x18004272d  call    ?_s_IsSpotlight@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlight(void)
0x180042732  test    al, al
0x180042734  jz      loc_1800428D3
0x18004273a  call    ?_s_IsSpotlightExpired@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlightExpired(void)
0x18004273f  test    al, al
0x180042741  jnz     loc_1800428D3
0x180042747  mov     [rsp+0FF0h+var_FA8], r12
0x18004274c  mov     [rsp+0FF0h+var_FA0], r12
0x180042751  mov     [rsp+0FF0h+var_F98], r12
0x180042756  lea     rcx, [rsp+0FF0h+var_FA8]
0x18004275b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180042760  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042764  mov     [rsp+0FF0h+var_FA0], rax
0x180042769  mov     [rsp+0FF0h+var_F98], rax
0x18004276e  lea     rax, [rsp+0FF0h+var_FA8]
0x180042773  mov     [rsp+0FF0h+pstmTemplate], rax; int
0x180042778  lea     r8, ?c_portraitAssetPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "PortraitAssetPath"
0x18004277f  lea     rdx, ?c_lockScreenCreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180042786  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18004278d  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180042792  mov     ebx, eax
  ... truncated ...
```
