# Wsp::Facade::LocalSmbFileServer::GetHosts(void)

- ea: `0x1800632a0`
- end: `0x180063409`
- name: `?GetHosts@LocalSmbFileServer@Facade@Wsp@@UEBA?BV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d624`
- `0x18000d6a4`
- `0x180014c94`
- `0x180026588`
- `0x180038a30`
- `0x1800632a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006338a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006338a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800632ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180063328`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800632ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180063328`

## string_xrefs

- `0x1800633c8`: `Expected GetComputerNameExW to fail (passed NULL buffer)`
- `0x180063377`: `Failed to get ComputerNameDnsFullyQualified in LocalSmbFileServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
WCHAR *__fastcall Wsp::Facade::LocalSmbFileServer::GetHosts(__int64 a1, WCHAR *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  DWORD nSize; // [rsp+20h] [rbp-79h] BYREF
  int v7; // [rsp+24h] [rbp-75h]
  __int64 LastError; // [rsp+28h] [rbp-71h] BYREF
  LPWSTR lpBuffer[4]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v10[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-29h] BYREF

  lpBuffer[3] = a2;
  std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(a2);
  v7 = 1;
  nSize = 0;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) )
  {
    v5 = std::wstring::wstring(v10, L"Expected GetComputerNameExW to fail (passed NULL buffer)");
    LastError = 1359;
    cxl::Exception::Exception(pExceptionObject, &LastError, v5);
    v7 = 3;
    throw (cxl::Exception *)pExceptionObject;
  }
  std::vector<wchar_t>::vector<wchar_t>(lpBuffer);
  nSize = lpBuffer[1] - lpBuffer[0];
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, lpBuffer[0], &nSize) )
  {
    v4 = std::wstring::wstring(v10, L"Failed to get ComputerNameDnsFullyQualified in LocalSmbFileServer");
    LastError = GetLastError();
    cxl::Exception::Exception(pExceptionObject, &LastError, v4);
    v7 = 5;
    throw (cxl::Exception *)pExceptionObject;
  }
  LastError = (__int64)lpBuffer[0];
  std::vector<std::wstring>::emplace_back<wchar_t const * const &>(a2, &LastError);
  std::vector<unsigned short>::_Tidy(lpBuffer);
  return a2;
}

```

## disassembly

```asm
0x1800632a0  mov     [rsp-8+arg_0], rbx
0x1800632a5  push    rbp
0x1800632a6  lea     rbp, [rsp-57h]
0x1800632ab  sub     rsp, 0F0h
0x1800632b2  mov     rax, cs:__security_cookie
0x1800632b9  xor     rax, rsp
0x1800632bc  mov     [rbp+57h+var_10], rax
0x1800632c0  mov     rbx, rdx
0x1800632c3  mov     [rbp+57h+var_A8], rdx
0x1800632c7  mov     [rbp+57h+var_CC], 0
0x1800632ce  mov     rcx, rdx
0x1800632d1  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x1800632d6  mov     [rbp+57h+var_CC], 1
0x1800632dd  mov     [rbp+57h+nSize], 0
0x1800632e4  lea     r8, [rbp+57h+nSize]; nSize
0x1800632e8  xor     edx, edx; lpBuffer
0x1800632ea  lea     ecx, [rdx+3]; NameType
0x1800632ed  call    cs:__imp_GetComputerNameExW
0x1800632f4  nop     dword ptr [rax+rax+00h]
0x1800632f9  test    eax, eax
0x1800632fb  jnz     loc_1800633C8
0x180063301  mov     edx, [rbp+57h+nSize]
0x180063304  lea     rcx, [rbp+57h+lpBuffer]
0x180063308  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18006330d  nop
0x18006330e  mov     rax, [rbp+57h+var_B8]
0x180063312  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x180063316  sub     rax, rdx
0x180063319  sar     rax, 1
0x18006331c  mov     [rbp+57h+nSize], eax
0x18006331f  lea     r8, [rbp+57h+nSize]; nSize
0x180063323  mov     ecx, 3; NameType
0x180063328  call    cs:__imp_GetComputerNameExW
0x18006332f  nop     dword ptr [rax+rax+00h]
0x180063334  test    eax, eax
0x180063336  jz      short loc_180063377
0x180063338  mov     rcx, [rbp+57h+lpBuffer]
0x18006333c  mov     [rbp+57h+var_C8], rcx
0x180063340  lea     rdx, [rbp+57h+var_C8]
0x180063344  mov     rcx, rbx
0x180063347  call    ??$emplace_back@AEBQEB_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBQEB_W@Z; std::vector<std::wstring>::emplace_back<wchar_t const * const &>(wchar_t const * const &)
0x18006334c  nop
0x18006334d  lea     rcx, [rbp+57h+lpBuffer]
0x180063351  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180063356  mov     rax, rbx
0x180063359  mov     rcx, [rbp+57h+var_10]
0x18006335d  xor     rcx, rsp; StackCookie
0x180063360  call    __security_check_cookie
0x180063365  mov     rbx, [rsp+0F0h+arg_0]
0x18006336d  add     rsp, 0F0h
0x180063374  pop     rbp
0x180063375  retn
0x180063377  lea     rdx, aFailedToGetCom_0; "Failed to get ComputerNameDnsFullyQuali"...
0x18006337e  lea     rcx, [rbp+57h+var_A0]
0x180063382  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180063387  mov     rbx, rax
0x18006338a  call    cs:__imp_GetLastError
0x180063391  nop     dword ptr [rax+rax+00h]
0x180063396  mov     dword ptr [rbp+57h+var_C8], eax
0x180063399  mov     dword ptr [rbp+57h+var_C8+4], 0
0x1800633a0  mov     r8, rbx
0x1800633a3  lea     rdx, [rbp+57h+var_C8]
0x1800633a7  lea     rcx, [rbp+57h+pExceptionObject]
0x1800633ab  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800633b0  mov     [rbp+57h+var_CC], 5
0x1800633b7  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800633be  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800633c2  call    _CxxThrowException_0
0x1800633c8  lea     rdx, aExpectedGetcom; "Expected GetComputerNameExW to fail (pa"...
0x1800633cf  lea     rcx, [rbp+57h+var_A0]
0x1800633d3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800633d8  nop
0x1800633d9  mov     [rbp+57h+var_C8], 54Fh
0x1800633e1  mov     r8, rax
0x1800633e4  lea     rdx, [rbp+57h+var_C8]
0x1800633e8  lea     rcx, [rbp+57h+pExceptionObject]
0x1800633ec  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800633f1  mov     [rbp+57h+var_CC], 3
0x1800633f8  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800633ff  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180063403  call    _CxxThrowException_0
```
