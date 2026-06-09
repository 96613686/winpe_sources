# wmi::QueryParser::QueryParser(void)

- ea: `0x180050c70`
- end: `0x180050d48`
- name: `??0QueryParser@wmi@@QEAA@XZ`
- size: `216`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036cb4`
- `0x180038a24`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000d140`
- `0x18001e5a4`
- `0x180021b24`
- `0x180050c70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050cd9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050cd9`

## string_xrefs

- `0x180050d09`: `_ptrQuery.CoCreateInstance( CLSID_WbemQuery )`

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
0x180050c70  mov     [rsp+arg_8], rbx
0x180050c75  push    rdi
0x180050c76  sub     rsp, 0E0h
0x180050c7d  mov     rax, cs:__security_cookie
0x180050c84  xor     rax, rsp
0x180050c87  mov     [rsp+0E8h+var_18], rax
0x180050c8f  mov     rbx, rcx
0x180050c92  mov     [rsp+0E8h+var_B8], rcx
0x180050c97  mov     qword ptr [rcx], 0
0x180050c9e  mov     qword ptr [rcx+8], 0
0x180050ca6  add     rcx, 10h
0x180050caa  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(std::less<std::wstring> const &)
0x180050caf  nop
0x180050cb0  mov     qword ptr [rbx+20h], 0
0x180050cb8  mov     qword ptr [rbx+28h], 0
0x180050cc0  mov     [rsp+0E8h+ppv], rbx; ppv
0x180050cc5  lea     r9, _GUID_81166f58_dd98_11d3_a120_00105a1f515a; riid
0x180050ccc  xor     edx, edx; pUnkOuter
0x180050cce  lea     r8d, [rdx+17h]; dwClsContext
0x180050cd2  lea     rcx, CLSID_WbemQuery; rclsid
0x180050cd9  call    cs:__imp_CoCreateInstance
0x180050cdf  mov     edi, eax
0x180050ce1  test    eax, eax
0x180050ce3  js      short loc_180050D09
0x180050ce5  mov     rax, rbx
0x180050ce8  mov     rcx, [rsp+0E8h+var_18]
0x180050cf0  xor     rcx, rsp; StackCookie
0x180050cf3  call    __security_check_cookie
0x180050cf8  mov     rbx, [rsp+0E8h+arg_8]
0x180050d00  add     rsp, 0E0h
0x180050d07  pop     rdi
0x180050d08  retn
0x180050d09  lea     rdx, aPtrqueryCocrea; "_ptrQuery.CoCreateInstance( CLSID_WbemQ"...
0x180050d10  lea     rcx, [rsp+0E8h+var_A8]
0x180050d15  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180050d1a  mov     r8, rax
0x180050d1d  mov     edx, edi
0x180050d1f  lea     rcx, [rsp+0E8h+var_B0]
0x180050d24  call    ?HrStatus@cxl@@YA?AVErrorCode@1@H@Z; cxl::HrStatus(int)
0x180050d29  mov     rdx, rax
0x180050d2c  lea     rcx, [rsp+0E8h+pExceptionObject]
0x180050d31  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x180050d36  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180050d3d  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180050d42  call    _CxxThrowException_0
```
