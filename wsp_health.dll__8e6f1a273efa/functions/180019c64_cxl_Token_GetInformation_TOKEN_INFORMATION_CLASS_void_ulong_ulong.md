# cxl::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x180019c64`
- end: `0x180019d3a`
- name: `?GetInformation@Token@cxl@@QEAA_NW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z`
- size: `214`
- prototype: `bool __fastcall(cxl::Token *__hidden this, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, PDWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800198ec`
- `0x18003d758`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cde0`
- `0x18000ce84`
- `0x18000ea70`
- `0x180011184`
- `0x180019c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ca2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cf6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019c92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019c92`

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
      cxl::TextWriter::Write<22>(v8);
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
0x180019c64  push    rbx
0x180019c66  sub     rsp, 100h
0x180019c6d  mov     rax, cs:__security_cookie
0x180019c74  xor     rax, rsp
0x180019c77  mov     [rsp+108h+var_18], rax
0x180019c7f  mov     rax, [rsp+108h+arg_20]
0x180019c87  mov     bl, 1
0x180019c89  mov     [rsp+108h+ReturnLength], rax; ReturnLength
0x180019c8e  mov     rcx, [rcx+8]; TokenHandle
0x180019c92  call    cs:__imp_GetTokenInformation
0x180019c99  nop     dword ptr [rax+rax+00h]
0x180019c9e  test    eax, eax
0x180019ca0  jnz     short loc_180019CB5
0x180019ca2  call    cs:__imp_GetLastError
0x180019ca9  nop     dword ptr [rax+rax+00h]
0x180019cae  cmp     eax, 7Ah ; 'z'
0x180019cb1  jnz     short loc_180019CD1
0x180019cb3  xor     bl, bl
0x180019cb5  mov     al, bl
0x180019cb7  mov     rcx, [rsp+108h+var_18]
0x180019cbf  xor     rcx, rsp; StackCookie
0x180019cc2  call    __security_check_cookie
0x180019cc7  add     rsp, 100h
0x180019cce  pop     rbx
0x180019ccf  retn
0x180019cd1  lea     rcx, [rsp+108h+var_B0]
0x180019cd6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180019cdb  nop
0x180019cdc  lea     rdx, [rsp+108h+var_B0]
0x180019ce1  lea     rcx, [rsp+108h+var_D0]
0x180019ce6  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180019ceb  nop
0x180019cec  lea     rcx, [rsp+108h+var_D0]
0x180019cf1  call    ??$Write@$0BG@@TextWriter@cxl@@QEAAAEAV01@AEAY0BG@$$CBD@Z; cxl::TextWriter::Write<22>(char const (&)[22])
0x180019cf6  call    cs:__imp_GetLastError
0x180019cfd  nop     dword ptr [rax+rax+00h]
0x180019d02  mov     [rsp+108h+var_D8], eax
0x180019d06  mov     [rsp+108h+var_D4], 0
0x180019d0e  lea     r8, [rsp+108h+var_B0]
0x180019d13  lea     rdx, [rsp+108h+var_D8]
0x180019d18  lea     rcx, [rsp+108h+pExceptionObject]
0x180019d20  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180019d25  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180019d2c  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180019d34  call    _CxxThrowException_0
```
