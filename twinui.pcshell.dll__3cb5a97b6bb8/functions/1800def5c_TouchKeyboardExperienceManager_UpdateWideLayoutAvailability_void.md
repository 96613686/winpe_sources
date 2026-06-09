# TouchKeyboardExperienceManager::UpdateWideLayoutAvailability(void)

- ea: `0x1800def5c`
- end: `0x1800df0f0`
- name: `?UpdateWideLayoutAvailability@TouchKeyboardExperienceManager@@AEAAXXZ`
- size: `404`
- prototype: `void __fastcall(TouchKeyboardExperienceManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180228770`
- `0x1804ba030`

## callees

- `0x180031c70`
- `0x1800def5c`
- `0x1800e0728`
- `0x1800e090c`
- `0x180356360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df0b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df0c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df0d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df0e9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df0b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df0c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df0d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df0e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800defaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800defdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df02c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df05a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800defaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800defdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df02c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df05a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TouchKeyboardExperienceManager::UpdateWideLayoutAvailability(TouchKeyboardExperienceManager *this)
{
  int MdmPolicyValue; // eax
  KeyboardHosting::TabTipAdapter *v3; // rdi
  HRESULT v4; // eax
  HSTRING v5; // rsi
  HRESULT v6; // eax
  int v7; // eax
  HRESULT v8; // eax
  HSTRING v9; // rsi
  HRESULT v10; // eax
  int v11; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER v14; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v15; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  MdmPolicyValue = KeyboardHosting::TextInputMdmPolicyHelper::GetMdmPolicyValue(L"TouchKeyboardWideModeAvailability");
  v3 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  if ( MdmPolicyValue == 2 )
  {
    string = 0;
    v4 = WindowsCreateStringReference(L"0", 1u, &hstringHeader, &string);
    if ( v4 < 0 )
    {
      RaiseException(v4, 1u, 0, 0);
    }
    else
    {
      v5 = string;
      v15 = 0;
      v6 = WindowsCreateStringReference(L"KeyboardModeEnabled_wide", 0x18u, &v14, &v15);
      if ( v6 >= 0 )
      {
        v7 = KeyboardHosting::TabTipAdapter::SetShellPreference(v3, v15, v5);
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x835,
            (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
            (const char *)(unsigned int)v7,
            (int)hstringHeader.Reserved.Reserved1);
        return;
      }
    }
    RaiseException(v6, 1u, 0, 0);
    goto LABEL_14;
  }
  v15 = 0;
  v8 = WindowsCreateStringReference(L"1", 1u, &v14, &v15);
  if ( v8 < 0 )
  {
LABEL_14:
    RaiseException(v8, 1u, 0, 0);
    goto LABEL_15;
  }
  v9 = v15;
  string = 0;
  v10 = WindowsCreateStringReference(L"KeyboardModeEnabled_wide", 0x18u, &hstringHeader, &string);
  if ( v10 < 0 )
  {
LABEL_15:
    RaiseException(v10, 1u, 0, 0);
    JUMPOUT(0x1800DF0EFLL);
  }
  v11 = KeyboardHosting::TabTipAdapter::SetShellPreference(v3, string, v9);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x839,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v11,
      (int)hstringHeader.Reserved.Reserved1);
}

```

## disassembly

