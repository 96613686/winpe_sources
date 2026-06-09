# wmi::QueryParser::QueryParser(void)

- ea: `0x180052700`
- end: `0x1800527df`
- name: `??0QueryParser@wmi@@QEAA@XZ`
- size: `223`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037fd4`
- `0x180039df4`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000d524`
- `0x18001f178`
- `0x18002271c`
- `0x180052700`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180052769`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180052769`

## string_xrefs

- `0x1800527a0`: `_ptrQuery.CoCreateInstance( CLSID_WbemQuery )`

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
0x180052700  mov     [rsp+arg_8], rbx
0x180052705  push    rdi
0x180052706  sub     rsp, 0E0h
0x18005270d  mov     rax, cs:__security_cookie
0x180052714  xor     rax, rsp
0x180052717  mov     [rsp+0E8h+var_18], rax
0x18005271f  mov     rbx, rcx
0x180052722  mov     [rsp+0E8h+var_B8], rcx
0x180052727  mov     qword ptr [rcx], 0
0x18005272e  mov     qword ptr [rcx+8], 0
0x180052736  add     rcx, 10h
0x18005273a  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(std::less<std::wstring> const &)
0x18005273f  nop
0x180052740  mov     qword ptr [rbx+20h], 0
0x180052748  mov     qword ptr [rbx+28h], 0
0x180052750  mov     [rsp+0E8h+ppv], rbx; ppv
0x180052755  lea     r9, _GUID_81166f58_dd98_11d3_a120_00105a1f515a; riid
0x18005275c  xor     edx, edx; pUnkOuter
0x18005275e  lea     r8d, [rdx+17h]; dwClsContext
0x180052762  lea     rcx, CLSID_WbemQuery; rclsid
0x180052769  call    cs:__imp_CoCreateInstance
0x180052770  nop     dword ptr [rax+rax+00h]
0x180052775  mov     edi, eax
0x180052777  test    eax, eax
0x180052779  js      short loc_1800527A0
0x18005277b  mov     rax, rbx
0x18005277e  mov     rcx, [rsp+0E8h+var_18]
0x180052786  xor     rcx, rsp; StackCookie
0x180052789  call    __security_check_cookie
0x18005278e  mov     rbx, [rsp+0E8h+arg_8]
0x180052796  add     rsp, 0E0h
0x18005279d  pop     rdi
0x18005279e  retn
0x1800527a0  lea     rdx, aPtrqueryCocrea; "_ptrQuery.CoCreateInstance( CLSID_WbemQ"...
0x1800527a7  lea     rcx, [rsp+0E8h+var_A8]
0x1800527ac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800527b1  mov     r8, rax
0x1800527b4  mov     edx, edi
0x1800527b6  lea     rcx, [rsp+0E8h+var_B0]
0x1800527bb  call    ?HrStatus@cxl@@YA?AVErrorCode@1@H@Z; cxl::HrStatus(int)
0x1800527c0  mov     rdx, rax
0x1800527c3  lea     rcx, [rsp+0E8h+pExceptionObject]
0x1800527c8  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x1800527cd  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800527d4  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x1800527d9  call    _CxxThrowException_0
```
