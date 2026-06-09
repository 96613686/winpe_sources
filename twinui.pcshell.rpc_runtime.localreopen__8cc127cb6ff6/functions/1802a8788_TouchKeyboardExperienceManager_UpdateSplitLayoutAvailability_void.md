# TouchKeyboardExperienceManager::UpdateSplitLayoutAvailability(void)

- ea: `0x1802a8788`
- end: `0x1802a8914`
- name: `?UpdateSplitLayoutAvailability@TouchKeyboardExperienceManager@@AEAAXXZ`
- size: `396`
- prototype: `void __fastcall(TouchKeyboardExperienceManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180228770`
- `0x1804b9f50`

## callees

- `0x180031c70`
- `0x1800e0728`
- `0x1800e090c`
- `0x1802a8788`
- `0x180356360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a87f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a882e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a8891`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a88cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a87f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a882e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a8891`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1802a88cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a87df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a881a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a887d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a88b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a87df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a881a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a887d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1802a88b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall TouchKeyboardExperienceManager::UpdateSplitLayoutAvailability(TouchKeyboardExperienceManager *this)
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

  MdmPolicyValue = KeyboardHosting::TextInputMdmPolicyHelper::GetMdmPolicyValue(L"TouchKeyboardSplitModeAvailability");
  v3 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  if ( MdmPolicyValue == 2 )
  {
    string = 0;
    v4 = WindowsCreateStringReference(L"0", 1u, &hstringHeader, &string);
    if ( v4 < 0 )
      RaiseException(v4, 1u, 0, 0);
    v5 = string;
    v15 = 0;
    v6 = WindowsCreateStringReference(L"KeyboardModeEnabled_split", 0x19u, &v14, &v15);
    if ( v6 < 0 )
      RaiseException(v6, 1u, 0, 0);
    v7 = KeyboardHosting::TabTipAdapter::SetShellPreference(v3, v15, v5);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x86C,
        (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
        (const char *)(unsigned int)v7,
        (int)hstringHeader.Reserved.Reserved1);
  }
  else
  {
    v15 = 0;
    v8 = WindowsCreateStringReference(L"1", 1u, &v14, &v15);
    if ( v8 < 0 )
      RaiseException(v8, 1u, 0, 0);
    v9 = v15;
    string = 0;
    v10 = WindowsCreateStringReference(L"KeyboardModeEnabled_split", 0x19u, &hstringHeader, &string);
    if ( v10 < 0 )
      RaiseException(v10, 1u, 0, 0);
    v11 = KeyboardHosting::TabTipAdapter::SetShellPreference(v3, string, v9);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x870,
        (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
        (const char *)(unsigned int)v11,
        (int)hstringHeader.Reserved.Reserved1);
  }
}

```

## disassembly

