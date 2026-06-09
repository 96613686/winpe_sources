# cxl::AclBase::GetAclSizeInfo(_ACL_SIZE_INFORMATION *)

- ea: `0x18001828c`
- end: `0x180018363`
- name: `?GetAclSizeInfo@AclBase@cxl@@QEBAXPEAU_ACL_SIZE_INFORMATION@@@Z`
- size: `215`
- prototype: `void(cxl::AclBase *__hidden this, struct _ACL_SIZE_INFORMATION *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001809c`
- `0x18001836c`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f14c`
- `0x1800124ac`
- `0x18001828c`
- `0x180018600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018303`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800182c7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800182c7`

## string_xrefs

- `0x1800182f2`: `GetAclInformation failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::AclBase::GetAclSizeInfo(PACL *this, struct _ACL_SIZE_INFORMATION *a2)
{
  _DWORD v4[2]; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v5[32]; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE v6[40]; // [rsp+48h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-88h] BYREF

  cxl::AclBase::ReportErrorIfEmpty((cxl::AclBase *)this);
  if ( !GetAclInformation(this[2], a2, 0xCu, AclSizeInformation) )
  {
    std::wstring::wstring(v6);
    cxl::StringWriter::StringWriter(v5, v6);
    cxl::TextWriter::WriteFmt<25>(v5, "GetAclInformation failed");
    v4[0] = GetLastError();
    v4[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v4, v6);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001828c  mov     [rsp+arg_10], rbx
0x180018291  push    rdi
0x180018292  sub     rsp, 0F0h
0x180018299  mov     rax, cs:__security_cookie
0x1800182a0  xor     rax, rsp
0x1800182a3  mov     [rsp+0F8h+var_18], rax
0x1800182ab  mov     rdi, rdx
0x1800182ae  mov     rbx, rcx
0x1800182b1  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x1800182b6  mov     r9d, 2; dwAclInformationClass
0x1800182bc  lea     r8d, [r9+0Ah]; nAclInformationLength
0x1800182c0  mov     rdx, rdi; pAclInformation
0x1800182c3  mov     rcx, [rbx+10h]; pAcl
0x1800182c7  call    cs:__imp_GetAclInformation
0x1800182ce  nop     dword ptr [rax+rax+00h]
0x1800182d3  test    eax, eax
0x1800182d5  jnz     short loc_180018341
0x1800182d7  lea     rcx, [rsp+0F8h+var_B0]
0x1800182dc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800182e1  nop
0x1800182e2  lea     rdx, [rsp+0F8h+var_B0]
0x1800182e7  lea     rcx, [rsp+0F8h+var_D0]
0x1800182ec  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x1800182f1  nop
0x1800182f2  lea     rdx, aGetaclinformat; "GetAclInformation failed"
0x1800182f9  lea     rcx, [rsp+0F8h+var_D0]
0x1800182fe  call    ??$WriteFmt@$0BJ@@TextWriter@cxl@@QEAAAEAV01@AEAY0BJ@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<25>(char const (&)[25],cxl::Format const &)
0x180018303  call    cs:__imp_GetLastError
0x18001830a  nop     dword ptr [rax+rax+00h]
0x18001830f  mov     [rsp+0F8h+var_D8], eax
0x180018313  mov     [rsp+0F8h+var_D4], 0
0x18001831b  lea     r8, [rsp+0F8h+var_B0]
0x180018320  lea     rdx, [rsp+0F8h+var_D8]
0x180018325  lea     rcx, [rsp+0F8h+pExceptionObject]
0x18001832a  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x18001832f  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180018336  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18001833b  call    _CxxThrowException_0
0x180018341  mov     rcx, [rsp+0F8h+var_18]
0x180018349  xor     rcx, rsp; StackCookie
0x18001834c  call    __security_check_cookie
0x180018351  mov     rbx, [rsp+0F8h+arg_10]
0x180018359  add     rsp, 0F0h
0x180018360  pop     rdi
0x180018361  retn
```
