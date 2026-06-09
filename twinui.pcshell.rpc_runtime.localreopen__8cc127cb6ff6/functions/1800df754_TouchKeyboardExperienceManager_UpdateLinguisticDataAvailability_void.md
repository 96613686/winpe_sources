# TouchKeyboardExperienceManager::UpdateLinguisticDataAvailability(void)

- ea: `0x1800df754`
- end: `0x1800df93c`
- name: `?UpdateLinguisticDataAvailability@TouchKeyboardExperienceManager@@AEAAXXZ`
- size: `488`
- prototype: `void __fastcall(TouchKeyboardExperienceManager *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180228770`
- `0x1804b9ff0`

## callees

- `0x180031c70`
- `0x1800df754`
- `0x1800e0728`
- `0x180356360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df8ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df911`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df923`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df935`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df8ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df911`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df923`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800df935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df7d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df7fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df7d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df7fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df854`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800df882`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800df78e`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800df78e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TouchKeyboardExperienceManager::UpdateLinguisticDataAvailability(TouchKeyboardExperienceManager *this)
{
  int PolicyInt; // eax
  KeyboardHosting::TabTipAdapter *v3; // rbx
  HRESULT v4; // eax
  HSTRING v5; // rdi
  HRESULT v6; // eax
  int v7; // eax
  HRESULT v8; // eax
  HSTRING v9; // rdi
  HRESULT v10; // eax
  int v11; // eax
  int v12; // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-50h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER v15; // [rsp+48h] [rbp-30h] BYREF
  HSTRING v16; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v12 = 1;
  PolicyInt = PolicyManager_GetPolicyInt(L"TextInput", L"AllowLinguisticDataCollection", &v12);
  if ( PolicyInt < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8E6,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)PolicyInt,
      v12);
  v3 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  if ( v12 != 1 )
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
      v16 = 0;
      v6 = WindowsCreateStringReference(L"LinguisticDataCollectionEnabled", 0x1Fu, &v15, &v16);
      if ( v6 >= 0 )
      {
        v7 = KeyboardHosting::TabTipAdapter::SetShellPreference(v3, v16, v5);
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x8EC,
            (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
            (const char *)(unsigned int)v7,
            v12);
        return;
      }
    }
    RaiseException(v6, 1u, 0, 0);
    goto LABEL_16;
  }
  v16 = 0;
  v8 = WindowsCreateStringReference(L"1", 1u, &v15, &v16);
  if ( v8 < 0 )
  {
LABEL_16:
    RaiseException(v8, 1u, 0, 0);
    goto LABEL_17;
  }
  v9 = v16;
  string = 0;
  v10 = WindowsCreateStringReference(L"LinguisticDataCollectionEnabled", 0x1Fu, &hstringHeader, &string);
  if ( v10 < 0 )
  {
LABEL_17:
    RaiseException(v10, 1u, 0, 0);
    JUMPOUT(0x1800DF93BLL);
  }
  v11 = KeyboardHosting::TabTipAdapter::SetShellPreference(v3, string, v9);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x8F0,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v11,
      v12);
}

```

## disassembly