```asm
0x1802a8788  push    rbp
0x1802a878a  push    rbx
0x1802a878b  push    rsi
0x1802a878c  push    rdi
0x1802a878d  mov     rbp, rsp
0x1802a8790  sub     rsp, 78h
0x1802a8794  mov     rax, cs:__security_cookie
0x1802a879b  xor     rax, rsp
0x1802a879e  mov     [rbp+var_18], rax
0x1802a87a2  mov     rbx, rcx
0x1802a87a5  lea     rcx, aTouchkeyboards; "TouchKeyboardSplitModeAvailability"
0x1802a87ac  call    ?GetMdmPolicyValue@TextInputMdmPolicyHelper@KeyboardHosting@@SA?AW4MdmAvailabilityPolicy@2@PEBGW432@@Z; KeyboardHosting::TextInputMdmPolicyHelper::GetMdmPolicyValue(ushort const *,KeyboardHosting::MdmAvailabilityPolicy)
0x1802a87b1  mov     rdi, [rbx+248h]
0x1802a87b8  mov     ebx, 1
0x1802a87bd  mov     edx, ebx; length
0x1802a87bf  cmp     eax, 2
0x1802a87c2  jnz     loc_1802A8866
0x1802a87c8  mov     [rbp+string], 0
0x1802a87d0  lea     r9, [rbp+string]; string
0x1802a87d4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1802a87d8  lea     rcx, a0_0; "0"
0x1802a87df  call    cs:__imp_WindowsCreateStringReference
0x1802a87e5  test    eax, eax
0x1802a87e7  jns     short loc_1802A87FA
0x1802a87e9  xor     r9d, r9d; lpArguments
0x1802a87ec  xor     r8d, r8d; nNumberOfArguments
0x1802a87ef  mov     edx, ebx; dwExceptionFlags
0x1802a87f1  mov     ecx, eax; dwExceptionCode
0x1802a87f3  call    cs:__imp_RaiseException
0x1802a87f9  nop
0x1802a87fa  mov     rsi, [rbp+string]
0x1802a87fe  mov     [rbp+var_20], 0
0x1802a8806  lea     r9, [rbp+var_20]; string
0x1802a880a  lea     r8, [rbp+var_38]; hstringHeader
0x1802a880e  mov     edx, 19h; length
0x1802a8813  lea     rcx, aKeyboardmodeen_1; "KeyboardModeEnabled_split"
0x1802a881a  call    cs:__imp_WindowsCreateStringReference
0x1802a8820  test    eax, eax
0x1802a8822  jns     short loc_1802A8835
0x1802a8824  xor     r9d, r9d; lpArguments
0x1802a8827  xor     r8d, r8d; nNumberOfArguments
0x1802a882a  mov     edx, ebx; dwExceptionFlags
0x1802a882c  mov     ecx, eax; dwExceptionCode
0x1802a882e  call    cs:__imp_RaiseException
0x1802a8834  nop
0x1802a8835  mov     r8, rsi; HSTRING
0x1802a8838  mov     rdx, [rbp+var_20]; HSTRING
0x1802a883c  mov     rcx, rdi; this
0x1802a883f  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1802a8844  mov     rcx, [rbp+20h]; this
0x1802a8848  test    eax, eax
0x1802a884a  jns     short loc_1802A8861
0x1802a884c  mov     r9d, eax; char *
0x1802a884f  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1802a8856  mov     edx, 86Ch; void *
0x1802a885b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802a8860  nop
0x1802a8861  jmp     loc_1802A88FF
0x1802a8866  mov     [rbp+var_20], 0
0x1802a886e  lea     r9, [rbp+var_20]; string
0x1802a8872  lea     r8, [rbp+var_38]; hstringHeader
0x1802a8876  lea     rcx, a1; "1"
0x1802a887d  call    cs:__imp_WindowsCreateStringReference
0x1802a8883  test    eax, eax
0x1802a8885  jns     short loc_1802A8898
0x1802a8887  xor     r9d, r9d; lpArguments
0x1802a888a  xor     r8d, r8d; nNumberOfArguments
0x1802a888d  mov     edx, ebx; dwExceptionFlags
0x1802a888f  mov     ecx, eax; dwExceptionCode
0x1802a8891  call    cs:__imp_RaiseException
0x1802a8897  nop
0x1802a8898  mov     rsi, [rbp+var_20]
0x1802a889c  mov     [rbp+string], 0
0x1802a88a4  lea     r9, [rbp+string]; string
0x1802a88a8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1802a88ac  mov     edx, 19h; length
0x1802a88b1  lea     rcx, aKeyboardmodeen_1; "KeyboardModeEnabled_split"
0x1802a88b8  call    cs:__imp_WindowsCreateStringReference
0x1802a88be  test    eax, eax
0x1802a88c0  jns     short loc_1802A88D3
0x1802a88c2  xor     r9d, r9d; lpArguments
0x1802a88c5  xor     r8d, r8d; nNumberOfArguments
0x1802a88c8  mov     edx, ebx; dwExceptionFlags
0x1802a88ca  mov     ecx, eax; dwExceptionCode
0x1802a88cc  call    cs:__imp_RaiseException
0x1802a88d2  nop
0x1802a88d3  mov     r8, rsi; HSTRING
0x1802a88d6  mov     rdx, [rbp+string]; HSTRING
0x1802a88da  mov     rcx, rdi; this
0x1802a88dd  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1802a88e2  mov     rcx, [rbp+20h]; this
0x1802a88e6  test    eax, eax
0x1802a88e8  jns     short loc_1802A88FF
0x1802a88ea  mov     r9d, eax; char *
0x1802a88ed  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1802a88f4  mov     edx, 870h; void *
0x1802a88f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802a88fe  nop
0x1802a88ff  mov     rcx, [rbp+var_18]
0x1802a8903  xor     rcx, rsp; StackCookie
0x1802a8906  call    __security_check_cookie
0x1802a890b  add     rsp, 78h
0x1802a890f  pop     rdi
0x1802a8910  pop     rsi
0x1802a8911  pop     rbx
0x1802a8912  pop     rbp
0x1802a8913  retn
```
