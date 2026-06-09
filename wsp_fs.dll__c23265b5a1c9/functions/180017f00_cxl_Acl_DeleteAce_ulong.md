# cxl::Acl::DeleteAce(ulong)

- ea: `0x180017f00`
- end: `0x180017fd3`
- name: `?DeleteAce@Acl@cxl@@QEAAXK@Z`
- size: `211`
- prototype: `void(cxl::Acl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800183b4`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f008`
- `0x1800124ac`
- `0x180017f00`
- `0x1800184e0`
- `0x180018600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f95`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180017f2f`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x180017f2f`

## string_xrefs

- `0x180017f84`: `DeleteAce failed`

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
    cxl::TextWriter::Write<17>(v5, "DeleteAce failed");
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
0x180017f00  mov     [rsp+arg_10], rbx
0x180017f05  push    rdi
0x180017f06  sub     rsp, 0F0h
0x180017f0d  mov     rax, cs:__security_cookie
0x180017f14  xor     rax, rsp
0x180017f17  mov     [rsp+0F8h+var_18], rax
0x180017f1f  mov     ebx, edx
0x180017f21  mov     rdi, rcx
0x180017f24  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x180017f29  mov     edx, ebx; dwAceIndex
0x180017f2b  mov     rcx, [rdi+10h]; pAcl
0x180017f2f  call    cs:__imp_DeleteAce
0x180017f36  nop     dword ptr [rax+rax+00h]
0x180017f3b  test    eax, eax
0x180017f3d  jz      short loc_180017F69
0x180017f3f  mov     rcx, rdi; this
0x180017f42  call    ?Repack@Acl@cxl@@AEAAXXZ; cxl::Acl::Repack(void)
0x180017f47  mov     rcx, [rsp+0F8h+var_18]
0x180017f4f  xor     rcx, rsp; StackCookie
0x180017f52  call    __security_check_cookie
0x180017f57  mov     rbx, [rsp+0F8h+arg_10]
0x180017f5f  add     rsp, 0F0h
0x180017f66  pop     rdi
0x180017f67  retn
0x180017f69  lea     rcx, [rsp+0F8h+var_B0]
0x180017f6e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017f73  nop
0x180017f74  lea     rdx, [rsp+0F8h+var_B0]
0x180017f79  lea     rcx, [rsp+0F8h+var_D0]
0x180017f7e  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180017f83  nop
0x180017f84  lea     rdx, aDeleteaceFaile; "DeleteAce failed"
0x180017f8b  lea     rcx, [rsp+0F8h+var_D0]
0x180017f90  call    ??$Write@$0BB@@TextWriter@cxl@@QEAAAEAV01@AEAY0BB@$$CBD@Z; cxl::TextWriter::Write<17>(char const (&)[17])
0x180017f95  call    cs:__imp_GetLastError
0x180017f9c  nop     dword ptr [rax+rax+00h]
0x180017fa1  mov     [rsp+0F8h+var_D8], eax
0x180017fa5  mov     [rsp+0F8h+var_D4], 0
0x180017fad  lea     r8, [rsp+0F8h+var_B0]
0x180017fb2  lea     rdx, [rsp+0F8h+var_D8]
0x180017fb7  lea     rcx, [rsp+0F8h+pExceptionObject]
0x180017fbc  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180017fc1  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180017fc8  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180017fcd  call    _CxxThrowException_0
```
