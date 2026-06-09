# cxl::Token::DuplicateEx(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)

- ea: `0x180020d50`
- end: `0x180020e36`
- name: `?DuplicateEx@Token@cxl@@QEAAXPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z`
- size: `230`
- prototype: `void(cxl::Token *__hidden this, void *, unsigned int, struct _SECURITY_ATTRIBUTES *, enum _SECURITY_IMPERSONATION_LEVEL, enum _TOKEN_TYPE)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020e3c`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f120`
- `0x1800124ac`
- `0x180015be4`
- `0x180020d50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020dd6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180020d9a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180020d9a`

## string_xrefs

- `0x180020dc5`: `DuplicateTokenEx failed`

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
0x180020d50  push    rbx
0x180020d52  push    rsi
0x180020d53  push    rdi
0x180020d54  sub     rsp, 100h
0x180020d5b  mov     rax, cs:__security_cookie
0x180020d62  xor     rax, rsp
0x180020d65  mov     [rsp+118h+var_28], rax
0x180020d6d  mov     rsi, r9
0x180020d70  mov     rdi, rdx
0x180020d73  mov     rbx, rcx
0x180020d76  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180020d7b  lea     rax, [rbx+8]
0x180020d7f  mov     [rsp+118h+phNewToken], rax; phNewToken
0x180020d84  mov     r9d, 2; ImpersonationLevel
0x180020d8a  mov     [rsp+118h+TokenType], r9d; TokenType
0x180020d8f  mov     r8, rsi; lpTokenAttributes
0x180020d92  mov     edx, 2000000h; dwDesiredAccess
0x180020d97  mov     rcx, rdi; hExistingToken
0x180020d9a  call    cs:__imp_DuplicateTokenEx
0x180020da1  nop     dword ptr [rax+rax+00h]
0x180020da6  test    eax, eax
0x180020da8  jnz     short loc_180020E1A
0x180020daa  lea     rcx, [rsp+118h+var_C0]
0x180020daf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020db4  nop
0x180020db5  lea     rdx, [rsp+118h+var_C0]
0x180020dba  lea     rcx, [rsp+118h+var_E0]
0x180020dbf  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180020dc4  nop
0x180020dc5  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed"
0x180020dcc  lea     rcx, [rsp+118h+var_E0]
0x180020dd1  call    ??$WriteFmt@$0BI@@TextWriter@cxl@@QEAAAEAV01@AEAY0BI@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<24>(char const (&)[24],cxl::Format const &)
0x180020dd6  call    cs:__imp_GetLastError
0x180020ddd  nop     dword ptr [rax+rax+00h]
0x180020de2  mov     [rsp+118h+var_E8], eax
0x180020de6  mov     [rsp+118h+var_E4], 0
0x180020dee  lea     r8, [rsp+118h+var_C0]
0x180020df3  lea     rdx, [rsp+118h+var_E8]
0x180020df8  lea     rcx, [rsp+118h+pExceptionObject]
0x180020e00  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180020e05  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180020e0c  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180020e14  call    _CxxThrowException_0
0x180020e1a  mov     rcx, [rsp+118h+var_28]
0x180020e22  xor     rcx, rsp; StackCookie
0x180020e25  call    __security_check_cookie
0x180020e2a  add     rsp, 100h
0x180020e31  pop     rdi
0x180020e32  pop     rsi
0x180020e33  pop     rbx
0x180020e34  retn
```
