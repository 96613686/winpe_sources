# TouchKeyboardExperienceManager::UpdateOobeRunningState(void)

- ea: `0x1800e02bc`
- end: `0x1800e05e1`
- name: `?UpdateOobeRunningState@TouchKeyboardExperienceManager@@AEAAXXZ`
- size: `805`
- prototype: `void __fastcall(TouchKeyboardExperienceManager *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180228770`
- `0x1804bc1c0`

## callees

- `0x180031c70`
- `0x18005d940`
- `0x1800e02bc`
- `0x1800e0728`
- `0x1800e0844`
- `0x180356360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e04f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e0507`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e051d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e057b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e058e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e05a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e05b4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e05c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e05da`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e04f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e0507`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e051d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e057b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e058e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e05a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e05b4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e05c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e05da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e0341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e036b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e03e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e0411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e0472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e049c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e0341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e036b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e03e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e0411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e0472`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e049c`

## string_xrefs

- `0x1800e0364`: `IsOobeCompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TouchKeyboardExperienceManager::UpdateOobeRunningState(TouchKeyboardExperienceManager *this)
{
  const WCHAR *v2; // rsi
  const WCHAR *v3; // r14
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // rdi
  KeyboardHosting::TabTipAdapter *v6; // r15
  unsigned int v7; // eax
  UINT32 v8; // edx
  HRESULT v9; // eax
  HSTRING v10; // rdi
  HRESULT v11; // eax
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  unsigned __int64 v14; // rdi
  KeyboardHosting::TabTipAdapter *v15; // r14
  unsigned int v16; // eax
  UINT32 v17; // edx
  HRESULT v18; // eax
  HSTRING v19; // rdi
  HRESULT v20; // eax
  int v21; // eax
  KeyboardHosting::TabTipAdapter *v22; // rdi
  unsigned int v23; // eax
  UINT32 v24; // edx
  HRESULT v25; // eax
  HSTRING v26; // rbx
  HRESULT v27; // eax
  int v28; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER v31; // [rsp+40h] [rbp-38h] BYREF
  HSTRING v32; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v2 = L"1";
  v3 = L"0";
  if ( !IsAnyOOBE() )
    v3 = L"1";
  string = 0;
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( v3[v5] );
  if ( v5 <= 0xFFFFFFFF )
  {
    v6 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
    v7 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v5);
    v8 = v7 - 1;
    if ( (unsigned int)v5 < v7 )
      v8 = v5;
    v9 = WindowsCreateStringReference(v3, v8, &hstringHeader, &string);
    if ( v9 < 0 )
    {
      RaiseException(v9, 1u, 0, 0);
    }
    else
    {
      v10 = string;
      v32 = 0;
      v11 = WindowsCreateStringReference(L"IsOobeCompleted", 0xFu, &v31, &v32);
      if ( v11 >= 0 )
      {
        v12 = KeyboardHosting::TabTipAdapter::SetShellPreference(v6, v32, v10);
        v13 = retaddr;
        if ( v12 >= 0 )
          goto LABEL_11;
        goto LABEL_34;
      }
    }
    RaiseException(v11, 1u, 0, 0);
LABEL_38:
    RaiseException(v18, 1u, 0, 0);
    goto LABEL_39;
  }
  RaiseException(0x80070216, 1u, 0, 0);
LABEL_34:
  wil::details::in1diag3::_Log_Hr(
    v13,
    (void *)0x9EC,
    (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
    (const char *)(unsigned int)v12,
    (int)hstringHeader.Reserved.Reserved1);
LABEL_11:
  if ( !IsAnyOOBE() )
    v2 = L"0";
  v32 = 0;
  v14 = -1;
  do
    ++v14;
  while ( v2[v14] );
  if ( v14 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v15 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  v16 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v14);
  v17 = v16 - 1;
  if ( (unsigned int)v14 < v16 )
    v17 = v14;
  v18 = WindowsCreateStringReference(v2, v17, &v31, &v32);
  if ( v18 < 0 )
    goto LABEL_38;
  v19 = v32;
  string = 0;
  v20 = WindowsCreateStringReference(L"ToolBar\\AlwaysShow", 0x12u, &hstringHeader, &string);
  if ( v20 < 0 )
  {
LABEL_39:
    RaiseException(v20, 1u, 0, 0);
LABEL_40:
    RaiseException(v25, 1u, 0, 0);
    goto LABEL_41;
  }
  v21 = KeyboardHosting::TabTipAdapter::SetShellPreference(v15, string, v19);
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9F0,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v21,
      (int)hstringHeader.Reserved.Reserved1);
  v32 = 0;
  do
    ++v4;
  while ( v2[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v22 = (KeyboardHosting::TabTipAdapter *)*((_QWORD *)this + 73);
  v23 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v4);
  v24 = v23 - 1;
  if ( (unsigned int)v4 < v23 )
    v24 = v4;
  v25 = WindowsCreateStringReference(v2, v24, &v31, &v32);
  if ( v25 < 0 )
    goto LABEL_40;
  v26 = v32;
  string = 0;
  v27 = WindowsCreateStringReference(L"ToolBar\\MinifiedMode", 0x14u, &hstringHeader, &string);
  if ( v27 < 0 )
  {
LABEL_41:
    RaiseException(v27, 1u, 0, 0);
    JUMPOUT(0x1800E05E0LL);
  }
  v28 = KeyboardHosting::TabTipAdapter::SetShellPreference(v22, string, v26);
  if ( v28 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x9F1,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v28,
      (int)hstringHeader.Reserved.Reserved1);
}

```

