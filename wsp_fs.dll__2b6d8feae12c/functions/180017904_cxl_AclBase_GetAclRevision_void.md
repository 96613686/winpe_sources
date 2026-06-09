# cxl::AclBase::GetAclRevision(void)

- ea: `0x180017904`
- end: `0x1800179c9`
- name: `?GetAclRevision@AclBase@cxl@@QEBAKXZ`
- size: `197`
- prototype: `unsigned int __fastcall(cxl::AclBase *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017630`
- `0x180017ce0`
- `0x180017e4c`
- `0x1800180fc`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ed0c`
- `0x180012028`
- `0x180017904`
- `0x180017df4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017977`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180017945`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180017945`

## string_xrefs

- `0x180017967`: `GetAclInformation failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall cxl::AclBase::GetAclRevision(PACL *this)
{
  unsigned int pAclInformation; // [rsp+20h] [rbp-79h] BYREF
  _DWORD v4[3]; // [rsp+24h] [rbp-75h] BYREF
  _BYTE v5[32]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v6[32]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-29h] BYREF

  pAclInformation = 0;
  cxl::AclBase::ReportErrorIfEmpty((cxl::AclBase *)this);
  if ( !GetAclInformation(this[2], &pAclInformation, 4u, AclRevisionInformation) )
  {
    std::wstring::wstring(v6);
    cxl::StringWriter::StringWriter(v5, v6);
    cxl::TextWriter::WriteFmt<25>((__int64)v5, (__int64)"GetAclInformation failed");
    v4[0] = GetLastError();
    v4[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v4, v6);
    throw (cxl::Exception *)pExceptionObject;
  }
  return pAclInformation;
}

```

## disassembly

```asm
0x180017904  mov     [rsp-8+arg_8], rbx
0x180017909  push    rbp
0x18001790a  lea     rbp, [rsp-57h]
0x18001790f  sub     rsp, 0F0h
0x180017916  mov     rax, cs:__security_cookie
0x18001791d  xor     rax, rsp
0x180017920  mov     [rbp+57h+var_10], rax
0x180017924  mov     rbx, rcx
0x180017927  mov     [rbp+57h+pAclInformation], 0
0x18001792e  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x180017933  mov     r9d, 1; dwAclInformationClass
0x180017939  lea     r8d, [r9+3]; nAclInformationLength
0x18001793d  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180017941  mov     rcx, [rbx+10h]; pAcl
0x180017945  call    cs:__imp_GetAclInformation
0x18001794b  test    eax, eax
0x18001794d  jnz     short loc_1800179A9
0x18001794f  lea     rcx, [rbp+57h+var_A0]
0x180017953  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017958  nop
0x180017959  lea     rdx, [rbp+57h+var_A0]
0x18001795d  lea     rcx, [rbp+57h+var_C0]
0x180017961  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180017966  nop
0x180017967  lea     rdx, aGetaclinformat; "GetAclInformation failed"
0x18001796e  lea     rcx, [rbp+57h+var_C0]
0x180017972  call    ??$WriteFmt@$0BJ@@TextWriter@cxl@@QEAAAEAV01@AEAY0BJ@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<25>(char const (&)[25],cxl::Format const &)
0x180017977  call    cs:__imp_GetLastError
0x18001797d  mov     [rbp+57h+var_CC], eax
0x180017980  mov     [rbp+57h+var_C8], 0
0x180017987  lea     r8, [rbp+57h+var_A0]
0x18001798b  lea     rdx, [rbp+57h+var_CC]
0x18001798f  lea     rcx, [rbp+57h+pExceptionObject]
0x180017993  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180017998  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001799f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800179a3  call    _CxxThrowException_0
0x1800179a9  mov     eax, [rbp+57h+pAclInformation]
0x1800179ac  mov     rcx, [rbp+57h+var_10]
0x1800179b0  xor     rcx, rsp; StackCookie
0x1800179b3  call    __security_check_cookie
0x1800179b8  mov     rbx, [rsp+0F0h+arg_8]
0x1800179c0  add     rsp, 0F0h
0x1800179c7  pop     rbp
0x1800179c8  retn
```
