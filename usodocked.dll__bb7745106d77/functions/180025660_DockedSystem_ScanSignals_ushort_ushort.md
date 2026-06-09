# DockedSystem::ScanSignals(ushort * *,ushort * *)

- ea: `0x180025660`
- end: `0x180025997`
- name: `?ScanSignals@DockedSystem@@UEAAJPEAPEAG0@Z`
- size: `823`
- prototype: `__int64 __fastcall(DockedSystem *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x1800183f4`
- `0x1800209fc`
- `0x1800233b8`
- `0x180023a34`
- `0x180025660`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180025833`
- `OLEAUT32!__imp_SysAllocString` at `0x18002586b`
- `OLEAUT32!__imp_SysAllocString` at `0x180025833`
- `OLEAUT32!__imp_SysAllocString` at `0x18002586b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800258a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800257f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025897`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800258a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002570d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002576f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002570d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002576f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025861`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180025861`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002572c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002572c`

## string_xrefs

- `0x180025972`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180025984`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800256a8`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x1800256d5`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180025919`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180025936`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x18002594b`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180025960`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DockedSystem::ScanSignals(DockedSystem *this, unsigned __int16 **a2, unsigned __int16 **a3)
{
  __int64 result; // rax
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 *v11; // rbx
  __int64 v12; // rdi
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int v16; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  const OLECHAR *StringRawBuffer; // rax
  unsigned __int16 *v25; // rax
  const char *v26; // r9
  const OLECHAR *v27; // rax
  unsigned __int16 *v28; // rax
  const char *v29; // r9
  const char *v30; // r9
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-68h] BYREF
  HSTRING string; // [rsp+48h] [rbp-50h] BYREF
  HSTRING v33; // [rsp+50h] [rbp-48h] BYREF
  HSTRING v34; // [rsp+58h] [rbp-40h] BYREF
  __int64 v35; // [rsp+60h] [rbp-38h] BYREF
  __int64 *v36; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)0x80004003LL,
      0);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)0x80004003LL,
      0);
    return 2147500035LL;
  }
  v36 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
         0x39u,
         &hstringHeader,
         &string);
  try
  {
    if ( v6 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    }
    else
    {
      ActivationFactory = RoGetActivationFactory(string, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &v36);
      v10 = retaddr;
      if ( ActivationFactory >= 0 )
      {
        v35 = 0;
        v11 = v36;
        v12 = *v36;
        v35 = 0;
        string = 0;
        v13 = WindowsCreateStringReference(L"MLMOD", 5u, &hstringHeader, &string);
        if ( v13 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
        }
        else
        {
          v16 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v12 + 48))(v11, string, &v35);
          v17 = retaddr;
          if ( v16 >= 0 )
          {
            v34 = 0;
            v18 = v35;
            v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35 + 104LL);
            WindowsDeleteString(0);
            v34 = 0;
            v20 = v19(v18, &v34);
            if ( v20 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x14A,
                (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
                (const char *)(unsigned int)v20,
                0);
            v33 = 0;
            v21 = v35;
            v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35 + 128LL);
            WindowsDeleteString(0);
            v33 = 0;
            v23 = v22(v21, &v33);
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x14D,
                (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
                (const char *)(unsigned int)v23,
                0);
            StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
            v25 = SysAllocString(StringRawBuffer);
            if ( !v25 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x15F3,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                v26);
            *a2 = v25;
            v27 = WindowsGetStringRawBuffer(v33, 0);
            v28 = SysAllocString(v27);
            if ( !v28 )
              wil::details::in1diag3::_Throw_NullAlloc(
                retaddr,
                (void *)0x15F3,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                v29);
            *a3 = v28;
            WindowsDeleteString(v33);
            v33 = 0;
            WindowsDeleteString(v34);
            v34 = 0;
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            if ( v36 )
              (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
            return 0;
          }
        }
        wil::details::in1diag3::Throw_Hr(
          v17,
          (void *)0x147,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
          (const char *)(unsigned int)v16,
          0);
      }
    }
    wil::details::in1diag3::Throw_Hr(
      v10,
      (void *)0x144,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)(unsigned int)ActivationFactory,
      0);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x154,
                           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\d"
                                         "ll\\dockedsystem.cpp",
                           v30);
  }
  return result;
}

```

## disassembly

