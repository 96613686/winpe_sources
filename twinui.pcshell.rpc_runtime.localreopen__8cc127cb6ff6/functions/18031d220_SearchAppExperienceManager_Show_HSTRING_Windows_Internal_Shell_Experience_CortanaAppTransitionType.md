# SearchAppExperienceManager::Show(HSTRING__ *,Windows::Internal::Shell::Experience::CortanaAppTransitionType)

- ea: `0x18031d220`
- end: `0x18031d4c3`
- name: `?Show@SearchAppExperienceManager@@UEAAJPEAUHSTRING__@@W4CortanaAppTransitionType@Experience@Shell@Internal@Windows@@@Z`
- size: `675`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path`

## callees

- `0x1800237c8`
- `0x180031c70`
- `0x1800b33c8`
- `0x18031d220`
- `0x18031d4cc`
- `0x18033e218`
- `0x180356360`
- `0x1803f36d0`
- `0x1803f3728`
- `0x1803f4438`
- `0x1803f50f8`
- `0x18041ff14`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d2da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d455`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d476`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d48a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d2da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d353`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d367`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d455`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d476`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d48a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18031d49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031d331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031d3b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031d3ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031d331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031d3b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18031d3ca`

## pseudocode

```c
__int64 __fastcall SearchAppExperienceManager::Show(__int64 a1, HSTRING a2, unsigned int a3)
{
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  unsigned int v9; // ebx
  SearchAppExperienceManager *v11; // rcx
  int v12; // eax
  unsigned int v13; // edi
  HSTRING v14; // rbx
  const unsigned __int16 *StringRawBuffer; // rdi
  SearchAppExperienceManager *v16; // rcx
  int CortanaEntryPointAndArgs; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v22; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 length; // [rsp+48h] [rbp-B8h] BYREF
  PCWSTR v25; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v26; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v27[336]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  LODWORD(string) = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)(a1 + 504) + 64LL))(*(_QWORD *)(a1 + 504), &string);
  v7 = 0;
  if ( v6 >= 0 )
    v7 = (int)string;
  LODWORD(string) = v7;
  CortanaProactiveTelemetry::CortanaExperienceManager_CortanaViewState<enum CSingleViewShellExperience::ExperienceViewState>(&string);
  SearchAppExperienceManager::_CancelDeferredSuspensionTimer((SearchAppExperienceManager *)a1);
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 424) + 72LL))(
         *(_QWORD *)(a1 + 424),
         *(_QWORD *)(a1 + 512),
         1);
  v9 = v8;
  if ( v8 >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    v12 = SearchAppExperienceManager::_NormalizeAndAddPositionerArgs(v11, a2, &string);
    v13 = v12;
    v14 = string;
    if ( v12 >= 0 )
    {
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v26 = StringRawBuffer;
      v22 = 0;
      v23 = 0;
      WindowsDeleteString(0);
      v23 = 0;
      WindowsDeleteString(v22);
      v22 = 0;
      CortanaEntryPointAndArgs = SearchAppExperienceManager::_GetCortanaEntryPointAndArgs(
                                   v16,
                                   StringRawBuffer,
                                   length,
                                   &v22,
                                   &v23);
      if ( CortanaEntryPointAndArgs < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B0,
          (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\searchappexperiencemanager.cpp",
          (const char *)(unsigned int)CortanaEntryPointAndArgs,
          v20);
      string = (HSTRING)WindowsGetStringRawBuffer(v23, 0);
      v25 = WindowsGetStringRawBuffer(v22, 0);
      CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::Start<unsigned short const *,unsigned short const *>((CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked *)v27);
      CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::CortanaExperienceManager_ShowDocked_LaunchArgs<unsigned short const * &>(
        v27,
        &v26);
      v18 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, _QWORD))(**(_QWORD **)(a1 + 432) + 80LL))(
              *(_QWORD *)(a1 + 432),
              v14,
              a3);
      v13 = v18;
      if ( v18 >= 0 )
      {
        wil::ActivityBase<CortanaProactiveLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v27);
        CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::~CortanaExperienceManager_ShowDocked((CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked *)v27);
        WindowsDeleteString(v23);
        v23 = 0;
        WindowsDeleteString(v22);
        v13 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\searchappexperiencemanager.cpp",
          (const char *)(unsigned int)v18,
          v20);
        CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::~CortanaExperienceManager_ShowDocked((CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked *)v27);
        WindowsDeleteString(v23);
        v23 = 0;
        WindowsDeleteString(v22);
      }
      v22 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\searchappexperiencemanager.cpp",
        (const char *)(unsigned int)v12,
        v19);
    }
    WindowsDeleteString(v14);
    return v13;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"pcshell\\twinui\\experiencemanagers\\lib\\searchappexperiencemanager.cpp",
      (const char *)(unsigned int)v8,
      v19);
    return v9;
  }
}

```

