# cxl::Environment::GetMachineName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800804c4`
- end: `0x180080587`
- name: `?GetMachineName@Environment@cxl@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180080590`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000c9f0`
- `0x18000cad8`
- `0x18000d618`
- `0x18000fac4`
- `0x1800804c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080510`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180080505`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180080505`

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
  std::wstring::resize(a1, 64);
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
0x1800804c4  push    rbx
0x1800804c6  sub     rsp, 0D0h
0x1800804cd  mov     rax, cs:__security_cookie
0x1800804d4  xor     rax, rsp
0x1800804d7  mov     [rsp+0D8h+var_18], rax
0x1800804df  mov     rbx, rcx
0x1800804e2  mov     edx, 40h ; '@'
0x1800804e7  mov     [rsp+0D8h+nSize], edx
0x1800804eb  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800804f0  mov     rcx, rbx
0x1800804f3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800804f8  lea     r8, [rsp+0D8h+nSize]; nSize
0x1800804fd  mov     rdx, rax; lpBuffer
0x180080500  mov     ecx, 1; NameType
0x180080505  call    cs:__imp_GetComputerNameExW
0x18008050b  cmp     eax, 1
0x18008050e  jz      short loc_18008051A
0x180080510  call    cs:__imp_GetLastError
0x180080516  mov     ebx, eax
0x180080518  jmp     short loc_180080528
0x18008051a  mov     edx, [rsp+0D8h+nSize]
0x18008051e  mov     rcx, rbx
0x180080521  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180080526  xor     ebx, ebx
0x180080528  test    ebx, ebx
0x18008052a  jz      short loc_18008056E
0x18008052c  lea     rdx, aTrygetmachinen; "TryGetMachineName( buffer )"
0x180080533  lea     rcx, [rsp+0D8h+var_B0]
0x180080538  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008053d  nop
0x18008053e  mov     [rsp+0D8h+nSize], ebx
0x180080542  mov     [rsp+0D8h+var_B4], 0
0x18008054a  mov     r8, rax
0x18008054d  lea     rdx, [rsp+0D8h+nSize]
0x180080552  lea     rcx, [rsp+0D8h+pExceptionObject]
0x180080557  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18008055c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180080563  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180080568  call    _CxxThrowException_0
0x18008056e  mov     rcx, [rsp+0D8h+var_18]
0x180080576  xor     rcx, rsp; StackCookie
0x180080579  call    __security_check_cookie
0x18008057e  add     rsp, 0D0h
0x180080585  pop     rbx
0x180080586  retn
```
