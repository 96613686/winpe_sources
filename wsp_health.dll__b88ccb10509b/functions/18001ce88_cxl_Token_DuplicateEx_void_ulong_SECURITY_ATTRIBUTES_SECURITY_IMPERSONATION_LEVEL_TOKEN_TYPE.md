# cxl::Token::DuplicateEx(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)

- ea: `0x18001ce88`
- end: `0x18001cf61`
- name: `?DuplicateEx@Token@cxl@@QEAAXPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z`
- size: `217`
- prototype: `void(cxl::Token *__hidden this, void *, unsigned int, struct _SECURITY_ATTRIBUTES *, enum _SECURITY_IMPERSONATION_LEVEL, enum _TOKEN_TYPE)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cf68`

## callees

- `0x180002ae0`
- `0x180003520`
- `0x18000ca34`
- `0x18000cad8`
- `0x18000e640`
- `0x180010ca4`
- `0x180013ec0`
- `0x18001ce88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf08`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001ced2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001ced2`

## string_xrefs

- `0x18001cef7`: `DuplicateTokenEx failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::Token::DuplicateEx(void **this, void *a2, __int64 a3, struct _SECURITY_ATTRIBUTES *a4)
{
  _DWORD v7[2]; // [rsp+30h] [rbp-E8h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE v9[40]; // [rsp+58h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+80h] [rbp-98h] BYREF

  cxl::Token::Clear((cxl::Token *)this);
  if ( !DuplicateTokenEx(a2, 0x2000000u, a4, SecurityImpersonation, TokenImpersonation, this + 1) )
  {
    std::wstring::wstring(v9);
    cxl::StringWriter::StringWriter(v8, v9);
    cxl::TextWriter::WriteFmt<24>((__int64)v8, (__int64)"DuplicateTokenEx failed");
    v7[0] = GetLastError();
    v7[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v7, v9);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001ce88  push    rbx
0x18001ce8a  push    rsi
0x18001ce8b  push    rdi
0x18001ce8c  sub     rsp, 100h
0x18001ce93  mov     rax, cs:__security_cookie
0x18001ce9a  xor     rax, rsp
0x18001ce9d  mov     [rsp+118h+var_28], rax
0x18001cea5  mov     rsi, r9
0x18001cea8  mov     rdi, rdx
0x18001ceab  mov     rbx, rcx
0x18001ceae  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001ceb3  lea     rax, [rbx+8]
0x18001ceb7  mov     [rsp+118h+phNewToken], rax; phNewToken
0x18001cebc  mov     r9d, 2; ImpersonationLevel
0x18001cec2  mov     [rsp+118h+TokenType], r9d; TokenType
0x18001cec7  mov     r8, rsi; lpTokenAttributes
0x18001ceca  mov     edx, 2000000h; dwDesiredAccess
0x18001cecf  mov     rcx, rdi; hExistingToken
0x18001ced2  call    cs:__imp_DuplicateTokenEx
0x18001ced8  test    eax, eax
0x18001ceda  jnz     short loc_18001CF46
0x18001cedc  lea     rcx, [rsp+118h+var_C0]
0x18001cee1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001cee6  nop
0x18001cee7  lea     rdx, [rsp+118h+var_C0]
0x18001ceec  lea     rcx, [rsp+118h+var_E0]
0x18001cef1  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001cef6  nop
0x18001cef7  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed"
0x18001cefe  lea     rcx, [rsp+118h+var_E0]
0x18001cf03  call    ??$WriteFmt@$0BI@@TextWriter@cxl@@QEAAAEAV01@AEAY0BI@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<24>(char const (&)[24],cxl::Format const &)
0x18001cf08  call    cs:__imp_GetLastError
0x18001cf0e  mov     [rsp+118h+var_E8], eax
0x18001cf12  mov     [rsp+118h+var_E4], 0
0x18001cf1a  lea     r8, [rsp+118h+var_C0]
0x18001cf1f  lea     rdx, [rsp+118h+var_E8]
0x18001cf24  lea     rcx, [rsp+118h+pExceptionObject]
0x18001cf2c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001cf31  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001cf38  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18001cf40  call    _CxxThrowException_0
0x18001cf46  mov     rcx, [rsp+118h+var_28]
0x18001cf4e  xor     rcx, rsp; StackCookie
0x18001cf51  call    __security_check_cookie
0x18001cf56  add     rsp, 100h
0x18001cf5d  pop     rdi
0x18001cf5e  pop     rsi
0x18001cf5f  pop     rbx
0x18001cf60  retn
```
