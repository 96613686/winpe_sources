# _anonymous_namespace_::wmi_connect

- ea: `0x18008c2d4`
- end: `0x18008c513`
- name: `_anonymous_namespace_::wmi_connect`
- size: `575`
- prototype: `__int64 __fastcall(BSTR bstrString)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008c520`
- `0x18008ca40`
- `0x18008cdc0`

## callees

- `0x180004510`
- `0x180005520`
- `0x18003af08`
- `0x180058600`
- `0x18008c2d4`
- `0x18009d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18008c35f`
- `OLEAUT32!__imp_SysAllocString` at `0x18008c35f`
- `OLEAUT32!__imp_SysFreeString` at `0x18008c3be`
- `OLEAUT32!__imp_SysFreeString` at `0x18008c3be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008c338`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008c338`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008c3f8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18008c3f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
IUnknown *__fastcall anonymous_namespace_::wmi_connect(BSTR bstrString, IUnknown **a2)
{
  HRESULT v4; // eax
  LPVOID v5; // rdi
  __int64 v6; // r14
  OLECHAR *v7; // rdx
  OLECHAR *v8; // rax
  __int64 v9; // rdi
  HRESULT v10; // eax
  IUnknown *result; // rax
  IUnknown *pProxy; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR *v14; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[1072]; // [rsp+70h] [rbp-90h] BYREF

  ppv = 0;
  pProxy = 0;
  v4 = CoCreateInstance(&CLSID_WbemLocator, 0, 0x17u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &ppv);
  if ( v4 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v4,
      0,
      "[%s:%d] failed; ",
      "wmi_connect",
      334);
    throw (windiag::system_exception *)pExceptionObject;
  }
  v5 = ppv;
  v6 = *(_QWORD *)ppv;
  if ( bstrString )
  {
    v8 = SysAllocString(bstrString);
    bstrString = v8;
    v14 = v8;
    if ( !v8 )
      ATL::AtlThrowImpl(-2147024882);
    v7 = v8;
  }
  else
  {
    v14 = 0;
    v7 = 0;
  }
  v9 = (*(int (__fastcall **)(LPVOID, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(v6 + 24))(
         v5,
         v7,
         0,
         0,
         0,
         0,
         0,
         0,
         &pProxy);
  SysFreeString(bstrString);
  if ( (int)v9 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v9,
      0,
      "[%s:%d] failed; ",
      "wmi_connect",
      337);
    throw (windiag::system_exception *)pExceptionObject;
  }
  v10 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0x20u);
  if ( v10 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v10,
      0,
      "[%s:%d] failed; ",
      "wmi_connect",
      348);
    throw (windiag::system_exception *)pExceptionObject;
  }
  result = pProxy;
  pProxy = 0;
  *a2 = result;
  if ( ppv )
    return (IUnknown *)(*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return result;
}

```

## disassembly

