# cxl::Token::GetInformation(_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x180019274`
- end: `0x180019337`
- name: `?GetInformation@Token@cxl@@QEAA_NW4_TOKEN_INFORMATION_CLASS@@PEAXKPEAK@Z`
- size: `195`
- prototype: `bool __fastcall(cxl::Token *__hidden this, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, PDWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018f1c`
- `0x18003c15c`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000ca34`
- `0x18000cad8`
- `0x18000e5e0`
- `0x180010ca4`
- `0x180019274`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800192a2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800192a2`

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
      cxl::TextWriter::Write<22>((__int64)v8);
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
0x180019274  push    rbx
0x180019276  sub     rsp, 100h
0x18001927d  mov     rax, cs:__security_cookie
0x180019284  xor     rax, rsp
0x180019287  mov     [rsp+108h+var_18], rax
0x18001928f  mov     rax, [rsp+108h+arg_20]
0x180019297  mov     bl, 1
0x180019299  mov     [rsp+108h+ReturnLength], rax; ReturnLength
0x18001929e  mov     rcx, [rcx+8]; TokenHandle
0x1800192a2  call    cs:__imp_GetTokenInformation
0x1800192a8  test    eax, eax
0x1800192aa  jnz     short loc_1800192B9
0x1800192ac  call    cs:__imp_GetLastError
0x1800192b2  cmp     eax, 7Ah ; 'z'
0x1800192b5  jnz     short loc_1800192D4
0x1800192b7  xor     bl, bl
0x1800192b9  mov     al, bl
0x1800192bb  mov     rcx, [rsp+108h+var_18]
0x1800192c3  xor     rcx, rsp; StackCookie
0x1800192c6  call    __security_check_cookie
0x1800192cb  add     rsp, 100h
0x1800192d2  pop     rbx
0x1800192d3  retn
0x1800192d4  lea     rcx, [rsp+108h+var_B0]
0x1800192d9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800192de  nop
0x1800192df  lea     rdx, [rsp+108h+var_B0]
0x1800192e4  lea     rcx, [rsp+108h+var_D0]
0x1800192e9  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800192ee  nop
0x1800192ef  lea     rcx, [rsp+108h+var_D0]
0x1800192f4  call    ??$Write@$0BG@@TextWriter@cxl@@QEAAAEAV01@AEAY0BG@$$CBD@Z; cxl::TextWriter::Write<22>(char const (&)[22])
0x1800192f9  call    cs:__imp_GetLastError
0x1800192ff  mov     [rsp+108h+var_D8], eax
0x180019303  mov     [rsp+108h+var_D4], 0
0x18001930b  lea     r8, [rsp+108h+var_B0]
0x180019310  lea     rdx, [rsp+108h+var_D8]
0x180019315  lea     rcx, [rsp+108h+pExceptionObject]
0x18001931d  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180019322  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180019329  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180019331  call    _CxxThrowException_0
```
