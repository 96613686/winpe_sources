# Wsp::Facade::LocalSmbFileServer::GetFriendlyName(void)

- ea: `0x180061ef0`
- end: `0x18006201a`
- name: `?GetFriendlyName@LocalSmbFileServer@Facade@Wsp@@UEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x180014630`
- `0x180025888`
- `0x180061ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061faf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180061f27`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180061f5c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180061f27`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180061f5c`

## string_xrefs

- `0x180061f9c`: `Failed to get ComputerNameDnsHostname in LocalSmbFileServer`
- `0x180061fe0`: `Expected GetComputerNameExW to fail (passed NULL buffer)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Wsp::Facade::LocalSmbFileServer::GetFriendlyName(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  DWORD nSize; // [rsp+20h] [rbp-79h] BYREF
  _QWORD v7[2]; // [rsp+28h] [rbp-71h] BYREF
  LPWSTR lpBuffer[3]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-29h] BYREF

  v7[0] = a2;
  nSize = 0;
  if ( GetComputerNameExW(ComputerNameDnsHostname, 0, &nSize) )
  {
    v5 = std::wstring::wstring(v9, L"Expected GetComputerNameExW to fail (passed NULL buffer)");
    v7[0] = 1359;
    cxl::Exception::Exception(pExceptionObject, v7, v5);
    throw (cxl::Exception *)pExceptionObject;
  }
  std::vector<wchar_t>::vector<wchar_t>(lpBuffer, nSize);
  nSize = lpBuffer[1] - lpBuffer[0];
  if ( !GetComputerNameExW(ComputerNameDnsHostname, lpBuffer[0], &nSize) )
  {
    v4 = std::wstring::wstring(v9, L"Failed to get ComputerNameDnsHostname in LocalSmbFileServer");
    v7[0] = GetLastError();
    cxl::Exception::Exception(pExceptionObject, v7, v4);
    throw (cxl::Exception *)pExceptionObject;
  }
  std::wstring::wstring(a2, lpBuffer[0]);
  std::vector<unsigned short>::_Tidy(lpBuffer);
  return a2;
}

```

## disassembly

```asm
0x180061ef0  mov     [rsp-8+arg_0], rbx
0x180061ef5  push    rbp
0x180061ef6  lea     rbp, [rsp-57h]
0x180061efb  sub     rsp, 0F0h
0x180061f02  mov     rax, cs:__security_cookie
0x180061f09  xor     rax, rsp
0x180061f0c  mov     [rbp+57h+var_10], rax
0x180061f10  mov     rbx, rdx
0x180061f13  mov     [rbp+57h+var_C8], rdx
0x180061f17  mov     [rbp+57h+nSize], 0
0x180061f1e  lea     r8, [rbp+57h+nSize]; nSize
0x180061f22  xor     edx, edx; lpBuffer
0x180061f24  lea     ecx, [rdx+1]; NameType
0x180061f27  call    cs:__imp_GetComputerNameExW
0x180061f2d  test    eax, eax
0x180061f2f  jnz     loc_180061FE0
0x180061f35  mov     edx, [rbp+57h+nSize]
0x180061f38  lea     rcx, [rbp+57h+lpBuffer]
0x180061f3c  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180061f41  nop
0x180061f42  mov     rax, [rbp+57h+var_B0]
0x180061f46  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x180061f4a  sub     rax, rdx
0x180061f4d  sar     rax, 1
0x180061f50  mov     [rbp+57h+nSize], eax
0x180061f53  lea     r8, [rbp+57h+nSize]; nSize
0x180061f57  mov     ecx, 1; NameType
0x180061f5c  call    cs:__imp_GetComputerNameExW
0x180061f62  test    eax, eax
0x180061f64  jz      short loc_180061F9C
0x180061f66  mov     rdx, [rbp+57h+lpBuffer]
0x180061f6a  mov     rcx, rbx
0x180061f6d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180061f72  nop
0x180061f73  lea     rcx, [rbp+57h+lpBuffer]
0x180061f77  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180061f7c  mov     rax, rbx
0x180061f7f  mov     rcx, [rbp+57h+var_10]
0x180061f83  xor     rcx, rsp; StackCookie
0x180061f86  call    __security_check_cookie
0x180061f8b  mov     rbx, [rsp+0F0h+arg_0]
0x180061f93  add     rsp, 0F0h
0x180061f9a  pop     rbp
0x180061f9b  retn
0x180061f9c  lea     rdx, aFailedToGetCom; "Failed to get ComputerNameDnsHostname i"...
0x180061fa3  lea     rcx, [rbp+57h+var_A0]
0x180061fa7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180061fac  mov     rbx, rax
0x180061faf  call    cs:__imp_GetLastError
0x180061fb5  mov     dword ptr [rbp+57h+var_C8], eax
0x180061fb8  mov     dword ptr [rbp+57h+var_C8+4], 0
0x180061fbf  mov     r8, rbx
0x180061fc2  lea     rdx, [rbp+57h+var_C8]
0x180061fc6  lea     rcx, [rbp+57h+pExceptionObject]
0x180061fca  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180061fcf  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180061fd6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180061fda  call    _CxxThrowException_0
0x180061fe0  lea     rdx, aExpectedGetcom; "Expected GetComputerNameExW to fail (pa"...
0x180061fe7  lea     rcx, [rbp+57h+var_A0]
0x180061feb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180061ff0  nop
0x180061ff1  mov     [rbp+57h+var_C8], 54Fh
0x180061ff9  mov     r8, rax
0x180061ffc  lea     rdx, [rbp+57h+var_C8]
0x180062000  lea     rcx, [rbp+57h+pExceptionObject]
0x180062004  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180062009  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180062010  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180062014  call    _CxxThrowException_0
```