```asm
0x18008c2d4  mov     [rsp-8+arg_10], rbx
0x18008c2d9  mov     [rsp-8+arg_18], rsi
0x18008c2de  push    rbp
0x18008c2df  push    rdi
0x18008c2e0  push    r14
0x18008c2e2  lea     rbp, [rsp-3B0h]
0x18008c2ea  sub     rsp, 4B0h
0x18008c2f1  mov     rax, cs:__security_cookie
0x18008c2f8  xor     rax, rsp
0x18008c2fb  mov     [rbp+3C0h+var_20], rax
0x18008c302  mov     rsi, rdx
0x18008c305  mov     rbx, rcx
0x18008c308  mov     [rsp+4C0h+var_468], 0
0x18008c311  mov     [rsp+4C0h+pProxy], 0
0x18008c31a  lea     rax, [rsp+4C0h+var_468]
0x18008c31f  mov     [rsp+4C0h+ppv], rax; ppv
0x18008c324  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x18008c32b  xor     edx, edx; pUnkOuter
0x18008c32d  lea     r8d, [rdx+17h]; dwClsContext
0x18008c331  lea     rcx, CLSID_WbemLocator; rclsid
0x18008c338  call    cs:__imp_CoCreateInstance
0x18008c33e  test    eax, eax
0x18008c340  js      loc_18008C48E
0x18008c346  mov     rdi, [rsp+4C0h+var_468]
0x18008c34b  mov     r14, [rdi]
0x18008c34e  test    rbx, rbx
0x18008c351  jnz     short loc_18008C35C
0x18008c353  mov     [rsp+4C0h+var_460], rbx
0x18008c358  xor     edx, edx
0x18008c35a  jmp     short loc_18008C379
0x18008c35c  mov     rcx, rbx; psz
0x18008c35f  call    cs:__imp_SysAllocString
0x18008c365  mov     rbx, rax
0x18008c368  mov     [rsp+4C0h+var_460], rax
0x18008c36d  test    rax, rax
0x18008c370  jz      loc_18008C4CB
0x18008c376  mov     rdx, rax
0x18008c379  lea     rax, [rsp+4C0h+pProxy]
0x18008c37e  mov     [rsp+4C0h+var_480], rax
0x18008c383  mov     qword ptr [rsp+4C0h+dwCapabilities], 0
0x18008c38c  mov     [rsp+4C0h+pAuthInfo], 0
0x18008c395  mov     [rsp+4C0h+dwImpLevel], 0
0x18008c39d  mov     [rsp+4C0h+ppv], 0
0x18008c3a6  xor     r9d, r9d
0x18008c3a9  xor     r8d, r8d
0x18008c3ac  mov     rcx, rdi
0x18008c3af  mov     rax, [r14+18h]
0x18008c3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c3b8  movsxd  rdi, eax
0x18008c3bb  mov     rcx, rbx; bstrString
0x18008c3be  call    cs:__imp_SysFreeString
0x18008c3c4  test    edi, edi
0x18008c3c6  js      loc_18008C4D6
0x18008c3cc  mov     [rsp+4C0h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18008c3d4  mov     [rsp+4C0h+pAuthInfo], 0; pAuthInfo
0x18008c3dd  mov     eax, 3
0x18008c3e2  mov     [rsp+4C0h+dwImpLevel], eax; dwImpLevel
0x18008c3e6  mov     dword ptr [rsp+4C0h+ppv], eax; dwAuthnLevel
0x18008c3ea  xor     r9d, r9d; pServerPrincName
0x18008c3ed  xor     r8d, r8d; dwAuthzSvc
0x18008c3f0  lea     edx, [rax+7]; dwAuthnSvc
0x18008c3f3  mov     rcx, [rsp+4C0h+pProxy]; pProxy
0x18008c3f8  call    cs:__imp_CoSetProxyBlanket
0x18008c3fe  test    eax, eax
0x18008c400  js      short loc_18008C451
0x18008c402  mov     rax, [rsp+4C0h+pProxy]
0x18008c407  mov     [rsp+4C0h+pProxy], 0
0x18008c410  mov     [rsi], rax
0x18008c413  mov     rcx, [rsp+4C0h+var_468]
0x18008c418  test    rcx, rcx
0x18008c41b  jz      short loc_18008C42A
0x18008c41d  mov     rax, [rcx]
0x18008c420  mov     rax, [rax+10h]
0x18008c424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c429  nop
0x18008c42a  mov     rcx, [rbp+3C0h+var_20]
0x18008c431  xor     rcx, rsp; StackCookie
0x18008c434  call    __security_check_cookie
0x18008c439  lea     r11, [rsp+4C0h+var_10]
0x18008c441  mov     rbx, [r11+30h]
0x18008c445  mov     rsi, [r11+38h]
0x18008c449  mov     rsp, r11
0x18008c44c  pop     r14
0x18008c44e  pop     rdi
0x18008c44f  pop     rbp
0x18008c450  retn
0x18008c451  movsxd  rdx, eax; __int64
0x18008c454  mov     [rsp+4C0h+dwImpLevel], 15Ch
0x18008c45c  lea     rax, aWmiConnect; "wmi_connect"
0x18008c463  mov     [rsp+4C0h+ppv], rax
0x18008c468  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008c46f  xor     r8d, r8d; void *
0x18008c472  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x18008c477  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008c47c  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008c483  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x18008c488  call    _CxxThrowException_0
0x18008c48e  movsxd  rdx, eax; __int64
0x18008c491  mov     [rsp+4C0h+dwImpLevel], 14Eh
0x18008c499  lea     rax, aWmiConnect; "wmi_connect"
0x18008c4a0  mov     [rsp+4C0h+ppv], rax
0x18008c4a5  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008c4ac  xor     r8d, r8d; void *
0x18008c4af  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x18008c4b4  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008c4b9  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008c4c0  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x18008c4c5  call    _CxxThrowException_0
0x18008c4cb  mov     ecx, 8007000Eh; int
0x18008c4d0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18008c4d6  mov     rdx, rdi; __int64
0x18008c4d9  mov     [rsp+4C0h+dwImpLevel], 151h
0x18008c4e1  lea     rax, aWmiConnect; "wmi_connect"
0x18008c4e8  mov     [rsp+4C0h+ppv], rax
0x18008c4ed  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18008c4f4  xor     r8d, r8d; void *
0x18008c4f7  lea     rcx, [rsp+4C0h+pExceptionObject]; this
0x18008c4fc  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18008c501  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18008c508  lea     rcx, [rsp+4C0h+pExceptionObject]; pExceptionObject
0x18008c50d  call    _CxxThrowException_0
```
