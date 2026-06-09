# CortanaSharedExperienceManager::Show(HSTRING__ *,Windows::Internal::Shell::Experience::CortanaAppTransitionType)

- ea: `0x180331e40`
- end: `0x1803321c4`
- name: `?Show@CortanaSharedExperienceManager@@UEAAJPEAUHSTRING__@@W4CortanaAppTransitionType@Experience@Shell@Internal@Windows@@@Z`
- size: `900`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x1800b33c8`
- `0x180331e40`
- `0x1803321cc`
- `0x18033e7b8`
- `0x180356360`
- `0x1803f31c8`
- `0x1803f36d0`
- `0x1803f3728`
- `0x1803f4438`
- `0x1803f50f8`
- `0x1803fa1a4`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331f73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331fed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331ffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803320f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180332107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180332115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180332170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180332180`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033218e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331f73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331fed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180331ffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803320f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180332107`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180332115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180332170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180332180`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033218e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180331fd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033204a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033205c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180331fd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033204a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033205c`

## pseudocode

```c
__int64 __fastcall CortanaSharedExperienceManager::Show(__int64 a1, HSTRING a2, unsigned int a3)
{
  int v6; // eax
  int v7; // ecx
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, struct Windows::Internal::Shell::Experience::IShellExperiencePositioner **); // rbx
  int v14; // eax
  CortanaSharedExperienceManager *v15; // rcx
  int v16; // eax
  HSTRING v17; // rbx
  const unsigned __int16 *StringRawBuffer; // rdi
  CortanaSharedExperienceManager *v19; // rcx
  int CortanaEntryPointAndArgs; // eax
  int v21; // edi
  __int64 v22; // rdx
  int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v27; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v28; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::Internal::Shell::Experience::IShellExperiencePositioner *v29; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 length; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v31[2]; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v32; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v33[336]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  LODWORD(string) = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)(a1 + 496) + 64LL))(*(_QWORD *)(a1 + 496), &string);
  v7 = 0;
  if ( v6 >= 0 )
    v7 = (int)string;
  LODWORD(string) = v7;
  CortanaProactiveTelemetry::CortanaExperienceManager_CortanaViewState<enum CSingleViewShellExperience::ExperienceViewState>(&string);
  CortanaSharedExperienceManager::_CancelDeferredSuspensionTimer((CortanaSharedExperienceManager *)a1);
  v8 = *(__int64 **)(a1 + 424);
  v9 = *v8;
  if ( !*(_BYTE *)(a1 + 537) )
  {
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING))(v9 + 24))(v8, *(_QWORD *)(a1 + 504), a2);
    if ( v10 < 0 )
    {
      v11 = 435;
      goto LABEL_6;
    }
LABEL_9:
    v29 = 0;
    v12 = *(_QWORD *)(a1 + 424);
    v13 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::Shell::Experience::IShellExperiencePositioner **))(*(_QWORD *)v12 + 8LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v14 = v13(v12, &v29);
    v10 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanasharedexperiencemanager.cpp",
        (const char *)(unsigned int)v14,
        v24);
