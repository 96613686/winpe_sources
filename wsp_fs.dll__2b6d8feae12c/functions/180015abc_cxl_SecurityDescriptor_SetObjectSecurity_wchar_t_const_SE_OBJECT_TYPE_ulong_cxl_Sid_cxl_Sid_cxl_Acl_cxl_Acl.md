# cxl::SecurityDescriptor::SetObjectSecurity(wchar_t const *,_SE_OBJECT_TYPE,ulong,cxl::Sid *,cxl::Sid *,cxl::Acl *,cxl::Acl *)

- ea: `0x180015abc`
- end: `0x180015b95`
- name: `?SetObjectSecurity@SecurityDescriptor@cxl@@SAXPEB_WW4_SE_OBJECT_TYPE@@KPEAVSid@2@2PEAVAcl@2@3@Z`
- size: `217`
- prototype: `void __fastcall(WCHAR *, enum _SE_OBJECT_TYPE, __int64, struct cxl::Sid *, struct cxl::Sid *, struct cxl::Acl *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005f9a4`
- `0x180060d28`
- `0x180061784`
- `0x180061b48`

## callees

- `0x180002a70`
- `0x1800034a4`
- `0x18000d298`
- `0x18000d33c`
- `0x18000ecb4`
- `0x180012028`
- `0x180015abc`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180015b0c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x180015b0c`

## string_xrefs

- `0x180015b33`: `SetSecurityInfo failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall cxl::SecurityDescriptor::SetObjectSecurity(
        WCHAR *a1,
        enum _SE_OBJECT_TYPE a2,
        __int64 a3,
        struct cxl::Sid *a4,
        struct cxl::Sid *a5,
        struct cxl::Acl *a6)
{
  struct _ACL *pDacl; // rdx
  DWORD v7; // ebx
  _DWORD v8[2]; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v9[32]; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE v10[40]; // [rsp+68h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+90h] [rbp-88h] BYREF

  pDacl = 0;
  if ( a6 )
    pDacl = (struct _ACL *)*((_QWORD *)a6 + 2);
  v7 = SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
  if ( v7 )
  {
    std::wstring::wstring(v10);
    cxl::StringWriter::StringWriter(v9, v10);
    cxl::TextWriter::Write<23>(v9, "SetSecurityInfo failed");
    v8[0] = v7;
    v8[1] = 0;
    cxl::Exception::Exception(pExceptionObject, v8, v10);
    throw (cxl::Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180015abc  push    rbx
0x180015abe  sub     rsp, 110h
0x180015ac5  mov     rax, cs:__security_cookie
0x180015acc  xor     rax, rsp
0x180015acf  mov     [rsp+118h+var_18], rax
0x180015ad7  mov     rax, [rsp+118h+arg_28]
0x180015adf  xor     edx, edx
0x180015ae1  test    rax, rax
0x180015ae4  jz      short loc_180015AEA
0x180015ae6  mov     rdx, [rax+10h]
0x180015aea  mov     [rsp+118h+pSacl], 0; pSacl
0x180015af3  mov     [rsp+118h+pDacl], rdx; pDacl
0x180015af8  mov     [rsp+118h+psidGroup], 0; psidGroup
0x180015b01  xor     r9d, r9d; psidOwner
0x180015b04  lea     edx, [r9+1]; ObjectType
0x180015b08  lea     r8d, [r9+4]; SecurityInfo
0x180015b0c  call    cs:__imp_SetNamedSecurityInfoW
0x180015b12  mov     ebx, eax
0x180015b14  test    eax, eax
0x180015b16  jz      short loc_180015B7C
0x180015b18  lea     rcx, [rsp+118h+var_B0]
0x180015b1d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015b22  nop
0x180015b23  lea     rdx, [rsp+118h+var_B0]
0x180015b28  lea     rcx, [rsp+118h+var_D0]
0x180015b2d  call    ??0StringWriter@cxl@@QEAA@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::StringWriter::StringWriter(std::wstring &)
0x180015b32  nop
0x180015b33  lea     rdx, aSetsecurityinf; "SetSecurityInfo failed"
0x180015b3a  lea     rcx, [rsp+118h+var_D0]
0x180015b3f  call    ??$Write@$0BH@@TextWriter@cxl@@QEAAAEAV01@AEAY0BH@$$CBD@Z; cxl::TextWriter::Write<23>(char const (&)[23])
0x180015b44  mov     [rsp+118h+var_D8], ebx
0x180015b48  mov     [rsp+118h+var_D4], 0
0x180015b50  lea     r8, [rsp+118h+var_B0]
0x180015b55  lea     rdx, [rsp+118h+var_D8]
0x180015b5a  lea     rcx, [rsp+118h+pExceptionObject]
0x180015b62  call    ??0Exception@cxl@@QEAA@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Exception::Exception(cxl::ErrorCode const &,std::wstring const &)
0x180015b67  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x180015b6e  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180015b76  call    _CxxThrowException_0
0x180015b7c  mov     rcx, [rsp+118h+var_18]
0x180015b84  xor     rcx, rsp; StackCookie
0x180015b87  call    __security_check_cookie
0x180015b8c  add     rsp, 110h
0x180015b93  pop     rbx
0x180015b94  retn
```
