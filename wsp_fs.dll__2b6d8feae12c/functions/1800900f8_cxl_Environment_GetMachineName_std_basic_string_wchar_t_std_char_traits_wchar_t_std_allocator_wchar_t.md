# cxl::Environment::GetMachineName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800900f8`
- end: `0x1800901bb`
- name: `?GetMachineName@Environment@cxl@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800901c4`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x180005e68`
- `0x18000d33c`
- `0x18000dd74`
- `0x180010e64`
- `0x1800900f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090144`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090139`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180090139`

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
0x1800900f8  push    rbx
0x1800900fa  sub     rsp, 0D0h
0x180090101  mov     rax, cs:__security_cookie
0x180090108  xor     rax, rsp
0x18009010b  mov     [rsp+0D8h+var_18], rax
0x180090113  mov     rbx, rcx
0x180090116  mov     edx, 40h ; '@'
0x18009011b  mov     [rsp+0D8h+nSize], edx
0x18009011f  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180090124  mov     rcx, rbx
0x180090127  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18009012c  lea     r8, [rsp+0D8h+nSize]; nSize
0x180090131  mov     rdx, rax; lpBuffer
0x180090134  mov     ecx, 1; NameType
0x180090139  call    cs:__imp_GetComputerNameExW
0x18009013f  cmp     eax, 1
0x180090142  jz      short loc_18009014E
0x180090144  call    cs:__imp_GetLastError
0x18009014a  mov     ebx, eax
0x18009014c  jmp     short loc_18009015C
0x18009014e  mov     edx, [rsp+0D8h+nSize]
0x180090152  mov     rcx, rbx
0x180090155  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18009015a  xor     ebx, ebx
0x18009015c  test    ebx, ebx
0x18009015e  jz      short loc_1800901A2
0x180090160  lea     rdx, aTrygetmachinen; "TryGetMachineName( buffer )"
0x180090167  lea     rcx, [rsp+0D8h+var_B0]
0x18009016c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180090171  nop
0x180090172  mov     [rsp+0D8h+nSize], ebx
0x180090176  mov     [rsp+0D8h+var_B4], 0
0x18009017e  mov     r8, rax
0x180090181  lea     rdx, [rsp+0D8h+nSize]
0x180090186  lea     rcx, [rsp+0D8h+pExceptionObject]
0x18009018b  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180090190  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180090197  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18009019c  call    _CxxThrowException_0
0x1800901a2  mov     rcx, [rsp+0D8h+var_18]
0x1800901aa  xor     rcx, rsp; StackCookie
0x1800901ad  call    __security_check_cookie
0x1800901b2  add     rsp, 0D0h
0x1800901b9  pop     rbx
0x1800901ba  retn
```