LABEL_22:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      return (unsigned int)v10;
    }
    WindowsDeleteString(0);
    string = 0;
    v16 = CortanaSharedExperienceManager::_NormalizeAndAddPositionerArgs(v15, a2, v29, &string);
    v10 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BA,
        (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanasharedexperiencemanager.cpp",
        (const char *)(unsigned int)v16,
        v24);
      WindowsDeleteString(string);
      goto LABEL_22;
    }
    length = 0;
    v17 = string;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v32 = StringRawBuffer;
    v27 = 0;
    v28 = 0;
    WindowsDeleteString(0);
    v28 = 0;
    WindowsDeleteString(v27);
    v27 = 0;
    CortanaEntryPointAndArgs = CortanaSharedExperienceManager::_GetCortanaEntryPointAndArgs(
                                 v19,
                                 StringRawBuffer,
                                 length,
                                 &v27,
                                 &v28);
    if ( CortanaEntryPointAndArgs < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanasharedexperiencemanager.cpp",
        (const char *)(unsigned int)CortanaEntryPointAndArgs,
        v25);
    string = (HSTRING)WindowsGetStringRawBuffer(v28, 0);
    v31[1] = WindowsGetStringRawBuffer(v27, 0);
    CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::Start<unsigned short const *,unsigned short const *>((CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked *)v33);
    CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::CortanaExperienceManager_ShowDocked_LaunchArgs<unsigned short const * &>(
      v33,
      &v32);
    v31[0] = 0;
    if ( (int)Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperiencePositioner>::As<TwinUI::Cortana::ICortanaExperienceView>(
                &v29,
                v31) < 0 )
    {
      v21 = (*(__int64 (__fastcall **)(struct Windows::Internal::Shell::Experience::IShellExperiencePositioner *, _QWORD, HSTRING, _QWORD))(*(_QWORD *)v29 + 80LL))(
              v29,
              *(_QWORD *)(a1 + 504),
              v17,
              0);
      if ( v21 < 0 )
      {
        v22 = 461;
        goto LABEL_18;
      }
    }
    else
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _QWORD))(*(_QWORD *)v31[0] + 80LL))(v31[0], v17, a3);
      if ( v21 < 0 )
      {
        v22 = 457;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanasharedexperiencemanager.cpp",
          (const char *)(unsigned int)v21,
          v25);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
        CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::~CortanaExperienceManager_ShowDocked((CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked *)v33);
        WindowsDeleteString(v28);
        v28 = 0;
        WindowsDeleteString(v27);
        v27 = 0;
        WindowsDeleteString(v17);
        v10 = v21;
        goto LABEL_22;
      }
    }
    wil::ActivityBase<CortanaProactiveLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
    CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::~CortanaExperienceManager_ShowDocked((CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked *)v33);
    WindowsDeleteString(v28);
    v28 = 0;
    WindowsDeleteString(v27);
    v27 = 0;
    WindowsDeleteString(v17);
    v10 = 0;
    goto LABEL_22;
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v9 + 32))(v8, 1, *(_QWORD *)(a1 + 504));
  if ( v10 >= 0 )
    goto LABEL_9;
  v11 = 431;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\cortanasharedexperiencemanager.cpp",
    (const char *)(unsigned int)v10,
    v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180331e40  push    rbp
