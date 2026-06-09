# cxl::AclBase::GetAclRevision(void)

- ea: `0x1800180e4`
- end: `0x1800181b6`
- name: `?GetAclRevision@AclBase@cxl@@QEBAKXZ`
- size: `210`
- prototype: `unsigned int __fastcall(cxl::AclBase *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017de4`
- `0x1800184e0`
- `0x180018658`
- `0x180018938`

## callees

- `0x180002ad0`
- `0x180003534`
- `0x18000d600`
- `0x18000d6a4`
- `0x18000f14c`
- `0x1800124ac`
- `0x1800180e4`
- `0x180018600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001815d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001815d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180018125`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180018125`

## string_xrefs

- `0x18001814d`: `GetAclInformation failed`

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
    cxl::TextWriter::WriteFmt<25>(v5, "GetAclInformation failed");
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
0x1800180e4  mov     [rsp-8+arg_8], rbx
0x1800180e9  push    rbp
0x1800180ea  lea     rbp, [rsp-57h]
0x1800180ef  sub     rsp, 0F0h
0x1800180f6  mov     rax, cs:__security_cookie
0x1800180fd  xor     rax, rsp
0x180018100  mov     [rbp+57h+var_10], rax
0x180018104  mov     rbx, rcx
0x180018107  mov     [rbp+57h+pAclInformation], 0
0x18001810e  call    ?ReportErrorIfEmpty@AclBase@cxl@@IEBAXXZ; cxl::AclBase::ReportErrorIfEmpty(void)
0x180018113  mov     r9d, 1; dwAclInformationClass
0x180018119  lea     r8d, [r9+3]; nAclInformationLength
0x18001811d  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180018121  mov     rcx, [rbx+10h]; pAcl
0x180018125  call    cs:__imp_GetAclInformation
0x18001812c  nop     dword ptr [rax+rax+00h]
0x180018131  test    eax, eax
0x180018133  jnz     short loc_180018195
0x180018135  lea     rcx, [rbp+57h+var_A0]
0x180018139  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001813e  nop
0x18001813f  lea     rdx, [rbp+57h+var_A0]
0x180018143  lea     rcx, [rbp+57h+var_C0]
0x180018147  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x18001814c  nop
0x18001814d  lea     rdx, aGetaclinformat; "GetAclInformation failed"
0x180018154  lea     rcx, [rbp+57h+var_C0]
0x180018158  call    ??$WriteFmt@$0BJ@@TextWriter@cxl@@QEAAAEAV01@AEAY0BJ@$$CBDAEBUFormat@1@@Z; cxl::TextWriter::WriteFmt<25>(char const (&)[25],cxl::Format const &)
0x18001815d  call    cs:__imp_GetLastError
0x180018164  nop     dword ptr [rax+rax+00h]
0x180018169  mov     [rbp+57h+var_CC], eax
0x18001816c  mov     [rbp+57h+var_C8], 0
0x180018173  lea     r8, [rbp+57h+var_A0]
0x180018177  lea     rdx, [rbp+57h+var_CC]
0x18001817b  lea     rcx, [rbp+57h+pExceptionObject]
0x18001817f  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180018184  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001818b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001818f  call    _CxxThrowException_0
0x180018195  mov     eax, [rbp+57h+pAclInformation]
0x180018198  mov     rcx, [rbp+57h+var_10]
0x18001819c  xor     rcx, rsp; StackCookie
0x18001819f  call    __security_check_cookie
0x1800181a4  mov     rbx, [rsp+0F0h+arg_8]
0x1800181ac  add     rsp, 0F0h
0x1800181b3  pop     rbp
0x1800181b4  retn
```
