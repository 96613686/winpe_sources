# cxl::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x18001ce34`
- end: `0x18001cf11`
- name: `?GetInformation@Token@cxl@@QEAA_NW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z`
- size: `221`
- prototype: `bool __fastcall(cxl::Token *__hidden this, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, PDWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001cabc`
- `0x180072fb4`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f0c8`
- `0x1800124ac`
- `0x18001ce34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cecd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ce62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ce62`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall cxl::Token::GetInformation(
        HANDLE *this,
        TOKEN_INFORMATION_CLASS a2,
        void *a3,
        DWORD a4,
        PDWORD ReturnLength)
{
  char v5; // bl
  _DWORD v7[2]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v9[40]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+80h] [rbp-88h] BYREF

  v5 = 1;
  if ( !GetTokenInformation(this[1], a2, a3, a4, ReturnLength) )
  {
    if ( GetLastError() != 122 )
    {
      std::wstring::wstring(v9);
      cxl::StringWriter::StringWriter(v8, v9);
      cxl::TextWriter::Write<22>(v8, "GetInformation failed");
      v7[0] = GetLastError();
      v7[1] = 0;
      cxl::Exception::Exception(pExceptionObject, v7, v9);
      throw (cxl::Exception *)pExceptionObject;
    }
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18001ce34  push    rbx
0x18001ce36  sub     rsp, 100h
0x18001ce3d  mov     rax, cs:__security_cookie
0x18001ce44  xor     rax, rsp
0x18001ce47  mov     [rsp+108h+var_18], rax
0x18001ce4f  mov     rax, [rsp+108h+arg_20]
0x18001ce57  mov     bl, 1
0x18001ce59  mov     [rsp+108h+ReturnLength], rax; ReturnLength
0x18001ce5e  mov     rcx, [rcx+8]; TokenHandle
0x18001ce62  call    cs:__imp_GetTokenInformation
0x18001ce69  nop     dword ptr [rax+rax+00h]
0x18001ce6e  test    eax, eax
0x18001ce70  jnz     short loc_18001CE85
0x18001ce72  call    cs:__imp_GetLastError
0x18001ce79  nop     dword ptr [rax+rax+00h]
0x18001ce7e  cmp     eax, 7Ah ; 'z'
0x18001ce81  jnz     short loc_18001CEA1
0x18001ce83  xor     bl, bl
0x18001ce85  mov     al, bl
0x18001ce87  mov     rcx, [rsp+108h+var_18]
0x18001ce8f  xor     rcx, rsp; StackCookie
0x18001ce92  call    __security_check_cookie
0x18001ce97  add     rsp, 100h
0x18001ce9e  pop     rbx
0x18001ce9f  retn
0x18001cea1  lea     rcx, [rsp+108h+var_B0]
0x18001cea6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001ceab  nop
0x18001ceac  lea     rdx, [rsp+108h+var_B0]
0x18001ceb1  lea     rcx, [rsp+108h+var_D0]
0x18001ceb6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001cebb  nop
0x18001cebc  lea     rdx, aGetinformation; "GetInformation failed"
0x18001cec3  lea     rcx, [rsp+108h+var_D0]
0x18001cec8  call    ??$Write@$0BG@@TextWriter@cxl@@QEAAAEAV01@AEAY0BG@$$CBD@Z; cxl::TextWriter::Write<22>(char const (&)[22])
0x18001cecd  call    cs:__imp_GetLastError
0x18001ced4  nop     dword ptr [rax+rax+00h]
0x18001ced9  mov     [rsp+108h+var_D8], eax
0x18001cedd  mov     [rsp+108h+var_D4], 0
0x18001cee5  lea     r8, [rsp+108h+var_B0]
0x18001ceea  lea     rdx, [rsp+108h+var_D8]
0x18001ceef  lea     rcx, [rsp+108h+pExceptionObject]
0x18001cef7  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001cefc  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001cf03  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001cf0b  call    _CxxThrowException_0
```
