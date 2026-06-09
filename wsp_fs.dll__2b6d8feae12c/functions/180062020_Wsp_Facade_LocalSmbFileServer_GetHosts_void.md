# Wsp::Facade::LocalSmbFileServer::GetHosts(void)

- ea: `0x180062020`
- end: `0x180062176`
- name: `?GetHosts@LocalSmbFileServer@Facade@Wsp@@UEBA?BV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d2bc`
- `0x18000d33c`
- `0x180014630`
- `0x180025888`
- `0x180037758`
- `0x180062020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800620fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800620fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18006206d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800620a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18006206d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800620a2`

## string_xrefs

- `0x180062135`: `Expected GetComputerNameExW to fail (passed NULL buffer)`
- `0x1800620ea`: `Failed to get ComputerNameDnsFullyQualified in LocalSmbFileServer`

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
  std::vector<wchar_t>::vector<wchar_t>(lpBuffer, nSize);
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
0x180062020  mov     [rsp-8+arg_0], rbx
0x180062025  push    rbp
0x180062026  lea     rbp, [rsp-57h]
0x18006202b  sub     rsp, 0F0h
0x180062032  mov     rax, cs:__security_cookie
0x180062039  xor     rax, rsp
0x18006203c  mov     [rbp+57h+var_10], rax
0x180062040  mov     rbx, rdx
0x180062043  mov     [rbp+57h+var_A8], rdx
0x180062047  mov     [rbp+57h+var_CC], 0
0x18006204e  mov     rcx, rdx
0x180062051  call    ??0?$vector@U_NOTIFY_FILTER_AND_TYPE@@V?$allocator@U_NOTIFY_FILTER_AND_TYPE@@@std@@@std@@QEAA@XZ; std::vector<_NOTIFY_FILTER_AND_TYPE>::vector<_NOTIFY_FILTER_AND_TYPE>(void)
0x180062056  mov     [rbp+57h+var_CC], 1
0x18006205d  mov     [rbp+57h+nSize], 0
0x180062064  lea     r8, [rbp+57h+nSize]; nSize
0x180062068  xor     edx, edx; lpBuffer
0x18006206a  lea     ecx, [rdx+3]; NameType
0x18006206d  call    cs:__imp_GetComputerNameExW
0x180062073  test    eax, eax
0x180062075  jnz     loc_180062135
0x18006207b  mov     edx, [rbp+57h+nSize]
0x18006207e  lea     rcx, [rbp+57h+lpBuffer]
0x180062082  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x180062087  nop
0x180062088  mov     rax, [rbp+57h+var_B8]
0x18006208c  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x180062090  sub     rax, rdx
0x180062093  sar     rax, 1
0x180062096  mov     [rbp+57h+nSize], eax
0x180062099  lea     r8, [rbp+57h+nSize]; nSize
0x18006209d  mov     ecx, 3; NameType
0x1800620a2  call    cs:__imp_GetComputerNameExW
0x1800620a8  test    eax, eax
0x1800620aa  jz      short loc_1800620EA
0x1800620ac  mov     rcx, [rbp+57h+lpBuffer]
0x1800620b0  mov     [rbp+57h+var_C8], rcx
0x1800620b4  lea     rdx, [rbp+57h+var_C8]
0x1800620b8  mov     rcx, rbx
0x1800620bb  call    ??$emplace_back@AEBQEB_W@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEBQEB_W@Z; std::vector<std::wstring>::emplace_back<wchar_t const * const &>(wchar_t const * const &)
0x1800620c0  nop
0x1800620c1  lea     rcx, [rbp+57h+lpBuffer]
0x1800620c5  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800620ca  mov     rax, rbx
0x1800620cd  mov     rcx, [rbp+57h+var_10]
0x1800620d1  xor     rcx, rsp; StackCookie
0x1800620d4  call    __security_check_cookie
0x1800620d9  mov     rbx, [rsp+0F0h+arg_0]
0x1800620e1  add     rsp, 0F0h
0x1800620e8  pop     rbp
0x1800620e9  retn
0x1800620ea  lea     rdx, aFailedToGetCom_0; "Failed to get ComputerNameDnsFullyQuali"...
0x1800620f1  lea     rcx, [rbp+57h+var_A0]
0x1800620f5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800620fa  mov     rbx, rax
0x1800620fd  call    cs:__imp_GetLastError
0x180062103  mov     dword ptr [rbp+57h+var_C8], eax
0x180062106  mov     dword ptr [rbp+57h+var_C8+4], 0
0x18006210d  mov     r8, rbx
0x180062110  lea     rdx, [rbp+57h+var_C8]
0x180062114  lea     rcx, [rbp+57h+pExceptionObject]
0x180062118  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006211d  mov     [rbp+57h+var_CC], 5
0x180062124  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006212b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006212f  call    _CxxThrowException_0
0x180062135  lea     rdx, aExpectedGetcom; "Expected GetComputerNameExW to fail (pa"...
0x18006213c  lea     rcx, [rbp+57h+var_A0]
0x180062140  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180062145  nop
0x180062146  mov     [rbp+57h+var_C8], 54Fh
0x18006214e  mov     r8, rax
0x180062151  lea     rdx, [rbp+57h+var_C8]
0x180062155  lea     rcx, [rbp+57h+pExceptionObject]
0x180062159  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006215e  mov     [rbp+57h+var_CC], 3
0x180062165  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18006216c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180062170  call    _CxxThrowException_0
```
