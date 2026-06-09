# cxl::Token::DuplicateEx(void *,ulong,_SECURITY_ATTRIBUTES *,_SECURITY_IMPERSONATION_LEVEL,_TOKEN_TYPE)

- ea: `0x1800200d8`
- end: `0x1800201b1`
- name: `?DuplicateEx@Token@cxl@@QEAAXPEAXKPEAU_SECURITY_ATTRIBUTES@@W4_SECURITY_IMPERSONATION_LEVEL@@W4_TOKEN_TYPE@@@Z`
- size: `217`
- prototype: `void(cxl::Token *__hidden this, void *, unsigned int, struct _SECURITY_ATTRIBUTES *, enum _SECURITY_IMPERSONATION_LEVEL, enum _TOKEN_TYPE)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800201b8`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ece0`
- `0x180012028`
- `0x1800154e0`
- `0x1800200d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020158`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180020122`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180020122`

## string_xrefs

- `0x180020147`: `DuplicateTokenEx failed`

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
0x1800200d8  push    rbx
0x1800200da  push    rsi
0x1800200db  push    rdi
0x1800200dc  sub     rsp, 100h
0x1800200e3  mov     rax, cs:__security_cookie
0x1800200ea  xor     rax, rsp
0x1800200ed  mov     [rsp+118h+var_28], rax
0x1800200f5  mov     rsi, r9
0x1800200f8  mov     rdi, rdx
0x1800200fb  mov     rbx, rcx
0x1800200fe  call    ?Clear@Token@cxl@@QEAAXXZ; cxl::Token::Clear(void)
0x180020103  lea     rax, [rbx+8]
0x180020107  mov     [rsp+118h+phNewToken], rax; phNewToken
0x18002010c  mov     r9d, 2; ImpersonationLevel
0x180020112  mov     [rsp+118h+TokenType], r9d; TokenType
0x180020117  mov     r8, rsi; lpTokenAttributes
0x18002011a  mov     edx, 2000000h; dwDesiredAccess
0x18002011f  mov     rcx, rdi; hExistingToken
0x180020122  call    cs:__imp_DuplicateTokenEx
0x180020128  test    eax, eax
0x18002012a  jnz     short loc_180020196
0x18002012c  lea     rcx, [rsp+118h+var_C0]
0x180020131  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020136  nop
0x180020137  lea     rdx, [rsp+118h+var_C0]
0x18002013c  lea     rcx, [rsp+118h+var_E0]
0x180020141  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180020146  nop
0x180020147  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed"
0x18002014e  lea     rcx, [rsp+118h+var_E0]
0x180020153  call    ??$WriteFmt@$0BI@@TextWriter@cxl@@QEAAAEAV01@AEAY0BI@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<24>(char const (&)[24],cxl::Format const &)
0x180020158  call    cs:__imp_GetLastError
0x18002015e  mov     [rsp+118h+var_E8], eax
0x180020162  mov     [rsp+118h+var_E4], 0
0x18002016a  lea     r8, [rsp+118h+var_C0]
0x18002016f  lea     rdx, [rsp+118h+var_E8]
0x180020174  lea     rcx, [rsp+118h+pExceptionObject]
0x18002017c  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180020181  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180020188  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180020190  call    _CxxThrowException_0
0x180020196  mov     rcx, [rsp+118h+var_28]
0x18002019e  xor     rcx, rsp; StackCookie
0x1800201a1  call    __security_check_cookie
0x1800201a6  add     rsp, 100h
0x1800201ad  pop     rdi
0x1800201ae  pop     rsi
0x1800201af  pop     rbx
0x1800201b0  retn
```
