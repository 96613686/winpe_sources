# UtilIsEdu(ulong *)

- ea: `0x180029b70`
- end: `0x180029cdd`
- name: `?UtilIsEdu@@YAJPEAK@Z`
- size: `365`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013838`

## callees

- `0x180029b70`
- `0x18003fb94`
- `0x180045388`
- `0x180053300`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029c11`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029c11`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029c2d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029c2d`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180029b9c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180029b9c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180029c83`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180029cb0`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180029c83`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180029cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029bf5`

## string_xrefs

- `0x180029bb5`: `onecore\windows\feedback\core\common\lib\utility.cpp`
- `0x180029c68`: `onecore\windows\feedback\core\common\lib\utility.cpp`

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
      (void *)0x15AE,
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
    v7 = 5559;
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
    v7 = 5561;
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
0x180029b70  mov     [rsp-8+arg_8], rbx
0x180029b75  mov     [rsp-8+arg_10], rdi
0x180029b7a  push    rbp
0x180029b7b  mov     rbp, rsp
0x180029b7e  sub     rsp, 60h
0x180029b82  mov     rax, cs:__security_cookie
0x180029b89  xor     rax, rsp
0x180029b8c  mov     [rbp+var_8], rax
0x180029b90  mov     rdi, rcx
0x180029b93  mov     byte ptr [rbp+var_40], 0
0x180029b97  mov     ecx, 1
0x180029b9c  call    cs:__imp_RoInitialize
0x180029ba3  nop     dword ptr [rax+rax+00h]
0x180029ba8  mov     ebx, eax
0x180029baa  test    eax, eax
0x180029bac  jns     short loc_180029BCD
0x180029bae  mov     rcx, [rbp+8]; this
0x180029bb2  mov     r9d, eax; char *
0x180029bb5  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x180029bbc  mov     edx, 15AEh; void *
0x180029bc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029bc6  mov     eax, ebx
0x180029bc8  jmp     loc_180029CBE
0x180029bcd  mov     [rbp+var_2F], 1
0x180029bd1  mov     [rbp+var_38], 0
0x180029bd9  mov     [rbp+string], 0
0x180029be1  lea     r9, [rbp+string]; string
0x180029be5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180029be9  mov     edx, 28h ; '('; length
0x180029bee  lea     rcx, ?RuntimeClass_Windows_System_Profile_EducationSettings@@3QB_WB; "Windows.System.Profile.EducationSetting"...
0x180029bf5  call    cs:__imp_WindowsCreateStringReference
0x180029bfc  nop     dword ptr [rax+rax+00h]
0x180029c01  test    eax, eax
0x180029c03  jns     short loc_180029C1E
0x180029c05  xor     r9d, r9d; lpArguments
0x180029c08  xor     r8d, r8d; nNumberOfArguments
0x180029c0b  lea     edx, [r9+1]; dwExceptionFlags
0x180029c0f  mov     ecx, eax; dwExceptionCode
0x180029c11  call    cs:__imp_RaiseException
0x180029c18  nop     dword ptr [rax+rax+00h]
0x180029c1d  int     3; Trap to Debugger
0x180029c1e  lea     r8, [rbp+var_38]
0x180029c22  lea     rdx, _GUID_fc53f0ef_4d3e_4e13_9b23_505f4d091e92
0x180029c29  mov     rcx, [rbp+string]
0x180029c2d  call    cs:__imp_RoGetActivationFactory
0x180029c34  nop     dword ptr [rax+rax+00h]
0x180029c39  mov     ebx, eax
0x180029c3b  test    eax, eax
0x180029c3d  jns     short loc_180029C46
0x180029c3f  mov     edx, 15B7h
0x180029c44  jmp     short loc_180029C65
0x180029c46  mov     rcx, [rbp+var_38]
0x180029c4a  mov     rax, [rcx]
0x180029c4d  lea     rdx, [rbp+var_40]
0x180029c51  mov     rax, [rax+30h]
0x180029c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c5a  mov     ebx, eax
0x180029c5c  test    eax, eax
0x180029c5e  jns     short loc_180029C94
0x180029c60  mov     edx, 15B9h; void *
0x180029c65  mov     r9d, eax; char *
0x180029c68  lea     r8, aOnecoreWindows_1; "onecore\\windows\\feedback\\core\\commo"...
0x180029c6f  mov     rcx, [rbp+8]; this
0x180029c73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029c78  nop
0x180029c79  lea     rcx, [rbp+var_38]
0x180029c7d  call    ??1?$unique_ptr@UIXmlWriter@@Urelease_delete@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<IXmlWriter,tlx::release_delete>::~unique_ptr<IXmlWriter,tlx::release_delete>(void)
0x180029c82  nop
0x180029c83  call    cs:__imp_RoUninitialize
0x180029c8a  nop     dword ptr [rax+rax+00h]
0x180029c8f  jmp     loc_180029BC6
0x180029c94  mov     rcx, [rbp+var_38]
0x180029c98  test    rcx, rcx
0x180029c9b  jz      short loc_180029CAA
0x180029c9d  mov     rax, [rcx]
0x180029ca0  mov     rax, [rax+10h]
0x180029ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ca9  nop
0x180029caa  movzx   eax, byte ptr [rbp+var_40]
0x180029cae  mov     [rdi], eax
0x180029cb0  call    cs:__imp_RoUninitialize
0x180029cb7  nop     dword ptr [rax+rax+00h]
0x180029cbc  xor     eax, eax
0x180029cbe  mov     rcx, [rbp+var_8]
0x180029cc2  xor     rcx, rsp; StackCookie
0x180029cc5  call    __security_check_cookie
0x180029cca  lea     r11, [rsp+60h+var_s0]
0x180029ccf  mov     rbx, [r11+18h]
0x180029cd3  mov     rdi, [r11+20h]
0x180029cd7  mov     rsp, r11
0x180029cda  pop     rbp
0x180029cdb  retn
```
