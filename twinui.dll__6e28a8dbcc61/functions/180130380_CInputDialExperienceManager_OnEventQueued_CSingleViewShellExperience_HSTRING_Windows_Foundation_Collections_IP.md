# CInputDialExperienceManager::OnEventQueued(CSingleViewShellExperience *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x180130380`
- end: `0x1801307d1`
- name: `?OnEventQueued@CInputDialExperienceManager@@EEAAJPEAVCSingleViewShellExperience@@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `1105`
- prototype: `int(CInputDialExperienceManager *__hidden this, struct CSingleViewShellExperience *, HSTRING, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180008acc`
- `0x18000cf94`
- `0x18003c5e4`
- `0x18003c898`
- `0x180040698`
- `0x180040b18`
- `0x180052980`
- `0x18006d698`
- `0x18008c6b0`
- `0x1800ead54`
- `0x1800f96d4`
- `0x180130380`
- `0x1801307d8`
- `0x180130878`
- `0x18013d330`
- `0x1801fbc04`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801306be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013076c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180130789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801307a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801306be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013076c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180130789`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801307a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801303f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013073f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801303f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013073f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18013074b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18013074b`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CInputDialExperienceManager::OnEventQueued(
        CInputDialExperienceManager *this,
        ExperienceManagerUtils **a2,
        Microsoft::WRL::Wrappers::Details *a3,
        struct Windows::Foundation::Collections::IPropertySet *a4)
{
  int v8; // eax
  __int64 v9; // rax
  HSTRING v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  HSTRING v13; // r8
  __int64 v14; // rax
  HSTRING v15; // r8
  __int64 v16; // rax
  HSTRING v17; // r8
  __int64 v18; // rax
  int v19; // eax
  char v20; // al
  __int64 v21; // rax
  HSTRING v22; // r8
  __int64 v23; // rax
  int v24; // eax
  char v25; // al
  __int64 v26; // rax
  HSTRING v27; // r8
  __int64 v28; // rax
  int v29; // eax
  char v30; // al
  HSTRING *v31; // rcx
  __int64 v32; // rax
  HSTRING v33; // r8
  __int64 v34; // rax
  int v35; // eax
  HSTRING v36; // r8
  unsigned int LastError; // ebx
  __int64 v38; // r9
  __int64 v39; // rdx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v40; // rdx
  HWND v41; // rbx
  const WCHAR *v42; // rax
  const char *v43; // r9
  int v45; // [rsp+20h] [rbp-60h]
  int StringRawBuffer; // [rsp+20h] [rbp-60h]
  HSTRING v47; // [rsp+30h] [rbp-50h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v48; // [rsp+38h] [rbp-48h] BYREF
  HSTRING v49; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v51[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v49 = (HSTRING)a3;
  string = 0;
  v8 = Microsoft::WRL::Wrappers::HString::Set(&string, &v49);
  if ( v8 >= 0 )
  {
    StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
    InputDial::InputDialTraceProvider::Info(
      "shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
      "na",
      0x38Au,
      "OnEventQueued: %ws");
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x388,
      (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
      (const char *)(unsigned int)v8,
      v45);
  }
  v9 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803E1B10);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v9 + 24), v10) )
  {
    v11 = 11;
LABEL_10:
    InputDialMenuStateModel::ProcessEvent(*((_QWORD *)this + 37), v11, 0);
LABEL_45:
    LastError = 0;
    goto LABEL_46;
  }
  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803E1B40);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v12 + 24), v13) )
  {
    v11 = 12;
    goto LABEL_10;
  }
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803E1B48);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v14 + 24), v15) )
  {
    v11 = 13;
    goto LABEL_10;
  }
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803E1B30);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v16 + 24), v17) )
  {
    v48 = a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
    LODWORD(v47) = 0;
    v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803B5598);
    v19 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v48,
            *(HSTRING *)(v18 + 24));
    if ( v19 >= 0 )
    {
      v20 = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x39D,
        (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
        (const char *)(unsigned int)v19,
        StringRawBuffer);
      v20 = 0;
    }
    if ( v20 )
    {
      v49 = (HSTRING)(unsigned int)v47;
      InputDialMenuStateModel::ProcessEvent(*((_QWORD *)this + 37), 16, &v49);
    }
    goto LABEL_43;
  }
  v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803E1B28);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v21 + 24), v22) )
  {
    v48 = a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
    LODWORD(v47) = 0;
    v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803B5598);
    v24 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v48,
            *(HSTRING *)(v23 + 24));
    if ( v24 >= 0 )
    {
      v25 = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A8,
        (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
        (const char *)(unsigned int)v24,
        StringRawBuffer);
      v25 = 0;
    }
    if ( v25 )
    {
      v49 = (HSTRING)(unsigned int)v47;
      InputDialMenuStateModel::ProcessEvent(*((_QWORD *)this + 37), 17, &v49);
    }
    goto LABEL_43;
  }
  v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803E1B58);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v26 + 24), v27) )
  {
    v47 = (HSTRING)a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v47);
    v48 = 0;
    v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, &off_1803B55A0);
    v29 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<Windows::Foundation::Point>(
            (Windows::Internal::ShellHelpers::PropertySetHelper *)&v47,
            *(HSTRING *)(v28 + 24));
    if ( v29 >= 0 )
    {
      v30 = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3B5,
        (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
        (const char *)(unsigned int)v29,
        StringRawBuffer);
      v30 = 0;
    }
    if ( v30 )
    {
      *((_DWORD *)this + 68) = (int)*(float *)&v48;
      *((_DWORD *)this + 69) = (int)*((float *)&v48 + 1);
    }
    v31 = &v47;
    goto LABEL_44;
  }
  v32 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803E1B50);
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v32 + 24), v33) )
    goto LABEL_45;
  v48 = a4;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v48);
  WindowsDeleteString(0);
  v47 = 0;
  v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v51, off_1803E1AE0);
  v35 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
          (Windows::Internal::ShellHelpers::PropertySetHelper *)&v48,
          *(HSTRING *)(v34 + 24));
  LastError = v35;
  if ( v35 >= 0 )
  {
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)v47,
                         0,
                         v36) )
    {
      v41 = ExperienceManagerUtils::WindowFromViewWrapper(a2[3], v40);
      if ( !v41 )
      {
        LastError = -2147023728;
        v38 = 2147943568LL;
        v39 = 963;
        goto LABEL_38;
      }
      v42 = WindowsGetStringRawBuffer(v47, 0);
      if ( !SetWindowTextW(v41, v42) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x3C4,
                      (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
                      v43);
        goto LABEL_41;
      }
    }
    WindowsDeleteString(v47);
    v47 = 0;
LABEL_43:
    v31 = (HSTRING *)&v48;
LABEL_44:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
    goto LABEL_45;
  }
  v38 = (unsigned int)v35;
  v39 = 959;
LABEL_38:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v39,
    (unsigned int)"shell\\twinui\\inputdial\\experiencemanager\\inputdialexperiencemanager.cpp",
    (const char *)v38,
    StringRawBuffer);
LABEL_41:
  WindowsDeleteString(v47);
  v47 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
LABEL_46:
  WindowsDeleteString(string);
  return LastError;
}

```

## disassembly

```asm
0x180130380  mov     [rsp-28h+arg_18], rbx
0x180130385  push    rbp
0x180130386  push    rsi
0x180130387  push    rdi
0x180130388  push    r14
0x18013038a  push    r15
0x18013038c  mov     rbp, rsp
0x18013038f  sub     rsp, 80h
0x180130396  mov     rax, cs:__security_cookie
0x18013039d  xor     rax, rsp
0x1801303a0  mov     [rbp+var_10], rax
0x1801303a4  mov     r14, r9
0x1801303a7  mov     rsi, r8
0x1801303aa  mov     r15, rdx
0x1801303ad  mov     rbx, rcx
0x1801303b0  mov     [rbp+var_40], r8
0x1801303b4  mov     [rbp+string], 0
0x1801303bc  lea     rdx, [rbp+var_40]; HSTRING *
0x1801303c0  lea     rcx, [rbp+string]; newString
0x1801303c4  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1801303c9  mov     rcx, [rbp+28h]; this
0x1801303cd  test    eax, eax
0x1801303cf  jns     short loc_1801303EA
0x1801303d1  mov     r9d, eax; char *
0x1801303d4  lea     rdi, aShellTwinuiInp_2; "shell\\twinui\\inputdial\\experienceman"...
0x1801303db  mov     r8, rdi; unsigned int
0x1801303de  mov     edx, 388h; void *
0x1801303e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801303e8  jmp     short loc_18013041E
0x1801303ea  xor     edx, edx; length
0x1801303ec  mov     rcx, [rbp+string]; string
0x1801303f0  call    cs:__imp_WindowsGetStringRawBuffer
0x1801303f6  mov     qword ptr [rsp+80h+var_60], rax; int
0x1801303fb  lea     r9, aOneventqueuedW; "OnEventQueued: %ws"
0x180130402  mov     r8d, 38Ah; unsigned int
0x180130408  lea     rdx, aNa; "na"
0x18013040f  lea     rdi, aShellTwinuiInp_2; "shell\\twinui\\inputdial\\experienceman"...
0x180130416  mov     rcx, rdi; char *
0x180130419  call    ?Info@InputDialTraceProvider@InputDial@@SAXPEBD0I0ZZ; InputDial::InputDialTraceProvider::Info(char const *,char const *,uint,char const *,...)
0x18013041e  lea     rdx, off_1803E1B10; "AnimateInCompleted"
0x180130425  lea     rcx, [rbp+var_30]
0x180130429  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18013042e  mov     rdx, [rax+18h]; HSTRING
0x180130432  mov     rcx, rsi; this
0x180130435  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18013043a  test    eax, eax
0x18013043c  jnz     short loc_180130443
0x18013043e  lea     edx, [rax+0Bh]
0x180130441  jmp     short loc_18013048B
0x180130443  lea     rdx, off_1803E1B40; "AnimateInPreviewMenuCompleted"
0x18013044a  lea     rcx, [rbp+var_30]
0x18013044e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180130453  mov     rdx, [rax+18h]; HSTRING
0x180130457  mov     rcx, rsi; this
0x18013045a  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18013045f  test    eax, eax
0x180130461  jnz     short loc_180130468
0x180130463  lea     edx, [rax+0Ch]
0x180130466  jmp     short loc_18013048B
0x180130468  lea     rdx, off_1803E1B48; "AnimateOutCompleted"
0x18013046f  lea     rcx, [rbp+var_30]
0x180130473  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180130478  mov     rdx, [rax+18h]; HSTRING
0x18013047c  mov     rcx, rsi; this
0x18013047f  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180130484  test    eax, eax
0x180130486  jnz     short loc_18013049F
0x180130488  lea     edx, [rax+0Dh]
0x18013048b  xor     r8d, r8d
0x18013048e  mov     rcx, [rbx+128h]
0x180130495  call    ?ProcessEvent@InputDialMenuStateModel@@QEAAJW4EventType@@PEATEventData@@@Z; InputDialMenuStateModel::ProcessEvent(EventType,EventData *)
0x18013049a  jmp     loc_1801307A0
0x18013049f  lea     rdx, off_1803E1B30; "ItemClickDown"
0x1801304a6  lea     rcx, [rbp+var_30]
0x1801304aa  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801304af  mov     rdx, [rax+18h]; HSTRING
0x1801304b3  mov     rcx, rsi; this
0x1801304b6  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1801304bb  test    eax, eax
0x1801304bd  jnz     loc_180130545
0x1801304c3  mov     [rbp+var_48], r14
0x1801304c7  lea     rcx, [rbp+var_48]
0x1801304cb  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1801304d0  nop
0x1801304d1  mov     dword ptr [rbp+var_50], 0
0x1801304d8  lea     rdx, off_1803B5598; "Int32Value"
0x1801304df  lea     rcx, [rbp+var_30]
0x1801304e3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801304e8  nop
0x1801304e9  lea     r9, [rbp+var_50]
0x1801304ed  mov     rdx, [rax+18h]; HSTRING
0x1801304f1  lea     rcx, [rbp+var_48]; this
0x1801304f5  call    ??$GetValue@H@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAH@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(int *),int *)
0x1801304fa  mov     rcx, [rbp+28h]; this
0x1801304fe  test    eax, eax
0x180130500  jns     short loc_180130516
0x180130502  mov     r9d, eax; char *
0x180130505  mov     r8, rdi; unsigned int
0x180130508  mov     edx, 39Dh; void *
0x18013050d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180130512  xor     al, al
0x180130514  jmp     short loc_180130518
0x180130516  mov     al, 1
0x180130518  test    al, al
0x18013051a  jz      short loc_180130540
0x18013051c  mov     [rbp+var_40], 0
0x180130524  mov     eax, dword ptr [rbp+var_50]
0x180130527  mov     dword ptr [rbp+var_40], eax
0x18013052a  lea     r8, [rbp+var_40]
0x18013052e  mov     edx, 10h
0x180130533  mov     rcx, [rbx+128h]
0x18013053a  call    ?ProcessEvent@InputDialMenuStateModel@@QEAAJW4EventType@@PEATEventData@@@Z; InputDialMenuStateModel::ProcessEvent(EventType,EventData *)
0x18013053f  nop
0x180130540  jmp     loc_180130797
0x180130545  lea     rdx, off_1803E1B28; "ItemClickUp"
0x18013054c  lea     rcx, [rbp+var_30]
0x180130550  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180130555  mov     rdx, [rax+18h]; HSTRING
0x180130559  mov     rcx, rsi; this
0x18013055c  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180130561  test    eax, eax
0x180130563  jnz     loc_1801305EB
0x180130569  mov     [rbp+var_48], r14
0x18013056d  lea     rcx, [rbp+var_48]
0x180130571  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180130576  nop
0x180130577  mov     dword ptr [rbp+var_50], 0
0x18013057e  lea     rdx, off_1803B5598; "Int32Value"
0x180130585  lea     rcx, [rbp+var_30]
0x180130589  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18013058e  nop
0x18013058f  lea     r9, [rbp+var_50]
0x180130593  mov     rdx, [rax+18h]; HSTRING
0x180130597  lea     rcx, [rbp+var_48]; this
0x18013059b  call    ??$GetValue@H@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAH@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(int *),int *)
0x1801305a0  mov     rcx, [rbp+28h]; this
0x1801305a4  test    eax, eax
0x1801305a6  jns     short loc_1801305BC
0x1801305a8  mov     r9d, eax; char *
0x1801305ab  mov     r8, rdi; unsigned int
0x1801305ae  mov     edx, 3A8h; void *
0x1801305b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801305b8  xor     al, al
0x1801305ba  jmp     short loc_1801305BE
0x1801305bc  mov     al, 1
0x1801305be  test    al, al
0x1801305c0  jz      short loc_1801305E6
0x1801305c2  mov     [rbp+var_40], 0
0x1801305ca  mov     eax, dword ptr [rbp+var_50]
0x1801305cd  mov     dword ptr [rbp+var_40], eax
0x1801305d0  lea     r8, [rbp+var_40]
0x1801305d4  mov     edx, 11h
0x1801305d9  mov     rcx, [rbx+128h]
0x1801305e0  call    ?ProcessEvent@InputDialMenuStateModel@@QEAAJW4EventType@@PEATEventData@@@Z; InputDialMenuStateModel::ProcessEvent(EventType,EventData *)
0x1801305e5  nop
0x1801305e6  jmp     loc_180130797
0x1801305eb  lea     rdx, off_1803E1B58; "WindowPositionChanged"
0x1801305f2  lea     rcx, [rbp+var_30]
0x1801305f6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801305fb  mov     rdx, [rax+18h]; HSTRING
0x1801305ff  mov     rcx, rsi; this
0x180130602  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180130607  test    eax, eax
0x180130609  jnz     short loc_180130682
0x18013060b  mov     [rbp+var_50], r14
0x18013060f  lea     rcx, [rbp+var_50]
0x180130613  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180130618  nop
0x180130619  xor     eax, eax
0x18013061b  mov     [rbp+var_48], rax
0x18013061f  lea     rdx, off_1803B55A0; "WindowPosition_Param"
0x180130626  lea     rcx, [rbp+var_30]
0x18013062a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18013062f  nop
0x180130630  lea     r9, [rbp+var_48]
0x180130634  mov     rdx, [rax+18h]; HSTRING
0x180130638  lea     rcx, [rbp+var_50]; this
0x18013063c  call    ??$GetValue@UPoint@Foundation@Windows@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAUPoint@63@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<Windows::Foundation::Point>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(Windows::Foundation::Point *),Windows::Foundation::Point *)
0x180130641  mov     rcx, [rbp+28h]; this
0x180130645  test    eax, eax
0x180130647  jns     short loc_18013065D
0x180130649  mov     r9d, eax; char *
0x18013064c  mov     r8, rdi; unsigned int
0x18013064f  mov     edx, 3B5h; void *
0x180130654  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180130659  xor     al, al
0x18013065b  jmp     short loc_18013065F
0x18013065d  mov     al, 1
0x18013065f  test    al, al
0x180130661  jz      short loc_180130679
0x180130663  cvttss2si eax, dword ptr [rbp+var_48]
0x180130668  mov     [rbx+110h], eax
0x18013066e  cvttss2si eax, dword ptr [rbp+var_48+4]
0x180130673  mov     [rbx+114h], eax
0x180130679  lea     rcx, [rbp+var_50]
0x18013067d  jmp     loc_18013079B
0x180130682  lea     rdx, off_1803E1B50; "NotifyWindowName"
0x180130689  lea     rcx, [rbp+var_30]
0x18013068d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180130692  mov     rdx, [rax+18h]; HSTRING
0x180130696  mov     rcx, rsi; this
0x180130699  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18013069e  test    eax, eax
0x1801306a0  jnz     loc_1801307A0
0x1801306a6  mov     [rbp+var_48], r14
0x1801306aa  lea     rcx, [rbp+var_48]
0x1801306ae  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1801306b3  nop
0x1801306b4  mov     [rbp+var_50], 0
0x1801306bc  xor     ecx, ecx; string
0x1801306be  call    cs:__imp_WindowsDeleteString
0x1801306c4  mov     [rbp+var_50], 0
0x1801306cc  lea     rdx, off_1803E1AE0; "TextContent"
0x1801306d3  lea     rcx, [rbp+var_30]
0x1801306d7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801306dc  nop
0x1801306dd  lea     r9, [rbp+var_50]
0x1801306e1  mov     rdx, [rax+18h]; HSTRING
0x1801306e5  lea     rcx, [rbp+var_48]; this
0x1801306e9  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x1801306ee  mov     ebx, eax
0x1801306f0  test    eax, eax
0x1801306f2  jns     short loc_1801306FE
0x1801306f4  mov     r9d, eax
0x1801306f7  mov     edx, 3BFh
0x1801306fc  jmp     short loc_18013072B
0x1801306fe  xor     edx, edx; HSTRING
0x180130700  mov     rcx, [rbp+var_50]; this
0x180130704  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180130709  test    eax, eax
0x18013070b  jz      short loc_180130785
0x18013070d  mov     rcx, [r15+18h]; this
0x180130711  call    ?WindowFromViewWrapper@ExperienceManagerUtils@@YAPEAUHWND__@@PEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; ExperienceManagerUtils::WindowFromViewWrapper(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x180130716  mov     rbx, rax
0x180130719  test    rax, rax
0x18013071c  jnz     short loc_180130739
0x18013071e  mov     ebx, 80070490h
0x180130723  mov     r9d, ebx; char *
0x180130726  mov     edx, 3C3h; void *
0x18013072b  mov     r8, rdi; unsigned int
0x18013072e  mov     rcx, [rbp+28h]; this
0x180130732  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180130737  jmp     short loc_180130768
0x180130739  xor     edx, edx; length
0x18013073b  mov     rcx, [rbp+var_50]; string
0x18013073f  call    cs:__imp_WindowsGetStringRawBuffer
0x180130745  mov     rdx, rax; lpString
0x180130748  mov     rcx, rbx; hWnd
0x18013074b  call    cs:__imp_SetWindowTextW
0x180130751  test    eax, eax
0x180130753  jnz     short loc_180130785
0x180130755  mov     rcx, [rbp+28h]; this
0x180130759  mov     r8, rdi; unsigned int
0x18013075c  mov     edx, 3C4h; void *
0x180130761  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180130766  mov     ebx, eax
0x180130768  mov     rcx, [rbp+var_50]; string
0x18013076c  call    cs:__imp_WindowsDeleteString
0x180130772  mov     [rbp+var_50], 0
0x18013077a  lea     rcx, [rbp+var_48]
0x18013077e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180130783  jmp     short loc_1801307A2
0x180130785  mov     rcx, [rbp+var_50]; string
0x180130789  call    cs:__imp_WindowsDeleteString
0x18013078f  mov     [rbp+var_50], 0
0x180130797  lea     rcx, [rbp+var_48]
0x18013079b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801307a0  xor     ebx, ebx
0x1801307a2  mov     rcx, [rbp+string]; string
0x1801307a6  call    cs:__imp_WindowsDeleteString
0x1801307ac  mov     eax, ebx
0x1801307ae  mov     rcx, [rbp+var_10]
0x1801307b2  xor     rcx, rsp; StackCookie
0x1801307b5  call    __security_check_cookie
0x1801307ba  mov     rbx, [rsp+80h+arg_18]
0x1801307c2  add     rsp, 80h
0x1801307c9  pop     r15
0x1801307cb  pop     r14
0x1801307cd  pop     rdi
0x1801307ce  pop     rsi
0x1801307cf  pop     rbp
0x1801307d0  retn
```
