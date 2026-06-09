# TouchKeyboardExperienceManager::UpdateHandwritingAvailability(void)

- ea: `0x1800dec84`
- end: `0x1800def53`
- name: `?UpdateHandwritingAvailability@TouchKeyboardExperienceManager@@AEAAXXZ`
- size: `719`
- prototype: `void __fastcall(TouchKeyboardExperienceManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180228770`
- `0x1804b9e80`

## callees

- `0x180031c70`
- `0x1800dec84`
- `0x1800e0728`
- `0x1800e090c`
- `0x180356360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800decef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ded2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800deda0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800deddc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dee2c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dee68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800deecf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800def0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800decef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ded2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800deda0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800deddc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dee2c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dee68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800deecf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800def0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800decda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ded16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ded8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dedc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dee17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dee53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800deeba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800deef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800decda`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ded16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ded8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dedc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dee17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dee53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800deeba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800deef6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TouchKeyboardExperienceManager::UpdateHandwritingAvailability(TouchKeyboardExperienceManager *this)
{
  int MdmPolicyValue; // esi
  KeyboardHosting::TabTipAdapter *v3; // r14
  HRESULT v4; // eax
  HSTRING v5; // rbx
  HRESULT v6; // eax
  int v7; // eax
  KeyboardHosting::TabTipAdapter *v8; // rbx
  HRESULT v9; // eax
  HSTRING v10; // rdi
  HRESULT v11; // eax
  int v12; // eax
  HRESULT v13; // eax
  HSTRING v14; // rsi
  HRESULT v15; // eax
  int v16; // eax
  KeyboardHosting::TabTipAdapter *v17; // rdi
  HRESULT v18; // eax
  HSTRING v19; // rbx
  HRESULT v20; // eax
  int v21; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER v24; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v25; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  MdmPolicyValue = KeyboardHosting::TextInputMdmPolicyHelper::GetMdmPolicyValue(L"TouchKeyboardHandwritingModeAvailability");
  v3 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  string = 0;
  v4 = WindowsCreateStringReference(L"0", 1u, &hstringHeader, &string);
  if ( v4 < 0 )
    RaiseException(v4, 1u, 0, 0);
  v5 = string;
  v25 = 0;
  v6 = WindowsCreateStringReference(L"KeyboardModeEnabled_handwritinglinenarrow", 0x29u, &v24, &v25);
  if ( v6 < 0 )
    RaiseException(v6, 1u, 0, 0);
  v7 = KeyboardHosting::TabTipAdapter::SetShellPreference(v3, v25, v5);
  if ( v7 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x857,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v7,
      (int)hstringHeader.Reserved.Reserved1);
  v8 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  v25 = 0;
  if ( MdmPolicyValue == 2 )
  {
    v9 = WindowsCreateStringReference(L"0", 1u, &v24, &v25);
    if ( v9 < 0 )
      RaiseException(v9, 1u, 0, 0);
    v10 = v25;
    string = 0;
    v11 = WindowsCreateStringReference(L"KeyboardModeEnabled_handwritingline", 0x23u, &hstringHeader, &string);
    if ( v11 < 0 )
      RaiseException(v11, 1u, 0, 0);
    v12 = KeyboardHosting::TabTipAdapter::SetShellPreference(v8, string, v10);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x85C,
        (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
        (const char *)(unsigned int)v12,
        (int)hstringHeader.Reserved.Reserved1);
  }
  else
  {
    v13 = WindowsCreateStringReference(L"1", 1u, &v24, &v25);
    if ( v13 < 0 )
      RaiseException(v13, 1u, 0, 0);
    v14 = v25;
    string = 0;
    v15 = WindowsCreateStringReference(L"KeyboardModeEnabled_handwritingline", 0x23u, &hstringHeader, &string);
    if ( v15 < 0 )
      RaiseException(v15, 1u, 0, 0);
    v16 = KeyboardHosting::TabTipAdapter::SetShellPreference(v8, string, v14);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x860,
        (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
        (const char *)(unsigned int)v16,
        (int)hstringHeader.Reserved.Reserved1);
    v17 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
    v25 = 0;
    v18 = WindowsCreateStringReference(L"handwritingline", 0xFu, &v24, &v25);
    if ( v18 < 0 )
      RaiseException(v18, 1u, 0, 0);
    v19 = v25;
    string = 0;
    v20 = WindowsCreateStringReference(L"DefaultPenKeyboardMode", 0x16u, &hstringHeader, &string);
    if ( v20 < 0 )
      RaiseException(v20, 1u, 0, 0);
    v21 = KeyboardHosting::TabTipAdapter::SetShellPreference(v17, string, v19);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x861,
        (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
        (const char *)(unsigned int)v21,
        (int)hstringHeader.Reserved.Reserved1);
  }
}