```asm
0x180025660  mov     [rsp+arg_0], rbx
0x180025665  mov     [rsp+arg_18], rsi
0x18002566a  push    rdi
0x18002566b  push    r14
0x18002566d  push    r15
0x18002566f  sub     rsp, 80h
0x180025676  mov     rax, cs:__security_cookie
0x18002567d  xor     rax, rsp
0x180025680  mov     [rsp+98h+var_28], rax
0x180025685  mov     rsi, r8
0x180025688  mov     r14, rdx
0x18002568b  xor     r15d, r15d
0x18002568e  mov     [rsp+98h+var_78], r15d; int
0x180025693  test    rdx, rdx
0x180025696  jnz     short loc_1800256C0
0x180025698  mov     rcx, [rsp+98h]; this
0x1800256a0  mov     ebx, 80004003h
0x1800256a5  mov     r9d, ebx; char *
0x1800256a8  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800256af  mov     edx, 13Eh; void *
0x1800256b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800256b9  mov     eax, ebx
0x1800256bb  jmp     loc_1800258E8
0x1800256c0  test    rsi, rsi
0x1800256c3  jnz     short loc_1800256ED
0x1800256c5  mov     rcx, [rsp+98h]; this
0x1800256cd  mov     ebx, 80004003h
0x1800256d2  mov     r9d, ebx; char *
0x1800256d5  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800256dc  mov     edx, 13Fh; void *
0x1800256e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800256e6  mov     eax, ebx
0x1800256e8  jmp     loc_1800258E8
0x1800256ed  mov     [rsp+98h+var_30], r15
0x1800256f2  mov     [rsp+98h+string], r15
0x1800256f7  lea     r9, [rsp+98h+string]; string
0x1800256fc  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180025701  mov     edx, 39h ; '9'; length
0x180025706  lea     rcx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18002570d  call    cs:__imp_WindowsCreateStringReference
0x180025713  test    eax, eax
0x180025715  js      loc_18002590E
0x18002571b  lea     r8, [rsp+98h+var_30]
0x180025720  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x180025727  mov     rcx, [rsp+98h+string]
0x18002572c  call    cs:__imp_RoGetActivationFactory
0x180025732  mov     rcx, [rsp+98h]
0x18002573a  test    eax, eax
0x18002573c  js      loc_180025916
0x180025742  mov     [rsp+98h+var_38], r15
0x180025747  mov     rbx, [rsp+98h+var_30]
0x18002574c  mov     rdi, [rbx]
0x18002574f  mov     [rsp+98h+var_38], r15
0x180025754  mov     [rsp+98h+string], r15
0x180025759  lea     r9, [rsp+98h+string]; string
0x18002575e  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x180025763  mov     edx, 5; length
0x180025768  lea     rcx, sourceString; "MLMOD"
0x18002576f  call    cs:__imp_WindowsCreateStringReference
0x180025775  test    eax, eax
0x180025777  js      loc_18002592B
0x18002577d  lea     r8, [rsp+98h+var_38]
0x180025782  mov     rdx, [rsp+98h+string]
0x180025787  mov     rcx, rbx
0x18002578a  mov     rax, [rdi+30h]
0x18002578e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025793  mov     rcx, [rsp+98h]
0x18002579b  test    eax, eax
0x18002579d  js      loc_180025933
0x1800257a3  mov     [rsp+98h+var_40], r15
0x1800257a8  mov     rdi, [rsp+98h+var_38]
0x1800257ad  mov     rax, [rdi]
0x1800257b0  mov     rbx, [rax+68h]
0x1800257b4  xor     ecx, ecx; string
0x1800257b6  call    cs:__imp_WindowsDeleteString
0x1800257bc  mov     [rsp+98h+var_40], r15
0x1800257c1  lea     rdx, [rsp+98h+var_40]
0x1800257c6  mov     rcx, rdi
0x1800257c9  mov     rax, rbx
0x1800257cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257d1  mov     rcx, [rsp+98h]; this
0x1800257d9  test    eax, eax
0x1800257db  js      loc_180025948
0x1800257e1  mov     [rsp+98h+var_48], r15
0x1800257e6  mov     rdi, [rsp+98h+var_38]
0x1800257eb  mov     rax, [rdi]
0x1800257ee  mov     rbx, [rax+80h]
0x1800257f5  xor     ecx, ecx; string
0x1800257f7  call    cs:__imp_WindowsDeleteString
0x1800257fd  mov     [rsp+98h+var_48], r15
0x180025802  lea     rdx, [rsp+98h+var_48]
0x180025807  mov     rcx, rdi
0x18002580a  mov     rax, rbx
0x18002580d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025812  mov     rcx, [rsp+98h]; this
0x18002581a  test    eax, eax
0x18002581c  js      loc_18002595D
0x180025822  xor     edx, edx; length
0x180025824  mov     rcx, [rsp+98h+var_40]; string
0x180025829  call    cs:__imp_WindowsGetStringRawBuffer
0x18002582f  nop
0x180025830  mov     rcx, rax; psz
0x180025833  call    cs:__imp_SysAllocString
0x180025839  mov     [rsp+98h+var_70], rax
0x18002583e  mov     [rsp+98h+var_78], 1
0x180025846  mov     rcx, [rsp+98h]; this
0x18002584e  test    rax, rax
0x180025851  jz      loc_180025972
0x180025857  mov     [r14], rax
0x18002585a  xor     edx, edx; length
0x18002585c  mov     rcx, [rsp+98h+var_48]; string
0x180025861  call    cs:__imp_WindowsGetStringRawBuffer
0x180025867  nop
0x180025868  mov     rcx, rax; psz
0x18002586b  call    cs:__imp_SysAllocString
0x180025871  mov     [rsp+98h+var_70], rax
0x180025876  mov     [rsp+98h+var_78], 2
0x18002587e  mov     rcx, [rsp+98h]; this
0x180025886  test    rax, rax
0x180025889  jz      loc_180025984
0x18002588f  mov     [rsi], rax
0x180025892  mov     rcx, [rsp+98h+var_48]; string
0x180025897  call    cs:__imp_WindowsDeleteString
0x18002589d  mov     [rsp+98h+var_48], r15
0x1800258a2  mov     rcx, [rsp+98h+var_40]; string
0x1800258a7  call    cs:__imp_WindowsDeleteString
0x1800258ad  mov     [rsp+98h+var_40], r15
0x1800258b2  mov     rcx, [rsp+98h+var_38]
0x1800258b7  test    rcx, rcx
0x1800258ba  jz      short loc_1800258C9
0x1800258bc  mov     rax, [rcx]
0x1800258bf  mov     rax, [rax+10h]
0x1800258c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258c8  nop
0x1800258c9  mov     rcx, [rsp+98h+var_30]
0x1800258ce  test    rcx, rcx
0x1800258d1  jz      short loc_1800258E0
0x1800258d3  mov     rax, [rcx]
0x1800258d6  mov     rax, [rax+10h]
0x1800258da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258df  nop
0x1800258e0  xor     eax, eax
0x1800258e2  jmp     short loc_1800258E8
0x1800258e4  mov     eax, [rsp+98h+var_78]
0x1800258e8  mov     rcx, [rsp+98h+var_28]
0x1800258ed  xor     rcx, rsp; StackCookie
0x1800258f0  call    __security_check_cookie
0x1800258f5  lea     r11, [rsp+98h+var_18]
0x1800258fd  mov     rbx, [r11+20h]
0x180025901  mov     rsi, [r11+38h]
0x180025905  mov     rsp, r11
0x180025908  pop     r15
0x18002590a  pop     r14
0x18002590c  pop     rdi
0x18002590d  retn
0x18002590e  mov     ecx, eax; this
0x180025910  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180025915  nop
0x180025916  mov     r9d, eax; char *
0x180025919  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180025920  mov     edx, 144h; void *
0x180025925  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002592b  mov     ecx, eax; this
0x18002592d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180025932  nop
0x180025933  mov     r9d, eax; char *
0x180025936  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002593d  mov     edx, 147h; void *
0x180025942  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025948  mov     r9d, eax; char *
0x18002594b  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180025952  mov     edx, 14Ah; void *
0x180025957  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002595d  mov     r9d, eax; char *
0x180025960  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180025967  mov     edx, 14Dh; void *
0x18002596c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025972  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025979  mov     edx, 15F3h; void *
0x18002597e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180025984  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002598b  mov     edx, 15F3h; void *
0x180025990  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