```asm
0x1800def5c  push    rbp
0x1800def5e  push    rbx
0x1800def5f  push    rsi
0x1800def60  push    rdi
0x1800def61  mov     rbp, rsp
0x1800def64  sub     rsp, 78h
0x1800def68  mov     rax, cs:__security_cookie
0x1800def6f  xor     rax, rsp
0x1800def72  mov     [rbp+var_18], rax
0x1800def76  mov     rbx, rcx
0x1800def79  lea     rcx, aTouchkeyboardw; "TouchKeyboardWideModeAvailability"
0x1800def80  call    ?GetMdmPolicyValue@TextInputMdmPolicyHelper@KeyboardHosting@@SA?AW4MdmAvailabilityPolicy@2@PEBGW432@@Z; KeyboardHosting::TextInputMdmPolicyHelper::GetMdmPolicyValue(ushort const *,KeyboardHosting::MdmAvailabilityPolicy)
0x1800def85  mov     rdi, [rbx+248h]
0x1800def8c  mov     ebx, 1
0x1800def91  mov     edx, ebx; length
0x1800def93  cmp     eax, 2
0x1800def96  jnz     short loc_1800DF015
0x1800def98  mov     [rbp+string], 0
0x1800defa0  lea     r9, [rbp+string]; string
0x1800defa4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800defa8  lea     rcx, a0_0; "0"
0x1800defaf  call    cs:__imp_WindowsCreateStringReference
0x1800defb5  test    eax, eax
0x1800defb7  js      loc_1800DF0AC
0x1800defbd  mov     rsi, [rbp+string]
0x1800defc1  mov     [rbp+var_20], 0
0x1800defc9  lea     r9, [rbp+var_20]; string
0x1800defcd  lea     r8, [rbp+var_38]; hstringHeader
0x1800defd1  lea     edx, [rbx+17h]; length
0x1800defd4  lea     rcx, aKeyboardmodeen_6; "KeyboardModeEnabled_wide"
0x1800defdb  call    cs:__imp_WindowsCreateStringReference
0x1800defe1  test    eax, eax
0x1800defe3  js      loc_1800DF0BD
0x1800defe9  mov     r8, rsi; HSTRING
0x1800defec  mov     rdx, [rbp+var_20]; HSTRING
0x1800deff0  mov     rcx, rdi; this
0x1800deff3  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800deff8  mov     rcx, [rbp+20h]; this
0x1800deffc  test    eax, eax
0x1800deffe  js      short loc_1800DF07D
0x1800df000  mov     rcx, [rbp+var_18]
0x1800df004  xor     rcx, rsp; StackCookie
0x1800df007  call    __security_check_cookie
0x1800df00c  add     rsp, 78h
0x1800df010  pop     rdi
0x1800df011  pop     rsi
0x1800df012  pop     rbx
0x1800df013  pop     rbp
0x1800df014  retn
0x1800df015  mov     [rbp+var_20], 0
0x1800df01d  lea     r9, [rbp+var_20]; string
0x1800df021  lea     r8, [rbp+var_38]; hstringHeader
0x1800df025  lea     rcx, a1; "1"
0x1800df02c  call    cs:__imp_WindowsCreateStringReference
0x1800df032  test    eax, eax
0x1800df034  js      loc_1800DF0CE
0x1800df03a  mov     rsi, [rbp+var_20]
0x1800df03e  mov     [rbp+string], 0
0x1800df046  lea     r9, [rbp+string]; string
0x1800df04a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800df04e  mov     edx, 18h; length
0x1800df053  lea     rcx, aKeyboardmodeen_6; "KeyboardModeEnabled_wide"
0x1800df05a  call    cs:__imp_WindowsCreateStringReference
0x1800df060  test    eax, eax
0x1800df062  js      short loc_1800DF0DF
0x1800df064  mov     r8, rsi; HSTRING
0x1800df067  mov     rdx, [rbp+string]; HSTRING
0x1800df06b  mov     rcx, rdi; this
0x1800df06e  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800df073  mov     rcx, [rbp+20h]; this
0x1800df077  test    eax, eax
0x1800df079  js      short loc_1800DF096
0x1800df07b  jmp     short loc_1800DF000
0x1800df07d  mov     r9d, eax; char *
0x1800df080  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800df087  mov     edx, 835h; void *
0x1800df08c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df091  jmp     loc_1800DF000
0x1800df096  mov     r9d, eax; char *
0x1800df099  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800df0a0  mov     edx, 839h; void *
0x1800df0a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df0aa  jmp     short loc_1800DF07B
0x1800df0ac  xor     r9d, r9d; lpArguments
0x1800df0af  xor     r8d, r8d; nNumberOfArguments
0x1800df0b2  mov     edx, ebx; dwExceptionFlags
0x1800df0b4  mov     ecx, eax; dwExceptionCode
0x1800df0b6  call    cs:__imp_RaiseException
0x1800df0bc  nop
0x1800df0bd  xor     r9d, r9d; lpArguments
0x1800df0c0  xor     r8d, r8d; nNumberOfArguments
0x1800df0c3  mov     edx, ebx; dwExceptionFlags
0x1800df0c5  mov     ecx, eax; dwExceptionCode
0x1800df0c7  call    cs:__imp_RaiseException
0x1800df0cd  nop
0x1800df0ce  xor     r9d, r9d; lpArguments
0x1800df0d1  xor     r8d, r8d; nNumberOfArguments
0x1800df0d4  mov     edx, ebx; dwExceptionFlags
0x1800df0d6  mov     ecx, eax; dwExceptionCode
0x1800df0d8  call    cs:__imp_RaiseException
0x1800df0de  nop
0x1800df0df  xor     r9d, r9d; lpArguments
0x1800df0e2  xor     r8d, r8d; nNumberOfArguments
0x1800df0e5  mov     edx, ebx; dwExceptionFlags
0x1800df0e7  mov     ecx, eax; dwExceptionCode
0x1800df0e9  call    cs:__imp_RaiseException
```
