# BrowserUtilEdp::IsEdpEnforcementEnabled(void)

- ea: `0x180008904`
- end: `0x1800089db`
- name: `?IsEdpEnforcementEnabled@BrowserUtilEdp@@YA_NXZ`
- size: `215`
- prototype: `bool __fastcall(BrowserUtilEdp *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800086cc`

## callees

- `0x180008904`
- `0x1800089e4`
- `0x180080fb0`
- `0x180081d2b`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000896c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000896c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008947`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008947`

## string_xrefs

- `0x180008940`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`

## pseudocode

```c
bool __fastcall BrowserUtilEdp::IsEdpEnforcementEnabled(BrowserUtilEdp *this)
{
  HRESULT v1; // eax
  HSTRING v2; // rbx
  __int64 v3; // rcx
  bool v4; // bl
  _BYTE v6[8]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v7; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  v6[0] = 0;
  v7 = 0;
  string = 0;
  v1 = WindowsCreateStringReference(
         L"Windows.Security.EnterpriseData.ProtectionPolicyManager",
         0x37u,
         &hstringHeader,
         &string);
  if ( v1 < 0 )
  {
    RaiseException_0(v1, 1u, 0, 0);
    __debugbreak();
  }
  v2 = string;
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>::InternalRelease(&v7);
  if ( (int)RoGetActivationFactory(v2, &GUID_b68f9a8c_39e0_4649_b2e4_070ab8a579b3, &v7) >= 0 )
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v7 + 112LL))(v7, v6);
  v3 = v7;
  v4 = v6[0] != 0;
  if ( v7 )
  {
    v7 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x180008904  mov     [rsp-8+arg_0], rbx
0x180008909  push    rbp
0x18000890a  mov     rbp, rsp
0x18000890d  sub     rsp, 60h
0x180008911  mov     rax, cs:__security_cookie
0x180008918  xor     rax, rsp
0x18000891b  mov     [rbp+var_10], rax
0x18000891f  lea     r9, [rbp+string]; string
0x180008923  mov     [rbp+var_40], 0
0x180008927  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000892b  mov     [rbp+var_38], 0
0x180008933  mov     edx, 37h ; '7'; length
0x180008938  mov     [rbp+string], 0
0x180008940  lea     rcx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyManager@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x180008947  call    cs:__imp_WindowsCreateStringReference
0x18000894d  test    eax, eax
0x18000894f  js      short loc_1800089B3
0x180008951  mov     rbx, [rbp+string]
0x180008955  lea     rcx, [rbp+var_38]
0x180008959  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics2@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>::InternalRelease(void)
0x18000895e  lea     r8, [rbp+var_38]
0x180008962  mov     rcx, rbx
0x180008965  lea     rdx, _GUID_b68f9a8c_39e0_4649_b2e4_070ab8a579b3
0x18000896c  call    cs:__imp_RoGetActivationFactory
0x180008972  test    eax, eax
0x180008974  js      short loc_18000898A
0x180008976  mov     rcx, [rbp+var_38]
0x18000897a  lea     rdx, [rbp+var_40]
0x18000897e  mov     rax, [rcx]
0x180008981  mov     rax, [rax+70h]
0x180008985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000898a  cmp     [rbp+var_40], 0
0x18000898e  mov     rcx, [rbp+var_38]
0x180008992  setnz   bl
0x180008995  test    rcx, rcx
0x180008998  jnz     short loc_1800089C5
0x18000899a  mov     al, bl
0x18000899c  mov     rcx, [rbp+var_10]
0x1800089a0  xor     rcx, rsp; StackCookie
0x1800089a3  call    __security_check_cookie
0x1800089a8  mov     rbx, [rsp+60h+arg_0]
0x1800089ad  add     rsp, 60h
0x1800089b1  pop     rbp
0x1800089b2  retn
0x1800089b3  xor     r9d, r9d; lpArguments
0x1800089b6  xor     r8d, r8d; nNumberOfArguments
0x1800089b9  mov     ecx, eax; dwExceptionCode
0x1800089bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800089bf  call    RaiseException_0
0x1800089c4  int     3; Trap to Debugger
0x1800089c5  mov     [rbp+var_38], 0
0x1800089cd  mov     rdx, [rcx]
0x1800089d0  mov     rax, [rdx+10h]
0x1800089d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089d9  jmp     short loc_18000899A
```
