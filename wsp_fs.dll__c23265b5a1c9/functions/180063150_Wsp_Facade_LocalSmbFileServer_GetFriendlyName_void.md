# Wsp::Facade::LocalSmbFileServer::GetFriendlyName(void)

- ea: `0x180063150`
- end: `0x18006328d`
- name: `?GetFriendlyName@LocalSmbFileServer@Facade@Wsp@@UEBA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x180014c94`
- `0x180026588`
- `0x180063150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006321c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006321c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180063187`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800631c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180063187`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800631c2`

## string_xrefs

- `0x180063209`: `Failed to get ComputerNameDnsHostname in LocalSmbFileServer`
- `0x180063253`: `Expected GetComputerNameExW to fail (passed NULL buffer)`

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
0x180063150  mov     [rsp-8+arg_0], rbx
0x180063155  push    rbp
0x180063156  lea     rbp, [rsp-57h]
0x18006315b  sub     rsp, 0F0h
0x180063162  mov     rax, cs:__security_cookie
0x180063169  xor     rax, rsp
0x18006316c  mov     [rbp+57h+var_10], rax
0x180063170  mov     rbx, rdx
0x180063173  mov     [rbp+57h+var_C8], rdx
0x180063177  mov     [rbp+57h+nSize], 0
0x18006317e  lea     r8, [rbp+57h+nSize]; nSize
0x180063182  xor     edx, edx; lpBuffer
0x180063184  lea     ecx, [rdx+1]; NameType
0x180063187  call    cs:__imp_GetComputerNameExW
0x18006318e  nop     dword ptr [rax+rax+00h]
0x180063193  test    eax, eax
0x180063195  jnz     loc_180063253
0x18006319b  mov     edx, [rbp+57h+nSize]
0x18006319e  lea     rcx, [rbp+57h+lpBuffer]
0x1800631a2  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x1800631a7  nop
0x1800631a8  mov     rax, [rbp+57h+var_B0]
0x1800631ac  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1800631b0  sub     rax, rdx
0x1800631b3  sar     rax, 1
0x1800631b6  mov     [rbp+57h+nSize], eax
0x1800631b9  lea     r8, [rbp+57h+nSize]; nSize
0x1800631bd  mov     ecx, 1; NameType
0x1800631c2  call    cs:__imp_GetComputerNameExW
0x1800631c9  nop     dword ptr [rax+rax+00h]
0x1800631ce  test    eax, eax
0x1800631d0  jz      short loc_180063209
0x1800631d2  mov     rdx, [rbp+57h+lpBuffer]
0x1800631d6  mov     rcx, rbx
0x1800631d9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800631de  nop
0x1800631df  lea     rcx, [rbp+57h+lpBuffer]
0x1800631e3  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800631e8  mov     rax, rbx
0x1800631eb  mov     rcx, [rbp+57h+var_10]
0x1800631ef  xor     rcx, rsp; StackCookie
0x1800631f2  call    __security_check_cookie
0x1800631f7  mov     rbx, [rsp+0F0h+arg_0]
0x1800631ff  add     rsp, 0F0h
0x180063206  pop     rbp
0x180063207  retn
0x180063209  lea     rdx, aFailedToGetCom; "Failed to get ComputerNameDnsHostname i"...
0x180063210  lea     rcx, [rbp+57h+var_A0]
0x180063214  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180063219  mov     rbx, rax
0x18006321c  call    cs:__imp_GetLastError
0x180063223  nop     dword ptr [rax+rax+00h]
0x180063228  mov     dword ptr [rbp+57h+var_C8], eax
0x18006322b  mov     dword ptr [rbp+57h+var_C8+4], 0
0x180063232  mov     r8, rbx
0x180063235  lea     rdx, [rbp+57h+var_C8]
0x180063239  lea     rcx, [rbp+57h+pExceptionObject]
0x18006323d  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180063242  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180063249  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006324d  call    _CxxThrowException_0
0x180063253  lea     rdx, aExpectedGetcom; "Expected GetComputerNameExW to fail (pa"...
0x18006325a  lea     rcx, [rbp+57h+var_A0]
0x18006325e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180063263  nop
0x180063264  mov     [rbp+57h+var_C8], 54Fh
0x18006326c  mov     r8, rax
0x18006326f  lea     rdx, [rbp+57h+var_C8]
0x180063273  lea     rcx, [rbp+57h+pExceptionObject]
0x180063277  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18006327c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180063283  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180063287  call    _CxxThrowException_0
```