```asm
0x1800df754  push    rbp
0x1800df756  push    rbx
0x1800df757  push    rdi
0x1800df758  push    r14
0x1800df75a  mov     rbp, rsp
0x1800df75d  sub     rsp, 78h
0x1800df761  mov     rax, cs:__security_cookie
0x1800df768  xor     rax, rsp
0x1800df76b  mov     [rbp+var_10], rax
0x1800df76f  mov     rbx, rcx
0x1800df772  mov     r14d, 1
0x1800df778  mov     [rbp+var_58], r14d
0x1800df77c  lea     r8, [rbp+var_58]
0x1800df780  lea     rdx, aAllowlinguisti; "AllowLinguisticDataCollection"
0x1800df787  lea     rcx, aTextinput; "TextInput"
0x1800df78e  call    cs:__imp_PolicyManager_GetPolicyInt
0x1800df794  mov     rcx, [rbp+20h]; this
0x1800df798  test    eax, eax
0x1800df79a  js      loc_1800DF8AC
0x1800df7a0  cmp     [rbp+var_58], r14d
0x1800df7a4  setz    al
0x1800df7a7  mov     rbx, [rbx+248h]
0x1800df7ae  mov     edx, r14d; length
0x1800df7b1  test    al, al
0x1800df7b3  jnz     loc_1800DF83D
0x1800df7b9  mov     [rbp+string], 0
0x1800df7c1  lea     r9, [rbp+string]; string
0x1800df7c5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800df7c9  lea     rcx, a0_0; "0"
0x1800df7d0  call    cs:__imp_WindowsCreateStringReference
0x1800df7d6  test    eax, eax
0x1800df7d8  js      loc_1800DF8F4
0x1800df7de  mov     rdi, [rbp+string]
0x1800df7e2  mov     [rbp+var_18], 0
0x1800df7ea  lea     r9, [rbp+var_18]; string
0x1800df7ee  lea     r8, [rbp+var_30]; hstringHeader
0x1800df7f2  mov     edx, 1Fh; length
0x1800df7f7  lea     rcx, aLinguisticdata; "LinguisticDataCollectionEnabled"
0x1800df7fe  call    cs:__imp_WindowsCreateStringReference
0x1800df804  test    eax, eax
0x1800df806  js      loc_1800DF906
0x1800df80c  mov     r8, rdi; HSTRING
0x1800df80f  mov     rdx, [rbp+var_18]; HSTRING
0x1800df813  mov     rcx, rbx; this
0x1800df816  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800df81b  mov     rcx, [rbp+20h]; this
0x1800df81f  test    eax, eax
0x1800df821  js      loc_1800DF8C5
0x1800df827  mov     rcx, [rbp+var_10]
0x1800df82b  xor     rcx, rsp; StackCookie
0x1800df82e  call    __security_check_cookie
0x1800df833  add     rsp, 78h
0x1800df837  pop     r14
0x1800df839  pop     rdi
0x1800df83a  pop     rbx
0x1800df83b  pop     rbp
0x1800df83c  retn
0x1800df83d  mov     [rbp+var_18], 0
0x1800df845  lea     r9, [rbp+var_18]; string
0x1800df849  lea     r8, [rbp+var_30]; hstringHeader
0x1800df84d  lea     rcx, a1; "1"
0x1800df854  call    cs:__imp_WindowsCreateStringReference
0x1800df85a  test    eax, eax
0x1800df85c  js      loc_1800DF918
0x1800df862  mov     rdi, [rbp+var_18]
0x1800df866  mov     [rbp+string], 0
0x1800df86e  lea     r9, [rbp+string]; string
0x1800df872  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800df876  mov     edx, 1Fh; length
0x1800df87b  lea     rcx, aLinguisticdata; "LinguisticDataCollectionEnabled"
0x1800df882  call    cs:__imp_WindowsCreateStringReference
0x1800df888  test    eax, eax
0x1800df88a  js      loc_1800DF92A
0x1800df890  mov     r8, rdi; HSTRING
0x1800df893  mov     rdx, [rbp+string]; HSTRING
0x1800df897  mov     rcx, rbx; this
0x1800df89a  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800df89f  mov     rcx, [rbp+20h]; this
0x1800df8a3  test    eax, eax
0x1800df8a5  js      short loc_1800DF8DE
0x1800df8a7  jmp     loc_1800DF827
0x1800df8ac  mov     r9d, eax; char *
0x1800df8af  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800df8b6  mov     edx, 8E6h; void *
0x1800df8bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df8c0  jmp     loc_1800DF7A0
0x1800df8c5  mov     r9d, eax; char *
0x1800df8c8  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800df8cf  mov     edx, 8ECh; void *
0x1800df8d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df8d9  jmp     loc_1800DF827
0x1800df8de  mov     r9d, eax; char *
0x1800df8e1  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800df8e8  mov     edx, 8F0h; void *
0x1800df8ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800df8f2  jmp     short loc_1800DF8A7
0x1800df8f4  xor     r9d, r9d; lpArguments
0x1800df8f7  xor     r8d, r8d; nNumberOfArguments
0x1800df8fa  mov     edx, r14d; dwExceptionFlags
0x1800df8fd  mov     ecx, eax; dwExceptionCode
0x1800df8ff  call    cs:__imp_RaiseException
0x1800df905  nop
0x1800df906  xor     r9d, r9d; lpArguments
0x1800df909  xor     r8d, r8d; nNumberOfArguments
0x1800df90c  mov     edx, r14d; dwExceptionFlags
0x1800df90f  mov     ecx, eax; dwExceptionCode
0x1800df911  call    cs:__imp_RaiseException
0x1800df917  nop
0x1800df918  xor     r9d, r9d; lpArguments
0x1800df91b  xor     r8d, r8d; nNumberOfArguments
0x1800df91e  mov     edx, r14d; dwExceptionFlags
0x1800df921  mov     ecx, eax; dwExceptionCode
0x1800df923  call    cs:__imp_RaiseException
0x1800df929  nop
0x1800df92a  xor     r9d, r9d; lpArguments
0x1800df92d  xor     r8d, r8d; nNumberOfArguments
0x1800df930  mov     edx, r14d; dwExceptionFlags
0x1800df933  mov     ecx, eax; dwExceptionCode
0x1800df935  call    cs:__imp_RaiseException
```
