# wmi::QueryParser::QueryParser(void)

- ea: `0x18009b594`
- end: `0x18009b673`
- name: `??0QueryParser@wmi@@QEAA@XZ`
- size: `223`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bb04`
- `0x180042ab4`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000dcc4`
- `0x180022e48`
- `0x180026558`
- `0x18009b594`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009b5fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009b5fd`

## string_xrefs

- `0x18009b634`: `_ptrQuery.CoCreateInstance( CLSID_WbemQuery )`

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
0x18009b594  mov     [rsp+arg_8], rbx
0x18009b599  push    rdi
0x18009b59a  sub     rsp, 0E0h
0x18009b5a1  mov     rax, cs:__security_cookie
0x18009b5a8  xor     rax, rsp
0x18009b5ab  mov     [rsp+0E8h+var_18], rax
0x18009b5b3  mov     rbx, rcx
0x18009b5b6  mov     [rsp+0E8h+var_B8], rcx
0x18009b5bb  mov     qword ptr [rcx], 0
0x18009b5c2  mov     qword ptr [rcx+8], 0
0x18009b5ca  add     rcx, 10h
0x18009b5ce  call    ??0?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@AEBU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(std::less<std::wstring> const &)
0x18009b5d3  nop
0x18009b5d4  mov     qword ptr [rbx+20h], 0
0x18009b5dc  mov     qword ptr [rbx+28h], 0
0x18009b5e4  mov     [rsp+0E8h+ppv], rbx; ppv
0x18009b5e9  lea     r9, _GUID_81166f58_dd98_11d3_a120_00105a1f515a; riid
0x18009b5f0  xor     edx, edx; pUnkOuter
0x18009b5f2  lea     r8d, [rdx+17h]; dwClsContext
0x18009b5f6  lea     rcx, CLSID_WbemQuery; rclsid
0x18009b5fd  call    cs:__imp_CoCreateInstance
0x18009b604  nop     dword ptr [rax+rax+00h]
0x18009b609  mov     edi, eax
0x18009b60b  test    eax, eax
0x18009b60d  js      short loc_18009B634
0x18009b60f  mov     rax, rbx
0x18009b612  mov     rcx, [rsp+0E8h+var_18]
0x18009b61a  xor     rcx, rsp; StackCookie
0x18009b61d  call    __security_check_cookie
0x18009b622  mov     rbx, [rsp+0E8h+arg_8]
0x18009b62a  add     rsp, 0E0h
0x18009b631  pop     rdi
0x18009b632  retn
0x18009b634  lea     rdx, aPtrqueryCocrea; "_ptrQuery.CoCreateInstance( CLSID_WbemQ"...
0x18009b63b  lea     rcx, [rsp+0E8h+var_A8]
0x18009b640  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18009b645  mov     r8, rax
0x18009b648  mov     edx, edi
0x18009b64a  lea     rcx, [rsp+0E8h+var_B0]
0x18009b64f  call    ?HrStatus@cxl@@YA?AVErrorCode@1@H@Z; cxl::HrStatus(int)
0x18009b654  mov     rdx, rax
0x18009b657  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18009b65c  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x18009b661  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009b668  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18009b66d  call    _CxxThrowException_0
```
