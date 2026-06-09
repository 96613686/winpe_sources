# wmi::QueryParser::QueryParser(void)

- ea: `0x18009913c`
- end: `0x180099214`
- name: `??0QueryParser@wmi@@QEAA@XZ`
- size: `216`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a7a4`
- `0x180041784`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d920`
- `0x18002210c`
- `0x18002585c`
- `0x18009913c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800991a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800991a5`

## string_xrefs

- `0x1800991d5`: `_ptrQuery.CoCreateInstance( CLSID_WbemQuery )`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LPVOID *__fastcall wmi::QueryParser::QueryParser(LPVOID *ppv)
{
  HRESULT Instance; // edi
  __int64 v4; // rax
  __int64 v5; // rax
  _BYTE v6[8]; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-88h] BYREF

  *ppv = 0;
  ppv[1] = 0;
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(ppv + 2);
  ppv[4] = 0;
  ppv[5] = 0;
  Instance = CoCreateInstance(&CLSID_WbemQuery, 0, 0x17u, &GUID_81166f58_dd98_11d3_a120_00105a1f515a, ppv);
  if ( Instance < 0 )
  {
    v4 = std::wstring::wstring(v7, L"_ptrQuery.CoCreateInstance( CLSID_WbemQuery )");
    v5 = cxl::HrStatus(v6, (unsigned int)Instance, v4);
    cxl::Error(pExceptionObject, v5);
    throw (cxl::Exception *)pExceptionObject;
  }
  return ppv;
}

```

## disassembly

```asm
0x18009913c  mov     [rsp+arg_8], rbx
0x180099141  push    rdi
0x180099142  sub     rsp, 0E0h
0x180099149  mov     rax, cs:__security_cookie
0x180099150  xor     rax, rsp
0x180099153  mov     [rsp+0E8h+var_18], rax
0x18009915b  mov     rbx, rcx
0x18009915e  mov     [rsp+0E8h+var_B8], rcx
0x180099163  mov     qword ptr [rcx], 0
0x18009916a  mov     qword ptr [rcx+8], 0
0x180099172  add     rcx, 10h
0x180099176  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(std::less<std::wstring> const &)
0x18009917b  nop
0x18009917c  mov     qword ptr [rbx+20h], 0
0x180099184  mov     qword ptr [rbx+28h], 0
0x18009918c  mov     [rsp+0E8h+ppv], rbx; ppv
0x180099191  lea     r9, _GUID_81166f58_dd98_11d3_a120_00105a1f515a; riid
0x180099198  xor     edx, edx; pUnkOuter
0x18009919a  lea     r8d, [rdx+17h]; dwClsContext
0x18009919e  lea     rcx, CLSID_WbemQuery; rclsid
0x1800991a5  call    cs:__imp_CoCreateInstance
0x1800991ab  mov     edi, eax
0x1800991ad  test    eax, eax
0x1800991af  js      short loc_1800991D5
0x1800991b1  mov     rax, rbx
0x1800991b4  mov     rcx, [rsp+0E8h+var_18]
0x1800991bc  xor     rcx, rsp; StackCookie
0x1800991bf  call    __security_check_cookie
0x1800991c4  mov     rbx, [rsp+0E8h+arg_8]
0x1800991cc  add     rsp, 0E0h
0x1800991d3  pop     rdi
0x1800991d4  retn
0x1800991d5  lea     rdx, aPtrqueryCocrea; "_ptrQuery.CoCreateInstance( CLSID_WbemQ"...
0x1800991dc  lea     rcx, [rsp+0E8h+var_A8]
0x1800991e1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800991e6  mov     r8, rax
0x1800991e9  mov     edx, edi
0x1800991eb  lea     rcx, [rsp+0E8h+var_B0]
0x1800991f0  call    ?HrStatus@cxl@@YA?AVErrorCode@1@H@Z; cxl::HrStatus(int)
0x1800991f5  mov     rdx, rax
0x1800991f8  lea     rcx, [rsp+0E8h+pExceptionObject]
0x1800991fd  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180099202  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180099209  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18009920e  call    _CxxThrowException_0
```
