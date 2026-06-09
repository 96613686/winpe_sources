# cxl::Token::DuplicateEx(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)

- ea: `0x18001da10`
- end: `0x18001daf6`
- name: `?DuplicateEx@Token@cxl@@QEAAXPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z`
- size: `230`
- prototype: `void(cxl::Token *__hidden this, void *, unsigned int, struct _SECURITY_ATTRIBUTES *, enum _SECURITY_IMPERSONATION_LEVEL, enum _TOKEN_TYPE)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001dafc`

## callees

- `0x180002b50`
- `0x1800035c0`
- `0x18000cde0`
- `0x18000ce84`
- `0x18000ead0`
- `0x180011184`
- `0x180014620`
- `0x18001da10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da96`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001da5a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001da5a`

## string_xrefs

- `0x18001da85`: `DuplicateTokenEx failed`

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
    cxl::TextWriter::WriteFmt<24>(v8, "DuplicateTokenEx failed");
    v7[0] = GetLastError();
    v7[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v7, v9);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001da10  push    rbx
0x18001da12  push    rsi
0x18001da13  push    rdi
0x18001da14  sub     rsp, 100h
0x18001da1b  mov     rax, cs:__security_cookie
0x18001da22  xor     rax, rsp
0x18001da25  mov     [rsp+118h+var_28], rax
0x18001da2d  mov     rsi, r9
0x18001da30  mov     rdi, rdx
0x18001da33  mov     rbx, rcx
0x18001da36  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x18001da3b  lea     rax, [rbx+8]
0x18001da3f  mov     [rsp+118h+phNewToken], rax; phNewToken
0x18001da44  mov     r9d, 2; ImpersonationLevel
0x18001da4a  mov     [rsp+118h+TokenType], r9d; TokenType
0x18001da4f  mov     r8, rsi; lpTokenAttributes
0x18001da52  mov     edx, 2000000h; dwDesiredAccess
0x18001da57  mov     rcx, rdi; hExistingToken
0x18001da5a  call    cs:__imp_DuplicateTokenEx
0x18001da61  nop     dword ptr [rax+rax+00h]
0x18001da66  test    eax, eax
0x18001da68  jnz     short loc_18001DADA
0x18001da6a  lea     rcx, [rsp+118h+var_C0]
0x18001da6f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001da74  nop
0x18001da75  lea     rdx, [rsp+118h+var_C0]
0x18001da7a  lea     rcx, [rsp+118h+var_E0]
0x18001da7f  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001da84  nop
0x18001da85  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed"
0x18001da8c  lea     rcx, [rsp+118h+var_E0]
0x18001da91  call    ??$WriteFmt@$0BI@@TextWriter@cxl@@QEAAAEAV01@AEAY0BI@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<24>(char const (&)[24],cxl::Format const &)
0x18001da96  call    cs:__imp_GetLastError
0x18001da9d  nop     dword ptr [rax+rax+00h]
0x18001daa2  mov     [rsp+118h+var_E8], eax
0x18001daa6  mov     [rsp+118h+var_E4], 0
0x18001daae  lea     r8, [rsp+118h+var_C0]
0x18001dab3  lea     rdx, [rsp+118h+var_E8]
0x18001dab8  lea     rcx, [rsp+118h+pExceptionObject]
0x18001dac0  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001dac5  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001dacc  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18001dad4  call    _CxxThrowException_0
0x18001dada  mov     rcx, [rsp+118h+var_28]
0x18001dae2  xor     rcx, rsp; StackCookie
0x18001dae5  call    __security_check_cookie
0x18001daea  add     rsp, 100h
0x18001daf1  pop     rdi
0x18001daf2  pop     rsi
0x18001daf3  pop     rbx
0x18001daf4  retn
```