```

## disassembly

```asm
0x1800dec84  push    rbp
0x1800dec86  push    rbx
0x1800dec87  push    rsi
0x1800dec88  push    rdi
0x1800dec89  push    r12
0x1800dec8b  push    r14
0x1800dec8d  mov     rbp, rsp
0x1800dec90  sub     rsp, 78h
0x1800dec94  mov     rax, cs:__security_cookie
0x1800dec9b  xor     rax, rsp
0x1800dec9e  mov     [rbp+var_18], rax
0x1800deca2  mov     rdi, rcx
0x1800deca5  lea     rcx, aTouchkeyboardh; "TouchKeyboardHandwritingModeAvailabilit"...
0x1800decac  call    ?GetMdmPolicyValue@TextInputMdmPolicyHelper@KeyboardHosting@@SA?AW4MdmAvailabilityPolicy@2@PEBGW432@@Z; KeyboardHosting::TextInputMdmPolicyHelper::GetMdmPolicyValue(ushort const *,KeyboardHosting::MdmAvailabilityPolicy)
0x1800decb1  mov     esi, eax
0x1800decb3  mov     r14, [rdi+248h]
0x1800decba  mov     [rbp+string], 0
0x1800decc2  lea     r9, [rbp+string]; string
0x1800decc6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800decca  mov     r12d, 1
0x1800decd0  mov     edx, r12d; length
0x1800decd3  lea     rcx, a0_0; "0"
0x1800decda  call    cs:__imp_WindowsCreateStringReference
0x1800dece0  test    eax, eax
0x1800dece2  jns     short loc_1800DECF6
0x1800dece4  xor     r9d, r9d; lpArguments
0x1800dece7  xor     r8d, r8d; nNumberOfArguments
0x1800decea  mov     edx, r12d; dwExceptionFlags
0x1800deced  mov     ecx, eax; dwExceptionCode
0x1800decef  call    cs:__imp_RaiseException
0x1800decf5  nop
0x1800decf6  mov     rbx, [rbp+string]
0x1800decfa  mov     [rbp+var_20], 0
0x1800ded02  lea     r9, [rbp+var_20]; string
0x1800ded06  lea     r8, [rbp+var_38]; hstringHeader
0x1800ded0a  mov     edx, 29h ; ')'; length
0x1800ded0f  lea     rcx, aKeyboardmodeen_3; "KeyboardModeEnabled_handwritinglinenarr"...
0x1800ded16  call    cs:__imp_WindowsCreateStringReference
0x1800ded1c  test    eax, eax
0x1800ded1e  jns     short loc_1800DED32
0x1800ded20  xor     r9d, r9d; lpArguments
0x1800ded23  xor     r8d, r8d; nNumberOfArguments
0x1800ded26  mov     edx, r12d; dwExceptionFlags
0x1800ded29  mov     ecx, eax; dwExceptionCode
0x1800ded2b  call    cs:__imp_RaiseException
0x1800ded31  nop
0x1800ded32  mov     r8, rbx; HSTRING
0x1800ded35  mov     rdx, [rbp+var_20]; HSTRING
0x1800ded39  mov     rcx, r14; this
0x1800ded3c  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800ded41  mov     rcx, [rbp+30h]; this
0x1800ded45  lea     r14, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800ded4c  test    eax, eax
0x1800ded4e  jns     short loc_1800DED61
0x1800ded50  mov     r9d, eax; char *
0x1800ded53  mov     r8, r14; unsigned int
0x1800ded56  mov     edx, 857h; void *
0x1800ded5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ded60  nop
0x1800ded61  mov     rbx, [rdi+248h]
0x1800ded68  mov     [rbp+var_20], 0
0x1800ded70  lea     r9, [rbp+var_20]; string
0x1800ded74  lea     r8, [rbp+var_38]; hstringHeader
0x1800ded78  mov     edx, r12d; length
0x1800ded7b  cmp     esi, 2
0x1800ded7e  jnz     loc_1800DEE10
0x1800ded84  lea     rcx, a0_0; "0"
0x1800ded8b  call    cs:__imp_WindowsCreateStringReference
0x1800ded91  test    eax, eax
0x1800ded93  jns     short loc_1800DEDA7
0x1800ded95  xor     r9d, r9d; lpArguments
0x1800ded98  xor     r8d, r8d; nNumberOfArguments
0x1800ded9b  mov     edx, r12d; dwExceptionFlags
0x1800ded9e  mov     ecx, eax; dwExceptionCode
0x1800deda0  call    cs:__imp_RaiseException
0x1800deda6  nop
0x1800deda7  mov     rdi, [rbp+var_20]
0x1800dedab  mov     [rbp+string], 0
0x1800dedb3  lea     r9, [rbp+string]; string
0x1800dedb7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800dedbb  mov     edx, 23h ; '#'; length
0x1800dedc0  lea     rcx, aKeyboardmodeen_8; "KeyboardModeEnabled_handwritingline"
0x1800dedc7  call    cs:__imp_WindowsCreateStringReference
0x1800dedcd  test    eax, eax
0x1800dedcf  jns     short loc_1800DEDE3
0x1800dedd1  xor     r9d, r9d; lpArguments
0x1800dedd4  xor     r8d, r8d; nNumberOfArguments
0x1800dedd7  mov     edx, r12d; dwExceptionFlags
0x1800dedda  mov     ecx, eax; dwExceptionCode
0x1800deddc  call    cs:__imp_RaiseException
0x1800dede2  nop
0x1800dede3  mov     r8, rdi; HSTRING
0x1800dede6  mov     rdx, [rbp+string]; HSTRING
0x1800dedea  mov     rcx, rbx; this
0x1800deded  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800dedf2  mov     rcx, [rbp+30h]; this
0x1800dedf6  test    eax, eax
0x1800dedf8  jns     short loc_1800DEE0B
0x1800dedfa  mov     r9d, eax; char *
0x1800dedfd  mov     r8, r14; unsigned int
0x1800dee00  mov     edx, 85Ch; void *
0x1800dee05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dee0a  nop
0x1800dee0b  jmp     loc_1800DEF3A
0x1800dee10  lea     rcx, a1; "1"
0x1800dee17  call    cs:__imp_WindowsCreateStringReference
0x1800dee1d  test    eax, eax
0x1800dee1f  jns     short loc_1800DEE33
0x1800dee21  xor     r9d, r9d; lpArguments
0x1800dee24  xor     r8d, r8d; nNumberOfArguments
0x1800dee27  mov     edx, r12d; dwExceptionFlags
0x1800dee2a  mov     ecx, eax; dwExceptionCode
0x1800dee2c  call    cs:__imp_RaiseException
0x1800dee32  nop
0x1800dee33  mov     rsi, [rbp+var_20]
0x1800dee37  mov     [rbp+string], 0
0x1800dee3f  lea     r9, [rbp+string]; string
0x1800dee43  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800dee47  mov     edx, 23h ; '#'; length
0x1800dee4c  lea     rcx, aKeyboardmodeen_8; "KeyboardModeEnabled_handwritingline"
0x1800dee53  call    cs:__imp_WindowsCreateStringReference
0x1800dee59  test    eax, eax
0x1800dee5b  jns     short loc_1800DEE6F
0x1800dee5d  xor     r9d, r9d; lpArguments
0x1800dee60  xor     r8d, r8d; nNumberOfArguments
0x1800dee63  mov     edx, r12d; dwExceptionFlags
0x1800dee66  mov     ecx, eax; dwExceptionCode
0x1800dee68  call    cs:__imp_RaiseException
0x1800dee6e  nop
0x1800dee6f  mov     r8, rsi; HSTRING
0x1800dee72  mov     rdx, [rbp+string]; HSTRING
0x1800dee76  mov     rcx, rbx; this
0x1800dee79  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800dee7e  mov     rcx, [rbp+30h]; this
0x1800dee82  test    eax, eax
0x1800dee84  jns     short loc_1800DEE97
0x1800dee86  mov     r9d, eax; char *
0x1800dee89  mov     r8, r14; unsigned int
0x1800dee8c  mov     edx, 860h; void *
0x1800dee91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dee96  nop
0x1800dee97  mov     rdi, [rdi+248h]
0x1800dee9e  mov     [rbp+var_20], 0
0x1800deea6  lea     r9, [rbp+var_20]; string
0x1800deeaa  lea     r8, [rbp+var_38]; hstringHeader
0x1800deeae  mov     edx, 0Fh; length
0x1800deeb3  lea     rcx, aHandwritinglin; "handwritingline"
0x1800deeba  call    cs:__imp_WindowsCreateStringReference
0x1800deec0  test    eax, eax
0x1800deec2  jns     short loc_1800DEED6
0x1800deec4  xor     r9d, r9d; lpArguments
0x1800deec7  xor     r8d, r8d; nNumberOfArguments
0x1800deeca  mov     edx, r12d; dwExceptionFlags
0x1800deecd  mov     ecx, eax; dwExceptionCode
0x1800deecf  call    cs:__imp_RaiseException
0x1800deed5  nop
0x1800deed6  mov     rbx, [rbp+var_20]
0x1800deeda  mov     [rbp+string], 0
0x1800deee2  lea     r9, [rbp+string]; string
0x1800deee6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800deeea  mov     edx, 16h; length
0x1800deeef  lea     rcx, aDefaultpenkeyb; "DefaultPenKeyboardMode"
0x1800deef6  call    cs:__imp_WindowsCreateStringReference
0x1800deefc  test    eax, eax
0x1800deefe  jns     short loc_1800DEF12
0x1800def00  xor     r9d, r9d; lpArguments
0x1800def03  xor     r8d, r8d; nNumberOfArguments
0x1800def06  mov     edx, r12d; dwExceptionFlags
0x1800def09  mov     ecx, eax; dwExceptionCode
0x1800def0b  call    cs:__imp_RaiseException
0x1800def11  nop
0x1800def12  mov     r8, rbx; HSTRING
0x1800def15  mov     rdx, [rbp+string]; HSTRING
0x1800def19  mov     rcx, rdi; this
0x1800def1c  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800def21  mov     rcx, [rbp+30h]; this
0x1800def25  test    eax, eax
0x1800def27  jns     short loc_1800DEF3A
0x1800def29  mov     r9d, eax; char *
0x1800def2c  mov     r8, r14; unsigned int
0x1800def2f  mov     edx, 861h; void *
0x1800def34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800def39  nop
0x1800def3a  mov     rcx, [rbp+var_18]
0x1800def3e  xor     rcx, rsp; StackCookie
0x1800def41  call    __security_check_cookie
0x1800def46  add     rsp, 78h
0x1800def4a  pop     r14
0x1800def4c  pop     r12
0x1800def4e  pop     rdi
0x1800def4f  pop     rsi
0x1800def50  pop     rbx
0x1800def51  pop     rbp
0x1800def52  retn
```