0x180331e42  push    rbx
0x180331e43  push    rsi
0x180331e44  push    rdi
0x180331e45  push    r12
0x180331e47  push    r14
0x180331e49  push    r15
0x180331e4b  lea     rbp, [rsp-0D0h]
0x180331e53  sub     rsp, 1D0h
0x180331e5a  mov     rax, cs:__security_cookie
0x180331e61  xor     rax, rsp
0x180331e64  mov     [rbp+100h+var_40], rax
0x180331e6b  mov     r15d, r8d
0x180331e6e  mov     r14, rdx
0x180331e71  mov     rsi, rcx
0x180331e74  xor     r12d, r12d
0x180331e77  mov     dword ptr [rsp+200h+string], r12d
0x180331e7c  mov     rcx, [rcx+1F0h]
0x180331e83  mov     rax, [rcx]
0x180331e86  lea     rdx, [rsp+200h+string]
0x180331e8b  mov     rax, [rax+40h]
0x180331e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180331e94  mov     ecx, r12d
0x180331e97  test    eax, eax
0x180331e99  cmovns  ecx, dword ptr [rsp+200h+string]
0x180331e9e  mov     dword ptr [rsp+200h+string], ecx
0x180331ea2  lea     rcx, [rsp+200h+string]
0x180331ea7  call    ??$CortanaExperienceManager_CortanaViewState@W4ExperienceViewState@CSingleViewShellExperience@@@CortanaProactiveTelemetry@@SAX$$QEAW4ExperienceViewState@CSingleViewShellExperience@@@Z; CortanaProactiveTelemetry::CortanaExperienceManager_CortanaViewState<CSingleViewShellExperience::ExperienceViewState>(CSingleViewShellExperience::ExperienceViewState &&)
0x180331eac  mov     rcx, rsi; this
0x180331eaf  call    ?_CancelDeferredSuspensionTimer@CortanaSharedExperienceManager@@AEAAJXZ; CortanaSharedExperienceManager::_CancelDeferredSuspensionTimer(void)
0x180331eb4  mov     rcx, [rsi+1A8h]
0x180331ebb  mov     rax, [rcx]
0x180331ebe  mov     rdx, [rsi+1F8h]
0x180331ec5  cmp     [rsi+219h], r12b
0x180331ecc  jz      short loc_180331F05
0x180331ece  mov     r8, rdx
0x180331ed1  lea     edx, [r12+1]
0x180331ed6  mov     rax, [rax+20h]
0x180331eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180331edf  mov     ebx, eax
0x180331ee1  test    eax, eax
0x180331ee3  jns     short loc_180331F1E
0x180331ee5  mov     edx, 1AFh; void *
0x180331eea  lea     r8, aPcshellTwinuiE_11; "pcshell\\twinui\\experiencemanagers\\li"...
0x180331ef1  mov     r9d, ebx; char *
0x180331ef4  mov     rcx, [rbp+108h]; this
0x180331efb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180331f00  jmp     loc_1803321A1
0x180331f05  mov     r8, r14
0x180331f08  mov     rax, [rax+18h]
0x180331f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180331f11  mov     ebx, eax
0x180331f13  test    eax, eax
0x180331f15  jns     short loc_180331F1E
0x180331f17  mov     edx, 1B3h
0x180331f1c  jmp     short loc_180331EEA
0x180331f1e  mov     [rsp+200h+var_1B8], r12
0x180331f23  mov     rdi, [rsi+1A8h]
0x180331f2a  mov     rax, [rdi]
0x180331f2d  mov     rbx, [rax+8]
0x180331f31  lea     rcx, [rsp+200h+var_1B8]
0x180331f36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180331f3b  lea     rdx, [rsp+200h+var_1B8]
0x180331f40  mov     rcx, rdi
0x180331f43  mov     rax, rbx
0x180331f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180331f4b  mov     ebx, eax
0x180331f4d  test    eax, eax
0x180331f4f  jns     short loc_180331F71
0x180331f51  mov     rcx, [rbp+108h]; this
0x180331f58  mov     r9d, eax; char *
0x180331f5b  lea     r8, aPcshellTwinuiE_11; "pcshell\\twinui\\experiencemanagers\\li"...
0x180331f62  mov     edx, 1B7h; void *
0x180331f67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180331f6c  jmp     loc_180332197
0x180331f71  xor     ecx, ecx; string
0x180331f73  call    cs:__imp_WindowsDeleteString
0x180331f79  mov     [rsp+200h+string], r12
0x180331f7e  lea     r9, [rsp+200h+string]; HSTRING *
0x180331f83  mov     r8, [rsp+200h+var_1B8]; struct Windows::Internal::Shell::Experience::IShellExperiencePositioner *
0x180331f88  mov     rdx, r14; HSTRING
0x180331f8b  call    ?_NormalizeAndAddPositionerArgs@CortanaSharedExperienceManager@@AEAAJPEAUHSTRING__@@PEAUIShellExperiencePositioner@Experience@Shell@Internal@Windows@@PEAPEAU2@@Z; CortanaSharedExperienceManager::_NormalizeAndAddPositionerArgs(HSTRING__ *,Windows::Internal::Shell::Experience::IShellExperiencePositioner *,HSTRING__ * *)
0x180331f90  mov     ebx, eax
0x180331f92  test    eax, eax
0x180331f94  jns     short loc_180331FC1
0x180331f96  mov     rcx, [rbp+108h]; this
0x180331f9d  mov     r9d, eax; char *
0x180331fa0  lea     r8, aPcshellTwinuiE_11; "pcshell\\twinui\\experiencemanagers\\li"...
0x180331fa7  mov     edx, 1BAh; void *
0x180331fac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180331fb1  mov     rcx, [rsp+200h+string]; string
0x180331fb6  call    cs:__imp_WindowsDeleteString
0x180331fbc  jmp     loc_180332197
0x180331fc1  mov     [rsp+200h+length], r12d
0x180331fc6  lea     rdx, [rsp+200h+length]; length
0x180331fcb  mov     rbx, [rsp+200h+string]
0x180331fd0  mov     rcx, rbx; string
0x180331fd3  call    cs:__imp_WindowsGetStringRawBuffer
0x180331fd9  mov     rdi, rax
0x180331fdc  mov     [rsp+200h+var_198], rax
0x180331fe1  mov     [rsp+200h+var_1C8], r12
0x180331fe6  mov     [rsp+200h+var_1C0], r12
0x180331feb  xor     ecx, ecx; string
0x180331fed  call    cs:__imp_WindowsDeleteString
0x180331ff3  mov     [rsp+200h+var_1C0], r12
0x180331ff8  mov     rcx, [rsp+200h+var_1C8]; string
0x180331ffd  call    cs:__imp_WindowsDeleteString
0x180332003  mov     [rsp+200h+var_1C8], r12
0x180332008  lea     rax, [rsp+200h+var_1C0]
0x18033200d  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x180332012  lea     r9, [rsp+200h+var_1C8]; HSTRING *
0x180332017  mov     r8d, [rsp+200h+length]; unsigned int
0x18033201c  mov     rdx, rdi; unsigned __int16 *
0x18033201f  call    ?_GetCortanaEntryPointAndArgs@CortanaSharedExperienceManager@@AEAAJPEBGIPEAPEAUHSTRING__@@1@Z; CortanaSharedExperienceManager::_GetCortanaEntryPointAndArgs(ushort const *,uint,HSTRING__ * *,HSTRING__ * *)
0x180332024  test    eax, eax
0x180332026  jns     short loc_180332043
0x180332028  mov     rcx, [rbp+108h]; this
0x18033202f  mov     r9d, eax; char *
0x180332032  lea     r8, aPcshellTwinuiE_11; "pcshell\\twinui\\experiencemanagers\\li"...
0x180332039  mov     edx, 1C1h; void *
0x18033203e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180332043  xor     edx, edx; length
0x180332045  mov     rcx, [rsp+200h+var_1C0]; string
0x18033204a  call    cs:__imp_WindowsGetStringRawBuffer
0x180332050  mov     [rsp+200h+string], rax
0x180332055  xor     edx, edx; length
0x180332057  mov     rcx, [rsp+200h+var_1C8]; string
0x18033205c  call    cs:__imp_WindowsGetStringRawBuffer
0x180332062  mov     [rsp+200h+var_1A0], rax
0x180332067  lea     r8, [rsp+200h+string]
0x18033206c  lea     rdx, [rsp+200h+var_1A0]
0x180332071  lea     rcx, [rsp+200h+var_190]; this
0x180332076  call    ??$Start@PEBGPEBG@CortanaExperienceManager_ShowDocked@CortanaProactiveTelemetry@@SA?AV01@$$QEAPEBG0@Z; CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::Start<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x18033207b  lea     rdx, [rsp+200h+var_198]
0x180332080  lea     rcx, [rsp+200h+var_190]
0x180332085  call    ??$CortanaExperienceManager_ShowDocked_LaunchArgs@AEAPEBG@CortanaExperienceManager_ShowDocked@CortanaProactiveTelemetry@@QEAAXAEAPEBG@Z; CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::CortanaExperienceManager_ShowDocked_LaunchArgs<ushort const * &>(ushort const * &)
0x18033208a  mov     [rsp+200h+var_1A8], r12
0x18033208f  lea     rdx, [rsp+200h+var_1A8]
0x180332094  lea     rcx, [rsp+200h+var_1B8]
0x180332099  call    ??$As@VICortanaExperienceView@Cortana@TwinUI@@@?$ComPtr@UIShellExperiencePositioner@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@VICortanaExperienceView@Cortana@TwinUI@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperiencePositioner>::As<TwinUI::Cortana::ICortanaExperienceView>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<TwinUI::Cortana::ICortanaExperienceView>>)
0x18033209e  test    eax, eax
0x1803320a0  js      short loc_18033211F
0x1803320a2  mov     rcx, [rsp+200h+var_1A8]
0x1803320a7  mov     rax, [rcx]
0x1803320aa  mov     r8d, r15d
0x1803320ad  mov     rdx, rbx
0x1803320b0  mov     rax, [rax+50h]
0x1803320b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803320b9  mov     edi, eax
0x1803320bb  test    eax, eax
0x1803320bd  jns     loc_18033214D
0x1803320c3  mov     edx, 1C9h; void *
0x1803320c8  lea     r8, aPcshellTwinuiE_11; "pcshell\\twinui\\experiencemanagers\\li"...
0x1803320cf  mov     r9d, edi; char *
0x1803320d2  mov     rcx, [rbp+108h]; this
0x1803320d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803320de  lea     rcx, [rsp+200h+var_1A8]
0x1803320e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803320e8  lea     rcx, [rsp+200h+var_190]; this
0x1803320ed  call    ??1CortanaExperienceManager_ShowDocked@CortanaProactiveTelemetry@@QEAA@XZ; CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::~CortanaExperienceManager_ShowDocked(void)
0x1803320f2  mov     rcx, [rsp+200h+var_1C0]; string
0x1803320f7  call    cs:__imp_WindowsDeleteString
0x1803320fd  mov     [rsp+200h+var_1C0], r12
0x180332102  mov     rcx, [rsp+200h+var_1C8]; string
0x180332107  call    cs:__imp_WindowsDeleteString
0x18033210d  mov     [rsp+200h+var_1C8], r12
0x180332112  mov     rcx, rbx; string
0x180332115  call    cs:__imp_WindowsDeleteString
0x18033211b  mov     ebx, edi
0x18033211d  jmp     short loc_180332197
0x18033211f  mov     rcx, [rsp+200h+var_1B8]
0x180332124  mov     rax, [rcx]
0x180332127  xor     r9d, r9d
0x18033212a  mov     r8, rbx
0x18033212d  mov     rdx, [rsi+1F8h]
0x180332134  mov     rax, [rax+50h]
0x180332138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033213d  mov     edi, eax
0x18033213f  test    eax, eax
0x180332141  jns     short loc_18033214D
0x180332143  mov     edx, 1CDh
0x180332148  jmp     loc_1803320C8
0x18033214d  lea     rcx, [rsp+200h+var_190]
0x180332152  call    ?Stop@?$ActivityBase@VCortanaProactiveLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CortanaProactiveLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180332157  lea     rcx, [rsp+200h+var_1A8]
0x18033215c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180332161  lea     rcx, [rsp+200h+var_190]; this
0x180332166  call    ??1CortanaExperienceManager_ShowDocked@CortanaProactiveTelemetry@@QEAA@XZ; CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::~CortanaExperienceManager_ShowDocked(void)
0x18033216b  mov     rcx, [rsp+200h+var_1C0]; string
0x180332170  call    cs:__imp_WindowsDeleteString
0x180332176  mov     [rsp+200h+var_1C0], r12
0x18033217b  mov     rcx, [rsp+200h+var_1C8]; string
0x180332180  call    cs:__imp_WindowsDeleteString
0x180332186  mov     [rsp+200h+var_1C8], r12
0x18033218b  mov     rcx, rbx; string
0x18033218e  call    cs:__imp_WindowsDeleteString
0x180332194  mov     ebx, r12d
0x180332197  lea     rcx, [rsp+200h+var_1B8]
0x18033219c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1803321a1  mov     eax, ebx
0x1803321a3  mov     rcx, [rbp+100h+var_40]
0x1803321aa  xor     rcx, rsp; StackCookie
0x1803321ad  call    __security_check_cookie
0x1803321b2  add     rsp, 1D0h
0x1803321b9  pop     r15
0x1803321bb  pop     r14
0x1803321bd  pop     r12
0x1803321bf  pop     rdi
0x1803321c0  pop     rsi
0x1803321c1  pop     rbx
0x1803321c2  pop     rbp
0x1803321c3  retn
```
