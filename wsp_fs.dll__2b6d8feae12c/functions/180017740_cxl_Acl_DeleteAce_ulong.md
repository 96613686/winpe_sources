# cxl::Acl::DeleteAce(ulong)

- ea: `0x180017740`
- end: `0x180017806`
- name: `?DeleteAce@Acl@cxl@@QEAAXK@Z`
- size: `198`
- prototype: `void(cxl::Acl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017bb4`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ebc8`
- `0x180012028`
- `0x180017740`
- `0x180017ce0`
- `0x180017df4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177ce`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18001776f`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18001776f`

## string_xrefs

- `0x1800177bd`: `DeleteAce failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::Acl::DeleteAce(PACL *this, DWORD a2)
{
  _DWORD v4[2]; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v5[32]; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v6[40]; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-88h] BYREF

  cxl::AclBase::ReportErrorIfEmpty((cxl::AclBase *)this);
  if ( !DeleteAce(this[2], a2) )
  {
    std::wstring::wstring(v6);
    cxl::StringWriter::StringWriter(v5, v6);
    cxl::TextWriter::Write<17>((__int64)v5, (__int64)"DeleteAce failed");
    v4[0] = GetLastError();
    v4[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v4, v6);
    throw (cxl::Exception *)pExceptionObject;
  }
  cxl::Acl::Repack((cxl::Acl *)this);
}

```

## disassembly

```asm
0x180017740  mov     [rsp+arg_10], rbx
0x180017745  push    rdi
0x180017746  sub     rsp, 0F0h
0x18001774d  mov     rax, cs:__security_cookie
0x180017754  xor     rax, rsp
0x180017757  mov     [rsp+0F8h+var_18], rax
0x18001775f  mov     ebx, edx
0x180017761  mov     rdi, rcx
0x180017764  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x180017769  mov     edx, ebx; dwAceIndex
0x18001776b  mov     rcx, [rdi+10h]; pAcl
0x18001776f  call    cs:__imp_DeleteAce
0x180017775  test    eax, eax
0x180017777  jz      short loc_1800177A2
0x180017779  mov     rcx, rdi; this
0x18001777c  call    ?Repack@Acl@cxl@@AEAAXXZ; cxl::Acl::Repack(void)
0x180017781  mov     rcx, [rsp+0F8h+var_18]
0x180017789  xor     rcx, rsp; StackCookie
0x18001778c  call    __security_check_cookie
0x180017791  mov     rbx, [rsp+0F8h+arg_10]
0x180017799  add     rsp, 0F0h
0x1800177a0  pop     rdi
0x1800177a1  retn
0x1800177a2  lea     rcx, [rsp+0F8h+var_B0]
0x1800177a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800177ac  nop
0x1800177ad  lea     rdx, [rsp+0F8h+var_B0]
0x1800177b2  lea     rcx, [rsp+0F8h+var_D0]
0x1800177b7  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800177bc  nop
0x1800177bd  lea     rdx, aDeleteaceFaile; "DeleteAce failed"
0x1800177c4  lea     rcx, [rsp+0F8h+var_D0]
0x1800177c9  call    ??$Write@$0BB@@TextWriter@cxl@@QEAAAEAV01@AEAY0BB@$$CBD@Z; cxl::TextWriter::Write<17>(char const (&)[17])
0x1800177ce  call    cs:__imp_GetLastError
0x1800177d4  mov     [rsp+0F8h+var_D8], eax
0x1800177d8  mov     [rsp+0F8h+var_D4], 0
0x1800177e0  lea     r8, [rsp+0F8h+var_B0]
0x1800177e5  lea     rdx, [rsp+0F8h+var_D8]
0x1800177ea  lea     rcx, [rsp+0F8h+pExceptionObject]
0x1800177ef  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x1800177f4  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800177fb  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180017800  call    _CxxThrowException_0
```