## disassembly

```asm
0x18031d220  push    rbp
0x18031d222  push    rbx
0x18031d223  push    rsi
0x18031d224  push    rdi
0x18031d225  push    r14
0x18031d227  lea     rbp, [rsp-0C0h]
0x18031d22f  sub     rsp, 1C0h
0x18031d236  mov     rax, cs:__security_cookie
0x18031d23d  xor     rax, rsp
0x18031d240  mov     [rbp+0E0h+var_30], rax
0x18031d247  mov     r14d, r8d
0x18031d24a  mov     rdi, rdx
0x18031d24d  mov     rsi, rcx
0x18031d250  mov     dword ptr [rsp+1E0h+string], 0
0x18031d258  mov     rcx, [rcx+1F8h]
0x18031d25f  mov     rax, [rcx]
0x18031d262  lea     rdx, [rsp+1E0h+string]
0x18031d267  mov     rax, [rax+40h]
0x18031d26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031d270  xor     ecx, ecx
0x18031d272  test    eax, eax
0x18031d274  cmovns  ecx, dword ptr [rsp+1E0h+string]
0x18031d279  mov     dword ptr [rsp+1E0h+string], ecx
0x18031d27d  lea     rcx, [rsp+1E0h+string]
0x18031d282  call    ??$CortanaExperienceManager_CortanaViewState@W4ExperienceViewState@CSingleViewShellExperience@@@CortanaProactiveTelemetry@@SAX$$QEAW4ExperienceViewState@CSingleViewShellExperience@@@Z; CortanaProactiveTelemetry::CortanaExperienceManager_CortanaViewState<CSingleViewShellExperience::ExperienceViewState>(CSingleViewShellExperience::ExperienceViewState &&)
0x18031d287  mov     rcx, rsi; this
0x18031d28a  call    ?_CancelDeferredSuspensionTimer@SearchAppExperienceManager@@AEAAJXZ; SearchAppExperienceManager::_CancelDeferredSuspensionTimer(void)
0x18031d28f  mov     rcx, [rsi+1A8h]
0x18031d296  mov     rax, [rcx]
0x18031d299  xor     r9d, r9d
0x18031d29c  lea     r8d, [r9+1]
0x18031d2a0  mov     rdx, [rsi+200h]
0x18031d2a7  mov     rax, [rax+48h]
0x18031d2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031d2b0  mov     ebx, eax
0x18031d2b2  test    eax, eax
0x18031d2b4  jns     short loc_18031D2D8
0x18031d2b6  mov     rcx, [rbp+0E8h]; this
0x18031d2bd  mov     r9d, eax; char *
0x18031d2c0  lea     r8, aPcshellTwinuiE_0; "pcshell\\twinui\\experiencemanagers\\li"...
0x18031d2c7  mov     edx, 19Fh; void *
0x18031d2cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031d2d1  mov     eax, ebx
0x18031d2d3  jmp     loc_18031D4A6
0x18031d2d8  xor     ecx, ecx; string
0x18031d2da  call    cs:__imp_WindowsDeleteString
0x18031d2e0  mov     [rsp+1E0h+string], 0
0x18031d2e9  lea     r8, [rsp+1E0h+string]; HSTRING *
0x18031d2ee  mov     rdx, rdi; HSTRING
0x18031d2f1  call    ?_NormalizeAndAddPositionerArgs@SearchAppExperienceManager@@AEAAJPEAUHSTRING__@@PEAPEAU2@@Z; SearchAppExperienceManager::_NormalizeAndAddPositionerArgs(HSTRING__ *,HSTRING__ * *)
0x18031d2f6  mov     edi, eax
0x18031d2f8  mov     rbx, [rsp+1E0h+string]
0x18031d2fd  test    eax, eax
0x18031d2ff  jns     short loc_18031D321
0x18031d301  mov     rcx, [rbp+0E8h]; this
0x18031d308  mov     r9d, eax; char *
0x18031d30b  lea     r8, aPcshellTwinuiE_0; "pcshell\\twinui\\experiencemanagers\\li"...
0x18031d312  mov     edx, 1A9h; void *
0x18031d317  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031d31c  jmp     loc_18031D49B
0x18031d321  mov     [rsp+1E0h+length], 0
0x18031d329  lea     rdx, [rsp+1E0h+length]; length
0x18031d32e  mov     rcx, rbx; string
0x18031d331  call    cs:__imp_WindowsGetStringRawBuffer
0x18031d337  mov     rdi, rax
0x18031d33a  mov     [rsp+1E0h+var_188], rax
0x18031d33f  mov     [rsp+1E0h+var_1A8], 0
0x18031d348  mov     [rsp+1E0h+var_1A0], 0
0x18031d351  xor     ecx, ecx; string
0x18031d353  call    cs:__imp_WindowsDeleteString
0x18031d359  mov     [rsp+1E0h+var_1A0], 0
0x18031d362  mov     rcx, [rsp+1E0h+var_1A8]; string
0x18031d367  call    cs:__imp_WindowsDeleteString
0x18031d36d  mov     [rsp+1E0h+var_1A8], 0
0x18031d376  lea     rax, [rsp+1E0h+var_1A0]
0x18031d37b  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18031d380  lea     r9, [rsp+1E0h+var_1A8]; HSTRING *
0x18031d385  mov     r8d, [rsp+1E0h+length]; unsigned int
0x18031d38a  mov     rdx, rdi; unsigned __int16 *
0x18031d38d  call    ?_GetCortanaEntryPointAndArgs@SearchAppExperienceManager@@AEAAJPEBGIPEAPEAUHSTRING__@@1@Z; SearchAppExperienceManager::_GetCortanaEntryPointAndArgs(ushort const *,uint,HSTRING__ * *,HSTRING__ * *)
0x18031d392  test    eax, eax
0x18031d394  jns     short loc_18031D3B1
0x18031d396  mov     rcx, [rbp+0E8h]; this
0x18031d39d  mov     r9d, eax; char *
0x18031d3a0  lea     r8, aPcshellTwinuiE_0; "pcshell\\twinui\\experiencemanagers\\li"...
0x18031d3a7  mov     edx, 1B0h; void *
0x18031d3ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18031d3b1  xor     edx, edx; length
0x18031d3b3  mov     rcx, [rsp+1E0h+var_1A0]; string
0x18031d3b8  call    cs:__imp_WindowsGetStringRawBuffer
0x18031d3be  mov     [rsp+1E0h+string], rax
0x18031d3c3  xor     edx, edx; length
0x18031d3c5  mov     rcx, [rsp+1E0h+var_1A8]; string
0x18031d3ca  call    cs:__imp_WindowsGetStringRawBuffer
0x18031d3d0  mov     [rsp+1E0h+var_190], rax
0x18031d3d5  lea     r8, [rsp+1E0h+string]
0x18031d3da  lea     rdx, [rsp+1E0h+var_190]
0x18031d3df  lea     rcx, [rsp+1E0h+var_180]; this
0x18031d3e4  call    ??$Start@PEBGPEBG@CortanaExperienceManager_ShowDocked@CortanaProactiveTelemetry@@SA?AV01@$$QEAPEBG0@Z; CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::Start<ushort const *,ushort const *>(ushort const * &&,ushort const * &&)
0x18031d3e9  lea     rdx, [rsp+1E0h+var_188]
0x18031d3ee  lea     rcx, [rsp+1E0h+var_180]
0x18031d3f3  call    ??$CortanaExperienceManager_ShowDocked_LaunchArgs@AEAPEBG@CortanaExperienceManager_ShowDocked@CortanaProactiveTelemetry@@QEAAXAEAPEBG@Z; CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::CortanaExperienceManager_ShowDocked_LaunchArgs<ushort const * &>(ushort const * &)
0x18031d3f8  mov     rcx, [rsi+1B0h]
0x18031d3ff  mov     rax, [rcx]
0x18031d402  mov     r8d, r14d
0x18031d405  mov     rdx, rbx
0x18031d408  mov     rax, [rax+50h]
0x18031d40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18031d411  mov     edi, eax
0x18031d413  test    eax, eax
0x18031d415  jns     short loc_18031D45D
0x18031d417  mov     rcx, [rbp+0E8h]; this
0x18031d41e  mov     r9d, eax; char *
0x18031d421  lea     r8, aPcshellTwinuiE_0; "pcshell\\twinui\\experiencemanagers\\li"...
0x18031d428  mov     edx, 1B5h; void *
0x18031d42d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18031d432  lea     rcx, [rsp+1E0h+var_180]; this
0x18031d437  call    ??1CortanaExperienceManager_ShowDocked@CortanaProactiveTelemetry@@QEAA@XZ; CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::~CortanaExperienceManager_ShowDocked(void)
0x18031d43c  mov     rcx, [rsp+1E0h+var_1A0]; string
0x18031d441  call    cs:__imp_WindowsDeleteString
0x18031d447  mov     [rsp+1E0h+var_1A0], 0
0x18031d450  mov     rcx, [rsp+1E0h+var_1A8]; string
0x18031d455  call    cs:__imp_WindowsDeleteString
0x18031d45b  jmp     short loc_18031D492
0x18031d45d  lea     rcx, [rsp+1E0h+var_180]
0x18031d462  call    ?Stop@?$ActivityBase@VCortanaProactiveLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CortanaProactiveLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18031d467  lea     rcx, [rsp+1E0h+var_180]; this
0x18031d46c  call    ??1CortanaExperienceManager_ShowDocked@CortanaProactiveTelemetry@@QEAA@XZ; CortanaProactiveTelemetry::CortanaExperienceManager_ShowDocked::~CortanaExperienceManager_ShowDocked(void)
0x18031d471  mov     rcx, [rsp+1E0h+var_1A0]; string
0x18031d476  call    cs:__imp_WindowsDeleteString
0x18031d47c  mov     [rsp+1E0h+var_1A0], 0
0x18031d485  mov     rcx, [rsp+1E0h+var_1A8]; string
0x18031d48a  call    cs:__imp_WindowsDeleteString
0x18031d490  xor     edi, edi
0x18031d492  mov     [rsp+1E0h+var_1A8], 0
0x18031d49b  mov     rcx, rbx; string
0x18031d49e  call    cs:__imp_WindowsDeleteString
0x18031d4a4  mov     eax, edi
0x18031d4a6  mov     rcx, [rbp+0E0h+var_30]
0x18031d4ad  xor     rcx, rsp; StackCookie
0x18031d4b0  call    __security_check_cookie
0x18031d4b5  add     rsp, 1C0h
0x18031d4bc  pop     r14
0x18031d4be  pop     rdi
0x18031d4bf  pop     rsi
0x18031d4c0  pop     rbx
0x18031d4c1  pop     rbp
0x18031d4c2  retn
```
