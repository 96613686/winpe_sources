# cxl::Environment::GetMachineName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180082888`
- end: `0x180082958`
- name: `?GetMachineName@Environment@cxl@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180082960`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cd9c`
- `0x18000ce84`
- `0x18000da34`
- `0x18000ffa4`
- `0x180082888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800828da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800828da`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800828c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800828c9`

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
0x180082888  push    rbx
0x18008288a  sub     rsp, 0D0h
0x180082891  mov     rax, cs:__security_cookie
0x180082898  xor     rax, rsp
0x18008289b  mov     [rsp+0D8h+var_18], rax
0x1800828a3  mov     rbx, rcx
0x1800828a6  mov     edx, 40h ; '@'
0x1800828ab  mov     [rsp+0D8h+nSize], edx
0x1800828af  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800828b4  mov     rcx, rbx
0x1800828b7  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800828bc  lea     r8, [rsp+0D8h+nSize]; nSize
0x1800828c1  mov     rdx, rax; lpBuffer
0x1800828c4  mov     ecx, 1; NameType
0x1800828c9  call    cs:__imp_GetComputerNameExW
0x1800828d0  nop     dword ptr [rax+rax+00h]
0x1800828d5  cmp     eax, 1
0x1800828d8  jz      short loc_1800828EA
0x1800828da  call    cs:__imp_GetLastError
0x1800828e1  nop     dword ptr [rax+rax+00h]
0x1800828e6  mov     ebx, eax
0x1800828e8  jmp     short loc_1800828F8
0x1800828ea  mov     edx, [rsp+0D8h+nSize]
0x1800828ee  mov     rcx, rbx
0x1800828f1  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800828f6  xor     ebx, ebx
0x1800828f8  test    ebx, ebx
0x1800828fa  jz      short loc_18008293E
0x1800828fc  lea     rdx, aTrygetmachinen; "TryGetMachineName( buffer )"
0x180082903  lea     rcx, [rsp+0D8h+var_B0]
0x180082908  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008290d  nop
0x18008290e  mov     [rsp+0D8h+nSize], ebx
0x180082912  mov     [rsp+0D8h+var_B4], 0
0x18008291a  mov     r8, rax
0x18008291d  lea     rdx, [rsp+0D8h+nSize]
0x180082922  lea     rcx, [rsp+0D8h+pExceptionObject]
0x180082927  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18008292c  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180082933  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180082938  call    _CxxThrowException_0
0x18008293e  mov     rcx, [rsp+0D8h+var_18]
0x180082946  xor     rcx, rsp; StackCookie
0x180082949  call    __security_check_cookie
0x18008294e  add     rsp, 0D0h
0x180082955  pop     rbx
0x180082956  retn
```