## disassembly

```asm
0x1800e02bc  push    rbp
0x1800e02be  push    rbx
0x1800e02bf  push    rsi
0x1800e02c0  push    rdi
0x1800e02c1  push    r12
0x1800e02c3  push    r13
0x1800e02c5  push    r14
0x1800e02c7  push    r15
0x1800e02c9  mov     rbp, rsp
0x1800e02cc  sub     rsp, 78h
0x1800e02d0  mov     rax, cs:__security_cookie
0x1800e02d7  xor     rax, rsp
0x1800e02da  mov     [rbp+var_18], rax
0x1800e02de  mov     r13, rcx
0x1800e02e1  call    ?IsAnyOOBE@@YA_NXZ; IsAnyOOBE(void)
0x1800e02e6  lea     rsi, a1; "1"
0x1800e02ed  lea     r14, a0_0; "0"
0x1800e02f4  xor     r12d, r12d
0x1800e02f7  test    al, al
0x1800e02f9  cmovz   r14, rsi
0x1800e02fd  mov     [rbp+string], r12
0x1800e0301  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800e0305  mov     rdi, rbx
0x1800e0308  inc     rdi
0x1800e030b  cmp     [r14+rdi*2], r12w
0x1800e0310  jnz     short loc_1800E0308
0x1800e0312  mov     eax, 0FFFFFFFFh
0x1800e0317  cmp     rdi, rax
0x1800e031a  ja      loc_1800E050E
0x1800e0320  mov     r15, [r13+248h]
0x1800e0327  mov     ecx, edi; unsigned int
0x1800e0329  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800e032e  lea     edx, [rax-1]
0x1800e0331  cmp     edi, eax
0x1800e0333  cmovb   edx, edi; length
0x1800e0336  lea     r9, [rbp+string]; string
0x1800e033a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800e033e  mov     rcx, r14; sourceString
0x1800e0341  call    cs:__imp_WindowsCreateStringReference
0x1800e0347  test    eax, eax
0x1800e0349  js      loc_1800E056F
0x1800e034f  mov     rdi, [rbp+string]
0x1800e0353  mov     [rbp+var_20], r12
0x1800e0357  lea     r9, [rbp+var_20]; string
0x1800e035b  lea     r8, [rbp+var_38]; hstringHeader
0x1800e035f  mov     edx, 0Fh; length
0x1800e0364  lea     rcx, aIsoobecomplete; "IsOobeCompleted"
0x1800e036b  call    cs:__imp_WindowsCreateStringReference
0x1800e0371  test    eax, eax
0x1800e0373  js      loc_1800E0582
0x1800e0379  mov     r8, rdi; HSTRING
0x1800e037c  mov     rdx, [rbp+var_20]; HSTRING
0x1800e0380  mov     rcx, r15; this
0x1800e0383  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800e0388  mov     rcx, [rbp+40h]
0x1800e038c  test    eax, eax
0x1800e038e  js      loc_1800E0524
0x1800e0394  call    ?IsAnyOOBE@@YA_NXZ; IsAnyOOBE(void)
0x1800e0399  test    al, al
0x1800e039b  lea     rax, a0_0; "0"
0x1800e03a2  cmovz   rsi, rax
0x1800e03a6  mov     [rbp+var_20], r12
0x1800e03aa  mov     rdi, rbx
0x1800e03ad  inc     rdi
0x1800e03b0  cmp     [rsi+rdi*2], r12w
0x1800e03b5  jnz     short loc_1800E03AD
0x1800e03b7  mov     r15d, 0FFFFFFFFh
0x1800e03bd  cmp     rdi, r15
0x1800e03c0  ja      loc_1800E04F8
0x1800e03c6  mov     r14, [r13+248h]
0x1800e03cd  mov     ecx, edi; unsigned int
0x1800e03cf  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800e03d4  lea     edx, [rax-1]
0x1800e03d7  cmp     edi, eax
0x1800e03d9  cmovb   edx, edi; length
0x1800e03dc  lea     r9, [rbp+var_20]; string
0x1800e03e0  lea     r8, [rbp+var_38]; hstringHeader
0x1800e03e4  mov     rcx, rsi; sourceString
0x1800e03e7  call    cs:__imp_WindowsCreateStringReference
0x1800e03ed  test    eax, eax
0x1800e03ef  js      loc_1800E0595
0x1800e03f5  mov     rdi, [rbp+var_20]
0x1800e03f9  mov     [rbp+string], r12
0x1800e03fd  lea     r9, [rbp+string]; string
0x1800e0401  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800e0405  mov     edx, 12h; length
0x1800e040a  lea     rcx, aToolbarAlwayss; "ToolBar\\AlwaysShow"
0x1800e0411  call    cs:__imp_WindowsCreateStringReference
0x1800e0417  test    eax, eax
0x1800e0419  js      loc_1800E05A8
0x1800e041f  mov     r8, rdi; HSTRING
0x1800e0422  mov     rdx, [rbp+string]; HSTRING
0x1800e0426  mov     rcx, r14; this
0x1800e0429  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800e042e  mov     rcx, [rbp+40h]; this
0x1800e0432  test    eax, eax
0x1800e0434  js      loc_1800E053D
0x1800e043a  mov     [rbp+var_20], r12
0x1800e043e  inc     rbx
0x1800e0441  cmp     [rsi+rbx*2], r12w
0x1800e0446  jnz     short loc_1800E043E
0x1800e0448  cmp     rbx, r15
0x1800e044b  ja      loc_1800E04E2
0x1800e0451  mov     rdi, [r13+248h]
0x1800e0458  mov     ecx, ebx; unsigned int
0x1800e045a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800e045f  lea     edx, [rax-1]
0x1800e0462  cmp     ebx, eax
0x1800e0464  cmovb   edx, ebx; length
0x1800e0467  lea     r9, [rbp+var_20]; string
0x1800e046b  lea     r8, [rbp+var_38]; hstringHeader
0x1800e046f  mov     rcx, rsi; sourceString
0x1800e0472  call    cs:__imp_WindowsCreateStringReference
0x1800e0478  test    eax, eax
0x1800e047a  js      loc_1800E05BB
0x1800e0480  mov     rbx, [rbp+var_20]
0x1800e0484  mov     [rbp+string], r12
0x1800e0488  lea     r9, [rbp+string]; string
0x1800e048c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800e0490  mov     edx, 14h; length
0x1800e0495  lea     rcx, aToolbarMinifie; "ToolBar\\MinifiedMode"
0x1800e049c  call    cs:__imp_WindowsCreateStringReference
0x1800e04a2  test    eax, eax
0x1800e04a4  js      loc_1800E05CE
0x1800e04aa  mov     r8, rbx; HSTRING
0x1800e04ad  mov     rdx, [rbp+string]; HSTRING
0x1800e04b1  mov     rcx, rdi; this
0x1800e04b4  call    ?SetShellPreference@TabTipAdapter@KeyboardHosting@@QEAAJPEAUHSTRING__@@0@Z; KeyboardHosting::TabTipAdapter::SetShellPreference(HSTRING__ *,HSTRING__ *)
0x1800e04b9  mov     rcx, [rbp+40h]; this
0x1800e04bd  test    eax, eax
0x1800e04bf  js      loc_1800E0556
0x1800e04c5  mov     rcx, [rbp+var_18]
0x1800e04c9  xor     rcx, rsp; StackCookie
0x1800e04cc  call    __security_check_cookie
0x1800e04d1  add     rsp, 78h
0x1800e04d5  pop     r15
0x1800e04d7  pop     r14
0x1800e04d9  pop     r13
0x1800e04db  pop     r12
0x1800e04dd  pop     rdi
0x1800e04de  pop     rsi
0x1800e04df  pop     rbx
0x1800e04e0  pop     rbp
0x1800e04e1  retn
0x1800e04e2  xor     r9d, r9d; lpArguments
0x1800e04e5  xor     r8d, r8d; nNumberOfArguments
0x1800e04e8  lea     edx, [r9+1]; dwExceptionFlags
0x1800e04ec  mov     ecx, 80070216h; dwExceptionCode
0x1800e04f1  call    cs:__imp_RaiseException
0x1800e04f7  int     3; Trap to Debugger
0x1800e04f8  xor     r9d, r9d; lpArguments
0x1800e04fb  xor     r8d, r8d; nNumberOfArguments
0x1800e04fe  lea     edx, [r9+1]; dwExceptionFlags
0x1800e0502  mov     ecx, 80070216h; dwExceptionCode
0x1800e0507  call    cs:__imp_RaiseException
0x1800e050d  int     3; Trap to Debugger
0x1800e050e  xor     r9d, r9d; lpArguments
0x1800e0511  xor     r8d, r8d; nNumberOfArguments
0x1800e0514  lea     edx, [r9+1]; dwExceptionFlags
0x1800e0518  mov     ecx, 80070216h; dwExceptionCode
0x1800e051d  call    cs:__imp_RaiseException
0x1800e0523  nop
0x1800e0524  mov     r9d, eax; char *
0x1800e0527  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800e052e  mov     edx, 9ECh; void *
0x1800e0533  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e0538  jmp     loc_1800E0394
0x1800e053d  mov     r9d, eax; char *
0x1800e0540  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800e0547  mov     edx, 9F0h; void *
0x1800e054c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e0551  jmp     loc_1800E043A
0x1800e0556  mov     r9d, eax; char *
0x1800e0559  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800e0560  mov     edx, 9F1h; void *
0x1800e0565  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e056a  jmp     loc_1800E04C5
0x1800e056f  xor     r9d, r9d; lpArguments
0x1800e0572  xor     r8d, r8d; nNumberOfArguments
0x1800e0575  lea     edx, [r9+1]; dwExceptionFlags
0x1800e0579  mov     ecx, eax; dwExceptionCode
0x1800e057b  call    cs:__imp_RaiseException
0x1800e0581  nop
0x1800e0582  xor     r9d, r9d; lpArguments
0x1800e0585  xor     r8d, r8d; nNumberOfArguments
0x1800e0588  lea     edx, [r9+1]; dwExceptionFlags
0x1800e058c  mov     ecx, eax; dwExceptionCode
0x1800e058e  call    cs:__imp_RaiseException
0x1800e0594  nop
0x1800e0595  xor     r9d, r9d; lpArguments
0x1800e0598  xor     r8d, r8d; nNumberOfArguments
0x1800e059b  lea     edx, [r9+1]; dwExceptionFlags
0x1800e059f  mov     ecx, eax; dwExceptionCode
0x1800e05a1  call    cs:__imp_RaiseException
0x1800e05a7  nop
0x1800e05a8  xor     r9d, r9d; lpArguments
0x1800e05ab  xor     r8d, r8d; nNumberOfArguments
0x1800e05ae  lea     edx, [r9+1]; dwExceptionFlags
0x1800e05b2  mov     ecx, eax; dwExceptionCode
0x1800e05b4  call    cs:__imp_RaiseException
0x1800e05ba  nop
0x1800e05bb  xor     r9d, r9d; lpArguments
0x1800e05be  xor     r8d, r8d; nNumberOfArguments
0x1800e05c1  lea     edx, [r9+1]; dwExceptionFlags
0x1800e05c5  mov     ecx, eax; dwExceptionCode
0x1800e05c7  call    cs:__imp_RaiseException
0x1800e05cd  nop
0x1800e05ce  xor     r9d, r9d; lpArguments
0x1800e05d1  xor     r8d, r8d; nNumberOfArguments
0x1800e05d4  lea     edx, [r9+1]; dwExceptionFlags
0x1800e05d8  mov     ecx, eax; dwExceptionCode
0x1800e05da  call    cs:__imp_RaiseException
```
