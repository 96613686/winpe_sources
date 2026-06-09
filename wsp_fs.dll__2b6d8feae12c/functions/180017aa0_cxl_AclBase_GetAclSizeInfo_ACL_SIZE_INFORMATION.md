# cxl::AclBase::GetAclSizeInfo(_ACL_SIZE_INFORMATION *)

- ea: `0x180017aa0`
- end: `0x180017b6a`
- name: `?GetAclSizeInfo@AclBase@cxl@@QEBAXPEAU_ACL_SIZE_INFORMATION@@@Z`
- size: `202`
- prototype: `void(cxl::AclBase *__hidden this, struct _ACL_SIZE_INFORMATION *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800178c0`
- `0x180017b70`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ed0c`
- `0x180012028`
- `0x180017aa0`
- `0x180017df4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b11`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180017adb`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180017adb`

## string_xrefs

- `0x180017b00`: `GetAclInformation failed`

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
    cxl::TextWriter::WriteFmt<25>((__int64)v5, (__int64)"GetAclInformation failed");
    v4[0] = GetLastError();
    v4[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v4, v6);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180017aa0  mov     [rsp+arg_10], rbx
0x180017aa5  push    rdi
0x180017aa6  sub     rsp, 0F0h
0x180017aad  mov     rax, cs:__security_cookie
0x180017ab4  xor     rax, rsp
0x180017ab7  mov     [rsp+0F8h+var_18], rax
0x180017abf  mov     rdi, rdx
0x180017ac2  mov     rbx, rcx
0x180017ac5  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x180017aca  mov     r9d, 2; dwAclInformationClass
0x180017ad0  lea     r8d, [r9+0Ah]; nAclInformationLength
0x180017ad4  mov     rdx, rdi; pAclInformation
0x180017ad7  mov     rcx, [rbx+10h]; pAcl
0x180017adb  call    cs:__imp_GetAclInformation
0x180017ae1  test    eax, eax
0x180017ae3  jnz     short loc_180017B49
0x180017ae5  lea     rcx, [rsp+0F8h+var_B0]
0x180017aea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017aef  nop
0x180017af0  lea     rdx, [rsp+0F8h+var_B0]
0x180017af5  lea     rcx, [rsp+0F8h+var_D0]
0x180017afa  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180017aff  nop
0x180017b00  lea     rdx, aGetaclinformat; "GetAclInformation failed"
0x180017b07  lea     rcx, [rsp+0F8h+var_D0]
0x180017b0c  call    ??$WriteFmt@$0BJ@@TextWriter@cxl@@QEAAAEAV01@AEAY0BJ@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<25>(char const (&)[25],cxl::Format const &)
0x180017b11  call    cs:__imp_GetLastError
0x180017b17  mov     [rsp+0F8h+var_D8], eax
0x180017b1b  mov     [rsp+0F8h+var_D4], 0
0x180017b23  lea     r8, [rsp+0F8h+var_B0]
0x180017b28  lea     rdx, [rsp+0F8h+var_D8]
0x180017b2d  lea     rcx, [rsp+0F8h+pExceptionObject]
0x180017b32  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180017b37  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180017b3e  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180017b43  call    _CxxThrowException_0
0x180017b49  mov     rcx, [rsp+0F8h+var_18]
0x180017b51  xor     rcx, rsp; StackCookie
0x180017b54  call    __security_check_cookie
0x180017b59  mov     rbx, [rsp+0F8h+arg_10]
0x180017b61  add     rsp, 0F0h
0x180017b68  pop     rdi
0x180017b69  retn
```
