# UtilIsEdu(ulong *)

- ea: `0x180028bf8`
- end: `0x180028d40`
- name: `?UtilIsEdu@@YAJPEAK@Z`
- size: `328`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017a18`

## callees

- `0x180028bf8`
- `0x18003db78`
- `0x180043d04`
- `0x180050db0`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028c8d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180028c8d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180028ca3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180028ca3`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180028c24`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180028c24`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180028cf3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180028d1a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180028cf3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180028d1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180028c77`

## string_xrefs

- `0x180028c37`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x180028cd8`: `onecore\windows\feedback\core\common\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UtilIsEdu(unsigned int *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  HRESULT v5; // eax
  int ActivationFactory; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // [rsp+20h] [rbp-40h] BYREF
  __int64 v11; // [rsp+28h] [rbp-38h] BYREF
  char v12; // [rsp+31h] [rbp-2Fh]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  LOBYTE(v10) = 0;
  v2 = RoInitialize(1);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15AD,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)(unsigned int)v2,
      v10);
    return v3;
  }
  v12 = 1;
  v11 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(L"Windows.System.Profile.EducationSettings", 0x28u, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_fc53f0ef_4d3e_4e13_9b23_505f4d091e92, &v11);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = 5558;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utility.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v10);
    utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(&v11);
    RoUninitialize(v8);
    return v3;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 48LL))(v11, &v10);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = 5560;
    goto LABEL_10;
  }
  v9 = v11;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  *a1 = (unsigned __int8)v10;
  RoUninitialize(v9);
  return 0;
}

```

## disassembly

```asm
0x180028bf8  mov     [rsp-8+arg_8], rbx
0x180028bfd  mov     [rsp-8+arg_10], rdi
0x180028c02  push    rbp
0x180028c03  mov     rbp, rsp
0x180028c06  sub     rsp, 60h
0x180028c0a  mov     rax, cs:__security_cookie
0x180028c11  xor     rax, rsp
0x180028c14  mov     [rbp+var_8], rax
0x180028c18  mov     rdi, rcx
0x180028c1b  mov     byte ptr [rbp+var_40], 0
0x180028c1f  mov     ecx, 1
0x180028c24  call    cs:__imp_RoInitialize
0x180028c2a  mov     ebx, eax
0x180028c2c  test    eax, eax
0x180028c2e  jns     short loc_180028C4F
0x180028c30  mov     rcx, [rbp+8]; this
0x180028c34  mov     r9d, eax; char *
0x180028c37  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x180028c3e  mov     edx, 15ADh; void *
0x180028c43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c48  mov     eax, ebx
0x180028c4a  jmp     loc_180028D22
0x180028c4f  mov     [rbp+var_2F], 1
0x180028c53  mov     [rbp+var_38], 0
0x180028c5b  mov     [rbp+string], 0
0x180028c63  lea     r9, [rbp+string]; string
0x180028c67  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180028c6b  mov     edx, 28h ; '('; length
0x180028c70  lea     rcx, ?RuntimeClass_Windows_System_Profile_EducationSettings@@3QB_WB; "Windows.System.Profile.EducationSetting"...
0x180028c77  call    cs:__imp_WindowsCreateStringReference
0x180028c7d  test    eax, eax
0x180028c7f  jns     short loc_180028C94
0x180028c81  xor     r9d, r9d; lpArguments
0x180028c84  xor     r8d, r8d; nNumberOfArguments
0x180028c87  lea     edx, [r9+1]; dwExceptionFlags
0x180028c8b  mov     ecx, eax; dwExceptionCode
0x180028c8d  call    cs:__imp_RaiseException
0x180028c93  int     3; Trap to Debugger
0x180028c94  lea     r8, [rbp+var_38]
0x180028c98  lea     rdx, _GUID_fc53f0ef_4d3e_4e13_9b23_505f4d091e92
0x180028c9f  mov     rcx, [rbp+string]
0x180028ca3  call    cs:__imp_RoGetActivationFactory
0x180028ca9  mov     ebx, eax
0x180028cab  test    eax, eax
0x180028cad  jns     short loc_180028CB6
0x180028caf  mov     edx, 15B6h
0x180028cb4  jmp     short loc_180028CD5
0x180028cb6  mov     rcx, [rbp+var_38]
0x180028cba  mov     rax, [rcx]
0x180028cbd  lea     rdx, [rbp+var_40]
0x180028cc1  mov     rax, [rax+30h]
0x180028cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cca  mov     ebx, eax
0x180028ccc  test    eax, eax
0x180028cce  jns     short loc_180028CFE
0x180028cd0  mov     edx, 15B8h; void *
0x180028cd5  mov     r9d, eax; char *
0x180028cd8  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x180028cdf  mov     rcx, [rbp+8]; this
0x180028ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ce8  nop
0x180028ce9  lea     rcx, [rbp+var_38]
0x180028ced  call    ??1?$unique_ptr@UIXmlWriter@@Urelease_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(void)
0x180028cf2  nop
0x180028cf3  call    cs:__imp_RoUninitialize
0x180028cf9  jmp     loc_180028C48
0x180028cfe  mov     rcx, [rbp+var_38]
0x180028d02  test    rcx, rcx
0x180028d05  jz      short loc_180028D14
0x180028d07  mov     rax, [rcx]
0x180028d0a  mov     rax, [rax+10h]
0x180028d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d13  nop
0x180028d14  movzx   eax, byte ptr [rbp+var_40]
0x180028d18  mov     [rdi], eax
0x180028d1a  call    cs:__imp_RoUninitialize
0x180028d20  xor     eax, eax
0x180028d22  mov     rcx, [rbp+var_8]
0x180028d26  xor     rcx, rsp; StackCookie
0x180028d29  call    __security_check_cookie
0x180028d2e  lea     r11, [rsp+60h+var_s0]
0x180028d33  mov     rbx, [r11+18h]
0x180028d37  mov     rdi, [r11+20h]
0x180028d3b  mov     rsp, r11
0x180028d3e  pop     rbp
0x180028d3f  retn
```
