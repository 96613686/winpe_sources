# TouchKeyboardExperienceManager::UpdateFullLayoutAvailability(void)

- ea: `0x1800dfad8`
- end: `0x1800dfe3f`
- name: `?UpdateFullLayoutAvailability@TouchKeyboardExperienceManager@@AEAAXXZ`
- size: `871`
- prototype: `void __fastcall(TouchKeyboardExperienceManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180228770`
- `0x1804b9f40`

## callees

- `0x180031c70`
- `0x1800dfad8`
- `0x1800e0728`
- `0x1800e090c`
- `0x1800e0f00`
- `0x1800e1520`
- `0x1801dd6f8`
- `0x180356360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfdc1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfdd2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfde3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfdf4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfe05`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfe16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfe27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfe38`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfdc1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfdd2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfde3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfdf4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfe05`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfe16`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfe27`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dfe38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfb40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfb6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfbb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfbe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfc52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfc7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfcc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfcf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfb40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfb6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfbb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfbe3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfc52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfc7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfcc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dfcf5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TouchKeyboardExperienceManager::UpdateFullLayoutAvailability(TouchKeyboardExperienceManager *this)
{
  int MdmPolicyValue; // eax
  KeyboardHosting::TabTipAdapter *v3; // rsi
  HRESULT v4; // eax
  HSTRING v5; // r14
  HRESULT v6; // eax
  int v7; // eax
  KeyboardHosting::TabTipAdapter *v8; // rsi
  HRESULT v9; // eax
  HSTRING v10; // rdi
  HRESULT v11; // eax
  int v12; // eax
  KeyboardHosting::TabTipAdapter *v13; // rsi
  HRESULT v14; // eax
  HSTRING v15; // r14
  HRESULT v16; // eax
  int v17; // eax
  KeyboardHosting::TabTipAdapter *v18; // rsi
  HRESULT v19; // eax
  HSTRING v20; // rdi
  HRESULT v21; // eax
  int v22; // eax
  TouchKeyboardExperienceManager *v23; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-50h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER v26; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v27; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  MdmPolicyValue = KeyboardHosting::TextInputMdmPolicyHelper::GetMdmPolicyValue(L"TouchKeyboardFullModeAvailability");
  if ( MdmPolicyValue != 2
    && (MdmPolicyValue
     || !(unsigned int)IsUserAssignedAccessSingleApp(-4)
     && !TouchKeyboardExperienceManager::IsKeyboardFilterServiceRunning(v23)
     || TouchKeyboardExperienceManager::IsCompatibilityKeyboardEnabled(v23)) )
  {
    v3 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
    string = 0;
    v4 = WindowsCreateStringReference(L"1", 1u, &hstringHeader, &string);
    if ( v4 < 0 )
    {
      RaiseException(v4, 1u, 0, 0);
    }
    else
    {
      v5 = string;
      v27 = 0;
      v6 = WindowsCreateStringReference(L"KeyboardModeEnabled_full", 0x18u, &v26, &v27);
      if ( v6 >= 0 )
      {
        v7 = KeyboardHosting::TabTipAdapter::SetShellPreference(v3, v27, v5);
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x829,
            (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
            (const char *)(unsigned int)v7,
            (int)hstringHeader.Reserved.Reserved1);
        v8 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
        v27 = 0;
        v9 = WindowsCreateStringReference(L"1", 1u, &v26, &v27);
        if ( v9 >= 0 )
        {
          v10 = v27;
          string = 0;
          v11 = WindowsCreateStringReference(L"KeyboardModeEnabled_full106", 0x1Bu, &hstringHeader, &string);
          if ( v11 >= 0 )
          {
            v12 = KeyboardHosting::TabTipAdapter::SetShellPreference(v8, string, v10);
            if ( v12 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x82A,
                (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
                (const char *)(unsigned int)v12,
                (int)hstringHeader.Reserved.Reserved1);
            return;
          }
          goto LABEL_29;
        }
LABEL_28:
        RaiseException(v9, 1u, 0, 0);
LABEL_29:
        RaiseException(v11, 1u, 0, 0);
        goto LABEL_30;
      }
    }
    RaiseException(v6, 1u, 0, 0);
    goto LABEL_28;
  }
  v13 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  v27 = 0;
  v14 = WindowsCreateStringReference(L"0", 1u, &v26, &v27);
  if ( v14 < 0 )
  {
LABEL_30:
    RaiseException(v14, 1u, 0, 0);
    goto LABEL_31;
  }
  v15 = v27;
  string = 0;
  v16 = WindowsCreateStringReference(L"KeyboardModeEnabled_full", 0x18u, &hstringHeader, &string);
  if ( v16 < 0 )
  {
LABEL_31:
    RaiseException(v16, 1u, 0, 0);
LABEL_32:
    RaiseException(v19, 1u, 0, 0);
    goto LABEL_33;
  }
  v17 = KeyboardHosting::TabTipAdapter::SetShellPreference(v13, string, v15);
  if ( v17 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x824,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v17,
      (int)hstringHeader.Reserved.Reserved1);
  v18 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  v27 = 0;
  v19 = WindowsCreateStringReference(L"0", 1u, &v26, &v27);
  if ( v19 < 0 )
    goto LABEL_32;
  v20 = v27;
  string = 0;
  v21 = WindowsCreateStringReference(L"KeyboardModeEnabled_full106", 0x1Bu, &hstringHeader, &string);
  if ( v21 < 0 )
  {
LABEL_33:
    RaiseException(v21, 1u, 0, 0);
    JUMPOUT(0x1800DFE3ELL);
  }
  v22 = KeyboardHosting::TabTipAdapter::SetShellPreference(v18, string, v20);
  if ( v22 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x825,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v22,
      (int)hstringHeader.Reserved.Reserved1);
}

```

## disassembly

```asm
0x1800dfad8  mov     [rsp-18h+arg_8], rbx
0x1800dfadd  mov     [rsp-18h+arg_10], rsi
0x1800dfae2  push    rbp
0x1800dfae3  push    rdi
0x1800dfae4  push    r14
0x1800dfae6  mov     rbp, rsp
0x1800dfae9  sub     rsp, 70h
0x1800dfaed  mov     rax, cs:__security_cookie
0x1800dfaf4  xor     rax, rsp
0x1800dfaf7  mov     [rbp+var_10], rax
0x1800dfafb  mov     rdi, rcx
0x1800dfafe  lea     rcx, aTouchkeyboardf; "TouchKeyboardFullModeAvailability"
0x1800dfb05  call    ?GetMdmPolicyValue@TextInputMdmPolicyHelper@KeyboardHosting@@SA?AW4MdmAvailabilityPolicy@2@PEBGW432@@Z; KeyboardHosting::TextInputMdmPolicyHelper::GetMdmPolicyValue(ushort const *,KeyboardHosting::MdmAvailabilityPolicy)
0x1800dfb0a  cmp     eax, 2
0x1800dfb0d  jz      loc_1800DFC2D
0x1800dfb13  test    eax, eax
0x1800dfb15  jz      loc_1800DFD1F
0x1800dfb1b  mov     rsi, [rdi+248h]
0x1800dfb22  mov     [rbp+string], 0
0x1800dfb2a  lea     r9, [rbp+string]; string
0x1800dfb2e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800dfb32  mov     ebx, 1
0x1800dfb37  mov     edx, ebx; length
0x1800dfb39  lea     rcx, a1; "1"
0x1800dfb40  call    cs:__imp_WindowsCreateStringReference
0x1800dfb46  test    eax, eax
0x1800dfb48  js      loc_1800DFDB7
0x1800dfb4e  mov     r14, [rbp+string]
0x1800dfb52  mov     [rbp+var_18], 0
0x1800dfb5a  lea     r9, [rbp+var_18]; string
0x1800dfb5e  lea     r8, [rbp+var_30]; hstringHeader
0x1800dfb62  lea     edx, [rbx+17h]; length
0x1800dfb65  lea     rcx, aKeyboardmodeen_0; "KeyboardModeEnabled_full"
0x1800dfb6c  call    cs:__imp_WindowsCreateStringReference
0x1800dfb72  test    eax, eax
0x1800dfb74  js      loc_1800DFDC8
0x1800dfb7a  mov     r8, r14; HSTRING
0x1800dfb7d  mov     rdx, [rbp+var_18]; HSTRING
0x1800dfb81  mov     rcx, rsi; this
0x1800dfb84  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800dfb89  mov     rcx, [rbp+18h]; this
0x1800dfb8d  test    eax, eax
0x1800dfb8f  js      loc_1800DFD41
0x1800dfb95  mov     rsi, [rdi+248h]
0x1800dfb9c  mov     [rbp+var_18], 0
0x1800dfba4  lea     r9, [rbp+var_18]; string
0x1800dfba8  lea     r8, [rbp+var_30]; hstringHeader
0x1800dfbac  mov     edx, ebx; length
0x1800dfbae  lea     rcx, a1; "1"
0x1800dfbb5  call    cs:__imp_WindowsCreateStringReference
0x1800dfbbb  test    eax, eax
0x1800dfbbd  js      loc_1800DFDD9
0x1800dfbc3  mov     rdi, [rbp+var_18]
0x1800dfbc7  mov     [rbp+string], 0
0x1800dfbcf  lea     r9, [rbp+string]; string
0x1800dfbd3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800dfbd7  mov     edx, 1Bh; length
0x1800dfbdc  lea     rcx, aKeyboardmodeen_4; "KeyboardModeEnabled_full106"
0x1800dfbe3  call    cs:__imp_WindowsCreateStringReference
0x1800dfbe9  test    eax, eax
0x1800dfbeb  js      loc_1800DFDEA
0x1800dfbf1  mov     r8, rdi; HSTRING
0x1800dfbf4  mov     rdx, [rbp+string]; HSTRING
0x1800dfbf8  mov     rcx, rsi; this
0x1800dfbfb  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800dfc00  mov     rcx, [rbp+18h]; this
0x1800dfc04  test    eax, eax
0x1800dfc06  js      loc_1800DFD5A
0x1800dfc0c  mov     rcx, [rbp+var_10]
0x1800dfc10  xor     rcx, rsp; StackCookie
0x1800dfc13  call    __security_check_cookie
0x1800dfc18  lea     r11, [rsp+70h+var_s0]
0x1800dfc1d  mov     rbx, [r11+28h]
0x1800dfc21  mov     rsi, [r11+30h]
0x1800dfc25  mov     rsp, r11
0x1800dfc28  pop     r14
0x1800dfc2a  pop     rdi
0x1800dfc2b  pop     rbp
0x1800dfc2c  retn
0x1800dfc2d  mov     rsi, [rdi+248h]
0x1800dfc34  mov     [rbp+var_18], 0
0x1800dfc3c  lea     r9, [rbp+var_18]; string
0x1800dfc40  lea     r8, [rbp+var_30]; hstringHeader
0x1800dfc44  mov     ebx, 1
0x1800dfc49  mov     edx, ebx; length
0x1800dfc4b  lea     rcx, a0_0; "0"
0x1800dfc52  call    cs:__imp_WindowsCreateStringReference
0x1800dfc58  test    eax, eax
0x1800dfc5a  js      loc_1800DFDFB
0x1800dfc60  mov     r14, [rbp+var_18]
0x1800dfc64  mov     [rbp+string], 0
0x1800dfc6c  lea     r9, [rbp+string]; string
0x1800dfc70  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800dfc74  lea     edx, [rbx+17h]; length
0x1800dfc77  lea     rcx, aKeyboardmodeen_0; "KeyboardModeEnabled_full"
0x1800dfc7e  call    cs:__imp_WindowsCreateStringReference
0x1800dfc84  test    eax, eax
0x1800dfc86  js      loc_1800DFE0C
0x1800dfc8c  mov     r8, r14; HSTRING
0x1800dfc8f  mov     rdx, [rbp+string]; HSTRING
0x1800dfc93  mov     rcx, rsi; this
0x1800dfc96  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800dfc9b  mov     rcx, [rbp+18h]; this
0x1800dfc9f  test    eax, eax
0x1800dfca1  js      loc_1800DFD73
0x1800dfca7  mov     rsi, [rdi+248h]
0x1800dfcae  mov     [rbp+var_18], 0
0x1800dfcb6  lea     r9, [rbp+var_18]; string
0x1800dfcba  lea     r8, [rbp+var_30]; hstringHeader
0x1800dfcbe  mov     edx, ebx; length
0x1800dfcc0  lea     rcx, a0_0; "0"
0x1800dfcc7  call    cs:__imp_WindowsCreateStringReference
0x1800dfccd  test    eax, eax
0x1800dfccf  js      loc_1800DFE1D
0x1800dfcd5  mov     rdi, [rbp+var_18]
0x1800dfcd9  mov     [rbp+string], 0
0x1800dfce1  lea     r9, [rbp+string]; string
0x1800dfce5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800dfce9  mov     edx, 1Bh; length
0x1800dfcee  lea     rcx, aKeyboardmodeen_4; "KeyboardModeEnabled_full106"
0x1800dfcf5  call    cs:__imp_WindowsCreateStringReference
0x1800dfcfb  test    eax, eax
0x1800dfcfd  js      loc_1800DFE2E
0x1800dfd03  mov     r8, rdi; HSTRING
0x1800dfd06  mov     rdx, [rbp+string]; HSTRING
0x1800dfd0a  mov     rcx, rsi; this
0x1800dfd0d  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800dfd12  mov     rcx, [rbp+18h]; this
0x1800dfd16  test    eax, eax
0x1800dfd18  js      short loc_1800DFD8C
0x1800dfd1a  jmp     loc_1800DFC0C
0x1800dfd1f  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x1800dfd26  call    IsUserAssignedAccessSingleApp
0x1800dfd2b  test    eax, eax
0x1800dfd2d  jz      short loc_1800DFDA5
0x1800dfd2f  call    ?IsCompatibilityKeyboardEnabled@TouchKeyboardExperienceManager@@AEBA_NXZ; TouchKeyboardExperienceManager::IsCompatibilityKeyboardEnabled(void)
0x1800dfd34  test    al, al
0x1800dfd36  jnz     loc_1800DFB1B
0x1800dfd3c  jmp     loc_1800DFC2D
0x1800dfd41  mov     r9d, eax; char *
0x1800dfd44  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800dfd4b  mov     edx, 829h; void *
0x1800dfd50  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dfd55  jmp     loc_1800DFB95
0x1800dfd5a  mov     r9d, eax; char *
0x1800dfd5d  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800dfd64  mov     edx, 82Ah; void *
0x1800dfd69  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dfd6e  jmp     loc_1800DFC0C
0x1800dfd73  mov     r9d, eax; char *
0x1800dfd76  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800dfd7d  mov     edx, 824h; void *
0x1800dfd82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dfd87  jmp     loc_1800DFCA7
0x1800dfd8c  mov     r9d, eax; char *
0x1800dfd8f  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800dfd96  mov     edx, 825h; void *
0x1800dfd9b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dfda0  jmp     loc_1800DFD1A
0x1800dfda5  call    ?IsKeyboardFilterServiceRunning@TouchKeyboardExperienceManager@@AEBA_NXZ; TouchKeyboardExperienceManager::IsKeyboardFilterServiceRunning(void)
0x1800dfdaa  test    al, al
0x1800dfdac  jz      loc_1800DFB1B
0x1800dfdb2  jmp     loc_1800DFD2F
0x1800dfdb7  xor     r9d, r9d; lpArguments
0x1800dfdba  xor     r8d, r8d; nNumberOfArguments
0x1800dfdbd  mov     edx, ebx; dwExceptionFlags
0x1800dfdbf  mov     ecx, eax; dwExceptionCode
0x1800dfdc1  call    cs:__imp_RaiseException
0x1800dfdc7  nop
0x1800dfdc8  xor     r9d, r9d; lpArguments
0x1800dfdcb  xor     r8d, r8d; nNumberOfArguments
0x1800dfdce  mov     edx, ebx; dwExceptionFlags
0x1800dfdd0  mov     ecx, eax; dwExceptionCode
0x1800dfdd2  call    cs:__imp_RaiseException
0x1800dfdd8  nop
0x1800dfdd9  xor     r9d, r9d; lpArguments
0x1800dfddc  xor     r8d, r8d; nNumberOfArguments
0x1800dfddf  mov     edx, ebx; dwExceptionFlags
0x1800dfde1  mov     ecx, eax; dwExceptionCode
0x1800dfde3  call    cs:__imp_RaiseException
0x1800dfde9  nop
0x1800dfdea  xor     r9d, r9d; lpArguments
0x1800dfded  xor     r8d, r8d; nNumberOfArguments
0x1800dfdf0  mov     edx, ebx; dwExceptionFlags
0x1800dfdf2  mov     ecx, eax; dwExceptionCode
0x1800dfdf4  call    cs:__imp_RaiseException
0x1800dfdfa  nop
0x1800dfdfb  xor     r9d, r9d; lpArguments
0x1800dfdfe  xor     r8d, r8d; nNumberOfArguments
0x1800dfe01  mov     edx, ebx; dwExceptionFlags
0x1800dfe03  mov     ecx, eax; dwExceptionCode
0x1800dfe05  call    cs:__imp_RaiseException
0x1800dfe0b  nop
0x1800dfe0c  xor     r9d, r9d; lpArguments
0x1800dfe0f  xor     r8d, r8d; nNumberOfArguments
0x1800dfe12  mov     edx, ebx; dwExceptionFlags
0x1800dfe14  mov     ecx, eax; dwExceptionCode
0x1800dfe16  call    cs:__imp_RaiseException
0x1800dfe1c  nop
0x1800dfe1d  xor     r9d, r9d; lpArguments
0x1800dfe20  xor     r8d, r8d; nNumberOfArguments
0x1800dfe23  mov     edx, ebx; dwExceptionFlags
0x1800dfe25  mov     ecx, eax; dwExceptionCode
0x1800dfe27  call    cs:__imp_RaiseException
0x1800dfe2d  nop
0x1800dfe2e  xor     r9d, r9d; lpArguments
0x1800dfe31  xor     r8d, r8d; nNumberOfArguments
0x1800dfe34  mov     edx, ebx; dwExceptionFlags
0x1800dfe36  mov     ecx, eax; dwExceptionCode
0x1800dfe38  call    cs:__imp_RaiseException
```
