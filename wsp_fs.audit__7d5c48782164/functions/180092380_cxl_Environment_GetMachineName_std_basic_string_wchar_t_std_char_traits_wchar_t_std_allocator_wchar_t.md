# cxl::Environment::GetMachineName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180092380`
- end: `0x180092450`
- name: `?GetMachineName@Environment@cxl@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180092458`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x180005fdc`
- `0x18000d6a4`
- `0x18000e14c`
- `0x1800112e4`
- `0x180092380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800923d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800923d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800923c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800923c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall cxl::Environment::GetMachineName(__int64 a1)
{
  WCHAR *v2; // rax
  DWORD result; // eax
  DWORD v4; // ebx
  __int64 v5; // rax
  DWORD nSize[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v7[40]; // [rsp+28h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+50h] [rbp-88h] BYREF

  nSize[0] = 64;
  ((void (*)(void))std::wstring::resize)();
  v2 = (WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
  if ( GetComputerNameExW(ComputerNameDnsHostname, v2, nSize) )
  {
    result = std::wstring::resize(a1, nSize[0]);
    v4 = 0;
  }
  else
  {
    result = GetLastError();
    v4 = result;
  }
  if ( v4 )
  {
    v5 = std::wstring::wstring(v7, L"TryGetMachineName( buffer )");
    nSize[0] = v4;
    nSize[1] = 0;
    cxl::Exception::Exception(pExceptionObject, nSize, v5);
    throw (cxl::Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180092380  push    rbx
0x180092382  sub     rsp, 0D0h
0x180092389  mov     rax, cs:__security_cookie
0x180092390  xor     rax, rsp
0x180092393  mov     [rsp+0D8h+var_18], rax
0x18009239b  mov     rbx, rcx
0x18009239e  mov     edx, 40h ; '@'
0x1800923a3  mov     [rsp+0D8h+nSize], edx
0x1800923a7  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800923ac  mov     rcx, rbx
0x1800923af  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800923b4  lea     r8, [rsp+0D8h+nSize]; nSize
0x1800923b9  mov     rdx, rax; lpBuffer
0x1800923bc  mov     ecx, 1; NameType
0x1800923c1  call    cs:__imp_GetComputerNameExW
0x1800923c8  nop     dword ptr [rax+rax+00h]
0x1800923cd  cmp     eax, 1
0x1800923d0  jz      short loc_1800923E2
0x1800923d2  call    cs:__imp_GetLastError
0x1800923d9  nop     dword ptr [rax+rax+00h]
0x1800923de  mov     ebx, eax
0x1800923e0  jmp     short loc_1800923F0
0x1800923e2  mov     edx, [rsp+0D8h+nSize]
0x1800923e6  mov     rcx, rbx
0x1800923e9  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800923ee  xor     ebx, ebx
0x1800923f0  test    ebx, ebx
0x1800923f2  jz      short loc_180092436
0x1800923f4  lea     rdx, aTrygetmachinen; "TryGetMachineName( buffer )"
0x1800923fb  lea     rcx, [rsp+0D8h+var_B0]
0x180092400  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180092405  nop
0x180092406  mov     [rsp+0D8h+nSize], ebx
0x18009240a  mov     [rsp+0D8h+var_B4], 0
0x180092412  mov     r8, rax
0x180092415  lea     rdx, [rsp+0D8h+nSize]
0x18009241a  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18009241f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180092424  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18009242b  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180092430  call    _CxxThrowException_0
0x180092436  mov     rcx, [rsp+0D8h+var_18]
0x18009243e  xor     rcx, rsp; StackCookie
0x180092441  call    __security_check_cookie
0x180092446  add     rsp, 0D0h
0x18009244d  pop     rbx
0x18009244e  retn
```
